# Backend-QA-task
FOR TASK 1 PLEASE SET A DELAY OF 10000MS BEFORE RUNNING A COLLECTION (because of pet.swagger limitation, data is saved not immediately, so GET request will fail without a delay)

**Task 2 - User endpoint**
(Fix version, environment, test type, description and pre-conditions can be a part of test cases, however, they are optional)

Test case 1
Summary: Verify that user can be created
Priority: High
Test steps:
1. Import attached collection and environment to Postman
2. Find in the collection POST request called Create User
2.1. Verify that body contains all required fields
2.2. Verify that URL used is for the corresponding environment and action
3. Click on Send button and verify response
Expected results:
1. Collection is successfully imported
2.1. Request body contains all required fields
2.2. URL is correct
3. The response is 200OK and a JSON with "message": "ok"
Attached files: [the Postman collections]

Test case 2
Summary: Verify that user can be received by username
Priority: High
Test steps: 
1. Import attached collection and environment to Postman
2. Find in the collection POST request called Create User
3. Click on Send button
4. Find GET request called Get user and verify the URL
5. Click on Send button and verify the response
Expected results:
1. Collection is successfully imported
3. The response is 200OK and a JSON with "message": "ok"
4. GET request contains appropriate URL
5. The response is 200OK and all the expected fields return values in the response
Attached files: [the Postman collections]

Test case 3
Summary:  Verify that user data can be updated
Priority: High
Test steps:
1. Import attached collection and environment to Postman
2. Find in the collection POST request called Create User and click on Send button
3. Find GET request called Get user and click on Send button
4. Find PUT request called Update user
4.1. Verify that PUT request contains corresponding URL and request body
5. Click on Send button and verify the response
6. Find the GET request called Get user after change and click on Send button
6.1. Verify the response
Expected results:
1. Collection is successfully imported
2. The response is 200OK and a JSON with "message": "ok"
3. The response is 200OK and all fields return values
4. PUT request called Update user goes after Get user request
4.1. PUT request contains data that needs to be modified and a correct URL
5. The response is 200OK and a JSON with "message": "ok"
6.-6.1. The response is 200OK and a JSON with User object with modified data is returned
Attached files: [the Postman collections]

Test case 4
Summary:  
Priority:
Test steps:
Expected results:
Description:
Attached files:

Test case 5
Summary:  
Priority:
Test steps:
Expected results:
Description:
Attached files:

Test case 6
Summary:  
Priority:
Test steps:
Expected results:
Description:
Attached files:

Test case 7
Summary:  
Priority:
Test steps:
Expected results:
Description:
Attached files:

Test case 8
Summary:  
Priority:
Test steps:
Expected results:
Description:
Attached files:

Test case 9
Summary:  
Priority:
Test steps:
Expected results:
Description:
Attached files:

Test case 10
Summary:  
Priority:
Test steps:
Expected results:
Description:
Attached files:
