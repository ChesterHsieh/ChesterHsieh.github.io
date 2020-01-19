# Primary section
- join
- Window function
- Aggregate
- Date data 
- Data type
- Logic Process
# Join
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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNzU3Mjg5MTddfQ==
-->