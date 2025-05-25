  * what is it?
    * me: AGENCY optimizing, local first - apps, data, errthing
    * framework for building p2p apps
    * there's no servers and no blockchain...this confuses me
    * each app enjoys its own isolated network built by all people that use it without maintenance effort on their part
    * ontology of holochain
      * AGENCY (you or software that runs on your behalf)
        * for every app you use the holochain runtime hosts a piece of code on your machine called the app's DNA
  * noteworthy stuff
    * bad stuff
      * holochain doesnt work on mobile devices yet
  * tech, features
    * apps
      * one [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/holochain#^pycnzzFmL|journal]] for each app
    * journal ^pycnzzFmL
      * journal data cannot be modified - it's an event log
      * if peer sees you tamper with journal, they report it
    * DNA
      * backend of your app.
      * run in webassembly sandbox - so need to write in language that compiles to WASM (there is SDK for Rust)
      * can write frontend in any framework or language, but remember it runs on user's devices - it talks to their locally running holochain runtime using RPC calls over websocket