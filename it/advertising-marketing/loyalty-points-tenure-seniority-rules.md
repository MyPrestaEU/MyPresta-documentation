---
title: "Punti fedeltà – Regole di anzianità (tenure) - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Punti fedeltà – Regole di anzianità (tenure) di MyPresta.eu."
sidebar:
  label: "Punti fedeltà – Regole di anzianità (tenure) - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Loyalty points – Tenure (seniority) rules su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-tenure-seniority-rules.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/loyalty-points-tenure-seniority-rules/)
>
> ---


# Punti fedeltà – Regole di anzianità (tenure)

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili sulla maggior parte degli ambienti di hosting. Questo modulo non ha requisiti specifici aggiuntivi oltre a una configurazione standard di PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestione moduli.

**Impostazioni generali**

-   **Abilita modulo:**

    *   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità del modulo.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Il modulo inizierà a elaborare le regole di fedeltà in base all'anzianità del cliente e ad assegnare i punti come configurato.
        *   *Quando disabilitato:* Il modulo cesserà di funzionare. Nessun nuovo punto verrà assegnato in base alle regole di anzianità e le regole esistenti verranno ignorate fino alla riabilitazione.
    *   **Valore consigliato:** SÌ
    *   **Scenario / esempio del commerciante:** Hai finito di impostare le tue regole e sei pronto a lanciare il tuo programma fedeltà. Abilita questa opzione per iniziare a premiare i clienti. Se hai bisogno di mettere in pausa temporaneamente il programma per manutenzione o revisione, puoi disabilitarlo qui.
-   **URL Cron Job:**

    *   **Cosa fa questa impostazione:** Visualizza un URL univoco che devi impostare come "cron job" sul tuo server web. Un cron job è un'attività pianificata che indica al tuo server di eseguire automaticamente questo URL a intervalli regolari (ad esempio, una volta al giorno). È così che il modulo controlla l'anzianità del cliente e assegna i punti senza che tu debba attivarli manualmente.
    *   **Effetto della modifica di questa impostazione:** Non puoi modificare direttamente questo URL. È generato dal modulo.
        *   *Quando configurato correttamente come cron job:* Il modulo eseguirà automaticamente i suoi controlli e assegnerà i punti secondo le tue regole.
        *   *Quando NON configurato come cron job:* L'assegnazione automatica dei punti del modulo non avverrà. Dovresti visitare manualmente questo URL nel tuo browser per attivare il processo, il che vanifica lo scopo dell'automazione.
    *   **Valore consigliato:** Copia questo URL e impostalo come cron job giornaliero sul tuo server.
    *   **Scenario / esempio del commerciante:** Dopo aver installato il modulo, copia questo URL. Vai al pannello di controllo del tuo hosting (ad esempio, cPanel, Plesk) e trova la sezione "Cron Jobs" o "Attività pianificate". Aggiungi un nuovo cron job per eseguire questo URL una volta ogni 24 ore. Ciò garantisce che i tuoi clienti ricevano i loro punti di anzianità automaticamente e in tempo.

### 2.2 Schermata di amministrazione dedicata: Regole di anzianità fedeltà (Back Office > MyPresta.eu > Regole di anzianità fedeltà)

Questa schermata ti consente di definire e gestire le regole specifiche per l'assegnazione di punti fedeltà in base all'anzianità del cliente.

-   **Nome schermata e posizione menu:** Puoi trovare questa schermata navigando su **MyPresta.eu > Regole di anzianità fedeltà** nel menu del Back Office di PrestaShop.
-   **Azioni e impostazioni disponibili:**

    *   **Tabella elenco regole:** Questa tabella visualizza tutte le tue regole di anzianità attive e inattive. Per ogni regola, vedrai:
        *   **ID:** Un identificatore univoco per la regola.
        *   **Anzianità (Giorni):** Il numero minimo di giorni in cui un cliente deve essere stato registrato per qualificarsi per questa regola.
        *   **Punti da assegnare:** Il numero di punti fedeltà che un cliente riceverà.
        *   **Attivo:** Un interruttore per abilitare o disabilitare la regola.
        *   **Azioni:** Pulsanti per "Modifica" o "Elimina" una regola.
    *   **Pulsante "Aggiungi nuova regola":** Clicca su questo pulsante per creare una nuova regola di anzianità.

    **Quando si aggiunge/modifica una regola:**
    Ti verrà presentato un modulo per definire i parametri della regola:

    *   **Anzianità (Giorni):**

        *   **Cosa fa questa impostazione:** Questo è il numero minimo di giorni in cui un cliente deve essere stato registrato nel tuo negozio per essere idoneo a questo specifico premio di punti fedeltà.
        *   **Effetto della modifica di questa impostazione:**
            *   *Impostando a 365:* I clienti registrati per almeno un anno si qualificheranno.
            *   *Impostando a 730:* I clienti registrati per almeno due anni si qualificheranno.
        *   **Valore consigliato:** Scegli valori che rappresentino tappe significative per i tuoi clienti (ad esempio, 365 giorni per 1 anno, 730 giorni per 2 anni, 1095 giorni per 3 anni).
        *   **Scenario / esempio del commerciante:** Vuoi premiare i clienti che sono stati con il tuo negozio per almeno un anno. Imposteresti questo valore a `365`.
    *   **Punti da assegnare:**

        *   **Cosa fa questa impostazione:** Questo è il numero esatto di punti fedeltà che verranno concessi a un cliente che soddisfa il requisito "Anzianità (Giorni)" per questa regola.
        *   **Effetto della modifica di questa impostazione:**
            *   *Impostando a 100:* I clienti qualificati ricevono 100 punti fedeltà.
            *   *Impostando a 50:* I clienti qualificati ricevono 50 punti fedeltà.
        *   **Valore consigliato:** Allinea questo valore con il valore del tuo programma di punti fedeltà esistente. Un buon punto di partenza potrebbero essere punti equivalenti a un piccolo sconto (ad esempio, 5-10% del valore medio di un ordine).
        *   **Scenario / esempio del commerciante:** Per ringraziare in modo significativo per un anno di fedeltà, potresti assegnare `250` punti, che potrebbero tradursi in uno sconto di 5€ sul loro prossimo acquisto.
    *   **Attivo:**

        *   **Cosa fa questa impostazione:** Questo interruttore determina se questa specifica regola è attualmente attiva e verrà considerata dal modulo quando assegna i punti.
        *   **Effetto della modifica di questa impostazione:**
            *   *Quando abilitato:* La regola verrà elaborata dal cron job e i punti verranno assegnati ai clienti qualificati.
            *   *Quando disabilitato:* La regola verrà ignorata e nessun punto verrà assegnato in base a questa specifica soglia di anzianità.
        *   **Valore consigliato:** SÌ (per le regole che vuoi siano attive).
        *   **Scenario / esempio del commerciante:** Hai creato una regola per 5 anni di anzianità ma vuoi testarla internamente prima di renderla operativa. Puoi mantenerla disabilitata finché non sei pronto ad attivarla.
-   **Effetto delle modifiche:**

    *   L'aggiunta di una nuova regola crea una nuova voce nel database che il cron job del modulo controllerà.
    *   La modifica di una regola ne altera i parametri (anzianità, punti, stato attivo), influenzando le future assegnazioni di punti.
    *   L'eliminazione di una regola la rimuove permanentemente e nessun altro punto verrà assegnato in base a quella specifica anzianità.
    *   La chiave di configurazione `PS_LIST_LIMIT` controlla il numero di elementi visualizzati per pagina nella tabella di elenco delle regole.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

    1.  **Pianifica i tuoi livelli di fedeltà:** Decidi quali tappe di anzianità vuoi premiare (ad esempio, 1 anno, 2 anni, 5 anni).
    2.  **Calcola i valori dei punti:** Determina quanti punti vuoi assegnare per ogni livello, considerando il valore monetario dei tuoi punti fedeltà.
    3.  **Crea regole:** Vai su **MyPresta.eu > Regole di anzianità fedeltà** e clicca su "Aggiungi nuova regola" per ogni livello.
    4.  **Monitora:** Controlla periodicamente i saldi dei punti fedeltà dei tuoi clienti e assicurati che il cron job funzioni correttamente.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | Abilita modulo | SÌ | Attiva/disattiva tutte le funzionalità del modulo. |
| Pagina di configurazione del modulo | URL Cron Job | Copia e imposta come cron job giornaliero | URL per l'esecuzione automatica del modulo per assegnare i punti. |
| Regole di anzianità fedeltà | Anzianità (Giorni) | 365, 730, 1095, ecc. | Numero minimo di giorni di registrazione per qualificarsi per i punti. |
| Regole di anzianità fedeltà | Punti da assegnare | Allineato al valore del programma fedeltà | Numero di punti fedeltà da assegnare. |
| Regole di anzianità fedeltà | Attivo | SÌ | Abilita/disabilita una specifica regola di anzianità. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non ricevono punti fedeltà, anche se ho impostato le regole.**
R1:

-   **Verifica attivazione modulo:** Assicurati che l'impostazione "Abilita modulo" nella pagina di configurazione principale sia impostata su SÌ.
-   **Verifica Cron Job:** La ragione più comune è un cron job configurato in modo errato o non in esecuzione. Ricontrolla l'URL del Cron Job dalla pagina di configurazione del modulo e assicurati che sia configurato correttamente sul tuo server di hosting per essere eseguito quotidianamente.
-   **Stato della regola:** Assicurati che le singole regole di anzianità fedeltà che hai creato siano contrassegnate come "Attive".
-   **Idoneità del cliente:** Il cliente ha effettivamente soddisfatto il requisito "Anzianità (Giorni)" per una delle tue regole attive? Il modulo assegna i punti solo una volta che un cliente supera una soglia.
-   **Cache Smarty:** A volte, la cache di PrestaShop può causare problemi di visualizzazione. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).

**D2: Come faccio a sapere se il cron job funziona correttamente?**
R2:

-   **Controlla i log dell'hosting:** La maggior parte dei provider di hosting offre un modo per visualizzare i log di esecuzione dei cron job nel tuo pannello di controllo (ad esempio, cPanel). Cerca le voci relative all'URL del cron job fornito dal modulo.
-   **Test manuale:** Puoi visitare manualmente l'URL del Cron Job nel tuo browser web. Questo attiverà il processo di assegnazione dei punti per quel momento. Se i punti vengono assegnati ai clienti idonei dopo questa visita manuale, conferma che la logica del modulo funziona e il problema riguarda la configurazione automatica del cron.

**D3: Posso assegnare punti retroattivamente ai clienti che hanno già superato un traguardo di anzianità prima che installassi il modulo?**
R3: Sì, quando il cron job viene eseguito per la prima volta dopo aver impostato le regole, valuterà tutti i clienti esistenti rispetto alle tue regole attive. Se un cliente soddisfa un requisito di anzianità e non gli sono stati assegnati punti per quella specifica regola in precedenza, li riceverà. Ciò significa che i clienti più anziani e fedeli riceveranno i loro punti meritati.

**D4: Il mio tema personalizzato non mostra correttamente i punti fedeltà, o le notifiche sembrano strane.**
R4: Questo modulo interagisce principalmente con il sistema di fedeltà principale di PrestaShop. Qualsiasi problema di visualizzazione con i punti fedeltà o le notifiche è solitamente correlato allo stile del tuo tema o alle sovrascritture per il modulo fedeltà nativo.

-   **Personalizzazione del tema:** Se hai un tema personalizzato, potrebbe avere i suoi modelli o CSS per la visualizzazione delle informazioni sulla fedeltà. Potrebbe essere necessario consultare lo sviluppatore del tuo tema o un webmaster per assicurarti che si integri correttamente con le funzionalità di fedeltà di PrestaShop.
-   **Test con tema predefinito:** Passa temporaneamente al tema predefinito di PrestaShop (Classic) per vedere se il problema persiste. Se funziona correttamente sul tema predefinito, il problema è sicuramente con il tuo tema personalizzato.

**D5: Cosa succede se modifico una regola (ad esempio, aumento i punti) dopo che i clienti hanno già ricevuto punti da essa?**
R5: Il modulo è progettato per assegnare punti *una volta* per ogni regola quando un cliente raggiunge per la prima volta la soglia di anzianità. Se modifichi una regola (ad esempio, aumenti i punti per 365 giorni da 100 a 150), i clienti che hanno già ricevuto 100 punti per 365 giorni *non* riceveranno automaticamente i 50 punti aggiuntivi. La regola è già stata "soddisfatta" per loro. Se vuoi dare loro i punti extra, dovrai regolare manualmente il loro saldo fedeltà o creare una nuova regola temporanea.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Punti fedeltà – Regole di anzianità (tenure)" (`myprestaloyalty_tenure`) estende la funzionalità di PrestaShop introducendo un nuovo concetto di assegnazione di punti fedeltà basato sull'anzianità di registrazione del cliente. Segue un'architettura standard del modulo PrestaShop, sfruttando `ObjectModel` per la gestione delle regole di anzianità e un controller frontale dedicato per l'esecuzione del cron job. Il modulo si integra con il `LoyaltyModule` principale di PrestaShop per assegnare i punti, garantendo la compatibilità con il sistema di fedeltà nativo.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    *   `controllers/front/cron.php`
        *   **Nome classe:** `MyprestaloyaltyTenureCronModuleFrontController` (estende `ModuleFrontController`)
        *   **Responsabilità:** Questo controller è progettato per essere eseguito tramite un cron job. Quando viene richiamato, itera su tutte le regole di anzianità attive e tutti i clienti registrati. Per ogni cliente, calcola l'età di registrazione e verifica se si qualificano per una qualsiasi regola attiva per la quale non hanno ancora ricevuto punti. Se un cliente si qualifica, assegna i punti fedeltà specificati utilizzando la funzionalità del `LoyaltyModule` principale. Tipicamente restituisce un semplice messaggio di successo o un output di log.
    *   `controllers/front/index.php`
        *   **Nome classe:** `MyprestaloyaltyTenureIndexModuleFrontController` (estende `ModuleFrontController`)
        *   **Responsabilità:** Questo è un controller frontale segnaposto o predefinito. In molti moduli, se non è definita alcuna azione specifica, `index.php` potrebbe gestire una vista predefinita o un reindirizzamento. Per questo modulo, la sua interazione principale con il front-office avviene tramite il controller `cron.php`.
-   **Controller Admin Back-Office**:

    *   `controllers/admin/AdminMyprestaloyaltyTenureController.php`
        *   **Nome classe:** `AdminMyprestaloyaltyTenureController` (estende `ModuleAdminController`)
        *   **Nome scheda:** "Regole di anzianità fedeltà" (sotto il menu MyPresta.eu)
        *   **Entità gestita:** `MyprestaloyaltyTenureRule` (mappa alla tabella del database `_myprestaloyalty_tenure_rule`)
        *   **Responsabilità:** Questo controller fornisce l'interfaccia CRUD (Crea, Leggi, Aggiorna, Elimina) per la gestione delle regole di anzianità fedeltà nel Back Office di PrestaShop. Utilizza `HelperList` per visualizzare l'elenco delle regole e `HelperForm` per aggiungere/modificare singole regole. Gestisce l'invio dei moduli, la convalida e l'interazione con l'`ObjectModel` `MyprestaloyaltyTenureRule`.
    *   `controllers/admin/index.php`
        *   **Nome classe:** (Nessuna classe specifica, tipicamente usata per la sicurezza)
        *   **Responsabilità:** Questo file di solito contiene un semplice `header('Location: ../../index.php?controller=AdminHome'); exit;` o simile per impedire l'elenco diretto delle directory e garantire che i controller admin siano accessibili tramite il dispatcher di PrestaShop.

### 4.3 Classi e modelli principali (`classes/`)

-   `classes/index.php`

    *   **Responsabilità:** File di sicurezza standard di PrestaShop, tipicamente contenente `header('Location: ../../index.php?controller=AdminHome'); exit;` per impedire l'accesso diretto alla directory `classes`.
-   `classes/MyprestaloyaltyTenureRule.php`

    *   **Nome classe:** `MyprestaloyaltyTenureRule` (estende `ObjectModel`)
    *   **Tabella database:** `_myprestaloyalty_tenure_rule`
    *   **Campi `$definition`:**
        *   `id_myprestaloyalty_tenure_rule`: Chiave primaria.
        *   `tenure_days`: Intero, il numero minimo di giorni in cui un cliente deve essere registrato.
        *   `points_to_award`: Intero, il numero di punti fedeltà da concedere.
        *   `active`: Booleano, se la regola è attiva (0 o 1).
    *   **Metodi pubblici chiave:**
        *   `__construct()`: Costruttore `ObjectModel` standard.
        *   `add()`: Sovrascrive `ObjectModel::add()` per logica personalizzata se necessaria (ad esempio, gestione delle date, convalida).
        *   `update()`: Sovrascrive `ObjectModel::update()`.
        *   `delete()`: Sovrascrive `ObjectModel::delete()`.
        *   `getAllActiveRules()`: Metodo statico per recuperare tutte le regole attive dal database.
        *   `hasCustomerReceivedPointsForRule($id_customer, $id_rule)`: Metodo statico per verificare se un cliente specifico ha già ricevuto punti per una data regola. Questo è fondamentale per prevenire assegnazioni duplicate.
        *   `markCustomerAsAwarded($id_customer, $id_rule)`: Metodo statico per registrare che un cliente ha ricevuto punti per una regola.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo indica che non sono presenti file JavaScript personalizzati in `views/js/`. Tutte le interazioni sono gestite lato server o tramite gli helper standard di PrestaShop per moduli/liste.

### 4.5 Fogli di stile CSS (`views/css/`)

Il dossier del modulo indica che non sono presenti file CSS personalizzati in `views/css/`. L'interfaccia del Back Office si basa sugli stili del tema admin predefinito di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il dossier del modulo indica che non sono presenti file di template Smarty personalizzati in `views/templates/`. Le schermate di configurazione e gestione delle regole del modulo sono renderizzate utilizzando le classi `HelperForm` e `HelperList` di PrestaShop, che si basano sui file di template principali di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    *   `ps_myprestaloyalty_tenure_rule`: Memorizza le definizioni di ogni regola di anzianità.
        *   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        *   `tenure_days` INT(10) UNSIGNED NOT NULL
        *   `points_to_award` INT(10) UNSIGNED NOT NULL
        *   `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
        *   PRIMARY KEY (`id_myprestaloyalty_tenure_rule`)
    *   `ps_myprestaloyalty_tenure_awarded`: Registra quali clienti hanno ricevuto punti per quali regole, per prevenire assegnazioni duplicate.
        *   `id_myprestaloyalty_tenure_awarded` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        *   `id_customer` INT(10) UNSIGNED NOT NULL
        *   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL
        *   `date_awarded` DATETIME NOT NULL
        *   PRIMARY KEY (`id_myprestaloyalty_tenure_awarded`)
        *   UNIQUE KEY `customer_rule` (`id_customer`, `id_myprestaloyalty_tenure_rule`)
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente alcun hook di visualizzazione front-office (come `displayHeader`, `displayRightColumn`, `displayProductExtraContent`, `displayFooter`) poiché la sua funzione principale è l'elaborazione in background tramite cron.
    Utilizza implicitamente:

    | Nome Hook | Tempo di esecuzione | Scopo tecnico |
    |---|---|---|
    | `actionModuleInstall` | Durante l'installazione del modulo | Crea tabelle del database, registra la scheda admin. |
    | `actionModuleUninstall` | Durante la disinstallazione del modulo | Elimina tabelle del database e configurazione. |
    | `actionAdminControllerSetMedia` | Quando viene caricato un controller admin | Se il modulo avesse JS/CSS personalizzati per l'admin, li registrerebbe qui. (Non utilizzato in questo modulo in base all'inventario) |
    | `displayBackOfficeTop` | Renderizza il contenuto nella parte superiore del Back Office | Utilizzato per visualizzare l'URL del cron job e le istruzioni nella pagina di configurazione del modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Punti fedeltà – Regole di anzianità (tenure)", fare riferimento al proprio account cliente su MyPresta.eu. Il nostro team è dedicato a fornire assistenza tempestiva e a garantire che il modulo funzioni in modo ottimale.

-   **Accedi a download e aggiornamenti:** Accedi al tuo account su [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/).
-   **Contatta il supporto:** Utilizza i canali di supporto forniti all'interno del tuo account MyPresta.eu per qualsiasi problema tecnico o domanda.
