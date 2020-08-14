# One Goal
To build xxx API .
- Sustainable
- Scalable

# Environment
## Docker
## Pycharm-testing
# APP

# Web
看起來明顯分成兩大不同陣營
- wsgi
- asgi
## WSGI
一開始為了將Server Code/Application Code 做區隔. Web Server Gateway interface相應而生.
- WSGI Framework:
	- Django
	- Flask
- WSGI Servers
	- gunicorn
	- uWSGI
### WSGI limitation
- Web Socket並沒有被官方支援
- 沒有支援async/await
## ASGI


# Terminologies
- websocket
> The **WebSocket API** is an advanced technology that makes it possible to open a two-way interactive communication session between the user's browser and a server. With this API, you can send messages to a server and receive event-driven responses without having to poll the server for a reply.

兩個關鍵字. Poll/two-way. Restful API 是無法達成這樣的功能. 如果User需要某個資料, user需要一直去詢問亦即polling. Two-way: 在單一封包中沒法兼顧聽和說這件事. (有些用Duplex)

- 

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNDMyNjUwNTYsLTE0MjcwODMzOTAsLT
Q4MTk3NTg4Ml19
-->