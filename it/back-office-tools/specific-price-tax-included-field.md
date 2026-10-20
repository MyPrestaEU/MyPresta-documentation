---
title: "Campo prezzo specifico tasse incluse - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Specific price tax included field' di MyPresta.eu."
sidebar:
  label: "Campo prezzo specifico tasse incluse - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Specific price tax included field su MyPresta.eu](https://mypresta.eu/modules/administration-tools/specific-price-tax-included-field.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/specific-price-tax-included-field/)
>
> ---


# Campo prezzo specifico tasse incluse

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Specific price tax included field" in Gestione moduli. Questo ti porterà alla schermata di configurazione principale del modulo.

#### Impostazioni Generali

- **Cosa fa questa impostazione:** Questa sezione contiene tipicamente le impostazioni generali relative agli aggiornamenti del modulo e ai controlli di versione.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Il modulo controllerà periodicamente la disponibilità di nuove versioni da MyPresta.eu e ti avviserà nel Back Office. Questo assicura che tu stia sempre utilizzando la versione più recente, sicura e ricca di funzionalità.
  - *Quando disabilitato:* Il modulo non eseguirà controlli automatici degli aggiornamenti. Dovresti controllare manualmente gli aggiornamenti visitando il tuo account MyPresta.eu.
- **Valore consigliato:** **SÌ** (o abilitato). Mantenere questa opzione abilitata ti assicura di rimanere informato su importanti aggiornamenti e correzioni di bug.
- **Scenario / esempio del commerciante:** Vuoi essere avvisato se viene rilasciata una nuova versione del modulo che include correzioni di compatibilità per una nuova versione di PrestaShop o miglioramenti delle prestazioni. Mantenendo questa opzione abilitata verrà visualizzata una notifica nel tuo Back Office.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Controlli aggiornamenti (mypresta\_updates, update\_, updatev\_) | Abilitato | Controlla periodicamente nuove versioni del modulo e ti avvisa nel Back Office. |

## 3. Risoluzione dei problemi per i commercianti e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo il nuovo campo "Prezzo tasse incluse".**
R: Innanzitutto, assicurati che il modulo sia abilitato in **Moduli > Gestione moduli**. Quindi, naviga alla pagina di un prodotto, vai alla scheda "Prezzi" e clicca su "Aggiungi un nuovo prezzo specifico" o "Modifica" uno esistente. Il nuovo campo dovrebbe apparire all'interno del modulo di creazione/modifica del prezzo specifico. Se non è ancora visibile, prova a svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni**, quindi clicca su "Svuota la cache").

**D: Il prezzo calcolato tasse escluse sembra errato.**
R: Il modulo si basa sulla regola fiscale assegnata al prodotto.
1. **Controlla la regola fiscale del prodotto:** Vai alla pagina del prodotto, scheda "Prezzi", e verifica che sia selezionata la "Regola fiscale" corretta per il prodotto.
2. **Controlla la configurazione della regola fiscale:** Vai su **Internazionale > Tasse > Regole tasse** e assicurati che le aliquote fiscali definite per la regola fiscale selezionata siano corrette per i tuoi paesi/zone di destinazione.
3. **Svuota la cache:** Dopo aver verificato ed eventualmente corretto le impostazioni fiscali, svuota la cache di PrestaShop.

**D: Questo modulo influisce sui prezzi specifici esistenti?**
R: No, questo modulo aggiunge solo un nuovo campo di input al modulo di creazione/modifica del prezzo specifico. Non altera né ricalcola alcun prezzo specifico creato prima della sua installazione o utilizzando il campo predefinito "Prezzo tasse escluse". Fornisce semplicemente un modo alternativo per inserire nuovi prezzi specifici.

**D: Questo modulo funzionerà con il mio tema personalizzato?**
R: Sì, questo modulo modifica principalmente un modulo standard del Back Office di PrestaShop. Utilizza hook e JavaScript standard di PrestaShop per iniettare il nuovo campo. È altamente improbabile che entri in conflitto con temi personalizzati del front-office, poiché non ha componenti di visualizzazione nel front-office.

**D: Ricevo un errore dopo aver aggiornato PrestaShop.**
R: Dopo qualsiasi aggiornamento importante di PrestaShop, è buona pratica:
1. Svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni**).
2. Verificare la disponibilità di una nuova versione del modulo "Specific price tax included field" nel tuo account MyPresta.eu, poiché gli aggiornamenti spesso includono correzioni di compatibilità.
3. Se il problema persiste, contatta il supporto MyPresta.eu.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Specific price tax included field" (`sptincl`) è un modulo leggero per PrestaShop 1.7.x progettato per migliorare l'interfaccia di gestione dei prezzi specifici nel Back Office. Opera principalmente iniettando JavaScript nell'hook `actionAdminControllerSetMedia`, che poi modifica il DOM del modulo del prezzo specifico per aggiungere il campo "Prezzo tasse incluse" e implementare la logica di calcolo lato client necessaria. Non introduce nuove tabelle di database, controller o logica di business complessa lato server oltre alla sua configurazione.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller Admin Front-Office o Back-Office personalizzato. Tutte le sue funzionalità sono iniettate nelle pagine admin esistenti di PrestaShop tramite hook e JavaScript.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non introduce alcuna classe PHP personalizzata o definizioni di `ObjectModel`. La sua logica principale risiede all'interno del file principale del modulo (`sptincl.php`).

### 4.4 Risorse JavaScript (`views/js/`)

- **`sptincl/views/js/sptincl.js`**
  - **Ambito:** Back-office (specificamente, il modulo di creazione/modifica del prezzo specifico).
  - **Scopo:** Questo script è responsabile della funzionalità principale del modulo.
    - **Manipolazione del DOM:** Aggiunge dinamicamente un nuovo campo di input per "Prezzo tasse incluse" al modulo del prezzo specifico. Modifica anche il comportamento del campo esistente "Prezzo tasse escluse".
    - **Listener di eventi:** Collega listener di eventi (es. `keyup`, `change`) sia al nuovo campo "Prezzo tasse incluse" che al campo esistente "Prezzo tasse escluse", così come al selettore della regola fiscale.
    - **Logica di calcolo:** Quando un utente inserisce un valore nel campo "Prezzo tasse incluse" o modifica la regola fiscale, lo script calcola il valore corrispondente "Prezzo tasse escluse" utilizzando l'aliquota fiscale selezionata. Viceversa, se il campo "Prezzo tasse escluse" viene modificato, calcola il valore "Prezzo tasse incluse".
    - **AJAX (Implicito):** Sebbene non esegua direttamente chiamate AJAX, si basa sulle aliquote fiscali disponibili nel DOM o recuperate dai meccanismi esistenti di PrestaShop per eseguire i suoi calcoli. Utilizza la funzione `getTaxRate()` (che potrebbe essere una funzione JS globale di PrestaShop o una personalizzata definita all'interno dello script) per recuperare l'aliquota fiscale corrente in base alla regola fiscale selezionata.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Si basa sullo stile predefinito di PrestaShop per gli elementi del modulo, garantendo un'integrazione perfetta con l'interfaccia utente del Back Office.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non utilizza file di template Smarty personalizzati. La sua configurazione è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo, e le sue modifiche front-end sono puramente basate su JavaScript.

### 4.7 Schema del database e Mappa degli Hook

- **Tabelle del database**: Questo modulo non crea alcuna tabella di database personalizzata. Memorizza le sue impostazioni di configurazione (come `mypresta_updates`, `update_`, `updatev_`) nella tabella standard `ps_configuration`.
- **Tabella degli Hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin viene inizializzato e le sue risorse multimediali (JS/CSS) vengono impostate. | Questo è l'hook principale utilizzato dal modulo. Inietta il file JavaScript `sptincl.js` nel Back Office, mirando specificamente al modulo di creazione/modifica del prezzo specifico. Ciò consente al modulo di modificare il DOM del modulo e aggiungere la sua logica di calcolo lato client. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Specific price tax included field", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
