## Download, install and Start the blockchain

First, you must download and install æternity. Instructions for
[Ubuntu](Troubleshooting#for-ubuntu) and for
[Mac](Troubleshooting#for-mac).

Before you can start executing commands, you have to start the node. In
order to start the node you must execute the following command.

```
sh start.sh
```

Commands
========

List:
* [Sync with the network](#sync-with-the-network)
* [Mining](#mining)
* [Spend](#spend)
* [Lookup a Block or Transaction](#lookup-a-block-or-Transaction)
* [Account ID](#account-id)
* [Public key](#public-key)
* [Address](#address)
* [Shared Secret](#shared-secret)
* [Balance](#balance)
* [Stop/Off](#stopoff)
* [Lock and Unlock](#lock-and-unlock)
* [Signing](#signing)
* [Passwords and Keys](#passwords-and-keys)
* [Channels](#channels)
* [Oracles](#oracles)

***

Sync with the network
---------------------

To sync with a network and download blockchain:

```
sync:start().
```

***

Mining
------

To start mining with all CPU cores:

```
mine:start().
```

***

To stop mining:

```
mine:stop().
```

***

To check if you are currently mining:

```
mine:is_on().
```

> Note: If it answers **Go**, it's mining!

***


Spend
-----

```
easy:spend(To, Amount).
```

Where:
- `To` is the recipient's account ID.
- `Amount` is the amount to be transferred.

***

Lookup a Block or Transaction
-----------------------------

Current Transaction(s) in the memory pool. Will be included in the next
block.

```
easy:mempool().
```

***

To look up a block by its number.

```
block:read_int(4)
```
> Note: This command is looking up block number 4. Just place the block number you are looking for in between the Parentheses ``()``. 

***

To look up the top blocks

```
block:read_int(easy:height()).
```

***

Last transactions

```
tx_pool:data().
```

***

Account ID
----------

To find out account ID:

```
keys:id().
```

***

Public key
----------

To find out your public key run:

```
keys:pubkey().
```

***

Address
-------

To find out your address:

```
keys:address().
```

> Note: If it returns something less than 1, that means you don't have an
account yet.

***

Shared Secret
-------------

To calculate a shared_secret with a partner, you need a copy of their
public key. Then you can use following command to get the Shared Secret:

```
keys:shared_secret(Pubkey).
```

***

Balance
-------

To check your balance:

```
easy:balance().
```

***

Stop/Off
--------

To stop a running node:

```
easy:off().
```

***

Lock and Unlock
---------------

To secure your node so no one can sign the transactions, you can either
turn off the node, or you can run this command:

```
keys:lock().
```

***

To check if your node is locked:

```
keys:status().
```

***

To unlock your node so that you can start signing transactions again,
run this command:

```
keys:unlock("password").
```

***

Signing
-------

First you have to have your keys unlocked. See [here](#Lock-and-Unlock)
Then, to manually sign a transaction:

```
keys:sign(Transactions, AccountRoot).
```

***

To manually sign raw binary data:

```
keys:raw_sign(<<"binary date">>).
```

***

Passwords and Keys
------------------

The node keeps an encrypted copy of your private key. The decrypted copy
is only stored in RAM.

You can generate a new private key this way:

```
keys:new("password").
```
( **!! Warning !!** This
deletes your old private key!!)

***

To load a private key into an existing node:

```
keys:load(Pubkey, Privkey, "password").
```

***

To change an account password:

```
keys:change_password("old_password", "new_password").
```

***

Channels
--------

Join the aeternity channel network. Your balance divided by the
receiving limit needs to be bigger than 1/2. ``Delay`` is how long at
most you would have to wait to get your money out.

```
easy:new_channel_with_server(Balance, ReceivingLimit, Delay).
```

Where:
- `Balance` is how much of your money you put into the channel.
- `ReceivingLimit` is how much money the server puts into the channel.

>Note: `ReceivingLimit` This is the maximum amount of money that can be
>sent to you until the channel runs out of space. `ReceivingLimit` needs
>to be bigger then `Balance` or the server will not let you make the
>channel.

***

To spend money through the lightning network. ``Pubkey`` is the
recipients pubkey. It is not recorded on the blockchain, it is recorded
along with every signature made by them.

```
easy:lightning_spend(To, Pubkey, Amount).
```

***

Learn a secret so that you can receive a channel payment. The ``Code``
is the contract that was agreed to, the ``Secret`` is evidence to unlock
the contact.

```
easy:add_secret(Code, Secret).
```

***

Sync channel state: Ask the server if your channel has been updated, and
sync. If you received a channel payment for example, your channel state
will have been updated. If your partner received a channel payment from
you, then your channel state will be updated to reflect the new
balances. This is how you sync with that new state.

```
easy:pull_channel_state().
```

***

To check your balance in the channel:

```
easy:channel_balance().
```

***

To gamble with the server:

```
easy:dice(Amount).
```

***

To close the channel and get your money out:

```
easy:close_channel().
```

***

After closing the channel you need to sync with the network to see if your
channel is closed.

If your channel partner disappears, or breaks, you can still get your
money without his or her help. Start with a solo-close transaction, then wait
over 100 blocks, then do a channel timeout transaction.

```
easy:solo_close_channel().
```

***

```
easy:channel_timeout().
```

***

Donate money to the server.

```
easy:channel_spend(Amount).
```

***

##  Oracles

New difficulty oracle. This kind of oracle is only for measuring the
expected difficulty in the future. ``Start`` is when trading starts.
``Difficulty`` is your approximation of the future value of the
difficulty. This oracle has 3 possible outputs: Either the difficulty
you estimated is too high, it is too low, or it is good enough. If it is
good enough, then we can launch a normal oracle.

```
easy:new_difficulty_oracle(Start, Difficulty).
```

***

New question oracle. This oracle asks a true/false question about the
future. Eventually, the answer to this question will get recorded on the
oracle, and will be accessible to the smart contracts. It must reference
a difficulty oracle that closed recently at the correct price.

```
easy:new_question_oracle(Start, Question, RecentDifficultyOracle).
```

***

New governance oracle. This oracle updates the variables that define the
blockchain protocol. It must reference a difficulty oracle that closed
recently at the correct price.

```
easy:new_governance_oracle(Start, GovName, GovAmount, RecentDifficultyOracle).
```

***

Bet in an oracle type is one of the atoms in this list:
[true, false, bad] You can either bet that the answer to the question is
true or false, or you can bet that it is a bed question.

```
easy:oracle_bet(OracleID, Type, Amount).
```

***

Close an oracle. If the oracle has had the same output state for a long
enough period of time, them this is how anyone can close the channel and
end the betting period.

```
oracle_close(OracleID).
```

***

Oracle shares collect. Collect shares purchased in an oracle.

```
oracle_shares(OracleID).
```

***

Oracle unmatched. If you had unmatched trades sitting in the order book
when the oracle closed. This is how you get your money back.

```
oracle_unmatched(OracleID, OrderID).
```

***

**//TODO  Add more commands.**

***
### Source:
 zack-bitcoin, keypair and stefek99
[/aeternity/testnet](https://github.com/aeternity/testnet/blob/master/README.md)
and
[/testnet/docs](https://github.com/aeternity/testnet/blob/master/docs/keys.md)

