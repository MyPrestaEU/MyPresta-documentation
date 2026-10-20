---
title: "Aggiungere immagini ai commenti (recensioni) dei prodotti - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Aggiungere immagini ai commenti (recensioni) dei prodotti' di MyPresta.eu."
sidebar:
  label: "Aggiungere immagini ai commenti (recensioni) dei prodotti - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Add pictures to product comments (reviews) su MyPresta.eu](https://mypresta.eu/modules/front-office-features/add-pictures-to-product-comments-reviews.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/add-pictures-to-product-comments-reviews/)
>
> ---


# Aggiungere immagini ai commenti (recensioni) dei prodotti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).
- **Dipendenza**: Questo modulo richiede che il modulo "Commenti sui prodotti" (sviluppato da MyPresta.eu) sia installato e attivo, in quanto ne estende la funzionalità.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Aggiungere immagini ai commenti (recensioni) dei prodotti" in Gestione moduli. Questo ti porterà alla sua schermata di configurazione principale.

La configurazione del modulo è semplice, concentrandosi principalmente sull'abilitazione o la disabilitazione della sua funzionalità principale.

**Impostazioni e Opzioni:**

- **Abilita caricamento immagini per i commenti sui prodotti:**
  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo. Quando abilitato, i tuoi clienti vedranno l'opzione per caricare immagini quando scrivono una recensione del prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Il campo di caricamento immagini apparirà nel modulo di invio della recensione del prodotto sulle pagine dei tuoi prodotti. I clienti potranno quindi allegare immagini alle loro recensioni. Le recensioni esistenti con immagini visualizzeranno anche tali immagini.
    - *Quando disabilitato (NO):* Il campo di caricamento immagini sarà nascosto dal modulo di invio della recensione del prodotto. I clienti potranno inviare solo recensioni testuali. Le recensioni esistenti con immagini potrebbero comunque visualizzarle, ma non potranno essere aggiunte nuove immagini.
  - **Valore consigliato:** **SÌ**. Per sfruttare i vantaggi delle recensioni visive, dovresti abilitare questa funzione.
  - **Scenario / esempio del commerciante:** Se vuoi consentire ai clienti di mostrare il loro nuovo vestito o come funziona un gadget nella vita reale, abilita questa opzione. Se temporaneamente vuoi limitare il caricamento di immagini per manutenzione o una campagna specifica, puoi disabilitarla.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Abilita caricamento immagini per i commenti sui prodotti | SÌ | Controlla se i clienti possono caricare immagini con le loro recensioni sui prodotti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato il modulo, ma non vedo il campo di caricamento immagini sulla pagina del mio prodotto.**
R:

1.  **Controlla il modulo "Commenti sui prodotti":** Questo modulo estende il modulo "Commenti sui prodotti". Assicurati che il modulo "Commenti sui prodotti" (di MyPresta.eu) sia installato, abilitato e configurato correttamente nel tuo negozio.
2.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo back office di PrestaShop e clicca su "Svuota la cache" in alto a destra. A volte, i vecchi file della cache impediscono la visualizzazione delle nuove funzionalità del modulo.
3.  **Compatibilità del tema:** Sebbene il modulo sia progettato per un'ampia compatibilità, i temi personalizzati potrebbero a volte sovrascrivere le strutture dei template predefinite. Se svuotare la cache non aiuta, contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D: I miei clienti stanno caricando immagini, ma non appaiono accanto alla recensione.**
R:

1.  **Moderazione delle recensioni:** Controlla se il tuo modulo "Commenti sui prodotti" ha la moderazione delle recensioni abilitata. In tal caso, le nuove recensioni (e le immagini associate) appariranno solo dopo che le avrai approvate nel Back Office.
2.  **Controlla la configurazione del modulo:** Ricontrolla che "Abilita caricamento immagini per i commenti sui prodotti" sia impostato su SÌ nella configurazione di questo modulo.
3.  **Permessi dei file:** Assicurati che la directory `img/p/` (o dove PrestaShop memorizza le immagini dei prodotti) abbia i permessi di scrittura corretti (solitamente 755 o 775). Se il server non può scrivere i file, le immagini non verranno salvate.

**D: Posso limitare il numero di immagini che un cliente può caricare per recensione?**
R: Questo modulo specifico fornisce una funzionalità di caricamento di base. Controlli avanzati come la limitazione del numero di immagini o delle dimensioni dei file potrebbero richiedere modifiche personalizzate o un aggiornamento al modulo "Commenti sui prodotti" principale. Si prega di controllare le impostazioni del modulo "Commenti sui prodotti" o di contattare il supporto MyPresta.eu per tali funzionalità.

**D: Le immagini caricate appaiono distorte o non vengono visualizzate correttamente.**
R:

1.  **Conflitti CSS:** Il CSS del tuo tema potrebbe essere in conflitto con lo stile del modulo. Usa gli strumenti per sviluppatori del tuo browser (F12) per ispezionare gli elementi dell'immagine e identificare eventuali stili in conflitto.
2.  **Rigenerazione delle immagini:** A volte, le miniature delle immagini potrebbero non essere generate correttamente. In PrestaShop, vai su **Design > Impostazioni immagini** e prova a rigenerare le miniature per "prodotti" o "recensioni" se tale opzione esiste, o per tutte le immagini.
3.  **Qualità dell'immagine originale:** Consiglia ai clienti di caricare immagini di dimensioni ragionevoli e chiare. Le immagini a risoluzione estremamente bassa appariranno naturalmente scadenti se visualizzate più grandi.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Aggiungere immagini ai commenti (recensioni) dei prodotti" (`reviewspics`) è progettato come un'estensione del modulo principale "Commenti sui prodotti" (presumibilmente `productcomments` o un modulo MyPresta.eu simile). Inietta principalmente un'interfaccia di caricamento immagini nel modulo di recensione esistente e modifica la visualizzazione delle recensioni per includere le immagini. Sfrutta il sistema di hook di PrestaShop per l'integrazione e utilizza risorse standard di front-office e back-office. Il modulo crea una tabella di database personalizzata per collegare le immagini a commenti specifici sui prodotti.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller Front-Office o Back-Office personalizzato. La sua funzionalità è integrata tramite hook e modifiche dirette ai template nel contesto del modulo "Commenti sui prodotti" genitore.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate nella directory `classes/`. La sua logica principale risiede nel file principale del modulo `index.php` e nel file `install.sql` per lo schema del database.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`reviewspics/views/js/reviewspics-bo.js`**

    -   **Ambito:** Back-office.
    -   **Scopo:** Questo script probabilmente gestisce qualsiasi funzionalità basata su JavaScript all'interno della configurazione del back-office del modulo o per la gestione delle immagini caricate associate alle recensioni nel pannello di amministrazione. Ciò potrebbe includere chiamate AJAX per l'eliminazione delle immagini, aggiornamenti di stato o elementi di modulo dinamici.
    -   **Dettagli:** Tipicamente si legherebbe a elementi all'interno del template `backOffice.tpl` o all'interfaccia di gestione dei commenti dei prodotti dell'amministratore.
-   **`reviewspics/views/js/reviewspics.js`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo è il JavaScript principale del front-office per la funzionalità di caricamento delle immagini. Gestisce:
        -   La visualizzazione dell'input di caricamento immagini (ad esempio, input file, area drag-and-drop).
        -   L'anteprima delle immagini selezionate prima del caricamento.
        -   Il caricamento delle immagini basato su AJAX durante l'invio della recensione.
        -   La convalida dei tipi/dimensioni delle immagini (lato client).
        -   Potenzialmente, la rimozione delle immagini selezionate prima dell'invio.
    -   **Dettagli:** Si lega agli elementi del modulo di invio della recensione, probabilmente all'interno del template `displayMyPrestaCommentsField.tpl`, e interagisce con la logica lato server per elaborare i file immagine.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`reviewspics/views/css/reviewspics.css`**
    -   **Ambito:** Front-office (principalmente) e potenzialmente Back-office.
    -   **Scopo:** Questo foglio di stile fornisce lo stile visivo per il modulo di caricamento delle immagini e la visualizzazione delle immagini caricate all'interno delle recensioni dei prodotti.
    -   **Componenti UI principali e contenitori che stilizza:**
        -   L'area di caricamento delle immagini (ad esempio, bordo, sfondo, icona).
        -   Anteprime delle immagini (dimensionamento, proporzioni, bordi).
        -   Layout delle immagini all'interno di una recensione.
        -   Potenzialmente, lo stile per la gestione delle immagini nel Back Office.
    -   **Selettori di classi CSS chiave che gli sviluppatori possono sovrascrivere:** Cerca classi come `.reviewspics-upload-area`, `.reviewspics-image-preview`, `.reviewspics-review-images`, ecc. Queste possono essere mirate nel `custom.css` o `theme.css` di un tema personalizzato per corrispondere al branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:

    -   **`reviewspics/views/templates/hook/backOffice.tpl`**

        -   **Hook:** Probabilmente renderizzato in `displayAdminProductsExtra` o un hook personalizzato all'interno dell'interfaccia di amministrazione del modulo "Commenti sui prodotti".
        -   **Output:** Questo template è per il Back Office. Probabilmente renderizza il modulo di configurazione del modulo (come descritto nella sezione 4.1) o fornisce un'interfaccia per gli amministratori per gestire le immagini associate ai commenti dei prodotti (ad esempio, visualizzare, eliminare, approvare le immagini).
    -   **`reviewspics/views/templates/hook/displayMyPrestaComment.tpl`**

        -   **Hook:** Questo template è progettato per essere agganciato alla visualizzazione di un *singolo* commento del prodotto, probabilmente all'interno di `displayProductListReviews` o un hook simile fornito dal modulo "Commenti sui prodotti".
        -   **Output:** Renderizza le immagini effettive associate a una specifica recensione del prodotto. Itererebbe attraverso le immagini collegate al commento e le visualizzerebbe, potenzialmente come miniature o una piccola galleria.
    -   **`reviewspics/views/templates/hook/displayMyPrestaCommentsField.tpl`**

        -   **Hook:** Questo template è destinato a essere iniettato nel *modulo di invio* della recensione del prodotto, probabilmente tramite un hook come `displayProductForm` o un hook personalizzato all'interno del modulo di recensione del modulo "Commenti sui prodotti".
        -   **Output:** Renderizza la struttura HTML per il campo di input di caricamento immagini con cui i clienti interagiscono quando scrivono una nuova recensione. Questo include l'input del file, eventuali aree drag-and-drop e potenzialmente segnaposto per le anteprime delle immagini.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il file `reviewspics/install.sql` indica la creazione di almeno una tabella personalizzata per archiviare i dati delle immagini e collegarli ai commenti dei prodotti.
    -   **`ps_reviewspics_image`**: (Probabile nome della tabella, basato sul nome del modulo e sulle convenzioni comuni di PrestaShop).
        -   **Scopo:** Archivia i metadati di ogni immagine caricata.
        -   **Campi (previsti):**
            -   `id_reviewspics_image` (Chiave primaria, INT)
            -   `id_product_comment` (Chiave esterna, INT, che si collega alla tabella delle recensioni del modulo "Commenti sui prodotti" genitore)
            -   `image_name` (VARCHAR, nome del file dell'immagine)
            -   `date_add` (DATETIME, timestamp del caricamento)
            -   `active` (TINYINT, per moderazione/visibilità)
            -   `position` (INT, per l'ordinamento se più immagini per recensione)
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Per includere i file CSS (`reviewspics.css`) e JavaScript (`reviewspics.js`) del front-office. |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` di tutte le pagine del back-office. | Per includere CSS e JavaScript (`reviewspics-bo.js`) del back-office per la configurazione dell'amministratore o la gestione delle recensioni. |
| `displayProductListReviews` (o simile dal modulo Commenti sui prodotti) | Renderizza all'interno dell'elenco delle recensioni dei prodotti sulle pagine dei prodotti. | Per iniettare `displayMyPrestaComment.tpl` per la visualizzazione delle immagini all'interno delle recensioni esistenti. |
| `displayProductForm` (o simile dal modulo Commenti sui prodotti) | Renderizza all'interno del modulo di invio della recensione del prodotto. | Per iniettare `displayMyPrestaCommentsField.tpl` per l'input di caricamento immagini. |
| `actionProductCommentAdd` (o simile dal modulo Commenti sui prodotti) | Eseguito dopo l'aggiunta di un nuovo commento del prodotto. | Per elaborare le immagini caricate, salvarle nel file system e registrare i loro dettagli nella tabella `ps_reviewspics_image`, collegandole al nuovo commento. |
| `actionProductCommentDelete` (o simile dal modulo Commenti sui prodotti) | Eseguito dopo l'eliminazione di un commento del prodotto. | Per pulire le immagini associate dal file system e dalla tabella `ps_reviewspics_image`. |
| `actionProductCommentUpdate` (o simile dal modulo Commenti sui prodotti) | Eseguito dopo l'aggiornamento di un commento del prodotto. | Per gestire eventuali modifiche alle associazioni di immagini o allo stato di moderazione. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto professionale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team è dedicato a garantire il buon funzionamento e il continuo miglioramento dei tuoi moduli PrestaShop.
