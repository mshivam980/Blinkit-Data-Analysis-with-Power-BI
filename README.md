# Blinkit-Data-Analysis-with-Power-BI-Dashboard

Dashboard Link: https://github.com/mshivam980/Blinkit-Data-Analysis-with-Power-BI/blob/main/Blinkit%20data%20analysis%20Dashboard.pbix

## Problem Statement - 8,523 Rows Dataset

Blinkit seeks to deepen its understanding of sales performance and customer behavior across its outlets. Key objectives include analyzing sales trends, customer preferences, and delivery efficiency across product types, fat content, and outlet characteristics. By using Power BI, Blinkit aims to gain actionable insights to optimize inventory, tailor product offerings, and improve customer satisfaction.

https://github.com/user-attachments/assets/4b97e188-3043-4ac3-a912-00676103d08b

### Key Requirements for the Dashboard
#### 1) Sales and Product Performance

- **Total Sales by Product Category**: Display total sales for each product category, with a breakdown by fat content to understand customer preferences.
- **Top-Selling Products**: Identify the top-performing items based on total sales, helping prioritize inventory and promotional efforts.
- **Sales by Item Type**: Use a bar chart to track item types’ performance, with additional insights on how KPIs like average sales and ratings vary with fat content.


#### 2) Customer Purchase Behavior

- **Sales Segmentation by Fat Content**: Show total sales segmented by fat content (e.g., low fat, regular), helping identify customer health preferences.
- **Sales by Outlet Type and Size**: Visualize sales across different outlet types and sizes, providing insights into how location and establishment type impact sales.
- **Geographic Distribution of Sales**: Use map or funnel charts to display sales by location type (Tier 1, Tier 2, Tier 3), revealing regional demand patterns.


#### 3) Outlet Performance Analysis

- **Sales by Outlet Establishment Year**: Analyze sales trends by the age of each outlet, using line charts to observe performance over time.
- **Sales by Outlet Size**: Use pie or donut charts to assess how outlet size (small, medium, large) correlates with total sales, helping to optimize store format planning.
- **All Metrics by Outlet Type**: Consolidate total sales, average sales, number of items sold, and average ratings by outlet type for a holistic view of each outlet’s performance.

#### 4) Customer Satisfaction Metrics

- **Average Ratings by Product and Outlet Type**: Provide average ratings across categories and outlets, identifying areas to enhance the customer experience.
- **Delivery Efficiency**: Analyze delivery times and satisfaction ratings to evaluate delivery performance across different regions and outlet types.


### Steps followed 

- Step 1: Load data into Power BI Desktop. The dataset is in CSV format.
- Step 2: Open Power Query Editor. Under the View tab in the Data Preview section, enable "Column Distribution," "Column Quality," and "Column Profile."


- Step 3: By default, profiling is limited to 1,000 rows. Change it to "Column profiling based on the entire dataset" for more accurate insights.

 
- Step 4: Check for errors and empty values. No issues were found except in the "Item Fat Content" column, which had inconsistent field names.

 
- Step 5: Standardize the "Item Fat Content" values. Replace "reg" with "Regular" and "LF" with "Low Fat."

 
- Step 6: Create calculated measures for KPIs to be later used as parameter:
Total Sales: Sum of individual item sales.


           Total Sales = 
                SUM(Sheet1[Sales])
Average Sales: Average of individual item sales.

           Average Sales = 
                AVERAGE(Sheet1[Sales])
Total Items Sold: Count of items, capturing inventory breadth.

           No of Items = 
                COUNT(Sheet1[Item Identifier]) 
Average Ratings: Average customer rating.

           Average Ratings = 
                AVERAGE(Sheet1[Rating]) 
- Step 7: Create a field parameter for dynamic KPI selection in visualizations.

           Parameter = {
                ("Total Sales", NAMEOF('Sheet1' [Total Sales]), 0),
                ("Average Sales", NAMEOF('Sheet1'[Average Sales]), 1),
                ("Average Ratings", NAMEOF('Sheet1'[Average Ratings]), 2),
                ("No of Items", NAMEOF('Sheet1'[No of Items]), 3)
                }
#### Visualizations by KPI


- Step 8: C Create a Donut Chart for KPI by Item Fat Content.

1. Add a Donut Chart to the report canvas.
2. Drag the Parameter into Values and "Item Fat Content" into Legend.
3. Format with distinct colors per KPI and enable data labels for clarity.



- Step 9: Create a Stacked Bar Chart for KPI by Item Type.

1. Add a Stacked Bar Chart to the canvas.
2. Use the Parameter in Values and "Item Type" in Axis.
3. Apply a color scheme per product type; enable tooltips and labels.

 
- Step 10: Create a Clustered Bar Chart for KPI by Outlet Location Type.

1. Use the Parameter in Values.
2. Place "Outlet Location Type" in Axis, "Item Fat Content" in Legend.
3. Assign colors per fat content type; enable legend and data labels.


- Step 11: Add a Slicer for KPI Selection.

1. Place the Parameter in the Slicer for user selection across visuals.
2. Confirm dynamic updates to Item Fat Content, Item Type, and Outlet Location Type charts.

#### Outlet-Wise Visualizations

- Step 12: Line Chart for Total Sales by Outlet Establishment Year.

1. Use "Outlet Establishment Year" in Axis and "Total Sales" in Values.
2. Format with clear data labels and a contrasting line color.



- Step 13: Donut Chart for Total Sales by Outlet Size.

1. Place "Outlet Size" in Legend and "Total Sales" in Values.
2. Format with distinct colors and data labels showing percentage of total sales.



- Step 14: Funnel Chart for Total Sales by Outlet Location Type.

1. Use "Total Sales" in Values and "Outlet Location Type" in Group.
2. Assign unique colors per location type; adjust labels for readability.

- Step 15: Matrix Table for All Key Metrics by Outlet Type.

1. Use "Outlet Type" in Rows and KPIs (Total Sales, Average Sales, etc.) in Columns.
2. Format with adjusted column widths, text alignment, and color highlights.

#### Additional Interactive Elements
- Step 16: Add KPI Cards for Overview.

1. Create Card visuals for Total Sales, Average Sales, No of Items, and Average Ratings.
2. Format with cohesive colors and centered text for easy readability.



- Step 17: Add Slicers for Interactive Filtering.

1. Add Slicers for Established Year, Outlet Type, and Outlet Size.
2. Place slicers for easy access and confirm they update visuals correctly.

- Step 18: Final Dashboard Formatting.

1. Apply a consistent color scheme and add clear titles per section.
2. Adjust data filters, interactions, data labels, and tooltips for smooth user experience.


 - Step 32 : Publish to Power BI Service.

1. Publish the dashboard to Power BI Service.
2. Set access permissions for team members and stakeholders.
3. Test all slicers and interactions to confirm functionality online.


 
 
![image](https://github.com/user-attachments/assets/65bc8662-dc11-4b35-8742-f73524c8006a)


# Snapshot of Dashboard (Power BI Service)

![image](https://github.com/user-attachments/assets/466cd989-1709-4cce-86cb-e83713681e99)


 # Report Snapshot (Power BI DESKTOP)

 
![image](https://github.com/user-attachments/assets/0abcab50-3cb5-4b75-8d41-c0e64cd44424)



# Insights 

Report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Sales and Product Trends


Sales Dominance by Item Fat Content:

- The majority of sales are generated from "Low Fat" items, accounting for 64.6% of total sales, compared to 35.4% from "Regular" fat content items. This could indicate a consumer preference for healthier, low-fat options in grocery purchases.
Performance by Outlet Type:

- Supermarket Type 1 has the highest total sales, with $787,550, followed by Grocery Stores with $151,939. This shows that larger retail formats such as Type 1 generate significantly more revenue 
Item Type Sales Insights:

- Certain categories, including Fruits & Vegetables and Snack Foods, are leading in sales, each generating around $0.18M. This highlights high consumer demand in perishable and snack categories, likely driven by frequent purchases.

### [2] Location-Based Sales Trends
Outlet Location Type Impact on Sales:

- Outlets located in Tier 3 locations lead with $472K in total sales, while Tier 2 and Tier 1 outlets trail at $393K and $336K, respectively. This may suggest that stores in less urbanized areas (Tier 3) are generating more revenue, possibly due to lower competition or higher dependence on local stores for groceries.
Outlet Size and Sales Distribution:

- Medium-sized outlets contribute the most to total sales at 42.27%, followed by small and large outlets at 37.01% and 20.72%, respectively. This implies that medium-sized stores may offer an optimal balance of product variety and convenience, appealing to a broader customer base.
### [3] Temporal Sales Insights

Sales Growth Over Time by Establishment Year:
- The trend of Total Sales by Outlet Establishment Year shows a steady increase over recent years, peaking around the year 2020. This likely reflects business expansion efforts or increased grocery demand during that period, potentially due to shifts in consumer behavior during the pandemic.

### [4] Customer Engagement and Satisfaction
Average Ratings Stability Across Outlets:
- The average rating across outlet types remains consistent, around 3.9 out of 5. This uniformity suggests stable customer satisfaction across different types of stores, which may indicate standardized service quality.
### [5] Visual Summary of Key KPIs
        Total Sales: $1M
        Average Sales per Item: $141
        Total Items Sold: 8,523
        Average Customer Rating: 3.92
        
        
# Conclusion
The data suggests that Blinkit’s customer base is heavily inclined towards healthier options (Low Fat) and relies more on medium-sized outlets, particularly in Tier 3 locations. The consistent average ratings indicate that customer satisfaction remains steady across outlet types, hinting at the effectiveness of standardized service practices across different store formats. Expansion efforts and a spike in sales in recent years reflect an evolving market presence and increased reliance on grocery delivery services.


