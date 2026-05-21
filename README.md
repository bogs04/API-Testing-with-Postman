# API Testing with Postman 🧪

This repository contains a **Postman collection** showcasing a hands-on API testing portfolio targeting the public [ReqRes REST API](https://reqres.in).

---

## 📋 What is Tested?

| # | Endpoint | Method | Test Focus |
|---|---|---|---|
| 1 | `/api/users?page=2` | GET | Status code, response time, pagination schema, data array validation |
| 2 | `/api/users` | POST | User creation (201 Created), returned fields (`id`, `createdAt`) |
| 3 | `/api/login` | POST | Successful login, JWT token returned |
| 4 | `/api/login` | POST | Negative test – missing password → 400 error message validation |

---

## 🛠️ Tools & Technologies

![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=Postman&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![JSON](https://img.shields.io/badge/JSON-000000?style=flat&logo=json&logoColor=white)

---

## 🚀 How to Run the Tests

1. **Download** the `api_testing_postman_collection.json` file from this repository.
2. Open **Postman** → Click **Import** → **Upload Files** → select the downloaded `.json` file.
3. The collection **"ReqRes API Testing Portfolio - bogs04"** will appear in your Collections sidebar.
4. Click on any request (e.g. *Login – Successful*) and press **Send**.
5. Go to the **Tests** tab in the response panel → view **PASS/FAIL** results for each assertion.

> 💡 **Tip:** Use **Collection Runner** (▶ Run button) to execute all requests in sequence and see a full test report at once.

---

## ✅ Test Scripts Overview

Each request contains pre-written **JavaScript assertions** in the `Tests` tab that automatically validate:

- ✔ **HTTP Status Code** – e.g. `200 OK`, `201 Created`, `400 Bad Request`
- ✔ **Response Time** – must be below `500ms`
- ✔ **Response Schema** – verifies required fields exist (`id`, `email`, `token`, etc.)
- ✔ **Error Messages** – checks exact error text for negative test cases

### Sample Test Script (Login – Successful)
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains token", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('token');
    pm.expect(jsonData.token).to.be.a('string');
});
```

---

## 📁 Repository Structure

```
API-Testing-with-Postman/
│
├── api_testing_postman_collection.json   # Full Postman collection with test scripts
└── README.md                             # This file
```

---

## 👤 Author

**Phung Van Anh** – Manual QA/QC Tester  
📧 vananh130804@gmail.com | 🔗 [github.com/bogs04](https://github.com/bogs04)
