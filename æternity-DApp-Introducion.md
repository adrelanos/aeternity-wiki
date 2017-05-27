# DApp Development Introduction

Take a look at the dice smart contract for an idea of what state channel
applications will look like. It is a slot machine where you gamble money
at 50/50 odds.

- [/tree/master/src/dice.erl](../../../../aeternity/testnet/tree/master/src/dice.erl)
- [/master/src/networking/handler.erl](../../../../aeternity/testnet/tree/master/src/networking/handler.erl#L104)
- [/master/src/easy.erl#L96](../../../../aeternity/testnet/tree/master/src/easy.erl#L96)
- [/master/src/networking/internal_handler.erl#L55](../../../../aeternity/testnet/tree/master/src/networking/internal_handler.erl#L55)

>**Zack said:**
>It is a little spread around now. We need a way to organize dapps so it
>is easy to upgrade a basic aeternity node to support whatever dapp you
>want.

This is the language for writing smart contracts:
[/BumblebeeBat/chalang](../../../../aeternity/chalang)

**On sources tree we have this modules:**

| No |                                                                                                       |
|:---|:------------------------------------------------------------------------------------------------------|
| 1  | [arithmetic_chalang.erl](../../../../aeternity/chalang/blob/master/src/arithmetic_chalang.erl) |
| 2  | [chalang.app.src](../../../../aeternity/chalang/blob/master/src/chalang.app.src)               |
| 3  | [chalang.erl](../../../../aeternity/chalang/blob/master/src/chalang.erl)                       |
| 4  | [chalang_app.erl](../../../../aeternity/chalang/blob/master/src/chalang_app.erl)               |
| 5  | [chalang_sup.erl](../../../../aeternity/chalang/blob/master/src/chalang_sup.erl)               |
| 6  | [compiler_chalang.erl](../../../../aeternity/chalang/blob/master/src/compiler_chalang.erl)     |
| 7  | [fractions.erl](../../../../aeternity/chalang/blob/master/src/fractions.erl)                   |
| 8  | [test_chalang.erl](../../../../aeternity/chalang/blob/master/src/test_chalang.erl)             |

1. arithmetic_chalang
2. chalang.app.src
3. chalang.erl
4. chalang_app.erl
5. chalang_sup.erl
6. compiler_chalang.erl
7. fractions.erl
8. test_chalang.erl

***

related: [æternity DApp Development](æternity-DApp-Development)

***

Sources:

æternity DApp Development
=========================

* [DApp Developper Introducion](æternity-DApp-Introducion)
* [Scripting Language](æternity-Scripting-Language)
  * [æternity Scripting Language Examples](æternity-Scripting-Language-Examples)
* [Resources](æternity-DApp-Developer-Resources)


***

Sources:

| No | Type | Source                                                          |
|:---|:-----|:----------------------------------------------------------------|
| 1  | docs | [SL docs](../../../../aeternity/chalang/blob/master/README.md)  |
| 2  | docs | [TestNet docs](../../../../aeternity/testnet/tree/master/docs/) |
| 3  | docs | [Opcodes](../../../../aeternity/chalang/blob/master/opcodes.md) |
