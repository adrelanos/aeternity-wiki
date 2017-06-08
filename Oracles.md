# Introduction

## What are Oracles?

In computer science oracles are considered to be special machines, that can provide answers to non-computable (non-mathematical) problems. In terms of that definition, all modern computers are **not** oracles. This fact is true because all problems that computers solve basically come down to performing some sort of computation, based on certain finite input parameters provided by the user. 

Therefore, oracles, or oracle machines, by definition <sup>1</sup>, can compute the uncomputable problems. In plain words, oracles can provide answers to the questions that are not mathematical problems. According to that terminology and the main point of reference to Alan Turing's Theory of Computation, the internal workings of an oracle are unknown. The oracle, however, will always provide one and the same output as a response to one and the same input. 

# æternity Oracles

## How do æternity oracles function?
Much like Turing's original oracle machine, an æternity oracle produces an output result, however, only to a given question. So, by itself, an individual æternity oracle is not universal. In order to answer a multitude of questions, an unlimited number of oracles must be created. The oracle's output result is then provided by the person, who has launched it. This person has committed, by means of the æternity token "æon" (which provides here the financial incentive), to provide an answer during a certain time-frame which is specified at the launch of the oracle. 

Because there are no hardware oracles, æternity oracles aim to provide a trustworthy YES or NO answer to every possible type of question, whose YES or NO answer can be substantiated with real-world data. So again, the human brain will be a part of the process performing a check on the question's answer. That is natural because the human brain is an instantiation of the oracle machine. It is only incentivized by "æons" to provide that correct answer. Accordingly, every single oracle resides on æternity's Blockchain.

![Governance on æternity](https://github.com/aeternity/wiki/blob/master/images/%C3%86_101_Governance.png)

## Users and the oracle
In the context of the æternity Oracle, there will be two types of users:
+ object creators: people who instantiate an oracle. They are the ones who commit to a certain result, by depositing "æon", during a specified time-frame.
+ object readers: all others who can refer to that oracle or submit counter-claims by depositing "æon" as a guarantee of their counter-claim.

## Consensus and oracles 

As you (may) have already noticed, "Oracles" is an item under "Consensus" in the æternity white paper. Since oracles can provide an input to the Blockchain, this input must be validated before every node applies the consensus mechanism function. Ultimately, the current oracle's answer gets included in the Blockchain forever. 

Validating the oracle output on the Blockchain has a number of obstacles. Essentially, the consensus mechanism must validate the oracle outcome separately from the other the other inputs it is validating - transactions, balances, etc. This fact means that on one hand you have the mechanism validating new blocks, and on the other, the same process goes on for the oracle answers. Although technically possible by means of running two consensus mechanisms consecutively, this process can be expensive and time-consuming. Therefore, the object creators commit to an oracle answer using "æons". Ultimately, the oracle's output is determined by its creators and readers (or counter-claimers) and the same output is included in the Blockchain as simply an end result.

![Prediction Markets on æternitry](https://github.com/aeternity/wiki/blob/master/images/AE101-Prediction_Market_noText.png)

## What good does the oracle bring

It is exciting to think that Blockchain oracles, by themselves, have their own use cases. On top of that, every oracle's answer or output is recorded forever in the Blockchain and cannot be altered. This would be revolutionary in the history of mankind. The recollection of past events (History) would not be written by the winners/survivors of historical events, but rather by the people living those events in real-time. Not only that, but a malicious object creator can be easily brought down by the public, with the oracle providing a steady vehicle for doing that.

Here is what an oracle is very good at:

+ by using "æons", creators and readers are financially incentivized to commit to true and realistic outputs;
+ oracles can be instantiated for every (non-computable) question;
+ an oracle's output is publicly visible to everyone, residing on the Blockchain, thus contributing to an impartial censorship-proof knowledge-based decentralized society.

It is yet to be determined if oracle machines are part of the Type Theory<sup>2</sup>. In essence, this fact means that it is questionable to what extent we can question oracles about themselves. 

***
<sup>1</sup> "Systems Of Logic Based On Ordinals", A. M. Turing, 1936, Seeley G. Mudd Manuscript Library,
Princeton, NJ, accessed on 05.05.2017, [Link](http://www.dcc.fc.up.pt/~acm/turing-phd.pdf)
***
<sup>2</sup> "Foundations of computation theory", p.4, Akeo Adachi, 1990, Ohmsha, accessed on 21.05.2017, [Link](https://books.google.bg/books?id=pzf46nN7L_kC&pg=PR2&lpg=PR2&dq=Akeo+Adachi,+Foundations+of+computation+theory,+Ohmsha,+1990.&source=bl&ots=yTYxgQ6n2R&sig=q-eKdtwsxyt4Gdi9ZnqKImjPiLA&hl=bg&sa=X&ved=0ahUKEwj3iJT_rNnTAhUDlCwKHUZeC40Q6AEINDAC#v=onepage&q=Akeo%20Adachi%2C%20Foundations%20of%20computation%20theory%2C%20Ohmsha%2C%201990.&f=false)



