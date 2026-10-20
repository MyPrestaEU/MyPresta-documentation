---
title: "Aggiornamento tassi di cambio NBP - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop di aggiornamento tassi di cambio NBP di MyPresta.eu."
sidebar:
  label: "Aggiornamento tassi di cambio NBP - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo NBP currency rates update su MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbp-currency-rates-update.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/nbp-currency-rates-update/)
>
> ---


# Aggiornamento tassi di cambio NBP

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Sono generalmente richieste estensioni PHP standard come cURL, JSON e OpenSSL, e sono standard nella maggior parte degli ambienti di hosting web moderni. Il tuo hosting deve anche supportare l'impostazione di cron job.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Aggiornamento tassi di cambio NBP". Ti verrà presentata la schermata di configurazione principale.

#### **URL Cron Job**

-   **Cosa fa questa impostazione:** Visualizza un URL unico che utilizzerai per impostare un'attività automatizzata (un "cron job") sul tuo server web. Quando si accede a questo URL, il modulo si connetterà ai server NBP, recupererà i tassi di cambio più recenti e li aggiornerà nel tuo negozio PrestaShop.
-   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. Viene generato dal modulo.
-   **Valore consigliato:** Copia questo URL esattamente come appare.
-   **Scenario / esempio del commerciante:** Prenderai questo URL e lo incollerai nella sezione "Cron Jobs" del pannello di controllo del tuo hosting (ad esempio, cPanel, Plesk o una configurazione cron personalizzata del server). Questo indica al tuo server di visitare questo URL a intervalli specificati (ad esempio, ogni giorno alle 3 del mattino), attivando automaticamente il processo di aggiornamento della valuta.

#### **Frequenza Cron Job**

-   **Cosa fa questa impostazione:** Questa non è un'impostazione che modifichi *all'interno* di PrestaShop, ma piuttosto una raccomandazione su quanto spesso dovresti impostare il cron job del tuo server per chiamare l'URL.
-   **Effetto della modifica di questa impostazione:** Questo testo ti fornisce semplicemente un consiglio. La frequenza effettiva è controllata dalla configurazione del cron job del tuo server.
-   **Valore consigliato:** "Una volta al giorno" è generalmente sufficiente per la maggior parte dei negozi, poiché i tassi NBP si aggiornano tipicamente quotidianamente.
-   **Scenario / esempio del commerciante:** Se imposti il cron job del tuo server per l'esecuzione giornaliera, i tassi di cambio del tuo negozio verranno aggiornati una volta ogni 24 ore, assicurando che siano sempre aggiornati con i dati NBP. Eseguirlo più frequentemente (ad esempio, ogni ora) è solitamente inutile e potrebbe sovraccaricare il tuo server o l'API NBP.

#### **Nota importante sui Cron Job**

-   **Cosa fa questa impostazione:** Questa sezione fornisce istruzioni cruciali su come impostare il cron job sul tuo server. Spiega che devi accedere al pannello di controllo del tuo hosting (come cPanel o Plesk) e aggiungere un nuovo cron job.
-   **Effetto della modifica di questa impostazione:** Questo è un testo informativo. Devi seguire queste istruzioni al di fuori di PrestaShop.
-   **Valore consigliato:** Leggi attentamente e segui i passaggi forniti dal tuo provider di hosting per l'impostazione dei cron job.
-   **Scenario / esempio del commerciante:** Il tuo provider di hosting avrà una sezione, solitamente chiamata "Cron Jobs" o "Attività pianificate", dove puoi aggiungere un nuovo comando. Tipicamente sceglierai una frequenza (ad esempio, "Una volta al giorno"), e poi incollerai l'"URL Cron Job" nel campo del comando, spesso preceduto da `wget -q -O /dev/null`. Se non sei sicuro, contatta il supporto del tuo provider di hosting.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | URL Cron Job | (URL unico) | L'URL per attivare gli aggiornamenti automatici della valuta tramite un cron job del server. Copialo per la configurazione del tuo server. |
| Configurazione Modulo | Frequenza Cron Job | Una volta al giorno | Raccomandazione su quanto spesso eseguire il cron job sul tuo server per mantenere i tassi aggiornati. |
| Configurazione Modulo | Istruzioni per la configurazione del Cron Job | N/A | Guida su come configurare il cron job sul tuo server di web hosting. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: I miei tassi di cambio non si aggiornano, anche dopo aver impostato il cron job. Cosa devo fare?**
R:

1.  **Controlla l'URL del Cron Job:** Assicurati di aver copiato l'URL esattamente dalla pagina di configurazione del modulo e di averlo incollato correttamente nelle impostazioni del cron job del pannello di controllo del tuo hosting.
2.  **Verifica l'esecuzione del Cron Job:** Controlla i log del cron job del tuo provider di hosting (se disponibili) per vedere se il cron job sta effettivamente funzionando all'ora programmata. A volte, il comando potrebbe essere errato o il percorso a `wget` potrebbe richiedere una regolazione.
3.  **Test manuale:** Prova a visitare l'"URL del Cron Job" direttamente nel tuo browser web. Questo dovrebbe attivare un aggiornamento immediato. Se i tassi si aggiornano dopo una visita manuale, il problema è nella configurazione del cron job del tuo server, non nel modulo stesso.
4.  **Controlla le valute di PrestaShop:** Assicurati che le valute che desideri aggiornare siano abilitate in PrestaShop (**Internazionale > Valute**) e che abbiano un codice ISO valido che NBP possa riconoscere (ad esempio, USD, EUR, GBP).
5.  **Svuota la cache:** A volte, la cache di PrestaShop potrebbe impedirti di vedere i cambiamenti immediati. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache".

**D: Questo modulo aggiorna tutte le valute nel mio negozio?**
R: Aggiorna le valute per le quali NBP fornisce tassi di cambio, rispetto al PLN. Il modulo è abbastanza intelligente da convertire questi tassi nella valuta predefinita del tuo negozio. Ad esempio, se la tua valuta predefinita è EUR e NBP fornisce USD/PLN ed EUR/PLN, il modulo può calcolare USD/EUR. Se NBP non fornisce un tasso per una valuta specifica, il tasso di quella valuta non verrà aggiornato da questo modulo.

**D: Posso impostare la frequenza di aggiornamento più spesso di una volta al giorno?**
R: Sebbene tu possa configurare il cron job del tuo server per l'esecuzione più frequente (ad esempio, ogni ora), i tassi di cambio NBP si aggiornano tipicamente una volta al giorno. Eseguire il cron job più spesso di una volta al giorno è solitamente inutile e non fornirà dati più freschi, ma non danneggerà nulla.

**D: Ricevo un messaggio di errore quando cerco di configurare il modulo o quando il cron job viene eseguito.**
R:

1.  **Controlla la versione PHP:** Assicurati che la tua versione PHP rientri nell'intervallo supportato (PHP 5.6 - 8.5).
2.  **Connettività del server:** Il modulo deve connettersi al sito web NBP per recuperare i tassi. Assicurati che il tuo server abbia accesso a Internet in uscita e non sia bloccato da un firewall dall'accesso a URL esterni.
3.  **Modalità Debug di PrestaShop:** Abilita la modalità debug di PrestaShop (**Parametri Avanzati > Prestazioni > Modalità debug**) per visualizzare messaggi di errore più dettagliati, che possono aiutare a individuare il problema. Ricorda di disabilitarla dopo la risoluzione dei problemi.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Aggiornamento tassi di cambio NBP` è un modulo PrestaShop leggero progettato principalmente per eseguire un singolo, critico compito: recuperare e aggiornare i tassi di cambio dalla Banca Nazionale Polacca (NBP) tramite un cron job programmato. Segue una struttura standard dei moduli PrestaShop, sfruttando `ModuleFrontController` per il suo endpoint cron e la classe principale del modulo per la configurazione e l'installazione. La logica centrale risiede nel file `cronjob.php`, che funge sia da classe principale del modulo che da punto di ingresso per l'esecuzione del cron.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `nbprates/controllers/front/cronjob.php`
        -   **Nome classe e classe genitore**: `NbpratesCronjobModuleFrontController` estende `ModuleFrontController`
        -   **Responsabilità**: Questo controller funge da endpoint pubblico per il cron job. Quando vi si accede tramite l'URL unico generato dal modulo, attiva la logica di aggiornamento della valuta. Non renderizza alcun output visivo ma esegue il processo di recupero e aggiornamento dei tassi. È progettato per essere chiamato da `wget` o `curl` da uno scheduler cron del server.
    -   `nbprates/controllers/front/index.php`
        -   **Nome classe e classe genitore**: `NbpratesIndexModuleFrontController` estende `ModuleFrontController`
        -   **Responsabilità**: Questo è un controller segnaposto, spesso incluso nei moduli per prevenire l'elenco delle directory se `index.php` non è presente nella directory `controllers/front`. Tipicamente non fa altro che reindirizzare alla home page o visualizzare un errore "404 Not Found". Non contiene alcuna logica di business specifica per questo modulo.
-   **Controller Admin Back-Office**:

    -   Nessuno. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

-   Nessuno. La logica del modulo è principalmente contenuta nel file principale del modulo (`nbprates/cronjob.php`).

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessuno. Il modulo non utilizza alcun JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessuno. Il modulo non utilizza alcun CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `nbprates/views/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` della classe principale del modulo (`NbpratesCronjob`) per visualizzare il modulo di configurazione del modulo nel Back Office di PrestaShop.
        -   **Contenuto**: Tipicamente visualizza l'"URL Cron Job" e le istruzioni per l'impostazione del cron job. È una visualizzazione statica di informazioni piuttosto che un modulo interattivo con campi di input.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea alcuna tabella SQL personalizzata.
    -   Memorizza la sua configurazione (specificamente il token cron generato) nella tabella `ps_configuration`. La chiave per il token cron sarebbe tipicamente `NBP_CRON_TOKEN`.
    -   Aggiorna i tassi di cambio esistenti nella tabella `ps_currency` (specificamente la colonna `conversion_rate`).
-   **Tabella degli hook registrati**:
    Il modulo non si registra esplicitamente a nessun hook di visualizzazione standard di PrestaShop (come `displayHeader`, `displayFooter`, ecc.) per il rendering del front-office. Il suo "hook" principale è l'endpoint `ModuleFrontController` che viene chiamato esternamente dal cron job del server.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `install()` | Durante l'installazione del modulo | Crea il token cron unico e lo memorizza in `ps_configuration`. |
| `uninstall()` | Durante la disinstallazione del modulo | Elimina il token cron da `ps_configuration`. |
| `actionFrontControllerSetMedia` | Non esplicitamente registrato, ma `ModuleFrontController` gestisce implicitamente il caricamento delle risorse se presenti. | N/A (nessuna risorsa viene caricata da questo modulo). |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Aggiornamento tassi di cambio NBP", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo e all'integrazione con il tuo negozio PrestaShop.
