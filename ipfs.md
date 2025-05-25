  * Questions
    * You could encrypt the contents of file posted on ipfs to keep data private, but how much effort does that take on your side? Like what goes into all that?
    * How can i use JS to add data to IPFS in a way that will PERSIST the data?

    * what is basic process of how storing data on ipfs works?
      * Command to store data (image, JSON, video, anything) on IPFS -> data converted into raw binary code -> binary code inputted into hash function and the output is the digest -> digest is multihashed into the CID
    * what is complicated process of how storing data on ipfs works?
      * Command to store data (image, JSON, video, anything) on IPFS
      * If the files are bigger than 256 kB, then they are broken down into smaller parts, so that all the part are equal or smaller than 256 kb. Can see the chunks of your photo/data using this command: ipfs object get Qmd286K6pohQcTKYqnS1YhWrCiS4gz7Xi34sdwMe9USZ7u
      * Each of these chunks is first converted into a **digest** using a hash function
      * and then digests are converted into **CIDs**. This is where IPLD comes in
    * what is Significance of Hash Function*
      * Hash functions take the data as input and give us an output(Digest) which is unique with respect to the data referenced by it and never changes.
      * If we change even a pixel in this image then the output will be different bc the input is different
      * This shows its **tamper-proof property**, hence making IPFS a **Self-certifying File System**. So if you transfer this image to anybody, he/she can check that if the photo received has been tampered with or not bc sender has the CID and you can check that CID of data has not changed. If it changed, it was tampered with.
      * Also, you cannot tell what was the input(in this case, cat photo) bc hacker would need to do the exact binary code, but can just see its output(the Digest). So, this also ensures a great amount of **security**.
    * what is Significance of CID
      * This CID is what IPFS will search for when we try to get back the image. For doing this, IPFS uses something called Multihash.
      * If CID changes from what someone sent you, it may have been tampered with.

  * how to
    * how to store encrypted data in ipfs
      * Option 1 - wallet signed data: the way Ceramic recommends in this tut: https://blog.ceramic.network/how-to-store-signed-and-encrypted-data-on-ipfs/

    * how to get data from IPFS OR view content on IPFS
      * In your browser using an IPFS HTTP gateway (can just google different Gateways)
        * Simple take the CID for the stored data and use a public gateway like so (1st value is CID): https://bafybeia7wh7jczfu6oxgoj67p6vgq3p4fzr2yvyby3ip3kwkd2bbqmssxi.ipfs.w3s.link/
      * Using JS in code
        * You can just query the IPFS HTTP gateway in point above.
        * web3.storage has js API for getting data, but they say it's not reliable right now.
    * how to view the DAG data of IPFS cid (in case the gateway shows a website or something, but you want the DAG data)
      * using IPLD Explorer: https://explore.ipld.io/#/explore/bafybeifpauacw3hqqvwxbr4islf5jdc7qlkqpp2whwjiuw745k3sbi27iq
  * Notes
    * Notes about public vs private data
      * If you post file on ipfs, anyone can see contents of that file if they have the CID,
      * You could encrypt the contents of file posted on ipfs to keep data private, but how much effort does that take on your side? Like what goes into all that?
    * Issues i ran into while learning ipfs
      * To use ipfs in JS, you needed to install prom-client, but literally nowhere does it tell you that.
    * Persisting data on IPFS (pinning) and garbage collection
      * Data will not be stored permanently on IPFS unless you PIN it to your OWN node. You cannot force others to pin it, but i think you can pay services to have others pin your data. It's free to a certain limit. 
      * Data not permanent unless pinned because garbage collection process will delete it if not pinned.
      * [[web3.storage|web3.storage]] project seems maybe like good way to easily use JS to store persisted data on IPFS and Filecoin at same time
        * Filecoin is needed because it is what persists data on IPFS, but they dont have their own JS API...which is where web3.storage comes in
    * Local IPFS nodes
      * Issues
        * You need to consistently run a local node if you want the data you add to persist. This cost money/memory/energy

  * Related
    * [[ipld]]