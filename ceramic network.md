  * Ceramic journal
    * sometime around [[2023-10-04]]
      * ceramic network meeting to see if it works for my project
        * notes
          * did:key - no wallet needed (no teams done it yet)
          * safe-core (full account abstraction) - used to be gnosis
            * creates wallet address -> then creates DID
            * is it open source?
            * react-example repo
          * how hard to switch from mongoDB 
        * questions
          * is wallet needed to store data using composeDB? or just a DID? ^SfdQDD8Qf
            * there are 3 DID methods mainly used. DID:PKH (or something like that) requires a wallet and most people use that. DID:key does not require wallet, but no one has used it yet
            * I guess DID:key would work by creating wallet and DID when you auth with google or twitter or whatevs.
            * I think safe-core does above point
          * i want data to be owned by user, is answer to point above still same?
            * yes
          * any tools that make this easier rather than me doing all work? i saw orbis
            * not really. maybe safe-core
          * any complications with switching from centralized DB to user owned data? how hard is it?
            * Medium difficulty. You'll need user to reauth - then custom modal that tells switching data over and confirm button. Not tooooo bad. Definitely possible despite annoying
    * [[2023-10-14]]
      * i learned Ceramic and ComposeDB using this demo repo: https://github.com/ceramicstudio/ceramic-ai/tree/main

  * what is it?
    * Ceramic is a "Data Ledger"
      * Ceramic can be viewed as a "Data Ledger" middle ground between on-chain data and the off-chain universe. Given that Ceramic events are periodically rolled into a Merkle tree and the root is published to the Ethereum blockchain (thus preserving consensus on the global ordering of Ceramic transactions), Ceramic contains characteristics that prevent it from being neatly assigned to a purely off or on-chain storage layer.
  * how TOs
    * how to encrypt data on ComposeDB
      * https://blog.ceramic.network/tutorial-encrypted-data-on-composedb/?ref=the-ceramic-blog-newsletter
    * how to decide how to store data using ceramic
      * choose 1 of 4 quadrants of the [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ceramic network#^kQUdEp2gc|data control patterns in decentralized storage: Users vs. Apps: Data Creation and Ownership (4 options)]]
  * key points
    * Currently, data deletion is not supported. All ComposeDB data transactions are timestamped via Ceramic into the public Ethereum blockchain. This means that data can always be retrieved from the blockchain.
  * questions
    * if i wanted to create a discord bot that can ping an API and then the API will store data in ceramic network - do i need a ceramic node running at all times or can i just start the node when the API is pinged and stop it after execution?
      * Your Ceramic node needs to be up and running for any interactions with your applications to be anchored and for the data to be available for your application.
      * For a small application you should be able to use a free-tier of most of the cloud providers and keep it running without interruptions if the cloud services cost is the point of of concern.
    * what are different ways to store and control data in Ceramic or decentralized data storage in general?
      * data control patterns in decentralized storage: Users vs. Apps: Data Creation and Ownership (4 options) ^kQUdEp2gc
        * blog covering this: https://blog.ceramic.network/data-control-patterns-in-decentralized-storage/?ref=the-ceramic-blog-newsletter
          * covers important factors for each options, such as:
            * 1) what kind of DID is needed (affects UX and good 4 dev to know)
            * 2) where generation of data and writes of data happen (affects UX and good 4 dev to know)
            * 3) Network data sync
              * i dont completely get how this is different from "Data Availability Motives"
            * 4) Data Availability Motives - somebody gotta keep data available
            * 5) who is trusted vector? - the application? some sort of Trust model?
            * 6) an actual Ceramic example
            * 7) unique needs
        * text version of options
          * 1) Application-Generated, Application-Controlled
          * 2) Application-Generated, User-Controlled
          * 3) User-Generated, Application-Controlled
          * 4) User-Generated, User-Controlled
        * image of options (maybe delete?)
          * ![[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Attachments/imgs/app/ShmojiMindMapPublic/HGQpykPtt-.png]]


  * related
    * [[DIDs]]