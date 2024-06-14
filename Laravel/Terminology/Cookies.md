HTTP cookies are small blocks of data created by a web server. 
while a user is browsing a website and placed on the user's web browser.
#### What Are Cookies Used For
**Session management**
* The primary use of the cookie is to manage user logins, shopping cart details, game scores, or anything else the server should remember when the user logs in next time.
**Tracking**
* Tracking involves recording the user activity and analyzing their `behaviours` to personalize the content for them. It records and analyzes their habits and interests and finds the pages that they visit. 
**Personalization**
* Cookies help in personalizing user preferences, themes, and other settings. Most of the time, these settings are synchronized with a central database to personalize the things for the users when the user logs in for the first time

```php
public function index($id)
    {
        $name = "Donal Trump";
        $age = "75";
        
        $data = [
            "id"=>$id,
            "name"=>$name,
            "age"=>$age,
        ];

        $name = "access_token";
        $value = "123-XYZ";
        $minutes = 1;
        $path = "/";
        $domain = $_SERVER['SERVER_NAME'];
        $secure = false;
        $httpOnly = true;

        return response($data)->cookie(
            $name,
            $value,
            $minutes,
            $path,
            $domain,
            $secure,
            $httpOnly,
        );

    }
```