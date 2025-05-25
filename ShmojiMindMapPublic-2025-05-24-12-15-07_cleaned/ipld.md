  * What is ipld?
    * IPLD is the data model of the content-addressable web
    * me: IPLD is a data structure that HAS a data structure inside that is guaranteed to **link data with hashes**. So, can have list of IPLDs and they are all IPLD instances, however, each data structure inside can be totally different from each other. Yet the different data structures/data can all be linked together or found by their CIDs
    * IPLD is a set of standards and implementations for creating decentralized data-structures that are **universally addressable** and **linkable**.
    * me: in a way, it's a data model for any data. Instead of needing to define a data model for your app for a user table, IPLD is a data model for ANY data. No need to define a data model like you do with MongoDB.
  * **What Does IPLD Do?**
    * It allows us to treat all **hash-linked data structures** as subsets of a unified information space, unifying all data models that **link data with hashes** as **instances of IPLD**.
    * These structures allow us to do for **data **what **URLs **and **links** did for HTML web **pages**. My interpretation: it's saying that you can FIND any data using an address, just like you can find a web page using an address. Whereas, previously all data did not follow a standard, so could not find all data the same way. Now you can.
    * In IPFS, IPLD helps to structure and link all the **data chunks/objects**. So, as we saw in part 1, IPLD was responsible for organizing all the data chunks that constituted the image of the kitty🐱.
    * IPFS uses IPLD (IPLD uses Merkle DAG, or directed acyclic graph) for managing all the **chunks **and **linking **it to the **base CID**.
  * **What i got out of this**
    * The big part of IPLD is that you can store ANY data as a DAG node using ipfs.dag.put() and you will always get an interoperable CID back out. This CID can be used by anyone to find the data OR any lil piece of that data too i think
  * **ipld codec**
    * Questions
      * Where is the structure of data itself defined?
    * What is an ipld codec?
      * IPLD codecs are functions that transform IPLD Data Model into serialized bytes so you can send and share data, and transform serialized bytes back into IPLD Data Model so you can work with it.
      * IPLD codec does not dictate the structure of the data itself. The structure of the data and the keys can be defined by the application or data model, and different IPLD codecs may have different capabilities and limitations in representing and linking different types of data.
  * other noteworthy stuff
    * IPLD is not just a part of the IPFS project, but a separate project in itself