**[Home](https://immail.github.io/api-doc/en)** / Send Private Message

**Send private message**
----
> Send a private message to one or more users.
The destination is the email address of a user already registered in the imMail database.

* **Message with file attached**

> To send a file as an attachment, you will need to upload it beforehand and get your ID (file_id).<br>
**[# Learn how to upload temporary file](https://immail.github.io/api-doc/en/v1/files/upload-temp-file.html)**

* **URL**
   
   /message/private

* **Method:**
  
  `POST`
  
* **Data Params**
  
  **Required:**

   ```
    {
      "emails":  [ 
            "test1@example.com",
            "test2@example.com",
            "test3@example.com"
      ],
      "text":    "Happy Birthday",
      "file_id": { FILE_ID } (ID obtido após enviar um arquivo temporário)
    }
  ```

* **Headers**

   ```
   AUTHORIZATION: "Bearer {API_TOKEN}"
   CONTENT-TYPE: application/json
   ```

* **Success Response:** 
  
  * **Code:** 201 <br />
    **Content:** 
```
{}
```
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ messages: ['You don\'t have authorization.'] }`

