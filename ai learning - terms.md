  * different types of learning for models
    * incremental learning
      * As prompts come in from user, they are learned by the model instantly and can be used for even more good responses
    * transfer learning
      * a model developed for a task is REUSED as that STARTING point for a model on a 2nd task.
    * Continual (or lifelong) learning
      * how to write code to do this
        * It seems best bet is to start learning fine-tuning using open ai api 
      * Combination of incremental and transfer learning
      * Examples
        * I think Quizlet may be releasing this with their new Q-chat
  * different types of learning for PEOPLE
    * Socratic method
      * In the Socratic method, a teacher or facilitator poses a series of questions to a student or group of students. These questions are designed to challenge assumptions, encourage critical thinking, and explore the underlying principles and concepts of a topic. The teacher does not provide answers or information DIRECTLY, but instead guides the student through a process of discovery and inquiry.
  * LLMs
    * different architectures
      * [[transformer LLM architecture]]
    * training LLMs (including fine-tuning)
      * conventions for training LLMs
        * The conventional paradigm is large-scale pretraining on generic web-scale data, followed by fine-tuning to downstream tasks. Fine-tuning these pretrained LLMs on downstream datasets results in huge performance gains when compared to using the pretrained LLMs out-of-the-box (zero-shot inference, for example).
          * questions
            * what are downstream tasks? and why does fine-tuning pretrained LLMs on them result in huge performance gains?
              * my answer
                * Downstream task is a SPECIFIC task. Different from larger tasks as explained in GPT answer. Get gains bc you dont have to do all that training yourself of base model - you be fine-tuning.
              * GPT answer
                * In the context of natural language processing (NLP), "downstream tasks" refer to specific NLP tasks that are built on top of more general language modeling tasks, such as text classification, machine translation, or named entity recognition. Downstream tasks often require specialized architectures and training procedures that are tailored to the specific task at hand.
                * Fine-tuning pretrained large language models (LLMs) on downstream datasets refers to the process of taking a pre-trained LLM, such as BERT or GPT-2, and adapting it to a specific downstream task by training it on a smaller dataset that is specific to that task. Fine-tuning the pretrained LLMs in this way results in huge performance gains because the models have already learned a lot about language and can leverage this knowledge to adapt to the specific task. This is more efficient than training the models from scratch, as it saves a lot of time and computational resources.
            * what is zero-shot inference? what is inference in this context?
              * my answer: no twaining on specific task, but model can perform the task successfully still. GPT gave good answer for what inference is in last sentence.
              * GPT answer:
                * Zero-shot inference refers to the ability of a model to perform a task for which it has not been explicitly trained. In other words, the model can "infer" the correct answer without being provided with any labeled examples of that particular task during training. This is made possible by the fact that the model has learned generalizable features of language during pretraining. For example, a language model that has been pre-trained on a large corpus of text can be used for text classification tasks, even if it has not been explicitly trained on that particular task. Zero-shot inference is a powerful technique for NLP tasks, as it allows models to generalize across tasks and domains. Inference in this context refers to the process of using a trained model to make predictions on new, unseen data.
            * what is difference in inference and intuition?
              * my answer:
                * inference = conscious process of drawing conclusions/judgements based on evidence or reasoning.
                * intuition = automatic, subconscious process that is often used to make quick judgments or decisions based on past experiences and emotions.. Knowing something without explicit reasoning or conscious thought
              * GPT answer:
                * Inference and intuition are related but distinct concepts in human cognition.
                * Inference refers to the process of drawing conclusions or making judgments based on evidence or reasoning. It involves using logic and available information to reach a logical conclusion or prediction. Inference is a conscious, deliberate process that relies on explicit rules and principles.
                * Intuition, on the other hand, refers to the ability to understand or know something without explicit reasoning or conscious thought. It is often described as a "gut feeling" or a sense of knowing that is not based on conscious analysis. Intuition is a subconscious process that often relies on past experiences or emotions rather than explicit rules or logic.
                * While both inference and intuition are important aspects of human cognition, they operate in different ways and serve different functions. Inference is a deliberate, conscious process that is used to draw logical conclusions, while intuition is a more automatic, subconscious process that is often used to make quick judgments or decisions based on past experiences and emotions.
            * what is difference in inference and general thinking?
              * my answer: inference is just type of thinking. Read GPT to understand how broad thinking is. It incorporates the FX of sensing, which previously i didnt really consider thinking (or even unconscious thinking)
              * gpt answer:
                * Thinking is a broad term that refers to the mental processes involved in acquiring, processing, and using information. It encompasses a wide range of cognitive activities, including perception, attention, memory, reasoning, problem-solving, and decision-making.
                * Inference, on the other hand, is a specific type of thinking that involves drawing conclusions or making predictions based on evidence or reasoning. It is a conscious, deliberate process that relies on explicit rules and principles.
                * So while inference is a type of thinking, not all thinking involves inference. For example, perception involves processing sensory information to form a mental representation of the world, but it does not necessarily involve drawing conclusions or making predictions based on evidence or reasoning.
                * Inference is often used in reasoning and problem-solving tasks, where it is necessary to draw conclusions based on available evidence or data. However, other types of thinking, such as creativity or imagination, may not necessarily rely on inference.
      * issues that arise when fine-tuning
        * Hardware processing issues and storage issues: As models get larger and larger, full fine-tuning becomes infeasible to train on consumer hardware. In addition, storing and deploying fine-tuned models independently for each downstream task becomes very expensive, because fine-tuned models are the same size as the original pretrained model.
          * Solutions:
            * Parameter-Efficient Fine-tuning (PEFT) approaches are meant to address both problems! (i think Adapter tuning is same thing as PEFT basically)
              * what this unlocks
                * Can tune large LLMs literally in Google Colab
                  * i feel like this is too good to be true. What is the catch? Is it the time it takes? Maybe Google will limit it soon due to compute costs?
              * In short, PEFT approaches enable you to get performance comparable to full fine-tuning while only having a small number of trainable parameters.
                * PEFT approaches only fine-tune a small number of (extra) model parameters while freezing most parameters of the pretrained LLMs, thereby greatly decreasing the computational and storage costs. This also overcomes the issues of [catastrophic forgetting](https://arxiv.org/abs/1312.6211), a behaviour observed during the full finetuning of LLMs. PEFT approaches have also shown to be better than fine-tuning in the low-data regimes and generalize better to out-of-domain scenarios. It can be applied to various modalities, e.g., [image classification](https://github.com/huggingface/peft/tree/main/examples/image_classification) and [stable diffusion dreambooth](https://github.com/huggingface/peft/tree/main/examples/lora_dreambooth).
              * It also helps in portability
                * users can tune models using PEFT methods to get tiny checkpoints worth a few MBs compared to the large checkpoints of full fine-tuning, e.g., bigscience/mt0-xxl takes up 40GB of storage and full fine-tuning will lead to 40GB checkpoints for each downstream dataset whereas using PEFT methods it would be just a few MBs for each downstream dataset all the while achieving comparable performance to full fine-tuning. The small trained weights from PEFT approaches are added on top of the pretrained LLM. So the same LLM can be used for multiple tasks by adding small weights without having to replace the entire model.
              * huggingface gave PEFT library here: https://huggingface.co/blog/peft
              * Use cases also found here: https://huggingface.co/blog/peft
    * temperature
      * low temp = convergent thinking
      * high temp = divergent thinking
      * GPT answer:
        * In the context of language models like LLMs (Large Language Models), temperature is a hyperparameter that controls the randomness of the model's output during text generation.
        * Specifically, when generating text, the LLM generates a probability distribution over the next word given the previous words in the sequence. The temperature parameter determines how "sharp" or "smooth" this probability distribution is.
        * A lower temperature (e.g., 0.1) results in a distribution that is more "peaky" and less random, which tends to produce more conservative, predictable output. On the other hand, a higher temperature (e.g., 1.0) results in a distribution that is more spread out and random, which tends to produce more creative and unpredictable output.
        * Therefore, temperature is an important parameter for controlling the balance between generating coherent text and generating more diverse and creative text.
    * questions
      * how does LLM INFERENCE work step by step from high level?
        * NOTE: gonna use example of using nano-gpt to sort sequence of 6 letters alphabetically
        * you have input of letters. Each letter is token. Each token has a token index
        * each number in list of tokenIndexes gets turned into 48 element vector (a size just chosen for this model). This is called an embedding
          * is the entire thing an embedding or just one single 48 element vector?? A: entire thing
        * embedding is then passed through the model, going through a series of layers, called TRANSFORMERS, before reaching the bottom
        * So what's the output? A prediction of the next token in the sequence.
  * fine-tuning
    * how LLM learn without storing state about what they learned
    * Very compute heavy...which means costs money
    * Seems like this cant really totally replace need for databases
  * embeddings

    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/transformer LLM architecture#^XPPhjCCbS|what does "embedded" mean and what are embeddings?]]
    * use cases
      * embeddings allows for more efficient and effective processing of high-dimensional data by representing it in a lower-dimensional space while still preserving the important relationships between data points.
    * terms
      * high/low dimensional data
        * high-dimensional refers to data that has many dimensions or features, while low-dimensional refers to data that has fewer dimensions or features.
        * For example, in natural language processing, words can be represented as high-dimensional vectors with thousands or even millions of dimensions, where each dimension corresponds to a different feature or aspect of the word. These high-dimensional word vectors can be difficult to work with directly, and can make many natural language processing tasks computationally expensive.
        * To address this challenge, embeddings are used to represent words as lower-dimensional vectors, typically with several hundred dimensions. These embeddings are learned by training a model to predict the context in which each word appears in a large corpus of text. By learning to predict the context of each word, the model learns to represent each word in a lower-dimensional space that captures the important relationships between words.
  * AGI terms

    * Convergence hypothesis / instrumental convergence 
      * non-math definition
        * sufficiently advanced AI systems would all naturally discover similar instrumental subgoals. This can go good or bad for Humans in various ways. 
      * Anecdotes 
        * I think AGI will autoalign. The paperclip maximizer is not an AGI. I think regular AI without cognition that's designed to be disruptive or destructive is a bigger threat.
          * what's name for concept of time before instrumental sub goals are set


  * Consciousness terms 
    * Nagel's Bat Problem 
      * We can never fully capture the subjective experience of what it's like to interact with that object. You can't experience being bat and vice versa

      * i wrote tweet about why i disagree
  * ai terms
    * vocabulary
      * list of the model's different tokens that make up its vocabulary. Ex: alphabet (but could be much more or less than that depending on tokens chosen)

  * [[ai learning log]]