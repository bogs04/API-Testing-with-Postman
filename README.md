{
  "repository": "API-Testing-with-Postman",
  "description": "Postman collection for API testing of the public ReqRes API, demonstrating manual and automated test scripts for user list, user creation, login success/failure, and login security checks.",
  "files": [
    {
      "name": "api_testing_postman_collection.json",
      "path": "api_testing_postman_collection.json"
    },
    {
      "name": "README.md",
      "content": "# API-Testing-with-Postman\n\nThis repository contains a **Postman collection** that showcases a comprehensive API testing portfolio for the public **ReqRes** API (https://reqres.in).\n\n## What is tested?\n- **GET /users?page=2** – verifies response status, response time (< 500 ms), pagination schema and data array integrity.\n- **POST /users** – validates successful user creation (status 201) and checks returned fields (id, createdAt).\n- **POST /login (successful)** – ensures a 200 status and that a JWT‑like token is returned.\n- **POST /login (missing password)** – expects a 400 status and a clear error message (`\"Missing password\"`).\n\n## How to run the tests\n1. Install **Postman** (free version is enough).\n2. Click **Import** → **Upload Files** and select `api_testing_postman_collection.json` from this repository.\n3. The collection will appear under **Collections**.\n4. Open a request (e.g., *Login – Successful*) and press **Send**.\n5. Switch to the **Tests** tab – the pre‑written JavaScript assertions will automatically run and display **PASS/FAIL** results in the **Test Results** panel.\n\n## Why this collection matters\n- Demonstrates the use of **test scripts** (written in JavaScript) to assert status codes, response times, and JSON schema.\n- Shows **negative testing** (missing password) and how to validate error messages.\n- Provides a reusable template for future API testing projects – just change the base URL and payloads.\n\nFeel free to fork this repo, add more endpoints, or integrate it into CI pipelines using Newman.\n",
      "type": "markdown"
    }
  ],
  "setupInstructions": [
    "Create a new repository on GitHub named `API-Testing-with-Postman`.",
    "Add the two files listed above (the Postman collection JSON and README.md).",
    "Commit and push to the remote repository."
  ]
}
