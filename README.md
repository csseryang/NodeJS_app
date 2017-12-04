# NodeJS_app

**Create User**
----
  Returns json data about a single user.

* **URL**

  /users

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
 
   None

* **Data Params**

   **Required:** 
   
   header
   
   `Content-Type:application/json`

   
   `{ eamil : example@e.com, password : "examplepassword" }`

* **Success Response:**

  * **Code:** 200 <br />
    **Header:**  ` x-auth : [auth-token] `<br />
    **Content:** `{ _id : 12, email : "example@e.com" }`
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

**Get User's Info**
----
  Returns json data about a single user.

* **URL**

  /users/me

* **Method:**

  `Get`
  
*  **URL Params**

   **Required:**
 
   None

* **Data Params**

   **Required:** 
   
   None

* **Success Response:**

  * **Code:** 200 <br />
    **Header:**  ` x-auth : [auth-token] `<br />
    **Content:** `{ _id : 12, email : "example@e.com" }`
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

**Create a new Todo**
----
  Returns json data about a single todo.

* **URL**

  /todos

* **Method:**

  `Post`
  
*  **URL Params**

   **Required:**
 
   None

* **Data Params**

   **Required:** 
   
   header
   
   `x-auth:[auth-token]`

    `Content-Type:application/json`
  
   `{ text : "To get a job" }`

* **Success Response:**

  * **Code:** 200 <br />

    **Content:** 
    ```javascript
     {
    "__v": 0,
    "text": "To get a job",
    "_creator": "5a18aac9de724f140016e661",
    "_id": "5a24f5f8fa6b661400f633e2",
    "completedAt": null,
    "completed": false}
    ```
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`
  
**List all Todos**
----
  Returns json data about  all todos by one user.

* **URL**

  /todos

* **Method:**

  `Get`
  
*  **URL Params**

   **Required:**
 
   None

* **Data Params**

   **Required:** 
   
   None


* **Success Response:**

  * **Code:** 200 <br />

    **Content:** 
    ```javascript
    {
    "todos": [
        {
            "_id": "5a18aafcde724f140016e663",
            "text": "To run",
            "_creator": "5a18aac9de724f140016e661",
            "__v": 0,
            "completedAt": null,
            "completed": false
        },
        {
            "_id": "5a24f5f8fa6b661400f633e2",
            "text": "To run b",
            "_creator": "5a18aac9de724f140016e661",
            "__v": 0,
            "completedAt": null,
            "completed": false
        }
    ]
    }
    ```
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`  

**Update a todo**
----
  Returns json data about  one signle todo by the user.

* **URL**

  /todos/:todoid

* **Method:**

  `Patch`
  
*  **URL Params**

   **Required:**
 
   [todoid]

* **Data Params**

   **Required:** 
   
   `content-type: applicaiton/json`

   `x-auth: token`

    e.g

    `{ "completed": true  }`

* **Success Response:**

  * **Code:** 200 <br />

    **Content:** 
    ```javascript
    {
    "todo": 
        {
            "_id": "5a18aafcde724f140016e663",
            "text": "To run",
            "_creator": "5a18aac9de724f140016e661",
            "__v": 0,
            "completedAt": 12345,
            "completed": true
        }        
    }
    ```
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }` 

**Delete a todo**
----
  Returns json data about  a todo deleted by the user.

* **URL**

  /todos/:todoid

* **Method:**

  `Delete`
  
*  **URL Params**

   **Required:**
 
   [todoid]

* **Data Params**

   **Required:** 
   
   `content-type: applicaiton/json`

   `x-auth: token`


* **Success Response:**

  * **Code:** 200 <br />

    **Content:** 
    ```javascript
    {
    "todo": 
        {
            "_id": "5a18aafcde724f140016e663",
            "text": "To run",
            "_creator": "5a18aac9de724f140016e661",
            "__v": 0,
            "completedAt": 12345,
            "completed": true
        }        
    }
    ```
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`          