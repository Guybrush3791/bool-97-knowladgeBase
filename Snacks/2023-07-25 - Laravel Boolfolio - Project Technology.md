## Repo
`laravel-many-to-many`

> [!ATTENTION] CONTINUAZIONE DELL'ESERCIZIO [[Snacks/2023-07-20 - Laravel Auth|Laravel Auth]]
> Continuare a lavorare sul codice del progetto, ma in una nuova `repo`.
> Si' consiglia di eliminare la cartella `.git` all'interno del progetto, e poi caricare tutto sulla nuova *repo*

## Todo
Aggiungere una nuova entità `Technology`. Questa entità rappresenta le tecnologie utilizzate ed è in relazione **many to many** con i *progetti*.

I task da svolgere sono diversi, ma alcuni di essi sono un ripasso di ciò che abbiamo fatto nelle lezioni dei giorni scorsi:
- creare la *migration* per la tabella `technologies`
- creare il *model* `Technology`
- creare la *migration* per la tabella magica *project_technology*
- aggiungere ai *model Technology e Project* i metodi per definire la relazione **many to many**
- aggiungere `factory` e `seeder` per la creazione di dati **fake** all'interno sia della tabella `Technology` che della tabella magica `project_technology`
- visualizzare nella *pagina di dettaglio* di un progetto *le tecnologie utilizzate*, se presenti
- permettere all’*utente di associare le tecnologie* nella pagina di `creazione` e `modifica` di un progetto


### Bonus 1
Gestire il *salvataggio dell’associazione* `progetto-tecnologie` con opportune regole di validazione

### Bonus 2
aggiungere le operazioni CRUD per il model `Technology`, in modo da gestire le tecnologie utilizzate nei progetti direttamente dal pannello di amministrazione