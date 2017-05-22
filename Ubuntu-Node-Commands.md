## Download, install and Start the blockchain
First, you must download and install æternity. Instructions for [Ubuntu](Troubleshooting#for-ubuntu) and for [Mac](Troubleshooting#for-mac).

Then, before you can start executing commands you have to start the node. To start it execute the `start.sh` script using the following command from inside the node folder:
```
sh start.sh
```

## Commands
List:
   * [Sync with the network](#sync-with-the-network)
   * [Mining](#mining)
   * [Spend](#spend)
   * [Last transactions](#last-transactions)
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
   * [Contracts](#contracts)
### Sync with the network
To sync with a network and download blockchain:
```
sync:start().
```
## 
### Mining
To start mining with all CPU cores:
```
mine:start().
```
To stop mining:
```
mine:stop().
```
To check if you are currently mining:
```
mine:is_on().
```
If it answers **Go**, it's mining.
## 
### Spend
```
easy:spend(To, Amount).
```
Where:
- `To` is the recipient's account ID.
- `Amount` is the amount to be transferred.

## 
### Last transactions
```
tx_pool:data().
```
## 
### Account ID
To find out account ID:
```
keys:id().
```
##
### Public key
To find out your public key run:
```
keys:pubkey().
```
##
### Address
To find out your address:
```
keys:address().
```
If it returns something less than 1, that means you don't have an account yet.
## 
### Shared Secret
To calculate a shared_secret with a partner, you need a copy of their public key. Then you can use following command to get the Shared Secret:
```
keys:shared_secret(Pubkey).
```
## 
### Balance
To check your balance:
```
easy:balance().
```
## 
### Stop/Off
To stop a running node:
```
easy:off().
```
## 
### Lock and unlock
To secure your node so no one can sign the transactions, you can either turn off the node, or you can run this command:
```
keys:lock().
```
To check if your node is locked:
```
keys:status().
```
To unlock your node so that you can start signing transactions again, run this command:
```
keys:unlock("password").
```
## 
### Signing
First you have to have your keys unlocked. See [here](#Lock and Unlock) Then, to manually sign a transaction:
```
keys:sign(Transactions, AccountRoot).
```
To manually sign raw binary data:
```
keys:raw_sign(<<"binary date">>).
```
## 
### Passwords and Keys

The node keeps an encrypted copy of your private key. The decrypted copy is only stored in RAM.                        

You can generate a new private key this way: ( !! Warning !!  This deletes your old private key!!)
```
keys:new("password").
```
To load a private key into an existing node:
```
keys:load(Pubkey, Privkey, "password").
```
To change an account password:
```
keys:change_password("old_password", "new_password").
```
## 
### Channels
Making a channel with the server:
```
easy:new_channel(Balance, ReceivingLimit).
```
Where:
- `Balance` is how much of your money you put into the channel.
- `ReceivingLimit` is how much money the server puts into the channel.

Note: `ReceivingLimit` This is the maximum amount of money that can be sent to you until the channel runs out of space. `ReceivingLimit` needs to be bigger then `Balance` or the server will not let you make the channel.
???Fee is the transaction fee, so that this transaction will be included into a block soon.??? (missing argument?)

To check your balance in the channel:
```
easy:channel_balance().
```
To gamble with the server:
```
easy:dice(Amount).
```
To close the channel and get your money out:
```
easy:close_channel().
```

After closing channel you need to sync with the network to see if your channel is closed.

If your channel partner disappears, or breaks, you can still get your money without his help. Start with a solo-close transaction, then wait over 100 blocks, then do a channel timeout transaction.
```
easy:solo_close_channel().
```
### 
```
easy:channel_timeout().
```
    


### Contracts
* coming soon
## 


## 

 **//TODO  Add more commands.**

# 

Source: zack-bitcoin, keypair and stefek99 [/aeternity/testnet](https://github.com/aeternity/testnet/blob/master/README.md) and [/testnet/docs](https://github.com/aeternity/testnet/blob/master/docs/keys.md)

