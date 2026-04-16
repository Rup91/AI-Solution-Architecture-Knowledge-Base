# Prompt Engineering Use Cases

This document describes real-world enterprise use cases where prompt engineering is applied to solve business problems.

Each use case includes:

    - Business scenario
    - Objective
    - Input
    - Prompt
    - Output
    - Benefits

## USE CASE 4: Automated Mainframe Record Retrieval API Development Using Organizational Standards

### Business Scenario

An enterprise backend system built on Spring Boot already exists and is running in production.

The organization relies on a legacy mainframe system that stores critical customer and policy records.  

Modern applications need to retrieve these records using unique identifiers such as:

    - ITV Number (Transaction Identifier)
    - CSI Number (Customer Identifier)
    - Dossier Number (Case or Record Identifier)

To maintain consistency, security, and compliance, the organization defines strict development standards documented in internal technical documentation.

Developers must follow these standards when creating new APIs.

To accelerate delivery and reduce manual effort, developers use AI-assisted tools (such as Copilot or Claude) to generate implementation-ready code directly inside the existing Spring Boot project.

### Objective

Design and implement a production-ready POST API within an existing Spring Boot microservice that retrieves records from a mainframe system using a unique identifier.

The generated API must:

    - Integrate into the existing application
    - Follow organizational development standards
    - Validate identifier and peer token
    - Retrieve records from mainframe
    - Transform response data- Implement logging and monitoring
    - Enforce rate limiting and security
    - Be ready for deployment

### Internal Documentation Source

The developer downloads relevant internal documentation from the organization's internal portal and stores the documents inside the project directory.

Example:

    project-root/
    |_ docs/
        |_ api-standards.pdf
        |_ security-guidelines.pdf
        |_ logging-rules.pdf
        |_ rate-limiting-policy.pdf
        |_ certificate-configuration.pdf
         
These documents define how APIs must be implemented and secured.

The AI assistant reads these documents and follows organizational standards when generating code.


### Input

The developer provides:

    - Existing Spring Boot project
    - API requirement
    - Identifier type (ITV / CSI / Dossier)
    - Internal documentation (PDF files)
    - Integration specifications
    - Security policies
    - Deployment requirements

### Example Requirement

Create a POST API to retrieve customer records from the mainframe system using a Dossier Number.

Business Rules:

    - Validate identifier format
    - Validate peer token
    - Authenticate request
    - Retrieve matching records from mainframe
    - Transform response data
    - Log request and response
    - Handle errors gracefully
    - Enforce rate limiting
    - Ensure secure communication

## Previous Project Structure (Existing Code)

The backend application already contains an existing Spring Boot microservice.

Example structure:

    - src/main/java/com/example/application/
        |_ controller/
           |_ HealthController.java
        |_service/
            |_ CustomerService.java
        |_ repository/
            |_ CustomerRepository.java
        |_ model/
            |_ Customer.java
        |_ config/
            |_ SecurityConfig.java
            |_ LoggingConfig.java  
        |_ integration/
            |_ MainframeClient.java
        |_ exception/
            |_ GlobalExceptionHandler.java
        |_ resources/
            |_ application.yml
            |_ logback.xml  

## New Project Structure (After Adding New API)

After generating the new POST API, additional files and configuration components are added to the existing project.
Updated structure:

- src/main/java/com/example/application/
        |_ controller/
           |_ HealthController.java
           |_ RecordRetrievalController.java <-- New File added
        |_service/
            |_ CustomerService.java
            |_ RecordRetrievalService.java <-- New file added
        |_ repository/
            |_ CustomerRepository.java
        |_ dto/
            |_ RecordRequestDTO.java
            |_ RecordResponseDTO.java
        |_ integration/
            |_ MainframeClient.java
            |_ RecordIntegrationClient.java
        |_ model/
            |_ Customer.java
        |_ config/
            |_ SecurityConfig.java
            |_ LoggingConfig.java
            |_ RateLimitConfig.java
        |_ exception/
            |_ GlobalExceptionHandler.java
            |_ RecordExceptionHandler.java
        |_ resources/
            |_ application.yml
            |_ logback.xml  


## Prompt to Run Inside Existing Spring Boot Project

### Prompt

You are a senior backend engineer working on an existing Spring Boot microservice application.

Your task is to add a new POST API to retrieve records from a mainframe system using a unique identifier.

Carefully analyze:
    - Existing project structure
    - Internal documentation stored in the project folder
    - Business requirements
    - Security and deployment standards

Generate implementation-ready code that integrates seamlessly into the current codebase.

Follow organizational standards and ensure production readiness.

### Perform the Following Tasks

    1. Create REST controller for the API
    2. Create service class for business logic
    3. Create request and response DTO models
    4. Implement mainframe integration logic
    5. Validate identifier format
    6. Validate peer token authentication
    7. Implement request validation
    8. Implement response verification
    9. Configure structured logging
    10. Implement centralized exception handling
    11. Configure rate limiting
    12. Configure secure communication settings
    13. Ensure load balancer compatibility
    14. Add required dependencies if missing
    15. Follow existing naming conventions
    16. Generate production-ready code

### API Specification

API Name:

    Retrieve Mainframe Record

HTTP Method:
    POST

Endpoint:
    /api/records/retrieve

### Request Payload

```json
    {  
        "identifierType": "DOSSIER",
        "identifierValue": "D123456789"
    }
```

### Expected ResponseJSON

```json
    {  
        "status": "SUCCESS",  
        "data": {    
                "customerName": "John Doe",    
                "policyNumber": "POL123456",    
                "policyStatus": "Active",    
                "lastUpdated": "2025-03-10"  
        }
    }
```
## Security and Validation Requirements

Ensure the API implementation includes:

    - Peer token validation
    - Authentication verification
    - Request payload validation
    - Response integrity verification
    - Secure error handling
    - Audit logging

## Infrastructure and Deployment Readiness

Ensure the API supports:

    - Logging and monitoring integration
    - Rate limiting configuration
    - Certificate-based secure communication
    - Health check readiness
    - Load-balanced deployment
    - CI/CD compatibility

## Summary of Changes Introduced by the New API

The following components are added to the existing system:

    - New REST controller
    - New service layer
    - DTO models
    - Mainframe integration client
    - Validation and security logic
    - Logging and monitoring configuration
    - Rate limiting configuration
All changes follow organizational standards and integrate safely into the existing application.

## Benefits

    - Faster API development
    - Reduced manual coding effort
    - Standardized implementation
    - Improved system reliability
    - Secure access to mainframe data
    - Production-ready deployment