  * TRACKING LEARNING
    * [[2023-11-05]]
      * i did this tutorial and learned how to visualize embeddings using Phoenix and find embeddings that have drifted with larger euclidian distance. These embeddings make your model worse or last accurate at predicting, so then once you find them, you can go back and label new data and finetune. I dont completely understand this, but that's what i somewhat got from it. Dont feel i really got anything super actionable from this, but kinda cool. Would be even cooler to see it done with my own data

  * what it be?
    * me: are embeddings always numbers in arrays when you open a file and look at them? Answer: yes
    * numerical representation of textual data (or any data i think)
    * list of numbers that represents data in different way
  * what they do?
    * measure relatedness of text strings (or any data i think)
    * good way to store data if it is unstructured and even tho unstructured, once it is embedding - can do all kinds of operations on data to find stuff out despite it not being manually labeled like with relation DBs
  * how TOs
    * how to generate embeddings quickly?
      * seems best way i know so far is to learn how to write quick script to do it - so that's a TODO
      * notes
        * need to use a pre-trained model to generate embeddings. I have no idea if some are better than others - i guess it depends on use-case but idk

  * questions
    * so when i have a model file, is that where the embeddings are literally stored?
      * A: YES
    * does the model file also contain weights? and what's the difference in the weights and the embeddings?
      * GPT4: Yes, the model file of a Large Language Model (LLM) like GPT-3 or GPT-4 contains both embeddings and weights, and they serve different but complementary roles in the model.
        * Role in the Model: Embeddings are specifically for representing language data in a form the model can process, while weights are used throughout the network to transform and interpret these representations.
        * Learning Process: Both embeddings and weights are learned during training, but they serve different purposes. Embeddings learn to represent words meaningfully, while weights learn to make accurate predictions or generate coherent text based on those representations.
        * Location in the Network: Embeddings are typically at the input and output layers of the model, translating words to and from the neural network's internal representation. Weights are found in every layer of the model, governing how data is processed at each stage.
    * would it be correct to say that embeddings are a more narrow type of weights?
      * YES
  * related
    * [[tokenizer]]