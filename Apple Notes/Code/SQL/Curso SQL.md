---
apple-notes-id: A88F2255-7950-46D7-A2BD-518D3778B7AC
---
select a.nome, c.nome, avg(n.nota) from nota n join
resposta r on n.resposta_id = r.id join 
exercicio e on r.exercicio_id = e.id 
join secao s on e.secao_id = s.id join
curso c on s.curso_id = c.id join 
aluno a on a.id = r.aluno_id group by c.nome, a.nome;

select a.nome, c.nome, n.nota from notas n join 
resposta r on n.resposta_id = r.id join 
exercicio e on r.exercicio_id = e.id join  
secao s on e.secao_id = s.id join 
curso c s.curso_id = c.id join 
aluno a e.aluno_id = a.id group by a.nome, c.nome;