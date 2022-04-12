# MechaCar_Statistical_Analysis
## Project Overview
Statistics is an essential component to data science because it helps analysts contextualize data and facilitates making informative decisions. 
R is a programming language that helps with statistical analysis. 

Statistical analysis can be helpful when companies are evaluating product design and improvement. 

In this project, AutosRUs' newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on Jeremy and the data analytics team to review the production data for insights that may help the manufacturing team.

## Linear Regression to Predict MPG
Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes. The 5 measurements tested are: 
- Vehicle Length
- Vehicle Weight
- Spoiler Angle
- Ground Clearance
- All Wheel Drive (AWD) or Front Wheel Drive (FWD)
    
### *Hypotheses*
* *Null Hypothesis (H0): The slope of the linear model is zero.*
* *Alternative Hypothesis (HA): The slope of the linear model is not zero.*
### *Results* 
![multiple lm](https://github.com/pnimma01/MechaCar_Statistical_Analysis/blob/b7f4c356a0df7189526b25473e0f17571f0233f9/Resources/Hypothesis.png)

Our multiple linear regression analysis demonstrates that 2 of the 5 variables contribute a non-random amount of variance to the mpg values in the dataset:
* Ground Clearance (p-value: 5.21e-08)
* Vehicle Length (p-value: 2.60e-12)
The p-value from this analysis was 5.35e-11, which is much smaller than our significance level of 0.05. Therefore, we have sufficient evidence to reject the null hypothesis - the slope is not equal to 0.
The R-Squared value of this model is 0.71, indicating a moderately strong likelihood (>70% chance) that this model can be used to predict mpg values in the dataset.

## Summary Statistics on Suspension Coils
Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots
### *Total Suspension Summary*

![summary stats](https://github.com/pnimma01/MechaCar_Statistical_Analysis/blob/9dabaa1c2174c913a5bbe4227bc03e0a902cb335/Resources/Total_Summary.png)

A summary of the entire dataset shows that the mean PSI of the suspension coils is 1498.78 with a variance of 62.29. Because the variance is less than 100, the manufacturing data meets the design specification for all manufacturing lots in total.
### *Individual Lot Suspension Summary*

![Lot Summary](https://github.com/pnimma01/MechaCar_Statistical_Analysis/blob/9dabaa1c2174c913a5bbe4227bc03e0a902cb335/Resources/Lot_Summary.png)

Looking at each lot individually, we can see that all lots (1-3) produce similar mean PSI values (~1500 PSI), however Lot3 produces extremely high variance (170.28) compared to Lot1 and Lot2 (0.97 and 7.46 respectively).
Lot1 and Lot2 meet the design specification, but Lot3 does not since the variance produced by this lot exceeds 100.

## T-Tests on Suspension Coils
Run t-tests to determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 pounds per square inch.
### *Hypotheses*
* *H0: There’s no statistical differences between the observed sample mean and its presumed population mean.*
* *HA: There’s a statistical difference between the observed sample mean and its presumed population mean.*
### *Results*
#### *Total T Test Summary*
![t test all](https://github.com/pnimma01/MechaCar_Statistical_Analysis/blob/9dabaa1c2174c913a5bbe4227bc03e0a902cb335/Resources/t_test.png)

Comparing the PSI values from all manufacturing lots to the population mean produces a p-value of 0.06, which does not pass our signficance level of 0.05. Therefore, we do not have enough evidence to reject the null hypothesis. This means that when analyzing PSI values from all manufacturing lots combined, there is not significant variation in the lots compared to the population mean.

#### *Lot 1 T Test Summary*

![lot1](https://github.com/pnimma01/MechaCar_Statistical_Analysis/blob/9dabaa1c2174c913a5bbe4227bc03e0a902cb335/Resources/t_test_lot1.png)

Comparing the PSI values from Lot 1 to the population mean produces a p-value of 1, which does not pass our signficance level of 0.05. Therefore, we do not have enough evidence to reject the null hypothesis. This means that when analyzing PSI values from Lot 1, there is not significant variation in the lots compared to the population mean.

#### *Lot 2 T Test Summary*

![lot 2](https://github.com/pnimma01/MechaCar_Statistical_Analysis/blob/9dabaa1c2174c913a5bbe4227bc03e0a902cb335/Resources/t_test_lot2.png)

Comparing the PSI values from Lot 1 to the population mean produces a p-value of .6072, which does not pass our signficance level of 0.05. Therefore, we do not have enough evidence to reject the null hypothesis. This means that when analyzing PSI values from Lot 2, there is not significant variation in the lots compared to the population mean.

#### *Lot 3 T Test Summary*

![lot 3](https://github.com/pnimma01/MechaCar_Statistical_Analysis/blob/9dabaa1c2174c913a5bbe4227bc03e0a902cb335/Resources/t_test_lot3.png)

Comparing the PSI values from Lot 1 to the population mean produces a p-value of .04168, which indeed passes our signficance level of 0.05. Therefore, we have enough evidence to fail to reject the null hypothesis. PSI values from Lot 3 are significantly different from the population mean. This supports our previous findings from the summary table, which revealed that the variance in PSI values from Lot 3 did not meet the design specificaiton for the amount of variance allowed.

### T Test Summary
✅ Overall - Meets design specifications

✅ Lot1 - Meets design specifications

✅ Lot2 - Meets design specifications

❌ Lot3 - Does not meet design specifications

## Study Design: MechaCar vs Competition
Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers.
### *What metric or metrics are you going to test?* 
To compare vehicle performance of the MechaCar versus its top competitors, AutosRUs should look at two main performance measures: 
* City and Highway Fuel Efficiency
* Horsepower
### What is the null hypothesis or alternative hypothesis?
* *H0: There is no statistifcal difference in the mean Fuel Efficiency and Horsepower between the MechaCar and its competitors.* 
* *HA: There is a statistical difference in the mean Fuel Efficiency and Horsepower between the MechaCar and its competitors.* 
### What statistical test would you use to test the hypothesis? And why?
* Fuel Efficiency (Miles Per Gallon)
    * A two-sample T-Test should be used to perform this analysis since the independent variable is split (MechaCar vs. Competitors) and the dependent variable (MPG) is continuous.
* Horsepower
    * A two-sample T-Test should be used to perform this analysis since the independent variable is split (MechaCar vs. Competitors) and the dependent variable (horsepower) is continuous.
### What data is needed to run the statistical test?
The data that is needed to run the tests will need to be gathered for both competitors and the MechaCar. Data will be needed for two continuous numerical data types:
* Fuel Efficiency: Fuel Efficiency can be measured by calculating how many miles per gallon the car can achieve at optimal level for both city and highway driving. 
* Horsepower: Horsepower can be measured by each vehicle's torque and tire rotations per minute (RPM) on a dynamometer

