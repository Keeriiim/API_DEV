# API Security
- Resources:
  [Owasp cheat sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)
  [CWE](https://cwe.mitre.org/documents/cwe_usage/guidance.html)  
  [Automated Threats](https://owasp.org/www-project-automated-threats-to-web-applications/)
  [Injection Flaws](https://owasp.org/www-community/Injection_Flaws)  
  
- [Vulnerabilites](#vulnerabilities)
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
  Every API request has techincal & financial cost. Lack of rate increases risk of: denial of service, unnecessary cost, degradation of service to users.
  ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/4c82c730-a48b-4102-be13-d151ca6c933c)  
  ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/c6090380-a9e4-4130-a5db-e05d4b4727ec)


5. Broken Function Level Authorization (BAFLA): Similar to broken object level authorization, this risk occurs when APIs do not properly check whether the user has the necessary permissions to perform a specific action, allowing unauthorized actions.  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/a51f4bbe-392f-42d9-a0d4-033c94286778)  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/ddec7069-6a23-4387-b5f7-d830bbe7a5ae)
  

6. Unrestricted Access to Sensitive Buisness Flows:  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/e16ef6cf-8cb3-4274-b558-9e211ac9fa52)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/db0c14bf-4509-4a96-ae72-aadb32cf9823)  


7. Server side Request Forgery:
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/a45aff15-147e-472a-9726-852fc8a76d8d)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/6c78e95f-7707-4792-9359-e56e36c6be55)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/b1f75f0b-3af7-483d-ae3e-e4076086fddb)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/3c7148b0-5dd0-4ae6-9460-4d0dc13e8308)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/db645695-84fa-44f9-a65e-76762d1d5a7d)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/8064fc80-fe57-4079-980b-7ce28730a7e7)


  
   
9. Security Misconfiguration: Improperly configured APIs can lead to a range of vulnerabilities. This includes using default settings, leaving debug flags on, or exposing sensitive information through error messages.  
   Automated scanners: Burp Suite, Nessus, Qualys, OWASP ZAP, and Nikto will automatically check responses from the web server to determine version information, headers, cookies, transit encryption configuration, and parameters to see if expected security measures are missing.  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/2e605ce6-cafb-4431-95a7-4f2972046710)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/ce48d686-7f14-4638-ad93-fb01318f3f31)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/f3b4d2a3-95ca-4861-980d-5697bac1d82c)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/fae1ecc1-4b29-43ce-b210-01bd0ab5cf43)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/d69d55cf-8433-4f9f-b77f-1ddb56f3286e)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/8f418ef1-474a-4133-9021-30042e379b07)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/cb53cf5f-379f-4799-8c5e-cf19eecd816a)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/f4979444-e05b-4408-96ea-fdd0bf9211e3)  


  

10. Improper Inventory(Assets) Management: This involves not properly tracking and managing API endpoints and their associated documentation. Attackers can exploit outdated or deprecated APIs that are still active.  
```bash
Outdated documentation makes it more difficult to find and/or fix vulnerabilities. Lack of assets inventory and retirement strategies leads to running unpatched systems, resulting in leakage of sensitive data. It's common to find unnecessarily exposed API hosts because of modern concepts like microservices, which make applications easy to deploy and independent (e.g. cloud computing, K8S). Simple Google Dorking, DNS enumeration, or using specialized search engines for various types of servers (webcams, routers, servers, etc.) connected to the internet will be enough to discover targets.  
Attackers can gain access to sensitive data, or even take over the server. Sometimes different API versions/deployments are connected to the same database with real data. Threat agents may exploit deprecated endpoints available in old API versions to get access to administrative functions or exploit known vulnerabilities.
```
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/834e8a57-be04-4aaa-a0e2-85ea55f0bce6)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/64a3829a-ca1a-41ca-9e17-7a1ec65095fb)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/0ca306ec-a2d9-42ba-8c05-f3fa5b21b22b)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/bd68fea2-4e43-4eba-ad48-579f2e0c096a)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/b5386121-9008-4f36-991a-bc4a0d846248)  
   ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/21444b66-c954-4332-b7fa-c5215be8b94c)




10. Unsafe Consumption of API's:
    ```bash
    Developers tend to trust and not verify the endpoints that interact with external or third-party APIs, relying on weaker security requirements such as those regarding transport security, authentication/authorization, and input validation and     sanitization. Attackers need to identify services the target API integrates with (data sources) and, eventually, compromise them.
    ```
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/c26bab72-bdca-4593-a9f1-b0125329e502)  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/3520c7d4-dc11-44cc-aa3a-e9c97c1b8650)  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/2eb55f7b-7485-4d2a-9fe0-6fcf1dc70585)


    

11. Injection: APIs that accept user input without proper validation and sanitization are vulnerable to injection attacks such as SQL injection, NoSQL injection, and command injection.  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/dfb1f909-a3a6-482a-bb29-103b9b857d0f)

12. Insufficient Logging & Monitoring: Inadequate logging and monitoring make it difficult to detect unauthorized access or abnormal behavior. This can delay incident response and increase the impact of a successful attack.  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/0b870fad-3077-4d18-abb1-8e4440aa9e9d)

13. Insecure Serialization: APIs that use insecure serialization methods are vulnerable to attacks such as deserialization of untrusted data, leading to remote code execution.
14. Buisness logic flaws:  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/c27fb2f9-bb99-42c3-8e0e-92ac2a11500f)  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/aa9a5b41-ff24-491b-b1a9-6b1e1a9f9c8c)  
    ![image](https://github.com/Keeriiim/API_DEV/assets/117115289/5e7d8c69-d300-4352-81c7-f1cc630d77ba)




# Extras:
## BOLA  

1. Weak Password Policy
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/b63183ce-64e2-44bf-9017-c91a420f42c3)

2.Credential sniffing  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/a3660c72-224d-4d21-aa24-cea4beab595e)  

3. Predictable tokens  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/5d12988b-6186-41cf-b31a-089261615a80)  

4. Misconfigured JWT
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/27107e7a-c26f-4d5a-946b-23251993b672)

5. Generall API problems  
   "The future of digital systems is complexity and complexity is the worst enemy of security"  
   REST APIs are designed to be stateless, therefor the api provider doesnt remember one request from another. Therefor tokens are created  

![image](https://github.com/Keeriiim/API_DEV/assets/117115289/e9a41986-6017-4b42-9534-c4241adea403)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/574393a8-2875-42c6-9a18-ae29d0c59fd1)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/e6db24fd-a3c4-47f7-818e-2be591ea81f4)  

## BOPLA - Broken Object Property Level Authorization  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/488188ee-66d7-4382-b94b-ffb55777ae2a)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/453ac6eb-b408-4642-81da-ff4700c5d10c)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/8641c9fb-9b8e-4612-a068-9bc36b300e73)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/ae116dd5-5e8c-4ccb-a604-90c805eedd62)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/622fa537-dbac-498e-af1b-ec77ab81e2b9)  

![image](https://github.com/Keeriiim/API_DEV/assets/117115289/558847f8-7f4e-474a-a8f5-518159549cd7)






































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










   


