# Alpha Node Rotation


## Overview

A hyperpool expects only one miner to produce ledger entries at any given time. Because only one alpha node is active at a time, all miners can replay identical copies of the ledger. The disadvantage of only running one alpha node at a time is that a malicious alpha node can censor votes and transactions. Because censoring cannot be distinguished from network packet loss, the hyperpool cannot simply elect a single node to serve as the alpha node indefinitely. Instead, the hyperpool reduces the impact of a malicious alpha node by alternating which node takes the lead.

Each miner employs the same algorithm, which is described below, to select the expected alpha node. When the miner receives a new signed ledger entry, it can be confident that it was generated by the anticipated alpha node. A alpha node schedule is the order in which each alpha node is assigned a slot.

## Rotation Mechnism

Blocks that are not signed by the slot alpha node are rejected by a miner. A slot alpha node schedule (alpha node schedule) is a list of all the IDs of the slot alpha nodes. Locally and every now and then, the alpha node scheduling is recomputed. Epochs last for a time that gives the assignment of alpha nodes for slot variables. In order to do their jobs properly, the work being done on the ledger must be completely finished before it can be scheduled to start. Alpha node schedule offset is the name of that duration. Solana establishes the time difference for slot durations until the next epoch. The alpha node schedule for an epoch is defined at the start of the preceding epoch, based on the ledger state. The amount of time between each epoch is assumed to be long enough for all miners to be finished before the next schedule is created. To help minimize the time between stake changes and alpha node schedule updates, a hyperpool may decide to reduce the offset.

There is no need to build a schedule unless the root fork passes the epoch limit. The root fork is planned for the next epoch, therefore the new roots won't be in use until then. The first block of epoch 0 that the node schedule crosses belongs to epoch 0.

Without a partition lasting longer than an epoch, the hyperpool will work as follows:

- A miner continuously updates its own root fork as it votes.
- The miner updates its alpha node schedule each time the slot height crosses an epoch boundary.

For example:

To make things simpler, assume an epoch length of 100 slots, even if it's in reality much larger. The root fork is moved to a new slot at a height of 102, which is from a slot height of 99. Due to errors, slots at height 100 and 101 were skipped. The slot height 102 bifurcation is the starting point for the new alpha node schedule. Until it is updated again, it is active from slot 200.

If a miner on the hyperpool votes for a different candidate than the majority of miners, then their current candidate's vote on issue 101 will be rendered meaningless. Every miner would have to commit to a root, either 102 or its descendent.

## Alpha Node Schedule Rotation with Epoch Sized Partitions

The alpha node schedule is vulnerable to error when the alpha node schedule has an inconsistent view of the actual alpha node schedule because of the duration of the alpha node schedule offset.

Picture this:

A couple of dividers with each one making half of the blocks. There will be no clear big bifurcation in either of them. Both of these will jump into the first two hundred generations without committing to the root or changing the new alpha node timetable for the hyperpool.

In this uncertain situation, several feasible plans for alpha nodes exist.

- A alpha node schedule is generated for every fork whose direct parent is in the previous epoch.
The alpha node schedule is valid after the start of the next epoch for descendant forks until it is updated.

- Each partition's schedule will diverge after the partition lasts more than an epoch. For this reason, the epoch duration should be selected to be much much larger then slot time and the expected length for a fork to be committed to root.

To find a suitable alpha node scheduling offset, the hyperpool should be watched for a long period, and then the interval should be based on the median partition duration and its standard deviation. For instance, for instance, a tolerance which is more than 6 standard deviations above the average length of a partition means that in a hyperpool the risk of a corrupt ledger schedule is 1 in 1 million.

## Alpha Node Schedule Generation at Genesis

The configuration file sets the first epoch's first node as its beginning. Because the alpha node schedule is likewise generated at slot 0 for the next epoch, the alpha node is planned for the first two epochs. You can specify the duration of the first two epochs in the genesis config. POD BFT defines the maximum rollback depth; the earliest epochs should have a minimum length that exceeds or equals that maximum.

## alpha node Schedule Generation Algorithm

In order to make scheduling of Alpha Node seed easy, a predetermined seed is used. Here is the process:

- The PoD tick height (a monotonically growing counter) can be used to seed a pseudo-random process, and can be used at regular intervals.

- It is recommended that each proxy node run a few network transaction consistency checks before moving onto the next task. For instance, the node can make sure to scan the network to discover all staked identities. The term "active set" describes the sample.

- Sort the people with the greatest impact on the problem into the critical set.

- Use the random seed to select nodes weighted by stake to create a stake-weighted ordering.

- This ordering becomes valid after a hyperpool-configured number of ticks.

## Schedule Attack Vectors

### Seed

Seed selection is not biased or predictable. No grinding attack to affect the outcome exists.

### Active Set

By suppressing miner votes, an alpha node can skew the active set. Alpha nodes can censor the active set in two ways:

- Ignore votes from miners

- Refuse to vote for blocks with votes from miners

The active set is calculated at the alpha node schedule offset border over an active set sampling length to minimise the possibility of censorship. The active set sampling duration is long enough that many alpha nodes will have collected votes.

### Staking

Alpha Nodes have the ability to censor new staking transactions or refuse to validate blocks containing new stakes. This attack is comparable to miner vote censorship.

### miner operational key loss

Alpha Nodes and miners are supposed to operate using ephemeral keys, and stake owners permit miners to execute work with their stake through delegation.

The hyperpool should be able to recover from the loss of all ephemeral keys used by alpha nodes and miners, which could happen as a result of a common software flaw shared by all nodes. Even though the stake is currently assigned to a miner, stake owners should be able to vote directly by co-signing a miner vote.




## Appending Entries

An epoch is the duration of an alpha node schedule. The epoch is divided into slots, each with a duration of T POD ticks.

During its slot, an alpha node sends entries. All miners switch to the next planned alpha node after T ticks. Miners must disregard entries received outside of an alpha node's allotted slot.

The following alpha node must witness all T ticks in order to create its own entries. If no entries are noticed (the alpha node is down), or if the entries are invalid (the alpha node is buggy or malicious), the following alpha node must supply ticks to fill the prior alpha node's slot. It should be noted that the next alpha node should do repair requests in parallel and delay delivering ticks until it is satisfied that other miners did not observe the previous alpha node's contents. If an alpha node builds wrongly on its own ticks, the alpha node that follows it must replace all of its ticks.