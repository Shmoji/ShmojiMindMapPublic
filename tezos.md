  * tracking thoughts
    * [[2023-12-22]]
      * im currently keeping my Tezos NFTs using briskett since it's only wallet provider that supports Trezor
      * to buy tezos NFTs you need tezos coin. Couldnt remember how i got last time, but this time i bought using Coinbase on Kukai
      * Kukai dependent on web2 email or browser - so i sent my NFT to Briskett since it uses Trezor
    * [[2023-12-30]]
      * this morning i started with goal that i wanted to buy tezos NFT from a mobile device. i learned many things:
      * 1) it's hard finding authentic NFTs - is this OG creator, is this scammer - you just gotta do your own research and some bit of trust. I ended up finding art that had some sort of soul that clicked with me and research seemed to show an authentic creator
      * 2) kukai in web of mobile device seems best to buy the NFTs. You have to sync wallet in objkt to kukai first - then you can buy. My plan is to then send to hardware wallet after
      * 3) the thing i wanted to buy is auction so you have to use wrapped XTZ or oXTZ for auction - you can do this wrapping directly in objkt - find on wallet button after syncing to kukai
      * 4) you have to switch back and forth between tabs to use kukai on mobile which is much more confusing than on desktop
      * 5) i wrapped some tezos to place bid on NFT and then i placed bid and it seemed like it just wrapped more of my tezos and didnt even use the already wrapped tezos lol
      * now im just wondering if i'll get notifications for the auction to my email - because that would suck if not and my guess is that i wont

  * key points
    * a blockchain
    * this shit seems used for minting a lot of NFTs. It's somewhat known as THE art blockchain for some reason
  * questions
    * how can you store your Tezos NFTs in hardware wallet if they dont support that chain?
      * me: briskett - details below
      * i dont think you really can - but you can generate a new Tezos wallet in a Tezos wallet provider that is derived from your hardware wallet. So that means you can only access those NFTs with the hardware wallet - not just the Tezos wallet provider. Only certain wallet providers support deriving from hardware wallets
      * Tezos wallet provider that allows derivation using browser wallet: MM does and then MM has Tezos wallet Snap created by [[airgap.it]]
        * basically your MM wallet master key is used locally in your browser i guess to generate a Tezos address private:public key pair. Since on browser, your master is harder to steal i guess? at least compared to Tezos address dependent on your web2 email. Deriving from hardware wallet much better tho

    * can tezos minted NFT be sent to any other wallet. 
      * on Tezos chain, yes. Not to another chain, i dont think so.
    * what are some Tezos wallets?
      * [[kukai]] (1st one i ever used - i logged in using my gmail and it generates wallet for you - not v secure)
      * Temple Wallet
        * as of 2023 supports Ledger but not Trezor - v secure NFT storage yay
      * Briskett
        * on Trezor website as only wallet that supports Trezor - so i use it duh
        * maintained by like 1 person - BUT it's open source so can always locally run it

    * what is best way to view your Tezos NFTs?
      * prob objkt or teia.art
