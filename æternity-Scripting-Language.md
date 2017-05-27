æternity Scripting Language (Chalang)
=====================================

Chalang is developed by Zackary Hess

It is built for blockchain smart contracts. This is a language make for
state channels.

It is deterministic, so that every node of the blockchain gets the same
result.

Functions are tail call optimized.

Manages 2 types of gas:
* one for space,
* and one for time.

Instead of using `goto` for recursion, it uses function calls.

[Example code is in this folder](https://github.com/aeternity/chalang/blob/master/examples)
and some more stuff about,
[hashlock](../../../../aeternity/chalang/blob/master/examples/hashlock.fs)
has lots of documentation.

* to install: `sh install.sh`

* to start a node with these libraries loaded: `sh start.sh`

* to run tests on a node: 1> `test_chalang:test().`
***
## Opcodes


***
related: [æternity DApp Development](æternity-DApp-Development),
***

Sources:

| No | Type | Source                                                           |
|:---|:-----|:-----------------------------------------------------------------|
| 1  | docs | [SL docs](../../../../aeternity/chalang/blob/master/README.md)   |
| 2  | docs | [TestNet docs](../../../../aeternity/testnet/tree/master/docs/)  |
| 3  | docs | [Opcodes](../../../../aeternity/chalang/blob/master//opcodes.md) |

