---
title: "Scheda prodotti popolari nella homepage - Manuale commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Scheda prodotti popolari nella homepage' di MyPresta.eu."
sidebar:
  label: "Scheda prodotti popolari nella homepage - Manuale commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homepage tab popular products su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-popular-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homepage-tab-popular-products/)
>
> ---


# Scheda prodotti popolari nella homepage

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono generalmente necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca sul pulsante "Configura" accanto al modulo "Scheda prodotti popolari nella homepage" in Gestione moduli. Questo ti porterà alla sua schermata di configurazione principale.

#### Impostazioni generali

- **Cosa fa questa impostazione:** Questo modulo si concentra principalmente sulla visualizzazione dei prodotti popolari. La schermata di configurazione per questo modulo è piuttosto semplice, spesso include le impostazioni standard di notifica degli aggiornamenti di MyPresta.eu. La funzionalità principale di visualizzazione dei "prodotti popolari" è solitamente gestita automaticamente dalla logica interna di PrestaShop per l'identificazione degli articoli popolari (ad esempio, basata su vendite, visualizzazioni o una combinazione).
- **Effetto della modifica di questa impostazione:**
  - **`mypresta_updates` (Abilita/Disabilita notifiche aggiornamenti MyPresta.eu):**
    - *Quando abilitato:* Riceverai notifiche nel tuo back office PrestaShop quando nuove versioni o aggiornamenti importanti per i moduli MyPresta.eu (incluso questo) saranno disponibili. Questo ti aiuta a mantenere i tuoi moduli sicuri e aggiornati con le ultime funzionalità e correzioni di bug.
    - *Quando disabilitato:* Non riceverai queste notifiche. Dovrai controllare manualmente il tuo account MyPresta.eu per gli aggiornamenti.
  - **`update_` e `updatev_` (Parametri di controllo aggiornamenti interni):** Questi sono tipicamente impostazioni interne utilizzate dai moduli MyPresta.eu per gestire e tracciare i controlli degli aggiornamenti. Non sono solitamente destinati all'interazione diretta del commerciante.
- **Valore consigliato:**
  - Per `mypresta_updates`: **SÌ** (Abilitato). Mantenere questa opzione abilitata ti assicura di essere sempre informato sugli aggiornamenti critici, migliorando la sicurezza e le prestazioni del tuo negozio.
  - Per `update_` e `updatev_`: Lasciare come predefinito. Questi sono interni e non dovrebbero essere modificati.
- **Scenario / esempio del commerciante:**
  - Vuoi assicurarti che il tuo negozio stia sempre eseguendo le versioni più recenti e sicure dei tuoi moduli MyPresta.eu. Abilitando le notifiche di aggiornamento, vedrai un avviso chiaro nel tuo pannello di amministrazione PrestaShop ogni volta che viene rilasciato un aggiornamento per "Scheda prodotti popolari nella homepage" (o qualsiasi altro modulo MyPresta.eu). Questo ti consente di scaricare e installare prontamente la nuova versione, beneficiando dei miglioramenti senza dover controllare costantemente manualmente.

#### Nota importante sulla logica dei "Prodotti popolari":

Questo modulo sfrutta i meccanismi esistenti di PrestaShop per determinare cosa costituisce un "prodotto popolare". Tipicamente, PrestaShop identifica i prodotti popolari in base ai dati di vendita (prodotti con il maggior numero di ordini) o alle visualizzazioni. Il modulo stesso di solito non offre impostazioni specifiche per definire la "popolarità" (ad esempio, "mostra i prodotti venduti negli ultimi 30 giorni" o "prodotti con X visualizzazioni"). Si basa sulla funzionalità principale di PrestaShop per questo. Se hai bisogno di influenzare quali prodotti appaiono come "popolari", dovrai generalmente aumentare le loro vendite o la loro visibilità attraverso altri sforzi di marketing.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Notifiche aggiornamenti MyPresta.eu | Abilitato (SÌ) | Ricevi avvisi per gli aggiornamenti del modulo, garantendo sicurezza e nuove funzionalità. |
| Pagina di configurazione del modulo | `update_` | Predefinito | Impostazione interna per il tracciamento degli aggiornamenti. Lasciare invariato. |
| Pagina di configurazione del modulo | `updatev_` | Predefinito | Impostazione interna per il tracciamento degli aggiornamenti. Lasciare invariato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La scheda "Prodotti popolari" non viene visualizzata sulla mia homepage.**
R1:

- **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Scheda prodotti popolari nella homepage" sia installato e abilitato.
- **Svuota la cache:** A volte, la cache di PrestaShop impedisce la visualizzazione di nuovi contenuti. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" se disponibile).
- **Compatibilità del tema:** Sebbene il modulo sia progettato per PrestaShop 1.7.x, 8.x e 9.x, alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Se svuotare la cache non funziona, contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu.
- **Controllo hook:** Assicurati che l'hook `displayHome` sia attivo e renderizzato dal tuo tema.

**D2: I prodotti visualizzati nella scheda "Prodotti popolari" non mi sembrano "popolari".**
R2:

- **Definizione di PrestaShop:** Il modulo si basa sulla logica interna di PrestaShop per identificare i prodotti popolari, che si basa tipicamente sul volume delle vendite o sulle visualizzazioni del prodotto. Se il tuo negozio è nuovo o ha basse vendite, l'elenco dei "popolari" potrebbe non essere così dinamico.
- **Aggiornamento dati:** Assicurati che il tuo negozio abbia dati di vendita recenti. La "popolarità" viene calcolata nel tempo.
- **Cache:** Svuota la cache di PrestaShop come descritto nella D1.

**D3: Posso cambiare il titolo della scheda (ad esempio, da "Prodotti popolari" a "I nostri best-seller")?**
R3:

- Questo modulo utilizza tipicamente un titolo predefinito. Per cambiarlo, di solito dovresti modificare i file di traduzione del modulo o, in alcuni casi, modificare direttamente il file del template.
  - Vai su **Internazionale > Traduzioni**.
  - Seleziona "Traduzioni dei moduli installati", il tuo tema e la tua lingua.
  - Trova il modulo "Scheda prodotti popolari nella homepage" e cerca la stringa del titolo della scheda.
  - Se non è traducibile in questo modo, potrebbe richiedere una piccola modifica al codice in `homepagetabs.tpl` (vedi Sezione 7).

**D4: Lo stile dei prodotti nella scheda non corrisponde al mio tema.**
R4:

- Il modulo utilizza il proprio CSS (`homepagetabs.css`). Il CSS del tuo tema potrebbe sovrascrivere alcuni stili, o gli stili del modulo potrebbero entrare in conflitto.
- **CSS personalizzato:** L'approccio migliore è aggiungere CSS personalizzato al file `custom.css` del tuo tema (o equivalente) per sovrascrivere gli stili del modulo e farlo corrispondere perfettamente al tuo tema. Utilizza gli strumenti per sviluppatori del tuo browser per ispezionare gli elementi e identificare i selettori CSS utilizzati dal modulo.

**D5: Come traduco il titolo della scheda o altri testi del modulo in diverse lingue?**
R5:

- Vai su **Internazionale > Traduzioni** nel tuo back office PrestaShop.
- Seleziona "Traduzioni dei moduli installati", quindi scegli il tuo tema e la lingua in cui vuoi tradurre.
- Trova il modulo "Scheda prodotti popolari nella homepage" nell'elenco e dovresti essere in grado di modificare le stringhe di testo ad esso associate.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Scheda prodotti popolari nella homepage", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo `Scheda prodotti popolari nella homepage` (`homepagetabs`) è un modulo PrestaShop semplice, progettato principalmente per estendere l'hook `displayHome`. Segue un modello standard PrestaShop simile a MVC per i moduli, dove il file principale del modulo (`homepagetabs.php`) gestisce l'installazione, la disinstallazione, la configurazione e la registrazione degli hook. Il modulo inietta una scheda personalizzata e il suo contenuto nella homepage, sfruttando i meccanismi esistenti di PrestaShop per il recupero dei "prodotti popolari".

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la logica è incapsulata all'interno del file principale del modulo e dei suoi template e asset associati.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce alcuna classe personalizzata né estende `ObjectModel`. Opera utilizzando le funzionalità principali di PrestaShop per il recupero dei prodotti.

### 4.4 Asset JavaScript (`views/js/`)

- **`homepagetabs/views/js/homepagetabs.js`**
  - **Ambito:** Front-office.
  - **Scopo:** Questo file contiene probabilmente la logica JavaScript per gestire la funzionalità di cambio scheda sulla homepage. Potrebbe ascoltare gli eventi di clic sulla scheda "Prodotti popolari", mostrare/nascondere il contenuto del prodotto corrispondente e potenzialmente interagire con altre schede della homepage per garantire che solo il contenuto di una scheda sia visibile alla volta. Potrebbe anche includere la logica per il comportamento responsive o il caricamento pigro delle immagini dei prodotti all'interno della scheda.
  - **Funzionalità chiave:**
    - Listener di eventi per i clic sulle schede.
    - Manipolazione del DOM per attivare/disattivare la visibilità degli elenchi di prodotti.
    - Potenziale integrazione con il comportamento predefinito delle schede di PrestaShop o con sistemi di schede di temi personalizzati.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`homepagetabs/views/css/homepagetabs.css`**
  - **Ambito:** Styling del cliente Front-office.
  - **Scopo:** Questo foglio di stile definisce l'aspetto visivo della scheda "Prodotti popolari" e degli elenchi di prodotti al suo interno. Assicura che la scheda sia posizionata e stilizzata correttamente e che la griglia/elenco dei prodotti sia presentata in modo ordinato.
  - **Componenti UI principali stilizzati:**
    - L'intestazione della scheda stessa (ad esempio, `.homepagetabs-tab-title`).
    - Il contenitore per i prodotti popolari (ad esempio, `.homepagetabs-products-container`).
    - Singoli elementi del prodotto all'interno della scheda (ad esempio, immagini del prodotto, nomi, prezzi, pulsanti).
    - Regolazioni responsive per diverse dimensioni dello schermo.
  - **Selettori di classe CSS chiave per l'override:** Gli sviluppatori possono ispezionare l'HTML generato per trovare selettori specifici. Quelli comuni potrebbero includere:
    - `.homepagetabs-tab`
    - `.homepagetabs-tab-content`
    - `.homepagetabs-product-list`
    - `.homepagetabs-product-item`

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:
  - **`homepagetabs/views/templates/hook/homepagetabs.tpl`**
    - **Hook:** `displayHome`
    - **Scopo:** Questo è il template principale del front-office. È responsabile del rendering dell'intestazione della scheda "Prodotti popolari" e del contenitore per l'elenco dei prodotti. Tipicamente itererà su una collezione di prodotti popolari passati ad esso dal metodo `hookDisplayHome` del modulo e renderizzerà ogni prodotto utilizzando un parziale standard di elenco prodotti di PrestaShop (o uno personalizzato definito all'interno del modulo). Questo template è dove viene generata la struttura HTML effettiva per la scheda e il suo contenuto.
- **Template admin (`views/templates/admin/`)**:
  - **`homepagetabs/views/templates/admin/homepagetabs.tpl`**
    - **Scopo:** Questo template renderizza il modulo di configurazione del modulo nel Back Office di PrestaShop. Visualizza le impostazioni per le notifiche di aggiornamento (`mypresta_updates`) e potenzialmente altre opzioni specifiche del modulo, se dovessero essere aggiunte. Utilizza le classi helper di PrestaShop per generare i campi di input e i pulsanti di salvataggio.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Questo modulo non crea alcuna tabella di database personalizzata. Memorizza le sue impostazioni di configurazione (come `mypresta_updates`) nella tabella standard `ps_configuration`.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHome` | Renderizza il contenuto sulla homepage del negozio. | Inietta la scheda "Prodotti popolari" e il suo contenuto nell'area principale della homepage. |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Utilizzato per accodare i file CSS (`homepagetabs.css`) e JavaScript (`homepagetabs.js`) del modulo, assicurando che vengano caricati correttamente per la visualizzazione del front-office. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi domanda relativa al modulo "Scheda prodotti popolari nella homepage", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto e le risorse sono disponibili per assistervi con l'installazione, la configurazione e la risoluzione dei problemi.
