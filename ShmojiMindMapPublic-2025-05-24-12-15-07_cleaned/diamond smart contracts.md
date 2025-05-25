  * what it be?
    * not me: A Diamond is a smart contract that uses other smart contracts (aka Facets) to make delegatecall calls. So, what exactly is a Facet and delegatecall?

In essence, a delegate call is a special form of an external function call in which a proxy contract uses code from another smart contract in its own context (i.e., its own state variables). Facets, which allow you to divide your implementation logic into multiple Solidity files and update them as required, make up the second critical aspect of a Diamond contract.
  * how does it work?
    * not me: A diamond is a smart contract. The only address external software uses to communicate with it is its Ethereum address.
Facets, a collection of contracts, are utilized by the Diamond to handle its external functions.
The storage of state variable data is housed in the Diamond rather than in its facets.
The external functions of facets can directly read and write data stored in a diamond. This makes facets easy to write and gas efficient.
The Diamond operates via a fallback function that leverages delegatecall to route external function calls to its facets.
To manage its data, a Diamond frequently leverages facets for its external functions rather than relying on any external operations of its own.