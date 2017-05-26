![FAQ image](https://cdn-images-1.medium.com/max/1400/1*zsBAnzRQJuhIJ4phSDoEEA.png)

Table of Contents
=================

   * [Table of Contents](#table-of-contents)
   * [How is æternity different from Ethereum and Bitcoin?](#how-is-æternity-different-from-ethereum-and-bitcoin)
   * [Why is æternity faster than Ethereum?](#why-is-æternity-faster-than-ethereum)
   * [In what language is æternity written?](#in-what-language-is-æternity-written)
   * [Which PoW Algorithm is used for mining in æternity?](#which-pow-algorithm-is-used-for-mining-in-æternity)
   * [How does PoS work in æternity?](#how-does-pos-work-in-æternity)
   * [How æternity protected from another DAO attack?](#how-is-æternity-protected-from-another-dao-attack)
   * [Is smart contract verification on the roadmap?](#is-smart-contract-verification-on-the-roadmap)
   * [How does on-chain conflict resolution work? (crypto-court)](#how-does-on-chain-conflict-resolution-work-crypto-court)
   * [What is the Circulating Supply of AE?](#what-is-the-circulating-supply-of-æ)
   * [What is the Maximum Supply of AE?](#what-is-the-maximum-supply-of-ae)
   * [How is the AE dispersed?](#how-is-the-ae-dispersed)
   * [Can malicious rich people make an oracle lie?](#can-malicious-rich-people-make-an-oracle-lie)
   * [How does æternity compare with..?](#how-does-æternity-compare-with)
   * [æternity is a new blockchain?](#æternity-is-a-new-blockchain)
   * [What are æternity tokens be used for?](#what-are-æternity-tokens-be-used-for)
   * [What are some of the more interesting applications that can be created on æternity?](#what-are-some-of-the-more-interesting-applications-that-can-be-created-on-æternity)
   * [What makes æternity smart contracts special?](#what-makes-æternity-smart-contracts-special)
   * [What are some of the features of æternity virtual machine?](#what-are-some-of-the-features-of-æternity-virtual-machine)
   * [Why do we need Ethereum?](#why-do-we-need-ethereum)
   * [What is the legal status of æternity?](#what-is-the-legal-status-of-æternity)
   * [What’s the difference between an account and the æternity wallet?](#whats-the-difference-between-an-account-and-the-æternity-wallet)
   * [Will there be different types of nodes in æternity?](#will-there-be-different-types-of-nodes-in-æternity)
   * [How can I type the æ character?](#how-can-i-type-the-æ-character)
   * [What can I expect to happen from æternity in the near future?](#what-can-i-expect-to-happen-from-æternity-in-the-near-future)

# How is æternity different from Ethereum and Bitcoin? #

Smart contracts don't yet exist in Bitcoin, and all transactions are executed on-chain.

In Ethereum, smart contracts exist on-chain for multiple blocks. They hold state and can interact with other contracts. There is only a ground layer for smart contracts, without a coherent design, coherent API for web apps, naming system, nor oracles. These can only be built _on top of_ the blockchain.

In æternity, smart contracts only exist for a moment. They are settled _independently_ from all other contracts via state channels. This makes blockchain use cases and throughput more scalable for mainstream adoption and suitable for private use cases.

# Why is æternity faster than Ethereum? #
Since contracts on æternity are independent, they can be processed in parallel.

On Ethereum it is possible to move computation, but it is much more complicated than standard contracts. A lot of boilerplate code needs to be reimplemented for every contract.

On æternity computation by default happens off-chain.

# In what language is æternity written? #

The blockchain code of æternity core is written in Erlang, which makes it easy to write distributed, fault-tolerant, soft real-time and highly available unstoppable applications. 

Erlang was chosen because it is the perfect choice to write a blockchain from scratch, enabling superior code execution, stability, and performance.

# Which PoW Algorithm is used for mining in æternity? #

æternity uses "Cuckoo Cycle" Proof-of-Work hash algorithm. It is more power efficient than most other algorithms currently available. Theoretically, devices with low power such as smartphones and tablets can mine on "Cuckoo Cycle" efficiently.

For more info: [Mining](Mining)

# How does PoS work in æternity? #

Any aeon holder can launch an oracle by committing to answering a yes/no question on the blockchain. The creator is required to deposit aeon in proportion to the length of the time frame. Other users can submit counterclaims by depositing the same amount of aeon. If there are counterclaims, the consensus mechanism will be used to decide the oracle. If the creator's answer is accepted, the aeon will be returned to the creator; Otherwise, it will be burned. And so, the creator will be rewarded if telling the truth and penalized if lying.

For more info: [Mining](Mining), [Oracles](Oracles)

# How is æternity protected from another DAO attack? #

In the DAO, some people trusted other people to spend their money for them. However, if you give your money to someone and trust them to spend it, there is nothing you can do to stop them from robbing you. 

æternity, in contrast, supports trustless smart contracts. With æternity, there is no reason to trust anybody or any other blockchain system. After all, any smart contract that requires trust is not so smart.

Since contracts in aeternity are independent of each other, it is much easier to prove and verify what each contract does.

# Is smart contract verification on the roadmap? #

The programming language for contracts will be written in a high-level functional language. This eliminates many types of possible errors and aids formal verification. Additionally, since contracts do not depend on each others' state, it is easier be correct.

# How does on-chain conflict resolution work? (Crypto-court) #

It is possible that conflicting final channel states are submitted to the blockchain. In this case, the blockchain will examine which has a higher nonce. Only the higher nonced version of the state is accepted. Every time there's a channel payment or update the channel state, the nonce is increased. 

The blockchain is not completely stateless. It keeps a record of each account balance and the results of every oracle, among other things. What is important for scalability is that channels cannot edit any shared memory. It is deterministic to let processes read data in parallel, but it is not deterministic to let processes edit data in parallel. Since channels can't edit shared memory, we can process all the channel transactions in parallel.

# What is the Circulating Supply of æ? #

Total æ distributed during Contribution Phase 1: 139,089,935.082

Total æ to be distributed during Contribution Phase 2: 21,000,000 CHF (Swiss Francs)

Total æ in circulation after contribution phase 2: 

# What is the Maximum Supply of AE? #

The maximum supply of AE tokens will be determined after the phase two of æternity backing campaign ends. 

# How is the AE dispersed? #

Following the phase two of æternity backing campaign, 82 % of the total AE that has been created will be distributed to all investors. While 17% of the AE has been reserved for the founding team, the founding company, and the foundation. Additionally, 1% of the AE available will be allocated to people who have BTC and ETH addresses. This will encourage the use of AE tokens and the æternity network.

90% of the AE that has been reserved for the founding team (a total of 17% of the available AE) will be locked away for a period of time so as to discourage team members from taking the AE tokens and leaving the project. 

# Can malicious rich people make an oracle lie? #

If people try to make the oracle lie, the blockchain ends up forking into two. One side is honest and the other dishonest. The attackers lose their bets on both sides of the fork, and the defenders win their bets on both sides. The side that answers the question honestly is the official æternity blockchain, and the other side is a new altcoin.

The people who caused the attack lose all the money they attacked with. The defenders all earn twice as much money as they used to defend with. Even a whale can't afford to do this attack many times, and we quickly recover after each attack with an honest oracle.

# How does æternity compare with..? #

* Ethereum is a Turing complete *stateful* smart contract system. It allows applications like subcurrencies, domain name servers, and card game gambling.
* Cosmos is a way to move coins from one blockchain to another.
* Qtum is a proposal for a software suite for making applications on blockchains like æternity or Ethereum.
* Ethereum's oracle systems, like Augur and Gnosis, will probably be much more expensive than the æternity system. æternity's oracle system is market based instead of voting based. It is connected to the blockchain consensus mechanism in a way that makes it more secure.
* æternity is a Turing complete *stateless* smart contract system with a built-in oracle. It allows the creation of trustless Dapps such as insurance, sports betting, stablecoins, prediction markets, insured crowdfunding, and card game gambling.

# æternity is a new blockchain? #

Yes, æternity is a next-level, brand new blockchain, with many features that solve current issues in blockchain technology in an elegant way. Reading [the whitepaper](Whitepaper_English) is the best way to understand æternity’s design. æternity’s first testnet is already online, ready for testing and mining.

# What are æternity tokens be used for? #

æternity tokens are called aeon (AE for short), and are the access tokens to the æternity blockchain. They act as a unit of account for the resources spent. Aeon are the energy (“crypto-fuel”) used to power any application implemented on the æternity platform. Every action (and even inaction) costs something, even if only a fraction of a cent.

# What are some of the more interesting applications that can be created on æternity? #
source: [website FAQ](https://blog.aeternity.com/%C3%A6ternity-frequently-asked-questions-faq-9cb0e34e0740)

æternity enables a high transaction throughput. Broadly speaking, and contrary to traditional blockchain limitations, any type of application that requires high transactional speed will run smoothly on æternity. Here are some of those:

* Nano and micro payments.
* Smart contracts using oracles to initiate millions of parallel transactions.
* Side-chained blockchain networks that can communicate efficiently and securely.
* Multiplayer video games where the rules are enforced by the blockchain. Poker, chess, Go, and first person shooter games.
* Investment opportunities for ventures that are specializing in predicting the price of food.
* Contracts for powering crowd sales to finance public goods and create a sustainable economy.
* Lie detectors to know when leaders or experts are hiding the truth.
* Prediction markets that can help us better prepare for the future.
* Everything else that we (and You) haven’t thought of yet.

# What makes æternity smart contracts special? #
source: [website FAQ](https://blog.aeternity.com/%C3%A6ternity-frequently-asked-questions-faq-9cb0e34e0740)

Manifold factors contribute to æternity’s uniqueness! One major advantage of æternity smart contracts is the fact that they are created off-chain. This allows to — once created — to interact with other participating parties blazingly fast and has important privacy implications. The users’ interactions stay off-chain and are kept secure. Only in cases of disagreement will a transaction be submitted on-chain. The æternity blockchain will function as a crypto-court.

Furthermore, there is no limit to the volume of smart contracts that can be processed per second, since æternity smart contracts don’t share state, they can be processed in parallel.

In comparison to ‘legacy’ Ethereum, we switched from being goto-based to being function-based. Thus, it is a lot simpler to reason about and write more secure smart contract code.

# What are some of the features of æternity virtual machine? #
source: [website FAQ](https://blog.aeternity.com/%C3%A6ternity-frequently-asked-questions-faq-9cb0e34e0740)

We are building a state-of-the-art virtual machine for secure and efficient blockchain computations. For example, we have added a tool for ‘merklizing’ the code, so that the users only publish the portion of code that actually gets executed.

æternity smart contracts can be massive and can be gigabytes to terabytes in volume. This, however, is not a problem  as long as the part that gets executed is relatively small.

# Why do we need Ethereum? #

The primary reason for using Ethereum created tokens for the token sale is that æternity is not functional yet. Once æternity launches, tokens will exist on æternity. However, even if æternity did exist, it wouldn’t give us the ability to do a decentralized token sale . Ethereum is great for this type of use-cases, that require a fully public index of things (e.g. tokens, …). æternity is focusing on scalable, real-world use-cases. Most of those don’t require data to be openly shared all of the time.

# What is the legal status of æternity? #
source: [website FAQ](https://blog.aeternity.com/%C3%A6ternity-frequently-asked-questions-faq-9cb0e34e0740)

We will provide a rock solid technology to build on, but that wouldn’t be enough if it wasn’t based on a legally safe foundation. æternity is incorporated in Liechtenstein and is in regular contact with regulators to keep track of the project’s legal status. The team includes a legal adviser and makes use of additional legal consultancy on an ad-hoc basis.

# What’s the difference between an account and the æternity wallet? #
source: [website FAQ](https://blog.aeternity.com/%C3%A6ternity-frequently-asked-questions-faq-9cb0e34e0740)

A wallet is a piece of software that is used to interact with æternity. It allows you to make accounts and channels. It will allow users to make channel contracts, bet, play games, buy/sell assets, provides identity, communicate with other users, etc. 

The account on æternity will be accessed by the wallet.

# Will there be different types of nodes in æternity? #
source: [website FAQ](https://blog.aeternity.com/%C3%A6ternity-frequently-asked-questions-faq-9cb0e34e0740)

Yes!

* Some nodes will be providing liquidity to the Lightning Network. They will have lots of channels with lots of people, so if you make a channel with them, you will be able to establish state channel contracts with many users. Using a channel contract through such a node will involve a fee.
* Some nodes will run trustless exchanges for any asset. They will also collect transaction fees. We envision nodes that let people use state channels to play games like Go, Monopoly, slot machines, or poker. Either single player,  with your friends, or with strangers. æternity enables trustless financial applications. They are not necessarily decentralized. Anyone can start a “centralized server” and use our software to create trustless financial tools.
* There can be ‘servers/nodes’ which you can use to invest in stocks, derivatives or metals. You can gamble at sports in a fully trustless and efficient way. Other nodes can specialize in recycling old accounts. There is a fee for having an account open. If the account runs out of money, anyone will be able to delete it and get a small reward.
* Some nodes will just run trading software. They will buy and sell assets offered by market makers in order to make a profit. Some nodes will specialize in participation in prediction markets, running the consensus mechanism. This will be profitable because transaction fees are the initial liquidity in these markets.

# How can I type the æ character? #
* On Windows devices it works by holding the Alt key while typing in 0230 (for æ) on the number pad.
* On MacOS the key combination is Option + ' (apostrophe key) for æ.
* On iOS and Android devices the characters can be selected by holding the "A" until a small menu appears that shows the character.


# What can I expect to happen from æternity in the near future? #
source: [website FAQ](https://blog.aeternity.com/%C3%A6ternity-frequently-asked-questions-faq-9cb0e34e0740)

The first testnet is now ready! We will be adding more features all the time. Start interacting with æternity by visiting [GitHub](http://github.com/aeternity/testnet).

Your feedback will be highly appreciated! Join our [public chat on Gitter](https://gitter.im/aeternity/Lobby).

You can also get in touch with us through our [Facebook page](https://www.facebook.com/aeternityproject), [Twitter profile](https://twitter.com/aetrnty), [LinkedIn account](https://www.linkedin.com/company/aeternity), [Telegram](https://telegram.me/aeternity), [Bitcointalk post](https://bitcointalk.org/index.php?topic=1733140.0) and our [subreddit](https://www.reddit.com/r/Aeternity).

A detailed roadmap is also in the making. You can get an update on this by [subscribing to our newsletter](http://www.aeternity.com/#newsletter).