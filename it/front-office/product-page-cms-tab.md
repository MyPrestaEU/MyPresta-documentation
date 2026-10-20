---
title: "Scheda CMS pagina prodotto - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Scheda CMS pagina prodotto' di MyPresta.eu."
sidebar:
  label: "Scheda CMS pagina prodotto - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product page CMS tab su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-cms-tab.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-page-cms-tab/)
>
> ---


# Scheda CMS pagina prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili per impostazione predefinita sulla maggior parte degli ambienti di hosting. Nessuna estensione speciale o insolita è necessaria per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Scheda CMS pagina prodotto" nel tuo Gestione moduli. Questo ti porterà alla schermata di configurazione principale.

#### **Seleziona la pagina CMS da visualizzare come scheda**

Questa è l'impostazione principale del modulo. Determina quale delle tue pagine CMS esistenti verrà visualizzata come nuova scheda su tutte le pagine prodotto.

- **Cosa fa questa impostazione:** Questo menu a discesa elenca tutte le pagine CMS che hai creato nel tuo negozio PrestaShop (trovate sotto **Design > Pagine** o **Design > CMS** nelle versioni precedenti). Devi selezionare una di queste pagine.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene selezionata una pagina CMS:* Una nuova scheda apparirà su ogni pagina prodotto del tuo negozio. Il titolo di questa scheda sarà il titolo della pagina CMS selezionata e il contenuto visualizzato quando si clicca sulla scheda sarà il contenuto di quella pagina CMS.
  - *Quando viene scelto "--- Seleziona ---":* Nessuna nuova scheda apparirà sulle pagine prodotto. Il modulo sarà effettivamente inattivo in termini di visualizzazione front-office.
- **Valore consigliato:** Seleziona la pagina CMS che contiene informazioni che desideri condividere universalmente su tutte le tue pagine prodotto (ad esempio, una pagina "Informazioni sulla spedizione", "Guida alle taglie" o "Dettagli sulla garanzia").
- **Scenario / esempio del commerciante:** Desideri fornire una "Guida alle taglie" dettagliata per tutti i prodotti di abbigliamento. Per prima cosa creeresti una pagina CMS intitolata "Guida alle taglie" con tutte le informazioni pertinenti. Quindi, nella configurazione di questo modulo, selezioneresti "Guida alle taglie" dal menu a discesa. Ora, ogni pagina prodotto avrà una scheda "Guida alle taglie".

#### **Tipo di scheda**

Questa impostazione controlla come il modulo si integra con il sistema di schede di PrestaShop, specialmente per le diverse versioni di PrestaShop.

- **Cosa fa questa impostazione:** Questo menu a discesa ti consente di scegliere il metodo che il modulo utilizza per visualizzare la scheda. È principalmente un'impostazione di compatibilità per le diverse versioni di PrestaShop.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene selezionato "PrestaShop 1.7 / 8.x / 9.x":* Il modulo utilizzerà l'hook `displayProductExtraContent`, che è il modo standard e consigliato per aggiungere nuove schede nelle versioni moderne di PrestaShop. Questo garantisce un aspetto e una sensazione nativi.
  - *Quando viene selezionato "PrestaShop 1.6":* Il modulo utilizzerà hook più vecchi come `productTab` e `productTabContent`, che erano standard in PrestaShop 1.6. Questa opzione è per la compatibilità con le versioni precedenti se stai eseguendo un negozio PrestaShop 1.6 più vecchio e non supportato (anche se il modulo è ufficialmente per 1.7+).
- **Valore consigliato:** Per i negozi PrestaShop 1.7, 8.x e 9.x, seleziona sempre **"PrestaShop 1.7 / 8.x / 9.x"**.
- **Scenario / esempio del commerciante:** Se stai eseguendo PrestaShop 8.1, selezioneresti "PrestaShop 1.7 / 8.x / 9.x" per assicurarti che la scheda venga visualizzata correttamente e si integri perfettamente con il design del tuo tema. Se, per qualche motivo, stessi utilizzando questo modulo su un vecchio negozio PrestaShop 1.6, selezioneresti "PrestaShop 1.6".

#### **Aggiornamenti in tempo reale MyPresta.eu**

Questa sezione è comune a tutti i moduli MyPresta.eu e ti aiuta a gestire gli aggiornamenti del modulo.

- **Cosa fa questa impostazione:** Questa funzione controlla la disponibilità di nuove versioni del modulo direttamente da MyPresta.eu.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Il modulo controllerà periodicamente la disponibilità di aggiornamenti. Se è disponibile una nuova versione, vedrai una notifica nell'elenco dei moduli o nella pagina di configurazione del modulo. Questo ti aiuta a rimanere aggiornato con correzioni di bug e nuove funzionalità.
  - *Quando disabilitato:* Il modulo non controllerà automaticamente la disponibilità di aggiornamenti. Dovrai controllare manualmente il tuo account MyPresta.eu per nuove versioni.
- **Valore consigliato:** **SÌ**. Mantenere i moduli aggiornati è fondamentale per la sicurezza, la compatibilità e l'accesso alle ultime funzionalità.
- **Scenario / esempio del commerciante:** Vuoi assicurarti che il tuo modulo abbia sempre le ultime patch di sicurezza. Abilitando questa opzione, riceverai una notifica quando è disponibile un aggiornamento, invitandoti a scaricarlo e installarlo.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | **Seleziona la pagina CMS da visualizzare come scheda** | --- Seleziona --- / La tua pagina CMS scelta | Determina quale contenuto della pagina CMS appare come nuova scheda su tutte le pagine prodotto. |
| Pagina di configurazione del modulo | **Tipo di scheda** | PrestaShop 1.7 / 8.x / 9.x | Assicura la corretta visualizzazione della scheda e l'integrazione con l'architettura della tua versione di PrestaShop. |
| Pagina di configurazione del modulo | **Aggiornamenti in tempo reale MyPresta.eu** | SÌ | Abilita i controlli automatici per gli aggiornamenti del modulo da MyPresta.eu. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: La nuova scheda non viene visualizzata sulle mie pagine prodotto. Cosa devo fare?**
R:

1.  **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli**, trova "Scheda CMS pagina prodotto" e clicca su "Configura". Assicurati di aver selezionato una pagina CMS valida dal menu a discesa "Seleziona la pagina CMS da visualizzare come scheda". Se è selezionato "--- Seleziona ---", non apparirà alcuna scheda.
2.  **Controlla il tipo di scheda:** Assicurati che "Tipo di scheda" sia impostato su "PrestaShop 1.7 / 8.x / 9.x" per le versioni moderne di PrestaShop.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, la cache di PrestaShop impedisce che le modifiche appaiano immediatamente.
4.  **Controlla lo stato della pagina CMS:** Assicurati che la pagina CMS selezionata sia attiva e visibile pubblicamente (non disabilitata o impostata come privata). Puoi verificarlo in **Design > Pagine**.
5.  **Compatibilità del tema:** Sebbene il modulo utilizzi gli hook standard di PrestaShop, i temi molto personalizzati potrebbero a volte interferire. Se i passaggi precedenti non funzionano, passa temporaneamente al tema predefinito di PrestaShop per vedere se la scheda appare. Se lo fa, il tuo tema potrebbe richiedere una piccola modifica.

**D: Posso avere diverse schede CMS per diversi prodotti?**
R: Questo modulo è progettato per visualizzare *una specifica pagina CMS* come scheda su *tutte* le pagine prodotto. Non supporta l'assegnazione di diverse pagine CMS a singoli prodotti. Se hai bisogno di schede specifiche per prodotto, in genere avresti bisogno di un modulo più avanzato o di uno sviluppo personalizzato.

**D: Il contenuto della scheda appare strano o senza stile.**
R: Il modulo estrae semplicemente il contenuto dalla tua pagina CMS. Lo stile di questo contenuto è solitamente gestito dal CSS del tuo tema PrestaShop.

1.  **Controlla il contenuto della pagina CMS:** Assicurati che il contenuto della tua pagina CMS originale (sotto **Design > Pagine**) sia formattato correttamente e non contenga HTML rotto.
2.  **CSS del tema:** Il CSS del tuo tema potrebbe non avere stili specifici per il contenuto all'interno delle schede prodotto, oppure potrebbe sovrascrivere gli stili predefiniti. Se hai uno sviluppatore web, può ispezionare la pagina per identificare e risolvere eventuali conflitti di stile.

**D: Ho aggiornato la mia pagina CMS, ma il contenuto della scheda sulle pagine prodotto non è cambiato.**
R: Dopo aver aggiornato una pagina CMS, svuota sempre la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**). Il tuo negozio potrebbe servire una versione più vecchia e memorizzata nella cache del contenuto.

**D: Come traduco il titolo della scheda se il mio negozio è multilingue?**
R: Il titolo della scheda viene automaticamente preso dal titolo della pagina CMS selezionata. Per tradurlo, devi modificare la pagina CMS stessa (**Design > Pagine**) e fornire le traduzioni per il suo titolo e contenuto per ogni lingua che supporti. Il modulo visualizzerà quindi il titolo tradotto corretto in base alla lingua selezionata dal cliente.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Scheda CMS pagina prodotto" (`cmstab`) è un modulo PrestaShop leggero progettato per iniettare il contenuto di una pagina CMS esistente nelle pagine prodotto come nuova scheda. Per raggiungere questo obiettivo, sfrutta principalmente il sistema di hook di PrestaShop. La logica principale del modulo risiede nel suo file PHP principale, `cmstab.php`, che gestisce l'installazione, la disinstallazione, la configurazione e la registrazione degli hook. Non introduce tabelle di database personalizzate o ObjectModels complessi, affidandosi invece alla classe `CMS` nativa di PrestaShop per il recupero dei contenuti. Il modulo fornisce due set di template per garantire la compatibilità con i meccanismi di rendering delle schede sia di PrestaShop 1.6 che di 1.7+, selezionabili tramite la configurazione del back-office.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller amministrativo o front-office personalizzato. Tutte le funzionalità sono gestite tramite la classe principale del modulo e il sistema di hook di PrestaShop.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce classi o ObjectModels personalizzati nella directory `classes/`. Utilizza direttamente la classe `CMS` principale di PrestaShop per recuperare i contenuti in base all'ID della pagina CMS configurata.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`cmstab/trusted.js`**
    -   **Ambito:** Back-office (pagina di configurazione del modulo).
    -   **Scopo:** Questo script è tipicamente incluso nei moduli MyPresta.eu per gestire la funzionalità "Aggiornamenti in tempo reale MyPresta.eu". Comunica con l'API di MyPresta.eu per verificare la disponibilità di nuove versioni del modulo e visualizzare le notifiche di aggiornamento all'interno del back office di PrestaShop. Non influisce sulla visualizzazione del front-office o sull'interazione con il cliente.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Lo stile della scheda e del suo contenuto è ereditato dal tema PrestaShop attivo. Gli sviluppatori che desiderano stilizzare la scheda dovrebbero mirare ai selettori appropriati forniti dal tema o dal sistema di schede principale di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo fornisce due set di template per adattarsi ai diversi approcci di rendering delle schede delle versioni di PrestaShop. Il set specifico utilizzato è determinato dall'impostazione "Tipo di scheda" nella configurazione del modulo.

-   **Template degli hook (`views/templates/hook/`)**: Questa directory non è esplicitamente utilizzata per il rendering diretto degli hook in questo modulo. I template sono direttamente referenziati da `views/front/`.
-   **Template del front-office (`views/templates/front/`)**:

    -   **`cmstab/views/front/tab.tpl`**
        -   **Scopo:** Questo template è progettato per la compatibilità con PrestaShop 1.6. Viene renderizzato quando il "Tipo di scheda" è impostato su "PrestaShop 1.6". Produce l'HTML per l'*intestazione* della scheda (la parte cliccabile della scheda) utilizzando il titolo della pagina CMS.
        -   **Hook:** `productTab` (specifico di PrestaShop 1.6)
        -   **Variabili:** `$cmstab_title` (il titolo della pagina CMS selezionata).
    -   **`cmstab/views/front/tab16.tpl`**
        -   **Scopo:** Questo template è anch'esso per la compatibilità con PrestaShop 1.6. Produce l'HTML per l'area del *contenuto* della scheda, visualizzando il contenuto effettivo della pagina CMS selezionata.
        -   **Hook:** `productTabContent` (specifico di PrestaShop 1.6)
        -   **Variabili:** `$cmstab_content` (il contenuto HTML della pagina CMS selezionata).
    -   **`cmstab/views/front/tabcontents.tpl`**
        -   **Scopo:** Questo template è per la compatibilità con PrestaShop 1.7, 8.x e 9.x. Viene renderizzato quando il "Tipo di scheda" è impostato su "PrestaShop 1.7 / 8.x / 9.x". Produce l'intera struttura della scheda, inclusi sia l'intestazione della scheda che il suo contenuto, come previsto dall'hook `displayProductExtraContent`.
        -   **Hook:** `displayProductExtraContent` (standard di PrestaShop 1.7+)
        -   **Variabili:**
            -   `$cmstab_title`: Il titolo della pagina CMS selezionata.
            -   `$cmstab_content`: Il contenuto HTML della pagina CMS selezionata.
            -   `$cmstab_id`: Un ID univoco per la scheda, derivato dall'ID della pagina CMS.
    -   **`cmstab/views/front/tabcontents16.tpl`**
        -   **Scopo:** Questo template sembra essere una versione ridondante o alternativa di `tab16.tpl` o `tabcontents.tpl`, probabilmente per scenari specifici di 1.6 o un'implementazione più vecchia. Data la logica attuale del modulo, `tabcontents.tpl` è usato per 1.7+ e `tab.tpl`/`tab16.tpl` per 1.6. Gli sviluppatori dovrebbero concentrarsi principalmente su `tabcontents.tpl` per le versioni moderne di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   Questo modulo non crea tabelle di database personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop:
        -   `CMSTAB_ID`: Memorizza l'ID della pagina CMS selezionata.
        -   `CMSTAB_TYPE`: Memorizza il tipo di scheda selezionato (es. '17' per PrestaShop 1.7+, '16' per PrestaShop 1.6).
        -   `MYPRESTA_UPDATES`: Memorizza l'impostazione per gli aggiornamenti in tempo reale.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato dal modulo per registrare il suo JavaScript per gli aggiornamenti in tempo reale nel back office. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del back-office. | Utilizzato dal modulo per registrare il suo JavaScript per gli aggiornamenti in tempo reale nel back office. |
| `displayProductExtraContent` | Nelle pagine prodotto, per aggiungere nuove schede (PrestaShop 1.7+). | Hook principale per il rendering della scheda CMS e del suo contenuto nelle versioni moderne di PrestaShop. |
| `productTab` | Nelle pagine prodotto, per aggiungere nuove intestazioni di scheda (PrestaShop 1.6). | Utilizzato per la compatibilità con le versioni precedenti per renderizzare l'intestazione della scheda su PrestaShop 1.6. |
| `productTabContent` | Nelle pagine prodotto, per aggiungere nuovo contenuto di scheda (PrestaShop 1.6). | Utilizzato per la compatibilità con le versioni precedenti per renderizzare il contenuto della scheda su PrestaShop 1.6. |
| `actionAdminControllerSetMedia` | Quando un controller amministrativo imposta le sue risorse multimediali. | Utilizzato dal modulo per registrare il suo JavaScript per gli aggiornamenti in tempo reale nel back office. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto professionale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza tempestiva e a garantire le prestazioni ottimali dei tuoi moduli.
