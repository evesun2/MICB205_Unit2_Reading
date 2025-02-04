# 8. Multiple Predictors to Multiple Responses

As you can probably predict from the way this textbook is progressing and from the title of this section, we are now going to complicate things even more with **multiple responses**. Can we cross compare many predictors to many responses. In some situations, this is necessary. For example, typically when considering immune cell percentage, we have to consider the changes in percentage of multiple cells at at time because a change in CD4 percent affects CD8 levels and vice versa. This means that the two responses are actually linked to each other and considering them separately would be inaccurate to do. In MICB 475, students measure microbial diversity which is measured through several responses: unique species numbers, relative abundances, and phylogenetic distances. All three measures have to considered collectively to measure 'diversity'.

## MANOVA and PERMANOVA

There are two statistical tests that allow us to work with multiple responses and predictors: **MANOVA** and **PERMANOVA**. MANOVA is the multivariant analysis of variance and PERMANOVA is the permutational multivariant analysis of variance. 

### MANOVA

A MANOVA assumes that the data is **parametric**. It combines concepts from both a linear model (like an ANOVA) and Wilcoxon test (ranking). First, it builds a linear model to measure the differences between the different comparison groups then it ranks those differences in a three-dimensional way. Based on the variance and sums of the ranks, it will determine whether or not we have significant comparisons. 

```
manova_mdl_multivar <- manova(cbind(Y1,Y2) ~ X1*X2, data)
summary(manova_mdl_multivar)

```

### PERMANOVA

A PERMANOVA is even more complex. It randomly samples the differences between groups and within groups then creates a histogram of the distances (which represent the differences) based on a distance matrix. It then calculates a **pseudo-F** value which represents the 'average' difference between the groups. From the histogram, it tries to determine where the pseudo-F was random and therefore there are no true differences or if it really represents a true pattern. Refer to this [resource](https://uw.pressbooks.pub/appliedmultivariatestatistics/chapter/permanova/#:~:text=PERMANOVA%20compares%20the%20variation%20between,importance%20of%20the%20grouping%20factor.) for the math around this. 

```
adonis2(cbind(Y1,Y2)~ X1*X2, dat=DATA)

```