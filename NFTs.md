  * tracking thoughts on where to sell your NFTs as creator
    * [[2024-01-17]]
      * i put my first shtory on ETH mainnet and realized after, maybe not ideal
      * ETH layer 1 is good bc no bridging bs needed. more simple. Also some big marketplaces like foundation. OpenSea is big, but not really in a "i wanna find art i like" way
      * i didn't really vibe with any of these marketplaces for some reason
      * i kinda vibe with objkt which is tezos, but it's filled with people posting art with no interaction. And tezos chain seems dead and nowhere near as tech advanced as ETH
      * there's also Zora which is layer 2 EVM. Aesthetically i vibe. Main issue is needing to bridge. i also vibe bc their ui makes interaction with art easy - but im not sure why, but you can see tons of people interacting
      * think im going to recreate shtory 1 and collection on Zora as experiment. Heck may do on objkt too. Heck, Solana too. Heck BTC inscription too

  * terms
    * what is an "edition"
      * me: NFT with x number of copies. Same visuals/content per copy, but different tokenID
      * GPT3.5
        * Each item within the edition is identical in terms of its content, but they are distinguishable from each other because they have unique token IDs on the blockchain.
        * Editions are often used in the NFT space to create scarcity and exclusivity for digital assets. Collectors may be drawn to owning a specific numbered edition within a limited set, and creators can use this concept to control the supply and demand for their digital creations. Additionally, some editions may have special features or benefits associated with them, such as access to exclusive content or events, which can further enhance their desirability.
    * lazy minting: only mint once someone buys and then the user that is buyer pays for all gas fees (including minting)
  * how TOs
    * how to use and view NFTs in hardware wallet? ^LdolpLOPF
      * connect hardware wallet to MM in browser and then use MM portfolio. Can send NFTs from MM.
    * how to set royalties on your NFT?
      * best way so far seems to use studio.manifold.xyz - their ui for creating NFTs with royalties is just SO smooth - it works using [[Manifold Royalty Registry]]
  * questions
    * what is best resolution to create NFT image in?
      * A bit up to interpretation, but i vibe with this: An image resolution of **2000×2000 to 3000×3000 pixels** is ideal for most NFT art, balancing quality and file size.
      * Some platforms it depends, but ideally you arent posting to just one platform bc it's supposed to be decentralized
      * Looks like poppel uses 800 by 800 mostly
    * how to know when all price action on NFT is faked?
      * i suppose doesnt matter when you actually vibe with the art
    * where is best place to view ALL NFTs? (im sure this will change over time)
      * for ETH layer 1:
        * on web: https://etherscan.io/tokenholdings?a=
        * on mobile: Rainbow wallet
          * really dig the ui
      * ((-1sMmS0LR))
    * what are different ways to sell NFT?
      * MINTING PROCESS
        * mint only a few editions
        * allow infinite editions (this is called [[open edition NFT]])
          * GPT4 on why:
            * The decision to create infinite editions impacts the perceived rarity and value of the NFT. While unique NFTs can be highly valued for their scarcity, infinite editions might be more affordable and accessible, but potentially less valuable as collectibles due to their abundance.

          * questions
            * do all NFT markets allow this?
        * just mint one. then, if other people want one, just mint more when needed
      * LISTING PROCESS
        * 1) list it as auction that ends after x time
        * 2) do not list it at all - buyers can create offers still anyways and you accept offer if you feel it's right price
        * 3) 
    * how to decide which chain to put your NFT on?
      * PRICES: interactive NFTs (and maybe all NFTs) seems to sell higher on ETH compared to Tezos - no idea if that price action is faked or not tho. Seems most sell for few dollars on Tezos and hundreds or thousands on ETH

    * what if you bought NFT that is 1 edition, but later realize that artist minted same NFT again with more editions? OR they put on another chain?
      * i think personally i'd be mostly okay with that since i still own the art and that's all i really care about. These things: 1) my wallet owns the art 2) proof that the original creator created that art 3) being able to view the art anytime i want
      * i could see how that may make the artist seem less trustworthy though in some people's eyes
    * how to know how many NFTs there are for a NFT contract?
      * Get the total supply of this contract (i think can call this on any NFT contract without costing gas)
    * when creating NFTs, do you deploy a new NFT contract every time you want to sell a new NFT?
      * GPT4: Customization and Series: If you have a series of NFTs (like a collection of digital art), all of them can be minted under one contract. However, if you plan to launch a completely different project or series that requires different rules or structures, then deploying a new contract might be appropriate.
      * what are most people doing in the NFT space nowadays when it comes to this?
        * GPT4:
          * Collection-Based Contracts: Most creators and projects in the NFT space use a single smart contract to manage an entire collection of NFTs. This approach is prevalent in art collections, gaming tokens, and virtual real estate. Each item or artwork in the collection is a unique token under the same contract, identified by a unique token ID.
          * Platform-Specific Contracts: Many NFT creators use popular platforms like OpenSea, Rarible, or Foundation, which provide user-friendly interfaces for minting NFTs. These platforms typically manage the technical aspects of the contract deployment, allowing creators to focus on the artistic or conceptual part of their projects.
    * ROYALTIES
      * NON-TECHNICAL
        * why set royalties?
          * muh-nee - everytime your art sells on 2ndary market - that's passive income
          * that passive income could fuel you to create more art
        * does setting royalties hurt others by you benefitting?
          * i dont think so??
      * TECHNICAL
        * for the NFTs you mint from the contract you deployed to set royalties everytime NFT is transferred, do you have to implement that on your NFT contract?
          * Yes. Or you can create your NFT contract using the NFT marketplaces so you dont have to write that code
        * OPENSEA:
          * you set royalties on the COLLECTION you create
          * you cannot set PER NFT royalty on opensea - only per collection - the chosen collection on opensea will override here
    * [[interactive NFTs]] [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/interactive NFTs#^TmaljIO3n|questions]]:
  * related
    * [[interactive NFTs]]
    * [[buying NFTs]]
    * [[ERC-721, NFT standard]]
    * [[ERC-2981, NFT royalty standard]]