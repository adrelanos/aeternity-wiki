# Examples and Tutorials (Whitepaper based)

>Stay tuned! We will fill this page with all your needs, from time to
>time. Note! æternity is still under development! We were creating this
>draft page to not forget something! Note that this is a draft and will
>change likely!


II. æTERNITY BLOCKCHAIN

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


I will show an example. I will show Satoshi Dice written in 3 different styles. The first is a forth compiler. It is very close to the VM. It is the most efficient of the 3, but hardest to read and write.

```
macro Amount int 1000 ;
macro Draw int 1 int 0 int 0 crash ;
: or_die not if Draw else then ;
macro reveal ( Reveal Commit -- bool )
  swap dup tuck hash == or_die call drop drop ;
macro Win1 int 0 Amount ; 
macro Win2 int 1 Amount ; 
macro player1revealed Commit1 reveal drop int 2 Win1 ;
macro player2revealed Commit2 reveal drop int 2 Win2 ;
macro bothRevealed Secret2 reveal swap
          Secret1 reveal bxor int 2 rem
	  int 3 swap
	  if Win1 else Win2 then ;
%syntax for case statements.
macro -> == if drop drop ;
macro -- crash else then drop ;
macro main
  int 1 -> player1revealed -- 
  int 2 -> player2revealed --
  int 3 -> bothRevealed --
  drop Draw ;
```
Here are the 4 ways this program can be run:
```
     int 0 main ;
     (choose path 0, so neither player revealed. It is a tie. The nonce is 1.)

     int 1 int 1 main ;
     (choose path 1, meaning only player 1 revealed their secret. So player 1 wins. The secret happens to be 1. The nonce is 2.)

     int 2 int 2 main ;
     (choose path 2, meaning only player 1 revealed their secret. So player 2 wins. The secret happens to be 2. The nonce is 2)

     int 1 int 2 int 3 main;
     (choose path 3, so both revealed. the secrets are 1 and 2. The winner will be selected by XORing the secrets. The nonce is 3.)
```

Next I will show what this program looks like written in lisp. The lisp compiler is mostly functioning now.

```
(set amount 1000)
(macro Draw () (end 1 0 0))
(define or_die (B)
	(cond ((B ())
	       (true (Draw)))))
(macro reveal (Secret Commit)
	(or_die (= Commit (hash Secret))))
(macro (win Player Nonce) (end Nonce Player amount))
(macro (playerRevealed Player Secret)
       (do (reveal Secret (commit player))
           (win Player 2)))
(macro (bothRevealed Secret1 Secret2)
       (do (reveal Secret1 (commit 0))
       	   (reveal Secret2 (commit 1))
	   (win (rem (bxor Secret1 Secret2)
	   	     2)
		3)))
(define main (Secret1 Secret2 mode)
	(cond
		(((== mode 1) (playerRevealed 0 Secret1))
		 ((== mode 2) (playerRevealed 1 Secret2))
		 ((== mode 3) (bothRevealed Secret1 Secret2))
		 (true (Draw)))))
		 
```

Finally, I will show how this program will look in the final language I am aiming to create.

```
-define(amount, 1000).
one_reveal(Secret) ->
     N = or(0, 1),
     Commit(N) = hash(Secret),
     end(2, N, ?amount).
both_reveal(Secret1, Secret2) ->
     Commit(0) = hash(Secret1),
     Commit(1) = hash(Secret2),
     C = rem(bxor(Secret1, Secret2) 2),
     end(3, C, ?amount).
doit() ->
     or(both_reveal(),
        one_reveal(),
        end(1, 0, 0)).
```

This final one is a prolog-like language with backtracking.
the "or" function does the backtracking. If an "=" sign doesn't match equality, then it triggers a backtracking event.
This version will be about 3-5 times more expensive than the original.

Although it is more expensive, I feel like we should support this third version primarily.
It is much easier to tell what it does from looking at it in comparison to the other two.
Making the code easy to read is our main goal.

Eventually we should also make custom types, and add static type
checking to all the functions. This would give us lots of nice error
messages to make programming easier.

Source: [ZACK-CHLANG-DOCS](https://github.com/BumblebeeBat/chalang/blob/master/docs/why.md)
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


***
***


related: [æternity DApp Development](æternity-DApp-Development)

***

## Sources:

| No | Type              | Source                                                                                          |
|:---|:------------------|:------------------------------------------------------------------------------------------------|
| 1  | White Paper V 0.1 | [æternity whitepaper](https://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) |
