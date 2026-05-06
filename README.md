# Pet Store API Test Automation

A comprehensive test automation framework for the **Swagger Petstore API** built using **REST Assured** and a **Fluent Design Framework** from scratch.

**API URL:** [https://petstore.swagger.io](https://petstore.swagger.io)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Technologies & Dependencies](#technologies--dependencies)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Running Tests](#running-tests)
- [Test Coverage](#test-coverage)
- [Framework Features](#framework-features)
- [Reporting](#reporting)
- [Contributing](#contributing)

---

## 🎯 Overview

This project provides an automated testing solution for the Swagger Petstore API, implementing best practices in API test automation including:

- **Fluent API design patterns** for readable and maintainable test code
- **REST Assured library** for HTTP request/response handling
- **TestNG framework** for test execution and organization
- **JSON schema validation** for response validation
- **Extent Reports** for comprehensive test reporting
- **Apache POI** for data-driven testing with Excel files
- **Java Faker** for generating realistic test data

---

## 🛠️ Technologies & Dependencies

### Core Technologies
- **Java 20** - Programming Language
- **Maven** - Build and Dependency Management

### Testing Libraries
| Dependency | Version | Purpose |
|-----------|---------|---------|
| REST Assured | 5.4.0 | API Testing & HTTP Requests |
| JSON Path | 5.3.1 | JSON Response Parsing |
| JSON Schema Validator | 5.3.2 | Schema Validation |
| TestNG | 7.8.0 | Test Framework & Assertions |
| JSON (org.json) | 20231013 | JSON Processing |

### Reporting & Data Handling
| Dependency | Version | Purpose |
|-----------|---------|---------|
| Extent Reports | 5.0.9 | Advanced Test Reporting |
| Apache POI | 5.2.3 | Excel Data Reading/Writing |
| Apache POI OOXML | 5.2.3 | OOXML Format Support |

### Utilities
| Dependency | Version | Purpose |
|-----------|---------|---------|
| Java Faker | 1.0.2 | Test Data Generation |
| ScribeJava APIs | 8.3.1 | OAuth Support |

---

## 📁 Project Structure

```
Pet-Store-API-Test-Automation/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/
│   │   │       ├── api/
│   │   │       ├── utils/
│   │   │       ├── models/
│   │   │       └── config/
│   │   └── resources/
│   └── test/
│       ├── java/
│       │   └── com/example/
│       │       ├── tests/
│       │       └── base/
│       └── resources/
│           ├── testdata/
│           └── schemas/
├── pom.xml
├── README.md
└── .gitignore
```

---

## ⚙️ Prerequisites

- **Java Development Kit (JDK) 20** or higher
- **Maven 3.6+** for dependency management
- **Git** for version control
- Internet connection to access the Petstore API

### Installation Steps

1. **Install Java 20+**
   ```bash
   java -version
   ```

2. **Install Maven**
   ```bash
   mvn -version
   ```

3. **Clone the Repository**
   ```bash
   git clone https://github.com/AshfatAbegh/Pet-Store-API-Test-Automation.git
   cd Pet-Store-API-Test-Automation
   ```

---

## 🚀 Installation & Setup

### 1. Clone Repository
```bash
git clone https://github.com/AshfatAbegh/Pet-Store-API-Test-Automation.git
cd Pet-Store-API-Test-Automation
```

### 2. Install Dependencies
```bash
mvn clean install
```

### 3. Configure Project
Update configuration files in `src/main/resources/` with:
- API base URL
- Request/Response timeouts
- Proxy settings (if required)

---

## 🧪 Running Tests

### Run All Tests
```bash
mvn clean test
```

### Run Specific Test Class
```bash
mvn clean test -Dtest=PetStoreTests
```

### Run Tests with Specific Suite
```bash
mvn clean test -Dsuites=src/test/resources/testng.xml
```

### Run Tests in Parallel
```bash
mvn clean test -Dparallel=true -DthreadCount=4
```

---

## 📊 Test Coverage

The framework provides comprehensive test coverage for:

### Pet Endpoints
- ✅ Add a new pet
- ✅ Update an existing pet
- ✅ Get pet by ID
- ✅ Find pets by status
- ✅ Find pets by tags
- ✅ Delete a pet

### Order Endpoints
- ✅ Place an order
- ✅ Get order by ID
- ✅ Delete an order

### User Endpoints
- ✅ Create user(s)
- ✅ Get user by username
- ✅ Update user
- ✅ Delete user
- ✅ User login/logout

---

## 🏗️ Framework Features

### 1. Fluent Design Pattern
Clean, readable test code with fluent API:
```java
given()
    .baseUri("https://petstore.swagger.io/v2")
    .contentType(ContentType.JSON)
    .body(petPayload)
when()
    .post("/pet")
then()
    .statusCode(200)
    .assertThat()
    .body("id", notNullValue());
```

### 2. Request/Response Handling
- Automatic serialization/deserialization
- Custom request builders
- Response extraction utilities
- Header management

### 3. Assertions & Validations
- REST Assured assertions
- JSON schema validation
- Custom validation methods
- Response time assertions

### 4. Test Data Management
- Excel-based test data (Apache POI)
- Dynamic data generation (Java Faker)
- Parameterized tests (TestNG DataProvider)
- Test fixtures and setup/teardown

### 5. Error Handling
- Comprehensive exception handling
- Detailed error logging
- API error response validation

---

## 📈 Reporting

### Extent Reports Integration
Detailed HTML reports generated with:
- Test execution summary
- Pass/Fail statistics
- Screenshots and logs
- Execution timeline
- Test categorization

### Report Location
```
target/surefire-reports/
```

### View Report
```bash
open target/ExtentReport.html  # macOS
start target/ExtentReport.html # Windows
```

---

## 📝 Best Practices Implemented

✅ **Page Object Model** - Organized API endpoints structure  
✅ **DRY Principle** - Reusable utility methods  
✅ **Fluent Assertions** - Readable test code  
✅ **Data-Driven Testing** - Parameterized tests  
✅ **Logging** - Comprehensive test execution logs  
✅ **Annotations** - Clear test metadata  
✅ **Exception Handling** - Robust error management  
✅ **Configuration Management** - Externalized settings  

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/YourFeature`)
3. **Commit** your changes (`git commit -m 'Add YourFeature'`)
4. **Push** to the branch (`git push origin feature/YourFeature`)
5. **Open** a Pull Request

### Coding Standards
- Follow Java naming conventions
- Write descriptive test method names
- Add comments for complex logic
- Maintain consistent indentation
- Update this README for new features

---

## 📚 Resources

- **Swagger Petstore API:** [https://petstore.swagger.io](https://petstore.swagger.io)
- **REST Assured Documentation:** [https://rest-assured.io](https://rest-assured.io)
- **TestNG Documentation:** [https://testng.org](https://testng.org)
- **Maven Guide:** [https://maven.apache.org](https://maven.apache.org)

---

## 📄 License

This project is open source and available under the MIT License.

---

## 👨‍💻 Author

**Ashfat Abegh**

---

## 🐛 Issue Tracking

Found a bug? Have a suggestion? Please create an [Issue](https://github.com/AshfatAbegh/Pet-Store-API-Test-Automation/issues)

---

**Last Updated:** May 2026
