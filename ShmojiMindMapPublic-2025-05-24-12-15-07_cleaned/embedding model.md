  * what is it?
    * ME: it helps to vectorize and create embeddings from any data
  * questions
    * what is diff in embedding model and LLM?
      * GPT
        * Purpose: Embedding models are used to represent words or text as numerical vectors, capturing semantic relationships. Language models focus on generating coherent and contextually relevant text based on a given input.
        * Output: Embedding models produce fixed-size vectors representing words or phrases. Language models generate sequences of text.
        * Use Cases: Embedding models are often used as feature representations for downstream tasks. Language models excel at generating human-like text and are used for text generation tasks.
        * Training Approach: Embedding models are trained to predict word co-occurrences or other linguistic features. Language models are trained to predict the next word or sequence of words in a given context.
        * Examples: Word2Vec, GloVe are examples of embedding models. GPT-3 is an example of a language model.
        * In some cases, the two concepts can intersect. Language models can learn contextual embeddings as part of their training process. For instance, GPT-3 embeddings can be used for downstream tasks, blurring the distinction between the two to some extent.
  * related
    * [[embeddings]]
