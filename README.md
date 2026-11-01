
# 🚆 Railway Ticket Booking Website – Software Testing

![Java](https://img.shields.io/badge/Java-24-ED8B00?logo=openjdk&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-4.31.0-43B02A?logo=selenium&logoColor=white)
![TestNG](https://img.shields.io/badge/TestNG-7.11.0-FF6C37)
![Maven](https://img.shields.io/badge/Maven-Build_Tool-C71A36?logo=apachemaven&logoColor=white)
![Testing](https://img.shields.io/badge/Testing-Manual_%26_Automation-blue)

## 📌 1. Project Overview

**Railway Ticket Booking Website** is a web-based application that allows users to register accounts, log in, manage passwords, search for train schedules, and book railway tickets online.

This project focuses on **Manual Testing and Test Automation** to evaluate the functionality, reliability, and usability of the application.

The testing activities include test case design, test execution, defect identification, bug reporting, and automated test development using Selenium WebDriver and TestNG.

**Project Information**

| Information | Details |
|---|---|
| Project Name | Railway Ticket Booking Website |
| Project Type | Web Application Testing |
| Role | Manual & Automation Tester |
| Testing Approach | Functional Testing, UI Testing, Regression Testing |
| Automation Framework | Selenium WebDriver + TestNG |
| Programming Language | Java |
| Build Tool | Maven |
| Test Documentation | Microsoft Excel, Word |
| Application URL | http://railwayb2.somee.com |

---

## 🎯 2. Testing Objectives

The primary objectives of this project are:

- Verify that the application's core functionalities meet the expected requirements.
- Identify functional defects and UI inconsistencies.
- Validate input fields, error messages, and business rules.
- Test positive, negative, and boundary scenarios.
- Document defects with clear reproduction steps and expected results.
- Develop automated test scripts for selected functional scenarios.
- Improve testing efficiency through reusable automation scripts.

---

## 🔍 3. Testing Scope

The following modules are included in the testing scope:

| Module | Test Coverage |
|---|---|
| Login | Valid/invalid credentials, login restrictions, error messages |
| Registration | Account creation, mandatory fields, input validation |
| Password Management | Change Password, Forgot Password, Reset Password |
| Ticket Booking | Booking process, ticket information, confirmation messages |

### Testing Techniques

- Black-box Testing
- Functional Testing
- UI Testing
- Positive & Negative Testing
- Boundary Value Analysis
- Equivalence Partitioning
- Regression Testing

---

## 🛠️ 4. Technologies & Tools

| Category | Technologies / Tools |
|---|---|
| Programming Language | Java 24 |
| Automation Tool | Selenium WebDriver 4.31.0 |
| Testing Framework | TestNG 7.11.0 |
| Dependency Management | Maven |
| Browser Driver Management | WebDriverManager 5.8.0 |
| IDE | IntelliJ IDEA |
| Manual Test Documentation | Microsoft Excel |
| Bug Reporting | Microsoft Word |
| Version Control | Git & GitHub |

---

## 📂 5. Project Structure

The following is a recommended repository structure for organizing the testing artifacts and automation source code.

```text
Railway-Testing/
│
├── README.md
├── pom.xml
│
├── Manual-Testing/
│   ├── Test-Cases/
│   │   └── TC_Railway.xlsx
│   │
│   └── Bug-Reports/
│       └── Bug Report.docx
│
├── Automation-Testing/
│   └── src/
│       └── test/
│           └── java/
│               └── tests/
│
└── Screenshots/
```

> Note: The automation source code and screenshots should be added to the corresponding directories when available.

---

## 📝 6. Manual Testing

Manual testing was performed to verify the main features of the Railway Ticket Booking Website.

### Test Case Design

Test cases were designed based on functional requirements and expected application behavior.

Each test case includes:

- Test Case ID
- Test Scenario
- Test Steps
- Test Data
- Expected Result
- Actual Result
- Test Status

### Test Execution

The testing process follows these steps:

1. Analyze the functional requirements.
2. Identify test scenarios.
3. Design test cases.
4. Prepare test data.
5. Execute test cases.
6. Compare actual and expected results.
7. Report defects.
8. Retest defects and perform regression testing when applicable.

📄 **Test Case Documentation:** [TC_Railway.xlsx](./Manual-Testing/Test-Cases/TC_Railway.xlsx)

---

## 🐞 7. Bug Reporting

During manual testing, **8 defect reports** were documented across different application modules.

### Sample Defects

| Bug ID | Module | Defect Description |
|---|---|---|
| BUG_001 | Login | Incorrect error message for invalid login credentials |
| BUG_002 | Login | Missing warning after multiple failed login attempts |
| BUG_003 | Registration | Incorrect registration success message |
| BUG_004 | Change Password | Incorrect success message formatting |
| BUG_005 | Registration | Missing punctuation in field validation messages |
| BUG_006 | Forgot Password | SMTP server error prevents password reset |
| BUG_007 | Forgot Password | SMTP issue blocks password confirmation testing |
| BUG_008 | Ticket Booking | Incorrect capitalization in booking confirmation |

### Bug Report Format

Each defect report includes:

- Bug ID and related Test Case ID
- Summary and Description
- Steps to Reproduce
- Actual Result
- Expected Result
- Screenshot Evidence

📄 **Bug Report Documentation:** [Bug Report.docx](./Manual-Testing/Bug-Reports/Bug%20Report.docx)

---

## 🤖 8. Automation Testing

Automation testing is developed using **Java, Selenium WebDriver, and TestNG**, with Maven for dependency management.

### Automation Objectives

- Automate selected repetitive functional test scenarios.
- Reduce manual effort during regression testing.
- Improve consistency of test execution.
- Practice writing maintainable and reusable automation scripts.

### Framework Dependencies

| Dependency | Version |
|---|---|
| Selenium Java | 4.31.0 |
| TestNG | 7.11.0 |
| WebDriverManager | 5.8.0 |
| Java | 24 |

### Maven Configuration

The project uses `pom.xml` to manage dependencies and configure the Java compilation environment.

### Running Automated Tests

**Step 1: Clone the repository**

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

**Step 2: Navigate to the project directory**

```bash
cd YOUR_REPOSITORY
```

**Step 3: Install dependencies**

```bash
mvn clean install
```

**Step 4: Execute automated tests**

```bash
mvn test
```

> Note: These commands assume the automation test source code has been added and the Maven test execution configuration is complete.

---

## 📊 9. Testing Deliverables

The project includes the following testing artifacts:

| Deliverable | Description |
|---|---|
| Test Case Document | Functional test cases and execution records |
| Bug Report | 8 documented defects with reproduction steps |
| Maven Configuration | Automation project dependencies |
| Automation Scripts | Selenium and TestNG test scripts (to be added) |
| Test Evidence | Screenshots included in bug reports |

---

## ⚠️ 10. Known Issues & Limitations

Several issues were identified during testing:

- The password reset process is blocked by an SMTP server error.
- Account activation behavior could not be fully verified because activation emails were not received.
- Some application messages do not match the expected specifications.
- Certain test scenarios are blocked by application or environment limitations.

These limitations were documented to maintain transparency and ensure accurate test reporting.

---

## 📚 11. Skills Demonstrated

Through this project, the following software testing skills are demonstrated:

**Manual Testing**
- Test Case Design & Execution
- Functional Testing
- UI Testing
- Defect Reporting
- Test Documentation
- Positive & Negative Testing

**Automation Testing**
- Java Programming
- Selenium WebDriver
- TestNG
- Maven Dependency Management
- Browser Automation

**Quality Assurance**
- Requirement Analysis
- Defect Identification
- Test Result Analysis
- Testing Process Documentation

---

## 👩‍💻 12. Author

**Role:** Software Tester – Manual & Automation Testing

**Project:** Railway Ticket Booking Website

**Purpose:** Software Testing Portfolio Project

---

⭐ This project demonstrates practical software testing experience through manual test execution, defect documentation, and Selenium-based automation development.
