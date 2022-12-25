# Fork Management

Natural fork will generate naturally as a consequnce of alpha node rotation.

## Overview

Nodes take turns being alphanode and generating the PoH that encodes state changes. The cluster can tolerate loss of connection to any alphanode by synthesizing what the alphanode would have generated had it been connected but not ingesting any state changes. The possible number of forks is thereby limited to a "there/not-there" skip list of forks that may arise on alphanode rotation slot boundaries. At any given slot, only a single alphanode's transactions will be accepted.

## Msg Flow

The current alpha node gets the transactions.
The alpha node checks for authentic transactions.
Transactions run properly and update the alpha node's state.
Alpha node assigns entries to current PoD slots.
Miner nodes get the entries from the alpha node (in signed shreds)
Tick streams have the empty entries that signal if the PoD stream is a alpha node and how long time has passed.
A alpha node stream begins with the tick entries that are required to return PoD (PoD that had previously been in the slot of the most recently seen previous alpha node) to the most recently found alpha node slot.
Miners repackage their entries and send them to the peers in their group, who in turn transmit them to nodes farther down the chain.
Transactions are validated and carried out by miners on their state.
Miners perform a hash operation on the state.
Miners send votes to the alpha node in defined windows, which are defined by PoD ticks.
Votes are just marks in the code that prove how the project is being run.
Some voters' decisions are influenced by "what everyone is saying."
The alpha node acts as if it is another transaction: it executes and broadcasts any of the votes cast.
A miner can observe all the votes that they cast and every vote from their shard.


## Partition Forks

Fork splits may be triggered in the code, by an impending vote. The future alphanode may begin their term by inserting fabricated records into the blockchain, without knowing that the slot prior to their own already had a poll. All the nodes in the cluster generate empty ticks at a set rate of hashes/per/tick Z.

During a voting slot, the POD can only exist in two possible forms: with T ticks and entries created by the current alphanode, or only ticks. The version "Just Ticks" of the POD can be regarded as a virtual directory that all cluster nodes can draw from the last tick in the preceding slot.

Miners have the option of ignoring forked transactions that occurred as a result of receiving false information, and they can also punish whoever provided the false information.

Miners use the greedy strategy mentioned in POD BFT to select an option that provides the greatest financial benefit for themselves.

 