# Rule Engine Application

## Overview

This application is a rule engine that determines user eligibility based on attributes such as age, department, salary, and experience. It uses an Abstract Syntax Tree (AST) to represent and manage conditional rules, allowing for dynamic rule creation, combination, and evaluation.

## Features

- **Create Rules:** Define rules using a string format that gets converted into an AST.
  
   ![Screenshot 2024-10-17 220711](https://github.com/user-attachments/assets/4e8ebc88-35c0-498e-8ad6-4ea28dfeadd5)
  
   ![Screenshot 2024-10-17 220743](https://github.com/user-attachments/assets/2864fd92-0a03-492e-a562-62b19223a6db)


- **Combine Rules:** Combine multiple rules into a single AST for more complex evaluations.
  
  ![Screenshot 2024-10-17 220829](https://github.com/user-attachments/assets/4c509f4f-bbbf-4fa4-8144-78279107c76d)

  ![Screenshot 2024-10-17 220847](https://github.com/user-attachments/assets/cc9b839e-3540-43c6-b02a-619a9028c1ca)

  
- **Evaluate Rules:** Check if the given data meets the criteria defined by the AST.

  ![Screenshot 2024-10-17 220927](https://github.com/user-attachments/assets/01f90378-8dad-4acb-ab31-d3c6b3008ecb)

  ![Screenshot 2024-10-17 220943](https://github.com/user-attachments/assets/f4971391-1d8d-419a-949f-09c8545f6a90)


- **Tree Visualization:** Define or Combine Rule would should show Tree Representation.

## Tech Stack

- **Backend:** Using Node.js, Express.js
- **Database:** Using MongoDB

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
   npm start
   ```
   **then click the localhost link in the terminal:**
   ```bash
   http://localhost:3000
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
     {
       "ruleString": "((age > 30 AND department = 'Marketing')) AND (salary > 20000 OR experience > 5)"
       "ruleName": "Rule 2"
     }
     ```
use appropriate spaces in Rules for correct results.

Rule should be in follow format:
variable operator value 

   - **Response:**

     ```json
     {
       "_id": "67113d109425f27c63a82b5c",
       "rule_name": "Rule1",
       "rule_ast": { ... }
     }
     {
       "_id": "67113d4d9425f27c63a82b5e",
       "rule_name": "Rule2",
       "rule_ast": { ... }
     }
     ```

2. **Combine Rules**
   - **Endpoint:** `/api/rules/combine_rules`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "ruleIds": ["67113d639425f27c63a82b61", "67113d8a9425f27c63a82b64"]
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
created bt: Deep Dutta
```
## THANK YOU
