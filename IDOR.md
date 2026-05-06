# Insecure Direct Object Reference (IDOR)

## 📌 Overview

Insecure Direct Object Reference (IDOR) is an access control vulnerability that occurs when an application exposes internal object references without properly validating user authorization.

Attackers can manipulate identifiers such as:

* User IDs
* File names
* Order numbers
* API keys
* UUIDs

to access unauthorized resources or perform actions on behalf of other users.

---

# 🧠 What is IDOR?

IDOR vulnerabilities occur when applications trust user-supplied object references without verifying whether the authenticated user is allowed to access the requested resource.

Example vulnerable request:

```http id="3l8t0y"
GET /profile?id=102 HTTP/1.1
```

Changing the ID may expose another user's data:

```http id="u9f0wa"
GET /profile?id=103 HTTP/1.1
```

---

# 🔥 Common IDOR Targets

Attackers commonly test:

* User profiles
* Invoice downloads
* API endpoints
* Admin panels
* File storage systems
* Chat applications
* Password reset flows

---

# 🔍 Identifying IDOR Vulnerabilities

## Common Indicators

* Sequential numeric IDs
* UUIDs exposed in URLs
* Predictable object references
* Missing authorization checks
* Sensitive API responses

---

# 🚀 Exploitation Methodology

## Step 1 — Identify Object References

Look for:

* `id=`
* `user=`
* `account=`
* `document=`
* UUID values

Example:

```http id="q3yxv8"
GET /api/orders/1001 HTTP/1.1
```

---

## Step 2 — Modify the Identifier

Change the reference:

```http id="jlwmxy"
GET /api/orders/1002 HTTP/1.1
```

---

## Step 3 — Observe the Response

Check whether:

* Unauthorized data is exposed
* Another user’s information becomes accessible
* Actions succeed without authorization

---

# 💥 Example Vulnerable Scenario

Vulnerable endpoint:

```http id="qz3w8l"
GET /download?file=report_102.pdf HTTP/1.1
```

Modified request:

```http id="7vhk2n"
GET /download?file=report_103.pdf HTTP/1.1
```

If the application returns another user’s file without authorization checks, an IDOR vulnerability exists.

---

# 🔬 API IDOR Example

Example REST API request:

```http id="9wrx2k"
GET /api/v1/users/15 HTTP/1.1
Authorization: Bearer token
```

Modified request:

```http id="4mg5qn"
GET /api/v1/users/16 HTTP/1.1
```

Weak backend authorization may expose sensitive user data.

---

# ⚠ Impact

Successful IDOR exploitation may lead to:

* Unauthorized data access
* Account takeover
* Sensitive information disclosure
* Privilege escalation
* Financial data exposure
* Administrative compromise

---

# 🛡 Prevention

## Recommended Mitigations

### Implement Proper Authorization Checks

Verify access permissions on the server side for every request.

---

### Use Indirect Object References

Avoid exposing internal identifiers directly.

---

### Apply Role-Based Access Control (RBAC)

Ensure users only access authorized resources.

---

### Validate Ownership

Example:

```python id="3c5mza"
if request.user.id != resource.owner_id:
    return 403
```

---

# 🧰 Tools Used

* Burp Suite
* Burp Repeater
* Burp Intruder
* Browser Developer Tools
* PortSwigger Web Security Academy

---

# 📚 Key Learning

IDOR vulnerabilities arise from broken access control rather than complex exploitation techniques.

Even simple identifier manipulation can expose highly sensitive information if authorization is not properly enforced.

Understanding access control testing is essential for real-world web application penetration testing and bug bounty hunting.

---

# 🏷 Tags

`#IDOR` `#AccessControl` `#BurpSuite` `#OWASP` `#WebSecurity`
