---
title: "Arukereso.hu - email di sondaggio del programma di acquisto fidato - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Arukereso.hu - email di sondaggio del programma di acquisto fidato di MyPresta.eu."
sidebar:
  label: "Arukereso.hu - email di sondaggio del programma di acquisto fidato - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Arukereso.hu - trusted purchase program survey emails su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/arukeresohu-trusted-purchase-program-survey-emails.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/arukeresohu-trusted-purchase-program-survey-emails/)
>
> ---


# Arukereso.hu - email di sondaggio del programma di acquisto fidato

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo Arukereso.hu. Puoi accedervi navigando su **Moduli > Gestione moduli**, cercando "Arukereso.hu" e cliccando su "Configura".

#### 2.1.1 Arukereso.hu WebApiKey

-   **Cosa fa questa impostazione:** Questo è il tuo identificatore unico fornito da Arukereso.hu. È essenziale che Arukereso.hu colleghi le richieste di sondaggio provenienti dal tuo negozio PrestaShop al tuo specifico account commerciante sulla loro piattaforma.
-   **Effetto della modifica di questa impostazione:**
    -   *Se inserito correttamente:* Il modulo può comunicare con successo con i sistemi di Arukereso.hu, abilitando il processo automatico di invio delle email di sondaggio.
    -   *Se errato o vuoto:* Arukereso.hu non sarà in grado di identificare il tuo negozio e le email di sondaggio non verranno inviate ai tuoi clienti. L'integrazione fallirà.
-   **Valore consigliato:** Inserisci l'esatta chiave API fornita da Arukereso.hu. Questa si trova solitamente nelle impostazioni del tuo account commerciante sul sito web di Arukereso.hu.
-   **Scenario / esempio del commerciante:** Ti registri al "Programma di Acquisto Fidato" su Arukereso.hu. Ti forniscono una stringa di caratteri come `abcdef1234567890`. Copi e incolli questa stringa in questo campo.

#### 2.1.2 Identificatore del prodotto (feed ITEM\_ID)

-   **Cosa fa questa impostazione:** Questa impostazione determina quale identificatore di prodotto dal tuo negozio PrestaShop verrà inviato ad Arukereso.hu. Arukereso.hu utilizza questo ID per abbinare il prodotto acquistato con la sua inserzione sulla loro piattaforma, garantendo che il sondaggio sia pertinente.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "ID Prodotto":* Verrà utilizzato l'ID interno del prodotto PrestaShop (es. `123`). Questa è l'opzione più comune e solitamente più sicura.
    -   *Se impostato su "Riferimento Prodotto":* Verrà utilizzato il codice di riferimento del tuo prodotto (es. `SKU-001`). Questo richiede che i tuoi riferimenti di prodotto siano unici e coerenti con ciò che Arukereso.hu si aspetta.
    -   *Se impostato su "EAN13 Prodotto":* Verrà utilizzato il codice a barre EAN-13 del prodotto. Questo è adatto se i tuoi EAN sono utilizzati in modo coerente e corrispondono al catalogo prodotti di Arukereso.hu.
    -   *Se impostato su "UPC Prodotto":* Verrà utilizzato il codice UPC del prodotto. Simile all'EAN13, richiede dati coerenti.
-   **Valore consigliato:** "ID Prodotto" è generalmente l'opzione più sicura e affidabile, a meno che tu non abbia un motivo specifico (e verificato con Arukereso.hu) per utilizzare un altro identificatore.
-   **Scenario / esempio del commerciante:** Se hai un prodotto "Maglietta Rossa" con un ID interno di `15`, un riferimento `TSHIRT-RED` e un EAN `1234567890123`, scegliendo "ID Prodotto" invierai `15` ad Arukereso.hu. Se scegli "Riferimento Prodotto", verrà inviato `TSHIRT-RED`. Assicurati che l'identificatore scelto sia quello che Arukereso.hu si aspetta per collegare correttamente i prodotti.

#### 2.1.3 Richiedi consenso del cliente

-   **Cosa fa questa impostazione:** Questa impostazione cruciale controlla se i tuoi clienti devono accettare esplicitamente di partecipare al programma di sondaggio di Arukereso.hu durante il checkout. Questo è vitale per la conformità alle normative sulla privacy dei dati come il GDPR.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato ("Sì"):* Una casella di controllo o un meccanismo di consenso simile apparirà durante il processo di checkout. Solo i clienti che spuntano questa casella avranno i loro dati d'ordine inviati ad Arukereso.hu per scopi di sondaggio. Questo garantisce la conformità al GDPR.
    -   *Se disabilitato ("No"):* Non verrà mostrata alcuna opzione di consenso. Tutti i clienti che completano un ordine verranno automaticamente iscritti al programma di sondaggio di Arukereso.hu. **Usare con cautela e solo se si è certi che le normative locali non richiedano un consenso esplicito per questo tipo di condivisione dei dati.**
-   **Valore consigliato:** "Sì". Si raccomanda vivamente di abilitare questa opzione per garantire la conformità al GDPR e ad altre leggi sulla privacy, dando ai clienti il controllo sui propri dati.
-   **Scenario / esempio del commerciante:** Operi nell'UE. Per conformarti al GDPR, abiliti questa impostazione. Durante il checkout, i clienti vedono una casella di controllo: "Sì, accetto di ricevere un sondaggio sulla soddisfazione del cliente da Arukereso.hu riguardo al mio acquisto." Solo se spuntano questa casella i loro dati verranno condivisi.

#### 2.1.4 Scrivi errori su log.txt

-   **Cosa fa questa impostazione:** Questa impostazione controlla se il modulo registra eventuali errori o problemi che incontra durante il suo funzionamento in un file `log.txt` all'interno della directory del modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato ("Sì"):* Eventuali problemi (es. fallimento della connessione ad Arukereso.hu, problemi di chiave API non valida) verranno scritti in `arukereso/log.txt`. Questo è estremamente utile per la risoluzione dei problemi.
    -   *Se disabilitato ("No"):* Gli errori non verranno registrati in un file. Sebbene ciò riduca leggermente l'attività del disco, rende molto più difficile la diagnosi dei problemi.
-   **Valore consigliato:** "Sì" durante la configurazione iniziale e se si riscontrano problemi. Una volta che il modulo funziona senza problemi, è possibile disabilitarlo se si preferisce, ma spesso è meglio lasciarlo abilitato per un monitoraggio continuo.
-   **Scenario / esempio del commerciante:** Hai configurato il modulo, ma i clienti non ricevono i sondaggi. Abiliti questa impostazione e, dopo alcuni ordini di prova, controlli `arukereso/log.txt` e trovi un messaggio di errore che indica "Chiave API non valida". Questo ti dice immediatamente dove cercare il problema.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Arukereso.hu WebApiKey | La tua chiave Arukereso.hu | Identificatore unico per il tuo negozio su Arukereso.hu. **Richiesto per l'integrazione.** |
| Configurazione Modulo | Identificatore del prodotto (feed ITEM\_ID) | ID Prodotto | Definisce quale ID prodotto (ID PrestaShop, Riferimento, EAN, UPC) viene inviato ad Arukereso.hu. |
| Configurazione Modulo | Richiedi consenso del cliente | Sì | Visualizza una casella di controllo per il consenso durante il checkout. **Altamente raccomandato per la conformità al GDPR.** |
| Configurazione Modulo | Scrivi errori su log.txt | Sì | Registra gli errori del modulo in `arukereso/log.txt` per la risoluzione dei problemi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non ricevono email di sondaggio da Arukereso.hu. Cosa devo controllare?**
R:

1.  **Arukereso.hu WebApiKey:** Ricontrolla che la tua chiave API sia inserita correttamente nella configurazione del modulo. Anche un singolo errore di battitura impedirà il funzionamento dell'integrazione.
2.  **Impostazione del Consenso:** Se "Richiedi consenso del cliente" è abilitato, assicurati che i clienti stiano effettivamente spuntando la casella di consenso durante il checkout. Se non lo fanno, nessun dato viene inviato.
3.  **File di Log:** Abilita "Scrivi errori su log.txt" nella configurazione del modulo e controlla il file `arukereso/log.txt` per eventuali messaggi di errore dopo un ordine di prova. Questo è il modo più diretto per diagnosticare i problemi.
4.  **Account Arukereso.hu:** Accedi al tuo account commerciante Arukereso.hu e controlla lo stato dell'integrazione del tuo "Programma di Acquisto Fidato". Potrebbero avere log o indicatori di stato specifici.
5.  **Stato dell'Ordine:** Assicurati che lo stato dell'ordine che attiva il sondaggio (solitamente "Pagamento accettato" o "Consegnato") sia configurato correttamente sul lato di Arukereso.hu e che i tuoi ordini PrestaShop raggiungano tale stato.

**D: Ho abilitato "Richiedi consenso del cliente", ma non vedo la casella di controllo durante il checkout.**
R:

1.  **Compatibilità del Tema:** Il modulo utilizza hook standard di PrestaShop (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`). Se il tuo tema è pesantemente personalizzato, potrebbe non renderizzare correttamente questi hook.
2.  **Cache:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota cache).
3.  **Posizione del Modulo:** Vai su Design > Posizioni e cerca gli hook menzionati sopra. Assicurati che il modulo Arukereso.hu sia elencato e attivo in questi hook. In caso contrario, prova a trapiantarlo.
4.  **Conflitti tra Moduli:** Disabilita temporaneamente altri moduli che modificano il processo di checkout per escludere conflitti.

**D: Cosa succede se un cliente richiede la cancellazione dei propri dati (Diritto all'oblio GDPR)?**
R: Il modulo è progettato per integrarsi con gli strumenti GDPR di PrestaShop. Quando un cliente richiede la cancellazione dei dati tramite il modulo GDPR di PrestaShop, questo modulo Arukereso.hu risponderà all'hook `actionDeleteGDPRCustomer`, garantendo che tutti i dati relativi al cliente detenuti dal modulo (ad esempio, i record di consenso) vengano rimossi. Tuttavia, è importante notare che questo modulo *invia* dati ad Arukereso.hu. Dovrai anche contattare direttamente Arukereso.hu per richiedere la cancellazione dei dati di quel cliente dai loro sistemi.

**D: Posso personalizzare l'aspetto della casella di controllo del consenso?**
R: L'aspetto della casella di controllo del consenso è controllato principalmente dal CSS del tuo tema PrestaShop. Il modulo fornisce la struttura HTML tramite il suo template `consent.tpl`. Puoi sovrascrivere questo template nel tuo tema o aggiungere CSS personalizzato per stilizzare l'elemento se hai bisogno di cambiarne l'aspetto.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Arukereso.hu è un modulo PrestaShop leggero focalizzato principalmente sull'integrazione con il "Programma di Acquisto Fidato" di Arukereso.hu. Sfrutta il sistema di hook di PrestaShop per iniettare un'opzione di consenso durante il checkout e per inviare i dati dell'ordine ad Arukereso.hu alla conferma dell'ordine. Segue una struttura standard dei moduli PrestaShop, con la sua logica principale residente nel file del modulo principale (`arukereso.php`) e utilizzando i template Smarty per la visualizzazione nel front-office. Non introduce controller o ObjectModels personalizzati, affidandosi alla classe `Configuration` di PrestaShop per l'archiviazione delle impostazioni.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller Front-Office o Back-Office personalizzato. Tutta la logica è gestita all'interno del file del modulo principale `arukereso.php`, principalmente tramite metodi hook.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo **non** definisce classi o ObjectModels personalizzati nella directory `classes/`. Opera direttamente all'interno del file `arukereso.php`, utilizzando classi e funzioni standard di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato. Tutta l'interazione front-office (ad esempio, la casella di controllo del consenso) è gestita tramite moduli HTML standard e elaborazione lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato. Qualsiasi stile per la casella di controllo del consenso o altri elementi verrebbe ereditato dal tema PrestaShop attivo.

### 4.6 Struttura dei template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

-   `arukereso/views/templates/hook/consent.tpl`
    -   **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop` (a seconda del tema e della versione di PrestaShop, uno di questi renderizzerà il consenso).
    -   **Scopo:** Questo template renderizza l'HTML per la casella di controllo del consenso del cliente durante il processo di checkout. Tipicamente include un'etichetta, l'input della casella di controllo e potenzialmente un link alla politica sulla privacy o maggiori informazioni su Arukereso.hu.
    -   **Output:** Un piccolo elemento del modulo che consente al cliente di aderire al programma di sondaggio.
-   `arukereso/views/templates/hook/displayOrderConfirmation.tpl`
    -   **Hook:** `displayOrderConfirmation`
    -   **Scopo:** Questo template viene renderizzato sulla pagina di conferma dell'ordine dopo un acquisto riuscito. Potrebbe visualizzare un messaggio al cliente che conferma la sua partecipazione al programma di sondaggio (se è stato dato il consenso) o fornire informazioni sul sondaggio imminente.
    -   **Output:** Un piccolo blocco informativo sulla pagina di conferma dell'ordine.

#### Template di amministrazione (`views/templates/admin/`)

Questo modulo **non** contiene alcun template di amministrazione personalizzato oltre a quanto renderizzato da `getContent()` nel file principale del modulo.

#### Template front-office (`views/templates/front/`)

Questo modulo **non** contiene alcun template di pagina front-office autonomo dedicato.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Questo modulo **non** crea tabelle di database personalizzate. Tutte le sue impostazioni di configurazione sono archiviate nella tabella `ps_configuration` di PrestaShop utilizzando le seguenti chiavi:

-   `ARUKERESO_FILE_LOG`: Memorizza il valore booleano per la registrazione degli errori.
-   `ARUKERESO_ID`: Memorizza la WebApiKey di Arukereso.hu.
-   `ARUKERESO_PRODUCT_ID`: Memorizza il tipo di identificatore del prodotto scelto (es. 'id\_product', 'reference').
-   `ARUKERESO_CONSENT`: Memorizza il valore booleano per la richiesta del consenso del cliente.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Una chiave di configurazione standard di PrestaShop, non gestita direttamente da questo modulo ma potenzialmente utilizzata per la gestione delle lingue nel back office.

#### Tabella degli hook registrati

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayGDPRConsent` | Durante il checkout, tipicamente vicino al consenso sulla privacy. | Renderizza la casella di controllo per il consenso del cliente alla partecipazione al sondaggio Arukereso.hu. |
| `actionDeleteGDPRCustomer` | Attivato quando un cliente richiede la cancellazione dei dati tramite il modulo GDPR di PrestaShop. | Gestisce la cancellazione di eventuali dati specifici del cliente memorizzati dal modulo (es. stato del consenso). |
| `actionExportGDPRData` | Attivato quando un cliente richiede l'esportazione dei dati tramite il modulo GDPR di PrestaShop. | Fornisce eventuali dati specifici del cliente memorizzati dal modulo per l'esportazione. |
| `displayOrderConfirmation` | Sulla pagina di conferma dell'ordine dopo un acquisto riuscito. | Renderizza un messaggio informativo al cliente e, in modo cruciale, invia i dati dell'ordine all'API di Arukereso.hu se il consenso è stato dato. |
| `displayPaymentTop` | Nella parte superiore della sezione di pagamento durante il checkout. | Hook alternativo per il rendering della casella di controllo del consenso del cliente, a seconda del tema. |
| `displayCheckoutSummaryTop` | Nella parte superiore della sezione di riepilogo del checkout. | Hook alternativo per il rendering della casella di controllo del consenso del cliente, a seconda del tema. |
| `DisplayGDPRConsent` | (Alias/Versione precedente di `displayGDPRConsent`) | Renderizza la casella di controllo per il consenso del cliente. |
| `DisplayPaymentTop` | (Alias/Versione precedente di `displayPaymentTop`) | Renderizza la casella di controllo per il consenso del cliente. |
| `DisplayOrderConfirmation` | (Alias/Versione precedente di `displayOrderConfirmation`) | Renderizza informazioni e invia i dati dell'ordine. |
| `ActionDeleteGDPRCustomer` | (Alias/Versione precedente di `actionDeleteGDPRCustomer`) | Gestisce la cancellazione dei dati del cliente. |
| `ActionExportGDPRData` | (Alias/Versione precedente di `actionExportGDPRData`) | Gestisce l'esportazione dei dati del cliente. |
| `DisplayCheckoutSummaryTop` | (Alias/Versione precedente di `displayCheckoutSummaryTop`) | Renderizza la casella di controllo per il consenso del cliente. |

La logica principale del modulo per l'invio dei dati dell'ordine ad Arukereso.hu risiede nel metodo `hookDisplayOrderConfirmation` in `arukereso.php`. Questo metodo verifica il consenso del cliente (se richiesto) e quindi costruisce e invia una richiesta HTTP all'API di Arukereso.hu con i dettagli dell'ordine.

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema tecnico o domanda che tu possa avere riguardo al modulo Arukereso.hu - email di sondaggio del programma di acquisto fidato.
