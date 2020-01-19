# Primary section
- join
- Window function
- Aggregate
- Date data 
- Data type
- Logic Process
- Variable
# Join mulitple table
## UNION
leetcode 608
If the question can be divide and conque. Union can simply add the result.

## 
# Window function

```sql
OVER ([ <PARTITION BY clause> ] 
	  [ <ORDER BY clause> ] 
	  [ <ROW or RANGE clause> ] )
```

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

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMDI0MTIxMzUsMjAxMzQ5NjU3Nyw3Nz
M0NjUzNjEsLTE0NTYxNzkwMTNdfQ==
-->