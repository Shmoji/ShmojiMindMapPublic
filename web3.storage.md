  * what it do?
    * me: stores your data on ipfs and filecoin forever (as long as you pay bish) and renews any necessary things to keep data stored
      * When storing data on Filecoin, you enter storage "deals" that have a finite duration. i guess using just filecoin this part can be complicated?? web3.storage service currently renews deals for you to ensure your data deals never expire.
      * i assume they also handle pinning on ipfs since they talk about storing on ipfs
    * me: you pay deez guyz and then you dont need to run your own ipfs node or filecoin node or whatevs - but if you stop paying them...your data is gone...but at same time it's the same thing if you're paying for AWS server to host IPFS node and can no longer pay that. i think only fix here is to run node on your own hardware so that you dont have to pay anything since running on your hardware
    * filecoin site: web3.storage is a storage on-ramp or storage helper - Storage helpers provide libraries that abstract Filecoin deal-making into simple, streamlined API calls and storing the data on [[ipfs]] to provide more efficient and fast retrieval for your content.
  * noteworthy stuff
    * relation to [[Filecoin]]
      * web3.storage uses the filecoin decentralized network to back up all its data
  * questions
    * how to upload a folder?
      * if just one or a few separate files: use console.web3.storage (doesnt work for CAR files rn)
      * if entire connected folder: use w3 cli - web3.storage has docs on how do https://web3.storage/docs/how-to/upload
      * but paths get very screwy when uploading using w3storage, so i recommend moving everything to one single folder if possible
