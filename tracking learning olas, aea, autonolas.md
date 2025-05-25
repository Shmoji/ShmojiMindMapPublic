  * tracking
    * [[2023-11-26]]
      * when doing quickstart https://open-aea.docs.autonolas.tech/quickstart/ after just doing aea init --remote, the fetching of public aea does not work bc many stupid issues. Basically i had to go into venv and change aea_cli_ipfs code and install several packages - but luckily the cli errors helped me do those and then it worked.
      * in beginning of the hello world, you have to install aea dependencies after fetching public aea. also all aeas need private key to run so you do 2 commands to add private key. Commands in quickstart demo.
      * quickstart gives a good step by step explanation of AEA loop at end of tut.
      * ran into this issue when doing quickstart demo:
        * Not sure if it's a Windows thing, but wanted to note that i get "The process cannot access the file because it is being used by another process." when doing the Interact with the AEA part of the Quickstart demo
        * EDIT: can just use Git Bash and then it works. But no windows terminals worked due to above error
      * when sending your first envelope/message in quickstart it says "Note, due to the dialogue reference having to be incremented, you can only send the above envelope once!" - i have no idea what this means or why it is
      * alternatively the quickstart shows how to create the aea step by step by adding each piece like the stub connection and echo skill (rather than just fetching entire aea)
      * at end of quickstart they give a unit test and notify you that there is utility classes made for fully testing your AEAs. However, the demo unit test doesnt work. Not sure why.
    * [[2023-12-02]]
      * did the HTTP echo demo. Got tripped up on "curl 0.0.0.0:5000" - just replace the 0 address with localhost
      * this was cool bc the AEA is used as an actual web server - as if i just setup a node app and API or something. The tut said this "The purpose of this demo is to show the open-aea framework can be used as a HTTP server. More concretely, an AEA with a http server connection and an appropriate skill can be used as a server."
      * at end of demo it says "If you feel confident enough, you can try modifying the agent so that it executes some additional action. If you do so, remember that you have to update the hash values in the configuration file" - what hash values and why?
        * i guess you have to edit hash value of whatever components you change? how does that work? do you change code, generate new component/hash, publish it, and then put hash in config?? like no idea tbh
    * [[2023-12-23]]
      * Trying the module 2 task of the academy today - which is the Hello World agent service
      * i am 30% sure that aea cli is used for managing aea's - duh - this is learned in beginning of academy. in module 2 of academy you learn of Agent SERVICES which use multiple aea's. They never show you that you need to learn to setup the open-autonomy cli for agent services - but you do and they dont show how to do it. it will prob move, but found out how here and in "quick start" https://docs.autonolas.network/open-autonomy/guides/set_up/
      * I am now 98% confident of the above after reading this: "
        * The [Open AEA](https://github.com/valory-xyz/open-aea) framework provides the necessary components for building single agents. [Open Autonomy](https://github.com/valory-xyz/open-autonomy) extends this framework to a service architecture, making possible to build applications as distributed systems (that is, agent services) that can be run by multiple, independent operators.
        * The internal state of an agent service is replicated across all the agents in the service through a **consensus gadget** (a sort of short-lived blockchain).
      * one of 1st questions i had was why use an Agent Service over using 1 single aea - and they have def got that question before. This is answer from their site and i documented here: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/autonolas, olas#^WQ6xosaj8|why use an Agent Service over using 1 single aea?]]
