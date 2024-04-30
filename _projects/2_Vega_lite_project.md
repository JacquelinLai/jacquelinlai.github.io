---
name: Vega Lite Project
tools: [Python, HTML, vega-lite]
image: assets/pngs/bldg.png
description: This is a project that uses altair and vega-lite for interactive viz!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Introduction of the project

The purpose of this project is to get some more practice developing on the web, specifically exporting plots made in Python + altair + vegalite to my github repository.

We can use a vegachart HTML tag like so:

```
<vegachart schema-url="{{ site.baseurl }}/assets/json/my_chart.json" style="width: 100%"></vegachart>
```

<vegachart schema-url="{{ site.baseurl }}/assets/json/my_chart.json" style="width: 100%"></vegachart>


The code I provided utilizes several design choices to create a visualization:

**Encoding Types:**

- **X-axis (Quantitative):** I am using a quantitative encoding for the x-axis by setting `x='Year Acquired'`. This assumes the "Year Acquired" column contains numerical data representing years. Altair will treat these values as a continuous scale for positioning data points on the x-axis.
- **Y-axis (Quantitative):** Similarly, the y-axis uses a quantitative encoding with `y='Square Footage'`. This assumes the "Square Footage" column contains numerical values representing the area of buildings. These values will be used on a continuous scale for the y-axis.

**Color Scheme (Absent):**

The code doesn't explicitly define a color scheme. By default, Altair assigns a sequential color scheme to line charts. This means the line will likely be colored using a gradient, with colors transitioning along the line's path. The specific default color scheme might vary depending on the Altair version you're using.

**Data Transformations:**

The code performs a data transformation during DataFrame creation:

- **Removing Duplicate Years (Optional):** I use `set` on the "Year Acquired" column before calculating square footage sums. This assumes you only want to consider unique years in the visualization. If all years are relevant, you can remove this step.

**Justifications:**

- **Quantitative Encodings:** Using quantitative encodings for both axes makes sense because you're dealing with numerical data for years and square footage. This allows Altair to display the data along continuous scales, enabling visualization of trends or relationships over time.
- **Default Color Scheme (Optional):** While the code doesn't define a specific color scheme, the default sequential scheme can be suitable for this visualization. It can help visualize the progression of total square footage across years.

**Additional Considerations:**

- I could explore customizing the color scheme using Altair's `color` channel to highlight specific aspects of the data. For example, you might use different colors to represent different building types if that information is available.
- Consider adding labels or titles to the axes for better readability.

Overall, the code effectively uses Altair to create a basic line chart that visualizes the relationship between year and total square footage. I can further enhance the visualization by employing additional design choices and data transformations.




<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>

