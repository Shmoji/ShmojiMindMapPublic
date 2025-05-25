  * what it do?
    * DOES NOT enforce royalties. INSTEAD, creates the ability to query the royalty info about an NFT (who receives royalty and how much) - now the royalty info itself is decentralized and doesnt need to be registered with each marketplace
    * But NOTE: the above requires each marketplace to implement that extra logic of getting the royalty data from chain
  * ISSUES
    * not backward compatible - so old NFTs created without this standard are poop for royalties
      * maybe if you had made your NFT contract upgradeable, then you'd be good - but most did not do that
    * many markets implemented their own version of this standard - but each varies greatly
    * SOLUTION to all above: [[Manifold Royalty Registry]]
      * GENERALIZED: it wraps all existing royalty info view functions (from diff markets), including EIP-2981
      * BACKWARD COMPATIBLE: fixes dis issue
      * PROBLEM with this registry: any market can still ignore the registry, allowing people to sell NFTs and circumvent paying creator royalties
        * NEXT SOLUTION lol: [[The Operator Filter]]:
          * allows creators to defend against 0% royalty markets (or any app) by making a BLOCK LIST that prevents their NFTs from selling on those markets
          * this CAN be enforced onchain bc markets are usually contracts that have permission to transfer an NFT on another's behalf
  * questions
    * as NFT creator, what to do to guarentee royalties?
      * register them on [[Manifold Royalty Registry]]
      * use an [[The Operator Filter]] - even if your block list is empty - good to have code their in contract just in case
      * use extensible contracts - ex: NFT contract creator of Manifold allows plugins in their code. So if you created NFT months before operator filters were a thing, you could still add a plugin that allows for it now