---
title: "Modifica data fattura - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Modifica data fattura' di MyPresta.eu."
sidebar:
  label: "Modifica data fattura - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Invoice date change su MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-date-change.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/invoice-date-change/)
>
> ---


# Modifica data fattura

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Modifica data fattura". Questo ti porterà alla schermata di configurazione principale.

In questa schermata, troverai la funzionalità principale del modulo, che ti consente di impostare la data di fattura desiderata per un ordine.

**Come usarlo:**

1. **Naviga a un ordine:**
   - Vai su **Ordini > Ordini** nel tuo Back Office di PrestaShop.
   - Clicca su un ordine esistente per visualizzarne i dettagli.
2. **Individua la sezione Data fattura:**
   - Nella pagina dei dettagli dell'ordine, scorri verso il basso. Troverai una nuova sezione o blocco relativo a "Modifica data fattura".
   - Questa sezione apparirà tipicamente all'interno del blocco "Documenti" o di un'area simile in cui vengono gestite le fatture.
3. **Seleziona la data desiderata:**
   - Vedrai un campo di selezione della data. Clicca su questo campo per aprire un calendario.
   - Scegli la data esatta che desideri appaia sulla fattura. Questa può essere una data passata o una data futura.
4. **Salva le modifiche:**
   - Dopo aver selezionato la data, ci sarà un pulsante "Salva" o "Aggiorna" all'interno di questa sezione. Cliccalo per applicare la nuova data di fattura all'ordine.
5. **Genera o rigenera la fattura:**
   - Una volta salvata la data, se generi una nuova fattura per questo ordine (o rigeneri una esistente), il PDF rifletterà la data che hai appena impostato.

**Cosa fa questa impostazione:** Questo modulo non ha un interruttore globale "on/off" o impostazioni complesse. La sua funzione principale è quella di inserire un selettore di data direttamente nelle pagine dei dettagli dell'ordine nel Back Office. Questo selettore di data ti consente di sovrascrivere manualmente la data di generazione predefinita della fattura per i singoli ordini.

**Effetto della modifica di questa impostazione:**

- *Quando selezioni una data e salvi:* La data scelta viene memorizzata per quell'ordine specifico. Qualsiasi fattura generata per questo ordine *dopo* aver impostato questa data utilizzerà la data selezionata invece della data di sistema corrente.
- *Quando non utilizzi il selettore di data del modulo:* PrestaShop continuerà a generare fatture con la data corrente, come fa per impostazione predefinita.

**Valore consigliato:** Utilizza il selettore di data per selezionare la data esatta richiesta per ogni fattura specifica. Non esiste un "valore consigliato" globale poiché la data varierà per ogni ordine.

**Scenario / esempio del commerciante:**
Immagina che un cliente abbia effettuato un ordine il 15 gennaio, ma a causa di un ritardo di magazzino, il prodotto è stato spedito e fatturato solo il 25 gennaio. Tuttavia, per scopi contabili, hai bisogno che la data della fattura rifletta la data originale dell'ordine del 15 gennaio.

1. Vai alla pagina dei dettagli dell'ordine per questo ordine specifico.
2. Nella sezione "Modifica data fattura", apri il calendario e seleziona il 15 gennaio.
3. Clicca su "Salva".
4. Ora, quando generi la fattura PDF per questo ordine, visualizzerà "15 gennaio" come data della fattura, anche se l'hai generata il 25 gennaio.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina Dettagli Ordine (Back Office) | Selettore data (all'interno della sezione "Modifica data fattura") | Varia per ordine | Consente la selezione manuale della data di emissione della fattura per un ordine specifico. La data selezionata apparirà sulla fattura PDF generata, sovrascrivendo la data corrente predefinita. |
| Pagina Dettagli Ordine (Back Office) | Pulsante Salva/Aggiorna | N/A | Applica la data di fattura selezionata all'ordine corrente. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho cambiato la data, ma la fattura mostra ancora la vecchia data. Cosa c'è che non va?**
R: Assicurati di aver cliccato il pulsante "Salva" o "Aggiorna" dopo aver selezionato la nuova data nella pagina dei dettagli dell'ordine. Inoltre, assicurati di generare una *nuova* fattura o di *rigenerare* quella esistente *dopo* aver salvato la nuova data. Se stai guardando un PDF già scaricato, non si aggiornerà magicamente. Devi scaricarlo di nuovo.

**D: Il selettore di data non compare nella mia pagina degli ordini.**
R:

1. **Verifica l'installazione del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Modifica data fattura" sia installato e abilitato.
2. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte PrestaShop ha bisogno di un aggiornamento della cache per visualizzare nuovi elementi del modulo.
3. **Compatibilità del tema:** Sebbene il modulo sia progettato per integrarsi perfettamente, temi molto personalizzati potrebbero occasionalmente interferire. Se svuotare la cache non aiuta, passa temporaneamente al tema PrestaShop predefinito per vedere se il selettore di data appare. Se lo fa, il tuo tema potrebbe richiedere una piccola modifica.

**D: Posso cambiare la data per più fatture contemporaneamente?**
R: No, questo modulo è progettato per modifiche individuali della data della fattura dell'ordine. Devi accedere alla pagina dei dettagli di ogni ordine per impostare la sua data di fattura specifica. Non esiste una funzione di modifica in blocco.

**D: Questo modulo influisce su altre date in PrestaShop, come la data dell'ordine o la data di pagamento?**
R: No, questo modulo *modifica solo* la data di emissione che appare sulla fattura PDF generata. Non altera la data di creazione dell'ordine, la data di pagamento o qualsiasi altra data associata all'ordine nel tuo database.

**D: Questo modulo funzionerà con il mio modello di fattura personalizzato?**
R: Sì, il modulo inserisce la data scelta nel processo di generazione della fattura standard di PrestaShop. Finché il tuo modello di fattura personalizzato utilizza correttamente le variabili standard per la data della fattura, dovrebbe visualizzare la data impostata dal modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Modifica data fattura" è un modulo PrestaShop leggero progettato principalmente per estendere la funzionalità di gestione degli ordini del Back Office. Sfrutta il sistema di hook di PrestaShop per inserire un campo di input data personalizzato nella pagina dei dettagli dell'ordine. Quando una nuova data viene selezionata e salvata, aggiorna il campo `invoice_date` dell'oggetto `OrderInvoice`, assicurando che le successive generazioni di fatture PDF riflettano la data definita dall'utente. Segue un approccio semplice e diretto senza complesse strutture MVC o tabelle di database personalizzate, basandosi sulle funzionalità core esistenti di PrestaShop.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Tutta la logica è gestita all'interno del file principale del modulo (`invoicedate/index.php`) e tramite il sistema di hook di PrestaShop.

### 4.3 Classi e modelli core (`classes/`)

Questo modulo non introduce alcuna classe o modello personalizzato nella directory `classes/`. Interagisce direttamente con l'oggetto `OrderInvoice` core e le sue proprietà.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è incluso in questo modulo. La funzionalità del selettore di data è tipicamente fornita dalle librerie JavaScript core di PrestaShop (ad esempio, jQuery UI Datepicker) che sono già caricate nel Back Office.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è incluso in questo modulo. Lo stile per il selettore di data e gli elementi circostanti si basa sul CSS predefinito del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza due template specifici per visualizzare il campo di input della data nella pagina dei dettagli dell'ordine, a seconda della versione di PrestaShop.

- **Template degli hook (`views/templates/hook/`)**:
  - `invoicedate/views/templates/hook/displayAdminOrder16.tpl`
    - **Hook**: Questo template viene renderizzato nell'hook `displayAdminOrder`, specificamente per le versioni PrestaShop 1.6.x.
    - **Scopo**: Genera la struttura HTML per il campo di input della data della fattura (un selettore di data) e un pulsante di invio all'interno della pagina dei dettagli dell'ordine nel Back Office di PrestaShop 1.6. Consente all'amministratore di selezionare e salvare una data di fattura personalizzata per l'ordine corrente.
  - `invoicedate/views/templates/hook/displayAdminOrder17.tpl`
    - **Hook**: Questo template viene renderizzato nell'hook `displayAdminOrder`, specificamente per le versioni PrestaShop 1.7.x e successive.
    - **Scopo**: Simile alla versione 1.6, questo template fornisce l'HTML per il campo di input della data della fattura e il pulsante di invio, adattato per le differenze strutturali e di stile della pagina degli ordini del Back Office di PrestaShop 1.7+.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:
  Questo modulo non crea nuove tabelle di database personalizzate. Modifica il campo `invoice_date` della tabella `ps_order_invoice` esistente (o `_order_invoice` a seconda del tuo prefisso) quando una data di fattura viene aggiornata tramite l'interfaccia del modulo.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayAdminOrder` | Eseguito nella pagina dei dettagli dell'ordine del Back Office di PrestaShop. | Questo hook viene utilizzato per inserire l'HTML personalizzato del modulo (il selettore di data e il pulsante di salvataggio) nella vista dei dettagli dell'ordine, consentendo al commerciante di interagire con l'impostazione della data della fattura. Il modulo utilizza template specifici per versione (`displayAdminOrder16.tpl` o `displayAdminOrder17.tpl`) per questo hook. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Modifica data fattura", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
