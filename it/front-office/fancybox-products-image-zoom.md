---
title: "Zoom immagine prodotti Fancybox - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Fancybox products image zoom di MyPresta.eu."
sidebar:
  label: "Zoom immagine prodotti Fancybox - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Fancybox products image zoom su MyPresta.eu](https://mypresta.eu/modules/front-office-features/fancybox-products-image-zoom.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/fancybox-products-image-zoom/)
>
> ---


# Zoom immagine prodotti Fancybox

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo Fancybox products image zoom. La troverai navigando su **Moduli > Gestione moduli**, cercando "Fancybox products image zoom" e cliccando su "Configura".

#### Impostazioni di supporto e selettore del tema

Queste impostazioni aiutano il modulo a identificare gli elementi corretti sulla tua pagina prodotto per applicare lo zoom Fancybox, particolarmente importanti per i temi personalizzati.

- **Supporto tema**

  - **Cosa fa questa impostazione:** Questa è un'impostazione cruciale che indica al modulo quale struttura del tema deve aspettarsi. Aiuta il modulo a identificare correttamente l'immagine principale del prodotto e le sue miniature sulle tue pagine prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "Classic":* Il modulo utilizzerà selettori predefiniti che funzionano perfettamente con il tema "Classic" predefinito di PrestaShop. Questa è l'impostazione più comune e consigliata se stai utilizzando il tema Classic o un tema basato molto strettamente su di esso.
    - *Se impostato su "Hummingbird":* Il modulo utilizzerà selettori predefiniti per il tema "Hummingbird", che è il tema predefinito per PrestaShop 8.1 e versioni successive.
    - *Se impostato su "Custom":* Questa opzione ti consente di specificare manualmente i selettori CSS per l'immagine principale del prodotto e le miniature. Questo è essenziale se stai utilizzando un tema fortemente personalizzato o un tema di terze parti che non segue la struttura "Classic" o "Hummingbird".
  - **Valore consigliato:** "Classic" se sei su PrestaShop 1.7.x a 8.0.x con il tema Classic. "Hummingbird" se sei su PrestaShop 8.1+ con il tema Hummingbird. "Custom" se hai un tema unico.
  - **Scenario / esempio del commerciante:** Se le immagini dei tuoi prodotti non si ingrandiscono correttamente dopo l'installazione e stai utilizzando un tema personalizzato, il passaggio a "Custom" e la successiva regolazione dei selettori sottostanti è il passo successivo.
- **Profilo tema rilevato**

  - **Cosa fa questa impostazione:** Questo campo visualizza il profilo del tema che il modulo ha rilevato automaticamente in base alla tua selezione di "Supporto tema". È un campo informativo, non direttamente configurabile.
  - **Effetto della modifica di questa impostazione:** Nessun effetto diretto, poiché è un campo di sola visualizzazione. Semplicemente conferma quale set di selettori il modulo sta attualmente utilizzando.
  - **Valore consigliato:** N/A (informativo).
  - **Scenario / esempio del commerciante:** Hai impostato "Supporto tema" su "Classic", e questo campo conferma che "Classic" è stato rilevato.
- **Selettore copertina Hummingbird** (Visibile solo se "Supporto tema" è "Hummingbird")

  - **Cosa fa questa impostazione:** Specifica il selettore CSS per il contenitore dell'immagine di copertina principale del prodotto quando si utilizza il tema Hummingbird. Questo aiuta il modulo a mirare all'area corretta per lo zoom.
  - **Effetto della modifica di questa impostazione:** Se errato, lo zoom Fancybox potrebbe non attivarsi sull'immagine principale del prodotto, oppure potrebbe mirare all'elemento sbagliato.
  - **Valore consigliato:** Lasciare come predefinito a meno che il tuo tema basato su Hummingbird non abbia alterato significativamente la sua struttura.
  - **Scenario / esempio del commerciante:** Il tuo tema Hummingbird ha una struttura unica per l'immagine principale. Potrebbe essere necessario ispezionare il codice del tuo tema per trovare la classe o l'ID CSS corretto per il contenitore dell'immagine principale e inserirlo qui.
- **Selettore immagine Hummingbird** (Visibile solo se "Supporto tema" è "Hummingbird")

  - **Cosa fa questa impostazione:** Specifica il selettore CSS per il tag `<img>` effettivo dell'immagine di copertina principale del prodotto all'interno del tema Hummingbird.
  - **Effetto della modifica di questa impostazione:** Simile al selettore della copertina, un valore errato impedirà allo zoom di funzionare sull'immagine principale.
  - **Valore consigliato:** Lasciare come predefinito.
  - **Scenario / esempio del commerciante:** Se lo zoom non funziona sull'immagine principale e sei su Hummingbird, controlla questo selettore.
- **Selettore miniature Hummingbird** (Visibile solo se "Supporto tema" è "Hummingbird")

  - **Cosa fa questa impostazione:** Specifica il selettore CSS per il contenitore delle immagini in miniatura del prodotto quando si utilizza il tema Hummingbird. Questo è importante per creare una galleria dalle tue miniature.
  - **Effetto della modifica di questa impostazione:** Se errato, il modulo potrebbe non essere in grado di creare una galleria Fancybox dalle tue miniature, oppure cliccando sulle miniature potrebbe non aprirsi Fancybox.
  - **Valore consigliato:** Lasciare come predefinito.
  - **Scenario / esempio del commerciante:** Se cliccando sulle miniature non si apre la galleria Fancybox, verifica questo selettore.
- **Selettore immagine di copertina principale** (Visibile solo se "Supporto tema" è "Custom")

  - **Cosa fa questa impostazione:** Quando è selezionato il supporto tema "Custom", questo campo ti consente di inserire manualmente il selettore CSS per l'elemento contenitore che contiene l'immagine principale del tuo prodotto sulla pagina prodotto.
  - **Effetto della modifica di questa impostazione:** Se questo selettore è errato, lo zoom Fancybox non si attiverà sull'immagine principale del tuo prodotto.
  - **Valore consigliato:** Dovrai utilizzare gli strumenti per sviluppatori del tuo browser (F12) per ispezionare la tua pagina prodotto e trovare la classe o l'ID CSS univoco del `<div>` o di un altro elemento contenitore che racchiude l'immagine principale del tuo prodotto.
  - **Scenario / esempio del commerciante:** Il tuo tema personalizzato utilizza `<div id="my-custom-main-image-wrapper">` per l'immagine principale. Inseriresti `#my-custom-main-image-wrapper` qui.
- **Immagine di copertina principale** (Visibile solo se "Supporto tema" è "Custom")

  - **Cosa fa questa impostazione:** Quando è selezionato il supporto tema "Custom", questo campo ti consente di inserire manualmente il selettore CSS per il tag `<img>` effettivo dell'immagine principale del tuo prodotto.
  - **Effetto della modifica di questa impostazione:** Se questo selettore è errato, lo zoom Fancybox non si attiverà sull'immagine principale del tuo prodotto.
  - **Valore consigliato:** Utilizza gli strumenti per sviluppatori del tuo browser per trovare la classe o l'ID CSS univoco del tag `<img>` stesso.
  - **Scenario / esempio del commerciante:** Il tuo tema personalizzato utilizza `<img class="product-main-image-src">` per l'immagine principale. Inseriresti `.product-main-image-src` qui.
- **Selettore immagini miniature** (Visibile solo se "Supporto tema" è "Custom")

  - **Cosa fa questa impostazione:** Quando è selezionato il supporto tema "Custom", questo campo ti consente di inserire manualmente il selettore CSS per l'elemento contenitore che contiene le immagini in miniatura del tuo prodotto.
  - **Effetto della modifica di questa impostazione:** Se questo selettore è errato, il modulo non sarà in grado di creare una galleria Fancybox dalle tue miniature, oppure cliccando sulle miniature potrebbe non aprirsi Fancybox.
  - **Valore consigliato:** Utilizza gli strumenti per sviluppatori del tuo browser per trovare la classe o l'ID CSS univoco del `<div>` o di un altro elemento contenitore che racchiude le miniature del tuo prodotto.
  - **Scenario / esempio del commerciante:** Il tuo tema personalizzato utilizza `<ul id="product-thumbnails-list">` per le miniature. Inseriresti `#product-thumbnails-list` qui.

#### Impostazioni di comportamento di Fancybox

Queste impostazioni controllano il comportamento dello zoom Fancybox e la sua interazione con i tuoi clienti.

- **Crea galleria**

  - **Cosa fa questa impostazione:** Determina se tutte le immagini del prodotto (immagine principale e miniature) sono raggruppate in un'unica galleria Fancybox. Quando abilitato, cliccando su qualsiasi immagine si aprirà Fancybox, e i clienti potranno quindi navigare tra tutte le immagini del prodotto utilizzando le frecce.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* I clienti possono sfogliare tutte le immagini del prodotto in una sovrapposizione Fancybox a schermo intero, utilizzando le frecce di navigazione. Questo fornisce una visione completa del prodotto.
    - *Quando disabilitato ("No"):* Cliccando su un'immagine si aprirà solo quell'immagine specifica in Fancybox. I clienti non possono navigare ad altre immagini del prodotto dalla visualizzazione Fancybox.
  - **Valore consigliato:** "Sì" per una migliore esperienza utente e per incoraggiare i clienti a visualizzare tutti gli angoli del prodotto.
  - **Scenario / esempio del commerciante:** Vuoi che i clienti possano sfogliare facilmente tutte le immagini del prodotto senza chiudere e riaprire lo zoom per ciascuna. Abilita questa opzione.
- **Scorrimento (Swipe)**

  - **Cosa fa questa impostazione:** Abilita o disabilita i gesti di scorrimento (swipe) per navigare nella galleria Fancybox su dispositivi touch (smartphone, tablet).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* I clienti possono scorrere a sinistra o a destra sui loro dispositivi touch per spostarsi tra le immagini nella galleria Fancybox.
    - *Quando disabilitato ("No"):* I gesti di scorrimento non funzioneranno. I clienti dovranno utilizzare le frecce di navigazione (se "Crea galleria" è abilitato).
  - **Valore consigliato:** "Sì" per un'esperienza mobile moderna e intuitiva.
  - **Scenario / esempio del commerciante:** Vuoi che i tuoi utenti mobili abbiano un modo fluido e naturale per sfogliare le immagini dei prodotti. Mantieni questa opzione abilitata.
- **Evita immagine di copertina duplicata nella galleria**

  - **Cosa fa questa impostazione:** Quando "Crea galleria" è abilitato, a volte l'immagine principale del prodotto potrebbe apparire due volte nella galleria (una volta come immagine principale e di nuovo se è anche elencata come miniatura). Questa impostazione previene tale duplicazione.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Il modulo cercherà di rilevare e rimuovere qualsiasi immagine principale del prodotto duplicata dalla galleria Fancybox, assicurando che ogni immagine appaia solo una volta.
    - *Quando disabilitato ("No"):* Se l'immagine principale del prodotto fa anche parte dell'elenco delle miniature, potrebbe apparire due volte nella galleria Fancybox.
  - **Valore consigliato:** "Sì" per un'esperienza di galleria più pulita e professionale.
  - **Scenario / esempio del commerciante:** Noti che quando i clienti aprono la galleria Fancybox, la prima immagine è identica alla seconda. L'abilitazione di questa opzione risolverà il problema.
- **Mostra didascalie (titoli immagini)**

  - **Cosa fa questa impostazione:** Controlla se il titolo/didascalia associato a ciascuna immagine del prodotto viene visualizzato all'interno della sovrapposizione Fancybox. Questi titoli sono solitamente impostati nella gestione delle immagini del prodotto di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Il titolo dell'immagine apparirà come didascalia sotto o sopra l'immagine nella sovrapposizione Fancybox.
    - *Quando disabilitato ("No"):* Non verrà visualizzata alcuna didascalia, fornendo una visualizzazione più pulita, solo immagine.
  - **Valore consigliato:** "Sì" se i tuoi titoli immagine forniscono informazioni utili (es. "Vista frontale", "Dettaglio del tessuto", "Modello che indossa il prodotto"). "No" se i tuoi titoli immagine sono generici o preferisci un aspetto minimalista.
  - **Scenario / esempio del commerciante:** Utilizzi titoli descrittivi per le immagini dei tuoi prodotti e vuoi che i clienti li vedano quando ingrandiscono. Abilita questa opzione.
- **Cambia immagine principale al passaggio del mouse sulla miniatura**

  - **Cosa fa questa impostazione:** Determina se il passaggio del mouse su una miniatura del prodotto cambia automaticamente l'immagine principale del prodotto visualizzata sulla pagina prodotto, *prima* di cliccare per aprire Fancybox.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Spostando il cursore del mouse su una miniatura si scambierà istantaneamente l'immagine principale del prodotto per mostrare la miniatura su cui si è passato il mouse. Questa è una funzione comune e conveniente per gli acquirenti.
    - *Quando disabilitato ("No"):* L'immagine principale del prodotto cambierà solo quando si clicca su una miniatura, non solo passando il mouse.
  - **Valore consigliato:** "Sì" per un'esperienza di navigazione più interattiva e user-friendly.
  - **Scenario / esempio del commerciante:** Vuoi che i clienti possano visualizzare rapidamente diverse immagini del prodotto semplicemente muovendo il mouse, senza dover cliccare. Abilita questa opzione.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Supporto tema** | Classic / Hummingbird | Seleziona selettori CSS predefiniti per il tuo tema (Classic, Hummingbird o Custom). Cruciale per la funzionalità del modulo. |
| Configurazione modulo | **Profilo tema rilevato** | N/A (Informativo) | Mostra quale profilo tema è attualmente attivo. |
| Configurazione modulo | **Selettore copertina Hummingbird** | Predefinito | Selettore CSS per il contenitore dell'immagine principale (tema Hummingbird). |
| Configurazione modulo | **Selettore immagine Hummingbird** | Predefinito | Selettore CSS per il tag `<img>` principale (tema Hummingbird). |
| Configurazione modulo | **Selettore miniature Hummingbird** | Predefinito | Selettore CSS per il contenitore delle miniature (tema Hummingbird). |
| Configurazione modulo | **Selettore immagine di copertina principale** | Custom (Ispeziona tema) | Selettore CSS per il contenitore dell'immagine principale (tema Custom). |
| Configurazione modulo | **Immagine di copertina principale** | Custom (Ispeziona tema) | Selettore CSS per il tag `<img>` principale (tema Custom). |
| Configurazione modulo | **Selettore immagini miniature** | Custom (Ispeziona tema) | Selettore CSS per il contenitore delle miniature (tema Custom). |
| Configurazione modulo | **Crea galleria** | Sì | Raggruppa tutte le immagini del prodotto in una galleria Fancybox navigabile. |
| Configurazione modulo | **Scorrimento (Swipe)** | Sì | Abilita i gesti di scorrimento per la navigazione della galleria su dispositivi touch. |
| Configurazione modulo | **Evita immagine di copertina duplicata nella galleria** | Sì | Impedisce che l'immagine principale appaia due volte nella galleria. |
| Configurazione modulo | **Mostra didascalie (titoli immagini)** | Sì / No (Preferenza commerciante) | Mostra i titoli delle immagini come didascalie nella sovrapposizione Fancybox. |
| Configurazione modulo | **Cambia immagine principale al passaggio del mouse sulla miniatura** | Sì | Cambia l'immagine principale del prodotto al passaggio del mouse sulla miniatura. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Lo zoom Fancybox non appare affatto sulle mie pagine prodotto.**
R:

1.  **Controlla lo stato del modulo:** Assicurati che il modulo sia installato e abilitato in **Moduli > Gestione moduli**.
2.  **Impostazione del supporto tema:** Vai alla pagina di configurazione del modulo. Se stai utilizzando il tema "Classic", assicurati che "Supporto tema" sia impostato su "Classic". Se sei su PrestaShop 8.1+ con il tema Hummingbird, impostalo su "Hummingbird". Se hai un tema personalizzato, impostalo su "Custom" e rivedi attentamente i selettori CSS che hai inserito (vedi punto successivo).
3.  **Selettori del tema personalizzato:** Se "Supporto tema" è "Custom", il problema più comune sono i selettori CSS errati. Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare la tua pagina prodotto. Trova le classi o gli ID CSS esatti per il contenitore dell'immagine principale del tuo prodotto, il tag `<img>` e il contenitore delle miniature. Aggiornali nelle impostazioni del modulo.

**D: Fancybox si apre, ma mostra l'immagine sbagliata o solo un'immagine.**
R:

1.  **Impostazione "Crea galleria":** Assicurati che "Crea galleria" sia impostato su "Sì" nella configurazione del modulo se desideri sfogliare più immagini.
2.  **Selettori miniature:** Se "Crea galleria" è attivo ma appare solo un'immagine, controlla il tuo "Selettore immagini miniature" (specialmente se "Supporto tema" è "Custom"). Il modulo deve identificare correttamente tutte le tue miniature per costruire la galleria.
3.  **Titoli/didascalie immagini:** Se le didascalie non vengono visualizzate, assicurati che "Mostra didascalie (titoli immagini)" sia "Sì" e che le immagini dei tuoi prodotti abbiano effettivamente dei titoli definiti nel back office di PrestaShop.

**D: I gesti di scorrimento non funzionano sul mio dispositivo mobile.**
R:

1.  **Impostazione "Scorrimento (Swipe)":** Assicurati che l'opzione "Scorrimento (Swipe)" sia impostata su "Sì" nella configurazione del modulo.
2.  **Galleria abilitata:** Lo scorrimento funziona solo se anche "Crea galleria" è "Sì", poiché serve per navigare tra più immagini.
3.  **Compatibilità browser/dispositivo:** Sebbene ampiamente supportato, browser molto vecchi o configurazioni specifiche di dispositivi potrebbero avere problemi. Testa su un browser mobile moderno.

**D: Il layout della mia pagina prodotto sembra un po' strano dopo l'installazione del modulo.**
R:

1.  **Svuota cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache". A volte, i vecchi file di cache possono interferire con il nuovo stile del modulo.
2.  **Conflitti con il tema:** Sebbene il modulo cerchi di essere compatibile, CSS di temi personalizzati molto specifici potrebbero entrare in conflitto. Se svuotare la cache non aiuta, disabilita temporaneamente il modulo per vedere se il problema scompare. Se lo fa, potresti aver bisogno di uno sviluppatore web per regolare il CSS del tuo tema o i selettori personalizzati del modulo.

**D: Come trovo i selettori CSS corretti per il mio tema personalizzato?**
R:

1.  Apri la tua pagina prodotto in un browser web (Chrome, Firefox, Edge).
2.  Fai clic destro sull'immagine principale del tuo prodotto e seleziona "Ispeziona" o "Ispeziona elemento".
3.  Questo aprirà gli strumenti per sviluppatori del browser. Cerca il tag `<img>` della tua immagine principale e il suo `<div>` genitore o un altro contenitore. Annota eventuali attributi `id` univoci (es. `id="my-image"`) o attributi `class` (es. `class="product-image-wrapper"`).
4.  Ripeti questo per le miniature dei tuoi prodotti.
5.  Usa questi ID (prefissati con `#`, es. `#my-image`) o classi (prefissate con `.`, es. `.product-image-wrapper`) nelle impostazioni del tema "Custom" del modulo. Potrebbe essere necessario sperimentare un po' per trovare i selettori più specifici e affidabili.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `fancyzoom` è un modulo PrestaShop leggero progettato principalmente per sostituire la funzionalità di zoom immagine predefinita del prodotto con Fancybox. Lo fa agganciandosi a `displayHeader` per iniettare il suo JavaScript e CSS personalizzati, e utilizzando JavaScript per identificare e reinizializzare gli elementi immagine con Fancybox. La configurazione del modulo è gestita tramite il metodo standard `getContent()` nel file principale del modulo, memorizzando le impostazioni in `ps_configuration`. Non introduce tabelle di database personalizzate, classi `ObjectModel` o controller front/admin dedicati oltre alla configurazione del modulo principale.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Tutte le funzionalità del front-office vengono iniettate tramite hook e gestite da JavaScript.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione del back-office è gestita dal metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuna classe personalizzata o definizione `ObjectModel` è presente nella directory `classes/`. Tutta la logica principale risiede all'interno del file principale del modulo `fancyzoom.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include due file JavaScript, principalmente per la funzionalità del front-office. Sono registrati tramite l'hook `displayHeader`.

-   `fancyzoom/views/templates/js/fancyzoom.js`

    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo è lo script principale che inizializza Fancybox. Identifica dinamicamente l'immagine principale del prodotto e le miniature in base ai selettori CSS configurati (o ai selettori predefiniti Classic/Hummingbird). Quindi associa gli eventi di clic a queste immagini per aprirle in una galleria Fancybox. Gestisce anche la funzionalità "cambia immagine principale al passaggio del mouse sulla miniatura". È responsabile della disabilitazione dello zoom predefinito di PrestaShop.
    -   **Funzionalità chiave:**
        -   Disabilita lo zoom immagine predefinito di PrestaShop.
        -   Rileva il profilo del tema (Classic, Hummingbird, Custom) e applica i selettori appropriati.
        -   Inizializza Fancybox sulle immagini dei prodotti.
        -   Gestisce la creazione della galleria Fancybox e le opzioni (scorrimento, didascalie, immagini duplicate).
        -   Gestisce l'effetto hover delle miniature per cambiare l'immagine principale.
        -   Ascolta l'evento `updateProduct` (aggiornamenti della pagina prodotto di PrestaShop 1.7+) per reinizializzare Fancybox.
-   `fancyzoom/views/templates/js/touchswipe.js`

    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questa è una libreria di terze parti che fornisce un robusto rilevamento degli eventi di scorrimento touch. Viene utilizzata da `fancyzoom.js` per abilitare la navigazione tramite scorrimento all'interno della galleria Fancybox sui dispositivi touch.
    -   **Funzionalità chiave:** Fornisce un plugin jQuery per il rilevamento dei gesti di scorrimento (sinistra, destra, su, giù) e altri eventi touch.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include un file CSS per lo stile del front-office.

-   `fancyzoom/views/templates/css/fancyzoom.css`
    -   **Ambito:** Stile del cliente del front-office.
    -   **Responsabilità:** Contiene il CSS necessario per la sovrapposizione di Fancybox stessa, inclusi lo stile per le frecce di navigazione, il pulsante di chiusura, le didascalie e l'aspetto generale. Assicura che il modale Fancybox sia posizionato e stilizzato correttamente.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:**
        -   `.fancybox-container`: Contenitore principale per la sovrapposizione Fancybox.
        -   `.fancybox-bg`: Sovrapposizione di sfondo.
        -   `.fancybox-toolbar`: Barra degli strumenti con pulsante di chiusura, ecc.
        -   `.fancybox-caption`: Area della didascalia.
        -   `.fancybox-button`: Pulsanti (chiudi, navigazione).
        -   `.fancybox-image`: L'immagine stessa all'interno di Fancybox.
        Gli sviluppatori possono sovrascrivere queste classi nel file `custom.css` del loro tema o in un file simile per adattarle al branding del loro negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:

    -   `fancyzoom/views/templates/hook/fancyzoom.tpl`
        -   **Hook:** `displayHeader`
        -   **Scopo:** Questo template è responsabile dell'iniezione delle variabili JavaScript necessarie e dei file JS e CSS del modulo nella sezione `<head>` del front-office. Passa le variabili di configurazione dal back office (come selettori, opzioni della galleria) allo script `fancyzoom.js`.
-   **Template admin (`views/templates/admin/`)**:

    -   `fancyzoom/views/templates/admin/admin.tpl`
        -   **Scopo:** Questo template renderizza il modulo di configurazione del modulo nel back office di PrestaShop. Visualizza tutte le impostazioni descritte nella Sezione 4.1, inclusi i campi di input per i selettori, le caselle di controllo per le opzioni della galleria e il rilevamento del profilo del tema.
-   **Template front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle di database personalizzate. Tutte le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi prefissate con `FZ_` (es. `FZ_THEME`, `FZ_COVER_DIV`, `FZ_GALLERY`).
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS e JavaScript del modulo e passa le variabili di configurazione agli script del front-end. Qui vengono caricati la libreria Fancybox e la sua logica di inizializzazione. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Fancybox products image zoom", accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
