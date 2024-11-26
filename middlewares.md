# **MIDDLEWARES**  
A small attempt to simplify the understanding and use case of **Middlewares** and **CORS** for backend development.

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






