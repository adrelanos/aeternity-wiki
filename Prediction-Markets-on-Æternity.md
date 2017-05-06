# 1. What are prediction markets? #
Prediction markets are exchange-traded markets where participants can trade around the probability of events, like the outcome of a presidential election, the likelihood of a natural disaster, the likely winner of a music competition and so on.



### Prediction markets serve two important functions:

### a) They allow participants to profit from making accurate predictions.

Participants in a prediction market buy and sell shares based on what they think the likelihood of an outcome will be. 
It is important to note that in order for a market participant to win consistently, he/she must not only predict the outcome correctly but must also correctly assess the probability of that outcome.
Take for example an event that has a 90% probability. If on a market the current price signals a probability of 95% instead of 90%, it can still be very profitable in the long run for a trader to bet against such events, even if that trader believes that the event will likely happen given the 90% probability.
This is very counter-intuitive, but it is easily explained by doing the math.

If Alice makes 100 different bets against events that have a 90% probability, she will be right 10 times and wrong 90 times. But because the odds given for each event were 19 to 1 (0.95/0.05=19), Alice will still make a nice profit assuming all bets were made for the same amount of money. In this case, if every bet was a 1000AE bet, Alice will make a profit of  5000AE (10x950-90x50=5000).

### b) They reveal information using the price mechanism.
 
Given that the participants in a prediction market are rewarded for being correct and punished for being wrong, they will try to be as accurate as possible and the prices will reflect that. In prediction markets prices can be understood as showing the probabilities of the outcome that is being traded.

An example here could be a miner who wants to plan his hardware purchases in advance and needs to know the probability of the total hash rate getting past a certain level in the following six months. In this case, instead of guessing or relying on his intuition, the miner can set up a prediction market that will give him very accurate probabilities.

# 2. How do prediction markets work on Æternity
Æternity allows the creation of smart contracts that interfere with real world data on the blockchain. This makes it very easy to create prediction markets on the Æternity blockchain since everything that is required for them to work is already available on the blockchain:

a) aeon token holders can play the role of market participants or bettors

b) the question that the market wants to answer and the rules of that market can be written in a smart contract

c) the oracle can also be created directly on the blockchain and be accessed by the smart contract
