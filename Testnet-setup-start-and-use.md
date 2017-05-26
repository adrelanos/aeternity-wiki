Table of content / Testnet setup start and use
==============================================

* [Testnet setup start and use](#testnet-setup-start-and-use)
* [How To handle the initd-aeternity script?](#how-to-handle-the-initd-aeternity-script)
* [How it works!](#how-it-works)
* [initd-aeternity script menu](#initd-aeternity-script-menu)
* [Screen session how to!](#screen-session-how-to)
* [Mining on æternity testnet (details)](#mining-on-æternity-testnet-details)
* [Questions about the æternity Testnet](#questions-about-the-æternity-testnet)
* [Translations](#translations)

***

# Testnet setup start and use

I had issues to setup up and use the æternity testnet so I modified the
original 'setup_test.sh' script from Zack
[origin script](../../../../aeternity/testnet/blob/master/setup_test.sh)

This work results to create this new script
[initd-aeternity.sh](../../../../Zwilla/aeternity-testnet/blob/master/initd-aeternity.sh)

[⇪](#table-of-content--testnet-setup-start-and-use)
## How To handle the initd-aeternity script?

| How to?                    | COMMAND                      |
|:---------------------------|:-----------------------------|
| Starting Testnet           | `sh setup_test.sh`           |
| Stop Testnet               | `sh initd-aeternity.sh stop` |
| Access screen session 3010 | `screen -r aeternity-3010`   |
| Access screen session 3020 | `screen -r aeternity-3020`   |
| Access screen session 3030 | `screen -r aeternity-3030`   |

(table 1)

[⇪](#table-of-content--testnet-setup-start-and-use)
***

## How it works!

The script '
[setup_test.sh](https://github.com/Zwilla/aeternity-testnet/blob/master/setup_test.sh)
' will copy 3 times the testnet-folder into this main folders:

- aeternity-testnet3010
- aeternity-testnet3020
- aeternity-testnet3030

**(WARNING! DO NOT RUN SCRIPTS FROM ..3010/20/30 folders)**

* Then it will compile and clean the testnet.app and
* starts a screen session for every NODE!

You can access every screens session.
* Node 3010 starts as mining node
* Node 3020 and 3030 as full node

To make some tests run this script:
[lightning_test.sh](https://github.com/Zwilla/aeternity-testnet/blob/master/tests/lightning_test.sh)


You find this file here:
https://github.com/Zwilla/aeternity-testnet/blob/master/docs/testnet.md

[⇪](#table-of-content--testnet-setup-start-and-use)
## initd-aeternity script menu
After running the test_setup script you can choose now:

| Choose                | COMMAND                                     |
|:----------------------|:--------------------------------------------|
| (1) update and setup! | will setup update and start your testnet    |
| (2) start now!        | starts an already installed testnet         |
| (3) how to?           | shows this file here                        |
| (4) clean             | will clean all and delete the extra folders |
| (5) run tests!        | starting lightning test                     |
| (6) exit!             | exit the script                             |

(table 2)

## Screen session how to!:

| Action                | How to                     |
|:----------------------|:---------------------------|
| enter screen session  | screen -r (see above)      |
| exit screen session   | CTRL + a d                 |
| show running sessions | screen -w                  |
| stop all sessions     | sh initd-aeternity.sh stop |

(table 3)

Warning! Community content! * 17th May 2017 @zwilla

[⇪](#table-of-content--testnet-setup-start-and-use)
***

## Mining on æternity testnet (details)

1. open your terminal client
2. enter the screen session for node 3010: 'screen -r aeternity-3010'
3. now you logged into your node 3010 you got this: '>1 '
4. enter this command: '*keys:new("YOUR_PSSWRD").*' (default password
   is: "abc")
5. unlock your node for mining on æternity testnet:
   '*keys:unlock("YOUR_PSSWRD").*'
6. start the æternity mining: '*mine:start().*'

Some æternity CLI commands which are usefull now:

| CLI Command         | Action                            | tested |
|:--------------------|:----------------------------------|:-------|
| '*easy:balance().*' | shows the balance of your account | [x]    |
| '*mine:stop().*'    | stops the mining                  | [x]    |
| '*mine:is_on().*'   | checks if mining is on            | [x]    |
| '*easy:off().*'     | shut down the hole node           | [x]    |
|                     |                                   | [ ]    |
|                     |                                   | [x]    |

[ x ] = tested and working / [  ] = not tested or not working at moment.

(table 4)

[⇪](#table-of-content--testnet-setup-start-and-use)
***

* more about commands you find here:
  [Terminal Interface Commands](Terminal-interface-commands)
* detail about [Transaction-Types](Transaction-Types)

* [source](https://blog.aeternity.com/%C3%A6ternity-testnet-install-and-mining-6f5b8e880ab1)

## Questions about the æternity Testnet

add your’s here
1. Hmmm..
2. hmmm …
3. ???

[⇪](#table-of-content--testnet-setup-start-and-use)
***

Note! This is a pure community content! * updated 17th May 2017 @zwilla

***

## Translations:
[German Testnet setup start and use]([German]-Testnet-setup-start-and-use)

[⇪](#table-of-content--testnet-setup-start-and-use)
***

Stay tuned this page will be updated recently. Feel free to add
questions to this page!

***
[⇪](#table-of-content--testnet-setup-start-and-use)

