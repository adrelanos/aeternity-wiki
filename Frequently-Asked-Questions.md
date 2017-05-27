![FAQ image](https://cdn-images-1.medium.com/max/1400/1*zsBAnzRQJuhIJ4phSDoEEA.png)

## Table of Contents


* [Table of Contents](#table-of-contents)
* [How is æternity different from Ethereum and Bitcoin?](#how-is-æternity-different-from-ethereum-and-bitcoin)
* [Why is æternity faster than Ethereum?](#why-is-æternity-faster-than-ethereum)
* [In what language is æternity written?](#in-what-language-is-æternity-written)
* [Which PoW Algorithm is used for mining in æternity?](#which-pow-algorithm-is-used-for-mining-in-æternity)
* [How does PoS work in æternity?](#how-does-pos-work-in-æternity)
* [How æternity protected from another DAO attack?](#how-is-æternity-protected-from-another-dao-attack)
* [Can smart contracts be formally verified?](#can-smart-contracts-be-formally-verified)
* [How does on-chain conflict resolution work? (crypto-court)](#how-does-on-chain-conflict-resolution-work-crypto-court)
* [What is the Circulating Supply of AE?](#what-is-the-circulating-supply-of-æ)
* [What is the Maximum Supply of AE?](#what-is-the-maximum-supply-of-ae)
* [How is the AE dispersed?](#how-is-the-ae-dispersed)
* [Can malicious rich people make an oracle lie?](#can-malicious-rich-people-make-an-oracle-lie)
* [How does æternity compare with..?](#how-does-æternity-compare-with)
* [æternity is a new blockchain?](#æternity-is-a-new-blockchain)
* [What are æternity tokens be used for?](#what-are-æternity-tokens-be-used-for)
* [What are some interesting applications?](#what-are-some-interesting-applications)
* [What makes æternity smart contracts special?](#what-makes-æternity-smart-contracts-special)
* [What are the features of the æternity virtual machine?](#what-are-the-features-of-the-æternity-virtual-machine)
* [Why is Ethereum used for the token sale?](#why-is-ethereum-used-for-the-token-sale)
* [What is the legal status of æternity?](#what-is-the-legal-status-of-æternity)
* [What’s the difference between an account and wallet?](#whats-the-difference-between-an-account-and-wallet)
* [Will there be different types of nodes in æternity?](#will-there-be-different-types-of-nodes-in-æternity)
* [How can I type the æ character?](#how-can-i-type-the-æ-character)
* [What can I expect in the near future?](#what-can-i-expect-in-the-near-future)
* [How do I contact you?](#how-do-I-contact-you)
***

## How is æternity different from Ethereum and Bitcoin?

Smart contracts don't yet exist in Bitcoin, and all transactions are
executed on-chain.

In Ethereum, smart contracts exist on-chain for multiple blocks. They
hold state and can interact with other contracts. There is only a ground
layer for smart contracts, without a coherent design, coherent API for
web apps, naming system, nor oracles. These can only be built _on top
of_ the blockchain.

In æternity, smart contracts only exist for a moment. They are settled
_independently_ from all other contracts via state channels. This makes
blockchain use cases and throughput more scalable for mainstream
adoption and suitable for private use cases.

## Why is æternity faster than Ethereum?

Since contracts on æternity are independent, they can be processed in
parallel.

On æternity computation by default happens off-chain. While it is possible to move computation in Ethereum, it is much more complicated than standard contracts. A lot of boilerplate code needs to be reimplemented for every contract.

## In what language is æternity written?

The blockchain of æternity is written in Erlang, which makes
it easy to write distributed, fault-tolerant, soft real-time, and highly
available unstoppable applications.

Erlang was chosen because it is the perfect choice to write a blockchain
from scratch, enabling superior code execution, stability, and
performance.

## Which PoW Algorithm is used for mining in æternity?

æternity uses the "Cuckoo Cycle" Proof-of-Work hash algorithm. It is more
power efficient than most other algorithms currently available.
Theoretically, devices with low power such as smartphones and tablets
can mine on "Cuckoo Cycle" efficiently.

For more info: [Mining](Mining)

## How does PoS work in æternity?

Any aeon holder can launch an oracle by committing to answering a yes/no
question on the blockchain. The creator is required to deposit aeon in
proportion to the length of the time frame. Other users can submit
counterclaims by depositing the same amount of aeon. If there are
counterclaims, the consensus mechanism will be used to decide the
oracle. If the creator's answer is accepted, the aeon will be returned
to the creator; Otherwise, it will be burned. And so, the creator will
be rewarded if telling the truth and penalized if lying.

For more info: [Mining](Mining), [Oracles](Oracles)

## How is æternity protected from another DAO attack?

In the DAO, some people trusted other people to spend their money for
them. However, if you give your money to someone and trust them to spend
it, there is nothing you can do to stop them from robbing you.

æternity, in contrast, supports trustless smart contracts. With
æternity, there is no reason to trust anybody or any other blockchain
system. After all, any smart contract that requires trust is not so
smart.

Since contracts in aeternity are independent of each other, it is much
easier to prove and verify what each contract does.

## Can smart contracts be formally verified?

Smart contracts are function-based. This eliminates many types of
possible errors, aids reasoning, and enables formal verification.
Additionally, since contracts do not depend on each others' state, it is
easier be correct.

## How does on-chain conflict resolution work? (Crypto-court) #

It is possible that conflicting final channel states are submitted to
the blockchain. In this case, the blockchain will look for the state with the 
higher nonce, and only the higher nonced version is accepted. 

Every time there's a channel payment or update to the channel state, the
nonce is increased.

The blockchain is not completely stateless. It keeps a record of each
account balance and the results of every oracle, among other things.
It is important for scalability that channels cannot edit any
shared memory: Processes read data in
parallel deterministically, but it is not deterministic for processes to edit data in
parallel. Since channels can't edit shared memory, we can process all
the channel transactions in parallel.

## What is the Circulating Supply of aeon?

Aeon distributed during Contribution Phase 1: 139,089,935.082

Aeon to be distributed during Contribution Phase 2: 21,000,000 Swiss Francs

## What is the Maximum Supply of aeon?

The maximum supply of aeon tokens will be determined after phase two
of the æternity backing campaign ends.

## How is the aeon dispersed?

Following phase two of the æternity backing campaign, 82% of the total aeon that has been created will be distributed to all investors. 17% has been reserved for the founding team, the founding company, and the foundation. 1% of the AE available will be allocated to people who have BTC and ETH addresses. This will encourage the use of aeon tokens and the æternity network.

90% of the aeon reserved for the founding team, company, and foundation will be released over time in order to discourage team members from leaving the project.

## Can malicious rich people make an oracle lie?

If people try to make the oracle lie, the blockchain forks
in two: One side is honest and the other dishonest. The attackers lose
their bets on both sides of the fork, and the defenders win their bets
on both. The side that answers the question honestly is the
official æternity blockchain, and the other side is a new altcoin.

The people who caused the attack will lose all the money they attacked with.
The defenders all earn twice the money that they used to defend.
Even a whale can't afford to do this attack many times, and we quickly
recover after each attack with an honest oracle.

## How does æternity compare with..?

* Ethereum is a Turing complete *stateful* smart contract system. It
  allows applications like subcurrencies, domain name servers, and card
  game gambling.
* Cosmos is a way to move coins from one blockchain to another.
* Qtum is a proposal for a software suite for making applications on
  blockchains like æternity or Ethereum.
* Ethereum's oracle systems, like Augur and Gnosis, will probably be
  much more expensive than the æternity system. æternity's oracle system
  is market based instead of voting based. It is connected to the
  blockchain consensus mechanism in a way that makes it more secure.
* æternity is a Turing complete *stateless* smart contract system with a
  built-in oracle. It allows the creation of trustless Dapps such as
  insurance, sports betting, stablecoins, prediction markets, insured
  crowdfunding, and card game gambling.

## æternity is a new blockchain?

Yes, æternity is a next-level, brand new blockchain, with many features
that solve current issues in blockchain technology in an elegant way.
Reading [the whitepaper](Whitepaper_English) is the best way to
understand æternity’s design. æternity’s first testnet is already
online, ready for testing and mining.

## What are æternity tokens be used for?

æternity tokens are called aeon (AE for short), and are the access
tokens to the æternity blockchain. They act as a unit of account for the
resources spent. Aeon are the energy (“crypto-fuel”) used to power any
application implemented on the æternity platform. Every action (and even
inaction) costs something, even if only a fraction of a cent.

## What are some interesting applications?

æternity enables a high transaction throughput. Broadly speaking, and
contrary to traditional blockchain limitations, any type of application
that requires high transactional speed will run smoothly on æternity.
For example:

* Nano and micropayments.
* Smart contracts using oracles to initiate millions of parallel
  transactions.
* Side-chained blockchain networks that can communicate efficiently and
  securely.
* Multiplayer video games where the rules are enforced by the
  blockchain, including Poker, Chess, Go, and first person shooter
  games.
* Investment opportunities for ventures that specialize in predicting
  the price of food.
* Contracts for powering crowd sales to finance public goods and create
  a sustainable economy.
* Lie detectors to know when leaders or experts are hiding the truth.
* Prediction markets that can help us better prepare for the future.
* Everything else that we (including you) haven’t thought of yet.

## What makes æternity smart contracts special?

One major advantage is that they are created off-chain. This enables
interaction with other participating parties quickly and privately. The
users’ interactions stay off-chain and are kept secure. Only in cases of
disagreement will a transaction be submitted on-chain, where blockchain
will function as a "crypto-court".

Furthermore, there is no limit to the volume of smart contracts that can
be processed per second: Since æternity smart contracts don’t share
state, they can be processed in parallel.

In comparison to Ethereum, we're function-based instead of goto-based.
Thus, it is a lot simpler to reason about and write secure smart
contract code.

## What are the features of the æternity virtual machine?

It is a state-of-the-art virtual machine for secure and efficient
blockchain computations. For example, we have added a tool for
‘merklizing’ the code so that the users only publish the portion of code
that actually gets executed: æternity smart contracts can be terabytes
in volume without a problem if part that gets executed is relatively
small.

## Why is Ethereum used for the token sale?

The primary reason for using Ethereum created tokens for the token sale
is that æternity is not functional yet. Once æternity launches, tokens
will exist on æternity. However, even if æternity did exist, it wouldn’t
give us the ability to do a decentralized token sale. Ethereum is great
for the type of use case that requires a fully public index of things
(e.g. tokens). æternity is focusing on scalable, real-world use cases
which usually don’t require data to be openly shared all of the time.

## What is the legal status of æternity?

æternity is incorporated in Liechtenstein and is in regular contact with
regulators to keep track of the project’s legal status. The team
includes a legal adviser and makes use of additional legal consultancy
on an ad-hoc basis.

## What’s the difference between an account and wallet?

A wallet is a piece of software that is used to interact with æternity.
It's what makes and accesses accounts and channels. With it, users make
channel contracts, bet, play games, buy/sell assets, provides identity,
communicate with other users, etc.

## Will there be different types of nodes in æternity?

Yes. Some nodes will be providing liquidity to the Lightning Network.
They will have lots of channels with lots of people. If you make a
channel, you will be able to establish state channel contracts with many
users. Using a channel contract through such a node will involve a fee.

Some nodes will run trustless exchanges for any asset, as well as
collect transaction fees. We envision nodes that let people use state
channels to play games like Go, Monopoly, slot machines, or poker –
single player, with your friends, or with strangers. æternity enables
trustless financial applications, but not necessarily decentralized
applications. Anyone can start a “centralized server” and use our
software to create trustless financial tools.

There can be "servers/nodes" to invest in stocks, derivatives, or
metals. You can gamble at sports in a fully trustless and efficient way.
Other nodes can specialize in recycling old accounts: There is a fee for
having an account open. If the account runs out of money, anyone will be
able to delete it for a small reward.

Some nodes will just run trading software. They will buy and sell assets
offered by market makers. Some nodes will specialize in participation in
prediction markets, running the consensus mechanism. This will be
profitable because transaction fees are the initial liquidity in these
markets.

## How can I type the æ character?

* Windows: Hold Alt and type 0230 on the number pad.
* macOS: Option and ' (apostrophe).
* iOS and Android: Hold "a" until a small menu appears.

## What can I expect in the near future?

The first testnet ready, and we are adding more features all the time.
Start interacting with æternity by visiting
[GitHub](http://github.com/aeternity/testnet). A detailed roadmap is
coming soon.
[Subscribe to our newsletter](http://www.aeternity.com/#newsletter) to
stay updated.

## How do I contact you?

Your feedback is highly appreciated: Join our
[public chat on Gitter](https://gitter.im/aeternity/Lobby).

You can also get in touch with us through our
[Facebook page](https://www.facebook.com/aeternityproject),
[Twitter profile](https://twitter.com/aetrnty),
[LinkedIn account](https://www.linkedin.com/company/aeternity),
[Telegram](https://telegram.me/aeternity),
[Bitcointalk post](https://bitcointalk.org/index.php?topic=1733140.0)
and our [subreddit](https://www.reddit.com/r/Aeternity).
***

on editing this page please use the right tags # = H1 / ## = H2 / ### = H3
and *** = horizontal line. For now this document is SEO safe!!!