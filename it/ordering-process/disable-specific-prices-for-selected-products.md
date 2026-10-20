---
title: "Disabilita prezzi specifici per prodotti selezionati - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Disabilita prezzi specifici per prodotti selezionati' di MyPresta.eu."
sidebar:
  label: "Disabilita prezzi specifici per prodotti selezionati - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Disable specific prices for selected products su MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/disable-specific-prices-for-selected-products/)
>
> ---


# Disabilita prezzi specifici per prodotti selezionati

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni. Questa è la schermata di configurazione principale e unica per questo modulo.

#### **Impostazioni Generali**

-   **Disabilita prezzi specifici per prodotti selezionati**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per abilitare o disabilitare la funzionalità principale del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato (SÌ):* Il modulo impedirà attivamente l'applicazione di prezzi specifici ai prodotti e alle categorie selezionati di seguito.
        -   *Quando Disabilitato (NO):* Il modulo sarà inattivo. Tutti i prezzi specifici e le regole di prezzo del catalogo si applicheranno a tutti i prodotti normalmente, indipendentemente dalle tue selezioni nei campi "Categorie" o "Prodotti specifici".
    -   **Valore consigliato:** **SÌ** se intendi utilizzare la funzionalità del modulo per escludere prodotti dagli sconti. **NO** se vuoi disabilitarlo temporaneamente senza perdere le tue configurazioni salvate.
    -   **Scenario / esempio commerciante:** Hai appena lanciato una nuova linea di prodotti premium e vuoi assicurarti che non vengano mai scontati. Abiliti questa impostazione e poi aggiungi quei prodotti all'elenco di esclusione.

#### **Criteri di Esclusione**

-   **Categorie**

    -   **Cosa fa questa impostazione:** Questo campo ti consente di selezionare intere categorie di prodotti i cui prodotti dovrebbero essere esclusi dai prezzi specifici.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando le categorie sono selezionate:* Tutti i prodotti appartenenti alle categorie selezionate (incluse le sottocategorie, a seconda della struttura delle categorie di PrestaShop e di come vengono applicati i prezzi specifici) avranno i prezzi specifici disabilitati.
        -   *Quando nessuna categoria è selezionata:* Solo i prodotti esplicitamente elencati nel campo "Prodotti specifici" saranno interessati.
    -   **Valore consigliato:** Seleziona le categorie che contengono prodotti che vuoi costantemente proteggere dagli sconti, come "Nuovi Arrivi", "Beni di Lusso" o "Liquidazione (se vuoi applicare solo sconti manuali)".
    -   **Scenario / esempio commerciante:** Hai una categoria "Marchi Premium". Selezionandola qui, tutti i prodotti all'interno di quella categoria saranno automaticamente esclusi dai calcoli dei prezzi specifici, risparmiandoti di elencare ogni prodotto individualmente.
-   **Prodotti specifici**

    -   **Cosa fa questa impostazione:** Questo campo ti consente di cercare e selezionare singoli prodotti che dovrebbero essere esclusi dai prezzi specifici. Utilizza uno strumento di ricerca con completamento automatico per aiutarti a trovare rapidamente i prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando i prodotti sono selezionati:* I singoli prodotti scelti avranno i prezzi specifici disabilitati, indipendentemente dalla loro categoria.
        -   *Quando nessun prodotto è selezionato:* Solo i prodotti all'interno delle "Categorie" selezionate saranno interessati.
    -   **Valore consigliato:** Usalo per articoli individuali che non rientrano in un'esclusione di categoria più ampia, o per specifici best-seller che vuoi mantenere a prezzo pieno.
    -   **Scenario / esempio commerciante:** Hai alcuni gadget molto richiesti che vendono sempre bene a prezzo pieno. Cerchi "iPhone 15" e "Samsung Galaxy S24" e li aggiungi a questa lista per assicurarti che non vengano mai scontati da prezzi specifici.

#### **Salvataggio delle modifiche**

Dopo aver apportato modifiche alle impostazioni, ricorda di cliccare sul pulsante **"Salva"** in fondo alla pagina di configurazione per applicarle.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Disabilita prezzi specifici per prodotti selezionati | SÌ | Interruttore principale per abilitare/disabilitare la funzionalità del modulo. SÌ significa che le esclusioni sono attive. |
| Pagina di configurazione del modulo | Categorie | Nessuna selezionata | Seleziona le categorie i cui prodotti saranno esclusi dai prezzi specifici. |
| Pagina di configurazione del modulo | Prodotti specifici | Nessuno selezionato | Cerca e seleziona singoli prodotti da escludere dai prezzi specifici. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho configurato il modulo, ma i prezzi specifici si applicano ancora ai miei prodotti esclusi. Cosa c'è che non va?**
R1:

-   **Controlla lo stato del modulo:** Innanzitutto, assicurati che l'impostazione "Disabilita prezzi specifici per prodotti selezionati" nella pagina di configurazione del modulo sia impostata su **SÌ (Abilitato)**.
-   **Verifica le esclusioni:** Ricontrolla che i prodotti o le categorie specifiche che intendi escludere siano correttamente selezionati nelle impostazioni del modulo. Usa la funzione di ricerca con attenzione per i prodotti.
-   **Svuota la cache:** PrestaShop spesso memorizza nella cache le informazioni sui prezzi. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. Svuota anche la cache del tuo browser.
-   **Priorità del prezzo specifico:** Assicurati che la regola di prezzo specifica che stai testando non stia in qualche modo sovrascrivendo il modulo. Questo modulo funziona sovrascrivendo il calcolo del prezzo specifico di base di PrestaShop. Se hai altri moduli che modificano anche i prezzi, potrebbe esserci un conflitto. Prova a disabilitare temporaneamente altri moduli relativi ai prezzi per diagnosticare.

**D2: Questo modulo influirà sulle mie Regole Carrello (voucher)?**
R2: Sì, indirettamente. Questo modulo impedisce l'applicazione di prezzi specifici ai prodotti selezionati. Se una Regola Carrello (voucher) offre uno sconto che *si basa* o interagisce con il meccanismo di prezzo specifico di PrestaShop (ad esempio, uno sconto percentuale che calcola in base al prezzo corrente del prodotto *dopo* i prezzi specifici), allora i prodotti esclusi non riceveranno quella riduzione di prezzo specifica prima che il voucher venga applicato. Il voucher si applicherà quindi al prezzo base del prodotto (o al suo prezzo dopo altri sconti non specifici).

**D3: Questo modulo funziona con configurazioni multi-negozio?**
R3: La configurazione del modulo è tipicamente globale o legata al contesto in cui ti trovi quando la configuri. Se hai una configurazione multi-negozio, testa accuratamente per assicurarti che le esclusioni si applichino come previsto in tutti i negozi pertinenti. Il meccanismo di `override` di PrestaShop di solito si applica globalmente, ma le regole di prezzo specifiche stesse possono essere specifiche del negozio.

**D4: Ho aggiunto un nuovo prodotto a una categoria esclusa, ma sta ancora ricevendo prezzi specifici. Perché?**
R4:

-   **Cache:** Svuota sempre la cache di PrestaShop (**Parametri Avanzati > Prestazioni**) dopo aver apportato modifiche a categorie o prodotti, specialmente se stai aggiungendo nuovi articoli o li stai spostando tra le categorie.
-   **Struttura della categoria:** Assicurati che la regola di prezzo specifica non venga applicata in un modo che bypassi l'esclusione della categoria (ad esempio, una regola per "tutti i prodotti" che non rispetta la gerarchia delle categorie). Il modulo dovrebbe intercettare il calcolo del prezzo specifico a prescindere, ma la cache è spesso la causa.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Disabilita prezzi specifici per prodotti selezionati" sfrutta il sistema di override di PrestaShop per modificare la logica di prezzo principale. In particolare, sovrascrive le classi `Product` e `SpecificPrice` per iniettare la sua logica di esclusione direttamente nel processo di calcolo del prezzo. Ciò garantisce che quando PrestaShop tenta di determinare il prezzo di un prodotto, il modulo verifica prima se il prodotto o la sua categoria è nell'elenco di esclusione e, in tal caso, impedisce l'applicazione di prezzi specifici. Il modulo utilizza una struttura standard di moduli PrestaShop, con un file di modulo principale, override e `views` per risorse e template.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller Front-Office o Back-Office Admin personalizzato. La sua configurazione è gestita direttamente all'interno del metodo `getContent()` del file del modulo principale e la sua funzionalità principale è implementata tramite override di classe.

### 4.3 Classi e Modelli Core (`classes/`)

-   **`exsp/override/classes/index.php`**:

    -   **Nome classe e classe padre**: `Product` (sovrascrive la classe `Product` core di PrestaShop).
    -   **Responsabilità**: Questo override è il meccanismo primario per intercettare i calcoli del prezzo del prodotto. Modifica il metodo `getPrice()` (o metodi correlati) per verificare se il prodotto corrente (o la sua categoria) è configurato per l'esclusione. Se lo è, il componente del prezzo specifico del calcolo viene bypassato, garantendo che il prezzo base del prodotto venga restituito senza alcuna riduzione di prezzo specifica. Questo è cruciale per impedire l'applicazione di prezzi specifici a livello di prodotto.
    -   **Metodi pubblici chiave**: Il metodo `getPrice()` sovrascritto (o metodi simili di calcolo del prezzo all'interno della classe `Product`) conterrà la logica per controllare i valori di configurazione `exsp_categories` e `exsp_products`.
-   **`exsp/override/classes/SpecificPrice.php`**:

    -   **Nome classe e classe padre**: `SpecificPrice` (sovrascrive la classe `SpecificPrice` core di PrestaShop).
    -   **Responsabilità**: Questo override influisce direttamente sul modo in cui i prezzi specifici vengono recuperati e applicati. Modifica metodi come `getSpecificPrice()` o `getSpecificPrices()` per filtrare o ignorare le regole di prezzo specifiche per i prodotti che sono nell'elenco di esclusione. Questo agisce come un secondo livello di difesa, garantendo che anche se esiste una regola di prezzo specifica, non verrà considerata per i prodotti esclusi.
    -   **Metodi pubblici chiave**: I metodi sovrascritti relativi al recupero o all'applicazione di prezzi specifici incorporeranno controlli rispetto agli elenchi di esclusione del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`exsp/lib/searchTool/views/js/autocomplete.js`**:

    -   **Ambito**: Back-office (pagina di configurazione del modulo).
    -   **Descrizione**: Questo script fornisce la funzionalità di completamento automatico per il campo di input "Prodotti specifici" nella pagina di configurazione del modulo. Probabilmente utilizza AJAX per interrogare il database dei prodotti di PrestaShop mentre l'utente digita, suggerendo nomi di prodotti corrispondenti. Gestisce la visualizzazione dei suggerimenti e la selezione dei prodotti da aggiungere all'elenco di esclusione.
    -   **Listener di eventi**: Eventi keyup sull'input di ricerca del prodotto, eventi click sui suggerimenti di completamento automatico.
    -   **Manipolazione del DOM**: Crea e aggiorna dinamicamente l'elenco dei suggerimenti, aggiunge i prodotti selezionati a un input nascosto o a un'area di visualizzazione.
-   **`exsp/views/js/exsp.js`**:

    -   **Ambito**: Back-office (pagina di configurazione del modulo).
    -   **Descrizione**: Questo è il file JavaScript principale per l'interfaccia di configurazione del modulo. Gestisce l'inizializzazione dello strumento di ricerca con completamento automatico, gestisce la visualizzazione e la rimozione dei prodotti/categorie selezionati e potenzialmente esegue altre interazioni UI specifiche delle impostazioni del modulo.
    -   **Listener di eventi**: Eventi click per la rimozione di prodotti/categorie selezionati, potenzialmente eventi change per l'interruttore principale di abilitazione/disabilitazione.
    -   **Manipolazione del DOM**: Gestisce la rappresentazione visiva delle categorie e dei prodotti selezionati, aggiorna i campi di input nascosti che memorizzano i valori di configurazione.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`exsp/lib/searchTool/views/css/autocomplete.css`**:
    -   **Ambito**: Back-office (pagina di configurazione del modulo).
    -   **Descrizione**: Questo foglio di stile fornisce lo stile visivo per l'input di ricerca con completamento automatico e il suo elenco di suggerimenti. Definisce l'aspetto della casella di ricerca, dei suggerimenti a discesa e potenzialmente degli stati hover/attivi per una migliore esperienza utente.
    -   **Componenti UI principali**: `.autocomplete-container`, `.autocomplete-suggestions`, `.autocomplete-suggestion`.
    -   **Selettori di classe CSS chiave**: `.exsp-product-search-input`, `.exsp-selected-item`, `.exsp-remove-item`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`exsp/lib/searchTool/views/scripts.tpl`**:

    -   **Ambito**: Back-office (pagina di configurazione del modulo).
    -   **Descrizione**: Questo template probabilmente include i file JavaScript e CSS necessari per lo strumento di ricerca con completamento automatico, oppure potrebbe contenere JavaScript inline per inizializzare il widget di completamento automatico con parametri specifici (ad esempio, URL AJAX per la ricerca di prodotti).
    -   **Renderizzato in**: Hook `ActionAdminControllerSetMedia` o direttamente all'interno di `getContent()`.
-   **`exsp/views/script.tpl`**:

    -   **Ambito**: Back-office (pagina di configurazione del modulo).
    -   **Descrizione**: Questo template è responsabile del rendering del modulo di configurazione principale del modulo. Include la struttura HTML per l'interruttore di abilitazione/disabilitazione, il campo di selezione della categoria e l'input di ricerca del prodotto con la sua visualizzazione associata per i prodotti selezionati. Probabilmente include anche gli script `exsp.js` e `autocomplete.js`.
    -   **Renderizzato in**: Metodo `getContent()` di `exsp.php`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione (stato abilitato, categorie escluse, prodotti esclusi) nella tabella `ps_configuration` di PrestaShop.
        -   `exsp_categories`: Memorizza un array serializzato o un elenco di ID di categoria separati da virgole da escludere.
        -   `exsp_products`: Memorizza un array serializzato o un elenco di ID di prodotto separati da virgole da escludere.
        -   `exsp_enabled`: Memorizza lo stato abilitato/disabilitato del modulo (ad esempio, `1` per abilitato, `0` per disabilitato).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin viene caricato, prima che il suo contenuto venga renderizzato. | Utilizzato per registrare e includere le risorse JavaScript e CSS del modulo (ad esempio, per lo strumento di ricerca con completamento automatico) nella pagina di configurazione del modulo. |
| (Hook Impliciti tramite Override) | Durante il calcolo del prezzo del prodotto (`Product::getPrice()`) e il recupero del prezzo specifico (`SpecificPrice::getSpecificPrices()`). | La funzionalità principale del modulo è implementata sovrascrivendo le classi `Product` e `SpecificPrice` di PrestaShop. Ciò significa che la logica del modulo viene eseguita ogni volta che questi metodi core vengono chiamati, "agganciandosi" efficacemente al processo di calcolo del prezzo senza registrare esplicitamente un hook `display` o `action`. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Disabilita prezzi specifici per prodotti selezionati", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema tecnico o domanda che tu possa avere riguardo alla funzionalità del modulo.
