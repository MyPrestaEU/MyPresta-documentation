---
title: "Shoutbox - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Shoutbox di MyPresta.eu."
sidebar:
  label: "Shoutbox - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Shoutbox su MyPresta.eu](https://mypresta.eu/modules/front-office-features/shoutbox.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/shoutbox/)
>
> ---


# Shoutbox

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo Shoutbox, accessibile direttamente dopo l'installazione o navigando su **Moduli > Gestione moduli**, cercando "Shoutbox" e cliccando su "Configura".

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio per il commerciante |
| --- | --- | --- | --- | --- |
| **Abilita Shoutbox** | Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità Shoutbox nel tuo negozio. | *Quando abilitato:* Lo Shoutbox apparirà nel tuo front office nelle posizioni hook scelte. I clienti possono vederlo e interagire con esso. *Quando disabilitato:* Lo Shoutbox sarà completamente nascosto dal tuo negozio e nessun messaggio verrà visualizzato o accettato. | **SÌ** | Vuoi attivare la funzione di chat della comunità nel tuo negozio. Se hai bisogno di nasconderlo temporaneamente per manutenzione o revisione dei contenuti, imposteresti questo su NO. |
| **Titolo Shoutbox** | Questo imposta il testo dell'intestazione che appare nella parte superiore del widget Shoutbox nel front office del tuo negozio. | *Quando impostato su "Chat della Comunità":* I tuoi clienti vedranno "Chat della Comunità" come titolo della casella. *Quando impostato su "Chiedici Qualsiasi Cosa":* Il titolo cambia in "Chiedici Qualsiasi Cosa". | **Chat della Comunità** | Vuoi etichettare chiaramente la chat box per i tuoi clienti. Potresti cambiarlo in "Discussioni sui Prodotti" se lo posizioni sulle pagine dei prodotti. |
| **Numero di Messaggi da Visualizzare** | Questo controlla quanti dei messaggi più recenti vengono mostrati nello Shoutbox in un dato momento. I messaggi più vecchi saranno nascosti. | *Quando impostato su 10:* Solo gli ultimi 10 messaggi saranno visibili nella chat box. *Quando impostato su 20:* Verranno mostrati gli ultimi 20 messaggi. | **10** | Per mantenere la chat concisa e impedire che diventi troppo lunga, mostrare gli ultimi 10-15 messaggi è di solito la soluzione migliore. Se hai una comunità molto attiva, potresti aumentare questo numero. |
| **Intervallo di Aggiornamento (secondi)** | Questo determina la frequenza con cui lo Shoutbox controlla e carica automaticamente nuovi messaggi senza che il cliente debba aggiornare la pagina. | *Quando impostato su 5:* I nuovi messaggi appariranno ogni 5 secondi. *Quando impostato su 15:* I nuovi messaggi appariranno ogni 15 secondi. | **10** | Un intervallo più breve (es. 5 secondi) rende la chat più in tempo reale ma utilizza più risorse del server. Un intervallo più lungo (es. 15-20 secondi) riduce il carico del server ma i messaggi appaiono meno istantaneamente. 10 secondi è un buon equilibrio. |
| **Consenti agli Ospiti di Pubblicare** | Questa opzione controlla se i visitatori che non sono loggati in un account cliente possono pubblicare messaggi nello Shoutbox. | *Quando abilitato:* Chiunque visiti il tuo negozio può pubblicare messaggi, anche se non si è registrato o loggato. Tipicamente pubblicheranno come "Ospite". *Quando disabilitato:* Solo i clienti registrati e loggati possono pubblicare messaggi. Gli ospiti vedranno la chat ma non potranno contribuire. | **NO** | Se vuoi incoraggiare la registrazione e prevenire lo spam anonimo, disabilita questa opzione. Se vuoi la massima interazione e non ti dispiacciono i post anonimi, abilitala. |
| **Visualizza Shoutbox In** | Questa impostazione cruciale determina dove il widget Shoutbox apparirà nel front office del tuo negozio. Puoi selezionare una o più posizioni. | *Quando è selezionata "Colonna Sinistra":* Lo Shoutbox apparirà nella barra laterale sinistra del tuo negozio. *Quando è selezionato "Piè di Pagina":* Lo Shoutbox apparirà nella parte inferiore delle pagine del tuo negozio. | **Colonna Sinistra** (o una posizione che si adatta al tuo tema) | Vuoi che lo Shoutbox sia facilmente visibile ma non interferisca con il contenuto principale del tuo prodotto. Posizionarlo in una colonna o nel piè di pagina è spesso una buona scelta. |
| **Moderazione Richiesta** | Se abilitato, i nuovi messaggi non appariranno nello Shoutbox finché un amministratore non li approverà manualmente nel Back Office. | *Quando abilitato:* Tutti i nuovi messaggi vanno in una coda di attesa. Devi approvare ogni messaggio prima che diventi visibile agli altri clienti. *Quando disabilitato:* I messaggi appaiono istantaneamente dopo essere stati pubblicati. | **NO** (a meno che non prevedi spam) | Se sei preoccupato per lo spam, contenuti inappropriati o vuoi mantenere uno stretto controllo sulla conversazione, abilita la moderazione. Per una chat più fluida e in tempo reale, disabilitala. |
| **Cancella Tutti i Messaggi** | Questo è un pulsante (non un interruttore) che, quando cliccato, eliminerà permanentemente tutti i messaggi esistenti dallo Shoutbox. | *Quando cliccato:* Tutti i messaggi storici nello Shoutbox vengono rimossi dal tuo database e non verranno più visualizzati. Questa azione è irreversibile. | **N/A** (Usare con cautela) | Potresti usarlo se la chat ha accumulato troppi messaggi vecchi, o se vuoi iniziare una nuova conversazione per una nuova promozione o evento. |

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Shoutbox | SÌ | Attiva/disattiva l'intera funzionalità Shoutbox. |
| Configurazione Modulo | Titolo Shoutbox | Chat della Comunità | Imposta il titolo visibile del widget Shoutbox. |
| Configurazione Modulo | Numero di Messaggi da Visualizzare | 10 | Controlla quanti messaggi recenti vengono mostrati. |
| Configurazione Modulo | Intervallo di Aggiornamento (secondi) | 10 | Frequenza di aggiornamento della chat con nuovi messaggi. |
| Configurazione Modulo | Consenti agli Ospiti di Pubblicare | NO | Determina se gli utenti non loggati possono pubblicare messaggi. |
| Configurazione Modulo | Visualizza Shoutbox In | Colonna Sinistra | Seleziona la/le posizione/i del front-office per lo Shoutbox. |
| Configurazione Modulo | Moderazione Richiesta | NO | Richiede l'approvazione dell'amministratore per i messaggi prima che appaiano. |
| Configurazione Modulo | Cancella Tutti i Messaggi | N/A | Elimina permanentemente tutti i messaggi dallo Shoutbox. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Lo Shoutbox non appare nel mio negozio, anche se l'ho abilitato.**
**R1:**

- **Controlla la selezione dell'Hook:** Vai alla configurazione del modulo e assicurati di aver selezionato almeno una posizione "Visualizza Shoutbox In" (ad esempio, Colonna Sinistra, Piè di Pagina).
- **Svuota la cache:** La cache di PrestaShop a volte può impedire la visualizzazione di nuovi moduli. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
- **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero non renderizzare correttamente gli hook standard dei moduli. Se svuotare la cache non funziona, prova a passare temporaneamente al tema PrestaShop predefinito per vedere se lo Shoutbox appare. Se lo fa, il tuo tema probabilmente necessita di una piccola modifica (contatta lo sviluppatore del tuo tema o un webmaster).

**D2: I nuovi messaggi non appaiono in tempo reale; devo aggiornare la pagina.**
**R2:**

- **Controlla l'intervallo di aggiornamento:** Nella configurazione del modulo, assicurati che "Intervallo di Aggiornamento (secondi)" sia impostato su un numero ragionevole (ad esempio, 5-15 secondi) e non su 0 o un numero molto alto.
- **Conflitti JavaScript:** Un altro modulo o il JavaScript del tuo tema potrebbe causare un conflitto. Controlla la console per sviluppatori del tuo browser (tasto F12, quindi guarda la scheda "Console") per eventuali errori JavaScript. Se appaiono errori, prova a disabilitare altri moduli installati di recente uno per uno per identificare il colpevole.

**D3: Ricevo molti messaggi di spam nello Shoutbox.**
**R3:**

- **Abilita la moderazione:** Vai alla configurazione del modulo e imposta "Moderazione Richiesta" su SÌ. Questo metterà tutti i nuovi messaggi in uno stato di attesa, permettendoti di approvarli prima che diventino visibili.
- **Disabilita la pubblicazione degli ospiti:** Se lo spam proviene da utenti anonimi, imposta "Consenti agli Ospiti di Pubblicare" su NO. Questo richiederà agli utenti di essere loggati in un account cliente per pubblicare, il che spesso riduce lo spam.

**D4: Come posso tradurre il titolo dello Shoutbox o altri testi in diverse lingue?**
**R4:**

- Naviga su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
- Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi seleziona la tua lingua.
- Trova il modulo "Shoutbox" nell'elenco e potrai modificare le stringhe traducibili, incluso il titolo dello Shoutbox.

**D5: Lo Shoutbox sembra un po' strano o non corrisponde allo stile del mio tema.**
**R5:**

- Il modulo utilizza uno stile di base. Per un aspetto personalizzato, avrai bisogno di un webmaster o di uno sviluppatore per aggiungere regole CSS personalizzate al foglio di stile del tuo tema. Possono mirare agli elementi dello Shoutbox e regolare colori, font, bordi, ecc., per abbinarli perfettamente al tuo brand.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo Shoutbox, destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo Shoutbox segue una classica struttura di modulo PrestaShop, sfruttando i controller frontali per le interazioni AJAX e il file principale del modulo (`index.php`) per la configurazione e la registrazione degli hook. È un modulo leggero, principalmente focalizzato sulla visualizzazione e l'invio di messaggi tramite AJAX senza complessi modelli di oggetti o tabelle di database dedicate oltre a `ps_configuration` per le impostazioni. La funzionalità principale si basa sull'interazione diretta con il database per l'archiviazione e il recupero dei messaggi.

### 4.2 Controller (`controllers/`)

Il modulo utilizza controller frontali per gestire le richieste AJAX per il caricamento e l'inserimento dei messaggi, garantendo un'esperienza utente dinamica senza ricariche complete della pagina.

- **Controller Front-Office**:

  - `controllers/front/ajaxload.php`
    - **Nome Classe**: `ShoutboxAjaxloadModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller gestisce la richiesta AJAX per il caricamento dei messaggi esistenti. Tipicamente recupera un numero specificato dei messaggi più recenti dal database e li restituisce, probabilmente come JSON o HTML grezzo, per essere visualizzati nel widget Shoutbox. Questo è l'endpoint per il meccanismo di auto-aggiornamento.
  - `controllers/front/index.php`
    - **Nome Classe**: `ShoutboxIndexModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller potrebbe servire come fallback o come punto di accesso diretto allo Shoutbox se dovesse avere una pagina dedicata. Data la natura del modulo, è più probabile che sia un segnaposto o che gestisca la logica di rendering iniziale se lo Shoutbox è incorporato direttamente piuttosto che tramite un hook. Nella maggior parte dei casi, lo Shoutbox viene renderizzato tramite `shoutbox.tpl` in un hook.
  - `controllers/front/insert.php`
    - **Nome Classe**: `ShoutboxInsertModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller gestisce la richiesta AJAX per l'invio di nuovi messaggi. Riceve il contenuto del messaggio (e potenzialmente l'ID/nome utente) dal front-end, esegue le convalide necessarie (ad esempio, pubblicazione degli ospiti, moderazione), memorizza il messaggio nel database e restituisce una risposta di successo/fallimento.
- **Controller Amministrativi Back-Office**:

  - Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non definisce classi personalizzate o `ObjectModel` nella directory `classes/`. L'archiviazione e il recupero dei messaggi sono gestiti direttamente all'interno dei file PHP del modulo, probabilmente utilizzando `Db::getInstance()` per le query SQL. Ciò implica che i messaggi sono archiviati in una tabella personalizzata creata durante l'installazione o direttamente in `ps_configuration` se i messaggi sono molto pochi e semplici (anche se una tabella dedicata è più probabile per i messaggi di chat).

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo si basa su JavaScript per la sua funzionalità AJAX e gli aggiornamenti dinamici.

- `js/advajax.js`
  - **Ambito**: Front-office.
  - **Dettagli**: Questo file contiene probabilmente un'utilità AJAX generica o funzioni wrapper utilizzate dal modulo. Potrebbe fornire compatibilità cross-browser per le richieste AJAX o semplificare il processo di invio e ricezione di dati dai controller frontali. Potrebbe essere un'implementazione personalizzata o una libreria leggera.
- `js/script.js`
  - **Ambito**: Front-office.
  - **Dettagli**: Questo è il file JavaScript principale per la logica front-end dello Shoutbox.
    - **Listener di eventi**: Si lega agli eventi di invio del modulo per la pubblicazione di nuovi messaggi e potenzialmente agli eventi di clic per azioni come la cancellazione dei messaggi (se esposti al front-end).
    - **Chiamate AJAX**: Avvia richieste AJAX a `ajaxload.php` per l'aggiornamento dei messaggi all'intervallo specificato e a `insert.php` per l'invio di nuovi messaggi.
    - **Manipolazione del DOM**: Aggiorna la visualizzazione dello Shoutbox con nuovi messaggi, scorre fino alla fine della chat e gestisce la cancellazione del campo di input.
    - **Timer**: Imposta `setInterval` per il caricamento periodico dei messaggi in base all'impostazione "Intervallo di Aggiornamento".

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non elenca esplicitamente alcun file CSS personalizzato nella directory `views/css/`. Ciò suggerisce che:

1. Il modulo si basa su stili inline o stili predefiniti di base del browser.
2. Potrebbe essere progettato per ereditare lo stile direttamente dal tema PrestaShop attivo, richiedendo un CSS personalizzato minimo.
3. Qualsiasi stile è incorporato direttamente nel file `shoutbox.tpl` o nel PHP del modulo principale.
   Gli sviluppatori che desiderano stilizzare lo Shoutbox dovranno ispezionare l'HTML generato e aggiungere regole CSS personalizzate al foglio di stile del loro tema, mirando agli ID e alle classi specifiche utilizzate dagli elementi dello Shoutbox.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**:
  - `shoutbox/shoutbox.tpl`
    - **Hook(s) renderizzati**: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o hook simile per la pagina prodotto). L'hook effettivo dipende dalla configurazione del commerciante nel Back Office.
    - **Output del blocco visivo**: Questo template renderizza la struttura HTML completa del widget Shoutbox. Include:
      - Il contenitore principale per la chat box.
      - Il titolo (es. "Chat della Comunità").
      - L'area in cui vengono visualizzati i messaggi (un div scorrevole).
      - Il campo di input per digitare nuovi messaggi.
      - Il pulsante "Invia".
      - Rendering condizionale per le capacità di pubblicazione degli ospiti.
      - Includerà anche il JavaScript necessario e potenzialmente CSS inline.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non dichiara esplicitamente un `ObjectModel` personalizzato o un file SQL. L'archiviazione dei messaggi è probabilmente gestita direttamente tramite `Db::getInstance()` nel file principale del modulo o nei controller frontali. Un modello comune per tali moduli è creare una tabella come `ps_shoutbox_messages` con campi come `id_shoutbox_message`, `id_customer`, `customer_name`, `message_content`, `date_add`, `ip_address`, `approved`.
  - **Record di configurazione**: Le impostazioni del modulo (ad esempio, `SHOUTBOX_ENABLED`, `SHOUTBOX_TITLE`, `SHOUTBOX_NUM_MESSAGES`, `SHOUTBOX_REFRESH_INTERVAL`, `SHOUTBOX_ALLOW_GUEST`, `SHOUTBOX_MODERATION`, `SHOUTBOX_HOOK`) sono archiviate nella tabella `ps_configuration`.
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` dell'HTML o all'inizio del `<body>`. | Utilizzato per iniettare CSS, file JavaScript o il widget Shoutbox stesso se configurato per la visualizzazione nell'intestazione. |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra del negozio. | Hook comune per visualizzare il widget Shoutbox come elemento della barra laterale. |
| `displayRightColumn` | Renderizza il contenuto nella barra laterale destra del negozio. | Hook comune per visualizzare il widget Shoutbox come elemento della barra laterale. |
| `displayFooter` | Renderizza il contenuto nella sezione del piè di pagina del negozio. | Utilizzato per visualizzare il widget Shoutbox nella parte inferiore della pagina. |
| `displayProductButtons` (o hook simile per la pagina prodotto) | Renderizza il contenuto nella pagina del prodotto, spesso vicino al pulsante "aggiungi al carrello" o alla descrizione del prodotto. | Utilizzato per visualizzare lo Shoutbox specificamente sulle pagine dei prodotti per discussioni relative ai prodotti. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller frontale imposta i suoi media (CSS/JS). | Utilizzato per registrare JavaScript specifici del modulo (`advajax.js`, `script.js`) e qualsiasi potenziale file CSS da caricare nel front office. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo Shoutbox, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto dedicato è pronto ad assisterti per qualsiasi problema o domanda tu possa avere.
