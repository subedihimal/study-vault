---
tags:
  - study
---
**Exponential backoff** is a retry strategy where a system waits **longer and longer** between retry attempts after failures. This helps prevent overwhelming a server during temporary outage.

Operation at t=0  -> failed
retry at t=1  -> failed
retry at t=2 -> failed
retry at t=4 -> failed
retry at t=8 -> failed
retry at t=16 ->failed
retry at t=32  -> and so on..

You retry after exponentially larger amount of time

---

## What do u do IF all RETRIES KEEP ON FAILING

### DLQ and Circuit Breakers

**DLQ (Dead Letter Queue)**
 DLQ says that after a N number of retries and still failing we know that there is some bigger issue. So we make a dedicated queue and add a payload that has all the details of api call and logs or errors. A technician can later fix the issue with the details from the dead letter queue.

**Circuit Breaker Pattern**
A Circuit Breaker works as a proxy for operation that may fail. It monitors the number of recent failures and use this information to decide whether to allow the operation to proceed or not.

The circuit Breaker can have 3 different types of states
- Closed (Allows request  calls and is monitoring) **(Circuit is closed meaning the current is flowing)**
	The proxy allows the service to be called and is in monitoring mode. It counts the number of failures if it exceeds a specific threshold in a certain time period it places the proxy into an open state. 
	
- Open (**Circuit is open meaning current is not flowing)**
	The proxy stops the request from the application immediately and returns an exception.
	
- Half -Open
	A few number of requests are allowed to pass through. If those requests pass then the circuit is changed to closed. If those requests fails then again the circuit is set to open.

## Conclusion
These mechanism saves unnecessary network calls, helps not to overwhelm a already struggling server, Less duplicate logs and better error handling.