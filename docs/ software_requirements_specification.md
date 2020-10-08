# Overview
The purpose of this document is to specify descriptions of how our system should behave as well as outline functional and non functional aspects of the application.
# Functional Requirements
1. User Login Service
    1. R1.1: The application shall query the database for information regarding the user attempting to log in.
    1. R1.2: The application shall query the database to store new user registration information.
1. Cloud-Based Shopping List Access
    1. R2.1: The application shall store local list data to the database. 
    1. R2.2: The application shall query the database for list data and store locally.
    1. R2.3: The application shall have the ability to form and invite users to user groups. 
    1. R2.4: The application shall link shopping lists to users of the same group in the database. 
1. Shopping List Cost Splitting Calculator
    1. R3.1: The application shall calculate the split cost of the completed shopping based on the items bought, price of the products input by the user, as well as the specified consumers receiving the product.
    1. R3.2: The application shall allow users to enter a product price that can be stored in 16 bits (0 -65,535).
    1. R3.3: The application shall allow the user to mark the other users who are consumers of the product. 
    1. R3.4: The application shall allow the shopper to choose which items are bought from the list during a shopping trip.
    1. R3.5: The application shall remove the items bought from the shopping list after a shopping trip is completed. 

# Non-Functional Requirements
1. Aesthetically Pleasing
    1. R4.1: The application shall use complimentary colors (160, 30, 30) (190, 60, 60)
    1. R4.2: The application shall have a consistent theme and use the font Nunito.
1. User Messages
    1. R5.1: The application shall provide messages to the user regarding login exceptions.   
    1. R5.2: The application shall provide a message to each user in the group containing their total owed to the shopper after a shopping trip has been completed. 
