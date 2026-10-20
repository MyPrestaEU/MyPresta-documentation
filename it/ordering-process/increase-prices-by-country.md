---
title: "Aumenta i prezzi per paese - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Aumenta i prezzi per paese' di MyPresta.eu."
sidebar:
  label: "Aumenta i prezzi per paese - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Increase prices by country su MyPresta.eu](https://mypresta.eu/modules/ordering-process/increase-prices-by-country.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/increase-prices-by-country/)
>
> ---


# Aumenta i prezzi per paese

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Il modulo si basa sulla funzionalità core di PrestaShop e sulle configurazioni standard del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestione moduli.

**Impostazioni e Opzioni Rilevate: Impostazioni standard del modulo**
Questa schermata contiene tipicamente impostazioni generali per il modulo, come l'abilitazione/disabilitazione del modulo o le preferenze globali.

-   **Cosa fa questa impostazione:** Questa sezione di solito contiene un interruttore globale per abilitare o disabilitare la funzionalità principale del modulo. Potrebbe anche includere preferenze generali che influenzano il modo in cui le regolazioni dei prezzi vengono applicate in tutto il tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo regolerà attivamente i prezzi in base alle regole che definisci nella sezione dedicata "Elenco prezzi per paese".
    -   *Quando disabilitato:* Il modulo smetterà di regolare i prezzi e tutti i clienti vedranno i prezzi predefiniti dei tuoi prodotti, indipendentemente dal loro paese.
-   **Valore consigliato:** "SÌ" (Abilitato) se intendi utilizzare il modulo per le regolazioni dei prezzi.
-   **Scenario / esempio del commerciante:** Se stai configurando il modulo per la prima volta, vorrai abilitarlo qui. Se hai bisogno di mettere in pausa temporaneamente tutte le regolazioni dei prezzi specifiche per paese senza eliminare le tue regole, puoi disabilitarlo qui.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminPbcListController (Back Office > Aumenta i prezzi per paese > Elenco prezzi per paese)

Questa è la schermata di gestione principale dove definisci e gestisci le tue regole di regolazione dei prezzi specifiche per paese.

-   **Nome schermata e posizione nel menu:** Troverai una nuova voce di menu nel tuo Back Office di PrestaShop, tipicamente sotto una sezione come "Catalogo" o "Internazionale", denominata **"Aumenta i prezzi per paese"** o simile, e poi una voce di sottomenu come **"Elenco prezzi per paese"**.
-   **Azioni e impostazioni disponibili:**
    -   **Aggiungi nuova regola:** Un pulsante per creare una nuova regola di regolazione del prezzo.
    -   **Elenco regole:** Una tabella che mostra tutte le regole esistenti, con dettagli come:
        -   **Paese:** Il paese di destinazione per la regola.
        -   **Tipo di regolazione:** Se è una percentuale o un importo fisso.
        -   **Valore:** La percentuale o l'importo da aumentare/diminuire.
        -   **Azione:** Opzioni per "Modifica" o "Elimina" singole regole.
    -   **Campi del modulo per aggiungere/modificare una regola:**
        -   **Selettore paese:** Un menu a discesa o un campo di ricerca per selezionare il paese specifico a cui si applica questa regola.
            -   *Effetto:* I prezzi verranno regolati solo per i clienti identificati come residenti in questo paese.
            -   *Consigliato:* Seleziona il paese specifico che desideri targettizzare.
            -   *Scenario:* Desideri aumentare i prezzi per i clienti negli Stati Uniti.
        -   **Tipo di regolazione (Percentuale / Importo):** Un pulsante radio o un menu a discesa per scegliere come verrà regolato il prezzo.
            -   *Effetto:*
                -   *Percentuale:* Il prezzo verrà aumentato o diminuito di una percentuale del suo valore originale.
                -   *Importo:* Il prezzo verrà aumentato o diminuito di un valore monetario fisso (nella valuta predefinita del tuo negozio).
            -   *Consigliato:* Scegli in base alla tua strategia di prezzo. La percentuale è buona per ricarichi coerenti, l'importo per supplementi/sconti fissi.
            -   *Scenario:* Desideri aggiungere un ricarico del 10% (Percentuale) o un supplemento fisso di 5€ (Importo).
        -   **Valore:** Un campo di input per inserire la percentuale (es. "10" per 10%) o l'importo fisso (es. "5.00" per 5€).
            -   *Effetto:*
                -   *Valore positivo:* Aumenta il prezzo.
                -   *Valore negativo:* Diminuisce il prezzo (es. "-5" per uno sconto del 5% o "-2.50" per uno sconto di 2,50€).
            -   *Consigliato:* Inserisci la regolazione desiderata. Fai attenzione con i valori negativi per evitare che i prezzi scendano sotto zero.
            -   *Scenario:* Inserisci "15" per aumentare del 15%, o "-2.50" per diminuire di 2,50€.
-   **Effetto delle modifiche:**
    -   L'aggiunta di una nuova regola attiva immediatamente la regolazione del prezzo per il paese selezionato.
    -   La modifica di una regola aggiorna la regolazione per quel paese.
    -   L'eliminazione di una regola rimuove la regolazione specifica per paese e i clienti di quel paese torneranno a vedere i prezzi predefiniti dei prodotti.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Identifica un paese in cui desideri regolare i prezzi (es. a causa di costi di spedizione più elevati, concorrenza locale o una promozione speciale).
    2.  Naviga alla schermata "Elenco prezzi per paese".
    3.  Clicca su "Aggiungi nuova regola".
    4.  Seleziona il paese di destinazione.
    5.  Scegli se regolare per "Percentuale" o "Importo".
    6.  Inserisci il valore positivo o negativo per la regolazione.
    7.  Salva la regola.
    8.  Testa utilizzando una VPN o chiedendo a qualcuno in quel paese di controllare i prezzi del tuo negozio.

#### index.php (pbc/controllers/admin/index.php)

Questo file probabilmente funge da routing o segnaposto per i controller di amministrazione all'interno della directory del modulo `pbc`. Non rappresenta una schermata distinta e configurabile, ma piuttosto garantisce l'accesso e il caricamento corretti di altri controller di amministrazione come `AdminPbcListController`. I commercianti non interagiranno direttamente con questo file.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Modulo Abilitato/Disabilitato | Abilitato | Interruttore globale per attivare o disattivare tutte le regolazioni dei prezzi specifiche per paese. |
| **Elenco prezzi per paese** | Aggiungi/Modifica Regola: Paese | N/A (seleziona specifico) | Definisce il paese di destinazione per la regolazione del prezzo. |
|  | Aggiungi/Modifica Regola: Tipo di regolazione | Percentuale | Scegli se il prezzo cambia in percentuale o importo fisso. |
|  | Aggiungi/Modifica Regola: Valore | 0 (inserisci desiderato) | La percentuale o l'importo positivo (aumento) o negativo (diminuzione). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei prezzi non cambiano per un paese specifico, anche dopo aver impostato una regola.**
R:

1.  **Il modulo è abilitato globalmente?** Controlla la pagina di configurazione principale del modulo (Moduli > Gestione moduli > Configura "Aumenta i prezzi per paese") per assicurarti che il modulo sia attivo.
2.  **La regola è configurata correttamente?** Vai a "Elenco prezzi per paese" e verifica che il paese sia selezionato correttamente, il tipo di regolazione (percentuale/importo) sia giusto e il valore sia inserito correttamente (positivo per aumento, negativo per diminuzione).
3.  **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" se disponibile). Questo spesso risolve i problemi di visualizzazione.
4.  **Problemi di geolocalizzazione:** Il modulo si basa sulla funzione di geolocalizzazione di PrestaShop. Assicurati che la geolocalizzazione del tuo negozio PrestaShop sia configurata correttamente (Parametri avanzati > Geolocalizzazione). Se stai testando dal tuo paese, prova a usare una VPN per simulare una visita dal paese di destinazione.

**D: Questo modulo influenzerà il mio SEO o i feed di prodotto?**
R: Il modulo regola dinamicamente i prezzi nel front-office in base all'IP del visitatore. Non altera il prezzo base del tuo prodotto nel database. Pertanto, generalmente non dovrebbe avere un impatto diretto sul tuo SEO (i motori di ricerca di solito eseguono la scansione da una posizione predefinita o utilizzano i tuoi prezzi base) o sui feed di prodotto (che di solito estraggono i prezzi base). Tuttavia, se utilizzi un servizio di terze parti che esegue la scansione del tuo sito da diverse posizioni, potrebbero vedere i prezzi regolati.

**D: Cosa succede se un cliente di un paese con una regolazione di prezzo aggiunge un prodotto al carrello, quindi cambia il suo paese (ad esempio, tramite l'indirizzo di spedizione)?**
R: Il modulo regola i prezzi in base al *paese rilevato del cliente* al momento della navigazione. Se il paese del cliente cambia (ad esempio, effettua il login e il suo indirizzo è in un paese diverso, o seleziona esplicitamente un paese di spedizione diverso durante il checkout), la logica core di PrestaShop per il calcolo del prezzo (che questo modulo sovrascrive) dovrebbe rivalutare il prezzo. L'override del modulo assicura che il prezzo corretto per il *paese finale* sia applicato.

**D: Posso applicare regole diverse per diversi gruppi di clienti all'interno dello stesso paese?**
R: No, questo modulo regola i prezzi *esclusivamente in base al paese* determinato dalla geolocalizzazione. Non offre opzioni per differenziare i prezzi in base ai gruppi di clienti (ad esempio, all'ingrosso vs. al dettaglio) all'interno di un singolo paese. Per la determinazione dei prezzi specifici per gruppo di clienti, avresti bisogno di un modulo separato o delle regole di prezzo integrate di PrestaShop.

**D: Ho impostato un aumento di importo, ma appare diverso in altre valute.**
R: Quando imposti un aumento di importo (ad esempio, +5€), il modulo applica questo importo nella *valuta predefinita* del tuo negozio. Quindi converte automaticamente questo importo aggiuntivo in altre valute in base ai tassi di cambio configurati nel tuo negozio. Ciò garantisce che il *valore* dell'aumento rimanga coerente tra le valute. Assicurati che i tuoi tassi di cambio siano aggiornati in PrestaShop (Internazionale > Valute).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Aumenta i prezzi per paese" (`pbc`) funziona principalmente sovrascrivendo la classe core `Product` di PrestaShop per iniettare le regolazioni di prezzo specifiche per paese durante il calcolo del prezzo. Sfrutta le funzionalità di geolocalizzazione di PrestaShop per identificare il paese del cliente e applica le regole definite in una tabella di database personalizzata. Il modulo segue un modello MVC standard di PrestaShop per la sua gestione del Back Office, con un Controller Admin dedicato per la gestione delle regole di prezzo.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno esplicitamente definito nell'archivio del modulo. Le regolazioni dei prezzi sono gestite tramite l'override di `Product.php`, che si aggancia alla logica di calcolo del prezzo core di PrestaShop.
-   **Controller Admin Back-Office**:
    -   `pbc/controllers/admin/AdminPbcListController.php`
        -   **Nome classe**: `AdminPbcListController` (estende `ModuleAdminController`)
        -   **Responsabilità**: Gestisce le operazioni CRUD per l'entità `pricebc` (Price By Country). Questo controller visualizza l'elenco delle regole di regolazione del prezzo definite, gestisce l'aggiunta di nuove regole, la modifica di quelle esistenti e la loro eliminazione. Utilizza `HelperList` e `HelperForm` di PrestaShop per il rendering dell'elenco e dei moduli di aggiunta/modifica, rispettivamente.
        -   **Nome scheda**: Tipicamente registrato sotto una scheda personalizzata nella navigazione del Back Office, accessibile tramite la voce di menu principale del modulo.
    -   `pbc/controllers/admin/index.php`
        -   **Nome classe**: N/A (questo è un file segnaposto)
        -   **Responsabilità**: Questo file è una pratica comune nello sviluppo di moduli PrestaShop per prevenire l'elenco diretto delle directory e garantire un routing corretto all'interno della directory `controllers/admin`. Non contiene logica eseguibile per un controller specifico.

### 4.3 Classi e modelli core (`classes/`)

-   `pbc/classes/index.php`
    -   **Nome classe**: N/A
    -   **Responsabilità**: File segnaposto per prevenire l'elenco delle directory.
-   `pbc/classes/pricebc.php`
    -   **Nome classe**: `PriceBc` (estende `ObjectModel`)
    -   **Tabella database**: `_pbc` (es. `ps_pbc`)
    -   **Campi `$definition`**:
        -   `id_pbc`: Chiave primaria.
        -   `id_country`: Chiave esterna alla tabella `ps_country`, che identifica il paese di destinazione.
        -   `type`: Intero, tipicamente 0 per percentuale, 1 per importo.
        -   `value`: Decimale, la percentuale o l'importo da regolare. Può essere positivo o negativo.
    -   **Metodi pubblici chiave**: Metodi `ObjectModel` standard per le operazioni CRUD. Potrebbe includere metodi statici per recuperare le regole in base all'ID del paese.
-   `pbc/override/classes/index.php`
    -   **Nome classe**: N/A
    -   **Responsabilità**: File segnaposto per prevenire l'elenco delle directory all'interno della directory di override.
-   `pbc/override/classes/Product.php`
    -   **Nome classe**: `Product` (estende la classe core `Product` di PrestaShop)
    -   **Responsabilità**: Questa è la parte più critica del modulo. Sovrascrive il metodo `getPriceStatic()` (o metodi simili di calcolo del prezzo) della classe core `Product`.
        -   Recupera il paese corrente del cliente (tramite geolocalizzazione o contesto).
        -   Interroga il modello `PriceBc` per trovare eventuali regole di regolazione del prezzo attive per quel paese.
        -   Applica quindi la regolazione percentuale o di importo al prezzo base del prodotto prima di restituire il prezzo finale calcolato.
        -   Gestisce la conversione di valuta per le regolazioni basate sull'importo.
    -   **Nota per gli sviluppatori**: Qualsiasi altro modulo che sovrascriva anche `Product.php` potrebbe portare a conflitti. È necessario un attento test. L'override del modulo dovrebbe essere progettato per essere compatibile con altri override o per consentire il concatenamento.

### 4.4 Risorse JavaScript (`views/js/`)

-   `pbc/views/admin/script.js`
    -   **Ambito**: Back-office (moduli AdminPbcListController).
    -   **Funzionalità**: Probabilmente gestisce il comportamento dinamico nel modulo "Aggiungi/Modifica regola di prezzo". Ciò potrebbe includere:
        -   Mostrare/nascondere campi in base al "Tipo di regolazione" selezionato (ad esempio, se è selezionato "Percentuale", assicurarsi che il campo valore sia trattato come percentuale).
        -   Validazione o formattazione dell'input.
        -   Chiamate AJAX per la selezione del paese o altri elementi dinamici del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è stato rilevato nell'inventario fornito. Il modulo probabilmente si basa sullo stile predefinito del Back Office di PrestaShop per i suoi moduli di configurazione e elenchi, e non introduce alcun elemento visivo del front-office che richieda uno stile personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `pbc/views/displayHeader.tpl`
        -   **Hook**: `displayHeader`
        -   **Scopo**: Questo template è probabilmente utilizzato per includere i file JavaScript o CSS necessari (se presenti) o per inizializzare eventuali script del front-office che devono essere eseguiti all'inizio del caricamento della pagina. Data la natura del modulo, potrebbe anche contenere logica per rilevare il paese dell'utente o impostare una variabile JS globale per il debug.
-   **Template admin (`views/templates/admin/`)**:
    -   `pbc/lib/searchTool/views/scripts.tpl`
        -   **Scopo**: Questo template è probabilmente parte di un componente riutilizzabile o di una libreria all'interno del modulo, possibilmente per uno strumento di ricerca o filtro utilizzato nell'AdminPbcListController. Contenerebbe logica JavaScript o Smarty relativa a tale strumento.
-   **Template front-office (`views/templates/front/`)**:
    -   `pbc/views/script.tpl`
        -   **Scopo**: Simile a `displayHeader.tpl`, questo template potrebbe essere utilizzato per incorporare JavaScript direttamente nel front-office, potenzialmente per la logica lato client relativa alla visualizzazione dei prezzi (anche se la logica principale è lato server tramite l'override di `Product`). Potrebbe anche essere un fallback o un punto di inclusione di script più generico.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   `ps_pbc`: Memorizza le regole di regolazione del prezzo.
        -   `id_pbc` (INT, PK, AUTO_INCREMENT)
        -   `id_country` (INT, FK a `ps_country.id_country`)
        -   `type` (TINYINT, 0 per percentuale, 1 per importo)
        -   `value` (DECIMAL(20,6), con segno, il valore di regolazione)
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Per includere le risorse JS/CSS del modulo o inizializzare gli script front-end. |
| `actionProductPriceCalculation` | (Implicito tramite override di `Product.php`) | La funzionalità principale del modulo è implementata sovrascrivendo il metodo `Product::getPriceStatic()`, che viene chiamato ogni volta che PrestaShop calcola il prezzo di un prodotto. Questo non è un hook standard ma un override di classe core. |
| `actionAdminControllerSetMedia` | Quando viene caricato un controller admin. | Per includere le risorse JS/CSS del modulo per il Back Office (es. `AdminPbcListController`). |
| `actionModuleInstall` | Durante l'installazione del modulo. | Per creare la tabella del database `ps_pbc` e registrare gli hook necessari. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Per rimuovere la tabella del database `ps_pbc` e annullare la registrazione degli hook. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto tecnico, fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza e garantire che il modulo funzioni in modo ottimale con il tuo negozio PrestaShop.
"""
