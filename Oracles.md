# Introduction

## What are Oracles?

An Oracle teaches blockchain about true facts of our world.
It does so by creating a prediction market for each question.
Each market consists of three different types of shares/stakes: 'yes', 'no' and 'faulty question'.


# æternity Oracles

## How do æternity oracles function?

Anyone with access to AE tokens can ask questions or participate in a market.
(All shares/stakes are matched in pairs at 50/50 odds)
(A high number of unmatched shares/stakes means that this answer will likely be true)
Once the Oracle settles a question (after a specific time length or upon a specific date or event) the shares/stakes become of the correct answer become profitable, stakes/shares from the incorrect answer become worthless.
More precise:
The winning bets in the Oracle become positive shares, which pay out if the difficulty is high.
The losing bets become negative shares, which pay out if the difficulty is low. 
The positive shares are profitable if the difficulty is high.  

Accordingly, every single oracle answer every given resides on æternity's Blockchain.

![Governance on æternity](https://github.com/aeternity/wiki/blob/master/images/%C3%86_101_Governance.png)

## Users and the oracle
In the context of the æternity Oracle, until now there are three types of roles to be found in a prediction market:

+ Creator: asks question, pay: a) fee for transaction (burned!) ; b) fee for account that closes Oracle ; c) last loosing bet in the book (as an initial incentive for others to participate in the market)
+ Participant: acquiring shares/stakes on prediction markets
+ Terminator/Closer: closes Oracle -> if only 1 type of shares exist for a certain amount of time, the oracle can be closed

Additional roles conceivable with the following concept:
+ funding the creation of an Oracle question with a dominant assurance contract https://github.com/aeternity/wiki/wiki/Idea-Box#insured-and-trust-less-crowdfunding

## Consensus and oracles 

As you (may) have already noticed, "Oracles" is an item under "Consensus" in the æternity white paper. Since an Oracle can provide an input to the Blockchain, this input must be validated before every node applies the consensus mechanism function. Ultimately, the current oracle's answer gets included in the Blockchain forever. 


![Prediction Markets on æternitry](https://github.com/aeternity/wiki/blob/master/images/AE101-Prediction_Market_noText.png)

## What good does the oracle bring

It is exciting to think that Blockchain oracles, by themselves, have their own use cases. On top of that, every oracle's answer or output is recorded forever in the Blockchain and cannot be altered. This would be revolutionary in the history of mankind. The recollection of past events (History) would not be written by the winners/survivors of historical events, but rather by the people living those events in real-time. Not only that, but a malicious object creator can be easily brought down by the public, with the oracle providing a steady vehicle for doing that.

Here is what an oracle is very good at:

+ by using "æons", creators and participants are financially incentivized to commit to truthful and realistic outputs;
+ oracle questions can be instantiated for every (non-computable) question;
+ an oracle's output is publicly visible to everyone, residing on the Blockchain, thus contributing to an impartial censorship-proof knowledge-based decentralized society.

It is yet to be determined if oracle machines are part of the Type Theory<sup>2</sup>. In essence, this fact means that it is questionable to what extent we can question oracles about themselves. 

***
<sup>1</sup> "Systems Of Logic Based On Ordinals", A. M. Turing, 1936, Seeley G. Mudd Manuscript Library,
Princeton, NJ, accessed on 05.05.2017, [Link](http://www.dcc.fc.up.pt/~acm/turing-phd.pdf)
***
<sup>2</sup> "Foundations of computation theory", p.4, Akeo Adachi, 1990, Ohmsha, accessed on 21.05.2017, [Link](https://books.google.bg/books?id=pzf46nN7L_kC&pg=PR2&lpg=PR2&dq=Akeo+Adachi,+Foundations+of+computation+theory,+Ohmsha,+1990.&source=bl&ots=yTYxgQ6n2R&sig=q-eKdtwsxyt4Gdi9ZnqKImjPiLA&hl=bg&sa=X&ved=0ahUKEwj3iJT_rNnTAhUDlCwKHUZeC40Q6AEINDAC#v=onepage&q=Akeo%20Adachi%2C%20Foundations%20of%20computation%20theory%2C%20Ohmsha%2C%201990.&f=false)



