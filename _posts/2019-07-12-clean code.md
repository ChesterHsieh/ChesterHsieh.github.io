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
I can't do it as my first trial for some function. Design pattern before code is a proper way to avoid produce shit code. However, it's not possible for everyone. Refactoring is the compromise method to achieve clean code. 

**How to refactor giant god function 100~1000 lines?**
- promote it as a class

# Object OOP utopia
SRP:
Don't use OOP, go with procedure code.

Except:
Your code is going to provide outside world(client) ?! 我這邊有點困惑


# Formating
SRP:
- No 3 tabs
- One function never exceed 10 lines.

***TIP:*** IDE can help you adjust structure and check the some rule, blank line or indent.....

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

# Comment
SRP:
Don't use comment. It will fail to sync with code all as time passing. That mean the comment will lie the reader and next one take over your job.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA5OTczODg4MCwxODg2OTMwNjg4LC0xNT
k2MTcyMDk1LDkyMTg2MzMxMywtNDAzNjE4MDY3LC0xNTIyMTMz
NTA3LC0yMDMzNjMxNjEyLC0xMTc3MDI5NDY4LC00MjMwNjQwMT
MsLTE0NzY3NjM0NTgsLTEyOTUyMDA5MzEsODg5OTgxMzgsMTAw
MTU2ODk3NiwxNjY2NzQ0Mjc5LC0yMTM3OTQ0NTEwLDM0MTkzNT
g2OCwxNjA1MTExNTE0LDEzMzE0ODM0MjFdfQ==
-->