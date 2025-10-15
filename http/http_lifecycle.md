# 🌐 Simple Example: How a Webpage Loads

Let’s see **what happens when you visit a website** — step by step.

---

### 🧭 Example: You open `https://example.com/hello`

---

### 📨 Step 1 — Browser Sends a Request

Your browser asks the server for the page.

```http
GET /hello HTTP/1.1
Host: example.com
```

**Meaning:**

* `GET` → You’re asking for a page.
* `/hello` → The page you want.
* `Host` → The website name.

---

### 📩 Step 2 — Server Sends a Response

The website replies with the page.

```http
HTTP/1.1 200 OK
Content-Type: text/html

<html><body>Hello, World!</body></html>
```

**Meaning:**

* `200 OK` → Everything is fine.
* `Content-Type` → It’s sending HTML.
* The last line → What you actually see on the screen.

---

### 🔁 Step 3 — What Happens Behind the Scenes

```
Browser (You)  ───▶  Request  ───▶  Server
Browser (You)  ◀───  Response (HTML Page)  ◀───  Server
```

Your browser reads the HTML and shows **“Hello, World!”**.

---


### 🧠 Key Idea

* **Browser = Client** (asks for the page)
* **Server = Website** (sends the page)
* The process of **Request → Response** is how all websites work.
