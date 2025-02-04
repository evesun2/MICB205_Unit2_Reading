# 5. Non-parametric Single Comparisons

The t-test and ANOVA rely on looking at the mean and variation to measure the likelihood that a comparison within a single predictor to response is significant or not. This is fine if your data is parametric which means that most of the points cluster around the mean but not all data is parametric. In cases where a non-parametric dataset skews to the left or right, we need to use a test that is not sensitive to the extremes. This is where you can use a Wilcoxon or Kruskall-Wallis test (named after their inventors I assume).

## Wilcoxon test

The Wilcoxon and Kruskall-Wallis (KW) tests both work in essentially the same way with similar assumptions but the KW test can handle more than two groups in your predictor. 

```{figure} https://www.investopedia.com/thmb/D_AxwOnonUnotVL3PUQMu14QWGw=/750x0/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/Wilcoxon-test_sketch_final-bc97bd1b88034fbbba28ca7c14a6ea34.png
:height: 250px
```

Here are the assumptions for the Wilcoxon test, also called the Mann-Whitney test:

1. The response is continuous and predictor is categorical with only 2 groups.
2. Data distribution of the response is non-parametric. 

How does it work?

The Wilcoxon test works by ranking the values within a group, adding up those ranks than comparing them to the other group's summed rank. The ranking is based on differences between the values of one group (in the predictor) and the average of the comparison group.

```{figure} https://online.stat.psu.edu/stat415/sites/stat415/files//lesson48/Lesson48_Data03.gif
:height: 250px
```

If you want to read more about the math involved in this test, try this [resource](https://online.stat.psu.edu/stat415/book/export/html/836).

Because the Wilcoxons test involves ranking the values, the rankings won't change even if we move the extremes further; therefore, it isn't going to be significantly effected by the changes in extreme values like a t-test or ANOVA would be as it relies on the means. 

To run the Wilcoxons test in R:

```
wilcox.test( Y ~ X, data = dat )
wilcox.test( dat$Y ~ dat$X )
wilcox.test( A_vec, B_vec)

```

## Kruskall-Wallis test

The KW test works in essentially the same way as the Wilcoxon except that it can compare across more than 2 groups in the predictor. It also ranks the values and takes the sum as a measure of significance. 

To run the KW test in R:

```
# Run the KW test
kruskal.test(Y~X, data=dat)

# OR run a dunn test to get pair-wise comparisons
dunn.test(dat$Y, dat$X, kw= TRUE)
```

The dunn test is a version of the KW test that does pair-wise comparisons for more nuanced information about your multiple groups. 