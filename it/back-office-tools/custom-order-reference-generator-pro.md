---
title: "Custom Order Reference Generator Pro - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Custom Order Reference Generator Pro di MyPresta.eu."
sidebar:
  label: "Custom Order Reference Generator Pro - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Custom Order Reference Generator Pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/custom-order-reference-generator-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/custom-order-reference-generator-pro/)
>
> ---


# Custom Order Reference Generator Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Custom Order Reference Generator Pro)

Questa è la schermata di configurazione principale dove definisci i tuoi modelli e regole di riferimento d'ordine personalizzati. La pagina è tipicamente organizzata in diverse schede o sezioni per chiarezza.

#### **Scheda Impostazioni Generali**

Questa scheda controlla il comportamento fondamentale del modulo.

- **Abilita la generazione di riferimenti d'ordine personalizzati:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo. Quando abilitato, il modulo si occuperà della generazione dei riferimenti d'ordine. Quando disabilitato, PrestaShop tornerà al suo metodo predefinito di generazione dei riferimenti d'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Tutti i nuovi ordini riceveranno un riferimento generato da questo modulo secondo le tue regole definite.
    - *Quando disabilitato:* Tutti i nuovi ordini utilizzeranno il formato di riferimento predefinito di PrestaShop. Gli ordini esistenti manterranno i loro riferimenti.
  - **Valore consigliato:** SÌ (per attivare la funzionalità del modulo).
  - **Scenario / esempio per il commerciante:** Se vuoi iniziare a usare riferimenti personalizzati, abilita questa opzione. Se hai bisogno di tornare temporaneamente al valore predefinito di PrestaShop per la risoluzione dei problemi, disabilitala.
- **Modello di riferimento predefinito:**

  - **Cosa fa questa impostazione:** Definisce la struttura di base per i tuoi riferimenti d'ordine personalizzati. Puoi combinare testo statico con "shortcode" dinamici che estraggono informazioni dall'ordine, dal cliente o dalla data.
  - **Effetto della modifica di questa impostazione:** Questo determina direttamente il formato dei tuoi riferimenti d'ordine quando non si applica alcuna regola specifica.
  - **Valore consigliato:** Inizia con qualcosa di semplice come `MIONOMEAZIENDA-{DATE:YMD}-{ID_ORDER}` o `ORD-{RAND:6}`.
  - **Scenario / esempio per il commerciante:**
    - `MIONOMEAZIENDA-{DATE:YMD}-{ID_ORDER}`: Genera riferimenti come `MIONOMEAZIENDA-20231027-12345`. Questo è ottimo per identificare facilmente gli ordini dal tuo negozio e vedere la data in cui sono stati effettuati, insieme a un ID ordine sequenziale.
    - `ORD-{RAND:6}`: Genera riferimenti come `ORD-A1B2C3`. Questo fornisce un riferimento breve, casuale e unico.
    - `{CUSTOMER_LASTNAME}-{ID_ORDER}`: Genera riferimenti come `ROSSI-12345`. Utile per B2B o servizi personalizzati.
  - **Shortcode disponibili:**
    - `{ID_ORDER}`: L'ID univoco dell'ordine (sequenziale).
    - `{ID_CUSTOMER}`: L'ID univoco del cliente.
    - `{DATE:format}`: Data e ora attuali. `format` utilizza la sintassi della funzione `date()` di PHP (es. `YMD` per 20231027, `His` per 143059).
    - `{RAND:length}`: Una stringa casuale di caratteri alfanumerici, `length` specifica quanti caratteri (es. `RAND:6`).
    - `{CUSTOMER_FIRSTNAME}`: Nome del cliente.
    - `{CUSTOMER_LASTNAME}`: Cognome del cliente.
    - `{CUSTOMER_EMAIL}`: Indirizzo email del cliente.
    - `{PAYMENT_METHOD}`: Il metodo di pagamento utilizzato per l'ordine.
    - `{DELIVERY_COUNTRY_ISO}`: Codice ISO del paese di consegna (es. IT, FR).
    - `{DELIVERY_CITY}`: Città dell'indirizzo di consegna.
    - `{CART_TOTAL}`: Valore totale del carrello.
    - `{PRODUCT_SKU}`: SKU del primo prodotto nel carrello (usare con cautela, può essere lungo).
    - `{PRODUCT_NAME}`: Nome del primo prodotto nel carrello (usare con cautela).
    - `{SHOP_NAME}`: Il nome del tuo negozio PrestaShop.
- **Valore iniziale del contatore sequenziale:**

  - **Cosa fa questa impostazione:** Se il tuo modello di riferimento include `{ID_ORDER}` o un elemento sequenziale simile, questo definisce il numero di partenza per quella sequenza.
  - **Effetto della modifica di questa impostazione:** I nuovi ordini inizieranno la loro numerazione sequenziale da questo valore. Questo è utile se stai migrando da un altro sistema o vuoi riavviare la numerazione.
  - **Valore consigliato:** 1 (per un nuovo inizio) o un numero più alto se devi continuare una sequenza.
  - **Scenario / esempio per il commerciante:** Se in precedenza avevi 1000 ordini e vuoi che i tuoi nuovi riferimenti personalizzati inizino da 1001, imposta questo valore a 1001.
- **Limite di lunghezza del riferimento:**

  - **Cosa fa questa impostazione:** PrestaShop ha un limite predefinito per la lunghezza del riferimento dell'ordine. Questo ti consente di definire una lunghezza massima per i tuoi riferimenti generati. Se un riferimento supera questo limite, verrà troncato.
  - **Effetto della modifica di questa impostazione:** Assicura che i tuoi riferimenti rientrino nei vincoli del database e vengano visualizzati correttamente in tutte le aree di PrestaShop.
  - **Valore consigliato:** 9 (il valore predefinito di PrestaShop è spesso 9, ma puoi aumentarlo se il tuo tema/database lo supporta, fino a 32 caratteri è generalmente sicuro).
  - **Scenario / esempio per il commerciante:** Se il tuo modello `MIONOMEAZIENDA-{DATE:YMD}-{ID_ORDER}` produce `MIONOMEAZIENDA-20231027-12345` (21 caratteri) e imposti il limite a 9, potrebbe diventare `MIONOMEAZIENDA-2`. Fai attenzione al troncamento.
- **Anteprima riferimento:**

  - **Cosa fa questa impostazione:** Questo è un campo di utilità che ti consente di testare il tuo `Modello di riferimento predefinito` con un ID ordine fittizio per vedere come apparirebbe il riferimento generato.
  - **Effetto della modifica di questa impostazione:** Nessun effetto diretto sul tuo negozio, è puramente uno strumento di test.
  - **Valore consigliato:** Usalo frequentemente quando progetti i tuoi modelli.
  - **Scenario / esempio per il commerciante:** Inserisci `12345` come ID ordine fittizio e clicca su "Genera Anteprima" per vedere come apparirebbe `MIONOMEAZIENDA-{DATE:YMD}-{ID_ORDER}`.

#### **Scheda Regole**

Questa scheda è dove definisci le condizioni specifiche in base alle quali devono essere applicati diversi modelli di riferimento d'ordine, sovrascrivendo il modello predefinito. Le regole vengono elaborate dall'alto verso il basso e viene applicata la prima regola corrispondente.

- **Aggiungi nuova regola / Modifica regola:**

  - **Cosa fa:** Ti consente di creare una nuova regola o modificare una esistente. Ogni regola consiste in:
    - **Nome regola:** Un nome descrittivo per il tuo riferimento interno (es. "Ordini di alto valore", "Clienti francesi").
    - **Modello regola:** Il modello di riferimento personalizzato da utilizzare se questa regola corrisponde (stessi shortcode del modello predefinito).
    - **Condizioni:** Uno o più criteri che devono essere soddisfatti affinché questa regola si applichi.
  - **Effetto della modifica di questa impostazione:** Aggiunge o modifica un modello di riferimento condizionale.
  - **Valore consigliato:** Crea regole per i tuoi segmenti di business più importanti.
  - **Scenario / esempio per il commerciante:**
    - **Regola 1: Ordini di alto valore**
      - **Modello:** `VIP-{ID_ORDER}-{DATE:YMD}`
      - **Condizione:** `Totale carrello` è `maggiore di` `500`
      - **Effetto:** Qualsiasi ordine superiore a €500 riceverà un riferimento come `VIP-12345-20231027`.
    - **Regola 2: Clienti francesi**
      - **Modello:** `FR-{ID_ORDER}`
      - **Condizione:** `Paese di consegna` è `Francia`
      - **Effetto:** Gli ordini spediti in Francia riceveranno `FR-12345`.
    - **Regola 3: Ordini di prodotti specifici**
      - **Modello:** `PROD-XYZ-{ID_ORDER}`
      - **Condizione:** `Prodotto nel carrello` è `Nome prodotto XYZ`
      - **Effetto:** Gli ordini contenenti "Nome prodotto XYZ" riceveranno `PROD-XYZ-12345`.
- **Condizioni della regola (per ogni regola):**

  - **Cosa fa:** Definisce i criteri affinché una regola sia attiva. Puoi combinare più condizioni usando la logica "AND".
  - **Condizioni disponibili:**
    - **Totale carrello:** Basato sul valore totale dell'ordine.
    - **Gruppo clienti:** Basato sul gruppo a cui appartiene il cliente (es. Visitatori, Clienti, Ospiti o gruppi personalizzati).
    - **Paese di consegna:** Basato sul paese dell'indirizzo di spedizione.
    - **Metodo di pagamento:** Basato sul modulo di pagamento utilizzato (es. Bonifico bancario, PayPal).
    - **Prodotto nel carrello:** Basato sulla presenza di un prodotto specifico (per ID o nome) nell'ordine.
    - **Corriere:** Basato sul corriere di spedizione scelto.
  - **Effetto della modifica di questa impostazione:** Determina quando viene utilizzato un modello di riferimento personalizzato specifico.
  - **Valore consigliato:** Utilizza condizioni che segmentano chiaramente i tuoi ordini.
  - **Scenario / esempio per il commerciante:** Una regola per "Clienti all'ingrosso" potrebbe utilizzare `Gruppo clienti è All'ingrosso`. Una regola per "Spedizione espressa" potrebbe utilizzare `Corriere è DHL Express`.

#### **Scheda Impostazioni Avanzate**

Questa scheda contiene impostazioni per aspetti più tecnici e di manutenzione.

- **Backup / Ripristino JSON:**

  - **Cosa fa:** Ti consente di esportare la configurazione del tuo modulo (modelli, regole) in un file JSON o importare una configurazione precedentemente salvata.
  - **Effetto della modifica di questa impostazione:**
    - *Backup:* Crea un file scaricabile delle tue impostazioni.
    - *Ripristino:* Sovrascrive le impostazioni attuali con quelle del file JSON caricato.
  - **Valore consigliato:** Esegui sempre il backup della tua configurazione prima di apportare modifiche importanti o aggiornare il tuo negozio PrestaShop.
  - **Scenario / esempio per il commerciante:** Prima di aggiornare PrestaShop o spostare il tuo negozio su un nuovo server, scarica un backup delle tue regole di riferimento personalizzate. Se commetti un errore con una regola, puoi facilmente ripristinare una versione precedente.
- **Reimposta configurazione modulo:**

  - **Cosa fa:** Elimina tutti i modelli e le regole personalizzate, riportando il modulo al suo stato predefinito, appena installato.
  - **Effetto della modifica di questa impostazione:** Tutti i tuoi modelli e le tue regole di riferimento personalizzati andranno persi.
  - **Valore consigliato:** Usa con estrema cautela, solo se vuoi ricominciare completamente da capo.
  - **Scenario / esempio per il commerciante:** Se le tue regole sono diventate troppo complesse o stanno causando problemi e vuoi ricominciare da zero, puoi usare questa opzione. Esegui sempre il backup prima!

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Impostazioni Generali** | Abilita la generazione di riferimenti d'ordine personalizzati | SÌ | Attiva/disattiva la logica di riferimento personalizzata del modulo. |
|  | Modello di riferimento predefinito | `ORD-{RAND:6}` (esempio) | Definisce il formato di riferimento di fallback quando nessuna regola corrisponde. |
|  | Valore iniziale del contatore sequenziale | 1 | Imposta il numero iniziale per `{ID_ORDER}` nei nuovi riferimenti. |
|  | Limite di lunghezza del riferimento | 9 (o superiore se sicuro) | Limita la lunghezza massima dei riferimenti generati per prevenire problemi. |
|  | Anteprima riferimento | (N/A) | Strumento per testare il tuo modello con un ID ordine fittizio. |
| **Scheda Regole** | Aggiungi/Modifica regola | N/A | Crea modelli di riferimento condizionali basati su criteri. |
|  | Nome regola | Descrittivo (es. "Ordini di alto valore") | Etichetta interna per la regola. |
|  | Modello regola | Personalizzato (es. `VIP-{ID_ORDER}`) | Il formato di riferimento per questa specifica regola. |
|  | Condizioni della regola | Varia (es. `Totale carrello > 500`) | Criteri che devono essere soddisfatti affinché la regola si applichi. |
| **Impostazioni Avanzate** | Backup / Ripristino JSON | N/A | Esporta/importa la configurazione del modulo per sicurezza o migrazione. |
|  | Reimposta configurazione modulo | N/A | Elimina tutte le impostazioni e le regole del modulo. Usa con estrema cautela. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: I miei riferimenti personalizzati non vengono visualizzati, o vedo ancora i riferimenti predefiniti di PrestaShop.**
R1: Innanzitutto, assicurati che il modulo sia **abilitato** nella scheda "Impostazioni generali". Inoltre, controlla se hai svuotato la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache). Se hai regole specifiche, assicurati che le loro condizioni siano soddisfatte e che le regole siano ordinate correttamente (viene applicata la prima regola corrispondente).

**D2: I miei riferimenti personalizzati sono troppo lunghi o vengono troncati.**
R2: Controlla il "Limite di lunghezza del riferimento" nella scheda "Impostazioni generali". PrestaShop ha un limite predefinito (spesso 9 caratteri) per i riferimenti d'ordine nel suo database. Se il tuo modello personalizzato genera riferimenti più lunghi, potresti dover aumentare questo limite. Fai attenzione, poiché aumentarlo troppo potrebbe causare problemi di visualizzazione in alcuni temi o versioni precedenti di PrestaShop. È generalmente sicuro arrivare fino a 32 caratteri. Se hai bisogno di più, consulta uno sviluppatore.

**D3: Ho commesso un errore con le mie regole e ora i miei riferimenti sono sbagliati. Come posso risolvere?**
R3: Se hai un backup JSON recente (dalla scheda "Impostazioni avanzate"), puoi ripristinarlo. Altrimenti, dovrai modificare o eliminare manualmente le regole problematiche. Se vuoi ricominciare completamente da capo, usa l'opzione "Reimposta configurazione modulo", ma tieni presente che questo eliminerà *tutti* i tuoi modelli e le tue regole personalizzate.

**D4: Posso usare questo modulo con più negozi (configurazione multistore)?**
R4: Sì, il modulo è progettato per essere compatibile con la funzionalità multistore di PrestaShop. Puoi configurare diversi modelli e regole di riferimento per ogni negozio dalla pagina di configurazione del modulo, selezionando il contesto specifico del negozio nel back office di PrestaShop.

**D5: Cosa succede agli ordini esistenti quando cambio il modello di riferimento?**
R5: La modifica del modello o delle regole di riferimento influisce solo sui *nuovi* ordini effettuati dopo la modifica. Gli ordini esistenti manterranno i loro riferimenti d'ordine originali. Il modulo non modifica retroattivamente i dati degli ordini passati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Custom Order Reference Generator Pro" estende principalmente la classe `Order` di PrestaShop tramite un override per intercettare e modificare il processo di generazione del riferimento dell'ordine. Segue un approccio basato sugli eventi in cui il modulo si aggancia al ciclo di vita della creazione dell'ordine. La configurazione è gestita tramite un metodo `getContent()` standard nel file principale del modulo, memorizzando le impostazioni in `ps_configuration` e le regole personalizzate nelle proprie tabelle di database (anche se non sono elencati file SQL specifici, ciò implica la creazione dinamica di tabelle o la memorizzazione della configurazione). Il modulo utilizza un `RulesEngine` per valutare le condizioni e un `ReferenceGenerator` per costruire il riferimento finale basato su modelli e shortcode definiti.

### 4.2 Controller (`controllers/`)

Questo modulo non sembra utilizzare controller front-office o back-office personalizzati. Tutta la configurazione è gestita all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

- `refchangepro/classes/PayloadFactory.php`

  - **Nome classe:** `PayloadFactory`
  - **Classe genitore:** Nessuna (probabilmente una classe di utilità)
  - **Responsabilità:** Responsabile della creazione di un payload di dati (contesto) che `RulesEngine` e `ReferenceGenerator` possono utilizzare. Questo payload conterrebbe informazioni sull'ordine corrente in fase di elaborazione (es. totale carrello, ID cliente, paese di consegna, prodotti). Agisce come un livello di astrazione per raccogliere tutti i dati necessari per la valutazione delle regole e la generazione del riferimento.
- `refchangepro/classes/ReferenceContext.php`

  - **Nome classe:** `ReferenceContext`
  - **Classe genitore:** Nessuna (probabilmente un oggetto di trasferimento dati o un oggetto valore)
  - **Responsabilità:** Una semplice classe per contenere e gestire i dati contestuali (es. ID ordine, dettagli cliente, dettagli carrello) che vengono passati durante il processo di generazione del riferimento. Assicura la coerenza dell'accesso ai dati per il generatore e il motore delle regole.
- `refchangepro/classes/ReferenceGenerator.php`

  - **Nome classe:** `ReferenceGenerator`
  - **Classe genitore:** Nessuna (probabilmente una classe di servizio)
  - **Responsabilità:** La logica principale per la costruzione della stringa di riferimento dell'ordine finale. Prende un modello (es. `MIONOMEAZIENDA-{DATE:YMD}-{ID_ORDER}`) e un oggetto `ReferenceContext`, quindi sostituisce gli shortcode con i valori effettivi. Gestisce la formattazione della data, la generazione di stringhe casuali e l'inserimento di ID sequenziali.
- `refchangepro/classes/RulesEngine.php`

  - **Nome classe:** `RulesEngine`
  - **Classe genitore:** Nessuna (probabilmente una classe di servizio)
  - **Responsabilità:** Valuta le regole definite rispetto al contesto dell'ordine corrente. Itera attraverso le regole configurate, verifica se le condizioni (es. totale carrello, gruppo clienti, paese) sono soddisfatte e restituisce il modello della prima regola corrispondente. Se nessuna regola corrisponde, indica che deve essere utilizzato il modello predefinito.
- `refchangepro/classes/Runtime.php`

  - **Nome classe:** `Runtime`
  - **Classe genitore:** Nessuna (probabilmente una classe di utilità o helper)
  - **Responsabilità:** Potrebbe gestire configurazioni di runtime, caching o altri aspetti operativi del modulo. Potrebbe essere responsabile del caricamento delle regole dalla configurazione, della gestione del contatore sequenziale o della fornitura di metodi di utilità utilizzati in tutto il modulo.
- `refchangepro/override/classes/order/Order.php`

  - **Percorso file esatto:** `refchangepro/override/classes/order/Order.php`
  - **Nome classe:** `Order`
  - **Classe genitore:** `OrderCore` (classe Order core di PrestaShop)
  - **Responsabilità:** Questo è l'override critico. Intercetta il metodo `generateReference()` (o un metodo simile responsabile dell'impostazione del riferimento dell'ordine) all'interno della classe `Order` core di PrestaShop. All'interno di questo metodo sovrascritto, chiama il `RulesEngine` del modulo per determinare il modello corretto e quindi il `ReferenceGenerator` per creare il riferimento personalizzato, impostandolo infine per l'oggetto ordine. Ciò garantisce che ogni nuovo ordine creato utilizzi la logica del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

- `refchangepro/lib/searchTool/views/js/autocomplete.js`

  - **Ambito:** Probabilmente Back-office.
  - **Descrizione:** Fornisce la funzionalità di completamento automatico, possibilmente per la selezione di prodotti, clienti o altre entità durante la definizione delle regole. Si legherebbe ai campi di input, effettuerebbe richieste AJAX a un controller di amministrazione di PrestaShop (o al metodo `getContent` del modulo) e visualizzerebbe suggerimenti.
- `refchangepro/views/js/admin-tabs.js`

  - **Ambito:** Back-office.
  - **Descrizione:** Gestisce l'interfaccia a schede all'interno della pagina di configurazione del modulo. Lega gli eventi di clic alle intestazioni delle schede, mostra/nasconde il contenuto delle schede corrispondenti e potrebbe gestire le modifiche dell'hash URL per il collegamento diretto alle schede.
- `refchangepro/views/js/rules-builder.js`

  - **Ambito:** Back-office.
  - **Descrizione:** Questo è il JavaScript principale per la scheda "Regole". Gestisce l'aggiunta, la modifica e l'eliminazione dinamica delle condizioni delle regole. Lega gli eventi ai pulsanti "Aggiungi condizione", gestisce i menu a discesa per i tipi di condizione (es. "Totale carrello", "Gruppo clienti") e renderizza dinamicamente i campi di input in base al tipo di condizione selezionato (es. input numerico per il totale del carrello, casella di selezione per i gruppi di clienti). Probabilmente serializza i dati della regola in un campo di input nascosto per l'invio.

### 4.5 Fogli di stile CSS (`views/css/`)

- `refchangepro/lib/searchTool/views/css/autocomplete.css`

  - **Ambito:** Stile dell'amministrazione del Back-office.
  - **Descrizione:** Stila gli elenchi di suggerimenti di completamento automatico e i campi di input, assicurando che siano visivamente coerenti e facili da usare all'interno del back office di PrestaShop.
- `refchangepro/views/css/admin.css`

  - **Ambito:** Stile dell'amministrazione del Back-office.
  - **Descrizione:** Fornisce uno stile generale per la pagina di configurazione del modulo, inclusi layout, tipografia, stili dei pulsanti e presentazione visiva complessiva per integrarsi perfettamente con il tema del back office di PrestaShop.
- `refchangepro/views/css/rules-builder.css`

  - **Ambito:** Stile dell'amministrazione del Back-office.
  - **Descrizione:** Stili specifici per l'interfaccia del costruttore di regole, inclusi il layout dei singoli blocchi di regole, le righe delle condizioni e qualsiasi elemento di trascinamento o riordino.

### 4.6 Struttura del template Smarty (`views/templates/`)

- `refchangepro/lib/searchTool/views/scripts.tpl`
  - **Ambito:** Amministrazione del Back-office.
  - **Descrizione:** Questo template probabilmente include il JavaScript e potenzialmente il CSS necessari per lo strumento di ricerca con completamento automatico. Sarebbe incluso nel template di configurazione del modulo principale per caricare la funzionalità di completamento automatico.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - La descrizione del modulo menziona "Regole intelligenti applicano modelli diversi per valore del carrello, paese, prodotto o gruppo di clienti". Ciò implica fortemente la creazione di tabelle di database personalizzate per memorizzare queste regole e le loro condizioni associate.
  - Tabelle previste (i nomi sono illustrativi, i nomi effettivi sarebbero prefissati con `ps_` e il nome del modulo):
    - `ps_refchangepro_rules`: Memorizza le definizioni delle regole principali (ID, nome, modello, stato attivo).
    - `ps_refchangepro_conditions`: Memorizza le singole condizioni per ogni regola (ID regola, tipo di condizione, operatore, valore).
  - Le impostazioni di configurazione (come `PS_REFCHANGEPRO_ENABLED`, `PS_REFCHANGEPRO_DEFAULT_PATTERN`, `PS_REFCHANGEPRO_COUNTER_START`) sono memorizzate nella tabella `ps_configuration` di PrestaShop.
  - Il contatore sequenziale per `{ID_ORDER}` potrebbe essere memorizzato in `ps_configuration` o in una tabella dedicata per un blocco più robusto.
- **Tabella degli hook registrati**:

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionOrderAdd` / `actionObjectOrderAddAfter` | Dopo la creazione di un nuovo oggetto ordine nel database. | L'override del modulo di `Order::generateReference()` è il meccanismo primario. Tuttavia, se il modulo deve eseguire azioni aggiuntive *dopo* che l'ordine è stato completamente salvato con il suo nuovo riferimento, questi hook verrebbero utilizzati. Ad esempio, per registrare il riferimento generato o aggiornare un contatore personalizzato. |
| `displayBackOfficeHeader` | Nella sezione `<head>` del Back Office. | Utilizzato per caricare CSS specifici del modulo (`admin.css`, `rules-builder.css`, `autocomplete.css`) e JavaScript (`admin-tabs.js`, `rules-builder.js`, `autocomplete.js`) per la pagina di configurazione. |
| `displayAdminProductsExtra` / `displayAdminCustomers` (Ipotetico) | Nelle pagine di modifica del prodotto o del cliente nel Back Office. | Se il modulo dovesse offrire impostazioni di riferimento specifiche per prodotto o cliente, si aggancerebbe qui per visualizzare tali opzioni. (Non esplicitamente dichiarato, ma comune per le versioni "Pro"). |
| `displayModuleConfigure` (Interno) | Quando viene caricata la pagina di configurazione del modulo. | Il metodo `getContent()` del file principale del modulo è implicitamente agganciato qui per renderizzare il modulo di configurazione. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriori informazioni riguardanti il modulo "Custom Order Reference Generator Pro", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi domanda o problema.
