---
title: "Hot Info - bottom sidebar - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Hot Info - bottom sidebar di MyPresta.eu."
sidebar:
  label: "Hot Info - bottom sidebar - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Hot Info - bottom sidebar su MyPresta.eu](https://mypresta.eu/modules/front-office-features/hot-info-bottom-sidebar.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/hot-info-bottom-sidebar/)
>
> ---


# Hot Info - bottom sidebar

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili in qualsiasi ambiente di hosting moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, clicca su "Configura" per accedere alle sue impostazioni. Qui definirai il contenuto e l'aspetto della tua barra laterale "Hot Info".

#### **Contenuto per il blocco Hot Info**

-   **Cosa fa questa impostazione:** Questa è l'area principale in cui inserirai il contenuto effettivo che i clienti vedranno nella barra laterale inferiore. È un editor di testo ricco (WYSIWYG - What You See Is What You Get), simile a quello che potresti usare per le descrizioni dei prodotti o gli articoli del blog.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando viene aggiunto contenuto:* Il testo, le immagini, i link o l'HTML che inserisci qui verranno visualizzati nel blocco "Hot Info" sul tuo storefront.
    *   *Quando lasciato vuoto:* Il blocco "Hot Info" potrebbe comunque apparire, ma sarà vuoto, oppure il modulo potrebbe non essere visualizzato affatto (a seconda di altre impostazioni e del comportamento del tema). È fondamentale aggiungere contenuto qui affinché il modulo sia utile.
-   **Valore consigliato:** Inserisci qui le tue "informazioni calde" desiderate. Usa un linguaggio chiaro e conciso e forti call to action.
-   **Scenario / esempio per il commerciante:** Potresti aggiungere "VENDITA LAMPO! Ottieni il 20% di sconto su tutti gli articoli estivi con il codice SUMMER20! [Acquista ora]" con un link alla tua collezione estiva. Oppure "Spedizione gratuita su tutti gli ordini superiori a $50!"

#### **Colore di sfondo**

-   **Cosa fa questa impostazione:** Controlla il colore di sfondo del blocco "Hot Info". Puoi selezionare un colore utilizzando uno strumento di selezione colori.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando impostato su un colore specifico (es. #FF0000 per il rosso):* Lo sfondo del blocco "Hot Info" verrà visualizzato in quel colore scelto.
    *   *Quando lasciato predefinito o trasparente:* Tipicamente erediterà il colore di sfondo dal tuo tema o sarà trasparente, il che potrebbe farlo confondere troppo o renderlo difficile da leggere.
-   **Valore consigliato:** Scegli un colore che si abbini al branding del tuo negozio o che risalti per attirare l'attenzione, a seconda del tuo obiettivo. Un colore contrastante può essere molto efficace.
-   **Scenario / esempio per il commerciante:** Se il tuo negozio usa molto blu, potresti scegliere un arancione o un giallo vibrante per far risaltare un annuncio di vendita.

#### **Colore del bordo**

-   **Cosa fa questa impostazione:** Controlla il colore del bordo attorno al blocco "Hot Info".
-   **Effetto della modifica di questa impostazione:**
    *   *Quando impostato su un colore specifico (es. #000000 per il nero):* Il bordo del blocco "Hot Info" verrà visualizzato in quel colore scelto.
    *   *Quando lasciato predefinito o trasparente:* Il blocco potrebbe apparire senza un bordo visibile, oppure potrebbe ereditare un colore del bordo dal tuo tema.
-   **Valore consigliato:** Spesso, un colore del bordo che corrisponde al colore del testo o una tonalità leggermente più scura del colore di sfondo funziona bene.
-   **Scenario / esempio per il commerciante:** Se il tuo sfondo è azzurro, un bordo blu più scuro può dargli un aspetto pulito e definito.

#### **Dimensione del bordo (in pixel)**

-   **Cosa fa questa impostazione:** Determina lo spessore del bordo attorno al blocco "Hot Info", misurato in pixel.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando impostato su un valore come '2':* Il blocco avrà un bordo spesso 2 pixel.
    *   *Quando impostato su '0':* Non verrà visualizzato alcun bordo.
-   **Valore consigliato:** Inizia con un valore piccolo come '1' o '2' per un bordo sottile. Aumentalo se desideri una cornice più pronunciata.
-   **Scenario / esempio per il commerciante:** Un bordo di 2px può incorniciare sottilmente il tuo messaggio, facendolo apparire come un elemento distinto sulla pagina.

#### **Altezza (in pixel)**

-   **Cosa fa questa impostazione:** Controlla l'altezza fissa del blocco "Hot Info", misurata in pixel.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando impostato su un valore come '50':* Il blocco sarà alto 50 pixel.
    *   *Quando il contenuto supera l'altezza:* Se il tuo contenuto è più alto dell'altezza specificata, apparirà una barra di scorrimento all'interno del blocco, consentendo ai clienti di scorrere il contenuto.
-   **Valore consigliato:** Mantieni questo valore relativamente piccolo (es. 40-60px) per evitare di occupare troppo spazio sullo schermo, specialmente su mobile. Regola in base alla quantità di contenuto che hai.
-   **Scenario / esempio per il commerciante:** Se hai un messaggio breve, su una singola riga, un'altezza di 40px potrebbe essere perfetta. Se hai alcune righe di testo, potresti aver bisogno di 60-80px.

#### **Lingua predefinita (PS\_LANG\_DEFAULT)**

-   **Cosa fa questa impostazione:** Questa è un'impostazione standard di PrestaShop che definisce la lingua predefinita per il tuo negozio. Sebbene non sia configurata direttamente da questo modulo, il campo contenuto del modulo mostrerà tipicamente il contenuto per la lingua attualmente selezionata nel back office, impostando questa come predefinita.
-   **Effetto della modifica di questa impostazione:** Questo influisce sulla lingua predefinita dell'intero negozio PrestaShop e su come viene gestito il contenuto multilingue. Per questo modulo, significa che il contenuto che inserisci sarà associato alla lingua che stai attualmente modificando nel back office.
-   **Valore consigliato:** Questo dovrebbe essere impostato sulla lingua principale del tuo negozio.
-   **Scenario / esempio per il commerciante:** Se il tuo mercato primario sono gli Stati Uniti, questo sarebbe impostato su Inglese. Quando inserisci il contenuto per il blocco "Hot Info", assicurati di modificare nella lingua corretta se il tuo negozio supporta più lingue.

#### **Aggiornamenti MyPresta.eu (mypresta\_updates, update\_, updatev\_)**

-   **Cosa fanno queste impostazioni:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per verificare e gestire gli aggiornamenti. Tipicamente memorizzano informazioni sulla versione del modulo e su quando ha controllato l'ultima volta gli aggiornamenti.
-   **Effetto della modifica di queste impostazioni:**
    *   *Quando abilitato/attivo:* Il modulo può comunicare con i server MyPresta.eu per notificarti nuove versioni o patch di sicurezza.
    *   *Quando disabilitato/inattivo:* Il modulo non controllerà automaticamente gli aggiornamenti.
-   **Valore consigliato:** Lascia queste impostazioni così come sono. Sono essenziali per mantenere il tuo modulo aggiornato e sicuro.
-   **Scenario / esempio per il commerciante:** Non interagisci tipicamente con queste direttamente. Assicurano che tu venga avvisato nel tuo back office PrestaShop quando una nuova versione del modulo è disponibile per il download dal tuo account MyPresta.eu.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Contenuto per il blocco Hot Info** | Il tuo messaggio personalizzato | Il testo, le immagini, i link effettivi visualizzati nella barra laterale inferiore. |
| Configurazione modulo | **Colore di sfondo** | Scegli per abbinare/contrastare il tema | Imposta il colore di sfondo del blocco informazioni. |
| Configurazione modulo | **Colore del bordo** | Scegli per abbinare/contrastare il tema | Imposta il colore del bordo attorno al blocco informazioni. |
| Configurazione modulo | **Dimensione del bordo (in pixel)** | 1 o 2 | Definisce lo spessore del bordo. Imposta a 0 per nessun bordo. |
| Configurazione modulo | **Altezza (in pixel)** | 40-60 | Imposta l'altezza fissa del blocco informazioni. Il contenuto che supera questa altezza scorrerà. |
| Configurazione modulo | **PS\_LANG\_DEFAULT** | Lingua principale del tuo negozio | Impostazione della lingua predefinita di PrestaShop, influisce sulla modifica del contenuto. |
| Configurazione modulo | **Aggiornamenti MyPresta.eu** | Abilitato | Impostazioni interne per i controlli degli aggiornamenti del modulo. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Il mio blocco "Hot Info" non viene visualizzato nel front office.**

-   **R:** Innanzitutto, assicurati che il modulo sia installato e abilitato in **Moduli > Gestione moduli**. In secondo luogo, verifica di aver effettivamente aggiunto contenuto nel campo "Contenuto per il blocco Hot Info" nella configurazione del modulo. Un blocco vuoto potrebbe non essere renderizzato. Infine, svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**) e la cache del tuo browser.

**D2: Il blocco "Hot Info" appare strano o non corrisponde allo stile del mio tema.**

-   **R:** Il modulo fornisce opzioni di stile di base (sfondo, colore/dimensione del bordo, altezza). Se continua a scontrarsi con il tuo tema, il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo.
    *   **Soluzione per i commercianti:** Prova a regolare i colori di sfondo e del bordo nelle impostazioni del modulo per vedere se riesci a trovare una corrispondenza migliore. In caso contrario, potresti aver bisogno di un webmaster per aggiungere CSS personalizzato al tuo tema per mirare e stilizzare specificamente il blocco del modulo.
    *   **Soluzione per i webmaster:** Ispeziona l'elemento negli strumenti di sviluppo del browser per identificare le regole CSS in conflitto e applica regole più specifiche o `!important` nel file CSS personalizzato del tuo tema.

**D3: Come posso aggiungere immagini o link al contenuto "Hot Info"?**

-   **R:** Utilizza l'editor di testo ricco fornito per l'impostazione "Contenuto per il blocco Hot Info". Ha pulsanti per inserire immagini, creare link, formattare il testo (grassetto, corsivo) e altro ancora, proprio come un normale elaboratore di testi. Clicca sull'icona "Immagine" per caricare e inserire un'immagine, oppure seleziona il testo e clicca sull'icona "Link" per aggiungere un collegamento ipertestuale.

**D4: Posso far apparire il blocco "Hot Info" solo su determinate pagine?**

-   **R:** Questo modulo, nella sua versione attuale, è progettato per apparire globalmente su tutte le pagine in cui viene eseguito l'hook `displayHeader`. Se hai bisogno di visibilità specifica per pagina, sarebbe necessario uno sviluppo personalizzato per modificare la logica di visualizzazione del modulo o utilizzare un modulo separato progettato per la visualizzazione condizionale del contenuto.

**D5: Il selettore colori non funziona o non viene visualizzato.**

-   **R:** Assicurati che JavaScript sia abilitato nel tuo browser. A volte, i conflitti con altri moduli o JavaScript del tema possono impedire il caricamento corretto del selettore colori. Prova a svuotare la cache e i cookie del tuo browser. Se il problema persiste, potrebbe indicare un conflitto JavaScript più complesso, che un webmaster dovrebbe indagare.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Hot Info - bottom sidebar" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo `hotinfo` è un modulo PrestaShop standard che segue il pattern MVC dove applicabile. Funziona principalmente come modulo di visualizzazione, iniettando contenuto nell'hook `displayHeader`. La configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo, memorizzando le impostazioni direttamente in `ps_configuration`. Sfrutta un editor di testo ricco (TinyMCE) per l'input del contenuto e un selettore colori JavaScript per le opzioni di stile.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office personalizzati. Tutta la configurazione è gestita all'interno del file principale del modulo `hotinfo.php` tramite il metodo `getContent()`.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate né estende `ObjectModel`. Tutti i dati (configurazione) sono memorizzati direttamente nella tabella `ps_configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`hotinfo/jscolor/jscolor.js`**
    *   **Ambito:** Back-office (pagina di configurazione del modulo).
    *   **Descrizione:** Questa è una libreria JavaScript di terze parti che fornisce un'interfaccia di selezione colori user-friendly. Viene tipicamente inizializzata su campi di input con una classe specifica (es. `jscolor`) per consentire agli amministratori di selezionare visivamente i colori per lo sfondo e il bordo del blocco "Hot Info". Si lega ai campi di input e aggiorna i loro valori in base alla selezione del colore dell'utente.
-   **`hotinfo/tinymce16.js`**
    *   **Ambito:** Back-office (pagina di configurazione del modulo).
    *   **Descrizione:** Questo script probabilmente inizializza e configura una versione dell'editor di testo ricco TinyMCE per l'area di testo "Contenuto per il blocco Hot Info". Trasforma un `<textarea>` HTML standard in un editor ricco di funzionalità, consentendo agli amministratori di formattare il testo, inserire immagini, creare link e gestire il contenuto HTML senza codifica diretta. Questo script si legherebbe all'elemento textarea pertinente e fornirebbe l'interfaccia dell'editor.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`hotinfo/css/hotinfo.css`**
    *   **Ambito:** Front-office (negozio rivolto al cliente).
    *   **Descrizione:** Questo foglio di stile contiene le regole CSS primarie per la barra laterale inferiore "Hot Info". Definisce il posizionamento fisso, le dimensioni, lo sfondo, il bordo e lo stile del testo per il blocco.
    *   **Selettori chiave (gli sviluppatori possono sovrascrivere):**
        *   `#hotinfo_block`: Il contenitore principale per l'intero blocco "Hot Info". Qui vengono applicati `position: fixed; bottom: 0; width: 100%;` e altri stili globali.
        *   `#hotinfo_block .hotinfo_content`: Il contenitore interno per il contenuto effettivo, dove `overflow-y: auto;` potrebbe essere applicato se il contenuto supera l'altezza definita.
        *   Stili per `p`, `a`, `img` all'interno di `#hotinfo_block` per garantire che il contenuto abbia un bell'aspetto.
    *   **Strategia di sovrascrittura:** Gli sviluppatori possono sovrascrivere questi stili aggiungendo regole CSS più specifiche nel file `custom.css` o `theme.css` del loro tema, o creando un tema figlio e modificando direttamente il CSS del modulo se necessario.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`hotinfo/hotinfo.tpl`**
    *   **Ambito:** Back-office (pagina di configurazione del modulo).
    *   **Descrizione:** Questo template viene utilizzato per renderizzare il modulo di configurazione all'interno del back office di PrestaShop quando si accede alla pagina di configurazione del modulo. Contiene la struttura HTML per l'editor di testo ricco, i selettori di colore e i campi di input per le impostazioni di altezza e bordo. Utilizza variabili Smarty per precompilare i campi del modulo con i valori di configurazione correnti.
-   **`hotinfo/views/templates/hook/hotinfo.tpl`**
    *   **Ambito:** Front-office (negozio rivolto al cliente).
    *   **Descrizione:** Questo template è responsabile del rendering del blocco "Hot Info" sul storefront. È agganciato a `displayHeader`. Recupera il contenuto configurato, il colore di sfondo, il colore del bordo, la dimensione del bordo e l'altezza dalle variabili Smarty passate dal modulo e le applica alla struttura HTML.
    *   **Elementi chiave:**
        *   Un `div` principale con un ID come `hotinfo_block` per il posizionamento fisso.
        *   Un `div` interno per il contenuto, potenzialmente con `overflow: auto;` per lo scorrimento.
        *   Il contenuto effettivo viene renderizzato utilizzando `{html_entity_decode($hotinfo_body)}` per visualizzare l'HTML dall'editor di testo ricco.
    *   **Hook:** `displayHeader` (sebbene visivamente appaia in basso, l'hook è nell'intestazione per garantire che si carichi presto).

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella standard di PrestaShop `ps_configuration`.

    -   Voci `PS_CONFIGURATION`:
        -   `HOTINFO_BODY`: Memorizza il contenuto HTML per il blocco "Hot Info" (multilingua).
        -   `HOTINFO_BG_COLOR`: Memorizza il valore esadecimale del colore di sfondo.
        -   `HOTINFO_BR_COLOR`: Memorizza il valore esadecimale del colore del bordo.
        -   `HOTINFO_BR_SIZE`: Memorizza il valore intero per lo spessore del bordo.
        -   `HOTINFO_HEIGHT`: Memorizza il valore intero per l'altezza del blocco.
        -   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Chiavi interne per il meccanismo di aggiornamento di MyPresta.eu.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Il modulo utilizza questo hook per iniettare i suoi file CSS e JavaScript e per renderizzare la struttura HTML principale del blocco "Hot Info". Sebbene il blocco sia posizionato visivamente in basso, renderizzarlo tramite `displayHeader` assicura che sia disponibile all'inizio del caricamento della pagina e possa essere stilizzato efficacemente con `position: fixed;`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Hot Info - bottom sidebar", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Puoi scaricare la versione più recente del modulo dalla cronologia degli ordini. Per qualsiasi assistenza tecnica o domanda, contatta direttamente il supporto di MyPresta.eu.
