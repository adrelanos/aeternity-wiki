# DApp Development Einführung in deutsch

Zunächst mal zum Begriff DAPP an sich selbst. Die Welt ist sich auch
nicht immer einig was denn nun DAPP bedeuten soll oder nicht.

(D)ezentralisierte App. Ich versuche nicht trocken zu wirken daher mein
vieles Prosa. Ein kleines Beispiel für eine mini Dapp:

Du lädst nun über Github ein Programm herunter, dort erhälst du den
Sourcecode mit hilfe dessen kannst du: alle Teile einsehen, sofern deine
Kenntnisse dafür ausreichend sind und das Programm zu einem lauffähigen
zusammenbauen.

Voraussetzungen, dass diese Programm sich nun Dapp nennen darf sind:
* es läuft auf einem Server / Computer deiner Wahl
* es kann gerade eben in China laufen und dann wieder in Deutschland
* du alleine kannst die völlige Steuereung übernehmen

Im Vergleich zu einer APP, kann die APP eben auf einem Server laufen und
du lädst dir nur einen Client herunter um daran teilzuhaben. Klassiker:
Multi-Player-Online Spiel. Ein Beispiel für eine DAPP wäre dann Moorhuhn.

Bei diesen klassikern fehl nur eines: Zugriff auf eine Blockchain-Technologie
***

Hier findese du einige Beispiele von [ZACK](https://github.com/aeternity/wiki/wiki/æternity-Team/#zack-hess)

>Schaue dir den Dice Smart Contract an um eine Idea zu bekommen wie
>State Channel Anwenungen aussehen können. Wie beim Roulett: Schwarz
>oder Rot die Chancen stehen 50/50 unentschieden.

- [/tree/master/src/dice.erl](../../../../aeternity/testnet/tree/master/src/dice.erl)
- [/master/src/networking/handler.erl](../../../../aeternity/testnet/tree/master/src/networking/handler.erl#L104)
- [/master/src/easy.erl#L96](../../../../aeternity/testnet/tree/master/src/easy.erl#L96)
- [/master/src/networking/internal_handler.erl#L55](../../../../aeternity/testnet/tree/master/src/networking/internal_handler.erl#L55)

>**Zack sagt:** It is a little spread around now. We need a way to
>organize dapps so it is easy to upgrade a basic aeternity node to
>support whatever dapp you want.

Die Sprache in der die Smart Contracts geschrieben werden:
[/aeternity/chalang](../../../../aeternity/chalang)

**Hier die Übersicht des Hauptordners:**

| No |                                                                                                |
|:---|:-----------------------------------------------------------------------------------------------|
| 1  | [arithmetic_chalang.erl](../../../../aeternity/chalang/blob/master/src/arithmetic_chalang.erl) |
| 2  | [chalang.app.src](../../../../aeternity/chalang/blob/master/src/chalang.app.src)               |
| 3  | [chalang.erl](../../../../aeternity/chalang/blob/master/src/chalang.erl)                       |
| 4  | [chalang_app.erl](../../../../aeternity/chalang/blob/master/src/chalang_app.erl)               |
| 5  | [chalang_sup.erl](../../../../aeternity/chalang/blob/master/src/chalang_sup.erl)               |
| 6  | [compiler_chalang.erl](../../../../aeternity/chalang/blob/master/src/compiler_chalang.erl)     |
| 7  | [fractions.erl](../../../../aeternity/chalang/blob/master/src/fractions.erl)                   |
| 8  | [test_chalang.erl](../../../../aeternity/chalang/blob/master/src/test_chalang.erl)             |

**Wofür die einzelnen Module stehen und was sie bewirken:**
1. arithmetic_chalang (wie die Arithmetik eingebettet wurde)
>Beispiel: `int_arithmetic(?add, A, B) -> A+B;`
>
>1. chalang.app.src (wird benötigt um die Chalang app zu kompilieren)
>2. chalang.erl (op_gas limitiert den Ablauf in der Zeit und ram_gas in
>   Raum, hier werden Variablen deklariert)
>3. chalang_app.erl (wird benötigt um die Chalang app zu kompilieren)
>4. chalang_sup.erl API Functionen, Supervisor callbacks, Helfer Macro's
>   zur Deklarierung der Kindes des Vaters (children of supervisor)
>5. compiler_chalang.erl Die Function ‚doit‘ wird in einigen Teilen der
>   æternityApp genutzt NewFunctions = dict:store(Name, Signature,
>   Functions) hier muss noch etwas Zeit investiert werden um die
>   Abläufe zu systematisieren.
>6. fractions.erl (im Christentum) Das Brechen des Brotes. Ein
>   numerisches Vielfaches das keine Ganze Zahl ist.
>   negate,add,sub,mul,divide,to_int,exponent,lt,gt,equal,is_fraction,sqrt
>7. test_chalang.erl Zum Testen und laufen lassen von
>   Scripts(run_script) wie satoshi_dice.fs (.fs hier werden Orakles geformt)

## Daten Struktur

Um Daten zu speichern besitzt die VM (Virtual Machine) einen
Hauptspeicher und einen zweiten Speicher (Nebenspeicher). Dort können
Variablen abgelegt werden. 

Das Prinzip nach dem Daten dort eingelagert werden können nennt sich
LIFO. 

>(L)ast(I)n(F)irst(Out)

Wer zuletzt auf die Party kommt geht als erster.

Folgende Typen können als Variablen abgespeichert werden:
* Listen
* Binär Daten

Wenn binäre Daten 32 Bit lang sind, dann können wir damit arithmetische
Operationen damit ausführen. Tja dann füllen wir eben mit Nullen auf
damit dies auf 32 Bit kommen. :)<sup>4</sup>


***

lese mehr: [æternity DApp Development](æternity-DApp-Development)

***

Sources:

| No | Type | Source                                                                                     |
|:---|:-----|:-------------------------------------------------------------------------------------------|
| 1  | docs | [SL docs](../../../../aeternity/chalang/blob/master/README.md)                             |
| 2  | docs | [TestNet docs](../../../../aeternity/testnet/tree/master/docs/)                            |
| 3  | docs | [Opcodes](../../../../aeternity/chalang/blob/master/opcodes.md)                            |
| 4  | docs | [data_structures.md](../../../../BumblebeeBat/chalang/tree/master/docs/data_structures.md) |
