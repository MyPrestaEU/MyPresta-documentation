---
title: "CBR Currency Exchange & Rates (Banca di Russia) - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop CBR Currency Exchange & Rates (Banca di Russia) di MyPresta.eu."
sidebar:
  label: "CBR Currency Exchange & Rates (Banca di Russia) - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo CBR Currency Exchange & Rates (Bank of Russia) su MyPresta.eu](https://mypresta.eu/modules/administration-tools/cbr-currency-exchange-rates-bank-of-russia.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/cbr-currency-exchange-rates-bank-of-russia/)
>
> ---


# CBR Currency Exchange & Rates (Banca di Russia)

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per la comunicazione API esterna, che sono comuni nella maggior parte degli ambienti di web hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, clicca su "Configura" per accedere alle sue impostazioni. Questa è la schermata principale dove gestirai tutti gli aspetti del modulo CBR Currency Exchange & Rates.

#### **Impostazioni Generali**

-   **Abilita aggiornamenti automatici:**

    -   **Cosa fa questa impostazione:** Questo interruttore controlla se il modulo verificherà e applicherà automaticamente nuovi tassi di cambio dalla Banca Centrale di Russia.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo recupererà periodicamente i tassi di cambio più recenti dal sito web della CBR. Questo è cruciale per mantenere i tuoi prezzi in RUB accurati senza intervento manuale. Dovrai impostare un CRON job (spiegato di seguito) affinché ciò funzioni.
        -   *Quando disabilitato (NO):* Il modulo non aggiornerà automaticamente i tassi. Dovresti aggiornare manualmente i tassi se questa opzione è disattivata, il che vanifica lo scopo del modulo.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Vuoi che i tuoi prezzi in RUB riflettano sempre il tasso di cambio ufficiale corrente senza dover accedere quotidianamente e aggiornarli. Abilitando questa opzione, il tuo negozio sarà sempre aggiornato.
-   **Frequenza di aggiornamento (in ore):**

    -   **Cosa fa questa impostazione:** Definisce la frequenza con cui il modulo dovrebbe tentare di recuperare nuovi tassi di cambio dalla CBR.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando un numero inferiore (ad esempio, 1 ora):* I tassi verranno controllati e aggiornati più frequentemente. Questo è l'ideale se la tua attività richiede conversioni molto precise, quasi in tempo reale.
        -   *Impostando un numero superiore (ad esempio, 24 ore):* I tassi verranno controllati meno frequentemente. Questo potrebbe essere adatto se i tuoi prezzi non fluttuano drasticamente o se preferisci ridurre il carico del server da frequenti chiamate esterne.
    -   **Valore consigliato:** 24 (Gli aggiornamenti giornalieri sono solitamente sufficienti, poiché i tassi CBR cambiano una volta al giorno).
    -   **Scenario / esempio del commerciante:** Vuoi assicurarti che i tuoi prezzi in RUB siano aggiornati quotidianamente, quindi imposti questo valore a 24 ore. Se vendi articoli di alto valore con margini stretti, potresti impostarlo a 12 ore per catturare i cambiamenti di metà giornata se la CBR li pubblica (anche se tipicamente è una volta al giorno).
-   **Margine sul tasso di cambio (%):**

    -   **Cosa fa questa impostazione:** Ti consente di aggiungere un margine percentuale in cima al tasso di cambio ufficiale della CBR. Questo può essere utilizzato per coprire commissioni di transazione, costi di conversione valuta o per aggiustare leggermente la tua strategia di prezzo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando un valore positivo (ad esempio, 2):* Il modulo aumenterà il tasso di cambio calcolato del 2%. Ciò significa che per ogni unità della tua valuta base, otterrai leggermente più RUB, aumentando efficacemente i tuoi prezzi in RUB.
        -   *Impostando 0 o lasciando vuoto:* Il modulo utilizzerà l'esatto tasso di cambio ufficiale della CBR senza alcuna regolazione.
        -   *Impostando un valore negativo (ad esempio, -1):* Il modulo diminuirà il tasso di cambio calcolato dell'1%. Ciò significa che otterrai leggermente meno RUB per ogni unità della tua valuta base, diminuendo efficacemente i tuoi prezzi in RUB.
    -   **Valore consigliato:** 0 (A meno che tu non abbia specifiche ragioni commerciali per aggiungere un margine).
    -   **Scenario / esempio del commerciante:** Il tuo gateway di pagamento addebita una commissione dell'1,5% per la conversione di RUB nella tua valuta base. Puoi impostare un margine dell'1,5% qui per compensare tale costo e mantenere i tuoi margini di profitto.
-   **URL del CRON Job:**

    -   **Cosa fa questa impostazione:** Visualizza l'URL unico che devi impostare come CRON job sul tuo server di hosting. Quando si accede a questo URL, il modulo viene attivato per recuperare e aggiornare i tassi di cambio.
    -   **Effetto della modifica di questa impostazione:** Questa non è un'impostazione che modifichi, ma piuttosto un URL che *usi*.
        -   *Quando correttamente configurato come CRON job:* Il modulo verrà eseguito automaticamente in background alla frequenza specificata (basata sull'impostazione "Frequenza di aggiornamento") per aggiornare i tassi.
        -   *Se non configurato come CRON job:* Gli aggiornamenti automatici non avverranno, anche se "Abilita aggiornamenti automatici" è impostato su SÌ.
    -   **Valore consigliato:** Copia questo URL e impostalo come CRON job sul tuo server.
    -   **Scenario / esempio del commerciante:** Dopo aver configurato il modulo, copi questo URL e lo aggiungi allo scheduler dei CRON job del tuo pannello di controllo dell'hosting per eseguirlo quotidianamente alle 3 del mattino, assicurando che i tassi siano aggiornati prima dell'inizio della tua giornata lavorativa.

#### **Impostazioni Valuta**

-   **Valuta da aggiornare:**
    -   **Cosa fa questa impostazione:** Questo menu a discesa ti consente di selezionare quale valuta specifica nel tuo negozio PrestaShop dovrebbe essere aggiornata con i tassi CBR. Elencherà tutte le valute che hai abilitato nel tuo Back Office PrestaShop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Selezionando "Rublo Russo (RUB)":* Il modulo mirerà specificamente e aggiornerà il tasso di cambio per il Rublo Russo rispetto alla valuta base del tuo negozio utilizzando i dati CBR.
        -   *Selezionando qualsiasi altra valuta:* Questo modulo è specificamente progettato per i tassi CBR, che sono per il Rublo Russo. Selezionare un'altra valuta potrebbe portare a comportamenti inaspettati o nessun aggiornamento per quella valuta.
    -   **Valore consigliato:** Rublo Russo (RUB)
    -   **Scenario / esempio del commerciante:** La valuta base del tuo negozio è EUR e vuoi assicurarti che quando i clienti selezionano RUB, la conversione da EUR a RUB sia accurata in base alla CBR. Selezioni "Rublo Russo (RUB)" qui.

#### **Pulsante Salva**

-   **Salva:**
    -   **Cosa fa:** Applica tutte le modifiche che hai apportato nella pagina di configurazione.
    -   **Effetto del clic:** Le tue impostazioni verranno memorizzate nel database e il modulo opererà secondo i nuovi parametri.
    -   **Azione consigliata:** Clicca sempre su "Salva" dopo aver apportato qualsiasi modifica.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita aggiornamenti automatici | SÌ | Controlla il recupero automatico dei tassi CBR. SÌ per aggiornamenti automatici. |
| Configurazione Modulo | Frequenza di aggiornamento (in ore) | 24 | Quanto spesso il CRON job dovrebbe attivare gli aggiornamenti dei tassi. 24 per giornaliero. |
| Configurazione Modulo | Margine sul tasso di cambio (%) | 0 | Aggiunge una percentuale al tasso ufficiale. Usa per commissioni o strategia di prezzo. |
| Configurazione Modulo | URL del CRON Job | (URL unico) | URL da configurare sul tuo server per gli aggiornamenti automatici. |
| Configurazione Modulo | Valuta da aggiornare | Rublo Russo (RUB) | Specifica quale valuta PrestaShop aggiornare con i tassi CBR. Deve essere RUB. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei prezzi in RUB non si aggiornano automaticamente. Cosa dovrei controllare?**
R1:

-   **"Abilita aggiornamenti automatici" è impostato su SÌ?** Controlla la configurazione del modulo.
-   **Hai impostato il CRON job sul tuo server di hosting?** Questa è la ragione più comune. Copia l'“URL del CRON Job” dalla configurazione del modulo e aggiungilo allo scheduler CRON del tuo pannello di hosting. Assicurati che sia impostato per essere eseguito almeno con la stessa frequenza dell'impostazione "Frequenza di aggiornamento".
-   **La "Valuta da aggiornare" è impostata su "Rublo Russo (RUB)"?** Il modulo è progettato per RUB.
-   **Controlla i log del CRON job del tuo server (se disponibili):** Il tuo provider di hosting potrebbe offrire log che mostrano se il CRON job è in esecuzione e se ha riscontrato errori.
-   **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" per assicurarti che il tuo negozio stia visualizzando i dati più recenti.

**D2: Il tasso di cambio sembra errato o non è cambiato da un po'.**
R2:

-   **Verifica il tasso ufficiale della CBR:** Controlla il sito web ufficiale della Banca Centrale di Russia per il tasso di cambio odierno per confermare quale dovrebbe essere.
-   **Controlla la tua "Frequenza di aggiornamento":** Se è impostata su 24 ore, si aggiornerà solo una volta al giorno.
-   **Festività bancarie:** La CBR non aggiorna i tassi durante le festività bancarie. Il modulo utilizza intelligentemente l'ultimo tasso disponibile. Se c'è un lungo periodo di festività, il tasso potrebbe rimanere statico per diversi giorni.
-   **Problemi con il CRON job:** Fai riferimento a D1 per la risoluzione dei problemi relativi ai CRON job.

**D3: Posso usare questo modulo per altre valute oltre a RUB?**
R3: No, questo modulo è specificamente progettato per integrarsi con i dati dei tassi di cambio della Banca Centrale di Russia, che sono principalmente per il Rublo Russo. Aggiornerà accuratamente solo la valuta RUB nel tuo negozio.

**D4: Ho cambiato il mio tema e ora i prezzi sembrano strani in RUB.**
R4: Questo modulo gestisce solo il *valore* della conversione di valuta. La *visualizzazione* dei prezzi (caratteri, colori, layout) è gestita dal tuo tema PrestaShop. Se i prezzi sembrano strani dopo un cambio di tema, è probabile che sia un problema di CSS o di template con il tuo nuovo tema, non del modulo stesso. Potrebbe essere necessario regolare lo stile del tuo tema.

**D5: Come posso aggiornare manualmente i tassi se necessario?**
R5: Sebbene il modulo sia progettato per aggiornamenti automatici, puoi forzare un aggiornamento visitando manualmente l'URL del CRON Job nel tuo browser web. Questo attiverà il processo di aggiornamento una volta. Ricorda di svuotare la cache di PrestaShop in seguito.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo CBR Currency Exchange & Rates.

### 4.1 Panoramica dell'architettura

Il modulo `cbrrates` segue un'architettura standard dei moduli PrestaShop, utilizzando principalmente la classe `Module` per la sua funzionalità principale e configurazione. Sfrutta i controller frontali per l'esecuzione dei CRON job e un semplice metodo `getContent()` per la configurazione del back-office. Il modulo recupera i dati XML dall'API della CBR, li analizza e aggiorna i tassi di cambio della `Currency` di PrestaShop.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe genitore**: `CbrratesCronjobModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è progettato per essere chiamato da un CRON job esterno. Quando viene richiamato, avvia il processo di aggiornamento del tasso di cambio. Controlla i valori di configurazione `update_` e `updatev_` per determinare se un aggiornamento è dovuto in base alla frequenza configurata. Quindi chiama la logica principale del modulo per recuperare e applicare i tassi CBR più recenti. Restituisce un semplice messaggio di successo o errore.
    -   `controllers/front/index.php`
        -   **Nome classe e classe genitore**: `CbrratesIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo è un controller frontale segnaposto o predefinito. In molti moduli, se non è definita alcuna azione specifica, `index.php` potrebbe fungere da fallback o semplicemente reindirizzare. Per `cbrrates`, la sua funzione principale è probabilmente minima, poiché l'interazione principale del front-office avviene tramite `cronjob.php`. Potrebbe essere presente per garantire che esista una rotta front-office valida per il modulo, anche se non attivamente utilizzata per la visualizzazione.
-   **Controller Admin Back-Office**:

    -   Nessun controller admin dedicato è presente in questo modulo. Tutta la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Nessuna classe personalizzata o definizione di `ObjectModel` è presente nella directory `classes/` per questo modulo. Tutta la logica principale risiede all'interno del file `cbrrates.php`.

### 4.4 Asset JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è presente nel modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è presente nel modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `cbrrates/views/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` in `cbrrates.php` per visualizzare il modulo di configurazione del modulo nel Back Office di PrestaShop.
        -   **Contenuto**: Tipicamente contiene la struttura HTML per i campi di input, gli interruttori e i pulsanti per impostazioni come `mypresta_updates`, `update_`, `updatev_`, `currency_` e la visualizzazione dell'URL del CRON job. Utilizza gli helper e lo stile standard dei moduli di PrestaShop.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` (o `_configuration` a seconda del prefisso).
        -   `PS_CBRRATES_UPDATE_ENABLED`: Booleano (0/1) per "Abilita aggiornamenti automatici".
        -   `PS_CBRRATES_UPDATE_FREQUENCY`: Intero per "Frequenza di aggiornamento (in ore)".
        -   `PS_CBRRATES_MARGIN`: Float per "Margine sul tasso di cambio (%)".
        -   `PS_CBRRATES_CURRENCY_ID`: Intero, ID della valuta PrestaShop da aggiornare (ad esempio, ID per RUB).
        -   `PS_CBRRATES_LAST_UPDATE`: Timestamp dell'ultimo aggiornamento riuscito.
        -   `PS_CBRRATES_CRON_TOKEN`: Una stringa unica utilizzata nell'URL del CRON job per la sicurezza.
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente hook per la visualizzazione del front-office (ad esempio, `displayHeader`, `displayFooter`). La sua interazione principale con il core di PrestaShop avviene tramite l'hook `actionUpdateCurrency` (implicitamente, aggiornando i tassi di cambio) e il suo meccanismo CRON interno.

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionUpdateCurrency` | Attivato quando una valuta viene aggiornata (implicitamente da questo modulo) | Non esplicitamente registrato dal modulo, ma la funzione principale del modulo è aggiornare i tassi di cambio, il che potrebbe attivare questo hook core di PrestaShop. |
| (CRON Interno) | Tramite `controllers/front/cronjob.php` | Attiva il recupero e l'aggiornamento dei tassi di cambio CBR in base alla frequenza configurata. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "CBR Currency Exchange & Rates (Banca di Russia)", fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
