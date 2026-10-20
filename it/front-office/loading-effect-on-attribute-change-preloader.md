---
title: "Effetto di caricamento al cambio di attributo - preloader - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Effetto di caricamento al cambio di attributo - preloader' di MyPresta.eu."
sidebar:
  label: "Effetto di caricamento al cambio di attributo - preloader - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Loading effect on attribute change - preloader su MyPresta.eu](https://mypresta.eu/modules/front-office-features/loading-effect-on-attribute-change-preloader.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/loading-effect-on-attribute-change-preloader/)
>
> ---


# Effetto di caricamento al cambio di attributo - preloader

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni. Questo modulo ha una pagina di configurazione semplice.

#### **Abilita / Disabilita Preloader**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'effetto di caricamento in tutto il tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* L'animazione di caricamento apparirà sulle pagine prodotto ogni volta che un cliente cambia gli attributi del prodotto.
    -   *Quando disabilitato (NO):* L'animazione di caricamento non apparirà e le tue pagine prodotto si comporteranno come prima dell'installazione del modulo (cioè, nessun feedback visivo durante i cambi di attributo).
-   **Valore consigliato:** SÌ
-   **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi attivarlo. Imposta questo su SÌ. Se hai bisogno di disabilitarlo temporaneamente per test o durante un importante aggiornamento del tema, puoi impostarlo su NO.

#### **Tipo di Preloader**

-   **Cosa fa questa impostazione:** Questa opzione ti permette di scegliere lo stile o il tipo di animazione di caricamento che verrà visualizzata. Il modulo tipicamente include una selezione di animazioni spinner predefinite.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "Spinner 1":* Verrà mostrato un tipo specifico di spinner animato (ad esempio, un semplice cerchio rotante).
    -   *Quando impostato su "Spinner 2":* Verrà mostrato un diverso spinner animato (ad esempio, un punto pulsante, una barra che svanisce).
    -   *Quando impostato su "Immagine personalizzata":* Se disponibile, questa opzione ti permetterebbe di caricare la tua GIF o immagine da usare come preloader. (Basandosi sulla descrizione del modulo, questo potrebbe essere un miglioramento futuro o un'opzione più avanzata non menzionata direttamente, ma è una caratteristica comune per le impostazioni di "tipo di preloader").
-   **Valore consigliato:** Sperimenta con le opzioni disponibili per vedere quale si adatta meglio al design e al branding del tuo negozio. Uno spinner semplice e pulito è spesso la scelta migliore.
-   **Scenario / esempio del commerciante:** Il tuo negozio ha un design minimalista, quindi potresti scegliere "Spinner 1" se è un'animazione pulita e discreta. Se il tuo brand è più giocoso, potresti scegliere uno "Spinner 2" più dinamico o persino caricare una GIF personalizzata con il tuo brand se l'opzione è disponibile.

#### **Colore del Preloader**

-   **Cosa fa questa impostazione:** Questo ti permette di definire il colore dell'animazione di caricamento. Questo è cruciale per abbinare il preloader alla combinazione di colori del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su `#007bff` (blu):* Lo spinner apparirà di colore blu.
    -   *Quando impostato su `#ff0000` (rosso):* Lo spinner apparirà di colore rosso.
-   **Valore consigliato:** Un colore che si abbina ai colori primari o d'accento del tuo negozio. Spesso, un grigio neutro, bianco o il colore principale delle azioni del tuo brand funziona bene.
-   **Scenario / esempio del commerciante:** I pulsanti principali di call-to-action del tuo negozio sono verdi. Impostare il colore del preloader su verde lo farà sentire come una parte integrata del design del tuo negozio, piuttosto che un elemento generico.

#### **Dimensione del Preloader (in pixel)**

-   **Cosa fa questa impostazione:** Controlla le dimensioni fisiche (larghezza e altezza) dell'animazione di caricamento.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su `32px`:* Lo spinner sarà piccolo e sottile.
    -   *Quando impostato su `64px`:* Lo spinner sarà più grande e più prominente.
-   **Valore consigliato:** Inizia con una dimensione moderata come `40px` o `48px`. Testa su desktop e mobile per assicurarti che sia visibile ma non eccessivamente intrusivo.
-   **Scenario / esempio del commerciante:** Su una pagina prodotto con immagini grandi, uno spinner da `32px` potrebbe perdersi. Aumentarlo a `48px` o `56px` lo renderebbe più evidente senza essere distraente. Al contrario, se le immagini del tuo prodotto sono piccole, uno spinner più piccolo potrebbe essere più appropriato.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita / Disabilita Preloader | SÌ | Attiva o disattiva l'animazione di caricamento al cambio degli attributi del prodotto. |
| Configurazione Modulo | Tipo di Preloader | (Scegli in base alle preferenze) | Seleziona lo stile visivo dell'indicatore di caricamento. |
| Configurazione Modulo | Colore del Preloader | (Abbina al tuo brand) | Imposta il colore dell'animazione di caricamento per integrarsi con il design del tuo negozio. |
| Configurazione Modulo | Dimensione del Preloader (in pixel) | 40px - 56px | Regola la dimensione fisica dell'indicatore per visibilità ed estetica. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato il modulo, ma non vedo alcun effetto di caricamento sulla mia pagina prodotto.**
R:

1.  **Svuota la cache:** La ragione più comune. Vai su **Parametri Avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
2.  **Posizione del modulo:** Assicurati che il modulo sia agganciato correttamente. Sebbene il modulo gestisca automaticamente questo aspetto, a volte i conflitti con il tema possono impedirlo. Il modulo tipicamente inietta il suo CSS/JS nell'hook `displayHeader`.
3.  **Override del tema:** Se stai utilizzando un tema fortemente personalizzato, potrebbe sovrascrivere il comportamento JavaScript predefinito di PrestaShop per i cambi di attributo, impedendo al modulo di rilevare l'evento. Contatta lo sviluppatore del tuo tema o un esperto PrestaShop.
4.  **Cache del browser:** Prova a svuotare la cache del tuo browser o a testare in una finestra di navigazione in incognito/privata.

**D: Il preloader appare, ma sembra fuori posto o non corrisponde al design del mio negozio.**
R:

1.  **Regola colore e dimensione:** Vai alla pagina di configurazione del modulo e sperimenta con le impostazioni "Colore del Preloader" e "Dimensione del Preloader". Prova ad abbinare i colori primari o d'accento del tuo brand.
2.  **Cambia tipo di preloader:** Se disponibile, prova diverse opzioni di "Tipo di Preloader" per trovarne una che si adatti meglio visivamente al tuo tema.
3.  **CSS personalizzato:** Per una personalizzazione avanzata, un webmaster può utilizzare CSS personalizzato per affinare il suo aspetto (vedi Guida per gli sviluppatori).

**D: Il preloader appare, ma rimane sullo schermo troppo a lungo, anche dopo che gli attributi del prodotto sono stati aggiornati.**
R: Questo di solito indica un conflitto JavaScript o un problema con il meccanismo di aggiornamento degli attributi del tuo tema. Il modulo si basa su eventi standard di PrestaShop per sapere quando nascondere il preloader.

1.  **Verifica errori JavaScript:** Apri la console per sviluppatori del tuo browser (F12) e cerca eventuali messaggi di errore rossi nella scheda "Console" quando cambi gli attributi.
2.  **Conflitti tra moduli:** Disabilita temporaneamente altri moduli del front-office che modificano il comportamento della pagina prodotto (ad esempio, moduli di visualizzazione rapida, moduli di attributi personalizzati) per vedere se uno di essi sta causando un conflitto.
3.  **Compatibilità del tema:** Assicurati che il tuo tema sia completamente compatibile con la tua versione di PrestaShop e non abbia JavaScript obsoleto.

**D: Questo modulo rallenta il mio sito web?**
R: No, il modulo stesso è molto leggero. Aggiunge una piccola quantità di CSS e JavaScript alla tua pagina. Il suo scopo è *gestire visivamente* la percezione del tempo di caricamento, non di causarlo. Se la tua pagina è lenta, il problema risiede altrove (ad esempio, immagini grandi, server non ottimizzato, altri moduli pesanti).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Effetto di caricamento al cambio di attributo - preloader" (`ppreloader`) è un modulo leggero, focalizzato sul front-office, progettato per migliorare l'esperienza utente durante gli aggiornamenti degli attributi del prodotto basati su AJAX. Sfrutta principalmente l'hook `displayHeader` di PrestaShop per iniettare il suo CSS e JavaScript, che poi ascolta specifici cambiamenti del DOM o eventi sulla pagina prodotto per attivare e nascondere l'animazione di caricamento. Non introduce nuove tabelle di database o logiche di backend complesse, concentrandosi esclusivamente sulla presentazione front-end.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza alcun controller personalizzato per il Front-Office o il Back-Office Admin. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non introduce classi personalizzate o definizioni di `ObjectModel`. Funziona interamente tramite il suo file principale del modulo e gli asset front-end.

### 4.4 Asset JavaScript (`views/js/`)

-   **`ppreloader/views/js/ppreloader.js`**
    -   **Ambito:** Front-office (Pagina Prodotto).
    -   **Responsabilità:** Questo script è il cuore della funzionalità del modulo.
        -   Attende che il DOM sia pronto.
        -   Ascolta i cambiamenti sui selettori degli attributi del prodotto (ad esempio, `select[name="group[X]"]`, pulsanti radio, selettori di colore, ecc., a seconda della struttura del tema).
        -   Probabilmente ascolta anche gli eventi AJAX relativi agli aggiornamenti delle combinazioni di prodotto (ad esempio, l'evento `updateProduct` o le chiamate `ajaxComplete` che mirano a URL specifici).
        -   Quando viene rilevato un cambio di attributo e viene avviata una chiamata AJAX, inserisce dinamicamente la struttura HTML del preloader (definita in `header.tpl` o generata al volo) in un contenitore rilevante sulla pagina prodotto (ad esempio, `$('#product_images')` o `$('#product-details')`).
        -   Applica il `Tipo di Preloader`, il `Colore del Preloader` e la `Dimensione del Preloader` scelti dalla configurazione del modulo.
        -   Una volta completata la chiamata AJAX e aggiornate le informazioni sul prodotto, rimuove l'HTML del preloader dal DOM.
        -   Garantisce la responsività mobile del preloader.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`ppreloader/views/css/ppreloader.css`**
    -   **Ambito:** Stile del cliente del front-office.
    -   **Responsabilità:** Questo foglio di stile definisce l'aspetto visivo e l'animazione del preloader di caricamento.
        -   Include stili per l'overlay che potrebbe coprire l'area del prodotto durante il caricamento.
        -   Definisce il CSS per vari tipi di preloader (spinner, punti, ecc.), incluse le loro keyframe di animazione.
        -   Assicura che il preloader sia centrato e posizionato correttamente all'interno del suo contenitore.
        -   Gestisce la responsività di base per diverse dimensioni dello schermo.
    -   **Selettori di classi CSS chiave che gli sviluppatori possono sovrascrivere:**
        -   `.ppreloader-overlay`: Il contenitore principale dell'overlay.
        -   `.ppreloader-spinner`: Il contenitore per l'animazione dello spinner vera e propria.
        -   Classi specifiche per diversi tipi di spinner (ad esempio, `.ppreloader-spinner-type1`, `.ppreloader-spinner-type2`).
        -   Regole `@keyframes` per le animazioni.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`ppreloader/views/header.tpl`**
    -   **Ambito:** Front-office.
    -   **Hook:** `displayHeader`
    -   **Responsabilità:** Questo template è principalmente responsabile dell'inclusione dei file CSS e JavaScript del modulo nella sezione `<head>` delle pagine del front-office.
        -   Utilizza `{$css_dir}ppreloader.css` per collegare il foglio di stile.
        -   Utilizza `{$js_dir}ppreloader.js` per collegare il file JavaScript.
        -   Probabilmente contiene anche JavaScript inline per passare le impostazioni di configurazione del modulo (stato abilitato, tipo, colore, dimensione) dal Back Office allo script `ppreloader.js`, rendendole disponibili per l'uso dinamico. Questo è cruciale affinché il JS sappia come renderizzare il preloader.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**: Questo modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi di configurazione standard di PrestaShop (ad esempio, `PPRELOADER_ENABLED`, `PPRELOADER_TYPE`, `PPRELOADER_COLOR`, `PPRELOADER_SIZE`).
-   **Tabella degli Hook Registrati**:

| Nome dell'Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS (`ppreloader.css`) e JavaScript (`ppreloader.js`) del modulo, oltre a passare le variabili di configurazione al JS. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Effetto di caricamento al cambio di attributo - preloader", accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
"""
