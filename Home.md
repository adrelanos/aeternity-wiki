<a href="http://www.aeternity.com/"><img width="160px" src="http://www.aeternity.com/user/themes/aeon/img/aeternity_logo.png" align="left" hspace="10" vspace="10"></a>

<p align = right><a target="_blank" href="https://twitter.com/intent/tweet?original_referer=https%3A%2F%2Fabout.twitter.com%2Fresources%2Fbuttons&text=Aeternity:%20scalable%20smart%20contracts%20interfacing%20with%20real%20world%20data&tw_p=tweetbutton&url=http%3A%2F%2Fwww.aeternity.com%2F&via=aetrnty"><img src="http://s30.postimg.org/j2q6ql27h/Tweet.png"></a>
<a target="_blank" href="https://twitter.com/aetrnty"> <img src="https://s24.postimg.org/4xcf9j8xh/Follow-_Twitter.jpg?2"></a>
</p>
<b>æternity Blockchain – A Functional Oracle Machine<p>

æternity is a [blockchain](https://en.wikipedia.org/wiki/Blockchain) protocol built from scratch in Erlang withspeed, efficiency and scalability in mind. It offers a unique hybrid [proof of work (PoW)](https://en.wikipedia.org/wiki/Proof-of-work_system) and [proof of stake (PoS)](https://en.wikipedia.org/wiki/Proof-of-stake) [consensus mechanism](https://www.ibm.com/developerworks/cloud/library/cl-blockchain-basics-intro-bluemix-trs/) that can be used to check [[oracles]], which maximizes their efficiency, as this prevents layering of consensus mechanisms on top of each other. [[State channels]] maximize scalability and privacy by removing the need to store smart-contract code on-chain. Transfer of [tokens](http://cruiserselite.co.in/downloads/btech/materials/second%20sem/4/e-com/UNIT-3.pdf) through channels is done by functional [smart contracts](https://en.wikipedia.org/wiki/Smart_contract) which have access to real-world data through the Oracle. æternity thus renders smart contracts faster, easier to execute, and more fault-tolerant, without degrading their performance or functionality.<p>

æternity's [white paper](https://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) was published to introduce this architecture and its potential use cases. æternity is built to be used on a global scale in [prediction markets](https://en.wikipedia.org/wiki/Prediction_market), [synthetic assets’ markets](https://syntheticassets.wordpress.com/) and [a variety of other use cases](https://github.com/aeternity/wiki/wiki/Idea-Box#use-case-ideas-for-%C3%A6ternity).<p>

<b>How Can æternity Blockchain Serve Smart Contract Platforms?<p>

There are three main problems that underlie the lack of sufficient scalability, coding safety and relatively inexpensive access to real-world data of the presently available smart contract platforms:<p>

<ol>
<li>The presently prevalent stateful design renders smart contracts, coded for smart contract platforms, rather hard to analyze. Moreover, combining statefefulness with sequential ordering of transactions reduces scalability.
<li>Introducing real-world data to smart contract platforms, in a trustless, decentralized and reliable manner significantly hurdles the realization of a large number of advantageous applications.
<li>Most smart contract platforms have limited abilities to update themselves to cope with newly emerging economic and technological knowledge.</ol><p>

Recent studies of the state channel technology have proven that, in many instances, storing state on-chain is unnecessary. In most cases, all data can be stored in state channels, and the blockchain would be only used to settle the economic results of exchange of information and/or to act as a fallout whenever a dispute occurs. This represents an alternative blockchain architecture approach, which is marked by [Turing-complete](https://en.wikipedia.org/wiki/Turing_completeness) smart contracts that exist in state channels but not on the blockchain. This would boost scalability as all transactions are independent and can be processed in parallel. Furthermore, this approach means that smart contracts will not write to [shared state](http://wiki.c2.com/?SharedStateConcurrency), which will greatly simplify contracts’ testing and verification.<p>

[Augur](https://en.wikipedia.org/wiki/Augur_(software)) is a decentralized prediction market that attempted to integrate real-world data with the blockchain in a decentralized manner via a process that implements a consensus mechanism on smart contracts, rather than implementing the consensus mechanism provided by the underlying blockchain. This will result in inefficiencies, yet it won’t boost security. So, it is logically better to generalize the consensus mechanism of the blockchain so that it can provide information on the next [internal state](https://www.cs.nmsu.edu/~rth/cs/cs177/map/intstate.html) as well as on the external world’s state. So, we can assume that the blockchain’s consensus mechanism dictates the outcome of executing what [complexity theory](https://en.wikipedia.org/wiki/Computational_complexity_theory) describes as an “[oracle machine](https://en.wikipedia.org/wiki/Oracle_machine)”. An oracle machine is a theoretical machine that is far more powerful than a [Turing machine](https://en.wikipedia.org/wiki/Turing_machine) due to the fact that it can bear answers to questions whose answers cannot be computed such as “Who won the Super Bowl in 2016?”<p>

<b>Overview and Applications of æternity:<p>

æternity is a blockchain protocol that is designed to solve all the aforementioned problems that are challenging smart contract platforms. æternity provides a highly efficient system for transferring value. Practically speaking, æternity represents a global oracle machine that can be utilized to provide decision making services on an enormous scale.<p>

The stateless nature of æternity’s smart contracts makes it ideal for building a myriad of applications including:<p>
1. Identities: Each account will be associated with a [unique ID number](https://en.wikipedia.org/wiki/Universally_unique_identifier). Users will be allowed to register distinctive names and link them to a data structure’s [Merkle](https://en.wikipedia.org/wiki/Merkle_tree) root.
2. Wallet: the [wallet](https://en.wikipedia.org/wiki/Wallet_(software)) manages the cryptocurrency, Aeon, [private keys](https://en.wikipedia.org/wiki/Public-key_cryptography), sends and signs transactions. It can also be used to create channel transactions and use apps within the channel network.
3. Toll API: Payment channels open the door to a novel type of APIs where a user can pay for every API request. [Toll APIs](https://en.wikipedia.org/wiki/AEternity#Toll_API) mitigate [DDoS](https://en.wikipedia.org/wiki/Distributed_denial-of-service_attacks_on_root_nameservers) problems and simplify the creation of high quality APIs.
4. Insured Crowdfunding: [Insured crowdfunding](https://en.m.wikipedia.org/wiki/Equity_crowdfunding#Crowdfunding_insurance) can be implemented via means of [dominant assurance contracts](https://en.wikipedia.org/wiki/Assurance_contract#Dominant_assurance_contracts), which are smart contracts that are created to raise money for a good cause.
5. Others: other possible applications include [cross-chain atomic swaps](https://en.bitcoin.it/wiki/Atomic_cross-chain_trading), event contracts (e.g. insurance, whistleblowing) and [prediction markets](https://en.m.wikipedia.org/wiki/Prediction_market).<p>

<i>Extracted from deepdotweb.com article by Tamer Sameeh from Feb 28, 2017. 

<b>æternity Launch

The Phase 1 "Friends, Family, and Real Innovators" contribution campaign ran for three days, beginning on April 3rd, 2017. In that time, contributors were able to purchase 1,100 AE for very ETH spent in the first 24 hours, and 1,000 AE per ETH thereafter. The first thousand who contributed 12 ETH or more were also entitled to a limited edition æternity branded Ledger Nano S hardware wallet. In this time period, 2466 contributers generated 139,099,689.485 AE through total contributions of 121,265.614 ETH and 323.5482 BTC. At current fiat to cryptocurrency conversion rates (as of 5/23/17), the USD value translates to $733,736.14 in BTC and $21,955,139.41 in ETH, totaling $22,688,875.55.

Phase 2, the "Early Adopter" round, which begins on May 29th, will be open for three full weeks - or until contributions reach the cap of twenty one million Swiss Franks (CHF). This round will allow contributors to purchase 800 AE for each ETH contributed over the first 24 hours, 750 over the remainder of the first week, 700 AE per ETH over the second week, and 650 ETH over the third week. As in the first round, BTC will also be accepted.

Contributors will be able to use their AE after Phase 2 is complete (most probably in the form of an ERC20 token on the Ethereum network).

The contributor portion will comprise eighty-two percent of the initial æternity AE tokens. Seventeen percent of funds will be allocated to Aeternity Anstalt, the foundation and the founding team, and one percent will be allocated to those who hold BTC or ETH, accessible when the æternity blockchain launches. 

All will be recorded on the ETH blockchain by a standard multisig-escrow-contract. The AE tokens for the team will be time-locked.

https://blog.aeternity.com/security-transparency-simplicity-1411fad10974

## Learn More
[æternity Wikipedia page](https://en.wikipedia.org/wiki/AEternity).

The dedicated Wiki channel on Slack is [HERE](https://pacific-beach-20900.herokuapp.com/), feel free to join us!
_This will be rapidly expanded._

[Whitepaper_English]: Whitepaper_English
[Whitepaper_Korean (한국어)]: Whitepaper_Korean-(한국어)
[Whitepaper_Indonesia]: Whitepaper_Indonesia
[Whitepaper_French]: Whitepaper_French
[Whitepaper_Chinese]: Whitepaper_Chinese
[Whitepaper_Russian]: Whitepaper_Russian
[Whitepaper_Español]: Whitepaper_Español
[Whitepaper_Japanese]: Whitepaper_Japanese