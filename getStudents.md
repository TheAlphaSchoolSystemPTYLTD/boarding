**getStudents**
----
  Returns an array of structured boarding student data in JSON format.
  
* **Version History:**

  TASS v52.2 - Method Added

* **Version:**

  3

* **Permission:**

  Boarders > Boarders > View

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
    {
      "students": [
          {
            "contacts": [
                {
                  "mobile2": "",
                  "town_suburb": "INDOOROOPILLY",
                  "phone": "378 4677",
                  "parent_name2": "",
                  "m_initials": "W",
                  "f_preferred_name": "Wendy",
                  "email": "",
                  "m_preferred_name": "Wendy",
                  "mother_name": "Wendy May",
                  "m_m_description": "Mother/Parent 1",
                  "country": "",
                  "salutation": "",
                  "parent_name": "Mr & Mrs W. Boyle",
                  "family_name": "Boyle",
                  "m_title": "",
                  "m_suffix": "",
                  "f_suffix": "",
                  "post_code": 4068,
                  "father_name": "Wade Boyle",
                  "mobile1": "",
                  "address1": "WWWW WWWW1WWWW WWWW2WWWW WWWW3WWWW WWWW4WWWW WWWA5",
                  "f_surname": "May",
                  "f_initials": "W",
                  "address_description": "Postal",
                  "f_description": "Father/Parent 2",
                  "f_other_name": "",
                  "email2": "tammys2@tassweb.com.au",
                  "f_title": "",
                  "m_first_name": "Wendy",
                  "work_phone": "378 4677",
                  "state_code": "QLD",
                  "parent_code": "000036",
                  "address_number": 1,
                  "f_first_name": "Wendy",
                  "m_other_name": "",
                  "m_surname": "May",
                  "relationship": ""
                }
            ],
            "boarding_house_name": "",
            "pref_name": "Henry",
            "boarding_house_code": "",
            "student_code": "0009112",
            "preferred_surname": "Boyle",
            "email": "",
            "first_name": "Henry",
            "hosts": [],
            "room_number": "",
            "year": 10,
            "dob": "23/09/1984",
            "family_name": "Boyle",
            "other_name": "",
            "gender": "M",
            "mobile": ""
          }

      ],
      "__tassversion": "01.053.3.000",
      "token": {
            "commtype": "ALL",
            "timestamp": "{ts '2021-01-20 10:42:25'}"
      },
    }
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
    {
        "commtype":"ALL",
        "studcode":"0009130"
    }
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
