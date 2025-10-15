# 🌐 What is `curl` 

`curl` is a **command** you use in the terminal to talk to a **website or API**.
It sends a **request** and shows you the **response** — just like your browser does, but in text form.

It works on **Windows, Mac, and Linux**.

---

### 🧪 We’ll use a test website: [https://reqres.in](https://reqres.in)

---

### 1️⃣ **GET** → Read data

Get users:

```bash
curl https://reqres.in/api/users?page=2
```

➡ Shows user details (like a list of users).

---

### 2️⃣ **POST** → Add new data

Create a user:

```bash
curl -X POST https://reqres.in/api/users \
  -H "Content-Type: application/json" \
  -d '{"name": "Wania", "job": "Developer"}'
```

➡ Adds a new user with name and job.

---

### 3️⃣ **PUT** → Change all data

Update the whole user info:

```bash
curl -X PUT https://reqres.in/api/users/2 \
  -H "Content-Type: application/json" \
  -d '{"name": "Wania", "job": "Senior Dev"}'
```

➡ Replaces old data with new one.

---

### 4️⃣ **PATCH** → Change part of data

Update just one thing:

```bash
curl -X PATCH https://reqres.in/api/users/2 \
  -H "Content-Type: application/json" \
  -d '{"job": "Engineer"}'
```

➡ Changes only the job.

---

### 5️⃣ **DELETE** → Remove data

```bash
curl -X DELETE https://reqres.in/api/users/2
```

➡ Deletes the user.

---

### 6️⃣ **HEAD** → Get only headers

```bash
curl -I https://reqres.in/api/users/2
```

➡ Shows only info like status and content type, not the data.

---

### 7️⃣ **OPTIONS** → See what actions are allowed

```bash
curl -X OPTIONS -i https://reqres.in/api/users/2
```

➡ Shows allowed methods like GET, POST, DELETE, etc.

---

### 🧾 Quick Summary

| Action          | Method  | What It Does        |
| --------------- | ------- | ------------------- |
| Read            | GET     | See data            |
| Create          | POST    | Add data            |
| Replace         | PUT     | Change all data     |
| Update          | PATCH   | Change part of data |
| Delete          | DELETE  | Remove data         |
| Headers only    | HEAD    | See info only       |
| Allowed actions | OPTIONS | See what’s possible |

---

### 💡 Simple Idea

`curl` helps you **send and see web requests** — it’s like a text-based browser for developers.
