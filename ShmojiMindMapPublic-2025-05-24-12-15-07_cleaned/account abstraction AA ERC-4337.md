  * what is it?
    * in general, is the ability to set the validity conditions of a transaction programmatically.
    * If I could rename account abstraction to be more intuitive, it’d be called “programmable transaction validity.”
    * AA is a technique that allows the use of smart contract wallets containing arbitrary verification logic to confirm the conditions of a transaction programmatically. It moves crypto from the current approach of one-account-fits-all, where someone can lose everything with a small mistake, to a future where an account can be tailored to people’s needs. AA is a highly effective solution to address significant user experience issues in web3.
    * In account abstraction, authentication, signing, and submitting transactions are unbundled. This is made possible by separating the transaction's signature from the account address, allowing for possibilities like switching between different accounts in a single transaction.
  * key points
    * ERC-4337 Bundler node ^XmmN5Z6_8
      * a core infrastructure component that enables account abstraction to work on any EVM network without requiring any changes to the protocol. Its purpose is to work with a new mempool of UserOperations and get the transaction included on-chain
      * not same thing as Lit relay server
  * the problem AA solves
    * 1)
      * Currently, on Ethereum, a transaction is valid if and only if:
      * 1. There's sufficient balance to pay gas.
      * 2. The nonce is correct.
      * 3. It has a valid digital signature.
      * But what if developers could define a different set of conditions in which transactions are valid?
  * what is it not?
    * paying users’ gas fees
    * native multi-sig
    * web3auth type “social login”
    * NOTE: You can do these things as a RESULT of an account abstraction implementation.
  * what UX improvements it enables:
    * Social recovery of wallets
    * Batching transactions
    * Applications can pay for the gas of their users’ transactions
    * Use wallets from different ecosystems (or same, that use different signature schemes)
    * Walletless web3 login
    * Users don’t need ETH in their “regular” wallet to initiate transactions
    * Ability to put 100% of funds in a multisig and initiate transactions from there directly
  * questions
    * if someone logs in to website for first time with gmail and it generates wallet for them, then someone hacks their gmail - does hacker now have access to their wallet and that account on that website?
      * i think so. What would be the defense against this? maybe 2 factor auth
  * people that are knowledgable on AA
    * johnrising_ on X
  * related
    * [[multiparty computation MPC]]
    * [[userops (UserOperations)]]
    * [[alchemy account kit]]
