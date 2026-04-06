<div align="center">

# 🚀 DummyJSON Product API Testing with Postman & Newman

<p align="center">
  <b>Real API testing project using DummyJSON, Postman, Newman, and HTML reporting</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Postman-API%20Testing-orange?style=for-the-badge&logo=postman" />
  <img src="https://img.shields.io/badge/Newman-CLI%20Execution-green?style=for-the-badge&logo=postman" />
  <img src="https://img.shields.io/badge/API-DummyJSON-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" />
</p>

<p align="center">
  <i>A portfolio-ready REST API testing project covering product endpoints, authentication flow, negative scenarios, and performance validation.</i>
</p>

</div>

---

## 📌 Project Overview

This project demonstrates **real API testing** using the hosted **DummyJSON API** instead of a local mock server. It was built to practice how QA engineers test production-like REST endpoints using **Postman** for request design and validation, and **Newman** for command-line execution and HTML report generation.

Unlike a basic mock API project, this repository includes:
- ✅ Real hosted API endpoints
- ✅ Authentication and token handling
- ✅ Negative testing scenarios
- ✅ Performance checks
- ✅ Newman CLI execution
- ✅ HTML report generation

---

## 🎯 Project Objectives

- Validate core **product API** functionality
- Test **authentication flow** using login and refresh token endpoints
- Practice **environment variables** and dynamic token storage
- Cover **negative and edge scenarios**
- Verify **response time and basic performance thresholds**
- Execute the collection through **Newman CLI**

---

## 🧰 Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Postman** | API request creation, testing, validation |
| **Newman** | Command-line execution of Postman collections |
| **DummyJSON API** | Hosted API used for testing |
| **Node.js / npm** | Required for Newman installation |
| **HTML Reporters** | Visual execution reports |

---

## 🌐 Base URL

```bash
https://dummyjson.com
```

---

## 📂 Collection Structure

```text
DummyJSON Product API Testing
├── Health Check
│   └── Test Route
├── Product APIs
│   ├── Get all Products
│   ├── Get single product by ID
│   ├── Search product
│   ├── Pagination test
│   └── Select specific fields
├── Auth APIs
│   ├── Login user and save tokens
│   ├── Get current auth user
│   └── Refresh token
├── Negative Testing
│   ├── Invalid product ID
│   ├── Invalid login
│   └── Auth behavior check without bearer token
└── Performance Testing
    ├── Delayed products response check
    └── Normal products response check
```

---

## 🧪 Modules Tested

### 1️⃣ Health Check
Used to verify that the API is reachable before running functional requests.

### 2️⃣ Product APIs
Covered the most common product-related scenarios such as:
- Fetching all products
- Fetching product by ID
- Searching products by keyword
- Pagination validation
- Field selection validation

### 3️⃣ Authentication APIs
Validated login and token-based workflow:
- Login with valid credentials
- Save `accessToken` and `refreshToken`
- Call authenticated endpoint `/auth/me`
- Refresh token using `/auth/refresh`

### 4️⃣ Negative Testing
Checked how the API behaves with invalid requests, such as:
- Invalid product endpoint
- Invalid login credentials
- Auth behavior without explicitly passing a bearer token

### 5️⃣ Performance Testing
Verified basic response-time expectations for:
- Normal response flow
- Delayed response flow using query delay parameter

---

## ✅ Validations Performed

- Status code validation
- JSON body validation
- Required field validation
- Pagination key validation
- Token extraction and reuse
- Header validation
- Response time validation
- Unauthorized / invalid request validation

---

## 🔁 Environment Variables Used

```text
baseURL = https://dummyjson.com
productId = 1
searchQuery = phone
username = emilys
password = emilyspass
accessToken =
refreshToken =
userId =
```

---

## 🧾 Sample Test Scripts

### Status Code Validation
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

### Save Access Token
```javascript
const res = pm.response.json();
pm.environment.set("accessToken", res.accessToken);
pm.environment.set("refreshToken", res.refreshToken);
```

### Response Time Validation
```javascript
pm.test("Response time is below 3000 ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(3000);
});
```

---

## ▶️ How to Run in Postman

1. Import the Postman collection file
2. Import the environment file
3. Select the environment
4. Run the collection from Collection Runner
5. Review the execution summary and passed assertions

---

## 💻 Run with Newman CLI

### Install Newman
```bash
npm install -g newman
```

### Run Collection
```bash
newman run "DummyJSON Product API Testing.postman_collection.json" -e "DummyJSON Env.postman_environment.json" -r cli
```

### Install HTML Reporter
```bash
npm install -g newman-reporter-html
```

### Install HTMLEXTRA Reporter
```bash
npm install -g newman-reporter-htmlextra
```

### Generate Premium HTML Report
```bash
newman run "DummyJSON Product API Testing.postman_collection.json" -e "DummyJSON Env.postman_environment.json" -r "cli,htmlextra" --reporter-htmlextra-export "newman-report.html"
```

---

## 📊 Newman CLI Result

This project was successfully executed through **Newman CLI**, and an HTML report was generated for better visualization of request execution, assertions, and overall results.

### Output Highlights
- ✅ All requests executed successfully
- ✅ Assertions passed successfully
- ✅ CLI execution completed
- ✅ HTML report generated

---

## 🖼️ Suggested Repository Assets

Add these files to make the repository stronger:
- `DummyJSON Product API Testing.postman_collection.json`
- `DummyJSON Env.postman_environment.json`
- `newman-report.html`
- `README.md`
- `screenshots/`

Recommended screenshots:
- Postman collection structure
- Collection Runner pass result
- Newman CLI terminal output
- HTML report preview

---

## 🌟 Why This Project Matters

This project is stronger than a simple mock API exercise because it demonstrates:

- Real API testing workflow
- Authentication handling
- Dynamic environment variable usage
- Command-line test execution
- Structured QA validation approach
- Portfolio-ready documentation

It shows practical skills that are useful for **Junior QA / SQA / API Testing roles**.

---

## 🧑‍💼 Resume / LinkedIn Project Description

**DummyJSON Product API Testing with Postman & Newman**  
Tested hosted REST APIs using Postman and Newman, including product endpoint validation, authentication flow, negative scenarios, environment variable handling, and performance checks with HTML reporting.

---

## 📬 Repository Description

> Real API testing project using DummyJSON, Postman, and Newman with product, auth, negative, and performance test scenarios.

---

## 🙌 Final Note

This project helped strengthen my understanding of:
- REST API testing
- Request chaining
- Token handling
- Negative testing
- Performance validation
- CLI-based automation execution

If you found this repository useful, feel free to explore the collection and report files.

---

<div align="center">
  <b>⭐ Built as a practical portfolio project for API Testing / QA roles</b>
</div>
