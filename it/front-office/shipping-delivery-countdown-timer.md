---
title: "Timer conto alla rovescia per la spedizione - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Timer conto alla rovescia per la spedizione' di MyPresta.eu."
sidebar:
  label: "Timer conto alla rovescia per la spedizione - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Shipping delivery countdown timer su MyPresta.eu](https://mypresta.eu/modules/front-office-features/shipping-delivery-countdown-timer.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/shipping-delivery-countdown-timer/)
>
> ---


# Timer conto alla rovescia per la spedizione

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove controlli tutti gli aspetti del timer conto alla rovescia per la spedizione.

#### Impostazioni Generali

-   **Abilitato / Disabilitato (Interruttore)**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intero modulo nel tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il timer conto alla rovescia apparirà nel tuo front office secondo le altre impostazioni.
        -   *Quando disabilitato:* Il timer conto alla rovescia non sarà visibile in nessun punto del tuo negozio.
    -   **Valore consigliato:** **Abilitato** (una volta configurato).
    -   **Scenario / esempio del commerciante:** Stai configurando il modulo per la prima volta e vuoi configurarlo completamente prima di renderlo attivo. Lo manterresti "Disabilitato" fino a quando non sei pronto, quindi lo attiveresti.

#### Visualizzazione e Design

-   **Dove vuoi visualizzare il timer? (Caselle di controllo)**

    -   **Cosa fa questa impostazione:** Questo determina le posizioni specifiche (hook) nel tuo tema PrestaShop dove verrà visualizzato il timer conto alla rovescia.
    -   **Effetto della modifica di questa impostazione:**
        -   *Spuntando una casella (es. `displayProductAdditionalInfo`):* Il timer apparirà in quella specifica area del tuo tema.
        -   *Despuntando una casella:* Il timer verrà rimosso da quella specifica area.
    -   **Valore consigliato:** Inizia con `displayProductAdditionalInfo` o `displayFooterProduct` per la visibilità sulla pagina del prodotto. Puoi sperimentare con altri come `displayNav1` o `displayReassurance` in base al tuo tema e all'impatto desiderato.
    -   **Scenario / esempio del commerciante:** Vuoi che il timer sia ben visibile sulle pagine dei prodotti. Spunteresti `displayProductAdditionalInfo` e `displayFooterProduct`. Se lo vuoi anche nell'intestazione, potresti spuntare `displayNav1`.
    -   **Opzioni disponibili:**
        -   `displayFooterProduct`
        -   `displayReassurance`
        -   `displayDeliveryTimer` (Hook personalizzato per integrazione avanzata del tema)
        -   `displayProductAdditionalInfo`
        -   `displayNav1`
-   **Quale design del modulo vuoi usare? (Pulsanti radio)**

    -   **Cosa fa questa impostazione:** Ti permette di selezionare uno stile visivo predefinito per il tuo timer conto alla rovescia. Questo include schemi di colori e layout generale.
    -   **Effetto della modifica di questa impostazione:** L'aspetto del timer conto alla rovescia nel tuo front office cambierà istantaneamente al design selezionato.
    -   **Valore consigliato:** Scegli il design che meglio si abbina al branding del tuo negozio e ai colori del tema.
    -   **Scenario / esempio del commerciante:** Il tuo negozio utilizza molto blu e bianco. Potresti selezionare "Blu 400x48" o "Blu 200x100" per assicurarti che il timer si integri perfettamente con l'estetica del tuo sito.

#### Orari limite di spedizione

-   **Ora limite di acquisto (Selettore ora)**
    -   **Cosa fa questa impostazione:** Questo è l'orario limite giornaliero entro il quale un ordine deve essere effettuato per qualificarsi per la spedizione del giorno corrente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando a 14:00:* Se un cliente ordina prima delle 14:00, il timer conta alla rovescia fino alle 14:00. Se ordina dopo le 14:00, il timer mostrerà il conto alla rovescia fino all'orario limite del giorno di spedizione successivo disponibile.
    -   **Valore consigliato:** Imposta questo al tuo effettivo orario limite di spedizione giornaliero (es. 15:00 per le 15:00).
    -   **Scenario / esempio del commerciante:** Il tuo team di magazzino elabora tutti gli ordini ricevuti entro le 16:00 per la spedizione in giornata. Imposteresti questo a `16:00`.

#### Messaggi giornalieri e disponibilità

-   **Mostra la domenica / lunedì / martedì / mercoledì / giovedì / venerdì / sabato (Caselle di controllo)**

    -   **Cosa fa questa impostazione:** Queste caselle di controllo controllano se il timer conto alla rovescia è attivo e visualizzato in giorni specifici della settimana.
    -   **Effetto della modifica di questa impostazione:**
        -   *Spuntando un giorno (es. "Mostra la domenica"):* Il timer sarà attivo e visualizzato la domenica.
        -   *Despuntando un giorno:* Il timer non verrà visualizzato in quel giorno specifico e il messaggio per quel giorno non verrà mostrato.
    -   **Valore consigliato:** Spunta tutti i giorni in cui effettivamente spedisci. Se non spedisci nei fine settimana, deseleziona sabato e domenica.
    -   **Scenario / esempio del commerciante:** La tua attività opera dal lunedì al venerdì. Spunteresti dal lunedì al venerdì e deselezioneresti sabato e domenica.
-   **Messaggio (Input di testo per ogni giorno: domenica, lunedì, martedì, mercoledì, giovedì, venerdì, sabato)**

    -   **Cosa fa questa impostazione:** Ti permette di personalizzare il messaggio visualizzato insieme al timer conto alla rovescia per ogni giorno della settimana. Puoi usare segnaposto per contenuti dinamici.
    -   **Effetto della modifica di questa impostazione:** Il testo visualizzato al cliente cambierà in base al tuo input per quel giorno specifico.
    -   **Valore consigliato:** Crea messaggi chiari e concisi. Usa segnaposto come `{time}` per il tempo rimanente e `{date}` per la data di consegna stimata.
    -   **Scenario / esempio del commerciante:**
        -   *Messaggio del lunedì:* "Ordina nelle prossime {time} per la consegna entro martedì!"
        -   *Messaggio del sabato (se non si spedisce):* "Gli ordini effettuati il sabato verranno spediti il lunedì."

#### Esclusioni/Inclusioni di prodotti e categorie

-   **Mostra solo per prodotti in stock (Interruttore)**

    -   **Cosa fa questa impostazione:** Controlla se il timer conto alla rovescia viene visualizzato solo per i prodotti attualmente in stock.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il timer apparirà solo sulle pagine dei prodotti dove il prodotto ha stock disponibile.
        -   *Quando disabilitato:* Il timer apparirà indipendentemente dallo stato dello stock (anche se potrebbe essere confuso per gli articoli esauriti).
    -   **Valore consigliato:** **Abilitato**. Ha poco senso mostrare un conto alla rovescia per la spedizione di un articolo che non può essere spedito immediatamente.
    -   **Scenario / esempio del commerciante:** Vuoi evitare di promettere spedizioni veloci per articoli che non hai. Abilitando questa opzione, il timer verrà mostrato solo per i prodotti disponibili.
-   **Escludi modulo dai prodotti selezionati / Visibilità modulo per i prodotti selezionati (Pulsanti radio)**

    -   **Cosa fa questa impostazione:** Questa è un'impostazione cruciale per definire se le seguenti selezioni di prodotti/categorie/produttori sono per *escludere* il modulo o per *includerlo* (rendendolo visibile solo per gli articoli selezionati).
    -   **Effetto della modifica di questa impostazione:**
        -   *Escludi modulo dai prodotti selezionati:* Il timer verrà mostrato ovunque *tranne* che per gli articoli che selezioni di seguito.
        -   *Visibilità modulo per i prodotti selezionati:* Il timer verrà mostrato *solo* per gli articoli che selezioni di seguito, e in nessun altro luogo.
    -   **Valore consigliato:** Dipende dalla tua strategia. Se hai alcuni prodotti specifici che non possono usare il timer, scegli "Escludi". Se vuoi il timer solo su pochi prodotti selezionati, scegli "Visibilità modulo".
    -   **Scenario / esempio del commerciante:**
        -   *Escludi:* Vendi principalmente piccoli articoli con spedizione veloce, ma anche alcuni grandi mobili che richiedono più tempo. Sceglieresti "Escludi" e poi selezioneresti i prodotti di arredamento.
        -   *Visibilità:* Stai eseguendo una promozione speciale su una categoria specifica di prodotti e vuoi che il timer appaia solo lì. Sceglieresti "Visibilità modulo" e selezioneresti quella categoria.
-   **Esclusioni/Inclusioni di prodotti (Cerca e Seleziona)**

    -   **Cosa fa questa impostazione:** Ti permette di cercare e selezionare prodotti specifici per escludere il timer o renderlo visibile solo per essi (in base all'impostazione "Escludi modulo dai prodotti selezionati" sopra).
    -   **Effetto della modifica di questa impostazione:** Aggiunge o rimuove prodotti specifici dall'elenco di esclusione/inclusione.
    -   **Valore consigliato:** Usalo per un controllo granulare sui singoli prodotti.
    -   **Scenario / esempio del commerciante:** Hai un nuovo prodotto in pre-ordine che non verrà spedito per settimane. Lo aggiungeresti all'elenco di esclusione per evitare che venga mostrato il conto alla rovescia.
-   **Esclusioni/Inclusioni di categorie (Cerca e Seleziona)**

    -   **Cosa fa questa impostazione:** Simile alle esclusioni di prodotti, ma si applica a intere categorie.
    -   **Effetto della modifica di questa impostazione:** Aggiunge o rimuove intere categorie dall'elenco di esclusione/inclusione.
    -   **Valore consigliato:** Utile per applicare regole a grandi gruppi di prodotti.
    -   **Scenario / esempio del commerciante:** Tutti i prodotti nella tua categoria "Su Misura" hanno tempi di consegna lunghi. Aggiungeresti questa categoria all'elenco di esclusione.
-   **Esclusioni/Inclusioni di produttori (Cerca e Seleziona)**

    -   **Cosa fa questa impostazione:** Simile alle esclusioni di prodotti/categorie, ma si applica ai prodotti di produttori specifici.
    -   **Effetto della modifica di questa impostazione:** Aggiunge o rimuove produttori dall'elenco di esclusione/inclusione.
    -   **Valore consigliato:** Utile se alcuni marchi hanno politiche di spedizione diverse.
    -   **Scenario / esempio del commerciante:** Uno dei tuoi fornitori è noto per spedizioni più lente. Aggiungeresti il loro produttore all'elenco di esclusione.

#### Altre impostazioni

-   **mypresta\_updates, update\_, updatev\_ (Impostazioni interne)**
    -   **Cosa fa questa impostazione:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni. Non sono destinate all'interazione diretta del commerciante.
    -   **Effetto della modifica di questa impostazione:** La modifica di queste potrebbe interferire con la capacità del modulo di controllare gli aggiornamenti.
    -   **Valore consigliato:** Lasciale così come sono.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilitato | Abilitato | Interruttore principale per la funzionalità del modulo. |
| Configurazione Modulo | Ora limite di acquisto | Il tuo orario limite di spedizione giornaliero | Definisce l'ora giornaliera entro cui un ordine deve essere effettuato per la spedizione del giorno corrente. |
| Configurazione Modulo | Dove vuoi visualizzare il timer? | `displayProductAdditionalInfo`, `displayFooterProduct` | Seleziona le posizioni del tema per il timer. |
| Configurazione Modulo | Quale design del modulo vuoi usare? | Corrisponde al tuo tema | Stile visivo del timer conto alla rovescia. |
| Configurazione Modulo | Mostra la domenica/lunedì/.../sabato | Spunta tutti i giorni di spedizione | Controlla in quali giorni il timer è attivo. |
| Configurazione Modulo | Messaggio (per ogni giorno) | "Ordina nelle prossime {time} per la consegna entro {date}!" | Testo personalizzabile visualizzato con il timer. |
| Configurazione Modulo | Mostra solo per prodotti in stock | Abilitato | Il timer appare solo per i prodotti con stock disponibile. |
| Configurazione Modulo | Escludi modulo dai prodotti selezionati / Visibilità modulo per i prodotti selezionati | Dipende dalla strategia | Definisce se le selezioni sono per esclusione o inclusione. |
| Configurazione Modulo | Esclusioni/Inclusioni di prodotti | Vuoto | Seleziona prodotti specifici da includere/escludere. |
| Configurazione Modulo | Esclusioni/Inclusioni di categorie | Vuoto | Seleziona categorie specifiche da includere/escludere. |
| Configurazione Modulo | Esclusioni/Inclusioni di produttori | Vuoto | Seleziona produttori specifici da includere/escludere. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il timer non appare nel mio negozio, o appare nel posto sbagliato.**
R1:

-   **Controlla lo stato del modulo:** Innanzitutto, assicurati che il modulo sia "Abilitato" nella pagina di configurazione.
-   **Controlla la selezione degli hook:** Verifica di aver selezionato le caselle di controllo corrette in "Dove vuoi visualizzare il timer?". Se il tuo tema è fortemente personalizzato, alcuni hook standard potrebbero non essere renderizzati, oppure potresti dover utilizzare un hook diverso.
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte PrestaShop memorizza nella cache vecchie posizioni dei moduli.
-   **Compatibilità del tema:** Se il tuo tema è altamente personalizzato, potrebbe non implementare gli hook standard di PrestaShop nel modo usuale. Potrebbe essere necessario consultare lo sviluppatore del tuo tema o un webmaster per inserire manualmente l'hook `displayDeliveryTimer` nei file `.tpl` del tuo tema.

**D2: Il messaggio del conto alla rovescia è errato, o l'orario limite sembra sbagliato.**
R2:

-   **Verifica "Ora limite di acquisto":** Ricontrolla che l'"Ora limite di acquisto" sia impostata correttamente all'orario limite di spedizione giornaliero.
-   **Controlla i messaggi giornalieri:** Assicurati che il "Messaggio" per il giorno della settimana corrente sia configurato correttamente e abbia senso.
-   **Fuso orario del server:** Assicurati che il fuso orario del server del tuo negozio PrestaShop sia configurato correttamente. Se l'ora del server è sbagliata, il conto alla rovescia sarà impreciso. Puoi verificarlo in **Parametri avanzati > Informazioni di configurazione** o con il tuo provider di hosting.

**D3: Il timer viene mostrato per i prodotti esauriti.**
R3:

-   **Impostazione "Mostra solo per prodotti in stock":** Assicurati che l'interruttore "Mostra solo per prodotti in stock" sia impostato su **Abilitato** nella configurazione del modulo. Se è disabilitato, il timer apparirà indipendentemente dallo stato dello stock.

**D4: Voglio cambiare i colori o i font del timer oltre i design preimpostati.**
R4:

-   Il modulo fornisce diversi design predefiniti. Per una personalizzazione più profonda (es. font specifici, codici colore esatti non disponibili nei design), avrai bisogno di un webmaster o uno sviluppatore. Possono sovrascrivere gli stili CSS del modulo aggiungendo CSS personalizzato al foglio di stile del tuo tema. Fai riferimento alla Sezione 7.5 per i dettagli sui file CSS.

**D5: Il timer non viene tradotto in altre lingue.**
R5:

-   Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
-   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi seleziona "Timer conto alla rovescia per la spedizione" dal menu a discesa del modulo.
-   Potrai quindi tradurre tutti i messaggi giornalieri e le altre stringhe del modulo nelle lingue desiderate.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `Timer conto alla rovescia per la spedizione` (`deliverycountdown`) è un modulo PrestaShop standard che segue un modello simile a MVC all'interno dell'ambito del modulo. Estende principalmente `Module` e sfrutta il sistema di hook di PrestaShop per iniettare il suo contenuto e la sua funzionalità nel front office. La configurazione è gestita tramite il metodo `getContent()`, memorizzando le impostazioni in `ps_configuration`. La visualizzazione del front office si basa su template Smarty e un file JavaScript dedicato per la logica del conto alla rovescia.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office personalizzati. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo. Il rendering del front office è ottenuto direttamente tramite hook e template associati.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate o `ObjectModel` nella directory `classes/`. Tutti i dati sono memorizzati direttamente in `ps_configuration` utilizzando chiavi di configurazione.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`deliverycountdown/views/js/deliverycountdown.js`**
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo è il file JavaScript principale responsabile della logica del conto alla rovescia.
    -   **Dettagli:**
        -   Probabilmente inizializza un timer conto alla rovescia su elementi identificati da specifiche classi o ID CSS.
        -   Calcola il tempo rimanente fino all'"Ora limite di acquisto" per il giorno corrente o il giorno di spedizione successivo disponibile.
        -   Aggiorna dinamicamente il tempo visualizzato (ore, minuti, secondi) nel template del front office.
        -   Gestisce la transizione dei messaggi quando viene raggiunto l'orario limite (es. cambiando da "Ordina in X tempo" a "Gli ordini effettuati ora verranno spediti domani").
        -   Potrebbe utilizzare `setInterval` o `setTimeout` per aggiornamenti in tempo reale.
        -   Probabilmente legge i valori di configurazione (come l'orario limite, i messaggi giornalieri e i giorni abilitati) passati dal template Smarty o da JavaScript inline.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include un file CSS di base e diversi file CSS specifici per il tema per diversi design visivi.

-   **`deliverycountdown/views/css/deliverycountdown.css`**

    -   **Ambito:** Front-office.
    -   **Responsabilità:** Contiene lo stile strutturale fondamentale e predefinito per il timer conto alla rovescia. Questo include il layout di base, le dimensioni dei font e gli elementi comuni condivisi tra tutti i design.
    -   **Selettori chiave:** Gli sviluppatori possono ispezionare l'output HTML del timer per identificare classi come `.deliverycountdown-container`, `.deliverycountdown-message`, `.deliverycountdown-timer`, ecc., per sovrascrivere gli stili nel file `custom.css` o `theme.css` del loro tema.
-   **`deliverycountdown/views/css/deliverycountdown-{colore}-{dimensione}.css`** (es. `deliverycountdown-black-200x100.css`, `deliverycountdown-blue-400x48.css`)

    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questi file forniscono gli schemi di colore specifici, le immagini di sfondo (se presenti) e le regolazioni delle dimensioni per le diverse opzioni di design selezionate nel back office. Tipicamente sovrascrivono o estendono gli stili definiti in `deliverycountdown.css`.
    -   **Selettori chiave:** Questi file mireranno agli stessi selettori core ma applicheranno `background-color`, `color`, `width`, `height`, `border`, ecc. specifici per ottenere lo stile visivo scelto.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:

    -   **`deliverycountdown/views/hook/displayFooterProduct.tpl`**
        -   **Hook:** `displayFooterProduct` (e potenzialmente altri come `displayProductAdditionalInfo`, `displayReassurance`, `displayNav1`, `displayDeliveryTimer` se configurati).
        -   **Scopo:** Questo è il template principale responsabile del rendering della struttura HTML del timer conto alla rovescia e del suo messaggio associato nel front office.
        -   **Contenuto:**
            -   Conterrà gli elementi `div` principali per il contenitore del timer.
            -   Visualizzerà il messaggio dinamico (es. "Ordina nelle prossime...") e le cifre del conto alla rovescia.
            -   Probabilmente passerà le variabili di configurazione necessarie (come l'orario limite, i messaggi giornalieri, i giorni abilitati, lo stato dello stock del prodotto corrente, le regole di esclusione/inclusione) allo script `deliverycountdown.js`, tramite attributi di dati o tag `<script>` inline.
            -   Include il file CSS di design selezionato e lo script `deliverycountdown.js`.
-   **Template di amministrazione (`views/templates/admin/`)**:

    -   **`deliverycountdown/views/admin/datepicker.tpl`**
        -   **Scopo:** Probabilmente un template riutilizzabile per il rendering di un campo di input per la selezione della data nella configurazione del back-office del modulo. (Anche se non esplicitamente utilizzato per le date nella configurazione attuale, potrebbe essere un componente di libreria).
    -   **`deliverycountdown/views/admin/selectedExcludedProducts.tpl`**
        -   **Scopo:** Rende l'elenco dei prodotti che sono stati selezionati per l'esclusione o l'inclusione nella configurazione del modulo. Questo fa parte dell'interfaccia di selezione di prodotti/categorie/produttori.
    -   **`deliverycountdown/views/admin/selectedProducts.tpl`**
        -   **Scopo:** Simile a `selectedExcludedProducts.tpl`, ma potenzialmente per un contesto di selezione diverso (es. se ci fossero elenchi separati di inclusione ed esclusione).
    -   **`deliverycountdown/views/admin/timepicker.tpl`**
        -   **Scopo:** Rende il campo di input per la selezione dell'ora utilizzato per impostare l'"Ora limite di acquisto" nella configurazione del back-office.
-   **Template di libreria (`deliverycountdown/lib/searchTool/views/scripts.tpl`)**:

    -   **`deliverycountdown/lib/searchTool/views/scripts.tpl`**
        -   **Scopo:** Probabilmente contiene logica JavaScript o Smarty relativa allo strumento di ricerca e selezione di prodotti/categorie/produttori utilizzato nella configurazione del modulo. Questo script facilita la ricerca basata su AJAX e la visualizzazione degli elementi selezionati.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella standard di PrestaShop `ps_configuration`.
    -   **Record di configurazione chiave (esempi):**
        -   `DC_LAYOUT`: Memorizza il layout di design selezionato (es. 'black-200x100').
        -   `DC_SUNDAY_MSG`, `DC_MONDAY_MSG`, ecc.: Memorizza il messaggio personalizzato per ogni giorno.
        -   `DC_TIME`: Memorizza l'"Ora limite di acquisto" (es. '16:00').
        -   `DC_EXCL`: Booleano per la regola di esclusione (0 o 1).
        -   `DC_INSTOCK`: Booleano per "Mostra solo per prodotti in stock".
        -   `dc_exclusions_products`, `dc_exclusions_cat`, `DC_EXCL_MANUF`: Elenchi JSON o separati da virgole di ID per entità escluse/incluse.
        -   `DC_SUNDAY`, `DC_MONDAY`, ecc.: Booleani per abilitare/disabilitare il timer in giorni specifici.
        -   `DC_HOOK_displayFooterProduct`, `DC_HOOK_displayReassurance`, ecc.: Booleani che indicano quali hook sono abilitati per la visualizzazione.
-   **Tabella degli hook registrati**:

| Nome Hook | Ambito | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | Nella sezione `<head>` di ogni pagina. | Utilizzato per caricare le risorse CSS e JS del modulo a livello globale, o per la visualizzazione del timer a livello di sito. |
| `displayNav1` | Front-office | Tipicamente nella barra di navigazione superiore. | Visualizza il timer nell'area di navigazione principale. |
| `displayNav2` | Front-office | Spesso in una barra di navigazione secondaria o link di utilità. | Visualizza il timer in un'area di navigazione secondaria. |
| `displayTop` | Front-office | Nella sezione dell'intestazione principale, sotto `displayNav`. | Visualizza il timer nell'intestazione principale. |
| `displayProductAdditionalInfo` | Front-office | Sulla pagina del prodotto, spesso vicino al pulsante "Aggiungi al carrello". | Posizionamento strategico per l'urgenza specifica del prodotto. |
| `displayFooterProduct` | Front-office | Sulla pagina del prodotto, tipicamente sotto la descrizione o i dettagli del prodotto. | Un altro posizionamento specifico del prodotto per l'urgenza. |
| `displayReassurance` | Front-office | In un blocco di rassicurazione (se il tema lo supporta), spesso sotto le informazioni del prodotto. | Integra il timer con altri elementi che costruiscono fiducia. |
| `displayDeliveryTimer` | Front-office | Hook personalizzato. | Consente agli sviluppatori di temi di posizionare il timer con precisione ovunque nel tema. |
| `actionAdminControllerSetMedia` | Back-office | Quando un controller admin carica le sue risorse multimediali. | Utilizzato per caricare CSS/JS specifici del modulo per la pagina di configurazione del back-office (es. per lo strumento di ricerca, il selettore dell'ora). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Timer conto alla rovescia per la spedizione", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
