## Repo
`laravel-auth`

## Todo
Creiamo con Laravel il nostro sistema di gestione del nostro portfolio di progetti.
Oggi iniziamo un nuovo progetto che si arricchirà nel corso delle prossime lezioni.

Ripercorriamo gli steps fatti a lezione ed iniziamo un nuovo progetto usando`laravel breeze` ed il pacchetto `Laravel 9 Preset` **con autenticazione**. 

Generare poi `migration`, `model`, `factory` e `seeder` per l'entita' `Project` (inventare i soliti 3-4-5 campi semplici).

Creare le seguenti rotte:
- `index`: rotta **pubblica** che stampa tutti i progetti presenti nel db (solo il nome del progetto)
- `show`: rotta **accessibile ai soli utenti loggati** che mostra i dettagli di un singolo `Project`