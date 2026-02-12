<!DOCTYPE html>
<html>
<head>
  <title>Login</title>
</head>
<body>

<h2>Login</h2>

<input type="text" id="loginUser" placeholder="Username"><br><br>
<input type="password" id="loginPass" placeholder="Password"><br><br>
<button onclick="login()">Login</button>

<p id="msg"></p>

<script>
function login() {
  let user = document.getElementById("loginUser").value;
  let pass = document.getElementById("loginPass").value;

  let savedUser = localStorage.getItem("username");
  let savedPass = localStorage.getItem("password");

  if (user === savedUser && pass === savedPass) {
    document.getElementById("msg").innerHTML = "Login successful 🎉";
  } else {
    document.getElementById("msg").innerHTML = "Invalid username or password ❌";
  }
}
</script>

</body>
</html>
