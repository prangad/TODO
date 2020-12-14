# HotShop Software Requirements Specifications
---

# Overview

The purpose of this document is to specify descriptions of how our system should behave as well as outline functional and non functional aspects of the application. This document outlines the specific functionality and constraints of the application, but not the implementation methods. 

# Software Requirements

This section outlines the Software requirements. It is divided into two subsections: Functional Requirements and Non-Functional Requirements. Each type of requirements has categories within for various features. 

## Functional Requirements

### User Login/Registration Service 

| ID  | Requirement     | Test Cases |
| :-------------: | :----------: | :----------: |
| FR1 | The application shall allow a user to login if the user’s password and username match the local database. | TC11, TC17 |
| FR2 | The application shall not allow a user to login if the user’s password and username do not match the local database. | TC12 |
| FR3 | The application shall contain a static “DB” class contained within the application that stores usernames and passwords. | TC5|
| FR4 | The application shall ensure emails follow a basic email convention consisting of strings separated by ‘@’ and ‘.’ | TBD |
| FR5 | The application shall ensure passwords follow a basic password convention in which passwords are a minimum of 5 characters long. | TBD |
| FR6 | The application stores new users' first and last name of the user to the local database. | TBD |

### Database Functionality

| ID  | Requirement     | Test Cases |
| :-------------: | :----------: | :----------: |
| FR7 | The application shall store local list data in the static “DB” class. | TC17 |
| FR8 | The application shall have the ability to join a list. | TC13 |
| FR9 | The application database shall have the ability to create new list groups. | TC4 |
| FR10 | The application database shall have the ability to add a new product. | TC1, TC17 |
| FR11 | The application database  shall have the ability to edit product price, name, quantity, and consumers. | TC2, TC17 |
| FR12 | The application database shall have the ability to remove a product from the database. | TC3 |
| FR13 | The application database shall have the ability to get a product from the ID. | TC6 |
| FR14 | The application database shall have the ability to get a list of the consumers of a product. | TC7 |
| FR15 | The application database shall have the ability to get a list ID from the name. | TC8 |
| FR16 | The application database shall have the ability to get the list from the ID. | TC9 |
| FR17 | The application database shall have the ability to get the current user based on their ID. | TC10 |

### Shopping Functionality

| ID  | Requirement     | Test Cases |
| :-------------: | :----------: | :----------: |
| FR18 | The application shall calculate the split cost for each consumer of a completed shopping trip based on the list they are in, items bought, price of the products input by the user, as well as the specified consumers receiving the product. | TC14, TC17 |
| FR19 | The application shall display the cost owed by each individual consumer. | TC14, TC17 |
| FR20 | The application shall allow the shopper to select which items are bought from the list during a shopping trip. | TC15, TC17 |
| FR21 | The application shall remove the items bought from the shopping list after a shopping trip is completed.  | TC16 |
| FR22 | The application shall begin the shopping trip upon user demand. | TC17 |
| FR23 | The application shall complete the shopping trip upon user demand. | TC17 |

## Non-Functional Requirements

### Aesthetics 

| ID  | Requirement     | Test Cases |
| :-------------: | :----------: | :----------: |
| NFR1 | The application shall use complimentary colors (160, 30, 30) (190, 60, 60). | TBD |
| NFR2 | The application shall have a consistent theme and use the font Nunito. | TBD |
| NFR3 | The application shall use the icon logo.png in the splashscreen. | TC21 |
| NFR4 | The application shall show the selected items during a shopping trip using color (80, 160, 102). | TBD |
| NFR5 | The application shall use the format “$###,###,##0.00” for all dollar values. | TBD |

### User Messages

| ID  | Requirement     | Test Cases |
| :-------------: | :----------: | :----------: |
| NFR6 | The application shall provide an error message to the user if the username and password do not match. | TBD |
| NFR7 | The application shall provide an error message if the input email does not match the basic email convention consisting of strings separated by ‘@’ and ‘.’ | TBD |
| NFR8 | The application shall provide a toast displaying the name of the list when selecting a list to be edited/shopped. | TBD |
| NFR9 | The application shall provide a toast informing the user that a list has been joined. | TBD |
| NFR10 | The application shall provide a toast informing the user that they have already joined a list they are attempting to join. | TBD |

### Usability

| ID  | Requirement     | Test Cases |
| :-------------: | :----------: | :----------: |
| NFR11 | The application shall allow the user to go to the HomeScreen from the ListProductsScreen. | TC18 |
| NFR12 | The application shall allow the user to go to the HomeScreen from the ShoppingScreen. | TC19 |
| NFR13 | The application shall allow the user to go to the HomeScreen from the SummaryScreen. | TC20 |
| NFR14 | The application shall show the user the current total cost of a shopping trip as items are selected on the ShoppingScreen. | TBD |
| NFR15 | The application shall show the user the total cost of a shopping trip on the SummaryScreen. | TBD |

---
# Test Specification
This section contains unit tests, integration tests, and system tests that were carried out on the HotShop application. The tests cover most-all basic functions of the application and ensure the application is working as intended.

## Unit tests
| ID    | Description |          Steps          | Input Values | Expected Output | Actual Output | Pass/Fail | Requirement Link |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| TC1 | Add Product | <ol><li>Call the Add Product Method in Static DB Class</li><li>Assert True Function Return Value</li></ol> | "Test", 19.99, 0, 10, new ArrayList | True | True | Pass | FR10 |
| TC2 | Edit Product | <ol><li>Call the Edit Product Method in Static DB Class</li><li>Assert True Function Return Value</li></ol> | 0, 0, "Test", 10.99, 2, new ArrayList | True | True | Pass | FR11 |
| TC3 | Remove Product | <ol><li>Call the Remove Product Method in Static DB Class</li><li>Assert True Function Return Value</li></ol> | 0 | True | True | Pass | FR12 |
| TC4 | Create List | <ol><li>Call the Add List Method in Static DB Class</li><li>Assert True Function Return Value</li></ol> | "Test", 123 | True | True | Pass | FR9 |
| TC5 | Create User | <ol><li>Call the Add User Method in Static DB Class</li><li>Assert True Function Return Value</li></ol> | "test@test.com", "Hello", "Mario", "Cart" | True | True | Pass | FR6 |
| TC6 | Get Product from ID | <ol><li>Call the Get Product from ID Method in Static DB Class</li><li>Assert Equal the Product Returned Corresponds with Product ID</li></ol> | 0 | Product 0 | Product 0 | Pass | FR13 |
| TC7 | Get Consumers of Product | <ol><li>Call the Get Consumers of Product Method in Static DB Class</li><li>Assert Equal the Consumers List Returned Matches the Product Consumers</li></ol> | 0, 0 | Consumers of Product 0 in List 0 | Consumers of Product 0 in List 0 | Pass | FR14 |
| TC8 | Get List ID from Name | <ol><li>Call the Get List ID from Name Method in Static DB Class</li><li>Assert Equal the Returned List's Name Equals Input Name</li></ol> | "The Cool List" | 0 | 0 | Pass | FR15 |
| TC9 | Get List from ID | <ol><li>Call the Get List from ID Method in Static DB Class</li><li>Assert Equal the Returned List's ID Equals Input ID</li></ol> | 0 | List 0 | List 0 | Pass | FR16 |
| TC10 | Get User from ID | <ol><li>Call the Get User from ID Method in Static DB Class</li><li>Assert Equal the Returned User's ID Equals Input ID</li></ol> | 1 | User 1 | User 1 | Pass | FR17 |
## Integration tests
| ID | Description | Steps | Input Values | Expected Output | Actual Output | Pass/Fail | Requirement Link |
| :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: |
| TC11 | Successful Login | <ol><li>Log in Using Username and Password in Default Database</li><li>Verify Successful Login</li></ol> | Valid Username and Password | Verified User Proceeds to Home Screen | Verified User Proceeded to Home Screen | Pass | FR1 |
| TC12 | Unsuccessful Login | <ol><li>Log in Using Unknown Username and Password</li><li>Verify Unsuccessful Login</li></ol> | Unknown Username and Password | Unverified User is Prompted to Login | Unverified User was Prompted to Login | Pass | FR2 |
| TC13 | User Joining Lists | <ol><li>Select "All Lists" Tab on Home Screen</li><li>Select a List the Verified User has not Joined</li><li>Verify the Selected List Appears in "Your Lists" on Home Screen</li></ol> | Manual List Selection | Verified User Joins List | Verified User Joined List | Pass | FR8 |
| TC14 | Split Cost | <ol><li>Begin a Shopping Trip for Any List</li><li>Select Multiple Products</li><li>Select "Complete Shopping"</li><li>Verify Split Cost is Accurate and Proportional to Purchased Products</li></ol> | Manual Shopping Completion | Consumers Receive Accurate Cost Split | Consumers Received Accurate Cost Split | Pass | FR18, FR19 |
| TC15 | Product Selection During Shopping | <ol><li>Begin a Shopping Trip for Any List</li><li>Select Multiple Items</li><li>Verify Items get Marked and Total Increases Appropriately</li></ol> | Manual Product Selection | Products Marked Green and Total Increases | Products were Marked Green and Total Increased | Pass | FR20 |
| TC16 | Removal of Purchased Products | <ol><li>Begin a Shopping Trip for Any List</li><li>Select Multiple Products</li><li>Select "Complete Shopping"</li><li>Return to List Screen</li><li>Ensure Products Selected were Removed from List</li></ol> | Manual Shopping Completion | Products are Removed from List | Products were Removed From List | Pass | FR21 |
## System tests
| ID | Description | Steps | Input Values | Expected Output | Actual Output | Pass/Fail | Requirement Link |
| :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: |
| TC17 | Successful Shopping | <ol><li>Login</li><li>Select List from "Your Lists"</li><li>Add a Product</li><li>Edit a Product</li><li>Select "Start Shopping"</li><li>Select Multiple Products</li><li>Complete Shopping</li><li>Verify Split Cost is Accurate and Proportional to Purchased Products</li><ol> | N/A | Correct Price Distribution Between Consumers | N/A | Pass | FR1, FR7, FR10, FR11, FR18, FR19, FR20, FR22, FR23 |
| TC18 | Simple Navigation from List Products Screen to Home | <ol><li>Navigate to List Products Screen</li><li>Select Home Button (Do Not Use Android Back Button)</li><li>Verify App Navigates Home</li></ol> | Manual Home Button Select | App Navigates Home | App Navigated Home | Pass | NFR11 |
| TC19 | Simple Navigation from Shopping Screen to Home | <ol><li>Navigate to Shopping Screen</li><li>Select Home Button (Do Not Use Android Back Button)</li><li>Verify App Navigates Home</li></ol> | Manual Home Button Select | App Navigates Home | App Navigated Home | Pass | NFR12 |
| TC20 | Simple Navigation from Summary Screen to Home | <ol><li>Navigate to Summary Screen</li><li>Select Home Button (Do Not Use Android Back Button)</li><li>Verify App Navigates Home</li></ol> | Manual Home Button Select | App Navigates Home | App Navigated Home | Pass | NFR12 |
| TC21 | Uses HotShop Logo for App Splashscreen | <ol><li>Navigate to Phone Downloaded Apps Overview</li><li>Locate HotShop App</li><li>Launch HotShop App</li><li>Verify App Splashscreen Contains App Logo</li></ol> | Manual Navigation | App Splashscreen Contains App Logo | App Splashscreen Contained App Logo | Pass | NFR3 |
---

# Software Artifacts
This section contains previous artifacts of the HotShop application. These artifacts were used as checkpoints in the software development process.

## Midterm Deliverables
* [Project Proposal](https://github.com/prangad/GVSU-CIS350-TODO/blob/master/docs/hotshop-proposal.md)
* [Project Tasks](https://github.com/prangad/GVSU-CIS350-TODO/blob/master/docs/hotshop-tasks.md)
* [Software Requirements](https://github.com/prangad/GVSU-CIS350-TODO/blob/master/docs/%20software_requirements_specification.md)
* [Use-Case Diagrams](https://github.com/prangad/GVSU-CIS350-TODO/blob/master/artifacts/use_case_diagrams/HW3_UseCase_Diagrams.pdf)
* [Development Gantt Chart](https://github.com/prangad/GVSU-CIS350-TODO/blob/master/docs/HotShotGantt.xlsx)
* [Midterm Presentation](https://github.com/prangad/GVSU-CIS350-TODO/blob/master/docs/HotShop.pdf)

## Final Deliverables
* [Project Source Code](https://github.com/prangad/HotShop)
* [Final Gantt Chart](https://github.com/prangad/GVSU-CIS350-TODO/blob/master/docs/HotShotGanttFinal.xlsx)
* [Final Presentation](https://github.com/prangad/GVSU-CIS350-TODO/blob/master/docs/HotShopFinal.pdf)

