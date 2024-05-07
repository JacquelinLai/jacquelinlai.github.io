---
name: Final Project
tools: [Python, HTML, vega-lite]
image: assets/pngs/World_map.png
description: This is the part 3 of Team 11's Final Project
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---
# Part 1: Intro of Dataset
The name of the dataset is "oil-and-gas-refining_emissions_sources.csv".

We obtained it from the Climate TRACE website (https://climatetrace.org/data) under "Fossil Fuel Operations".

We located the license of the dataset in the about_the_data.pdf file within the ABOUT_THE_DATA folder. The document states that "all Climate TRACE data is freely available under the Creative Commons Attribution 4.0 International Public License".

The file size is 12.5MB and there are 27360 items.

# Part 2: Data Cleaning and Analysis
In this section, we conducted a thorough data cleaning and analysis process to prepare our dataset for further exploration. One of the initial steps involved dropping columns that were deemed irrelevant for our analysis. These columns included 'other1', 'other2', 'other3', and so on, along with their corresponding definition columns like 'other1_def', 'other2_def', and so forth. These columns were not essential to our analysis objectives and were thus removed to streamline our dataset.

Following the column removal, we focused on extracting relevant information from the remaining data. Specifically, we extracted the year component from the 'date' column, as it was the only temporal information required for our analysis. This step allowed us to simplify the dataset structure while retaining the necessary temporal context for our analysis.

Additionally, we addressed any missing or null values within the dataset. Although the number of rows with null values was relatively small, approximately 50 to 60 rows, we opted to drop these rows to ensure the integrity and accuracy of our analysis. Removing these rows helped us maintain a clean and consistent dataset, which is crucial for drawing meaningful insights and making informed decisions based on the data.

Overall, through these data cleaning and preprocessing steps, we have prepared a refined dataset that is well-suited for further analysis and exploration. The streamlined structure, devoid of unnecessary columns and cleaned of missing values, sets a solid foundation for conducting insightful data analysis and deriving valuable insights.

# Part 3: Data Visualization

#### Description of Visualization: Graph 1: Stacked Barchart

We first plotted the comprehensive gas emissions for the countries with the top 10 emissions around the world. This is in the form of a stacked bar chart in order to be able to see the distribution of the different types of gases.

<vegachart schema-url="{{ site.baseurl }}/assets/json/Graph_1.json" style="width: 100%"></vegachart>

#### Description of Visualization: Graph 2: Barchart

To explore this concept further, we made an interactive bar chart to select the year to focus on. This shows the gas emissions of the same top 10 countries, separated by gas types, which are side by side. 

Interactivity: 
- Select the year from the dropdown
- Reference the key to identify the color-coded gas types

Insights: 
- USA and China are in the lead for gas emissions every year
- Carbon dioxide is so significant that N2O and CH4 are not even visible on this graph

#### Description of Visualization: Graph 3: Line Chart

This visualization better displays the pattern of gas emissions over time. These are separated by gas type and country.

Interactivity: 
- Select the gas type from the dropdown
- Reference the key to identify the color-coded countries

Insights: 
- As expected, the gas emissions for every type have generally increased over the years. 
- USA and China are in the lead every year
- There are some interesting dips that could be investigated further

#### Description of Visualization: Graph 4: World Map

To better visualize the geographic distribution of gas emissions, we have plotted this onto a world map. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/Graph_4.json" style="width: 100%"></vegachart>

Interactivity: 
- Select the gas and the year from the dropdown
- The size of the bubbles is proportional to the emissions at that specific latitude and longitude
- The color of the bubbles is based on the gas type

Insights: 
- Over a period of time, CH4 was decreasing in Australia, so there may have been 1 or 2 industries that have shut down.
- There are a lot of large bubbles
in the USA, which matches the insights from the other visualizations

#### Description of Visualization: Graph 5: World Map

This graph is the same as the previous graph but was implemented using plotly rather than altair, as altair doesn't support zoom/pan functionality for world maps. However, the functionality of the results is nearly identical.

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/adlthya/adlthya.github.io/main/_data/oil-and-gas-refining_emissions_sources.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/JacquelinLai/jacquelinlai.github.io/blob/main/python_notebooks/Team_11_Final_Project.ipynb" %}
</div>