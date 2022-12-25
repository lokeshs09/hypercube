# Terminology

## Current Supply Cap 

The total number of tokens (locked or unlocked) generated (via genesis block or protocol inflation) less any tokens burned (via transaction fees or other mechanism) or slashed.

210,000,000 XPZ were instantiated in the genesis block at network launch. The Current Supply Cap is subjecto to reduction since then as a result of the burning of transaction fees and a planned token reduction event.

## Inflation Index 

The HyperCube protocol will generate new tokens based on a predetermined inflation schedule (discussed below). The annualized growth rate of the Current Supply Cap at any point in time is represented by the Inflation Index [ % ].

## Supply Time Table 

A time-dependent deterministic description of token issuance. A dis-inflationary inflation schedule is proposed by the HyperCube Protocol. In other words, inflation begins at its highest level and gradually decreases until it reaches a predetermined long-term inflation rate (see discussion below). Three numbers completely and uniquely parameterize this schedule:

- Initial Inflation Index [%]: The starting Inflation Rate for when inflation is first enabled. Token issuance rate can only decrease from this point.

- Deflation Index [%]: The rate at which the Inflation Rate is reduced.

- Long-term Inflation Index [%]: The stable, long-term Inflation Rate to be expected.

## Viable Inflation Index 

After accounting for other factors that could reduce the Current Supply Cap, the inflation index observed on the HyperCube network. It should be noted that tokens cannot be created outside of the parameters specified in the **Supply Time Table**.

- While the **Supply Time Table** governs how the protocol distributes XPZ, it ignores the concurrent elimination of tokens in the ecosystem due to a variety of factors. The burning of a portion of each transaction fee is the primary token burning mechanism. Half of each transaction fee is burned, with the remaining fee kept by the miner who processes the transaction.

- Other factors, such as the loss of private keys and slashing events, should be considered in a comprehensive analysis of the Viable Inflation Index. For example, it is estimated that 10% of all BTC has been lost and is unrecoverable, and that networks may experience similar yearly losses of 1-2%.


## Staking Yield [%] 

The rate of return (aka interest) earned on XPZ staked on the network. It is often quoted as an annualized rate (e.g. "the network staking yield is currently %10% per year").

The rate of return (also known as interest) on XPZ staked on the network. It is frequently expressed as an annualized rate (e.g. "the network staking yield is currently percent 10 percent per year").

- miners and token holders who want to delegate their tokens to avoid token dilution due to inflation are particularly interested in staking yield (the extent of which is discussed below).

- 100% of inflationary issuances will be distributed to staked token holders in proportion to their staked XPZ, as well as miners who will charge a commission on the rewards earned by their delegated XPZ.

    - With the introduction of Evernet Keeper into the economy, there may be future consideration for an additional split of inflation issuance.

    - Evernet Keepers are network participants who provide a decentralized storage service and should be rewarded with token distributions from inflation issuances in exchange for this service.

    - Similarly, early concepts called for a fixed percentage of inflationary issuance to be delivered to the Foundation treasury for operational expenses and future grants.

    - Inflation, on the other hand, will begin without any funds allocated to the Foundation.

- The Supply Time Table, along with the fraction of the Current Supply Cap staked at any given time, can be used to calculate staking yield. The following expresses the explicit relationship:

![Formula1](https://i.imgur.com/GxVGSA9.png)




## Token Dilution [%]

Dilution is defined as a change in the proportional representation of a set of tokens within a larger set as a result of the introduction of new tokens. 

In practice, we talk about the dilution of staked or un-staked tokens as a result of the introduction and distribution of inflation issuance across the network. While dilution affects all token holders, the relative dilution between staked and un-staked tokens should be of primary concern to un-staked token holders, as shown below. Staking tokens, which will receive their proportional distribution of inflation issuance, should alleviate staked token holders' concerns about dilution. 

In other words, the dilution caused by 'inflation' is offset by the distribution of new tokens to staked token holders, effectively canceling out the 'dilutive' effects of the inflation for that group.

## Adjusted Staking Yield [%]

A complete assessment of the earning potential of staking tokens should consider staked Token Dilution and its impact on the Staking Yield. We define the Adjusted Staking Yield as the change in fractional token supply ownership of staked tokens as a result of inflation issuance distribution. In other words, the positive dilutive effects of inflation.