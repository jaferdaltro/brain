`.`
`├── airflow`
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
`│   │   │   └── silver_to_gold.py`
`│   │   └── videos`
`│   │       ├── bronze_to_silver.py`
`│   │       └── silver_to_gold.py`
`│   ├── feature_repo`
`│   │   ├── data`
`│   │   │   ├── chunks_history.parquet`
`│   │   │   ├── online.db`
`│   │   │   └── registry.db`
`│   │   ├── __init__.py`
`│   │   ├── chunk.py`
`│   │   ├── feature_store.yaml`
`│   │   └── init_feast.py`
`│   ├── logs`
`│   │   └── dag_processor`
`│   │       └── latest`
`│   └── src`
`│       ├── db`
`│       │   ├── dao`
`│       │   │   ├── milvus`
`│       │   │   │   └── main_dao.py`
`│       │   │   ├── postgres`
`│       │   │   │   ├── __init__.py`
`│       │   │   │   ├── audio_metadata_silver_dao.py`
`│       │   │   │   ├── chunk_dao.py`
`│       │   │   │   ├── historical_emb_dao.py`
`│       │   │   │   ├── transcription_dao.py`
`│       │   │   │   ├── video_metadata_bronze_dao.py`
`│       │   │   │   └── video_metadata_silver_dao.py`
`│       │   │   └── __init__.py`
`│       │   ├── models`
`│       │   │   ├── postgres`
`│       │   │   │   ├── __init__.py`
`│       │   │   │   ├── audio_metadata_silver.py`
`│       │   │   │   ├── chunks.py`
`│       │   │   │   ├── historical_emb.py`
`│       │   │   │   ├── transcription.py`
`│       │   │   │   ├── video_metadata_bronze.py`
`│       │   │   │   └── video_metadata_silver.py`
`│       │   │   └── __init__.py`
`│       │   ├── __init__.py`
`│       │   ├── base.py`
`│       │   ├── milvus.py`
`│       │   └── postgres.py`
`│       ├── tasks`
`│       │   ├── audio_tasks`
`│       │   │   ├── extract_metadata.py`
`│       │   │   ├── transcribe.py`
`│       │   │   └── treat_audio.py`
`│       │   ├── chunk_tasks`
`│       │   │   ├── bronze_to_silver`
`│       │   │   │   └── translate.py`
`│       │   │   └── silver_to_gold`
`│       │   │       └── migrate_data.py`
`│       │   ├── transcription_tasks`
`│       │   │   ├── chunking.py`
`│       │   │   ├── extract_metadata.py`
`│       │   │   └── process_text.py`
`│       │   ├── versioning_tasks`
`│       │   │   ├── commit.py`
`│       │   │   └── migrate_to_minio.py`
`│       │   └── video_tasks`
`│       │       ├── bronze_to_silver`
`│       │       │   ├── extract_audio.py`
`│       │       │   ├── extract_metadata.py`
`│       │       │   ├── generate_thumbnail.py`
`│       │       │   └── process_video.py`
`│       │       └── raw_to_bronze`
`│       │           ├── copy_files.py`
`│       │           └── extract_metadata.py`
`│       ├── utils`
`│       │   ├── chunk_features.py`
`│       │   ├── clean_data.py`
`│       │   ├── clean_logs.py`
`│       │   ├── clean_versioning.py`
`│       │   ├── clean_volumes.py`
`│       │   ├── mixins.py`
`│       │   ├── model_request.py`
`│       │   └── time_utils.py`
`│       ├── __init__.py`
`│       └── config.py`
`├── test`
`│   ├── embeddings`
`│   │   └── embedding.json`
`│   └── transcriptions`
`│       └── transcript.txt`
`├── Dockerfile`
`├── README.md`
`├── db-init.Dockerfile`
`├── docker-compose.yaml`
`├── init-db.sql`
`├── requirements.txt`
`└── test.py`