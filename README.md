# AirdropClaim
Airdrop Claim Smart Contract for LOWB

### Compiling and running the code
- Before running this project, install truffle first: `npm install -g truffle`.

- Compile the smart contracts: `truffle compile`.

- Deploy to local network: `truffle migrate`. (You may need to start [Ganache](https://www.trufflesuite.com/ganache) before migrating.)

- Now you can start to play with this contract: `truffle console`. For example, you can set up the white list by:

  ```javascript
  truffle(development)> let instance = await AirdropClaim.deployed()
  truffle(development)> let accounts = await web3.eth.getAccounts()
  truffle(development)> instance.setupWhitelist(accounts, [10,20,30,40,50,60,70,80,90,100])
  ```
### Depolying to the live network

- Create a new .secret file in root directory and enter your 12 word mnemonic seed phrase. Then just run `truffle migrate --network testnet`. You will deploy contracts to the Binance testnet. (You may need to install hdwallet-provider first: `npm install @truffle/hdwallet-provider@1.2.2`.)
- To verify the contract, create a new .apikey file in root directory and enter the [API Key](https://bscscan.com/myapikey). Then just run `truffle run verify GameItem@{contract-address} --network testnet`. (You may need to install truffle-plugin-verify first: `npm install -D truffle-plugin-verify`.)