  * LangChainProjects/retrieval-augment-tut1
    * shows super simple RAG example at app.py with my health data
    * shows super simple BUT super SLOW example at roam-RAG.py with roam data. Super slow because creating embeddings and vector storage every single time
    * no text splitting or chunking
    * uses OpenAI embeddings model and GPT3 LLM
    * uses FAISS for vectorDB - it's all in memory (nothing on disk)
