---
title: "Modifica numero fattura - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Modifica numero fattura' di MyPresta.eu."
sidebar:
  label: "Modifica numero fattura - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Invoice number change su MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-number-change.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/invoice-number-change/)
>
> ---


# Modifica numero fattura

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, vai su **Moduli > Gestione moduli** e cerca "Modifica numero fattura". Clicca sul pulsante "Configura".

Questo modulo non ha una schermata di configurazione separata con più impostazioni. La sua funzionalità è integrata direttamente nella pagina dei dettagli dell'ordine nel tuo Back Office. Il pulsante "Configura" si limiterà a confermare che il modulo è installato e pronto per l'uso.

La funzionalità principale di questo modulo è aggiungere un nuovo campo o modificare una visualizzazione esistente nella pagina dei dettagli dell'ordine, consentendoti di modificare direttamente il numero della fattura.

**Come usare il modulo:**

1. **Naviga a un ordine:** Nel tuo Back Office PrestaShop, vai su **Ordini > Ordini**.
2. **Seleziona un ordine:** Clicca su qualsiasi ordine per visualizzarne i dettagli.
3. **Individua la sezione Fattura:** Scorri la pagina dei dettagli dell'ordine fino a trovare la sezione "Documenti" o "Fatture".
4. **Modifica il numero della fattura:** Ora vedrai un campo modificabile o un pulsante accanto al numero della fattura che ti consente di modificarlo.
   - **Cosa fa questa impostazione:** Questa funzione ti consente di digitare direttamente un nuovo numero di fattura per una fattura specifica associata all'ordine corrente.
   - **Effetto della modifica di questa impostazione:**
     - *Quando inserisci un nuovo numero e salvi:* Il numero della fattura per quella specifica fattura dell'ordine verrà aggiornato nel tuo database e riflesso sul documento di fattura stesso (se rigenerato o visualizzato). Questa modifica è permanente e influisce sui tuoi registri finanziari.
   - **Valore consigliato:** Modifica i numeri di fattura solo quando assolutamente necessario e controlla sempre l'accuratezza. Assicurati che il nuovo numero segua il tuo schema di numerazione interno o i requisiti legali.
   - **Scenario / esempio del commerciante:** Un ordine è stato inizialmente fatturato come INV00123. A causa di una migrazione di dati, hai bisogno che questa fattura sia INV2024-005. Navigheresti all'ordine, troveresti INV00123, cliccheresti per modificare, inseriresti INV2024-005 e salveresti.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina Dettagli Ordine (sezione Documenti/Fatture) | Numero Fattura (campo modificabile) | N/A (dipende dalla fattura esistente) | Consente la modifica diretta di un numero di fattura per un ordine specifico. Cruciale per correzioni, conformità o integrazione con sistemi esterni. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho installato il modulo, ma non vedo alcuna nuova pagina di impostazioni. Funziona?**
R1: Sì, il modulo funziona come previsto. Questo modulo non aggiunge una pagina di configurazione separata. La sua funzionalità è integrata direttamente nella pagina dei dettagli dell'ordine. Vai su **Ordini > Ordini**, seleziona un ordine e dovresti trovare un campo modificabile o un'opzione per modificare il numero della fattura all'interno della sezione "Documenti" o "Fatture".

**D2: Ho cambiato un numero di fattura, ma il vecchio numero appare ancora sulla fattura PDF.**
R2: Dopo aver cambiato il numero della fattura nel Back Office, potrebbe essere necessario rigenerare la fattura PDF per quell'ordine per riflettere il nuovo numero. PrestaShop spesso memorizza nella cache il contenuto PDF. Scarica nuovamente la fattura dalla pagina dei dettagli dell'ordine e dovrebbe visualizzare il numero aggiornato.

**D3: Posso annullare una modifica del numero di fattura?**
R3: Il modulo ti consente di cambiare il numero a qualsiasi cosa tu desideri. Se hai bisogno di annullare, dovresti semplicemente modificare nuovamente il campo e inserire il numero originale (se lo ricordi o lo hai registrato). Il modulo non tiene una cronologia delle modifiche, quindi si consiglia un'attenta registrazione da parte tua.

**D4: La modifica di un numero di fattura influirà sui miei rapporti contabili in PrestaShop?**
R4: Sì, la modifica di un numero di fattura aggiornerà il campo `invoice_number` nel tuo database per quella specifica fattura. Qualsiasi rapporto PrestaShop che estrae i numeri di fattura direttamente dal database rifletterà il nuovo numero. Assicurati che le tue modifiche siano coerenti con le tue pratiche contabili.

**D5: Il modulo non sembra essere attivo sul mio tema personalizzato. Cosa devo fare?**
R5: Questo modulo utilizza il sistema di override di PrestaShop per modificare il comportamento principale e si aggancia ai modelli di amministrazione standard. Dovrebbe funzionare con la maggior parte dei temi personalizzati senza problemi, poiché influisce solo sul Back Office. Se riscontri problemi, prima svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**). Se il problema persiste, potrebbe essere un conflitto con un altro modulo o un modello di amministrazione altamente personalizzato. Contatta il supporto MyPresta.eu con i dettagli del tuo tema e di eventuali altri moduli pertinenti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Modifica numero fattura" (`invoicenb`) è progettato per estendere la funzionalità di gestione delle fatture di base di PrestaShop senza alterare lo schema del database. Ciò si ottiene principalmente tramite un `override` della classe `OrderInvoice` e agganciandosi alla pagina dei dettagli dell'ordine del Back Office per fornire un'interfaccia modificabile per il numero della fattura. Questo approccio garantisce un impatto minimo sul sistema principale fornendo la funzionalità desiderata.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Tutte le funzionalità sono integrate tramite il file del modulo principale, gli override e gli hook del template.

### 4.3 Classi e modelli principali (`classes/`)

- **`invoicenb/override/classes/order/OrderInvoice.php`**
  - **Nome classe**: `OrderInvoice` (sovrascrive la classe `OrderInvoice` principale)
  - **Classe genitore**: `OrderInvoiceCore`
  - **Responsabilità**: Questo override è il cuore della funzionalità del modulo. Modifica il comportamento della classe `OrderInvoice`, in particolare il modo in cui i numeri di fattura vengono gestiti e potenzialmente salvati. L'override è responsabile di consentire l'aggiornamento del numero di fattura dal Back Office. Probabilmente aggiunge o modifica un metodo per facilitare il salvataggio di un nuovo numero di fattura quando inviato tramite l'interfaccia di amministrazione.
  - **Tabella del database**: `ps_order_invoice` (o il prefisso della tua tabella)
  - **Campi `$definition`**: Questo override funziona con la `$definition` esistente di `OrderInvoiceCore`, in particolare il campo `number`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. La funzionalità di modifica interattiva è gestita direttamente all'interno dei template Smarty e potenzialmente tramite meccanismi AJAX standard di PrestaShop se è coinvolta una sottomissione di modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Lo stile per il campo modificabile o il pulsante nella pagina dell'ordine si baserà sul CSS predefinito del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo utilizza i template per iniettare il campo modificabile del numero di fattura nella pagina dei dettagli dell'ordine del Back Office.

- **Template hook (`views/templates/hook/`)**:
  - **`invoicenb/views/templates/hook/displayAdminOrder16.tpl`**
    - **Hook**: `displayAdminOrder` (per PrestaShop 1.6.x)
    - **Scopo**: Questo template viene renderizzato nella pagina dei dettagli dell'ordine in PrestaShop 1.6.x. Inietta gli elementi del modulo HTML (ad esempio, un campo di input e un pulsante di salvataggio) che consentono all'amministratore di visualizzare e modificare il numero di fattura per un ordine specifico. Probabilmente include la logica per visualizzare il numero di fattura corrente e gestire l'invio di uno nuovo.
  - **`invoicenb/views/templates/hook/displayAdminOrder17.tpl`**
    - **Hook**: `displayAdminOrder` (per PrestaShop 1.7.x, 8.x, 9.x)
    - **Scopo**: Simile a `displayAdminOrder16.tpl`, ma adattato per la struttura del template e potenzialmente diversi parametri hook di PrestaShop 1.7.x e versioni più recenti. Fornisce la stessa funzionalità: visualizzare un campo modificabile del numero di fattura nella pagina dei dettagli dell'ordine.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea nuove tabelle di database personalizzate. Interagisce con la tabella `ps_order_invoice` esistente (o il prefisso della tua tabella) per aggiornare la colonna `number`.
  - I record di configurazione sono archiviati in `ps_configuration` per le impostazioni interne del modulo (se presenti, anche se questo modulo sembra avere impostazioni esplicite minime).
- **Tabella degli hook registrati**:

  | Nome Hook | Tempo di esecuzione | Scopo tecnico |
  | --- | --- | --- |
  | `displayAdminOrder` | Renderizza il contenuto nella pagina dei dettagli dell'ordine del Back Office. | Utilizzato per iniettare il modulo HTML per la modifica del numero di fattura direttamente nella vista dell'ordine. Il modulo fornisce template separati per PrestaShop 1.6 e 1.7+ per questo hook. |
  | `actionObjectOrderInvoiceUpdateAfter` | Eseguito dopo l'aggiornamento di un oggetto `OrderInvoice`. | (Implicito, se l'override lo usa) Potrebbe essere utilizzato per attivare azioni aggiuntive o la registrazione dopo che un numero di fattura è stato modificato con successo. |
  | `actionObjectOrderInvoiceAddAfter` | Eseguito dopo l'aggiunta di un oggetto `OrderInvoice`. | (Implicito, se l'override lo usa) Potrebbe essere utilizzato per modificare il numero di fattura iniziale al momento della creazione, anche se l'obiettivo principale è la modifica di quelli esistenti. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Modifica numero fattura", fai riferimento al tuo account cliente MyPresta.eu. Puoi scaricare le versioni più recenti dalla cronologia degli ordini e accedere ai nostri canali di supporto dedicati per qualsiasi assistenza tecnica o richiesta.
