# REST
REST (Representational State Transfer):
REST is an architectural style for designing networked applications. It is based on the principles of a client-server architecture and the idea of treating resources as representations that can be manipulated using standard operations.

Characteristics of REST:
Resource-Based: REST focuses on resources, which are identified by URIs (Uniform Resource Identifiers). Resources can be any object or entity, such as a user, product, or service.

Stateless: REST is stateless, meaning that each request from a client to the server must contain all the information necessary to understand and fulfill the request. The server does not store any client state.

CRUD Operations: RESTful services typically use standard HTTP methods for CRUD (Create, Read, Update, Delete) operations:

GET: Retrieve a resource.
POST: Create a new resource.
PUT: Update an existing resource.
DELETE: Delete a resource.
Representation: Resources are represented in various formats such as JSON (JavaScript Object Notation) or XML. The client and server can negotiate the representation format using content negotiation.

Uniform Interface: RESTful services have a uniform interface, which simplifies client-server interactions. This includes self-descriptive messages, hypermedia as the engine of application state (HATEOAS), and a separation of concerns between client and server.

Scalability: REST is well-suited for scalable systems due to its stateless nature and cacheability of responses.

- [Node](#node)
- [Tools](#tools)
- [Environment](#environment)
- [Tests](#tests)
- [Authentication](#authentication)
- [File Upload](#file-upload)

## Node
* Node.js is an open-source, cross-platform, JavaScript runtime environment that executes JavaScript code outside a web browser.

## JSON Server
* JSON Server is a full fake REST API with zero coding in less than 30 seconds.

### Installation - Using Chocolatey in powershell

```bash
choco install nodejs # Install Node.js in powershell
npm install -g json-server # Install JSON Server in CMD
json-server students.json # Run JSON Server with the local file students.json
```

# Postman
Get - http://localhost:3000  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/9f80e97a-059c-4093-b24f-2c626c0ccc11)


Get - http://localhost:3000/students  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/3e81fffb-70df-4464-af65-09d20e88aa5d)



# Tools
https://jsonpathfinder.com/ # JSON Pathfinder

https://jsonpath.com/ # JSON Path

# Environment
## Global variable
You can create a global variable in Postman by clicking on the eye icon in the top right corner of the Postman window.
There you create the name of the global variable and set the value to an adress

```bash
{
   GET {{[global_name]}}/api/v1 # Example
}
```

![image](https://github.com/Keeriiim/API_DEV/assets/117115289/b64d99dd-27f5-4150-8bf2-39e6ec1b4e4f)


## Collection variable 
Accessable only in the specified collection

```bash
{
    GET {{[collection_name]}}/api/v1 # Example
}
```

![image](https://github.com/Keeriiim/API_DEV/assets/117115289/9bae7092-166c-4292-949a-84cf3433e678)


## Environment variable
Accessable in all collections but only in the specified environment

```bash
{
    GET {{[env_name]}}/api/v1 # Example, in this case env_name is localhost
}
```

![image](https://github.com/Keeriiim/API_DEV/assets/117115289/a3fc0d80-da8b-41a7-8892-ca820d07c7f5)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/79e21d38-8f9e-4df8-917c-918587ffc95a)



## Local variable
Accessable only within request

```bash
{
    // Set local variable for a specific endpoint
      pm.variables.set("test","/api/users?page=2")
}
```
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/508c0ed9-7bb8-4cb1-a5d0-bfafc9484082)


## PreScript
By prerunnnig this script you dont need to save variables using the GUI, they will be stored from the script.
To delete, use .unset
```bash
{
    // Set local variable for a specific endpoint
       pm.variables.set("test","/api/users?page=2")

   // Set global variable for a specific endpoint
      pm.globals.set("global","/api/users?page=2")

   // Set environmental variable for a specific endpoint
      pm.environment.set("env","/api/users?page=2")

   // Set collection variable for a specific endpoint
      pm.collectionVariables.set("env","/api/users?page=2")
}
```
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/7eab9885-8911-4adb-97ca-30f5e5ec1367)












# Tests
## Status codes
```bash
{
    pm.test("Status code is 200", () => {
        pm.response.to.have.status(200);
    })

    pm.test("Successful Get request", () => {
        pm.expect(pm.response.code).to.be.oneOf([200,201]);
    })

    pm.test("Status code name has a String", () => {
        pm.response.to.have.status("Created");
    })
}
```

![image](https://github.com/Keeriiim/API_DEV/assets/117115289/a11d3e9d-16c2-4f2d-ab6b-34224787db10)
 

## Headers
```bash
{
    pm.test("Content-Type header is present", () => {
        pm.response.to.have.header("Content-Type");
    })

    pm.test("Content-Type header is application/json", () => {
        pm.expect(pm.response.headers.get("Content-Type")).to.eql("application/json");
    })

}
```

## Cookies
```bash
{
    pm.test("Cookie 'language' is present", () => {
        pm.expect(pm.cookies.has("language")).to.be.true;
    })

    pm.test("Cookie language a value 1", () => {
        pm.expect(pm.cookies.get("language")).to.eql("en-gb");
    })

    pm.test("Cookie has a specific value", () => {
        pm.expect(pm.cookies.get("cookie_name")).to.eql("cookie_value");
    })

}
```

## Response time
```bash
{
    pm.test("Response time is less than 200ms", () => {
        pm.expect(pm.response.responseTime).to.be.below(200);
    })
}
```

## Response body
```bash
{
    pm.test("Test data type of the response", () => {
        const jsonData = pm.response.json();
        pm.expect(jsonData).to.be.an("object");
        pm.expect(jsonData.name).to.be.a("string");
        pm.expect(jsonData.id).to.be.a("number");
        pm.expect(jsonData.curses).to.be.an("array")
    })
}
```

## Response body - Array
```bash
{
    pm.test("Test data type of the response", () => {
        const jsonData = pm.response.json();
        pm.expect(jsonData).to.be.an("array");
        pm.expect(jsonData.courses).to.include("Java")
        pm.expect(jsonData.courses).to.have.members(["Java", "Python", "C++"])
    })
}
```

# Authentication
## Basic auth - non encrypted login
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/92a244d2-6cb8-4324-989a-6b65dba8c629)

## Digest auth - encrypted login (MD5)
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/62631c55-df12-4bdb-9224-468ddefaab1f)

Collection - Variables
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/28175cfe-2623-4b21-98ab-f1d8822d197d)

## Oauth - 3rd party authentication
oauth1 - just some info
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/4f18a5eb-aa56-41d5-9d40-bb2f5018f456)
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/6c5957ee-9476-4de1-a9d6-ac22ae75665d)


Collection - Variables
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/3f0e42bf-cef8-42f4-8d3d-392816743cba)


oauth2

Collection - Variables
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/3f64d2bb-2f79-492d-8b14-f18cd35b83bd)




## Bearer Token / JWT 
You can add a token for all runs.
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/89047399-758f-497e-a4a0-20cb825589c9)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/dfb6461f-5eb9-444a-bc59-9bdf48a26ea3)  

## 

# File upload
convertcsv.com/
## CSV
Iterations - Specify how many rows you want to loop through
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/1838461d-d176-40b6-829c-a6725833fcc6)

IMPORTANT! - Postman has a default comma separator !
If you don't have comma separator (delimiter) as standard. Your textfile in the preview will not look like this. 
```bash
BookID,CustomerName
1,k
2,e
3,r
4,i
5,m
```
1. Easy way to fix is to open the .csv file in a text editor and exchange the ; to ,
2. If working with big data, import the file using "from" in excell, then in the wizard change delimiter to comma
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/1d87ae0e-8f24-4f33-93bd-2f89b9378f0b)
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/96f3e37e-c919-45a9-b2da-aeba8f925bf2)

## From form-data
Important!
Your endpoint has to know how to handle the file in order for it to store it.
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/59770739-42f6-4ae5-b29d-8a4a86718df7)






