**getMedicalConditions**
----
  Returns an array of all structured student medical conditions details data in JSON format.
  
* **Version History:**

  TASS v52.3 - Method Added

  TASS v54.0 - Add a new conditional field `currentstatus`, change the required field `studcode` to a conditional field. Add new validations for `studcode` and `currentstatus`.

  TASS v56.5 - Add a new optional field `includemedication`, new return data `general_note`.
               Add a conditional return data `medication_requirements` within `medconditions` array

  TASS v57.12.150 - Add a new optional field `includemedicationnotes`, new return data `note_date` and `note_text`.
               Add a conditional return data `medication_notes` within `medconditions` array

* **Version:**

  3

* **Permission:**

  Medical Setup > Student Medical > Medical Conditions tab > View

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   None

   **Optional:**

    `includemedication [boolean]` - Must be 'true' or 'false'. If it is not provided, treat it as 'false'.

    `includemedicationnotes [boolean]` - Must be 'true' or 'false'. If it is not provided, treat it as 'false'.

   **Conditional:**

    `currentstatus [string]` - Required if `studcode` is not supplied. Must be 'current' or 'future' or 'past' or 'noncurrent'.

    `studcode [string]` - Required if `currentstatus` is not supplied. Contains Only One Student Code if supplied.

* **Success Response:**

    when only `studcode` is supplied
    ```javascript
      {
        "data": [
            {
              "last_occ_date": "2018-01-30 00:00:00.0",
              "mcond_desc": "Accident",
              "mcond_code": "ACC",
              "severe_ind": "N",
              "general_note": "Must not have running exercise"
            },
            {
              "last_occ_date": "2016-01-31 00:00:00.0",
              "mcond_desc": "Anaphylaxis",
              "mcond_code": "ANA",
              "severe_ind": "Y",
              "general_note": "Has suffered Anaphylaxis since birth."
            }
        ],
        "__tassversion": "01.057.8.200",
        "token": {
            "timestamp": "{ts '2021-01-19 16:29:38'}",
            "studcode": "0009130"
        }
      }
    ```

    when only `currentstatus` is supplied
    ```javascript
    {
        "data":[
            {
                "studcode":"0009130",
                "medconditions":[
                    {
                        "last_occ_date":"2018-01-30 00:00:00.0",
                        "mcond_desc":"Accident",
                        "mcond_code":"ACC",
                        "severe_ind":"N",
                        "general_note": "Must not have running exercise"
                    },
                    {
                        "last_occ_date":"2016-01-31 00:00:00.0",
                        "mcond_desc":"Anaphylaxis",
                        "mcond_code":"ANA",
                        "severe_ind":"Y",
                        "general_note": "Has suffered Anaphylaxis since birth."
                    }
                ]
            },
            {
                "studcode":"0009134",
                "medconditions":[
                    {
                        "last_occ_date":"",
                        "mcond_desc":"Asthma",
                        "mcond_code":"AST",
                        "severe_ind":"N",
                        "general_note": "Asthma requires monitoring.Ventoline Required",
                    }
                ]
            }
        ],
        "__tassversion":"01.057.8.200",
        "token":{
            "timestamp":"{ts '2020-11-11 14:01:03'}",
            "currentstatus":"current"
        }
    }
    ```
    when `currentstatus` or `studcode` is supplied and `includemedication` is supplied as 'true'
    ```javascript
    {
      "data": [
        {
            "studcode":"0009130",
            "medconditions":[
                {
                    "last_occ_date":"2018-01-30 00:00:00.0",
                    "mcond_desc": "Anaphylaxis",
                    "general_note": "Has suffered Anaphylaxis since birth.",
                    "mcond_code": "ANA",
                    "severe_ind": "Y",
                    "medication_requirements": [
                        {
                            "med_detl": "To reduce allergic response",
                            "med_text": "Epinephrine",
                            "med_meth": "Injection"
                        },
                        {
                            "med_detl": "To help you breathe",
                            "med_text": "Oxygen bag",
                            "med_meth": "Bag valve mask"
                        }
                    ]
                }
            ]
        }
      ]
    }
    ```
    when `currentstatus` or `studcode` is supplied and `includemedicationnotes` is supplied as 'true'
    ```javascript
    {
      "data": [
        {
            "studcode":"0009158",
            "medconditions":[
                {
                    "last_occ_date":"2021-12-03 00:00:00.0",
                    "mcond_desc": "Migraine",
                    "general_note": "James is prone to Migraines, generally introduced by sweet items or high level of stress.",
                    "mcond_code": "MIG",
                    "severe_ind": "Y",
                    "medication_notes": [
                        {
                            "note_date": "2021-12-28",
                            "note_text": "Needs to have the Neurofen as soon as symtoms start otherwise chances of getting severe migraines is likely."
                        }
                    ]
                }
            ]
        }
      ]
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

    `includemedication` does not match 'true' or 'fasle'
    ```javascript
      "error": "[includemedication] must be 'true' or 'false'."
    ```  

    `includemedicationnotes` does not match 'true' or 'fasle'
    ```javascript
      "error": "[includemedicationnotes] must be 'true' or 'false'."
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

    when `currentstatus` or `studcode` is supplied and `includemedication` is supplied
  ```javascript
    {
      "currentstatus":"current"
      ,"includemedication":"true"
    }
  ```

    when `currentstatus` or `studcode` supplied and `includemedicationnotes` is supplied
  ```javascript
    {
      "currentstatus":"current"
      ,"includemedicationnotes":"true"
    }
  ```   

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getMedicalConditions&appcode=API10&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getMedicalConditions">
       <input type="hidden" name="appcode" value="API10">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```
