---
title: "Assegna corriere ai prodotti in blocco - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Assegna corriere ai prodotti in blocco di MyPresta.eu."
sidebar:
  label: "Assegna corriere ai prodotti in blocco - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Assign carrier to products in bulk su MyPresta.eu](https://mypresta.eu/modules/administration-tools/assign-carrier-to-products-in-bulk.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/assign-carrier-to-products-in-bulk/)
>
> ---


# Assegna corriere ai prodotti in blocco

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Assegna corriere ai prodotti in blocco)

Questa è l'interfaccia principale in cui definirai le tue attività di assegnazione massiva dei corrieri. La pagina è progettata per essere intuitiva, guidandoti attraverso il processo di selezione dei corrieri e quindi specificando quali prodotti devono essere interessati.

**Opzioni di configurazione principali:**

1.  **Seleziona Corrieri:**

    -   **Cosa fa questa impostazione:** Questa sezione visualizza un elenco di tutti i corrieri di spedizione attivi configurati nel tuo negozio PrestaShop (che si trovano in **Spedizione > Corrieri**). Puoi selezionare uno o più corrieri che desideri assegnare ai tuoi prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando uno o più corrieri sono selezionati:* I corrieri scelti verranno assegnati ai prodotti specificati nei passaggi successivi. Ciò significa che questi corrieri diventeranno opzioni di spedizione disponibili per tali prodotti durante il checkout.
        -   *Quando nessun corriere è selezionato:* Il modulo non eseguirà alcuna assegnazione. Devi selezionare almeno un corriere per procedere.
    -   **Valore consigliato:** Seleziona tutti i corrieri che dovrebbero essere disponibili per i prodotti target.
    -   **Scenario/esempio del commerciante:** Se desideri rendere disponibili "UPS Ground" e "FedEx Express" per una nuova linea di elettronica, li selezioneresti entrambi da questo elenco.
2.  **Seleziona Prodotti a cui Assegnare i Corrieri:**

    -   **Cosa fa questa impostazione:** Questa sezione cruciale ti consente di definire l'ambito dei prodotti che riceveranno le assegnazioni dei corrieri selezionati. Hai tre potenti opzioni:
        -   **Per Categorie:** Assegna i corrieri a tutti i prodotti all'interno di categorie specifiche.
        -   **Per Produttori:** Assegna i corrieri a tutti i prodotti di produttori specifici.
        -   **Per Prodotti Specifici:** Assegna i corrieri a singoli prodotti che selezioni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando è selezionato "Per Categorie":* Verrà visualizzato un elenco delle categorie del tuo negozio. La selezione delle categorie qui significa che a tutti i prodotti appartenenti a queste categorie verranno assegnati i corrieri scelti.
        -   *Quando è selezionato "Per Produttori":* Verrà visualizzato un elenco dei produttori del tuo negozio. La selezione dei produttori qui significa che a tutti i prodotti associati a questi produttori verranno assegnati i corrieri scelti.
        -   *Quando è selezionato "Per Prodotti Specifici":* Verrà visualizzato un campo di input con una funzione di completamento automatico. Puoi digitare i nomi dei prodotti e il sistema suggerirà i prodotti. Puoi aggiungere più prodotti specifici all'elenco.
    -   **Valore consigliato:** Scegli il metodo che raggruppa meglio i tuoi prodotti target. Per modifiche ampie, categorie o produttori sono efficienti. Per regolazioni precise, i prodotti specifici sono i migliori.
    -   **Scenario/esempio del commerciante:**
        -   *Categorie:* Lanci una nuova categoria "Articoli Fragili". Selezioneresti questa categoria e assegneresti un "Corriere Merci Fragili" specializzato a tutti i prodotti al suo interno.
        -   *Produttori:* Arriva un nuovo marchio di abbigliamento. Selezioni il produttore e assegni il tuo "Corriere Abbigliamento" standard a tutti i loro prodotti.
        -   *Prodotti Specifici:* Hai tre prodotti unici e di grandi dimensioni che richiedono un "Corriere Merci". Cercheresti e aggiungeresti questi tre prodotti individualmente.
3.  **Pulsanti di Azione:**

    -   **Pulsante "Assegna Corrieri":**
        -   **Cosa fa questo pulsante:** Avvia il processo di assegnazione massiva. Dopo aver cliccato, il modulo elaborerà le tue selezioni e aggiornerà le associazioni dei corrieri per tutti i prodotti specificati.
        -   **Effetto del clic su questo pulsante:** I corrieri selezionati verranno collegati ai prodotti scelti. Verrà tipicamente visualizzato un messaggio di successo o di errore.
        -   **Azione consigliata:** Clicca solo dopo aver esaminato attentamente le tue selezioni di corrieri e prodotti.
        -   **Scenario/esempio del commerciante:** Dopo aver impostato i tuoi corrieri e gruppi di prodotti, cliccando su questo pulsante si eseguono le modifiche in tutto il tuo negozio.
    -   **Pulsante "Cancella Tutte le Assegnazioni" (o simile):**
        -   **Cosa fa questo pulsante:** Questa opzione (se presente) rimuoverebbe tipicamente *tutte* le assegnazioni di corrieri per i prodotti selezionati, o potenzialmente per tutti i prodotti nel negozio, a seconda dell'esatta implementazione del modulo.
        -   **Effetto del clic su questo pulsante:** I prodotti tornerebbero a non avere corrieri specifici assegnati, o solo corrieri predefiniti, potenzialmente influenzando la disponibilità di spedizione.
        -   **Azione consigliata:** Usare con estrema cautela e solo se si comprendono appieno le implicazioni. Questa è un'azione potente che può interrompere le opzioni di spedizione.
        -   **Scenario/esempio del commerciante:** Stai completamente rivedendo la tua strategia di spedizione e devi reimpostare tutti i collegamenti prodotto-corriere prima di riassegnarli.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 AdminMassCarrierCronController (Back Office > Parametri Avanzati > Cron Mass Carrier)

Questa schermata fornisce la gestione dei cron job relativi al modulo, consentendo di pianificare e automatizzare le attività di assegnazione dei corrieri.

-   **Nome schermata e posizione nel menu:** Troverai tipicamente una nuova voce di menu sotto **Parametri Avanzati** (o una sezione simile, a seconda della versione di PrestaShop) denominata qualcosa come "Cron Mass Carrier" o "Pianificatore Assegnazione Corriere".
-   **Azioni e impostazioni disponibili:** Questa schermata mostrerà probabilmente una griglia (elenco) di attività pianificate. Per ogni attività, potresti vedere:
    -   **ID attività:** Identificatore univoco.
    -   **Descrizione:** Una breve spiegazione di cosa fa l'attività (ad esempio, "Assegna UPS alla Categoria X").
    -   **Frequenza:** Quanto spesso viene eseguita l'attività (ad esempio, giornalmente, settimanalmente, una volta).
    -   **Ultima esecuzione:** Timestamp dell'ultima esecuzione.
    -   **Stato:** Se l'attività è attiva, in sospeso o completata.
    -   **Azioni:** Pulsanti per "Aggiungi nuova attività", "Modifica", "Elimina" o "Esegui ora".
-   **Effetto delle modifiche:**
    -   *Aggiunta di una nuova attività:* Consente di definire una nuova operazione di assegnazione massiva di corrieri da eseguire automaticamente a un intervallo specificato. Questo è utile per aggiornamenti ricorrenti (ad esempio, nuove importazioni di prodotti).
    -   *Modifica di un'attività:* Modifica i parametri (corrieri, prodotti, frequenza) di un'assegnazione pianificata esistente.
    -   *Eliminazione di un'attività:* Rimuove un'assegnazione pianificata, impedendone l'esecuzione futura.
    -   *Esecuzione di un'attività ora:* Esegue un'attività pianificata immediatamente, al di fuori del suo programma regolare.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   Usa questa schermata per automatizzare le assegnazioni di corrieri di routine, specialmente se importi regolarmente nuovi prodotti in categorie specifiche o da determinati produttori che utilizzano sempre gli stessi corrieri.
    -   Per assegnazioni una tantum e immediate, usa la pagina di configurazione principale del modulo (4.1).
    -   Controlla regolarmente "Ultima esecuzione" e "Stato" per assicurarti che le tue attività automatizzate vengano eseguite correttamente.

#### 2.2.2 index.php (masscarrier/controllers/admin/index.php)

Questo file funge tipicamente da segnaposto o da reindirizzamento all'interno della directory dei controller di amministrazione del modulo e di solito non rappresenta una schermata distinta e configurabile per il commerciante. Nello sviluppo di moduli PrestaShop, i file `index.php` all'interno delle sottodirectory spesso impediscono l'elenco delle directory o gestiscono il routing di base, piuttosto che fornire un'interfaccia utente. Pertanto, non ci sono impostazioni o azioni specifiche rivolte al commerciante associate a questo file.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Seleziona Corrieri | Seleziona tutti i pertinenti | Scegli quali corrieri verranno assegnati ai prodotti. |
|  | Seleziona Prodotti: Per Categorie | Seleziona le categorie pertinenti | Assegna i corrieri a tutti i prodotti all'interno delle categorie scelte. |
|  | Seleziona Prodotti: Per Produttori | Seleziona i produttori pertinenti | Assegna i corrieri a tutti i prodotti dei produttori scelti. |
|  | Seleziona Prodotti: Per Prodotti Specifici | Cerca e aggiungi prodotti | Assegna i corrieri ai prodotti selezionati individualmente. |
|  | Pulsante Assegna Corrieri | Clicca dopo la selezione | Esegue l'assegnazione massiva dei corrieri. |
|  | Pulsante Cancella Tutte le Assegnazioni | Usa con cautela | Rimuove le assegnazioni dei corrieri per i prodotti selezionati (se presente). |
| **AdminMassCarrierCronController** | Aggiungi/Modifica/Elimina Attività | In base alle esigenze di automazione | Pianifica e gestisci le assegnazioni massive automatizzate dei corrieri. |
|  | Azione Esegui Ora | Secondo necessità per l'esecuzione immediata | Attiva manualmente un'attività pianificata. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho assegnato i corrieri, ma non vengono visualizzati ai clienti al checkout.**
R:

1.  **Svuota la cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). PrestaShop spesso memorizza nella cache la disponibilità dei corrieri.
2.  **Configurazione del corriere:** Ricontrolla che i corrieri stessi siano attivi, abbiano zone di spedizione valide e siano configurati per gestire l'intervallo di peso/prezzo del prodotto. Vai su **Spedizione > Corrieri** e modifica il corriere per rivedere le sue impostazioni.
3.  **Dimensioni/Peso del prodotto:** Assicurati che le dimensioni e il peso del prodotto siano inseriti correttamente e rientrino negli intervalli definiti dal corriere.
4.  **Esecuzione del modulo:** Rilancia il processo di assegnazione nel modulo, assicurandoti di aver selezionato i corrieri e i gruppi di prodotti corretti.

**D: Il modulo sembra bloccato o impiega molto tempo per elaborare.**
R:

1.  **Risorse del server:** Se hai un catalogo molto grande (decine di migliaia di prodotti) e stai assegnando a "tutti i prodotti", il processo può essere intensivo in termini di risorse. Assicurati che il tuo hosting abbia memoria PHP e limiti di tempo di esecuzione sufficienti.
2.  **Cron Job:** Per operazioni estremamente grandi, considera l'utilizzo di "AdminMassCarrierCronController" per pianificare l'attività come un cron job in background, che è più robusto per processi a lunga esecuzione.
3.  **Suddividi le attività:** Invece di assegnare a *tutti* i prodotti contemporaneamente, prova a suddividerli per categorie o produttori principali.

**D: Posso rimuovere un corriere dai prodotti in blocco usando questo modulo?**
R: La funzione principale di questo modulo è *assegnare* i corrieri. Sebbene non abbia una funzione diretta "rimuovi corriere dai prodotti selezionati", puoi ottenerlo efficacemente tramite:

1.  **Riassegnazione:** Se desideri sostituire il Corriere A con il Corriere B per un gruppo di prodotti, seleziona semplicemente il Corriere B e il gruppo di prodotti, quindi esegui l'assegnazione. Questo aggiungerà il Corriere B. Dovrai quindi rimuovere manualmente il Corriere A da quei prodotti se lo desideri completamente eliminato, o utilizzare uno strumento separato se disponibile.
2.  **Rimozione manuale:** Per prodotti specifici, puoi comunque andare alla pagina di modifica del prodotto (**Catalogo > Prodotti > Modifica Prodotto > Scheda Spedizione**) e deselezionare manualmente il corriere.

**D: Il mio tema personalizzato non visualizza correttamente gli elementi del modulo (se ce n'erano di visibili).**
R: Questo modulo non ha elementi visivi nel front-office, quindi i problemi di compatibilità del tema sono improbabili dal punto di vista della visualizzazione. Se riscontri problemi con le schermate di configurazione del *back-office*:

1.  **Versione PrestaShop:** Assicurati di aver scaricato la versione corretta del modulo per la tua installazione di PrestaShop.
2.  **Cache del browser:** Svuota la cache del tuo browser.
3.  **Override del tema:** Se il tuo tema del back-office è fortemente personalizzato, potrebbe interferire. Prova a passare temporaneamente al tema predefinito del back-office di PrestaShop per vedere se il problema persiste.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Assegna corriere ai prodotti in blocco" (`masscarrier`) segue un modello MVC (Model-View-Controller) standard di PrestaShop, concentrandosi principalmente sulle attività amministrative. Sfrutta la classe `Module` di PrestaShop per la sua funzionalità principale ed estende `AdminController` per le sue schermate di gestione dedicate nel back-office. Il modulo interagisce direttamente con i dati principali di prodotto e corriere di PrestaShop, modificando la tabella `ps_product_carrier` per stabilire le associazioni. Include anche un front controller per l'esecuzione di cron job, consentendo operazioni massive pianificate.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe genitore**: `MassCarrierCronjobModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è progettato per essere chiamato esternamente, tipicamente da un cron job lato server. Esegue le attività di assegnazione dei corrieri pianificate definite nel back-office. Non produce alcun output visivo al browser ma esegue l'elaborazione in background. Gestisce la logica per recuperare le attività in sospeso dalla tabella `masscarriercron` e applicare le modifiche del corriere ai prodotti.
-   **Controller Admin Back-Office**:

    -   `controllers/admin/AdminMassCarrierCron.php`
        -   **Nome scheda ed entità gestita**: Questo controller gestisce l'entità `masscarriercron`, che rappresenta le attività di assegnazione massiva dei corrieri pianificate. Crea una nuova scheda nel back office di PrestaShop (probabilmente sotto "Parametri Avanzati" o un menu personalizzato "Mass Carrier").
        -   **Responsabilità**: Fornisce un'interfaccia `AdminController` standard di PrestaShop per elencare, aggiungere, modificare ed eliminare le attività cron pianificate. Gestisce l'invio di moduli per la creazione/aggiornamento delle attività, la convalida dell'input e l'interazione con la tabella del database `masscarriercron`.
    -   `controllers/admin/index.php`
        -   **Responsabilità**: Questo è un file `index.php` vuoto standard spesso posizionato nelle directory dei moduli di PrestaShop per impedire l'elenco delle directory quando vi si accede direttamente tramite un browser web. Non contiene alcuna logica funzionale o gestisce alcuna entità.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò implica che la logica principale per l'assegnazione dei corrieri e la gestione dei cron job è probabilmente gestita direttamente all'interno del file principale `masscarrier.php` e dei rispettivi controller, possibilmente utilizzando direttamente gli `ObjectModel` `Product` e `Carrier` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   `masscarrier/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito**: Back-office.
    -   **Responsabilità**: Questo script probabilmente fornisce la funzionalità di completamento automatico per la selezione di prodotti specifici nella pagina di configurazione principale del modulo. Ascolta l'input dell'utente in un campo di ricerca prodotti designato, invia richieste AJAX a un controller del back-office (o al metodo `getContent()` del modulo principale) per recuperare i suggerimenti di prodotti e li visualizza in un elenco a discesa. Gestisce gli eventi di selezione per aggiungere i prodotti scelti a un elenco per l'assegnazione massiva.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `masscarrier/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito**: Styling del modulo di amministrazione del back-office.
    -   **Responsabilità**: Fornisce lo styling per l'input di ricerca con completamento automatico e il suo elenco di suggerimenti, garantendo che si integri visivamente con il tema del back-office di PrestaShop. Definisce gli stili per il campo di input, il contenitore a discesa e i singoli elementi di suggerimento. Gli sviluppatori possono sovrascrivere queste classi nei loro temi personalizzati del back-office, se necessario.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:

    -   Non sono elencati template hook specifici, suggerendo che la configurazione principale del modulo è gestita tramite `getContent()` e controller di amministrazione dedicati.
-   **Template admin (`views/templates/admin/`)**:

    -   `masscarrier/lib/searchTool/views/scripts.tpl`
        -   **Scopo**: Questo template probabilmente include il JavaScript necessario per lo strumento di ricerca con completamento automatico (ad esempio, `autocomplete.js`) e potenzialmente configurazioni JavaScript inline o collegamenti CSS. È probabilmente incluso nel modulo di configurazione principale o in un modulo del controller di amministrazione.
    -   `masscarrier/masscarrier.tpl`
        -   **Scopo**: Questo è il template di configurazione principale per il modulo, renderizzato dal metodo `getContent()` di `masscarrier.php`. Contiene la struttura HTML per la selezione dei corrieri, la scelta dei gruppi di prodotti (categorie, produttori, prodotti specifici) e il pulsante "Assegna Corrieri". Probabilmente include `scripts.tpl` per la funzionalità di completamento automatico.
    -   `masscarrier/views/button-subcategories.tpl`
        -   **Scopo**: Questo template probabilmente renderizza un pulsante o una sezione relativa alla gestione delle sottocategorie, possibilmente per espandere/comprimere gli alberi delle categorie nell'interfaccia di selezione dei prodotti, o per azioni specifiche relative alla selezione delle sottocategorie.
-   **Template front-office (`views/templates/front/`)**:

    -   Non sono elencati template front-office, coerentemente con la natura amministrativa del modulo nel back-office.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_masscarriercron`: Questa tabella personalizzata memorizza i dettagli delle attività di assegnazione massiva dei corrieri pianificate. Tipicamente conterrebbe campi come:
        -   `id_masscarriercron`: Chiave primaria.
        -   `carriers`: Un array serializzato o una stringa di ID corriere separati da virgole.
        -   `product_selection_type`: (ad esempio, 'category', 'manufacturer', 'product').
        -   `product_selection_ids`: Un array serializzato o una stringa di ID categoria/produttore/prodotto separati da virgole.
        -   `frequency`: (ad esempio, 'daily', 'weekly', 'once').
        -   `last_run`: DATETIME dell'ultima esecuzione.
        -   `active`: BOOLEAN che indica se l'attività è abilitata.
    -   Il modulo interagisce principalmente con le tabelle principali di PrestaShop:
        -   `ps_product_carrier`: Questa è la tabella cruciale che memorizza la relazione molti-a-molti tra prodotti e corrieri. Il modulo inserisce/aggiorna i record in questa tabella.
        -   `ps_product`: Per recuperare le informazioni sul prodotto.
        -   `ps_category_product`: Per collegare i prodotti alle categorie.
        -   `ps_product_supplier` / `ps_manufacturer`: Per collegare i prodotti ai produttori.
        -   `ps_carrier`: Per recuperare le informazioni sul corriere.
-   **Tabella degli hook registrati**:
    La descrizione del modulo menziona "Hook Front-Office: Header, Columns, Product, or Footer" ma, in base all'inventario del codice e allo scopo del modulo, è altamente improbabile che registri hook front-office per l'output visivo. Questi potrebbero essere segnaposto generici o riferirsi a hook interni utilizzati per l'inizializzazione del modulo o l'elaborazione dei dati.

    Il modulo utilizzerebbe principalmente hook interni di PrestaShop per la sua funzionalità:

    | Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
    | --- | --- | --- |
    | `actionModuleInstall` | Durante l'installazione del modulo | Crea la tabella `ps_masscarriercron`, registra le schede di amministrazione. |
    | `actionModuleUninstall` | Durante la disinstallazione del modulo | Elimina la tabella `ps_masscarriercron`, annulla la registrazione delle schede di amministrazione. |
    | `actionAdminControllerSetMedia` | Quando viene caricato un controller di amministrazione | Inietta risorse JS/CSS per i moduli del back-office (ad esempio, autocomplete.js, autocomplete.css). |
    | `displayBackOfficeHeader` | Renderizza nell'intestazione del back-office | Può includere JS/CSS o configurazioni globali del back-office. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Assegna corriere ai prodotti in blocco", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu fornisce supporto diretto e garantisce l'accesso alle versioni più compatibili e ricche di funzionalità del modulo per il tuo negozio PrestaShop.
