# API Security Assessment (Authorized Lab) Regional Elderly Care Facility

**SDC Internship Week 3 (Professional Advanced Build)**
**Prepared by:** Member 3 (Zoya Zia)
**Target:** VAmPI (Vulnerable API), running locally in Docker http://localhost:5000
**Primary tool:** OWASP ZAP 2.17.0, plus manual authentication/authorization testing

## Overview

This repository contains an authorized security assessment of a lab API modeled on a fictional Regional Elderly Care Facility, focused on authentication and authorization (authz/authn) issues. The full write-up, scope statement, methodology, and detailed findings are in the report file.

## Contents

- **Report** : full written report (scope, methodology, findings, recommendations)
- **/screenshots** : evidence for each finding (setup, manual tests, ZAP scan and alerts)

## Summary of findings

| ID | Finding | Severity | Found by |
|----|---------|----------|----------|
| Z1 | SQL Injection in the username parameter | High | OWASP ZAP active scan |
| M1 | Unauthenticated disclosure of user data | High | Manual testing |
| M2 | Debug endpoint (`/users/v1/_debug`) reachable without a token | High | Manual testing |
| Z2 | Server version disclosed in response header | Low | OWASP ZAP passive scan |
| Z3 | X-Content-Type-Options header missing | Low | OWASP ZAP passive scan |
| M3 | Email update endpoint ignores the username in the URL | Informational | Manual testing |

Full details, evidence, and recommendations for each finding are in the report.

## Tools used

- **OWASP ZAP** : active/passive scanning, OpenAPI-driven import
- **Docker** : running the VAmPI lab target
- **Swagger UI / PowerShell** : manual authentication and authorization testing

## Key takeaway

OWASP ZAP and manual testing found different categories of issues. ZAP identified technical vulnerabilities (SQL injection, missing headers), while manual testing identified authorization gaps (data accessible without login) that an automated scanner cannot judge on its own. Both approaches were necessary to fully cover the assignment's authz/authn focus.

## AI Assistance Disclosure

Claude (Anthropic) was used as a learning aid throughout this task : to explain authentication/authorization concepts, guide the Docker and OWASP ZAP setup, help interpret ZAP alerts, and assist in formatting the report. All findings were independently verified manually as documented in the report.
