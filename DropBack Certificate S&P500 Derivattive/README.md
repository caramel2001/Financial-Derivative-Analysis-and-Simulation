## 1. Product description

"USD Drop-Back Certificate" is tied to the S&P 500® Index, with a term of 3 years. It is issued by Credit Suisse AG,
London Branch, and allows participation in the performance of the S&P 500® Index. The certificate also has a fixed
interest component of 9.85% p.a. daily accrued and paid at maturity. It also has a mechanism of trigger events, where
additional investments are made if the index drops below certain percentages from its initial level. We incorporated dividends in the simulation which yielded better results.

## 2. Model(s) of Underlying Assets and Estimation/Calibration Approach

We modelled with and without callable feature and incorporated variance reduction for each model using Control Variate and Emphirical Martingale Correction method.
we used the follwoing models:

- Heston Stochastic Volatility
- Implied Volitlity Model
- Interest Rate Model (CIR Model)
- Normal GBM

## 3. Pricing and Estimating Sensitivities of the Product
To assess the model's response to changes in the underlying asset price, the Greeks δ and Γ are estimated using the
Finite-difference Method for each day in our simulation period. We set h = 0.001 * (terminal price) and used the GBM with
dividend yields to obtain the 3 price paths. Surprisingly the delta values are quite small, which indicates the price of the product is quite stable with respect to the underlying asset. The gammas are also on the lower end and sync up to the spikes in the deltas.

## 4.  Simulation Settings
Settings that were common among all experiments we ran (except the Heston model) are as follows.
- The product was priced from 9th August to 9th November, 2023.
- The backtest window was 252 days long.
- 20,000 simulations were done for pricing each day.
- We generated a set of 20,000 random normal variables and used the same set for each experiment.

Additionally, the simulations were sped up by using the NumPy and Numba libraries that leveraged parallelisation and
Just-In-Time compilation to allow us to conduct 20,000 simulations in under 4 minutes. In fact, we stopped at 20,000
simulations as beyond that our laptops could not keep that many random normal variables in memory!

## 5. Conclusion and Reflection

In this project, we have utilised various modelling paradigms to predict the derivative price across rolling windows. Now,
we attempt to interpret our results using two ablation experiments:
1. How does our product compare to a similar product with the same initial portfolio distribution ($550 in S&P 500 &
$450 at 9.85% simple interest p.a.) but no triggers. That is, how do the triggers affect the price of the product?
2. What is the difference between investing the denomination in this financial product versus directly investing the
denomination in an ETF maintaining the S&P 500 index?

For the first query, we ran simulations using the GBM model on both the real and our hypothetical product with no triggers.

The results are presented as follows:

We can clearly observe that the hypothetical product without triggers would be priced higher than the existing financial product. This can be primarily attributed to the fact that the 9.85% simple interest p.a. is much higher than the historical average return on the S&P 500 index, which is 6.43%. Thus, the value of this product would be higher if
none of the triggers are ever hit, and no proportion of the funds are transferred from the faster growing component to the
S&P 500 index.

Now, what would happen in the scenario in which the price of S&P 500 index falls? Our product would transfer some
amount from the faster growing component to the S&P 500 index. The rationale here is that if the S&P 500 index recovers
quickly, the transferred amount would also grow quickly, and would lead to better returns than the case in which all the
capital was invested in the S&P 500 index. However, if the value of the S&P 500 index does not recover quickly enough
(at less than 9.85%) after a crash, the transfer would be worse than the original distribution of the funds. In the worst case, the value of the index falls to zero, and the buyers lose all their investment.

In conclusion, the product analysed performs better than the investment in S&P 500 index in all cases other than the one
in which S&P 500 grows faster than 9.85% simple interest p.a