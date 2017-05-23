# aeternity Testnet: Setup, start und Benutzung

Mit der Installation des Testnet hatte ich einige Probleme und habe dann eine Lösung
hierzu erstellt in dem ich das original ‚setup_test.sh‘ Script von Zack [Link original Script](../../../../aeternity/testnet/blob/master/setup_test.sh) modifiziert habe.

Aus dieser Arbeit heraus ist diese neue Script geworden [initd-aeternity.sh](../../../../Zwilla/aeternity-testnet/blob/master/initd-aeternity.sh). Gerne kann es in die aktive Entwicklung von aeternity übernommen werden



## Handhabung des initd-aeternity Scripts

So gehts? | BEFEHL
------------ | -------------
Starting Testnet | `sh setup_test.sh`
Stop Testnet | `sh initd-aeternity.sh stop`
Access screen session 3010| `screen -r aeternity-3010`
Access screen session 3020| `screen -r aeternity-3020`
Access screen session 3030| `screen -r aeternity-3030`

* Tabelle 2
***

# Wie sind die Abläufe?

Das neue Script‚ [setup_test.sh](https://github.com/Zwilla/aeternity-testnet/blob/master/setup_test.sh) ‚
wird drei neue Ordner anlegen „testnet-folder“ oberhalb des Ordners von dem aus du das Script aufrufst.

**Neue Ordner:**

- aeternity-testnet3010
- aeternity-testnet3020
- aeternity-testnet3030

**(WARNUNG! STARTE DAS SCRIPT NICHT AUS DIESEN ORDNERN HERAUS ..3010/20/30)**

 * Dann wir die Testnet App compiled und das Testnet von überflüssigem gereinigt.
 * Für jeden Server der erforderlich ist (3) wird ein eigener NODE gestartet!

 Du kannst jeden aeternity Node über seine Screen Session aufrufen (sieh Tabelle 2).
 * Node 3010 starts as mining node
 * Node 3020 and 3030 as full node

 Um ein paar Tests auszuführen rufe über das Terminal dieses Script auf.
 [lightning_test.sh](https://github.com/Zwilla/aeternity-testnet/blob/master/tests/lightning_test.sh)


  Original Doku hier: https://github.com/Zwilla/aeternity-testnet/blob/master/docs/testnet.md

  Nach dem aufrufen des test_setup Scripts bekommst du folgendes Menu angezeigt:

Wähle  | BEFEHL
------------ | -------------
 (1) update and setup! | Setup, update und start des testnet
 (2) start now!        | startet ein bereits installiertes Testnet
 (3) how to?           | Zeigt diese Tabelle hier an
 (4) clean             | Reinigt alles und löscht die extra Ordner
 (5) run tests!        | startet die lightning Tests
 (6) exit!             | beendet dieses Script/Menu

 __**Screen session how to:**__

  Aktion  | How to
  ------------ | -------------
  öffnen der Screen Session | screen -r (see above)
  beenden der Screen Session | CTRL + a d
  zeigt laufende Sessions an| screen -w
  stopt alla Sessions | sh initd-aeternity.sh stop

Warning! Community Inhalte! * 17th May 2017 @zwilla
***
Translations: [German Testnet setup start and use]([German]-Testnet-setup-start-and-use)
***
Stay tuned this page will be updated recently. Feel free to add questions to this page!
***

### Questions about the æternity Testnet
add your’s here
1. Hmmm..
2. hmmm …
3. ???

***
Note! This is a pure community content! * updated 17th May 2017 @zwilla
***
Page of origin: [Testnet setup start and use](Testnet-setup-start-and-use)
***
Stay tuned! This page will be updated recently. Feel free to add questions to this page!
***

  Donate to .. and support Zwilla:
  * btc: -[1DaGkc1Uv4GeCSpjkrMVzCA35ENmrd526V]
  * eth: -[0x284DbB6139e2e08cd3D3BE6f51306c19cAB04e3c]
  * ltc: -[LNvu63U68G72KXHWP5yqSuSYpoa7ef58c7]
  * æon: -[0x] (æternity Tokens)