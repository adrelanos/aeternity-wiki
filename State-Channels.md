State channels are a new development in blockchain technology. They come from the realization that for most purposes only, the actors involved in a smart contract are required to know about it. Two (or more) actors lock a state in the blockchain and then perform (signed) transactions between themselves, off-chain. The final state is then logged on the blockchain. If this end result is for some reason disputed, the series of signed off-chain transactions can be uploaded to the blockchain for verification and/or dispute resolution. 

The fact that State Channels are mostly off chain allows for both improved scalability, because most of the computation and storage of intermediate states is done off-chain, and improved privacy since only the intervening parties know about the details of the transaction.

# An example:

Alice and Bob would like to transact on æternity. They both sign a transaction that specifies how much AE they both wish to commit to the transaction. The blockchain opens a channel and both can create new channel states. Channel states can either be a new distribution of funds between them, or a contract that determines a new distribution. Each of these channel states is signed by both parties and the sequence of state changes has a definite order. If a dispute arises, the latest signed state can be sent to the blockchain which will use it to distribute the funds accordingly and close the channel.  In general, there are two ways to close a channel: either the parties agree on a state and no longer wish to keep transacting, or a dispute arises and the channel is closed by the blockchain after the funds are redistributed according to the latest valid channel state. In the latter case, once the dispute is announced, a countdown begins for the closing of the channel. Both parties have the opportunity to upload signed states as candidates for the last valid state. Because each new state has an increasing [nonce](https://en.bitcoin.it/wiki/Nonce), it is trivial to verify which state is the most recent.

## Applications of State Channels
By combining State Channels with Smart Contracts, it is possible to develop a number of micro-applications that require a large volume of transactions.

### Toll API

Most APIs existing today are publicly available for anyone to call, or else they are secured by a username-password–scheme or unique access tokens. Payment channels allow for a new kind of API, where one pays for every call to the API, possibly every HTTP-request.
Paying to access an API solves DDoS problems, and it makes it easier to build high-quality APIs that are always available.
API responses that require a payment are fundamental for the creation of as of yet impossible types of businesses and can
play an important role in the emergence of the decentralized economy. They create incentives for information owners to make otherwise private data publicly available.

#### Insured Crowdfunding

We can implement insured crowdfunding using dominant assurance contracts. 
These are smart contracts that are used to raise money for a public good, like a new bridge, a school or a market.
Dominant assurance contracts differ from traditional assurance contracts like Kickstarter, in that they make it a
dominant strategy to participate. If the good is not funded, all participants get their aeon back plus interest, so they are insured against reducing their liquidity without receiving the good. Using an oracle, we can ensure that the provider of the good or service only gets paid if the good or service is actually provided.

##### Cross-Chain atomic swaps
Cross chain atomic swaps allow for trustless exchange of aeon for other cryptcurrencies (for example, bitcoins). These can be implemented using a hashlock, that locks the transactions on both blockchains under the same value.

######  Stable value assets and portfolio replication
We can use smart contracts to program synthetic assets that stay nearly the same price as a real world asset. For example,
we could make an asset that stays the same price as gold. Synthetic derivatives are created in equal and opposite pairs.
For one user to have an asset that moves with gold, a different user will have to have an asset that move inversely to gold.
For example, Alice could make a contract with Bob so that Alice owns 1 gram of gold. Out of the money in the contract,
one gram of gold worth of aeon will go to Alice, and the leftover money goes to Bob. The contract has an expiration
date when the price of gold will be measured, and the funds distributed to Alice and Bob accordingly.

####### Event contracts

Event contracts pay when an event happens and don’t pay when an event does not happen, as per the oracle’s telling. Apart from being interesting in themselves, these can be used by several different applications:

* __Insurances:__ 
We can use event contracts to implement insurances. For example, expensive music event tickets can become worthless if the weather goes bad. However, if the concert-goer receives money if the oracle decides that it rained on the day of the event, the investment can be protected so that one can afford to find an emotionally adequate alternative. Slightly more seriously, farmers are often interested in the total number of inches of rain in a season. We can insure them against their crops wilting from
dryness.
* __Whistleblowing:__ Event contracts can also be used to incentivize revealing sensitive information. For example,
we could bet on the event “Information indicating that Company A has used illegal pesticides was released on or before January 24th, 2017”. Any person with access to such information would be incentivized to first bet that the event
will happen and then release it.

######## Prediction Markets
A prediction market works by letting users bet on whether a future event will happen. From the price of the bets we can predict the future likelihood [3], [8], [16]. They are the most accurate way to measure the future at a given price. Once the event has happened, the market is settled using the oracle.
We can, for example, use prediction markets to predict which updates made to the software will be beneficial, and which of those will be harmful. We can also use them to estimate how much candidates in an election will actually be able to accomplish, so lies and baseless promises can be detected more easily!

--- taken from the [[Whitepaper_English]].
