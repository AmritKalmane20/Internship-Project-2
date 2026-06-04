# Week 1 – Environment Setup and Reconnaissance

## Project Overview

This repository contains the Week 1 activities of a Web Application Penetration Testing Internship. The objective of this phase was to establish a secure and controlled penetration testing environment, study common web application vulnerabilities, and perform reconnaissance on intentionally vulnerable applications.

The testing environment was configured using OWASP Juice Shop and DVWA (Damn Vulnerable Web Application), while Burp Suite and Nmap were used for traffic analysis and reconnaissance activities.

---

## Objectives

* Study the OWASP Top 10 Web Application Security Risks
* Configure a penetration testing environment
* Deploy OWASP Juice Shop using Docker
* Verify Apache and MariaDB services
* Configure Burp Suite as an intercepting proxy
* Perform reconnaissance and traffic analysis
* Discover application endpoints for future vulnerability assessment

---

## Tools and Technologies Used

| Tool                         | Purpose                            |
| ---------------------------- | ---------------------------------- |
| Kali Linux                   | Penetration Testing Platform       |
| OWASP Juice Shop             | Vulnerable Web Application         |
| DVWA                         | Vulnerable Web Application         |
| Docker                       | Container Deployment               |
| Burp Suite Community Edition | Traffic Interception & Analysis    |
| Firefox Browser              | Web Application Access             |
| Nmap                         | Reconnaissance & Service Discovery |
| Apache2                      | Web Server                         |
| MariaDB                      | Database Server                    |

---

## OWASP Top 10 Vulnerabilities Studied

* Broken Access Control
* Cryptographic Failures
* Injection Attacks
* Insecure Design
* Security Misconfiguration
* Vulnerable Components
* Identification and Authentication Failures
* Software and Data Integrity Failures
* Security Logging and Monitoring Failures
* Server-Side Request Forgery (SSRF)

---

## OWASP Juice Shop Deployment

### Verify Docker Installation

```bash
docker --version
```

### Download Juice Shop Image

```bash
docker pull bkimminich/juice-shop
```

### Run Juice Shop Container

```bash
docker run -d -p 3000:3000 bkimminich/juice-shop
```

### Verify Running Containers

```bash
docker ps
```

### Access Application

```text
http://127.0.0.1:3000
```

---

## Service Verification

### Check Apache Status

```bash
systemctl status apache2
```

### Check MariaDB Status

```bash
systemctl status mariadb
```

### Check Active Ports

```bash
ss -tulnp
```

### Services Identified

| Port | Service                 |
| ---- | ----------------------- |
| 80   | Apache HTTP Server      |
| 3000 | OWASP Juice Shop        |
| 3306 | MariaDB Database Server |

---

## Reconnaissance Using Nmap

### Command

```bash
nmap -sV 127.0.0.1
```

### Results

The scan successfully identified:

* Apache HTTP Server (Port 80)
* OWASP Juice Shop (Port 3000)
* MariaDB Database Server (Port 3306)

---

## Burp Suite Configuration

### Launch Burp Suite

```bash
burpsuite
```

### Proxy Configuration

```text
HTTP Proxy : 127.0.0.1
Port       : 8080
```

### Activities Performed

* Configured Firefox Proxy Settings
* Enabled Request Interception
* Captured HTTP Requests
* Monitored HTTP Responses
* Analyzed API Endpoints

---

## Endpoint Discovery

The following endpoints were identified during traffic analysis:

```text
/api/Products
/api/Challenges
/api/BasketItems
/api/Quantitys
/rest/admin/application-configuration
```

### Functional Areas Identified

* Product Management
* User Authentication
* Basket Operations
* Administrative Configuration
* Application Challenge Tracking

---

## Challenges Encountered

### Issue 1: Juice Shop Not Accessible

**Cause:** Docker container was not running correctly.

**Solution:** Verified running containers and restarted the application.

**Result:** Application became accessible successfully.

---

### Issue 2: Burp Suite Not Capturing Traffic

**Cause:** Incorrect browser proxy configuration.

**Solution:** Configured Firefox to use 127.0.0.1:8080.

**Result:** Burp Suite successfully captured HTTP requests and responses.

---

### Issue 3: Empty Site Map in Burp Suite

**Cause:** Community Edition limitations.

**Solution:** Utilized HTTP History for traffic analysis.

**Result:** Successfully identified application endpoints.

---

## Key Outcomes

* Successfully studied OWASP Top 10 vulnerabilities
* Deployed OWASP Juice Shop using Docker
* Verified Apache and MariaDB services
* Conducted reconnaissance using Nmap
* Configured Burp Suite for traffic interception
* Identified important API endpoints
* Prepared the environment for future vulnerability assessments

---

## Repository Structure

```text
Week-1/
├── Installation_setup_week1.pdf
├── README.md
└── Screenshots/
```

---

## References

* OWASP Top 10 – https://owasp.org/www-project-top-ten/
* OWASP Juice Shop – https://owasp.org/www-project-juice-shop/
* Burp Suite Documentation – https://portswigger.net/burp/documentation
* Nmap Documentation – https://nmap.org/book/man.html
* Docker Documentation – https://docs.docker.com/

---

# Week 2 – Web Application Traffic Analysis and API Enumeration Using Burp Suite

## Overview

This repository documents the activities completed during Week 2 of my Web Application Penetration Testing Internship. The primary objective of this phase was to analyze web application traffic, enumerate APIs, understand request-response mechanisms, and identify potential attack surfaces using Burp Suite Community Edition.

## Objectives

* Understand HTTP and HTTPS communication
* Capture and analyze web application traffic
* Perform API endpoint enumeration
* Identify request parameters and response structures
* Analyze application behavior through intercepted traffic
* Document findings for future vulnerability assessment

## Tools Used

| Tool                         | Purpose                         |
| ---------------------------- | ------------------------------- |
| Kali Linux                   | Penetration Testing Platform    |
| Burp Suite Community Edition | Traffic Interception & Analysis |
| Firefox Browser              | Web Application Testing         |
| OWASP Juice Shop             | Vulnerable Target Application   |
| Docker                       | Application Deployment          |

## Activities Performed

### Burp Suite Configuration

* Configured Burp Suite as an intercepting proxy
* Set browser proxy settings to route traffic through Burp
* Verified successful interception of HTTP requests and responses

### Traffic Analysis

* Captured incoming and outgoing web requests
* Examined HTTP headers, cookies, and session information
* Analyzed application behavior through intercepted traffic

### API Enumeration

* Identified accessible API endpoints
* Examined request methods (GET, POST, PUT, DELETE)
* Reviewed parameters passed between client and server
* Analyzed API responses for information disclosure

### Request and Response Analysis

* Studied request structures
* Examined response codes and server behavior
* Identified application functionalities exposed through APIs

## Skills Demonstrated

* Web Application Traffic Analysis
* API Enumeration
* Burp Suite Usage
* HTTP Request Inspection
* Endpoint Discovery
* Security Assessment Methodology

## Key Findings

* Successfully intercepted web application traffic
* Identified multiple API endpoints
* Analyzed request-response communication
* Documented application functionality exposed through APIs
* Prepared the environment for further vulnerability assessment

## Screenshots

Include screenshots demonstrating:

* Burp Suite Proxy Configuration
* Intercepted HTTP Requests
* HTTP History Analysis
* API Endpoint Enumeration
* Request and Response Inspection

## Outcome

The objectives of Week 2 were successfully completed. Traffic analysis and API enumeration provided valuable insights into application behavior and established a foundation for future vulnerability assessment activities.

## Author

**Amrit A. Kalmane**

BCA Student | Cybersecurity Enthusiast | Penetration Testing Intern
