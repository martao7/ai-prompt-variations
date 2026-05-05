# Date Input Validation – Test Plan

## Overview
This document describes a structured test plan for validating a date input form consisting of three fields:

- **Day (DD)**
- **Month (MM)**
- **Year (YYYY)**

The test plan is based on **equivalence class testing** and contains **exactly 11 test cases**, covering both **positive** and **negative** scenarios.

---

## Rules and Constraints

### Day (DD)
- Valid: **1–28** (for all months)
- **29**: valid only for **February in leap years**
- **30**: invalid for February
- **31**: valid only for long months (**1, 3, 5, 7, 8, 10, 12**)
- Invalid: **0**, **>31**

### Month (MM)
- Long months: **1, 3, 5, 7, 8, 10, 12**
- Short months: **4, 6, 9, 11**
- February: **2**
- Invalid: **0**, **>12**

### Year (YYYY)
- Leap year rule (simplified): **year divisible by 4**
- Both leap years and non-leap years must be considered

---

## Test Cases

### Positive Test Cases

| Test Case ID | Description | Input (DD/MM/YYYY) | Expected Result |
|-------------|------------|--------------------|----------------|
| TC-01 | Valid standard date | 15/03/2023 | Valid |
| TC-02 | Valid date in short month | 30/04/2023 | Valid |
| TC-03 | February 29 in leap year | 29/02/2024 | Valid |
| TC-04 | Day 31 in a long month | 31/01/2023 | Valid |
| TC-05 | Minimum valid day | 01/12/2023 | Valid |

---

### Negative Test Cases

| Test Case ID | Description | Input (DD/MM/YYYY) | Expected Result |
|-------------|------------|--------------------|----------------|
| TC-06 | February 29 in non-leap year | 29/02/2023 | Invalid |
| TC-07 | Day 31 in short month | 31/04/2023 | Invalid |
| TC-08 | Day greater than 31 | 32/01/2023 | Invalid |
| TC-09 | Day equals zero | 00/05/2023 | Invalid |
| TC-10 | Month greater than 12 | 10/13/2023 | Invalid |
| TC-11 | Month equals zero | 15/00/2023 | Invalid |

---

## Summary

- Total test cases: **11**
- Positive test cases: **5**
- Negative test cases: **6**

This test plan ensures complete coverage of critical equivalence classes, including leap year validation, invalid ranges, and boundary conditions.
