
`.`
`├── agent`
`│   ├── node`
`│   │   ├── awnser.py`
`│   │   ├── thought.py`
`│   │   └── tool.py`
`│   ├── router`
`│   │   └── pos_thought.py`
`│   ├── tools`
`│   │   └── retrieve.py`
`│   ├── Dockerfile`
`│   ├── gold_data_retriever.py`
`│   ├── graph.py`
`│   ├── llama_config.py`
`│   ├── requirements.txt`
`│   ├── serve.py`
`│   └── state.py`
`├── airflow`
`│   ├── config`
`│   │   └── simple_auth_passwords.json`
`│   ├── dags`
`│   │   ├── audios`
`│   │   │   └── bronze_to_silver.py`
`│   │   ├── chunks`
`│   │   │   ├── bronze_to_silver.py`
`│   │   │   └── silver_to_gold.py`
`│   │   ├── rag`
`│   │   │   └── rag.py`
`│   │   ├── recovery`
`│   │   │   └── emb_recovery.py`
`│   │   ├── transcriptions`
`│   │   │   ├── bronze_to_silver.py`
`│   │   │   ├── refined_transcription_to_markdown.py`
`│   │   │   └── silver_to_gold.py`
`│   │   ├── videos`
`│   │   │   ├── bronze_to_silver.py`
`│   │   │   └── silver_to_gold.py`
`│   │   ├── knowledge_ingestion_pipeline.py`
`│   │   └── knowledge_ingestion_pipeline_lite.py`
`│   ├── feature_repo`
`│   │   ├── data`
`│   │   │   ├── chunks_history.parquet`
`│   │   │   ├── online.db`
`│   │   │   └── registry.db`
`│   │   ├── __init__.py`
`│   │   ├── chunk.py`
`│   │   ├── feature_store.yaml`
`│   │   └── init_feast.py`
`│   ├── src`
`│   │   ├── db`
`│   │   │   ├── dao`
`│   │   │   │   ├── milvus`
`│   │   │   │   │   └── main_dao.py`
`│   │   │   │   ├── postgres`
`│   │   │   │   │   ├── __init__.py`
`│   │   │   │   │   ├── audio_metadata_silver_dao.py`
`│   │   │   │   │   ├── chunk_dao.py`
`│   │   │   │   │   ├── historical_emb_dao.py`
`│   │   │   │   │   ├── transcription_dao.py`
`│   │   │   │   │   ├── video_metadata_bronze_dao.py`
`│   │   │   │   │   └── video_metadata_silver_dao.py`
`│   │   │   │   └── __init__.py`
`│   │   │   ├── models`
`│   │   │   │   ├── postgres`
`│   │   │   │   │   ├── __init__.py`
`│   │   │   │   │   ├── audio_metadata_silver.py`
`│   │   │   │   │   ├── chat_message.py`
`│   │   │   │   │   ├── chat_session.py`
`│   │   │   │   │   ├── chunks.py`
`│   │   │   │   │   ├── historical_emb.py`
`│   │   │   │   │   ├── transcription.py`
`│   │   │   │   │   ├── video_metadata_bronze.py`
`│   │   │   │   │   └── video_metadata_silver.py`
`│   │   │   │   └── __init__.py`
`│   │   │   ├── __init__.py`
`│   │   │   ├── base.py`
`│   │   │   ├── milvus.py`
`│   │   │   └── postgres.py`
`│   │   ├── tasks`
`│   │   │   ├── audio_tasks`
`│   │   │   │   ├── extract_metadata.py`
`│   │   │   │   ├── transcribe.py`
`│   │   │   │   └── treat_audio.py`
`│   │   │   ├── chunk_tasks`
`│   │   │   │   ├── bronze_to_silver`
`│   │   │   │   │   └── translate.py`
`│   │   │   │   └── silver_to_gold`
`│   │   │   │       ├── migrate_data.py`
`│   │   │   │       └── migrate_data_lite.py`
`│   │   │   ├── transcription_tasks`
`│   │   │   │   ├── extract_metadata.py`
`│   │   │   │   ├── markdown_chunking.py`
`│   │   │   │   ├── plain_text_chunking.py`
`│   │   │   │   ├── refine_transcription.py`
`│   │   │   │   └── refined_transcription_to_markdown.py`
`│   │   │   ├── versioning_tasks`
`│   │   │   │   ├── commit.py`
`│   │   │   │   └── migrate_to_minio.py`
`│   │   │   └── video_tasks`
`│   │   │       ├── bronze_to_silver`
`│   │   │       │   ├── extract_audio.py`
`│   │   │       │   ├── extract_metadata.py`
`│   │   │       │   ├── generate_thumbnail.py`
`│   │   │       │   └── process_video.py`
`│   │   │       └── raw_to_bronze`
`│   │   │           ├── extract_metadata.py`
`│   │   │           └── raw_to_bronze.py`
`│   │   ├── utils`
`│   │   │   ├── chunk_features.py`
`│   │   │   ├── chunk_features_llm.py`
`│   │   │   ├── clean_data.py`
`│   │   │   ├── clean_logs.py`
`│   │   │   ├── clean_versioning.py`
`│   │   │   ├── clean_volumes.py`
`│   │   │   ├── mixins.py`
`│   │   │   └── time_utils.py`
`│   │   ├── __init__.py`
`│   │   └── config.py`
`│   └── backup_knowledge_ingestion_pipeline.py`
`├── chatbot`
`│   ├── assets`
`│   │   └── bot_atlantico.png`
`│   ├── services`
`│   │   ├── db.py`
`│   │   └── rag_service.py`
`│   ├── Dockerfile`
`│   ├── app.py`
`│   └── requirements.txt`
`├── knowledge_manager`
`│   ├── assets`
`│   │   └── logo.webp`
`│   ├── services`
`│   │   └── video_service.py`
`│   ├── Dockerfile`
`│   ├── app.py`
`│   └── requirements.txt`
`├── samples`
`│   └── videos.zip`
`├── test`
`│   ├── embeddings`
`│   │   └── embedding.json`
`│   └── transcriptions`
`│       └── transcript.txt`
`├── utils`
`│   ├── llm`
`│   │   ├── prompts`
`│   │   │   ├── system`
`│   │   │   │   ├── agent_decision.txt`
`│   │   │   │   ├── agent_system.txt`
`│   │   │   │   ├── chunk_features.txt`
`│   │   │   │   ├── generate_answer.txt`
`│   │   │   │   ├── refine_transcription.txt`
`│   │   │   │   └── refined_transcription_to_markdown.txt`
`│   │   │   └── user`
`│   │   │       ├── chunk_features.txt`
`│   │   │       ├── generate_answer.txt`
`│   │   │       ├── refine_transcription.txt`
`│   │   │       └── refined_transcription_to_markdown.txt`
`│   │   ├── client.py`
`│   │   ├── constants.py`
`│   │   └── llm_config.yaml`
`│   └── milvus`
`│       └── milvus_reader.py`
`├── Dockerfile`
`├── README.md`
`├── architecture.svg`
`├── chatbot_inovacao.code-workspace`
`├── db-init.Dockerfile`
`├── docker-compose.yaml`
`├── init-db.sql`
`├── pipeline_timing.py`
`├── requirements.txt`
`├── reset_and_restart.py`
`├── test.py`
`└── test_alia_thinking_mode.ipynb`