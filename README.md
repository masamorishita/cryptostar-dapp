# Cryptostar Dapp on Ethereum
A simple CryptoStar Dapp running on Rinkeby Ethereum Testnet.

The name of the token is `Masa Token` and the symbol is `MAS`.
The token address on the Rinkeby Network is `0x3a28638FEd7689bb71744dB4d067B2f7c7A660Ea`.

## Prerequisite
You need to install `truffle-hdwallet-provider` and `openzeppelin-solidity`. You can install them by running the following commands:
```
$ npm install --save truffle-hdwallet-provider
```
```
$ npm install --save openzeppelin-solidity
```
You will also need to have the latest version of Truffle (V5...) and the latest version of Metamask Chrome extension installed.

This code is tested on `Truffle v5.0.21` and `OpenZeppelin v2.1.2`.

## Deploy the contract on Rinkeby Ethereum Testnet.
When you deploy the contract on Rinkeby Ethereum Testnet, you need to modify `truffle-config.js` file by using your Metamask’s seed and Infura setup.

The code of `truffle-config.js` should look something as follows:
```
const HDWalletProvider = require('truffle-hdwallet-provider');
const infuraKey = "<Infura PROJECT ID>";
//
// const fs = require('fs');
const mnemonic = "<METAMASK SEED>";

module.exports = {

  networks: {
    development: {
      host: "127.0.0.1",     // Localhost (default: none)
      port: 9545,            // Standard Ethereum port (default: none)
      network_id: "*",       // Any network (default: none)
     },
    // Useful for deploying to a public network.
    // NB: It's important to wrap the provider as a function.
    rinkeby: {
      provider: () => new HDWalletProvider(mnemonic, `https://rinkeby.infura.io/v3/${infuraKey}`),
        network_id: 4,       // rinkeby's id
        gas: 4500000,        // rinkeby has a lower block limit than mainnet
        gasPrice: 10000000000
    },
  },

  // Set default mocha options here, use special reporters etc.
  mocha: {
    // timeout: 100000
  },

  // Configure your compilers
  compilers: {
    solc: {
      // version: "0.5.1",    // Fetch exact version from solc-bin (default: truffle's version)
      // docker: true,        // Use "0.5.1" you've installed locally with docker (default: false)
      // settings: {          // See the solidity docs for advice about optimization and evmVersion
      //  optimizer: {
      //    enabled: false,
      //    runs: 200
      //  },
      //  evmVersion: "byzantium"
      // }
    }
  }
}
```

Onece you set up, you can deploy the code by running the following command:
```
$ truffle migrate --reset --network rinkeby
```
