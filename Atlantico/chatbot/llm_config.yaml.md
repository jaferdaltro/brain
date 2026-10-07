phoenix_evaluation:

  provider: alia

  model: gpt-oss:20b  #TODO: problema de não passagem dos parametros pelo litellm para modelo no alia (problema interno do alia)

  # provider: openai

  # model: gpt-4o-mini

  temperature: 0.0

  

refine_transcription:

  provider: alia

  # provider: openai

  model: qwen3.6:35b

  # model: gpt-5.4-nano

  temperature: 0.1

  # max_tokens: 144000

  max_tokens: 128000

  system_prompt_file: refine_transcription.txt

  user_prompt_file: refine_transcription.txt

  

refined_transcription_to_markdown:

  provider: alia

  model: qwen3.6:35b

  # provider: openai

  # model: gpt-5.4-nano

  temperature: 0.1

  # max_tokens: 144000

  max_tokens: 128000

  system_prompt_file: refined_transcription_to_markdown.txt

  user_prompt_file: refined_transcription_to_markdown.txt

  

extract_chunk_features:

  provider: alia

  model: qwen3.6:35b

  # provider: openai

  # model: gpt-5.4-nano

  temperature: 0.1

  # max_tokens: 144000

  max_tokens: 128000

  system_prompt_file: chunk_features.txt

  user_prompt_file: chunk_features.txt

  

generate_embedding:

  #provider: openai

  #model: text-embedding-3-small

  #dimensions: 384

  provider: ollama

  model: qwen3-embedding:0.6b

  dimensions: 1024

  

generate_answer:

  provider: alia

  model: qwen3.6:35b

  # provider: openai

  # model: gpt-5.4-nano

  temperature: 0.5

  # max_tokens: 144000

  max_tokens: 128000

  system_prompt_file: generate_answer.txt

  user_prompt_file: generate_answer.txt

  

agent_reasoning:

  provider: alia

  model: qwen3.6:35b

  # provider: openai

  # model: gpt-5.4-nano

  temperature: 0.0

  system_prompt_file: agent_system.txt