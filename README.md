# 🚀 DummyJSON Product API Testing with Postman & Newman

<div align="center">

![Postman](https://img.shields.io/badge/Postman-API%20Testing-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![Newman](https://img.shields.io/badge/Newman-CLI%20Execution-3B82F6?style=for-the-badge)
![HTML Report](https://img.shields.io/badge/Report-htmlextra-8B5CF6?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-All%20Tests%20Passed-22C55E?style=for-the-badge)

</div>

---

## 📌 Project Overview

This project demonstrates **real API testing** using the **DummyJSON** hosted REST API.  
It was created as the next step after a **Product API Mock Testing** project built with **JSON Server** on a local machine.

This repository covers:

- ✅ Health check testing
- ✅ Product API testing
- ✅ Authentication API testing
- ✅ Negative testing
- ✅ Performance testing
- ✅ Newman CLI execution
- ✅ HTML report generation

---

## 🧰 Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Postman** | API request creation, validation, and collection execution |
| **DummyJSON** | Real hosted API used for testing |
| **Newman** | Command-line runner for Postman collections |
| **newman-reporter-htmlextra** | Advanced HTML report generation |
| **GitHub** | Project hosting and portfolio showcase |

---

## 🌐 Base URL

```bash
https://dummyjson.com
```

---

## 📂 Project Structure

```text
DummyJSON-Product-API-Testing-Postman/
│── DummyJSON Product API Testing.postman_collection.json
│── DummyJSON Env.postman_environment.json
│── newman-report.html
│── README.md
│── DummyJSON_Project_Tracker.xlsx
│── screenshots/
```

---

## 🧪 Modules Tested

### 1) Health Check
- **Test Route**
  - `GET /test`

### 2) Product APIs
- **Get all Products**
  - `GET /products`
- **Get single product by ID**
  - `GET /products/{{productId}}`
- **Search product**
  - `GET /products/search?q={{searchQuery}}`
- **Pagination test**
  - `GET /products?limit=10&skip=0`
- **Select specific fields**
  - `GET /products?limit=5&select=title,price`

### 3) Auth APIs
- **Login user and save tokens**
  - `POST /auth/login`
- **Get current auth user**
  - `GET /auth/me`
- **Refresh token**
  - `POST /auth/refresh`

### 4) Negative Testing
- **Invalid product ID**
  - `GET /productss/999999`
- **Invalid login**
  - `POST /auth/login`
- **Auth behavior check without bearer token**
  - `GET /auth/me`

### 5) Performance Testing
- **Delayed products response check**
  - `GET /products?delay=1000`
- **Normal products response check**
  - `GET /products`

---

## ✅ Validations Performed

- Status code validation
- Response body validation
- Key/value existence validation
- Pagination validation
- Token extraction and reuse
- Environment variable handling
- Negative scenario validation
- Response time validation
- Content-Type validation

---

## 🔐 Environment Variables

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

## ⚡ Sample Postman Test Scripts

### Status Code Check
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

### Response Time Check
```javascript
pm.test("Response time is below 3000 ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(3000);
});
```

### Save Access Token
```javascript
const res = pm.response.json();
pm.environment.set("accessToken", res.accessToken);
pm.environment.set("refreshToken", res.refreshToken);
```

---

## 🏃 Newman CLI Execution

### Install Newman
```bash
npm install -g newman
npm install -g newman-reporter-htmlextra
```

### Run Collection
```bash
newman run "DummyJSON Product API Testing.postman_collection.json" -e "DummyJSON Env.postman_environment.json" -r cli
```

### Generate Dashboard-style HTML Report
```bash
newman run "DummyJSON Product API Testing.postman_collection.json" -e "DummyJSON Env.postman_environment.json" -r "cli,htmlextra" --reporter-htmlextra-export "newman-report.html"
```

---

## 📊 Newman CLI Result

- ✅ Collection executed successfully
- ✅ All requests completed
- ✅ All test cases passed
- ✅ HTML execution report generated successfully

---

## 🧠 Challenges Faced & Fixes

### 1) Invalid credentials with variables
**Issue:** Login worked with hardcoded values but failed with `{{username}}` and `{{password}}`  
**Fix:** Corrected environment variable names and values.

### 2) `/auth/me` returned 200 without bearer token
**Issue:** Expected 401/403 but received 200  
**Fix:** Identified cookie-based session behavior after login and updated the negative test accordingly.

### 3) Newman failed while Postman passed
**Issue:** Newman showed invalid URI / unresolved variables  
**Fix:** Removed extra spaces from variable names such as `{{baseURL }}` and ensured exported environment values were correct.

---

## 📈 Performance Testing

Two requests were used to validate performance:

- **Delayed products response check**
  - `GET /products?delay=1000`
- **Normal products response check**
  - `GET /products`

Example performance script:

```javascript
pm.test("Response time is below 3000 ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(3000);
});
```

---

## 📸 Suggested Screenshots

Add these images to the `screenshots/` folder:

- Postman collection structure
- All tests passed in Collection Runner
- Newman CLI terminal result
- HTML report dashboard

---

## 🎯 Project Outcome

This project demonstrates practical **API testing on a real hosted API** using **Postman** and **Newman**.  
It validates functional behavior, authentication flow, negative scenarios, and performance checks in a portfolio-ready format.

---

## 💼 Resume / LinkedIn Description

**DummyJSON Product API Testing with Postman & Newman**  
Tested hosted REST APIs using Postman and Newman, including product validation, authentication flow, negative scenarios, environment variable handling, and performance checks.

---

## 👨‍💻 Author

**Your Name Here**  
SQA / API Testing Learner

---

## ⭐ If you like this project

Give it a star on GitHub and use it as part of your software testing portfolio.
