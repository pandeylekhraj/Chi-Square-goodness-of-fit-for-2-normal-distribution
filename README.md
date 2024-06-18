# Chi-Square-goodness-of-fit-for-2-normal-distribution
To test the goodness of fit for your 2D histogram data against the expected bivariate normal distribution, you can use the Chi-square test. Here is the step-by-step explanation.

1) Generate Example Data:
 You generate data_x and data_y from normal distributions.

2) Create 2D Histogram:
 You bin the data into a 2D histogram (hist) with num_bins bins.

3) Calculate Expected Counts: 
Using the mean and standard deviation of data_x and data_y, you define a bivariate normal PDF function (bivariate_normal_pdf) and integrate it over each bin to compute the expected counts (expected_counts).

4) Flatten Arrays: 
Flatten both the observed (hist) and expected (expected_counts) matrices into 1D arrays (observed_counts_flat and expected_counts_flat) for the Chi-square test.

5) Normalize Expected Counts: 
Ensure that the total sum of expected counts matches the total sum of observed counts to avoid Chi-square test errors due to discrepancies in total counts. Code might throw an error

6) Perform Chi-square Test: 
Use scipy.stats.chisquare to compute the Chi-square statistic (chi_square_stat) and p-value (p_value).

7) Calculate Degrees of Freedom: 
Determine the degrees of freedom (df), which is typically (number of bins) - 1.

8) Determine Critical Value: 
	Calculate the critical value for a 95% confidence level using chi2.ppf(0.95, df). Lastly, test the null hypothesis rejected or not.
