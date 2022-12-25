# XRC Standard

XRC is an acronym for XPZ Request for Comments and is defined as XPZ Request for Comments. XRCs are blockchain-based application standards, such tokens, tokens, name registries, and package formats, which can contain many things. The author of an XRC must properly document their standard and must educate and empower the community to use their standard.
To ensure smooth and uniform integration of tokens, which interact with various applications and smart contracts, into systems, a standard set of functionalities for a token type must be included.
To date, the most popular standard has been the XRC20, which enables it easy to create, use, and trade Ethereum-based tokens.
XRC20 defines a protocol that helps to create tokens and programs in the XPZ virtual machine (XVM). It's completely ERC-20 compliant.

***

## XRC20 Standard 

HyperCube operates on a coin set concept (which is comparable to Bitcoin's UTXO mechanism) as follows: The only thing that remains constant is the current set of unspent coins, which are distinguished by their sizes and the rules that govern how they may be spent. When a coin is spent, the value of the coin may be used to create new coins, but the value of the original coin is lost forever. All permanent data must be stored in the form of coins. This is significantly better for scalability since the data that full nodes have to keep track of is simpler and smaller than the objects that the EVM needs to store, and therefore far more efficient. Validating a block requires the completion of all of its transactions, with the only output being a list of coins that have been spent and destroyed. Because of this, we are able to achieve an effective transaction rate that is higher than Ethereum's while still being able to operate a complete node on a typical desktop computer. At first glance, it seems that the flattening of data types will make it much more difficult to create smart coins in HyperCube, however the flattening of data types has many significant advantages. Everyone and everything communicates and cooperates with one another, and bits of functionality may be reused and layered on top of one another.

One of the most important tools for doing business in HyperCube is the use of XRC20 currencies. A tokenization of some kind is represented by an XRC20 coin, which has coin sizes with melt values that are very tiny yet represent something else at a high ratio. (An XRC20 coin has a preset divisibility of one billion by default. The fact that a HyperCube is a trillion Mojo (which is the smallest indivisible unit, equivalent to a Satoshi in Bitcoin) means that there is space for such an operation. On the surface, this seems to be the same as the Omni protocol (a coloration format for Bitcoin), however the coloration of coins may be verified in a very simple and straightforward way. In fact, it is so lightweight that even smart coins may perform this function, as opposed to the Omni protocol, which needs operating a complete node in order to determine whether XRC20 coins are genuine. This is accomplished while maintaining the potential of XRC20 coins to perform at least as well as non-XRC20 coins in terms of intelligence. It is also possible to have one XRC20 currency incorporated in another XRC20 coin.

One of the additional pieces of functionality that our XRC20 currency implementation makes possible is the ability to make 'offers' to other users. Suppose you wish to exchange some HyperCube for some of an XRC20 currency. You might create an incomplete transaction in which some HyperCube is burned and some of the XRC20 coin is printed. The transaction itself will be void, but you may take your offer and submit it to an exchange, or send an email copy of it to a friend, or post it on Reddit. It will be possible for whoever receives it to accept the offer by creating their own partial transaction, which prints a counterbalancing amount of HyperCube and burns a counterbalancing amount of XRC20 coin, and combining it with yours to form a valid transaction that will be recorded on the blockchain. Considering that in HyperCube everything in a block occurs concurrently, the money are effectively transferred in a single step from one input to the other output, and there is never a point at which there are too many coins in the system. In reality, it is feasible for a third party to handle the bookkeeping of numerous offers involving a number of different assets, and as long as the totals line up, everything will go through as planned.



***


## XRC77 Standard

The following standard enables the creation of a standardized API for non-fungible tokens within smart contracts. This standard defines the fundamental functionality required to track and transfer NFTs.
We examined both private ownership and transaction of NFTs as well as consignment to third-party brokers/wallets/auctioneers ("operators"). Non-financial tokens (NFTs) can be used to represent ownership of digital or physical assets. We evaluated a wide variety of assets, and we're sure you'll think of many more:

- Physical property – residences, one-of-a-kind artwork

- Virtual collectibles – one-of-a-kind cat images, collectible cards

- Assets with a "negative value" — loans, obligations, and other responsibilities

By and large, each house is unique, and no two kittens are same. NFTs are distinct from one another, and you must track their ownership separately.



***

## XRC155

### Standard Mass Transfers

The XRC55 standard enables the native transfer of large amounts of tokens from a smart contract to another smart contract. Using this method, we may transfer many NFT tokens or fungible tokens (or both) in a single operation, allowing us to complete the transfer in a single action. This is particularly useful if we have a series of NFT tokens or fungible tokens (or both).
It is feasible to save money on transaction fees, reduce the effect on the network, and make it much easier to implement a trading system (escrow/atomic swap) utilizing the tokens in question.

### Multiple Token Contracts

An XRC55 may also explain the presence and functioning of several tokens at the same time, in addition to the above features. It may thus generate and describe one or more fungible tokens (such as the XRC55) while simultaneously describing one or more non-fungible tokens (such as the XRC77) inside the same contract, therefore simplifying the deployment and programming of the tokens.

### Integrated Token Type Detection

Another feature of the XRC55 token is the possibility to incorporate the functionality of the XRC165 token (also known as the Standard Detection Interface) into the same system as the XRC55 token. Thus, the XRC55 token is able to detect the interface of a token and modify its behavior in response to that interface's detection. This is particularly helpful owing to the fact that the XRC55 is a multitoken coin, and thus simplifies the design of applications.

### Secure Token Transfer

The safe token transfer function of the XRC55 token is maybe one of the most promising aspects of the token. In order to do this, the XRC55 standard smart contract contains a function that checks that the transaction has been completed and, if it has not, reverts the transaction to allow the tokens to be returned to their issuer.
This is particularly helpful when we make a mistake in the transcription or copying of addresses and instead send our tokens to the incorrect address, rendering our transaction ineffective. In such scenario, the transfer is considered invalid, and the issuer recovers the tokens, enabling it to check the address once again and repeat the transaction if necessary. For the purpose of avoiding assaults from double spending, a number of rules have been defined that prohibit this behavior, keeping it secure against these kinds of attacks and other traps in general.

***

