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

In this post, I'm going to guide you how to crack SQL interview questions.  I'll use MS sql as primary sql tool to solve the questions, since the MS sql is more frequently pop out on job description from Linkedin. 


# Who need this post?
Some junior data related job seekers. Not knowing database too much or try to learn with sql question. Unlike the real problem, the question won't touch more complicated issue around big data or database principles. However, keep in mind big O issue is also important. It can be common following questions. 

**Getting start**
 To make sure you already pass these 2 web site 
 - w3school
 - hackrank
 Then... Let's rockroll on leetcode. For most of questions, the database questions on leetcode need to pay for play.

# Clause
What's minimum unit in RDBMS? I'll say it's **Clause**
 
- order by
- top
- group by
- having



## ORDER BY
- Rows cluase
## MS SQL special
don't allow wher PAIR in SELECT .

# More than one table ?!
*leetcode 608, 1350*

We all need to answer this question first "Why DB needs multiple table?"

> Having 1 giant table is called, Denormalization. Breaking that giant
> table into multiple tables is called, Normalization. The appeal of
> Database Normalization is that is prevents:
> 
> -   Insert Anomalies: When you need to insert some data, but all required values are not known, so it is impossible to conduct the
> insert.
> -   Update Anomalies: When 1 single attribute of something changes in the real world, but you have to update multiple rows, multiple
> columns, or both. There is risk in these rows and/or columns getting
> out of sync.
> -   Delete Anomalies: You need to delete some data, but there is data in the rows that you want to keep. You either have to forego the
> delete, or conduct the delete and lose the data.

Therefore, the query in most of relational database is need to twinkle multiple table. There's primary key to connect two tables, sometimes, two table are the same one.   

**UNION/EXCEPT/INTERSECT/JOIN**



# Window function
As a data user, window function is inevitable part of analysis. Why it so important in interview? It can be daily function on even simple task.


## Aggregation
If we assume all the data as giant single window. The aggregation is the way to extract the statistical insight on data set. 
- **SUM/AVG/MIN/MAX**
	They are easy to understand.
- **Median**
	Hohohoho! This is not cute at all. Check *Leetcode569*. Take out the median, the question is super easy. 
- **VAR/STDEV**
	More stats

## Set the window
Easy window questions : *Leetcode 185*

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
# String operation
The questions sometime will come with varchar type data. I

**Pick only LEFT or RIGHT**
```sql
SELECT LEFT('2017-03-31',7)
```
The string trim down as "2017-03"

**LIKE pattern**
Easy: *Leetcode 1527*
Mid: *Leetcode1517*

```sql
WHERE condition LIKE '%SOMEKEYWORD%'
```
If you think that's the regular express? nah... half and half.  Unlike the regular expres[(cheat sheet)](https://cheatography.com/davechild/cheat-sheets/regular-expressions/), use "+" as infinity possible .[LIKE rule from MS sql](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/like-transact-sql?view=sql-server-ver15)
- **%** mean the one or more characters 
- **_** mean one characters
Here's some examples:
1. `LIKE '%@leetcode'`  12341dsafasdfe4@leetcode is valid for pattern. [:alpha:]+@leetcode is the same pattern for regex
2. 
# Conditional control
## IF ELSE statement
*Leetcode 608*
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

## Important! 
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



# Function
Last part in this short introduction. 

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
## Variable declaration 
DECLARE @variable_name datatype
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIzMTM2ODI0MywtODEwNzY1NzM3LC0xMz
c3NDcwMDI0LC0xMzgxNzc0NTc5LC0xNjAwMTU4MDA5LC0xMzA5
ODg5MDY2LC02MTUzMzc4NzEsLTIwNTMyMDE0NDksLTIwNTg5MD
g4OTEsMjAyODA3MTgxNCwxODQ0NTA2OTc3LC01Mzk0MTE3ODYs
LTEzMTYxMDAxMDksMTA4ODUwMTUwLDUxMzE5NzE2NCwtMzYyMj
Y4MTI2LC0yNDE2MzAzNDAsLTEyNjg3NzI4NzldfQ==
-->