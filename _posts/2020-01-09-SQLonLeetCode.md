---
layout:     post
title:      Nail down the SQL interview question
subtitle:   Tight arsenal to crack the questions
date:       2020-01-09
author:    Chester
header-img: img/makeup_title.jpeg
catalog: true
tags:
   Job
---
# Intro
This tutor is very focus on how to solve the question from interviews. It's not always true or efficiency to have such queries on real big database. I'll use MS sql as primary sql tool to solve the questions, since the MS sql is more freu


# Primary section
- join
- Window function
- Aggregate
- Date data 
- Data type
- Logic Process
- Variable
- Clause
- Function
- Pivot
# Join multiple table
## UNION/EXCEPT/INTERSET
leetcode 608
If the question can be divide and conque. Union can simply add the result.
## JOIN 


# Window function
Leetcode 185
```sql
FUNCTION() OVER ([ <PARTITION BY clause> ] 
	  [ <ORDER BY clause> ] 
	  [ <ROW or RANGE clause> ] )
```


## ROW and Range clause
- UNBOUNDED  PRECEDING
- CURRENT ROW
- UNBOUNDED FOLLOWING
- ?FOLLOWING
- ?PRECEDING




## ROW_NUMBER
```sql
ROW_NUMBER ( ) 
OVER ( [ PARTITION BY value_expression , ... [ n ] ] order_by_clause )
```
## LEAD/LAG
```sql
LEAD/LAG(columns, step) OVER ([ PARTITION BY value_expression , ... [ n ] ] order_by_clause )
```

## LIMIT
SQL server doesn't have limit. We can use alternative way to acieve the same result.
Use **TOP**

## ROW
	```sql
	SELECT TOP 1 * FROM table_Name 
	ORDER BY unique_column DESC 
	```
- OFFSET + FETCH 
	```sql
	OFFSET n ROWS
	FETCH  NEXT m ROWS  ONLY
	```

## RANK & DENSERANK
RANK gives you the ranking within your ordered partition. Ties are assigned the same rank, with the next ranking(s) skipped. So, if you have 3 items at rank 2, the next rank listed would be ranked 5.

DENSE_RANK again gives you the ranking within your ordered partition, but the ranks are consecutive. No ranks are skipped if there are ranks with multiple items.

| number   |      DENSERANK      |  RANK |
|----------|:-------------:|------:|
| 1|  1| 1 |
| 1 |1 |   1 |
| 2 | 2 | 3|
| 3 | 3 | 4 |


# Date data related useful function
- DATEADD(datepart, number, date)
- DATEDIFF ( datepart , startdate , enddate)
- DATEPART ( datepart , date )
- BETWEEN can be apply to date format. Berween is inclusive both bound.

# Data type
## Enumerate
Leetcode 262
## CAST & CONVERT
They are the same. Try use **CONVERT** only. Keep it simple and easy to rememver. 
```sql
-- CAST Syntax:  
CAST ( expression AS data_type [ ( length ) ] )  
  
-- CONVERT Syntax:  
CONVERT ( data_type [ ( length ) ] , expression [ , style ] )
```
Example :
```sql
CONVERT(int, ListPrice)
```

## Pick only LEFT or RIGHT
```sql
SELECT LEFT('2017-03-31',7)
```
=> "2017-03"
# Logic Process
## IF ELSE statement
Leetcode 608
```sql
iff(regulation, return1,return2)
```
Here's the example show, if else result can be directly use in other function.
```sql
SELECT Request_at as Day,
       ROUND(COUNT(iff(Status != 'completed', TRUE, NULL)) / COUNT(*), 2) AS 'Cancellation Rate'
FROM Trips
WHERE (Request_at BETWEEN '2013-10-01' AND '2013-10-03')
      AND Client_id NOT IN (SELECT Users_Id FROM Users WHERE Banned = 'Yes')
GROUP BY Request_at;
```
## WHEN case end
If the if-else case more than 2 split point, when/case is easier
```sql
WHEN statement
CASE case1 THEN value_1
CASE .... THEN value_....
ELSE value_else
END
```

# Clause
## ORDER BY
- Rows cluase
## MS SQL special
don't allow wher PAIR in SELECT .

# Function
- Variable @/ DECLARE
```sql
CREATE  FUNCTION dbo.ufnGetInventoryStock(@ProductID int) 
RETURNS  int  
AS 
BEGIN  
DECLARE @ret int; 
SELECT @ret = SUM(p.Quantity) FROM Production.ProductInventory p WHERE p.ProductID = @ProductID AND p.LocationID = '6'; IF (@ret IS NULL) SET @ret = 0; 
RETURN @ret; 
END;
```
## Vairable
DECLARE @variable_name datatype

# PIVOT
When the question ask about column and rows transfer, pivot is very useful to deal with.
pivot: rows-> Columns
unpivot -> columns ->rows

Leetcode 1179
```sql
+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| revenue       | int     |
| month         | varchar |
+---------------+---------+
```
=>
```sql
+------+-------------+-------------+-------------+-----+-------------+
| id   | Jan_Revenue | Feb_Revenue | Mar_Revenue | ... | Dec_Revenue |
+------+-------------+-------------+-------------+-----+-------------+
| 1    | 8000        | 7000        | 6000        | ... | null        |
| 2    | 9000        | null        | null        | ... | null        |
| 3    | null        | 10000       | null        | ... | null        |
+------+-------------+-------------+-------------+-----+-------------+
```
every Row has months label, we expect it as new columns. It's the typical question we can easier to get from ***PIVOT***

SELECT <non-pivoted column>,  
    [first pivoted column] AS <column name>,  
    [second pivoted column] AS <column name>,  
    ...  
    [last pivoted column] AS <column name>  
FROM  
    (<SELECT query that produces the data>)   
    AS <alias for the source query>  
PIVOT  
(  
    <aggregation function>(<column being aggregated>)  
FOR   
[<column that contains the values that will become column headers>]   
    IN ( [first pivoted column], [second pivoted column],  
    ... [last pivoted column])  
) AS <alias for the pivot table>  
<optional ORDER BY clause>;

## Improtant! 
	[<column that contains the values that will become column headers>]   :
Represent the original column cotains the future column headers


Example :
```sql
SELECT 
    id,
    Jan AS Jan_Revenue,
    Feb AS Feb_Revenue, 
    Mar AS Mar_Revenue, 
    Apr AS Apr_Revenue,
    May AS May_Revenue,
    Jun AS Jun_Revenue,
    Jul AS Jul_Revenue,
    Aug AS Aug_Revenue,
    Sep AS Sep_Revenue,
    Oct AS Oct_Revenue,
    Nov AS Nov_Revenue,
    Dec AS Dec_Revenue
FROM Department
PIVOT 
(
    MAX(revenue)
    FOR month IN (Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec)        
) AS MonthsRevenue
```




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgzNjE4NzY0MywxMDg4NTAxNTAsNTEzMT
k3MTY0LC0zNjIyNjgxMjYsLTI0MTYzMDM0MCwtMTI2ODc3Mjg3
OV19
-->