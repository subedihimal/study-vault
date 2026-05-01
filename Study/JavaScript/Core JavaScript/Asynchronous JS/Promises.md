A **Promise** is an object that represents the **future result of an asynchronous operation**
Promises has 3 stages
- Pending
- Fulfilled
- Rejected



```js
function prepareOrder(dish) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (!dish) {
                reject(new Error("No Dish is there"));
                return;
            }
            console.log(`${dish} is ready`);

            resolve({ dish, status: "prepared" });
        }, 100);
    });
}

function pickupOrder(order) {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log(`${order.dish} is picked up`);

            resolve({ ...order, status: "ready" });
        }, 100);
    });
}

function deliverOrder(order) {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log(`${order.dish} is delivered`);

            resolve({ ...order, status: "delivered" });
        }, 100);
    });
}

prepareOrder("Chai")
    .then(order => pickupOrder(order))
    .then(order => deliverOrder(order))
    .catch(err => console.error(err.message));

```


---


**Before Promises  - > (CalBack Hell)❌**
```js
function prepareOrderCB(dish, cb){
    setTimeout(() => cb(null, { dish, status: "prepared" }), 100);
}

function pickupOrderCB(order, cb){
    setTimeout(() => cb(null, { ...order, status: "picked-up" }), 100);
}

function deliverOrderCB(order, cb){
    setTimeout(() => cb(null, { ...order, status: "delivered" }), 100);
}

prepareOrderCB("Biryani", (err, order) => {
    if (err) return console.log(err);

    pickupOrderCB(order, (err, order) => {
        if (err) return console.log(err);

        deliverOrderCB(order, (err, order) => {
            if (err) return console.log(err);

            console.log(`${order.dish}: ${order.status}`);
        });
    });
});

//Output: Biryani: delivered

```
