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
eyJoaXN0b3J5IjpbMjQzMTA1Nzk1XX0=
-->