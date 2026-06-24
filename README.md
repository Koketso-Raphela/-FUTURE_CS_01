# -FUTURE_CS_01
# News24 Vulnerability Assessment Report

## Overview

This repository contains a passive vulnerability assessment conducted against **News24 ([www.news24.com](http://www.news24.com))** as part of the **Future Interns Fellowship Cybersecurity Internship Program**.

The assessment was performed strictly within ethical boundaries using only non-intrusive reconnaissance and analysis techniques. The objective was to evaluate the public-facing security posture of News24 by identifying exposed services, reviewing security configurations, and assessing potential security weaknesses.

> **Assessment Date:** 10 June 2026
> **Assessment Type:** Passive Vulnerability Assessment
> **Overall Risk Rating:** Medium

---

## Objectives

* Perform passive reconnaissance on the target website.
* Identify exposed services and publicly accessible ports.
* Analyze HTTP security headers.
* Review browser console output for information leakage.
* Inspect cookie security configurations.
* Conduct passive traffic analysis using OWASP ZAP.
* Evaluate the overall security posture and provide remediation recommendations.

---

## Scope

### In Scope

* Public-facing web pages
* Passive scanning and observation
* HTTP security header analysis
* Browser Developer Tools inspection
* Configuration review

### Out of Scope

* Exploitation of vulnerabilities
* Authentication bypass attempts
* Brute-force attacks
* Denial-of-Service (DoS) attacks
* Any activity capable of disrupting services

---

## Methodology

The following methodology was used during the assessment:

1. Reconnaissance and information gathering
2. Nmap port scanning
3. HTTP security header analysis
4. Browser console review
5. Cookie inspection
6. OWASP ZAP passive scanning
7. Risk classification and reporting

---

## Tools Used

| Tool                | Purpose                              |
| ------------------- | ------------------------------------ |
| Nmap                | Port scanning and service detection  |
| Browser DevTools    | Header, cookie, and console analysis |
| SecurityHeaders.com | Security header evaluation           |
| OWASP ZAP           | Passive traffic analysis             |

---

## Key Findings

| ID | Finding                                             | Risk Level                       |
| -- | --------------------------------------------------- | -------------------------------- |
| F1 | Non-standard ports 8080 and 8443 publicly exposed   | High                             |
| F2 | HTTP Port 80 accepts unencrypted traffic            | High                             |
| F3 | Outdated JavaScript library in production           | Medium                           |
| F4 | Browser console errors publicly visible             | Medium                           |
| F5 | First-party cookies missing Secure flag             | Medium                           |
| F6 | Narrow Content Security Policy scope                | Medium                           |
| F7 | Deprecated Feature-Policy header in use             | Low                              |
| F8 | Cloudflare rate limiting blocked automated scanning | Informational (Positive Control) |
| F9 | Cloudflare masking origin infrastructure            | Informational (Positive Control) |

---

## Positive Security Controls Identified

* Cloudflare CDN protecting the origin infrastructure.
* Effective rate limiting and bot mitigation.
* Strong HTTP security header implementation.
* HSTS, X-Frame-Options, and X-Content-Type-Options correctly configured.
* SecurityHeaders.com rating: **A**

---

## Recommendations

### Immediate Actions

* Restrict or disable unnecessary public access to ports **8080** and **8443**.
* Force all traffic to HTTPS.
* Enable HSTS with long-duration policies.
* Set the `Secure` flag on all first-party cookies.
* Remove or update outdated JavaScript libraries.
* Expand Content Security Policy directives.

### Long-Term Improvements

* Conduct regular vulnerability assessments.
* Implement automated dependency scanning within CI/CD pipelines.
* Review security header configurations periodically.
* Monitor third-party libraries for newly disclosed vulnerabilities.
* Maintain Cloudflare security controls and rate-limiting policies.

---

## Ethical Notice

This assessment was conducted solely for educational and internship purposes. Only passive, read-only techniques were employed, and no exploitation or disruptive testing was performed.

---

## Disclaimer

This report does not represent a comprehensive penetration test. Findings are based exclusively on passive observation of publicly accessible resources and should not be interpreted as confirmation of exploitable vulnerabilities.

---

## Author

**Makgomo Koketso Raphela**
Future Interns Fellowship Program
Cybersecurity Internship | June 2026
