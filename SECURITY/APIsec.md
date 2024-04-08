# API Security

- [Owasp](#vulnerabilities)
- [Real Word Examples](#examples)
- [3 Pillars of APIsec](#pillars)
-

# Vulnerabilites
The OWASP (Open Web Application Security Project) 10 most common API vulnerabilites:  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/3babd851-1455-49e1-934b-ecbcf8d6339d)  

1. Broken Object Level Authorization (BOLA): This occurs when APIs fail to properly check whether the user has access to the requested data or functionality. Attackers can exploit this by manipulating the object identifiers in requests to access unauthorized data.
   This is a pure authorization flaw.  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/4e4a634e-5ebc-448f-84de-9321bb436157)

   
2. Broken Authentication: APIs that have weak authentication mechanisms or improper session management can be vulnerable to attacks such as credential stuffing, session hijacking, and brute force attacks.
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/05846179-db88-4c9a-99ac-e3dbec60fe67)  

3. Broken Object Property Level Authorization: 
   Excessive Data Exposure: This risk arises when APIs expose sensitive information such as PII (Personally Identifiable Information), credentials, or other critical data. Attackers can exploit this by intercepting the data in transit or by accessing it through insufficiently protected endpoints.
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/1d81072e-8182-4dff-973b-3a2e3fe29141)  

4. Unrestired Resource Consuption:  
  Lack of Rate Limiting: APIs that lack rate limiting controls are susceptible to abuse by attackers who can flood the API with requests, leading to denial of service (DoS) or brute force attacks.  
  ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/4c82c730-a48b-4102-be13-d151ca6c933c)  

5. Broken Function Level Authorization: Similar to broken object level authorization, this risk occurs when APIs do not properly check whether the user has the necessary permissions to perform a specific action, allowing unauthorized actions.  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/a51f4bbe-392f-42d9-a0d4-033c94286778)  

6. Unrestricted Access to Sensitive Buisness Flows:  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/e16ef6cf-8cb3-4274-b558-9e211ac9fa52)  

7. Server side Request Forgery:  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/6c78e95f-7707-4792-9359-e56e36c6be55)  
   
8. Security Misconfiguration: Improperly configured APIs can lead to a range of vulnerabilities. This includes using default settings, leaving debug flags on, or exposing sensitive information through error messages.  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/2e605ce6-cafb-4431-95a7-4f2972046710)  

9. Improper Inventory(Assets) Management: This involves not properly tracking and managing API endpoints and their associated documentation. Attackers can exploit outdated or deprecated APIs that are still active.  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/834e8a57-be04-4aaa-a0e2-85ea55f0bce6)  

10. Unsafe Consumption of API's:  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/c26bab72-bdca-4593-a9f1-b0125329e502)  

11. Injection: APIs that accept user input without proper validation and sanitization are vulnerable to injection attacks such as SQL injection, NoSQL injection, and command injection.
12. Improper Inventory(Assets) Management: This involves not properly tracking and managing API endpoints and their associated documentation. Attackers can exploit outdated or deprecated APIs that are still active.
13. Insufficient Logging & Monitoring: Inadequate logging and monitoring make it difficult to detect unauthorized access or abnormal behavior. This can delay incident response and increase the impact of a successful attack.
14. Insecure Serialization: APIs that use insecure serialization methods are vulnerable to attacks such as deserialization of untrusted data, leading to remote code execution.




# Real World examples
Everything starts from sniffing the traffic!
## examples
1. Validation check - Is the source the same?, is the reciever the same?  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/7078116e-6155-41d3-aa62-66b66948b317)  

2. Authenticate - vs Authorice
  You could create an account and check unauthorized details about somebody else

3. No authentication
   Some APIS are left without the need of authentication

4. Creative brute force
   Password reset was limited to 200 req/IP'adress. Rotating every IP can give you full access to a complete brute force schema.

5. UI filter
   A filter was created for the UI but not for the app. You can then ping the server through an API for successfull responses.

6. Broken function leve Authorization
   From a simple account you are able to use CRUD and change database functions.

# Pillars  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/1cb4d6c5-b275-46bc-9f90-0051fb5ea7d1)  

READ: 
https://apistylebook.com/design/guidelines/atlassian-rest-api-design-guidelines-version-1#api-lifecycle
https://developer.atlassian.com/server/framework/atlassian-sdk/atlassian-rest-api-design-guidelines-version-1/

1. Governance  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/901c9375-dc3a-4f30-9b1b-b6a669a301f8)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/421d4083-233a-49bf-8831-a20d4805dcbd)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/8806f11f-ccef-489f-a57f-260984a67a10)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/5062e1a4-05bc-4e75-8507-9a31cb420b57)  

2. Testing  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/ae3948bb-8ece-49e6-8e31-a3b55238f2f1)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/8f5b19e3-6710-4526-b4d2-37d690937cd0)  

3. Monitoring  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/7d0254ad-ca3b-4b79-9c48-6db70b85cbbf)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/0ff800dd-1acf-4a59-95da-b43038167778)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/c5d6053e-3245-4f11-abdb-1b2f93698278)  

![image](https://github.com/Keeriiim/API_DEV/assets/117115289/6c75ae43-d7ff-4dcf-be02-485885e31e23)  

## Best practices  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/3a6ddf28-c343-4f2d-849f-d3cf2f683ea3)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/0ce9cbe1-d091-442b-9c00-94635c5a90b0)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/90f19013-6180-447a-8eca-4331c199a7e7)  










   


