## Commands

First you must install and compile eaternity. Instructions for Ubuntu and Mac are [here.](https://github.com/aeternity/testnet/wiki/Troubleshooting#for-ubuntu)   

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

`keys:sigh(Transactions, AccountRoot).`

To manually sign raw binary data:

`keys:raw_sign(<<"binary date">>).`

### Passwords and Keys

The node keeps an encrypted copy of your private key. The decrypted copy is only stored in RAM.                        

You can generate a new private key this way:( !! Warning !!  This deletes your old private key!!)

`keys:new("password").`

To load a private key into an existing node:

`keys:load(Pubkey, Privkey, password").`

You can set or change the password for encryption like this:

`keys:change_password("old_password", "new_password").`

_The default password on a new node is ''''', the empty string._








## 


## 

 **//TODO Add more node commands etc.  Help would be appreciated!! .**

# 

Source:[/aeternity/testnet](https://github.com/aeternity/testnet/blob/master/README.md)



