# Whitepaper

[English (original)](http://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) | [Spanish (translation)](http://blockchain.aeternity.com/Aeternity-blockchain-espaniol.pdf) | [Chinese (translation)](http://blockchain.aeternity.com/Aeternity%E5%8C%BA%E5%9D%97%E9%93%BE%E7%99%BD%E7%9A%AE%E4%B9%A6.pdf)

# Concepts
## State Channels
The state channel design enables off-chain verification of data and smart contracts. If the verification in the channel fails, the blockchain is asked to resolve. This in return permits a high transactional throughput and parallel processing of smart contracts. Hence, the programmability of complex relationships for large numbers of users and handling high volumes of products and information in parallel is æternity's strong suit.
Only the parties participating in a smart contract know about the contents of that smart contract.
When a channel is settled on-chain, the only way it changes the blockchain state is by changing account balances.
No contract state is stored on-chain, so all channels are independent from each other. Transaction speed is limited only by bandwidth, so the æternity system can scale as well as known centralized solutions available today.
 For more information refer to [State Channel](http://www.jeffcoleman.ca/state-channels/)
## Decentralized Oracles
An oracle is a mechanism that tells the blockchain facts about the world we live in e.g. the close price of Apple shares on a particular date. Aeternity's oracle system uses the same consensus system as the Aeternity blockchain itself i.e. it does not require a separate consensus layer on top of the AE mainnet. 

To launch an oracle, an aeon holder has to commit to answering a yes or no question (e.g. whether the price of an Apple share is above $200) and specify additional conditions such as the time frame in which the Aeon holder can answer that question. The aeon holder then has to deposit/commit a certain amount of aeon, which is proportional to the time frame during which the oracle is operational. When the oracle supplies an answer that is accepted as the truth by users, the deposit will be returned to the creator of the oracle. Otherwise, the deposit will be destroyed.

Once the oracle has submitted an answer, other users are free to dispute the answer by submitting a counter-claim by depositing the same amount of aeon as the oracle creator. If there are no counter-claims by the end of the time frame, the answer supplied by the oracle is deemed to be the truth. If there are counter-claims, the consensus system for the AE mainnet will be used to decide on which is the correct answer.

Therefore, what is in effect achieved is a decentralised oracle system. The truth value of oracle answers, if in dispute, will be ultimately determined by the decentralised consensus system of the AE network.

![aeternity Oracle at work](http://i66.tinypic.com/2emjrzm.png)

For more information, refer to the [Aeternity White Paper](https://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf)

## Prediction Markets
### 1. What are prediction markets?
Prediction markets are exchange-traded markets where participants can trade around the probability of events, like the outcome of a presidential election, the likelihood of a natural disaster, the likely winner of a music competition and so on.



### Prediction markets serve two important functions:

**a) They allow participants to profit from making accurate predictions.**

Participants in a prediction market buy and sell shares based on what they think the likelihood of an outcome will be. 
It is important to note that in order for a market participant to win consistently, he/she must not only predict the outcome correctly but must also correctly assess the probability of that outcome.
Take for example an event that has a 90% probability. If on a market the current price signals a probability of 95% instead of 90%, it can still be very profitable in the long run for a trader to bet against such events, even if that trader believes that the event will likely happen given the 90% probability.
This is very counter-intuitive, but it is easily explained by doing the math.

If Alice makes 100 different bets against events that have a 90% probability, she will be right 10 times and wrong 90 times. However, because the odds given for each event were 19 to 1 (0.95/0.05=19), Alice will still make a nice profit assuming all bets were made for the same amount of money. In this case, if every bet was a 1000AE bet, Alice will make a profit of  5000AE (10x950-90x50=5000).

**b) They reveal information using the price mechanism.**
 
Given that the participants in a prediction market are rewarded for being correct and punished for being wrong, they will try to be as accurate as possible and the prices will reflect that. In prediction markets prices can be understood as showing the probabilities of the outcome that is being traded.

An example here could be a miner who wants to plan his hardware purchases in advance and needs to know the probability of the total hash rate getting past a certain level in the following six months. In this case, instead of guessing or relying on his intuition, the miner can set up a prediction market that will give him very accurate probabilities.

### 2. How do prediction markets work on Æternity
Prediction markets (Oracles) are one of the most anticipated use cases for blockchains. They can make possible the harnessing of the wisdom of the crowds in a decentralised and transparent manner for the first time.

Ethereum has Augur and Gnosis trying to build prediction markets on top of it, with each its different system and currency.
æternity differentiates itself, by integrating the oracle into the blockchain consensus. 

Any user may create an oracle by posing a question or statement, staking coins and providing a binary or a scaled answering option. 
AE coins can be used to acquire stakes of those specific outcomes. 
The more sure a user is about the outcome, the more stakes he may acquire and hence more likely (he thinks) the outcome will be correct. Applying the wisdom of the crowd to all participating users of the prediction market, it is possible to 

a) statistically predict the probability of a future event occurring  

b) verify historic data from legacy systems or other blockchains

c)  verify API data from legacy systems or other blockchains

Meaning any data outside the blockchain can be translated into a deterministic value that can be used in æternity smart contracts, making real-world data easy accessible and actionable.  

##### Prediction Market - High Level Concept
![aeternity prediction market](http://i66.tinypic.com/2emjrzm.jpg)

##### Oracle & Prediction Market - High Level Concept
![aeternity oracle & prediction market](http://i63.tinypic.com/30c291s.png)

## Governance & Consensus
![æternity governance](http://i67.tinypic.com/axehab.png)
## Futarchy
Here follows a collection of in-depth analysis about Futarchy ordered by publication date:
* [Futarchy: Vote Values, But Bet Beliefs - by Robin Hanson](http://mason.gmu.edu/~rhanson/futarchy.html)
* [An Introduction to Futarchy - by Vitalik Buterin](https://blog.ethereum.org/2014/08/21/introduction-futarchy/)
* [Futarchy: Two-Step Democracy with Voting + Prediction Markets - by Melanie Swan](https://books.google.it/books?id=RHJmBgAAQBAJ&pg=PA51&lpg=PA51&redir_esc=y#v=onepage&q&f=false)
* [Markets for the Future - by Matt Liston](https://medium.com/@ConsenSys/markets-for-the-future-c73fa73fe35d)
* [Empirical Cryptoeconomics - by Vitalik Buterin](https://www.reddit.com/r/ethereum/comments/453sid/empirical_cryptoeconomics/)
* [DAOs, Democracy and Governance - by Ralph C. Merkle](http://merkle.com/papers/DAOdemocracyDraft.pdf)
* [Response to Merkle’s DAO Paper - by Dan Finlay](https://medium.com/@danfinlay/response-to-merkles-dao-paper-61d76d2dd333)
* [BFF: A Recursive Merkle DAO - by Dan Finlay](https://medium.com/@danfinlay/bff-a-recursive-merkle-dao-121327d48493)
* [Merkle’s Futarchy - By Robin Hanson](http://www.overcomingbias.com/2016/07/merkles-futarchy.html)
# Research
Eg.) Turing, State Channels, Blockchain etc.
# Working Theories

# Open problems
## Optimal properties of consensus algorithms
## Censorship resistance
## Maximally accurate time stamping
## Scalable validation
## Optimal data availability solutions
