**getStudents**
----
  Returns an array of structured boarding student data in JSON format.

* **Version:**

  1
  
* **Version History:**

  New properties `includephoto` and `thumbnail` added in Version 51.4.

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `commtype [string]` - Communication Rule Type. Must be one of:
    ```HTML
        ALL - Communication Types
        ACA – Academic Reports
        ATT – Attendance
        EC – Emergency Contact
        GEN – TASS.web Correspondence
        LW – Student Lives With
        TK – Teacher Kiosk View
        TKCO – Teacher Kiosk Correspondence
    ```                       

   **Optional:**

   `studcode [string]` - Student Code for retrieving a specified single student record

   `includephoto [boolean]` - Must be 'true' or 'false' for whether returning student photo.

   **Conditional:**

   `thumbnail [boolean]` - Must be 'true' or 'false' for whether returning student thumbnail photo, when includephoto = 'true'.

* **Success Response:**

    ```javascript
    students: [
      {
        contacts: [
          {
            mobile2: "0412016535 (test)",
            town_suburb: "CHERMSIDE WEST",
            address_description: "Correspondence",
            phone: "07 3366 2541",
            parent_name2: "",
            email: "erd@dre.com",
            work_phone: "848 2256",
            state_code: "QLD",
            mother_name: "Joan Angus",
            parent_code: "000011",
            address_number: 1,
            country: "",
            salutation: "Ms Angus",
            parent_name: "Ms. J. Angus",
            family_name: "Angus",
            post_code: 4032,
            relationship: "",
            father_name: "Ronald Angus",
            mobile1: "0413443655 (sumlog)",
            address1: "Correspondence Address",
            address3: "",
            address2: "PO Box 3088"
          },
          {
            mobile2: "",
            town_suburb: "KEDRON",
            address_description: "Billing",
            phone: "3366 2541 Mobile: 015 667 8349",
            parent_name2: "",
            email: "",
            work_phone: "848 2256",
            state_code: "QLD",
            mother_name: "Joan Angus",
            parent_code: "000011",
            address_number: 3,
            country: "",
            salutation: "Ms Angus",
            parent_name: "Ms. J. Angus",
            family_name: "Angus",
            post_code: 4031,
            relationship: "",
            father_name: "Ronald Angus",
            mobile1: "0413698552",
            address1: "Billing Address",
            address3: "",
            address2: "U 4/6 Emerald St"
          }
        ],
        boarding_house_name: "Grand Hall Dormitory",
        year: 11,
        pref_name: "Paul",
        boarding_house_code: "GHD",
        dob: "15/10/1991",
        family_name: "Angus",
        gender: "M",
        student_code: "0009080",
        email: "davidh@tassweb.com.au",
        first_name: "Paul",
        mobile: "0412016500 "
      }
    ]
    ```
 
* **Error Response:**

    `commtype` not supplied
    ```javascript
      "__msg": "'commtype' IS REQUIRED"
    ```

    `includephoto` not a valid boolean
    ```javascript
      "__msg": "'includephoto' IS NOT A VALID BOOLEAN"
    ```

    `thumbnail` not a valid boolean when includephoto = 'true'
    ```javascript
      "__msg": "'thumbnail' IS NOT A VALID BOOLEAN"
    ```
    
* **Sample Parameters:**

  ```javascript
    commtype=ALL
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=GetStudents&appcode=DEMOB&company=10&token=THgDmy%2F7dWxUqvyAgjHHeg%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
      <input type="hidden" name="method" value="getStudents" />
      <input type="hidden" name="appcode" value="DEMOB" />
      <input type="hidden" name="company" value="10" />
      <textarea name="token">THgDmy/7dWxUqvyAgjHHeg==</textarea>
    </form>
  ```
