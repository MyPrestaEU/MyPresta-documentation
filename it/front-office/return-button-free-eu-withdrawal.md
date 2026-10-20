---
title: "Pulsante di Reso Gratuito - Recesso UE - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pulsante di Reso Gratuito - Recesso UE di MyPresta.eu."
sidebar:
  label: "Pulsante di Reso Gratuito - Recesso UE"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Return Button Free - EU Withdrawal su MyPresta.eu](https://mypresta.eu/modules/front-office-features/return-button-free-eu-withdrawal.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/return-button-free-eu-withdrawal/)
>
> ---


# Pulsante di Reso Gratuito - Recesso UE

## 1. Requisiti e Compatibilità
-   **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di Hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)
Questa è la schermata di configurazione principale del modulo, dove controlli il suo comportamento generale e l'aspetto.

#### Scheda Impostazioni Generali

-   **Abilita Modulo:**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo sul tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il pulsante di recesso e la funzionalità saranno attivi e visibili ai clienti in base alle altre tue impostazioni.
        -   *Quando disabilitato:* Le funzionalità del modulo saranno completamente nascoste dal front office e i clienti non potranno inviare richieste di recesso tramite esso.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Lo abiliteresti quando sei pronto a offrire l'opzione di recesso ai tuoi clienti. Potresti disabilitarlo temporaneamente durante la manutenzione o se devi apportare modifiche significative alla tua politica di reso.

-   **Visualizza Pulsante di Recesso In:**
    -   **Cosa fa questa impostazione:** Determina dove appare il pulsante principale "Richiesta di Recesso" nel front office del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Intestazione:* Il pulsante appare nella sezione superiore del tuo sito web, spesso visibile globalmente.
        -   *Colonna Sinistra:* Il pulsante appare nella barra laterale sinistra (se il tuo tema ne ha una).
        -   *Colonna Destra:* Il pulsante appare nella barra laterale destra (se il tuo tema ne ha una).
        -   *Pagina Prodotto:* Il pulsante appare sulle singole pagine dei prodotti.
        -   *Piè di pagina:* Il pulsante appare nella sezione inferiore del tuo sito web.
    -   **Valore consigliato:** Piè di pagina (spesso una buona posizione, discreta per i link legali) o Intestazione (per la massima visibilità). Scegli in base al layout del tuo tema e alla tua preferenza di prominenza.
    -   **Scenario / esempio del commerciante:** Se vuoi che i clienti trovino facilmente l'opzione, posizionarla nell'Intestazione o nel Piè di pagina è comune. Se preferisci che sia meno prominente ma comunque accessibile, una colonna potrebbe essere adatta.

-   **Consenti Richieste di Recesso Ospite:**
    -   **Cosa fa questa impostazione:** Controlla se i clienti che hanno effettuato il checkout senza creare un account possono comunque inviare una richiesta di recesso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Gli ospiti potranno accedere al modulo di recesso fornendo il riferimento dell'ordine e l'indirizzo email.
        -   *Quando disabilitato:* Solo i clienti registrati che hanno effettuato l'accesso ai loro account potranno inviare richieste di recesso.
    -   **Valore consigliato:** SÌ (Altamente raccomandato per la conformità UE, poiché il diritto di recesso si applica a tutti i consumatori, non solo a quelli registrati).
    -   **Scenario / esempio del commerciante:** Abilitare questa opzione garantisce la conformità ai diritti dei consumatori per tutti i clienti, indipendentemente dal loro metodo di checkout, ed evita di frustrare gli ospiti che non riescono a trovare un modo per recedere.

-   **Stati dell'Ordine per l'Idoneità al Recesso:**
    -   **Cosa fa questa impostazione:** Definisce quali stati dell'ordine rendono un ordine idoneo per una richiesta di recesso. Ad esempio, potresti consentire i recessi solo per gli ordini che sono stati "Consegnati" o "Spediti".
    -   **Effetto della modifica di questa impostazione:** I clienti vedranno l'opzione di recesso solo per gli ordini che corrispondono a uno degli stati selezionati nella loro cronologia ordini o quando inseriscono un riferimento di ordine ospite.
    -   **Valore consigliato:** Seleziona stati come "Pagamento accettato", "Preparazione in corso", "Spedito", "Consegnato". Evita stati come "Annullato" o "Rimborsato" poiché i recessi non sono applicabili lì.
    -   **Scenario / esempio del commerciante:** Vuoi consentire i recessi per gli ordini già elaborati o consegnati, ma non per gli ordini ancora in attesa di pagamento o già annullati.

-   **Stati dell'Ordine per la Conferma del Recesso:**
    -   **Cosa fa questa impostazione:** Specifica quale stato dell'ordine deve essere applicato automaticamente a un ordine una volta che una richiesta di recesso è stata inviata con successo dal cliente. Questo ti aiuta a identificare rapidamente gli ordini con richieste di recesso in sospeso.
    -   **Effetto della modifica di questa impostazione:** Quando un cliente invia un recesso, lo stato dell'ordine cambierà a quello che selezioni qui.
    -   **Valore consigliato:** Crea un nuovo stato dell'ordine distinto come "Recesso Richiesto" o "Recesso UE in Sospeso" nelle impostazioni degli stati dell'ordine di PrestaShop (sotto Parametri Negozio > Impostazioni Ordini > Stati) e selezionalo qui.
    -   **Scenario / esempio del commerciante:** Impostare uno stato specifico come "Recesso Richiesto" consente al tuo team di assistenza clienti di filtrare e gestire facilmente gli ordini che richiedono attenzione per un processo di recesso.

-   **Stati dell'Ordine per il Completamento del Recesso:**
    -   **Cosa fa questa impostazione:** Specifica quale stato dell'ordine deve essere applicato automaticamente a un ordine una volta che tu, il commerciante, hai elaborato e completato il recesso (ad esempio, emesso un rimborso).
    -   **Effetto della modifica di questa impostazione:** Dopo aver contrassegnato una richiesta di recesso come completata nell'interfaccia di amministrazione del modulo, lo stato dell'ordine associato si aggiornerà a questo stato scelto.
    -   **Valore consigliato:** Seleziona uno stato esistente come "Rimborsato" o creane uno nuovo come "Recesso UE Completato".
    -   **Scenario / esempio del commerciante:** Una volta elaborato il rimborso e chiuso il caso di recesso, l'aggiornamento dello stato dell'ordine a "Rimborsato" fornisce un registro chiaro sia per te che per il cliente.

-   **Abilita Statistiche:**
    -   **Cosa fa questa impostazione:** Controlla se il modulo raccoglie statistiche anonime sul suo utilizzo. Questi dati aiutano lo sviluppatore del modulo a migliorarlo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo invierà dati di utilizzo anonimi.
        -   *Quando disabilitato:* Nessun dato di utilizzo verrà inviato.
    -   **Valore consigliato:** SÌ (Aiuta a migliorare il modulo per tutti).
    -   **Scenario / esempio del commerciante:** Abiliti questa opzione per contribuire allo sviluppo del modulo, o la disabiliti se hai politiche di privacy dei dati rigorose che impediscono qualsiasi trasmissione di dati esterni.

#### Scheda Informazioni Legali

-   **Periodo di Recesso (Giorni):**
    -   **Cosa fa questa impostazione:** Definisce il numero di giorni di calendario che un cliente ha per esercitare il proprio diritto di recesso, a partire dal giorno in cui riceve la merce.
    -   **Effetto della modifica di questa impostazione:** Il modulo visualizzerà questo periodo ai clienti e lo utilizzerà internamente per eventuali calcoli di date o controlli di idoneità.
    -   **Valore consigliato:** 14 (Questo è il requisito legale minimo nell'UE, ma puoi offrire un periodo più lungo se lo desideri).
    -   **Scenario / esempio del commerciante:** Imposti questo valore a 14 giorni per conformarti alla legge UE. Se offri una politica di reso più generosa, potresti impostarlo a 30 giorni.

-   **Testo Modulo di Recesso:**
    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il testo introduttivo visualizzato nella parte superiore del modulo di richiesta di recesso. Questo è un campo multilingue.
    -   **Effetto della modifica di questa impostazione:** Il testo che inserisci apparirà ai clienti quando accedono al modulo di recesso.
    -   **Valore consigliato:** Fornisci istruzioni chiare e concise o una breve spiegazione del processo di recesso.
    -   **Scenario / esempio del commerciante:** Potresti aggiungere un messaggio come: "Si prega di compilare questo modulo per esercitare il diritto di recesso. Hai 14 giorni dal ricevimento del tuo ordine per inviare questa richiesta."

-   **Testo Email di Conferma:**
    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il testo incluso nell'email di conferma inviata ai clienti dopo che hanno inviato una richiesta di recesso. Questo è un campo multilingue.
    -   **Effetto della modifica di questa impostazione:** Il testo che inserisci farà parte dell'email che i clienti ricevono, fungendo da prova su supporto durevole della loro richiesta.
    -   **Valore consigliato:** Includi informazioni importanti come i passaggi successivi, dove inviare la merce e eventuali istruzioni specifiche per il reso.
    -   **Scenario / esempio del commerciante:** Potresti scrivere: "Grazie per la tua richiesta di recesso. La tua richiesta è stata ricevuta e sarà elaborata a breve. Si prega di restituire la merce a [Il tuo indirizzo di reso] entro 14 giorni. Per maggiori dettagli, si prega di fare riferimento alla nostra politica di reso."

-   **Link Politica di Recesso:**
    -   **Cosa fa questa impostazione:** Ti consente di fornire un link alla pagina dettagliata della politica di recesso o di reso del tuo negozio.
    -   **Effetto della modifica di questa impostazione:** Un link verrà visualizzato sul modulo di recesso, indirizzando i clienti alla tua politica completa.
    -   **Valore consigliato:** Fornisci l'URL della tua pagina CMS dedicata ai resi/recessi.
    -   **Scenario / esempio del commerciante:** Hai una pagina CMS intitolata "Politica Resi e Rimborsi" su `iltuonegozio.com/content/resi-rimborsi`. Inseriresti questo URL qui.

#### 2.1.1 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| **Scheda Impostazioni Generali** | Abilita Modulo | SÌ | Attiva/disattiva la funzionalità del modulo. |
| | Visualizza Pulsante di Recesso In | Piè di pagina / Intestazione | Imposta la posizione del pulsante principale di recesso. |
| | Consenti Richieste di Recesso Ospite | SÌ | Abilita il recesso per i clienti non registrati. |
| | Stati dell'Ordine per l'Idoneità al Recesso | Pagamento accettato, Spedito, Consegnato | Definisce quali stati dell'ordine consentono le richieste di recesso. |
| | Stati dell'Ordine per la Conferma del Recesso | "Recesso Richiesto" (Personalizzato) | Stato applicato all'ordine al momento dell'invio da parte del cliente. |
| | Stati dell'Ordine per il Completamento del Recesso | "Rimborsato" (Esistente) / "Recesso UE Completato" (Personalizzato) | Stato applicato all'ordine al momento del completamento da parte del commerciante. |
| | Abilita Statistiche | SÌ | Consente la raccolta di dati di utilizzo anonimi per il miglioramento del modulo. |
| **Scheda Informazioni Legali** | Periodo di Recesso (Giorni) | 14 | Imposta il periodo legale per il recesso. |
| | Testo Modulo di Recesso | Personalizzabile | Testo introduttivo sul modulo di recesso. |
| | Testo Email di Conferma | Personalizzabile | Testo incluso nell'email di conferma del recesso. |
| | Link Politica di Recesso | URL della tua pagina CMS | Link alla tua politica dettagliata di reso/recesso. |

### 2.2 Schermate di Amministrazione Dedicate e Viste del Controller

#### Richieste di Recesso (Back Office > Moduli > Pulsante di Reso Gratuito > Richieste di Recesso)
Questa schermata di amministrazione dedicata è dove gestisci tutte le richieste di recesso in arrivo dai tuoi clienti.

-   **Nome Schermata e Posizione Menu:** **Richieste di Recesso** (si trova sotto il menu principale "Moduli", quindi il sottomenu "Pulsante di Reso Gratuito").
-   **Azioni e Impostazioni Disponibili:**
    -   **Tabella di Elenco:** Visualizza un elenco completo di tutte le richieste di recesso.
        -   **ID:** Identificatore univoco per ogni richiesta.
        -   **Inviato:** Data e ora di invio della richiesta.
        -   **Ordine:** Il riferimento dell'ordine PrestaShop associato.
        -   **Nome, Cognome, Email:** Dettagli di contatto del cliente.
        -   **Ambito:** Indica se si tratta di un recesso dell'intero ordine (questa versione gratuita supporta solo il recesso dell'intero ordine).
        -   **Tipo:** Il tipo di recesso (es. "Recesso UE").
        -   **Stato:** Lo stato attuale della richiesta di recesso (es. "In sospeso", "Elaborato", "Annullato").
    -   **Visualizza Dettagli:** Clicca su qualsiasi richiesta nell'elenco per aprire una vista dettagliata.
        -   Questa vista fornisce tutte le informazioni inviate dal cliente, inclusi i dettagli dell'ordine, i prodotti e eventuali note aggiuntive.
        -   Puoi aggiungere note interne, modificare lo stato del recesso (es. da "In sospeso" a "Elaborato" o "Annullato") e tracciare la cronologia delle modifiche.
        -   L'impostazione "Stati dell'Ordine per il Completamento del Recesso" (dalla configurazione principale) verrà applicata all'ordine associato quando contrassegni un recesso come completato qui.
    -   **Filtro e Ricerca:** Puoi filtrare l'elenco per stato, nome cliente, ID ordine, ecc., per trovare rapidamente richieste specifiche.
-   **Effetto delle modifiche:**
    -   **Modifica dello Stato:** L'aggiornamento dello stato di una richiesta di recesso (es. a "Elaborato" o "Completato") aggiornerà il record nel modulo e, se configurato, lo stato dell'ordine PrestaShop associato. Questo ti aiuta a tracciare i progressi e a comunicare con i clienti.
    -   **Aggiunta di Note:** Le note interne sono per riferimento del tuo team e non sono visibili al cliente. Aiutano a documentare la comunicazione e le azioni intraprese per ogni recesso.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Controlla regolarmente la schermata "Richieste di Recesso" per nuove richieste "In sospeso".
    2.  Clicca su una richiesta per visualizzarne i dettagli.
    3.  Rivedi le informazioni del cliente e l'ordine associato.
    4.  Comunica con il cliente se necessario (es. fornisci istruzioni per la spedizione di reso).
    5.  Una volta ricevuta e ispezionata la merce, elabora il rimborso nella gestione ordini di PrestaShop.
    6.  Aggiorna lo stato della richiesta di recesso nel modulo a "Elaborato" o "Completato". Questo aggiornerà anche lo stato dell'ordine principale se hai configurato "Stati dell'Ordine per il Completamento del Recesso".
    7.  Aggiungi eventuali note interne pertinenti sul rimborso, i numeri di tracciamento o la comunicazione.

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

-   **D: Il pulsante di recesso non appare nel mio negozio.**
    -   **R:** Innanzitutto, controlla se il modulo è "Abilitato" nella sua configurazione. Quindi, verifica di aver selezionato una posizione per "Visualizza Pulsante di Recesso In" (es. Piè di pagina, Intestazione). Se il tuo tema è molto personalizzato, potrebbe non agganciarsi correttamente. Prova a selezionare una posizione di visualizzazione diversa. Inoltre, assicurati che la cache di Smarty sia stata svuotata (Parametri Avanzati > Prestazioni > Svuota cache).
-   **D: I clienti inviano richieste di recesso, ma lo stato dell'ordine non cambia.**
    -   **R:** Vai alla configurazione del modulo e controlla l'impostazione "Stati dell'Ordine per la Conferma del Recesso". Assicurati di aver selezionato uno stato dell'ordine appropriato lì. Se hai creato un nuovo stato, assicurati che sia configurato correttamente in PrestaShop (Parametri Negozio > Impostazioni Ordini > Stati).
-   **D: I clienti possono recedere da singoli prodotti di un ordine con questo modulo?**
    -   **R:** No, il modulo gratuito "Pulsante di Reso Gratuito - Recesso UE" è progettato solo per il **recesso dell'intero ordine**, come previsto dalla Direttiva UE. Se hai bisogno di gestire resi parziali per singoli prodotti, avresti bisogno di un modulo di gestione dei resi più avanzato.
-   **D: Il modulo è installato, ma il testo sul modulo o sull'email è nella lingua sbagliata o sembra generico.**
    -   **R:** Le impostazioni "Testo Modulo di Recesso" e "Testo Email di Conferma" sono campi multilingue. Assicurati di aver inserito il testo desiderato per ogni lingua abilitata nel tuo negozio. Puoi passare da una lingua all'altra utilizzando l'icona della bandiera accanto all'area di testo nella configurazione del modulo.
-   **D: Ho aggiornato il modulo e ora qualcosa non va. Cosa devo fare?**
    -   **R:** Dopo qualsiasi aggiornamento del modulo, è buona pratica svuotare la cache di PrestaShop. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache". Se il problema persiste, controlla le impostazioni di configurazione del modulo per assicurarti che siano ancora come ti aspetti.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Pulsante di Reso Gratuito - Recesso UE", destinata a sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura
Il modulo segue un modello MVC (Model-View-Controller) standard di PrestaShop. Sfrutta `ModuleFrontController` per le interazioni del front-office e `AdminController` per la gestione del back-office. `ObjectModel` viene utilizzato per l'archiviazione persistente dei dati relativi alle richieste di recesso. I servizi chiave e le classi helper incapsulano la logica di business e garantiscono la compatibilità tra le versioni di PrestaShop. Il modulo si integra con vari hook di PrestaShop per visualizzare la sua funzionalità.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office
Questi controller gestiscono le interazioni rivolte al cliente relative alle richieste di recesso.

-   `rbfree/controllers/front/confirm.php`
    *   Nome classe: `RbfConfirmModuleFrontController` (estende `RbfModuleFrontController`)
    *   Responsabilità: Visualizza il passaggio di conferma finale del modulo di recesso, consentendo al cliente di rivedere e inviare la propria richiesta. Gestisce l'invio POST per creare una nuova voce `RbfWithdrawal`.
-   `rbfree/controllers/front/form.php`
    *   Nome classe: `RbfFormModuleFrontController` (estende `RbfModuleFrontController`)
    *   Responsabilità: Renderizza il modulo iniziale di richiesta di recesso. Gestisce la convalida dell'input per il riferimento dell'ordine, l'email e i dettagli del cliente.
-   `rbfree/controllers/front/print.php`
    *   Nome classe: `RbfPrintModuleFrontController` (estende `RbfModuleFrontController`)
    *   Responsabilità: Fornisce una versione stampabile del modulo di richiesta di recesso, tipicamente dopo l'invio, per i registri del cliente.
-   `rbfree/controllers/front/RbfModuleFrontController.php`
    *   Nome classe: `RbfModuleFrontController` (estende `ModuleFrontController`)
    *   Responsabilità: Classe base per tutti i controller del front-office del modulo, che fornisce utilità comuni, controlli di sicurezza e assegnazioni di variabili Smarty.
-   `rbfree/controllers/front/status.php`
    *   Nome classe: `RbfStatusModuleFrontController` (estende `RbfModuleFrontController`)
    *   Responsabilità: Visualizza lo stato attuale di una specifica richiesta di recesso al cliente.
-   `rbfree/controllers/front/track.php`
    *   Nome classe: `RbfTrackModuleFrontController` (estende `RbfModuleFrontController`)
    *   Responsabilità: Consente ai clienti (inclusi gli ospiti) di tracciare la propria richiesta di recesso inserendo un riferimento dell'ordine e un'email.

#### Controller di Amministrazione Back-Office
Questi controller gestiscono l'interfaccia di amministrazione per le richieste di recesso.

-   `rbfree/controllers/admin/AdminRbfWithdrawalController.php`
    *   Nome classe: `AdminRbfWithdrawalController` (estende `ModuleAdminController`)
    *   Nome scheda: "Richieste di Recesso" (sotto "Moduli > Pulsante di Reso Gratuito")
    *   Entità gestita: `RbfWithdrawal`
    *   Responsabilità: Fornisce l'interfaccia CRUD (Create, Read, Update, Delete) per la gestione delle richieste di recesso. Visualizza un elenco di richieste, consente di visualizzare informazioni dettagliate, aggiornare lo stato e aggiungere note. Gestisce gli invii di moduli per modifiche di stato e note.

### 4.3 Classi e Modelli Core (`classes/`)

-   `rbfree/classes/RbfCompatibility.php`
    *   Nome classe: `RbfCompatibility`
    *   Responsabilità: Fornisce metodi helper per garantire la compatibilità tra diverse versioni di PrestaShop (es. gestione delle differenze nei metodi `Context` o `Tools`).
-   `rbfree/classes/RbfSecurity.php`
    *   Nome classe: `RbfSecurity`
    *   Responsabilità: Contiene metodi helper relativi alla sicurezza, come la generazione e la convalida di token, per proteggere i moduli dagli attacchi CSRF.
-   `rbfree/classes/RbfSelfHeal.php`
    *   Nome classe: `RbfSelfHeal`
    *   Responsabilità: Implementa la logica per l'auto-riparazione o i controlli diagnostici, garantendo l'integrità del modulo e la coerenza dei dati.
-   `rbfree/classes/RbfStatsService.php`
    *   Nome classe: `RbfStatsService`
    *   Responsabilità: Gestisce la raccolta e l'invio di statistiche di utilizzo anonime se abilitato dal commerciante.
-   `rbfree/classes/RbfWithdrawal.php`
    *   Nome classe: `RbfWithdrawal` (estende `ObjectModel`)
    *   Tabella database: `ps_rbf_withdrawal`
    *   Campi `$definition`: Definisce la struttura di una richiesta di recesso, inclusi `id_order`, `id_customer`, `firstname`, `lastname`, `email`, `status`, `date_add`, `date_upd`, ecc.
    *   Metodi pubblici chiave: `add()`, `update()`, `delete()`, metodi per recuperare i dettagli del recesso, gestire le transizioni di stato.
-   `rbfree/classes/RbfWithdrawalAttachment.php`
    *   Nome classe: `RbfWithdrawalAttachment` (estende `ObjectModel`)
    *   Tabella database: `ps_rbf_withdrawal_attachment`
    *   Campi `$definition`: Memorizza informazioni sui file allegati a una richiesta di recesso (se la versione Pro lo supporta).
    *   Metodi pubblici chiave: Metodi per la gestione degli allegati.
-   `rbfree/classes/RbfWithdrawalHistory.php`
    *   Nome classe: `RbfWithdrawalHistory` (estende `ObjectModel`)
    *   Tabella database: `ps_rbf_withdrawal_history`
    *   Campi `$definition`: Registra le modifiche allo stato di una richiesta di recesso o ad altri attributi chiave.
    *   Metodi pubblici chiave: `add()`, metodi per recuperare la cronologia.
-   `rbfree/classes/RbfWithdrawalNote.php`
    *   Nome classe: `RbfWithdrawalNote` (estende `ObjectModel`)
    *   Tabella database: `ps_rbf_withdrawal_note`
    *   Campi `$definition`: Memorizza le note interne aggiunte dagli amministratori a una richiesta di recesso.
    *   Metodi pubblici chiave: `add()`, metodi per recuperare le note.
-   `rbfree/classes/RbfWithdrawalProduct.php`
    *   Nome classe: `RbfWithdrawalProduct` (estende `ObjectModel`)
    *   Tabella database: `ps_rbf_withdrawal_product`
    *   Campi `$definition`: Memorizza i dettagli dei prodotti inclusi in una richiesta di recesso.
    *   Metodi pubblici chiave: Metodi per la gestione dei prodotti associati.
-   `rbfree/classes/RbfWithdrawalService.php`
    *   Nome classe: `RbfWithdrawalService`
    *   Responsabilità: Incapsula la logica di business principale per la gestione delle richieste di recesso, come la creazione di nuove richieste, l'aggiornamento degli stati degli ordini, l'invio di email e la convalida dell'idoneità.

### 4.4 Risorse JavaScript (`views/js/`)

-   `rbfree/views/js/admin-order-state-picker.js`
    *   Ambito: Back-office
    *   Dettagli: Gestisce la selezione interattiva degli stati dell'ordine nella configurazione del modulo, probabilmente per le impostazioni "Stati dell'Ordine per l'Idoneità/Conferma/Completamento del Recesso".
-   `rbfree/views/js/front.js`
    *   Ambito: Front-office
    *   Dettagli: Contiene JavaScript generale del front-office per il modulo. Questo potrebbe includere la convalida del modulo, gli invii AJAX per i moduli di recesso, il caricamento dinamico dei contenuti o le interazioni con il pulsante di recesso.
-   `rbfree/views/js/order-history.js`
    *   Ambito: Front-office (Account Cliente > Cronologia Ordini)
    *   Dettagli: Gestisce specificamente l'integrazione del link/pulsante di recesso all'interno della pagina della cronologia ordini del cliente, potenzialmente aggiungendo listener di eventi per mostrare/nascondere dinamicamente le opzioni in base allo stato dell'ordine.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `rbfree/views/css/admin-config.css`
    *   Ambito: Back-office (Configurazione Modulo)
    *   Dettagli: Stili per la pagina di configurazione principale del modulo (`configure.tpl`), garantendo un aspetto coerente all'interno dell'amministrazione di PrestaShop.
-   `rbfree/views/css/admin-dashboard.css`
    *   Ambito: Back-office (dashboard di AdminRbfWithdrawalController)
    *   Dettagli: Stili per la vista dashboard delle richieste di recesso, inclusi layout di tabella, indicatori di stato e layout generale.
-   `rbfree/views/css/admin-order-state-picker.css`
    *   Ambito: Back-office
    *   Dettagli: Stili per l'interfaccia di selezione dello stato dell'ordine utilizzata nella configurazione del modulo.
-   `rbfree/views/css/admin-pro-teaser.css`
    *   Ambito: Back-office
    *   Dettagli: Stili per gli elementi teaser della versione "Pro" all'interno dell'interfaccia di amministrazione del modulo gratuito.
-   `rbfree/views/css/admin-searchtool.css`
    *   Ambito: Back-office
    *   Dettagli: Stili per gli strumenti di ricerca e filtro all'interno dell'elenco di amministrazione dei recessi.
-   `rbfree/views/css/admin-withdrawal-view.css`
    *   Ambito: Back-office (vista AdminRbfWithdrawalController)
    *   Dettagli: Stili per la vista dettagliata di una singola richiesta di recesso nell'amministrazione, incluse note, cronologia ed elenchi di prodotti.
-   `rbfree/views/css/front-classic.css`
    *   Ambito: Front-office (tema Classic)
    *   Dettagli: Specifici aggiustamenti di stile per il tema Classic di PrestaShop, garantendo coerenza visiva con il design del tema.
-   `rbfree/views/css/front-hummingbird.css`
    *   Ambito: Front-office (tema Hummingbird)
    *   Dettagli: Specifici aggiustamenti di stile per il tema Hummingbird di PrestaShop, garantendo coerenza visiva con il design del tema.
-   `rbfree/views/css/front.css`
    *   Ambito: Front-office
    *   Dettagli: Stili generali del front-office per i moduli di recesso, i pulsanti e le pagine di stato, applicati a tutti i temi.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)
-   `rbfree/views/templates/hook/account-link-classic.tpl`
    *   Hook: `displayCustomerAccount` (o simile)
    *   Output: Un link nella dashboard dell'account cliente per il tema Classic.
-   `rbfree/views/templates/hook/account-link-hummingbird.tpl`
    *   Hook: `displayCustomerAccount` (o simile)
    *   Output: Un link nella dashboard dell'account cliente per il tema Hummingbird.
-   `rbfree/views/templates/hook/button-classic.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o simile)
    *   Output: Il pulsante principale di recesso per il tema Classic.
-   `rbfree/views/templates/hook/button-hummingbird.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o simile)
    *   Output: Il pulsante principale di recesso per il tema Hummingbird.
-   `rbfree/views/templates/hook/button.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o simile)
    *   Output: Pulsante principale di recesso generico, utilizzato come fallback o per elementi comuni.
-   `rbfree/views/templates/hook/order-detail-classic.tpl`
    *   Hook: `displayOrderDetail` (o simile)
    *   Output: Un link/pulsante di recesso all'interno della pagina dei dettagli dell'ordine per il tema Classic.
-   `rbfree/views/templates/hook/order-detail-hummingbird.tpl`
    *   Hook: `displayOrderDetail` (o simile)
    *   Output: Un link/pulsante di recesso all'interno della pagina dei dettagli dell'ordine per il tema Hummingbird.
-   `rbfree/views/templates/hook/order-detail.tpl`
    *   Hook: `displayOrderDetail` (o simile)
    *   Output: Link/pulsante di recesso generico all'interno della pagina dei dettagli dell'ordine.
-   `rbfree/views/templates/hook/order-withdrawal-notice.tpl`
    *   Hook: `displayAdminOrder` (o simile)
    *   Output: Un avviso o un riepilogo dello stato del recesso nella pagina di visualizzazione dell'ordine nel Back Office.

#### Template Admin (`views/templates/admin/`)
-   `rbfree/views/templates/admin/configure.tpl`
    *   Utilizzato da: `getContent()` in `rbfree/index.php`
    *   Output: Il modulo di configurazione principale del modulo nel Back Office.
-   `rbfree/views/templates/admin/dashboard.tpl`
    *   Utilizzato da: `AdminRbfWithdrawalController`
    *   Output: La vista dashboard che elenca tutte le richieste di recesso.
-   `rbfree/views/templates/admin/order-state-picker.tpl`
    *   Utilizzato da: Configurazione del modulo
    *   Output: Il widget interattivo di selezione dello stato dell'ordine.
-   `rbfree/views/templates/admin/order-withdrawal-notice.tpl`
    *   Utilizzato da: Hook `displayAdminOrder`
    *   Output: Un avviso sullo stato del recesso nella pagina di visualizzazione dell'ordine nel Back Office.
-   `rbfree/views/templates/admin/pro-teaser-dashboard-intro.tpl`
    *   Utilizzato da: `AdminRbfWithdrawalController`
    *   Output: Teaser introduttivo per la versione Pro nella dashboard.
-   `rbfree/views/templates/admin/pro-teaser-dashboard.tpl`
    *   Utilizzato da: `AdminRbfWithdrawalController`
    *   Output: Teaser generale della versione Pro nella dashboard.
-   `rbfree/views/templates/admin/pro-teaser-exclusions.tpl`
    *   Utilizzato da: Configurazione del modulo
    *   Output: Teaser per le funzionalità della versione Pro relative alle esclusioni.
-   `rbfree/views/templates/admin/pro-teaser-order-states.tpl`
    *   Utilizzato da: Configurazione del modulo
    *   Output: Teaser per le funzionalità della versione Pro relative agli stati dell'ordine.
-   `rbfree/views/templates/admin/pro-teaser-withdrawal-scope.tpl`
    *   Utilizzato da: Configurazione del modulo
    *   Output: Teaser per le funzionalità della versione Pro relative all'ambito del recesso.
-   `rbfree/views/templates/admin/pro-teaser.tpl`
    *   Utilizzato da: Varie sezioni di amministrazione
    *   Output: Teaser generico della versione Pro.
-   `rbfree/views/templates/admin/updates.tpl`
    *   Utilizzato da: Configurazione del modulo
    *   Output: Visualizza informazioni sugli aggiornamenti del modulo.
-   `rbfree/views/templates/admin/view.tpl`
    *   Utilizzato da: `AdminRbfWithdrawalController`
    *   Output: La pagina di visualizzazione dettagliata per una singola richiesta di recesso nel Back Office.

#### Template Front-office (`views/templates/front/`)
-   `rbfree/views/templates/front/confirm_step.tpl`
    *   Utilizzato da: `RbfConfirmModuleFrontController`
    *   Output: Il secondo passaggio del modulo di recesso, per la conferma.
-   `rbfree/views/templates/front/error.tpl`
    *   Utilizzato da: Vari controller frontali
    *   Output: Una pagina di messaggio di errore generico.
-   `rbfree/views/templates/front/form.tpl`
    *   Utilizzato da: `RbfFormModuleFrontController`
    *   Output: Il modulo iniziale di richiesta di recesso.
-   `rbfree/views/templates/front/print.tpl`
    *   Utilizzato da: `RbfPrintModuleFrontController`
    *   Output: La versione stampabile del modulo di recesso.
-   `rbfree/views/templates/front/status.tpl`
    *   Utilizzato da: `RbfStatusModuleFrontController`
    *   Output: La pagina che visualizza lo stato di una specifica richiesta di recesso.
-   `rbfree/views/templates/front/success.tpl`
    *   Utilizzato da: `RbfConfirmModuleFrontController`
    *   Output: Un messaggio di successo dopo l'invio di una richiesta di recesso.
-   `rbfree/views/templates/front/track.tpl`
    *   Utilizzato da: `RbfTrackModuleFrontController`
    *   Output: Il modulo per i clienti per tracciare la loro richiesta di recesso.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database
-   `ps_rbf_withdrawal`: Memorizza i dettagli principali della richiesta di recesso (id, id_order, id_customer, status, date, info cliente).
-   `ps_rbf_withdrawal_attachment`: Memorizza i dettagli di eventuali allegati a una richiesta di recesso.
-   `ps_rbf_withdrawal_history`: Memorizza un registro delle modifiche di stato e altri aggiornamenti per ogni richiesta di recesso.
-   `ps_rbf_withdrawal_note`: Memorizza le note interne aggiunte dagli amministratori a una richiesta di recesso.
-   `ps_rbf_withdrawal_product`: Memorizza i dettagli dei prodotti inclusi in una richiesta di recesso.
-   `ps_configuration`: Le impostazioni del modulo sono memorizzate qui con chiavi come `RBFREE_ENABLED`, `RBFREE_BUTTON_HOOK`, `RBFREE_ALLOW_GUEST`, ecc.

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta CSS/JS, o renderizza il pulsante di recesso se configurato. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine applicabili. | Renderizza il pulsante di recesso se configurato. |
| `displayRightColumn` | Nella barra laterale destra delle pagine applicabili. | Renderizza il pulsante di recesso se configurato. |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Renderizza il pulsante di recesso se configurato. |
| `displayProductButtons` | Sulla pagina del prodotto, vicino al pulsante "aggiungi al carrello". | Renderizza il pulsante di recesso se configurato. |
| `displayCustomerAccount` | Nella dashboard "Il mio account" del cliente. | Aggiunge un link al modulo di recesso. |
| `displayOrderDetail` | Nella pagina dei dettagli dell'ordine del cliente. | Aggiunge un link/pulsante per avviare il recesso per quell'ordine specifico. |
| `displayAdminOrder` | Nella pagina di visualizzazione dell'ordine del Back Office. | Visualizza un avviso o un riepilogo di qualsiasi richiesta di recesso associata. |
| `actionOrderStatusUpdate` | Quando lo stato di un ordine viene modificato. | Potenzialmente attiva azioni come l'aggiornamento dello stato del recesso o l'invio di notifiche. |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renderizzi il suo template. | Accoda file CSS e JavaScript del front-office. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renderizzi il suo template. | Accoda file CSS e JavaScript del back-office. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Crea tabelle del database, imposta la configurazione predefinita. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Rimuove tabelle del database, elimina la configurazione. |

## 5. Supporto Ufficiale e Aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Pulsante di Reso Gratuito - Recesso UE", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema tecnico o domanda che tu possa avere riguardo alla funzionalità del modulo.
