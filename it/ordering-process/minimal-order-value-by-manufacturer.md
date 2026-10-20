---
title: "Valore minimo ordine per produttore - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Valore minimo ordine per produttore' di MyPresta.eu."
sidebar:
  label: "Valore minimo ordine per produttore - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Minimal order value by manufacturer su MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-manufacturer.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/minimal-order-value-by-manufacturer/)
>
> ---


# Valore minimo ordine per produttore

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo, accessibile direttamente dopo l'installazione o cliccando su "Configura" accanto al modulo in Gestione moduli.

-   **Cosa fa questa schermata:** Questa pagina ti consente di abilitare/disabilitare il modulo e gestire le impostazioni principali che controllano il suo comportamento.

#### Impostazioni e Opzioni

-   **Abilita / Disabilita Modulo:**

    -   **Cosa fa questa impostazione:** Questo è un interruttore globale per attivare o disattivare la funzionalità dell'intero modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo controllerà attivamente i valori minimi d'ordine per produttore nei carrelli dei clienti e applicherà restrizioni se le condizioni non sono soddisfatte.
        -   *Quando disabilitato:* Il modulo cesserà di funzionare. Non verranno eseguiti controlli sul valore minimo d'ordine e i clienti potranno ordinare qualsiasi importo da qualsiasi produttore.
    -   **Valore consigliato:** **SÌ** (per attivare la funzione principale del modulo).
    -   **Scenario / esempio del commerciante:** Se stai testando il modulo o desideri disabilitare temporaneamente tutte le regole di ordine minimo senza eliminarle, puoi disattivarlo.
-   **Visualizza messaggio nella pagina del carrello:**

    -   **Cosa fa questa impostazione:** Controlla se un messaggio di avviso viene mostrato al cliente nella pagina del carrello se il valore minimo d'ordine di un produttore non è soddisfatto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti vedranno un messaggio chiaro e informativo nella pagina del carrello, indicando quale minimo del produttore non è soddisfatto e quanto devono aggiungere.
        -   *Quando disabilitato:* Nessun messaggio apparirà nella pagina del carrello. La restrizione si applicherà comunque, ma il cliente potrebbe scoprirla solo più tardi durante il checkout, potenzialmente portando a frustrazione.
    -   **Valore consigliato:** **SÌ**.
    -   **Scenario / esempio del commerciante:** L'abilitazione di questa opzione offre una migliore esperienza utente, guidando i clienti a risolvere il problema in anticipo piuttosto che sorprenderli al checkout.
-   **Visualizza messaggio nella pagina di checkout:**

    -   **Cosa fa questa impostazione:** Controlla se un messaggio di avviso viene mostrato al cliente nella pagina di checkout se il valore minimo d'ordine di un produttore non è soddisfatto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti vedranno un messaggio nella pagina di checkout, impedendo loro di completare l'ordine fino a quando il minimo non sarà soddisfatto.
        -   *Quando disabilitato:* Il processo di checkout potrebbe semplicemente bloccarsi senza una chiara spiegazione, o il modulo potrebbe impedire la progressione senza un messaggio specifico, il che può confondere i clienti.
    -   **Valore consigliato:** **SÌ**.
    -   **Scenario / esempio del commerciante:** Questo è fondamentale per prevenire ordini che non soddisfano i tuoi criteri e per comunicare chiaramente il motivo al cliente.
-   **Messaggio da visualizzare (per le pagine del carrello e del checkout):**

    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il testo del messaggio di avviso visualizzato ai clienti quando un valore minimo d'ordine non è soddisfatto. Puoi usare segnaposto come `{manufacturer_name}` e `{missing_amount}`.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* Il messaggio personalizzato apparirà nel front office.
        -   *Quando lasciato predefinito:* Verrà utilizzato un messaggio standard.
    -   **Valore consigliato:** Personalizza per essere chiaro e utile. Esempio: "Per completare il tuo ordine, devi aggiungere {missing\_amount} in più dai prodotti di {manufacturer\_name}."
    -   **Scenario / esempio del commerciante:** Potresti voler rendere il messaggio più amichevole, includere una call to action o allinearlo al tono di voce del tuo brand.

### 2.2 Schermate di amministrazione dedicate: Regole del valore minimo d'ordine per produttore (Back Office > Catalogo > Valore minimo ordine per produttore)

Questa schermata è dove definisci e gestisci le effettive regole del valore minimo d'ordine per ciascun produttore.

-   **Nome schermata e posizione nel menu:** "Valore minimo ordine per produttore" sotto il menu **Catalogo**.
-   **Cosa fa questa schermata:** Questa è un'area di gestione dedicata per aggiungere, modificare ed eliminare regole per i valori minimi d'ordine per produttore. Presenta un elenco di tutte le regole attualmente configurate.

#### Azioni e Impostazioni disponibili

-   **Elenco delle regole:**

    -   **Cosa fa:** Visualizza una tabella di tutte le regole esistenti per il valore minimo d'ordine. Ogni riga mostra tipicamente il nome del produttore, il valore minimo impostato e le opzioni per modificare o eliminare la regola.
    -   **Effetto delle modifiche:** Questa tabella fornisce una panoramica di tutte le regole attive.
    -   **Flusso di lavoro consigliato:** Rivedi regolarmente questo elenco per assicurarti che le tue regole siano aggiornate con le tue esigenze aziendali.
-   **Pulsante "Aggiungi nuova regola":**

    -   **Cosa fa:** Cliccando su questo pulsante si accede a un modulo in cui è possibile creare una nuova regola per il valore minimo d'ordine.
    -   **Effetto delle modifiche:** Apre un nuovo modulo.
    -   **Flusso di lavoro consigliato:** Usalo quando devi impostare un nuovo minimo per un produttore non ancora presente nell'elenco.
-   **Pulsante "Modifica" (per ogni regola):**

    -   **Cosa fa:** Consente di modificare le impostazioni di una regola esistente.
    -   **Effetto delle modifiche:** Apre il modulo della regola con i dati precompilati, consentendo di modificare il produttore o il valore minimo.
    -   **Flusso di lavoro consigliato:** Usalo per regolare i minimi in base a nuovi accordi con i fornitori o strategie di vendita.
-   **Pulsante "Elimina" (per ogni regola):**

    -   **Cosa fa:** Rimuove una specifica regola del valore minimo d'ordine.
    -   **Effetto delle modifiche:** La regola viene immediatamente rimossa e il produttore associato non avrà più un requisito di valore minimo d'ordine.
    -   **Flusso di lavoro consigliato:** Usalo quando un produttore non richiede più un ordine minimo, o se stai dismettendo un marchio.

#### Modulo Aggiungi/Modifica Regola

Quando aggiungi una nuova regola o ne modifichi una esistente, vedrai tipicamente i seguenti campi:

-   **Produttore:**

    -   **Cosa fa questa impostazione:** Questo campo ti consente di selezionare il produttore specifico a cui si applicherà questa regola del valore minimo d'ordine. Di solito presenta una ricerca con completamento automatico per aiutarti a trovare facilmente i produttori.
    -   **Effetto della modifica di questa impostazione:** Collega la regola a un particolare produttore.
    -   **Valore consigliato:** Seleziona il produttore esatto a cui intendi applicare la regola.
    -   **Scenario / esempio del commerciante:** Potresti selezionare "Apple" per impostare un minimo per tutti i prodotti Apple, o "Samsung" per i prodotti Samsung.
-   **Valore minimo ordine:**

    -   **Cosa fa questa impostazione:** Qui inserisci il valore numerico (nella valuta predefinita del tuo negozio, ad esempio USD, EUR) che rappresenta l'importo totale minimo richiesto per i prodotti del produttore selezionato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un valore (ad esempio, 50.00):* I clienti devono avere almeno 50.00 di prodotti del produttore selezionato nel carrello per procedere.
        -   *Quando impostato su 0 o lasciato vuoto:* Questo disabilita efficacemente il minimo per quel produttore (anche se è meglio eliminare la regola se non è necessario un minimo).
    -   **Valore consigliato:** Un valore numerico positivo che riflette le tue esigenze aziendali.
    -   **Scenario / esempio del commerciante:** Se il tuo fornitore per "BrandX" ti richiede di ordinare almeno $100 di prodotti, imposteresti questo valore a "100.00" per "BrandX".

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita / Disabilita Modulo | SÌ | Interruttore globale per la funzionalità del modulo. |
| Configurazione Modulo | Visualizza messaggio nella pagina del carrello | SÌ | Mostra avviso nel carrello se il minimo non è soddisfatto. |
| Configurazione Modulo | Visualizza messaggio nella pagina di checkout | SÌ | Mostra avviso nel checkout se il minimo non è soddisfatto. |
| Configurazione Modulo | Messaggio da visualizzare | Personalizzabile | Personalizza il testo del messaggio di avviso. |
| AdminMobmController | Produttore (Aggiungi/Modifica Regola) | Seleziona dall'elenco | Collega la regola a un produttore specifico. |
| AdminMobmController | Valore minimo ordine (Aggiungi/Modifica Regola) | Valore numerico | Imposta il valore totale minimo per i prodotti del produttore selezionato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato un minimo, ma non funziona nel front office. Cosa devo controllare?**
R1:

-   **Il modulo è abilitato?** Vai su `Moduli > Gestione moduli` e assicurati che "Valore minimo ordine per produttore" sia attivo.
-   **La regola specifica è abilitata?** Controlla `Catalogo > Valore minimo ordine per produttore` per assicurarti che la regola per il produttore in questione sia configurata correttamente con un valore positivo.
-   **Svuota la cache:** Vai su `Parametri avanzati > Prestazioni` e clicca su "Svuota la cache" (per tutte le cache). A volte, la cache di PrestaShop può impedire che le modifiche appaiano immediatamente.
-   **Verifica la presenza di conflitti:** Disabilita temporaneamente altri moduli che modificano il carrello o il processo di checkout per vedere se c'è un conflitto.

**D2: Il messaggio nella pagina del carrello/checkout non viene visualizzato.**
R2:

-   **Controlla la configurazione del modulo:** Vai su `Moduli > Gestione moduli > Configura` per "Valore minimo ordine per produttore". Assicurati che "Visualizza messaggio nella pagina del carrello" e "Visualizza messaggio nella pagina di checkout" siano entrambi impostati su **SÌ**.
-   **Il minimo è effettivamente non raggiunto?** Ricontrolla che i prodotti nel carrello del produttore specifico siano effettivamente inferiori al minimo impostato.

**D3: Posso impostare minimi diversi per diversi gruppi di clienti?**
R3: Questo modulo, nella sua forma standard, applica un singolo valore minimo per produttore a tutti i clienti. Se hai bisogno di minimi specifici per gruppo di clienti, ciò richiederebbe uno sviluppo personalizzato o un modulo diverso.

**D4: Come gestisce il modulo i negozi multi-valuta?**
R4: Il modulo utilizza la valuta predefinita del tuo negozio (come definita in `Localizzazione > Valute` e `Localizzazione > Localizzazione`) per il "Valore minimo ordine" che imposti. Convertirà automaticamente il totale del carrello del cliente nella valuta predefinita per il confronto, garantendo la coerenza.

**D5: Il modulo sembra rallentare il mio sito. Cosa posso fare?**
R5:

-   **Svuota la cache:** Assicurati che tutte le cache vengano svuotate regolarmente (`Parametri avanzati > Prestazioni`).
-   **Risorse del server:** Controlla le risorse del tuo ambiente di hosting (CPU, RAM). Se il tuo negozio ha un numero molto elevato di produttori o prodotti, assicurati che il tuo server possa gestire il carico.
-   **Aggiornamenti del modulo:** Utilizza sempre l'ultima versione del modulo da MyPresta.eu, poiché gli aggiornamenti spesso includono miglioramenti delle prestazioni.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Valore minimo ordine per produttore" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo segue un modello MVC (Model-View-Controller) standard di PrestaShop. Estende principalmente `Module` per la sua funzionalità e configurazione principali, utilizza `AdminController` per la gestione delle regole nel back-office e `ModuleFrontController` per le interazioni AJAX nel front-office relative alla convalida del carrello. Non sembra utilizzare classi `ObjectModel` personalizzate, affidandosi invece a `Configuration` per le impostazioni generali e all'interazione diretta con il database (o potenzialmente una semplice struttura di array) per le regole specifiche del produttore. Gli hook sono ampiamente utilizzati per integrarsi nel flusso del carrello e del checkout.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/ajax.php`
    -   **Nome classe:** `MobmAjaxModuleFrontController` (probabilmente, basato sulla convenzione di denominazione dei file) che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller è probabilmente responsabile della gestione delle richieste AJAX dal front-office, in particolare quelle relative agli aggiornamenti del carrello o alla progressione del checkout. Riceverebbe i dati del carrello, eseguirebbe i controlli del valore minimo d'ordine e restituirebbe una risposta JSON indicando se le condizioni sono soddisfatte e quali messaggi dovrebbero essere visualizzati. Questo è cruciale per gli aggiornamenti dinamici senza ricaricamenti completi della pagina.
-   `controllers/front/index.php`
    -   **Nome classe:** `MobmIndexModuleFrontController` (probabilmente) che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo file potrebbe essere un segnaposto o utilizzato per una semplice pagina del front-office se il modulo ne avesse una. Dato lo scopo del modulo, è meno probabile che renderizzi una pagina completa e più probabile che sia un fallback o parte di una catena di reindirizzamento se `ajax.php` è il punto di interazione principale.

#### Controller Admin Back-Office

-   `controllers/admin/AdminMobm.php`
    -   **Nome classe:** `AdminMobmController` che estende `ModuleAdminController`.
    -   **Nome scheda:** "Valore minimo ordine per produttore" (sotto Catalogo).
    -   **Entità gestita:** Gestisce l'entità `mobm`, che rappresenta le singole regole del valore minimo d'ordine per i produttori.
    -   **Responsabilità:** Questo è il controller principale per la gestione dell'elenco delle regole del valore minimo d'ordine per produttore. Gestisce:
        -   Visualizzazione dell'elenco delle regole esistenti (utilizzando `renderList()`).
        -   Aggiunta di nuove regole (utilizzando `renderForm()` per il modulo di aggiunta).
        -   Modifica delle regole esistenti (utilizzando `renderForm()` per il modulo di modifica).
        -   Eliminazione delle regole.
        -   Validazione del modulo e salvataggio dei dati.
        -   Probabilmente interagisce con la tabella `ps_configuration` o una tabella personalizzata per memorizzare l'ID del produttore e il valore minimo associato.
-   `controllers/admin/index.php`
    -   **Nome classe:** `AdminMobmIndexModuleAdminController` (probabilmente) che estende `ModuleAdminController`.
    -   **Responsabilità:** Simile a `index.php` del front-office, questo potrebbe essere un segnaposto o un punto di ingresso predefinito. In PrestaShop, i file `index.php` nelle directory dei controller spesso fungono da misure di sicurezza di base (ad esempio, `die('Access Denied');`) o da semplice routing se non gestiti esplicitamente da un controller più specifico.

### 4.3 Classi e Modelli Core (`classes/`)

Il dossier del modulo indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo:

1.  Memorizza le sue regole del produttore direttamente nella tabella `ps_configuration` (ad esempio, come un array serializzato).
2.  Utilizza query dirette al database all'interno del file del modulo principale o del controller amministrativo per gestire una tabella personalizzata.
3.  Gestisce i dati come un semplice array all'interno del contesto del modulo senza un `ObjectModel` formale.

Dato che `AdminMobmController` gestisce un'entità `mobm`, è altamente probabile che una tabella personalizzata (ad esempio, `ps_mobm`) venga creata durante l'installazione e che `AdminMobmController` gestisca implicitamente le operazioni CRUD per questa tabella senza una classe `ObjectModel` dedicata in `classes/`. La `$definition` per questa entità verrebbe quindi definita direttamente all'interno di `AdminMobmController` o del file del modulo principale.

### 4.4 Risorse JavaScript (`views/js/`)

-   `mobm/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office (probabilmente per il modulo `AdminMobmController`).
    -   **Responsabilità:** Fornisce la funzionalità di completamento automatico per la selezione dei produttori nel modulo "Aggiungi/Modifica Regola". Ascolta l'input dell'utente in un campo di testo, invia richieste AJAX a un controller del back-office (ad esempio, `AdminManufacturers` o un metodo `AdminMobm` personalizzato) per recuperare i nomi dei produttori corrispondenti e visualizza i suggerimenti.
-   `mobm/views/js/mobm.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo è il JavaScript principale del front-office per il modulo. Probabilmente:
        -   Si lega agli eventi nella pagina del carrello (ad esempio, modifiche della quantità, rimozione/aggiunta di prodotti).
        -   Si lega agli eventi nella pagina di checkout (ad esempio, clic sui pulsanti "Procedi al checkout").
        -   Invia richieste AJAX a `controllers/front/ajax.php` per convalidare il carrello rispetto ai minimi del produttore.
        -   Riceve risposte JSON e aggiorna dinamicamente l'interfaccia utente con messaggi di avviso o impedisce la progressione se i minimi non sono soddisfatti.
        -   Potrebbe gestire popup modali o segnali visivi per il cliente.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `mobm/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Stila il menu a discesa di completamento automatico e il campo di input utilizzati per la selezione del produttore nel modulo di amministrazione.
    -   **Selettori di classe CSS chiave:** Probabilmente si rivolge a classi come `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, ecc.
-   `mobm/views/css/mobm.css`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Stila i messaggi di avviso visualizzati nelle pagine del carrello e del checkout. Assicura che questi messaggi siano visivamente distinti e si integrino bene con il tema.
    -   **Selettori di classe CSS chiave:** Probabilmente si rivolge a classi personalizzate aggiunte dal modulo ai contenitori dei messaggi di avviso, ad esempio, `.mobm-warning-message`, `.mobm-error-block`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   `mobm/lib/searchTool/views/scripts.tpl`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Questo template probabilmente include il JavaScript necessario per la funzionalità di completamento automatico (da `autocomplete.js`) e potenzialmente alcuni script o configurazioni inline per esso. Verrebbe renderizzato all'interno del metodo `renderForm()` di `AdminMobmController`.
-   `mobm/views/templates/front/displayShoppingCart.tpl`
    -   **Ambito:** Front-office.
    -   **Hook:** Questo template è progettato per essere renderizzato in un hook che visualizza il contenuto nella pagina del carrello, come `displayShoppingCartFooter` o `displayBeforeShoppingCartBlock`.
    -   **Responsabilità:** Visualizza il messaggio di avviso al cliente se il valore minimo d'ordine di un produttore non è soddisfatto. Conterrà la logica per mostrare il messaggio solo quando `{$mobm_warning_message}` (o variabile simile passata dal modulo) non è vuoto.

### 4.7 Schema del database e Mappa degli hook

#### Tabelle del database

-   **`ps_configuration`**: Memorizza le impostazioni generali del modulo (ad esempio, `PS_MOVB_ENABLED`, `PS_MOVB_CART_MSG_ENABLED`, `PS_MOVB_CHECKOUT_MSG_ENABLED`, `PS_MOVB_CUSTOM_MESSAGE`).
-   **`ps_mobm` (Probabile tabella personalizzata)**: Questa tabella è altamente probabile dato che `AdminMobmController` gestisce un'entità `mobm`.
    -   **Colonne (Ipotetiche):**
        -   `id_mobm` (Chiave primaria, INT)
        -   `id_manufacturer` (INT, Chiave esterna a `ps_manufacturer`)
        -   `min_value` (DECIMAL(20,6), memorizza l'importo minimo dell'ordine)
        -   `date_add` (DATETIME)
        -   `date_upd` (DATETIME)

#### Tabella degli hook registrati

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di tutte le pagine del front-office. | Per includere le risorse CSS (`mobm.css`) e JavaScript (`mobm.js`) del front-office. |
| `actionCartSave` | Dopo il salvataggio di un carrello (ad esempio, modifica quantità, prodotto aggiunto/rimosso). | Per eseguire la convalida in tempo reale dei minimi del produttore e potenzialmente memorizzare lo stato di convalida. |
| `actionValidateOrder` | Prima che un ordine venga ufficialmente convalidato. | Per impedire la convalida dell'ordine se i minimi del produttore non sono soddisfatti. |
| `displayShoppingCartFooter` (o simile) | In fondo alla pagina del carrello. | Per visualizzare il messaggio di avviso (`displayShoppingCart.tpl`) se i minimi non sono soddisfatti. |
| `displayPaymentTop` (o hook di checkout simile) | All'inizio del passaggio di selezione del pagamento nel checkout. | Per visualizzare il messaggio di avviso e impedire la progressione se i minimi non sono soddisfatti. |
| `displayAdminProductsExtra` (o simile) | Nella pagina di modifica del prodotto nel back office. | Potenzialmente per visualizzare informazioni sul valore minimo del produttore direttamente sulle pagine dei prodotti (meno probabile ma possibile). |
| `displayBackOfficeHeader` | Nella sezione `<head>` di tutte le pagine del back-office. | Per includere le risorse CSS (`autocomplete.css`) e JavaScript (`autocomplete.js`) del back-office per il modulo `AdminMobmController`. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per assicurarti di utilizzare la versione più recente e compatibile del modulo "Valore minimo ordine per produttore", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
