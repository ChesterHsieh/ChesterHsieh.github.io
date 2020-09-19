# SOLID 老實說
## D-
DIP 概念其實沒有這們炫砲. 為了減少改動下層結構的痛苦而來的. 我這邊記錄一下我實際上的案例
```python
Class MYSQL_HANDLER():
	def __init__(self):
		#import some config
		configs = json.loads("./config.json")
		self.handler = SOME_DB_CLIENT()
	def
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNzE2MzQxNjgsLTE5ODIzMzk0MzFdfQ
==
-->