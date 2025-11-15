<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: #eef2f3;
            padding: 40px;
        }

        .login-box {
            width: 350px;
            margin: auto;
            background: #fff;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 0 15px rgba(0,0,0,0.15);
        }

        h2 {
            text-align: center;
            margin-bottom: 20px;
        }

        input[type="text"], 
        input[type="password"] {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 6px;
            transition: 0.2s;
        }

        input[type="text"]:focus, 
        input[type="password"]:focus {
            border-color: #007bff;
            box-shadow: 0 0 5px rgba(0,123,255,0.4);
        }

        button {
            width: 100%;
            padding: 12px;
            background: #007bff;
            border: none;
            color: white;
            border-radius: 6px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 10px;
        }

        button:hover {
            background: #0056b3;
        }

        .links {
            text-align: center;
            margin-top: 15px;
        }

        .links a {
            color: #007bff;
            text-decoration: none;
        }

        .links a:hover {
            text-decoration: underline;
        }

        .error {
            color: red;
            text-align: center;
            display: none;
            margin-bottom: 10px;
        }
    </style>
</head>

<body>

    <div class="login-box">
        <h2>Login</h2>

        <div id="errorMessage" class="error">Please fill all fields!</div>

        <form onsubmit="return validateForm()" action="dashboard.html" method="POST">
            <input type="text" name="username" id="username" placeholder="Enter Username">
            <input type="password" name="password" id="password" placeholder="Enter Password">
            <button type="submit">Login</button>
        </form>

        <div class="links">
            <a href="forgot-password.html">Forgot Password?</a><br>
            <a href="signup.html">Create an Account</a>
        </div>
    </div>

    <script>
        function validateForm() {
            let user = document.getElementById("username").value.trim();
            let pass = document.getElementById("password").value.trim();
            let errorBox = document.getElementById("errorMessage");

            if (user === "" || pass === "") {
                errorBox.style.display = "block";
                return false;
            }

            errorBox.style.display = "none";
            return true;
        }
    </script>

</body>
</html>
