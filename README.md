# TruffleDeploy

* **[Pre-requisites](#pre-requisites)**
* **[Setup](#setup)**
* **[Run](#run)**

## Getting Started

These instructions will allow you to deploy a smart contract with truffle.



## Pre-requisites
* Install truffle
```sh
npm install -g truffle
```

* Launch a blockchain with geth or ganache where we can deploy the smart contract.
To launch the blockchain with geth <https://github.com/AndreaMattone/EthereumPoABlockchain>
To launch the blockchain with ganache
via shell:
```sh
npm install -g ganache-cli
```
via Ganache Suite 
<https://www.trufflesuite.com/ganache>


## Setup

###  1]  Enviroment
* Launch the blockchain

Create a directory where we are can deploy our smart contract and initialize truffle
```sh
$> mkdir myEthDapp
$> cd myEthDapp
myEthDapp$> truffle init
```
Now we have the initialized folder.

Let's now modify truffle-config.js
```sh
$> mkdir myEthDapp
$> cd myEthDapp
myEthDapp$> truffle init
```
module.exports = {
networks: {
    development: {
      host: "127.0.0.1",
      port: 8545,
      network_id: "*" // Match any network id
    }
  }
};









