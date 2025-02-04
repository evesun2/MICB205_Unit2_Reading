# 4. Parametric Single Comparisons

Before we move into the first statistical test, I want to address what statistics does for our data analysis. When we compare the summative information about our data which allows us to compare between predictor groups, we focus on patterns. For example, we look at whether the mean is higher in group A versus group B or whether one group has a higher standard deviation than another to infer that the group experiences greater variability. But all of these things are inferences made by us based on those patterns. If we want to definitively say that a comparison (eg. Group A has a higher mean than Group B) is actually **significant**, we need to apply the appropriate statistical test to measure our level of confidence and error in that interpretation. Let's get into the first test. 

## t-test

The first statistical test we want to look at is the classical **student t-test**. 

```{figure} https://www.investopedia.com/thmb/pUIy_k7H35ssuuD3AHsd1Uei6I4=/750x0/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/t-test_final2-d26bbb129cc441c192ccf8e784ae06a4.png
:height: 250px
```

Every statistical test is going to have a set of assumptions. The more our data fit those assumptions, the more likely we are to get an accurate interpretation of the statistical test. This is why it is important to evaluate our data and what we are comparing to ensure we pick the right test. Multiple different statistical tests can be used for the same research question but they might not give an accurate interpretation if it is not a good fit.

Here are the assumptions associated with a t-test:

1. The data for the response is continuous and the predictor only has two categories 
2. The response data is parametric
3. There is equal variance between the two groups (although it does take in consideration the standard deviation)

The t-test is going to consider 3 things when analyzing the differences between the two groups: means, standard deviations and sample size. If you are curious about the math behind the t-test, check out this [resource](https://www.investopedia.com/terms/t/t-test.asp ).

## p-value

The t-test will generate a **p-value** which is essential a measure of how likely the **null hypothesis** is true.

**Null hypothesis**: This is the opposite of your own hypothesis. So, if you hypothesize that Group A is going to have a higher mean than Group B, the null hypothesis will be that it will not have any difference. 

When the t-test spits out the p-value, it will tell you how likely the null hypothesis is true. Let's interpret an example:

> You set your confidence level to 95% (which is what we will set for this course) which means that
> you will accept an error margin of 5%. Anything below 5% for a p-value means that you have enough
> confidence to accept that the comparison is **significant**. If the p-value is above 5%, this means
> that there is a greater chance (above your accepted threshold) that the null hypothesis is true and 
> your comparison is not significant. 


## Running t-test in R

R was originally developed for statisticians so it is full of functions used to perform statistical tests! For most tests, it follows the common structure of `func(Y~X, data = dat)` where Y is your response, X is the predictor, and dat is your data frame. The ~ represents an indication that you want to explore the relationship between the two. You can also structure it a bit differently as is shown for the t-test code below:

```
# Y is your response column and X is your predictor column
# two ways to structure the code
t.test(Y~X, data=dat)
t.test(dat$Y~dat$X)

# You can also compare two vectors instead of columns
t.test(A_vec, B_vec)
```

## ANOVA

An ANOVA (Analysis of Variance) works much the same way as a t-test except that it can compare across more than two groups for the predictor. Because it cross-compares more than two groups, it can look at the variability between all the groups and within all the groups.

```{figure} https://www.leansixsigmadefinition.com/wp-content/uploads/2019/03/anova_charts-e1578120944898-1024x395.jpg
:height: 300px
```

The assumptions are essentially the same as the t-test except that now it can compare across more than two groups (for the predictor). 

To run an ANOVA in R require 3 steps:

```
# Step 1: create a linear model which will save the within and between group variances
model <- lm(Y~X, data=dat)

# Step 2: run the ANOVA test, you can also visualize the results with the summary function
model_aov <- aov(model)
summary(model_aov)

# Step 3: to get a pair-wise comparison, you run a Tukey test
TukeyHSD(model_aov)
```

You interpret the p-values the same way as you do for the t-test. 

You can read more about the math behind the Tukey test in this [wiki here](https://en.wikipedia.org/wiki/Tukey%27s_range_test). 