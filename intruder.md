# 🛡️ Jr Penetration Tester – Burp Suite: Intruder

**Room:** [Burp Suite: Intruder](https://tryhackme.com/)  
**Path:** Junior Penetration Tester  
**Platform:** TryHackMe (Premium Room)  

---

## 📖 Overview
This room focused on **Burp Suite’s Intruder tab**, which automates sending multiple HTTP requests to test web applications.  
Intruder is useful for:
- Brute-forcing login credentials  
- Fuzzing parameters  
- Enumerating hidden endpoints or values  

It allows testers to **rapidly send multiple requests with different payloads** and analyze server responses efficiently.

---

## ✅ Task-by-Task Summary

<details>
<summary><strong>📝 Task 1 – Introduction to Intruder</strong></summary>

- Intruder automates repetitive HTTP requests for testing security.  
- Key uses:
  - Brute force login credentials  
  - Parameter fuzzing  
  - Enumerating hidden fields or endpoints  
- Four attack types: **Sniper, Battering Ram, Pitchfork, Cluster Bomb**  

</details>

<details>
<summary><strong>📤 Task 2 – Configuring Targets and Positions</strong></summary>

- Captured requests in Proxy and sent them to Intruder.  
- Highlighted positions in the request where payloads will be injected.  
- Verified payload positions in the **Positions tab**.  

</details>

<details>
<summary><strong>✏️ Task 3 – Selecting Attack Type</strong></summary>

- Explored Intruder attack types:  
  - **Sniper:** single payload per position  
  - **Battering Ram:** same payload for all positions  
  - **Pitchfork:** parallel payloads for multiple positions  
  - **Cluster Bomb:** combines all payloads across positions  
- Selected attack type depending on testing goal.  

</details>

<details>
<summary><strong>👀 Task 4 – Configuring Payloads</strong></summary>

- Defined payloads manually or via built-in generators.  
- Payload types:
  - Strings (common passwords, usernames)  
  - Numbers (IDs, session tokens)  
  - Custom lists for fuzzing  
- Optional: added prefixes, suffixes, or encoding to payloads.  

</details>

<details>
<summary><strong>🔧 Task 5 – Launching Attack & Analyzing Results</strong></summary>

- Started Intruder attack and monitored progress in **Intruder → Attack Results**.  
- Observed response codes, lengths, and content for anomalies.  
- Identified potential vulnerabilities:
  - Weak passwords  
  - IDOR endpoints  
  - Unexpected server responses  

</details>

---

### **PRACTICALS**

<details>
<summary><strong>💻 Task 6 – Practical: Brute-Force Login</strong></summary>

### **Objective**
Automate login attempts with multiple credentials to test password strength.

### **Skills Applied**
- Sending requests to Intruder  
- Setting payload positions  
- Choosing attack types  
- Analyzing server responses  

---

### **Step 1 – Capture Login Request**
1. Open **Burp Proxy → Intercept**.  
2. Navigate to the login page in your browser.  
3. Capture the login POST request.

<img width="800" height="241" alt="image" src="https://github.com/user-attachments/assets/5bd3047d-6b60-4935-81cd-196ad4148a81" />


---

### **Step 2 – Send Request to Intruder**
1. Right-click the captured request → **Send to Intruder**.  
2. Go to the **Intruder** tab and select the request.
   
---

### **Step 3 – Configure Payload Positions**
1. Highlight the **password field** as the payload position.  
2. Ensure no other unnecessary positions are selected.  

<img width="640" height="688" alt="image" src="https://github.com/user-attachments/assets/f81c8137-c3e9-4b7f-965d-f133e1d7ded3" />

---

### **Step 4 – Select Attack Type**
- Choose **Sniper** for testing one payload per position.  

---

### **Step 5 – Configure Payloads**
1. Load payload list of passwords (provided).  
2. Optionally, configure encoding if needed.

<img width="448" height="440" alt="image" src="https://github.com/user-attachments/assets/3d2c674a-946c-459f-be84-55d2a965ea15" />


---

### **Step 6 – Launch Attack**
1. Click **Start Attack**.  
2. Observe responses for differences in:
   - Response codes  
   - Response lengths  
   - Content changes  

---

### **Step 7 – Analyze Results**
- Identify valid credentials based on unique server responses.  
- Note potential weaknesses in authentication.

<img width="1507" height="806" alt="image" src="https://github.com/user-attachments/assets/0bbdf38a-285c-49d7-9d15-626052aab1fc" />
 
- Successful login

<img width="918" height="483" alt="image" src="https://github.com/user-attachments/assets/a1b2033b-0904-4101-a997-53f02c1ffa37" />

</details>

<details>
<summary><strong>💻 Task 7 – Practical: Fuzzing Parameters</strong></summary>

### **Objective**
Use Intruder to test numeric or text parameters for hidden endpoints or vulnerabilities.

### **Skills Applied**
- Sending requests to Intruder  
- Fuzzing input parameters  
- Observing server responses  
- Identifying security flaws  

---

### **Step 1 – Capture Request**
- Capture a GET request with parameters (e.g., `/products?id=1`) via Proxy.  
- Send to Intruder.  

---

### **Step 2 – Set Payload Positions**
- Highlight the **parameter value** as the payload position.

<img width="565" height="530" alt="image" src="https://github.com/user-attachments/assets/30dd4c26-b2a6-4e2f-a57a-745ca8e49dfd" />

---

### **Step 3 – Choose Attack Type**
- Use **Sniper** for single-value testing or **Cluster Bomb** for multiple parameters.  

---

### **Step 4 – Configure Payloads**
- Load payload list (e.g., `-1,0,9999,abc`).  
- Optionally include fuzzing lists for hidden values.  

<img width="458" height="388" alt="image" src="https://github.com/user-attachments/assets/04af2e71-299a-4a93-bc2e-d00b1149e8f7" />

---

### **Step 5 – Launch Attack**
- Click **Start Attack** and monitor responses.  

---

### **Step 6 – Analyze Results**
- Identify parameters that may be vulnerable to:
  - **IDOR**  
  - **Information leakage**  
  - **Input validation flaws**

<img width="1669" height="888" alt="image" src="https://github.com/user-attachments/assets/13651c08-72a7-4a85-bbb9-0b587a61e3d2" />


</details>

<details>
<summary><strong>🚀 Extra Mile Challenge – Advanced Payload Testing</strong></summary>

### **Objective**
Combine multiple payload lists and positions to discover hidden values or endpoints.

### **Scenario**
- Test a web app where **ID** and **token** parameters may reveal additional resources.  

---

### **Step 1 – Capture Request**
- Capture request in Proxy and send to Intruder.  

### **Step 2 – Set Multiple Payload Positions**
- Highlight all relevant parameters (e.g., `id`, `token`).

<img width="510" height="664" alt="image" src="https://github.com/user-attachments/assets/6882806d-3247-4da7-9b18-ca98ce58dd6c" />


### **Step 3 – Select Attack Type**
- Use **Pitchfork** to combine payload lists across positions.  

### **Step 4 – Configure Payloads**
- Payload list 1: usernames 
- Payload list 2: passwords

### **Step 5 – Launch Attack**
-  With the username and password parameters handled, we now need to find a way to grab the ever-changing loginToken and session cookie.
-  Unfortunately, "recursive grep" won't work here due to the redirect response, so we can't do this entirely within Intruder – we will need to build a macro.

<img width="510" height="419" alt="image" src="https://github.com/user-attachments/assets/8f8d85e0-a1eb-4aa8-ac7c-8e625b810f16" />

### **Observation**
- Unique response codes or lengths may indicate hidden endpoints or data.

<img width="1508" height="790" alt="image" src="https://github.com/user-attachments/assets/e5af1235-7fcd-4e39-9d20-646c5e96dad2" />

successful login

<img width="1183" height="748" alt="image" src="https://github.com/user-attachments/assets/d3e90aad-625e-4ac0-b197-56179c91eeee" />


</details>

---

## 🎯 Key Takeaways
- Intruder automates **repetitive web testing tasks**.  
- Useful for **brute-force, fuzzing, and parameter enumeration**.  
- Attack types allow flexibility depending on the testing goal.  
- Should be used responsibly and only in **authorized environments**.  

---

## 📊 Intruder in the Pentesting Workflow

```mermaid
flowchart LR
    A[🌐 Web Browser] --> B[🧩 Burp Proxy]
    B -->|Send to Intruder| C[🎯 Burp Intruder]
    C --> D[✏️ Configure Payloads & Positions]
    D --> E[🚀 Launch Attack]
    E --> F[👀 Analyze Responses]
    F --> G[🕵️ Identify Vulnerabilities]
