# function-Notes-
## 1. Aggregate Functions
### **1. SUM**
- **Syntax**: `SUM(<ColumnName>)`
- **Example**: `Total Sales = SUM(Sales[Amount])`
  - Adds up all values in the *Amount* column of the *Sales* table.

### **2. SUMX**
- **Syntax**: `SUMX(<Table>, <Expression>)`
- **Example**: `Total Sales per Product = SUMX(Sales, Sales[Quantity] * Sales[UnitPrice])`
  - Calculates `Quantity * UnitPrice` for each row in the *Sales* table and then sums the results.

### **3. AVERAGE**
- **Syntax**: `AVERAGE(<ColumnName>)`
- **Example**: `Average Sales = AVERAGE(Sales[Amount])`
  - Calculates the average of the values in the *Amount* column of the *Sales* table.

### **4. AVERAGEX**
- **Syntax**: `AVERAGEX(<Table>, <Expression>)`
- **Example**: `Average Sale per Product = AVERAGEX(Sales, Sales[Quantity] * Sales[UnitPrice])`
  - Evaluates `Quantity * UnitPrice` for each row and averages the result.

### **5. MIN**
- **Syntax**: `MIN(<ColumnName>)`
- **Example**: `Minimum Price = MIN(Products[Price])`
  - Returns the smallest price in the *Price* column of the *Products* table.

### **6. MINX**
- **Syntax**: `MINX(<Table>, <Expression>)`
- **Example**: `Minimum Sale Amount = MINX(Sales, Sales[Quantity] * Sales[UnitPrice])`
  - Calculates `Quantity * UnitPrice` for each row and returns the minimum result.

### **7. MAX**
- **Syntax**: `MAX(<ColumnName>)`
- **Example**: `Maximum Price = MAX(Products[Price])`
  - Returns the largest value in the *Price* column of the *Products* table.

### **8. MAXX**
- **Syntax**: `MAXX(<Table>, <Expression>)`
- **Example**: `Maximum Sale Amount = MAXX(Sales, Sales[Quantity] * Sales[UnitPrice])`
  - Calculates `Quantity * UnitPrice` for each row and returns the maximum result.

### **9. COUNT**
- **Syntax**: `COUNT(<ColumnName>)`
- **Example**: `Total Orders = COUNT(Sales[OrderID])`
  - Counts the number of rows in *OrderID* that contain numbers.

### **10. COUNTA**
- **Syntax**: `COUNTA(<ColumnName>)`
- **Example**: `Non-Empty Orders = COUNTA(Sales[OrderID])`
  - Counts the number of non-blank rows in the *OrderID* column of the *Sales* table.

### **11. COUNTX**
- **Syntax**: `COUNTX(<Table>, <Expression>)`
- **Example**: `Orders with High Sales = COUNTX(Sales, IF(Sales[Amount] > 5000, 1, BLANK()))`
  - Counts rows where the amount is greater than 5000.

### **12. COUNTROWS**
- **Syntax**: `COUNTROWS(<Table>)`
- **Example**: `Total Rows = COUNTROWS(Sales)`
  - Counts the number of rows in the *Sales* table.

### **13. DISTINCTCOUNT**
- **Syntax**: `DISTINCTCOUNT(<ColumnName>)`
- **Example**: `Unique Customers = DISTINCTCOUNT(Sales[CustomerID])`
  - Counts distinct values in the *CustomerID* column of the *Sales* table.

--- 

These DAX functions are essential for performing calculations, aggregations, and counting operations in Power BI, allowing for deeper insights into data.

## **2. Date and Time Functions**

### **1. DATE**
- **Syntax**: `DATE(<Year>, <Month>, <Day>)`
- **Example**: `Order Date = DATE(2024, 10, 25)`
  - Creates a date value of October 25, 2024.

### **2. DATEDIFF**
- **Syntax**: `DATEDIFF(<StartDate>, <EndDate>, <Interval>)`
- **Example**: `Days Difference = DATEDIFF(Sales[StartDate], Sales[EndDate], DAY)`
  - Returns the difference in days between two date columns in the *Sales* table.

### **3. DATEADD**
- **Syntax**: `DATEADD(<DateColumn>, <Number>, <Interval>)`
- **Example**: `Previous Month Sales = CALCULATE(SUM(Sales[Amount]), DATEADD(Sales[OrderDate], -1, MONTH))`
  - Shifts the dates in the *OrderDate* column back by one month and calculates the sales amount.

### **4. YEAR**
- **Syntax**: `YEAR(<Date>)`
- **Example**: `Order Year = YEAR(Sales[OrderDate])`
  - Extracts the year from the *OrderDate* column.

### **5. MONTH**
- **Syntax**: `MONTH(<Date>)`
- **Example**: `Order Month = MONTH(Sales[OrderDate])`
  - Extracts the month from the *OrderDate* column.

### **6. DAY**
- **Syntax**: `DAY(<Date>)`
- **Example**: `Order Day = DAY(Sales[OrderDate])`
  - Extracts the day from the *OrderDate* column.

### **7. HOUR**
- **Syntax**: `HOUR(<Time>)`
- **Example**: `Order Hour = HOUR(Sales[OrderTime])`
  - Extracts the hour from the *OrderTime* column.

### **8. MINUTE**
- **Syntax**: `MINUTE(<Time>)`
- **Example**: `Order Minute = MINUTE(Sales[OrderTime])`
  - Extracts the minute from the *OrderTime* column.

### **9. NOW**
- **Syntax**: `NOW()`
- **Example**: `Current Date and Time = NOW()`
  - Returns the current date and time.

### **10. TODAY**
- **Syntax**: `TODAY()`
- **Example**: `Current Date = TODAY()`
  - Returns the current date.

---

## **3. Time Intelligence Functions**

### **1. TOTALYTD**
- **Syntax**: `TOTALYTD(<Expression>, <DateColumn>, [<Filter>])`
- **Example**: `YTD Sales = TOTALYTD(SUM(Sales[Amount]), Sales[OrderDate])`
  - Calculates the year-to-date total of the sales amount.

### **2. TOTALQTD**
- **Syntax**: `TOTALQTD(<Expression>, <DateColumn>, [<Filter>])`
- **Example**: `QTD Sales = TOTALQTD(SUM(Sales[Amount]), Sales[OrderDate])`
  - Calculates the quarter-to-date total of the sales amount.

### **3. TOTALMTD**
- **Syntax**: `TOTALMTD(<Expression>, <DateColumn>, [<Filter>])`
- **Example**: `MTD Sales = TOTALMTD(SUM(Sales[Amount]), Sales[OrderDate])`
  - Calculates the month-to-date total of the sales amount.

### **4. SAMEPERIODLASTYEAR**
- **Syntax**: `SAMEPERIODLASTYEAR(<DateColumn>)`
- **Example**: `Sales Last Year = CALCULATE(SUM(Sales[Amount]), SAMEPERIODLASTYEAR(Sales[OrderDate]))`
  - Returns the sales amount from the same period last year.

### **5. PREVIOUSYEAR**
- **Syntax**: `PREVIOUSYEAR(<DateColumn>)`
- **Example**: `Sales Previous Year = CALCULATE(SUM(Sales[Amount]), PREVIOUSYEAR(Sales[OrderDate]))`
  - Returns all dates from the previous year and calculates the sales amount.

### **6. NEXTYEAR**
- **Syntax**: `NEXTYEAR(<DateColumn>)`
- **Example**: `Sales Next Year = CALCULATE(SUM(Sales[Amount]), NEXTYEAR(Sales[OrderDate]))`
  - Returns all dates from the next year and calculates the sales amount.

### **7. DATESYTD**
- **Syntax**: `DATESYTD(<DateColumn>, [<YearEndDate>])`
- **Example**: `YTD Dates = DATESYTD(Sales[OrderDate])`
  - Returns a set of dates up to the last date in the year-to-date context.

### **8. DATESQTD**
- **Syntax**: `DATESQTD(<DateColumn>)`
- **Example**: `QTD Dates = DATESQTD(Sales[OrderDate])`
  - Returns dates in the quarter-to-date context.

### **9. DATESMTD**
- **Syntax**: `DATESMTD(<DateColumn>)`
- **Example**: `MTD Dates = DATESMTD(Sales[OrderDate])`
  - Returns dates in the month-to-date context.

### **10. PARALLELPERIOD**
- **Syntax**: `PARALLELPERIOD(<DateColumn>, <Number>, <Interval>)`
- **Example**: `Sales Parallel Period = CALCULATE(SUM(Sales[Amount]), PARALLELPERIOD(Sales[OrderDate], -1, MONTH))`
  - Shifts the dates in the *OrderDate* column back by one month.

### **11. STARTOFMONTH**
- **Syntax**: `STARTOFMONTH(<DateColumn>)`
- **Example**: `First Day of Month = STARTOFMONTH(Sales[OrderDate])`
  - Returns the first date of the month in the *OrderDate* column.

### **12. ENDOFMONTH**
- **Syntax**: `ENDOFMONTH(<DateColumn>)`
- **Example**: `Last Day of Month = ENDOFMONTH(Sales[OrderDate])`
  - Returns the last date of the month in the *OrderDate* column.


