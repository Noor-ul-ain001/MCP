

# 🌐 What is REST?

> **REST** (Representational State Transfer) is a **way to design web services** so that **computers can easily communicate** over the internet using **HTTP**.

---

## ❓ Is REST a Technology?

No. REST is **not** a:

* Programming language
* Software
* Tool
* Protocol (like HTTP or FTP)

✅ It is a **design style** — a **set of rules** for building web APIs.

---

## 🍔 Real-Life Example

Think of a **food delivery app**:

* You view restaurants
* Add items to cart
* Place an order
* Track your order

Each of these actions happens through **RESTful API calls** to the backend — exchanging data between your app (client) and server.

---

## 💬 REST Means

| Word                 | Simple Meaning                                                       |
| -------------------- | -------------------------------------------------------------------- |
| **Representational** | You get a *copy* of data (like JSON), not the actual database record |
| **State**            | The data or condition of something (like your order status)          |
| **Transfer**         | The exchange of data between client and server                       |

---

## ⚙️ How REST Works

1. **Resources** (like `/users`, `/orders`) are identified by **URLs**.
2. The **client** sends HTTP requests like:

   * `GET` → Read data
   * `POST` → Add new data
   * `PUT` → Update data
   * `DELETE` → Remove data
3. The **server** sends back a response (usually in **JSON**).

---

## 🛍️ Example: REST in a Shopping App

| Action            | Method   | URL           | Description            |
| ----------------- | -------- | ------------- | ---------------------- |
| View all products | `GET`    | `/products`   | Fetch list of products |
| View one product  | `GET`    | `/products/5` | Get product with ID 5  |
| Add product       | `POST`   | `/products`   | Add a new product      |
| Update product    | `PUT`    | `/products/5` | Replace product 5      |
| Delete product    | `DELETE` | `/products/5` | Remove product 5       |

---

## 🔑 6 REST Rules (Constraints)

1. **Client-Server** → UI and backend are separate.
2. **Stateless** → Each request is independent; server doesn’t remember past requests.
3. **Cacheable** → Responses can be saved to speed things up.
4. **Uniform Interface** → Same way to access all data (via HTTP methods).
5. **Layered System** → Middle layers (like proxies) can exist.
6. **Code on Demand (Optional)** → Server can send code (e.g., JavaScript) to the client.

---

# 🔗 HATEOAS (Hypermedia As The Engine Of Application State)

> HATEOAS means the **server guides the client** by sending links in responses — so the client always knows *what to do next*.

---

## 🧭 Real-Life Analogy

When you browse a website:

1. You start at the homepage
2. You see links like “About” or “Products”
3. You click to move forward — without memorizing URLs

✅ That’s exactly how **HATEOAS** works for APIs.

---

## 💡 Example (With vs Without HATEOAS)

### ❌ Without HATEOAS

Client must already know all URLs:

```
/users
/orders
/cart
```

If one changes, the app breaks.

---

### ✅ With HATEOAS

You start with one URL, and the server provides next steps:

```json
{
  "links": {
    "products": "/api/products",
    "cart": "/api/cart",
    "checkout": "/api/checkout"
  }
}
```

Now the client simply follows these links — no memorization needed!

---

## 🧱 Example JSON

```json
{
  "id": 1,
  "name": "Wania",
  "links": {
    "self": "/api/users/1",
    "update": "/api/users/1",
    "delete": "/api/users/1",
    "orders": "/api/users/1/orders"
  }
}
```

✅ The client can:

* View, update, or delete the user
* See their orders — all using server-provided links

---

## 🌟 HATEOAS Benefits

| Benefit         | Meaning                                     |
| --------------- | ------------------------------------------- |
| 🔄 Flexible     | Server can change URLs freely               |
| 🧭 Discoverable | Client can explore without hardcoding paths |
| 🔐 Secure       | Server controls what actions are visible    |
| 🧩 Evolvable    | New links can be added anytime              |

---

# ⚙️ What is Idempotence?

> **Idempotence** means doing the same action multiple times has the **same result** as doing it once.

---

## 🧃 Example

* Turn off a light once → it’s off ✅
* Turn it off 5 times → still off ✅

➡️ That’s **idempotent** (result doesn’t change).

---

## 🍕 Another Example

* “Cancel order” once or five times → still canceled ✅
* “Place order” five times → 5 new orders ❌ (not idempotent)

---

## 🌍 In HTTP

| Method    | Idempotent?  | Why                                                 |
| --------- | ------------ | --------------------------------------------------- |
| `GET`     | ✅            | Just reads data                                     |
| `HEAD`    | ✅            | Reads headers only                                  |
| `OPTIONS` | ✅            | Just asks what’s allowed                            |
| `PUT`     | ✅            | Replaces existing data                              |
| `DELETE`  | ✅            | Removes resource (already deleted after first time) |
| `POST`    | ❌            | Creates new data each time                          |
| `PATCH`   | ⚠️ Sometimes | Depends on implementation                           |

---

### ✅ Summary

> If repeating a request **doesn’t change the result**, it’s **idempotent**.
> If repeating it **creates or modifies new data**, it’s **not idempotent**.

