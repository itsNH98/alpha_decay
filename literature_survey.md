# Strategy Research 

**Note: Might merge to Alpha Decay**
We take all anomalies that have very recent significance and some anomalies that have longer term strong significance, and plan stock trading strategies.

In the longer term horizon, it would be interesting to see whether the anomalies themselves can be forecasted or classified using machine learning methods based on sets of features (own lags, other anomalies, economic data). In this manner, we could have a "meta-strategy" of sorts

Given a portfolio of anomalies (which abnormal returns are exceeding the risk free by definition), it is probably that some will perform better in some conditions, with others performing better in some other conditions.

- Plot the rolling correlation matrix of diverse anomalies?
- Plot threshold correlation (as in Christoffersen & Langlois 2012)
- Rank approximation of anomalies, forecasting their distribution, something like this 


## Implemented 

### Announcement Returns (Chan, 1995)
Past return and past earnings surprise each predict large drifts in future returns after controlling for the other. 

3-12 months horizon: Winners outperform losers 

"If we do not understand why a particular investment strategy works then there is a good chance that the strategy will not work OOS" 

This paper related the evidence on momentum in stock prices to the evidence on the market's underreaction to earnings-related information. 

Earnings surprises + momentum represent underreactions reaction to different information 

Most common way of measuring earnings suprises is int erms of "standardized unexpected earnings"

Ranking various used in price momentum strategy is six months past returns. 

Three different measures of earnings news: 
1. Unexpected earnings SUE (I prefer)
SUE = e_iq - e_iq-4 / std of unexpected earnings 
2. Cumulative ABR :
ABR = E (r_ij - r_mj)
3. Six month moving average of past changes in earnings forecasts
REV6_it = E change in earnings average/scaled by stock price

Skip the first five days after portfolio formation before we begin to measure returns. 

The spread between the SUE of the winner and loser portfolios is actually wider in the quarter following portfolio formation. 

"The abnormal return around the first subsequent announcement is higher by 2.6% for winner stocks compared to loser stocks"

### Firm Age Momentum (Zhang, 2006)
Role of information uncertainty in price continuation anomalies and cross-sectional variations in stock returns. 

Information uncertainty: Ambiguity with respect to the implications of new information for a firm's value 

Investors should underreact even more in cases of greater information uncertainty?

The new information is the average monthly stock returns over the past 11 months (1 year momentum)

Greater information uncertainty leads to relatively higher future returns following good news and relatively lower returns following bad news. 

"Trading strategies that buy good news stocks and shot bad news stocks work particularly well when limited to high-uncertainty stocks" 

Measure of good news is earnings revision

5 alternatives of uncertainty: 
1. Firm age (!!) 
2. Analyst coverage 
3. Dispersion in analyst forecasts 
4. Stock volatility 
5. Cash flow volatility 

## On hold

### DivOmit (Michaely, 1995)
Quite old 
Would be very easy to backtest 

### ShortInterest (Dechow, 2001)
Seems in contradiction with the findings of Nagel 2005 (professional investors which are not short sellers??)

### Change in NWC (Soliman, 2008)

### GP (Novy-Marx, 2013)
Shows as very strong in the last 10 years, but not so previously.

I think this anomaly is perhaps a tad simple to not be arbitraged away



## In consideration

### Skew (Xing, 2010)
Stocks with the steppest smirks in their option underperform significantly

Might be hard to replicate due to live data availability from options, but these measures show very strong performance (along with the Smile slope, which is similar)

Option prices contain important information content of volatility smirks 

Smirks become especially prominent before big negative jumps in price. 

Higher volatility smirks in individual options should reflect a greater risk of large negative price jumps. 

Stocks with steeper volatility smirks underperform those with flatter smirks by 10.90% per year on a risk adjusted bases 

Persistent for at least 6 months

Stocks with the steepest smirsk are those experiencing the worst earnings shocks


### Smile Slope (Yan, 2011)
Negative relation between expected stock return and slope of implied volatility smile (seems very similar to Xing 2010, almost identitical).

Options are forward looking contracts and thus are informative about future expected returns. 

Slope of implied volatility smile: Difference between fitted implied volatilities of one month to expiration put and call options with option delta = -0.5 and 0.5

Slope is proportional to the jump size 

Expected stock return is decreasing with average stock jump size 




### RIO (Nagel, 1995)
VERY aligned with the limits to arbitrage argument. 

Shows very strong performance in the recent years too, so would be interesting.

Central element of the mispricing story has to be an explanation of why these abnormal returns are not arbitraged away.

Do short sale constraints play a role in the limits to arbitrage arguments?
1. Institutional and cultural reasons = indirect short sale constraints are more likely to affect stocks that are owned by individuals (rather than by institutions)
2. Short selling is costly 

Predictions: 
1. Predictability should be most pronounced among stocks with low institutional ownership. Going down from high to low inst. ownership, sorts on variables that forecast returns should produce an increasing spread in future returns, but mainly on the short side. 

- Using residual institutional ownership (percentage of shares held by institutions, adjusted for size in a cross sectional regression)
- Exclusion of small stocks below the 20th NYSE/Amex size percentile 
- Predictors: Dispersion and Firm-Level volatility

Conclusion: Holding size fixed, the strength of these return predictability effects increases sharply with lower institutional ownership


### Earnings Streak (Loh, 2012)
Anomaly very close to the Mixed Momentum anomaly which is already implemented. 

Trends bias investor expectations. Investors underreact to streaks of consecutive earnings surprises with the same sign. 

Streaks explain about half of the post-earnings announcement drift in their sample. 

Intuitive idea of "balancing" 

Paper uses past earnings surprise to test the conflicting predictions of the gambler's fallacy and representativeness 

Main definition of a trend is a streak of consecutive earnings surprises with the same sign

Strategies:
1. Ignores the magnitude of earnings surprises and buys stocks with positive streaks while selling those with negative streaks. Respective streak length is minimum two (2)
2. Accounts for the magnitude of the most recent earnings surprise. Subportfolios of streaks 




## Rejected

### Exchange Switch (Dharan, 1995)
Stocks have low returns post-listing
Rejected due to only in the short-side

### Order Backlog Changes (Baik, 2007)
Niche accounting measure 
Paper has very low amount of citations
Rejected





## Summary

### For very strong recent anomalies (10 years)

Obviously I have a strong preference for anomalies that correspond to (i) behavioral bias of momentum or persistence (ii) limits to arbitrage. Also, we can see empirically that these anomalies stand the test of time, so that preference is motivated by data. 

Numerous anomalies surround accounting measures. My intuition is that since this is public information, it will be arbitraged away with time. There are also several modified versions of the accruals anomaly. However, I fail to see the behavioral bias behind this type of anomaly and their concordance with the limits to arbitrage argument. Therefore, I will probably not trade them 

### For very strong longer termed anomalies (25 years)

