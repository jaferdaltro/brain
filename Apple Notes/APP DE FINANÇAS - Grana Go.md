---
apple-notes-id: 9C069A9B-5D58-4C2B-8A6A-053B0A75A105
---
### PROMPT:
Criar um projeto usando Ruby on Rails versão 8, usando Tailwind css, Postgres, irei fazer o deploy em fly.io. O projeto consiste em criar uma aplicação de finanças pessoal, onde a pessoa possa: 

- receitas e despesas;
- acompanhar seus gastos diários em conta corrente e cartão de crédito;
- ter um dashboard para acompanhamento dos gastos diarios, mensal e anual;
- ter funcionalidade de planejamento financeiro mensal e anual;
- Criar categoria de gastos;
- Investimentos;
- Férias;
- Decimo terceiro salário;
- Freelancer;


- Organize
- Mobills [mobills.com.br](http://mobills.com.br) 
- Monelover
- Fortuno
- Wallet https://web.budgetbakers.com/dashboard 


—-


```
rails new grana_go -d postgresql -c tailwind
```

Token GitHub actions

```
FlyV1 fm2_lJPECAAAAAAAAbhqxBDK20TNLceYOAt6qpTFSxEywrVodHRwczovL2FwaS5mbHkuaW8vdjGWAJLOAAVVyR8Lk7lodHRwczovL2FwaS5mbHkuaW8vYWFhL3YxxDzUSRbmBdF1gDfPZn8MzxfByk3ul3+9imXnPhowkB0dAzdvbla6ZPlrzHJtaQTEZnjR8uKbCNIGhD6gqiXETgJ4mZEyU1i9PO0EA6GVRzw9tWNvf7jotNk1fUNpiYOA7GuT+nqOGI55HHjEwKpJvkPlH24nv0RANtY2UOXR3YNlmia65uj2i0lnCt1ndw2SlAORgc4AYg+eHwWRgqdidWlsZGVyH6J3Zx8BxCBkX1gI0IHHrUHbnkd4+65O+xbEUKMdvyR9Zwr40vLeJg==,fm2_lJPETgJ4mZEyU1i9PO0EA6GVRzw9tWNvf7jotNk1fUNpiYOA7GuT+nqOGI55HHjEwKpJvkPlH24nv0RANtY2UOXR3YNlmia65uj2i0lnCt1nd8QQG+TCipVQDclmcqr+YXDIkMO5aHR0cHM6Ly9hcGkuZmx5LmlvL2FhYS92MZgEks5nmOO1zwAAAAE+LHnDF84ABPMDCpHOAATzAwzEEJ0NHvUtSFRPVg3hKCYkqPjEIFB1jvx/XRd9RJG/Vj1s+MnXwC9ATte/1380sBPPQ3ZY
```

### Tabelas
Transaction
Category
Plan
User