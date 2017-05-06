### Abstract
 Since the introduction of Ethereum in 2014 there
has  been  great  interest  in  decentralized  trustless  applications
(smart contracts). Consequently, many have tried to implement
applications  with  real  world  data  on  top  of  a  blockchain.  We
believe that storing the application’s state and code on-chain is
wrong  for  several  reasons.

We present a highly scalable blockchain architecture with a
consensus  mechanism  which  is  also  used  to  check  the  oracle.
This makes the oracle very efficient, because it avoids layering
one  consensus  mechanism  on  top  of  another.  State  channels
are  integrated  to  increase  privacy  and  scalability.  Tokens  in
channels  can  be  transferred  using  purely  functional  smart
contracts that can access oracle answers. By not storing contract
code  or  state  on-chain,  we  are  able  to  make  smart  contracts
easier to analyze and faster to process, with no substantial loss in de facto functionality.

Applications like markets for synthetic assets and prediction
markets can be efficiently implemented at global scale. Several
parts have proof-of-concept implementations in Erlang. Development tools and application essentials such as a wallet, naming and  identity  system  will  also  be  provided.  

***


Download the entire white paper v0.1 (PDF) here:
[Æternity whitepaper](https://blockchain.aeternity.com/%C3%A6ternity-blockchain-whitepaper.pdf)

Authors:  
Zackary Hess - zack@aeternity.com  
Yanislav Malahov - yani@aeternity.com  
Jack Pettersson - jack@aeternity.com

Published February 6, 2017