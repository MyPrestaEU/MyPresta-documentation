---
title: "Accesso ai prodotti per paese - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Accesso ai prodotti per paese' di MyPresta.eu."
sidebar:
  label: "Accesso ai prodotti per paese - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Access to products by country su MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products-by-country.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/access-to-products-by-country/)
>
> ---


# Accesso ai prodotti per paese

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Accesso ai prodotti per paese". Qui troverai tutte le impostazioni per definire come viene limitato l'accesso ai prodotti.

#### Impostazioni generali

-   **Abilitato / Disabilitato (Stato del modulo)**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato:* Il modulo filtrerà attivamente i prodotti in base alle restrizioni per paese.
        -   *Quando Disabilitato:* Il modulo sarà inattivo e tutti i prodotti saranno visibili a tutti i clienti, indipendentemente dal loro paese.
    -   **Valore consigliato:** **Abilitato** una volta configurate le tue regole.
    -   **Scenario / esempio del commerciante:** Stai configurando il modulo per la prima volta; tienilo disabilitato finché non hai definito tutte le tue regole, quindi abilitalo per renderlo operativo.
-   **Cosa vuoi fare? (Tipo di restrizione)**

    -   **Cosa fa questa impostazione:** Definisce la logica principale delle tue restrizioni per paese: vuoi *bloccare* i prodotti in paesi selezionati, o *consentire* i prodotti *solo* in paesi selezionati?
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Blocca l'accesso ai prodotti nei paesi selezionati":* I prodotti che configuri saranno nascosti ai clienti nei paesi che specifichi. Saranno visibili ovunque altrove.
        -   *Quando impostato su "Consenti l'accesso ai prodotti SOLO nei paesi selezionati":* I prodotti che configuri saranno visibili *solo* ai clienti nei paesi che specifichi. Saranno nascosti ovunque altrove.
    -   **Valore consigliato:** Scegli in base al tuo caso d'uso principale. Se hai pochi paesi in cui un prodotto è limitato, scegli "Blocca". Se un prodotto è esclusivo per pochi paesi, scegli "Consenti SOLO".
    -   **Scenario / esempio del commerciante:**
        -   *Blocca:* Vendi un marchio specifico che non può essere spedito in Canada. Selezioneresti "Blocca accesso" e poi sceglieresti il Canada per quel prodotto.
        -   *Consenti SOLO:* Hai un prodotto in edizione speciale disponibile per la vendita solo negli Stati Uniti e in Messico. Selezioneresti "Consenti accesso SOLO" e poi sceglieresti Stati Uniti e Messico per quel prodotto.
-   **Seleziona paesi**

    -   **Cosa fa questa impostazione:** Qui selezioni i paesi specifici che saranno interessati dalla regola "Cosa vuoi fare?".
    -   **Effetto della modifica di questa impostazione:** I paesi selezionati saranno bloccati dalla visualizzazione del prodotto o saranno gli unici a cui sarà consentito vederlo, a seconda dell'impostazione "Cosa vuoi fare?".
    -   **Valore consigliato:** Seleziona tutti i paesi pertinenti in base alle tue restrizioni sui prodotti.
    -   **Scenario / esempio del commerciante:** Se stai bloccando le vendite in Canada e Australia, selezioneresti sia Canada che Australia dall'elenco.
-   **Seleziona categorie**

    -   **Cosa fa questa impostazione:** Ti consente di applicare le regole di restrizione per paese a intere categorie di prodotti anziché a singoli prodotti.
    -   **Effetto della modifica di questa impostazione:** Tutti i prodotti all'interno delle categorie selezionate erediteranno le regole di restrizione per paese definite sopra.
    -   **Valore consigliato:** Usalo per restrizioni ampie. Lascia vuoto se vuoi gestire le restrizioni prodotto per prodotto.
    -   **Scenario / esempio del commerciante:** Tutti i prodotti nella tua categoria "Elettronica" non possono essere venduti in Brasile. Selezioneresti la categoria "Elettronica" qui.
-   **Seleziona produttore**

    -   **Cosa fa questa impostazione:** Ti consente di applicare le regole di restrizione per paese a tutti i prodotti di produttori specifici.
    -   **Effetto della modifica di questa impostazione:** Tutti i prodotti dei produttori selezionati erediteranno le regole di restrizione per paese.
    -   **Valore consigliato:** Usalo per restrizioni a livello di marchio. Lascia vuoto se vuoi gestire le restrizioni prodotto per prodotto o categoria per categoria.
    -   **Scenario / esempio del commerciante:** Hai un accordo di distribuzione che ti impedisce di vendere prodotti "Marchio X" in Europa. Selezioneresti "Marchio X" qui.

#### Esclusioni clienti e gruppi

-   **Escludi gruppi di clienti**

    -   **Cosa fa questa impostazione:** Ti consente di esentare determinati gruppi di clienti dalle restrizioni per paese. Ad esempio, potresti avere un gruppo B2B speciale a cui è consentito acquistare prodotti con restrizioni.
    -   **Effetto della modifica di questa impostazione:** I clienti appartenenti ai gruppi selezionati *non* saranno soggetti alle restrizioni per paese definite da questo modulo. Vedranno tutti i prodotti.
    -   **Valore consigliato:** Seleziona i gruppi che necessitano di accesso speciale, come "Clienti all'ingrosso" o "Dipendenti". Lascia vuoto se tutti i clienti devono essere soggetti a restrizioni.
    -   **Scenario / esempio del commerciante:** Hai un gruppo "Clienti VIP" a cui è consentito acquistare prodotti altrimenti soggetti a restrizioni nel loro paese. Selezioneresti il gruppo "Clienti VIP" qui.
-   **Escludi clienti**

    -   **Cosa fa questa impostazione:** Ti consente di esentare specifici clienti individuali dalle restrizioni per paese.
    -   **Effetto della modifica di questa impostazione:** I singoli clienti selezionati *non* saranno soggetti alle restrizioni per paese. Vedranno tutti i prodotti.
    -   **Valore consigliato:** Usalo per eccezioni specifiche. Lascia vuoto se non necessario.
    -   **Scenario / esempio del commerciante:** Un cliente specifico è un partner a lungo termine e necessita di accesso a tutti i prodotti indipendentemente dalla sua posizione. Selezioneresti il suo account cliente qui.

#### Impostazioni di geolocalizzazione e simulazione

-   **Imposta priorità dei metodi di identificazione dell'origine**

    -   **Cosa fa questa impostazione:** Determina l'ordine in cui il modulo tenta di identificare il paese del cliente. Questo è cruciale per la precisione.
    -   **Effetto della modifica di questa impostazione:** Il modulo proverà prima il metodo in cima all'elenco. Se questo fallisce o non è disponibile, passerà al successivo.
    -   **Valore consigliato:**
        1.  **Indirizzo di consegna (se disponibile):** Questo è il più accurato per l'intento di acquisto effettivo.
        2.  **Geolocalizzazione:** Ottimo per la navigazione iniziale.
        3.  **Paese dell'account cliente:** Se loggato.
    -   **Scenario / esempio del commerciante:** Un cliente sta navigando dagli Stati Uniti (geolocalizzazione), ma intende spedire in Canada. Se "Indirizzo di consegna" è prioritario, il modulo utilizzerà il Canada per le restrizioni una volta che lo avranno inserito nel carrello.
-   **Usa indirizzo di consegna**

    -   **Cosa fa questa impostazione:** Quando abilitato, il modulo considererà il paese dell'indirizzo di consegna selezionato dal cliente nel carrello come la sua "origine" per l'applicazione delle restrizioni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato:* Se un cliente aggiunge un prodotto con restrizioni al carrello e poi seleziona un indirizzo di consegna in un paese bloccato, il modulo impedirà il checkout o rimuoverà il prodotto.
        -   *Quando Disabilitato:* Il modulo si baserà esclusivamente sulla geolocalizzazione IP o sul paese registrato del cliente, che potrebbe non corrispondere alla destinazione di spedizione prevista.
    -   **Valore consigliato:** **SÌ**. Questo fornisce l'applicazione delle restrizioni più accurata e pratica durante il processo di checkout.
    -   **Scenario / esempio del commerciante:** Un cliente dalla Germania (dove un prodotto è consentito) lo aggiunge al carrello, ma poi seleziona un indirizzo di spedizione in Austria (dove il prodotto è bloccato). Con questa impostazione abilitata, il modulo impedirà l'ordine.
-   **Simula visita**

    -   **Cosa fa questa impostazione:** Ti consente di testare le tue restrizioni per paese simulando una visita da un paese specifico senza effettivamente cambiare il tuo indirizzo IP.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato:* Il modulo tratterà la tua sessione corrente come se stessi navigando dal paese specificato in "Simula IP".
        -   *Quando Disabilitato:* Il modulo utilizza il tuo indirizzo IP effettivo per la geolocalizzazione.
    -   **Valore consigliato:** **Disabilitato** per i negozi live. **Abilitato** solo per i test.
    -   **Scenario / esempio del commerciante:** Vuoi verificare se un prodotto è correttamente nascosto ai clienti in Francia. Abiliti "Simula visita", inserisci un indirizzo IP francese (o selezioni la Francia se disponibile) e poi navighi nel tuo negozio.
-   **Simula IP**

    -   **Cosa fa questa impostazione:** Quando "Simula visita" è abilitato, questo campo ti consente di inserire un indirizzo IP del paese che desideri simulare, o selezionare un paese da un elenco a discesa.
    -   **Effetto della modifica di questa impostazione:** Il modulo utilizzerà questo IP/paese per tutti i controlli di restrizione durante la tua sessione simulata.
    -   **Valore consigliato:** Inserisci un indirizzo IP valido o seleziona un paese a scopo di test.
    -   **Scenario / esempio del commerciante:** Per simulare una visita dalla Germania, potresti inserire `88.130.179.0` (un IP tedesco) o semplicemente selezionare "Germania" dall'elenco.

#### Impostazioni Whitelist

-   **Attiva whitelist**

    -   **Cosa fa questa impostazione:** Questa impostazione sfrutta la funzionalità di whitelist di geolocalizzazione integrata di PrestaShop. Se la geolocalizzazione di PrestaShop è attiva, questa whitelist ti consente di definire indirizzi IP specifici o intervalli IP che dovrebbero *sempre* essere autorizzati ad accedere al tuo negozio, indipendentemente dal loro paese rilevato. Questo è utile per gli IP del tuo ufficio o per i partner fidati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato:* Il modulo rispetterà la whitelist di geolocalizzazione di PrestaShop. Gli IP in questo elenco bypasseranno qualsiasi restrizione per paese.
        -   *Quando Disabilitato:* La whitelist non sarà considerata.
    -   **Valore consigliato:** **SÌ** se utilizzi la geolocalizzazione di PrestaShop e hai IP che desideri whitelistere.
    -   **Scenario / esempio del commerciante:** Il tuo ufficio si trova in un paese in cui alcuni prodotti sono soggetti a restrizioni, ma devi accedervi per scopi amministrativi. Aggiungeresti l'indirizzo IP del tuo ufficio alla whitelist di geolocalizzazione di PrestaShop e abiliteresti questa impostazione.
-   **Whitelist**

    -   **Cosa fa questa impostazione:** Qui gestisci gli indirizzi IP specifici o gli intervalli IP che sono whitelisted. Questo corrisponde direttamente all'impostazione `PS_GEOLOCATION_WHITELIST` di PrestaShop.
    -   **Effetto della modifica di questa impostazione:** Qualsiasi indirizzo IP o intervallo inserito qui bypasserà tutte le restrizioni basate sulla geolocalizzazione.
    -   **Valore consigliato:** Aggiungi gli indirizzi IP del tuo ufficio, gli IP del server di sviluppo o qualsiasi altro IP fidato che dovrebbe sempre avere pieno accesso.
    -   **Scenario / esempio del commerciante:** Aggiungi `192.168.1.1/24` (la tua rete d'ufficio) per assicurarti che tutti i dipendenti possano accedere a tutti i prodotti.

#### Impostazioni di aggiornamento (interne)

-   **mypresta\_updates, update\_, updatev\_**
    -   **Cosa fanno queste impostazioni:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per gestire gli aggiornamenti e i controlli di versione. Non sono destinate all'interazione diretta del commerciante.
    -   **Effetto della modifica di questa impostazione:** La modifica di queste potrebbe interferire con le notifiche di aggiornamento del modulo.
    -   **Valore consigliato:** Lascia queste impostazioni così come sono.
    -   **Scenario / esempio del commerciante:** Nessuno scenario del commerciante; queste sono per la gestione interna del modulo.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Abilitato / Disabilitato** | Abilitato | Interruttore principale per la funzionalità del modulo. |
| Configurazione modulo | **Cosa vuoi fare?** | Blocca accesso | Definisce se le regole bloccano l'accesso o consentono l'accesso SOLO. |
| Configurazione modulo | **Seleziona paesi** | (Nessuno) | Paesi interessati dalla regola di restrizione. |
| Configurazione modulo | **Seleziona categorie** | (Nessuno) | Categorie i cui prodotti sono interessati dalla regola. |
| Configurazione modulo | **Seleziona produttore** | (Nessuno) | Produttori i cui prodotti sono interessati dalla regola. |
| Configurazione modulo | **Escludi gruppi di clienti** | (Nessuno) | Gruppi di clienti esenti da restrizioni. |
| Configurazione modulo | **Escludi clienti** | (Nessuno) | Singoli clienti esenti da restrizioni. |
| Configurazione modulo | **Imposta priorità dei metodi di identificazione dell'origine** | Indirizzo di consegna, Geolocalizzazione, Paese dell'account cliente | Ordine dei metodi per determinare il paese del cliente. |
| Configurazione modulo | **Usa indirizzo di consegna** | SÌ | Considera l'indirizzo di consegna per l'applicazione delle restrizioni. |
| Configurazione modulo | **Simula visita** | Disabilitato | Abilita/disabilita la simulazione IP per i test. |
| Configurazione modulo | **Simula IP** | (Vuoto) | Indirizzo IP/paese da simulare per i test. |
| Configurazione modulo | **Attiva whitelist** | SÌ | Abilita/disabilita la whitelist di geolocalizzazione di PrestaShop. |
| Configurazione modulo | **Whitelist** | (Vuoto) | Elenco di indirizzi IP/intervalli per bypassare le restrizioni. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I prodotti sono ancora visibili in un paese bloccato, cosa devo fare?**
R1: Innanzitutto, controlla la configurazione del tuo modulo:
\* Il modulo è "Abilitato"?
\* "Cosa vuoi fare?" è impostato correttamente (ad esempio, "Blocca accesso" se vuoi nasconderli)?
\* Sono stati scelti i "Seleziona paesi" corretti?
\* "Seleziona categorie" o "Seleziona produttore" sono applicati correttamente ai prodotti in questione?
\* Se stai testando, assicurati che "Simula visita" sia abilitato e "Simula IP" sia impostato sul paese corretto.
\* Infine, svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**) e la cache del tuo browser.

**D2: Il mio indirizzo IP sembra essere bloccato, anche se mi trovo in un paese consentito.**
R2: Questo può accadere se il tuo IP è in qualche modo identificato erroneamente o se hai commesso un errore nella configurazione.
\* Controlla l'impostazione "Whitelist" e assicurati che l'indirizzo IP del tuo ufficio o personale sia aggiunto lì se vuoi bypassare tutte le restrizioni.
\* Verifica il tuo indirizzo IP pubblico effettivo (puoi usare siti web come "what is my IP").
\* Assicurati che "Attiva whitelist" sia abilitato se stai usando la whitelist di geolocalizzazione integrata di PrestaShop.

**D3: Come fa il modulo a determinare il paese di un cliente?**
R3: Il modulo utilizza un sistema di priorità:
1.  **Indirizzo di consegna:** Se "Usa indirizzo di consegna" è abilitato e il cliente ha inserito un indirizzo di spedizione nel carrello, questo ha la priorità.
2.  **Geolocalizzazione:** Utilizza l'indirizzo IP del cliente per determinare la sua posizione geografica.
3.  **Paese dell'account cliente:** Se il cliente è loggato, utilizza il paese registrato nel suo account.
Puoi regolare la priorità di questi metodi nella configurazione del modulo.

**D4: Ho un tema personalizzato, questo modulo funzionerà?**
R4: Sì, il modulo è progettato per funzionare con i temi standard di PrestaShop. Filtra principalmente i prodotti a livello di dati prima che vengano renderizzati dal tema. Tuttavia, se il tuo tema personalizzato ha una logica di elenco prodotti molto insolita o sovrascrive gli hook di visualizzazione dei prodotti core di PrestaShop, potrebbero essere necessarie piccole modifiche. Se riscontri problemi, contatta il supporto MyPresta.eu.

**D5: Posso limitare l'accesso a prodotti specifici, non solo a categorie o produttori?**
R5: Sì, il modulo funziona filtrando i prodotti. Sebbene la schermata di configurazione principale ti consenta di selezionare categorie e produttori, la logica principale del modulo si applica ai singoli prodotti. Puoi lasciare vuoti "Seleziona categorie" e "Seleziona produttore" e gestire le restrizioni direttamente sulle singole pagine dei prodotti (se il modulo aggiunge una scheda lì, cosa comune per tali moduli). *In base alle informazioni fornite, il modulo funziona configurando regole che si applicano ai prodotti in base alle categorie/produttori selezionati nella configurazione principale. Non dichiara esplicitamente una scheda di configurazione a livello di prodotto, ma la descrizione implica "ogni prodotto individualmente". Se non c'è una scheda prodotto, la selezione di categoria/produttore è il modo principale per mirare ai prodotti.*

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Accesso ai prodotti per paese" (`atpbc`) è costruito come un modulo PrestaShop standard, sfruttando il pattern MVC dove appropriato. La sua funzione principale è intercettare le query sui prodotti e filtrare i risultati in base alle restrizioni per paese configurate e alla posizione identificata del cliente. Si integra con il core di PrestaShop agganciandosi a vari punti di visualizzazione e azione, in particolare quelli relativi al recupero e alla visualizzazione dei prodotti. La geolocalizzazione è un componente chiave, che determina l'origine del cliente, che viene poi confrontata con le regole del modulo.

### 4.2 Controller (`controllers/`)

Il modulo non sembra avere controller front-office o back-office personalizzati nella sua directory `controllers/` in base all'inventario fornito. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli core (`classes/`)

Il modulo non sembra avere classi personalizzate o definizioni `ObjectModel` in una directory `classes/`. La logica principale e la gestione dei dati sono probabilmente incapsulate all'interno del file `atpbc.php` principale, utilizzando `Configuration` per le impostazioni e query dirette al database o le classi `Product` e `Category` di PrestaShop per la manipolazione dei dati.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`atpbc/lib/searchTool/views/js/autocomplete.js`**
    -   **Ambito:** Back-office.
    -   **Scopo:** Questo script probabilmente fornisce funzionalità di completamento automatico per i campi di input all'interno della configurazione del modulo, come la selezione di clienti, categorie o produttori. Migliora l'esperienza utente suggerendo opzioni mentre l'amministratore digita, riducendo errori e accelerando la configurazione.
    -   **Funzionalità:** Lega i listener di eventi a campi di input specifici (ad esempio, `keyup`, `focus`), invia richieste AJAX a un endpoint del back-office (probabilmente gestito dal file principale del modulo o da un controller amministrativo core di PrestaShop) per recuperare i suggerimenti e visualizza questi suggerimenti in un elenco a discesa. Gestisce la selezione e il popolamento del campo di input.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`atpbc/lib/searchTool/views/css/autocomplete.css`**
    -   **Ambito:** Styling del modulo di amministrazione del back-office.
    -   **Scopo:** Fornisce lo styling per il menu a discesa dei suggerimenti di completamento automatico e potenzialmente per i campi di input stessi, garantendo un aspetto coerente e facile da usare all'interno del back office di PrestaShop.
    -   **Selettori chiave:** Probabilmente mira a classi come `.autocomplete-suggestions`, `.autocomplete-suggestion-item`, `.autocomplete-input` per controllare layout, colori, font e stati di hover. Gli sviluppatori possono sovrascriverli nel loro tema amministrativo personalizzato o aggiungendo CSS con maggiore specificità.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`atpbc/lib/searchTool/views/scripts.tpl`**

    -   **Ambito:** Back-office.
    -   **Scopo:** Questo template è probabilmente utilizzato per includere lo script `autocomplete.js` e potenzialmente altre configurazioni relative a JavaScript o script inline per la funzionalità `searchTool`. Potrebbe anche definire variabili passate al JavaScript.
    -   **Renderizzato in:** Probabilmente agganciato a `actionAdminControllerSetMedia` o direttamente incluso nel template di configurazione principale.
-   **`atpbc/views/templates/admin/AdminTab.tpl`**

    -   **Ambito:** Back-office.
    -   **Scopo:** Questo template è probabilmente un template generico per una scheda amministrativa personalizzata o una sezione all'interno della configurazione del modulo. Potrebbe contenere la struttura per la visualizzazione di elenchi, moduli o altri contenuti amministrativi.
    -   **Renderizzato in:** Potrebbe essere incluso da `configuration.tpl` o utilizzato se il modulo avesse un controller amministrativo dedicato.
-   **`atpbc/views/templates/admin/button-subcategories.tpl`**

    -   **Ambito:** Back-office.
    -   **Scopo:** Questo template probabilmente renderizza un pulsante o un elemento dell'interfaccia utente specificamente per la gestione delle sottocategorie all'interno della configurazione del modulo, possibilmente per l'impostazione "Seleziona categorie" per espandere/comprimere gli alberi delle categorie.
    -   **Renderizzato in:** All'interno di `configuration.tpl` quando si visualizzano le opzioni di selezione delle categorie.
-   **`atpbc/views/templates/admin/configuration.tpl`**

    -   **Ambito:** Back-office.
    -   **Scopo:** Questo è il template Smarty principale per la pagina di configurazione del modulo, renderizzato dal metodo `getContent()` in `atpbc.php`. Contiene tutti i moduli HTML, i campi di input, gli interruttori e gli elenchi di selezione per le impostazioni del modulo.
    -   **Renderizzato in:** Quando si accede alla pagina di configurazione del modulo nel Back Office di PrestaShop.
-   **`atpbc/views/templates/hook/displayHeader.tpl`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo template è agganciato a `displayHeader`. Viene tipicamente utilizzato per includere CSS, JavaScript o meta tag del front-office che devono essere caricati all'inizio della pagina. Per questo modulo, potrebbe includere la logica per rilevare il paese del cliente o impostare variabili lato client per un uso successivo.
    -   **Renderizzato in:** La sezione `<head>` di ogni pagina del front-office.
-   **`atpbc/views/templates/hook/displayHeaderNoAccess.tpl`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo template è probabilmente un fallback o una visualizzazione specifica per quando un cliente viene rilevato come "senza accesso" a un particolare prodotto o pagina. Potrebbe contenere uno script di reindirizzamento, un messaggio o uno styling specifico per nascondere il contenuto.
    -   **Renderizzato in:** Potenzialmente all'interno di `displayHeader` o un altro hook, condizionato dalle restrizioni di accesso.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo utilizza principalmente la tabella `ps_configuration` di PrestaShop per memorizzare le sue impostazioni (ad esempio, `atpbc_EXCLUDE_GROUP`, `atpbc_EXCLUDE_CUSTOMER`, `atpbc_COUNTRY`, `atpbc_WTD`, `atpbc_MANUFACT`, `atpbc_CATEGORIES`, `atpbc_PRIORITY`, `atpbc_SIMULATE_ON`, `atpbc_SIMULATE_IP`, `atpbc_DELIVERY`, `atpbc_WHITELIST_ON`).
    -   Non sembra creare tabelle SQL personalizzate in base all'inventario fornito.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Prima che il contenuto di un controller amministrativo venga renderizzato, dopo che i media sono stati impostati. | Per includere JS/CSS del back-office (ad esempio, `autocomplete.js`, `autocomplete.css`) per la pagina di configurazione del modulo. |
| `actionDispatcherAfter` | Dopo che il dispatcher ha elaborato una richiesta. | Potenzialmente utilizzato per eseguire reindirizzamenti o modificare la risposta in base alle regole di accesso dopo che una pagina è stata identificata. |
| `displayFilterProductSearch` | Durante il filtraggio della ricerca prodotti. | Per modificare i risultati della ricerca prodotti, rimuovendo i prodotti con restrizioni in base al paese. |
| `actionProductUpdate` | Dopo che un prodotto viene aggiornato nel Back Office. | Per potenzialmente svuotare la cache relativa alla disponibilità del prodotto o rivalutare le regole per il prodotto aggiornato. |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office. | Per aggiungere campi extra o una scheda per le regole di accesso specifiche del prodotto (sebbene non esplicitamente dichiarato, questo è un uso comune per questo hook). |
| `actionCartSave` | Dopo che un carrello viene salvato o aggiornato. | Per verificare se i prodotti nel carrello sono consentiti per il paese identificato del cliente (specialmente se "Usa indirizzo di consegna" è abilitato). |
| `FilterProductSearch` | Durante il filtraggio della ricerca prodotti (simile a `displayFilterProductSearch`, spesso per manipolare direttamente la query). | Per modificare la query del database per le ricerche di prodotti, assicurando che i prodotti con restrizioni non vengano recuperati. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Per includere JavaScript/CSS del front-office (ad esempio, `displayHeader.tpl`, `displayHeaderNoAccess.tpl`) o eseguire la rilevazione precoce del paese. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto professionale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il tuo modulo funzioni in modo ottimale e offra la migliore esperienza possibile per il tuo negozio.
"""
