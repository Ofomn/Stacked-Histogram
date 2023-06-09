# Creating a Stacked Histogram
---


### Introduction

The dataset I would be using is the *Insurance* dataset which would be imported from the `pycaret.dateset`.

I would be using a stacked chart for our visualization.

A stacked chart is a type of bar chart that displays the relationship and structure of a restricted amount of variables through duration, whether they be relative or absolute.

For  this project, I would be using the built-in `hist()` function from pandas to plot a histogram for age, BMI, and charges against the target variable which is **Insurance Charges** for each person.


## Data

The data used originates from the book [Machine Learning with R](https://www.amazon.com/Machine-Learning-R-Brett-Lantz/dp/1782162143/ref=as_li_ss_tl?ie=UTF8&linkCode=ll1&tag=learnds-20&linkId=acc9debcffa9ec9b8dc01374ead56eaf&language=en_US) by Brett Lantz, and it contains health insurance information.

Below are the columns in the dataset:

💡 Age

💡 Sex:  female, male.

💡 BMI: Body mass index.

💡 Children: Number of children covered by health insurance / Number of dependents.

💡 Smoker: If the person smokes or not.

💡 Region: Northeast, Southeast, Southwest, Northwest.

💡 Charges: Individual medical costs billed by health insurance

----

## Steps:

```bash python

from pycaret.datasets import get_data

data = get_data('insurance')

import matplotlib.pyplot as plt
import seaborn as sns

```

```bash python

data.info()

```


```bash python

sns.set_style('darkgrid')
colors = ['#851836', '#EDBD17', '#0E1428', '#407076', '#4C5B61']
sns.set_palette(sns.color_palette(colors))

```



```bash python

categorical = ['sex', 'children', 'smoker', 'region']

fig, axs = plt.subplots(2, 2, figsize=(20,10))

for variable, ax in zip(categorical, axs.flatten()):
  sns.histplot(data, x='charges', hue=variable, multiple='stack', ax=ax)

```



## Visualization

![viz](https://user-images.githubusercontent.com/122539866/230698823-10054ef0-ddb6-4016-934e-c8c6495dc8df.png)

----

## [View My Jupyter Notebook](https://nbviewer.org./github/Ofomn/Stacked-Histogram/blob/f0c4b6ca83b55013f89ab65095202aa4e0899920/DataViz.ipynb)

----

## Technologies Used
- [Installing Pycaret](https://pycaret.gitbook.io/docs/)

- [matlotlib](https://matplotlib.org/)

- [Seaborn](https://seaborn.pydata.org/)

## Installation and Usage
- It is requires that the matplotlib and seaborn modules are installed. These libraries are imported into the module.

---

&copy; 2023 Ofomnbuk

<!-- markdownlint-enable -->

