  * tracking thoughts
    * tracking meetings with their team
      * [[2024-06-19]]
        * met with Seref. I was trying to see if i could built the api for people on index network. Seems maybe?
        * he showed me very small amount of code that can read indexes, listen to source list of DIDs, and write indexes. He seemed to think i could use that. It was the index network SDK and very simple - like 20 lines of code to do read, listen, and write
        * it sounds like maybe one wallet connect is needed at beginning but then never again i think
    * tracking trying to use index.network for my projects
      * [[2024-06-19]]
        * the docs are too unclear for me to use rn i think
        * for example, i couldnt even tell if all items added to an index need to be URL. had to ask on discord and wait
  * features
    * create index/list of ANYTHING in decentralized manner. 
    * using NFTs - anyone who has proper NFT can ALSO add content to your index/list
  * how it uses Lit Protocol
    * me: for access to curated content of your indexes.
      * index network: Lit Protocol allows creators to specify on-chain criteria such as "user must hold an NFT" and the network provides signatures to those that meet those criteria. This brings composability to collaboration and enables a diverse range of new user groups —including companies, communities, and DAOs— to actively participate in the decentralized discovery ecosystem.
        * Question: does this just work for onchain conditions? Or can you use web2 api or something? Also, does it only work for NFTs or can it be any onchain condition?
  * questions
    * what is difference in Index Network and Kleros Curate
    * what is difference in index network and are.na?
      * seref:
        * I think I've been following are.na for about 5 years and I like it. Also, In the part where users create their own indexes, we are similar to are.na in terms of the relationships between indexes and channels. 
        * If I were to talk about our difference in addition to the expected benefits from ownership benefits and decentralized access control: In my opinion, while are.na focuses on presenting data, we are interested in querying functions, especially querying them together. Being able to compare them, to compose them. While doing this, we are focusing to preserve privacy, and bringing agents in the workflows to automate things. 
        * Besides, indexing a channel on are.na to index and querying it with your DAO index together might be a good integration idea though : )
    * why did Index Network not use Ocean Protocol for data access?