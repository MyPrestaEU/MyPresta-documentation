---
title: "Codice voucher dopo la registrazione - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Codice voucher dopo la registrazione di MyPresta.eu."
sidebar:
  label: "Codice voucher dopo la registrazione - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Voucher code after registration su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-code-after-registration.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/voucher-code-after-registration/)
>
> ---


# Codice voucher dopo la registrazione

## 1. Requisiti e compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito preinstallate nella maggior parte degli ambienti di hosting web.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca sul pulsante "Configura" accanto al modulo "Codice voucher dopo la registrazione". Questo ti porterà alla schermata di configurazione principale dove potrai definire come funzioneranno i tuoi nuovi voucher per i clienti.

La pagina di configurazione ti presenterà le opzioni per definire le caratteristiche del voucher che i nuovi clienti riceveranno. Queste impostazioni corrispondono direttamente alle funzionalità standard di "Regola carrello" (voucher) di PrestaShop.

Ecco le impostazioni tipiche che incontrerai:

-   **Descrizione:**

    -   **Cosa fa questa impostazione:** Questo è il nome interno della regola del carrello (voucher) che verrà creata. Ti aiuta a identificare il voucher nel tuo Back Office.
    -   **Effetto della modifica di questa impostazione:** Questo nome è solo per tuo riferimento e non è visibile ai clienti.
    -   **Valore consigliato:** Qualcosa di descrittivo come "Voucher di registrazione nuovo cliente" o "Sconto di benvenuto".
    -   **Scenario / esempio del commerciante:** Se gestisci più promozioni, una descrizione chiara come "Voucher di benvenuto - 10% di sconto" ti aiuta a monitorarne le prestazioni.
-   **Codice:**

    -   **Cosa fa questa impostazione:** Definisce il prefisso per i codici voucher unici generati. Il modulo aggiungerà una stringa unica a questo prefisso per ogni nuovo cliente.
    -   **Effetto della modifica di questa impostazione:** Se lo imposti su "BENVENUTO", i clienti potrebbero ricevere codici come "BENVENUTO12345" o "BENVENUTOABCDE". Questo rende i codici facilmente identificabili.
    -   **Valore consigliato:** Un prefisso breve e memorabile come "BENVENUTO", "NUOVOCLIENTE" o "MIONOTEGOZIO". Lascia vuoto per un codice completamente casuale.
    -   **Scenario / esempio del commerciante:** L'uso di "BENVENUTO" chiarisce al cliente che si tratta di un'offerta di benvenuto.
-   **Evidenzia:**

    -   **Cosa fa questa impostazione:** Se abilitato, questo voucher verrà visualizzato nel riepilogo del carrello (se applicabile) e nella pagina del prodotto (se configurato per farlo dalle impostazioni principali di PrestaShop).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* L'esistenza del voucher potrebbe essere sottilmente suggerita nei luoghi in cui le regole del carrello sono solitamente promosse.
        -   *Quando disabilitato:* Il voucher è noto al cliente solo tramite e-mail e il suo account.
    -   **Valore consigliato:** SÌ (Abilitato), in quanto può sottilmente ricordare ai clienti gli sconti disponibili.
    -   **Scenario / esempio del commerciante:** L'abilitazione di questa opzione può incoraggiare i clienti a utilizzare il voucher che hanno ricevuto, anche se se ne sono dimenticati.
-   **Uso parziale:**

    -   **Cosa fa questa impostazione:** Determina se il voucher può essere utilizzato più volte se il suo valore è maggiore del totale dell'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Se un cliente ha un voucher da 50€ e acquista un articolo da 30€, avrà un saldo di 20€ rimanente sul voucher per un acquisto futuro.
        -   *Quando disabilitato:* L'intero valore del voucher deve essere utilizzato in una transazione, o il saldo rimanente viene perso.
    -   **Valore consigliato:** NO (Disabilitato) per la maggior parte dei voucher di benvenuto, per incoraggiare un acquisto completo.
    -   **Scenario / esempio del commerciante:** Per un voucher "10% di sconto", questa impostazione è meno rilevante, ma per un voucher "importo fisso" (ad esempio, "10€ di sconto"), la disabilitazione dell'uso parziale incoraggia un primo ordine più grande.
-   **Priorità:**

    -   **Cosa fa questa impostazione:** Se un cliente ha più voucher, questo numero determina l'ordine in cui vengono applicati. Numeri più bassi significano priorità più alta.
    -   **Effetto della modifica di questa impostazione:** Un voucher con priorità 1 verrà applicato prima di un voucher con priorità 2. Questo è importante se i voucher non possono essere combinati.
    -   **Valore consigliato:** 1 (Priorità più alta) per i voucher di benvenuto, assicurando che vengano applicati per primi.
    -   **Scenario / esempio del commerciante:** Se hai un voucher generale "spedizione gratuita" (priorità 5) e un voucher "sconto di benvenuto" (priorità 1), lo sconto di benvenuto verrà calcolato per primo.
-   **Stato:**

    -   **Cosa fa questa impostazione:** Controlla se il modulo è attivo e genera voucher.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I nuovi clienti riceveranno voucher al momento della registrazione.
        -   *Quando disabilitato:* Il modulo smetterà di generare e inviare voucher.
    -   **Valore consigliato:** SÌ (Abilitato) per attivare la funzionalità principale del modulo.
    -   **Scenario / esempio del commerciante:** Potresti disabilitarlo temporaneamente durante un evento di vendita specifico in cui non desideri offrire sconti di registrazione aggiuntivi.
-   **Tipo di sconto:**

    -   **Cosa fa questa impostazione:** Definisce se lo sconto è una percentuale, un importo fisso o la spedizione gratuita.
    -   **Effetto della modifica di questa impostazione:**
        -   *Percentuale:* ad esempio, "10%" di sconto sull'ordine.
        -   *Importo:* ad esempio, "10€" di sconto sull'ordine.
        -   *Spedizione gratuita:* Annulla i costi di spedizione.
    -   **Valore consigliato:** Percentuale o Importo, a seconda della tua strategia di marketing.
    -   **Scenario / esempio del commerciante:** Offrire "10% di sconto" è comune per gli sconti di benvenuto. "5€ di sconto" potrebbe essere migliore per articoli a basso prezzo.
-   **Valore:**

    -   **Cosa fa questa impostazione:** Il valore effettivo dello sconto, corrispondente al "Tipo di sconto" selezionato.
    -   **Effetto della modifica di questa impostazione:** Se "Tipo di sconto" è Percentuale e "Valore" è 10, i clienti ottengono il 10% di sconto. Se "Tipo di sconto" è Importo e "Valore" è 10, ottengono 10€ di sconto.
    -   **Valore consigliato:** Un valore attraente ma anche redditizio, ad esempio, "10" per il 10% o "5€".
    -   **Scenario / esempio del commerciante:** Uno sconto del 10% è un buon punto di partenza per attirare nuovi clienti.
-   **Importo minimo:**

    -   **Cosa fa questa impostazione:** Il totale minimo dell'ordine (prima della spedizione) richiesto affinché il voucher sia valido.
    -   **Effetto della modifica di questa impostazione:** Se impostato a 50€, il cliente deve effettuare un ordine di 50€ o più per utilizzare il voucher.
    -   **Valore consigliato:** Imposta un minimo ragionevole per incoraggiare ordini iniziali più grandi, o 0 se non è richiesto alcun minimo.
    -   **Scenario / esempio del commerciante:** Impostare un minimo di 50€ per un voucher del 10% di sconto garantisce che tu realizzi comunque un buon profitto sul primo ordine.
-   **Cumulativo:**

    -   **Cosa fa questa impostazione:** Determina se questo voucher può essere combinato con altri voucher.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono utilizzare questo voucher di benvenuto insieme ad altri voucher attivi (ad esempio, un voucher per la spedizione gratuita).
        -   *Quando disabilitato:* Questo voucher non può essere utilizzato se un altro voucher è già applicato al carrello.
    -   **Valore consigliato:** NO (Disabilitato) per la maggior parte dei voucher di benvenuto per prevenire sconti eccessivi.
    -   **Scenario / esempio del commerciante:** Di solito si desidera limitare l'accumulo di sconti per proteggere i margini, quindi la disabilitazione dell'uso cumulativo è spesso preferita.
-   **Valido dal / Valido al:**

    -   **Cosa fa questa impostazione:** Definisce l'intervallo di date durante il quale il voucher è attivo.
    -   **Effetto della modifica di questa impostazione:** Il voucher sarà valido solo tra queste date.
    -   **Valore consigliato:** Lascia "Valido dal" come data corrente. Per "Valido al", considera di impostare una data di scadenza (ad esempio, 30 giorni dalla registrazione) per creare urgenza, o lasciala molto in futuro se vuoi che sia sempre valida.
    -   **Scenario / esempio del commerciante:** Impostare "Valido al" a 30 giorni nel futuro incoraggia i clienti a utilizzare il voucher rapidamente.
-   **Quantità:**

    -   **Cosa fa questa impostazione:** Si riferisce al numero totale di voucher *unici* che possono essere generati dal modulo.
    -   **Effetto della modifica di questa impostazione:** Se impostato a 100, solo i primi 100 nuovi iscritti riceveranno un voucher.
    -   **Valore consigliato:** Un numero molto alto (ad esempio, 999999) o lasciare vuoto se si desidera che venga generato un numero illimitato di voucher per i nuovi iscritti.
    -   **Scenario / esempio del commerciante:** Per un'offerta di benvenuto in corso, di solito si desidera una quantità illimitata. Se stai eseguendo una campagna a tempo limitato per i primi X iscritti, imposteresti un numero specifico.
-   **Quantità per cliente:**

    -   **Cosa fa questa impostazione:** Definisce quante volte un *singolo cliente* può ricevere questo specifico voucher.
    -   **Effetto della modifica di questa impostazione:** Impostato a 1 per garantire che ogni cliente riceva un solo voucher di benvenuto al momento della registrazione iniziale.
    -   **Valore consigliato:** 1.
    -   **Scenario / esempio del commerciante:** Vuoi che ogni nuovo cliente riceva uno sconto di benvenuto, non più di uno se si registra di nuovo con un'e-mail diversa (anche se il core di PrestaShop di solito lo impedisce).

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Descrizione** | "Voucher nuovo cliente" | Nome interno del voucher nel BO. |
| Configurazione modulo | **Codice** | Vuoto (casuale) / "BENVENUTO" | Prefisso per i codici voucher generati. |
| Configurazione modulo | **Evidenzia** | SÌ | Visualizza il voucher nel riepilogo del carrello/pagina del prodotto. |
| Configurazione modulo | **Uso parziale** | NO | Consente usi multipli se il valore > totale ordine. |
| Configurazione modulo | **Priorità** | 1 | Ordine di applicazione se più voucher. |
| Configurazione modulo | **Stato** | SÌ | Attiva/disattiva la generazione di voucher del modulo. |
| Configurazione modulo | **Tipo di sconto** | Percentuale | Tipo di sconto (%, importo, spedizione gratuita). |
| Configurazione modulo | **Valore** | 10 | Il valore effettivo dello sconto (es. 10 per 10%). |
| Configurazione modulo | **Importo minimo** | 0 | Totale minimo dell'ordine per la validità del voucher. |
| Configurazione modulo | **Cumulativo** | NO | Consente la combinazione con altri voucher. |
| Configurazione modulo | **Valido dal** | Data corrente | Data di inizio validità del voucher. |
| Configurazione modulo | **Valido al** | Futuro lontano / 30 giorni | Data di fine validità del voucher. |
| Configurazione modulo | **Quantità** | 999999 | Numero totale di voucher unici da generare. |
| Configurazione modulo | **Quantità per cliente** | 1 | Quante volte un singolo cliente può ottenerlo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non ricevono l'e-mail del voucher. Cosa devo controllare?**
R:

1.  **Stato del modulo:** Assicurati che l'impostazione "Stato" nella configurazione del modulo sia impostata su SÌ (Abilitato).
2.  **Configurazione e-mail:** Controlla le impostazioni e-mail di PrestaShop in **Parametri avanzati > E-mail**. Invia un'e-mail di prova per assicurarti che il sistema di e-mail del tuo negozio funzioni correttamente.
3.  **Cartelle spam:** Consiglia ai clienti di controllare le loro cartelle spam o posta indesiderata.
4.  **Log del modulo:** Se disponibili, controlla eventuali log di errore relativi al modulo o all'invio di e-mail.
5.  **Cache Smarty:** A volte, la cancellazione della cache Smarty in **Parametri avanzati > Prestazioni** può risolvere problemi di visualizzazione o funzionalità.

**D: Il codice voucher è generato, ma non si applica correttamente al checkout.**
R:

1.  **Impostazioni voucher:** Ricontrolla tutte le impostazioni del voucher nella configurazione del modulo (ad esempio, "Importo minimo", "Valido dal/al", "Cumulativo"). Assicurati che il carrello del cliente soddisfi tutte le condizioni.
2.  **Inserimento codice:** Conferma che il cliente stia inserendo il codice correttamente nel carrello/checkout.
3.  **Restrizioni prodotto:** Assicurati che non ci siano restrizioni nascoste su prodotti o categorie applicate alla regola del carrello generata (anche se questo modulo di solito crea regole semplici e ampie).

**D: Posso personalizzare il modello di e-mail che invia il voucher?**
R: Sì, il modulo utilizza il sistema di modelli di e-mail standard di PrestaShop. Puoi trovare e personalizzare i file del modello di e-mail pertinenti (di solito in `themes/your_theme/mail/en/` o `mails/en/` per le versioni precedenti) che vengono attivati quando viene creata e inviata una nuova regola del carrello. Cerca modelli relativi a `voucher` o `cart_rule`.

**D: Cosa succede se un cliente si registra più volte con indirizzi e-mail diversi?**
R: Il modulo genererà un nuovo voucher unico per ogni nuova registrazione. La funzionalità principale di PrestaShop di solito impedisce registrazioni e-mail duplicate, ma se un cliente utilizza e-mail diverse, riceverà un nuovo voucher ogni volta. L'impostazione "Quantità per cliente" si applica a un singolo ID cliente, non necessariamente a indirizzi e-mail unici se bypassano i controlli principali.

**D: Il modulo è installato, ma non vedo nuove voci di menu nel Back Office.**
R: Questo modulo si integra direttamente nella sezione esistente "Moduli > Gestione moduli" e non aggiunge nuove voci di menu di primo livello. La sua configurazione è accessibile cliccando su "Configura" accanto al suo nome nell'elenco dei moduli.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Codice voucher dopo la registrazione" (`registervoucher`) è un modulo PrestaShop standard progettato principalmente per estendere l'hook `actionCustomerAccountAdd`. Sfrutta la funzionalità `CartRule` (voucher) principale di PrestaShop per creare e assegnare automaticamente un codice sconto unico ai nuovi account cliente. La configurazione del modulo è gestita tramite il metodo `getContent()` nel file principale del modulo, memorizzando le impostazioni in `ps_configuration`. Include un'interazione minima con il front-office, basandosi principalmente sul sistema di e-mail nativo di PrestaShop e sulla visualizzazione dell'account cliente per la consegna del voucher.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller amministrativo personalizzato per il Front-Office o il Back-Office. Tutta la logica è incapsulata all'interno del file principale del modulo e dei suoi hook registrati.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce alcuna classe personalizzata né estende `ObjectModel`. Interagisce direttamente con la classe `CartRule` principale di PrestaShop per creare e gestire i voucher.

### 4.4 Risorse JavaScript (`views/js/`)

-   `registervoucher/lib/voucherengine/script.js`
    -   **Ambito:** Potenzialmente Back-office, o uno script generico incluso per compatibilità.
    -   **Descrizione:** Data la funzione principale del modulo (generazione di voucher backend), questo script è probabilmente un'utilità o uno script di compatibilità. Potrebbe gestire miglioramenti dell'interfaccia utente nella pagina di configurazione, la convalida dei moduli o fornire correzioni di compatibilità per le versioni precedenti di PrestaShop, in particolare per quanto riguarda gli elementi dinamici del modulo o le interazioni AJAX all'interno del metodo `getContent()`. Senza ulteriori ispezioni, il suo scopo esatto è speculativo ma generalmente correlato al miglioramento dell'interfaccia di configurazione del modulo o alla garanzia della compatibilità tra le versioni per il pannello di amministrazione.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `registervoucher/css.css`

    -   **Ambito:** Probabilmente stile del modulo di amministrazione del Back-office.
    -   **Descrizione:** Questo foglio di stile probabilmente contiene stili personalizzati per la pagina di configurazione del modulo all'interno del Back Office di PrestaShop. Potrebbe regolare il layout, la spaziatura, i colori o l'aspetto di elementi specifici per garantire che il modulo di configurazione sia visivamente coerente o per applicare un branding personalizzato.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** `.registervoucher-config`, `.form-group`, `.control-label`, `.help-block` (specifici per l'HTML generato dal modulo).
-   `registervoucher/lib/voucherengine/ps16.css`

    -   **Ambito:** Stile del modulo di amministrazione del Back-office, specificamente per la compatibilità con PrestaShop 1.6.
    -   **Descrizione:** Questo foglio di stile è quasi certamente incluso per garantire che la pagina di configurazione del modulo venga renderizzata correttamente e in modo coerente con il tema del Back Office di PrestaShop 1.6. Affronta le differenze di stile tra PS 1.6 e le versioni più recenti, fornendo le sovrascritture necessarie o stili specifici per elementi come pulsanti, campi del modulo e contenitori di layout per mantenere un aspetto e una sensazione adeguati.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Specifici per il tema di amministrazione di PS 1.6, ad esempio, `.panel`, `.form-horizontal`, `.btn`.

### 4.6 Struttura del modello Smarty (`views/templates/`)

Il dossier del modulo non indica file `.tpl` personalizzati. Ciò suggerisce che il modulo di configurazione del modulo viene renderizzato direttamente all'interno del metodo `getContent()` utilizzando le classi helper di PrestaShop (ad esempio, `HelperForm`), e qualsiasi visualizzazione front-office (come il voucher nell'account cliente) viene gestita sovrascrivendo i modelli principali di PrestaShop o iniettando contenuto direttamente tramite hook senza modelli di modulo dedicati. Il contenuto dell'e-mail è gestito tramite i modelli di posta nativi di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle di database personalizzate.
    -   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` (ad esempio, `PS_REGISTERVOUCHER_DESCRIPTION`, `PS_REGISTERVOUCHER_CODE`, ecc.).
    -   I voucher generati sono memorizzati nelle tabelle principali di PrestaShop `ps_cart_rule` e `ps_cart_rule_lang`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Eseguito immediatamente dopo la creazione di un nuovo account cliente. | Questo è l'hook principale. Il modulo ascolta questo evento per attivare il processo di generazione e assegnazione del voucher per il cliente appena registrato. |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Spesso utilizzato per aggiungere CSS/JS, ma in questo modulo non è esplicitamente utilizzato per la visualizzazione del front-office. Potrebbe essere per la configurazione interna del modulo o la compatibilità. |
| `displayRightColumn` | Eseguito nella colonna destra del front-office. | Non utilizzato direttamente per la funzionalità principale del modulo di visualizzazione del voucher. |
| `displayLeftColumn` | Eseguito nella colonna sinistra del front-office. | Non utilizzato direttamente per la funzionalità principale del modulo di visualizzazione del voucher. |
| `displayFooter` | Eseguito nella sezione del piè di pagina di ogni pagina del front-office. | Non utilizzato direttamente per la funzionalità principale del modulo di visualizzazione del voucher. |
| `displayProductButtons` | Eseguito nella pagina del prodotto, vicino al pulsante "aggiungi al carrello". | Non utilizzato direttamente per la funzionalità principale del modulo di visualizzazione del voucher. |
| `displayCustomerAccount` | Eseguito nella pagina "Il mio account" del cliente. | Questo hook è cruciale per visualizzare il codice voucher generato direttamente nell'area dell'account del cliente, rendendolo facilmente accessibile. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Codice voucher dopo la registrazione", fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda relativa alla funzionalità del modulo.
