# Market-Making Simulator

A simplified market-making simulation comparing a naive strategy against an inventory-aware improved strategy.

## Overview
Brief 2-3 sentence summary: what the project simulates, what question it's trying to answer 
(e.g., "how much does inventory-aware risk management improve a market maker's P&L and 
drawdown compared to a naive fixed-spread strategy?").

## How it works
- **Price model**: geometric random walk representing the asset's true value
- **Order flow**: simulated buy/sell orders generated with noise around true value
- **Naive market maker**: fixed spread, no inventory awareness
- **Improved market maker**: spread widens with inventory, [+ skewing if you added it]
- **Fair value estimation**: EWMA of executed trade prices

## Results
- P&L comparison (naive vs. improved) — include a plot
- Inventory over time — include a plot
- Drawdown comparison
- 2-3 sentences on what the results show

## What I'd improve with more time
- Order flow imbalance reaction
- Kalman filter for fair value
- Full resting limit order book instead of market orders
- wider spread until fair value estimate settles
- skewing

## Usage
\`\`\`bash
python simulate.py
\`\`\`

## Files
- `simulator.py` — order book and matching logic
