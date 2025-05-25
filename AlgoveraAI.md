  * Why i stopped playing with this for now
    * updating underlying LLM with user's input dynamically seems tough. Could prob do it like how i explained in there discord support channel, but not easy. Plus give it a month or so and they may support that themselves. This is what i really want: ![](https://twitter.com/Shmojii/status/1632039181735149568)
  * Algovera TODO
    * [x] Figure out if possible to update underlying LLM with user's input dynamically
      * job_uuid: '87d4af20784945e5a2af6e97659353e5', 
      * qanda_uuid: '6ef1b39adabf49b39b778346152ee69f'
  * use cases
    * what ive experienced
      * You pass any file/url/any data source in (i passed PDF of MBTI stuff) and then you can ask it questions.
    * Use Q&A on GitHub repos
    * Use Q&A on YT videos
    * Use Q&A on any data you upload (any file type i think)
    * Anecdotes
      * i asked: "Would it be possible for an app that is built to take in user data and use algovera API to continuously build a knowledge base for that user? Or is that not possible at the moment?" 
        * Jakub in discord responded: "That’s an awesome use case and one we’re definitely building towards. It’s currently possible to take an existing knowledge base to create a workflow on top of it, but knowledge base creation as a workflow itself should not be that far away."
  * Algovera journal
    * My qandas were giving poop short answers and then i used "chain_type" of "refine" and it fixed. These types explained in algovera discord thread
  * The forms the use-cases can take
    * AI assistant (for individual or for organization)
  * Resources
    * API: https://api.algovera.ai/docs
  * Other projects just like this / related projects
    * steamship.com: Maybe similar on API level?
    * LangChain
      * Algovera is built using LangChain. It is one part of tech stack.
      * LangChain is much more developer focused. Algovera is focused on making AI assistants and building AI workflows accessible for everyone, not just for developers.
      * Langchain is limited to text but Algovera will eventually be multimodal with ability to build workflows that connect text, image, web3, speech, video etc.
      * There are a lot of things that come out of the box with Algovera that you would need to set up separately when running langchain e.g credits, storage, runtime env.
    * llama index: Many of Algovera's workflows built ontop of llama index
  * What is unique about this project
    * The API and getting started seems pretty simple
    * OCEAN is involved
      * The Algovera Flow platform uses a credit system for running AI workflows. These credits cover the cost of compute and tokens from other platforms such as OpenAI, StabilityAI and Ocean Protocol. When is compute from OCEAN used? Only place i see is for Ocean Question Answering workflow. It answers questions based on OCEAN dataset.
      * You can get funded to build your AI workflow through Algovera Grants. "We're very grateful to Ocean Protocol Foundation for sponsoring Algovera Grants."
  * Terms
    * context
      * The vector database that is used in question answering.
      * For example, when you run createqanda, it uses the files you uploaded to create this vector DB that will be used for your future question answering.
    * qanda
      * This is the endpoint used to do question answering.
      * There are different means for creating the vector DB (context) (like from files, github repo, etc) - but there is only one endpoint to do the question answering.
    * workflow
      * Generic term for any actions/tasks the API do. For example, the createqanda workflow to create context using uploaded files. Or openaitxt2img workflow can be used to call Dalle 2 to generate an image.
    * Related
