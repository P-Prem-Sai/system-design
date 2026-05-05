# 🌐 HTTP Status Codes

## ⚡ Quick Revision

* **1xx → Informational**
* **2xx → Success**
* **3xx → Redirection**
* **4xx → Client Errors**
* **5xx → Server Errors**

---

## 📘 What are HTTP Status Codes?

HTTP status codes are **standard response codes** returned by servers to indicate the result of a client’s request.

---

## 🟢 1xx – Informational

These indicate the request was received and is being processed.

* **100 Continue** → Client should continue request
* **101 Switching Protocols** → Server switching protocols

---

## ✅ 2xx – Success

Request was successfully received and processed.

* **200 OK** → Request successful
* **201 Created** → Resource successfully created
* **202 Accepted** → Request accepted but not completed
* **204 No Content** → Success but no response body

💡 **Interview Tip**

* Use **201** for POST (resource creation)
* Use **204** when no response body is needed

---

## 🔁 3xx – Redirection

Further action is needed to complete the request.

* **301 Moved Permanently** → Resource moved permanently
* **302 Found** → Temporary redirect
* **304 Not Modified** → Use cached version

💡 **Interview Tip**

* **301 vs 302** is commonly asked
* **304** is important for caching

---

## ❌ 4xx – Client Errors

Client made a bad request.

* **400 Bad Request** → Invalid request
* **401 Unauthorized** → Authentication required
* **403 Forbidden** → Authenticated but no permission
* **404 Not Found** → Resource not found
* **405 Method Not Allowed** → Invalid HTTP method
* **408 Request Timeout** → Request took too long
* **409 Conflict** → Conflict with current state

💡 **Interview Tip**

* **401 vs 403** is a classic question

  * 401 → Not authenticated
  * 403 → Not authorized

---

## 💥 5xx – Server Errors

Server failed to fulfill a valid request.

* **500 Internal Server Error** → Generic server failure
* **501 Not Implemented** → Functionality not supported
* **502 Bad Gateway** → Invalid response from upstream server
* **503 Service Unavailable** → Server overloaded/down
* **504 Gateway Timeout** → Upstream server timeout

💡 **Interview Tip**

* **502 vs 504** difference is frequently asked

---

## 🔥 Common Interview Questions

### 1. Difference between 401 and 403?

* **401** → Authentication required
* **403** → Authentication done but access denied

### 2. When to use 201 vs 200?

* **201** → New resource created
* **200** → General success

### 3. What is 304 used for?

* Used in **caching** to avoid re-downloading resources

---

## 📌 Quick Cheat Sheet

| Category | Meaning       |
| -------- | ------------- |
| 1xx      | Informational |
| 2xx      | Success       |
| 3xx      | Redirection   |
| 4xx      | Client Error  |
| 5xx      | Server Error  |

---

## 🔗 Reference

* https://www.geeksforgeeks.org/computer-networks/what-are-http-status-codes/

---

## 🧠 Final Tip

Focus more on:

* **2xx, 4xx, 5xx**
* And real-world usage in API design

👉 That’s what matters in interviews.
