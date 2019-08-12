# Intro
SPR: simple rule policy. 
This document is mean to collect all the simple rule and try to explain my way as much as possible.
# Variable naming
- 避免誤導. List, 不應該出現在變數..
	=> 這跟匈牙利命名法,現在IDE take care them. 所以 python 這種語言更加的用不到...
	=> 還有Tab 是現代IDE都有的. 必須思考到使用者根本不看說明....variable本身提供足夠多的訊息
- 每一次 commit 都要比上一次更乾淨.  如同童軍一樣.
- 所有的function應該儘量服膺一個目的而已
- 有利於搜尋,  這也就代表說過於短的文字不利於程式編碼.


## PEP8-Basic naming rule
- function: lower_and_underline
- variable: lower_and_underline
- class: CapWords

# Function
## Refactoring! 
**As key to craft the function is to remember all the simple rule and follow it all the time**. Really? 
I can't do it as my first trial for some function. Design pattern before code is a proper way to avoid produce shit code. However, it's not possible for everyone. Refactoring is the 
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

Follow 上面function的原則. 如果需要在function中作例外處理.  Try 一定是寫在最頂頭.  也不會有別的Code跟在finally or else clause
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEzNjQxOTYwNiwtMjAzMzYzMTYxMiwtMT
E3NzAyOTQ2OCwtNDIzMDY0MDEzLC0xNDc2NzYzNDU4LC0xMjk1
MjAwOTMxLDg4OTk4MTM4LDEwMDE1Njg5NzYsMTY2Njc0NDI3OS
wtMjEzNzk0NDUxMCwzNDE5MzU4NjgsMTYwNTExMTUxNCwxMzMx
NDgzNDIxXX0=
-->