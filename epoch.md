  * what is it?
    * an interval of training of a LLM. Ex: After 20 epochs, training is done.
    * One epoch means that each [[sample]] in the training dataset has had an opportunity to update the internal model parameters. 
    * The number of epochs is a hyperparameter that defines the number times that the learning algorithm will work through the entire training dataset.
  * questions
    * does changing the total training epoch change the size of the resulting model?
      * GPT4:
        * Changing the total number of training epochs does not change the size of the resulting model in terms of its storage size or the number of parameters. The size of a machine learning model, particularly a neural network like GPT-4, is determined by the architecture of the model - specifically, the number of layers and the number of neurons (or units) in each layer.
        * Here’s what happens with different training epochs:
          * Fewer Epochs: Training for fewer epochs means the model has less exposure to the training data. This can lead to underfitting, where the model may not learn the patterns in the data effectively.
          * More Epochs: Training for more epochs allows the model more time to learn and adapt to the training data. However, too many epochs can lead to overfitting, where the model starts to learn noise and patterns specific to the training data that do not generalize well to new data.
        * In summary, the number of training epochs affects the model's performance and its ability to generalize to new data, but not the physical size or the number of parameters of the model.
  * related
    * [[sample]]
    * [[batch size]]