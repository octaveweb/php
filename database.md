# Database Connection
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
## Creating DATABASE & TABLE using sql query
```php
$sql= "CREATE DATABASE demo";
$sql2= "CREATE TABLE Persons (PersonID int,LastName varchar(255),FirstName varchar(255),Address varchar(255),City varchar(255));";
$result = mysqli_query($conn, $sql);
```
## Explaining
| Keyword     | Decription                      |
| --------- | -------------------------------- |
| `$sql`  | Storing SQL query inside the variable. In this case it is to Createting DATABASE |
| `$sql2`  |  Createting TABLE using SQL |
| `$result`  | $result is variable  |
| `mysqli_query()`  | mysqli_query() is to fire the quarry to the server this takes two parameters one is connection variable another one is SQL quarry  |

## INSERT Record in TABLE Using Quary 
### Example How it manualy works 
```php
INSERT INTO Persons (PersonID, LastName, FirstName, Address, City) 
VALUES (1, 'Sharma', 'Amit', '123 Street Name', 'Delhi'),
(2, 'Verma', 'Rohit', '456 Market Road', 'Mumbai'),
(3, 'Singh', 'Neha', '789 Park Avenue', 'Kolkata'),
(4, 'Patel', 'Anjali', '101 Business Tower', 'Ahmedabad');
``` 
### Dinimacaly Insert Record using PHP
```php
$id = 1;
$lastname = "Sharma";
$firstname = "Amit";
$address = "123 Street Name";
$city = "Delhi";

$sql = "INSERT INTO Persons (PersonID, LastName, FirstName, Address, City) VALUES ($id, $lastname, $firstname, $address, $city)";

$result = mysqli_query($conn, $sql);
```