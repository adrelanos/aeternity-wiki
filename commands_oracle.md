### The terminal interface to the oracle
***


### New difficulty oracle
This kind of oracle is only for measuring the expected difficulty in the future. Start is when trading starts. Difficulty is your approximation of the future value of the difficulty. This oracle has 3 possible outputs: Either the difficulty you estimated is too high, or it is too low, or it is good enough. If it is good enough, then we can launch a normal oracle.
```
easy:new_difficulty_oracle(Start, Difficulty).
```


### New question oracle
This oracle asks a true/false question about the future. Eventually, the answer to this question will get recorded on the oracle, and will be accessible to the smart contracts.
```
easy:new_question_oracle(Start, Question, RecentDifficultyOracle).
```

### Bet in an oracle
type is one of the atoms in this list: [true, false, bad]
You can either bet that the answer to the question is true or false, or you can bet that it is a bad question.
```
easy:oracle_bet(OracleID, Type, Amount).
```

### Close an oracle
If the oracle has had the same output state for a long enough period of time, then this is how anyone can close the channel and end the betting period.
```
oracle_close(OracleID).
```

### Oracle Shares
Collect shares purchased in an oracle
```
oracle_shares(OracleID).
```

### Oracle unmatched
If you had unmatched trades sitting in the order book when the oracle closed, this is how you get your money back.
```
oracle_unmatched(OracleID, OrderID).
```



***
read this: - [commands](commands)
- [api_examples](api_examples)
- [oracle](oracle)
- [oracle_answers_for_smith_crown](oracle_answers_for_smith_crown)
- [oracle_manipulation](oracle_manipulation)
- [oracle_motivations](oracle_motivations)
- [oracle_simple](oracle_simple)
- [questions](questions)

***
[Zack’s - TOC Aeternity Blockchain Documentation](Zack_Docs_TOC)