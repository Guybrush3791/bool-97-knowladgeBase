# Intro PHP
## Snippets
```php
<?php

   $x = 4;

   if ($x > 20) {

    echo "x > 20";
   } else if ($x >= 10) {

    echo "x >= 10";
   } else {

    echo "x < 10";
   }

   echo "<br />";

   $x += 100;
   $x++;
   echo "<h1>" . $x . "</h1>";

   $y = "Ciao mondo";
   $y .= " Hola mundo";

   echo $y ?? "Hello world";

   echo "<br /><br />";

   $arr = [
    "val 1",
    "val 2",
    "val 3",
    "val 4"
   ];

   $arr[] = "new value";

   var_dump($arr);

   echo "<br /><br />";

   echo $arr[1];

   $pers = [
    "name" => "Guybrush",
    "lastname" => "Threepwood"
   ];
   $pers["dateOfBirth"] = "1989-01-01";

   echo "<br /><br />";

   var_dump($pers);

   echo "<br /><br />";

   echo $pers["lastname"] . " " . $pers["name"];

   echo "<br /><br />";

   $nameEx = array_key_exists("name", $pers);
   var_dump($nameEx);

   echo "<br /><br />";
   $guybrushEx = in_array("pluto", $pers);
   var_dump($guybrushEx);

   echo "<br /><br />";
   $keys = array_keys($pers);
   var_dump($keys);

   echo "<br /><br />";
   $persData = ["cf" => "asldkfjsldkfj", "rating" => "5"];
   $pers = array_merge($pers, $persData);
   var_dump($pers);

   echo "<br /><br />";
   $indData = array_search("1989-01-01", $pers);
   var_dump($indData);
   
   $perss = [
    [
        "name" => "Guybrush",
        "lastname" => "Threepwood"
    ],
    [
        "name" => "Mario",
        "lastname" => "Rossi"
    ]
   ];
   $perss[] = [
        "name" => "Franca",
        "lastname" => "Bianchi"
   ];

   echo "<br /><br />";
   $secondName = $perss[1];
   echo "---------------<br />";
   var_dump($secondName);

   echo "<br /><br />";

   echo "<pre>";
   var_dump($perss);
   echo "</pre>";

   echo "<br /><br />";
   $rndVal = rand(5, 50);
   var_dump($rndVal);

   echo "<br /><br />";
   for ($x=0; $x <= 10; $x++) { 
    
        var_dump($x);
        echo "<br />";
   }

   echo "<br /><br />";
   $x = 0;
   while(++$x < 10) {

    var_dump($x);
    echo "<br />";
   }

   echo "<br /><br />";
   $x = 0;
   do {

    var_dump($x);
    echo "<br />";
   } while($x++ < 10);

   echo "<br /><br />";
   foreach ($arr as $value) {

        var_dump($value);
        echo "<br />";
   }

   echo "<br /><br />";
   foreach($pers as $key => $value) {

        echo $key . " => " . $value;
        echo "<br />";
   }

   echo "<br /><br />";
   foreach ($perss as $k => $p) {
    echo "[" . $k + 1 . "]<br />";
    foreach ($p as $key => $value) {
        echo $key . " => " . $value . "<br />";
    }
   }

   /*
$perss = [
    [
        "name" => "Guybrush",
        "lastname" => "Threepwood"
    ],
    [
        "name" => "Mario",
        "lastname" => "Rossi"
    ],
    [
        "name" => "Franca",
        "lastname" => "Bianchi"
    ]
];
   */
```
## Ricerca in array a piu' livelli
```php
<form>
    <label for="search">Search:</label>
    <input type="text" name="search">
    <input type="submit" value="SEARCH">
</form>

<?php

// var_dump($_GET);

$perss = [
    [
        "name" => "Guybrush",
        "lastname" => "Threepwood"
    ],
    [
        "name" => "Mario",
        "lastname" => "Rossi"
    ],
    [
        "name" => "Franca",
        "lastname" => "Rossi"
    ]
];

// echo "<pre>";
// var_dump($perss);
// echo "</pre>";

if ($_GET == [] || $_GET["search"] == "") {
    
    echo "<ul>";
    foreach ($perss as $pers) {
        
        echo "<li>" . $pers["name"] . " " 
            . $pers["lastname"] . "</li>";
    }
    echo "</ul>";
} else {
    
    echo "<ul>";
    foreach ($perss as $pers) {
        
        if (array_search($_GET["search"], $pers)) {

            echo "<li>" . $pers["name"] . " " 
                . $pers["lastname"] . "</li>";
        } 
    }
    echo "</ul>";
}
```
## Ricerca in array (case insensitive)
```php
<form>
    <label for="search">Search:</label>
    <input type="text" name="search">
    <input type="submit" value="SEARCH">
</form>

<?php

$words = [
    "Lorem,",
    "ipsum",
    "dolor",
    "sit",
    "amet",
    "consectetur",
    "adipisicing",
    "elit.",
    "Impedit,",
    "voluptate,",
    "cumque",
    "temporibus",
    "facere",
    "corporis",
    "rem",
    "quae",
    "illo",
    "deleniti,",
    "tempora",
    "ab",
    "perspiciatis",
    "delectus",
    "quibusdam",
    "doloremque",
    "velit",
    "dolores",
    "quia",
    "odit",
    "magni",
    "autem."
];

if ($_GET == [] || $_GET["search"] == "") {

    echo "<ul>";
    foreach ($words as $word) {
        
        echo "<li>" . $word . "</li>";
    }
    echo "</ul>";
} else {

    $lSearch = strtolower($_GET["search"]);

    echo "<ul>";
    foreach ($words as $word) {
        
        $lWord = strtolower($word);
        
        if (str_contains($lWord, $lSearch)) {

            echo "<li>" . $word . "</li>";
        }
    }
    echo "</ul>";
}

```
## Listare tutti i parametri in GET
```php
<form>
    <label for="search">Search:</label>
    <br />
    <input type="text" name="search1">
    <br />
    <input type="number" name="search2">
    <br />
    <input type="submit" value="SEARCH">
</form>

<?php

    foreach ($_GET as $key => $value) {
        
        echo $key . " => " . $value . "<br />";
    }
```

## Password check
Tramite un form inviare una stringa al server. Se la variabile password passata in GET è uguale a "Boolean" stampare una stringa verde, altrimenti stampare una stringa rossa.
```php
<style>
    .green {
        color: white;
        background-color: green;
    }
    .red {
        color: white;
        background-color: red;
    }
</style>

<form>
    <label for="password">Password:</label>
    <input type="password" name="password">
    <input type="submit" value="LOGIN">
</form>

<?php

$pws = $_GET["password"];

if ($pws === "Boolean") {

    echo "<div class='green'>ok</div>";
} else { 

    echo "<div class='red'>ko</div>";
}
```