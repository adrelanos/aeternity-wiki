## API Commands internal and external

***

**Hier wirst du:**

- [alle Api Befehle und Funktionen finden](#alle-æternity-api-funktionen)
- [erfahren wofür diese sind.](#aktionen-der-api-befehle)
- [was du tun musst bevor du beginnst](#setup-vor-benutzung-der-api-befehle)
- [weitere (en)Erklärungen zu den Befehlen](Ubuntu-Node-Commands#commands)

Quelle für die Api Befehle findest du hier:
[easy.erl](../../../../aeternity/testnet/blob/master/src/easy.erl)

***

### Alle æternity Api Funktionen

| Funktionen                  | Variablen                                  | ok  | Aktion                             |
|:----------------------------|:-------------------------------------------|:----|:-----------------------------------|
| "height"                    | keine notwendig                            | [x] | zeigt den letzten Block an         |
| "top"                       | keine notwendig                            | [x] | zeigt den aktuellen Block an       |
| "sign"                      | TX                                         | [x] | signiere                           |
| "tx_maker"                  | F                                          | [ ] |                                    |
| "create_account"            | (NewAddr, Amount)                          | [x] | neues Konto anlegen                |
| "spend"                     | (ID, Amount))                              | [x] | sende tokens                       |
| "delete_account"            | (ID)                                       | [x] | lösche Konto mit der ID            |
| "repo_account"              | (ID)                                       | [ ] | repo account                       |
| "new_channel_tx"            | (CID, Acc2, Bal1, Bal2, Entropy, Delay)    | [ ] | Neuer Kanal tx                     |
| "new_channel_with_server"   | (Bal1, Bal2, Delay)                        | [x] | Neuer Kanal mit Server             |
| "find_id"                   | (Name, Tree)                               | [ ] | finde diese ID                     |
| "pull_channel_state"        | (IP, Port)                                 | [x] | Kanla Status holen                 |
| "decrypt_msgs"              | more soon                                  | [ ] | dekodiere eine Nachricht           |
| "learn_secret"              | (Secret, Code)                             | [x] | Geheimnisse lernen                 |
| "add_secret"                | (Code, Secret)                             | [x] |                                    |
| "bet_unlock"                | (IP, Port)                                 | [ ] |                                    |
| "teach_secrets"             | (ID, (Secrets, IP, Port)                   | [ ] | Geheimnisse beibringen             |
| "channel_spend"             | (IP, Port, Amount)                         | [ ] | Tokens über Kanal senden           |
| "lightning_spend"           | (IP, Port, Recipient, Pubkey, Amount, Fee) | [ ] |                                    |
| "channel_balance"           | keine notwendig                            | [ ] | Kontostand Kanal                   |
| "dice"                      | (Amount)                                   | [ ] | Würfeln / Zufallsgenerator         |
| "close_channel_with_server" | (ID, IP, Port)                             | [ ] | Kanal an Server schliessen         |
| "solo_close_channel"        | (ID, IP, Port)                             | [ ] | Einseitige Kanalschießung          |
| "channel_timeout"           | (ID, IP, Port)                             | [ ] | Timeout für Kanal setzen           |
| "grow_channel"              | (CID, Bal1, Bal2)                          | [ ] | Erweitere den Kanal                |
| "channel_team_close"        | (CID, Amount, Fee)                         | [ ] | Team schliesst den Kanal           |
| "channel_repo"              | (CID, Fee)                                 | [ ] | Kanal repro                        |
| "channel_solo_close"        | (CID, Fee, SPK, ScriptSig)                 | [ ] | Einseitiges Kanal schliessen       |
| "channel_timeout"           | (CID, Fee)                                 | [ ] | Kosten für KanalTimeout            |
| "channel_slash"             | (CID, Fee, SPK, SS)                        | [ ] | Kanal umlegen                      |
| "new_question_oracle"       | (Start, Question, DiffOracleID)            | [ ] | Neue Frage an das Orakel           |
| "new_difficulty_oracle"     | (Fee, Start, ID, Difficulty)               | [ ] | Neue Schwierigkeit                 |
| "new_governance_oracle"     | (Start, GovName, GovAmount, DiffOracleID)  | [ ] | Neues Verwaltungsorakel            |
| "oracle_bet"                | (Fee, OID, Type, Amount)                   | [ ] | Orakel Wette                       |
| "oracle_close"              | (Fee, OID)                                 | [ ] | Orakel schliessen                  |
| "oracle_shares"             | (Fee, OID)                                 | [ ] | Orakel Anteile                     |
| "oracle_unmatched"          | (Fee, OracleID, OrderID)                   | [ ] | Orakel unzutreffend                |
| "account"                   | (ID)                                       | [ ] | Konto anzeigen mit ID              |
| "account"                   | keine notwendig                            | [ ] | Konto anzeigen                     |
| "mempool"                   | keine notwendig                            | [ ] | Unbestätigt Transaktionen          |
| "off"                       | keine notwendig                            | [ ] | schaltet den Node ganz aus         |
| "mine_block"                |                                            | [ ] | Mining starten                     |
| "channel_close"             | (IP, Port, Fee)                            | [ ] | Kanal schliessen                   |
| "add_peer"                  | (IP, Port)                                 | [ ] | Peer hinzufügen                    |
| "sync"                      | (IP, Port)                                 | [ ] | Syncronisiert mit Peers            |
| "pubkey"                    | keine notwendig                            | [x] | öffentlicher Schlüssel             |
| "address"                   | keine notwendig                            | [ ] | öffentliche Konto-Adresse          |
| "address"                   | (Pub)                                      | [ ] | öffentliche Adresse mit Pub.Key    |
| "id"                        | keine notwendig                            | [ ] | ID abfragen                        |
| "new_pubkey"                | (Password) ["abc"]                         | [ ] | neuer öff. Schlüssel               |
| "channel_keys"              | keine notwendig                            | [ ] | Kanal Schlüssel                    |
| "test"                      | keine notwendig                            | [x] | Antwortet hierauf "Test"           |
| "keys_status"               | keine notwendig                            | [ ] | Schlüssel Status (zu/auf)          |
| "keys_unlock"               | (Password)                                 | [ ] | Konto entsichern                   |
| keys_id_update              | (ID)                                       | [ ] | Konto sichern                      |
| "keys_new"                  | (Password)                                 | [ ] | Schlüssel-ID's aktualisieren       |
| test_it_out                 | keine notwendig                            | [ ] | nur interen Developer Testanworten |
|                             |                                            | [ ] |                                    |
|                             |                                            | [ ] |                                    |

HINWEIS! Bitte nichts hier oben löschen, bitte durchstreichen und
ersetzen falls erforderlich, damit man nachvollziehen kann was geändert
wurde. Vielen herzlichen Dank!

[x] = getestet und ok / [ ] = nicht getested oder ohne Funktion

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
