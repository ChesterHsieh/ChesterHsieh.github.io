# Primary section
- join
- Window function
- Aggregate
- Date data 
- Data type
- Logic Process
- Variable
- Clause
# Join mulitple table
## UNION
leetcode 608
If the question can be divide and conque. Union can simply add the result.

## 
# Window function
Leetcode 185
```sql
FUNCTION() OVER ([ <PARTITION BY clause> ] 
	  [ <ORDER BY clause> ] 
	  [ <ROW or RANGE clause> ] )
```
It can share groupy by feeling and function(aggregate/rank)

## ROW_NUMBER
```sql
ROW_NUMBER ( ) 
OVER ( [ PARTITION BY value_expression , ... [ n ] ] order_by_clause )
```
## Producing a moving average and cumulative total



## RANK & DENSERANK
RANK gives you the ranking within your ordered partition. Ties are assigned the same rank, with the next ranking(s) skipped. So, if you have 3 items at rank 2, the next rank listed would be ranked 5.

DENSE_RANK again gives you the ranking within your ordered partition, but the ranks are consecutive. No ranks are skipped if there are ranks with multiple items.

| number   |      DENSERANK      |  RANK |
|----------|:-------------:|------:|
| 1|  1| 1 |
| 1 |1 |   1 |
| 2 | 2 | 3|
| 3 | 3 | 4 |

# Date data
## Time Stamp
- **DATEADD()**
- **DATEDIFF()**
	Example SELECT  DATEDIFF(year,  '2017/08/25',  '2011/08/25')  AS  DateDiff;
- **BETWEEN** can be apply to date format.

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
# Variable
# Clause
##
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzA3NDY0MzYzLDI0MTMwMjQ4NSw2OTY2ND
g5NTQsMTA0NzAwNjMyNSwtMTI0MDE0NjMxNCwxNTA1MDU1ODcs
MjAxMzQ5NjU3Nyw3NzM0NjUzNjEsLTE0NTYxNzkwMTNdfQ==
-->