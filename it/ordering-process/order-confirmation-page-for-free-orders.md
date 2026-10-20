---
title: "Pagina di conferma ordine per ordini gratuiti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Pagina di conferma ordine per ordini gratuiti' di MyPresta.eu."
sidebar:
  label: "Pagina di conferma ordine per ordini gratuiti - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Order confirmation page for free orders su MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-confirmation-page-for-free-orders.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/order-confirmation-page-for-free-orders/)
>
> ---


# Pagina di conferma ordine per ordini gratuiti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Pagina di conferma ordine per ordini gratuiti)

Questa è la schermata di configurazione principale e unica per il modulo. È semplice e ti consente di abilitare o disabilitare la funzionalità principale del modulo.

![Screenshot della configurazione del modulo Placeholder]

- **Attiva la pagina di conferma ordine**
  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo. Controlla se gli ordini gratuiti visualizzano la pagina di conferma standard o tornano al comportamento predefinito di PrestaShop (reindirizzamento alla cronologia ordini).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (selezionato "Abilitato"):* Tutti gli ordini, inclusi quelli con un totale di €0,00, visualizzeranno la pagina standard "Conferma ordine" dopo il checkout.
    - *Quando disabilitato (selezionato "Disabilitato"):* Gli ordini gratuiti torneranno al comportamento predefinito di PrestaShop, reindirizzando i clienti direttamente alla loro pagina di cronologia ordini invece di mostrare la pagina di conferma.
  - **Valore consigliato:** **Abilitato**. Questo è lo scopo principale del modulo e fornisce una migliore esperienza al cliente.
  - **Scenario / esempio del commerciante:** Se offri un e-book gratuito da scaricare, abilitando questa opzione i clienti vedranno una pagina di conferma con un link per il download, invece di essere confusi da un reindirizzamento diretto alla loro cronologia ordini. Se desideri temporaneamente tornare al comportamento predefinito di PrestaShop per gli ordini gratuiti (ad esempio, per test specifici), puoi disabilitarlo.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Attiva la pagina di conferma ordine | Abilitato | Controlla se gli ordini gratuiti visualizzano la pagina di conferma ordine standard (Abilitato) o reindirizzano alla cronologia ordini (Disabilitato). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei ordini gratuiti continuano a reindirizzare alla pagina della cronologia ordini, anche dopo aver abilitato il modulo. Cosa devo fare?**
R:

1. **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Pagina di conferma ordine per ordini gratuiti" sia installato e abilitato.
2. **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli > Configura** per questo modulo e assicurati che l'impostazione "Attiva la pagina di conferma ordine" sia impostata su **"Abilitato"**.
3. **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" nell'angolo in alto a destra. Questo è spesso necessario dopo le modifiche alla configurazione del modulo.
4. **Cache del browser:** Prova a svuotare la cache del tuo browser o a testare in una finestra di navigazione in incognito/privata per escludere problemi di caching locale.

**D: Questo modulo influenzerà i miei ordini a pagamento?**
R: No, questo modulo si rivolge specificamente al comportamento degli ordini con un totale di €0,00. Gli ordini a pagamento continueranno a visualizzare la pagina di conferma ordine standard come hanno sempre fatto.

**D: Questo modulo richiede modifiche speciali al tema?**
R: No, il modulo funziona sovrascrivendo un controller core di PrestaShop. Sfrutta il modello della pagina di conferma ordine del tuo tema esistente. Non sono richieste modifiche al tema. Se la tua pagina di conferma ordine appare bene per gli ordini a pagamento, apparirà bene anche per gli ordini gratuiti.

**D: E se volessi mostrare contenuti diversi sulla pagina di conferma per ordini gratuiti rispetto agli ordini a pagamento?**
R: Questo modulo assicura che venga visualizzata la *stessa* pagina di conferma. Per mostrare contenuti diversi, dovresti personalizzare il tuo template `order-confirmation.tpl` (solitamente trovato in `themes/your-theme/templates/checkout/`) per includere logica condizionale basata sul totale dell'ordine o sul metodo di pagamento. Questo richiederebbe l'assistenza di uno sviluppatore.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Pagina di conferma ordine per ordini gratuiti" raggiunge la sua funzionalità sovrascrivendo un controller front-office core di PrestaShop. In particolare, si rivolge a `OrderConfirmationController` per modificare la logica di reindirizzamento che si verifica dopo che un ordine gratuito è stato effettuato. Questo è un meccanismo di override standard di PrestaShop, che garantisce un impatto minimo sui file core e consente una facile disinstallazione.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:
  - `freeorderconfirmation/override/controllers/front/index.php`
    - Questo file è un segnaposto o un artefatto del processo di override. In PrestaShop 1.7+, gli override sono tipicamente gestiti posizionando la classe sovrascritta direttamente nella directory `override/classes` o `override/controllers`, e l'autoloader di PrestaShop gestisce il resto. Questo file `index.php` stesso non contiene una definizione di classe o una logica diretta per la funzionalità del modulo. La sua presenza assicura che il meccanismo di override sia correttamente attivato per `OrderConfirmationController`.
  - `freeorderconfirmation/override/controllers/front/OrderConfirmationController.php`
    - **Nome della classe e classe genitore**: `OrderConfirmationController` (sovrascrive la classe core `OrderConfirmationController`).
    - **Responsabilità**: Questo è il cuore della funzionalità del modulo. Sovrascrive il metodo `initContent()` (o logica simile all'interno del ciclo di vita del controller) dell'originale `OrderConfirmationController`. La logica originale di PrestaShop controlla se il totale dell'ordine è zero e, in tal caso, reindirizza il cliente alla sua cronologia ordini. Questo controller sovrascritto rimuove o modifica quel reindirizzamento condizionale, assicurando che il metodo `initContent()` del `OrderConfirmationController` standard (che renderizza la pagina di conferma) sia sempre eseguito, anche per gli ordini gratuiti. Impedisce efficacemente la chiamata a `Tools::redirect()` per gli ordini a valore zero.

### 4.3 Classi e Modelli Core (`classes/`)

Nessuna classe personalizzata o definizione di `ObjectModel` è presente in questo modulo. Il modulo opera puramente sovrascrivendo un controller core di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è incluso con questo modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è incluso con questo modulo. Il modulo si basa sullo stile esistente del tema per la pagina di conferma ordine.

### 4.6 Struttura del template Smarty (`views/templates/`)

Nessun file di template Smarty personalizzato è incluso con questo modulo. Il modulo assicura che il template di conferma ordine *standard* di PrestaShop (tipicamente `themes/your-theme/templates/checkout/order-confirmation.tpl`) venga renderizzato per gli ordini gratuiti, proprio come per gli ordini a pagamento.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle SQL personalizzate.
  - Memorizza le sue impostazioni di configurazione (es. `freeorderconfirmation_oc`) nella tabella `ps_configuration`.
  - Memorizza anche `mypresta_updates`, `update_`, `updatev_` per il tracciamento interno degli aggiornamenti da parte di MyPresta.eu.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin imposta i suoi media (CSS/JS). | Utilizzato dal modulo per includere potenzialmente le proprie risorse per la pagina di configurazione del back-office. Nel caso di questo modulo, è probabile che venga utilizzato per garantire che il modulo di configurazione del modulo sia correttamente renderizzato nell'interfaccia di amministrazione di PrestaShop, anche se non vengono caricate esplicitamente risorse personalizzate. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto tecnico, fare riferimento al proprio account cliente su MyPresta.eu. Il nostro team è disponibile per assistere con qualsiasi problema o domanda riguardante il modulo "Pagina di conferma ordine per ordini gratuiti".
