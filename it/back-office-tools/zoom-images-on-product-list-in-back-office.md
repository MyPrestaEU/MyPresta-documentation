---
title: "Zoom immagini nell'elenco prodotti nel back office - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Zoom immagini nell'elenco prodotti nel back office' di MyPresta.eu."
sidebar:
  label: "Zoom immagini nell'elenco prodotti nel back office - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Zoom images on product list in back office su MyPresta.eu](https://mypresta.eu/modules/administration-tools/zoom-images-on-product-list-in-back-office.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/zoom-images-on-product-list-in-back-office/)
>
> ---


# Zoom immagini nell'elenco prodotti nel back office

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo. Verrai indirizzato alla sua schermata di configurazione principale.

Questo modulo ha una configurazione molto semplice, tipicamente composta da un singolo interruttore per abilitare o disabilitare la sua funzionalità.

- **Abilita Zoom nell'Elenco Prodotti:**
  - **Cosa fa questa impostazione:** Questo è l'interruttore principale del modulo. Controlla se la funzione di zoom dell'immagine è attiva o inattiva nell'elenco prodotti del tuo Back Office.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Quando navighi su **Catalogo > Prodotti** nel tuo Back Office, passando il mouse su qualsiasi miniatura dell'immagine del prodotto nell'elenco verrà visualizzata una versione più grande e ingrandita di quell'immagine.
    - *Quando disabilitato (NO):* La funzionalità di zoom verrà disattivata. Passando il mouse sulle immagini dei prodotti non si avrà alcun effetto speciale e vedrai le miniature piccole standard.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio per il commerciante:** Se desideri utilizzare la comoda funzione di zoom per controllare rapidamente le immagini dei prodotti, assicurati che sia impostata su "SÌ". Se ritieni che interferisca con un'altra personalizzazione del Back Office o semplicemente preferisci non usarla, impostala su "NO".

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Zoom nell'Elenco Prodotti | SÌ | Attiva o disattiva la funzione di zoom dell'immagine nell'elenco prodotti del Back Office. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato il modulo, ma lo zoom non funziona nel mio elenco prodotti. Cosa devo fare?**
R:

1. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, la cache di PrestaShop può impedire il caricamento di nuovo JavaScript.
2. **Controlla la console del browser:** Apri gli strumenti per sviluppatori del tuo browser (solitamente F12) e cerca eventuali errori nella scheda "Console". Questo potrebbe indicare un conflitto con un altro modulo o tema.
3. **Conflitti tra moduli:** Disabilita temporaneamente altri moduli che modificano l'elenco prodotti del Back Office (se presenti) per vedere se c'è un conflitto.
4. **Override del tema:** Se stai utilizzando un tema del Back Office pesantemente personalizzato, potrebbe sovrascrivere la struttura standard dell'elenco prodotti, impedendo al modulo di iniettare il suo JavaScript. Contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu.

**D: L'immagine ingrandita appare, ma sembra sfocata o pixelata.**
R: Il modulo visualizza l'immagine che PrestaShop fornisce per l'elenco prodotti. Se l'immagine originale caricata per quel prodotto è a bassa risoluzione, anche la versione ingrandita apparirà sfocata. Assicurati di caricare immagini ad alta risoluzione per i tuoi prodotti.

**D: Questo modulo rallenta il mio Back Office?**
R: No, il modulo è molto leggero. Carica solo una piccola libreria JavaScript e la applica quando passi il mouse su un'immagine. Non esegue operazioni pesanti o query di database che potrebbero influire sulle prestazioni.

**D: Posso personalizzare la dimensione della casella di zoom o il livello di zoom?**
R: Il modulo utilizza uno strumento standard "elevateZoom", che ha alcuni comportamenti predefiniti. Sebbene il modulo stesso non offra opzioni di configurazione per questi aspetti visivi specifici, uno sviluppatore potrebbe potenzialmente modificare il file `zplb.js` per regolare questi parametri. Ciò richiederebbe una codifica personalizzata.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Zoom immagini nell'elenco prodotti nel back office" (`zplb`) è un modulo PrestaShop semplice, ma efficace, progettato principalmente per iniettare JavaScript lato client nell'elenco prodotti del Back Office. Sfrutta il sistema di hook di PrestaShop per caricare le sue risorse e si basa su una libreria JavaScript di terze parti (elevateZoom, sebbene integrata in `zplb.js`) per fornire la funzionalità di zoom. Non introduce nuove tabelle di database o logiche di business complesse.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Questo modulo è esclusivamente per il Back Office.
- **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

- Nessuno. Il modulo non definisce classi personalizzate o istanze di `ObjectModel`. Tutta la logica è contenuta nel file principale `zplb/index.php`.

### 4.4 Risorse JavaScript (`views/js/`)

- `zplb/lib/js/zplb.js`
  - **Ambito:** Back-office. Questo script viene caricato specificamente sulla pagina dell'elenco prodotti del Back Office.
  - **Funzionalità:** Questo file contiene la logica JavaScript principale per la funzione di zoom. Probabilmente include o integra la libreria "elevateZoom". Si rivolge agli elementi dell'immagine del prodotto all'interno della tabella dell'elenco prodotti del Back Office (ad esempio, `img.img-thumbnail` o selettori simili utilizzati dall'elenco prodotti di PrestaShop). Lega gli eventi mouseover/hover a queste immagini e inizializza la funzionalità di zoom, creando la vista ingrandita.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessuno. Il modulo non include alcun file CSS personalizzato. Lo stile per la casella di zoom è tipicamente gestito dalla libreria JavaScript stessa, spesso iniettando stili in linea o utilizzando uno stile predefinito minimo che si integra bene con il Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

- Nessuno. Il modulo non utilizza alcun file `.tpl`. La sua funzionalità viene iniettata direttamente tramite JavaScript nella struttura HTML esistente dell'elenco prodotti del Back Office.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:
  - Il modulo non crea tabelle di database personalizzate.
  - Memorizza la sua configurazione (ad esempio, l'impostazione "Abilita Zoom") nella tabella `ps_configuration`, utilizzando una chiave come `ZPLB_ENABLED`.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` di ogni pagina del Back Office. | Utilizzato per caricare condizionalmente lo script `zplb.js` solo quando la pagina corrente del Back Office è l'elenco prodotti (`AdminProducts`). Ciò garantisce che lo script non venga caricato inutilmente su altre pagine di amministrazione, ottimizzando le prestazioni. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Zoom immagini nell'elenco prodotti nel back office", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità e compatibilità del modulo.
