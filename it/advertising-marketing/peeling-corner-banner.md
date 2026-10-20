---
title: "Peeling Corner Banner - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Peeling Corner Banner di MyPresta.eu."
sidebar:
  label: "Peeling Corner Banner - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Peeling Corner Banner su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/peeling-corner-banner.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/peeling-corner-banner/)
>
> ---


# Peeling Corner Banner

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, clicca su "Configura" per accedere alle sue impostazioni. Qui potrai personalizzare l'aspetto e il comportamento del tuo banner a strappo.

#### **Immagine per l'angolo (Immagine piccola)**

- **Cosa fa questa impostazione:** Questa è la piccola immagine che appare sull'angolo arricciato della tua pagina. È l'anteprima iniziale che cattura l'attenzione del cliente.
- **Effetto della modifica di questa impostazione:**
  - *Quando un'immagine viene caricata:* Questa immagine verrà visualizzata sull'angolo piccolo e arricciato.
  - *Quando nessuna immagine viene caricata:* L'angolo potrebbe apparire vuoto o utilizzare uno stile predefinito, il che è meno efficace.
- **Valore consigliato:** Carica un'immagine piccola e accattivante (es. una piccola icona, un tag "Saldi" o un frammento di logo) che suggerisca la promozione senza rivelare tutto.
- **Scenario/esempio per il commerciante:** Stai organizzando una vendita estiva. Potresti caricare una piccola immagine di un'icona del sole o un piccolo badge "SALDI" per questa impostazione.

#### **Immagine per il banner (Immagine grande)**

- **Cosa fa questa impostazione:** Questa è l'immagine principale del banner che viene rivelata quando un cliente passa il mouse sull'angolo. Qui dovrebbe essere il tuo messaggio principale, l'immagine del prodotto o la call to action.
- **Effetto della modifica di questa impostazione:**
  - *Quando un'immagine viene caricata:* Questa immagine più grande verrà visualizzata quando l'angolo si stacca.
  - *Quando nessuna immagine viene caricata:* L'area staccata sarà vuota, rendendo il modulo inefficace.
- **Valore consigliato:** Carica un'immagine chiara e accattivante che contenga il tuo messaggio promozionale completo, una foto del prodotto o una forte call to action. Assicurati che sia dimensionata in modo appropriato per un banner (es. 200-300px di larghezza, altezza simile).
- **Scenario/esempio per il commerciante:** Seguendo l'esempio della vendita estiva, questa immagine sarebbe un banner completo che annuncia "Saldi Estivi! Fino al 50% di sconto su tutti i costumi da bagno!" con foto di prodotti accattivanti.

#### **Link per il banner**

- **Cosa fa questa impostazione:** Questo è l'URL (indirizzo web) a cui i clienti verranno reindirizzati quando cliccano sul banner rivelato.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene inserito un URL valido:* Cliccando sul banner si aprirà quella pagina.
  - *Quando lasciato vuoto o viene inserito un URL non valido:* Cliccando sul banner potrebbe non succedere nulla o portare a una pagina di errore, frustrando i clienti.
- **Valore consigliato:** Fornisci sempre un URL completo e valido (es. `https://tuonegozio.com/categoria-saldi-estivi`).
- **Scenario/esempio per il commerciante:** Collegheresti questo alla tua pagina di categoria dedicata ai "Saldi Estivi" o a una pagina prodotto specifica che vuoi evidenziare.

#### **Posizione del banner**

- **Cosa fa questa impostazione:** Controlla in quale angolo del tuo sito web appare il banner a strappo.
- **Effetto della modifica di questa impostazione:**
  - *Sinistra:* Il banner apparirà nell'angolo in alto a sinistra della finestra del browser.
  - *Destra:* Il banner apparirà nell'angolo in alto a destra della finestra del browser.
- **Valore consigliato:** Scegli l'angolo che meglio si adatta al design del tuo sito web e non oscura elementi importanti. "Destra" è spesso una buona impostazione predefinita in quanto è meno comune che la navigazione o i loghi si trovino lì.
- **Scenario/esempio per il commerciante:** Se il tuo logo principale e la navigazione sono a sinistra, sceglieresti "Destra" per evitare l'ingombro visivo.

#### **Abilita/Disabilita Modulo**

- **Cosa fa questa impostazione:** Questo è un interruttore principale per attivare o disattivare l'intera funzionalità del banner a strappo senza disinstallare il modulo.
- **Effetto della modifica di questa impostazione:**
  - *Abilitato:* Il banner a strappo sarà visibile nel tuo front office secondo le altre impostazioni.
  - *Disabilitato:* Il banner a strappo non apparirà nel tuo front office.
- **Valore consigliato:** "Abilitato" quando vuoi usare il banner, "Disabilitato" se hai bisogno di nasconderlo temporaneamente per manutenzione o durante periodi specifici.
- **Scenario/esempio per il commerciante:** Hai terminato la tua promozione natalizia e vuoi nascondere temporaneamente il banner fino alla prossima campagna. Lo disabiliteresti qui.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Immagine per l'angolo | Carica piccola immagine teaser | Piccola immagine sull'angolo arricciato. Cattura l'attenzione. |
| Configurazione Modulo | Immagine per il banner | Carica immagine promozionale più grande | Immagine principale del banner rivelata al passaggio del mouse. Contiene il messaggio principale. |
| Configurazione Modulo | Link per il banner | URL completo (es. `https://tuonegozio.com/promo`) | URL di destinazione quando si clicca sul banner. Dirige il traffico. |
| Configurazione Modulo | Posizione del banner | Destra | In quale angolo dello schermo appare il banner (Sinistra/Destra). |
| Configurazione Modulo | Abilita/Disabilita Modulo | Abilitato | Interruttore principale per mostrare o nascondere il banner nel negozio. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Il mio banner non viene visualizzato dopo la configurazione. Cosa devo fare?**
R:

1. **Controlla "Abilita/Disabilita Modulo":** Assicurati che il modulo sia abilitato nella sua configurazione.
2. **Verifica i caricamenti delle immagini:** Assicurati che sia "Immagine per l'angolo" che "Immagine per il banner" siano state caricate con successo.
3. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo back office di PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, i vecchi file memorizzati nella cache impediscono la visualizzazione dei nuovi contenuti del modulo.
4. **Hook del modulo:** Il modulo dovrebbe agganciarsi automaticamente a `displayHeader`. Se non viene visualizzato, assicurati che sia correttamente agganciato. Puoi verificarlo in **Design > Posizioni** (o **Moduli > Posizioni**). Cerca `peelingcornerbanner` e conferma che sia associato a `displayHeader`.

**D: Le immagini del banner appaiono sfocate o allungate.**
R: Questo di solito significa che le immagini che hai caricato non sono ottimizzate per le dimensioni di visualizzazione del banner.

1. **Dimensioni dell'immagine:** Controlla le dimensioni effettive del banner quando si stacca (potrebbe essere necessario utilizzare gli strumenti per sviluppatori del tuo browser). Quindi, ridimensiona la tua "Immagine per il banner" in modo che corrisponda a queste dimensioni o sia leggermente più grande, garantendo una buona qualità.
2. **Dimensione del file:** Sebbene la qualità sia importante, mantieni le dimensioni dei file immagine il più piccole possibile (sotto 100-200KB) per garantire un caricamento rapido della pagina. Utilizza strumenti come TinyPNG o ottimizzatori di immagini online.

**D: Il banner appare, ma cliccandoci sopra non succede nulla.**
R:

1. **Controlla "Link per il banner":** Torna alla configurazione del modulo e ricontrolla l'URL che hai inserito per il link del banner. Assicurati che sia un URL completo e valido (es. `https://www.tuonegozio.com/categoria/prodotto.html`).
2. **Testa il link:** Copia e incolla il link direttamente nel tuo browser per assicurarti che funzioni correttamente al di fuori del modulo.

**D: Il banner si sovrappone ad altri elementi della mia pagina.**
R:

1. **Cambia posizione:** Prova a cambiare la "Posizione del banner" da Sinistra a Destra (o viceversa) nella configurazione del modulo.
2. **Conflitti con il tema:** Se cambiare la posizione non aiuta, potrebbe essere un conflitto con il CSS specifico del tuo tema PrestaShop. Questo potrebbe richiedere a un webmaster di regolare il CSS del modulo o del tema (vedi Sezione 7 per i dettagli per gli sviluppatori).

**D: Posso avere più banner a strappo?**
R: No, questo modulo è progettato per visualizzare un singolo banner a strappo alla volta. Se ne hai bisogno di più, dovresti duplicare e modificare il modulo, il che richiede competenze da sviluppatore.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Peeling Corner Banner (`pcb`) è un modulo PrestaShop semplice progettato principalmente per iniettare un effetto visivo basato su JavaScript nel front-office. Segue una struttura di modulo PrestaShop di base, utilizzando la classe `Module` per l'installazione, la disinstallazione e la configurazione (`getContent()`). La funzionalità principale si basa su un file JavaScript personalizzato (`peelback.js`) che gestisce la manipolazione del DOM e l'animazione, e un template Smarty (`header.tpl`) per renderizzare la struttura HTML iniziale nell'hook `displayHeader`. Le impostazioni di configurazione sono memorizzate in `ps_configuration`.

### 4.2 Controller (`controllers/`)

- Nessun controller Front-Office personalizzato.
- Nessun controller Admin Back-Office personalizzato.
  La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

- Nessuna classe personalizzata o definizione di `ObjectModel`.
  Tutta la configurazione è gestita tramite `Configuration::get()` e `Configuration::updateValue()`.

### 4.4 Risorse JavaScript (`views/js/`)

- `pcb/peelback.js`
  - **Ambito:** Front-office.
  - **Descrizione:** Questo è il file JavaScript principale responsabile dell'animazione dell'angolo a strappo. Probabilmente inizializza un plugin jQuery o uno script personalizzato che:
    - Rileva la presenza della struttura HTML del banner (es. un `div` con un ID specifico come `#peelback`).
    - Collega i listener di eventi, principalmente `mouseover` e `mouseout`, all'elemento dell'angolo.
    - Al `mouseover`, anima l'immagine del banner più grande per "staccarsi" e apparire (es. modificando le proprietà CSS come `width`, `height`, `top`, `left`, `z-index`).
    - Al `mouseout`, anima il banner di nuovo al suo stato iniziale arricciato.
    - Gestisce l'evento di clic sul banner per reindirizzare all'URL configurato.
    - Probabilmente utilizza la funzione `animate()` di jQuery per transizioni fluide.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessun file CSS dedicato trovato nell'archivio del modulo.
  Ciò implica che lo stile per il banner (posizione iniziale, dimensioni, z-index, ecc.) è:
  1. Iniettato direttamente tramite stili inline all'interno del template `header.tpl`.
  2. Gestito interamente dal JavaScript, che imposta dinamicamente le proprietà CSS.
  3. Si basa su uno stile predefinito minimo del browser o si aspetta che il tema fornisca reset di base.
     Gli sviluppatori che desiderano personalizzare l'aspetto dovranno ispezionare l'HTML e il JavaScript generati per stili inline o classi/stili applicati dinamicamente.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**:
  - `pcb/header.tpl`
    - **Hook:** `displayHeader` (o `displayTop` nelle versioni precedenti, ma `displayHeader` è lo standard per iniettare elementi globali).
    - **Output:** Questo template renderizza la struttura HTML iniziale per il banner a strappo. Tipicamente include:
      - Un `div` contenitore per l'intero banner.
      - Un tag `img` per l'immagine piccola dell'angolo.
      - Un tag `img` per l'immagine del banner più grande (inizialmente nascosta o parzialmente nascosta).
      - Un tag `<a>` che avvolge queste immagini, collegato all'URL configurato.
      - Probabilmente utilizzerà variabili Smarty passate dal metodo `hookDisplayHeader()` del modulo per visualizzare gli URL delle immagini, l'URL del link e la posizione del banner (sinistra/destra).
      - Potrebbe contenere tag `<style>` inline o fare affidamento su `peelback.js` per applicare dinamicamente gli stili.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` (o prefisso `_configuration`) con chiavi come:
    - `PCB_CORNER_IMAGE` (percorso dell'immagine piccola dell'angolo)
    - `PCB_BANNER_IMAGE` (percorso dell'immagine grande del banner)
    - `PCB_BANNER_LINK` (l'URL per il banner)
    - `PCB_BANNER_POSITION` (es. 'left' o 'right')
    - `PCB_ENABLED` (1 per abilitato, 0 per disabilitato)
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Inietta la struttura HTML necessaria per il banner e registra lo script `peelback.js`. |
| `actionFrontControllerSetMedia` | Eseguito quando i media (JS/CSS) vengono impostati per un controller frontale. | (Utilizzato implicitamente da `displayHeader` o `hookDisplayHeader` per registrare JS/CSS, sebbene non sia esplicitamente elencato come hook separato nel metodo `install()` del modulo, è così che PrestaShop gestisce la registrazione dei media). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo Peeling Corner Banner, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire il buon funzionamento e il continuo miglioramento dei nostri moduli.
