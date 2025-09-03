# 🛡️ Jr Penetration Tester – Burp Suite: The Basics

**Room:** [Burp Suite: The Basics](https://tryhackme.com/)  
**Path:** Junior Penetration Tester  
**Platform:** TryHackMe   

---

## 📖 Overview
This room introduced the **fundamentals of Burp Suite** for web application pentesting.  
I learned how to set up Burp, intercept traffic, and use its core features such as Proxy, Repeater, and Intruder.  

---

## 📌 Progress Tracker
- [x] Task 1 – Introduction  
- [x] Task 2 – Installation & Setup  
- [x] Task 3 – Proxy Tab  
- [x] Task 4 – Target Tab  
- [x] Task 5 – Repeater Tab  
- [x] Task 6 – Intruder Tab  
- [x] Task 7 – Decoder & Comparer  
- [x] Task 8 – Sequencer  
- [x] Task 9 – Applying Burp in Workflow  

---

## ✅ Task-by-Task Summary

<details>
  <summary><strong>📝 Task 1 – Introduction</strong></summary>

- Learned what Burp Suite is and why it’s used in pentesting.  
- Difference between **Community** and **Professional** editions.  
- Overview of Burp components: Proxy, Repeater, Intruder, Decoder, Comparer, Sequencer.  

</details>

---

<details>
  <summary><strong>⚙️ Task 2 – Installation & Setup</strong></summary>

- Installed **Burp Suite Community Edition**.  
- Configured browser with **FoxyProxy** to route traffic.  
- Installed Burp’s **CA certificate** to intercept HTTPS.  

</details>

---

<details>
  <summary><strong>🔍 Task 3 – Proxy Tab</strong></summary>

- Intercepted and forwarded HTTP(S) requests.  
- Used filters to focus only on in-scope traffic.  
- Explored **HTTP history** for analyzing requests.  

</details>

---

<details>
  <summary><strong>🎯 Task 4 – Target Tab</strong></summary>

- Mapped endpoints and site structure.  
- Set **scope** to restrict testing targets.  
- Used **site map** for reconnaissance.  

</details>

---

<details>
  <summary><strong>♻️ Task 5 – Repeater Tab</strong></summary>

- Sent requests to Repeater for manual testing.  
- Modified parameters and replayed requests.  
- Observed server behavior for authentication and validation flaws.  

</details>

---

<details>
  <summary><strong>💣 Task 6 – Intruder Tab</strong></summary>

- Learned Intruder attack types: Sniper, Battering Ram, Pitchfork, Cluster Bomb.  
- Automated payload testing and brute forcing.  
- Discovered hidden fields and tested parameters.  

</details>

---

<details>
  <summary><strong>🔐 Task 7 – Decoder & Comparer</strong></summary>

- **Decoder:** Converted Base64, URL, and Hex encoded data.  
- **Comparer:** Compared responses to highlight subtle differences.  

</details>

---

<details>
  <summary><strong>🎲 Task 8 – Sequencer</strong></summary>

- Tested randomness of session tokens.  
- Understood weak entropy and session hijacking risks.  

</details>

---

<details>
  <summary><strong>🕵️ Task 9 – Applying Burp in Workflow</strong></summary>

- Applied Burp in a structured pentesting methodology:  
  **Recon → Exploitation → Analysis → Reporting**  
- Identified vulnerabilities such as:
  - SQL Injection (SQLi)  
  - Cross-Site Scripting (XSS)  
  - Insecure Direct Object References (IDOR)  
  - Weak session management  

</details>

---

## 🎯 Key Takeaways
- Burp Suite is an **essential toolkit** for web application pentesting.  
- Proper **proxy configuration** and **scope** setup improve efficiency.  
- Core tools (**Repeater** and **Intruder**) are the backbone of manual and automated testing.  
- Burp integrates into every step of the pentesting workflow.  

---

## 📊 Burp Suite in the Pentesting Workflow

```mermaid
flowchart LR
    A[🌐 Web Browser] -->|HTTP/S Traffic| B[🧩 Proxy]
    B --> C[📌 Target / Site Map]
    C --> D[🎯 Repeater]
    C --> E[💣 Intruder]
    C --> F[🔐 Decoder & Comparer]
    C --> G[🎲 Sequencer]
    D --> H[🕵️ Analysis & Exploitation]
    E --> H
    F --> H
    G --> H
    H --> I[📑 Reporting]
