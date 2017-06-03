    Never send private keys to anybody asking for them - never send
    contribution transactions to any other address then on
    wallet.aeternity.com

# Sign a Message:

* [WARNINGS](#warnings)
  * [warnings npm](#warnings-npm)
  * [Keeping your Cryptocurrency Safe & Secure](Keeping-your-Cryptocurrency--Safe-%26-Secure)
* [sign with æternity](#æternity-sign-a-message)
* [sign with bitcoin](#sign-a-message-bitcoin)
* [sign with ethereum (mew)](#sign-a-message-ethereum-myetherwallet-mew)


* [Where are my private Keys?](#where-are-my-private-keys)
  * [Ledger Wallet](#ledger-wallet-where-are-my-private-keys)
  * [Treor sign a message](https://doc.satoshilabs.com/trezor-user/messages.html)
[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)


### Use-Case Concepts

There are many ways of signing a message with a private key.

Quite rightfully there are not many websites that allow you to do so -
it would be suicide to trust anyone with your private key.

However, with some precautions you can build a website yourself.


[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)

## Warnings


**Never send private keys to anybody asking for them - never send
contribution transactions to any other address then on
wallet.aeternity.com**
<sup>[A-Team on Slack](https://aeternity.slack.com/archives/C229MJXFE/p1496480397840208)</sup>

### WARNINGS NPM

Installing from npm can be also be dangerous, see links below:

- https://security.stackexchange.com/questions/118547/unpublished-modules-on-npm-could-an-attacker-take-advantage-of-their-former-not/118579
- https://github.com/joaojeronimo/rimrafall
- it's inherit property of any software...
- ...even if it open-source and has well-established reputation you
  never know
- _(not being paranoid, just being aware of security implications)_

> As I mentioned you cannot republish a file of a particular version. By
> setting an exact version in your dependencies, your application will
> only download this version. If an attacker was to gain control of the
> package they could only push malicious code to users of a later
> package.

[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)

## æternity Sign a message

**Will be updated soon with more details** You can take a look here
[API-Commands](API-Commands)

## Sign a Message: Bitcoin

### Browser method - only with a website you fully **trust** and **control**

Why don't you build it yourself? For that reason we will use:

- https://github.com/bitcoinjs/bitcoinjs-lib
- https://github.com/bitcoinjs/bitcoinjs-message

You will need to have `node` and `browserify` installed. Start with
installing `node` and then execute the command `npm install browserify
-g`

We will create a file with the required libraries , let's call it
`dependencies.js`

```
module.exports = {
  base58: require('bs58'),
  bitcoin: require('bitcoinjs-lib'),
  bitcoinMessage: require('bitcoinjs-message'),
  ecurve: require('ecurve'),
  BigInteger: require('bigi')
}
```

We also need to install these libraries locally:

`npm install bs58 bitcoinjs-lib bitcoinjs-message ecurve bigi`

* [read warnings!](#warnings-npm)

From here, we can use `browserify` to make it available in the browser:

`browserify index.js --standalone library > bitcoin.js`

Now let's create a super simple webpage:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Signing message with private key</title>
    <script src="bitcoin.js"></script>
	<script>
		var keyPair = library.bitcoin.ECPair.fromWIF('5KYZdUEo39z3FPrtuX2QbbwGnNP5zTd7yyr2SC1j299sBCnWjss')
		var privateKey = keyPair.d.toBuffer(32)
		var message = 'This is an example of a signed message.'
		var messagePrefix = library.bitcoin.networks.bitcoin.messagePrefix
		 
		var signature = library.bitcoinMessage.sign(message, messagePrefix, privateKey, keyPair.compressed)
		console.log(signature.toString('base64'))
	</script>
  </head>
  <body>
  
  </body>
</html>
```

[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)

### TODO:

- provide user interface for inputting the key
- use https://wzrd.in/ to avoid installing files
- create standalone demo


# Sign a Message: ETHEREUM myetherwallet MEW

**(M)y(e)ther(w)allet** is a trustless open-source application that
allows you to interact with the Ethereum network without running a full
client. You can create and manage wallets without uploading your private
key.

To sign a message perform the following steps:

### MEW ONLINE

- go to https://www.myetherwallet.com/signmsg.html
- click "View wallet info" tab
- choose how you would like to access your wallet and decrypt it locally
- scroll to the section "Sign or verify message" on the bottom of the
  page

or
- OFFLINE: just add signmsg.html behind you local version at the address
  bar of you browser.


***

https://www.myetherwallet.com/signmsg.html

<sup>[signmsg.html](https://github.com/kvhnuke/etherwallet/blob/68abcad30dd5f18d504b9ae7756270c96b39046e/dist/signmsg.html "dist/signmsg.html")</sup>

## Where are my private Keys?

### Ledger wallet: Where are my private keys?

​Your private keys are securely protected inside the Secure element of
your device. This is the purpose of using hardware wallets - you don't
have to display these private keys.

If for some reason you need to see them, there is a tool to get all your
public and private addresses:
https://ledger.groovehq.com/knowledge_base/topics/restoring-your-ethers-eth-or-etc-without-a-ledger-nano-s  
Be aware that displaying your private keys outside the Secure Element
would expose these private data, the security of your funds wouldn't be
guaranteed anymore by the device.

For backup reason you got a 24 keyword list.

    One master node (seed) can be used for unlimited number of independent 
    cryptocoins such as Bitcoin, Ethereum, Litecoin or Namecoin. 
    However, sharing the same space for various cryptocoins has some disadvantages
<sup>[read more](https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki#coin-type)</sup>

<sup>[source link](http://support.ledgerwallet.com/knowledge_base/topics/where-are-my-private-keys),
* [How to secure your ETH tokens with your Ledger Nano S](http://support.ledgerwallet.com/knowledge_base/categories/ledger-nano-s)
* [Restoring your Ethers (ETH or ETC) without a Ledger Nano S](https://ledger.groovehq.com/knowledge_base/topics/restoring-your-ethers-eth-or-etc-without-a-ledger-nano-s)
* [Ledger Security](https://ledger.groovehq.com/knowledge_base/categories/security-14)
***

**Was this article helpful?**
[Yes](#)/[No, I want to contact community support](Contacts-and-Communities)


[![](https://cdn-images-1.medium.com/max/800/1*Fh8Te8hkihkvLufP05tKPQ.png)](#)
