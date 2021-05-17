# MIP10c3-SP4: Subproposal to Onboard Oracle

## Preamble
```
MIP10c3-SP#: 4
Author(s): Niklas Kunkel (@NiklasKunkel)
Contributors:
Type: Process Component
Tags: oracle-onboarding, oracles
Oracle Team Name: Green
Status: Withdrawn
Date Proposed: 2020-07-08
Date Ratified: n/a
```
## Sentence Summary
MIP10c3-SP4 onboards the LEND/USD Oracle.

## Specification

### Introduction

This Oracle would provide the LEND/USD price as part of the collateral onboarding process for LEND.

### Oracle Data Model 

    |     Source    |  Asset Pair  |Quorum | Feed Model  | Oracle Model |
    | :------------ | :----------- | :---: | :---------: | :----------: |
    |    Binance    |   LEND/BTC   |   13  |    Median   |    Median    |
    |     Huobi     |   LEND/USDT  |
    | Kyber Network |   LEND/ETH   |
    |      OKEx     |   LEND/USDT  |
    |    Uniswap    |   LEND/ETH   |


### Oracle Supporting Data Model(s)

**USDT/USD (canonical)**

    |    Source     |  Asset Pair   |  Feed Model  |
    | :------------ | :------------ | :----------: | 
    |   Binance     |    BTC/USDT   |    Median    |
    |   BitFinex    |    USDT/USD   |              |
    |   Huobi       |    ETH/USDT   |              |
    |   Kraken      |    USDT/USD   |              |
    |   OKEx        |    BTC/USDT   |              |

**ETH/USD (canonical)**

    |    Source     |  Asset Pair   |  Feed Model  |
    | :------------ | :------------ | :----------: | 
    |   Binance     |    ETH/USD    |    Median    |
    |   Bitfinex    |    ETH/USDT   |              |
    |   Bitstamp    |    ETH/USD    |              |
    |   Coinbase    |    ETH/USD    |              |
    |   Gemini      |    ETH/USD    |              |
    |   Kraken      |    ETH/USD    |              |

**BTC/USD (canonical)**

    |    Source     |  Asset Pair   |  Feed Model  |
    | :------------ | :------------ | :----------: | 
    |   Bitstamp    |    BTC/USD    |    Median    |
    |   Bittrex     |    BTC/USD    |              |
    |   Coinbase    |    BTC/USD    |              |
    |   Gemini      |    BTC/USD    |              |
    |   Kraken      |    BTC/USD    |              |


 
### Oracle Address
- Medianizer - n/a
- Oracle Security Module (OSM) - n/a
    
### Supported Tools
- Setzer - 77876f0b94a00880534e5076e6b9c15f2ca260cf - [Added support for MANA/USD](https://github.com/makerdao/setzer-mcd/commit/77876f0b94a00880534e5076e6b9c15f2ca260cf)
- Omnia - 11406ae80bd0297c28e136282ac90f54cc1801d3 - [Added support for MANA/USD](https://github.com/makerdao/oracles-v2/commit/11406ae80bd0297c28e136282ac90f54cc1801d3)
- MANA/USD Medianizer on Kovan Testnet - [0x40828a42ebaae02a2dc774077fb286702bc4d2f7](https://kovan.etherscan.io/address/0x40828a42ebaae02a2dc774077fb286702bc4d2f7)

### Remaining Work

- Deploy and configure Medianizer and Oracle Security Module smart contracts to Mainnet
- Coordinate Feeds to upgrade to latest release candidate
- Push new relayer configuration with LEND/USD Medianizer smart contract address


### Summary

In light of recent exchange listings, the Oracle Team has reviewed the liquidity profile of the LEND token again. I consideration of the wider array of sources included in the Data Model, the previous Oracle manipulation has reduced considerably. The Oracle Team is withdrawing its previous recommendation that the debt ceiling be artificially limited to account for elevated Oracle risk.

The Oracle Team will continue to monitor the development of new exchange sources for LEND and evolution of liquidity profiling for existing sources. Ideally LEND would accrue a couple fiat based pairs on an exchange like Coinbase or Kraken with significant volume.