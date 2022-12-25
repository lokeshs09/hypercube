## ATHENA SDK

The ATHENA SDK is a software development kit that allows developers to create blockchains that are tailored to particular applications. It incorporates common functionality across blockchains and establishes standards that may be anticipated across different blockchains, including common patterns, among other things. This is shown via the MsgSend message type, which is used to transmit fungible tokens of specified amounts between two parties using the bank module, as seen in the following example: Other examples include account querier, which is a component of the Auth Module that provides information on a user's account independent of whatever chain the user is a member of.

The NFT Module presented here is intended to be used as a cross-chain module for managing non-fungible tokens, which represent separate assets with distinct characteristics and are not intended to be fungible.

On Ethereum, this standard was originally created as part of the ERC-721 (XRC77 on HyperCube) and the following EIP of the same name, both of which were released in 2014. This standard made use of the capabilities of the Ethereum blockchain as well as the limitations of the network.

The ERC-1155 (XRC155 on HyperCube) standard addressed some of the limitations of Ethereum, such as the high cost of storage and the lack of liquidity of semi-fungible assets.

Unlike their Ethereum counterparts, NFTs on HyperCube blockchain have some, but not all, of the same characteristics as their Ethereum counterparts. 

Because HyperCube blockchains are more flexible in how their resources are used, it seems logical that they should be able to take advantage of those resources if they so want. This includes the ability to utilize strings as IDs as well as the ability to optionally store information on the blockchain. 

Composability with smart contracts should also be rethought in terms of user-flow on HyperCube blockchain, particularly with respect to Inter-Blockchain Communication, since this is a very distinct design experience from communication between smart contracts.

***
