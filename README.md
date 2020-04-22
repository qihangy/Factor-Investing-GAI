# Factor-Investing-GAI

We follow Brandt, Santa-Clara, and Valkanov (2004) in calculating our factor scores for the portfolio. They model the portfolio weight of each stock directly as a function of the factor. The coefficient(s) of this function is found by optimizing the investor’s average utility of the portfolio’s return over the sample period.

===================================================================================== 

Main File:<br/>

-- z-score.ipynb: transfer raw data from winsor_factors_univariate.csv and show the matrix with factors and industry's

-- z_score Calculate_score.ipynb: score calculation from the matrix with factors and industry's z_score <br/>

-- theta-Score.ipynb: theta calculation and the return <br/>

-- pre-processing.ipynb: 
1. Data Cleaning Process <br/>

   a. clean <br/>
        i. input: raw_Q_file.csv {quarter_compustat_0227.csv}
            raw Q file is the raw csv file from compustat fundamentals quarterly download all the variables and entire database from 1961-01 to the latest available date in the query filter for foreign incorporation code or fic == USA exchange code or exchg == 11, 12 or 14 <br/>
        ii. output: df_rdq_output.csv; df_Q_output.csv <br/>
        iii. package: clean_quarterly.py (Compustat fundamentals quarterly data)<br/>
        <br/>
   b. clean <br/>
        i. input: annual.csv; df_rdq_output.csv (Compustat fundamentals annual data)<br/>
        ii. output: df_A_output.csv <br/>
        iii. package: clean_annual.py <br/>
        <br/>
   c. link fundamental data with prices <br/>
        i. input: wprice.csv; <br/>
        ii. output: linkedprice.csv <br/>
        <br/>

2. Factor Calculations <br/>

   a. Quarterly factors <br/>
        i. Input: df_Q_output.csv; linkedprice.csv <br/>
        ii. Output: final_Q.csv <br/>
        iii. Package: quarterly_factors.py <br/>
        <br/>
   b. Annual factors <br/>
        i. Input: df_A_output.csv <br/>
        ii. Output: final_A.csv <br/>
        iii. Package: annual_factors.py <br/>
        <br/>
   c. winsorize.py does size screens and cross-sectional winsorizing <br/>
        i. Input: final_Q.csv, final_A.csv <br/>
        ii. Output: all_factos.csv; winsor_factors_univariate.csv <br/>

=========================================================================================

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
