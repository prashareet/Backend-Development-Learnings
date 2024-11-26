# **MIDDLEWARES**  
A small attempt to simplify the understanding and use case of **Middlewares**  for backend development.

## **What is a Middleware in Simple Terms?**

To begin, we need to understand that a **Middleware** is nothing but a *JavaScript function*.  
Like many other functions in JavaScript — for example, a `sum` function that returns `a + b` — a middleware function also serves a specific purpose.

In **Express.js** (a Node.js library), middlewares are functions that have access to the **request (`req`)**, **response (`res`)** objects, and also take a third argument, **`next()`**, which is a function.

## **Reasons to Use Middlewares**

- **Modifying the request object:**  
  A middleware function can intercept the request object, modify it, and control its flow.  
- **Handling request flow:**  
  When a request reaches a middleware function, it has access to the **request object (`req`)**, which allows the middleware to:  
  - Stop the request.  
  - Edit or modify the request.  
  - Send the modified request back to the final route handler.

## **Code Snippet for Middleware Syntax**

The following code demonstrates how to use middleware to log request details and add a timestamp to the request object. It also includes a POST route to calculate the sum of two numbers.

```javascript
// Middleware function
function middleWare(req, res, next) {
    console.log(`Method is ${req.method}`);
    console.log(`Request URL is ${req.url}`);
    // Uncomment the next line to log the timestamp
    // console.log(`Timestamp is ${Date.now()}`);
    req.requestTime = Date.now();
    next();
}

// Use the middleware in the app
app.use(middleWare);

// POST route to calculate the sum of two numbers
app.post("/sum", function(req, res) {
    const a = parseInt(req.body.a);
    const b = parseInt(req.body.b);

    res.json({
        ans: a + b
    });
});






