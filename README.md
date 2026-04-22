# API Testing & Security Validation — FakeStore API

## Overview

This project demonstrates API testing using Postman with a focus on functional validation, negative testing, and security assessment. The objective was to evaluate API behavior beyond standard use cases and identify weaknesses in validation, authentication, and error handling.

---

## Objective

To analyze how APIs behave under normal, invalid, and manipulated inputs, and to identify gaps in validation, response handling, and basic security practices.

---

## Scope

Tested endpoints include:

- Products  
- Users  
- Carts  
- Authentication  

---

## Testing Approach

- Designed structured test scenarios across functional, validation, negative, and security layers  
- Used Postman test scripts to automate response validation  
- Applied parameter tampering and input manipulation to evaluate system behavior  
- Performed request chaining to simulate real-world API workflows  
- Analyzed API responses to identify inconsistencies and validation gaps  

---

## Testing Coverage

### Functional Testing
- Verified core API operations across all major endpoints  
- Validated expected responses for standard use cases  

### Validation & Schema Testing
- Checked response structure and required fields  
- Verified data types and consistency across responses  

### Negative & Edge Case Testing
- Tested invalid inputs (IDs, missing fields, incorrect data types)  
- Evaluated boundary conditions and edge scenarios  

### Authentication Testing
- Validated login behavior for valid and invalid credentials  
- Verified token generation and response structure  

### Security Testing
- SQL Injection attempts  
- Script and HTML injection  
- Parameter tampering (userId, quantity, price)  
- Large payload handling  

### Workflow Testing
- Implemented request chaining using environment variables  
- Simulated flows such as Create → Fetch → Delete  
- Validated data flow between dependent API calls  

### Performance Checks
- Performed basic response time validation  
- Observed consistency across multiple API requests  

---

## Key Findings

- API lacks strict input validation, allowing invalid data types to be accepted  
- Missing required fields are not consistently validated across endpoints  
- Error handling is inconsistent and does not provide standardized responses  
- API accepts edge-case inputs (negative values, malformed data) without rejection  
- Authentication endpoint deviates from REST standards by returning HTTP 201 instead of 200  
- No validation for tampered parameters such as userId, indicating potential authorization risks  
- No rate limiting observed, making endpoints potentially vulnerable to abuse  
- Performance remained stable under basic testing, with no major latency spikes observed  

---

## Security Observations

- Lack of input validation increases risk of injection-based attacks  
- Absence of parameter validation may allow unauthorized data manipulation  
- Inconsistent validation logic across endpoints weakens API reliability  

---

## Tools Used

- Postman  
- JavaScript (Postman test scripts)  

---

## Limitations

- FakeStore API is a mock API and does not fully persist created data  
- Some validations could not be fully verified due to API limitations  

---

## Outcome

This project demonstrates the ability to:

- Test APIs beyond basic functionality  
- Identify validation gaps and inconsistent behavior  
- Analyze API responses under edge and manipulated conditions  
- Apply a security-focused approach to API testing  

---

## Future Improvements

- Automate execution using Newman  
- Perform load testing using tools such as k6 or JMeter  
- Expand testing using OWASP API Security Top 10 scenarios  
