### Introduction
Uniswap, Compound, and YFI, as the star projects in 2020, detonated the Defi market in the cryptocurrency world, but there has always been a problem of high user operation thresholds and limited assets on the chain. YFarm Protocol is a decentralized Defi aggregation mining protocol that aims to introduce incremental users and incremental assets. Based on community governance and decentralization, it can allow users to mine with zero fees and introduce the real world. China's assets and credits are used to allocate mining capital leverage to solve the user's pain point of "high mining threshold and insufficient mining funds", so that users can fully enjoy the Defi world dividend.

YFarm Protocol has the following unique advantages:

##### Zero mining fees: 
using intelligent aggregate mining algorithms, saving users hundreds of dollars in gas fees and giving 100% subsidies to the fees, thus greatly reducing the threshold for users to reach the Defi world.
##### Introduce real-world assets and credit to realize leveraged mining: 
Combining the Synthetix synthetic asset on-chain framework and the original trust collaboration mechanism, complete on-chain synthetic asset authority management and trust chain marking through smart contracts, so that those with only a small amount of digital assets or even zero digital assets Users can also introduce real-world assets and credits to allocate funds to amplify Defi mining leverage, play a "small investment, large income" leverage, realize the interest rate arbitrage of assets on and off the chain, and expand the value of Defi's underlying assets.

##### Ease of use and scalability: 
YFarm Protocol will become the entry-level application platform for users to enter Defi through an extensible protocol framework design and friendly user interaction experience and function integration.

The development route of YFarm Protocol is: 

First, by lowering the threshold for using DeFi mining, lowering the fee aggregation and providing 100% subsidies, so as to allow more people in the blockchain industry to participate in the actual operation of DeFi. The mining rights are promoted from technicians to people in the industry. 

Second, through the synthetic asset chain and credit coordination mechanism, the system security is improved and the excellent interaction design allows financial demanders outside the industry, such as borrowers and lenders from traditional fields, Begin to pay attention to and use decentralized financial products, that is, to achieve promotion from within the industry to outside the industry; 

Third, create an open technology framework agreement and DAO community governance mechanism, so that Y Farm Protocol can become a Defi infrastructure and common component.

### Functions
##### Aggregate mining with zero transaction fees
Based on the realization of YFI, this function realizes the aggregation mining model based on intelligent algorithms, realizes the dual goal optimization of improving the efficiency of capital use and aggregation and reducing the operation fee, and gives users 100% token subsidy of the deposit and withdrawal fees, thereby Greatly reduce the barriers to entry for users.

##### Leveraged mining
The Defi world currently can only use the digital currency and assets on the chain for mining and trading, making the risk-free benefits of Defi mining far higher than the real world advantage cannot be fully utilized. Defi mining miners are limited by the limited numbers in their hands. Assets cannot fully enjoy the Defi bonus. In the real world, funds and assets pursue low risk and a return rate relative to legal currency, making it difficult to accept Defi's liquidity mining token standard incentive model. To achieve this, we provide a leveraged mining allocation model in YFarm Pool, which divides miners into leverage user A and leverage provider B. The former amplifies the leverage of digital asset mining to obtain excess returns, and the latter obtains stable income based on fiat currency and priority protection of funds.
 For example, in the face of a mining pool where APY is 100% income, A can use 10,000 USDT and leverage it to 50,000 USDT to participate in mining, and provide B branch with 40,000 USDT leveraged funds with a standard APY of 30% leverage interest. YFarm Pool controls the flow of mining funds through the smart contract module group, and the return funds are given priority to pay B's principal and interest. In this case, assuming that the mining APY remains unchanged, A's ROE will increase to 380%, and B will obtain a stable income relative to fiat currency.

##### Synthetic asset and credit synergy method
In the above-mentioned YFarm Pool allocation model, leverage users can use leverage to achieve excess returns, and the interest rate and ratio of leverage will be realized by market-based mechanisms and smart contracts. In order to further introduce assets and trust in the real world, YFarm Protocol adopts a synthetic asset mechanism and an asset chain model similar to Synthetix. Leverage users can mortgage real assets to the chain and realize price connection through oracles. Real assets off the chain It will help leverage users to bring lower interest rates and higher ratios of leverage providers to increase credit and disadvantages. At the same time, YFarm will also use the blockchain address credit synergy relationship based on real world credit, and introduce the credit system into the digital world on the chain through multi-party secure calculations, so as to provide leveraged users with credit enhancement and better leverage. And set up a credit coordination insurance pool to reduce the capital risk of leverage providers.


### Methodology
In the first phase of the project, relying on Ethererum's mature smart contract technology, all funds and behaviors of YFarm users are completed by smart contracts on the Ethereum chain. In view of the fact that Ethererum's increasing transaction fees have imposed a greater burden on users, the second phase of the project will add additional public chain support without transaction fees, such as TRON using the DPos mechanism. According to the logic flow, the YFarm system is composed of five modules: Pool, Vault, Controller, Strategy, and Farm, and their interaction is shown in Figure 1.

<div align="center">
  <a href="https://www.yFarm.finance"> <img width="850px" height="auto" 
  src="yFarm-logic.png"></a>
   <p> Figure 1: Figure of the relationship between YFarm modules </p>
</div>


The direction of the arrow in Figure 1 represents the direction of the flow of user funds for mining, and the direction of the flow of funds for the user to obtain income is opposite to the arrow in the figure. Below we introduce the logic function of each module in turn. It is worth noting that all modules are smart contracts on Ethereum, and the flow of funds is function calls between contracts.

The YFarm system is divided into two modules at the logical level, namely the Funding module for user deposits and allocations; and the intelligent mining and Farming module. The former relies on the latter to run, while the latter is a fully functional sub-module that can operate independently as an independent non-user funded liquidity mining system.

For the Funding module, its purpose is to meet the different needs of two groups of people. The two groups are represented by the leverage user UserA and the leverage provider UserB. For UserA, it is pursuing high-risk and high-yield, such as APY above 100%, but lacks sufficient principal; for UserB, it has sufficient principal, but it is pursuing relatively high stable returns, such as APY 30 %. Specifically, the functions of the Funding module are implemented by a series of smart contract Pools. Each Pool is an independent fund pool and includes the following functions:

##### a. Fund allocation: 
For each smart contract pool, it specifies the type of funds to be accepted, such as ETH, the minimum return for UserB, such as APY 30%, and the leverage ratio, such as 300%. Under this value setting, UserA can be funded by Pool in a ratio of 1:3. If UserA obtains more than 100% of APY through liquidity mining through funding, that is, borrowing money from UserB, then UserA needs to distribute 30% of the funding part to UserB. For each pool, UserA will issue a funding requirement, and UserB can store funds in the pool according to demand. Of course, UserB can also store funds in the pool if there is not enough demand for subsequent priority use.

##### b. Liquidation: 
In addition to the settlement of income in the above fund allocation process, Pool also needs to maintain operations such as liquidation and liquidation caused by changes in asset value. UserA transfers to the Vaunt contract through the allocation of funds (see below for the introduction of Vaunt). In Vaunt, users may need to convert their assets. For example, the currency with the highest rate of return in Vaunt is YFI, and Pool's funds are ETH, then UserA can first convert ETH to YFI through a one-step conversion and store it in Vaunt. The relative price changes of ETH and YFI will affect UserB's principal security. Pool judges by introducing an oracle of over-the-counter prices, and periodically judges whether to trigger a liquidation operation to protect UserB's fund safety.

For the Farming module, in general, the intelligent and reducible relationship can be summarized as the fund pool Vault collects funds through the controller Controller and uses different strategies to invest funds in different liquid mining scenarios Farm to earn income. The entrance and exit of its funds is the Vaunt smart contract, which is a series of different assets for intelligent automatic mining, such as an aggregated fund pool of ETH and YFI, which pools funds and settles the proceeds after the end of mining. Overall. As the core feature of the YFarm system, Vault additionally maintains the user's invitation relationship when users make investments (for example, users can set an address as their own inviter), and then distribute a certain percentage or amount of invitation dividends when the income is settled .

When the user's funds are pooled to a threshold, Vaunt will invest the funds into the specific liquid mining mining scenario Farm, which is managed by the controller. Specifically, the Controller first holds the user's funds, and it has a trusted mining strategy Strategy pool. After a period of time, the Controller will use intelligent algorithms and oracle models to select the highest yield in the current market Strategic investment. For example, suppose that the most profitable way to mine YFI liquidity in the market is to invest in Compound DeFi. After updating the node, the Controller will choose to invest YFI in Compound's Strategy to manage YFI investment. From the above statement, we can see that Strategy mainly completes two functions:
a. Specify the mining link of a certain asset.
b. Contracts for liquid mining scenarios, that is, the docking function of the Farm contract.

Finally, we introduce the liquidity mining scenario contract Farm. At present, people are already familiar with liquid mining scenarios such as compound and balancer loans or decentralized transactions. Naturally, Farm includes support for this liquid mining scenario, that is, as a kind of Farm contract, it has a corresponding Strategy Docking and oracle monitoring. For YFarm, its innovative combination of asset chaining process supports liquidity mining of physical assets. Specifically, YFarm uses a mechanism similar to Synthetix to synthesize assets, but unlike Synthetix, users can choose appropriate credit for mortgage when publishing assets. For example, suppose that users seek to publish N residential assets and the number of tokens is M. The credit here can be a digital contract with legal effect, which stipulates that when the user saves M/N tokens, it can be exchanged for a house. Then, using this as collateral (the specific implementation method is to place this digital contract in a synthetic asset contract), users can release assets without the need for token collateral, and then conduct liquidity transaction mining.

### Governance
After initial testing and code design, YFarm Protocol will be promoted online. After the initial developer committee promotes the product and the community cold start, the governance of YFarm will completely enter the DAO stage. This agreement is subject to YFX constraints, and any improvements will be decided by voting by YFX holders. Some of the powers that can be controlled by the governance system are listed below:

Set up a new mining pool and choose a suitable mining protocol

Update the oracle address and the interest rate and ratio of leveraged funds

Change the proportion and method of the back-end revenue

Set up a new DAO community


### Token Distribution
Token distribution will be completely decentralized, with no private placement and no pre-mining, and community governance will benefit the community. Tokens will be automatically distributed based on smart contracts, a total of 1 million tokens will be distributed in 3 stages:

The first stage: light up the plan. Early supporters in the community adopted the snapshot mode to record the total assets supported by the lighting plan initiated by the agreement and distribute YFX Early Bird earnings.

The second stage: liquidity mining. In this stage, a liquid mining mechanism similar to YFI will be adopted, and multiple mining pools and machine gun pools will be set up to provide excess YFX revenue for the early Farmer.

The third stage: mining with leveraged funds. In this stage, a mining allocation model will be introduced, and a smart contract component for capital risk control will be implanted in YFarm Pool, and the allocation ratio and interest rate will be determined based on the synthetic asset chain and credit coordination mechanism, and provide leverage for leverage providers and leverage users Provide YFX rewards.


