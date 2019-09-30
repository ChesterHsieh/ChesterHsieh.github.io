# Concept application
## Compare two list
In the other programming language, this idea need such double for loop
In SQL can be write  as **NOT IN** to achieve this concept

[Sales-Analysis]([https://leetcode.com/problems/sales-analysis-ii/](https://leetcode.com/problems/sales-analysis-ii/))

## Time Stamp
**DATEADD()**
**DATEDIFF()**
Example SELECT  DATEDIFF(year,  '2017/08/25',  '2011/08/25')  AS  DateDiff;
**BETWEEN** can be apply to date format.



# Question STACK
why cast ?
```SQL
SELECT s.product_id, product_name
FROM Sales s
LEFT JOIN Product p
ON s.product_id = p.product_id
GROUP BY s.product_id
HAVING MIN(sale_date) >= CAST('2019-01-01' AS DATE) AND
       MAX(sale_date) <= CAST('2019-03-31' AS DATE)
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM0OTEwNzY5NiwxMDk5MTM5MDUzLDE5NT
IzODIwODIsMTc0MjUyMjU5OV19
-->