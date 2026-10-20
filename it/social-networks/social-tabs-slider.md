---
title: "Social tabs slider - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Social tabs slider di MyPresta.eu."
sidebar:
  label: "Social tabs slider - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Social tabs slider su MyPresta.eu](https://mypresta.eu/modules/social-networks/social-tabs-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/social-tabs-slider/)
>
> ---


# Social tabs slider

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e garantiscono una corretta comunicazione con le API dei social media.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale dove imposterai tutte le opzioni per il tuo Social tabs slider.

#### Impostazioni Generali

-   **Template:**

    -   **Cosa fa questa impostazione:** Ti permette di scegliere lo stile visivo e il design delle tue schede social. Il modulo viene fornito con diversi template predefiniti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su Template 1, 2, 3, ecc.:* L'aspetto delle icone social, il design della scheda e potenzialmente lo stile di animazione cambieranno nel tuo front office.
    -   **Valore consigliato:** Sperimenta per trovare quello che meglio si adatta al tema del tuo negozio.
    -   **Scenario / esempio per il commerciante:** Se il tuo negozio ha un design minimalista, potresti scegliere un template con icone pulite e piatte. Se preferisci un look più vivace, un altro template potrebbe offrire icone colorate e lucide.
-   **Posizione:**

    -   **Cosa fa questa impostazione:** Determina dove apparirà lo slider delle schede social sul tuo sito web.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Sinistra":* Lo slider sarà fissato sul lato sinistro della finestra del browser.
        -   *Quando impostato su "Destra":* Lo slider sarà fissato sul lato destro della finestra del browser.
    -   **Valore consigliato:** "Sinistra" o "Destra" a seconda del layout del tuo tema e di dove causa meno interferenze con altri elementi.
    -   **Scenario / esempio per il commerciante:** Se il tuo tema ha una barra laterale sinistra, potresti scegliere "Destra" per evitare l'ingombro. Se il tuo tema è ampio e centrato, sia "Sinistra" che "Destra" potrebbero funzionare bene.
-   **Ultima scheda aperta per impostazione predefinita:**

    -   **Cosa fa questa impostazione:** Controlla se una delle schede social deve aprirsi automaticamente quando un visitatore arriva per la prima volta sulla tua pagina.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "SÌ":* L'ultima scheda social che è stata aperta da un visitatore precedente (o una predefinita se non c'è cronologia) si aprirà automaticamente quando arriva un nuovo visitatore.
        -   *Quando impostato su "NO":* Tutte le schede social rimarranno chiuse finché il visitatore non cliccherà o passerà attivamente il mouse su una di esse.
    -   **Valore consigliato:** "NO" per evitare di infastidire potenzialmente i visitatori con una scheda che si apre automaticamente.
    -   **Scenario / esempio per il commerciante:** Potresti impostarlo su "SÌ" temporaneamente se stai conducendo una campagna speciale su un social network e vuoi attirare immediatamente l'attenzione su di essa, ma in generale, "NO" offre una migliore esperienza utente.

#### Impostazioni Facebook Like Box

-   **Visualizza Facebook Like Box:**

    -   **Cosa fa questa impostazione:** Attiva/disattiva la visibilità della scheda Facebook e della sua Like Box incorporata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* La scheda Facebook apparirà nello slider e, quando aperta, visualizzerà la tua Facebook Fan Page Like Box.
        -   *Quando disabilitato (NO):* La scheda Facebook non verrà mostrata nello slider.
    -   **Valore consigliato:** "SÌ" se hai una pagina Facebook attiva che vuoi promuovere.
    -   **Scenario / esempio per il commerciante:** Se Facebook è un canale primario per l'interazione con i clienti e il marketing, vorrai sicuramente abilitarlo.
-   **Altezza Facebook Like Box:**

    -   **Cosa fa questa impostazione:** Imposta la dimensione verticale dell'area del contenuto della Facebook Like Box quando la scheda è aperta.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un valore più alto (es. 500px):* Più contenuto (post, volti) dalla tua pagina Facebook sarà visibile all'interno della scheda.
        -   *Quando impostato su un valore più basso (es. 200px):* Meno contenuto sarà visibile, richiedendo lo scorrimento se il feed è lungo.
    -   **Valore consigliato:** Inizia con `280px` e regola in base a quanto contenuto vuoi mostrare e a come appare sul tuo sito.
    -   **Scenario / esempio per il commerciante:** Se pubblichi frequentemente e vuoi che i visitatori vedano più della tua attività recente, aumenta l'altezza.
-   **Schema colori Facebook Like Box:**

    -   **Cosa fa questa impostazione:** Cambia il tema colore della Facebook Like Box stessa (non l'icona della scheda).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Chiaro":* Lo sfondo e il testo della Like Box utilizzeranno colori più chiari.
        -   *Quando impostato su "Scuro":* Lo sfondo e il testo della Like Box utilizzeranno colori più scuri.
    -   **Valore consigliato:** Scegli "Chiaro" o "Scuro" per abbinare al meglio il design generale del tuo negozio.
    -   **Scenario / esempio per il commerciante:** Se il tuo sito web ha uno sfondo scuro, uno schema colori "Scuro" per la Like Box potrebbe integrarsi meglio visivamente.
-   **Facebook Like Box Mostra volti:**

    -   **Cosa fa questa impostazione:** Determina se le immagini del profilo delle persone che mettono "Mi piace" alla tua pagina vengono visualizzate nella Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Verrà mostrata una riga di immagini del profilo dei fan della tua pagina.
        -   *Quando disabilitato (NO):* Le immagini del profilo non verranno visualizzate.
    -   **Valore consigliato:** "SÌ" in quanto aggiunge un elemento di prova sociale, mostrando che persone reali apprezzano la tua pagina.
    -   **Scenario / esempio per il commerciante:** Mostrare i volti può incoraggiare altri a mettere "Mi piace" alla tua pagina, in quanto dimostra popolarità.
-   **Colore bordo Facebook Like Box:**

    -   **Cosa fa questa impostazione:** Imposta il colore del bordo attorno alla Facebook Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un colore specifico (es. #CCCCCC):* Il bordo apparirà in quel colore.
    -   **Valore consigliato:** Un colore che si abbina al design del tuo sito web o è trasparente/invisibile se preferisci.
    -   **Scenario / esempio per il commerciante:** Potresti usare il colore primario del tuo brand per il bordo per rafforzare il branding.
-   **Facebook Like Box Mostra flusso:**

    -   **Cosa fa questa impostazione:** Controlla se i tuoi post recenti di Facebook (il "flusso") vengono visualizzati all'interno della Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* I tuoi ultimi post di Facebook saranno visibili nella scheda.
        -   *Quando disabilitato (NO):* Verrà mostrato solo il pulsante "Mi piace" e potenzialmente i volti, senza il flusso di post.
    -   **Valore consigliato:** "SÌ" per fornire contenuti freschi e incoraggiare l'engagement.
    -   **Scenario / esempio per il commerciante:** Se condividi regolarmente notizie, promozioni o aggiornamenti di prodotti su Facebook, mostrare il flusso mantiene i visitatori informati.
-   **Facebook Like Box Mostra intestazione:**

    -   **Cosa fa questa impostazione:** Attiva/disattiva la visibilità dell'intestazione "Trovaci su Facebook" nella parte superiore della Like Box.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* L'intestazione verrà visualizzata.
        -   *Quando disabilitato (NO):* L'intestazione verrà nascosta, rendendo la Like Box più compatta.
    -   **Valore consigliato:** "SÌ" per chiarezza, o "NO" se desideri un aspetto più pulito e presumi che gli utenti capiscano che si tratta di Facebook.
    -   **Scenario / esempio per il commerciante:** Se lo spazio è limitato, nascondere l'intestazione può risparmiare spazio verticale.
-   **URL pagina fan di Facebook:**

    -   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale per Facebook. Devi inserire l'URL completo della tua pagina fan di Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserito correttamente:* La scheda Facebook visualizzerà la Like Box per la pagina specificata.
        -   *Quando errato o vuoto:* La scheda Facebook potrebbe non essere visualizzata correttamente o mostrerà un errore.
    -   **Valore consigliato:** L'URL esatto della tua pagina fan di Facebook (es. `https://www.facebook.com/MyPresta`).
    -   **Scenario / esempio per il commerciante:** Copia e incolla l'URL direttamente dal tuo browser quando visualizzi la tua pagina Facebook per garantirne l'accuratezza.

#### Impostazioni Google+

-   **Visualizza Google+ Follow:**

    -   **Cosa fa questa impostazione:** Attiva/disattiva la visibilità della scheda Google+ e del suo pulsante/profilo di follow incorporato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* La scheda Google+ apparirà nello slider.
        -   *Quando disabilitato (NO):* La scheda Google+ non verrà mostrata.
    -   **Valore consigliato:** "SÌ" se utilizzi attivamente Google+ (anche se il suo utilizzo è diminuito, potrebbe essere ancora rilevante per alcune nicchie).
    -   **Scenario / esempio per il commerciante:** Se la tua attività ha una forte presenza su Google My Business o specifiche strategie SEO locali che coinvolgono Google+, questo può essere vantaggioso.
-   **ID profilo Google+:**

    -   **Cosa fa questa impostazione:** Devi fornire il tuo ID profilo Google+ (una stringa numerica) affinché il modulo visualizzi il profilo corretto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserito correttamente:* La scheda Google+ visualizzerà il pulsante di follow/profilo per l'ID specificato.
        -   *Quando errato o vuoto:* La scheda Google+ potrebbe non essere visualizzata correttamente.
    -   **Valore consigliato:** Il tuo ID profilo Google+.
    -   **Scenario / esempio per il commerciante:** Trova il tuo ID Google+ navigando alla pagina del tuo profilo Google+ e guardando l'URL (di solito è una lunga stringa di numeri).

#### Impostazioni Twitter

-   **Visualizza timeline utente Twitter:**

    -   **Cosa fa questa impostazione:** Attiva/disattiva la visibilità della scheda Twitter e del suo widget di timeline utente incorporato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* La scheda Twitter apparirà nello slider, mostrando i tuoi tweet recenti.
        -   *Quando disabilitato (NO):* La scheda Twitter non verrà mostrata.
    -   **Valore consigliato:** "SÌ" se hai un account Twitter attivo per la tua attività.
    -   **Scenario / esempio per il commerciante:** Se usi Twitter per il servizio clienti, annunci o vendite flash, questo è un ottimo modo per tenere aggiornati i visitatori.
-   **Nome utente Twitter:**

    -   **Cosa fa questa impostazione:** Specifica l'account Twitter la cui timeline verrà visualizzata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserito correttamente (es. MyPresta):* La scheda Twitter mostrerà i tweet di quel nome utente.
        -   *Quando errato o vuoto:* La scheda Twitter potrebbe non essere visualizzata correttamente.
    -   **Valore consigliato:** Il tuo nome utente Twitter (senza il simbolo "@").
    -   **Scenario / esempio per il commerciante:** Inserisci `MyPresta` se il tuo handle Twitter è `@MyPresta`.
-   **ID widget Twitter:**

    -   **Cosa fa questa impostazione:** Questo è un ID univoco generato da Twitter quando crei un widget di timeline incorporato. È fondamentale per il funzionamento del widget.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserito correttamente:* La timeline di Twitter si caricherà e verrà visualizzata correttamente.
        -   *Quando errato o vuoto:* La scheda Twitter probabilmente mostrerà un errore o rimarrà vuota.
    -   **Valore consigliato:** Il tuo ID widget Twitter.
    -   **Scenario / esempio per il commerciante:** Per ottenerlo, vai su [Twitter Publish](https://publish.twitter.com/), seleziona "Embedded Timeline", inserisci l'URL del tuo profilo e copia il `data-widget-id` dal codice generato.

#### Impostazioni YouTube

-   **Visualizza account YouTube:**

    -   **Cosa fa questa impostazione:** Attiva/disattiva la visibilità della scheda YouTube e del suo feed di canale/utente incorporato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* La scheda YouTube apparirà nello slider.
        -   *Quando disabilitato (NO):* La scheda YouTube non verrà mostrata.
    -   **Valore consigliato:** "SÌ" se hai un canale YouTube con video di prodotti, tutorial o contenuti del brand.
    -   **Scenario / esempio per il commerciante:** Se vendi prodotti che beneficiano di dimostrazioni video, questo è un ottimo modo per mostrarli.
-   **Nome utente YouTube:**

    -   **Cosa fa questa impostazione:** Specifica il canale o l'utente YouTube i cui video verranno visualizzati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserito correttamente:* La scheda YouTube visualizzerà i contenuti di quel canale/utente.
        -   *Quando errato o vuoto:* La scheda YouTube potrebbe non essere visualizzata correttamente.
    -   **Valore consigliato:** Il nome URL personalizzato del tuo canale YouTube o il nome utente legacy.
    -   **Scenario / esempio per il commerciante:** Se l'URL del tuo canale YouTube è `youtube.com/user/MyPrestaVideos`, il tuo nome utente sarebbe `MyPrestaVideos`. Se è `youtube.com/c/MyPresta`, potresti dover trovare il nome utente legacy o l'ID del canale.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Template** | (Scegli il più adatto) | Cambia lo stile visivo delle schede social. |
| | **Posizione** | Destra | Determina se le schede appaiono sul lato sinistro o destro del browser. |
| | **Ultima scheda aperta per impostazione predefinita** | NO | Controlla se una scheda si apre automaticamente al caricamento della pagina. |
| | **Visualizza Facebook Like Box** | SÌ | Mostra/nasconde la scheda Facebook. |
| | **Altezza Facebook Like Box** | 280px | Imposta l'altezza dell'area del contenuto di Facebook. |
| | **Schema colori Facebook Like Box** | Chiaro | Cambia il tema colore della Facebook Like Box. |
| | **Facebook Like Box Mostra volti** | SÌ | Visualizza le immagini del profilo dei fan. |
| | **Colore bordo Facebook Like Box** | (vuoto/trasparente) | Imposta il colore del bordo della Like Box. |
| | **Facebook Like Box Mostra flusso** | SÌ | Visualizza i post recenti di Facebook. |
| | **Facebook Like Box Mostra intestazione** | SÌ | Mostra/nasconde l'intestazione "Trovaci su Facebook". |
| | **URL pagina fan di Facebook** | (Il tuo URL Facebook) | **CRITICO:** URL della tua pagina fan di Facebook. |
| | **Visualizza Google+ Follow** | NO | Mostra/nasconde la scheda Google+. |
| | **ID profilo Google+** | (Il tuo ID Google+) | **CRITICO:** Il tuo ID numerico del profilo Google+. |
| | **Visualizza timeline utente Twitter** | SÌ | Mostra/nasconde la scheda Twitter. |
| | **Nome utente Twitter** | (Il tuo handle Twitter) | **CRITICO:** Il tuo nome utente Twitter (es. `MyPresta`). |
| | **ID widget Twitter** | (Il tuo ID widget Twitter) | **CRITICO:** ID univoco per il tuo widget di timeline Twitter. |
| | **Visualizza account YouTube** | SÌ | Mostra/nasconde la scheda YouTube. |
| | **Nome utente YouTube** | (Il tuo nome utente YouTube) | **CRITICO:** Il nome utente o l'ID legacy del tuo canale YouTube. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le schede social non appaiono nel mio negozio, o ne vengono mostrate solo alcune.**
**R1:**

-   **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Social tabs slider" sia installato e abilitato.
-   **Verifica la configurazione:** Vai alla pagina di configurazione del modulo. Assicurati che "Visualizza Facebook Like Box", "Visualizza Google+ Follow", ecc., siano impostati su "SÌ" per le schede che desideri mostrare.
-   **ID/URL corretti:** Ricontrolla che l'URL della tua pagina fan di Facebook, l'ID del profilo Google+, il nome utente/ID widget di Twitter e il nome utente di YouTube siano inseriti *esattamente* come richiesto. Un singolo errore di battitura impedirà il caricamento della scheda.
-   **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero avere problemi con gli hook del modulo. Prova a passare temporaneamente al tema PrestaShop predefinito per vedere se le schede appaiono. Se lo fanno, il tuo tema potrebbe richiedere piccole modifiche.
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, i vecchi file di cache impediscono la visualizzazione di nuovi contenuti del modulo.

**D2: La mia scheda Facebook/Twitter/YouTube mostra un errore o è vuota quando viene aperta.**
**R2:**

-   **ID/URL errati:** Questa è la ragione più comune. Ricontrolla ogni singolo carattere dell'URL della tua pagina fan di Facebook, dell'ID del profilo Google+, del nome utente di Twitter, dell'ID del widget di Twitter e del nome utente di YouTube. Anche una barra mancante o uno spazio extra possono causare problemi.
-   **Modifiche API:** Le piattaforme di social media aggiornano occasionalmente le loro API o i codici di incorporamento. Assicurati che la versione del tuo modulo sia aggiornata da MyPresta.eu.
-   **Impostazioni sulla privacy:** Assicurati che le tue pagine/profili social siano pubblici e accessibili. Se sono impostati su privati, il modulo non sarà in grado di visualizzare il loro contenuto.
-   **Problemi di rete:** Disabilita temporaneamente eventuali ad blocker o estensioni del browser che potrebbero interferire con i widget dei social media.

**D3: Le schede social appaiono strane o disallineate sul mio dispositivo mobile.**
**R3:**

-   **Reattività del tema:** Sebbene il modulo sia progettato per essere reattivo, il suo aspetto può essere influenzato dalla reattività complessiva del tema del tuo PrestaShop.
-   **Conflitti CSS:** Il CSS del tuo tema potrebbe sovrascrivere lo stile del modulo. Se hai un webmaster, può ispezionare gli elementi utilizzando gli strumenti di sviluppo del browser per identificare i conflitti.
-   **Template del modulo:** Prova a passare a un "Template" diverso nella configurazione del modulo per vedere se uno si adatta meglio al mobile.
-   **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione.

**D4: Come ottengo il mio ID widget Twitter?**
**R4:**

1.  Vai su [Twitter Publish](https://publish.twitter.com/).
2.  Seleziona "Embedded Timeline".
3.  Inserisci l'URL completo del tuo profilo Twitter (es. `https://twitter.com/MyPresta`).
4.  Clicca sulla freccia, quindi seleziona "Embedded Timeline".
5.  Twitter genererà un codice. Cerca `data-widget-id="YOUR_WIDGET_ID_HERE"` all'interno di quel codice. Copia solo l'ID numerico.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Social tabs slider" è un classico modulo PrestaShop implementato come un singolo file PHP (`socialslider.php`) seguendo la struttura del modulo PrestaShop. Sfrutta il sistema di hook di PrestaShop per iniettare il suo CSS, JavaScript e contenuto HTML nel front office. La configurazione è gestita tramite il metodo `getContent()` nella classe principale del modulo, memorizzando le impostazioni in `ps_configuration`. Il modulo utilizza librerie JavaScript esterne (jscolor) e script personalizzati per gestire l'animazione scorrevole e il caricamento dei widget dei social media.

### 4.2 Controller (`controllers/`)

Questo modulo **non** utilizza controller personalizzati per il Front-Office o il Back-Office Admin. Tutta la logica è incapsulata nel file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** definisce classi personalizzate né estende `ObjectModel`. Tutta la logica principale risiede all'interno della classe `Socialslider` in `socialslider.php`. I valori di configurazione sono memorizzati direttamente nella tabella `ps_configuration` utilizzando `Configuration::get()` e `Configuration::updateValue()`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include diversi file JavaScript per gestire la sua funzionalità:

-   `socialslider/jscolor/jscolor.js`
    -   **Ambito:** Back-office (utilizzato in `getContent()` per l'input del selettore colori).
    -   **Responsabilità:** Fornisce una funzionalità di selettore colori JavaScript per i campi di input, in particolare per l'impostazione del colore del bordo di Facebook.
-   `socialslider/left.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Contiene la logica JavaScript per l'animazione scorrevole e l'interazione delle schede quando lo slider è posizionato sul lato **sinistro** dello schermo. Gestisce l'apertura/chiusura delle schede, il caricamento dinamico dei contenuti dei social media e potenzialmente la gestione dei cookie per la funzione "ultima scheda aperta".
-   `socialslider/right.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Contiene la logica JavaScript per l'animazione scorrevole e l'interazione delle schede quando lo slider è posizionato sul lato **destro** dello schermo. Simile a `left.js` ma adattato per il posizionamento a destra.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo utilizza un approccio basato su template per la sua stilizzazione, con file CSS separati per ogni template e posizione.

-   `socialslider/templates/1/css/left.css`
    -   **Ambito:** Front-office (per Template 1, posizione Sinistra).
    -   **Responsabilità:** Definisce gli stili visivi per le schede social, le icone e il contenitore dello slider quando è selezionato il Template 1 e lo slider è a sinistra.
    -   **Selettori chiave:** `.socialslider_left`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
-   `socialslider/templates/1/css/right.css`
    -   **Ambito:** Front-office (per Template 1, posizione Destra).
    -   **Responsabilità:** Definisce gli stili visivi per le schede social, le icone e il contenitore dello slider quando è selezionato il Template 1 e lo slider è a destra.
    -   **Selettori chiave:** `.socialslider_right`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
-   `socialslider/templates/2/css/left.css`
    -   **Ambito:** Front-office (per Template 2, posizione Sinistra).
    -   **Responsabilità:** Stilizzazione per Template 2, posizione Sinistra.
-   `socialslider/templates/2/css/right.css`
    -   **Ambito:** Front-office (per Template 2, posizione Destra).
    -   **Responsabilità:** Stilizzazione per Template 2, posizione Destra.
-   `socialslider/templates/3/css/left.css`
    -   **Ambito:** Front-office (per Template 3, posizione Sinistra).
    -   **Responsabilità:** Stilizzazione per Template 3, posizione Sinistra.
-   `socialslider/templates/3/css/right.css`
    -   **Ambito:** Front-office (per Template 3, posizione Destra).
    -   **Responsabilità:** Stilizzazione per Template 3, posizione Destra.
-   `socialslider/templates/4/css/left.css`
    -   **Ambito:** Front-office (per Template 4, posizione Sinistra).
    -   **Responsabilità:** Stilizzazione per Template 4, posizione Sinistra.
-   `socialslider/templates/4/css/right.css`
    -   **Ambito:** Front-office (per Template 4, posizione Destra).
    -   **Responsabilità:** Stilizzazione per Template 4, posizione Destra.
-   `socialslider/templates/5/css/left.css`
    -   **Ambito:** Front-office (per Template 5, posizione Sinistra).
    -   **Responsabilità:** Stilizzazione per Template 5, posizione Sinistra.
-   `socialslider/templates/5/css/right.css`
    -   **Ambito:** Front-office (per Template 5, posizione Destra).
    -   **Responsabilità:** Stilizzazione per Template 5, posizione Destra.
-   `socialslider/templates/6/css/left.css`
    -   **Ambito:** Front-office (per Template 6, posizione Sinistra).
    -   **Responsabilità:** Stilizzazione per Template 6, posizione Sinistra.
-   `socialslider/templates/6/css/right.css`
    -   **Ambito:** Front-office (per Template 6, posizione Destra).
    -   **Responsabilità:** Stilizzazione per Template 6, posizione Destra.

Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` del loro tema o creando un tema figlio.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per il rendering del suo contenuto nel front-office e per il modulo di configurazione nel back-office.

-   **Template degli hook (`views/templates/hook/`)**:
    -   `socialslider/header.tpl`
        -   **Hook:** `displayHeader`
        -   **Output:** Questo template è responsabile dell'inclusione dei file CSS e JavaScript necessari in modo dinamico in base alla configurazione del modulo (ad esempio, caricando `left.js` o `right.js` e il CSS corretto specifico del template). Include anche gli SDK/widget di Facebook, Twitter e Google+ se abilitati.
    -   `socialslider/top.tpl`
        -   **Hook:** `displayTop`
        -   **Output:** Questo è il template principale che renderizza la struttura HTML dello slider delle schede social stesso. Genera gli elementi `div` per il contenitore dello slider, le singole schede (Facebook, Google+, Twitter, YouTube) e le rispettive aree di contenuto, popolandole con i valori di configurazione.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella standard di PrestaShop `ps_configuration`.

    -   `ps_configuration` (o `_configuration` con il tuo prefisso): Memorizza coppie chiave-valore per le impostazioni del modulo, ad esempio, `SS_TEMPLATE`, `SS_POSITION`, `SS_FCB_FANPAGEURL`.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS e JavaScript del modulo e gli SDK/script dei widget delle piattaforme di social media (SDK di Facebook, script del widget di Twitter, script di Google+). |
| `displayTop` | Tipicamente nella parte superiore dell'area del contenuto, sotto l'intestazione principale. | Renderizza la struttura HTML principale dello slider delle schede social (il contenitore fisso, le singole schede e le loro aree di contenuto). |
| `header` | (Alias per `displayHeader` in alcune versioni di PrestaShop, o utilizzato per temi più vecchi) | Come `displayHeader`, garantisce la compatibilità per l'iniezione di risorse. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto per sviluppatori per il modulo "Social tabs slider", si prega di fare riferimento al proprio account cliente MyPresta.eu. È possibile scaricare le ultime versioni e accedere alle risorse di supporto direttamente dalla cronologia degli ordini.
