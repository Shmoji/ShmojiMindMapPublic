  * tracking UX of trying to use this platform as main one for creating art
    * [[2024-01-18]]
      * tried uploading shtory 1 and it just didnt work. Followed guide perfectly step by step. Nothing showed up and no errors. idk if it takes hours for ipfs to settle or what. is something in my zip of files causing issues? if so no errors are given to me. Why does it say it's a zip instead of html?
      * no obv way to get their specific testnet tokens nice - so cant test there and dont quickly know how to test
      * hmm objkt, ordinals, and solana looking a lot better with these issues now happening

  * what is it?
    * nft marketplace with best aesthetic so far i think
    * Zora Network, launched in 2023, is an EVM-compatible Layer 2 blockchain solution
  * questions
    * i see you can upload entire folder to create HTML NFTs - where is that data stored?
      * stored in IPFS according to this article: https://www.coingecko.com/learn/what-is-zora-and-zora-network-crypto
    * how does minting fees work?
      * total collector mint fee will remain the same at 0.000777 ETH (~$1.40) - but this total value is split various different ways:
        * me: tldr:
          * WHAT COLLECTOR PAYS: collector always pays minimum of 0.000777 ETH and that's default - called 0 ETH mint. If no that, then creator set price that is not default and collector will pay 0.000777 + whatever price creator set
          * WHAT CREATOR GETS PAID: if 0 ETH mint, they get paid 0.000333. If paid mint, they are paid price they set (could be more or less than default for 0 ETH mint)
        * EXTRA FROM THEIR SITE: the primary factor for how money is split is whether the edition is a 0 ETH mint or a paid mint. 0 ETH mint just uses protocol default price of 0.000777 for collector. Paid mint costs extra, which all goes to creator (so that defined price by creator + 0.000777) - but only price set by creator goes to creator - so they could accidentally set it below 0.000333 funny enough - which is default if 0 ETH mint
