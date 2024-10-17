# Rule Engine Application

## Overview

This application is a rule engine that determines user eligibility based on attributes such as age, department, salary, and experience. It uses an Abstract Syntax Tree (AST) to represent and manage conditional rules, allowing for dynamic rule creation, combination, and evaluation.

## Features

- **Create Rules:** Define rules using a string format that gets converted into an AST.
  
   ![Screenshot 2024-10-17 220711](https://github.com/user-attachments/assets/4e8ebc88-35c0-498e-8ad6-4ea28dfeadd5)
   ![Screenshot 2024-10-17 220743](https://github.com/user-attachments/assets/2864fd92-0a03-492e-a562-62b19223a6db)


- **Combine Rules:** Combine multiple rules into a single AST for more complex evaluations.
  
  
  <img width="376" alt="image" src="https://github.com/user-attachments/assets/63145818-6936-4763-8fbe-db65f264e4ff">

  
- **Evaluate Rules:** Check if the given data meets the criteria defined by the AST.
  
  <img width="375" alt="image" src="https://github.com/user-attachments/assets/041e664f-1711-4bbb-b107-50d5fb7909f4">


- **Tree Visualization:** Define or Combine Rule would should show Tree Representation.

## Tech Stack

- **Backend:** Node.js, Express.js
- **Database:** MongoDB

## Getting Started

### Prerequisites

- Node.js and npm installed
- MongoDB installed and running

### Installation

1. **Clone the Repository**
   ```bash
   git clone "https://github.com/Deep0729/Application_-1-_Rule_-Engine_with_AST.git"
   ```

2. **Install Backend Dependencies**

   ```bash
   npm install
   ```
   
3. **Start MongoDB**

   Ensure that MongoDB is running on your local machine:

   ```bash
   mongod
   ```

4. **Start the Backend Server**

   ```bash
   nodemon server.js
   ```

## API Endpoints

1. **Create a Rule**
   - **Endpoint:** `/api/create_rule`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
       "ruleName": "Rule 1"
     }
     ```
use appropriate spaces in Rules for correct results.

Rule should be in follow format:
variable operator value 

   - **Response:**

     ```json
     {
       "_id": "605c72ef1f4e3a001f4d2e9a",
       "rule_name": "Rule1",
       "rule_ast": { ... }
     }
     ```

2. **Combine Rules**
   - **Endpoint:** `/api/rules/combine_rules`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "ruleIds": ["605c72ef1f4e3a001f4d2e9a", "605c730f1f4e3a001f4d2e9b"]
       "operators: op
     }
     ```
   - **Response:**

     ```json
     {
       "type": "operator",
       "value": operator,
       "left": { ... },
       "right": { ... }
     }
     ```

3. **Evaluate a Rule**
   - **Endpoint:** `/api/rules/evaluate_rule`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "rule": { ... },
       "data": {
         "age": 35,
         "department": "Sales",
         "salary": 60000,
         "experience": 3
       }
     }
     ```
   - **Response:**

     ```json
     {
       "result": true
     }
     ```

## Running Tests

You can add and run tests to ensure everything is working correctly. 
```
created bt: santosh sahoo
