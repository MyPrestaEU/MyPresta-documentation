---
title: "Fullscreen Banner Slider - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Fullscreen Banner Slider di MyPresta.eu."
sidebar:
  label: "Fullscreen Banner Slider - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Fullscreen Banner Slider su MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/fullscreen-banner-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/sliders-slideshows/fullscreen-banner-slider/)
>
> ---


# Fullscreen Banner Slider

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Fullscreen Banner Slider" nel tuo Gestione moduli. Questo ti porterà alla schermata di configurazione principale dove puoi gestire tutti gli aspetti del tuo slider.

La configurazione del modulo è gestita tramite il metodo `getContent()` nel file principale del modulo, presentando un modulo di configurazione standard di PrestaShop.

#### **Impostazioni generali**

- **Cosa fa questa impostazione:** Queste impostazioni controllano il comportamento generale e l'aspetto del tuo slider a schermo intero.
- **Effetto della modifica di questa impostazione:** La regolazione di questi valori avrà un impatto diretto su come lo slider viene visualizzato ai tuoi clienti, le sue dimensioni, la velocità e se è attivo.

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- |
| **Abilita Slider a schermo intero** | SÌ | **Scopo:** Attiva o disattiva l'intera funzionalità dello slider.   **Effetto:**   *Quando abilitato:* Lo slider a schermo intero apparirà ai nuovi visitatori.   *Quando disabilitato:* Lo slider non verrà visualizzato sul tuo negozio.   **Consigliato:** SÌ, per attivare la funzionalità. |
| **Larghezza Slider** | 100% | **Scopo:** Definisce la larghezza dello slider.   **Effetto:**   *Impostato su 100% (consigliato):* Lo slider si estenderà per l'intera larghezza della finestra del browser.   *Impostato su un valore fisso in pixel (es. 1200px):* Lo slider avrà una larghezza fissa, potenzialmente lasciando spazio vuoto su schermi molto ampi.   **Consigliato:** 100% per un'esperienza veramente a schermo intero. |
| **Altezza Slider** | 100% | **Scopo:** Definisce l'altezza dello slider.   **Effetto:**   *Impostato su 100% (consigliato):* Lo slider si estenderà per l'intera altezza della finestra del browser.   *Impostato su un valore fisso in pixel (es. 800px):* Lo slider avrà un'altezza fissa, potenzialmente lasciando spazio vuoto su schermi molto alti o corti.   **Consigliato:** 100% per un'esperienza veramente a schermo intero. |
| **Tipo di Animazione** | (Menu a discesa con varie opzioni) | **Scopo:** Seleziona l'effetto di transizione visiva tra i banner.   **Effetto:** Ogni opzione fornisce uno stile di animazione diverso (es. dissolvenza, scorrimento, cubo, ecc.). Sperimenta per trovarne uno che si adatti al tuo marchio.   **Consigliato:** Scegli un'animazione fluida e non troppo distraente. "Dissolvenza" o "Scorrimento" sono spesso buoni punti di partenza. |
| **Velocità Animazione (ms)** | 800 | **Scopo:** Controlla la velocità con cui avviene la transizione tra i banner, in millisecondi (1000ms = 1 secondo).   **Effetto:**   *Valore più alto (es. 1500):* Transizioni più lente e graduali.   *Valore più basso (es. 400):* Transizioni più veloci e scattanti.   **Consigliato:** 800-1000ms per un'atmosfera equilibrata e professionale. |
| **Intervallo tra le slide (ms)** | 3000 | **Scopo:** Imposta la durata di visualizzazione di ogni banner prima di passare al successivo, in millisecondi.   **Effetto:**   *Valore più alto (es. 5000):* I banner rimangono sullo schermo più a lungo, dando ai visitatori più tempo per leggere/visualizzare.   *Valore più basso (es. 2000):* I banner cambiano più rapidamente, creando un'atmosfera dinamica.   **Consigliato:** 3000-5000ms, a seconda della complessità del contenuto del tuo banner. |
| **Mostra Frecce di Navigazione** | SÌ | **Scopo:** Determina se le frecce "avanti" e "indietro" sono visibili per la navigazione manuale delle slide.   **Effetto:**   *Quando abilitato:* Le frecce appaiono ai lati dello slider, consentendo agli utenti di cliccare sui banner.   *Quando disabilitato:* I banner cambiano solo automaticamente in base all'intervallo.   **Consigliato:** SÌ, per un migliore controllo utente. |
| **Mostra Punti di Paginazione** | SÌ | **Scopo:** Determina se sono visibili piccoli punti (o miniature) che rappresentano ogni slide, solitamente nella parte inferiore dello slider.   **Effetto:**   *Quando abilitato:* Appaiono i punti, consentendo agli utenti di vedere quante slide ci sono e di saltare a una specifica.   *Quando disabilitato:* Nessun indicatore visivo del numero di slide o navigazione diretta.   **Consigliato:** SÌ, per un migliore orientamento e navigazione dell'utente. |
| **Riproduzione Automatica Slider** | SÌ | **Scopo:** Controlla se lo slider scorre automaticamente i banner.   **Effetto:**   *Quando abilitato:* I banner cambieranno automaticamente dopo l'intervallo impostato.   *Quando disabilitato:* I banner cambieranno solo se l'utente clicca sulle frecce di navigazione o sui punti di paginazione.   **Consigliato:** SÌ, per assicurarti che tutti i tuoi messaggi vengano visti. |
| **Testo Pulsante Chiudi** | Chiudi | **Scopo:** Ti permette di personalizzare il testo visualizzato sul pulsante che chiude lo slider a schermo intero.   **Effetto:** Cambia il testo sul pulsante.   **Consigliato:** "Chiudi", "Salta" o "Continua nel negozio". |
| **Scadenza Cookie (giorni)** | 7 | **Scopo:** Imposta per quanto tempo il modulo ricorda che un utente ha visto lo slider, impedendone la nuova visualizzazione.   **Effetto:**   *Impostato a 7 giorni:* Lo slider riapparirà per lo stesso utente dopo 7 giorni.   *Impostato a 0:* Lo slider apparirà ad ogni visita (non consigliato per l'esperienza utente).   *Impostato a un numero elevato (es. 365):* Lo slider apparirà solo una volta all'anno per i visitatori di ritorno.   **Consigliato:** 7 giorni è un buon equilibrio, permettendoti di coinvolgere nuovamente i visitatori di ritorno con nuove offerte periodicamente senza essere invadente. |

#### **Gestione Banner**

Questa sezione ti permette di aggiungere, modificare e rimuovere i singoli banner che verranno visualizzati nel tuo slider.

- **Cosa fa questa impostazione:** Ogni voce qui rappresenta un'immagine (banner) nel tuo slider. Puoi caricare l'immagine, collegarla a una pagina specifica e impostarne l'ordine di visualizzazione.
- **Effetto della modifica di questa impostazione:**
  - *Aggiungere un nuovo banner:* Introduce una nuova slide nella tua rotazione.
  - *Modificare un banner:* Aggiorna la sua immagine, il link o la posizione.
  - *Eliminare un banner:* Lo rimuove dallo slider.

Per ogni banner, troverai tipicamente campi come:

- **Immagine Banner:** Carica il file immagine per la tua slide. Assicurati che le immagini siano ad alta risoluzione e ottimizzate per il web per mantenere tempi di caricamento rapidi.
- **Link Banner (URL):** L'indirizzo web (URL) a cui i clienti verranno reindirizzati se cliccano su questo banner. Lascia vuoto se il banner è puramente informativo.
- **Ordine di Visualizzazione:** Un valore numerico che determina la sequenza dei banner. I banner con numeri inferiori appaiono per primi.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|
| Configurazione Modulo | Abilita Slider a schermo intero | SÌ | Attiva/disattiva l'intera funzionalità dello slider. |
| Configurazione Modulo | Larghezza Slider | 100% | Imposta la larghezza dello slider (es. 100% per larghezza intera). |
| Configurazione Modulo | Altezza Slider | 100% | Imposta l'altezza dello slider (es. 100% per altezza intera). |
| Configurazione Modulo | Tipo di Animazione | (Vari) | Sceglie l'effetto di transizione visiva tra le slide. |
| Configurazione Modulo | Velocità Animazione (ms) | 800 | Controlla la velocità delle transizioni delle slide. |
| Configurazione Modulo | Intervallo tra le slide (ms) | 3000 | Imposta per quanto tempo viene visualizzato ogni banner. |
| Configurazione Modulo | Mostra Frecce di Navigazione | SÌ | Mostra/nasconde le frecce per la navigazione manuale delle slide. |
| Configurazione Modulo | Mostra Punti di Paginazione | SÌ | Mostra/nasconde punti/miniature per l'accesso diretto alle slide. |
| Configurazione Modulo | Riproduzione Automatica Slider | SÌ | Abilita/disabilita la progressione automatica delle slide. |
| Configurazione Modulo | Testo Pulsante Chiudi | Chiudi | Personalizza il testo sul pulsante di chiusura dello slider. |
| Configurazione Modulo | Scadenza Cookie (giorni) | 7 | Determina per quanto tempo un utente non vedrà lo slider dopo averlo chiuso. |
| Configurazione Modulo | Immagine Banner | (Carica) | Carica l'immagine per una singola slide. |
| Configurazione Modulo | Link Banner (URL) | (Vuoto) | Imposta l'URL di destinazione quando si clicca su un banner. |
| Configurazione Modulo | Ordine di Visualizzazione | (Numero) | Definisce la sequenza in cui appaiono i banner. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Lo slider non appare nel mio negozio. Cosa devo fare?**
R:

1. **Verifica lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Fullscreen Banner Slider" sia installato e abilitato.
2. **Configurazione:** Verifica che "Abilita Slider a schermo intero" sia impostato su SÌ nella configurazione del modulo.
3. **Scadenza Cookie:** Se hai già visto lo slider, potrebbe essere dovuto al cookie. Prova a cancellare i cookie del tuo browser o ad aprire il tuo negozio in una finestra di navigazione in incognito/privata per simulare un visitatore per la prima volta.
4. **Cache:** Cancella la cache di PrestaShop in **Parametri Avanzati > Prestazioni**. Cancella anche la cache del tuo browser.
5. **Compatibilità del tema:** Sebbene il modulo sia progettato per essere compatibile, a volte i temi personalizzati possono interferire. Passa temporaneamente al tema predefinito di PrestaShop per vedere se lo slider appare. Se lo fa, il tuo tema potrebbe richiedere una piccola modifica (contatta lo sviluppatore del tuo tema o un webmaster).

**D: Le immagini del mio banner appaiono sfocate o allungate. Come posso risolvere questo problema?**
R: Questo di solito accade se le immagini caricate non sono ad alta risoluzione o hanno proporzioni errate per una visualizzazione a schermo intero.

1. **Qualità dell'immagine:** Utilizza sempre immagini ad alta risoluzione.
2. **Proporzioni:** Sebbene il modulo si ridimensioni, prova a utilizzare immagini larghe e relativamente corte, adatte per un banner a schermo intero (ad esempio, 1920x1080 pixel o formati larghi simili). Evita immagini molto alte o strette.
3. **Ottimizzazione:** Assicurati che le tue immagini siano ottimizzate per il web (compresse) per prevenire tempi di caricamento lenti, anche se sono ad alta risoluzione.

**D: Posso avere slider diversi per pagine diverse o gruppi di clienti?**
R: Questa specifica versione del modulo Fullscreen Banner Slider è progettata per una singola visualizzazione a schermo intero a livello di sito che appare una volta per sessione/cookie del visitatore. Non offre opzioni di targeting avanzate per pagine specifiche o gruppi di clienti. Se hai bisogno di tale funzionalità, potresti aver bisogno di un modulo di gestione banner più avanzato o di uno sviluppo personalizzato.

**D: Come posso tradurre il testo del pulsante "Chiudi" in altre lingue?**
R:

1. Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2. Seleziona "Traduzioni dei moduli installati" come Tipo di traduzione.
3. Scegli il tuo tema.
4. Seleziona la lingua che desideri tradurre.
5. Trova il modulo "Fullscreen Banner Slider" nell'elenco. Dovresti vedere il campo "Testo Pulsante Chiudi" lì per tradurre. Salva le modifiche.

**D: Lo slider appare, ma le animazioni non funzionano o il layout è sfasato.**
R:

1. **Conflitti JavaScript:** Questo è spesso dovuto a conflitti con il JavaScript di altri moduli o il JavaScript del tuo tema. Controlla la console per sviluppatori del tuo browser (tasto F12) per eventuali errori JavaScript.
2. **Conflitti CSS:** Similmente a JS, il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo.
3. **Reinstallazione del modulo:** A volte una reinstallazione pulita può risolvere problemi inaspettati. Disinstalla il modulo (senza eliminare i dati se richiesto), quindi reinstallalo.
   Se gli errori persistono, consulta un webmaster o contatta il supporto MyPresta.eu con i dettagli dalla console per sviluppatori del tuo browser.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Fullscreen Banner Slider (`fullscreenslider`) è un modulo PrestaShop standard implementato principalmente nel suo file PHP principale, `ajax_fullscreenslider.php`. Sfrutta la classe `Module` di PrestaShop per l'installazione, la disinstallazione e la configurazione (`getContent()`). La visualizzazione front-office è gestita agganciandosi a `displayHeader` e renderizzando un template Smarty. La funzionalità dello slider stesso si basa su plugin jQuery esterni (`jquery.skitter.js`, `jquery.easing.1.3.js`) per le animazioni e `noconflict.js` per garantire la compatibilità con jQuery. I valori di configurazione sono memorizzati in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il Front-Office o il Back-Office Admin. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate o istanze di `ObjectModel` nella directory `classes/`. Tutti i dati (immagini banner, link, ordine) sono gestiti direttamente tramite le impostazioni di configurazione del modulo, tipicamente serializzati e memorizzati in `ps_configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include diversi file JavaScript, principalmente per la funzionalità principale dello slider e le animazioni. Questi vengono tipicamente caricati nel front-office.

- `fullscreenslider/js/jquery.easing.1.3.js`
  - **Ambito:** Front-office.
  - **Responsabilità:** Fornisce funzioni di easing aggiuntive per le animazioni jQuery, consentendo effetti di transizione più diversi e fluidi oltre quelli predefiniti lineari o swing. Questa è una dipendenza per `jquery.skitter.js`.
- `fullscreenslider/js/jquery.skitter.js`
  - **Ambito:** Front-office.
  - **Responsabilità:** Questo è il plugin jQuery principale responsabile della funzionalità dello slider. Gestisce il caricamento delle immagini, le transizioni delle animazioni, la navigazione (frecce, paginazione), l'autoplay e il binding degli eventi per l'interazione dell'utente. Inizializza lo slider in base alle impostazioni di configurazione passate dal modulo.
- `fullscreenslider/js/noconflict.js`
  - **Ambito:** Front-office.
  - **Responsabilità:** Questo script è cruciale per garantire la compatibilità quando più librerie JavaScript (specialmente diverse versioni di jQuery) sono caricate sulla stessa pagina. Tipicamente avvolge il codice jQuery in un'espressione di funzione immediatamente invocata (IIFE) che passa `jQuery` come argomento, consentendogli di essere aliasato come `$` localmente senza entrare in conflitto con altre librerie che potrebbero anch'esse usare `$`.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include un file CSS principale per lo stile dello slider.

- `fullscreenslider/css/skitter.styles.css`
  - **Ambito:** Stile del cliente front-office.
  - **Responsabilità:** Contiene tutte le regole CSS necessarie per stilizzare lo slider a schermo intero, inclusi il suo contenitore, le frecce di navigazione, i punti di paginazione e gli effetti visivi del tipo di animazione scelto. Definisce l'aspetto e la sensazione predefiniti dello slider.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:**
    - `.box_skitter` (contenitore principale dello slider)
    - `.box_skitter ul` (elenco di slide)
    - `.box_skitter ul li` (singola slide)
    - `.box_skitter .info_slide` (didascalie/informazioni della slide, se utilizzate)
    - `.box_skitter .prev_button`, `.box_skitter .next_button` (frecce di navigazione)
    - `.box_skitter .info_slide_dots`, `.box_skitter .info_slide_thumb` (elementi di paginazione)
    - Classi specifiche per i tipi di animazione (es. `.cube`, `.fade`, ecc.)

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per renderizzare il suo contenuto front-office.

- **Template hook (`views/templates/hook/`)**:

  - `fullscreenslider/header.tpl`
    - **Hook:** `displayHeader` (o simile, a seconda dell'implementazione del metodo `hook` del modulo).
    - **Scopo:** Questo template è probabilmente responsabile dell'iniezione dei file CSS e JavaScript necessari nella sezione `<head>` dell'HTML, e potenzialmente della struttura HTML iniziale per il contenitore dello slider, che verrà poi popolato e animato dal JavaScript. Potrebbe anche contenere la logica per controllare il cookie che determina se lo slider deve essere mostrato.
  - `fullscreenslider/top.tpl`
    - **Hook:** Questo template è probabilmente renderizzato all'interno dell'hook `displayTop` o direttamente incluso da `header.tpl` per produrre la struttura HTML principale dello slider a schermo intero stesso.
    - **Scopo:** Contiene gli elementi `div` e la struttura `ul/li` che `jquery.skitter.js` si aspetta di trovare per inizializzare lo slider. Itera attraverso i banner configurati, producendo ogni immagine con il suo link associato. Include anche l'HTML per il pulsante di chiusura.
- **Template admin (`views/templates/admin/`)**: Questo modulo non sembra utilizzare template admin dedicati, poiché la configurazione è gestita direttamente all'interno di `getContent()`.
- **Template front-office (`views/templates/front/`)**: Questo modulo non sembra utilizzare template di pagina front-office autonomi dedicati.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione (inclusi i dati serializzati per i banner come percorsi immagine, link e ordine) sono memorizzate nella tabella `ps_configuration`. Le chiavi seguono tipicamente il modello `FULLSCREENSLIDER_SETTING_NAME`.
- **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS e JavaScript del modulo, e potenzialmente la struttura HTML iniziale per lo slider, insieme alla logica di controllo dei cookie. |
| `displayTop` (o simile) | Eseguito nella sezione superiore della pagina del front-office, spesso appena sotto l'header. | Renderizza la struttura HTML principale dello slider a schermo intero, incluse le immagini dei banner e gli elementi di navigazione. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Fullscreen Banner Slider, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
