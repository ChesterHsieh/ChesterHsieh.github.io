# SOLID 老實說
## Dependency inversion principle
DIP 概念其實沒有這們炫砲. 為了減少改動下層結構的痛苦而來的. 我這邊記錄一下我實際上的案例
```python
Class MYSQL_HANDLER():
	def __init__(self):
		#import some config
		configs = json.loads("./config.json")
		self.handler = SOME_DB_CLIENT()
	def query_for_user_inf(self):
		self.handler.query(
			"""
			SELECT * FROM db.user_info
			"""
		)
```
縱然 call function其實很方便啦. 因為自動提示一下就跑出來有什麼已經內建好的SQL query. 然而就是這個問題. 如果我有一個應用. 是透過這個handler 去使用user info. 當Database結構改變. 其實所以的程式都會報錯, 例如 database columns 或db本身服務遷移. 我覺得以現在database重構如此頻繁, 把所以資料來源當作是一個外設的硬體下去做思考和抽象化非常重要.

比較簡單的一點的做法
```python

```
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTQ4MzQ0MjM3LDI5NDYxNTk2LC0xOTgyMz
M5NDMxXX0=
-->