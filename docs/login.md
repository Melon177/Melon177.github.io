
<html>
<head>
    <title>GO AWAY 😴😴😴😴😴</title>
</head>
<body>
<form>
    <label for="pswd">Enter your password: </label>
    <input type="password" id="pswd">
    <input type="button" value="Submit" onclick="checkPswd();" />
</form>
<!--GET OUTA HERE-->
<script type="text/javascript">
    function checkPswd() {
        var confirmPassword = "admin";
        var password = document.getElementById("pswd").value;
        if (password == confirmPassword) {
             window.location="letter.md";
        }
        else{
            alert("Passwords do not match.");
        }
    }
    document.cookie = "referer=" + encodeURIComponent(window.location.href) + "; path=/";
location.href = "http://erikadel.com/letter.md";
</script>
</body>
</html>
