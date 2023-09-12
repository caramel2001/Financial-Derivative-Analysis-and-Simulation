# MH4518 : Simulation Techniques in Finance
## 1. Product description

Our group has chosen the 10% p.a. Callable Barrier Reverse Convertible derivative product on a single underlying asset, Credit Suisse Group AG, listed on the SIX Swiss Exchange Ltd. The denomination of the product is 1000 CHF, with an initial fixing date of 15 August 2022 and final fixing date of 17 August 2023. The product has a maturity of 1 year, and pays coupons quarterly at 10% p.a., with a barrier at 50% of the initial level. On top of that, the product is callable for early redemption by the issuer quarterly, starting from 6 months, at 100% of the denomination plus the corresponding coupon amount. The product is also labelled as a reverse convertible as the issuer has the option to convert the investment amount to Credit Suisse stocks at a conversion ratio of 184.5018 at the maturity date if the Barrier has been reached during the lifetime of the product.

## 2. Model(s) of Underlying Assets and Estimation/Calibration Approach

We modelled with and without callable feature and incoporated variance reduction for each model using Control Variate and Emphirical Martingale Correction method.
we used the follwoing models:

- Heston Stochastic Volatility
- Implied Volitlity Model
- Interest Rate Model (CIR Model)
- Normal GBM

## 3. Pricing and Estimating Sensitivities of the Product

We estimated the sensitivities - Delta, 𝛅 and Gamma, 𝚪 using the Finite Difference Method (FDM). Delta refers to the rate of change of an option price with respect to the change in the underlying asset price, whereas Gamma refers to the rate of change of delta with respect to the underlying asset price.

## 4. Data and Backtest Results

We are performing backtesting from 15 August 2022 to 8 November 2022. By the help of the above collected data we perform simulations and estimate the derivative price using all data available on the day. After testing multiple
rolling windows of 1 year, 6 months and 3 months. We found out that window size of 3 months is yielding the best results.

## 5. Conclusion and Reflection

To conclude, while the simulated pricings in the backtest do follow the trends in the actual data and are able to capture major dips and rises, there is still a noticeable difference between the simulations and the actual data, that we did not manage to model accurately. The difference in premium between the callable and non-callable product is also quite low, this is because the product only has two early redemption dates and we noticed the probability of calling back the product is also low around 0.25. We also performed some error analysis in order to find reasons behind the largest errors. Such as on 27th October we observed a large error which when we backtracked,could be due Credit Suisse unveiling their new strategy which aims to focus from investment banking towards rich clients and re-allocate capital to global wealth management business, another case of large error was on 23rd September which may account to Credit Suisse looking for capital to revamp their its investment banking business and thinking to quit the US markets announced by Reuters on 22nd September. We also observe an overall trend of increasing errors which we believe is due to our underlying asset being in the limelight for most of the 2022 announcing various changes in leaderships,strategies,etc and also drastic changes in inflation and interest rates is affecting the Banking and asset management sector such as our asset has caused a lot of deviation. Hence, we suggest for future work we should try a model with stochastic volatility and stochastic interest rates together.
