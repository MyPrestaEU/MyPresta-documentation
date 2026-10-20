---
title: "Disabilita sconto gruppo per prodotti specifici - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Disabilita sconto gruppo per prodotti specifici' di MyPresta.eu."
sidebar:
  label: "Disabilita sconto gruppo per prodotti specifici - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Disable group discount for specific products su MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-for-specific-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/disable-group-discount-for-specific-products/)
>
> ---


# Disabilita sconto gruppo per prodotti specifici

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Disabilita sconto gruppo per prodotti specifici". Qui troverai tutte le impostazioni per controllare quali prodotti sono esclusi dagli sconti di gruppo.

**Posizione del menu:** Back Office > Moduli > Gestione moduli > "Disabilita sconto gruppo per prodotti specifici" > Configura

#### 2.1.1 Sezione "Disabilita sconti di gruppo per prodotti specifici"

Questa sezione contiene le impostazioni principali per abilitare o disabilitare la funzionalità del modulo e definire quali prodotti sono interessati.

-   **Impostazione: Interruttore Abilitato / Disabilitato**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale del modulo. Determina se la logica del modulo per la disabilitazione degli sconti di gruppo è attiva o inattiva.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato:* Il modulo controllerà attivamente se un prodotto o la sua categoria è elencata nelle tue regole di esclusione. In tal caso, eventuali sconti di gruppo verranno ignorati per quel prodotto.
        -   *Quando Disabilitato:* Il modulo non interferirà con i calcoli predefiniti degli sconti di gruppo di PrestaShop. Tutti i prodotti saranno soggetti a sconti di gruppo, se applicabili.
    -   **Valore consigliato:** "Abilitato" se intendi utilizzare la funzionalità del modulo.
    -   **Scenario / esempio per il commerciante:** Se stai configurando il modulo per la prima volta o eseguendo la manutenzione, lo abiliteresti. Se desideri temporaneamente che tutti gli sconti di gruppo si applichino senza disinstallare il modulo, lo disabiliteresti.
-   **Impostazione: Categorie (Casella di selezione)**

    -   **Cosa fa questa impostazione:** Ti consente di selezionare intere categorie di prodotti i cui prodotti dovrebbero essere esclusi dagli sconti di gruppo. Qualsiasi prodotto appartenente a una categoria selezionata non riceverà sconti di gruppo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando le categorie sono selezionate:* Tutti i prodotti all'interno delle categorie scelte (e delle loro sottocategorie, a seconda della struttura delle categorie di PrestaShop e di come i prodotti sono assegnati) avranno gli sconti di gruppo disabilitati.
        -   *Quando nessuna categoria è selezionata:* I prodotti non vengono esclusi in base alla loro categoria.
    -   **Valore consigliato:** Seleziona le categorie che contengono prodotti che desideri escludere dagli sconti di gruppo.
    -   **Scenario / esempio per il commerciante:** Vendi elettronica. La tua categoria "Nuovi arrivi" contiene spesso articoli molto richiesti. Vuoi assicurarti che anche i tuoi clienti all'ingrosso paghino il prezzo intero per questi nuovi prodotti per il primo mese. Selezioneresti la categoria "Nuovi arrivi" qui.
-   **Impostazione: Prodotti specifici (Input di ricerca e selezione)**

    -   **Cosa fa questa impostazione:** Ti consente di cercare e selezionare singoli prodotti che dovrebbero essere esclusi dagli sconti di gruppo. Questo fornisce un controllo più granulare rispetto alle categorie.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando vengono selezionati prodotti specifici:* Solo i prodotti esplicitamente scelti avranno gli sconti di gruppo disabilitati, indipendentemente dalla loro categoria.
        -   *Quando non vengono selezionati prodotti specifici:* I prodotti non vengono esclusi in base alla selezione individuale.
    -   **Valore consigliato:** Seleziona i prodotti specifici che desideri escludere dagli sconti di gruppo.
    -   **Scenario / esempio per il commerciante:** Hai una stampa d'arte in edizione limitata (ID Prodotto 123) e un'offerta speciale in bundle (ID Prodotto 456) che non vuoi mai scontare per nessun gruppo di clienti. Cercheresti e aggiungeresti "Stampa d'arte (Edizione limitata)" e "Offerta speciale in bundle" a questo elenco.

#### 2.1.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilitato / Disabilitato | Abilitato | Interruttore principale per attivare/disattivare la funzionalità del modulo. |
| Configurazione modulo | Categorie | Seleziona le categorie pertinenti | Esclude tutti i prodotti all'interno delle categorie selezionate dagli sconti di gruppo. |
| Configurazione modulo | Prodotti specifici | Seleziona i prodotti pertinenti | Esclude i prodotti selezionati individualmente dagli sconti di gruppo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho configurato il modulo, ma gli sconti di gruppo si applicano ancora ai miei prodotti esclusi. Cosa c'è che non va?**
R:

-   **Il modulo è abilitato?** Ricontrolla l'interruttore "Abilitato / Disabilitato" nella pagina di configurazione del modulo. Deve essere impostato su "Abilitato".
-   **Hai salvato le modifiche?** Clicca sempre sul pulsante "Salva" dopo aver apportato modifiche alla configurazione.
-   **Svuota la cache di PrestaShop:** A volte, la cache di PrestaShop può impedire che le modifiche vengano visualizzate immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
-   **Controlla l'assegnazione prodotto/categoria:** Assicurati che il prodotto sia correttamente assegnato alla categoria che hai escluso, o che tu abbia selezionato il prodotto esatto che intendi escludere.
-   **Controlla altri moduli:** Un altro modulo di prezzo o sconto potrebbe essere in conflitto. Prova a disabilitare temporaneamente altri moduli relativi agli sconti per vedere se il problema si risolve.

**D2: Questo modulo influenzerà le mie normali regole di prezzo del catalogo o i prezzi specifici?**
R: No, questo modulo si rivolge specificamente agli *sconti di gruppo*. Non interferisce con le regole di prezzo del catalogo, i prezzi specifici che imposti per i singoli prodotti o le regole del carrello (voucher). Impedisce solo lo sconto percentuale aggiuntivo applicato in base al gruppo di un cliente.

**D3: Come gestisce questo modulo i prodotti in più categorie?**
R: Se un prodotto si trova in più categorie e *una qualsiasi* di queste categorie è selezionata per l'esclusione nel modulo, il prodotto verrà escluso dagli sconti di gruppo. Il modulo controlla se il prodotto *appartiene* a una categoria esclusa.

**D4: Sto usando un tema personalizzato. Questo modulo funzionerà correttamente?**
R: Sì, questo modulo funziona a livello di calcolo del prezzo principale e non introduce nuovi elementi front-office o stili complessi che tipicamente entrerebbero in conflitto con i temi. Dovrebbe essere completamente compatibile con qualsiasi tema PrestaShop.

**D5: Posso escludere prodotti per *alcuni* gruppi ma non per altri?**
R: No, questo modulo disabilita gli sconti di gruppo per i prodotti/categorie selezionati *per tutti i gruppi di clienti*. Se un prodotto è nell'elenco di esclusione, nessun gruppo di clienti riceverà uno sconto su di esso. La funzionalità principale di PrestaShop ti consente di impostare sconti di gruppo per gruppo, ma questo modulo agisce come un override per prodotti specifici, rendendoli esenti da *qualsiasi* sconto di gruppo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che desiderano comprendere, eseguire il debug o estendere il modulo "Disabilita sconto gruppo per prodotti specifici".

### 4.1 Panoramica dell'architettura

Il modulo funziona principalmente sovrascrivendo una classe core di PrestaShop (`Product.php`) per modificare la logica di calcolo del prezzo. Si aggancia al metodo `Product::getPriceStatic()`, che è centrale per il modo in cui PrestaShop determina il prezzo finale di un prodotto. Quando questo metodo viene chiamato, il modulo controlla se il prodotto corrente o le sue categorie associate sono configurate per l'esclusione dagli sconti di gruppo. Se lo sono, garantisce che il componente di sconto di gruppo del calcolo del prezzo venga ignorato.

Il modulo utilizza la classe `Module` standard di PrestaShop per la sua interfaccia di configurazione e si basa sulle voci della tabella `Configuration` per memorizzare le sue impostazioni. Include anche un semplice strumento di ricerca per la selezione dei prodotti nel back office.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce controller front-office o back-office personalizzati. La sua logica è implementata principalmente tramite un override di classe e il metodo `getContent()` del file principale del modulo per la configurazione.

### 4.3 Classi e modelli core (`classes/`)

-   **`exgdisc/override/classes/Product.php`**
    -   **Responsabilità:** Questo è il file più critico del modulo. Sovrascrive la classe `Product` core per modificare il metodo `getPriceStatic()`.
    -   **Nome classe:** `Product` (sovrascrive la classe `Product` originale)
    -   **Classe padre:** `ProductCore`
    -   **Logica chiave:**
        -   Il metodo `getPriceStatic()` sovrascritto chiama prima il `getPriceStatic()` del padre per ottenere il prezzo base.
        -   Recupera quindi la configurazione del modulo (`exgdisc_categories`, `exgdisc_products`) da `Configuration::get()`.
        -   Controlla se l'ID del prodotto corrente (`$id_product`) è nell'elenco `exgdisc_products`.
        -   Controlla anche se una qualsiasi delle categorie associate a `$id_product` è nell'elenco `exgdisc_categories`.
        -   Se una delle due condizioni è vera, significa che il prodotto deve essere escluso dagli sconti di gruppo. Il metodo ricalcola quindi il prezzo, ignorando di fatto il componente di sconto di gruppo che normalmente verrebbe applicato dal metodo `getPriceStatic()` del padre.
        -   Il metodo originale `Product::getPriceStatic()` ha un parametro `$use_group_reduction`. L'override garantisce che, anche se questo è `true`, la riduzione di gruppo non venga applicata se il prodotto è escluso dal modulo.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`exgdisc/lib/searchTool/views/js/autocomplete.js`**
    -   **Ambito:** Back-office (utilizzato nella pagina di configurazione del modulo).
    -   **Scopo:** Fornisce la funzionalità di completamento automatico per la selezione di prodotti specifici nel modulo di configurazione del modulo.
    -   **Logica chiave:**
        -   Inizializza un campo di input di completamento automatico (probabilmente mirato a un elemento con un ID specifico, ad esempio `#product_autocomplete_input`).
        -   Invia richieste AJAX a un controller di amministrazione di PrestaShop (ad esempio, `AdminProducts` o un controller di ricerca personalizzato) per recuperare suggerimenti di prodotti in base all'input dell'utente.
        -   Gestisce la selezione dei prodotti, aggiungendoli a un campo di input nascosto o a un elenco visivo nella pagina di configurazione.
        -   Gestisce la rimozione dei prodotti selezionati dall'elenco.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`exgdisc/lib/searchTool/views/css/autocomplete.css`**
    -   **Ambito:** Back-office (stili lo strumento di ricerca con completamento automatico).
    -   **Scopo:** Fornisce lo stile per l'input di ricerca del prodotto e l'elenco dei prodotti selezionati nella pagina di configurazione del modulo.
    -   **Selettori chiave:** Probabilmente include stili per il menu a discesa di completamento automatico, i tag/badge degli elementi selezionati e possibilmente il campo di input di ricerca stesso. Gli sviluppatori possono sovrascrivere queste classi nei loro temi di amministrazione personalizzati, se necessario.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`exgdisc/lib/searchTool/views/scripts.tpl`**

    -   **Ambito:** Back-office (incluso nella pagina di configurazione del modulo).
    -   **Scopo:** Renderizza la struttura HTML per l'input di ricerca del prodotto e l'area in cui vengono visualizzati i prodotti selezionati. Probabilmente include anche le chiamate JavaScript necessarie per inizializzare lo script `autocomplete.js`.
    -   **Elementi chiave:** Campo di input per la ricerca di prodotti, un contenitore per la visualizzazione dei prodotti selezionati (ad esempio, come tag o elementi di elenco) e campi di input nascosti per memorizzare gli ID dei prodotti selezionati.
-   **`exgdisc/views/script.tpl`**

    -   **Ambito:** Back-office (incluso nella pagina di configurazione del modulo).
    -   **Scopo:** Questo template è probabilmente utilizzato per produrre JavaScript o CSS aggiuntivi specifici per il modulo di configurazione principale, potenzialmente correlati alla validazione del modulo o a elementi UI dinamici. Dato l'hook `ActionAdminControllerSetMedia`, potrebbe essere utilizzato per registrare risorse.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle di database personalizzate.
    -   Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`:
        -   `exgdisc_categories`: Memorizza una stringa serializzata o un elenco di ID di categoria separati da virgole da escludere.
        -   `exgdisc_products`: Memorizza una stringa serializzata o un elenco di ID di prodotto separati da virgole da escludere.
        -   `mypresta_updates`, `update_`, `updatev_`: Relativi al meccanismo di aggiornamento di MyPresta.eu.
        -   `exgdisc_groups`: (Non esplicitamente utilizzato nelle informazioni fornite, ma potrebbe essere un'impostazione legacy o futura per esclusioni specifiche per gruppo).
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un controller di amministrazione viene caricato e i suoi media (JS/CSS) vengono impostati. | Utilizzato dal modulo per caricare il suo JavaScript (`autocomplete.js`) e CSS (`autocomplete.css`) del back-office per la pagina di configurazione, garantendo il funzionamento dello strumento di ricerca dei prodotti. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Disabilita sconto gruppo per prodotti specifici", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il modulo funzioni in modo ottimale con il tuo negozio PrestaShop.
