# Authentication & Access Control Flaws

## 📌 Overview

Authentication and Access Control flaws occur when web applications fail to properly verify user identity or incorrectly enforce permissions.

These vulnerabilities can allow attackers to:

* Bypass login mechanisms
* Escalate privileges
* Access sensitive functionality
* Compromise user accounts
* Gain administrative access

Authentication flaws are among the most critical vulnerabilities in modern web applications.

---

# 🧠 Authentication vs Authorization

## Authentication

Authentication verifies:

> "Who are you?"

Examples:

* Username & password
* MFA
* OAuth
* JWT tokens

---

## Authorization

Authorization verifies:

> "What are you allowed to do?"

Examples:

* User roles
* Admin access
* Object ownership
* Resource permissions

---

# 🔥 Common Authentication Flaws

## Weak Password Policies

Applications allowing:

* Short passwords
* Common passwords
* No rate limiting

are vulnerable to brute force attacks.

---

## Username Enumeration

Applications reveal whether usernames exist through:

* Different error messages
* Different response times
* Different status codes

Example:

```http id="j3k4zl"
Invalid password
```

vs

```http id="x8p2wd"
User does not exist
```

---

## Brute Force Attacks

Attackers automate login attempts using:

* Password spraying
* Credential stuffing
* Dictionary attacks

---

## Broken Session Management

Weak session handling may involve:

* Predictable session tokens
* Session fixation
* Session hijacking
* Tokens not invalidated after logout

---

## Multi-Factor Authentication Bypass

Improper MFA implementations may allow:

* Direct endpoint access
* Session reuse
* Token manipulation

---

# 🔥 Common Access Control Flaws

## Vertical Privilege Escalation

Regular users gain admin functionality.

Example:

```http id="w9kx4n"
GET /admin HTTP/1.1
```

---

## Horizontal Privilege Escalation

Users access resources belonging to other users.

Example:

```http id="0p9wvl"
GET /account?id=102 HTTP/1.1
```

---

## Parameter-Based Access Control

Applications rely on client-side parameters:

```http id="v8n2ye"
role=admin
```

Attackers may manipulate these values.

---

# 🚀 Exploitation Methodology

## Step 1 — Analyze Authentication Flow

Check:

* Login requests
* Session cookies
* MFA flow
* Password reset mechanisms

---

## Step 2 — Test for Enumeration

Observe:

* Error messages
* Response length
* Response timing

---

## Step 3 — Test Access Controls

Modify:

* URLs
* IDs
* Roles
* HTTP methods
* Hidden parameters

---

## Step 4 — Attempt Privilege Escalation

Check whether unauthorized functionality becomes accessible.

---

# 💥 Example Vulnerable Request

```http id="3k7wzn"
GET /admin/deleteUser?username=carlos HTTP/1.1
Cookie: session=abc123
```

If a regular user can access this endpoint, the application contains broken access control.

---

# ⚠ Impact

Authentication and access control flaws may lead to:

* Account takeover
* Administrative compromise
* Sensitive data exposure
* Privilege escalation
* Full application compromise

---

# 🛡 Prevention

## Recommended Mitigations

### Strong Authentication

* Enforce strong password policies
* Implement MFA
* Use secure password hashing

---

### Secure Session Management

* Rotate session tokens
* Expire sessions properly
* Use Secure and HttpOnly cookies

---

### Proper Authorization Checks

Validate permissions server-side for every request.

---

### Implement Least Privilege

Users should only access required functionality.

---

### Use Rate Limiting

Prevent brute force attacks using:

* CAPTCHA
* Account lockouts
* Request throttling

---

# 🧰 Tools Used

* Burp Suite
* Burp Intruder
* Burp Repeater
* Browser Developer Tools
* PortSwigger Web Security Academy

---

# 📚 Key Learning

Authentication and access control vulnerabilities often arise from flawed application logic rather than technical complexity.

Testing authentication flows, session handling, and permission enforcement is critical during real-world penetration testing and bug bounty hunting.

---

# 🏷 Tags

`#Authentication` `#AccessControl` `#PrivilegeEscalation` `#BurpSuite` `#OWASP`
