  * how TOs
    * how to find contract code?
      * 1: if OS, should find code on GH from creators
      * 2: if creator verified contract, then can see code on blockchain explorer. Additional notes: [[ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/ShmojiMindMapPublic-2025-05-24-12-15-07_cleaned/smart contracts, abis#^SLdc-I4kX|is it possible to take a public ethereum smart contract address and find the code with just the starting point of that address?]]
    * How to call contract methods as quick as possible
      * 1)
        * https://eth95.dev/
        * Allows you to test smart contract methods and SEE ANY contract method, unlike etherscan. Although i think etherscan will give you ABI needed maybe?
        * Press "Add  Contract" -> paste ABI in. PAste contract address into Feild at top leftish. Select method you want and args and submit.
      * 2)
        * npx hardhat console -and then you can just use javascript in command line like in a deploy script in order to call contract method (i guess should be at root of project directory tho, idk)
    * how to deploy smart contracts
      * checkout Solidity folder in evernote
  * questions
    * Who pays for TX/contract method (minting/etc) that is called by a contract itself?
      * Gas is always paid by the original sender (**tx.origin** in Solidity), not by any **intermediate **contracts. The gas used in a transaction is always subtracted from the balance of the sending account. So, tx.origin = sending account = EOA
      * The gas fee for any smart contract interaction is paid by the [[EOA (Externally Owned Account)]] that calls it. Even if the smart contract makes **another **transaction (as an **internal **transaction), it's considered to be part of the **original **transaction called by the EOA, so the EOA will have to pay the gas for the **entire **transaction.
    * is it possible to take a public ethereum smart contract address and find the code with just the starting point of that address? ^SLdc-I4kX
      * Yes, ONLY IF CREATOR VERIFIED the contracts on a blockchain explorer like Etherscan
      * another note: there's kind of another option that may or may not work:
        * Unverified Contracts: If the contract hasn't been verified, you won't be able to see the source code, only the bytecode.
        * Decompiling: Decompiling the bytecode to get the source code is possible but challenging and won't give you the original code.
          * Another way to find the code is to use a tool like Remix IDE, which can decompile the bytecode and provide a representation of the code in Solidity[1](https://forum.openzeppelin.com/t/can-you-get-the-code-of-an-unverified-smart-contract/32247). However, this method is not always reliable, and the resulting code may not be the exact code used to create the contract.
        * Another approach is to search for the contract's bytecode on a search engine or blockchain explorer and look for similar contracts with verified source code
