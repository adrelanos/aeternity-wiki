![FAQ image](https://cdn-images-1.medium.com/max/1400/1*zsBAnzRQJuhIJ4phSDoEEA.png)

Table of Contents
=================

   * [How is Aeternity different from Ethereum?](#how-is-aeternity-different-from-ethereum)
   * [Why is Aeternity faster than Ethereum?](#why-is-aeternity-faster-than-ethereum)
   * [How does Aeternity protect from the next DAO happening?](#how-does-aeternity-protect-from-the-next-dao-happening)
   * [Is smart contract verification on the roadmap?](#is-smart-contract-verification-on-the-roadmap)
   * [How does on-chain conflict resolution work? (crypto-court)](#how-does-on-chain-conflict-resolution-work-crypto-court)
   * [What is the Circulating Supply of AE?](#what-is-the-circulating-supply-of-ae)
   * [What is Maximum Supply of AE?](#what-is-maximum-supply-of-ae)
   * [Can malicious rich people make an oracle lie?](#can-malicious-rich-people-make-an-oracle-lie)

# How is Aeternity different from Ethereum? #

On Ethereum contracts exist on-chain for multiple blocks. They hold state and can interact with other contracts.
On Aeternity each contract only exists for a moment. It is settled independently of all the other contracts.

# Why is Aeternity faster than Ethereum? #
Since contracts on Aeternity are independent, they can be processed in parallel.

On Ethereum it is possible to move computation, but it is much more complicated than standard contracts. A lot of boilerplate code needs to be reimplemented for every contract.

On Aeternity computation by default happens off-chain.

# How does Aeternity protect from the next DAO happening? #
Since contracts are independent, it is much easier to prove and verify what each contract does.

The DAO was a problem where some people trusted other people to spend their money for them.
If you give your money to someone, and trust them to spend it for you wisely, there is nothing that I can do to stop them from robbing you.

Aeternity supports many trustless contracts. There is no reason you should ever use trust with Aeternity, or any other blockchain system.
Any smart contract that requires trust is not so smart.

# Is smart contract verification on the roadmap? #

The language for Aeternity is very simple. Smart contracts do not depend on each other's state, so it is easy to prove the correctness of a smart contract.
We wont need any special verification software to be sure of the correctness of Aeternity contracts.

Channels can be connected to each other using hashlocking. This is how cross chain atomic swaps work. This is how the lightning network works. This is how we can build prediction markets with more than 2 users.

# How does on-chain conflict resolution work? (crypto-court) #

Answer by agorism1337 from [reddit](https://www.reddit.com/r/Aeternity/comments/64x1u7/how_does_onchain_conflict_resolution_work/).

It is possible that you each submit conflicting final channel states to the blockchain. The blockchain processes both options, and examines which has a higher nonce. The higher nonced version of the state is accepted, and the other is rejected.

So every time we make a channel payment or update the channel state, we also have to update the nonce in the channel state. That way the blockchain will prefer the most recent channel state we made.

The blockchain is not completely stateless. It keeps a record of each account balance, and the results of every oracle, and some other things. What is important for scalability is that channels cannot edit any shared memory. It is deterministic to let processes read data in parallel, but it is not deterministic to let processes edit data in parallel. Since channels can't edit shared memory, we can process all the channel transactions in parallel.

# What is the Circulating Supply of AE? #
AE currently in circulation: TODO

AE in circulation after contribution phase 2: TODO

# What is Maximum Supply of AE? #
Answer by vdramaliev on [reddit](https://www.reddit.com/r/Aeternity/comments/64z73r/will_there_have_the_cap_amount_of_aeon/).

It is very much possible for the mining reward amount to be modifiable by the users through a prediction market.

# Can malicious rich people make an oracle lie? #

Answered by agorism1337 on [reddit](https://www.reddit.com/r/Aeternity/comments/64x733/the_highest_stakes_the_whales_decide_what_will_be/). (modified)

If people try to make the oracle lie, then the blockchain ends up forking into two. One side is honest, and the other is dishonest. The attackers lose their bets on both side of the fork, and the defenders win their bets on both sides. The side that answers the question honestly is the official Aeternity blockchain, the other is a new altcoin.

The people who caused the attack lose all the money they attacked with. The defenders all earn twice as much money as they used to defend with.

Even a whale can't afford to do this attack many times, and we quickly recover after each attack with an honest oracle.

# How does aeternity compare to ...? #

Based on replies by agorism1337 at reddit from [here](https://www.reddit.com/r/Aeternity/comments/63tabp/aeternity_vs_qtum_vs_cosmos/) and [here](https://www.reddit.com/r/Aeternity/comments/63mhg7/how_does_aeternity_contrast_with_truebit/).

* Ethereum is a turing complete stateful smart contract system. It allows for examples apps like: subcurrencies, domain name servers, and blackjack card game gambling.
* Cosmos is a way to move coins from one blockchain to another.
* Qtum is a proposal for a software suite for making dapps on blockchains like Aeternity or Ethereum.
* Ethereum's oracle systems, like Augur and Gnosis, will probably be much more expensive than the Aeternity oracle. Aeternity's oracle is market based instead of voting based. Aeternity's oracle is connected to the blockchain consensus mechanism in a way that makes it more secure.
* Aeternity is a turing complete stateless smart contract system with a built in oracle. It allows for the creation of trustless Dapps. For example: insurance, sports betting, stablecoins, prediction markets, insured crowdfunding, blackjack card game gambling.
