# 3. Summarizing data

In Unit 1, you learned a key function in R that makes it easy to determine information about your data including the mean/average, median and standard deviation. 


Let's review some of these:
- **average or mean**: This attempts to predict where the majority of values fall (ie. a middle value). It is a sum of all values divided by the size of the dataset (sample size). However, it is sensitivity to the extremes meaning that a very low or very high value in the mix will skew the average downwards or upwards respectively. 

$average = sum (values) /samplesize$

- **median**: The 'true' middle value. Once you arrange all the values, this is the value that directly represents the middle value of the distribution but it doesn't necessarily mean that most of the value align here. Although unlike the mean which is sensitive to extremes, the median is not. However, unlike the mean, it doesn't quite predict where the majority of values fall. 

- **standard deviation**: This calculates generally how much variation you have in your data. A standard deviation of zero represents no variation which means all data points are exactly the same (which is rarely true). Take a minute right now to think about what factors cause data to vary so much. As per the equation below, the standard deviation takes in account all the differences between values relative to the mean, and the sample size in order to determine how much variability we have. If you add and subtract the standard deviation from the mean, you get a range of extremes within your data. This is different from standard error which is a fixed calculation of error that may contribute to variation in your data.

```{figure} https://www.nlm.nih.gov/oet/ed/stats/img/SDFormula.png
:height: 100px
```

The sigma value  ($\sigma$) represents the standard deviation. x are the values and $ \mu $ is the mean. 

## Choosing the right way to visualize

I don't know about you but I prefer everything in a more visual way. Instead of looking a raw numbers, I prefer to look at colorful graphs. I think it's easier for my brain to interpret patterns. But, as scientists in training, we have to make sure we pick the right way to visualize. As mentioned before, in this unit, we visualize everything as **boxplots** because the type of data we work with is ideal for boxplot visualization. But regardless, let's consider some characteristics that will help you determine the best way to visualize.

What is the **relationship** that you want to visualize. Is it between discrete groups? Is it over the course of time? 

For time-based visualizations, a line graph is most ideal as it represents the linear course of the patterns we are trying to visualize. This could include bacterial growth over time.

```{figure} https://revopsteam.com/wp-content/uploads/sites/7/2023/05/rev-types-of-data-visualization-infographics-04-1024x737.png
:height: 250px
```

But maybe you care about the **correlation** instead where the pathway isn't very smooth but you can infer a linear relationship. Then a scatterplot which shows the varying data points with a best fit line would be ideal. A line moving upwards refers to positive correlation and a line moving downwards is a negative correlation. 

```{figure} https://revopsteam.com/wp-content/uploads/sites/7/2023/05/rev-types-of-data-visualization-infographics-01-1-1024x737.png
:height: 250px
```

Bar plots are very commonly used because they are often easy to interpret, but we have consider the requirement for a bar plot before we use. Bar plots should only be used if the numbers represented on the y-axis are continuous. This is why the bar goes upwards from zero. This means that the response being measured can be zero or 100 or more. For non-cumulative numerical values like your student number where we don't expect it to change over time, a bar plot is not the ideal representation. 

To interpret the bar plot, consider that the tops of each bar represent the mean of each group. 

```{figure} https://revopsteam.com/wp-content/uploads/sites/7/2023/05/rev-types-of-data-visualization-infographics-06-1024x737.png
:height: 250px
```

In this unit, although a lot of our proposed research questions could be answered using bar plots, we are going to use the superior boxplot! Why does Evelyn think it's superior? Well, for 1, I have been told by many researchers in the field that it is becoming the predominant way of visualizing continuous data. Two, it looks cleaner than a bar plot where error bars can extend in weird ways when added. Three, you get a better sense of what the 'shape' of the data is in terms of distribution of values and it also takes in consideration potential outliers which often skew the mean (tops of the bar plots). So because I do like it better, we are using it!

```{figure} https://revopsteam.com/wp-content/uploads/sites/7/2023/05/rev-types-of-data-visualization-infographics-10-1024x737.png
:height: 250px
```