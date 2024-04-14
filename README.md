# MH4518 : Simulation Techniques in Finance

In this repository, we simulate and price various derivatives. Currently. we have two complete examples of derivative pricing:

1. [Callable Barrier Reverse Convertible derivative](https://github.com/caramel2001/Financial-Derivative-Analysis-and-Simulation/blob/39e221e87a1440ac5d2e249ccccfa910ecc0c784/Callable%20Derivative)
2. [USD Drop-Back Certificate tied to the S&P 500® Index](https://github.com/caramel2001/Financial-Derivative-Analysis-and-Simulation/blob/77f036e4941d2c5ea0728033c81be43538840cbc/DropBack%20Certificate%20S&P500%20Derivattive)

We have added the Factsheets for the corresponding products for more information.


## 1. Model(s) of Underlying Assets and Estimation/Calibration Approach

We use the following models and simulate  with callable and without callable as well as with dividends and without dividends

- Heston Stochastic Volatility
- Implied Volitlity Model
- Interest Rate Model (CIR Model)
- Normal GBM

## 2. Pricing and Estimating Sensitivities of the Product

We estimated the sensitivities - Delta, 𝛅 and Gamma, 𝚪 using the Finite Difference Method (FDM). Delta refers to the rate of change of an option price with respect to the change in the underlying asset price, whereas Gamma refers to the rate of change of delta with respect to the underlying asset price.

## 3. Data and Backtest Results

We perform backtesting and evaluation for the pricing for each product