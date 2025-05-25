  * tracking thoughts
    * [[2023-12-29]]
      * at least rn, imo this is more decentralized and better options for NFTs - at least ones that just store images ^K83g6kJt1
      * apparently it is cheaper than contract NFTs too ^_7nQz2-0O
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ethscriptions#^xQv8vVfVN|possible downsides]] updated

  * what it be?
    * me: so it's basically a protocol that formats calldata data in a meaningful way so it can be used as NFT
    * me: NFTs where data is stored in calldata instead of smart contract. contract created and maybe controlled by central party, whereas calldata is literally just on the blockchain
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ethscriptions#^K83g6kJt1|at least rn, imo this is more decentralized and better options for NFTs - at least ones that just store images]]
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ethscriptions#^_7nQz2-0O|apparently it is cheaper than contract NFTs too]]
    * creator guy: Also protocol guarantees global uniqueness of the content of all valid Ethscriptions! - this is thanks to their central protocol - not a decentralized factor of blockchain (i think)
      * An Ethscription is created whenever an Ethereum transaction is successful, and its input data (interpreted as UTF-8) forms a valid data URI. This URI must be unique, meaning duplicate content is disregarded. Ethscriptions support all valid mimetypes.
      * The URI’s uniqueness is guaranteed by ensuring that no prior block or transaction within the same block has identical content as the Ethscription.
      * The input data of any Ethereum transaction can also serve as a valid Ethscription transfer, as long as the data is the transaction hash of a valid Ethscription and the sender of the transaction is the rightful owner of the Ethscription.
      * When an [Ethscription is created](https://ethscriptions.com/), the recipient becomes the initial owner, while the sender is designated as the Ethscription’s creator.
  * possible downsides ^xQv8vVfVN
    * i saw someone mentioning calldata may not be permanent - somehow it could get deleted one day...dont know how true that is
    * apparently this is dependent on offchain consensus - is this true and is this bad?