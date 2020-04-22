# factor-investing-GAI
-- z-score.ipynb: transfer raw data from winsor_factors_univariate.csv and show the matrix with factors and industry's z_score <br/>
-- pre-processing.ipynb: data preprocess <br/>
-- Calculate_score.ipynb: score calculation from the matrix with factors and industry's z_score <br/>
-- theta-Score.ipynb: theta calculation and the return <br/>

We follow Brandt, Santa-Clara, and Valkanov (2004) in calculating our factor scores for the portfolio. They model the portfolio weight of each stock directly as a function of the factor. The coefficient(s) of this function is found by optimizing the investor’s average utility of the portfolio’s return over the sample period.
Let the portfolio weights, benchmark weights (cap-weighted), and score vector for month 𝑡 be

representedbyvector𝑊,𝑊,and𝑆 respectively.For𝑁securitiestheyhavea𝑁×1shape.Then
𝑡𝑡𝑡
the portfolio weights can be represented as a sum of benchmark weights and scores.
