  * what is it?
    * when you make move on ETH, there is hidden high-stakes game going on - that is MEV. Game can be secret for cheaper, more efficient, transactions - OR sometime the cause of HIGH fees and DELAYS. Goes both ways.
  * noteworthy stuff
    * how ETH txs work
      * initiate tx
      * enters mempool (waiting room for pending txs) - when building a block, the block proposer can choose and prioritize tx (and order of tx in block) from mempool based on tx fees
      * MEV causes twist in the above step. Block proposers can do what said prev, but also add their own tx. The sequence of these tx can sometimes yield profits bc:
        * Sue has tx to BUY. Bob has tx to SELL. Block proposer can use the fact that BUY increases DEMAND with knowledge that Bob's SELL will happen after in order to profit