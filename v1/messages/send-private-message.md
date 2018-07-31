**Enviar mensagem privada**
----
> Envia uma mensagem privada para um ou mais destinatários.
O destino é o e-mail de um usuário já cadastrado na base de dados do Immail.

* **Mensagem com arquivo em anexo**

> Para enviar um arquivo em anexo, será nescessário fazer o upload do mesmo previamente e obter o seu ID.<br>
**[# Saiba como fazer o upload de arquivo temporário](v2/files/upload-temp.files.md)**

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

* **Notes:**
