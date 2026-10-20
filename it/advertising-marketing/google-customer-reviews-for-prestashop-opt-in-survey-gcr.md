---
title: "Recensioni dei clienti Google per PrestaShop - opt-in e sondaggio (GCR) - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Recensioni dei clienti Google per PrestaShop - opt-in & sondaggio (GCR) di MyPresta.eu."
sidebar:
  label: "Recensioni dei clienti Google per PrestaShop - opt-in e sondaggio (GCR) - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Google Customer Reviews for PrestaShop - opt-in & survey (GCR) su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr/)
>
> ---


# Recensioni dei clienti Google per PrestaShop - opt-in e sondaggio (GCR)

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alle impostazioni del modulo, vai su **Moduli > Gestione moduli**, cerca "Recensioni dei clienti Google" e clicca sul pulsante "Configura".

#### **ID Commerciante Google**

-   **Cosa fa questa impostazione:** Questo è l'identificatore univoco per il tuo account Google Merchant Center. Google utilizza questo ID per associare le recensioni raccolte alla tua attività specifica.
-   **Effetto della modifica di questa impostazione:**
    -   *Se inserito correttamente:* Lo script di opt-in delle Recensioni dei clienti Google funzionerà correttamente, inviando i dati delle recensioni al tuo account Google Merchant Center.
    -   *Se errato o vuoto:* Lo script di opt-in non funzionerà e Google non raccoglierà recensioni per il tuo negozio.
-   **Valore consigliato:** Il tuo ID Google Merchant Center esatto. Puoi trovare questo ID accedendo al tuo account Google Merchant Center (merchant.google.com) – di solito è visualizzato nell'angolo in alto a destra.
-   **Scenario/esempio del commerciante:** Se il tuo ID Google Merchant Center è `123456789`, dovresti inserire `123456789` in questo campo. Senza di esso, Google non sa a quale commerciante attribuire le recensioni.

#### **Includi elenco GTIN prodotto nel payload GCR**

-   **Cosa fa questa impostazione:** Questa opzione controlla se i Global Trade Item Numbers (GTIN) dei prodotti nell'ordine del cliente vengono inclusi quando i dati di opt-in vengono inviati a Google. I GTIN (come EAN, UPC, ISBN) aiutano Google a identificare prodotti specifici per le recensioni a livello di prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato (Sì):* Il modulo tenterà di recuperare e includere i GTIN per ogni prodotto nell'ordine. Ciò consente a Google di raccogliere potenzialmente recensioni specifiche del prodotto, che possono apparire sulle pagine dei prodotti e in Google Shopping.
    -   *Se disabilitato (No):* Verranno raccolte solo le recensioni del venditore. I GTIN specifici del prodotto non verranno inviati, il che significa che Google non chiederà ai clienti recensioni sui singoli prodotti di quell'ordine.
-   **Valore consigliato:** **Sì**. L'inclusione dei GTIN è altamente raccomandata se si desidera raccogliere recensioni a livello di prodotto, che sono molto preziose per la visibilità e la fiducia del prodotto. Assicurati che i tuoi prodotti in PrestaShop abbiano i campi EAN/UPC correttamente compilati.
-   **Scenario/esempio del commerciante:** Se vendi una "Maglietta Blu" con EAN `1234567890123`, abilitando questa opzione Google saprà *quale* prodotto ha acquistato il cliente, consentendogli di recensire quell'articolo specifico. Se disabilitato, Google chiederebbe solo una recensione generale del tuo negozio.

#### **Offset di consegna di fallback (giorni)**

-   **Cosa fa questa impostazione:** Questa impostazione determina il numero stimato di giorni dopo l'effettuazione di un ordine in cui il cliente dovrebbe ricevere la consegna. Google utilizza questa data per programmare l'invio dell'e-mail di sondaggio sulle recensioni.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su un numero specifico (es. 7):* Il modulo calcola la data di consegna stimata aggiungendo questo numero di giorni alla data dell'ordine. Google invierà quindi l'e-mail di sondaggio intorno a questa data di consegna calcolata.
    -   *Se impostato su 0 o un numero molto basso:* Google potrebbe inviare il sondaggio troppo presto, prima che il cliente abbia ricevuto il prodotto, portando a recensioni irrilevanti o negative.
    -   *Se impostato su un numero molto alto:* Google potrebbe inviare il sondaggio troppo tardi e il cliente potrebbe aver dimenticato i dettagli della sua esperienza di acquisto.
-   **Valore consigliato:** Dipende dai tuoi tempi di spedizione medi. Un punto di partenza comune è **7 giorni**. Regola questo valore in base alle tue effettive prestazioni di consegna.
-   **Scenario/esempio del commerciante:** Se il tuo tempo di consegna medio è di 5-7 giorni lavorativi, impostare questo valore su `7` giorni è appropriato. Se spedisci a livello internazionale e le consegne richiedono 2-3 settimane, potresti impostarlo su `14` o `21` giorni. Ciò garantisce che il sondaggio arrivi quando il cliente ha avuto il tempo di ricevere e provare il prodotto.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | ID Commerciante Google | Il tuo ID Commerciante | Collega le recensioni raccolte al tuo account Google Merchant Center. **CRITICO per la funzione.** |
| Configurazione modulo | Includi elenco GTIN prodotto nel payload GCR | Sì | Abilita la raccolta di recensioni specifiche del prodotto inviando gli identificatori del prodotto. |
| Configurazione modulo | Offset di consegna di fallback (giorni) | 7 | Imposta la data di consegna stimata per la pianificazione del sondaggio. Regola in base al tempo medio di spedizione. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma non vedo l'opt-in delle Recensioni dei clienti Google sulla mia pagina di conferma dell'ordine.**
R:

1.  **Controlla il tuo ID Commerciante Google:** Ricontrolla di aver inserito l'ID Commerciante Google corretto nella configurazione del modulo. Un ID errato impedirà il caricamento dello script.
2.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte, il contenuto memorizzato nella cache può impedire la visualizzazione di nuovi script del modulo.
3.  **Verifica la presenza di errori JavaScript:** Apri la console per sviluppatori del tuo browser (solitamente F12) sulla pagina di conferma dell'ordine. Cerca eventuali errori JavaScript, che potrebbero indicare un conflitto con un altro modulo o il tuo tema.
4.  **Verifica l'esecuzione dell'hook:** Assicurati che il tuo tema chiami correttamente l'hook `displayOrderConfirmation`. Sebbene standard, alcuni temi pesantemente personalizzati potrebbero omettere o rinominare gli hook.

**D: L'opt-in appare, ma non vedo recensioni nel mio Google Merchant Center.**
R:

1.  **Stato di Google Merchant Center:** Accedi al tuo account Google Merchant Center e naviga nella sezione "Recensioni dei clienti Google". Assicurati che il programma sia attivo e che non ci siano problemi segnalati. Potrebbe essere necessario del tempo prima che le recensioni inizino ad apparire dopo la configurazione iniziale.
2.  **Tasso di opt-in del cliente:** Non tutti i clienti aderiranno al sondaggio. Una certa percentuale di clienti deve accettare di ricevere l'e-mail di sondaggio da Google.
3.  **Completamento del sondaggio:** Anche se un cliente aderisce, deve comunque completare il sondaggio inviato da Google.

**D: Posso personalizzare l'aspetto dell'opt-in o del badge delle Recensioni dei clienti Google?**
R: L'aspetto del prompt di opt-in e del badge delle Recensioni dei clienti Google è controllato da Google e non può essere personalizzato direttamente tramite il modulo PrestaShop. Google mantiene un'esperienza di marca coerente per questi elementi. Puoi, tuttavia, scegliere dove visualizzare il badge sul tuo sito tramite le impostazioni del tuo Google Merchant Center (ad esempio, piè di pagina, barra laterale).

**D: I miei prodotti hanno GTIN, ma non ricevo recensioni a livello di prodotto.**
R:

1.  **Abilita i GTIN nel modulo:** Assicurati che l'opzione "Includi elenco GTIN prodotto nel payload GCR" sia impostata su "Sì" nella configurazione del modulo.
2.  **Formato GTIN corretto:** Verifica che i GTIN dei tuoi prodotti (EAN, UPC, ISBN) siano inseriti correttamente nelle pagine dei tuoi prodotti PrestaShop e seguano i formati standard. GTIN formattati in modo errato potrebbero essere ignorati da Google.
3.  **Discrezione di Google:** Anche con i GTIN forniti, Google decide in ultima analisi se chiedere recensioni a livello di prodotto. Fattori come la popolarità del prodotto e il volume delle recensioni possono influenzare questa decisione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `gcroptin` è un modulo PrestaShop leggero progettato per iniettare lo script ufficiale di opt-in delle Recensioni dei clienti Google nell'hook `displayOrderConfirmation`. Sfrutta la classe `Module` di PrestaShop e il motore di templating `Smarty`. La logica principale risiede nel file principale del modulo, gestendo l'archiviazione della configurazione e l'iniezione dinamica dei dati nel template Smarty. Non introduce controller personalizzati, modelli o asset JavaScript/CSS complessi, concentrandosi esclusivamente sull'iniezione dello script richiesta con dati dinamici dell'ordine.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Il modulo opera agganciandosi a `displayOrderConfirmation` e renderizzando un template direttamente.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Non sono definite classi personalizzate o istanze di `ObjectModel`. Tutta la logica è autocontenuta all'interno di `gcroptin.php`.

### 4.4 Asset JavaScript (`views/js/`)

-   Nessuno. Il modulo produce direttamente lo snippet JavaScript delle Recensioni dei clienti Google all'interno di un template Smarty.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessuno. L'interfaccia utente di opt-in delle Recensioni dei clienti Google è renderizzata dallo script di Google e non richiede stili personalizzati dal modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   `gcroptin/views/templates/hook/gcroptin-order-confirmation.tpl`
        -   **Scopo:** Questo template viene renderizzato quando viene eseguito l'hook `displayOrderConfirmation`. Contiene lo snippet JavaScript principale di opt-in delle Recensioni dei clienti Google.
        -   **Dati disponibili:** Questo template riceve varie variabili specifiche dell'ordine dal modulo, tra cui:
            -   `{$gcr_merchant_id}`: L'ID Google Merchant Center configurato nel back office.
            -   `{$gcr_order_id}`: L'ID dell'ordine PrestaShop.
            -   `{$gcr_currency_iso_code}`: Codice ISO della valuta dell'ordine.
            -   `{$gcr_total_paid}`: Importo totale pagato per l'ordine.
            -   `{$gcr_customer_email}`: Indirizzo email del cliente.
            -   `{$gcr_delivery_country}`: Codice ISO del paese di consegna.
            -   `{$gcr_delivery_date}`: Data di consegna stimata calcolata.
            -   `{$gcr_product_gtins_json}`: Array codificato JSON dei GTIN dei prodotti (se abilitato).
        -   **Output:** Produce un tag `<script>` contenente il codice di opt-in delle Recensioni dei clienti Google, popolato dinamicamente con i dettagli dell'ordine.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle del database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop utilizzando chiavi come `GCROPTIN_MERCHANT_ID`, `GCROPTIN_INCLUDE_GTIN` e `GCROPTIN_DELIVERY_OFFSET`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayOrderConfirmation` | Eseguito sulla pagina di conferma dell'ordine dopo un checkout riuscito. | Inietta lo snippet JavaScript di opt-in delle Recensioni dei clienti Google con dati dinamici dell'ordine. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda relativa al modulo "Recensioni dei clienti Google per PrestaShop - opt-in e sondaggio (GCR)".
