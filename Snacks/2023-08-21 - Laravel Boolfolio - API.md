## Repo
==Vedi MILTESTONE 1 e 3==

## Todo
Continuiamo a lavorare sul codice dei giorni scorsi, ma in **DUE nuova repo**.
L’esercizio di oggi è suddiviso in milestone ed è importante che ne seguiate l’ordine.

### Milestone 1
#### Repo
Nome repo 1 (*back-end*): `laravel-api`

#### Todo
Aggiungiamo al nostro progetto Laravel una nuovo `Api/ProjectController`. Questo controller risponderà a delle richieste via *API* e si occuperà di restituire la lista dei progetti presenti nel database in **formato json**.

### Milestone 2
Testiamo la chiamata *API* tramite `Postman` e assicuriamoci di ricevere i dati correttamente.

### Milestone 3
#### Repo
Nome repo 2 (*front-end*): `vite-boolfolio`

#### Todo
Iniziamo ad occuparci della parte front-end della nostra applicazione: creiamo un nuovo progetto `Vue 3 + Vite` e installiamo `axios`. 
Colleghiamo questo progetto ad una repo separata.

### Milestone 4
Nel componente principale della nostra `Vue App` facciamo una chiamata API all’endpoint costruito nel progetto Laravel ([[2023-08-21 - Laravel Boolfolio - API#Milestone 1|Milestone 1]]) e recuperiamo tutti i progetti dal nostro `back-end`.
Stampiamo in console i risultati e verifichiamo di ricevere i dati correttamente.

### Milestone 5
Creiamo un nuovo componente `ProjectCard`, che corrisponde ad una card per visualizzare un progetto. Utilizziamo questo componente per visualizzare tutti i progetti ricevuti tramite API.

### Bonus
Gestire la paginazione dei risultati

### Bonus 2
Gestire correttamente le **CORS Policy** all'interno del file `config/cors.php`