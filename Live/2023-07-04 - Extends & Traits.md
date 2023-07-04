## Live
[Repo](https://github.com/Guybrush3791/bool-97-extends-and-traits)

## Todo
Creare una classe `Item` e tre sottoclassi `Product` e `DigitalProduct` e `CoderProduct`.

Creare una classe `Person` ed estenderla con la classe `User`.

Aggiungere un `trait` *`Weightable`* nel quale definiamo la proprietá `$weight` piú un *setter* ed un *getter*.

Usare *il trait* nelle classi `Product`, `Person`.
Notare come sia `Product`, che `CoderProduct` hanno accesso al trait ma non `Item` e `DigitalProduct`.

Mostrare anche come `Person` e *tutte le sue sottoclassi* hanno accesso a al trait.

## Code
```php
<?php 

trait Weightable {

    private $weight;

    public function getWeight() {

        return $this -> weight;
    }
    public function setWeight($weight) {

        if ($weight <= 0) {

            throw new Exception("Weight can't be negative");
        }

        $this -> weight = $weight;
    }
}

// ------------------------------------------------------------------------------------------------------

class Item {

    private $price;
    private $name;
    private $description;

    public function __construct($price, $name, $description) {

        $this -> setPrice($price);
        $this -> setName($name);
        $this -> setDescription($description);
    }

    public function getPrice() {

        return $this -> price;
    }
    public function setPrice($price) {

        if ($price < 0) {
            throw new Exception("Price can't be negative");
        }

        $this -> price = $price;
    }
    public function getName() {

        return $this -> name;
    }
    public function setName($name) {

        $this -> name = $name;
    }
    public function getDescription() {

        return $this -> description;
    }
    public function setDescription($description) {

        $this -> description = $description;
    }
}

class Product extends Item {

    use Weightable;

    private $shipCost;
    private $shipTime;

    public function __construct($price, $name, $description, 
                                $shipCost, $shipTime,
                                $weight) {
        
        parent :: __construct($price, $name, $description);

        $this -> setShipCost($shipCost);
        $this -> setShipTime($shipTime);

        $this -> setWeight($weight);
    }

    public function getShipCost() {

        return $this -> shipCost;
    }
    public function setShipCost($shipCost) {

        $this -> shipCost = $shipCost;
    }
    public function getShipTime() {

        return $this -> shipTime;
    }
    public function setShipTime($shipTime) {

        $this -> shipTime = $shipTime;
    }
}
class CoderProduct extends Product {

    private $backendFriendly;
    private $frontendFriendly;

    public function __construct($price, $name, $description, 
                                $shipCost, $shipTime,
                                $weight,
                                $backendFriendly, $frontendFriendly) {

        parent :: __construct($price, $name, $description, $shipCost, $shipTime, $weight);

        $this -> setBackendFriendly($backendFriendly);
        $this -> setFrontendFriendly($frontendFriendly);
    }

    public function getBackendFriendly() {

        return $this -> backendFriendly;
    }
    public function setBackendFriendly($backendFriendly) {

        $this -> backendFriendly = $backendFriendly;
    }
    public function getFrontendFriendly() {

        return $this -> frontendFriendly;
    }
    public function setFrontendFriendly($frontendFriendly) {

        $this -> frontendFriendly = $frontendFriendly;
    }


}

class DigitalProduct extends Item {

    private $deliveryType;
    private $frequency;

    public function __construct($price, $name, $description, 
                                $deliveryType, $frequency) {

        parent :: __construct($price, $name, $description);

        $this -> setDeliveryType($deliveryType);
        $this -> setFrequency($frequency);
    }

    public function getDeliveryType() {

        return $this -> deliveryType;
    }
    public function setDeliveryType($deliveryType) {

        $this -> deliveryType = $deliveryType;
    }
    public function getFrequency() {

        return $this -> frequency;
    }
    public function setFrequency($frequency) {

        $this -> frequency = $frequency;
    }
}

// ------------------------------------------------------------------------------------------------------

class Person {

    private $name;
    private $lastname;
    private $dateOfBirth;

    use Weightable;

    public function __construct($name, $lastname, $dateOfBirth, $weight) {

        $this -> setName($name);
        $this -> setLastname($lastname);
        $this -> setDateOfBirth($dateOfBirth);
        $this -> setWeight($weight);
    }

    public function getName() {

        return $this -> name;
    }
    public function setName($name) {

        if (strlen($name) < 1) {

            throw new Exception("Name can't be empty");
        }

        $this -> name = $name;
    }
    public function getLastname() {

        return $this -> lastname;
    }
    public function setLastname($lastname) {

        if (strlen($lastname) < 1) {

            throw new Exception("Lastname can't be empty");
        }

        $this -> lastname = $lastname;
    }
    public function getDateOfBirth() {

        return $this -> dateOfBirth;
    }
    public function setDateOfBirth($dateOfBirth) {

        $this -> dateOfBirth = $dateOfBirth;
    }    
}
class User extends Person {

    private $username;
    private $password;

    public function __construct($name, $lastname, $dateOfBirth, $weight,
                                $username, $password) {

        parent :: __construct($name, $lastname, $dateOfBirth, $weight);

        $this -> setUsername($username);
        $this -> setPassword($password);
    }

    public function getUsername() {

        return $this -> username;
    }
    public function setUsername($username) {

        $this -> username = $username;
    } 
    public function getPassword() {

        return $this -> password;
    }
    public function setPassword($password) {

        $this -> password = $password;
    } 
}

// ------------------------------------------------------------------------------------------------------

$myProduct1 = new Product(10, "Peso", "Pesantissimo", 15, 2, 10);
var_dump($myProduct1);

echo "<br>-------------------------------------------------------------<br>";

try {

    $myProduct2 = new Product(-10, "Peso", "Pesantissimo", 15, 2, -10);
    var_dump($myProduct2);
} catch (Exception $e) {

    echo "Error: " . $e -> getMessage();
}

echo "<br>-------------------------------------------------------------<br>";

try {

    $myUser1 = new User(
        "", "Threepwood", 1988, 67, "guybrush1973", "miaPws"
    );
    var_dump($myUser1);

    echo "<br>-------------------------------------------------------------<br>";

    $myUser2 = new User(
        "Mario", "Rossi", 2000, 86, "miariottide2000", "ciaociao"
    );
    var_dump($myUser2);
} catch(Exception $e) {

    echo "Error: " . $e -> getMessage();
}

echo "<br>-------------------------------------------------------------<br>";

echo "The end";
```