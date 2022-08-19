# Kelly-Sizing, Mean-Variance Optimization, and Covariance Shrinkage
We will look into application of Kelly Sizing, Mean-Variance Optimization (MVO) and Shrinked MVO to the (Malaysian) stock market. 

The Kelly criterion is F∗=C−1(M–R), which is analogous to the MVO framework. Figure below shows almost comparable performance between the two approaches, albeit lower Sharpe for MVO due to its higher volatility. Note that Kelly portfolio does not necessarily behave like a mean-variance model.

![image](https://user-images.githubusercontent.com/105033135/185535247-98de69e2-2997-4956-a2b7-690f78e65897.png)

Shrinking the covariance matrix helps with performance, as it addresses the misallocation in MV scaling from estimation error of expected returns and dispersion of stock volatilities. Figure below shows the cumulative returns for MVO and Shrinked MVO (using Ledoit Wolf):

![image](https://user-images.githubusercontent.com/105033135/185540396-aa662095-3762-4fc0-904b-d24eb738d5ec.png)

Another way to calculate the optimal weights F* is by solving for F such that the following integral (below) is a maximum. This is explained in great detail by Rotando and Thorp in their paper titled 'The Kelly Criterion and the Stock Market'. They also recommended truncating the return distribution at +/- 3 sigma to yield more realistic weights. 

![image](https://user-images.githubusercontent.com/105033135/185541208-d770eee5-c175-4383-af79-6bbfdc9bdbc7.png)

Here is the backtested returns we achieved by "chopping off the tails" and solving for optimal weights F*. The result appears underwhelming, which we attribute to leverage and concentrated positions during the bear market of 2020-2021. Mitigation measures include the use of fractional Kelly (i.e. half-Kelly), cap on individual positions, etc. We will look into more risk management measures in later papers.

![image](https://user-images.githubusercontent.com/105033135/185547840-6f6e3866-8002-4b5d-8860-2599a1b2579f.png)





