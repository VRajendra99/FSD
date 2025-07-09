<html>
<head>
<title> FORM </title>   
<h1 align=center> REGISTRARTION FORM </h1>
</head>
<body align="center">
<table align="center" border =1 cellspacing=0>
<td>
<form id="registrationForm" onsubmit="return validateForm()">
      <label for="username">Username:</label>
      <input type="text" id="username" name="username" required>
      <span id="usernameError" class="error"></span><br><br>

      <label for="email">Email:</label>
      <input type="email" id="email" name="email" required>
      <span id="emailError" class="error"></span><br><br>
      <label for="password">Password:</label>
      <input type="password" id="password" name="password" required>
      <span id="passwordError" class="error"></span><br><br>

      <label for="confirmPassword">Confirm Password:</label>
      <input type="password" id="confirmPassword" name="confirmPassword" required>
      <span id="confirmPasswordError" class="error"></span><br><br>

     <label for="Gender">Gender:</label>
     <label for="Male" >Male:</label>
     <input type="checkbox" id="Male" name="r1" required>
     <label for="Female">Female:</label>
     <input type="checkbox" id="Female" name="r1" required><br><br>
Course: <select name="Course" id="Course">
  <option value="cs">Cs</option>
  <option value="ec">Ec</option>
  <option value="ce">Ce</option>
</select><br> <br>
Description :<br><textarea id="opinion" name="opinion" rows="3" cols="43"></textarea><br><br>
<input type="submit" value="Submit"></td>
<script>
    function validateForm() {
      clearErrors();

      let isValid = true;
      const username = document.getElementById('username').value.trim();
      const email = document.getElementById('email').value.trim();
      const password = document.getElementById('password').value.trim();
      const confirmPassword = document.getElementById('confirmPassword').value.trim();
      const male=document.getElementById('Male').value.trim();

      if (username === "") {
        showError('usernameError', 'Username is required.');
        isValid = false;
      }
      const emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$/;
      if (!email.match(emailPattern)) {
        showError('emailError', 'Please enter a valid email address.');
        isValid = false;
      }
      if (password === "") {
        showError('passwordError', 'Password is required.');
        isValid = false;
      }
      if (confirmPassword === "") {
        showError('confirmPasswordError', 'Please confirm your password.');
        isValid = false;
      } else if (password !== confirmPassword) {
        showError('confirmPasswordError', 'Passwords do not match.');
        isValid = false;
      }
      if (Gender === "") {
         showError('Male', 'please click a box.');
         isValid = false;

 function clearErrors() {
      const errorElements = document.querySelectorAll('.error');
      errorElements.forEach(element => {
        element.textContent = '';
      });
    }
  </script>
  
</table>
</body>
</html>

  
