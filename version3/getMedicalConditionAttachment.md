**getMedicalConditionAttachment**
----
  Returns a structured student medical condition attachment details data in JSON format.
  
* **Version History:**

  TASS v52.2 - Method Added

* **Version:**

  3

* **Permission:**

  Student Medical > Medical Conditions tab

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `studcode [string]` - Student Code

   `mcond_code [string]` - Medical Condition Code

   `attach_id [string]` - Attachment Id

   **Optional:**

   None

   **Conditional:**

   None

* **Success Response:**

    ```javascript
    { 
       "file_size":73771,
       "has_attachment":true,
       "file":"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",
       "file_name":"testing.JPG",
       "token":{ 
          "timestamp":"{ts '2020-02-14 09:13:41'}",
          "studcode":"0009130",
          "mcond_code":"AST",
          "attach_id":"5F724726-E361-C720-A1160233A4E8893D"
       }
    }
    ```
 
* **Error Response:**

    `studcode` not supplied
    ```javascript
      "error": "studcode is required."
    ```

    `mcond_code` not supplied
    ```javascript
      "error": "mcond_code is required."
    ```

    `attach_id` not supplied
    ```javascript
      "error": "attach_id is required."
    ```

* **Sample Parameters:**

  ```javascript
    {"studcode":"0009130","mcond_code":"AST","attach_id":"5F724726-E361-C720-A1160233A4E8893D"}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getMedicalConditionAttachment&appcode=API10&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getMedicalConditionAttachment">
       <input type="hidden" name="appcode" value="API10">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```