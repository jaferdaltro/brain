---
apple-notes-id: DD850515-503A-406B-BB2B-935D25580808
---
## #ruby 


Em Ruby e Ruby on Rails temos diversas formas de verificar valores de um objeto. São tanta as possibilidades que acabam trazendo dúvidas sobre a diferença – até a performance – de cada opção. Vamos ver algumas das mais usadas no dia a dia e a diferença entre elas.
.nil? \[Ruby\]
Verifica se o objeto é nil. Todos os objetos implementam este método.
nil.nil?
*#  => true*
false.nil?
*#  => false*
\[\].nil?
*#  => false*
"".nil?
*#  => false*
"   ".nil?
*#  => false*
.empty? \[Ruby\]
Pode ser usado somente em alguns tipos de objetos, como Hash, String, Array. Verifica se aquele objeto é vazio, mas nem todas as coleções implementam esse método. <a href="https://ruby-doc.org/core/Enumerable.html" rel="noopener" class="external-link" target="_blank"><u>Enumerable</u></a>, por exemplo, não possui esse método.
No Rails, ele dispara uma *query* de COUNT no banco.
nil.empty?
*#  => NoMethodError*
false.empty?
*#  => NoMethodError*
\[\].empty?
*#  => true*
\[ nil \].empty?
*#  => false*
"".empty?
*#  => true*
"   ".empty?
*#  => false*
.any? \[Ruby\]
Verifica se a coleção tem algum objeto. String não implementa esse método, classes com <a href="https://ruby-doc.org/core/Enumerable.html#method-i-any-3F" rel="noopener" class="external-link" target="_blank"><u>bloco</u></a>, sim.
Este método roda em todos os objetos da coleção, por isso é mais lento e ignora os nil/false.
Uma diferença importante dele com relação aos outros é que ele pode receber um <a href="https://ruby-doc.org/core/Enumerable.html#method-i-any-3F" rel="noopener" class="external-link" target="_blank"><u>bloco</u></a> para verificar uma condição.
No Rails, algumas vezes seu uso pode ou não influenciar na performance por disparar uma *query* de COUNT no banco. Caso haja bloco, o método busca os valores e itera sobre o resultado como se fosse um Array.
nil.any?
**#  => NoMethodError**
false.any?
**#  => NoMethodError**
\[\].any?
**#  => false**
\[ nil \].any?
**#  => false**
"".any?
**#  => NoMethodError**
"   ".any?
**#  => NoMethodError**
.blank? \[Rails\]
Esse método é provido pelo Rails e funciona para todos os tipos de objetos, então, dependendo do tipo de objeto e quantidade de dados, pode ser mais lento.
nil.blank?
**#**  => true
false.blank?
**#**  => true
\[\].blank?
**#**  => true
\[ nil \].blank?
**#**  => false
"".blank?
**#**  => true
"   ".blank?
**#**  => true
present? \[Rails\]
Exatamente o oposto do blank?. A <a href="https://github.com/rails/rails/blob/66cabeda2c46c582d19738e1318be8d59584cc5b/activesupport/lib/active_support/core_ext/object/blank.rb#L25" rel="noopener" class="external-link" target="_blank"><u>implementação</u></a> dele é:
def **present?**
  !blank?
end
Como a performance deles é similar, podemos nos preocupar como o código consegue transmitir as regras de negócio. Em alguns casos, nil? não é a melhor escolha por não descrever o que realmente a regra de negócio quer dizer. Outros métodos – como empty?, present? ou blank? – podem descrever melhor esta regra. Você encontra mais sobre isso neste <a href="https://campuscode.com.br/conteudos/blank-e-present-em-rails" rel="noopener" class="external-link" target="_blank"><u>tutorial</u></a>.