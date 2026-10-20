---
title: "Widget per l'iscrizione al gruppo Facebook - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Facebook join to group widget' di MyPresta.eu."
sidebar:
  label: "Widget per l'iscrizione al gruppo Facebook - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook join to group widget su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-join-to-group-widget.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-join-to-group-widget/)
>
> ---


# Widget per l'iscrizione al gruppo Facebook

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale dove imposterai tutte le opzioni per il tuo widget "Facebook Join Group".

-   **Nome schermata e posizione nel menu:** Back Office > Moduli > Gestione moduli > "Facebook join to group widget" > Configura

#### Impostazioni e opzioni:

1.  **URL del gruppo** (Chiave di configurazione: `fbg_href`)

    -   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Definisce il link diretto al tuo gruppo Facebook. Quando i clienti cliccano sul pulsante "Unisciti al gruppo", verranno indirizzati a questo URL.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un URL di gruppo Facebook valido:* Il pulsante "Unisciti al gruppo" reindirizzerà correttamente gli utenti al gruppo specificato.
        -   *Se lasciato vuoto o impostato su un URL non valido:* Il pulsante potrebbe non funzionare, o potrebbe portare a una pagina di errore, frustrando i tuoi clienti.
    -   **Valore consigliato:** Fornisci sempre l'URL completo e corretto del tuo gruppo Facebook (es. `https://www.facebook.com/groups/ilnomedeltuogruppo/`).
    -   **Scenario/esempio per il commerciante:** Vuoi che i clienti si uniscano al tuo gruppo "Comunità del mio fantastico negozio". Incolleresti `https://www.facebook.com/groups/comunitadelmiofantasticonegozio/` qui.
2.  **Larghezza della casella** (Chiave di configurazione: `fbg_width`)

    -   **Cosa fa questa impostazione:** Controlla la larghezza della casella del widget "Facebook Join Group" sul tuo negozio. Puoi specificarla in pixel.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un valore in pixel specifico (es. `280`):* La casella tenterà di essere renderizzata a quella larghezza esatta.
        -   *Se lasciato vuoto o impostato su `0`:* Il modulo tenterà di regolare automaticamente la sua larghezza in base allo spazio disponibile nell'hook in cui è visualizzato, o utilizzerà un valore predefinito.
    -   **Valore consigliato:** Inizia con `280` o `300` pixel. Testa su diversi dispositivi. Se vuoi che riempia lo spazio disponibile in una colonna, potresti lasciarlo vuoto, ma sii consapevole che potrebbe estendersi troppo in alcuni hook.
    -   **Scenario/esempio per il commerciante:** Vuoi che il widget si adatti perfettamente alla tua colonna sinistra, che è larga 250px. Imposteresti questo valore a `250`.
3.  **Dove vuoi visualizzare la casella?** (Chiave di configurazione: `fbg_hook`)

    -   **Cosa fa questa impostazione:** Questo menu a tendina ti permette di selezionare la posizione specifica (hook di PrestaShop) dove il widget apparirà sul tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Selezionando `DisplayFooter`:* Il widget apparirà in fondo a ogni pagina.
        -   *Selezionando `DisplayHome`:* Il widget apparirà solo sulla tua homepage.
        -   *Selezionando `DisplayRightColumn`:* Il widget apparirà nella barra laterale destra sulle pagine che ne hanno una.
        -   *Selezionando qualsiasi altro hook:* Il widget apparirà in quella posizione specifica.
    -   **Valore consigliato:** Dipende interamente dal tuo tema e dalla tua strategia di marketing. `DisplayRightColumn` o `DisplayLeftColumn` sono comuni per i widget laterali. `DisplayFooter` è buono per un posizionamento meno invasivo. `DisplayHome` è ottimo per un'alta visibilità.
    -   **Scenario/esempio per il commerciante:** Vuoi che il widget sia visibile sulla maggior parte delle pagine ma non interferisca con il tuo contenuto principale. Scegli `DisplayRightColumn`.
4.  **Intestazione** (Chiave di configurazione: `fbg_header`)

    -   **Cosa fa questa impostazione:** Questo è il testo del titolo principale visualizzato nella parte superiore del tuo widget "Facebook Join Group".
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su "Unisciti alla nostra comunità":* Questo testo verrà visualizzato in modo prominente.
        -   *Se lasciato vuoto:* Non verrà visualizzato alcun testo di intestazione, rendendo il widget meno chiaro ai clienti.
    -   **Valore consigliato:** Un titolo chiaro e invitante come "Unisciti al nostro gruppo Facebook", "La nostra comunità" o "Connettiti con noi".
    -   **Scenario/esempio per il commerciante:** Vuoi dire chiaramente ai clienti di cosa tratta la casella. Lo imposti su "Unisciti al nostro gruppo Facebook esclusivo!".
5.  **Descrizione** (Chiave di configurazione: `fbg_desc`)

    -   **Cosa fa questa impostazione:** Fornisce un breve testo esplicativo sotto l'intestazione, dando ai clienti più contesto sul tuo gruppo Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su "Ricevi offerte esclusive e aggiornamenti!":* Questo messaggio apparirà sotto l'intestazione.
        -   *Se lasciato vuoto:* Il widget mostrerà solo l'intestazione e il pulsante, perdendo potenzialmente l'opportunità di attirare gli utenti.
    -   **Valore consigliato:** Una o due frasi brevi e accattivanti che spiegano i vantaggi dell'adesione (es. "Sii il primo a conoscere nuovi prodotti e offerte speciali!").
    -   **Scenario/esempio per il commerciante:** Vuoi incoraggiare le iscrizioni evidenziando i vantaggi. Lo imposti su "Accedi a sconti riservati ai membri, anteprime e connettiti con altri appassionati!".
6.  **Testo del pulsante** (Chiave di configurazione: `fbg_btn_text`)

    -   **Cosa fa questa impostazione:** Questo è il testo visualizzato sul pulsante che i clienti cliccano per unirsi al tuo gruppo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su "Unisciti al gruppo":* Questo testo apparirà sul pulsante.
        -   *Se lasciato vuoto:* Il pulsante potrebbe apparire vuoto o utilizzare un valore predefinito, il che è meno efficace.
    -   **Valore consigliato:** Una chiara call to action come "Unisciti al gruppo", "Unisciti ora" o "Connettiti su Facebook".
    -   **Scenario/esempio per il commerciante:** Vuoi una call to action diretta. Lo imposti su "Unisciti al nostro gruppo".
7.  **Colore del testo** (Chiave di configurazione: `fbg_text_color`)

    -   **Cosa fa questa impostazione:** Ti permette di impostare il colore del testo dell'intestazione e della descrizione all'interno del widget.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su `#000000` (nero):* Il testo apparirà nero.
        -   *Se impostato su `#FFFFFF` (bianco):* Il testo apparirà bianco.
    -   **Valore consigliato:** Scegli un colore che contrasti bene con il colore di sfondo scelto e che si abbini alla palette di colori del tuo marchio. Usa un codice esadecimale (es. `#333333`).
    -   **Scenario/esempio per il commerciante:** Il tuo widget ha uno sfondo scuro. Imposti il colore del testo su `#FFFFFF` per la leggibilità.
8.  **Stile del bordo** (Chiave di configurazione: `fbg_border_style`)

    -   **Cosa fa questa impostazione:** Definisce lo stile visivo del bordo attorno alla casella del widget.
    -   **Effetto della modifica di questa impostazione:**
        -   *`solid` (solido):* Una linea singola e continua.
        -   *`dashed` (tratteggiato):* Una serie di linee corte.
        -   *`dotted` (puntinato):* Una serie di punti.
        -   *`none` (nessuno):* Non verrà visualizzato alcun bordo.
    -   **Valore consigliato:** `solid` o `none` sono i più comuni. `solid` fornisce un confine chiaro.
    -   **Scenario/esempio per il commerciante:** Vuoi un contorno sottile per la casella. Scegli `solid`.
9.  **Colore del bordo** (Chiave di configurazione: `fbg_border_color`)

    -   **Cosa fa questa impostazione:** Imposta il colore del bordo attorno alla casella del widget.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su `#CCCCCC` (grigio chiaro):* Il bordo sarà grigio chiaro.
        -   *Se impostato su `#FF0000` (rosso):* Il bordo sarà rosso.
    -   **Valore consigliato:** Un colore che si abbini al design del tuo negozio, spesso un grigio sottile o un colore accentuato del marchio. Usa un codice esadecimale.
    -   **Scenario/esempio per il commerciante:** Il tuo marchio utilizza una specifica tonalità di blu. Imposti il colore del bordo su `#007bff`.
10. **Dimensione del bordo** (Chiave di configurazione: `fbg_border_size`)

    -   **Cosa fa questa impostazione:** Determina lo spessore del bordo in pixel.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su `1`:* Apparirà un bordo sottile.
        -   *Se impostato su `5`:* Apparirà un bordo più spesso e prominente.
    -   **Valore consigliato:** `1` o `2` pixel per un bordo sottile.
    -   **Scenario/esempio per il commerciante:** Vuoi un bordo molto sottile. Imposti la dimensione su `1`.
11. **Raggio del bordo** (Chiave di configurazione: `fbg_border_radius`)

    -   **Cosa fa questa impostazione:** Controlla la rotondità degli angoli della casella del widget. Un valore più alto crea angoli più arrotondati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su `0`:* La casella avrà angoli netti e squadrati.
        -   *Se impostato su `10`:* Gli angoli saranno notevolmente arrotondati.
    -   **Valore consigliato:** `0` per angoli netti, da `3` a `5` per leggermente arrotondati, o `10+` per molto arrotondati, a seconda dell'estetica del tuo tema.
    -   **Scenario/esempio per il commerciante:** Il tuo tema utilizza elementi leggermente arrotondati. Imposti il raggio del bordo su `5`.
12. **Colore di sfondo** (Chiave di configurazione: `fbg_bg_color`)

    -   **Cosa fa questa impostazione:** Imposta il colore di sfondo principale della casella del widget.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su `#F0F2F5` (grigio chiaro, simile allo sfondo di Facebook):* Lo sfondo della casella sarà grigio chiaro.
        -   *Se impostato su `#FFFFFF` (bianco):* Lo sfondo della casella sarà bianco.
    -   **Valore consigliato:** Un colore che renda il testo leggibile e si adatti al design del tuo negozio. Usa un codice esadecimale.
    -   **Scenario/esempio per il commerciante:** Vuoi che il widget si distingua leggermente da uno sfondo di pagina bianco. Imposti il colore di sfondo su `#F8F8F8`.
13. **Sfumatura di sfondo** (Chiave di configurazione: `fbg_bg_gradient`)

    -   **Cosa fa questa impostazione:** Ti permette di aggiungere una sfumatura CSS allo sfondo della casella del widget, creando una transizione fluida tra due o più colori. Questo sovrascrive il singolo "Colore di sfondo" se utilizzato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su `linear-gradient(to right, #FFD700, #FFA500)`:* Lo sfondo passerà dall'oro all'arancione.
        -   *Se lasciato vuoto:* Verrà utilizzata l'impostazione "Colore di sfondo".
    -   **Valore consigliato:** Usa una stringa di sfumatura CSS se desideri uno sfondo più dinamico. Se non sei sicuro, lascialo vuoto e usa un singolo "Colore di sfondo".
    -   **Scenario/esempio per il commerciante:** Vuoi un aspetto sottile e moderno. Usi una sfumatura come `linear-gradient(to bottom, #e0eafc, #cfdef3)`.

#### Impostazioni nascoste/interne (per riferimento sviluppatori, non configurabili direttamente dal commerciante):

-   `mypresta_updates`, `update_`, `updatev_`: Chiavi interne per gli aggiornamenti del modulo e i controlli di versione.
-   `fbg_app`, `fbg_appid`: Queste chiavi suggeriscono un potenziale per l'integrazione con l'App di Facebook, ma non sono esposte nella configurazione attuale.
-   `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Impostazioni core di PrestaShop relative alla gestione delle lingue nel back office.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **URL del gruppo** | Il tuo URL del gruppo Facebook | Link diretto al tuo gruppo Facebook per il pulsante "Unisciti al gruppo". **CRITICO!** |
| Configurazione modulo | **Larghezza della casella** | `280` o `300`px | Imposta la larghezza della casella del widget. Lascia vuoto per l'auto-regolazione. |
| Configurazione modulo | **Dove vuoi visualizzare la casella?** | `DisplayRightColumn` o `DisplayFooter` | Seleziona l'hook di PrestaShop dove appare il widget. |
| Configurazione modulo | **Intestazione** | "Unisciti al nostro gruppo Facebook" | Testo del titolo principale per il widget. |
| Configurazione modulo | **Descrizione** | "Ricevi offerte esclusive e aggiornamenti!" | Breve testo esplicativo sotto l'intestazione. |
| Configurazione modulo | **Testo del pulsante** | "Unisciti al gruppo" | Testo visualizzato sul pulsante di azione. |
| Configurazione modulo | **Colore del testo** | `#333333` (grigio scuro) | Colore del testo dell'intestazione e della descrizione. Usa il codice esadecimale. |
| Configurazione modulo | **Stile del bordo** | `solid` o `none` | Stile visivo del bordo della casella (solido, tratteggiato, puntinato, nessuno). |
| Configurazione modulo | **Colore del bordo** | `#CCCCCC` (grigio chiaro) | Colore del bordo della casella. Usa il codice esadecimale. |
| Configurazione modulo | **Dimensione del bordo** | `1` o `2`px | Spessore del bordo della casella. |
| Configurazione modulo | **Raggio del bordo** | `0` o `5`px | Rotondità degli angoli della casella. |
| Configurazione modulo | **Colore di sfondo** | `#F0F2F5` (grigio chiaro) | Colore di sfondo principale della casella del widget. Usa il codice esadecimale. |
| Configurazione modulo | **Sfumatura di sfondo** | Lascia vuoto | Sfumatura CSS per lo sfondo. Sovrascrive il `Colore di sfondo` se impostato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

1.  **Il widget non viene visualizzato nel mio negozio.**

    -   **Controllo 1:** Vai su **Moduli > Gestione moduli**, cerca "Facebook join to group widget" e assicurati che sia installato e abilitato.
    -   **Controllo 2:** Nella configurazione del modulo, verifica di aver selezionato un'opzione per "Dove vuoi visualizzare la casella?" (hook). Assicurati che l'hook selezionato esista effettivamente e sia attivo nel tuo tema attuale. Alcuni temi potrebbero non utilizzare tutti gli hook standard di PrestaShop.
    -   **Controllo 3:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**). A volte, le modifiche non appaiono finché la cache non viene aggiornata.
    -   **Controllo 4:** Se hai un tema personalizzato, potrebbe sovrascrivere le visualizzazioni degli hook standard. Contatta lo sviluppatore del tuo tema o un webmaster.
2.  **Il pulsante "Unisciti al gruppo" non funziona o porta a un errore.**

    -   **Controllo:** Vai alla configurazione del modulo e reinserisci attentamente il tuo "URL del gruppo". Assicurati che sia l'URL completo e corretto del tuo gruppo Facebook (es. `https://www.facebook.com/groups/ilnomedeltuogruppo/`). Testa l'URL direttamente nel tuo browser per confermare che funzioni.
3.  **Il widget appare strano o non si adatta al design del mio tema.**

    -   **Controllo 1:** Regola l'impostazione "Larghezza della casella". Se è troppo larga per una colonna, potrebbe rompere il layout. Prova un valore in pixel più piccolo.
    -   **Controllo 2:** Usa le impostazioni "Colore del testo", "Stile del bordo", "Colore del bordo", "Dimensione del bordo", "Raggio del bordo", "Colore di sfondo" e "Sfumatura di sfondo" per abbinare i colori e gli stili del tuo tema.
    -   **Controllo 3:** Svuota la cache di PrestaShop dopo aver apportato modifiche di stile.
    -   **Controllo 4:** Se il problema persiste, potrebbe trattarsi di un conflitto CSS con il tuo tema. Un webmaster può ispezionare il CSS del tuo sito per identificare e risolvere i conflitti.
4.  **Posso visualizzare il widget in più posizioni?**

    -   La versione attuale del modulo ti consente di selezionare un solo hook dal menu a tendina. Se hai bisogno di visualizzarlo in più posizioni, dovresti duplicare il modulo (il che richiede l'intervento di uno sviluppatore) o utilizzare una soluzione personalizzata.
5.  **Il mio testo non viene visualizzato nella lingua corretta.**

    -   I campi "Intestazione", "Descrizione" e "Testo del pulsante" sono tipicamente traducibili se la tua installazione di PrestaShop supporta più lingue per le configurazioni dei moduli. Assicurati di modificare la configurazione del modulo nel contesto linguistico corretto nel Back Office (controlla il menu a tendina della lingua in alto a destra nel tuo pannello di amministrazione).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Facebook join to group widget" è un modulo PrestaShop semplice che segue un modello di tipo MVC di base inerente alla struttura dei moduli di PrestaShop. Utilizza principalmente la classe `Module` per la sua funzionalità principale, la gestione della configurazione e la registrazione degli hook. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file del modulo principale, memorizzando le impostazioni in `ps_configuration`. La visualizzazione nel front-office è gestita tramite template Smarty renderizzati tramite hook registrati. Non ci sono controller personalizzati o ObjectModels.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Tutto il rendering del front-office è gestito direttamente tramite i metodi `hook` all'interno del file del modulo principale `fbgroup.php`, che poi renderizzano i template Smarty.
-   **Controller Admin Back-Office**: Nessuno. Tutta l'amministrazione è gestita tramite il metodo `getContent()` della classe del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

-   **`fbgroup/fbgroup.php` (Classe del modulo principale)**
    -   **Nome classe:** `Fbgroup`
    -   **Classe padre:** `Module`
    -   **Responsabilità:**
        -   Installazione (`install()`) e disinstallazione (`uninstall()`) del modulo.
        -   Registrazione di tutti gli hook specificati (`registerHook()`).
        -   Gestione delle impostazioni di configurazione del modulo tramite il metodo `getContent()`, che gestisce l'invio del modulo e aggiorna la tabella `ps_configuration`.
        -   Implementazione di vari metodi `hook` (es. `hookDisplayHeader`, `hookDisplayFooter`, `hookDisplayHome`, ecc.) per renderizzare il widget nel front office.
        -   Recupero dei valori di configurazione da `ps_configuration` per il rendering del template.
        -   Metodo `_clearCache()` per la pulizia della cache specifica del modulo.
        -   Metodo `_displayForm()` per il rendering del modulo di configurazione nel back office.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessun file JavaScript personalizzato è incluso in questo modulo. Tutte le funzionalità sono gestite lato server o tramite HTML/CSS standard.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessun file CSS personalizzato è incluso in questo modulo. Tutti gli stili sono applicati in linea all'interno del template `displayHeader.tpl` o direttamente tramite il metodo `hookDisplayHeader`, utilizzando i valori di configurazione. Ciò significa che gli sviluppatori che desiderano sovrascrivere gli stili dovranno mirare direttamente all'HTML generato o utilizzare l'hook `displayHeader` per iniettare il proprio CSS.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:

    -   `fbgroup/views/displayHeader.tpl`:
        -   **Hook:** Principalmente destinato a `displayHeader` (sebbene il metodo `hookDisplayHeader` del modulo sia utilizzato per iniettare CSS, non per renderizzare il widget stesso). Questo template NON è utilizzato per la visualizzazione principale del widget. È probabilmente un residuo o utilizzato per l'iniezione di meta/CSS.
        -   **Scopo:** Se fosse utilizzato, produrrebbe HTML all'interno della sezione `<head>`. Nel contesto di questo modulo, il metodo `hookDisplayHeader` viene utilizzato per *iniettare stili CSS* dinamicamente in base alle impostazioni di configurazione, piuttosto che renderizzare un template visibile.
    -   `fbgroup/views/displayWidget.tpl`:
        -   **Hook:** Questo è il template principale utilizzato per renderizzare il widget "Facebook Join Group" in tutti gli hook del front-office selezionati (es. `displayFooter`, `displayHome`, `displayRightColumn`, ecc.).
        -   **Scopo:** Produce la struttura HTML per il widget, inclusi l'intestazione, la descrizione e il pulsante "Unisciti al gruppo". Riceve variabili come `fbg_href`, `fbg_header`, `fbg_desc`, `fbg_btn_text` e stili CSS dinamici dai metodi hook del modulo.
-   **Template di amministrazione (`views/templates/admin/`)**: Nessuno. Il modulo di configurazione è costruito programmaticamente all'interno di `getContent()` utilizzando `HelperForm` di PrestaShop.
-   **Template del front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle di database personalizzate.
    -   Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` (o prefisso `_configuration`, a seconda della tua configurazione) utilizzando le chiavi di configurazione elencate nella sezione 4.1 (es. `FBG_HREF`, `FBG_WIDTH`, `FBG_HEADER`, ecc.).
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato dal modulo per iniettare stili CSS dinamici per il widget in base alla configurazione. |
| `displayFooter` | In fondo a ogni pagina, prima di `</body>`. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayHome` | Sulla homepage, di solito nell'area del contenuto principale. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayNav1` | Nella barra di navigazione, spesso in alto a sinistra. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayNav2` | Nella barra di navigazione, spesso in alto a destra. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayNav` | Hook di navigazione generico, dipendente dal tema. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayFbgroup` | Hook personalizzato, richiede l'integrazione del tema. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayTop` | Nella sezione dell'intestazione, spesso sopra il logo. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayTopColumn` | Nell'area del contenuto principale dell'intestazione. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine che ne hanno una. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |
| `displayRightColumn` | Nella barra laterale destra delle pagine che ne hanno una. | Renderizza il template `displayWidget.tpl`, mostrando il widget di Facebook. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Facebook join to group widget", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
