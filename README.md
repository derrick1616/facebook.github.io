<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Login</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f2f5;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .container {
      max-width: 400px;
      padding: 20px;
      background-color: #fff;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    }
    .form-group {
      margin-bottom: 20px;
    }
    .form-group label {
      display: block;
      margin-bottom: 5px;
      font-weight: bold;
    }
    .form-group input {
      width: 100%;
      padding: 10px;
      border: 1px solid #dddfe2;
      border-radius: 4px;
      font-size: 16px;
    }
    .form-group button {
      width: 100%;
      padding: 12px;
      background-color: #1877f2;
      color: #fff;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      cursor: pointer;
    }
    .form-group button:hover {
      background-color: #166fe5;
    }
    .form-group .signup-link {
      margin-top: 10px;
      text-align: center;
    }
    .form-group .signup-link a {
      color: #1877f2;
      text-decoration: none;
    }
    .form-group .signup-link a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <div class="container">
    <img src="facebook_logo.png" alt="Facebook Logo" style="display: block; margin: 0 auto; width: 100px; margin-bottom: 20px;">
    <h2 style="text-align: center; margin-bottom: 30px;">Log into Facebook</h2>
    <form action="login.php" method="POST">
      <div class="form-group">
        <label for="email">Email or Phone</label>
        <input type="text" id="email" name="email" required>
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input type="password" id="password" name="password" required>
      </div>
      <div class="form-group">
        <button type="submit">Log In</button>
      </div>
    </form>
    <div class="form-group signup-link">
      <a href="register.html">Create New Account</a> | <a href="#">Forgot Password?</a>
    </div>
  </div>
</body>
</html>
