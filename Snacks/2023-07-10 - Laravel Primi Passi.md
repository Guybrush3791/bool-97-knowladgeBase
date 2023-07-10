## Repo
`laravel-primi-passi`

## Todo
Per prima cosa, creiamo un nuovo progetto **Laravel 9**, utilizzando questo comando:
```sh
composer create-project laravel/laravel=9.2 laravel-primi-passi
```

Al termine dell'installazione, aprire la cartella con il nome del progetto dentro `VSCode` e avviamo l'`artisan serve` con il seguente comando:
```sh
php artisan serve
```

A questo punto, iniziamo a prendere confidenza con le *rotte* e le *views*. Cancellare la view `welcome.blade.php` e creare una *homepage*. Visualizzare alla rotta `/` (root) la *view*  `home.blade.php`. 
Inizialmente stampare un `Hello World`, poi passiamo dei dati alla *view* in modo da visualizzarli dinamicamente con **Blade** come visto a lezione.

### Bonus
Creiamo più di una pagina e visualizziamo un `header menu` con i link di **tutte le pagine**, utilizzando la funzione `route()`.