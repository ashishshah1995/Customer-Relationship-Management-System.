# Customer-Relationship-Management-System

Build web application for allowing user to make CRUD operations which includes 

1. Creating the customer

2. Updating the customer

3. Deleting the customer

4. Searching the customer

# Working Demo of the project

    1. Adding the customer
    2. Updating the customer
    3. Deleting the customer
    4. Searching the customer

![ScreenCapture_13-05-2019-15 42 15 (1)](https://user-images.githubusercontent.com/26305085/57651763-1178fb00-759c-11e9-82f8-f96e31eda619.gif)


# Running the project

1. Make a local database installation. (MySQL can be downlaoded from http://dev.mysql.com/downloads)

2. Open MySql workbench and run two scripts 

    1. create-user.sql

    2. customer-tracker.sql

    These scripts would create a db user called springstudent, create the DB schema called web_customer_tracker, create a Customer table, populate the Customer table and create user and role tables

3. To run the application locally: 
 
    1. Select the root project folder

    2. Right-Click, select Run As > Run On Server (A tomcat server should have been installed in your local machine) 

# Development process

1. Set up Database Development environment

2. List customers

3. Add a new customer

4. Update the customer

5. Delete the customer

6. Search the customer

In this project browser make requests to customer controller which will make use of Data Access object (DAO). DAO will access database for by using hibernate API, the controller will place into spring MVC model and send it to jsp pages which will render data to screen

**Data Access Object** DAO is helper/utility class for talking with database, we used dao uses hibernate api for accessing data 

# Develpoment process for listing customers

1. Create Customer.java

2. Create CustomerDAO.java

    1. CustomerDAOImpl.java
  
3. Create CustoomerController.java

4. Create JSP page: list-customers.jsp

# Annotations

1. Spring provides **@Transactional** which will automatically begin and end transaction of hibernate code.

2. **@Repository** 

    1. For DAO implementation class

    2. Inherits from @Component so component scanning will be done automatically and registers DAO implementation

    3. Translation of any jdbc related exception, any checked expection will be translate to unchecked excepion

3. **@GetMapping**  Request data from given source

4. **@PostMapping** Submit data to given source

5. **@Service** layer sits between customer controller and customer DAO

    1. Intermediate layer for custom business logic

    2. Integrate data from multiple sources

# Development process for adding customer

1. Update list-customer.jsp

2. New "Add Customer" button

3. Creating html form for new customer

4. Process from data

    1. Controller-> Services -> DAO

# Development process for Updating customer

1. Update list-customer.jsp

    1. New "Update" link
    
2. Create customerform.jsp

    1. Prepolutate the form
    
3. Process form data

    1.Controller -> Service -> DAO

In hibernate API there are 2 methods to save data in database

1. save() - insert new record

2. update() - update existing record

3. saveOrUpdate() - if primary key empty then insert new customer else Update existing customer

# Development process for Deleting customer

1. Add "Delete" link on JSP

2. Add code for "Delete"

3. Controller-> Service -> DAO

# Development process for Searching customer

1. Create the HTML form

2. Add mapping to the controller

3. Add methods in the service layer to delegate to DAO

4. Add method in the DAO to perfom search

