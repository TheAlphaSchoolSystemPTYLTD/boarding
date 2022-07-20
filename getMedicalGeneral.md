**getMedicalGeneral**
----
  Returns student general medical details data in JSON format.
  
* **Version History:**

  TASS v52.3 - Method Added

  TASS v54.0 - Add a new conditional field `currentstatus`, change the required field `studcode` to a conditional field. Add new validations for `studcode` and `currentstatus`.

* **Version:**

  3

* **Permission:**

  Medical Setup > Student Medical > View

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   None

   **Optional:**

   None

   **Conditional:**

    `currentstatus [string]` - Required if `studcode` is not supplied. Must be 'current' or 'future' or 'past' or 'noncurrent'.

    `studcode [string]` - Required if `currentstatus` is not supplied. Contains Only One Student Code if supplied.

* **Success Response:**

    when `currentstatus` is supplied
    ```javascript
    {
        "data": [
            {
                "contacts": [
                    {
                        "contact_name": "Mr & Mrs L. O'Bell",
                        "medical_townsub": "INALA",
                        "medical_home_phone": "073874 6589",
                        "medical_addr1": "6 Polaris Street",
                        "medical_country": "",
                        "medical_addr2": "",
                        "medical_mob_phone2": "0427203657",
                        "medical_addr3": "",
                        "medical_post_code": 4077,
                        "medical_bus_phone": "073564 8941",
                        "medical_mob_phone": "0488067672",
                        "medical_state_code": "QLD"
                    },
                    {
                        "contact_name": "Bell Mother",
                        "medical_townsub": "",
                        "medical_home_phone": "",
                        "medical_addr1": "",
                        "medical_country": "",
                        "medical_addr2": "",
                        "medical_mob_phone2": "",
                        "medical_addr3": "",
                        "medical_post_code": "",
                        "medical_bus_phone": "",
                        "medical_mob_phone": "",
                        "medical_state_code": ""
                    },
                    {
                        "contact_name": "Dr S O'Bell",
                        "medical_townsub": "INALA",
                        "medical_home_phone": "073874 6589",
                        "medical_addr1": "19 Polaris Street",
                        "medical_country": "",
                        "medical_addr2": "",
                        "medical_mob_phone2": "0427203657",
                        "medical_addr3": "",
                        "medical_post_code": 4077,
                        "medical_bus_phone": "073564 8941",
                        "medical_mob_phone": "",
                        "medical_state_code": "QLD"
                    }
                ],
                "swimingLevel": "Treads water",
                "surname": "Bell",
                "given_name": "Eric James",
                "mud_fields": {
                    "Panadol/Aspirin": "",
                    "Allergies2": "",
                    "Allergies": "",
                    "Diabeties": "",
                    "Measles": "",
                    "Blood Group": "B",
                    "Preferred Hospital": "Mater",
                    "Private Health No.": "903600060139933770",
                    "Private Health Insur": "",
                    "Health Insurance Co": "",
                    "Consent Form": "",
                    "ADHD Medication": ""
                },
                "preferred_name": "Erica",
                "studcode": "0009097"
            },
            {
                "contacts": [
                    {
                        "contact_name": "Mr & Mrs L Davenport-Henderson",
                        "medical_townsub": "CHERMSIDE",
                        "medical_home_phone": "265 7741",
                        "medical_addr1": "11 Buruda Street",
                        "medical_country": "",
                        "medical_addr2": "",
                        "medical_mob_phone2": "",
                        "medical_addr3": "",
                        "medical_post_code": 4032,
                        "medical_bus_phone": "357 2251",
                        "medical_mob_phone": "0412016500",
                        "medical_state_code": "QLD"
                    }
                ],
                "swimingLevel": "",
                "surname": "Davenport-Henderson",
                "given_name": "Wayney Eric Henry Graham",
                "mud_fields": {
                    "Panadol/Aspirin": "",
                    "Allergies2": "",
                    "Allergies": "",
                    "Diabeties": "",
                    "Measles": "",
                    "Blood Group": "",
                    "Preferred Hospital": "",
                    "Private Health No.": "",
                    "Private Health Insur": "",
                    "Health Insurance Co": "",
                    "Consent Form": "",
                    "ADHD Medication": ""
                },
                "preferred_name": "Wayne",
                "studcode": "0009149"
            }
        ],
        "__tassversion": "01.054.0.000",
        "token": {
            "timestamp": "{ts '2022-07-20 10:54:04'}",
            "currentstatus": "current"
        }
    }
    ```

     when `studcode` is supplied
    ```javascript
    {
        "contacts": [
            {
                "contact_name": "Mrs P Clarke Second Line",
                "medical_townsub": "TOOWONG",
                "medical_home_phone": "3870 9987",
                "medical_addr1": "Gigi Lodge",
                "medical_country": "",
                "medical_addr2": "Unit 810",
                "medical_mob_phone2": "yeah yeah",
                "medical_addr3": "24 Augustus Street",
                "medical_post_code": 4066,
                "medical_bus_phone": "3201 1302",
                "medical_mob_phone": "0412016500",
                "medical_state_code": "QLD"
            },
            {
                "contact_name": "Mr E.& R Clark",
                "medical_townsub": "MUDGEERABA",
                "medical_home_phone": "3870 9987",
                "medical_addr1": "Somerset Park",
                "medical_country": "",
                "medical_addr2": "Unit 54",
                "medical_mob_phone2": "0412016500",
                "medical_addr3": "2-4 Langport Parade",
                "medical_post_code": 4213,
                "medical_bus_phone": "33201 1301",
                "medical_mob_phone": "",
                "medical_state_code": "QLD"
            },
            {
                "contact_name": "Mrs Nose.E. Neighbour",
                "medical_townsub": "STAFFORD",
                "medical_home_phone": "870 9987",
                "medical_addr1": "Alt Emergency Address",
                "medical_country": "",
                "medical_addr2": "34 Dunedoo St",
                "medical_mob_phone2": "0995 111 222",
                "medical_addr3": "",
                "medical_post_code": 4053,
                "medical_bus_phone": "201 1301",
                "medical_mob_phone": "0488067672",
                "medical_state_code": "TAS"
            }
        ],
        "swimingLevel": "Can float with assistance but will sink if unassisted",
        "surname": "Clark",
        "given_name": "Andrea Gracie Joan",
        "mud_fields": {
            "Panadol/Aspirin": "N",
            "Allergies2": "YES",
            "Private Health": "",
            "Text UD 15": "",
            "Text UD 14": "",
            "Allergies": "Y",
            "Diabeties": "",
            "Measles": "N",
            "Blood Group": "A+",
            "Preferred Hospital": "WE",
            "Private Health No.": "703600060139933770",
            "Private Health Insur": "N",
            "Health Insurance Co": "MP",
            "Consent Form": "ATH",
            "ADHD Medication": "RAK"
        },
        "stud_code": "0009130",
        "__tassversion": "01.054.0.000",
        "preferred_name": "Joanna",
        "token": {
            "timestamp": "{ts '2022-07-20 10:32:12'}",
            "studcode": "0009130"
        }
    }
    
    ```
 
* **Error Response:**

    `studcode` and `currentstatus` are both not supplied
    ```javascript
      "error": "studcode or currentstatus is required."
    ```

    `studcode` contains more than one student code
    ```javascript
      "error": "Only one studcode can be processed at a time."
    ```

    `studcode` does not exist in `currentstatus` student list
    ```javascript
      "error": "[studcode] is not a valid [currentstatus] student."
    ```

    `currentstatus` does not match 'current' or 'future' or 'past' or 'noncurrent'
    ```javascript
      "error": "[currentstatus] must be 'current' or 'future' or 'past' or 'noncurrent'."
    ```

* **Sample Parameters:**

    when `currentstatus` is supplied
  ```javascript
    {
      "currentstatus":"current"
    }
  ```

    when only `studcode` is supplied
  ```javascript
    {
      "studcode":"0009130"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getMedicalGeneral&appcode=API10&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getMedicalGeneral">
       <input type="hidden" name="appcode" value="API10">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```
