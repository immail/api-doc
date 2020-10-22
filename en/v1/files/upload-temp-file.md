**[Home](https://immail.github.io/api-doc/en)** / Upload a temporary file

**Upload temporary files**
----
Uploads one or more temporary files, these files will have nothing to do with a specific directory or conversation. Usually used for sending as an attachment to a message later.

* **URL**
   
   /file/temp

* **Method:**
  
  `POST`
  
* **URL Params**

* **Data Params**

   **Required:**

   `form-data: file: [ ]`

* **Headers**

   ```
   AUTHORIZATION: "Bearer {API_TOKEN}"
   ```

* **Success Response:** 
  
  * **Code:** 201 <br />
    **Content:** 
```
[ 
  { 
    _id:             '598b128100ea8423a3109b2c',
    name:            'demo.txt',
    type:            'FILE',
    mime_type:       'text/plain',
    size:            7 (bytes),
    parent:          '598b128100ea8423a3109b26',
    created_by:      '598b128100ea8423a3109b17',
    conversation_id: '598b128100ea8423a3109b23',
    updated_at:      '2017-08-09T13:47:45.000Z',
    created_at:      '2017-08-09T13:47:40.000Z',
    viewers: 
         [
           {
             profile_id: '598b13b0344087250bef8e3c',
             file_id: '598b13b0344087250bef8e50',
             updated_at: '2017-08-09T13:52:43.000Z',
             created_at: '2017-08-09T13:52:43.000Z',
             _id: '598b13b0344087250bef8e51',
             role: 'ADMIN | EDITOR | READER'
            }
          ],
    status: 'OK' 
  }
]
```
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ messages: ['You don\'t have editor access on target files.'] }`

