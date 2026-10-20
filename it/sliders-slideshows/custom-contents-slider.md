---
title: "Slider contenuti personalizzati - Manuale per il commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Slider contenuti personalizzati' di MyPresta.eu."
sidebar:
  label: "Slider contenuti personalizzati - Manuale per il commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Custom contents slider su MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/custom-contents-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/sliders-slideshows/custom-contents-slider/)
>
> ---


# Slider contenuti personalizzati

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono in genere sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali del modulo "Slider contenuti personalizzati". Qui è dove definisci il contenuto, l'aspetto e il comportamento dei tuoi slider.

La pagina di configurazione è alimentata dalla libreria `SmartyTemplatesManager`, che ti consente di creare e gestire più blocchi di contenuto personalizzati.

#### **Modulo principale (mainForm.tpl)**

Questa sezione fornisce una panoramica dei tuoi slider esistenti e ti consente di aggiungerne di nuovi.

-   **Cosa fa questa sezione:** Visualizza un elenco di tutti gli slider di contenuto personalizzati che hai creato. Ogni voce mostra informazioni di base come il nome, la posizione e lo stato dello slider.
-   **Effetto della modifica di questa sezione:** Da qui, puoi vedere rapidamente quali slider sono attivi e dove sono visualizzati. Puoi anche cliccare per modificare gli slider esistenti o aggiungerne di nuovi.
-   **Azione consigliata:** Rivedi i tuoi slider esistenti. Se stai configurando per la prima volta, vorrai cliccare sul pulsante "Aggiungi nuovo modello".

#### **Modulo Crea/Modifica modello (createTemplateForm.tpl / editTemplateForm.tpl)**

Quando clicchi su "Aggiungi nuovo modello" o "Modifica" uno slider esistente, verrai indirizzato a un modulo in cui definisci tutti i dettagli per quello specifico slider.

-   **Nome modello:**

    -   **Cosa fa questa impostazione:** Questo è un nome interno per il tuo slider, visibile solo nel back office. Ti aiuta a identificare diversi slider.
    -   **Effetto della modifica di questa impostazione:** La modifica di questo influisce solo su come lo vedi nel pannello di amministrazione; non ha alcun impatto sul front-office.
    -   **Valore consigliato:** Un nome descrittivo, ad esempio "Slider Saldi Estivi Sinistro", "Iscrizione Newsletter Inferiore".
    -   **Scenario / esempio per il commerciante:** Se hai più promozioni, nominarle chiaramente ti aiuta a gestirle.
-   **Contenuto modello:**

    -   **Cosa fa questa impostazione:** Questo è il cuore del tuo slider. Puoi inserire qualsiasi HTML, testo o persino codice Smarty qui. Questo contenuto verrà visualizzato all'interno del pannello scorrevole.
    -   **Effetto della modifica di questa impostazione:** Questo cambia direttamente ciò che i tuoi clienti vedono quando lo slider si espande. Puoi includere immagini, link, paragrafi, moduli, ecc.
    -   **Valore consigliato:** Usa HTML standard. Mantienilo conciso e visivamente accattivante. Per le immagini, usa URL assoluti o l'helper di immagini di PrestaShop.
    -   **Scenario / esempio per il commerciante:**

        ```
        <h3>Offerta a tempo limitato!</h3><p>Ottieni il <strong>15% DI SCONTO</strong> su tutti gli articoli della collezione estiva!</p><a href="{$link->getPageLink('category', true, null, ['id\_category' => 123])}" class="button btn btn-primary">Acquista ora!</a>
        ```

        (Nota: le variabili Smarty come `{$link->getPageLink(...)` richiedono che l'elaborazione Smarty sia abilitata per il contenuto, cosa che questo modulo supporta.)
-   **Posizione:**

    -   **Cosa fa questa impostazione:** Determina dove apparirà lo slider sullo schermo del cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Sinistra:* Lo slider appare dal bordo sinistro.
        -   *Destra:* Lo slider appare dal bordo destro.
        -   *In basso:* Lo slider appare dal bordo inferiore.
    -   **Valore consigliato:** Scegli in base al tuo design e ad altri elementi sulla tua pagina. Destra e Basso sono spesso meno intrusivi di Sinistra.
    -   **Scenario / esempio per il commerciante:** Usa "Destra" per un modulo di contatto rapido, "In basso" per un banner di consenso ai cookie o "Sinistra" per un codice sconto speciale.
-   **Apri su:**

    -   **Cosa fa questa impostazione:** Definisce come lo slider si espande per mostrare il suo contenuto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Click:* Lo slider si espande solo quando il cliente clicca sulla sua scheda di attivazione.
        -   *Hover:* Lo slider si espande quando il cliente sposta il cursore del mouse sulla sua scheda di attivazione.
    -   **Valore consigliato:** "Click" è generalmente meno intrusivo e previene aperture accidentali. "Hover" può essere utile per contenuti molto sottili e a rapida occhiata.
    -   **Scenario / esempio per il commerciante:** Per annunci o moduli importanti, "Click" è migliore. Per un pulsante di chat rapido "Ciao, come posso aiutarti?", "Hover" potrebbe funzionare.
-   **Attivo:**

    -   **Cosa fa questa impostazione:** Attiva/disattiva la visibilità e l'attività di questo specifico slider sul tuo front office.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato (Sì):* Lo slider apparirà nel tuo negozio in base alle sue impostazioni.
        -   *Disabilitato (No):* Lo slider sarà nascosto dal tuo negozio, ma la sua configurazione verrà salvata.
    -   **Valore consigliato:** "Sì" per slider attivi, "No" per slider che vuoi nascondere temporaneamente o su cui stai ancora lavorando.
    -   **Scenario / esempio per il commerciante:** Potresti disabilitare uno slider di promozione natalizia dopo le vacanze, quindi riabilitarlo l'anno successivo.

#### **Gestore pulsanti (buttonManager.tpl)**

Questa sezione fa parte di `SmartyTemplatesManager` e ti consente di gestire i pulsanti o i trigger per i tuoi slider. Sebbene il modulo utilizzi principalmente l'impostazione "Apri su", questa sezione potrebbe offrire personalizzazioni aggiuntive per il trigger visivo stesso.

-   **Cosa fa questa sezione:** Fornisce opzioni per personalizzare l'aspetto della scheda o del pulsante con cui i clienti interagiscono per aprire lo slider. Questo potrebbe includere testo, icone o stili di base.
-   **Effetto della modifica di questa sezione:** Modifica l'aspetto visivo del trigger dello slider sul front office.
-   **Valore consigliato:** Mantieni il trigger chiaro e invitante. Usa testo conciso o un'icona pertinente.
-   **Scenario / esempio per il commerciante:** Potresti impostare il testo del pulsante su "Saldi!", "Contattaci" o utilizzare una piccola icona di chat.

#### **Input di selezione (selectInput.tpl)**

Questo è un modello generico per le selezioni a discesa all'interno di `SmartyTemplatesManager`. Viene utilizzato per impostazioni come "Posizione" e "Apri su".

-   **Cosa fa questa sezione:** Presenta un elenco a discesa di opzioni predefinite per una particolare impostazione.
-   **Effetto della modifica di questa sezione:** Ti consente di scegliere tra un set limitato di opzioni per una data configurazione.
-   **Valore consigliato:** Seleziona l'opzione che meglio si adatta al comportamento desiderato dello slider.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Modulo principale | (Elenco di Slider) | N/A | Panoramica di tutti gli slider creati; consente di aggiungere/modificare. |
| Crea/Modifica modello | **Nome modello** | Nome descrittivo | Identificatore interno per lo slider nel back office. |
| Crea/Modifica modello | **Contenuto modello** | HTML/Testo personalizzato | Il contenuto effettivo visualizzato all'interno dello slider. |
| Crea/Modifica modello | **Posizione** | Destra / Basso | Dove lo slider appare sullo schermo (Sinistra, Destra, Basso). |
| Crea/Modifica modello | **Apri su** | Click | Come lo slider si espande (Click o Hover). |
| Crea/Modifica modello | **Attivo** | Sì | Attiva/disattiva la visibilità dello slider sul front office. |
| Gestore pulsanti | (Opzioni pulsante) | N/A | Personalizza il trigger visivo per lo slider (testo, icona, stile). |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Il mio slider non viene visualizzato nel front office. Cosa devo controllare?**
R:

1.  **Lo slider è "Attivo"?** Vai alla configurazione del modulo, modifica il tuo slider e assicurati che l'impostazione "Attivo" sia impostata su "Sì".
2.  **Il contenuto è valido?** Assicurati che non ci siano tag HTML non chiusi o errori JavaScript nel tuo "Contenuto modello" che potrebbero compromettere la visualizzazione.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel back office di PrestaShop e svuota la cache di Smarty (e opzionalmente l'intera cache).
4.  **Verifica la presenza di conflitti:** Disabilita temporaneamente altri moduli che potrebbero aggiungere elementi flottanti o modificare il layout della pagina per vedere se c'è un conflitto.

**D: Lo slider appare, ma lo stile sembra strano o non corrisponde al mio tema.**
R:

1.  **CSS predefinito del modulo:** Il modulo viene fornito con il proprio CSS. Il CSS del tuo tema potrebbe sovrascriverlo, o viceversa.
2.  **Stile del tema personalizzato:** Potrebbe essere necessario aggiungere regole CSS personalizzate al foglio di stile del tuo tema per regolare l'aspetto dello slider. Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare gli elementi dello slider e identificare le classi CSS da targetizzare.
3.  **Stile del contenuto:** Se stai inserendo HTML grezzo nel "Contenuto modello", assicurati di utilizzare classi appropriate o stili in linea che funzionino con il tuo tema.

**D: Posso avere più slider attivi contemporaneamente?**
R: Sì, il modulo supporta più slider. Tuttavia, fai attenzione all'esperienza utente. Avere troppi slider (ad esempio, uno a sinistra, uno a destra e uno in basso) può ingombrare l'interfaccia e sopraffare i clienti. Generalmente è meglio usarne uno o due strategicamente.

**D: Come aggiungo immagini o link al contenuto del mio slider?**
R: Puoi usare i tag HTML standard all'interno del campo "Contenuto modello":

-   **Immagini:** `<img src="your_image_url.jpg" alt="Descrizione" style="width:100px;">` (Usa URL assoluti per le immagini).
-   **Link:** `<a href="your_page_url.html">Clicca qui</a>` (Puoi anche usare variabili Smarty per i link di PrestaShop, ad esempio `<a href="{$link->getPageLink('contact')}">Contattaci</a>`).

**D: Funziona con multi-lingua e multi-negozio?**
R: Sì, il modulo è progettato per funzionare correttamente in ambienti multi-lingua e multi-negozio. Puoi creare slider diversi o contenuti diversi per lo stesso slider per ogni lingua e negozio, consentendo una messaggistica altamente mirata.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Slider contenuti personalizzati" (`saslider`) è costruito come un modulo PrestaShop standard, sfruttando principalmente la classe `Module` per il suo ciclo di vita e `SmartyTemplatesManager` per la creazione e la gestione dinamica dei contenuti. Si integra con il sistema di hook di PrestaShop per iniettare i suoi asset e contenuti nel front-office. La logica principale del modulo risiede nel suo file `index.php` principale, che gestisce la configurazione, l'installazione e il rendering del front-office. Non utilizza controller front-office o admin dedicati, ma si basa sul metodo `getContent()` per la configurazione del back-office e sulla registrazione diretta degli hook per la visualizzazione del front-office.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Tutto il rendering del front-office è gestito direttamente tramite hook registrati all'interno del file principale del modulo.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione del back-office è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce classi personalizzate che estendono `ObjectModel`. La sua archiviazione dati primaria per le configurazioni dello slider è probabilmente gestita tramite `Configuration::updateValue()` per le impostazioni a livello di modulo e potenzialmente dati serializzati archiviati in `ps_configuration` per il contenuto e le proprietà dei singoli slider, gestiti dalla libreria `SmartyTemplatesManager`.

### 4.4 Asset JavaScript (`views/js/`)

Il modulo include diversi file JavaScript, principalmente responsabili dell'animazione scorrevole e della logica di interazione (click/hover) per diverse posizioni dello slider.

-   `saslider/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`

    -   **Ambito**: Back-office.
    -   **Responsabilità**: Questo script fa parte della libreria `SmartyTemplatesManager`. Probabilmente gestisce la creazione dinamica, la modifica e la gestione dei modelli (slider) all'interno dell'interfaccia di configurazione del modulo. Potrebbe gestire l'invio di moduli, le chiamate AJAX per il salvataggio/caricamento dei contenuti e le interazioni dell'interfaccia utente per il sistema di gestione dei modelli.
-   `saslider/views/js/saslider-click-bottom.js`

    -   **Ambito**: Front-office.
    -   **Responsabilità**: Implementa la logica JavaScript per uno slider posizionato in basso che si espande/comprime su un evento click. Collegherà i listener di click all'elemento trigger dello slider, attiverà/disattiverà le classi CSS o manipolerà direttamente le proprietà `style` per animare l'espansione e la contrazione dello slider.
-   `saslider/views/js/saslider-click-left.js`

    -   **Ambito**: Front-office.
    -   **Responsabilità**: Simile a `saslider-click-bottom.js`, ma specificamente per uno slider posizionato a sinistra, gestendo la sua espansione/contrazione basata sul click.
-   `saslider/views/js/saslider-click-right.js`

    -   **Ambito**: Front-office.
    -   **Responsabilità**: Simile a `saslider-click-bottom.js`, ma specificamente per uno slider posizionato a destra, gestendo la sua espansione/contrazione basata sul click.
-   `saslider/views/js/saslider-hover-bottom.js`

    -   **Ambito**: Front-office.
    -   **Responsabilità**: Implementa la logica JavaScript per uno slider posizionato in basso che si espande/comprime su un evento hover. Collegherà i listener `mouseenter` e `mouseleave` all'elemento trigger dello slider, attivando/disattivando la sua visibilità e posizione.
-   `saslider/views/js/saslider-hover-left.js`

    -   **Ambito**: Front-office.
    -   **Responsabilità**: Simile a `saslider-hover-bottom.js`, ma specificamente per uno slider posizionato a sinistra, gestendo la sua espansione/contrazione basata sull'hover.
-   `saslider/views/js/saslider-hover-right.js`

    -   **Ambito**: Front-office.
    -   **Responsabilità**: Simile a `saslider-hover-bottom.js`, ma specificamente per uno slider posizionato a destra, gestendo la sua espansione/contrazione basata sull'hover.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include diversi file CSS sia per lo stile della configurazione del back-office che per l'aspetto dello slider nel front-office.

-   `saslider/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`

    -   **Ambito**: Stile del modulo admin del back-office.
    -   **Componenti UI principali**: Stila gli elementi dell'interfaccia `SmartyTemplatesManager`, inclusi moduli, pulsanti, campi di input e potenzialmente tabelle elenco per la gestione dei modelli.
    -   **Selettori di classe CSS chiave**: Probabilmente include classi per layout di moduli, gruppi di input e componenti UI amministrativi generali.
-   `saslider/views/css/saslider-bottom.css`

    -   **Ambito**: Stile del cliente del front-office.
    -   **Componenti UI principali**: Definisce il posizionamento specifico, lo stato iniziale (compresso) e le proprietà di animazione per lo slider posizionato in basso.
    -   **Selettori di classe CSS chiave**: `body #saslider_bottom`, `.saslider-bottom-tab`, `.saslider-bottom-content`, classi per gli stati `open`/`closed`.
-   `saslider/views/css/saslider-left.css`

    -   **Ambito**: Stile del cliente del front-office.
    -   **Componenti UI principali**: Definisce il posizionamento specifico, lo stato iniziale e le proprietà di animazione per lo slider posizionato a sinistra.
    -   **Selettori di classe CSS chiave**: `body #saslider_left`, `.saslider-left-tab`, `.saslider-left-content`, classi per gli stati `open`/`closed`.
-   `saslider/views/css/saslider-right.css`

    -   **Ambito**: Stile del cliente del front-office.
    -   **Componenti UI principali**: Definisce il posizionamento specifico, lo stato iniziale e le proprietà di animazione per lo slider posizionato a destra.
    -   **Selettori di classe CSS chiave**: `body #saslider_right`, `.saslider-right-tab`, `.saslider-right-content`, classi per gli stati `open`/`closed`.
-   `saslider/views/css/saslider.css`

    -   **Ambito**: Stile del cliente del front-office.
    -   **Componenti UI principali**: Contiene stili generali e comuni applicabili a tutte le posizioni dello slider, come stili di base del contenitore, dimensioni dei caratteri, colori, z-index e proprietà di transizione.
    -   **Selettori di classe CSS chiave**: `.saslider-container`, `.saslider-tab`, `.saslider-content` e potenzialmente aggiustamenti reattivi.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty sia per la sua interfaccia di configurazione del back-office che per il rendering dei contenuti del front-office.

-   **Template admin (`saslider/lib/smartyTemplatesManager/views/`)**:

    -   `buttonManager.tpl`: Probabilmente renderizza l'interfaccia utente per la gestione del pulsante/scheda di attivazione dello slider.
    -   `createTemplateForm.tpl`: Il template del modulo utilizzato per creare un nuovo slider.
    -   `editTemplateForm.tpl`: Il template del modulo utilizzato per modificare uno slider esistente.
    -   `mainForm.tpl`: Il template della pagina di configurazione principale, che probabilmente elenca tutti gli slider e fornisce il pulsante "Aggiungi nuovo".
    -   `selectInput.tpl`: Un template riutilizzabile per il rendering degli elementi `<select>` a discesa all'interno dei moduli admin.
-   **Template hook (`saslider/views/`)**:

    -   `footer-bottom.tpl`: Renderizza la struttura HTML per uno slider posizionato in basso. Questo template è probabilmente agganciato a `displayFooter` o a un hook globale simile. Contiene i `div` wrapper per lo slider, la sua scheda di attivazione e l'area del contenuto.
    -   `footer-left.tpl`: Renderizza la struttura HTML per uno slider posizionato a sinistra. Probabilmente agganciato a `displayFooter` o simile.
    -   `footer-right.tpl`: Renderizza la struttura HTML per uno slider posizionato a destra. Probabilmente agganciato a `displayFooter` o simile.
-   **Template di esempio/utilità (`saslider/lib/smartyTemplatesManager/tpl/`)**:

    -   `example.tpl`: Un template di esempio, possibilmente per dimostrazione o test interno di `SmartyTemplatesManager`.
    -   `MyShortCode.tpl`: Suggerisce che `SmartyTemplatesManager` potrebbe supportare una qualche forma di shortcode o inserimento dinamico di contenuti.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non definisce esplicitamente tabelle SQL personalizzate tramite `install.sql`.
    -   La configurazione per i singoli slider (contenuto, posizione, stato attivo, apertura) è memorizzata nella tabella `ps_configuration`, probabilmente come dati serializzati sotto chiavi di configurazione specifiche gestite dalla libreria `SmartyTemplatesManager`. Ad esempio, `PS_SASLIDER_TEMPLATES` o simili.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per registrare asset CSS e JavaScript (es. `saslider.css`, `saslider-click-right.js`) necessari per la visualizzazione e la funzionalità dello slider nel front-office. |
| `displayFooter` | Alla fine della sezione `<body>` di ogni pagina, prima del tag di chiusura `</body>`. | Utilizzato per renderizzare la struttura HTML effettiva dello slider (es. `footer-bottom.tpl`, `footer-left.tpl`, `footer-right.tpl`) nella pagina, assicurando che fluttui correttamente. |
| `displayLeftColumn` | Nella colonna sinistra del negozio. | *Potenzialmente* utilizzato per renderizzare lo slider, sebbene `displayFooter` sia più comune per gli elementi flottanti. |
| `displayRightColumn` | Nella colonna destra del negozio. | *Potenzialmente* utilizzato per renderizzare lo slider, sebbene `displayFooter` sia più comune per gli elementi flottanti. |
| `displayProductAdditionalInfo` | Nella pagina del prodotto, sotto le informazioni principali del prodotto. | *Potenzialmente* utilizzato per renderizzare uno slider specificamente nelle pagine dei prodotti, ad esempio per offerte correlate. |
| `actionFrontControllerSetMedia` | Dopo che un controller front-office ha impostato i suoi media, consentendo ai moduli di aggiungere i propri. | Utilizzato per aggiungere condizionalmente file CSS/JS in base alla pagina corrente o ad altre condizioni, garantendo un caricamento ottimale. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Slider contenuti personalizzati", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza tempestiva e a garantire che il tuo modulo funzioni senza problemi con il tuo negozio PrestaShop.
