## Repo
`laravel-one-to-many`

> [!ATTENTION] CONTINUAZIONE DELL'ESERCIZIO [[Snacks/2023-07-20 - Laravel Auth|Laravel Auth]]
> Continuare a lavorare sul codice del progetto, ma in una nuova `repo`.
> Si' consiglia di eliminare la cartella `.git` all'interno del progetto, e poi caricare tutto sulla nuova *repo*

## Todo
Continuare a lavorare sul codice del progetto , ma in una nuova `repo` e aggiungendo una nuova entità: `Type`
Questa entità rappresenta la tipologia di progetto ed è in **relazione one to many** con i *progetti*.

I task da svolgere sono diversi, ma alcuni di essi sono un ripasso di ciò che abbiamo fatto nelle lezioni dei giorni scorsi:
- creare la `migration` per la tabella *types*
- creare il `model` *Type*
- creare il `factory` e `seeder` per il model `Type`
- modificare il `seeder` dei `project` per includere la valorizzazione della chiave esterna (vedi `PostTableSeeder`)
- creare la `migration` di *modifica per la tabella projects* per aggiungere la nuova *chiave esterna*
- aggiungere ai `model` *Type* e *Project* i metodi per definire la relazione `one to many`
- visualizzare nella *pagina di dettaglio di un progetto* la tipologia associata, se presente
- permettere all’utente di *associare una tipologia* nella pagina di `creazione` di un progetto

### Bonus 1
Aggiungere la possibilita' di selezionare la tipologia anche all'interno dell'`update` di un *progetto*

### Bonus 2
Gestire il salvataggio dell’associazione *progetto-tipologia* con opportune regole di validazione

### Bonus 3
Aggiungere le operazioni `CRUD` per il model `Type`, in modo da gestire le tipologie di progetto direttamente dal *pannello di amministrazione*