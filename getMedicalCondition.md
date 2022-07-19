**getMedicalCondition**
----
  Returns a structured student medical condition details data in JSON format.
  
* **Version History:**

  TASS v52.3 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Setup > Student Medical > Medical Conditions tab > View

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `studcode [string]` - Student Code

   `mcond_code [string]` - Medical Condition Code

   **Optional:**

   None

   **Conditional:**

   None

* **Success Response:**

    ```javascript
	{
		"attachment": [
					{
					"attach_id_filename": "51.txt",
					"mcond_code": "AST",
					"attach_id": "CDF58B76-BAE6-6C3B-5387B0C9BDB4FA41"
					}
		],
		"medication_notes": [
					{
					"note_date": "2018-04-30 00:00:00.0",
					"note_text": "she has trouble breathing apparently."
					},
					...
		],
		"general_note": "Problem processing any lactose, so a dairy free diet",
		"ud_area": {
					"Ventolin - Does the student xx": "Carries Ventolin with her at all times when she remembers xx",
					"Expiry date of medication": "01/03/2016",
					"Authorised staff member": "123456789012345678901234567890123456789012345678901234567890",
					"Dosage": "123456789012345678901234567890123456"
		},
		"date_of_last_occurence": "2019-08-15 00:00:00.0",
		"severe_condition": "Y",
		"medication_requirements": [
					{
						"med_detl": "Will usually alleviate attack but it may not.",
						"med_text": "Ridiculously long",
						"med_meth": "Uses a puffer."
					},
					{
						"med_detl": "Administer 4 puffs",
						"med_text": "Ventolin",
						"med_meth": "Puffer"
					}
		],
		"__tassversion": "01.053.3.000",
		"token": {
				"timestamp": "{ts '2021-01-19 16:03:56'}",
				"studcode": "0009130",
				"mcond_code": "AST"
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

* **Sample Parameters:**

  ```javascript
    {"studcode":"0009130","mcond_code":"AST"}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getMedicalCondition&appcode=API10&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getMedicalCondition">
       <input type="hidden" name="appcode" value="API10">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```
