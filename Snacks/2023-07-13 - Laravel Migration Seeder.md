## Repo
`laravel-migration-seeder`

## Todo
Scopo del gioco e' creare e popolare una tabella che rappresenti una tratta ferroviaria con le seguenti caratteristiche:
- azienda
- stazione di partenza
- stazione di arrivo
- orario di partenza
- orario di arrivo
- codice treno
- numero carrozze
- in orario
- cancellato

Sara' quindi necessario creare la relativa `migration` che disponga la struttura della tabella con tutti **i campi**, **i tipi di dato** ed eventuali **vincoli di integrita'**.
Una volta creata la tabella, generare il `model` corrispondente (al singolare), il `factory` (nome al singolare seguito da `Factory`) che accoppiera' tutte le colonne con la relativa funzione del `faker` ed infine il `seeder` (nome al singolare seguito da `TableSeeder`) che generera' i **dati fake** da inserire in tabella.

Verificare in ultima analisi la struttura e il contenuto della tabella in `PHPMyAdmin`.

### Bonus
Generare un minimo front-end per rappresentare i dati inseriti in tabella