# HyperPool

A HyperPool is a group of miners who collaborate to serve client transactions while maintaining the ledger's integrity. Several pools may coexist. When two pools share a genesis block, they make an attempt to converge. Otherwise, they simply ignore the other's existence. Transactions sent to the incorrect address are quietly rejected. In this section, we'll go over how to create a pool, how nodes join the pool, how they share the ledger, how they ensure the ledger is replicated, and how they deal with buggy and malicious nodes.

## Constructing a HyperPool

Before starting any miners, a genesis config must be created. The configuration makes use of two public keys, a mint and a bootstrap miner. The miner in possession of the bootstrap miner's private key is in charge of appending the first entries to the ledger. It loads the mint's account into its internal state. That account will contain the number of native tokens specified in the genesis configuration. After that, the second miner contacts the bootstrap miner to register as a miner. Additional miners can then register with any registered pool member.

A miner receives all entries from the alphanode and votes to confirm the validity of those entries. The miner is expected to save the votes after they have been cast. When the miner notices that there are a sufficient number of copies, it deletes its copy.

## Becoming a member of a HyperPool

Miners join the pool by sending registration messages to the pool's control plane. The control plane is implemented using a gossip protocol, which means that a node can register with any existing node and expect its registration to be broadcast to all nodes in the pool. The time it takes for all nodes in the pool to synchronize is proportional to the square of the number of nodes in the pool. That is considered very slow algorithmically, but in exchange for that time, a node is assured that it will eventually have all of the same information as every other node, and that that information cannot be censored by any single node.

## Transacting with a HyperPool

Clients send transactions to the Transaction Processing Unit (TPU) port of any miner. If the node is acting as a miner, it sends the transaction to the designated alphanode. If the node is in the alphanode role, it bundles incoming transactions, timestamps them, creates an entry, and pushes them onto the data plane of the pool. Once on the data plane, miner nodes validate the transactions, effectively appending them to the ledger.

## Transaction Confirmation

A HyperCube pool can confirm transactions in subseconds for up to 150 nodes, with plans to scale up to hundreds of thousands of nodes. Once fully implemented, confirmation times are expected to increase only in proportion to the logarithm of the number of miners, where the base of the logarithm is very large. If the base is one thousand, for example, it means that confirmation will take three network hops plus the time it takes the slowest miner in a supermajority to vote for the first thousand nodes. Confirmation increases by one network hop for the next million nodes.

According to HyperCube, confirmation is the period of time between when the alphanode timestamps a new entry and when it recognizes a supermajority of ledger votes.

Once a gossip network reaches a certain size, it becomes far too slow to achieve subsecond confirmation. The time it takes to send messages to all nodes is proportional to the number of nodes multiplied by the square of the number of nodes. If a blockchain wants to achieve low confirmation and uses a gossip network, it will be forced to centralize to a small number of nodes.

Scalable confirmation can be achieved by combining the following techniques:

- Sign the timestamp and timestamp transactions with a VDF sample.

- Divide the transactions into batches, send each to a different node, and have

- Each node distributes its batch to its peers.

- Repetition the previous step until all nodes have all batches.

HyperCube rotates alphanodes at predetermined intervals known as slots. Each alphanode may only submit entries during the time allotted to them. As a result, the alphanode timestamps transactions so that miners can look up the designated alphanode's public key. The alphanode then signs the timestamp so that a miner can verify it, proving that the signer is the owner of the designated alphanode's public key.

Following that, transactions are divided into batches so that a node can send transactions to multiple parties without having to duplicate them. If the alphanode needed to send 60 transactions to six nodes, it would divide the collection into batches of ten transactions and send one to each node. This enables the alphanode to send 60 transactions over the wire rather than 60 transactions for each node. Each node then distributes its batch to its peers. Once all six batches have been collected, the node reconstructs the original set of 60 transactions.

A batch of transactions can only be split so many times before the header information consumes the majority of network bandwidth. At the time of writing, the approach has scaled up to about 150 miners. To scale to hundreds of thousands of miners, each node can apply the same technique as the alphanode node to another set of equal-sized nodes. Turbine Block Propogation is the name we give to this technique.