Host URL:  http://localhost:8080/
Base URL1: /api/
Base URL: /api/user/
----------------------------------------------------------------------------------------------0. During Start of application
API 1.1: Force Update
URL:  Base URL +forceUpdate
Request type : POST
Request JSON
{"version":"1.2.3"}
 
Response JSON
Success
{"message":"Please update to a new version","status":"success",”update”:”1”}
{"message":"Already updated","status":"success",”update”:”0”}

 
Failure
{"message":"Something went wrong","status":"failed"}


----------------------------------------------------------------------------------------------------------------------------1. Splash Screen
API 1: Registration
URL:  Base URL + register
Request type : POST
Request JSON
{"email":"shishir.cse@gmail.com","phone":"919899999999","name":"Shishir Gupta", "password":"123456"}
 
Response JSON
Success
{"message":"Registration Successful","status":"success"}
 
Failure
{"message":"Registration Failed","status":"failed"}

API 1.1: Login
URL:  Base URL + login
Request type : POST
Request JSON
{"email":"shishir.cse@gmail.com","password":"123456","gcm_token":"123456"}
 
Response JSON
Success
{"message":"Login Successful","status":"success", "id":"1", "token": "adosjadiojsdoiasjdioajoia"}
 
Failure
{"message":"Login Failed","status":"failed"}


API 1.2: Forgot password
URL:  Base URL + forgotPassword
Request type : POST
Request JSON
{"email":"shishir.cse@gmail.com"}
 
Response JSON
Success
{"message":"Your password has been sent to your email","status":"success","token":"adosjadiojsdoiasjdioajoia"}
 
Failure
{"message":"Something went wrong","status":"failed"}

API 1.3: Change password
URL:  Base URL + changePassword
Request type : POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia","current_password":"123456","new_password":"123456"}
 
Response JSON
Success
{"message":"Password change successful","status":"success"}
 
Failure
{"message":"Something went wrong","status":"failed"}
Token Invalid
{"message":"Authentication Failure","status":"failed"}


API 1.4: Logout
URL:  Base URL + logout
Request type : POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia"}
 
Response JSON
Success
{"message":"Logout successful","status":"success"}
 
Failure
{"message":"Something went wrong","status":"failed"}
Token Invalid
{"message":"Authentication Failure","status":"failed"}

API 1.5: Update profile
URL:  Base URL + update
Request type : POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia",”name”:”ShishirGupta”,”photo”:”filepath”,”phone”:”8826003394”}
 
Response JSON
Success
{"message":"Update successful","status":"success"}
 
Failure
{"message":"Something went wrong","status":"failed"}
Token Invalid
{"message":"Authentication Failure","status":"failed"}

API 1.5: Get profile
URL:  Base URL + getProfile
Request type : POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia"}
 
Response JSON
Success
{"message":"Get profile successful","status":"success",”first_name”:”Shishir”,”last_name”:”Gupta”,”photo”:”url of photo”,”phone”:”8826003394”,”email”:”shishir.cse@gmail.com”}
 
Failure
{"message":"Something went wrong","status":"failed"}
Token Invalid
{"message":"Authentication Failure","status":"failed"}





 
----------------------------------------------------------------------------------------------------------------------------
2. Language selection screen & Home screen
 
API 2: Master data
 
URL:  Base URL + masterdata
Request Type: POST

Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia","last_updated":"0}
 
Response JSON
Success
 
{"message": "Get master data successfull",
"status": "success",
"languages": [{"name": "Java",
"topics": ["Exception Handling","Inheritance"],
"logo": "http:\/\/www.csuchico.edu\/itss\/images\/java-logo.png"},
{"name": "Android",
"topics": ["Activity","Fragment"],
"logo": "http:\/\/www.csuchico.edu\/itss\/images\/java-logo.png"}],
"levels": [{"level_id": "1","name": "Easy"},
 {"level_id": "2","name": "Medium"},
 {"level_id": "3","name": "Hard"}]
}
 
 
Failure
 
{"message":"Masterdata Failed","status":"failed"}
 
 
 
 
 
----------------------------------------------------------------------------------------------------------------------------API 3: Questions/Programs/Tests Data
URL:  Base URL + data
 
Request Type: POST
 
Request JSON
 
{"id":"1","token":"adosjadiojsdoiasjdioajoia","phone":"919899999999","pageno":"0","pagesize":"30","levels":["Easy","Medium","Hard"],"languages":[{"name":"Java","topics":["Exception Handling","Inheritance"]},{"name":"Android","topics":["Activity","Fragment"]}]}
Note: if pageno and pagesize both will 0 in request then server will send all data. 
 
Response JSON
Success
 
{"message":"sample","status":"success","questions":[{"id":"12","title":"What is Activity?","language":"Android","topic":"activity","level":"Easy","options":["It is a screen in Android","It looks like Intent","It is like a Fragment","All of the above"],"answer":"It is a screen in Android","reason":"Activity is a screen which is displayed to user in Android"},{"id":"14","title":"What is Intent?","language":"Android","topic":"intent","level":"Hard","options":["It is a screen in Android","It looks like Intent","It is like a Fragment","All of the above"],"answer":"It is a screen in Android","reason":"Activity is a screen which is displayed to user in Android"}],"programs":[{"id":"23","title":"Reverse a string","language":"Java","topic":"String","level":"Hard","code":"\nimport java.util.*;\nclass ReverseString {\n   public static void main(String args[]) {\n	  String original, reverse = \"\";\n  	Scanner in = new Scanner(System.in);\n  	System.out.println(\"Enter a string to reverse\");\n  	original = in.nextLine();\n  	int length = original.length();\n  	for ( int i = length - 1 ; i >= 0 ; i-- )\n     	reverse = reverse + original.charAt(i);\n  	System.out.println(\"Reverse of entered string is: \"+reverse);\n   }\n}\n"},{"id":"26","title":"Check whether string is palindrome or not","language":"Java","topic":"String","level":"Hard","code":"\nimport java.util.*;\nclass ReverseString {\n   public static void main(String args[]) {\n  	String original, reverse = \"\";\n  	Scanner in = new Scanner(System.in);\n  	System.out.println(\"Enter a string to reverse\");\n  	original = in.nextLine();\n  	int length = original.length();\n  	for ( int i = length - 1 ; i >= 0 ; i-- )\n     	reverse = reverse + original.charAt(i);\n  	System.out.println(\"Reverse of entered string is: \"+reverse);\n   }\n}\n"}],"tests":[{"title":"20 questions in 5 minutes","level":"Easy","time":"5000","noofquestions":"20","languages":[{"name":"Java","topics":["Exception Handling","Inheritance"]},{"name":"Android","topics":["Activity","Fragment"]}]},{"title":"20 questions in 5 minutes","level":"Hard","time":"5000","noofquestions":"20","languages":[{"name":"Java","topics":["Exception Handling","Inheritance"]},{"name":"Android","topics":["Activity","Fragment"]}]},{"title":"20 questions in 5 minutes","level":"Medium","time":"5000","noofquestions":"20","languages":[{"name":"Java","topics":["Exception Handling","Inheritance"]},{"name":"android","topics":["Activity","Fragment"]}]}]}
 
Failure
 
{"message":"Data Failed","status":"failed"}
 
---------------------------------------------------------------------------------------------------------------------------- 
3. Shortlist Screen
 
API 4: Shortlist data
URL: Base URL + shortlistdata
Request type: POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia","phone":"918999999999","pageno":"0","pagesize":"30"}
Note: if pageno and pagesize both will 0 in request then server will send all data.
 
Response JSON
Success
{"status":"success","message":"any message","questions":[{"id":"56","title":"What is Activity?","language":"Android","topic":"activity","level":"Easy","options":["It is a screen in Android","It looks like Intent","It is like a Fragment","All of the above"],"answer":"It is a screen in Android","reason":"Activity is a screen which is displayed to user in Android"},{"id":"36","title":"What is Intent?","language":"Android","topic":"intent","level":"Hard","options":["It is a screen in Android","It looks like Intent","It is like a Fragment","All of the above"],"answer":"It is a screen in Android","reason":"Activity is a screen which is displayed to user in Android"}],"programs":[{"id":"31","title":"Reverse a string","language":"Java","topic":"String","level":"Hard","code":"\nimport java.util.*;\nclass ReverseString {\n   public static void main(String args[]) {\n  	String original, reverse = \"\";\n  	Scanner in = new Scanner(System.in);\n  	System.out.println(\"Enter a string to reverse\");\n  	original = in.nextLine();\n  	int length = original.length();\n  	for ( int i = length - 1 ; i >= 0 ; i-- )\n     	reverse = reverse + original.charAt(i);\n  	System.out.println(\"Reverse of entered string is: \"+reverse);\n   }\n}\n"},{"id":"21","title":"Check whether string is palindrome or not","language":"Java","topic":"String","level":"Hard","code":"\nimport java.util.*;\nclass ReverseString {\n   public static void main(String args[]) {\n  	String original, reverse = \"\";\n  	Scanner in = new Scanner(System.in);\n  	System.out.println(\"Enter a string to reverse\");\n  	original = in.nextLine();\n  	int length = original.length();\n  	for ( int i = length - 1 ; i >= 0 ; i-- )\n     	reverse = reverse + original.charAt(i);\n  	System.out.println(\"Reverse of entered string is: \"+reverse);\n   }\n}\n"}]}
 
Failure
 
{"message":"Shorltist Failed","status":"failed"}
 
---------------------------------------------------------------------------------------------------------------------------- 
4. Report Screen
 
 
API 5: Report data
URL: Base URL + report
Request type: POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia","phone":"919899999999","pageno":"0","pagesize":"30"}
Note: if pageno and pagesize both will 0 in request then server will send all data.
 
Response JSON
{"message":"Sample message","status":"success/failure","test_reports":[{"title":"20 questions in 5 minutes","level":"Hard","time":"5000","noofquestions":"20","attemptedquestions":"19","correctquestions":"15","incorrectquestions":"4","attemptedtime":"4500","languages":[{"name":"Java","topics":["Exception Handling","Inheritance"]},{"name":"Android","topics":["Activity","Fragment"]}]},{"title":"20 questions in 20 minutes","level":"Easy","time":"20000","noofquestions":"20","attemptedquestions":"15","correctquestions":"15","incorrectquestions":"0","attemptedtime":"1000","languages":[{"name":"Java","topics":["Exception Handling","Inheritance"]},{"name":"Android","topics":["Activity","Fragment"]}]},{"title":"50 questions in 25 minutes","level":"Medium","time":"25000","noofquestions":"50","attemptedquestions":"40","correctquestions":"39","incorrectquestions":"1","attemptedtime":"25000","languages":[{"name":"Java","topics":["Exception Handling","Inheritance"]},{"name":"Android","topics":["Activity","Fragment"]}]}]}
 
 
 
Failure
 
{"message":"Report Failed","status":"failed"}
 
---------------------------------------------------------------------------------------------------------------------------- 
5. Home screen : Shortlist Question/Program
 
API 6: Shortlist question
URL: Base URL + shortlist
Request type : POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia",,"phone":"919899999999","id":"34","select":"true/false", “type”:”0”}
 
Response JSON
Success
{"message":"This question is added/removed in your shortlist successfully","status":"success"}
 
Failure
{"message":"Shortlist Failed","status":"failed"}
 
 
---------------------------------------------------------------------------------------------------------------------------- 
API 7: Shortlist program
URL: Base URL + shortlist
Request type: POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia",,"phone":"919899999999","id":"14","select":"true/false", “type”:”1”}
 
Response JSON
Success
{"message":"This program is added/removed in your shortlist successfully","status":"success"}
 
Failure
{"message":"Shortlist Failed","status":"failed"}
 
 
----------------------------------------------------------------------------------------------------------------------------
6. Home screen -> Test Tab : Start Test
 
API 8:  Test Launch
URL : Base URL + testlaunch
Request type : POST
Request JSON
{"id":"1","token":"adosjadiojsdoiasjdioajoia",,"id":"786","phone":"919899999999", "languages":[{"name":"Java","topics":["Exception Handling","Inheritance"]},{"name":"Android","topics":["Activity","Fragment"]}]}
 
Response JSON
Success
{"message":"Sample Message","status":"success/failure","questions":[{"id":"16","title":"What is Activity?","language":"Android","topic":"activity","level":"Easy","options":["It is a screen in Android","It looks like Intent","It is like a Fragment","All of the above"],"answer":"It is a screen in Android","reason":"Activity is a screen which is displayed to user in Android"},{"id":"19","title":"What is Intent?","language":"Android","topic":"intent","level":"Easy","options":["It is a screen in Android","It looks like Intent","It is like a Fragment","All of the above"],"answer":"It is a screen in Android","reason":"Activity is a screen which is displayed to user in Android"}]}
 
Failure
{"message":"Test launch Failed","status":"failed"}
 
 
 
 
 
 
 
 
 
 


