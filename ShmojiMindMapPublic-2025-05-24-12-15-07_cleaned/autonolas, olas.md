  * TODO soon
    * [ ] wait until new academy posted and start that for 1 hour at least
  * what is it?
    * many things that i need to differentiate. it's a company, a DAO, a bunch of products mostly related to autonomous agents
    * open source framework (what) for devs (who) to implement their own offchain apps that are secured onchain
    * provides framework to build FSM-based agent services
  * how TOs
    * how to setup AEA
      * based on quickstart demo (lots of unknowns)
        * either 1) fetch aea or 2) create aea and fetch/create any needed components
        * aea install (is this needed and what do? like what are aea dependencies?)
        * add and create private key for aea:
          * aea generate-key ethereum
          * aea add-key ethereum
        * aea run
    * how to setup open autonomy framework WORKSPACE for creating an Agent Service
      * me: git clone the below
      * their site:
        * For convenience, we provide a **Dev template** repository that you can fork and clone for your Open Autonomy projects, and use it as your workspace folder:
        * https://github.com/valory-xyz/dev-template
        * The **Dev template** comes with:
          * a preconfigured Pipenv environment with required dependencies, - although they dont tell you it requires poetry for install instead of pipenv
          * an empty local registry,
          * a number of preconfigured linters via [Tox](https://tox.wiki/en/latest/).
    * how to install remote packages from remote registry
      * first you need to be in a virtual env - can use pipenv or poetry or whatevs
      * edit the local registry index file (./packages/packages.json) and ensure that it has the third_party entries you need (can find example of this on their site). Then:
      * "autonomy packages sync" - The framework will fetch components from the remote registry into the local registry.
  * questions
    * CATEGORY: coding-related
      * what is the vendor folder in AEA project?
    * what is the remote registry?
      * where developers publish finalized software packages, similar to Docker Hub images
      * in first tut, you set this as IPFS registry as default using: "autonomy init --remote --ipfs" - This means that when the framework will be fetching a component, it will do so from the remote registry
      * NOTE: If you had previously initialized the framework, you need to use the flag --reset with the init command to change the configuration.
    * what is the local registry?
      * stores packages being developed (dev), or fetched from the remote registry (third_party) to be used locally
      * you initialize local registry with: "autonomy packages init" - This will create an empty local registry in the ./packages folder
    * why use an Agent Service over using 1 single aea? ^WQ6xosaj8
      * me: depends on use-case, but might as well just make as service with single service operator
      * their site:
        * Having understood how agent services fit into the wider crypto ecosystem, sometimes there is the question whether is it best to design a certain application as single-agent or as an agent service. This is often a question that new developers in the field of agent systems and multi-agent systems face. We provide below a comparison table which hopefully will give you some guidance on which of the both approaches is best for your use case.
        * ![[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/Attachments/imgs/app/ShmojiMindMapPublic/pVo-imw7RJ.png]]
        * ## Progressive decentralization
          * Of course, many use cases that apply for single-agent application can later be considered to be offered as an agent service. For this reason, it is often advisable to implement a single-agent application as an agent service with a single service operator. This approach has the benefit that whenever the developer wants to make the promotion of that application to an agent service, they will be able to do so almost effortlessly, except for some modifications to account for potentially extra configuration requirements.
    * how is fetchAI related to Olas? (i ask bc i kept seeing fetchAI in their tut videos)
  * concepts, terms
    * their solution is comprised of 2 frameworks: ^vj3jE6Ny9
      * Open Autonomy framework
        * concerned with generating service that is composed of multiple agents
      * Open AEA framework
        * define the components and structure of each of indvidual agents
    * FSM app
      * inside each agent is FSM app - it is a skill that defines the business logic of Agent Service
      * Each agent of a Agent Service has same FSM app, but it is setup with different parameters is my understanding
      * States
        * have 2 components for dealign with responsibilities
          * Rounds
            * handle the result of the consensus layer and decide how the FSM should behave
          * Behaviors
            * execute proactive actions in each state
      * Transitions
    * Consensus Gadget
      * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/autonolas, olas#^aZeZ_kozn|each agent is connected to a consensus gadget node]]
      * [[tendermint]]
  * general key points
    * most your time will be spent developing the Skills for an agent
  * products, features, tech
    * [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/autonolas, olas#^vj3jE6Ny9|their solution is comprised of 2 frameworks:]]
    * agents
      * you run these
    * mechs
      * agents that execute tasks for other agents
      * they provide services
    * notes on WALLETS
      * contains the private-public key pairs used by the AEA. Skills do not have access to the wallet, only Decision Maker does
      * Each AEA has 2 sets of private keys, configured in the aea-config.yaml
        * 1: private keys which identify the ledger specific keys
        * private keys used in the connections
      * keys are only used by a single AEA. Using same key across different AEAs will lead to various failure modes
    * IDENTITY
      * an abstraction that represents the identity of an AEA
      * it contains the AEAs addresses AND its name
      * the identity can be accessed in a Skill via the AgentContext
    * components (apparently also called FSM app)
      * can be used by all and is whole other economy
      * 2 types of components
        * core components
          * common across all agents
          * there are specific components, but here is general way to membuh:
            * handle message passing, structure and actual running of the code (main loop)
            * multiplexor - agent loop - decision maker - envelopes
        * extension components
          * components that dev creates to tailor agent to their own needs. Custom code developed by anyone. protocols - skills - connections - contracts
      * the specific components
        * envelope (core component)
          * simply wrappers for messages
          * used to communicate between different components in an agent, BUT also used to communicate between different agents
          * messages in an envelope must adhere to a protocol
        * protocol (extension component)
          * defines rules for communication between agents or between components
          * often library comes with many predefined protocols and you dont need to create your own. For example, HTTP, Ledger, Contract are protocols. But if you need custom protocol, there is a protocol guide and even a protocol generator to help
        * connections (extension component)
          * these continuously run
          * one connection per protocol (typically)
          * wraps an SDK or API and provides an interface to networks, ledgers, or other services
          * responsible for translating between the external message format and internal message format for the agent
          * connections are managed by the multiplexer
        * multiplexer (core component)
          * processes incoming and outgoing messages across several connections asynchronously
          * manages connections of the agent
          * maintains an InBox and OutBox, which are queues for incoming and outgoing Envelopes from the perspective of Skills
        * skills (extension component)
          * most important component
          * represent the agent knowledge. Self-contained capabilities
          * implement the business logic to deliver economic value for the AEA
          * AEAs can dynamically take Skills on board in order to expand their effectiveness in different situations
          * skills have implementations of the 3 abstract base classes:
            * 1: Handler: implement reactive actions to external events
            * 2: Behavior: proactive logic initiated from the AEA
              * me: Behaviors execute actions initiated by internals of the AEA rather than external events
              * the act() method implements core functionality of the Behavior
              * the various Behavior types (abstract base classes) define how often and in what order a behavior and its sub-behaviors must be executed
            * 3: Model: custom objects which are accessible via the skill context
              * Model represents an abstraction for some data object related to the business logic of the app
              * all model objects inherit from the Mode abstract base class and are accessible via the SkillContext
              * Seems can be useful when wanting to synchronize data across multiple agents
          * SkillContext: The SkillContext object provides access to persistent state and config options, as well as access/link to the AgentContext object
            * is local to the skill. But is accessible to all the skill's Handlers, Behaviors, and models
            * The AgentContext provides access to AEA sepcific info like the public key and address of the AEA. Also provides access to the OutBox. This means it is possible to at any point grab the context and have access to the objects in other parts of the Skill
          * Tasks: encapsulate bg work internal to the AEA
            * is not part of a Skill, but Tasks are declared in or from Skill if a packaging approach for AEA creation is used
        * contracts (extension component)
          * wrap smart contracts around the API or ABI of a contract and its byte code
          * implement a translation between framework messages and the implementation specifics of the ABI
          * contracts need to implement 4 types of methods:
            * 1: a method to create a smart contract deployment tx
            * 2: methods to create tx to modify state in the deployed contract
            * 3: methods to create contract calls to execute static methods on the deployed contract
            * 4: methods to query the state of the deployed contract
        * Decision Maker (core component)
          * wallet manager + economic brain of the AEA
          * is responsible for the AEAs crypto economic security and goal management
          * it is only component with access to the Wallet's private keys
          * in simplest form, the Decision Maker acts like a wallet with Handler to react to messages it receives from the Skills
        * Agent Loop (core component)
          * orchestrates the life cycle of the agent
          * executes all this continuously:
            * calls the act() function of all registered Behaviors at their respective tick rate (remember Behaviors are part of the Skills)
            * grabs all Envelopes waiting in the InBox queue of the Multiplexer and calls the handle() function for the Handlers currently registered against the protocol of the Envelope
            * dispatches the internal Messages from the decision maker to the handler in the relevant Skill
    * services
      * key points
        * they can be completely decentralized
        * they can be offchain, onchain, or both
      * Agent services
        * composed of multiple agents, controlled by diff operators
        * each agent is connected to a consensus gadget node ^aZeZ_kozn
          * Consensus gadget = consensus gadget nodes + consensus gadget network
          * CG used to get consensus between all agents of service
          * CG can run on same server as agent or elsewhere - whatever operator wants

  * examples
    * good example of entire process of an agent
      * 11:20 of this: https://drive.google.com/file/d/12LExuXnt61hQ1W6kOFFHzvVLRri8Xv-s/view
      * The framework first calls the setup methods in the skill's Handler and Behaviour classes in that order; after which it repeatedly calls the act method of Behaviour class. This is the main agent loop in action.
  * related
    * [[tracking learning olas, aea, autonolas]]
