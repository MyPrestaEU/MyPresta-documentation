---
title: "Prezzo al dettaglio suggerito/raccomandato dal produttore (MSRP) - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo Prezzo al dettaglio suggerito/raccomandato dal produttore (MSRP) di MyPresta.eu."
sidebar:
  label: "Prezzo al dettaglio suggerito/raccomandato dal produttore (MSRP) - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Manufacturer suggested / recommended retail price (MSRP) su MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturer-suggested-recommended-retail-price-msrp.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/manufacturer-suggested-recommended-retail-price-msrp/)
>
> ---


# Prezzo al dettaglio suggerito/raccomandato dal produttore (MSRP)

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo MSRP, accessibile dopo l'installazione cliccando sul pulsante "Configura". Qui definirai come gli MSRP vengono visualizzati e gestiti in tutto il tuo negozio.

#### **Abilita visualizzazione MSRP**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzione MSRP per l'intero negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo inizierà a visualizzare le informazioni MSRP sulle tue pagine prodotto e negli elenchi dei prodotti, a condizione che tu abbia inserito gli MSRP per i tuoi prodotti.
    -   *Quando disabilitato (NO):* La funzione MSRP sarà completamente inattiva e nessuna informazione MSRP sarà mostrata ai clienti, anche se hai inserito dei valori.
-   **Valore consigliato:** SÌ (per utilizzare le funzionalità del modulo).
-   **Scenario/esempio del commerciante:** Se stai configurando il modulo per la prima volta, abilitalo per vedere le modifiche. Se hai bisogno di nascondere temporaneamente gli MSRP per una promozione o una manutenzione, puoi disabilitarlo qui.

#### **Visualizza MSRP sulla pagina prodotto**

-   **Cosa fa questa impostazione:** Controlla se l'MSRP viene mostrato sulle singole pagine di dettaglio del prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* L'MSRP, il tuo prezzo e le informazioni "Risparmi" appariranno sulla pagina del prodotto.
    -   *Quando disabilitato (NO):* L'MSRP non verrà mostrato sulla pagina del prodotto, anche se abilitato globalmente.
-   **Valore consigliato:** SÌ (Questa è una posizione primaria per i clienti per vedere il valore).
-   **Scenario/esempio del commerciante:** Potresti disabilitarlo se preferisci evidenziare i risparmi solo sulle pagine di categoria, o se il design della tua pagina prodotto è già molto affollato.

#### **Visualizza MSRP sull'elenco prodotti**

-   **Cosa fa questa impostazione:** Controlla se l'MSRP viene mostrato sulle pagine che visualizzano più prodotti, come pagine di categoria, risultati di ricerca o blocchi di prodotti in evidenza.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* L'MSRP, il tuo prezzo e le informazioni "Risparmi" appariranno per ogni prodotto negli elenchi dei prodotti.
    -   *Quando disabilitato (NO):* L'MSRP non verrà mostrato nelle pagine degli elenchi dei prodotti.
-   **Valore consigliato:** SÌ (Ottimo per confronti rapidi e per evidenziare il valore durante la navigazione).
-   **Scenario/esempio del commerciante:** Abilitare questa opzione aiuta i clienti a identificare rapidamente buone offerte durante la navigazione delle categorie, aumentando potenzialmente i tassi di clic alle pagine dei prodotti.

#### **Mostra prezzo tasse incluse**

-   **Cosa fa questa impostazione:** Determina se l'MSRP visualizzato deve includere le tasse o essere mostrato come tasse escluse.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* L'MSRP verrà mostrato con le tasse applicabili già aggiunte, riflettendo il prezzo finale che un cliente pagherebbe.
    -   *Quando disabilitato (NO):* L'MSRP verrà mostrato senza tasse.
-   **Valore consigliato:** SÌ (Generalmente, i clienti preferiscono vedere i prezzi finali, specialmente in contesti B2C).
-   **Scenario/esempio del commerciante:** Se il tuo negozio serve principalmente clienti B2C, mostrare i prezzi tasse incluse è più chiaro. Per i negozi B2B, i prezzi tasse escluse potrebbero essere preferiti.

#### **Mostra prezzo tasse escluse**

-   **Cosa fa questa impostazione:** Determina se l'MSRP visualizzato deve escludere le tasse o essere mostrato come tasse incluse.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* L'MSRP verrà mostrato senza tasse.
    -   *Quando disabilitato (NO):* L'MSRP verrà mostrato con le tasse applicabili già aggiunte.
-   **Valore consigliato:** NO (A meno che tu non ti rivolga specificamente a clienti B2B o operi in una regione in cui i prezzi tasse escluse sono standard per la visualizzazione iniziale).
-   **Scenario/esempio del commerciante:** Se abiliti "Mostra prezzo tasse incluse", di solito disabiliteresti questa opzione per evitare confusione. Abilita entrambe solo se vuoi mostrare entrambi i valori affiancati (il che potrebbe essere confuso per i clienti).

#### **Visualizza informazioni "Risparmi"**

-   **Cosa fa questa impostazione:** Controlla se il modulo calcola e visualizza la differenza monetaria tra l'MSRP e il prezzo di vendita del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo mostrerà un messaggio come "Risparmi X,XX €" o "Risparmi X%" accanto all'MSRP e al tuo prezzo.
    -   *Quando disabilitato (NO):* Verranno mostrati solo l'MSRP e il tuo prezzo, senza il calcolo esplicito dei risparmi.
-   **Valore consigliato:** SÌ (Questo è un vantaggio chiave dell'utilizzo del modulo, che motiva fortemente gli acquisti).
-   **Scenario/esempio del commerciante:** Questa funzione evidenzia direttamente la proposta di valore. Se i tuoi prezzi sono costantemente inferiori all'MSRP, abilitare questa opzione aumenterà significativamente il valore percepito.

#### **Campo MSRP per i prodotti**

-   **Cosa fa questa impostazione:** Questa impostazione definisce dove inserirai l'MSRP per ogni prodotto nel tuo Back Office di PrestaShop.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando selezionato:* Il modulo utilizzerà il campo prodotto scelto per recuperare il valore MSRP. Dovrai inserire manualmente l'MSRP per ogni prodotto nel campo specificato.
-   **Valore consigliato:** Il modulo di solito crea un campo personalizzato o suggerisce di utilizzarne uno esistente. Segui le istruzioni del modulo per identificare il campo corretto.
-   **Scenario/esempio del commerciante:** Dopo aver installato il modulo, andrai su **Catalogo > Prodotti**, modificherai un prodotto e troverai un nuovo campo di input (o uno esistente riutilizzato) dove potrai digitare l'MSRP per quel prodotto specifico.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita visualizzazione MSRP | SÌ | Interruttore principale per attivare/disattivare la funzione MSRP a livello di negozio. |
| Configurazione modulo | Visualizza MSRP sulla pagina prodotto | SÌ | Mostra MSRP sulle singole pagine di dettaglio del prodotto. |
| Configurazione modulo | Visualizza MSRP sull'elenco prodotti | SÌ | Mostra MSRP sulle pagine di categoria/risultati di ricerca. |
| Configurazione modulo | Mostra prezzo tasse incluse | SÌ | Visualizza MSRP con tasse incluse (adatto per B2C). |
| Configurazione modulo | Mostra prezzo tasse escluse | NO | Visualizza MSRP senza tasse (adatto per B2B, evita conflitti con 'Tasse incluse'). |
| Configurazione modulo | Visualizza informazioni "Risparmi" | SÌ | Mostra i risparmi calcolati (MSRP - Il tuo prezzo). |
| Configurazione modulo | Campo MSRP per i prodotti | (Specifico del modulo) | Definisce quale campo prodotto nel BO memorizza il valore MSRP. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho abilitato il modulo e inserito gli MSRP, ma non appare nulla nel mio negozio. Cosa c'è che non va?**
R1:

-   **Verifica l'abilitazione globale:** Assicurati che "Abilita visualizzazione MSRP" sia impostato su SÌ nella configurazione del modulo.
-   **Controlla le impostazioni di visualizzazione specifiche:** Verifica che "Visualizza MSRP sulla pagina prodotto" e "Visualizza MSRP sull'elenco prodotti" siano anch'essi impostati su SÌ per le aree in cui ti aspetti di vederlo.
-   **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
-   **MSRP specifico del prodotto:** Ricontrolla di aver effettivamente inserito un valore MSRP per i prodotti specifici che stai testando.
-   **Compatibilità del tema:** A volte, temi altamente personalizzati potrebbero richiedere piccole modifiche per visualizzare nuovi elementi. Se dopo aver svuotato la cache non appare ancora, contatta il supporto MyPresta.eu.

**D2: L'importo "Risparmi" sembra errato o non appare.**
R2:

-   **Abilita "Risparmi":** Assicurati che "Visualizza informazioni 'Risparmi'" sia abilitato nelle impostazioni del modulo.
-   **MSRP vs. Il tuo prezzo:** Il calcolo "Risparmi" dipende sia dall'MSRP che dal prezzo di vendita del tuo prodotto. Assicurati che entrambi i valori siano impostati correttamente per il prodotto. Se il tuo prezzo di vendita è superiore o uguale all'MSRP, non verranno visualizzati risparmi.
-   **Impostazioni fiscali:** Il calcolo potrebbe essere influenzato dal fatto che tu stia mostrando prezzi tasse incluse o tasse escluse. Assicurati che le tue impostazioni fiscali siano coerenti.

**D3: Come inserisco l'MSRP per ogni prodotto?**
R3: Dopo aver installato il modulo, vai su **Catalogo > Prodotti** nel tuo Back Office di PrestaShop. Modifica un prodotto esistente o creane uno nuovo. All'interno dell'interfaccia di modifica del prodotto, dovresti trovare un nuovo campo specifico per "MSRP" (o un campo esistente riutilizzato, come definito nella configurazione del modulo). Inserisci lì il prezzo al dettaglio suggerito dal produttore e salva il prodotto.

**D4: Il testo MSRP non corrisponde al design/font del mio negozio. Come posso cambiarlo?**
R4: Il modulo utilizza il proprio CSS per lo stile. Per piccole modifiche (come dimensione del font, colore), puoi spesso sovrascrivere questi stili nel file CSS personalizzato del tuo tema (es. `themes/yourtheme/assets/css/custom.css` o `themes/yourtheme/css/custom.css`). Per modifiche più estese, potresti aver bisogno di uno sviluppatore web per ispezionare il CSS del modulo e applicare override più specifici.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Manufacturer suggested / recommended retail price (MSRP)" è un modulo PrestaShop standard progettato per estendere le funzionalità di visualizzazione dei prodotti del front-office. Opera principalmente agganciandosi ai punti di visualizzazione PrestaShop esistenti (come pagine prodotto ed elenchi prodotti) per iniettare le informazioni MSRP. Sfrutta il sistema di configurazione di PrestaShop per le sue impostazioni e i template Smarty per il rendering dell'output del front-office. La logica centrale del modulo risiede nel suo file PHP principale, che gestisce l'installazione, la disinstallazione, la configurazione e la registrazione degli hook.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office Admin personalizzati. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo, e la visualizzazione del front-office è gestita tramite hook e rendering dei template.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate o istanze `ObjectModel` nella directory `classes/`. Interagisce direttamente con i dati e la configurazione dei prodotti PrestaShop esistenti.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`msrp/views/admin/js/msrp.js`**

    -   **Ambito:** Back-office.
    -   **Scopo:** Questo script probabilmente gestisce qualsiasi comportamento dinamico o convalida all'interno del modulo di configurazione del modulo nel Back Office di PrestaShop. Ciò potrebbe includere la visualizzazione/nascondimento di campi in base ad altre selezioni, chiamate AJAX per il salvataggio delle impostazioni o la convalida lato client.
    -   **Dettagli:** Lega i listener di eventi agli elementi del modulo di configurazione, esegue la gestione dell'invio del modulo e potenzialmente aggiorna l'interfaccia utente in base all'input dell'utente.
-   **`msrp/views/js/msrp.js`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo script è responsabile di qualsiasi interazione lato client o aggiornamento dinamico relativo alla visualizzazione MSRP nel front office. Ciò potrebbe comportare l'aggiornamento dinamico dell'importo "Risparmi" se gli attributi del prodotto cambiano (ad esempio, selezionando una dimensione/colore diverso che influisce sul prezzo) o la gestione della logica di visualizzazione.
    -   **Dettagli:** Si lega agli eventi `prestashop.on` (ad esempio, `updatedProduct` per le modifiche di prezzo della pagina prodotto), manipola gli elementi DOM per aggiornare la visualizzazione MSRP o dei risparmi e garantisce la reattività.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`msrp/views/admin/css/msrp.css`**

    -   **Ambito:** Styling del modulo di amministrazione del Back-office.
    -   **Scopo:** Fornisce uno stile specifico per la pagina di configurazione del modulo all'interno del Back Office di PrestaShop, garantendo un'interfaccia coerente e user-friendly.
    -   **Selettori chiave:** Si rivolge agli elementi all'interno dell'output `getContent()` del modulo, come campi del modulo, etichette e sezioni.
-   **`msrp/views/css/msrp.css`**

    -   **Ambito:** Styling del cliente del Front-office.
    -   **Scopo:** Stila le informazioni visualizzate di MSRP, il tuo prezzo e "Risparmi" sulle pagine prodotto e negli elenchi dei prodotti. Ciò garantisce che le informazioni siano chiaramente visibili e si integrino bene con il design generale del negozio.
    -   **Selettori chiave:** Si rivolge a specifici elementi `div` o `span` generati dai template Smarty del modulo (ad esempio, `.msrp-price`, `.msrp-you-save`, `.msrp-old-price`). Gli sviluppatori possono sovrascrivere queste classi nel `custom.css` del loro tema per adattarle al loro branding.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`msrp/views/admin/msrp.tpl`**

    -   **Ambito:** Template di amministrazione.
    -   **Scopo:** Questo template renderizza il modulo di configurazione del modulo nel Back Office di PrestaShop. Contiene la struttura HTML per tutte le impostazioni descritte nella Sezione 4.1.
    -   **Dettagli:** Utilizza i componenti del modulo di aiuto di PrestaShop (ad esempio, `helperForm`) per creare campi di input, interruttori e pulsanti per le impostazioni del modulo.
-   **`msrp/views/templates/msrp-product-list.tpl`**

    -   **Ambito:** Template di hook (ad esempio, `displayProductPriceBlock` o simili per gli elenchi di prodotti).
    -   **Scopo:** Questo template è responsabile della visualizzazione delle informazioni MSRP nelle pagine degli elenchi di prodotti (categorie, risultati di ricerca, ecc.). Tipicamente riceve i dati del prodotto e le impostazioni di configurazione del modulo per renderizzare l'MSRP, il prezzo corrente e il messaggio "Risparmi".
    -   **Dettagli:** Contiene la logica per verificare se l'MSRP è disponibile, se "Risparmi" deve essere visualizzato e formatta i prezzi in base alle impostazioni fiscali.
-   **`msrp/views/templates/msrp-product-page.tpl`**

    -   **Ambito:** Template di hook (ad esempio, `displayProductPriceBlock` o `displayProductButtons` sulle pagine prodotto).
    -   **Scopo:** Questo template renderizza le informazioni MSRP sulle singole pagine di dettaglio del prodotto. È progettato per integrarsi perfettamente vicino al blocco principale del prezzo del prodotto.
    -   **Dettagli:** Simile a `msrp-product-list.tpl`, gestisce la visualizzazione condizionale di MSRP, prezzo corrente e risparmi, applicando regole fiscali e formattazione.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`, tipicamente con chiavi prefissate da `MSRP_` (ad esempio, `MSRP_ENABLE`, `MSRP_DISPLAY_PRODUCT_PAGE`).
    -   I valori MSRP per i prodotti sono memorizzati in un campo prodotto esistente, come configurato nel modulo (ad esempio, `ps_product_lang.description_short` o un campo prodotto personalizzato se creato dal modulo).
-   **Tabella degli hook registrati**:
    Il modulo registra gli hook per iniettare il suo contenuto nel front office e gestire il suo ciclo di vita.

    | Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `install()` | Durante l'installazione del modulo | Crea voci di configurazione, registra hook, potenzialmente aggiunge campi prodotto. |
    | `uninstall()` | Durante la disinstallazione del modulo | Pulisce le voci di configurazione, deregistra gli hook, rimuove i campi prodotto. |
    | `displayHeader` | Nella sezione `<head>` di ogni pagina | Inietta i file CSS e JS del modulo per la visualizzazione nel front-office. |
    | `displayProductPriceBlock` | All'interno del blocco prezzo del prodotto nelle pagine prodotto e negli elenchi | Hook principale per il rendering di MSRP, prezzo corrente e informazioni "Risparmi". Questo hook viene chiamato più volte con parametri diversi (ad esempio, `type='after_price'`). |
    | `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office | Potenzialmente utilizzato per garantire che i dati MSRP siano correttamente salvati o elaborati. |
    | `actionProductSave` | Dopo il salvataggio di un prodotto nel Back Office | Simile a `actionProductUpdate`, garantisce l'integrità dei dati MSRP. |
    | `actionProductDelete` | Dopo l'eliminazione di un prodotto | Pulisce eventuali dati MSRP associati se memorizzati separatamente. |
    | `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office | Aggiunge il campo di input MSRP al modulo del prodotto. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore assistenza con il modulo "Manufacturer suggested / recommended retail price (MSRP)", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto e gli sviluppatori sono pronti ad aiutarti a massimizzare il potenziale di questo modulo per il tuo negozio PrestaShop.
