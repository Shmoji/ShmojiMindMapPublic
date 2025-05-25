  * Lit journal
    * [[2023-10-09]]
      * im trying to learn the key concepts by coding it - but struggling to catch the spark that makes things click. I downloaded an AA repo and it works almost instantly. I think i need to find a way to convert it so it works with the Emote auth system and then everything about lit will click for me.
      * i learned Lit account abstraction using this demo repo: https://github.com/LIT-Protocol/lit-pkp-auth-demo
    * [[2023-10-14]]
      * Think im done with Lit for now until they have tut on how to do MFA. Currently i can get everything to work but i cant risk having my app attach data to PKP address without understanding how when user's gmail gets hacked - they can still get access to that PKP back.

  * what is it?
    * A decentralized key management network, Lit can be used in place of centralized key custodians and other key management solutions (such as ur gmail account, X account, etc - i think lol)
    * an [[multiparty computation MPC|MPC]] network
  * features
    * Programmable Key Pairs (PKPs)
      * access control
      * allow you to securely store your data encrypted
        * if someone hacks Google account that generated the PKP - isnt that data gone forever that was tied to that PKP address?
      * i think a PKP is a NFT
    * Lit Actions
      * Lit Actions are IMMUTABLE JavaScript functions stored on IPFS. Actions can be thought of as smart contracts with superpowers: they have network access and the ability to make arbitrary HTTP requests
      * Lit’s native implementation of JavaScript smart contracts that are blockchain agnostic. They can communicate data across blockchains, interoperate between previously disconnected ecosystems, and use off-chain data sources in their computation by making arbitrary [HTTP requests](https://developer.litprotocol.com/SDK/Explanation/LitActions/usingFetch?ref=spark.litprotocol.com)
      * Lit Actions are used in conjunction with PKPs to give smart contracts signing capabilities. Each PKP is generated collectively by the Lit network in a process called Distributed Key Generation (DKG) whereby each node only holds a share of the underlying private key (a key-share) and the complete private key never exists in its entirety.
    * Claimable Keys (HD Keys)
      * what they do?
        * allow you to send funds to a phone number, X user, email, etc - that can then be claimed by that person at any time

    * Lit Nodes and networks
      * what do Lit Nodes do?
        * i think they basically allow all the functionality of the protocol to work
          * so if these are not decentralized, then this seems like a fail to me (although, most of it seems open source, so maybe someone could always just fork)
      * where are Lit Nodes stored/hosted/ran?
        * Nodes are always part of a certain network. Like Jalapeno, Serrano. You can find the list of networks in Lit docs.
        * Currently the Lit team is running all the nodes. It is unaudited and the nodes are not distributed yet
          * If this never happens (distributing nodes/decentralized network), then that is not a good signal. BUT they say: data is persistent and we plan to support this network (called Jalapeno) in perpetuity. We are in the active process of decentralizing and working towards a decentralized mainnet release
      * what networks are available right now?
        * Jalapeno is the centralized main default network right now. I dont think it currently supports the AA stuff yet
        * Serrano is the testnet. Is being turned off soon, but it does support AA. I think maybe the new testnet called Cayenne is available now, but not sure
  * terms
    * relay server
      * docs: Relay Server is a server that is centrally run by the Lit Protocol team to facilitate and subsidize some interactions with the Lit Protocol smart contracts.
        * will this ever be decentralized somehow?
          * me: i dont think it can be. Maybe it can but idk how. BUT good thing is they allow you to run your own or mint PKPs directly using Lit contracts. ALSO, the relay server code is totally open source
      * Lit YT owner: a hot wallet that pays the onchain transaction to associate an initial authentication credential with a PKP
      * The Lit Relay Server enables you to mint PKPs without worrying about GAS fees. You can also use your own relay server or mint PKPs directly using Lit's contracts.
      * If you are using Lit Relay Server, you will need to request an API key [here](https://forms.gle/RNZYtGYTY9BcD9MEA).
      * Not the same thing as [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/account abstraction AA ERC-4337#^XmmN5Z6_8|ERC-4337 Bundler node]]
    * SessionSig
      * what is it used for?
        * used to sign all requests to the Lit Nodes
  * questions
    * i understand this process: 1) user auths using their gmail account 2) this mints PKP and associates public ETH address with that gmail account. But how does the user gain access to that ETH address? they never receive a private key for it or anything. Like for example if they want to use that ETH address on different websites
      * me: the wallet address is just an interface
      * me: with Lit-generated wallet addresses, you do not get access to private keys. The private keys are fragmented across many Lit nodes. Then, the origin AuthMethod you used (like google login) is how user gains access to that wallet or performing transactions with that wallet.
      * me: so if user's google hasnt been hacked, they should be able to login with google on any website, which gives access to generated wallet, which gives access to DID generated from that wallet, which gives access to user's data ANYWHERE (this brings the question of adding backups which i ask below)
      * JLM answer from Litcord:
        * Lit Protocol uses "wallets" like interfaces to enable users to interact with dapps and bridge across networks. These wallets can be standalone applications or integrated directly into dapps for seamless wallet interactions. At the time the private key is generated, a corresponding public key (address) is also created - this is the address displayed to the user. The dapp or wallet has knowledge of this address to show the user.
        * The main difference between a normal wallet and Lit Protocol is where the private key is stored. With Lit, the private key is split and distributed across nodes in the network. To authorize transactions, users authenticate via their Google account, signaling to the nodes that signature(s) are needed. Typically, wallets store private keys locally, encrypted. When a user unlocks their wallet or a dapp connects, the wallet authorizes access and provides signatures as needed. The wallet constructs, signs, and broadcasts transactions on behalf of the user.
        * Lit Protocol follows a similar flow, but authentication happens at the protocol level. When a transaction is requested, the wallet forwards it to the network. After verifying identity via social login, the nodes generate partial signatures that are combined into a valid full signature for the private key. The private key itself never exists wholly anywhere. This effectively distributes and decentralizes the security of the private key across the network.
        * In summary, wallets and dapp interfaces are still needed to bridge the connection for users via intuitive interfaces. Lit protocol just moves the security point of the private key from wallet to a distributed network allowing the network to authenticate the usage of the private key. All of this happens very quickly behind the scenes so overall there is no major UX difference for the user in a wallet or dapp.
    * if you Auth with a web3 wallet, does another address get generated or does it use the one you authed with?
    * is there any way to backup the data tied to the generated PKP? For example, user does login with google account and PKP is generated. Then, the app stores that user's data in a decentralized storage network using the generated ETH address from the PKP. But then the user's google account is hacked. Which means they no longer have access to the ETH address that basically holds their data. Is there anyway for the user to add multiple methods of auth for 1 PKP?
      * JLM answer from Litcord:
        * Yes, theoretically you can add multiple authentication options for a single PKP pair as Lit directly supports multiple auth methods set either by the PKP Permissions contract or the user who owns the PKP NFT. A custom Lit actions can also do this and provide Auth methods that aren't directly supported by Lit directly.
        * Additionally I believe you can request the PKP from the network for client side encryption meaning the key has to exist in a whole form on the client application so you could in theory backup it up however you deem fit. The intent though is that the key was for encryption so that would be a work around not the ideal.
    * what is auth process using Google with Lit?
      * user clicks login with google button. It basically does same oauth process i know about all with an SDK
        * (not sure how they avoid needing config variables and dev setup of google console tho bc my backend google auth repo needs those). I think they do do dis - i saw some code in relay server repo doing something like this - no idea when it gets called tho
      * Lot more to frontend process im not putting here. if future me thinks i should put it, then do it
      * If useEffect detects user is authenticated after redirect back to your app, create a PKP using that AuthMethod of Google. This calls provider.mintPKPThroughRelayer(authMethod) from lit sdk
      * Eventually that leads to relay.ts where API call to RELAY SERVER happens (in a different OS repo).
      * Eventually leads to code in relay server that calls smart contract function to mint PKP
      * TODO: add logic that smart contract calls here one day
      * ...
      * Eventually relay server finishes minting and your app detects that in mintPKP. You will be returned with a pkpTokenD, pkpPublicKey, and pkpEthAddress
      * if user has authMethod, then fetchAccounts (pkps) - this makes contract call too fetch pkps through the relayer.
      * if user is authed, and has multiple pkps, then they have to choose one (maybe could get this step idk)
      * if user is authed and selected a pkp (detected in useEffect), now time to init a SessionSig. This calls lit SDK to getSessionSigs. Im uncertain if this ever calls a contract. I think it uses SIWE mixed with Lit Nodes to create a session.
      * Once user has SessionSig, they can now sign messages with their PKP. Why does this mean anything at all?
        * I think this is cool bc you can now do the wallet signing thing that used to popup a MetaMask popup - but now without all that. But i still dont really understand what signing is even for. Like why do they need to sign anything if they're already authed into the app? Maybe extra security? I remember only time IM used signing was to login to web2 IM account.
    * what are the big dependences for Lit Protocol to work?
      * user to use some AuthMethod (google, discord, email, phone, wallet)
      * Relay Server
      * Lit SDK
      * Lit smart contracts
      * i think ERC-4337 somewhere inside the Lit smart contracts (but i havent learned this part yet). 
  * related
    * [[lit contracts]]
  * similar tech
    * [[particle network]]
