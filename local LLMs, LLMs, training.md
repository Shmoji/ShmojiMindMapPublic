  * what is it?
    * just a file. ex: "large-v2.pt" is what was downloaded to my PC for the OS whisper model. But a file with a ton of functionality. But separate code is needed to make this functionality work in any context really (like your code)
      * so...is an LLM just a file?
        * GPT-3.5
          * Considering an LLM (Large Language Model) as just a file is a simplified perspective, but it's not entirely accurate. Let's break it down:
            * LLM as a File: Yes, when you download an open-source LLM, what you receive is typically a file that contains the model's parameters and weights. This file is essentially a snapshot of the trained model. So, in a technical sense, you do have a file.
            * More Than Just a File: However, the true nature of an LLM goes beyond just being a file. Here's why:
            * a. Complexity: The contents of the file represent a highly complex neural network. It comprises layers, nodes, and weights that have been trained on a vast amount of text data. This network can generate human-like text based on the input it receives.
            * b. Functionality: An LLM can perform various natural language processing tasks, such as text generation, translation, summarization, and question-answering. It can be a valuable tool for developers to build applications with natural language understanding capabilities.
            * c. Continuous Learning: Some LLMs are designed to be fine-tuned or updated with new data, making them adaptable and potentially improving their performance over time.
      * to access the functionality on this file requires separate code (in other files) (this is what whisper package is that is imported at top of your code when using whisper local model)
      * to use a local LLM file, separate code in different files is required. For example, to use the whisper LLM base.pt model, you need many other  files such as model.py. Are these other files considered the LLM too or no?
        * GPT-3.5
          * The additional files required to use a local LLM, such as model.py, are not considered the LLM itself, but they are essential components that enable you to use the LLM effectively. Let's clarify their roles:
            * LLM Model File (base.pt): This file contains the pre-trained model's parameters and weights. It's the core component of the LLM and is responsible for generating text based on input.
            * model.py and Other Support Files: These additional files typically include Python scripts, classes, and functions that provide the necessary infrastructure to load and interact with the LLM model file. They handle tasks such as model initialization, tokenization, input processing, and output generation. These files are essential for integrating the LLM into your projects.
          * In summary:
            * The LLM model file (base.pt) is the heart of the LLM, containing the knowledge and capabilities to generate text.
            * model.py and other support files are tools and code that enable you to harness the power of the LLM model. They facilitate the interaction between your code and the model, making it usable in your applications.
      * Maybe like to think of it in same way as package/api in that you interface with it and it returns a certain functionality based on what model it is.
    * a local/downloadable API that anyone can use OFFLINE. In the past if i created API it had to run on some hosted backend server. Now i can basically create API/database/functionality all in one that people can use OFFLINE if they download it. 
  * questions
    * so a pre-trained model has been trained before? that confused me bc i assumed it meant there had been no training yet
      * "pre-trained" means initial training on a generic dataset, and "trained" or "fine-tuned" means additional training for a particular task or domain.
      * obviously that confusion is stupid from the POV of someone knowledgeable - bc if there's no training at all, then there's no model. But from someone new to the space, it can be quite confusing
    * how is the execution of LLM different from a regular app that executes instruction by instruction?
      * me
        * LLM does not execute linearly instruction by instruction. Instead, there is a list of mathematical operations (not necessarily know at beginning) and all these operations happen in parallel (of course some happen after others tho).
    * do LLMs use CPUs or GPUs?
      * GPT-3.5
        * SUMMARY: So, while LLMs can run on both CPUs and GPUs, using GPUs or dedicated accelerators like TPUs is often preferred for faster inference.
        * Local LLMs can run on both CPUs and GPUs. The choice of hardware depends on the available resources and the specific implementation.
        * CPUs are capable of running LLMs, but the processing is generally slower compared to GPUs because LLMs involve a lot of matrix operations, and GPUs are highly optimized for parallel computation.
        * GPUs are well-suited for deep learning tasks like LLMs due to their parallel processing capabilities. Many LLM frameworks, like TensorFlow and PyTorch, provide GPU support for accelerated execution.
        * Additionally, there are specialized hardware accelerators like TPUs (Tensor Processing Units) that can further enhance the performance of LLMs.
    * are models always one file? how are they stored?
      * NOPE! i thought they were bc in beginning all local LLMs i used were a single .pt file. But then i used ollama to download llama3 and it has a folder called blobs with a bunch of files inside and those files combined make up the local model. Apparently .gguf files are models too?
  * options for local LLMs
    * [[open webUI]]
  * related
