---
title: "Scroll to top - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Scroll to top di MyPresta.eu."
sidebar:
  label: "Scroll to top - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Scroll to top su MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-top.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/scroll-to-top/)
>
> ---


# Scroll to top

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, naviga su **Moduli > Gestione moduli** e clicca su "Configura" accanto a "Scroll to top". Questa pagina ti permette di personalizzare l'aspetto e il posizionamento del pulsante "scroll-to-top".

#### **Posizionamento Visivo**

-   **Cosa fa questa impostazione:** Questa è una rappresentazione visiva di dove apparirà il pulsante nel tuo negozio. Non è un'impostazione diretta ma piuttosto un aiuto visivo che cambia in base alle tue impostazioni "Posizione X" e "Posizione Y".
-   **Effetto del cambiamento di questa impostazione:** Man mano che regoli "Posizione X" e "Posizione Y", l'anteprima del pulsante su questa pagina di configurazione si sposterà, aiutandoti a visualizzare la sua posizione finale sul tuo front office.
-   **Valore consigliato:** Questo è dinamico.
-   **Scenario / esempio per il commerciante:** Se desideri che il pulsante sia più vicino in basso a destra, vedrai l'anteprima spostarsi lì mentre regoli i valori X e Y.

#### **Schema Colore**

-   **Cosa fa questa impostazione:** Controlla il colore di sfondo del pulsante "scroll-to-top".
-   **Effetto del cambiamento di questa impostazione:**
    -   *Quando impostato su un colore specifico (es. #007bff per il blu):* Il pulsante verrà visualizzato con quel colore di sfondo sul tuo front office.
    -   *Quando impostato su un colore diverso:* Lo sfondo del pulsante cambierà di conseguenza.
-   **Valore consigliato:** Scegli un colore che si abbini al branding del tuo negozio e sia chiaramente visibile sullo sfondo del tuo sito web, ma non troppo distraente.
-   **Scenario / esempio per il commerciante:** Se i colori del tuo brand sono blu e bianco, potresti impostarlo su una tonalità di blu per abbinarlo al tuo tema.

#### **Opacità**

-   **Cosa fa questa impostazione:** Determina quanto è trasparente o opaco il pulsante "scroll-to-top". Un'opacità inferiore lo rende più trasparente, permettendo al contenuto di sfondo di trasparire.
-   **Effetto del cambiamento di questa impostazione:**
    -   *Quando impostato su un valore alto (es. 1.0 o 100%):* Il pulsante sarà completamente opaco, senza trasparenza.
    -   *Quando impostato su un valore inferiore (es. 0.7 o 70%):* Il pulsante sarà semi-trasparente, fondendosi sottilmente con lo sfondo del tuo negozio.
-   **Valore consigliato:** Un valore tra 0.8 e 1.0 (80%-100%) è solitamente buono. Troppo basso, e potrebbe essere difficile da vedere; troppo alto, e potrebbe sembrare troppo prominente.
-   **Scenario / esempio per il commerciante:** Se desideri che il pulsante sia presente ma non eccessivamente dominante, impostare l'opacità a 0.8 potrebbe essere una buona scelta.

#### **Posizione X (da destra)**

-   **Cosa fa questa impostazione:** Controlla la posizione orizzontale del pulsante, in particolare la sua distanza dal bordo destro della finestra del browser.
-   **Effetto del cambiamento di questa impostazione:**
    -   *Aumentando il valore (es. da 20px a 50px):* Sposta il pulsante più a sinistra, lontano dal bordo destro.
    -   *Diminuendo il valore (es. da 50px a 20px):* Sposta il pulsante più vicino al bordo destro.
-   **Valore consigliato:** Inizia con un valore come `20px` o `30px` per mantenerlo comodamente lontano dal bordo senza essere troppo nell'area del contenuto.
-   **Scenario / esempio per il commerciante:** Se hai un widget di chat o un altro elemento fisso sul lato destro del tuo negozio, potresti aumentare questo valore a `60px` per evitare che il pulsante "scroll-to-top" lo sovrapponga.

#### **Posizione Y (dal basso)**

-   **Cosa fa questa impostazione:** Controlla la posizione verticale del pulsante, in particolare la sua distanza dal bordo inferiore della finestra del browser.
-   **Effetto del cambiamento di questa impostazione:**
    -   *Aumentando il valore (es. da 20px a 50px):* Sposta il pulsante più in alto, lontano dal bordo inferiore.
    -   *Diminuendo il valore (es. da 50px a 20px):* Sposta il pulsante più vicino al bordo inferiore.
-   **Valore consigliato:** Inizia con un valore come `20px` o `30px` per mantenerlo comodamente lontano dal bordo inferiore, sopra il footer.
-   **Scenario / esempio per il commerciante:** Se il tuo negozio ha un footer fisso o una barra di consenso ai cookie nella parte inferiore, potresti aumentare questo valore a `70px` per assicurarti che il pulsante "scroll-to-top" sia sempre visibile sopra questi elementi.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Posizionamento Visivo | Dinamico | Aiuto visivo per il posizionamento del pulsante basato sulle impostazioni X/Y. |
| Configurazione Modulo | Schema Colore | Varia (es. #007bff) | Imposta il colore di sfondo del pulsante "scroll-to-top". |
| Configurazione Modulo | Opacità | 0.8 - 1.0 | Controlla la trasparenza del pulsante (0.0 = completamente trasparente, 1.0 = completamente opaco). |
| Configurazione Modulo | Posizione X (da destra) | 20px - 30px | Definisce la distanza orizzontale del pulsante dal bordo destro dello schermo. |
| Configurazione Modulo | Posizione Y (dal basso) | 20px - 30px | Definisce la distanza verticale del pulsante dal bordo inferiore dello schermo. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Il pulsante "scroll-to-top" non appare nel mio negozio. Cosa devo fare?**
R:

1.  **Verifica lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Scroll to top" sia installato e abilitato.
2.  **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni**, scorri fino a "Svuota la cache" e clicca su "Svuota la cache". Quindi aggiorna il tuo front office.
3.  **Scorri verso il basso:** Ricorda, il pulsante appare solo quando scorri la pagina verso il basso. Assicurati di aver scorri sufficientemente per renderlo visibile.
4.  **Controlla le posizioni:** Assicurati che "Posizione X" e "Posizione Y" non siano impostate su valori estremamente alti che potrebbero spingere il pulsante fuori dallo schermo. Prova a impostarli a `20px` ciascuno come test.
5.  **Compatibilità del tema:** Sebbene raro, alcuni temi altamente personalizzati potrebbero avere conflitti CSS. Se i passaggi precedenti non funzionano, passa temporaneamente al tema PrestaShop predefinito (Classic) per vedere se il pulsante appare. Se lo fa, lo sviluppatore del tuo tema potrebbe dover assistere.

**D: Il pulsante è visibile ma non scorre verso l'alto quando cliccato.**
R:

1.  **Controlla JavaScript:** Questo di solito indica un conflitto o un errore JavaScript. Apri la console per sviluppatori del tuo browser (solitamente F12, quindi vai alla scheda "Console") e cerca eventuali messaggi di errore rossi.
2.  **Ordine dei moduli:** Assicurati che nessun altro modulo stia interferendo con la funzionalità JavaScript principale.
3.  **Reinstalla:** Prova a disinstallare e reinstallare il modulo. Questo a volte può risolvere file corrotti.

**D: Come posso cambiare l'icona del pulsante (es. da una freccia a qualcos'altro)?**
R: Il modulo utilizza un'icona a freccia standard. Cambiare questo richiede una modifica diretta dei file CSS o del template del modulo, il che rientra nella personalizzazione dello sviluppatore. Non è un'opzione disponibile nella configurazione del modulo.

**D: Il pulsante appare bene su desktop ma è troppo grande/piccolo/spostato su mobile.**
R:

1.  **Regola X e Y:** Usa le impostazioni "Posizione X" e "Posizione Y" per perfezionare il suo posizionamento specificamente per il mobile. Potresti aver bisogno di valori diversi per evitare conflitti con elementi UI specifici per il mobile.
2.  **Reattività del tema:** Il CSS del modulo è progettato per essere reattivo, ma la reattività complessiva del tuo tema può influenzare il suo aspetto. Testa su dispositivi reali o usa gli strumenti per sviluppatori del tuo browser per simulare diverse dimensioni dello schermo.
3.  **CSS personalizzato (attività dello sviluppatore):** Per modifiche avanzate di dimensionamento o stile specifiche per il mobile, un webmaster dovrebbe aggiungere regole CSS personalizzate al tuo tema, mirando al pulsante solo su schermi più piccoli.

**D: Questo modulo rallenterà il mio sito web?**
R: No, il modulo "Scroll to top" è molto leggero. Aggiunge CSS e JavaScript minimi, che vengono caricati in modo efficiente. Qualsiasi impatto sulle prestazioni sarebbe trascurabile.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori, webmaster e agenzie che desiderano comprendere, eseguire il debug o estendere il modulo "Scroll to top".

### 4.1 Panoramica dell'architettura

Il modulo "Scroll to top" è un modulo PrestaShop semplice, focalizzato principalmente sul miglioramento dell'interfaccia utente del front-office. Segue una classica struttura di modulo PrestaShop, sfruttando gli hook per iniettare i suoi asset HTML, CSS e JavaScript nel front office. Non introduce controller personalizzati o modelli di dati complessi, affidandosi invece al sistema di configurazione di PrestaShop per le sue impostazioni. La funzionalità principale è gestita lato client tramite JavaScript.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. La funzionalità front-office del modulo è interamente gestita iniettando asset e un template tramite hook.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

-   Nessuna classe personalizzata o definizione di `ObjectModel` è presente in questo modulo. Tutta la logica risiede nel file principale `scrolltop.php`.

### 4.4 Asset JavaScript (`views/js/`)

-   **`scrolltop/scrolltop.js`**
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo script gestisce la logica principale lato client per il pulsante "scroll-to-top".
    -   **Dettagli:**
        -   Attende che il DOM sia completamente caricato (`$(document).ready()`).
        -   Allega un listener di eventi all'evento `$(window).scroll()`.
        -   All'interno del gestore dell'evento scroll, controlla `$(this).scrollTop()`. Se la posizione di scorrimento è maggiore di una certa soglia (es. 100px), mostra il pulsante "scroll-to-top"; altrimenti, lo nasconde.
        -   Allega un listener di eventi click all'elemento del pulsante "scroll-to-top".
        -   Quando cliccato, utilizza `$('html, body').animate({scrollTop: 0}, 'slow');` per animare fluidamente lo scorrimento della pagina fino all'inizio.
        -   Impedisce il comportamento predefinito del link (`return false;`).
    -   **Dipendenze:** jQuery (che è tipicamente disponibile nel front office di PrestaShop).

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`scrolltop/scrolltop.css`**
    -   **Ambito:** Stile del cliente del front-office.
    -   **Responsabilità:** Definisce l'aspetto visivo e il posizionamento fisso del pulsante "scroll-to-top".
    -   **Dettagli:**
        -   Target l'elemento `#scroll-to-top`.
        -   Utilizza `position: fixed;` per mantenere il pulsante in una posizione statica rispetto alla viewport.
        -   Applica le proprietà `bottom` e `right`, impostate dinamicamente dalla configurazione del modulo, per controllare il suo posizionamento esatto.
        -   Definisce `z-index` per assicurare che il pulsante appaia sopra altri contenuti.
        -   Imposta `display: none;` inizialmente, poiché JavaScript controlla la sua visibilità.
        -   Stili per `background-color`, `border-radius`, `padding`, `width`, `height`, `line-height`, `text-align`, `color` (per l'icona a freccia), `font-size` e `cursor`.
        -   Include una proprietà `transition` per transizioni visive fluide (es. al passaggio del mouse o quando appare/scompare).
        -   Può includere aggiustamenti reattivi utilizzando media query per ottimizzare l'aspetto su diverse dimensioni dello schermo.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** `#scroll-to-top`, `#scroll-to-top i` (per l'icona).

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   **`scrolltop/footer.tpl`**
        -   **Hook:** `displayFooter` (o `displayHeader` per il caricamento degli asset).
        -   **Scopo:** Questo template renderizza la struttura HTML per il pulsante "scroll-to-top".
        -   **Contenuto:** Tipicamente contiene un tag `<a>` o `<div>` con un ID come `#scroll-to-top`, e un tag `<i>` (spesso utilizzando Font Awesome o un font icona simile) per l'icona a freccia.
        -   Include anche attributi di stile inline o attributi data per passare i valori configurati di `color`, `opacity`, `position X` e `position Y` dalle impostazioni del modulo al CSS o JavaScript del front-end per lo stile dinamico.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Le impostazioni di configurazione (`st_color`, `st_x`, `st_y`, `st_o`, `mypresta_updates`, `update_`, `updatev_`) sono memorizzate nella tabella `ps_configuration` di PrestaShop.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per registrare e caricare gli asset CSS (`scrolltop.css`) e JavaScript (`scrolltop.js`) del modulo. |
| `displayFooter` | Alla fine della sezione `<body>` di ogni pagina del front-office, appena prima del tag di chiusura `</body>`. | Utilizzato per renderizzare la struttura HTML del pulsante "scroll-to-top" (`footer.tpl`). Questo assicura che l'HTML del pulsante sia presente nel DOM per la manipolazione da parte di JavaScript. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "Scroll to top", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
