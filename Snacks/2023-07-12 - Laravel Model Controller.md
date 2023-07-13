## Repo
`laravel-model-controller`

## Correzione
[Repo](https://github.com/Guybrush3791/bool-97-laravel-comics-cor)

## Database
Vedi [[2023-07-12 - DB Movies|DB Movies]]

## Todo
Oggi facciamo la nostra prima vera interazione con il database utilizzando l’**ORM di Laravel**.

1. **create un nuovo progetto** Laravel 9
2. tramite `phpMyAdmin` create un **nuovo database** `laravel_model_controller`
3. importate nel vostro database la tabella `movies`
4. **inserite le vostre credenziali** per il database nel file `.env`
5. **create un model** `Movie` con `php artisan make:model Movie`
6. **create un controller** che gestirà la rotta `/` con `php artisan make:controller Guest/PageController`
7. all’interno della funzione `index()` del controller
	1. **recuperare tutti i film** dal database
	2. **passarli alla view**
	3. **rappresentarli** in semplici card

### BONUS
Stilare il layout nei dettagli con Sass