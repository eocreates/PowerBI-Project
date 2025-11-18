## BloomGro Store Analysis
-----
Table of Contents
  * Project Overview
  * Business Problem
  * Aim of the Project
  * Data Sources
  * KPI Requirements
  * Key Insights
  * Dashboard Features
  * Results / Findings
  * Recommendations

## Project Overview
BloomGro is a retail brand specializing in grocery and household items.
This project provides a comprehensive Power BI analysis of BloomGro’s:
* Sales performance
* Customer satisfaction
* Inventory distribution
The goal is to uncover actionable insights and optimization opportunities using detailed KPIs, data modeling, and interactive dashboards.

## Business Problem
BloomGro management needs clarity on:
* Which product categories generate the highest revenue
* How outlet characteristics (size, location, establishment year) impact sales
* What drives customer ratings
* How inventory can be better distributed
* Which outlets or item types underperform

## Aim of the Project
To conduct a full Power BI analytics solution that:
* Measures key business KPIs
* Identifies high- and low-performing product groups
* Highlights outlet-level profit drivers
* Assesses customer sentiment through ratings
* Supports data-driven business strategy and optimization

## Data Sources
The primary data set used for this analysis is the ["BloomGro Dataset"](https://github.com/eocreates/PowerBI-Project/blob/main/BloomGroStore/BloomGro%20Grocery%20Data.xlsx) file

| Data Table       | 	Description            | 
| ----------- | ---------------------------- | 
| DSales Data     | 	Includes sales revenue, quantity, and item attributes  |
| Outlet Data	    | 	Includes outlet size, establishment year, location & type  |
|Item Data	   | Includes	item type, fat content, customer ratings  |

## KPI Requirements
1. Total Sales
Total revenue generated from all items sold.
```DAX
Total Sales = SUM(Sales[Sales_Amount])
```

2. Average Sales
The average revenue per transaction/item.
````DAX:
Average Sales = AVERAGE(Sales[Sales_Amount])
````

3. Number of Items
Total count of different items sold.
````DAX
Number of Items = DISTINCTCOUNT(Sales[Item_Identifier])
`````

4. Average Rating
Overall customer satisfaction score for purchased items.
````DAX
Average Rating = AVERAGE(Items[Rating])
````
DAX METRICS
* This is a calculated table that creates a list of KPI names and their measure references and allows switching between KPIs using a slicer/button
```DAX
Metric = {
    ("Total Sales", NAMEOF('BloomGro'[Total Sales]), 0),
    ("No of Sales", NAMEOF('BloomGro'[No of Sales]), 1),
    ("Avg Sales", NAMEOF('BloomGro'[Avg Sales]), 2),
    ("Avg Ratings", NAMEOF('BloomGro'[Avg Ratings]), 3)
}
```

## Dashboard
<a href="https://github.com/eocreates/PowerBI-Project/blob/main/BloomGroStore/BloomGro.png">
  <img src="https://github.com/eocreates/PowerBI-Project/blob/main/BloomGroStore/BloomGro.png" width="900">
</a>



