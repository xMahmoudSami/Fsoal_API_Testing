# 🚀 Fsoal LMS - API Testing Framework

Comprehensive Automated API Testing Suite for **Fsoal** (Learning Management System), validating backend stability, student workflows, and data integrity in a production environment.

## 🛠️ Tech Stack
* **Tool:** Postman
* **Automation:** JavaScript (Chai Assertion Library) applied at collection level.
* **Reporting:** JSON Execution Logs & Visual Dashboards.
* **Metrics:** Status Code Validation (200/201/204) & Response Time Benchmarking (< 2000ms).

## 📂 Repository Contents
This repository contains the full test artifacts:
1.  `collection.json`: The source code containing all requests and test scripts.
2.  `execution-logs.json`: Detailed JSON logs of the test run for auditing purposes.
3.  `dashboard-report.png`: Visual proof of execution summary.

## 🧪 Testing Scope
The suite validates critical LMS business logic including:
* **Authentication:** Student/Instructor Login, Register, OTP Verification.
* **User Profile:** Password management and profile updates.
* **Course Interaction:** Retrieving course details and user reviews.

## 📊 Execution Insights & Bug Report
The automated suite executed **64 tests**, successfully validating core flows but **proactively detecting critical issues** in the system:

### 📸 Execution Dashboard
![Execution Report](dashboard-report.png)

### 🔴 Critical Issues Discovered:
1.  **Performance Bottleneck (Severity: High):**
    * **Endpoint:** `edit_password`
    * **Observation:** Response time spiked to **4.4s** (exceeding the 2s SLA).
    * **Impact:** Poor user experience during sensitive account operations.

2.  **Backend Logic Crash (Severity: Critical):**
    * **Endpoint:** `reviews_per_user`
    * **Observation:** Returned **Status 500 (Internal Server Error)** instead of 200.
    * **Impact:** Indicates an unhandled exception in the database layer when retrieving user reviews.

## 🚀 How to Run
1.  Download `collection.json` from this repository.
2.  Import it into **Postman**.
3.  Run via **Collection Runner** to verify the results.
