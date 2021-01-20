**getMedicalConfNoteAttachment**
----
  Returns a structured student medical condition attachment details data in JSON format.
  
* **Version History:**

  TASS v52.3 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Setup > Student Medical > Confidential Notes tab > View

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `studcode [string]` - Student Code

   `note_cat [string]` - Medical Note Category

   `note_date [timestamp yyyy-MM-dd HH:mm:ss.SSS]` - Medical Note Date and Time

   `attach_id [string]` - Attachment Id

   **Optional:**

   None

   **Conditional:**

   None

* **Success Response:**

    ```javascript
  {
      "file_size": 80039,
      "has_attachment": true,
      "file": "[Base64 encoded image string]",
      "file_name": "0009445.jpg",
      "__tassversion": "01.053.3.000",
      "token": {
            "note_date": "2021-01-19 16:13:29.000",
            "timestamp": "{ts '2021-01-19 16:47:35'}",
            "studcode": "0009130",
            "note_cat": "NUR",
            "attach_id": "FCC951C5-C477-4CF3-1005C09A39997741"
      }
  }
    ```
 
* **Error Response:**

    `studcode` not supplied
    ```javascript
      "error": "studcode is required."
    ```

    `note_cat` not supplied
    ```javascript
      "error": "note_cat is required."
    ```

    `note_date` not supplied
    ```javascript
      "error": "note_date is required."
    ```

    `attach_id` not supplied
    ```javascript
      "error": "attach_id is required."
    ```

* **Sample Parameters:**

  ```javascript
    {"studcode":"0009130","note_cat":"NUR","note_date":"2021-01-19 16:13:29.000","attach_id":"FCC951C5-C477-4CF3-1005C09A39997741"}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getMedicalConfNoteAttachment&appcode=API10&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getMedicalConfNoteAttachment">
       <input type="hidden" name="appcode" value="API10">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```
