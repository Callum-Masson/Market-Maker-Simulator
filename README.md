# Market-Making Simulator

A simplified market-making simulation comparing a basic strategy against an inventory-aware improved strategy.

## Overview
This project investigates how much an inventory-aware risk management method can improve a market maker's P&L and drawdown compared to a basic fixed-spread strategy.

## How it works
- **Price model**: geometric random walk representing the asset's true value
- **Order flow**: simulated buy/sell orders generated with noise around true value
- **Naive market maker**: fixed spread, no inventory awareness
- **Improved market maker**: spread widens with inventory, uses an exponentially weighted moving average for estimating asset value


## Results
After running the simulation 200 times:
- Basic (fixed spread): P&L mean = -1177.69
- Improved (dynamic spread + EWMA): P&L = -266.84

The basic strategy accumulated much larger inventory swings, leaving it exposed
during drift in the true value; the improved strategy's spread widening kept
inventory closer to zero throughout. <br>
It seems slightly counterintuitive that even the improved method yields a negative mean P&L. The cause of this is likely to be because of the estimated asset value never quite being up to date with the true value. The improved method has a better P&L because the estimation method weighs the recent trades more heavily making it closer to the true value than the basic method but still isn't completely accurate. See notebook for full plots.

## What I'd improve with more time
- Order flow imbalance reaction
- Kalman filter for fair value
- Full resting limit order book instead of market orders
- Wider spread until fair value estimate settles
- Skewing to control inventory aswell as widening the spread



