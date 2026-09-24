Aqui está um resumo do artigo "A Resilient RAGOps Architecture for Chatbots over Multimodal Knowledge Bases":

## Problema
Chatbots baseados em RAG (Retrieval-Augmented Generation) dependem de pipelines operacionais complexos para construir e manter bases de conhecimento a partir de artefatos multimodais (vídeos, áudio, documentos). O desafio abordado é a falta de mecanismos que preservem a integridade semântica da base vetorial e permitam sua recuperação após falhas, sem precisar reprocessar tudo do zero.

## Proposta
Os autores apresentam uma **arquitetura RAGOps resiliente**, organizada em 4 camadas:

1. **Data Processing** — transforma artefatos brutos (vídeo/áudio/documento) em chunks e embeddings, passando por ingestão, extração de metadados, pré-processamento e extração de conteúdo.
2. **Persistence** — armazena artefatos, metadados, registros de proveniência e embeddings, usando PostgreSQL (proveniência), MinIO (object store) e Milvus (vector store).
3. **Resilience** — coordena a recuperação seletiva de embeddings afetados via rollback, usando versionamento (Feast para Point-in-Time Recovery) sem reprocessar todo o pipeline.
4. **Chatbot** — realiza busca semântica, constrói o contexto e gera respostas via LLM (Ollama + Llama 3).

A implementação usa Apache Airflow para orquestração, Whisper para transcrição de áudio, tradução automática e o modelo all-MiniLM-L6-v2 para embeddings.

## Avaliação
Foi feita com 5 vídeos e 15 pares de perguntas/respostas geradas via Gemini, comparando respostas com métricas de PLN (ROUGE, BLEU, METEOR, BERTScore) em dois protocolos:
- **Qualidade de resposta**: usando a base "estável" (íntegra).
- **Resiliência**: comparando estados estável → contaminado (degradação simulada) → recuperado (após rollback).

## Resultados principais
- Na base estável, o BERTScore médio foi ~0,786, indicando boa similaridade semântica.
- Após contaminação, o BERTScore caiu para ~0,7445 (queda de ~5,27%).
- Após o rollback, o BERTScore subiu para ~0,7945, praticamente recuperando o nível da base estável (exceto no vídeo V3, que teve recuperação parcial).

## Conclusão
Os resultados indicam que a arquitetura proposta consegue construir bases de conhecimento multimodais eficazes e recuperar a qualidade das respostas após degradação, sem necessidade de reprocessamento completo — contribuindo para práticas mais robustas de RAGOps. Trabalhos futuros incluem testar outros tipos de falhas e detecção automática de degradação.