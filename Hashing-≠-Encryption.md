# The differences between hashing and encryption

In this article we have set to explain the major difference between hashing and encryption and how each process is important to blockchain architecture and crypto tokens. 

## Hashing
By definition, hashing means taking an arbitrary piece of data and mapping it to data of fixed size. In reality, this means that if you hash the word "hello" and a whole page of text, the two hashes will always have one and the same length, when processed through the same hashing function. Each hash function has a many-to-one relation. //todo

The output of the hashing function is the hash. There are two major facts about hashing that every person, taking interest in blockchain technology should know:
* Hashing one and the same input will **always** produce one and the same hash output;
* Given an output hash, one **can not** "unhash" it, or see the input;
* Every output hash can be **instantaneously checked** if it is the result of a specific input that has been hashed.

**Important:** the expression "two-way hashing function" is an oxymoron.

## Encryption
Encryption makes it possible to obfuscate any piece of data and produce an output that maps only to its input. Therefore, in encryption, the relationship between input and output is one-to-one. Unlike hashing, everyone with the decryption key would be able to verify the input data by actually decrypting and seeing it.  //todo

Another major difference between hashing and encryption is that hashing does not require as much processing power as decryption. Therefore, when only checking the data is necessary, hashing is preferred. 


