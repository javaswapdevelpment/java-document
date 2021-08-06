---
description: JavaSwap's Exchange
---

# Exchange

[**Token swaps**](https://exchange.javaswap.io/#/swap) on JavaSwap are a simple way to trade one BEP-20 token for another via automated liquidity pools. In the backend of the exchange we are using [PancakeSwap](https://pancakeswap.finance/).

![JavaSwap Exchange UI](../.gitbook/assets/javaswap-exchange.png)

The liquidity provided to the exchange comes from Liquidity Providers \("LPs"\) who stake their tokens in "Pools". In exchange, they get FLIP \(JavaSwap Liquidity Provider\) tokens, which can also be staked to earn JAVA tokens in the "farm".

![JavaSwap Pools UI](../.gitbook/assets/liquidity.png)

When you make a token swap \(trade\) on the exchange you will pay a **0.2% trading fee**, which is broken down as follows:

**0.17%** - Returned to liquidity pools in the form of a fee reward for liquidity providers.

**0.03%** - Sent to the PancakeSwap Treasury.
