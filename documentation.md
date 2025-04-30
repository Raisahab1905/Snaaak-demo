
# Frontend Documentation

![Image](https://thumbs.dreamstime.com/b/frontend-development-web-banner-concept-website-interface-frontend-development-web-banner-concept-website-interface-design-159250288.jpg)

---

## Author Information

| **Created** | **Version** | **Last Modified** | **Author** | **Level** | **Reviewer** |
|-------------|-------------|-------------------|------------|------------|--------------|
| 26-04-2025  | V1.1         | 28-04-2025         | Prateek Rai | Internal review | Siddharth Pawar |

---

## Table of Contents

- [Introduction](#introduction)
-  [Purpose](#purpose)
- [Key Features](#key-features)
- [Pre-requisites](#pre-requisites)
- [Software Overview](#software-overview)
- [Important Ports](#important-ports)
- [Architecture](#architecture)
- [Troubleshooting](#troubleshooting)
- [Conclusion](#conclusion)
- [Contact](#contact)
- [References](#references)

---

## Introduction

This document provides the details for setting up and working with the Frontend application found in the GitHub repository: [OT-MICROSERVICES/frontend](https://github.com/OT-MICROSERVICES/frontend). It covers architecture, dependencies, troubleshooting guidance and installation setup reference as well for users and developers.

---

## Purpose

The Frontend application is designed to serve as the user interface for interacting with backend services, allowing users to view and interact with various features of the system through a browser-based interface. It focuses on creating an intuitive and user-friendly environment.

---

## Key Features

| **Feature**          | **Description**                                               |
|-----------------------|---------------------------------------------------------------|
| Responsive Design     | Ensures the frontend works seamlessly across different devices.|
| Component-based       | Built using React.js for modular and reusable UI components.  |
| API Integration       | Consumes backend APIs to display dynamic content in real time.|
| User Authentication   | Integrated login system for user management and session handling.|

---

## Pre-requisites

| **Requirement**        | **Details**                                      |
|-------------------------|--------------------------------------------------|
| Operating System        | Linux, Windows, or macOS                         |
| Software Version        | Compatible with React v17+ and Node.js v14+      |
| Hardware Requirements   | Minimum of 2GB RAM, 1.5 GHz Processor, 1GB Disk Space |

---

## Software Overview

| **Software** | **Version** | **Description**                             |
|--------------|-------------|---------------------------------------------|
| React.js     | 17.x.x       | JavaScript library for building UIs.        |
| Node.js      | 14.x.x       | JavaScript runtime environment.            |

---

## Important Ports

| **Ports** | **Description**                                   |
|-----------|---------------------------------------------------|
| 3000      | Default port used by the React.js development server. |
| 443       | Standard port for secure HTTPS communication.    |

---

## Architecture

![Image](https://github.com/Raisahab1905/Snaaak-demo/blob/main/386696373-3fe57c96-3e8b-4407-afc3-1beb61163959.png?raw=true)

### Frontend Web:
The Frontend Web is the primary user interface for the OT-Microservices stack. It is a ReactJS-based application that allows users to interact with the system through a web browser. Built using the ReactJS framework, it provides a fast, responsive, and dynamic UI that can handle complex user interactions with minimal loading times.

### Employee API:
The Employee API is responsible for managing all employee-related data and operations within the system. It is one of the critical microservices in the OT-Microservices stack, providing endpoints for creating, reading, updating, and deleting (CRUD) employee records.

### Salary API:
The Salary API manages all salary-related operations, including salary calculations, pay slips, and adjustments. It serves as another independent microservice in the stack and is tightly integrated with both the frontend and the other APIs.

### Attendance API:

The Attendance API handles all aspects of employee attendance tracking and management. This includes logging attendance, monitoring work hours, and tracking leaves or absences.


---

## Troubleshooting

### Issue 1: Application not loading after `npm start`

**Solution**:

- Ensure Node.js and npm are installed correctly.
- Try clearing the npm cache:

```bash
npm cache clean --force
```

- Verify there are no dependency conflicts.

### Issue 2: CORS error when accessing APIs

**Solution**:

- Make sure the backend server allows CORS from the frontend domain.

---


## Conclusion

This document outlines the architecture, dependencies and troubleshooting steps required for using the Frontend application. With its modular and responsive design, it can be adapted for various use cases.

---

## Contact

| **Name**         | **Email Address**                            |
|------------------|----------------------------------------------|
| Prateek Rai   | prateek.rai.snaatak@mygurukulam.co         |

---

## References

| **Links**                                                        | **Descriptions**                           |
|-------------------------------------------------------------------|--------------------------------------------|
| [React Documentation](https://reactjs.org/docs/getting-started.html) | Official React.js documentation.         |
| [Node.js Documentation](https://nodejs.org/en/docs/)             | Official Node.js documentation.           |
| [Frontend API setup](https://github.com/snaatak-Downtime-Crew/Documentation/tree/SCRUMS-82-Nishkarsh/ot-ms-understanding/frontend/poc#1-update-package-index)     | Step by step installation and set of frontend API   |

