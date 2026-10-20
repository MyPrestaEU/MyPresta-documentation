---
title: "Punti fedeltà - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Punti fedeltà di MyPresta.eu."
sidebar:
  label: "Punti fedeltà - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Loyalty points su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/loyalty-points/)
>
> ---


# Punti fedeltà

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alla configurazione del modulo, vai su **Moduli > Gestione moduli** nel tuo back office di PrestaShop, cerca "Punti fedeltà" e clicca sul pulsante "Configura".

Questa schermata ti consente di definire le regole fondamentali del tuo programma di fidelizzazione.

#### **Tasso di cambio punti fedeltà**

-   **Cosa fa questa impostazione:** Questa impostazione cruciale definisce quanti punti fedeltà un cliente guadagna per un importo specifico di denaro speso nel tuo negozio. È la base del tuo programma di fidelizzazione.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "1 punto per ogni €10 spesi":* Un cliente che spende €50 guadagnerà 5 punti.
    -   *Se impostato su "1 punto per ogni €5 spesi":* Un cliente che spende €50 guadagnerà 10 punti.
    -   Un valore più alto (es. €10) significa che i clienti guadagnano punti più lentamente, mentre un valore più basso (es. €1) significa che guadagnano punti più velocemente.
-   **Valore consigliato:** Questo dipende dai tuoi margini di profitto e dall'incentivo desiderato per il cliente. Un punto di partenza comune è "1 punto per ogni €10 spesi" o "1 punto per ogni €5 spesi".
-   **Scenario / esempio per il commerciante:** Se il tuo valore medio dell'ordine è di €50 e vuoi che i clienti si sentano rapidamente ricompensati, "1 punto per ogni €5 spesi" potrebbe essere migliore. Se i tuoi margini sono più stretti, "1 punto per ogni €10 spesi" potrebbe essere più sostenibile.

#### **Valore dei punti fedeltà**

-   **Cosa fa questa impostazione:** Questa impostazione determina il valore monetario di ogni punto fedeltà quando un cliente decide di convertirli in un buono sconto.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "1 punto = €0.10":* Un cliente con 100 punti può ottenere un buono da €10.
    -   *Se impostato su "1 punto = €0.05":* Un cliente con 100 punti può ottenere un buono da €5.
    -   Un valore più alto rende i punti più attraenti e preziosi per il cliente, ma costa di più al tuo negozio in sconti.
-   **Valore consigliato:** Questo dovrebbe essere bilanciato con il "Tasso di cambio punti fedeltà" per garantire che il tuo programma sia sia attraente per i clienti che finanziariamente sostenibile per la tua attività. Un rapporto comune è che 10 punti (guadagnati spendendo €100 se il tasso è 1 punto per ogni €10) valgono €1.
-   **Scenario / esempio per il commerciante:** Se dai 1 punto per ogni €10 spesi, e 1 punto vale €0.10, allora un cliente che spende €100 ottiene 10 punti, che possono essere scambiati con un buono da €1. Questo significa che ottiene un 1% di sconto sui suoi acquisti. Potresti aumentarlo al 2% o 3% per essere più competitivo.

#### **Punti minimi per la conversione**

-   **Cosa fa questa impostazione:** Questo imposta il numero minimo di punti fedeltà che un cliente deve accumulare prima di poterli convertire in un buono sconto.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "50 punti":* I clienti non possono riscattare i punti finché non ne hanno almeno 50.
    -   *Se impostato su "10 punti":* I clienti possono riscattare i punti molto prima.
    -   Un minimo più alto incoraggia i clienti a fare più acquisti per raggiungere la soglia, aumentando potenzialmente il loro valore a vita. Un minimo più basso offre una gratificazione più rapida.
-   **Valore consigliato:** Imposta un valore che incoraggi gli acquisti ripetuti senza essere così alto da far sentire ai clienti che è irraggiungibile. 50-100 punti è un buon intervallo di partenza, a seconda del tuo tasso di guadagno punti.
-   **Scenario / esempio per il commerciante:** Se si guadagna 1 punto per ogni €10, e sono necessari 50 punti, un cliente deve spendere €500 per ottenere il suo primo buono. Questo assicura che sia un cliente fedele prima di ricevere uno sconto significativo.

#### **Validità del buono (giorni)**

-   **Cosa fa questa impostazione:** Questo definisce per quanti giorni sarà valido un buono sconto generato dai punti fedeltà.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "30 giorni":* Il buono scade 30 giorni dopo essere stato generato.
    -   *Se impostato su "365 giorni":* Il buono è valido per un anno intero.
    -   Un periodo di validità più breve incoraggia i clienti a utilizzare il loro buono prima, stimolando acquisti ripetuti più rapidi. Un periodo più lungo offre maggiore flessibilità ma potrebbe ritardare gli acquisti.
-   **Valore consigliato:** Da 30 a 90 giorni è un intervallo comune. Questo crea un senso di urgenza senza essere eccessivamente restrittivo.
-   **Scenario / esempio per il commerciante:** Un periodo di validità di 60 giorni offre ai clienti abbastanza tempo per trovare qualcosa che vogliono acquistare senza lasciare il buono inutilizzato indefinitamente.

#### **Abilita programma fedeltà**

-   **Cosa fa questa impostazione:** Questo è un interruttore principale per attivare o disattivare l'intero programma di punti fedeltà.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il programma di fidelizzazione è attivo. I clienti guadagneranno punti, vedranno le informazioni sui punti sulle pagine dei prodotti e nel loro carrello, e potranno gestire i punti nel loro account.
    -   *Quando disabilitato (NO):* Il programma di fidelizzazione è inattivo. Non verranno guadagnati punti, non verranno visualizzate informazioni sui punti e i clienti non potranno riscattare i punti. I punti esistenti verranno mantenuti ma inaccessibili fino alla riabilitazione.
-   **Valore consigliato:** SÌ, una volta configurate tutte le altre impostazioni.
-   **Scenario / esempio per il commerciante:** Potresti disabilitarlo temporaneamente per manutenzione o se stai eseguendo una diversa campagna promozionale che è in conflitto con il programma di fidelizzazione.

#### **Visualizza punti fedeltà sulla pagina del prodotto**

-   **Cosa fa questa impostazione:** Questo controlla se le informazioni sui punti fedeltà guadagnati per un prodotto vengono mostrate sulle singole pagine dei prodotti nel tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* I clienti vedranno un testo come "Guadagna X punti con questo acquisto" su ogni pagina del prodotto.
    -   *Quando disabilitato (NO):* Questa informazione non apparirà sulle pagine dei prodotti.
-   **Valore consigliato:** SÌ. Visualizzare queste informazioni in modo prominente aiuta i clienti a comprendere la proposta di valore del tuo programma di fidelizzazione e incoraggia gli acquisti.
-   **Scenario / esempio per il commerciante:** Mantenere questa opzione abilitata assicura che i clienti siano sempre consapevoli delle ricompense che possono guadagnare, il che può essere un fattore decisivo nel loro acquisto.

#### **Visualizza punti fedeltà nel carrello**

-   **Cosa fa questa impostazione:** Questo controlla se i punti fedeltà totali da guadagnare per l'ordine corrente vengono visualizzati nel riepilogo del carrello.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* I clienti vedranno un riepilogo dei punti che guadagneranno per il contenuto del loro carrello attuale.
    -   *Quando disabilitato (NO):* Questa informazione non apparirà nel carrello.
-   **Valore consigliato:** SÌ. Questo serve come incentivo finale prima del checkout, ricordando ai clienti i futuri benefici del loro acquisto.
-   **Scenario / esempio per il commerciante:** La visualizzazione dei punti nel carrello può ridurre l'abbandono aggiungendo un ulteriore livello di valore all'acquisto, specialmente se il cliente è indeciso.

#### **Descrizione del programma punti fedeltà**

-   **Cosa fa questa impostazione:** Questo ti consente di fornire una descrizione o una spiegazione personalizzata del tuo programma di fidelizzazione. Questo testo verrà tipicamente visualizzato nella sezione "Il mio account" del cliente dove gestisce i suoi punti.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando compilato con testo:* I clienti vedranno il tuo messaggio personalizzato che spiega come funziona il programma, i suoi vantaggi o eventuali regole specifiche.
    -   *Quando lasciato vuoto:* Non verrà mostrata alcuna descrizione personalizzata, lasciando potenzialmente i clienti con meno informazioni.
-   **Valore consigliato:** Fornisci una descrizione chiara, concisa e coinvolgente. Spiega come si guadagnano i punti, il loro valore e come riscattarli.
-   **Scenario / esempio per il commerciante:** "Guadagna 1 punto per ogni €10 spesi! Raccogli 50 punti e ottieni un buono da €5 per il tuo prossimo acquisto. È il nostro modo di ringraziarti per essere un cliente fedele!"

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Tasso di cambio punti fedeltà | 1 punto per ogni €10 spesi | Definisce quanti punti vengono guadagnati per unità di valuta spesa. |
| Configurazione modulo | Valore dei punti fedeltà | 1 punto = €0.10 | Definisce il valore monetario di ogni punto quando convertito in un buono. |
| Configurazione modulo | Punti minimi per la conversione | 50 punti | Imposta i punti minimi richiesti prima che un cliente possa riscattarli per un buono. |
| Configurazione modulo | Validità del buono (giorni) | 60 giorni | Per quanto tempo è valido un buono generato. |
| Configurazione modulo | Abilita programma fedeltà | SÌ | Interruttore principale per attivare/disattivare l'intero programma fedeltà. |
| Configurazione modulo | Visualizza punti fedeltà sulla pagina del prodotto | SÌ | Mostra le informazioni sui punti guadagnati sulle singole pagine dei prodotti. |
| Configurazione modulo | Visualizza punti fedeltà nel carrello | SÌ | Mostra i punti totali da guadagnare nel riepilogo del carrello. |
| Configurazione modulo | Descrizione del programma punti fedeltà | Testo personalizzato | Fornisce una spiegazione dettagliata del programma ai clienti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non vedono le informazioni sui punti fedeltà sulle pagine dei prodotti o nel carrello. Cosa c'è che non va?**
R:

1.  **Controlla "Abilita programma fedeltà":** Assicurati che questa impostazione sia impostata su SÌ nella configurazione del modulo.
2.  **Controlla le impostazioni di visualizzazione:** Verifica che "Visualizza punti fedeltà sulla pagina del prodotto" e "Visualizza punti fedeltà nel carrello" siano entrambi impostati su SÌ.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo back office di PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, le modifiche non appaiono finché la cache non viene aggiornata.
4.  **Compatibilità del tema:** Sebbene il modulo sia progettato per la compatibilità, i temi personalizzati a volte potrebbero sovrascrivere i hook di visualizzazione predefiniti. Se svuotare la cache non funziona, contatta il supporto MyPresta.eu.

**D: I clienti stanno guadagnando punti, ma non riescono a convertirli in buoni.**
R:

1.  **Controlla "Punti minimi per la conversione":** Assicurati che il cliente abbia accumulato almeno il numero di punti specificato in questa impostazione. Se il minimo è 50 e ne ha solo 45, non vedrà l'opzione di conversione.
2.  **Processo di generazione del buono:** Guida i tuoi clienti alla sezione "Il mio account", quindi alla sezione "I miei punti fedeltà" (o simile), dove dovrebbero trovare un'opzione per convertire i loro punti in un buono.

**D: Un cliente ha generato un buono, ma non funziona o è scomparso.**
R:

1.  **Controlla "Validità del buono (giorni)":** Il buono potrebbe essere scaduto se il cliente ha aspettato troppo a lungo per usarlo.
2.  **Codice del buono:** Assicurati che il cliente stia inserendo correttamente il codice del buono durante il checkout.
3.  **Stato del buono:** Nel back office di PrestaShop, vai su **Catalogo > Sconti > Regole carrello**. Cerca il codice del buono generato. Controlla le sue date di validità, l'importo minimo e se è già stato utilizzato.

**D: Posso aggiungere o rimuovere manualmente punti fedeltà per un cliente?**
R: La versione attuale del modulo non fornisce un'interfaccia diretta nel back office per regolare manualmente i punti fedeltà del cliente. I punti vengono calcolati automaticamente in base agli ordini. Se hai bisogno di effettuare regolazioni manuali, potresti dover considerare uno sviluppo personalizzato o contattare il supporto MyPresta.eu per opzioni avanzate.

**D: La descrizione del programma di fidelizzazione non viene visualizzata correttamente in più lingue.**
R: Quando imposti la "Descrizione del programma punti fedeltà", assicurati di utilizzare il selettore della lingua in alto a destra del campo di testo per fornire le traduzioni per tutte le lingue abilitate nel tuo negozio. Se inserisci il testo solo in una lingua, apparirà solo in quella lingua.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Loyalty points` (`myprestaloyalty`) segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale e configurazione. Si integra nel front office tramite vari hook per visualizzare le informazioni sulla fedeltà e fornisce una pagina dedicata all'account cliente per la gestione dei punti. Il modulo non introduce tabelle di database personalizzate o classi `ObjectModel`, basandosi sulla `Configuration` di PrestaShop per le impostazioni ed estendendo potenzialmente i dati esistenti di clienti o ordini tramite hook.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `myprestaloyalty/controllers/front/default.php`
        -   **Nome classe e classe padre**: `MyPrestaLoyaltyDefaultModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller funge probabilmente da fallback o da punto di ingresso generico per le azioni del front-office relative al modulo. Potrebbe gestire le richieste iniziali o i reindirizzamenti se un controller più specifico non viene trovato. Dato il controller `index.php`, `default.php` potrebbe essere meno critico o servire a uno scopo specifico e meno comune.
    -   `myprestaloyalty/controllers/front/index.php`
        -   **Nome classe e classe padre**: `MyPrestaLoyaltyIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo è il controller principale del front-office per il modulo. È responsabile della visualizzazione delle informazioni sui punti fedeltà del cliente e della gestione della logica per la conversione dei punti in buoni. Probabilmente recupera i punti attuali del cliente, calcola i potenziali valori dei buoni e elabora la richiesta di generazione del buono. Renderizza il template `loyalty.tpl`.
-   **Controller Admin Back-Office**: Nessuno identificato. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

Nessuna classe o modello personalizzato (estensioni `ObjectModel`) è stato identificato nell'inventario del modulo fornito. Il modulo probabilmente gestisce la logica dei punti fedeltà direttamente all'interno del file principale `myprestaloyalty.php` e tramite la `Configuration` di PrestaShop per le impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

-   `myprestaloyalty/views/js/admin_manual_customer_search.js`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Questo script suggerisce la funzionalità per la ricerca manuale dei clienti all'interno del pannello di amministrazione. Sebbene non siano stati esplicitamente elencati controller di amministrazione, questo file JS implica che potrebbe esserci un'interfaccia di amministrazione (forse integrata in una pagina PrestaShop esistente o in un modulo personalizzato all'interno di `getContent()`) dove un amministratore può cercare i clienti, possibilmente per visualizzare o gestire i loro punti fedeltà (sebbene la modifica diretta dei punti non sia confermata dalla descrizione del modulo). Probabilmente utilizza AJAX per recuperare i dati dei clienti.
-   `myprestaloyalty/views/js/myprestaloyalty.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Questo è il JavaScript principale del front-office per il modulo. Probabilmente gestisce le interazioni dinamiche sulla pagina di fidelizzazione del cliente (`loyalty.tpl`), come:
        -   Visualizzazione dei punti attuali e dei potenziali valori dei buoni.
        -   Gestione dell'evento click per il pulsante "Converti punti in buono".
        -   Effettuazione di richieste AJAX al controller frontale `index.php` per elaborare la generazione del buono.
        -   Aggiornamento dell'interfaccia utente per mostrare il codice del buono appena generato o messaggi di successo/errore.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `myprestaloyalty/views/css/myprestaloyalty.css`
    -   **Ambito**: Front-office (e potenzialmente alcuni elementi del back-office se vengono utilizzati stili comuni).
    -   **Descrizione**: Questo foglio di stile fornisce lo stile visivo per i componenti del front-office del modulo. Questo include:
        -   La visualizzazione dei punti fedeltà sulle pagine dei prodotti.
        -   Il riepilogo dei punti nel carrello.
        -   Il layout e lo stile della sezione "I miei punti fedeltà" nell'account del cliente, inclusi il saldo dei punti, la cronologia e il modulo di generazione dei buoni.
        -   Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema: Cerca classi con prefisso `myprestaloyalty-` o simili, come `.myprestaloyalty-product-points`, `.myprestaloyalty-cart-summary`, `.myprestaloyalty-account-section`, `.myprestaloyalty-voucher-form`, ecc.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:

    -   `myprestaloyalty/views/templates/admin/advert.tpl`
        -   **Descrizione**: Questo template è probabilmente utilizzato per visualizzare contenuti promozionali o pubblicità da MyPresta.eu all'interno della pagina di configurazione del modulo nel back office. È una pratica comune per gli sviluppatori di moduli includere tali elementi.
    -   `myprestaloyalty/views/templates/admin/_configure/helpers/form/form.tpl`
        -   **Descrizione**: Questo template è un template helper standard di PrestaShop utilizzato per il rendering del modulo di configurazione del modulo. Non è unico per questo modulo ma è incluso per garantire che la pagina di configurazione (`getContent()`) venga renderizzata correttamente, potenzialmente con campi personalizzati o stili specifici.
-   **Template Front-office (`views/templates/front/`)**:

    -   `myprestaloyalty/views/templates/front/loyalty.tpl`
        -   **Descrizione**: Questo è il template principale per la pagina dedicata "I miei punti fedeltà" del cliente, renderizzata da `MyPrestaLoyaltyIndexModuleFrontController`. Visualizza il saldo attuale dei punti del cliente, la cronologia dei punti guadagnati e spesi e l'interfaccia per convertire i punti in buoni sconto.
-   **Template Hook (`views/templates/hook/`)**:

    -   `myprestaloyalty/views/templates/hook/my-account.tpl`
        -   **Hook**: `displayCustomerAccount` (o simile, es. `displayMyAccountBlock`).
        -   **Descrizione**: Questo template aggiunge un link o un blocco alla pagina "Il mio account" del cliente, indirizzandolo alla pagina dedicata ai punti fedeltà del modulo (`loyalty.tpl`).
    -   `myprestaloyalty/views/templates/hook/product.tpl`
        -   **Hook**: `displayProductExtraContent`, `displayProductButtons` o `displayProductActions` (a seconda della versione e del tema di PrestaShop).
        -   **Descrizione**: Questo template visualizza le informazioni su quanti punti fedeltà un cliente guadagnerà acquistando il prodotto specifico sulla sua pagina prodotto.
    -   `myprestaloyalty/views/templates/hook/shopping-cart.tpl`
        -   **Hook**: `displayShoppingCartFooter`, `displayCartExtraProductActions` o `displayReassurance` (a seconda della versione e del tema di PrestaShop).
        -   **Descrizione**: Questo template visualizza un riepilogo dei punti fedeltà totali che il cliente guadagnerà per gli articoli attualmente nel suo carrello.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Nessuna tabella SQL personalizzata viene creata da questo modulo. Tutte le impostazioni del modulo sono memorizzate nella tabella `ps_configuration` di PrestaShop, tipicamente con chiavi prefissate da `MYPRESTALOYALTY_`.

    -   Esempio di chiavi di configurazione: `MYPRESTALOYALTY_EXCHANGE_RATE`, `MYPRESTALOYALTY_POINT_VALUE`, `MYPRESTALOYALTY_MIN_POINTS`, `MYPRESTALOYALTY_VOUCHER_VALIDITY`, `MYPRESTALOYALTY_ENABLED`, `MYPRESTALOYALTY_DISPLAY_PRODUCT`, `MYPRESTALOYALTY_DISPLAY_CART`, `MYPRESTALOYALTY_DESCRIPTION`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Per includere risorse CSS e JS per il front-office. |
| `displayCustomerAccount` | Sulla pagina "Il mio account" del cliente. | Per aggiungere un link alla sezione "I miei punti fedeltà". |
| `displayProductExtraContent` (o simile) | Sulla pagina del prodotto, vicino ai dettagli/pulsanti del prodotto. | Per mostrare i punti guadagnati per il prodotto specifico. |
| `displayShoppingCartFooter` (o simile) | Nel riepilogo del carrello. | Per mostrare i punti totali guadagnati per l'ordine corrente. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Per calcolare e assegnare punti fedeltà al cliente in base al totale dell'ordine. |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` (opzionale) | Nelle rispettive aree della colonna/piè di pagina. | Potenzialmente utilizzato per visualizzare un link rapido o un riepilogo del programma di fidelizzazione, se configurato. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto tecnico dedicato per il modulo "Punti fedeltà", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
