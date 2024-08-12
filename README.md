# MH4518: Simulation Techniques in Finance

Welcome to our repository dedicated to the simulation and pricing of financial derivatives. Here, we explore various models and methods to price complex derivatives effectively. Our repository includes practical examples and deep dives into derivative products and their pricing methodologies.

## Featured Derivative Pricing Examples

We currently feature comprehensive simulations for two specific types of financial derivatives:

1. **[Callable Barrier Reverse Convertible Derivative](https://github.com/caramel2001/Financial-Derivative-Analysis-and-Simulation/blob/39e221e87a1440ac5d2e249ccccfa910ecc0c784/Callable%20Derivative)** - Explore the pricing model and sensitivities of this complex structured product.
2. **[USD Drop-Back Certificate tied to the S&P 500® Index](https://github.com/caramel2001/Financial-Derivative-Analysis-and-Simulation/blob/77f036e4941d2c5ea0728033c81be43538840cbc/DropBack%20Certificate%20S&P500%20Derivative)** - A detailed case study on this index-tied financial instrument.

For more detailed insights, refer to the factsheets included in each project directory.

## Modeling and Simulation of Underlying Assets

In our simulations, we incorporate various asset models to ensure robust derivative pricing:

- **Heston Stochastic Volatility Model**: Used to capture the dynamic volatility of the underlying assets.
- **Implied Volatility Model**: Helps in understanding the market's view on future volatility.
- **CIR Model for Interest Rates**: Utilized for modelling the risk-free rate movements and their impact on derivative pricing.
- **Geometric Brownian Motion (Normal GBM)**: The foundational model for asset price simulation under a random walk hypothesis.

Each model is simulated under various scenarios including with and without call features, and considering the effects of dividends.

## Pricing Derivatives and Sensitivity Analysis

We utilize advanced numerical techniques such as the Finite Difference Method (FDM) to estimate the sensitivities of derivative prices to changes in underlying parameters:

- **Delta (𝛅)**: Measures the rate of change in derivative price relative to the price of the underlying asset.
- **Gamma (𝚪)**: Captures the rate of change of Delta, providing insights into the convexity of the derivative's price.

## Data Analysis and Backtesting

Our repository not only focuses on theoretical modelling but also on empirical testing and validation:

- **Backtesting**: We perform rigorous backtests to validate our pricing models against historical data, ensuring their effectiveness and robustness.
- **Data Evaluation**: Through detailed analysis, we scrutinize the performance and stability of our models under different market conditions.

## Contributing

Interested in contributing to our simulations? We welcome contributions that enhance our simulations or introduce new models.
