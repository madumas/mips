# MIP10c3-SP3: Subproposal to Onboard Oracle

## Preamble
```
MIP10c3-SP#: 3
Author(s): Niklas Kunkel (@NiklasKunkel)
Contributors:
Type: Process Component
Tags: oracle-onboarding, oracles
Oracle Team Name: Green
Status: Accepted
Date Proposed: 2020-07-08
Date Ratified: 2020-07-28
```
## Sentence Summary
MIP10c3-SP3 onboards the MANA/USD Oracle.

## Specification

### Introduction

This Oracle would provide the MANA/USD price as part of the collateral onboarding process for MANA.

### Oracle Data Model 

    |    Source    |  Asset Pair   |Quorum | Feed Model  | Oracle Model |
    | :----------- | :------------ | :---: | :---------: | :----------: |
    |   Binance    |    MANA/BTC   |   13  |    Median   |    Median    |
    |   Bittrex    |    MANA/BTC   |
    |   Coinbase   |    MANA/USDC  |
    |   Huobi      |    MANA/USDT  |
    |   Upbit      |    MANA/KRW   |


### Oracle Supporting Data Model(s)

**USDT/USD (canonical)**

    |    Source     |  Asset Pair   |  Feed Model  |
    | :------------ | :------------ | :----------: | 
    |   Binance     |    BTC/USDT   |    Median    |
    |   BitFinex    |    USDT/USD   |              |
    |   FTX         |    ETH/USDT   |              |
    |   Huobi       |    ETH/USDT   |              |
    |   Kraken      |    USDT/USD   |              |
    |   OKEx        |    BTC/USDT   |              |

**USDC/USD**

    |    Source     |  Asset Pair   |  Feed Model  |
    | :------------ | :------------ | :----------: | 
    |       1       |    USDC/USD   |      N/A     |

**KRW/USD**

    |          Source       |  Asset Pair   |  Feed Model  |
    | :-------------------- | :------------ | :----------: |
    | European Central Bank |    KRW/USD    |      N/A     |
 
### Oracle Address
- Medianizer - 0x681c4f8f69cf68852bad092086ffeab31f5b812c
- Oracle Security Module (OSM) - 0x8067259ea630601f319fcce477977e55c6078c13
    
### Supported Tools
- Setzer - 27628c409128492874151239a114faa017099943 - [Added support for MANA/USD](https://github.com/makerdao/setzer-mcd/commit/27628c409128492874151239a114faa017099943)
- Omnia - 11406ae80bd0297c28e136282ac90f54cc1801d3 - [Added support for MANA/USD](https://github.com/makerdao/oracles-v2/commit/11406ae80bd0297c28e136282ac90f54cc1801d3)
- MANA/USD Medianizer on Kovan Testnet - [0x721c49EC4002E81bDd466639b574F9107cCc0865](https://kovan.etherscan.io/address/0x721c49ec4002e81bdd466639b574f9107ccc0865)

### Remaining Work

- none

### Summary

MANA has a diverse set of exchanges to choose from enabling a robust Oracle. That being said, liquidity is quite low overall, leaving the door open for 3rd party manipulation of order books give enough capital. The liquidity profile will be monitored closely by the Oracle Team and the ensuing risks have been discussed with the Interim Risk Team.