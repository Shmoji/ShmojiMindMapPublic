  * tracking learnings in general
    * [[2024-09-02]]
      * For = blue, Against = orange
  * tech
    * atom, identity
      * it's basically a thing of any type
      * each one has DID
      * each one has vault for people to deposit/withdraw into like ideamarket tokens
      * Q: what happens if many people create same atom?
    * staking on atoms (by depositing into its respective ERC-4626-esque Vault)
      * By staking ETH on the Atom, you’ll earn fee revenue whenever any subsequent user interacts with the Atom. The more you stake, the higher your % ownership, and the higher your proportion of fees
    * triplet, claim
      * a triple may be something such as [Vitalik] [founderOf] [Ethereum], wherein [Vitalik], [founderOf], and [Ethereum] are all Atoms
      * Each ‘Claim’ also has an ‘Identity’ - therefore, Triples can also have an associated Atom, allowing them to be used as Atoms in other Triples - enabling the expression of arbitrarily-complex statements.
      * Each Triple/Claim in Intuition has two associated ERC-4626-esque Vaults—one for the 'positive' (true) side of the Triple/Claim, and one for the 'negative' (false) side. Staking ETH in the 'positive' Vault would signify that you believe the statement represented by the Claim to be true, while staking ETH in the 'negative' Vault would indicate that you believe the statement to be false. To draw a parallel, you may think of this as a non-resolving prediction market.
        * having 2 vaults for true and for false tightly integrates sentiment with the statement, eliminating the need for separate statements to express agreement or disagreement.
        * Please note that it is not possible to stake on both the Positive and Negative Vaults of a Triple simultaneously; you must withdraw your entire position from one Vault before staking on the other.
      * Cascading Positions:
        * When you stake on a Triple, a portion of your deposit is automatically allocated to the Triple’s underlying Atoms, since your interaction with the Triple indicates your belief that these constituent Atoms are relevant to the system.
        * For example, if you stake on the Claim, [Vitalik] [founderOf] [Ethereum], you will also be staking on the Atoms [Vitalik], [founderOf], and [Ethereum]. This process enhances Intuition’s TCR (Token Curated Registry) by indicating which Atoms are most frequently utilized across the Intuition system.
        * Q: what about negative staking? feel it doesnt make sense to negative stake on the solo pieces just bc neg stake on the whole triplet...
    * lists and queries
      * Intuition’s primitives offer the following as query parameters:
        * Atom Data
        * Subject
        * Subject Atom Data
        * Predicate
        * Predicate Atom Data
        * Object
        * Object Atom Data
        * Attestors (users staked)
        * Stake Amount (by user)
        * Stake Timestamp (and, by proxy, Stake Duration)
    * tags
      * Tags are your shortcut to organizing and finding what matters most, as well as the underlying feature that makes lists possible. Attach tags to any ‘identity’ (atom) in the Intuition knowledge graph to easily search and reference that information later. Super helpful when you want to stay on top of everything or discover something new! Structurally, Tags are simply Claims with the Predicate [has tag].
      * Adding Tags to an Identity helps with discoverability for you and others later! Tagging is also how you add Identities to Lists. For example, to add this identity to the [Wallets] List, you would tag it with [Wallet]! Behind the scenes, tagging involves creating and staking on a Triple with the Predicate [has tag], and the Object [Wallet].