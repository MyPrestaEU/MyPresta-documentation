---
title: "Nascondi prodotti per paese - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Nascondi prodotti per paese di MyPresta.eu."
sidebar:
  label: "Nascondi prodotti per paese - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Hide products by country su MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-products-by-country.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/hide-products-by-country/)
>
> ---


# Nascondi prodotti per paese

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Puoi accedere alla configurazione del modulo navigando su **Moduli > Gestione moduli** e cercando "Nascondi prodotti per paese", quindi facendo clic su "Configura".

#### Impostazioni generali

-   **Abilitato / Disabilitato (Interruttore)**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo filtra attivamente i prodotti in base alle tue impostazioni.
        -   *Quando disabilitato:* Il modulo smette di filtrare i prodotti e tutti i prodotti saranno visibili a tutti i clienti indipendentemente dal paese.
    -   **Valore consigliato:** **Abilitato** una volta configurate le tue regole.
    -   **Scenario / esempio del commerciante:** Stai configurando il modulo per la prima volta e vuoi testarlo prima di renderlo attivo, quindi lo tieni disabilitato. Una volta pronto, lo abiliti.
-   **Cosa vuoi fare? (Menu a discesa)**

    -   **Cosa fa questa impostazione:** Definisce la logica principale delle tue regole di occultamento dei prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Nascondi prodotti per i paesi selezionati:* I prodotti scelti nelle sezioni "Seleziona categorie" e "Seleziona produttore" saranno nascosti ai clienti nell'elenco "Seleziona paesi". Questo è il caso d'uso più comune.
        -   *Mostra prodotti solo per i paesi selezionati:* I prodotti scelti saranno visibili SOLO ai clienti nell'elenco "Seleziona paesi". Per tutti gli altri paesi, questi prodotti saranno nascosti.
    -   **Valore consigliato:** Di solito **Nascondi prodotti per i paesi selezionati**.
    -   **Scenario / esempio del commerciante:**
        -   *Nascondi prodotti:* Vendi un marchio specifico che non può essere venduto in Germania. Selezioni "Nascondi prodotti per i paesi selezionati", scegli il marchio e selezioni la Germania.
        -   *Mostra prodotti solo:* Hai una collezione speciale di prodotti esclusivamente per il mercato statunitense. Selezioni "Mostra prodotti solo per i paesi selezionati", scegli la collezione e selezioni gli Stati Uniti.
-   **Seleziona paesi (Elenco a selezione multipla)**

    -   **Cosa fa questa impostazione:** Ti consente di scegliere i paesi specifici a cui si applicherà la tua regola "Cosa vuoi fare?".
    -   **Effetto della modifica di questa impostazione:** Solo i clienti identificati come provenienti da questi paesi selezionati saranno interessati dalle regole di visibilità dei prodotti che hai impostato.
    -   **Valore consigliato:** Seleziona tutti i paesi pertinenti per le tue regole.
    -   **Scenario / esempio del commerciante:** Se stai nascondendo prodotti per i clienti in Francia e Spagna, selezioneresti "Francia" e "Spagna" da questo elenco.
-   **Seleziona categorie (Albero delle categorie)**

    -   **Cosa fa questa impostazione:** Ti consente di scegliere categorie di prodotti specifiche i cui prodotti saranno soggetti alla regola di occultamento/visualizzazione.
    -   **Effetto della modifica di questa impostazione:** Tutti i prodotti all'interno delle categorie selezionate (e delle loro sottocategorie, se scegli di includerle) saranno interessati dalla regola "Cosa vuoi fare?".
    -   **Valore consigliato:** Seleziona le categorie contenenti i prodotti che desideri controllare.
    -   **Scenario / esempio del commerciante:** Vuoi nascondere tutti i prodotti nella tua categoria "Elettronica" ai clienti in Canada. Selezioneresti "Elettronica" qui.
-   **Seleziona produttore (Elenco a selezione multipla)**

    -   **Cosa fa questa impostazione:** Ti consente di scegliere produttori specifici i cui prodotti saranno soggetti alla regola di occultamento/visualizzazione.
    -   **Effetto della modifica di questa impostazione:** Tutti i prodotti dei produttori selezionati saranno interessati dalla regola "Cosa vuoi fare?".
    -   **Valore consigliato:** Seleziona i produttori i cui prodotti desideri controllare.
    -   **Scenario / esempio del commerciante:** Hai un accordo di distribuzione che ti impedisce di vendere prodotti "Brand X" in Australia. Selezioneresti "Brand X" qui.
-   **Escludi gruppi di clienti (Elenco a selezione multipla)**

    -   **Cosa fa questa impostazione:** Ti consente di esentare determinati gruppi di clienti dalle regole di occultamento dei prodotti del modulo.
    -   **Effetto della modifica di questa impostazione:** I clienti appartenenti ai gruppi selezionati vedranno sempre tutti i prodotti, indipendentemente dal loro paese o dalle impostazioni del modulo. Questo è utile per i partner B2B o i VIP.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia gruppi di clienti specifici che devono ignorare le regole.
    -   **Scenario / esempio del commerciante:** Hai un gruppo di clienti "Grossisti" che dovrebbe sempre vedere il tuo catalogo completo, anche se alcuni prodotti sono limitati per i clienti normali nel loro paese. Selezioneresti "Grossisti" qui.
-   **Escludi clienti (Input ricercabile)**

    -   **Cosa fa questa impostazione:** Ti consente di esentare singoli clienti dalle regole di occultamento dei prodotti del modulo.
    -   **Effetto della modifica di questa impostazione:** I clienti specifici che selezioni vedranno sempre tutti i prodotti, indipendentemente dal loro paese o dalle impostazioni del modulo.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia singoli clienti specifici che devono ignorare le regole.
    -   **Scenario / esempio del commerciante:** Un responsabile di account chiave specifico deve vedere tutti i prodotti per un cliente, anche se sta navigando da un paese con restrizioni. Cercheresti e selezioneresti quel cliente qui.

#### Impostazioni di geolocalizzazione e simulazione

-   **Imposta priorità dei metodi di identificazione dell'origine (Elenco trascina e rilascia)**

    -   **Cosa fa questa impostazione:** Determina l'ordine in cui il modulo tenta di identificare il paese di un cliente. Questo è cruciale perché metodi diversi possono talvolta dare risultati diversi.
    -   **Effetto della modifica di questa impostazione:** Il modulo proverà i metodi dall'alto verso il basso. Verrà utilizzata la prima identificazione riuscita.
        -   *Indirizzo di consegna:* Utilizza il paese dall'indirizzo di consegna selezionato dal cliente (richiede che il cliente sia loggato e abbia un indirizzo).
        -   *Indirizzo IP (Geolocalizzazione):* Utilizza l'indirizzo IP del cliente per determinare il suo paese (il più comune per gli ospiti).
        -   *Lingua del browser:* Inferisce il paese dalle impostazioni della lingua del browser del cliente (meno affidabile per un'identificazione precisa del paese).
    -   **Valore consigliato:**
        1.  Indirizzo di consegna (se l'indirizzo del cliente loggato è il più importante)
        2.  Indirizzo IP (per una precisione generale per tutti i visitatori)
        3.  Lingua del browser (come fallback, meno precisa)
    -   **Scenario / esempio del commerciante:** Vuoi dare priorità all'indirizzo di consegna effettivo del cliente se è loggato, poiché questo è il più accurato per la spedizione. Per gli ospiti, vuoi fare affidamento sulla geolocalizzazione IP. Trascineresti "Indirizzo di consegna" in alto, quindi "Indirizzo IP".
-   **Usa indirizzo di consegna (Interruttore)**

    -   **Cosa fa questa impostazione:** Controlla se il modulo considera il paese dell'indirizzo di consegna scelto dal cliente per il filtraggio dei prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Se un cliente è loggato e ha un indirizzo di consegna selezionato, il modulo utilizzerà il paese di quell'indirizzo per determinare la visibilità del prodotto.
        -   *Quando disabilitato:* Il modulo ignorerà l'indirizzo di consegna e si baserà su altri metodi (come l'indirizzo IP) anche per i clienti loggati.
    -   **Valore consigliato:** **Abilitato** per i clienti loggati, poiché l'indirizzo di consegna è spesso l'indicatore più accurato di dove deve andare il prodotto.
    -   **Scenario / esempio del commerciante:** Un cliente dagli Stati Uniti sta navigando dal Canada. Se "Usa indirizzo di consegna" è abilitato e ha un indirizzo di consegna statunitense selezionato, vedrà i prodotti disponibili negli Stati Uniti. Se disabilitato, potrebbe vedere i prodotti disponibili in Canada (in base al suo IP).
-   **Attiva whitelist (Interruttore)**

    -   **Cosa fa questa impostazione:** Questa impostazione funziona in combinazione con la funzione di geolocalizzazione integrata di PrestaShop (che si trova in **Parametri negozio > Generale > Geolocalizzazione**). Se la geolocalizzazione di PrestaShop è abilitata, questo modulo può utilizzare la sua whitelist.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Se la geolocalizzazione nativa di PrestaShop è attiva e configurata con una whitelist (paesi autorizzati a navigare), questo modulo rispetterà tale whitelist. I visitatori da paesi *non* presenti nella whitelist di PrestaShop potrebbero essere bloccati o reindirizzati prima che questo modulo applichi le sue regole.
        -   *Quando disabilitato:* Questo modulo ignorerà la whitelist di geolocalizzazione di PrestaShop e applicherà le sue regole in base alla propria identificazione del paese.
    -   **Valore consigliato:** **Disabilitato** a meno che tu non stia attivamente utilizzando e gestendo la whitelist di geolocalizzazione nativa di PrestaShop.
    -   **Scenario / esempio del commerciante:** Hai configurato la geolocalizzazione di PrestaShop per consentire solo i visitatori dai paesi dell'UE. Se abiliti "Attiva whitelist" qui, i visitatori da fuori dell'UE saranno gestiti dal sistema centrale di PrestaShop, e questo modulo applicherà quindi le sue regole specifiche per i prodotti ai visitatori dell'UE consentiti.
-   **Simula visita (Interruttore)**

    -   **Cosa fa questa impostazione:** Questo è un potente strumento di test che ti consente di fingere di navigare da un paese diverso senza effettivamente cambiare la tua posizione o utilizzare una VPN.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il campo "Simula IP" diventa attivo, consentendoti di inserire un indirizzo IP. Il modulo tratterà quindi la tua sessione di navigazione corrente come se stessi visitando dal paese associato a quell'IP.
        -   *Quando disabilitato:* Il modulo identifica il tuo paese normalmente.
    -   **Valore consigliato:** **Disabilitato** per i negozi live. Abilita solo temporaneamente per i test.
    -   **Scenario / esempio del commerciante:** Vuoi verificare che i prodotti siano correttamente nascosti per i clienti in Germania. Abiliti "Simula visita", inserisci un indirizzo IP tedesco (ad esempio, 85.214.132.112) e quindi navighi nel tuo negozio per vedere se i prodotti corretti sono nascosti.
-   **Simula IP (Input di testo)**

    -   **Cosa fa questa impostazione:** Quando "Simula visita" è abilitato, inserisci un indirizzo IP qui per simulare un visitatore dal paese di quell'IP.
    -   **Effetto della modifica di questa impostazione:** La tua sessione di navigazione corrente si comporterà come se fossi situato nel paese associato all'indirizzo IP inserito, consentendoti di testare le regole di visibilità dei prodotti.
    -   **Valore consigliato:** Lascia vuoto a meno che "Simula visita" non sia abilitato per i test.
    -   **Scenario / esempio del commerciante:** Dopo aver abilitato "Simula visita", inserisci "192.168.1.1" (un IP locale comune, ma useresti un IP pubblico reale per un paese) per testare. Per un IP tedesco, potresti usare "85.214.132.112".

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Abilitato** | Abilitato | Interruttore principale per la funzionalità del modulo. |
| Configurazione modulo | **Cosa vuoi fare?** | Nascondi prodotti per i paesi selezionati | Definisce se i prodotti sono nascosti per i paesi selezionati o mostrati solo a essi. |
| Configurazione modulo | **Seleziona paesi** | (Vuoto) / Seleziona pertinenti | Paesi interessati dalla regola di visibilità del prodotto. |
| Configurazione modulo | **Seleziona categorie** | (Vuoto) / Seleziona pertinenti | Categorie i cui prodotti sono interessati. |
| Configurazione modulo | **Seleziona produttore** | (Vuoto) / Seleziona pertinenti | Produttori i cui prodotti sono interessati. |
| Configurazione modulo | **Escludi gruppi di clienti** | (Vuoto) | Gruppi di clienti esenti dalle regole di occultamento. |
| Configurazione modulo | **Escludi clienti** | (Vuoto) | Singoli clienti esenti dalle regole di occultamento. |
| Configurazione modulo | **Imposta priorità dei metodi di identificazione dell'origine** | Indirizzo di consegna, Indirizzo IP, Lingua del browser | Ordine dei metodi per identificare il paese del cliente. |
| Configurazione modulo | **Usa indirizzo di consegna** | Abilitato | Usa il paese dell'indirizzo di consegna del cliente per il filtraggio. |
| Configurazione modulo | **Attiva whitelist** | Disabilitato | Rispetta la whitelist di geolocalizzazione nativa di PrestaShop. |
| Configurazione modulo | **Simula visita** | Disabilitato | Abilita per testare la visibilità del prodotto da un IP specifico. |
| Configurazione modulo | **Simula IP** | (Vuoto) | Indirizzo IP da simulare quando "Simula visita" è abilitato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma i prodotti sono ancora visibili/nascosti in modo errato. Cosa dovrei controllare per primo?**
R:

1.  **Modulo abilitato:** Ricontrolla che l'interruttore principale "Abilitato" nella pagina di configurazione del modulo sia su ON.
2.  **Cache:** Svuota la cache di PrestaShop (vai su **Parametri avanzati > Prestazioni**, quindi fai clic su "Svuota cache" in alto a destra). Anche la cache del browser a volte può interferire, quindi prova un aggiornamento forzato (Ctrl+F5 o Cmd+Shift+R) o una finestra di navigazione in incognito/privata.
3.  **Simulazione:** Se stai testando, assicurati che "Simula visita" sia abilitato e "Simula IP" sia impostato correttamente. Se non stai simulando, assicurati che "Simula visita" sia disabilitato.
4.  **Logica delle regole:** Rivedi la tua impostazione "Cosa vuoi fare?" ("Nascondi prodotti per i paesi selezionati" vs. "Mostra prodotti solo per i paesi selezionati") e assicurati che corrisponda alla tua intenzione.
5.  **Selezione paese/categoria/produttore:** Assicurati di aver selezionato correttamente i paesi, le categorie e i produttori che dovrebbero essere interessati.

**D: Come identifica il modulo il paese di un cliente?**
R: Il modulo utilizza un sistema di priorità che configuri:

1.  **Indirizzo di consegna:** Se il cliente è loggato e ha un indirizzo di consegna, questo è il più accurato.
2.  **Indirizzo IP (Geolocalizzazione):** Per gli ospiti o se non viene utilizzato alcun indirizzo di consegna, utilizza l'indirizzo IP del visitatore per determinare il suo paese.
3.  **Lingua del browser:** Come fallback, può inferire il paese dalle impostazioni della lingua del browser, anche se questo è meno preciso. Puoi regolare la priorità nelle impostazioni del modulo.

**D: Questo modulo influirà sulla mia SEO? Google indicizzerà comunque i miei prodotti nascosti?**
R: Il modulo nasconde i prodotti dalla visualizzazione front-office per paesi specifici. Generalmente, i crawler dei motori di ricerca (come Googlebot) spesso eseguono la scansione da indirizzi IP specifici (ad esempio, IP basati negli Stati Uniti). Se i tuoi prodotti sono nascosti per gli Stati Uniti, Google potrebbe non vederli. Se sono nascosti per altri paesi ma visibili per gli Stati Uniti, Google potrebbe comunque indicizzarli. Per problemi SEO critici, considera l'utilizzo della funzione nativa "Disabilita prodotto" di PrestaShop o di regole specifiche di robots.txt se non desideri assolutamente che un prodotto venga indicizzato da nessuna parte. Questo modulo è principalmente per l'esperienza utente front-end e la conformità, non per il controllo SEO.

**D: Posso nascondere prodotti per clienti o gruppi di clienti specifici, indipendentemente dal loro paese?**
R: Sì! Il modulo include le impostazioni "Escludi gruppi di clienti" ed "Escludi clienti". Queste ti consentono di specificare gruppi o singoli clienti che vedranno *sempre* tutti i prodotti, bypassando efficacemente le regole di occultamento basate sul paese. Questo è utile per VIP, partner B2B o personale interno.

**D: Cosa succede se un cliente di un paese con restrizioni tenta di accedere a un prodotto nascosto tramite un link diretto?**
R: Il modulo è progettato per impedire l'accesso. Tipicamente, verranno reindirizzati alla homepage o a un errore "pagina non trovata", assicurando che non possano visualizzare o aggiungere il prodotto con restrizioni al loro carrello.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Nascondi prodotti per paese" (`hbc`) opera principalmente sovrascrivendo le classi core di PrestaShop e utilizzando hook per intercettare e modificare le query dei prodotti prima che vengano visualizzate al cliente. Sfrutta l'`ObjectModel` di PrestaShop per l'archiviazione della configurazione e si basa sulla geolocalizzazione IP o sui dati dell'indirizzo del cliente per determinare il paese del visitatore. La logica del modulo viene iniettata nel processo di filtraggio dei prodotti, garantendo che i prodotti con restrizioni vengano rimossi dagli elenchi, dai risultati di ricerca e dai tentativi di accesso diretto.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene controller Front-Office o Back-Office Admin dedicati. La sua configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli core (`classes/`)

Il modulo implementa override per modificare il comportamento core di PrestaShop.

-   **`hbc/override/classes/index.php`**: File `index.php` vuoto standard per prevenire l'elenco delle directory.
-   **`hbc/override/classes/shop/index.php`**: File `index.php` vuoto standard per prevenire l'elenco delle directory.
-   **`hbc/override/classes/shop/Shop.php`**:
    -   **Nome classe**: `Shop` (sovrascrive la classe `Shop` core di PrestaShop)
    -   **Classe genitore**: `ShopCore`
    -   **Responsabilità**: Questa sovrascrittura è critica. Probabilmente modifica il modo in cui viene determinato il contesto del prodotto o del negozio, iniettando potenzialmente la logica di filtraggio specifica per paese a un livello molto fondamentale del sistema di multi-negozio e recupero prodotti di PrestaShop. Ciò garantisce che le regole di visibilità dei prodotti siano applicate in modo coerente in varie parti del negozio. Gli sviluppatori dovrebbero essere consapevoli che la sovrascrittura di `Shop.php` può avere effetti di vasta portata e può entrare in conflitto con altri moduli che sovrascrivono anche questa classe core.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`hbc/lib/searchTool/views/js/autocomplete.js`**:
    -   **Ambito**: Back-office (probabilmente utilizzato nel modulo di configurazione del modulo).
    -   **Scopo**: Questo script fornisce la funzionalità di completamento automatico, in particolare per il campo di input "Escludi clienti" nella configurazione del modulo. Probabilmente effettua chiamate AJAX a un endpoint di amministrazione di PrestaShop per cercare i clienti mentre l'amministratore digita, migliorando l'usabilità per la selezione di singoli clienti.
    -   **Funzionalità chiave**:
        -   Inizializza un widget di completamento automatico su un campo di input specifico (ad esempio, `#hbc_exclude_customer`).
        -   Invia richieste AJAX (ad esempio, a `admin-ajax.php` o a un controller admin dedicato) con la query digitata.
        -   Analizza le risposte JSON contenenti i dati del cliente (ID, nome, email).
        -   Visualizza i suggerimenti in un elenco a discesa.
        -   Gestisce la selezione di un cliente, popolando un input nascosto con l'ID del cliente e visualizzando il nome.
        -   Gestisce la rimozione dei clienti selezionati dall'elenco.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`hbc/lib/searchTool/views/css/autocomplete.css`**:
    -   **Ambito**: Back-office (stila il widget di completamento automatico).
    -   **Scopo**: Fornisce lo stile per lo strumento di ricerca di completamento automatico del cliente utilizzato nella configurazione del modulo. Ciò include lo stile per il campo di input, l'elenco a discesa dei suggerimenti e potenzialmente la visualizzazione dei clienti selezionati.
    -   **Selettori chiave**: Probabilmente si rivolge a classi e ID associati al widget di completamento automatico, come `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item` ed elementi per la visualizzazione di tag/token selezionati.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`hbc/lib/searchTool/views/scripts.tpl`**:

    -   **Ambito**: Back-office.
    -   **Scopo**: Questo template probabilmente include i file JavaScript e CSS necessari per lo strumento di ricerca di completamento automatico (`autocomplete.js` e `autocomplete.css`) e potenzialmente inizializza la logica JavaScript. Probabilmente è incluso nel template di configurazione principale.
-   **`hbc/views/templates/admin/AdminTab.tpl`**:

    -   **Ambito**: Back-office.
    -   **Scopo**: Questo template è probabilmente un wrapper generico o un componente utilizzato all'interno della pagina di configurazione del modulo. Potrebbe definire la struttura per un'interfaccia a schede o una sezione specifica all'interno delle impostazioni del modulo.
-   **`hbc/views/templates/admin/button-subcategories.tpl`**:

    -   **Ambito**: Back-office.
    -   **Scopo**: Questo template probabilmente renderizza un pulsante o un elemento dell'interfaccia utente relativo alla selezione delle categorie, in particolare per includere/escludere sottocategorie quando si selezionano categorie padre nel modulo di configurazione.
-   **`hbc/views/templates/admin/configuration.tpl`**:

    -   **Ambito**: Back-office.
    -   **Scopo**: Questo è il template Smarty principale per la pagina di configurazione del modulo. Renderizza tutte le impostazioni, i campi di input, gli interruttori e gli elenchi descritti nella Sezione 4.1. Utilizza i componenti del modulo helper di PrestaShop e probabilmente include `scripts.tpl` per la funzionalità di completamento automatico.
-   **`hbc/views/templates/hook/displayHeader.tpl`**:

    -   **Ambito**: Front-office.
    -   **Hook**: `displayHeader`
    -   **Scopo**: Questo template viene renderizzato nella sezione `<head>` di ogni pagina del front-office. Potrebbe essere utilizzato per:
        -   Iniettare JavaScript inline per il rilevamento del paese lato client (meno probabile dato il filtraggio lato server).
        -   Impostare variabili JavaScript in base alla configurazione del modulo (ad esempio, modalità di simulazione).
        -   Includere file CSS o JS aggiuntivi necessari a livello globale per la funzionalità front-office del modulo (anche se il filtraggio core è lato server).
        -   Potenzialmente gestire reindirizzamenti o controlli iniziali basati sulla geolocalizzazione prima che la pagina si carichi completamente.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo utilizza principalmente la tabella `ps_configuration` di PrestaShop per archiviare le sue impostazioni.
    -   Le chiavi di configurazione includono: `HBC_EXCLUDE_GROUP`, `HBC_EXCLUDE_CUSTOMER`, `HBC_SIMULATE_ON`, `HBC_SIMULATE_IP`, `HBC_DELIVERY`, `HBC_WHITELIST_ON`, `HBC_COUNTRY`, `HBC_WTD`, `HBC_MANUFACT`, `HBC_CATEGORIES`, `HBC_PRIORITY`.
    -   Nessuna tabella SQL personalizzata viene creata da questo modulo.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Ambito | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | Nella sezione `<head>` di ogni pagina. | Potenzialmente per iniettare script lato client, meta tag o controlli iniziali. |
| `actionAdminControllerSetMedia` | Back-office | Quando un controller admin imposta le sue risorse multimediali. | Utilizzato per caricare CSS/JS per la pagina di configurazione del modulo (ad esempio, `autocomplete.js`, `autocomplete.css`). |
| `actionDispatcherAfter` | Front-office | Dopo che il dispatcher ha elaborato la richiesta. | Potrebbe essere utilizzato per eseguire reindirizzamenti o controlli finali dopo che una pagina è stata identificata ma prima del rendering. |
| `displayFilterProductSearch` | Front-office | Durante il filtraggio della ricerca prodotti. | **CRITICO**: Questo hook viene utilizzato per iniettare la logica del modulo nella query di ricerca prodotti, garantendo che i prodotti nascosti siano esclusi dai risultati di ricerca. |
| `actionProductUpdate` | Back-office | Dopo che un prodotto viene aggiornato nel Back Office. | Potrebbe essere utilizzato per svuotare la cache relativa alla visibilità del prodotto o rivalutare le regole per il prodotto aggiornato. |
| `displayAdminProductsExtra` | Back-office | Nella pagina di modifica del prodotto nel Back Office. | Potrebbe essere utilizzato per visualizzare informazioni o impostazioni aggiuntive relative all'occultamento del prodotto specifico in fase di modifica (anche se non esplicitamente identificato nelle impostazioni). |
| `actionCartSave` | Front-office | Quando il carrello viene salvato (ad esempio, prodotto aggiunto/rimosso). | Potrebbe essere utilizzato per impedire l'aggiunta di prodotti nascosti al carrello o per rimuoverli se il paese del cliente cambia. |
| `FilterProductSearch` | Front-office | Durante il filtraggio della ricerca prodotti (simile a `displayFilterProductSearch`). | **CRITICO**: Un altro hook per modificare le query di ricerca prodotti, garantendo un filtraggio completo in diversi contesti di ricerca. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Nascondi prodotti per paese", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
