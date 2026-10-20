---
title: "Free Shipping Progress Bar Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Free Shipping Progress Bar Pro di MyPresta.eu."
sidebar:
  label: "Free Shipping Progress Bar Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Free Shipping Progress Bar Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/free-shipping-progress-bar-pro/)
>
> ---


# Free Shipping Progress Bar Pro

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Sono generalmente richieste le estensioni PHP standard (cURL, JSON, OpenSSL) e di solito sono abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è l'area di configurazione principale dove imposterai tutte le regole, l'aspetto e il comportamento della tua Free Shipping Progress Bar. La pagina è progettata per essere intuitiva, guidandoti attraverso varie sezioni.

#### Impostazioni generali

-   **Cosa fa questa impostazione:** Controlla l'attivazione generale e il comportamento di base della barra di avanzamento.
-   **Effetto della modifica di questa impostazione:**
    -   *Abilita/Disabilita Modulo:* Attiva o disattiva l'intera funzionalità della barra di avanzamento per il tuo negozio.
    -   *Posizione di visualizzazione:* Determina dove appare la barra di avanzamento nel tuo front office (ad esempio, Header, Footer, Pagina Prodotto, Pagina Carrello).
    -   *Barra fissa:* Rende la barra "fissa" nella parte superiore o inferiore dello schermo mentre l'utente scorre, mantenendola visibile.
-   **Valore consigliato:**
    -   *Abilita Modulo:* SÌ (per attivare la funzione).
    -   *Posizione di visualizzazione:* Header (spesso la più efficace per la visibilità).
    -   *Barra fissa:* SÌ (per il massimo impatto).
-   **Scenario/esempio del commerciante:** Vuoi che la barra di avanzamento sia sempre visibile nella parte superiore del tuo negozio per ricordare costantemente ai clienti la spedizione gratuita. Abiliteresti il modulo, imposteresti la posizione di visualizzazione su "Header" e abiliteresti "Barra fissa".

#### Soglie di spedizione gratuita

-   **Cosa fa questa impostazione:** Definisce l'importo che i clienti devono spendere per qualificarsi per la spedizione gratuita. Questo è il cuore della funzionalità del modulo. Puoi impostare una soglia predefinita e poi sovrascriverla con regole specifiche per paesi o gruppi di clienti.
-   **Effetto della modifica di questa impostazione:**
    -   *Soglia predefinita:* Imposta l'importo base per tutti i clienti non coperti da regole specifiche.
    -   *Soglie specifiche per paese:* Ti consente di impostare diversi importi di spedizione gratuita per i clienti di paesi particolari (ad esempio, più alti per la spedizione internazionale).
    -   *Soglie specifiche per gruppo di clienti:* Personalizza le soglie per diversi gruppi di clienti (ad esempio, inferiori per i clienti VIP, superiori per i grossisti).
-   **Valore consigliato:** Inizia con una soglia predefinita che abbia senso per il tuo valore medio dell'ordine e i costi di spedizione. Quindi, aggiungi regole specifiche secondo necessità.
-   **Scenario/esempio del commerciante:** La tua spedizione gratuita predefinita è di 100 €. Tuttavia, per i clienti in Canada, vuoi che sia di 150 € a causa dei costi di spedizione più elevati. Imposteresti la soglia predefinita a 100 € e poi aggiungeresti una regola per il Canada a 150 €. Per il tuo gruppo di clienti "Grossisti", potresti impostarla a 500 €.

#### Designer visivo

-   **Cosa fa questa impostazione:** Fornisce un'interfaccia user-friendly per personalizzare l'aspetto della tua barra di avanzamento senza alcuna codifica. Puoi cambiare colori, font, stili della barra e altro ancora.
-   **Effetto della modifica di questa impostazione:** Influisce direttamente sull'aspetto visivo della barra di avanzamento nel tuo front office.
    -   *Colori:* Regola i colori di sfondo, testo e riempimento della barra di avanzamento per abbinarli al tuo marchio.
    -   *Font e dimensioni:* Personalizza gli stili del testo per i messaggi.
    -   *Stile della barra:* Scegli tra diversi stili visivi per la barra di avanzamento stessa (ad esempio, arrotondata, piatta).
    -   *Animazioni:* Aggiungi animazioni sottili per un'esperienza più coinvolgente.
-   **Valore consigliato:** Sperimenta per trovare un design visivamente accattivante, chiaramente visibile e coerente con il branding del tuo negozio.
-   **Scenario/esempio del commerciante:** Il tuo negozio utilizza una specifica tonalità di blu e un font pulito e moderno. Utilizzeresti il designer visivo per impostare lo sfondo della barra di avanzamento su quel blu, il testo su bianco e scegliere un font sans-serif per abbinarlo al tuo tema.

#### Messaggi dinamici

-   **Cosa fa questa impostazione:** Ti consente di creare messaggi personalizzati che appaiono nella barra di avanzamento, cambiando in base ai progressi del cliente verso la spedizione gratuita. Puoi utilizzare segnaposto per inserire valori dinamici come l'importo rimanente.
-   **Effetto della modifica di questa impostazione:**
    -   *Messaggi per "Non ancora qualificato":* Visualizzato quando il cliente non ha raggiunto la soglia.
    -   *Messaggi per "Qualificato":* Visualizzato una volta che il cliente ha raggiunto o superato la soglia.
    -   *Segnaposto:* L'utilizzo di `[amount_left]`, `[total_cart]`, `[free_shipping_threshold]`, `[currency_symbol]` inserirà dinamicamente questi valori nei tuoi messaggi.
-   **Valore consigliato:** Mantieni i messaggi chiari, concisi e incoraggianti. Usa i segnaposto per renderli dinamici e personali.
-   **Scenario/esempio del commerciante:**
    -   *Non qualificato:* "Spendi [amount\_left] in più per ottenere la spedizione GRATUITA!"
    -   *Qualificato:* "Congratulazioni! Il tuo ordine si qualifica per la spedizione GRATUITA!"
    Questo comunica chiaramente l'obiettivo e celebra il raggiungimento.

#### A/B Testing e Analytics

-   **Cosa fa questa impostazione:** Ti consente di eseguire test A/B su diverse configurazioni della barra di avanzamento (ad esempio, messaggi, colori o soglie diverse) e di monitorarne le prestazioni.
-   **Effetto della modifica di questa impostazione:**
    -   *Abilita la modalità A/B Test:* Ti consente di creare variazioni della tua barra di avanzamento.
    -   *Traccia le conversioni:* Registra come le diverse variazioni influiscono sui tuoi tassi di conversione e sul valore medio dell'ordine.
-   **Valore consigliato:** Abilita questa funzione una volta che la tua configurazione di base è stabile. Usala per ottimizzare continuamente l'efficacia della tua barra di avanzamento.
-   **Scenario/esempio del commerciante:** Vuoi testare se "Spendi X € in più per la spedizione GRATUITA!" funziona meglio di "Sblocca la spedizione GRATUITA con soli X € in più!". Imposteresti due varianti e lasceresti che il modulo tracci quale porta a più vendite.

#### Impostazioni avanzate

-   **Cosa fa questa impostazione:** Contiene opzioni per aspetti più tecnici, come la memorizzazione nella cache, la compatibilità con temi specifici o CSS/JS personalizzati.
-   **Effetto della modifica di questa impostazione:** Può influire sulle prestazioni, sull'integrazione del tema o consentire personalizzazioni altamente specifiche.
    -   *Impostazioni cache:* Migliora la velocità di caricamento memorizzando nella cache il contenuto della barra.
    -   *CSS/JS personalizzati:* Consente agli sviluppatori di aggiungere il proprio stile o script.
-   **Valore consigliato:** Generalmente, lasciali ai valori predefiniti a meno che tu non abbia un'esigenza specifica o ti sia stato consigliato da uno sviluppatore.
-   **Scenario/esempio del commerciante:** Il tuo tema personalizzato ha una struttura di intestazione unica e la barra di avanzamento non si allinea perfettamente. Uno sviluppatore potrebbe utilizzare il campo "CSS personalizzato" per aggiungere regole di stile specifiche per correggere l'allineamento.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Impostazioni generali** | Abilita modulo | SÌ | Attiva/disattiva l'intera funzionalità della barra di avanzamento. |
|  | Posizione di visualizzazione | Header | Dove appare la barra (Header, Footer, Prodotto, Carrello, Colonne). |
|  | Barra fissa | SÌ | Rende la barra fissa nella parte superiore/inferiore dello schermo. |
| **Soglie di spedizione gratuita** | Soglia predefinita | Importo di spedizione gratuita del tuo negozio | Importo base per la spedizione gratuita. |
|  | Regole per paese | Secondo necessità | Sovrascrive il valore predefinito per paesi specifici. |
|  | Regole per gruppo di clienti | Secondo necessità | Sovrascrive il valore predefinito per gruppi di clienti specifici. |
| **Designer visivo** | Colore sfondo barra | Dipendente dal tema | Cambia il colore di sfondo della barra. |
|  | Colore riempimento avanzamento | Dipendente dal tema | Cambia il colore della sezione di avanzamento riempita. |
|  | Colore testo | Dipendente dal tema | Cambia il colore dei messaggi. |
|  | Famiglia / Dimensione font | Dipendente dal tema | Personalizza l'aspetto del testo. |
|  | Stile barra | Predefinito | Design visivo della barra di avanzamento stessa. |
| **Messaggi dinamici** | Messaggio - Non qualificato | "Spendi [amount\_left] in più per la spedizione GRATUITA!" | Messaggio visualizzato quando l'obiettivo non è raggiunto. |
|  | Messaggio - Qualificato | "Congratulazioni! Il tuo ordine si qualifica per la spedizione GRATUITA!" | Messaggio visualizzato quando l'obiettivo è raggiunto. |
| **A/B Testing e Analytics** | Abilita A/B Testing | NO (inizialmente) | Consente di eseguire test su diverse configurazioni della barra. |
|  | Traccia conversioni | SÌ (durante A/B testing) | Registra le prestazioni delle diverse versioni della barra. |
| **Impostazioni avanzate** | Abilita cache | SÌ | Migliora la velocità di caricamento della barra. |
|  | CSS personalizzato | Lascia vuoto | Per override di stile avanzati da parte degli sviluppatori. |
|  | JS personalizzato | Lascia vuoto | Per aggiunte di script avanzate da parte degli sviluppatori. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La barra di avanzamento non viene visualizzata nel mio negozio o non si aggiorna.**
**R1:**

-   **Verifica lo stato del modulo:** Innanzitutto, assicurati che il modulo sia abilitato nel tuo Back Office di PrestaShop in **Moduli > Gestione moduli**.
-   **Verifica la posizione di visualizzazione:** Vai alla configurazione del modulo e controlla l'impostazione "Posizione di visualizzazione". Assicurati che sia impostata su un hook visibile (ad esempio, Header, Footer). Se hai scelto un hook di colonna, assicurati che il tuo tema visualizzi effettivamente quella colonna.
-   **Svuota la cache:** PrestaShop spesso memorizza i contenuti nella cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). Inoltre, svuota la cache del tuo browser.
-   **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Se il problema persiste dopo aver svuotato la cache, contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D2: La barra di avanzamento ha un aspetto strano o non corrisponde al design del mio tema.**
**R2:**

-   **Usa il Designer Visivo:** Il modulo include una sezione "Designer Visivo" nella sua configurazione. Usala per regolare colori, font e stili per abbinarli meglio al tuo tema.
-   **CSS personalizzato:** Se il designer visivo non è sufficiente, il tuo webmaster o uno sviluppatore può utilizzare il campo "CSS personalizzato" nelle impostazioni avanzate del modulo per aggiungere regole di stile specifiche che sovrascrivono quelle predefinite.
-   **Cache del tema:** Dopo aver apportato modifiche al design, svuota sempre la cache di PrestaShop (**Parametri avanzati > Prestazioni**) e la cache del tuo browser.

**D3: L'importo della spedizione gratuita non è corretto o non cambia per alcuni clienti.**
**R3:**

-   **Controlla le regole di soglia:** Vai alla sezione "Soglie di spedizione gratuita" nella configurazione del modulo.
    -   Verifica che la "Soglia predefinita" sia corretta.
    -   Controlla se eventuali "Soglie specifiche per paese" o "Soglie specifiche per gruppo di clienti" stanno sovrascrivendo il valore predefinito per i clienti interessati. Assicurati che le regole siano impostate correttamente per i paesi/gruppi pertinenti.
-   **Valuta:** Assicurati che la tua valuta predefinita e la valuta utilizzata per la soglia corrispondano.
-   **Calcolo del carrello:** Il modulo si basa sul totale del carrello di PrestaShop. Assicurati che i tuoi prodotti abbiano prezzi corretti e che le regole fiscali siano applicate come previsto.

**D4: Come posso tradurre i messaggi in diverse lingue per i miei clienti internazionali?**
**R4:**

-   Il modulo supporta il sistema di traduzione nativo di PrestaShop.
-   Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
-   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona il modulo "Free Shipping Progress Bar Pro".
-   Potrai quindi tradurre tutti i messaggi dinamici e altri testi visualizzati dal modulo nelle lingue desiderate. Ricorda di salvare le modifiche.

**D5: La barra di avanzamento non viene visualizzata sui dispositivi mobili o non è reattiva.**
**R5:**

-   Il modulo è progettato per essere completamente reattivo.
-   **Svuota la cache:** Come sempre, svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**) e la cache del tuo browser mobile.
-   **Controlla la posizione di visualizzazione:** Assicurati che la posizione di visualizzazione scelta (ad esempio, Header) sia una che il tuo tema rende in modo prominente sui dispositivi mobili. Alcuni temi potrebbero nascondere determinati elementi su schermi più piccoli.
-   **Conflitti del tema:** Molto raramente, un tema mobile altamente personalizzato potrebbe avere CSS in conflitto. Se il problema persiste, consulta il supporto MyPresta.eu o il tuo webmaster.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo Free Shipping Progress Bar Pro, destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo `Free Shipping Progress Bar Pro` (`smartfreeshippingpro`) segue l'architettura standard dei moduli PrestaShop, sfruttando principalmente gli hook per la visualizzazione front-office e un `ModuleFrontController` dedicato per le interazioni AJAX. La configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo, che renderizza un template Smarty per l'interfaccia back-office. Utilizza la classe `Configuration` di PrestaShop per memorizzare le impostazioni e si basa sui servizi core di PrestaShop per le informazioni sul carrello e sulla valuta. Il modulo enfatizza un approccio di configurazione visiva con JS dedicato per l'interfaccia di amministrazione.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `smartfreeshippingpro/controllers/front/index.php`
        -   **Nome classe:** `SmartFreeShippingProIndexModuleFrontController` (probabilmente, basato sulla convenzione di denominazione dei file)
        -   **Classe padre:** `ModuleFrontController`
        -   **Responsabilità:** Questo controller funge probabilmente da base o punto di ingresso per le interazioni front-office, sebbene i suoi metodi specifici possano essere minimi se `refresh.php` gestisce l'AJAX primario. Potrebbe essere responsabile della configurazione iniziale dei dati o della logica front-office non AJAX.
    -   `smartfreeshippingpro/controllers/front/refresh.php`
        -   **Nome classe:** `SmartFreeShippingProRefreshModuleFrontController`
        -   **Classe padre:** `ModuleFrontController`
        -   **Responsabilità:** Questo è l'endpoint AJAX critico. Risponde alle richieste (ad esempio, da `front.js`) per aggiornare la barra di avanzamento della spedizione gratuita. Recupera il totale corrente del carrello, calcola l'importo rimanente per la spedizione gratuita in base alle soglie configurate (regole predefinite, per paese, per gruppo) e restituisce i dati di avanzamento e i messaggi aggiornati, tipicamente in formato JSON. Questo controller è responsabile degli aggiornamenti in tempo reale della barra.
-   **Controller Admin Back-Office**:

    -   Non sono presenti file `AdminController` dedicati. Tutta la configurazione del back-office è gestita all'interno del metodo `getContent()` del file principale del modulo (`index.php`).

### 4.3 Classi e modelli core (`classes/`)

Nessuna classe personalizzata che estende `ObjectModel` o altre classi core di PrestaShop è esplicitamente elencata nell'inventario fornito. Il modulo si basa probabilmente sulle classi `Cart`, `Context`, `Configuration`, `Currency` e `Country` integrate di PrestaShop per la sua logica.

### 4.4 Risorse JavaScript (`views/js/`)

-   `smartfreeshippingpro/views/js/admin-config.js`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Probabilmente gestisce le interazioni generali del modulo di configurazione, il salvataggio delle impostazioni e potenzialmente la convalida del modulo per la pagina di configurazione principale del modulo.
-   `smartfreeshippingpro/views/js/admin-placeholders.js`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Gestisce l'inserimento dinamico di segnaposto (ad esempio, `[amount_left]`, `[total_cart]`) nei campi di input dei messaggi all'interno della configurazione di amministrazione, rendendo più facile per i commercianti creare messaggi dinamici.
-   `smartfreeshippingpro/views/js/admin-threshold-picker.js`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Gestisce la logica per l'aggiunta, la modifica e la rimozione delle soglie di spedizione gratuita specifiche per paese e per gruppo di clienti. Ciò comporterebbe elementi di modulo dinamici per la selezione di paesi/gruppi e l'inserimento di importi.
-   `smartfreeshippingpro/views/js/admin-visual-designer.js`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Alimenta l'interfaccia di personalizzazione visiva. Probabilmente utilizza JavaScript per aggiornare dinamicamente un'anteprima della barra di avanzamento mentre l'amministratore cambia colori, font e stili, fornendo un feedback visivo immediato.
-   `smartfreeshippingpro/views/js/admin.js`
    -   **Ambito:** Back-office.
    -   **Descrizione:** Uno script di amministrazione generico che potrebbe inizializzare altri file JS specifici per l'amministrazione, gestire eventi di amministrazione globali o fornire funzioni di utilità per l'interfaccia back-office.
-   `smartfreeshippingpro/views/js/front.js`
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo è lo script front-end principale.
        -   **Listener di eventi:** Si lega a `prestashop.on('updateCart', ...)` o eventi simili per rilevare modifiche nel carrello (aggiunta, rimozione, aggiornamento quantità).
        -   **Chiamate AJAX:** Attiva richieste AJAX al controller frontale `refresh.php` per ottenere dati aggiornati della barra di avanzamento.
        -   **Manipolazione DOM:** Aggiorna la larghezza della barra di avanzamento, i messaggi di testo e potenzialmente la sua visibilità in base alla risposta AJAX.
        -   **Animazioni:** Potrebbe includere la logica per transizioni o animazioni fluide della barra di avanzamento.
        -   **Logica della barra fissa:** Se la funzione della barra fissa è abilitata, questo script gestirebbe il posizionamento CSS (`position: fixed`) e potenzialmente i listener di eventi di scorrimento per gestirne la visibilità.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `smartfreeshippingpro/views/css/admin-config.css`
    -   **Ambito:** Styling del modulo di amministrazione back-office.
    -   **Descrizione:** Stili per il layout generale e gli elementi della pagina di configurazione principale del modulo.
-   `smartfreeshippingpro/views/css/admin-threshold-picker.css`
    -   **Ambito:** Styling del modulo di amministrazione back-office.
    -   **Descrizione:** Stili specifici per le interfacce di selezione della soglia per paese e per gruppo di clienti.
-   `smartfreeshippingpro/views/css/admin-visual-designer.css`
    -   **Ambito:** Styling del modulo di amministrazione back-office.
    -   **Descrizione:** Stili per l'interfaccia del designer visivo, inclusi selettori di colore, elementi di anteprima e layout.
-   `smartfreeshippingpro/views/css/admin.css`
    -   **Ambito:** Styling del modulo di amministrazione back-office.
    -   **Descrizione:** Stili di amministrazione generali, potenzialmente inclusi elementi comuni utilizzati in diverse sezioni di amministrazione del modulo.
-   `smartfreeshippingpro/views/css/front.css`
    -   **Ambito:** Styling del cliente front-office.
    -   **Descrizione:**
        -   Componenti principali dell'interfaccia utente: Stili il contenitore della barra di avanzamento, il riempimento dell'avanzamento e i messaggi di testo.
        -   Selettori di classi CSS chiave: Probabilmente include classi come `.smartfreeshippingpro-bar`, `.smartfreeshippingpro-progress`, `.smartfreeshippingpro-message`, `.smartfreeshippingpro-sticky`. Gli sviluppatori possono sovrascriverle nel `custom.css` del loro tema o aggiungendo CSS personalizzato nelle impostazioni avanzate del modulo.
        -   Regole di progettazione reattiva per varie dimensioni dello schermo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template di amministrazione (`views/templates/admin/`)**:

    -   `smartfreeshippingpro/views/templates/admin/configure.tpl`
        -   **Descrizione:** Il template principale per la pagina di configurazione del modulo nel Back Office. Renderizza l'intero modulo, incluse le impostazioni generali, i collegamenti ad altri sotto-template per sezioni specifiche (come il designer visivo, il selettore di soglie).
    -   `smartfreeshippingpro/views/templates/admin/country-priority.tpl`
        -   **Descrizione:** Probabilmente un sotto-template utilizzato all'interno di `configure.tpl` per gestire la priorità delle regole specifiche per paese se più regole potrebbero essere applicate (ad esempio, un cliente si trova in un paese con una regola specifica, ma fa anche parte di un gruppo con un'altra regola).
    -   `smartfreeshippingpro/views/templates/admin/country-rules-picker.tpl`
        -   **Descrizione:** Un sotto-template per l'interfaccia in cui gli amministratori definiscono e gestiscono le soglie di spedizione gratuita in base ai paesi dei clienti.
    -   `smartfreeshippingpro/views/templates/admin/group-rules-picker.tpl`
        -   **Descrizione:** Un sotto-template per l'interfaccia in cui gli amministratori definiscono e gestiscono le soglie di spedizione gratuita in base ai gruppi di clienti.
    -   `smartfreeshippingpro/views/templates/admin/visual-designer.tpl`
        -   **Descrizione:** Un sotto-template per l'interfaccia del designer visivo, contenente la struttura HTML per la barra di anteprima e i campi di input (selettori di colore, slider, campi di testo) per la personalizzazione.
-   **Template di hook (`views/templates/hook/`)**:

    -   `smartfreeshippingpro/views/templates/hook/progress.tpl`
        -   **Descrizione:** Questo è il template front-office principale. Contiene la struttura HTML per la barra di avanzamento della spedizione gratuita stessa (ad esempio, un `div` per la barra, un `div` per il riempimento dell'avanzamento e uno `span` per il messaggio dinamico).
        -   **Renderizzato negli hook:** Questo template viene renderizzato in vari hook front-office come `displayHeader`, `displayFooter`, `displayProductButtons`, `displayShoppingCart`, `displayLeftColumn`, `displayRightColumn`, a seconda della configurazione del commerciante.
        -   **Output del blocco visivo:** Emette la barra di avanzamento completa e stilizzata con il suo messaggio dinamico.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non sembra creare tabelle SQL personalizzate in base all'inventario.
    -   I record di configurazione sono memorizzati nella tabella `ps_configuration` di PrestaShop. Le chiavi seguirebbero tipicamente un modello come `SMARTFREESHIPPINGPRO_ENABLED`, `SMARTFREESHIPPINGPRO_THRESHOLD_DEFAULT`, `SMARTFREESHIPPINGPRO_COLOR_BAR`, `SMARTFREESHIPPINGPRO_MESSAGE_NOT_QUALIFIED`, ecc.
    -   Le regole specifiche per paese e gruppo potrebbero essere memorizzate come array serializzati all'interno di una singola voce `ps_configuration` o potenzialmente in una semplice tabella personalizzata se la struttura è complessa, sebbene l'inventario suggerisca che `ObjectModel` non sia utilizzato.
-   **Tabella degli hook registrati**:

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` o all'inizio del `<body>`. | Inietta risorse CSS/JS e/o l'HTML della barra di avanzamento (specialmente per le barre fisse). |
| `displayFooter` | Renderizza nella parte inferiore del `<body>` prima del tag di chiusura. | Inietta risorse CSS/JS e/o l'HTML della barra di avanzamento. |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra del negozio. | Visualizza la barra di avanzamento nella colonna sinistra. |
| `displayRightColumn` | Renderizza il contenuto nella barra laterale destra del negozio. | Visualizza la barra di avanzamento nella colonna destra. |
| `displayProductButtons` | Renderizza vicino al pulsante "Aggiungi al carrello" nelle pagine dei prodotti. | Visualizza la barra di avanzamento direttamente nelle pagine dei prodotti. |
| `displayShoppingCart` | Renderizza nella pagina di riepilogo del carrello. | Visualizza la barra di avanzamento nella pagina del carrello per incoraggiare più acquisti. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller frontale imposta i suoi media (CSS/JS). | Inietta file CSS e JavaScript specifici per il front-office. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin imposta i suoi media (CSS/JS). | Inietta file CSS e JavaScript specifici per il back-office per la pagina di configurazione. |
| `actionCartSave` | Eseguito dopo il salvataggio di un carrello (ad esempio, articolo aggiunto/rimosso). | Attiva il JS del front-office per aggiornare la barra di avanzamento tramite AJAX. |
| `actionObjectCartUpdateAfter` | Eseguito dopo l'aggiornamento di un oggetto carrello. | Simile a `actionCartSave`, utilizzato per attivare gli aggiornamenti. |
| `actionObjectOrderAddAfter` | Eseguito dopo l'aggiunta di un nuovo ordine. | Potenzialmente utilizzato per l'analisi A/B testing per tracciare le conversioni. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il tuo modulo Free Shipping Progress Bar Pro, fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team è dedicato a garantire che il tuo modulo funzioni senza intoppi ed efficacemente.

-   **Accedi agli aggiornamenti:** Accedi al tuo account MyPresta.eu e vai alla sezione della cronologia degli ordini e dei download per ottenere la versione più recente del modulo.
-   **Supporto tecnico:** Se riscontri problemi, hai domande o hai bisogno di assistenza con la configurazione, apri un ticket di supporto tramite il tuo account cliente MyPresta.eu. Il nostro team di esperti sarà lieto di aiutarti.
