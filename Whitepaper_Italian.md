# La blockchain Æternity
## La piattaforma di oracoli decentralizzata, perfettamente funzionale e trustless(**)
_(**trustless: che non richiede la fiducia in enti terzi che validino l'operato della piattaforma stessa)_

February 6, 2017
v0.1

* Zackary Hess zack@aeternity.com
* Yanislav Malahov yani@aeternity.com
* Jack Pettersson jack@aeternity.com

Abstract — Dal momento dell'introduzione di Ethereum nel 2014 c'è stato un grande interesse nelle applicazioni decentralizzate trustless (contratti smart). In seguito, molti hanno tentato di implementare applicazioni con dati derivanti dal mondo reale innestati su di una blockchain. Noi crediamo che allocare lo stato ed il codice di una applicazione sulla blockchain sia sbagliato per varie ragioni. Presentiamo l'architettura altamente scalabile di una blockchain dotata di un meccanismo di consenso che è anche usato per controllare l'oracolo. Questo rende l'oracolo molto efficiente, perché evita lo stratificarsi di ciascun meccanismo di consenso sopra ad un altro. I canali a Stati sono integrati pper incrementare la privacy e la scalabilità. I token nei canali possono essere trasferiti utilizzando smart contract perfettamente funzionali che possono accedere alle domande dell'oracolo. Non allocando codice di contratto sulla catena, siamo in grado di creare contratti smart più semplici da analizzare e più veloci da processare, con nessuna sostanziale perdita sulla funzionalità reale. Applicazioni come i mercati per gli asset sintetici e i mercati predittivi possono essere efficientemente implementate su scala globale. Diverse parti hanno una implementazione prototipale in Erlang. Gli strumenti di sviluppo e le applicazioni essenziali come il portafoglio, un sistema di identificazione e di attribuzione del nome saranno anche predisposti.

# CONTENUTI
I [Introduzione](#introduzione) . . . . . . . . . . . . . . . . . 1  
I-Un lavoro predecente . . . . . . . . . . . . . 2  
II La blockchain Æternity  . . . . . . . . . . . 2  
II-A Token, account e blocchi  . . . . . . . . . 2  
II-A.1 Token di accesso, Aeon  . . . . . . . . . 2  
II-A.2 Account . . . . . . . . . . . . . . . . . 2  
II-A.3 Sistema dei nomi  . . . . . . . . . . . . 3  
II-A.4 Contenuti dei blocchi . . . . . . . . . . 3  
II-B State channel . . . . . . . . . . . . . . . 3  
II-B.1 Smart contract  . . . . . . . . . . . . . 3  
II-B.2 Esempi  . . . . . . . . . . . . . . . . . 4  
II-C Meccanismo di Consenso  . . . . . . . . . . 5  
II-C.1 Oracoli . . . . . . . . . . . . . . . . . 5  
II-D Governance  . . . . . . . . . . . . . . . . 5  
II-E Scalabilità . . . . . . . . . . . . . . . . 6  
II-E.1 Sharding  trees . . . . . . . . . . . . . 6  
II-E.2 Client leggero  . . . . . . . . . . . . . 6  
II-E.3 State channel e parallelismo. . . . . . . 6  
II-E.4 Transazioni per secondo ad una certa richiesta di memoria 6  
III Applicazioni . . . . . . . . . . . . . . . . 6  
III-A Elementi essenziali della blockchain . . . 6  
III-A.1 Identità . . . . . . . . . . . . . . . . 6  
III-A.2 Portafoglio  . . . . . . . . . . . . . . 6  
III-A.3 Prova di Esistenza . . . . . . . . . . . 6  
III-B Applicazioni su canali a Stati . . . . . . 7  
III-B.1 Strumento API  . . . . . . . . . . . . . 7  
III-B.2 Raccolta fondi assicurata  . . . . . . . 7  
III-B.3 Swap atomico tra blockchain  . . . . . . 7  
III-B.4 Asset a valore stabile e replicazione del portafoglio . . . . 7  
III-B.5 Contratti dell'evento  . . . . . . . . . 7  
III-B.6 Mercati predittivi . . . . . . . . . . . 7  
III-B.7 Market con un lotto in vendita ad un prezzo singolo . . . . . . 7  
IV Implementazione . . . . . . . . . . . . . . . 8  
IV-A Macchine e linguaggio del contratto . . . . 8  
IV-B Adozione tramite integrazione web . . . . . 8  
IV-C Moduli open source  . . . . . . . . . . . . 8  
IV-D condizioni d'uso e design dell'UX . . . . . 8  
V Discussioni  . . . . . . . . . . . . . . . . . 8  
V-A Limitazioni e tradeoff . . . . . . . . . . . 9  
V-A.1 Stati sulla blockchain . . . . . . . . . . 9  
V-A.2 Problema dell'opzione gratuita . . . . . . 9  
V-A.3 Perdita di liquidità e tipologie di macchine a stati . . . . . 9  
V-B Lavori Futuri  . . . . . . . . . . . . . . . 9  
V-B.1 Linguaggio funzionale del contratto  . . . 9  
V-B.2 Canali multi-parti . . . . . . . . . . . . 9  

#### Introduzione
Lo scopo di questo paper è di dare un quadro d'insieme della architettura della blockchain Æternity blockchain e delle sue possibili applicazioni. Paper più dettagliati verranno rilasciati in futuro, specificatamente per i meccanismi di consenso e governance. In ogni caso, deve essere sottolineato che la nostra architettura è olistica; tutti i componenti sono strettamente interconnessi e sinergici, in maniera modulare. La struttura di questo paper è suddivisa in quattro parti.
* Primo, introdurremo e analizzeremo la struttura teorica fondamentale che da forma alla nostra architettura.
* Secondo, analizzeremo le applicazioni essenziali integrate (1), altri possibili casi di utilizzo e daremo degli spunti di come sia possibile per uno sviluppatore utilizzare la piattaforma.
* Terzo, presenteremo l'attuale implementazione del POC (proof-of-concept), scritto in Erlang.
* Concluderemo con una discussione che includa possibili futuri sviluppi e comparazioni con altre tecnologie.

A. Le Blockchain nate precedentemente, prima di tutti il Bitcoin, hanno mostrato un nuovo modo di consentire il trasferimento di valore su Internet [1].  A ciò è seguito un certo numero di promettenti passi in avanti: Ethereum ha mostrato un modo per scrivere smart contract Turing-complete legati ad una architettura blockchain [2]; Truthcoin ha creato degli strumenti per creare degli oracoli su blockchain [3], mentre Gnosis e Augur hanno mostrato come rendere gli stessi più efficienti [4]; Casey Detrio ha mostrato come creare dei mercati su blockchain [5]; Namecoin come una prova di esistenza di qualsiasi dato digitale [7]. Queste tecnologie sono molto promettenti qualora giungano a fornire servizi finanziari e legali di prim'ordine a ciascuno. 

Per ora però hanno fallito nel mettersi insieme in un sistema unificato che mantenga le promesse. Più specificatamente, tutte le soluzioni sono venute meno in almeno uno dei seguenti aspetti: governance, scalabilità, sicurezza del codice e accesso economico ai dati del mondo reale [richiede citazione]. Æternity punta a migliorare lo stato dell'arte in tutti questi aspetti.

############# PROSEGUIRE TRADUZIONE #################