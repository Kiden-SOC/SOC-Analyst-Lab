# Web Application Vulnerability Analysis Using OWASP ZAP

A hands-on security assessment demonstrating automated vulnerability scanning, risk identification, and remediation planning against a target web application environment.

## Tools and Technologies Used
- OWASP ZAP: Automated passive and active vulnerability scanner
- OWASP Juice Shop: Intentionally vulnerable application environment
- Security Reporting: Analysis and documentation of findings

## Project Methodology

### 1. Target Reconnaissance and Passive Scan
- Configured baseline settings inside the intercepting proxy.
- Spidered the web application to map all visible endpoints and directories.
- Executed passive scanning to monitor traffic headers without aggressive target interaction.

### 2. Active Attack Simulation
- Configured targeted policy scans to identify active injection points.
- Executed fuzzing inputs against login portals and input fields.
- Tested for critical risks including SQL Injection and Cross-Site Scripting.

### 3. Vulnerability Analysis and Triage
- Evaluated scanning alert logs to categorize risks by severity level.
- Verified findings to isolate and remove false positives.

## Executive Metrics
The automated assessment yielded 9 total alerts categorized by threat severity:
High Risk: 1
Medium Risk: 4
Low Risk: 3
Informational: 1

## Finding 1: SQL Injection
Risk Level: High Risk
Vulnerable Endpoint: /rest/products/search?q=
Analysis: The application's search bar parameter directly handles user data without server-side validation. Sending a single quote and an open parenthesis ('() alters the structured syntax of the underlying database query, triggering a visible database error. An attacker can exploit this structural flaw to bypass access controls or extract backend data.

## Finding 2: Medium Risk Vulnerabilities
Risk Level: Medium Risk 
Aggregated Count: 4 Alerts DetectedSummary 
Analysis: The scanner flagged four separate medium-severity instances across the application footprint. These issues primarily involve improper data handling and reflective input points, which could potentially expose session elements or permit unauthorized client-side script execution.

## Remediation and Strategic Recommendations
- Input Validation: Implement context-aware escaping for client-supplied data.
- Security Headers: Enforce protective response headers across application boundaries to suppress common cross-site risks.
- Implement Parameterised Queries:  Ensure the database layer utilizes prepared statements for the search endpoint. This strictly treats incoming input (such as ' or () as safe string literals rather than executable database commands. 

Disclaimer: This assessment was conducted entirely within an authorized local laboratory environment for educational purposes.
