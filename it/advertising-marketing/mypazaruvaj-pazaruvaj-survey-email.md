---
title: "MyPazaruvaj - Email di sondaggio Pazaruvaj - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop MyPazaruvaj - Email di sondaggio Pazaruvaj di MyPresta.eu."
sidebar:
  label: "MyPazaruvaj - Email di sondaggio Pazaruvaj - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo MyPazaruvaj - Pazaruvaj survey email su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/mypazaruvaj-pazaruvaj-survey-email.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/mypazaruvaj-pazaruvaj-survey-email/)
>
> ---


# MyPazaruvaj - Email di sondaggio Pazaruvaj

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5 (Il modulo è progettato per essere ampiamente compatibile con varie versioni PHP, fino all'ultima versione stabile supportata da PrestaShop 8 e 9.)
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo. Non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > MyPazaruvaj)

Questa è la schermata di configurazione principale e unica per il modulo MyPazaruvaj. Qui imposterai tutti i parametri necessari per connettere il tuo negozio con Pazaruvaj.com.

#### **ID Negozio Pazaruvaj.com**

-   **Cosa fa questa impostazione:** Questo è il tuo identificatore univoco fornito da Pazaruvaj.com per il tuo negozio online. Indica a Pazaruvaj a quale negozio appartengono i dati dell'ordine.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato correttamente:* Il modulo invierà correttamente i dati dell'ordine al tuo profilo negozio Pazaruvaj.com.
    -   *Se errato o vuoto:* Pazaruvaj.com non sarà in grado di identificare il tuo negozio e nessuna email di sondaggio verrà inviata ai tuoi clienti.
-   **Valore consigliato:** Inserisci l'ID Negozio esatto fornito da Pazaruvaj.com. Questo è un campo obbligatorio.
-   **Scenario / esempio del commerciante:** Hai registrato il tuo negozio su Pazaruvaj.com e ti hanno dato un ID Negozio come `12345`. Devi inserire `12345` qui affinché l'integrazione funzioni.

#### **Campo ID Prodotto Pazaruvaj.com**

-   **Cosa fa questa impostazione:** Questa opzione determina quale identificatore di prodotto dal tuo negozio PrestaShop deve essere inviato a Pazaruvaj.com. Pazaruvaj.com utilizza questo ID per abbinare il prodotto acquistato con la sua inserzione sulla loro piattaforma.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "ID Prodotto":* Verrà inviato l'ID prodotto interno di PrestaShop (es. `id_product`). Questa è di solito l'opzione più sicura se il tuo feed Pazaruvaj.com utilizza questi ID.
    -   *Se impostato su "Riferimento Prodotto":* Verrà inviato il codice di riferimento del prodotto (es. `reference`). Scegli questa opzione se il tuo feed Pazaruvaj.com abbina i prodotti in base al loro riferimento.
    -   *Se impostato su "EAN13 Prodotto":* Verrà inviato il codice a barre EAN13 del prodotto. Utile se il tuo feed Pazaruvaj.com si basa sugli EAN.
    -   *Se impostato su "UPC Prodotto":* Verrà inviato il codice UPC del prodotto.
-   **Valore consigliato:** "ID Prodotto" è spesso il valore predefinito più affidabile. Tuttavia, **devi** verificare quale identificatore il tuo feed di prodotti su Pazaruvaj.com utilizza per abbinare i prodotti. Se il tuo feed utilizza i riferimenti dei prodotti, seleziona "Riferimento Prodotto".
-   **Scenario / esempio del commerciante:** Se il tuo feed di prodotti su Pazaruvaj.com utilizza l'ID interno univoco che PrestaShop assegna a ogni prodotto, dovresti selezionare "ID Prodotto". Se hai caricato un feed in cui ogni prodotto è identificato da un SKU o un numero di riferimento specifico (es. `REF-001`), allora seleziona "Riferimento Prodotto".

#### **Abilita consenso all'invio dei dati a Pazaruvaj.com**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se i clienti devono accettare esplicitamente che i dati del loro ordine vengano inviati a Pazaruvaj.com per il sondaggio. Quando abilitato, una casella di controllo appare durante il checkout.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato (SÌ):* Apparirà una casella di controllo nella pagina di checkout. Solo i clienti che spuntano questa casella avranno i dati del loro ordine inviati a Pazaruvaj.com. Questo aiuta con il GDPR e altre normative sulla privacy dei dati.
    -   *Se disabilitato (NO):* I dati dell'ordine verranno inviati a Pazaruvaj.com per *tutti* gli ordini completati senza richiedere il consenso esplicito del cliente. Questo è più semplice per i clienti ma potrebbe non essere conforme a tutte le leggi sulla privacy nella tua regione.
-   **Valore consigliato:** "SÌ" è generalmente raccomandato per la conformità alle normative sulla protezione dei dati (come il GDPR).
-   **Scenario / esempio del commerciante:** Per garantire che il tuo negozio sia pienamente conforme alle leggi sulla privacy, abiliti questa impostazione. Durante il checkout, i tuoi clienti vedranno una casella di controllo etichettata qualcosa come "Accetto di condividere i dettagli del mio ordine con Pazaruvaj.com per un sondaggio di recensione". Solo se la spuntano, i dati verranno inviati.

#### **Mostra consenso su**

-   **Cosa fa questa impostazione:** Se "Abilita consenso" è impostato su SÌ, questa opzione determina dove verrà visualizzata la casella di controllo del consenso nel front-office del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Intestazione, Colonne, Prodotto, Piè di pagina:* La casella di controllo del consenso verrà visualizzata nell'area hook selezionata. La posizione visiva esatta dipende dal layout del tuo tema per quell'hook.
-   **Valore consigliato:** Scegli una posizione prominente ma non intrusiva. Il "Piè di pagina" o una "Colonna" specifica (se il tuo tema ne ha una adatta) sono spesso buone scelte per le notifiche relative alla privacy. Potrebbe essere necessario testare diverse opzioni per vedere cosa si adatta meglio al tuo tema.
-   **Scenario / esempio del commerciante:** Hai abilitato il consenso. Decidi di mostrare la casella di controllo del consenso nel "Piè di pagina" in modo che sia visibile ma non ingombri il flusso principale del checkout.

#### **Abilita registro errori**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se il modulo registra eventuali errori riscontrati durante il processo di trasferimento dei dati a Pazaruvaj.com.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato (SÌ):* Il modulo salverà i dettagli di eventuali invii di dati falliti in un file di log. Questo è prezioso per la risoluzione dei problemi se i sondaggi non vengono inviati.
    -   *Se disabilitato (NO):* Nessuna informazione di errore verrà registrata, rendendo più difficile diagnosticare i problemi.
-   **Valore consigliato:** "SÌ" è altamente raccomandato, specialmente durante la configurazione iniziale e per il monitoraggio continuo.
-   **Scenario / esempio del commerciante:** Non sei sicuro che l'integrazione funzioni perfettamente. Abiliti il registro errori. Se Pazaruvaj.com non riceve dati, puoi controllare il log per vedere se ci sono messaggi di errore specifici, come un ID Negozio non valido o problemi di connessione.

#### **Cancella registro errori**

-   **Cosa fa questa impostazione:** Questo pulsante ti consente di eliminare tutte le voci dal registro errori del modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando cliccato:* Tutti gli errori precedentemente registrati vengono rimossi permanentemente dal file di log.
-   **Valore consigliato:** Usalo dopo aver esaminato e risolto eventuali problemi, o se il file di log diventa troppo grande.
-   **Scenario / esempio del commerciante:** Hai risolto un problema con il tuo ID Negozio Pazaruvaj.com. Clicchi su "Cancella registro errori" per ricominciare da capo e assicurarti che vengano registrati solo nuovi errori pertinenti.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | ID Negozio Pazaruvaj.com | Il tuo ID Pazaruvaj (Obbligatorio) | Identificatore univoco per il tuo negozio su Pazaruvaj.com. Essenziale per il trasferimento dei dati. |
| Configurazione Modulo | Campo ID Prodotto Pazaruvaj.com | ID Prodotto (Verifica con feed Pazaruvaj) | Determina quale identificatore di prodotto PrestaShop (ID, Riferimento, EAN13, UPC) viene inviato a Pazaruvaj.com per l'abbinamento dei prodotti. |
| Configurazione Modulo | Abilita consenso all'invio dei dati a Pazaruvaj.com | SÌ (Per conformità) | Richiede il consenso del cliente tramite una casella di controllo durante il checkout prima di inviare i dati a Pazaruvaj.com. |
| Configurazione Modulo | Mostra consenso su | Piè di pagina (Testa per il miglior posizionamento) | Specifica l'hook del front-office dove apparirà la casella di controllo del consenso se abilitata. |
| Configurazione Modulo | Abilita registro errori | SÌ (Per la risoluzione dei problemi) | Attiva la registrazione di eventuali errori durante l'invio dei dati a Pazaruvaj.com. |
| Configurazione Modulo | Cancella registro errori | N/A (Pulsante) | Elimina tutte le voci dal registro errori del modulo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non ricevono le email di sondaggio da Pazaruvaj.com. Cosa dovrei controllare?**
R:

1.  **ID Negozio Pazaruvaj.com:** Ricontrolla che il tuo "ID Negozio Pazaruvaj.com" nella configurazione del modulo sia assolutamente corretto e corrisponda all'ID fornito da Pazaruvaj.com.
2.  **Registro errori:** Abilita il "Registro errori" nella configurazione del modulo e controlla eventuali errori registrati dopo un ordine di prova. Questo spesso indicherà il problema esatto.
3.  **Impostazione del consenso:** Se "Abilita consenso all'invio dei dati a Pazaruvaj.com" è abilitato, assicurati che i clienti stiano effettivamente spuntando la casella di controllo durante il checkout. Se non lo fanno, i dati non verranno inviati.
4.  **Stato dell'ordine:** Assicurati che l'ordine raggiunga uno stato "Pagamento accettato" o uno stato finale simile in PrestaShop, poiché il modulo si attiva tipicamente al completamento dell'ordine.
5.  **Account Pazaruvaj.com:** Accedi al tuo account Pazaruvaj.com per vedere se ci sono problemi o avvisi da parte loro riguardo al tuo negozio o al feed di dati.

**D: La casella di controllo del consenso non appare nella mia pagina di checkout.**
R:

1.  **Impostazione "Abilita consenso":** Innanzitutto, assicurati che "Abilita consenso all'invio dei dati a Pazaruvaj.com" sia impostato su SÌ nella configurazione del modulo.
2.  **Impostazione "Mostra consenso su":** Controlla quale hook hai selezionato per "Mostra consenso su". Se il tuo tema non visualizza attivamente il contenuto in quell'hook specifico (es. un `displayMyCustomHook` personalizzato), la casella di controllo non apparirà. Prova a passare a un hook comune come `displayFooter` o `displayHeader` per testare.
3.  **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero sovrascrivere i posizionamenti standard degli hook. Se il problema persiste, potrebbe essere necessario che un webmaster ispezioni i file del template del tuo tema.
4.  **Cache Smarty:** Cancella la cache Smarty di PrestaShop in **Parametri avanzati > Prestazioni** (Forza compilazione e svuota cache).

**D: Ho modificato un'impostazione, ma non è successo nulla nel mio negozio.**
R: Dopo aver apportato modifiche nella configurazione del modulo, svuota sempre la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni**, quindi clicca su "Svuota cache" e opzionalmente "Forza compilazione" se stai apportando modifiche relative al template. Potrebbe essere necessario svuotare anche la cache del tuo browser (Ctrl+F5 o Cmd+R).

**D: Posso personalizzare il testo della casella di controllo del consenso?**
R: Sì, il testo della casella di controllo del consenso è traducibile. Puoi modificarlo tramite il sistema di traduzione di PrestaShop:

1.  Vai su **Internazionale > Traduzioni**.
2.  Seleziona "Traduzioni dei moduli installati".
3.  Scegli il tuo tema, la lingua e quindi seleziona "MyPazaruvaj".
4.  Troverai la stringa relativa al messaggio di consenso lì e potrai modificarla.

**D: Cosa succede se ho più negozi (multistore) abilitati?**
R: Il modulo deve essere configurato individualmente per ogni negozio in un ambiente multistore. Assicurati di selezionare il contesto del negozio corretto nel back office di PrestaShop prima di configurare il modulo per quel negozio specifico. Ogni negozio avrà probabilmente il proprio ID Negozio Pazaruvaj.com univoco.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo MyPazaruvaj.

### 4.1 Panoramica dell'architettura

Il modulo MyPazaruvaj segue un'architettura standard per i moduli PrestaShop, utilizzando principalmente la classe `Module` e i suoi metodi `install()`, `uninstall()` e `getContent()` per la configurazione. La sua funzionalità principale è basata sugli eventi, sfruttando gli hook di PrestaShop per intercettare gli eventi di conferma dell'ordine e visualizzare il consenso opzionale. L'invio dei dati a Pazaruvaj.com è gestito direttamente all'interno del file PHP principale del modulo, senza controller front-office o admin dedicati, rendendolo una soluzione leggera ed efficiente.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office dedicati. Tutta la logica di configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo, e la logica di visualizzazione del front-office è gestita direttamente tramite i template degli hook.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate né estende `ObjectModel`. Tutta la logica è contenuta all'interno della classe principale `MyPazaruvaj` definita in `mypazaruvaj/index.php`.

La classe principale `MyPazaruvaj` estende `Module` e contiene:

-   `__construct()`: Imposta le proprietà del modulo (nome, tab, versione, autore, `need_instance`, `ps_versions_compliancy`, `bootstrap`).
-   `install()`: Registra gli hook necessari (`displayOrderConfirmation`, `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`), crea le voci di configurazione e inizializza il file di log degli errori.
-   `uninstall()`: Deregistra gli hook ed elimina le voci di configurazione.
-   `getContent()`: Renderizza il modulo di configurazione del back-office, gestisce gli invii del modulo e aggiorna i valori di configurazione.
-   `hookDisplayOrderConfirmation()`: L'hook primario per l'invio dei dati. Recupera i dettagli dell'ordine, le informazioni del cliente e i dati del prodotto, quindi costruisce e invia la richiesta a Pazaruvaj.com. Gestisce anche il controllo del consenso opzionale.
-   `hookDisplayHeader()`, `hookDisplayFooter()`, `hookDisplayLeftColumn()`, `hookDisplayRightColumn()`: Questi hook vengono utilizzati per visualizzare la casella di controllo del consenso se abilitata e configurata per apparire in queste posizioni. Renderizzano il template `consent.tpl`.
-   `_clearLog()`: Metodo interno per cancellare il file di log degli errori.
-   `_writeLog()`: Metodo interno per scrivere messaggi nel file di log degli errori.
-   `_displayForm()`: Metodo interno per renderizzare il modulo di configurazione utilizzando `HelperForm` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Qualsiasi stile per la casella di controllo del consenso si baserebbe sullo stile predefinito degli elementi del modulo del tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:

    -   `mypazaruvaj/views/templates/hook/consent.tpl`:
        -   **Scopo:** Renderizza la casella di controllo del consenso opzionale per l'invio dei dati a Pazaruvaj.com.
        -   **Renderizzato negli hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn` (a seconda della configurazione del modulo).
        -   **Variabili:** Tipicamente controlla `$consent_enabled` e visualizza un input del modulo.
        -   **Output:** Una semplice casella di controllo HTML e un'etichetta.
    -   `mypazaruvaj/views/templates/hook/displayOrderConfirmation.tpl`:
        -   **Scopo:** Questo template è probabilmente un segnaposto o utilizzato per la logica interna del modulo che non produce direttamente contenuto visibile al cliente. La logica principale di invio dei dati per `displayOrderConfirmation` è gestita nel metodo PHP dell'hook stesso, non necessariamente tramite un output del template. Potrebbe essere utilizzato per passare variabili o attivare JS se il modulo ne avesse. Nel contesto di questo modulo, è principalmente il metodo PHP dell'hook che esegue l'azione.
-   **Template di amministrazione (`views/templates/admin/`)**:

    -   Questo modulo non utilizza template di amministrazione dedicati. Il modulo di configurazione viene generato programmaticamente utilizzando `HelperForm` all'interno di `getContent()`.
-   **Template del front-office (`views/templates/front/`)**:

    -   Questo modulo non include alcun template dedicato al front-office oltre ai template degli hook.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration` di PrestaShop.
        -   `MYPAZARUVAJ_SHOP_ID`: Memorizza l'ID Negozio Pazaruvaj.com.
        -   `MYPAZARUVAJ_PRODUCT_ID_FIELD`: Memorizza il campo ID prodotto selezionato (es. 'id\_product', 'reference').
        -   `MYPAZARUVAJ_CONSENT_ENABLED`: Booleano (0 o 1) per abilitare/disabilitare il consenso.
        -   `MYPAZARUVAJ_CONSENT_HOOK`: Memorizza il nome dell'hook in cui viene visualizzato il consenso.
        -   `MYPAZARUVAJ_ERROR_LOG_ENABLED`: Booleano (0 o 1) per abilitare/disabilitare il log degli errori.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayOrderConfirmation` | Dopo che un cliente completa con successo un ordine. | **Hook primario per l'invio dei dati.** Recupera i dettagli dell'ordine e del prodotto, costruisce la richiesta Pazaruvaj.com e la invia. Controlla il consenso se abilitato. |
| `displayHeader` | Nella sezione `<head>` o nella parte superiore di ogni pagina. | Renderizza `consent.tpl` se configurato per mostrare il consenso qui. |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Renderizza `consent.tpl` se configurato per mostrare il consenso qui. |
| `displayLeftColumn` | Nella colonna della barra laterale sinistra (se attiva nel tema). | Renderizza `consent.tpl` se configurato per mostrare il consenso qui. |
| `displayRightColumn` | Nella colonna della barra laterale destra (se attiva nel tema). | Renderizza `consent.tpl` se configurato per mostrare il consenso qui. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo al modulo MyPazaruvaj.
