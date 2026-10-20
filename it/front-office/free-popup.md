---
title: "Free PopUp - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Free PopUp di MyPresta.eu."
sidebar:
  label: "Free PopUp - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Free PopUp su MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-popup.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/free-popup/)
>
> ---


# Free PopUp

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo Free PopUp. Qui troverai tutte le impostazioni per controllare il contenuto e il comportamento del tuo popup.

#### **1. Abilita / Disabilita Popup**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per il tuo popup.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il popup apparirà sul tuo front office in base alle altre impostazioni.
    -   *Quando disabilitato (NO):* Il popup non apparirà sul tuo front office, indipendentemente dalle altre impostazioni.
-   **Valore consigliato:** SÌ (quando vuoi che il popup sia attivo), NO (quando vuoi nasconderlo temporaneamente).
-   **Scenario / esempio per il commerciante:** Abilitalo quando hai una nuova promozione in corso. Disabilitalo durante la manutenzione o se vuoi eseguire una campagna diversa temporaneamente.

#### **2. Contenuto del Popup**

-   **Cosa fa questa impostazione:** Qui inserisci il messaggio, l'offerta o le informazioni che vuoi visualizzare all'interno del popup. Utilizza un editor di testo ricco (TinyMCE), che ti permette di formattare il testo, aggiungere immagini, link e altro.
-   **Effetto della modifica di questa impostazione:** Tutto ciò che digiti e formatti qui verrà visualizzato direttamente ai tuoi clienti nella finestra del popup.
-   **Valore consigliato:** Il tuo messaggio promozionale specifico, testo di benvenuto o annuncio importante.
-   **Scenario / esempio per il commerciante:** "Benvenuto nel nostro negozio! Usa il codice BENVENUTO10 per il 10% di sconto sul tuo primo ordine!" o "Spedizione gratuita su tutti gli ordini superiori a 50€ questa settimana!" Puoi anche aggiungere un'immagine di un nuovo prodotto o un logo del marchio.

#### **3. Scadenza Cookie (Giorni)**

-   **Cosa fa questa impostazione:** Determina per quanto tempo il popup rimane nascosto dopo che un cliente lo chiude. Imposta un cookie nel browser del cliente.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato a 0:* Il popup apparirà ad *ogni* caricamento della pagina, anche se il cliente lo ha appena chiuso. Questo generalmente non è raccomandato in quanto può essere fastidioso.
    -   *Quando impostato a un numero positivo (es. 7):* Il popup apparirà alla prima visita. Una volta chiuso, non riapparirà per i successivi 7 giorni per quel cliente specifico su quel browser specifico.
-   **Valore consigliato:** 7 (per promozioni settimanali), 30 (per messaggi di benvenuto mensili) o 1 (se vuoi che riappaia quotidianamente).
-   **Scenario / esempio per il commerciante:** Se hai un messaggio di benvenuto generale, impostarlo a 30 giorni è una buona idea. Se stai eseguendo una vendita settimanale, 7 giorni assicura che i clienti vedano la nuova offerta la prossima settimana.

#### **4. Modalità Test**

-   **Cosa fa questa impostazione:** Ti permette di testare l'aspetto e il contenuto del tuo popup senza attendere la scadenza del cookie.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il popup apparirà ad ogni aggiornamento della pagina, anche se lo hai appena chiuso. Questo sovrascrive l'impostazione "Scadenza Cookie" per scopi di test.
    -   *Quando disabilitato (NO):* Il popup si comporterà normalmente, rispettando l'impostazione "Scadenza Cookie".
-   **Valore consigliato:** SÌ (mentre stai configurando e perfezionando il popup), NO (una volta che sei soddisfatto della configurazione e vuoi che funzioni normalmente per i clienti).
-   **Scenario / esempio per il commerciante:** Hai appena aggiornato il contenuto del tuo popup e vuoi vedere immediatamente come appare sul front office. Abilita la Modalità Test, aggiorna la pagina del tuo negozio e il popup apparirà. Una volta soddisfatto, disabilita la Modalità Test.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di Configurazione del Modulo | Abilita / Disabilita Popup | SÌ | Interruttore principale per mostrare o nascondere il popup nel tuo negozio. |
| Pagina di Configurazione del Modulo | Contenuto del Popup | Il tuo messaggio | Il testo, le immagini e i link effettivi visualizzati all'interno del popup. |
| Pagina di Configurazione del Modulo | Scadenza Cookie (Giorni) | 7 | Quanti giorni il popup rimane nascosto dopo che un cliente lo chiude. |
| Pagina di Configurazione del Modulo | Modalità Test | NO | Forza la visualizzazione del popup ad ogni aggiornamento per scopi di test. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Il mio popup non appare sul front office, anche dopo averlo abilitato.**

-   **R:** Per prima cosa, controlla se "Abilita / Disabilita Popup" è impostato su SÌ. Se lo è, prova ad abilitare la "Modalità Test" per vedere se appare. Se ancora non si mostra, svuota la cache del tuo browser e la cache Smarty di PrestaShop (Vai su **Parametri Avanzati > Prestazioni**, quindi clicca su "Svuota la cache" in alto a destra). Inoltre, assicurati di aver salvato la configurazione dopo aver apportato modifiche.

**D2: Il popup è apparso una volta, ma ora non si mostra più.**

-   **R:** Questo è un comportamento normale dovuto all'impostazione "Scadenza Cookie". Il modulo imposta un cookie nel tuo browser per impedire al popup di riapparire per il numero di giorni specificato. Per forzarne la visualizzazione per i test, abilita la "Modalità Test" nella configurazione del modulo. Per vederlo come un nuovo visitatore, cancella i cookie del tuo browser per il dominio del tuo negozio o usa una finestra di navigazione in incognito/privata.

**D3: Come posso far apparire il popup in modo diverso (cambiare colori, font, ecc.)?**

-   **R:** Il modulo fornisce un modale bianco di base con un overlay al 70%. Per uno stile avanzato, avresti bisogno di CSS personalizzato. Questo è tipicamente gestito da uno sviluppatore web. Puoi aggiungere CSS personalizzato al file `custom.css` del tuo tema o modificare direttamente il file `front.css` del modulo (anche se quest'ultimo non è raccomandato in quanto gli aggiornamenti lo sovrascriverebbero).

**D4: Posso avere popup diversi per pagine diverse o gruppi di clienti?**

-   **R:** Il modulo Free PopUp è progettato per una singola campagna a livello di negozio. Visualizza lo stesso contenuto a tutti i visitatori. Per popup più avanzati e mirati, avresti bisogno di un modulo popup più ricco di funzionalità (e probabilmente a pagamento).

**D5: Le mie immagini o i miei link nel contenuto del popup non funzionano correttamente.**

-   **R:** Assicurati di utilizzare URL completi e assoluti per immagini e link (es. `https://iltuonegozio.com/img/tuaimmagine.jpg` invece di `/img/tuaimmagine.jpg`). L'editor TinyMCE dovrebbe gestire questo automaticamente, ma a volte sorgono problemi se copi-incolli contenuti da fonti esterne. Controlla il codice HTML sorgente se ti senti a tuo agio.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo Free PopUp è un modulo PrestaShop semplice che segue un modello MVC di base. Utilizza principalmente la classe `Module` per la sua funzionalità principale, la gestione della configurazione e la registrazione degli hook. La visualizzazione del front-office è gestita da un singolo template renderizzato tramite un hook, e il suo comportamento è controllato da un semplice file JavaScript. Lo stile è gestito da file CSS dedicati sia per l'amministrazione che per il front-office.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office personalizzati. Tutta la configurazione è gestita all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi Core e Modelli (`classes/`)

Questo modulo non definisce classi personalizzate o istanze di `ObjectModel`. Tutti i dati di configurazione sono memorizzati direttamente nella tabella `ps_configuration` di PrestaShop utilizzando i metodi standard `Configuration::get()` e `Configuration::updateValue()`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`myfreepopup/js/front.js`**
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo script è responsabile del comportamento lato client del popup.
    -   **Dettagli:**
        -   Controlla la presenza di un cookie specifico (`myfreepopup_closed`).
        -   Se il cookie non viene trovato (il che significa che l'utente non ha chiuso il popup di recente o è la sua prima visita), visualizza il popup manipolando le proprietà CSS (es. `display: block`).
        -   Allega un listener di eventi al pulsante di chiusura all'interno del popup.
        -   Quando il pulsante di chiusura viene cliccato, nasconde il popup e imposta il cookie `myfreepopup_closed` con una scadenza basata sulla configurazione del modulo.
        -   Gestisce anche la logica della "Modalità Test", assicurando che il controllo del cookie venga ignorato quando la modalità test è attiva.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   **`myfreepopup/css/admin.css`**
    -   **Ambito:** Stile del modulo di amministrazione del back-office.
    -   **Dettagli:** Contiene regole di stile di base per la pagina di configurazione del modulo nel back office di PrestaShop, garantendo un aspetto coerente all'interno del pannello di amministrazione.
-   **`myfreepopup/css/front.css`**
    -   **Ambito:** Stile del cliente del front-office.
    -   **Dettagli:** Definisce l'aspetto visivo del popup stesso. Questo include:
        -   Stile per l'overlay modale (es. `position: fixed`, `background-color`, `opacity`, `z-index`).
        -   Stile per la scatola del contenuto principale del popup (es. `background-color: #fff`, `border`, `box-shadow`, `max-width`, `padding`, `text-align`, `position: fixed`, `top`, `left`, `transform` per il centraggio).
        -   Stile per il pulsante di chiusura (es. `position: absolute`, `font-size`, `cursor: pointer`).
        -   Regolazioni responsive per diverse dimensioni dello schermo utilizzando le media query.
    -   **Selettori di classe CSS chiave per l'override:** `.myfreepopup_overlay`, `.myfreepopup_content`, `.myfreepopup_close`.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **`myfreepopup/views/admin_banner.tpl`**
    -   **Ambito:** Template di amministrazione.
    -   **Scopo:** Visualizza un banner promozionale o un messaggio informativo all'interno della pagina di configurazione del modulo nel back office.
-   **`myfreepopup/views/admin_locks.tpl`**
    -   **Ambito:** Template di amministrazione.
    -   **Scopo:** Probabilmente utilizzato per visualizzare informazioni relative alla licenza del modulo o a funzionalità aggiuntive, spesso con un'icona a lucchetto.
-   **`myfreepopup/views/front.tpl`**
    -   **Ambito:** Template di hook del front-office.
    -   **Scopo:** Questo è il template principale responsabile del rendering della struttura HTML del popup sul front office.
    -   **Renderizzato nell'hook:** `displayHeader` (o hook globale simile dove JS/CSS possono essere caricati).
    -   **Contenuto:** Contiene l'HTML per l'overlay, la scatola del contenuto del popup, il pulsante di chiusura e inserisce dinamicamente la variabile `{$popup_content}` (che proviene dall'editor TinyMCE nel back office). Include anche i file JavaScript e CSS necessari.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration` utilizzando chiavi come `MYFREEPOPUP_ENABLED`, `MYFREEPOPUP_CONTENT`, `MYFREEPOPUP_COOKIE_DAYS`, `MYFREEPOPUP_TEST_MODE`.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere i file CSS e JavaScript del modulo e per renderizzare la struttura HTML iniziale del popup (`front.tpl`) che viene poi controllata da JavaScript. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante il modulo Free PopUp.
