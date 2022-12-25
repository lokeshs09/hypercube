# XRexx

We have recently released the first version of the XRexx programming language and on-chain programming environment, which offers a completely new and much improved method to developing smart transactions on the Ethereum blockchain. This article will provide an overview of the latest developments and how they are superior to previous models.

Up to this point, the two broad approaches to smart transaction environments that have emerged from Bitcoin and Ethereum have been referred to as ‘the UTXO model' and ‘the Solidity model,' respectively. As long as servers keep track of the current set of unspent coins (and their birthdates, which is a minor addition), transactions are only allowed to spend some coins and create others and are not allowed to rely on any external data, the only way for them to go from good to bad is for one of the inputs to be spent (or to be reorged into never existing or having a different birthdate, again a minor gotcha). While the Solidity model includes a large amount of on-chain information, including running applications, the consequences of a transaction cannot always be predicted before the transaction is executed. The UTXO method is much simpler, easier to implement, has reduced overhead on full nodes, and results in smart transactions that are significantly more reliable, secure, and succinct. The Solidity model is much more hazardous, costly, and unreliable than the other models, but it has significantly more expressive potential.

Our solution for Solidity (and the surrounding CLVM) is to retain the UTXO paradigm while also incorporating the broad capability of the Solidity programming language. This is accomplished via a series of straightforward cleanups that, although individually insignificant, build up to something very powerful:

Bitcoin is a first-class object in which coins are represented as a transaction id and an output number, while transactions in Ethereum are ephemeral justifications for destroying some coins and creating others. In contrast, transactions in Bitcoin are first-class objects in which coins (UTXOs) are represented as a transaction id and an output number.

A significant reduction in the complexity of the coin format (UTXOs). It consists only of the main input, the puzzle hash, and the amount.

Transactions take place in real time rather than in a sequential fashion.

Using BLS, which is a non-interactively aggregatable format, signatures are created, and aggregation is performed at every stage.

There are no negative consequences from the words used. In comparison to the existing taproot concept for Bitcoin, this enables delegation and partial delegation in a far more broad and powerful manner.

The return value of all puzzle (scriptpubkey in Bitcoin parlance) solutions (scriptsigs) expresses the needs of the solutions (scriptsigs).

The language has achieved the turing completion. Considering that execution is temporary, this adds much less complexity than most people believe. Solidity's complexity is caused by the complicated persistent state that exists in the system.

Because the language has the required primitives for calculating coin ids, and because coins are capable of asserting their own ids, it eliminates the need for quines and enables explicit self-reference.

Apart from language and environment extensions, there are several programmatic techniques that allow for much more functionality than you would expect:

It is possible to construct covenants by stating assertions about the puzzle hashes of outputs that are applicable recursively. This could theoretically be accomplished using Bitcoin Script, but it lacks adequate string mangling skills and the ability to do a ‘check signature from stack,' which was the motivation for utilizing Bitcoin Script in this instance.

A capability may be achieved by employing backwards pointing covenants, which refer to ancestors rather than descendants in order to achieve the desired result.

Coins may interact with one another via the use of ephemeral coins, which are spent in the same transaction in which they are generated and are declared as inputs by the currency that is receiving the communication.

When a reveal is obtained in a solution, state may be stored in inaccessible portions of the code, which can then be retrieved by asserting the coin id, which is computed based on the puzzle hash, which is calculated in the puzzle.

These methods, when combined, allow for the creation of arbitrarily complicated functionality without the need for any additional opcodes. New functionality may be created and deployed in a matter of minutes.

As an example of what may be done with this technology, we are making accessible a number of reference smart transactions and the wallets that utilize them, including the following:

A wallet that can only transfer money to those who have been authorized to receive them.

A wallet that can only spend money at a predetermined pace, as well as the ability to make payments to it non-interactively, is described as follows: If the wallet software is capable of creating several funds-holding coins and spending from all of them at the same time, this seems to be required in order to do this.

It is similar to a paper wallet in that it contains deposit recovery information, but it has a reduced attack surface. It can be used to recover funds from a wallet whose secure hardware has failed; however, unlike a traditional paper wallet, instead of immediately gaining control of the coins, the deposit recovery information can be used to initiate a process for gaining control that takes some time, during which the hardware wallet (if it is still online) can claw the funds back from the deposit recovery information. Furthermore, it may support the need of a deposit to begin the healing process, which the person who has been assaulted has the ability to "take."

As well as this, we've created implementations of certain fundamental Bitcoin functionality that already exists but is important:

Multisig. We're beginning with the most basic method, which is the same as it is in Bitcoin, and will be implementing the more advanced ways, which make excellent use of signature aggregation, in the next months.

Swaps at the atomic level. We have a smart wallet that does the exchange and deals with all of the edge situations on the blockchain.

Further reference smart transactions will be developed in the future, and the XRexx feature will be implemented on our testnet before being rolled out to our mainnet. Prior to the final launch of the mainnet, there will be incompatible modifications, but the core principles will remain unchanged. In the coming months, we will be adding some interesting new reference transactions to this list, including light client verifiable colored coins that inherit full XRexx capability, as well as distributed identity wallets with advanced recovery capabilities.
