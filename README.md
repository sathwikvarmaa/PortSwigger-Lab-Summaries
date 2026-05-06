# PortSwigger Web Security Notes

A curated collection of practical web security notes, payloads, exploitation methodologies, and vulnerability writeups based on PortSwigger Web Security Academy labs.

This repository focuses on understanding real-world web vulnerabilities through hands-on practice, structured documentation, and practical exploitation techniques used during web application penetration testing.

---

# 📚 Topics Covered

## 🔥 Cross-Site Scripting (XSS)

* Reflected XSS
* Stored XSS
* DOM XSS
* HTML Context Injection
* JavaScript Context Injection
* Filter Bypass Techniques

---

## 🗄 SQL Injection (SQLi)

### Classic SQL Injection

* Authentication Bypass
* UNION Attacks
* Column Enumeration
* Database Enumeration
* Data Extraction

### Blind SQL Injection

* Boolean-Based SQLi
* Time-Based SQLi
* Error-Based SQLi
* Out-of-Band (OAST) SQLi

---

## 🔐 Cross-Site Request Forgery (CSRF)

* CSRF Exploitation
* Token Validation Flaws
* Referer Bypass
* SameSite Cookie Issues

---

## 🧩 Insecure Direct Object References (IDOR)

* Horizontal Privilege Escalation
* API IDOR
* File Access Vulnerabilities
* Access Control Testing

---

## 🛡 Authentication & Access Control Flaws

* Broken Authentication
* Session Management Issues
* Privilege Escalation
* MFA Bypass
* Access Control Weaknesses

---

# 📂 Repository Structure

```txt id="6mqf8x"
PortSwigger-Web-Security-Notes/
│
├── XSS/
│   ├── reflected-xss-html-context.md
│   ├── dom-xss-document-write.md
│
├── SQLi/
│   ├── Classic-SQLi/
│   └── Blind-SQLi/
│
├── CSRF/
├── IDOR/
├── Auth-Flaws/
│
├── Payloads/
├── Methodology/
└── README.md
```

---

# 🧰 Tools Used

* Burp Suite
* Burp Repeater
* Burp Intruder
* Burp Collaborator
* Browser Developer Tools
* Kali Linux

---

# 🎯 Purpose

This repository serves as:

* A cybersecurity learning resource
* A practical VAPT knowledge base
* A bug bounty methodology reference
* A personal web security documentation archive

The goal is to improve practical web application penetration testing skills through hands-on vulnerability analysis and exploitation.

---

# ⚠ Disclaimer

This repository is intended strictly for educational purposes and authorized security testing only.

Do not use these techniques against systems without proper permission.

---

# 🏷 Topics

`Web Security` `Burp Suite` `OWASP` `VAPT` `Bug Bounty` `XSS` `SQLi` `CSRF` `IDOR` `Authentication`

---

# ⭐ Acknowledgement

Labs and learning material are based on:

* PortSwigger Web Security Academy
* OWASP Web Security Testing Methodology
