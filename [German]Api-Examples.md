**API-Beispiele**

Hier entdeckstu wie man mit der æternity software und den [API Befehlen]([German]API-Commands) umgeht.

Um die Befehle und Funktionen in das Ziel System zu bekommen benötigt man das Programm ‚curl‘

- ‚-i (Parameter) = Include protocol headers in the output (H/F)‚
- ‚-d (Parameter) = HTTP POST data (H)‚

Sehe die folgendes Beispiel an. **"add_peer"** and inside the source command:
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

>["function-name", variable formatted, and so on] http://server-ip:port


**Call a function:**

just paste the function inside the quotes. `curl -i -d ["height"]' http://localhost:3011`

***
The source file for the curl api commands for using with curl, you find
inside this file: [easy.erl](../../../../aeternity/testnet/blob/master/src/networking/easy.erl)

***

1. Example of how to add a node to the list of nodes you share blocks
with. This is an example of accessing the local api on the same machine.

```
curl -i -d '["add_peer", [127,0,0,1], 3010]' http://localhost:8041
```

#example response

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

2. Example: Executing this api request from **javascript**
first make sure that rpc.js is loaded, then you can do this:

```
local_get(["add_peer", [127,0,0,1], 3010]);
```
***

[The internal API is defined here](../../../../aeternity/testnet/blob/master/src/networking/internal_handler.erl)

***


3. Example: Now an example of accessing an api of a different node.

This is how you request the header of the genesis block.
Notice that the ip for external api is one lower than the ip for the api
that is only on the same node.

```
curl -i -d '["header", 0]' http://localhost:8040
```

example response

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

4. Example: Here is an example of accessing the genesis block from javascript

```
function callback(x) {
	 console.log("the header is ");
	 console.log(x);
};
get(["header", 0], callback);
```

[The external API is defined here](../../../../aeternity/testnet/blob/master/src/networking/handler.erl)

***
related: [Ubuntu Node Commands](Ubuntu-Node-Commands), [Api-Commands](Api-Examples), [Terminal Interface Commands](Terminal-interface-commands)

Issue? [check now for an issue about the api](https://github.com/aeternity/testnet/issues?q=api)

source: [api_examples.md](../../../../aeternity/testnet/blob/master/docs/api_examples.md)