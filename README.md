# Welcome to DeFi StableCoin - Decentralized Stablecoin Protocol

## Overview
 - Welcome to our decentralized stablecoin project! Our primary goal is to achieve relative stability by pegging our stablecoin to $1.00. Here's a brief overview of the key components and features:

1. Relative Stability (Pegged to $1.00)

- Leveraging the Chainlink Price feed for accurate real-time market data.
- Implementation of a flexible function allowing users to seamlessly exchange ETH and BTC within our ecosystem.

2. Stability Mechanism (Algorithmic Minting)

- Users can mint the stablecoin exclusively with sufficient collateral, as per our decentralized algorithm.

3. Collateral (Exogenous Crypto)

- Backed by widely recognized cryptocurrencies, wETH and wBTC.

4. Enhanced Functionality

- Calculation of the health factor function.
- Dynamic health factor adjustment when debt is zero.
- Addition of various view functions for increased transparency.


## Project Roadmap
1. Invariants/Properties

- Defining core principles that guide our system.

2. Oracle Integration

- Ensuring proper use of oracles for reliable external data.

3. Test Coverage

- Expanding test coverage to validate system integrity.

4. Smart Contract Audit Preparation

- Meticulous preparation for a smart contract audit to enhance system security.


# Getting Started

## Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`
- [foundry](https://getfoundry.sh/)
  - You'll know you did it right if you can run `forge --version` and you see a response like `forge 0.2.0 (816e00b 2023-03-16T00:05:26.396218Z)`

## Quickstart

```
git clone https://github.com/Dav1dStefanow/foundry-defi-stablecoin-f23
cd foundry-defi-stablecoin-f23
forge build
```

### Deploy

```shell
$ forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

## Scripts

Instead of scripts, we can directly use the `cast` command to interact with the contract.

For example, on Sepolia:

1. Get some WETH

```
cast send 0xdd13E55209Fd76AfE204dBda4007C227904f0a81 "deposit()" --value 0.1ether --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY
```

2. Approve the WETH

```
cast send 0xdd13E55209Fd76AfE204dBda4007C227904f0a81 "approve(address,uint256)" 0x091EA0838eBD5b7ddA2F2A641B068d6D59639b98 1000000000000000000 --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY
```

3. Deposit and Mint DSC

```
cast send 0x091EA0838eBD5b7ddA2F2A641B068d6D59639b98 "depositCollateralAndMintDsc(address,uint256,uint256)" 0xdd13E55209Fd76AfE204dBda4007C227904f0a81 100000000000000000 10000000000000000 --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY
```

## Estimate gas

You can estimate how much gas things cost by running:

```
forge snapshot
```

And you'll see an output file called `.gas-snapshot`

# Formatting

To run code formatting:

```
forge fmt
```

# Slither

```
slither :; slither . --config-file slither.config.json
```

# Push To GitHub

1. Save changes

```
git add .
```

2. See all changes

```
git status
```

3. Log in your GitHub Profile

```
git log
```

4. Commit changes

```
git commit -m 'Initial Create'
```

5. Choose a project to push your protocol

```
git remote add origin https://github.com/Dav1dStefanow/foundry-stable-coin-f23.git
```

6. Push command

```
git push -u origin master/main
```
