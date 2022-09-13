# MechaCar_Statistical_Analysis

#### Christopher Madden

## OVERVIEW
Throughout the module, you'll extract, transform, and load (ETL) data; visualize the data; and analyze the data using R. Additionally, you'll learn a variety of statistical tests, their real-world application in data science, and their implementation in R. The goal is for you to apply these statistical concepts beyond this module, to any dataset, using any programming language—including Python.
The key points of the module are as follows:
 - Load, clean up, and reshape datasets using tidyverse in R.
 - Visualize datasets with basic plots such as line, bar, and scatter plots using ggplot2.
 - Generate and interpret more complex plots such as boxplots and heatmaps using ggplot2.
 - Plot and identify distribution characteristics of a given dataset.
 - Formulate null and alternative hypothesis tests for a given data problem.
 - Implement and evaluate simple linear regression and multiple linear regression models for a given dataset.
 - Implement and evaluate the one-sample t-Tests, two-sample t-Tests, and analysis of variance (ANOVA) models for a given dataset.
 - Implement and evaluate a chi-squared test for a given dataset.
 - Identify key characteristics of A/B and A/A testing.
 - Determine the most appropriate statistical test for a given hypothesis and dataset.

## Linear Regression to Predict MPG
Questions:
1. Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?
2. Is the slope of the linear model considered to be zero? Why or why not?
3. Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?

![Img1](https://github.com/maddenc33/MechaCar_Statistical_Analysis/blob/main/Images/Img1.png?raw=true)

The resulting model:
mpg = (6.267)vehicle_length + (0.0012)vehicle_weight + (0.0688)spoiler_angle + (3.546)ground_clearance - (3.411)AWD - 104

Among the variables, we find that vehicle ground clearance and vehicle length account for the most variance in the model.  These variables have the strongest influence on miles per gallon performance.  It appears that vehicle weight, spoiler angle and AWD do not significantly impact miles per gallon performance.
There is a relatively high r-squared value, indicating that this model is reasonably reliable at predicting MechaCar prototypes.
The p-value in this case is so small that we can reject our null hypothesis; the slope of the linear model is not zero.

## Summary Statistics on Suspension Coils
Question: The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

The MechaCar Suspension_Coil.csv dataset contains the results from multiple production lots. In this dataset, the weight capacities of multiple suspension coils were tested to determine if the manufacturing process is consistent across production lots.

Statistics for all manufacturing lots:
![Img2](https://github.com/maddenc33/MechaCar_Statistical_Analysis/blob/main/Images/Img2.png?raw=true)

Statistics for each lot individually:
![Img3](https://github.com/maddenc33/MechaCar_Statistical_Analysis/blob/main/Images/Img3.png?raw=true)

Although when analyzing all manufacturing lots, we see that the variance is well within the 100 PSI threshold, when we look at each group individually, we see that lot 3 would fail if analyzed on its own.  Lots 1 and 2 have an acceptable variance and would therefore pass on their own.  This suggests that larger data sets can hide variance in smaller components of that data set.

## T-Tests on Suspension Coils
Prompt: Briefly summarize your interpretation and findings for the t-test results

![Img4](https://github.com/maddenc33/MechaCar_Statistical_Analysis/blob/main/Images/Img4.png?raw=true)

When analyzing the results of the t-test across all manufacturing lots shows that the results are not statistically different from the population mean.

![Img5](https://github.com/maddenc33/MechaCar_Statistical_Analysis/blob/main/Images/Img5.png?raw=true)

![Img6](https://github.com/maddenc33/MechaCar_Statistical_Analysis/blob/main/Images/Img6.png?raw=true)

For manufacturing lots 1 and 2, the p-value is high enough to accept the null hypothesis and the t-test reveals that the results are not statistically different from the population mean.

![Img7](https://github.com/maddenc33/MechaCar_Statistical_Analysis/blob/main/Images/Img7.png?raw=true)

Manufacturing lot 3 is different:  The p-value is low, so we reject the null hypothesis.  Also, the t-test shows that the results do have a high degree of variance from the mean.

## Study Design: MechaCar vs Competition

Various possible metrics to consider when trying to quantify car performance could include horsepower, safety rating, fuel efficiency, carbon emissions, etc.

As an example, let's formulate a short description of the proposed statistical study:

- What metric or metrics are you going to test?

    Let's assume that MechaCar has developed new manufacuring processes that reduce factory emissions, as well as several new vehicle models with very high fuel capacity and efficiency.  A good metric to test for this example will be carbon emissions, comparing MechaCar with a group of similar size competitors.

- What is the null hypothesis or alternative hypothesis?

    Null hypothesis: MechaCar's carbon emissions caused by the manufacturing process and from the operation of their vehicles is very similar to that of similarly sized competitors in their industry.

    Alternative hypothesis: MechaCar's carbon emissions caused by the manufacturing process and from the operation of their vehicles is not similar to that of similarly sized competitors in their industry.  MechaCar may be outperforming, or underperforming, rivals in its industry.

- What statistical test would you use to test the hypothesis? And why?

    Once the proper emissions data is collected from manufacturing facilities and from test vehicles from the companies involved in the study, a one-tailed t-test will be performed to compare MechaCar's data with its competitors.

- What data is needed to run the statistical test?

    We need total emissions for each facility, and for each vehicle model, from each company.  We should also include MechaCar's emission data showing emissions before and after the new innovations were implemented.

