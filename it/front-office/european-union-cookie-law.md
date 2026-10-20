---
title: "Legge sui Cookie dell'Unione Europea - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Legge sui Cookie dell'Unione Europea di MyPresta.eu."
sidebar:
  label: "Legge sui Cookie dell'Unione Europea - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo European Union Cookie Law su MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/european-union-cookie-law/)
>
> ---


# Legge sui Cookie dell'Unione Europea

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo Legge sui Cookie dell'Unione Europea. Qui troverai tutte le impostazioni per personalizzare la tua notifica sui cookie.

#### **Abilita / Disabilita Modulo**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la notifica sui cookie in tutto il tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* La barra di notifica sui cookie apparirà nel tuo front office in base alle altre tue impostazioni.
    -   *Quando disabilitato:* La barra di notifica sui cookie non verrà visualizzata a nessun visitatore.
-   **Valore consigliato:** SÌ (a meno che tu non abbia un altro metodo per la conformità ai cookie).
-   **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi attivare l'avviso sui cookie. Imposta questo su "SÌ". Se hai bisogno di nasconderlo temporaneamente per manutenzione o test, puoi impostarlo su "NO".

#### **Testo Cookie**

-   **Cosa fa questa impostazione:** Questo è il messaggio effettivo che verrà visualizzato ai tuoi clienti riguardo all'uso dei cookie. Supporta più lingue, permettendoti di fornire un messaggio localizzato per ogni lingua abilitata nel tuo negozio.
-   **Effetto della modifica di questa impostazione:** Il testo che inserisci qui verrà mostrato nella barra di notifica sui cookie. Puoi utilizzare l'editor di testo ricco per formattare il testo, aggiungere collegamenti (ad esempio, alla tua pagina completa della politica sulla privacy) ed enfatizzare informazioni importanti.
-   **Valore consigliato:** Un messaggio chiaro e conciso che informa gli utenti sui cookie e idealmente include un link alla tua politica sulla privacy completa o alla pagina della politica sui cookie.
-   **Scenario / esempio del commerciante:** Potresti scrivere: "Questo sito web utilizza i cookie per assicurarti la migliore esperienza sul nostro sito web. [Link alla Politica sulla Privacy]". Assicurati di tradurre questo in tutte le lingue attive del tuo negozio.

#### **Testo Pulsante**

-   **Cosa fa questa impostazione:** Definisce il testo visualizzato sul pulsante che i clienti cliccano per riconoscere o accettare la politica sui cookie. Come il testo del cookie, supporta più lingue.
-   **Effetto della modifica di questa impostazione:** Il pulsante visualizzerà il testo specificato. Cliccando su questo pulsante si chiuderà la notifica sui cookie per l'utente.
-   **Valore consigliato:** "Ho capito", "Accetto", "Ok", "Continua" o "OK".
-   **Scenario / esempio del commerciante:** Per chiarire che gli utenti stanno riconoscendo la politica, potresti impostare questo su "Ho capito e accetto".

#### **Posizione**

-   **Cosa fa questa impostazione:** Determina dove appare la barra di notifica sui cookie sul tuo sito web.
-   **Effetto della modifica di questa impostazione:**
    -   *In alto:* La barra apparirà fissa nella parte superiore della finestra del browser.
    -   *In basso:* La barra apparirà fissa nella parte inferiore della finestra del browser.
-   **Valore consigliato:** In basso (spesso meno invasivo rispetto all'alto, che a volte può interferire con gli elementi dell'intestazione).
-   **Scenario / esempio del commerciante:** Vuoi che l'avviso sui cookie sia visibile ma non ostruisca la tua navigazione principale o il logo. Scegliere "In basso" è di solito un buon compromesso.

#### **Colore Sfondo**

-   **Cosa fa questa impostazione:** Ti consente di scegliere il colore di sfondo della barra di notifica sui cookie. Questo aiuta a integrare visivamente la barra con il design del tuo negozio.
-   **Effetto della modifica di questa impostazione:** Lo sfondo della barra dei cookie cambierà nel colore selezionato. Di solito viene fornito uno strumento di selezione del colore per una facile selezione.
-   **Valore consigliato:** Un colore che contrasti bene con il colore del tuo testo e si integri con il branding del tuo negozio.
-   **Scenario / esempio del commerciante:** Il tuo negozio usa molto blu. Potresti scegliere un azzurro chiaro o un grigio tenue per lo sfondo per abbinarlo al tuo tema.

#### **Colore Testo**

-   **Cosa fa questa impostazione:** Ti consente di scegliere il colore del testo all'interno della barra di notifica sui cookie.
-   **Effetto della modifica di questa impostazione:** Il testo nella barra dei cookie cambierà nel colore selezionato.
-   **Valore consigliato:** Un colore che fornisca un buon contrasto con il colore di sfondo scelto per la leggibilità.
-   **Scenario / esempio del commerciante:** Se il colore di sfondo è scuro, scegli un colore di testo chiaro (ad esempio, bianco, grigio chiaro). Se lo sfondo è chiaro, scegli un colore di testo scuro (ad esempio, nero, grigio scuro).

#### **Colore Link**

-   **Cosa fa questa impostazione:** Ti consente di scegliere il colore di eventuali link inclusi nel tuo "Testo Cookie" (ad esempio, un link alla tua politica sulla privacy).
-   **Effetto della modifica di questa impostazione:** Tutti i tag `<a>` all'interno del testo della barra dei cookie verranno visualizzati in questo colore.
-   **Valore consigliato:** Un colore che si distingua dal colore del testo principale ma che si adatti comunque al tuo brand.
-   **Scenario / esempio del commerciante:** Vuoi che il link alla tua politica sulla privacy sia facilmente visibile. Potresti scegliere il colore accentuato del tuo brand per il link.

#### **Colore Sfondo Pulsante**

-   **Cosa fa questa impostazione:** Imposta il colore di sfondo del pulsante "Testo Pulsante".
-   **Effetto della modifica di questa impostazione:** Il pulsante avrà il colore di sfondo selezionato.
-   **Valore consigliato:** Un colore che faccia risaltare il pulsante e incoraggi i clic, spesso abbinato al colore del pulsante di chiamata all'azione principale del tuo negozio.
-   **Scenario / esempio del commerciante:** I pulsanti "Aggiungi al carrello" del tuo negozio sono verdi. Potresti scegliere il verde per lo sfondo del pulsante dei cookie per mantenere la coerenza.

#### **Colore Testo Pulsante**

-   **Cosa fa questa impostazione:** Imposta il colore del testo sul pulsante "Testo Pulsante".
-   **Effetto della modifica di questa impostazione:** Il testo del pulsante verrà visualizzato in questo colore.
-   **Valore consigliato:** Un colore che fornisca un buon contrasto con il colore di sfondo del pulsante per la leggibilità.
-   **Scenario / esempio del commerciante:** Se lo sfondo del tuo pulsante è verde scuro, scegli il bianco o un colore molto chiaro per il testo del pulsante.

#### **Scadenza Cookie (in giorni)**

-   **Cosa fa questa impostazione:** Determina per quanto tempo la notifica sui cookie rimane nascosta dopo che un utente fa clic sul pulsante "Ho capito". Dopo questo periodo, la notifica riapparirà per l'utente.
-   **Effetto della modifica di questa impostazione:**
    -   *Impostato su 30:* La notifica sarà nascosta per 30 giorni per quell'utente specifico.
    -   *Impostato su 0:* La notifica potrebbe riapparire ad ogni visita o sessione, il che generalmente non è raccomandato in quanto può essere fastidioso.
-   **Valore consigliato:** Da 30 a 365 giorni. Una pratica comune è 90 o 180 giorni.
-   **Scenario / esempio del commerciante:** Per evitare di infastidire ripetutamente i clienti di ritorno, imposti questo su "180" giorni. Ciò significa che un cliente che accetta la politica non vedrà più la barra per sei mesi.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | **Abilita / Disabilita Modulo** | SÌ | Interruttore principale per la visibilità della barra dei cookie. |
| Configurazione Modulo | **Testo Cookie** | Personalizzabile | Il messaggio principale sull'uso dei cookie, supporta testo ricco e multilingue. |
| Configurazione Modulo | **Testo Pulsante** | Personalizzabile | Testo sul pulsante per chiudere l'avviso, multilingue. |
| Configurazione Modulo | **Posizione** | In basso | Dove appare la barra (In alto o In basso dello schermo). |
| Configurazione Modulo | **Colore Sfondo** | Personalizzabile | Colore di sfondo della barra dei cookie. |
| Configurazione Modulo | **Colore Testo** | Personalizzabile | Colore del testo principale nella barra dei cookie. |
| Configurazione Modulo | **Colore Link** | Personalizzabile | Colore di eventuali link all'interno del testo del cookie. |
| Configurazione Modulo | **Colore Sfondo Pulsante** | Personalizzabile | Colore di sfondo del pulsante di chiusura. |
| Configurazione Modulo | **Colore Testo Pulsante** | Personalizzabile | Colore del testo sul pulsante di chiusura. |
| Configurazione Modulo | **Scadenza Cookie (in giorni)** | 180-365 giorni | Per quanto tempo l'avviso rimane nascosto dopo l'accettazione dell'utente. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: La barra dei cookie non viene visualizzata nel mio negozio.**
R1:

-   **Controlla "Abilita / Disabilita Modulo":** Assicurati che questa impostazione sia su "SÌ" nella configurazione del modulo.
-   **Svuota Cache:** Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota cache" in alto a destra. A volte, i vecchi contenuti memorizzati nella cache impediscono la visualizzazione delle modifiche del nuovo modulo.
-   **Verifica Conflitti:** Disabilita temporaneamente altri moduli installati di recente per vedere se c'è un conflitto.
-   **Cache del Browser:** Prova a svuotare la cache del tuo browser o ad aprire il tuo negozio in una finestra di navigazione in incognito/privata.

**D2: Ho aggiornato il testo, ma non cambia nel front office.**
R2:

-   **Salva Modifiche:** Assicurati di aver fatto clic sul pulsante "Salva" dopo aver apportato modifiche nella configurazione del modulo.
-   **Svuota Cache di PrestaShop:** Come menzionato sopra, svuotare la cache di Smarty (sotto **Parametri avanzati > Prestazioni**) è spesso necessario affinché le modifiche al template e al testo abbiano effetto.
-   **Controlla la Lingua:** Assicurati di modificare il testo per la lingua corretta se il tuo negozio è multilingue.

**D3: La barra dei cookie ha un aspetto strano o non si adatta al mio tema.**
R3:

-   **Regola i Colori:** Utilizza le impostazioni "Colore Sfondo", "Colore Testo", "Colore Link", "Colore Sfondo Pulsante" e "Colore Testo Pulsante" per abbinare la palette del tuo tema.
-   **Conflitti con il Tema:** Alcuni temi personalizzati potrebbero avere stili CSS in conflitto. Se la regolazione dei colori non aiuta, potresti aver bisogno di uno sviluppatore web per ispezionare il CSS e apportare piccole modifiche.

**D4: Come aggiungo un link alla mia Politica sulla Privacy nel testo del cookie?**
R4:

-   Nel campo "Testo Cookie", usa l'editor di testo ricco. Digita il testo che vuoi che sia un link (ad esempio, "Politica sulla Privacy"), selezionalo e quindi fai clic sull'icona "Link" nella barra degli strumenti dell'editor. Inserisci l'URL della tua pagina della Politica sulla Privacy.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori, webmaster e agenzie che lavorano con il modulo Legge sui Cookie dell'Unione Europea.

### 4.1 Panoramica dell'Architettura

Il modulo `uecookie` è un modulo PrestaShop semplice, progettato principalmente per iniettare un template del front-office in un hook di visualizzazione, controllato da un metodo di configurazione `getContent()` standard. Sfrutta la classe `Module` di PrestaShop per l'installazione, la disinstallazione e la configurazione, e utilizza i template Smarty per il rendering della notifica sui cookie. La logica lato client per la chiusura della barra dei cookie è gestita tramite JavaScript.

### 4.2 Controller (`controllers/`)

-   Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutte le funzionalità sono gestite all'interno del file principale del modulo e dei suoi template e asset associati.

### 4.3 Classi e Modelli Core (`classes/`)

-   Questo modulo **non** contiene classi personalizzate o definizioni di `ObjectModel`. Tutta la configurazione è memorizzata direttamente in `ps_configuration` utilizzando `Configuration::get()` e `Configuration::updateValue()`.

### 4.4 Asset JavaScript (`views/js/`)

-   `uecookie/jscolor/jscolor.js`:
    -   **Ambito:** Back-office.
    -   **Scopo:** Fornisce una funzionalità di selezione del colore JavaScript per il modulo di configurazione del modulo, consentendo agli amministratori di selezionare visivamente i colori per la barra dei cookie.
-   `uecookie/tinymce-original.js`:
    -   **Ambito:** Back-office.
    -   **Scopo:** Una versione completa dell'editor di testo ricco TinyMCE, utilizzata per il campo "Testo Cookie" nella configurazione del modulo. Ciò consente agli amministratori di formattare il testo, aggiungere link, ecc.
-   `uecookie/tinymce16.inc.js`:
    -   **Ambito:** Back-office.
    -   **Scopo:** Probabilmente un file di inclusione o configurazione per TinyMCE, che personalizza la sua barra degli strumenti o le opzioni per la compatibilità con PrestaShop 1.6 o esigenze specifiche del modulo.
-   `uecookie/views/js/scripts.js`:
    -   **Ambito:** Front-office.
    -   **Scopo:** Questo script gestisce la logica lato client per la barra di notifica sui cookie.
        -   **Listener di Eventi:** Probabilmente ascolta un evento di clic sul pulsante "Ho capito".
        -   **Manipolazione DOM:** Nasconde l'elemento della barra dei cookie dal DOM al momento della chiusura.
        -   **Gestione Cookie:** Imposta un cookie del browser (ad esempio, `uecookie_accepted`) con una data di scadenza (determinata dall'impostazione "Scadenza Cookie") per impedire che la barra riappaia per la durata specificata.
        -   **Controllo Iniziale:** Al caricamento della pagina, controlla la presenza del cookie `uecookie_accepted` per determinare se visualizzare la barra o meno.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   Questo modulo **non** contiene file CSS personalizzati in `views/css/`. Lo stile per la barra dei cookie è probabilmente inline o generato dinamicamente in base alle impostazioni di colore, o si basa su stili predefiniti minimi del browser. Gli sviluppatori che desiderano personalizzare ulteriormente l'aspetto dovrebbero mirare alla struttura HTML prodotta da `top.tpl` utilizzando il CSS personalizzato del loro tema.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **Template Hook (`views/templates/hook/`)**:
    -   `uecookie/top.tpl`:
        -   **Hook:** Questo template è progettato principalmente per essere renderizzato in un hook del front-office come `displayHeader`, `displayFooter`, `displayTop` o `displayBeforeBodyClosingTag`. Il metodo `hookDisplayHeader` del modulo è tipicamente responsabile della registrazione e del rendering di questo template.
        -   **Output:** Produce la struttura HTML per la barra di notifica sui cookie, inclusi il testo personalizzabile, il pulsante e lo stile dinamico basato sulle impostazioni di configurazione del modulo (colore di sfondo, colore del testo, ecc.). Include anche il JavaScript necessario (`scripts.js`) per gestire la chiusura e l'impostazione dei cookie.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    -   Questo modulo non crea tabelle di database personalizzate.
    -   Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`. Le voci di configurazione chiave includerebbero:
        -   `UECOOKIE_ENABLED` (booleano)
        -   `UECOOKIE_TEXT` (stringa multilingue)
        -   `UECOOKIE_BUTTON_TEXT` (stringa multilingue)
        -   `UECOOKIE_POSITION` (stringa: 'top' o 'bottom')
        -   `UECOOKIE_BG_COLOR` (stringa: codice colore esadecimale)
        -   `UECOOKIE_TEXT_COLOR` (stringa: codice colore esadecimale)
        -   `UECOOKIE_LINK_COLOR` (stringa: codice colore esadecimale)
        -   `UECOOKIE_BUTTON_BG_COLOR` (stringa: codice colore esadecimale)
        -   `UECOOKIE_BUTTON_TEXT_COLOR` (stringa: codice colore esadecimale)
        -   `UECOOKIE_EXPIRATION` (intero: giorni)
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per iniettare i file CSS (se presenti) e JavaScript del modulo, e potenzialmente la struttura HTML iniziale della barra dei cookie se posizionata in alto. |
| `displayFooter` | Eseguito nella parte inferiore di ogni pagina del front-office, prima del tag di chiusura `</body>`. | Può essere utilizzato per iniettare l'HTML e il JavaScript della barra dei cookie, specialmente se posizionata in basso. |
| `displayTop` | Eseguito nella sezione dell'intestazione del tema, tipicamente sopra il contenuto principale. | Hook alternativo per visualizzare la barra dei cookie in alto. |
| `displayBeforeBodyClosingTag` | Eseguito appena prima del tag `</body>`. | Un hook robusto per iniettare elementi JavaScript e HTML che dovrebbero apparire alla fine della pagina. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Legge sui Cookie dell'Unione Europea", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
