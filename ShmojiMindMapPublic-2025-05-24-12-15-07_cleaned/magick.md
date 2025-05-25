  * tracking stuff related to Magick
    * tracking thoughts while learning
      * [[2023-11-04]]
        * novel thing: their AIDE. Nodebased editor for creating ai agents
        * novel thing: using node-based editor you can easily create text embeddings from any input (such as people sending your bot messages in your discord)
        * novel thing: can easily create input on a node in AIDE and then in TextTemplate node you can use that input in a static string like a variable
        * i think i wanna try creating a discord bot for shmoji universe with this
    * tracking my judgements of where they are so far
      * [[2023-11-04]]


  * what is it?
    * no-code or low-code builder for creating ai agents
  * features
    * you can create agents
      * you can create agents with no-code (limited) or with code
    * you can remix any public agent and make it your own
      * i dont completely get how this works tho - gotta try it
  * aide (node-based editor)
    * types of nodes
      * Request node
        * allows you to send HTTP requests and query API endpoints (same thing)
      * TypeChat
        * im not totally sure, but i think you can give this node text as input and a schema defined by typescript (so just a type), then it uses ai to convert what's in the input text into the defined schema.
      * TextTemplate node
        * you can use the input(s) on the node in a static string as a variable. So dynamic template
        * could be wrong, but seems like this node may query LLM???
  * public agents
    * promptimus created by Rob Lennon
      * what it does: you prompt it to do some task. It then gives you back a better prompt for what you want to do. it looks into DB of previous prompts to analyze what you're trying to do based on priors
        * step 1: promptimus analyzes your prompt to tag it with goals and anything else
        * step 2: goes into DB and pulls 3 closest prompts to what you wanna do and generates a multi-shot prompt
        * at same time as above, it analyzes to figure out persona of expert who would be best at what you wanna do. It generates system directive to place in and further enhance prompt
        * last step: runs prompt through GPT4 and Claude2 to test your new megaprompt
      * me: it literally returns a prompt.
      * QUESTION: where do i send the prompt to get answer after promptimus generates the prompt?
      * me: seems it does chain-of-thought prompting for you by altering your prompt
  * costs of Magick
    * not sure yet, but ideas:
      * theyre thinking of taking percent of what your agent makes
      * theyre thinking of making so users of agents pay you to use your agents