# Blockthread Data Structure

A blockchain is formed when all consecutive blocks from a block that has reached finality, all the way back to the genesis block, unite to form a linear chain that is generally referred to as the blockchain. To keep the network running until then, the miner is responsible for maintaining all potentially viable chains, which are referred to as forks. Detailed explanation of the method by which forks spontaneously develop as a result of alpha node rotation may be found in the section on fork creation. A miner's ability to cope with forks until blocks are completed is facilitated by the use of the blockthread data structure described here.

Every shred a miner observes on the network, in any order, must be signed by the expected alpha node for that specific slot in order for the miner to record it. This is performed using the blockthread, which is used to ensure that every shred is recorded.

Fork-able key space relocation is accomplished by relocating shreds to an alpha node slot + shred index tuple. The tuple of alpha node slot + shred index represents the fork-able key space relocation (within the slot). The skip-list structure of the HyperCube protocol can be stored in its whole as a result of this, eliminating the need to determine which fork to follow, which Entries to persist, or when to persist them.

Blockthread's store implements this concept by serving current shred repair requests from RAM or recent files, whereas less recent shred repair requests are serviced from deeper storage, as demonstrated by the store that supports blockthread.

## Functionalities of Blockthread

### Persistence

Located in the foreground of the nodes verification process, immediately following network receive and signature verification is the blockthread. Immediately after receiving a shred, if it is consistent with the alpha node schedule (i.e., if it was signed by the alpha node for the indicated slot), it is stored.

### Repair

Repair is the same as described above for windows, but it is capable of serving any shred that has been received. blockthread stores shreds that have been signed, allowing the origination chain to be preserved.

### Forks

Due to the fact that blockthread allows for random access to shreds, it can accommodate a miner's requirement to rollback and replay from a transaction processor checkpoint.

### Restart

The blockthread can be replayed by ordering the enumeration of items from slot 0. This can be accomplished with suitable pruning/culling. Because of this, the logic of the replay stage (which includes dealing with forks) will have to be applied to the most recent entries in the blockthread to ensure that they are correctly identified.