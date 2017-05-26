# La blockchain æternity
## La piattaforma di oracoli decentralizzata, perfettamente funzionale e trustless(**)
_(**trustless: che non richiede la fiducia in enti terzi che validino l'operato della piattaforma stessa)_

February 6, 2017
v0.1

* Zackary Hess zack@aeternity.com
* Yanislav Malahov yani@aeternity.com
* Jack Pettersson jack@aeternity.com

Abstract — Dal momento dell'introduzione di Ethereum nel 2014 c'è stato un grande interesse nelle applicazioni decentralizzate trustless (smart contract). Di conseguenza molti hanno tentato di implementare applicazioni con dati derivanti dal mondo reale innestati su di una blockchain. Noi crediamo che allocare lo stato e il codice di una applicazione sulla blockchain sia sbagliato per varie ragioni. 
Presentiamo un'architettura altamente scalabile di una blockchain dotata di un meccanismo di consenso che è anche usato per controllare l'oracolo. Questo rende l'oracolo molto efficiente, perché evita lo stratificarsi dei meccanismi di consenso uno sopra l'altro. I canali a Stati sono integrati per incrementare la privacy e la scalabilità. I token nei canali possono essere trasferiti utilizzando smart contract perfettamente funzionali che possono accedere alle risposte dell'oracolo. Non allocando codice di contratto sulla catena, siamo in grado di creare contratti smart più semplici da analizzare e più veloci da processare, con nessuna sostanziale perdita sulla funzionalità reale.
Applicazioni come i mercati per gli asset sintetici e i mercati predittivi possono essere efficientemente implementate su scala globale. Diverse parti hanno una implementazione prototipale in Erlang. Saranno anche predisposti gli strumenti di sviluppo e le applicazioni essenziali come il portafoglio e un sistema di identificazione e di attribuzione del nome.
***
## CONTENUTI
I [Introduzione](#introduzione) . . . . . . . . . . . . . . . . . 1  
I-A [Lavori precedenti](#lavori-precedenti) . . . . . . . . . . . . . 2  
II [Cos'è la blockchain æternity](#cosé-la-blockchain-æternity)  . . . . . . . . . . . 2  
II-A [Token, account e blocchi](#token-account-e-blocchi)  . . . . . . . . . 2  
II-A.1 [Token di accesso, Aeon](#token-di-accesso-aeon)  . . . . . . . . . 2  
II-A.2 [Account](#account) . . . . . . . . . . . . . . . . . 2  
II-A.3 [Sistema dei nomi](#sistema-dei-nomi)  . . . . . . . . . . . . 3  
II-A.4 [Contenuti dei blocchi](#contenuti-dei-blocchi) . . . . . . . . . . 3  
II-B [Canali a stati](#canali-a-stati) . . . . . . . . . . . . . . . 3  
II-B.1 [Smart contract](#smart-contract)  . . . . . . . . . . . . . 3  
II-B.2 [Esempio](#esempio)  . . . . . . . . . . . . . . . . . 4  
II-C [Meccanismo di Consenso](#meccanismo-di-consenso)  . . . . . . . . . . 5  
II-C.1 [Oracoli](#oracoli) . . . . . . . . . . . . . . . . . 5  
II-D [Governance](#governance)  . . . . . . . . . . . . . . . . 5  
II-E [Scalabilità](#scalabilità) . . . . . . . . . . . . . . . . 6  
II-E.1 [Frammentazione ad alberi](#frammentazione-ad-alberi) . . . . . . . . . . . . . 6  
II-E.2 [Client leggero](#client-leggero)  . . . . . . . . . . . . . 6  
II-E.3 [Canali a stati e parallelismo](#canali-a-stati-e-parallelismo). . . . . . . 6  
II-E.4 [Transazioni per secondo ad una certa richiesta di memoria](#transazioni-per-secondo-ad-una-certa-richiesta-di-memoria) 6  
III [Applicazioni](#applicazioni) . . . . . . . . . . . . . . . . 6  
III-A [Elementi essenziali della blockchain](#elementi-essenziali-della-blockchain) . . . 6  
III-A.1 [Identità](#identità) . . . . . . . . . . . . . . . . 6  
III-A.2 [Portafoglio](#portafoglio)  . . . . . . . . . . . . . . 6  
III-A.3 [Prova di esistenza](#prova-di-esistenza) . . . . . . . . . . . 6  
III-B [Applicazioni su canali a stati](#applicazioni-su-canali-a-stati) . . . . . . 7  
III-B.1 [Strumento API](#strumento-api)  . . . . . . . . . . . . . 7  
III-B.2 [Raccolta fondi assicurata](#raccolta-fondi-assicurata)  . . . . . . . 7  
III-B.3 [Swap atomico tra blockchain](#swap-atomico-tra-blockchain)  . . . . . . 7  
III-B.4 [Asset a valore stabile e replicazione del portafoglio](#asset-a-valore-stabile-e-replicazione-del-portafoglio) . . . . 7  
III-B.5 [Contratti ad eventi](#Contratti-ad-eventi)  . . . . . . . . . 7  
III-B.6 [Mercati predittivi](#mercati-predittivi) . . . . . . . . . . . 7  
III-B.7 [Market con un lotto in vendita ad un prezzo singolo](#market-con-un-lotto-in-vendita-ad-un-prezzo-singolo) . . . . . . 7  
IV [Implementazione](#implementazione) . . . . . . . . . . . . . . . 8  
IV-A [Macchine e linguaggio del contratto](#macchine-e-linguaggio-del-contratto) . . . . 8  
IV-B [Adozione tramite integrazione web](#adozione-tramite-integrazione-web) . . . . . 8  
IV-C [Moduli open source](#moduli-open-source)  . . . . . . . . . . . . 8  
IV-D [Condizioni d'uso e design dell'UX](#condizioni-duso-e-design-dellux) . . . . . 8  
V [Discussioni](#discussioni)  . . . . . . . . . . . . . . . . . 8  
V-A [Limitazioni e compromessi](#limitazioni-e-compromessi) . . . . . . . . . . . 9  
V-A.1 [Stati sulla blockchain](#stati-sulla-blockchain) . . . . . . . . . . 9  
V-A.2 [Problema dell'opzione gratuita](#problema-dellopzione-gratuita) . . . . . . 9  
V-A.3 [Perdita di liquidità e tipologie di macchine a stati](#perdita-di-liquidità-e-tipologie-di-macchine-a-stati) . . . . . 9  
V-B [Lavori Futuri](#lavori-futuri)  . . . . . . . . . . . . . . . 9  
V-B.1 [Linguaggio funzionale del contratto](#linguaggio-funzionale-del-contratto)  . . . 9  
V-B.2 [Canali multi-parti](#canali-multi-parti) . . . . . . . . . . . . 9
[GLOSSARIO](#glossario)  
[RINGRAZIAMENTI](#ringraziamenti)  
[RIFERIMENTI](#riferimenti)  

#### Introduzione
Lo scopo di questo paper è di dare un quadro d'insieme dell'architettura della æternity blockchain e delle sue possibili applicazioni. Paper più dettagliati verranno rilasciati in futuro, specificatamente per i meccanismi di consenso e governance. In ogni caso, deve essere sottolineato che la nostra architettura è olistica: tutti i componenti sono strettamente interconnessi e sinergici, in maniera modulare. La struttura di questo paper è suddivisa in quattro parti.
* Primo, introdurremo e analizzeremo la struttura teorica fondamentale che da forma alla nostra architettura.
* Secondo, analizzeremo le applicazioni essenziali integrate (1), altri possibili casi di utilizzo e daremo degli spunti di come sia possibile per uno sviluppatore utilizzare la piattaforma.
* Terzo, presenteremo l'attuale implementazione del POC (proof-of-concept), scritto in Erlang.
* Concluderemo con una discussione che includa possibili futuri sviluppi e comparazioni con altre tecnologie.

I-A
#### Lavori precedenti
Le Blockchain nate precedentemente, prima di tutti il Bitcoin, hanno mostrato un nuovo modo di consentire il trasferimento di valore su Internet [1]. A ciò è seguito un certo numero di promettenti passi avanti: Ethereum ha mostrato un modo per scrivere smart contract Turing-complete legati a una architettura blockchain [2]; Truthcoin ha creato degli strumenti per creare degli oracoli su blockchain [3], mentre Gnosis e Augur hanno mostrato come rendere gli stessi più efficienti [4]; Casey Detrio ha mostrato come creare dei mercati su blockchain [5], Namecoin come realizzare l'equivalente distribuito di un dominio server; Factom ha mostrato come una blockchain che generi hash possa essere usata come prova di esistenza di qualsiasi dato digitale [7].  
Queste tecnologie sono molto promettenti qualora giungano a fornire servizi finanziari e legali di prim'ordine a chiunque.  
Per ora però hanno fallito nel mettersi insieme in un sistema unificato che mantenga le promesse. Più specificatamente, tutte le soluzioni sono venute meno in almeno uno dei seguenti aspetti: governance, scalabilità, sicurezza del codice e accesso economico ai dati del mondo reale [richiede citazione]. æternity punta a migliorare lo stato dell'arte in tutti questi aspetti.

II
#### Cos'é la blockchain æternity
Crediamo che le carenze nelle “piattaforme di smart contract” in termini di scalabilità, sicurezza del codice e accesso economico ai dati del mondo reale si possano ricondurre a tre problemi di fondo.
Primo, il predominio dello “stateful design” rende gli smart contract scritti per queste piattaforme difficili da analizzare 
> *La difficoltà di analizzare contratti “stateful” è stata chiaramente dimostrata dal bug di chiamata ricorsiva che ha buttato giù “The DAO”. Questo è successo nonostante il codice fosse stato verificato da diversi creatori di Ethereum così come dalla più ampia comunità [cit. necessaria].*
 
, e la “statefulness” (assenza di stato) combinata con l’ordinamento sequenziale delle transazioni rende più complessa la scalabilità [cit. necessaria]. Secondo, l’alto costo di trasportare i dati dal mondo reale all'interno del sistema in modo decentralizzato, “trustless” e affidabile complica o rende del tutto impossibile la realizzazione di molte promettenti applicazioni [cit. necessaria]. Terzo, le piattaforme vengono limitate nella loro capacità di adattarsi a nuovi sviluppi economici o tecnologici. Riteniamo che ciascuno di questi tre problemi abbia dei percorsi risolutivi del tutto chiari che dovrebbero essere esplorati.  
Primo, recenti ricerche nella tecnologia dei canali a stati suggeriscono che per molti utilizzi, mantenere lo stato su blockchain non sia necessario [cit. necessaria]. Molto spesso è del tutto possibile immagazzinare tutte le informazioni in canali a stati, e utilizzare la blockchain soltanto per risolvere qualsiasi risultato economico conseguente allo scambio di informazioni, e come metodo per ripristinare una situazione precedente in caso di disputa. Ciò suggerisce un approccio alternativo alla architettura della blockchain nella quale gli “smart contract” “Touring complete” esistano esclusivamente sui canali a stati, non su blockchain. Questo incrementa la scalabilità dal momento che tutte le transazioni diventano indipendenti e possono quindi essere processate in parallelo. In aggiunta, questo significa che i contratti non scrivono mai su uno stato condiviso, semplificando di gran lunga le necessità di controllo e verifica. Riteniamo che questo design renda più evidente che le blockchain riguardano la logica finanziaria più che l’archiviazione dei dati; esistono soluzioni decentralizzate che sono perfettamente complementari alle blockchain.  
Secondo, applicazioni come Augur hanno tentato di portare i dati del mondo reale dentro la blockchain in modo decentralizzato – nel processo di fatto hanno costruito un meccanismo di consenso dentro gli smart contract [8], invece di utilizzare il meccanismo di consenso della sottostante blockchain. Ciò genera inefficienze ma nello stesso tempo non aumenta il livello di sicurezza. La naturale conclusione che deriva da ciò è di rendere generale il meccanismo di consenso della blockchain in modo tale che esso possa fornire le informazioni non soltanto sullo stato interno successivo, ma anche sullo stato del mondo esterno. Potrebbe tuttavia essere argomentato che il meccanismo di consenso della blockchain determini il risultato di decidere quale teoria della complessità stia dietro a un oracolo: una macchina teorica che è molto più potente di una macchina di Touring perché ha le risposte ad alcune domande che non possono necessariamente essere calcolate come “Chi ha vinto la partita X di calcio?” [cit. necessaria].  
Terzo, sembra naturale che il meccanismo di consenso potrebbe essere anche utilizzato per determinare i parametri del sistema. Ciò gli permetterebbe di adattarsi alle mutevoli condizioni esterne esattamente come nell'adottare nuove ricerche e sviluppi recenti nel campo.
Il resto di questa sezione introduce la æternity blockchain in maggior dettaglio, a cominciare da una breve panoramica degli account, dei token, dei nomi e della struttura dei blocchi. Questa è seguita da una spiegazione del nostro approccio ai canali di stato e agli smart contract, quindi da una discussione su come il meccanismo di consenso della blockchain può essere utilizzato sia per creare un meccanismo di oracolo efficiente sia per governare il sistema. Infine parliamo della scalabilità da diversi punti di vista. 

II-A
#### Token, account e blocchi
Nonostante sia "stateless" dal punto di vista del contratto dello sviluppatore, la æternity blockchain mantiene traccia di vari componenti di stato predefiniti. Ora spiegheremo queste e il contenuto di ciascun blocco. Per semplicità, questa sezione presuppone che ogni nodo tenga traccia dell'intera blockchain. Possibili ottimizzazioni sono descritte nella sezione II-E.  

II-A.1
#### Token di accesso, Aeon
L'uso della blockchain non è gratuito e presuppone che l'utente spenda un token chiamato aeon. Gli aeon sono usati come pagamento per qualsiasi risorsa consumata sulla piattaforma, così come base per le applicazioni finanziarie implementate sulla piattaforma.  
La distribuzione degli aeon nel blocco di genesi sarà determinato da uno smart contract ospitato su Ethereum. Ulteriori aeon saranno creati tramite mining.  
Ogni compenso del sistema è pagato con aeon, ogni smart contract è stabilito in aeon.  
 
II-A.2
#### Account
Ogni account ha un indirizzo e un bilancio di aeon e anche un livello di difficoltà che aumenta ad ogni transazione ed all'altezza del suo ultimo aggiornamento. Ogni account deve anche pagare un piccolo compenso in base al tempo intercorso dalla sua apertura. I costi per creare e mantenere account prevengono lo spam e disincentivano l'aumento a dismisura degli stati. Il compenso per l'eliminazione di un account incentiva la rivendicazione di spazio.  

II-A.3
#### Sistema dei nomi
Molti sistemi di blockchain soffrono per gli indirizzi illeggibili dei loro utenti. In modo analogo al lavoro di Aaron Swartz e di Namecoin, æternity presenta un sistema nominale che è tanto decentralizzato quanto sicuro, pur supportando nomi user-friendly [9]. Lo stato della blockchain include una mappatura da stringhe unicamente user-friendly ad array di dimensioni fisse di byte. Questi nomi possono essere usati per puntare a cose come indirizzi di account su æternity o
ad hash come, per esempio, nell'albero di Merkle.

II-A.4
#### Contenuti dei blocchi
Ogni blocco contiene i seguenti componenti:
- L'hash del blocco precedente.
- Un albero di Merkle delle transazioni.
- Un albero di Merkle degli account.
- Un albero di Merkle dei nomi.
- Un albero di Merkle dei canali aperti.
- Un albero di Merkle degli oracoli che non hanno risposto alle loro rispettive domande.
- Un albero di Merkle delle risposte degli oracoli.
- Un albero di Merkle delle prove Merkle.
- L'entropia corrente nel generatore di numeri casuali.
L'hash del blocco precedente è richiesto per mantenere un ordinamento della blockchain. L'albero delle transazioni contiene tutte le transazioni che sono incluse nel blocco corrente. Ad eccezione dell'albero del voto di consenso tutti gli alberi sono interamente sotto consenso: se un albero è cambiato fra un blocco e il successivo, tale cambiamento deve essere dovuto a una transazione nell'albero delle transazioni del nuovo blocco, e una prova Merkle dell'aggiornamento deve
essere incluso nell'albero di prova del blocco. Lo scopo dei tre alberi restanti sarà chiarito nelle seguenti sezioni.  

II-B
#### Canali a stati
Uno degli sviluppi recenti più interessanti riguardo la blockchain è quello dei canali a stati. Questi operano sul principio base che in molti casi solo le persone coinvolte in una transazione devono averne conoscenza. In sintesi, le parti che effettuano una transazione instaurano qualche stato sulla blockchain, ad esempio un contratto Ethereum o un contratto Bitcoin multi-firma. Quindi inviano semplicemente aggiornamenti firmati allo stato condiviso. Il punto chiave è che entrambi potrebbero usarli per aggiornare lo stato sulla blockchain ma, nella maggior parte dei casi, non lo fanno. Ciò permette di condurre transazioni tanto rapidamente quanto le parti possono trasmettere e processare i dati invece che dover aspettare che la transazione sia stata validata (e potenzialmente finalizzata) dal meccanismo di consenso della blockchain.  
Su æternity l'unico aggiornamento dello stato che può essere stabilito sulla blockchain è un trasferimento di aeon, e gli unici aeon che possono essere trasmessi sono quelli che le parti hanno già depositato nel canale. Ciò rende ogni canale indipendente dagli altri, il che ha l'immediato beneficio che qualsiasi transazione in relazione ai canali può essere processata in parallelo migliorando considerevolmente il volume di trasmissione di transazioni.  
La blockchain è usata unicamente per risolvere l'esito finale o eventuali conflitti che potrebbero palesarsi, grossomodo analogamente al sistema giudiziario. Poiché il comportamento della blockchain sarà prevedibile, non c'è comunque alcun vantaggio nel disputarsi il risultato previsto del canale di stato: agenti malevoli sono incentivati a comportarsi correttamente e a stabilire lo stato finale sulla blockchain. Preso tutto insieme, ciò aumenta la velocità e il volume di transazione, nonché la privacy, di varie unità di grandezza.  

II-B.1
#### Smart contract
Nonostante l'unico stato che possa essere risolto on-chain sia un trasferimento di aeon, æternity comunque dispone di una macchina virtuale Turing-complete che può gestire "smart contract". I contratti su æternity sono tassativamente accordi che distribuiscono fondi in ottemperanza a certe regole, il che si pone in totale contrasto con i contratti di natura simil-giuridica come quelli di, per esempio, Ethereum. Due delle differenze pratiche più rimarchevoli sono che per default solo le parti coinvolte sono a conoscenza di un dato contratto e che solo le parti che hanno un canale di stato aperto possono creare un contratto valido. Se le parti si accordano con un contratto, lo firmano e ne conservano copia per usi futuri. Viene inviato alla blockchain solo se il suo esito è discusso, nel qual caso il codice sarà conservato esclusivamente come parte della transazione inviata, mai in alcun altro stato. Se ciò dovesse capitare, la blockchain distribuisce i token in base al contratto e chiude il canale. 

> *1 | macro Gold f870e8f615b386aad5b953fe089 ;  
2 |  
3 | Gold oracle  
4 | if 0 1000 else 0 0 end  
5 | 0*  

Fig. 1. Un semplice contratto che codifica una scommessa sul valore dell'oro. Il linguaggio utilizzato è quello simil-Forth Chalang che sarà presentato nella sezione [IV-A](#macchine-e-linguaggio-del-contratto).  

Ad esempio, la figura 1 mostra un contratto molto semplice che codifica una scommessa sul valore dell'oro in un dato momento. Alla riga 1, la macro _**Gold**_ salva l'identificatore dell'oracolo in questione il cui risultato sarà vero ("True") nel caso in cui il prezzo dell'oro sia inferiore a 38$ per grammo il primo dicembre 2016. Il corpo del contratto è visualizzato alle righe 2-4: inizialmente inviamo l'identificatore dell'oracolo sull'oro allo stack e lo invochiamo usando _**oracle**_, il quale lascerà la risposta dell'oracolo in cima allo stack. Facciamo ciò per ottenere una ramificazione condizionale: se l'oracolo restituisce _True_, inviamo 0 e 1000 allo stack, indicando che 0 aeon devono essere bruciati e che 1000 devono andare al primo partecipante del canale. Altrimenti inviamo 0 e 0, con il secondo 0 a indicare che l'altro partecipante riceve tutti gli aeon del canale. Infine inviamo 0 che verrà preso come il livello di difficoltà di questo stato del canale. Nell'uso effettivo il livello di difficoltà verrebbe generato all'apertura.  
Una cosa importante da notare è che i contratti su æternity non mantengono alcun stato per conto loro. Qualunque stato è mantenuto dalle parti e inviato come input durante l'esecuzione. Ogni contratto è essenzialmente una _funzione pura_ che prende un dato input e ritorna un nuovo canale di stato come output
> *Da notare che, potendo leggere le risposte degli oracoli e alcuni parametri ambientali, i contratti non sono del tutto _funzioni pure_. Tuttavia le risposte degli oracoli non cambiano una volta fornite e può essere messo in discussione che ciò sia dovuto alla ricchezza computazionale della macchina dell'oracolo piuttosto che si tratti di una impurità. I parametri ambientali sono ritenuti un "male necessario" e verranno idealmente compartimentalizzati appropriatamente da linguaggi di alto livello.*

I benefici nell'utilizzo di _funzioni pure_ nello sviluppo di software in generale, e in quello di applicazioni economiche in particolare, è ampiamente documentato da decenni in ambiente accademico e nell'industria [10] [cit. necessaria].  

> *1 | : hashlock  
2 | swap  
3 | hash  
4 | == ;*  

Fig. 2. Un semplice hashlock. 

> *1 | macro Commitment a9d7e8023f80ac8928334 ;  
2 |  
3 | Commitment hashlock call  
4 | if 0 100 else 0 50 end  
5 | 1*  
 
Fig. 3. Utilizzo di un hashlock per un invio trustless di token attraverso un intermediario.  

a) Interazione con i contratti e contratti progressivi:  
Anche se tutti i contratti sono privi di stato e vengono eseguiti indipendentemente l'uno dall'altro, l'interazione fra contratti e assenza di stato ("statefulness") può comunque essere ottenuta tramite **_hashlocking_** [cit. necessaria]. Un semplice hashlock è mostrato nella figura 2. Sulla linea 1 definiamo una funzione chiamata hashlock che prevede che lo stack contenga uno hash h e un segreto s. Li scambia alla linea 2, in maniera da rendere il segreto un hash alla linea 3, prima di invocare l'operatore di uguaglianza sull'hash(v) e h alla linea 4. Ciò restituisce Vero ("True") se il segreto è una immagine precedente dell'hash. Questa funzione può essere utilizzata per dichiarare l'esecuzione di ramificazioni di codice in contratti diversi sulla base dell'esistenza dello stesso valore segreto.  
Come semplice utilizzo, gli hashlock permettono agli utenti che non condividono un canale di stato di scambiarsi aeon in maniera trustless, a patto che fra di essi esistano dei canali che li mettano in comunicazione. Ad esempio, se Alice e Bob hanno un canale e Bob e Carol ne hanno un altro, allora Alice e Carol possono fare delle transazioni tramite Bob mediante la creazione di due copie del contratto in figura 3, una per ogni canale. Il "_Commitment_" di linea 1 è l'hash di un segreto scelto da Alice. Sulla linea 3 viene inviato allo stack e si richiama la funzione hashlock. Il valore di ritorno dell'hashlock determina quale ramo dell'if viene eseguito. Alice rivela il segreto non appena i contratti saranno firmati da tutte le parti coinvolte, permettendo così a Bob e a Carol di usarlo per rivendicare i loro aeon.  
L'hashlocking può essere anche utilizzato, ad esempio, per partecipare a giochi multi-player nei canali, come mostrato nella figura 4. Ognuno crea un canale con il game manager che pubblicherà lo stesso contratto in ogni canale. Ad esempio, se ci trovassimo nello stato di gioco 32, definito dalla funzione _State32_, e se volessimo aggiornare simultaneamente in maniera trustless tutti i canali allo stato 33, non appena il game manager rivelasse il segreto ciò causerebbe l'aggiornamento simultaneo di tutti i canali.  

> *1 | macro Commitment a9d7e8023f80ac8928334 ;  
2 |  
3 | Commitment hashlock call  
4 | if State33 else State32 end  
5 | call*  

Fig. 4. Un esempio semplificato dell'uso di un hashlock per giocare a un gioco multi-player nei canali.  
  
b) Esecuzione misurata:
L'esecuzione dei contratti è misurata in maniera analoga al "gas" di Ethereum, ma æternity usa due risorse differenti per la sua misurazione, una per il tempo e una per lo spazio. Entrambe sono pagate per l'utilizzo di aeon dalla parte che richiede l'esecuzione.  
Ciò potrebbe essere considerato sgradito in quanto probabilmente è un'altra parte a provocare in principio la necessità per la blockchain di risolvere la disputa. Tuttavia, a meno che tutto il denaro nel canale non sia stato usato per scommettere, ciò può essere risolto efficacemente nel codice di contratto in quanto questi è in grado di ridistribuire i fondi da una delle parti all'altra. È di fatto una buona norma generale evitare di usare tutti i fondi in un canale per la transazione per non disincentivare la parte perdente a cooperare nella chiusura del canale. 

II-B.2
#### Esempio
Portiamo tutte queste idee con i piedi per terra. In pratica, se Alice e Bob vogliono effettuare una transazione usando un canale di stato su æternity, devono avvalersi della seguente procedura:  
1) Alice e Bob firmano una transazione che specifica quanto denaro ciascuno di essi deposita nel canale, e la pubblicano nella blockchain.  
2) Una volta che la blockchain apre il canale, entrambi possono creare nuovi stati del canale, inviarseli a vicenda e firmarli. Gli stati del canale possono essere sia una nuova distribuzione dei fondi nel canale che un contratto che determini una nuova distribuzione. Ognuno di tali stati del canale ha un livello di difficoltà crescente ed è firmato da entrambe le parti così che se dovesse manifestarsi una disputa, l'ultimo stato valido possa essere inviato alla blockchain per essere imposto.  
3) Il canale può essere chiuso in due modi differenti:  
    a) Se Alice e Bob decidono che la transazione è cessata e si accordano sul loro bilancio finale, firmano entrambi una transazione che lo dichiari e la inviano alla blockchain. Questa chiuderà il canale e vi distribuirà di conseguenza il denaro.  
    b) Se Alice per qualsiasi ragione si rifiuta di firmare una transazione di chiusura, Bob può inviare l'ultimo stato firmato da entrambi e richiedere la chiusura del canale utilizzando tale stato. Ciò da il via a un conto alla rovescia. Se Alice crede che Bob sia disonesto può pubblicare prima della scadenza uno stato con un livello di difficoltà più alto che entrambi hanno siglato. Se lo fa, il canale è chiuso immediatamente. Altrimenti chiude al termine del conto alla rovescia.  

II-C
#### Meccanismo di Consenso
æternity usa un meccanismo di consenso ibrido fra Proof-of-Work e Proof-of-Stake. L'ordine dei blocchi è determinato dal metodo Proof-of-Work. Certe variabili di sistema verranno determinate in base ad un sistema di mercato predittivo residente su blockchain che permetta agli utenti di partecipare in base alla propria competenza. Per quanto riguarda l'algoritmo di validazione del consenso legato al Proof-of-Work, al momento siamo favorevoli ad utilizzare una variante del Cuckoo Cycle di Tromp, un sistema di validazione connesso alla memoria disponibile, in quanto lo riteniamo un "sistema di Proof-of-work indirettamente utile" in quanto richiede meno elettricità per girare, ed utilizza come fattore limitante anche la disponibilità dei tempi di latenza della memoria. Ciò rende anche possibile il mining tramite smartphone.  
Tromp scrive a proposito del suo lavoro:  
> *"[Il Cuckoo Cycle è] un sistema di validazione di tipo Proof-of-Work legato alla disponibilità di memoria istantaneamente verificabile unico nel suo genere in quanto fa prevalere il peso del tempo di latenza della memoria stessa piuttosto che la potenza di calcolo. In questo senso il mining di un Cuckoo Cycle è una forma di ASIC mining in cui i chip di memoria DRAM vengono pilotati dall'applicazione nella lettura e scrittura casuale di miliardi di bits.  
Quando persino i telefoni cellulari durante la ricarica notturna potranno eseguire mining senza perdite di efficenza di alcuni ordini di grandezza, non con l'atteggiamento mentale di cercare il profitto ma nell'ottica di tentare la sorte alla lotteria, il panorama hardware del mining vedrà una vasta espansione, beneficiandone sia in termini di adozione che di decentralizzazione."*
  
Introduzione: il meccanismo di consenso ha in qualche modo un ruolo non standard in æternity. Oltre a dare il consenso a nuovi blocchi della blockchain, da l'avvallo anche alle risposte alle domande dell'oracolo e ai valori dei parametri di sistema. In particolare il meccanismo di consenso può anche cambiare sé stesso. È da notare tuttavia che ciò non avviene del tutto senza problemi. Ad esempio, nel caso in cui fosse adottato solamente un metodo di validazione Proof-of-Work, sarebbe piuttosto economico corrompere i miners per manipolare a sua volta l'oracolo. Per questo motivo æternity utilizzerà un nuovo algoritmo ibrido fra Proof-of-Work e Proof-of-Stake, godendo dei benefici di entrambi. Indipendentemente da ciò, il metodo Proof-of-Work verrà utilizzato per emettere nuovi token aeon.  
Nota a margine: in origine æternity intendeva essere una blockchain convalidata al 100% da un metodo Proof-of-Stake, ma non pensiamo più sia possibile un sistema decentralizzato basato al 100% sul metodo Proof-of-Stake.  

II-C.1
#### Oracoli
L'abilità di ricorrere a valori ambientali, quali i prezzi di diversi prodotti o l'eventuale occorrenza di un evento, è una caratteristica decisiva di gran parte dei contratti, sia sotto forma testuale che codificati. Un sistema contrattuale brillante privo di questa abilità è essenzialmente un sistema chiuso e verosimilmente poco utile. Questo è un dato generalmente accettato e ci sono già diversi progetti che tentano di importare dati esterni nella blockchain in maniera decentralizzata [8]. Tuttavia la decisione circa la verità o meno di un fatto acquisito richiede essenzialmente l'implementazione di un ulteriore meccanismo di consenso al di sopra del meccanismo di consenso esistente.  
L'attivazione di due meccanismi di consenso uno sopra l'altro è costoso tanto quanto gestirli entrambi separatamente. Inoltre non aumenta la sicurezza in quanto il meno sicuro dei due può ancora essere attaccato e costretto a produrre valori "falsi". Di conseguenza proponiamo di fondere i due meccanismi di consenso in uno solo riutilizzando essenzialmente il meccanismo che adoperiamo per accordarci sullo stato del sistema per accordarci anche sullo stato del mondo esterno.  
Il modo in cui ciò avviene è il seguente. Qualsiasi possessore di aeon può lanciare un oracolo impegnandosi a rispondere a una domanda sì/no. Facendo ciò deve anche specificare il lasso di tempo entro il quale la domanda deve ricevere una risposta, che può iniziare nell'immediato o in un dato istante del futuro. L'utente che lancia l'oracolo deve, in proporzione al lasso di tempo, depositare una quantità di aeon che gli verrà restituita nel caso in cui l'utente fornisca una risposta accettata come vera, altrimenti sarà bruciata. La blockchain genera un identificatore univoco per l'oracolo che potrà essere utilizzato per recuperare la risposta appena sarà resa disponibile.  
Quando sarà ora di rispondere alla domanda, l'utente che ha lanciato l'oracolo può fornire una risposta gratuitamente. Una volta risposto, o dopo un determinato lasso di tempo, qualsiasi altro utente potrà fornire un contro reclamo depositando la stessa quantità di aeon. Se nessun reclamo sarà stato fornito entro la fine del lasso di tempo stabilito, la risposta data dall'utente che ha lanciato l'oracolo verrà accettata come vera, e il deposito sarà restituito. Nel caso in cui sia stato fornito un reclamo il meccanismo di consenso per i blocchi verrà utilizzato per rispondere all'oracolo. Ciò risulta più costoso, ma il saper di poter ottenere almeno uno dei due depositi di sicurezza ci permette di usarlo.

II-D
#### Governance
La governance dei sistemi basati sulle blockchain è stata un grande problema nel passato. Ogni volta che un sistema necessita di un aggiornamento è richiesto un "hard-fork" (una biforcazione netta della blockchain) che normalmente porta a grandi discussioni fra tutti coloro che detengono il valore (la moneta digitale). Anche questioni semplici, come la correzione di un set arbitrario di variabili nel codice sorgente vista nel dibattito sulla dimensione dei blocchi in Bitcoin, sembrano essere molto complesse in un sistema in cui gli incentivi degli utenti non sono allineati con coloro che prendono le decisioni e dove non c'è un chiaro percorso di aggiornamento. Abbiamo anche assistito a decisioni di governance più difficili che hanno richiesto un intervento rapido dagli sviluppatori del sistema, come la correzione di un singolo bug del contratto smart in "The DAO".  
Il problema principale di questi sistemi è facilmente identificabile: il processo decisionale per l'aggiornamento o il cambiamento di un protocollo non è ben definito e manca di trasparenza. Il sistema di governance di æternity è parte del meccanismo di consenso. Usa mercati predittivi per funzionare nel modo più efficace e trasparente possibile.  
Il meccanismo di consenso è inoltre definito da un numero di variabili che determinano come funziona il sistema e che sono aggiornate a poco a poco da ciascun nuovo blocco. Dal costo per effettuare transazioni o per interrogare un oracolo fino alle modifiche dei valori di parametri fondamentali come il tempo di generazione di un blocco.  
Gli utenti possono imparare come migliorare efficacemente il protocollo attivando dei mercati predittivi sulle variabili che lo definiscono. Possiamo aiutare la comunità a raggiungere un consenso su quale versione del codice utilizzare attivando dei mercati predittivi su potenziali "hard-fork" della blockchain. Ciascun utente sceglie per conto suo quale metrica preferisce ottimizzare, ma massimizzare il valore di ciò che possiede è la strategia predefinita più semplice.  

II-E
#### Scalabilità
II-E.1
#### Frammentazione ad alberi
L'architettura presentata fino a questo punto è altamente scalabile. È possibile far funzionare la blockchain anche quando ciascun utente tiene traccia esclusivamente dello stato della blockchain di suo interesse ignorando i dati altrui. I nuovi utenti hanno bisogno di almeno una copia dello stato della blockchain per essere certi del sotto-stato di loro interesse, ma possiamo frammentare tali dati attraverso parecchi nodi casuali così che il carico di ciascun nodo sia arbitrariamente piccolo. Viene utilizzato lo schema ad alberi di Merkle per dimostrare che un sotto-stato sia parte di uno stato [11]. È facile immaginare uno scenario in cui certi nodi si specializzino nel mantenere traccia delle ramificazioni e nell'essere pagati per inserimenti e consultazioni.  

II-E.2
#### Client leggero
I client leggeri non scaricano interamente i blocchi. In primo luogo l'utente da al proprio client un hash tratto dallo storico della biforcazione che preferisce, una tecnica nota anche come soggettività debole [12]. Quindi il client sa di dover scaricare biforcazioni che includono un blocco di tale hash e scarica solo le intestazioni dei blocchi, decisamente più piccole dei blocchi interi: sono pochissime le transazioni processate. Per semplicità non abbiamo fatto menzione delle intestazioni dei blocchi quando ne abbiamo discusso la struttura nella sezione [II-A.4](#contenuti-dei-blocchi), ma i loro contenuti sono i seguenti:  
    - L'hash del blocco precedente.  
    - L'hash radice di tutti gli alberi dello stato.  

II-E.3
#### Canali a stati e parallelismo
I canali a stati processano una immensa mole di dati e molte delle transazioni che avvengono al loro interno non sono mai eseguite o addirittura registrate nella blockchain. Inoltre i canali non registrano su nessuno stato condiviso con la blockchain, così tutte le transazioni che invece vengono effettivamente registrate sulla blockchain possono essere processate in parallelo. Dato che gran parte dell'hardware venduto oggi ai consumatori possiede almeno quattro processori, l'effetto immediato è che la capacità di trasmissione delle transazioni è grossomodo quadruplicata.  
Inoltre il fatto che non ci sia alcuna interazione concorrenziale complessa suggerisce che la frammentazione di questa architettura della blockchain dovrebbe essere relativamente semplice. Poiché la frammentazione di una blockchain è una tecnologia ancora piuttosto sperimentale, abbiamo deciso deliberatamente di non perseguire alcuna specifica tecnica di frammentazione nella progettazione iniziale di æternity. Tuttavia, se ci dovessero essere dei cambiamenti futuri, æternity dovrebbe essere una delle blockchain più facili da frammentare.  

II-E.4
#### Transazioni per secondo ad una certa richiesta di memoria
Le variabili che definiscono il protocollo sono tutte aggiornate costantemente dal consenso. Possiamo calcolare il tasso iniziale di default delle transazioni per secondo dai loro valori di default iniziali.   

> *1 | Nota che questa è una bozza e probabilmente  
2 | varierà  
3 |   
4 | Definiamo le seguenti variabili per il calcolo che segue:  
5 |  
6 |  B = dimensione del blocco in bytes  
7 |  F = blocchi al termine  
8 |  R = tempo al termine in secondi  
9 |  T = dimensione della transazione in bytes  
10 |  
11 |  transazioni per secondo = B * F / (T * R)  
12 |  
13 |  B = 1000000 bytes = 1 megabyte per blocco  
14 |  F = 24*60*2 blocchi al giorno  
15 |  R / F = 30 secondi per blocco  
16 |  R = 24*3600 secondi al giorno  
17 |  T = 1000 bytes per transazione   
18 |  
19 |  1000000 * 24*60*2 / 1000 / 24*3600  
20 |  = 1000000 / 1000 / 30  
21 |  = ca. 32 transazioni per secondo (sufficientemente veloce per registrare ogni essere umano entro gli 8 anni)*

Per operare un nodo dobbiamo conservare una copia di tutti i blocchi fino al suo stato conclusivo e dobbiamo essere in grado di registrare cento volte più informazioni nel caso in cui dovesse avvenire un attacco. Stimando che il termine sia due giorni, ci saranno 5760 blocchi fino al termine. Quindi i requisiti di memoria sono di 5760 * 1 megabyte * 100 = 576000 megabyte = 576 gigabyte. In assenza di un attacco servirebbero solo 5.76 gigabyte per conservare i blocchi.  

III
#### Applicazioni
L'implementazione delle seguenti applicazioni sulla blockchain di æternity è resa semplice dalla natura "stateless" degli smart contract di æternity. Questa è adatta soprattutto ai casi di utilizzo ad ampio volume.  

III-A
#### Elementi essenziali della blockchain
Gli elementi essenziali della blockchain sono necessariamente quegli elementi nativi come aeon, portafoglio, nomi e concetti collegati. Questi rendono modulari i componenti riutilizzabili che possono quindi essere utilizzati come base per le applicazioni da sviluppare e possono essere migliorati. 

III-A.1
#### Identità
A ciascun account sarà associato un ID univoco. Gli utenti possono registrare nomi univoci e collegarli alla radice Merkle della struttura dati. Questa può contenere sia l'ID univoco che altre informazioni circa l'account di un individuo. Puntiamo ad usare il formato JSON di [Schema.org](Schema.org) per rappresentare oggetti come persone o società [13].  

III-A.2
#### Portafoglio
Il portafoglio ("wallet") è un elemento di software utilizzato per interagire con æternity. Gestisce credenziali private per gli aeon, crea e firma le transazioni. Un individuo può usare il portafoglio per inviare transazioni in un certo canale, e per utilizzare le applicazioni nel network dei canali.  

III-A.3
#### Prova di esistenza
Un certo tipo di transazione permette la pubblicazione di hash di qualsiasi dato. Chiunque adoperi il sistema può usare le intestazioni per provare che i dati esistevano in quel punto nel tempo.  

III-B
#### Applicazioni su canali a stati
Gli smart contract nei canali a stati sono perfetti per micro-servizi sul web che richiedono un'alta capacità di trasmissione.  

III-B.1
#### Strumento API
La maggior parte delle API sono disponibili per chiunque voglia fare una chiamata pubblica, sono alternativamente accessibili tramite uno schema utente-password o tramite un token di accesso univoco. I canali per i pagamenti permettono una nuova tipologia di API in cui si paga per ogni richiesta all'API, eventualmente persino per ogni richiesta HTTP. Pagare per accedere ad una API risolve i problemi degli attacchi DDoS e rende più facile costruire API sempre disponibili di alta qualità. Le risposte API che richiedono un pagamento sono fondamentali per la creazione di tipologie di business ancora impossibili e possono ricoprire un ruolo importante nell'emergere di una economia decentralizzata. Creano incentivi affinché i possessori di informazioni rendano disponibili pubblicamente dati di norma privati.  

III-B.2
#### Raccolta fondi assicurata
Possiamo implementare un crowdfunding assicurato utilizzando contratti di assicurazione "dominanti" [necessita citazione]. Questi sono smart contract utilizzati per raccogliere fondi per un'opera di utilità pubblica come un nuovo ponte, una scuola o un mercato.  
I contratti di assicurazione dominanti differiscono dai contratti di assicurazione tradizionali come Kickstarter nel rendere la partecipazione la strategia dominante. Se il prodotto non è finanziato ogni partecipante rientra in possesso dei propri aeon più un certo interesse, in modo da essere assicurati contro la riduzione della loro liquidità senza aver ottenuto il prodotto. Possiamo assicurare per mezzo di un oracolo che il fornitore del prodotto o del servizio sia pagato solo nel caso in cui prodotto o servizio siano effettivamente erogati.  

III-B.3
#### Swap atomico tra blockchain
Gli swap atomici tra blockchain permettono lo scambio trustless fra aeon e bitcoin [14], [15]. Possono essere implementati tramite un blocco di hash ("hashlock") che blocchi le transazioni su entrambe le blockchain per il medesimo valore.  

III-B.4
#### Asset a valore stabile e replicazione del portafoglio
Possiamo usare gli smart contract per programmare asset sintetici che mantengano quasi lo stesso prezzo di un asset del mondo reale. Potremmo creare ad esempio un asset che mantenga lo stesso prezzo dell'oro. I derivati sintetici sono creati a coppie, uguali e opposte. Affinché un utente possieda un asset che muti con l'oro, un altro utente deve possedere un asset che muti inversamente rispetto all'oro. Ad esempio Alice potrebbe creare un contratto con Bob che le permette di possedere 1 grammo d'oro. Del denaro del contratto, l'equivalente in aeon del valore di un grammo d'oro va ad Alice e il corrispondente valore in soldi a Bob. Il contratto ha una data di scadenza fissata al momento in cui il prezzo dell'oro verrà calcolato e i fondi verranno distribuiti di conseguenza ad Alice e Bob.  

III-B.5
#### Contratti ad eventi
I contratti ad eventi pagano quando avviene un evento e non lo fanno quando non avviene, a seconda del responso dell'oracolo. Oltre a essere interessanti di per sé, possono essere utilizzati da parecchie applicazioni diverse:  
a) Assicurazioni: possiamo usare contratti ad eventi per integrare delle assicurazioni. Ad esempio i biglietti di un costoso evento musicale possono perdere il loro valore nel caso di pessime condizioni atmosferiche. Tuttavia, se lo spettatore riceve del denaro in quanto l'oracolo stabilisce che nel giorno dell'evento ha piovuto, il suo investimento viene protetto in modo che possa trovare un'alternativa emotivamente adeguata. Parlando un po' più seriamente, gli agricoltori sono sovente interessati alla quantità di precipitazioni di una stagione. Possiamo assicurarli sul pessimo raccolto dovuto alla siccità.  
b) Informatori: i contratti ad eventi possono anche essere utilizzati per incentivare la rivelazione di informazioni sensibili. Potremmo ad esempio scommettere sull'evento "Informazioni che la Società A ha fatto un uso illegale di pesticidi sono rese disponibili entro la data del 24 gennaio 2017". Qualsiasi persona con accesso a tale tipo di informazione sarebbe incentivata a scommettere sull'evento e poi a rilasciarla.  

III-B.6
#### Mercati predittivi
Un mercato predittivo funziona permettendo agli utenti di scommettere sull'eventuale occorrenza di un evento futuro. Dalle cifre puntate possiamo prevedere la probabilità del futuro [3], [8], [16]. Rappresentano il metodo più accurato per misurare il futuro ad un dato prezzo [cit. necessaria]. Una volta avvenuto l'evento, l'esito del mercato viene stabilito attraverso l'oracolo.  
Come notato nella sezione II-D, possiamo ad esempio utilizzare mercati predittivi per prevedere quali aggiornamenti del software saranno positivi e quali nocivi. Possiamo anche utilizzarli per stimare quanto i candidati di una elezione siano effettivamente in grado di mettere in pratica ciò che dichiarano, così da poter individuare più facilmente menzogne e promesse senza fondamento.   

![fig_5](https://cloud.githubusercontent.com/assets/18164515/26499741/f6818440-4233-11e7-892f-1937b1ca5f56.JPG)

Fig. 5. Mercato predittivo multidimensionale.  

a) Mercati predittivi multidimensionali: i mercati predittivi multidimensionali ci permettono di prevedere la correlazione fra possibili eventi futuri. Per esempio si potrebbe quindi prevedere se, nel caso in cui Alice fosse eletta leader, il prezzo delle patate andrebbe al ribasso o se, nel caso in cui vincesse Bob, al rialzo. Si potrebbe capire che se Google utilizzasse il piano A nei prossimi tre mesi guadagnerebbe probabilmente di più, o che se seguisse il piano B guadagnerebbe di meno. O, ancora, come in figura 5, che se Alice fosse eletta presidente ci sarebbe un'elevata probabilità che il prezzo delle patate sarebbe piuttosto basso.  

III-B.7
#### Market con un lotto in vendita ad un prezzo singolo
Un attacco per rubare aeon a un mercato ha due strategie possibili. Potrebbe sfruttare la divisione del mercato nel tempo o nello spazio.  
* Se il mercato è diviso nello spazio, allora l'attaccante fa dell'arbitraggio. Egli, facendo scambi simultanei in entrambi i mercati, annulla il rischio e fa del profitto.  
* Se il mercato è diviso nel tempo, allora l'attaccante cerca di anticipare il mercato. Egli, leggendo le transazioni in ingresso nel mercato, crea ordini di acquisto e di vendita immediatamente prima e dopo.  

![fig_6](https://cloud.githubusercontent.com/assets/18164515/26499742/f682326e-4233-11e7-84f0-9aed9927db25.JPG)

Fig. 6. La linea nera è la curva di domanda, quella rossa di offerta. Le vendite in rosso sono della stessa dimensione degli acquisti in nero. La linea verticale è il prezzo selezionato dal creatore del mercato. Chiunque fosse intenzionato a comprare a un prezzo più alto ha scambiato a quel prezzo, chiunque fosse intenzionato a vendere a un prezzo più basso ha scambiato a quel prezzo.  
  
Per riunione i mercati nello spazio, tutti dovrebbero utilizzare lo stesso creatore del mercato.  
Per riunirli nel tempo dobbiamo fare scambi per lotti, ciascun lotto ad un singolo prezzo. Il creatore del mercato deve proporre a ciascuna persona il prezzo da lui stabilito e se qualcuno dovesse scoprire proposte contraddittorie da parte del creatore, allora tutti i suoi clienti dovrebbero essere in grado di prosciugare ogni suo canale. Se il creatore dovesse proporre un prezzo ragionevole, allora dovrebbe ottenere lo stesso volume di acquirenti e venditori, come mostrato in fig. 6. Altrimenti finirebbe in una situazione simile a quella di fig. 7, prendendosi dunque un grave rischio.  

![fig_7](https://cloud.githubusercontent.com/assets/18164515/26499743/f6831eae-4233-11e7-9d89-76e491660787.JPG)

Fig. 7. Il nero è molto più esteso del rosso. Il creatore del mercato sta vendendo molte più quote di quante ne stia comprando, prendendosi di conseguenza un grave rischio.  
  
IV
#### Implementazione
Molti concetti chiave hanno già implementazioni a livello prototipale in Erlang, inclusi la stessa blockchain, il linguaggio contrattuale e la VM, l'oracolo e i meccanismi di governance e anche una vecchia versione del meccanismo di consenso. Abbiamo usato Erlang/OTP in quanto rende agevole la scrittura di codice in grado di rispondere a molte richieste in parallelo senza andare in crash. I server con il più elevato tempo di funzionamento sono basati su Erlang. Ha dimostrato di essere un prodotto stabile e affidabile in trent'anni di uso per applicazioni industriali.  

IV-A
#### Macchine e linguaggio del contratto
La macchina virtuale (VM o "virtual machine") è basata su stack ed è simile ai linguaggi di scripting di Forth e Bitcoin, anche se in rapporto a quest'ultimo è decisamente più ricca. La VM supporta funzioni piuttosto che reindirizzamenti ("gotos") rendendo relativamente semplice l'analisi della sua semantica. Si può trovare una lista dei codici operativi della VM sul [nostro Github](https://github.com/aeternity/chalang/blob/master/opcodes.md ).  
Inoltre esiste un linguaggio simile a Forth di livello superiore, il Chalang, che compila in bytecode per la VM. Supporta macro e nomi di variabili, ma mantiene il modello di esecuzione basato su stack [17]. Potete trovare esempi di codice Chalang sempre sul [nostro Github](https://github.com/aeternity/chalang/tree/master/examples ).  

IV-B
#### Adozione tramite integrazione web
Il web è la piattaforma di applicazione più popolare. Forniremo strumenti di sviluppo web facili da usare, come librerie JS e JSON-API per le caratteristiche di base della blockchain æternity. 

IV-C
#### Moduli open source
Il software sarà scritto con moduli di licenza MIT, come il modulo di consenso che può essere adattato a necessità individuali, così da poterlo facilmente riutilizzare per un consorzio di blockchain privato e per altri usi.  

IV-D
#### Condizioni d'uso e design dell'UX
I nostri sforzi di sviluppo saranno focalizzati nel ridurre gli attriti dovuti alla interazione umana. Nel dettaglio, ci assicureremo che sia chiaramente stabilito chi controlla identità, chiavi e transazioni. Inoltre, offrire un accesso facilitato tramite web-gateway sarà al centro del nostro futuro lavoro. La partecipazione degli utenti ai mercati predittivi tramite interfacce mobili simili a Tinder (scorrimento sinistra/destra) e la facile integrazione in un sito attraverso iframe di semplici portafogli web diventeranno esperienza di uso comune.  

V
#### Discussioni
Abbiamo fornito una spiegazione su come progettare un sistema di trasferimento di valore fondamentalmente più efficiente. Il sistema descritto è di fatto una macchina-oracolo globale, cioè una machcina che può essere usata per fornire servizi decisionali su scala globale. In particolare si possono implementare facilmente su æternity tutte le applicazioni proposte nella [III sezione](#applicazioni).  
Il nostro approccio ha tuttavia sia limiti fondamentali che spazi di miglioramento. Entrambi vengono discussi qui.  

V-A
#### Limitazioni e compromessi
Nonostante crediamo che i compromessi fatti nella nostra architettura siano ragionevoli visto l'incremento conseguente di performance in altre aeree, æternity non è una soluzione onnicomprensiva per applicazioni decentralizzate. Dovrebbe essere piuttosto vista come un complemento sinergico alle attuali tecnologie. Ci sono diverse considerazioni di cui ci si deve rendere conto.  

V-A.1
#### Stati sulla blockchain
Nonostante abbia molti vantaggi, la mancanza di stati programmabili di æternity la rende inadeguata per le applicazioni che richiedono di mantenere sotto consenso uno stato personalizzato. Ad esempio ciò include le DAO (Organizzazioni Decentralizzate Autonome o "Decentralized Autonomous Organizations") per come sono normalmente concepite, i sistemi di nomi personalizzati e le sotto-valute che non sono legate al valore di un asset di base.  

V-A.2
#### Problema dell'opzione gratuita
Se Alice e Bob possiedono un canale e Alice sigla un contratto, quando lo invia a Bob gli da essenzialmente una libera opzione: Bob potrebbe scegliere di siglare e restituire (cioè attivare) il contratto in qualsiasi momento del futuro. Spesso ciò non è però voluto. Per evitare questo problema i contratti del canale non sono attivati immediatamente con la cifra intera, ma sono suddivisi in tempo o spazio. Entrambi i partecipanti sigleranno i contratti in brevi intervalli così da evitare che un utente offra una grande opzione libera all'altro.  
Ad esempio, se le parti vogliono scommettere 100 aeon, allora potrebbero siglare il contratto in 1000 frazioni, ognuna delle quali incrementerebbe la scommessa di 0,1 aeon. Ciò richiederebbe il passaggio di 1000 messaggi, 500 in ogni direzione, il che risulterebbe abbastanza economico dato che il contratto non verrebbe mai sottomesso alla blockchain. Come ulteriore esempio, se qualcuno volesse creare un asset economico della durata di 100 giorni, si potrebbe siglare in 2400 frazioni di un'ora ciascuna, cioè 2400 messaggi, 1200 in ciascuna direzione. 

V-A.3
#### Perdita di liquidità e tipologie di macchine a stati
Quando si compongono canali mediante un blocco di hash ("hashlock") come mostrato nella sezione [II-B.1](#smart-contract), ogni intermediario deve bloccare almeno il doppio degli aeon trasmessi per suo tramite. Ad esempio, se Alice e Carol vogliono compiere una transazione tramite Bob, Bob agirà come Carol quando interagirà con Alice e viceversa.  
Poiché questo risulta costoso per Bob, molto probabilmente guadagnerebbe una tariffa come compenso. Se Alice e Carol pensano di condurre molti scambi fra di loro, possono evitare ciò creando un nuovo canale e trasferendogli in maniera trustless i contratti attivi utilizzando un hashlock.  
Ma poiché il mantenimento di un ulteriore canale aperto impatta negativamente la liquidità personale, il passaggio da un intermediario rimane preferibile in molti casi, soprattutto quando le parti non si aspettano di commerciare molto nel futuro. Dunque si prevede l'emergere di una tipologia di canale in cui alcuni ricchi utenti guadagnino nel trasmettere in maniera trustless transazioni fra altri utenti.  
È da notare che ciò non costituisce un punto critico di fallimento in quanto non affidiamo nulla a questi trasmettitori di transazioni. Se un trasmettitore andasse offline prima che il segreto fosse rivelato ad un hashlock, la transazione non passerebbe. Se dovesse andare offline in seguito, l'unico possibile effetto "negativo" è che il trasmettitore non sarebbe in grado di reclamare i propri aeon.  

V-B
#### Lavori Futuri
Ci sono varie possibilità per migliorare l'architettura attuale.  

V-B.1
#### Linguaggio funzionale del contratto
Una strada ragionevole per il futuro potrebbe essere la sperimentazione con linguaggi di alto livello che rispettino più strettamente il paradigma funzionale. Il mantenere traccia di uno stack implicito generalmente predispone ad errori e presumibilmente non è adatto ad un linguaggio di alto livello pensato per lo sviluppo. Ciò dovrebbe essere piuttosto semplice dal momento che i programmi sono già puramente funzionali e semplificherebbe enormemente sia lo sviluppo che la verifica formale dei contratti. Se ciò fosse fatto, avrebbe anche senso rivedere la VM per abbinarla strettamente al nuovo linguaggio per rendere la compilazione meno propensa a errori e meno dipendente dalla fiducia nei confronti degli sviluppatori. Idealmente la traduzione dal linguaggio di superficie al codice della VM dovrebbe essere una trascrizione diretta di una ricerca rivista tra pari, anche se probabilmente bisognerebbe fare delle concessioni pragmatiche.  

V-B.2
#### Canali multi-parti
Al momento tutti i canali su æternity sono limitati a due parti. Nonostante si potrebbero ottenere di fatto canali multi-parti attraverso hashlocking, ciò potrebbe risultare costoso. Per questo motivo stiamo progettando di studiare la possibilità di aggiungere il supporto a canali di _n-_parti con un meccanismo di accordo di tipo _m-_di_-n_.  

#### GLOSSARIO  

**Blockchain** Un database distribuito, non manomissibile con accesso libero e pay-per-use ("metered"). Il database è costituito da una lista crescente di blocchi collegati tramite hash, e può utilizzare una qualsiasi regola per collegarli.  

**Aeon** Un aeon rappresenta una unità di accreditamento ed un diritto di accesso alla blockchain æternity. E' trasferibile.  

**Transazione** Un messaggio da uno utente della blockchain. Questo è il modo in cui gli utenti possono utilizzare la loro moneta per accedere alla blockchain.  

**Canali a stati** Una relazione tra due utenti registrata sulla blockchain. Essa abilita gli utenti ad inviare aeon avanti ed indietro, ed a creare smart contract che non necessitino di fiducia reciproca tra gli utenti stessi in quanto i contratti vengono rinforzati e determinati dalla blockchain.  

**Hash** Un hash prende come informazione in ingresso ("input") un dato di tipo binario di qualsiasi dimensione. Restituisce una informazione in uscita ("output") di dimensione stabilita. Lo stesso input determina il medesimo output. Ma dato un output, non si può risalire all'input che l'ha generato.  

**Hashlocking** Questo è il modo in cui colleghiamo coppie di canali per creare uno smart contract the coinvolgano più di due persone. Un segreto viene referenziato dal suo proprio hash. Quando il segreto è rivelato, può aggiornare molteplici canali contemporaneamente.  

**Governance** Un processo ben definito per la modalità di revisione di ogni futuro protocollo(i) della blockchain. 

**Oracoli** Un meccanismo che racconta alla blockchain i fatti accaduti nel mondo reale in cui viviamo. Attraverso gli oracoli gli utenti possono predire l'esito degli eventi, esternamente al sistema della blockchain.  

**Detentori di valore** Un utente che possieda aeon, o un derivato finanziario nel sistema.  

**Validatore** Un validatore è un utente che partecipa al meccanismo di consenso. Nel caso di æternity, ogni detentore di valore può partecipare a tale processo.  

#### RINGRAZIAMENTI  

Grazie a Vlad, Matt, Paul, Dirk, Martin, Alistair, Devon e Ben per la revisione. Grazie a queste e molte altre persone per il confronto approfondito.  

#### RIFERIMENTI  

