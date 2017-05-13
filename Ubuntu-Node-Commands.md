## Commands

First you must download and install æternity. Instructions for [Ubuntu](Troubleshooting#for-ubuntu) and for [Mac](Troubleshooting#for-mac)  

### Start the blockchain
Start your node with the following script:

`sh start.sh`

### Sync with the network
To sync with the network and download the blockchain:

`easy:sync().`

### Mining
To start mining with all CPU cores:

`mine:start().`

To stop mining:

`mine:stop().`

To check if you are currently mining:

`mine:is_on().`

If it answers **Go**; then its mining

### Spend

`easy:spend(To, Amount).`

_"To"_ is the recipient's account ID.

### Last transactions

`tx_pool:data().`

### Find out your account ID, public key, and address with these 3 commands
To find out account ID:

`keys:id().`

To find out your public key run:

`keys:pubkey().`

To find out your address:

`keys:address().`

If it returns something less than 1, that means you don't have an account yet.

### To calculate a shared_secret with a partner, you need a copy of their public key

`keys:shared_secret(Pubkey).`

### Check your balance

`easy:balance().`

### To stop a node run

`easy:off().`

### Securing your node

To secure your node so no one can sign transactions, you can either turn off the node, or you can run this command:

`keys:lock().`

To check if your node is locked:

`keys:status().`

### Signing

To unlock your node so that you can start signing transactions again, run this:

`keys:unlock("password").`

To manually sign a transaction:

`keys:sign(Transactions, AccountRoot).`

To manually sign raw binary data:

`keys:raw_sign(<<"binary date">>).`

### Passwords and Keys

The node keeps an encrypted copy of your private key. The decrypted copy is only stored in RAM.                        

You can generate a new private key this way: ( !! Warning !!  This deletes your old private key!!)

`keys:new("password").`

To load a private key into an existing node:

`keys:load(Pubkey, Privkey, "password").`

To change the address password:

`keys:change_password("old_password", "new_password").`


## 


## 

 **//TODO  Add more commands. Proof read and correct any syntax errors.   Help would be appreciated !! .**

# 

Source: zack-bitcoin, keypair and stefek99 [/aeternity/testnet](https://github.com/aeternity/testnet/blob/master/README.md) and [/testnet/docs](https://github.com/aeternity/testnet/blob/master/docs/keys.md)


