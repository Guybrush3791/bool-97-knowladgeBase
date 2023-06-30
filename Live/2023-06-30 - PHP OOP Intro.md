## PHP OOP Fundamentals
```php
<?php

class Address {

    public $street;
    public $city;
    public $postCode;

    public function __construct($street, $city, $postCode) {

        $this -> street = $street;
        $this -> city = $city;
        $this -> postCode = $postCode;
    }
}

class User {

    public static $userCounter = 0;

    public $name;
    public $lastname;
    public $email;

    public Array $addresses;

    public function __construct($name, $lastname, String $email, Address ...$addresses) {

        self :: $userCounter++;

        $this -> name = $name;
        $this -> lastname = $lastname;
        $this -> email = $email;

        $this -> addresses = $addresses;
    }

    public function getFullname() {

        return $this -> name . " " . $this -> lastname;
    }

    public function getCity() {

        return $this -> address -> city;
    }

    public static function getCounter() {
        
        // ...

        return self :: $userCounter;
    }
}

$address1 = new Address("via Milano, 27", "Roma", "34398");
$address2 = new Address("via Palermo, 10", "Bologna", "98978");

$user1 = new User("Guybrush", "Threepwood", "guybrush@gmail.com", $address1, $address2);
var_dump($user1);

echo "<br><br>";

$user2 = new User("Mario", "Rossi", "mario@gmail.com", $address2);
var_dump($user2);
```