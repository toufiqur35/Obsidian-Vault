**COOKIES: **
1. Cookies are small pieces of data that servers send to the user's browser. 
2. Browsers send back with subsequent requests.

**Same Site:**
1. Strict: The cookie will only be sent only to the site that set the cookie.
2. Lax: This is more lenient than Strict. The cookie will be withheld on cross-site sub-requests.
3. None: The cookie will be sent in all contexts, both first-party and cross-site requests.

```php
// Take Data From Client & Set Cookie 
if ($_SERVER["REQUEST_METHOD"] == "POST") 
{ 
$StringData = file_get_contents("php://input");
$PHPAsocArray = json_decode($StringData, true); 
setcookie("username", $PHPAsocArray['username'], [ "expires" => time() + 3600, "path" => "/", "domain" => "localhost", "secure" => true, "httponly" => true, "samesite" => "Lax" ]); 
echo "Cookie Set Success"; 
}


// Read Cookie From Request 
if ($_SERVER["REQUEST_METHOD"] == "GET") 
{ 
echo $_COOKIE["username"]; 
} 

// Destroy Cookie From Request 
if ($_SERVER["REQUEST_METHOD"] == "DELETE") 
{ 
setcookie("username", "", time() - 3600, "/"); 
echo "Cookie Destroy Success"; 
}
```

**Advantages:**
1. Don't use server-side resources. 
2. Cookies can be set to persist for long durations, enabling you to recognize return visitors even after weeks or months.

**Limitations: **
1.Each cookie has a size limit (typically around 4KB) 
2.Number of cookies you can set for each domain (usually 50).