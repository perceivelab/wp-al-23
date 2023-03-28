## Mini-homework 2

In questo MHW, utilizzerete i concetti di JavaScript visti a lezione per interagire con la vostra pagina web. L'obiettivo principale dell'homework è quello di caricare dinamicamente contenuti sulla vostra homepage e poterli ricercare.

La consegna del MHW dovrà essere effettuata sul vostro account GitHub, in un repository chiamato `mhw2`, e dovrà includere:
-   i file relativi al precedente homework (ai quali potete applicare eventuali modifiche in questo homework), un file  `script.js` e un file `contents.js`, che conterrà le informazioni da visualizzare nella pagina;
-   una presentazione in PowerPoint,  `mhw2.pptx`, che descrive l’implementazione e le specifiche utilizzate nella pagina.

### 1. Aspetto generale

L'aspetto generale della pagina da realizzare è mostrato nella figura sottostante.

<img src="{{ site.baseurl }}/imgs/mhw2_overview.png" width="450">

In pratica, dovrete estendere la struttura della pagina sviluppata nel mini-homework 1 (all'interno della quale avete inserito una sezione principale con "blocchi di contenuto") aggiungendo i seguenti componenti:
- una sezione di "preferiti", all'interno della quale l'utente può inserire un sottinsieme dei contenuti visualizzati;
- una barra di ricerca, tramite la quale l'utente può filtrare i contenuti, mostrando solo quelli che contengono una certa stringa.

### 2. Caricamento contenuti

Ai fini della descrizione del mini-homework 2, prendiamo in considerazione un'ipotetica applicazione in cui vengono visualizzato "blocchi di contenuto" relativi a giocatori di calcio, per ciascuno dei quali memorizziamo nome, un'immagine e un testo di descrizione. Queste informazioni devono essere inserite all'interno del file `contents.js`. 

Ad esempio, in questo caso il file `contents.js` potrebbe contenere delle variabili come le seguenti:
```
const titoli = ['Ferrara', 'Chiellini', 'Zidane, ...];
const immagini = ['ferrara.png', 'chiellini.jpg', '21.png'];
const descrizioni = ['Descrizione...', 'Altra descrizione...', 'Ennesima descrizione...']
```
o una struttura come la seguente (lista di oggetti)
```
const contenuti = [
  {
    titolo: 'Ferrara',
    immagine: 'ferrara.png',
    descrizione: 'Descrizione...'
  },
  {
    titolo: 'Chiellini',
    immagine: 'chiellini.jpg',
    descrizione: 'Altra descrizione...'
  },
  {
    titolo: 'Zidane',
    immagine: '21.png',
    descrizione: 'Ennesima descrizione...'
  }
]
```
Queste due possibili modalità per rappresentare i contenuti sono solo degli esempi. Esistono altri modi per descrivere i contenuti della pagina: scegliete quello che preferite.

In questo caso abbiamo definito un insieme di informazioni per ogni elemento (titolo, immagine, descrizione) che avesse senso per questo esempio. Nella vostra specifica applicazione, potrebbe essere opportuno aggiungerne di altri. **Come specifica, ogni blocco di contenuto deve contenere almeno un titolo, un'immagine e una descrizione testuale.** La descrizione non deve essere inizialmente visibile, ma può essere mostrata cliccando su una sezione "dettagli" all'interno del blocco stesso, come illustrato nelle immagini seguenti:

<img src="{{ site.baseurl }}/imgs/mhw2_dettagli_off.png" width="200"><img src="{{ site.baseurl }}/imgs/mhw2_dettagli_on.png" width="200">

Analogamente, deve essere possibile nascondere la descrizione dopo averla visualizzata.

Al caricamento della pagina, dovrete leggere i dati da `contents.js` e **inserire dinamicamente** (ovvero, tramite `createElement` e `appendChild`) i blocchi corrispondenti nella vostra sezione di contenuti della pagina.

**Ad ogni blocco di contenuti dovrete anche aggiungere un pulsante per inserire quel contenuto tra i preferiti.**

In questa fase, dovrete quindi visualizzare una schermata strutturalmente analoga alla seguente:

<img src="{{ site.baseurl}}/imgs/mhw2_caricamento_contenuti.png" width="450">

### 3. Selezione dei preferiti

Predisponete una sezione (inizialmente nascosta) al di sopra dei contenuti. Cliccando sul pulsante per l'inserimento di un elemento tra i preferiti, dovrete aggiungere il blocco selezionato tra i preferiti, come mostrato sotto:

<img src="{{ site.baseurl }}/imgs/mhw2_preferiti.png" width="450">

Scegliete voi quale sottinsieme di informazioni mostrare nel blocco tra i preferiti, rispetto al blocco originale. **Come minimo, dovete visualizzare il titolo e l'immagine del blocco.**

Ogni elemento aggiunto tra i preferiti deve anche contenere un pulsante per rimuoverlo. Se l'insieme dei preferiti è vuoto, la sezione non deve essere mostrata.

### 4. Ricerca

Come mostrato nell'overview, la sezione principale dei contenuti (non quella dei preferiti) deve contenere una barra di ricerca (potete usare un elemento `<input type='text'>`). L'inserimento di testo in questa barra permette di *filtrare* la lista di contenuti, selezionando solo quelli che contengono il testo cercato e nascondendo gli altri, come nell'esempio sottostante:

<img src="{{ site.baseurl }}/imgs/mhw2_ricerca.png" width="450">

Scegliete voi, in funzione del vostro caso d'uso, all'interno di quali informazioni volete effettuare la ricerca del testo (nel nostro esempio, potremmo effettuare la ricerca nel testo del titolo o nel testo della descrizione).

L'aggiornamento del filtro va effettuato **ad ogni lettera digitata** (usate l'evento [keyup](https://developer.mozilla.org/en-US/docs/Web/API/Document/keyup_event)). In altre parole, ad ogni lettera che digitate (o cancellate) nella barra di ricerca, si aggiorna la lista di contenuti per mostrare **solo** quelli che contengono il testo digitato fino a quel momento. Ovviamente, quando svuotate la barra di ricerca, tutti gli elementi originali devono essere visibili.
