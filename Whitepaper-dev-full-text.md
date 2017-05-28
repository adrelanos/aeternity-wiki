# æternity Whitepaper for development purposes

>We need this document to refer to the full text if we write some
>developer tutorials or other stuff Note that this is a draft and will
>change likely!

## CONTENTS

* [Abstract](#abstract)

* I. [Introduction](#introduction)
  * [Previous Work](#previous-work)

* II. æTERNITY BLOCKCHAIN

* [Tokens, accounts and blocks](#æternity-tokens-accounts-and-blocks)
  * [Access Token](#æternity-access-token)
  * [Access Aeon](#æternity-access-aeon)
  * [Name System](#æternity-name-system)
  * [Block Contents](#æternity-block-contents)
* [State Channels](#æternity-state-channels)
  * [Smart Contracts](#æternity-smart-contracts)
    * [Contract interaction and multi-step contracts](#æternity-contract-interaction-and-multi-step-contracts)
    * [Metered Execution](#æternity-metered-execution)
    * [æternity State Channel Example](#æternity-state-channel-example)
* [Consensus Mechanism](#æternity-consensus-mechanism)
  * [Oracles](#æternity-oracles)
* [Governance](#æternity-governance)
* [Scalability](#æternity-scalability)
  * [Sharding trees](#æternity-sharding-trees)
  * [Light clients](#æternity-light-clients)
  * [State channels and parallelism](#æternity-state-channels-and-parallelism)
  * [Transactions per second at a given memory requirement](#æternity-transactions-per-second-at-a-given-memory-requirement)
* [Applications](#æternity-applications)
  * [Blockchain Essentials](#æternity-blockchain-essentials)
    * [Identities](#æternity-identities)
    * [Proof of Existence](#æternity-proof-of-existence)
  * [State channel applications](#æternity-state-channel-applications)
    * [Toll API](#æternity-toll-api)
    * [Insured crowdfunding](#æternity-insured-crowdfunding)
    * [Cross-chain atomic swaps](#æternity-cross-chain-atomic-swaps)
    * [Stable value assets and portfolio replication](#æternity-stable-value-assets-and-portfolio-replication)
    * [Event contracts](#æternity-event-contracts)
      * [Insurances](#æternity-insurances)
      * [Whistleblowing](#æternity-whistleblowing)
    * [Prediction markets](#æternity-prediction-markets)
      * [Multidimensional prediction markets](#æternity-multidimensional-prediction-markets)
      * [Market with batch trading at a single price](#æternity-market-with-batch-trading-at-a-single-price)
* [Implementation](#æternity-implementation)
  * [Virtual machine and contract language](#æternity-virtual-machine-and-contract-language)
  * [Adoption via web-integration](#æternity-adoption-via-web-integration)
  * [Open source modules](#æternity-open-source-modules)
  * [Usability and UX design](#æternity-usability-and-ux-design)
* [Disscussion and Idea-Box Solutions](#æternity-disscussion-and-idea-box-solutions)
  * [Limitations and tradeoffs](#æternity-limitations-and-tradeoffs)
    * [On-chain state](#æternity-on-chain-state)
    * [Free option problem](#æternity-free-option-problem)
    * [Liquidity loss and state channel topologies](#æternity-liquidity-loss-and-state-channel-topologies)
  * [Future work](#æternity-future-work)
    * [Functional contract language](#æternity-functional-contract-language)
    * [Multi-party channels:](#æternity-multi-party-channels)

* [Sources](#sources)

***

## Abstract

Abstract--- Since the introduction of Ethereum in 2014 there has been
great interest in decentralized trustless applications (smart
contracts). Consequently, many have tried to implement applications with
real world data on top of a blockchain. We believe that storing the
application's state and code on-chain is wrong for several reasons.

We present a highly scalable blockchain architecture with a consensus
mechanism which is also used to check the oracle. This makes the oracle
very efficient, because it avoids layering one consensus mechanism on
top of another. State channels are integrated to increase privacy and
scalability. Tokens in channels can be transferred using purely
functional smart contracts that can access oracle answers. By not
storing contract code or state on-chain, we are able to make smart
contracts easier to analyze and faster to process, with no substantial
loss in de facto functionality.

Applications like markets for synthetic assets and prediction markets
can be efficiently implemented at global scale. Several parts have
proof-of-concept implementations in Erlang. Devel- opment tools and
application essentials such as a wallet, naming and identity system will
also be provided.


[☝](#)

***

## Introduction

White Paper section: I

The intention of this paper is to give a overview of the Æternity
blockchain architecture and possible applica- tions. More detailed
papers will be released in the future, specifically for the consensus
and governance mechanisms. However, it should be noted that our
architecture is holistic; all components tie together and synergize, in
a modular way.

The rest of this paper is broken into four parts. First, we will
introduce and discuss the fundamental theoretical ideas that inform our
architecture. Second, we will discuss the included essential
applications, other possible use cases and give intuitions for how to
use the platform as a developer. Third, we will present the current
proof-of-concept imple- mentation, written in Erlang. We conclude with a
discussion, including possible future directions and comparisons to
other technologies.

[☝](#)

***

## Previous Work

White Paper section: I.A

Blockchains, first of all Bitcoin, have shown a new way to architect
value exchange on the Internet [1](#sources). This has been followed by
a number of promising advances: Ethereum demonstrated a way to write
Turing-complete smart con- tracts secured by a blockchain architecture
[2](#sources); Truthcoin created tools for making oracles on blockchains
[3](#sources), while GroupGnosis and Augur showed how to make them more
efficient [4](#sources); Casey Detrio showed how to make markets on
blockchains [5](#sources); Namecoin showed how to make the distributed
equivalent of a domain name server [6](#sources); Factom showed how a
blockchain that stores hashes can be used as a proof of existence for
any digital data [7](#sources).

These technologies show great promise when it comes to providing
first-class financial and legal services to anyone. So far however, they
have failed to come together to a unified whole that actually fulfills
the promise. Specifically, all solutions so far have been lacking in at
least one of the following respects: governance, scalability, scripting
safety and cheap access to real-world data [need cit.]. Æternity aims to
improve the state of the art in all of these respects.

***

## æternity Tokens, accounts and blocks

White Paper section: II A


[☝](#)

***

### æternity Access Token

White Paper section: II A.1

[☝](#)

***

### æternity Access Aeon

White Paper section: II A.1

[☝](#)

***

### æternity Accounts

White Paper section: II A.2


[☝](#)

***

### æternity Name System

White Paper section: II A.3


[☝](#)

***

### æternity Block Contents

White Paper section: II A.4

[☝](#)

***
***


## æternity State Channels

White Paper section: II B


[☝](#)

***

### æternity Smart Contracts

White Paper section: II B.1


[☝](#)

***

### æternity Contract interaction and multi-step contracts

White Paper section: II B.1 a)

[☝](#)

***

### æternity Metered Execution

White Paper section: II B.1 b)

[☝](#)

***

### æternity State Channel Example

White Paper section: II B.2)

[☝](#)

***
***


## æternity Consensus Mechanism

White Paper section: II C

[☝](#)

***

### æternity Oracles

White Paper section: II C.1

[☝](#)

***
***


## æternity Governance

White Paper section: II D

[☝](#)

***
***


## æternity Scalability

White Paper section: II E

[☝](#)

***

### æternity Sharding trees

White Paper section: II E.1

[☝](#)

***

### æternity Light clients

White Paper section: II E.2


[☝](#)

***

### æternity State channels and parallelism

White Paper section: II E.3


[☝](#)

***

### æternity Transactions per second at a given memory requirement

White Paper section: II E.4


[☝](#)

***
***


## æternity Applications

White Paper section: III


[☝](#)

***

### æternity Blockchain Essentials

White Paper section: III A


[☝](#)

***

### æternity Identities

White Paper section: III A.1


[☝](#)

***

### æternity Wallet

White Paper section: III A.2


[☝](#)

***

### æternity Proof of Existence

White Paper section: III A.3

[☝](#)

***

## æternity State channel applications

White Paper section: III B


[☝](#)

***

### æternity Toll API

White Paper section: III B.1


[☝](#)

***

### æternity Insured crowdfunding

White Paper section: III B.2


[☝](#)

***

### æternity Cross-chain atomic swaps

White Paper section: III B.3


[☝](#)

***

### æternity Stable value assets and portfolio replication

White Paper section: III B.4


[☝](#)

***

### æternity Event contracts

White Paper section: III B.5


[☝](#)

***

### æternity Insurances

White Paper section: III B.5 a)


[☝](#)

***

### æternity Whistleblowing

White Paper section: III B.5 b)


[☝](#)

***

## æternity Prediction markets

White Paper section: III B.6


[☝](#)

***

### æternity Multidimensional prediction markets

White Paper section: III B.6 a)


[☝](#)

***

### æternity Market with batch trading at a single price

White Paper section: III B.7


[☝](#)

***

## æternity Implementation

White Paper section: IV


[☝](#)

***

### æternity Virtual machine and contract language

White Paper section: IV A


[☝](#)

***

### æternity Adoption via web-integration

White Paper section: IV B


[☝](#)

***

### æternity Open source modules

White Paper section: IV C


[☝](#)

***

### æternity Usability and UX design

White Paper section: IV D


[☝](#)

***

## æternity Disscussion and Idea-Box Solutions

White Paper section: V


[☝](#)

***

### æternity Limitations and tradeoffs

White Paper section: V A


[☝](#)

***

### æternity On-chain state

White Paper section: V A.1


[☝](#)

***

### æternity Free option problem

White Paper section: V A.2


[☝](#)

***

### æternity Liquidity loss and state channel topologies

White Paper section: V A.3


[☝](#)

***

## æternity Future work

White Paper section: V B


[☝](#)

***

### æternity Functional contract language

White Paper section: V B.1


[☝](#)

***

### æternity Multi-party channels:

White Paper section: V B.2


[☝](#)

***

[☝](#)

***

related: [æternity DApp Development](æternity-DApp-Development) [☝](#)

***

## REFERENCES:

| No | Name                                       | Title / Link                                                                                                                   |                                                                                                                                             |
|:---|:-------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | S. Nakamoto                                | "Bitcoin: A peer-to-peer electronic cash system," 2008.                                                                        | [link](https://bitcoin.org/bitcoin.pdf)                                                                                        |
| 2  | V. Buterin                                 | "Ethereum: A next-generation smart contract and decentralized application platform," 2014.                                     | [link](https://github.com/ethereum/wiki/wiki/White-Paper)                                                                      |
| 3  | P. Sztorc                                  | "Market empiricism,"                                                                                                           | [link](http://bitcoinhivemind.com/papers/1_Purpose.pdf)                                                                        |
| 4  | M. Liston and M. Koppelmann                | "A visit to the oracle," 2016.                                                                                                 | [link](https://blog.gnosis.pm/a-visit-to-the-oracle-fefc9dec5462)                                                              |
| 5  | C. Detrio                                  | "Smart markets for smart contracts," 2015.                                                                                     | [link](http://cdetr.io/smart-markets/)                                                                                         |
| 6  | many                                       | Namecoin wiki, 2016.                                                                                                           | [link](https://wiki.namecoin.org/index.php?title=Welcome)                                                                      |
| 7  | P. Snow, B. Deery, J. Lu,et al.            | "Factom: Business processes secured by immutable audit trails on the blockchain," 2014.                                        | [link](http://bravenewcoin.com/assets/Whitepapers/Factom-Whitepaper.pdf)                                                       |
| 8  | J. Peterson and J. Krug                    | "Augur: A decentralized, open-source platform for prediction markets," 2014.                                                   | [link](http://bravenewcoin.com/assets/Whitepapers/Augur-A-Decentralized-Open-Source-Platform-for-Prediction-Markets.pdf) |
| 9  | A. Swartz                                  | "Squaring the triangle: Secure, decentralized, human-readable names," 2011.                                                    | [link](http://www.aaronsw.com/weblog/squarezooko)                                                                              |
| 10 | T. Hvitved                                 | "A Survey of Formal Languages for Contracts," inFormal Languages and Analysis of Contract-Oriented Software, 2010, pp. 29--32. | [link](http://www.diku.dk/hjemmesider/ansatte/hvitved/publications/hvitved10flacosb.pdf)                                       |
| 11 | R. C. Merkle                               | Protocols for public key cryptosystems,"                                                                                       | inIEEE Symposium on Security and Privacy, 1980.                                                                                             |
| 12 | V. Buterin                                 | "Proof of stake: How I learned to love weak subjectivity," 2014.                                                               | [link](https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/)                                       |
| 13 |                                            | "Schema.org schemas," 2016.                                                                                                    | [link](http://schema.org/docs/schemas.html)                                                                                    |
| 14 |                                            | "Atomic-cross-chain-trading," 2016.                                                                                            | [link](https://en.bitcoin.it/wiki/Atomic%5C_cross-chain%5C_trading)                                                            |
| 15 |                                            | "Interledger," 2016.                                                                                                           | [link](https://interledger.org)                                                                                                |
| 16 | K. J. Arrow, R. Forsythe, M. Gorham,et al. | "The promise of prediction markets,"Science, 320 2008                                                                          | [link](http://mason.gmu.edu/˜rhanson/PromisePredMkt.pdf)                                                                       |
| 17 | Z. Hess                                    | "Chalang," 2016.                                                                                                               | [link](https://github.com/aeternity/chalang)                                                                                   |
| 18 | White Paper V 0.1                          | [æternity whitepaper](https://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf)                                |                                                                                                                                             |

[☝](#)

***
