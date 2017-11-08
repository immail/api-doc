**Enviar mensagem privada**
----
> Envia uma mensagem privada para um ou mais destinatários.
O destino é o e-mail de um usuário já cadastrado na base de dados do Immail.

* **Enviar mensagem com arquivo em anexo**

> Para enviar um arquivo em anexo, será nescessário fazer o upload do mesmo previamente e obter o seu ID.<br>
**[# Saiba como fazer o upload de arquivo temporário](v2/files/upload-temp.files.md)**

* **URL**
   
   /message/private

* **Method:**
  
  `POST`
  
* **Data Params**
  
  _Para enviar um arquivo em anexo é necessário enviá-lo como arquivo temporário _

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
   X-ACTING-PROFILE: {PROFILE_ID}
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

* **Sample Call:**


* **Notes:**
