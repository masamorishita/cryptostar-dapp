# Cryptostar Dapp on Ethereum
A simple CryptoStar Dapp running Rinkeby Ethereum Testnet.

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

Onece you set up, you can deploy the code by running the following command:
```
$ truffle migrate --reset --network rinkeby
```
