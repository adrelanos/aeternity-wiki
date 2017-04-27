There are many ways of signing a message with a private key.

Quite rightfully there are not many websites allowing you to do so - that would be a suicide to trust anyone with your private key.

However, with some precautions you can build a website yourself.

# Browser method - only website you fully **trust** and **control**

Why don't you build it yourself? For that reason we will use:

- https://github.com/bitcoinjs/bitcoinjs-lib
- https://github.com/bitcoinjs/bitcoinjs-message

You'll need to have `node` and `browserify` installed. Start with installing `node` and then `npm install browserify -g`

We will create a file with required libraries, let's call it `dependencies.js`

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

From here we can use `browserify` to make it available in the browser:

`browserify index.js --standalone library > bitcoin.js`

Now let's create super simple webpage:
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




