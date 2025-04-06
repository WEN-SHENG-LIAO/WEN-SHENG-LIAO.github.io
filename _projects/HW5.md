---
name: HW5 - Jekyll Webpage
tools: [Python, Altair, Vega-Lite]
image: /assets/pngs/iSchool.png
description: Two interactive Altair visualizations showing government building construction years and usage types by county.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Plot 1: Building Construction Histogram by County

<vegachart schema-url="{{ site.baseurl }}/assets/plot/plot1.json" style="width: 100%; height: 500px;"></vegachart>

In plot one, I try to demonstrate the distribution of buildings (year constructed) in different counties. I select histogram as visualization since year is a numeric value. By viewing this plot, we could gain insight into whether particular counties have concentrated large-scale construction in certain eras. As for the data transformation, I apply `dropna()` to remove some NA values in columns County and Year Constructed to prevent missing data. Also, I do not filter year, since I am afraid some buildings' constructed years are not documented correctly in the original data — this may explain why some buildings are shown as being built in year 0. For the encodings, x-axis shows year as a continuous real-valued quantity so I use `Q` (quantitative); for y-axis, since I try to show total quantities of buildings, I utilize `count():Q` to bring out total count of data objects in the group. The interactivity part allows users to choose various counties and their specific visualization. I create `county_dropdown` and `selection` for the purpose of generating county dropdown.

---

# Plot 2: Building Usage Types by County

<vegachart schema-url="{{ site.baseurl }}/assets/plot/plot2.json" style="width: 100%; height: 500px;"></vegachart>

In plot two, since plot 1 shows the year of building construction, I think it is worth mentioning the buildings' usage. Therefore, I create plot 2 (bar graph) to reveal the distribution of building usage in different counties. It could serve as a visualization that allows policy makers to gain insight into differences in functional needs among counties. Compared to the last plot, I also add a transformation in data that filters the building usage after 1950 and apply `dropna()` to ensure a clean dataset. For the encoding parts, x-axis uses `count():Q` to show the number of buildings and y-axis uses nominal `N` (a discrete unordered category) to access different usages. Also, to show the trend, I apply `sort='-x'` to display the most common usage types at the top. The interactivity part is the same as plot 1 — it enables users to select different counties' data and update automatically. At last, both of my plots do not include a color scheme because colors would affect viewing data trends.

---

## Dataset and Python Notebook Links

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/WEN-SHENG-LIAO/WEN-SHENG-LIAO.github.io/blob/main/python_notebooks/Workbook.ipynb" text="The Analysis Notebook" %}
</div>


