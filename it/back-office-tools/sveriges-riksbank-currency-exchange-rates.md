---
title: "Sveriges Riksbank - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Sveriges Riksbank - tassi di cambio valuta di MyPresta.eu."
sidebar:
  label: "Sveriges Riksbank - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Sveriges Riksbank - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/sveriges-riksbank-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/sveriges-riksbank-currency-exchange-rates/)
>
> ---


# Sveriges Riksbank - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per le chiamate API esterne, che sono standard sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alla pagina delle impostazioni principali del modulo. Qui imposterai come il modulo recupera e applica i tassi di cambio.

#### **Impostazioni Generali**

- **Abilita Modulo:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo sarà attivo e il suo cron job e la logica di aggiornamento dei tassi funzioneranno secondo le altre impostazioni.
    - *Quando disabilitato:* Il modulo sarà inattivo e non si verificheranno aggiornamenti automatici dei tassi. I tuoi tassi di cambio rimarranno come erano stati impostati l'ultima volta (manualmente o da un precedente aggiornamento del modulo).
  - **Valore consigliato:** SÌ
  - **Scenario / esempio per il commerciante:** Se stai solo configurando o risolvendo problemi, potresti disabilitarlo temporaneamente. Per il normale funzionamento, dovrebbe essere sempre abilitato.
- **URL Cron Job:**

  - **Cosa fa questa impostazione:** Visualizza un URL unico che devi impostare come "cron job" sul tuo server di web hosting. Un cron job è un'attività pianificata che indica al tuo server di visitare questo URL a intervalli regolari (ad esempio, una volta al giorno). Quando l'URL viene visitato, il modulo recupera e aggiorna automaticamente i tassi di cambio.
  - **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. È generato dal modulo. L'effetto deriva dall'*utilizzo* di questo URL nel tuo pannello di hosting.
    - *Quando correttamente impostato come cron job:* I tuoi tassi di cambio si aggiorneranno automaticamente alla frequenza specificata (ad esempio, giornalmente).
    - *Quando non impostato come cron job:* I tassi non si aggiorneranno automaticamente. Dovresti visitare manualmente questo URL nel tuo browser per attivare un aggiornamento, il che vanifica lo scopo dell'automazione.
  - **Valore consigliato:** Copia questo URL e impostalo come cron job giornaliero sul tuo server.
  - **Scenario / esempio per il commerciante:** Tipicamente lo imposteresti per essere eseguito una volta ogni 24 ore per assicurarti che i tuoi tassi siano sempre aggiornati. Consulta la documentazione o il supporto del tuo provider di hosting per sapere come impostare un cron job (spesso si trova in cPanel o Plesk sotto "Cron Jobs" o "Attività pianificate").

#### **Impostazioni specifiche per valuta**

Sotto le impostazioni generali, vedrai un elenco di tutte le valute attive nel tuo negozio PrestaShop. Per ogni valuta, puoi configurare impostazioni specifiche:

- **Nome Valuta (es. Euro, Dollaro USA):**

  - **Cosa fa questa impostazione:** Identifica la valuta che stai configurando.
  - **Effetto della modifica di questa impostazione:** Questa è solo un'etichetta; non puoi modificare il nome della valuta qui.
- **Ricarico / Ribasso (%):**

  - **Cosa fa questa impostazione:** Ti consente di applicare una regolazione percentuale al tasso di cambio recuperato da Sveriges Riksbank.
    - Un **valore positivo (ricarico)** aumenta il tasso di cambio, il che significa che ottieni più valuta estera per la tua valuta base. Questo è utile per coprire le commissioni di transazione o aumentare il tuo margine di profitto.
    - Un **valore negativo (ribasso)** diminuisce il tasso di cambio, il che significa che ottieni meno valuta estera. Questo potrebbe essere utilizzato per scopi promozionali o se desideri offrire un tasso leggermente migliore ai clienti.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato a 0:* Il tasso di cambio sarà esattamente quello fornito da Sveriges Riksbank.
    - *Quando impostato a 2 (ricarico):* Se il tasso della Riksbank è 1 EUR = 10 SEK, con un ricarico del 2%, il tuo negozio utilizzerà 1 EUR = 10.20 SEK. Ciò significa che quando un cliente paga in EUR, ricevi effettivamente più SEK.
    - *Quando impostato a -1 (ribasso):* Se il tasso della Riksbank è 1 EUR = 10 SEK, con un ribasso dell'1%, il tuo negozio utilizzerà 1 EUR = 9.90 SEK. Ciò significa che quando un cliente paga in EUR, ottiene un tasso leggermente migliore.
  - **Valore consigliato:** Dipende dalla tua strategia aziendale. Una pratica comune è aggiungere un piccolo ricarico (ad esempio, 1-3%) per coprire le commissioni del gateway di pagamento e i costi di conversione valuta.
  - **Scenario / esempio per il commerciante:** Se il tuo processore di pagamento addebita una commissione dell'1,5% per la conversione da EUR a SEK, potresti impostare un ricarico del 2% per l'EUR per assicurarti di coprire tale commissione e mantenere un piccolo profitto.

#### **Pulsante Salva**

- **Cosa fa questo pulsante:** Salva tutte le modifiche apportate nella pagina di configurazione.
- **Effetto del clic su questo pulsante:** Le tue nuove impostazioni (abilita/disabilita, percentuali di ricarico/ribasso) verranno applicate. La prossima volta che il cron job verrà eseguito, o attiverai manualmente un aggiornamento, queste nuove impostazioni verranno utilizzate.
- **Azione consigliata:** Clicca sempre su "Salva" dopo aver apportato qualsiasi modifica.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Modulo | SÌ | Attiva/disattiva gli aggiornamenti automatici dei tassi del modulo. |
| Configurazione Modulo | URL Cron Job | (URL generato) | URL da impostare come attività pianificata sul tuo server per gli aggiornamenti automatici. |
| Configurazione Modulo | Ricarico / Ribasso (%) (per valuta) | 0 | Regola il tasso di cambio recuperato di una percentuale per coprire le commissioni o gestire il profitto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei tassi di cambio non si aggiornano automaticamente. Cosa dovrei controllare?**
R1:

- **Il modulo è abilitato?** Vai su Moduli > Gestione moduli > Sveriges Riksbank - tassi di cambio valuta e assicurati che "Abilita Modulo" sia impostato su SÌ.
- **Il cron job è configurato correttamente?** Ricontrolla il tuo pannello di controllo hosting (cPanel, Plesk, ecc.) per assicurarti che l'URL del Cron Job fornito nella configurazione del modulo sia inserito correttamente e programmato per essere eseguito. Assicurati che il comando sia corretto (ad esempio, `wget -q -O /dev/null "YOUR_CRON_URL"` o `curl -s "YOUR_CRON_URL"`).
- **Ci sono errori quando si visita manualmente l'URL del Cron Job?** Prova a incollare l'URL del Cron Job nel tuo browser. Se vedi un messaggio di errore, potrebbe indicare un problema del server o un problema con la connessione del modulo a Sveriges Riksbank.
- **Connettività del server:** Assicurati che il tuo server possa effettuare connessioni in uscita a siti web esterni (l'API di Sveriges Riksbank). A volte i firewall possono bloccarlo. Contatta il tuo provider di hosting se sospetti questo.

**D2: Ho aggiornato le percentuali di ricarico, ma i prezzi nel mio negozio non sono cambiati.**
R2:

- **Hai salvato le impostazioni?** Clicca sempre sul pulsante "Salva" dopo aver apportato modifiche nella pagina di configurazione del modulo.
- **Il cron job è stato eseguito da quando hai salvato?** Le modifiche avranno effetto solo dopo che il modulo avrà completato il suo prossimo ciclo di aggiornamento. Puoi attendere il tuo cron job programmato o attivare manualmente un aggiornamento visitando l'URL del Cron Job nel tuo browser.
- **Svuota la cache di PrestaShop:** A volte la cache di PrestaShop può conservare dati vecchi. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.

**D3: I tassi di cambio sembrano errati o non sono quelli che mi aspetto da Sveriges Riksbank.**
R3:

- **Controlla le tue impostazioni di Ricarico/Ribasso:** Assicurati di non aver accidentalmente impostato una percentuale di ricarico o ribasso elevata che sta distorcendo i tassi.
- **Verifica i tassi ufficiali di Sveriges Riksbank:** Confronta i tassi nel tuo negozio (dopo un aggiornamento) con i tassi ufficiali pubblicati sul sito web di Sveriges Riksbank per vedere se c'è una discrepanza.
- **Valuta base del modulo:** Il modulo recupera i tassi relativi a SEK. Assicurati che la valuta predefinita del tuo PrestaShop sia configurata correttamente se ti aspetti una base diversa.

**D4: Questo modulo funzionerà con il mio tema personalizzato?**
R4: Sì, questo modulo opera interamente in background e non aggiunge elementi visivi né modifica alcun template nel front office. Pertanto, è completamente compatibile con qualsiasi tema PrestaShop, personalizzato o predefinito. La sua funzione è puramente basata sui dati (aggiornamento dei tassi di cambio).

**D5: Come faccio ad aggiungere una nuova valuta al mio negozio in modo che questo modulo possa gestirla?**
R5:

1. Vai su **Internazionale > Valute** nel tuo Back Office di PrestaShop.
2. Clicca su "Aggiungi nuova valuta" (o l'icona più).
3. Inserisci i dettagli per la nuova valuta (codice ISO, simbolo, tasso di cambio relativo alla tua valuta predefinita).
4. Una volta aggiunta e abilitata, la nuova valuta apparirà nella pagina di configurazione del modulo "Sveriges Riksbank - tassi di cambio valuta", permettendoti di impostare il suo ricarico/ribasso.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Sveriges Riksbank - tassi di cambio valuta".

### 4.1 Panoramica dell'architettura

Il modulo segue un'architettura standard dei moduli PrestaShop, concentrandosi principalmente sulla configurazione del back-office e sull'esecuzione del cron job del front-office. Sfrutta il sistema di configurazione di PrestaShop per l'archiviazione delle impostazioni e `ModuleFrontController` per la gestione della richiesta del cron job. La logica principale risiede nel file principale del modulo, che gestisce l'installazione, la disinstallazione e il metodo `getContent()` per il modulo di configurazione. La funzione principale del modulo è recuperare dati esterni (tassi di cambio) e aggiornare i dati dell'oggetto `Currency` di PrestaShop.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller sono progettati per essere accessibili pubblicamente, principalmente per la funzionalità del cron job.

- **`srrates/controllers/front/cronjob.php`**

  - **Nome classe e classe padre:** `SrratesCronjobModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo è il controller cruciale per gli aggiornamenti automatici delle valute. Quando questo URL viene acceduto (tipicamente da un cron job lato server), attiva la logica del modulo per recuperare gli ultimi tassi di cambio da Sveriges Riksbank e aggiornarli nel database di PrestaShop. Non produce alcun output visivo ma tipicamente restituisce un semplice messaggio di successo o errore. È progettato per essere leggero ed efficiente per le attività pianificate.
- **`srrates/controllers/front/index.php`**

  - **Nome classe e classe padre:** `SrratesIndexModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller probabilmente funge da fallback o da punto di ingresso predefinito per il routing del front-office del modulo. In molti moduli, `index.php` in una directory di controller front-end viene utilizzato per gestire la rotta base per il modulo se non viene richiesta alcuna azione specifica. Potrebbe reindirizzare o semplicemente visualizzare una pagina vuota se non esplicitamente utilizzato per una funzionalità. Per questo modulo, la sua funzione principale è probabilmente minima, poiché `cronjob.php` gestisce la logica principale del front-office.

#### Controller Admin Back-Office

Il modulo non utilizza alcun controller Admin personalizzato. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non definisce classi personalizzate o `ObjectModel` nella directory `classes/`. Interagisce direttamente con la classe `Currency` e la classe `Configuration` di PrestaShop per gestire le impostazioni e aggiornare i tassi.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non include alcun file JavaScript personalizzato. Tutte le interazioni nella pagina di configurazione sono gestite da elementi di modulo standard di PrestaShop e potenzialmente da jQuery se utilizzato direttamente all'interno del metodo `getContent()`.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato. Lo stile della pagina di configurazione si basa interamente sugli stili predefiniti del tema del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`srrates/views/admin.tpl`**
  - **Ambito:** Template amministrativo.
  - **Scopo:** Questo template viene utilizzato per renderizzare il modulo di configurazione del modulo all'interno del Back Office di PrestaShop. Visualizza l'interruttore "Abilita Modulo", l'URL del "Cron Job" e l'elenco dinamico delle valute con i rispettivi campi di input "Ricarico / Ribasso (%)". È responsabile del layout visivo dell'output di `getContent()`.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:
  Il modulo non crea tabelle SQL personalizzate. Memorizza le sue impostazioni di configurazione (come `PS_SRRATES_ENABLED` e i ricarichi delle singole valute) direttamente nella tabella `ps_configuration` di PrestaShop.

  - `ps_configuration`: Memorizza le impostazioni del modulo. Le chiavi tipicamente seguono un modello come `PS_SRRATES_ENABLED` per l'interruttore principale, e potenzialmente `PS_SRRATES_MARKUP_EUR` per i ricarichi specifici per valuta.
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Non esplicitamente utilizzato da questo modulo per l'output, ma `install()` potrebbe registrarlo come pratica standard. |
| `displayRightColumn` | Nella colonna destra delle pagine del front-office. | Non esplicitamente utilizzato da questo modulo per l'output. |
| `displayLeftColumn` | Nella colonna sinistra delle pagine del front-office. | Non esplicitamente utilizzato da questo modulo per l'output. |
| `displayFooter` | Nella sezione del footer di ogni pagina del front-office. | Non esplicitamente utilizzato da questo modulo per l'output. |
| `displayProductExtraContent` | Nella pagina del prodotto, sotto il contenuto principale. | Non esplicitamente utilizzato da questo modulo per l'output. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Non esplicitamente utilizzato da questo modulo, poiché la sua funzione è l'aggiornamento dei tassi, non l'elaborazione degli ordini. |
| `actionAdminControllerSetMedia` | Quando un controller admin viene caricato, prima del rendering. | Potenzialmente utilizzato per caricare CSS/JS per la pagina di configurazione del modulo, sebbene non siano presenti risorse personalizzate. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Utilizzato per eseguire la configurazione iniziale, creare voci di configurazione e registrare gli hook. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Utilizzato per pulire le voci di configurazione e annullare la registrazione degli hook. |

La funzionalità principale del modulo (aggiornamento dei tassi) è attivata dal controller front-end `cronjob.php`, non direttamente da un hook di PrestaShop, sebbene il modulo stesso sia installato e gestito tramite hook standard del modulo.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Sveriges Riksbank - tassi di cambio valuta", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). È possibile scaricare le versioni più recenti dalla cronologia degli ordini e accedere alle risorse di supporto lì.
"""
