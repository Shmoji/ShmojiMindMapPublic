  * what is it?
    * a form of semantic compression
    * an alternative to teaching LLMs stuff (different from RAG, fine-tuning, etc)
    * a way to make your prompt smaller without losing much info
    * important context:
      * language models are like human brains in that they are ASSOCIATIVE. Which means you/LLM takes input of 3 words, then you/LLM point to a ton of associated info to those words. This is called a mental model.
      * LLMs have limited context window (num of token they can take as input in prompt). No way to get past this. Well in terms of mashing more text in there. There is something you can do tho:
      * The best superpower of LLMs: LATENT SPACE. 
      * https://github.com/daveshap/SparsePrimingRepresentations/tree/main
  * how it works
    * take David Shapiro's SparsePrimingRepresentations repo system message and paste into system message of OpenAI playground.
    * Send first message to LLM containing all the data you want to teach the LLM. This data will be compressed and will return a list of statements. This is the SPR.
    * Remove old system message and have it as empty. New message starting with unpack statement from David's repo pasted. Then, paste SPR and send.
    * Now you can ask questions in similar way to RAG or a model trained on that data.