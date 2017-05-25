![whitepaper unofficial translation](http://aeternity.de/images-by-zwilla/whitepaper-header.jpg)
## Seite 1

aeternity blockchainDie vertrauenswürdige, dezentralisierte und rein
funktionierende Orakelmaschine

6. Februar 2017 V0.1
***
* Zackary Hess[Zack@aeternity.com](mailto:zack@aeternity.com)
* Yanislav Malahov[Yani@aeternity.com](mailto:yani@aeternity.com)
* Jack Pettersson[Jack@aeternity.com](mailto:jack@aeternity.com)

* WICHTIGER HINWEIS: Dies ist eine Community Übersetzung und erhebt keinen Anspruch auf Richtigkeit
* Das original Dokument findest du hier: [original æternity Whitepaper Version 0.01 vom 06.02.2017]()

Zusammenfassung
===============
\- Seit der Einführung von Ethereum im Jahr 2014 dort hat großes Interesse
an dezentralisierten vertrauenswürdigen Anwendungen (Intelligente
Verträge / Smart Contracts). Infolgedessen haben viele versucht zu
implementierenAnwendungen mit realen Weltdaten über eine Blockkette.
WirGlaube, dass die Speicherung der Anwendung der Staat und
Code-on-Kette istAus mehreren Gründen falsch.Wir präsentieren eine hoch
skalierbare Blockchain - Architektur mit einemKonsens-Mechanismus, der
auch verwendet wird, um das Orakel zu überprüfen.Das macht das Orakel
sehr effizient, weil es die Schichtung vermeidetEin Konsensmechanismus
auf der anderen Seite. ZustandskanäleSind integriert, um die
Privatsphäre und Skalierbarkeit zu erhöhen. Token inKanäle können mit
rein funktionalem Smart übertragen werdenVerträge, die auf oracle
Antworten zugreifen können. Durch die Nichtlagerung des VertragesCode
oder Zustand on-chain, können wir intelligente Verträge machenEinfacher
zu analysieren und schneller zu verarbeiten, ohne erheblichen VerlustIn
faktischer Funktionalität.Anwendungen wie Märkte für synthetische
Vermögenswerte und VorhersageMärkte können auf globaler Ebene effizient
umgesetzt werden. MehrereTeile haben in Erlang
Proof-of-Concept-Implementierungen. EntwicklungOpment Werkzeuge und
Anwendung Essentials wie eine Brieftasche, BenennungUnd Identitätssystem
wird auch zur Verfügung gestellt.C
INHALT[ich](#seite-1)[Einführung](#seite-1)1[IA](#seite-2)[Vorherige Arbeit .](#seite-2)
. . . . . . . . . . .
.2[II](#seite-2)[aeternity blockchain](#seite-2)2[II-A](#seite-2)[Token, Konten und Blöcke](#seite-2)
. . . . .2[II-A.1](#seite-2)[Zugangstoken, Aeon](#seite-2) . . .
.2[II-A.2](#seite-2)[Konten.](#seite-2) . . . . . . . .
.2[II-A.3](#seite-3)[Name System](#seite-3) . . . . . .
.3[II-A.4](#seite-3)[Inhalt blockieren](#seite-3) . . . . .
.3[II-B](#seite-3)[Zustandskanäle](#seite-3) . . . . . . . . . . .
.3[II-B.1](#seite-3)[Intelligente Verträge](#seite-3) . . . . .
.3[II-B.2](#seite-4)[Beispiel](#seite-4) . . . . . . . .
.4[II-C](#seite-5)[Konsensmechanismus](#seite-5) . . . . . . .
.5[II-C.1](#seite-5)[Orakel](#seite-5) . . . . . . . . .
.5[II-D](#seite-5)[Regierungsführung](#seite-5) . . . . . . . . . . . .
.5[II-E](#seite-6)[Skalierbarkeit](#seite-6) . . . . . . . . . . . . .
.6[II-E.1](#seite-6)[Scheiße Bäume](#seite-6) . . . . .
.6[II-E.2](#seite-6)[Leichte Klienten](#seite-6) . . . . . . .
.6[II-E.3](#seite-6)[Zustandskanäle und paral-](#seite-6)[Lelismus](#seite-6)
. . . . . . . . . .
.6[II-E.4](#seite-6)[Transaktionen pro Sekunde bei](#seite-6)[Eine gegebene Speicheranforderung](#seite-6)
6[III](#seite-6)[Anwendungen](#seite-6)6[III-A](#seite-6)[Blockchain Essentials](#seite-6)
. . . . . . . . .6[III-A.1](#seite-6)[Identitäten](#seite-6) . . . . . .
. . .6[III-A.2](#seite-6)[Geldbörse](#seite-6) . . . . . . . . .
.6[III-A.3](#seite-6)[Nachweis der Existenz](#seite-6) . . .
.6[III-B](#seite-7)[Zustandskanalanwendungen](#seite-7) . . . . . .
.7[III-B.1](#seite-7)[Maut API](#seite-7) . . . . . . . . .
.7[III-B.2](#seite-7)[Versicherter Crowdfunding](#seite-7) . .
.7[III-B.3](#seite-7)[Kreuzketten-Atom-Swaps](#seite-7)
.7[III-B.4](#seite-7)[Stabile Vermögenswerte und](#seite-7)[Portfolio-Replikation](#seite-7)
. . . .7[III-B.5](#seite-7)[Eventverträge](#seite-7) . . . .
.7[III-B.6](#seite-7)[Vorhersagemärkte](#seite-7) . . .
.7[III-B.7](#seite-7)[Markt mit Chargenhandel](#seite-7)[Zu einem einzigen preis](#seite-7)
. . . .
.7[IV](#seite-8)[Implementierung](#seite-8)8[IV-A](#seite-8)[Virtuelle Maschine und Vertragssprache](#seite-8)8[IV-B](#seite-8)[Adoption über Web-Integration](#seite-8)
. . . . .8[IV-C](#seite-8)[Open Source Module.](#seite-8) . . . . . . .
.8[IV-D](#seite-8)[Usability und UX Design](#seite-8) . . . . . .
.8[V.](#seite-8)[Diskussion](#seite-8)8[VA](#seite-9)[Einschränkungen und Kompromisse](#seite-9)
. . . . . . .9[VA.1](#seite-9)[On-Chain-Zustand](#seite-9) . . . . . .
.9[VA.2](#seite-9)[Kostenloses Optionsproblem](#seite-9) . .
.9[VA.3](#seite-9)[Liquiditätsverlust und -zustand](#seite-9)[Kanaltopologien](#seite-9)
. . . . .9[VB](#seite-9)[Zukünftige Arbeit .](#seite-9) . . . . . . . .
. . . . .9[VB.1](#seite-9)[Funktionale Vertragssprache](#seite-9)
9[VB.2](#seite-9)[Mehrparteienkanäle](#seite-9) . . .9I. E INFÜHRUNGDie
Absicht dieser Arbeit ist es, einen Überblick zu gebenDie
aeternity-Blockchain-Architektur und mögliche ApplikationenTionen In
Zukunft werden detailliertere Beiträge veröffentlicht,Speziell für die
Konsens- und Governance-Mechanismen.Es ist jedoch zu beachten, dass
unsere Architektur ganzheitlich ist;Alle komponenten verbinden sich und
synergieren in modularer Weise.Der Rest dieses Papiers ist in vier Teile
gebrochen. Als erstes werden wirWird die grundlegenden theoretischen
Ideen vorstellen und diskutierenInformieren unsere architektur Zweitens
werden wir diskutieren1

***

## Seite 2

Beinhalten wesentliche Anwendungen, andere mögliche Anwendungsfälle
undGeben Intuitionen für die Nutzung der Plattform als
Entwickler.Drittens werden wir die aktuelle Proof-of-Concept-In Erlang
geschrieben. Wir schließen mit einer Diskussion,Einschließlich möglicher
zukünftiger Richtungen und Vergleiche mit anderenTechnologien.A.
Vorherige ArbeitBlockchains, vor allem Bitcoin, haben einen neuen Weg
gezeigtArchitektenaustausch im Internet [ [1](#seite-10) ]. Das
hatGefolgt von einer Reihe von vielversprechenden Fortschritten:
EthereumZeigte einen Weg, um Turing-komplette intelligente Kon-Durch
eine Blockchain-Architektur gesicherte Traktate [ [2](#seite-10) ];
TruthcoinErstellt Werkzeuge für die Herstellung von Orakeln auf
Blockchains [ [3]](#seite-10) , währendGroupGnosis und Augur zeigten,
wie man sie mehr machteffizient [4]; Casey Detrio zeigte, wie man Märkte
erschließtAuf Blockchains [[](#seite-10) 5]; Namecoin zeigte, wie man
das machtVerteiltes Äquivalent eines Domain Name Servers [[6](#seite-10)
]; FaktorZeigte, wie eine Blockkette, die Hashes speichert, als
verwendet werden kannEin Nachweis der Existenz für irgendwelche
digitalen Daten [ [7]](#seite-10) .Diese Technologien zeigen ein großes
Versprechen, wenn es darum gehtBereitstellung von erstklassigen
finanziellen und juristischen Dienstleistungen für jedermann.Bisher
haben sie es versäumt, zusammen zu kommenEinheitliches Ganzes, das
tatsächlich das Versprechen erfüllt. Speziell,Alle bisherigen Lösungen
fehlten in mindestens einer derFolgende Achtung: Governance,
Skalierbarkeit, Scripting SicherheitUnd billiger Zugang zu realen Daten
[Notwendigkeit cit.] . aeternity zielt darauf abUm den Stand der Technik
in all diesen Punkten zu verbessern.II. ae TERNITY BLOCKCHAINWir
glauben, dass der Mangel an Skalierbarkeit, Scripting SicherheitUnd
billiger Zugang zu realen Daten der aktuellen "smart
con-Tract-Plattformen "kommen auf drei Kernfragen. Zuerst dieDerzeit
herrschsüchtiges Design macht intelligente VerträgeGeschrieben für die
Plattform schwer zu analysieren [1](#seite-2) Und
ZustandlichkeitKombiniert mit sequentieller Transaktionsbestellung
kompliziertSkalierbarkeit [ Notwendigkeit cit.] . Zweitens sind die
hohen Kosten für die Real-Welt-Daten in das System in einem
dezentralisierten, vertrauenswürdigen undZuverlässige Weise kompliziert
oder völlig verhindert die RealisierungVielversprechender Bewerbungen .
Drittens die PlattformenSind in ihren Fähigkeiten begrenzt, um sich
selbst zu aktualisierenSich an neue technologische oder wirtschaftliche
Kenntnisse anzupassen. WirGlauben, dass jedes dieser drei Probleme eine
klare Lösung hatWege, die erforscht werden sollten.Erstens, die jüngsten
Forschungen zur staatlichen KanaltechnologieWitze, die für viele
Anwendungsfälle, halten Zustand an-Kette ist nichtNotwendigkeit
[ Notwendigkeit cit.] . Es ist sehr oft ganz möglich zu lagernAlle
Informationen in staatlichen Kanälen und verwenden nur die BlockketteUm
alle wirtschaftlichen Ergebnisse des Informationsaustauschs zu
beheben,Und als Fallback im Streitfall. Das deutet anEin alternativer
Ansatz zur Blockchain-Architektur, in demTuring-komplette
Smart-Kontrakte gibt es in staatlichen Kanälen, aberNicht auf Kette.
Dies erhöht die Skalierbarkeit seit allen Transaktionen1 Die
Schwierigkeit, staatliche Verträge zu analysieren, warDurch den
Wiedereintrittsfehler, der den "DAO" heruntergebracht hat. Das ist
passiertTrotz des Codes, der von mehreren von Ätherischen Schöpfern als
geprüft worden istSo gut wie die allgemeine gemeinschaftWerden
unabhängig und können so parallel verarbeitet werden.Darüber hinaus
bedeutet dies, dass Verträge niemals teilenStaat, die ihre Prüfung und
Überprüfung erheblich vereinfacht. WirGlaube, dass dieser Entwurf
betont, dass Blockchains sindÜber die Finanzlogik und nicht die
Datenspeicherung; es gibtDezentrale Speicherlösungen, die Blockchains
ergänzenperfekt.Zweitens haben Anwendungen wie Augur versuchtBringen
reale Daten auf die Blockkette in einem dezentral-In den Prozess, der im
Wesentlichen einen Konsens bautMechanismus in intelligente Verträge
[8 [],](#seite-10) anstatt zu nutzenDer Konsensmechanismus der
zugrundeliegenden Blockkette. DiesFührt zu Ineffizienzen, erhöht aber
nicht die Sicherheit. DasNatürliche Schlussfolgerung daraus besteht
darin, die Blockkette zu verallgemeinernKonsens-Mechanismus, so dass es
Informationen liefern kannNicht nur auf den nächsten internen Zustand,
sondern auch auf den StaatDer Außenwelt. Es könnte also argumentiert
werden, dass dieDer Konsensmechanismus von blockchain bestimmt das
Ergebnis vonLaufen, welche Komplexitätstheorie eine Orakelmaschine
trennt:Eine theoretische Maschine, die stärker ist als ein
TuringMaschine, weil es Antworten auf einige Fragen, die nicht
könnenNotwendigerweise berechnet werden, wie "Wer gewann FußballspielX?
" [Notwendigkeit cit.] .Drittens scheint es natürlich, dass der
KonsensmechanismusKönnte auch verwendet werden, um die Parameter des
Systems zu bestimmen.Dies ermöglicht es, sich an wechselnde äußere
Bedingungen anzupassenGenauso wie die neue Forschung und die jüngsten
Entwicklungen indas Feld.Der Rest dieses Abschnitts stellt die
aeternity-Blockkette vorIm Detail, beginnend mit einem kurzen Überblick
über Konten,Token, Namen und die Struktur der Blöcke. Darauf folgtEine
Erklärung unseres Ansatzes für staatliche Kanäle und smartVerträge, und
dann eine Diskussion darüber, wie die BlockketteKonsens-Mechanismus kann
sowohl zur Schaffung eines effizienten verwendet werdenOracle
Mechanismus und das System zu regieren. Schließlich, wirDiskutieren die
Skalierbarkeit aus verschiedenen Blickwinkeln.A. Token, Konten und
BlöckeTrotz "staatenlos" aus dem VertragspartnerDer aeternity-Blockchain
verfolgt mehrereVordefinierte Zustandskomponenten. Wir werden jetzt
erklären, wieEbenso wie der Inhalt jedes Blocks. Zur Vereinfachung ist
dieser AbschnittGeht davon aus, dass jeder Knoten die gesamte Blockkette
verfolgt.Mögliche Optimierungen sind in Abschnitt [II-E](#seite-6)
beschrieben [.](#seite-6)A.1) Zugriffstoken, Aeon: Zur Verwendung der
Blockkette ist nichtKostenlos, aber verlangt, dass der Benutzer ein
Token namens aeon ausgibt.Aeon werden als Zahlung für alle Ressourcen
verwendet, die man verbrauchtAuf der Plattform, sowie die Basis für
FinanzanwendungenAuf der Plattform implementiertDie Verteilung von Aeon
im Geneseblock wird seinBestimmt durch einen intelligenten Vertrag auf
Ethereum gehostet. Des WeiterenAeon wird über den Bergbau erstellt.Alle
Systemgebühren werden mit aeon bezahlt, alle klaren VerträgeSich in aeon
niederlassen.A.2) Konten: Jedes Konto hat eine Adresse und eine Bal-Aeon
und auch ein nonce, das mit jedem zunimmtTransaktion und die Höhe der
letzten Aktualisierung. Jedes Konto2

***

## Seite 3

Muss auch eine kleine Gebühr für die Zeit, die es ist zu zahlenöffnen.
Die Kosten für die Erstellung und Beibehaltung von Konten verhindernSpam
und disincentiviert state-bloat. Die Belohnung zum LöschenKonten
stimulieren die Rückgewinnung des Raumes.A.3) Namensystem: Viele
Blockchain-Systeme leiden darunterUnlesbare Adressen für ihre Benutzer.
In der Ader von AaronSwartz 'Arbeit und Namecoin, aeternity kennzeichnet
einen NamenSystem, das sowohl dezentralisiert als auch sicher
istUnterstützung von menschlich-freundlichen Namen [9 [].](#seite-10)
Der Zustand der BlockketteBeinhaltet eine Zuordnung von einzigartigen
menschlich-freundlichen Saiten zuFeste Byte-Arrays. Diese Namen können
verwendet werden, um darauf hinzuweisenDinge wie Kontoadressen auf
aeternity oder Hashes zBVon Merkle-Bäumen.A.4) Blockinhalt: Jeder Block
enthält folgendesKomponenten:• Der Hash des vorherigen Blocks.• Ein
Merkelbaum von Transaktionen.• Ein Merkel Baum der Konten• Ein
Merkelbaum von Namen.• Ein Merkelbaum von offenen Kanälen.• Ein
Merkelbaum von Orakeln, die ihr nicht geantwortet habenJeweilige fragen•
Ein Merkelbaum der Orakel antwortet.• Ein Merkle Baum von Merkle
Beweise.• Die aktuelle Entropie im Zufallszahlengenerator.Der Hash des
vorherigen Blocks ist erforderlich, um einenBestellen der Blockkette.
Der Transaktionsbaum enthält alleTransaktionen, die im aktuellen Block
enthalten sind. Mit demAusnahme des Konsens-Stimmbaums, alle Bäume sind
vollUnter Konsens: Wenn ein Baum von einem Block zu dem geändert wirdAls
nächstes muss diese Änderung auf eine Transaktion im neuen
zurückzuführen seinBlocks Transaktionsbaum und ein Merkle-Beweis für das
UpdateMuss in den Beweisbaum des Blocks aufgenommen werden. Der Zweck
vonDie drei verbleibenden Bäume werden hoffentlich klarFolgenden
AbschnittenB. StaatskanäleEine der interessantesten Entwicklungen in
derBlockchain-Raum ist in letzter Zeit der der staatlichen Kanäle. Sie
betreibenAuf dem Grundprinzip, dass in den meisten Fällen nur die
MenschenVon einer Transaktion betroffen sein müssen, um darüber zu
wissen. Im Wesentlichen,Die abschiebenden Parteien instanziieren einen
Zustand auf einer Blockkette,ZB ein Ethereum-Vertrag oder ein Bitcoin
multisig. Sie dannSenden Sie einfach signierte Updates in diesen Zustand
zwischen einander.Der entscheidende Punkt ist, dass einer von ihnen
diese nutzen könnteUm den Zustand auf der Blockkette zu aktualisieren,
aber in den meisten Fällen,Sie nicht. Damit können Transaktionen
durchgeführt werdenSo schnell wie Informationen übertragen und
verarbeitet werden könnenVon den Parteien, anstatt sie warten müssen,
bis dieTransaktion wurde validiert - und möglicherweise abgeschlossen
-Durch den Konsensusmechanismus der Blockkette.Auf aeternity, die
einzige Statusaktualisierung, die abgerechnet werden kannDie Blockkette
ist eine Übertragung von Aeon, und das einzige Aeon dasKann übertragen
werden, diejenigen, die die Transaktion ParteienBereits in den Kanal
abgelegt. Das macht alle KanäleUnabhängig voneinander, was den
unmittelbaren Nutzen hat,1Makro Gold f870e8f615b386aad5b953fe089;23Gold
Orakel4Wenn 0 1000 sonst 0 0 enden50Feige. 1. Ein einfacher Vertrag, der
eine Wette auf den Goldpreis kodiert. Die SpracheVerwendet wird der
Forth-ähnliche Chalang, der in Abschnitt [IV-A](#seite-8) vorgestellt
wird [.](#seite-8)Dass Transaktionen im Zusammenhang mit Kanälen
verarbeitet werden könnenParallel dazu den Transaktionsdurchsatz
deutlich verbessern.Die Blockkette wird nur verwendet, um das endgültige
Ergebnis zu begleichenOder um Konflikte zu lösen, die sich annähernd
analog zumJustizsystem. Allerdings, weil das Blockchain-VerhaltenWird
vorhersehbar sein, es gibt keinen Gewinn bei der Streitigkeit der
beabsichtigtenErgebnis eines Zustandskanals; Böswillige Akteure sind
angeregtSich richtig verhalten und nur den letzten Zustand auf
demBlockchain Alle zusammengenommen, das erhöht die
TransaktionGeschwindigkeit und Volumen um mehrere GrößenordnungenAls
Privatsphäre.B.1) Intelligente Verträge: Trotzdem der einzige Zustand,
derKann abgewickelt werden on-chain ist eine Übertragung von aeon,
aeternityImmer noch eine Turing-komplette virtuelle Maschine, die
kannLaufen "smart contracts". Verträge über aeternity sind
striktVereinbarungen, die Mittel nach einigen Regeln verteilen,Die in
krassem Kontrast zu den entitätsähnlichen Verträgen stehtZB Äther. Zwei
der bemerkenswerten praktischen UnterschiedeIst das standardmäßig nur
die beteiligten ParteienEinen bestimmten Vertrag und nur Parteien, die
einen offenen Zustand habenKanal kann einen gültigen Vertrag erstellen.
Wenn die Parteien einverstanden sindVertrag, sie unterschreiben und
halten Kopien für zukünftige Referenz.Es wird nur der Blockkette
vorgelegt, wenn sein Ergebnis istUmstritten, in welchem ​​Fall der Code
nur als Teil gespeichert wirdDer eingereichten Transaktion, niemals in
einem anderen Staat. Ob dasPassiert, die Blockkette verteilt die
Spielmarken nachDen Vertrag und schließt den Kanal.Als Beispiel, Abb.
[1](#seite-3) zeigt einen sehr einfachen Vertrag, derKodiert eine Wette
auf den Goldpreis zu einer bestimmten Zeit. In Zeile 1,Das Makro Gold
speichert die Kennung des betreffenden Orakels,Die zurückkehren wird,
wenn der Goldpreis unter $ 38 / g liegt1. Dezember 2016. Die Karosserie
des Vertrages wird angezeigtAuf den Zeilen 2-4: Wir schieben zuerst die
Gold-Orakel-Kennung anDen Stapel und nennen es mit Orakel, die die
verlassen wirdOracles Antwort auf die Oberseite des Stapels. Wir
verwenden das, um ein zu tunBedingte Verzweigung: Wenn das Orakel wahr
ist, drücken wir0 und 1000 zum Stapel, was anzeigt, dass 0 aeon sein
sollteVerbrannt und 1000 aeon sollte zum ersten teilnehmen inder Kanal.
Andernfalls drücken wir 0 und 0, mit dem zweiten 0Dass der andere
Teilnehmer alle aeon in derKanal. Schließlich drücken wir 0, was
genommen wird, um die nonce zu seinVon diesem Kanalzustand. Im
eigentlichen Gebrauch wäre das NonceBei der Bereitstellung erzeugt.Eine
wichtige Sache zu beachten ist, dass Verträge auf aeternityKeinen
eigenen Zustand behalten. Jeder Staat wird beibehaltenVon den
Geschädigten und eingereicht als Input bei der Ausführung.Jeder Vertrag
ist im Wesentlichen eine reine Funktion, die einige nimmt3

***

## Seite 4

1: Hashlock2Wechsel3Hash4==;Feige. 2. Ein einfaches Hakel.1Makro
Verpflichtung a9d7e8023f80ac8928334;23Verpflichtung hashlock call4Wenn 0
100 sonst 0 50 enden51Feige. 3. Mit dem Hakel, um vertrauenswürdige
Token durch einen Zwischenhändler zu schicken.Eingabe und gibt einen
neuen Kanalzustand als Ausgang [2](#seite-4) . Die VorteileDer
Verwendung von reinen Funktionen in der Software-Entwicklung im
Allgemeinen,Und insbesondere bei der Entwicklung von
Finanzanwendungen,Wurde in akademie und industrie ausführlich
dokumentiertSeit Jahrzehnten [ [10]](#seite-10) [brauchen cit.] .A)
Vertragsinteraktion und mehrstufige Verträge:Auch wenn alle Verträge
staatenlos sind undPendent von einander, Vertrag Interaktion und
StatefulnessKann noch durch Häufigkeit erreicht werden
[ Notwendigkeit cit.] . Eine einfacheHashlock ist in Abb. [2](#seite-4)
In Zeile 1 definieren wir eine FunktionGenannt hashlock, der erwartet,
dass der Stapel einen Hash enthältH und ein Geheimnis s. Es tauscht sie
auf Linie 2, um Hash zu habenDas Geheimnis auf Zeile 3, bevor man den
Gleichheitsoperator anruftHash (v) und h auf Zeile 4. Das gibt true
zurück, wenn das Geheimnis a istVorbild des Hashs Diese Funktion kann
zur Vorhersage verwendet werdenDie Ausführung von Code -
Zweigniederlassungen in verschiedenen Verträgen auf derExistenz des
gleichen Geheimwertes.Als einfache Beispielnutzung machen hashlocks es
möglichBenutzer, die keinen Statuskanal teilen, um sie vertrauensvoll zu
sendenAndere aeon, solange es einen Pfad von Kanälen zwischen gibtSie.
Zum Beispiel, wenn Alice und Bob einen Kanal haben undBob und Carol
haben einen Kanal, dann können Alice und CarolTransf durch Bob. Sie tun
dies, indem sie zwei Kopien erstellenDes in Abb. [3](#seite-4) , eine
für jeden Kanal. DasEngagement auf Linie 1 ist die Hash von einem
Geheimnis, dass AliceWählt In Zeile 3 schieben wir ihn auf den Stack und
rufen anHashlock Funktion. Welcher Zweig der, wenn das bekommtAusgeführt
hängt vom Rückgabewert von hashlock ab. EinmalDiese Verträge wurden von
allen Parteien unterzeichnet, sagt AliceDas Geheimnis, das es Bob und
Carol erlaubt, es zu benutzen, um sie zu beanspruchenÄon.Hashlocking
kann auch verwendet werden, um zB Multiplayer zu spielenSpiele in den
Kanälen, wie in Abb [.](#seite-4)

1. Jeder machtEin Kanal mit dem Game Manager, der das gleiche
   veröffentlichtVertrag zu jedem Kanal. Sagen wir sind im Spielzustand
   32,2 Es ist zu beachten, dass, da Verträge Antworten von Orakeln
   lesen könnenUnd einige Umgebungsparameter sind sie nicht ganz reine
   Funktionen.Allerdings ändern sich Orakel-Antworten niemals, sobald
   sie bereitgestellt wurden undKann auf den rechnerischen Reichtum des
   Orakels hingewiesen werdenMaschine, anstatt eine Verunreinigung zu
   sein. Umgebungsparameter werden berücksichtigtEin "notwendiges Übel"
   und wird idealerweise angemessen umgestelltHochrangige
   Sprachen.1Makro Verpflichtung a9d7e8023f80ac8928334;23Verpflichtung
   hashlock call4Wenn State33 sonst State32 endet5AnrufFeige. 4. Ein
   vereinfachtes Beispiel für die Verwendung des Hakens, um einen
   Multiplayer zu spielenSpiel in Kanälen.Definiert durch die Funktion
   State32, und wir wollen vertrauensvollGleichzeitig alle Kanäle auf
   den Zustand 33 aktualisierenGame Manager zeigt das Geheimnis, es
   verursacht alle KanäleGleichzeitig zu aktualisieren.B) Dosierte
   Ausführung: Die Ausführung des Vertrages erfolgtIn ähnlicher Weise
   wie Ethereums "Gas", aber die Natur benutzt zweiVerschiedene
   Ressourcen für seine Dosierung, eine für die Zeit und eine fürPlatz.
   Beide werden für die Verwendung von Aeon von der Partei bezahltDas
   verlangt die Ausführung.Dies könnte als unerwünscht angesehen werden,
   weil es wahrscheinlich istEine andere Partei, die die Notwendigkeit
   für die Blockkette verursachtBeilegung des Streits an erster Stelle.
   Solange aberAlles Geld in den Kanal ist nicht für Wetten verwendet,
   kann diesIm Vertragskodex wirksam aufgehoben werden, da es
   dieFähigkeit, Mittel von einer Partei zum anderen neu zu verteilen.
   EsIst in der Regel in der Regel gute Praxis zu vermeiden, alle Mittel
   zu verwendenIn einem Kanal zu handeln, weil es das Verlieren
   entkräftetBei der Schließung des Kanals kooperieren.B.2) Beispiel:
   Lassen Sie uns alle diese Ideen aufErde. In der Praxis, wenn Alice
   und Bob mit der Transaktion umgehen wollenEin staatlicher kanal auf
   aeternity, sie gehen durch die folgendenVerfahren:1) Alice und Bob
   unterzeichnen eine Transaktion, die angibt, wieViel Geld jeder von
   ihnen ist in derKanal, und veröffentlichen sie in der Blockkette.2)
   Sobald die Blockkette den Kanal geöffnet hat, können sieBeide
   erstellen neue Kanalzustände, senden sie zwischenEinander und
   unterschreiben sie. Kanalzustände können entweder seinEine neue
   Verteilung der Mittel im Kanal oder aVertrag, der eine neue
   Verteilung bestimmt. Jeder vonDiese Kanalzustände haben eine
   zunehmende Nonce und sindVon beiden Parteien unterzeichnet, also wenn
   ein Streit entsteht, der spätesteDer gültige Zustand kann der
   Blockkette vorgelegt werdenErzwingt sie.3) Der Kanal kann auf zwei
   verschiedene Arten geschlossen werden:A) Wenn Alice und Bob
   entscheiden, dass sie fertig sindIhre endgültigen Guthaben
   abzuschließen und zu vereinbaren,Sie unterzeichnen beide eine
   Transaktion, die dies angibtLege es an die Blockkette, die das
   schließen wirdKanal und verteilen das Geld im Kanalentsprechend.B)
   Wenn Alice sich weigert, eine abschließende Transaktion zu
   unterzeichnenJeder Grund, Bob kann den letzten Zustand, dass beideVon
   ihnen unterzeichnet und verlangt, den Kanal zu habenGeschlossen mit
   diesem Zustand. Dies beginnt mit einem Countdown.Wenn Alice glaubt,
   dass Bob unehrlich ist,Sie hat die Gelegenheit, einen Staat zu
   veröffentlichen4

***

## Seite 5

Eine höhere nonce, die beide unterzeichnet habenBevor der Countdown
beendet ist. Wenn sie das tut,Kanal schließt sofort. Ansonsten schließt
esWenn der Countdown beendet ist.C. Konsensmechanismusaeternity
verwendet einen hybriden Proof-of-Work und
Proof-of-StakeKonsensmechanismus Die Blockreihenfolge wird bestimmtÜber
Proof-of-Work. Bestimmte Systemvariablen werden abge-Abgebaut über
On-Kette Vorhersage Markt-System, das erlaubtDie Benutzer zu beteiligen
und bringen ihr Wissen. ZumDer PoW-Algorithmus, den wir derzeit eine
Variante von Tromp's bevorzugenKuckuckszyklus, einer, der Gedächtnis
gebunden ist und auch istEin "indirekt nützlicher Proof-of-Work", da er
weniger benötigtElektrizität zu laufen, sondern hat stattdessen einen
weiteren begrenzenden Faktor,Die eine Speicher-Latenz-Verfügbarkeit. Das
macht es auchMachbar, um mit einem Smartphone zu beschäftigen.Tromp
schreibt über seine Arbeit:"[Kuckuckszyklus ist ein sofort
verifizierbares GedächtnisGebundenen PoW, der einzigartig ist, indem er
dominiert wirdLatenz statt Berechnungen. In diesem Sinne min-Cuckoo
Cycle ist eine Form von ASIC Bergbau woDRAM-Chips dienen der Anwendung
von zufälligLesen und Schreiben von Milliarden von Bits.Wenn auch
Telefone, die über Nacht aufladen können,Ohne Größenordnungen
Effizienzverlust,Nicht mit einer Denkweise der Profitabilität, sondern
des SpielsDie Lotterie, die Bergbau-Hardware-Landschaft wirdSehen große
Expansion, profitieren Adoption sowieDezentralisierung."Vorschau: Der
Konsensmechanismus hat eine etwas nicht-Standardrolle in der aeternity.
Neben der Vereinbarung auf neueBlöcke für die Blockkette, es stimmt auch
auf beide Antworten zuOracle Fragen und die Werte der
Systemparameter.Insbesondere kann sich der Konsensmechanismus
verändern.Es ist jedoch zu beachten, dass dies nicht ganz
unpro-Lematische Zum Beispiel, wenn ein einfacher
Proof-of-Work-MechanismusWurde verwendet, es wäre ziemlich billig, die
Bergleute zu bestechenBeschädigt das Orakel. Deshalb wird die Welt einen
Roman benutzenHybrid-Proof-of-Stake Proof-of-Work-Algorithmus,
HebelwirkungDie Vorteile von beiden. Unabhängig davon geht PoW losUm
neue aeon-toks zu vergeben.Sidenote: Ursprünglich war die Aeternity ein
100 ProzentProof-of-Stake-Blockkette. Wir denken nicht mehr, dass
aDezentrales 100 Prozent PoS-System ist möglich.C.1) Orakel: Ein
wichtiges Merkmal für die meisten Verträge,Ob als Text oder als Code
codiert, ist die Fähigkeit zu verweisenWerte aus der Umwelt, wie die
Preise von verschiedenenWaren oder ob ein bestimmtes Ereignis
eingetreten ist oder nicht. Ein klugerVertragssystem ohne diese
Fähigkeit ist im Wesentlichen eine geschlosseneSystem und wohl nicht
sehr nützlich. Dies ist ein allgemeinerCepted Tatsache und es gibt
bereits mehrere Projekte, die versuchenExterne Daten in deklaratorische
Daten in die Blockkette bringenWeg [ [8]](#seite-10) . Um zu
entscheiden, ob eine gelieferte Tatsache wahr istOder nicht, dies
erfordert im Wesentlichen die Umsetzung eines neuenKonsensmechanismus
auf dem Konsensmechanismus.Zwei Konsensmechanismen übereinander laufen
lassenIst so teuer wie man beide separat laufen Darüber hinaus ist
esErhöht nicht die Sicherheit, weil die am wenigsten sichere kannNoch
angegriffen und gemacht, um "falsche" Werte zu produzieren. So,Wir
schlagen vor, die beiden Konsensmechanismen ineinander zu
verwandelnEins, im Wesentlichen die Wiederverwendung der Mechanismus,
den wir verwenden, um zuzustimmenÜber den Zustand des Systems, um auch
über den Zustand derAußenwelt.Die Art und Weise, wie das funktioniert,
ist wie folgt. Jeder Aeon-InhaberKann ein Orakel starten, indem er sich
verpflichtet, eine Ja / Nein-Frage. Dabei müssen sie auch dieZeitrahmen,
in dem die Frage beantwortet werden kann, welcheKann jetzt oder
irgendwann in der Zukunft beginnen. Der Benutzer, derStartet das Orakel
ist erforderlich, um Aeon im Verhältnis einzahlenAuf die Länge des
Zeitrahmens, die zurückgegeben wird, wenn dieBenutzer liefert eine
Antwort, die als Wahrheit akzeptiert wird, sonstEs ist verbrannt Die
Blockkette erzeugt eine eindeutige Kennung fürDas Orakel, das verwendet
werden kann, um die Antwort abzurufen, sobald es istverfügbar.Sobald die
Zeit gekommen ist, die Frage zu beantworten, dieBenutzer, der das Orakel
gestartet hat, kann eine Antwort kostenlos geben.Sobald der
Orakelstarter eine Antwort gegeben hat oder bis einGewisse zeit
vergangen ist, können alle anderen einreichenGegenansprüche durch
Hinterlegung der gleichen Menge an Aeon. ObBis zum Ende des Jahres
wurden keine Gegenansprüche geltend gemachtTimeframe, die Antwort, die
vom Benutzer, der das gestartet hat, geliefert wirdOrakel wird als
Wahrheit angenommen, und die Kaution wird zurückgegeben. Wenn
überhauptGegenansprüche werden eingereicht, dann der
KonsensmechanismusFür Blöcke wird verwendet, um das Orakel zu
beantworten. Das ist mehrTeuer, aber da wir wissen, können wir
mindestens einen vonDie beiden Sicherheitsvorkommen, können wir es
verwenden.D. GovernanceDie Regierungsführung von Blockchain-basierten
Systemen war großProblem in der Vergangenheit. Wann immer ein
System-Upgrade sein mussGetan, das erfordert eine harte gabel, die in
der Regel zu groß führtDiskussionen unter allen Wertschülern. Sogar
einfache Dinge, wieKorrektur einer beliebig eingestellten Variablen im
Quellcode, asWir haben mit der Blockgröße Debatte in Bitcoin gesehen,
scheinenSehr hart in einem System zu sein, in dem die Anreize der
Benutzer sindNicht mit den Entscheidungsträgern ausgerichtet und wo es
istKein klarer Upgrade-Pfad. Wir haben auch komplizierter
gesehenGovernance-Entscheidungen, wie die Festlegung eines einzigen
intelligenten Vertrag BugIn "The DAO", die eine schnelle Intervention
durch das System erfordertenEntwicklerDas primäre Problem dieser Systeme
ist leichtIdentifizierbar - der Entscheidungsprozess für ein
Protokoll-up-Klasse oder Veränderung ist nicht gut definiert und fehlt
an Transparenz.Das Regierungssystem der aeternity ist Teil des
Konsenses. Es benutztVorhersagemärkte funktionieren effizient und
transparentwie möglich.Darüber hinaus wird der Konsensmechanismus durch
eine Num-Variablen, die bestimmen, wie das System funktioniertUnd das
wird von jedem neuen Block leicht aktualisiert. VonWie viel kostet es,
Transaktionen zu tätigen oder ein Orakel zu fragenModifikationen von
fundamentalen Parameterwerten wie dem BlockZeit.5

***

## Seite 6

Durch Vorhersage Märkte über die Variablen, dieDefinieren das Protokoll,
können die Benutzer lernen, wie effizientDas Protokoll verbessern Durch
die Vorhersage Märkte überPotenzielle harte Gabeln, können wir helfen,
die Gemeinschaft zu kommenKonsens über die Version des zu verwendenden
Codes. Jeder BenutzerWählt für sich selbst, welche Metrik es zu
optimieren sucht, aber aEinfache Standardstrategie wäre, den Wert von zu
maximierenSeine Bestände.E. SkalierbarkeitE.1) Schattige Bäume: Die
Architektur, die vor-Bisher skalierbar ist. Es ist möglich,
dieBlockchain auch wenn jeder Benutzer nur den Überblick über dieTeil
des Blockchain-Zustandes, den sie interessieren und ignorierenAlle
anderen Daten. Mindestens eine Kopie des Staates wird benötigtFür neue
Benutzer sicher sein, über die Substate, die sie interessierenÜber, aber
wir können diese Daten über willkürlich viele zerschlagenKnoten, so dass
die Last jedes Knotens beliebig klein ist. MerkleBäume werden verwendet,
um zu beweisen, dass ein Unterzustand Teil des Staates
ist[[11](#seite-10) ] Es ist leicht, sich ein Szenario vorzustellen, wo
bestimmte KnotenSpezialisiert auf die Verfolgung der Bäume und bezahlt
werdenEinsätze und Look-ups.E.2) Leichte Kunden: Leichte Clients laden
das ganze nicht herunterBlöcke Zuerst gibt der Benutzer seinem Klienten
einen Hash in der GeschichteVon der Gabel, die sie bevorzugen, eine
Technik, die auch als schwach bekannt istSubjektivität [[12](#seite-10)
]. Dann weiß der Klient nur zum DownloadGabeln, die einen Block mit
diesem Hash enthalten. Der Kunde nurLädt die Header der Blöcke herunter.
Die Header sind vielKleiner als volle Blöcke; Es werden nur sehr wenige
Transaktionen verarbeitet.Zur Vereinfachung haben wir die
Blocküberschriften nicht erwähntBei der Erörterung der Blockstruktur in
Abschnitt [II-A.4,](#seite-3) aberSie enthalten folgendes:• Der Hash des
vorherigen Blocks.• Der Wurzel-Hash aller Staatsbäume.E.3)
Zustandskanäle und Parallelität: ZustandskanäleHaben immense Durchsatz
und die meisten Transaktionen in ihnenWerden niemals ausgeführt oder
sogar auf der Blockkette aufgezeichnet.Darüber hinaus schreiben die
Kanäle nicht in einen gemeinsamen StatusOn-chain, so dass alle
Transaktionen, die tatsächlich aufgezeichnet werdenAuf der Blockkette
kann parallel verarbeitet werden. Angesichts dessenDie meisten heute
verkauften Verbrauchsmaterialien haben mindestens vierCessing Kerne, das
hat die unmittelbare Wirkung, dass TransaktionDer Durchsatz wird mit
einem Faktor von 4 multipliziert.Darüber hinaus ist die Tatsache, dass
es nie komplex sein wirdGleichzeitige Interaktion schlägt vor, dass
diese Blockkette beschädigt wirdArchitektur sollte relativ einfach sein.
Seit BlockketteScherben ist noch ziemlich experimentell, wir haben
bewusstGewählt, um keine Zerreißtechniken in der Initiale zu
verfolgenDesign von aeternity. Wenn sich das aber in der Zukunft
ändert,aeternity sollte eine der einfachsten Blockchains sein, um zu
scheißen.E.4) Transaktionen pro Sekunde bei einem gegebenen
Speicher-Quirement: Die Variablen, die das Protokoll definieren, sind
alleStändig aktualisiert durch den Konsens. Von ihrer
anfänglichenStandardwerte können wir die anfängliche Ausfallrate von
berechnenTransaktionen pro Sekunde.1Beachten Sie, dass dies ein Entwurf
ist und wird wahrscheinlich2Veränderung.34Wir definieren die folgenden
Variablen für dieFolgende Berechnungen:56B = Block \\ _Size in Bytes7F =
Blöcke \\ _till \\ _finalität8R = Zeit \\ _till \\ _finalität in
Sekunden9T = Transaktionsgröße in Bytes1011Transaktionen pro Sekunde = B
\* F / (T * R)1213B = 1000000 Bytes = 1 Megabyte pro Block14F = 24 * 60 *
2 Blöcke pro Tag15R / F = 30 Sekunden pro Block16R = 24 * 3600 Sekunden
pro Tag17T = 1000 Bytes pro Transaktion18191000000 * 24 * 60 * 2/1000/24
​​* 360020= 1000000/1000/3021= Ca. 32 Transaktionen pro Sekunde
(schnellGenug, um jeden Menschen innerhalb von 8 zu
unterzeichnenJahre)Um einen Knoten zu betreiben, müssen wir eine Kopie
von allen haltenBlöcke seit der Endgültigkeit, und wir müssen in der
Lage sein, 100 aufzunehmenMal mehr Informationen, falls es einen Angriff
gibt. SchätzenDass die Endgültigkeit 2 Tage dauert, dann würde es bis zu
6060 Blöcke kommenEndgültigkeit. So ist der Speicherbedarf 5760 * ein
Megabyte* 100 = 576000 Megabyte = 576 Gigabyte. Wenn daIst kein Angriff
passiert, man braucht nur etwa 5.76Gigabyte, um die Blöcke zu
speichern.III. A PPLIKATIONENDie staatenlose Natur der aeternity smart
contracts machtEs ist einfach, die folgenden Anwendungen auf aeternity
zu bauenBlockchain Es eignet sich besonders für den Großraum-Fälle.A.
Blockchain WesentlicheBlockchain Essentials sind notwendig Primitiven
wie aeon,Brieftaschen, Namen und verwandte Konzepte. Sie
modularisierenWiederverwendbare Komponenten, die als Applikations-Und
kann verbessert werden.A.1) Identitäten: Jedes Konto wird einbezogen
habenEindeutige ID-Nummer. Benutzer können eindeutige Namen registrieren
undLink-Namen zum Merkle-Root einer Datenstruktur. DasDatenstruktur kann
die eindeutige ID sowie andere enthaltenInformationen über das Konto.
Wir wollen Schema.org verwendenJSON-Format, um Dinge wie Personen oder
Unternehmen zu vertreten[ [13]](#seite-10)A.2) Brieftasche: Eine
Brieftasche ist ein Stück Software, die verwendet wirdMit Aeternity
interagieren. Eine Brieftasche verwaltet private Schlüssel fürDer aeon
und schafft und unterzeichnet transaktionen. Man kann benutzenDie
Brieftasche, um Kanaltransaktionen zu senden und Apps in
derKanalnetzwerkA.3) Nachweis der Existenz: Eine Transaktionsart erlaubt
esDie Veröffentlichung der Hash von Daten. SystemteilnehmerKann die
Header verwenden, um zu beweisen, dass die Daten vorhanden
sindZeitpunkt.6

***

## Seite 7

B. ZustandskanalanwendungenIntelligente Verträge in staatlichen Kanälen
sind perfekt für Mikro-Dienstleistungen im Internet, die eine hohe
Transaktions-stellen.B.1) Maut API: Die meisten heute existierenden APIs
sind öffentlichFür jedermann zu rufen, oder sie sind durch eine
gesichertBenutzername-Passwort-Schema oder eindeutige Zugriffstoken.
Zahlen-Kanäle erlauben eine neue Art von API, wo einerZahlt für jeden
Anruf an die API, evtl. jede HTTP-Anfrage.Bezahlen an eine API-Zugriff
löst DDoS-Probleme, und es machtes einfacher, qualitativ hochwertige
APIs zu bauen, die immer zur Verfügung stehen.API-Antworten, die eine
Zahlung sind von grundlegender Bedeutung für die erfordernSchaffung als
die noch unmöglich Arten von Unternehmen und kanneine wichtige Rolle bei
der Entstehung der dezentralen spielenWirtschaft. Sie schaffen Anreize
für Informationsbesitzermacht sonst private Daten öffentlich zugänglich
ist.B.2) Versicherte Crowdfunding: Wir können Versicherte
implementierenCrowdfunding mit dominanten Versicherungsverträge
[müssen cit.] .Dies sind intelligente Verträge, die verwendet werden, um
ein Geld zu beschaffenÖffentlichkeit gut, wie eine neue Brücke, eine
Schule oder einen Markt.Dominant Versicherungsverträge unterscheiden
sich von traditionellen as-surance Verträge wie Kickstarter, dass sie
machen es zu einemdominante Strategie zu beteiligen. Wenn das gut ist,
nicht finanziert werden,Alle Teilnehmer erhalten ihre Äon zurück plus
Zinsen, so dass sieversichert gegen ihre Liquidität zu reduzieren, ohne
den Empfanggut. Mit Hilfe eines Orakels, können wir, dass der Anbieter
sicherstellen, vondie Ware oder Dienstleistung wird erst dann bezahlt,
wenn die Ware oder Dienstleistung isttatsächlich zur Verfügung
gestellt.B.3) Querkette Atom Swaps: Kreuzkette AtomSwaps ermöglichen
trustless Austausch von Acon für bitcoins [ [14]](#seite-10)
,[[15](#seite-10) ]. Diese können mit einem hashlock implementiert
werden, dass Sperrendie Transaktionen auf beiden blockchains unter dem
gleichen Wert.B.4) Stabiler Wert Vermögen und Portfolio Replikation:
Wirverwenden Smart-Verträge können synthetische Vermögenswerte zu
programmieren, die bleibenfast den gleichen Preis wie eine reale Welt
Kapital. Beispielsweise,konnten wir einen Vermögenswert machen, die den
gleichen Preis wie Gold bleibt.Synthetische Derivate sind in gleichen
und entgegengesetzten Paaren erstellt.Für einen Benutzer ein Asset zu
haben, die mit Gold bewegt, eine andereBenutzer müssen einen
Vermögenswert haben, die in umgekehrtem Verhältnis zu Gold zu
bewegen.Zum Beispiel könnte Alice einen Vertrag mit Bob machen, so
dassAlice besitzt 1 Gramm Gold. Aus dem Geld in dem Vertrag,ein Gramm
Gold im Wert von Äon wird Alice gehen, und dieübrig gebliebenen Geld
geht an Bob. Der Vertrag hat einen AblaufDatum, wenn der Goldpreis
gemessen werden, und die MittelAlice und Bob entsprechend verteilt.B.5)
Ereignis Verträge: Event Verträge zahlen, wenn ein Ereignisgeschieht und
nicht zahlen, wenn ein Ereignis nicht passiert, alspro vielsagend
Orakel. Abgesehen von in spielen sich interessant seinSelbst, können
diese durch verschiedene Anwendungen eingesetzt werden:a)
Versicherungen: Wir Veranstaltungsverträge, verwenden können, um
Durch-ment Versicherungen. Zum Beispiel teure Musik-Event-Ticketskann
wertlos werden, wenn das Wetter schlecht geht. Wie auch immer, wenndie
Konzertbesucher erhalten Geld, wenn das Orakel entscheidet, dasses
regnete am Tag der Veranstaltung kann die Investitiongeschützt, so dass
man es sich leisten kann, eine emotionally- zu findenadäquate
Alternative. Etwas ernster sind die Landwirtein der Gesamtzahl des Zolls
regt in einem interessiertJahreszeit. Wir können sie gegen ihre Ernte
versichern welken ausTrockenheit.b) Whistleblowing: Event-Verträge
können auch verwendet werden,Enthüllung sensiblere Informationen zur
Schaffung von Anreizen. Beispielsweise,wir konnten auf der Veranstaltung
„Information Wette darauf hinweist, dassUnternehmen A hat illegale
Pestizide verwendet wurde veröffentlicht am odervor 24. Januar 2017" .
Jede Person mit Zugang zu solchenInformationen würden zum ersten Wette
incentivised werden, dass die Veranstaltungwird passieren, und dann
loslassen.B.6) Prognosemärkte: Ein Prognosemarkt funktioniert
durchVermietung auf Nutzer wetten, ob ein Ereignis in der Zukunft
passieren wird. Vonder Preis der Wetten können wir die Zukunft
Wahrscheinlichkeit [voraussagen [3]](#seite-10) ,[[8](#seite-10) ],
[16]. Sie sind die genaueste Methode , die messenZukunft zu einem
bestimmten Preis [muß cit.] . Sobald das Ereignis passiert,der Markt
wird mit dem Orakel angesiedelt.Wie in Abschnitt erwähnt
[II-D](#seite-5) , können wir zum Beispiel verwenden Vorhersagention
Märkte, welche Updates für die Software zur Vorhersage wirdvorteilhaft,
und das wird schädlich sein. Wir können sie auch benutzenwie viel
Kandidaten bei einer Wahl zu schätzen tatsächlichin der Lage zu
erreichen, so Lügen und unbegründete Versprechungen sein könnenleichter
erkannt.Feige. 5. Mehrdimensionale Prognosemarkt.a) Multidimensional
Prognosemärkte: mehrdimensio-len Prognosemärkte ermöglichen es uns, die
Korrelation zur Vorhersagezwischen möglichen zukünftigen Ereignissen. So
zum Beispiel, könnte mansagen voraus, dass, wenn Alice Führer gewählt,
der Preis für Kartoffelnnach unten gehen wird, und dass, wenn Bob
gewinnt, wird der Preis steigen.Man könnte lernen, dass, wenn Google
verwendet Plan A für die nächsten 3Monate, dass es wahrscheinlich mehr
Geld verdienen, und dass es, wennPlan B verwendet, wird es
wahrscheinlich weniger verdienen. Oder, wie in Abb. [5](#seite-7) ,
wirsehen, dass, wenn Alice Präsidenten gewählt würde, es ist einhohe
Wahrscheinlichkeit, dass der Preis für Kartoffeln ist eher gering.B.7)
Markt mit Batch-Handel zum Einheitspreis: Essind zwei Ansätze zur
Verfügung, die Angreifer zu berauben wollenÄon von einem Markt. Sie
können die Vorteile des Marktes nehmenwird in der Zeit geteilt, oder sie
können es nutzen seinSplit im Raum.• Wenn der Markt im Raum aufgespalten
wird, dann hat der AngreiferArbitrage. Er macht gleichzeitig Geschäfte
in beiden Mar-KET auf einmal so, dass sein Risiko aufhebt und er
verdient eine7

***

## Seite 8

profitieren.• Wenn der Markt in der Zeit geteilt, dann wird der
Angreifer front-läuft auf den Markt. Er liest die Transaktionen kommen
inund der Markt schafft Kauf- und Verkaufsaufträge sofortvorher und
nachher.Feige. 6. Die schwarze Linie ist die Nachfragekurve, ist die
rote Linie die VersorgungsKurve. Die Sells in rot sind die gleiche Größe
wie die Käufe in rot. die vertikaleLinie ist der Preis der Market Maker
ausgewählt. Jeder bereit auf einem kaufenhöherer Preis zu diesem Preis
gehandelt werden, jeder bereit zu einem niedrigen Preis zu verkaufenzu
diesem Preis gehandelt.So kombinieren Märkte im Raum, sollte jeder
nutzen diegleicher Market Maker. Zu den Märkten in der Zeit zu
verbinden, brauchen wirhat den Handel an Einzelpreis in Chargen
durchgeführt. Der MarktHersteller muss für jede Person begehen, welchen
Preis er beschlossen,und wenn jemand widersprüchlichen Verpflichtungen
aus dem findenMarket Maker, dann sollten alle seine Kunden in der Lage
zualle seine Kanäle ablaufen lassen. Wenn der Market Maker verpflichtet
sich einfairer Preis, dann wird er das gleiche Volumen von Käufern
entspricht undVerkäufer zusammen, wie Abb [.](#seite-8)6 zeigt.
Andernfalls endet er aufin einer ähnlichen Situation wie Abb.
[7](#seite-8) , so dass ein großes Risiko ein.Feige. 7. Der schwarze ist
viel größer als die roten Zahlen. Der Market Maker verkauftviel mehr
Aktien als es kauft, also auf eine Menge von Risiko.IV. I UMSETZUNGDie
meisten Schlüsselkonzepte haben bereits
Proof-of-Concept-Durch-mentierungen in Erlang. Dazu gehört auch die
blockchain selbst,die Vertragssprache und VM, das Orakel und
GovernanceMechanismen, sowie eine alte Version des KonsensMechanismus.
Wir haben Erlang / OTP verwendet, weil es es machteinfach Code zu
schreiben, zu viele Anfragen reagieren könnenparallel und nicht
abstürzt. Die Server mit der höchsten Up-Zeit in der Welt basiert auf
Erlang. Es wird verwendet, um fürindustrielle Anwendungen seit 30 Jahren
selbst erweist sich als seinzuverlässiges und stabiles Produkt.A.
Virtuelle Maschine und VertragsspracheDie virtuelle Maschine wird
Stack-basierte und ähnlich wie Forthund Bitcoin' Skriptsprache, obwohl
im Vergleich zuletztere ist es ziemlich reich. Die VM unterstützt
Funktionen stattihre Semantik zu analysieren relativ einfach von gotos,
zu machen.Eine Liste der Opcodes VM finden Sie auf unserer Github zu
finden [3](#seite-8) .Darüber hinaus gibt es eine übergeordnete
Forth-like Spra-che Chalang genannt, die für die zu Bytecode
kompiliertVM Es unterstützt Makros und Variablennamen, sondern hält
dieStapel-basiertes Ausführungsmodell [[17](#seite-10) ]. Beispiele für
Chalang Codekönnen Sie auch auf unserer Github zu finden [4](#seite-8)
.B. Annahme über Web-integrationDas Web ist die beliebteste
Anwendungsplattform. Wirwird bieten Web-Entwicklung einfach zu
bedienende Werkzeuge, wie JS-Bibliotheken und JSON-APIs für die
Kernfunktionen des aeternityblockchain.C. Open-Source-ModuleUm für
privat blockchain Con- leicht wiederverwendet werdensortium und andere
Anwendungsfälle, wird die Software in geschriebenMIT-lizenzierten
Module, wie ein Konsens-Modul, das kannauf die spezifischen Bedürfnisse
angepasst werden.D. Usability und UX DesignReibungsfreihe menschliche
Interaktion wird ein großer Fokus unsererEntwicklungsanstrengungen.
Genauer gesagt, werden wir sicherstellen,dass die die Identität steuert,
Schlüssel und Transaktionen ist deutlichetabliert. Außerdem bietet
einfachen Zugang über Web-Gatewaysein Schwerpunkt der zukünftigen
Entwicklung sein. Benutzer teilnehmenin Prognosemärkte über einen
Zunder-like (streichen Sie nach links / rechts)mobile Schnittstelle und
einfache Web-Wallets, die leicht sein könnenin einer Website über einen
iFrame eingebunden wird die neueNorm.V. D ISKUSSIONWir haben eine
Erklärung, wie zu versehen Architektenein grundsätzlich effizientes
Wertübertragungssystem. Dasbeschriebenes System ist eine globale
Oracle-Maschine in der Tat das kannwerden verwendet Entscheidungsfindung
Dienstleistungen auf globaler Ebene bereitzustellen.Insbesondere alle
Anwendungen in Abschnitt vorgeschlagen [III](#seite-6) Dosewerden
einfach und effizient auf der aeternity gebaut.3
[](https://github.com/aeternity/chalang/blob/master/opcodes.md)[https://github.com/aeternity/chalang/blob/](https://github.com/aeternity/chalang/blob/master/opcodes.md)[Master / opcodes.md](https://github.com/aeternity/chalang/blob/master/opcodes.md)4
[](https://github.com/aeternity/chalang/tree/master/examples)[https://github.com/aeternity/chalang/tree/](https://github.com/aeternity/chalang/tree/master/examples)[Master / Beispiele](https://github.com/aeternity/chalang/tree/master/examples)8

***

## Seite 9

Doch unser Ansatz hat sowohl grundlegende Einschränkungenund
Möglichkeiten für Verbesserungen. Diese werden hier diskutiert.A.
Einschränkungen und KompromisseWährend wir glauben, dass die
vorgenommenen Abwägungen in unseremArchitektur ist vernünftig, die
resultierende Leistung gegebenErhöhung in anderen Bereichen, aeternity
ist keine allumfassende Lösungfür dezentrale Anwendungen. Es sollte
vielmehr betrachtet werden alseine synergistische Ergänzung zu
bestehenden Technologien. Es gibtmehrere Einsprüche, die man sich
bewusst sein müssen.A.1) On-Kette Zustand: Trotz vieler Vorteile
aufweist,aeternity Mangel an programmierbarem Zustand macht es
ungeeignet fürAnwendungen, die einen benutzerdefinierten Zustand zu
sein, unter Con- erfordernsensus. Zum Beispiel enthält diese DAOs, wie
sie in der Regel sindkonzipiertes, individueller name Systeme und
subcurrencies Welchenicht auf den Wert eines Basiswerts gebunden.A.2)
Freie Option Problem: Wenn Alice und Bob haben eineKanal und Alice einen
Vertrag unterzeichnet, gibt sie im Wesentlichen Bobeine kostenlose
Option, wenn sie es ihm sendet: Bob wählenschreiben und zurücksenden (dh
aktiviert), um den Vertrag jederzeit indie Zukunft. Oft ist dies nicht
das, was beabsichtigt ist. Um dies zu vermeidenProblem, Kanalverträge
werden nicht sofort aktiviert mitdie volle Menge. Sie sind in Zeit oder
Raum aufgeteilt. BeideTeilnehmer für den Vertrag in kleinen Intervallen
anmelden würdenso dass weder Benutzer immer eine große kostenlose Option
auf die Angeboteandere.Zum Beispiel, wenn die Parteien 100 Äon wetten,
dannsie könnten in 1000 Schritte, um es registrieren Sie sich, dass jede
der ErhöhungWette von 0,1 Äon. Dies würde erfordern, etwa 1000
Meldungenin jede Richtung passieren, 500, die seit billig genug istder
Vertrag nie zum blockchain vorgelegt. wie ein andererWenn man
beispielsweise einen finanziellen Vermögenswert machen wollte das
wäre100 Tage letzte, so könnte man in 2400 Schritten von einer
AnmeldungStunde jeder. Dies würde etwa 2400 Nachrichten erfordern
passieren,1200 in jede Richtung.A.3) Liquiditätsverlust und
Kanalzustands Topologien: BeiKomponieren Kanäle hashlocks wie gezeigt
inAbschnitt [II-B.1](#seite-3) beliebige Mittelsmänner mindestens
zweimal einzusperrenso viele Äon wie wird durch sie übertragen.
ZumBeispiel: Wenn Alice und Carol will Bob transact durch,Bob wird als
Carol wirken, wenn sie mit Alice Interaktion und Vize-kehrt.Da dies für
Bob teuer ist, würde er höchstwahrscheinlicheine Gebühr als Vergütung
erhalten. Wenn Alice und Carol erwartenführen viele Gewerke
untereinander, können sie vermeiden diesedurch einen neuen Kanal zu
schaffen und trustlessly Bewegen der aktivenVerträge auf den neuen Kanal
ein hashlock verwenden.Noch ein zusätzlicher Kanal geöffnet
Auswirkungen, da halten jemandesnegativ Liquidität wird durch
Mittelsmann erwartetin vielen Fällen wünschenswert, vor allem in den
Fällen, in denenDie Parteien erwarten nicht viel in der Zukunft zu
handeln. Also aKanal-Topologie, wo reiche Benutzer Geld austrustlessly
Transaktionen zwischen anderen Benutzern übertragen wirdvoraussichtlich
entstehen.Es sei darauf hingewiesen, dass dies nicht ein einziges
darstellePoint of Failure, da wir kein Vertrauen in dieser
TransaktionSender mit irgendetwas. Wenn ein Sender geht offline vordas
Geheimnis einer hashlock offenbart worden, die Transaktionnicht
durchlaufen. Wenn es geht danach offline, der einzigemöglicher
„negativer" Effekt ist, dass der Sender nicht in der Lage istseine Acon
Anspruch.B. Zukünftige ArbeitenEs gibt mehrere Möglichkeiten, auf den
Strom zu verbesserndie Architektur.B.1) Funktionsvertragssprache: Eine
vernünftige ZukunftRichtung würde mit Hochsprachen zu experimentieren
seindass haften stärker an die funktionale Paradigma. Behalten-Spur
eines impliziten Stapel Ing ist allgemein fehleranfällig undwohl nicht
geeignet für eine High-Level, der Entwickler gerichteten LAN-Guage Dies
sollte recht einfach gegeben werden, dass die Programme sindbereits
reine Funktionen (Umgebungsvariablen Modulo),und würde erheblich
vereinfachen sowohl die Entwicklung und formaleÜberprüfung von
Verträgen. Wenn dies geschehen ist, könnte es auch machenSinn der VM zu
überarbeiten eng gekoppelt werden, mit dem neuenSprache, die
Zusammenstellung weniger fehleranfällig zu machen und wenigerabhängig
von Vertrauen in die Entwickler. Idealerweise ist die Übersetzungvon
Oberflächensprache VM sein Code würde einfach eine direkteTranskription
von Peer-Review-Forschung, obwohl pragmatischZugeständnisse werden
wahrscheinlich gemacht werden müssen.B.2) Multi-Party-Kanäle: Derzeit
werden alle Kanäle aufaeternity sind auf zwei Parteien begrenzt. Während
Mehrparteien Chan-nels können de facto durch hashlocking erreicht
werden, kann diesteuer sein. Daher planen wir die Möglichkeit zu
untersuchen,das Hinzufügen von Unterstützung für n-Partei-Kanäle, mit
einem m-aus-nBeilegungsmechanismus.G LOSSARBlockchain A verteilt,
manipulationssichere Datenbank mit me-tered Zugang. Die Datenbank wird
von einer wachsenden Liste definiertHash-verknüpften Blöcke und kann
keine Regeln zum AnhängenSie.Aeon Ein Äon stellt eine Rechnungseinheit
und eine ZugangsRecht auf den aeternity blockchain. Es ist
übertragbar.Transaktion Eine Nachricht von einem Benutzer zum
blockchain.Dies ist, wie die Benutzer ihre Währung verwenden können, die
für den Zugriff aufblockchain.Zustand Kanal Eine Beziehung zwischen zwei
Benutzern aufgezeichnetauf der blockchain. Es ermöglicht Benutzern, Äon
zurück zu schickenund her, und trustless intelligente Verträge zu
schaffen zwischensie, die von der blockchain erzwungen und abgerechnet
werden.Hash hash A nimmt als Eingabe eine binäre jeder Größe. Es
gibteine feste Größe ausgegeben. Der gleiche Eingang immer Hashesdie
gleiche Leistung. ein Ausgang gegeben, kann man nicht berechnendie
Eingabe.Hashlocking Dies ist, wie wir Paare von Kanälen verbinden
zumacht intelligente Verträge, die mehr als 2 Personen beinhalten.Ein
Geheimnis wird durch die Hash verwiesen. Wenn das Geheimnis
ist,offenbart, kann es mehrere Kanäle gleichzeitig
aktualisierenZeit.Governance Eine klar definierte Prozess der
Entscheidungsfindung fürdas zukünftige Protokoll (e) des blockchain.9

***

## Seite 10

Oracle Ein Mechanismus, der die blockchain Tatsachen erzähltdie Welt in
der wir leben. können Orakeln Benutzer verwenden vorhersagen dieAusgang
von Ereignissen, die außerhalb des blockchain System.Value-Halter Ein
Benutzer, der Äon besitzt, oder eine finanzielle Deri-tive in dem
System.Validator Ein Validator ist ein Benutzer, der in der
beteiligtKonsensus-Mechanismus. Im Fall von aeternity, jederWerthalter
kann teilnehmen.ANERKENNUNGENDank Vlad, Matt, Paul, Dirk, Martin,
Alistair, Devonund Ben für das Korrekturlesen. Dank dieser und viele
andereMenschen für interessante Diskussionen.

## REFERENZEN

<table style="text-align: left; width: 100%;" border="1" cellpadding="2"
cellspacing="2">
<tbody>
<tr>
<td style="vertical-align: top;">REFERENCES<br>
[1] S. Nakamoto, “Bitcoin: A peer-to-peer electronic cash<br>
system,” 2008. [Online]. Available: https://<br>
bitcoin.org/bitcoin.pdf.<br>
[2] V. Buterin, “Ethereum: A next-generation smart con-<br>
tract and decentralized application platform,” 2014.<br>
[Online]. Available:https://github . com /<br>
ethereum/wiki/wiki/White-Paper.<br>
[3] P. Sztorc, “Market empiricism,” [Online]. Available:<br>
http://bitcoinhivemind.com/papers/1_<br>
Purpose.pdf.<br>
[4] M. Liston and M. Koppelmann, “A visit to the ora-¨<br>
cle,” 2016. [Online]. Available:https://bloggnosis.pm<br>
[5] C. Detrio, “Smart markets for smart contracts,” 2015.<br>
[Online]. Available:http://cdetr.io/smart-markets/ <br>
[6]Namecoin wiki, 2016. [Online]. Available: https://wiki.namecoin.org/index.php?title=Welcome.<br>
[7] P. Snow, B. Deery, J. Lu,et al., “Factom: Business<br>
processes secured by immutable audit trails on the<br>
blockchain,” 2014. [Online]. Available:http : / /<br>
bravenewcoin.com/assets/Whitepapers/<br>
Factom-Whitepaper.pdf.<br>
[8] J. Peterson and J. Krug, “Augur: A decentralized,<br>
open-source platform for prediction markets,” 2014.<br>
[Online]. Available:http : / / bravenewcoin .<br>
com / assets / Whitepapers / Augur - A -<br>
Decentralized - Open - Source - Platform -<br>
for-Prediction-Markets.pdf.<br>
[9] A. Swartz, “Squaring the triangle: Secure, decentral-<br>
ized, human-readable names,” 2011. [Online]. Avail-<br>
able:http : / / www . aaronsw . com / weblog /<br>
squarezooko.<br>
[10] T. Hvitved, “A Survey of Formal Languages for<br>
Contracts,” inFormal Languages and Analysis of<br>
Contract-Oriented Software, 2010, pp. 29–32. [On-<br>
line]. Available:http : / / www . diku .<br>
dk / hjemmesider / ansatte / hvitved /<br>
publications/hvitved10flacosb.pdf.<br>
</td>
<td style="vertical-align: top;">[11] R. C. Merkle, “Protocols
for public key cryptosys-<br>
tems,” inIEEE Symposium on Security and Privacy,<br>
1980.<br>
[12] V. Buterin, “Proof of stake: How I learned to<br>
love weak subjectivity,” 2014. [Online]. Available:<br>
https://blog . ethereum . org / 2014 / 11 /<br>
25 / proof - stake - learned - love - weak -<br>
subjectivity/.<br>
[13] “Schema.org schemas,” 2016. [Online]. Available:<br>
http://schema.org/docs/schemas.html.<br>
[14] “Atomic-cross-chain-trading,” 2016. [Online]. Avail-<br>
able:https://en . bitcoin . it / wiki /<br>
Atomic%5C_cross-chain%5C_trading.<br>
[15] “Interledger,” 2016. [Online]. Available:https://<br>
interledger.org/.<br>
[16] K. J. Arrow, R. Forsythe, M. Gorham,et al., “The<br>
promise of prediction markets,”Science, 320 2008.<br>
[Online]. Available:http : / / mason . gmu . edu /<br>
˜rhanson/PromisePredMkt.pdf.<br>
[17] Z. Hess, “Chalang,” 2016. [Online]. Available:<br>
https://github.com/aeternity/chalang.<br>
</td>
</tr>
</tbody>
</table>