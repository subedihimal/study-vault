## Call Stack

The **Call Stack** is where JavaScript keeps track of the functions it is currently running.

- Uses **LIFO (Last In, First Out)**.
    
- When a function is called, it is **added (pushed)** to the stack.
    
- When the function finishes, it is **removed (popped)** from the stack.
    
- JavaScript always runs the function at the **top** of the stack.
    
- Asynchronous callbacks can only run when the Call Stack is empty.


---

## Event Loop

The **Event Loop** manages when asynchronous callbacks are added to the Call Stack. Normal synchronous function calls are added to the Call Stack directly by JavaScript, **not** by the Event Loop. The Event Loop only handles asynchronous callbacks.

- JavaScript can only execute **one task at a time**.
    
- Asynchronous tasks (like `setTimeout` or `fetch`) are handled outside the Call Stack.
    
- When they finish, their callbacks wait in a queue.
    
- The Event Loop keeps checking if the **Call Stack is empty**.
    
- If it is empty, the Event Loop moves the next callback from the queue to the Call Stack.
    
- The Event Loop **adds** tasks to the Call Stack—it does **not** remove them.