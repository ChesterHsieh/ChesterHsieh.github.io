# Concept application
## Compare two list
In the other programming language, this idea need such double for loop
In SQL can be write  as **NOT IN** to achieve this concept

[Sales-Analysis]([https://leetcode.com/problems/sales-analysis-ii/](https://leetcode.com/problems/sales-analysis-ii/))




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
eyJoaXN0b3J5IjpbNjg0NzYxNDk4XX0=
-->