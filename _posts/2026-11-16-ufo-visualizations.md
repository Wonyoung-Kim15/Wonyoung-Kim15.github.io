---
title: UFO Sightings Visualization
tags: [# Data Visualization, # UFO, # Altair]
style: fill
color: secondary
description: Visualizing UFO sightings over time and across countries.
---
<style>
  p {
    text-indent: 1.5em;
    line-height: 1.8;
  }
</style>

For this assignment, I used a UFO sightings dataset to create two visualizations with Python and Altair. I wanted to see **how the number of reported sightings changed over time and what kinds of UFO shapes were commonly reported in different countries.**

## 1. UFO Sightings Over Time

<div id="ufo-trend"></div>

For the first visualization, I created a **line chart** to see how UFO sightings changed over the years. I used the year for the x-axis and the number of sightings for the y-axis. Both are quantitative variables. I kept the default blue color because I was only showing one trend, so I didn't need different colors. Before making the chart, I converted the date column into a datetime format, extracted the year, and counted the sightings for each year using `groupby()`. I also added a tooltip to show the exact year and number of sightings when hovering over the line. I made the line slightly thicker to make it easier to hover over.

## 2. UFO Sightings by Shape and Country

<div id="ufo-shapes"></div>

For the second visualization, I wanted to see which UFO shapes were reported most often in different countries. I used a **bar chart** with UFO shapes on the x-axis (nominal) and the number of sightings on the y-axis (quantitative). I sorted the bars by the number of sightings so that the most common shapes would appear first. I used the default blue color because the bar heights already show the differences between shapes. To prepare the data, I removed rows with missing country or shape values and used `groupby()` to count sightings for each country and shape.

I also added a **dropdown menu** so users can select a country and see how the chart changes. The five countries are the United States, United Kingdom, Germany, Canada, and Australia. I noticed that `light` was the most commonly reported shape in all five countries, although the other shapes had different rankings. The y-axis scale changes depending on the selected country, which makes it easier to see the differences within each country. However, this also means that the bar heights should not be compared directly between countries.

## 3. Data and Code

- [Original UFO Sightings Dataset](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/ufo-scrubbed-geocoded-time-standardized-00.csv)
- [Python Notebook on GitHub](https://github.com/Wonyoung-Kim15/Wonyoung-Kim15.github.io/blob/main/python_notebooks/ufo_visualizations.ipynb)

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
vegaEmbed('#ufo-trend', '{{ "/assets/json/ufo_trend.json" | relative_url }}');
vegaEmbed('#ufo-shapes', '{{ "/assets/json/ufo_shapes.json" | relative_url }}');
</script>
