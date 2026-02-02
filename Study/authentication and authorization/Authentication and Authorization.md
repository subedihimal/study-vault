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
	![[10.png]]

	###Problem can occur in micro-service architecture like the session storage being hit a lot of times causing unnecessary traffic
	![[11.png]]
- Tokens: stateless
	No data storage happens in the server side. Every request is treated as independent request.
	![[12.png]]
	You don't have to do a db call every time in each service you can just have a auth service that deciphers the token and lets you know if the user is valid or not.
	The token can be deciphered with a secret key and it includes data about the user.
## Deep Dive into Token Based Authentication

1st time authentication 
email + password -> validate credentials -> issue token

### JWT TOKENS
format -> xxxxx.yyyyy.zzzzz
x -> first part ->  Headers
y->middle part -> payload
z -> last part -> signature

Each part is implemented in form of json except signature and are encoded in base64 encoding

We use signing algorithm to ensure no one has tempered with the token.
![[13.png]]

## JWT IMPLEMENTATION IN MICROSERVICE ARCHITECTURE

Rather then having each service hit the authentication service every time there is internal transfer of data. We can create an API gateway that acts as a barrier before u are able to interact with the micro service.
The micro services stay in a type of intranet only accessible via the api gateway.

![[14.png]]
**Authorization**
Defining what you are allowed to do as a valid user in the platform.