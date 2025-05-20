# Backend-QA-task
**FOR TASK 1 PLEASE SET A DELAY OF 10000MS BEFORE RUNNING A COLLECTION (because of pet.swagger limitation, data is saved not immediately, so GET request will fail without a delay)**

**Task 2 - User endpoint**
(Fix version, environment, test type, description and pre-conditions can be a part of test cases, however, they can be optional)

Test case 1

Summary: Verify that user can be created
Priority: High
Test type: Functional (positive)
Test steps:
1. Import attached collections to Postman
2. Find in the collection POST request called Create User
   2.1. Verify that body contains all required fields
   2.2. Verify that URL used is for the corresponding environment and action
3. Click on Send button and verify response
Expected results:
1. Collections are successfully imported
   2.1. Request body contains all required fields
   2.2. URL is correct
3. The response is 200OK and a JSON with "message": "ok"
Attached files: [the Postman collections]

Test case 2

Summary: Verify that user can be received by username
Priority: High
Test type: Functional (positive)
Pre-conditions:
Import attached collections to Postman and create a user using POST request
Test steps: 
1. Find GET request called Get user
2. Verify that the URL contains the correct username via {{username}} variable
3. Click on Send button and verify the response
Expected results:
1. GET request contains appropriate URL
2. The response is 200OK and all fields return expected values in the response
Attached files: [the Postman collections]

Test case 3
Summary:  Verify that user data can be updated
Priority: High
Test type: Functional (positive)
Pre-conditions:
1. Import attached collections to Postman and create a user using POST request
Test steps:
1. Find a PUT request called Update user
2. Verify that PUT request contains corresponding URL: /user/{{username}}
3. Check that the request body has modified values
4. Click on Send button and verify the response
Expected results:
1. PUT request called Update user is in the collection
2-3.PUT request contains data that needs to be modified and a correct URL
4. The response is 200OK and a JSON with message "ok" or user ID
Attached files: [the Postman collections]

Test case 4
Summary:  Verify that updated user data is returned correctly after change
Priority: High
Test type: Functional (positive)
Pre-conditions:
1. Import attached collections to Postman and create a user using POST request
2. Update the created user using a PUT request
Test steps:
1. Find the GET request called Get user after change and check that the URL contains correct username
2. Click on Send button and verify the response
Expected results:
1. PUT request contains data that needs to be modified and a correct URL
2. The response is 200OK
2.1. A JSON response with modified fields from previous step and all other unchanged fields is returned
Attached files: [the Postman collections]

Test case 5
Summary: Verify that user can be successfully deleted
Priority: Medium → High
Test type: Functional (positive)
Pre-conditions: 
1. Import attached collections
2. Create a user using a POST request from the imported collection
3. Username value is saved in the environment
Test steps:
1. Import the DELETE request into the attached collection, using the following curl and Send it:
curl -X 'DELETE' \
  'https://petstore.swagger.io/v2/user/{{username}}' \
  -H 'accept: application/json'
2. Verify the response
Expected results:
1. Request is successfully imported and sent
2. The response is 200OK and JSON response contains a message with a username
Attached files: [the Postman collections]

Test case 6
Summary:  Verify that deleted user cannot be retrieved
Priority: High
Test type: Functional (positive)
Pre-conditions: 
1. Import attached collections
2. Create a user using a POST request from the imported collection
3. Username value is saved in the environment
4. Delete user using a DELETE request
Test steps:
1. Open a GET request called Get user and Send it
2. Verify the response
Expected results:
1. GET request called Get user is in the collection
2. The response status is 404 Not Found and the response body contains message saying "User not found"
Attached files: [the Postman collections]

Test case 7
Summary: Verify that user can be created without a required field 
Priority: Medium
Test type: Functional (negative)
Test steps:
1. Import attached collections to Postman
2. Find in the collection POST request called Create User
2.1. In the body of the request delete username field and adjust the request accordingly
2.2. Verify that URL used is for the corresponding environment and action
3. Click on Send button and verify response
Expected results:
1. Collections are successfully imported
2.1. Request body contains all fields except username
2.2. URL is correct
3. The response is 200OK (due to Swagger mock implementation) and a JSON returned with "message": "ok"
Attached files: [the Postman collections]
Note: In the real API this request would send 400 Bad Request or 422 Unprocessable Entity.

Test case 8
Summary: Verify behavior when trying to retrieve a user that was created without a username
Priority: Medium
Test type: Functional (negative)
Pre-conditions: 
1. Import attached collections
2. Create a user without username using a POST request from the imported collection
Test steps:
1. Find a Get user request
1.1. Make sure that the {{username}} value is not set or empty
2. Send a request and verify the response
Expected results:
1-1.1. Get user request contains the not set or empty {{username}} value in the URL
2.The response code is 404 Not Found and the response body contains message "User not found
Attached files: [the Postman collections]

Test case 9
Summary:  
Priority:
Test steps:
Expected results:
Attached files:

Test case 10
Summary:  
Priority:
Test steps:
Expected results:
Description:
Attached files:
