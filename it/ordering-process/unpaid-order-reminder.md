---
title: "Promemoria ordini non pagati - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Promemoria ordini non pagati di MyPresta.eu."
sidebar:
  label: "Promemoria ordini non pagati - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Unpaid order reminder su MyPresta.eu](https://mypresta.eu/modules/ordering-process/unpaid-order-reminder.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/unpaid-order-reminder/)
>
> ---


# Promemoria ordini non pagati

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Assicurati che la funzionalità cron job del tuo server sia abilitata e configurata correttamente affinché i promemoria automatici del modulo funzionino.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Promemoria ordini non pagati" offre diverse schermate di configurazione per gestire le impostazioni dei promemoria, visualizzare la cronologia e gestire i clienti disiscritti.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Promemoria ordini non pagati)

Questa è la schermata di configurazione principale dove imposti il comportamento fondamentale del modulo.

-   **Cosa fa questa impostazione:** Questa sezione ti consente di abilitare o disabilitare il modulo, configurare il cron job e gestire le impostazioni generali per le tue email di promemoria.
-   **Effetto della modifica di questa impostazione:** Controlla la funzionalità complessiva e l'automazione del sistema di promemoria.

#### Impostazioni generali

-   **Abilita modulo:**

    -   **Cosa fa questa impostazione:** Attiva o disattiva l'intero modulo "Promemoria ordini non pagati".
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo inizierà a inviare promemoria secondo le regole definite e il cron job.
        -   *Quando disabilitato:* Nessun promemoria verrà inviato e il modulo sarà inattivo.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Abilita questo dopo aver impostato le tue regole di promemoria per iniziare a recuperare gli ordini non pagati. Disabilitalo se hai bisogno di interrompere temporaneamente tutti i promemoria per manutenzione o una campagna specifica.
-   **URL Cron Job:**

    -   **Cosa fa questa impostazione:** Visualizza l'URL unico che il cron job del tuo server deve eseguire periodicamente. Questo URL attiva il modulo per controllare gli ordini non pagati e inviare promemoria.
    -   **Effetto della modifica di questa impostazione:** Questo URL è cruciale per l'automazione del modulo. Senza che venga chiamato da un cron job, nessun promemoria verrà inviato automaticamente.
    -   **Valore consigliato:** Copia questo URL e impostalo nel gestore cron job del pannello di controllo del tuo hosting.
    -   **Scenario / esempio del commerciante:** Tipicamente lo imposterai una volta durante la configurazione iniziale. Ad esempio, potresti configurare il tuo server per chiamare questo URL ogni ora per garantire promemoria tempestivi.
-   **Link di disiscrizione nell'email:**

    -   **Cosa fa questa impostazione:** Determina se un link di disiscrizione è incluso nelle email di promemoria.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono cliccare su un link nell'email per annullare l'iscrizione a futuri promemoria di ordini non pagati.
        -   *Quando disabilitato:* I clienti non possono facilmente annullare l'iscrizione, il che potrebbe portare a frustrazione o a contrassegnare le tue email come spam.
    -   **Valore consigliato:** SÌ (Altamente consigliato per conformità e soddisfazione del cliente).
    -   **Scenario / esempio del commerciante:** Includi sempre questo per dare ai clienti il controllo e mantenere una buona reputazione del mittente.
-   **Stati ordine da ricordare:**

    -   **Cosa fa questa impostazione:** Ti consente di selezionare quali specifici stati dell'ordine dovrebbero attivare un promemoria. Tipicamente, questi sono stati che indicano che un ordine è in attesa di pagamento (ad esempio, "In attesa di bonifico bancario", "In attesa di pagamento con assegno").
    -   **Effetto della modifica di questa impostazione:** Solo gli ordini con gli stati selezionati verranno considerati per i promemoria.
    -   **Valore consigliato:** Seleziona tutti gli stati che rappresentano un ordine in attesa di pagamento.
    -   **Scenario / esempio del commerciante:** Se utilizzi "In attesa di bonifico bancario" e "In attesa di pagamento con assegno", seleziona entrambi. Se hai uno stato personalizzato come "Pagamento gateway in sospeso", includi anche quello.
-   **Stati ordine per interrompere i promemoria:**

    -   **Cosa fa questa impostazione:** Definisce quali stati dell'ordine, se raggiunti, dovrebbero interrompere ulteriori promemoria per quell'ordine specifico. Questo di solito include stati come "Pagamento accettato", "Spedito" o "Annullato".
    -   **Effetto della modifica di questa impostazione:** Una volta che un ordine raggiunge uno di questi stati, il modulo non invierà più promemoria per esso, prevenendo email inutili o confuse.
    -   **Valore consigliato:** Seleziona tutti gli stati che indicano che il pagamento è stato ricevuto, l'ordine è stato elaborato o l'ordine non è più valido (ad esempio, "Pagamento accettato", "Annullato", "Rimborsato").
    -   **Scenario / esempio del commerciante:** Se un cliente paga un ordine, non vuoi che riceva un altro promemoria. Selezionando "Pagamento accettato" qui si garantisce questo.

#### Regole di promemoria

Questa sezione è dove definisci le effettive email di promemoria. Puoi creare più regole, ognuna con tempi e contenuti email diversi.

-   **Aggiungi nuova regola di promemoria:**
    -   **Cosa fa questa impostazione:** Ti consente di creare un nuovo set di parametri di promemoria.
    -   **Effetto della modifica di questa impostazione:** Apre un modulo per definire una nuova email di promemoria.
    -   **Valore consigliato:** Crea almeno una regola.
    -   **Scenario / esempio del commerciante:** Potresti voler inviare un primo promemoria dopo 24 ore e un secondo, più urgente, dopo 72 ore.

Quando aggiungi/modifica una regola, configurerai:

-   **Giorni dopo la creazione dell'ordine:**

    -   **Cosa fa questa impostazione:** Specifica quanti giorni dopo l'ordine è stato effettuato questa particolare email di promemoria dovrebbe essere inviata.
    -   **Effetto della modifica di questa impostazione:** Controlla la tempistica del promemoria.
    -   **Valore consigliato:** Inizia con 1 o 2 giorni per il primo promemoria.
    -   **Scenario / esempio del commerciante:** Imposta su "1" per un primo promemoria 24 ore dopo l'ordine. Imposta su "3" per un secondo promemoria 3 giorni dopo l'ordine.
-   **Oggetto email:**

    -   **Cosa fa questa impostazione:** La riga dell'oggetto dell'email di promemoria.
    -   **Effetto della modifica di questa impostazione:** Questo è ciò che i clienti vedono nella loro posta in arrivo. Un oggetto chiaro e conciso aumenta i tassi di apertura.
    -   **Valore consigliato:** Qualcosa come "Promemoria: Il tuo ordine non pagato su [Nome negozio]" o "Azione richiesta: Completa il tuo ordine #[ID ordine]".
    -   **Scenario / esempio del commerciante:** "Non dimenticare il tuo ordine da MyPresta.eu!"
-   **Contenuto email:**

    -   **Cosa fa questa impostazione:** Il corpo principale dell'email di promemoria. Puoi usare variabili (come `{customer_name}`, `{order_id}`, `{shop_name}`) per personalizzare il messaggio.
    -   **Effetto della modifica di questa impostazione:** Questo è il messaggio principale per il tuo cliente. Un tono amichevole e disponibile è il migliore.
    -   **Valore consigliato:** Includi un saluto, menziona l'ordine non pagato, fornisci istruzioni su come pagare o dove trovare i dettagli di pagamento e offri aiuto.
    -   **Scenario / esempio del commerciante:** "Gentile {customer\_name}, Questo è un promemoria amichevole riguardo al tuo recente ordine #{order\_id} su {shop\_name}. Sembra che il pagamento per questo ordine sia ancora in sospeso. Ti preghiamo di completare il pagamento il prima possibile per garantire che il tuo ordine venga elaborato. Puoi visualizzare i dettagli del tuo ordine qui: [Link alla cronologia ordini]. Se hai domande, non esitare a contattarci."
-   **Attivo:**

    -   **Cosa fa questa impostazione:** Abilita o disabilita questa specifica regola di promemoria.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Questo promemoria verrà inviato secondo la sua tempistica.
        -   *Quando disabilitato:* Questo promemoria non verrà inviato, anche se il modulo è attivo.
    -   **Valore consigliato:** SÌ per le regole attive.
    -   **Scenario / esempio del commerciante:** Potresti disabilitare una regola se stai testando nuovi contenuti o vuoi mettere in pausa temporaneamente un promemoria specifico.

### 2.2 Gestione promemoria ordini (Back Office > Moduli > Promemoria ordini non pagati > Promemoria ordini)

Questa schermata dedicata, accessibile tramite il menu del modulo nel Back Office, ti consente di visualizzare e gestire gli ordini attualmente idonei per i promemoria.

-   **Nome schermata e posizione nel menu:** **Promemoria ordini** (sotto la voce di menu "Promemoria ordini non pagati").
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza un elenco di ordini che attualmente corrispondono ai tuoi criteri "Stati ordine da ricordare".
    -   **Vista griglia / Gestione:** Vedrai una tabella con colonne come ID ordine, Nome cliente, Data ordine, Stato attuale e potenzialmente la data del prossimo promemoria.
    -   **Azioni:** Potresti avere azioni per inviare manualmente un promemoria per un ordine specifico o per escludere un ordine da futuri promemoria.
-   **Effetto delle modifiche:**
    -   **Invio manuale di un promemoria:** Invia immediatamente l'email di promemoria successiva programmata per quell'ordine.
    -   **Esclusione di un ordine:** Impedisce al modulo di inviare ulteriori promemoria per quell'ordine specifico, anche se il suo stato corrisponde ancora ai criteri di promemoria.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla periodicamente questo elenco per avere una panoramica degli ordini non pagati in sospeso. Utilizza l'opzione di invio manuale se un cliente chiama e desideri inviargli immediatamente di nuovo i dettagli di pagamento. Escludi gli ordini se hai preso un accordo speciale con un cliente o se un ordine è problematico.

### 2.3 Cronologia promemoria ordini (Back Office > Moduli > Promemoria ordini non pagati > Cronologia)

Questa schermata fornisce un registro di tutte le email di promemoria che sono state inviate dal modulo.

-   **Nome schermata e posizione nel menu:** **Cronologia** (sotto la voce di menu "Promemoria ordini non pagati").
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza una tabella con i dettagli di ogni promemoria inviato:
    -   Le colonne tipicamente includono: ID ordine, Nome cliente, Indirizzo email, Regola di promemoria (quale regola l'ha attivato), Data di invio e potenzialmente l'oggetto dell'email.
-   **Effetto delle modifiche:** Questo è un registro di sola lettura. Non vengono apportate modifiche dirette qui, ma fornisce informazioni preziose.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa schermata per verificare che i promemoria vengano inviati correttamente. Se un cliente afferma di non aver ricevuto un promemoria, puoi controllare questa cronologia per confermare se è stato spedito.

### 2.4 Clienti disiscritti (Back Office > Moduli > Promemoria ordini non pagati > Clienti disiscritti)

Questa schermata elenca i clienti che hanno annullato l'iscrizione alla ricezione dei promemoria degli ordini non pagati.

-   **Nome schermata e posizione nel menu:** **Clienti disiscritti** (sotto la voce di menu "Promemoria ordini non pagati").
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza una tabella con:
    -   Le colonne tipicamente includono: ID cliente, Nome cliente, Indirizzo email e Data di disiscrizione.
    -   **Azioni:** Potresti avere un'opzione per rimuovere manualmente un cliente da questo elenco, ri-iscrivendolo di fatto ai promemoria (usa con cautela e solo se richiesto dal cliente).
-   **Effetto delle modifiche:**
    -   **Rimozione dall'elenco:** Il cliente sarà nuovamente idoneo a ricevere promemoria se lo stato del suo ordine corrisponde.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Monitora questo elenco per comprendere le preferenze dei clienti. Ri-iscrivi un cliente solo se lo richiede esplicitamente.

### 2.5 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita modulo | SÌ | Attiva/disattiva la funzionalità del modulo. |
| | URL Cron Job | Copia e configura | Essenziale per l'invio automatico dei promemoria. |
| | Link di disiscrizione nell'email | SÌ | Consente ai clienti di annullare l'iscrizione, migliora la reputazione del mittente. |
| | Stati ordine da ricordare | In attesa di bonifico, In attesa di assegno, ecc. | Definisce quali stati dell'ordine attivano i promemoria. |
| | Stati ordine per interrompere i promemoria | Pagamento accettato, Annullato, ecc. | Impedisce i promemoria per ordini pagati o non validi. |
| | **Regole di promemoria** | | |
| | Giorni dopo la creazione dell'ordine | 1, 3, 7 (esempio) | Imposta la tempistica per ogni email di promemoria. |
| | Oggetto email | "Promemoria: Il tuo ordine non pagato..." | Riga dell'oggetto dell'email di promemoria. |
| | Contenuto email | Messaggio personalizzato con variabili | Corpo dell'email di promemoria. |
| | Attivo (per ogni regola) | SÌ | Abilita/disabilita le singole regole di promemoria. |
| **Promemoria ordini** | (Elenco di ordini idonei) | N/A | Panoramica degli ordini in attesa di pagamento. |
| | Invia promemoria manuale | N/A | Invia immediatamente il prossimo promemoria per l'ordine selezionato. |
| | Escludi ordine | N/A | Impedisce futuri promemoria per l'ordine selezionato. |
| **Cronologia** | (Registro dei promemoria inviati) | N/A | Traccia di controllo di tutte le email di promemoria spedite. |
| **Clienti disiscritti** | (Elenco di clienti disiscritti) | N/A | Mostra i clienti che hanno annullato l'iscrizione ai promemoria. |
| | Rimuovi dall'elenco di disiscrizione | N/A | Ri-iscrive il cliente ai promemoria (usa con cautela). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei promemoria non vengono inviati. Cosa dovrei controllare per primo?**
**R1:**

-   **Modulo abilitato:** Vai su **Moduli > Gestione moduli > Promemoria ordini non pagati** e assicurati che l'impostazione "Abilita modulo" sia impostata su SÌ.
-   **Cron Job:** Il problema più comune. Devi *assolutamente* configurare il cron job sul tuo server di hosting. Copia l'"URL Cron Job" dalla pagina di configurazione del modulo e aggiungilo al gestore cron job del pannello di controllo del tuo hosting. Assicurati che sia impostato per essere eseguito frequentemente (ad esempio, ogni ora). Se non sei sicuro di come fare, contatta il tuo provider di hosting.
-   **Stati ordine:** Ricontrolla "Stati ordine da ricordare" e "Stati ordine per interrompere i promemoria" nella configurazione del modulo. Assicurati che gli ordini per cui ti aspetti promemoria abbiano uno stato selezionato nell'elenco "da ricordare" e non abbiano raggiunto uno stato nell'elenco "da interrompere".
-   **Regole di promemoria attive:** Assicurati che le singole regole di promemoria che hai creato siano contrassegnate come "Attive".

**D2: I clienti ricevono troppi promemoria, o promemoria dopo aver pagato. Come posso risolvere questo problema?**
**R2:**

-   **"Stati ordine per interrompere i promemoria":** Questo è cruciale. Assicurati che tutti gli stati che indicano un ordine pagato o completato (ad esempio, "Pagamento accettato", "Spedito", "Annullato", "Rimborsato") siano selezionati in questa impostazione. Questo indica al modulo di interrompere l'invio di promemoria una volta che l'ordine raggiunge uno di questi stati.
-   **Tempistica delle regole di promemoria:** Rivedi i "Giorni dopo la creazione dell'ordine" per ogni regola di promemoria. Assicurati che siano distanziati in modo appropriato e non si sovrappongano in modo da inviare troppe email troppo rapidamente.

**D3: Posso personalizzare i modelli di email?**
**R3:** Sì, il modulo ti consente di personalizzare l'oggetto e il contenuto dell'email direttamente nelle impostazioni delle regole di promemoria. Puoi utilizzare variabili specifiche (come `{customer_name}`, `{order_id}`, `{shop_name}`) per personalizzare il messaggio. Per una personalizzazione visiva più avanzata, uno sviluppatore dovrebbe modificare i file del modello di email sottostanti (situati in `mails/` all'interno della tua installazione PrestaShop, utilizzando la struttura del modello del modulo come guida).

**D4: Il link di disiscrizione non funziona, o i clienti continuano a ricevere email dopo essersi disiscritti.**
**R4:**

-   **Link di disiscrizione abilitato:** Assicurati che "Link di disiscrizione nell'email" sia impostato su SÌ nella configurazione principale del modulo.
-   **Controlla l'elenco "Clienti disiscritti":** Vai su **Moduli > Promemoria ordini non pagati > Clienti disiscritti**. Verifica che l'indirizzo email del cliente appaia in questo elenco. Se non appare, potrebbero non essersi disiscritti correttamente.
-   **Cache:** Cancella la cache di PrestaShop (**Parametri avanzati > Prestazioni > Cancella cache**) dopo aver apportato modifiche alla configurazione.

**D5: Cosa succede se un cliente ha più ordini non pagati?**
**R5:** Il modulo tratterà ogni ordine non pagato individualmente. Se un cliente ha due ordini non pagati separati, riceverà promemoria per ogni ordine secondo le tue regole definite, purché tali ordini soddisfino i criteri.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Promemoria ordini non pagati", destinata a sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Promemoria ordini non pagati" (`oreminders`) segue un'architettura standard dei moduli PrestaShop, sfruttando i principi MVC. Si concentra principalmente sull'amministrazione del back-office per la configurazione e su un cron job del front-office per l'elaborazione automatizzata. Estende `Module` per la sua funzionalità principale e utilizza classi `AdminController` personalizzate per la gestione dei promemoria, della cronologia e dei clienti disiscritti. La gestione dei modelli di email è affidata a un gestore personalizzato e la configurazione è memorizzata in `ps_configuration`.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/CronJob.php`
    -   **Nome classe e classe padre:** `OremindersCronJobModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller è progettato per essere chiamato da un cron job lato server. È il punto di ingresso per la logica automatizzata del modulo. Quando eseguito, itera attraverso gli ordini non pagati, verifica le regole di promemoria definite e invia le email di promemoria. Tipicamente restituisce un semplice messaggio di successo/fallimento o un output di log.
-   `controllers/front/index.php`
    -   **Nome classe e classe padre:** `OremindersIndexModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo è probabilmente un segnaposto o un controller di fallback. In molti moduli, `index.php` in `controllers/front` serve come punto di ingresso predefinito o semplice se non viene richiesta alcuna azione specifica. Potrebbe gestire la visualizzazione di base del modulo o la reindirizzamento se il modulo avesse una presenza nel front-office. Data la natura del modulo, la sua interazione principale nel front-office avviene tramite `CronJob.php`.

#### Controller Admin Back-Office

-   `controllers/admin/AdminOrderReminders.php`
    -   **Nome scheda ed entità gestita:** Gestisce l'elenco "Promemoria ordini". Questo controller è responsabile della visualizzazione di un elenco di ordini attualmente idonei per i promemoria in base alla configurazione del modulo. Fornisce azioni per inviare manualmente promemoria o escludere ordini specifici.
-   `controllers/admin/AdminOrderRemindersHistory.php`
    -   **Nome scheda ed entità gestita:** Gestisce il registro "Cronologia". Questo controller visualizza un elenco di sola lettura di tutte le email di promemoria che sono state inviate con successo dal modulo, inclusi dettagli come l'ID dell'ordine, il cliente e la data di invio.
-   `controllers/admin/AdminOrderRemindersUnsub.php`
    -   **Nome scheda ed entità gestita:** Gestisce l'elenco "Clienti disiscritti". Questo controller visualizza i clienti che hanno annullato l'iscrizione alla ricezione dei promemoria e consente la loro ri-iscrizione (se necessario).
-   `controllers/admin/index.php`
    -   **Nome classe e classe padre:** `AdminOremindersIndexController` estende `ModuleAdminController`.
    -   **Nome scheda ed entità gestita:** Simile a `index.php` del front-office, questo potrebbe servire come controller amministrativo predefinito o di fallback. Potrebbe potenzialmente gestire la configurazione principale del modulo se `getContent()` nel file principale del modulo reindirizza ad esso, o se viene utilizzato per un'azione amministrativa specifica e semplice.

### 4.3 Classi e modelli principali (`classes/`)

L'inventario fornito non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo potrebbe utilizzare `ObjectModel` direttamente all'interno del suo file principale del modulo o dei controller amministrativi, oppure sta gestendo i dati tramite query dirette al database o estendendo i modelli principali esistenti di PrestaShop (ad esempio, `Order`, `Customer`).

Se i dati personalizzati vengono memorizzati, è probabile che siano gestiti tramite `ps_configuration` per le impostazioni e potenzialmente tabelle di database personalizzate create durante l'installazione (anche se non sono stati elencati file SQL, quindi la creazione della tabella sarebbe in linea in `install()`).

### 4.4 Risorse JavaScript (`views/js/`)

-   `oreminders/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    -   **Ambito:** Back-office.
    -   **Dettagli:** Questo script probabilmente fornisce funzionalità dinamiche per l'interfaccia di gestione dei modelli di email all'interno della configurazione del modulo. Ciò potrebbe includere:
        -   Aggiunta/rimozione dinamica di regole di promemoria.
        -   Gestione delle richieste AJAX per il salvataggio/caricamento dei modelli di email.
        -   Implementazione di un editor di testo ricco (ad esempio, integrazione TinyMCE) per il contenuto dell'email.
        -   Gestione dell'inserimento di variabili nei modelli di email.
        -   Validazione lato client per i campi del modulo relativi alle regole delle email.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `oreminders/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    -   **Ambito:** Stile del modulo di amministrazione del back-office.
    -   **Dettagli:** Questo foglio di stile fornisce uno stile specifico per l'interfaccia del gestore di modelli di email nella configurazione del Back Office del modulo. Definirebbe gli stili per:
        -   Layout dei moduli delle regole di promemoria.
        -   Stile dei campi di input, pulsanti e aree di testo all'interno dell'editor di modelli.
        -   Garantire un aspetto e una sensazione coerenti con il tema del Back Office di PrestaShop.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Cerca classi specifiche con prefisso `oreminders-` o `email-templates-manager-` all'interno dei modelli di amministrazione del modulo per identificare gli elementi personalizzabili.

### 4.6 Struttura del modello Smarty (`views/templates/`)

#### Modelli di hook (`views/templates/hook/`)

-   `oreminders/views/templates/hook/form.tpl`
    -   **Hook:** Potenzialmente `displayAdminModuleConfigure` o simile, se utilizzato per un piccolo modulo in un contesto di hook. Più probabilmente, è un modello di modulo generico utilizzato internamente.
    -   **Output:** Renderizza una struttura di modulo generica.
-   `oreminders/views/templates/hook/header.tpl`
    -   **Hook:** `displayHeader` (Front-office).
    -   **Output:** Utilizzato per includere file CSS o JavaScript necessari nella sezione `<head>` del front-office, se il modulo avesse componenti front-end (ad esempio, per la pagina di disiscrizione).
-   `oreminders/views/templates/hook/identity.tpl`
    -   **Hook:** Non chiaro dal nome, ma `displayCustomerAccount` o simile per la visualizzazione di informazioni specifiche del cliente, o forse correlato al processo di disiscrizione.
    -   **Output:** Potrebbe renderizzare un messaggio o un modulo relativo all'identità o alle preferenze del cliente.

#### Modelli di amministrazione (`views/templates/admin/`)

-   `oreminders/lib/emailTemplatesManager/views/buttonManager.tpl`
    -   **Contesto:** Utilizzato all'interno del gestore di modelli di email.
    -   **Output:** Renderizza i pulsanti per la gestione dei modelli di email (ad esempio, "Aggiungi nuova regola", "Salva", "Elimina").
-   `oreminders/lib/emailTemplatesManager/views/createTemplateForm.tpl`
    -   **Contesto:** Utilizzato all'interno del gestore di modelli di email.
    -   **Output:** Renderizza il modulo per la creazione di un nuovo modello/regola di email di promemoria.
-   `oreminders/lib/emailTemplatesManager/views/editTemplateForm.tpl`
    -   **Contesto:** Utilizzato all'interno del gestore di modelli di email.
    -   **Output:** Renderizza il modulo per la modifica di un modello/regola di email di promemoria esistente.
-   `oreminders/lib/emailTemplatesManager/views/mainForm.tpl`
    -   **Contesto:** Utilizzato all'interno del gestore di modelli di email.
    -   **Output:** Il modello wrapper principale per l'interfaccia di gestione dei modelli di email, probabilmente combinando `buttonManager`, `createTemplateForm` e `editTemplateForm`.
-   `oreminders/lib/emailTemplatesManager/views/selectInput.tpl`
    -   **Contesto:** Utilizzato all'interno del gestore di modelli di email.
    -   **Output:** Un modello riutilizzabile per il rendering di un input a discesa `<select>`, probabilmente per la scelta degli stati dell'ordine o di altre opzioni.
-   `oreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    -   **Contesto:** Utilizzato da `AdminOrderRemindersController` per le sue viste di modulo (ad esempio, se c'è un modulo di aggiunta/modifica per una voce di promemoria ordine, anche se è principalmente un controller di elenco).
    -   **Output:** Renderizza un modulo di amministrazione PrestaShop standard.
-   `oreminders/views/templates/admin/order_reminders/helpers/list/list_action_email.tpl`
    -   **Contesto:** Utilizzato da `AdminOrderRemindersController` nella sua vista elenco.
    -   **Output:** Renderizza un pulsante o un link di azione specifico all'interno dell'elenco dei promemoria ordine, probabilmente per "Invia email" o "Visualizza email".
-   `oreminders/views/templates/admin/script.tpl`
    -   **Contesto:** Back Office di amministrazione.
    -   **Output:** Probabilmente include codice JavaScript inline o variabili di configurazione necessarie all'interfaccia del Back Office, possibilmente per chiamate AJAX o elementi UI dinamici.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

La descrizione del modulo e l'inventario dei file non elencano esplicitamente i file SQL per la creazione di tabelle personalizzate. Tuttavia, in base ai controller di amministrazione, il modulo probabilmente interagisce con i seguenti (tabelle personalizzate o `ps_configuration` per le impostazioni):

-   `ps_configuration`: Memorizza tutte le impostazioni del modulo (ad esempio, `OREMINDERS_ENABLED`, `OREMINDERS_CRON_URL`, `OREMINDERS_UNSUB_LINK`, `OREMINDERS_STATUSES_REMIND`, `OREMINDERS_STATUSES_STOP` e dati serializzati per le singole regole di promemoria).
-   `ps_or` (o simile, gestito da `AdminOrderRemindersController`): Probabilmente una tabella personalizzata per memorizzare informazioni sugli ordini attualmente in fase di promemoria, o per contrassegnare gli ordini come esclusi.
-   `ps_or_history` (o simile, gestito da `AdminOrderRemindersHistoryController`): Una tabella personalizzata per registrare ogni email di promemoria inviata, inclusi `id_order`, `id_customer`, `email`, `id_reminder_rule`, `date_sent`.
-   `ps_or_ounsub` (o simile, gestito da `AdminOrderRemindersUnsubController`): Una tabella personalizzata per memorizzare gli ID cliente o gli indirizzi email di coloro che si sono disiscritti dai promemoria.

#### Tabella degli hook registrati

| Nome Hook | Ambito | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Nella sezione `<head>` di tutte le pagine del front-office. | Per includere CSS/JS specifici del modulo per i componenti del front-office (ad esempio, pagina di disiscrizione). |
| `displayAdminModuleConfigure` | Back-Office | Quando si visualizza la pagina di configurazione principale del modulo. | Per renderizzare il modulo di configurazione principale del modulo (metodo `getContent()`). |
| `actionValidateOrder` | Back-Office | Dopo che un ordine è stato convalidato con successo. | Potenzialmente utilizzato per inizializzare il tracciamento dei promemoria per i nuovi ordini, sebbene il cron job sia il trigger principale. |
| `actionOrderStatusUpdate` | Back-Office | Quando lo stato di un ordine viene modificato. | Per verificare se il nuovo stato di un ordine dovrebbe interrompere i promemoria (ad esempio, se diventa "Pagamento accettato"). |
| `actionCronJob` | Back-Office (tramite Front Controller) | Eseguito dal cron job del server. | L'hook principale che attiva la logica del modulo per trovare gli ordini non pagati e inviare promemoria. |
| (Hook impliciti per schede di amministrazione) | Back-Office | Quando si renderizza il menu del Back Office. | Per aggiungere le voci di menu personalizzate del modulo (Promemoria ordini, Cronologia, Clienti disiscritti). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Promemoria ordini non pagati", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
