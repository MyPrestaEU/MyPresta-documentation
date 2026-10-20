---
title: "Editor di combinazioni di prodotti in massa - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Editor di combinazioni di prodotti in massa' di MyPresta.eu."
sidebar:
  label: "Editor di combinazioni di prodotti in massa - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Mass product combinations editor su MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-product-combinations-editor.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/mass-product-combinations-editor/)
>
> ---


# Editor di combinazioni di prodotti in massa

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito speciale del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Editor di combinazioni di prodotti in massa)

Dopo aver cliccato su "Configura" per il modulo "Editor di combinazioni di prodotti in massa", verrai indirizzato a un'interfaccia di amministrazione dedicata. È qui che eseguirai tutte le tue modifiche in massa alle combinazioni.

La pagina di configurazione principale per questo modulo funge da interfaccia primaria. Non ha una tradizionale "scheda delle impostazioni" con interruttori e campi di input per il modulo stesso, ma piuttosto È lo strumento per modificare le combinazioni.

Ecco una ripartizione di ciò che vedrai e come usarlo:

**Nome schermata e posizione nel menu:**

-   **Percorso menu:** Dopo l'installazione, di solito troverai una nuova voce di menu sotto **Catalogo** o **Moduli** (a seconda della tua versione e tema PrestaShop) oppure puoi sempre accedervi tramite **Moduli > Gestione moduli** e cliccando su "Configura" accanto a "Editor di combinazioni di prodotti in massa".
-   **Titolo schermata:** "Editor di combinazioni di prodotti in massa" o simile.

**Azioni e impostazioni disponibili:**

L'interfaccia principale ti presenterà una potente griglia o tabella che elenca le combinazioni di prodotti. L'aspetto esatto può variare leggermente tra le versioni di PrestaShop, ma la funzionalità principale rimane coerente.

1.  **Selezione / Filtro prodotto:**

    -   **Cosa fa:** Quest'area ti consente di selezionare le combinazioni di quali prodotti desideri modificare. Potresti vedere una barra di ricerca, un menu a discesa per i prodotti o filtri per categoria, produttore, ecc.
    -   **Effetto della modifica di questa impostazione:** Selezionando un prodotto o applicando filtri, la tabella sottostante verrà popolata solo con le combinazioni appartenenti ai prodotti scelti. Questo è fondamentale per restringere il tuo focus.
    -   **Valore consigliato:** Inizia cercando un prodotto specifico o filtrando per categoria per familiarizzare con l'interfaccia.
    -   **Scenario / esempio del commerciante:** Desideri aggiornare lo stock per tutte le combinazioni del tuo prodotto "T-Shirt Estiva". Cercheresti "T-Shirt Estiva" e lo selezioneresti.
2.  **Tabella di elenco delle combinazioni:**

    -   **Cosa fa:** Questo è il cuore del modulo. Visualizza una tabella in cui ogni riga rappresenta una combinazione di prodotto unica (ad esempio, "T-Shirt - Rossa - Piccola"). Le colonne rappresentano campi modificabili come:
        -   **Riferimento:** Codice prodotto interno per questa specifica combinazione.
        -   **EAN13 / UPC:** Numeri di codice a barre.
        -   **Quantità:** Livello di stock per questa combinazione.
        -   **Impatto sul prezzo:** Come questa combinazione influisce sul prezzo base del prodotto (ad esempio, +$5 per la taglia XL).
        -   **Prezzo all'ingrosso:** Il prezzo di costo di questa combinazione.
        -   **Peso:** Come questa combinazione influisce sul peso base del prodotto.
        -   **Quantità minima:** Il numero minimo di questa combinazione che un cliente deve acquistare.
        -   **Combinazione predefinita:** Una casella di controllo per contrassegnare una combinazione come predefinita per il prodotto.
        -   **Immagine:** L'immagine associata a questa combinazione.
    -   **Effetto della modifica di questa impostazione:** Puoi cliccare direttamente nelle celle di questa tabella e digitare nuovi valori. Ad esempio, cambiare la "Quantità" da 5 a 10 aggiornerà il livello di stock per quella specifica combinazione.
    -   **Valore consigliato:** Rivedi attentamente ogni combinazione e i suoi valori attuali prima di apportare modifiche.
    -   **Scenario / esempio del commerciante:** Hai appena ricevuto una nuova spedizione. Puoi scorrere la colonna "Quantità" e aggiornare i livelli di stock per tutte le combinazioni pertinenti in pochi secondi.
3.  **Pulsante Salva:**

    -   **Cosa fa:** Dopo aver apportato tutte le modifiche desiderate nella tabella, **devi** cliccare su un pulsante "Salva" o "Applica modifiche" (di solito si trova nella parte superiore o inferiore della tabella) per confermare le tue modifiche al database.
    -   **Effetto della modifica di questa impostazione:** Fino a quando non clicchi su salva, le tue modifiche sono visibili solo sullo schermo e non sono attive nel tuo negozio. Cliccando su salva vengono applicate tutte le modifiche in sospeso.
    -   **Valore consigliato:** Salva sempre il tuo lavoro frequentemente, specialmente dopo aver apportato un gruppo di modifiche.
    -   **Scenario / esempio del commerciante:** Hai aggiornato i prezzi per 20 combinazioni. Clicca su "Salva" per rendere questi nuovi prezzi attivi sulle tue pagine prodotto.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1.  **Identifica il tuo compito:** Devi aggiornare lo stock, cambiare i prezzi o modificare i riferimenti?
2.  **Naviga al modulo:** Vai su **Moduli > Gestione moduli** e clicca su "Configura" per "Editor di combinazioni di prodotti in massa".
3.  **Seleziona i prodotti:** Usa le opzioni di ricerca o filtro per caricare le combinazioni con cui devi lavorare.
4.  **Apporta modifiche:** Modifica direttamente i valori nelle celle della tabella. Spesso puoi usare scorciatoie da tastiera (come Tab) per spostarti rapidamente tra i campi.
5.  **Rivedi:** Ricontrolla le tue modifiche prima di salvare.
6.  **Salva:** Clicca sul pulsante "Salva" per applicare tutte le modifiche.
7.  **Svuota cache (se necessario):** In alcuni casi, specialmente dopo importanti modifiche di prezzo o stock, è buona pratica svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni**) per assicurarsi che le modifiche siano immediatamente visibili nel front office.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Selezione/Filtro prodotto | (Varia in base al prodotto) | Restringe le combinazioni visualizzate per la modifica. |
| Pagina di configurazione del modulo | Tabella di elenco delle combinazioni (es. Quantità, Impatto sul prezzo, Riferimento, EAN13) | (Varia in base al prodotto) | Modifica diretta degli attributi della combinazione. Le modifiche vengono applicate alla combinazione selezionata. |
| Pagina di configurazione del modulo | Pulsante Salva | Clicca dopo le modifiche | Conferma tutte le modifiche sullo schermo al database, rendendole attive nel tuo negozio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Le mie modifiche non vengono visualizzate nel front office dopo aver salvato!**
R: Questo è di solito un problema di cache. Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota cache" (o "Svuota cache Smarty" / "Svuota cache" a seconda della tua versione). Le tue modifiche dovrebbero quindi apparire.

**D: Il modulo è lento a caricare le combinazioni per prodotti con molte varianti.**
R: Per prodotti con centinaia o migliaia di combinazioni, il caricamento di tutti i dati può richiedere tempo. Questo è normale a causa della quantità di dati elaborati. Assicurati che il tuo server soddisfi le specifiche raccomandate da PrestaShop. Se è costantemente molto lento, controlla il limite di memoria PHP e le impostazioni del tempo di esecuzione del tuo server (il tuo provider di hosting può aiutarti con questo).

**D: Posso annullare le modifiche apportate con questo modulo?**
R: Il modulo aggiorna direttamente il tuo database. Non esiste un pulsante "annulla" integrato. Questo è il motivo per cui è fondamentale **avere sempre un backup recente del tuo negozio** prima di apportare modifiche in massa. Se commetti un errore, dovrai correggere manualmente i valori o ripristinare da un backup.

**D: Non riesco a trovare il modulo nel menu dopo l'installazione.**
R: Dopo l'installazione, naviga su **Moduli > Gestione moduli**. Cerca "Editor di combinazioni di prodotti in massa" e clicca sul pulsante "Configura" accanto ad esso. Questo ti porterà sempre all'interfaccia del modulo. A seconda della tua versione e tema di PrestaShop, un link diretto nel menu potrebbe apparire sotto "Catalogo" o "Moduli" per un accesso più rapido.

**D: Questo modulo funziona con temi personalizzati?**
R: Sì, questo modulo opera interamente all'interno del Back Office di PrestaShop. Non produce alcun elemento del front office, quindi dovrebbe essere completamente compatibile con qualsiasi tema personalizzato senza conflitti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Editor di combinazioni di prodotti in massa" (`qce`) è principalmente uno strumento di amministrazione del Back-Office. Sfrutta la classe `Module` di PrestaShop per la sua funzionalità principale e utilizza un endpoint AJAX personalizzato per gestire il caricamento dinamico e il salvataggio dei dati delle combinazioni di prodotti. L'interfaccia del modulo è renderizzata tramite un template Smarty, con JavaScript che gestisce le interazioni dell'utente e l'invio dei dati. Interagisce direttamente con le strutture dati principali di prodotti e combinazioni di PrestaShop senza introdurre nuove classi `ObjectModel` o tabelle di database.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza classi `ModuleFrontController` o `AdminController` dedicate nella directory `controllers/`. Tutta la logica del Back-Office, incluso l'endpoint AJAX, è gestita direttamente all'interno del file principale del modulo `qce/ajax_qce.php` tramite il metodo `getContent()`.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non introduce alcuna classe personalizzata in una directory `classes/`. Utilizza direttamente le classi principali di PrestaShop, come `Product`, `Combination`, `Tools`, `Configuration`, ecc., per recuperare e aggiornare i dati.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`qce/views/admin/js/qce.js`**
    -   **Ambito:** Back-office (pannello di amministrazione).
    -   **Scopo:** Questo è il file JavaScript principale per l'interfaccia del modulo. Gestisce:
        -   **Selezione prodotto:** Probabilmente gestisce il menu a discesa o il campo di ricerca per la selezione di un prodotto.
        -   **Caricamento dati AJAX:** Invia richieste AJAX al metodo `getContent()` del modulo (o a un gestore AJAX specifico al suo interno) per recuperare i dati delle combinazioni per il prodotto selezionato.
        -   **Rendering della tabella:** Popola dinamicamente la tabella HTML con i dati delle combinazioni ricevuti dal server.
        -   **Modifica in loco:** Implementa la funzionalità per gli utenti di cliccare sulle celle della tabella e modificare direttamente i valori (ad esempio, campi di input che appaiono al clic).
        -   **Validazione dei dati:** Può includere la validazione lato client per i campi di input (ad esempio, assicurarsi che la quantità sia un numero).
        -   **Salvataggio dati AJAX:** Raccoglie tutti i dati delle combinazioni modificati dalla tabella e li invia tramite AJAX al metodo `getContent()` del modulo per l'elaborazione e il salvataggio nel database.
        -   **Feedback utente:** Visualizza spinner di caricamento, messaggi di successo o avvisi di errore.
        -   **Listener di eventi:** Collega listener a elementi come menu a discesa di selezione prodotto, campi di input all'interno della tabella e il pulsante "Salva".

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`qce/lib/blue/style.css`**
    -   **Ambito:** Back-office (pannello di amministrazione).
    -   **Scopo:** Questo sembra essere un foglio di stile di terze parti o generico, possibilmente per un componente UI o un tema di stile specifico utilizzato all'interno dell'interfaccia del modulo. Probabilmente definisce stili generali di tabella, stili di campi di input o estetica dei pulsanti. Gli sviluppatori dovrebbero ispezionare questo file per comprenderne l'impatto sulla presentazione visiva del modulo.
-   **`qce/views/admin/css/qce.css`**
    -   **Ambito:** Back-office (pannello di amministrazione).
    -   **Scopo:** Questo è il foglio di stile specifico del modulo. Contiene regole CSS personalizzate per stilizzare la tabella di modifica delle combinazioni, gli elementi di selezione del prodotto e qualsiasi altro componente UI unico all'interno della pagina di configurazione del modulo.
    -   **Selettori di classi CSS chiave:** Gli sviluppatori che desiderano sovrascrivere o personalizzare l'aspetto del modulo dovrebbero ispezionare questo file per nomi di classi come `.qce-table`, `.qce-product-selector`, `.qce-input-field`, ecc., e indirizzarli nel loro tema amministrativo personalizzato o sovrascrivendo il CSS del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`qce/views/admin/qce.tpl`**
    -   **Ambito:** Template amministrativo.
    -   **Scopo:** Questo è il file template Smarty principale responsabile del rendering dell'intera interfaccia dell'"Editor di combinazioni di prodotti in massa" all'interno del Back Office di PrestaShop.
    -   **Contenuto:** Tipicamente include:
        -   La struttura HTML per l'area di selezione/filtro del prodotto.
        -   Il segnaposto (ad esempio, un `<table>` o `<div>` vuoto) dove i dati delle combinazioni verranno caricati e renderizzati dinamicamente da `qce.js`.
        -   Il pulsante "Salva" e qualsiasi altro pulsante di azione.
        -   Inclusioni per i file JavaScript (`qce.js`) e CSS (`qce.css`, `style.css`) necessari.
        -   Eventuali messaggi iniziali o istruzioni per il commerciante.
    -   **Rendering:** Questo template viene renderizzato dal metodo `getContent()` del file del modulo `ajax_qce.php`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   Il modulo **non** crea tabelle di database personalizzate.
    -   Legge e scrive direttamente nelle tabelle principali di PrestaShop relative a prodotti e combinazioni, principalmente:
        -   `ps_product_attribute` (dati principali delle combinazioni)
        -   `ps_product_attribute_shop` (dati delle combinazioni specifici del negozio)
        -   `ps_product_attribute_combination` (collega gli attributi alle combinazioni)
        -   `ps_product` (per le informazioni sul prodotto)
        -   `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang` (per le definizioni degli attributi)
        -   `ps_image`, `ps_image_shop`, `ps_image_lang` (per le immagini delle combinazioni)
    -   Le impostazioni di configurazione (se presenti oltre all'interfaccia principale) verrebbero memorizzate in `ps_configuration`.
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente alcun hook di visualizzazione del front-office o del back-office (`displayHeader`, `actionValidateOrder`, ecc.) in senso tradizionale. La sua funzionalità è accessibile direttamente tramite la sua pagina di configurazione nel Back Office. Il metodo `install()` del modulo lo registrerebbe come modulo amministrativo, rendendolo accessibile tramite il Gestore moduli.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Editor di combinazioni di prodotti in massa", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo.
