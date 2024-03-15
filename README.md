<!DOCTYPE html>
<html>
 <head>
 <title>Sign up to {this}</title>
 <link rel="stylesheet" type="text/css" href="pgm1.css" />
 <script type="text/javascript" src="pgm1.js"></script>
 </head>
 <body>
 <form method="post" target="#" onsubmit="return validate()">
 <h1>Sign up to {this}</h1>
 <p>To be able to use all features of {this} you will require an account. The form below will allow 
you to create a new account if you don't have one yet.</p>
 Name<br>
 <input type="text" name="name"><br>
 Email<br>
<input type="text" name="email"><br>
 Retype email<br>
 <input type="text" name="retype_email"><br>
 Create a password<br>
<input type="password" name="password"><br>
 Retype password<br>
<input type="password" name="retype_password"><br>
 <label>
 <input type="checkbox" name="terms">By signing up to {this} you agree to your
 <a href="#service">Terms of Service</a> and <a href="#policy">Privacy Policy</a>
 </label>
 <div class="button">
 <input type="submit" class="button" value="Set Up Account">
 </div>
 </form>
</body>
</html>
Pgm1.js
function validate() { 
var result = "";
result += validateName(); 
result += validateEmail();
result += validatePassword();
result += validateTerms();
if(result != "")
{
alert("Validation Result:\n\n" + result);
}
else
{
alert("Congrats!!! Your account Created.");
}
 }
function validateName() {
var name = document.getElementsByName("name")[0].value;
if (name.length <= 2)
return "Name should be at least three characters.\n";
return "";
}
function validatePassword() {
var password = valueOf("password");
var retype = valueOf("retype_password");
if (password.length <= 5) 
return "Password should be at least 6 characters.\n";
if (password != retype) 
return "Passwords do not match.\n";
return "";
}
function validateEmail() {
var email = valueOf("email");
var retype = valueOf("retype_email");
if (email.indexOf('@') == -1) 
return "Email should be a valid address.\n";
if (email != retype)
return "Email addresses do not match.\n";
return "";
}
function validateTerms() {
var terms = document.getElementsByName("terms")[0];
if (!terms.checked)
return "Please accept the Terms of Service and Privacy Policy";
return "";
}
function valueOf(name) {
return document.getElementsByName(name)[0].value;
}
Pgm1.css
body {
 font-family: Verdana, sans-serif;
}
input {
border-radius: 5px;
padding: 5px;
}
div.button {
text-align: right;
}
a {
text-decoration: none;
color: #e51;
}
form { 
width: 480px; 
margin: auto;
padding: 5px; 
border: solid black 1px;
border-radius: 5px; 
box-shadow: 5px 5px 2px #888;
}
