## Repo
`php-strong-password-generator`

## Correzione
[Repo](https://github.com/Guybrush3791/bool-97-php-strong-password-generator)

## Todo
Dobbiamo creare una pagina che permetta ai nostri utenti di utilizzare il nostro generatore di password (abbastanza) sicure.
L’esercizio è suddiviso in varie milestone ed è molto importante svilupparle in modo ordinato.

### Milestone 1
Creare un `form` che invii in `GET` la *lunghezza della password*. Una nostra funzione utilizzerà questo dato per generare una **password casuale** (composta da *lettere* minuscole e maiuscole, *numeri* e *simboli*) da restituire all’utente.
Scriviamo tutto (logica e layout) in un unico file `index.php`.

### Milestone 2
Verificato il corretto funzionamento del nostro codice, spostiamo la logica in un file `functions.php` che includeremo poi nella pagina principale.

### Bonus
#### Milestone 3
Invece di visualizzare la password nella `index.php`, effettuare un redirect ad una pagina dedicata che tramite `$_SESSION` recupererà la password da mostrare all’utente.

#### Milestone 4
Gestire ulteriori parametri per la password dando all'utente la possibilita' di scegliere quali caratteri usare fra numeri, lettere e simboli. 
Possono essere **scelti singolarmente** (es. solo numeri) oppure possono essere **combinati fra loro** (es. numeri e simboli, oppure tutti e tre insieme).
Dare all’utente anche la possibilità di permettere o meno la **ripetizione di caratteri uguali**.

## Layout
![[Pasted image 20230621123915.png]]