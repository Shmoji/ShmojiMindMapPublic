  * how to know what method to use to create an LLM?
    * 1: KNOWLEDGE BASE EMBEDDING / [[Retrieval-Augmented Generation RAG]]: if you want LLM to give very specific answers based on your data you have: use knowledge base embeddings with some base model ^UafYFUv_e
      * prompt goes to some knowledge base first, THEN goes to base LLM
      * SPECIFICALLY: prompt gets turned into vectors, does similarity search on vector DB, get results from that. Then, (prompt template, user input, and similarity search results) go into LLM as vectors and BOOM
      * I have example of this locally in LangChainProjects/retrieval-augment-tut1 (although this is for small amount of data - need to use text splitting or something like that for large data)
    * 2: FINE-TUNING: if you want not as specific, but maybe more creative: use finetuning of some other big model. More likely to not give accurate answer
  * how to take your data and turn it into LLM? (different from using your data as KNOWLEDGE BASE EMBEDDING since it is never trained on for that)
    * g
  * how to take your data and use as LLM without training?
    * tells how here: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/how tos for creating LLMs or AI#^UafYFUv_e|1: KNOWLEDGE BASE EMBEDDING / Retrieval-Augmented Generation RAG: if you want LLM to give very specific answers based on your data you have: use knowledge base embeddings with some base model ^UafYFUv_e]]
