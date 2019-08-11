# Variable naming
- 避免誤導. List, 不應該出現在變數..
	=> 這跟匈牙利命名法,現在IDE take care them. 所以 python 這種語言更加的用不到...
	=> 還有Tab 是現代IDE都有的. 必須思考到使用者根本不看說明....variable本身提供足夠多的訊息
- 每一次 commit 都要比上一次更乾淨.  如同童軍一樣.
- 所有的function應該儘量服膺一個目的而已
- 有利於搜尋,  這也就代表說過於短的文字不利於程式編碼.


## CI/CD + PEP8補充
PEP8
# Function
# Exception
Prefer doing exception instead of running error code. 有一個絕大的好處, 就是可以切割exception的處理機制. 以python為例子.  可以透過繼承 Exceptions class 去創造屬於自己的exception type. 
```python
if deletePage(page) == E_OK:
	react(page)
else:
	if deletePage(page)== E_invalidPage:
		reactInvalidPage()
	else:
		doSthElse()

try:
	deletePage(page)
except E_invalidPage:
	reactInvalidPage()
except B:
else:
	doSthElse()
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1OTcyNzMzMzYsLTEyOTUyMDA5MzEsOD
g5OTgxMzgsMTAwMTU2ODk3NiwxNjY2NzQ0Mjc5LC0yMTM3OTQ0
NTEwLDM0MTkzNTg2OCwxNjA1MTExNTE0LDEzMzE0ODM0MjFdfQ
==
-->