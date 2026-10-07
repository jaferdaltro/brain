---
apple-notes-id: B7141443-474D-4ACE-B76D-638C41258420
---
<p style="text-align:left;margin:0">#engenharia 

</p>
- A métrica PF é uma técnica de medição do tamanho funcional de um software. 
	
- Essas funções são operações extraídas dos **requisitos funcionais** gerados a partir da visão do usuário. 
	
- A partir dessa medição, é possível **estimar o esforço** para implementação do sistema utilizando ponto de função, que é a unidade de medida desta técnica. 
	
- A métrica PF mede o que o software faz, independentemente de como ele foi construído. Assim, o processo de medição é fundamentado em uma avaliação padronizada dos requisitos lógicos do usuário. 
	



<p style="text-align:left;margin:0">## CLASSIFICAÇÃO DOS TIPOS DE FUNÇÃO

### Interação função de transição 
EE - Entrada externa
SE - Saída externa
CE - Consulta externa 

### Armazenamento função de dados
ALI - Arquivo lógico interno
AIE - Arquivo de interface externa



![[Pasted Graphic 1 1.png]]


### Tipo de Contagem
- Projeto de desenvolvimento
- Projeto de melhoria
- Aplicação
	
### Funções de Dados
- Arquivos Lógicos Internos(ALI): grupos de dados logicamente relacionados(do ponto de vista do usuário) e mantidos pela própria aplicação.
- Arquivos de Interface Externa(AIE): grupos de dados logicamente relacionados(do ponto de vista do usuário) e apenas referenciados de outras aplicações.

### Funções de Transição 
- Entradas Externas(EE): transações com o objetivo de atualizar arquivos lógicos internos ou modificar o comportamento do sistema
- Consultas Externas(CE): transações que representam simples recuperação de dados de arquivos lógicos internos e/ou arquivos de interface externa.
- Saídas Externas(SE): transações com o objetivo de apresentação de informação, porém envolvendo lógica de processamento adicional a uma consulta externa. 
	

![[Pasted Graphic 2 1.png]]



</p>