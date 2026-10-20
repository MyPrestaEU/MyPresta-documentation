---
title: "Popup Slider - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Popup Slider di MyPresta.eu."
sidebar:
  label: "Popup Slider - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Popup Slider su MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/popup-slider/)
>
> ---


# Popup Slider

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo Popup Slider, dove definirai l'aspetto e il comportamento del tuo popup.

#### Impostazioni generali

- **Larghezza popup (px):**

  - **Cosa fa questa impostazione:** Definisce la larghezza della finestra popup in pixel.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un valore specifico (es. 800):* Il popup apparirà esattamente largo 800 pixel sugli schermi desktop.
    - *Quando impostato su un valore diverso:* Il popup si ridimensionerà di conseguenza.
  - **Valore consigliato:** 800px (o regola in base alle dimensioni delle tue immagini e al design).
  - **Scenario/esempio per il commerciante:** Se le tue immagini slider sono larghe 800px, impostando questo valore a 800px si assicura che si adattino perfettamente senza problemi di scalatura.
- **Altezza popup (px):**

  - **Cosa fa questa impostazione:** Definisce l'altezza della finestra popup in pixel.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un valore specifico (es. 500):* Il popup apparirà esattamente alto 500 pixel.
    - *Quando impostato su un valore diverso:* Il popup si ridimensionerà di conseguenza.
  - **Valore consigliato:** 500px (o regola in base alle dimensioni delle tue immagini e al design).
  - **Scenario/esempio per il commerciante:** Se le tue immagini slider sono alte 500px, impostando questo valore a 500px si assicura che si adattino perfettamente.
- **Colore sfondo popup:**

  - **Cosa fa questa impostazione:** Imposta il colore di sfondo della finestra popup stessa (l'area dietro le immagini del tuo slider). Puoi usare un selettore di colori per scegliere.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un colore specifico (es. #FFFFFF per il bianco):* Lo sfondo del popup visualizzerà quel colore.
    - *Quando impostato su un colore diverso:* Il colore di sfondo cambia.
  - **Valore consigliato:** #FFFFFF (bianco) o un colore che si abbini al design del tuo negozio.
  - **Scenario/esempio per il commerciante:** Se il tuo negozio ha un tema scuro, potresti scegliere un grigio chiaro (#F5F5F5) per lo sfondo del popup per far risaltare il contenuto.
- **Colore bordo popup:**

  - **Cosa fa questa impostazione:** Imposta il colore del bordo attorno alla finestra popup.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un colore specifico (es. #CCCCCC per il grigio chiaro):* Il popup avrà un bordo di quel colore.
    - *Quando impostato su un colore diverso:* Il colore del bordo cambia.
  - **Valore consigliato:** #CCCCCC (grigio chiaro) o un colore che si abbini al tuo brand.
  - **Scenario/esempio per il commerciante:** Un bordo sottile può aiutare a definire il popup rispetto a uno sfondo affollato.
- **Larghezza bordo popup (px):**

  - **Cosa fa questa impostazione:** Definisce lo spessore del bordo del popup in pixel.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 1:* Il bordo sarà spesso 1 pixel.
    - *Quando impostato su 0:* Nessun bordo sarà visibile.
  - **Valore consigliato:** 1px o 0px.
  - **Scenario/esempio per il commerciante:** Un bordo di 0px può creare un aspetto più uniforme e moderno se il tuo design non richiede un bordo visibile.
- **Raggio bordo popup (px):**

  - **Cosa fa questa impostazione:** Controlla l'arrotondamento degli angoli del popup. Un valore più alto significa angoli più arrotondati.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 0:* Il popup avrà angoli netti e squadrati.
    - *Quando impostato su 10:* Gli angoli saranno leggermente arrotondati.
  - **Valore consigliato:** 5px o 0px.
  - **Scenario/esempio per il commerciante:** Gli angoli arrotondati possono dare al tuo popup un'estetica più morbida e moderna.
- **Ombra popup:**

  - **Cosa fa questa impostazione:** Aggiunge un effetto ombra attorno al popup, facendolo apparire come se fluttuasse sopra la pagina.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Un'ombra sottile apparirà attorno al popup.
    - *Quando disabilitato (NO):* Il popup non avrà ombra.
  - **Valore consigliato:** SÌ.
  - **Scenario/esempio per il commerciante:** Un'ombra aiuta il popup a distinguersi dal contenuto di sfondo, migliorando la visibilità e la profondità percepita.
- **Colore overlay popup:**

  - **Cosa fa questa impostazione:** Imposta il colore dell'overlay semi-trasparente che copre il resto del contenuto del tuo negozio quando il popup è attivo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un colore specifico (es. #000000 per il nero):* L'overlay sarà di quel colore.
  - **Valore consigliato:** #000000 (nero).
  - **Scenario/esempio per il commerciante:** Un overlay scuro aiuta a focalizzare l'attenzione del visitatore esclusivamente sul contenuto del popup.
- **Opacità overlay popup (0-1):**

  - **Cosa fa questa impostazione:** Controlla la trasparenza dell'overlay. 0 è completamente trasparente, 1 è completamente opaco.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 0.5:* L'overlay sarà trasparente al 50%, permettendo di vedere parte del contenuto del negozio in background.
    - *Quando impostato su 0.8:* L'overlay sarà opaco all'80%, rendendo il contenuto di sfondo molto fioco.
  - **Valore consigliato:** 0.7 o 0.8.
  - **Scenario/esempio per il commerciante:** Un'opacità maggiore assicura che il popup sia l'attenzione principale, mentre un'opacità inferiore potrebbe essere utilizzata se si desidera suggerire sottilmente il contenuto dietro il popup.
- **Tempo di ri-visualizzazione popup (ore):**

  - **Cosa fa questa impostazione:** Determina quante ore devono trascorrere prima che il popup venga mostrato di nuovo allo stesso visitatore dopo che lo ha chiuso.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 0:* Il popup apparirà ogni volta che il visitatore carica una pagina (non consigliato per l'esperienza utente).
    - *Quando impostato su 24:* Il popup riapparirà dopo 24 ore.
    - *Quando impostato su un numero molto alto (es. 8760 per 1 anno):* Il popup si mostrerà effettivamente solo una volta per visitatore.
  - **Valore consigliato:** 24 (per promozioni giornaliere) o 168 (per promozioni settimanali) o un numero molto alto come 8760 (per una volta all'anno o effettivamente una volta per sempre).
  - **Scenario/esempio per il commerciante:** Se gestisci offerte giornaliere, impostando questo valore a 24 ore assicura che i visitatori vedano la nuova offerta ogni giorno. Se vuoi mostrare un messaggio di benvenuto solo una volta, impostalo su un numero molto alto.
- **Mostra pulsante di chiusura:**

  - **Cosa fa questa impostazione:** Attiva/disattiva la visibilità del pulsante di chiusura 'X' sul popup.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Un pulsante di chiusura sarà visibile, consentendo ai visitatori di chiudere facilmente il popup.
    - *Quando disabilitato (NO):* Nessun pulsante di chiusura sarà mostrato. I visitatori dovranno cliccare al di fuori del popup o navigare via per chiuderlo.
  - **Valore consigliato:** SÌ.
  - **Scenario/esempio per il commerciante:** Fornisci sempre un modo chiaro per gli utenti di chiudere il popup per evitare frustrazioni e migliorare l'esperienza utente.
- **Chiudi al clic sull'overlay:**

  - **Cosa fa questa impostazione:** Determina se cliccando sull'overlay semi-trasparente (al di fuori del contenuto del popup) si chiuderà il popup.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Cliccando sull'overlay si chiuderà il popup.
    - *Quando disabilitato (NO):* Solo il pulsante di chiusura (se abilitato) o la navigazione via chiuderanno il popup.
  - **Valore consigliato:** SÌ.
  - **Scenario/esempio per il commerciante:** Questo fornisce un modo intuitivo e comune per gli utenti di chiudere i popup, migliorando l'usabilità.

#### Configurazione immagini slider

Questa sezione ti consente di aggiungere, modificare e gestire le immagini che appariranno nel tuo slider popup. Puoi aggiungere un numero illimitato di immagini.

Per ogni slot immagine, troverai tipicamente:

- **Campo di caricamento immagine:**

  - **Cosa fa questa impostazione:** Ti consente di caricare un file immagine dal tuo computer per essere visualizzato nello slider.
  - **Effetto della modifica di questa impostazione:**
    - *Quando un'immagine viene caricata:* Sostituisce qualsiasi immagine esistente in quello slot o ne aggiunge una nuova allo slider.
  - **Valore consigliato:** Utilizza immagini di alta qualità e ottimizzate che corrispondano al rapporto d'aspetto della larghezza/altezza del tuo popup.
  - **Scenario/esempio per il commerciante:** Carica la tua ultima foto di prodotto, un banner per una vendita o una grafica che promuove una nuova funzionalità.
- **Link immagine (URL):**

  - **Cosa fa questa impostazione:** Specifica l'URL a cui i visitatori verranno reindirizzati quando cliccano su questa specifica immagine dello slider.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene inserito un URL:* Cliccando sull'immagine si porterà il visitatore a quella pagina.
    - *Quando lasciato vuoto:* L'immagine non sarà cliccabile.
  - **Valore consigliato:** Collega sempre a pagine pertinenti (prodotto, categoria, post del blog, pagina di contatto).
  - **Scenario/esempio per il commerciante:** Collega un banner "Nuovi Arrivi" alla pagina della categoria dei tuoi nuovi prodotti, o un banner "Saldi Estivi" alla tua landing page dei saldi.
- **Titolo immagine/Testo Alt:**

  - **Cosa fa questa impostazione:** Fornisce una descrizione testuale per l'immagine. Questo testo è importante per la SEO (motori di ricerca) e l'accessibilità (screen reader per utenti con disabilità visive).
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene inserito del testo:* Questo testo verrà utilizzato dai motori di ricerca per comprendere il contenuto dell'immagine e dagli screen reader per descrivere l'immagine.
  - **Valore consigliato:** Una frase concisa e descrittiva che descriva accuratamente il contenuto dell'immagine e includa parole chiave pertinenti.
  - **Scenario/esempio per il commerciante:** Per un'immagine di un nuovo vestito, usa "Nuovo Vestito Collezione Estiva - Acquista Ora".
- **Pulsante Elimina immagine:**

  - **Cosa fa questa impostazione:** Rimuove l'immagine selezionata dallo slider.
  - **Effetto della modifica di questa impostazione:**
    - *Quando cliccato:* L'immagine e le sue impostazioni associate vengono rimosse dalla configurazione dello slider.
  - **Valore consigliato:** Usalo per rimuovere promozioni o immagini obsolete.
  - **Scenario/esempio per il commerciante:** Dopo la fine di una vendita, elimina l'immagine del banner che promuoveva quella vendita.
- **Pulsante Aggiungi nuova immagine:**

  - **Cosa fa questa impostazione:** Aggiunge un nuovo slot vuoto per caricare un'altra immagine nello slider.
  - **Effetto della modifica di questa impostazione:**
    - *Quando cliccato:* Appare un nuovo set di campi per il caricamento dell'immagine, il link e il titolo.
  - **Valore consigliato:** Usalo per espandere il contenuto del tuo slider.
  - **Scenario/esempio per il commerciante:** Aggiungi una nuova slide per una prossima promozione festiva.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Larghezza popup (px) | 800 | Imposta la larghezza della finestra popup. |
| Configurazione modulo | Altezza popup (px) | 500 | Imposta l'altezza della finestra popup. |
| Configurazione modulo | Colore sfondo popup | #FFFFFF | Colore di sfondo dell'area contenuto del popup. |
| Configurazione modulo | Colore bordo popup | #CCCCCC | Colore del bordo attorno al popup. |
| Configurazione modulo | Larghezza bordo popup (px) | 1 | Spessore del bordo del popup. |
| Configurazione modulo | Raggio bordo popup (px) | 5 | Arrotondamento degli angoli del popup. |
| Configurazione modulo | Ombra popup | SÌ | Aggiunge un effetto ombra per la profondità. |
| Configurazione modulo | Colore overlay popup | #000000 | Colore dell'overlay di sfondo semi-trasparente. |
| Configurazione modulo | Opacità overlay popup (0-1) | 0.7 | Livello di trasparenza dell'overlay. |
| Configurazione modulo | Tempo di ri-visualizzazione popup (ore) | 24 | Quanto tempo prima che il popup venga mostrato di nuovo a un visitatore. |
| Configurazione modulo | Mostra pulsante di chiusura | SÌ | Visualizza un pulsante 'X' per chiudere il popup. |
| Configurazione modulo | Chiudi al clic sull'overlay | SÌ | Consente di chiudere il popup cliccando al di fuori di esso. |
| Configurazione modulo | Campo di caricamento immagine | N/A | Carica un'immagine per una slide. |
| Configurazione modulo | Link immagine (URL) | N/A | URL a cui navigare cliccando sull'immagine della slide. |
| Configurazione modulo | Titolo immagine/Testo Alt | N/A | Testo descrittivo per SEO e accessibilità. |
| Configurazione modulo | Pulsante Elimina immagine | N/A | Rimuove una slide dallo slider. |
| Configurazione modulo | Pulsante Aggiungi nuova immagine | N/A | Aggiunge un nuovo slot slide vuoto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio popup non viene visualizzato affatto. Cosa dovrei controllare?**
R1:

-   **Modulo abilitato:** Innanzitutto, assicurati che il modulo sia abilitato in **Moduli > Gestione moduli**.
-   **Configurazione salvata:** Assicurati di aver salvato le impostazioni di configurazione dopo aver apportato modifiche.
-   **Immagini aggiunte:** Hai caricato almeno un'immagine nella configurazione dello slider? Lo slider non apparirà se non ci sono immagini.
-   **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**) e la cache del tuo browser. A volte i vecchi file memorizzati nella cache impediscono il caricamento di nuovi contenuti del modulo.
-   **Tempo di ri-visualizzazione:** Se hai visitato il tuo sito in precedenza, il "Tempo di ri-visualizzazione popup" potrebbe impedirne la nuova visualizzazione. Prova ad aprire il tuo negozio in una finestra del browser in incognito/privata per simulare un visitatore per la prima volta.

**D2: Il mio popup ha un aspetto strano o non è centrato correttamente sul mio tema personalizzato.**
R2:

-   **Conflitti del tema:** I temi personalizzati a volte hanno stili CSS in conflitto.
-   **Impostazioni Larghezza/Altezza:** Ricontrolla le impostazioni "Larghezza popup" e "Altezza popup" nella configurazione del modulo. Assicurati che siano appropriate per le tue immagini e le dimensioni dello schermo.
-   **Assistenza sviluppatore:** Se il problema persiste, potrebbe essere necessario un piccolo aggiustamento CSS da parte di uno sviluppatore web che abbia familiarità con il tuo tema. Possono ispezionare gli elementi e applicare stili personalizzati per risolvere i conflitti.

**D3: Le immagini nel mio slider sono sfocate o distorte.**
R3:

-   **Qualità dell'immagine:** Assicurati che le immagini che stai caricando siano ad alta risoluzione e non pixelate.
-   **Rapporto d'aspetto:** Le immagini dovrebbero idealmente corrispondere al rapporto d'aspetto (rapporto larghezza/altezza) che hai impostato per la tua "Larghezza popup" e "Altezza popup". Se le tue immagini hanno un rapporto diverso, potrebbero essere allungate o compresse per adattarsi.
-   **Ottimizzazione delle immagini:** Sebbene l'alta risoluzione sia buona, file di dimensioni eccessivamente grandi possono rallentare il tuo sito. Ottimizza le tue immagini per l'uso web (ad esempio, comprimile) prima di caricarle.

**D4: Posso avere popup diversi per pagine diverse o gruppi di clienti?**
R4: Il modulo Popup Slider, nella sua versione attuale, visualizza un singolo popup globale a tutti i visitatori in base alla logica di ri-visualizzazione. Non supporta nativamente popup diversi per pagine specifiche o gruppi di clienti. Per una funzionalità così avanzata, avresti tipicamente bisogno di un modulo più complesso o di uno sviluppo personalizzato.

**D5: Come si traduce il testo del modulo (ad esempio, il testo del pulsante di chiusura, se presente)?**
R5: Sebbene questo modulo utilizzi principalmente immagini, qualsiasi elemento di testo predefinito sarebbe traducibile tramite il sistema di traduzione di PrestaShop:

-   Naviga su **Internazionale > Traduzioni**.
-   Seleziona "Traduzioni dei moduli installati".
-   Scegli il tuo tema, la tua lingua e poi trova "Popup Slider" nell'elenco dei moduli.
-   Potrai quindi modificare qualsiasi stringa traducibile.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi tecnica approfondita dell'architettura del modulo Popup Slider, destinata a sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo Popup Slider (`popupslider/cz.php`) è un classico modulo PrestaShop 1.4-1.6, che sfrutta principalmente la classe `Module` per la sua funzionalità principale. Si integra nel front-office tramite un hook (tipicamente `displayHeader` o `displayFooter` implicitamente, sebbene la documentazione menzioni `Header, Columns, Product, or Footer` come potenziali aree di visualizzazione, il template fornito `header.tpl` suggerisce che `displayHeader` sia il punto di integrazione primario). La configurazione è gestita tramite il metodo `getContent()`, memorizzando le impostazioni in `ps_configuration`. L'interazione con il front-office è gestita iniettando JavaScript e CSS, che poi renderizzano lo slider utilizzando la libreria bxSlider.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate o istanze di `ObjectModel`. Tutti i dati di configurazione sono memorizzati direttamente nella tabella `ps_configuration` utilizzando i metodi standard `Configuration::get()` e `Configuration::updateValue()`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo si basa fortemente su JavaScript per la sua funzionalità front-office, in particolare per il comportamento del popup e dello slider.

-   **`popupslider/jscolor/jscolor.js`**:
    *   **Ambito:** Back-office (utilizzato all'interno della pagina di configurazione del modulo).
    *   **Responsabilità:** Fornisce una funzionalità di selezione colori JavaScript per il modulo di configurazione, consentendo ai commercianti di selezionare facilmente i colori per lo sfondo, il bordo e l'overlay del popup.
    *   **Dettagli:** Questa è una libreria di terze parti integrata per il miglioramento dell'interfaccia utente nel pannello di amministrazione.
-   **`popupslider/js/bxslider.js`**:
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questa è la libreria principale per lo slider di immagini animate all'interno del popup. Gestisce le transizioni, i controlli di navigazione (frecce, punti) e il comportamento reattivo della presentazione.
    *   **Dettagli:** Uno slider di contenuti jQuery ampiamente utilizzato. Il modulo inizializza questo slider sulle immagini all'interno del popup.
-   **`popupslider/js/script.js`**:
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questo script personalizzato orchestra l'aspetto e il comportamento del popup.
        *   **Gestione dei cookie:** Controlla un cookie per determinare se l'utente è un visitatore per la prima volta o se il tempo di ri-visualizzazione è trascorso.
        *   **Visualizzazione popup:** Attiva la visualizzazione dell'overlay del popup e del contenuto dello slider.
        *   **Gestione eventi:** Collega gli eventi per la chiusura del popup (ad esempio, cliccando sul pulsante di chiusura, cliccando sull'overlay).
        *   **Inizializzazione bxSlider:** Inizializza il `bxslider.js` sull'elemento DOM appropriato contenente le immagini dello slider.
    *   **Dettagli:** Questo script è cruciale per la logica di visualizzazione "intelligente" del modulo e l'interazione con l'utente.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non elenca esplicitamente file CSS personalizzati nell'inventario fornito. Tuttavia, è altamente probabile che la libreria `bxslider.js` includa il proprio CSS (ad esempio, `jquery.bxslider.css` o simile) che verrebbe caricato, e il `header.tpl` o `cz.php` del modulo potrebbe iniettare stili inline basati sulle impostazioni di configurazione (colori, dimensioni).

Se fossero presenti file CSS, tipicamente:

-   **Ambito:** Front-office (per lo stile del popup e dello slider).
-   **Componenti principali dell'interfaccia utente:** Stilizzano il contenitore del popup, l'overlay, il pulsante di chiusura, la navigazione dello slider (frecce, punti) e le singole immagini delle slide.
-   **Selettori di classi CSS chiave:** Gli sviluppatori dovrebbero cercare classi come `.popupslider-overlay`, `.popupslider-container`, `.popupslider-close`, `.bx-wrapper`, `.bx-viewport`, `.bx-controls`, ecc., da sovrascrivere nel `custom.css` del loro tema o nel tema figlio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    *   **`popupslider/header.tpl`**:
        *   **Hook:** Probabilmente `displayHeader` (o simile, dato il nome). Questo template è responsabile del rendering della struttura HTML dell'overlay del popup, del contenitore del popup e dello slider di immagini stesso.
        *   **Output:** Genera gli elementi `div` necessari per l'overlay, la casella popup principale, il pulsante di chiusura e l'elenco `ul` che `bxslider.js` trasformerà in una presentazione interattiva. Probabilmente include anche stili inline derivati dalle impostazioni di configurazione del modulo (larghezza, altezza, colori, ecc.) e include le risorse JavaScript e CSS necessarie.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Questo modulo non crea tabelle di database personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella standard di PrestaShop `ps_configuration`.
    *   **Chiavi di configurazione (Esempi):**
        *   `POPUP_SLIDER_WIDTH`
        *   `POPUP_SLIDER_HEIGHT`
        *   `POPUP_SLIDER_BG_COLOR`
        *   `POPUP_SLIDER_BORDER_COLOR`
        *   `POPUP_SLIDER_BORDER_WIDTH`
        *   `POPUP_SLIDER_BORDER_RADIUS`
        *   `POPUP_SLIDER_SHADOW`
        *   `POPUP_SLIDER_OVERLAY_COLOR`
        *   `POPUP_SLIDER_OVERLAY_OPACITY`
        *   `POPUP_SLIDER_REDISPLAY_TIME`
        *   `POPUP_SLIDER_SHOW_CLOSE_BTN`
        *   `POPUP_SLIDER_CLOSE_ON_OVERLAY_CLICK`
        *   `POPUP_SLIDER_IMAGE_X` (dove X è un ID incrementale per ogni immagine, che memorizza URL, link, testo alt).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per iniettare i file CSS e JavaScript del modulo, e potenzialmente la struttura HTML iniziale per il popup (anche se il popup stesso è solitamente nascosto fino a quando non viene attivato da JS). |
| `displayFooter` (Potenziale) | Eseguito alla fine della sezione `<body>` di ogni pagina del front-office. | Potrebbe essere utilizzato come alternativa a `displayHeader` per iniettare l'HTML e il JS del popup, spesso preferito per le prestazioni in quanto non blocca il rendering della pagina. |
| `displayRightColumn` (Potenziale) | Eseguito nella colonna destra del front-office. | Sebbene menzionato nella descrizione del commerciante, è improbabile che un popup a pagina intera venga renderizzato qui. Più probabile per un piccolo banner o un trigger. |
| `displayLeftColumn` (Potenziale) | Eseguito nella colonna sinistra del front-office. | Simile a `displayRightColumn`, improbabile per un popup a pagina intera. |
| `displayProductButtons` (Potenziale) | Eseguito sulla pagina del prodotto, vicino al pulsante "aggiungi al carrello". | Improbabile per un popup globale, ma potrebbe essere utilizzato per un popup specifico del prodotto se il modulo avesse tali funzionalità avanzate. |

Dato il file `header.tpl`, `displayHeader` è l'hook più probabile per iniettare le risorse del modulo e la struttura iniziale del popup.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Popup Slider, fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team è dedicato a fornire assistenza e a garantire che il tuo modulo funzioni in modo ottimale.

-   **Cronologia ordini e download MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
-   **Contatto supporto MyPresta.eu:** <https://mypresta.eu/contact>
"""
