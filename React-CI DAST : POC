# React CI Checks DAST: POC

---

![image](https://github.com/user-attachments/assets/fabe8487-d70c-4dba-b9d6-ddcc1139b444)

---

## Author Information 
| Created     | Last Updated | Version | Author       | Comment         | Reviewer         |
|-------------|--------------|---------|--------------|------------------|------------------|
| 14-05-2025  | 14-05-2025   | V1    | Prateek Rai  | Internal Review  | Siddharth Pawar  |

---

## Table of Contents
- [Introduction](#introduction)
- [Purpose](#purpose)
- [Prerequisites](#prerequisites)
- [Steps to Set Up PoC](#steps-to-set-up)
- [Conclusion](#conclusion)

---

## Introduction
This Proof of Concept (POC) demonstrates how to set up a CI (Continuous Integration) pipeline for a React application with integrated CI checks and Dynamic Application Security Testing (DAST) using OWASP ZAP.
For more information related refer this link [DAST Documentation](https://github.com/snaatak-Downtime-Crew/Documentation/blob/SCRUMS-154-Prateek/application-ci/checks/react/dast/documentation/README.md#popular-dast-tools) 

---
## Purpose
The purpose of this Proof of Concept (POC) is to:
- **Automate the build, linting, and unit testing** of a React application using a CI/CD pipeline.
- **Integrate Dynamic Application Security Testing (DAST)** into the pipeline to identify potential security vulnerabilities at runtime.
- **Establish a repeatable and reliable CI/CD process** that enhances code quality and application security prior to merging code into the production environment.

---
## Prerequisites
Before implementing this Proof of Concept (POC), ensure the following tools and services are available:
| Category            | Requirement                                      | Description                                                   |
|---------------------|--------------------------------------------------|---------------------------------------------------------------|
| Version Control      | GitHub or GitLab repository                     | Used to store code and configure the CI/CD pipeline           |
| Runtime Environment  | Node.js and npm                                  | Required to run, build, and manage dependencies for React app |
| Application          | Sample or existing React application            | Used as the base for automating build, test, and security     |
| CI/CD Tool           | GitHub Actions or GitLab CI                     | To automate build, test, and DAST processes                   |

---
## Steps to Set Up 
### React App Folder Structure (Sample)
```bash
my-react-app/
├── .github/workflows/
│   └── ci.yml
├── public/
├── src/
│   └── components/
│   └── App.js
├── package.json
└── README.md
```
### Step 1: CI Workflow (GitHub Actions Example)
Create the following file: `.github/workflows/ci.yml`
This CI workflow automates build, linting, testing, and dynamic application security testing (DAST) using GitHub Actions.
```yaml
name: React CI Checks
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - name: Install dependencies
        run: npm ci
      - name: Run ESLint
        run: npm run lint
      - name: Run Tests
        run: npm test
  dast-scan:
    needs: build-and-test
    runs-on: ubuntu-latest
    steps:
      - name: Install OWASP ZAP
        run: sudo apt-get install zaproxy -y
      - name: Run DAST Scan
        run: |
          zap-baseline.py -t http://your-deployed-preview-url.com -r zap-report.html
 ```
### Step 2: Add Lint and Test Scripts
Update the `scripts` section of your `package.json` to include linting and testing commands. These scripts will be used in the CI workflow to validate code quality and functionality.
```json
"scripts": {
  "start": "react-scripts start",
  "build": "react-scripts build",
  "test": "react-scripts test --watchAll=false",
  "lint": "eslint ./src"
}
```
### Step 3: Add DAST Configuration (OWASP ZAP)
To integrate **Dynamic Application Security Testing (DAST)** using **OWASP ZAP**, you can start with a basic scan command. This helps identify runtime security vulnerabilities in your application.
#### Basic ZAP Scan Command
```bash
zap-baseline.py -t http://your-app-url.com -g gen.conf -r report.html
```
---

## Conclusion
This POC demonstrates an efficient and scalable way to enforce code quality and runtime security checks in a React application using CI pipelines. By integrating DAST with OWASP ZAP, you ensure vulnerabilities are identified early in the development lifecycle, significantly reducing the risk in production.
This setup can be extended with:
Deployment pipelines (CD)
Integration with Docker for isolated testing
Enhanced ZAP scanning policies
Notifications on failed security checks

---

## Contact Information
| Name       | Email Address                |
|------------|------------------------------|
| Prateek Rai  | prateek.rai.snaatak@mygurukulam.co|

---

## References
| **Link** | **Description** |
|------------------------------------------------------|------------------|
| [DAST in CI/CD](https://circleci.com/blog/dynamic-application-security-testing-dast/)| Documentation followed from this link      |
