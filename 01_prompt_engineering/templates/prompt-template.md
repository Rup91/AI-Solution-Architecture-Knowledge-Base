# Prompt Template

## Overview

This template provides a standardized structure for designing reliable, reusable, and production-ready prompts in enterprise environments.

Use this template to ensure:

    - Consistency across prompts
    - Clear objectives and constraints
    - Predictable output quality
    - Easier maintenance and reuse
    - Governance and audit readiness

## i. Prompt Name

Provide a clear and descriptive name.

Example:

    Customer Data Retrieval Prompt

## ii. Prompt Description

Briefly describe what this prompt does.

Example:

    This prompt retrieves customer information from enterprise systems and returns structured data in JSON format.

## iii. Business Use Case

Describe the real-world scenario where this prompt will be used.

Example:

    Used in customer support systems to retrieve customer account details based on customer ID.

## iv. Role

Define the role of the AI system.

Example:

    You are a senior backend engineer responsible for building secure and scalable APIs in an enterprise environment.

## v. Objective

Clearly define the expected outcome.

Example:

    Generate a production-ready API response based on the provided customer ID.

## vi. Context

Provide background information required to perform the task.

Example:
    
    The system uses Spring Boot and connects to enterprise databases. All responses must follow organizational security and logging standards.

## vii. Input

Define the input data format.

Example:
```json
    {  
        "customerId": "12345"
    }
```

## viii. Task

Describe the exact task the model must perform.

Example:

    Retrieve customer details using the provided customer ID and return the information in structured JSON format.

## ix. Instructions

Provide step-by-step instructions.

Example:

    i. Validate the input
    ii. Retrieve customer data
    iii. Handle missing records
    iv. Format the response
    v. Log the operation

## x. Constraints

Define rules and limitations.

Example:

    - Follow organizational coding standards
    - Validate all inputs
    - Do not expose sensitive data
    - Ensure secure implementation
    - Handle errors gracefully
    - Maintain performance efficiency

## xi. Output Format

Specify the required output format.

Example: JSON

## xii. Expected Output

Provide an example output.

Example:
```json
        {  
            "status": "SUCCESS",  
            "customerName": "John Doe",  
            "accountStatus": "Active"
        }
```
## xiii. Error Handling

Define how errors should be handled.

Example:

    Return a structured error response if the customer is not found.

## xiv. Security Requirements

Define security expectations.

Example:
    
    - Validate authentication tokens
    - Mask sensitive information
    - Prevent unauthorized access

## xv. Logging Requirements

Define logging expectations.

Example:

    - Log request timestamp
    - Log operation status
    - Log error details if any

## xvi. Performance Requirements

Define performance expectations.

Example:

    - Response time must be under 2 seconds
    - Support concurrent requests

## xvii. Validation Rules

Define quality checks.

Example:
    
    - No missing required fields
    - Correct data format
    - Accurate results

## xviii. Dependencies

List required systems or tools.

Example:

    - Database service
    - Authentication service
    - Logging service

## xix. Version

Specify prompt version.

Example:
    
    v1.0

## xx. Owner

Specify responsible person or team.

Example:

    AI Engineering Team

## xxi. Review 

Specify the next review date.

Example:

    01-Jan-2026

## xxii. Status

Specify current status.

Example:

    Draft / Approved / Deprecated
