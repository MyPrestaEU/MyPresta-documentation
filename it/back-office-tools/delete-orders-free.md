---
title: "Delete Orders Free - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Delete Orders Free di MyPresta.eu."
sidebar:
  label: "Delete Orders Free - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Delete Orders Free su MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/delete-orders-free/)
>
> ---


# Delete Orders Free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito abilitate per impostazione predefinita nella maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina di configurazione principale del modulo. Questa pagina gestisce principalmente le notifiche di aggiornamento per il modulo stesso.

-   **Cosa fa questa impostazione:** Questa sezione gestisce la capacità del modulo di controllare gli aggiornamenti e visualizzare le notifiche.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo controllerà periodicamente MyPresta.eu per versioni più recenti. Se è disponibile un aggiornamento, potrebbe apparire una notifica nel tuo back office di PrestaShop, invitandoti a scaricare e installare l'ultima versione. Ciò garantisce che tu abbia sempre la versione più sicura e ricca di funzionalità del modulo.
    -   *Quando disabilitato:* Il modulo non controllerà automaticamente gli aggiornamenti. Dovresti visitare manualmente MyPresta.eu per verificare la presenza di nuove versioni. Sebbene ciò possa ridurre leggermente le richieste al server, significa che potresti perdere importanti aggiornamenti o correzioni di bug.
-   **Valore consigliato:** **Abilitato (SÌ)**. Mantenere questa opzione abilitata ti assicura di essere sempre informato sugli ultimi miglioramenti e patch di sicurezza per il modulo.
-   **Scenario/esempio del commerciante:** Vuoi essere avvisato se viene rilasciata una nuova versione di "Delete Orders Free" che corregge un bug o aggiunge una nuova funzionalità. Mantenere questa opzione abilitata ti assicura di vedere una notifica nel tuo pannello di amministrazione di PrestaShop.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Scheda Elimina Ordini (Back Office > Ordini > Elimina Ordini)

Questa è l'interfaccia principale per la funzionalità del modulo.

-   **Nome schermata e posizione nel menu:** Puoi accedere a questa schermata navigando su **Ordini > Elimina Ordini** nel menu del tuo back office di PrestaShop.
-   **Azioni e impostazioni disponibili:**
    -   Entrando in questa scheda, vedrai un elenco di tutti gli ordini nel tuo negozio PrestaShop, simile all'elenco standard "Ordini".
    -   Ogni ordine nell'elenco avrà un pulsante o un'icona **"Elimina"** dedicato (spesso un'icona a forma di cestino) accanto ad esso.
    -   **Eliminazione di un ordine:** Cliccando sul pulsante "Elimina" accanto a qualsiasi ordine, questo verrà rimosso immediatamente e permanentemente dal tuo database. Questa azione è irreversibile.
-   **Effetto delle modifiche:**
    -   Quando clicchi su "Elimina" per un ordine, il record dell'ordine, insieme a tutti i dati associati (come i dettagli dell'ordine, i messaggi del cliente relativi a quell'ordine, le fatture e potenzialmente i movimenti di magazzino se lo stato dell'ordine era configurato per influenzare il magazzino) verranno rimossi dal tuo database PrestaShop.
    -   L'ordine non apparirà più nella tua lista "Ordini", né sarà incluso in alcun rapporto di vendita o statistica.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Rivedi regolarmente la tua lista "Ordini" per ordini di prova, ordini fraudolenti o ordini che sono stati completamente annullati e non devono più essere tracciati.
    2.  Naviga su **Ordini > Elimina Ordini**.
    3.  Identifica attentamente gli ordini che desideri rimuovere.
    4.  Clicca sul pulsante "Elimina" accanto a ogni ordine specifico che desideri rimuovere.
    5.  Conferma l'eliminazione se richiesto.
    6.  **Importante:** Esercita estrema cautela poiché questa azione è permanente e non può essere annullata. Si consiglia vivamente di eseguire un backup del database prima di eliminare un gran numero di ordini.

#### 2.2.2 Index.php (deleteordersfree/controllers/admin/index.php)

Questo file è un segnaposto standard del controller PrestaShop e in genere non presenta una schermata diretta e configurabile al commerciante. Il suo scopo è solitamente quello di reindirizzare alla configurazione principale del modulo o a una specifica scheda di amministrazione. Nel contesto di questo modulo, probabilmente assicura che la navigazione al percorso di amministrazione di base del modulo ti indirizzi correttamente al controller `deleteorderstab`.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Controllo aggiornamenti (mypresta\_updates) | Abilitato (SÌ) | Controlla se il modulo verifica la presenza di nuove versioni e ti avvisa. Mantieni abilitato per gli aggiornamenti. |
| **Ordini > Elimina Ordini** | Pulsante Elimina (per ordine) | N/A | Rimuove permanentemente un ordine selezionato e i suoi dati associati dal database. **Azione irreversibile.** |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho eliminato un ordine per errore! Posso recuperarlo?**
R: Purtroppo no. Il modulo "Delete Orders Free" esegue un'eliminazione permanente. Questo è il motivo per cui sottolineiamo la cautela. Avere sempre un backup recente del tuo database, specialmente prima di eseguire eliminazioni in blocco. Se hai un backup, potresti essere in grado di ripristinare l'intero database a uno stato precedente, ma ciò annullerebbe anche tutte le altre modifiche apportate dal backup.

**D: Non vedo la scheda "Elimina Ordini" sotto il menu "Ordini".**
R:

1.  **Verifica l'installazione del modulo:** Vai su **Moduli > Gestione moduli** e cerca "Delete Orders Free". Assicurati che sia installato e abilitato.
2.  **Svuota la cache:** A volte, la cache del menu di PrestaShop deve essere aggiornata. Vai su **Parametri Avanzati > Prestazioni**, scorri fino a "Svuota la cache" e clicca su "Svuota la cache".
3.  **Verifica i permessi:** Assicurati che il tuo profilo utente abbia i permessi necessari per accedere e gestire moduli e ordini. Vai su **Parametri Avanzati > Team > Profili**, seleziona il tuo profilo, quindi vai su **Permessi > Moduli** e **Permessi > Ordini** per verificare.

**D: L'eliminazione di un ordine rimborserà anche il cliente o annullerà il pagamento?**
R: No. Questo modulo rimuove solo il record dell'ordine dal tuo database PrestaShop. NON interagisce con i gateway di pagamento (come PayPal, Stripe, ecc.) per emettere rimborsi o annullare transazioni. Devi gestire eventuali storni di pagamento o rimborsi direttamente tramite l'interfaccia del tuo gateway di pagamento.

**D: L'eliminazione di un ordine influisce sullo stock del prodotto?**
R: Se la tua configurazione PrestaShop per gli stati degli ordini è impostata per decrementare lo stock quando viene effettuato un ordine, e tu elimini un ordine, lo stock NON verrà automaticamente ri-incrementato. Dovresti regolare manualmente lo stock per i prodotti interessati se desideri rimetterli in inventario. Questo è un punto critico da ricordare per la gestione dell'inventario.

**D: Il modulo è installato, ma non vedo alcun pulsante "Elimina" nell'elenco degli ordini.**
R: Assicurati di essere nella scheda dedicata **Ordini > Elimina Ordini**, non nell'elenco standard **Ordini > Ordini**. La funzionalità di eliminazione è specificamente aggiunta alla scheda personalizzata del modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Delete Orders Free" è un modulo PrestaShop semplice, focalizzato principalmente sull'estensione della funzionalità del Back Office. Segue un modello MVC standard di PrestaShop per la sua interfaccia amministrativa. La logica centrale risiede nel file principale del modulo per l'installazione/disinstallazione e in un AdminController dedicato per la gestione del processo di eliminazione degli ordini. Non introduce nuove tabelle di database o interazioni complesse nel front-office.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Questo modulo non ha presenza nel front-office.
-   **Controller Admin Back-Office**:

    -   `deleteordersfree/controllers/admin/deleteorderstab.php`
        -   **Nome classe e classe genitore**: `DeleteOrdersTabController` estende `ModuleAdminController`.
        -   **Responsabilità**: Questo è il controller principale per la funzionalità del modulo. Rende l'elenco degli ordini nel Back Office, fornendo l'azione "Elimina" per ogni ordine. Gestisce la logica per la ricezione della richiesta di eliminazione (ad esempio, tramite parametro GET o invio POST) e quindi esegue l'eliminazione del database per l'ID ordine specificato. Questo controller probabilmente sovrascrive o estende i metodi di `AdminController` per visualizzare l'elenco degli ordini e aggiungere l'azione personalizzata.
    -   `deleteordersfree/controllers/admin/index.php`
        -   **Nome classe e classe genitore**: Questo è tipicamente un file segnaposto che assicura un routing corretto all'interno della sezione amministrativa. Di solito contiene un semplice reindirizzamento `header('Location: ...')` o un file vuoto per prevenire l'elenco delle directory. In PrestaShop, i file `index.php` nelle sottodirectory di `controllers/admin` sono spesso usati per definire il punto di ingresso per una sezione specifica o per prevenire l'accesso diretto. Per questo modulo, probabilmente assicura che l'accesso al percorso base `admin/deleteordersfree` indirizzi correttamente al controller `deleteorderstab`.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce classi personalizzate o definizioni di `ObjectModel`. Interagisce direttamente con le classi `Order` e `ObjectModel` correlate di PrestaShop (ad esempio, `OrderInvoice`, `OrderPayment`, `OrderHistory`, `Message`, `Cart`, `CustomerThread`, `SpecificPrice`, `StockAvailable`) per eseguire le eliminazioni.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è incluso in questo modulo. L'azione di eliminazione è probabilmente gestita tramite un invio di modulo standard o una semplice richiesta GET con una richiesta di conferma.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è incluso in questo modulo. Il modulo si basa sullo stile predefinito del Back Office di PrestaShop per la sua interfaccia.

### 4.6 Struttura del template Smarty (`views/templates/`)

Nessun file di template Smarty personalizzato è esplicitamente elencato nell'inventario del modulo. Il controller `deleteorderstab` probabilmente utilizza i template predefiniti di PrestaShop `list.tpl` o simili per il rendering della griglia degli ordini, iniettando l'azione "Elimina" tramite la logica del controller (ad esempio, il metodo `renderList()`).

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Questo modulo non crea nuove tabelle di database personalizzate. Opera direttamente sulle tabelle core esistenti di PrestaShop relative agli ordini, come:

    -   `ps_orders`
    -   `ps_order_detail`
    -   `ps_order_history`
    -   `ps_order_invoice`
    -   `ps_order_payment`
    -   `ps_message` (per i messaggi relativi all'ordine)
    -   `ps_cart` (il carrello associato all'ordine)
    -   `ps_customer_thread` (thread del servizio clienti relativi all'ordine)
    -   `ps_specific_price` (se sono stati applicati prezzi specifici tramite l'ordine)
    -   `ps_stock_available` (se lo stock è stato decrementato dall'ordine)
    -   E potenzialmente altre tabelle correlate (ad esempio, `ps_order_carrier`, `ps_order_slip`).
        Memorizza anche le sue impostazioni di configurazione (come `mypresta_updates`) nella tabella `ps_configuration`.
-   **Tabella degli hook registrati**:
    La descrizione del modulo menziona "Hook Front-Office: Header, Colonne, Prodotto o Footer" ma la funzionalità del modulo è puramente back-office. Ciò suggerisce che questi hook non sono attivamente utilizzati dalla logica centrale del modulo o sono residui di un template di modulo generico. Basandosi sullo scopo dichiarato del modulo e sull'inventario dei file, è altamente improbabile che renda qualcosa in questi hook del front-office.

    L'uso principale degli hook per questo modulo è probabilmente:

    | Nome Hook | Tempo di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `actionAdminControllerSetMedia` | Eseguito quando un AdminController viene inizializzato e prima che il suo contenuto venga reso. | Potenzialmente utilizzato per aggiungere JS/CSS personalizzati (anche se nessuno è elencato) o per registrare risorse specifiche del modulo per la pagina di amministrazione. |
    | `displayBackOfficeHeader` | Eseguito nell'intestazione di ogni pagina del Back Office. | Potrebbe essere utilizzato per notifiche di aggiornamento o per iniettare script/stili minori specifici dell'amministrazione. |
    | `actionModuleInstall` | Eseguito quando il modulo viene installato. | Crea la scheda "Elimina Ordini" nel menu del Back Office e imposta i valori di configurazione predefiniti. |
    | `actionModuleUninstall` | Eseguito quando il modulo viene disinstallato. | Rimuove la scheda "Elimina Ordini" e pulisce i valori di configurazione. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Delete Orders Free", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda relativa alla funzionalità del modulo.
"""
