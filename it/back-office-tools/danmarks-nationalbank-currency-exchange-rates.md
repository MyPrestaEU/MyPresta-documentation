---
title: "Danmarks Nationalbank - tassi di cambio valuta - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Danmarks Nationalbank - tassi di cambio valuta di MyPresta.eu."
sidebar:
  label: "Danmarks Nationalbank - tassi di cambio valuta - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Danmarks Nationalbank - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/danmarks-nationalbank-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/danmarks-nationalbank-currency-exchange-rates/)
>
> ---


# Danmarks Nationalbank - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni. Queste sono quasi sempre disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni. Qui gestirai come vengono recuperati e applicati i tassi di cambio.

La pagina di configurazione mostrerà un elenco di tutte le valute attive nel tuo negozio, permettendoti di gestire il tasso di cambio e il margine di profitto per ciascuna.

**Per ogni valuta elencata (ad esempio, USD, EUR, GBP):**

-   **Tasso di cambio attuale:**

    -   **Cosa fa questa impostazione:** Questo campo visualizza il tasso di cambio attuale per questa valuta rispetto alla valuta predefinita del tuo negozio (ad esempio, DKK se il tuo negozio ha sede in Danimarca). Questo valore viene aggiornato automaticamente dal modulo quando viene eseguito il cron job.
    -   **Effetto della modifica di questa impostazione:** Puoi regolarlo manualmente se necessario, ma lo scopo principale del modulo è automatizzare questo processo. Qualsiasi modifica manuale verrà sovrascritta dalla prossima esecuzione del cron job.
    -   **Valore consigliato:** Lascia che il modulo lo aggiorni automaticamente. Regola manualmente solo per esigenze temporanee e specifiche.
    -   **Scenario/esempio del commerciante:** Se il modulo non è ancora stato eseguito, o se hai bisogno di regolare rapidamente un tasso prima del prossimo aggiornamento programmato, potresti modificarlo manualmente. Tuttavia, per un'accuratezza a lungo termine, affidati agli aggiornamenti automatici.
-   **Markup / Markdown (%):**

    -   **Cosa fa questa impostazione:** Questo ti consente di aggiungere un margine di profitto basato su percentuale (markup) o uno sconto (markdown) al tasso di cambio recuperato.
        -   Un valore positivo (ad esempio, `+2%`) aumenterà il tasso di cambio, il che significa che i clienti pagano leggermente di più in quella valuta, assicurandoti di coprire le commissioni di conversione o di ottenere un piccolo profitto.
        -   Un valore negativo (ad esempio, `-1%`) diminuirà il tasso di cambio, rendendo il prezzo in valuta estera leggermente inferiore.
    -   **Effetto della modifica di questa impostazione:** Questa percentuale viene applicata *dopo* che il tasso ufficiale è stato recuperato dalla Danmarks Nationalbank.
        -   *Se impostato su `+2%` per USD:* Se il tasso ufficiale è 1 USD = 6.50 DKK, il tuo negozio utilizzerà 1 USD = 6.63 DKK (6.50 \* 1.02).
        -   *Se impostato su `-1%` per EUR:* Se il tasso ufficiale è 1 EUR = 7.45 DKK, il tuo negozio utilizzerà 1 EUR = 7.3755 DKK (7.45 \* 0.99).
    -   **Valore consigliato:** Inizia con `0%` e regola in base al tuo modello di business, alle commissioni del gateway di pagamento e ai margini di profitto desiderati. Molti commercianti aggiungono un piccolo markup (ad esempio, da `0.5%` a `2%`) per coprire i costi di transazione.
    -   **Scenario/esempio del commerciante:** Il tuo processore di pagamento addebita una commissione dell'1.5% per la conversione di EUR in DKK. Puoi impostare un markup di `+1.5%` per EUR per trasferire efficacemente questo costo al cliente e mantenere il tuo margine di profitto.

**URL del Cron Job:**

-   **Cosa fa questa impostazione:** Visualizza un URL univoco che devi impostare come cron job sul tuo server. Quando questo URL viene richiamato, il modulo si connette alla Danmarks Nationalbank, recupera gli ultimi tassi di cambio, applica i markup/markdown definiti e li aggiorna nel tuo negozio PrestaShop.
-   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. Viene generato dal modulo.
-   **Valore consigliato:** Copia questo URL e impostalo nel tuo pannello di controllo dell'hosting (cPanel, Plesk, ecc.) o con un servizio cron.
-   **Scenario/esempio del commerciante:** Vuoi che i tuoi tassi di cambio si aggiornino quotidianamente alle 3 del mattino. Copieresti questo URL e configureresti un cron job sul tuo server per eseguirlo ogni giorno alle 3 del mattino.

**Pulsante Salva:**

-   **Cosa fa questa impostazione:** Applica tutte le modifiche apportate alle percentuali di Markup/Markdown.
-   **Effetto della modifica di questa impostazione:** I tuoi nuovi margini di profitto verranno salvati e applicati la prossima volta che il cron job verrà eseguito e aggiornerà i tassi.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | **Tasso di cambio attuale** (per valuta) | Aggiornato automaticamente dal cron | Visualizza il tasso attuale; le modifiche manuali sono temporanee. |
| Pagina di configurazione del modulo | **Markup / Markdown (%)** (per valuta) | `0%` (regolare secondo necessità) | Aggiunge una percentuale al tasso recuperato per gestire i margini di profitto o coprire le commissioni. |
| Pagina di configurazione del modulo | **URL del Cron Job** | URL univoco (copia e configura) | L'URL per attivare gli aggiornamenti automatici dei tassi dalla Danmarks Nationalbank. |
| Pagina di configurazione del modulo | **Pulsante Salva** | N/A | Salva le tue percentuali personalizzate di Markup/Markdown. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei tassi di cambio non si aggiornano. Cosa devo fare?**
R:

1.  **Controlla il Cron Job:** La ragione più comune è un cron job configurato in modo errato o non in esecuzione. Verifica con il tuo provider di hosting che l'URL del cron job fornito nella configurazione del modulo sia correttamente pianificato ed eseguito.
2.  **Stato del Modulo:** Assicurati che il modulo sia abilitato nel tuo Back Office di PrestaShop.
3.  **Connettività del Server:** Conferma che il tuo server abbia accesso a Internet in uscita per connettersi all'API della Danmarks Nationalbank.
4.  **Svuota Cache:** A volte, la cache di PrestaShop potrebbe impedire la visualizzazione immediata dei tassi aggiornati. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache".

**D: Posso impostare markup diversi per valute diverse?**
R: Sì, assolutamente! Questa è una delle funzionalità principali di questo modulo. Nella pagina di configurazione del modulo, troverai un campo separato "Markup / Markdown (%)" per ogni valuta attiva nel tuo negozio.

**D: Cosa succede se il servizio della Danmarks Nationalbank è temporaneamente non disponibile?**
R: Il modulo tenterà di recuperare i tassi. Se fallisce, di solito manterrà gli ultimi tassi aggiornati con successo. È progettato per essere resiliente, ma fallimenti consistenti potrebbero indicare un problema di connettività del server da parte tua o un'interruzione prolungata dalla fonte.

**D: Questo modulo influirà sul mio SEO o sugli URL dei prodotti?**
R: No, questo modulo gestisce solo i tassi di cambio valuta. Non altera gli URL dei prodotti, le meta descrizioni o altri elementi correlati al SEO. Il suo impatto è puramente sulla visualizzazione dei prezzi.

**D: Il mio tema personalizzato non sembra visualizzare correttamente i prezzi aggiornati.**
R: Questo modulo aggiorna i tassi di cambio principali di PrestaShop. Se il tuo tema utilizza le funzioni standard di PrestaShop per visualizzare i prezzi, dovrebbe riflettere le modifiche. In caso contrario, potrebbe essere un problema di caching (svuota la cache come sopra) o un tema altamente personalizzato che bypassa il rendering standard dei prezzi di PrestaShop. In questi rari casi, potrebbe essere necessario che uno sviluppatore web indaghi sulla logica di visualizzazione dei prezzi del tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Danmarks Nationalbank - tassi di cambio valuta".

### 4.1 Panoramica dell'architettura

Il modulo segue un'architettura standard per i moduli PrestaShop, utilizzando principalmente un approccio basato su cron per aggiornare i tassi di cambio valuta. Si aggancia al sistema di configurazione di PrestaShop per le impostazioni e sfrutta i controller frontali per l'esecuzione del cron. La logica principale risiede nel file principale del modulo, gestendo le chiamate API alla Danmarks Nationalbank e aggiornando le voci della tabella `ps_currency`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `dnbrates/controllers/front/cronjob.php`
        -   **Nome della classe e classe padre**: `DnbratesCronjobModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è il punto di ingresso per il cron job. Quando viene richiamato tramite l'URL univoco fornito nella configurazione back-office del modulo, attiva il processo di aggiornamento dei tassi. È progettato per essere chiamato esternamente da uno scheduler cron lato server. Gestisce la logica per il recupero dei dati dalla Danmarks Nationalbank e l'aggiornamento della tabella `ps_currency`.
    -   `dnbrates/controllers/front/index.php`
        -   **Nome della classe e classe padre**: `DnbratesIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo è un controller segnaposto, spesso incluso nei moduli ma non attivamente utilizzato per la visualizzazione specifica nel front-office nel contesto di questo modulo. Potrebbe servire come punto di ingresso predefinito o per future espansioni.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione back-office è gestita direttamente all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

Nessuna classe personalizzata o definizione di `ObjectModel` si trova nella directory `classes/`. Il modulo interagisce direttamente con la classe `Currency` e la classe `Configuration` di PrestaShop per gestire i tassi di cambio e le impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato si trova nell'archivio del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato si trova nell'archivio del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `dnbrates/views/admin.tpl`
        -   **Scopo**: Questo template renderizza il modulo di configurazione del modulo nel Back Office di PrestaShop. Visualizza l'elenco delle valute, i loro tassi di cambio attuali, i campi di input per le percentuali di markup/markdown e l'URL del cron job. Viene renderizzato dal metodo `getContent()` del file principale del modulo.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Interagisce principalmente con la tabella `ps_currency` (in particolare la colonna `conversion_rate`) per aggiornare i tassi di cambio.
    -   Le impostazioni specifiche del modulo (come le percentuali di markup/markdown per ogni valuta e l'URL del cron) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi tipicamente prefissate con `DNBRATES_`.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` delle pagine del front-office. | Non direttamente utilizzato per l'output di contenuto, ma i moduli spesso si registrano qui per il caricamento di risorse o l'inizializzazione. |
| `displayLeftColumn` | Renderizza il contenuto nella colonna sinistra delle pagine del front-office. | Non direttamente utilizzato per l'output di contenuto da questo modulo. |
| `displayRightColumn` | Renderizza il contenuto nella colonna destra delle pagine del front-office. | Non direttamente utilizzato per l'output di contenuto da questo modulo. |
| `displayFooter` | Renderizza il contenuto nel piè di pagina delle pagine del front-office. | Non direttamente utilizzato per l'output di contenuto da questo modulo. |
| `displayProductAdditionalInfo` | Renderizza il contenuto nella pagina del prodotto, tipicamente sotto le informazioni principali del prodotto. | Non direttamente utilizzato per l'output di contenuto da questo modulo. |
| `actionUpdateCurrency` | Eseguito dopo l'aggiornamento dei dettagli di una valuta. | Il modulo probabilmente utilizza questo o un hook simile internamente per garantire che la sua logica sia applicata quando i dati della valuta cambiano. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin sta impostando i suoi media (JS/CSS). | Potrebbe essere utilizzato per caricare risorse specifiche per la pagina di configurazione del modulo, anche se non sono presenti file JS/CSS personalizzati. |

*Nota: La funzione principale del modulo (aggiornamento dei tassi) è attivata dal controller frontale tramite cron, non da un hook standard di PrestaShop all'interno del ciclo di vita della richiesta.*

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Danmarks Nationalbank - tassi di cambio valuta", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e all'integrazione del modulo.
