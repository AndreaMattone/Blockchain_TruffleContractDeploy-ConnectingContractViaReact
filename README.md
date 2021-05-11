# TruffleDeploy

* **[Pre-requisites](#pre-requisites)**
* **[Setup](#setup)**
* **[Deploying](#deploying)**

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

Let's now modify truffle-config.js using our blockchain data
```sh
module.exports = {
networks: {
    development: {
      host: "127.0.0.1",
      port: 8501,
      network_id: "*" // Match any network id
    }
  }
};
```


##Deploying
###  2]  Insert contracts
In ./contracts we can insert our "myContract.sol", for example
```sh
pragma solidity >=0.4.22 <0.8.0;
contract myContract {
    
    ...
```

Now we open ./migrations/2_deploy_contracts.js (if doesnt exist let's create it).
And we add a dependency for every contract that we want to deploy.
```sh
const myContract = artifacts.require("./myContract.sol");

module.exports = function(deployer) {
  deployer.deploy(myContract);
};

```


### Compiling and Deploying
```sh
$>truffle compile
$>truffle migrate --network development
$>truffle migrate
```



