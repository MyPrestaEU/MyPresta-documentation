---
title: "Disponibilità corriere per valore carrello - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Carrier availability by cart value' di MyPresta.eu."
sidebar:
  label: "Disponibilità corriere per valore carrello - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Carrier availability by cart value su MyPresta.eu](https://mypresta.eu/modules/ordering-process/carrier-availability-by-cart-value.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/carrier-availability-by-cart-value/)
>
> ---


# Disponibilità corriere per valore carrello

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su qualsiasi ambiente di hosting moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina di configurazione principale del modulo.

- **Cosa fa questa impostazione:** Questa schermata gestisce principalmente le impostazioni generali del modulo, spesso relative agli aggiornamenti o alla funzionalità di base.
- **Effetto della modifica di questa impostazione:**
  - `mypresta_updates`: Questa è un'impostazione comune tra i moduli MyPresta.eu.
    - *Quando abilitata:* Il modulo controllerà periodicamente la disponibilità di nuove versioni e aggiornamenti da MyPresta.eu. Questo ti aiuta a rimanere aggiornato con correzioni di bug e nuove funzionalità.
    - *Quando disabilitata:* Il modulo non controllerà automaticamente gli aggiornamenti. Dovrai controllare manualmente le nuove versioni su MyPresta.eu.
  - `update_` e `updatev_`: Queste sono impostazioni interne utilizzate dal meccanismo di aggiornamento del modulo per tenere traccia dell'ultima verifica e della versione disponibile. Tipicamente non è necessario interagire direttamente con queste.
- **Valore consigliato:**
  - Per `mypresta_updates`: **SÌ** (Abilitato). È sempre consigliabile mantenere i moduli aggiornati per sicurezza, prestazioni e nuove funzionalità.
- **Scenario / esempio per il commerciante:** L'abilitazione degli aggiornamenti garantisce che il tuo modulo esegua sempre l'ultima versione, prevenendo potenziali problemi di compatibilità con futuri aggiornamenti di PrestaShop o altri moduli.

### 2.2 Schermata amministrativa dedicata: Regole di disponibilità del corriere

Questo è il cuore del modulo dove definisci le regole per la disponibilità del corriere in base al valore del carrello.

- **Nome schermata e posizione nel menu:**

  - Nel tuo Back Office di PrestaShop, vai su **Spedizione > Disponibilità corriere per valore ordine**.
  - Questo aprirà una nuova schermata dedicata dove puoi gestire le tue regole.
- **Azioni e impostazioni disponibili:**
  Questa schermata presenta un elenco di regole esistenti e ti consente di aggiungerne di nuove o di modificarle/eliminarle.

  **Colonne della tabella di elenco:**

  - **ID**: Identificatore univoco per la regola.
  - **Corriere**: Il nome del corriere di spedizione a cui si applica la regola.
  - **Ordine\_da**: Il valore minimo del carrello affinché questo corriere sia disponibile.
  - **Ordine\_a**: Il valore massimo del carrello affinché questo corriere sia disponibile.
  - **Attivo**: Un interruttore per abilitare o disabilitare la regola senza eliminarla.

  **Aggiunta/Modifica di una regola (Campi del modulo):**
  Quando clicchi su "Aggiungi nuova regola" o modifichi una esistente, vedrai un modulo con i seguenti campi:

  - **Disponibilità corriere per valore ordine**: Questo è un elenco a discesa dove selezioni il corriere di spedizione specifico a cui vuoi applicare la regola.

    - *Effetto:* La regola che definisci influenzerà solo la disponibilità del corriere scelto.
    - *Valore consigliato:* Seleziona il corriere che desideri gestire.
    - *Scenario per il commerciante:* Se vuoi limitare la "Consegna Espressa" agli ordini di alto valore, selezioneresti "Consegna Espressa" qui.
  - **Valore ordine da**: Inserisci il valore totale minimo del carrello (nella tua valuta predefinita) affinché questo corriere sia disponibile.

    - *Effetto:* Se il valore del carrello del cliente è inferiore a questo importo, il corriere selezionato non verrà mostrato durante il checkout.
    - *Valore consigliato:* Inserisci `0` se non c'è un minimo, o un importo specifico (es. `50.00`).
    - *Scenario per il commerciante:* Imposta a `50.00` affinché la "Spedizione Gratuita" appaia solo per ordini superiori a $50.
  - **Valore ordine a**: Inserisci il valore totale massimo del carrello (nella tua valuta predefinita) affinché questo corriere sia disponibile.

    - *Effetto:* Se il valore del carrello del cliente è superiore a questo importo, il corriere selezionato non verrà mostrato durante il checkout.
    - *Valore consigliato:* Lascia vuoto o imposta a `0` se non c'è un massimo, o un importo specifico (es. `200.00`).
    - *Scenario per il commerciante:* Imposta a `200.00` per la "Spedizione Standard" per evitare che venga scelta per ordini di valore molto elevato che dovrebbero utilizzare la "Spedizione Assicurata".
  - **Attivo**: Un semplice interruttore ON/OFF.

    - *Effetto:*
      - *Quando abilitato:* La regola è attiva e filtrerà la disponibilità del corriere.
      - *Quando disabilitato:* La regola viene ignorata e il corriere sarà disponibile in base ad altre impostazioni di PrestaShop (peso, prezzo, zone) indipendentemente dal valore del carrello.
    - *Valore consigliato:* **ON** per le regole attive.
    - *Scenario per il commerciante:* Disabilita temporaneamente una regola durante una promozione senza eliminarla.
  - **Salva**: Clicca su questo pulsante per applicare le modifiche o creare la nuova regola.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

  1. **Identifica i tuoi corrieri:** Elenca tutti i tuoi corrieri di spedizione e i loro casi d'uso previsti.
  2. **Definisci gli intervalli di valore:** Per ogni corriere, decidi se esiste un intervallo di valore del carrello specifico in cui dovrebbe essere disponibile.
     - *Esempio 1:* "Spedizione Economica" per ordini da $0 a $75.
     - *Esempio 2:* "Spedizione Standard" per ordini da $75 a $250.
     - *Esempio 3:* "Premium Assicurata" per ordini da $250 in su (imposta "Valore ordine da" a 250, lascia "Valore ordine a" vuoto/0).
  3. **Aggiungi regole:** Vai su **Spedizione > Disponibilità corriere per valore ordine** e clicca su "Aggiungi nuova regola".
  4. **Configura ogni regola:** Seleziona il corriere, inserisci "Valore ordine da" e "Valore ordine a", e assicurati che "Attivo" sia ON.
  5. **Testa accuratamente:** Dopo aver impostato le tue regole, effettua acquisti di prova con diversi valori del carrello per assicurarti che i corrieri vengano visualizzati come previsto.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | `mypresta_updates` | SÌ (Abilitato) | Abilita i controlli automatici per gli aggiornamenti del modulo. |
| Regole Disponibilità Corriere | Corriere | Seleziona dall'elenco | Il corriere di spedizione specifico a cui si applica questa regola. |
| Regole Disponibilità Corriere | Valore ordine da | `0` o importo specifico | Valore minimo del carrello affinché il corriere sia disponibile. |
| Regole Disponibilità Corriere | Valore ordine a | `0` (nessun max) o importo specifico | Valore massimo del carrello affinché il corriere sia disponibile. |
| Regole Disponibilità Corriere | Attivo | ON | Abilita o disabilita la specifica regola di disponibilità del corriere. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato le regole, ma i corrieri non cambiano nel checkout. Cosa c'è che non va?**
R1:

- **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione del modulo. Vai su **Parametri avanzati > Prestazioni**, quindi clicca su "Svuota la cache" in alto a destra.
- **Conflitti di regole:** Controlla se hai regole in conflitto. Ad esempio, se il Corriere A è impostato da $0-$100 e il Corriere B è impostato da $50-$150, assicurati che i tuoi intervalli siano logici.
- **Stato del corriere:** Assicurati che i corrieri stessi siano attivi e configurati correttamente in **Spedizione > Corrieri** in PrestaShop. Questo modulo filtra solo i corrieri *disponibili*, non attiva quelli inattivi.
- **Altre restrizioni del corriere:** Ricorda che PrestaShop ha le sue restrizioni sui corrieri (per zona, peso, prezzo). Questo modulo *aggiunge* un altro livello di filtraggio. Se un corriere è già limitato per peso, questo modulo non lo renderà disponibile.

**D2: Il mio simbolo di valuta non viene visualizzato correttamente, o i valori sembrano sbagliati.**
R2: Il modulo utilizza la valuta predefinita del tuo negozio per i campi "Valore ordine da" e "Valore ordine a". Assicurati che la tua valuta predefinita sia impostata correttamente in **Internazionale > Valute**. Il modulo opera sul valore numerico, quindi il simbolo visualizzato nel back office è per tuo riferimento.

**D3: Posso usare questo modulo con altri moduli di spedizione?**
R3: Sì, generalmente. Questo modulo si aggancia al processo standard di PrestaShop per filtrare gli elenchi dei corrieri. Applicherà le sue regole *dopo* che altre condizioni principali di PrestaShop (come peso, prezzo, zona) avranno già ristretto l'elenco dei potenziali corrieri. Se un altro modulo filtra anche i corrieri, si applicheranno le regole più restrittive di tutti i moduli.

**D4: Come faccio a rendere un corriere *sempre* disponibile, indipendentemente dal valore del carrello?**
R4: Non è necessario creare una regola per un tale corriere. Se un corriere non è elencato nelle tue regole di "Disponibilità corriere per valore ordine", rimarrà disponibile in base alle impostazioni predefinite del corriere di PrestaShop (peso, prezzo, zona, ecc.) senza alcuna restrizione di valore del carrello da parte di questo modulo.

**D5: Il modulo sembra rallentare il mio checkout. È normale?**
R5: Questo modulo è progettato per essere leggero e non dovrebbe influire significativamente sulle prestazioni. Se noti un rallentamento, assicurati che la tua installazione di PrestaShop sia ottimizzata (ad esempio, caching abilitato, ultima versione di PHP, nessun modulo eccessivo). Se il problema persiste, contatta il supporto MyPresta.eu con i dettagli della tua configurazione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Disponibilità corriere per valore carrello" (`cbp`) segue l'architettura standard dei moduli PrestaShop, sfruttando principalmente un AdminController per la configurazione e un hook Front-Office per modificare l'elenco dei corrieri durante il checkout. Utilizza un `ObjectModel` personalizzato per gestire le regole di disponibilità dei corrieri nella propria tabella del database.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:
  Questo modulo non include alcun controller front-office dedicato. Tutta la logica front-office è gestita direttamente tramite un hook nel file principale del modulo (`cbp.php`).
- **Controller Admin Back-Office**:

  - `cbp/controllers/admin/AdminCbpr.php`

    - **Nome classe:** `AdminCbprController` (estende `ModuleAdminController`)
    - **Responsabilità:** Questa è l'interfaccia amministrativa principale per la gestione delle regole di disponibilità dei corrieri. Gestisce le operazioni CRUD (Create, Read, Update, Delete) per l'entità `cbpr`.
    - **Nome scheda:** "Disponibilità corriere per valore ordine" (sotto il menu Spedizione).
    - **Entità gestita:** `Cbpr` (l'`ObjectModel` personalizzato per le regole dei corrieri).
    - **Caratteristiche chiave:**
      - Visualizza una vista `list` di tutte le regole configurate, inclusi ID, nome del corriere, Order\_from, Order\_to e stato Attivo.
      - Fornisce moduli `add` e `edit` per le singole regole, consentendo la selezione di un corriere e l'inserimento dei valori min/max dell'ordine.
      - Gestisce l'invio dei moduli e le interazioni con il database per salvare e aggiornare le regole.
      - Utilizza `PS_CURRENCY_DEFAULT` per visualizzare le informazioni sulla valuta nei moduli.
  - `cbp/controllers/admin/index.php`

    - **Responsabilità:** Questo file è un file `index.php` vuoto standard, tipicamente incluso nelle directory di PrestaShop per prevenire l'elenco delle directory per motivi di sicurezza. Non contiene alcuna logica di controller funzionale.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non ha una directory `classes/` dedicata. L'`ObjectModel` principale per la gestione delle regole dei corrieri è probabilmente definito direttamente all'interno del file principale del modulo (`cbp/cbp.php`) o gestito implicitamente dall'`AdminCbprController` utilizzando una definizione `ObjectModel` dinamica.

Dato che l'`AdminCbprController` gestisce una tabella denominata `cbpr`, deve esserci una classe `ObjectModel`, probabilmente denominata `Cbpr`, definita da qualche parte. Questa classe definirebbe la struttura delle regole di disponibilità dei corrieri.

**`ObjectModel` `Cbpr` presunto (probabilmente in `cbp.php`):**

- **Nome classe:** `Cbpr` (estende `ObjectModel`)
- **Tabella del database:** `ps_cbpr` (o `_cbpr` con prefisso)
- **Campi `$definition` (previsti):**
  - `id_cbpr`: Chiave primaria.
  - `id_carrier`: Chiave esterna alla tabella `ps_carrier`.
  - `order_from`: Campo decimale per il valore minimo del carrello.
  - `order_to`: Campo decimale per il valore massimo del carrello.
  - `active`: Campo booleano per lo stato della regola.
- **Metodi chiave:** Metodi `ObjectModel` standard per `add()`, `update()`, `delete()`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non contiene alcun file JavaScript personalizzato in `views/js/`. Tutta la logica front-office è gestita lato server tramite hook PHP. I moduli back-office si basano sulla gestione predefinita dei moduli di PrestaShop e su jQuery.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non contiene alcun file CSS personalizzato in `views/css/`. L'interfaccia back-office utilizza lo stile predefinito di PrestaShop per i moduli e gli elenchi di `ModuleAdminController`. Le modifiche al front-office sono gestite filtrando l'elenco dei corrieri direttamente in PHP, non tramite il rendering di nuovi modelli.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo non contiene alcun file di template Smarty personalizzato in `views/templates/`. I moduli di configurazione e gli elenchi nel back office vengono renderizzati utilizzando i template predefiniti di `ModuleAdminController` di PrestaShop. Le modifiche al front-office sono gestite filtrando l'elenco dei corrieri direttamente in PHP, non tramite il rendering di nuovi template.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - `ps_cbpr`: Questa tabella memorizza le regole di disponibilità dei corrieri.

    - `id_cbpr` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
    - `id_carrier` INT(10) UNSIGNED NOT NULL
    - `order_from` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
    - `order_to` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
    - `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
    - PRIMARY KEY (`id_cbpr`)
    - KEY `id_carrier` (`id_carrier`)
  - `ps_configuration`: Il modulo memorizza le sue impostazioni generali (come `mypresta_updates`, `update_`, `updatev_`) nella tabella `ps_configuration`.
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un AdminController viene inizializzato e i suoi media (JS/CSS) vengono impostati. | Utilizzato dal modulo per registrare il suo AdminController personalizzato (`AdminCbprController`) nella struttura del menu di PrestaShop. |
| `actionFilterDeliveryOptionList` | Eseguito durante il processo di checkout, in particolare quando PrestaShop sta costruendo l'elenco delle opzioni di consegna disponibili. | Questo è l'hook front-office principale. Il modulo lo utilizza per iterare attraverso l'elenco dei corrieri che PrestaShop ha già ritenuto disponibili (in base a zone, peso, prezzo) e quindi filtra ulteriormente questo elenco in base al valore totale del carrello e alle regole definite in `ps_cbpr`. Se la regola di un corriere non corrisponde al valore corrente del carrello, viene rimosso dall'elenco presentato al cliente. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Disponibilità corriere per valore carrello", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire il buon funzionamento e il miglioramento continuo dei nostri moduli.
