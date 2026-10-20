---
title: "PopUp Login Pro - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop PopUp Login Pro di MyPresta.eu."
sidebar:
  label: "PopUp Login Pro - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo PopUp Login Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-login-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/popup-login-pro/)
>
> ---


# PopUp Login Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un negozio PrestaShop e questo modulo non ha requisiti insoliti oltre a questi.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > PopUp Login Pro)

Questa è la schermata di configurazione principale per il modulo PopUp Login Pro. Qui puoi personalizzare l'aspetto e il comportamento del pop-up sul tuo negozio.

#### Impostazioni Generali

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio per il commerciante |
| --- | --- | --- | --- | --- |
| **Abilita PopUp Login** | Questo interruttore controlla se la funzionalità di login pop-up è attiva sul tuo negozio. | *Quando abilitato:* Il modulo intercetterà i clic sui link di login e visualizzerà il pop-up. *Quando disabilitato:* Il tuo negozio tornerà ai reindirizzamenti predefiniti della pagina di login di PrestaShop. | SÌ | Vuoi utilizzare la funzione di login pop-up. |
| **Tipo di Modulo PopUp** | Questa opzione ti permette di selezionare tra diversi stili visivi predefiniti per il tuo modulo di login pop-up. | *Se impostato su Opzione A:* Il pop-up verrà visualizzato con il design dell'Opzione A. *Se impostato su Opzione B:* Il pop-up verrà visualizzato con il design dell'Opzione B. Ogni opzione offre un aspetto e una sensazione distinti. | Scegli quello che meglio si adatta al design del tuo negozio. | Vuoi un modulo di login minimalista (Opzione 1) o uno più accattivante visivamente con un'immagine (Opzione 3). |
| **Larghezza PopUp (pixel)** | Definisce la larghezza della finestra pop-up in pixel. | *Se impostato a 400px:* Il pop-up sarà largo 400 pixel. *Se impostato a 600px:* Il pop-up sarà largo 600 pixel. Una larghezza minore potrebbe apparire meglio su mobile, mentre una maggiore può ospitare più contenuti o un design specifico. | 400-500px (regola in base al tipo di modulo selezionato) | Il tipo di modulo scelto appare troppo stretto a 400px, quindi lo aumenti a 500px per una migliore leggibilità. |
| **Altezza PopUp (pixel)** | Definisce l'altezza della finestra pop-up in pixel. | *Se impostato a 300px:* Il pop-up sarà alto 300 pixel. *Se impostato a 500px:* Il pop-up sarà alto 500 pixel. Assicurati che sia abbastanza alto da mostrare tutti i campi del modulo senza scorrere. | 300-450px (regola in base al tipo di modulo selezionato) | Il tipo di modulo scelto ha molti campi e a 300px i clienti devono scorrere. Lo aumenti a 450px per mostrare tutto. |
| **Colore Sfondo PopUp** | Imposta il colore di sfondo della finestra pop-up. Di solito puoi usare un selettore di colori o inserire un codice colore esadecimale (es. #FFFFFF per il bianco). | *Se impostato su #FFFFFF:* Lo sfondo del pop-up sarà bianco. *Se impostato su #F0F0F0:* Lo sfondo del pop-up sarà grigio chiaro. Questo aiuta a far corrispondere il pop-up alla combinazione di colori del tuo negozio. | #FFFFFF (Bianco) o un colore che si abbini al tuo tema. | Il tuo negozio utilizza un tema scuro, quindi imposti lo sfondo su un grigio scuro (#333333) per coerenza. |
| **Colore Bordo PopUp** | Imposta il colore del bordo attorno alla finestra pop-up. | *Se impostato su #CCCCCC:* Il bordo del pop-up sarà grigio chiaro. *Se impostato su trasparente:* Non verrà visualizzato alcun bordo visibile. | #CCCCCC (Grigio Chiaro) o trasparente | Vuoi un bordo sottile per definire il pop-up, quindi scegli un grigio chiaro. |
| **Raggio Bordo PopUp (pixel)** | Controlla la rotondità degli angoli della finestra pop-up. Un valore di 0 significa angoli acuti, valori più alti creano angoli più arrotondati. | *Se impostato a 0:* Il pop-up avrà angoli acuti e quadrati. *Se impostato a 10:* Il pop-up avrà angoli leggermente arrotondati. | 5-10px | Preferisci un aspetto più morbido e moderno, quindi imposti il raggio del bordo a 8px. |
| **Colore Sfondo Overlay** | Imposta il colore dello sfondo oscurato che appare dietro il pop-up. Questo aiuta a focalizzare l'attenzione sul pop-up. | *Se impostato su #000000:* L'overlay sarà nero. *Se impostato su #FFFFFF:* L'overlay sarà bianco. | #000000 (Nero) | Vuoi un overlay scuro e trasparente per separare chiaramente il pop-up dal contenuto principale. |
| **Opacità Overlay (0-1)** | Controlla la trasparenza dello sfondo dell'overlay. 0 è completamente trasparente, 1 è completamente opaco. | *Se impostato a 0.5:* L'overlay sarà trasparente al 50%. *Se impostato a 0.8:* L'overlay sarà opaco all'80%. | 0.7-0.8 | Vuoi che il contenuto di sfondo sia leggermente visibile ma comunque chiaramente oscurato, quindi lo imposti a 0.7. |
| **Colore Pulsante Chiudi** | Imposta il colore del pulsante 'X' (chiudi) per il pop-up. | *Se impostato su #000000:* Il pulsante di chiusura sarà nero. *Se impostato su #FF0000:* Il pulsante di chiusura sarà rosso. | #000000 (Nero) | Il tuo negozio utilizza un colore accento rosso, quindi rendi il pulsante di chiusura rosso per coerenza. |
| **Colore Sfondo Pulsante Chiudi** | Imposta il colore di sfondo del pulsante 'X' (chiudi). | *Se impostato su #FFFFFF:* Lo sfondo del pulsante di chiusura sarà bianco. *Se impostato su trasparente:* Non verrà applicato alcun colore di sfondo. | trasparente | Vuoi che il pulsante di chiusura si fonda con il pop-up, quindi imposti il suo sfondo su trasparente. |
| **Abilita Google reCAPTCHA** | Attiva Google reCAPTCHA per i moduli di login e registrazione all'interno del pop-up, aiutando a prevenire spam e registrazioni di bot. | *Quando abilitato:* reCAPTCHA apparirà sui moduli, richiedendo agli utenti di verificare di non essere robot. *Quando disabilitato:* Non sarà presente alcun reCAPTCHA. | SÌ (se hai le chiavi reCAPTCHA) | Stai riscontrando molte registrazioni di spam, quindi abiliti reCAPTCHA per filtrarle. |
| **Chiave Sito reCAPTCHA** | La tua chiave pubblica del sito reCAPTCHA, ottenuta da Google. Richiesta se reCAPTCHA è abilitato. | *Se inserita correttamente:* reCAPTCHA funzionerà. *Se errata o vuota:* reCAPTCHA non funzionerà, potenzialmente bloccando utenti legittimi o non riuscendo a prevenire i bot. | La tua vera chiave del sito Google reCAPTCHA | Hai registrato il tuo sito con Google reCAPTCHA e incolli qui la chiave del sito fornita. |
| **Chiave Segreta reCAPTCHA** | La tua chiave segreta privata reCAPTCHA, ottenuta da Google. Richiesta se reCAPTCHA è abilitato. | *Se inserita correttamente:* reCAPTCHA funzionerà. *Se errata o vuota:* reCAPTCHA non funzionerà. | La tua vera chiave segreta Google reCAPTCHA | Hai registrato il tuo sito con Google reCAPTCHA e incolli qui la chiave segreta fornita. |

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita PopUp Login | SÌ | Attiva/disattiva la funzione di login pop-up. |
| Configurazione Modulo | Tipo di Modulo PopUp | (Scegli in base al design) | Seleziona lo stile visivo del modulo di login. |
| Configurazione Modulo | Larghezza PopUp (pixel) | 400-500px | Controlla la larghezza della finestra pop-up. |
| Configurazione Modulo | Altezza PopUp (pixel) | 300-450px | Controlla l'altezza della finestra pop-up. |
| Configurazione Modulo | Colore Sfondo PopUp | #FFFFFF | Imposta il colore di sfondo del pop-up. |
| Configurazione Modulo | Colore Bordo PopUp | #CCCCCC o trasparente | Imposta il colore del bordo del pop-up. |
| Configurazione Modulo | Raggio Bordo PopUp (pixel) | 5-10px | Controlla la rotondità degli angoli del pop-up. |
| Configurazione Modulo | Colore Sfondo Overlay | #000000 | Imposta il colore dello sfondo oscurato dietro il pop-up. |
| Configurazione Modulo | Opacità Overlay (0-1) | 0.7-0.8 | Controlla la trasparenza dello sfondo dell'overlay. |
| Configurazione Modulo | Colore Pulsante Chiudi | #000000 | Imposta il colore del pulsante di chiusura del pop-up. |
| Configurazione Modulo | Colore Sfondo Pulsante Chiudi | trasparente | Imposta il colore di sfondo del pulsante di chiusura. |
| Configurazione Modulo | Abilita Google reCAPTCHA | SÌ (se le chiavi sono disponibili) | Attiva reCAPTCHA per la protezione dai bot. |
| Configurazione Modulo | Chiave Sito reCAPTCHA | La tua chiave effettiva | Chiave pubblica per la verifica reCAPTCHA. |
| Configurazione Modulo | Chiave Segreta reCAPTCHA | La tua chiave effettiva | Chiave privata per la verifica reCAPTCHA. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Il pop-up non appare quando clicco su "Accedi". Cosa devo fare?**
R:

1.  **Controlla lo stato del modulo:** Assicurati che l'impostazione "Abilita PopUp Login" sia impostata su SÌ nella configurazione del modulo.
2.  **Svuota la cache:** Vai su **Parametri Avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte i vecchi file di cache impediscono il caricamento delle nuove funzionalità del modulo.
3.  **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero utilizzare modi non standard per gestire i link di accesso. Controlla se il tuo tema ha impostazioni o override specifici per l'accesso. Se i problemi persistono, contatta il supporto MyPresta.eu.

**D2: Il pop-up ha un aspetto strano o non corrisponde allo stile del mio tema.**
R:

1.  **Regola le impostazioni di stile:** Vai alla configurazione del modulo e sperimenta con "Colore Sfondo PopUp", "Colore Bordo PopUp", "Raggio Bordo PopUp", "Colore Sfondo Overlay" e "Opacità Overlay".
2.  **Tipo di modulo:** Prova diverse opzioni di "Tipo di Modulo PopUp" per vedere se un altro design si integra meglio con il tuo tema.
3.  **CSS personalizzato:** Se le impostazioni di base non sono sufficienti, il tuo webmaster potrebbe dover aggiungere CSS personalizzato al tuo tema per sovrascrivere gli stili predefiniti del modulo (vedi Sezione 7.5 per i dettagli sui file CSS).

**D3: reCAPTCHA non funziona sui moduli pop-up.**
R:

1.  **Abilita reCAPTCHA:** Assicurati che "Abilita Google reCAPTCHA" sia impostato su SÌ.
2.  **Controlla le chiavi:** Ricontrolla che la tua "Chiave Sito reCAPTCHA" e la "Chiave Segreta reCAPTCHA" siano inserite correttamente nella configurazione del modulo. Queste sono sensibili alle maiuscole/minuscole.
3.  **Configurazione Google reCAPTCHA:** Assicurati che il tuo dominio sia correttamente registrato nel tuo account Google reCAPTCHA.
4.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alle impostazioni di reCAPTCHA.

**D4: Il pop-up è troppo grande/piccolo sul mio telefono cellulare.**
R:

1.  **Regola Larghezza/Altezza:** Modifica "Larghezza PopUp (pixel)" e "Altezza PopUp (pixel)" nella configurazione del modulo. Sebbene questi siano valori in pixel, il modulo è progettato per essere reattivo, quindi la loro regolazione influenzerà la sua scalatura su diversi dispositivi.
2.  **Testa la reattività:** Utilizza gli strumenti per sviluppatori del tuo browser (F12) per simulare diversi dispositivi mobili e perfezionare le dimensioni.

**D5: Come posso tradurre il testo all'interno del pop-up?**
R:

1.  **Traduci il modulo:** Nel tuo Back Office di PrestaShop, vai su **Internazionale > Traduzioni**.
2.  **Seleziona le opzioni:**
    -   Tipo di traduzione: "Traduzioni dei moduli installati"
    -   Seleziona il tuo tema: Il tuo tema attuale
    -   Seleziona la tua lingua: La lingua che vuoi tradurre
3.  **Trova il modulo:** Cerca "PopUp Login Pro" (o `popuplogin`).
4.  **Traduci i campi:** Troverai tutte le stringhe traducibili utilizzate dal modulo. Inserisci le tue traduzioni e salva.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo PopUp Login Pro segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente i controller frontali per le richieste AJAX e gli hook per l'integrazione nel tema. Utilizza JavaScript per intercettare i clic sui link di login standard e visualizzare il pop-up, caricando dinamicamente il contenuto tramite AJAX. La configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo, memorizzando le impostazioni in `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    -   `controllers/front/index.php`
        -   **Nome Classe**: `PopUpLoginIndexModuleFrontController`
        -   **Classe Padre**: `ModuleFrontController`
        -   **Responsabilità**: Questo controller funge probabilmente da punto di ingresso generale o gestisce la configurazione iniziale per le interazioni del front-office, sebbene i suoi metodi specifici definirebbero il suo ruolo esatto. Potrebbe essere responsabile del rendering della struttura iniziale del pop-up o della gestione delle chiamate AJAX non correlate al login.
    -   `controllers/front/loginbox.php`
        -   **Nome Classe**: `PopUpLoginLoginBoxModuleFrontController`
        -   **Classe Padre**: `ModuleFrontController`
        -   **Responsabilità**: Questo è il controller principale per la gestione della logica del modulo di login e registrazione. Risponde alle richieste AJAX per la visualizzazione del contenuto del modulo di login/registrazione, l'elaborazione dei tentativi di login, la gestione delle nuove registrazioni e la gestione delle richieste di "password dimenticata". Probabilmente restituisce frammenti HTML o risposte JSON a JavaScript per l'inserimento dinamico nel pop-up.

### 4.3 Classi Core e Modelli (`classes/`)

In base all'inventario fornito, non ci sono classi personalizzate o definizioni di `ObjectModel` all'interno della directory `classes/`. Il modulo probabilmente sfrutta le classi core esistenti di PrestaShop per la gestione dei clienti (`Customer`, `Context`, `Tools`) e l'archiviazione standard della configurazione.

### 4.4 Risorse JavaScript (`views/js/`)

-   `popuplogin/popuplogin.js`
    -   **Ambito**: Front-office.
    -   **Dettagli**: Questo è il file JavaScript principale per la funzionalità front-end del modulo.
        -   **Listener di Eventi**: Collega listener di eventi a vari elementi, in modo più critico ai link standard di login/account (es. `a[href*="controller=authentication"]`, `a[href*="my-account"]`). Intercetta gli eventi di clic su questi link.
        -   **Chiamate AJAX**: Quando si clicca su un link di login, impedisce la navigazione predefinita e avvia una richiesta AJAX a `popuplogin/controllers/front/loginbox.php` (o simile) per recuperare l'HTML del modulo di login/registrazione.
        -   **Manipolazione del DOM**: Crea e inserisce dinamicamente l'overlay del pop-up e il contenuto del modulo di login nel DOM. Gestisce la visualizzazione/nascondimento del pop-up, la gestione dell'overlay e potenzialmente il passaggio tra le viste di login e registrazione all'interno del pop-up.
        -   **Invio del Modulo**: Probabilmente intercetta gli invii del modulo all'interno del pop-up (login, registrazione, password dimenticata) e li invia tramite AJAX al controller `loginbox.php`, elaborando le risposte (es. visualizzazione di messaggi di successo, messaggi di errore o reindirizzamento dopo un login riuscito).
        -   **UI/UX**: Gestisce gli effetti visivi del pop-up (es. dissolvenza in entrata/uscita, centratura).
        -   **Integrazione reCAPTCHA**: Se reCAPTCHA è abilitato, questo script è responsabile del rendering del widget reCAPTCHA e dell'inclusione del suo token negli invii di moduli AJAX.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `popuplogin/css.css`
    -   **Ambito**: Stile del cliente del front-office.
    -   **Dettagli**: Questo file contiene probabilmente stili generali e fondamentali per il contenitore del pop-up, l'overlay e potenzialmente elementi comuni del modulo. Potrebbe includere stili di reset o regole di layout di base.
    -   **Selettori Chiave**: `.popuplogin-overlay`, `.popuplogin-popup`, `.popuplogin-close-btn`.
-   `popuplogin/popuplogin.css`
    -   **Ambito**: Stile del cliente del front-office.
    -   **Dettagli**: Questo file contiene probabilmente lo stile più specifico e dettagliato per i vari tipi di moduli pop-up, inclusi campi di input, pulsanti, messaggi di errore e regolazioni reattive. Definirà le differenze visive tra le opzioni "Tipo di Modulo PopUp".
    -   **Selettori Chiave**: `.popuplogin-form-type-1`, `.popuplogin-form-type-2`, `.popuplogin-input`, `.popuplogin-button`, `.popuplogin-error-message`.
    -   **Override dello Sviluppatore**: Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` del loro tema o creando un tema figlio per modificare l'aspetto senza modificare direttamente i file del modulo.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **Template Hook (`views/templates/hook/`)**:
    -   `popuplogin/dashboardZoneOne.tpl`
        -   **Hook**: Probabilmente `displayDashboardZoneOne` (o hook simile della dashboard).
        -   **Scopo**: Questo template serve probabilmente per visualizzare un piccolo blocco informativo o statistiche rapide relative al modulo PopUp Login Pro nella dashboard del Back Office di PrestaShop. È un template rivolto all'amministratore.
    -   `popuplogin/displayPopUpLogin.tpl`
        -   **Hook**: Questo template è probabilmente renderizzato dal controller frontale `loginbox.php` e contiene la struttura HTML effettiva per il modulo di login/registrazione che appare all'interno del pop-up. Non è direttamente agganciato a un hook `display` nel tema, ma piuttosto caricato dinamicamente.
        -   **Scopo**: Renderizza i moduli di login, registrazione e recupero password, inclusi campi di input, pulsanti e potenzialmente segnaposto reCAPTCHA.
    -   `popuplogin/header.tpl`
        -   **Hook**: Probabilmente `displayHeader`.
        -   **Scopo**: Questo template è responsabile dell'inclusione dei file CSS e JavaScript del modulo (`popuplogin.js`, `css.css`, `popuplogin.css`) nella sezione `<head>` delle pagine del front-office, assicurando che vengano caricati prima che la funzionalità del modulo venga attivata.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:
    -   Il modulo non crea tabelle SQL personalizzate.
    -   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi tipicamente prefissate con `POPUPLOGIN_` (es. `POPUPLOGIN_ENABLED`, `POPUPLOGIN_FORM_TYPE`, `POPUPLOGIN_WIDTH`, `POPUPLOGIN_RECAPTCHA_SITE_KEY`).
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS e JavaScript del modulo per la funzionalità front-end. |
| `displayDashboardZoneOne` | Nella dashboard del Back Office di PrestaShop. | Visualizza un blocco informativo o un widget per il modulo nel pannello di amministrazione. |
| (Hook Impliciti) | Attivati dall'intercettazione JavaScript dei link di login standard. | Il JavaScript del modulo intercetta i clic su elementi che normalmente porterebbero ai controller `authentication` o `my-account`, e quindi utilizza AJAX per caricare dinamicamente il contenuto dai propri controller frontali. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo PopUp Login Pro, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il vostro modulo funzioni perfettamente e si integri senza problemi con il vostro negozio PrestaShop.
