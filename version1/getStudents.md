**getStudents**
----
  Returns an array of structured boarding student data in JSON format.
  
* **Version History:**

  TASS v51.4 - Add two new properties `includephoto` and `thumbnail`.

  TASS v51.4 (PR4) - Add new Property `email2`.

  TASS v52.0 - Return 3 new fields `preferred_surname`, `first_name`, `other_name` for each student. Return 16 new fields `m_description`, `m_title`, `m_initials`, `m_surname`, `m_first_name`, `m_other_name`, `m_preferred_name`, `m_suffix`, `f_description`, `f_title`, `f_initials`, `f_surname`, `f_first_name`, `f_other_name`, `f_preferred_name`, `f_suffix` for parent1 & parent2 per contact.

* **Version:**

  1

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
    "students": [
      {
        "contacts": [
          {
            "mobile2": "0412016500",
            "town_suburb": "ALBION",
            "m_initials": "P",
            "m_suffix": "suf",
            "m_surname": "Clark",
            "m_description": "Mother/Parent 1",
            "m_preferred_name": "Paula",
            "m_other_name": "PauOth",
            "m_title": "Mrs",
            "m_first_name": "Paula",
            "phone": "3870 9987",
            "parent_name2": "",
            "f_initials": "E",
            "f_suffix": "",
            "f_surname": "Clark",
            "f_description": "Father/Parent 2",
            "f_preferred_name": "Edward",
            "f_other_name": "",
            "f_title": "",
            "f_first_name": "Edward",
            "email": "t.sloman84@gmail.com",
            "mother_name": "Paula Clark",
            "country": "AUSTRALIA",
            "salutation": "Mr and Mrs Clark",
            "parent_name": "Mrs E Clark PNE",
            "family_name": "Clark",
            "post_code": 4005,
            "father_name": "Edward Clark",
            "mobile1": "0427203657",
            "address1": "",
            "address3": "Addr Line 3",
            "address2": "123 Smith Rd",
            "address_description": "Correspondence",
            "email2": "fang.guo@tassweb.com",
            "work_phone": "3201 1302",
            "state_code": "QLD",
            "parent_code": "000055",
            "address_number": 1,
            "relationship": ""
          },
          {
            "mobile2": "",
            "town_suburb": "JIMBOOMBA",
            "m_initials": "P",
            "m_suffix": "suf",
            "m_surname": "Clark",
            "m_description": "Mother/Parent 1",
            "m_preferred_name": "Paula",
            "m_other_name": "PauOth",
            "m_title": "Mrs",
            "m_first_name": "Paula",
            "phone": "",
            "parent_name2": "",
            "f_initials": "E",
            "f_suffix": "",
            "f_surname": "Clark",
            "f_description": "Father/Parent 2",
            "f_preferred_name": "Edward",
            "f_other_name": "",
            "f_title": "",
            "f_first_name": "Edward",
            "email": "tammy.sloman@yahoo.com.au",
            "mother_name": "Paula Clark",
            "country": "",
            "salutation": "Clark Salutation",
            "parent_name": "Paula Clarké Another Line",
            "family_name": "Clark",
            "post_code": 4280,
            "father_name": "Edward Clark",
            "mobile1": "0412016500WWUFUGLQWUWEHEFLKUQH",
            "address1": "Residential Address",
            "address3": "",
            "address2": "536 Arrow Road",
            "address_description": "Residential",
            "email2": "residential.address@tassweb.com",
            "work_phone": "",
            "state_code": "NSW",
            "parent_code": "000055",
            "address_number": 2,
            "relationship": ""
          }
        ],
        "boarding_house_name": "Grand Hall Dormitory",
        "pref_name": "Andy",
        "boarding_house_code": "GHD",
        "student_code": "0009130",
        "preferred_surname": "Clark",
        "email": "peter.ripper@tassweb.com.au",
        "first_name": "Andréa",
        "hosts": [
          {
            "town_suburb": "ALBION",
            "mobile2": "",
            "address_description": "",
            "host_number": 1,
            "email": "smithy@alphabus.com.au",
            "state_code": "QLD",
            "business_phone": "3321 9943",
            "address_number": "",
            "parent_code": "",
            "country": "",
            "host_name": "Mr & Mrs J A Smith",
            "salutation": "Mr & Mrs Smith",
            "post_code": 4007,
            "home_phone": "3262 1149",
            "enrolled_parent_code": "",
            "relationship": "Aunty",
            "address1": "121 Applefield Avenue",
            "mobile1": "0418 558 845",
            "fax": "",
            "address3": "",
            "address2": ""
          }
        ],
        "room_number": "A214",
        "year": 11,
        "dob": "02/09/1994",
        "family_name": "Clark",
        "other_name": "Joan",
        "gender": "F",
        "mobile": "0025632532"
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
