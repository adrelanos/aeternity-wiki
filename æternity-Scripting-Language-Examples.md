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


## Opcodes

The data is lists of binaries opcode, symbol for compiled language,
stack changes.

* [Values Opcodes](#values-opcodes)
* [Other Opcodes](#other-opcodes)
* [Stack Opcodes](#stack-opcodes)
* [R-Stack Opcodes](#r-stack-opcodes)
* [Crypto Opcodes](#crypto-opcodes)
* [Arithmetic Opcodes](#arithmetic-opcodes)
* [Conditions Opcodes](#conditions-opcodes)
* [Logic Opcodes](#logic-opcodes)
* [Check state Opcodes](#check-state-opcodes)
* [Function Opcodes](#function-opcodes)
* [Variables Opcodes](#variables-opcodes)
* [Lists Opcodes](#lists-opcodes)

***

### values opcodes

| opcode | symbol | stack changes | comment                                                             |
|:-------|:-------|:--------------|:--------------------------------------------------------------------|
| 0      | int    | -- X          | the next 32 bits = 4 bytes are put on the stack as a single binary. |
| 2      | binary | N -- L        | the next N * 8 bits are put on the stack as a single binary.        |


### other opcodes

| opcode | symbol | stack changes | comment                                                                        |
|:-------|:-------|:--------------|:-------------------------------------------------------------------------------|
| 10     | print  | ( Y -- X )    | prints the top element on stack                                                |
| 11     | crash  |               | code stops execution here. Whatever is on top of the stack is the final state. |
| 12     | nop    | ( -- )        | does nothing.                                                                  |


### stack opcodes

| opcode | symbol | stack changes  | comment                                 |
|:-------|:-------|:---------------|:----------------------------------------|
| 20     | drop   | X --           | will remove the top element on stack    |
| 21     | dup    | X -- X X       | duplicates the top element of the stack |
| 22     | swap   | A B -- B A     | swaps the top two element of the stack  |
| 23     | tuck   | a b c -- c a b |                                         |
| 24     | rot    | a b c -- b c a |                                         |
| 25     | 2dup   | a b -- a b a b |                                         |
| 26     | tuckn  | X N --         | inserts X N-deeper into the stack.      |
| 27     | pickn  | N -- X         | grabs X from N-deep into the stack.     |


### r-stack opcodes

| opcode | symbol | stack changes | comment                     |
|:-------|:-------|:--------------|:----------------------------|
| 30     | >r     | V --          |                             |
| 31     | r>     | -- V          | moves from return to stack  |
| 32     | r@     | -- V          | copies from return to stack |


### crypto opcodes

| opcode | symbol     | stack changes              | comment                                                                                                  |
|:-------|:-----------|:---------------------------|:---------------------------------------------------------------------------------------------------------|
| 40     | hash       | X -- <<Bytes:256>>         |                                                                                                          |
| 41     | verify_sig | Sig Data Pub -- true/false |                                                                                                          |
| 42     | pub2addr   | Pub -- Addr                | This is difficult because we can't represent tuples. Maybe pinkcrypto:address needs to use lists instead |


### arithmetic opcodes

Note about arithmetic opcodes: they only works with 4-byte integers.
Results are 4-byte integers. 32-bits. The integers are encoded so that
FFFFFFFF is the highest integer and 00000000 is the lowest.

| opcode | symbol | stack changes         | comment                  |
|:-------|:-------|:----------------------|:-------------------------|
| 50     | +      | X Y -- Z              |                          |
| 51     | -      | X Y -- Z              |                          |
| 52     | *      | X Y -- Z              |                          |
| 53     | /      | X Y -- Z              |                          |
| 54     | >      | X Y -- true/false X Y |                          |
| 55     | <      | X Y -- true/false X Y |                          |
| 56     | ^      | X Y -- Z              |                          |
| 57     | rem    | A B -- C              | only works for integers. |
| 58     | ==     | X Y -- true/false X Y |                          |


### conditions opcodes

| opcode | symbol | stack changes | comment                                 |
|:-------|:-------|:--------------|:----------------------------------------|
| 70     | if     |               | conditional statement                   |
| 71     | else   |               | part of an switch conditional statement |
| 72     | then   |               | part of switch conditional statement.   |


### logic opcodes

| opcode | symbol | stack changes                       | comment                                                                            |
|:-------|:-------|:------------------------------------|:-----------------------------------------------------------------------------------|
| 80     | not    | true/false -- false/true            |                                                                                    |
| 81     | and    | true/false true/false -- true/false | false is 0, true is any non-zero byte.                                             |
| 82     | or     | true/false true/false -- true/false |                                                                                    |
| 83     | xor    | true/false true/false -- true/false |                                                                                    |
| 84     | band   | 4 12 -- 4                           | if inputed binaries are different length, it returns a binary of the longer length |
| 85     | bor    | 4 8 -- 12                           |                                                                                    |
| 86     | bxor   | 4 12 -- 8                           |                                                                                    |


### check state opcodes

| opcode | symbol        | stack changes                        | comment                                                                                                   |
|:-------|:--------------|:-------------------------------------|:----------------------------------------------------------------------------------------------------------|
| 90     | stack_size    | -- Size                              |                                                                                                           |
| 91     | total_coins   | -- TotalCoins                        |                                                                                                           |
| 92     | height        | -- Height                            |                                                                                                           |
| 93     | slash         | -- true/false                        | if this is part of a solo_stop transaction, then return 0. If it is part of a slash transaction, return 1 |
| 94     | gas           | -- X                                 |                                                                                                           |
| 95     | ram           | -- X                                 | tells how much space is left in ram.                                                                      |
| 96     | id2addr       | ID -- Addr                           |                                                                                                           |
| 97     | many_vars     | -- R                                 | how many more variables are defined                                                                       |
| 98     | many_funs     | -- F                                 | how many functions are there defined                                                                      |
| 99     | oracle        | -- R                                 | the root of the oracle trie from the previous block.                                                      |
| 100    | id_of_caller  | -- ID                                | the ID of the person who published the code on-chain                                                      |
| 101    | accounts      | -- A                                 | the root of the accounts trie from the previous block.                                                    |
| 102    | channels      | -- C                                 | the root of the channels trie from the previous block.                                                    |
| 103    | verify_merkle | Root Proof Value -- Value true/false |                                                                                                           |


### function opcodes

| opcode | symbol  | stack changes | comment                                                                                                                        |
|:-------|:--------|:--------------|:-------------------------------------------------------------------------------------------------------------------------------|
| 110    | :       |               | this starts the function declaration.                                                                                          |
| 111    | ;       |               | This symbol ends a function declaration. example : square dup * ;                                                              |
| 112    | recurse |               | crash. this word should only be used in the definition of a word.                                                              |
| 113    | call    |               | Use the binary at the top of the stack to look in our hashtable of defined words. If it exists call the code, otherwise crash. |


### variables opcodes

| opcode | symbol | stack changes | comment                     |
|:-------|:-------|:--------------|:----------------------------|
| 120    | !      | X -- Y        | only stores 32-bit integers |
| 121    | @      | Y -- X        |                             |


### lists opcodes

| opcode | symbol  | stack changes               | comment                                                                                        |
|:-------|:--------|:----------------------------|:-----------------------------------------------------------------------------------------------|
| 130    | cons    | X Y -- [X\|Y]               |                                                                                                |
| 131    | car     | [X\|Y] -- X Y               |                                                                                                |
| 132    | nil     | -- []                       | this is the root of a list.                                                                    |
| 134    | ++      | X Y -- Z                    | appends 2 lists or 2 binaries. Cannot append a list to a binary. Also works on pairs of lists. |
| 135    | split   | N Binary -- BinaryA BinaryB | Binary A has N*8 many bits. BinaryA appended to BinaryB makes Binary.                          |
| 136    | reverse | F -- G                      | only works on lists                                                                            |
| 137    | is_list | L -- L B                    | checks if the thing on the top of the stack is a list or not. Does not drop it.                |


***

**These are compiler macros to make it easier to program.**
* ( a open parenthesis starts a multi-line comment block.
* ) a closed parenthesis ends the comment.
* Make sure to put spaces between the parenthesis and the other words.
* or_die ( B -- ) if B is true, then does nothing. if B is false, then
  it crashes.

* +! ( Number Name -- ) increments the variable Name by Number

* Lists are easy with these 3 words: "[", "," and, "]". You don't need
  spaces between them either. example: "[1,2,3,4]"

***

## Compile Backtracking

(logic_or '((both_reveal) (one_reveal) (end 1 0 0)))

(logic_define both_reveal (Secret1 Secret2) ((X (commit 0)) (X (hash
Secret1)) (Y (commit 1)) (Y (hash Secret2)) (C (rem (bxor Secret1
Secret2) 2))) (end 3 C (amount)))

(logic_define one_reveal (Secret) ((N (logic_or (0 1))) (X (commit N))
(X (hash Secret))) (end 2 N (amount)))

(macro (logic_or L) %each one needs to be a function, that way we can
have continutations. (let ((Fs (to_funcs L (cond ((= (cdr L) ()) '(car
L)) (

(macro (logic_eqs Pointer Func Continuation) (let ((Var '(get Pointer)))
'(case ((eqs Var (empty)) (store (Func) Pointer)) ((eqs Var (Func)) ())
(true (Continutation)))))

(macro both_reveal (define (Secret1 Secret2 Continuation VarCounter)
(nop (store (empty) (+ 0 VarCounter)) (store (empty) (+ 1 VarCounter))
(store (empty) (+ 2 VarCounter)) (logic_eqs (+ 0 VarCounter) (commit 0)
Continutation) (logic_eqs (+ 0 VarCounter) Secret1 Continutation)
(logic_eqs (+ 1 VarCounter) (commit 1) Continutation) (logic_eqs (+ 1
VarCounter) Secret2 Continutation) (logic_eqs (+ 2 VarCounter) (rem
(bxor Secret1 Secret2) 2) Continutation) (end 3 C (amount)))))
<sup>5</sup>

## Compile Functions

getting variables to work correctly in functions can't be done
completely at compile-time. If a function calls itself recursively, and
the function is not tail-call optimized, then we need to remember the
values of the caller-function's variables, so that when the child
returns, we know how to finish the parent's execution. So, we need to
keep track of a variable, at run-time, which increments every time we
call a function, once for each of the function's inputs. The goal is to
never re-use variables for functions that are being executed
simultaniously.

f(x) -> cond (= x ()) () true ((f (cdr (x))) drop %x needs to still
exist at this point, with value 'x' x)

Fdepth will keep track of how many variables have been defined. When
returning from a function, fdepth needs to decrease by the number of
variables to to the caller function.

When calling a function, Fdepth needs to increase by the number of
variables to the caller function.

So variables in functions get compiled something like this:

(define func1 (x y) (+ x y)) (define func2 (x y) (+ (apply func1 (x y))
y)) (define func3 (x y) (apply func2 (x y)))

macro Fname 9999 ; macro Fdepth Fname @ ; macro A1 Fdepth 0 + ; macro A2
Fdepth 1 + ; : func1 A1 ! A2 ! A1 @ A2 @ + ; : func2 A1 ! A2 ! A1 @ A2 @
Fdepth 2 + Fname ! func1 call Fdepth 2 - Fname ! A2 @ +; : func3 A1 ! A2
! A1 @ A2 @ func2 call ;

: func1 + ; : func2 dup tuck func1 call + ; : func3 func2 call ;

<sup>6</sup>
***

related: [æternity DApp Development](æternity-DApp-Development),
[æternity Scripting Language Examples](æternity-Scripting-Language-Examples)

***

Sources:

| No | Type | Source                                                                                    |
|:---|:-----|:------------------------------------------------------------------------------------------|
| 1  | docs | [SL docs](../../../../aeternity/chalang/blob/master/README.md)                            |
| 2  | docs | [TestNet docs](../../../../aeternity/testnet/tree/master/docs/)                           |
| 3  | docs | [Opcodes](../../../../aeternity/chalang/blob/master/Opcodes.md)                           |
| 4  | docs | [BumblebeeBat/chalang](../../../../BumblebeeBat/chalang/tree/master/docs)                 |
| 5  | docs | [backtracking](../../../../BumblebeeBat/chalang/tree/master/docs/compile_backtracking.md) |
| 6  | docs | [compile functions](../../../../BumblebeeBat/chalang/tree/master/docs/compile_functions.md) |
