# Data Base Connection 
*Database is a fill that stores data in a table format.*

> Current Contax of xmapp is http://localhost/phpmyadmin/

## So how to connect with database 

### Step 1
Create a extre fill or write inside of current file.  
```php
//  For XMAPP surver_name user_name and password 
$survername = "localhost";
$username = "root";
$password= "";
$db_name = "demo"
```
## Now time to connect to database 
### Step 2
`musqli_connect()` is use to connect with the surver.
```php
$conn = musqli_connect($survername, $username,  $password,  $db_name)
```
## Check if is it connect or not with database 
### Step 3
```php
if(!conn){
    die("Sorry we failed to connect: " . mysqli_connect_error());
}else{
    echo "Connection Success with Database";
}
```
