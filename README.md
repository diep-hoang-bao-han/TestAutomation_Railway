
# 🚆 Railway Ticket Booking – Automation Testing

![Java](https://img.shields.io/badge/Java-24-orange)
![Selenium](https://img.shields.io/badge/Selenium-4.31.0-green)
![TestNG](https://img.shields.io/badge/TestNG-7.11.0-red)
![Maven](https://img.shields.io/badge/Maven-Build_Tool-blue)
![POM](https://img.shields.io/badge/Design-Page_Object_Model-purple)

## 📌 Project Overview

This project focuses on **automated functional testing** of a Railway Ticket Booking Website using Java, Selenium WebDriver, and TestNG.

The automation framework follows the **Page Object Model (POM)** design pattern to improve code reusability, maintainability, and test execution efficiency.

Automated tests cover key application functionalities, with defects identified during testing documented in bug reports.

**Application:** http://railwayb2.somee.com  
**Role:** Automation Tester

## 🛠️ Tech Stack

| Category | Technologies / Tools |
|---|---|
| Language | Java 24 |
| Automation | Selenium WebDriver 4.31.0 |
| Test Framework | TestNG 7.11.0 |
| Design Pattern | Page Object Model (POM) |
| Build Tool | Maven |
| Driver Management | WebDriverManager 5.8.0 |
| IDE | IntelliJ IDEA |

## 🔍 Automation Scope

- **Authentication:** Login and Registration.
- **Password Management:** Forgot Password, Reset Password, and Change Password.
- **Ticket Booking:** Ticket booking and confirmation validation.
- **Ticket Management:** View and manage booked tickets.
- **Train Timetable:** Train schedule functionality.

## ⚙️ Framework Highlights

- Implemented Page Object Model (POM) architecture.
- Developed reusable Page Objects and utility classes.
- Centralized browser management using WebDriverFactory.
- Organized test setup and execution using BaseTest and TestNG.
- Managed project dependencies with Maven.
- Documented defects identified during automation testing.

## 📊 Test Artifacts

| Artifact | Description |
|---|---|
| [Automation Test Scripts](./src/test/java/tests) | Selenium automated test cases |
| [Page Objects](./src/main/java/pages) | Reusable page classes |
| [Test Case Documentation](./TC_Railway.xlsx) | Test scenarios and expected results |
| [Bug Reports](./Bug%20Report.docx) | 8 documented defects identified during testing |
| [Maven Configuration](./pom.xml) | Project dependencies |

## 🐞 Defect Reporting

During test execution, **8 defects** were documented, including:

- Incorrect validation and confirmation messages.
- Missing warnings after repeated failed login attempts.
- SMTP server errors blocking password reset scenarios.
- UI message formatting inconsistencies.

Each bug report includes reproduction steps, actual results, expected results, and screenshot evidence.

## 👩‍💻 Author

**Diệp Hoàng Bảo Hân**  
Automation Tester

---

⭐ Selenium-based automation testing project demonstrating Page Object Model implementation, functional test automation, and defect reporting.
