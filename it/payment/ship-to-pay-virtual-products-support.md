---
title: "Ship to pay + virtual products support - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Ship to pay + virtual products support di MyPresta.eu."
sidebar:
  label: "Ship to pay + virtual products support - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Ship to pay + virtual products support su MyPresta.eu](https://mypresta.eu/modules/payment-process/ship-to-pay-virtual-products-support.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/ship-to-pay-virtual-products-support/)
>
> ---


# Ship to pay + virtual products support

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono solitamente presenti su qualsiasi ambiente di hosting compatibile.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Ship to pay + virtual products support". Ti verrà presentata un'unica, completa schermata di configurazione.

Questa schermata visualizza una matrice (una griglia) dove puoi collegare i tuoi corrieri di spedizione disponibili con i tuoi moduli di pagamento installati.

**Comprendere la griglia di configurazione:**

-   **Righe (Corrieri):** Ogni riga rappresenta un corriere di spedizione che hai configurato nel tuo negozio PrestaShop (ad esempio, "Il mio corriere", "Corriere predefinito PrestaShop", "DHL", "UPS", ecc.).
-   **Colonne (Moduli di pagamento):** Ogni colonna rappresenta un modulo di pagamento che hai installato e abilitato nel tuo negozio PrestaShop (ad esempio, "Bonifico bancario", "Contrassegno", "PayPal", "Stripe", ecc.).
-   **Caselle di controllo:** All'intersezione di ogni riga del corriere e colonna del modulo di pagamento, c'è una casella di controllo.

**Come configurare:**

1.  **Identifica i tuoi Corrieri:** Guarda la colonna di sinistra per vedere tutti i tuoi corrieri di spedizione attivi.
2.  **Identifica i tuoi Metodi di Pagamento:** Guarda la riga superiore per vedere tutti i tuoi moduli di pagamento attivi.
3.  **Collegali:** Per ogni corriere, scorri la sua riga e **seleziona la casella** per ogni metodo di pagamento che desideri consentire per quel corriere specifico.
    -   *Cosa fa questa impostazione:* Questa casella di controllo determina se un particolare metodo di pagamento verrà offerto al cliente quando seleziona il corriere di spedizione corrispondente durante il checkout.
    -   *Effetto della modifica di questa impostazione:*
        -   **Quando selezionata:** Il metodo di pagamento sarà visibile e selezionabile dal cliente se sceglie questo corriere.
        -   **Quando deselezionata:** Il metodo di pagamento sarà nascosto e non disponibile per il cliente se sceglie questo corriere.
    -   *Valore consigliato:* Seleziona solo le combinazioni che hanno senso per la tua logica aziendale.
    -   *Scenario/esempio del commerciante:* Se "DHL Express" è un servizio veloce e premium, potresti selezionare solo "PayPal" e "Carta di Credito (Stripe)" per esso, e deselezionare "Bonifico bancario" per garantire un pagamento rapido per una consegna rapida.

**Riga speciale: "Prodotti virtuali"**

Questo modulo include una funzionalità unica per i prodotti virtuali. Vedrai una riga dedicata etichettata **"Prodotti virtuali"** (o simile, a seconda della tua versione e lingua di PrestaShop).

-   **Cosa fa questa impostazione:** Questa riga ti permette di specificare quali metodi di pagamento sono disponibili quando il carrello di un cliente contiene *solo* prodotti virtuali. Poiché i prodotti virtuali non hanno un metodo di spedizione tradizionale, questa riga agisce come il loro "corriere" per l'associazione del metodo di pagamento.
-   *Effetto della modifica di questa impostazione:*
    -   **Quando selezionata (per un metodo di pagamento nella riga "Prodotti virtuali"):** Quel metodo di pagamento sarà disponibile se il carrello del cliente è composto esclusivamente da prodotti virtuali.
    -   **Quando deselezionata:** Quel metodo di pagamento non sarà disponibile per i carrelli contenenti solo prodotti virtuali.
-   *Valore consigliato:* Seleziona i metodi di pagamento adatti per la consegna digitale immediata, tipicamente gateway di pagamento online come PayPal, Stripe o moduli di carta di credito.
-   *Scenario/esempio del commerciante:* Se vendi e-book, probabilmente selezioneresti "PayPal" e "Carta di Credito (Stripe)" nella riga "Prodotti virtuali", ma deselezioneresti "Contrassegno" o "Bonifico bancario" poiché questi non sono adatti per la consegna digitale istantanea.

**Salvataggio della configurazione:**

-   Dopo aver effettuato tutte le tue selezioni, ricorda di cliccare sul pulsante **"Salva"** (solitamente in fondo alla pagina) per applicare le modifiche.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Casella di controllo per Corriere X / Pagamento Y | Deselezionato per impostazione predefinita | **Scopo:** Collega un metodo di pagamento specifico a un corriere di spedizione specifico. **Impatto:** Se selezionato, il metodo di pagamento è disponibile quando viene scelto il Corriere X. Se deselezionato, è nascosto. |
| Pagina di configurazione del modulo | Casella di controllo per "Prodotti virtuali" / Pagamento Y | Deselezionato per impostazione predefinita | **Scopo:** Collega un metodo di pagamento specifico ai carrelli contenenti solo prodotti virtuali. **Impatto:** Se selezionato, il metodo di pagamento è disponibile per i carrelli solo con prodotti virtuali. Se deselezionato, è nascosto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho configurato il modulo, ma i metodi di pagamento non cambiano nel checkout. Cosa c'è che non va?**
R1:

-   **Svuota la cache:** Il problema più comune. Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
-   **Modulo abilitato:** Assicurati che il modulo "Ship to pay + virtual products support" sia effettivamente abilitato in **Moduli > Gestione moduli**.
-   **Moduli di pagamento abilitati:** Assicurati che i moduli di pagamento che stai cercando di collegare siano anch'essi abilitati e configurati correttamente nel tuo negozio.
-   **Compatibilità del tema:** Sebbene raro, alcuni temi pesantemente personalizzati potrebbero interferire. Se svuotare la cache non funziona, prova a passare temporaneamente al tema predefinito di PrestaShop per vedere se il problema persiste. Se si risolve, il tuo tema potrebbe aver bisogno di un aggiustamento.

**D2: Perché alcuni metodi di pagamento sono ancora visibili anche se li ho deselezionati per un corriere?**
R2:

-   **Più corrieri nel carrello:** Se un cliente ha prodotti nel carrello che utilizzerebbero corrieri diversi (ad esempio, un prodotto spedito dal Corriere A, un altro dal Corriere B), la logica di checkout di PrestaShop potrebbe diventare complessa. Questo modulo funziona principalmente quando viene selezionato un singolo metodo di spedizione per l'intero carrello.
-   **Prodotti virtuali nel carrello:** Se il carrello contiene un mix di prodotti fisici e virtuali, la logica del modulo per i prodotti virtuali potrebbe interagire con la logica specifica del corriere. Assicurati che la tua riga "Prodotti virtuali" sia configurata come previsto.
-   **Altri moduli:** Un altro modulo potrebbe sovrascrivere le opzioni di pagamento. Disabilita temporaneamente altri moduli relativi al pagamento per verificare la presenza di conflitti.

**D3: Come posso tradurre il testo del modulo in altre lingue?**
R3:

-   Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
-   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona la lingua che desideri tradurre.
-   Trova il modulo "Ship to pay + virtual products support" nell'elenco e clicca su "Modifica". Potrai quindi modificare qualsiasi stringa traducibile.

**D4: Ho aggiunto un nuovo corriere o modulo di pagamento, ma non compare nella griglia di configurazione.**
R4:

-   **Aggiorna la configurazione del modulo:** A volte, PrestaShop ha bisogno di un aggiornamento per rilevare nuove entità. Vai su **Moduli > Gestione moduli**, trova "Ship to pay + virtual products support" e clicca di nuovo su "Configura". Questo dovrebbe ricaricare la pagina di configurazione e visualizzare il nuovo corriere/modulo di pagamento.
-   **Assicurati che sia abilitato:** Assicurati che il nuovo corriere o modulo di pagamento sia completamente abilitato e configurato nella sua rispettiva sezione del Back Office di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente riservata a sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Ship to pay + virtual products support" opera sovrascrivendo una classe core di PrestaShop responsabile della ricerca delle opzioni di pagamento disponibili durante il checkout. Ciò gli consente di iniettare la sua logica personalizzata basata sui corrieri selezionati e sulla presenza di prodotti virtuali nel carrello, filtrando i metodi di pagamento presentati al cliente. Sfrutta il sistema di override di PrestaShop e l'archiviazione della configurazione standard.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. La sua logica è gestita principalmente tramite il file del modulo principale e un override.

### 4.3 Classi e modelli core (`classes/`)

-   **`shiptopay/override/classes/checkout/PaymentOptionsFinder.php`**
    -   **Scopo:** Questo è il cuore della funzionalità del modulo. Sovrascrive la classe `PaymentOptionsFinder` predefinita di PrestaShop, che è responsabile della determinazione delle opzioni di pagamento disponibili per il cliente durante il checkout.
    -   **Classe padre:** `PaymentOptionsFinderCore`
    -   **Metodi chiave e logica:**
        -   Il metodo `find()` sovrascritto (o simile, a seconda della versione di PrestaShop) viene intercettato.
        -   All'interno di questo metodo, il modulo recupera l'ID del corriere attualmente selezionato (dal carrello o dalla sessione) e verifica se il carrello contiene solo prodotti virtuali.
        -   Interroga quindi la configurazione del modulo (memorizzata in `ps_configuration`) per determinare quali moduli di pagamento sono consentiti per il corriere selezionato o per i prodotti virtuali.
        -   L'elenco originale delle opzioni di pagamento restituite da `PaymentOptionsFinderCore` viene quindi filtrato, rimuovendo tutti i metodi di pagamento non consentiti secondo la configurazione del modulo.
        -   Ciò garantisce che vengano visualizzati al cliente solo i metodi di pagamento consentiti.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. L'aggiornamento dinamico delle opzioni di pagamento è gestito dal JavaScript core di checkout di PrestaShop, che reagisce ai cambiamenti nella selezione del metodo di spedizione e ri-renderizza la sezione di pagamento in base alle opzioni filtrate fornite dal `PaymentOptionsFinder` sovrascritto.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Si integra perfettamente con lo stile del tema PrestaShop esistente per le opzioni di pagamento.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`shiptopay/views/shiptopay.tpl`**
    -   **Scopo:** Questo template è probabilmente utilizzato per il rendering del modulo di configurazione del modulo nel Back Office di PrestaShop. Costruisce la matrice HTML (griglia) di corrieri e metodi di pagamento con caselle di controllo, consentendo al commerciante di collegarli.
    -   **Ambito:** Template di amministrazione.
    -   **Variabili:** Tipicamente itererebbe sugli array `$carriers` e `$payment_modules`, utilizzando `Configuration::get()` per recuperare le impostazioni salvate per ogni casella di controllo.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database:**

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Le impostazioni di configurazione (i collegamenti tra corrieri/prodotti virtuali e metodi di pagamento) sono memorizzate nella tabella `ps_configuration`. Ogni impostazione verrebbe tipicamente memorizzata come coppia chiave-valore, dove la chiave potrebbe essere `SHIP_TO_PAY_CARRIER_X_PAYMENT_Y` e il valore `1` (abilitato) o `0` (disabilitato). Le impostazioni dei "Prodotti virtuali" seguirebbero una convenzione di denominazione simile.
-   **Tabella degli hook registrati:**

    | Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `displayHeader` | Nella sezione `<head>` di ogni pagina. | Sebbene elencato come potenziale hook front-office, questo modulo utilizza principalmente un override e non renderizza tipicamente contenuti visibili tramite `displayHeader`. Potrebbe essere utilizzato per l'inizializzazione interna del modulo o il caricamento di risorse, se presenti. |
    | `displayRightColumn` | Nella colonna destra delle pagine (se abilitato dal tema). | Non utilizzato direttamente per la funzionalità principale del modulo, poiché il suo impatto è sulle opzioni di pagamento del checkout. |
    | `displayLeftColumn` | Nella colonna sinistra delle pagine (se abilitato dal tema). | Non utilizzato direttamente per la funzionalità principale del modulo, poiché il suo impatto è sulle opzioni di pagamento del checkout. |
    | `displayFooter` | Nella sezione del footer di ogni pagina. | Non utilizzato direttamente per la funzionalità principale del modulo, poiché il suo impatto è sulle opzioni di pagamento del checkout. |
    | `displayModuleConfigureExtraButtons` | Nel gestore moduli, accanto al pulsante di configurazione. | Non utilizzato esplicitamente per la funzionalità principale, ma potrebbe essere utilizzato per azioni amministrative aggiuntive. |
    | `actionPaymentOptionsModifier` | (Implicito/Interno) | Questo modulo funziona principalmente sovrascrivendo `PaymentOptionsFinder`, che viene chiamato internamente durante il processo di checkout per generare l'elenco delle opzioni di pagamento. Sebbene non sia un tradizionale hook `hookDisplay` o `action`, l'override agisce come un punto di intercettazione. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Ship to pay + virtual products support", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema tecnico o domanda riguardante la funzionalità del modulo.
