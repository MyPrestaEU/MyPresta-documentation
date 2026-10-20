---
title: "Modifica data prodotto - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Modifica data prodotto' di MyPresta.eu."
sidebar:
  label: "Modifica data prodotto - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product date change su MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-date-change.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/product-date-change/)
>
> ---


# Modifica data prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina di configurazione principale del modulo "Modifica data prodotto". Qui potrai selezionare i prodotti e modificare le loro date.

#### **Selezione Prodotto**

- **Cosa fa questa impostazione:** Questa sezione ti permette di cercare e selezionare i prodotti specifici di cui desideri modificare le date.
- **Effetto della modifica di questa impostazione:**
  - *Ricerca di un prodotto:* Digitando nella casella di ricerca filtrerai l'elenco dei prodotti, rendendo più facile trovare il prodotto esatto di cui hai bisogno.
  - *Selezione di un prodotto:* Una volta selezionato un prodotto, verranno visualizzate le sue attuali date di creazione e aggiornamento, e potrai inserire nuove date.
- **Valore consigliato:** Utilizza la barra di ricerca per individuare rapidamente i prodotti per nome o ID.
- **Scenario / esempio per il commerciante:** Vuoi cambiare la data per "Vestito Estivo 2023". Digiti "Vestito Estivo" nella casella di ricerca e il modulo visualizza i prodotti corrispondenti. Quindi clicchi su "Vestito Estivo 2023" per selezionarlo.

#### **Modifica Data Creazione Prodotto**

- **Cosa fa questa impostazione:** Questo campo ti permette di impostare una nuova `date_add` (data di creazione) per il prodotto selezionato. Questa data è spesso utilizzata da PrestaShop per determinare se un prodotto è "nuovo".
- **Effetto della modifica di questa impostazione:**
  - *Quando viene inserita e salvata una nuova data:* La data di creazione del prodotto nel tuo database verrà aggiornata. Questo può far sì che il prodotto riappaia nei blocchi "Nuovi Prodotti" o cambi la sua posizione quando si ordina per "Data di aggiunta".
  - *Quando lasciato invariato:* La data di creazione originale del prodotto verrà preservata.
- **Valore consigliato:** Imposta una data che rifletta quando vuoi che il prodotto sia considerato "nuovo" o quando è stato effettivamente aggiunto al tuo catalogo. Per la rievidenziazione, una data recente (oggi o ieri) è l'ideale.
- **Scenario / esempio per il commerciante:** Il tuo prodotto "Cappotto Invernale" è stato aggiunto l'anno scorso. Vuoi promuoverlo come "nuovo arrivo" per la prossima stagione invernale. Selezioni il prodotto, quindi imposti "Modifica Data Creazione Prodotto" alla data odierna. Ora, apparirà nella tua sezione "Nuovi Prodotti".

#### **Modifica Data Aggiornamento Prodotto**

- **Cosa fa questa impostazione:** Questo campo ti permette di impostare una nuova `date_upd` (data dell'ultimo aggiornamento) per il prodotto selezionato. Questa data viene utilizzata per il tracciamento interno e può anche influenzare l'ordinamento dei prodotti.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene inserita e salvata una nuova data:* La data dell'ultimo aggiornamento del prodotto nel tuo database verrà modificata. Questo può influenzare le opzioni di ordinamento in cui i clienti ordinano per "Data di aggiornamento".
  - *Quando lasciato invariato:* La data di aggiornamento originale del prodotto verrà preservata.
- **Valore consigliato:** Imposta una data che rifletta l'ultima volta che hai apportato modifiche significative al prodotto (ad esempio, descrizione aggiornata, prezzo, immagini) o se vuoi portarlo in cima agli elenchi di "aggiornati di recente".
- **Scenario / esempio per il commerciante:** Hai appena aggiornato la descrizione e aggiunto nuove immagini per il tuo prodotto "Chicchi di Caffè Biologici". Vuoi che questo prodotto appaia più in alto quando i clienti ordinano per "aggiornati di recente". Selezioni il prodotto e imposti "Modifica Data Aggiornamento Prodotto" alla data odierna.

#### **Pulsante Salva**

- **Cosa fa questa impostazione:** Questo pulsante applica tutte le modifiche di data che hai apportato per il prodotto selezionato.
- **Effetto della modifica di questa impostazione:** Cliccando su "Salva" verranno salvate le nuove date di creazione e/o aggiornamento nel tuo database PrestaShop. Di solito vedrai un messaggio di successo.
- **Valore consigliato:** Clicca sempre su "Salva" dopo aver apportato qualsiasi modifica alle date.
- **Scenario / esempio per il commerciante:** Dopo aver impostato sia la data di creazione che quella di aggiornamento per le tue "Sneakers Edizione Limitata", clicchi su "Salva" per applicare queste modifiche al tuo negozio.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Campo di ricerca prodotto | N/A | Trova prodotti per nome o ID per modificarne le date. |
| Pagina di configurazione del modulo | Modifica Data Creazione Prodotto | `date_add` corrente del prodotto | Imposta una nuova data di creazione. Influisce sulla visibilità dei "Nuovi Prodotti" e sull'ordinamento per "Data di aggiunta". Consigliato: Una data recente per la rievidenziazione. |
| Pagina di configurazione del modulo | Modifica Data Aggiornamento Prodotto | `date_upd` corrente del prodotto | Imposta una nuova data dell'ultimo aggiornamento. Influisce sull'ordinamento per "Data di aggiornamento". Consigliato: Una data recente dopo modifiche significative al prodotto. |
| Pagina di configurazione del modulo | Pulsante Salva | N/A | Applica tutte le modifiche di data selezionate al prodotto nel database. |

## 3. Risoluzione dei problemi per il commerciante e Domande Frequenti (FAQ)

**D1: Ho cambiato la data, ma il prodotto non appare come "nuovo" sulla mia homepage. Cosa c'è che non va?**
R1:

- **Svuota la cache:** PrestaShop si basa molto sulla cache. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). Questa è la soluzione più comune.
- **Configurazione del modulo:** Controlla le impostazioni del tuo modulo "Nuovi Prodotti" (ad esempio, "Blocco nuovi prodotti" o "Pagina nuovi prodotti"). Assicurati che sia configurato per visualizzare i prodotti in base alla loro data di creazione e che il numero di giorni per i prodotti "nuovi" sia impostato in modo appropriato (ad esempio, 30 giorni). Se imposti la data di creazione di un prodotto in modo che sia più vecchia di questa soglia, non apparirà come nuovo.
- **Specifiche del tema:** Alcuni temi potrebbero avere la propria cache o logica personalizzata per i "nuovi prodotti". Se svuotare la cache non funziona, consulta la documentazione o il supporto del tuo tema.

**D2: La modifica della data del prodotto influirà sulla mia SEO?**
R2: Direttamente, no. I motori di ricerca come Google si concentrano principalmente sul contenuto della pagina del tuo prodotto (descrizione, immagini, recensioni) e sui link esterni, non sulle date interne dei prodotti PrestaShop. Tuttavia, indirettamente, se la modifica della data fa apparire il prodotto come "nuovo" e genera più traffico interno o vendite, quell'aumento di coinvolgimento *può* influenzare positivamente la SEO nel tempo. Si tratta più di esperienza utente e merchandising che di manipolazione diretta della SEO.

**D3: Posso cambiare le date per più prodotti contemporaneamente (modifica in blocco)?**
R3: Questo modulo è progettato per modifiche individuali delle date dei prodotti. Se hai bisogno di modificare in blocco le date per un gran numero di prodotti, avresti tipicamente bisogno di uno strumento di importazione/esportazione più avanzato o di uno script personalizzato. Per pochi prodotti, farli uno per uno con questo modulo è efficiente.

**D4: Cosa succede se imposto una data futura?**
R4: PrestaShop accetterà una data futura. Tuttavia, l'effetto pratico potrebbe essere limitato. Un prodotto impostato con una data di creazione futura potrebbe non apparire negli elenchi di "nuovi prodotti" fino a quando quella data non arriva. Si consiglia generalmente di utilizzare date attuali o passate.

**D5: Ho cambiato la data, ma quando modifico il prodotto nel Back Office, la vecchia data è ancora lì.**
R5: Questo modulo modifica direttamente i campi `date_add` e `date_upd` nel database. Quando visualizzi un prodotto nella pagina di modifica standard del prodotto PrestaShop, dovrebbe riflettere queste modifiche. Se non lo fa, assicurati di aver cliccato su "Salva" nella configurazione del modulo, di aver svuotato la cache di PrestaShop e di aver ricaricato la pagina di modifica del prodotto. Se il problema persiste, potrebbe esserci un conflitto con un altro modulo o un problema di caching più profondo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente riservata a sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Product date change` (`pdc`) è un modulo PrestaShop semplice progettato per interagire direttamente con l'ObjectModel `Product`. Sfrutta il metodo standard `getContent()` per la sua configurazione nel Back Office, fornendo un semplice modulo per selezionare un prodotto e modificare i suoi campi `date_add` e `date_upd`. Non introduce nuove tabelle di database, controller complessi o logica estesa per il front-office, rendendolo leggero e focalizzato sul suo compito amministrativo principale.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene controller front-office o back-office personalizzati. Tutta la logica è incapsulata all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non introduce classi o ObjectModels personalizzati nella directory `classes/`. Interagisce direttamente con l'ObjectModel `Product` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include file JavaScript personalizzati.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include file CSS personalizzati. Lo stile dovrebbe essere gestito dagli stili predefiniti del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`pdc/views/pdc.tpl`**:
  - **Ambito**: Configurazione amministrativa del Back-office.
  - **Scopo**: Questo template renderizza il modulo di configurazione principale per il modulo. Include:
    - Un campo di input di ricerca per trovare i prodotti.
    - Aree di visualizzazione per la `date_add` e `date_upd` correnti del prodotto selezionato.
    - Campi di input (probabilmente selettori di data) per impostare nuovi valori `date_add` e `date_upd`.
    - Un pulsante di invio per salvare le modifiche.
  - **Utilizzo**: Questo template viene renderizzato dal metodo `getContent()` del modulo `pdc`.
  - **Selettori chiave**: Gli sviluppatori possono ispezionare l'HTML generato per ID o classi specifiche per sovrascrivere lo stile se necessario, anche se tipicamente non richiesto per un semplice modulo amministrativo.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle di database personalizzate.
  - Modifica direttamente le colonne `date_add` e `date_upd` all'interno della tabella `ps_product` esistente (e potenzialmente `ps_product_shop` se vengono gestite date specifiche per il contesto, sebbene la descrizione del modulo implichi una modifica diretta dell'oggetto prodotto).
  - I valori di configurazione (se presenti, anche se nessuno è esplicitamente elencato oltre la manipolazione diretta del prodotto) verrebbero memorizzati in `ps_configuration`.
- **Tabella degli hook registrati**:
  Questo modulo non registra alcun hook specifico per la visualizzazione front-office o le azioni back-office oltre allo standard `displayBackOfficeHeader` (per le risorse, se presenti) e `moduleRoutes` (se fossero necessari URL personalizzati, cosa che non è per questo modulo). La sua interazione principale avviene tramite il metodo `getContent()`.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` delle pagine del Back Office. | (Potenzialmente) Per includere eventuali JS/CSS necessari per la pagina di configurazione del modulo, anche se nessuno è presente in questo modulo. |
| `actionProductUpdate` | Eseguito dopo l'aggiornamento di un prodotto. | La logica interna del modulo per l'aggiornamento delle date dei prodotti potrebbe attivare questo hook, ma il modulo stesso non si registra esplicitamente per ascoltarlo o eseguire azioni basate su di esso. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Modifica data prodotto", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
