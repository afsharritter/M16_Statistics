# Module 16: MechaCar with R

## Overview

In this project, car manufacturing data was analyzed to assist in the prototyping process for the MechaCar. The findings of these statistical assays will be used to design a competitive study for the MechaCar. 

# Results 
Two datafiles were provided to perform Linear Regression, Summary Statistics, and T-Testing. 

### Linear Regression to Predict MPG

The results of the linear regression analysis on the MechaCar_mpg dataset are shown below:

p-value: 5.35e-11
multi r-squared: 0.7149
adj r-squared:0.6825
F-statistic: 22.07 on 5/44 DF

The multiple linear regression model is:

```
mpg = 6.27 vehicle_length + 1.25e-03 vehicle_weight + 6.88e-02 spoiler_angle + 3.55 ground_clearance - 3.42 AWD - 103.96
```

Coefficients:
|                   |Estimate| Std. Error| t value |Pr(>|t|)|
|-------------------|-------|-----------|-------|-----------|
|(Intercept)     | -1.040e+02|  1.585e+01|  -6.559| 5.08e-08|
|vehicle_length  |  6.267e+00|  6.553e-01|   9.563| 2.60e-12|
|vehicle_weight  |  1.245e-03|  6.890e-04|   1.807|   0.0776|
|spoiler_angle   |  6.877e-02|  6.653e-02|   1.034|   0.3069|
|ground_clearance|  3.546e+00|  5.412e-01|   6.551| 5.21e-08|
|AWD             | -3.411e+00|  2.535e+00|  -1.346|   0.1852|


Vehicle length and ground clearance provided the highest amount of variance to the mpg values in the dataset, receiving P(>|t|) values of 2.60e-12 and 5.21e-08, repectively. The other variables imparted a near-zero amount of variance to the datset. 

The p-value of 5.35e-11 is significantly less than 0.05 indicating that the relationship is statistically significant. The F-statistic of 22.07 is larger than the critical value of ~ 1.97 indicating statistically significant relationship between (at least) one of the variables and mpg. The multiple and adjusted r-squred values of 0.7149 and 0.6825, respectively, indicate a moderately strong correlation. The null hypothesis is rejected. The slope of the linear regression model is not zero. This model does an adequate job of predicting mpg; however the correlation could be imporved. 

### Visualizations for Trip Analysis

The suspension_coil dataframe was first summarized to show the average, median, variance and standard deviation for vehicle PSI values. The results are as follows:

|Average_PSI|Median_PSI|Variance_PSI|SD_PSI|NumVehicles|
|---|---|---|---|---|
|1498.78|1500|62.29356|7.892627|150|

The suspension_coil dataframe was then summarized to reflect PSI measurements for 150 vehicles across 3 lots. The results are as follows:

|Manufacturing_Lot|Average_PSI|Median_PSI|Variance_PSI|SD_PSI|NumVehicles|
|---|---|---|---|---|---|
|Lot 1|1500.00|1500.0|0.9795918|0.9897433|50|
|Lot 2|1500.20|1500.0|7.4693878|2.7330181|50|
|Lot 3|1496.14|1498.5|170.2861224|13.0493725|50|

The three manufacturing lots have similar mean and median values, but with widely differeing variance and standard deviations. Lot 1 seems to reflect the best manufacturing quality, displaying low variance and standard deviation values, indicating that all 50 cars in this lot have very similar PSI values. Lots 2 and especially 3 show poorer manufacturing quality, which is reflected in the lots' higher Variance and Standard Deviation measures. This means that cars in these lots will have vastly different PSI measurements between vehicles in these lots. 

The design specifications indicate that variance must not exceed 100 PSI. Overall, the total variance meets this requirement (62.3 PSI); however Lot 3's variance of 170.3 is much larger than the maximum and will not meet the design specifications for this product. 

### T-Tests on Suspension Coils

A one-sample t-test was performed on the suspension_coil dataset to compare PSI values to a population average of 1500 PSI. The null hypothesis is that there is no statistically significant difference between sample and population means. 

The p-value for this first t-test is 0.06028. Assuming a significant level of 0.05, we must fail to reject the null hypothesis. The sample and population means are statistically similar. 

This process was repeated, performing one-sample t-tests on each manufacturing lot.  

* For Lot 1, the p-value was 1.568e-11, which is smaller than the significance level of 0.05. We reject the null hypothesis and accept the alternative hypothesis that the sample and population means are statistically different. See Figure 1:
![Figure 1](/images/Lot1_T_Test.png)
* For Lot 2, the p-value was 0.0005911, which is smaller than the significance level of 0.05. We reject the null hypothesis and accept the alternative hypothesis that the sample and population means are statistically different. See Figure 2:
![Figure 2](/images/Lot2_T_Test.png)
* For Lot 3, the p-value was 0.1589, which is larger than the significance level of 0.05. We fail to reject the null hypothesis on this lot, indicating that population and sample means are statistically similar. See Figure 3:
![Figure 3](/images/Lot3_T_Test.png)

## MechaCar vs Competition

A possible statistical 