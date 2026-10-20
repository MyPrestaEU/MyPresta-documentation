---
title: "Metodi di spedizione (corrieri) dal prodotto più costoso - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Metodi di spedizione (corrieri) dal prodotto più costoso' di MyPresta.eu."
sidebar:
  label: "Metodi di spedizione (corrieri) dal prodotto più costoso - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Shipping methods (carriers) from the most expensive product su MyPresta.eu](https://mypresta.eu/modules/ordering-process/shipping-methods-carriers-from-the-most-expensive-product.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/shipping-methods-carriers-from-the-most-expensive-product/)
>
> ---


# Metodi di spedizione (corrieri) dal prodotto più costoso

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni.

#### **Abilita / Disabilita Modulo**

- **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Il modulo modificherà la logica di selezione del corriere predefinita di PrestaShop, garantendo che vengano visualizzati durante il checkout solo i corrieri associati al prodotto più costoso nel carrello.
  - *Quando disabilitato:* PrestaShop tornerà al suo comportamento predefinito, in cui i corrieri vengono mostrati solo se possono spedire *tutti* i prodotti nel carrello.
- **Valore consigliato:** "Abilitato" se si desidera utilizzare la funzionalità del modulo.
- **Scenario / esempio del commerciante:** Se stai testando il modulo o desideri temporaneamente tornare al comportamento predefinito di PrestaShop senza disinstallare, puoi disabilitarlo qui.

#### **Come ottenere i corrieri?**

- **Cosa fa questa impostazione:** Questa impostazione cruciale definisce *come* il modulo identifica il "prodotto più costoso" e successivamente determina i corrieri disponibili. Offre due metodi distinti.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "Dal prodotto più costoso (per prezzo)":* Il modulo calcolerà il prezzo totale di ogni prodotto unico nel carrello (quantità * prezzo unitario) e identificherà il prodotto con il prezzo totale più alto. I corrieri associati a *quel prodotto specifico* verranno quindi utilizzati per filtrare le opzioni di spedizione disponibili.
  - *Quando impostato su "Dal prodotto più costoso (per prezzo) - SPEDIZIONE GRATUITA":* Questa opzione funziona in modo simile alla prima, ma considera anche se il prodotto più costoso si qualifica per la spedizione gratuita. Se il prodotto più costoso ha la spedizione gratuita abilitata, le opzioni di spedizione gratuita verranno prioritarie o rese disponibili in base alle impostazioni del tuo corriere.
  - *Quando impostato su "Dal prodotto più costoso (per prezzo) - COSTO":* Questa opzione identifica anche il prodotto più costoso per prezzo, ma si concentra specificamente sul *costo* associato alla spedizione di quel prodotto. Garantisce che i costi di spedizione e le opzioni presentate siano direttamente collegati alla configurazione di spedizione dell'articolo più costoso.
- **Valore consigliato:**
  - "Dal prodotto più costoso (per prezzo)" è la scelta più comune e consigliata per l'uso generale, in quanto implementa direttamente la promessa principale del modulo.
  - Scegli "Dal prodotto più costoso (per prezzo) - SPEDIZIONE GRATUITA" se offri frequentemente la spedizione gratuita su articoli di alto valore e desideri che questa sia una considerazione primaria nella selezione del corriere.
  - Scegli "Dal prodotto più costoso (per prezzo) - COSTO" se hai regole complesse sui costi di spedizione legate a specifici prodotti di alto valore e desideri che tali regole dettino i corrieri disponibili.
- **Scenario / esempio del commerciante:**
  - Vendi una TV da $1000 e un telecomando da $10. Se la TV è configurata con corrieri specifici (es. trasporto assicurato) e il telecomando con il servizio postale standard, la scelta di "Dal prodotto più costoso (per prezzo)" garantirà che vengano mostrati i corrieri della TV.
  - Se la tua TV da $1000 include la spedizione gratuita, selezionando "Dal prodotto più costoso (per prezzo) - SPEDIZIONE GRATUITA" si garantirebbe che le opzioni di spedizione gratuita vengano presentate se disponibili per la TV.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Abilita / Disabilita Modulo | Abilitato | Attiva/disattiva la logica del modulo per la selezione del corriere in base al prodotto più costoso. |
| Pagina di configurazione del modulo | Come ottenere i corrieri? | Dal prodotto più costoso (per prezzo) | Definisce il metodo per identificare il "prodotto più costoso" e i suoi corrieri associati. Opzioni: "per prezzo", "per prezzo - SPEDIZIONE GRATUITA", "per prezzo - COSTO". |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato il modulo, ma continuo a vedere le vecchie opzioni di corriere o nessun corriere.**
R:

1.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione del modulo. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
2.  **Controlla le associazioni dei corrieri del prodotto:** Assicurati che i tuoi prodotti, specialmente quelli più costosi, siano correttamente associati ai corrieri desiderati nelle impostazioni del prodotto (**Catalogo > Prodotti > Modifica prodotto > Scheda Spedizione**).
3.  **Verifica che il modulo sia abilitato:** Ricontrolla che l'impostazione "Abilita / Disabilita Modulo" sia impostata su "Abilitato" nella configurazione del modulo.
4.  **Compatibilità del tema:** Sebbene raro per questo tipo di modulo, un tema altamente personalizzato potrebbe interferire. Passa temporaneamente al tema predefinito di PrestaShop per escludere questa possibilità.

**D: Come gestisce il modulo due prodotti con lo stesso prezzo più alto?**
R: Nei casi in cui due o più prodotti condividono esattamente il prezzo più alto, il modulo ne selezionerà tipicamente uno in base all'ordine interno dell'ID del prodotto PrestaShop o all'ordine in cui sono stati aggiunti al carrello. Utilizzerà quindi i corrieri associati a quel prodotto selezionato. Per coerenza, è meglio assicurarsi che le configurazioni dei corrieri siano sufficientemente robuste da coprire articoli di alto valore simili.

**D: Questo modulo influisce sui costi di spedizione o solo sulla disponibilità del corriere?**
R: Questo modulo influisce principalmente sulla *disponibilità del corriere*. Determina *quali* corrieri vengono mostrati. I costi di spedizione effettivi per il corriere scelto verranno comunque calcolati dai meccanismi standard di PrestaShop (in base a peso, prezzo, zona, ecc.) per l'*intero carrello*, ma solo per i corrieri resi disponibili dalla logica di questo modulo.

**D: Cosa succede se il prodotto più costoso non ha corrieri associati?**
R: Se il prodotto più costoso nel carrello non ha corrieri esplicitamente associati nelle impostazioni del prodotto, allora nessun corriere verrà visualizzato durante il checkout, portando potenzialmente a un messaggio "nessun metodo di spedizione disponibile". Assicurati sempre che i tuoi prodotti di alto valore abbiano corrieri appropriati assegnati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Metodi di spedizione (corrieri) dal prodotto più costoso" raggiunge la sua funzionalità sovrascrivendo una classe core di PrestaShop, `Cart`. Questo è un metodo comune e potente in PrestaShop per alterare comportamenti fondamentali senza modificare direttamente i file core. Sovrascrivendo `Cart::getAvailableCarriers()`, il modulo inietta la sua logica personalizzata per filtrare i corrieri in base al prodotto più costoso, piuttosto che la regola predefinita "tutti i prodotti devono essere compatibili".

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Il modulo opera sovrascrivendo una classe core, non introducendo nuove rotte o pagine front-office.
- **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

La logica principale del modulo risiede in una sovrascrittura della classe `Cart`.

- **`cfep/override/classes/Cart.php`**

  - **Nome classe**: `Cart` (sovrascrive `PrestaShop\Classes\Cart\Cart` o `CartCore` a seconda della versione e del contesto di PrestaShop).
  - **Classe genitore**: `CartCore`
  - **Responsabilità**: Questo file contiene il metodo `getAvailableCarriers()` sovrascritto. Questo metodo è cruciale per determinare quali corrieri di spedizione vengono presentati al cliente durante il checkout. La sovrascrittura introduce la logica per:
    1. Identificare il prodotto più costoso nel carrello corrente in base alla configurazione del modulo (`CFEP`, `CFEP_FREE`, `CFEP_COST`).
    2. Recuperare i corrieri specificamente associati a questo prodotto più costoso.
    3. Filtrare l'elenco di tutti i corrieri disponibili per includere solo quelli compatibili con il prodotto più costoso.
    4. Restituire questo elenco filtrato di corrieri.
  - **Metodi pubblici chiave**:
    - `getAvailableCarriers(bool $return_full_list = false, int $id_zone = null, bool $use_cache = true)`: Questo è il metodo sovrascritto. Estende l'originale `CartCore::getAvailableCarriers` per implementare la logica di filtraggio personalizzata del corriere. Prima chiama il metodo genitore per ottenere tutti i corrieri potenzialmente disponibili, quindi applica il proprio filtraggio in base al prodotto più costoso.
- **`cfep/override/classes/index.php`**

  - **Responsabilità**: Questo è un file `index.php` vuoto standard, tipicamente posizionato nelle directory per impedire l'elenco delle directory quando vi si accede direttamente tramite un browser web. Non ha alcun impatto funzionale sulla logica del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessuno. Il modulo non aggiunge alcun JavaScript personalizzato al front o back office.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessuno. Il modulo non aggiunge alcun CSS personalizzato al front o back office.

### 4.6 Struttura del template Smarty (`views/templates/`)

- Nessuno. Il modulo non utilizza alcun template Smarty personalizzato. La sua interfaccia di configurazione è generata dinamicamente da `getContent()` nel file principale del modulo.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:
  Il modulo non crea tabelle di database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration`.

  - Voci `ps_configuration`:
    - `CFEP`: Memorizza il metodo selezionato per ottenere i corrieri (es. 'price', 'free', 'cost').
    - `mypresta_updates`: Utilizzato per i controlli di aggiornamento interni di MyPresta.eu.
    - `update_`: Utilizzato per i controlli di aggiornamento interni di MyPresta.eu.
    - `updatev_`: Utilizzato per i controlli di aggiornamento interni di MyPresta.eu.
- **Tabella degli hook registrati**:
  Il modulo non registra esplicitamente alcun hook nella tabella `ps_hook_module`. La sua funzionalità è implementata tramite una sovrascrittura di classe, che è un modo più diretto per alterare il comportamento core di PrestaShop senza fare affidazione su specifici punti di esecuzione degli hook.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Metodi di spedizione (corrieri) dal prodotto più costoso", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
