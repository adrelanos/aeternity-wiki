#### IMPORTANT NOTEs

    Only send contributions from Ether addresses of which you have the private keys.
    If in doubt, please generate a new wallet using this contribution wallet.
    **Do NOT send directly from exchanges** , like Coinbase, Bistamp or ShapeShift,
    mixers, or any other 3rd party service that does not provide you access to private keys.
    Contributions from hardware, desktop, mobile & paper wallets of which you have the
    private keys and/or seed are acceptable. Make sure that you are sending to the correct
    Ether address of æternity's contribution campaign. Funds sent to any other address will
    not be exchanged for AE tokens and will not be returned to you.

* [Security Concerns on Contributing to æternity?](#security-concerns-on-contributing-to-æternity)
* [short version](#short-version)
  * [Contribute now to æternity](https://wallet.aeternity.com)
    * [How to contribute ether?](https://blog.aeternity.com/how-to-send-ether-to-%C3%A6ternitys-contribution-campaign-wallet-e11ef89b847e)
    * [How to contribute bitcoin?](https://blog.aeternity.com/how-to-send-bitcoin-to-%C3%A6ternitys-contribution-campaign-wallet-65d3f46aa4b9)
* [light version](#light-version)
* [paranoid version](#paranoid-version)
  * [Mnemonic Code Converter](#mnemonic-code-converter)
  * [Supply my own source of entropy]()
  * [Why to choose a 24 Word BIP39 Mnemonic?](#why-to-choose-a-24-word-bip39-mnemonic)
  * [Storage medium](#storage-medium)
* [**Verify if new the address is a valid one!**](#verify-if-new-the-address-is-a-valid-one)
* [**Additional WARNINGS**](#additional-warnings)

**Never send private keys to anybody asking for them - never send
contribution transactions to any other address then on
wallet.aeternity.com**

[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)

## Security Concerns on Contributing to æternity?

There exist an easy way to bypass your security concerns, this solution
are also often chosen from investors which own only a online wallet at
Coinbase, Bistamp aso.

***

## Short Version

### [Contribute now to æternity](https://wallet.aeternity.com/)

<sup>click on the headline</sup>

#### [How to contribute ether?](https://blog.aeternity.com/how-to-send-ether-to-%C3%A6ternitys-contribution-campaign-wallet-e11ef89b847e)

<sup>click on the headline</sup>

#### [How to contribute bitcoin?](https://blog.aeternity.com/how-to-send-bitcoin-to-%C3%A6ternitys-contribution-campaign-wallet-65d3f46aa4b9)

<sup>click on the headline</sup>

[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)

### light Version!

1. download this: https://github.com/LedgerHQ/bip39/archive/master.zip
2. use an offline computer
3. extract the zip, open bip39-standalone.html
4. **choose COIN: ETHEREUM**
5. **choose Generate: 24 Word**
   <sup>[read why?](#why-to-choose-a-24-word-bip39-mnemonic)</sup>
6. **choose Mnemonic Language: english**
7. click multiple times on **generate*
8. **write down** the 24 words on a paper
9. at Derived Addresses: write down the **first Ethereum address**
10. [goto section: verify the new addres](#verify-if-new-the-address-is-a-valid-one)
11. transfer your coins to the new address
12. [contribute now on æternity!](https://wallet.aeternity.com/)


[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)

## paranoid version

### Mnemonic Code Converter

*DO NOT USE A ONLINE VERSION ! This instructions are for strong safety
!*
1. Download https://github.com/LedgerHQ/bip39/archive/master.zip
2. review the code
3. put this file on an usb stick, sd-card, burn it to on
   cd/dvd/(finalize session) what ever you want
4. choose an offline computer (I prefer a raspi run from sd-card - never
   connected to the web or local network)
5. unzip this software
6. open 'bip39-standalone.html'
7. **check the box: 'Supply my own source of entropy'**
8. **select a 24 Word BIP39 Mnemonic!**
   <sup>[read why?](#why-to-choose-a-24-word-bip39-mnemonic)</sup>
9. **click english!**
   <sup>[read why?](#why-to-choose-a-24-word-bip39-mnemonic)</sup>
10. **choose COIN: ETHEREUM**
11. open a picture YOU made >1MB with an text editor
12. copy the hole text (CTRL-A)
13. come back to: 'bip39-standalone.html'
14. past (CRTL-V)the text into 'Entropy BOX'
15. Drink a cup of coffee or a beer, it your choice now. (my security
    concerns: don't drink and send money )!
16. write down the *24 words* on a paper with an pen .
    <sup>[* for documentary use](http://www.iso.org/iso/en/CatalogueDetailPage.CatalogueDetail?CSNUMBER=23720&ICS1=1&ICS2=100&ICS3=40)</sup>
17. Save your wallet datas,
18. power off your computer and wipe the hard disk
    <sup>[*](#storage-medium)</sup> at minimum 7 times
19. [contribute now on æternity!](https://wallet.aeternity.com/)
20. [goto section: verify the new addres](#verify-if-new-the-address-is-a-valid-one)
21. transfer your coins to the new address
22. [contribute now on æternity!](https://wallet.aeternity.com/)

#### Supply my own source of entropy

Check this box to use your own entropy. For example:
1. make a picture with you cam,
2. save it as compressed jpeg +- 1MB and
3. open it with an text editor of your choice
4. open 'bip39-standalone.html'
5. NOW !! Change Mnemonic Length to 24 WORDS
6. copy the text and past it in to the box: **Entropy**


[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)

### Why to choose a 24 Word BIP39 Mnemonic?

Later you can use this 24 words to setup a new Ledgerwallet or the
hardware wallet Trezor
* [How to import / recover a backup on a Nano S?](http://support.ledgerwallet.com/knowledge_base/topics/how-to-import-slash-recover-a-backup-on-a-nano-s)
* [Trezor Advanced Recovery process](http://doc.satoshilabs.com/trezor-user/advancedrecovery.html?highlight=recovery)

***

### Storage medium

| medium                     | bevore      | after                |
|:---------------------------|:------------|:---------------------|
| usb stick                  | format      | wipe minimum 7 times |
| sd-card                    | format      | wipe minimum 7 times |
| cd/dvd (finalize session!) | buy         | reuse it             |
| hdd (ssd, flash, magnetic) | do not use! | do not use!          |

## Verify if new the address is a valid one!

To verify the new Ethereum address we use OFFLINE - the software
(**M**)y(**E**)ther(**W**)allet (MEW), if you need help you can get it
here:
* https://myetherwallet.groovehq.com/help_center
* https://www.myetherwallet.com/#help
* or via mail: support@myetherwallet.com


1. Download MyEtherWallet:
   https://github.com/kvhnuke/etherwallet/releases/latest <sup>(we need
   the **dist-vx.x.x.zip** file!)</sup>
2. transfer it to you offline computer
3. unzip the downloaded file
4. open index.html
5. click on menu *View Wallet Info*
6. on 'How would you like to access your wallet?' choose: *Mnemonic
   Phrase*
7. type in there your *24 words* <sup>no password!</sup>
8. click *Unlock your Wallet*
9. write down the fist address 'Your Address'
10. compare it with the first address on BIP39-Tool

Bingo Bongo: Now you have successfully verified that the address will
match. Transfer now your coins from your exchange or where ever you have
some, to the new address you generated.


| no | what          | Title                                 | Link                                                           |
|:---|:--------------|:--------------------------------------|:---------------------------------------------------------------|
| 1  | software      | (**M**)y(**E**)ther(**W**)allet (MEW) | [link](https://github.com/kvhnuke/etherwallet/releases/latest) |
| 2  | software      | BIP39/44 Mnemonic Code Converter      | [link](https://github.com/LedgerHQ/bip39/archive/master.zip)   |
| 3  | Ledger-Wallet | Ledger Nano s - hardware wallet       | [link](https://www.ledgerwallet.com/r/07c5)                    |
| 4  | Trezor-Wallet | Trezor - hardware wallet              | [link](https://trezor.io/?a=bitcoins-today.com)                |
| 5  | inspiration   | æternity wallet                       | [link]((https://wallet.aeternity.com/)                         |
| 6  | Brainwallet   | Zwilla's Brainwallet                  | [author profile](æternity-wiki-authors#zwilla)                                                               |

## Additional WARNINGS

THIS INSTRUCTIONS ARE PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THIS INSTRUCTIONS OR THE USE OR OTHER
DEALINGS IN THE INSTRUCTIONS.

DO NOT SHARE YOUR PRIVATE KEYS!!!
