---
title: "Ordine creato da dipendente - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Ordine creato da dipendente' di MyPresta.eu."
sidebar:
  label: "Ordine creato da dipendente - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Order created by employee su MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-created-by-employee.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/order-created-by-employee/)
>
> ---


# Ordine creato da dipendente

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL) tipicamente disponibili su qualsiasi ambiente di hosting compatibile con PrestaShop.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando sul pulsante "Configura" verrai indirizzato alla pagina di configurazione principale del modulo.

Questo modulo è progettato per essere estremamente semplice ed efficace, richiedendo una configurazione minima. Dopo l'installazione, inizia automaticamente a raccogliere i dati necessari.

**Cosa fa questa schermata:**
Questa pagina serve come conferma che il modulo è installato e attivo. Non presenta alcuna impostazione configurabile perché la funzionalità principale del modulo (registrazione degli ordini creati dai dipendenti) è abilitata per impostazione predefinita all'installazione.

**Effetto della modifica di questa impostazione:**
Non ci sono impostazioni da modificare su questa schermata. La funzionalità del modulo è "sempre attiva" una volta installato.

**Valore consigliato:**
Nessun valore da impostare. Assicurati semplicemente che il modulo sia installato e abilitato.

**Scenario / esempio del commerciante:**
Hai appena installato il modulo. Navighi alla sua pagina di configurazione e vedi un semplice messaggio che ne conferma lo stato. Da questo momento in poi, ogni nuovo ordine creato da un dipendente tramite il Back Office di PrestaShop sarà contrassegnato come tale. Quando visualizzi i dettagli di un ordine, vedrai una nuova sezione che indica se è stato creato da un dipendente e quale dipendente lo ha fatto.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo non aggiunge nuove voci di menu dedicate o schermate di amministrazione complesse. La sua funzionalità si integra direttamente nella pagina dei dettagli dell'ordine esistente di PrestaShop.

**Nome schermata e posizione nel menu:**
Le informazioni fornite da questo modulo vengono visualizzate direttamente nella **Pagina dei dettagli dell'ordine**.
Per accedervi:

1. Naviga su **Ordini > Ordini** nel tuo Back Office di PrestaShop.
2. Clicca su qualsiasi ordine dall'elenco per visualizzarne i dettagli.

**Azioni e impostazioni disponibili:**
Nella Pagina dei dettagli dell'ordine, troverai una nuova sezione (tipicamente vicino alla parte superiore o in un blocco dedicato) che mostra se l'ordine è stato creato da un dipendente. In tal caso, mostrerà anche il nome del dipendente che lo ha creato.

**Effetto delle modifiche:**
Non ci sono azioni o impostazioni da modificare in questa vista. Questa sezione è puramente informativa, fornendoti i dati raccolti dal modulo.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
Quando esamini gli ordini, specialmente quelli che sembrano insoliti, o quando esegui audit interni, controlla sempre la sezione "Ordine creato da dipendente" nella pagina dei dettagli dell'ordine. Questo rapido controllo può fornire un contesto immediato sull'origine dell'ordine, aiutandoti a capire se si trattava di un acquisto diretto del cliente o di un inserimento interno.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | *(Nessuna impostazione configurabile)* | N/A | Conferma l'installazione e l'attivazione del modulo. La funzionalità del modulo è sempre attiva. |
| Pagina Dettagli Ordine (Back Office) | Blocco informazioni "Ordine creato da dipendente" | N/A | Mostra se l'ordine è stato creato da un dipendente e il suo nome. Puramente informativo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo alcuna modifica sugli ordini vecchi.**
R: Questo modulo inizia a raccogliere dati dal momento in cui viene installato. Non può determinare retroattivamente se gli ordini passati sono stati creati da un dipendente. Vedrai le informazioni "Ordine creato da dipendente" solo sugli ordini effettuati *dopo* che il modulo è stato installato e attivo con successo.

**D: Ho creato un ordine nel Back Office, ma non vedo le informazioni sul dipendente nella pagina dei dettagli dell'ordine.**
R: Innanzitutto, assicurati che il modulo sia installato e abilitato (controlla **Moduli > Gestione moduli**). Se lo è, svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**). Se il problema persiste, assicurati di visualizzare un ordine che è stato *effettivamente creato da un dipendente* nel Back Office *dopo* l'installazione del modulo.

**D: Questo modulo influisce sulle prestazioni del mio negozio?**
R: No, il modulo è molto leggero. Aggiunge solo un piccolo dato durante il processo di creazione dell'ordine nel Back Office e visualizza quel dato nella pagina dei dettagli dell'ordine. Non ha alcun impatto sulle prestazioni del tuo front office o sull'esperienza del cliente.

**D: Posso disabilitare la funzionalità del modulo senza disinstallarlo?**
R: Questo modulo non ha un interruttore on/off nella sua configurazione. Per interrompere la sua funzionalità, dovresti disabilitare o disinstallare il modulo tramite il Gestore moduli. Tuttavia, data la sua natura benefica per il tracciamento interno, è generalmente consigliato mantenerlo attivo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Ordine creato da dipendente" (`logoe`) è un modulo PrestaShop semplice progettato per estendere la funzionalità principale dell'oggetto `Order`. Opera principalmente agganciandosi al processo di creazione dell'ordine all'interno del Back Office per registrare l'`id_employee` responsabile dell'ordine. Queste informazioni vengono quindi visualizzate sulla pagina dei dettagli dell'ordine esistente nel Back Office. Segue un semplice modello basato su eventi utilizzando gli hook di PrestaShop.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Tutta la sua logica è gestita all'interno del file principale del modulo e tramite hook.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce alcuna classe personalizzata o definizione di `ObjectModel`. Interagisce direttamente con l'oggetto `Order` e `Configuration` per le sue impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Lo stile per le informazioni visualizzate è tipicamente minimale e si basa sugli stili esistenti del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo utilizza un singolo file di template per visualizzare le informazioni nel Back Office.

- **Template di amministrazione (`views/templates/admin/`)**:
  - `logoe/views/templates/admin/logoelog.tpl`: Questo template è responsabile del rendering del blocco di informazioni "Ordine creato da dipendente" nella pagina dei dettagli dell'ordine del Back Office di PrestaShop. Tipicamente visualizza il nome del dipendente se l'ordine è stato creato da un dipendente. È probabile che venga renderizzato tramite un hook come `displayAdminOrder` o `displayAdminOrderTabContent`.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:
  Il modulo non crea una nuova tabella di database dedicata. Invece, estende la tabella `ps_orders` esistente aggiungendo una nuova colonna durante l'installazione.

  - `ps_orders`: Una nuova colonna, probabilmente `id_employee_created`, viene aggiunta a questa tabella per memorizzare l'ID del dipendente che ha creato l'ordine. Questa colonna sarebbe `INT(10) UNSIGNED` e nullable, con un valore predefinito di `NULL`.
- **Tabella degli hook registrati**:

  | Nome Hook | Tempo di esecuzione | Scopo tecnico |
  | --- | --- | --- |
  | `actionOrderAdd` | Dopo che un nuovo ordine è stato aggiunto con successo al database. | Questo hook è cruciale. Viene utilizzato per catturare l'`id_employee` dalla sessione corrente del Back Office e aggiornare la colonna `id_employee_created` del nuovo ordine in `ps_orders`. |
  | `displayAdminOrder` (o simile, ad esempio, `displayAdminOrderTabContent`, `displayAdminOrderMain`) | Quando viene renderizzata la pagina dei dettagli dell'ordine del Back Office. | Questo hook viene utilizzato per iniettare il template `logoelog.tpl` nella pagina dei dettagli dell'ordine, visualizzando le informazioni `id_employee_created` (ad esempio, il nome del dipendente). |

## 5. Supporto ufficiale e aggiornamenti

Per supporto ufficiale, aggiornamenti del modulo e qualsiasi ulteriore assistenza, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire supporto tempestivo e a garantire che il tuo modulo funzioni perfettamente.
