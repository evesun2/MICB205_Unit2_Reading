# 7. Multiple Predictors to a Single Response

As we move through the course, we will layer in extra levels of complexity allowing us to ask more complex research questions. So far, we have primarily been looking at comparing one response to one predictor but what happens if we want to know how multiple predictors affect a single response?

For example, how does temperature and salinity affect *E. coli* growth rate?

Remember this figure from section 2, we see that it looks at temperature (x-axis) and growth rate (y-axis), but we have a third axis next to temperature labeled 'aw'. This actually refers to a measure of salt concentration or salinity. So it is possible to compare multiple predictors to a single response. Having multiple axes is a good way to visualize it. But how do we statistically test it?

```{figure} https://akjournals.com/view/journals/066/50/2/full-066.2020.00213_f001.jpg
:height: 300px
```

## 2-way ANOVA

Previously in section 4, we looked at an ANOVA (technically a 1-way ANOVA) where it cross compares multiple groups for in-between and within comparisons. A 2-way ANOVA is going to get crazier and not only make those comparisons but also cross-compare between two predictor variables. Like an ANOVA, it will assume the predictor data is parametric. 

The way that a 2-way ANOVA works is by creating several **models** of possible comparisons. 

- **Model 1** comparing within a single predictor while assuming there is no interaction with the second predictor so it won't try to correct for any effects that the second predictor may have on the response.
- **Model 2** comparing within a single predictor but it does assume that the second predictor affects the first so it corrects for it.
- **Model 3** comparing between the two predictors assuming that they both have an effect on the response.

After it runs through the 3 models, it will tell you if the individual predictors affect the response and whether they collectively have an effect on the response. Going back to the original question at the beginning, if the 2-way ANOVA tells you that there is a significance of both predictors on the response, it means that growth rate is affected when you change both the temperature and salinity and not just individually. 

### Running the 2-way ANOVA in R

You can run the code in one line with all the functions nested or in separate lines:

```
# One line 2-way ANOVA
# X1 and X2 represent the two predictor columns of interest
summary(aov(lm( Y ~ X1*X2, data = dat)))

# Seprate lines, build a linear model first 
mdl <- lm( Y ~ X1*X2, data = dat)
mdl_aov <- aov(mdl)
summary(mdl_aov)
```

## Linear model

If you ran just the linear model code by itself `lm( Y ~ X1*X2..., data = dat)`, like the 2-Way ANOVA, it will also make cross-comparison and it does *somewhat* assume that the data is parametric but it is a bit more flexible which means that it does well with non-parametric data. This is an option when trying to conduct statistical testing on non-parametric data for multiple predictor analyses. 

```
mdl <- lm( Y ~ X1*X2..., data = dat)
summary(mdl)
```

Linear regression is a topic that is beyond the scope of MICB 205 but to describe it in brief, it attempts to build a linear model based on the relationship between the predictors and the response assuming that it can even correlate them. You are free to read through the math on this in this [wiki](https://en.wikipedia.org/wiki/Linear_model).


