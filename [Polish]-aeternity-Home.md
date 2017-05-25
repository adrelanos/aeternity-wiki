<a href="http://www.aeternity.com/"><img width="160px" src="http://www.aeternity.com/user/themes/aeon/img/aeternity_logo.png" align="left" hspace="10" vspace="10"></a>

<p align = right><a target="_blank" href="https://twitter.com/intent/tweet?original_referer=https%3A%2F%2Fabout.twitter.com%2Fresources%2Fbuttons&text=Aeternity:%20scalable%20smart%20contracts%20interfacing%20with%20real%20world%20data&tw_p=tweetbutton&url=http%3A%2F%2Fwww.aeternity.com%2F&via=aetrnty"><img src="http://s30.postimg.org/j2q6ql27h/Tweet.png"></a>
<a target="_blank" href="https://twitter.com/aetrnty"> <img src="https://s24.postimg.org/4xcf9j8xh/Follow-_Twitter.jpg?2"></a>
</p>
<b>æternity Blockchain – Funkcjonalna Maszyna Wyrocznia<p>

æternity to protokół [blockchain](https://en.wikipedia.org/wiki/Blockchain) zbudowany od  zera w języku [Erlang](https://en.wikipedia.org/wiki/Erlang_(programming_language)) z uwzględnieniem prędkości, sprawności i skalowalności. Oferuje unikalny, hybrydowy [mechanizm konsensusu](https://www.ibm.com/developerworks/cloud/library/cl-blockchain-basics-intro-bluemix-trs/) [proof of work (PoW)](https://en.wikipedia.org/wiki/Proof-of-work_system) oraz [proof of stake (PoS)](https://en.wikipedia.org/wiki/Proof-of-stake) który może być zastosowany do sprawdzania [[wyroczni]], co maksymalizuje ich wydajność, ponieważ zapobiega nawarstwianiu się mechanizmów konsensusu na górze każdego z nich. [[Kanały stanów]] maksymalizują skalowalność i prywatność poprzez usunięcie potrzeby do zachowania kodu smart-kontraktu w łańcuchu. Transfer [tokenów](http://cruiserselite.co.in/downloads/btech/materials/second%20sem/4/e-com/UNIT-3.pdf) przez kanały odbywa się przez funkcjonalne [smart-kontrakty](https://en.wikipedia.org/wiki/Smart_contract) które mają dostęp do rzeczywistych danych przez Wyrocznię. æternity renderuje smart-kontrakty szybciej, pozwala na ich łatwiejsze wykonanie i większą tolerancję na błędy, bez degradacji ich wydajności czy funkcjonalności.<p>

[Specyfikacja](https://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf) æternity została opublikowana aby zaprezentować tę architekturę i jej potencjalną użyteczność. æternity jest budowane do zastosowania w skali globalnej na[rynkach prognostycznych](https://pl.wikipedia.org/wiki/Rynek_prognostyczny), [syntetycznych rynkach aktywów](https://syntheticassets.wordpress.com/) oraz [w wielu innych przykładach użycia](https://github.com/aeternity/wiki/wiki/Idea-Box#use-case-ideas-for-%C3%A6ternity).<p>

<b>Jak łańcuch bloków æternity może służyć jako platforma smart-kontraktowa?<p>

Wyróżniamy trzy główne problemy, które leżą u podstaw obecnie dostępnych platform smart-kontraktowych.
Są to głównie brak wystarczającej skalowalności (przepustowość globalnego użycia), bezpieczeństwo kodu oraz 
relatywnie niedrogi dostęp do danych rzeczywistych i zarządzania łańcuchem:
<p>

<ol>
<li>
Obecnie powszechne pełno-stanowe projekty renderują smart-kontrakty zakodowane na platformach smart-kontraktów jak Ethereum
jako trudne do analizy. Ponadto poprzez powiązanie bezpełno-stanowości z sekwencyjnym porządkowaniem transakcji znacznie
redukuje skalowalność łańcucha bloków.
<li> Trudność aby wprowadzić dane rzeczywiste do platform smart-kontraktowych w niezaufany, zdecentralizowany oraz solidny sposób w znacznym stopniu przeszkadza w realizacji dużej liczby korzystnych aplikacji smart-kontraktów.
<li>Większość platform smart-kontraktowych ma ograniczone możliwości usprawniania się, aby radzić sobie w nowo powstałej ekonomii i wiedzy technologicznej.
</ol><p>

Recent studies of the state channel technology have proven that, in many instances, storing state on-chain is unnecessary. In most cases, all data can be stored in state channels, and the Blockchain would be only used to settle the economic results of exchange of information and/or to act as a fallout whenever a dispute occurs. This represents an alternative Blockchain architecture approach, which is marked by Turing-complete smart contracts that exist in state channels but not on the Blockchain. This would boost scalability as all transactions are independent and can be processed in parallel. Furthermore, this approach means that smart contracts will not write to shared state, which will greatly simplify contracts’ safety and the process of testing and verification.

Decentralized prediction markets like Augur and Gnosis are attempting to integrate real-world data with the Blockchain in a decentralized manner via a process that implements a consensus mechanism on smart contracts, on top of the Blockchain. This will result in inefficiencies, and it wo=ill not boost security. So, it is logically better to generalize the consensus mechanism of the Blockchain so that it can provide information on the next internal state as well as on the external world’s state via its own mechanisms. That way we can ensure that the Blockchain’s consensus mechanism dictates the outcome of executing what complexity theory describes as an “oracle machine”. An oracle machine is a theoretical machine that is far more powerful than a Turing machine due to the fact that it can bear answers to questions whose answers cannot be computed such as “Who won the Super Bowl in 2016?”

Wiki w pełni przetłumaczone na język polski przy pomocy Google Translate można znaleźć na stronie:
* [Home Polski](https://translate.google.com/translate?sl=en&tl=pl&u=https://github.com/aeternity/wiki/wiki/)



