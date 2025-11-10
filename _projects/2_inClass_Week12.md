---
name: Licenses Visualization
tools: [Python, Altair, Vega-Lite, HTML]
image: assets/pngs/licenses.png
description: Two interactive visualizations of business license data using Vega-Lite and Altair.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Plots using Altair, a few ways

<h2>Interactive Scatter Plot</h2>
<vegachart schema-url="{{ site.baseurl }}/assets/json/licenses.json" style="width: 100%"></vegachart>

## Write up
This visualization shows the relationship between **license types**, their **original issue year**, and their **status**. Each circle represents a license, positioned by its issue year on the x-axis and its type on the y-axis. Color encodes the **license status**, which allows viewers to easily compare how active or inactive licenses are distributed across years and types. The main encodings used are *x = temporal*, *y = categorical*, *color = nominal*, and *size = fixed*. I chose a categorical color scheme because status is a discrete variable that benefits from contrasting hues. On the data side, I converted the issue dates into **year values** to make trends across time more interpretable. The visualization includes a **dropdown filter** that lets users select a specific license type, which makes it easier to focus on patterns for a single category.

<h2>License Issue Histogram</h2>
<vegachart schema-url="{{ site.baseurl }}/assets/json/licenses_hist.json" style="width: 100%"></vegachart>

## Write up
The second visualization summarizes how many licenses were issued per year, grouped by **license status**. The x-axis represents the **year of issue**, and the y-axis shows the **count of licenses**. Color once again represents the **license status**, using the same categorical color palette for consistency between plots. This bar chart uses *x = temporal*, *y = quantitative (count)*, and *color = nominal*. I aggregated the data by year to simplify comparisons over time and to show how licensing activity changes. Although this chart is static, it complements the first one by providing an overview of temporal trends.


<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>

