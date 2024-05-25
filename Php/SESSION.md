* PHP sessions are a way to store user information on the server for later use.
* They are particularly useful for maintaining state between multiple page requests.

```php
// Take Data From Client & Store Inside Session 
if ($_SERVER["REQUEST_METHOD"] == "POST")
{ 
$StringData = file_get_contents("php://input"); 
$PHPAsocArray = json_decode($StringData, true); 
session_start(); 
$_SESSION["user"] = $PHPAsocArray['username']; 
echo "Data Store Success"; 
} 

// Take Data From Client & Store Inside Session 
if ($_SERVER["REQUEST_METHOD"] == "GET") 
{
session_start(); 
echo $_SESSION["user"]; 
} 

// Destroy Session 
if ($_SERVER["REQUEST_METHOD"] == "DELETE") 
{ 
session_start(); 
unset($_SESSION["user"]); 
session_destroy(); 
echo "Destroy Success"; 
}
```

**Where Session store data:**
1. PHP sessions can be configured in the php.ini file 
2. `session.save_path: `Defines where session data is saved on the server. 
3. Default path is` "C:\xampp\tmp" `

**Advantages of Sessions:**
5. Sessions store data on the server, making them more secure. 
6. Sessions allow you to store complex data types, like arrays and objects. 
7. Sessions don't have size Limitations 

**Limitations of Sessions: **
9. As traffic increases, storing a large number of sessions can strain server resources