# 2. Features of Data 

## Predictor vs Response

When a researcher designs an experiment, if it's a hypothesis-testing experiment, it usually involves looking at a **predictor** and measuring the **response**.

Consider the example research question: Does *E. coli* grow better at different temperatures?

```{figure} https://akjournals.com/view/journals/066/50/2/full-066.2020.00213_f001.jpg
:height: 300px
```

**Predictor**: a variable that the researchers are able to change or control. In this example, temperature would be the predictor. This is often shown on the x-axis of a graph. 

**Response**: often a continuous variable that is measured in response to different predictor levels or categories. In this case, growth or growth rate is the response. This is often shown on the y-axis of a graph.

## Categorical vs Continuous

Once we know what our predictor and response are, we also have to ensure we know what types of variables we are working with.

**Categorical variable**: In R, this is usually `character` based where there are discrete groups. 

**Continuous variable**: In R, a continuous variable is usually numeric (classified as `double` or `integer`). This represents a variable that is number based. All responses that we analyze in this course will be continuous. 

## Parametric vs Non-parametric 

A very important characterization of data that is used in statistics is the shape of the data distribution itself. This is often visualized as a **histogram** which measures the frequency of each data point (for the response).

```{figure} https://i0.wp.com/techqualitypedia.com/wp-content/uploads/2021/01/Histogram.png?resize=666%2C542&ssl=1
:height: 300px
```

In R, you can make the histogram using your response column and the following command:

```
# data is your dataframe and column is your column name
hist(data$column)
```

The distribution of your response data usually follows two types of patterns: **parametric** or **non-parametric**. Parametric means that the distribution is bell-shaped and the majority of the data points cluster around the mean or median. Non-parametric data skews either to the left or right meaning the extreme points make up the majority of the observations. 

```{figure} https://media.springernature.com/lw685/springer-static/image/chp%3A10.1007%2F978-981-97-3385-9_4/MediaObjects/604071_1_En_4_Fig1_HTML.png
:height: 300px
```

```{note}
Textbook figures can be deceiving, data isn't always so clean that it looks perfectly bell shape or skewed. We have to use our own critical thinking to best evaluate whether data is parametric or not. We'll see some examples of this in class. 
```