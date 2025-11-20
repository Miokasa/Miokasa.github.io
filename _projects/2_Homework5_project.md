---
name: Homework 5
tools: [Python, Altair, vega-lite]
image: assets/pngs/ufo.png
description: UFO Sightings Visualization Project for IS445
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# UFO Sightings Homework 5
This homework explores UFO sightings data using Python, Altair, and Vega-Lite. We created **two visualizations** of the dataset.  
## Plot 1: UFO Sightings Per Year

This plot shows the total number of UFO sightings reported per year. This helps identify long-term trends in how UFO reports increased or decreased over time. 

**Design choices:**  

- **Encoding types:** X-axis is the year (`year:O` for ordinal), Y-axis is the number of reports (`count:Q`).  
- **Color scheme:** No color variable used for this plot, points on the line are used to indicate individual years.  
- **Data transformations:** Grouped the original dataset by `year` using Pandas, removed rows with missing or zero coordinates.  

**Interactivity:**  
- Tooltips allow users to identify exact yearly counts without cluttering the chart.
- Tooltip shows the year and count for each point.  
- Users can hover over a point to see the exact count, which helps highlight trends and spikes in the data.  

<vegachart schema-url="{{ site.baseurl }}/assets/json/plot1.json" style="width: 100%"></vegachart>
---

## Plot 2: UFO Reports by Location

This plot shows UFO sightings on a map, with latitude vs. longitude, colored by UFO shape. By mapping longitude and latitude, we can see the geographic distribution of sightings.

**Design choices:**  

- **Encoding types:** X-axis is longitude (`longitude:Q`), Y-axis is latitude (`latitude:Q`), color is `shape:N`.  
- **Color scheme:** Each UFO shape gets a different color to distinguish patterns in sightings.  
- **Data transformations:** Filtered out rows with missing or zero latitude/longitude.  

**Interactivity:**  
- The state dropdown helps viewers filter the map and focus on specific geographic regions.
- Dropdown menu allows filtering sightings by state.  
- Hovering over points shows city, state, date, and shape.  
- `.interactive()` enables zooming/panning, making it easier to explore dense areas.  

<vegachart schema-url="{{ site.baseurl }}/assets/json/plot2.json" style="width: 100%"></vegachart>

---
## Data & Analysis

Below are links to the dataset and the Python notebook used to generate these plots:

<div class="left">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/Miokasa/Miokasa.github.io/blob/main/python_notebooks/Workbook2.ipynb" text="The Analysis" %}
</div>
