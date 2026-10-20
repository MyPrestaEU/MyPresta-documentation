---
title: "Responsive Facebook Like Box - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Responsive Facebook Like Box di MyPresta.eu."
sidebar:
  label: "Responsive Facebook Like Box - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Responsive Facebook Like Box su MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-facebook-like-box.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/responsive-facebook-like-box/)
>
> ---


# Responsive Facebook Like Box

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su qualsiasi ambiente di hosting moderno. Nessun requisito di hosting speciale oltre a una configurazione PrestaShop standard.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il tuo modulo "Responsive Facebook Like Box". Qui definirai l'aspetto e il comportamento della tua Facebook Like Box sul tuo negozio.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Responsive Facebook Like Box" > Fai clic su "Configura".

#### Impostazioni e Opzioni:

1.  **URL della Fanpage di Facebook:**

    -   **Cosa fa questa impostazione:** Questa è l'impostazione più critica. Indica al modulo quale specifica pagina Facebook visualizzare nella Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato sull'URL della tua pagina Facebook (es. `https://www.facebook.com/MyPresta.eu`):* Il modulo visualizzerà la Like Box per quella specifica pagina.
        -   *Quando lasciato vuoto o impostato su un URL non valido:* La Like Box non verrà visualizzata correttamente o affatto.
    -   **Valore consigliato:** L'URL ufficiale della tua Fanpage di Facebook.
    -   **Scenario / esempio del commerciante:** Se la pagina Facebook del tuo negozio è `https://www.facebook.com/MyAwesomeStore`, inseriresti quell'URL qui.
2.  **Larghezza della Like Box (in pixel):**

    -   **Cosa fa questa impostazione:** Controlla la dimensione orizzontale della Facebook Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un valore in pixel specifico (es. `340`):* La Like Box tenterà di essere renderizzata a quella larghezza esatta.
        -   *Quando impostato su un valore più piccolo:* La casella sarà più stretta, potenzialmente nascondendo parte del contenuto o rendendo il testo più piccolo.
        -   *Quando impostato su un valore più grande:* La casella sarà più larga, occupando più spazio orizzontale.
    -   **Valore consigliato:** `340` (Questo è un valore predefinito comune per il Page Plugin di Facebook e spesso funziona bene nelle colonne laterali). Per sezioni a larghezza intera, potresti usare un valore più grande o lasciarlo regolare automaticamente se il tema lo consente.
    -   **Scenario / esempio del commerciante:** Se la tua colonna destra è larga 300px, impostando questo valore a 280-300px ti assicureresti che si adatti perfettamente senza overflow.
3.  **Altezza della Like Box (in pixel):**

    -   **Cosa fa questa impostazione:** Controlla la dimensione verticale della Facebook Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un valore in pixel specifico (es. `500`):* La Like Box verrà renderizzata a quella altezza esatta.
        -   *Quando impostato su un valore più piccolo:* La casella sarà più corta, richiedendo potenzialmente lo scorrimento per vedere tutto il contenuto (come post recenti o volti di amici).
        -   *Quando impostato su un valore più grande:* La casella sarà più alta, occupando più spazio verticale.
    -   **Valore consigliato:** `500` (Un buon equilibrio per mostrare alcuni contenuti senza essere eccessivamente lunga). Regola in base a quanto contenuto desideri visualizzare (es. più post = più altezza).
    -   **Scenario / esempio del commerciante:** Se vuoi mostrare 3-4 post recenti dalla tua pagina Facebook, potresti aver bisogno di un'altezza di 500px o più. Se vuoi mostrare solo il pulsante "Mi piace" e la foto di copertina, un'altezza minore come 200px potrebbe essere sufficiente.
4.  **Mostra volti degli amici:**

    -   **Cosa fa questa impostazione:** Determina se la Like Box visualizza le immagini del profilo delle persone a cui piace la tua pagina e che sono anche amici del visualizzatore corrente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* La Like Box mostrerà i volti, aggiungendo un elemento di prova sociale, poiché i visitatori vedono i loro amici connessi al tuo brand.
        -   *Quando disabilitato (NO):* I volti non verranno visualizzati, risultando in un aspetto più pulito e compatto.
    -   **Valore consigliato:** SÌ (Sfrutta la prova sociale per incoraggiare più mi piace).
    -   **Scenario / esempio del commerciante:** L'abilitazione di questa opzione può aumentare la fiducia e l'engagement, poiché gli acquirenti sono più propensi a seguire un brand che piace già ai loro amici.
5.  **Mostra Stream (Post dalla tua Pagina):**

    -   **Cosa fa questa impostazione:** Controlla se i post recenti dalla tua pagina Facebook vengono visualizzati all'interno della Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* I tuoi ultimi post di Facebook appariranno nella casella, fornendo contenuti freschi e incoraggiando l'interazione.
        -   *Quando disabilitato (NO):* Saranno visibili solo la foto di copertina, il nome della pagina e il pulsante "Mi piace", rendendo la casella più compatta.
    -   **Valore consigliato:** SÌ (Mantiene il contenuto fresco e mostra ai visitatori che tipo di contenuto possono aspettarsi se ti seguono).
    -   **Scenario / esempio del commerciante:** Se pubblichi regolarmente aggiornamenti, promozioni o contenuti interessanti su Facebook, mostrare lo stream mantiene i visitatori del tuo sito web coinvolti con la tua attività sui social media.
6.  **Mostra Intestazione:**

    -   **Cosa fa questa impostazione:** Determina se una piccola intestazione "Facebook" viene visualizzata nella parte superiore della Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Apparirà una piccola intestazione con il logo e il testo di Facebook.
        -   *Quando disabilitato (NO):* L'intestazione verrà rimossa, dando un aspetto leggermente più integrato, ma potenzialmente meno chiaro che si tratti di un widget di Facebook.
    -   **Valore consigliato:** SÌ (Fornisce un branding e un contesto chiari).
    -   **Scenario / esempio del commerciante:** Mantenere l'intestazione aiuta gli utenti a riconoscerla immediatamente come un widget di Facebook.
7.  **Usa Intestazione Piccola:**

    -   **Cosa fa questa impostazione:** Se "Mostra Intestazione" è abilitato, questa opzione controlla se viene utilizzata una versione più piccola dell'intestazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* L'intestazione sarà più compatta.
        -   *Quando disabilitato (NO):* Verrà utilizzata l'intestazione di dimensioni standard.
    -   **Valore consigliato:** SÌ (Spesso ha un aspetto migliore nelle colonne laterali o in spazi più piccoli).
    -   **Scenario / esempio del commerciante:** Utile se stai posizionando la Like Box in una colonna stretta dove lo spazio è limitato.
8.  **Adatta alla Larghezza del Contenitore:**

    -   **Cosa fa questa impostazione:** Questa è un'impostazione cruciale per la reattività. Indica alla Facebook Like Box di regolare automaticamente la sua larghezza per adattarsi alla larghezza del contenitore in cui è posizionata (es. la colonna del tuo tema).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* La Like Box si ridimensionerà dinamicamente, rendendola veramente reattiva e prevenendo problemi di overflow su diverse dimensioni dello schermo. L'impostazione "Larghezza della Like Box" potrebbe essere sovrascritta o utilizzata come massimo.
        -   *Quando disabilitato (NO):* La Like Box cercherà di mantenere l'impostazione "Larghezza della Like Box", portando potenzialmente a problemi di layout su schermi più piccoli se la larghezza impostata è troppo grande.
    -   **Valore consigliato:** SÌ (Essenziale per un design reattivo e una buona esperienza utente su mobile).
    -   **Scenario / esempio del commerciante:** Se posizioni la Like Box in una barra laterale reattiva, abilitando questa opzione ti assicuri che si adatti sempre perfettamente, indipendentemente dal dispositivo utilizzato dal tuo cliente.
9.  **Colore di Sfondo (Codice Esadecimale):**

    -   **Cosa fa questa impostazione:** Ti consente di impostare un colore di sfondo personalizzato per la Like Box utilizzando un codice colore esadecimale (es. `#FFFFFF` per il bianco).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un codice esadecimale specifico:* Lo sfondo della Like Box cambierà in quel colore.
        -   *Quando lasciato vuoto o impostato su un codice non valido:* Verrà utilizzato il colore di sfondo predefinito di Facebook (solitamente grigio chiaro o bianco).
    -   **Valore consigliato:** Abbina il colore di sfondo del tuo tema o lascia vuoto per il valore predefinito.
    -   **Scenario / esempio del commerciante:** Se il tuo negozio ha un tema scuro, potresti impostarlo su un grigio scuro per integrarsi meglio.
10. **Hook di Posizionamento:**

    -   **Cosa fa questa impostazione:** Determina dove sul tuo negozio PrestaShop verrà visualizzata la Facebook Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su `displayHeader`:* La Like Box apparirà nella sezione dell'header del tuo negozio.
        -   *Quando impostato su `displayLeftColumn` o `displayRightColumn`:* La Like Box apparirà nella rispettiva barra laterale.
        -   *Quando impostato su `displayFooter`:* La Like Box apparirà nella sezione del footer.
        -   *Quando impostato su `displayProductButtons` o un hook simile della pagina prodotto:* La Like Box apparirà sulle pagine prodotto.
    -   **Valore consigliato:** `displayRightColumn` o `displayLeftColumn` (Comune ed efficace per la visibilità senza essere intrusivo).
    -   **Scenario / esempio del commerciante:** Se vuoi che la Like Box sia visibile sulla maggior parte delle pagine senza occupare lo spazio principale dell'header, posizionarla in una colonna è una buona scelta. Se vuoi che sia molto prominente, l'header potrebbe essere preferito.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | URL Fanpage Facebook | URL della tua Pagina Facebook | Collega il modulo alla tua specifica pagina Facebook. |
| Configurazione Modulo | Larghezza della Like Box (px) | 340 | Imposta la dimensione orizzontale. |
| Configurazione Modulo | Altezza della Like Box (px) | 500 | Imposta la dimensione verticale. |
| Configurazione Modulo | Mostra Volti degli Amici | SÌ | Visualizza le immagini del profilo degli amici per la prova sociale. |
| Configurazione Modulo | Mostra Stream (Post) | SÌ | Visualizza i post recenti dalla tua pagina Facebook. |
| Configurazione Modulo | Mostra Intestazione | SÌ | Visualizza l'intestazione "Facebook". |
| Configurazione Modulo | Usa Intestazione Piccola | SÌ | Utilizza un'intestazione compatta se "Mostra Intestazione" è abilitato. |
| Configurazione Modulo | Adatta alla Larghezza del Contenitore | SÌ | Rende la Like Box reattiva al suo contenitore genitore. |
| Configurazione Modulo | Colore di Sfondo (Hex) | (Lascia vuoto per predefinito) | Personalizza il colore di sfondo della casella. |
| Configurazione Modulo | Hook di Posizionamento | displayRightColumn / displayLeftColumn | Determina dove appare la casella nel tuo negozio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La Facebook Like Box non appare nel mio negozio. Cosa devo fare?**

-   **R:** Innanzitutto, ricontrolla di aver inserito l'**"URL della Fanpage di Facebook"** corretto e completo nella configurazione del modulo. Assicurati che inizi con `https://`.
-   **R:** Verifica che l'**"Hook di Posizionamento"** selezionato sia effettivamente attivo e visualizzato dal tuo tema. Alcuni temi potrebbero non visualizzare determinati hook (es. colonna sinistra) su tutte le pagine. Prova a passare a un hook diverso come `displayFooter` per vedere se appare lì.
-   **R:** Svuota la cache di PrestaShop. Vai su **Parametri Avanzati > Prestazioni** e fai clic su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Svuota anche la cache del tuo browser.
-   **R:** Assicurati che il modulo sia abilitato. In **Moduli > Gestione moduli**, cerca il modulo e conferma che non sia disabilitato.

**D2: La Like Box appare troppo larga/stretta o troppo alta/bassa.**

-   **R:** Regola le impostazioni **"Larghezza della Like Box"** e **"Altezza della Like Box"** nella configurazione del modulo.
-   **R:** Se vuoi che si adatti automaticamente alla colonna del tuo tema, assicurati che **"Adatta alla Larghezza del Contenitore"** sia impostato su SÌ. Questo è particolarmente importante per i temi reattivi.

**D3: Perché i post recenti o i volti degli amici non vengono visualizzati nella Like Box?**

-   **R:** Controlla le impostazioni di configurazione del modulo:
    -   Assicurati che **"Mostra Stream (Post dalla tua Pagina)"** sia impostato su SÌ per visualizzare i post.
    -   Assicurati che **"Mostra Volti degli Amici"** sia impostato su SÌ per visualizzare i volti degli amici.
-   **R:** L'API di Facebook a volte presenta limitazioni o ritardi. Assicurati che la tua pagina Facebook abbia post pubblici recenti.

**D4: Il colore di sfondo che ho impostato non appare.**

-   **R:** Assicurati di aver inserito un codice colore esadecimale valido (es. `#RRGGBB`). Se stai utilizzando un tema personalizzato, potrebbero esserci stili CSS in conflitto. Potrebbe essere necessario un web developer per ispezionare l'elemento e applicare una regola CSS più specifica se l'impostazione del modulo viene sovrascritta.

**D5: Il modulo funziona su desktop ma appare strano su mobile.**

-   **R:** Questo è quasi sempre dovuto all'impostazione **"Adatta alla Larghezza del Contenitore"**. Assicurati che sia impostata su SÌ. Questo indica al widget di Facebook di essere reattivo. Inoltre, controlla la reattività del tuo tema; se il contenitore in cui si trova il modulo non è reattivo, il modulo non può adattarsi perfettamente.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Responsive Facebook Like Box" per sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura

Il modulo `Responsive Facebook Like Box` (`likebox/ar.php`) è un modulo PrestaShop standard che segue il pattern MVC, ove applicabile, per la sua configurazione. Sfrutta principalmente il sistema di hook di PrestaShop per iniettare il Facebook Page Plugin (Like Box) in varie posizioni del front-office. La funzionalità principale si basa sull'SDK JavaScript del Facebook Page Plugin, che viene caricato e configurato dinamicamente in base alle impostazioni del modulo. La configurazione è gestita tramite `Configuration::get()` e `Configuration::updateValue()` all'interno della classe principale del modulo.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office Admin personalizzati. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi Core e Modelli (`classes/`)

Questo modulo non definisce classi personalizzate né estende `ObjectModel`. Tutta la logica è incapsulata nel file principale del modulo `ar.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**

    -   **Ambito:** Back-office (Pagina di configurazione Admin).
    -   **Scopo:** Questa è una libreria JavaScript di terze parti per un selettore di colori. Viene utilizzata nella pagina di configurazione del modulo per fornire un'interfaccia user-friendly per la selezione dell'impostazione "Colore di Sfondo".
    -   **Funzionalità:** Trasforma un campo di input di testo standard in un selettore di colori interattivo, consentendo all'amministratore di selezionare visivamente un codice colore esadecimale.
-   **`likebox/script.js`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo script è responsabile del caricamento dinamico dell'SDK JavaScript di Facebook e dell'inizializzazione del Facebook Page Plugin (Like Box) nel front-office.
    -   **Funzionalità:**
        -   Tipicamente controlla l'esistenza dell'SDK di Facebook (`FB`) e lo carica se non è già presente.
        -   Quindi chiama `FB.XFBML.parse()` o metodi simili per renderizzare l'elemento `div` con la classe `fb-page`, applicando gli attributi (data-href, data-width, ecc.) in base alla configurazione del modulo.
        -   Assicura che la Like Box sia renderizzata correttamente dopo che il DOM è pronto.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   **`likebox/css/css.css`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Contiene regole di stile generali per il contenitore della Facebook Like Box e potenzialmente alcune regolazioni reattive.
    -   **Selettori chiave:** Probabilmente si rivolge al `div` del contenitore principale che avvolge il Facebook Page Plugin, assicurando che si adatti al layout del tema e gestisca la reattività di base. Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` o `theme.css` del loro tema, se necessario.
-   **`likebox/css.css`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Simile a `likebox/css/css.css`, questo file probabilmente contiene regole di stile aggiuntive o alternative per la visualizzazione front-office della Like Box. Potrebbe includere regole per posizionamenti specifici o piccole modifiche visive.
    -   **Selettori chiave:** Si rivolge al contenitore della Facebook Like Box e agli elementi correlati.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **`likebox/header.tpl`**

    -   **Ambito:** Front-office.
    -   **Hook:** `displayHeader` (o hook simile relativo all'header).
    -   **Scopo:** Questo template è responsabile dell'output della struttura HTML per la Facebook Like Box quando il modulo è configurato per essere visualizzato nell'header. Contiene l'elemento `div` con la classe `fb-page` e gli attributi `data-*` che l'SDK di Facebook utilizza per renderizzare il plugin.
    -   **Variabili:** Accede a variabili di configurazione (es. `{$facebook_page_url}`, `{$width}`, `{$height}`, `{$show_faces}`, ecc.) passate dalla logica PHP del modulo.
-   **`likebox/rightcolumn.tpl`**

    -   **Ambito:** Front-office.
    -   **Hook:** `displayRightColumn` (o `displayLeftColumn`, `displayFooter`, `displayProductButtons`, ecc., a seconda dell'hook scelto).
    -   **Scopo:** Questo template è responsabile dell'output della struttura HTML per la Facebook Like Box quando il modulo è configurato per essere visualizzato in una colonna o in altre aree di contenuto. Contiene l'elemento `div` con la classe `fb-page` e gli attributi `data-*`.
    -   **Variabili:** Simile a `header.tpl`, accede a variabili di configurazione per impostare dinamicamente gli attributi del plugin.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` (o prefisso `_configuration`) utilizzando chiavi come `RESPONSIVE_FB_LIKEBOX_URL`, `RESPONSIVE_FB_LIKEBOX_WIDTH`, ecc.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` della pagina, o all'inizio del `<body>`. | Inietta l'HTML della Facebook Like Box e potenzialmente lo script di inizializzazione dell'SDK di Facebook. |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra del negozio. | Inietta l'HTML della Facebook Like Box nella colonna sinistra. |
| `displayRightColumn` | Renderizza il contenuto nella barra laterale destra del negozio. | Inietta l'HTML della Facebook Like Box nella colonna destra. |
| `displayFooter` | Renderizza il contenuto nella sezione del footer del negozio. | Inietta l'HTML della Facebook Like Box nel footer. |
| `displayProductButtons` (o hook simile della pagina prodotto) | Renderizza il contenuto nella pagina prodotto, spesso vicino al pulsante "aggiungi al carrello" o alla descrizione. | Inietta l'HTML della Facebook Like Box nelle pagine prodotto. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-office sta impostando i suoi media (JS/CSS). | Registra i file CSS e JavaScript del modulo per la visualizzazione front-office. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin sta impostando i suoi media (JS/CSS). | Registra lo script `jscolor.js` e potenzialmente CSS specifici per l'amministrazione per la pagina di configurazione del modulo. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, nuove versioni e supporto ufficiale per il modulo "Responsive Facebook Like Box", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi domanda o problema tu possa incontrare.
