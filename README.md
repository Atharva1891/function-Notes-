# function-Notes-
Here’s a categorized list of DAX functions commonly used in Power BI, Excel Power Pivot, and Analysis Services. They’re grouped by function type for easier reference:

---

### 1. **Aggregate Functions**
   - **SUM**: Adds all numbers in a column.
   - **SUMX**: Iterates over a table and sums an expression for each row.
   - **AVERAGE**: Computes the average of numbers in a column.
   - **AVERAGEX**: Iterates over a table and averages an expression for each row.
   - **MIN**: Returns the smallest value in a column.
   - **MINX**: Evaluates an expression for each row and returns the minimum result.
   - **MAX**: Returns the largest value in a column.
   - **MAXX**: Evaluates an expression for each row and returns the maximum result.
   - **COUNT**: Counts the number of rows in a column that contain numbers.
   - **COUNTA**: Counts non-blank rows in a column.
   - **COUNTX**: Counts the rows where an expression evaluates to non-blank.
   - **COUNTROWS**: Counts the number of rows in a table.
   - **DISTINCTCOUNT**: Counts the distinct values in a column.

---

### 2. **Date and Time Functions**
   - **DATE**: Creates a date from year, month, and day.
   - **DATEDIFF**: Returns the difference between two dates.
   - **DATEADD**: Shifts dates by a specified interval (day, month, quarter, year).
   - **YEAR**: Extracts the year from a date.
   - **MONTH**: Extracts the month from a date.
   - **DAY**: Extracts the day from a date.
   - **HOUR**: Extracts the hour from a time.
   - **MINUTE**: Extracts the minute from a time.
   - **NOW**: Returns the current date and time.
   - **TODAY**: Returns the current date.

---

### 3. **Time Intelligence Functions**
   - **TOTALYTD**: Calculates year-to-date totals.
   - **TOTALQTD**: Calculates quarter-to-date totals.
   - **TOTALMTD**: Calculates month-to-date totals.
   - **SAMEPERIODLASTYEAR**: Returns dates from the same period last year.
   - **PREVIOUSYEAR**: Returns all dates from the previous year.
   - **NEXTYEAR**: Returns all dates from the next year.
   - **DATESYTD**: Returns a set of dates up to the last date in the year-to-date context.
   - **DATESQTD**: Returns dates in the quarter-to-date context.
   - **DATESMTD**: Returns dates in the month-to-date context.
   - **PARALLELPERIOD**: Shifts dates by a specified number of intervals (months, quarters, years).
   - **STARTOFMONTH**: Returns the first date of the month in a date column.
   - **ENDOFMONTH**: Returns the last date of the month in a date column.

---

### 4. **Filter Functions**
   - **ALL**: Ignores all filters on a column or table.
   - **ALLEXCEPT**: Removes all filters on a table except for specified columns.
   - **FILTER**: Returns a table with rows that satisfy a condition.
   - **REMOVEFILTERS**: Clears all filters on a table or column.
   - **KEEPFILTERS**: Retains any existing filters on a column.
   - **RELATEDTABLE**: Returns a table related to the current row.
   - **RELATED**: Fetches a related value from another table based on relationships.

---

### 5. **Logical Functions**
   - **IF**: Evaluates a condition and returns different results based on True or False.
   - **AND**: Returns True if all arguments are true.
   - **OR**: Returns True if any arguments are true.
   - **NOT**: Returns the opposite Boolean value.
   - **SWITCH**: Evaluates multiple expressions for conditions, returns the first matching result.
   - **ISBLANK**: Checks if a value is blank.
   - **IFERROR**: Returns a specified value if the expression has an error.

---

### 6. **Text Functions**
   - **CONCATENATE**: Combines two text strings into one.
   - **CONCATENATEX**: Joins text from rows in a table using a specified delimiter.
   - **LEFT**: Returns the leftmost characters of a string.
   - **RIGHT**: Returns the rightmost characters of a string.
   - **MID**: Returns a substring from a text string based on position and length.
   - **LEN**: Returns the length of a text string.
   - **SEARCH**: Finds the starting position of text within a string.
   - **REPLACE**: Replaces part of a text string with new text.
   - **UPPER**: Converts text to uppercase.
   - **LOWER**: Converts text to lowercase.
   - **FORMAT**: Formats a value based on a specified format string.

---

### 7. **Math and Trigonometry Functions**
   - **ABS**: Returns the absolute value of a number.
   - **CEILING**: Rounds a number up to the nearest integer.
   - **FLOOR**: Rounds a number down to the nearest integer.
   - **ROUND**: Rounds a number to a specified number of digits.
   - **ROUNDDOWN**: Rounds a number down.
   - **ROUNDUP**: Rounds a number up.
   - **INT**: Rounds a number down to the nearest integer.
   - **MOD**: Returns the remainder when dividing two numbers.
   - **SQRT**: Returns the square root of a number.
   - **EXP**: Returns e raised to the power of a number.
   - **LOG**: Returns the logarithm of a number.
   - **POWER**: Returns the result of a number raised to a power.

---

### 8. **Statistical Functions**
   - **MEDIAN**: Returns the median of values in a column.
   - **MEDIANX**: Evaluates an expression for each row and returns the median.
   - **STDEV**: Estimates the standard deviation.
   - **STDEVX.P**: Calculates standard deviation based on entire population.
   - **VAR**: Estimates variance.
   - **VAR.P**: Calculates variance based on entire population.

---

### 9. **Information Functions**
   - **BLANK**: Returns a blank.
   - **ISBLANK**: Checks if a value is blank.
   - **ISNUMBER**: Checks if a value is a number.
   - **ISTEXT**: Checks if a value is text.
   - **ISERROR**: Checks if a value results in an error.

---

### 10. **Other Useful Functions**
   - **CALCULATE**: Modifies a measure's filter context.
   - **CALCULATETABLE**: Returns a table based on a modified filter context.
   - **SELECTEDVALUE**: Returns the selected value in a column.
   - **VALUES**: Returns a one-column table of distinct values.
   - **DISTINCT**: Returns a one-column table of unique values.
   - **RANKX**: Returns the rank of an expression in a table.
   - **LOOKUPVALUE**: Returns a value from a different row based on a specified condition.
   - **GENERATE**: Creates a Cartesian product of two tables.
   - **CROSSJOIN**: Returns the Cartesian product of two or more tables.

---

This list covers the majority of DAX functions, each of which can be combined to create powerful analytical calculations within Power BI and other Microsoft data tools. These functions help users to handle everything from basic aggregations to complex data modeling and advanced time intelligence calculations.
