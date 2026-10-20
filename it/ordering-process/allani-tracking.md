---
title: "Tracciamento Allani - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop di tracciamento Allani di MyPresta.eu."
sidebar:
  label: "Tracciamento Allani - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Allani tracking su MyPresta.eu](https://mypresta.eu/modules/ordering-process/allani-tracking.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/allani-tracking/)
>
> ---


# Tracciamento Allani

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5 (Il modulo è progettato per funzionare su un'ampia gamma di versioni PHP, fino all'ultima versione stabile supportata da PrestaShop 1.7.x e versioni future.)
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL) tipicamente disponibili su qualsiasi ambiente di hosting PrestaShop moderno.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Tracciamento Allani" per accedere alle sue impostazioni.

#### Identificazione dell'ordine

Questa sezione controlla come il modulo identifica e invia i dati dell'ordine ad Allani.

-   **Cosa fa questa impostazione:** Questa è l'impostazione principale per il modulo. Determina se il modulo è attivo e invia i dati dell'ordine ad Allani.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo invierà automaticamente i dettagli dell'ordine (ID prodotto, valore dell'ordine, ID ordine) alla piattaforma Allani ogni volta che un cliente completa con successo un ordine sul tuo negozio PrestaShop. Questo è essenziale affinché Allani possa tracciare le tue vendite.
    -   *Quando disabilitato (NO):* Il modulo smetterà di inviare qualsiasi dato dell'ordine ad Allani. Ciò significa che Allani non riceverà aggiornamenti in tempo reale sulle tue vendite, potenzialmente influenzando le tue analisi e i tuoi rapporti sulla loro piattaforma.
-   **Valore consigliato:** **SÌ**. Per utilizzare appieno il servizio di tracciamento Allani, questa impostazione dovrebbe essere sempre abilitata.
-   **Scenario / esempio del commerciante:** Se ti sei appena iscritto ad Allani e vuoi iniziare a tracciare le tue vendite immediatamente, abiliteresti questa impostazione. Se desideri sospendere temporaneamente la trasmissione dei dati ad Allani per scopi di manutenzione o test, potresti disabilitarla, ma ricorda di riabilitarla in seguito.

#### Altre impostazioni interne (Non configurabili direttamente dal commerciante)

Potresti vedere altre chiavi di configurazione come `mypresta_updates`, `update_`, `updatev_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Queste sono impostazioni interne utilizzate dal modulo per i propri controlli di aggiornamento o per interagire con le funzionalità principali di PrestaShop (come la gestione delle lingue). Non è necessario configurarle e non sono esposte come opzioni modificabili dall'utente.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Identificazione dell'ordine | SÌ | Controlla se i dati dell'ordine vengono inviati ad Allani. **Abilita** per il tracciamento Allani. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo alcun cambiamento nel mio negozio. Funziona?**
R: Sì, è normale! Il modulo di tracciamento Allani funziona interamente in background. Non aggiunge alcun elemento visibile al front office del tuo negozio. La sua funzione è inviare dati ad Allani dopo che un ordine è stato effettuato. Per confermare che funziona, effettua un ordine di prova e poi controlla il tuo account Allani per i nuovi dati dell'ordine.

**D: Allani non riceve i dati del mio ordine. Cosa devo controllare?**
R:

1.  **Modulo abilitato:** Vai su **Moduli > Gestione moduli**, trova "Tracciamento Allani" e assicurati che sia installato e abilitato.
2.  **Impostazione di configurazione:** Clicca su "Configura" per il modulo e assicurati che "Identificazione dell'ordine" sia impostato su **SÌ**.
3.  **Svuota cache:** A volte, la cache di PrestaShop può impedire che le nuove impostazioni abbiano effetto. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
4.  **Account Allani:** Ricontrolla le impostazioni del tuo account Allani o contatta il supporto Allani per assicurarti che il tuo negozio sia correttamente collegato dalla loro parte.
5.  **Versione PrestaShop:** Assicurati di aver scaricato la versione corretta del modulo per la tua installazione di PrestaShop (es. 1.7.x, 1.6.x).

**D: Questo modulo rallenterà il mio negozio?**
R: No, l'impatto sulle prestazioni del tuo negozio è trascurabile. Lo script di tracciamento viene eseguito solo sulla pagina di conferma dell'ordine, che è tipicamente l'ultimo passaggio nel percorso del cliente. Il trasferimento dei dati è rapido e asincrono, il che significa che non rallenterà il caricamento della pagina per i tuoi clienti.

**D: Questo modulo supporta configurazioni multi-lingua o multi-negozio?**
R: Il modulo invia principalmente dati numerici e ID prodotto, che sono indipendenti dalla lingua. Per il multi-negozio, finché il modulo è abilitato e configurato per ogni contesto di negozio in cui desideri tracciare gli ordini, dovrebbe funzionare correttamente.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Tracciamento Allani` è un modulo PrestaShop leggero progettato per un unico scopo: inviare i dati di conferma dell'ordine alla piattaforma Allani. Segue una struttura standard dei moduli PrestaShop, utilizzando principalmente gli hook per iniettare la sua logica di tracciamento. La funzionalità principale risiede all'interno della classe principale del modulo (`allanitracking.php`), che gestisce l'installazione, la disinstallazione, la configurazione e la registrazione degli hook. Non introduce controller personalizzati, modelli o complesse risorse JavaScript/CSS, concentrandosi esclusivamente sulla trasmissione dei dati tramite un template Smarty iniettato nell'hook `displayOrderConfirmation`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. La logica front-office del modulo è gestita direttamente all'interno dell'hook `displayOrderConfirmation` tramite un template Smarty.
-   **Controller Admin Back-Office**: Nessuno. La configurazione è gestita direttamente tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuna classe personalizzata o definizione di `ObjectModel` è introdotta da questo modulo. Tutta la logica è autocontenuta all'interno di `allanitracking.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessun file JavaScript personalizzato è incluso o utilizzato da questo modulo. Lo script di tracciamento è incorporato direttamente nel template `displayOrderConfirmation.tpl`.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessun file CSS personalizzato è incluso o utilizzato da questo modulo, poiché non ha componenti front-office visibili.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per iniettare lo script di tracciamento nel front office.

-   **Template degli hook (`views/templates/hook/`)**:

    -   `allanitracking/views/templates/hook/displayOrderConfirmation.tpl`
        -   **Hook**: `displayOrderConfirmation`
        -   **Scopo**: Questo template viene renderizzato sulla pagina di conferma dell'ordine (dopo un acquisto riuscito). Contiene la logica principale per l'invio dei dati dell'ordine ad Allani. Accede alle variabili Smarty `$order` e `$products`, che vengono passate da PrestaShop a questo hook, per estrarre `orderValue`, `orderID` e `productIds`. Il template quindi costruisce ed esegue il JavaScript necessario per trasmettere questi dati alla piattaforma Allani.
    -   `allanitracking/views/templates/hook/header.tpl`
        -   **Hook**: `displayHeader` (o `header` nelle versioni precedenti)
        -   **Scopo**: Questo template è tipicamente utilizzato per includere JavaScript o CSS globali nella sezione `<head>` della pagina. Nel contesto di questo modulo, potrebbe essere utilizzato per includere eventuali script globali Allani o meta tag necessari, sebbene la trasmissione primaria dei dati sia gestita da `displayOrderConfirmation.tpl`. Data la descrizione del modulo, probabilmente include una configurazione minima o un segnaposto.
-   **Template di amministrazione (`views/templates/admin/`)**: Nessuno.
-   **Template Front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza la sua configurazione nella tabella `ps_configuration`, in particolare la chiave `ALLANI_ORDER_TRACK`.
    -   Utilizza anche chiavi di configurazione standard di PrestaShop per i controlli di aggiornamento (`mypresta_updates`, `update_`, `updatev_`).
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` / `header` | Nella sezione `<head>` di ogni pagina del front-office. | Potenzialmente utilizzato per l'inizializzazione dello script globale Allani o per i meta tag. |
| `displayOrderConfirmation` | Sulla pagina di conferma dell'ordine, dopo un acquisto riuscito. | **Hook principale per questo modulo.** Inietta il codice JavaScript per inviare i dettagli dell'ordine (ID prodotto, valore dell'ordine, ID ordine) alla piattaforma Allani. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Tracciamento Allani", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere riguardo alla funzionalità del modulo.
