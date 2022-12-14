# Sandbox project: Hardhat

A playground project used to discover new techniques, tools or just to try things out.

## Techstack

- [Solidity](https://solidity.readthedocs.io/en/v0.5.3/)
- [ethers.js](https://docs.ethers.io/ethers.js/html/)
- [TypeScript](https://www.typescriptlang.org/)
- [Prettier](https://prettier.io/)
- [dotenv](https://github.com/motdotla/dotenv)
- [Hardhat](https://hardhat.io/)
- [Mocha](https://mochajs.org/)
- [hardhat-gas-reporter](https://www.npmjs.com/package/hardhat-gas-reporter)
- [Solidity Coverage](https://github.com/sc-forks/solidity-coverage)
- [Typechain](https://github.com/dethcrypto/TypeChain)
- [Chainlink](https://chain.link/)
- [hardhat-deploy](https://github.com/wighawag/hardhat-deploy)


## Automatic verification
The hardhat-etherscan plugin is used to verify the deployed contract programmatically and automatically, make sure the Etherscan API key is set in the `.env` file. Verification will only be performed if the `ETHERSCAN_API_KEY` environment variable is true and `chainId` is 5 (a.k.a. chainId of Goerli test network). 

## Deploying
At the moment there are two ways to deploy smart contracts. Using `hardhat-deploy` is prefered. 

### Using the local `utils/deploy.ts` script.
`npm run deploy` to deploy on default and temporary hardhat blockchain. To deploy on the goerli test network you can run `npm run deploy-goerli`. The `utils/deploy.ts` script will automatically deploy the contract to the specified network.

### Using the `hardhat-deploy` plugin.
`npm run hardhat-deploy` will use the `hardhat-deploy` plugin to deploy the contract to the default and temporary hardhat blockchain. run `npm run hardhat-deploy-goerli` to deploy to the goerli test network.

## Local environment file should have the following variables:
- `GOERLI_RPC_URL` and `PRIVATE_KEY` are used to connect to the Goerli test network.
- `PRIVATE_KEY` is used to sign transactions.
- `ETHERSCAN_API_KEY` is used to verify the deployed contract.
- `COINMARKETCAP_API_KEY` is used to see current gas prices in specified currency inside gas report.


## Notes
- While deploying to the default and temporary hardhat blockchain, the pricefeed will be served by a mock. This is because there is no pricefeed available for a local test network.