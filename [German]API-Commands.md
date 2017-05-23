## API Commands internal and external
***


**Hier wirst du:**

- [alle Api Befehle und Funktionen finden](#alle-æternity-api-functionen)
- [erfahren wofür diese sind.](#aktionen-der-api-befehle)
- [was du tun musst bevor du beginnst](#setup-vor-benutzung-der-api-befehle)
- [(en)Erklärungen zu den Befehlen](Ubuntu-Node-Commands#commands)

Quelle für die Api Befehle findest du hier:
[easy.erl](../../../../aeternity/testnet/blob/master/src/easy.erl)

***

### Alle æternity api functionen

| Function                    | Variablen                                  | ok  | Aktion                        |
|:----------------------------|:-------------------------------------------|:----|:------------------------------|
| "height"                    | none                                       | [x] | shows the latest block height |
| "top"                       |                                            | [x] |                               |
| "sign"                      | TX                                         | [x] |                               |
| "tx_maker"                  | F                                          | [ ] |                               |
| "create_account"            | (NewAddr, Amount)                          | [x] | create new account            |
| "spend"                     | (ID, Amount))                              | [x] | send tokens                   |
| "delete_account"            | (ID)                                       | [x] | delete account with id        |
| "repo_account"              | (ID)                                       | [ ] | repo account                  |
| "new_channel_tx"            | (CID, Acc2, Bal1, Bal2, Entropy, Delay)    | [ ] | new channel tx                |
| "new_channel_with_server"   | (Bal1, Bal2, Delay)                        | [x] | new channel with server       |
| "find_id"                   | (Name, Tree)                               | [ ] | find id                       |
| "pull_channel_state"        | (IP, Port)                                 | [x] | pull channel state            |
| "decrypt_msgs"              | more soon                                  | [ ] |                               |
| "learn_secret"              | (Secret, Code)                             | [x] |                               |
| "add_secret"                | (Code, Secret)                             | [x] |                               |
| "bet_unlock"                | (IP, Port)                                 | [ ] |                               |
| "teach_secrets"             | (ID, (Secrets, IP, Port)                   | [ ] | teach_secrets                 |
| "channel_spend"             | (IP, Port, Amount)                         | [ ] |                               |
| "lightning_spend"           | (IP, Port, Recipient, Pubkey, Amount, Fee) | [ ] |                               |
| "channel_balance"           | none                                       | [ ] |                               |
| "dice"                      | (Amount)                                   | [ ] |                               |
| "close_channel_with_server" | (ID, IP, Port)                             | [ ] |                               |
| "solo_close_channel"        | (ID, IP, Port)                             | [ ] |                               |
| "channel_timeout"           | (ID, IP, Port)                             | [ ] |                               |
| "grow_channel"              | (CID, Bal1, Bal2)                          | [ ] |                               |
| "channel_team_close"        | (CID, Amount, Fee)                         | [ ] |                               |
| "channel_repo"              | (CID, Fee)                                 | [ ] |                               |
| "channel_solo_close"        | (CID, Fee, SPK, ScriptSig)                 | [ ] |                               |
| "channel_timeout"           | (CID, Fee)                                 | [ ] |                               |
| "channel_slash"             | (CID, Fee, SPK, SS)                        | [ ] |                               |
| "new_question_oracle"       | (Start, Question, DiffOracleID)            | [ ] |                               |
| "new_difficulty_oracle"     | (Fee, Start, ID, Difficulty)               | [ ] |                               |
| "new_governance_oracle"     | (Start, GovName, GovAmount, DiffOracleID)  | [ ] |                               |
| "oracle_bet"                | (Fee, OID, Type, Amount)                   | [ ] |                               |
| "oracle_close"              | (Fee, OID)                                 | [ ] |                               |
| "oracle_shares"             | (Fee, OID)                                 | [ ] |                               |
| "oracle_unmatched"          | (Fee, OracleID, OrderID)                   | [ ] |                               |
| "account"                   | (ID)                                       | [ ] |                               |
| "account"                   |                                            | [ ] |                               |
| "mempool"                   | none                                       | [ ] |                               |
| "off"                       |                                            | [ ] |                               |
| "mine_block"                |                                            | [ ] |                               |
| "channel_close"             | (IP, Port, Fee)                            | [ ] |                               |
| "add_peer"                  | (IP, Port)                                 | [ ] |                               |
| "sync"                      | (IP, Port)                                 | [ ] |                               |
| "pubkey"                    | none                                       | [x] |                               |
| "address"                   | none                                       | [ ] |                               |
| "address"                   | (Pub)                                      | [ ] |                               |
| "id"                        | none                                       | [ ] |                               |
| "new_pubkey"                | (Password) ["abc"]                         | [ ] |                               |
| "channel_keys"              |                                            | [ ] |                               |
| "test"                      | none                                       | [x] |                               |
| "keys_status"               | none                                       | [ ] |                               |
| "keys_unlock"               | (Password)                                 | [ ] |                               |
| keys_id_update              | (ID)                                       | [ ] |                               |
| "keys_new"                  | (Password)                                 | [ ] |                               |
| test_it_out                 | none                                       | [ ] |                               |
|                             |                                            | [ ] |                               |
|                             |                                            | [ ] |                               |


[x] = tested and ok / [ ] = untested or not working at moment

***

### Aktionen der Api Befehle


***

### Setup vor Benutzung der Api Befehle

***

erfahre mehr: [(en)Ubuntu Node Commands](Ubuntu-Node-Commands),
[Api Beispiel]([German]Api-Examples),
[Terminal Interface Befehle]([German]Terminal-interface-commands)

Problem?
[Siehe hier nach ob Api Probleme vorliegen](https://github.com/aeternity/testnet/issues?q=api)

Quellen (en):
[api_examples.md](../../../../aeternity/testnet/blob/master/docs/api_examples.md),
[internal CLI commands](../../../../aeternity/testnet/blob/master/src/networking/internal_handler.erl),
[external api](../../../../aeternity/testnet/blob/master/src/networking/handler.erl)

***
