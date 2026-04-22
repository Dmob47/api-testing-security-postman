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
- Validated behavior for valid and invalid login attempts
- Verified token generation and response structure

### Security Testing
- SQL Injection attempts
- Script and HTML injection
- Parameter tampering (userId, quantity, price)
- Large payload handling

### Workflow Testing
- Implemented request chaining using environment variables
- Simulated flows such as Create → Fetch → Delete

### Performance Checks
- Basic response time validation
- Consistency checks across multiple requests

---

## Key Findings

- API accepts invalid data types without proper validation  
- Missing fields are not consistently validated  
- Weak error handling observed in some endpoints  
- No strict validation for edge-case inputs  
- Authentication returns token only for valid credentials  
- Successful login returns HTTP 201 instead of standard 200  
- Login endpoint deviates from REST conventions by returning 201  
- No major latency spikes observed during testing  
- Performance is stable under basic testing conditions  
- No rate limiting observed across endpoints  

---

## Tools Used

- Postman  
- JavaScript (Postman test scripts)  

---

## Limitations

- FakeStore API does not fully persist created data  
- Some validations cannot be confirmed due to mock behavior  

---

## Outcome

This project demonstrates the ability to:

- Test APIs beyond basic functionality  
- Identify validation gaps and inconsistent behavior  
- Analyze API responses under edge and manipulated conditions  
- Understand practical limitations of API testing tools and environments  

---

## Future Improvements

- Integrate automated execution using Newman  
- Perform load testing using tools such as k6 or JMeter  
- Expand testing using OWASP API Security Top 10 scenarios  
