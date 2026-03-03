# Short Response Questions

Answer each question below in your own words. Aim for 3–5 sentences per answer. Be specific — use the exact terms and concepts from the lesson.

Your responses will each be evaluated out of 6 points. You can earn 3 points for writing quality and 3 points for the accuracy and precision of the technical content per question.

---

## Question 1: Express vs `node:http`

Express is described as a framework that "wraps" `node:http`. What does that mean? Compare how you would handle a `GET /api/users` request in `node:http` versus in Express. What does Express do for you automatically that you had to write manually with `node:http`?

**Your answer here**:
Express is a framework that wraps `node:http`, meaning that it abstracts the process of creating a server and server endpoints. Whereas with the node:http module, you have to use if/else statements to create endpoints and a callback function to create the server. Express shortens that process. Creating a server uses `express();` and instead of if/else statements, we create **controllers** which are then passed into `app.get()` along with the endpoint `url`. Express automatically writes the header with the status code and content type, stringifies the JSON, and ends the connection using `res.send`.

---

## Question 2: Endpoints, Controllers, and Middleware

What are **controllers** and **middleware** in Express? What are each responsible for and how do they work together to handle incoming requests?

**Your answer here**:
**Controllers** are functions in Express that we pass into `app.get()` to tell the server what data to send back when the **client** hits an endpoint. **middleware** is a function that we invoke for all endpoints before any of them return a response and pass control to the next middleware or controller using `next();`. They work together to handle requests as the middleware can log information like time of request, date of request, and the endpoint that was hit, while the controller can send back the data to the client.

---

## Question 3: Query Strings and Route Parameters

How are **query strings** and **route parameters** similar? How are they different? In your answer, provide an example of when you would use each.

**Your answer here**:
**Query strings** and **route parameters** are similar as they are added onto already existing endpoints usually to modify the data already being returned for specific conditions before returning. They're different because query strings consist of filtering while route parameters consist of finding. I would use query strings when filtering for any tags or genres relating to multiple objects in a response. I would use route parameters when I want to return one object that corresponds to the number/id given.

---

## Question 4: Same-Origin Requests

For API fetch calls from a client-side application, explain the difference between fetching from endpoints with relative paths like `/api/quotes` and fetching from endpoints with a full URL like `https://dog.ceo/api/breeds/image/random`. Why do we not send a fetch using a url like `http://localhost:8080/api/quotes`?

**Your answer here**:
We don't fetch from endpoints with a full URL when working with our own backend server because hardcoding the full domain name can lead to issues when the application is deployed to a different domain. Instead, we can use relative paths like `/api/quotes` to ensure more flexibility as they'll automatically use the current domain name, preventing any future issues if the domain name is modified or changed.
