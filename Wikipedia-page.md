AEternity
From Wikipedia, the free encyclopedia

[hide]This article has multiple issues. Please help improve it or discuss these issues on the talk page. (Learn how and when to remove these template messages)
This article possibly contains original research. (April 2017)
This article relies too much on references to primary sources. (April 2017)
This article's use of external links may not follow Wikipedia's policies or guidelines. (April 2017)
This article is an orphan, as no other articles link to it. Please introduce links to this page from related articles; try the Find link tool for suggestions. (May 2017)
æternity
Developer(s)	æternity team
Initial release	29 October 2016
Development status	Under development
Written in	Erlang, JavaScript, HTML, React
Operating system	Linux, Ubuntu
Platform	x86, ARM
Type	Decentralized computing
License	Multiple open-source licenses
Website	www.aeternity.com
æternity is a new type of open-source, public, Blockchain-based distributed computing platform that innovates and expands upon existing platforms such as Bitcoin, Ethereum, and Augur. Real-world data can interface with smart contracts through decentralized oracles.True scalability and trust-less Turing-complete state channels sets æternity apart from all other Blockchain 2.0 projects[1].

It provides a decentralised virtual machine which can execute scripts using an international network of public nodes all connected to the Blockchain and through state channels. æternity also provides a value token called "aeon", which can be transferred between participants and is used to compensate participant nodes for computations performed. aeon, is used to pay for space and computation time on the Virtual-Machine and prevents spam on the network while allocating resources (Storage & Computaion time) proportionally to the incentive offered by the request.

Contents  [hide] 
1	Purpose
2	Innovation
3	Team
4	Technology
4.1	State Channels
4.2	Decentralized Oracle
5	Mining
5.1	Proof-Of-Work Mining
5.2	Proof-Of-Stake Mining (Oracle)
6	Governance
7	Uses cases
7.1	Prediction Markets
7.2	DocOræcle
7.2.1	Use Case Flow
7.2.2	Target audiences
7.3	Supply Chain Management
7.4	Digital insurance
7.5	Toll API
7.6	Insured (and Trust-less) crowdfunding
7.7	Cross-chain atomic swaps
7.8	Stable value assets and portfolio replication
8	References
9	External links
Purpose[edit source]
æternity's Blockchain architecture with a Hybrid Proof-of-Work & Proof of Stake consensus mechanism. is primarily built for privacy and scalability. Tokens in channels can be transferred between parties of a smart-contract without storing the code on-chain, which will enable Enterprise and private use of the state channels (without disclosure of the activities) . This huge throughput and speed enabled, will power be the main vector of micro and nano-transactions needed for all internet-of-things use cases. In the same time this will make smart contracts easier to analyze and faster to process, with no substantial loss in functionality[2].

æternity has held a first successful contribution campaign round in which the team was able to raise 121,212 Ethers and  324 Bitcoins, the rough equivalent of 12,500,00 USD at the time[3].

A second round is scheduled for 29 May 2017, in which the team's ambition is to raise a maximum capped amount of 21,000,000 CHF (Swiss Francs) roughly equivalent of 21,500,00 USD.

æternity has a working test-net as of February 2017[4], which is the stepping stone for the launch of the æternity Main-net which is scheduled for Q1 2018.

Innovation[edit source]
æernity is a next-level, brand new Blockchain technology in the making, with many features that tackle current issues and short-comings of Blockchain systems. It provides such innovations as [5]:

Industrial grade code base. æternity core is written in Erlang [6]. This is the perfect language choice to write a Blockchain from scratch allowing to achieve superior operational stability and performance [7][8].
Stateless smart contracts. This allows to write distributed, fault-tolerant [9], soft real-time and highly available non-stop applications.
State channels enable highly scalable, trust-less transactions of value [10] and purely functional, easily verifiable Turing-complete smart contracts.
Integrated Name System (DNS). This represents an easy to use name system, that is both decentralized and secure, while still supporting human-friendly, memorable names.
Oracles [11]. A crucial feature for most contracts, whether encoded as text or as code, is the ability to refer to values from the outside environment and real-world data. The æternity Oracle Machine provides real-world data to the smart-contracts in way that is closely integrated into the Blockchain.
Identity Accounts. Allows to create and own identity on the æternity network - then use it on the web, in real life, or voting systems.
Cuckoo Cycle mining algorithm[12] . This is a new memory-efficient mining algorithm that solves ASIC problem[13] that is relevant for Proof of Work based Bockchains, and that provides great decentralization potential. Anyone can efficiently mine even through low powered devices such as smart-phones[14].
Team[edit source]
æternity is a project still under development[15] by an experienced team of twelve people :

Yanislav Malahov - Founder: Having exchanged ideas and pursued Blockchain endeavors with many of the greatest minds, Yanislav is a true veteran of the blockchain space. The "Godfather of Ethereum"[16] envisioned in 2013 to have powerful algorithms on blockchains. Now, with æternity, a new version of his vision is becoming reality again.
Zack Hess - Technical Lead: Zack writes blockchains and is a true visionary. His first "basic coin" was the attempt to write the most compact Blockchain. Years later, after having worked for Augur and built a few other Blockchains from scratch, he is now leading æternity's technical implementation.
Marion Vogel - Marketing & Operations:] Being intrigued by the magic of Blockchain technology since early 2014, Marion is especially interested in connecting the dots between technology and the growing community. Research on the socioeconomic impact, spreading the word and taking care of handling æternity's operations efficiently is where she performs best. Previously she worked in marketing & business development in Silicon Valley.
Nikola Stojanow - Business Development: As a multi-national Business Development Executive with experience working in Germany, Eastern Europe, MENA, Asia and Pacific, Nikola is the go-to person for Strategy and Business Development. He has developed and consulted numerous international projects for almost a decade and has recently been introduced to the unlimited possibilities of Blockchain technologies.
Vladislav Dramaliev - Marketing & Community: Digital marketing analyst and Bitcoin entrepreneur. Founder of BitHope.org, CryptoCrowd.org, and Bitcoin/Blockchain meetup in Sofia, Bulgaria. Co-Founder of the Bulgarian Bitcoin Association and the first website for bitcoin exchange in the country. Fascinated by technology, Bitcoin, Blockchains and the future. Member of MENSA.
Lior Zysman - Legal lead:Lior is a corporate lawyer advising startups and investors in the blockchain space. He is working on decentralized autonomous non profits (Runner-up at Consensus 2016 Hackathon), and is cofounder of the "DAO Tel Aviv" meetup group. Lior holds a Bachelor of Law and a B.A. in Business Administration, from Tel Aviv university.
Dan Verowski - Project manager: Born and raised in Berlin he started working as a Scrum Master in 2011, later becoming a Business Analyst, interfacing splendidly between thankful developers and content clients. Blended with his fast growing knowledge and interest in blockchain technologies and the Fintech industry in general, he supports the project management pillar of team æternity.
Jack Pettersson - Scientific Advisor: Computer science and blockchain enthusiast, looking for ways to combine the two. Advocate of functional programming and expressive type systems. Previously worked for Synereo to develop the language and VM of their blockchain, and spent his master's thesis arguing for the use of dependent types in smart contract development.
Louis Chang - Creative Advisor: Louis Chang is Co-founder and Creative Director of Proof of Work, The first creative design and communication agency working specifically with Blockchain companies. Particularly interested in Human computer interaction, design, education and behavioral patterns. Louis has a 12 year creative pedigree working for agencies such as Ogilvy, Saatchi and Saatchi, Blast Radius and JWT.
Julio Alexandro - Humanitarian Advisor: "Leonardo da Vinci of Fintech" (CoinTelegraph, 2016), is the Founder and CEO of Humanitarian Blockchain, an e-governance and human rights consultancy. Branded as “World’s #1" in decentralized political technologies, he lectured at United Nations, European Union, Google, and University of Cambridge on 2016. He has globalization and immigration studies from Sciences Po (Paris) and Cambridge and resides in London.
John Tromp - Advisor on POW "Cuckoo Cycle"[17]: Board Games and Artificial Intelligence, Algorithms, Complexity, Algorithmic Information Theory, Distributed Computing, Computational biology, and what not. Recently he has been designing a new Proof-of-Work system called "Cuckoo Cycle", which æternity Blockchain will be using. John is advising the æternity team on the integration of the "Cuckoo Cycle" mining algorithm.
Vincent Zhou - China Advisor: Founding partner of FinTech Blockchain Group [18], Vincent is an expert on digital currency trading and an active investor in blockchain industry. As an early adopter of blockchain technology and a KOL in China’s crypto community, Vincent is advising the aeternity team on China strategy.
Technology[edit source]
State Channels[edit source]
State channels[19] [20] are a new æternity development in blockchain technology. They are bases on the idea of payment channels, but expand a lot on it [21]. They also come from the realization that for most purposes only, the actors involved in a smart contract are required to know about it. Two (or more) actors lock a state in the Blockchain and then perform (signed) transactions between themselves, off-chain. The final state is then logged on the blockchain. If this end result is for some reason disputed, the series of signed off-chain transactions can be uploaded to the Blockchain for verification and/or dispute resolution[22].

The State Channel design [23][24] enables off-chain, or off-network, verification of data and smart contracts. This mechanism permits a high transactional throughput and parallel processing of smart contracts by allowing for their independence from the network [21]. Hence, æternity's strengths lie in the programability of complex relationships for large numbers of users and in the parallel handling of high volumes of products and information. State channels allow for increased privacy in a way that only the parties participating in a smart contract know about the contents of that smart contract. When a channel is settled on-chain, the only information being put onto the Blockchain is the end-result of the transactional value that was exchanged. No contract state is stored on-chain, so all channels are independent of each other. Transaction speed is limited only by bandwidth, so æternity's scalable smart contract systems improves upon all the centralized and de-centralized scaling solutions that are available today.

Decentralized Oracle[edit source]
An Oracle[11] is a mechanism that tells the Blockchain facts about the real-world we live in e.g. the weather today, the closing price of Apple shares on a particular date, any sports event outcome or even humans life events (Death, birth, ...) . æternity's oracle system[25] uses the same consensus mechanism as the æternity Blockchain itself which means that it does not require a separate consensus layer on top of the æternity main-net [26] (Like Augur or Gnosis[27] on top of Ethereum).

To launch an Oracle, any "æon" holder has to commit to answering a yes or no question (e.g. whether the price of an Apple share is above $200) and specify additional conditions such as the time frame in which the "æon" holder can answer that question. Then he has to deposit/commit a certain amount of "æons" which is proportional to the time frame during which the oracle will be operational.

When the time comes for the Oracle to supply an answer, the user who previously deposited his "æons", provides his answer on the question for free. If that proposition is not counter-claimed, his response is deemed to be the truth. If any other user wants to counter-claim the answer, he has to deposit an amount that is equivalent to the first user's deposit. In that event, the consensus mechanism for the æternity main-net will be used to decide on which is the correct answer. The user who supplied the false answer will have is "æons" burned, while the user saying the truth will get his deposit back, with a small profit.

Therefore, what is achieved is a decentralized Oracle system. The truth value of oracle answers, if in dispute, will be ultimately determined by the decentralized consensus system of the æternity network[28].

Mining[edit source]
Proof-Of-Work Mining[edit source]
The validation of block on the æternity Blockchain is done by a Proof-of-Work consensus mechanism, leveraging the "Cuckoo Cycle" Algorithm [29]. The "Cuckoo Cycle" PoW is more power efficient and indirectly useful, as it encourages the development of better random access memory (DRAM) chips [30]. Even low-power devices such as smartphones, tablets and laptops can efficiently mine new tokens. This will achieve an unparalleled decentralization and geographical distribution of the mining power, which will be crucial to the success of any Blockchain.

As such, æternity mining is designed to be more egalitarian and inclusive compared to crypto-currencies where mining is dominated by large mining entities which use application-specific integrated circuit ("ASIC") chips designed specifically to take advantage of a particular PoW algorithm. This wider distribution of the mining incentives will then contribute to even wider use and adoption of æternity[31] .

Proof-Of-Stake Mining (Oracle)[edit source]
Any "æon" holder can launch an oracle by committing to answering a yes/no question on the Blockchain. When doing so, they also need to specify the time-frame during which the question can be answered, which can start now or at any point in the future. The user that launches the oracle is also required to deposit "æon" in proportion to the length of the time-frame, which will be returned if the user supplies an answer that gets accepted as truth, otherwise it is burned. The Blockchain generates a unique identifier for the oracle that can be used to retrieve the answer once it is available. Once the time comes for the question to be answered, the user who launched the oracle can supply an answer for free. Once the oracle launcher has supplied an answer the other users have a set amount of time to submit counter-claims by depositing the same amount of "æon". If no counter-claims have been submitted by the end of the time-frame, the answer supplied by the user that launched the oracle is accepted as truth, and the deposit is returned. If any counter claims are submitted, then the consensus mechanism for blocks will be used to answer the oracle. This is more expensive, but since we know we can take at least one of the two safety deposits, we can use it [28].

While hardware requirements for creating a PoS miner will not be particularly high, it is important to have a Fixed IP address, as is the case with all other PoS cryptocurrencies.

Governance[edit source]
In public Blockchains currently (Bitcoin, Ethereum, ...) whenever a system upgrade needs to be done, a hard fork is required. This leads to heated discussions among all value holders. Even simple changes, like correcting an arbitrary set variables in the source code, painfully obvious in the block size debate in Bitcoin, or the “ DAO” issue in Ethereum [32] [33], seem to be very hard to agree on in a system where not all the users’ incentives are aligned with those of decision makers. This can cause deep Schisms in the community, which would sometime endanger the value and reliability of any Blockchain.

The problem here is that  the decision-making process for a protocol upgrade or change is not well defined, lacks transparency and more importantly, it still uses legacy mediums, like forums, discussion websites or even requires sometimes physical meetups to try to reach a consensud. It is neither decentralized and nor done on the Blockchain. æternity aims to improve this process and thus gain an important competitive advantage.

In fact, æternity’s governance system is part of the consensus. It will use prediction markets to function as efficiently and transparently as possible. This consensus mechanism is defined by a number of variables that determine how the system functions. Those can be updated by each new block. From how much it costs to make transactions or ask an Oracle, to modifications of fundamental parameters like the block time, block size and the number of new tokens created per block (Inflation). Since the oracle is incorporated in the Blockchain consensus mechanism, using its services will be very cheap, and will rely on the resilient architecture of the æternity Blockchain, and not on legacy systems that can be compromised[34].

By having prediction markets determine the value of variables that define the protocol, users can learn how to efficiently improve the protocol. Furthermore, predictions markets can facilitate potential hard forks decisions and help the community reach consensus about which version of the code to use. Each user chooses for himself which variable he seeks to optimize, but his default strategy would be to maximize the value of his holdings.

Prediction markets could be the solution to public Blockchain governance and allow for a novel way of organizing society and global economic interactions [35].

Uses cases[edit source]
Prediction Markets[edit source]
Prediction markets (Oracles) are one of the most anticipated use cases for Blockchains[36]. They can make possible the harnessing of the wisdom of the crowds in a decentralized and transparent manner for the first time[37].

Ethereum has Augur and Gnosis trying to build prediction markets on top of it, with each its different system and currency. æternity differentiates itself, by integrating the oracle into the blockchain consensus .

Any user may create an oracle by posing a question or statement, staking coins and providing a binary or a scaled answering option. æ coins can be used to acquire stakes of those specific outcomes. The more sure a user is about the outcome, the more stakes he may acquire and hence more likely (he thinks) the outcome will be correct. Applying the wisdom of the crowd to all participating users of the prediction market, it is possible to:

a) statistically predict the probability of a future event occurring

b) verify historic data from legacy systems or other Blockchains

c) verify API data from legacy systems or other Blockchains

Meaning any data outside the blockchain can be translated into a deterministic value that can be used in æternity smart contracts, making real-world data easily accessible and actionable [38].

And what is even better in æternity is that this source of information would come from inside the Blockchain, and not from an outside entity built on top of it. This makes the source of information more reliable, more decentralized and not relying on a 3rd Party company or entity (Like Augur and Gnosis) [39].

DocOræcle[edit source]
A platform for everyone to get meaningful medical advice, no matter the infrastructure or insurance policy. A platform for questions too sensible or personal to ask a doctor in person. Answering questions and participating in the prediction markets created by the medical Oracles should only be accessible to doctors with digitally signed degree. Furthermore Oracles may be fed information regarding symptoms diagnosis & can be combined with AI image recognition to offer diagnosis prediction.

Use Case Flow[edit source]
Raise questions: A question can be asked in a forum like interface, using æternity identity. Account info only revealed to professional who answers.
Get answers : An answer is provided in a state channel.
Ask follow up questions: Follow up questions may be asked in private state channels susequently.
Test answers in oracle: Any answer provided by the medical professional may be forwarded to an Oracle. The prediction market that emerges is open to professionals to reach a comprehensive diagnosis, comparable with visiting 20 doctors
Target audiences[edit source]
Persons struggling with sensible, personal medical problems or questions, or rare medical conditions.

Persons in need of fast medical advice, or suffering from psychological issues.

Supply Chain Management[edit source]
The supply chain management can be trusted to a smart-contract that is constantly interfacing with the Oracle on æternity. The demand for any product can be fed to the smart-contract through the Oracle. That will trigger the contract to send procurement orders to suppliers, and raw materials providers, taking into consideration the normal delays of each item in the procurement process. In the mean time, the smart-contract's information being fed through the Oracle can be regulated to increase or decrease the quantity of the orders in-real time, thus eliminating waste of material/overstocking of storage facilities.

High-level concept of Supply Chain Management (SCM) automation with Smart Contracts, Prediction Markets, and Oracles.

Digital insurance[edit source]
In order for insurance on the Blockchain to work, a few features must be technologically achievable [40]:

Identity of the insured: That can be attached to a unique address (an address in the case of the Bitcoin Blockchain or Human readable digital Identity ), the private key of which is protected by password and/or 2FA solution. User reputation can be fully managed on the Blockchain through digital identities (think electronic signatures). And that’s exactly what the “bookies” (insurers) need.
Insurer/bookie setting the odds: There must be a way of determining the odds of an event occurring and providing that information to users. How about a prediction market? Public Blockchain solutions existing today do not offer integrated prediction markets. This service can only be provided by “attached” systems, which leads to increased complexity and inefficiencies, raising the cost of use. In the case of Ethereum, a prediction market service may be provided by Augur or Gnosis. For Bitcoin, Hive-Mind is considered the most promising project.
What is a prediction market?

It is a market where users can bet on outcomes and/or set odds for markets their create themselves.

In æternity “Individuals might ‘bet’ on natural disaster, death, industry-killing technological innovations, crippling regulatory activities, pandemic, disruptive weather or any other events. The “bookie” which becomes the insurer in that case is anyone willing to bet on the outcome of an event by setting the odds, and paying in case they occur.

Then photographically-secured smart contracts eliminate any trust-related risk. If event “X” happens, as determined by the consensus of the Oracle machine, execution is immediate and irreversible. There is no room for interpreattion or selectivity in the enforcement of the insurance contract. That's why, the æternity Blockchain incorporates (in its core features) all that is required for a scalable, secure, stable, open and efficient insurance platform.

Toll API[edit source]
Most websites and servers APIs existing today are publicly available for anyone to call, or secured by a username-password–scheme or unique access tokens. The æternity payment channels allow for a new kind of API, where the requesting user would have to pay (Micro transaction) for every call to the API, possibly every HTTP-request. Paying to access an API solves the DDoS problem, by providing a counter incentive to sending large amounts of requests that are destined to overload the servers. It also makes it easier to build high-quality APIs that are always available, albeit for a small fee. API responses that require a payment are fundamental for the creation of as of yet impossible types of businesses and can play an important role in the emergence of the decentralized economy, the Internet-of-things and the internet-of-value. This also create strong incentives for information/technology owners to make otherwise private data publicly available, while getting paid for this information.

Insured (and Trust-less) crowdfunding[edit source]
Crowdfunding can be made trust-less and more transparent by using dominant assurance contracts. These are smart-contracts that are used to raise money for a public good, or any other commercial project. Part of the funds can be locked for development and other parts are locked to provide an ROI for investors.

The release of funds can be set on several milestones. Once a milestone is cleared and approved, the contract will release the funds allocated to that specific milestone. Several methods can be used to verify the completion including specific Oracles. If the Oracle concludes that the milestone is not reached, investors get their investments with interests back.

Dominant assurance contracts differ from traditional assurance contracts like Kickstarter, in that they make it a dominant strategy to participate. If the good is produced, all participants get their "æons" back plus interest, so they are insured against reducing their liquidity without receiving the good. Using an oracle, we can ensure that the provider of the good or service only gets paid if he provide the goods as promised.

This will enable a leap of transparency and trust-less investment opportunities in ICOs and startups , where the investors funds are safe from mismanagement or fraud by the project's founders.

This can also be implemented on any other exchange of services between multiple parties, thus decentralizing the freelancing and business-to-business sectors.

Cross-chain atomic swaps[edit source]
æternity's blockchain architecture can enable cross chain atomic swaps to allow for trust-less exchange of "æons" for bitcoins, or any other crypto-currencies. These can easily be implemented using a hashlock that locks the transactions on both blockchains under the same value. This will make the cross-chain exchange of currencies decentralized, without having to deal with the single point of failure of the current exchanges.

Stable value assets and portfolio replication[edit source]
æternity's smart-contracts can be used to program synthetic assets that stay nearly the same price as a real world asset. For example, we could make an asset that follows the price as gold. These synthetic derivatives will be created created in equal and opposite pairs. For one user to have an asset that moves up with gold, a different user will have to have an asset that move inversely to gold. This would basically enable the "Blockchainization" of all the real-world assets (or financial derivatives) , and their exchange in a decentralized stock-market. For example, Alice could make a contract with Bob so that Alice owns 1 gram of gold. Out of the money in the contract, one gram of gold worth of "æon" will go to Alice, and the leftover money goes to Bob. The contract has an expiration date at which point the price of gold will be re-measured, and the funds distributed to Alice and Bob accordingly.