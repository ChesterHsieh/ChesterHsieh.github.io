# Primary section
- join
- Window function
- Aggregate
- Date data 
- Data type
- Logic Process
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
# Logic Process
## IF ELSE statement
Leetcode 608
```sql
IF DATENAME(weekday, GETDATE()) IN (N'Saturday', N'Sunday')
       SELECT 'Weekend';
ELSE 
       SELECT 'Weekday';
```

Here's the example show, if else result can be directly use in other function.
```sql
SELECT Request_at as Day,
       ROUND(COUNT(IF(Status != 'completed', TRUE, NULL)) / COUNT(*), 2) AS 'Cancellation Rate'
FROM Trips
WHERE (Request_at BETWEEN '2013-10-01' AND '2013-10-03')
      AND Client_id NOT IN (SELECT Users_Id FROM Users WHERE Banned = 'Yes')
GROUP BY Request_at;
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NTYxNzkwMTNdfQ==
-->