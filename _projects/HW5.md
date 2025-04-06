---
title: Homework 5 - HW5: Jekyll Webpage
layout: project
excerpt: "Two interactive Altair visualizations showing government building construction years and usage types by county."
date: 2025-04-05
tags: [Python, Altair, Vega-Lite]
image: /assets/pngs/iSchool.png
---

## Plot 1: Building Construction Histogram by County

<iframe src="/assets/plots/plot1.html" width="700" height="450"></iframe>

In plot one, I try to demonstrate the distribution of buildings(year constructed) in different counties. I select historgram as visualization since year is numeric values. By viewing this plot, we could gain insight of whether particular counties have concentrated large-scale construction in certain eras. As for the data transformation, I apply dropna.() to remove some NA values in columns County and Year Constructed to prevent missing data; also, I do not filter year since I am afraid some buildings' consturcted year do not document correctly in the original data and this is the reason some of the buildings built in 0 year. For the encodings, x-axis shows year is a continuous real-valued quantity so I use Q(quantitative); for y-axis, since I try to show total quantities of buildings; thus, I utilize count():Q to brings out total count of data objects in the group. The interactivity part allow users to chose various counties and their specific visualization. I create county_dropdown and selection for the purpose of generating county dropdown.
---

## Plot 2: Building Usage Types by County

<iframe src="/assets/plots/plot2.html" width="700" height="450"></iframe>

In plot two, since plot 1 show the year of building constructed, I think is worth mentioning the buildings' usage. Therefore, I create plot 2 (bar graph)to reveal the distribution of building usage in different counties. It could serve as the visualization that allow policy makers to gain insight of observing the differences in functional needs among counties. Compared to last plot, I also add a transformation in data that filter the building usage after 1950 and apply dropna.() to ensure a clean dataset. For the encoding parts, x-axis uses count():Q to show numbers of buildings and y-axis uses nominal N(a discrete unordered category to gain access of different usages. Also, to show the trend, I apply sort'-x' that display the most common usage types at the top. The interactivity part is same with plot 1 that able users to select different counties' data and update automatically. At last, both of my plots do not set up color scheme this is because colors would affect viewing data trends.)
---

## Data and Notebook Links

- [The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv)  
- [The Analysis Notebook](https://github.com/WEN-SHENG-LIAO/WEN-SHENG-LIAO.github.io/blob/main/python_notebooks/Homework5.ipynb)
