  * MPC wallets
    * what is it?
      * works in conjunction with AA. An MPC-powered wallet can support anything and everything a normal self-custody wallet can with the added benefits of
        * 1: cross chain compatibility
        * 2: ability to process off-chain information
      * An MPC wallet is a smart contract wallet whose private key is divided, encrypted, and shared among multiple parties, in Lit’s case the key is stored across the Lit nodes and only an authorized party can decrypt and recombine the key shares to generate a signing key.
  * what it allows for
    * allows for authorization processes to occur outside of the blockchain, the underlying key generation and signing rely on cryptography off-chain. Despite this abstraction, users will need a solid understanding of blockchain technology to use MPC wallets securely
  * questions
    * how can any of this be off chain?
      * ### How Off-Chain Works in MPC
        * Local Computation: Each party performs computations on their own data locally. No data is exposed to the other parties or to the blockchain.
        * Partial Results: Parties generate partial results or "shares" based on their local computations.
        * Combining Shares: The partial results are combined to get the final result. This can be done off-chain or be recorded on-chain for verification.
        * Anchoring to Blockchain: If needed, a hash of the final result or a proof of correctness can be recorded on the blockchain for transparency and immutability.
      * further questions
        * so you can trust this offchain because why?
          * Cryptography: The cryptographic algorithms used in MPC are designed to be secure. They ensure that even if some parties are malicious, they can't derive meaningful information from the partial data they see.
          * Zero-Knowledge Proofs: These can be used to verify that a computation was performed correctly without revealing the actual data involved.
          * Commitment Schemes: Parties commit to their input beforehand, making it impossible to change the data after the fact without detection.
          * Secure Channels: Communication between parties can be encrypted and authenticated, ensuring data integrity and confidentiality.
          * Auditability: The final result or a proof of the computation can be anchored back to the blockchain for transparency and immutability, providing a way to audit the process.
  * related
    * [[lit protocol]] uses MPC to provide a blockchain-independent middleware layer that enables secure reading and writing of data between blockchains and off-chain platforms. With the added benefits of encryption, access control, and programmatic signing, Lit enhances the capabilities of what’s possible with account abstraction, such as allowing compute of off-chain data with on-chain conditional signing.
