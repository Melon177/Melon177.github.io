<!DOCTYPE html>
<html>
<p> I was never ready, ill never be ready, i wont be ready next time
  :(
  </p>
  
  <?php
if (isset($_SERVER['HTTP_REFERER']) && $_SERVER['HTTP_REFERER'] === 'http://erikadel.com/letter.md') {
} else {
  http_response_code(403);
  die("Access denied");
}
?>
</html>
