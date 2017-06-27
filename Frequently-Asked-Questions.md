![FAQ image](https://cdn-images-1.medium.com/max/1400/1*zsBAnzRQJuhIJ4phSDoEEA.png)

## Table of Contents

* [æternity is a new blockchain?](#æternity-is-a-new-blockchain)
* [What are some interesting applications?](#what-are-some-interesting-applications)
* [What are the features of the æternity virtual machine?](#what-are-the-features-of-the-æternity-virtual-machine)
* [What makes æternity smart contracts special?](#what-makes-æternity-smart-contracts-special)
* [What are æternity tokens used for?](#what-are-æternity-tokens-used-for)
* [How is æternity different from Ethereum and Bitcoin?](#how-is-æternity-different-from-ethereum-and-bitcoin)
* [Why is æternity faster than Ethereum?](#why-is-æternity-faster-than-ethereum)
* [How does æternity compare with..?](#how-does-æternity-compare-with)
* [How is æternity protected from another DAO attack?](#how-is-æternity-protected-from-another-dao-attack)
* [Can malicious rich people make an oracle lie?](#can-malicious-rich-people-make-an-oracle-lie)
* [Which PoW Algorithm is used for mining in æternity?](#which-pow-algorithm-is-used-for-mining-in-æternity)
* [How does PoS work in æternity?](#how-does-pos-work-in-æternity)
* [How does on-chain conflict resolution work? (crypto-court)](#how-does-on-chain-conflict-resolution-work-crypto-court)
* [In what language is æternity written?](#in-what-language-is-æternity-written)
* [Can smart contracts be formally verified?](#can-smart-contracts-be-formally-verified)
* [What’s the difference between an account and wallet?](#whats-the-difference-between-an-account-and-wallet)
* [Will there be different types of nodes in æternity?](#will-there-be-different-types-of-nodes-in-æternity)
* [Why is Ethereum used for the token sale?](#why-is-ethereum-used-for-the-token-sale)
* [What is the circulating supply of aeon?](#what-is-the-circulating-supply-of-aeon)
* [What is the maximum supply of aeon?](#what-is-the-maximum-supply-of-aeon)
* [How is the aeon dispersed?](#how-is-the-aeon-dispersed)
* [What is the legal status of æternity?](#what-is-the-legal-status-of-æternity)
* [How can I type the æ character?](#how-can-i-type-the-æ-character)
* [What can I expect in the near future?](#what-can-i-expect-in-the-near-future)
* [How do I contact you?](#how-do-i-contact-you)
***


## æternity is a new blockchain?

Yes, æternity is a next-level, brand new blockchain, with many features
that solve current issues in blockchain technology in an elegant way.
Read [the white paper](Whitepaper_English) to
understand æternity’s design. 
æternity enables a high transaction throughput.
æternity’s testnet is already
online, ready for testing and mining.


## What are some interesting applications?

* Nano and micropayments.
* Lightning network that allows payments that flow across multiple 
  blockchains between the sender and recipient. 
* Multiplayer video games where the rules are enforced by the
  blockchain, including Poker, Chess, Go, and first person shooter
  games.
* Investment opportunities for ventures that specialize in predicting
  the price of food.
* Insurance for farmers producing food, to protect them against
  volatility in the price of food.
* Contracts for powering crowd sales to finance public goods and create
  a sustainable economy.
* Lie detectors to know when leaders or experts are hiding the truth.
* Prediction markets that can help us better prepare for the future.
* Everything else that we (including you) haven’t thought of yet.


## What are the features of the æternity virtual machine?

It is a state-of-the-art virtual machine for secure and efficient
blockchain computations. For example, we have added a tool for
‘merklizing’ the code so that the users only publish the portion of code
that actually gets executed. Therefore, æternity smart contracts can be terabytes
in volume without a problem if part that gets executed is relatively
small.


## What makes æternity smart contracts special?

One major advantage is that they are created off-chain. This enables
interaction with other participating parties quickly and privately. The
users’ interactions stay off-chain and are kept secure. Only in cases of
disagreement will a transaction be submitted on-chain, where the blockchain
will function as a "crypto-court".

Furthermore, there is no limit to the volume of smart contracts that can
be processed per second: Since æternity smart contracts don’t share
state, they can be processed in parallel.

In comparison with Ethereum, we're function-based instead of goto-based.
Thus, it is a lot simpler to reason about and write secure smart
contract code.


## What are æternity tokens used for?

æternity tokens are called aeon (AE for short) and are the access
tokens to the æternity blockchain. They are the unit of account for the
resources spent. Aeon are the energy (“crypto-fuel”) used to power any
application implemented on the æternity platform. Every action (and even
inaction) costs something, even if only a fraction of a cent.


## How is æternity different from Ethereum and Bitcoin?

Smart contracts don't yet exist in Bitcoin, and channels are limited
to only doing payments. Bitcoin channels are also only one-way channels
currently.

In Ethereum, smart contracts exist on-chain for multiple blocks. They
hold state and can interact with other contracts. 

In æternity, smart contracts only exist for a moment. They are settled
_independently_ from all other contracts via state channels. 
Since contracts on æternity are independent, they can be processed in
parallel. This makes
Aeternity more scalable and thus, more suited for mainstream adoption.

## Why is æternity faster than Ethereum?

On æternity computation by default happens off-chain. While it is possible to move computation off-chain in Ethereum, it is much more complicated than standard contracts. A lot of boilerplate code needs to be reimplemented for every contract.
If you want an off-chain app with turing complete capability on ethereum, that app would depend on an on-chain virtual machine to process the off-chain state. 
Layering another compiler on top of the ethereum VM makes it slower.


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


## Which PoW Algorithm is used for mining in æternity?

æternity uses the "Cuckoo Cycle" Proof-of-Work hash algorithm. It is more
power efficient than most other algorithms currently available.
Theoretically, devices with low power such as smartphones and tablets
can mine on "Cuckoo Cycle" efficiently.

For more info: [Mining](Mining)


## How does PoS work in æternity?

Any aeon holder can ask the oracle a question. It has to be a yes/no
question. They choose a date when they want the oracle to answer the
question. Asking the oracle a question costs a fee in Aeons.

The oracle is a market where Aeon holders can bet with each other.
The bets are designed so that the Aeon holders are incentivized to
reveal the true outcome of the question.
They are betting on the correlation between the future difficulty
of blocks, and the answer to the question.

For more info: [Mining](Mining), [Oracles](Oracles)


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


## In what language is æternity written?

The blockchain of æternity is written in Erlang, which makes
it easy to write distributed, fault-tolerant, soft real-time, and highly
available unstoppable applications.

Erlang was chosen because it is the perfect choice to write a blockchain
from scratch, enabling superior code execution, stability, and
performance.


## Can smart contracts be formally verified?

Smart contracts are function-based. This eliminates many types of
possible errors, aids reasoning, and enables formal verification.
Additionally, since contracts do not depend on each others' state, it is
easier be correct.


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
trustless financial applications, but doesn't require decentralization.
Anyone can start a “centralized server” and use our
software to create trustless financial tools.

There can be nodes to invest in stocks, derivatives, or
metals. You can gamble at sports in a fully trustless and efficient way.
Other nodes can specialize in recycling old accounts: There is a fee for
having an account open. If the account runs out of money, anyone will be
able to delete it for a small reward.

Some nodes will run trading software. They will buy and sell assets
offered by market makers. Some nodes will specialize in participation in
prediction markets.


## Why is Ethereum used for the token sale?

The primary reason for using Ethereum tokens for the sale
is that æternity is not functional yet. Once æternity launches, tokens
will exist on æternity. Ethereum is great
for token sales. æternity is focusing on scalable, real-world use cases
which usually don’t require data to be openly shared all of the time.


## What is the circulating supply of aeon?

Somewhere between 300 million and 200 million.


## What is the maximum supply of aeon?

The block reward is set by the governance mechanism. 
No one knows how fast the community will decide to
increase the supply of aeon.


## How is the aeon dispersed?

Following phase two of the æternity backing campaign, 82% of the total aeon that has been created will be distributed to all investors. 17% has been reserved for the founding team, the founding company, and the foundation. 1% of the aeon available will be allocated to people who have BTC and ETH addresses. This will encourage the use of aeon tokens and the æternity network.

90% of the aeon reserved for the founding team, company, and foundation will be released over time in order to discourage team members from leaving the project.


## What is the legal status of æternity?

æternity is incorporated in Liechtenstein and is in regular contact with
regulators in order to keep track of the project’s legal status. The team
includes a legal adviser and makes use of additional legal consultancy
on an ad-hoc basis.


## How can I type the æ character?

* Windows: Hold Alt and type 0230 on the number pad.
* macOS: Option and ' (apostrophe).
* iOS and Android: Hold "a" until a small menu appears.


## What can I expect in the near future?

The first testnet is ready, and we are adding more features all the time.
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