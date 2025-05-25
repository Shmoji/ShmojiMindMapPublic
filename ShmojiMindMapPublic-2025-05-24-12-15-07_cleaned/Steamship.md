  * TODO
    * [ ] how to use steamship to build model that has a base of GPT model, but slowly builds knowledge of user as they input words they know and confidence rating in each word.
  * General TODO
    * [ ] Try doing Jap idea with Steamship. If doesnt work, maybe go lower level? LangChain maybe? Open AI API?
  * Questions
    * When it allows you to persist chatbot histories, is it actually learning or is it storing a longer and longer concatenated string for the prompt?
  * What can I do with it rn?
    * You can deploy your own API for AI chatbot with memory. Important to remember it is just API that it allows you to create (but with many functionality).
  * What is it?
    * Steamship is a managed backend for hosting AI services, allowing you to turn clever prompts into instant API endpoints. It integrates with major model providers like OpenAI, Hugging Face, Co:here and more, and allows you to create scalable interfaces without actually managing the infrastructure. Steamship's LangChain wrappers add managed cloud hosting to the underlying capabilities, making it really easy to publish LangChain endpoints. Steamship has yet to release their pricing, but their introductory offer of 500 API calls and 200K characters / 40 MB of LLM usage should be sufficient for our walk-through today.
  * [[Steamship log]]