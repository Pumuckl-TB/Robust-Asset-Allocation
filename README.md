# Robust-Asset-Allocation

This is a python implementation of the robust bayesian portfolio method introduced by Evan W. Anderson and Ai-Ru Meg Cheng in 2012. 
The orginial paper can be found here: https://www.jstor.org/stable/43866052

The named sections in the code refer to the precise parts in the original paper. The data required to run this code is attached. 

## Modern Portfolio Theory
Mean-Variance optimization, better known as modern portfolio theory, describes the school of Markowitz, whereby the trade-off between risk and reward is solved, such that the expected return is maximized given a certain level of risk (cf Markowitz 1952). This mathematical approach to asset allocation is the formalization of diversification, which allows the portfolio to reduce all asset specific risk to the level that only market risk remains. This implies that a portfolio has a lower risk to the same expected return compared to a non optimally diversified strategy and therefore, arguably the most efficient way to asset allocation. However, this only holds true given the true expected returns and covariances are known, since those are crucial for an optimal allocation. Historical correlations might indicate future ones but are not perfectly matching. Thus, distortions arise and portfolios are non-optimally diversified in future periods. This parameter uncertainty is a key problem to solve.

## Robust Bayesian Portfolio Choices
I compare different methods to allocate assets in a portfolio that go beyond simple Markovitz portfolio optimization. These robust approaches aim to be more stable in out-of-sample performance by accounting for real world uncertainty and frictions. The main model is based on Anderson and Cheng 2016 approach which introduces a Bayesian probability framework. In each time period a new model is born and all probabilities of all previous models are updated to account for this new information. This information then gets aggregated to allocate the assets accordingly.

I compare this model to a simple Markovitz portfolio strategy and an equal-weight strategy. I find that depending on the time frame and performance metric, different models perform best. During higher volatility periods the Bayesian approach achieves the best results, while under more stable conditions the equally weighted model is superior. Therefore, in regard to the research question, whether ‘Robust Bayesian Portfolio Choices’ yield superior returns in an environment of extreme financial markets, I can conclude that this holds true based on the focus on sharpe ratios, max drawdowns and returns, even though the strategy was outperformed otherwise. I investigate a timeframe from 2005 until 2020 to evaluate these models.
While no clear winner emerged it is interesting to note that the Bayesian model might be a good method in more volatile times such as recessions.
Potential extensions would be the inclusion of GARCH specifications to model time varying volat- ility in the variance-covariance estimations, a combination of Anderson and Cheng’s and Richard Michaud and Robert Michaud’s approach, wherby the ‘Robust Bayesian Portfolio Choices’ technique is enforced by repeatedly bootstrapping past observations.

Below you will find the math for this model. 

![alt text](https://github.com/Pumuckl-TB/Robust-Asset-Allocation/blob/main/Model1.png)

![alt text](https://github.com/Pumuckl-TB/Robust-Asset-Allocation/blob/main/Model2.png)
