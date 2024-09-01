## Combine .env and forge keystore

#### To create the keystore

```shell
cast wallet import testkey --interactive
```

#### To use the keystore

```shell
forge script script/DeploySimpleStorage.s.sol --rpc-url $RPC_URL --broadcast --account testkey --sender $TEST_SENDER --password $TEST_PASSWORD
```

So, your .env file should have RPC_URL, TEST_SENDER and TEST_PASSWORD.

## Interactive with contract

```shell
cast send 0xa513E6E4b8f2a923D98304ec87F64353C4D5C853 "store(uint256)" 42 --account testkey --password $TEST_PASSWORD
```

```shell
cast call <contract address> "retrieve()"
```

```shell
cast --to-base <hex stored number> dec
```

## Deploy on Sepolia Testnet by foundry

```shell
forge script script/DeploySimpleStorage.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast
```

SimpleStorage.sol

```shell
0x3Fa916A053787212B0Df37b92A0cd7f198e92B01
```

## foundry-zksync

```shell
foundryup-zksync
```

```shell
forge compile --zk-compile
```

### Deploy on Local Zksync Node by foundry-zksync

```shell
npx zksync-cli dev config
```

```shell
npx zksync-cli dev start
```

```shell
forge create src/SimpleStorage.sol:SimpleStorage --rpc-url http://127.0.0.1:8011 --private-key 0x7726827caac94a7f9e1b160f7ea819f172f7b6f9d2a97f992c38edeab82d4110 --legacy --zksync
```

```shell
forge script script/DeploySimpleStorage.s.sol:DeploySimpleStorage --rpc-url http://127.0.0.1:8011 --private-key 0x7726827caac94a7f9e1b160f7ea819f172f7b6f9d2a97f992c38edeab82d4110 --legacy --broadcast --zksync
```

## Foundry

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

- **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
- **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
- **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
- **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Usage

### Build

```shell
$ forge build
```

### Test

```shell
$ forge test
```

### Format

```shell
$ forge fmt
```

### Gas Snapshots

```shell
$ forge snapshot
```

### Anvil

```shell
$ anvil
```

### Deploy

```shell
$ forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

### Cast

```shell
$ cast <subcommand>
```

### Help

```shell
$ forge --help
$ anvil --help
$ cast --help
```
