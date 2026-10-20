---
title: "hreflang e URL canonici gratuiti - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop hreflang e URL canonici gratuiti di MyPresta.eu."
sidebar:
  label: "hreflang e URL canonici gratuiti - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Free hreflang & canonical urls su MyPresta.eu](https://mypresta.eu/modules/seo/free-hreflang-canonical-urls.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/seo/free-hreflang-canonical-urls/)
>
> ---


# hreflang e URL canonici gratuiti

## 1. Requisiti e compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito preinstallate nella maggior parte degli ambienti di hosting. Non sono richieste configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, naviga su **Moduli > Gestione moduli**, cerca "hreflang e URL canonici gratuiti" e clicca su "Configura". Ti verrà presentata la schermata di configurazione principale del modulo.

#### **Opzioni di configurazione:**

-   **Abilita tag hreflang:**

    -   **Cosa fa questa impostazione:** Questo interruttore principale controlla se il modulo genererà e aggiungerà i tag `hreflang` all'intestazione HTML del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo genererà e inserirà attivamente i tag `hreflang` per tutte le versioni linguistiche disponibili delle tue pagine (pagine prodotto, pagine categoria, pagine CMS, ecc.). Questo è cruciale per la SEO internazionale.
        -   *Quando disabilitato (NO):* Nessun tag `hreflang` verrà aggiunto da questo modulo. Se hai un negozio multilingue, i motori di ricerca potrebbero trattare le tue diverse versioni linguistiche come contenuto duplicato, potenzialmente danneggiando il tuo posizionamento internazionale.
    -   **Valore consigliato:** **SÌ**. Abilita sempre questa opzione se il tuo negozio supporta più lingue o si rivolge a regioni diverse.
    -   **Scenario / esempio del commerciante:** Se vendi prodotti sia in inglese che in spagnolo, abilitando questa opzione ti assicuri che un cliente di lingua spagnola che cerca su Google vedrà la versione spagnola della tua pagina prodotto, e un cliente di lingua inglese vedrà la versione inglese.
-   **Abilita URL canonici:**

    -   **Cosa fa questa impostazione:** Questo interruttore principale controlla se il modulo genererà e aggiungerà i tag URL `canonical` all'intestazione HTML del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo genererà e inserirà attivamente i tag `canonical` per tutte le pagine, puntando alla versione preferita di ogni pagina. Questo aiuta a consolidare i segnali SEO e previene problemi di contenuto duplicato.
        -   *Quando disabilitato (NO):* Nessun tag `canonical` verrà aggiunto da questo modulo. Il tuo negozio potrebbe soffrire di problemi di contenuto duplicato se lo stesso contenuto è accessibile tramite più URL (ad esempio, con o senza slash finali, con parametri diversi o tramite percorsi di categoria diversi).
    -   **Valore consigliato:** **SÌ**. I tag canonici sono fondamentali per una buona SEO su quasi tutti i siti web.
    -   **Scenario / esempio del commerciante:** Una pagina prodotto potrebbe essere accessibile tramite `iltuonegozio.com/nome-prodotto` e anche `iltuonegozio.com/categoria/nome-prodotto`. Abilitando gli URL canonici si indica a Google che `iltuonegozio.com/nome-prodotto` è la versione principale, assicurando che tutto il credito SEO vada a quell'unico URL.
-   **Usa hreflang x-default:**

    -   **Cosa fa questa impostazione:** L'attributo hreflang `x-default` specifica una pagina predefinita che dovrebbe essere mostrata agli utenti quando nessun'altra lingua/regione corrisponde alle impostazioni del loro browser o alla loro posizione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo aggiungerà un tag hreflang `x-default`, tipicamente puntando alla lingua predefinita del tuo negozio o a una versione internazionale generica. Questo è utile per gli utenti la cui lingua o regione non è esplicitamente targetizzata dagli altri tag hreflang.
        -   *Quando disabilitato (NO):* Nessun tag hreflang `x-default` verrà aggiunto. Agli utenti la cui lingua/regione non corrisponde a nessun hreflang specifico potrebbe essere mostrata una pagina meno pertinente, o i motori di ricerca potrebbero dover indovinare quale pagina mostrare.
    -   **Valore consigliato:** **SÌ**. È generalmente una buona pratica includere un `x-default` per una SEO internazionale completa, specialmente se hai un pubblico globale.
    -   **Scenario / esempio del commerciante:** Se hai versioni inglese (USA), inglese (UK) e francese, ma un utente dalla Germania cerca in inglese, l'`x-default` può indirizzarlo alla tua pagina inglese (USA) generale, assicurando che riceva comunque contenuti pertinenti.
-   **Usa solo il codice lingua (es. "en" invece di "en-us"):**

    -   **Cosa fa questa impostazione:** Controlla il formato dei codici lingua utilizzati nei tuoi tag `hreflang`.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo utilizzerà solo il codice lingua ISO di due lettere (es. `en`, `fr`, `de`). Questo è più semplice e adatto se ti rivolgi a una lingua a livello globale piuttosto che a regioni specifiche.
        -   *Quando disabilitato (NO):* Il modulo utilizzerà sia il codice lingua che il codice regione (es. `en-US`, `en-GB`, `fr-CA`). Questo è più preciso e consigliato se hai contenuti o prezzi diversi per paesi specifici all'interno della stessa lingua.
    -   **Valore consigliato:**
        -   **NO** se hai un targeting regionale specifico (es. contenuti inglesi diversi per USA vs. UK).
        -   **SÌ** se le tue diverse versioni linguistiche sono generiche e non specifiche per paese (es. una versione "inglese" per tutti i parlanti inglesi).
    -   **Scenario / esempio del commerciante:** Se vendi in inglese e hai una versione inglese per tutti i paesi, scegli SÌ. Se hai contenuti/prezzi inglesi separati per USA e UK, scegli NO per usare `en-US` e `en-GB`.

#### **Salvataggio delle impostazioni:**

Dopo aver effettuato le tue selezioni, clicca sul pulsante **"Salva"** in fondo alla pagina di configurazione per applicare le modifiche.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita tag hreflang | SÌ | Attiva i tag hreflang per la SEO internazionale. |
| Configurazione modulo | Abilita URL canonici | SÌ | Attiva i tag canonici per prevenire contenuti duplicati. |
| Configurazione modulo | Usa hreflang x-default | SÌ | Fornisce una pagina di fallback per gli utenti con lingua/regione non corrispondente. |
| Configurazione modulo | Usa solo il codice lingua (es. "en" invece di "en-us") | NO (dipende dalla strategia) | Determina se hreflang usa solo la lingua (`en`) o lingua-regione (`en-US`). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho abilitato il modulo, ma non vedo alcun cambiamento visivo sul mio sito web. Funziona?**
R1: Sì, funziona come previsto! Questo modulo opera interamente in background. Aggiunge codice speciale (tag hreflang e canonici) alla sezione `<head>` dell'HTML del tuo sito web, che è visibile ai motori di ricerca ma non ai tuoi clienti. Per verificare che funzioni, puoi fare clic con il tasto destro su qualsiasi pagina del tuo negozio, selezionare "Visualizza sorgente pagina" (o simile) e cercare "hreflang" o "canonical". Dovresti vedere i tag lì.

**D2: Dopo aver abilitato il modulo, il mio posizionamento nei motori di ricerca non è migliorato immediatamente. Cosa dovrei aspettarmi?**
R2: I cambiamenti SEO, specialmente quelli relativi alla scansione e all'indicizzazione, richiedono tempo per essere riflessi nei risultati dei motori di ricerca. Google e altri motori di ricerca devono scansionare nuovamente il tuo sito, elaborare i nuovi tag e aggiornare il loro indice. Questo processo può richiedere da pochi giorni a diverse settimane o addirittura mesi. Continua a monitorare la tua Google Search Console per eventuali modifiche nell'indicizzazione o nei rapporti di targeting internazionale.

**D3: Il mio tema personalizzato ha alcune strutture URL uniche. Questo modulo funzionerà comunque correttamente?**
R3: Il modulo è progettato per integrarsi con i meccanismi di generazione URL principali di PrestaShop. Nella maggior parte dei casi, dovrebbe funzionare senza problemi con i temi personalizzati. Tuttavia, se il tuo tema modifica pesantemente il routing URL standard di PrestaShop o il rendering delle pagine, c'è una piccola possibilità di conflitto. Se sospetti un problema, prima svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**). Se i problemi persistono, contatta il supporto MyPresta.eu con i dettagli del tuo tema e di eventuali pagine specifiche in cui riscontri problemi.

**D4: Ho un negozio multilingue, ma alcune pagine non hanno traduzioni per tutte le lingue. Come gestisce questo il modulo?**
R4: Il modulo genera tipicamente i tag `hreflang` solo per le lingue che hanno effettivamente contenuto disponibile per una data pagina. Se un prodotto o una categoria non è tradotto in una lingua specifica, il modulo non dovrebbe generare un tag `hreflang` per quella traduzione inesistente. Assicurati che le tue traduzioni PrestaShop siano gestite correttamente nel Back Office.

**D5: Vedo più tag canonici o tag hreflang errati. Cosa potrebbe esserci di sbagliato?**
R5: Questo di solito indica un conflitto con un altro modulo SEO o il tuo tema che potrebbe anche cercare di aggiungere tag canonici o hreflang.
1.  **Verifica la presenza di altri moduli SEO:** Disabilita qualsiasi altro modulo SEO uno per uno per identificare quello in conflitto.
2.  **Verifica il tuo tema:** Alcuni temi potrebbero avere tag canonici codificati.
3.  **Svuota la cache:** Svuota sempre la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**) dopo aver apportato modifiche al modulo.
Se il problema persiste, contatta il supporto MyPresta.eu per assistenza.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "hreflang e URL canonici gratuiti" (`myhreflang`) è un modulo PrestaShop leggero progettato principalmente per iniettare meta tag `hreflang` e `canonical` nella sezione `<head>` delle pagine del front-office. Aderisce all'architettura standard dei moduli PrestaShop, utilizzando hook per integrare la sua funzionalità senza modificare i file core. La logica del modulo risiede principalmente nel suo file PHP principale, `index.php`, che gestisce la configurazione, l'installazione, la disinstallazione e la logica principale per la generazione dei tag. Sfrutta le classi `Context` e `Link` di PrestaShop per determinare la pagina corrente, le lingue disponibili e generare URL corretti.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller personalizzato per il Front-Office o il Back-Office Admin. Tutta la logica è gestita all'interno del file principale del modulo e dei suoi metodi agganciati.

### 4.3 Classi e modelli core (`classes/`)

Questo modulo **non** definisce classi personalizzate o `ObjectModel` in una directory `classes/`. Tutta la logica core è autocontenuta all'interno della classe `myhreflang` in `index.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato. La sua funzionalità è puramente la generazione di tag HTML lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato. La sua funzionalità è puramente la generazione di tag HTML lato server e non ha alcun impatto visivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza un singolo template Smarty per renderizzare i tag `hreflang` e `canonical`.

-   **Template degli hook (`views/templates/hook/`)**:
    -   `myhreflang/views/templates/hook/hreflang.tpl`: Questo template è responsabile dell'output dei tag effettivi `<link rel="alternate" hreflang="..." href="..." />` e `<link rel="canonical" href="..." />`.
        -   **Renderizzato nell'hook**: `displayHeader`
        -   **Scopo**: Riceve un array di `hreflang_links` e un `canonical_link` dal metodo `hookDisplayHeader` del modulo. Quindi itera su questi per generare i tag HTML `<link>` necessari.
        -   **Variabili disponibili**:
            -   `$hreflang_links`: Un array di array associativi, ciascuno contenente `lang_code` (es. 'en', 'en-US', 'x-default') e `url`.
            -   `$canonical_link`: Una stringa contenente l'URL canonico per la pagina corrente.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Questo modulo **non** crea tabelle SQL personalizzate. Memorizza le sue impostazioni di configurazione direttamente nella tabella `ps_configuration` utilizzando i metodi standard di PrestaShop `Configuration::get()` e `Configuration::updateValue()`.

    -   Chiavi di configurazione memorizzate in `ps_configuration`:
        -   `MYHREFLANG_HREFLANG_ENABLED` (booleano)
        -   `MYHREFLANG_CANONICAL_ENABLED` (booleano)
        -   `MYHREFLANG_XDEFAULT_ENABLED` (booleano)
        -   `MYHREFLANG_LANG_CODE_ONLY` (booleano)
-   **Tabella degli hook registrati**:

    | Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Questo è l'hook principale utilizzato dal modulo. Chiama il metodo `hookDisplayHeader()` per generare e iniettare i tag `<link>` `hreflang` e `canonical` nell'HTML `<head>` della pagina. |

## 5. Supporto ufficiale e aggiornamenti

Per il supporto ufficiale, gli aggiornamenti del modulo e qualsiasi ulteriore assistenza con il modulo "hreflang e URL canonici gratuiti", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per aiutarti con qualsiasi domanda o problema tecnico tu possa incontrare.
