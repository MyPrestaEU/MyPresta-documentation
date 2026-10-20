---
title: "Pulsante Reso UE – Modulo di Recesso Online - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pulsante Reso UE – Modulo di Recesso Online di MyPresta.eu."
sidebar:
  label: "Pulsante Reso UE – Modulo di Recesso Online - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo EU Return Button – Online Withdrawal Form su MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/eu-return-button-online-withdrawal-form/)
>
> ---


# Pulsante Reso UE – Modulo di Recesso Online

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili nella maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove controlli il comportamento generale e l'aspetto del pulsante e del modulo di reso.

#### Scheda Impostazioni Generali

-   **Abilita Modulo:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il pulsante di reso e il modulo di recesso online diventano attivi e visibili ai clienti in base alle altre impostazioni.
        -   *Quando disabilitato:* Il modulo è completamente disattivato. Il pulsante non apparirà e i moduli non saranno accessibili.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Lo disabiliteresti solo se desideri temporaneamente interrompere l'offerta di resi online, magari durante la manutenzione o un cambio di politica.
-   **Visualizza Pulsante Reso In:**

    -   **Cosa fa questa impostazione:** Determina dove apparirà il pulsante principale "Reso" o "Recesso" nel front office del tuo negozio. Puoi selezionare più posizioni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato (ad esempio, Header):* Un pulsante apparirà nella posizione scelta, fornendo un link diretto al modulo di reso.
        -   *Quando deselezionato:* Il pulsante non apparirà in quella specifica posizione.
    -   **Valore consigliato:** Header e/o Footer per un facile accesso, e Pagina Prodotto per informare i clienti in anticipo.
    -   **Scenario / esempio del commerciante:** Se vuoi che i clienti trovino facilmente l'opzione di reso da qualsiasi pagina, abilita "Header" e "Footer". Se vuoi enfatizzare la tua politica di reso sulle pagine dei prodotti, abilita "Pagina Prodotto".
-   **Testo Pulsante:**

    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il testo visualizzato sul pulsante di reso.
    -   **Effetto della modifica di questa impostazione:** Il testo sul pulsante cambierà al valore specificato.
    -   **Valore consigliato:** "Richiesta di Reso", "Modulo di Recesso Online" o "Avvia un Reso".
    -   **Scenario / esempio del commerciante:** Potresti cambiarlo da "Reso" a "Modulo di Recesso" per allinearti a una terminologia legale specifica nella tua regione.
-   **Stato Minimo Ordine per Recesso:**

    -   **Cosa fa questa impostazione:** Definisce lo stato dell'ordine più precoce in cui un cliente può avviare una richiesta di reso per un ordine. Gli ordini con uno stato inferiore a questo non saranno idonei.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Pagamento accettato":* I clienti possono richiedere un reso solo dopo che il loro pagamento è stato elaborato con successo.
        -   *Quando impostato su "Spedito":* I clienti possono richiedere un reso solo dopo che il loro ordine è stato contrassegnato come spedito.
    -   **Valore consigliato:** "Pagamento accettato" o "Spedito", a seconda della tua politica.
    -   **Scenario / esempio del commerciante:** Se accetti resi solo per articoli che sono stati effettivamente pagati ed elaborati, imposta questo su "Pagamento accettato". Se accetti resi solo per articoli che hanno già lasciato il tuo magazzino, impostalo su "Spedito".
-   **Giorni Massimi per Recesso:**

    -   **Cosa fa questa impostazione:** Imposta il numero massimo di giorni dopo l'effettuazione di un ordine (o la spedizione, a seconda della tua politica) durante i quali un cliente può inviare una richiesta di reso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 14:* I clienti hanno 14 giorni dalla data dell'ordine per richiedere un reso. Dopo 14 giorni, l'opzione non sarà più disponibile per quell'ordine.
        -   *Quando impostato su 30:* I clienti hanno 30 giorni.
    -   **Valore consigliato:** 14 (per la conformità standard UE) o 30 (se offri un periodo di reso esteso).
    -   **Scenario / esempio del commerciante:** Per rispettare il diritto di recesso standard di 14 giorni dell'UE, imposta questo su 14. Se offri una politica più generosa, puoi estenderlo a 30 o più.
-   **Consenti Recessi Ospiti:**

    -   **Cosa fa questa impostazione:** Determina se i clienti che hanno effettuato il checkout come ospiti (senza creare un account) possono utilizzare il modulo di recesso online.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti ospiti possono accedere al modulo fornendo il loro riferimento d'ordine e l'indirizzo email.
        -   *Quando disabilitato:* Solo i clienti registrati che hanno effettuato l'accesso possono avviare un reso.
    -   **Valore consigliato:** SÌ (per la massima comodità del cliente e la conformità UE).
    -   **Scenario / esempio del commerciante:** L'abilitazione di questa opzione garantisce che tutti i clienti, indipendentemente dal loro metodo di checkout, possano facilmente avviare un reso, il che è fondamentale per la conformità e la soddisfazione del cliente.
-   **Consenti Allegati:**

    -   **Cosa fa questa impostazione:** Consente ai clienti di caricare file (ad esempio, foto di prodotti danneggiati, prova d'acquisto) quando inviano la loro richiesta di reso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un campo di caricamento apparirà sul modulo.
        -   *Quando disabilitato:* I clienti non possono caricare file.
    -   **Valore consigliato:** SÌ (specialmente per prodotti in cui potrebbe essere necessaria una prova visiva per danni o difetti).
    -   **Scenario / esempio del commerciante:** Se vendi articoli fragili, consentire gli allegati aiuta i clienti a fornire rapidamente prove di danni, accelerando il processo di risoluzione.
-   **Dimensione Massima Allegato (MB):**

    -   **Cosa fa questa impostazione:** Imposta la dimensione massima del file per ogni allegato che un cliente può caricare.
    -   **Effetto della modifica di questa impostazione:** I file più grandi di questo limite verranno rifiutati dal modulo.
    -   **Valore consigliato:** 2-5 MB.
    -   **Scenario / esempio del commerciante:** L'impostazione di un limite ragionevole impedisce ai clienti di caricare file eccessivamente grandi che potrebbero rallentare il tuo server o il sistema di posta elettronica.
-   **Estensioni Allegati Consentite (separate da virgola):**

    -   **Cosa fa questa impostazione:** Specifica quali tipi di file (ad esempio, jpg, png, pdf) i clienti sono autorizzati a caricare.
    -   **Effetto della modifica di questa impostazione:** Saranno accettati solo file con queste estensioni.
    -   **Valore consigliato:** jpg, jpeg, png, gif, pdf.
    -   **Scenario / esempio del commerciante:** Limitare ai formati di immagine e documento comuni garantisce di ricevere file utilizzabili e previene caricamenti dannosi.
-   **Richiedi Messaggio di Stato:**

    -   **Cosa fa questa impostazione:** Quando modifichi lo stato di una richiesta di reso nel back office, questa impostazione determina se sei tenuto ad aggiungere un messaggio al cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un campo di input per un messaggio sarà obbligatorio quando si aggiorna uno stato di reso.
        -   *Quando disabilitato:* Puoi cambiare gli stati senza aggiungere un messaggio.
    -   **Valore consigliato:** SÌ (per una comunicazione chiara e tracce di controllo).
    -   **Scenario / esempio del commerciante:** L'abilitazione di questa opzione garantisce che il tuo team fornisca sempre un motivo o un aggiornamento al cliente quando cambia lo stato, migliorando la trasparenza.

#### Scheda Stati Ordine

Questa scheda ti consente di definire i vari stati per le richieste di reso e come interagiscono con gli stati degli ordini PrestaShop esistenti.

-   **Nuovo Stato Recesso:**

    -   **Cosa fa questa impostazione:** Seleziona lo stato dell'ordine PrestaShop che verrà assegnato a una nuova richiesta di reso quando viene inviata per la prima volta da un cliente.
    -   **Effetto della modifica di questa impostazione:** Tutte le nuove richieste di reso verranno automaticamente contrassegnate con questo stato nel tuo back office.
    -   **Valore consigliato:** Crea un nuovo stato d'ordine personalizzato come "Reso Richiesto" o "Recesso in Sospeso" per una chiara identificazione.
    -   **Scenario / esempio del commerciante:** Creando uno stato specifico "Reso Richiesto", il tuo team di assistenza clienti può facilmente filtrare e identificare le nuove richieste di reso che richiedono la loro attenzione.
-   **Stato Recesso Accettato:**

    -   **Cosa fa questa impostazione:** Seleziona lo stato dell'ordine PrestaShop che verrà assegnato quando tu, come commerciante, accetti la richiesta di reso di un cliente.
    -   **Effetto della modifica di questa impostazione:** Quando contrassegni un reso come "Accettato" nel modulo, il suo stato cambierà a questo stato dell'ordine selezionato.
    -   **Valore consigliato:** Crea un nuovo stato d'ordine personalizzato come "Reso Accettato" o "Recesso Approvato".
    -   **Scenario / esempio del commerciante:** Una volta che hai esaminato una richiesta e l'hai approvata, cambiare il suo stato in "Reso Accettato" può attivare un'email al cliente con ulteriori istruzioni.
-   **Stato Recesso Rifiutato:**

    -   **Cosa fa questa impostazione:** Seleziona lo stato dell'ordine PrestaShop che verrà assegnato quando rifiuti la richiesta di reso di un cliente.
    -   **Effetto della modifica di questa impostazione:** Quando contrassegni un reso come "Rifiutato" nel modulo, il suo stato cambierà a questo stato dell'ordine selezionato.
    -   **Valore consigliato:** Crea un nuovo stato d'ordine personalizzato come "Reso Rifiutato" o "Recesso Rifiutato".
    -   **Scenario / esempio del commerciante:** Se una richiesta di reso non rientra nella tua politica (ad esempio, oltre la finestra di reso), cambieresti il suo stato in "Reso Rifiutato" e idealmente invieresti un messaggio che ne spieghi il motivo.
-   **Stato Recesso Chiuso:**

    -   **Cosa fa questa impostazione:** Seleziona lo stato dell'ordine PrestaShop che verrà assegnato quando una richiesta di reso è completata o risolta (ad esempio, rimborso emesso, sostituzione inviata).
    -   **Effetto della modifica di questa impostazione:** Quando contrassegni un reso come "Chiuso" nel modulo, il suo stato cambierà a questo stato dell'ordine selezionato.
    -   **Valore consigliato:** Crea un nuovo stato d'ordine personalizzato come "Reso Completato" o "Recesso Chiuso".
    -   **Scenario / esempio del commerciante:** Dopo che un rimborso è stato elaborato, contrassegnare il reso come "Reso Completato" fornisce una chiara traccia di controllo e lo rimuove dalla tua coda di resi attivi.
-   **Stati Ordine da Escludere dal Recesso:**

    -   **Cosa fa questa impostazione:** Ti consente di selezionare stati d'ordine PrestaShop specifici per i quali i clienti *non possono* avviare una richiesta di reso, anche se soddisfano altri criteri.
    -   **Effetto della modifica di questa impostazione:** Gli ordini con uno qualsiasi degli stati selezionati non mostreranno l'opzione di reso al cliente.
    -   **Valore consigliato:** "Annullato", "Rimborsato", "Errore" o qualsiasi altro stato che indichi che un ordine non è più idoneo per una nuova richiesta di reso.
    -   **Scenario / esempio del commerciante:** Se un ordine è già stato "Rimborsato", non vorresti che un cliente potesse inviare un'altra richiesta di reso per esso.

### 2.2 Schermate Amministrative Dedicate e Viste Controller

#### Richieste di Recesso (Back Office > Ordini > Richieste di Recesso)

Questo è l'hub centrale per la gestione di tutte le richieste di reso e recesso inviate dai tuoi clienti.

-   **Nome schermata e posizione menu:** Puoi trovare questa schermata navigando su **Ordini > Richieste di Recesso** nel menu del tuo back office PrestaShop.
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Visualizza un elenco completo di tutte le richieste di reso, inclusi:
        -   **ID:** Identificatore univoco per la richiesta.
        -   **Nome Cliente:** Il cliente che ha inviato la richiesta.
        -   **Riferimento Ordine:** L'ordine PrestaShop associato.
        -   **Data:** Quando la richiesta è stata inviata.
        -   **Stato:** Lo stato attuale della richiesta (ad esempio, "Reso Richiesto", "Reso Accettato").
        -   **Azioni:** Pulsanti per "Visualizzare" i dettagli della richiesta, cambiarne lo stato o eseguire altre attività di gestione.
    -   **Filtro e ricerca:** Puoi filtrare l'elenco per stato, cliente, riferimento ordine e intervallo di date per trovare rapidamente richieste specifiche.
    -   **Azioni di massa:** Ti consente di selezionare più richieste ed eseguire azioni come cambiarne lo stato contemporaneamente.
    -   **Visualizza dettagli:** Cliccando su "Visualizza" per una richiesta specifica si apre una pagina dettagliata dove puoi:
        -   Vedere tutte le informazioni fornite dal cliente (motivo, commenti, file allegati).
        -   Rivedere i prodotti inclusi nella richiesta di reso.
        -   Visualizzare una cronologia delle modifiche di stato e delle note interne.
        -   Aggiungere note private per la comunicazione interna del team.
        -   Cambiare lo stato della richiesta (ad esempio, da "Reso Richiesto" a "Reso Accettato").
        -   Inviare messaggi al cliente (se "Richiedi Messaggio di Stato" è abilitato).
        -   Scaricare allegati.
        -   Stampare il modulo di recesso.
-   **Effetto delle modifiche:**
    -   **Modifica dello stato:** Aggiorna lo stato della richiesta di reso, il che può attivare notifiche email al cliente e aggiornare la visualizzazione nel suo account cliente.
    -   **Aggiunta di note:** Registra la comunicazione interna o le decisioni relative alla richiesta, visibili solo agli utenti del back office.
    -   **Invio di messaggi:** Comunica direttamente con il cliente riguardo alla sua richiesta di reso.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Controlla regolarmente l'elenco "Richieste di Recesso" per nuove richieste (stato "Reso Richiesto").
    2.  Esamina ogni nuova richiesta, controllando i dettagli dell'ordine, i commenti del cliente e gli eventuali allegati.
    3.  Decidi se accettare o rifiutare la richiesta in base alla politica di reso del tuo negozio.
    4.  Cambia lo stato di conseguenza (ad esempio, a "Reso Accettato" o "Reso Rifiutato"). Se "Richiedi Messaggio di Stato" è abilitato, fornisci un messaggio chiaro al cliente.
    5.  Procedi con i passaggi successivi (ad esempio, emetti un rimborso, organizza la spedizione di reso) e aggiorna lo stato a "Reso Completato" una volta risolto.
    6.  Usa le note interne per la comunicazione del team o per registrare azioni specifiche intraprese.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di Configurazione Modulo** | Abilita Modulo | SÌ | Attiva/disattiva l'intero modulo. |
| | Visualizza Pulsante Reso In | Header, Footer, Pagina Prodotto | Controlla dove appare il pulsante di reso nel front office. |
| | Testo Pulsante | "Richiesta di Reso" | Personalizza il testo sul pulsante di reso. |
| | Stato Minimo Ordine per Recesso | "Pagamento accettato" | Imposta lo stato dell'ordine più precoce per l'idoneità al reso. |
| | Giorni Massimi per Recesso | 14 | Definisce la finestra di reso in giorni dalla data dell'ordine. |
| | Consenti Recessi Ospiti | SÌ | Consente ai clienti non registrati di utilizzare il modulo. |
| | Consenti Allegati | SÌ | Abilita/disabilita il caricamento di file sul modulo. |
| | Dimensione Massima Allegato (MB) | 2-5 MB | Imposta la dimensione massima per i file caricati. |
| | Estensioni Allegati Consentite | jpg, jpeg, png, gif, pdf | Specifica i tipi di file consentiti per i caricamenti. |
| | Richiedi Messaggio di Stato | SÌ | Rende obbligatorio un messaggio quando si cambia lo stato del reso. |
| **Scheda Stati Ordine** | Nuovo Stato Recesso | "Reso Richiesto" (personalizzato) | Stato per le richieste appena inviate. |
| | Stato Recesso Accettato | "Reso Accettato" (personalizzato) | Stato quando il commerciante approva una richiesta. |
| | Stato Recesso Rifiutato | "Reso Rifiutato" (personalizzato) | Stato quando il commerciante rifiuta una richiesta. |
| | Stato Recesso Chiuso | "Reso Completato" (personalizzato) | Stato quando una richiesta è completamente risolta. |
| | Stati Ordine da Escludere dal Recesso | "Annullato", "Rimborsato" | Impedisce i resi per gli ordini con questi stati. |
| **Richieste di Recesso (Admin)** | Visualizza/Modifica Richiesta | N/A | Gestisci le singole richieste di reso, cambia stato, aggiungi note. |
| | Filtra/Cerca | N/A | Individua richieste specifiche in base a vari criteri. |
| | Azioni di Massa | N/A | Esegui azioni su più richieste selezionate. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il pulsante di reso non appare nel mio negozio. Cosa devo fare?**
R1:

-   **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli**, trova "Pulsante Reso UE – Modulo di Recesso Online" e assicurati che sia "Abilitato".
-   **Controlla le posizioni di visualizzazione:** Nella configurazione del modulo, nella scheda "Impostazioni Generali", verifica di aver selezionato almeno una posizione "Visualizza Pulsante Reso In" (ad esempio, Header, Footer).
-   **Svuota la cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte, il vecchio contenuto della cache impedisce la visualizzazione di nuovi elementi del modulo.
-   **Compatibilità del tema:** Sebbene il modulo sia progettato per un'ampia compatibilità, i temi personalizzati potrebbero richiedere piccole modifiche. Se il pulsante non appare ancora, contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D2: I clienti segnalano di non poter inviare un reso per un ordine specifico, anche se rientra nel periodo di reso.**
R2:

-   **Controlla lo stato minimo dell'ordine:** Nella configurazione del modulo, in "Impostazioni Generali", rivedi "Stato Minimo Ordine per Recesso". Assicurati che l'ordine del cliente abbia raggiunto questo stato. Ad esempio, se è impostato su "Spedito" e l'ordine è ancora "Pagamento accettato", non vedranno l'opzione.
-   **Controlla gli stati dell'ordine esclusi:** Nella configurazione del modulo, nella scheda "Stati Ordine", controlla "Stati Ordine da Escludere dal Recesso". Se l'ordine del cliente ha uno di questi stati (ad esempio, "Annullato", "Rimborsato"), non sarà in grado di avviare un nuovo reso.
-   **Giorni massimi per il recesso:** Ricontrolla l'impostazione "Giorni Massimi per Recesso". La finestra di reso potrebbe essere scaduta per quell'ordine specifico.

**D3: Ho cambiato un'impostazione, ma non si riflette nel front office.**
R3:

-   **Svuota la cache:** Questa è la ragione più comune. Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione in qualsiasi modulo. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache". Se utilizzi un modulo di caching di terze parti o un CDN, svuota anche le loro cache.
-   **Cache del browser:** Chiedi ai tuoi clienti (o a te stesso) di svuotare la cache del browser o prova a visualizzare la pagina in una finestra in incognito/privata per escludere problemi di caching lato browser.

**D4: Come posso tradurre il testo del modulo in altre lingue?**
R4:

-   Vai su **Internazionale > Traduzioni** nel tuo back office PrestaShop.
-   Seleziona "Traduzioni dei moduli installati".
-   Scegli il tuo tema, la lingua che desideri tradurre e quindi seleziona "Pulsante Reso UE – Modulo di Recesso Online" dall'elenco dei moduli.
-   Vedrai quindi un elenco di tutte le stringhe traducibili all'interno del modulo, inclusi il testo del pulsante, le etichette del modulo e i messaggi. Inserisci le tue traduzioni e salva.

**D5: Voglio personalizzare l'aspetto del modulo di reso per abbinarlo al mio tema.**
R5:

-   Il modulo include file CSS (`front-classic.css`, `front-hummingbird.css`, `front.css`) progettati per i temi PrestaShop comuni.
-   Per uno stile avanzato, avrai bisogno di uno sviluppatore web. Possono ispezionare la struttura HTML del modulo e sovrascrivere le sue regole CSS nel file `custom.css` del tuo tema o creando un nuovo foglio di stile che si carica dopo il CSS del modulo. Evita di modificare direttamente i file CSS del modulo, poiché le tue modifiche andranno perse durante gli aggiornamenti.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo "Pulsante Reso UE – Modulo di Recesso Online" (`rbpro`) segue l'architettura MVC (Model-View-Controller) standard di PrestaShop. Sfrutta `ModuleFrontController` per le interazioni lato cliente e `AdminController` per la gestione del back-office. La logica di business principale è incapsulata in classi di servizio e ObjectModel dedicate, garantendo l'integrità dei dati e la separazione delle preoccupazioni. Il modulo si integra con il sistema di hook di PrestaShop per l'iniezione dinamica di contenuti e utilizza Smarty per il templating. Include anche livelli di compatibilità per diverse versioni di PrestaShop e una classe di sicurezza per la convalida degli input.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono le interazioni del cliente relative al modulo di reso e al tracciamento dello stato.

-   `rbpro/controllers/front/confirm.php`

    -   **Nome Classe:** `RbpConfirmModuleFrontController` (estende `RbpModuleFrontController`)
    -   **Responsabilità:** Visualizza il passaggio di conferma finale del modulo di recesso. Elabora i dati del modulo inviati, crea la voce `RbpWithdrawal` e reindirizza alla pagina di successo o di errore. Gestisce la convalida dei dati prima del salvataggio.
-   `rbpro/controllers/front/form.php`

    -   **Nome Classe:** `RbpFormModuleFrontController` (estende `RbpModuleFrontController`)
    -   **Responsabilità:** Renderizza il modulo di recesso online principale. Gestisce la visualizzazione iniziale degli ordini/prodotti idonei, elabora le selezioni dell'utente e prepara i dati per il passaggio di conferma. Gestisce l'accesso degli ospiti tramite riferimento d'ordine ed email.
-   `rbpro/controllers/front/print.php`

    -   **Nome Classe:** `RbpPrintModuleFrontController` (estende `RbpModuleFrontController`)
    -   **Responsabilità:** Fornisce una versione stampabile del modulo di recesso o dei dettagli della richiesta. Tipicamente utilizzato dai clienti da includere con il loro pacco restituito.
-   `rbpro/controllers/front/RbpModuleFrontController.php`

    -   **Nome Classe:** `RbpModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Questa è una classe base per tutti i controller front-office all'interno del modulo `rbpro`. Fornisce funzionalità comuni come l'impostazione dei breadcrumb, la gestione delle risorse specifiche del modulo e potenzialmente controlli di sicurezza condivisi o l'inizializzazione dei dati.
-   `rbpro/controllers/front/status.php`

    -   **Nome Classe:** `RbpStatusModuleFrontController` (estende `RbpModuleFrontController`)
    -   **Responsabilità:** Visualizza lo stato attuale e la cronologia di una specifica richiesta di reso al cliente. Accessibile tramite un link di tracciamento univoco o dall'account del cliente.
-   `rbpro/controllers/front/track.php`

    -   **Nome Classe:** `RbpTrackModuleFrontController` (estende `RbpModuleFrontController`)
    -   **Responsabilità:** Fornisce un'interfaccia semplice per i clienti (specialmente gli ospiti) per inserire un riferimento d'ordine e un'email per tracciare lo stato della loro richiesta di recesso.

#### Controller Admin Back-Office

-   `rbpro/controllers/admin/AdminRbpWithdrawalController.php`
    -   **Nome Classe:** `AdminRbpWithdrawalController` (estende `ModuleAdminController`)
    -   **Nome Tab:** "Richieste di Recesso" (sotto "Ordini")
    -   **Entità Gestita:** `RbpWithdrawal`
    -   **Responsabilità:** Gestisce l'elenco, la visualizzazione, la modifica e gli aggiornamenti di stato di tutte le richieste di recesso dei clienti nel back office di PrestaShop. Implementa `renderList()` per la tabella di panoramica e `renderForm()` per la vista dettagliata di una singola richiesta. Gestisce azioni come il cambio di stato, l'aggiunta di note e la gestione degli allegati.

### 4.3 Classi e Modelli Core (`classes/`)

-   `rbpro/classes/index.php`

    -   **Responsabilità:** File `index.php` vuoto standard per prevenire l'elenco delle directory.
-   `rbpro/classes/RbpCompatibility.php`

    -   **Responsabilità:** Fornisce metodi statici per gestire problemi di compatibilità tra diverse versioni di PrestaShop (ad esempio, logica specifica per `_PS_VERSION_`, sostituzioni di funzioni deprecate). Garantisce che il modulo funzioni correttamente da PS 1.6 a 9.x.
-   `rbpro/classes/RbpSecurity.php`

    -   **Responsabilità:** Contiene metodi statici per attività relative alla sicurezza, come la convalida degli input, la sanificazione e potenzialmente la generazione/verifica di token CSRF per moduli specifici.
-   `rbpro/classes/RbpStatsService.php`

    -   **Responsabilità:** Una classe di servizio responsabile della raccolta e potenzialmente dell'elaborazione di statistiche relative alle richieste di recesso (ad esempio, numero di richieste, tempo medio di elaborazione).
-   `rbpro/classes/RbpWithdrawal.php`

    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `rbp_withdrawal`
    -   **Campi `$definition`:** Definisce la struttura di una richiesta di recesso, inclusi campi come `id_customer`, `id_order`, `id_order_state`, `reference`, `email`, `date_add`, `date_upd`, `status`, `reason`, `message`, ecc.
    -   **Metodi Pubblici Chiave:** Metodi per operazioni CRUD sulle richieste di recesso, recupero di prodotti associati, cronologia e note.
-   `rbpro/classes/RbpWithdrawalAttachment.php`

    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `rbp_withdrawal_attachment`
    -   **Campi `$definition`:** Definisce la struttura per gli allegati collegati a una richiesta di recesso, inclusi `id_rbp_withdrawal`, `filename`, `original_filename`, `mime_type`, `date_add`.
    -   **Metodi Pubblici Chiave:** Metodi per la gestione dei file allegati (caricamento, recupero, eliminazione).
-   `rbpro/classes/RbpWithdrawalHistory.php`

    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `rbp_withdrawal_history`
    -   **Campi `$definition`:** Definisce la cronologia delle modifiche di stato per una richiesta di recesso, inclusi `id_rbp_withdrawal`, `id_order_state`, `id_employee`, `message`, `date_add`.
    -   **Metodi Pubblici Chiave:** Metodi per la registrazione e il recupero delle modifiche di stato e dei messaggi associati.
-   `rbpro/classes/RbpWithdrawalNote.php`

    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `rbp_withdrawal_note`
    -   **Campi `$definition`:** Definisce le note interne aggiunte dai dipendenti a una richiesta di recesso, inclusi `id_rbp_withdrawal`, `id_employee`, `note`, `date_add`.
    -   **Metodi Pubblici Chiave:** Metodi per l'aggiunta e il recupero di note interne.
-   `rbpro/classes/RbpWithdrawalProduct.php`

    -   **Estende:** `ObjectModel`
    -   **Tabella Database:** `rbp_withdrawal_product`
    -   **Campi `$definition`:** Definisce i prodotti specifici inclusi in una richiesta di recesso, collegandosi a `id_rbp_withdrawal`, `id_order_detail`, `id_product`, `id_product_attribute`, `quantity`, `reason`.
    -   **Metodi Pubblici Chiave:** Metodi per la gestione dell'elenco dei prodotti all'interno di una richiesta di reso.
-   `rbpro/classes/RbpWithdrawalService.php`

    -   **Responsabilità:** Una classe di livello di servizio che orchestra la logica di business complessa che coinvolge più ObjectModel correlati a `RbpWithdrawal`. Esempi includono la creazione di una nuova richiesta di recesso (che coinvolge `RbpWithdrawal`, `RbpWithdrawalProduct`, `RbpWithdrawalHistory`), l'aggiornamento del suo stato, l'invio di notifiche email e la gestione degli allegati.

### 4.4 Risorse JavaScript (`views/js/`)

-   `rbpro/lib/searchTool/views/js/autocomplete.js`

    -   **Ambito:** Back-office (probabilmente per la ricerca di ordini/clienti nei moduli di amministrazione).
    -   **Dettagli:** Implementa la funzionalità di autocompletamento per i campi di input, tipicamente per la ricerca di clienti o ordini durante la creazione/modifica manuale delle richieste di recesso nel back office. Si lega agli eventi `keyup` ed effettua chiamate AJAX per recuperare i suggerimenti.
-   `rbpro/views/js/admin-order-state-picker.js`

    -   **Ambito:** Back-office (configurazione del modulo e `AdminRbpWithdrawalController`).
    -   **Dettagli:** Migliora i menu a discesa di selezione dello stato dell'ordine nella configurazione del modulo e potenzialmente nella vista dettagliata del recesso. Può aggiungere segnali visivi o capacità di filtro.
-   `rbpro/views/js/front.js`

    -   **Ambito:** Front-office (moduli di recesso e pagine di stato).
    -   **Dettagli:** Gestisce le interazioni lato client sul modulo di recesso, come:
        -   Selezione dinamica del prodotto in base all'ordine.
        -   Convalida dei campi del modulo prima dell'invio.
        -   Chiamate AJAX per l'invio del modulo o il caricamento dei dati.
        -   Visualizzazione di messaggi o gestione del caricamento di file.
-   `rbpro/views/js/order-history.js`

    -   **Ambito:** Front-office (account cliente > cronologia ordini).
    -   **Dettagli:** Integra il pulsante o il link "Richiedi Reso" nella pagina della cronologia ordini del cliente. Può utilizzare AJAX per verificare l'idoneità dell'ordine o mostrare/nascondere dinamicamente il pulsante.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `rbpro/lib/searchTool/views/css/autocomplete.css`

    -   **Ambito:** Back-office.
    -   **Dettagli:** Stili per i menu a discesa di autocompletamento e i campi di input di ricerca utilizzati nel pannello di amministrazione.
-   `rbpro/views/css/admin-config.css`

    -   **Ambito:** Back-office (pagina di configurazione del modulo).
    -   **Dettagli:** Stili per il modulo di configurazione principale del modulo, inclusi schede, campi di input e layout generale.
-   `rbpro/views/css/admin-dashboard.css`

    -   **Ambito:** Back-office (potenzialmente per una dashboard del modulo o una vista statistiche).
    -   **Dettagli:** Stili per eventuali elementi personalizzati della dashboard o visualizzazioni statistiche all'interno dell'interfaccia di amministrazione del modulo.
-   `rbpro/views/css/admin-order-state-picker.css`

    -   **Ambito:** Back-office.
    -   **Dettagli:** Stili specifici per gli elementi di selezione dello stato dell'ordine migliorati nell'amministrazione.
-   `rbpro/views/css/admin-searchtool.css`

    -   **Ambito:** Back-office.
    -   **Dettagli:** Stili generali per gli strumenti di ricerca e i componenti di filtro all'interno dell'interfaccia di amministrazione.
-   `rbpro/views/css/admin-withdrawal-view.css`

    -   **Ambito:** Back-office (vista dettagliata di `AdminRbpWithdrawalController`).
    -   **Dettagli:** Stili per la vista dettagliata di una singola richiesta di recesso, incluse sezioni per le informazioni del cliente, i prodotti, la cronologia e le note.
-   `rbpro/views/css/front-classic.css`

    -   **Ambito:** Front-office (per la compatibilità con il tema Classic).
    -   **Dettagli:** Regolazioni di stile specifiche per il modulo di recesso e i pulsanti per integrarsi perfettamente con il tema Classic di PrestaShop.
-   `rbpro/views/css/front-hummingbird.css`

    -   **Ambito:** Front-office (per la compatibilità con il tema Hummingbird).
    -   **Dettagli:** Regolazioni di stile specifiche per il modulo di recesso e i pulsanti per integrarsi perfettamente con il tema Hummingbird di PrestaShop.
-   `rbpro/views/css/front.css`

    -   **Ambito:** Front-office (stile generale).
    -   **Dettagli:** CSS principale per il modulo di recesso front-office, i pulsanti e le pagine di stato, fornendo uno stile di base che può essere sovrascritto da fogli di stile specifici del tema.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

Questi template vengono renderizzati quando il modulo è agganciato a specifici punti di visualizzazione.

-   `rbpro/views/templates/hook/account-link-classic.tpl`

    -   **Hook:** `displayCustomerAccount` (o simile)
    -   **Output:** Un link nella sezione "Il mio account" del cliente per il tema Classic, che porta al modulo di recesso o alla pagina di tracciamento.
-   `rbpro/views/templates/hook/account-link-hummingbird.tpl`

    -   **Hook:** `displayCustomerAccount` (o simile)
    -   **Output:** Un link nella sezione "Il mio account" del cliente per il tema Hummingbird.
-   `rbpro/views/templates/hook/button-classic.tpl`

    -   **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (o simile)
    -   **Output:** Il pulsante principale "Reso" o "Recesso", stilizzato per il tema Classic.
-   `rbpro/views/templates/hook/button-hummingbird.tpl`

    -   **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (o simile)
    -   **Output:** Il pulsante principale "Reso" o "Recesso", stilizzato per il tema Hummingbird.
-   `rbpro/views/templates/hook/button.tpl`

    -   **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (o simile)
    -   **Output:** Un pulsante generico "Reso" o "Recesso", utilizzato come fallback o base per i pulsanti specifici del tema.
-   `rbpro/views/templates/hook/order-detail-classic.tpl`

    -   **Hook:** `displayOrderDetail` (o simile)
    -   **Output:** Un'opzione o un pulsante nella pagina dei dettagli dell'ordine individuale del cliente per il tema Classic, che consente loro di avviare un reso per quell'ordine specifico.
-   `rbpro/views/templates/hook/order-detail-hummingbird.tpl`

    -   **Hook:** `displayOrderDetail` (o simile)
    -   **Output:** Un'opzione o un pulsante nella pagina dei dettagli dell'ordine individuale del cliente per il tema Hummingbird.
-   `rbpro/views/templates/hook/order-detail.tpl`

    -   **Hook:** `displayOrderDetail` (o simile)
    -   **Output:** Un'opzione o un pulsante generico nella pagina dei dettagli dell'ordine individuale del cliente.
-   `rbpro/views/templates/hook/order-withdrawal-notice.tpl`

    -   **Hook:** `displayAdminOrder` (o simile)
    -   **Output:** Un avviso o un riepilogo delle richieste di recesso relative a un ordine specifico, visualizzato all'interno della vista dell'ordine di amministrazione di PrestaShop.

#### Template Admin (`views/templates/admin/`)

Questi template sono utilizzati per l'interfaccia di back-office del modulo.

-   `rbpro/lib/searchTool/views/scripts.tpl`

    -   **Output:** Inclusione di JavaScript e CSS per la libreria dello strumento di ricerca, tipicamente inclusa nei moduli di amministrazione che utilizzano l'autocompletamento.
-   `rbpro/views/templates/admin/configure.tpl`

    -   **Output:** Il modulo di configurazione principale per il modulo, renderizzato da `getContent()` in `index.php`. Contiene tutte le impostazioni descritte nella sezione 4.1.
-   `rbpro/views/templates/admin/dashboard.tpl`

    -   **Output:** Una dashboard o una vista riassuntiva per il modulo, che potenzialmente mostra statistiche o richieste di recesso recenti.
-   `rbpro/views/templates/admin/order-state-picker.tpl`

    -   **Output:** Un template personalizzato per la selezione degli stati dell'ordine, utilizzato nella configurazione del modulo o nella vista di recesso dell'amministrazione.
-   `rbpro/views/templates/admin/order-withdrawal-notice.tpl`

    -   **Output:** Un piccolo widget o avviso visualizzato all'interno della pagina dei dettagli dell'ordine di PrestaShop nel back office, che indica se esiste una richiesta di recesso attiva per quell'ordine.
-   `rbpro/views/templates/admin/updates.tpl`

    -   **Output:** Un template per la visualizzazione di notifiche di aggiornamento del modulo o changelog all'interno dell'interfaccia di amministrazione.
-   `rbpro/views/templates/admin/view.tpl`

    -   **Output:** Il template di vista dettagliata per una singola richiesta di recesso, renderizzato da `AdminRbpWithdrawalController::renderForm()`. Mostra tutti i dettagli della richiesta, i prodotti, la cronologia, le note e le opzioni di cambio stato.

#### Template Front-Office (`views/templates/front/`)

Questi sono template di pagina standalone per il processo di recesso lato cliente.

-   `rbpro/views/templates/front/confirm_step.tpl`

    -   **Output:** Il passaggio di conferma del modulo di recesso, che riassume le selezioni del cliente prima dell'invio finale.
-   `rbpro/views/templates/front/error.tpl`

    -   **Output:** Una pagina di errore generica visualizzata se qualcosa va storto durante il processo di recesso (ad esempio, ordine non valido, problema tecnico).
-   `rbpro/views/templates/front/form.tpl`

    -   **Output:** Il modulo principale di richiesta di recesso online, che consente ai clienti di selezionare ordini, prodotti e fornire dettagli.
-   `rbpro/views/templates/front/print.tpl`

    -   **Output:** Una versione stampabile della richiesta di recesso, tipicamente un layout semplificato senza navigazione.
-   `rbpro/views/templates/front/status.tpl`

    -   **Output:** La pagina che visualizza lo stato attuale e la cronologia di una specifica richiesta di recesso.
-   `rbpro/views/templates/front/success.tpl`

    -   **Output:** Una pagina di messaggio di successo visualizzata dopo che una richiesta di recesso è stata inviata con successo.
-   `rbpro/views/templates/front/track.tpl`

    -   **Output:** Il modulo in cui i clienti possono inserire il loro riferimento d'ordine e l'email per tracciare una richiesta di recesso.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Il modulo crea e gestisce diverse tabelle personalizzate:

-   `ps_rbp_withdrawal`: Memorizza i dettagli principali della richiesta di recesso (cliente, ordine, stato, motivo, ecc.).
-   `ps_rbp_withdrawal_attachment`: Memorizza i dettagli sui file caricati dai clienti per una richiesta di recesso.
-   `ps_rbp_withdrawal_history`: Registra tutte le modifiche di stato e i messaggi associati per ogni richiesta di recesso.
-   `ps_rbp_withdrawal_note`: Memorizza le note interne aggiunte dai dipendenti a una richiesta di recesso.
-   `ps_rbp_withdrawal_product`: Collega prodotti specifici da un ordine a una richiesta di recesso, inclusi quantità e motivo.

I record di configurazione sono memorizzati in `ps_configuration` con chiavi tipicamente prefissate con `RBP_` (ad esempio, `RBP_ALLOW_GUEST_WITHDRAWAL`, `RBP_MIN_ORDER_STATUS`).

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta CSS/JS, visualizza il pulsante di reso (se configurato). |
| `displayFooter` | Nel footer di ogni pagina. | Visualizza il pulsante di reso (se configurato). |
| `displayLeftColumn` | Nella colonna sinistra delle pagine. | Visualizza il pulsante di reso (se configurato). |
| `displayRightColumn` | Nella colonna destra delle pagine. | Visualizza il pulsante di reso (se configurato). |
| `displayProductButtons` | Sulla pagina del prodotto, vicino al pulsante "aggiungi al carrello". | Visualizza il pulsante di reso (se configurato). |
| `displayCustomerAccount` | Sulla pagina "Il mio account" del cliente. | Aggiunge un link al modulo di recesso/tracciamento. |
| `displayOrderDetail` | Sulla pagina dei dettagli dell'ordine individuale del cliente. | Aggiunge un'opzione per richiedere un reso per quell'ordine. |
| `displayAdminOrder` | Nel back office di PrestaShop, sulla pagina dei dettagli dell'ordine. | Visualizza un avviso o un riepilogo delle richieste di recesso correlate. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Potenziale registrazione dei dettagli dell'ordine per futuri controlli di idoneità al recesso. |
| `actionOrderStatusUpdate` | Dopo che lo stato di un ordine è stato modificato. | Controlla se lo stato dell'ordine influisce sull'idoneità al recesso o attiva notifiche. |
| `actionFrontControllerSetMedia` | Prima che un controller front-office renderizzi il suo contenuto. | Carica risorse CSS e JavaScript specifiche del front-office. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renderizzi il suo contenuto. | Carica risorse CSS e JavaScript specifiche del back-office. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Crea tabelle del database, imposta i valori di configurazione predefiniti. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Rimuove tabelle del database, pulisce i valori di configurazione. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi domanda relativa al modulo "Pulsante Reso UE – Modulo di Recesso Online", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto e gli sviluppatori sono disponibili per assistervi con qualsiasi problema o richiesta.
"""
