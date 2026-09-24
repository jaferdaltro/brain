
# 📘 ChatBot Inovação
Assistente Virtual Institucional, desenvolvido pela Plataforma de IA do Time de P&D (Pesquisa e Desenvolvimento).
Um chatbot inteligente para otimizar o acesso e a consulta a dados corporativos internos.
STATUS: Em Construção
## 🚀 Índice
- [Sobre o Projeto](#sobre-o-projeto)
- [Arquitetura](#arquitetura)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Funcionalidades](#funcionalidades)
- [Pré-requisitos](#pré-requisitos)
- [Instalação](#instalacao)
- [Como Executar](#como-executar)
- [Testes](#testes)
- [Estrutura de Pastas](#estrutura-de-pastas)
- [Pipeline de Execução das DAGs](#pipeline-de-execução-das-dags)
- [Roadmap](#roadmap)
- [Dívidas Técnicas (TODO)](#dívidas-técnicas-todo)
---
## Sobre o Projeto
O objetivo deste projeto é desenvolver um Assistente Virtual (ChatBot) inteligente focado em otimizar a gestão e a recuperação de informações no Instituto Atlântico.
A solução processará o repositório de dados institucionais multimodais e multimídia da empresa, tornando esse vasto volume de conhecimento imediatamente consultável.
Este sistema permitirá que os colaboradores realizem pesquisas institucionais relevantes com alta precisão e facilidade, garantindo o acesso rápido e eficiente à informação corporativa essencial.
---
## Arquitetura
Descreva brevemente ou inclua um diagrama.
```
📦 chatbot_inovacao
 ┣ 📂 airflow
   ┣ 📂 feature_repo
 ┣ 📂 test
 ┣ Dockerfile
 ┣ db-init.Dockerfile
 ┣ docker-compose.yaml
 ┣ init-db.sql
 ┣ test.py
 ┣ requirements.txt
 ┗ README.md
```
---
## Tecnologias Utilizadas
Liste as principais tecnologias:
- Python
- Docker
- PostgreSQL
- Milvus
- Feast
- DVC
- Minio
---
## Funcionalidades
[x] Trasformação dos Dados utilizando Arquitetura Medalhão para vídeos  
[x] Gerenciamento do Dados com Feast   
[x] Recuperação do dados com RAG   
[x] Recovery dos dados de embedding 
---
## Pré-requisitos
Exemplos:
- Docker e Docker Compose
- Python 3.9+
- Ambiente Linux
---
## Instalação
```bash
git clone https://usuario@bitbucket.org/institutoatlantico/chatbot_inovacao.git
cd projeto
```
---
## Como Executar
### Pré-requisitos
1. Inicie o **Docker Desktop** antes de executar qualquer comando
2. Certifique-se de que o arquivo `.env` existe na raiz do projeto com as variáveis necessárias (use o `.env.example` como referência)
### Usando Docker:
```bash
docker compose up --build
```
Para atualização de mudanças nos containers:
```docker compose up -d```
---
## Testes
É necessário ter vídeos de exemplo dentro de src/data/raw
### Airflow
http://localhost:8080/auth/login?next=http://localhost:8080/
Username: airflow  
Password: airflow
### pgAdmin
http://localhost:8081/login  
Username: admin@admin.com  
Password: admin  
1. Clique com botão direito em **Servers** → **Register** → **Server**
2. Aba **General** → Name: `postgres`
3. Aba **Connection**:
   - Host: `postgres`
   - Port: `5432`
   - Database: `media_pipeline`
   - Username: `user`
   - Password: `password`
4. Clique **Save**
### Milvus
http://localhost:8000/#/connect  
Milvus Address: milvus:19530
### Knowledge Manager (Upload de Vídeos)
http://localhost:8501  
Interface para upload e gerenciamento dos vídeos da base de conhecimento.
### Chatbot (Assistente Virtual)
http://localhost:8502  
Interface de chat para consultar a base de conhecimento via RAG.
---
## Estrutura de Pastas
```md
airflow/
  dags/
    audios/
    chunks/
    transcriptions/
    videos/
  logs/
  plugins/
  src/
    data/
    db/
    tasks/
    utils/
  feature_repo/
    data/
test/
  audios_raw/
  embeddings/
  transcriptions/
  videos_raw/
```
---
## Pipeline de Execução das DAGs
O pipeline segue a arquitetura medalhão (Raw → Bronze → Silver → Gold). Execute as DAGs na ordem abaixo pelo Airflow.
> **Execução:** você pode rodar cada DAG individualmente na ordem listada, ou acionar a `0_knowledge_ingestion_pipeline` para executar todas em sequência automaticamente.
### Fluxo Principal
1. **`1_video_raw_to_bronze`**
   - Extrai metadados e copia os vídeos para a camada bronze
   - Alimenta: **PostgreSQL** (`video_bronze_metadata`)
2. **`2_video_bronze_to_silver`**
   - Gera thumbnail, otimiza o vídeo e extrai o áudio
   - Alimenta: **PostgreSQL** (`video_silver_metadata`)
3. **`3_audio_bronze_to_silver`**
   - Trata o áudio e gera a transcrição
   - Alimenta: **PostgreSQL** (`audio_silver_metadata`, `transcriptions`)
4. **`4_transcription_bronze_to_silver`**
   - Processa o texto da transcrição e gera os chunks
   - Alimenta: **PostgreSQL** (`chunks`)
5. **`5_chunks_bronze_to_silver`**
   - Traduz os chunks gerados
   - Alimenta: **PostgreSQL** (`chunks` — atualiza as traduções)
6. **`6_chunks_silver_to_gold`**
   - Gera embeddings, migra para o banco vetorial e versiona os dados
   - Alimenta:
     - **Milvus** — embeddings e payload dos chunks
     - **PostgreSQL** (`data_historical`) — histórico de versões dos embeddings
     - **MinIO** — snapshot das tabelas e arquivos de mídia
     - **DVC** — versionamento do estado do MinIO
### DAGs sob demanda
- **`rag_taskflow_pipeline`** — acionar para queries ao chatbot após o pipeline principal ter populado o Milvus
  - Usa: **Milvus** (leitura)
  - Para fazer uma pergunta:
    1. Acesse o Airflow em `http://localhost:8080`
    2. Encontre a DAG **`rag_taskflow_pipeline`**
    3. Clique em **Trigger DAG** → **Trigger DAG w/ config**
    4. Passe a pergunta no JSON de configuração:
       ```json
       {"question": "Sobre o que é o vídeo?"}
       ```
    5. Clique em **Trigger** e acompanhe o log da task `generate_answer` para ver a resposta
- **`disaster_recovery_emb_pipeline`** — restaura o estado do Milvus a um ponto no tempo
  - Usa: **PostgreSQL** `data_historical` (leitura) + **Milvus** (escrita)
---
## Roadmap
[x] Criar Pipeline que chame o Feast para RAG   
[x] Configurar Milvus para chamadas RAG + integração com Minio   
[x] Criar disparo de atualização de dados para Recovery  
[ ] Adição de Ingestão de documentos  
[ ] Criação de Interface
---
## Dívidas Técnicas (TODO)
### Versionamento de dados ponta a ponta
- [ ] Implementar ID único por documento/vídeo que persista desde a camada Raw até o Milvus, permitindo rastrear todas as versões do mesmo dado pelo mesmo identificador
- [ ] Garantir que cada etapa da pipeline (raw → bronze → silver → gold) registre a versão do dado no PostgreSQL com referência ao `original_id`, criando um histórico completo de transformações
### Ingestão de documentos
- [ ] Criar pipeline paralela para ingestão de documentos (PDF, DOCX, TXT) seguindo a mesma arquitetura medalhão (raw → bronze → silver → gold)
- [ ] Permitir ingestão direta via banco de dados: receber um registro já existente no PostgreSQL (por `id`) e injetá-lo diretamente a partir da camada silver, sem precisar reprocessar desde o raw
- [ ] Definir schema comum de chunks para que vídeos e documentos gerem chunks com o mesmo contrato de dados, garantindo compatibilidade com o Milvus e o RAG