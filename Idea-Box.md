# Wiki Wishes
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

# Use Case Ideas for æternity

## Health & æternity 

### DocOræcle
A platform for everyone to get meaningful medical advice, no matter the infrastructure or insurance policy. A platform for questions too sensible or personal to ask a doctor in person. 
Answering questions and participating in the prediction markets created by the medical Oracles should only be accessible to doctors with digitally signed degree. 
[Furthermore Oracles may be fed information regarding symptoms diagnosis & can be combined with AI image recognition to offer diagnosis prediction.]

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
* persons struggling with sensible, personal medical problems or questions
  * person suffering from unknown medical condition 
  * person in need of nutrition advice
  * person in need of homeopathic advice
  * person suffering from psychological stress

#### Requirements
* User interface
    * Question board and Oracle marketplace
* æternity identity
* Working state channels
* Pool of medicinal professionals
    * Only they are allowed to answer questions and participate in oracle

***

## Supply Chain Management

The supply chain management can be trusted to a smart-contract that is constantly interfacing with the Oracle on æternity.
The demand for any product can be fed to the smart-contract through the Oracle. That will trigger the contract to send procurement orders to suppliers, and raw materials providers, taking into consideration the normal delays of each item in the procurement process. In the mean time, the smart-contract's information being fed through the Oracle can be regulated to increase or decrease the quantity of the orders in-real time, thus eliminating waste of material/overstocking of storage facilities. 

High-level concept of Supply Chain Management (SCM) automation with Smart Contracts, Prediction Markets, and Oracles.

![SCM automation (high level)](http://i67.tinypic.com/1112pw4.png)

## Prediction Markets
> Prediction Markets (created with Oracles) are one of the most anticipated use cases for Blockchains. They can make possible the harnessing of the wisdom of the crowds in a decentralized and transparent manner for the first time.

[What's a Prediction Market?](Research-and-Theory#prediction-markets)

[What's and Oracle?](Understanding-Aeternity#what-is-an-oracle)  

### Use Case Ideas 
* Digital Insurance Marketplace - 'Bond of Trust' flattened into a simple product based on prediction market odds, tradable on the digital marketplace to provide instant insurance by the hour.
* [Humanistic Use Cases ](https://github.com/aeternity/wiki/wiki/Humanistic-Use-Cases)

***
## Gaming
> [State channels](Research-and-Theory#state-channels) can be used through special nodes to play games using æon (AE). Either single player games, between friends, or even total strangers. æternity will enable trust-less gaming applications, where no player puts his trust into the other's infrastructure or central servers, but into the state channels of the æternity Blockchain.

[State Channel Info](Research-and-Theory#state-channels)  

### Use Case Ideas 
* [Humanistic Use Cases ](https://github.com/aeternity/wiki/wiki/Humanistic-Use-Cases)


***  

##  Insured (and Trust-less) crowdfunding

Crowdfunding can be made trust-less and more transparent by using dominant assurance contracts. These are smart-contracts that are used to raise money for a public good, or any other commercial project. Part of the funds can be locked for development and other parts are locked to provide an ROI for investors.

The release of funds can be set on several milestones. Once a milestone is cleared and approved, the contract will release the funds allocated to that specific milestone. Several methods can be used to verify the completion including specific Oracles. If the Oracle concludes that the milestone is not reached, investors get their investments with interests back.

Dominant assurance contracts differ from traditional assurance contracts like Kickstarter, in that they make it a dominant strategy to participate. If the good is produced, all participants get their "æons" back plus interest, so they are insured against reducing their liquidity without receiving the good. Using an oracle, we can ensure that the provider of the good or service only gets paid if he provide the goods as promised.

This will enable a leap of transparency and trust-less investment opportunities in ICOs and startups , where the investors funds are safe from mismanagement or fraud by the project's founders.

This can also be implemented on any other exchange of services between multiple parties, thus decentralizing the freelancing and business-to-business sectors.

### Use Case Ideas 
* [Humanistic Use Cases ](https://github.com/aeternity/wiki/wiki/Humanistic-Use-Cases)
* Kickstarter 2.0 (with a Money Back guarantee & milestone dependent release of funds)
  
***
## Micro- & Nano Payments
> æternity will be the preferred Blockchain for the Micro and Nano payments. No other Blockchain now can match the speed that's provided by æternity's [State channels](State-Channels).

Once such example of this use case is the roll-out of hundreds of charging stations for electric cars using  Ethereum in Germany. Innogy, a subsidiary of Germany’s energy giant RWE has added Blockchain capabilities to their E2E Product using asset-backed Crypto-EURO for payments in charging stations for electric vehicles. 

> Because the idea here is for, eventually, the car itself to pay the charging station. How? The exact details would probably be closely guarded, but at a high level you can Blockchainize the car, give it a smart contract, connect it to wi-fi, and write some code which orders it to pay if:then, while:else etc.

The only problem with other Blockchains solutions like Ethereum, is that storing all these micro-payments and contracts information on-chain will lead very soon to a bloating of the size of the chain, and render it virtually unusable. Here comes the æternity innovation, with [State channels](State-Channels).

Source: [Cryptocoinnews](https://www.cryptocoinsnews.com/hundreds-charging-stations-electric-cars-blockchenized-ethereum-germany/)

[State Channel Info](Research-and-Theory#state-channels)  

## Toll API

Most websites and servers APIs existing today are publicly available for anyone to call, or secured by a username-password–scheme or unique access tokens. The æternity payment channels allow for a new kind of API, where the requesting user would have to pay (Micro transaction) for every call to the API, possibly every HTTP-request. Paying to access an API solves the DDoS problem, by providing a counter incentive to sending large amounts of requests that are destined to overload the servers. It also makes it easier to build high-quality APIs that are always available, albeit for a small fee.

API responses that require a payment are fundamental for the creation of as of yet impossible types of businesses and can play an important role in the emergence of the decentralized economy, the Internet-of-things and the internet-of-value. This also create strong incentives for information/technology owners to make otherwise private data publicly available, while getting paid for this information.



***