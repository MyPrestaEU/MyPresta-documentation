---
title: "HM Revenue & Customs (HMRC) - tassi di cambio valuta - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop HM Revenue & Customs (HMRC) - tassi di cambio valuta di MyPresta.eu."
sidebar:
  label: "HM Revenue & Customs (HMRC) - tassi di cambio valuta - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo HM Revenue & Customs (HMRC) - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/hm-revenue-customs-hmrc-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/hm-revenue-customs-hmrc-currency-exchange-rates/)
>
> ---


# HM Revenue & Customs (HMRC) - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni, che sono standard nella maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale del modulo Tassi di cambio HMRC. Qui imposterai come il modulo recupera e applica i tassi di cambio ufficiali.

La pagina di configurazione ti presenterà le seguenti informazioni e impostazioni chiave:

#### **URL del Cron Job**

-   **Cosa fa questa impostazione:** Questo è un indirizzo web speciale (URL) che, quando visitato, attiva il modulo per recuperare gli ultimi tassi di cambio HMRC e aggiornarli nel tuo negozio PrestaShop. È progettato per essere eseguito automaticamente da un "cron job" sul tuo server.
-   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. Viene generato dal modulo.
-   **Valore consigliato:** Copia questo URL esattamente come appare.
-   **Scenario/esempio del commerciante:** Avrai bisogno di questo URL per impostare un'attività automatizzata (cron job) sul server del tuo hosting web. Questa attività visiterà l'URL a un orario programmato (ad esempio, una volta al giorno o una volta al mese) per garantire che i tuoi tassi siano sempre aggiornati senza che tu debba cliccare manualmente nulla.

#### **Comando Cron Job (per server Linux/Unix)**

-   **Cosa fa questa impostazione:** Questa è un'istruzione da riga di comando che ottiene lo stesso risultato della visita dell'URL del Cron Job, ma è specificamente formattata per l'uso diretto in uno scheduler di cron job del server (spesso presente nel pannello di controllo del tuo hosting come cPanel o Plesk). Utilizza `wget` o `curl` per richiedere silenziosamente l'URL.
-   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo comando. Viene generato dal modulo.
-   **Valore consigliato:** Copia questo comando esattamente come appare.
-   **Scenario/esempio del commerciante:** Se il tuo provider di hosting utilizza server Linux/Unix (come la maggior parte), utilizzerai questo comando per impostare il tuo cron job automatizzato. Questo è generalmente più affidabile che affidarsi a servizi cron basati sul web.

#### **Stato Ultimo Aggiornamento**

-   **Cosa fa questa impostazione:** Questa sezione visualizza informazioni su quando il modulo ha recuperato e aggiornato con successo i tassi HMRC l'ultima volta. Mostrerà la data e l'ora dell'ultimo aggiornamento.
-   **Effetto della modifica di questa impostazione:** Questo è solo un display informativo; non puoi modificarlo.
-   **Valore consigliato:** Monitora questo per assicurarti che il tuo cron job sia in esecuzione correttamente e che i tassi vengano aggiornati regolarmente.
-   **Scenario/esempio del commerciante:** Se imposti il tuo cron job per l'esecuzione giornaliera, dovresti vedere lo "Stato Ultimo Aggiornamento" cambiare quotidianamente, confermando che il modulo funziona come previsto. Se non si aggiorna, indica un problema con la configurazione del tuo cron job.

#### **Pulsante "Aggiorna Ora"**

-   **Cosa fa questa impostazione:** Questo pulsante ti consente di attivare manualmente il processo di aggiornamento dei tassi immediatamente, direttamente dalla pagina di configurazione del modulo.
-   **Effetto della modifica di questa impostazione:** Cliccando questo pulsante verranno recuperati istantaneamente gli ultimi tassi HMRC e applicati alle valute del tuo negozio.
-   **Valore consigliato:** Utilizza questo pulsante per i test iniziali dopo l'installazione, o se hai bisogno di forzare un aggiornamento immediato al di fuori del tuo cron job programmato.
-   **Scenario/esempio del commerciante:** Dopo aver installato il modulo, clicca su "Aggiorna Ora" per vedere se recupera correttamente i tassi e per popolare il tuo negozio con gli ultimi tassi HMRC prima che venga eseguito il tuo primo cron job programmato.

#### **Nota importante sui Cron Job:**

La funzionalità principale di questo modulo si basa sull'impostazione di un **cron job** sul tuo server web. Un cron job è uno scheduler di processi basato sul tempo nei sistemi operativi simili a Unix. Consente agli utenti di programmare l'esecuzione periodica di processi (comandi o script) a orari, date o intervalli fissi.

**Come impostare un cron job (passaggi generali):**

1.  **Accedi al tuo Pannello di Controllo Hosting:** Accedi al tuo cPanel, Plesk o altro pannello di controllo hosting.
2.  **Trova "Cron Jobs" o "Attività pianificate":** Cerca una sezione solitamente denominata "Cron Jobs", "Attività pianificate" o "Automazione".
3.  **Aggiungi un nuovo Cron Job:**
    -   **Frequenza:** Imposta la frequenza. Per i tassi HMRC, mensile è solitamente sufficiente (ad esempio, "Una volta al mese" il 1° giorno del mese). Alcuni commercianti preferiscono giornaliero per maggiore sicurezza, ma i tassi HMRC sono mensili.
    -   **Comando:** Incolla il "Comando Cron Job" fornito dal modulo nel campo del comando.
    -   **Email:** Di solito puoi specificare un indirizzo email per ricevere l'output del cron job. Questo è utile per la risoluzione dei problemi se il job fallisce.
4.  **Salva:** Salva il cron job.

Se non sei sicuro su come impostare un cron job, contatta il team di supporto del tuo provider di hosting e fornisci loro il "Comando Cron Job" dalla pagina di configurazione del modulo, chiedendo loro di impostarlo per l'esecuzione mensile (o giornaliera, secondo le tue preferenze).

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | URL Cron Job | N/A (Copia e Usa) | URL per attivare l'aggiornamento dei tassi; per servizi cron basati sul web. |
| Configurazione Modulo | Comando Cron Job | N/A (Copia e Usa) | Istruzione da riga di comando per cron job basati su server (es. cPanel). |
| Configurazione Modulo | Stato Ultimo Aggiornamento | N/A (Informativo) | Mostra data/ora dell'ultimo aggiornamento riuscito dei tassi. |
| Configurazione Modulo | Pulsante "Aggiorna Ora" | Clicca per aggiornamento manuale | Recupera e applica immediatamente gli ultimi tassi HMRC. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei tassi di cambio non si aggiornano. Cosa devo fare?**
R: La ragione più comune è un cron job configurato in modo errato.
1.  **Controlla la configurazione del tuo cron job:** Accedi al tuo pannello di controllo hosting (cPanel, Plesk, ecc.) e verifica che il cron job sia configurato correttamente utilizzando il "Comando Cron Job" fornito dal modulo. Assicurati che la frequenza sia impostata come desiderato (ad esempio, mensile o giornaliera).
2.  **Testa manualmente:** Vai alla pagina di configurazione del modulo nel back office di PrestaShop e clicca sul pulsante "Aggiorna Ora". Se questo funziona, il problema è sicuramente nella configurazione del tuo cron job. Se non funziona, potrebbe esserci un problema lato server che impedisce al modulo di recuperare i dati (ad esempio, firewall, problemi cURL).
3.  **Contatta il tuo host:** Se non sei sicuro dei cron job, fornisci al supporto del tuo hosting il "Comando Cron Job" e chiedi loro di configurarlo per te.

**D: Questo modulo influisce sui prezzi che i clienti vedono sul mio sito web?**
R: Sì, indirettamente. Il modulo aggiorna i tassi di cambio sottostanti in PrestaShop. Se il tuo negozio consente ai clienti di passare da una valuta all'altra, i prezzi visualizzati in quelle valute estere rifletteranno i tassi aggiornati. Tuttavia, lo scopo principale del modulo è per la contabilità *interna* e la conformità fiscale, non necessariamente per strategie di prezzo dinamiche sul front-end.

**D: Cosa succede se l'HMRC cambia il suo metodo di pubblicazione dei tassi di cambio?**
R: MyPresta.eu monitora regolarmente i cambiamenti ai servizi esterni come l'HMRC. Se l'HMRC altera la sua fonte di dati o il formato, rilasceremo un aggiornamento al modulo per garantire la compatibilità continua. Mantieni sempre i tuoi moduli aggiornati alle loro ultime versioni.

**D: Posso usare questo modulo se la mia valuta base non è GBP?**
R: Sebbene il modulo recuperi i tassi HMRC, il suo vantaggio principale è per la conformità IVA del Regno Unito, che tipicamente assume GBP come valuta di rendicontazione. Se la tua valuta base non è GBP, il modulo aggiornerà comunque i tassi di cambio per altre valute rispetto alla tua valuta base, ma dovrai capire come questo interagisce con i tuoi specifici obblighi di rendicontazione fiscale. Per l'IVA del Regno Unito, avere GBP come valuta predefinita è generalmente consigliato.

**D: Visualizzo un messaggio di errore quando cerco di aggiornare i tassi manualmente.**
R: Questo potrebbe indicare alcune cose:
1.  **Connettività del server:** Il tuo server potrebbe non essere in grado di connettersi al sito web dell'HMRC per recuperare i dati. Ciò potrebbe essere dovuto a un firewall, un problema di rete o un'interruzione temporanea del server HMRC.
2.  **Estensioni PHP:** Assicurati che le estensioni PHP standard come `cURL` e `JSON` siano abilitate sul tuo server.
3.  **Permessi del modulo:** Controlla che i file del modulo abbiano i permessi di lettura/scrittura corretti.
Se il problema persiste, contatta il supporto MyPresta.eu con il messaggio di errore esatto.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster responsabili della manutenzione o dell'estensione del negozio PrestaShop.

### 4.1 Panoramica dell'architettura

Il modulo `hmrcrates` è un modulo PrestaShop semplice progettato per recuperare e aggiornare i tassi di cambio valuta dal sito web dell'HMRC. Sfrutta l'architettura dei moduli di PrestaShop, utilizzando principalmente la classe `Module` per l'installazione/disinstallazione e `ModuleFrontController` per la gestione delle richieste di cron job. La logica principale risiede nel file del modulo principale, `cronjob.php`, che funge anche da punto di ingresso primario per la configurazione e l'esecuzione del cron. Non utilizza `ObjectModel` in quanto manipola direttamente gli oggetti `Currency` esistenti.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe padre**: `HmrcratesCronjobModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è l'endpoint pubblico per il cron job. Quando viene acceduto tramite il suo URL (ad esempio, `iltuonegozio.com/module/hmrcrates/cronjob`), attiva il metodo `processUpdateRates()` nel modulo `hmrcrates` principale. È progettato per essere chiamato da servizi cron esterni o cron job lato server. Restituisce un semplice messaggio di successo o di errore.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre**: `HmrcratesIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo è un controller segnaposto, tipicamente utilizzato per fornire un punto di ingresso predefinito per un modulo se non viene richiesta alcuna azione specifica. Nel contesto di questo modulo, probabilmente non ha uno scopo funzionale diretto se non quello di fornire una rotta predefinita se `cronjob.php` non viene chiamato esplicitamente. Potrebbe reindirizzare o semplicemente visualizzare una pagina vuota.
-   **Controller Admin Back-Office**:

    -   Questo modulo non utilizza file `AdminController` dedicati. Tutta la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` della classe del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce alcuna classe personalizzata all'interno della directory `classes/`. La logica principale per il recupero e l'aggiornamento dei tassi è incapsulata all'interno del file del modulo principale, `hmrcrates/cronjob.php`. Interagisce direttamente con la classe `Currency` integrata di PrestaShop per aggiornare i tassi di cambio.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. La configurazione del back-office si basa sullo stile predefinito del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `views/templates/admin/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` della classe del modulo principale (`hmrcrates/cronjob.php`) per visualizzare il modulo di configurazione del modulo nel back office di PrestaShop.
        -   **Contenuti**: Tipicamente include la struttura HTML per visualizzare l'URL del Cron Job, il Comando del Cron Job, lo Stato dell'Ultimo Aggiornamento e il pulsante "Aggiorna Ora". Utilizza gli helper di modulo e lo stile standard di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione (ad esempio, `HMRCRATES_LAST_UPDATE`) nella tabella standard `ps_configuration` di PrestaShop.
    -   Aggiorna la colonna `exchange_rate` nella tabella `ps_currency` per le valute pertinenti.
-   **Tabella degli hook registrati**:
    Questo modulo non registra esplicitamente alcun hook di visualizzazione del front-office (come `displayHeader`, `displayRightColumn`, `displayFooter`) poiché la sua funzionalità è puramente orientata al backend. Il suo "hook" principale è l'hook `action` attivato dal `ModuleFrontController` per il cron job.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante l'installazione del modulo | Crea voci di configurazione, imposta i dati iniziali. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce le voci di configurazione. |
| (Implicito) `actionFrontControllerSetMedia` | Quando viene caricato un controller frontale | Non esplicitamente utilizzato da questo modulo, ma standard per i moduli per caricare risorse. |
| (Implicito) `actionDispatcher` | Quando viene inviato un controller frontale | Il `ModuleFrontController` `HmrcratesCronjobModuleFrontController` viene inviato quando si accede all'URL del cron, attivando la logica di aggiornamento dei tassi. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "HM Revenue & Customs (HMRC) - tassi di cambio valuta", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità o alla configurazione del modulo.
