  * what is it?
    * tx.origin = sending account = EOA
    * Gas is always paid by the original sender (**tx.origin** in Solidity), not by any **intermediate **contracts. The gas used in a transaction is always subtracted from the balance of the sending account. So, tx.origin = sending account = EOA
    * The gas fee for any smart contract interaction is paid by the [[EOA (Externally Owned Account)]] that calls it. Even if the smart contract makes **another **transaction (as an **internal **transaction), it's considered to be part of the **original **transaction called by the EOA, so the EOA will have to pay the gas for the **entire **transaction.
  * what is EOA wallet?
    * examples: MetaMask
    * are like the old landline phones
    * controlled by private keys
    * different from a [[smart wallet, contract accounts, smart accounts]] (what they're usually contrasted with)