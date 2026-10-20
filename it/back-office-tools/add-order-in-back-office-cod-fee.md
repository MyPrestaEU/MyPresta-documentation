---
title: "Aggiungi ordine nel back office + commissione contrassegno - Manuale per il commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Aggiungi ordine nel back office + commissione contrassegno di MyPresta.eu."
sidebar:
  label: "Aggiungi ordine nel back office + commissione contrassegno - Manuale per il commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Add order in back office + cod fee su MyPresta.eu](https://mypresta.eu/modules/administration-tools/add-order-in-back-office-cod-fee.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/add-order-in-back-office-cod-fee/)
>
> ---


# Aggiungi ordine nel back office + commissione contrassegno

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).
- **Modulo prerequisito**: Questo modulo richiede che un modulo di pagamento "Contrassegno con commissione" sia installato e configurato nel tuo negozio. Questo modulo *estende* la funzionalità di tale modulo di pagamento all'interno del Back Office.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo modulo ha una pagina di configurazione molto semplice. La sua funzione principale è abilitare o disabilitare la funzionalità principale del modulo.

**Accesso:** Back Office > Moduli > Gestione moduli > Cerca "Aggiungi ordine nel back office + commissione contrassegno" > Clicca su "Configura"

#### **Abilita / Disabilita la funzionalità del modulo**

-   **Cosa fa questa impostazione:** Questo è un interruttore standard che controlla se la funzionalità del modulo è attiva o inattiva. Quando abilitato, il modulo aggiungerà automaticamente le commissioni di contrassegno agli ordini creati manualmente nel Back Office. Quando disabilitato, questa funzionalità cesserà.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo monitorerà attivamente il processo di creazione degli ordini nel Back Office. Se selezioni un metodo di pagamento "Contrassegno con commissione" durante la creazione di un ordine, la commissione associata verrà automaticamente calcolata e aggiunta al totale dell'ordine.
    -   *Quando disabilitato (NO):* Il modulo non interferirà con il processo di creazione degli ordini nel Back Office. Se selezioni un metodo di pagamento "Contrassegno con commissione", la commissione *non* verrà aggiunta automaticamente, e dovrai regolare manualmente il totale dell'ordine se desideri includerla.
-   **Valore consigliato:** **SÌ**. Per beneficiare dello scopo principale del modulo di automatizzare l'inclusione della commissione di contrassegno, dovrebbe essere abilitato.
-   **Scenario / esempio del commerciante:** Stai prendendo un ordine telefonico da un cliente che desidera pagare in contrassegno. Vai su Back Office > Ordini > Aggiungi nuovo ordine. Dopo aver aggiunto i prodotti e selezionato il cliente, scegli il tuo metodo di pagamento "Contrassegno con commissione". Se questo modulo è abilitato, la commissione di contrassegno apparirà immediatamente nel riepilogo dell'ordine, assicurando che al cliente venga addebitato l'importo corretto. Se disabilitato, la commissione mancherebbe, portando potenzialmente a un totale d'ordine errato.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita / Disabilita modulo | SÌ | Controlla se il modulo aggiunge automaticamente le commissioni di contrassegno agli ordini creati manualmente nel Back Office. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma la commissione di contrassegno non appare quando creo un ordine nel Back Office.**
R:

1.  **Controlla lo stato del modulo:** Vai su Moduli > Gestione moduli e assicurati che "Aggiungi ordine nel back office + commissione contrassegno" sia installato e **abilitato**.
2.  **Controlla il prerequisito:** Questo modulo *richiede* che un modulo di pagamento "Contrassegno con commissione" separato sia installato e configurato. Assicurati di avere un tale modulo e che sia configurato correttamente con le sue commissioni. Questo modulo *estende* tale funzionalità, non fornisce il meccanismo della commissione di contrassegno stesso.
3.  **Svuota la cache:** A volte la cache di PrestaShop può impedire che le nuove funzionalità del modulo appaiano immediatamente. Vai su Parametri avanzati > Prestazioni e clicca su "Svuota la cache" in alto a destra.
4.  **Verifica il metodo di pagamento:** Assicurati di selezionare il metodo di pagamento *specifico* "Contrassegno con commissione" fornito dal tuo altro modulo, non un'opzione generica "Contrassegno" senza commissione.

**D: Questo modulo influenzerà gli ordini effettuati dai clienti sul front-office del mio negozio?**
R: No, questo modulo influisce solo sul processo di creazione degli ordini *manualmente* nel Back Office di PrestaShop. Non altera il modo in cui i clienti effettuano ordini o come vengono calcolate le commissioni nel processo di checkout del front-end.

**D: Cosa succede se ho più moduli "Contrassegno con commissione"?**
R: Questo modulo è progettato per integrarsi con il modo standard in cui PrestaShop gestisce i moduli di pagamento e le loro commissioni associate. Dovrebbe funzionare con qualsiasi modulo "Contrassegno con commissione" che registra correttamente il calcolo della sua commissione all'interno del framework di pagamento di PrestaShop. Se riscontri problemi, contatta il supporto MyPresta.eu.

**D: Questo modulo crea l'opzione di pagamento "Contrassegno con commissione" stessa?**
R: No, non lo fa. Questo modulo è un *miglioramento* per un modulo di pagamento "Contrassegno con commissione" esistente. Devi avere un modulo di pagamento separato installato che fornisce il metodo di pagamento in contrassegno effettivo e la sua configurazione della commissione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Aggiungi ordine nel back office + commissione contrassegno" è un modulo PrestaShop leggero progettato principalmente per estendere la funzionalità di `AdminOrdersController`. Raggiunge il suo scopo agganciandosi ad azioni specifiche all'interno del processo di creazione degli ordini nel Back Office, in particolare quando viene selezionato o aggiornato un metodo di pagamento. La sua logica principale risiede nel file principale del modulo, sfruttando il sistema di hook di PrestaShop per modificare il comportamento esistente senza modifiche dirette ai file core. Si basa sulla presenza di un modulo di pagamento "Contrassegno con commissione" separato per fornire la logica effettiva di calcolo della commissione.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller Front-Office o Back-Office personalizzato. La sua funzionalità viene iniettata nell'esistente `AdminOrdersController` tramite hook.

### 4.3 Classi e modelli core (`classes/`)

Questo modulo non definisce classi personalizzate o istanze di `ObjectModel`. Tutta la logica è contenuta nel file principale del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. La funzionalità è gestita lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non include alcun file di template Smarty personalizzato. La sua configurazione è gestita dal metodo standard `getContent()`, che tipicamente utilizza i moduli helper di PrestaShop.

### 4.7 Schema del database e mappa degli hook

**Tabelle del database**:
Questo modulo non crea tabelle di database personalizzate. Memorizza la sua configurazione (ad esempio, stato di abilitazione/disabilitazione) nella tabella standard `ps_configuration`, utilizzando una chiave come `ADDORDERINBACKOFFICECODFEE_ENABLED`.

**Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Admin Controller imposta le sue risorse multimediali. | Usato per iniettare potenzialmente JS/CSS se necessario, anche se questo modulo non lo usa per questo. È un hook comune per le modifiche lato amministratore. |
| `actionAdminOrdersControllerSaveAfter` | Eseguito dopo che un ordine viene salvato in `AdminOrdersController`. | Questo è l'hook principale utilizzato dal modulo. Permette al modulo di ispezionare l'ordine appena salvato, controllare il metodo di pagamento selezionato e, se è un contrassegno con commissione, applicare la commissione. |
| `displayAdminOrder` | Eseguito sulla pagina dei dettagli dell'ordine nel Back Office. | Potrebbe essere utilizzato per visualizzare informazioni aggiuntive relative alla commissione di contrassegno nella vista dell'ordine, anche se la funzione principale del modulo è *aggiungere* la commissione, non solo visualizzarla. |

**Logica chiave all'interno di `add-order-in-back-office-cod-fee.php`:**

La funzionalità principale del modulo è probabilmente implementata all'interno del metodo `hookActionAdminOrdersControllerSaveAfter`. Questo metodo dovrebbe:

1.  Recuperare l'oggetto `Order` appena salvato.
2.  Identificare il `PaymentModule` utilizzato per l'ordine.
3.  Verificare se il modulo di pagamento selezionato è di tipo "Contrassegno con commissione" (questo tipicamente comporta il controllo del nome del modulo o di una proprietà/metodo specifico che espone).
4.  In tal caso, richiamerebbe un metodo su quel modulo di pagamento (o calcolerebbe direttamente in base alla sua configurazione) per ottenere la commissione di contrassegno.
5.  Infine, aggiornerebbe il totale dell'ordine, aggiungerebbe un nuovo dettaglio `OrderInvoice` (o modificherebbe uno esistente) per riflettere la commissione di contrassegno e persisterebbe queste modifiche nel database. Ciò potrebbe comportare la creazione di una nuova voce `OrderPayment` o la regolazione dei campi `total_paid_tax_incl` e `total_paid_tax_excl` dell'oggetto `Order`.

Gli sviluppatori dovrebbero essere consapevoli che questo modulo si basa fortemente sulla struttura interna e sul comportamento del modulo di pagamento "Contrassegno con commissione" con cui sta interagendo. Qualsiasi modulo di pagamento in contrassegno personalizzato potrebbe richiedere aggiustamenti o controlli di compatibilità specifici.

## 5. Supporto ufficiale e aggiornamenti

Per supporto ufficiale, aggiornamenti e ulteriori informazioni relative al modulo "Aggiungi ordine nel back office + commissione contrassegno", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/) o contatta direttamente il supporto MyPresta.eu.
