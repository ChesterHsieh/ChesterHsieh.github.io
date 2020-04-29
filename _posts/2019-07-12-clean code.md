---
layout:     post
title:      CLEAN CODE reivew
subtitle:   Rule of thumb = only thing can remain in my mind when coding
date:       2019-07-12
author:    Chester
catalog: true
tags:

---
# Intro
SPR: simple rule policy. 
Clean code is a more than 400 pages book, it's extraordinary concepts inspire many many programmer, however, human beings especially coders have very poor memorization. Simple rule principle is sth I found that can summon whole block of knowledge. Instead of well-explanation or second re-work, this article is nothing but just knowledge index. 


# Variable naming
**Hungarian** notation was once the best helper to save time on debugging, nonthers 

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

# CH 10 Class
Before I start to explore this chapter, I've had many questions into this part. For a coder, he/she might come from different background or learning path. Me, the first job is embedded engineer, then coding Labview, and now being data scientist. Whole 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0Njk1Mzk2MzcsMTU2NzAyMzUxMiwxNT
AzNTE5MjQzLDE4ODY5MzA2ODgsLTE1OTYxNzIwOTUsOTIxODYz
MzEzLC00MDM2MTgwNjcsLTE1MjIxMzM1MDcsLTIwMzM2MzE2MT
IsLTExNzcwMjk0NjgsLTQyMzA2NDAxMywtMTQ3Njc2MzQ1OCwt
MTI5NTIwMDkzMSw4ODk5ODEzOCwxMDAxNTY4OTc2LDE2NjY3ND
QyNzksLTIxMzc5NDQ1MTAsMzQxOTM1ODY4LDE2MDUxMTE1MTQs
MTMzMTQ4MzQyMV19
-->