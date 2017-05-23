**API-Beispiele**

Hier entdecks du wie man mit der æternity software und den [API Befehlen]([German]API-Commands) umgeht.

Um die Befehle und Funktionen in das Ziel System zu bekommen benötigt man das Programm ‚curl‘

- ‚-i (Parameter) = Include protocol headers in the output (H/F)‚
- ‚-d (Parameter) = HTTP POST data (H)‚

Sehe dir folgendes Beispiel an. **"add_peer"** im Quellcode sieht das so aus:
`add_peer(IP, Port) ->`

Hier als Beispiel haben wir zwei Variablen: IP und Port
- IP: Die Variable wurde so deklariert: `-define(IP, {46,101,103,165}).`, daraus folgt das diese in jene Klammern gesetzt werden muss [ und ]
- Port: ist wie folgt definiert worden `-define(Port, 8080).`, als Integer Typ.

Bedeuted, dass unterschiedlich definierte Variablen auch entsprechend formatiert werden müssen um an den Server
weiter gereicht werden zu können.

- Integer Typ = [3010] or [,3010]
- Text Typ  = ["3010"]
- binärer Typ  = [<<>>]
- Puffer       = [<<"[\"dice\", 100]">>}]
- diese Klammer { wird zu dieser [
- und diese Klammer } zu dieser hier ]
- später mehr hierzu

**Curl String Formatierung:**

Folgendermaßen sind die Strings auf gebaut:

>["Functions-Name", formatierte Variable, und immer so weiter] http://server-ip:port


**Eine Funktion oder einen Befehl aufrufen:**

Einfach die gewünschte Funktion auswählen [link]([German]Api-Commands). `curl -i -d ["height"]' http://localhost:3011`

***
Zugriff auf den Quellcode der Befehle und Funktionen erhälst du hier: [(en)easy.erl](../../../../aeternity/testnet/blob/master/src/networking/easy.erl)

***

1. Beispiel zum Hinzufügen eines æternity-Servers mit dem du deine Blöcke teilen / syncronisieren möchtest.
In diesem Beispiel sind beide æternity-Server auf der gleichen Maschine.

```
curl -i -d '["add_peer", [127,0,0,1], 3010]' http://localhost:8041
```

#Beispiel einer æternity-Server Antwort

```
HTTP/1.1 200 OK
server: Cowboy
date: Fri, 14 Apr 2017 09:49:41 GMT
content-length: 4
content-type: application/octet-stream
Access-Control-Allow-Origin: *

"ok"
```
***

2. Beispiel: Api Zugriff von einem Javascript aus.
Versichere dich, dass die Datei 'rpc.js' geladen ist:

```
local_get(["add_peer", [127,0,0,1], 3010]);
```
***

[(en)Interner API Quellcode](../../../../aeternity/testnet/blob/master/src/networking/internal_handler.erl)

***


3. Beispiel: Abfrage des Headers eines anderen æternity-Node/Server's

Hiermit wird der "Genesis Block" abgefragt:

```
curl -i -d '["header", 0]' http://localhost:8040
```

Beachte bitte das die PortNummern (hier 8040) und (8041) sich anders verhalten.
- 8040 ist für externe Zugriffe gedacht und
- 8041 ist nur für interne Zugriffe geschaffen
- Startest du deinen Server mit dem Port 3310 dann ist immer um eines höher der Port für den internen Zugriff.
Es ist aber auch möglich direkt in den Quellcode einzugreifen und den Abstand manuel fest zu legen.


Beispiel einer æternity-Server Antwort

```
HTTP/1.1 200 OK
server: Cowboy
date: Fri, 14 Apr 2017 09:56:29 GMT
content-length: 53
content-type: application/octet-stream
Access-Control-Allow-Origin: *

["ok","AAAAAAAAAAAAAAAA1oYN5PPka/zJxej5AAAAAAAP8AAB"]
```
***

4. Beispiel: Abfrage des "Genesis Block's" von einem Javascript aus.

```
function callback(x) {
	 console.log("the header is ");
	 console.log(x);
};
get(["header", 0], callback);
```

Der æternity-Server übermittelt diesen dann auch.

[Externe Api's sind hier definiert](../../../../aeternity/testnet/blob/master/src/networking/handler.erl)

Hinweis: Ein æternity-Node ist das gleiche wie ein æternity-Server
***
mehr erfahren: [(en)Ubuntu Node Commands](Ubuntu-Node-Commands), [Api-Commands]([German]Api-Commands), [Terminal Interface Commands]([German]Terminal-interface-commands)

Probleme? [prüfe ob es ungelöste API Fälle gibt](https://github.com/aeternity/testnet/issues?q=api)

Quelle: [(en)api_examples.md](../../../../aeternity/testnet/blob/master/docs/api_examples.md)

- Übersetzung: [Api Befehle(original)](Api-Commands)
***

Fragen? Kein Problem! Hier gibt es einen [Slack-Channel](https://aeternity.slack.com/)
