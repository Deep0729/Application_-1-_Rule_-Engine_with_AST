# Rule Engine Application with AST

## Hosted Link: https://application1-rule-engine-with-ast.onrender.com

## Overview

This application is a rule engine that determines user eligibility based on attributes such as age, department, salary, and experience. It uses an Abstract Syntax Tree (AST) to represent and manage conditional rules, allowing for dynamic rule creation, combination, and evaluation.

## Features

- **Create Rules:** Define rules using a string format that gets converted into an AST.
  
   ![Screenshot 2024-10-22 130251](https://github.com/user-attachments/assets/7693be71-1b6e-4f90-bd7b-6161fe5a324d)

   ![Screenshot 2024-10-22 130322](https://github.com/user-attachments/assets/4174797d-719e-469c-8c39-2b157282d207)


- **Combine Rules:** Combine multiple rules into a single AST for more complex evaluations.
  
  ![Screenshot 2024-10-22 130422](https://github.com/user-attachments/assets/9448d787-fbb2-44db-8c87-a90d6ed488b3)
 
  ![Screenshot 2024-10-22 130401](https://github.com/user-attachments/assets/fbb968de-59ee-4611-a48d-6a10819df034)


- **Evaluate Rules:** Check if the given data meets the criteria defined by the AST.

  ![Screenshot 2024-10-22 130552](https://github.com/user-attachments/assets/30ad179b-7558-4e01-9910-24cc50242cdc)

  ![Screenshot 2024-10-22 130534](https://github.com/user-attachments/assets/317bf9bc-92e1-492d-8b0a-2240d261771b)


**Database:** This is my database where all the data are stored.

  ![Screenshot 2024-10-22 131014](https://github.com/user-attachments/assets/086eadec-2c75-40fc-a34f-1c922d36c963)


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
   http://localhost:3000 (ctrl+click)
   ```
I already use Rule Name as "Rule1" and "Rule2" for testing so please use another rule name. So That you get the correct output, Otherwise, it shows "Rule Name: undefined"

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
       "_id": "67175513fa041bc5eb63ad73",
       "rule_name": "Rule1",
       "rule_ast": { ... }
     }
     {
       "_id": "67175534fa041bc5eb63ad75",
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
       "ruleIds": ["67175554fa041bc5eb63ad78", "6717556ffa041bc5eb63ad7b"]
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

2. **Evaluate a Rule**
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
