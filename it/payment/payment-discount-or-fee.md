---
title: "Sconto o Commissione di Pagamento - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Sconto o Commissione di Pagamento di MyPresta.eu."
sidebar:
  label: "Sconto o Commissione di Pagamento - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Payment Discount or Fee su MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-discount-or-fee.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/payment-discount-or-fee/)
>
> ---


# Sconto o Commissione di Pagamento

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting web moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Sconto o Commissione di Pagamento" offre un set completo di opzioni per controllare con precisione come vengono applicati sconti o commissioni.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Sconto o Commissione di Pagamento)

Questa è la schermata di configurazione principale in cui abiliti e imposti il comportamento principale del modulo.

- **Abilita Modulo:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo in tutto il tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo inizierà ad applicare sconti o commissioni in base alle tue regole definite durante il checkout.
    - *Quando disabilitato:* Il modulo cesserà tutte le operazioni e non verranno applicati sconti o commissioni.
  - **Valore consigliato:** SÌ (una volta configurate le tue regole).
  - **Scenario / esempio del commerciante:** Hai finito di impostare tutte le tue regole e sei pronto per andare online. Abilita questo per attivare il modulo. Se hai bisogno di disabilitarlo temporaneamente per manutenzione, impostalo su NO.
- **Visualizza Commissione/Sconto nel Riepilogo Carrello:**

  - **Cosa fa questa impostazione:** Controlla se l'aggiustamento del metodo di pagamento viene mostrato come una voce separata nel riepilogo del carrello *prima* che il cliente raggiunga il passaggio di pagamento.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti vedranno una voce come "Aggiustamento Metodo di Pagamento" nel riepilogo del carrello, anche prima di selezionare un metodo di pagamento, indicando che il prezzo finale potrebbe cambiare.
    - *Quando disabilitato:* L'aggiustamento apparirà solo una volta che il cliente seleziona un metodo di pagamento nella pagina di checkout.
  - **Valore consigliato:** SÌ (per trasparenza).
  - **Scenario / esempio del commerciante:** Vuoi che i clienti siano pienamente consapevoli di potenziali aggiustamenti di pagamento il prima possibile. L'abilitazione di questa opzione fornisce la massima trasparenza.
- **Applica Commissione/Sconto al Costo di Spedizione:**

  - **Cosa fa questa impostazione:** Determina se lo sconto o la commissione calcolati devono essere applicati anche al costo di spedizione dell'ordine, o solo al totale dei prodotti.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Se hai una commissione del 2% e il totale dei prodotti è $100 e la spedizione è $10, la commissione sarà il 2% di $110 ($2.20).
    - *Quando disabilitato:* La commissione del 2% si applicherebbe solo al totale dei prodotti di $100 ($2.00) e la spedizione rimarrebbe separata.
  - **Valore consigliato:** SÌ (se le commissioni del tuo gateway di pagamento si applicano anche al valore totale dell'ordine, inclusa la spedizione).
  - **Scenario / esempio del commerciante:** La maggior parte dei gateway di pagamento addebita una commissione percentuale sull'importo *totale* della transazione, inclusa la spedizione. L'abilitazione di questa opzione garantisce che la tua commissione rifletta accuratamente i tuoi costi.
- **Applica Commissione/Sconto all'IVA:**

  - **Cosa fa questa impostazione:** Determina se lo sconto o la commissione calcolati devono essere applicati anche all'importo dell'IVA dell'ordine, o solo al totale dei prodotti (e potenzialmente alla spedizione).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Se hai una commissione del 2% e il totale dei prodotti è $100, la spedizione $10 e l'IVA $20, la commissione sarà il 2% di $130 ($2.60).
    - *Quando disabilitato:* La commissione del 2% si applicherebbe solo al totale dei prodotti (e alla spedizione se abilitata) e l'IVA rimarrebbe separata.
  - **Valore consigliato:** SÌ (se le commissioni del tuo gateway di pagamento si applicano anche al valore totale dell'ordine, inclusa l'IVA).
  - **Scenario / esempio del commerciante:** Similmente alla spedizione, i gateway di pagamento di solito addebitano sul totale complessivo. L'abilitazione di questa opzione garantisce che il calcolo della tua commissione sia completo.
- **Etichetta Commissione/Sconto nel Carrello/Ordine:**

  - **Cosa fa questa impostazione:** Ti consente di personalizzare l'etichetta di testo che appare accanto all'importo dello sconto o della commissione nel riepilogo del carrello e nei dettagli dell'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su "Supplemento Metodo di Pagamento":* Verrà visualizzato questo testo.
    - *Quando impostato su "Sconto Pagamento":* Verrà visualizzato questo testo.
  - **Valore consigliato:** "Aggiustamento Metodo di Pagamento" o "Supplemento Pagamento" / "Sconto Pagamento" a seconda del tuo uso principale.
  - **Scenario / esempio del commerciante:** Utilizzi principalmente il modulo per aggiungere commissioni. Impostare l'etichetta su "Supplemento Pagamento" lo rende chiaro ai clienti. Se offri sconti, "Sconto Pagamento" è più appropriato.
- **URL Cron Job per la pulizia del log di controllo:**

  - **Cosa fa questa impostazione:** Fornisce un URL che puoi impostare come cron job sul tuo server per pulire automaticamente le voci obsolete dal log di controllo del modulo, impedendo che il database diventi troppo grande.
  - **Effetto della modifica di questa impostazione:**
    - *Quando configurato come cron job:* Il log di controllo verrà regolarmente purgato delle voci obsolete, migliorando le prestazioni del database.
    - *Quando non configurato:* Il log di controllo crescerà indefinitamente, rallentando potenzialmente il tuo Back Office nel tempo.
  - **Valore consigliato:** Imposta un cron job per eseguire questo URL quotidianamente o settimanalmente.
  - **Scenario / esempio del commerciante:** Vuoi mantenere il tuo database snello e veloce. Copia questo URL e aggiungilo allo scheduler dei cron job del tuo pannello di controllo hosting.

### 2.2 Schermata amministrativa dedicata: Regole Sconto o Commissione di Pagamento (Back Office > Pagamento > Regole Sconto o Commissione di Pagamento)

Questa schermata è dove definisci e gestisci tutte le regole per l'applicazione di sconti o commissioni.

- **Nome schermata e posizione nel menu:** **Regole Sconto o Commissione di Pagamento** (si trova sotto **Pagamento** nel menu principale del Back Office di PrestaShop).
- **Azioni e impostazioni disponibili:**

  - **Tabella di elenco delle regole:** Visualizza tutte le tue regole attualmente attive e inattive, mostrando il loro nome, metodo di pagamento, tipo (sconto/commissione), valore e stato.
  - **Pulsante "Aggiungi nuova regola":** Clicca qui per creare una nuova regola di sconto o commissione.
  - **Azioni Modifica/Elimina:** Per ogni regola nell'elenco, puoi cliccare per modificarne i dettagli o eliminarla.
  - **Campi del modulo per aggiungere/modificare una regola:**
    - **Nome regola:**
      - **Cosa fa questa impostazione:** Un nome descrittivo per la tua regola, visibile solo nel Back Office.
      - **Effetto della modifica di questa impostazione:** Ti aiuta a identificare e gestire facilmente le tue regole.
      - **Valore consigliato:** Chiaro e descrittivo (es. "Commissione PayPal 2%", "Sconto Bonifico Bancario 5%").
    - **Metodo di pagamento:**
      - **Cosa fa questa impostazione:** Seleziona a quale gateway o metodo di pagamento specifico si applica questa regola.
      - **Effetto della modifica di questa impostazione:** La regola si attiverà solo quando un cliente sceglie questo metodo di pagamento.
      - **Valore consigliato:** Scegli il metodo di pagamento esatto che vuoi targettizzare.
      - **Scenario / esempio del commerciante:** Vuoi aggiungere una commissione per "PayPal", quindi selezioni "PayPal" dal menu a discesa.
    - **Tipo:**
      - **Cosa fa questa impostazione:** Determina se la regola applica uno "Sconto" o una "Commissione".
      - **Effetto della modifica di questa impostazione:**
        - *Sconto:* Riduce il totale dell'ordine.
        - *Commissione:* Aumenta il totale dell'ordine.
      - **Valore consigliato:** Seleziona in base al tuo obiettivo (es. "Commissione" per i costi di elaborazione della carta di credito).
    - **Valore:**
      - **Cosa fa questa impostazione:** L'importo o la percentuale dello sconto/commissione.
      - **Effetto della modifica di questa impostazione:**
        - *Se "Tipo" è "Percentuale":* Inserisci "2" per il 2%.
        - *Se "Tipo" è "Importo Fisso":* Inserisci "5.00" per $5.00.
      - **Valore consigliato:** La percentuale o l'importo fisso esatto che desideri applicare.
    - **Tipo di valore:**
      - **Cosa fa questa impostazione:** Scegli se il "Valore" è una "Percentuale" del totale dell'ordine o un "Importo Fisso".
      - **Effetto della modifica di questa impostazione:** Dettaglia come viene interpretato il campo "Valore".
      - **Valore consigliato:** La percentuale è comune per le commissioni; l'importo fisso per sconti specifici.
    - **Importo minimo carrello (Opzionale):**
      - **Cosa fa questa impostazione:** Il totale minimo dell'ordine (prima dello sconto/commissione) richiesto per l'applicazione di questa regola.
      - **Effetto della modifica di questa impostazione:** Se il totale del carrello è inferiore a questo importo, la regola non verrà applicata.
      - **Valore consigliato:** Lascia vuoto se non è richiesto un minimo.
      - **Scenario / esempio del commerciante:** Vuoi applicare una commissione solo su ordini più grandi per evitare micro-commissioni su piccoli acquisti.
    - **Importo massimo carrello (Opzionale):**
      - **Cosa fa questa impostazione:** Il totale massimo dell'ordine (prima dello sconto/commissione) per l'applicazione di questa regola.
      - **Effetto della modifica di questa impostazione:** Se il totale del carrello è superiore a questo importo, la regola non verrà applicata.
      - **Valore consigliato:** Lascia vuoto se non è richiesto un massimo.
    - **Gruppi clienti (Opzionale):**
      - **Cosa fa questa impostazione:** Limita la regola a specifici gruppi di clienti (es. "Grossisti", "Ospiti").
      - **Effetto della modifica di questa impostazione:** Solo i clienti appartenenti ai gruppi selezionati saranno interessati da questa regola.
      - **Valore consigliato:** Seleziona "Tutti i gruppi clienti" a meno che tu non abbia strategie di prezzo specifiche basate sui gruppi.
      - **Scenario / esempio del commerciante:** Vuoi offrire uno sconto speciale ai tuoi "Clienti VIP" quando pagano tramite bonifico bancario.
    - **Paesi (Opzionale):**
      - **Cosa fa questa impostazione:** Limita la regola ai clienti di specifici paesi.
      - **Effetto della modifica di questa impostazione:** La regola si applicherà solo se l'indirizzo di spedizione del cliente si trova in uno dei paesi selezionati.
      - **Valore consigliato:** Seleziona "Tutti i paesi" a meno che tu non abbia strategie di pagamento specifiche per paese.
      - **Scenario / esempio del commerciante:** Hai commissioni di elaborazione più elevate per i pagamenti internazionali con carta di credito da determinate regioni.
    - **Prodotti da escludere (Opzionale):**
      - **Cosa fa questa impostazione:** Ti consente di specificare singoli prodotti che *non* devono essere inclusi nel calcolo dello sconto o della commissione.
      - **Effetto della modifica di questa impostazione:** Il valore di questi prodotti verrà sottratto dal totale del carrello *prima* che venga calcolata la percentuale o l'importo fisso.
      - **Valore consigliato:** Lascia vuoto a meno che prodotti specifici non debbano essere esenti.
      - **Scenario / esempio del commerciante:** Vendi alcuni prodotti a basso margine in cui l'applicazione di una commissione li renderebbe non redditizi, quindi li escludi.
    - **Stato (Abilita/Disabilita):**
      - **Cosa fa questa impostazione:** Attiva o disattiva una singola regola senza eliminarla.
      - **Effetto della modifica di questa impostazione:**
        - *Abilitato:* La regola è attiva e verrà applicata.
        - *Disabilitato:* La regola è inattiva e non verrà applicata.
      - **Valore consigliato:** Abilitato per le regole attive.
      - **Scenario / esempio del commerciante:** Vuoi mettere in pausa temporaneamente una regola per una promozione senza perdere la sua configurazione.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

  1. Inizia identificando quali metodi di pagamento comportano costi o offrono vantaggi che desideri trasferire.
  2. Clicca su "Aggiungi nuova regola".
  3. Dai alla regola un nome chiaro.
  4. Seleziona il metodo di pagamento target.
  5. Scegli "Commissione" o "Sconto" e inserisci il valore (percentuale o fisso).
  6. Affina la regola con importi minimi/massimi del carrello, gruppi di clienti, paesi o esclusioni di prodotti, se necessario.
  7. Abilita la regola e salva.
  8. Testa la regola sul tuo front office effettuando un ordine di prova.

### 2.3 Schermata amministrativa dedicata: Log di controllo Sconto o Commissione di Pagamento (Back Office > Pagamento > Log di controllo Sconto o Commissione di Pagamento)

Questa schermata fornisce un registro storico di tutte le istanze in cui il modulo ha applicato uno sconto o una commissione.

- **Nome schermata e posizione nel menu:** **Log di controllo Sconto o Commissione di Pagamento** (si trova sotto **Pagamento** nel menu principale del Back Office di PrestaShop).
- **Azioni e impostazioni disponibili:**
  - **Tabella di elenco dei log:** Visualizza le voci con dettagli come:
    - **ID Ordine:** L'ID dell'ordine in cui è stato applicato l'aggiustamento.
    - **Nome Cliente:** Il cliente che ha effettuato l'ordine.
    - **Metodo di Pagamento:** Il metodo di pagamento scelto.
    - **Regola Applicata:** Il nome della regola che ha attivato l'aggiustamento.
    - **Tipo di Aggiustamento:** Se era uno sconto o una commissione.
    - **Valore di Aggiustamento:** L'importo dello sconto o della commissione.
    - **Data:** Quando è stato applicato l'aggiustamento.
  - **Filtro e Ricerca:** Puoi filtrare il log per ID ordine, cliente, metodo di pagamento o data per trovare rapidamente voci specifiche.
  - **Effetto delle modifiche:** Questa schermata è solo per la visualizzazione; non puoi modificare direttamente le voci del log qui. Serve come un prezioso registro per la risoluzione dei problemi e l'analisi.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  - Rivedi regolarmente il log di controllo per assicurarti che le regole vengano applicate correttamente.
  - Usalo per risolvere le richieste dei clienti relative a discrepanze di prezzo.
  - Monitora il volume degli aggiustamenti per comprendere l'impatto delle tue regole.

### 2.4 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Abilita Modulo | SÌ | Interruttore principale per la funzionalità del modulo. |
|  | Visualizza Commissione/Sconto nel Riepilogo Carrello | SÌ | Mostra l'aggiustamento in anticipo nel carrello per trasparenza. |
|  | Applica Commissione/Sconto al Costo di Spedizione | SÌ | Include la spedizione nel calcolo della commissione/sconto. |
|  | Applica Commissione/Sconto all'IVA | SÌ | Include l'IVA nel calcolo della commissione/sconto. |
|  | Etichetta Commissione/Sconto nel Carrello/Ordine | "Aggiustamento Metodo di Pagamento" | Personalizza l'etichetta mostrata ai clienti. |
|  | URL Cron Job per la pulizia del log di controllo | (URL fornito) | Automatizza la pulizia delle voci obsolete del log di controllo. |
| **Regole Sconto o Commissione di Pagamento** | Nome Regola | (Nome descrittivo) | Nome interno per la regola. |
|  | Metodo di Pagamento | (Metodo specifico) | Seleziona il metodo di pagamento per la regola. |
|  | Tipo | Commissione / Sconto | Determina se è un aumento o una diminuzione. |
|  | Valore | (Valore numerico) | L'importo o la percentuale dell'aggiustamento. |
|  | Tipo di Valore | Percentuale / Importo Fisso | Come viene interpretato il 'Valore'. |
|  | Importo Minimo Carrello | (Vuoto) | Totale minimo dell'ordine per l'applicazione della regola. |
|  | Importo Massimo Carrello | (Vuoto) | Totale massimo dell'ordine per l'applicazione della regola. |
|  | Gruppi Clienti | Tutti i Gruppi Clienti | Limita la regola a specifici gruppi di clienti. |
|  | Paesi | Tutti i Paesi | Limita la regola a specifici paesi. |
|  | Prodotti da Escludere | (Vuoto) | Prodotti il cui valore è escluso dal calcolo. |
|  | Stato | Abilitato | Attiva o disattiva la regola. |
| **Log di controllo Sconto o Commissione di Pagamento** | (Tutti i campi) | (Solo Visualizzazione) | Fornisce un registro storico degli aggiustamenti applicati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei sconti/commissioni non vengono visualizzati nella pagina di checkout. Cosa devo controllare?**
R1:

- **Modulo Abilitato?** Vai su **Moduli > Gestione moduli** e assicurati che "Sconto o Commissione di Pagamento" sia abilitato.
- **Regole Attive?** Naviga su **Pagamento > Regole Sconto o Commissione di Pagamento** e verifica che le tue regole specifiche siano abilitate (colonna Stato).
- **Condizioni della Regola Soddisfatte?** Ricontrolla se il totale del carrello, il gruppo clienti, il paese o le condizioni dei prodotti esclusi delle tue regole sono soddisfatte dal tuo ordine di prova.
- **Metodo di Pagamento Selezionato?** L'aggiustamento appare solo *dopo* che un metodo di pagamento è stato selezionato nella pagina di checkout (a meno che "Visualizza Commissione/Sconto nel Riepilogo Carrello" non sia abilitato).
- **Svuota Cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (in alto a destra). A volte, i dati della cache obsoleti impediscono che le modifiche appaiano immediatamente.

**D2: L'importo dello sconto/commissione sembra errato.**
R2:

- **Tipo di Valore (Percentuale vs. Fisso):** Assicurati di aver selezionato il "Tipo di Valore" corretto (Percentuale o Importo Fisso) per la tua regola.
- **Applica a Spedizione/IVA:** Controlla la configurazione principale del modulo se "Applica Commissione/Sconto al Costo di Spedizione" e "Applica Commissione/Sconto all'IVA" sono abilitati o disabilitati, poiché ciò influisce sull'importo base per i calcoli percentuali.
- **Prodotti Esclusi:** Se hai prodotti esclusi dal calcolo, assicurati che il loro valore sia correttamente sottratto prima che venga applicata la percentuale/l'importo fisso.
- **Valuta:** Assicurati che la valuta predefinita del tuo negozio sia impostata correttamente in PrestaShop, poiché il modulo si basa su questo per gli importi fissi.

**D3: Il modulo sta causando un conflitto con un altro modulo o il mio tema.**
R3:

- **Identifica il Conflitto:** Prova a disabilitare altri moduli uno per uno per individuare quale sta causando il conflitto.
- **Sovrascritture del Tema:** Se hai un tema fortemente personalizzato, potrebbe sovrascrivere i template di checkout di PrestaShop su cui il modulo si basa. Controlla la cartella `templates/checkout/` del tuo tema per file come `payment.tpl` o `cart-summary.tpl`.
- **Contatta il Supporto:** Se sospetti un conflitto, raccogli i dettagli (messaggi di errore, passaggi per riprodurre) e contatta il supporto MyPresta.eu.

**D4: Come traduco l'"Etichetta Commissione/Sconto" in altre lingue?**
R4:

- Vai su **Internazionale > Traduzioni**.
- Seleziona "Traduzioni dei moduli installati", il tuo tema e la lingua che desideri tradurre.
- Trova il modulo "Sconto o Commissione di Pagamento". Dovresti vedere il campo per tradurre l'impostazione "Etichetta Commissione/Sconto nel Carrello/Ordine".

**D5: Il mio log di controllo sta diventando troppo grande. Come lo gestisco?**
R5:

- Nella configurazione principale del modulo, troverai un "URL Cron Job per la pulizia del log di controllo".
- Copia questo URL e impostalo come cron job sul tuo server di hosting. La maggior parte dei pannelli di controllo hosting (cPanel, Plesk) ha una sezione "Cron Jobs" dove puoi aggiungere un nuovo job.
- Impostalo per essere eseguito quotidianamente o settimanalmente (es. `wget -q -O /dev/null "IL_TUO_URL_CRON_QUI"`). Questo rimuoverà automaticamente le voci di log obsolete e manterrà il tuo database ottimizzato.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Sconto o Commissione di Pagamento" per sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'Architettura

Il modulo "Sconto o Commissione di Pagamento" segue un modello MVC (Model-View-Controller) standard di PrestaShop, con una forte enfasi sugli hook per integrarsi nel flusso di checkout. Utilizza `ObjectModel` per la gestione delle regole e dei log di controllo, e controller personalizzati sia per le interazioni AJAX del front-office che per la gestione del back-office. La logica principale per il calcolo e l'applicazione di commissioni/sconti è incapsulata in classi motore dedicate, garantendo la separazione delle preoccupazioni. Le classi di compatibilità sono utilizzate per colmare le differenze tra PrestaShop 1.7, 8 e 9.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/ajax.php`
  - **Nome Classe:** `PaydisorfeeAjaxModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Gestisce le richieste AJAX dalla pagina di checkout. Quando un cliente seleziona un metodo di pagamento, questo controller riceve la richiesta, calcola lo sconto/commissione applicabile in base alle regole attive e restituisce i dati riepilogativi del carrello aggiornati (es. nuovo totale, voce di commissione/sconto) da visualizzare dinamicamente.
- `controllers/front/cron.php`
  - **Nome Classe:** `PaydisorfeeCronModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Fornisce l'endpoint per il cron job di pulizia del log di controllo. Quando viene acceduto, attiva la logica di pulizia all'interno del modulo, rimuovendo le voci di log obsolete in base alle politiche di conservazione configurate.
- `controllers/front/index.php`
  - **Nome Classe:** `PaydisorfeeIndexModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Un controller frontale segnaposto, tipicamente utilizzato per le pagine predefinite del modulo o per prevenire l'elenco delle directory. In questo modulo, la sua funzione principale potrebbe essere quella di gestire il routing predefinito se non viene richiesta alcuna azione specifica, oppure potrebbe reindirizzare alla pagina principale del negozio.

#### Controller Amministrativi Back-Office

- `controllers/admin/AdminPaydisorfeeAuditLog.php`
  - **Nome Classe:** `AdminPaydisorfeeAuditLogController` (estende `ModuleAdminController`)
  - **Nome Tab:** Log di controllo Sconto o Commissione di Pagamento
  - **Entità Gestita:** `PaydisorfeeAuditLog` (mappa alla tabella del database `paydisorfee_log`)
  - **Responsabilità:** Gestisce la visualizzazione e il filtraggio delle voci del log di controllo nel Back Office di PrestaShop. Utilizza `HelperList` per renderizzare la vista a griglia dei record di log.
- `controllers/admin/AdminPaydisorfeeRules.php`
  - **Nome Classe:** `AdminPaydisorfeeRulesController` (estende `ModuleAdminController`)
  - **Nome Tab:** Regole Sconto o Commissione di Pagamento
  - **Entità Gestita:** `PaydisorfeeRule` (mappa alla tabella del database `paydisorfee_rule`)
  - **Responsabilità:** Fornisce l'interfaccia per creare, modificare, eliminare ed elencare le regole di sconto/commissione di pagamento. Utilizza `HelperList` per la panoramica delle regole e `HelperForm` per i moduli di aggiunta/modifica delle regole, inclusi i selettori dinamici per prodotti, gruppi di clienti e paesi.
- `controllers/admin/index.php`
  - **Nome Classe:** `PaydisorfeeAdminIndexModuleFrontController` (estende `ModuleAdminController`)
  - **Responsabilità:** Simile al front `index.php`, questo potrebbe servire come controller amministrativo predefinito o un reindirizzatore se non viene richiesta alcuna azione specifica per il contesto amministrativo.

### 4.3 Classi e Modelli Core (`classes/`)

- `classes/index.php`: File vuoto standard per prevenire l'elenco delle directory.
- `classes/PaydisorfeeAdmin.php`
  - **Responsabilità:** Probabilmente contiene metodi helper o funzioni di utilità specifiche per l'amministrazione del Back Office, potenzialmente per la gestione delle sottomissioni di moduli, la validazione dei dati o il rendering di componenti amministrativi specifici.
- `classes/PaydisorfeeAuditLog.php`
  - **Estende:** `ObjectModel`
  - **Tabella Database:** `paydisorfee_log`
  - **Campi `$definition`:** Definisce la struttura delle voci del log di controllo (es. `id_order`, `id_customer`, `payment_method`, `rule_name`, `type`, `value`, `date_add`).
  - **Metodi Pubblici Chiave:** Metodi per aggiungere nuove voci di log, recuperare i dati del log e potenzialmente per operazioni di pulizia.
- `classes/PaydisorfeeCartState.php`
  - **Responsabilità:** Gestisce lo stato del carrello durante il processo di checkout, in particolare in relazione allo sconto/commissione applicato dal modulo. Probabilmente memorizza e recupera l'aggiustamento calcolato per garantire che persista attraverso i diversi passaggi del checkout e sia correttamente applicato all'ordine.
- `classes/PaydisorfeeCompatibility.php`
  - **Responsabilità:** Contiene metodi per gestire i problemi di compatibilità tra diverse versioni di PrestaShop (1.7.x, 8.x, 9.x). Questa classe astrae il codice specifico della versione, come le differenze nei nomi degli hook, nelle strutture delle classi o nelle chiamate API, garantendo che il modulo funzioni correttamente su tutte le versioni supportate.
- `classes/PaydisorfeeDashboard.php`
  - **Responsabilità:** Probabilmente fornisce dati o logica per un potenziale dashboard o vista analitica all'interno dell'interfaccia di amministrazione del modulo, riassumendo l'impatto di sconti/commissioni.
- `classes/PaydisorfeeEngine.php`
  - **Responsabilità:** Questa è la classe logica principale per il calcolo e l'applicazione dello sconto o della commissione. Prende il carrello corrente, il metodo di pagamento selezionato e le regole attive come input, quindi determina l'importo finale dell'aggiustamento. Gestisce i calcoli percentuali vs. fissi, gli importi minimi/massimi del carrello e le esclusioni di prodotti.
- `classes/PaydisorfeeFeeProduct.php`
  - **Responsabilità:** Potenzialmente una classe helper per creare un "prodotto virtuale" per rappresentare la commissione/sconto nel carrello, consentendone la visualizzazione come voce di riga. Questa è una tecnica comune in PrestaShop per integrare aggiustamenti di prezzo dinamici nel riepilogo del carrello.
- `classes/PaydisorfeeLog.php`
  - **Responsabilità:** Questo potrebbe essere un alias o una versione precedente di `PaydisorfeeAuditLog.php`, o un meccanismo di logging più semplice per scopi di debug.
- `classes/PaydisorfeeRule.php`
  - **Estende:** `ObjectModel`
  - **Tabella Database:** `paydisorfee_rule`
  - **Campi `$definition`:** Definisce la struttura di una regola di pagamento (es. `name`, `id_payment_module`, `type`, `value`, `value_type`, `min_cart_amount`, `max_cart_amount`, `customer_groups`, `countries`, `excluded_products`, `active`).
  - **Metodi Pubblici Chiave:** Metodi per operazioni CRUD sulle regole, recupero delle regole attive e validazione delle condizioni delle regole.

### 4.4 Risorse JavaScript (`views/js/`)

- `paydisorfee/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office (utilizzato in `AdminPaydisorfeeRules` per il selettore di esclusione prodotti).
  - **Descrizione:** Fornisce la funzionalità di autocompletamento per la ricerca di prodotti durante la configurazione del campo "Prodotti da escludere" in una regola. Probabilmente invia richieste AJAX a un controller del back-office per recuperare suggerimenti di prodotti.
- `paydisorfee/views/js/adminPaydisorfeeDashboard.js`
  - **Ambito:** Back-office (se esiste una vista dashboard).
  - **Descrizione:** JavaScript per eventuali funzionalità di dashboard o analisi all'interno dell'interfaccia di amministrazione del modulo. Ciò potrebbe includere il rendering di grafici, il filtraggio dei dati o il caricamento dinamico dei contenuti.
- `paydisorfee/views/js/adminPaydisorfeeSelector.js`
  - **Ambito:** Back-office (utilizzato in `AdminPaydisorfeeRules`).
  - **Descrizione:** Gestisce la selezione dinamica di gruppi di clienti, paesi e potenzialmente metodi di pagamento all'interno del modulo di configurazione delle regole. Potrebbe gestire caselle di selezione multiple o fornire elementi interattivi per questi campi.
- `paydisorfee/views/js/checkout.js`
  - **Ambito:** Front-office (pagina di checkout).
  - **Descrizione:** Questo è uno script critico per la funzionalità del front-office. Ascolta i cambiamenti nel metodo di pagamento selezionato nella pagina di checkout. Quando viene scelto un metodo di pagamento, attiva una chiamata AJAX a `controllers/front/ajax.php` per ricalcolare il totale del carrello e aggiornare dinamicamente il riepilogo dell'ordine con la nuova voce di sconto/commissione. Gestisce anche la logica di visualizzazione per questi aggiornamenti.

### 4.5 Fogli di stile CSS (`views/css/`)

- `paydisorfee/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office.
  - **Descrizione:** Stili per l'input di ricerca con autocompletamento e il suo menu a discesa di suggerimenti, utilizzati nel selettore di esclusione prodotti all'interno della configurazione delle regole.
- `paydisorfee/views/css/admin_paydisorfee.css`
  - **Ambito:** Back-office.
  - **Descrizione:** Stili generali per le pagine del Back Office del modulo, inclusi l'elenco delle regole, il log di controllo e i moduli di configurazione. Garantisce un aspetto e una sensazione coerenti con il tema di amministrazione di PrestaShop.
- `paydisorfee/views/css/front.css`
  - **Ambito:** Front-office.
  - **Descrizione:** Stili per la visualizzazione della voce di sconto/commissione e di eventuali messaggi correlati nella pagina di checkout o nel riepilogo del carrello. Garantisce che l'aggiustamento sia chiaramente visibile e ben integrato nel design del negozio.

### 4.6 Struttura del Template Smarty (`views/templates/`)

- `paydisorfee/lib/searchTool/views/scripts.tpl`
  - **Ambito:** Back-office.
  - **Descrizione:** Contiene codice Smarty per includere JavaScript e potenzialmente CSS per lo strumento di ricerca (es. `autocomplete.js`). È probabilmente incluso nel modulo `AdminPaydisorfeeRules`.
- `paydisorfee/views/templates/admin/auditPreview.tpl`
  - **Ambito:** Back-office (AdminPaydisorfeeAuditLogController).
  - **Descrizione:** Template per il rendering delle voci del log di controllo, tipicamente utilizzato da `HelperList` per visualizzare la griglia dei dati.
- `paydisorfee/views/templates/admin/cron_setup.tpl`
  - **Ambito:** Back-office (Configurazione principale del modulo).
  - **Descrizione:** Visualizza l'URL del cron job e le istruzioni per la sua configurazione, come visto nella pagina di configurazione principale del modulo.
- `paydisorfee/views/templates/admin/rulesPreview.tpl`
  - **Ambito:** Back-office (AdminPaydisorfeeRulesController).
  - **Descrizione:** Template per il rendering dell'elenco delle regole di pagamento, utilizzato da `HelperList` per visualizzare la griglia dei dati.
- `paydisorfee/views/templates/admin/scopeSelector.tpl`
  - **Ambito:** Back-office (AdminPaydisorfeeRulesController).
  - **Descrizione:** Template per i selettori dinamici (gruppi di clienti, paesi, prodotti da escludere) all'interno del modulo di configurazione delle regole, spesso utilizzato in combinazione con `adminPaydisorfeeSelector.js`.
- `paydisorfee/views/templates/hook/admin_order.tpl`
  - **Ambito:** Back-office (Hook `displayAdminOrderTabContent` o simile).
  - **Descrizione:** Visualizza le informazioni sullo sconto o sulla commissione di pagamento applicati all'interno della pagina dei dettagli dell'ordine di PrestaShop nel Back Office. Ciò consente agli amministratori di vedere l'aggiustamento direttamente sull'ordine.
- `paydisorfee/views/templates/hook/payment_top.tpl`
  - **Ambito:** Front-office (Hook `displayPaymentTop` o simile).
  - **Descrizione:** Questo template è probabilmente utilizzato per visualizzare le informazioni dinamiche di sconto/commissione nella pagina di checkout, di solito sopra la selezione del metodo di pagamento, o come parte del riepilogo dell'ordine. Viene aggiornato da `checkout.js` tramite AJAX.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

- `ps_paydisorfee_log`: Memorizza le voci del log di controllo per ogni sconto o commissione applicati.
  - `id_paydisorfee_log` (CHIAVE PRIMARIA)
  - `id_order` (INT)
  - `id_customer` (INT)
  - `payment_method` (VARCHAR)
  - `rule_name` (VARCHAR)
  - `type` (VARCHAR, 'discount' o 'fee')
  - `value` (DECIMAL)
  - `date_add` (DATETIME)
- `ps_paydisorfee_rule`: Memorizza la configurazione per ogni regola di sconto/commissione di pagamento.
  - `id_paydisorfee_rule` (CHIAVE PRIMARIA)
  - `name` (VARCHAR)
  - `id_payment_module` (INT)
  - `type` (VARCHAR, 'discount' o 'fee')
  - `value` (DECIMAL)
  - `value_type` (VARCHAR, 'percentage' o 'fixed')
  - `min_cart_amount` (DECIMAL)
  - `max_cart_amount` (DECIMAL)
  - `customer_groups` (TEXT, array serializzato di ID)
  - `countries` (TEXT, array serializzato di ID)
  - `excluded_products` (TEXT, array serializzato di ID)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_configuration`: Le impostazioni del modulo sono memorizzate qui con chiavi come `PAYDISORFEE_ENABLED`, `PAYDISORFEE_DISPLAY_CART`, `PAYDISORFEE_APPLY_SHIPPING`, `PAYDISORFEE_APPLY_TAX`, `PAYDISORFEE_LABEL`.

#### Tabella degli Hook Registrati

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Prima del rendering del controller frontale | Registra CSS (`front.css`) e JS (`checkout.js`) del front-office. |
| `actionAdminControllerSetMedia` | Prima del rendering del controller amministrativo | Registra CSS (`admin_paydisorfee.css`, `autocomplete.css`) e JS (`adminPaydisorfeeDashboard.js`, `adminPaydisorfeeSelector.js`, `autocomplete.js`) del back-office. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina | Potenzialmente per il caricamento di JS/CSS globali o meta tag. |
| `displayPaymentTop` | Nella parte superiore del blocco di selezione del pagamento nella pagina di checkout | Visualizza le informazioni dinamiche di commissione/sconto al cliente. |
| `actionCartSummary` | Dopo la generazione del riepilogo del carrello | Utilizzato per iniettare la voce di commissione/sconto nel riepilogo del carrello. |
| `actionPaymentConfirmation` | Dopo che un ordine è stato effettuato con successo | Registra lo sconto/commissione applicato nel log di controllo. |
| `actionValidateOrder` | Quando un ordine viene convalidato | Assicura che il totale finale dell'ordine rifletta l'aggiustamento del metodo di pagamento. |
| `displayAdminOrderTabContent` | All'interno della pagina dei dettagli dell'ordine nel Back Office | Visualizza i dettagli dell'aggiustamento del pagamento per l'ordine. |
| `displayAdminOrder` | Nella pagina dei dettagli dell'ordine nel Back Office | Simile a `displayAdminOrderTabContent`, per la visualizzazione dei dati del modulo specifici dell'ordine. |
| `actionGetExtraMailTemplateVars` | Prima dell'invio di un'e-mail di conferma dell'ordine | Inietta i dettagli di commissione/sconto nei template delle e-mail. |
| `actionObjectOrderAddAfter` | Dopo l'aggiunta di un nuovo oggetto ordine | Potenzialmente per l'elaborazione finale o la registrazione relativa all'ordine. |
| `actionObjectOrderUpdateAfter` | Dopo l'aggiornamento di un oggetto ordine | Potenzialmente per la rivalutazione delle commissioni se un ordine viene modificato. |
| `actionObjectCartUpdateAfter` | Dopo l'aggiornamento di un oggetto carrello | Attiva il ricalcolo di potenziali commissioni/sconti. |
| `actionObjectCartAddAfter` | Dopo l'aggiunta di un nuovo oggetto carrello | Attiva il ricalcolo di potenziali commissioni/sconti. |
| `actionAjaxDie` | Prima di `die()` nel contesto AJAX | Consente al modulo di eseguire azioni prima dell'invio della risposta AJAX. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del Back Office | Registra JS/CSS amministrativi globali. |
| `displayModuleConfigureExtraButtons` | Nella pagina di configurazione del modulo | Aggiunge pulsanti extra (es. "Gestisci Regole", "Visualizza Log di Controllo"). |
| `displayPaymentOptions` | Visualizza le opzioni di pagamento al checkout | Potenzialmente modifica le opzioni di pagamento in base alle regole. |
| `actionPaymentOptionsModifier` | Modifica le opzioni di pagamento prima della visualizzazione | Consente al modulo di aggiungere/rimuovere/modificare le opzioni di pagamento. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Sconto o Commissione di Pagamento", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
