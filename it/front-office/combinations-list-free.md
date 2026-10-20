---
title: "Combinations List Free - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Combinations List Free di MyPresta.eu."
sidebar:
  label: "Combinations List Free - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Combinations List Free su MyPresta.eu](https://mypresta.eu/modules/front-office-features/combinations-list-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/combinations-list-free/)
>
> ---


# Combinations List Free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop, ma questo modulo non ha requisiti esotici specifici oltre a un ambiente PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Combinations List Free" nel tuo Gestione moduli. Questo ti porterà alla schermata di configurazione principale.

#### Impostazioni generali

- **Cosa fa questa impostazione:** Questa sezione controlla il comportamento generale e l'aspetto dell'elenco delle combinazioni sulle tue pagine di prodotto.

  - **Visualizza l'elenco delle combinazioni sulla pagina del prodotto:**

    - **Cosa fa questa impostazione:** Questo è l'interruttore principale per abilitare o disabilitare la funzionalità del modulo.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Il modulo tenterà di visualizzare l'elenco delle combinazioni sulle pagine dei prodotti in base alle altre impostazioni.
      - *Quando disabilitato (NO):* Il modulo sarà inattivo e le tue pagine dei prodotti torneranno ai selettori di combinazione predefiniti di PrestaShop (menu a discesa).
    - **Valore consigliato:** SÌ (per utilizzare il modulo).
    - **Scenario / esempio del commerciante:** Se stai testando il modulo o desideri disabilitarlo temporaneamente senza disinstallarlo, impostalo su NO.
  - **Hook per visualizzare l'elenco delle combinazioni:**

    - **Cosa fa questa impostazione:** Determina dove sulla pagina del prodotto apparirà l'elenco delle combinazioni. Questo è cruciale per integrare visivamente l'elenco con il tuo tema.
    - **Effetto della modifica di questa impostazione:**
      - *Quando impostato su `displayProductButtons` (o hook simile relativo al prodotto):* L'elenco apparirà tipicamente vicino al pulsante "Aggiungi al carrello" o al prezzo del prodotto, spesso sotto i dettagli principali del prodotto.
      - *Quando impostato su `displayProductExtraContent` (o hook simile relativo alle schede):* L'elenco apparirà all'interno di una nuova o esistente scheda prodotto, mantenendo più pulita l'area della descrizione principale del prodotto.
      - *Quando impostato su `displayFooterProduct` (o hook simile del piè di pagina):* L'elenco apparirà nella parte inferiore della pagina del prodotto.
    - **Valore consigliato:** Sperimenta con diversi hook per trovare la migliore integrazione visiva con il tuo tema specifico. `displayProductButtons` o `displayProductExtraContent` sono scelte comuni.
    - **Scenario / esempio del commerciante:** Se la tua pagina del prodotto è già lunga, posizionare l'elenco in una scheda `displayProductExtraContent` può rendere la pagina meno ingombra. Se desideri che l'elenco sia immediatamente visibile, un hook come `displayProductButtons` è migliore.
  - **Mostra immagine combinazione:**

    - **Cosa fa questa impostazione:** Controlla se una piccola immagine specifica per ogni combinazione viene visualizzata nell'elenco.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Se hai caricato immagini specifiche per ogni combinazione di prodotto, appariranno accanto alla rispettiva combinazione nell'elenco.
      - *Quando disabilitato (NO):* Verranno mostrati solo il nome, il riferimento e il prezzo della combinazione, senza un'immagine.
    - **Valore consigliato:** SÌ, se hai immagini uniche per le combinazioni. Questo aiuta significativamente i clienti a visualizzare il prodotto esatto che stanno selezionando.
    - **Scenario / esempio del commerciante:** Per l'abbigliamento, mostrare un'immagine di una maglietta rossa per la combinazione "Rossa - Grande" è molto più chiaro del solo testo.
  - **Mostra riferimento combinazione:**

    - **Cosa fa questa impostazione:** Determina se il numero di riferimento interno per ogni combinazione viene visualizzato.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Il riferimento della combinazione (es. SKU) sarà visibile nell'elenco.
      - *Quando disabilitato (NO):* Il numero di riferimento sarà nascosto.
    - **Valore consigliato:** SÌ, specialmente per i negozi B2B o prodotti in cui i clienti spesso ordinano per riferimento.
    - **Scenario / esempio del commerciante:** Un cliente che riordina una parte specifica potrebbe conoscerla tramite il suo numero di riferimento, rendendola più facile da trovare.
  - **Mostra campo quantità combinazione:**

    - **Cosa fa questa impostazione:** Consente ai clienti di specificare la quantità per ogni combinazione direttamente all'interno dell'elenco, piuttosto che aggiungerne solo una alla volta.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Un campo di input per la quantità (es. una casella numerica) apparirà accanto a ogni combinazione, consentendo ai clienti di inserire una quantità desiderata prima di cliccare su "Aggiungi al carrello".
      - *Quando disabilitato (NO):* Il pulsante "Aggiungi al carrello" aggiungerà tipicamente una unità della combinazione al carrello.
    - **Valore consigliato:** SÌ, per la maggior parte dei negozi, poiché migliora l'efficienza per i clienti che acquistano più unità della stessa combinazione.
    - **Scenario / esempio del commerciante:** Un cliente che acquista 5 unità di "Blu - Medio" e 3 unità di "Verde - Grande" può farlo rapidamente dall'elenco.
  - **Mostra prezzo combinazione:**

    - **Cosa fa questa impostazione:** Controlla se il prezzo di ogni singola combinazione viene visualizzato nell'elenco.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Il prezzo per ogni combinazione specifica verrà mostrato.
      - *Quando disabilitato (NO):* Il prezzo sarà nascosto e i clienti potrebbero vedere solo il prezzo principale del prodotto o doverlo dedurre.
    - **Valore consigliato:** SÌ. La trasparenza dei prezzi è cruciale per la fiducia e il processo decisionale del cliente.
    - **Scenario / esempio del commerciante:** Se diverse taglie o colori hanno prezzi diversi, mostrare il prezzo esatto per ogni combinazione è essenziale.
  - **Mostra disponibilità combinazione:**

    - **Cosa fa questa impostazione:** Visualizza lo stato delle scorte (es. "Disponibile," "Esaurito," "Ultimi pezzi!") per ogni combinazione.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* I clienti vedranno lo stato di disponibilità per ogni combinazione, aiutandoli a prendere decisioni di acquisto informate.
      - *Quando disabilitato (NO):* Lo stato delle scorte non verrà mostrato nell'elenco.
    - **Valore consigliato:** SÌ. Questo impedisce ai clienti di aggiungere articoli esauriti al carrello, riducendo la frustrazione e i carrelli abbandonati.
    - **Scenario / esempio del commerciante:** Un cliente può vedere immediatamente che la maglietta "Rossa - Grande" è esaurita e scegliere invece "Blu - Grande".
  - **Mostra descrizione combinazione:**

    - **Cosa fa questa impostazione:** Se hai descrizioni specifiche per ogni combinazione, questa impostazione ne controlla la visualizzazione.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Qualsiasi descrizione unica associata a una combinazione verrà mostrata nell'elenco.
      - *Quando disabilitato (NO):* Le descrizioni specifiche della combinazione saranno nascoste.
    - **Valore consigliato:** SÌ, se le tue combinazioni hanno descrizioni distinte che aggiungono valore alla decisione del cliente.
    - **Scenario / esempio del commerciante:** Per un prodotto personalizzabile, una descrizione della combinazione potrebbe dettagliare i materiali specifici utilizzati per quella variante.
  - **Testo del pulsante Aggiungi al carrello:**

    - **Cosa fa questa impostazione:** Ti consente di personalizzare il testo visualizzato sul pulsante "Aggiungi al carrello" per ogni combinazione.
    - **Effetto della modifica di questa impostazione:**
      - *Quando modificato:* Il testo del pulsante si aggiornerà alla tua frase personalizzata.
      - *Quando lasciato vuoto:* Verrà utilizzato il testo predefinito "Aggiungi al carrello" (o quello predefinito del tuo tema).
    - **Valore consigliato:** "Aggiungi al carrello" o "Acquista ora" per chiarezza. Mantienilo conciso.
    - **Scenario / esempio del commerciante:** Potresti cambiarlo in "Seleziona e Acquista" se vuoi enfatizzare la selezione prima dell'acquisto.
  - **Visualizza combinazioni come tabella:**

    - **Cosa fa questa impostazione:** Cambia la presentazione visiva delle combinazioni da un semplice elenco a una tabella HTML strutturata.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Le combinazioni verranno presentate in formato tabella con colonne per immagine, nome, riferimento, prezzo, quantità e aggiungi al carrello. Questo è spesso più compatto e organizzato per molte combinazioni.
      - *Quando disabilitato (NO):* Le combinazioni verranno visualizzate come un elenco meno strutturato, tipicamente una combinazione per riga.
    - **Valore consigliato:** SÌ, nella maggior parte dei casi, poiché una tabella offre una migliore leggibilità e allineamento, specialmente con molte opzioni.
    - **Scenario / esempio del commerciante:** Se hai più di 20 combinazioni, una tabella rende molto più facile la scansione e il confronto.
  - **Visualizza combinazioni come scheda:**

    - **Cosa fa questa impostazione:** Questa impostazione è probabilmente un dettaglio di implementazione legacy o specifico. Data l'impostazione `Hook per visualizzare l'elenco delle combinazioni`, questa potrebbe essere ridondante o riferirsi a un modello specifico.
    - **Effetto della modifica di questa impostazione:**
      - *Quando abilitato (SÌ):* Potrebbe forzare l'elenco delle combinazioni in una struttura a schede, potenzialmente sovrascrivendo l'hook scelto se quell'hook non crea naturalmente una scheda.
      - *Quando disabilitato (NO):* La visualizzazione seguirà più direttamente l'hook scelto.
    - **Valore consigliato:** Generalmente NO, a meno che tu non voglia specificamente una scheda e l'hook scelto non la fornisca. Affidati all'impostazione "Hook per visualizzare l'elenco delle combinazioni" per il posizionamento.
    - **Scenario / esempio del commerciante:** Se il tuo tema non crea automaticamente schede per `displayProductExtraContent`, abilitare questa opzione potrebbe forzare un aspetto a schede.

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Visualizza l'elenco delle combinazioni sulla pagina del prodotto | SÌ | Interruttore principale per abilitare/disabilitare la visualizzazione front-office del modulo. |
| Configurazione modulo | Hook per visualizzare l'elenco delle combinazioni | `displayProductButtons` o `displayProductExtraContent` | Determina la posizione esatta dell'elenco sulla pagina del prodotto. |
| Configurazione modulo | Mostra immagine combinazione | SÌ (se esistono immagini) | Visualizza immagini uniche per ogni combinazione. |
| Configurazione modulo | Mostra riferimento combinazione | SÌ | Mostra il numero SKU/riferimento per ogni combinazione. |
| Configurazione modulo | Mostra campo quantità combinazione | SÌ | Consente ai clienti di inserire le quantità per ogni combinazione. |
| Configurazione modulo | Mostra prezzo combinazione | SÌ | Visualizza il prezzo specifico per ogni combinazione. |
| Configurazione modulo | Mostra disponibilità combinazione | SÌ | Mostra lo stato delle scorte (es. "Disponibile") per ogni combinazione. |
| Configurazione modulo | Mostra descrizione combinazione | SÌ (se esistono descrizioni) | Visualizza descrizioni uniche per ogni combinazione. |
| Configurazione modulo | Testo del pulsante Aggiungi al carrello | "Aggiungi al carrello" | Personalizza il testo sui pulsanti 'Aggiungi al carrello'. |
| Configurazione modulo | Visualizza combinazioni come tabella | SÌ | Presenta le combinazioni in un formato tabella strutturato per una migliore leggibilità. |
| Configurazione modulo | Visualizza combinazioni come scheda | NO | (Probabilmente legacy/specifico) Controlla la visualizzazione a schede; preferire l'impostazione dell'hook. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: L'elenco delle combinazioni non viene visualizzato sulla mia pagina del prodotto.**
**R1:**

- Per prima cosa, controlla se "Visualizza l'elenco delle combinazioni sulla pagina del prodotto" è impostato su SÌ nella configurazione del modulo.
- Successivamente, verifica l'impostazione "Hook per visualizzare l'elenco delle combinazioni". Alcuni temi potrebbero non renderizzare tutti gli hook standard di PrestaShop allo stesso modo. Prova a passare a un hook diverso (es. `displayProductButtons`, `displayProductExtraContent`, `displayFooterProduct`) per vedere se appare.
- Assicurati che il prodotto che stai visualizzando abbia effettivamente delle combinazioni definite.
- Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).

**D2: Le immagini delle mie combinazioni non appaiono nell'elenco.**
**R2:**

- Assicurati che "Mostra immagine combinazione" sia abilitato nelle impostazioni del modulo.
- Fondamentale, devi aver caricato immagini specifiche per ogni combinazione nell'editor del prodotto di PrestaShop (Prodotto > Scheda Combinazioni > Modifica ogni combinazione > Aggiungi immagine). Se nessuna immagine specifica è assegnata a una combinazione, non apparirà.

**D3: L'elenco sembra disordinato o non si adatta al design del mio tema.**
**R3:**

- Prova ad abilitare "Visualizza combinazioni come tabella" se non lo è già. Questo spesso fornisce un layout più strutturato e visivamente accattivante.
- Il modulo utilizza il proprio CSS. Il CSS del tuo tema potrebbe sovrascrivere o entrare in conflitto con esso. Potrebbe essere necessario un web developer per regolare il CSS del modulo (`mycombtabfree.css`) o aggiungere CSS personalizzato al tuo tema per stilizzarlo a tuo piacimento.
- Sperimenta con diversi hook. Alcuni hook potrebbero avere una migliore stilizzazione predefinita dal tuo tema.

**D4: Posso tradurre il testo del pulsante "Aggiungi al carrello" in altre lingue?**
**R4:** Sì. Vai su **Internazionale > Traduzioni** nel Back Office di PrestaShop. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi seleziona "Combinations List Free" dal menu a discesa del modulo. Potrai quindi tradurre il testo del pulsante e qualsiasi altra frase specifica del modulo.

**D5: Perché alcune combinazioni mostrano "Esaurito" anche se ho scorte?**
**R5:**

- Controlla le impostazioni di magazzino del tuo prodotto nell'editor del prodotto di PrestaShop. Assicurati che la combinazione specifica abbia una quantità disponibile.
- Verifica le tue impostazioni globali di gestione del magazzino (Parametri negozio > Impostazioni prodotto > Magazzino prodotti).
- Svuota la cache di PrestaShop dopo aver apportato modifiche alle scorte.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Combinations List Free" (`mycombtabfree`) è un modulo PrestaShop standard progettato per migliorare la pagina del prodotto del front-office. Opera principalmente agganciandosi a vari punti di visualizzazione sulla pagina del prodotto per iniettare la sua struttura HTML personalizzata per le combinazioni di prodotti. Il modulo segue un modello di tipo MVC di base all'interno del framework del modulo PrestaShop, utilizzando una classe di modulo principale per la configurazione e la registrazione degli hook, e i template Smarty per il rendering dell'output del front-office. Sfrutta le funzionalità core esistenti di PrestaShop per recuperare i dati di prodotto e combinazione.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la configurazione è gestita tramite il metodo `getContent()` della classe del modulo principale, e il rendering del front-office viene eseguito direttamente tramite hook.

### 4.3 Classi e modelli core (`classes/`)

Questo modulo non contiene classi personalizzate o definizioni di `ObjectModel` nella directory `classes/`. Si basa interamente sulle classi core `Product` e `Combination` di PrestaShop per recuperare e visualizzare i dati.

### 4.4 Risorse JavaScript (`views/js/`)

- **`mycombtabfree/js/atc.js`**
  - **Ambito:** Front-office.
  - **Scopo:** Questo script è responsabile della gestione della funzionalità "Aggiungi al carrello" per le combinazioni visualizzate dal modulo. Probabilmente intercetta gli eventi di clic sui pulsanti "Aggiungi al carrello" personalizzati generati dal modulo.
  - **Funzionalità:**
    - Lega i listener di eventi ai pulsanti "Aggiungi al carrello" all'interno dell'elenco/tabella delle combinazioni.
    - Quando un pulsante viene cliccato, raccoglie l'`id_product`, l'`id_product_attribute` (ID combinazione) e potenzialmente la quantità dal campo di input associato.
    - Effettua quindi una richiesta AJAX al controller `cart` core di PrestaShop (o a un endpoint simile) per aggiungere la combinazione selezionata al carrello.
    - Potrebbe anche aggiornare il blocco del carrello, visualizzare notifiche (successo/errore) o gestire altri feedback dell'interfaccia utente dopo la chiamata AJAX.
    - Probabilmente utilizza jQuery o gli eventi nativi `prestashop.on` di PrestaShop per gli aggiornamenti dinamici.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`mycombtabfree/css/admin.css`**

  - **Ambito:** Stilizzazione del modulo di amministrazione del Back-office.
  - **Scopo:** Contiene stili specifici per la pagina di configurazione del modulo nel Back Office di PrestaShop. Questo potrebbe includere la stilizzazione per elementi del modulo, avvisi o aggiustamenti del layout per rendere l'interfaccia di configurazione user-friendly.
  - **Selettori chiave:** Probabilmente targetta elementi all'interno dell'output `getContent()` del modulo, come `.panel`, `.form-group`, `.alert`, ecc., per garantire un'interfaccia utente amministrativa coerente.
- **`mycombtabfree/css/mycombtabfree.css`**

  - **Ambito:** Stilizzazione del cliente del Front-office.
  - **Scopo:** Fornisce la stilizzazione visiva principale per l'elenco/tabella delle combinazioni visualizzate sulla pagina del prodotto. Questo include layout, tipografia, colori e reattività.
  - **Selettori chiave:**
    - `.mycombtabfree-container`: Wrapper principale per l'elenco delle combinazioni.
    - `.mycombtabfree-table`: Stili per l'elemento `<table>` quando "Visualizza combinazioni come tabella" è abilitato.
    - `.mycombtabfree-row`, `.mycombtabfree-cell`: Stili per righe e celle della tabella.
    - `.mycombtabfree-image`, `.mycombtabfree-name`, `.mycombtabfree-reference`, `.mycombtabfree-price`, `.mycombtabfree-qty`, `.mycombtabfree-atc`: Stili specifici per ogni pezzo di dati della combinazione.
    - Media query per aggiustamenti reattivi su schermi più piccoli.
  - **Override dello sviluppatore:** Gli sviluppatori possono sovrascrivere questi stili nei file CSS del loro tema personalizzato utilizzando selettori più specifici o modificando direttamente questo file (anche se quest'ultima opzione non è raccomandata per la facilità di aggiornamento).

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`mycombtabfree/views/templates/admin/configure.tpl`**

  - **Ambito:** Pannello di configurazione amministrativo.
  - **Scopo:** Rende il modulo HTML per le impostazioni di configurazione del modulo nel Back Office di PrestaShop. Questo template viene caricato dal metodo `getContent()` della classe del modulo principale.
  - **Contenuto:** Contiene campi del modulo (checkbox, input di testo, menu a discesa di selezione) corrispondenti alle impostazioni descritte nella Sezione 4.1.
- **`mycombtabfree/views/templates/admin/pro-upsell.tpl`**

  - **Ambito:** Pannello di configurazione amministrativo.
  - **Scopo:** Visualizza contenuti promozionali o un banner di upsell per una versione "Pro" del modulo all'interno della configurazione del Back Office. Questa è una pratica comune per i moduli gratuiti.
- **`mycombtabfree/views/templates/hook/pro-banner.tpl`**

  - **Ambito:** Hook del Front-office.
  - **Scopo:** Rende un banner promozionale per la versione "Pro" del modulo, probabilmente visualizzato in un hook del front-office meno intrusivo (es. `displayFooter` o `displayLeftColumn`).
- **`mycombtabfree/views/templates/hook/tab.tpl`**

  - **Ambito:** Hook del Front-office.
  - **Scopo:** Questo template è probabilmente utilizzato quando l'impostazione "Visualizza combinazioni come scheda" è abilitata, o quando il modulo è agganciato a una posizione che crea naturalmente una scheda (es. `displayProductExtraContent`). Contiene la struttura per una scheda prodotto, all'interno della quale verrà renderizzato l'elenco/tabella delle combinazioni effettive.
- **`mycombtabfree/views/templates/hook/table.tpl`**

  - **Ambito:** Hook del Front-office.
  - **Scopo:** Questo è il template principale responsabile del rendering dell'elenco o della tabella effettiva delle combinazioni di prodotti nel front-office. Itera attraverso le combinazioni disponibili per un dato prodotto e visualizza ciascuna di esse in base alle impostazioni di configurazione del modulo (es. mostrando immagine, riferimento, prezzo, campo quantità, pulsante aggiungi al carrello).
  - **Logica:** Contiene cicli Smarty (`{foreach}`) per iterare sull'array `$combinations`, istruzioni condizionali (`{if}`) per visualizzare gli elementi in base alle impostazioni del modulo e variabili come `$combination.id_product_attribute`, `$combination.name`, `$combination.price`, ecc.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle SQL personalizzate.
  - Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop. Le chiavi di configurazione seguirebbero tipicamente un modello come `MYCOMBTABFREE_SETTING_NAME`.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per registrare risorse CSS (`mycombtabfree.css`) e JavaScript (`atc.js`) per il front-office. |
| `displayProductButtons` | Vicino al pulsante "Aggiungi al carrello" sulla pagina del prodotto. | Un hook comune per visualizzare l'elenco delle combinazioni direttamente sotto i dettagli del prodotto. |
| `displayProductExtraContent` | All'interno dell'area delle schede prodotto sulla pagina del prodotto. | Consente all'elenco delle combinazioni di apparire nella propria scheda dedicata. |
| `displayFooterProduct` | Nella parte inferiore del contenuto della pagina del prodotto. | Un'altra possibile posizione per l'elenco delle combinazioni, spesso meno prominente. |
| `actionFrontControllerSetMedia` | Prima che il controller frontale renda il suo output. | Utilizzato per aggiungere file CSS e JS specifici del modulo alla pagina. |
| `moduleRoutes` | Durante l'inizializzazione della riscrittura URL. | (Non esplicitamente utilizzato da questo modulo, ma un hook comune per moduli con URL personalizzati). |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto dedicato agli sviluppatori per il modulo "Combinations List Free", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Assicurati di scaricare l'ultima versione compatibile con la tua installazione PrestaShop dalla cronologia degli ordini.
