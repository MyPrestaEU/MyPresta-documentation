---
title: "Modifica numero nota di credito - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Modifica numero nota di credito' di MyPresta.eu."
sidebar:
  label: "Modifica numero nota di credito - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Credit slip number change su MyPresta.eu](https://mypresta.eu/modules/administration-tools/credit-slip-number-change.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/credit-slip-number-change/)
>
> ---


# Modifica numero nota di credito

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo modulo ha una pagina di configurazione molto semplice, principalmente per gli aggiornamenti interni di MyPresta.eu. La funzionalità principale di modifica dei numeri delle note di credito è accessibile direttamente dalla pagina dei dettagli dell'ordine.

- **Posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Modifica numero nota di credito" > Clicca su "Configura".

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio del commerciante |
| --- | --- | --- | --- | --- |
| **Aggiornamenti MyPresta.eu** | Questa impostazione controlla se il modulo verifica la presenza di aggiornamenti da MyPresta.eu. | *Quando abilitato:* Il modulo verificherà periodicamente la presenza di nuove versioni e ti avviserà nel back office. *Quando disabilitato:* Il modulo non verificherà automaticamente la presenza di aggiornamenti. | SÌ | Mantenere questa opzione abilitata ti assicura di essere sempre a conoscenza di nuove versioni, correzioni di bug e miglioramenti delle funzionalità per il modulo. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

La funzionalità principale di questo modulo è integrata direttamente nella **pagina dei dettagli dell'ordine** nel tuo back office PrestaShop. Non ci sono schermate di amministrazione dedicate separate.

- **Nome schermata e posizione del menu:** Back Office > Ordini > Ordini > Clicca su qualsiasi ordine per visualizzarne i dettagli.
- **Azioni e impostazioni disponibili:**
  - Nella pagina dei dettagli dell'ordine, scorri fino alla sezione "Note di credito".
  - Per ogni nota di credito elencata, vedrai un nuovo campo di input accanto al suo numero attuale.
  - Puoi digitare un nuovo numero in questo campo.
  - Dopo aver inserito il nuovo numero, clicca sul pulsante "Salva" (o icona simile, solitamente un floppy disk o un segno di spunta) accanto al campo di input per applicare la modifica.
- **Effetto delle modifiche:**
  - Quando modifichi un numero di nota di credito e lo salvi, il nuovo numero viene immediatamente aggiornato nel tuo database PrestaShop.
  - Questo nuovo numero sarà quindi riflesso sul PDF della nota di credito generato per quella specifica nota di credito. Sia tu che il tuo cliente vedrete il numero aggiornato sul documento.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Vai su **Ordini > Ordini** nel tuo back office PrestaShop.
  2. Seleziona l'ordine per il quale devi modificare un numero di nota di credito.
  3. Nella pagina dei dettagli dell'ordine, individua il blocco "Note di credito".
  4. Trova la specifica nota di credito che desideri modificare.
  5. Inserisci il nuovo numero desiderato nel campo di input fornito.
  6. Clicca sull'icona di salvataggio accanto al campo di input.
  7. Verifica la modifica scaricando il PDF della nota di credito; ora dovrebbe visualizzare il nuovo numero.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Aggiornamenti MyPresta.eu | SÌ | Controlla i controlli automatici degli aggiornamenti per il modulo. |
| Pagina Dettagli Ordine (sezione Note di Credito) | Campo di input Numero Nota di Credito | N/A (Definito dall'utente) | Consente la modifica diretta dei singoli numeri delle note di credito. Le modifiche si riflettono sul PDF. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho cambiato il numero della nota di credito, ma non compare sul PDF.**
R: Dopo aver cambiato il numero, assicurati di aver cliccato sul pulsante "Salva" accanto al campo di input. Quindi, rigenera o scarica nuovamente il PDF della nota di credito. Se ancora non compare, prova a svuotare la cache del tuo browser o la cache Smarty di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).

**D: Posso cambiare il numero di una nota di credito già convalidata o inviata?**
R: Sì, il modulo ti consente di cambiare il numero di qualsiasi nota di credito esistente. La modifica influenzerà solo il numero visualizzato sul PDF, non la transazione finanziaria sottostante.

**D: Esiste un modo per modificare in blocco i numeri delle note di credito?**
R: No, questo modulo è progettato per modifiche individuali dei numeri delle note di credito direttamente nella pagina dei dettagli dell'ordine. Non offre una funzione di modifica in blocco. Per operazioni in blocco, potrebbe essere necessario uno sviluppo personalizzato.

**D: Cosa succede se inserisco un numero di nota di credito duplicato?**
R: Il sistema principale di PrestaShop potrebbe non impedire numeri di nota di credito duplicati, poiché il modulo aggiorna direttamente il numero. È tua responsabilità garantire l'unicità se le tue pratiche contabili lo richiedono. Il modulo facilita la modifica ma non impone vincoli di unicità oltre il comportamento predefinito di PrestaShop.

**D: Il campo di input per cambiare il numero non compare nella mia pagina dell'ordine.**
R:

1. **Verifica l'installazione del modulo:** Assicurati che il modulo sia correttamente installato e abilitato in **Moduli > Gestione moduli**.
2. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache".
3. **Compatibilità del tema:** Sebbene il modulo utilizzi hook standard di PrestaShop, temi molto personalizzati potrebbero talvolta interferire. Se il problema persiste, passa temporaneamente al tema predefinito di PrestaShop per vedere se il campo appare. Se lo fa, il tuo tema potrebbe richiedere una piccola modifica.
4. **Versione di PrestaShop:** Assicurati di aver scaricato la versione corretta del modulo per la tua installazione di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Modifica numero nota di credito" (`creditnb`) è un modulo PrestaShop leggero che estende la funzionalità del back-office iniettando un campo di input personalizzato nell'hook `displayAdminOrder`. Ciò consente agli amministratori di modificare i numeri delle note di credito direttamente nella pagina dei dettagli dell'ordine. Il modulo interagisce principalmente con l'oggetto `OrderSlip` di PrestaShop e la sua tabella di database associata per aggiornare il campo `number`. Sfrutta la struttura standard del modulo PrestaShop e la templating.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Tutte le interazioni sono gestite tramite il file principale del modulo (`creditnb.php`) e i meccanismi AJAX standard di PrestaShop per l'invio di moduli all'interno della pagina dell'ordine amministrativo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce classi o modelli personalizzati nella directory `classes/`. Interagisce direttamente con l'oggetto `OrderSlip` nativo di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. La funzionalità per salvare il nuovo numero della nota di credito è gestita dall'invio del modulo all'interno del template dell'hook `displayAdminOrder`, probabilmente sfruttando l'AJAX o la gestione dei moduli esistenti di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Lo stile del campo di input dovrebbe ereditare dal tema del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template degli hook per iniettare la sua funzionalità nel back office di PrestaShop.

- **Template degli hook (`views/templates/hook/`)**:
  - `creditnb/views/templates/hook/displayAdminOrder16.tpl`
    - **Scopo:** Questo template è progettato per PrestaShop 1.6.x (sebbene il modulo elenchi la compatibilità con 1.7.x, 8.x, 9.x, questo file potrebbe essere un'inclusione legacy o per una compatibilità più ampia). Rende il campo di input e il pulsante di salvataggio per la modifica dei numeri delle note di credito all'interno della sezione "Note di credito" della pagina dei dettagli dell'ordine.
    - **Hook:** `displayAdminOrder`
    - **Output:** Un blocco HTML contenente un elemento form con un campo di input per il numero di ogni nota di credito e un meccanismo per salvare il valore aggiornato.
  - `creditnb/views/templates/hook/displayAdminOrder17.tpl`
    - **Scopo:** Questo template è progettato per PrestaShop 1.7.x, 8.x e 9.x. Rende il campo di input e il pulsante di salvataggio per la modifica dei numeri delle note di credito all'interno della sezione "Note di credito" della pagina dei dettagli dell'ordine, adattato per la nuova UI del back-office.
    - **Hook:** `displayAdminOrder`
    - **Output:** Un blocco HTML contenente un elemento form con un campo di input per il numero di ogni nota di credito e un meccanismo per salvare il valore aggiornato.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea nuove tabelle di database personalizzate.
  - Modifica la colonna `number` nella tabella `ps_order_slip` (o `_order_slip`), che fa parte dello schema del database principale di PrestaShop.
  - Le impostazioni di configurazione (`mypresta_updates`, `update_`, `updatev_`) sono memorizzate nella tabella `ps_configuration`.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayAdminOrder` | Rende il contenuto nella pagina dei dettagli dell'ordine del back-office di PrestaShop. | Inietta il campo di input personalizzato e il meccanismo di salvataggio per la modifica dei numeri delle note di credito direttamente nella sezione "Note di credito" della vista dell'ordine. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Modifica numero nota di credito", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire il buon funzionamento e il miglioramento continuo dei nostri moduli.
