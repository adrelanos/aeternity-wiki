State channels are a new development in blockchain technology. They come from the realization that for most purposes only the actors involved in a smart contract need to know about it. Two (or more) actors lock a state in the blockchain and then perform (signed) transactions between themselves, off-chain. The final state is then logged on the blockchain. If this end result is for some reason disputed, the series of signed off-chain transactions can be uploaded to the blockchain for verification and/or dispute resolution. 

The fact that State Channels are mostly off chain allows for both improved scalability, because most of the computation and storage of intermediate states is done off-chain, and improved privacy since only the intervening parties know about the details of the transaction.

## An example

Alice and Bob would like to transact on æternity. They both sign a transaction that specifies how much AE they both wish to commit to the transaction. The blockchain opens a channel and both can create new channel states. Channel states can either be a new distribution of funds between them, or a contract that determines a new distribution. Each of these channel states is signed by both parties and the sequence of state changes has a definite order. If a dispute arises, the latest signed state can be sent to the blockchain which will use it to distribute the funds accordingly and close the channel.  In general, there are two ways to close a channel: either the parties agree on a state and no longer wish to keep transacting, or a dispute arises and the channel is closed by the blockchain after the funds are redistributed according to the latest valid channel state. In the latter case, once the dispute is announced, a countdown begins for the closing of the channel. Both parties have the opportunity to upload signed states as candidates for the last valid state. Because each new state has an increasing [nonce](https://en.bitcoin.it/wiki/Nonce), it is trivial to verify which state is the most recent.

## Applications of State Channels
By combining State Channels with Smart Contracts, it is possible to develop a number of micro-applications that require a large volume of transactions.

### Toll API

Most APIs existing today are publicly available for anyone to call, or else they are secured by a username-password–scheme or unique access tokens. Payment channels allow for a new kind of API, where one pays for every call to the API, possibly every HTTP-request.
Paying to access an API solves DDoS problems, and it makes it easier to build high-quality APIs that are always available.
API responses that require a payment are fundamental for the creation of as of yet impossible types of businesses and can
play an important role in the emergence of the decentralized economy. They create incentives for information owners to make otherwise private data publicly available.

### Insured Crowdfunding

### Cross-Chain atomic swaps

###  Stable value assets and portfolio replication

### Event contracts

### Insurances

### Prediction Markets

### Whistleblowing


--- taken from the whitepaper
