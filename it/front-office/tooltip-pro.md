---
title: "Tooltip Pro - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Tooltip Pro di MyPresta.eu."
sidebar:
  label: "Tooltip Pro - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Tooltip Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/tooltip-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/tooltip-pro/)
>
> ---


# Tooltip Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Tooltip Pro)

Questa è la schermata di configurazione principale per il modulo Tooltip Pro, dove controlli il suo comportamento generale e l'aspetto.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Tooltip Pro" > Clicca "Configura"

#### Impostazioni e Opzioni:

1.  **Abilita Tooltip:**

    *   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità dei tooltip nel tuo front office.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (SÌ):* I tooltip saranno attivi nel tuo negozio in base alle altre impostazioni.
        *   *Quando disabilitato (NO):* Nessun tooltip apparirà nel tuo negozio, indipendentemente dalle singole voci di tooltip che hai creato.
    *   **Valore consigliato:** SÌ (una volta che hai configurato i tuoi tooltip).
    *   **Scenario / esempio del commerciante:** Se stai eseguendo una manutenzione o vuoi disabilitare temporaneamente tutti i tooltip senza eliminarli, imposta questo su NO.
2.  **Evidenzia Parole Chiave Tooltip:**

    *   **Cosa fa questa impostazione:** Determina se il testo che attiva un tooltip deve essere evidenziato visivamente sul tuo sito web.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (SÌ):* Le parole chiave che hai definito per i tooltip avranno uno stile visivo applicato (ad esempio, una sottolineatura punteggiata, il grassetto o un colore specifico, a seconda del CSS del tuo tema o dello stile predefinito del modulo). Questo aiuta i clienti a identificare gli elementi interattivi.
        *   *Quando disabilitato (NO):* Le parole chiave appariranno come testo normale, ma passando il mouse su di esse si attiverà comunque il tooltip. Questo può rendere i tooltip meno scopribili.
    *   **Valore consigliato:** SÌ.
    *   **Scenario / esempio del commerciante:** Abilitando questa opzione, i tuoi clienti capiranno chiaramente quali parole sono interattive, incoraggiandoli a scoprire le informazioni utili. Se preferisci un design molto minimalista e ti aspetti che gli utenti scoprano i tooltip naturalmente, potresti disabilitarla.
3.  **Posizionamento Tooltip:**

    *   **Cosa fa questa impostazione:** Controlla dove appare il popup del tooltip rispetto al testo della parola chiave.
    *   **Effetto della modifica di questa impostazione:**
        *   *Opzioni (ad esempio, Sopra, Sotto, Sinistra, Destra, Auto):* Scegliendo "Sopra" il tooltip apparirà sopra il testo, "Sotto" sotto, ecc. "Auto" tenta di posizionare intelligentemente il tooltip per evitare che vada fuori schermo.
    *   **Valore consigliato:** Auto.
    *   **Scenario / esempio del commerciante:** "Auto" è generalmente la scelta migliore in quanto si adatta a diverse dimensioni dello schermo e layout di contenuto. Se trovi che i tooltip oscurano costantemente contenuti importanti in un'area specifica, potresti sperimentare un posizionamento fisso come "Sotto".
4.  **Animazione Tooltip:**

    *   **Cosa fa questa impostazione:** Seleziona l'effetto di animazione quando un tooltip appare e scompare.
    *   **Effetto della modifica di questa impostazione:**
        *   *Opzioni (ad esempio, Dissolvenza, Crescita, Oscillazione, Scorrimento, Caduta):* Ogni opzione fornisce una transizione visiva diversa. "Dissolvenza" è una semplice dissolvenza, "Crescita" si espande, ecc.
    *   **Valore consigliato:** Dissolvenza o Crescita.
    *   **Scenario / esempio del commerciante:** Un'animazione sottile come "Dissolvenza" o "Crescita" aggiunge un tocco di eleganza senza essere distraente. Evita animazioni eccessivamente complesse che potrebbero rallentare l'esperienza utente o sembrare fuori luogo con il tuo marchio.
5.  **Tema Tooltip:**

    *   **Cosa fa questa impostazione:** Ti permette di scegliere un tema visivo predefinito per i tuoi tooltip. Questo influenza colori, bordi e stile generale.
    *   **Effetto della modifica di questa impostazione:**
        *   *Opzioni (ad esempio, Predefinito, Chiaro, Scuro, Bordato, Punk):* Ogni tema applica un diverso set di stili CSS.
    *   **Valore consigliato:** Predefinito o Chiaro.
    *   **Scenario / esempio del commerciante:** Scegli un tema che si abbini meglio al design generale e al branding del tuo negozio. "Chiaro" o "Predefinito" sono spesso buoni punti di partenza. Se hai un sito web con un tema scuro, "Scuro" potrebbe essere più appropriato.
6.  **Larghezza Massima Tooltip (pixel):**

    *   **Cosa fa questa impostazione:** Imposta la larghezza massima per la casella popup del tooltip in pixel.
    *   **Effetto della modifica di questa impostazione:**
        *   *Inserendo un valore (ad esempio, 300):* Il tooltip non supererà questa larghezza, andando a capo del testo se necessario.
        *   *Lasciando vuoto o 0:* Il tooltip si ridimensionerà automaticamente per adattarsi al suo contenuto, il che a volte può portare a tooltip molto larghi.
    *   **Valore consigliato:** 250-350 pixel.
    *   **Scenario / esempio del commerciante:** Impostare una larghezza massima ragionevole assicura che i tooltip non diventino troppo larghi e si estendano sullo schermo, specialmente su dispositivi più piccoli o in layout a colonne strette.
7.  **Ritardo Prima di Mostrare (millisecondi):**

    *   **Cosa fa questa impostazione:** Il tempo (in millisecondi) che un utente deve passare il mouse su una parola chiave prima che appaia il tooltip.
    *   **Effetto della modifica di questa impostazione:**
        *   *Valore più alto (ad esempio, 500ms):* I tooltip appaiono dopo un ritardo maggiore, impedendo che compaiano troppo rapidamente se un utente sta solo muovendo il mouse sulla pagina.
        *   *Valore più basso (ad esempio, 0ms):* I tooltip appaiono istantaneamente.
    *   **Valore consigliato:** 200-300.
    *   **Scenario / esempio del commerciante:** Un leggero ritardo (ad esempio, 200ms) offre un'esperienza utente più fluida, poiché impedisce che i tooltip accidentali appaiano e scompaiano rapidamente.
8.  **Ritardo Prima di Nascondere (millisecondi):**

    *   **Cosa fa questa impostazione:** Il tempo (in millisecondi) in cui il tooltip rimane visibile dopo che l'utente ha allontanato il mouse dalla parola chiave.
    *   **Effetto della modifica di questa impostazione:**
        *   *Valore più alto (ad esempio, 200ms):* Il tooltip rimane visibile per un breve periodo, consentendo agli utenti di muovere leggermente il mouse senza che il tooltip scompaia immediatamente.
        *   *Valore più basso (ad esempio, 0ms):* Il tooltip scompare istantaneamente quando il mouse lascia la parola chiave.
    *   **Valore consigliato:** 100-200.
    *   **Scenario / esempio del commerciante:** Un piccolo ritardo qui può essere utile se un utente sposta accidentalmente il mouse dalla parola chiave ma vuole continuare a leggere il tooltip.
9.  **Tipi di Pagina Consentiti per i Tooltip:**

    *   **Cosa fa questa impostazione:** Specifica su quali tipi di pagine i tooltip dovrebbero essere attivi.
    *   **Effetto della modifica di questa impostazione:**
        *   *Caselle di controllo (ad esempio, Pagine Prodotto, Pagine Categoria, Pagine CMS, Tutte le Pagine):* Seleziona i tipi di pagina specifici in cui desideri che i tuoi tooltip funzionino.
        *   *Selezionando "Tutte le Pagine":* I tooltip saranno attivi ovunque nel tuo negozio.
    *   **Valore consigliato:** Seleziona solo i tipi di pagina in cui hai realmente bisogno dei tooltip per evitare elaborazioni non necessarie su altre pagine.
    *   **Scenario / esempio del commerciante:** Se utilizzi principalmente i tooltip per le specifiche dei prodotti, potresti selezionare solo "Pagine Prodotto". Se hai molti termini tecnici in tutto il tuo sito, "Tutte le Pagine" potrebbe essere appropriato.

### 2.2 Schermata di amministrazione dedicata: Elenco Tooltip (Back Office > Tooltip Pro > Tooltip)

Questa schermata è dove gestisci tutti i singoli tooltip che desideri creare e visualizzare nel tuo negozio. Funge da hub centrale per aggiungere, modificare ed eliminare le voci dei tooltip.

-   **Nome schermata e posizione del menu:** Back Office > Tooltip Pro > Tooltip
-   **Azioni e impostazioni disponibili:**
    *   **Tabella Elenco Tooltip:** Visualizza un elenco di tutti i tooltip creati, mostrando tipicamente la parola chiave, il contenuto e il suo stato (abilitato/disabilitato).
    *   **Pulsante Aggiungi Nuovo Tooltip:** Clicca qui per creare una nuova voce di tooltip.
    *   **Azioni Modifica/Elimina:** Ogni tooltip nell'elenco avrà pulsanti di azione (ad esempio, un'icona a matita per "Modifica", un'icona del cestino per "Elimina") per gestire le singole voci.
    *   **Azioni di massa:** Spesso, ci sono opzioni per abilitare, disabilitare o eliminare più tooltip selezionati contemporaneamente.

#### Quando si aggiunge/modifica un Tooltip:

1.  **Parola chiave:**

    *   **Cosa fa questa impostazione:** Questa è la parola o frase esatta che, quando trovata sul tuo sito web, attiverà il tooltip.
    *   **Effetto della modifica di questa impostazione:** Il modulo cercherà questo testo specifico sulle tue pagine abilitate. La distinzione tra maiuscole e minuscole potrebbe applicarsi a seconda della logica interna del modulo (presumi che sia sensibile alle maiuscole per i migliori risultati).
    *   **Valore consigliato:** Sii preciso. Usa l'ortografia e la capitalizzazione esatte come appaiono sul tuo sito.
    *   **Scenario / esempio del commerciante:** Se vuoi spiegare "Cotone Biologico", inserisci "Cotone Biologico". Se inserisci "cotone biologico", potrebbe non attivarsi su "Cotone Biologico".
2.  **Contenuto Tooltip:**

    *   **Cosa fa questa impostazione:** Questa è l'informazione che verrà visualizzata all'interno del popup del tooltip. È tipicamente un editor di testo ricco (WYSIWYG) che consente vari tipi di contenuto.
    *   **Effetto della modifica di questa impostazione:** Tutto ciò che inserisci qui verrà mostrato al cliente quando passa il mouse sulla parola chiave.
    *   **Valore consigliato:** Mantienilo conciso e informativo. Usa immagini, video o link con parsimonia per evitare di sopraffare l'utente.
    *   **Scenario / esempio del commerciante:** Per "Cotone Biologico", potresti aggiungere: "Il cotone biologico è coltivato senza sostanze chimiche nocive, pesticidi o OGM, rendendolo migliore per l'ambiente e la tua pelle. [Link al post del blog sulla sostenibilità]".
3.  **Attivo:**

    *   **Cosa fa questa impostazione:** Controlla se questa specifica voce di tooltip è attiva o inattiva.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (SÌ):* Questo singolo tooltip apparirà nel tuo negozio.
        *   *Quando disabilitato (NO):* Questo tooltip non apparirà, anche se il modulo principale è abilitato.
    *   **Valore consigliato:** SÌ (per i tooltip che desideri visualizzare).
    *   **Scenario / esempio del commerciante:** Potresti disabilitare temporaneamente un tooltip se le informazioni sono obsolete o se una funzionalità del prodotto che descrive non è più disponibile, senza eliminare l'intera voce.

-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Inizia identificando domande comuni o termini confusi nelle tue pagine prodotto, pagine categoria o pagine CMS importanti.
    2.  Vai su **Back Office > Tooltip Pro > Tooltip**.
    3.  Clicca su "Aggiungi Nuovo Tooltip".
    4.  Inserisci la **Parola chiave** esatta che desideri spiegare.
    5.  Crea un **Contenuto Tooltip** chiaro, conciso e utile.
    6.  Assicurati che **Attivo** sia impostato su SÌ.
    7.  Salva le modifiche.
    8.  Testa il tooltip nel tuo front office per assicurarti che appaia correttamente e fornisca le informazioni desiderate.
    9.  Rivedi regolarmente i tuoi tooltip per assicurarti che le informazioni rimangano accurate e pertinenti.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Abilita Tooltip | SÌ | Interruttore principale per tutte le funzionalità dei tooltip. |
| | Evidenzia Parole Chiave Tooltip | SÌ | Contrassegna visivamente le parole chiave nel front-office. |
| | Posizionamento Tooltip | Auto | Posizione del popup del tooltip rispetto alla parola chiave. |
| | Animazione Tooltip | Dissolvenza / Crescita | Effetto visivo quando il tooltip appare/scompare. |
| | Tema Tooltip | Predefinito / Chiaro | Stile (colori, bordi) della casella del tooltip. |
| | Larghezza Massima Tooltip (pixel) | 250-350 | Impedisce che i tooltip diventino troppo larghi. |
| | Ritardo Prima di Mostrare (ms) | 200-300 | Tempo prima che il tooltip appaia al passaggio del mouse. |
| | Ritardo Prima di Nascondere (ms) | 100-200 | Tempo prima che il tooltip scompaia dopo il passaggio del mouse. |
| | Tipi di Pagina Consentiti | Seleziona secondo necessità | Limita i tooltip a tipi di pagina specifici (es. Prodotto, Categoria). |
| **Elenco Tooltip (Aggiungi/Modifica)** | Parola chiave | Testo esatto | La parola/frase specifica che attiva il tooltip. |
| | Contenuto Tooltip | Conciso, informativo | Le informazioni visualizzate all'interno del tooltip. |
| | Attivo | SÌ | Abilita/disabilita una singola voce di tooltip. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei tooltip non vengono visualizzati nel front office, anche se li ho creati.**
R:

1.  **Controlla l'interruttore principale:** Vai su **Moduli > Gestione moduli > Configura Tooltip Pro**. Assicurati che "Abilita Tooltip" sia impostato su SÌ.
2.  **Controlla lo stato del singolo tooltip:** Vai su **Tooltip Pro > Tooltip**. Assicurati che il tooltip specifico che ti aspetti di vedere abbia "Attivo" impostato su SÌ.
3.  **Controlla il tipo di pagina:** Verifica che l'impostazione "Tipi di Pagina Consentiti per i Tooltip" includa il tipo di pagina che stai attualmente visualizzando (ad esempio, se sei su una pagina prodotto, "Pagine Prodotto" deve essere selezionato).
4.  **Corrispondenza parola chiave:** Assicurati che la "Parola chiave" che hai inserito per il tooltip corrisponda esattamente al testo nel tuo front office, inclusa la capitalizzazione e la spaziatura.
5.  **Svuota cache:** A volte la cache di PrestaShop può impedire la visualizzazione di nuovi contenuti. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache".

**D: Il contenuto del tooltip appare strano o non viene visualizzato correttamente (ad esempio, immagini rotte, formattazione strana).**
R:

1.  **Errori HTML:** Se hai utilizzato l'editor di testo ricco, assicurati di non aver introdotto tag HTML rotti. Passa alla visualizzazione del codice sorgente nell'editor per verificare la presenza di tag non chiusi o attributi non validi.
2.  **Percorsi delle immagini:** Se le immagini non vengono visualizzate, controlla che l'URL dell'immagine nel contenuto del tooltip sia corretto e accessibile. Utilizza URL assoluti (che iniziano con `http://` o `https://`) per le immagini ospitate sul tuo server.
3.  **Conflitti CSS:** Il CSS del tuo tema potrebbe sovrascrivere lo stile del modulo. Questo è più un problema per gli sviluppatori, ma puoi provare a cambiare il "Tema Tooltip" nella configurazione del modulo per vedere se un tema diverso risolve il problema.

**D: I tooltip appaiono su pagine dove non li voglio.**
R:

1.  **Rivedi "Tipi di pagina consentiti":** Vai su **Moduli > Gestione moduli > Configura Tooltip Pro**. Rivedi attentamente i "Tipi di pagina consentiti per i tooltip" e deseleziona tutti i tipi di pagina in cui non desideri che appaiano i tooltip.
2.  **Specificità della parola chiave:** Se una parola chiave è molto generica (ad esempio, "prodotto"), potrebbe apparire su molte pagine. Considera di rendere le tue parole chiave più specifiche o di limitarle a determinati tipi di pagina.

**D: Come traduco i miei tooltip in altre lingue?**
R:

1.  **Modifica Tooltip:** Vai su **Tooltip Pro > Tooltip** e clicca su "Modifica" sul tooltip che desideri tradurre.
2.  **Selettore lingua:** All'interno dell'editor di testo ricco "Contenuto Tooltip", dovresti vedere un selettore di lingua (di solito un'icona a bandiera o un menu a discesa). Seleziona la lingua desiderata e inserisci il contenuto tradotto per quella lingua. Ripeti per tutte le lingue.
3.  **Traduzione parola chiave:** La "Parola chiave" stessa di solito non viene tradotta dal modulo, poiché cerca il testo esatto sulla pagina. Se le tue parole chiave cambiano per lingua (ad esempio, "Guida alle taglie" vs. "Guide des Tailles"), dovrai creare voci di tooltip separate per la parola chiave di ogni lingua.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Tooltip Pro segue un'architettura standard dei moduli PrestaShop, sfruttando i principi MVC. Consiste principalmente in:

-   Una classe di modulo principale (`index.php`) per l'installazione, la disinstallazione e la configurazione.
-   Controller Admin dedicati (`AdminTooltipsListController`) per la gestione delle entità tooltip nel Back Office.
-   Controller Front (`ajax.php`) per gestire le richieste di contenuto dinamico, se necessario (anche se il rendering del tooltip principale è lato client).
-   JavaScript lato client (utilizzando la libreria Tooltipster) per rilevare le parole chiave e visualizzare i tooltip dinamicamente.
-   Tabella di database personalizzata (`ps_tooltips`) per memorizzare le definizioni dei tooltip.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/ajax.php`
    *   **Nome classe e classe genitore:** `TooltipsAjaxModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller è progettato per gestire le richieste AJAX dal front-office. Sebbene il contenuto principale del tooltip sia spesso renderizzato direttamente nell'HTML, questo controller potrebbe essere utilizzato per il caricamento dinamico dei contenuti, il recupero dei dati del tooltip su richiesta o altre funzionalità interattive. Risponde a percorsi specifici definiti dal modulo.
-   `controllers/front/index.php`
    *   **Nome classe e classe genitore:** `TooltipsIndexModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller potrebbe fungere da fallback o da segnaposto. In molti moduli semplici, `index.php` nella directory del controller front non viene utilizzato direttamente per il rendering di una pagina, ma potrebbe essere presente per completezza architetturale o per gestire il routing predefinito del modulo se nessun altro controller front specifico corrisponde. Per Tooltip Pro, l'interazione principale del front-office avviene tramite JavaScript e hook.

#### Controller Admin Back-Office

-   `controllers/admin/AdminTooltipsList.php`
    *   **Nome classe e classe genitore:** `AdminTooltipsListController` estende `ModuleAdminController`.
    *   **Nome scheda ed entità gestita:** Questo controller gestisce l'elenco "Tooltip" nel Back Office di PrestaShop. È responsabile della visualizzazione della griglia dei tooltip esistenti, della gestione delle operazioni di aggiunta/modifica/eliminazione per gli oggetti `Tooltip` e del rendering dei moduli associati. Interagisce direttamente con l'`ObjectModel` `Tooltip`.
-   `controllers/admin/index.php`
    *   **Nome classe e classe genitore:** `TooltipsAdminIndexModuleFrontController` estende `ModuleAdminController`.
    *   **Nome scheda ed entità gestita:** Simile a `index.php` del front-office, questo potrebbe essere un segnaposto o un punto di ingresso predefinito per la sezione amministrativa del modulo. La gestione principale è gestita da `AdminTooltipsList.php`.

### 4.3 Classi e Modelli Core (`classes/`)

Il dossier del modulo non indica una directory `classes/` specifica, il che implica che il principale `ObjectModel` `Tooltip` e la logica correlata potrebbero essere definiti direttamente all'interno del file principale `tooltips/index.php` o generati dinamicamente.
Assumendo una struttura standard del modulo PrestaShop, ci sarebbe tipicamente una classe `Tooltip.php`.

-   **`Tooltip` (ipotetico, probabilmente in `index.php` o in un `classes/Tooltip.php` dedicato se presente):**
    *   **Tabella database:** `ps_tooltips` (o `_PREFIX_tooltips`)
    *   **Estende `ObjectModel`:** Sì.
    *   **Campi `$definition`:**
        *   `id_tooltip`: Chiave primaria (INT)
        *   `keyword`: La stringa di testo da evidenziare (VARCHAR)
        *   `content`: Il contenuto HTML del tooltip (HTML, TEXT)
        *   `active`: Booleano per lo stato attivo/inattivo (TINYINT)
        *   `date_add`: Data di creazione (DATETIME)
        *   `date_upd`: Data dell'ultimo aggiornamento (DATETIME)
        *   `id_shop`: ID del negozio per multi-store (INT)
        *   `id_lang`: ID della lingua per contenuti multilingue (INT)
    *   **Metodi pubblici chiave:** Metodi `ObjectModel` standard (`add()`, `update()`, `delete()`, `getFields()`). I metodi personalizzati potrebbero includere `getTooltipsByShopAndLang()` o `getKeywordsForPageType()`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo sfrutta la libreria `Tooltipster` per la sua funzionalità di tooltip.

-   `tooltips/lib/tooltipster/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Un plugin per la libreria Tooltipster specificamente per la gestione degli elementi SVG. Se i tuoi tooltip devono interagire con o essere posizionati su grafici SVG, questo plugin fornisce la funzionalità necessaria.
-   `tooltips/lib/tooltipster/js/tooltipster.bundle.js`
    *   **Ambito:** Front-office.
    *   **Descrizione:** La versione completa e in bundle della libreria Tooltipster, inclusi il suo core e potenzialmente altri plugin comuni. Questo fornisce la funzionalità principale per la creazione e la gestione dei tooltip.
-   `tooltips/lib/tooltipster/js/tooltipster.core.js`
    *   **Ambito:** Front-office.
    *   **Descrizione:** La funzionalità core della libreria Tooltipster. Questo file contiene la logica essenziale per la creazione, il posizionamento, gli eventi e lo stile dei tooltip.
-   `tooltips/views/js/tooltips.js`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Questo è il JavaScript personalizzato del modulo.
        *   **Listener di eventi:** Probabilmente si lega all'evento `ready` del documento (`$(document).ready()` o simile) per inizializzare i tooltip.
        *   **Manipolazione del DOM:** Scansiona il contenuto della pagina per le parole chiave definite, le avvolge in un elemento HTML specifico (ad esempio, `<span class="tooltip-keyword">`) e quindi inizializza la libreria Tooltipster su questi elementi.
        *   **Inizializzazione di Tooltipster:** Configura Tooltipster con le impostazioni del Back Office del modulo (posizionamento, animazione, tema, ritardi, larghezza massima).
        *   **Chiamate AJAX:** Potenzialmente effettua chiamate AJAX a `controllers/front/ajax.php` per recuperare il contenuto del tooltip dinamicamente, anche se la descrizione del modulo suggerisce che il contenuto è spesso pre-renderizzato.
        *   **Interazione mobile:** Gestisce gli eventi di tocco per i dispositivi mobili per attivare i tooltip.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `tooltips/lib/tooltipster/css/tooltipster.bundle.css`
    *   **Ambito:** Stile del cliente front-office.
    *   **Descrizione:** Il foglio di stile principale per la libreria Tooltipster, contenente stili predefiniti per la casella del tooltip, le frecce e vari temi.
-   `tooltips/lib/tooltipster/css/tooltipster.core.css`
    *   **Ambito:** Stile del cliente front-office.
    *   **Descrizione:** CSS core per la libreria Tooltipster, che definisce le proprietà visive essenziali per i tooltip.
-   `tooltips/views/css/tooltips-admin.css`
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Descrizione:** Contiene stili specifici per le pagine di configurazione del modulo e il controller `AdminTooltipsList` nel Back Office di PrestaShop, garantendo un'interfaccia di amministrazione coerente e facile da usare.
-   `tooltips/views/css/tooltips.css`
    *   **Ambito:** Stile del cliente front-office.
    *   **Descrizione:** Questo è il CSS personalizzato del front-office del modulo.
        *   **Componenti UI principali:** Stila le parole chiave evidenziate (ad esempio, `span.tooltip-keyword`).
        *   **Selettori di classe CSS chiave:** Gli sviluppatori possono sovrascrivere gli stili per `.tooltip-keyword` o classi di tema Tooltipster specifiche (ad esempio, `.tooltipster-base`, `.tooltipster-light`) nel `custom.css` del loro tema o creando un file di override.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   `tooltips/views/tooltips.tpl`
    *   **Ambito:** Template hook front-office.
    *   **Descrizione:** Questo template è probabilmente agganciato a `displayHeader` o `displayFooter` per produrre le variabili JavaScript necessarie e potenzialmente lo script di inizializzazione per il file `tooltips.js`. Potrebbe passare le impostazioni di configurazione dal Back Office (ad esempio, `tooltip_placement`, `tooltip_animation`, `tooltip_theme`) come variabili Smarty al JavaScript. Non renderizza direttamente il contenuto del tooltip stesso, poiché questo è gestito dinamicamente da JavaScript.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    *   `ps_tooltips`: Memorizza le definizioni per ogni tooltip.
        *   `id_tooltip` (PK, INT)
        *   `keyword` (VARCHAR)
        *   `content` (TEXT, HTML consentito)
        *   `active` (TINYINT(1))
        *   `date_add` (DATETIME)
        *   `date_upd` (DATETIME)
        *   `id_shop` (INT)
        *   `id_lang` (INT)
    *   `ps_configuration`: Memorizza le impostazioni a livello di modulo (ad esempio, `TOOLTIPS_PRO_ENABLED`, `TOOLTIPS_PRO_HIGHLIGHT`, `TOOLTIPS_PRO_PLACEMENT`, ecc.).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta file CSS e JavaScript (libreria Tooltipster, `tooltips.js` e stili specifici del modulo) nella pagina. Emette anche variabili di configurazione per JS. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del Back Office. | Inietta CSS specifico per l'amministrazione (`tooltips-admin.css`) e potenzialmente JS per le pagine di configurazione e elenco del modulo. |
| `actionFrontControllerSetMedia` | Dopo che i media sono stati impostati per un controller front. | Consente al modulo di aggiungere condizionalmente il suo CSS/JS in base al contesto della pagina corrente (ad esempio, solo sulle pagine prodotto se configurato). |
| `moduleRoutes` | Durante l'inizializzazione del router. | Registra percorsi front-office personalizzati per `ajax.php` se viene utilizzato il caricamento dinamico dei contenuti. |
| `actionObjectTooltipAddAfter` | Dopo l'aggiunta di un oggetto `Tooltip`. | Può essere utilizzato per la pulizia della cache o la registrazione. |
| `actionObjectTooltipUpdateAfter` | Dopo l'aggiornamento di un oggetto `Tooltip`. | Può essere utilizzato per la pulizia della cache o la registrazione. |
| `actionObjectTooltipDeleteAfter` | Dopo l'eliminazione di un oggetto `Tooltip`. | Può essere utilizzato per la pulizia della cache o la registrazione. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il tuo modulo Tooltip Pro, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il tuo modulo funzioni perfettamente e ti aiuti a migliorare il tuo negozio PrestaShop.
