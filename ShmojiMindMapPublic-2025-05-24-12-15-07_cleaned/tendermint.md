  * what is it?
    * consensus engine
    * software for securely and consistently replicating an app on many machines
      * secure and consistent replication is a fundamental problem in distributed systems. it plays a critical role in the fault tolerance of a broad range of apps, from currencies, to elections, to infrastructure orchestration, etc
      * Securely: tendermint works even if up to 1/3 of machines fail in arbitrary ways
      * Consistently: every non-faulty machine sees the same tx log and computes the same state
  * terms, concepts
    * consensus engine
      * Tendermint Core - ensures that same txs are recorded on every machine in the same order
    * Application BlockChain Interface (ABCI)
      * it is interface between:
        * the app business logic (state machine)
        * the replication layer (consensus and peer-to-peer networking)
      * Tendermint separates the business logic layer from the consensus and P2P networking layer by decoupling them through the ABCI protocol, abstracting away the details of the application to an interface, which is implemented as a socket protocol.
      * allowing transactions to be processed in any programming language. Unlike other blockchain and consensus solutions, which come pre-packaged with built-in state machines, developers can use Tendermint for byzantine fault-tolerant (BFT) state machine replication of applications written in the language and using a development environment of their choosing.
