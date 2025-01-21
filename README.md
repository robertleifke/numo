# Numo

[![Fuzz Testing](https://github.com/Uniswap/uniswap-v3-core/actions/workflows/fuzz-testing.yml/badge.svg)](https://github.com/numotrade/numo/actions/workflows/fuzz-testing.yml)
[![npm version](https://img.shields.io/npm/v/@uniswap/v3-core/latest.svg)](https://www.npmjs.com/package/@numotrade/numo/v/latest)

> ⚠️ **WARNING:** This code has not yet been audited. Use at your own risk.

## Overview

The Uniswap v4 hook enables an options marketplace for stablecoins. Allowing users to hedge, earn yield, or speculate on stablecoins depegging. 

### Earning yield on stablecoins

Similar to a covered call, users deploy their stablecoin liquidity to a Numo pool (e.g. USDC/USDT) with a desired `expiry` and `price_range`. During this time, users are selling a call option from which they yield.

### Hedging FX pairs. 

Any option strategy can be replicated with Numo. In traditional finance, a common strategy for hedging FX risk are collars. Using Numo, a user could build a custom replicated portfolio of an european-style, "zero-cost" collar for FX pairs (e.g. EUROC/USDC). This enables SMEs to hedge their FX risk with a low cost alternative that is non-custodial and doesn't require a sophisticated market maker as a counterparty.

Hedgers buy a FX collar by providing a desired notional amount of `EUROC` and `USDC` into Numo as well as set the cap and the floor for which the exchange rate should stay. Lastly hedgers can opt for an expiry to meet their specific needs (e.g. geopolitical event). Unlike traditional FX collars, there is no need for a direct counterparty. Instead the expected returns of a FX collar are provided from fees on spot volume for the `EUROC/USDC` pair on Uniswap. You can think of fees on swaps as the premium paid by the option buyers who enjoy the *right but not obligation* to exercise the provided option if it is in the money. Numo deploys a `collar` instance for each pair. While each `collar` can handle any two arbitrary ERC-20 tokens but has its premium optimized for FX pairs.

#### Acknowledgements

The smart contract suite is inspired by Primitive's open source [RMM](https://github.com/primitivefinance/rmm) and the [replicating market makers](https://arxiv.org/abs/2103.14769) paper that first proved the replicated portfolio of any option strategy can be constructed using AMMs.

## Usage

```
forge install
```

#### Update dependencies

```bash
git submodule update --init --recursive
```

## Deployment

**TODO:** Add Deployed Addresses

---
