## API Commands to CURL

***

**Here you will:**

- [find all api commands which exist at this moment](#all-æternity-api-commands)
- [learn what are they for.](#Actions-with-api-functions)
- [what you have to setup first](#Setup-first-for-using-api-commands)

The source file for the curl api commands for using with curl, you find
inside this file:
[easy.erl](../../../../aeternity/testnet/blob/master/src/easy.erl)

***

### All æternity api functions

| Function                  | Variables                                        | ok  | Action                        |
|:--------------------------|:-------------------------------------------------|:----|:------------------------------|
| "height"                  | none                                             | [x] | shows the latest block height |
| "top"                     |                                                  | [x] |                               |
| "sign"                    | TX                                               | [x] |                               |
| "tx_maker"                | F                                                | [ ] |                               |
| "create_account"          | (NewAddr, Amount)                                | [x] | create new account            |
| "spend"                   | (ID, Amount))                                    |     | send tokens                   |
| "delete_account"          | (ID)                                             |     | delete account with id        |
| "repo_account"            | (ID)                                             |     | repo account                  |
| "new_channel_tx"          | (CID, Acc2, Bal1, Bal2, Entropy, Delay)          |     | new channel tx                |
| "new_channel_with_server" | (Bal1, Bal2, Delay)                              |     | new channel with server       |
| "find_id"                 | (Name, Tree)                                     |     | find id                       |
| "pull_channel_state"      | (IP, Port)                                       |     | pull channel state            |
| "decrypt_msgs"            | more soon                                        |     |                               |
| "learn_secret"            | (Secret, Code)                                   |     |                               |
| "add_secret"              | (Code, Secret)                                   |     |                               |
| "bet_unlock"              | (IP, Port)                                       |     |                               |
| "teach_secrets"           | (ID, [{secret, Secret, Code}|Secrets], IP, Port) |     | teach_secrets                 |
| "channel_spend"           | (IP, Port, Amount)                               |     |                               |
| "lightning_spend"         | (IP, Port, Recipient, Pubkey, Amount, Fee)       |     |                               |
| "channel_balance"         | none                                             |     |                               |
| "dice"                    | (Amount)                                         |     |                               |
|                           |                                                  |     |                               |


***

### Actions with api commands


***

### Setup first for using api commands

***

related: [Ubuntu Node Commands](Ubuntu-Node-Commands),
[Api Examples](Api-Examples),
[Terminal Interface Commands](Terminal-interface-commands)

Issue?
[check now for an issue about the api](https://github.com/aeternity/testnet/issues?q=api)

source:
[api_examples.md](../../../../aeternity/testnet/blob/master/docs/api_examples.md),
[internal CLI commands](../../../../aeternity/testnet/blob/master/src/networking/internal_handler.erl),
[external api](../../../../aeternity/testnet/blob/master/src/networking/handler.erl)

***
