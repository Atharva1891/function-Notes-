# function-Notes-
## DAX in Power BI: 
### **DAX (Data Analysis Expressions)** is a formula language used in Microsoft Power BI to create calculations and measures. It's a powerful tool that allows you to perform complex data manipulations and analysis directly within your Power BI reports.

## Key DAX Functions and Concepts
**Calculated Columns**: These are columns created within a table using DAX formulas. They can be used to derive new values based on existing data.
**Measures**: Measures are calculated fields that are typically used in visualizations. They are created within the Data View and can be used to aggregate data across multiple rows.

## Common DAX Functions:
**Statistical Functions**: AVERAGE, SUM, MIN, MAX, COUNT, COUNTROWS, etc.
**Logical Functions**: IF, AND, OR, NOT, etc.
**Date and Time Functions**: YEAR, MONTH, DAY, DATEADD, DATEDIFF, etc.
**Mathematical Functions**: ABS, SQRT, POWER, etc.
**Text Functions**: LEFT, RIGHT, MID, FIND, SUBSTITUTE, etc.

### Use Cases for DAX in Power BI
-DAX is used for a wide range of data analysis tasks, including:
-Creating calculated fields: Derive new information from existing data.
-Aggregating data: Calculate totals, averages, and other summary statistics.
-Performing time-series analysis: Analyze trends over time.
-Creating conditional calculations: Perform calculations based on certain conditions.
-Building complex measures: Create custom measures to meet specific analysis needs.

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

## **4. Filter Functions**

### **1. ALL**
- **Syntax**: `ALL(<TableOrColumn>)`
- **Example**: `Total Sales All = CALCULATE(SUM(Sales[Amount]), ALL(Sales))`
  - Ignores any filters applied to the *Sales* table and calculates the total sales amount.

### **2. ALLEXCEPT**
- **Syntax**: `ALLEXCEPT(<Table>, <Column1>, <Column2>, ...)`
- **Example**: `Sales by Region = CALCULATE(SUM(Sales[Amount]), ALLEXCEPT(Sales, Sales[Region]))`
  - Removes all filters on the *Sales* table except for the *Region* column, allowing you to see total sales per region.

### **3. FILTER**
- **Syntax**: `FILTER(<Table>, <Condition>)`
- **Example**: `High Value Sales = FILTER(Sales, Sales[Amount] > 1000)`
  - Returns a table with only the rows from the *Sales* table where the *Amount* is greater than 1000.

### **4. REMOVEFILTERS**
- **Syntax**: `REMOVEFILTERS(<TableOrColumn>)`
- **Example**: `Total Sales Without Filters = CALCULATE(SUM(Sales[Amount]), REMOVEFILTERS(Sales))`
  - Clears all filters from the *Sales* table when calculating total sales.

### **5. KEEPFILTERS**
- **Syntax**: `KEEPFILTERS(<Table>)`
- **Example**: `Filtered Sales = CALCULATE(SUM(Sales[Amount]), KEEPFILTERS(Sales[Amount] > 500))`
  - Retains any existing filters on the *Sales* table and applies the additional filter of sales greater than 500.

### **6. RELATEDTABLE**
- **Syntax**: `RELATEDTABLE(<TableName>)`
- **Example**: `Related Orders = COUNTROWS(RELATEDTABLE(Orders))`
  - Returns a table containing rows from the *Orders* table that are related to the current row in the context.

### **7. RELATED**
- **Syntax**: `RELATED(<ColumnName>)`
- **Example**: `Customer Country = RELATED(Customers[Country])`
  - Fetches the *Country* value from the *Customers* table for the current row in the context.

## **5. Logical Functions**

### **1. IF**
- **Syntax**: `IF(<Condition>, <ValueIfTrue>, [<ValueIfFalse>])`
- **Example**: `Sales Status = IF(Sales[Amount] > 1000, "High", "Low")`
  - Returns "High" if the *Amount* is greater than 1000; otherwise, it returns "Low".

### **2. AND**
- **Syntax**: `AND(<Logical1>, <Logical2>, ...)`
- **Example**: `High Value Sales = IF(AND(Sales[Amount] > 1000, Sales[Region] = "West"), "High", "Low")`
  - Returns "High" if both conditions are true: the *Amount* is greater than 1000 and the *Region* is "West".

### **3. OR**
- **Syntax**: `OR(<Logical1>, <Logical2>, ...)`
- **Example**: `Sales Status = IF(OR(Sales[Amount] > 1000, Sales[Region] = "West"), "High", "Low")`
  - Returns "High" if either condition is true: the *Amount* is greater than 1000 or the *Region* is "West".

### **4. NOT**
- **Syntax**: `NOT(<Logical>)`
- **Example**: `Sales Status = IF(NOT(Sales[Amount] > 1000), "Low", "High")`
  - Returns "Low" if the *Amount* is not greater than 1000; otherwise, it returns "High".

### **5. SWITCH**
- **Syntax**: `SWITCH(<Expression>, <Value1>, <Result1>, [<Value2>, <Result2>, ...], [<DefaultResult>])`
- **Example**: `Sales Category = SWITCH(Sales[Amount], 0, "No Sales", 1, "Low Sales", 1000, "Medium Sales", "High Sales")`
  - Evaluates the *Amount* and returns different categories based on the specified values.

### **6. ISBLANK**
- **Syntax**: `ISBLANK(<Value>)`
- **Example**: `Check Blank = IF(ISBLANK(Sales[Amount]), "No Amount", "Has Amount")`
  - Checks if the *Amount* is blank and returns "No Amount" if true; otherwise, it returns "Has Amount".

### **7. IFERROR**
- **Syntax**: `IFERROR(<Expression>, <ValueIfError>)`
- **Example**: `Safe Division = IFERROR(Sales[Amount] / Sales[Quantity], 0)`
  - Returns 0 if there is an error in the division; otherwise, it returns the result of the division.


## **6. Text Functions**

### **1. CONCATENATE**
- **Syntax**: `CONCATENATE(<Text1>, <Text2>)`
- **Example**: 
  Full Name = CONCATENATE(Employees[FirstName], Employees[LastName])
  ```
  - Combines the first name and last name of employees into a single string.

### **2. CONCATENATEX**
- **Syntax**: `CONCATENATEX(<Table>, <Expression>, <Delimiter>, [<OrderBy_Expression>], [<Order>])`
- **Example**: 
  Product List = CONCATENATEX(Products, Products[ProductName], ", ")
  ```
  - Joins all product names from the *Products* table into a single string, separated by a comma and a space.

### **3. LEFT**
- **Syntax**: `LEFT(<Text>, <NumberOfCharacters>)`
- **Example**: 
  First Initial = LEFT(Employees[FirstName], 1)
  ```
  - Returns the first character of the employee's first name.

### **4. RIGHT**
- **Syntax**: `RIGHT(<Text>, <NumberOfCharacters>)`
- **Example**: 
  Last 3 Digits = RIGHT(Employees[EmployeeID], 3)
  ```
  - Returns the last three characters of the employee's ID.

### **5. MID**
- **Syntax**: `MID(<Text>, <StartPosition>, <NumberOfCharacters>)`
- **Example**: 
  Middle Characters = MID(Products[ProductCode], 2, 3)
  ```
  - Extracts three characters from the product code starting at the second character.

### **6. LEN**
- **Syntax**: `LEN(<Text>)`
- **Example**: 
  Code Length = LEN(Products[ProductCode])
  ```
  - Returns the length of the product code.

### **7. SEARCH**
- **Syntax**: `SEARCH(<FindText>, <WithinText>, [<StartPosition>], [<NotFoundValue>])`
- **Example**: 
  Position of "Sales" = SEARCH("Sales", Orders[Description], 1, -1)
  ```
  - Finds the starting position of the word "Sales" within the order description. Returns -1 if not found.

### **8. REPLACE**
- **Syntax**: `REPLACE(<OldText>, <StartPosition>, <NumberOfCharacters>, <NewText>)`
- **Example**: 
  Updated Code = REPLACE(Products[ProductCode], 1, 3, "ABC")
  ```
  - Replaces the first three characters of the product code with "ABC".

### **9. UPPER**
- **Syntax**: `UPPER(<Text>)`
- **Example**: 
  Uppercase Name = UPPER(Employees[FirstName])
  ```
  - Converts the employee's first name to uppercase.

### **10. LOWER**
- **Syntax**: `LOWER(<Text>)`
- **Example**: 
  Lowercase Name = LOWER(Employees[LastName])
  ```
  - Converts the employee's last name to lowercase.

### **11. FORMAT**
- **Syntax**: `FORMAT(<Value>, <FormatString>)`
- **Example**: 

  Formatted Amount = FORMAT(Sales[Amount], "Currency")
  ```
  -Formats the sales amount as currency.

 
## **7. Math and Trigonometry Functions**

### **1. ABS**
- **Syntax**: `ABS(<Number>)`
- **Example**: 
  Absolute Value = ABS(Sales[Profit])
  ```
  - Returns the absolute value of the profit, converting any negative profit into a positive value.

### **2. CEILING**
- **Syntax**: `CEILING(<Number>, <Significance>)`
- **Example**: 
  Ceiling Value = CEILING(Sales[Amount], 10)
  ```
  - Rounds the sales amount up to the nearest multiple of 10.

### **3. FLOOR**
- **Syntax**: `FLOOR(<Number>, <Significance>)`
- **Example**: 
  Floor Value = FLOOR(Sales[Amount], 10)
  ```
  - Rounds the sales amount down to the nearest multiple of 10.

### **4. ROUND**
- **Syntax**: `ROUND(<Number>, <NumDigits>)`
- **Example**: 
  Rounded Value = ROUND(Sales[Amount], 2)
  ```
  - Rounds the sales amount to two decimal places.

### **5. ROUNDDOWN**
- **Syntax**: `ROUNDDOWN(<Number>, <NumDigits>)`
- **Example**: 
  Round Down Value = ROUNDDOWN(Sales[Amount], 0)
  ```
  - Rounds the sales amount down to the nearest whole number.

### **6. ROUNDUP**
- **Syntax**: `ROUNDUP(<Number>, <NumDigits>)`
- **Example**: 
  Round Up Value = ROUNDUP(Sales[Amount], 0)
  ```
  - Rounds the sales amount up to the nearest whole number.

### **7. INT**
- **Syntax**: `INT(<Number>)`
- **Example**: 
  Integer Value = INT(Sales[Amount])
  ```
  - Rounds the sales amount down to the nearest integer.

### **8. MOD**
- **Syntax**: `MOD(<Number>, <Divisor>)`
- **Example**: 
  Remainder = MOD(Sales[Amount], 5)
  ```
  - Returns the remainder when the sales amount is divided by 5.

### **9. SQRT**
- **Syntax**: `SQRT(<Number>)`
- **Example**: 
  Square Root = SQRT(Sales[Amount])
  ```
  - Returns the square root of the sales amount.

### **10. EXP**
- **Syntax**: `EXP(<Number>)`
- **Example**: 
  Exponential Value = EXP(Sales[GrowthRate])
  ```
  - Returns \( e \) raised to the power of the sales growth rate.

### **11. LOG**
- **Syntax**: `LOG(<Number>, [<Base>])`
- **Example**: 
  Logarithm Value = LOG(Sales[Amount], 10)
  ```
  - Returns the logarithm of the sales amount to the base of 10.

### **12. POWER**
- **Syntax**: `POWER(<Number>, <Power>)`
- **Example**: 
  Power Value = POWER(Sales[Amount], 2)
  ```
  - Returns the result of the sales amount raised to the power of 2 (squared).
---

## **8. Statistical Functions**

### **1. MEDIAN**
- **Syntax**: `MEDIAN(<Column>)`
- **Example**: 
  Median Sales = MEDIAN(Sales[Amount])
  ```
  - Returns the median sales amount from the *Sales* table.

### **2. MEDIANX**
- **Syntax**: `MEDIANX(<Table>, <Expression>)`
- **Example**: 
  Median Profit = MEDIANX(Sales, Sales[Profit])
  ```
  - Evaluates the profit for each row in the *Sales* table and returns the median.

### **3. STDEV**
- **Syntax**: `STDEV(<Column>)`
- **Example**: 
  Standard Deviation = STDEV(Sales[Amount])
  ```
  - Estimates the standard deviation of the sales amounts.

### **4. STDEVX.P**
- **Syntax**: `STDEVX.P(<Table>, <Expression>)`
- **Example**: 
  Population StdDev = STDEVX.P(Sales, Sales[Amount])
  ```
  - Calculates the standard deviation of the sales amount based on the entire population.

### **5. VAR**
- **Syntax**: `VAR(<Column>)`
- **Example**: 
  Variance = VAR(Sales[Amount])
  ```
  - Estimates the variance of the sales amounts.

### **6. VAR.P**
- **Syntax**: `VAR.P(<Column>)`
- **Example**: 

  Population Variance = VAR.P(Sales[Amount])
  ```
  - Calculates the variance of the sales amount based on the entire population.

---

## **9. Information Functions**

### **1. BLANK**
- **Syntax**: `BLANK()`
- **Example**: 
  No Value = BLANK()
  ```
  - Returns a blank value.

### **2. ISBLANK**
- **Syntax**: `ISBLANK(<Value>)`
- **Example**: 
  Is Sales Blank = ISBLANK(Sales[Amount])
  ```
  - Checks if the sales amount is blank.

### **3. ISNUMBER**
- **Syntax**: `ISNUMBER(<Value>)`
- **Example**: 
  Is Amount Number = ISNUMBER(Sales[Amount])
  ```
  - Checks if the sales amount is a number.

### **4. ISTEXT**
- **Syntax**: `ISTEXT(<Value>)`
- **Example**: 
  Is Description Text = ISTEXT(Sales[Description])
  ```
  - Checks if the sales description is text.

### **5. ISERROR**
- **Syntax**: `ISERROR(<Value>)`
- **Example**: 
  ```DAX
  Is Error = ISERROR(Sales[Amount]/0)
  ```
  - Checks if dividing the sales amount by zero results in an error.

---

## **10. Other Useful Functions**

### **1. CALCULATE**
- **Syntax**: `CALCULATE(<Expression>, <Filter1>, <Filter2>, ...)`
- **Example**: 
  Total Sales = CALCULATE(SUM(Sales[Amount]), Sales[Region] = "East")
  ```
  - Modifies the filter context to sum sales amounts only for the East region.

### **2. CALCULATETABLE**
- **Syntax**: `CALCULATETABLE(<Table>, <Filter1>, <Filter2>, ...)`
- **Example**: 
  East Sales Table = CALCULATETABLE(Sales, Sales[Region] = "East")
  ```
  - Returns a table of sales data filtered for the East region.

### **3. SELECTEDVALUE**
- **Syntax**: `SELECTEDVALUE(<Column>, [<AlternateResult>])`
- **Example**: 
  Selected Product = SELECTEDVALUE(Products[ProductName], "None Selected")
  ```
  - Returns the selected product name or "None Selected" if multiple values are selected.

### **4. VALUES**
- **Syntax**: `VALUES(<Column>)`
- **Example**: 
  Distinct Products = VALUES(Sales[ProductID])
  ```
  - Returns a one-column table of distinct product IDs from the sales table.

### **5. DISTINCT**
- **Syntax**: `DISTINCT(<Column>)`
- **Example**: 
  Unique Customers = DISTINCT(Sales[CustomerID])
  ```
  - Returns a one-column table of unique customer IDs from the sales table.

### **6. RANKX**
- **Syntax**: `RANKX(<Table>, <Expression>, [<Value>, [<Order>, [<TieBreakOrder>]]])`
- **Example**: 
  Product Rank = RANKX(ALL(Products), SUM(Sales[Amount]), , DESC)
  ```
  - Ranks products based on total sales in descending order.

### **7. LOOKUPVALUE**
- **Syntax**: `LOOKUPVALUE(<Result_ColumnName>, <Search_ColumnName>, <Search_Value>)`
- **Example**: 
  Product Price = LOOKUPVALUE(Products[Price], Products[ProductID], Sales[ProductID])
  ```
  - Returns the price of a product based on its ID in the sales table.

### **8. GENERATE**
- **Syntax**: `GENERATE(<Table1>, <Table2>)`
- **Example**: 
  Generated Table = GENERATE(Products, Sales)
  ```
  - Creates a Cartesian product of the *Products* and *Sales* tables.

### **9. CROSSJOIN**
- **Syntax**: `CROSSJOIN(<Table1>, <Table2>, ...)`
- **Example**: 
  Crossjoined Table = CROSSJOIN(Products, Customers)
  ```
  - Returns the Cartesian product of the *Products* and *Customers* tables.

