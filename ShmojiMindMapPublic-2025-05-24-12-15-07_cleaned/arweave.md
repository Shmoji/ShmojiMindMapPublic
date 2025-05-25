  * how TOs
    * how to deploy unity webGL game to PROD/mainnet
      * [[2025-02-08]]
        * using ardrive cli didnt seem to have the needed details for it, BUT arweave cli did. Need full control over content types basically
        * getting AR tokens is about impossible in USA, so i got TurboCredits instead just using regular debit card - and they work fine for arweave storage using cli
        * tbh it was simple thanks to cursor compose lmao
        * TURBO SDK IS THE MOVE: didnt end up even using arweave cli since not using AR tokens - i used the "import { TurboFactory } from '@ardrive/turbo-sdk'" turbo SDK. NOTE: turbo API and regular arweave upload API just didnt work, BUT Turbo SDK did work
        * TAKES TIME: after uploading, can take longgg time for it to even show up on block explorer...so be patient

  * what da value?
    * compelling to know I can pay a single transaction fee and store my information forever, unlike other types of hosting where you are held hostage to pay monthly fees for the rest of your life or your data will be deleted (this is case for ipfs and web2)
  * pricing
    * it v good, you can look it up, but [this](![](https://twitter.com/dabit3/status/1665492170508312576)) shows good example related to pricing:
  * noteworthy stuff
    * Atticus: it's not p2p for most arweave users. It is for miners.
      * more context: It's p2p for the miners but for security reasons miners restrict access to certain ips. Most people need to use a gateway to get the data - also miners don't index the data in a very usable way, gateways implement a graphql interface for search for transaction tags
      * big difference here compared to IPFS where everyone is gateway and a "miner" meaning they hold the data. Another diff is IPFS requires pinning and arweave has redudancy metric for duplicating data across nodes so if node fails data isnt lost
    * has miners to financially incentivize the storage of data
    * if all miners died and their computers exploded, would important data stored on arweave be lost?
      * atticus: Yes
  * related
    * testing arweave deployments: [[arlocal]]