  * When contract return UINT, this number is returned to frontend as a BigInt
  * When you see web3BNToFloatString and pow, these are used to convert a BigInt to a regular int. I think a better way may be to do this: https://ethereumdev.io/how-to-deal-with-big-numbers-in-javascript/
  * Web3 returns primitive data types (including uint) as strings. If you try to parse it into javascript native number with something like parseInt, it will fail.
  * To work with the big numbers received via web3, you have to use library which can handle them. One such library is BigNumber.JS
  * What i learned
    * new BN(1) is not same as new BN(new BigNumber(1).multipliedBy(new BigNumber('10').exponentiatedBy(18)))
    * use BigNumber.js when using **fractions** and any MATH. Do not use BN for arithmetic since it can't do fractions. Only use BN for sending to smart contracts as BN
    * When converting regular number to decimal, it's confusing. GREAT example of how to do this is at top of useStakingAPR.ts, those constant values