<!DOCTYPE html>
<html>
<head>
<title>Copy Text to Clipboard</title>
</head>
<body>
<script>
function copyToClipboard(text) {
  var dummy = document.createElement("textarea");
  dummy.textContent = text;
  document.body.appendChild(dummy);
  dummy.select();
  document.execCommand("copy");
  document.body.removeChild(dummy);
}

window.onload = function() {
  copyToClipboard("This text has been copied to your clipboard.");
  window.close();
};
</script>
</body>
</html>
