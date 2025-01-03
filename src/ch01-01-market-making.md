# Market Making Basics

## Market Makers

Consider a market for two financial assets, say, USDC and SOL. A market maker is a participant in this market who is willing, at any time, to trade either one for the other.

If you have 100 million USDC and want to use it to buy SOL, you probably won't be able to find another individual who wants to do the opposite trade at the exact same time. Instead, you will most likely go to a market populated by one or more market makers and trade with them.

## Adverse Selection

Market makers earn a profit from the spread, effectively a fee they charge on each trade. They lose money when prices move against them — when they buy an asset whose price then goes down, or sell an asset whose price then goes up.

Unfortunately for market makers, prices tend to move against them on average. This phenomenon is known as adverse selection. It happens because traders with information about future price movements are more likely to trade against market makers for large size.

The most dangerous orders are ones that are both large and urgent, because those are precisely the type of orders informed traders tend to make. As a result, the most basic market making tactic is to fade incoming orders, adjusting prices up when a large buy order comes in, and adjusting prices down when a large sell order comes in.
