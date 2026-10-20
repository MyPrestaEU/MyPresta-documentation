---
title: "Esporta Clienti con indirizzo - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Esporta Clienti con indirizzo di MyPresta.eu."
sidebar:
  label: "Esporta Clienti con indirizzo - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Export Customers with address su MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-customers-with-address.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/export-customers-with-address/)
>
> ---


# Esporta Clienti con indirizzo

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti per i moduli PrestaShop. Nessun requisito di hosting speciale oltre a un ambiente PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" sul modulo verrai indirizzato alla sua pagina di configurazione principale. Questa schermata gestisce principalmente le impostazioni interne del modulo relative agli aggiornamenti.

-   **Cosa fa questa impostazione:** Questa sezione gestisce tipicamente i controlli interni degli aggiornamenti del modulo e le informazioni sulla versione. Queste impostazioni sono solitamente per uso interno del modulo per assicurarti di utilizzare l'ultima versione e per fornire notifiche di aggiornamento.
-   **Effetto della modifica di questa impostazione:**
    -   *`mypresta_updates`*: Questo è probabilmente un flag interno per abilitare o disabilitare i controlli degli aggiornamenti da MyPresta.eu.
    -   *`update_`*: Questo potrebbe memorizzare l'ultima volta che è stato eseguito un controllo degli aggiornamenti.
    -   *`updatev_`*: Questo potrebbe memorizzare l'ultima versione disponibile rilevata.
-   **Valore consigliato:** È generalmente consigliato lasciare queste impostazioni ai loro valori predefiniti per assicurarti di ricevere importanti notifiche di aggiornamento.
-   **Scenario / esempio del commerciante:** Normalmente non interagisci direttamente con queste impostazioni. Funzionano in background per informarti se è disponibile una nuova versione del modulo, assicurandoti di avere accesso alle ultime funzionalità e correzioni di bug.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Esporta Clienti con indirizzo (Back Office > Parametri Avanzati > Esporta Clienti con indirizzo)

Questa è la schermata principale in cui eseguirai l'esportazione dei clienti. Puoi trovarla nel menu "Parametri Avanzati" del tuo back office PrestaShop.

-   **Nome schermata e posizione nel menu:** **Parametri Avanzati > Esporta Clienti con indirizzo**
-   **Azioni e impostazioni disponibili:**
    -   Quando navighi in questa schermata, vedrai un pulsante o un link per avviare il processo di esportazione. Il modulo prepara automaticamente un file CSV contenente tutti i dati dei clienti e i loro indirizzi associati.
    -   Il file esportato includerà le seguenti colonne, formattate per lo strumento di importazione di PrestaShop:
        -   **ID Cliente**: Identificatore univoco per il cliente.
        -   **Attivo (0/1)**: Se l'account cliente è attivo (1) o inattivo (0).
        -   **ID Titoli (Sig = 1, Sig.ra = 2, altro 0)**: L'ID corrispondente al titolo del cliente (es. Sig., Sig.ra).
        -   \*\*Email \*\*\*: L'indirizzo email del cliente (obbligatorio).
        -   \*\*Password \*\*\*: La password del cliente (obbligatoria, solitamente hashata).
        -   **Data di nascita (aaaa-mm-gg)**: La data di nascita del cliente.
        -   \*\*Cognome \*\*\*: Il cognome del cliente (obbligatorio).
        -   \*\*Nome \*\*\*: Il nome del cliente (obbligatorio).
        -   **Newsletter (0/1)**: Se il cliente è iscritto alla newsletter (1) o meno (0).
        -   **Opt-in (0/1)**: Se il cliente ha acconsentito alle offerte dei partner (1) o meno (0).
        -   **Data di registrazione**: La data in cui il cliente ha registrato il proprio account.
        -   **Gruppi (x,y,z…)**: Un elenco di ID separati da virgole dei gruppi di clienti a cui appartiene il cliente.
        -   **ID gruppo predefinito**: L'ID del gruppo predefinito del cliente.
        -   **ID / Nome del negozio**: L'ID o il nome del negozio a cui è associato il cliente (utile in ambienti multi-negozio).
        -   **ID Indirizzo**: Identificatore univoco per l'indirizzo del cliente.
        -   \*\*Alias \*\*\*: Un alias per l'indirizzo (es. "Il mio indirizzo di casa").
        -   \*\*Email cliente \*\*\*: L'email associata a questo indirizzo (dovrebbe corrispondere all'email del cliente).
        -   **Produttore**: (Se applicabile)
        -   **Fornitore**: (Se applicabile)
        -   **Azienda**: Il nome dell'azienda associato all'indirizzo.
        -   … e altri campi indirizzo standard come `Indirizzo1`, `Indirizzo2`, `CAP`, `Città`, `Paese`, `Telefono`, `Cellulare`, `Partita IVA`, ecc.
-   **Effetto delle modifiche:** Cliccando sul pulsante di esportazione verrà generato e scaricato un file CSV sul tuo computer. Questa azione non modifica alcun dato nel tuo negozio PrestaShop; si limita a estrarli.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Backup regolari:** Esporta periodicamente i dati dei tuoi clienti come backup, specialmente prima di importanti aggiornamenti o migrazioni del negozio.
    2.  **Generazione di liste di marketing:** Esporta i dati dei clienti per creare liste per campagne di email marketing, segmentando per gruppi o date di registrazione.
    3.  **Aggiornamenti CRM:** Se utilizzi un CRM esterno, esporta i dati per mantenerlo sincronizzato con la tua base clienti PrestaShop.

#### 2.2.2 AdminExportCustomersController (index.php)

Questo file probabilmente funge da punto di ingresso o da helper per `AdminExportCustomersController`, garantendo che l'interfaccia amministrativa del modulo funzioni correttamente all'interno del back office di PrestaShop. Non presenta una schermata configurabile separata, ma piuttosto facilita la visualizzazione e la funzionalità della schermata di esportazione principale.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | `mypresta_updates` | Abilitato | Flag interno per i controlli degli aggiornamenti di MyPresta.eu. Mantienilo abilitato per le notifiche. |
| Pagina di configurazione del modulo | `update_` | (Interno) | Memorizza l'ultima data e ora del controllo degli aggiornamenti. |
| Pagina di configurazione del modulo | `updatev_` | (Interno) | Memorizza l'ultima versione del modulo disponibile. |
| Parametri Avanzati > Esporta Clienti con indirizzo | Pulsante Esporta | N/A | Avvia il download di un file CSV contenente tutti i dati dei clienti e degli indirizzi. |
| Parametri Avanzati > Esporta Clienti con indirizzo | Colonne CSV esportate | N/A | Include ID Cliente, Attivo, ID Titoli, Email, Password, Data di nascita, Cognome, Nome, Newsletter, Opt-in, Data di registrazione, Gruppi, ID gruppo predefinito, ID/Nome negozio, ID Indirizzo, Alias, Email cliente, Azienda e tutti i campi indirizzo standard. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho cliccato sul pulsante di esportazione, ma non è successo nulla o il file è vuoto.**
**R1:**

-   **Controlla i blocchi pop-up del browser:** Il tuo browser potrebbe bloccare il download del file. Cerca una notifica o un'icona nella barra degli indirizzi del tuo browser e consenti i download dall'amministrazione di PrestaShop.
-   **Permessi del modulo:** Assicurati che il modulo abbia i permessi necessari del file system per creare e servire il file CSV. Sebbene raro, permessi errati possono impedire la generazione del file.
-   **Limiti di memoria del server:** Se hai un numero molto elevato di clienti, il processo di esportazione potrebbe raggiungere i limiti di memoria PHP sul tuo server. Controlla i log degli errori PHP del tuo server (spesso trovati in `var/logs` o nel pannello di controllo del tuo hosting) per errori relativi alla memoria. Potrebbe essere necessario aumentare temporaneamente `memory_limit` nel tuo file `php.ini`.
-   **Database clienti vuoto:** Ricontrolla che tu abbia effettivamente clienti registrati nel tuo negozio.

**D2: Il file CSV esportato sembra illeggibile o presenta caratteri strani.**
**R2:** Questo è spesso un problema di codifica.

-   **Apri con la codifica corretta:** Quando apri il file CSV in un programma di fogli di calcolo (come Excel), assicurati di selezionare **UTF-8** come origine o codifica del file. La maggior parte dei sistemi moderni utilizza UTF-8 e le esportazioni di PrestaShop sono tipicamente in questo formato.
-   **Controlla le impostazioni della lingua di PrestaShop:** Assicurati che la lingua predefinita e il set di caratteri del tuo negozio PrestaShop siano configurati correttamente in **Internazionale > Localizzazione**.

**D3: Posso scegliere quali campi esportare?**
**R3:** Questo modulo esporta un set predefinito di campi cliente e indirizzo compatibili con lo strumento di importazione nativo di PrestaShop. Non offre opzioni per selezionare o deselezionare singoli campi. Se hai bisogno di un'esportazione altamente personalizzata, potresti aver bisogno di un modulo di esportazione più avanzato o di uno sviluppo personalizzato.

**D4: L'esportazione dei clienti influirà sulle prestazioni del mio negozio?**
**R4:** Per la maggior parte dei negozi, un'esportazione una tantum avrà un impatto trascurabile. Per i negozi con centinaia di migliaia di clienti, il processo di esportazione potrebbe richiedere alcuni istanti e consumare alcune risorse del server. Si consiglia generalmente di eseguire esportazioni di grandi dimensioni durante le ore non di punta se si prevede un tempo di elaborazione molto lungo. Il modulo è progettato per essere efficiente, ma le risorse del server sono sempre un fattore.

**D5: Voglio reimportare i clienti dopo aver apportato modifiche. Come faccio?**
**R5:** Questo modulo gestisce solo l'esportazione. Per reimportare, utilizzeresti lo strumento di importazione nativo di PrestaShop:

1.  Vai su **Parametri Avanzati > Importa**.
2.  Seleziona "Clienti" o "Indirizzi" come entità da importare.
3.  Carica il tuo file CSV modificato.
4.  Mappa attentamente le colonne dal tuo CSV ai campi del database di PrestaShop.

Testa sempre le importazioni prima su un ambiente di sviluppo o di staging e assicurati di avere un backup completo del database prima di eseguire qualsiasi importazione su larga scala sul tuo negozio live. Importazioni errate possono portare a perdita o corruzione dei dati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Esporta Clienti con indirizzo" (`exportcustomers`) è un modulo PrestaShop semplice, principalmente focalizzato sulla funzionalità del back-office. Segue un modello MVC standard di PrestaShop per la sua interfaccia amministrativa. La logica principale risiede nel file del modulo principale e in un Controller Admin dedicato. Non introduce nuove tabelle di database ma sfrutta le strutture `ObjectModel` esistenti di `Customer` e `Address` di PrestaShop per recuperare e formattare i dati per l'esportazione. La semplicità del modulo significa che non ha componenti front-office, classi personalizzate o asset JavaScript/CSS complessi.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Questo modulo non ha funzionalità front-office.
-   **Controller Admin Back-Office**:

    -   `exportcustomers/controllers/admin/AdminExportCustomers.php`
        -   **Nome classe e classe genitore**: `AdminExportCustomersController` che estende `ModuleAdminController`.
        -   **Responsabilità**: Questo è il controller principale responsabile della gestione della logica di esportazione di clienti e indirizzi. Quando vi si accede tramite il menu del back office di PrestaShop, avvia il processo di recupero dei dati di clienti e indirizzi dal database, formattandoli in una stringa CSV e inviandoli come file scaricabile al browser. Costruisce la riga di intestazione CSV con tutti i campi specificati (ID Cliente, Email, ID Indirizzo, Alias, ecc.) e quindi itera attraverso gli oggetti `Customer` e `Address` per popolare le righe di dati.
    -   `exportcustomers/controllers/admin/index.php`
        -   **Responsabilità**: Questo è un file segnaposto comune nelle directory dei controller admin dei moduli PrestaShop. Tipicamente contiene un semplice `header('Location: ../../index.php?controller=AdminHome')` o un reindirizzamento simile per prevenire l'elenco diretto delle directory o l'accesso, garantendo sicurezza e routing corretto all'interno del back office di PrestaShop. Non contiene alcuna logica funzionale per il modulo stesso.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce classi o modelli personalizzati nella directory `classes/`. Utilizza direttamente le classi `ObjectModel` principali di PrestaShop `Customer` e `Address` per recuperare i dati dal database.

### 4.4 Asset JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. Il processo di esportazione è tipicamente avviato da una semplice sottomissione di un modulo o da un link diretto, gestito interamente dal controller PHP.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. La sua interfaccia di back-office si basa interamente sullo stile predefinito del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non include alcun file di template Smarty personalizzato. L'`AdminExportCustomersController` probabilmente renderizza una vista molto semplice, forse solo un pulsante o un messaggio, direttamente all'interno del suo metodo `renderForm()` o `initContent()`, oppure attiva direttamente un download di file senza renderizzare un template complesso.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**: Questo modulo non crea tabelle di database personalizzate. Legge i dati dalle tabelle PrestaShop esistenti, principalmente `ps_customer` e `ps_address`.

    -   `ps_configuration`: Il modulo memorizza le sue impostazioni di configurazione interne (`mypresta_updates`, `update_`, `updatev_`) nella tabella `ps_configuration`.
-   **Tabella degli hook registrati**:
    Questo modulo non registra alcun hook front-office. La sua funzionalità è interamente confinata al back office.
    Probabilmente utilizza l'hook `actionAdminControllerSetMedia` (implicitamente o esplicitamente) per il suo controller admin, e potenzialmente `displayAdminProductsExtra` o simili per la sua voce di menu nel back-office.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin viene inizializzato. | Utilizzato da `ModuleAdminController` per aggiungere asset CSS/JS (anche se questo modulo non ne ha). |
| `displayAdminAdvancedParameters` | Renderizza il contenuto nella sezione "Parametri Avanzati" del back office. | Probabilmente utilizzato per aggiungere il link/punto di ingresso del modulo al menu "Parametri Avanzati". |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "Esporta Clienti con indirizzo", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
