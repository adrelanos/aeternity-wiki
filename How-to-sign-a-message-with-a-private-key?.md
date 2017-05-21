There are many ways of signing a message with a private key.

Quite rightfully there are not many websites that allow you to do so - it would be suicide to trust anyone with your private key.

However, with some precautions you can build a website yourself.

# Browser method - only with a website you fully **trust** and **control**

Why don't you build it yourself? For that reason we will use:

- https://github.com/bitcoinjs/bitcoinjs-lib
- https://github.com/bitcoinjs/bitcoinjs-message

You will need to have `node` and `browserify` installed. Start with installing `node` and then execute the command `npm install browserify -g`

We will create a file with the required libraries , let's call it `dependencies.js`

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

---

**WARNING:** Installing from npm can be also be dangerous, see links below:

- https://security.stackexchange.com/questions/118547/unpublished-modules-on-npm-could-an-attacker-take-advantage-of-their-former-not/118579
- https://github.com/joaojeronimo/rimrafall
- it's inherit property of any software...
- ...even if it open-source and has well-established reputation you never know
- _(not being paranoid, just being aware of security implications)_

>  As I mentioned you cannot republish a file of  a particular version. By setting an exact version in your dependencies, your application will only download this version. If an attacker was to gain control of the package they could only push malicious code to users of a later package.

---

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

## TODO:

- provide user interface for inputting the key
- use https://wzrd.in/ to avoid installing files
- create standalone demo


# Alternative: myetherwallet

Myetherwallet is a trustless open-source application that allows you to interact with the Ethereum network without running a full client. You can create and manage wallets without uploading your private key.

To sign a message perform the following steps:

- go to https://www.myetherwallet.com/
- click "View wallet info" tab
- choose how you would like to access your wallet and decrypt it locally
- scroll to the section "Sign or verify message" on the bottom of the page
- enter your message and optionally enter a date before clicking the "Sign message" button

