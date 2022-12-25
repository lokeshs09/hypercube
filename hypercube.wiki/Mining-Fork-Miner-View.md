# Miner Fork


## Progression 

The diagram below represents a Miner's view of the PoD stream with possible forks over time. L1, L2, etc. are alpha node slots, and Es represent entries from that alpha node during that its slot. The TXs represent ticks only, and time flows downwards in the diagram.

![f1]

Note that an E appearing on 2 forks at the same slot is a slashable condition, so a miner observing E3 and E3' can slash L3 and safely choose x for that slot. Once a miner commits to a fork, other forks can be discarded below that tick count. For any slot, miners need only consider a single "has entries" chain or a "ticks only" chain to be proposed by a alphanode. But multiple virtual entries may overlap as they link back to the a previous slot.


## Time Division 

We can better keep the cluster encoding by distributing work with the usage of rotating alphanodes. The next table contains the previously described ledger, which is spread over time.

| Leader Slot      | L1 | L2 | L3 | L4 | L5 |
|------------------|----|----|----|----|----|
| Data             | E1 | E2 | E3 | E4 | E5 |
| Ticks Since Prev |    |    |    | x  | xx |

Data is accepted exclusively from L3, the top alphanode, during L3's portion. If L3's data doesn't include L2's information, it may "catch up" and tick back to a slot that's different from L2. Ticks known as "ticks to previous" are found in L4 and L5 transmissions.

This configuration has data streams that can save crucial information on the ledger to enable auditing, in case of a breakdown.























[f1]:https://i.imgur.com/0fVg8FX.png

