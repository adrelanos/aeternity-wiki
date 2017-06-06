[Use Case Fantasies for æternity](#use-case-ideas-for-æternity)
===========================================================

* [Use Case Flow](#use-case-flow)
* [Target audiences](#target-audiences)
* [Requirements](#requirements)
* [Supply Chain Management](#supply-chain-management)
* [Prediction Markets](#prediction-markets)
* [Use Case Ideas 1](#use-case-ideas-1)
* [Gaming](#gaming)
* [Use Case Ideas 2](#use-case-ideas-2)
* [Insured (and Trust-less) crowdfunding](#insured-and-trust-less-crowdfunding)
* [Use Case Ideas 3](#use-case-ideas-3)
* [Micro- & Nano Payments](#micro---nano-payments)
* [Toll API](#toll-api)
* [Cross-chain atomic swaps](#cross-chain-atomic-swaps)
* [Stable value assets and portfolio replication](#stable-value-assets-and-portfolio-replication)

[Wiki Wishes](#the-wiki-wishes)
===============================

* [~Google Calendar Plug In~](#google-calendar-plug-in)
* [~Subpages~](#subpages)
* [Using Mediawiki format?](#using-mediawiki-format)
* [Migrating Zack's notes into wiki format](#migrating-zacks-notes-into-wiki-format)


***

# Use Case Ideas for æternity

#### Use Case Flow
1. Raise question
    * in a forum like interface, using æternity identity. Account info only revealed to professional who answers
2. Get answer
    * An answer is provided in a state channel
3. Ask follow up questions
    * follow up questions may be asked in private state channels
4. test answers  in oracle
    * any answer provided by the medical professional may be forwarded to an Oracle. The prediction market that emerges is open to professionals to reach a comprehensive diagnosis, comparable with visiting 20 doctors

#### Target audiences
* persons struggling with sensitive, personal medical problems or questions
  * person suffering from unknown medical condition
  * person in need of nutrition advice
  * person in need of homeopathic advice
  * person suffering from psychological stress

#### Requirements
* User interface
    * Question board and Oracle marketplace
* æternity identity
* Working state channels
* Pool of medical professionals
    * Only they are allowed to answer questions and participate in oracle

***

## Prediction Markets
> Prediction Markets (created with Oracles) are one of the most anticipated use cases for Blockchains. They can make possible the harnessing of the wisdom of the crowds in a decentralized and transparent manner for the first time.

[What's a Prediction Market?](Research-and-Theory#prediction-markets)

[What's and Oracle?](Understanding-Aeternity#what-is-an-oracle)

### Use Case Ideas 1
* Digital Insurance Marketplace - 'Bond of Trust' flattened into a simple product based on prediction market odds, tradeable on the digital marketplace to provide instant insurance by the hour.
* [Humanistic Use Cases ](https://github.com/aeternity/wiki/wiki/Humanistic-Use-Cases)

***
## Gaming
> [State channels](Research-and-Theory#state-channels) can be used through special nodes to play games using æon (AE). Either single player games, between friends, or even total strangers. æternity will enable trust-less gaming applications, where no player puts his trust into the other's infrastructure or central servers, but into the state channels of the æternity Blockchain.

[State Channel Info](Research-and-Theory#state-channels)

### Use Case Ideas 2
* [Humanistic Use Cases ](https://github.com/aeternity/wiki/wiki/Humanistic-Use-Cases)


***

##  Insured (and Trust-less) crowdfunding

Crowdfunding can be made trust-less and more transparent by using dominant assurance contracts. These are smart contracts that are used to raise money for a public good, or any other commercial project. Part of the funds can be locked for development and other parts are locked to provide an ROI for investors.

The release of funds can be set on several milestones. Once a milestone is cleared and approved, the contract will release the funds allocated to that specific milestone. Several methods can be used to verify the completion including specific Oracles. If the Oracle concludes that the milestone is not reached, investors get their investments with interests back.

Dominant assurance contracts differ from traditional assurance contracts like Kickstarter, in that they make it a dominant strategy to participate. If the good is produced, all participants get their "æons" back plus interest, so they are insured against reducing their liquidity without receiving the good. Using an Oracle, we can ensure that the provider of the good or service only gets paid if he provides the goods as promised.

This will enable a leap of transparency and trust-less investment opportunities in ICOs and startups, where the investors funds are safe from mismanagement or fraud by the project's founders.

This can also be implemented on any other exchange of services between multiple parties, thus decentralizing the freelancing and business-to-business sectors.

### Use Case Ideas 3
* [Humanistic Use Cases ](https://github.com/aeternity/wiki/wiki/Humanistic-Use-Cases)
* Kickstarter 2.0 (with a Money Back guarantee & milestone dependent release of funds)

***
## Micro- & Nano Payments
> æternity will be the preferred Blockchain for the Micro and Nano payments. No other Blockchain now can match the speed that's provided by æternity's [State channels](State-Channels).

Once such example of this use case is the roll-out of hundreds of charging stations for electric cars using  Ethereum in Germany. Innogy, a subsidiary of Germany’s energy giant RWE has added Blockchain capabilities to their E2E Product using asset-backed Crypto-EURO for payments in charging stations for electric vehicles.

> Because the idea here is for, eventually, the car itself to pay the charging station. How? The exact details would probably be closely guarded, but at a high level you can Blockchainize the car, give it a smart contract, connect it to wi-fi, and write some code which orders it to pay if:then, while:else etc.

The only problem with other blockchain solutions like Ethereum, is that storing all these micro-payments and contract information on-chain will soon lead to a bloating of the size of the chain, and render it virtually unusable. Here comes the æternity innovation, with [State channels](State-Channels).

Source: [Cryptocoinnews](https://www.cryptocoinsnews.com/hundreds-charging-stations-electric-cars-blockchenized-ethereum-germany/)

[State Channel Info](Research-and-Theory#state-channels)

## Toll API

Most website and server APIs existing today are publicly available for anyone to call or secured by a username-password–scheme or unique access tokens. The æternity payment channels allow for a new kind of API, where the requesting user would have to pay (Micro transaction) for every call to the API, possibly every HTTP-request. Paying to access an API solves the DDoS problem, by providing a counter incentive to sending large amounts of requests that are destined to overload the servers. It also makes it easier to build high-quality APIs that are always available, albeit for a small fee.

API responses that require a payment are fundamental for the creation of as of yet impossible types of businesses and can play an important role in the emergence of the decentralized economy, the Internet-of-things and the internet-of-value. This also creates strong incentives for information/technology owners to make otherwise private data publicly available, while getting paid for this information.

## Cross-chain atomic swaps

Cross-chain atomic swaps allow for a trust-less exchange of "æons" for bitcoins, or any other cryptocurrencies. These can easily be implemented using a hashlock that locks the transactions on both blockchains under the same value. This will make the cross-chain exchange of currencies decentralized, without having to deal with the single point of failure of the current exchanges.

## Stable value assets and portfolio replication

æternity's smart contracts can be used to program synthetic assets that stay nearly the same price as a real world asset. For example, we could make an asset that follows the price of gold. These synthetic derivatives will be created in equal and opposite pairs. For one user to have an asset that moves up with gold, a different user will have to have an asset that move inversely to gold. This would basically enable the "Blockchainization" of all the real-world assets (or financial derivatives) , and their exchange in a decentralized stock-market. For example, Alice could make a contract with Bob so that Alice owns 1 gram of gold. Out of the money in the contract, one gram of gold worth of "æon" will go to Alice, and the leftover money goes to Bob. The contract has an expiration date at which point the price of gold will be re-measured, and the funds distributed to Alice and Bob accordingly.

***

# The Wiki Wishes
## ~Google Calendar Plug In~

~It would be great to have a google calendar plug in, to have a comprehensive overview of meetups and events.
There is a [MediaWiki plug in](https://www.mediawikiwidgets.org/Google_Calendar) available, but don't know if it's working.~

Github wiki is not Mediawiki. Unlikely any plugins are supported here?

## ~Subpages~
~In order to better structure the content in the wiki, subpages would be very useful.
[Plug In](https://github.com/wikimedia/mediawiki-extensions-EditSubpages)~

Same as above - Mediawiki plugins not supported on Github.

## Using Mediawiki format?

Even though plugins are unlikely to be supported, the Mediawiki format is supported, see proposals on Bitcoin: https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki

## Migrating Zack's notes into wiki format

Over the months of development Zack has accumulated a lot of notes - https://github.com/aeternity/testnet/tree/master/docs - even though the folder name says `docs` it is more suited for `wiki` - a lot of use cases and great examples.
***