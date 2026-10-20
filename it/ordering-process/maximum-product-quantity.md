---
title: "Quantità massima di prodotto - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Quantità massima di prodotto di MyPresta.eu."
sidebar:
  label: "Quantità massima di prodotto"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Maximum product quantity su MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-product-quantity.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/maximum-product-quantity/)
>
> ---


# Quantità massima di prodotto

## 1. Requisiti e Compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono richieste configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Quantità massima di prodotto)

La pagina di configurazione principale del modulo è dove definisci le impostazioni globali e gestisci i limiti di quantità specifici per prodotto.

#### **Impostazioni Generali**

-   **Cosa fa questa impostazione:** Queste sono le impostazioni principali che abilitano o disabilitano la funzionalità del modulo e definiscono come si comporta a livello globale.
-   **Effetto della modifica di questa impostazione:**
    -   *Abilita/Disabilita Modulo:* Attiva o disattiva l'intero sistema di limitazione della quantità.
    -   *Quantità Massima Globale:* Imposta una quantità massima predefinita per tutti i prodotti se non è definito un limite specifico.
-   **Valore consigliato:** Inizia abilitando il modulo e impostando un ragionevole massimo globale se desideri applicare una regola generale.
-   **Scenario/esempio per il commerciante:** Se vuoi assicurarti che nessun cliente possa mai acquistare più di 100 unità di *qualsiasi* prodotto, imposta il massimo globale a 100.

#### **Limiti di Quantità Specifici per Prodotto**

Questa sezione è solitamente una tabella o un elenco dove puoi cercare prodotti e definire limiti specifici per essi.

-   **Cosa fa questa impostazione:** Ti permette di sovrascrivere le impostazioni globali per i singoli prodotti. Puoi specificare:
    -   **Quantità massima per ordine:** Il numero più alto di unità di questo prodotto che un cliente può aggiungere a un singolo carrello.
    -   **Quantità massima per cliente (totale):** Il numero più alto di unità di questo prodotto che un cliente specifico può acquistare *attraverso tutti i suoi ordini*.
    -   **Limiti specifici per gruppo di clienti:** Applica limiti diversi in base al gruppo di clienti (es. "Ospiti", "Clienti", "Grossisti").
-   **Effetto della modifica di questa impostazione:**
    -   *Quando i limiti sono impostati:* Il modulo applicherà questi limiti specifici per il prodotto scelto, sovrascrivendo qualsiasi impostazione globale.
    -   *Quando i limiti vengono rimossi:* Il prodotto tornerà a utilizzare le impostazioni di quantità massima globale.
-   **Valore consigliato:** Imposta limiti specifici per prodotti molto richiesti, con scorte limitate o strategicamente importanti.
-   **Scenario/esempio per il commerciante:**
    -   Hai un prodotto in edizione limitata. Imposti "Quantità massima per ordine" a 1 e "Quantità massima per cliente (totale)" a 1 per garantire una unità per cliente.
    -   Per un articolo all'ingrosso, potresti impostare "Quantità massima per ordine" a 50 per i "Clienti" ma a 500 per i "Grossisti".

#### **Impostazioni di Tracciamento della Cronologia Ordini**

-   **Cosa fa questa impostazione:** Controlla se il modulo esamina gli ordini passati di un cliente per applicare i limiti di "quantità massima per cliente (totale)". Spesso puoi specificare quali stati dell'ordine contano ai fini del limite (ad esempio, solo ordini "Consegnati" o "Pagamento accettato").
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo interrogherà la cronologia degli ordini del cliente per calcolare i suoi acquisti totali di un prodotto.
    -   *Quando disabilitato:* Verrà controllata solo la quantità attuale del carrello rispetto al limite di "quantità massima per ordine". I limiti di "quantità massima per cliente (totale)" saranno effettivamente ignorati.
-   **Valore consigliato:** Abilita questa opzione se desideri applicare veri limiti per cliente nel tempo. Seleziona gli stati dell'ordine pertinenti (ad esempio, "Pagamento accettato", "Consegnato") per tracciare accuratamente gli acquisti.
-   **Scenario/esempio per il commerciante:** Stai eseguendo una promozione in cui ogni cliente può acquistare un massimo di 3 unità di un prodotto specifico *in assoluto*. Abiliti il tracciamento della cronologia degli ordini e selezioni gli stati "Pagamento accettato" e "Consegnato". Se un cliente ha già acquistato 2 unità, può aggiungerne solo 1 al carrello.

#### **Personalizzazione del Messaggio di Errore**

-   **Cosa fa questa impostazione:** Ti permette di personalizzare il messaggio visualizzato ai clienti quando superano un limite di quantità.
-   **Effetto della modifica di questa impostazione:** Il messaggio di errore predefinito e generico verrà sostituito con il tuo testo personalizzato, che può essere più informativo o brandizzato.
-   **Valore consigliato:** Fornisci un messaggio chiaro, cortese e utile. Puoi usare segnaposto (se supportati dal modulo) come `{max_quantity}` per mostrare il limite effettivo.
-   **Scenario/esempio per il commerciante:** Invece di "La quantità supera il massimo", potresti impostare: "Siamo spiacenti, puoi acquistare un massimo di {max_quantity} unità di questo articolo. Questo ci aiuta a garantire un accesso equo a tutti i nostri clienti!"

#### **Esportazione e Importazione CSV / JSON (se disponibile)**

-   **Cosa fa questa impostazione:** Fornisce strumenti per esportare i tuoi limiti di quantità attuali in un file CSV o JSON e importare nuovi limiti da tali file. Questo è utile per la modifica in blocco o la migrazione delle impostazioni.
-   **Effetto della modifica di questa impostazione:**
    -   *Esporta:* Crea un file con tutti i limiti di quantità di prodotto definiti.
    -   *Importa:* Sovrascrive o aggiunge nuovi limiti di quantità in base ai dati nel file caricato.
-   **Valore consigliato:** Utilizza questa funzione per aggiornamenti su larga scala o per la configurazione iniziale se hai molti prodotti con limiti specifici. Esegui sempre un backup delle tue impostazioni attuali prima di importare.
-   **Scenario/esempio per il commerciante:** Stai lanciando un nuovo catalogo con 500 prodotti, ognuno dei quali necessita di una quantità massima unica. Invece di inserirli manualmente, prepari un file CSV e lo importi.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Configurazione Modulo | Abilita/Disabilita Modulo | Abilitato | Attiva/disattiva tutte le funzionalità di limitazione della quantità. |
| Configurazione Modulo | Quantità Max Globale per Ordine | Varia / 100 | Imposta una quantità massima predefinita per i prodotti senza limiti specifici. |
| Configurazione Modulo | Quantità Max Specifica per Prodotto per Ordine | Varia / Personalizzato | Sovrascrive il limite globale per i singoli prodotti in un singolo carrello. |
| Configurazione Modulo | Quantità Max Specifica per Prodotto per Cliente (Totale) | Varia / Personalizzato | Limita gli acquisti totali di un prodotto da parte di un cliente su tutti gli ordini. |
| Configurazione Modulo | Limiti Specifici per Gruppo di Clienti | Varia / Personalizzato | Applica limiti diversi in base ai gruppi di clienti (es. Grossisti). |
| Configurazione Modulo | Traccia Cronologia Ordini | Abilitato | Controlla gli ordini passati per applicare la "Quantità Max per Cliente (Totale)". |
| Configurazione Modulo | Stati Ordine per Tracciamento | Pagamento accettato, Consegnato | Definisce quali stati dell'ordine contano per gli acquisti totali del cliente. |
| Configurazione Modulo | Messaggio di Errore Personalizzato | "La quantità supera il limite" | Personalizza il messaggio mostrato ai clienti quando viene raggiunto un limite. |
| Configurazione Modulo | Esporta/Importa CSV/JSON | N/A | Consente la gestione in blocco dei limiti di quantità tramite caricamento/download di file. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato dei limiti, ma i clienti possono ancora aggiungere più del consentito. Cosa c'è che non va?**
R1:
*   **Modulo Abilitato?** Per prima cosa, ricontrolla che il modulo sia abilitato nella configurazione principale.
*   **Prodotto Specifico vs. Globale:** Assicurati di aver impostato correttamente i limiti per il *prodotto specifico* in questione, o che i limiti globali siano attivi se non esistono limiti specifici per prodotto.
*   **Gruppo Clienti:** Verifica che il gruppo di clienti a cui appartiene il cliente abbia i limiti corretti applicati.
*   **Cache:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota cache). A volte, vengono ancora servite vecchie impostazioni.
*   **Conflitti del Tema:** Raramente, un tema altamente personalizzato potrebbe interferire con il modo in cui vengono gestiti gli input di quantità. Testa con il tema predefinito di PrestaShop per escludere questa possibilità.

**D2: La "quantità massima per cliente (totale)" non funziona, anche con il tracciamento della cronologia degli ordini abilitato.**
R2:
*   **Stati dell'ordine:** Vai alla configurazione del modulo e controlla quali "Stati dell'ordine per il tracciamento" sono selezionati. Se gli ordini precedenti di un cliente si trovano in uno stato non selezionato (ad esempio, "In sospeso" invece di "Consegnato"), non verranno conteggiati ai fini del limite. Assicurati che gli stati pertinenti siano selezionati.
*   **Accesso del cliente:** Assicurati che il cliente sia loggato. Il modulo può tracciare gli acquisti precedenti solo per i clienti identificati, non per gli ospiti.

**D3: Come posso tradurre i messaggi di errore in altre lingue?**
R3:
*   Naviga su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
*   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona la tua lingua.
*   Trova il modulo "Quantità massima di prodotto" nell'elenco. Dovresti essere in grado di modificare i messaggi di errore personalizzati che hai impostato per ogni lingua.

**D4: Il modulo sembra rallentare le mie pagine prodotto o il carrello.**
R4:
*   Sebbene il modulo sia ottimizzato, se hai un numero estremamente elevato di prodotti con limiti complessi e specifici per gruppo e un ampio tracciamento della cronologia degli ordini, potrebbe aggiungere un leggero sovraccarico.
*   **Prestazioni > CCC:** Assicurati che le impostazioni CCC (Combina, Comprimi, Cache) per CSS e JavaScript siano abilitate in **Parametri Avanzati > Prestazioni**.
*   **Risorse del server:** Controlla il limite di memoria PHP e il tempo di esecuzione del tuo server. Se sono troppo bassi, possono influire sulle prestazioni.
*   **Ottimizzazione del database:** Assicurati che il tuo database PrestaShop sia regolarmente ottimizzato.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Quantità massima di prodotto".

### 4.1 Panoramica dell'Architettura
Il modulo `Quantità massima di prodotto` (nome interno `mqc`) è un modulo PrestaShop standard progettato per estendere il processo di ordinazione principale. Opera principalmente agganciandosi a vari punti del front-office (pagina prodotto, carrello, checkout) per convalidare le quantità di prodotto rispetto ai limiti configurati. La configurazione è gestita tramite un singolo metodo `getContent()` nel file principale del modulo, sfruttando la classe `Configuration` di PrestaShop per memorizzare le impostazioni. Utilizza JavaScript per la validazione front-end e il feedback utente, e i template Smarty per visualizzare messaggi e moduli di configurazione.

### 4.2 Controller (`controllers/`)
Questo modulo non contiene controller dedicati per il front-office o il back-office. Tutta la logica del front-office è gestita tramite hook e JavaScript, mentre la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` del file `index.php` del modulo.

### 4.3 Classi e Modelli Core (`classes/`)
Il modulo non definisce classi `ObjectModel` personalizzate. Tutti i dati sono memorizzati direttamente nella tabella `ps_configuration` utilizzando chiavi di configurazione standard di PrestaShop. La logica principale risiede nel file `mqc/index.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`mqc/views/js/mqc-17500.js`**:
    *   **Ambito:** Front-office (specifico per PrestaShop 1.7.5.0+).
    *   **Responsabilità:** Contiene la logica JavaScript adattata per le versioni più recenti di PrestaShop 1.7.x e 8.x. Probabilmente si aggancia a `prestashop.on('updateProduct', ...)` o eventi simili per riconvalidare le quantità quando gli attributi del prodotto cambiano o quando l'input della quantità viene modificato nella pagina del prodotto. Potrebbe anche gestire chiamate AJAX al `index.php` del modulo per ottenere la validazione della quantità in tempo reale.
    *   **Interazione:** Si lega ai campi di input della quantità, ai pulsanti "aggiungi al carrello" e potenzialmente ai selettori di attributi del prodotto per fornire un feedback immediato all'utente se un limite di quantità viene superato.

-   **`mqc/views/js/mqc-front.js`**:
    *   **Ambito:** Front-office (generale, potenzialmente per versioni precedenti di PrestaShop o logica comune).
    *   **Responsabilità:** Contiene la logica JavaScript generale del front-office per la validazione della quantità. Questo potrebbe includere:
        *   Listener di eventi per le modifiche dell'input della quantità nella pagina del prodotto o nel carrello.
        *   Chiamate AJAX al server per controllare i limiti di quantità.
        *   Visualizzazione di messaggi di errore all'utente.
        *   Potenziale disabilitazione o limitazione dei campi di input della quantità.
    *   **Interazione:** Simile a `mqc-17500.js` ma potrebbe utilizzare un binding di eventi basato su jQuery più vecchio o eventi PrestaShop meno specifici.

-   **`mqc/views/js/mqc.js`**:
    *   **Ambito:** Back-office.
    *   **Responsabilità:** Gestisce il JavaScript per la pagina di configurazione del modulo nel Back Office di PrestaShop. Questo potrebbe includere:
        *   Elementi di modulo dinamici (ad esempio, aggiunta/rimozione di righe di limite specifiche per prodotto).
        *   Ricerca AJAX per i prodotti durante l'impostazione di limiti individuali.
        *   Validazione dei campi di input nel modulo di configurazione.
        *   Logica per le funzionalità di importazione/esportazione CSV/JSON.
    *   **Interazione:** Si lega agli elementi del modulo nella pagina di configurazione del modulo, potenzialmente effettuando richieste AJAX al metodo `getContent()` del modulo per il recupero o l'invio dei dati.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`mqc/views/css/mqc.css`**:
    *   **Ambito:** Sia Front-office (per i messaggi di errore) che Back-office (per lo stile della pagina di configurazione).
    *   **Componenti e contenitori UI principali che stilizza:**
        *   Contenitori di messaggi di errore (ad esempio, `div.alert.alert-danger` o classi personalizzate per messaggi specifici del modulo).
        *   Campi di input ed etichette nella pagina di configurazione del back-office.
        *   Potenziale stile per elementi dinamici aggiunti da `mqc.js` (ad esempio, risultati di ricerca prodotti, righe di tabella per i limiti).
    *   **Selettori di classi CSS chiave che gli sviluppatori possono sovrascrivere:** Cerca classi come `.mqc-error-message`, `.mqc-limit-table`, `.mqc-product-search-results` all'interno dei template del modulo e dell'HTML generato. Gli sviluppatori possono sovrascriverle nel `custom.css` del loro tema o creando un tema figlio.

### 4.6 Struttura del Template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty sia per la visualizzazione nel front-office che per la configurazione nel back-office.

-   **Template degli hook (`views/templates/hook/`)**:
    *   **`product-details.tpl`**:
        *   **Hook:** Probabilmente `displayProductExtraContent` o `displayProductButtons` (a seconda della versione di PrestaShop e dell'implementazione specifica).
        *   **Output:** Potrebbe visualizzare un piccolo messaggio informativo sui limiti di quantità nella pagina del prodotto, o renderizzare un campo di input quantità personalizzato se il modulo sostituisce quello predefinito.
    *   **`productActions.tpl`**:
        *   **Hook:** `displayProductActions` (nella pagina del prodotto).
        *   **Output:** Potenzialmente utilizzato per iniettare variabili JavaScript o input nascosti relativi ai limiti di quantità vicino al pulsante "aggiungi al carrello", o per visualizzare un messaggio di errore se un limite di quantità viene superato prima di aggiungere al carrello.
    *   **`shoppingCart.tpl`**:
        *   **Hook:** `displayShoppingCartFooter` o `displayShoppingCart` (nella pagina del carrello).
        *   **Output:** Utilizzato per visualizzare messaggi di errore direttamente all'interno del carrello se le quantità superano i limiti, impedendo il checkout.

-   **Template di amministrazione (`views/templates/admin/`)**: Questi template vengono renderizzati all'interno del metodo `getContent()` di `mqc/index.php` per costruire l'interfaccia di configurazione del modulo.
    *   **`admintab.tpl`**: Probabilmente un wrapper o un'intestazione/piè di pagina comune per la pagina di configurazione dell'amministrazione.
    *   **`button-subcategories-purchases.tpl`**: Potrebbe essere un pulsante o una sezione relativa alla gestione degli acquisti per sottocategorie, possibilmente per report avanzati o impostazione di limiti.
    *   **`button-subcategories.tpl`**: Simile al precedente, ma per le sottocategorie in generale.
    *   **`csv.tpl`**: Template per la funzionalità di esportazione CSV, potenzialmente contenente elementi di modulo per la selezione delle opzioni di esportazione.
    *   **`csv_file.tpl`**: Template per la funzionalità di importazione CSV, solitamente un modulo di caricamento.
    *   **`json.tpl`**: Template per l'esportazione/importazione JSON, simile a `csv.tpl` e `csv_file.tpl`.
    *   **`main.tpl`**: Il template principale per la pagina di configurazione del modulo, contenente la struttura principale del modulo, le impostazioni generali e potenzialmente una tabella per i limiti specifici del prodotto.
    *   **`message.tpl`, `message2.tpl`, `message3.tpl`, `message4.tpl`, `message5.tpl`**: Template di messaggi generici utilizzati per visualizzare messaggi di successo, errore o informativi all'interno della configurazione del back-office.
    *   **`orderstates.tpl`**: Template per la selezione degli stati dell'ordine che contano per il limite di "quantità massima per cliente (totale)".

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:
    *   Il modulo non crea tabelle SQL personalizzate.
    *   Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`. Le chiavi di configurazione seguiranno tipicamente un modello come `MQC_GLOBAL_MAX_QTY`, `MQC_PRODUCT_LIMITS_[id_product]`, `MQC_TRACK_HISTORY_STATUSES`, ecc. I limiti specifici del prodotto potrebbero essere memorizzati come array serializzati o stringhe JSON in una singola chiave di configurazione, o chiavi individuali per prodotto/gruppo.
    *   Il tracciamento della cronologia degli ordini si basa sull'interrogazione delle tabelle PrestaShop esistenti: `ps_orders`, `ps_order_detail` e `ps_order_state`.

-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Registra risorse CSS e JavaScript (`mqc.css`, `mqc-front.js`, `mqc-17500.js`) per la funzionalità front-office. |
| `displayProductButtons` | Vicino al pulsante "Aggiungi al carrello" nella pagina del prodotto. | Inietta la logica di validazione della quantità o visualizza messaggi relativi ai limiti specifici del prodotto. |
| `displayProductExtraContent` | Sotto la descrizione del prodotto, sopra i prodotti correlati. | Può essere utilizzato per visualizzare messaggi informativi sui limiti di quantità. |
| `displayShoppingCart` | All'interno del riepilogo del carrello. | Convalida le quantità nel carrello e visualizza messaggi di errore se i limiti vengono superati. |
| `displayShoppingCartFooter` | In fondo alla pagina del carrello. | Simile a `displayShoppingCart`, per la validazione finale prima del checkout. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato e salvato. | Potenzialmente utilizzato per l'elaborazione o la registrazione post-ordine, sebbene la validazione primaria sia pre-checkout. |
| `actionCartSave` | Dopo che un carrello viene salvato o aggiornato (ad esempio, modifica della quantità). | Cruciale per la validazione della quantità in tempo reale quando un cliente modifica le quantità nel carrello o aggiunge nuovi prodotti. |
| `actionFrontControllerSetMedia` | Prima che un controller front-end renda il suo output. | Registra le risorse del front-office, simile a `displayHeader` ma più specifico per il contesto del controller. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renda il suo output. | Registra le risorse del back-office (`mqc.js`, `mqc.css`) per la pagina di configurazione del modulo. |

## 5. Supporto Ufficiale e Aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Quantità massima di prodotto", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
