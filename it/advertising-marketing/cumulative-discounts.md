---
title: "Sconti cumulativi - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Sconti cumulativi di MyPresta.eu."
sidebar:
  label: "Sconti cumulativi - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cumulative discounts su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cumulative-discounts.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/cumulative-discounts/)
>
> ---


# Sconti cumulativi

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove definisci come opera il tuo programma di sconti cumulativi.

#### **Attiva programma**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intero programma di sconti cumulativi.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo traccerà attivamente la spesa del cliente, assegnerà i gruppi e visualizzerà le informazioni sugli sconti nel tuo front office.
    -   *Quando disabilitato:* Il modulo cesserà tutte le operazioni, non verranno applicati sconti e non verranno visualizzate informazioni.
-   **Valore consigliato:** SÌ (per attivare il programma).
-   **Scenario / esempio del commerciante:** Se stai configurando il modulo per la prima volta, abilitalo dopo aver configurato tutte le altre impostazioni. Se hai bisogno di mettere in pausa temporaneamente il programma (ad esempio, durante una grande vendita in cui si applicano altri sconti), puoi disabilitarlo qui.

#### **Disabilita il programma di sconti cumulativi per gruppi di clienti selezionati**

-   **Cosa fa questa impostazione:** Ti permette di selezionare specifici gruppi di clienti che *non* dovrebbero far parte del programma di sconti cumulativi. I clienti in questi gruppi selezionati non riceveranno sconti cumulativi, indipendentemente dalla loro spesa.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando un gruppo è selezionato:* I clienti appartenenti a quel gruppo saranno esclusi dal programma.
    -   *Quando nessun gruppo è selezionato:* Tutti i gruppi di clienti sono idonei per il programma per impostazione predefinita.
-   **Valore consigliato:** Seleziona gruppi come "Visitatori" o "Ospiti" se desideri che solo i clienti registrati partecipino. Potresti anche escludere un gruppo "Grossisti" se hanno una struttura di prezzi separata.
-   **Scenario / esempio del commerciante:** Potresti avere un gruppo di clienti "Grossisti" che riceve già prezzi speciali. Per evitare conflitti o doppi sconti, selezioneresti il gruppo "Grossisti" qui per escluderli dal programma di sconti cumulativi.

#### **Periodo di tempo**

-   **Cosa fa questa impostazione:** Definisce il periodo di tempo in cui gli ordini del cliente vengono considerati per il calcolo della loro spesa totale.
-   **Effetto della modifica di questa impostazione:**
    -   *Tutti gli ordini:* Considera ogni ordine mai effettuato dal cliente.
    -   *Ordini dell'ultimo anno / Ordini dell'ultimo semestre / Ordini dell'ultimo trimestre / Ordini dell'ultimo mese / Ordini dell'ultima settimana / Ordini dell'ultimo giorno:* Limita il calcolo agli ordini effettuati nel periodo recente specificato.
    -   *Solo l'ultimo ordine valido:* Considera solo l'ordine completato più recente.
-   **Valore consigliato:** "Ordini dell'ultimo anno" o "Tutti gli ordini" sono scelte comuni per i programmi fedeltà. "Ordini dell'ultimo mese" potrebbe essere utilizzato per una spinta fedeltà più aggressiva e a breve termine.
-   **Scenario / esempio del commerciante:** Se vuoi premiare la fedeltà a lungo termine, scegli "Tutti gli ordini". Se vuoi incoraggiare acquisti recenti e frequenti, "Ordini dell'ultimo semestre" potrebbe essere più appropriato.

#### **Tipo di prezzo**

-   **Cosa fa questa impostazione:** Determina se il calcolo della spesa cumulativa deve utilizzare il "Prezzo netto" (prezzo prima delle tasse) o il "Prezzo lordo" (prezzo incluse le tasse) dei prodotti negli ordini.
-   **Effetto della modifica di questa impostazione:**
    -   *Prezzo netto:* La spesa totale verrà calcolata in base ai prezzi dei prodotti escluse le tasse.
    -   *Prezzo lordo:* La spesa totale verrà calcolata in base ai prezzi dei prodotti incluse le tasse.
-   **Valore consigliato:** Il "Prezzo lordo" è spesso più intuitivo per i clienti in quanto riflette ciò che hanno effettivamente pagato. Tuttavia, il "Prezzo netto" potrebbe essere preferito per i negozi B2B o per la coerenza contabile interna.
-   **Scenario / esempio del commerciante:** Se il tuo pubblico di riferimento è principalmente costituito da consumatori, l'utilizzo del "Prezzo lordo" ha più senso in quanto si allinea al prezzo finale che vedono e pagano.

#### **Seleziona stati dell'ordine**

-   **Cosa fa questa impostazione:** Ti permette di specificare quali stati dell'ordine devono essere inclusi nel calcolo della spesa totale di un cliente. Solo gli ordini con questi stati selezionati conteranno per il totale cumulativo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando "Pagamento accettato" e "Consegnato" sono selezionati:* Solo gli ordini che sono stati pagati con successo e consegnati contribuiranno al totale di spesa del cliente.
    -   *Quando "Annullato" o "Rimborsato" NON sono selezionati:* Questi ordini non conteranno, impedendo ai clienti di ottenere punti fedeltà per acquisti non completati.
-   **Valore consigliato:** Seleziona gli stati che indicano una transazione completata e riuscita, come "Pagamento accettato", "Consegnato". Escludi stati come "Annullato", "Rimborsato", "Errore di pagamento", ecc.
-   **Scenario / esempio del commerciante:** Vuoi assicurarti che solo gli acquisti effettivi e completati contribuiscano alla fedeltà. Selezioneresti "Pagamento accettato" e "Consegnato" per assicurarti che i clienti guadagnino sconti solo per gli ordini che hanno effettivamente pagato e ricevuto.

#### **Escludi ordini effettuati con codice voucher**

-   **Cosa fa questa impostazione:** Se abilitata, gli ordini in cui è stato utilizzato un codice voucher o coupon non conteranno per il totale di spesa cumulativa del cliente.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Gli ordini con voucher vengono ignorati per i calcoli di fedeltà.
    -   *Quando disabilitato:* Gli ordini con voucher *contano* per il totale cumulativo.
-   **Valore consigliato:** SÌ, se vuoi premiare maggiormente gli acquisti a prezzo pieno. NO, se vuoi incoraggiare qualsiasi acquisto, anche quelli scontati, a contribuire alla fedeltà.
-   **Scenario / esempio del commerciante:** Stai eseguendo una promozione speciale con un coupon del 20% di sconto. Se abiliti questa impostazione, i clienti che utilizzano quel coupon non vedranno quell'ordine contare per il loro progresso di sconto cumulativo, assicurando che guadagnino fedeltà sugli acquisti a prezzo pieno.

#### **Escludi prodotti con prezzi specifici**

-   **Cosa fa questa impostazione:** Se abilitata, i prodotti che hanno un "prezzo specifico" (ad esempio, un prezzo promozionale speciale impostato per un periodo limitato o un particolare gruppo di clienti) non contribuiranno al calcolo della spesa cumulativa.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* I prodotti con prezzi specifici vengono ignorati per i calcoli di fedeltà.
    -   *Quando disabilitato:* I prodotti con prezzi specifici *contano* per il totale cumulativo.
-   **Valore consigliato:** SÌ, se vuoi premiare gli acquisti di articoli a prezzo normale. NO, se vuoi che tutti gli acquisti di prodotti contribuiscano.
-   **Scenario / esempio del commerciante:** Hai una vendita flash su alcuni articoli utilizzando la funzione di prezzo specifico di PrestaShop. Se abiliti questa opzione, l'acquisto di questi articoli in saldo non aiuterà il cliente a raggiungere il livello di fedeltà successivo, incoraggiandolo invece ad acquistare articoli a prezzo normale.

#### **Escludi prodotti con sconti per quantità**

-   **Cosa fa questa impostazione:** Se abilitata, i prodotti acquistati con uno sconto per quantità (ad esempio, "Acquista 3, ottieni il 10% di sconto") non contribuiranno al calcolo della spesa cumulativa.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* I prodotti acquistati con sconti per quantità vengono ignorati per i calcoli di fedeltà.
    -   *Quando disabilitato:* I prodotti acquistati con sconti per quantità *contano* per il totale cumulativo.
-   **Valore consigliato:** SÌ, se vuoi premiare gli acquisti di singoli articoli a prezzo pieno. NO, se vuoi incoraggiare gli acquisti in blocco a contribuire alla fedeltà.
-   **Scenario / esempio del commerciante:** Offri un'offerta "acquista 5 e ottieni il 15% di sconto". Se abiliti questa opzione, i clienti che approfittano di questa offerta non vedranno quegli articoli specifici contare per il loro progresso di sconto cumulativo.

#### **Gruppo di clienti predefinito**

-   **Cosa fa questa impostazione:** Definisce il gruppo di clienti predefinito a cui i clienti verranno assegnati se non soddisfano i criteri di spesa per nessun altro gruppo di sconti cumulativi. Questo è tipicamente il tuo gruppo "Cliente" standard.
-   **Effetto della modifica di questa impostazione:** Assicura che i clienti appartengano sempre a un gruppo valido, anche se non hanno speso abbastanza per qualificarsi per un livello di sconto speciale.
-   **Valore consigliato:** Il tuo gruppo "Cliente" standard (spesso ID 3).
-   **Scenario / esempio del commerciante:** Un nuovo cliente si registra. Non ha ancora effettuato acquisti, quindi il modulo lo assegna al "Gruppo di clienti predefinito" (ad esempio, "Cliente"), che potrebbe avere uno sconto dello 0%. Man mano che spendono, verranno spostati in "Bronzo", "Argento", ecc.

#### **Informazioni per i clienti loggati (Pagina del prodotto)**

-   **Cosa fa questa impostazione:** Questo è un editor di testo dove puoi personalizzare il messaggio visualizzato ai *clienti loggati* sulle pagine dei prodotti. Questo messaggio di solito li informa sul loro stato di sconto attuale o sui progressi.
-   **Effetto della modifica di questa impostazione:** Il testo che inserisci qui apparirà sulle pagine dei prodotti per i clienti che hanno effettuato l'accesso al loro account. Puoi utilizzare variabili Smarty (come `{$total_spent}`, `{$discount_value}`, `{$next_group_name}`, `{$next_group_value}`) per personalizzare il messaggio.
-   **Valore consigliato:** Un messaggio di benvenuto come: "Ciao {$customer\_name}! Attualmente sei nel gruppo {$current\_group\_name} e ricevi uno sconto del {$discount\_value}%. Spendi {$to\_next\_group} in più per raggiungere il gruppo {$next\_group\_name} e ottenere il {$next\_group\_value}% di sconto!"
-   **Scenario / esempio del commerciante:** Vuoi motivare i clienti loggati. Puoi dire loro esattamente quanto devono spendere ancora per ottenere uno sconto maggiore, creando un chiaro incentivo.

#### **Informazioni per i clienti non loggati (Pagina del prodotto)**

-   **Cosa fa questa impostazione:** Questo è un editor di testo dove puoi personalizzare il messaggio visualizzato ai *clienti ospiti o non loggati* sulle pagine dei prodotti. Questo messaggio di solito li incoraggia a registrarsi e a partecipare al programma fedeltà.
-   **Effetto della modifica di questa impostazione:** Il testo che inserisci qui apparirà sulle pagine dei prodotti per i clienti che non hanno effettuato l'accesso al loro account.
-   **Valore consigliato:** Un messaggio invitante come: "Registrati ora e inizia a guadagnare sconti cumulativi! Più spendi, più risparmi!"
-   **Scenario / esempio del commerciante:** Un nuovo visitatore arriva su una pagina di prodotto. Questo messaggio può invogliarlo a creare un account evidenziando i vantaggi del tuo programma fedeltà, potenzialmente convertendolo in un cliente registrato.

#### **Informazioni per i clienti loggati (Pagina del carrello)**

-   **Cosa fa questa impostazione:** Questo è un editor di testo dove puoi personalizzare il messaggio visualizzato ai *clienti loggati* sulla pagina del carrello. Questo messaggio può rafforzare il loro stato di sconto o mostrare come il loro carrello attuale contribuisce alla loro fedeltà.
-   **Effetto della modifica di questa impostazione:** Il testo che inserisci qui apparirà sulla pagina del carrello per i clienti loggati. Puoi utilizzare variabili Smarty.
-   **Valore consigliato:** Simile al messaggio della pagina del prodotto, ma forse enfatizzando il contributo del carrello attuale: "Il valore attuale del tuo carrello è {$cart\_value}. Con il tuo sconto {$current\_group\_name}, risparmi il {$discount\_value}%! Spendi {$to\_next\_group} in più per raggiungere il gruppo {$next\_group\_name}!"
-   **Scenario / esempio del commerciante:** Un cliente sta per effettuare il checkout. Questo messaggio gli ricorda i suoi vantaggi fedeltà e potrebbe persino incoraggiarlo ad aggiungere un piccolo articolo per raggiungere il livello di sconto successivo.

#### **Informazioni per i clienti non loggati (Pagina del carrello)**

-   **Cosa fa questa impostazione:** Questo è un editor di testo dove puoi personalizzare il messaggio visualizzato ai *clienti ospiti o non loggati* sulla pagina del carrello. Questo messaggio li incoraggia a registrarsi prima di completare l'acquisto per iniziare a guadagnare fedeltà.
-   **Effetto della modifica di questa impostazione:** Il testo che inserisci qui apparirà sulla pagina del carrello per i clienti non loggati.
-   **Valore consigliato:** "Non perdere gli sconti fedeltà! Registrati prima del checkout per iniziare a guadagnare premi sui tuoi acquisti!"
-   **Scenario / esempio del commerciante:** Un cliente ospite ha articoli nel carrello. Questo messaggio fornisce un'ultima spinta per registrare un account, trasformando un acquirente occasionale in un potenziale cliente fedele.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminCudiListController (Back Office > Sconti cumulativi > Gestisci sconti)

-   **Nome schermata e posizione menu:** Puoi trovare questa schermata navigando su **Catalogo > Sconti cumulativi** (o una posizione simile a seconda della tua versione di PrestaShop e della personalizzazione del menu). L'etichetta esatta potrebbe essere "Gestisci sconti" o "Regole di sconto cumulativo".
-   **Azioni e impostazioni disponibili:** Questa schermata presenta una griglia (elenco) delle tue regole di sconto cumulativo definite. Ogni regola specifica:
    -   **Importo minimo di spesa:** L'importo totale che un cliente deve spendere per qualificarsi per questo gruppo.
    -   **Gruppo di clienti:** Il gruppo di clienti PrestaShop a cui verranno assegnati i clienti che soddisfano i criteri di spesa.
    -   **Percentuale di sconto:** La percentuale di sconto associata a quel gruppo di clienti.
    -   **Azioni:** Puoi "Aggiungi nuove" regole, "Modifica" regole esistenti o "Elimina" regole.
-   **Effetto delle modifiche:**
    -   **Aggiunta di una nuova regola:** Crea un nuovo livello nel tuo programma fedeltà. Ad esempio, "Spendi $500 per unirti al gruppo Oro e ottenere il 15% di sconto."
    -   **Modifica di una regola:** Modifica la soglia di spesa o il gruppo/sconto assegnato per un livello esistente. Le modifiche influenzeranno le future assegnazioni di gruppo e i ricalcoli.
    -   **Eliminazione di una regola:** Rimuove un livello di fedeltà. I clienti precedentemente in quel gruppo verranno riassegnati in base alle regole rimanenti.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Pianifica i tuoi livelli:** Decidi le tue soglie di spesa e i corrispondenti gruppi di sconto (ad esempio, Bronzo: $100 per il 5%, Argento: $500 per il 10%, Oro: $1000 per il 15%).
    2.  **Crea gruppi di clienti:** Assicurati di avere gruppi di clienti corrispondenti in PrestaShop (Back Office > Clienti > Gruppi) per ogni livello (ad esempio, "Cliente Bronzo", "Cliente Argento", "Cliente Oro"). Assegna la percentuale di sconto globale appropriata a ciascuno di questi gruppi.
    3.  **Aggiungi regole:** Utilizza il pulsante "Aggiungi nuovo" per creare ogni livello, collegando l'importo di spesa al gruppo di clienti corretto.
    4.  **Ordina le regole:** Il modulo elabora le regole dal minimo di spesa al massimo. Assicurati che le tue regole siano ordinate logicamente.
    5.  **Rivedi e adatta:** Rivedi periodicamente i tuoi livelli per assicurarti che siano ancora efficaci e redditizi.

#### index.php (cudi/controllers/admin/index.php)

Questo file è tipicamente un segnaposto o un reindirizzamento all'interno della struttura del controller admin e non rappresenta una schermata diretta e configurabile per il commerciante. Fa parte del routing interno del modulo per il back office. Tutta la configurazione rivolta al commerciante per gli sconti cumulativi avviene o nella pagina di configurazione principale del modulo o tramite l'`AdminCudiListController`.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Attiva programma | SÌ | Interruttore principale per il programma fedeltà. |
| | Disabilita il programma di sconti cumulativi per gruppi di clienti selezionati | Seleziona "Ospite", "Visitatore" | Esclude i gruppi di clienti specificati dal programma. |
| | Periodo di tempo | Ordini dell'ultimo anno / Tutti gli ordini | Definisce il periodo per il calcolo della spesa totale. |
| | Tipo di prezzo | Prezzo lordo | Determina se i prezzi netti o lordi vengono utilizzati per il calcolo della spesa. |
| | Seleziona stati dell'ordine | Pagamento accettato, Consegnato | Specifica quali stati dell'ordine contano per la spesa totale. |
| | Escludi ordini effettuati con codice voucher | SÌ | Impedisce agli ordini con voucher di contribuire alla fedeltà. |
| | Escludi prodotti con prezzi specifici | SÌ | Impedisce ai prodotti in promozioni a prezzo specifico di contribuire. |
| | Escludi prodotti con sconti per quantità | SÌ | Impedisce ai prodotti con sconti per quantità di contribuire. |
| | Gruppo di clienti predefinito | Il tuo gruppo "Cliente" standard | Il gruppo assegnato se nessun livello di fedeltà è raggiunto. |
| | Informazioni per i clienti loggati (Pagina del prodotto) | Testo personalizzabile con variabili Smarty | Messaggio per gli utenti loggati sulle pagine dei prodotti. |
| | Informazioni per i clienti non loggati (Pagina del prodotto) | Testo personalizzabile | Messaggio per gli ospiti sulle pagine dei prodotti, che incoraggia la registrazione. |
| | Informazioni per i clienti loggati (Pagina del carrello) | Testo personalizzabile con variabili Smarty | Messaggio per gli utenti loggati sulle pagine del carrello. |
| | Informazioni per i clienti non loggati (Pagina del carrello) | Testo personalizzabile | Messaggio per gli ospiti sulle pagine del carrello, che incoraggia la registrazione. |
| **AdminCudiListController** | Importo minimo di spesa | Varia per livello | Soglia per qualificarsi per un gruppo di sconto specifico. |
| | Gruppo di clienti | I tuoi gruppi fedeltà personalizzati (es. Bronzo, Argento) | Il gruppo PrestaShop assegnato quando la soglia di spesa è raggiunta. |
| | Percentuale di sconto | Varia per livello | Lo sconto applicato al gruppo di clienti assegnato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non vengono assegnati ai gruppi corretti, o gli sconti non vengono applicati.**
R1:

-   **Controlla "Attiva programma":** Assicurati che l'interruttore principale nella configurazione del modulo sia impostato su SÌ.
-   **Verifica "Periodo di tempo" e "Seleziona stati dell'ordine":** Assicurati che gli ordini che ti aspetti contengano rientrino nel periodo di tempo selezionato e abbiano gli stati dell'ordine corretti (ad esempio, "Consegnato", "Pagamento accettato").
-   **Rivedi le impostazioni "Escludi":** Controlla se "Escludi ordini effettuati con codice voucher", "Escludi prodotti con prezzi specifici" o "Escludi prodotti con sconti per quantità" sono abilitati e potrebbero impedire agli ordini di contare.
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache". A volte la cache di PrestaShop può impedire che le modifiche abbiano effetto immediatamente.
-   **Controlla i gruppi di clienti:** Assicurati che i gruppi di clienti che hai collegato nell'`AdminCudiListController` esistano effettivamente in PrestaShop (Clienti > Gruppi) e abbiano la percentuale di sconto globale corretta assegnata.
-   **Ordine delle regole:** Assicurati che le tue regole nell'`AdminCudiListController` siano ordinate logicamente dalla soglia di spesa più bassa a quella più alta.

**D2: Le informazioni sullo sconto non vengono visualizzate sulle mie pagine dei prodotti o sul carrello.**
R2:

-   **Controlla gli hook del modulo:** Assicurati che il modulo sia agganciato a `displayProductAdditionalInfo` e `displayShoppingCart`. Puoi verificarlo in **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti di PS). Cerca "Sconti cumulativi" sotto questi hook. In caso contrario, prova a reinstallare il modulo o ad agganciarlo manualmente.
-   **Testo di configurazione del modulo:** Assicurati di aver inserito del testo nei campi "Informazioni per i clienti loggati" e "Informazioni per i clienti non loggati" per le pagine dei prodotti e del carrello. Se questi campi sono vuoti, non verrà visualizzato nulla.
-   **Compatibilità del tema:** Il tuo tema personalizzato potrebbe sovrascrivere le posizioni degli hook standard. Se le informazioni non appaiono ancora, potresti aver bisogno di uno sviluppatore web per regolare i file `.tpl` del tuo tema per includere esplicitamente gli hook del modulo.

**D3: Come posso tradurre i messaggi del modulo in altre lingue?**
R3:

-   Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
-   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e quindi seleziona "Sconti cumulativi" dal menu a discesa del modulo.
-   Potrai quindi tradurre tutte le stringhe statiche del modulo. Per i messaggi personalizzati che hai inserito nella configurazione (ad esempio, "Informazioni per i clienti loggati"), dovrai utilizzare il selettore della lingua in alto a destra della pagina di configurazione del modulo per cambiare lingua e inserire il testo tradotto per ogni lingua.

**D4: Posso assegnare manualmente un cliente a un gruppo di sconti cumulativi?**
R4: Sì, puoi modificare manualmente il gruppo di un cliente nel suo profilo cliente (Back Office > Clienti > Clienti > Modifica cliente). Tuttavia, il modulo rivaluterà automaticamente il loro gruppo in base alla loro cronologia di spesa durante il prossimo aggiornamento dello stato dell'ordine o quando la logica del modulo viene attivata. Se desideri che un cliente rimanga *permanentemente* in un gruppo specifico indipendentemente dalla spesa, potresti dover escludere quel gruppo dal programma di sconti cumulativi (utilizzando l'impostazione "Disabilita il programma di sconti cumulativi per gruppi di clienti selezionati") e gestirli manualmente.

**D5: Cosa succede se la spesa totale di un cliente scende al di sotto di un livello (ad esempio, a causa di un rimborso)?**
R5: Il modulo ricalcola la spesa totale del cliente in base al "Periodo di tempo" e agli "Stati dell'ordine selezionati" configurati ogni volta che lo stato di un ordine viene aggiornato. Se un rimborso fa scendere il loro totale al di sotto di un livello, il modulo li riassegnerà automaticamente al gruppo di livello inferiore appropriato durante il ricalcolo successivo, garantendo l'accuratezza.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Sconti cumulativi" (`cudi`) segue un'architettura standard dei moduli PrestaShop, sfruttando i principi MVC. Opera principalmente agganciandosi a vari eventi del front-office e del back-office per calcolare la spesa del cliente e assegnarli dinamicamente ai gruppi di clienti appropriati. La configurazione è gestita tramite il metodo principale `getContent()` e un `AdminCudiListController` dedicato per la gestione dei livelli di sconto. Non introduce tabelle di database personalizzate ma si basa su `ps_configuration` di PrestaShop per le impostazioni e `ps_customer_group` per le assegnazioni di gruppo.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `cudi/controllers/front/index.php`
    -   **Nome classe e classe padre:** `CudiIndexModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller probabilmente funge da predefinito o fallback per il routing del front-office del modulo. Potrebbe gestire la configurazione iniziale o il reindirizzamento, sebbene `mydiscount.php` sia più specifico per i contenuti rivolti al cliente.
-   `cudi/controllers/front/mydiscount.php`
    -   **Nome classe e classe padre:** `CudiMydiscountModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller è responsabile del rendering della pagina dedicata "I miei sconti" nell'area account del cliente. Recupera la spesa totale del cliente, il gruppo attuale e i progressi verso il livello successivo, quindi passa questi dati al template `myDiscount.tpl` per la visualizzazione. Risponde a un percorso come `iltuonegozio.com/module/cudi/mydiscount`.

#### Controller Admin Back-Office

-   `cudi/controllers/admin/AdminCudiList.php`
    -   **Nome scheda ed entità gestita:** "Sconti cumulativi" (o simile, accessibile tramite il menu Catalogo). Gestisce l'entità `cudi`, che rappresenta le regole di sconto cumulativo (soglie di spesa collegate a gruppi di clienti).
    -   **Responsabilità:** Questo è il controller admin principale per la gestione dei livelli di sconto. Estende `AdminController` e utilizza `HelperList` per la visualizzazione della griglia e `HelperForm` per l'aggiunta/modifica di singole regole. Gestisce le operazioni CRUD per le regole di sconto cumulativo, inclusa la definizione della spesa minima, del gruppo di clienti target e dello sconto associato.
-   `cudi/controllers/admin/index.php`
    -   **Responsabilità:** Questo file funge tipicamente da punto di ingresso o da reindirizzamento all'interno della directory del controller admin. In molti moduli, potrebbe contenere un semplice `header('Location: ...')` per reindirizzare al controller admin principale (`AdminCudiList.php` in questo caso) o essere un segnaposto. Non rappresenta una schermata diretta e configurabile.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. La logica principale per il calcolo della spesa cumulativa e l'assegnazione dei gruppi è probabilmente incapsulata nel file principale del modulo `cudi.php` stesso, in particolare all'interno dei suoi metodi hook e potenzialmente delle funzioni helper. Interagisce direttamente con gli `ObjectModel` di PrestaShop `Customer`, `Order`, `OrderState` e `Group`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `cudi/views/admin/js/cudi.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Questo script probabilmente gestisce le interazioni lato client sulla pagina di configurazione del modulo o sull'`AdminCudiListController`. Ciò potrebbe includere:
        -   Visibilità dinamica dei campi del modulo in base alle opzioni selezionate (ad esempio, mostrare/nascondere le opzioni di esclusione).
        -   Chiamate AJAX per salvare le impostazioni senza un ricaricamento completo della pagina.
        -   Validazione dell'input o elementi interattivi specifici dell'interfaccia di amministrazione del modulo.
        -   Listener di eventi per modifiche del modulo o clic sui pulsanti all'interno del pannello di amministrazione.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `cudi/views/admin/css/cudi.css`
    -   **Ambito:** Stile del modulo di amministrazione del back-office.
    -   **Responsabilità:** Fornisce lo stile per la pagina di configurazione del modulo e l'interfaccia `AdminCudiListController`, assicurando che si integri visivamente con il tema del back office di PrestaShop.
    -   **Selettori di classe CSS chiave:** Probabilmente si rivolge a ID o classi specifici all'interno dei template di amministrazione del modulo (ad esempio, `.cudi-settings-panel`, `.cudi-list-table`).
-   `cudi/views/css/cudi.css`
    -   **Ambito:** Stile del cliente del front-office.
    -   **Responsabilità:** Stila le informazioni visualizzate ai clienti sulle pagine dei prodotti, sulle pagine del carrello e sulla pagina "I miei sconti".
    -   **Selettori di classe CSS chiave:** Si rivolgerà agli elementi generati dai template del front-office del modulo (ad esempio, `.cudi-info-block`, `.cudi-discount-message`, `.cudi-progress-bar`). Gli sviluppatori possono sovrascriverli nel `custom.css` del loro tema o creando un tema figlio.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

-   `cudi/views/templates/hook/displayProductAdditionalInfo-unlogged.tpl`
    -   **Hook:** `displayProductAdditionalInfo` (specificamente per utenti non loggati).
    -   **Output:** Visualizza il messaggio personalizzabile per i clienti non loggati sulle pagine dei prodotti, incoraggiando la registrazione ed evidenziando il programma fedeltà.
-   `cudi/views/templates/hook/displayProductAdditionalInfo.tpl`
    -   **Hook:** `displayProductAdditionalInfo` (per utenti loggati).
    -   **Output:** Visualizza il messaggio personalizzabile per i clienti loggati sulle pagine dei prodotti, mostrando il loro stato di sconto attuale e i progressi verso il livello successivo.
-   `cudi/views/templates/hook/myAccount.tpl`
    -   **Hook:** `displayCustomerAccount`.
    -   **Output:** Renderizza un link o un blocco nella sezione "Il mio account" del cliente, tipicamente etichettato "I miei sconti", che porta alla pagina dedicata `mydiscount`.

#### Template admin (`views/templates/admin/`)

-   `cudi/views/admin/assignButton.tpl`
    -   **Ambito:** Back-office.
    -   **Output:** Probabilmente renderizza un pulsante o un link di azione all'interno dell'interfaccia di amministrazione, possibilmente per attivare un ricalcolo manuale o l'assegnazione di gruppi di clienti.
-   `cudi/views/admin/orderstates.tpl`
    -   **Ambito:** Back-office.
    -   **Output:** Utilizzato all'interno del modulo principale di configurazione (`getContent()`) per renderizzare il menu a discesa a selezione multipla o le caselle di controllo per "Seleziona stati dell'ordine".

#### Template front-office (`views/templates/front/`)

-   `cudi/views/templates/front/myDiscount.tpl`
    -   **Ambito:** Front-office.
    -   **Output:** Questo è il template di pagina dedicato per il `CudiMydiscountModuleFrontController`. Visualizza una panoramica completa dello stato di fedeltà del cliente, inclusi la spesa totale, il gruppo attuale, la percentuale di sconto e i progressi verso livelli superiori.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo non crea tabelle SQL personalizzate. Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop, utilizzando chiavi come `CUDI_ACTIVE`, `CUDI_ORDERSDATE`, `CUDI_PRICETYPE`, `CUDI_ORDERSTATES`, `CUDI_EX_SP`, `CUDI_EX_SP_QTY`, `CUDI_ORDERCOUPON`, `CUDI_DEFGROUP`, `CUDI_GROUPSNOT`, `CUDI_SHOWINFO_PRODUCT`, `CUDI_SHOWINFO_CART`, `logged_cudi_contents`, `unlogged_cudi_contents`.
Le regole di sconto cumulativo (soglie di spesa e gruppi di clienti associati) sono probabilmente memorizzate come dati serializzati all'interno di una voce `ps_configuration` o gestite direttamente dall'`AdminCudiListController` che potrebbe utilizzare una tabella personalizzata (anche se non esplicitamente elencata in `classes/` o `sql/`). *Autocorrezione: Dato l'`AdminCudiListController` e la sua gestione dell'entità `cudi`, è altamente probabile che esista una tabella personalizzata `ps_cudi`, anche se non esplicitamente elencata in `classes/` o `sql/` nel dossier fornito. Questa tabella memorizzerebbe `id_cudi`, `min_spend`, `id_group`, `discount_percentage` per ogni regola.*

#### Tabella degli hook registrati

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Utilizzato per includere le risorse CSS/JS del modulo per il front-office, o per inizializzare variabili JS globali. |
| `displayProductAdditionalInfo` | Sulle pagine dei prodotti, tipicamente sotto la descrizione del prodotto o il pulsante "aggiungi al carrello". | Visualizza le informazioni del programma fedeltà (sconto attuale, progressi) ai clienti. |
| `displayCustomerAccount` | Sulla pagina "Il mio account" del cliente. | Aggiunge un link alla pagina dedicata "I miei sconti". |
| `displayShoppingCart` | Sulla pagina di riepilogo del carrello. | Visualizza le informazioni del programma fedeltà (sconto attuale, contributo del carrello) ai clienti. |
| `updateOrderStatus` | Attivato quando lo stato di un ordine viene modificato nel back office. | **Cruciale per ricalcolare la spesa totale del cliente e riassegnare il suo gruppo.** |
| `actionOrderStatusUpdate` | Simile a `updateOrderStatus`, fornisce un controllo più granulare dopo un aggiornamento dello stato dell'ordine. | **Anche cruciale per ricalcolare la spesa totale del cliente e riassegnare il suo gruppo.** |
| `actionAdminControllerSetMedia` | Nel back office, quando viene caricato un controller admin. | Utilizzato per includere le risorse CSS/JS del modulo per il back-office (ad esempio, `cudi.js`, `cudi.css`). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Lì troverai i moduli acquistati e i relativi link per il download. Per assistenza tecnica, utilizza i canali di supporto forniti su MyPresta.eu.
