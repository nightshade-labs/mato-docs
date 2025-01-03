# Introduction

Mato introduces a new type of order book that mitigates sandwich attacks and helps traders to efficiently execute large trades.

We call it the time-weighted order book, or TWOB (pronounced "tee-wob")[^note].

It works by streaming orders continuously over a user-defined time horizon.

## Summary

Let's say Alice wants to buy 100 million USDC worth of SOL on-chain. An order of this size will be expensive to execute on existing AMMs, which must charge Alice a high price in case she knows something they don't.

Today, Alice's best option is to manually break her order up into several pieces and execute them over a period of hours, giving the market time to realize she does not have inside information so it can give her a better price.

If she sends a few large sub-orders, each will still have significant price impact and will be vulnerable to sandwich attacks by adversarial traders. On the other hand, if she sends many small sub-orders, she will have to take on all the work and risk of active trading, and will pay high costs in the form of transaction fees.

The TWOB resolves this dilemma for Alice by trading on her behalf. It breaks her order into infinitely many infinitely small virtual orders to ensure perfectly smooth execution over time. Because this streams trades even in between blocks, it is also less susceptible to sandwich attacks.

[^note]: TWOB shares some conceptual similarities with [TWAMM described by paradigm](https://www.paradigm.xyz/2021/07/twamm) and therefore draws from its illustrative examples.
