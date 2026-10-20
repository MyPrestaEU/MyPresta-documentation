---
title: "Banca d'Israele - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Banca d'Israele - tassi di cambio valuta di MyPresta.eu."
sidebar:
  label: "Banca d'Israele - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Bank of Israel - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-israel-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/bank-of-israel-currency-exchange-rates/)
>
> ---


# Banca d'Israele - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni. Il tuo ambiente di hosting deve anche supportare i CRON job per gli aggiornamenti automatici.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alle impostazioni del modulo. Questa è la schermata principale dove imposterai come il modulo recupera e applica i tassi di cambio.

#### **Aggiornamenti MyPresta.eu**

-   **Cosa fa questa impostazione:** Questa sezione fornisce informazioni sugli aggiornamenti da MyPresta.eu, inclusa la versione corrente del modulo e gli aggiornamenti disponibili. Ti aiuta a mantenere il tuo modulo aggiornato.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando è disponibile un aggiornamento:* Vedrai una notifica e un link per scaricare l'ultima versione dal tuo account MyPresta.eu.
    *   *Quando non è disponibile alcun aggiornamento:* La sezione mostrerà semplicemente la tua versione attuale.
-   **Valore consigliato:** Mantieni sempre i tuoi moduli aggiornati per beneficiare di nuove funzionalità, correzioni di bug e miglioramenti della sicurezza.
-   **Scenario / esempio del commerciante:** Controlla regolarmente questa sezione per assicurarti che il tuo modulo sia aggiornato, specialmente dopo importanti aggiornamenti della versione di PrestaShop.

#### **Intervallo di aggiornamento**

-   **Cosa fa questa impostazione:** Determina la frequenza con cui il modulo tenta di recuperare e aggiornare i tassi di cambio dalla Banca d'Israele.
-   **Effetto della modifica di questa impostazione:**
    *   *Impostando un intervallo più breve (es. 1 ora):* I tassi di cambio verranno aggiornati più frequentemente, assicurando che i tuoi prezzi siano sempre molto vicini al tempo reale. Questo è utile per valute altamente volatili o vendite internazionali ad alto volume.
    *   *Impostando un intervallo più lungo (es. 24 ore):* I tassi di cambio verranno aggiornati meno frequentemente. Questo potrebbe essere adatto se le fluttuazioni valutarie non sono una preoccupazione importante per la tua attività o se preferisci chiamate esterne meno frequenti.
-   **Valore consigliato:** "24 ore" per la maggior parte dei negozi. Se hai un alto volume di vendite con clienti internazionali e tassi di cambio che cambiano frequentemente, considera "12 ore" o "6 ore".
-   **Scenario / esempio del commerciante:** Se vendi elettronica di alto valore a clienti internazionali, potresti scegliere "6 ore" per assicurarti che i tuoi prezzi riflettano le ultime condizioni di mercato. Per una boutique locale con vendite internazionali occasionali, "24 ore" è sufficiente.

#### **Margine di aggiornamento (%)**

-   **Cosa fa questa impostazione:** Ti consente di aggiungere un margine percentuale ai tassi di cambio recuperati dalla Banca d'Israele. Questo margine viene applicato in aggiunta al tasso ufficiale.
-   **Effetto della modifica di questa impostazione:**
    *   *Impostando un margine positivo (es. 2%):* I tuoi prezzi convertiti in altre valute saranno leggermente superiori al tasso di cambio ufficiale diretto, aiutandoti a coprire potenziali commissioni di transazione, costi di conversione valuta o semplicemente ad aumentare il tuo margine di profitto.
    *   *Impostando un margine zero (0%):* I tuoi prezzi rifletteranno l'esatto tasso di cambio ufficiale senza alcun ricarico aggiuntivo.
-   **Valore consigliato:** "0" se desideri tassi ufficiali esatti. Un piccolo valore positivo (es. "1" o "2") è spesso consigliato per coprire potenziali commissioni bancarie o fornire un cuscinetto contro piccole fluttuazioni.
-   **Scenario / esempio del commerciante:** Se il tuo gateway di pagamento addebita una commissione dell'1,5% per le transazioni internazionali, impostare un margine dell'"1,5" o "2" percento può aiutarti ad assorbire quel costo senza influire sul prezzo base del tuo prodotto nella tua valuta predefinita.

#### **Valute da aggiornare**

-   **Cosa fa questa impostazione:** Questo è un elenco di tutte le valute attualmente attive nel tuo negozio PrestaShop. Puoi selezionare quali di queste valute devono avere i loro tassi di cambio aggiornati automaticamente da questo modulo.
-   **Effetto della modifica di questa impostazione:**
    *   *Selezionando una valuta (casella di controllo spuntata):* Il modulo recupererà il tasso di cambio per questa valuta (relativo a ILS) dalla Banca d'Israele e lo aggiornerà nel tuo negozio.
    *   *Deselezionando una valuta (casella di controllo deselezionata):* Il modulo ignorerà questa valuta e il suo tasso di cambio *non* verrà aggiornato automaticamente. Dovresti aggiornarlo manualmente se necessario.
-   **Valore consigliato:** Seleziona tutte le valute che utilizzi attivamente per le vendite internazionali e che desideri mantenere aggiornate. Assicurati che la tua valuta predefinita (es. ILS) sia configurata correttamente in PrestaShop.
-   **Scenario / esempio del commerciante:** Se vendi a clienti negli Stati Uniti, in Europa e nel Regno Unito, spunteresti le caselle per USD, EUR e GBP. Se vendi solo localmente in ILS e occasionalmente negli Stati Uniti, potresti spuntare solo USD.

#### **URL del CRON Job**

-   **Cosa fa questa impostazione:** Visualizza l'URL unico che deve essere configurato come CRON job sul tuo server web. Un CRON job è un'attività pianificata che indica al tuo server di visitare questo URL a intervalli regolari, attivando il modulo per recuperare e aggiornare automaticamente i tassi di cambio.
-   **Effetto della modifica di questa impostazione:** Questa non è un'impostazione che modifichi, ma piuttosto un URL che *usi*.
    *   *Quando il CRON job è configurato correttamente:* Il modulo verrà eseguito automaticamente all'intervallo di aggiornamento specificato, mantenendo i tuoi tassi di cambio aggiornati senza alcun intervento manuale.
    *   *Quando il CRON job NON è configurato:* I tassi di cambio *non* verranno aggiornati automaticamente. Dovresti visitare manualmente questo URL nel tuo browser (cosa non consigliata per un uso regolare) o aggiornare manualmente i tassi in PrestaShop.
-   **Valore consigliato:** Copia questo URL e impostalo come CRON job nel tuo pannello di hosting (es. cPanel, Plesk o tramite SSH). La frequenza del CRON job dovrebbe corrispondere o essere leggermente più frequente dell'impostazione del tuo "Intervallo di aggiornamento". Ad esempio, se il tuo intervallo di aggiornamento è di 24 ore, imposta il CRON job per essere eseguito una volta ogni 24 ore.
-   **Scenario / esempio del commerciante:** Dopo aver configurato tutte le altre impostazioni, copia questo URL e incollalo nello scheduler dei CRON job del tuo provider di hosting. Impostalo per essere eseguito quotidianamente in un momento di basso traffico (es. 3 AM).

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Aggiornamenti MyPresta.eu | N/A | Visualizza la versione del modulo e la disponibilità di aggiornamenti. |
| Configurazione Modulo | Intervallo di aggiornamento | 24 ore | Frequenza di recupero dei tassi di cambio (es. 6, 12, 24 ore). |
| Configurazione Modulo | Margine di aggiornamento (%) | 0-2% | Aggiunge un ricarico percentuale ai tassi di cambio recuperati. |
| Configurazione Modulo | Valute da aggiornare | Tutte le valute attive | Seleziona quali valute aggiornare automaticamente. |
| Configurazione Modulo | URL del CRON Job | N/A | URL da configurare sul tuo server per gli aggiornamenti automatici. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei tassi di cambio non si aggiornano automaticamente. Cosa devo fare?**
R:

1.  **Controlla il CRON Job:** La ragione più comune è un CRON job configurato in modo errato o mancante. Ricontrolla l'URL del CRON job fornito nella configurazione del modulo e assicurati che sia configurato correttamente sul tuo server di hosting per essere eseguito alla frequenza desiderata.
2.  **Impostazioni del modulo:** Verifica che l'"Intervallo di aggiornamento" sia impostato e che le "Valute da aggiornare" desiderate siano selezionate nella configurazione del modulo.
3.  **Accesso al server:** Assicurati che il tuo server possa effettuare richieste esterne all'API della Banca d'Israele. A volte firewall o impostazioni di sicurezza possono bloccarlo. Contatta il tuo provider di hosting se sospetti questo.
4.  **Cache di PrestaShop:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) dopo aver apportato modifiche alle impostazioni del modulo.

**D: Posso sovrascrivere manualmente un tasso di cambio dopo che il modulo lo ha aggiornato?**
R: Sì, puoi. Dopo l'esecuzione del modulo, i tassi vengono memorizzati nelle impostazioni di valuta standard di PrestaShop (Internazionale > Valute). Puoi modificare manualmente il tasso di cambio di una valuta specifica lì. Tuttavia, tieni presente che la prossima volta che il CRON job verrà eseguito, sovrascriverà la tua modifica manuale con l'ultimo tasso della Banca d'Israele (più il tuo margine).

**D: Cosa succede se l'API della Banca d'Israele è temporaneamente non disponibile?**
R: Se il modulo non riesce a recuperare i dati, di solito manterrà gli ultimi tassi di cambio aggiornati con successo. Non eliminerà o resetterà i tuoi tassi a zero. Semplicemente riproverà durante la prossima esecuzione programmata del CRON job.

**D: I miei prezzi sembrano leggermente sbagliati dopo l'aggiornamento. Perché?**
R:

1.  **Margine di aggiornamento:** Controlla l'impostazione "Margine di aggiornamento (%)" nella configurazione del modulo. Se hai impostato un margine positivo, i tuoi prezzi saranno leggermente superiori al tasso ufficiale diretto.
2.  **Arrotondamento:** Le impostazioni di valuta di PrestaShop hanno anche un'opzione "Cifre decimali". Assicurati che sia impostata in modo appropriato per le tue valute per evitare problemi di arrotondamento imprevisti.
3.  **Valuta di base:** Assicurati che la tua valuta predefinita in PrestaShop (Internazionale > Valute) sia impostata correttamente come Shekel Israeliano (ILS) se questa è la tua valuta di base per questi aggiornamenti.

**D: Come si configura un CRON job?**
R: Questo processo varia a seconda del provider di hosting. Generalmente, accederai al tuo pannello di controllo di hosting (es. cPanel, Plesk). Cerca una sezione denominata "Cron Jobs", "Attività pianificate" o "Attività automatizzate". Dovrai aggiungere un nuovo CRON job, specificare la frequenza (es. una volta al giorno) e incollare l'"URL del CRON Job" fornito dal modulo. Se non sei sicuro, contatta il supporto del tuo provider di hosting, fornendo loro l'URL e la frequenza desiderata.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Banca d'Israele - tassi di cambio valuta" (`boirates`) segue un'architettura standard per i moduli PrestaShop. Sfrutta una classe di modulo principale (`boirates.php`) per l'installazione, la disinstallazione e la gestione della configurazione. Gli aggiornamenti dei tassi di cambio sono principalmente attivati tramite un controller frontale (`cronjob.php`) progettato per essere chiamato da un CRON job lato server. Il modulo recupera i dati XML dall'API ufficiale della Banca d'Israele, li analizza e aggiorna la tabella `ps_currency` di PrestaShop.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe**: `BoiratesCronjobModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità**: Questo controller è progettato per essere invocato da un CRON job esterno. Contiene la logica principale per recuperare i tassi di cambio dall'API della Banca d'Israele, analizzare la risposta XML, applicare il margine configurato e aggiornare la tabella `ps_currency` in PrestaShop. Non renderizza alcun contenuto front-office ma esegue l'elaborazione dei dati in background. È cruciale per la funzionalità automatizzata del modulo.
    -   `controllers/front/index.php`
        -   **Nome classe**: `BoiratesIndexModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità**: Questo è un controller frontale segnaposto o predefinito. In molti moduli, se un'azione specifica non è instradata, `index.php` potrebbe essere chiamato. Per questo modulo, la sua funzione principale è probabilmente quella di prevenire l'elenco delle directory o fornire una risposta predefinita minima se acceduto direttamente senza parametri specifici. La logica principale risiede in `cronjob.php`.
-   **Controller Admin Back-Office**:

    -   Nessuno. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuno. La logica del modulo è principalmente incapsulata nel file `boirates.php` principale e nel `BoiratesCronjobModuleFrontController`. L'interazione con i dati è diretta con la classe `Currency` di PrestaShop e la tabella `ps_configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessuno. Il modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessuno. Il modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `views/templates/admin/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` del file del modulo `boirates.php`. Definisce la struttura e il layout della pagina di configurazione del modulo nel Back Office di PrestaShop. Include gli elementi del modulo per le impostazioni `mypresta_updates`, `update_`, `updatev_` e `currency_`, oltre a visualizzare l'URL del CRON job.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea alcuna tabella SQL personalizzata.
    -   Interagisce con la tabella standard `ps_configuration` di PrestaShop per memorizzare le sue impostazioni (es. `BOIRATES_UPDATE_INTERVAL`, `BOIRATES_UPDATE_MARGIN`, `BOIRATES_CURRENCIES_TO_UPDATE`).
    -   Aggiorna la colonna `exchange_rate` nella tabella `ps_currency` per le valute selezionate.
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente alcun hook di visualizzazione front-office (come `displayHeader`, `displayRightColumn`, `displayProductButtons`, `displayFooter`) nel suo metodo `install()` per il rendering del contenuto. La sua funzione principale è l'elaborazione dei dati in background.
    Probabilmente utilizza hook interni di PrestaShop per la sua funzionalità principale, come:

    | Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
    | --- | --- | --- |
    | `actionModuleInstall` | Durante l'installazione del modulo | Imposta i valori di configurazione predefiniti e registra gli elementi necessari. |
    | `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce i valori di configurazione. |
    | `displayBackOfficeHeader` | Renderizza il contenuto nell'intestazione del Back Office | Potenzialmente utilizzato per aggiungere CSS/JS o notifiche, sebbene non esplicitamente rilevato nell'inventario. |

## 5. Supporto ufficiale e aggiornamenti

Per supporto ufficiale, aggiornamenti e per scaricare le ultime versioni del modulo "Banca d'Israele - tassi di cambio valuta", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
