---
apple-notes-id: 6CC0729C-AE70-4DFE-948D-98914BF9DF7E
---
## Escrevendo o esqueleto do arquivo de testes
Abra o arquivo *aws_sqs_spec.rb* e ponha os seguintes comandos:
require 'spec_helper.rb'
describe "AWS::SQS" do

  let(:queue_url){"https://sqs.us-west-2.amazonaws.com/943154236803/gabrielzuqueto_eti_br"}
  let(:queue_name){:gabrielzuqueto_eti_br}

  before do
    @client_aws_sqs = Aws::SQS::Client.new
  end
end
Na primeira linha, a gente está carregando o arquivo de configuração do rspec no nosso teste.
require 'spec_helper.rb'
Após iniciamos o bloco geral dos nossos testes:
describe "AWS::SQS" do

end
Dentro do bloco, definimos 2 variáveis de instância, que vão nos ajudar a criar um padrão.
  let(:queue_url){"https://sqs.us-west-2.amazonaws.com/943154236803/gabrielzuqueto_eti_br"}
  let(:queue_name){:gabrielzuqueto_eti_br}
Daí, criamos um bloco que será executado, antes de cada teste posto dentro do bloco geral:
  before do
    @client_aws_sqs = Aws::SQS::Client.new
  end
Adicionamos dentro do bloco *before*, uma variável global chamada *client_aws_sqs* que recebe uma instância do Aws::SQS::Client.
A partir desta variável global, faremos nossos testes.
## Stub AWS SQS Client create_queue
O método *create_queue* da classe *Aws::SQS::Clien*t, é reponsável por criar a fila. Este método aceita vários argumentos, porém vou me ater à criação padrão.
Lembrando que validações de caracteres no nome da fila, tamanho do nome, entre outros, não são validados pelo SDK e sim pelo servidor SQS, logo não conseguiremos testar estes tipos de validações.
  describe "When called create_queue" do
    it "Should error if queue_name is invalid" do
      expect { @client_aws_sqs.create_queue({queue_name: nil}) }.to raise_error(ArgumentError)
    end

    it "Should success" do
      @client_aws_sqs.stub_responses(:create_queue, queue_url: queue_url)
      response = @client_aws_sqs.create_queue({queue_name: queue_name})
      expect ( response.successful? ).should be_truthy
      expect ( response.queue_url ).should eq(queue_url)
    end
  end
No primeiro teste a gente garante que se for passado um valor nulo, um erro é retornado.
No segundo teste, a gente cria um stub para o *Aws SQS Client create_queue*, o qual retornará *queue_url* com o valor da nossa variável de instância, *queue_url*. Após a gente “cria” a fila e verifica se tudo o correu bem. E para finalizar, a gente confere se o valor de *queue_url* confere com o esperado.