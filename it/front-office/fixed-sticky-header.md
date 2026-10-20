---
title: "Intestazione fissa adesiva - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Intestazione fissa adesiva di MyPresta.eu."
sidebar:
  label: "Intestazione fissa adesiva - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Fixed sticky header su MyPresta.eu](https://mypresta.eu/modules/front-office-features/fixed-sticky-header.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/fixed-sticky-header/)
>
> ---


# Intestazione fissa adesiva

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Il modulo funziona con i template default-bootstrap e classic e con tutti i temi con struttura simile.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, fai clic su "Configura" accanto al modulo "Intestazione fissa adesiva" nel tuo Gestione moduli. Questo ti porterà alla pagina di configurazione principale del modulo.

#### Impostazioni generali

-   **Cosa fa questa impostazione:** Questa sezione include tipicamente le impostazioni standard del modulo MyPresta.eu relative agli aggiornamenti e al supporto.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Consente al modulo di verificare la disponibilità di aggiornamenti da MyPresta.eu e potenzialmente visualizzare notifiche nel tuo Back Office. Ciò garantisce che tu stia sempre utilizzando la versione più recente, sicura e ricca di funzionalità del modulo.
    -   *Quando disabilitato:* Il modulo non controllerà automaticamente gli aggiornamenti. Dovresti controllare manualmente le nuove versioni accedendo al tuo account MyPresta.eu.
-   **Valore consigliato:** **SÌ** (o abilitato). Mantenere questa impostazione attiva è altamente consigliato per assicurarti di ricevere aggiornamenti tempestivi e correzioni di bug, che sono cruciali per la sicurezza e la compatibilità con le future versioni di PrestaShop.
-   **Scenario / esempio del commerciante:** Vuoi essere avvisato se viene rilasciata una nuova versione del modulo che corregge un bug o aggiunge una nuova funzionalità. Mantenere questa opzione abilitata ti assicura di essere sempre informato.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Controlli aggiornamenti (mypresta\_updates, update\_, updatev\_) | Abilitato | Consente al modulo di controllare e notificarti gli aggiornamenti disponibili da MyPresta.eu, garantendo che tu abbia le ultime funzionalità e correzioni di sicurezza. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: L'intestazione non si attacca o si sovrappone ad altri elementi. Cosa devo fare?**
R1: Questo accade spesso a causa di conflitti con il CSS o JavaScript del tuo tema, specialmente se il tuo tema ha una struttura di intestazione molto personalizzata.
\* **Svuota la cache:** Per prima cosa, prova a svuotare la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota la cache" in alto a destra.
\* **Compatibilità del tema:** Il modulo è progettato per funzionare con i temi PrestaShop standard (come Classic) e temi con strutture simili. Se hai un tema fortemente personalizzato, potrebbero essere necessarie piccole modifiche CSS.
\* **Contatta il supporto:** Se il problema persiste, raccogli screenshot e dettagli sul tuo tema e contatta il supporto MyPresta.eu. Possono aiutarti a diagnosticare e fornire snippet CSS personalizzati se necessario.

**D2: La mia intestazione appare strana o ha spazio extra quando diventa adesiva.**
R2: Questo può essere un problema di stile.
\* **Ispeziona elemento:** Usa gli strumenti per sviluppatori del tuo browser (fai clic con il tasto destro sull'intestazione e seleziona "Ispeziona") per vedere quali regole CSS vengono applicate. Cerca `position: fixed;` e `top: 0;`.
\* **Stile del tema:** Il tuo tema potrebbe avere regole specifiche di padding o margin che entrano in conflitto. Potrebbe essere necessario aggiungere CSS personalizzato per regolare l'aspetto dell'intestazione adesiva. Il supporto MyPresta.eu può guidarti.

**D3: Questo modulo rallenterà il mio sito web?**
R3: Il modulo "Intestazione fissa adesiva" è molto leggero, utilizzando JavaScript e CSS minimi. Dovrebbe avere un impatto trascurabile sulla velocità di caricamento e sulle prestazioni del tuo sito web. L'effetto viene attivato solo allo scorrimento, quindi non aggiunge overhead al caricamento iniziale della pagina.

**D4: Come traduco il modulo se avesse del testo visibile?**
R4: Sebbene questo modulo fornisca principalmente un effetto visivo e non abbia tipicamente testo rivolto all'utente, se una versione futura introducesse testo configurabile, lo tradurresti tramite:
\* **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
\* Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi seleziona "Intestazione fissa adesiva" dal menu a discesa del modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Intestazione fissa adesiva" è un modulo leggero per le funzionalità del front-office progettato per migliorare l'esperienza utente rendendo l'intestazione principale adesiva allo scorrimento. Sfrutta principalmente JavaScript per rilevare gli eventi di scorrimento e applicare classi CSS all'elemento dell'intestazione, che poi attiva lo stile `position: fixed`. Aderisce alla struttura standard del modulo PrestaShop, utilizzando l'hook `displayHeader` per iniettare le sue risorse.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. La funzionalità del modulo è interamente gestita tramite JavaScript iniettato tramite un hook.
-   **Controller Admin Back-Office**: Nessuno. La configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Non vengono utilizzate classi personalizzate o definizioni `ObjectModel`. Il modulo opera manipolando gli elementi DOM esistenti.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`fixedheader/fixedheader.js`**
    -   **Ambito:** Front-office.
    -   **Scopo:** Questo script è responsabile della funzionalità principale dell'intestazione adesiva.
    -   **Dettagli:**
        -   Ascolta l'evento `scroll` sull'oggetto `window`.
        -   Determina la posizione di scorrimento e l'offset iniziale dell'elemento dell'intestazione.
        -   Quando l'utente scorre oltre una certa soglia (l'altezza iniziale dell'intestazione), aggiunge una classe CSS specifica (ad esempio, `fixed-header-active` o simile, come definito in `fixedheader.css`) al contenitore principale dell'intestazione.
        -   Quando l'utente scorre di nuovo sopra la soglia, rimuove questa classe.
        -   Probabilmente mira a un selettore di intestazione comune (ad esempio, `#header`, `.header-container`, o simile, a seconda della struttura del tema) per applicare il comportamento adesivo.
        -   Potrebbe anche gestire l'aggiunta di un `padding-top` al `body` o a un wrapper del contenuto principale per evitare che il contenuto "salti" o venga nascosto dietro l'intestazione fissa.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`fixedheader/fixedheader.css`**
    -   **Ambito:** Stile del cliente del front-office.
    -   **Scopo:** Fornisce le regole CSS necessarie per rendere l'intestazione adesiva quando JavaScript aggiunge la classe di attivazione.
    -   **Dettagli:**
        -   Definisce gli stili per lo stato attivo dell'intestazione adesiva. Le proprietà chiave includeranno:
            -   `position: fixed;`
            -   `top: 0;`
            -   `width: 100%;`
            -   `z-index: 1000;` (o un valore alto per assicurarsi che rimanga sopra altri contenuti).
            -   Potenzialmente `box-shadow` o `background-color` per distinguere visivamente l'intestazione adesiva.
        -   Potrebbe anche includere regole per gestire il padding o il margin del `body` per prevenire la sovrapposizione del contenuto.
        -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** La classe primaria aggiunta dal JS (ad esempio, `.fixed-header-active` o simile) e il selettore per l'elemento dell'intestazione stesso (ad esempio, `#header`, `.header-container`). Gli sviluppatori possono sovrascrivere questi stili nel CSS personalizzato del loro tema per adattarli al loro design.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   Non vengono utilizzati file `.tpl` personalizzati. Il modulo inietta il suo JavaScript e CSS direttamente nella sezione `<head>` tramite l'hook `displayHeader`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Non vengono create tabelle del database personalizzate. La configurazione è memorizzata in `ps_configuration` utilizzando chiavi come `MYPRESTA_UPDATES`, `UPDATE_FIXEDHEADER`, `UPDATEV_FIXEDHEADER`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS (`fixedheader.css`) e JavaScript (`fixedheader.js`) del modulo nella pagina, assicurando che vengano caricati prima che il contenuto della pagina venga renderizzato e siano disponibili per l'esecuzione immediata. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "Intestazione fissa adesiva", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla compatibilità del modulo.
"""
