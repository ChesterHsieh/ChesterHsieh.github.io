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

| id | p_id |
|-|:-:|
| 1  | null |
| 2  | 1    |
| 3  | 1    |
| 4  | 2    |
| 5  | 2    |


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
eyJoaXN0b3J5IjpbMTM1ODk0MjcwNF19
-->