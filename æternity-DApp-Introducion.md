# DApp Development Introduction

[NOT only a copy and past! DO NOT DELETE, please. THX - my pull request](https://github.com/aeternity/testnet/pull/94)

Take a look at the dice smart contract for an idea of what state channel applications will look like.
It is a slot machine where you gamble money at 50/50 odds.

- [/tree/master/src/dice.erl](../../../../aeternity/testnet/tree/master/src/dice.erl)
- [/master/src/networking/handler.erl](../../../../aeternity/testnet/tree/master/src/networking/handler.erl#L104)
- [/master/src/easy.erl#L96](../../../../aeternity/testnet/tree/master/src/easy.erl#L96)
- [/master/src/networking/internal_handler.erl#L55](../../../../aeternity/testnet/tree/master/src/networking/internal_handler.erl#L55)

It is a little spread around now.
We need a way to organize dapps so it is easy to upgrade a basic aeternity node to support whatever dapp you want.

This is the language for writing smart contracts:
[/BumblebeeBat/chalang](../../../../BumblebeeBat/chalang)


***
related: [æternity DApp Development](æternity-DApp-Development)
***
sources:
* [TestNet docs](../../../../aeternity/testnet/tree/master/docs/)
* [SL docs](../../../../aeternity/testnet/tree/master/docs/)
