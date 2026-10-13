# ❄️ Alterra Snowmaking Utilities Budget

### Project

An analysis case study to determine budget variance for Alterra's snowmaking team at Snowshoe Mountain Resort. Stakeholders asked the following business questions:

1. How many days in the season had favorable weather for snowmaking?
2. What is the budget per kw/h to run all fan and snow guns?

### The Dataset 

The dataset was collected from multiple sources including [NCEI](www.ncei.gov) and [Weather Underground](www.wunderground.com). Columns include day, date and time of observation, temperature, humidity, the time difference between observations, and the amount of fresh snow that day in inches if any.

### Workflow & Methodology

Snowmaking is only possible when the temperature is at or below 27 degrees Fahrenheit and the humidity is between 30 and 60%. I began by filtering the data down to a subset of observations that matched this precise combination of conditions. To sum the total hours of these conditions, I created an additional datetime column from existing columns. Exploratory data analysis revealed that Snowshoe, WV received **128.4 inches** of natural snowfall during the '24-'25 season, and that there were only **74 hours** in the season where snowmaking was possible. I was unfamiliar with the range of snowmaking equipment at the resort, so I had to conduct some research to better understand the equipment inventory and the utility provider's rates. I translated the variables from that research into a Python function which converted kw/h and estimated the budget. Reported to stakeholders that with a minimum budget of **$208,825.62** the snowmaking team could run the inventory of pumps, compressors, and snow guns on days where weather conditions were favorable.

### Environment Setup

Anaconda Navigator 2.7.0
Jupyter Notebook 7.5.7
Python 3.13.9

```
# The notebook has some dependencies
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import sys
```

### How to Run the Analysis

```
# Change the file path and run all cells.
sn = pd.read_csv("C:/Users/Spencer Woo/Downloads/data(9).csv", header=1)
```

### Repository Layout

```
# 001_Alterra_Snowmaking_Utilities_Budget_Analysis
├── data/               # Raw and processed datasets
├── notebooks/          # Jupyter notebooks for EDA
├── src/                # Python scripts for cleaning and modeling
├── images/             # Visualizations used in the README
├── requirements.txt    # Library dependencies
└── README.md           # This file
```