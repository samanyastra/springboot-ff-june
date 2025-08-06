# Project103 - Employee management(Spring boot) 

- ## Create spring boot application **Employee manager** with below APIs

    - ## Models
        - **employeeDetails**
            - empId - Integer
            - empName - String | varchar(30)
            - location - String | varchar(20)
            - password - String | varchar(20)
            - department - int (many to one relation with department)
            - doj - date
            - isDeleted - boolean - default=false
            - isDisabled - boolean - default=false
        - **department**
            - deptId - Integer
            - deptName - String | Varchar(30)
        - **skills**
            - skillId - Integer - primary key - (no null and unique) 
            - skillName - String | Varchar(45)

        - **employeeSkillMapping** -> composite primary key - (employeeId, skillId)
            - employeeId - int 
            - skillId - int



    - ### /getallemployee (Get Request) - Access(Anyone including unauthenticated users)
        - ***Business Logic*** - Should fetch all the avlb employee with the below information from the database (Services, JPA, Model)
            - name
            - department
            - experience
        - ***Validation*** - If database not contain any employee, send empty list with the response code  **200** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with an array or list of the employees with the status code of **200**.


    - ### /getprofile/{empId} (Get Request) - Access(USER, ADMIN)
        - ***Params*** - empId - a unique ID to identify each employee  (Path variable)
        - ***Business Logic*** - Should fetch all details of the employees based on the employee id. (Services, JPA, Model)
        - ***Validation*** - If database not contain any book with this id, send not found error with response code  **404** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the JSON(HashMap) of the required details with the status code of **200**.

    - ### /createemployee (Post Request) - Access(ADMIN)
        - ***Business Logic*** - Should take user input and create a new Employee after validating all the inputs. (Services, JPA, Model)
            - User Input
                - emp_name - String
                - location - String
                - password - String
                - department - int
                - doj - date
        - ***Validation*** - If input values are invalid return  **400** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the newly created record with the status code of **201**.

    - ### /updateemployee (Post Request) - Access(ADMIN)
        - ***Business Logic*** - Should take user input and update the Employee details after validating all the inputs. (Services, JPA, Model)
            - User Input
                - emp_id - Integer
                - emp_name - String
                - location - String
                - password - String
                - department - int
                - doj - date
        - ***Validation*** - If input values are invalid return  **400**. If that empId does not exist return **404**.  (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the newly updated record with the status code of **200**.

    - ### /deleteemployee (Delete Request) - Access(ADMIN)
        - ***Business Logic*** - Should take empid as user input and **soft-delete** the Employee details. (Services, JPA, Model)
            - User Input
                - emp_id - Integer
        - ***Validation*** - If that empId does not exist return **404**.  (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the message "User deleted" and the status code of **200**.
    
    - ### /mapskills/{emp_Id} (Post Request) - Access(USER, ADMIN)
        - ***Business Logic*** - Should map all the provided skillset to the employee with provided empId. (Services, JPA, Model)
            - skill_name
        - ***Validation*** - If database not contain any empof those skillset, create them and then map it to the user. If user with the provided empId does not exist return Status code of **404**.
        - ***Response*** - Upon successful operation return the response with the user details **200**.

    ---
    - ### /getallskills (Get Request) - Access(USER, ADMIN)
        - ***Business Logic*** - Should fetch all the avlb skills with the below information from the database (Services, JPA, Model)
            - skill_id
            - skill
        - ***Validation*** - If database not contain any skill, send empty list with the response code  **200** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with an array or list of the skills with the status code of **200**.

    - ### /createskill (Post Request) - Access(ADMIN)
        - ***Business Logic*** - Should take user input and create a new Skill after validating all the inputs. (Services, JPA, Model)
            - User Input
                - skill - String
        - ***Validation*** - If input values are invalid return  **400** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the newly created record with the status code of **201**.

    - ### /deleteskill (Delete Request) - Access(ADMIN)
        - ***Business Logic*** - Should take skillid as user input and **soft-delete** the skill. (Services, JPA, Model)
            - User Input
                - skill_id - Integer
        - ***Validation*** - If that skillId does not exist return **404**.  (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with the message "skill deleted" and the status code of **200**.

    ---

    - ### /getalldept (Get Request) - Access(USER, ADMIN)
        - ***Business Logic*** - Should fetch all the deplartment with the below information from the database (Services, JPA, Model)
            - dept_id
            - dept_name
        - ***Validation*** - If database not contain any skill, send empty list with the response code  **200** (ResponseEntity)
        - ***Response*** - Upon successful operation return the response with an array or list of the skills with the status code of **200**.


