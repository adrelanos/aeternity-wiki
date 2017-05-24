Inhaltsübersicht / Testnet Setup, start und Benutzung
=====================================================

* [aeternity Testnet: Setup, start und Benutzung](#testnet-setup-start-and-use)
* [Handhabung des initd-aeternity Scripts](#how-to-handle-the-initd-aeternity-script)
* [Wie sind die Abläufe?](#how-it-works)
* [initd-aeternity Script Menu](#initd-aeternity-script-menu)
* [Screen session how to!](#screen-session-how-to)
* [Mining im æternity Testnet (Details)](#mining-on-æternity-testnet-details)
* [Fragen zum æternity Testnet](#questions-about-the-æternity-testnet)
* [Übersetzungen](#translations)

***

# aeternity Testnet: Setup, start und Benutzung

Mit der Installation des Testnet hatte ich einige Probleme und habe dann eine Lösung
hierzu erstellt in dem ich das original ‚setup_test.sh‘ Script von Zack [Link original Script](../../../../aeternity/testnet/blob/master/setup_test.sh) modifiziert habe.

Aus dieser Arbeit heraus ist diese neue Script geworden [initd-aeternity.sh](../../../../Zwilla/aeternity-testnet/blob/master/initd-aeternity.sh). Gerne kann es in die aktive Entwicklung von aeternity übernommen werden

[⇪](#inhaltsübersicht--testnet-setup-start-und-benutzung)
***

## Handhabung des initd-aeternity Scripts

So gehts? | BEFEHL
------------ | -------------
Testnet starten| `sh setup_test.sh`
Stoppt das Testnet | `sh initd-aeternity.sh stop`
Zugriff auf die Screen Session 3010| `screen -r aeternity-3010`
Zugriff auf die Screen Session 3020| `screen -r aeternity-3020`
Zugriff auf die Screen Session 3030| `screen -r aeternity-3030`

(Tabelle 1)

[⇪](#inhaltsübersicht--testnet-setup-start-und-benutzung)
***

## Wie sind die Abläufe?

Das neue Script‚ [setup_test.sh](https://github.com/Zwilla/aeternity-testnet/blob/master/setup_test.sh) ‚
wird drei neue Ordner anlegen „testnet-folder“ oberhalb des Ordners von dem aus du das Script aufrufst.

**Neue Ordner:**

- aeternity-testnet3010
- aeternity-testnet3020
- aeternity-testnet3030

**(WARNUNG! STARTE DAS SCRIPT NICHT AUS DIESEN ORDNERN HERAUS ..3010/20/30)**

 * Dann wir die Testnet App compiled und das Testnet von überflüssigem gereinigt.
 * Für jeden Server der erforderlich ist (3) wird ein eigener NODE gestartet!

 Du kannst jeden aeternity Node über seine Screen Session aufrufen (sieh Tabelle 1).
 * Node 3010 starts as mining node
 * Node 3020 and 3030 as full node

 Um ein paar Tests auszuführen rufe über das Terminal dieses Script auf.
 [lightning_test.sh](https://github.com/Zwilla/aeternity-testnet/blob/master/tests/lightning_test.sh)


  Original Doku hier: https://github.com/Zwilla/aeternity-testnet/blob/master/docs/testnet.md

  Nach dem aufrufen des test_setup Scripts bekommst du folgendes Menu angezeigt:

[⇪](#inhaltsübersicht--testnet-setup-start-und-benutzung)
***

## initd-aeternity Script Menu

Wähle  | BEFEHL
------------ | -------------
 (1) update and setup! | Setup, update und start des testnet
 (2) start now!        | startet ein bereits installiertes Testnet
 (3) how to?           | Zeigt diese Tabelle hier an
 (4) clean             | Reinigt alles und löscht die extra Ordner
 (5) run tests!        | startet die lightning Tests
 (6) exit!             | beendet dieses Script/Menu

(Tabelle 2)

[⇪](#inhaltsübersicht--testnet-setup-start-und-benutzung)
***

## Screen session how to!

  Aktion  | How to
  ------------ | -------------
  öffnen der Screen Session | screen -r (see above)
  beenden der Screen Session | CTRL + a d
  zeigt laufende Sessions an| screen -w
  stopt alla Sessions | sh initd-aeternity.sh stop

(Tabelle 3)

[⇪](#inhaltsübersicht--testnet-setup-start-und-benutzung)
***

## Mining im æternity Testnet (Details)

1. öffne eine Terminal Sitzung
2. In die Screen Session des Node 3010 eintauchen: 'screen -r aeternity-3010'
3. Du bist nun eingeloggt und siehst das: '>1 '
4. Gebe diesen Befehl ein: '*keys:new("YOUR_PSSWRD").*' (Standard Passwort
   ist: "abc")
5. Entsperren des Node um das Mining im æternity Testnet zu beginnen:
   '*keys:unlock("YOUR_PSSWRD").*'
6. Starte das æternity Mining: '*mine:start().*'

Hier einige hilfreiche æternity CLI Befehle:

| CLI Command         | Action                            | tested |
|:--------------------|:----------------------------------|:-------|
| '*easy:balance().*' | zeigt deinen Kontostand an | [x]    |
| '*mine:stop().*'    | stopt das Mining                  | [x]    |
| '*mine:is_on().*'   | prüft ob das Mining läuft            | [x]    |
| '*easy:off().*'     | schaltet den æternity Node/Server Dienst aus            | [x]    |
|                     |                                   | [ ]    |
|                     |                                   | [x]    |

[ x ] = getestet und läuft / [  ] = ungetestet oder ohne Funktion.

(Tabelle 4)

[⇪](#inhaltsübersicht--testnet-setup-start-und-benutzung)
***
Hinweis! Dieser Artikel ist reine Community Arbeit! * erstellt am 17. Mai 2017 @zwilla

## Fragen zum æternity Testnet

1. Hmmm..
2. hmmm …
3. ???

[⇪](#inhaltsübersicht--testnet-setup-start-und-benutzung)

***

## Übersetzung

* [(en)Testnet setup start and use](Testnet-setup-start-and-use)

***
Diese Seite ist in Überarbeitung. Wenn du Fragen hast kannst du diese gerne hier anfügen!
***
