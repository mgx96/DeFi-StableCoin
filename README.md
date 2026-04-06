# DeFi StableCoin

## Overview

DeFi StableCoin is a decentralized, overcollateralized stablecoin protocol built with Solidity and Foundry. The system allows users to deposit approved collateral assets and mint a USD-pegged stablecoin while maintaining protocol solvency through enforced collateralization ratios.

The architecture is modular and designed to be extensible, allowing new collateral types to be integrated with minimal changes to core logic.

## Key Features

- Overcollateralized stablecoin model  
- USD-pegged token with minting and burning mechanisms  
- Support for multiple collateral assets  
- Deterministic health factor and liquidation logic  
- Oracle-based price feeds  
- Fuzz testing and invariant testing support  
- Built using Foundry for fast and efficient development  

## Architecture

The protocol is composed of three main components:

### 1. Stablecoin Contract

Implements the ERC20 token representing the stablecoin. Handles minting and burning, restricted to the engine contract.

### 2. Engine (Core Logic)

Manages:
- Collateral deposits and withdrawals  
- Stablecoin minting and burning  
- Health factor calculations  
- Liquidations  

### 3. Oracle Library

Provides price feed integration used to determine collateral value and enforce system safety.

## How It Works

1. Users deposit supported collateral (e.g. ETH, BTC derivatives)  
2. The protocol calculates the USD value using price oracles  
3. Users can mint stablecoins based on a safe collateralization ratio  
4. If a position becomes undercollateralized, it can be liquidated  

This ensures that every unit of stablecoin remains backed by sufficient collateral.

## Getting Started

### Prerequisites

- Git  
- Foundry  

    git clone https://github.com/mgx96/DeFi-StableCoin
    cd DeFi-StableCoin
    forge build

## Usage

### Run Local Node

    make anvil

### Deploy Contracts

    make deploy

### Run Tests

    forge test

### Test Coverage

    forge coverage

## Testing Strategy

The project includes:

- Unit tests for core logic  
- Fuzz testing for edge cases  
- Invariant-style testing for protocol safety  

This ensures robustness against unexpected inputs and economic edge cases.

## Security Considerations

- Overcollateralization is enforced at all times  
- Liquidation mechanisms protect protocol solvency  
- Oracle dependency introduces external risk  
- Insolvency scenarios are not recoverable by design  

This project is intended for educational and research purposes and has not been audited.

## Future Improvements

- Additional collateral types  
- Improved liquidation incentives  
- Governance mechanisms  
- Frontend interface  
- Mainnet deployment scripts  

## License

MIT License
