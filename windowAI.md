  * when would i use this?
    * if i started using local LLMs
    * if i started using multiple LLMs and wanted all history in one place
    * if i could find frontend that doesnt look sketchy or create one myself (which they do offer templates for)
  * what is it?
    * A standard that apps can be built on top of. With this standard, you no longer need to paste your LLM keys into each app BC they're already stored in WindowAI browser extension.
    * Instead you give signature to each app allowing them to use each LLM you try to use. You're basically just allowing that app to send prompts to the LLM - my understanding is that the signature doesnt actually give the app access to your API key or any private data.
  * my questions
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/windowAI#^hlO3LMUqb|how do they store that history?]]
  * how does it REALLY work (not in IDEA way, but REAL way)
    * Window works as a browser extension and JavaScript API:
    * 1: You configure your keys and models just once
    * 2: Apps can request permission to send prompts to your chosen model via the injected "[http://window.ai](https://t.co/9DdhSIUWwp)" lib.
    * 3: You maintain visibility on what's being asked! (history)
      * how do they store that history? ^hlO3LMUqb
  * cool shiz about this idea
    * saves time of pasting LLM key into all these apps. Also, dont need to trust all those apps with LLM key anymore, just need to trust WindowAI. Which is open source yay.
    * If app does integrate this standard, then any LLM that WindowAI supports can be used with that app
    * You can even use a LLM running locally with any app that supports this standard
  * issues with idea
    * it requires people to integrate this standard into their app and most people will not if i had to guess