---
title: "Order Grid Manager Free - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Order Grid Manager Free di MyPresta.eu."
sidebar:
  label: "Order Grid Manager Free - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Order Grid Manager Free su MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-manager-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/order-grid-manager-free/)
>
> ---


# Order Grid Manager Free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL) tipicamente incluse in qualsiasi ambiente di hosting web moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali del modulo. Qui troverai un elenco di tutte le colonne che appaiono nell'elenco degli ordini del tuo Back Office PrestaShop. Ogni colonna ha un semplice interruttore ON/OFF.

**Nome schermata e posizione nel menu:**

- **Percorso menu:** Back Office > Moduli > Gestione moduli > Order Grid Manager Free > Configura

**Impostazioni disponibili:**
Vedrai un elenco di caselle di controllo o interruttori, ognuno corrispondente a una colonna nell'elenco degli ordini del tuo Back Office. L'elenco esatto delle colonne può variare leggermente a seconda della tua versione di PrestaShop e di altri moduli installati, ma esempi comuni includono:

- **ID:** L'identificatore univoco per ogni ordine.

  - **Cosa fa questa impostazione:** Controlla se la colonna "ID" è visibile nell'elenco degli ordini.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "ID" verrà visualizzata.
    - *Quando disabilitata:* La colonna "ID" verrà nascosta.
  - **Valore consigliato:** SÌ (Spesso utile per riferimento rapido e supporto).
  - **Scenario/esempio del commerciante:** Se fai spesso riferimento agli ordini tramite il loro ID univoco quando comunichi con i clienti o il tuo magazzino, mantieni questa opzione abilitata. Se utilizzi principalmente altri identificatori come il nome del cliente o il riferimento, potresti nasconderla.
- **Riferimento:** Il numero di riferimento interno per l'ordine.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Riferimento".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Riferimento" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Riferimento" verrà nascosta.
  - **Valore consigliato:** SÌ (Cruciale per il tracciamento e la comunicazione interna).
  - **Scenario/esempio del commerciante:** La maggior parte dei commercianti utilizza il riferimento dell'ordine per le bolle di accompagnamento, le fatture e il servizio clienti. Mantieni questa opzione visibile a meno che tu non abbia un flusso di lavoro molto specifico che non la utilizzi.
- **Nuovo cliente:** Indica se l'ordine proviene da un nuovo cliente.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Nuovo cliente".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Nuovo cliente" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Nuovo cliente" verrà nascosta.
  - **Valore consigliato:** NO (A meno che tu non miri specificamente ai dati dei nuovi clienti nel tuo flusso di lavoro quotidiano).
  - **Scenario/esempio del commerciante:** Se il tuo team di marketing esamina frequentemente gli ordini per identificare le tendenze di acquisizione di nuovi clienti, potresti mantenerla visibile. Altrimenti, è spesso un buon candidato da nascondere per una visualizzazione più pulita.
- **Cliente:** Il nome del cliente che ha effettuato l'ordine.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Cliente".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Cliente" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Cliente" verrà nascosta.
  - **Valore consigliato:** SÌ (Quasi sempre essenziale per l'identificazione dell'ordine).
  - **Scenario/esempio del commerciante:** Hai quasi certamente bisogno di vedere chi ha effettuato l'ordine. Mantieni questa opzione abilitata.
- **Totale:** L'importo totale dell'ordine.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Totale".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Totale" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Totale" verrà nascosta.
  - **Valore consigliato:** SÌ (Importante per una panoramica finanziaria).
  - **Scenario/esempio del commerciante:** Essenziale per vedere rapidamente il valore di ogni ordine. Mantieni questa opzione abilitata.
- **Pagamento:** Il metodo di pagamento utilizzato per l'ordine.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Pagamento".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Pagamento" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Pagamento" verrà nascosta.
  - **Valore consigliato:** SÌ (Utile per la riconciliazione dei pagamenti).
  - **Scenario/esempio del commerciante:** Se hai bisogno di vedere rapidamente se un ordine è stato pagato tramite carta di credito, PayPal o bonifico bancario, mantieni questa opzione abilitata.
- **Stato:** Lo stato attuale dell'ordine (es. Pagamento accettato, Spedito, Consegnato).

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Stato".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Stato" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Stato" verrà nascosta.
  - **Valore consigliato:** SÌ (Critico per il monitoraggio dell'avanzamento dell'ordine).
  - **Scenario/esempio del commerciante:** Assolutamente essenziale per la gestione dell'evasione degli ordini. Mantieni questa opzione abilitata.
- **Data:** La data e l'ora in cui l'ordine è stato effettuato.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Data".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Data" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Data" verrà nascosta.
  - **Valore consigliato:** SÌ (Importante per l'ordine cronologico e l'invecchiamento).
  - **Scenario/esempio del commerciante:** Utile per ordinare gli ordini in base a quando sono stati effettuati o per identificare gli ordini più vecchi che richiedono attenzione. Mantieni questa opzione abilitata.
- **Fattura:** Link per visualizzare/scaricare la fattura.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Fattura".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Fattura" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Fattura" verrà nascosta.
  - **Valore consigliato:** SÌ (Comodo per un rapido accesso alle fatture).
  - **Scenario/esempio del commerciante:** Se il tuo team ha spesso bisogno di scaricare o visualizzare le fatture direttamente dall'elenco degli ordini, mantieni questa opzione abilitata.
- **Consegna:** Link per visualizzare/scaricare la bolla di consegna.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Consegna".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Consegna" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Consegna" verrà nascosta.
  - **Valore consigliato:** SÌ (Comodo per un rapido accesso alle bolle di consegna).
  - **Scenario/esempio del commerciante:** Se il tuo magazzino o il team di spedizione utilizza le bolle di consegna, mantenerla visibile fornisce un rapido accesso.
- **Azioni:** Pulsanti per visualizzare, modificare o eliminare l'ordine.

  - **Cosa fa questa impostazione:** Controlla la visibilità della colonna "Azioni".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitata:* La colonna "Azioni" verrà visualizzata.
    - *Quando disabilitata:* La colonna "Azioni" verrà nascosta.
  - **Valore consigliato:** SÌ (Essenziale per la gestione dei singoli ordini).
  - **Scenario/esempio del commerciante:** Avrai quasi sempre bisogno di visualizzare o modificare un ordine. Mantieni questa opzione abilitata.

**Salvataggio delle modifiche:**
Dopo aver effettuato le tue selezioni, ricorda di cliccare sul pulsante **"Salva"** (solitamente in fondo alla pagina di configurazione) per applicare le modifiche. Una volta salvato, naviga su **Ordini > Ordini** nel tuo Back Office per vedere il layout delle colonne aggiornato.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | ID | SÌ | Mostra/nasconde l'ID univoco dell'ordine. |
| Configurazione modulo | Riferimento | SÌ | Mostra/nasconde il riferimento interno dell'ordine. |
| Configurazione modulo | Nuovo cliente | NO | Mostra/nasconde l'indicatore per i nuovi clienti. |
| Configurazione modulo | Cliente | SÌ | Mostra/nasconde il nome del cliente. |
| Configurazione modulo | Totale | SÌ | Mostra/nasconde l'importo totale dell'ordine. |
| Configurazione modulo | Pagamento | SÌ | Mostra/nasconde il metodo di pagamento utilizzato. |
| Configurazione modulo | Stato | SÌ | Mostra/nasconde lo stato attuale dell'ordine. |
| Configurazione modulo | Data | SÌ | Mostra/nasconde la data di inserimento dell'ordine. |
| Configurazione modulo | Fattura | SÌ | Mostra/nasconde il link per scaricare la fattura. |
| Configurazione modulo | Consegna | SÌ | Mostra/nasconde il link per scaricare la bolla di consegna. |
| Configurazione modulo | Azioni | SÌ | Mostra/nasconde i pulsanti di azione (visualizza, modifica, elimina). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma la griglia degli ordini non è cambiata.**
R: Dopo aver salvato le modifiche nella configurazione del modulo, potrebbe essere necessario svuotare la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" nell'angolo in alto a destra. Inoltre, prova ad aggiornare la pagina del tuo browser (Ctrl+F5 o Cmd+R) per assicurarti di non visualizzare una versione in cache del Back Office.

**D: Posso avere diverse visualizzazioni delle colonne per diversi utenti amministratori?**
R: Il modulo "Order Grid Manager Free" applica un'unica impostazione universale per tutti gli amministratori. Non supporta le preferenze individuali degli utenti per la visibilità delle colonne. Se hai bisogno di questa funzionalità avanzata, potresti dover cercare un modulo premium o uno sviluppo personalizzato.

**D: Questo modulo influirà sulle prestazioni del mio negozio?**
R: No, questo modulo ha un impatto trascurabile sulle prestazioni. Modifica solo le colonne visualizzate nell'elenco degli ordini del Back Office, che è una regolazione di rendering lato client (browser) basata su una semplice configurazione. Non altera le query del database o i tempi di caricamento del front-office.

**D: E se nascondo accidentalmente una colonna di cui ho bisogno?**
R: Nessun problema! Torna semplicemente su **Moduli > Gestione moduli > Order Grid Manager Free > Configura**, riabilita la colonna desiderata spuntando la sua casella e salva le modifiche. Quindi svuota la cache e aggiorna il tuo browser.

**D: Questo modulo supporta le traduzioni multilingue per i nomi delle colonne?**
R: Il modulo stesso non introduce nuove stringhe traducibili per i nomi delle colonne. Controlla semplicemente la visibilità dei nomi delle colonne esistenti di PrestaShop, che sono già gestiti dal sistema di traduzione principale di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che desiderano comprendere, eseguire il debug o estendere il modulo "Order Grid Manager Free".

### 4.1 Panoramica dell'architettura

Il modulo `Order Grid Manager Free` è un modulo PrestaShop semplice progettato principalmente per modificare la visualizzazione dell'elenco `AdminOrders`. Sfrutta il sistema di configurazione di PrestaShop per memorizzare le preferenze dell'utente per la visibilità delle colonne e inietta JavaScript per nascondere/mostrare dinamicamente le colonne in base a queste impostazioni. Segue una struttura di modulo PrestaShop di base, con la sua logica principale che risiede nel file del modulo principale.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office personalizzati. Tutta la configurazione e la logica sono gestite all'interno della classe principale del modulo e del suo metodo `getContent()`.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate o istanze di `ObjectModel`. Opera direttamente sulla configurazione core di PrestaShop e sulle strutture esistenti del Back Office.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include file JavaScript dedicati in `views/js/`. La logica per nascondere/mostrare le colonne è probabilmente iniettata direttamente nel Back Office tramite un hook o all'interno del template del metodo `getContent()`, utilizzando JavaScript inline o una semplice iniezione CSS. Data la semplicità del modulo e la designazione "Free", è altamente probabile che l'occultamento delle colonne sia ottenuto aggiungendo regole CSS `display: none;` o manipolando direttamente il DOM dopo il caricamento della pagina, in base alla configurazione memorizzata.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include file CSS dedicati in `views/css/`. Similmente a JavaScript, qualsiasi stile (principalmente `display: none;` per le colonne) è probabilmente iniettato inline o generato dinamicamente in base alla configurazione.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`myordergridfree/views/templates/admin/advert.tpl`**:
  - **Ambito:** Back-office (pagina di configurazione Admin).
  - **Scopo:** Questo template è probabilmente utilizzato per visualizzare un annuncio o un messaggio promozionale all'interno della pagina di configurazione del modulo nel Back Office. È una pratica comune per i moduli gratuiti includere tali elementi. Non controlla direttamente la funzionalità della griglia degli ordini ma fa parte dell'output di `getContent()` del modulo.

Il modulo di configurazione effettivo per la visibilità delle colonne è probabilmente renderizzato direttamente all'interno del metodo `getContent()` del file principale del modulo, possibilmente utilizzando `HelperForm` di PrestaShop o HTML personalizzato, e quindi `advert.tpl` viene incluso per il contenuto promozionale.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle SQL personalizzate.
  - Memorizza le sue impostazioni di configurazione nella tabella standard di PrestaShop `ps_configuration`. Ogni impostazione (es. `MYORDERGRIDFREE_HIDE_ID_COLUMN`) corrisponderà a una riga in questa tabella, memorizzando un valore booleano (0 o 1) per la visibilità.
- **Tabella degli hook registrati**:
  La funzionalità principale di questo modulo si basa sulla modifica della visualizzazione del Back Office. Data la semplicità della versione "Free", è probabile che utilizzi uno o più dei seguenti approcci:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` delle pagine del Back Office. | Hook più probabile per iniettare CSS o JavaScript inline per nascondere le colonne nella pagina `AdminOrders`. Ciò consente al modulo di applicare `display: none;` a specifici elementi `<th>` e `<td>` in base alla configurazione salvata. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller Admin imposta le sue risorse multimediali. | Potrebbe essere utilizzato per registrare un piccolo file JS o uno script inline che viene eseguito specificamente sul controller `AdminOrders` per manipolare il DOM. |
| `displayAdminOrderListBefore` / `displayAdminOrderListAfter` | Prima/Dopo il rendering della tabella dell'elenco degli ordini. | Meno probabile per questo modulo, poiché modifica l'elenco stesso, non solo aggiunge contenuto intorno ad esso. |

Il metodo `install()` del modulo registrerebbe questi hook, e il metodo `hookDisplayBackOfficeHeader()` (o simile) conterrebbe la logica per recuperare la configurazione memorizzata e produrre il CSS/JS necessario per nascondere le colonne selezionate quando viene caricata la pagina `AdminOrders`.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Order Grid Manager Free", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo.
