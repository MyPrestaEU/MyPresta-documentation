---
title: "Recupero semplice della password - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Recupero semplice della password di MyPresta.eu."
sidebar:
  label: "Recupero semplice della password - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Simple password recovery su MyPresta.eu](https://mypresta.eu/modules/front-office-features/simple-password-recovery.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/simple-password-recovery/)
>
> ---


# Recupero semplice della password

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Il modulo "Recupero semplice della password" è progettato per essere in gran parte plug-and-play, sostituendo il flusso di recupero della password predefinito di PrestaShop con una configurazione minima richiesta.

Quando navighi su **Moduli > Gestione moduli** e clicchi su "Configura" accanto a "Recupero semplice della password", troverai tipicamente un'interfaccia di configurazione semplice.

**Cosa fa questa impostazione:** Questa schermata ti consente di abilitare o disabilitare la funzionalità principale del modulo e potenzialmente regolare impostazioni comportamentali minori. Lo scopo principale è attivare il processo di recupero della password semplificato.

**Effetto della modifica di questa impostazione:**

- **Quando abilitato:** Il modulo prende il controllo del meccanismo di recupero della password predefinito di PrestaShop. Quando un cliente richiede un ripristino della password, riceverà un'email con un link unico e sicuro che lo indirizza a una pagina dedicata per impostare la sua nuova password. Questo semplifica significativamente l'esperienza utente.
- **Quando disabilitato:** La funzionalità del modulo è disattivata. Il tuo negozio PrestaShop tornerà al suo processo di recupero della password predefinito e standard, che potrebbe comportare più passaggi o diversi metodi di verifica per il cliente.

**Valore consigliato:** **Abilitato (SÌ)**. Il vantaggio principale di questo modulo è semplificare il processo di recupero della password. Mantenerlo abilitato garantisce che i tuoi clienti beneficino di questa esperienza migliorata.

**Scenario / esempio del commerciante:**
Hai notato che i clienti contattano frequentemente il supporto perché hanno difficoltà con il recupero della password predefinito. Abilitando questo modulo, fornisci un link diretto, con un solo clic, nell'email, consentendo loro di impostare istantaneamente una nuova password. Questo riduce la confusione e li riporta allo shopping più velocemente.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Stato del modulo (Abilita/Disabilita) | Abilitato | Attiva o disattiva il processo di recupero della password semplificato. Quando abilitato, i clienti ricevono un link diretto per impostare una nuova password. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non ricevono le email di ripristino della password.**
R:

- **Controlla le cartelle spam:** Consiglia ai clienti di controllare le loro cartelle spam o posta indesiderata.
- **Configurazione email:** Verifica le impostazioni email di PrestaShop in **Parametri avanzati > E-mail**. Assicurati che le tue impostazioni SMTP siano corrette o che la funzione PHP `mail()` funzioni.
- **Conflitti tra moduli:** Disabilita temporaneamente altri moduli che potrebbero interferire con l'invio di email o la gestione degli account clienti per escludere conflitti.
- **Log del server:** Controlla i log di posta del tuo server per eventuali errori relativi alle email in uscita.

**D: Il link di ripristino della password porta i clienti a una pagina vuota o a un errore.**
R:

- **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e svuota la cache di Smarty, la cache del browser e la cache del modulo.
- **Riscrivi URL:** Assicurati che la riscrittura URL sia abilitata in PrestaShop (**Parametri negozio > SEO e URL**) e che il tuo file `.htaccess` sia configurato correttamente.
- **Integrità del modulo:** Ricarica i file del modulo tramite FTP per assicurarti che nessun file sia corrotto o mancante.
- **Compatibilità del tema:** Sebbene raro, un tema altamente personalizzato potrebbe avere conflitti JavaScript. Controlla la console per sviluppatori del tuo browser per eventuali errori JavaScript.

**D: Posso personalizzare l'aspetto della nuova pagina della password?**
R: Sì, il modulo utilizza il templating standard di PrestaShop. L'aspetto è principalmente controllato dal CSS del tuo tema PrestaShop attivo e dal CSS proprio del modulo (`spreset/views/css/spreset.css`). Gli sviluppatori possono sovrascrivere questi stili nel CSS personalizzato del loro tema o modificando i file di template del modulo (`views/templates/front/password-change-form.tpl`, `views/templates/front/simple-reset-page.tpl`, `views/templates/front/simple-reset.tpl`).

**D: Questo modulo funziona con negozi multilingue?**
R: Sì, come la maggior parte dei moduli PrestaShop, le stringhe di testo sono traducibili. Puoi tradurre le frasi del modulo tramite **Internazionale > Traduzioni** nel tuo Back Office, selezionando "Traduzioni dei moduli installati" e quindi trovando "Recupero semplice della password".

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Recupero semplice della password".

### 4.1 Panoramica dell'architettura

Il modulo "Recupero semplice della password" sovrascrive il meccanismo di recupero della password predefinito di PrestaShop introducendo controller front-end personalizzati per gestire la generazione del token, l'invio dell'email e il processo di impostazione della nuova password. Sfrutta il pattern MVC di PrestaShop, con controller dedicati per le diverse fasi del recupero. Il file principale del modulo (`index.php`) gestisce l'installazione, la disinstallazione e il modulo di configurazione principale.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `controllers/front/changepass.php`
    - **Nome classe**: `SpresetChangepassModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller è responsabile della visualizzazione del modulo in cui un cliente può impostare la propria nuova password dopo aver cliccato sul link di ripristino sicuro. Convalida il token fornito nell'URL e gestisce l'invio della nuova password.
  - `controllers/front/index.php`
    - **Nome classe**: `SpresetIndexModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller probabilmente funge da fallback o da punto di ingresso generale per la funzionalità front-office del modulo, potenzialmente reindirizzando o gestendo le richieste iniziali relative al processo di ripristino della password. In molti casi, potrebbe essere un segnaposto o utilizzato per un routing specifico.
  - `controllers/front/simplereset.php`
    - **Nome classe**: `SpresetSimpleresetModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller è il cuore del processo di ripristino semplificato. Riceve la richiesta iniziale di ripristino della password (ad esempio, dal modulo standard "Password dimenticata" di PrestaShop), genera il token sicuro, invia l'email con il link di ripristino unico e gestisce la convalida iniziale dell'indirizzo email del cliente.
- **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non sembra definire classi personalizzate che estendono `ObjectModel` o altre classi principali di PrestaShop all'interno di una directory `classes/` dedicata. La sua logica è principalmente incapsulata all'interno del file principale del modulo e dei suoi controller front-end.

### 4.4 Risorse JavaScript (`views/js/`)

- `views/js/spreset.js`
  - **Ambito**: Front-office.
  - **Dettagli**: Questo script probabilmente gestisce la convalida lato client per il modulo della nuova password (ad esempio, controllando se le password corrispondono, i requisiti di lunghezza minima) e potenzialmente gli invii AJAX per la modifica della password. Potrebbe anche includere miglioramenti dell'interfaccia utente o interazioni specifiche per la pagina di ripristino della password. Gli sviluppatori dovrebbero ispezionare questo file per specifici listener di eventi (ad esempio, `submit` sul modulo della password) e qualsiasi funzione personalizzata.

### 4.5 Fogli di stile CSS (`views/css/`)

- `views/css/spreset.css`
  - **Ambito**: Styling del cliente front-office.
  - **Dettagli**: Questo foglio di stile fornisce uno styling specifico per i componenti front-office del modulo, principalmente il modulo di inserimento della nuova password e le pagine associate. Garantisce che l'interfaccia di recupero della password abbia un aspetto presentabile e si integri ragionevolmente bene con vari temi. Gli sviluppatori possono ispezionare questo file per identificare i selettori di classe CSS chiave (ad esempio, `.spreset-form`, `.spreset-input`, `.spreset-button`) che possono essere sovrascritti nel file CSS personalizzato del loro tema per corrispondere al branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template Front-office (`views/templates/front/`)**:

  - `views/templates/front/password-change-form.tpl`
    - **Scopo**: Questo template probabilmente renderizza il modulo effettivo in cui il cliente inserisce e conferma la propria nuova password. Contiene campi di input per "Nuova password" e "Conferma nuova password", insieme a un pulsante di invio.
  - `views/templates/front/simple-reset-page.tpl`
    - **Scopo**: Questo template potrebbe fungere da wrapper principale o layout per il processo di ripristino della password semplificato, potenzialmente includendo messaggi, istruzioni e incorporando altri template parziali come `password-change-form.tpl`.
  - `views/templates/front/simple-reset.tpl`
    - **Scopo**: Simile a `simple-reset-page.tpl`, questo template fa parte della visualizzazione front-office per il flusso di ripristino della password. Potrebbe essere utilizzato per il modulo iniziale "inserisci la tua email" o per visualizzare messaggi di successo/errore relativi alla richiesta di ripristino.
- **Template specifici del modulo (`views/templates/`)**:

  - `views/templates/spreset.tpl`
    - **Scopo**: Questo template è probabilmente utilizzato per la configurazione principale del modulo nel Back Office (se `getContent()` renderizza un template) o per un hook di visualizzazione generico se il modulo ha un output semplice per un hook. Data la natura del modulo, è più probabile per la configurazione del Back Office.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Il modulo non sembra creare tabelle SQL personalizzate. Probabilmente utilizza tabelle PrestaShop esistenti (ad esempio, `ps_customer` per i dati dei clienti, `ps_configuration` per le impostazioni del modulo) e genera token temporanei senza archiviazione persistente in una tabella dedicata. I token sono tipicamente archiviati nella sessione o passati tramite parametri URL con una breve scadenza.
- **Tabella degli hook registrati**:
  Il modulo non elenca esplicitamente gli hook registrati nelle informazioni fornite, ma in base alla sua funzionalità, interagirebbe implicitamente con il flusso di recupero della password standard di PrestaShop, che è spesso attivato dagli hook `displayCustomerAccountForm` o `actionAuthenticationBefore`, o sovrascrivendo i controller principali di PrestaShop.
  Il file principale del modulo (`index.php`) registrerebbe i suoi controller front-end per gestire percorsi specifici, "agganciandosi" efficacemente al sistema di routing URL piuttosto che agli hook tradizionali `display` o `action` per l'output visivo.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Recupero semplice della password", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire le prestazioni e la compatibilità ottimali dei nostri moduli con le ultime versioni di PrestaShop.
"""
