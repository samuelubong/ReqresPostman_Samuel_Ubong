# 🧪 API Test Plan – Reqres.in (Mock API)

## 📌 1. What Is Being Tested

This plan outlines API testing for [https://reqres.in](https://reqres.in), a mock API service used to simulate RESTful endpoints. The following endpoints are tested:

- `GET /api/users?page=2` – Retrieve list of users
- `POST /api/users` – Create a new user
- `PUT /api/users/:id` – Update user details
- `DELETE /api/users/:id` – Delete a user
- `POST /api/login` – Authenticate a user

---

## 📘 2. Test Coverage Areas

| Endpoint           | Test Type | Description                                             |
|--------------------|-----------|---------------------------------------------------------|
| `GET /users`       | ✅ Positive | Check valid response, structure, status 200             |
|                    | ❌ Negative | Invalid query params, wrong path                        |
| `POST /users`      | ✅ Positive | Create a user with name and job                         |
|                    | ❌ Negative | Missing fields (name/job), invalid data types           |
| `PUT /users/:id`   | ✅ Positive | Update an existing user’s job/title                     |
|                    | ❌ Negative | Invalid/missing ID, invalid data                        |
| `DELETE /users/:id`| ✅ Positive | Confirm user deletion with 204                          |
|                    | ❌ Negative | Delete non-existent user, no ID                         |
| `POST /login`      | ✅ Positive | Log in with valid email/password                        |
|                    | ❌ Negative | Missing fields, wrong credentials, token assertion      |

---

## 🛠️ 3. Tools Used & Why

| Tool             | Purpose                                 |
|------------------|-----------------------------------------|
| **Postman**      | Manual & automated API testing          |
| **JavaScript Tests** | Add custom test scripts to assert responses |
| **Collection Runner / Monitor** | Automate sequence of test cases |
| **Mock Server (Reqres)** | Safe testing environment without real data |

---

## ▶️ 4. How to Run the Tests

### Option 1: Manual Testing (Using Postman)
1. Open Postman.
2. Import the collection or create new requests for each endpoint.
3. Use base URL: `https://reqres.in/api`
4. Send requests manually and inspect responses.

### Option 2: Automated Collection Runner
1. Open "Runner" in Postman.
2. Select the Reqres collection.
3. Optionally add environment/collection variables.
4. Run all requests and view test results.

---

## ⚠️ 5. Assumptions & Limitations

### ✅ Assumptions
- The Reqres API is publicly available and functional.
- Test users and mock data exist as per documentation.
- Response formats and sample inputs are based on official Reqres guides.

### ❌ Limitations
- **No data persistence:** POST/PUT/DELETE do not affect stored data.
- **Limited error simulation:** Some real-world errors (like rate limiting or 500s) cannot be tested.
- **No authentication/token-based session management** beyond mock login.
- **No backend validation:** Only frontend-like behavior is simulated.

---

> 🔗 [Reqres.in Official Docs](https://reqres.in)
