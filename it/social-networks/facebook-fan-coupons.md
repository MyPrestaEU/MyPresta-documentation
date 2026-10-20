---
title: "Facebook Fan Coupons - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Facebook Fan Coupons di MyPresta.eu."
sidebar:
  label: "Facebook Fan Coupons - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Fan Coupons su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-coupons.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-fan-coupons/)
>
> ---


# Facebook Fan Coupons

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Il tuo server deve essere in grado di comunicare con l'API di Facebook.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo Facebook Fan Coupons, dove definisci come vengono generati i coupon e come si comporta il modulo.

#### Impostazioni generali

-   **Cosa fa questa impostazione:** Queste impostazioni controllano il comportamento generale del modulo, inclusi gli aggiornamenti e le funzionalità di base.
-   **Effetto della modifica di questa impostazione:**
    -   `mypresta_updates`, `update_`, `updatev_`: Queste sono impostazioni interne relative agli aggiornamenti del modulo e ai controlli di versione da parte di MyPresta.eu. Generalmente non è necessario modificarle.
-   **Valore consigliato:** Lascia questi valori predefiniti.
-   **Scenario/esempio del commerciante:** Queste impostazioni assicurano che il tuo modulo sia aggiornato e compatibile con i servizi MyPresta.eu.

#### Impostazioni di generazione del coupon

-   **FANCOUPON\_FONTSTYLE**

    -   **Cosa fa questa impostazione:** Definisce lo stile del carattere utilizzato per il codice coupon generato e visualizzato al cliente sulla tua scheda Facebook. Questo è puramente per la presentazione visiva.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un carattere specifico:* Il codice coupon verrà visualizzato in quel carattere, rendendolo più accattivante o in linea con il tuo marchio.
        -   *Se lasciato predefinito:* Verrà utilizzato un carattere standard e leggibile.
    -   **Valore consigliato:** Scegli un carattere chiaro e leggibile che si abbini all'estetica del tuo marchio.
    -   **Scenario/esempio del commerciante:** Se il tuo marchio utilizza un carattere elegante specifico, puoi inserire il suo nome qui (ad esempio, "Arial Black", "Verdana") per far sì che il coupon appaia più integrato.
-   **FANCOUPON\_VOUCHERCODE**

    -   **Cosa fa questa impostazione:** Questo è il *prefisso* per i codici voucher generati automaticamente. Ogni codice inizierà con questo testo, seguito da caratteri casuali.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su "FANCOUPON":* Tutti i codici generati avranno l'aspetto di "FANCOUPONABCD123".
        -   *Se impostato su "FBPROMO":* Tutti i codici generati avranno l'aspetto di "FBPROMOXYZ789".
    -   **Valore consigliato:** Un prefisso breve e memorabile relativo a Facebook o alla tua promozione (ad esempio, "FBPROMO", "FAN2024", "MYFAN").
    -   **Scenario/esempio del commerciante:** L'utilizzo di "FBPROMO" ti aiuta a identificare facilmente quali ordini provengono da questa campagna Facebook nella cronologia degli ordini di PrestaShop.
-   **FANCOUPON\_MODE**

    -   **Cosa fa questa impostazione:** Determina il tipo di sconto che il codice voucher generato fornirà (ad esempio, percentuale, importo fisso, spedizione gratuita).
    -   **Effetto della modifica di questa impostazione:**
        -   *Sconto percentuale:* Il coupon ridurrà il totale dell'ordine di una percentuale (ad esempio, 10% di sconto).
        -   *Sconto importo fisso:* Il coupon ridurrà il totale dell'ordine di un valore monetario fisso (ad esempio, 10€ di sconto).
        -   *Spedizione gratuita:* Il coupon renderà la spedizione gratuita per l'ordine.
    -   **Valore consigliato:** Questo dipende dalla tua strategia di marketing. Gli sconti percentuali sono spesso popolari per le promozioni generali.
    -   **Scenario/esempio del commerciante:** Per offrire il 15% di sconto ai nuovi fan di Facebook, selezioneresti "Sconto percentuale" qui e poi specificheresti "15" nel campo valore corrispondente (che appare dopo aver selezionato la modalità).
-   **FANCOUPON\_CHARS**

    -   **Cosa fa questa impostazione:** Specifica i tipi di caratteri (lettere, numeri) che verranno utilizzati nella *parte casuale* del codice voucher generato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Lettere e numeri:* I codici saranno un mix di caratteri alfanumerici (ad esempio, "ABC123").
        -   *Solo numeri:* I codici conterranno solo cifre (ad esempio, "123456").
        -   *Solo lettere:* I codici conterranno solo lettere (ad esempio, "ABCDEF").
    -   **Valore consigliato:** "Lettere e numeri" per la massima unicità e sicurezza.
    -   **Scenario/esempio del commerciante:** Per rendere i codici più facili da leggere, potresti scegliere "Solo lettere", ma questo riduce il numero di combinazioni uniche possibili per una data lunghezza.
-   **FANCOUPON\_LENGTH**

    -   **Cosa fa questa impostazione:** Definisce la lunghezza della *parte casuale* del codice voucher generato (escluso il prefisso).
    -   **Effetto della modifica di questa impostazione:**
        -   *Lunghezza più corta (ad esempio, 4):* I codici sono più veloci da digitare ma meno unici (ad esempio, "FBPROMOABCD").
        -   *Lunghezza più lunga (ad esempio, 8):* I codici sono più sicuri e unici ma richiedono più tempo per essere digitati (ad esempio, "FBPROMOABCD12345").
    -   **Valore consigliato:** 6-8 caratteri per un buon equilibrio tra unicità e usabilità.
    -   **Scenario/esempio del commerciante:** Se ti aspetti un volume molto elevato di generazioni di coupon, una lunghezza maggiore assicura che ogni codice sia veramente unico e previene duplicati accidentali.
-   **FANCOUPON\_VOUCHER\_CAT**

    -   **Cosa fa questa impostazione:** Ti consente di limitare il codice voucher generato in modo che si applichi solo ai prodotti all'interno di categorie specifiche nel tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando vengono selezionate categorie specifiche:* Il coupon funzionerà solo se il cliente ha prodotti di quelle categorie nel carrello.
        -   *Quando non vengono selezionate categorie:* Il coupon si applicherà a tutti i prodotti del negozio.
    -   **Valore consigliato:** Lascia vuoto se il coupon deve applicarsi a tutto il negozio. Seleziona le categorie se vuoi promuovere linee di prodotti specifiche.
    -   **Scenario/esempio del commerciante:** Se stai eseguendo una promozione specifica per la tua "Collezione Estiva", selezioneresti quella categoria qui in modo che il coupon funzioni solo su quegli articoli.
-   **PS\_LANG\_DEFAULT**

    -   **Cosa fa questa impostazione:** Questo è l'ID della lingua predefinita del tuo negozio PrestaShop. Viene utilizzato internamente dal modulo per garantire che le descrizioni dei coupon e altri elementi dipendenti dalla lingua vengano creati correttamente.
    -   **Effetto della modifica di questa impostazione:** Una modifica errata di questo valore potrebbe causare problemi con il modo in cui i coupon vengono creati nella lingua predefinita del tuo negozio.
    -   **Valore consigliato:** Lascia il valore predefinito rilevato automaticamente da PrestaShop.
    -   **Scenario/esempio del commerciante:** Questo assicura che quando un coupon viene generato, la sua descrizione interna (ad esempio, "Coupon Fan Facebook") sia impostata correttamente nella lingua principale del tuo negozio.

#### Impostazioni dei blocchi pubblicitari (Opzionale)

-   **FANCOUPON\_ADV\_POS1**

    -   **Cosa fa questa impostazione:** Controlla l'immagine/banner visualizzato nella **colonna sinistra** del tuo negozio PrestaShop per promuovere l'offerta del coupon Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un URL immagine:* L'immagine specificata apparirà nella colonna sinistra.
        -   *Quando lasciato vuoto:* Nessuna immagine verrà visualizzata nella colonna sinistra.
    -   **Valore consigliato:** Un'immagine banner accattivante (ad esempio, larga 200px) che pubblicizzi chiaramente l'offerta "Metti Mi piace su Facebook, ottieni un coupon!".
    -   **Scenario/esempio del commerciante:** Carichi un'immagine banner personalizzata sul tuo server (ad esempio, `img/cms/fb-coupon-left.jpg`) e inserisci il suo URL completo qui.
-   **FANCOUPON\_ADV\_POS2**

    -   **Cosa fa questa impostazione:** Controlla l'immagine/banner visualizzato nella **colonna destra** del tuo negozio PrestaShop per promuovere l'offerta del coupon Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un URL immagine:* L'immagine specificata apparirà nella colonna destra.
        -   *Quando lasciato vuoto:* Nessuna immagine verrà visualizzata nella colonna destra.
    -   **Valore consigliato:** Simile a `FANCOUPON_ADV_POS1`, un'immagine banner accattivante (ad esempio, larga 200px).
    -   **Scenario/esempio del commerciante:** Potresti usare un design diverso per il banner della colonna destra o semplicemente duplicare quello della colonna sinistra.
-   **FANCOUPON\_ADV\_POS3**

    -   **Cosa fa questa impostazione:** Controlla l'immagine/banner visualizzato nel **footer** del tuo negozio PrestaShop per promuovere l'offerta del coupon Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un URL immagine:* L'immagine specificata apparirà nel footer.
        -   *Quando lasciato vuoto:* Nessuna immagine verrà visualizzata nel footer.
    -   **Valore consigliato:** Un'immagine banner accattivante adatta all'area del footer.
    -   **Scenario/esempio del commerciante:** Un banner più largo e più corto (ad esempio, largo 900px, alto 100px) che si adatti bene al footer.
-   **FANCOUPON\_ADV\_URL**

    -   **Cosa fa questa impostazione:** Questo è l'URL a cui tutti i banner pubblicitari (`FANCOUPON_ADV_POS1`, `POS2`, `POS3`) si collegheranno quando cliccati. Questo dovrebbe essere l'URL diretto alla scheda della tua Pagina Fan di Facebook dove il coupon può essere generato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato sull'URL della tua scheda Facebook:* Cliccando su uno qualsiasi dei banner, il cliente verrà portato direttamente alla scheda di generazione del coupon sulla tua pagina Facebook.
        -   *Se lasciato vuoto o errato:* I banner non saranno cliccabili o porteranno a una pagina errata.
    -   **Valore consigliato:** L'URL esatto della scheda della tua Pagina Fan di Facebook dove è incorporato il modulo coupon.
    -   **Scenario/esempio del commerciante:** Dopo aver configurato la scheda di Facebook, otterrai un URL unico per essa (ad esempio, `https://www.facebook.com/YOURPAGE/app_1234567890`). Inserisci quell'URL qui.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | `FANCOUPON_FONTSTYLE` | Carattere di sistema predefinito | Stile del carattere per il codice coupon visualizzato su Facebook. |
| Configurazione modulo | `FANCOUPON_VOUCHERCODE` | `FANCOUPON` | Prefisso per i codici voucher generati. Aiuta a identificare la campagna. |
| Configurazione modulo | `FANCOUPON_MODE` | Sconto percentuale | Tipo di sconto (percentuale, fisso, spedizione gratuita). |
| Configurazione modulo | `FANCOUPON_CHARS` | Lettere e numeri | Set di caratteri per la parte casuale del codice. |
| Configurazione modulo | `FANCOUPON_LENGTH` | 6-8 caratteri | Lunghezza della parte casuale del codice. Influisce sull'unicità. |
| Configurazione modulo | `FANCOUPON_VOUCHER_CAT` | Vuoto (tutti i prodotti) | Limita l'uso del coupon a categorie di prodotti specifiche. |
| Configurazione modulo | `FANCOUPON_ADV_POS1` | Vuoto | URL dell'immagine banner per la colonna sinistra. |
| Configurazione modulo | `FANCOUPON_ADV_POS2` | Vuoto | URL dell'immagine banner per la colonna destra. |
| Configurazione modulo | `FANCOUPON_ADV_POS3` | Vuoto | URL dell'immagine banner per il footer. |
| Configurazione modulo | `FANCOUPON_ADV_URL` | Vuoto | URL di destinazione per tutti i banner pubblicitari (la tua scheda Facebook). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei coupon non funzionano dopo la generazione.**
R: Controlla quanto segue:
1.  **Regole carrello PrestaShop:** Vai su **Catalogo > Sconti > Regole carrello** nel back office di PrestaShop. Cerca i coupon con il prefisso che hai definito (`FANCOUPON_VOUCHERCODE`). Assicurati che siano attivi e non siano scaduti. Il modulo li crea automaticamente, ma a volte può verificarsi un intervento manuale o un conflitto.
2.  **Configurazione del modulo:** Ricontrolla le impostazioni `FANCOUPON_MODE` e `FANCOUPON_VOUCHER_CAT`. Se hai limitato il coupon a una categoria, assicurati che il cliente stia cercando di usarlo su prodotti di quella categoria.
3.  **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**) e la cache del tuo browser.

**D: I banner pubblicitari non vengono visualizzati nel mio negozio.**
R:
1.  **Hook del modulo:** Assicurati che il modulo sia agganciato correttamente. In **Moduli > Gestione moduli**, trova "Facebook Fan Coupons" e clicca su "Configura". Controlla la scheda "Posizioni" (o "Hook" nelle versioni precedenti) per vedere se è assegnato a `displayLeftColumn`, `displayRightColumn` o `displayFooter`. In caso contrario, potrebbe essere necessario agganciarlo manualmente tramite **Design > Posizioni** (o **Moduli > Posizioni**).
2.  **URL delle immagini:** Verifica che gli URL inseriti per `FANCOUPON_ADV_POS1`, `POS2`, `POS3` siano corretti e che le immagini esistano in quelle posizioni.
3.  **Compatibilità del tema:** Alcuni temi personalizzati potrebbero sovrascrivere le posizioni degli hook standard. Se i banner non appaiono ancora, potresti aver bisogno di un webmaster per controllare i file del tuo tema.

**D: La scheda di Facebook non funziona o non mostra il generatore di coupon.**
R: Questo modulo fornisce la logica di backend per la generazione dei coupon. La configurazione effettiva della scheda di Facebook viene eseguita *all'interno degli strumenti per sviluppatori di Facebook* o di un'app di terze parti che incorpora contenuti personalizzati.
1.  **Configurazione dell'app di Facebook:** Assicurati di aver configurato correttamente un'app di Facebook e di averla collegata alla tua Pagina Fan, puntando all'URL del modulo (che è tipicamente il dominio del tuo negozio PrestaShop con un percorso specifico, o una pagina dedicata che hai configurato per ospitare l'output del modulo). Questo modulo fornisce la *logica* per il coupon, ma la *visualizzazione su Facebook* richiede una corretta configurazione dell'app di Facebook.
2.  **Permessi della pagina Facebook:** Assicurati che la tua pagina Facebook abbia i permessi necessari per le schede personalizzate.
3.  **Connessione sicura (HTTPS):** Facebook richiede che tutte le applicazioni incorporate funzionino tramite HTTPS. Assicurati che il tuo negozio PrestaShop sia completamente protetto con un certificato SSL.

**D: Come traduco il testo del modulo?**
R: Puoi tradurre le frasi del modulo tramite il back office di PrestaShop:
1.  Vai su **Internazionale > Traduzioni** (o **Localizzazione > Traduzioni** nelle versioni precedenti).
2.  Seleziona "Traduzioni dei moduli installati".
3.  Scegli il tuo tema, la tua lingua, quindi seleziona "Facebook Fan Coupons" dall'elenco dei moduli.
4.  Potrai quindi modificare qualsiasi stringa traducibile utilizzata dal modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Facebook Fan Coupons (`fancoupon`) è un modulo PrestaShop standard focalizzato principalmente sulla logica di backend per la generazione di coupon e sulla pubblicità di base nel front-office. Sfrutta la classe `Module` e la classe `Configuration` di PrestaShop per memorizzare le impostazioni. La funzionalità principale prevede la creazione dinamica di oggetti `CartRule` (voucher) basati sull'interazione dell'utente su una scheda Facebook (che è esterna a PrestaShop ma interagisce con la logica del modulo). I componenti del front-office sono limitati a semplici banner immagine agganciati a posizioni di visualizzazione standard.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene controller dedicati per il front-office o il back-office. Tutta la configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo. Qualsiasi interazione per la generazione di coupon verrebbe tipicamente gestita da un'applicazione Facebook esterna che punta a un URL sul sito PrestaShop, che poi attiva la logica del modulo (probabilmente tramite un hook o un punto di ingresso personalizzato non esplicitamente definito come `ModuleFrontController` nell'inventario fornito, ma piuttosto gestito dalla logica centrale del modulo quando chiamato).

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** contiene classi o modelli personalizzati nella directory `classes/`. Utilizza direttamente le classi `CartRule` e `Configuration` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   `fancoupon/lib/voucherengine/script.js`
    -   **Ambito:** Probabilmente Front-office (destinato all'interfaccia della scheda Facebook).
    -   **Responsabilità:** Questo script dovrebbe gestire la logica lato client per il processo di generazione del coupon. Ciò includerebbe:
        -   Rilevare se un utente ha "messo mi piace" alla pagina Facebook (tramite l'API di Facebook).
        -   Attivare una richiesta AJAX al backend di PrestaShop (o al punto di ingresso del modulo) per generare un coupon.
        -   Visualizzare il codice coupon generato all'utente.
        -   Potenzialmente gestire elementi dell'interfaccia utente come spinner di caricamento o messaggi di successo/errore.
-   `fancoupon/views/js/voucherengine/script.js`
    -   **Ambito:** Probabilmente Front-office (destinato all'interfaccia della scheda Facebook).
    -   **Responsabilità:** Questo sembra essere un duplicato o una versione dello script in `lib/`. Servirebbe allo stesso scopo descritto sopra, gestendo gli elementi interattivi della generazione del coupon sulla scheda Facebook. Gli sviluppatori dovrebbero verificare quale `script.js` viene effettivamente caricato e utilizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `fancoupon/lib/voucherengine/ps16.css`
    -   **Ambito:** Stile del cliente del Front-office.
    -   **Responsabilità:** Fornisce uno stile di base per l'interfaccia di generazione del coupon, probabilmente all'interno della scheda Facebook. Il `ps16` nel nome del file suggerisce che potrebbe contenere stili specificamente adattati alla struttura del tema predefinito di PrestaShop 1.6, ma dovrebbe essere generalmente compatibile o facilmente adattabile.
    -   **Selettori di classe CSS chiave:** Includerebbe tipicamente stili per pulsanti, campi di input, aree di visualizzazione del testo per il codice coupon e il layout generale del generatore di coupon. Gli sviluppatori possono ispezionare l'HTML renderizzato sulla scheda Facebook per identificare selettori specifici per l'override.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/advert-*.tpl`)**:
    -   `fancoupon/views/templates/advert-footer.tpl`
        -   **Hook:** `displayFooter` (o `footer` nelle versioni precedenti).
        -   **Output:** Renderizza un banner/immagine pubblicitario nel footer del negozio, collegandosi alla scheda della Pagina Fan di Facebook. Utilizza `FANCOUPON_ADV_POS3` per la sorgente dell'immagine e `FANCOUPON_ADV_URL` per il link.
    -   `fancoupon/views/templates/advert-left.tpl`
        -   **Hook:** `displayLeftColumn` (o `leftcolumn` nelle versioni precedenti).
        -   **Output:** Renderizza un banner/immagine pubblicitario nella colonna sinistra del negozio, collegandosi alla scheda della Pagina Fan di Facebook. Utilizza `FANCOUPON_ADV_POS1` per la sorgente dell'immagine e `FANCOUPON_ADV_URL` per il link.
    -   `fancoupon/views/templates/advert-right.tpl`
        -   **Hook:** `displayRightColumn` (o `rightcolumn` nelle versioni precedenti).
        -   **Output:** Renderizza un banner/immagine pubblicitario nella colonna destra del negozio, collegandosi alla scheda della Pagina Fan di Facebook. Utilizza `FANCOUPON_ADV_POS2` per la sorgente dell'immagine e `FANCOUPON_ADV_URL` per il link.
-   **Template di amministrazione (`views/templates/admin/`)**: Nessuno identificato.
-   **Template del front-office (`views/templates/front/`)**: Nessuno identificato. L'interfaccia utente di generazione del coupon principale è probabilmente renderizzata dinamicamente tramite JavaScript o direttamente all'interno della logica di `fancoupon.php` quando chiamata da Facebook.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop utilizzando chiavi come `FANCOUPON_FONTSTYLE`, `FANCOUPON_VOUCHERCODE`, ecc.
    -   Crea voci in `ps_cart_rule` e tabelle correlate (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group`, ecc.) per ogni coupon generato.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra del negozio. | Visualizza il banner pubblicitario della colonna sinistra. |
| `displayRightColumn` | Renderizza il contenuto nella barra laterale destra del negozio. | Visualizza il banner pubblicitario della colonna destra. |
| `displayFooter` | Renderizza il contenuto nella sezione del footer del negozio. | Visualizza il banner pubblicitario del footer. |
| `leftcolumn` | (PrestaShop 1.6.x e precedenti) Renderizza il contenuto nella barra laterale sinistra. | Hook legacy per il banner pubblicitario della colonna sinistra. |
| `rightcolumn` | (PrestaShop 1.6.x e precedenti) Renderizza il contenuto nella barra laterale destra. | Hook legacy per il banner pubblicitario della colonna destra. |
| `footer` | (PrestaShop 1.6.x e precedenti) Renderizza il contenuto nella sezione del footer. | Hook legacy per il banner pubblicitario del footer. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, il supporto tecnico e qualsiasi domanda relativa al modulo Facebook Fan Coupons, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto dedicato è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda.
