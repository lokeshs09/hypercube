# Supply Time Table

As previously stated, the network's Supply Time Table is uniquely described by three parameters: Initial Inflation Index, Deflation Index, and Long-term Inflation Index. Many factors must be considered when analyzing these figures:

A large portion of the XPZ issued through inflation will be distributed to XPZ miners in proportion to the XPZ staked. We want to make sure that the Supply Time Table design results in reasonable Staking Yields for token holders who delegate XPZ and validation service providers (via commissions taken from Staking Yields).

The primary determinant of Staked Yield is the amount of XPZ staked divided by the total amount of XPZ ( percent of total XPZ). As a result, when determining initial inflation parameters, it is critical to understand the distribution and delegation of tokens across miners.

Yield throttling is a current area of research that could have an impact on staking-yields. This is not taken into account in the discussion or modeling below.
Overall token issuance - i.e., what do we expect the Current Total Supply to be in 10 years or 20 years?
Long-term, steady-state inflation is an important consideration not only for long-term support for the miner ecosystem and the Solana Foundation grant programs, but it should also be tuned in consideration of expected token losses and burning over time.
The rate at which we expect network usage to grow in relation to the disinflationary rate. We expect inflation to fall over time and usage to rise.
Based on these considerations and the community discussions that followed the initial design, the Solana Foundation proposes the following Inflation Schedule parameters:

- Initial Inflation Index: 8%
- Deflation Index: 15%
- Long-term Inflation Index: 0.8 percent

These parameters define the proposed Inflation Schedule. The consequences of these parameters are shown below. These plots only show the impact of inflation issuances given the Inflation Schedule as parameterized above. They do not take into account other factors that may have an impact on Total Supply, such as fee/rent burning, slashing, or other unforeseen future token destruction events. As a result, what is presented here is an upper limit on the amount of XPZ issued through inflation.

![Figure1](https://i.imgur.com/iAEIzbo.png)

In the above graph we see the annual inflation rate [\%%] over time, given the inflation parameters proposed above.

![Figure2](https://i.imgur.com/pawB0p8.png)

Similarly, we can see the Circulating Supply Cap of XPZ [MM] over time, assuming an initial Circulating Supply Cap of 488,587,349 XPZ (i.e. for this example, taking the Circulating Supply Cap as of 2020-01-25 and simulating inflation starting from that day).

When miner uptime and commissions are taken into account, the expected Staking Yield and Adjusted Staking Yield metrics are essentially a function of the percent of total XPZ staked on the network. As a result, if we add an additional parameter percent of Staked XPZ, we can model Staking Yield:

![Formula2](https://i.imgur.com/XyFPDz8.png)


Where Sr stands for the precentage of the staked XPZ in the total supply.

Because it is a dynamic characteristic of token holders and staking incentives, this parameter must be calculated. Based on comments from the investor and miner communities, as well as what is observed on analogous Proof-of-Stake protocols, the percent of Staked XPZ shown here ranges from 60% to 90%, which we believe represents the likely range we expect to see.

![Formula2](https://i.imgur.com/zgq9l8s.png)

Again, with the Supply Time Tables supplied, the following displays an example Staked Yield that a staker can expect over time on the HyperCube network. This is a skewed Staked Yield since it ignores the influence of miner downtime on rewards, miner commissions, potential yield throttling, and potential slashing occurrences. It also ignores the fact that the percent of Staked XPZ is dynamic by design - the economic incentives established by this Supply Time Table are more clearly seen when Token Dilution is included (see the Adjusted Staking Yield section below).