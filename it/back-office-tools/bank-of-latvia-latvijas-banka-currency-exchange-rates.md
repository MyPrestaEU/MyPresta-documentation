---
title: "Banca di Lettonia (Latvijas Banka) - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Banca di Lettonia (Latvijas Banka) - tassi di cambio valuta di MyPresta.eu."
sidebar:
  label: "Banca di Lettonia (Latvijas Banka) - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Bank of Latvia (Latvijas Banka) - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates/)
>
> ---


# Banca di Lettonia (Latvijas Banka) - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni, e sono quasi universalmente disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alla pagina delle impostazioni principali del modulo. Qui definirai come il modulo recupera e applica i tassi di cambio.

La pagina di configurazione del modulo "Banca di Lettonia (Latvijas Banka) - tassi di cambio valuta" è semplice e progettata per farti iniziare rapidamente.

**Screenshot della Pagina di Configurazione (Esempio):**
*(Immagina uno screenshot qui che mostra la pagina di configurazione del modulo con i campi per "URL CRON", "Spread", "Frequenza di aggiornamento" e interruttore "Abilitato/Disabilitato")*

#### 2.1.1 URL CRON

- **Cosa fa questa impostazione:** Questo è un indirizzo web unico (URL) che, quando visitato, attiva il modulo per recuperare gli ultimi tassi di cambio dalla Banca di Lettonia e aggiornarli nel tuo negozio PrestaShop. È progettato per essere chiamato automaticamente da un "cron job" sul tuo server.
- **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. Viene generato dal modulo. Copiare questo URL è essenziale per impostare gli aggiornamenti automatici. Se non imposti un cron job utilizzando questo URL, i tassi di cambio non verranno aggiornati automaticamente.
- **Valore consigliato:** Copia questo URL esattamente come appare.
- **Scenario/esempio del commerciante:** Copierai questo URL e lo incollerai nella sezione "Cron Jobs" del pannello di controllo del tuo hosting (ad esempio, cPanel, Plesk o un'interfaccia simile) per programmare aggiornamenti giornalieri.

#### 2.1.2 Spread (%)

- **Cosa fa questa impostazione:** Questo ti permette di aggiungere un "buffer" o margine percentuale ai tassi di cambio ufficiali. Quando il modulo recupera un tasso, lo aumenterà di questa percentuale prima di salvarlo nel tuo negozio. Questo aiuta a proteggere i tuoi margini di profitto contro le fluttuazioni valutarie e le commissioni di transazione.
- **Effetto della modifica di questa impostazione:**
  - *Se impostato a 0:* Il modulo utilizzerà i tassi di cambio esatti forniti dalla Banca di Lettonia. I tuoi prezzi rifletteranno direttamente i tassi ufficiali.
  - *Se impostato su un valore positivo (ad esempio, 2%):* I tassi di cambio nel tuo negozio saranno del 2% più alti rispetto ai tassi ufficiali. Ciò significa che se un prodotto costa 100 EUR e il tasso ufficiale in USD è 1.10, con uno spread del 2%, il modulo utilizzerà un tasso di 1.122 (1.10 \* 1.02), rendendo il prezzo in USD 112.20.
- **Valore consigliato:** Questo dipende dal tuo modello di business, dalle commissioni del gateway di pagamento e dai margini di profitto desiderati. Un punto di partenza comune potrebbe essere dallo 0.5% al 2% per coprire i costi di transazione e le piccole fluttuazioni.
- **Scenario/esempio del commerciante:** Se il tuo processore di pagamento addebita una commissione dell'1% per le transazioni internazionali, impostare uno spread dell'1.5% potrebbe aiutarti ad assorbire quel costo e mantenere comunque il tuo margine di profitto desiderato.

#### 2.1.3 Frequenza di aggiornamento

- **Cosa fa questa impostazione:** Questa impostazione determina la frequenza con cui il modulo *dovrebbe* tentare di aggiornare i tassi di cambio. Mentre il cron job (vedi URL CRON) è ciò che effettivamente attiva l'aggiornamento, questa impostazione funge da salvaguardia per prevenire aggiornamenti troppo frequenti, che potrebbero essere inutili o addirittura problematici per alcuni ambienti di hosting.
- **Effetto della modifica di questa impostazione:**
  - *Se impostato su "Giornaliero":* Il modulo elaborerà un aggiornamento solo una volta ogni 24 ore, anche se il cron job viene eseguito più frequentemente.
  - *Se impostato su "Orario":* Il modulo elaborerà un aggiornamento una volta ogni ora.
  - *Se impostato su "Ogni 15 minuti":* Il modulo elaborerà un aggiornamento ogni 15 minuti.
- **Valore consigliato:** "Giornaliero" è solitamente sufficiente per la maggior parte dei negozi e-commerce, poiché i tassi di cambio ufficiali in genere non fluttuano drasticamente in pochi minuti. Se hai articoli di altissimo valore o operi in mercati estremamente volatili, potrebbe essere considerato "Orario".
- **Scenario/esempio del commerciante:** Imposti il tuo cron job per essere eseguito ogni 6 ore, ma imposti la "Frequenza di aggiornamento" qui su "Giornaliero". Il modulo eseguirà un aggiornamento effettivo del tasso solo una volta in un periodo di 24 ore, anche se il cron job tenta di attivarlo più spesso. Questo previene chiamate API e utilizzo di risorse non necessari.

#### 2.1.4 Abilita Modulo

- **Cosa fa questa impostazione:** Questo è un semplice interruttore di accensione/spegnimento per la funzionalità principale del modulo.
- **Effetto della modifica di questa impostazione:**
  - *Se abilitato (SÌ):* Il modulo recupererà e aggiornerà attivamente i tassi di cambio in base alle tue impostazioni e alla pianificazione del cron job.
  - *Se disabilitato (NO):* Il modulo smetterà di recuperare e aggiornare i tassi di cambio. Il tuo negozio continuerà a utilizzare gli ultimi tassi noti, o il comportamento predefinito di PrestaShop per gli aggiornamenti dei tassi se hai altri meccanismi in atto.
- **Valore consigliato:** "SÌ" per garantire aggiornamenti automatici della valuta.
- **Scenario/esempio del commerciante:** Potresti disabilitare temporaneamente il modulo se hai bisogno di eseguire la manutenzione sul tuo negozio o se decidi di gestire i tassi di cambio manualmente per un breve periodo. Ricorda di riabilitarlo in seguito.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | URL CRON | Copia esattamente | URL per attivare gli aggiornamenti dei tassi tramite cron job del server. Essenziale per l'automazione. |
| Configurazione Modulo | Spread (%) | 0% - 2% (dipende dal business) | Aggiunge un margine percentuale ai tassi di cambio recuperati per proteggere i profitti. |
| Configurazione Modulo | Frequenza di aggiornamento | Giornaliero | Controlla la frequenza con cui il modulo *effettivamente* elabora un aggiornamento, anche se il cron viene eseguito più spesso. |
| Configurazione Modulo | Abilita Modulo | SÌ | Attiva o disattiva la funzionalità di aggiornamento dei tassi del modulo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei tassi di cambio non si aggiornano. Cosa devo fare?**
R:

1.  **Controlla il tuo Cron Job:** La ragione più comune è un cron job configurato in modo errato o mancante sul tuo server di hosting. Ricontrolla di aver copiato l'esatto URL CRON dalla pagina di configurazione del modulo e che il tuo cron job sia programmato per essere eseguito.
2.  **Modulo Abilitato?** Assicurati che l'interruttore "Abilita Modulo" nella pagina di configurazione sia impostato su "SÌ".
3.  **Frequenza di aggiornamento:** Controlla l'impostazione "Frequenza di aggiornamento". Se il tuo cron job viene eseguito ogni ora ma la frequenza è impostata su "Giornaliero", si aggiornerà solo una volta al giorno.
4.  **Cache di PrestaShop:** A volte, svuotare la cache di PrestaShop (sotto **Parametri avanzati > Prestazioni**) può aiutare ad aggiornare i dati visualizzati, anche se è meno probabile che influenzi gli aggiornamenti dei tassi di backend.

**D: Posso sovrascrivere manualmente un tasso di cambio dopo che il modulo lo ha aggiornato?**
R: Sì, puoi. Il modulo aggiorna i tassi nel sistema di gestione delle valute standard di PrestaShop. Se vai su **Internazionale > Valute** nel tuo Back Office, puoi modificare manualmente il tasso di cambio per qualsiasi valuta. Tuttavia, tieni presente che il modulo sovrascriverà le tue modifiche manuali la prossima volta che il cron job verrà eseguito e attiverà un aggiornamento.

**D: Cosa succede se il servizio della Banca di Lettonia è temporaneamente non disponibile?**
R: Il modulo è progettato per recuperare i tassi da una fonte esterna. Se il servizio della Banca di Lettonia è inattivo o irraggiungibile, il modulo probabilmente non riuscirà a recuperare nuovi tassi. In questi casi, il tuo negozio continuerà a utilizzare gli *ultimi tassi di cambio aggiornati con successo*. Non tornerà a tassi predefiniti o errati. Una volta ripristinato il servizio, la prossima esecuzione del cron job aggiornerà nuovamente i tassi.

**D: Questo modulo crea nuove valute nel mio negozio?**
R: No, questo modulo aggiorna solo i tassi di cambio per le valute che hai *già abilitato* nel tuo negozio PrestaShop (sotto **Internazionale > Valute**). Devi prima aggiungere e abilitare le valute desiderate nelle impostazioni standard di PrestaShop affinché questo modulo possa gestire i loro tassi.

**D: Il mio tema personalizzato non visualizza correttamente i prezzi dopo gli aggiornamenti.**
R: Questo modulo modifica solo i tassi di cambio sottostanti. Se i prezzi vengono visualizzati in modo errato, è altamente improbabile che sia un problema diretto del modulo.

1.  **Svuota la cache di Smarty:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".
2.  **Compatibilità del tema:** Assicurati che il tuo tema personalizzato sia completamente compatibile con la tua versione di PrestaShop.
3.  **Codice personalizzato:** Se il tuo tema ha codice personalizzato per la visualizzazione dei prezzi, potrebbe non interpretare correttamente i tassi di cambio aggiornati di PrestaShop. Consulta lo sviluppatore del tuo tema o un esperto di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Banca di Lettonia (Latvijas Banka) - tassi di cambio valuta" (`lbrates`) è un modulo PrestaShop leggero progettato principalmente per automatizzare gli aggiornamenti dei tassi di cambio valuta. Segue un semplice modello MVC in cui il file principale del modulo (`cronjob.php`) funge da controller primario per la configurazione e il front controller (`cronjob.php`) gestisce la logica effettiva di recupero dei tassi. Sfrutta le classi `Currency` e `Configuration` di PrestaShop per gestire tassi e impostazioni. Il modulo è guidato da chiamate esterne di cron job, rendendolo un processo in background asincrono.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `lbrates/controllers/front/cronjob.php`
    - Nome classe: `LbratesCronjobModuleFrontController`
    - Classe genitore: `ModuleFrontController`
    - Responsabilità: Questo controller è il cuore della funzionalità del modulo. È progettato per essere chiamato da un cron job esterno. Quando viene acceduto, recupera gli ultimi tassi di riferimento dell'Euro dall'API ufficiale della Banca di Lettonia, applica lo spread configurato e aggiorna i tassi di cambio per tutte le valute attive nel database di PrestaShop. Gestisce anche la registrazione e previene aggiornamenti troppo frequenti basati sulla chiave di configurazione `PS_LBRATES_LAST_UPDATE`.
  - `lbrates/controllers/front/index.php`
    - Nome classe: `LbratesIndexModuleFrontController`
    - Classe genitore: `ModuleFrontController`
    - Responsabilità: Questo è un file `index.php` vuoto standard spesso incluso nelle directory dei controller frontali dei moduli PrestaShop per prevenire l'elenco delle directory. Non contiene alcuna logica funzionale.
- **Controller Admin Back-Office**:

  - Nessuno. Tutta l'amministrazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

- Nessuno. Il modulo interagisce direttamente con le classi core `Currency` e `Configuration` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessuno. Il modulo non utilizza alcun JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessuno. Il modulo non utilizza alcun CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template Admin (`views/templates/admin/`)**:
  - `lbrates/views/admin.tpl`
    - Questo template viene renderizzato dal metodo `getContent()` nel file principale del modulo `cronjob.php`. Visualizza il modulo di configurazione del modulo nel Back Office di PrestaShop. Questo include campi per l'URL CRON, lo Spread, la Frequenza di aggiornamento e l'interruttore Abilita/Disabilita. Utilizza gli helper e lo stile standard dei moduli di PrestaShop.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration`:
    - `PS_LBRATES_SPREAD`: Memorizza lo spread percentuale configurato.
    - `PS_LBRATES_UPDATE_FREQUENCY`: Memorizza la frequenza di aggiornamento configurata (ad esempio, giornaliera, oraria).
    - `PS_LBRATES_LAST_UPDATE`: Memorizza il timestamp dell'ultimo aggiornamento riuscito per prevenire chiamate troppo frequenti.
    - `PS_LBRATES_ENABLED`: Memorizza lo stato abilitato/disabilitato del modulo.
  - Aggiorna la colonna `exchange_rate` nella tabella `ps_currency` per le valute attive.
- **Tabella degli hook registrati**:

  - Il modulo non registra alcun hook di visualizzazione tradizionale (`displayHeader`, `displayFooter`, ecc.) nel front office. La sua funzione principale è l'elaborazione in background.
  - Utilizza implicitamente l'hook `actionUpdateCurrency` (o meccanismi interni simili) modificando direttamente i tassi di cambio valuta, ma non si registra esplicitamente ad esso.
  - Il metodo `install()` del modulo registrerebbe il modulo stesso all'interno del sistema dei moduli di PrestaShop, rendendo accessibile la sua configurazione.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Banca di Lettonia (Latvijas Banka) - tassi di cambio valuta", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda relativa alla funzionalità e all'integrazione del modulo.
