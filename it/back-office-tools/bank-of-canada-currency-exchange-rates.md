---
title: "Banca del Canada - tassi di cambio valuta - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Banca del Canada - tassi di cambio valuta' di MyPresta.eu."
sidebar:
  label: "Banca del Canada - tassi di cambio valuta - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Bank of Canada - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-canada-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/bank-of-canada-currency-exchange-rates/)
>
> ---


# Banca del Canada - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni, e sono quasi universalmente disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alle impostazioni del modulo. Questa è la schermata principale dove gestirai come vengono aggiornati i tassi di cambio.

#### **1. Aggiorna i tassi di cambio manualmente**

-   **Cosa fa questa impostazione:** Questo è un pulsante che, quando cliccato, attiva immediatamente il modulo per recuperare gli ultimi tassi di cambio dalla Banca del Canada e aggiornarli nel tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando cliccato:* Il modulo si connette alla Banca del Canada, recupera i tassi più attuali, calcola i tassi incrociati e li applica alle valute del tuo negozio. Di solito apparirà un messaggio di conferma.
-   **Valore consigliato:** Usa questo pulsante per aggiornamenti immediati o per testare il modulo dopo la configurazione iniziale. Per aggiornamenti continui, è consigliato il CRON job (spiegato di seguito).
-   **Scenario / esempio per il commerciante:** Hai appena lanciato un nuovo prodotto e vuoi assicurarti che tutti i prezzi internazionali siano assolutamente attuali prima di una grande spinta di marketing. Clicca questo pulsante per forzare un aggiornamento immediato.

#### **2. URL del CRON Job**

-   **Cosa fa questa impostazione:** Questo campo visualizza un URL unico che, quando acceduto, attiva il modulo per aggiornare automaticamente i tassi di cambio. Questo URL è progettato per essere utilizzato con un "CRON job" sul tuo server web.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando l'URL viene acceduto (da un CRON job):* Il modulo esegue lo stesso processo di aggiornamento dei tassi come cliccando il pulsante di aggiornamento manuale, ma lo fa automaticamente a intervalli programmati.
-   **Valore consigliato:** Copia questo URL e impostalo come CRON job sul tuo server di hosting.
-   **Scenario / esempio per il commerciante:** Vuoi che i tuoi tassi di cambio si aggiornino ogni giorno alle 3 del mattino. Copi questo URL e configuri il tuo pannello di hosting (cPanel, Plesk, ecc.) per visitare questo URL quotidianamente alle 3 del mattino. Questo assicura che i tuoi tassi siano sempre freschi senza che tu debba muovere un dito.

#### **3. Margine del tasso di cambio (%)**

-   **Cosa fa questa impostazione:** Questo ti permette di aggiungere un margine percentuale ai tassi di cambio recuperati dalla Banca del Canada. Ad esempio, se il tasso BOC è 1.20 e imposti un margine del 2%, il tuo negozio utilizzerà un tasso di 1.224 (1.20 \* 1.02).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un valore positivo (es. 2):* Tutti i prezzi convertiti nel tuo negozio saranno leggermente più alti, riflettendo il margine aggiunto. Questo può aiutare a coprire le commissioni di transazione, i costi di conversione valuta, o semplicemente aumentare il tuo margine di profitto sulle vendite internazionali.
    -   *Quando impostato su 0 (o lasciato vuoto):* Il modulo utilizzerà i tassi di cambio esatti forniti dalla Banca del Canada senza alcun markup aggiuntivo.
-   **Valore consigliato:** Inizia con 0% e regola in base alle tue esigenze aziendali, alle commissioni del gateway di pagamento e ai margini di profitto desiderati. Una pratica comune è 1-3% per coprire potenziali costi.
-   **Scenario / esempio per il commerciante:** Il tuo gateway di pagamento addebita una commissione dell'1.5% per le conversioni di valuta internazionali. Imposti il "Margine del tasso di cambio" all'1.5% per assicurarti che questo costo sia coperto nel prezzo dei tuoi prodotti, piuttosto che erodere il tuo profitto.

#### **4. Ultimo aggiornamento**

-   **Cosa fa questa impostazione:** Questo campo visualizza la data e l'ora dell'ultimo aggiornamento riuscito dei tassi di cambio eseguito dal modulo.
-   **Effetto della modifica di questa impostazione:** Questo è un campo di sola lettura e non può essere modificato. Serve come indicatore informativo.
-   **Valore consigliato:** Monitora questo campo per assicurarti che il tuo CRON job stia funzionando correttamente e che i tassi vengano aggiornati regolarmente.
-   **Scenario / esempio per il commerciante:** Noti che i tuoi prezzi internazionali sembrano obsoleti. Controlli "Ultimo aggiornamento" e vedi che non è stato aggiornato da una settimana, indicando un potenziale problema con la configurazione del tuo CRON job.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Aggiorna tassi di cambio manualmente (Pulsante) | Clicca per aggiornare | Forza un aggiornamento immediato di tutti i tassi di cambio valuta dalla BOC. |
| Configurazione modulo | URL del CRON Job | Copia e configura sul server | Fornisce un URL per aggiornamenti automatici e programmati tramite il servizio CRON del tuo hosting. |
| Configurazione modulo | Margine del tasso di cambio (%) | 0% | Aggiunge un markup percentuale ai tassi di cambio recuperati, influenzando tutti i prezzi convertiti. |
| Configurazione modulo | Ultimo aggiornamento | Sola lettura | Visualizza il timestamp dell'ultimo aggiornamento riuscito dei tassi di cambio. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: I miei tassi di cambio non si aggiornano automaticamente. Cosa devo fare?**
R1: Questo è quasi sempre un problema del CRON job.
-   **Controlla il tuo pannello di hosting:** Accedi al tuo account di hosting (cPanel, Plesk, ecc.) e verifica che il CRON job sia configurato correttamente con l'URL esatto fornito dal modulo. Assicurati che la frequenza sia corretta (es. giornaliera).
-   **Verifica il comando CRON:** Il comando di solito assomiglia a `wget -O /dev/null "IL_TUO_URL_CRON_QUI"` o `curl "IL_TUO_URL_CRON_QUI"`. Assicurati che non ci siano errori di battitura.
-   **Controlla "Ultimo aggiornamento" nel modulo:** Se questa data è vecchia, conferma che il CRON non è in esecuzione.
-   **Esegui manualmente l'URL del CRON:** Copia l'URL del CRON dalla configurazione del modulo e incollalo nel tuo browser. Se si aggiorna, allora l'URL stesso è corretto e il problema è puramente con la configurazione del CRON del tuo hosting.

**D2: I prezzi in altre valute sembrano troppo alti/bassi rispetto alla valuta predefinita.**
R2:
-   **Controlla il tuo "Margine del tasso di cambio (%)":** Se questo è impostato troppo alto, i prezzi saranno gonfiati. Se è negativo (anche se non raccomandato), i prezzi sarebbero più bassi.
-   **Verifica la tua valuta predefinita:** Assicurati che la valuta predefinita del tuo negozio PrestaShop (Localizzazione > Valute) sia impostata correttamente sulla tua valuta operativa principale (es. CAD se stai recuperando dalla Banca del Canada). Il modulo calcola i tassi rispetto alla tua valuta predefinita.
-   **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte i vecchi prezzi possono essere memorizzati nella cache.

**D3: Il modulo dice che "Ultimo aggiornamento" è stato eseguito con successo, ma non vedo modifiche nel front office.**
R3:
-   **Svuota la cache di PrestaShop:** Questa è la ragione più comune. Svuota sempre la cache dopo qualsiasi aggiornamento significativo dei dati in PrestaShop.
-   **Controlla la cache del browser:** Prova a svuotare la cache del tuo browser o a visualizzare il tuo negozio in una finestra in incognito/privata per escludere problemi di caching locale.
-   **Verifica la selezione della valuta:** Assicurati di stare effettivamente visualizzando il negozio nella valuta non predefinita dove ti aspetti di vedere i prezzi convertiti.

**D4: Questo modulo funziona con temi personalizzati?**
R4: Sì, questo modulo funziona in background aggiornando i tassi di cambio valuta di base di PrestaShop. Non interagisce direttamente con gli elementi visivi del tuo tema, quindi dovrebbe essere compatibile con qualsiasi tema personalizzato. Il selettore di valuta del tema visualizzerà semplicemente i prezzi basati sui tassi forniti dal modulo.

**D5: Posso usare questo modulo se la mia valuta predefinita non è CAD?**
R5: Sì, puoi. Il modulo recupera i tassi base dalla Banca del Canada (es. USD a CAD, EUR a CAD). Quindi calcola in modo intelligente i tassi incrociati rispetto alla *valuta predefinita del tuo negozio*. Quindi, se la tua valuta predefinita è EUR e la BOC fornisce USD/CAD, il modulo calcolerà EUR/USD, EUR/CAD, ecc., basandosi sui dati disponibili.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Banca del Canada - tassi di cambio valuta" (`bocrates`) è progettato come una soluzione leggera e automatizzata per la sincronizzazione dei tassi di cambio. Sfrutta principalmente l'`ObjectModel` `Currency` di PrestaShop per aggiornare i tassi di cambio. Il modulo utilizza un controller frontale per l'esecuzione del CRON job, garantendo che gli aggiornamenti dei tassi avvengano al di fuori del contesto standard del Back Office, il che è ideale per le attività programmate. Aderisce all'architettura del modulo PrestaShop, utilizzando i metodi `install()` e `uninstall()` per la configurazione e la pulizia, e `getContent()` per la configurazione del Back Office.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe padre**: `BocratesCronjobModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è il punto di ingresso per il CRON job automatizzato. Quando viene acceduto tramite il suo URL unico (fornito nella configurazione del modulo), attiva il metodo `processUpdateExchangeRates()` all'interno della classe principale del modulo. È progettato per essere chiamato esternamente da uno scheduler CRON lato server, non direttamente da un utente. Tipicamente restituisce un semplice messaggio di successo o errore.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre**: `BocratesIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo è un controller frontale segnaposto o predefinito. In molti moduli, se un'azione specifica non è definita, potrebbe essere utilizzato `index.php`. Per questo modulo, la sua funzione principale è probabilmente quella di fungere da fallback o per garantire che il routing del front-office del modulo sia correttamente stabilito, anche se non esegue un'azione specifica rivolta all'utente. Il `cronjob.php` è il controller frontale attivo per la funzionalità.
-   **Controller Admin Back-Office**:

    -   Nessuno. Tutta la configurazione del Back Office è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo `bocrates.php`.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuno. Il modulo interagisce direttamente con l'`ObjectModel` `Currency` e la classe `Configuration` di PrestaShop per l'archiviazione e la manipolazione dei dati.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessuno. Il modulo non utilizza JavaScript personalizzato per la sua funzionalità.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessuno. Il modulo non utilizza CSS personalizzato per la sua funzionalità.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `bocrates/views/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` del file principale del modulo `bocrates.php`. Visualizza il modulo di configurazione del modulo nel Back Office di PrestaShop. Questo include il pulsante di aggiornamento manuale, l'URL del CRON job, l'input del margine del tasso di cambio e il timestamp dell'ultimo aggiornamento.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` utilizzando chiavi come:
        -   `BOCRATES_MARGIN`: Memorizza il margine percentuale per i tassi di cambio.
        -   `BOCRATES_LAST_UPDATE`: Memorizza il timestamp dell'ultimo aggiornamento riuscito.
        -   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Relativi al meccanismo di aggiornamento di MyPresta.eu.
-   **Tabella degli hook registrati**:
    Il modulo opera principalmente in background e non registra hook per la visualizzazione nel front-office. La sua funzionalità principale è attivata dal controller frontale `cronjob`.

    | Nome Hook | Tempistica di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `actionModuleInstall` | Durante l'installazione del modulo | Imposta i valori di configurazione predefiniti e registra gli hook necessari (se presenti). |
    | `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce i valori di configurazione. |
    | `displayBackOfficeHeader` | Renderizza nell'intestazione del Back Office | Potenzialmente utilizzato per includere risorse o visualizzare avvisi nel pannello di amministrazione (anche se non sono elencate risorse specifiche). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto tecnico dedicato per il modulo "Banca del Canada - tassi di cambio valuta", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
