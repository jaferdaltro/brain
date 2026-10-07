---
apple-notes-id: FF9C15F7-3532-4014-8046-81D2C21861D0
---
Crie uma função que irá receber uma lista ordenada de inteiros e retornará uma outra lista. 
A lista retornada deve ter apenas os valores que aparecem duas ou mais vezes dentro da lista recebida inicialmente.


Exemplo:

numbers = \[1,2,2,3,4,4,5\]
find_duplicates(numbers)
# \[2,4\]
 
 

def find_duplicates(numbers)	
	duplic = \[\]
numbers.each do |n| 
	duplic < if n.is_included?
end
duplic
end

\[regrinhas\] 

1. O código não necessariamente precisa compilar, então não se preocupe com isso;
2. Com esse teste queremos ver apenas sua lógica, não se você conhece tudo de ruby;
3. Não é para fazer em nenhum lugar além do documento do Google Docs;
4. Não é para usar VSCode, Sublime, RubyMine ou qualquer outro editor;
5. Não é para testar as coisas no irb (interactive ruby shell);
6. Não é para fazer pesquisa no Google;
7. Se quiser, após terminar o desafio e houver tempo, pode escrever testes para ele.