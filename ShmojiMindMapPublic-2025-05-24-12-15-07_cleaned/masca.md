  * tracking
    * tracking research into masca
      * [[2023-11-22]]
        * Masca has several exciting features in the pipeline, such as:
          * Enabling users to store encrypted data
          * Supporting selective disclosure for VCs
          * Adding support for ComposeDB on Ceramic
    * tracking my UX with masca ^VFHIPpmEU
      * [[2023-11-22]]
        * I created my first verifiable credential VC using Masca. I think the credential just verifies me as Masca user, but idk. Confusing. Also all the json shown is confusing. Also terrible UX of waiting over and over and signing a million Metamask things
        * Then i refreshed site and my credential seems gone. This is because i have to click button on their site to make MM popup appear that i need to approve to share credential on their site. I can apparently have this auto-accept with some setting in MM, but couldnt find it. Oh i think setting is in Masca settings itself on their site. Idc anymore tho lol.

  * what is it?
    * open-source, decentralized identity wallet that lets you manage your off-chain identifiers and attestations
    * a MetaMask Snap plugin for MetaMask that extends its base functionalities for decentralized identifiers (DIDs) and verifiable credentials (VCs)—turning MetaMask into an identity hub.
  * noteworthy stuff
    * They are integrated with Ceramic and Ceramic put blog out on them at end of 2023
      * Ceramic, as one of the supported storage solutions in Masca, plays a crucial role in enabling users to store their data, have it available on different devices, and will serve as a foundation for data interoperability with other projects in the future.
    * Masca is developed by [Blockchain Lab:UM](https://blog.ceramic.network/r/4a24150b?m=d0d17d8c-2d98-428b-b016-2b3a76602e85), an R&D laboratory specializing in blockchain technology, decentralized identity, and decentralized artificial intelligence.
    * Masca uses Veramo Client for DID management, as well as for the creation, presentation, and validation of Verifiable Credentials
    * In alignment with Masca’s mission, the snap also offers flexibility around data storage, allowing users to toggle between the local MetaMask Snap state (which exists fully off-chain and exclusively in the user’s browser), as well as storage on the Ceramic Network.
  * questions
    * How Masca Uses Ceramic?
      * Masca is now live on Ceramic Mainnet! Ceramic is currently used in the Masca ecosystem for two primary purposes:
        * Verifiable Credential Storage: Since VCs are off-chain attestations, users must store them somewhere. Ceramic offers a scalable way to store attestations.
        * Schemas: Each VC has a strictly defined structure and data model, which are defined with schemas. Using schemas, VCs of the same type are consistent across different applications.
      * Users can freely migrate their credentials between Snap-encrypted storage and Ceramic Network as they wish. Selection of storage most often depends on the type of attestations and level of security/privacy needed.
  * related
    * [[verifiable credientials VC]]
