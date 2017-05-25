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
I-A [Un lavoro precedente](#un-lavoro-precedente) . . . . . . . . . . . . . 2  
II [Cos'è la blockchain æternity](#cosé-la-blockchain-æternity)  . . . . . . . . . . . 2  
II-A [Token, account e blocchi](#token-account-e-blocchi)  . . . . . . . . . 2  
II-A.1 [Token di accesso, Aeon](#token-di-accesso-aeon)  . . . . . . . . . 2  
II-A.2 [Account](#account) . . . . . . . . . . . . . . . . . 2  
II-A.3 [Sistema dei nomi](#sistema-dei-nomi)  . . . . . . . . . . . . 3  
II-A.4 [Contenuti dei blocchi](#contenuti-dei-blocchi) . . . . . . . . . . 3  
II-B [State channel](#state-channel) . . . . . . . . . . . . . . . 3  
II-B.1 [Smart contract](#smart-contract)  . . . . . . . . . . . . . 3  
II-B.2 [Esempi](#esempi)  . . . . . . . . . . . . . . . . . 4  
II-C [Meccanismo di Consenso](#meccanismo-di-consenso)  . . . . . . . . . . 5  
II-C.1 [Oracoli](#oracoli) . . . . . . . . . . . . . . . . . 5  
II-D [Governance](#governance)  . . . . . . . . . . . . . . . . 5  
II-E [Scalabilità](#scalabilità) . . . . . . . . . . . . . . . . 6  
II-E.1 [Sharding trees](#sharding-trees) . . . . . . . . . . . . . 6  
II-E.2 [Client leggero](#client-leggero)  . . . . . . . . . . . . . 6  
II-E.3 [State channel e parallelismo](#state-channel-e-parallelismo). . . . . . . 6  
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
III-B.5 [Contratti dell'evento](#contratti-dellevento)  . . . . . . . . . 7  
III-B.6 [Mercati predittivi](#mercati-predittivi) . . . . . . . . . . . 7  
III-B.7 [Market con un lotto in vendita ad un prezzo singolo](#market-con-un-lotto-in-vendita-ad-un-prezzo-singolo) . . . . . . 7  
IV [Implementazione](#implementazione) . . . . . . . . . . . . . . . 8  
IV-A [Macchine e linguaggio del contratto](#macchine-e-linguaggio-del-contratto) . . . . 8  
IV-B [Adozione tramite integrazione web](#adozione-tramite-integrazione-web) . . . . . 8  
IV-C [Moduli open source](#moduli-open-source)  . . . . . . . . . . . . 8  
IV-D [Condizioni d'uso e design dell'UX](#condizioni-duso-e-design-dellux) . . . . . 8  
V [Discussioni](#discussioni)  . . . . . . . . . . . . . . . . . 8  
V-A [Limitazioni e tradeoff](#limitazioni-e-tradeoff) . . . . . . . . . . . 9  
V-A.1 [Stati sulla blockchain](#stati-sulla-blockchain) . . . . . . . . . . 9  
V-A.2 [Problema dell'opzione gratuita](#problema-dellopzione-gratuita) . . . . . . 9  
V-A.3 [Perdita di liquidità e tipologie di macchine a stati](#perdita-di-liquidità-e-tipologie-di-macchine-a-stati) . . . . . 9  
V-B [Lavori Futuri](#lavori-futuri)  . . . . . . . . . . . . . . . 9  
V-B.1 [Linguaggio funzionale del contratto](#linguaggio-funzionale-del-contratto)  . . . 9  
V-B.2 [Canali multi-parti](#canali-multi-parti) . . . . . . . . . . . . 9

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
Primo, il predominio dello “stateful design” rende gli smart contract scritti per queste piattaforme difficili da analizzare 1
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
Uno degli sviluppi recenti più interessanti riguardo la blockchain è quello dei canali di stato. Questi operano sul principio base che in molti casi solo le persone coinvolte in una transazione devono averne conoscenza. In sintesi, le parti che effettuano una transazione instaurano qualche stato sulla blockchain, ad esempio un contratto Ethereum o un contratto Bitcoin multi-firma. Quindi inviano semplicemente aggiornamenti firmati allo stato condiviso. Il punto chiave è che entrambi potrebbero usarli per aggiornare lo stato sulla blockchain ma, nella maggior parte dei casi, non lo fanno. Ciò permette di condurre transazioni tanto rapidamente quanto le parti possono trasmettere e processare i dati invece che dover aspettare che la transazione sia stata validata (e potenzialmente finalizzata) dal meccanismo di consenso della blockchain.  
Su æternity l'unico aggiornamento dello stato che può essere stabilito sulla blockchain è un trasferimento di aeon, e gli unici aeon che possono essere trasmessi sono quelli che le parti hanno già depositato nel canale. Ciò rende ogni canale indipendente dagli altri, il che ha l'immediato beneficio che qualsiasi transazione in relazione ai canali può essere processata in parallelo migliorando considerevolmente il volume di trasmissione di transazioni.  
La blockchain è usata unicamente per risolvere l'esito finale o eventuali conflitti che potrebbero palesarsi, grossomodo analogamente al sistema giudiziario. Poiché il comportamento della blockchain sarà prevedibile, non c'è comunque alcun vantaggio nel disputarsi il risultato previsto del canale di stato: agenti malevoli sono incentivati a comportarsi correttamente e a stabilire lo stato finale sulla blockchain. Preso tutto insieme, ciò aumenta la velocità e il volume di transazione, nonché la privacy, di varie unità di grandezza.  

II-B.1
#### Smart contract
Nonostante l'unico stato che possa essere risolto on-chain sia un trasferimento di aeon, æternity comunque dispone di una macchina virtuale Turing-complete che può gestire "smart contract". I contratti su æternity sono tassativamente accordi che distribuiscono fondi in ottemperanza a certe regole, il che si pone in totale contrasto con i contratti di natura simil-giuridica come quelli di, per esempio, Ethereum. Due delle differenze pratiche più rimarchevoli sono che per default solo le parti coinvolte sono a conoscenza di un dato contratto e che solo le parti che hanno un canale di stato aperto possono creare un contratto valido. Se le parti si accordano con un contratto, lo firmano e ne conservano copia per usi futuri. Viene inviato alla blockchain solo se il suo esito è discusso, nel qual caso il codice sarà conservato esclusivamente come parte della transazione inviata, mai in alcun altro stato. Se ciò dovesse capitare, la blockchain distribuisce i token in base al contratto e chiude il canale. 

II-B.2
#### Esempi
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
II-E
#### Scalabilità
II-E.1
#### Sharding trees
II-E.2
#### Client leggero
II-E.3
#### State channel e parallelismo
II-E.4
#### Transazioni per secondo ad una certa richiesta di memoria
III
#### Applicazioni
III-A
#### Elementi essenziali della blockchain
III-A.1
#### Identità
III-A.2
#### Portafoglio
III-A.3
#### Prova di esistenza
III-B
#### Applicazioni su canali a stati
III-B.1
#### Strumento API
III-B.2
#### Raccolta fondi assicurata
III-B.3
#### Swap atomico tra blockchain
III-B.4
#### Asset a valore stabile e replicazione del portafoglio
III-B.5
#### Contratti dell'evento
III-B.6
#### Mercati predittivi
III-B.7
#### Market con un lotto in vendita ad un prezzo singolo
IV
#### Implementazione
IV-A
#### Macchine e linguaggio del contratto
IV-B
#### Adozione tramite integrazione web
IV-C
#### Moduli open source
IV-D
#### Condizioni d'uso e design dell'UX
V
#### Discussioni
V-A
#### Limitazioni e tradeoff
V-A.1
#### Stati sulla blockchain
V-A.2
#### Problema dell'opzione gratuita
V-A.3
#### Perdita di liquidità e tipologie di macchine a stati
V-B
#### Lavori Futuri
V-B.1
#### Linguaggio funzionale del contratto
V-B.2
#### Canali multi-parti