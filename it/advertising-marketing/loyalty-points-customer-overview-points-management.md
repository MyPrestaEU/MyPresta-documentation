---
title: "Punti fedeltà – Panoramica clienti e gestione punti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Punti fedeltà – Panoramica clienti e gestione punti di MyPresta.eu."
sidebar:
  label: "Punti fedeltà – Panoramica clienti e gestione punti - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Loyalty points – Customer overview & points management su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-customer-overview-points-management.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/loyalty-points-customer-overview-points-management/)
>
> ---


# Punti fedeltà – Panoramica clienti e gestione punti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono richieste per PrestaShop stesso e sono tipicamente disponibili su tutti gli ambienti di hosting compatibili.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina di configurazione principale del modulo "Punti fedeltà – Panoramica clienti e gestione punti". Questa schermata fornisce le impostazioni generali per il comportamento del modulo.

#### Abilita notifica email manuale

- **Cosa fa questa impostazione:** Questo interruttore controlla se viene inviata una notifica email al cliente quando regoli manualmente i suoi punti fedeltà.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Se aggiungi o rimuovi manualmente punti per un cliente, riceverà un'email che lo informa della modifica e del suo nuovo saldo. Questo aiuta a mantenere i clienti informati e a costruire trasparenza.
  - *Quando disabilitato:* Le regolazioni manuali dei punti avverranno silenziosamente, senza alcuna notifica email al cliente. Questo potrebbe essere preferibile per piccole correzioni interne o se gestisci la comunicazione con i clienti tramite altri canali.
- **Valore consigliato:** SÌ
- **Scenario/esempio per il commerciante:** Hai appena aggiunto 50 punti bonus all'account di un cliente come regalo di compleanno. Se questa impostazione è abilitata, il cliente riceve immediatamente un'email che dice: "Buon compleanno! Abbiamo aggiunto 50 punti fedeltà al tuo account. Il tuo nuovo saldo è X punti." Questo migliora l'esperienza del cliente e rende la ricompensa tangibile.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### Gestione Punti Fedeltà Cliente (Back Office > Catalogo > Punti Fedeltà)

Questa è la schermata di gestione principale per il modulo, accessibile tramite una nuova voce di menu nel back office di PrestaShop.

- **Nome schermata e posizione menu:** **Catalogo > Punti Fedeltà** (o simile, a seconda della versione di PrestaShop e della personalizzazione del menu).
- **Azioni e impostazioni disponibili:**
  - **Elenco clienti:** Vedrai un elenco completo di tutti i tuoi clienti, insieme ai loro attuali saldi di punti fedeltà.
  - **Cerca e filtra:** Trova facilmente clienti specifici per nome, email o ID.
  - **Visualizza cronologia:** Per ogni cliente, puoi cliccare per visualizzare un registro dettagliato di tutte le transazioni di punti fedeltà (guadagnati, spesi, scaduti e regolati manualmente).
  - **Aggiungi/Rimuovi punti:**
    - Clicca sulla riga di un cliente o su un'icona "Modifica" per accedere alla sua interfaccia di gestione punti individuale.
    - Troverai campi per aggiungere o sottrarre manualmente un numero specifico di punti fedeltà.
    - Un campo "Motivo" ti consente di annotare il motivo della regolazione (es. "Bonus compleanno", "Compensazione per ordine in ritardo", "Correzione punti"). Questo motivo è cruciale per i tuoi registri interni e per il servizio clienti.
    - Al salvataggio, il saldo del cliente viene aggiornato e, se l'impostazione "Abilita notifica email manuale" è attiva, viene inviata un'email.
  - **Paginazione:** Si applicherà la paginazione standard di PrestaShop (`PS_LIST_LIMIT`), consentendoti di controllare quanti clienti vengono visualizzati per pagina.
- **Effetto delle modifiche:**
  - **Aggiunta di punti:** Aumenta il saldo dei punti fedeltà del cliente. Questo può essere utilizzato per premiare i clienti, offrire compensazioni o eseguire promozioni speciali.
  - **Rimozione di punti:** Diminuisce il saldo dei punti fedeltà del cliente. Ciò potrebbe essere necessario per correggere errori, revocare punti da ordini restituiti o gestire attività fraudolente.
  - **Visualizzazione della cronologia:** Fornisce una traccia di controllo trasparente di tutti i movimenti dei punti, preziosa per il supporto clienti e la reportistica interna.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. **Controlla regolarmente i saldi dei punti dei clienti:** Soprattutto dopo promozioni o se i clienti segnalano discrepanze.
  2. **Usa diligentemente il campo "Motivo":** Fornisci sempre un motivo chiaro e conciso per qualsiasi regolazione manuale. Questo ti farà risparmiare tempo e confusione in seguito quando esaminerai la cronologia o spiegherai le modifiche ai clienti.
  3. **Sfrutta le notifiche email:** Per le regolazioni positive (bonus, premi), l'abilitazione delle notifiche email può aumentare significativamente la soddisfazione del cliente e la consapevolezza dei loro vantaggi di fedeltà. Per le correzioni, considera se un'email è necessaria o se le note interne sono sufficienti.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita notifica email manuale | SÌ | Controlla se i clienti ricevono un'email quando i loro punti fedeltà vengono regolati manualmente. |
| Catalogo > Punti Fedeltà | Elenco clienti e ricerca | N/A | Visualizza tutti i clienti e i loro attuali saldi di punti fedeltà. |
| Catalogo > Punti Fedeltà | Aggiungi/Rimuovi punti | N/A | Consente la regolazione manuale dei punti fedeltà di un cliente. |
| Catalogo > Punti Fedeltà | Motivo della regolazione | N/A (Input richiesto) | Fornisce una nota interna sul motivo per cui i punti sono stati aggiunti o rimossi. |
| Catalogo > Punti Fedeltà | Visualizza cronologia | N/A | Mostra un registro dettagliato di tutte le transazioni di punti fedeltà per un cliente specifico. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho aggiunto punti, ma il cliente dice di non aver ricevuto un'email.**
R: Innanzitutto, verifica se "Abilita notifica email manuale" è impostato su SÌ nella configurazione principale del modulo. Se lo è, controlla i log delle email del tuo negozio (se disponibili) o i log di posta del tuo server per vedere se l'email è stata inviata. Inoltre, consiglia al cliente di controllare la sua cartella spam/posta indesiderata. Assicurati che le impostazioni email di PrestaShop siano configurate correttamente e che il tuo server di posta funzioni.

**D2: Non riesco a trovare la voce di menu "Punti Fedeltà" nel mio Back Office.**
R: Dopo l'installazione, il modulo dovrebbe creare una nuova voce di menu, tipicamente sotto "Catalogo" o "Clienti". Se manca, prova a svuotare la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota cache). Se ancora non appare, assicurati che il modulo sia abilitato e installato correttamente. Inoltre, controlla i tuoi permessi utente in **Parametri Avanzati > Team > Profili** per assicurarti che il tuo profilo amministratore abbia accesso al controller del modulo.

**D3: Il saldo dei punti fedeltà del cliente non si aggiorna nel front office dopo aver apportato una modifica manuale.**
R: Questo è solitamente un problema di caching. Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota cache). Se utilizzi un modulo di caching di terze parti o un CDN, svuota anche la sua cache. Il modulo aggiorna direttamente il database, quindi il front office dovrebbe riflettere le modifiche una volta che la cache è stata aggiornata.

**D4: Posso importare/esportare i dati dei punti fedeltà con questo modulo?**
R: Questo modulo si concentra sulla gestione manuale e sulla visualizzazione all'interno del back office di PrestaShop. Non include funzionalità di importazione/esportazione integrate per operazioni di dati in blocco. Per tali attività, potrebbe essere necessario considerare query di database personalizzate o altri moduli specializzati.

**D5: Cosa succede se disinstallo questo modulo?**
R: Alla disinstallazione, il modulo rimuoverà le sue voci di menu amministrative dedicate e potenzialmente le sue impostazioni di configurazione. Tuttavia, è progettato per gestire i punti fedeltà esistenti, che sono tipicamente parte del sistema di fedeltà principale di PrestaShop o di un altro modulo di fedeltà. I punti stessi dovrebbero rimanere nel database, ma perderesti la comoda interfaccia di gestione fornita da questo modulo. Esegui sempre il backup del tuo database prima di disinstallare qualsiasi modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Punti fedeltà – Panoramica clienti e gestione punti" (`myprestaloyalty_customerpoints`) è costruito seguendo il pattern MVC di PrestaShop, estendendo principalmente `Module` per la sua funzionalità principale e `AdminController` per la sua interfaccia dedicata nel back-office. Interagisce con il sistema di fedeltà principale di PrestaShop (o un modulo di fedeltà compatibile) fornendo un livello di gestione migliorato. Il modulo introduce un `ObjectModel` personalizzato per registrare le regolazioni manuali dei punti, garantendo una traccia di controllo.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Questo modulo non include alcun controller front-office dedicato. Tutte le interazioni con il cliente relative ai punti fedeltà sono gestite dal modulo di fedeltà principale di PrestaShop o dal tema stesso.
- **Controller Admin Back-Office**:

  - `controllers/admin/AdminMyprestaloyaltyCustomerPointsController.php`
    - **Nome classe e classe genitore**: `AdminMyprestaloyaltyCustomerPointsController` estende `ModuleAdminController`.
    - **Responsabilità**: Questo è il controller principale del back-office per la gestione dei punti fedeltà dei clienti. Fornisce la vista elenco dei clienti con i loro saldi fedeltà, consente la ricerca e il filtraggio e gestisce il modulo per aggiungere/rimuovere manualmente punti per i singoli clienti. Gestisce l'entità `customer_points` (anche se interagisce principalmente con i dati dei punti fedeltà esistenti, registra anche le modifiche manuali tramite `MyprestaloyaltyCustomerPointsManualLog`).
    - **Nome tab**: "Punti Fedeltà" (o simile, impostato dinamicamente durante l'installazione).
    - **Entità gestita**: Visualizza e consente la modifica dei punti fedeltà dei clienti, registrando queste modifiche.
  - `controllers/admin/index.php`
    - **Nome classe e classe genitore**: Questo file serve tipicamente come segnaposto o un semplice reindirizzamento nei moduli PrestaShop. Potrebbe contenere una semplice istruzione `die()` o un reindirizzamento per impedire l'accesso diretto, garantendo che la logica del controller venga eseguita tramite il meccanismo di dispatching di PrestaShop. Non gestisce un'entità specifica né fornisce una vista distinta.

### 4.3 Classi e Modelli Core (`classes/`)

- `classes/MyprestaloyaltyCustomerPointsManualLog.php`
  - **Nome classe**: `MyprestaloyaltyCustomerPointsManualLog` estende `ObjectModel`.
  - **Tabella database**: `_myprestaloyalty_customer_points_manual_log` (o simile, prefissata da `_DB_PREFIX_`).
  - **Campi `$definition`**:
    - `id_myprestaloyalty_customer_points_manual_log`: Chiave primaria.
    - `id_customer`: L'ID del cliente i cui punti sono stati regolati.
    - `id_employee`: L'ID dell'impiegato che ha effettuato la regolazione.
    - `points_change`: Il numero di punti aggiunti o rimossi (può essere positivo o negativo).
    - `reason`: Un campo di testo che spiega il motivo della regolazione.
    - `date_add`: Timestamp di quando è stata effettuata la regolazione.
  - **Metodi pubblici chiave e logica di business**: Questa classe è responsabile della persistenza dei dettagli di ogni regolazione manuale dei punti fedeltà effettuata tramite l'interfaccia del back-office. Fornisce un record storico, cruciale per l'audit e il supporto clienti.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non include alcun file JavaScript personalizzato. Tutte le interazioni nella schermata di gestione del back-office sono gestite dai meccanismi predefiniti di jQuery e di invio dei moduli di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato. Si basa sullo stile predefinito del back-office di PrestaShop per i suoi moduli di configurazione e le viste elenco, garantendo un aspetto e una sensazione coerenti.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo non include alcun file di template Smarty personalizzato. Il modulo di configurazione e le viste di elenco/modifica dell'amministrazione sono renderizzati utilizzando i template predefiniti `getContent()` e `ModuleAdminController` di PrestaShop.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - `ps_myprestaloyalty_customer_points_manual_log`:
    - `id_myprestaloyalty_customer_points_manual_log` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `points_change` INT(11) NOT NULL
    - `reason` TEXT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_customer_points_manual_log`)
    - KEY `id_customer` (`id_customer`)
    - KEY `id_employee` (`id_employee`)
  - **Record di configurazione (in `ps_configuration`)**:
    - `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Memorizza il valore booleano per abilitare/disabilitare le notifiche email per le regolazioni manuali dei punti.
- **Tabella degli hook registrati**:
  Questo modulo fornisce principalmente funzionalità di back-office e non registra alcun hook di visualizzazione front-office (`displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductExtraContent`, ecc.) o hook di azione (`actionValidateOrder`, `actionProductUpdate`, ecc.) nel suo metodo `install()` principale. La sua integrazione avviene tramite `AdminController` e l'interazione diretta con il database per la registrazione.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Punti fedeltà – Panoramica clienti e gestione punti", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
