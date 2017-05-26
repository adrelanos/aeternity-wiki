# What is mining?

Volunteers can run the æternity mining software on computers, servers or mobile devices to order and validate transactions. Miners are compensated with the issuance of AEON tokens, the native cryptocurrency asset of the æternity network. Aeon can be used as payment for any resources one consumes on the æternity platform, as well as the basis for financial applications implemented on the platform.

Unlike Bitcoin, Ethereum and most other cryptocurrencies, æternity uses a hybrid Proof-of-Work ("PoW") and Proof-of-Stake ("PoS") consensus mechanism. The PoW algorithm used is called the Cuckoo Cycle.

# How can you earn Aeons (AE) by securing the network and setting up a node?

The consensus on the æternity blockchain is achieved through hybrid Proof-of-Work (PoW) and Proof-of-Stake (PoS) algorithm. The Proof-of-work will be done by miners via the "Cuckoo Cycle" algorithm. Proof-of-Stake is implemented via on-chain prediction markets, which project the information available to the network to one single number between 0 and 1. This number is used to signal to the miners which version of the blockchain to mine on.

# Mining & Node types:

The æternity blockchain will feature multiple types of nodes that each fulfill a certain task on the network. Use cases are diverse, and the best ones are still to be imagined.

* Some nodes will be providing liquidity to the State channels Lightning Network. These nodes will maintain multiple connection channels with other nodes. Creating a channel with them will enable any node to establish state channel contracts with many others. This will involve a fee paid to the node.

* Some nodes will run as trust-less exchanges with multiple assets. These nodes collect transaction fees from their users. State channels can be used through these nodes to play games using Aeon (AE). Whether single player, with friends or total strangers, æternity will enable trust-less financial applications where no user puts his trust into the other, but into the fair logic of the blockchain. These financial applications do not necessarily need to be decentralized. They can exist on a “centralized server” and through the æternity blockchain become trust-less financial tools.

* Some nodes will be running as exchanges to invest in stocks, futures, bonds and precious metal, or can be used for gamblers in a trust-less and efficient way. 

* Some nodes can specialize in maintaining the blockchain, and preserve it from bloat, by recycling old accounts. There will be a fee for maintaining an open account. When an account runs out of Aeons, these nodes will be able to delete it and get a reward.

* Some nodes will just run the trading software, merely buying and selling any offered assets.

# Proof-Of-Stake Mining (Oracle):

Source: [(White Paper)](http://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf)

Any Aeon holder can launch an oracle by committing to answering a yes/no question on the blockchain.
When doing so, they also need to specify the time-frame during which the question can be answered, which can start now or at any point in the future. The user that launches the oracle is also required to deposit AEON in proportion to the length of the time-frame, which will be returned if the user supplies an answer that gets accepted as truth, otherwise, it is burned. The blockchain generates a unique identifier for the oracle that can be used to retrieve the answer once it is available. Once the time comes for the question to be answered, the user who launched the oracle can supply an answer for free. Once the oracle launcher has supplied an answer the other users have a set amount of time to submit counter-claims by depositing the same amount of AEON. If no counter-claims have been submitted by the end of the time-frame, the answer supplied by the user that launched the oracle is accepted as truth, and the deposit is returned. If any counter claims are submitted, then the consensus mechanism for blocks will be used to answer the oracle. This is more expensive, but since we know we can take at least one of the two safety deposits, we can use it.

While hardware requirements for creating a PoS miner will not be particularly high, it is important to have a **Fixed IP address**, as is the case with all other PoS cryptocurrencies.

# Proof-Of-Work Mining - which kind of hardware is best?

The "Cuckoo Cycle" PoW is more power efficient and indirectly useful, as it encourages the development of better random access memory (DRAM) chips. Even low-power devices such as smartphones, tablets, and laptops can efficiently mine new tokens. This will achieve an unparalleled decentralisation and geographical distribution of the mining power, which will be crucial to the success of any Blockchain.

As such, æternity mining is designed to be more egalitarian and inclusive compared to crypto-currencies where mining is dominated by large mining entities which use application-specific integrated circuit ("ASIC") chips designed specifically to take advantage of a particular PoW algorithm. This wider distribution of the mining incentives will then contribute to even wider use and adoption of æternity.

As noted by John Tromp in his paper, "Cuckoo Cycle: a memory bound graph-theoretic proof-of-work":
>”[Cuckoo Cycle is] an instantly verifiable memory bound PoW that unique in being dominated by latency rather than computation. In that sense, mining Cuckoo Cycle is a form of ASIC mining where DRAM chips serve the application of randomly reading and writing billions of bits. When even phones charging overnight can mine without orders of magnitude loss in efficiency, not with a mindset of profitability but of playing the lottery, the mining hardware landscape will see vast expansion, benefiting adoption as well as decentralization.”

***
related: [Terminal interface commands](Terminal-interface-commands#mining)