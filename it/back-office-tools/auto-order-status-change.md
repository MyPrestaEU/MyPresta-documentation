---
title: "Cambio automatico stato ordine - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Cambio automatico stato ordine di MyPresta.eu."
sidebar:
  label: "Cambio automatico stato ordine - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Auto order status change su MyPresta.eu](https://mypresta.eu/modules/administration-tools/auto-order-status-change.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/auto-order-status-change/)
>
> ---


# Cambio automatico stato ordine

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Cambio automatico stato ordine)

Questa è la schermata di configurazione principale e unica per il modulo "Cambio automatico stato ordine". Qui definirai le regole per come gli stati degli ordini passano automaticamente.

La pagina di configurazione ti presenterà un elenco dei tuoi stati d'ordine attuali. Per ogni stato, potrai definire a quale nuovo stato dovrebbe cambiare automaticamente.

**Come configurare una regola:**

1. **Identifica lo stato "Da":** Sul lato sinistro della tabella di configurazione, vedrai un elenco di tutti i tuoi stati d'ordine esistenti (es. "In attesa di bonifico bancario", "Pagamento accettato", "Spedito", ecc.). Questo è lo *stato iniziale* che attiva il cambio automatico.
2. **Seleziona lo stato "A":** Accanto a ogni stato "Da", troverai un menu a discesa. Questo menu contiene tutti gli stati d'ordine disponibili nel tuo negozio. Seleziona lo stato a cui desideri che l'ordine *cambi automaticamente* quando entra nello stato "Da".
3. **Salva le modifiche:** Dopo aver impostato le transizioni desiderate, assicurati di cliccare sul pulsante **"Salva"** (solitamente in fondo alla pagina) per applicare le tue regole.

Analizziamo le impostazioni tipiche che incontrerai:

#### **Gruppo di impostazioni: Transizioni automatiche di stato**

Questa sezione visualizzerà una tabella o una serie di menu a discesa, che ti consentiranno di mappare gli stati "Da" agli stati "A".

- **Cosa fa questa impostazione:** Questa è la funzionalità principale del modulo. Per ogni stato d'ordine esistente nel tuo negozio, puoi specificare uno *stato di destinazione* a cui un ordine passerà automaticamente *se* il suo stato cambia allo stato "Da".
- **Effetto della modifica di questa impostazione:**
  - *Quando viene selezionato uno stato "A" per uno stato "Da":* Ogni volta che lo stato di un ordine viene aggiornato allo stato "Da" (manualmente da un amministratore, da un gateway di pagamento o da un altro modulo), il modulo tenterà immediatamente di cambiarlo allo stato "A" selezionato.
  - *Quando viene selezionato "Nessun cambiamento" o simile (o lasciato vuoto):* Se non selezioni uno stato "A" per un particolare stato "Da", non si verificherà alcun cambiamento automatico per gli ordini che entrano in quello specifico stato "Da". L'ordine rimarrà semplicemente nello stato "Da" fino a quando non verrà modificato manualmente o agito da un'altra regola/modulo.
- **Valore consigliato:** Questo dipende interamente dal flusso di lavoro del tuo negozio.
  - **Esempio 1 (Pagamento accettato a In elaborazione):**
    - **Stato Da:** `Pagamento accettato`
    - **Stato A:** `In elaborazione` (o `Preparazione in corso`)
    - **Scopo e impatto:** Questa è una configurazione molto comune e altamente raccomandata. Quando un cliente paga e il pagamento viene confermato (es. da PayPal, Stripe, modulo carta di credito), lo stato dell'ordine si aggiorna automaticamente a "Pagamento accettato". Questa regola lo sposta quindi immediatamente a "In elaborazione", segnalando al tuo magazzino o al team di evasione di iniziare a preparare l'ordine senza alcun intervento manuale. Ciò consente di risparmiare tempo e garantisce un'evasione rapida.
  - **Esempio 2 (Spedito a Consegnato):**
    - **Stato Da:** `Spedito`
    - **Stato A:** `Consegnato`
    - **Scopo e impatto:** Mentre "Spedito" indica che l'articolo ha lasciato il tuo magazzino, "Consegnato" conferma che ha raggiunto il cliente. Se l'integrazione del tuo corriere non si aggiorna automaticamente a "Consegnato", potresti impostare questa regola. Tuttavia, fai attenzione: questo presuppone che tutti gli ordini "Spediti" siano alla fine "Consegnati". Spesso è meglio affidarsi al tracciamento del corriere per lo stato "Consegnato" se possibile. Usalo se vuoi eliminare rapidamente gli ordini "Spediti" dal tuo elenco attivo dopo un tempo di consegna ragionevole, ma sii consapevole che potrebbe non riflettere la consegna effettiva.
  - **Esempio 3 (In attesa di bonifico bancario a Annullato - con cautela):**
    - **Stato Da:** `In attesa di bonifico bancario`
    - **Stato A:** `Annullato`
    - **Scopo e impatto:** Se hai una politica rigorosa secondo cui i pagamenti tramite bonifico bancario devono essere ricevuti entro un certo periodo di tempo, e modifichi manualmente gli ordini in ritardo in "Annullato", questo modulo potrebbe automatizzarlo. Tuttavia, il modulo si attiva *quando lo stato cambia a* "In attesa di bonifico bancario". Se vuoi annullare *dopo un ritardo*, questo modulo da solo non lo farà. Avresti bisogno di un altro meccanismo (es. un cron job o un altro modulo) per cambiare lo stato a "In attesa di bonifico bancario" *dopo* il ritardo, il che attiverebbe quindi questo modulo per cambiarlo in "Annullato". Questo caso d'uso specifico è meno diretto per l'attivazione immediata di questo modulo.
- **Scenario / esempio del commerciante:**
  - "Voglio che tutti gli ordini che completano con successo il pagamento passino automaticamente a 'Preparazione in corso' in modo che il mio team di imballaggio sappia di iniziare a lavorarci immediatamente."
  - "Quando un cliente richiede un rimborso e io cambio lo stato dell'ordine in 'Rimborsato', voglio che passi automaticamente a 'Chiuso' in modo che non sia più nel mio elenco di ordini attivi."

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | `Stato Da` (es. Pagamento accettato) | Varia in base al flusso di lavoro | Lo stato iniziale che attiva un cambiamento automatico. |
| Configurazione modulo | `Stato A` (menu a discesa per ogni `Stato Da`) | `In elaborazione` (per `Pagamento accettato`) | Lo stato di destinazione a cui un ordine passerà automaticamente quando entra nello `Stato Da`. Automatizza il flusso di lavoro, risparmia tempo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei stati d'ordine non cambiano automaticamente. Cosa devo controllare?**

- **R:** Innanzitutto, vai su **Moduli > Gestione moduli > Cambio automatico stato ordine > Configura** e assicurati di aver impostato correttamente gli stati "Da" e "A".
- **R:** Verifica che il cambio di stato iniziale (lo stato "Da") stia effettivamente avvenendo. Ad esempio, se ti aspetti che "Pagamento accettato" attivi un cambiamento, assicurati che l'ordine raggiunga prima "Pagamento accettato".
- **R:** Svuota la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" in alto a destra. A volte, le configurazioni dei moduli necessitano di un aggiornamento della cache per avere effetto.

**D2: Questo modulo può cambiare gli stati in base a un ritardo temporale (es. annullare un ordine se non pagato entro 24 ore)?**

- **R:** No, questo modulo si attiva *immediatamente* quando lo stato di un ordine *cambia* a uno specifico stato "Da". Non ha funzionalità integrate per ritardi basati sul tempo o cron job. Per azioni basate sul tempo, avresti bisogno di un modulo separato o di uno sviluppo personalizzato che cambi lo stato dell'ordine dopo un ritardo, il che attiverebbe quindi questo modulo.

**D3: Questo modulo interferirà con gli aggiornamenti di stato del mio gateway di pagamento?**

- **R:** No, funziona *con* essi. I gateway di pagamento in genere aggiornano un ordine a uno stato come "Pagamento accettato" o "In attesa di pagamento". Questo modulo interviene *dopo* quell'aggiornamento iniziale, applicando la tua prossima regola. Non impedisce al gateway di pagamento di impostare il suo stato iniziale.

**D4: Ho un tema personalizzato. Questo modulo funzionerà?**

- **R:** Sì, assolutamente. Questo modulo opera interamente nel back-office di PrestaShop e sulla logica di elaborazione degli ordini. Non ha componenti visivi front-office o stili specifici del tema, quindi è pienamente compatibile con qualsiasi tema PrestaShop.

**D5: Come traduco le impostazioni del modulo se il mio back-office è in un'altra lingua?**

- **R:** PrestaShop gestisce automaticamente la traduzione degli stati degli ordini. Il modulo utilizza i nomi dei tuoi stati d'ordine esistenti. Se hai bisogno di tradurre gli elementi dell'interfaccia del modulo stesso (come il pulsante "Salva" o i titoli delle sezioni), puoi farlo tramite **Internazionale > Traduzioni** nel tuo back-office di PrestaShop. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, la tua lingua e quindi trova il modulo "schange".

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Cambio automatico stato ordine".

### 4.1 Panoramica dell'architettura

Il modulo "Cambio automatico stato ordine" (`schange`) è un modulo PrestaShop semplice progettato principalmente per agganciarsi all'evento `actionOrderStatusPostUpdate`. Segue una struttura standard del modulo PrestaShop, sfruttando la classe `Module` per l'installazione, la disinstallazione e la configurazione. La sua logica principale risiede nel file del modulo principale, elaborando i cambiamenti di stato in base alle configurazioni memorizzate in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del file del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** definisce alcuna classe personalizzata o istanza di `ObjectModel` in una directory `classes/`. Tutta la logica è incapsulata all'interno della classe principale `schange`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato. Lo stile per la pagina di configurazione è gestito dal CSS predefinito del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza un singolo template Smarty per la sua interfaccia di configurazione.

- **Template amministrativi (`views/templates/admin/`)**:
  - `schange/views/tpl/selectedProducts.tpl`: Questo template viene utilizzato all'interno del metodo `getContent()` per renderizzare il modulo di configurazione del modulo. Tipicamente visualizza l'elenco degli stati d'ordine "Da" e i relativi menu a discesa dello stato "A". Gli sviluppatori possono ispezionare questo file per comprendere la struttura del modulo di configurazione e come viene presentata la mappatura dello stato.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Questo modulo **non** crea alcuna tabella SQL personalizzata.
  - Tutte le impostazioni di configurazione (le mappature degli stati "Da" a "A") sono memorizzate nella tabella `ps_configuration`. Ogni mappatura è probabilmente memorizzata come una chiave di configurazione separata, o un array serializzato sotto una singola chiave, utilizzando il nome del modulo come prefisso (es. `SCHANGE_STATUS_FROM_X_TO_Y` o `SCHANGE_STATUS_MAP`).
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Attivato immediatamente dopo che lo stato di un ordine è stato aggiornato con successo. | Questo è l'hook principale utilizzato dal modulo. Quando lo stato di un ordine cambia (es. da "In attesa di pagamento" a "Pagamento accettato"), questo hook si attiva. Il modulo quindi controlla se il nuovo stato (lo stato "Da") ha uno stato "A" configurato. Se esiste una mappatura, il modulo aggiorna programmaticamente l'ordine allo stato "A" designato. |

### 4.8 File del modulo principale (`schange/index.php`)

- **Nome della classe**: `schange`
- **Classe genitore**: `Module`
- **Metodi chiave**:
  - `__construct()`: Inizializza i metadati del modulo (nome, scheda, versione, autore, ecc.).
  - `install()`: Registra l'hook `actionOrderStatusPostUpdate` e potenzialmente imposta i valori di configurazione predefiniti.
  - `uninstall()`: Deregistra l'hook e pulisce i valori di configurazione da `ps_configuration`.
  - `getContent()`: Renderizza la pagina di configurazione del modulo nel Back Office. Questo metodo gestisce l'invio del modulo, salva le impostazioni in `ps_configuration` e visualizza l'interfaccia di mappatura dello stato utilizzando `selectedProducts.tpl`.
  - `hookActionOrderStatusPostUpdate($params)`: Questo è il gestore della logica principale.
    - Riceve `$params` contenente `newOrderStatus` e `id_order`.
    - Recupera le mappature di stato configurate da `ps_configuration`.
    - Se `newOrderStatus` corrisponde a uno stato "Da" configurato, carica l'oggetto `Order` per `id_order`.
    - Tenta quindi di aggiornare lo stato dell'ordine allo stato "A" corrispondente utilizzando `Order->setCurrentState()`.
    - Assicura che il cambio di stato sia valido e gestisce potenziali errori.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Cambio automatico stato ordine", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
"""
