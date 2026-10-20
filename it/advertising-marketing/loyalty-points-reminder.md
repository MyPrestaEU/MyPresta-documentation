---
title: "Promemoria punti fedeltà - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Promemoria punti fedeltà di MyPresta.eu."
sidebar:
  label: "Promemoria punti fedeltà - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Loyalty points reminder su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-reminder.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/loyalty-points-reminder/)
>
> ---


# Promemoria punti fedeltà

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Il modulo si basa sulle funzioni di posta nativa di PrestaShop e sulle capacità dei cron job.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Promemoria punti fedeltà)

Questa è la schermata di configurazione principale e unica per il modulo "Promemoria punti fedeltà". Qui definirai come e quando vengono inviate le email di promemoria.

#### **Abilita / Disabilita Modulo**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo controllerà attivamente i punti fedeltà in scadenza e invierà email di promemoria in base alle altre impostazioni.
    -   *Quando disabilitato:* Il modulo non invierà alcuna email di promemoria, indipendentemente dalle altre impostazioni.
-   **Valore consigliato:** SÌ (una volta configurate le altre impostazioni).
-   **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi iniziare a ricordare i clienti. Lo abiliteresti dopo aver impostato i giorni prima della scadenza.

#### **Giorni prima della scadenza per inviare il promemoria**

-   **Cosa fa questa impostazione:** Determina quanti giorni *prima* della scadenza dei punti fedeltà di un cliente verrà inviata l'email di promemoria.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su 7:* I clienti riceveranno un'email 7 giorni prima della scadenza dei loro punti.
    -   *Se impostato su 30:* I clienti riceveranno un'email 30 giorni prima della scadenza dei loro punti.
-   **Valore consigliato:** 7-14 giorni. Questo dà ai clienti abbastanza tempo per reagire senza essere troppo in anticipo da dimenticare.
-   **Scenario / esempio del commerciante:** Vuoi dare ai clienti una settimana per utilizzare i loro punti. Imposteresti questo valore su "7". Se vuoi dare loro più margine, forse "14".

#### **URL del Cron Job**

-   **Cosa fa questa impostazione:** Visualizza un URL unico che devi configurare come cron job sul tuo server. Un cron job è un'attività pianificata che indica al tuo server di eseguire uno script specifico a intervalli regolari (ad esempio, una volta al giorno). È così che il modulo controlla automaticamente i punti in scadenza e invia le email senza che tu debba fare nulla manualmente.
-   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questa impostazione. È un URL generato.
    -   *Se il cron job è configurato correttamente:* Il modulo verrà eseguito automaticamente, inviando email come configurato.
    -   *Se il cron job NON è configurato:* Il modulo non invierà mai alcuna email di promemoria, anche se abilitato.
-   **Valore consigliato:** Copia questo URL e impostalo come cron job giornaliero sul tuo server di hosting.
-   **Scenario / esempio del commerciante:** Dopo aver configurato l'impostazione "Giorni prima della scadenza", copieresti questo URL e lo incolleresti nello scheduler dei cron job del tuo pannello di controllo di hosting (ad esempio, cPanel, Plesk o accesso diretto al server). Tipicamente lo imposteresti per essere eseguito una volta ogni 24 ore.

#### **Indirizzo email di prova**

-   **Cosa fa questa impostazione:** Ti consente di inviare un'email di promemoria di prova a un indirizzo specifico per assicurarti che il modulo funzioni correttamente e che il contenuto dell'email sia buono.
-   **Effetto della modifica di questa impostazione:**
    -   *Inserendo un'email e cliccando su "Invia email di prova":* Verrà inviata un'email all'indirizzo specificato, simulando un promemoria dei punti fedeltà. Questa email conterrà dati segnaposto in quanto è una prova.
-   **Valore consigliato:** Usa il tuo indirizzo email o quello di un collega per i test.
-   **Scenario / esempio del commerciante:** Prima di andare online, vuoi vedere come appare l'email di promemoria. Inseriresti il tuo indirizzo email qui e cliccheresti sul pulsante di prova.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Abilita / Disabilita Modulo** | SÌ | Interruttore principale per attivare o disattivare le email di promemoria. |
| Configurazione modulo | **Giorni prima della scadenza per inviare il promemoria** | 7-14 giorni | Definisce quanti giorni prima della scadenza dei punti viene inviata l'email. |
| Configurazione modulo | **URL del Cron Job** | Copia e imposta giornalmente | Essenziale per l'invio automatico delle email; deve essere configurato sul tuo server. |
| Configurazione modulo | **Indirizzo email di prova** | La tua email per i test | Invia un'email di promemoria di esempio per verificare il contenuto e la consegna. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non ricevono le email di promemoria. Cosa dovrei controllare?**
R:

1.  **Il modulo è abilitato?** Vai alla configurazione del modulo e assicurati che "Abilita / Disabilita Modulo" sia impostato su SÌ.
2.  **Il cron job è configurato correttamente?** Questo è il problema più comune. Il modulo si basa su un cron job per funzionare automaticamente. Copia l'"URL del Cron Job" dalla configurazione del modulo e assicurati che sia configurato correttamente sul tuo server di hosting per essere eseguito quotidianamente.
3.  **Controlla le impostazioni email di PrestaShop:** Vai su **Parametri avanzati > E-mail** nel tuo Back Office. Invia un'email di prova da lì per assicurarti che il sistema email del tuo negozio funzioni.
4.  **Controlla le cartelle spam:** Chiedi ai clienti di controllare le loro cartelle spam o posta indesiderata.
5.  **Svuota la cache di Smarty:** A volte, le modifiche ai modelli o gli aggiornamenti dei moduli richiedono lo svuotamento della cache. Vai su **Parametri avanzati > Prestazioni**, scorri fino a "Svuota la cache" e clicca su "Svuota la cache".

**D: L'email di prova funziona, ma i clienti non ricevono ancora i promemoria.**
R: Questo suggerisce fortemente che il problema è il cron job. L'email di prova utilizza l'invio immediato della posta di PrestaShop, mentre i promemoria effettivi dipendono dall'esecuzione del processo in background del modulo da parte del cron job. Ricontrolla la configurazione del tuo cron job con il tuo provider di hosting.

**D: Posso personalizzare il contenuto dell'email di promemoria?**
R: Il modulo utilizza i modelli di email standard di PrestaShop. Tipicamente troveresti i file del modello di email nella directory `mails/` del tuo tema (ad esempio, `themes/yourtheme/mails/en/loyalty_points_reminder.html` e `loyalty_points_reminder.txt`). Se questi non esistono, il modulo utilizzerà i modelli di posta predefiniti di PrestaShop. Puoi sovrascriverli nel tuo tema per personalizzare il testo e l'aspetto.

**D: Cosa succede se un cliente non ha punti fedeltà?**
R: Il modulo è progettato per inviare email solo ai clienti che hanno effettivamente punti fedeltà che si avvicinano alla data di scadenza. Se un cliente non ha punti, o i suoi punti non scadono presto, non riceverà un'email.

**D: Questo modulo funziona con moduli di punti fedeltà personalizzati?**
R: Questo modulo è progettato per funzionare con il sistema nativo di punti fedeltà di PrestaShop. Se utilizzi un modulo di fidelizzazione di terze parti, potrebbe non integrarsi direttamente a meno che quel modulo non estenda o utilizzi specificamente le funzionalità di fidelizzazione principali di PrestaShop in modo compatibile.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Promemoria punti fedeltà".

### 4.1 Panoramica dell'architettura

Il modulo "Promemoria punti fedeltà" (`lpreminder`) è un modulo PrestaShop standard che segue un modello simile a MVC. La sua funzionalità principale ruota attorno a un'attività pianificata (cron job) che attiva un front controller per elaborare i punti fedeltà in scadenza e inviare email. Sfrutta le classi native `LoyaltyModule` e `Mail` di PrestaShop.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller sono progettati per essere accessibili tramite un URL specifico, principalmente per l'esecuzione di cron job.

-   **`controllers/front/cronjob.php`**
    -   **Nome classe e classe padre:** `LpreminderCronjobModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo è l'endpoint critico per il cron job. Quando viene acceduto, esegue la logica del modulo per identificare i clienti con punti fedeltà in scadenza e invia le email di promemoria. Idealmente dovrebbe essere protetto (ad esempio, da un token o una restrizione IP) se non già implementato dal modulo per prevenire accessi non autorizzati. Non rende alcun output visivo ma esegue l'elaborazione in background.
-   **`controllers/front/index.php`**
    -   **Nome classe e classe padre:** `LpreminderIndexModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller potrebbe fungere da punto di ingresso predefinito o da segnaposto. In molti moduli, se un'azione specifica non è definita, `index.php` potrebbe gestirla. Data la funzione primaria del modulo, `cronjob.php` è il principale front controller operativo. Questo `index.php` potrebbe essere un fallback o utilizzato per future estensioni.

#### Controller Admin Back-Office

Il modulo non utilizza alcun controller Admin personalizzato. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce classi personalizzate o `ObjectModel` nella directory `classes/`. Interagisce direttamente con le classi principali di PrestaShop, in particolare:

-   `LoyaltyModule`: Per recuperare i punti fedeltà del cliente e le loro date di scadenza.
-   `Customer`: Per recuperare i dettagli del cliente per l'invio di email.
-   `Mail`: Per inviare le email di promemoria.
-   `Configuration`: Per archiviare e recuperare le impostazioni del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non include alcun file JavaScript personalizzato. Tutte le funzionalità sono gestite lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato. La pagina di configurazione utilizza lo stile predefinito del Back Office di PrestaShop.

### 4.6 Struttura del modello Smarty (`views/templates/`)

Il modulo non include alcun file di modello Smarty personalizzato nella sua directory `views/templates/`.

-   **Modelli di email:** Il modulo si basa sul sistema di modelli di email predefinito di PrestaShop. Il contenuto dell'email per il promemoria viene generato utilizzando un modello chiamato `loyalty_points_reminder`. Gli sviluppatori possono personalizzare questa email creando o sovrascrivendo i seguenti file nella directory `mails/` del loro tema attivo:
    -   `themes/yourtheme/mails/en/loyalty_points_reminder.html` (per il contenuto dell'email HTML)
    -   `themes/yourtheme/mails/en/loyalty_points_reminder.txt` (per il contenuto dell'email in testo semplice)
    -   Sostituire `en` con il codice lingua appropriato.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle del database personalizzate. Memorizza le sue impostazioni di configurazione (ad esempio, `PS_LPREMINDER_DAYS_BEFORE_EXPIRY`, `PS_LPREMINDER_ENABLED`) nella tabella `ps_configuration`. Interroga le tabelle PrestaShop esistenti come `ps_loyalty_history` e `ps_customer`.
-   **Tabella degli hook registrati**:
    Il modulo utilizza principalmente l'hook `actionFrontControllerSetMedia` per l'eventuale inclusione futura di JS/CSS (anche se attualmente non presenti) e si basa implicitamente sul meccanismo del cron job per la sua funzionalità principale, che non è un hook tradizionale di PrestaShop ma un trigger esterno a un front controller.

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Rende il contenuto nella sezione `<head>` delle pagine del front-office. | Non utilizzato direttamente per la logica principale del modulo, ma potrebbe essere utilizzato per JS/CSS se necessario. |
| `displayRightColumn` | Rende il contenuto nella colonna destra delle pagine del front-office. | Non utilizzato direttamente per la logica principale del modulo. |
| `displayLeftColumn` | Rende il contenuto nella colonna sinistra delle pagine del front-office. | Non utilizzato direttamente per la logica principale del modulo. |
| `displayFooter` | Rende il contenuto nel piè di pagina delle pagine del front-office. | Non utilizzato direttamente per la logica principale del modulo. |
| `displayProductExtraContent` | Rende il contenuto nella pagina del prodotto. | Non utilizzato direttamente per la logica principale del modulo. |
| `actionFrontControllerSetMedia` | Eseguito quando un front controller sta impostando i suoi media (JS/CSS). | Consente al modulo di registrare le proprie risorse JS/CSS se necessario. |
| *(Trigger Cron Job)* | Attività pianificata lato server esterno (ad esempio, giornaliera). | Attiva il front controller `cronjob.php` per elaborare i punti fedeltà in scadenza e inviare email. Questo è il trigger operativo primario del modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Promemoria punti fedeltà", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema tecnico o domanda riguardante la funzionalità del modulo.
