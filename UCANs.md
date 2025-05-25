  * what is it?
    * Universal Capabilities Authorization Network
    * They are a way of implementing access control that focuses on capabilities rather than traditional user-based or role-based access control models. In a UCAN system, entities (like users or services) are given capabilities that grant them specific access rights to resources or actions. The key idea is that access to resources is determined by possessing the appropriate capabilities, and there is no need for centralized user management or role assignments.
    * me: Noosphere is using them. They seem to be a data structure stored in IPFS. Your key stays on your device and somehow that key and using UCANs together stored on IPFS (with help of "spheres" is key) - no dependency on servers.
    * cdata: UCANs use DIDs as building block. DIDs are identifiers, UCANs are [[OCAP]] using those identifiers
    * gordon: extension of JWTs that does user-owned auth