# POC of Notification-API

---

## Author Information

| Created/Modified | Version | Author       | Comment         | Internal Reviewer    |
|------------------|---------|--------------|------------------|----------------------|
| 24-04-2025       | V1      | Prateek Rai  | Initial Commit   | Siddharth Pawar      |

---

## Table of Contents

- [Introduction](#introduction)
- [Supported Features](#supported-features)
- [Pre-requisites](#pre-requisites)
- [System Requirements](#system-requirements)
- [Important Ports](#important-ports)
- [Architecture](#architecture)
- [Dependencies](#dependencies)
- [Step-by-step Installation](#step-by-step-installation)
  - [Update System and Install Dependencies](#update-system-and-install-dependencies)
  - [Verify Python and pip](#verify-python-and-pip)
  - [Clone the Repository](#clone-the-repository)
  - [Set Up Virtual Environment](#set-up-virtual-environment)
  - [Install Python Dependencies](#install-python-dependencies)
  - [Install Elasticsearch](#install-elasticsearch)
- [Configure & Run the Application](#configure--run-the-application)
  - [Add Test Data](#add-test-data)
  - [Configure YAML](#configure-yaml)
  - [Run the Notification Service](#run-the-notification-service)
- [Testing the Application](#testing-the-application)
- [Conclusion](#conclusion)
- [Contacts](#contacts)
- [References](#references)

---

## Introduction

This POC outlines the setup of the `Notification API` without using Docker. It leverages Python, Elasticsearch, and local system services to run the application as intended.

---

## Supported Features

- Sends Email notifications based on data
- Integration with Elasticsearch to fetch records
- Configurable SMTP via YAML
- CLI mode selection for flexibility (`external` / `cron`)

---

## Pre-requisites

| Tool         | Version   |
|--------------|-----------|
| Python       | 3.8+      |
| pip          | 20+       |
| Git          | Any       |
| Elasticsearch| 7.17.17   |
| Linux OS     | Ubuntu 20.04/22.04 recommended |

---

## System Requirements

- 2 vCPU
- 4 GB RAM
- 10 GB free disk
- Open ports: 9200 (Elasticsearch), 587 (SMTP)

---

## Important Ports

| Service         | Port |
|-----------------|------|
| Elasticsearch   | 9200 |
| SMTP (Gmail)    | 587  |

---

## Architecture

---


---

## Dependencies

- Python 3.x
- Elasticsearch 7.17.17
- SMTP (Gmail SMTP server)
- Python Libraries (from `requirements.txt`)

---

## Step-by-step Installation

### Update System and Install Dependencies

```
sudo apt update && sudo apt upgrade -y
sudo apt install python3 python3-pip python3-venv curl wget git -y ``` 
