# Testnet setup start and use

I had issues to setup up and use the æternity testnet so I modified the
original 'setup_test.sh' script from Zack [origin script](../../../../aeternity/testnet/blob/master/setup_test.sh)

This work results to create this new script [initd-aeternity.sh](../../../../Zwilla/aeternity-testnet/blob/master/initd-aeternity.sh)



## How To handle the initd-aeternity script?

How to? | COMMAND
------------ | -------------
Starting Testnet | `sh setup_test.sh`
Stop Testnet | `sh initd-aeternity.sh stop`
Access screen session 3010| `screen -r aeternity-3010`
Access screen session 3020| `screen -r aeternity-3020`
Access screen session 3030| `screen -r aeternity-3030`

***

# How it works!
The script ' [setup_test.sh](https://github.com/Zwilla/aeternity-testnet/blob/master/setup_test.sh) '
will copy 3 times the testnet-folder into this main folders:

- aeternity-testnet3010
- aeternity-testnet3020
- aeternity-testnet3030

**(WARNING! DO NOT RUN SCRIPST FROM ..3010/20/30 folders)**

 * Than it will compile and clean the testnet.app and
 * starts a screen session for every NODE!

 You can access the every screens session.
 * Node 3010 starts as mining node
 * Node 3020 and 3030 as full node

 To make some tests run this script:
 [lightning_test.sh](https://github.com/Zwilla/aeternity-testnet/blob/master/tests/lightning_test.sh)


  You find this file here: https://github.com/Zwilla/aeternity-testnet/blob/master/docs/testnet.md

  After running the test_setup script you can choose now:

Choose  | COMMAND
------------ | -------------
 (1) update and setup! | will setup update and start your testnet
 (2) start now!        | starts an already installed testnet
 (3) how to?           | shows this file here
 (4) clean             | will clean all and delete the extra folders
 (5) run tests!        | starting lightning test
 (6) exit!             | exit the script

 __**Screen session how to:**__

  Action  | How to
  ------------ | -------------
  enter screen session | screen -r (see above)
  exit screen session | CTRL + a d
  show running sessions | screen -w
  stop all sessions | sh initd-aeternity.sh stop

Warning! Community content! * 17th May 2017 @zwilla
***
Translations: [German Testnet setup start and use]([German]-Testnet-setup-start-and-use)
***
Stay tuned this page will be updated recently. Feel free to add questions to this page!
***

### Questions about the æternity Testnet
add your’s here
1. Hmmm..
2. hmmm …
3. ???

***
Note! This is a pure community content! * updated 17th May 2017 @zwilla
***
Translations: [German Testnet setup start and use]([German]-Testnet-setup-start-and-use)
***
Stay tuned this page will be updated recently. Feel free to add questions to this page!
***

  Donate to .. and support Zwilla:
  * btc: -[1DaGkc1Uv4GeCSpjkrMVzCA35ENmrd526V]
  * eth: -[0x284DbB6139e2e08cd3D3BE6f51306c19cAB04e3c]
  * ltc: -[LNvu63U68G72KXHWP5yqSuSYpoa7ef58c7]
  * æon: -[0x] (æternity Tokens)