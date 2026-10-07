---
apple-notes-id: 364B4AED-1FCE-4932-AE52-1A4D8889F810
---
```
dias_anteriores = {
  'segunda' => 'domingo',
  'terça' => 'segunda',
  'quarta' => 'terça',
  'quinta' => 'quarta',
  'sexta' => 'quinta',
  'sábado' => 'sexta',
  'domingo' => 'sábado'
}

array = ['segunda', 'quinta', 'quarta']
resultado = array.map { |dia| dias_anteriores[dia] }

puts resultado
```



![[Pasted Graphic 3 7.png]]