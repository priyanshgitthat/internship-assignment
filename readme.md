# Serverless Email API

This project implements a simple RESTful API using the Serverless Framework and AWS Lambda (Python 3.8 runtime) to send emails. It's designed to be easily deployable to AWS and can be tested locally using `serverless-offline`.

## 🚀 Features

* **Email Sending:** Sends emails to a specified recipient with a subject and body text.
* **RESTful Endpoint:** Exposes a `POST` endpoint for sending emails.
* **Error Handling:** Includes robust error handling for missing fields, invalid JSON, and SMTP issues.
* **Environment Variables:** Securely manages email credentials using environment variables.
* **Local Development:** Supports local testing with `serverless-offline`.
* **CORS Enabled:** Allows cross-origin requests for easier integration with front-end applications.

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

* **Node.js & npm:** The Serverless Framework is built on Node.js.
    * [Download Node.js](https://nodejs.org/en/download/) (npm is included)
* **Serverless Framework CLI:**
    ```bash
    npm install -g serverless
    ```
* **Python 3.8:** Ensure Python 3.8 is installed and accessible in your PATH.
    * [Download Python](https://www.python.org/downloads/)
* **pip:** Python's package installer (usually comes with Python).

## ⚙️ Setup Instructions

Follow these steps to get the project up and running on your local machine:

1.  **Navigate to the Project Directory:**
    ```bash
    # Assuming you've cloned the repository
    cd internship-assignment/email-api
    ```

2.  **Install Node.js Dependencies:**
    This installs the `serverless-offline` and `serverless-python-requirements` plugins.
    ```bash
    npm install
    ```

3.  **Install Serverless Plugins:**
    ```bash
    serverless plugin install -n serverless-python-requirements
    serverless plugin install -n serverless-offline
    ```

4.  **Create `.env` File:**
    Create a file named `.env` in the root of your `email-api` directory.
    **Important:** This file should **never** be committed to version control (e.g., Git). Ensure `.env` is in your `.gitignore`.

    Populate the `.env` file with your email credentials:

    ```ini
    EMAIL_PROVIDER=smtp.gmail.com
    EMAIL_USERNAME="your-email@gmail.com"
    EMAIL_PASSWORD="your-app-specific-password" # Strongly recommended for Gmail
    ```

## 🏃 Running Locally (Offline)

To run your API locally using `serverless-offline`, ensure you are in the `email-api` directory and execute:

## 🧪 Testing the API

with the serverless offline server running, you can send a POST request to http://localhost:4000/dev/send-email with a JSON body containing receiver_email, subject, and body_text. You can use tools like curl or Postman.

```
    curl -X POST -H "Content-Type: application/json" -d '{
    "receiver_email": "recipient@example.com",
    "subject": "Test Email from Serverless Offline",
    "body_text": "Hello from the local Serverless API!"
    }' http://localhost:4000/dev/send-email
```


### Example using Postman:

    Method: POST
    URL: http://localhost:4000/dev/send-email
    Headers: Content-Type: application/json
    Body (raw JSON):
```
    {
    "receiver_email": "recipient@example.com",
    "subject": "Test Email from Postman",
    "body_text": "This email was sent using Postman."
    }
```

## Project Structure

internship-assignment/
└── email-api/
    ├── .env
    ├── handler.py
    ├── serverless.yml
    ├── package.json
    └── package-lock.json
.gitignore
README.md

## Contact me

* **GitHub:** [https://github.com/priyanshgitthat/internship-assignment](https://github.com/priyanshgitthat/internship-assignment)
* **Email:** priyanshverma157@gmail.com
* **LinkedIn:** [https://www.linkedin.com/in/priyanshv/](https://www.linkedin.com/in/priyanshv/)
