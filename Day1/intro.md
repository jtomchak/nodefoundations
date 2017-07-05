##Node
* non-blocking I/O model (asynchronous)
* execute JavaScript outside of a browser
* REPL is an acronym for Read-Eval-Print-Loop.
* perfect for microservices architecture.
* Rich ecosystem, With about 350,000 tools available in the npm registry as of now, and over 10,000 new ones being published every week
* Node.js, these are real-time applications with intense I/O, requiring speed and scalability.
  * social networks, gaming apps, live chats or forums as well as stock exchange software or ad servers, where speed is everything.
  * Not all sunshine
    * Node.js is a single-threaded environment, 
    *  callback hell, “situation where callbacks are nested within other callbacks several levels deep, potentially making it difficult to understand and maintain the code.”
    * Immaturity of tooling 2009

[Monolith vs MicroService](https://www.altexsoft.com/wp-content/uploads/2016/11/The-difference-between-the-monolithic-and-microservices-architecture-1.png)


---

##Import / Export
* must be exported via modules to be able to import
* value or object literial
* Detection of CommonJS vs. ESM
* Resource
  * [ARTICAL](https://hackernoon.com/node-js-tc-39-and-modules-a1118aecf95e)
  * [PROCESS](https://cdn-images-1.medium.com/max/1600/1*W9dyBkQ7nRT_YiaZupFhaw.png)
  * [WRAPING](https://cdn-images-1.medium.com/max/1600/1*Rn5xTqjKdPZuG7VnqMzN1w.png)


##Middleware 
* Make changes to the request and the response objects.
* End the request-response cycle
* data validation and security on the server
* next() keyword is optional, don't need to include it your function isn't going to use it
* If the current middleware function does not end the request-response cycle, it must call next() to pass control to the next middleware function. Otherwise, the request will be left hanging.
* Types of middleware
  * Application-level middleware
    * .get (All HTTP Methods)
  * Router-level middleware
    * router.get or router.route()
  * Error-handling middleware
    * (err, req, res, next)
    * the 404 at the bottom of express
  * Built-in middleware
    * only serve-static
    * serve files from within a given root directory
  * Third-party middleware  
    * cookieParser expamle
    * so many middles ware

  #Super simple middleware
  ```app.use((req, res, next) => {
  console.log('I hear you, it's a request!!!!!!');
  next();
});
```