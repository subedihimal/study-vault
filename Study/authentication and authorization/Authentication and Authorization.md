---
tags:
  - study
---

**Authentication**
Process of proving who you are and prove the fact that you are actually who you claim to be.
Basics Need of authentication
- Registration

**How to keep the user authenticated**
- Session: stateful
	Some info is stored in the server side. This storage is used to check if user is valid or not
	![[1.png]]

	###Problem can occur in micro-service architecture like the session storage being hit a lot of times causing unnecessary traffic
	![[2.png]]
- Tokens: stateless
	No data storage happens in the server side. Every request is treated as independent request.
	![[3.png]]
	You don't have to do a db call every time in each service you can just have a auth service that deciphers the token and lets you know if the user is valid or not.
	The token can be deciphered with a secret key and it includes data about the user.
