# factor-investing-GAI
-- z-score.ipynb: transfer raw data from winsor_factors_univariate.csv and show the matrix with factors and industry's z_score <br/>
-- pre-processing.ipynb: data preprocess <br/>
-- Calculate_score.ipynb: score calculation from the matrix with factors and industry's z_score <br/>
-- theta-Score.ipynb: theta calculation and the return <br/>

We follow Brandt, Santa-Clara, and Valkanov (2004) in calculating our factor scores for the portfolio. They model the portfolio weight of each stock directly as a function of the factor. The coefficient(s) of this function is found by optimizing the investor’s average utility of the portfolio’s return over the sample period.

Notes:
1. Number of securities change over time. We only choose months in our sample when the
number of securities exceeds 100.
2. The number of samples (stocks) differ for each factor. Hence, the benchmark portfolios are
slightly different for each factor. The benchmark stats in all the portfolio tables is for B/M.
3. Our benchmark portfolio returns show 99% correlation with the market portfolio returns from
Kenneth French’s website.
4. The average risk-free rate in the sample is 0.0461 (annualized).
5. P-values for theta’s are all either zero or close to zero.
6. The timeframe for each factor vary. Generally, for annual factors its 1961-07 to 2018-11, and 1972-01 to 2018-11 for quarterly factors.
