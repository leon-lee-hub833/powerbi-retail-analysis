# Powerbi-Retail-Analysis
A Power BI project for essential retail KPI analysis   
## Data Schema   
### Sales Table  
MonthID, ItemID, LocationID, Sum_GrossMarginAmount, Sum_regular_Sales_Dollars, Sum_Markdown_Sales_dollars,  
ScenarioID, ReportingPeriodID, Sum-Regular_Sales_Units, Sum_Markdown_Sales_Units  

### District Table  
DistrictID, District, DM_pic_fl, DM_Pic, BusinessUnitID, DMImage  

### Item Table  
ItemID, Segment, Category, Buyer, FamilyNane  

### Store Table  
LocationID, CityName, Territory, PostalCode, OpenDate, SellingAreaSize, DistrictName, Name, StoreNumberName, City  
Chain, DM, DM_pic, DistrictID, OpenYear, StoreType, OpenMonth No., OpenMonth  

### Time Table 
ReportingporiedID, Period, FiscalYear, FiscalMonth, Month  

## Measure    
1.Total Sales = [Regular_Sales_Dollars]+[Markdown_Sales_Dollars]  
2.Total Sales This Year = CALCULATE([TotalSales], Sales[ScenarioID]=1)  
3.Total Sales Last Year = CALCULATE([TotalSales], Sales[ScenarioID]=2)  
4.Total Sales Variance = [TotalSalesThisYear]-[TotalSalesLastYear]  
5.Percentage Change = IF([TotalSalesLastyear]<>0, [Total Sales Variance]/[TotalSalesLastYear], BLANK())  

6.Total Unit = [Regular_Sales_Units]+[Markdown_Sales_Units]  
7.Total Unit This Year =  CALCULATE([TotalUnits], Sales[ScenarioID]=1)  
8.Total Unit Last Year =  CALCULATE([TotalUnits], Sales[ScenarioID]=2)  

9.Average Unit Price Last Year =  IF([Total Units Last Year]<>0, [TotalSalesLY]/[Total Units Last Year], BLANK())  
10.Average Unit Price This Year = IF([Total Units This Year]<>0, [TotalSalesTY]/[Total Units This Year], BLANK())  

11.Gross Margin This Year = CALCULATE(SUM([Sum_GrossMarginAmount]), Sales[ScenarioID]=1)  
12.Gross Margin Last year = CALCULATE(SUM([Sum_GrossMarginAmount]), Sales[ScenarioID]=2)  
13.Gross Margin Percentage This Year = [Gross Margin This Year]/[TotalSalesTY]  
14.Gross Margin Percentage Last Year =  [Gross Margin Last Year]/[TotalSalesLY]  





![image](https://github.com/user-attachments/assets/2802d4da-5543-4f06-b0d8-6d25169bbbd0)
![image](https://github.com/user-attachments/assets/aedb8a9d-a38d-49e7-bad8-f99d46d34d8a)
![image](https://github.com/user-attachments/assets/c3bfbca0-672c-4c11-b347-36dc9e0c7afc)
