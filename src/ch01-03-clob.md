# Central Limit Order Book

## The Order Matching System

A Central Limit Order Book (CLOB) is a trading mechanism that matches buyers and sellers by maintaining a sorted list of orders, allowing traders to specify their desired prices rather than accepting prices from a formula.

To participate in a CLOB, traders submit either limit orders or market orders. Limit orders specify both quantity and price, while market orders execute immediately at the best available price. These orders are arranged in the order book with buy orders (bids) sorted from highest to lowest price and sell orders (asks) from lowest to highest price.

The spread between the highest bid and lowest ask represents the cost of immediate execution. For example, if the highest bid for SOL is 195 USDC and the lowest ask is 200 USDC, the spread is 5 USDC.

When new orders arrive, the CLOB follows strict price-time priority: orders at better prices execute first, and among orders at the same price, earlier orders execute first.

### Example

Consider a SOL/USDC CLOB with the following orders:

Sell 2 SOL @ 205 USDC

Sell 1 SOL @ 200 USDC

Buy 1.5 SOL @ 195 USDC

Buy 2 SOL @ 190 USDC

If a trader submits a market order to buy 1.5 SOL, they will:

1. First buy 1 SOL at 200 USDC (the lowest ask)
2. Then buy 0.5 SOL at 205 USDC (the next available ask)

The average execution price would be 201.67 USDC per SOL.

### Price Discovery and Market Depth

Unlike AMMs, CLOBs allow traders to express their view of fair value through limit orders. The collection of these orders forms the "market depth" - the available liquidity at different price levels. Deep markets with many orders close to the current price typically provide better execution for large trades.

This is how CLOBs manage price discovery: traders actively compete to provide the best prices, while the order book structure ensures that patient traders can get better prices by posting limit orders instead of crossing the spread with market orders. The trade-off is between immediate execution (market orders) and better prices (limit orders).

### Price Impact and Adverse Selection

In CLOBs, price impact manifests differently than in AMMs. Instead of following a mathematical formula, price impact depends on the available depth of the order book. When a large market order consumes multiple price levels of liquidity, each subsequent fill occurs at a progressively worse price.

This "walking the book" effect illustrates price impact in CLOBs - larger orders must reach deeper into the order book, resulting in worse average execution prices.
However, CLOBs handle adverse selection differently from AMMs. Instead of automatically charging higher prices for larger trades, CLOBs rely on market makers to manage adverse selection risk. These makers can:

- Adjust their quoted prices and sizes based on market conditions
- Cancel or update their orders when they suspect informed trading
- Widen their spreads during periods of high volatility

This dynamic response to market conditions means that CLOB liquidity can evaporate quickly when market makers detect potential adverse selection.
