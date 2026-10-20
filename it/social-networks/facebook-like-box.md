---
title: "Facebook Like Box - Manuale Commerciante & Guida alla Configurazione"
description: ""
sidebar:
  label: "Facebook Like Box - Manuale Commerciante & Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Like Box su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-like-box/)
>
> ---


# Facebook Like Box

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e per qualsiasi modulo che interagisce con API esterne come Facebook.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il tuo modulo Facebook Like Box. Qui definirai come il tuo Like Box appare e si comporta nel tuo negozio.

**Nome schermata e posizione menu:** Back Office > Moduli > Gestione moduli > Facebook Like Box > Configura

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio commerciante |
| --- | --- | --- | --- | --- |
| **URL Pagina Facebook** | Questo è il link diretto alla tua Pagina Facebook ufficiale. | *Se impostato:* Il Like Box visualizzerà il contenuto di questa specifica pagina Facebook. *Se vuoto:* Il modulo non funzionerà correttamente in quanto non saprà quale pagina visualizzare. | L'URL della tua Pagina Facebook (es. `https://www.facebook.com/myprestaeu`) | Vuoi promuovere la tua pagina Facebook aziendale principale. |
| **ID App (Facebook)** | Il tuo ID App Facebook, richiesto per alcune funzionalità avanzate e integrazioni API. | *Se impostato:* Abilita il modulo a interagire con l'API Graph di Facebook utilizzando la tua applicazione. *Se vuoto:* Potrebbe causare errori "App non configurata" se il modulo richiede l'accesso all'API. | Il tuo ID App Facebook (es. `123456789012345`) | Devi risolvere un errore "App non configurata" o abilitare funzionalità avanzate dell'API di Facebook. |
| **Larghezza** | Controlla la larghezza del Facebook Like Box in pixel. | *Se impostato su un valore specifico (es. 280):* Il Like Box manterrà quella larghezza esatta. *Se lasciato vuoto o impostato su 0:* Il Like Box tenterà di essere reattivo e di regolare automaticamente la sua larghezza per adattarsi al suo contenitore. | Lascia vuoto per il rilevamento automatico (comportamento reattivo) o imposta un valore specifico come `280` se hai bisogno di una larghezza fissa. | Vuoi che il Like Box si adatti perfettamente a una colonna stretta, quindi lo imposti a `280`. |
| **Altezza** | Controlla l'altezza del Facebook Like Box in pixel. | *Se impostato su un valore specifico (es. 500):* Il Like Box manterrà quell'altezza esatta. *Se lasciato vuoto o impostato su 0:* Il Like Box tenterà di essere reattivo e di regolare automaticamente la sua altezza. | Lascia vuoto per il rilevamento automatico (comportamento reattivo) o imposta un valore specifico come `500` se vuoi mostrare più del flusso di post. | Vuoi visualizzare più post recenti dalla tua pagina Facebook, quindi aumenti l'altezza a `500`. |
| **Mostra Volti** | Determina se vengono visualizzate le immagini del profilo delle persone che hanno messo "Mi piace" alla tua pagina. | *Se abilitato (SÌ):* Piccole immagini del profilo di alcuni dei tuoi fan di Facebook appariranno sotto il pulsante "Mi piace", aggiungendo prova sociale. *Se disabilitato (NO):* Verranno mostrati solo il pulsante "Mi piace" e le informazioni della pagina, senza i volti individuali. | SÌ | Vuoi mostrare che persone reali apprezzano la tua pagina, incoraggiando altri a unirsi. |
| **Mostra Stream** | Controlla se i post recenti dalla tua pagina Facebook vengono visualizzati all'interno del Like Box. | *Se abilitato (SÌ):* I tuoi ultimi post di Facebook scorreranno all'interno del Like Box, fornendo contenuti freschi. *Se disabilitato (NO):* Saranno visibili solo la copertina della pagina, il profilo e il pulsante "Mi piace", rendendo la casella più compatta. | SÌ | Pubblichi frequentemente aggiornamenti su Facebook e vuoi condividerli direttamente sul tuo negozio. |
| **Mostra Intestazione** | Controlla se l'intestazione "Facebook" viene mostrata nella parte superiore del Like Box. | *Se abilitato (SÌ):* Un piccolo titolo "Facebook" apparirà nella parte superiore del widget. *Se disabilitato (NO):* L'intestazione sarà nascosta, rendendo il widget più pulito e integrato. | NO | Preferisci un aspetto minimalista per il Like Box e non hai bisogno dell'intestazione esplicita "Facebook". |
| **Intestazione Piccola** | Utilizza una versione più piccola dell'intestazione. | *Se abilitato (SÌ):* L'intestazione sarà più compatta. *Se disabilitato (NO):* Verrà utilizzata la dimensione standard dell'intestazione. | NO | Vuoi risparmiare spazio verticale nel tuo layout. |
| **Nascondi Copertina** | Nasconde la foto di copertina della tua pagina Facebook. | *Se abilitato (SÌ):* Saranno visibili solo l'immagine del profilo e il nome della tua pagina, rendendo il widget più compatto. *Se disabilitato (NO):* La foto di copertina della tua pagina Facebook verrà visualizzata nella parte superiore del widget. | NO | Hai uno spazio molto ristretto e vuoi dare priorità al pulsante "Mi piace" e ai post rispetto alla foto di copertina. |
| **Adatta alla larghezza del contenitore** | Consente al Like Box di regolare automaticamente la sua larghezza per adattarsi al contenitore genitore in cui è posizionato. | *Se abilitato (SÌ):* Il widget si ridimensionerà per riempire la larghezza disponibile, rendendolo reattivo. *Se disabilitato (NO):* Il widget si atterrà all'impostazione `Larghezza` specificata, potenzialmente causando overflow o spazio vuoto. | SÌ | Vuoi che il Like Box abbia un bell'aspetto su tutti i dispositivi e le dimensioni dello schermo senza regolazioni manuali. |
| **CSS Personalizzato** | Ti consente di aggiungere regole CSS personalizzate per stilizzare ulteriormente il Like Box. | *Se compilato con codice CSS:* I tuoi stili personalizzati verranno applicati, sovrascrivendo gli stili predefiniti. *Se vuoto:* Il modulo utilizzerà la sua stilizzazione predefinita o la stilizzazione predefinita di Facebook. | Lascia vuoto a meno che tu non abbia esigenze di stile specifiche. | Vuoi cambiare la dimensione del carattere o il colore del testo all'interno del Like Box per abbinarlo al tema del tuo marchio. |
| **Hook per visualizzare il modulo** | Seleziona dove nel tuo negozio apparirà il Like Box. | *Quando un hook è selezionato:* Il modulo renderà il suo contenuto in quella posizione specifica (es. `displayRightColumn`, `displayFooter`). *Quando nessun hook è selezionato:* Il modulo non sarà visibile nel tuo front office. | `displayRightColumn` o `displayLeftColumn` sono comuni, ma scegli in base al layout del tuo tema. | Vuoi che il Like Box sia visibile a lato delle tue schede prodotto, quindi scegli `displayRightColumn`. |
| **Colore di Sfondo** | Imposta il colore di sfondo del Like Box. | *Quando viene selezionato un colore:* Il Like Box avrà quel colore di sfondo. *Quando lasciato vuoto:* Il Like Box in genere erediterà il colore di sfondo del suo contenitore genitore o utilizzerà quello predefinito di Facebook. | Lascia vuoto o abbina il colore di sfondo del tuo tema. | Il tuo tema ha uno sfondo scuro e vuoi che il Like Box si integri, quindi imposti un colore di sfondo scuro. |
| **Colore Bordo** | Imposta il colore del bordo attorno al Like Box. | *Quando viene selezionato un colore:* Il Like Box avrà un bordo di quel colore. *Quando lasciato vuoto:* Il Like Box in genere non avrà bordo o un bordo predefinito di Facebook. | Lascia vuoto o abbina i colori del bordo del tuo tema. | Vuoi un sottile bordo grigio attorno al Like Box per separarlo dagli altri contenuti. |

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | URL Pagina Facebook | Il tuo URL Pagina Facebook | Collega il widget alla tua specifica pagina Facebook. |
| Configurazione Modulo | ID App (Facebook) | Vuoto (se non richiesto) | Il tuo ID App Facebook per l'integrazione API. |
| Configurazione Modulo | Larghezza | Vuoto (Reattivo) | Controlla la larghezza del widget; vuoto per la regolazione automatica. |
| Configurazione Modulo | Altezza | Vuoto (Reattivo) | Controlla l'altezza del widget; vuoto per la regolazione automatica. |
| Configurazione Modulo | Mostra Volti | SÌ | Visualizza le immagini del profilo dei "Mi piace" per la prova sociale. |
| Configurazione Modulo | Mostra Stream | SÌ | Visualizza i post recenti dalla tua pagina Facebook. |
| Configurazione Modulo | Mostra Intestazione | NO | Nasconde il titolo "Facebook" per un aspetto più pulito. |
| Configurazione Modulo | Intestazione Piccola | NO | Utilizza un'intestazione più piccola se `Mostra Intestazione` è SÌ. |
| Configurazione Modulo | Nascondi Copertina | NO | Mostra la foto di copertina della tua pagina Facebook. |
| Configurazione Modulo | Adatta alla larghezza del contenitore | SÌ | Assicura che il widget sia reattivo al suo contenitore genitore. |
| Configurazione Modulo | CSS Personalizzato | Vuoto | Consente una stilizzazione avanzata con regole CSS personalizzate. |
| Configurazione Modulo | Hook per visualizzare il modulo | `displayRightColumn` (o colonna pertinente) | Determina dove appare il modulo nel tuo negozio. |
| Configurazione Modulo | Colore di Sfondo | Vuoto | Imposta il colore di sfondo del widget. |
| Configurazione Modulo | Colore Bordo | Vuoto | Imposta il colore del bordo del widget. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il Facebook Like Box non viene visualizzato nel mio negozio. Cosa devo fare?**
R1:

-   **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Facebook Like Box" sia installato e abilitato.
-   **Verifica la selezione dell'hook:** Nella configurazione del modulo, assicurati di aver selezionato un "Hook per visualizzare il modulo" (es. `displayRightColumn`, `displayFooter`). Se il tuo tema non renderizza l'hook selezionato, non apparirà. Prova un hook comune diverso.
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte, la cache di PrestaShop impedisce ai nuovi moduli di apparire immediatamente.
-   **URL Pagina Facebook:** Ricontrolla che l'"URL Pagina Facebook" nella configurazione del modulo sia corretto e accessibile.

**D2: Il Like Box appare troppo largo/stretto o non si adatta correttamente al mio tema.**
R2:

-   **Impostazioni reattive:** Nella configurazione del modulo, assicurati che "Adatta alla larghezza del contenitore" sia impostato su SÌ e lascia vuoti i campi "Larghezza" e "Altezza". Questo consente a Facebook di gestire la reattività.
-   **Conflitti con il tema:** Il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo. Se hai familiarità con il CSS, usa gli strumenti per sviluppatori del tuo browser (F12) per ispezionare l'elemento e vedere quali regole CSS vengono applicate.
-   **CSS personalizzato:** Utilizza il campo "CSS Personalizzato" nella configurazione del modulo per aggiungere regole specifiche per regolare le sue dimensioni o l'aspetto, se necessario. Ad esempio: `.fb_iframe_widget { max-width: 100% !important; }`.

**D3: Il Like Box mostra un errore o non carica il contenuto dalla mia pagina Facebook.**
R3:

-   **URL corretto:** Verifica che l'"URL Pagina Facebook" sia assolutamente corretto e punti a una pagina Facebook pubblica (non un profilo personale o un gruppo).
-   **Problemi API di Facebook:** Occasionalmente, l'API di Facebook potrebbe riscontrare problemi temporanei. Attendi un po' e controlla di nuovo.
-   **Restrizioni della pagina:** Assicurati che la tua pagina Facebook non abbia restrizioni di paese o di età che potrebbero impedire al widget di caricarsi per tutti i visitatori.

:::caution
\*\*Errore "App non configurata" (Modulo versione 1.8 e successive)\*\*
Se riscontri un errore "App non configurata", specialmente con la versione del modulo 1.8 o superiore, che supporta l'API Facebook Graph v18.0:
1.  \*\*Inserisci il tuo ID App Facebook:\*\* Assicurati di aver inserito correttamente il tuo ID App Facebook nel campo di configurazione del modulo.
2.  \*\*Verifica le impostazioni del dominio su Facebook:\*\* Accedi al tuo account sviluppatore Facebook ([developers.facebook.com](https://developers.facebook.com/)). Naviga nelle impostazioni della tua app e conferma che il dominio del tuo negozio (es. `iltuonegozio.com`) sia correttamente aggiunto e verificato nelle impostazioni dell'app.
:::

**D4: Posso avere più Facebook Like Box su pagine diverse?**
R4: Questo modulo è progettato per visualizzare un Facebook Like Box configurato globalmente. Se hai bisogno di più Like Box distinti (ad esempio, per diverse pagine Facebook o con impostazioni diverse), dovresti tipicamente installare il modulo più volte (se supportato dal sistema di moduli di PrestaShop, cosa rara per i moduli a istanza singola) o utilizzare codice personalizzato. Per questo modulo specifico, è generalmente una singola istanza, una singola configurazione.

**D5: Come traduco il testo all'interno del Like Box (ad esempio, "Mi piace alla pagina")?**
R5: Il testo all'interno del Facebook Like Box stesso (come "Mi piace alla pagina", "Segui", "Condividi") è controllato da Facebook in base alle impostazioni della lingua del browser dell'utente e alla localizzazione di Facebook. Questo modulo non traduce direttamente questi elementi. Qualsiasi testo *attorno* al Like Box che aggiungi nel tuo tema o in altri moduli sarebbe traducibile tramite il sistema di traduzione di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Facebook Like Box (`likebox`) è un modulo PrestaShop standard che segue un modello MVC di base. Utilizza principalmente la classe `Module` per l'installazione, la disinstallazione e la gestione della configurazione. La funzionalità principale consiste nel renderizzare un template Smarty che incorpora il Facebook Page Plugin (precedentemente Like Box) utilizzando l'SDK JavaScript ufficiale di Facebook. Le impostazioni di configurazione sono memorizzate in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office Admin personalizzati. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate né estende `ObjectModel`. Tutta la logica è contenuta nel file principale del modulo (`likebox/ar.php`).

### 4.4 Risorse JavaScript (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**
    *   **Ambito:** Back-office (Pagina di configurazione amministrativa)
    *   **Scopo:** Questa è una libreria JavaScript di terze parti che fornisce una funzionalità di selezione colori. Viene utilizzata nella pagina di configurazione del modulo per consentire al commerciante di selezionare visivamente le impostazioni "Colore di Sfondo" e "Colore Bordo".
    *   **Interazione:** Si lega a specifici campi di input (probabilmente con una classe come `jscolor`) per aprire una palette di selezione colori.
-   **`likebox/script.js`**
    *   **Ambito:** Back-office (Pagina di configurazione amministrativa)
    *   **Scopo:** Questo script gestisce gli aggiornamenti dinamici e la funzionalità di anteprima dal vivo nella pagina di configurazione del modulo. Prende le impostazioni di input del commerciante (URL Pagina Facebook, larghezza, altezza, mostra volti, ecc.) e aggiorna dinamicamente un `<iframe>` o un'area di anteprima per mostrare come apparirà il Facebook Like Box.
    *   **Interazione:**
        *   Ascolta gli eventi `change` e `keyup` su vari campi di input (es. `#facebook_page_url`, `#width`, `#height`, checkbox).
        *   Costruisce i parametri URL del Facebook Page Plugin in base alle impostazioni correnti.
        *   Aggiorna l'attributo `src` di un `<iframe>` di anteprima o genera dinamicamente il codice di incorporamento dell'SDK di Facebook per riflettere le modifiche in tempo reale.
        *   Probabilmente utilizza `jscolor.js` per ottenere i valori di colore per sfondo e bordo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`likebox/css.css`**
    *   **Ambito:** Back-office (Pagina di configurazione amministrativa)
    *   **Scopo:** Fornisce lo stile per il modulo di configurazione del modulo nel Back Office di PrestaShop. Questo potrebbe includere regolazioni del layout, stile dei campi di input o stile per l'area di anteprima dal vivo.
    *   **Selettori chiave:** Probabilmente si rivolge agli elementi all'interno dell'output di `getContent()`, come gruppi di moduli, etichette e il contenitore di anteprima.
-   **`likebox/css/css.css`**
    *   **Ambito:** Front-office (Negozio rivolto al cliente)
    *   **Scopo:** Fornisce uno stile minimo per il widget Facebook Like Box stesso, principalmente per garantire che si integri bene con il layout del negozio. Questo potrebbe includere padding, margini predefiniti o regolazioni reattive di base.
    *   **Selettori chiave:** Si rivolge all'elemento contenitore in cui è incorporato il widget di Facebook (ad esempio, `.facebook_like_box_container`) e potenzialmente applica `max-width: 100%` per la reattività. Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` o `theme.css` del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

I template del modulo si trovano direttamente nella directory principale del modulo.

-   **`likebox/header.tpl`**
    *   **Ambito:** Front-office
    *   **Hook:** `displayHeader`
    *   **Scopo:** Questo template è progettato per essere agganciato a `displayHeader`. Il suo ruolo principale è includere l'SDK JavaScript di Facebook, necessario affinché il Facebook Page Plugin venga renderizzato correttamente. Contiene anche l'elemento `div` dove il Like Box verrà renderizzato dall'SDK.
    *   **Output:**

        ```
        <div id="fb-root"></div><script> (function(d, s, id) { var js, fjs = d.getElementsByTagName(s)[0]; if (d.getElementById(id)) return; js = d.createElement(s); js.id = id; js.src = "//connect.facebook.net/en\_US/sdk.js#xfbml=1&version=v2.8&appId={$app\_id}"; // La versione potrebbe variare, appId aggiunto fjs.parentNode.insertBefore(js, fjs); }(document, 'script', 'facebook-jssdk'));</script><div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div></div>
        ```

        (Nota: la versione effettiva dell'SDK e gli attributi dei dati potrebbero variare leggermente in base all'implementazione esatta del modulo e alle modifiche dell'API di Facebook.)
-   **`likebox/rightcolumn.tpl`**
    *   **Ambito:** Front-office
    *   **Hook:** `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayProductButtons`, ecc. (a seconda della configurazione del modulo)
    *   **Scopo:** Questo template funge da wrapper per il Facebook Like Box. È progettato per essere flessibile e può essere agganciato a varie posizioni. In genere include l'elemento `div` con la classe `fb-page` che l'SDK di Facebook trasformerà nel Like Box visivo.
    *   **Output:**

        ```
        <div class="block facebook\_like\_box\_container"> <h4>{l s='Seguici su Facebook' mod='likebox'}</h4> <div class="block\_content"> <div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div> </div> </div></div>
        ```

        Questo template include anche il titolo `<h4>` e la struttura `block_content` comuni per i blocchi di colonna di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Questo modulo non crea tabelle SQL personalizzate.
    *   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi tipicamente prefissate con `LIKEBOX_` (es. `LIKEBOX_FACEBOOK_PAGE_URL`, `LIKEBOX_WIDTH`, `LIKEBOX_HEIGHT`, `LIKEBOX_APP_ID`, ecc.).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di ogni pagina. | Utilizzato per includere l'SDK JavaScript di Facebook e il div `fb-root` iniziale, essenziale per il funzionamento del Like Box. |
| `displayLeftColumn` | Renderizza il contenuto nella colonna laterale sinistra. | Visualizza il widget Facebook Like Box nella colonna sinistra. |
| `displayRightColumn` | Renderizza il contenuto nella colonna laterale destra. | Visualizza il widget Facebook Like Box nella colonna destra. |
| `displayFooter` | Renderizza il contenuto nella sezione del piè di pagina del negozio. | Visualizza il widget Facebook Like Box nel piè di pagina. |
| `displayHome` | Renderizza il contenuto nella homepage. | Visualizza il widget Facebook Like Box nella homepage. |
| `displayProductButtons` | Renderizza il contenuto vicino ai pulsanti di azione del prodotto nella pagina del prodotto. | Visualizza il widget Facebook Like Box nelle pagine dei prodotti. |
| `displayProductExtraContent` | Renderizza contenuto aggiuntivo nella pagina del prodotto, spesso in una scheda o sotto il contenuto principale. | Visualizza il widget Facebook Like Box nelle pagine dei prodotti. |
| `displayMyAccountBlock` | Renderizza il contenuto nel blocco "Il mio account" del cliente. | Visualizza il widget Facebook Like Box nell'area dell'account cliente (meno comune per questo modulo). |
| `displayMyAccountBlockfooter` | Renderizza il contenuto nel piè di pagina del blocco "Il mio account". | Visualizza il widget Facebook Like Box nell'area dell'account cliente. |

(Nota: il metodo `install()` del modulo registra questi hook, e i metodi `hook<NomeHook>()` in `ar.php` sono responsabili del rendering di `rightcolumn.tpl` o `header.tpl` in base all'hook.)

## 5. Supporto ufficiale e aggiornamenti

Per le ultime versioni, gli aggiornamenti e il supporto dedicato per il modulo Facebook Like Box, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere.
