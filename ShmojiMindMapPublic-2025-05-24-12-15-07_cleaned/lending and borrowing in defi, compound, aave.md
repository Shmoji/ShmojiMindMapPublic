  * old evernote notes
    * **Risks**
      * Quickly changing APYs (mainly just a borrower issue). For example, during last yield farming craze, the borrow APY of BAT token went up to over 40%. This could cause unaware users who are not tracking interest rates daily, to get liquidated by having to pay more than expected in same period of time
    * **Why would anyone borrow funds**
      * In defi in 2021, basically ALL loans are over-collateralized. This means that user that wants to borrow funds has to supply tokens (as collateral) that is worth more than the actual loan they want. But WHY? Why not just sell tokens instead? Here's the reasons: 1) user doesn't want to sell tokens, but needs funds to cover unexpected expenses 2) avoiding/delaying paying capital gain taxes on tokens 3) using borrowed funds to increase leverage in certain position
      * Of course, there are multiple more complicated reasons such as borrowing stable coins to buy even more ETH (leverage) or borrowing other coins to use them for yield farming.
      * **Good example #1**:
      * Imagine you invested your money into ETH and you believe it will go up to $1000 per coin. A tough month comes and you have some unexpected expenses that you have to cover and you already run out of USD (assuming this is your currency).
      * Now, instead of selling your ETH, paying capital tax gain on it and risking that ETH price will go up after you sold it, you can take a loan in USD-based stable coin with ETH as your collateral. Now you can pay your expenses by withdrawing borrowed stable coins. In the next few months you received your salary and you can use some of it to pay of the USD-based stable coin loan. During that whole time you had a full exposure to the initial amount of ETH.
    * **Is there a limit on how much can be borrowed?**
      * Yes. Depends on 2 main factors
      * 1) how much funds are available to be borrowed on particular market. Not typically an issue on active markets unless someone is trying to borrow BIG amount
      * 2) what is the collateral factor of supply tokens? **Collateral factor** determines how much can be borrowed based on the QUALITY of the collateral. DAI and ETH for example, have CF of 75% on Compound. This means up to 75% of the **value **(what is value?) of the supplied DAI/ETH can be used to borrow other tokens
      * If user decides to borrow funds, the value of the borrowed amount must always stay lower than the value of their collateral * CF. If this condition holds, there is NO LIMIT on HOW LONG this user can borrow funds for.
      * However, if value of collateral falls below the required collateral level, they would have their collateral liquidated in order for the protocol to repay the borrowed amount
    * **How is interest received calculated for borrowers and lenders?**
      * it is determined by the **ratio **of **supplied **and **borrowed **tokens in a particular market.
      * interest paid by borrowers is the interest earned by lenders, so the borrow APY is higher than supply APY (why?)
    * **Differences in Defi Protocols**
      * Compound offers variable supply/borrow APY. Aave offers stable borrow APY. It is stabled in short term, but not long term. On top of stable APY, aave also offers flash loans where users can borrow funds with **no upfront collateral** for very short period of time (1 ETH tx)