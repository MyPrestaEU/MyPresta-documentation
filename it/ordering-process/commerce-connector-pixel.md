---
title: "Pixel Commerce Connector - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pixel Commerce Connector di MyPresta.eu."
sidebar:
  label: "Pixel Commerce Connector - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Commerce Connector pixel su MyPresta.eu](https://mypresta.eu/modules/ordering-process/commerce-connector-pixel.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/commerce-connector-pixel/)
>
> ---


# Pixel Commerce Connector

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti per i moduli PrestaShop. Di solito non sono necessarie configurazioni speciali del server per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Pixel Commerce Connector" per accedere alle sue impostazioni.

#### **Identificativo negozio**

-   **Cosa fa questa impostazione:** Questo è l'identificativo unico fornito da Commerce Connector per il tuo negozio o account commerciante specifico. È fondamentale affinché Commerce Connector attribuisca correttamente i dati di vendita al tuo account.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato con il tuo ID negozio corretto:* Il pixel si attiverà con il tuo identificativo unico, consentendo a Commerce Connector di tracciare accuratamente le vendite per il tuo negozio.
    -   *Quando errato o vuoto:* Il pixel potrebbe non attivarsi correttamente, o i dati di vendita potrebbero essere attribuiti all'account sbagliato, portando a un tracciamento inaccurato e potenzialmente a una perdita di informazioni di marketing.
-   **Valore consigliato:** Inserisci la stringa esatta "Identificativo negozio" fornita da Commerce Connector. Di solito è una combinazione di lettere e numeri.
-   **Scenario / esempio per il commerciante:** Commerce Connector ti dice che il tuo ID negozio è "MYSTORE12345". Dovresti inserire "MYSTORE12345" in questo campo. Senza di esso, Commerce Connector non saprà da quale negozio proviene la vendita.

#### **Registra avvii pixel**

-   **Cosa fa questa impostazione:** Questa impostazione controlla se il modulo registra un log ogni volta che il pixel Commerce Connector viene avviato (cioè, ogni volta che un cliente raggiunge la pagina di conferma dell'ordine e il pixel tenta di attivarsi). Questo log può essere utile per la risoluzione dei problemi.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato ("Sì"):* Il modulo creerà un file di log (solitamente nella directory del modulo) che dettaglia ogni avvio del pixel, inclusi i dettagli dell'ordine. Questo può aiutarti a verificare se il pixel si sta attivando come previsto.
    -   *Quando disabilitato ("No"):* Non verrà generato alcun file di log, che è l'impostazione standard per un negozio di produzione per risparmiare spazio su disco e elaborazione.
-   **Valore consigliato:** "No" per un negozio di produzione attivo. Abilita "Sì" solo temporaneamente se stai risolvendo problemi e hai bisogno di verificare l'attività del pixel.
-   **Scenario / esempio per il commerciante:** Sospetti che il pixel non stia tracciando tutte le vendite. Abiliti "Registra avvii pixel" su "Sì", effettui un ordine di prova e poi controlli il file di log per vedere se il tuo ordine di prova è stato registrato, confermando che il pixel si è attivato. Una volta confermato, lo riporti su "No".

#### **Abilita / Disabilita Modulo**

-   **Cosa fa questa impostazione:** Questo è un interruttore standard del modulo PrestaShop che ti consente di abilitare o disabilitare globalmente l'intero modulo Pixel Commerce Connector.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo sarà attivo e il pixel Commerce Connector verrà iniettato nella tua pagina di conferma dell'ordine, tracciando le vendite.
    -   *Quando disabilitato:* Il modulo sarà inattivo e il pixel Commerce Connector NON sarà presente nella tua pagina di conferma dell'ordine, il che significa che nessuna vendita verrà tracciata tramite questo modulo.
-   **Valore consigliato:** "Sì" se stai utilizzando attivamente Commerce Connector per il tracciamento delle vendite.
-   **Scenario / esempio per il commerciante:** Hai completato la tua integrazione con Commerce Connector e vuoi iniziare a tracciare le vendite. Ti assicuri che questa impostazione sia "Sì". Se metti temporaneamente in pausa le tue campagne Commerce Connector, potresti impostarla su "No" per evitare l'attivazione non necessaria del pixel.

#### Altre chiavi di configurazione (Interne)

Il modulo utilizza anche chiavi di configurazione interne come `mypresta_updates`, `update_`, `updatev_`, `COMCONN_SIDENT_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Queste sono tipicamente per la gestione interna del modulo, i controlli degli aggiornamenti e la gestione delle lingue all'interno del back office di PrestaShop. I commercianti generalmente non hanno bisogno di interagire direttamente con queste.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Identificativo negozio | Il tuo ID unico Commerce Connector | Cruciale per attribuire i dati di vendita al tuo account Commerce Connector specifico. |
| Configurazione Modulo | Registra avvii pixel | No | Controlla se il modulo crea un file di log degli avvii del pixel. Abilita per la risoluzione dei problemi, disabilita per la produzione. |
| Configurazione Modulo | Abilita / Disabilita Modulo | Sì | Attiva o disattiva globalmente l'intero modulo e il suo tracciamento pixel. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma Commerce Connector non mostra alcuna vendita. Cosa devo fare?**
R:

1.  **Controlla "Identificativo negozio":** Vai alla configurazione del modulo e assicurati che il tuo "Identificativo negozio" sia inserito correttamente e corrisponda esattamente a quanto fornito da Commerce Connector.
2.  **Modulo Abilitato:** Assicurati che il modulo sia abilitato nella pagina di configurazione.
3.  **Svuota Cache:** Vai su **Parametri Avanzati > Prestazioni** nel tuo back office PrestaShop e svuota la cache di Smarty e tutte le cache.
4.  **Acquisto di Prova:** Esegui un acquisto di prova completo sul tuo negozio, arrivando fino alla pagina di conferma dell'ordine.
5.  **Abilita la Registrazione:** Abilita temporaneamente "Registra avvii pixel" nella configurazione del modulo, esegui un altro acquisto di prova e poi controlla il file `logFile.tpl` (o un file di log simile) all'interno della directory del modulo tramite FTP per vedere se l'avvio del pixel è stato registrato.
6.  **Contatta il Supporto:** Se i problemi persistono, contatta il supporto MyPresta.eu con i dettagli della tua configurazione e qualsiasi voce di log.

**D: Questo modulo rallenterà il mio sito web?**
R: No. Il pixel Commerce Connector è uno script molto leggero che si carica solo sulla pagina di conferma dell'ordine. Questa pagina viene tipicamente raggiunta dopo l'esperienza di acquisto principale, e l'esecuzione del pixel è minima, quindi non influirà in modo significativo sulle prestazioni o sulla velocità di caricamento del tuo negozio per i clienti.

**D: Posso usare questo modulo con altri pixel di tracciamento (es. Google Analytics, Facebook Pixel)?**
R: Sì, assolutamente. Questo modulo è progettato per integrarsi specificamente con Commerce Connector. Opera indipendentemente e non entrerà in conflitto con altri pixel di tracciamento o script di analisi che hai installato sul tuo negozio PrestaShop.

**D: Dove posso trovare il file di log se abilito "Registra avvii pixel"?**
R: Se abilitato, il file di log viene tipicamente generato all'interno della directory del modulo. Avresti bisogno dell'accesso FTP al tuo server per navigare in `tua_root_prestashop/modules/comconn/views/templates/hook/logFile.tpl` (o un percorso simile) per visualizzarne il contenuto. Ricorda di disabilitare la registrazione una volta completata la risoluzione dei problemi.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Pixel Commerce Connector (`comconn`) è un modulo PrestaShop semplice progettato per iniettare un pixel JavaScript specifico nella pagina di conferma dell'ordine. Aderisce all'architettura del modulo PrestaShop, sfruttando principalmente l'hook `displayOrderConfirmation` per renderizzare il suo script di tracciamento. La logica del modulo è contenuta nel suo file PHP principale, con la configurazione gestita tramite `getContent()` e i template per il rendering del pixel e un log opzionale.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Il modulo si aggancia direttamente a `displayOrderConfirmation` e renderizza il suo contenuto tramite un template.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

-   Nessuno. Il modulo non definisce alcuna classe personalizzata o istanza di `ObjectModel`. Tutta la logica è autocontenuta all'interno di `comconn.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessuno. Il modulo incorpora direttamente lo script del pixel Commerce Connector all'interno del suo template Smarty, piuttosto che collegarsi a file `.js` esterni.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessuno. Il modulo non aggiunge alcuna stilizzazione personalizzata al front o al back office.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per renderizzare il suo output.

-   **Template hook (`views/templates/hook/`)**:

    -   `comconn/views/templates/hook/displayOrderConfirmation.tpl`
        -   **Hook**: `displayOrderConfirmation`
        -   **Scopo**: Questo è il template principale responsabile del rendering dello script del pixel Commerce Connector. Inserisce dinamicamente l'`Identificativo negozio` (dalla configurazione `COMCONN_SIDENT`) e i dettagli dell'ordine (ID ordine, totale, valuta, prodotti) nel codice JavaScript che attiva il pixel. Questo template è cruciale per la funzionalità principale del modulo.
    -   `comconn/views/templates/hook/logFile.tpl`
        -   **Hook**: Non direttamente agganciato, ma utilizzato dal meccanismo di logging interno del modulo.
        -   **Scopo**: Questo template viene utilizzato per formattare e archiviare le voci di log quando l'opzione "Registra avvii pixel" è abilitata. Registra i dettagli di ogni avvio del pixel, inclusi il timestamp, l'ID dell'ordine e i dati inviati a Commerce Connector. Gli sviluppatori possono ispezionare questo file tramite FTP per la risoluzione dei problemi.
-   **Template admin (`views/templates/admin/`)**: Nessuno.
-   **Template front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle del database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration`.

    -   Voci `PS_CONFIGURATION`:
        -   `COMCONN_SIDENT`: Memorizza l'ID negozio Commerce Connector del commerciante.
        -   `COMCONN_LOG`: Memorizza il valore booleano (0 o 1) per abilitare/disabilitare la registrazione degli avvii del pixel.
        -   `mypresta_updates`, `update_`, `updatev_`: Chiavi interne per gli aggiornamenti del modulo e il versioning.
-   **Tabella degli hook registrati**:

    | Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
    | --- | --- | --- |
    | `displayOrderConfirmation` | Dopo che un cliente completa con successo un ordine e raggiunge la pagina di conferma. | Inietta lo script del pixel Commerce Connector nella pagina per tracciare l'acquisto completato. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo "Pixel Commerce Connector", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per aiutarti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
"""
