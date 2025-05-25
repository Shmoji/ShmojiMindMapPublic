  * TODO

    * [ ] Figure out how to create a file URL that is completely private for an algorithm to be published, that is totally free and secure
  * Elevator pitch / quick understanding
    * Access control for ANYONE/THING's data/compute.
    * Data pipeline with access control at CORE. Instead of building data wallet, data exchange, data DAO - you tokenize ACCESS and then all other techs/protocols can be added on top. Memory, compute, etc are all plug and play.
  * Use cases for ME

    * Sell my mind model as data. This maybe fixes issue of choosing data format because i choose format for my mind model. Also, random thought, maybe Ceramic can be used to choose data format.
  * Questions
    * Where to ask questions about OCEAN?
      * Ask AI chatbot. One is based off OCEAN docs and other is based on Ocean Protocol's ocean.py GitHub repo: https://app.algovera.ai/organizations?id=ocean

    * Is it financially better for individual to give their data to data union or to sell their data themselves?
    * DATA FORMAT: As a data seller, how do you know what format is best for buyers? I can imagine some consumers would want one format and others may want another format
      * Creator of DataUnion said this: The benefit of a DataUnion is, that our backend is a NoSQL database, so the data format can be dynamically adjusted from it depending on the format wanted by a data buyer.
    * When publishing data asset, What is difference in leaving "Provider URL" as default versus using a custom provider (and how do you even get a custom provider?)?
    * Algorithms
      * Can you store a variable in an algorithm and it will stay private? Such as a string holding the key for a key-DID?
      * If an algorithm is downloaded (some cannot be downloaded but some can, seller sets that), can the code be viewed? 
      * How can algo be truly private if you have to give URL for file containing code? A gist works, but then trusting github. IS this where private docker registry comes in? I see IPFS is option, but can it be encrypted still? Where would it get decrypted at?
  * How Tos
    * How to put completely private data on OCEAN?
      * Issues im having with figuring this out
        * Can you store a variable in an algorithm and it will stay private? Such as a string holding the key for a key-DID? Maybe i should just experiment with algorithms and ill find out answers.
        * how to use a local node in js (not an in-memory node)
        * Should my data be plain object, text file, CSV, or what?
          * This is probably biggest issue ive had. You can store is so many different ways and encryption adds another layer of complexity to it.
      * Option 1
        * Need to get data onto IPFS and the data needs to be signed and encrypted. This is because you want to make sure the data on IPFS is itself private
          * Need a DID that you control. Only this DID has access to data in IPFS. But then my question is: how can Ocean buyer get access to that DID bc they need data access too
            * I think you can create one in basic JS code just like in shmoji-experiments/store-encrypted-ipfs

    * How to publish and use datasets
      * Make sure to edit compute settings of dataset to choose which algos can run on this data
    * Algorithms
      * How to write and publish algorithm
        * Steps
        * Notes
          * You need to provide a file with the code for algorithm
            * Options:
              * A private gist from GitHub
              * Guy in tutorial said typically file with code would be hosted as file somewhere...but where is BEST and completely secure?
  * Notes
    * Published algorithms
      * Downloadable vs private: some algos are downloadable and some are not; algo seller sets this
      * Downloadable algos

    * Provider (of data services)
      * Whoever is running the provider has access to your data if using that provider.
      * What it does
        * The only component that can access your data
        * Performs checks on chain for buyer permissions and payments
        * Encrypts the URL and metadata during publish
        * Decrypts the URL when the dataset is downloaded or a compute job is started
        * Provides access to data assets by streaming data (and never the URL)
        * Provides compute services (connects to C2D environment)
        * Typically run by the Data Provider (huh?)
    * Compute-to-data (private data)
      * each compute job/algo runs in an isolated Kubernetes Pod (K8) with these VOLUMES mounted:
        * /data/inputs
          * Storage for input data sets, accessible only to the algorithm running in the pod. Contents will be the files themselves, inside indexed folders e.g. /data/inputs/{did}/{service_id} (so file names will not longer be what they were before)
        * /data/ddos
        * /data/outputs
        * /data/logs/
      * Good example to see how to access volumes in your algo in js: https://docs.oceanprotocol.com/building-with-ocean/compute-to-data/compute-to-data-algorithms#example-javascript-node.js
      * User defined parameters
        * Ocean Protocol allows dataset buyers to provide custom parameters that can be used to fetch the downloaded data in a specific format, download a different type of data or pass some additional input to the algorithms in the Compute-to-Data job.
        * There 2 are types of parameters that asset publishers can support:r
          * User defined parameters
          * Algorithm custom parameters
    * Data Farming

      * Risks
        * There is really no risk to DF. Only risk is if you need to sell your OCEAN, but you cant because it's locked.
      * Summary
        * Lock OCEAN for up to 4 years or less and get veOCEAN. When OCEAN unlocks, you get exact amount you locked back. veOCEAN cannot be unlocked before the pre-set time.  
        * Stake veOCEAN on datasets you find valuable and potentially get rewards if they are valuable.
      * Rewards
        * veOCEAN holders get earnings from community fees and Data Farming.
        * PASSIVE: 50% of community fees on Ocean Market go to veOCEAN holders. This is passive reward. So guess it doesnt depend on what you stake on.
        * ACTIVE: You stake on datasets you think people will consume. DF formula: DCV (data consume volume) * stake. Stake is amount of veOCEAN you allocated to dataset. 
    * Terms
      * DDO
        * Structured document containing metadata of data asset. Holds file URLs too. The whole DDO is encrypted.
        * The encrypted DDO is stored on-chain as part of the Data NFT. Indexers like Aquarius can decrypt the DDO for displaying purposes, but the file URLs can only be decrypted by exchanging the respective datatokens for this asset.
  * Vulnerabilities
    * Provider. Seems this is only vulnerability i can think of so far. At it lies on user. If you trust some data union and they secretly take your data, then it's kinda on you. The provider that runs compute-to-data has access to all data, even if private.
  * [[Ocean Protocol Dev]]
  * Partner projects
    * [[Filecoin]]