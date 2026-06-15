## Internship Progress

* [x] Week 1 – Environment Setup and Reconnaissance
* [x] Week 2 – Vulnerability Assessment and Traffic Analysis
* [x] Week 3 – Security Misconfiguration and Access Control Testing
* [x] Week 4 – Final Reporting and Remediation

# Web Application Penetration Testing Internship

This repository contains the work completed during a four-week Web Application Penetration Testing Internship focused on the OWASP Top 10 security risks. The project involved deploying vulnerable web applications, performing reconnaissance, analyzing web traffic, assessing security weaknesses, documenting Proof-of-Concepts (PoCs), and providing remediation recommendations.

## Technologies Used

- Kali Linux
- OWASP Juice Shop
- DVWA
- Burp Suite Community Edition
- Docker
- Nmap
- Gobuster
- cURL
- Firefox Browser

## Key Skills Demonstrated

- Web Application Penetration Testing
- OWASP Top 10 Security Assessment
- Reconnaissance and Enumeration
- HTTP Traffic Analysis
- API Enumeration
- Security Misconfiguration Testing
- Access Control Assessment
- Vulnerability Documentation
- Proof-of-Concept Creation
- Remediation Planning



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

# Week 3 – Security Misconfiguration and Access Control Testing

## Overview

This repository documents the activities completed during Week 3 of my Web Application Penetration Testing Internship. The primary objective of this phase was to identify security misconfigurations, assess access control mechanisms, perform endpoint enumeration, and create Proof-of-Concept (PoC) documentation for discovered findings.

## Objectives

* Identify Security Misconfiguration vulnerabilities
* Assess Broken Access Control weaknesses
* Perform directory and endpoint enumeration
* Analyze administrative configuration endpoints
* Test authorization mechanisms
* Create professional Proof-of-Concept (PoC) reports
* Document security findings and remediation recommendations

## Tools Used

| Tool                         | Purpose                                   |
| ---------------------------- | ----------------------------------------- |
| Kali Linux                   | Penetration Testing Platform              |
| OWASP Juice Shop             | Vulnerable Web Application                |
| Burp Suite Community Edition | Traffic Analysis and Request Manipulation |
| Firefox Browser              | Web Application Testing                   |
| Nmap                         | Service Enumeration                       |
| cURL                         | HTTP Analysis and Endpoint Testing        |
| Gobuster                     | Directory Enumeration                     |
| Docker                       | Container Deployment                      |

## Activities Performed

### Security Misconfiguration Assessment

* Inspected HTTP response headers
* Analyzed application configuration information
* Reviewed exposed administrative endpoints
* Examined publicly accessible resources

### Directory and Resource Enumeration

* Enumerated hidden directories using Gobuster
* Inspected robots.txt and sitemap.xml files
* Identified application resources and endpoints

### Broken Access Control Testing

* Tested direct access to restricted application routes
* Evaluated authorization mechanisms
* Assessed administrative functionality access controls

### Burp Suite Analysis

* Captured and analyzed application traffic
* Inspected administrative endpoints
* Performed request manipulation using Burp Repeater
* Reviewed session and authorization-related requests

## Skills Demonstrated

* Security Misconfiguration Assessment
* Broken Access Control Testing
* Directory Enumeration
* Authorization Analysis
* Burp Repeater Usage
* Endpoint Discovery
* Proof-of-Concept Documentation

## Key Findings

* Administrative configuration information was exposed through application endpoints.
* Multiple application resources were identified through enumeration.
* Access control mechanisms were assessed for restricted functionality.
* Burp Suite successfully captured and analyzed administrative requests.
* Proof-of-Concept documentation was created for identified findings.

## Screenshots

Include screenshots demonstrating:

* HTTP Header Analysis
* Administrative Configuration Exposure
* Robots.txt Enumeration
* Gobuster Directory Enumeration
* Burp Suite HTTP History
* Burp Repeater Testing
* Access Control Testing
* Proof-of-Concept Evidence

## Outcome

The objectives of Week 3 were successfully completed. Security Misconfiguration and Access Control assessments provided deeper insight into application security and helped establish professional vulnerability documentation practices.

---

# Week 4 – Final Reporting and Remediation

## Overview

This repository documents the activities completed during Week 4 of my Web Application Penetration Testing Internship. The primary objective of this phase was to consolidate findings from previous weeks, prepare a comprehensive penetration testing report, document Proof-of-Concept evidence, and provide remediation recommendations for identified security weaknesses.

## Objectives

* Consolidate findings from Weeks 1–3
* Validate previously identified vulnerabilities
* Prepare a professional penetration testing report
* Create Proof-of-Concept documentation
* Assess security impact and risk levels
* Provide remediation recommendations
* Document testing evidence and screenshots

## Tools Used

| Tool                         | Purpose                         |
| ---------------------------- | ------------------------------- |
| Kali Linux                   | Penetration Testing Platform    |
| OWASP Juice Shop             | Target Web Application          |
| Burp Suite Community Edition | Traffic Analysis and Validation |
| Firefox Browser              | Application Testing             |
| Nmap                         | Service Verification            |
| cURL                         | API Verification                |
| Gobuster                     | Resource Verification           |
| Docker                       | Environment Management          |

## Activities Performed

### Final Validation

* Verified application availability
* Confirmed running services
* Reviewed application endpoints
* Validated previously identified findings

### Vulnerability Documentation

* Organized assessment results
* Documented identified findings
* Assigned risk levels
* Recorded evidence and observations

### Proof-of-Concept Creation

* Prepared vulnerability descriptions
* Documented reproduction steps
* Attached supporting evidence
* Explained security impacts

### Remediation Analysis

* Recommended corrective actions
* Identified security improvements
* Suggested access control enhancements
* Proposed configuration hardening measures

## Skills Demonstrated

* Penetration Testing Reporting
* Vulnerability Documentation
* Risk Assessment
* Security Analysis
* Remediation Planning
* Technical Documentation
* Professional Report Writing

## Key Findings Summary

| Vulnerability                    | Risk Level |
| -------------------------------- | ---------- |
| Security Misconfiguration        | Medium     |
| Information Disclosure           | Medium     |
| API Enumeration Exposure         | Low        |
| Broken Access Control Assessment | Medium     |
| Authentication Analysis          | Medium     |
| Input Validation Assessment      | Low        |

## Screenshots

Include screenshots demonstrating:

* Final Environment Verification
* Nmap Service Enumeration
* API Verification
* Burp HTTP History
* Burp Repeater Analysis
* Security Misconfiguration Evidence
* Broken Access Control Assessment
* Vulnerability Summary

## Outcome

The objectives of Week 4 were successfully completed. The penetration testing assessment was finalized, findings were documented professionally, remediation recommendations were provided, and the overall security posture of the target application was evaluated.

---

## Author

**Amrit A. Kalmane**

BCA Student | Cybersecurity Enthusiast | Penetration Testing Intern
