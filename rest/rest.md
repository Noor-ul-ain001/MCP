

# 🌐 REST (Representational State Transfer)

**REST** is a way to design web services that allows different systems to communicate easily over the internet.
It uses **HTTP** and focuses on **resources** (like users, products, posts) identified by URLs.

---

## 🔑 Main Principles of REST

1. **Client-Server**

   * The client (like a browser or app) and the server (which stores data) are separate.
   * They can work and update independently.

2. **Stateless**

   * Each request contains all the information needed.
   * The server doesn’t remember previous requests.

3. **Cacheable**

   * Responses can be saved (cached) to improve speed and reduce server load.

4. **Layered System**

   * The system can have multiple layers (like load balancers or proxies).
   * Clients don’t need to know if they talk to the main server or a middle layer.

5. **Uniform Interface**

   * Everything is accessed in the same way:

     * **Resources** identified by URLs (e.g., `/users/1`)
     * **HTTP methods** to perform actions:

       * `GET` – Read data
       * `POST` – Create data
       * `PUT` – Update data
       * `DELETE` – Remove data
     * **Responses** use standard codes like:

       * `200 OK`, `201 Created`, `404 Not Found`, `500 Server Error`

6. **Code on Demand (Optional)**

   * Servers can send code (like JavaScript) to clients.

---

## 💡 Example

| Action         | HTTP Method | Endpoint   | Description     |
| -------------- | ----------- | ---------- | --------------- |
| Get all users  | `GET`       | `/users`   | Retrieve users  |
| Get one user   | `GET`       | `/users/1` | Retrieve user 1 |
| Add a new user | `POST`      | `/users`   | Create a user   |
| Update user    | `PUT`       | `/users/1` | Update user 1   |
| Delete user    | `DELETE`    | `/users/1` | Delete user 1   |

---

## ⚙️ REST in Python (Simple Example)

```python
import requests

# GET request
response = requests.get("https://jsonplaceholder.typicode.com/posts/1")
print
```
