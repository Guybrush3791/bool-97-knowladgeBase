# Install Dependencies
## Install Composer
### Enable `PHP` from terminal 
Per farlo e' necessario esportare la variabile globale aprendo il file `~/.zshrc` da terminale con il seguente comando
```sh
nano ~/.zshrc
```
![[Pasted image 20230710114349.png]]

Aggiungere in fondo al file la seguente riga
```sh
export PATH=/Applications/MAMP/bin/php/php8.2.0/bin:$PATH
```
> [!attention] potrebbe essere necessario aggiornare la versione del `PHP` in accordo con quella presente dentro la cartella di `MAMP` (selezionare ultima versione disponibile)

Uscire dall'editor salvando il file tramite `CTRL + X` --> `Y`
Chiudere e riaprire il terminale. Digitare il seguente comando e' verificare che non restituisca errore
```sh
php --version
```

### Install Composer
Da terminale digitare i seguenti comandi:
- download e "compilazione" del `composer`
```sh
curl -sS https://getcomposer.org/installer | php
```
- spostare il compilato nella cartella di sistema
```sh
sudo mv composer.phar /usr/local/bin/composer
```

### Verify Composer installation
Da terminale
```sh
composer
```

Risultato atteso:
![[Pasted image 20230710115230.png]]

# Create Laravel Project
Aprire un terminale nella posizione in cui si vuole creare il progetto
```sh
composer create-project --prefer-dist laravel/laravel=9.2 MyProject
```

Aprire la cartella appena creata (nell'esempio `MyProject`) con `VSCode`
![[Pasted image 20230710120626.png]]

Da terminale di `VSCode` eseguire il seguente comando
```sh
php artisan serve
```
![[Pasted image 20230710120827.png]]

E' ora possibile aprire l'URL esposto da terminale nel browser per vedere la pagina di *welcome*
![[Pasted image 20230710120949.png]]