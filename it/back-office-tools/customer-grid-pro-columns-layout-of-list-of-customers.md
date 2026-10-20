---
title: "Customer Grid Pro - colonne e layout dell'elenco clienti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Customer Grid Pro - colonne e layout dell'elenco clienti di MyPresta.eu."
sidebar:
  label: "Customer Grid Pro - colonne e layout dell'elenco clienti"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Customer Grid Pro - columns & layout of list of customers su MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-grid-pro-columns-layout-of-list-of-customers.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/customer-grid-pro-columns-layout-of-list-of-customers/)
>
> ---


# Customer Grid Pro - colonne e layout dell'elenco clienti

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 9.x, 8.x, 1.7.8.x, 1.7.7.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo aver installato il modulo, clicca su "Configura" per accedere alle sue impostazioni. Questa pagina ti consente di selezionare quali colonne appaiono nell'elenco dei tuoi clienti e in quale ordine.

La pagina di configurazione visualizzerà un elenco di tutte le colonne disponibili per la tua griglia clienti. Queste includono colonne standard di PrestaShop e nuove aggiunte dal modulo (come telefono, indirizzo, statistiche ordini).

**Come usare l'interfaccia di configurazione:**

1.  **Elenco Colonne Disponibili:** Sul lato sinistro, vedrai un elenco di tutte le colonne che *possono* essere visualizzate.
2.  **Elenco Colonne Attive:** Sul lato destro, vedrai un elenco di colonne che sono attualmente *attive* e verranno mostrate nell'elenco dei tuoi clienti.
3.  **Aggiungere una Colonna:** Per aggiungere una colonna all'elenco dei tuoi clienti, trascinala semplicemente dall'elenco "Colonne Disponibili" a sinistra e rilasciala nell'elenco "Colonne Attive" a destra.
4.  **Rimuovere una Colonna:** Per rimuovere una colonna dall'elenco dei tuoi clienti, trascinala dall'elenco "Colonne Attive" a destra e rilasciala nuovamente nell'elenco "Colonne Disponibili" a sinistra.
5.  **Riordinare le Colonne:** All'interno dell'elenco "Colonne Attive", puoi trascinare e rilasciare le colonne verso l'alto o verso il basso per cambiarne l'ordine di visualizzazione nella tua griglia clienti. La colonna in cima all'elenco apparirà per prima (più a sinistra) nell'elenco dei tuoi clienti.
6.  **Pulsante Salva:** Dopo aver apportato modifiche (aggiungendo, rimuovendo o riordinando le colonne), ricorda di cliccare sul pulsante **"Salva"** in fondo alla pagina per applicare la tua nuova configurazione.

**Elenco delle colonne disponibili e il loro scopo:**

| Nome Colonna (Esempio) | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio commerciante |
|---|---|---|---|---|
| **ID** | Visualizza il numero di identificazione univoco per ogni cliente. | *Quando attivo:* Mostra l'ID del cliente. *Quando inattivo:* Nasconde la colonna ID. | Attivo | Utile per fare riferimento rapidamente ai clienti tramite il loro ID interno, specialmente quando si gestiscono ticket di supporto. |
| **Titolo Sociale** | Visualizza il titolo scelto dal cliente (es. Sig., Sig.ra). | *Quando attivo:* Mostra il titolo sociale. *Quando inattivo:* Nasconde la colonna del titolo sociale. | Attivo (opzionale) | Ottimo per la comunicazione formale o se la tua attività richiede saluti specifici. |
| **Nome** | Visualizza il nome del cliente. | *Quando attivo:* Mostra il nome. *Quando inattivo:* Nasconde la colonna del nome. | Attivo | Essenziale per identificare i clienti. |
| **Cognome** | Visualizza il cognome del cliente. | *Quando attivo:* Mostra il cognome. *Quando inattivo:* Nasconde la colonna del cognome. | Attivo | Essenziale per identificare i clienti. |
| **Indirizzo Email** | Visualizza l'indirizzo email del cliente. | *Quando attivo:* Mostra l'indirizzo email. *Quando inattivo:* Nasconde la colonna email. | Attivo | Cruciale per contattare i clienti e spesso usato come identificatore primario. |
| **Età** | Visualizza l'età del cliente (se la data di nascita è fornita). | *Quando attivo:* Mostra l'età calcolata del cliente. *Quando inattivo:* Nasconde la colonna dell'età. | Attivo (opzionale) | Utile per la segmentazione di marketing o prodotti con restrizioni di età. |
| **Data di Registrazione** | Visualizza la data in cui il cliente ha registrato il proprio account. | *Quando attivo:* Mostra la data di registrazione. *Quando inattivo:* Nasconde la colonna della data di registrazione. | Attivo | Aiuta a tracciare l'acquisizione dei clienti e a identificare clienti nuovi vs. vecchi. |
| **Ultima Visita** | Visualizza la data dell'ultimo accesso/visita del cliente. | *Quando attivo:* Mostra la data dell'ultima visita. *Quando inattivo:* Nasconde la colonna dell'ultima visita. | Attivo (opzionale) | Utile per identificare clienti attivi vs. inattivi per campagne di re-engagement. |
| **Ordini Totali** | Visualizza il numero totale di ordini effettuati dal cliente. | *Quando attivo:* Mostra un conteggio di tutti gli ordini. *Quando inattivo:* Nasconde questa colonna. | Attivo | Eccellente per identificare acquirenti frequenti o clienti con acquisti multipli. |
| **Totale Speso** | Visualizza il valore monetario totale speso dal cliente su tutti gli ordini. | *Quando attivo:* Mostra la somma di tutti i totali degli ordini. *Quando inattivo:* Nasconde questa colonna. | Attivo | Critico per identificare clienti di alto valore (VIP) e per la gestione degli account B2B. |
| **Numero di Telefono** | Visualizza il numero di telefono principale del cliente (dal suo indirizzo predefinito). | *Quando attivo:* Mostra il numero di telefono. *Quando inattivo:* Nasconde questa colonna. | Attivo | Essenziale per il contatto diretto, specialmente per problemi di consegna o richieste urgenti. |
| **Telefono Cellulare** | Visualizza il numero di telefono cellulare del cliente (dal suo indirizzo predefinito). | *Quando attivo:* Mostra il numero di telefono cellulare. *Quando inattivo:* Nasconde questa colonna. | Attivo | Fornisce un metodo di contatto alternativo, spesso preferito per comunicazioni rapide. |
| **Indirizzo 1** | Visualizza la prima riga dell'indirizzo predefinito del cliente. | *Quando attivo:* Mostra la riga dell'indirizzo. *Quando inattivo:* Nasconde questa colonna. | Attivo (opzionale) | Utile per un rapido riferimento della posizione senza aprire l'indirizzo completo. |
| **Indirizzo 2** | Visualizza la seconda riga dell'indirizzo predefinito del cliente. | *Quando attivo:* Mostra la riga dell'indirizzo. *Quando inattivo:* Nasconde questa colonna. | Attivo (opzionale) | Fornisce dettagli aggiuntivi sull'indirizzo. |
| **Codice Postale** | Visualizza il codice postale dell'indirizzo predefinito del cliente. | *Quando attivo:* Mostra il codice postale. *Quando inattivo:* Nasconde questa colonna. | Attivo (opzionale) | Utile per la segmentazione geografica o la pianificazione delle consegne. |
| **Città** | Visualizza la città dell'indirizzo predefinito del cliente. | *Quando attivo:* Mostra la città. *Quando inattivo:* Nasconde questa colonna. | Attivo (opzionale) | Utile per la segmentazione geografica o il marketing locale. |
| **Stato** | Visualizza lo stato/provincia dell'indirizzo predefinito del cliente. | *Quando attivo:* Mostra lo stato/provincia. *Quando inattivo:* Nasconde questa colonna. | Attivo (opzionale) | Importante per il targeting regionale e la spedizione. |
| **Paese** | Visualizza il paese dell'indirizzo predefinito del cliente. | *Quando attivo:* Mostra il paese. *Quando inattivo:* Nasconde questa colonna. | Attivo (opzionale) | Essenziale per i negozi internazionali e la logistica di spedizione. |
| **Newsletter** | Indica se il cliente è iscritto alla tua newsletter. | *Quando attivo:* Mostra un indicatore "Sì" o "No". *Quando inattivo:* Nasconde questa colonna. | Attivo | Aiuta a identificare opportunità di marketing e a gestire le liste email. |
| **Opt-in** | Indica se il cliente ha acconsentito a ricevere offerte da partner. | *Quando attivo:* Mostra un indicatore "Sì" o "No". *Quando inattivo:* Nasconde questa colonna. | Attivo (opzionale) | Utile per gestire gli sforzi di marketing dei partner. |
| **Attivo** | Indica se l'account del cliente è attualmente attivo. | *Quando attivo:* Mostra un indicatore "Sì" o "No". *Quando inattivo:* Nasconde questa colonna. | Attivo | Aiuta a identificare gli account disabilitati. |
| **Gruppo Predefinito** | Visualizza il gruppo clienti principale del cliente. | *Quando attivo:* Mostra il nome del gruppo predefinito. *Quando inattivo:* Nasconde questa colonna. | Attivo | Cruciale per i negozi B2B o i negozi con prezzi/accessi a livelli. |
| **Nome Negozio** | Visualizza il nome del negozio se si utilizza la modalità multi-negozio. | *Quando attivo:* Mostra il nome del negozio. *Quando inattivo:* Nasconde questa colonna. | Attivo (se multi-negozio) | Essenziale per gli ambienti multi-negozio per differenziare i clienti per negozio. |
| **Importo In Sospeso** | Visualizza qualsiasi saldo in sospeso che il cliente deve (se applicabile, es. per credito B2B). | *Quando attivo:* Mostra l'importo in sospeso. *Quando inattivo:* Nasconde questa colonna. | Attivo (se applicabile) | Importante per la gestione del credito B2B. |
| **Backorder Consentito** | Indica se al cliente è consentito effettuare ordini in arretrato. | *Quando attivo:* Mostra "Sì" o "No". *Quando inattivo:* Nasconde questa colonna. | Attivo (se applicabile) | Rilevante per la gestione dell'inventario e accordi specifici con i clienti. |

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | Ordine colonne Drag & Drop | Definito dall'utente | Controlla l'ordine visivo delle colonne nell'elenco clienti del Back Office. |
| Pagina di configurazione del modulo | Elenco Colonne Attive | Definito dall'utente | Determina quali colonne sono visibili nell'elenco clienti del Back Office. |
| Pagina di configurazione del modulo | Elenco Colonne Disponibili | Definito dall'utente | Elenca tutte le possibili colonne che possono essere aggiunte all'elenco clienti. |
| Pagina di configurazione del modulo | Pulsante Salva | Clicca dopo le modifiche | Applica tutte le modifiche di visibilità e ordine delle colonne alla griglia clienti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato le colonne, ma non vedo alcun cambiamento nell'elenco dei miei clienti.**
R:
1.  **Hai cliccato su "Salva"?** Dopo aver apportato modifiche nella pagina di configurazione del modulo, devi cliccare sul pulsante "Salva".
2.  **Svuota la cache di PrestaShop:** A volte, la cache di PrestaShop può impedire che le modifiche appaiano immediatamente. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
3.  **Controlla la cache del browser:** Prova a svuotare la cache del tuo browser o ad aprire il Back Office in una finestra di navigazione in incognito/privata.

**D: Alcune colonne che mi aspetto di vedere (come "Nome Azienda" o "Importo In Sospeso") non sono disponibili nell'elenco.**
R:
1.  **Compatibilità del modulo:** Assicurati di aver scaricato e installato la versione corretta del modulo per la tua specifica versione di PrestaShop.
2.  **Funzionalità di PrestaShop:** Alcune colonne (ad esempio, "Importo In Sospeso") sono rilevanti solo se hai abilitato specifiche funzionalità di PrestaShop (come la modalità B2B) o installato altri moduli che forniscono questi dati. Se i dati non esistono nel tuo negozio, il modulo potrebbe non essere in grado di visualizzarli.

**D: La funzionalità di drag-and-drop non funziona nella pagina di configurazione.**
R:
1.  **Compatibilità del browser:** Assicurati di utilizzare un browser web moderno (Chrome, Firefox, Edge, Safari) e che JavaScript sia abilitato.
2.  **Moduli in conflitto:** Raramente, un altro modulo o una modifica del tema personalizzato potrebbe interferire con JavaScript. Prova a disabilitare temporaneamente altri moduli per vedere se il problema si risolve. In tal caso, contatta il supporto MyPresta.eu.

**D: Posso tradurre i nuovi nomi delle colonne in altre lingue?**
R: Sì, il sistema di traduzione di PrestaShop dovrebbe permetterti di tradurre le stringhe del modulo.
1.  Vai su **Internazionale > Traduzioni**.
2.  Seleziona "Traduzioni dei moduli installati".
3.  Scegli il tuo tema, la tua lingua e poi seleziona "Customer Grid Pro".
4.  Dovresti trovare le stringhe per i nomi delle colonne lì da tradurre.

**D: Questo modulo rallenterà il mio Back Office?**
R: Il modulo è ottimizzato per integrarsi con la griglia clienti principale di PrestaShop. Sebbene l'aggiunta di molte colonne complesse (specialmente quelle che richiedono calcoli come "Totale Speso") possa aumentare leggermente il tempo di caricamento rispetto a un elenco essenziale, l'impatto è generalmente trascurabile su un server ben configurato. I benefici in termini di efficienza di solito superano di gran lunga eventuali piccole differenze di prestazioni.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo `Customer Grid Pro` estende principalmente la funzionalità dell'elenco clienti del Back Office di PrestaShop. Lo fa agganciandosi agli hook `actionCustomerGridDefinitionModifier` e `actionCustomerGridDataModifier`, che fanno parte del nuovo sistema di griglia di PrestaShop introdotto in 1.7.x. Ciò consente al modulo di aggiungere, rimuovere e riordinare dinamicamente colonne e i relativi dati senza modificare direttamente i file core. La configurazione è gestita tramite un metodo `getContent()` standard nel file principale del modulo, utilizzando un JavaScript e CSS personalizzati per l'interfaccia drag-and-drop.

### 4.2 Controller (`controllers/`)
Questo modulo non introduce alcun controller Front-Office o Back-Office personalizzato. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)
Questo modulo non definisce alcuna classe personalizzata o entità `ObjectModel` in una directory `classes/`. Tutta la logica è autocontenuta all'interno del file principale del modulo `index.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`mycustomergridpro/views/js/customer_grid_admin.js`**
    *   **Ambito:** Back-office (in particolare la pagina di configurazione del modulo).
    *   **Scopo:** Questo script fornisce la funzionalità drag-and-drop per l'interfaccia di selezione delle colonne nella pagina di configurazione del modulo. Utilizza il widget `sortable` di jQuery UI per consentire il riordino e lo spostamento di elementi tra gli elenchi "Colonne Disponibili" e "Colonne Attive".
    *   **Funzionalità chiave:**
        *   Inizializza due elenchi ordinabili: `#available_columns` e `#active_columns`.
        *   Configura `connectWith` per consentire lo spostamento di elementi tra questi due elenchi.
        *   Gestisce l'evento `update` per gli elenchi ordinabili per potenzialmente attivare il salvataggio o l'aggiornamento di campi di input nascosti (sebbene il salvataggio effettivo sia gestito dall'invio del modulo).
        *   Assicura che l'ordine degli elementi nell'elenco `#active_columns` sia correttamente inviato con il modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`mycustomergridpro/views/css/customer_grid_admin.css`**
    *   **Ambito:** Back-office (in particolare la pagina di configurazione del modulo).
    *   **Scopo:** Fornisce lo stile per l'interfaccia di selezione delle colonne drag-and-drop.
    *   **Stile chiave:**
        *   Stili per i contenitori dell'elenco delle colonne (`#available_columns`, `#active_columns`).
        *   Stili per i singoli elementi delle colonne (`.column-item`).
        *   Indicatori visivi per le operazioni di drag-and-drop (es. `ui-sortable-helper`, `ui-sortable-placeholder`).
        *   Assicura che i due elenchi di colonne siano visualizzati affiancati o in un layout chiaro per l'usabilità.

### 4.6 Struttura del template Smarty (`views/templates/`)
Questo modulo non utilizza file `.tpl` separati per la sua configurazione o la visualizzazione nel front-office. L'intero HTML del modulo di configurazione è generato direttamente all'interno del metodo `getContent()` del file principale del modulo `index.php`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Questo modulo non crea tabelle SQL personalizzate.
    *   Memorizza la sua configurazione (l'elenco delle colonne attive e il loro ordine) nella tabella `ps_configuration` utilizzando chiavi come `MYCUSTOMERGRIDPRO_ACTIVE_COLUMNS`. Questa configurazione è memorizzata come un array serializzato o una stringa JSON.

-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
|---|---|---|
| `actionCustomerGridDefinitionModifier` | Eseguito quando la definizione della griglia clienti viene costruita nel Back Office. | Consente al modulo di aggiungere nuove colonne (es. telefono, ordini totali, totale speso, campi indirizzo) e rimuovere quelle esistenti dalla definizione della griglia. Questo hook riceve l'oggetto `GridDefinition`. |
| `actionCustomerGridDataModifier` | Eseguito dopo che i dati della griglia clienti sono stati recuperati, ma prima che vengano renderizzati. | Consente al modulo di popolare i dati per le colonne personalizzate aggiunte tramite `actionCustomerGridDefinitionModifier`. Questo hook riceve l'oggetto `QueryResult`, consentendo la modifica delle righe di dati. |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` delle pagine del Back Office. | Utilizzato per includere i file CSS (`customer_grid_admin.css`) e JavaScript (`customer_grid_admin.js`) personalizzati del modulo nella pagina di configurazione del modulo, abilitando l'interfaccia drag-and-drop. |

## 5. Supporto Ufficiale e Aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Customer Grid Pro - colonne e layout dell'elenco clienti", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda relativa alla funzionalità e all'integrazione del modulo.
