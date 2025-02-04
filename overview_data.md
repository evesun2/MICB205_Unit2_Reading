# 1. The Importance of Working with Data

Data is the foundation of science. Based on data, we infer how aspects of the natural world work. In microbiology, for example, we use a combination of genetic sequencing data and lab-based growth assay data to determine what types of microbes grow in our gut and how they evolve overtime. 

The field of data science was born in response to the massive amounts of data that are collected due to advancements in technology. In microbiology, we have seen an influx of genetic sequencing data in the past few years due to the technological advancements making it easier and cheaper to sequence DNA. As humans, we can try to determine patterns in the data, but it would be quite exhausting to try to parse through so much data manually. So instead, we deploy coding in the form of data science to help us clean, analyze, and interpret large amounts of data. 

## How we go from a hypothesis to a concept

We can never truly collect 'perfect data'. Instead, data is always **representative**. What this means is that we collect **samples** from the environment hoping that they represent the population at large or the environment at large but they never truly do. But it is still useful to collect data because over time, as our confidence level in our data increases and patterns within the data became clearer, we eventually reach a point where we consider the hypothesis a concept. 

**Hypothesis**: inference of a biological model based on some clear rationale, testable but not yet a true representation of how the biological model/system works

**Concept**: our 'true' inference of how the biological model/system works based on years of strong and reliable data

In MICB 211, Foundations in Microbiology, we teach you about diauxic growth. This is the concept that bacteria are picky about what their sugar source or carbon source is. We know now (as a concept) that most bacterial species prefer glucose as their carbon source, which means that as long as there is glucose in the environment, they don't metabolize any other sugar until all the glucose is gone. 

In order to solidify this as a concept, scientists went through several iterations of hypotheses and data collection. In the data collected below, we see that when different combinations of sugars are used, *Escherichia coli* will always use up the glucose first. 


```{figure} https://upload.wikimedia.org/wikipedia/commons/b/b8/Monod%27s_Diauxic_growth.gif
```


## Process of Analyzing Data

In Unit 1, you learned a lot about how you can use R to *wrangle* and *tidy* data then you used ggplot to visualize the data in a way that allows you see patterns more clearly. In this unit, we want to combine them all into the process of **analyzing data**. Here is the general process:

Collecting the data is usually the first step but as pure data scientists, we don't do that in this course. Instead, we use datasets collected by other researchers. In this unit, we will be using the HIV dataset collected by [Colorado et al., 2024](https://pmc.ncbi.nlm.nih.gov/articles/PMC10837999/). 

```{note}
The dataset that we are working with is called a metadata table. Metadata includes information about the variables associated with a sample. In this case, fecal samples were collected in order to study the effects of HIV on the gut microbial species. Students from MICB 475 have helped us analyze the genetic data and annotated into our table! Thanks, MICB 475 students!
```

1. In this course, we will start our data analysis with wrangling and tidying activities. For data wrangling, this includes correcting for potential **confounding variables**. Confounding variables include any variables (columns) that you think could have an effect on what we are measuring besides the variable of interest. Tidying activities may include pivoting the data table, removing NA values, ensuring our columns of interest are the correct variable type (eg. numeric or character), and/or replacing values so they are more meaningful. 

2. After we have cleaned our table, we have to select the best way to visualize our data. In this unit, we will be using **boxplots** for all of our visuals because boxplots help us see not only the median of the data points but also the distribution. Check out this [resource](https://www.ncl.ac.uk/webtemplate/ask-assets/external/maths-resources/statistics/data-presentation/box-and-whisker-plots.html#:~:text=A%20box%20and%20whisker%20plot,than%20one%20boxplot%20per%20graph.) for more information about interpreting boxplots. 

3. Once we have visualized the data which will help **summarize** our findings, we proceed to selecting the right statistical tool in order to determine if what we are comparing is truly **significant** or not. 

This unit focuses on Statistics! Although statistics are very powerful in helping us answer research questions, it is not perfect. It will only give us a certain level of confidence in interpreting our data combined with our own critical thinking and understanding of science. 