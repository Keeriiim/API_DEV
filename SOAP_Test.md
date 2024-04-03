# SOAP
SOAP (Simple Object Access Protocol):
SOAP is a protocol for exchanging structured information in the implementation of web services. It is based on XML (eXtensible Markup Language) and was one of the first standardized protocols for web services.

Characteristics of SOAP:
Message Format: SOAP messages are formatted using XML. They are typically defined by a WSDL (Web Services Description Language) file, which describes the structure of the request and response messages.

Transport Protocol: SOAP can be used with various transport protocols such as HTTP, SMTP, or JMS. It is flexible in terms of transport.

Stateful Interaction: SOAP is often used in scenarios where stateful interactions are required. It supports transactions, security, and reliable messaging.

Error Handling: SOAP has built-in error handling through standardized fault elements in its messages.

Complex Operations: It is well-suited for scenarios where complex operations or transactions need to be performed.

Tool Support: SOAP has extensive tool support, and frameworks such as Apache CXF, Apache Axis, and JAX-WS are commonly used for implementing SOAP-based services.

Example SOAP Message:
Here is an example of a SOAP message:

- [Setup](#setup)
- [Project](#project)


# Setup
Go to [SoapUI](#https://www.soapui.org/downloads/soapui/) and download the program for SOAP testing
Also download chrome extention [Wizdler](#https://chromewebstore.google.com/detail/wizdler/oebpmncolmhiapingjaagmapififiakb?pli=1)



# Project
## 1. Create Soap project using WSDL
You can open the .xml file or browse  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/81cefc31-6bc2-4f23-9aa9-e529608fdc94)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/48871dca-c6ba-4a4e-9251-cca4ecb4baae)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/ad169bfb-60ac-4091-878b-026f259a84d6)  


The extention shows me for the wsdl URL  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/6d9af950-ea15-4721-9939-d474a00d49fd)

## 2. Create test suite & Test cases  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/25f3f37c-31ff-4cae-9825-08780bba8d11)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/7eee7dae-d71b-4c01-98d5-8c288a887094)

? means place input  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/42b113fa-8400-4b33-942e-363ab6a54f00)  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/eb03c88c-71a8-4804-9d91-bcfa2c31b100)



## 3. Added contains assertion  
+ symbol to add assertions
Select contains and press on add
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/6cf6eaae-473b-469e-a561-5a3a5ff59d01)
Write the expectation  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/1d5d40d4-9851-4041-96ab-2f3d4ed30240)



## 4. Execute tests in sequence & parallel  
Sequance and paralell 
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/dd26abb8-a15e-40f7-ac4f-78d71e90a8a6)  

Individual testing  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/8678ba86-96c8-428b-9a14-ee777403ba19)  

Group testing  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/2d2c5ba0-211b-4607-8240-aad734cca84f)  

## 5. Documentation
Generate Docs  
![image](https://github.com/Keeriiim/API_DEV/assets/117115289/b41e42a3-8ce5-43fb-9ee0-44434d6f35db)
