# 🛡️ Jr Penetration Tester – Burp Suite: Repeater

**Room:** [Burp Suite: Repeater](https://tryhackme.com/)  
**Path:** Junior Penetration Tester  
**Platform:** TryHackMe (Premium Room)  

---

## 📖 Overview
This room focused on **Burp Suite’s Repeater tab**, one of the most important tools for manual web application testing.  
Repeater allows testers to send, modify, and replay individual HTTP(S) requests to analyze how a web server responds under different conditions.  

---

## 📌 Progress Tracker
- [x] Task 1 – Introduction to Repeater  
- [x] Task 2 – Sending Requests to Repeater  
- [x] Task 3 – Modifying Requests  
- [x] Task 4 – Observing and Analyzing Responses  
- [x] Task 5 – Practical Use Cases of Repeater  
- [x] Task 6 – Modify Request Headers Practical  
- [x] Task 7 – Validate Numeric Endpoint Practical  
- [x] Extra Mile Challenge – Union SQL Injection

---

## ✅ Task-by-Task Summary

</details><summary><strong>📝 Task 1 – Introduction to Repeater</strong></summary>

- Learned that Repeater is used for **manual testing** of HTTP requests.  
- Key benefit: the ability to modify requests repeatedly and observe server responses.  
- Unlike automated modules, Repeater gives **fine-grained control** for testing specific parameters.  

</details>

---

<details>
  <summary><strong>📤 Task 2 – Sending Requests to Repeater</strong></summary>

- Captured requests in Proxy and forwarded them to Repeater.  
- Learned multiple ways to send requests:
  - Right-click → "Send to Repeater"  
  - Hotkey: **Ctrl+R** (Windows/Linux) or **Cmd+R** (Mac).  
- Requests appear in the **Repeater tab** for further testing.  

</details>

---

<details>
  <summary><strong>✏️ Task 3 – Modifying Requests</strong></summary>

- Edited HTTP headers, methods, and parameters directly in Repeater.  
- Practiced changing:
  - Request methods (e.g., `GET` → `POST`).  
  - Query string parameters.  
  - Cookie/session values.  
- Observed how changes impacted server behavior.  

</details>

---

<details>
  <summary><strong>👀 Task 4 – Observing and Analyzing Responses</strong></summary>

- Compared server responses to different request modifications.  
- Used the **Response tab** to check HTML, JSON, and error messages.  
- Learned to identify:
  - Authentication bypass opportunities.  
  - Input validation flaws.  
  - Unexpected server behavior.  

</details>

---

<details>
  <summary><strong>🔧 Task 5 – Practical Use Cases</strong></summary>

- Tested authentication mechanisms by replaying login requests with altered credentials.  
- Analyzed parameter tampering for access control flaws.  
- Practiced with reflected input fields to test for **Cross-Site Scripting (XSS)**.  
- Reinforced Repeater’s role in **exploitation and vulnerability confirmation**.  

</details>

---
### **PRACTICALS**
<details>
  <summary><strong>💻 Task 6 – Repeater: Modify Request Headers Practical</strong></summary>

### **Objective**
Use Burp Suite Repeater to modify HTTP request headers and observe server responses.

### **Skills Applied**
- Proxy interception  
- Sending requests to Repeater  
- Modifying headers  
- Analyzing responses  

---

### **Step 1 – Capture the Request**
1. Open **Burp Suite → Proxy → Intercept**.  
2. Navigate to the target URL: `http://10.10.26.44/`.  
3. Capture the HTTP request to the target page.  

---

### **Step 2 – Send Request to Repeater**
1. Right-click the captured request → **Send to Repeater**.  
2. Go to the **Repeater** tab and select the request.  
3. Click **Send** once to view the response.  
   - The **Response** tab shows the HTML source.  
4. Optionally, switch the **Display** view to **Hex** or **Raw**.
 
<img width="984" height="904" alt="Send Request to Repeater" src="https://github.com/user-attachments/assets/802dfbbd-54d6-4b02-9e00-5662e2362e9d" />

---

### **Step 3 – Modify the Request Header**
1. In the Repeater request editor, add a new header:  

2. Ensure the header is correctly formatted and placed above the first blank line in the request.
   
<img width="319" height="705" alt="Modify Header in Repeater" src="https://github.com/user-attachments/assets/2e394f9c-f9e2-4f8f-8dbf-1e054890f5cc" />

---

### **Step 4 – Send Modified Request**
1. Click **Send** in Repeater.  
2. Observe the server’s response in the **Response** tab.
   
<img width="979" height="912" alt="Response After Header Modification" src="https://github.com/user-attachments/assets/a335e7e1-169b-4741-b8b1-4a3a942396fe" />

---

### **Step 5 – Observations / Notes**
- Repeater allows **rapid iteration** of requests with minor modifications.  
- Useful for testing:  
  - **SQL Injection**  
  - **WAF bypasses**  
  - **Parameter tampering**  
- Adding custom headers helps test **access control or authentication logic**.  

---

### **Example Request & Response**
**Request:**  

<img width="306" height="318" alt="Original Request" src="https://github.com/user-attachments/assets/908de1c8-f08f-454f-b78f-186b1f8ec88c" />

**Response:**  

<img width="315" height="263" alt="Response Example" src="https://github.com/user-attachments/assets/90f8e82c-4b80-4bf2-b0f5-c2639c4c9cb1" />

**Observation:**  
The page responded successfully with the added header. Repeater makes it easy to experiment with headers and other request modifications.

</details>

---

<details>
  <summary><strong>💻 Task 7 – Repeater Practical: Validate Numeric Endpoint</strong></summary>

### **Objective**
Use Burp Suite Repeater to test numeric endpoints for proper validation and observe potential security issues when the input is not validated.

### **Skills Applied**
- Sending requests to Repeater  
- Modifying URL parameters  
- Observing server responses  
- Identifying input validation issues  

---

### **Step 1 – Disable Proxy Interception**
1. Go to **Proxy → Intercept** in Burp Suite.  
2. Click **Intercept is off** to disable interception for smooth browsing.  

---

### **Step 2 – Browse the Target**
1. Navigate in your browser to: `http://10.10.26.44/products/`.  
2. Click on some of the **See More** links.  
   - Notice the numeric endpoints in the URL, e.g., `/products/3`.
     
<img width="985" height="371" alt="Products Page Example" src="https://github.com/user-attachments/assets/110b2281-dcaf-497e-ad0b-8e0ec1cdc2a6" />

---

### **Step 3 – Send Request to Repeater**
1. Capture one of the numeric endpoint requests via Proxy (if needed).  
2. Right-click the request → **Send to Repeater**.  
3. Go to the **Repeater** tab and select the request.
   
<img width="983" height="885" alt="Send Request to Repeater" src="https://github.com/user-attachments/assets/425f8bc5-1ba1-49d3-ae9b-3bdb3085021c" />

---

### **Step 4 – Modify the Endpoint**
1. Change the numeric part of the URL to test different values:  
   - Valid integers (e.g., `/products/1`, `/products/5`)  
   - Invalid inputs (e.g., `/products/abc`, `/products/9999`)  
2. Click **Send** and observe server responses.
   
<img width="992" height="897" alt="Modified Endpoint Response" src="https://github.com/user-attachments/assets/a1ef011c-4b5c-4bad-be5a-d321283711a7" />

---

### **Step 5 – Analyze Responses**
- Check if the server validates numeric input properly:  
  - Valid integers → Page displays product info.  
  - Invalid values → Error messages or unexpected behavior.  
- Take note of potential vulnerabilities such as:  
  - **IDOR** (Insecure Direct Object Reference)  
  - **Improper input validation**  
  - **Information leakage**  

---

### **Step 6 – Document Observations**

**Request:**

<img width="294" height="294" alt="Original Request" src="https://github.com/user-attachments/assets/2db65492-d547-4180-aedc-57263e29f191" />

**Modified Request (Invalid Input):**

<img width="308" height="321" alt="Modified Request" src="https://github.com/user-attachments/assets/c424a551-416f-45f9-882a-7a76d9773156" />

**Response:**  

<img width="313" height="223" alt="Response for Invalid Input" src="https://github.com/user-attachments/assets/6b901429-0410-4d85-b9ef-ae51621b0a30" />

**Observation:**  
The endpoint may not validate input properly, potentially allowing unauthorized access or revealing sensitive information.

</details>

---

<details>
  <summary><strong>🚀 Extra Mile Challenge – Union SQL Injection with Burp Repeater</strong></summary>

### **Objective**
Identify and exploit a **Union SQL Injection vulnerability** in the `ID` parameter of the `/about/ID` endpoint to retrieve sensitive data (CEO notes)


---

### **Prerequisite Knowledge**
- Basic understanding of SQL Injection principles.  
- Familiarity with Burp Suite Repeater and Proxy.  
- Optional: Review the SQL Injection TryHackMe room.  

---

### **Challenge Walkthrough**

#### Step 1 – Capture the Request
1. Open **Burp Proxy → Intercept**.  
2. Navigate to `http://10.10.26.44/about/2`.  
3. Send the captured request to **Repeater** (`Ctrl + R` or right-click → Send to Repeater).  

---

#### Step 2 – Confirm Vulnerability
1. Modify the URL to add a single apostrophe:
     
<img width="577" height="428" alt="image" src="https://github.com/user-attachments/assets/844e96b4-9821-42ee-9224-006126f105d5" />

- **500 Internal Server Error** indicates the query broke

2. If we look through the body of the server's response, we see something very interesting at around line 40. The server is telling us the query we tried to execute:

<img width="324" height="296" alt="image" src="https://github.com/user-attachments/assets/6659ecb8-6d9f-4945-8359-fd03a189ec97" />

 - Response shows the SQL query executed

### Step 3 – Enumerate Columns
1. Use a Union query to retrieve all column names from the people table:

<img width="585" height="428" alt="image" src="https://github.com/user-attachments/assets/fb250478-4982-4c7e-9195-34b060e0f6ac" />

- columns identified: id, firstName, lastName, pfpLink, role, shortRole, bio, notes
  
### Step 4 – Extract the Target Data

- Determine the target column (notes) and the CEO ID (1).
- Construct the final query to retrieve the CEO notes:
/about/0 UNION ALL SELECT notes,null,null,null,null FROM people WHERE id = 1
- Send the request and observe the notes displayed in the response.
  

<img width="684" height="544" alt="image" src="https://github.com/user-attachments/assets/85a96f29-cfde-4238-9484-f2f9dce9c6fe" />


**Observations**

Verbose server error messages greatly simplify enumeration (though this is a real-world misconfiguration).
Union SQL Injection allows retrieval of arbitrary database data.
group_concat() is useful for combining multiple results into one output.
Manual Repeater testing gives fine-grained control over requests for exploitation.

</details>

---

## 🎯 Key Takeaways
- Repeater is a **core manual testing tool** within Burp Suite.  
- It enables iterative testing by replaying modified requests and analyzing responses.  
- Ideal for testing authentication, input handling, parameter manipulation, and business logic flaws.  

---

## 📊 Repeater in the Pentesting Workflow

```mermaid
flowchart LR
    A[🌐 Web Browser] --> B[🧩 Burp Proxy]
    B -->|Send to Repeater| C[🎯 Burp Repeater]
    C --> D[✏️ Modify Request]
    D --> E[👀 Observe Response]
    E --> F[🕵️ Exploitation & Analysis]
    F --> G[📑 Reporting]
