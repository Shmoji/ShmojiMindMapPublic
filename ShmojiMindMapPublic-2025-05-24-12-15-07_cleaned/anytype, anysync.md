  * what is it?
    * defined by their tech
  * their tech
    * anytype
      * what is it?
        * collaborative local-first note-taking app built with anysync
    * anysync
      * what is it?
        * their site: Any-Sync is an open-source protocol that enables local first communication and collaboration based on CRDTs.
  * code of anytype, anysync
    * questions
      * where is ACTUAL functionality defined for anytype APP in regards to CRUD of data?
        * anytype-heart repo in /core/application for account stuff - so i think it's just all in that core folder
          * tracking thoughts
            * [[2024-04-27]] found this because i traced it all the way back from anytype client to middleware to core folder using the AccountCreate method
  * questions
    * how is anytype/sync different from [[automerge from ink and switch]]?
      * their docs: "Although they share similar ideas regarding data representation, such as a logical ordering of object operations, they don’t offer content identifiers and encryption schemes."
        * me: so cids and encryption is answer
      * their docs: Additionally, they are designed to work with plaintext data, while any-sync relies on a binary format to support complex data structures.
      * their docs: hybrid networking support: We thus designed data structures that fit our requirements. Notably, none of the solutions mentioned support hybrid networking, which would require us to build something on top of them.
        * me: i didnt really get this from their docs: 
          * We also considered using IPFS, but its approach to content identifiers didn’t meet our use cases. While IPFS could address our requirements for hybrid networking, it uses CID to describe documents, and this CID changes with each modification. However, we need documents to have stable identifiers for linking and other purposes.
          * Creating stable identifiers and implementing logic to merge different document states on top of IPFS would be too complex, so we chose a straightforward approach.
    * how is anytype monetizing?
      * seems multiples ways:
      * 1) some mebership thing
      * 2) maybe through licensing their OS software when it's used for commercial use (specifically i think the anysync software that runs on nodes)