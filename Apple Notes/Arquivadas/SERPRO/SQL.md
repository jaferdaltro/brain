---
apple-notes-id: 05CA9D7C-84FC-414E-B211-63AA40C9527F
---
#serpro #tecnologia #db

1 Banco de dados. 
- 1.1 Arquitetura de banco de dados: relacional (PostgreSQL, Oracle, SqlServer), não relacional (orientado a documento, chave-valor, grafo, colunar, time series). 
- 1.2 Modelagem de banco de dados: físico, lógico e conceitual. 
- 1.3 Álgebra relacional, SQL/ANSI e linguagens procedurais embarcadas. 
- 1.4 Gestão de banco de dados. 
- 1.4.1 Controle de acesso, usuário, cálculo volumétrico, replicação, cluster, particionamento e esquemas. 



SELECT Unit,AVG(Price) FROM \[Products\] group by Unit having AVG(Price) > 20;

- SELECT - extracts data from a database
- UPDATE - updates data in a database
- DELETE - deletes data from a database
- INSERT INTO - inserts new data into a database
- CREATE DATABASE - creates a new database
- ALTER DATABASE - modifies a database
- CREATE TABLE - creates a new table
- ALTER TABLE - modifies a table
- DROP TABLE - deletes a table
- CREATE INDEX - creates an index (search key)
- DROP INDEX - deletes an index


### VIEW
Nas atualizações das views poderá haver a inserção de valores nulos caso as colunas da tabela não estejam na definição da view
Nesses casos é possível evitar esse problema com a opção WITH CHECK OPTION.

Uma view é atualizável se: 
- A PK ou outra chave candidata estiver presente na lista de atributos;
- A cláusula FROM  possui apenas uma relação;
- A cláusula SELECT possui apenas atributos da relação. Não possui expressões, agregadas ou especificação distinct;
- Os atributos não listados na view podem ser definidos como nulos( se a pessoa tiver a restrição de integridade referencial, se tentar inserir e disser que é not null, não vai acontecer);
- A consulta não possui cláusula group by ou having(existe uma série de critérios para fazer a atualização das views, lembrando que a view é uma consulta, então atualiza-se a relação que aquela view está consultando).
	
 
Não são atualizáveis: 
- Views definidas em múltiplas tabelas (joins)(quando passar o insert, o banco não saberá para onde enviar o dado, porque tem um resultado de um join, parecendo que é apenas uma relação, mas são várias relações envolvidas);
- Views com uso de funções de agregação(san, avg, max, min).


### CESPE
A diferença entre *materialized view* e *view* comum em banco de dados é o fato de que a primeira é armazenada em *cache* como uma tabela física, enquanto  a segunda existe apenas virtualmente.