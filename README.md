# Power BI Dashboard for PooyaGostar Khorasan Company Data

Link in powerbi.com: https://app.powerbi.com/groups/me/reports/6069c500-b08f-432f-85b1-4e2b1b37b777/ReportSection09398833ec2d89f27e41?experience=power-bi

This repository contains a Power BI dashboard designed to analyze and visualize data for PooyaGostar Khorasan (PouyaGostar Khorasan Co. is one of the largest manufacturer of sealing systems in Iran. Founded in 2002, they produce various rubber profiles for automotive and other industries.) The dashboard is created using various datasets, and it provides insights into customer demographics, product analysis, promotions, and temporal data.

![customers](https://github.com/user-attachments/assets/9ab0e4c4-1e81-4951-b63c-d59b24f107b9)

## Data Sources

The dashboard uses the following datasets:

1. **Currency**: Contains information about different currencies.
   - Columns: CurrencyKey, CurrencyAlternateKey, CurrencyName, PersianCurrencyName

2. **Customer**: Contains demographic information about customers.
   - Columns: CustomerKey, GeographyKey, Name, BirthDate, Status, EmailAddress, YearlyIncome, TotalChildren, NumberChildrenAtHome, EnglishEducation, SpanishEducation, FrenchEducation, EnglishOccupation, FrenchOccupation, HouseOwnerFlag, NumberCarsOwned, AddressLine, Phone, DateFirstPurchase, CommuteDistance

3. **DateKey**: Contains detailed information about dates.
   - Columns: DateKey, FullDateAlternateKey, DayNumberOfWeek, EnglishDayNameOfWeek, SpanishDayNameOfWeek, FrenchDayNameOfWeek, DayNumberOfMonth, DayNumberOfYear, WeekNumberOfYear, EnglishMonthName, SpanishMonthName, FrenchMonthName, MonthNumberOfYear, CalendarQuarter, CalendarYear, CalendarSemester, FiscalQuarter, FiscalYear, FiscalSemester

4. **Product**: Contains information about products.
   - Columns: ProductKey, ProductAlternateKey, ProductSubcategoryKey, Weight, EnglishProductName, SpanishProductName, FrenchProductName, StandardCost, FinishedGoodsFlag, Color, SafetyStockLevel, ReorderPoint, ListPrice, Size_clean, SizeRange, DaysToManufacture, ProductLine, DealerPrice, Class, Style, ModelName, EnglishDescription, FrenchDescription, ChineseDescription, ArabicDescription, HebrewDescription, ThaiDescription, GermanDescription, JapaneseDescription, TurkishDescription, StartDate, StartHour, EndDate, EndHour

5. **Product Category**: Contains information about product categories.
   - Columns: ProductCategoryKey, PersianProductCategoryName, EnglishProductCategoryName, SpanishProductCategoryName, FrenchProductCategoryName

6. **Product Subcategory**: Contains information about product subcategories.
   - Columns: ProductSubcategoryKey, ProductCategoryKey, PersianProductSubcategoryName, EnglishProductSubcategoryName, SpanishProductSubcategoryName, FrenchProductSubcategoryName

7. **Promotion**: Contains information about promotions.
   - Columns: PromotionKey, EnglishPromotionName, SpanishPromotionName, FrenchPromotionName, DiscountPct, EnglishPromotionType, SpanishPromotionType, FrenchPromotionType, EnglishPromotionCategory, SpanishPromotionCategory, FrenchPromotionCategory, MinQty, MaxQty, StartDate, StartTime, EndDate, EndTime

8. **Sales Territory**: Contains information about sales territories.
   - Columns: PersianSalesTerritory, SalesTerritoryCountry, SalesTerritoryGroup, SalesTerritoryImage, SalesTerritoryKey, SalesTerritoryRegion

## Dashboard Visualizations

### Customer Demographics

1. **Treemap**: Displays customer distribution by education level and occupation.
   - **Fields**: 
     - **Axis**: [EnglishEducation]
     - **Legend**: [EnglishOccupation]
     - **Values**: [CustomerKey] (Count)

2. **Donut Chart**: Shows the number of cars owned by customers.
   - **Fields**: 
     - **Legend**: [NumberCarsOwned]
     - **Values**: [CustomerKey] (Count)

### Product Analysis

1. **Line Chart**: Compares the average list price and dealer price for each product.
   - **Fields**: 
     - **Axis**: [EnglishProductName]
     - **Values**: [ListPrice] (Average), [DealerPrice] (Average)

2. **Pie Chart**: Displays the count of reorder points by safety stock level.
   - **Fields**: 
     - **Legend**: [SafetyStockLevel]
     - **Values**: [ReorderPoint] (Count)

### Promotions

1. **Column Chart**: Shows the discount percentage for each promotion.
   - **Fields**: 
     - **Axis**: [EnglishPromotionName]
     - **Values**: [DiscountPct] (Sum)

2. **Slicer**: Allows filtering promotions by category.
   - **Fields**: 
     - [EnglishPromotionCategory]

### Temporal Analysis

1. **Line Chart**: Displays the number of purchases over time.
   - **Fields**: 
     - **Axis**: [FullDateAlternateKey]
     - **Values**: [DateKey] (Count)

2. **Heat Map**: Shows the distribution of purchases by day of the week and month.
   - **Fields**: 
     - **Rows**: [EnglishDayNameOfWeek]
     - **Columns**: [EnglishMonthName]
     - **Values**: [DateKey] (Count)

