# WAD-LAB-EXP.2
2.html
<html>
<head>
<title>Student Registration</title>
</head>
<body>
<div align="Left">
<h1>Student Registration Portal</h1>
<form id="xyz">
<label for="name">Enter name: </label>
<input type="text" id="name" /><br /><hr />
<label for="dob">Select date of birth: </label>
<input type="date" id="dob" /><br /><hr />
<label for="branch">Enter branch: </label>
<input type="text" id="branch" /><br /><hr />
<label for="semester">Select Semester: </label>
<input type="number" id="semester" max="8" min="0" /><br /><hr />
<label for="doj">Select date of joining: </label>
<input type="date" id="doj" /><br /><hr />
<label for="university">Enter University Name: </label>
<input type="text" id="university" /><br /><hr />
<label for="mobile">Enter mobile number: </label>
<input type="text" id="mobile" /><br /><hr />
<label for="email_add">Enter email: </label>
<input type="email" id="email_add" /><br /><hr />
</form>
<button onclick="validate()">Submit</button>
<p>
Result: <span id="result"></span>
</p>
</div>
</body>
<script>
function validate() 
{
var result_text = document.getElementById("result");
var dob = document.getElementById("dob").value;
var birth_year = parseInt(dob.substring(0, 4));
var doj = document.getElementById("doj").value;
var join_year = parseInt(doj.substring(0,4));
if (join_year - birth_year < 17) 
{
result_text.innerHTML = "Too young to have started college!"			
return;			
}
var branch = document.getElementById("branch").value;
if (branch.search(/(CSE|ECE|ME|CE|EEE|BCA|MCA)/i) == -1) 
{
result_text.innerHTML = "Invalid branch!";
return;			
}
var mobile_no = document.getElementById("mobile").value;
if (mobile_no.search(/^[0-9]+$/) == -1 || mobile_no.length != 10) 
{
result_text.innerHTML = "Invalid mobile number!";
return;			
}
var email = document.getElementById("email_add").value;			
if (email.search(/^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/) == -1) 
{
result_text.innerHTML = "Invalid email ID";			
return;			
}
alert('Successfully transmitted data!');
result_text.innerHTML = "Success!";		
}
</script>
</html>
