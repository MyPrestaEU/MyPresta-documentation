---
title: "Voucher per commenti sui prodotti - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Voucher per commenti sui prodotti di MyPresta.eu."
sidebar:
  label: "Voucher per commenti sui prodotti - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Voucher for product comment su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-product-comment.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/voucher-for-product-comment/)
>
> ---


# Voucher per commenti sui prodotti

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il corretto funzionamento di PrestaShop. Non sono necessarie estensioni aggiuntive specifiche per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è l'area di configurazione principale per il modulo "Voucher per commenti sui prodotti". Qui troverai tutte le impostazioni relative ai promemoria per i commenti e alla generazione di voucher.

#### **Impostazioni promemoria commenti**

-   **Chiedi il permesso di inviare promemoria**

    -   **Cosa fa questa impostazione:** Se abilitata, apparirà una casella di controllo sui moduli di registrazione e aggiornamento dell'identità del cliente (Il mio account > Informazioni) che chiederà ai clienti se accettano di ricevere promemoria per i commenti. Questo è importante per la conformità al GDPR e per il rispetto della privacy del cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti devono esplicitamente acconsentire a ricevere promemoria. Solo i clienti che selezionano questa casella riceveranno email di promemoria.
        -   *Quando disabilitato:* Tutti i clienti che soddisfano altri criteri (es. prodotti acquistati, non hanno commentato) riceveranno promemoria, senza un'esplicita accettazione.
    -   **Valore consigliato:** SÌ (Altamente raccomandato per la conformità al GDPR e migliori relazioni con i clienti).
    -   **Scenario / esempio del commerciante:** Vuoi assicurarti che le tue pratiche di marketing siano conformi alle normative sulla protezione dei dati. Abilitando questa opzione, i clienti hanno il controllo sulle loro preferenze di comunicazione.
-   **Invia promemoria commento**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per la funzione di promemoria commenti. Se disabilitato, nessuna email di promemoria commenti verrà inviata, indipendentemente dalle altre impostazioni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo invierà attivamente email di promemoria in base alle altre impostazioni.
        -   *Quando disabilitato:* Nessuna email di promemoria verrà inviata.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Hai deciso di raccogliere attivamente più recensioni e vuoi iniziare a inviare promemoria.
-   **Ricorda i commenti dopo:**

    -   **Cosa fa questa impostazione:** Definisce il numero di giorni dopo che un ordine raggiunge uno stato specifico (definito di seguito) in cui verrà inviata la prima email di promemoria commento.
    -   **Effetto della modifica di questa impostazione:**
        -   *Modificando il numero:* Determina il ritardo. Un ritardo più breve significa che i clienti ricevono i promemoria prima; un ritardo più lungo dà loro più tempo prima di essere sollecitati.
    -   **Valore consigliato:** 7 giorni (Dà ai clienti abbastanza tempo per ricevere e utilizzare il prodotto).
    -   **Scenario / esempio del commerciante:** Vuoi dare ai clienti una settimana per ricevere il loro prodotto e formarsi un'opinione prima di chiedere una recensione.
-   **Ripeti promemoria**

    -   **Cosa fa questa impostazione:** Se un cliente non ha ancora lasciato un commento dopo il promemoria iniziale, questa impostazione determina se e quando deve essere inviato un secondo promemoria.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando un numero (es. 14):* Un secondo promemoria verrà inviato 14 giorni dopo il *primo* promemoria, se non è stato lasciato alcun commento.
        -   *Impostando a 0 o lasciando vuoto:* Nessun secondo promemoria verrà inviato.
    -   **Valore consigliato:** 14 (Fornisce un gentile follow-up senza essere troppo aggressivo).
    -   **Scenario / esempio del commerciante:** Alcuni clienti potrebbero perdere la prima email o semplicemente dimenticare. Un secondo promemoria dopo due settimane può catturare nuovamente la loro attenzione.
-   **Titolo email**

    -   **Cosa fa questa impostazione:** Ti permette di personalizzare l'oggetto delle email di promemoria commenti. Questo è cruciale per i tassi di apertura delle email.
    -   **Effetto della modifica di questa impostazione:**
        -   *Modificando il testo:* Cambia direttamente l'oggetto che i clienti vedono nella loro casella di posta.
    -   **Valore consigliato:** "Ci piacerebbe sentire la tua opinione sul tuo recente acquisto!" o "Condividi la tua esperienza e aiuta altri acquirenti!"
    -   **Scenario / esempio del commerciante:** Vuoi rendere l'oggetto dell'email coinvolgente e chiaro, incoraggiando i clienti ad aprirla.
-   **Seleziona stati ordine**

    -   **Cosa fa questa impostazione:** Determina quali stati dell'ordine attivano il processo di promemoria commenti. I promemoria verranno inviati solo per i prodotti di ordini che hanno raggiunto uno degli stati selezionati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Selezionando stati (es. "Consegnato"):* I promemoria verranno inviati solo per gli ordini contrassegnati come consegnati.
        -   *Non selezionando uno stato pertinente:* I promemoria potrebbero non essere inviati al momento opportuno (es. se selezioni solo "Pagamento accettato" ma i prodotti non sono ancora stati spediti).
    -   **Valore consigliato:** "Consegnato" (Questo assicura che i clienti abbiano ricevuto i loro prodotti prima di essere invitati a recensirli).
    -   **Scenario / esempio del commerciante:** Vuoi chiedere recensioni solo dopo che il cliente ha effettivamente ricevuto il suo ordine, quindi selezioni "Consegnato" e "Spedito".
-   **Gruppo di clienti (per Promemoria)**

    -   **Cosa fa questa impostazione:** Ti permette di targettizzare specifici gruppi di clienti per i promemoria commenti. Solo i clienti appartenenti ai gruppi selezionati riceveranno promemoria.
    -   **Effetto della modifica di questa impostazione:**
        -   *Selezionando gruppi (es. "Clienti"):* Solo i clienti nel gruppo "Clienti" riceveranno promemoria.
        -   *Non selezionando alcun gruppo:* I promemoria verranno inviati a tutti i clienti (a meno che non si applichino altri filtri).
    -   **Valore consigliato:** "Clienti" (Tipicamente, vuoi ricordare a tutti i tuoi clienti abituali).
    -   **Scenario / esempio del commerciante:** Hai un gruppo di clienti "VIP" speciale e vuoi inviare loro promemoria personalizzati, oppure vuoi escludere i clienti all'ingrosso dai promemoria.
-   **Invia promemoria sui commenti per i prodotti degli ordini:**

    -   **Cosa fa questa impostazione:** Questo è un filtro per data. I promemoria verranno inviati solo per i prodotti acquistati in ordini effettuati *dopo* questa data specificata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando una data:* Impedisce l'invio di promemoria per ordini molto vecchi, concentrandosi sugli acquisti recenti.
        -   *Lasciando vuoto:* I promemoria potrebbero potenzialmente essere inviati per tutti gli ordini passati, il che potrebbe non essere desiderabile.
    -   **Valore consigliato:** Imposta una data recente, o la data di installazione del modulo, per evitare di spammare vecchi clienti.
    -   **Scenario / esempio del commerciante:** Hai appena installato il modulo e non vuoi inviare promemoria per ordini di un anno fa; ti interessano solo gli ordini degli ultimi 3 mesi.
-   **Dimensione immagine per le foto dei prodotti**

    -   **Cosa fa questa impostazione:** Determina la dimensione delle immagini dei prodotti incluse nelle email di promemoria.
    -   **Effetto della modifica di questa impostazione:**
        -   *Selezionando una dimensione (es. "home\_default"):* Le immagini dei prodotti nell'email verranno renderizzate a quella dimensione specifica, influenzando il layout dell'email e il tempo di caricamento.
    -   **Valore consigliato:** "home\_default" o "small\_default" (Un'immagine di medie dimensioni che abbia un bell'aspetto senza rendere l'email troppo pesante).
    -   **Scenario / esempio del commerciante:** Vuoi che le immagini dei prodotti nelle tue email di promemoria siano chiare ma non eccessivamente grandi, quindi scegli una dimensione immagine adatta definita nel tuo tema.

#### **Impostazioni di generazione voucher**

-   **Invia codice voucher per commento**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per la funzione di generazione voucher. Se disabilitato, nessun voucher verrà generato o inviato, anche se vengono lasciati commenti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo genererà e invierà un codice voucher unico ai clienti che lasciano un commento sul prodotto.
        -   *Quando disabilitato:* Nessun voucher verrà inviato.
    -   **Valore consigliato:** SÌ (Questa è una funzionalità fondamentale per incentivare i commenti).
    -   **Scenario / esempio del commerciante:** Vuoi premiare i clienti per il loro impegno nel lasciare una recensione, incoraggiandoli a fare nuovamente acquisti.
-   **Invia voucher solo ai clienti che hanno acquistato il prodotto**

    -   **Cosa fa questa impostazione:** Se abilitata, un voucher verrà inviato *solo* se il cliente che ha lasciato il commento ha anche acquistato il prodotto. Questo impedisce a persone che non hanno acquistato dal tuo negozio di ottenere voucher semplicemente lasciando commenti.
    -   **Effetto della modifica di questa impostata:**
        -   *Quando abilitato:* I voucher sono limitati agli acquirenti verificati.
        -   *Quando disabilitato:* Chiunque lasci un commento (es. un ospite, o qualcuno che non ha acquistato il prodotto) potrebbe ricevere un voucher.
    -   **Valore consigliato:** SÌ (Altamente raccomandato per garantire che i voucher siano dati a clienti reali e prevenire abusi).
    -   **Scenario / esempio del commerciante:** Vuoi premiare i clienti fedeli che hanno già effettuato un acquisto, non solo chiunque lasci un commento.
-   **Quando generare il voucher?**

    -   **Cosa fa questa impostazione:** Determina quando il voucher viene generato e inviato al cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Opzione 1 (es. "Dopo l'aggiunta del commento"):* Il voucher viene inviato immediatamente dopo che il cliente ha inviato il suo commento.
        -   *Opzione 2 (es. "Dopo l'approvazione del commento"):* Il voucher viene inviato solo dopo che un amministratore ha approvato manualmente il commento nel Back Office.
    -   **Valore consigliato:** "Dopo l'approvazione del commento" (Impedisce di dare voucher per spam o commenti inappropriati).
    -   **Scenario / esempio del commerciante:** Moderi tutti i commenti sui prodotti per mantenere la qualità. Vuoi assicurarti che solo i commenti approvati e di valore ricevano un voucher.
-   **Genera voucher per i commenti:**

    -   **Cosa fa questa impostazione:** Questa sezione ti permette di definire le proprietà del voucher che verrà generato. Questo include il tipo di sconto (percentuale, importo), valore, acquisto minimo, validità e altro.
    -   **Effetto della modifica di questa impostazione:**
        -   *Ogni campo qui (es. "Tipo di sconto", "Valore", "Importo minimo"):* Configura direttamente le regole e i benefici del voucher di sconto generato.
        -   *Lasciando i campi vuoti o configurati in modo errato:* Potrebbe portare a voucher non validi o voucher che non soddisfano i tuoi obiettivi di marketing.
    -   **Valore consigliato:**
        -   **Tipo di sconto:** Percentuale (es. 10%) o Importo (es. 5€).
        -   **Valore:** Un incentivo ragionevole (es. 5, 10, 15).
        -   **Importo minimo:** Imposta un acquisto minimo per garantire la redditività (es. 50€).
        -   **Validità:** 30 giorni (Incoraggia un utilizzo rapido).
        -   **Descrizione:** "Grazie per la tua recensione del prodotto!"
    -   **Scenario / esempio del commerciante:** Vuoi offrire uno sconto del 10% sul loro prossimo ordine, valido per 30 giorni, con un acquisto minimo di 50€, come ringraziamento per la loro recensione.
-   **Gruppo di clienti (per Voucher)**

    -   **Cosa fa questa impostazione:** Simile all'impostazione del promemoria, questa ti permette di limitare la generazione di voucher a specifici gruppi di clienti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Selezionando gruppi:* Solo i clienti nei gruppi selezionati riceveranno voucher.
        -   *Non selezionando alcun gruppo:* I voucher verranno inviati a tutti i clienti (a meno che non si applichino altri filtri).
    -   **Valore consigliato:** "Clienti"
    -   **Scenario / esempio del commerciante:** Vuoi dare voucher solo al tuo gruppo standard di "Clienti", non a "Ospiti" o "Grossisti".
-   **Limita il numero di email**

    -   **Cosa fa questa impostazione:** Questa è una funzione di sicurezza per impedire al tuo server di inviare troppe email in un breve periodo, il che potrebbe portare le tue email a essere contrassegnate come spam o il tuo provider di hosting a imporre limiti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo rispetterà l'impostazione "Limite email".
        -   *Quando disabilitato:* Nessun limite di invio email verrà applicato dal modulo stesso.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Hai un gran numero di promemoria in sospeso e vuoi inviarli gradualmente per evitare di sovraccaricare il tuo server di posta.
-   **Limite email:**

    -   **Cosa fa questa impostazione:** Specifica il numero massimo di email (promemoria o voucher) che il modulo può inviare in un singolo ciclo di esecuzione (es. quando viene eseguito il cron job).
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando un numero (es. 50):* Il modulo invierà un massimo di 50 email per ogni esecuzione del cron job. Se ce ne sono di più, verranno inviate nelle esecuzioni successive.
    -   **Valore consigliato:** 50-100 (Regola in base ai limiti di invio email del tuo provider di hosting e alla capacità del server).
    -   **Scenario / esempio del commerciante:** Il tuo provider di hosting consente 100 email all'ora. Imposti questo limite a 50 per rimanere ampiamente entro le loro linee guida.

#### **Filtri prodotto (per Promemoria e Voucher)**

-   **Abilita filtri**

    -   **Cosa fa questa impostazione:** Attiva opzioni di filtro aggiuntive sia per i promemoria che per i voucher, permettendoti di specificare quali prodotti o produttori sono idonei.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il filtro "Produttori" diventa attivo.
        -   *Quando disabilitato:* Nessun filtro specifico per prodotto verrà applicato.
    -   **Valore consigliato:** NO (A meno che tu non abbia una specifica necessità di filtrare).
    -   **Scenario / esempio del commerciante:** Vuoi inviare promemoria o voucher solo per prodotti di determinati produttori.
-   **Produttori**

    -   **Cosa fa questa impostazione:** Se "Abilita filtri" è attivo, questo ti permette di selezionare produttori specifici. Promemoria e voucher verranno inviati solo per i prodotti dei produttori selezionati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Selezionando produttori:* Restringe l'ambito di funzionamento del modulo solo ai prodotti di quei marchi.
    -   **Valore consigliato:** Lascia tutti deselezionati (a meno che tu non abbia una necessità specifica).
    -   **Scenario / esempio del commerciante:** Stai eseguendo una promozione con un marchio specifico e vuoi incentivare i commenti solo per i loro prodotti.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Chiedi il permesso di inviare promemoria | SÌ | Garantisce la conformità al GDPR; i clienti acconsentono ai promemoria. |
| Configurazione modulo | Invia promemoria commento | SÌ | Interruttore principale per l'invio di email di promemoria. |
| Configurazione modulo | Ricorda i commenti dopo: | 7 giorni | Ritardo (in giorni) dopo il cambio di stato dell'ordine per il primo promemoria. |
| Configurazione modulo | Ripeti promemoria | 14 giorni | Ritardo (in giorni) dopo il primo promemoria per un secondo (0 per nessuno). |
| Configurazione modulo | Titolo email (Promemoria) | Personalizzabile | Oggetto delle email di promemoria. |
| Configurazione modulo | Seleziona stati ordine | Consegnato | Stati dell'ordine che attivano il processo di promemoria. |
| Configurazione modulo | Gruppo di clienti (Promemoria) | Clienti | Limita i promemoria ai gruppi di clienti selezionati. |
| Configurazione modulo | Invia promemoria sui commenti per i prodotti degli ordini: | Data recente / Vuoto | Filtro data per gli ordini idonei. |
| Configurazione modulo | Dimensione immagine per le foto dei prodotti | home\_default | Dimensione delle immagini dei prodotti nelle email di promemoria. |
| Configurazione modulo | Invia codice voucher per commento | SÌ | Interruttore principale per la generazione e l'invio di voucher. |
| Configurazione modulo | Invia voucher solo ai clienti che hanno acquistato il prodotto | SÌ | Limita i voucher agli acquirenti effettivi. |
| Configurazione modulo | Quando generare il voucher? | Dopo l'approvazione del commento | Tempistica di generazione del voucher (dopo l'invio o l'approvazione). |
| Configurazione modulo | Genera voucher per i commenti: (Proprietà voucher) | Personalizzabile | Definisce il tipo di sconto, il valore, la validità, ecc., del voucher. |
| Configurazione modulo | Gruppo di clienti (Voucher) | Clienti | Limita i voucher ai gruppi di clienti selezionati. |
| Configurazione modulo | Limita il numero di email | SÌ | Abilita la limitazione della velocità di invio delle email. |
| Configurazione modulo | Limite email: | 50-100 | Max email inviate per esecuzione del cron job. |
| Configurazione modulo | Abilita filtri | NO | Attiva il filtro per prodotto/produttore. |
| Configurazione modulo | Produttori | Tutti deselezionati | Filtra i prodotti idonei per produttore. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo aggiunge diverse schermate dedicate al tuo Back Office di PrestaShop per la gestione di promemoria, voucher e clienti disiscritti. Puoi trovarle sotto la voce di menu **"Voucher per commento"**, solitamente situata sotto **"Catalogo"** o **"Marketing"**.

#### **4.2.1 AdminComRemCommentsController: Gestione dei promemoria commenti**

-   **Nome schermata e posizione menu:** **Voucher per commento > Promemoria commenti**
-   **Azioni e impostazioni disponibili:** Questa schermata mostra un elenco di tutti i promemoria commenti in sospeso, inviati o falliti. Vedrai dettagli come il nome del cliente, l'email, il prodotto su cui deve commentare, l'ID dell'ordine, la data di invio (o di programmazione) del promemoria e il suo stato attuale.
    -   **Vista griglia / Gestione:** Puoi visualizzare, filtrare e cercare nell'elenco dei promemoria. Questo ti permette di monitorare l'attività del modulo.
    -   **Azioni di massa:** A seconda della versione del modulo, potresti essere in grado di inviare manualmente promemoria o eliminare voci.
-   **Effetto delle modifiche:** Questa schermata è principalmente per il monitoraggio. L'eliminazione di una voce qui impedirebbe l'invio di un promemoria programmato. L'invio manuale di un promemoria attiverebbe un'email al cliente.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla periodicamente questa schermata per assicurarti che i promemoria vengano inviati come previsto. Se noti che un cliente non ha ricevuto un promemoria, puoi indagare o attivarlo manualmente.

#### **4.2.2 AdminComUnsubController: Clienti disiscritti**

-   **Nome schermata e posizione menu:** **Voucher per commento > Clienti disiscritti**
-   **Azioni e impostazioni disponibili:** Questa schermata elenca i clienti che hanno scelto di non ricevere promemoria commenti (se l'impostazione "Chiedi il permesso" è abilitata). Vedrai il loro ID cliente e l'indirizzo email.
    -   **Vista griglia / Gestione:** Ti permette di visualizzare e gestire l'elenco dei clienti disiscritti.
-   **Effetto delle modifiche:** La rimozione di un cliente da questo elenco lo renderebbe nuovamente idoneo a ricevere promemoria (supponendo che soddisfi altri criteri e non abbia esplicitamente disattivato altrove).
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Questa è una schermata relativa alla conformità. Generalmente non dovrai interagire con essa quotidianamente, ma è importante sapere dove trovare e gestire le preferenze di opt-out dei clienti.

#### **4.2.3 AdminComVouCommentsController: Gestione voucher per commenti**

-   **Nome schermata e posizione menu:** **Voucher per commento > Voucher per commenti**
-   **Azioni e impostazioni disponibili:** Questa schermata fornisce un elenco completo di tutti i voucher generati dal modulo in risposta ai commenti sui prodotti. Vedrai dettagli come il cliente che ha ricevuto il voucher, il prodotto su cui ha commentato, il codice voucher generato, il suo valore, la validità e se è stato utilizzato.
    -   **Vista griglia / Gestione:** Puoi filtrare, cercare e ordinare i voucher. Questo è utile per monitorare l'efficacia del tuo programma di incentivi.
    -   **Chiavi di configurazione associate:** Le opzioni di visualizzazione e filtro qui potrebbero essere influenzate da `cvo_filters` e `cvo_fil_manuf` dalla configurazione principale.
-   **Effetto delle modifiche:** Questa schermata è principalmente per il monitoraggio. Puoi vedere quali voucher sono stati emessi e se sono stati riscattati.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Rivedi questa schermata per monitorare quanti voucher vengono emessi e i loro tassi di riscatto. Questi dati possono aiutarti a valutare il successo del tuo programma di incentivi per le recensioni.

#### **4.2.4 index.php (Segnaposto del controller Admin)**

-   **Nome schermata e posizione menu:** Questo file `index.php` serve tipicamente come segnaposto o reindirizzamento all'interno della directory `controllers/admin` del modulo, garantendo che l'accesso diretto alla directory non esponga informazioni sensibili. Non rappresenta una schermata visibile all'utente nel Back Office di PrestaShop.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non ricevono le email di promemoria. Cosa devo controllare?**
R1:

-   **Modulo abilitato:** Assicurati che "Invia promemoria commento" sia impostato su SÌ nella configurazione del modulo.
-   **Stati dell'ordine:** Verifica che gli ordini in questione abbiano raggiunto uno degli "Seleziona stati ordine" che hai scelto (es. "Consegnato").
-   **Ritardo promemoria:** Controlla "Ricorda i commenti dopo:" per assicurarti che siano trascorsi abbastanza giorni dal cambio di stato dell'ordine.
-   **Cron Job:** Il modulo si basa sul cron job di PrestaShop per inviare le email. Assicurati che il tuo cron job sia configurato correttamente e che venga eseguito regolarmente sul tuo server. Di solito puoi trovare le istruzioni per il cron job nel tuo pannello di hosting o nella sezione "Parametri avanzati > Informazioni" di PrestaShop.
-   **Configurazione email:** Controlla le impostazioni email di PrestaShop (Parametri avanzati > E-mail) per assicurarti che le email vengano inviate correttamente dal tuo negozio in generale.
-   **Opt-in del cliente:** Se "Chiedi il permesso di inviare promemoria" è abilitato, assicurati che i clienti abbiano effettivamente acconsentito.
-   **Limiti email:** Controlla le impostazioni "Limita il numero di email" e "Limite email". Se il limite viene raggiunto, le email verranno inviate nella successiva esecuzione del cron.
-   **Cartelle spam:** Chiedi ai clienti di controllare le loro cartelle spam o posta indesiderata.

**D2: I voucher non vengono inviati dopo che i commenti sono stati lasciati.**
R2:

-   **Modulo abilitato:** Assicurati che "Invia codice voucher per commento" sia impostato su SÌ.
-   **Tempistica di generazione del voucher:** Controlla "Quando generare il voucher?". Se è impostato su "Dopo l'approvazione del commento", assicurati che i commenti siano stati effettivamente approvati nel tuo Back Office di PrestaShop (Catalogo > Commenti sui prodotti, se usi il modulo predefinito, o il tuo modulo di recensioni di terze parti).
-   **Solo acquirente:** Se "Invia voucher solo ai clienti che hanno acquistato il prodotto" è abilitato, verifica che il cliente che ha lasciato il commento abbia effettivamente acquistato quel prodotto specifico.
-   **Configurazione voucher:** Ricontrolla tutte le impostazioni sotto "Genera voucher per i commenti" per assicurarti che un voucher valido possa essere creato (es. valore dello sconto, validità).
-   **Configurazione email e Cron Job:** Similmente ai problemi di promemoria, assicurati che le tue impostazioni email e il cron job funzionino.

**D3: Il modulo sta inviando troppe email, o le email vengono ritardate.**
R3:

-   **Limite email:** Vai alla configurazione del modulo e assicurati che "Limita il numero di email" sia abilitato e che "Limite email" sia impostato su un numero ragionevole (es. 50-100). Questo impedisce al tuo server di essere sovraccaricato.
-   **Frequenza del Cron Job:** Se il tuo cron job viene eseguito molto frequentemente (es. ogni minuto) e hai un limite email elevato, potrebbe inviare molte email rapidamente. Regola la frequenza del cron job o il limite email.
-   **Limiti di hosting:** Contatta il tuo provider di hosting per comprendere i loro limiti di invio email per ora/giorno. Regola di conseguenza il "Limite email" del modulo.

**D4: Come posso tradurre i testi del modulo o i modelli di email?**
R4:

-   **Traduzione Back Office:** Vai su **Internazionale > Traduzioni**.
-   **Tipo di traduzione:** Seleziona "Traduzioni dei moduli installati".
-   **Seleziona il tuo tema:** Scegli il tuo tema attuale.
-   **Seleziona la tua lingua:** Scegli la lingua che vuoi tradurre.
-   **Modulo:** Trova "Voucher per commenti sui prodotti" nell'elenco.
-   Potrai quindi modificare le stringhe di testo per la configurazione del modulo, gli elementi del front-office (come la casella di opt-in) e i modelli di email. Ricorda di salvare le modifiche.

**D5: La casella di controllo del front-office del modulo (per i permessi) non appare correttamente sul mio tema.**
R5:

-   **Compatibilità del tema:** I temi personalizzati a volte richiedono piccole modifiche CSS per i nuovi elementi del modulo.
-   **Svuota cache:** Per prima cosa, prova a svuotare la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).
-   **Contatta il supporto:** Se il problema persiste, potrebbe richiedere una piccola modifica CSS. Contatta il supporto MyPresta.eu con screenshot e il nome del tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Voucher per commenti sui prodotti" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo segue un'architettura standard dei moduli PrestaShop, sfruttando i pattern MVC dove appropriato. Si integra con il core di PrestaShop tramite hook per la visualizzazione del front-office e le azioni del back-office. Utilizza AdminController personalizzati per la gestione delle sue entità dati (promemoria, voucher, disiscrizioni) e un FrontController per l'esecuzione del cron job. La configurazione è gestita tramite `Configuration::get()` e `Configuration::updateValue()`. Il modulo non sembra utilizzare classi `ObjectModel` personalizzate, ma probabilmente gestisce i suoi dati direttamente o tramite entità PrestaShop esistenti (come `CartRule` per i voucher).

### 4.2 Controller (`controllers/`)

#### Controller del Front-Office

-   `comvou/controllers/front/CronJob.php`
    -   **Nome classe e classe padre:** `ComvouCronJobModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller è progettato per essere eseguito tramite un cron job. Gestisce le attività in background del modulo, come il controllo degli ordini idonei, l'invio di promemoria per i commenti e la generazione/invio di voucher basati su nuovi commenti. Tipicamente non renderizza una pagina visiva ma esegue azioni ed esce. È il cuore dell'automazione del modulo.

#### Controller Admin del Back-Office

-   `comvou/controllers/admin/AdminComRemComments.php`

    -   **Nome scheda ed entità gestita:** "Promemoria commenti" (sotto il menu "Voucher per commento"). Gestisce le entità `cvor` (Comment Voucher Order Reminder), che rappresentano promemoria programmati o inviati.
    -   **Responsabilità:** Fornisce un elenco (vista a griglia) di tutti i promemoria commenti. Permette agli amministratori di visualizzare lo stato dei promemoria, filtrarli e potenzialmente eseguire azioni come l'invio manuale di un promemoria o l'eliminazione di una voce. Estende `AdminController` e utilizza `HelperList` per la visualizzazione.
-   `comvou/controllers/admin/AdminComUnsub.php`

    -   **Nome scheda ed entità gestita:** "Clienti disiscritti" (sotto il menu "Voucher per commento"). Gestisce le entità `cunsub` (Comment Unsubscribe).
    -   **Responsabilità:** Visualizza un elenco di clienti che si sono disiscritti dai promemoria commenti. Questo controller fornisce un'interfaccia per visualizzare e gestire queste preferenze di opt-out, tipicamente utilizzando `HelperList`.
-   `comvou/controllers/admin/AdminComVouComments.php`

    -   **Nome scheda ed entità gestita:** "Voucher per commenti" (sotto il menu "Voucher per commento"). Gestisce le entità `cvov` (Comment Voucher Order Voucher), che rappresentano i voucher generati.
    -   **Responsabilità:** Presenta un elenco di tutti i voucher generati dal modulo, dettagliando quale cliente lo ha ricevuto, per quale prodotto, il codice del voucher, il suo valore e lo stato di utilizzo. Utilizza `HelperList` per la visualizzazione e consente il filtraggio. La visualizzazione potrebbe incorporare logica basata sulle chiavi di configurazione `cvo_filters` e `cvo_fil_manuf`.
-   `comvou/controllers/admin/index.php`

    -   **Nome scheda ed entità gestita:** Non è una schermata direttamente visibile all'utente.
    -   **Responsabilità:** Questa è una misura di sicurezza standard in PrestaShop. Tipicamente contiene `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` per prevenire l'elenco delle directory e reindirizzare alla radice del negozio.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo potrebbe gestire i suoi dati direttamente all'interno del file principale `comvou.php` o dei suoi controller, potenzialmente utilizzando `ObjectModel` esistenti di PrestaShop (come `Order`, `Customer`, `Product`, `CartRule`) e query dirette al database per la sua archiviazione dati personalizzata (es. per promemoria e record di voucher).

### 4.4 Risorse JavaScript (`views/js/`)

-   `comvou/lib/voucherengine/script.js`
    -   **Ambito:** Probabilmente Back-office.
    -   **Dettagli:** Questo script è probabilmente associato alle impostazioni di generazione dei voucher all'interno della configurazione del modulo o del controller AdminComVouComments. Potrebbe gestire elementi dinamici del modulo, la validazione o le interazioni AJAX relative ai parametri di creazione dei voucher (es. mostrare/nascondere campi in base al tipo di sconto, calcolare valori). Potrebbe anche essere utilizzato per miglioramenti generali dell'interfaccia utente nelle pagine di amministrazione del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `comvou/lib/voucherengine/ps16.css`
    -   **Ambito:** Stile del modulo di amministrazione del Back-office.
    -   **Dettagli:** Questo foglio di stile fornisce uno stile specifico per la pagina di configurazione del modulo e potenzialmente per le sue viste personalizzate del controller di amministrazione, assicurando che abbiano un aspetto coerente con il design del back-office di PrestaShop 1.6. Potrebbe contenere regole per i layout dei moduli, i campi di input, i pulsanti e le visualizzazioni a griglia. Gli sviluppatori che lo sovrascrivono si rivolgeranno a ID o classi specifici utilizzati dai modelli di amministrazione del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

-   `comvou/views/templates/hook/form.tpl`

    -   **Hook:** Potenzialmente `displayAdditionalCustomerFormFields` o `displayCustomerAccountForm`.
    -   **Output:** Questo template probabilmente renderizza la casella di controllo "Chiedi il permesso di inviare promemoria" sui moduli di registrazione o aggiornamento dell'identità del cliente nel front office. Contenerebbe l'HTML per la casella di controllo e la sua etichetta associata.
-   `comvou/views/templates/hook/header.tpl`

    -   **Hook:** `displayHeader`
    -   **Output:** Questo template è tipicamente utilizzato per includere file CSS o JavaScript che devono essere caricati nella sezione `<head>` delle pagine del front-office. Potrebbe caricare condizionalmente risorse in base alle impostazioni del modulo o alla pagina corrente.
-   `comvou/views/templates/hook/identity.tpl`

    -   **Hook:** Potenzialmente `displayCustomerAccountForm` o hook simili sulla pagina dell'identità del cliente.
    -   **Output:** Simile a `form.tpl`, questo template probabilmente renderizza la casella di controllo di opt-in specificamente sulla pagina "Il mio account > Informazioni" del cliente, consentendo ai clienti esistenti di gestire le loro preferenze di promemoria.

#### Template di amministrazione (`views/templates/admin/`)

-   `comvou/views/templates/admin/com_rem_comments/helpers/form/form.tpl`

    -   **Scopo:** Questo template è utilizzato da `AdminComRemCommentsController` per renderizzare il modulo (se presente) per aggiungere/modificare un promemoria commento, o più probabilmente, per personalizzare la visualizzazione dell'helper di elenco.
-   `comvou/views/templates/admin/com_vou_comments/helpers/form/form.tpl`

    -   **Scopo:** Questo template è utilizzato da `AdminComVouCommentsController` per renderizzare il modulo (se presente) per aggiungere/modificare una voce di voucher, o per personalizzare la visualizzazione dell'helper di elenco per i voucher generati.
-   `comvou/views/templates/admin/orderstates.tpl`

    -   **Scopo:** Questo template è probabilmente utilizzato all'interno della configurazione principale del modulo (`getContent()`) per renderizzare l'elenco a selezione multipla degli stati dell'ordine, consentendo al commerciante di scegliere quali stati attivano i promemoria.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

La descrizione del modulo e l'analisi del codice suggeriscono che il modulo memorizza i suoi dati personalizzati (promemoria, voucher, disiscrizioni) in tabelle di database dedicate. Sebbene non siano elencati file SQL specifici, `AdminComRemCommentsController`, `AdminComUnsubController` e `AdminComVouCommentsController` implicano l'esistenza di tabelle come:

-   `ps_cvor`: Memorizza i record relativi ai promemoria commenti (es. ID cliente, ID prodotto, ID ordine, stato promemoria, ultima data di invio).
-   `ps_cunsub`: Memorizza i record dei clienti che si sono disiscritti dai promemoria (es. ID cliente, email).
-   `ps_cvov`: Memorizza i record dei voucher generati (es. ID cliente, ID prodotto, `id_cart_rule` generato, codice voucher, stato).
-   I valori di configurazione sono memorizzati in `ps_configuration` con chiavi come `cvo_r_d`, `cvo_r`, `cvo_repeat`, `cvo_orderstates`, `CR_ALLOWED`, `cvo_v`, `cvo_v_fn`, `cvo_v_t`, `cvo_filters`, `cvo_fil_manuf`, `CVOR_TITLE`, `CVOV_TITLE`, `cvo_customergroups_reminder`, `cvo_customergroups_voucher`, `cvo_r_fn`, `cvo_r_date`, `cvo_vonlycust`, `cvo_v_date`, `cvo_img_type`, `CVO_LIM_M_V`, `CVO_LIM_M`.

#### Tabella degli hook registrati

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Quando un AdminController viene inizializzato e i suoi media (JS/CSS) vengono impostati. | Per iniettare JS/CSS specifici del modulo nel Back Office. |
| `actionOrderStatusUpdate` | Dopo che lo stato di un ordine è stato aggiornato. | Per rilevare quando un ordine raggiunge uno stato "consegnato" o pertinente, attivando il processo di promemoria. |
| `actionCustomerAccountAdd` | Dopo la creazione di un nuovo account cliente. | Per verificare le preferenze di opt-in iniziali per i nuovi clienti. |
| `displayHeader` | Nella sezione `<head>` delle pagine del front-office. | Per includere CSS/JS del front-office o meta tag. |
| `displayCustomerAccountForm` | Sulla pagina "Il mio account > Informazioni" del cliente. | Per visualizzare la casella di controllo di opt-in per i clienti esistenti. |
| `displayAdditionalCustomerFormFields` | Sul modulo di registrazione del cliente. | Per visualizzare la casella di controllo di opt-in per le nuove registrazioni dei clienti. |
| `validateCustomerFormFields` | Quando viene inviato un modulo cliente (registrazione/identità). | Per elaborare la selezione della casella di controllo di opt-in e salvare la preferenza del cliente. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto tecnico professionale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assicurati di utilizzare l'ultima versione compatibile del modulo per il tuo negozio PrestaShop per beneficiare di tutti i miglioramenti e le patch di sicurezza.
