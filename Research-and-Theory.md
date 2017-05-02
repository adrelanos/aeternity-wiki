# Whitepaper

[English (original)](http://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) | [Spanish (translation)](http://blockchain.aeternity.com/Aeternity-blockchain-espaniol.pdf) | [Chinese (translation)](http://blockchain.aeternity.com/Aeternity%E5%8C%BA%E5%9D%97%E9%93%BE%E7%99%BD%E7%9A%AE%E4%B9%A6.pdf)

# Concepts
## State Channels
The State Channel design enables off chain verification of data and smart contracts. If the verification in the channel fails, the blockchain is asked to resolve. This in return permits a high transactional throughput and parallel processing of smart contracts. Hence, the programmability of complex relationships for large numbers of users and handling high volumes of products and information in parallel is Æternity's strong suit.
Only the parties participating in a smart contract know about the contents of that smart contract.
When a channel is settled on-chain, the only way it changes the blockchain state is by changing account balances.
No contract state is stored on-chain, so all channels are independent from each other. Transaction speed is limited only by bandwidth, so the Æternity system can scale as well as known centralized solutions available today.
 For more information refer to [State Channel](http://www.jeffcoleman.ca/state-channels/)
## Decentralized Oracles
An oracle is a mechanism that tells the blockchain facts about the world we live in e.g. the close price of Apple shares on a particular date. Aeternity's oracle system uses the same consensus system as the Aeternity blockchain itself i.e. it does not require a separate consensus layer on top of the AE mainnet. 

To launch an oracle, an aeon holder has to commit to answering a yes or no question (e.g. whether the price of an Apple share is above $200) and specify additional conditions such as the timeframe in which the Aeon holder can answer that question. The aeon holder then has to deposit/commit a certain amount of aeon, which is proportional to the timeframe during which the oracle is operational. When the oracle supplies an answer that is accepted as the truth by users, the deposit will be returned to the creator of the oracle. Otherwise, the deposit will be destroyed.

Once the oracle has submitted an answer, other users are free to dispute the answer by submitting a counter-claim by depositing the same amount of aeon as the oracle creator. If there are no counter-claims by the end of the timeframe, the answer supplied by the oracle is deemed to be the truth. If there are counter-claims, the consensus system for the AE mainnet will be used to decide on which is the correct answer.

Therefore, what is in effect achieved is a decentralised oracle system. The truth value of oracle answers, if in dispute, will be ultimately determined by the decentralised consensus system of the AE network.

For more information, refer to the [Aeternity White Paper](https://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf)
## Consensus
## Futarchy
here follow a collection of in-depth analysis about Futarchy ordered by publication date:
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
