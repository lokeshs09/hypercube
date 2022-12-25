## Why design a proof of PoD dedication

Blockchain was originally built for cryptocurrency, but we found that as the use of blockchain becomes more and more widespread, the scope of applications is also more and more extensive, it should be used to provide digital services in many business areas, including accounting And currency issuance. Its idea is: the idea of ​​a computer platform that serves people all over the world. Only by creating a global infrastructure that serves all levels of development can blockchain technology be used in our daily lives.

However, in order to achieve the goal of having a global computing platform, there are two challenges to overcome:
(1) Must include Turing completeness. Therefore, the program can only perform certain tasks if it has proper logical integrity.
(2) Super Ability It was basically the same thing before, but now it’s complicated, listening to music, playing games, and arranging things. If you want to accomplish more work, you must be able to accomplish several things at the same time.

The initial problem that Ethereum wants to solve is a breakthrough. After making Ethereum more humane for developers, the project realized Turing completeness and "smart contracts" before using the virtual machine EVM, providing project members with opportunities to interact with Ethereum more easily. Understand the specific needs of your business, complete the blockchain + deployment of your project, and use the underlying data. The bottom layer is the source of the anti-tampering function of the project.

The PoW (Proof of Work) consensus method used by Ethereum can only complete basic calculation work and storage capacity. With the rapid development of modern blockchains, innovations in practical applications of NFT and DeFi continue to emerge. The challenges faced by all new public blockchains are about performance: how to get better?

TPS is the core indicator that considers the underlying standards of the blockchain. TPS means how many pieces of data can be processed at the same time per second. At present, there are 24,000 Visa transactions, 100,000 stock transactions, and 250,000 Taobao transactions per second in the world. Shopping transactions, and at the same time, the cost and handling fee of each transaction relative to individual users can be ignored. As we face the blockchain world, the TPS of Ethereum is around 20, and the TPS of Bitcoin is 7. Therefore, in contrast, the expansion of the blockchain has become very important. The purpose of expansion is not only to increase the transaction speed, but also to increase the single transaction fee. Pave the way for scale applications.

The proof of POD dedication proposed by the HyperCube team is to build a new generation of consensus protocol for the expansion of the blockchain from the protocol level.


## Why do we need to expand the capacity of Ethereum?

HyperCube chooses Ethereum as the object of expansion, and defines PoD as a 2-layer solution that helps Ethereum improve processing speed and storage capacity.

This choice is because we realize that in addition to the improvement and expansion of the underlying technology, the success or failure of the blockchain system lies in the vast number of developers and the flourishing ecology. Ethereum is now the world's largest DAPP operating platform. , Has a wide range of and loyal developers and users. Therefore, the essence of commercial competition is traffic competition. We hope that POD can provide the most developers and the most blockchain users with a better experience.

### POD dedication to prove how to improve computing power

As the infrastructure for DAPP development, the public chain only provides a fast and reliable foundation for DAPP. This will only provide a basis for creating killer applications. When comparing blockchain to the Internet, the first issue to discuss is its relative speed: its outstanding performance in processing data.

Blockchain technology must verify data upload. In short, in order to ensure the accuracy of the upload, the data must pass through all network nodes for parallel calculation, and then return to the network for data collection and verification. The latter process is definitely slower than centralized processing. Therefore, many people think that blockchain is a technology that sacrifices efficiency for security.

POD dedication proves that a balance between performance and decentralization is found. By combining sharding and staking, the definition of Value Of Dedication is proposed. Through the size of the dedication value, every In each block creation cycle, define who will verify and choose which data to write to the chain.

### What is the difference between POD dedication certificate and POW and POS

PoW is the English abbreviation of the method used for proof of work. Under this algorithm, each network node in the network performs calculations at the same time, and the first person to obtain the correct answer will gain the ability to perform the next set of calculations. Therefore, a lot of meaningless waste will be generated. PoS depends on the age of the coin and the number of coins owned, as well as some randomness to select those with longer coin age and more coins, and they are ultimately responsible for the information that joins the blockchain.

In the PoW consensus algorithm network, all network nodes participate in the calculation at the same time, and the person who calculates the result the fastest gets the accounting power. This process is essentially a calculation competition and zero-zero game. Machines with insufficient computing power consume electricity and time. , There will be no meaningful returns, and a lot of power resources are wasted.

The PoS is based on the age of the currency and the number of coins, plus some randomness, selects people with a longer coin age and a larger number of coins to obtain the verification power, and is ultimately responsible for putting the verified data on the chain. But so far, it is difficult for PoS to solve the problem of over-issued currency and the kidnapping of the community by large nodes.

POD proves consensus through dedication, and through reasonable selection of high-speed nodes for accounting, while taking into account performance, it also guarantees the high-speed performance of the network. This is like making a decision to choose a qualified president during a national election. If all the people of the whole country need to vote at the last minute, it will inevitably be slower to wait until the people of the whole country vote. However, adopting a similar proxy system and selecting a group of "reliable" people to choose the right president on behalf of the public can greatly improve the efficiency of the election.

## D-Value

The POD consensus mechanism describes an indicator for users of the entire network: D-Value. The quantitative consensus on dedication value is the consensus on the dynamic definition of multi-dimensional network proposed by HyperCube. D-Value is established based on the DAG transaction data model and social graph model of the directed acyclic graph. D-Value is used to quantify the contribution of nodes to the network, including computing power, time, storage and Multi-dimensional data such as community input.

Often the simplest and simplest ideas require the most complex and rigorous engineering methods to achieve. In the real society, everyone's social status depends on the value of his dedication to others. If a person has enough dedication to the family, he enjoys a high reputation in the family, and if he has dedication to the society, he has a lofty reputation in the society. Reputation. Contribution is the manifestation of an individual’s value to others and the collective in the social organization structure. The more dedication, the more personal feedback will often be, thus forming a positive cycle. The value of dedication includes the superposition of multiple factors such as group, labor, and creation. This invisible value determines the right to speak for individuals in the world. But it is the hidden value, so it is difficult to quantify it with models. Therefore, in HyperCube, we have realized the quantitative expression of the dedication system for the first time, using mathematical consensus to more accurately describe the existence value of a single individual in the entire organizational structure.

The emergence of POD is just like the emergence of POW. Using computer language to express the existence of individuals in social organizations, POW solves the credit value of labor, and POD takes it to a higher level. It not only expresses labor, but also expresses trust. , The credit value of existence and exchange.


## Determine the consensus node through D-Value

POD uses Byzantine fault tolerance, which analyzes possible nodes and their results before assigning nodes. In the first stage, all nodes will be evaluated and the 15% with the highest contribution will be randomly selected. This can be considered the "best" node in the network. In contrast, the maximum number of nodes allowed in the node pool is 1000 and the minimum is 100. In order to ensure that the transaction passes Byzantine Fault Tolerance (PFDT), you need to randomly select nodes in the "node candidate pool". After that, a selected node checks the transaction of the network and puts the confirmed transaction on the chain.

By using a collective decision-making process, the strategy aims to combat election bribery and provides a "choice of good nodes" procedure that will verify a limited range of data while being efficient and decentralized.


### Various factors that determine D-Value

D-Value is determined according to the HyperCube network dynamic equilibrium formula, and it will keep changing at every moment. The nodes participating in the formula must want to obtain a high D-Value, and must strengthen the node configuration in the following aspects

**Holding currency**

All HyperCube nodes must be pledged to start using XPZ tokens. The more the number of tokens pledged by the node, the longer the pledge time, and the larger the D-Value will be.

**The internet**

In the HyperCube network, there will be backbone nodes and verification nodes. After being filtered by D-Value, a backbone node will be formed, and all nodes will communicate and exchange data with the backbone node. In this process, the smoother the communication, the higher the D-Value.

At the same time, if the node goes offline, D-Value will be greatly reduced


**hardware**

HyperCube will determine the contribution value of the node to the network based on the CPU core, GPU core, hard disk space, RAM space and other multi-dimensional factors.


**Community**

HyperCube supports the entire SPS ecosystem, and users with SPS tokens can get a higher D-Value. Considering the number of users who have strong social connections with each other on HyperCube, how often they interact with friends, their dedication to each other, and the volume of transactions between them, it can be determined that this node will be very advantageous in the competition of the bookkeeping node , Will get higher rewards. If you are a high-profile project party on HyperCube, a key opinion alphanode (KOL) who often interacts with fans, or a community alphanode with excellent operational capabilities, then D-Value rewards may be very beneficial to your account balance.


