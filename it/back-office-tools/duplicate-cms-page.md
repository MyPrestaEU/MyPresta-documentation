---
title: "Duplica pagina CMS - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Duplica pagina CMS di MyPresta.eu."
sidebar:
  label: "Duplica pagina CMS - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Duplicate CMS page su MyPresta.eu](https://mypresta.eu/modules/administration-tools/duplicate-cms-page.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/duplicate-cms-page/)
>
> ---


# Duplica pagina CMS

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Duplica pagina CMS" in Gestione moduli. Questo ti porterà alla schermata di configurazione principale del modulo.

#### Impostazioni generali

- **Aggiornamenti MyPresta.eu (mypresta\_updates)**

  - **Cosa fa questa impostazione:** Questa impostazione controlla se il modulo verifica la disponibilità di aggiornamenti da MyPresta.eu. Mantenere questa opzione abilitata ti assicura di essere avvisato di nuove versioni, correzioni di bug e miglioramenti delle funzionalità.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo verificherà periodicamente la disponibilità di aggiornamenti. Se viene trovato un aggiornamento, potrebbe apparire una notifica nel tuo Back Office di PrestaShop.
    - *Quando disabilitato:* Il modulo non verificherà la disponibilità di aggiornamenti e non sarai avvisato automaticamente di nuove versioni. Dovresti controllare manualmente gli aggiornamenti su MyPresta.eu.
  - **Valore consigliato:** **SÌ** (Abilitato).
  - **Scenario/esempio del commerciante:** Vuoi assicurarti che il tuo modulo sia sempre aggiornato con le ultime patch di sicurezza e funzionalità senza dover controllare manualmente il sito web MyPresta.eu ogni settimana.
- **Aggiorna (update\_)**

  - **Cosa fa questa impostazione:** Questo è solitamente un campo di visualizzazione o un pulsante relativo al controllo degli aggiornamenti, che mostra lo stato attuale o consente un controllo manuale. Funziona in combinazione con l'impostazione "Aggiornamenti MyPresta.eu".
  - **Effetto della modifica di questa impostazione:** Cliccando un pulsante qui (se presente) si avvierebbe un controllo immediato degli aggiornamenti.
  - **Valore consigliato:** N/A (Basato sull'interazione).
  - **Scenario/esempio del commerciante:** Dopo aver abilitato "Aggiornamenti MyPresta.eu", potresti cliccare qui per vedere immediatamente se è disponibile una nuova versione, piuttosto che aspettare il prossimo controllo automatico.
- **Versione aggiornamento (updatev\_)**

  - **Cosa fa questa impostazione:** Questo campo visualizza tipicamente l'ultima versione disponibile del modulo rilevata dal verificatore di aggiornamenti.
  - **Effetto della modifica di questa impostazione:** Questo è un campo di sola visualizzazione e non può essere modificato direttamente. Fornisce informazioni sull'ultima versione.
  - **Valore consigliato:** N/A (Sola visualizzazione).
  - **Scenario/esempio del commerciante:** Vedi "1.2.3" qui, indicando che è disponibile una versione più recente della tua attuale (es. 1.2.2).
- **Ultima versione (dupcms\_LATEST)**

  - **Cosa fa questa impostazione:** Simile a "Versione aggiornamento", questo campo visualizza la versione più recente del modulo disponibile.
  - **Effetto della modifica di questa impostazione:** Questo è un campo di sola visualizzazione.
  - **Valore consigliato:** N/A (Sola visualizzazione).
  - **Scenario/esempio del commerciante:** Puoi verificare rapidamente se il tuo modulo installato è quello più attuale confrontando questo valore con la tua versione installata.
- **Miniature (dupcms\_MINIATURES)**

  - **Cosa fa questa impostazione:** Questa impostazione probabilmente controlla se le immagini in miniatura o le icone vengono visualizzate nell'interfaccia del modulo, possibilmente in relazione al verificatore di aggiornamenti o ad altri elementi visivi all'interno del pannello di amministrazione del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Potresti vedere piccole icone o immagini nella configurazione del modulo o nelle notifiche di aggiornamento.
    - *Quando disabilitato:* Questi elementi visivi sarebbero nascosti, risultando in un'interfaccia più basata sul testo.
  - **Valore consigliato:** **SÌ** (Abilitato).
  - **Scenario/esempio del commerciante:** Preferisci un'interfaccia più ricca visivamente nel tuo Back Office, quindi mantieni questa opzione abilitata per vedere eventuali icone pertinenti.
- **ID Categoria CMS (dupcms\_ID\_CMSCAT)**

  - **Cosa fa questa impostazione:** Questa impostazione è cruciale per la funzionalità principale del modulo. Ti consente di selezionare una categoria CMS predefinita in cui verranno posizionate le pagine CMS duplicate.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene selezionata una categoria specifica:* Tutte le nuove pagine CMS duplicate verranno automaticamente assegnate a questa categoria. Questo aiuta nell'organizzazione dei tuoi contenuti.
    - *Quando non viene selezionata alcuna categoria (o predefinita):* Il modulo potrebbe impostare come predefinita la stessa categoria della pagina originale, o una categoria radice, a seconda della sua logica interna. L'impostazione di una categoria specifica ti dà più controllo.
  - **Valore consigliato:** Seleziona una categoria predefinita logica, come "Informazioni" o una categoria specifica che utilizzi per le nuove pagine.
  - **Scenario/esempio del commerciante:** Duplichi frequentemente pagine di "Note legali" per diverse regioni. Puoi impostare questa opzione sulla tua categoria CMS "Pagine legali" in modo che tutti i nuovi duplicati vi atterrino automaticamente, rendendoli più facili da trovare e gestire.

#### Come utilizzare la funzione di duplicazione

L'azione di duplicazione effettiva avviene nell'elenco standard delle pagine CMS di PrestaShop:

1. Naviga su **Migliora > Design > Pagine** nel tuo Back Office di PrestaShop.
2. Vedrai un elenco delle tue pagine CMS esistenti.
3. Individua la pagina CMS che desideri duplicare.
4. Nella colonna "Azioni" (solitamente rappresentata da tre puntini o un menu a discesa) per quella specifica pagina CMS, troverai una nuova opzione aggiunta da questo modulo: **"Duplica"** (o un'icona/testo simile).
5. Clicca su "Duplica".
6. Il modulo creerà una copia esatta della pagina, inclusi il suo contenuto, le meta informazioni, l'URL amichevole e lo stato attivo. La nuova pagina avrà tipicamente un nome come "Copia di [Nome Pagina Originale]" o simile, che potrai poi modificare.
7. La pagina duplicata verrà posizionata nella categoria CMS che hai selezionato nella configurazione del modulo (se `dupcms_ID_CMSCAT` è impostato) o nella stessa categoria dell'originale.
8. Potrai quindi modificare la pagina appena duplicata per cambiarne il titolo, il contenuto, l'URL e altre impostazioni secondo necessità.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Aggiornamenti MyPresta.eu | SÌ | Abilita i controlli automatici per gli aggiornamenti del modulo. |
| Configurazione modulo | Aggiorna | N/A (Pulsante) | Avvia un controllo manuale per gli aggiornamenti del modulo. |
| Configurazione modulo | Versione aggiornamento | N/A (Visualizzazione) | Mostra l'ultima versione disponibile del modulo. |
| Configurazione modulo | Ultima versione | N/A (Visualizzazione) | Visualizza la versione più recente del modulo rilevata. |
| Configurazione modulo | Miniature | SÌ | Controlla la visualizzazione di elementi visivi/icone nell'interfaccia del modulo. |
| Configurazione modulo | ID Categoria CMS | Seleziona una categoria | Imposta la categoria CMS predefinita per le pagine duplicate. |
| Elenco pagine CMS (Design > Pagine) | Azione Duplica | N/A (Pulsante) | Crea una copia esatta della pagina CMS selezionata. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho duplicato una pagina, ma non riesco a trovarla.**
R: Controlla la categoria CMS che hai selezionato nella configurazione del modulo (`dupcms_ID_CMSCAT`). Se non ne hai impostata una, potrebbe trovarsi nella stessa categoria della pagina originale o nella categoria CMS radice. Inoltre, assicurati di cercare "Copia di [Nome Pagina Originale]" o simile, poiché il modulo aggiunge un prefisso al titolo della pagina duplicata.

**D: La pagina duplicata ha lo stesso URL amichevole dell'originale. È un problema?**
R: Sì, questo può causare conflitti e problemi SEO. Dopo aver duplicato una pagina, **modifica sempre la nuova pagina immediatamente** e cambia il suo URL amichevole (noto anche come "URL Rewrite" o "Slug") in qualcosa di unico e descrittivo per il nuovo contenuto. PrestaShop di solito aggiunge un numero (ad esempio, `-1`) all'URL, ma è meglio personalizzarlo tu stesso.

**D: Non vedo l'opzione "Duplica" nell'elenco delle pagine CMS.**
R:

1. Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Duplica pagina CMS" sia installato e abilitato.
2. Svuota la cache di PrestaShop: Vai su **Parametri avanzati > Prestazioni**, scorri verso il basso e clicca su "Svuota la cache".
3. Se ancora non appare, prova a reinstallare il modulo (dopo aver eseguito il backup del tuo negozio). Se il problema persiste, contatta il supporto MyPresta.eu.

**D: Questo modulo duplica immagini e file collegati all'interno del contenuto della pagina CMS?**
R: Sì, il modulo duplica l'intero contenuto HTML della pagina. Se le tue immagini sono collegate utilizzando percorsi relativi all'interno del contenuto, continueranno a funzionare. Se sono caricate direttamente tramite l'editor di testo ricco, i riferimenti verranno copiati. Tuttavia, il modulo non duplica i *file* immagine effettivi sul tuo server; duplica i *riferimenti* ad essi. Questo è generalmente il comportamento desiderato.

**D: Posso duplicare una categoria CMS?**
R: No, questo modulo è specificamente progettato per duplicare singole *pagine* CMS, non intere *categorie* CMS.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che desiderano comprendere, eseguire il debug o estendere il modulo "Duplica pagina CMS".

### 4.1 Panoramica dell'architettura

Il modulo "Duplica pagina CMS" è un modulo PrestaShop leggero focalizzato principalmente sull'estensione della funzionalità dell'esistente `AdminCmsController`. Sfrutta il sistema di hook di PrestaShop (`actionAdminControllerSetMedia`) per iniettare JavaScript che modifica la tabella di elenco delle pagine CMS predefinita, aggiungendo un'azione "Duplica". La logica di duplicazione principale è gestita dal file `dupcms.php` del modulo, che intercetta le richieste AJAX per eseguire le operazioni di database richieste per copiare i dati delle pagine CMS. Non introduce nuove tabelle di database o modelli di oggetti complessi, affidandosi invece alla manipolazione diretta delle tabelle esistenti `ps_cms` e `ps_cms_lang`.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. La sua funzionalità è integrata nell'esistente `AdminCmsController` tramite hook e AJAX.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce alcuna classe personalizzata o definizione di `ObjectModel`. Interagisce direttamente con le classi core di PrestaShop `CMS` e `CMSCategory` e le loro tabelle di database associate.

### 4.4 Risorse JavaScript (`views/js/`)

- **`dupcms/views/js/dupcms.js`**
  - **Ambito:** Back-office (in particolare, la pagina `AdminCms`).
  - **Responsabilità:**
    - Questo script viene iniettato nella pagina `AdminCmsController` (Migliora > Design > Pagine) tramite l'hook `actionAdminControllerSetMedia`.
    - Attende che il DOM sia pronto.
    - Identifica la colonna "Azioni" nella tabella di elenco delle pagine CMS.
    - Per ogni riga di pagina CMS, aggiunge dinamicamente un nuovo pulsante o link di azione "Duplica" al menu a discesa delle azioni esistente.
    - Allega un listener di eventi (ad esempio, `click`) a questi elementi "Duplica" appena aggiunti.
    - Quando viene cliccata un'azione "Duplica", estrae l'`id_cms` della pagina da duplicare.
    - Invia quindi una richiesta AJAX al file PHP principale del modulo (`dupcms/dupcms.php`) con l'`id_cms` e un parametro di azione (ad esempio, `action=duplicateCms`).
    - Gestisce la risposta AJAX, tipicamente visualizzando un messaggio di successo o di errore e potenzialmente aggiornando l'elenco delle pagine CMS per mostrare la pagina appena duplicata.
    - Potrebbe anche includere logica per le notifiche di aggiornamento o altri elementi UI dinamici relativi alla configurazione del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`dupcms/views/css/dupcms.css`**
  - **Ambito:** Back-office (in particolare, la pagina `AdminCms`).
  - **Responsabilità:**
    - Fornisce lo stile per il link/pulsante di azione "Duplica" aggiunto dinamicamente per garantire che si integri visivamente con il tema del Back Office di PrestaShop.
    - Può includere stili per eventuali notifiche specifiche del modulo o elementi UI all'interno del contesto `AdminCms`.
    - Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere: Cerca classi come `.dupcms-duplicate-action` o simili all'interno dell'HTML iniettato per personalizzarne l'aspetto.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non utilizza alcun file di template Smarty personalizzato (`.tpl`). Tutte le sue modifiche all'interfaccia utente nel Back Office vengono eseguite dinamicamente tramite JavaScript.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea nuove tabelle di database personalizzate.
  - Opera sulle tabelle PrestaShop esistenti:
    - `ps_cms`: Memorizza le informazioni generali della pagina CMS (stato attivo, posizione, ecc.).
    - `ps_cms_lang`: Memorizza il contenuto della pagina CMS specifico per la lingua (titolo, meta descrizione, contenuto, URL amichevole).
    - `ps_cms_shop`: Collega le pagine CMS a negozi specifici in un ambiente multishop.
    - `ps_configuration`: Memorizza le impostazioni di configurazione del modulo (ad esempio, `dupcms_ID_CMSCAT`, `mypresta_updates`).
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un controller del Back Office sta impostando i suoi media (JS/CSS). | Questo è l'hook principale utilizzato dal modulo. Inietta `dupcms.js` e `dupcms.css` nella pagina `AdminCmsController`, consentendo al modulo di modificare l'elenco delle pagine CMS e aggiungere l'azione "Duplica". |

## 5. Supporto ufficiale e aggiornamenti

Per supporto ufficiale, aggiornamenti e per scaricare l'ultima versione del modulo "Duplica pagina CMS", accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo.
