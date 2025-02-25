<!DOCTYPE html>
<html>
<head>
<style>

fieldset label {
    display: flex;
    align-items: center;
    margin: 8px 0;
}

input[type="checkbox"], 
input[type="radio"] {
    margin: 0 10px 0 0;
    width: auto;
    display: inline-block;
}

.checkbox-group,
.radio-group {
    text-align: left;
    margin-left: 20px;
}

body {
  background-image: url('https://i.imgur.com/M2CKpMF.jpeg');
  background-repeat: no-repeat;
  background-attachment: fixed;  
  background-size: cover;
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  margin: 0;
}
.container {
  background: rgba(255, 255, 255, 0.9);
  padding: 20px;
  border-radius: 10px;
  box-shadow:  0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  max-width: 600px;
}
input {
  display: block;
  width: calc(100% - 20px);
  margin: 10px auto;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
button {
  background-color: #4CAF50;
  color: white;
  padding: 10px 15px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
  margin-top: 10px;
}
button:hover {
  background-color: #45a049;
}
.clear {
  background-color: #f44336;
}
.clear:hover {
  background-color: #d32f2f;
}
.hidden {
  display: none;
}
fieldset {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  margin: 10px 0;
  text-align: left;
}
legend {
  font-weight: bold;
  color: #a7835a;
  padding: 0 10px;
}
input[readonly], input[disabled] {
  background-color: #f0f0f0;
  color: #888;
  cursor: not-allowed;
}
textarea {
  width: calc(100% - 20px);
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  resize: vertical;
}
select {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: white;
  font-family: Arial, sans-serif;
}
</style>
<script>

function clearFields() {
  document.getElementById('username').value = '';
  document.getElementById('password').value = '';
  document.getElementById('loginFields').classList.remove('hidden');
  document.getElementById('additionalFields').classList.add('hidden');
}
function showAdditionalFields() {
  const username = document.getElementById('username').value;
  const password = document.getElementById('password').value;

  if (username && password) {
    document.getElementById('loginFields').classList.add('hidden');
    document.getElementById('additionalFields').classList.remove('hidden');
  } else {
    alert('Please enter both username and password.');
  }
}
</script>
</head>
<body>

<!-- Login Fields -->
<div class="container" id="loginFields">
  <h1>WELCOME</h1>
  <legend>1. Password and Box Control</legend>
  <input type="text" id="username" placeholder="Enter Username">
  <input type="password" id="password" placeholder="Enter Password">
  <button type="button" onclick="showAdditionalFields()">Login</button>
  <button type="button" class="clear" onclick="clearFields()">Clear All</button>
</div>

<div class="container hidden" id="additionalFields">
  
  <!-- Checkboxes -->
  <fieldset>
    <legend>2. Check Boxes</legend>
    <p>What are the favorite things you love to do?</p>
    <div class="checkbox-group">
      <label><input type="checkbox" name="hobby" value="Reading"> Reading</label>
      <label><input type="checkbox" name="hobby" value="Watching"> Watching</label>
      <label><input type="checkbox" name="hobby" value="Listening to Music"> Listening to Music</label>
      <label><input type="checkbox" name="hobby" value="Playing Online Games"> Playing Online Games</label>
      <label><input type="checkbox" name="hobby" value="Playing Sports"> Playing Sports</label>
      <label>
        <input type="checkbox" name="hobby" value="Other"> Other: 
        <input type="text" placeholder="Please specify" style="width: 60%; margin-left: 10px;">
      </label>
    </div>
  </fieldset>

  <!-- Option Buttons -->
  <fieldset>
    <legend>3. Option Buttons</legend>
    <div class="radio-group">
    <label for="you">What is your marital status?</label>
      <label><input type="radio" name="maritalStatus" value="Single"> Single, never married</label>
      <label><input type="radio" name="maritalStatus" value="Married"> Married or domestic partnership</label>
      <label><input type="radio" name="maritalStatus" value="Widowed"> Widowed</label>
      <label><input type="radio" name="maritalStatus" value="Divorced"> Divorced</label>
      <label><input type="radio" name="maritalStatus" value="Separated"> Separated</label>
    </div>
  </fieldset>

  <!-- Text Area -->
  <fieldset>
    <legend>4. Text Area Controls</legend>
    <label for="you">Tell me about yourself:</label>
    <textarea placeholder="Write something about yourself"></textarea>
  </fieldset>

  <!-- Optgroup Control -->
  <fieldset>
    <legend>5. OPTGROUP Tag</legend>
    <label for="color">What is your favorite color?</label>
    <select>
      <option value="Red">Red</option>
      <option value="Blue">Blue</option>
      <option value="Green">Green</option>
      <option value="Yellow">Yellow</option>
      <option value="Orange">Orange</option>
      <option value="Purple">Purple</option>
      <option value="Pink">Pink</option>
      <option value="Black">Black</option>
      <option value="White">White</option>
      <option value="Brown">Brown</option>
    </select>
  </fieldset>

  <!-- Personal Information -->
  <fieldset>
    <legend>6. FIELDSET and LEGEND Tags with READONLY and DISABLED Attributes</legend>
    <style>
        .personal-info-label {
          display: block;
          text-align: center;
          font-weight: bold;
        }
      </style>
    <label for="name" class="personal-info-label">MY PERSONAL INFORMATION</label>
    <label for="name">My name:</label>
    <input type="text" id="name" name="name" value="Ianna Erin Marquez" readonly>
    <label for="province-info">My province:</label>
    <input type="text" id="province-info" name="province-info" value="don't have one! I'm a Manila girlie :)" disabled>
    <label for="color">My Favorite Color:</label>
    <input type="text" id="color" name="color" placeholder="black, sometimes pink and yellow" readonly>
    <label>Sex:</label>
    <div class="radio-group">
      <label><input type="radio" name="sex" value="male" disabled> Male</label>
      <label><input type="radio" name="sex" value="female" checked disabled> Female</label>
    </div>
  </fieldset>

  <script>
    function showThankYouMessage(event) {
      event.preventDefault(); 

      document.getElementById('additionalFields').style.display = 'none';
  
      const thankYouMessage = document.createElement('div');
      thankYouMessage.innerHTML = `
        <div class="container">
          <h2>Thank You!</h2>
          <p>Your submission has been received.</p>
        </div>
      `;
      document.body.appendChild(thankYouMessage);
    }
    </script>
    

    <form id="creditCardForm" onsubmit="showThankYouMessage(event)">
      <fieldset>
        <legend>7. Submit Query and Reset Buttons</legend>
        <style>
          .appli-label {
            display: block;
            text-align: center;
            font-weight: bold;
          }
        </style>
      <label for="name" class="appli-label">CREDIT CARD APPLICATION PRE-QUALIFYING SURVEY</label>
        <label for="name">Enter Name:</label>
        <input type="text" id="name" name="name" placeholder="Enter your name">
        <label for="age">Age:</label>
        <input type="text" id="age" name="age" placeholder="Enter your age">
        <label for="profession">Profession:</label>
        <input type="text" id="profession" name="profession" placeholder="Enter your job">
        <label for="monthly-salary">Monthly Salary:</label>
        <select id="monthly-salary" name="monthly-salary">
          <option value="" disabled selected>Select your monthly salary</option>
          <option value="0-10000">₱0 - ₱10,000</option>
          <option value="10001-20000">₱10,001 - ₱20,000</option>
          <option value="20001-30000">₱20,001 - ₱30,000</option>
          <option value="30001-40000">₱30,001 - ₱40,000</option>
          <option value="40001-50000">₱40,001 - ₱50,000</option>
          <option value="50001+">₱50,001 and above</option>
        </select>
      </fieldset>
      <button type="reset">Reset Credit Card Application</button>
      <button type="submit">Submit Query</button>
    </form>
    
</div>
</body>
</html>
