# Attack Report — MySQL Brute Force
**Date:** 2026-03-17  
**Time:** 03:44 AM UTC  
**Severity:** High  

---

## Overview
While monitoring live traffic, a sudden rush of attacks at approx a rate of ~30/s attacks from the same IP which had an "unknown reputation" by an IP in Sweden at an extremely high rate for a good minute all directed at port 3306 with login attempts.
Credential logging wasn't possible due to the honeypot not implementing a full MYSQL authentication handshake, preventing credential logging.

---

## Attack Details
| Field        | Value                  |
|--------------|------------------------|
| Source IP    | 192.109.200.204        |
| Origin       | Sweden                 |
| Target Port  | 3306 (MySQL)           |
| Attack Type  | Brute Force            |
| Rate         | ~30 connections/sec    |

---

## OSINT Findings (Spiderfoot)
| Type                          | Unique | Total |
|-------------------------------|--------|-------|
| Affiliate IP Address          | 15     | 15    |
| Blacklisted IP Address        | 1      | 1     |
| Blacklisted IP on Same Subnet | 264    | 264   |
| Malicious Affiliate IP        | 19     | 19    |
| Malicious IP on Same Subnet   | 264    | 264   |

---

## Analysis
Mass random attacks on open 3306 ports with brute force logins to gain access to databases.

---

## IOCs
- **IP:** 192.109.200.204
- **Port:** 3306
- **Protocol:** TCP
- **BGP AS:** 51396

---

## Conclusion
What you concluded, what was done in response if anything.
