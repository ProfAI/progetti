# Modifica foglio di calcolo su reclami degli utenti

Questo progetto consiste nel modificare il foglio di calcolo allegato in modo da soddisfare alcuni requisiti.

## Il dataset

Per cominciare, il file Excel contiene una banca dati di reclami degli utenti fatti a compagnie di gestione finanziaria.
Le colonne di tale file rappresentano dati utili al fine di valutare il grado di soddisfazione dei clienti, in particolare:

* `Date received:` la data in cui è stato fatto il reclamo in formato YYY-MM-DD
* `Product:` la categoria di prodotto sul quale si sta facendo il reclamo
* `Sub-product:` la sotto-categoria di prodotto
* `Issue:` macro descrizione del problema
* `Sub-issue:` dettaglio di descrizione del problema
* `Consumer complaint narrative:` descrizione della donamica del problema
* `Company public response:` La risposta fornita dalla compagnia
* `Company:` nome della compagnia
* `State:` sigla dello stato statunitense in cui si è verificato il problema
* `ZIP code:` Codice postale
* `Tags:` Tag che identifica la categoria del reclamante
* `Submitted via:` mezzo con cui è stato fatto il reclamo
* `Date sent to company:` la data in cui è stato ricevuto il reclamo dalla compagnia in formato YYY-MM-DD
* `Company response to consumer:` risposta della banca al reclamo
* `Timely response?:` Variabile booleana che rappresenta il concetto di utilità temporale della risposta
* `Complaint ID:` numero identificativo del reclamo sulla piattaforma
    
## Cosa devi fare

Per realizzare il progetto, dovrai modificare il foglio di calcolo allegato in modo da fargli avere la seguente struttura:

### Primo tab o scheda
* Nome: "Consumer complaints"
* Stile:
    * La prima riga di intestazione ha carattere Comics Sans MS, dimensione 12pt e colore blu, riquadrata su 4 lati con bordo doppio
    * Ogni cella non del titolo è riquadrata su 4 lati in nero con il bordo sottile
    * Non sono presenti celle vuote (vengono eliminate righe e colonne a contorno dei veri e propri dati)
    * Le date presenti (colonne `Date received` e `Date sent to company`) hanno la data in formato dd/mm/yy
* Contenuto:
    * Una colonna in fondo che contiene il numero di giorni lavorativi intercorsi fra la data di invio e quella di ricezione della comunicazione
    * Il foglio di calcolo contiene righe ordinate in modo crescente sul valore della colonna `Complaint ID`
    * È presente un filtro sulla colonna `Date received`, che permette la visualizzazione delle *sole righe* con data antecedente al 8 agosto 2016
    
### Secondo tab o scheda
* Nome: "Geographical insights"
* Stile:
    * La prima riga di intestazione ha carattere Comics Sans MS, dimensione 12pt e colore blu, riquadrata su 4 lati con bordo doppio
    * Ogni cella non del titolo è riquadrata su 4 lati in nero con il bordo sottile
    * Non sono presenti celle vuote (vengono eliminate righe e colonne a contorno dei veri e propri dati)
    * La riga di intestazione contiene i seguenti titoli:
        * `Number of complaints per state`
        * `Percentage of complaints per state`
    * È presente una colonna di intestazione che contiene tutte le sigle degli stati presenti nel tab "Consumer complaints"
* Contenuto:
    * Nella colonna B è riportato il numero di lamentele presenti nel tab principale suddivise per stato (Hint: utilizzare la funzione CONTA.SE)
    * Nella colonna C è riportato il numero percentuale (arrotondato all'intero successivo) di lamentele presenti nel tab principale suddivise per stato. La cella è di colore verde se tale percentuale è inferiore al 2%, rossa altrimenti (Hint: formattazione condizionale)
  
   
### Terzo tab o scheda
* Nome: "Statistical insights"
* Stile:
    * La prima riga di intestazione ha carattere Comics Sans MS, dimensione 12pt e colore blu, riquadrata su 4 lati con bordo doppio
    * Ogni cella non del titolo è riquadrata su 4 lati in nero con il bordo sottile
    * Non sono presenti celle vuote (vengono eliminate righe e colonne a contorno dei veri e propri dati)
    * La riga di intestazione contiene i seguenti titoli:
        * `Distinct issues`
* Contenuto:
    * Nella colonna A sono riportati tutti i possibili motivi di reclamo (valori distinti della colonna `Issues` del tab principale
    * Nella cella B7 si riporta il valore moda (il più frequente) fra tutte le categorie di reclami
