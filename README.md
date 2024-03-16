# Optimizing Product Mix and Market Strategy for Drinko's FMCG Business
![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346.svg?style=for-the-badge&logo=Microsoft-Excel&logoColor=white) 
## 1- Executive Summary:
The FMCG landscape is highly competitive, demanding constant adaptation and optimization. In this case study, we searched into Drinko's extensive dataset, employing pivot tables to unlock accurate insights into sales performance, profitability, client segmentation, and brand analysis. The goal is to guide Drinko towards informed decisions that enhance its product offerings and market strategy.

## 2- Introduction:
Drinko, a prominent player in the Fast-Moving Consumer Goods (FMCG) industry, faces the dynamic challenges of a competitive market. In the pursuit of sustained growth, Drinko recognizes the pivotal role of data analytics in optimizing its product mix and market strategy. This case study embarks on a comprehensive exploration of Drinko's FMCG business, leveraging detailed data encompassing key dimensions such as brands, clients, client types, months, years, sizes, and packs. By employing powerful pivot tables, we aim to unearth nuanced insights that will empower Drinko to make informed decisions, enhance product offerings, and maximize profitability in the ever-evolving FMCG landscape.

## 3- Objectives:
- Analyze brand and product performance using pivot tables to refine Drinko's product portfolio, focusing on top-performing brands, sizes, and packs.
- Tailor Marketing Strategies: Utilize client segmentation insights to tailor marketing strategies, aligning offerings with client preferences to enhance market positioning and strengthen client relationships.
- Boost Profitability: Optimize profitability by examining net sales, profit margins, and cost breakdowns through pivot tables, identifying opportunities to enhance revenue and manage costs effectively.


# Data Overview:

## Dataset Columns:
- **Month**: Indicates the month of sales (01-12).
- **Year**: Represents the year of sales (2015, 2016).
- **Material Number**: Unique identifier for each product.
- **Material Description**: Descriptive information about the product.
- **Brand**: Brand names include Buratino, Crocky, Dundy, Evan, Pit Bull, Zumba.
- **Size**: Represents the size of the product (1.25L, 1.5L, etc.).
- **Pack**: Denotes the packaging size (12X, 15X, etc.).
- **Client**: Different clients include Albertsons, Costco, HEB, etc.
- **Client Type**: Categories of clients include Big-box, Discounters, Grocery, Supermarkets.
- **Volume**: Quantity of units sold.
- **Gross Sales**: Total income generated from sales.
- **Discounts**: Differentiated discounts based on business volume.
- **Net Sales**: The sum of a company's gross sales minus its returns, allowances, and discounts.
- **Cost of Goods Sold (COGS)**: The sum of all direct costs associated with making a product.
- **Distribution**: Transportation expenditure for product delivery.
- **Warehousing**: Cost for keeping items in the company's warehousing facilities.

## Analysis (with Pivot Tables):



### Step 1: Data Setup
Ensure the dataset is well-structured with columns such as Material Number, Period, Brand, Size, Pack, Client, Client Type, Volume, Gross Sales, Discounts, Net Sales, Cost of Goods Sold, Distribution, and Warehousing. Create new columns named “Month" and “Year” to extract data from Period, using Right() and Left() functions.

![image](https://github.com/Abdelrahman-Hatem/Excel-Project/assets/60587162/e7da6913-6524-4d0d-97f9-42eaef629114)

![image](https://github.com/Abdelrahman-Hatem/Excel-Project/assets/60587162/6281cf64-3a0c-4e99-a69d-a3b551b66e46)



### Step 2: Pivot Table Construction

i Create a pivot table with the following structure:

**Row Labels**: Categorical information about the Brand field.
**Sum of Volume**: The total volume sold for each category.
**Sum of Gross Sales**: The total gross sales for each category.
**Sum of Discounts**: The total discounts applied for each category.
**Sum of Net Sales**: The total net sales (after discounts) for each category.
**Sum of Cost of Goods Sold**: The total cost incurred to produce the goods for each category.

This structure enables quick analysis and comparison of the performance of different categories based on volume, sales, discounts, net sales, and cost of goods sold for every month.

![image](https://github.com/Abdelrahman-Hatem/Excel-Project/assets/60587162/43c12b1d-b431-490c-befb-1b0e0cfeb722)


![image](https://github.com/Abdelrahman-Hatem/Excel-Project/assets/60587162/ee91c68c-e93c-4e7e-a6ec-094bfb7cce85)



### Step 3: Key Performance Indicator (KPI) Definition

Key Performance Indicators (KPIs) have been defined for the years 2015 and 2016.

![image](https://github.com/Abdelrahman-Hatem/Excel-Project/assets/60587162/4aca72ad-2c59-4a32-8bbe-a6f4b402e5b2)


#### KPI Definition:

1. **Volume**:
   - Represents the quantity of units sold.
   
2. **Gross Sales**:
   - Total sales revenue before any deductions.
   
3. **Discounts**:
   - The amount deducted from gross sales due to client discounts.
   
4. **Net Sales**:
   - Gross Sales minus Discounts, representing the actual revenue.
   
5. **Cost of Goods Sold (COGS)**:
   - The total cost incurred to produce the goods sold.
   
6. **Gross Profit**:
   - Calculated as Net Sales minus COGS, indicating the profit after deducting production costs.
   
7. **Distribution**:
   - The expenditure incurred for transporting products to clients.
   
8. **Warehousing**:
   - The cost associated with storing products in the company's warehousing facilities.
   
9. **Full Delivered Margin (FDM)**:
   - Represents the overall profit margin after considering all costs associated with production, distribution, and warehousing. Calculated as (Net Sales - COGS - Distribution - Warehousing).

#### KPIs:

1. **Gross Profit %**:
   - Calculated as (Gross Profit / Net Sales) * 100.
   - Indicates the percentage of revenue retained after accounting for production costs.
   
2. **FDM % (Full Delivered Margin %)**:
   - Calculated as (Full Delivered Margin / Net Sales) * 100.
   - Represents the percentage of revenue retained after considering all costs, including production, distribution, and warehousing.

#### Note:
- All monetary values are denominated in USD (United States Dollars) and presented in thousands (USD in 000s) for simplicity and readability.



### Step 4: Extracting Data with GETPIVOTDATA

The GETPIVOTDATA function is utilized to extract specific information from the pivot tables. The syntax for the GETPIVOTDATA function is as follows:

GETPIVOTDATA(data_field, pivot_table, [field1, item1, field2, item2], ...)

![image](https://github.com/Abdelrahman-Hatem/Excel-Project/assets/60587162/24306915-123b-493b-a7e9-309df7499efd)


```excel•	=GETPIVOTDATA("Sum of "&$B5,'Pivot Table'!$A$3,"Year",C$3)/1000 ```

-	This formula is extracting data from a pivot table. Let's go through each part:

1. **GETPIVOTDATA**: This is an Excel function used to extract data from a pivot table.

2. **"Sum of "&$B5**: Specifies the data field to retrieve. It concatenates the text "Sum of " with the content of cell B5. This is typically the field name in the pivot table.

3. **'Pivot Table'!$A$3**: Specifies the location of the pivot table and the reference point for data extraction. In this case, it refers to cell A3 in the sheet named "Pivot Table".

4. **"Year",C$3**: This part specifies a filter to apply to the pivot table. It filters by the "Year" field and uses the value in cell C3 for that filter. This allows for dynamic filtering based on the value in cell C3.

5. **/1000**: Finally, the division by 1000 indicates that the result should be divided by 1000. This might be used to convert the result from a larger unit (e.g., grams or milliliters) to a smaller unit (e.g., kilograms or liters).


### Step 5: Adding Interactive Slicers

Adding slicers for Month, Pack, Client Type, Brand, Client, and Size can enhance the interactivity and usability of the user interface, allowing users to dynamically filter and analyze data based on their preferences.

Slicers provide a visual and intuitive way to filter data in pivot tables, enabling users to easily narrow down their focus and explore specific subsets of information. By incorporating slicers into the Excel workbook, users can interactively adjust filters and instantly see the corresponding changes in the displayed data.

![image](https://github.com/Abdelrahman-Hatem/Excel-Project/assets/60587162/00f13f7c-0e2e-4759-901c-6c0873828d2b)


### Step 6: Conclusion:

Drinko's FMCG analysis for 2015-2016 reveals a decline in volume and net sales, which has impacted gross profit and key margins. While the company demonstrates effective cost management, it faces challenges related to discounting strategies and a decline in sales volume.

To address these challenges and ensure sustained profitability in a changing market, Drinko must undertake the following actions:

1. **Optimize Product Mix**: Evaluate and adjust the product mix to align with changing consumer preferences and market demands. This may involve discontinuing underperforming products and introducing new offerings to capitalize on emerging trends.

2. **Explore Market Expansion**: Identify opportunities for market expansion, both geographically and within existing market segments. This could involve targeting new customer segments or exploring distribution channels to reach untapped markets.

3. **Review Discounting Strategies**: Conduct a comprehensive review of discounting strategies to ensure they are effectively driving sales without compromising profitability. This may involve adjusting discount levels or targeting discounts to specific customer segments to maximize returns.

4. **Investigate Volume Decline**: Deep dive into the causes of the volume decline to identify underlying issues and develop targeted solutions. This could involve analyzing consumer trends, competitor activity, or changes in market dynamics to understand the root causes of the decline.


