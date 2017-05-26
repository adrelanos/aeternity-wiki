TOC Merkle trees
================

* [What are Merkle trees?](#what-are-merkle-trees)
     * [Uses](#uses)
     * [æternity is the blockchain to rule them all!](#æternity-is-the-blockchain-to-rule-them-all)
     * [æternity the blockchain to rule them all](#æternity-the-blockchain-to-rule-them-all)
     * [Structure: Merkle tree](#structure-merkle-tree)
     * [The Basic Protocol Merkle Trees follow](#the-basic-protocol-merkle-trees-follow)
     * [Benefits](#benefits)

* [æternity Merkle trees](#æternity-merkle-trees)
     * [æternity orders](#æternity-orders)
     * [æternity channels](#æternity-channels)
     * [æternity accounts](#æternity-accounts)
     * [æternity oracle bets](#æternity-oracle-bets)
     * [æternity oracle shares](#æternity-oracle-shares)
     * [æternity proof of burn](#æternity-proof-of-burn)
     * [æternity æternity proof of existence](#æternity-proof-of-existence)
* [Sources](#sources)

***

## What are Merkle trees?

In cryptography and cryptocurrency a Merkle tree: also referred to as a
hash tree, is a mathematical structure that hashes different sets of
data into a single, compact hash: the Merkle root. It is a tree
structure in which each leaf node is a hash of a block of data, and each
non-leaf node is a hash of its children. You can think of a Merkle tree
as a network of cascading hashes or hash trees.


### Uses

Merkle trees are used to verify data being stored and transmitted in and
between different computers on a network and do so very efficiently.
There main use is to unsure data blocks received from other peers in a
peer-to-peer network are received undamaged and unaltered, and even to
check that the other peers do not lie and send fake blocks. To do this
Merkle trees use a cryptographic hash function. In order for you, the
reader, to understand Merkle trees, a basic understanding of a
cryptographic hash functions is needed.

A cryptographic hash function is a mathematical algorithm that maps data
of arbitrary size to a bit string of a fixed size (a hash function)
which is designed to also be a one-way function. This means that there
is no mathematical equation, or algorithm that can unhash or reverse the
data to its original data state prior to being hashed. Hashes provide
efficient data storage and reduce the level of data needed to prove
something exists.

There are many different cryptographic protocal suites that use hashes
to verify data. One example is Asymmetric-key cryptography: also
referred to as public key cryptography, and digital signatures. They use
cryptographic hash functions to verify data. However, explaining how
they work and their uses is well outside the scope of the paper. What we
will do instead is go through a very simplified example of how data can
be verified with a cryptographic hash function.

    In this example, lets say Bob wants to send Alice a block of data and
    wants Alice to be able to verify that the data she received has not been
    corrupted or tampered with in transit. What Bob will do is use a
    cryptograpic hash function like sha-2 to create a hash of the block of
    data before he sends it to Alice. In the example below, Bob uses sha-256
    to hash the block of data which in this case is a short sentence:


### æternity is the blockchain to rule them all!

The hash of the above sentence is:
`60c1be71e2915ea72a33c059cf7710787f6748e10091173dfc17363444a2d3ce`

    After Bob has created  the hash,  he sends  the original data over the
    network to Alice. 
    However, Bob does not send the hash along with the data,  he sends them 
    separately. We will assume for the sake of this example that Alice rec-
    eived the hash of Bobs data from a known trusted source. 
    
    Now, Alice has both the data Bob sent her and the hash of the data. 
    
    What Alice will do next is us the same cryptographic hash function that 
    Bob used,  and create a  hash  of the data that she received:  referred 
    to as a checksum. Lets say that Alice received the below sentence from
    Bob.

### æternity the blockchain to rule them all

The hash of the above sentence is:
`45c93bfadb67691456e61e011ba4652125c16303304ecb2ab31d6f033ef09180`

    I am sure you have notices 2 things. First is that the 2 hashes values are
    completely different.The second is the hashes are larger  than  the actual
    size of the data that was  hashed.  Would this  not  mean  that hashes are
    inefficient?  Why is this?  Well, to answer  the  first question.  If  you
    look carefully you will notice that the exclamation point is missing  from 
    the sentence that Alice received. This is the reason the 2 hash values are 
    different. For some reason the data was altered while in transit to  Alice. 
    
    Alice does not need to know what the original sentence looked like to know 
    it has been altered. As you can see even a very small change  in  the data 
    will result in  completely different outcomes  when using  a cryptographic 
    hash function. 
    Now, to answer the second question. As stated above, cryptograhic hash func-
    tions map data of any size to a bit string of a fixed size.  Since we are 
    using sha-256 as a hashing algorithm, the data is mapped to a 32 byte string. 
    
    This means regardless of the size of the block of data being hashed, the hash 
    value will always be a 32 byte string: weather it is an 8 byte block  or an 8
    terabyte block of data. 
    
    This would also mean if the data you are verifying is very small,  lets say: 
    10 bytes, using a hashing algorithm that maps data to a 32 byte string would 
    not be efficient. 
    
    However,  if the block of data being hashed is very large,  for instance a 100 terabyte block, 
    using the same hashing algorithm would be efficient, and this in turn is what
    makes Merkle trees so efficient.

### Structure: Merkle tree

Merkle trees are essentially a tree of hashes where each leaf is a hash
of a block of data. Nodes further up in the tree are the hashes of their
respective children. For example, in the picture below: hash 0 is the
result of hashing the concatenation of hash 0-0 and hash 0-1. That is,
hash 0=hash( hash 0-0 + hash 0-1 ) where + denotes concatenation.


![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Hash_Tree.svg/640px-Hash_Tree.svg.png)


In most cases, merkle trees have a branching factor of 2, meaning that
each node has up to 2 children. They can however use many more child
nodes under each node.

Every Merkle tree has a master hash known as a Merkle root. This Merkle
root can only be acquired from a trusted source. While using the master
hash it is possible to receive the Merkle tree regardless of which
source is responsible for sharing the data. After receiving the Merkle
tree it is checked against the master hash to verify the data has not
been tampered with or corrupted during transmission. If the data can not
be verified another attempt will be made to retrieve the information
from another source until data can be found that can be verified.

In the top of a hash tree there is a top hash (or root hash or master
hash). Before downloading a file on a peer-to-peer network, in most
cases the top hash is acquired from a trusted source, for instance a
friend or a web site that is known to have good recommendations of files
to download. When the top hash is available, the hash tree can be
received from any non-trusted source, like any peer in the peer-to-peer
network. Then, the received hash tree is checked against the trusted top
hash, and if the hash tree is damaged or fake, another hash tree from
another source will be tried until the program finds one that matches
the top hash.

The main difference from a hash list is that one branch of the hash tree
can be downloaded at a time and the integrity of each branch can be
checked immediately, even though the whole tree is not available yet.
For example, in the picture, the integrity of data block 2 can be
verified immediately if the tree already contains hash 0-0 and hash 1 by
hashing the data block and interatively combining the result with hash
0-0 and then hash 1 and finally comparing the result with the top hash.
Similarly, the integrity of data block 3 can be verified if the tree
already has hash 1-1 and hash 0. This can be an advantage since it is
efficient to split files up in very small data blocks so that only small
blocks have to be re-downloaded if they get damaged. If the hashed file
is very big, such a hash tree or hash list becomes fairly big. But if it
is a tree, one small branch can be downloaded quickly, the integrity of
the branch can be checked, and then the downloading of data blocks can
start.

### The Basic Protocol Merkle Trees follow

1. Computer A sends a hash of the data to computer B.
2. Computer B checks that hash against the root of the Merkle tree.
3. If there is no difference, nothing further is done.
4. If there is difference in a single hash, computer B will request the
   roots of the two subtrees of that hash.
5. Computer A creates the necessary hashes and sends them back to
   computer B.
6. Steps 4 and 5 are repeated until the inconsistent data block(s) are
   found. It is possible to find more than 1 data block that is wrong
   because there may be more than one error in the data.

### Benefits

Because the computers are only sending hashes over the network (not the
entire file), this process can go very quickly. Plus, if an inconsistent
piece of data is found, it's much easier to insert a small chunk of
fixed data then to completely rewrite the entire file to fix the issue.

One of the reasons Merkle trees are useful in distributed systems
because they significantly reduce the amount of data that a trusted
authority has to maintain to proof the integrity of the data. It is
inefficient to check the entirety of the data to check for issues. They
are useful in peer-to-peer networks because they help verify
information. They separate the validation of the data from the data
itself even if it comes from a untrusted source. This is a concern in a
peer-to-peer network. Merkle trees also significantly reduce the network
I/O packet size to perform consistency and data verification as well as
data synchronization there by making network I/O cheaper.

***
***


## æternity Merkle trees

The æternity blockchain uses Merkle trees to verify data. At the time
this paper was composed there was 8 Merkle trees in the æternity
blockchain. The following is a brief description:

### æternity oracles:

These are the oracles that exist right now. They are stored by integer
oracle ID and never reuse the same ID. The hash of the text of the
question is stored and are the results of the oracles that have existed.
They are stored by ID. This data is available to the virtual machine.
The result is stored in 1 byte. Either it is 0 for false, 1 for true, 2
if the question was bad, or 4 if the question hasn't been answered yet.

related æ-wiki pages: [Oracles](Oracles)
***
### æternity orders:

Every oracle has an order book. The order book is a linked list of
orders. Each order has an amount, and the ID of the owner.

related æ-wiki pages:
***
### æternity channels:

This stores channels by an integer channel ID.

related æ-wiki pages: [Channels](https://github.com/aeternity/wiki/wiki/Channels), [State-Channels](State-Channels)
***
### æternity accounts

This tree stores accounts by integer ID. Each account has 2 Merkle roots
written in them. One is for a shares tree, the other is for an oracle
bets tree.

related æ-wiki pages:   [Accounts]()
***
### æternity oracle bets:

Each account has a tree of oracle bets. Oracle bets are not
transferable. Once an oracle is settled, the bets in it can be converted
in to shares.

related æ-wiki pages:  [Oracles](Oracles)
***
### æternity oracle shares:

Each account has a tree of shares. The shares are stored by share ID.
The ID of a share determines it's difficulty. You can own either
negative, positive, or zero amount of each type of share. Shares are
also transferable.

related æ-wiki pages: [Oracles](Oracles),
***
### æternity proof of burn

Proof of burn tree stores by address. It stores the number of AE tokens
that this address has burned. This data is available to the virtual
machine.

related æ-wiki pages:   [Proof of burn]()
***
### æternity proof of existence

This tree stores by hash. If returns a 1 if the thing exists, a 0
otherwise. This data is available to the virtual machine.

related æ-wiki pages:   [Proof of Existence]()
***
###  æternity contracts

Add some words here:

related æ-wiki pages: [æternity-Contracts](æternity-Contracts)
***

## Sources:

| No |                                                                                                                                               |                                                                      |                                                                                                 |
|:---|:----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------|:------------------------------------------------------------------------------------------------|
| 1  | Zackary Hess, Yanislav Malahov, Jack Pettersson                                                                                               | æternity blockchain                                                  | [æternity Whitepaper](https://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) |
| 2  | zaghal, A. _Wikipedia Merkle Tree.                                                                                                            | _ **Picture**                                                        | [wikipedia/merkle_tree](https://en.wikipedia.org/wiki/Merkle_tree#/media/File:Hash_Tree.svg)    |
| 3  | Becker, George.                                                                                                                               | **Merkle Signatures Schemes, Merkle Trees and Their Cryptanalysis**. | [link](http://www.emsec.rub.de/media/crypto/attachments/files/2011/04/becker_1.pdf  )           |
| 4  | Chumble, Alex. Moore, Karleigh. _Merkle Tree_                                                                                                 | **Protocol**;                                                        | [brillian.org](https://brilliant.org/wiki/merkle-tree/ )                                        |
| 5  | zack-bitcoin, sjamayee.                                                                                                                       | **_æternity Merkle trees_**                                          | [aeternity/testnet](https://github.com/aeternity/testnet/blob/master/docs/trees.md  )           |
| 6  | [Katz, J. Wikipedia](https://www.politicalavenue.com/libraryebooks/cryptology-and-cryptography/Introduction%20to%20Modern%20Cryptography.pdf) | **Introduction to Modern Cryptography**.                             | Capman & Hall/CRC.                                                                              |

