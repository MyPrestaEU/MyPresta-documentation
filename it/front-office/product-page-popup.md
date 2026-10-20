---
title: "Popup pagina prodotto - Manuale commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Popup pagina prodotto di MyPresta.eu."
sidebar:
  label: "Popup pagina prodotto - Manuale commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product page popup su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-popup.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-page-popup/)
>
> ---


# Popup pagina prodotto

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, verrai reindirizzato alla pagina di configurazione principale del modulo. Qui puoi gestire tutti i tuoi popup della pagina prodotto.

La pagina di configurazione è divisa in due sezioni principali:

1.  Scheda **"Aggiungi nuovo popup"**: Per creare nuove finestre popup.
2.  Scheda **"Elenco dei popup"**: Per visualizzare, modificare o eliminare i popup esistenti.

#### 2.1.1 Scheda "Aggiungi nuovo popup"

Questa scheda ti consente di definire una nuova finestra popup e le sue impostazioni associate.

-   **Nome popup:**

    -   **Cosa fa questa impostazione:** Questo è un nome interno per il tuo popup, visibile solo nel tuo back office PrestaShop. Ti aiuta a identificare e gestire diversi popup.
    -   **Effetto della modifica di questa impostazione:** La modifica di questo nome influisce solo su come lo vedi nel back office; non ha alcun impatto sul front office o sull'esperienza del cliente.
    -   **Valore consigliato:** Usa un nome descrittivo, ad esempio "Saldi estivi sulle magliette", "Guida alle taglie per i jeans", "Tutorial video per il prodotto X".
    -   **Scenario/esempio per il commerciante:** Se hai un popup per un prodotto specifico, chiamalo con il nome di quel prodotto per trovarlo facilmente in seguito.
-   **Contenuto popup:**

    -   **Cosa fa questa impostazione:** Questo è il contenuto principale che verrà visualizzato all'interno della finestra popup. È un editor di testo ricco (TinyMCE) dove puoi aggiungere testo, immagini, video, link e persino HTML personalizzato.
    -   **Effetto della modifica di questa impostazione:** Questo cambia direttamente ciò che i tuoi clienti vedono quando appare il popup. Puoi renderlo informativo, promozionale o interattivo.
    -   **Valore consigliato:** Mantienilo conciso e visivamente accattivante. Usa titoli, elenchi puntati e immagini pertinenti.
    -   **Scenario/esempio per il commerciante:** Potresti aggiungere un codice sconto, un video di YouTube incorporato che dimostra il prodotto o una tabella dettagliata delle taglie.
-   **Larghezza popup (px):**

    -   **Cosa fa questa impostazione:** Definisce la larghezza della finestra popup in pixel.
    -   **Effetto della modifica di questa impostazione:** Una larghezza maggiore renderà il popup più ampio, potendo ospitare più contenuto orizzontalmente. Una larghezza minore lo renderà più stretto.
    -   **Valore consigliato:** Inizia con `600px` e regola in base al tuo contenuto. Assicurati che appaia bene su varie dimensioni di schermo.
    -   **Scenario/esempio per il commerciante:** Se il tuo popup contiene un'immagine ampia o una tabella, potresti aver bisogno di una larghezza maggiore. Per testo semplice, una larghezza più stretta potrebbe essere sufficiente.
-   **Altezza popup (px):**

    -   **Cosa fa questa impostazione:** Definisce l'altezza della finestra popup in pixel.
    -   **Effetto della modifica di questa impostazione:** Un'altezza maggiore renderà il popup più alto, consentendo più contenuto verticale senza scorrimento. Un'altezza minore lo renderà più corto, richiedendo potenzialmente lo scorrimento se il contenuto supera l'altezza.
    -   **Valore consigliato:** Inizia con `400px` e regola in base al tuo contenuto.
    -   **Scenario/esempio per il commerciante:** Se hai una lunga descrizione testuale o un'immagine alta, aumenta l'altezza. Se il contenuto è breve, un'altezza minore appare più pulita.
-   **Colore sfondo popup:**

    -   **Cosa fa questa impostazione:** Ti consente di scegliere il colore di sfondo della finestra popup stessa. Utilizza uno strumento di selezione colore.
    -   **Effetto della modifica di questa impostazione:** Cambia l'aspetto visivo del popup, aiutandolo a corrispondere al branding del tuo negozio o a risaltare.
    -   **Valore consigliato:** Scegli un colore che si abbini al design del tuo negozio e garantisca una buona leggibilità del tuo contenuto.
    -   **Scenario/esempio per il commerciante:** Usa il colore primario del tuo brand per lo sfondo, o un bianco/grigio chiaro neutro per la massima leggibilità.
-   **Colore bordo popup:**

    -   **Cosa fa questa impostazione:** Ti consente di scegliere il colore del bordo attorno alla finestra popup.
    -   **Effetto della modifica di questa impostazione:** Aggiunge una cornice visiva al popup, definendone i bordi.
    -   **Valore consigliato:** Spesso, un colore del bordo sottile che si abbini all'estetica del tuo negozio o un colore contrastante per far risaltare il popup.
    -   **Scenario/esempio per il commerciante:** Un bordo grigio chiaro per un look pulito, o un colore vibrante se il popup deve essere molto accattivante.
-   **Spessore bordo popup (px):**

    -   **Cosa fa questa impostazione:** Definisce lo spessore del bordo del popup in pixel.
    -   **Effetto della modifica di questa impostazione:** Un valore più alto rende il bordo più spesso e più prominente.
    -   **Valore consigliato:** `1px` o `2px` per un bordo sottile.
    -   **Scenario/esempio per il commerciante:** Un bordo di `5px` potrebbe essere utilizzato per un messaggio molto audace e urgente, mentre `1px` è più comune per informazioni generali.
-   **Raggio bordo popup (px):**

    -   **Cosa fa questa impostazione:** Controlla la rotondità degli angoli del popup. Un valore di `0` significa angoli netti e quadrati. Valori più alti creano angoli più arrotondati.
    -   **Effetto della modifica di questa impostazione:** Influisce sull'estetica generale del popup, rendendolo più morbido o più moderno.
    -   **Valore consigliato:** `0px` per angoli netti, da `5px` a `10px` per angoli leggermente arrotondati.
    -   **Scenario/esempio per il commerciante:** Se il design del tuo negozio utilizza elementi arrotondati, un raggio del bordo di `10px` farebbe sì che il popup si integri meglio.
-   **Colore overlay popup:**

    -   **Cosa fa questa impostazione:** Questo è il colore dello strato semi-trasparente che appare dietro il popup, oscurando il resto della pagina del prodotto.
    -   **Effetto della modifica di questa impostazione:** Cambia il contrasto visivo tra il popup e lo sfondo. Un overlay più scuro fa risaltare di più il popup.
    -   **Valore consigliato:** Un nero semi-trasparente (`#000000` con una certa trasparenza) è standard.
    -   **Scenario/esempio per il commerciante:** Un overlay leggermente più chiaro potrebbe essere utilizzato se si desidera che le informazioni sul prodotto di sfondo siano ancora in qualche modo visibili.
-   **Opacità overlay popup (0-100):**

    -   **Cosa fa questa impostazione:** Controlla la trasparenza del colore dell'overlay. `0` è completamente trasparente (invisibile), `100` è completamente opaco (colore solido, nasconde completamente lo sfondo).
    -   **Effetto della modifica di questa impostazione:** Determina quanto della pagina del prodotto sottostante è visibile attraverso l'overlay.
    -   **Valore consigliato:** `70` a `80` è un buon equilibrio, rendendo il popup prominente senza oscurare completamente la pagina.
    -   **Scenario/esempio per il commerciante:** Se vuoi che il cliente veda ancora leggermente l'immagine del prodotto dietro il popup, usa un'opacità inferiore come `50`.
-   **Prodotti per questo popup:**

    -   **Cosa fa questa impostazione:** Questa è la parte cruciale in cui selezioni quali prodotti specifici attiveranno questo popup. Puoi cercare prodotti per nome.
    -   **Effetto della modifica di questa impostazione:** Il popup apparirà *solo* sulle pagine dei prodotti che selezioni qui. Se non vengono selezionati prodotti, il popup non apparirà da nessuna parte.
    -   **Valore consigliato:** Seleziona tutti i prodotti pertinenti per questo messaggio specifico.
    -   **Scenario/esempio per il commerciante:** Se hai creato un popup con una guida alle taglie per "Magliette da uomo", selezioneresti qui tutti i tuoi prodotti di magliette da uomo.

Dopo aver configurato tutte le impostazioni, clicca sul pulsante **"Salva"** per creare il tuo nuovo popup.

#### 2.1.2 Scheda "Elenco dei popup"

Questa scheda visualizza una tabella di tutti i popup che hai creato.

-   **Colonne della tabella:**
    -   **ID:** Identificatore univoco per il popup.
    -   **Nome:** Il nome interno che hai dato al popup.
    -   **Prodotti:** Elenca il numero di prodotti associati a questo popup.
    -   **Azioni:**
        -   **Modifica:** Clicca sull'icona della matita per tornare alla scheda "Aggiungi nuovo popup" con tutte le impostazioni del popup corrente precompilate, consentendoti di modificarle.
        -   **Elimina:** Clicca sull'icona del cestino per rimuovere definitivamente il popup. Apparirà una richiesta di conferma.
-   **Effetto delle modifiche:**
    -   **Modifica:** Ti consente di aggiornare contenuto, stile o associazioni di prodotti per un popup esistente senza crearne uno nuovo.
    -   **Elimina:** Rimuove permanentemente il popup dal tuo negozio. Non apparirà più su nessuna pagina di prodotto.
-   **Flusso di lavoro consigliato:** Rivedi regolarmente questo elenco per assicurarti che tutti i tuoi popup siano aggiornati e pertinenti. Elimina eventuali promozioni o informazioni obsolete.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Aggiungi nuovo popup** | Nome popup | Nome descrittivo | Identificazione interna per il back office. |
| | Contenuto popup | HTML/Testo personalizzato | Messaggio principale visualizzato al cliente. |
| | Larghezza popup (px) | 600px | Dimensione orizzontale del popup. |
| | Altezza popup (px) | 400px | Dimensione verticale del popup. |
| | Colore sfondo popup | Bianco / Colore del brand | Colore di sfondo dell'area contenuto del popup. |
| | Colore bordo popup | Sottile / Colore del brand | Colore della cornice attorno al popup. |
| | Spessore bordo popup (px) | 1px - 2px | Spessore del bordo del popup. |
| | Raggio bordo popup (px) | 0px - 10px | Rotondità degli angoli del popup. |
| | Colore overlay popup | Nero semi-trasparente | Colore dello sfondo oscurato. |
| | Opacità overlay popup (0-100) | 70 - 80 | Trasparenza dell'overlay di sfondo. |
| | Prodotti per questo popup | Seleziona i prodotti pertinenti | Determina su quali pagine prodotto appare il popup. |
| **Elenco dei popup** | Azione Modifica | N/A | Modifica le impostazioni di un popup esistente. |
| | Azione Elimina | N/A | Rimuove un popup in modo permanente. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il mio popup non appare sulla pagina del prodotto. Cosa devo controllare?**
R:

1.  **Il popup è associato al prodotto corretto?** Vai alla configurazione del modulo, modifica il tuo popup e assicurati che il prodotto specifico su cui stai testando sia selezionato nel campo "Prodotti per questo popup".
2.  **Il modulo è abilitato?** In **Moduli > Gestione moduli**, assicurati che "Popup pagina prodotto" sia installato e abilitato.
3.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Potrebbe essere necessario svuotare anche la cache del tuo browser (Ctrl+F5 o Cmd+R).
4.  **Controlla gli errori JavaScript:** Apri la console per sviluppatori del tuo browser (F12) e cerca eventuali errori nella scheda "Console". Se vedi errori, potrebbe indicare un conflitto con un altro modulo o il tuo tema.

**D: Il popup ha un aspetto strano o non corrisponde allo stile del mio tema.**
R:

1.  **Rivedi le impostazioni di stile del popup:** Ricontrolla le impostazioni "Colore sfondo popup", "Colore bordo popup", "Spessore bordo popup" e "Raggio bordo popup" nella configurazione del modulo.
2.  **Conflitti con il tema:** Il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo. Se hai familiarità con il CSS, puoi ispezionare gli elementi del popup utilizzando gli strumenti per sviluppatori del tuo browser per identificare gli stili in conflitto. Per problemi di stile complessi, potresti aver bisogno dell'assistenza di uno sviluppatore web.

**D: Posso avere più popup sulla stessa pagina del prodotto?**
R: No, il modulo è progettato per visualizzare un popup specifico per pagina del prodotto. Se un prodotto è associato a più popup, ne verrà visualizzato solo uno (tipicamente il primo trovato o quello con l'ID più basso, anche se questo comportamento non è esplicitamente garantito e dovrebbe essere evitato). La migliore pratica è creare un popup completo per prodotto o gruppo di prodotti.

**D: Come traduco il contenuto del popup in diverse lingue?**
R: Il campo "Contenuto popup" nella configurazione del modulo dovrebbe offrire schede linguistiche se il tuo negozio PrestaShop ha più lingue abilitate. Basta passare alla scheda della lingua desiderata e inserire il contenuto tradotto per quella lingua.

**D: Il contenuto del popup è troppo lungo e richiede lo scorrimento. Come posso risolvere questo problema?**
R:

1.  **Aumenta l'altezza del popup:** Nella configurazione del modulo, aumenta il valore di "Altezza popup (px)".
2.  **Condensa il contenuto:** Cerca di rendere il contenuto del tuo popup più conciso. Usa elenchi puntati, paragrafi più brevi e, se possibile, link a pagine esterne per informazioni molto dettagliate.
3.  **Ottimizza immagini/video:** Assicurati che qualsiasi media nel tuo popup sia ottimizzato per l'uso web per prevenire tempi di caricamento eccessivi e migliorare la visualizzazione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Product page popup` per PrestaShop 1.5.x e 1.6.x segue un modello di progettazione monolitico e diretto, tipico dei moduli PrestaShop più vecchi. Utilizza principalmente la classe `Module` per la sua funzionalità principale, gestendo installazione, disinstallazione e configurazione. La visualizzazione nel front-office è gestita agganciandosi a punti di visualizzazione standard, mentre la configurazione è gestita tramite il metodo `getContent()` all'interno del file principale del modulo. I dati sono archiviati direttamente in `ps_configuration` e gestiti tramite interazioni standard del database PrestaShop. Non ci sono classi `ObjectModel` personalizzate o controller front/admin dedicati oltre al file principale del modulo.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il front-office o il back-office nella directory `controllers/`. Tutta la logica del front-office è gestita direttamente all'interno del file principale del modulo tramite hook, e tutta la configurazione del back-office è gestita dal metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non contiene classi o modelli PHP personalizzati nella directory `classes/`. Tutta la gestione dei dati e la logica di business sono incapsulate all'interno del file principale del modulo `ajax_productpopup.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`productpopup/js/jscolor/jscolor.js`**
    -   **Ambito:** Back-office.
    -   **Descrizione:** Questa è una libreria JavaScript di terze parti per fornire una funzionalità di selezione colore. Viene utilizzata nel modulo di configurazione per consentire ai commercianti di selezionare facilmente i colori per lo sfondo, il bordo e l'overlay del popup. Tipicamente funziona collegandosi a campi di input con una classe specifica (ad esempio, `jscolor`).
-   **`productpopup/js/script.js`**
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo script contiene la logica principale per la visualizzazione del popup nel front office.
        -   **Event Listeners:** Probabilmente ascolta l'evento `DOMContentLoaded` o simili per assicurarsi che la pagina sia completamente caricata.
        -   **Manipolazione del DOM:** È responsabile di:
            -   Verificare se l'ID del prodotto corrente ha un popup associato.
            -   Creare dinamicamente la struttura HTML del popup (overlay, contenitore popup, area contenuto, pulsante di chiusura).
            -   Iniettare il contenuto del popup (recuperato dalla configurazione del modulo).
            -   Applicare gli stili configurati (larghezza, altezza, colori, bordo, opacità).
            -   Visualizzare il popup con un'animazione (ad esempio, fade-in).
            -   Associare eventi per chiudere il popup (clic sul pulsante di chiusura, clic sull'overlay, pressione del tasto ESC).
-   **`productpopup/js/tinymce16.inc.js`**
    -   **Ambito:** Back-office.
    -   **Descrizione:** Questo file è uno script di integrazione per l'editor di testo ricco TinyMCE, specificamente adattato per ambienti PrestaShop 1.6.x. Inizializza l'editor TinyMCE per l'area di testo "Contenuto popup" nel modulo di configurazione, fornendo al commerciante un'interfaccia WYSIWYG per creare contenuti HTML ricchi per i popup. Configura le opzioni di TinyMCE come i pulsanti disponibili, i plugin e le impostazioni della lingua.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`productpopup/css/productpopup.css`**
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo foglio di stile definisce l'aspetto visivo predefinito e il layout del popup della pagina prodotto e del suo overlay.
        -   **Componenti UI principali:** Stili per `.productpopup-overlay` (lo sfondo oscurato) e `.productpopup-container` (la scatola del popup vera e propria).
        -   **Selettori di classe CSS chiave:**
            -   `.productpopup-overlay`: Controlla `position`, `top`, `left`, `width`, `height`, `background-color`, `opacity`, `z-index`.
            -   `.productpopup-container`: Controlla `position`, `top`, `left`, `transform` (per il centraggio), `background-color`, `border`, `border-radius`, `box-shadow`, `z-index`, `overflow`.
            -   `.productpopup-content`: Stili per l'area del contenuto interno, inclusi `padding`, `font-size`, `line-height`.
            -   `.productpopup-close`: Stili per il pulsante di chiusura (ad esempio, `position`, `top`, `right`, `font-size`, `color`, `cursor`).
        -   **Override dello sviluppatore:** Gli sviluppatori possono sovrascrivere questi stili nel `global.css` del loro tema o creando un foglio di stile personalizzato caricato dopo questo, mirando a queste classi specifiche.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Questo modulo non definisce esplicitamente template per hook specifici in questa directory. L'HTML del popup del front-office è probabilmente generato dinamicamente da `script.js` in base alla configurazione.
-   **Template admin (`views/templates/admin/`)**:
    -   **`productpopup/views/templates/admin/tabs-no-product.tpl`**
        -   **Descrizione:** Questo template è probabilmente utilizzato all'interno del metodo `getContent()` del modulo per renderizzare il modulo "Aggiungi nuovo popup" quando nessun popup specifico è in fase di modifica, o forse una versione semplificata del modulo. Contiene i campi di input per il nome del popup, il contenuto, le dimensioni, i colori e l'interfaccia di selezione del prodotto.
    -   **`productpopup/views/templates/admin/tabs.tpl`**
        -   **Descrizione:** Questo è il template principale per la pagina di configurazione del back-office del modulo. Tipicamente renderizza la struttura a schede (ad esempio, "Aggiungi nuovo popup" e "Elenco dei popup") e include il contenuto di altri template admin (come `tabs-no-product.tpl`) all'interno dei suoi pannelli a schede. Renderizza anche la tabella per elencare i popup esistenti.
-   **Template front-office (`views/templates/front/`)**:
    -   **`productpopup/views/templates/front/footer.tpl`**
        -   **Descrizione:** Questo template è probabilmente utilizzato per produrre un piccolo contenitore HTML nascosto o una variabile JavaScript che contiene i dati del popup (contenuto, stili, ID prodotto) affinché `script.js` del front-office li raccolga e renderizzi il popup dinamicamente. È tipicamente agganciato a `displayFooter` o `displayHeader` per garantire che i dati siano disponibili ad ogni caricamento della pagina.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione e i dati del popup sono archiviati nella tabella di configurazione standard di PrestaShop: `ps_configuration`.
    -   **Chiavi di configurazione**:
        -   `PRODUCTPOPUP_DATA`: Archivia dati serializzati per tutti i popup creati, inclusi il loro contenuto, lo stile e gli ID prodotto associati. Questa chiave contiene una struttura array complessa.
        -   Potrebbero esistere altre chiavi per le impostazioni globali del modulo, se presenti, ma i dati primari si trovano in `PRODUCTPOPUP_DATA`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Probabilmente utilizzato per includere file CSS e JavaScript (`productpopup.css`, `script.js`) per la funzionalità del popup nel front-office. |
| `displayFooter` | Eseguito alla fine della sezione `<body>` di ogni pagina. | Potrebbe essere utilizzato per produrre i dati nascosti per `script.js` o per garantire che la struttura HTML del popup sia aggiunta al DOM dopo tutto il resto del contenuto. |
| `displayProductTab` (PrestaShop 1.6.x) / `displayProductExtraContent` (PrestaShop 1.7+) | Eseguito sulla pagina del prodotto, tipicamente all'interno delle schede del prodotto o dell'area del contenuto extra. | Sebbene la descrizione del modulo implichi un modale, potrebbe utilizzare questo hook per iniettare un trigger per il popup, o per garantire che il suo JS sia caricato specificamente sulle pagine dei prodotti. |
| `displayRightColumn` / `displayLeftColumn` | Eseguito nelle colonne laterali del negozio. | Meno probabile per un popup della pagina del prodotto, ma potrebbe essere utilizzato per iniettare un trigger globale o un piccolo script se necessario. |
| `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Eseguito quando un prodotto viene aggiunto, aggiornato o eliminato. | Potrebbe essere utilizzato per aggiornare o pulire i `PRODUCTPOPUP_DATA` in `ps_configuration` se un prodotto associato a un popup viene rimosso. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto dedicato agli sviluppatori, fai riferimento al tuo account cliente su MyPresta.eu. Assicurati di scaricare l'ultima versione del modulo "Popup pagina prodotto" compatibile con la tua installazione PrestaShop. Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
