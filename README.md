# CoinAlpha Fund Protocol

A blockchain protocol for tokenized hedge funds.

This open-source protocol enables asset managers to create a blockchain-based vehicle that manages capital contributed by external investors. The protocol utilizes the blockchain to perform functions such as segregated asset custody, net asset value calculation, fee accounting, and management of investor in-flows and out-flows.  The goal of this project is to eliminate the setup and operational costs imposed by middlemen in traditional funds, while maximizing transparency and liquidity for investors.  

For more information about the project, please see the our [wiki](https://github.com/CoinAlpha/fund-protocol/wiki).

## Installation

### Geth
Ethereum client for testnet and live
```
brew tap ethereum/ethereum
brew install ethereum
```

### TestRPC
Ethereum client for local testing
```
npm install -g ethereumjs-testrpc
```

### Truffle
Deployment and testing framework.  Use v3.4.7 which ships with solc v0.4.13.
```
npm install -g truffle@3.4.7
```


### Libraries and dependencies
```
npm install
```
## Testing

### Local
1. Run TestRPC with a 1 second block time, to allow for simulation of time-based fees: `testrpc -b 1` 
2. In another Terminal window, `truffle console`
3. `truffle test` to run all tests

### Tesnet
1. Run `geth --testnet --rpc --rpcapi eth,net,web3,personal`
2. In another Terminal window, `truffle console`
3. `web3.eth.accounts` and check that you have at least 4 accounts.  Each account should have more than 5 test eth.
4. Unlock your primary account: `web3.personal.unlockAccount(web3.eth.accounts[0], <INSERT YOUR PASSWORD HERE>, 15000)`
5. Follow manual testing workflows in `js/Fund-test.js`
