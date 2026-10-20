---
title: "Scheda Vendite Facebook - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Scheda Vendite Facebook di MyPresta.eu."
sidebar:
  label: "Scheda Vendite Facebook - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Sales Tab su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-sales-tab.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-sales-tab/)
>
> ---


# Scheda Vendite Facebook

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).
- **Requisiti esterni**: Una Fanpage di Facebook (Pagina aziendale) attiva di cui sei amministratore. Dovrai anche creare un'applicazione Facebook per collegare il tuo negozio alla tua Fanpage, il che implica l'ottenimento di un ID app e un Segreto app dal portale per sviluppatori di Facebook.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Scheda Vendite Facebook)

Questa è la schermata di configurazione principale e unica per il modulo Scheda Vendite Facebook. Qui collegherai il tuo negozio PrestaShop alla tua Fanpage di Facebook e definirai quale contenuto viene visualizzato.

Per accedere a questa pagina, vai su **Back Office > Moduli > Gestione moduli**, cerca "Scheda Vendite Facebook" e clicca su "Configura".

#### **Impostazioni dell'applicazione Facebook**

Queste impostazioni sono cruciali per stabilire la connessione tra il tuo negozio PrestaShop e la tua Fanpage di Facebook. Dovrai creare un'applicazione Facebook tramite il portale per sviluppatori di Facebook per ottenere queste credenziali.

-   **ID app Facebook:**

    *   **Cosa fa questa impostazione:** Questo è un identificatore univoco per la tua applicazione Facebook. Indica a Facebook quale applicazione sta tentando di connettersi alla tua Fanpage.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se inserito correttamente:* Consente al tuo modulo di comunicare con Facebook e visualizzare la scheda delle vendite.
        *   *Se errato o vuoto:* Il modulo non sarà in grado di connettersi a Facebook e la scheda delle vendite non funzionerà o non apparirà sulla tua Fanpage.
    *   **Valore consigliato:** L'ID app esatto fornito da Facebook quando crei la tua applicazione.
    *   **Scenario/esempio del commerciante:** Hai creato un'app Facebook chiamata "Scheda Vendite MyStore" su developers.facebook.com e Facebook le ha assegnato un ID app come `123456789012345`. Inseriresti questo numero qui.
-   **Segreto app Facebook:**

    *   **Cosa fa questa impostazione:** Questa è una chiave segreta associata alla tua applicazione Facebook, utilizzata per autenticare le richieste della tua applicazione a Facebook. Dovrebbe essere mantenuta riservata.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se inserito correttamente:* Garantisce una comunicazione sicura tra il tuo negozio e Facebook.
        *   *Se errato o vuoto:* Facebook rifiuterà i tentativi di connessione e la scheda delle vendite non funzionerà.
    *   **Valore consigliato:** Il Segreto app esatto fornito da Facebook quando crei la tua applicazione.
    *   **Scenario/esempio del commerciante:** Insieme al tuo ID app, Facebook fornisce un Segreto app (es. `abcdef1234567890abcdef1234567890`). Inserisci questa stringa qui.
-   **ID pagina Facebook:**

    *   **Cosa fa questa impostazione:** Questo è l'identificatore univoco per la tua specifica Fanpage di Facebook dove desideri che appaia la scheda delle vendite.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se inserito correttamente:* Il modulo sa quale Fanpage targetizzare per aggiungere la scheda delle vendite.
        *   *Se errato o vuoto:* La scheda delle vendite non verrà aggiunta alla Fanpage desiderata, oppure potrebbe essere aggiunta a quella sbagliata se viene inserito un ID errato.
    *   **Valore consigliato:** L'ID pagina esatto della tua Fanpage di Facebook. Di solito puoi trovarlo nella sezione "Informazioni" della tua Fanpage o utilizzando uno strumento di ricerca ID pagina Facebook.
    *   **Scenario/esempio del commerciante:** La Fanpage di Facebook del tuo negozio è "Il Mio Fantastico Negozio". Trovi il suo ID pagina (es. `987654321098765`) e lo inserisci qui.

#### **Impostazioni del contenuto della scheda vendite**

Queste impostazioni controllano quali prodotti o promozioni vengono visualizzati nella tua scheda vendite di Facebook.

-   **Numero di prodotti da visualizzare:**

    *   **Cosa fa questa impostazione:** Determina quanti prodotti dalla tua selezione di vendite speciali verranno mostrati nella scheda di Facebook.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se impostato su un numero più alto (es. 20):* Saranno visibili più prodotti, offrendo ai clienti una selezione più ampia.
        *   *Se impostato su un numero più basso (es. 5):* Verranno visualizzati meno prodotti, concentrando potenzialmente l'attenzione sulle tue migliori offerte.
    *   **Valore consigliato:** 10-20, a seconda di quante vendite attive hai tipicamente e di quanto contenuto vuoi presentare.
    *   **Scenario/esempio del commerciante:** Hai 15 prodotti in saldo. Impostando questo valore su "15" ti assicuri che tutti vengano mostrati nella tua scheda di Facebook. Se vuoi evidenziare solo i primi 5, lo imposteresti su "5".
-   **Visualizza prodotti da categorie specifiche:**

    *   **Cosa fa questa impostazione:** Ti consente di filtrare i prodotti visualizzati nella scheda di Facebook per includere solo quelli provenienti da categorie selezionate nel tuo negozio PrestaShop.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando vengono selezionate categorie specifiche:* Solo i prodotti appartenenti a tali categorie appariranno nella scheda di Facebook, anche se altri prodotti sono in saldo.
        *   *Quando non vengono selezionate categorie (o tutte sono selezionate):* Verranno visualizzati tutti i prodotti che soddisfano i criteri di "vendita".
    *   **Valore consigliato:** Seleziona le categorie pertinenti alle tue promozioni attuali o agli articoli più venduti che desideri evidenziare su Facebook.
    *   **Scenario/esempio del commerciante:** Stai eseguendo una promozione speciale su "Abiti estivi" e "Accessori da spiaggia". Selezioneresti queste due categorie per assicurarti che solo quei prodotti appaiano nella tua scheda vendite di Facebook.
-   **Visualizza prodotti con sconti/saldi specifici:**

    *   **Cosa fa questa impostazione:** Questo è il filtro principale per ciò che costituisce un prodotto "in saldo". Puoi scegliere di visualizzare prodotti che hanno una specifica riduzione di prezzo.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se abilitato e configurato:* Verranno mostrati solo i prodotti con prezzi speciali attivi o sconti percentuali.
        *   *Se disabilitato:* Il modulo potrebbe visualizzare prodotti regolari o prodotti basati su altri criteri (anche se lo scopo principale del modulo è "saldi").
    *   **Valore consigliato:** SÌ, e assicurati che i tuoi prodotti abbiano prezzi speciali attivi configurati in PrestaShop.
    *   **Scenario/esempio del commerciante:** Hai impostato uno sconto del 10% su tutti i "Cappotti invernali" nelle impostazioni dei prodotti del tuo PrestaShop. Questa impostazione assicura che quei cappotti scontati siano quelli che appaiono nella tua scheda di Facebook.

#### **Impostazioni di visualizzazione generali**

-   **Titolo della scheda su Facebook:**

    *   **Cosa fa questa impostazione:** Questo è il testo che apparirà come nome della scheda sulla tua Fanpage di Facebook.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se impostato su "Offerte Speciali":* La tua scheda sarà etichettata "Offerte Speciali" su Facebook.
        *   *Se impostato su "Acquista Ora":* La tua scheda sarà etichettata "Acquista Ora".
    *   **Valore consigliato:** Qualcosa di chiaro e invitante come "Offerte Speciali", "Acquista Ora" o "Le Nostre Offerte".
    *   **Scenario/esempio del commerciante:** Vuoi indicare chiaramente che questa scheda è per le promozioni, quindi imposti il titolo su "Vendite Flash!".
-   **Icona della scheda:**

    *   **Cosa fa questa impostazione:** Ti consente di caricare un'icona personalizzata che apparirà accanto al titolo della tua scheda su Facebook. Questo aiuta la tua scheda a distinguersi.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando viene caricata un'icona:* La tua scheda avrà un identificatore visivo personalizzato.
        *   *Quando non viene caricata alcuna icona:* Facebook utilizzerà un'icona predefinita, oppure la scheda potrebbe apparire senza un'icona specifica.
    *   **Valore consigliato:** Un'icona piccola, chiara e pertinente (es. un carrello della spesa, una stella, un segno di percentuale) che corrisponda al tuo marchio.
    *   **Scenario/esempio del commerciante:** Carichi una piccola immagine di un carrello della spesa per rendere la tua scheda "Acquista Ora" visivamente accattivante e facile da individuare.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | ID app Facebook | Il tuo ID app Facebook | Collega il tuo negozio alla tua app Facebook per l'autenticazione. |
| Configurazione modulo | Segreto app Facebook | Il tuo Segreto app Facebook | Autentica in modo sicuro la tua app con Facebook. |
| Configurazione modulo | ID pagina Facebook | Il tuo ID Fanpage Facebook | Specifica a quale Fanpage verrà aggiunta la scheda delle vendite. |
| Configurazione modulo | Numero di prodotti da visualizzare | 10-20 | Controlla quanti prodotti in saldo vengono mostrati nella scheda. |
| Configurazione modulo | Visualizza prodotti da categorie specifiche | Seleziona le categorie pertinenti | Filtra i prodotti per categoria per la visualizzazione nella scheda. |
| Configurazione modulo | Visualizza prodotti con sconti/saldi specifici | SÌ | Assicura che solo i prodotti scontati vengano mostrati nella scheda. |
| Configurazione modulo | Titolo della scheda su Facebook | "Offerte Speciali" / "Acquista Ora" | Imposta il nome visibile della scheda sulla tua Fanpage di Facebook. |
| Configurazione modulo | Icona della scheda | Carica un'icona pertinente | Fornisce un'icona visiva personalizzata per la tua scheda Facebook. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La mia scheda vendite di Facebook non appare sulla mia Fanpage. Cosa devo fare?**
R1:

-   **Controlla ID app, Segreto app e ID pagina:** Ricontrolla che tutti e tre i valori siano inseriti correttamente nella configurazione del modulo. Anche un singolo errore di battitura impedirà la connessione.
-   **Stato dell'app Facebook:** Assicurati che la tua applicazione Facebook sia attiva e disponibile pubblicamente (non in modalità di sviluppo). Puoi verificarlo nella tua dashboard per sviluppatori di Facebook.
-   **Permessi:** Assicurati che la tua app Facebook abbia i permessi necessari per gestire le pagine.
-   **Cache:** Cancella la cache Smarty di PrestaShop (Parametri avanzati > Prestazioni) e la cache del tuo browser. A volte, le modifiche impiegano un momento per propagarsi.
-   **Amministratore della pagina Facebook:** Assicurati che l'account Facebook che stai utilizzando per gestire la Fanpage abbia i diritti di amministratore sia per la Fanpage che per l'app Facebook.

**D2: I prodotti mostrati nella scheda di Facebook non sono quelli che mi aspetto.**
R2:

-   **Impostazione "Visualizza prodotti con sconti/saldi specifici":** Assicurati che sia abilitata se vuoi mostrare solo articoli scontati.
-   **Sconti sui prodotti:** Verifica che i prodotti che ti *aspetti* di vedere abbiano effettivamente prezzi speciali attivi o sconti percentuali configurati nelle impostazioni dei prodotti del tuo PrestaShop.
-   **Impostazione "Visualizza prodotti da categorie specifiche":** Se hai selezionato categorie specifiche, assicurati che i prodotti che desideri visualizzare appartengano a tali categorie.
-   **"Numero di prodotti da visualizzare":** Se hai molte vendite, ma questo numero è basso, verranno mostrati solo i primi pochi.

**D3: Come ottengo un ID app Facebook, un Segreto app e un ID pagina?**
R3:

-   **ID app Facebook e Segreto app:** Vai su [developers.facebook.com](https://developers.facebook.com/), accedi e crea una nuova app. Segui le istruzioni di Facebook per configurare una nuova app, scegliendo tipicamente un tipo "Business" o "Sito web". Una volta creata, troverai l'ID app e il Segreto app nelle impostazioni della dashboard della tua app.
-   **ID pagina Facebook:** Naviga alla tua Fanpage di Facebook. Spesso puoi trovare l'ID pagina nella sezione "Informazioni" della tua pagina. In alternativa, ci sono strumenti online (cerca "Facebook Page ID Finder") dove puoi incollare l'URL della tua Fanpage per recuperare il suo ID.

**D4: L'icona o il titolo della scheda non si aggiornano su Facebook.**
R4:

-   **Caching di Facebook:** Facebook stesso può memorizzare nella cache le informazioni della pagina. Potrebbe essere necessario del tempo (fino a qualche ora) affinché le modifiche al titolo o all'icona della scheda si riflettano a livello globale.
-   **Salvataggio della configurazione del modulo:** Assicurati di aver salvato la configurazione del modulo dopo aver apportato le modifiche.
-   **Cancella cache:** Cancella la cache di PrestaShop (Parametri avanzati > Prestazioni) e la cache del tuo browser.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Scheda Vendite Facebook` (`prestasales`) è un modulo PrestaShop standard progettato per integrarsi con la piattaforma Facebook. La sua funzione principale è quella di servire contenuti (in particolare, un elenco di prodotti in saldo) che possono essere incorporati all'interno di una scheda di una Fanpage di Facebook. Il modulo sfrutta il sistema di configurazione di PrestaShop per memorizzare le credenziali dell'API di Facebook e le preferenze di visualizzazione. Non introduce complessi pattern MVC o tabelle di database personalizzate, ma si basa sulle funzionalità principali di PrestaShop per il recupero dei prodotti e la gestione della configurazione. La logica principale del modulo risiede nel suo file `de.php`, che gestisce l'installazione, la disinstallazione e la visualizzazione della configurazione.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce classi personalizzate o definizioni di `ObjectModel`. Interagisce direttamente con le classi `Product` e `Category` principali di PrestaShop e con la classe `Configuration` per le impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`prestasales/css/css.css`**:
    *   **Ambito:** Questo foglio di stile è destinato alla stilizzazione del contenuto visualizzato all'interno della scheda di Facebook.
    *   **Componenti UI principali e contenitori che stilizza:** Tipicamente conterrebbe stili per elenchi di prodotti, immagini, prezzi, badge di sconto e pulsanti "aggiungi al carrello" o "visualizza prodotto" all'interno della scheda Facebook incorporata.
    *   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:** Gli sviluppatori dovrebbero ispezionare l'output HTML all'interno della scheda Facebook per identificare nomi di classe specifici. I selettori comuni potrebbero includere `.prestasales-product-list`, `.prestasales-product-item`, `.prestasales-product-image`, `.prestasales-product-name`, `.prestasales-price`, `.prestasales-discount`, `.prestasales-button`.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non elenca esplicitamente i file `.tpl` nell'inventario fornito. Tuttavia, in base alla sua funzionalità, tipicamente conterrebbe:

-   **Template di hook (`views/templates/hook/`)**:

    *   È altamente probabile che un template come `views/templates/hook/displayFacebookSalesTab.tpl` (o simile) esista internamente all'interno del file `de.php` del modulo o sia generato al volo. Questo template sarebbe responsabile del rendering della struttura HTML dell'elenco prodotti che viene poi servito a Facebook.
    *   **Scopo:** Questo template itererebbe sui prodotti in saldo selezionati e visualizzerebbe le loro immagini, nomi, prezzi e link, formattati per l'incorporamento all'interno di un iframe di Facebook.
-   **Template di amministrazione (`views/templates/admin/`)**:

    *   Dato che la configurazione è gestita da `getContent()`, un template come `views/templates/admin/configure.tpl` o `views/templates/admin/configuration_form.tpl` verrebbe utilizzato per renderizzare il modulo del modulo di configurazione del back-office. Questo template conterrebbe i campi di input per ID app, Segreto app, ID pagina, opzioni di visualizzazione prodotti, ecc.
-   **Template front-office (`views/templates/front/`)**:

    *   Non sono previsti template dedicati al front-office poiché l'output del modulo è principalmente per la piattaforma Facebook.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    *   Questo modulo non crea tabelle SQL personalizzate.
    *   Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` di PrestaShop utilizzando chiavi come `PRESTASALES_APP_ID`, `PRESTASALES_APP_SECRET`, `PRESTASALES_PAGE_ID`, `PRESTASALES_NUM_PRODUCTS`, `PRESTASALES_CATEGORIES`, `PRESTASALES_DISCOUNTS_ONLY`, `PRESTASALES_TAB_TITLE`, `PRESTASALES_TAB_ICON`.
-   **Tabella degli hook registrati**:
    L'interazione principale del modulo con il sistema di hook di PrestaShop sarebbe per la sua configurazione e potenzialmente per il rendering del contenuto che Facebook recupera.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Sebbene il modulo non visualizzi direttamente contenuti sul negozio, potrebbe utilizzare questo hook per caricare gli script SDK di Facebook necessari o i meta tag se dovesse implementare funzionalità avanzate di integrazione con Facebook (ad esempio, tag Open Graph), sebbene ciò non sia esplicitamente dichiarato per la funzione principale di questo modulo. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del back-office. | Utilizzato per caricare CSS o JS specifici del modulo per la pagina di configurazione, se presenti. |
| `moduleRoutes` | Durante l'inizializzazione della riscrittura URL. | Non esplicitamente utilizzato da questo modulo, in quanto non definisce percorsi front-office personalizzati. |
| `actionProductUpdate` / `actionProductAdd` | Dopo l'aggiornamento o l'aggiunta di un prodotto. | Non esplicitamente utilizzato, ma potrebbe essere utilizzato per cancellare la cache relativa agli elenchi di prodotti per la scheda di Facebook. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Per registrare i valori predefiniti della configurazione e potenzialmente impostare i passaggi iniziali di integrazione dell'app Facebook. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Per pulire i dati di configurazione dalla tabella `ps_configuration`. |

La funzionalità principale di servire il contenuto a Facebook è probabilmente gestita da una richiesta diretta al file PHP principale del modulo (`de.php`) o a un metodo interno specifico che renderizza l'elenco dei prodotti, piuttosto che un hook `display` standard di PrestaShop. Questo contenuto viene quindi incorporato all'interno di un iframe sulla Fanpage di Facebook.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo "Scheda Vendite Facebook", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per aiutarti con qualsiasi problema o domanda tu possa avere.
