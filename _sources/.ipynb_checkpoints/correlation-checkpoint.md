# 6. Continuous versus Continuous

Up until now, we have only looked at comparing a `categorical` predictor to `continuous` response but we haven't considered looking a **continuous predictor**. This is where we can look at the relationship between two numerical columns. Oh! Oops, I think I mentioned somewhere that we would only visualize things as boxplots in this unit. I guess I lied because as mentioned before, the best way to visualize linear relationships is with a good ol' **scatterplot and best-fit line**. 

```{figure} https://revopsteam.com/wp-content/uploads/sites/7/2023/05/rev-types-of-data-visualization-infographics-01-1-1024x737.png
:height: 250px
```

This will allow use to interpret **correlations**, if a linear relationship even exists. Using a Pearson or Spearman test, you can determine if the correlations that you are seeing are actually significantly 'real' or not. 

## Pearson and Spearman Correlation Test

A Pearson correlation test is a measure of correlation and statistical significance of two continuous groups (predictor and response) where the response data is **parametric**. Spearman, on the other hand, doesn't assume that the data is parametric and, therefore, can work with **non-parametric** data. Another key assumption that is different between Pearson and Spearman is the skedasticity of the data.

Pearson's test will assume that the data points follow a **homoscedastic** pattern which means that they are evenly scattered around the best-fit line. Spearman's test makes no such assumptions and can work with either homoscedastic or **heteroscedastic** data. 

```{figure} https://i.sstatic.net/RXQv9.png
```

The way that a correlation test works is that it attempts to predict the `middle` of the correlation; and as the predictor values increase, it measure how much the response values deviate from this middle. If they deviate upwards, there is a **positive correlation** and if they deviate downwards, there is a **negative correlation**. How much they deviate is also taken into consideration when generating the p-value which tells you whether the correlation is significant or not. 

## Correlation coefficient

The two correlation tests don't just generate a p-value but also a **correlation coefficient**. The correlation coefficient ranges from -1 to 1 where -1 is a perfect negative correlation, 1 is a perfect positive correlation, and 0 is no correlation. 

## Running a correlation test in R

Both the Pearson and Spearman tests use the same base function but with an option difference:

```
# Spearman is the default
cor.test(~Y+X, data=dat)

# Pearson is an optional change
cor.test(~Y+X, data=dat, method="pearson")
```