
Arquitetura Medalhão
Feature Store
Disaster Recovery
RAG


### Arquitetura Medalhão

padrão de design de dados para organizar logicamente os dados

![[Pasted image 20260811152840.png]]

### Feature Store

#### O que é uma feature? 
é o dado utilizado como um sinal de entrada para um modelo.

#### Uma feature store 
é uma interface entre modelos e dados, onde:
- Rodam pipelines que tranformam,, daods brutos em features
- Armazenam e gerenciam a feature em si e sevem os dados das features de forma consistente, para propósitos de treino e inferência de modelos.

![[Pasted image 20260811153314.png]]

### RAG

Retrieval-Augmented Generation - Geração Aumentada por Recuperação 
é uma técnica que permite que modelos de IA Gererativas consultem fontes externas de informação antes de gerar uma resposta.

![[Pasted image 20260811154129.png]]


### Tools


| DVC            | Sistema de controle de versão para dados e modelos de machine learning, funcionando como um "Git" para arquivos grandes                             |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Minio          | É um servidor de armazenamento de objetos de alta performance, compatível com a API do Amazon S3.                                                   |
| Docker         | Ferramenta de empacotamento de aplicações e suas dependências em containers isolados para garantir que rodem da mesma forma em qualquer computador. |
| Apache Airflow | Plataforma de orquestração usada para programar, monitorar e gerenciar fluxos de trabalho (pipelines) de dados complexos através de código.         |
| Ollama         | Ferramenta que permite rodar modelos de linguagem grandes (LLMs), como Llama e Mistral, localmente.                                                 |
| LangChain      | Framework de desenvolvimento projetado para facilitar a criação de aplicações que conectam LLMs a outras fontes de dados e ferramentas.             |
| PostgreSQL     | É um banco de dados relacional de código aberto extremamente robusto, focado em integridade de dados e extensibilidade.                             |
| Milvus         | É um banco de dados vetorial focado em busca de similaridade para alimentar aplicações de IA e machine learning em larga escala                     |
| FEAST          | É uma ferramenta de aplicação de Feature Store que centraliza, armazena e serve características (features) para modelos com alta peformance.        |


### DAG's
Airflow

Um DAG(Grafo Acíclico Dirigido) é um modelo que encapsula tudo o que é necessário para executar um fluxo de trabalho.


### Arquitetura dos Dados - VIDEO

![[Pasted image 20260811155223.png]]

![[Pasted image 20260811155329.png]]