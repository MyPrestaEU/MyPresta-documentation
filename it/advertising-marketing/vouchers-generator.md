---
title: "Generatore di Buoni - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Generatore di Buoni di MyPresta.eu."
sidebar:
  label: "Generatore di Buoni - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Vouchers Generator su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/vouchers-generator.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/vouchers-generator/)
>
> ---


# Generatore di Buoni

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, naviga su **Moduli > Gestione Moduli** e clicca su "Configura" accanto a "Generatore di Buoni". Questa è la schermata principale dove gestirai tutte le impostazioni e genererai i tuoi buoni.

La pagina di configurazione è progettata per essere intuitiva, permettendoti di definire le regole per i tuoi nuovi buoni e poi generarli.

#### **1. Impostazioni di Generazione Buoni**

Questa sezione ti permette di definire le proprietà principali dei buoni che desideri generare.

- **Nome:**

  - **Cosa fa questa impostazione:** Questo è il nome che apparirà nel tuo Back Office di PrestaShop sotto "Catalogo > Sconti > Regole Carrello" per il lotto di buoni generati. È anche il nome base per i singoli codici buono (ad esempio, se imposti "ESTATE2024", i codici potrebbero essere "ESTATE2024-ABCDE", "ESTATE2024-FGHIJ").
  - **Effetto della modifica di questa impostazione:** Un nome chiaro e descrittivo ti aiuta a identificare lo scopo del lotto di buoni in seguito.
  - **Valore consigliato:** Qualcosa di descrittivo come "Saldi Estivi 2024", "Benvenuto Nuovo Cliente" o "Recupero Carrello Abbandonato".
  - **Scenario / esempio per il commerciante:** Stai eseguendo una promozione estiva. Potresti chiamarla "ESTATE2024".
- **Descrizione:**

  - **Cosa fa questa impostazione:** Una nota interna per il tuo riferimento, visibile solo nel Back Office. Ti aiuta a ricordare i dettagli specifici o gli obiettivi di questa campagna di buoni.
  - **Effetto della modifica di questa impostazione:** Fornisce contesto per te e il tuo team.
  - **Valore consigliato:** Una breve spiegazione, ad esempio, "20% di sconto su tutti gli ordini superiori a $50, valido per 1 mese, distribuito tramite newsletter via email."
  - **Scenario / esempio per il commerciante:** Per la campagna "ESTATE2024", potresti aggiungere "20% di sconto su tutti i prodotti, acquisto minimo $50, valido fino al 31 agosto."
- **Evidenzia:**

  - **Cosa fa questa impostazione:** Se abilitato, questo buono verrà visualizzato nel riepilogo del carrello per tutti i clienti, anche se non lo hanno inserito. Questo è tipicamente usato per promozioni generali e pubbliche.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il buono appare automaticamente nel riepilogo del carrello, incoraggiando i clienti a usarlo.
    - *Quando disabilitato:* Il buono viene applicato solo se il cliente inserisce esplicitamente il codice.
  - **Valore consigliato:** "NO" per buoni unici e mirati; "SÌ" per promozioni pubbliche a livello di negozio.
  - **Scenario / esempio per il commerciante:** Se stai dando codici unici a clienti specifici, disabilita questa opzione. Se è una promozione generale "10% di sconto su tutto", abilitala.
- **Uso parziale:**

  - **Cosa fa questa impostazione:** Determina se un buono può essere utilizzato più volte se il suo valore supera il totale dell'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Se un cliente ha un buono da $50 e acquista un articolo da $30, avrà un saldo di $20 rimanente su quello stesso buono per un acquisto futuro.
    - *Quando disabilitato:* Se un cliente ha un buono da $50 e acquista un articolo da $30, l'intero buono da $50 viene consumato e non rimane alcun saldo.
  - **Valore consigliato:** "NO" per la maggior parte delle promozioni per incoraggiare l'uso completo o prevenire un tracciamento complesso. "SÌ" per buoni regalo o credito del negozio.
  - **Scenario / esempio per il commerciante:** Per uno sconto standard, di solito disabiliteresti questa opzione. Per un buono regalo, la abiliteresti.
- **Priorità:**

  - **Cosa fa questa impostazione:** Imposta l'ordine in cui vengono applicate le regole del carrello se più regole sono attive. Un numero inferiore significa priorità più alta (applicato per primo).
  - **Effetto della modifica di questa impostazione:** Influisce su come si accumulano gli sconti. Se si applicano due buoni, quello con priorità più alta viene elaborato per primo.
  - **Valore consigliato:** Lasciare il valore predefinito (1) a meno che tu non abbia regole di accumulo complesse.
  - **Scenario / esempio per il commerciante:** Se hai un buono "Spedizione Gratuita" (priorità 1) e un buono "10% di Sconto" (priorità 2), la spedizione gratuita verrà calcolata prima dello sconto percentuale.
- **Stato:**

  - **Cosa fa questa impostazione:** Attiva o disattiva i buoni generati.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I buoni sono attivi e possono essere utilizzati dai clienti.
    - *Quando disabilitato:* I buoni sono inattivi e non possono essere utilizzati.
  - **Valore consigliato:** "SÌ" se vuoi che i buoni siano immediatamente utilizzabili. Puoi disabilitarli in seguito se necessario.
  - **Scenario / esempio per il commerciante:** Generi buoni per una vendita futura. Potresti abilitarli il giorno in cui inizia la vendita.

#### **2. Condizioni del Buono**

Questa sezione definisce quando e come i buoni generati possono essere utilizzati.

- **Valido da:**

  - **Cosa fa questa impostazione:** Imposta la data di inizio da cui i buoni diventano attivi.
  - **Effetto della modifica di questa impostazione:** I buoni non possono essere utilizzati prima di questa data.
  - **Valore consigliato:** La data odierna se vuoi che siano attivi immediatamente, o una data futura per una promozione pianificata.
  - **Scenario / esempio per il commerciante:** Imposta su "2024-07-01" per una promozione di luglio.
- **Valido a:**

  - **Cosa fa questa impostazione:** Imposta la data di fine dopo la quale i buoni scadono.
  - **Effetto della modifica di questa impostazione:** I buoni non possono essere utilizzati dopo questa data.
  - **Valore consigliato:** Una data di scadenza ragionevole per la tua promozione (ad esempio, 1 settimana, 1 mese, fine stagione).
  - **Scenario / esempio per il commerciante:** Imposta su "2024-07-31" per una promozione di luglio.
- **Importo minimo:**

  - **Cosa fa questa impostazione:** L'importo totale minimo dell'acquisto (prima della spedizione e delle tasse) richiesto affinché il buono sia valido.
  - **Effetto della modifica di questa impostazione:** Se il totale del carrello del cliente è inferiore a questo importo, il buono non può essere applicato.
  - **Valore consigliato:** Imposta un valore che incoraggi valori medi degli ordini più elevati, o 0 se non è richiesto un minimo.
  - **Scenario / esempio per il commerciante:** Imposta su "50.00" per offrire uno sconto solo su ordini superiori a $50.
- **Totale disponibile:**

  - **Cosa fa questa impostazione:** Il numero totale di volte in cui *tutti* i buoni generati in questo lotto possono essere utilizzati da *tutti* i clienti.
  - **Effetto della modifica di questa impostazione:** Una volta raggiunto questo limite, nessun altro buono di questo lotto può essere utilizzato, anche se i singoli codici hanno ancora usi rimanenti.
  - **Valore consigliato:** Un numero elevato (ad esempio, 99999) se vuoi che si applichino i limiti dei singoli codici, o un numero specifico per una campagna a tempo limitato con uso totale.
  - **Scenario / esempio per il commerciante:** Se generi 100 codici unici e imposti "Totale disponibile" a 50, solo i primi 50 utilizzi su tutti i codici saranno validi.
- **Totale disponibile per ogni utente:**

  - **Cosa fa questa impostazione:** Il numero massimo di volte in cui *ogni singolo cliente* può utilizzare *qualsiasi* dei buoni di questo lotto.
  - **Effetto della modifica di questa impostazione:** Impedisce a un singolo cliente di utilizzare ripetutamente codici diversi dallo stesso lotto.
  - **Valore consigliato:** "1" per la maggior parte delle campagne di buoni unici per garantire che ogni cliente ottenga un solo utilizzo. "0" per usi illimitati per cliente (non consigliato per codici unici).
  - **Scenario / esempio per il commerciante:** Imposta su "1" per assicurarti che ogni cliente possa beneficiare di uno solo dei tuoi codici generati.

#### **3. Azioni del Buono**

Questa sezione definisce cosa fa effettivamente il buono quando viene applicato.

- **Spedizione gratuita:**

  - **Cosa fa questa impostazione:** Determina se il buono concede la spedizione gratuita.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I costi di spedizione vengono annullati per gli ordini che utilizzano questo buono.
    - *Quando disabilitato:* Si applicano i costi di spedizione standard.
  - **Valore consigliato:** "NO" a meno che non sia una specifica promozione di spedizione gratuita.
  - **Scenario / esempio per il commerciante:** Per una promozione "Weekend di Spedizione Gratuita", abiliteresti questa opzione.
- **Applica uno sconto:**

  - **Cosa fa questa impostazione:** Qui definisci l'importo o la percentuale di sconto effettivi.
  - **Effetto della modifica di questa impostazione:** Determina il valore monetario dello sconto.
  - **Valore consigliato:** Scegli un tipo di sconto (percentuale, importo o prodotto specifico) e compila i dettagli.
  - **Scenario / esempio per il commerciante:** Vuoi offrire il 15% di sconto.
  - **Percentuale:**

    - **Cosa fa questa impostazione:** Applica uno sconto percentuale al totale dell'ordine.
    - **Effetto della modifica di questa impostazione:** Riduce il totale dell'ordine della percentuale specificata.
    - **Valore consigliato:** Una percentuale comune come 5, 10, 15, 20.
    - **Scenario / esempio per il commerciante:** Inserisci "15" per il 15% di sconto.
  - **Importo:**

    - **Cosa fa questa impostazione:** Applica uno sconto monetario fisso al totale dell'ordine.
    - **Effetto della modifica di questa impostazione:** Riduce il totale dell'ordine dell'importo specificato.
    - **Valore consigliato:** Un importo fisso come 5.00, 10.00, 25.00.
    - **Scenario / esempio per il commerciante:** Inserisci "10.00" per $10 di sconto.
  - **Applica sconto a:**

    - **Cosa fa questa impostazione:** Specifica a quale parte dell'ordine si applica lo sconto.
    - **Effetto della modifica di questa impostazione:**
      - *Ordine (esclusa spedizione):* Lo sconto si applica solo al totale dei prodotti.
      - *Prodotto specifico:* Lo sconto si applica solo a un particolare prodotto o selezione di prodotti.
      - *Prodotto più economico:* Lo sconto si applica all'articolo con il prezzo più basso nel carrello.
      - *Prodotti selezionati:* Lo sconto si applica a un elenco specifico di prodotti che definisci.
    - **Valore consigliato:** "Ordine (esclusa spedizione)" per sconti generali.
    - **Scenario / esempio per il commerciante:** Per un 15% di sconto generale, scegli "Ordine (esclusa spedizione)". Se vuoi il 20% di sconto solo sulle "T-shirt", selezioneresti "Prodotti selezionati" e poi scegliere la categoria/i prodotti T-shirt.
- **Invia un regalo:**

  - **Cosa fa questa impostazione:** Ti permette di aggiungere automaticamente un prodotto specifico come regalo gratuito quando viene utilizzato il buono.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un prodotto scelto viene aggiunto gratuitamente al carrello del cliente.
    - *Quando disabilitato:* Non viene fornito alcun regalo gratuito.
  - **Valore consigliato:** "NO" a meno che non sia una specifica promozione "regalo con acquisto".
  - **Scenario / esempio per il commerciante:** Vuoi regalare un "Portachiavi" gratuito con ogni ordine superiore a $100. Abiliteresti questa opzione e selezioneresti il prodotto Portachiavi.

#### **4. Generazione Buoni**

Questo è il passaggio finale in cui definisci quanti codici generare e poi esegui la generazione.

- **Numero di buoni da generare:**

  - **Cosa fa questa impostazione:** Specifica quanti codici buono unici vuoi che il modulo crei.
  - **Effetto della modifica di questa impostazione:** Determina la quantità di singoli codici sconto che verranno aggiunti alle tue Regole Carrello di PrestaShop.
  - **Valore consigliato:** Il numero esatto di codici unici di cui hai bisogno per la tua campagna (ad esempio, 100 per una lista email, 500 per un giveaway sui social media).
  - **Scenario / esempio per il commerciante:** Hai bisogno di 250 codici unici per una campagna di marketing. Inserisci "250".
- **Pulsante Genera Buoni:**

  - **Cosa fa questa impostazione:** Questo pulsante avvia il processo di creazione di tutti i buoni in base alle impostazioni che hai configurato sopra.
  - **Effetto della modifica di questa impostazione:** Cliccando su questo pulsante verranno create il numero specificato di regole carrello uniche nel tuo negozio PrestaShop. Apparirà un messaggio di conferma e potrai scaricare un file CSV/Excel contenente i codici generati.
  - **Valore consigliato:** Clicca su questo solo dopo essere assolutamente sicuro che tutte le tue impostazioni siano corrette.
  - **Scenario / esempio per il commerciante:** Dopo aver rivisto tutte le impostazioni per la tua campagna "ESTATE2024" e aver impostato il numero di buoni a 250, clicchi su "Genera Buoni".

#### **5. Aggiornamenti e Informazioni MyPresta.eu**

Questa sezione contiene tipicamente informazioni sulla versione del modulo, la disponibilità di aggiornamenti e link a MyPresta.eu.

- **Aggiornamenti MyPresta.eu / Controllo Aggiornamenti:**
  - **Cosa fa questa impostazione:** Permette al modulo di verificare la disponibilità di nuove versioni da MyPresta.eu.
  - **Effetto della modifica di questa impostazione:** Ti aiuta a mantenere il tuo modulo aggiornato con le ultime funzionalità e correzioni di bug.
  - **Valore consigliato:** Mantieni questa opzione abilitata per ricevere notifiche sugli aggiornamenti.
  - **Scenario / esempio per il commerciante:** Vedi una notifica che una nuova versione è disponibile, assicurandoti di avere la versione più stabile e ricca di funzionalità.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Nome | Testo descrittivo | Nome interno per il lotto di buoni. |
| Configurazione Modulo | Descrizione | Testo opzionale | Note interne per i dettagli della campagna. |
| Configurazione Modulo | Evidenzia | NO | Visualizza il buono nel riepilogo del carrello (SÌ per pubblico, NO per privato). |
| Configurazione Modulo | Uso parziale | NO | Consenti l'uso multiplo del buono se il valore > ordine. |
| Configurazione Modulo | Priorità | 1 | Ordine di applicazione per più regole carrello (inferiore = priorità più alta). |
| Configurazione Modulo | Stato | SÌ | Attiva/disattiva i buoni generati. |
| Configurazione Modulo | Valido da | Data corrente | Data di inizio validità del buono. |
| Configurazione Modulo | Valido a | Data futura | Data di fine validità del buono. |
| Configurazione Modulo | Importo minimo | 0.00 | Acquisto minimo richiesto per l'uso del buono. |
| Configurazione Modulo | Totale disponibile | Numero elevato (es. 99999) | Usi totali per TUTTI i buoni in questo lotto. |
| Configurazione Modulo | Totale disponibile per ogni utente | 1 | Usi massimi per cliente per qualsiasi buono in questo lotto. |
| Configurazione Modulo | Spedizione gratuita | NO | Concede la spedizione gratuita con il buono. |
| Configurazione Modulo | Applica uno sconto | SÌ | Abilita l'applicazione dello sconto. |
| Configurazione Modulo | Percentuale | (es. 10) | Sconto percentuale. |
| Configurazione Modulo | Importo | (es. 10.00) | Sconto monetario fisso. |
| Configurazione Modulo | Applica sconto a | Ordine (esclusa spedizione) | Ambito dello sconto (ordine, prodotto specifico, ecc.). |
| Configurazione Modulo | Invia un regalo | NO | Aggiungi un prodotto gratuito come regalo. |
| Configurazione Modulo | Numero di buoni da generare | (es. 100) | Quantità di codici unici da creare. |
| Configurazione Modulo | Pulsante Genera Buoni | Clicca quando pronto | Avvia la creazione dei buoni e l'esportazione CSV. |
| Configurazione Modulo | Aggiornamenti MyPresta.eu | SÌ | Controlla gli aggiornamenti del modulo. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Ho generato dei buoni, ma non sembrano funzionare nel front office.**
R1:

- **Controlla Stato e Date:** Vai su "Catalogo > Sconti > Regole Carrello" nel tuo Back Office di PrestaShop. Trova i buoni che hai generato. Assicurati che il loro "Stato" sia impostato su "Sì" e che le date "Valido da" e "Valido a" siano attuali.
- **Importo Minimo:** Verifica se il carrello del cliente soddisfa il requisito di "Importo minimo" impostato per il buono.
- **Condizioni:** Ricontrolla eventuali altre condizioni che hai impostato (es. prodotti specifici, gruppi di clienti).
- **Cache:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota Cache).

**D2: Posso modificare i buoni generati dopo che sono stati creati?**
R2: Sì, una volta generato, ogni buono diventa una "Regola Carrello" standard in PrestaShop. Puoi andare su "Catalogo > Sconti > Regole Carrello" nel tuo Back Office, trovare i singoli buoni (di solito condivideranno lo stesso nome base che hai fornito) e modificarne le proprietà (es. data di scadenza, importo dello sconto, condizioni) individualmente. Tuttavia, è generalmente meglio impostare correttamente tutte le impostazioni prima della generazione.

**D3: Come ottengo l'elenco dei codici buono generati?**
R3: Immediatamente dopo aver cliccato sul pulsante "Genera Buoni", il modulo ti chiederà di scaricare un file CSV/Excel contenente tutti i codici unici. Se hai perso questa opportunità, non puoi scaricare nuovamente l'elenco direttamente dal modulo. Dovresti esportare manualmente le "Regole Carrello" da "Catalogo > Sconti > Regole Carrello" in PrestaShop, o accedere direttamente al database (attività per sviluppatori). È fondamentale salvare il file CSV immediatamente dopo la generazione.

**D4: Il modulo dice "Aggiornamenti MyPresta.eu" ma non mostra una nuova versione.**
R4: Questo significa che il tuo modulo è attualmente aggiornato con l'ultima versione ufficiale disponibile da MyPresta.eu. Non è richiesta alcuna azione.

**D5: Il mio tema personalizzato non visualizza correttamente il campo di input del buono.**
R5: Il modulo Generatore di Buoni non aggiunge elementi al front-office. Il campo di input del buono è una funzionalità standard di PrestaShop. Se non viene visualizzato correttamente, è probabile che sia un problema con lo stile del tuo tema personalizzato o con le sovrascritture dei template per le pagine del carrello/checkout. Dovresti consultare lo sviluppatore del tuo tema o un webmaster per regolare i file CSS o TPL relativi agli hook `displayCart` o `displayPaymentTop` dove tipicamente appare il campo del buono.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo Generatore di Buoni (`vouchers`) è un modulo PrestaShop standard che opera principalmente all'interno del Back Office. Sfrutta la funzionalità `CartRule` di PrestaShop per creare più codici sconto in modo efficiente. La logica principale del modulo risiede nel suo file `vouchers.php`, che gestisce la configurazione e il processo di generazione. Non introduce complessi modelli MVC o tabelle di database personalizzate, ma interagisce direttamente con il modello di oggetti `CartRule` esistente di PrestaShop.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Il modulo non aggiunge alcun controller front-office personalizzato. Tutte le interazioni front-office relative ai buoni sono gestite dai controller nativi di PrestaShop `CartController` o `OrderController`.
- **Controller Admin Back-Office**: Nessuno. La logica di configurazione e generazione del modulo è interamente contenuta nel metodo `getContent()` della classe principale del modulo, che viene renderizzato dal `AdminModulesController` standard.

### 4.3 Classi e Modelli Core (`classes/`)

- Nessuno. Il modulo non definisce classi personalizzate né estende `ObjectModel`. Utilizza direttamente la classe nativa `CartRule` di PrestaShop per creare e gestire i buoni.

### 4.4 Risorse JavaScript (`views/js/`)

- `vouchers/lib/voucherengine/script.js`
  - **Ambito:** Back-office.
  - **Scopo:** Questo script contiene probabilmente la logica lato client per la pagina di configurazione del modulo. Questo potrebbe includere:
    - Validazione del modulo prima della generazione dei buoni.
    - Chiamate AJAX al metodo `getContent()` del modulo per aggiornamenti o elaborazioni dinamiche.
    - Miglioramenti dell'interfaccia utente o interazioni specifiche per il modulo di generazione dei buoni.
    - Potenziale gestione del download del file CSV generato.
  - **Listener di Eventi:** Probabilmente si lega agli eventi di invio del modulo, agli eventi di modifica dell'input e ai clic sui pulsanti nella pagina di configurazione del modulo.
  - **Manipolazione del DOM:** Può mostrare/nascondere elementi in base alle selezioni dell'utente (ad esempio, mostrando campi di selezione di prodotti specifici se viene scelto "Applica sconto a: Prodotto specifico").

### 4.5 Fogli di Stile CSS (`views/css/`)

- `vouchers/lib/voucherengine/ps16.css`
  - **Ambito:** Stile del modulo admin del Back-office.
  - **Scopo:** Fornisce uno stile specifico per l'interfaccia di configurazione del modulo, potenzialmente per garantire un aspetto coerente tra le diverse versioni di PrestaShop (ad esempio, adattandosi alla struttura specifica del tema admin di PrestaShop 1.6).
  - **Componenti principali dell'interfaccia utente:** Stili i campi del modulo, i pulsanti e gli elementi di layout all'interno dell'output di `getContent()` del modulo.
  - **Selettori di classe CSS chiave:** Gli sviluppatori possono ispezionare la pagina di configurazione del modulo nel browser per identificare classi specifiche (ad esempio, `.vouchers-generator-form`, `.mypresta-update-block`) che possono essere sovrascritte in un tema admin personalizzato se necessario.

### 4.6 Struttura del Template Smarty (`views/templates/`)

- `vouchers/views/pdf.tpl`
  - **Ambito:** Back-office / Utilità.
  - **Scopo:** Questo template è probabilmente utilizzato per generare un documento PDF stampabile o scaricabile contenente l'elenco dei buoni generati. Sebbene la descrizione del modulo menzioni l'esportazione CSV/Excel, un template PDF suggerisce un formato di output alternativo o aggiuntivo per l'elenco dei buoni, possibilmente per la stampa di buoni fisici.
  - **Utilizzo:** Verrà renderizzato quando il modulo deve presentare i codici buono generati in un formato strutturato e stampabile. Riceverà un array di dati del buono (codice, valore, scadenza, ecc.) dalla logica PHP.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**:

  - Il modulo non crea tabelle di database personalizzate.
  - Interagisce con le tabelle native di PrestaShop `ps_cart_rule` e `ps_cart_rule_lang` per memorizzare i buoni generati.
  - Le impostazioni di configurazione (come `vg_counter`, `mypresta_updates`) sono memorizzate nella tabella `ps_configuration`.
- **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin viene inizializzato e i suoi media (JS/CSS) vengono impostati. | Utilizzato dal modulo per includere i suoi file JavaScript (`script.js`) e CSS (`ps16.css`) del Back Office specificamente sulla sua pagina di configurazione, assicurando che vengano caricati solo quando necessario. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Generatore di Buoni, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e compatibilità del modulo.
