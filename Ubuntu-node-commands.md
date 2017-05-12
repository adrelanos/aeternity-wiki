## Commands

### Start the blockchain
Start your node with the following script:

`sh start.sh`

### Sync with the network
To sync with the network and download the blockchain:

`easy:sync().`

### Mining
To start mining with as CPU cores:

`mine:start().`

To stop mining:

`mine:stop().`

To check if you are currently mining:

`mine:is_on()`

### Spend

`easy:spend(To, Amount).`

_To_ is the recipient's account ID.

### Last transactions

`tx_pool:data().`

### Find out your account ID

`keys:id().`

If it returns something less than 1, that means you don't have an account yet.

### Check your balance

`easy:balance().`

### Stop a node run:

`easy:off().`






## 


## 

 **//TODO Signing transactions, generating new private keys, lock/unlock node etc.**

# 

Source: [/aeternity/testnet](https://github.com/aeternity/testnet)



