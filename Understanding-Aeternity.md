# What is æternity?

æternity is a new type of blockchain that innovates and expands upon existing platforms such as Bitcoin, Ethereum, and Augur. 
Real-world data can interface, through decentralized Oracles, with smart contracts.
True scalability and trust-less Turing complete state channels are setting æternity apart from Ethereum.

![æternity platform-vision](http://i67.tinypic.com/2ewm694.png)

æternity is unique in many ways, but the key features are:

- Hybrid PoW/PoS;
- Oracle Machine;
- State Channels, or "Off-chain transactions" will allow for both faster transaction time as well as improving anonymity when sending and receiving transactions;
- Governance;
- Address naming system;

# What is the purpose of æternity?


æternity seeks to present a highly scalable blockchain architecture with a consensus mechanism which is also used to check the oracle. Thus the oracle will get efficient and layering one consensus mechanism on top of another will be avoided. State channels are integrated to increase the privacy and scalability. Tokens in channels can be transferred using purely functional smart contracts that can access oracle answers. By not storing contract code or state on-chain, we are able to make smart contracts easier to analyze and faster to process, with no substantial loss in de facto functionality.


# What is blockchain?

In short, a blockchain is a secure ledger distributed among participants computers and in this case, governed only by the æternity software. More generally, a blockchain is essentially a distributed database that contains a constantly growing chronological list of unchangeable records called "blocks". Each block in the chain consists of bundled transaction data that is cryptographically hashed. In order to prevent tampering of the recorded data in the chain, each block is timestamped and links to the previous block in the chain. Typically each node, or computer connected to the blockchain network, is charged with creating and validating new blocks using various consensus algorithms. Once new blocks are validated, they are appended to the chain. In this way, blockchains serve as the complete record of all transactions on the network from the genesis block to the most recently completed block.

# What is special about æternity and how does it compare to other blockchains?
(Focus on Oracles, practicality, flexibility, the AE court, state channels)

æternity is built for scalable smart contracts that can interface with real-world data through oracles. 
Other smart contract platforms are experimenting with 3rd party oracle machines added on top of the consensus. 
The Oracle is part of the consensus in æternity and can deliver deterministic values (from legacy systems or other blockchains) for smart contract interaction. Thus offering real-world data to be instantly implemented in æternity smart contracts, in return enabling countless business use cases.

![æternity-tech stack](http://i64.tinypic.com/219uskn.png)

# What is an Oracle?

Oracle is a mechanism to teach the blockchain true facts about our world. This is a virtual machine that crowdsources real-time answers to specific questions using principles of [Prediction Markets](https://github.com/aeternity/testnet/wiki/Research-and-Theory#prediction-markets) and can also be used to negotiate fundamental changes on how the system functions, allowing for high adaptability to market demands and other developments. Good examples include weather conditions, currency valuation and any other information accessible to the public.

[More details](https://github.com/aeternity/testnet/wiki/Research-and-Theory#decentralized-oracles)

# What are State Channels?

The State Channel design enables off-chain verification of data and smart contracts. If the verification in the channel fails, the blockchain is asked to resolve. This in return permits a high transactional throughput and parallel processing of smart contracts. Hence, the programmability of complex relationships for large numbers of users and handling high volumes of products and information in parallel is æternity's strong suit.
Only the parties participating in a smart contract know about the contents of that smart contract.
When a channel is settled on-chain, the only way it changes the blockchain state is by changing account balances.
No contracting state is stored on-chain, so all channels are independent of each other. Transaction speed is limited only by bandwidth, so the æternity system can scale as well as known centralized solutions available today.

--Taken from [here](https://github.com/aeternity/testnet/wiki/Research-and-Theory#state-channels)
 
For more information refer to [State Channel](http://www.jeffcoleman.ca/state-channels/)

# How does æternity work?
* [Governance & æternity](https://github.com/aeternity/testnet/wiki/Research-and-Theory#governance--consensus)

(High-level, also describe the proof system, state channels):



# What are AE Tokens and how are they used and consumed?

The æternity tokens will be used to pay for resources consumed through the platform, as well as "gas" used to power applications built on top of it.

All æternity tokens will be distributed via the genesis block through an ERC20 Ethereum Smart contract, and at a later stage by mining.

# How can æternity be used?

Toll API: Payment channels allow for a new kind of API, where one
pays for every call to the API, possibly every HTTP-request.
Paying to access an API solves DDoS problems, and it makes
it easier to build high-quality APIs that are always available.

Stable value assets: Smart contracts and oracles can be used in combination to program synthetic assets that stay
nearly the same price as a real world asset.

Event contracts: Event contracts pay when an event
happens and don’t pay when an event does not happen, as
per the oracle’s telling. Event contracts can be used as the basis for many other types of useful applications such as encouraging whistleblowing and supporting prediction markets.

Micropayments: æternity's state channels will allow for off-chain, peer-to-peer payments that will open up many revenue generation possibilities for content creators and publishers. While micropayments are currently possible on other blockchains, tx/min and block size limitations prevent many current blockchains from being able to handle micropayments at scale.  

P2P Bandwidth Sales: State channel supported payments could allow for compensation-based sharing of wifi hotspots. Think of it like an Uber-for-wifi. Anyone could offer wifi to anyone else via their mobile phone for a price. 

Like any platform, the potential applications are limited only by the imagination of the user base. 

# Purchasing and acquiring æternity: 

The first round available to purchase æternity was during æternity's public 'Friends, Family and Real Innovators' round which took place on 3rd April 2017, 13:05 GMT and lasted for 72 hours until 6th April 13:05 GMT. This round was open to the public, meaning anyone could participate. At this time, you were able to buy 1000 AE tokens for 1 ETH. Investors in the first 24 hours received an extra 10% for a total of 1100 AE tokens for 1 ETH. 

The second round will begin 29th May 2017. You can participate as well as follow any updates here: https://wallet.aeternity.com/



---
For more info, feel free to check out the [Wikipedia](https://en.wikipedia.org/wiki/AEternity) page on æternity.