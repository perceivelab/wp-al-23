
## Homework 1

Lo scopo dell'homework è quello di realizzare un sito web (3-5 pagine distinte, oltre a quelle di registrazione/login/logout) che integri quanto visto finora nel corso (HTML, CSS, JavaScript, PHP e interazione con DBMS), estendendo la tematica sviluppata nei precedenti mini-homework.

In particolare, è richiesto l'utilizzo di API REST sia da PHP (ad esempio, per servizi che richiedono l'utilizzo di credenziali segrete) che da JavaScript (accedendo tramite `fetch` a dati JSON forniti dal vostro sito stesso).

### Funzionalità richieste

- Meccanismo di registrazione, login, logout degli utenti, con opportuna validazione dei dati (sia lato client che lato server).
Dal lato client, le minime validazioni richieste sono: username già in uso, password con una struttura ben definita (ad esempio, vincoli sulla lunghezza minima, sulla presenza di maiuscole, numeri, simboli, ecc.).

- I "blocchi di contenuto" da visualizzare nella home page devono essere caricati accedendo tramite API REST a pagine PHP del vostro sito.

- La home page deve supportare meccanismi di interazione con l'utente tramite JavaScript e richieste asincrone (ad esempio, "like" a elementi, commenti, chat, inserimento in un carrello, salvataggio tra preferiti, ricerca di contenuti, e così via).

- Le pagine oltre la home page sono a vostra scelta, col vincolo che il caricamento di contenuti debba sempre avvenire tramite API REST.

- Il sito deve prevedere la possibilità di ricercare contenuti tramite API REST oltre che inserire nel database alcuni dei contenuti scelti dall'utente.

- **In generale, sarà oggetto di valutazione l'uso di richieste asincrone tramite JavaScript al posto di ricaricamenti della pagina.**

### Modalità di consegna
- Non è necessaria una presentazione, vanno consegnati tutti i file di progetto, compresa un'esportazione del database (file .sql, non la cartella data)
