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

## Key Findings Summary
- SQL Injection: High Risk. Vulnerable endpoint found in search queries.
- Cross-Site Scripting: Medium Risk. Reflective input strings not properly sanitized.
- Missing Security Headers: Low Risk. Lack of anti-clickjacking defense detected.

## Remediation and Strategic Recommendations
- Input Validation: Implement context-aware escaping for client-supplied data.
- Security Headers: Enforce protective response headers across application boundaries.

Disclaimer: This assessment was conducted entirely within an authorized local laboratory environment for educational purposes.
