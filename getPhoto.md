**getPhoto**
----
  Returns a Photo of the specified User.
  
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
 
   `type [string]`

   `userid [string]`
   
   **Optional:**
 
   none

   **Conditional:**

   none

* **Success Response:**
	
	```javascript
	file_info: {
			image: [Base64 encoded image string],
			file_name: "0009068.jpg",
			mime_type: "image/jpeg"
		}
  ```
 
* **Error Response:**

	Required `[field_name]` not supplied
	```javascript
	__invalid: {
	  [field_name]: "field is required."
	}
	```
	
	`type` not one of 'E' or 'S'
	```javascript
	__invalid: {
	  "type": MUST BE 'E' or 'S'
	}
	```

* **Sample Parameters:**

  ```javascript
	type=S&userid=0009068
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=getPhoto&appcode=API10&company=10&v=1&token=nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc%3D
  ```
  
* **Sample POST:**

  ```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
	  <input type="hidden" name="method" value="getPhoto">
	  <input type="hidden" name="appcode" value="API10">
	  <input type="hidden" name="company" value="10">
	  <input type="hidden" name="v" value="1">
	  <textarea name="token">nb3QZurfruc1oEsFRAHeUFij5yf8M7mzO1vPmh7giNc=</textarea>
	</form>
  ```
