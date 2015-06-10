
# PumpCaptcha - Very simple captcha library for php/gd

### Required
-PHP5
-GD
-.ttf TrueType Font file

### example

```
<?php session_start(); ?><html>
<head>
    <script type="text/javascript" src="http://code.jquery.com/jquery-2.1.4.js"></script>
</head>
<body>
<form method="post">
  captcha:<br />
  <input type="text" name="captcha_text">
  <input type="submit"><br />
  <img src="pumpcaptcha.php" id="captcha_image"><br />
  <input type="button" value="reload" onclick="src=$('#captcha_image').attr('src'); $('#captcha_image').attr('src', src + '?' + new Date().getTime());"><br />
</form>
<br />
<?php
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
  if (strtolower($_POST['captcha_text']) == strtolower($_SESSION['pumpcaptcha_text'])) {
    echo 'captcha OK';
  } else {
    echo 'captcha NG';
  }
}
?>
</body>
</html>
```
