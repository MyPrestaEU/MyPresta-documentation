---
title: "Valore minimo ordine per fornitore - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Valore minimo ordine per fornitore di MyPresta.eu."
sidebar:
  label: "Valore minimo ordine per fornitore - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Minimal order value by supplier su MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-supplier.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/minimal-order-value-by-supplier/)
>
> ---


# Valore minimo ordine per fornitore

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" si accede alla pagina principale di configurazione del modulo. Qui puoi abilitare o disabilitare il modulo e accedere alla schermata di gestione principale per i tuoi minimi per fornitore.

-   **Cosa fa questa impostazione:** Questa schermata funge da hub centrale per il modulo. Ti consente di abilitare o disabilitare l'intera funzionalità del modulo e fornisce un collegamento diretto per gestire i tuoi valori minimi d'ordine per i fornitori.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando abilitato:* Il modulo controllerà attivamente i carrelli dei clienti rispetto ai valori minimi d'ordine del fornitore definiti e bloccherà il checkout se i requisiti non sono soddisfatti.
    *   *Quando disabilitato:* Il modulo cesserà di funzionare. Non verranno eseguiti controlli sul valore minimo d'ordine e i clienti potranno effettuare il checkout indipendentemente dai totali d'ordine del fornitore.
-   **Valore consigliato:** "SÌ" (Abilitato) se intendi utilizzare le funzionalità del modulo.
-   **Scenario / esempio del commerciante:** Se stai configurando il modulo per la prima volta, lo abiliterai qui. Se hai bisogno di sospendere temporaneamente le regole (ad esempio, durante una promozione a livello di negozio in cui desideri consentire tutti gli ordini), puoi disabilitarlo qui.

Su questa schermata, troverai anche un pulsante o un link per **"Gestisci valori minimi d'ordine per fornitore"**. Cliccandoci sopra si accederà alla schermata di amministrazione dedicata dove definisci le regole effettive.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminMobsController (Back Office > Moduli > Valore minimo ordine per fornitore > Gestisci valori minimi d'ordine)

Questa è la schermata principale in cui definisci e gestisci i valori minimi d'ordine per ciascuno dei tuoi fornitori.

-   **Nome schermata e posizione menu:** Accedi a questa schermata navigando su **Moduli > Gestione moduli**, trovando "Valore minimo ordine per fornitore", cliccando su "Configura" e quindi cliccando sul pulsante/link "Gestisci valori minimi d'ordine per fornitore".
-   **Azioni e impostazioni disponibili:**
    *   **Tabella di elenco:** Questa schermata visualizza una tabella di tutti i valori minimi d'ordine attualmente configurati. Ogni riga tipicamente mostra:
        *   **Nome fornitore:** Il nome del fornitore a cui si applica la regola.
        *   **Valore minimo d'ordine:** L'importo monetario che i prodotti di questo fornitore devono raggiungere nel carrello.
        *   **Azioni:** Solitamente pulsanti "Modifica" ed "Elimina" per modificare o rimuovere una regola esistente.
    *   **Pulsante Aggiungi nuova regola:** Un pulsante (ad esempio, "Aggiungi nuovo valore minimo d'ordine") per creare una nuova regola.
    *   **Modulo Aggiungi/Modifica:** Quando aggiungi una nuova regola o ne modifichi una esistente, vedrai tipicamente un modulo con i seguenti campi:
        *   **Selezione fornitore:** Un menu a discesa o un campo di ricerca per selezionare uno dei tuoi fornitori esistenti.
        *   **Valore minimo:** Un campo di input in cui inserisci l'importo numerico minimo d'ordine richiesto per i prodotti del fornitore selezionato. Questo valore sarà nella valuta predefinita del tuo negozio (ad esempio, EUR, USD).
        *   **Pulsante Salva:** Per applicare le modifiche.
-   **Effetto delle modifiche:**
    *   *Aggiunta di una regola:* Una volta salvata, il nuovo valore minimo d'ordine per il fornitore selezionato diventa immediatamente attivo. I clienti saranno tenuti a soddisfare questo valore per i prodotti di quel fornitore.
    *   *Modifica di una regola:* La modifica del valore minimo o la modifica del fornitore per una regola esistente aggiorna il requisito attivo.
    *   *Eliminazione di una regola:* Rimuove il requisito del valore minimo d'ordine per quel fornitore specifico. I clienti non saranno più limitati da un acquisto minimo da quel fornitore.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Identifica i fornitori:** Determina quali fornitori richiedono valori minimi d'ordine in base alle tue esigenze aziendali (ad esempio, costi di spedizione elevati, accordi di dropshipping).
    2.  **Aggiungi regole:** Per ogni fornitore identificato, clicca su "Aggiungi nuovo valore minimo d'ordine", seleziona il fornitore, inserisci l'importo minimo e salva.
    3.  **Monitora e regola:** Rivedi regolarmente i tuoi accordi con i fornitori e i dati di vendita. Se un fornitore modifica i suoi termini, o se noti una tendenza di ordini piccoli non redditizi, torna a questa schermata per regolare o aggiungere nuove regole.
    4.  **Testa:** Dopo aver aggiunto o modificato le regole, testa sempre la funzionalità aggiungendo prodotti dai fornitori interessati al tuo carrello nel front office e tentando di effettuare il checkout.

#### index.php (mobs/controllers/admin/index.php)

Questo file funge tipicamente da segnaposto o da reindirizzamento all'interno della directory dei controller admin e non presenta una schermata di configurazione diretta al commerciante. La sua funzione principale è solitamente quella di garantire che l'accesso diretto alla directory sia gestito con grazia, spesso reindirizzando alla configurazione principale del modulo o a una pagina di errore. I commercianti non interagiranno direttamente con questo file.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Abilita/Disabilita Modulo | Abilitato | Controlla se la funzionalità del modulo (controlli del valore minimo d'ordine) è attiva o inattiva. |
| **AdminMobsController** | Aggiungi nuova regola (Fornitore) | N/A | Seleziona un fornitore a cui applicare una regola di valore minimo d'ordine. |
| **AdminMobsController** | Aggiungi nuova regola (Valore minimo) | N/A | Imposta la soglia monetaria per i prodotti del fornitore selezionato. |
| **AdminMobsController** | Modifica regola (Fornitore) | N/A | Modifica il fornitore associato a una regola esistente. |
| **AdminMobsController** | Modifica regola (Valore minimo) | N/A | Modifica la soglia monetaria per una regola di fornitore esistente. |
| **AdminMobsController** | Elimina regola | N/A | Rimuove un requisito di valore minimo d'ordine per un fornitore specifico. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato un valore minimo, ma non funziona nel carrello. Cosa devo controllare?**
R1:

1.  **Il modulo è abilitato?** Vai su **Moduli > Gestione moduli**, trova "Valore minimo ordine per fornitore" e assicurati che sia abilitato.
2.  **La regola è configurata correttamente?** Vai alla schermata "Gestisci valori minimi d'ordine per fornitore" e verifica che il fornitore sia selezionato correttamente e che il valore minimo sia inserito come numero (senza simboli di valuta).
3.  **I prodotti sono assegnati correttamente al fornitore?** Ricontrolla i prodotti nel carrello del cliente per assicurarti che siano effettivamente associati al fornitore per il quale hai impostato la regola.
4.  **Svuota la cache:** A volte, la cache di PrestaShop può impedire che le modifiche appaiano immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".

**D2: Il messaggio di notifica viene visualizzato, ma non è nella lingua del mio negozio.**
R2: I messaggi front-office del modulo sono traducibili.

1.  Vai su **Internazionale > Traduzioni**.
2.  Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, seleziona la tua lingua e clicca su "Modifica".
3.  Trova il modulo "mobs" (Valore minimo ordine per fornitore) e traduci le stringhe pertinenti. Salva le modifiche.

**D3: Il modulo blocca il checkout, ma voglio consentire un'eccezione per un cliente o un ordine specifico.**
R3: Il modulo applica le regole a livello globale. Per fare un'eccezione, dovresti disabilitare temporaneamente la regola del fornitore specifico nella configurazione del modulo (**Moduli > Valore minimo ordine per fornitore > Gestisci valori minimi d'ordine**) o disabilitare l'intero modulo se sono attive più regole. Ricorda di riabilitarlo in seguito. Non esiste una funzione di "override" integrata per cliente o ordine.

**D4: Il modulo è attivo, ma lo stile del messaggio di notifica non corrisponde al mio tema.**
R4: Il modulo viene fornito con uno stile di base. Se si scontra con il tuo tema personalizzato, il tuo webmaster o sviluppatore può sovrascrivere il CSS del modulo. Il file CSS del modulo è `mobs/views/css/mobs.css`. Possono aggiungere stili personalizzati al file `custom.css` o `theme.css` del tuo tema, mirando agli elementi di notifica del modulo per abbinarli al tuo marchio.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Valore minimo ordine per fornitore" (`mobs`) segue un'architettura standard per i moduli PrestaShop, sfruttando i principi MVC. Consiste principalmente in una classe modulo principale, un controller Admin dedicato per la gestione delle regole e un controller Front per le interazioni AJAX e la visualizzazione delle notifiche. Non utilizza classi `ObjectModel` personalizzate ma memorizza la configurazione direttamente in `ps_configuration` e gestisce i minimi specifici del fornitore tramite l'`AdminMobsController` che probabilmente interagisce con una tabella personalizzata o estende un `AdminController` generico per gestire i dati. L'interazione front-office è gestita tramite un template dedicato per il carrello e un controller AJAX per i controlli dinamici.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nome classe e classe genitore**: `MobsAjaxModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è responsabile della gestione delle richieste AJAX dal front-office, tipicamente avviate dalla pagina del carrello. Probabilmente esegue controlli in tempo reale sul contenuto del carrello rispetto ai valori minimi d'ordine del fornitore configurati. Restituisce risposte JSON che indicano se i minimi sono soddisfatti e fornisce messaggi pertinenti in caso contrario. Ciò consente aggiornamenti dinamici alla visualizzazione del carrello senza ricaricare l'intera pagina.
    -   `controllers/front/index.php`
        -   **Nome classe e classe genitore**: `MobsIndexModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller potrebbe fungere da punto di ingresso predefinito per la parte front-office del modulo, sebbene la sua funzione principale sia spesso quella di reindirizzare o servire una pagina di base se il modulo non ha una pagina front-office dedicata. Data la funzionalità del modulo, è più probabile che il controller `ajax.php` gestisca la logica principale del front-office e `index.php` sia un fallback o una pagina minima.
-   **Controller Admin Back-Office**:

    -   `controllers/admin/AdminMobs.php`
        -   **Nome classe e classe genitore**: `AdminMobsController` estende `ModuleAdminController`.
        -   **Nome scheda ed entità gestita**: Questo controller gestisce le regole "Valori minimi d'ordine per fornitore". Fornisce l'interfaccia per elencare, aggiungere, modificare ed eliminare queste regole. Probabilmente interagisce con una tabella di database personalizzata (ad esempio, `ps_mobs_rules`) per memorizzare l'ID del fornitore e il valore minimo associato. La vista a griglia e i campi del modulo sono renderizzati utilizzando le classi `HelperList` e `HelperForm` di PrestaShop.
    -   `controllers/admin/index.php`
        -   **Nome classe e classe genitore**: Nessuna classe specifica, tipicamente un semplice file PHP.
        -   **Responsabilità**: Questo file è solitamente un segnaposto o una misura di sicurezza per prevenire l'elenco diretto delle directory. Spesso contiene un semplice `header('Location: ../../../index.php?controller=AdminHome');` o un reindirizzamento simile alla dashboard del back office di PrestaShop, garantendo che l'accesso diretto a `yourshop.com/modules/mobs/controllers/admin/` non esponga informazioni sensibili o causi errori. Non presenta una schermata rivolta all'utente.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo:

1.  Memorizza la sua configurazione direttamente in `ps_configuration` per impostazioni semplici.
2.  Gestisce i suoi dati (minimi del fornitore) direttamente all'interno dell'`AdminMobsController` utilizzando i metodi di query del database standard di PrestaShop, interagendo potenzialmente con una tabella personalizzata creata durante l'installazione, senza un `ObjectModel` dedicato.

Se viene utilizzata una tabella personalizzata, la sua struttura sarebbe definita nel metodo `install()` del file principale del modulo (`mobs/index.php`).

### 4.4 Risorse JavaScript (`views/js/`)

-   `views/js/mobs.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Questo file JavaScript è responsabile delle interazioni lato client relative ai controlli del valore minimo d'ordine. Probabilmente:
        -   Associa listener di eventi alle modifiche della quantità del carrello, alle rimozioni di prodotti o al pulsante "Procedi al checkout".
        -   Invia richieste AJAX a `controllers/front/ajax.php` per convalidare il carrello rispetto ai minimi del fornitore.
        -   Riceve risposte JSON dal controller AJAX.
        -   Aggiorna dinamicamente la visualizzazione del carrello, mostrando messaggi di notifica se i minimi non sono soddisfatti.
        -   Disabilita o abilita il pulsante "Procedi al checkout" in base ai risultati della convalida.
        -   Può includere logica per la visualizzazione di popup modali o messaggi di errore in linea.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `views/css/mobs.css`
    -   **Ambito**: Stile del cliente front-office.
    -   **Descrizione**: Questo foglio di stile fornisce la presentazione visiva per gli elementi front-office del modulo, principalmente i messaggi di notifica visualizzati nel carrello.
    -   **Componenti e contenitori UI principali che stilizza**: Probabilmente mirerà a classi CSS specifiche aggiunte dal modulo al template del carrello, come `div.mobs-notification`, `p.mobs-error-message`, o elementi simili che visualizzano gli avvisi sui valori minimi d'ordine non soddisfatti.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Gli sviluppatori possono ispezionare l'output HTML delle notifiche del modulo per identificare i nomi esatti delle classi (ad esempio, `.mobs-alert`, `.mobs-supplier-name`, `.mobs-required-value`) e sovrascriverli nel `custom.css` del loro tema per abbinarli al branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:

    -   Nessun template hook specifico è elencato nell'inventario, suggerendo che l'output front-office del modulo viene principalmente iniettato in un template esistente come `displayShoppingCart.tpl` o tramite un rendering diretto del template all'interno di un controller.
-   **Template admin (`views/templates/admin/`)**:

    -   Il dossier del modulo non elenca template admin specifici. L'`AdminMobsController` probabilmente utilizza i template `HelperList` e `HelperForm` predefiniti di PrestaShop per le sue viste a griglia e modulo, che fanno parte del framework core di PrestaShop.
-   **Template front-office (`views/templates/front/`)**:

    -   `views/templates/front/displayShoppingCart.tpl`
        -   **Descrizione**: Questo template è specificamente progettato per essere incluso o renderizzato all'interno della pagina del carrello. Contiene la struttura HTML per visualizzare le notifiche del valore minimo d'ordine al cliente. Probabilmente itererà su eventuali minimi del fornitore non soddisfatti e visualizzerà un messaggio per ciascuno, possibilmente includendo il nome del fornitore e l'importo rimanente necessario. Questo template viene aggiornato dinamicamente dallo script `mobs.js` in base alle risposte AJAX.

### 4.7 Schema del database e mappa dei hook

-   **Tabelle del database**:

    -   Il dossier del modulo non elenca esplicitamente classi personalizzate o file SQL, ma affinché l'`AdminMobsController` gestisca i "Valori minimi d'ordine per fornitore", deve memorizzare questi dati. È altamente probabile che il modulo crei una tabella personalizzata durante il suo metodo `install()` in `mobs/index.php`.
    -   **Nome tabella probabile**: `ps_mobs_rules` (o simile, ad esempio, `ps_minimal_order_by_supplier`).
    -   **Struttura tabella probabile**:
        -   `id_mobs_rule` (PRIMARY KEY, INT)
        -   `id_supplier` (INT, FOREIGN KEY a `ps_supplier.id_supplier`)
        -   `min_value` (DECIMAL(20,6))
        -   `date_add` (DATETIME)
        -   `date_upd` (DATETIME)
    -   **Record di configurazione**: Lo stato principale di abilitazione/disabilitazione del modulo è probabilmente memorizzato in `ps_configuration` con una chiave come `MOBS_ENABLED`.
-   **Tabella dei hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Per includere file CSS (`mobs.css`) e JavaScript (`mobs.js`) per la funzionalità front-office. |
| `displayShoppingCartFooter` | In fondo alla pagina del carrello. | Per visualizzare il template `displayShoppingCart.tpl`, che contiene i messaggi di notifica per i valori minimi d'ordine non soddisfatti. |
| `actionCartSave` | Dopo che un carrello viene salvato (ad esempio, modifica quantità, aggiunta/rimozione prodotto). | Per attivare la logica che controlla i valori minimi d'ordine e potenzialmente aggiorna lo stato del carrello o le variabili di sessione. |
| `actionValidateOrder` | Prima che un ordine venga ufficialmente convalidato. | Per eseguire un controllo finale sui valori minimi d'ordine e impedire la convalida dell'ordine se i requisiti non sono soddisfatti. |
| `displayBeforeCarrier` | Prima del passaggio di selezione del corriere nel checkout. | Per visualizzare avvisi o bloccare la progressione se i minimi non sono soddisfatti in una fase precedente del checkout. |
| `displayPaymentTop` | In cima alla pagina di selezione del pagamento. | Per visualizzare avvisi o bloccare la progressione se i minimi non sono soddisfatti prima del pagamento. |

*Nota: Il dossier del modulo menziona "Header, Columns, Product, or Footer" come hook front-office. Mentre `displayHeader` è certo, il modulo probabilmente utilizza `displayShoppingCartFooter` o un hook simile specifico per il carrello per il suo output principale, e `actionCartSave`/`actionValidateOrder` per la sua logica principale. `displayRightColumn` o `displayLeftColumn` potrebbero essere utilizzati per blocchi statici opzionali, ma sono meno probabili per la funzionalità principale.*

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo "Valore minimo ordine per fornitore", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
