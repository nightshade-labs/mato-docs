# Automated Market Makers

## The Constant Product Formula

The constant product formula is a simple rule that allows anybody to spin up both a new market and a new AMM for a new pair of assets instantaneously.

To create a new Constant Product AMM (CPAMM) between two assets X and Y, a user, called a liquidity provider, or LP, deposits reserves x and y of those two assets.

The ratio of these assets at any given time represents the instantaneous price on the AMM, or the price it will charge for a very small order. For example, if a CPAMM contains 200 USDC and 1 SOL in its reserves, its instantaneous price for SOL will be 200 USDC.

When traders come to trade with the AMM, it decides what price to give them based on the formula xy = k, where x and y are the reserve sizes and k is a constant. This means that the product of its reserve sizes stays the same during a trade (ignoring fees).

### Example

Consider an SOL/USDC CPAMM with 200 USDC and 1 SOL in the reserves, so that x = 200, y = 1, and xy = k = 200. The instantaneous price of this AMM is 200 / 1 = 200 USDC per SOL.

If a trader comes and buys 50 USDC worth of ETH, that means they are depositing 50 USDC into the X reserves, so that we will have x = 200 + 50 = 250.

Then, since k = 200, we must have y = k/x = 200/250 = 0.8 after the trade. Since y was originally 1, 1 - 0.8 = 0.2 SOL must have gone to the trader.

Since the trader bought 0.2 SOL with their 50 USDC, they paid an average price of 250 USDC per SOL. This high price relative to the instantaneous price reflects the large order size relative to the liquidity in the AMM.

### Price Impact and Adverse Selection

In the above case, the trader had to pay 250 USDC per SOL for their large order when the cost for a small order would have been only 200 USDC per SOL. This difference in price is referred to as the price impact of the order. The larger the incoming order, the greater the price impact.

This is how the AMM combats adverse selection: large incoming orders are more likely to be informed, and so the AMM makes them pay a high price. It is the automated equivalent of fading an order.
