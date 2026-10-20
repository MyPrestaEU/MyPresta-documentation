---
title: "Omnibus Directive Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Omnibus Directive Pro di MyPresta.eu."
sidebar:
  label: "Omnibus Directive Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Omnibus Directive Pro su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/omnibus-directive-pro/)
>
> ---


# Omnibus Directive Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Omnibus Directive Pro)

Questa è la schermata di configurazione principale dove controlli il comportamento centrale e le opzioni di visualizzazione del modulo Omnibus Directive Pro.

#### Impostazioni Generali

-   **Abilita Modulo:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo inizierà a tracciare i prezzi, a visualizzare le informazioni sul prezzo più basso e tutte le altre funzionalità configurate diventeranno attive.
        -   *Quando disabilitato:* Il modulo interromperà tutte le sue operazioni, inclusi il tracciamento dei prezzi e la visualizzazione nel front-office. Nessuna informazione sul prezzo più basso verrà mostrata.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Abilitalo dopo l'installazione per iniziare a conformarti alla direttiva. Disabilitalo solo se hai bisogno di sospendere temporaneamente la sua funzionalità per manutenzione o test specifici.
-   **Visualizza Prezzo Più Basso sulla Pagina Prodotto:**

    -   **Cosa fa questa impostazione:** Controlla se il badge o il testo "prezzo più basso negli ultimi 30 giorni" appare sulle singole pagine prodotto quando un prodotto è in saldo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Le informazioni sul prezzo più basso saranno visibili ai clienti su ogni pagina prodotto in cui è attiva una riduzione di prezzo.
        -   *Quando disabilitato:* Le informazioni sul prezzo più basso NON verranno mostrate sulle pagine prodotto, anche se un prodotto è in saldo.
    -   **Valore consigliato:** SÌ (Altamente raccomandato per la conformità).
    -   **Scenario / esempio per il commerciante:** Devi abilitare questa opzione per conformarti alla Direttiva Omnibus. Se la disabiliti, le tue pagine prodotto non mostreranno le informazioni richieste durante i saldi.
-   **Visualizza Prezzo Più Basso negli Elenchi Prodotti (Categoria, Ricerca, ecc.):**

    -   **Cosa fa questa impostazione:** Determina se le informazioni sul prezzo più basso vengono mostrate sulle schede prodotto negli elenchi (es. pagine di categoria, risultati di ricerca, pagine del produttore).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il badge del prezzo più basso apparirà sulle schede prodotto nelle visualizzazioni di elenco, fornendo una trasparenza precoce ai clienti.
        -   *Quando disabilitato:* Le informazioni sul prezzo più basso appariranno solo sulla singola pagina prodotto, non negli elenchi.
    -   **Valore consigliato:** SÌ (Consigliato per la massima trasparenza e visibilità della conformità).
    -   **Scenario / esempio per il commerciante:** L'abilitazione di questa opzione aiuta i clienti a identificare rapidamente i saldi conformi direttamente dalle pagine di categoria, aumentando potenzialmente i tassi di clic verso le pagine prodotto.
-   **Abilita Grafico Prezzi sulla Pagina Prodotto:**

    -   **Cosa fa questa impostazione:** Attiva un grafico interattivo sulla pagina prodotto che visualizza visivamente la cronologia dei prezzi del prodotto nel tempo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un grafico verrà incorporato nella pagina prodotto, consentendo ai clienti di vedere le fluttuazioni dei prezzi passate.
        -   *Quando disabilitato:* Il grafico dei prezzi non verrà visualizzato.
    -   **Valore consigliato:** SÌ (Migliora la trasparenza e la fiducia del cliente).
    -   **Scenario / esempio per il commerciante:** I clienti sensibili al prezzo o che desiderano verificare la legittimità di un saldo possono utilizzare questo grafico. Aggiunge un ulteriore livello di fiducia.
-   **URL Cron Pulizia Cronologia Prezzi:**

    -   **Cosa fa questa impostazione:** Fornisce un URL unico che, quando viene acceduto, attiva il processo automatizzato del modulo per pulire i dati della cronologia dei prezzi obsoleti. Questo mantiene il tuo database ottimizzato.
    -   **Effetto della modifica di questa impostazione:** Questo è un campo di sola lettura. Devi impostare un cron job sul tuo server per visitare regolarmente questo URL.
    -   **Valore consigliato:** Copia questo URL e imposta un cron job.
    -   **Scenario / esempio per il commerciante:** Imposta un cron job per eseguire questo URL una volta al giorno (es. alle 3 del mattino) per assicurarti che il tuo database della cronologia dei prezzi rimanga snello ed efficiente, impedendogli di crescere troppo nel tempo.
-   **Abilita Log di Audit CSV:**

    -   **Cosa fa questa impostazione:** Se abilitato, il modulo genererà un file CSV contenente un log dettagliato delle modifiche di prezzo e dei calcoli del prezzo più basso, che può essere utile per l'audit e la verifica della conformità.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Verrà generato e aggiornato un file CSV con le informazioni di audit.
        -   *Quando disabilitato:* Nessun log di audit verrà creato o mantenuto.
    -   **Valore consigliato:** NO (A meno che non sia specificamente richiesto per audit interni o scopi legali, poiché può consumare spazio su disco).
    -   **Scenario / esempio per il commerciante:** Se il tuo team legale o gli auditor richiedono un registro verificabile delle tue attività di conformità, abilita questa opzione. Altrimenti, generalmente non è necessaria per il funzionamento quotidiano.

#### Badge Studio

Questa sezione ti consente di personalizzare l'aspetto visivo del badge "prezzo più basso" visualizzato nel tuo negozio.

-   **Tipo di Badge:**

    -   **Cosa fa questa impostazione:** Scegli tra un "Badge Intelligente" (altamente personalizzabile con icone, colori e testo) o una visualizzazione "Testo Semplice".
    -   **Effetto della modifica di questa impostazione:**
        -   *Badge Intelligente:* Sblocca ulteriori opzioni di personalizzazione per un badge visivamente ricco.
        -   *Testo Semplice:* Visualizza solo testo semplice senza stili avanzati.
    -   **Valore consigliato:** Badge Intelligente (Offre più controllo e una migliore integrazione con il tuo tema).
    -   **Scenario / esempio per il commerciante:** Se desideri un badge prominente e brandizzato, scegli "Badge Intelligente". Se preferisci un approccio minimalista, "Testo Semplice" potrebbe essere migliore.
-   **Posizione Badge (Pagina Prodotto):**

    -   **Cosa fa questa impostazione:** Seleziona dove il badge appare sulla pagina prodotto. Le opzioni tipicamente includono "Vicino al Prezzo", "Sotto il Prezzo", "Hook Personalizzato", ecc.
    -   **Effetto della modifica di questa impostazione:** Modifica il posizionamento visivo del badge sulla pagina prodotto.
    -   **Valore consigliato:** Vicino al Prezzo (Posizionamento più comune e legalmente chiaro).
    -   **Scenario / esempio per il commerciante:** Prova diverse posizioni per vedere quale si integra meglio con il tuo tema ed è più visibile ai clienti senza essere invadente.
-   **Posizione Badge (Elenchi Prodotti):**

    -   **Cosa fa questa impostazione:** Seleziona dove il badge appare sulle schede prodotto nelle pagine di elenco. Le opzioni tipicamente includono "Sotto il Nome Prodotto", "Sotto il Prezzo", "Hook Personalizzato", ecc.
    -   **Effetto della modifica di questa impostazione:** Modifica il posizionamento visivo del badge sulle schede prodotto.
    -   **Valore consigliato:** Sotto il Prezzo (Chiaro e coerente con il posizionamento della pagina prodotto).
    -   **Scenario / esempio per il commerciante:** Assicurati che il badge non si sovrapponga ad altri elementi sulle tue schede prodotto, specialmente su mobile.
-   **Testo Badge:**

    -   **Cosa fa questa impostazione:** Personalizza il testo effettivo visualizzato all'interno del badge. Puoi usare segnaposto come `{lowest_price}` per il valore effettivo del prezzo più basso.
    -   **Effetto della modifica di questa impostazione:** Modifica il messaggio che i clienti leggono.
    -   **Valore consigliato:** "Prezzo più basso negli ultimi 30 giorni: {lowest\_price}" (Chiaro e conforme).
    -   **Scenario / esempio per il commerciante:** Potresti tradurre questo testo per diverse lingue o riformularlo leggermente per adattarlo al tono del tuo brand, purché il significato rimanga chiaro e conforme.
-   **Colore Sfondo Badge:**

    -   **Cosa fa questa impostazione:** Imposta il colore di sfondo del Badge Intelligente.
    -   **Effetto della modifica di questa impostazione:** Modifica lo sfondo visivo del badge.
    -   **Valore consigliato:** Un colore che contrasti bene con il tuo testo e il tuo tema, ad esempio un grigio chiaro o un colore accentuato del brand.
    -   **Scenario / esempio per il commerciante:** Scegli un colore che faccia risaltare il badge ma che abbia comunque un aspetto professionale e si integri con il design del tuo negozio.
-   **Colore Testo Badge:**

    -   **Cosa fa questa impostazione:** Imposta il colore del testo all'interno del Badge Intelligente.
    -   **Effetto della modifica di questa impostazione:** Modifica il colore visivo del testo.
    -   **Valore consigliato:** Un colore altamente leggibile rispetto al colore di sfondo scelto, ad esempio nero o grigio scuro.
    -   **Scenario / esempio per il commerciante:** Assicurati un contrasto elevato per accessibilità e leggibilità.
-   **Icona Badge:**

    -   **Cosa fa questa impostazione:** Ti consente di selezionare un'icona da visualizzare accanto al testo nel Badge Intelligente.
    -   **Effetto della modifica di questa impostazione:** Aggiunge un'icona visiva al badge.
    -   **Valore consigliato:** Un'icona pertinente, come un'icona "tag" o "info".
    -   **Scenario / esempio per il commerciante:** Una piccola icona chiara può attirare l'attenzione sul badge e rendere il suo scopo più intuitivo.

#### Pannello Analisi

Questa sezione fornisce informazioni sulle prestazioni del tuo modulo e sullo stato di conformità.

-   **Visualizza Analisi:**
    -   **Cosa fa questa impostazione:** Questo pulsante apre un pannello dedicato all'interno del tuo Back Office, visualizzando statistiche relative al tracciamento dei prezzi, ai prodotti in saldo e allo stato di conformità.
    -   **Effetto della modifica di questa impostazione:** Cliccando su questo pulsante si naviga alla dashboard delle analisi.
    -   **Valore consigliato:** Controlla regolarmente questa sezione.
    -   **Scenario / esempio per il commerciante:** Utilizza il pannello di analisi per monitorare quanti prodotti stanno attualmente visualizzando il prezzo più basso, identificare eventuali problemi potenziali o rivedere lo stato generale di conformità del tuo negozio.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Abilita Modulo | SÌ | Attiva/disattiva tutte le funzionalità del modulo. |
| | Visualizza Prezzo Più Basso sulla Pagina Prodotto | SÌ | Mostra il prezzo più basso degli ultimi 30 giorni sulle pagine prodotto durante i saldi. |
| | Visualizza Prezzo Più Basso negli Elenchi Prodotti | SÌ | Mostra il prezzo più basso degli ultimi 30 giorni sulle pagine di categoria/ricerca durante i saldi. |
| | Abilita Grafico Prezzi sulla Pagina Prodotto | SÌ | Visualizza un grafico interattivo della cronologia dei prezzi sulle pagine prodotto. |
| | URL Cron Pulizia Cronologia Prezzi | (Copia e Imposta) | URL per la pulizia automatica del database. Esegui quotidianamente. |
| | Abilita Log di Audit CSV | NO | Crea un log dettagliato delle modifiche di prezzo per l'audit. |
| **Badge Studio** | Tipo di Badge | Badge Intelligente | Scegli tra badge personalizzabile o testo semplice. |
| | Posizione Badge (Pagina Prodotto) | Vicino al Prezzo | Imposta il posizionamento del badge sulle singole pagine prodotto. |
| | Posizione Badge (Elenchi Prodotti) | Sotto il Prezzo | Imposta il posizionamento del badge sulle schede prodotto negli elenchi. |
| | Testo Badge | "Prezzo più basso negli ultimi 30 giorni: {lowest\_price}" | Testo personalizzabile per il badge. |
| | Colore Sfondo Badge | (Dipendente dal tema) | Imposta il colore di sfondo del Badge Intelligente. |
| | Colore Testo Badge | (Dipendente dal tema) | Imposta il colore del testo del Badge Intelligente. |
| | Icona Badge | (Icona pertinente) | Aggiunge un'icona visiva al Badge Intelligente. |
| **Pannello Analisi** | Visualizza Analisi | (Clicca pulsante) | Apre una dashboard per le statistiche di conformità e tracciamento dei prezzi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il badge del prezzo più basso non viene visualizzato sulle mie pagine prodotto, anche se l'ho abilitato.**
R:

1.  **Controlla lo stato del modulo:** Assicurati che l'impostazione "Abilita Modulo" sia impostata su SÌ.
2.  **Prodotto in saldo?** Il badge appare solo per i prodotti che sono attualmente in saldo (hanno un prezzo specifico o uno sconto applicato). Assicurati che il prodotto che stai testando abbia una riduzione di prezzo attiva.
3.  **Svuota la cache:** Vai su **Parametri Avanzati > Prestazioni** nel tuo Back Office PrestaShop e svuota la cache Smarty, la cache del browser e qualsiasi altra cache (es. cache CDN) che potresti utilizzare.
4.  **Compatibilità del tema:** Sebbene il modulo sia progettato per un'ampia compatibilità, temi molto personalizzati potrebbero richiedere piccole modifiche. Se il problema persiste, contatta il supporto MyPresta.eu.

**D2: Il grafico della cronologia dei prezzi non mostra dati o sembra incompleto.**
R:

1.  **Modulo Abilitato:** Assicurati che "Abilita Grafico Prezzi sulla Pagina Prodotto" sia impostato su SÌ.
2.  **Modifiche di Prezzo:** Il grafico visualizzerà i dati solo se il prodotto ha avuto modifiche di prezzo registrate da quando il modulo è stato installato e attivo. Se il prezzo di un prodotto non è mai cambiato, non ci sarà cronologia da mostrare.
3.  **Tempo per la Raccolta Dati:** Il modulo impiega tempo per raccogliere la cronologia dei prezzi. Se lo hai appena installato, i dati si accumuleranno man mano che i prezzi cambiano nel corso di giorni/settimane.

**D3: Ogni quanto tempo dovrei eseguire il Cron Job di Pulizia della Cronologia dei Prezzi?**
R: Si consiglia di eseguire il cron job una volta ogni 24 ore. Questa frequenza è sufficiente per mantenere il database ottimizzato senza sovraccaricare eccessivamente il server.

**D4: Lo stile del mio tema personalizzato è in conflitto con il badge del modulo. Come posso risolvere questo problema?**
R: Il "Badge Studio" offre ampie possibilità di personalizzazione per colori, testo e icone. Prova prima a regolare queste impostazioni per abbinarle al tuo tema. Se hai ancora conflitti di stile, potresti aver bisogno di un webmaster per applicare override CSS personalizzati. I file CSS del modulo sono progettati per essere facilmente sovrascritti dal foglio di stile del tuo tema.

**D5: Cosa succede se disabilito il modulo? Elimina i miei dati di cronologia dei prezzi?**
R: La disabilitazione del modulo interromperà la sua visualizzazione nel front-office e i processi in background, ma in genere non elimina i dati di cronologia dei prezzi raccolti. Se lo riabiliti in seguito, i dati dovrebbero essere ancora disponibili. Tuttavia, per una rimozione completa dei dati, dovresti disinstallare il modulo e scegliere di eliminare i suoi dati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita dell'architettura tecnica del modulo Omnibus Directive Pro, destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'Architettura

Il modulo Omnibus Directive Pro segue un modello MVC (Model-View-Controller) standard di PrestaShop, con un focus sugli hook basati su eventi per l'integrazione. Estende principalmente `Module` per la sua funzionalità e configurazione principali, utilizza `ModuleFrontController` per azioni specifiche del front-office (come la pulizia cron), e sfrutta i template Smarty per il rendering. La cronologia dei prezzi è gestita tramite interazione diretta con il database e valori di `Configuration`. Il modulo integra un "Badge Studio" e un "Pannello Analisi" all'interno del Back Office per un maggiore controllo e approfondimenti per il commerciante.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `omnipro/controllers/front/cleanupcron.php`
    -   **Nome classe e classe padre:** `OmniproCleanupcronModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller è progettato per essere acceduto tramite un cron job. Quando invocato, esegue la logica di pulizia interna del modulo per i dati della cronologia dei prezzi, tipicamente rimuovendo i record obsoleti per mantenere le prestazioni del database. Non rende alcun output visivo al browser, di solito restituendo un semplice messaggio di successo o errore.
-   `omnipro/controllers/front/index.php`
    -   **Nome classe e classe padre:** `OmniproIndexModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller probabilmente funge da fallback o da punto di ingresso generale per le azioni del modulo nel front-office che non richiedono un routing specifico, oppure potrebbe essere un segnaposto. Data la funzione principale del modulo, è meno probabile che gestisca direttamente interazioni utente complesse, ma potrebbe essere utilizzato per semplici recuperi di dati o controlli di stato.

#### Controller Admin Back-Office

Non sono stati identificati controller Admin dedicati (`controllers/admin/`), suggerendo che tutta la configurazione e l'analisi del Back Office sono gestite direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Non sono state identificate classi personalizzate che estendono `ObjectModel` nella directory `classes/`. Ciò indica che i dati della cronologia dei prezzi sono probabilmente archiviati direttamente in `ps_configuration` o in una tabella personalizzata gestita dal file principale del modulo (`omnipro/index.php`) senza un wrapper `ObjectModel` dedicato.

### 4.4 Risorse JavaScript (`views/js/`)

-   `omnipro/views/js/admin-analytics.js`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Questo script è responsabile dell'alimentazione degli elementi interattivi e della visualizzazione dei dati all'interno del "Pannello Analisi" del modulo nel Back Office. Probabilmente gestisce le richieste AJAX per recuperare i dati analitici, rende i grafici (ad esempio, utilizzando Chart.js o librerie simili) e aggiorna l'interfaccia utente in base alle interazioni dell'utente all'interno della dashboard analitica.
-   `omnipro/views/js/admin-badge-studio.js`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Questo script fornisce la funzionalità interattiva per la schermata di configurazione del "Badge Studio". Gestisce le anteprime in tempo reale del badge mentre il commerciante regola colori, testo, icone e posizioni. Probabilmente gestisce i selettori di colore, gli aggiornamenti dei campi di input e il rendering dinamico di un badge di anteprima.
-   `omnipro/views/js/admin-config.js`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Uno script generico per la pagina di configurazione principale del modulo. Potrebbe gestire la convalida del modulo, la visualizzazione condizionale delle impostazioni in base ad altre selezioni (ad esempio, mostrando la personalizzazione del badge solo se è selezionato "Badge Intelligente") e miglioramenti generali dell'interfaccia utente per il modulo di configurazione.
-   `omnipro/views/js/front-chart.js`
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo script è responsabile del rendering del grafico interattivo della cronologia dei prezzi sulla pagina prodotto. Probabilmente recupera i dati dei prezzi tramite AJAX (possibilmente da un controller frontale dedicato o un hook), inizializza una libreria di grafici (ad esempio, Chart.js) e visualizza visivamente l'evoluzione dei prezzi al cliente.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `omnipro/views/css/admin-analytics.css`
    -   **Ambito:** Stile amministrativo del Back-office.
    -   **Descrizione:** Fogli di stile specifici per il layout e l'aspetto del "Pannello Analisi" nella configurazione del Back Office del modulo.
-   `omnipro/views/css/admin-badge-studio.css`
    -   **Ambito:** Stile amministrativo del Back-office.
    -   **Descrizione:** Fogli di stile per l'interfaccia del "Badge Studio", inclusa la stilizzazione per i selettori di colore, gli elementi di anteprima e il layout delle opzioni di personalizzazione.
-   `omnipro/views/css/admin-config.css`
    -   **Ambito:** Stile amministrativo del Back-office.
    -   **Descrizione:** Stile generale per il modulo di configurazione principale nel Back Office, garantendo un'interfaccia coerente e user-friendly.
-   `omnipro/views/css/omnibus-classic.css`
    -   **Ambito:** Stile cliente del Front-office.
    -   **Descrizione:** Fornisce uno stile predefinito per il badge del prezzo più basso e potenzialmente per il grafico dei prezzi, specificamente adattato per i temi "Classic" di PrestaShop più vecchi o per i temi che ne imitano la struttura.
-   `omnipro/views/css/omnibus-hummingbird.css`
    -   **Ambito:** Stile cliente del Front-office.
    -   **Descrizione:** Fornisce uno stile predefinito per il badge del prezzo più basso e potenzialmente per il grafico dei prezzi, specificamente ottimizzato per il nuovo tema "Hummingbird" di PrestaShop.
-   `omnipro/views/css/omnibus.css`
    -   **Ambito:** Stile cliente del Front-office.
    -   **Descrizione:** Stili core del front-office per il badge del prezzo più basso e il grafico dei prezzi, applicabili a vari temi. Questo probabilmente contiene le regole visive fondamentali, con `omnibus-classic.css` e `omnibus-hummingbird.css` che forniscono override o aggiunte specifiche per il tema.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   `omnipro/lib/searchTool/views/scripts.tpl`
    -   **Ambito:** Non chiaro senza contesto, ma `lib` suggerisce una libreria di terze parti o un'utilità interna. `scripts.tpl` spesso include risorse JS o CSS.
    -   **Descrizione:** Questo template probabilmente include file JavaScript o CSS richiesti da uno strumento di ricerca interno o un'utilità utilizzata dal modulo, possibilmente per l'elaborazione dei dati o componenti specifici dell'interfaccia utente all'interno dell'amministrazione.
-   `omnipro/views/templates/admin/analytics-panel.tpl`
    -   **Ambito:** Template amministrativo.
    -   **Descrizione:** Rende la struttura HTML per il "Pannello Analisi" nel Back Office, inclusi i segnaposto per grafici, statistiche e tabelle di dati.
-   `omnipro/views/templates/admin/badge-studio.tpl`
    -   **Ambito:** Template amministrativo.
    -   **Descrizione:** Rende il modulo HTML e l'area di anteprima per la configurazione del "Badge Studio", consentendo ai commercianti di personalizzare l'aspetto del badge del prezzo più basso.
-   `omnipro/views/templates/admin/configure.tpl`
    -   **Ambito:** Template amministrativo.
    -   **Descrizione:** Il template di configurazione principale per il modulo, reso da `getContent()` in `omnipro/index.php`. Include tutte le impostazioni generali e probabilmente include `analytics-panel.tpl` e `badge-studio.tpl` o link ad essi.
-   `omnipro/views/templates/hook/omnibus-badge.tpl`
    -   **Ambito:** Template hook (Front-office).
    -   **Descrizione:** Questo template viene reso in vari hook del front-office (es. `displayProductPriceBlock`, `displayProductListFunctionalButtons`) per produrre l'HTML per il badge del prezzo più basso sulle pagine prodotto e negli elenchi. Riceve variabili contenenti il prezzo più basso e altre opzioni di personalizzazione del badge.
-   `omnipro/views/templates/hook/omnibus.tpl`
    -   **Ambito:** Template hook (Front-office).
    -   **Descrizione:** Un template hook più generale, potenzialmente utilizzato per incorporare il grafico dei prezzi (`front-chart.js`) o altri contenuti correlati al modulo sulla pagina prodotto, o per l'inizializzazione generale del modulo in `displayHeader` o `displayFooter`.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    -   Il modulo probabilmente memorizza le sue impostazioni di configurazione principali in `ps_configuration` (es. `OMNIPRO_ENABLED`, `OMNIPRO_DISPLAY_PRODUCT_PAGE`).
    -   Data la funzionalità "cronologia dei prezzi" e la "pulizia cron", è altamente probabile che il modulo crei almeno una tabella di database personalizzata (es. `ps_omnipro_price_history`) per memorizzare i record dei prezzi dei prodotti nel tempo. Questa tabella conterrebbe tipicamente i campi `id_product`, `id_product_attribute`, `id_shop`, `id_currency`, `price` e `date_add`.
    -   Se il "Log di Audit CSV" è abilitato, potrebbe memorizzare riferimenti a file CSV generati o voci di log in una tabella dedicata.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta risorse CSS/JS per il front-office, inizializza variabili JS a livello di modulo. |
| `displayProductPriceBlock` | Vicino al prezzo del prodotto sulla pagina prodotto. | Rende il badge del prezzo più basso (`omnibus-badge.tpl`) sulla pagina prodotto. |
| `displayProductListFunctionalButtons` | All'interno degli elenchi di prodotti (categoria, ricerca, ecc.). | Rende il badge del prezzo più basso (`omnibus-badge.tpl`) sulle schede prodotto. |
| `displayFooterProduct` | In fondo alla pagina prodotto. | Potenziale rendering del grafico dei prezzi (`omnibus.tpl` con `front-chart.js`). |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Attiva la registrazione della cronologia dei prezzi per il prodotto aggiornato. |
| `actionProductAdd` | Dopo l'aggiunta di un nuovo prodotto. | Inizializza la registrazione della cronologia dei prezzi per il nuovo prodotto. |
| `actionProductDelete` | Dopo l'eliminazione di un prodotto. | Pulisce i dati associati alla cronologia dei prezzi. |
| `actionUpdateQuantity` | Dopo la modifica della quantità del prodotto. | (Meno probabile per la cronologia dei prezzi, ma possibile per logiche correlate). |
| `actionUpdateSpecificPrice` | Dopo l'aggiunta/aggiornamento di un prezzo specifico (sconto). | Cruciale per attivare il calcolo del prezzo più basso e la logica di visualizzazione. |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renda il suo output. | Aggiunge condizionalmente CSS/JS del front-office in base al contesto della pagina. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renda il suo output. | Aggiunge condizionalmente CSS/JS del back-office per le pagine di configurazione. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Omnibus Directive Pro, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità e all'integrazione del modulo.
