<!DOCTYPE html>

<p> I was never ready, ill never be ready, i wont be ready next time
  :(
  </p>
  
  <?php
// Check if the referer is set and matches the expected value
if (isset($_SERVER['HTTP_REFERER']) && $_SERVER['HTTP_REFERER'] === 'http://erikadel.com/letter.md') {
  // The user was redirected from the expected page, allow access
  // TODO: insert your page content here
} else {
  // The user did not come from the expected page, deny access
  http_response_code(403);
  die("Access denied");
}
?>
