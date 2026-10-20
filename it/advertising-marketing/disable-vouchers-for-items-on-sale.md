---
title: "Disabilita buoni per articoli in saldo - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Disabilita buoni per articoli in saldo' di MyPresta.eu."
sidebar:
  label: "Disabilita buoni per articoli in saldo - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Disable vouchers for items on sale su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/disable-vouchers-for-items-on-sale.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/disable-vouchers-for-items-on-sale/)
>
> ---


# Disabilita buoni per articoli in saldo

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili su qualsiasi moderno ambiente di hosting PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Disabilita buoni per articoli in saldo". Puoi accedervi navigando su **Moduli > Gestione moduli** e cercando "Disabilita buoni per articoli in saldo", quindi cliccando sul pulsante "Configura".

#### **Impostazioni Generali**

-   **Disabilita buoni per articoli in saldo:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Se il carrello di un cliente contiene *qualsiasi* prodotto attualmente in saldo (ha un prezzo speciale), gli verrà impedito di applicare *qualsiasi* codice buono.
        -   *Quando disabilitato (NO):* Il modulo sarà inattivo. I clienti potranno applicare codici buono anche se il loro carrello contiene articoli in saldo, consentendo il "doppio sconto".
    -   **Valore consigliato:** **SÌ** se vuoi prevenire il doppio sconto e proteggere i tuoi margini.
    -   **Scenario / esempio per il commerciante:** Stai effettuando una "Vendita estiva" con il 20% di sconto su articoli selezionati. Hai anche un buono "Benvenuto10" per i nuovi clienti. Se questa impostazione è **SÌ**, un nuovo cliente non può usare "Benvenuto10" se il suo carrello include qualsiasi articolo della Vendita estiva.
-   **Disabilita modulo per codici che iniziano con:**

    -   **Cosa fa questa impostazione:** Questo ti permette di creare un'eccezione. Se un codice buono inizia con una stringa specifica che definisci qui, la restrizione del modulo *non* si applicherà a quel buono, anche se ci sono articoli in saldo nel carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserita una stringa (ad esempio, "SPEDGRATIS"):* Qualsiasi codice buono che inizia con "SPEDGRATIS" (ad esempio, "SPEDGRATIS2023", "SPEDGRATISORA") bypasserà la restrizione del modulo. I clienti possono usare questi buoni specifici anche con articoli in saldo nel carrello.
        -   *Quando lasciato vuoto:* Non vengono fatte eccezioni basate sui prefissi dei codici buono. Tutti i buoni sono soggetti alla regola "Disabilita buoni per articoli in saldo".
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia buoni specifici che vuoi *sempre* consentire, indipendentemente dagli articoli in saldo.
    -   **Scenario / esempio per il commerciante:** Hai un buono speciale "SPEDGRATIS" che offre la spedizione gratuita. Decidi che la spedizione gratuita dovrebbe essere sempre consentita, anche sugli articoli in saldo, per incoraggiare ordini più grandi. Inseriresti "SPEDGRATIS" in questo campo.
-   **Messaggio per il cliente:**

    -   **Cosa fa questa impostazione:** Questo è il messaggio personalizzato che i clienti vedranno nel loro carrello quando tentano di applicare un codice buono ma vengono bloccati a causa di articoli in saldo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un messaggio (ad esempio, "I buoni non possono essere usati con articoli in saldo."):* Questo messaggio esatto verrà visualizzato al cliente.
        -   *Quando lasciato vuoto:* Il modulo probabilmente visualizzerà un messaggio di errore predefinito o generico, che potrebbe essere meno chiaro per il cliente.
    -   **Valore consigliato:** Un messaggio chiaro, cortese e informativo.
    -   **Scenario / esempio per il commerciante:** Vuoi informare chiaramente i clienti: "Questo buono non può essere applicato perché il tuo carrello contiene articoli già in saldo. Rimuovi gli articoli in saldo o usa un buono diverso."

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Disabilita buoni per articoli in saldo | SÌ | Attiva/disattiva la funzionalità principale per bloccare i buoni sugli articoli in saldo. |
| Configurazione Modulo | Disabilita modulo per codici che iniziano con: | Lascia vuoto | Consente a specifici codici buono (per prefisso) di bypassare le restrizioni del modulo. |
| Configurazione Modulo | Messaggio per il cliente | "I buoni non possono essere usati con articoli in saldo." (o simile) | Personalizza il messaggio di errore mostrato ai clienti quando un buono viene bloccato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato il modulo, ma i clienti possono ancora usare i buoni sugli articoli in saldo. Cosa c'è che non va?**
R:

1.  **Controlla l'impostazione "Disabilita buoni per articoli in saldo":** Assicurati che sia impostata su **SÌ** nella configurazione del modulo.
2.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). Le modifiche al modulo a volte richiedono un aggiornamento della cache.
3.  **Verifica lo stato di saldo:** Ricontrolla che i prodotti con cui stai testando siano effettivamente contrassegnati come "in saldo" in PrestaShop (ad esempio, hanno un prezzo specifico definito che li rende più economici del loro prezzo normale).
4.  **Controlla l'eccezione del prefisso del codice buono:** Se hai inserito una stringa in "Disabilita modulo per codici che iniziano con:", assicurati che il buono che stai testando non inizi con quella stringa.

**D: Il modulo sta bloccando i buoni, ma il messaggio non viene visualizzato, oppure mostra un errore generico.**
R:

1.  **Personalizza il messaggio:** Vai alla configurazione del modulo e assicurati di aver inserito un messaggio personalizzato nel campo "Messaggio per il cliente".
2.  **Compatibilità del tema:** Sebbene il modulo cerchi di integrarsi senza problemi, alcuni temi altamente personalizzati potrebbero sovrascrivere i meccanismi di visualizzazione degli errori predefiniti di PrestaShop. Se il messaggio non appare, potrebbe essere un problema del tema del front-office. Contatta lo sviluppatore del tuo tema o un webmaster per assistenza.

**D: Posso disabilitare questo modulo per specifici gruppi di clienti o singoli prodotti?**
R: No, questo modulo opera globalmente in base alla presenza di *qualsiasi* articolo in saldo nel carrello. Non offre un controllo granulare per specifici gruppi di clienti o esclusioni di prodotti oltre all'eccezione del prefisso del codice buono. Se hai bisogno di una logica più avanzata, potrebbe essere necessario uno sviluppo personalizzato.

**D: Questo modulo influirà sul mio SEO o sulle mie schede prodotto?**
R: No, questo modulo opera puramente sulla logica di applicazione dei buoni nel carrello. Non altera i prezzi dei prodotti, le descrizioni, gli URL o qualsiasi altro elemento del front-office che potrebbe influire sul SEO.

**D: Ho aggiornato la mia versione di PrestaShop e ora il modulo non funziona.**
R:

1.  **Controlla la compatibilità del modulo:** Assicurati di aver scaricato e installato la versione del modulo specificamente progettata per la tua versione di PrestaShop dal tuo account MyPresta.eu.
2.  **Reinstalla/Riconfigura:** A volte, dopo un importante aggiornamento di PrestaShop, i moduli potrebbero dover essere reinstallati o riconfigurati. Prova a disinstallare e poi a reinstallare il modulo (ricorda di eseguire il backup delle tue impostazioni se possibile, anche se questo modulo ha dati minimi).
3.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo qualsiasi aggiornamento o modifica del modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Disabilita buoni per articoli in saldo" (`dvfis`) funziona principalmente sovrascrivendo il `CartController` principale per intercettare il processo di applicazione del buono. Sfrutta il meccanismo di override di PrestaShop per iniettare la sua logica prima che un buono venga convalidato e applicato. La configurazione del modulo è memorizzata in `ps_configuration` e accessibile tramite la classe principale del modulo.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `dvfis/override/controllers/front/CartController.php`
        -   **Nome classe e classe genitore**: `CartController` (sovrascrive la classe `CartController` principale)
        -   **Responsabilità**: Questo è il file più critico. Estende il `CartController` principale per modificare il metodo `postProcess()`. In particolare, intercetta la logica quando un cliente tenta di aggiungere un buono (`addDiscount()`). Controlla se il modulo è abilitato e se il carrello contiene prodotti con un prezzo speciale. Se entrambe le condizioni sono soddisfatte (e il codice del buono non corrisponde a un prefisso di esclusione), impedisce l'aggiunta del buono e visualizza un messaggio di errore personalizzato.
    -   `dvfis/override/controllers/front/index.php`
        -   **Nome classe e classe genitore**: Non è un file di classe, tipicamente un file vuoto o un file con un `<?php exit;` di base per impedire l'elenco diretto della directory. È una pratica standard per le directory di override di PrestaShop.
-   **Controller Admin Back-Office**: Nessuno. Il modulo utilizza il metodo `getContent()` standard all'interno del suo file principale del modulo per la configurazione.

### 4.3 Classi e modelli principali (`classes/`)

Nessuno. Il modulo non definisce alcuna classe `ObjectModel` personalizzata o altre classi PHP standalone nella directory `classes/`. Tutta la logica è contenuta nel file principale del modulo e nell'override del `CartController`.

### 4.4 Risorse JavaScript (`views/js/`)

Nessuno. Il modulo non include alcun file JavaScript personalizzato. Tutte le interazioni del front-office sono gestite lato server dall'override del `CartController`.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessuno. Il modulo non include alcun file CSS personalizzato. Eventuali messaggi visualizzati al cliente erediteranno lo stile dei messaggi di errore/notifica del tema PrestaShop attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

Nessuno. Il modulo non utilizza file di template Smarty personalizzati. I messaggi di errore vengono passati direttamente all'array `errors` del `CartController`, che vengono poi renderizzati dal meccanismo di visualizzazione degli errori standard del tema.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea alcuna tabella di database personalizzata. Tutte le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`:

    -   `DVFIS_MESSAGE`: Memorizza il messaggio personalizzato per i clienti.
    -   `DVFIS_ENABLED`: Memorizza il valore booleano (0 o 1) per abilitare/disabilitare il modulo.
    -   `DVFIS_STR`: Memorizza il prefisso della stringa per le eccezioni del codice buono.
    -   `DVFIS_STRV`: (Probabilmente una chiave di versione legacy o interna, non direttamente configurabile dall'utente).
    -   `mypresta_updates`, `update_`, `updatev_`: Chiavi relative al sistema di aggiornamento di MyPresta.eu.
    -   `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Chiavi di configurazione standard di PrestaShop utilizzate per la gestione delle lingue nel `getContent()` del modulo.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Durante l'inizializzazione del controller del Back Office | Utilizzato dal modulo per includere i propri file CSS/JS (se presenti) nel Back Office. Nel caso di questo modulo, è probabilmente utilizzato per il sistema di aggiornamento di MyPresta.eu o per la configurazione generale del modulo, non per stili/script personalizzati. |
| `actionFrontControllerInitAfter` | Dopo che un controller del Front Office è stato inizializzato | Utilizzato dal modulo per eseguire potenzialmente azioni o modificare il comportamento del controller all'inizio del ciclo di richiesta. Per questo modulo, è probabilmente utilizzato per garantire che l'override del `CartController` sia caricato e attivo correttamente. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Disabilita buoni per articoli in saldo", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
