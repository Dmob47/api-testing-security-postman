# API Test Cases — FakeStore API

## 1. Invalid Data Type in Product Creation

- Endpoint: POST /products  
- Scenario: Send incorrect data types (e.g., price as string)  
- Expected: API should reject invalid data types  
- Actual: API accepts invalid data types  
- Result: FAIL  

---

## 2. Missing Required Fields

- Endpoint: POST /products  
- Scenario: Send request with missing fields  
- Expected: API should return validation error  
- Actual: Missing fields not properly validated  
- Result: FAIL  

---

## 3. Negative Price Input

- Endpoint: POST /products  
- Scenario: Send negative value for price  
- Expected: API should reject negative values  
- Actual: API accepts negative values  
- Result: FAIL  

---

## 4. Negative Quantity in Cart

- Endpoint: POST /carts  
- Scenario: Send negative quantity  
- Expected: Quantity should be greater than or equal to 1  
- Actual: Negative quantity accepted  
- Result: FAIL  

---

## 5. Invalid Product ID

- Endpoint: GET /products/{id}  
- Scenario: Use invalid or non-existent ID  
- Expected: API should return error response  
- Actual: Inconsistent error handling observed  
- Result: FAIL  

---

## 6. Login with Valid Credentials

- Endpoint: POST /auth/login  
- Scenario: Provide correct username and password  
- Expected: Status code 200 and token returned  
- Actual: Token returned with status code 201  
- Result: PASS (Functional), FAIL (Standards Compliance)  

---

## 7. Login with Invalid Credentials

- Endpoint: POST /auth/login  
- Scenario: Provide incorrect credentials  
- Expected: Authentication should fail  
- Actual: API correctly rejects invalid login  
- Result: PASS  

---

## 8. Parameter Tampering — userId

- Endpoint: POST /carts  
- Scenario: Modify userId to unauthorized value  
- Expected: API should validate ownership  
- Actual: API accepts tampered userId  
- Result: FAIL  

---

## 9. Large Payload Handling

- Endpoint: POST /products  
- Scenario: Send very large input string  
- Expected: API should handle or reject large payload  
- Actual: API accepts input without restriction  
- Result: FAIL  

---

## 10. Performance Stability

- Endpoint: Multiple  
- Scenario: Execute repeated requests  
- Expected: Consistent response times  
- Actual: No major latency spikes observed  
- Result: PASS  
