---
title: "Quantità minima di prodotto - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Quantità minima di prodotto' di MyPresta.eu."
sidebar:
  label: "Quantità minima di prodotto - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Minimal product quantity su MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-product-quantity.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/minimal-product-quantity/)
>
> ---


# Quantità minima di prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali del modulo "Quantità minima di prodotto". Qui è dove definisci le regole fondamentali per le quantità minime.

La pagina di configurazione è progettata per essere intuitiva, consentendoti di impostare quantità minime per singoli prodotti e specifici gruppi di clienti.

**Come impostare una quantità minima per un prodotto:**

1.  **Cerca un prodotto:**

    -   Vedrai una barra di ricerca o un elenco di prodotti. Inizia a digitare il nome del prodotto che desideri configurare. Mentre digiti, il modulo suggerirà i prodotti corrispondenti.
    -   *Cosa fa questa impostazione:* Ti consente di individuare rapidamente il prodotto specifico a cui vuoi applicare una regola di quantità minima.
    -   *Effetto della modifica di questa impostazione:* N/A (funzione di ricerca).
    -   *Valore consigliato:* Digita il nome esatto del prodotto per precisione.
    -   *Scenario del commerciante:* Vuoi impostare un minimo per "Chicchi di caffè biologici (1kg)". Digita "Caffè biologico".
2.  **Seleziona il prodotto:**

    -   Clicca sul prodotto desiderato dai risultati della ricerca. Questo lo aggiungerà a un elenco di prodotti configurati di seguito.
    -   *Cosa fa questa impostazione:* Conferma a quale prodotto stai applicando la regola.
    -   *Effetto della modifica di questa impostazione:* Il prodotto appare nell'elenco di configurazione, pronto per le impostazioni di quantità e gruppo.
    -   *Valore consigliato:* Seleziona il prodotto corretto.
    -   *Scenario del commerciante:* Dopo aver digitato "Caffè biologico", clicchi su "Chicchi di caffè biologici (1kg)".
3.  **Imposta la quantità minima:**

    -   Accanto al prodotto selezionato, ci sarà un campo di input (es. "Quantità minima"). Inserisci il numero più basso di unità che un cliente deve acquistare per questo prodotto specifico.
    -   *Cosa fa questa impostazione:* Definisce il numero minimo assoluto di unità per questo prodotto.
    -   *Effetto della modifica di questa impostazione:*
        -   *Se impostato a 5:* I clienti devono aggiungere almeno 5 unità di questo prodotto al loro carrello. Se tentano di aggiungere 1, 2, 3 o 4, riceveranno un messaggio di errore.
        -   *Se impostato a 1 (o comportamento predefinito di PrestaShop):* Nessuna quantità minima speciale viene applicata oltre il valore predefinito di PrestaShop.
    -   *Valore consigliato:* Un numero maggiore di 1, che rifletta le tue esigenze aziendali (es. 6, 12, 24).
    -   *Scenario del commerciante:* Vendi chicchi di caffè all'ingrosso. Imposti la "Quantità minima" a 5.
4.  **Seleziona il gruppo di clienti (Opzionale):**

    -   Probabilmente vedrai un menu a discesa o un elenco di gruppi di clienti (es. "Ospite", "Cliente", "Grossista"). Puoi selezionare uno o più gruppi per i quali si applica questa quantità minima.
    -   *Cosa fa questa impostazione:* Ti consente di applicare diverse regole di quantità minima in base al gruppo del cliente. Se non viene selezionato alcun gruppo, la regola si applica a tutti i clienti.
    -   *Effetto della modifica di questa impostazione:*
        -   *Quando è selezionato "Grossista":* Solo i clienti appartenenti al gruppo "Grossista" saranno soggetti a questa quantità minima. Altri gruppi potrebbero avere un minimo diverso (o nessun minimo).
        -   *Quando non è selezionato un gruppo specifico (o è implicito "Tutti i clienti"):* La quantità minima si applica a ogni cliente, indipendentemente dal suo gruppo.
    -   *Valore consigliato:* Seleziona gruppi specifici se hai diverse strategie di prezzo o di vendita per essi. Altrimenti, lascialo per "Tutti i clienti".
    -   *Scenario del commerciante:* Vuoi che i grossisti acquistino almeno 10 unità, ma i clienti regolari devono acquistarne solo 5. Creeresti due regole separate per lo stesso prodotto, una per il gruppo "Grossista" con quantità 10, e un'altra per il gruppo "Cliente" con quantità 5.
5.  **Salva modifiche:**

    -   Dopo aver configurato il/i prodotto/i e le relative quantità minime/gruppi, ricorda di cliccare sul pulsante "Salva" o "Aggiorna" per applicare le tue impostazioni.
    -   *Cosa fa questa impostazione:* Persiste le modifiche alla configurazione nel database.
    -   *Effetto della modifica di questa impostazione:* Le nuove regole di quantità minima diventano attive sul tuo front office immediatamente.
    -   *Valore consigliato:* Salva sempre dopo aver apportato modifiche.
    -   *Scenario del commerciante:* Hai impostato tutti i tuoi minimi; ora clicchi su "Salva" per renderli attivi.

**Impostazioni generali del modulo (se presenti):**

Mentre la funzione principale è quella delle quantità minime per prodotto, alcuni moduli potrebbero includere impostazioni generali:

-   **Abilita/Disabilita Modulo:**

    -   *Cosa fa questa impostazione:* Attiva o disattiva la funzionalità dell'intero modulo.
    -   *Effetto della modifica di questa impostazione:*
        -   *Quando abilitato:* Le regole di quantità minima vengono applicate.
        -   *Quando disabilitato:* Tutte le regole di quantità minima vengono ignorate e i clienti possono aggiungere qualsiasi quantità.
    -   *Valore consigliato:* SÌ (abilitato) una volta configurato.
    -   *Scenario del commerciante:* Stai testando il modulo e vuoi disabilitarlo temporaneamente senza perdere le tue impostazioni.
-   **Tipo di messaggio di errore da visualizzare (es. Pop-up, In linea):**

    -   *Cosa fa questa impostazione:* Controlla come il cliente viene notificato quando tenta di aggiungere meno della quantità minima.
    -   *Effetto della modifica di questa impostazione:*
        -   *Se impostato su Pop-up:* Appare una finestra modale, interrompendo il flusso dell'utente, che indica chiaramente il problema.
        -   *Se impostato su In linea:* Appare un messaggio direttamente sulla pagina del prodotto o nel carrello, senza un pop-up.
    -   *Valore consigliato:* Il pop-up è spesso più efficace per errori critici come le quantità minime, poiché richiede attenzione.
    -   *Scenario del commerciante:* Vuoi assicurarti che i clienti non perdano il requisito di quantità minima, quindi scegli un pop-up.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Ricerca prodotto | N/A | Individua i prodotti a cui applicare le regole di quantità minima. |
| Pagina di configurazione del modulo | Quantità minima (per prodotto) | Varia (es. 5, 10) | Imposta il numero più basso di unità che un cliente deve acquistare per quel prodotto. |
| Pagina di configurazione del modulo | Gruppo clienti (per prodotto) | Tutti i clienti | Applica la regola di quantità minima a specifici gruppi di clienti o a tutti i clienti. |
| Pagina di configurazione del modulo | Pulsante Salva | N/A | Applica tutte le regole di quantità minima configurate al negozio. |
| Pagina di configurazione del modulo | Abilita/Disabilita Modulo | Abilitato | Attiva o disattiva la funzionalità del modulo a livello globale. |
| Pagina di configurazione del modulo | Tipo di messaggio di errore | Pop-up | Definisce come gli errori di quantità minima vengono visualizzati ai clienti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato una quantità minima, ma non funziona nel mio negozio. Cosa c'è che non va?**
R:

1.  **Il modulo è abilitato?** Ricontrolla la pagina di configurazione principale per assicurarti che il modulo "Quantità minima di prodotto" sia attivo.
2.  **Hai salvato le modifiche?** Clicca sempre sul pulsante "Salva" o "Aggiorna" dopo aver apportato modifiche alla configurazione.
3.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, PrestaShop memorizza nella cache le vecchie impostazioni.
4.  **Verifica la presenza di conflitti con il tema:** Se hai un tema altamente personalizzato, potrebbe interferire con il modo in cui il modulo visualizza i messaggi o interagisce con il pulsante "Aggiungi al carrello". Passa temporaneamente al tema PrestaShop predefinito (Classic o Hummingbird) per vedere se il problema persiste. Se si risolve, il tuo tema necessita di una regolazione.
5.  **Gruppo clienti:** Assicurati che il cliente con cui stai testando appartenga al gruppo per il quale è impostata la quantità minima. Se non è specificato alcun gruppo, dovrebbe applicarsi a tutti.

**D2: La notifica pop-up ha un aspetto strano o non corrisponde al design del mio negozio.**
R: Il modulo utilizza il proprio CSS per il pop-up. Se il tuo tema ha regole di stile molto specifiche, potrebbero sovrascrivere o entrare in conflitto.

1.  **Controlla le impostazioni del modulo:** Vedi se il modulo offre opzioni per personalizzare l'aspetto del pop-up o scegliere un metodo di visualizzazione diverso (es. messaggio in linea invece di pop-up).
2.  **CSS personalizzato:** Per sviluppatori o webmaster, è possibile aggiungere CSS personalizzato al file `custom.css` del tuo tema per sovrascrivere gli stili predefiniti del modulo. (Vedi Sezione 7.5 per i dettagli del file CSS).

**D3: Posso impostare una quantità minima per le combinazioni di prodotti (attributi)?**
R: Il modulo applica tipicamente le quantità minime a livello di prodotto. Se hai bisogno di minimi specifici per le combinazioni (es. "Maglietta rossa, Taglia S" vs. "Maglietta blu, Taglia L"), potresti dover verificare se il modulo supporta esplicitamente questa funzionalità nella sua configurazione. In caso contrario, imposteresti il minimo per il prodotto padre, che si applica a qualsiasi combinazione di quel prodotto.

**D4: Come posso tradurre i messaggi del modulo in altre lingue?**
R:

1.  Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2.  Seleziona "Traduzioni dei moduli installati".
3.  Scegli il tuo tema, la lingua che desideri tradurre e quindi seleziona "Quantità minima di prodotto" dall'elenco dei moduli.
4.  Troverai tutte le stringhe traducibili utilizzate dal modulo (es. "Devi aggiungere almeno X unità di questo prodotto"). Traducile e salva.

**D5: Cosa succede se un cliente ha un prodotto nel carrello a cui viene successivamente applicata una quantità minima?**
R: Quando il cliente visiterà nuovamente il carrello o tenterà di effettuare il checkout, il modulo rileverà la discrepanza. Verrà visualizzato il messaggio di errore e gli verrà impedito di procedere finché non avrà regolato la quantità per soddisfare il nuovo minimo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Quantità minima di prodotto" (`minqc`) segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente gli hook per iniettare la sua logica e le risorse front-end. Opera intercettando le modifiche di quantità e le aggiunte al carrello, convalidando rispetto ai minimi configurati e visualizzando un feedback all'utente. La logica centrale del modulo risiede nel suo file `index.php` principale, che gestisce l'installazione, la disinstallazione, la configurazione e la registrazione degli hook. L'interazione front-end è gestita tramite una suite di file JavaScript personalizzati per diverse versioni e contesti di PrestaShop (pagina prodotto, carrello, visualizzazione rapida).

### 4.2 Controller (`controllers/`)

Questo modulo non sembra utilizzare controller Front-Office o Back-Office Admin personalizzati. La sua configurazione è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo, e le interazioni front-office sono gestite tramite JavaScript e chiamate AJAX alle funzionalità core di PrestaShop o al proprio `ajax.php` del modulo (se presente, anche se non esplicitamente elencato come controller dedicato, è un pattern comune per i moduli gestire le richieste AJAX tramite il loro file principale o uno script semplice).

### 4.3 Classi e Modelli Core (`classes/`)

Sulla base dell'inventario fornito, questo modulo non definisce classi `ObjectModel` personalizzate o altre classi PHP complesse in una directory `classes/` dedicata. La sua logica è probabilmente incapsulata all'interno del file `minqc/index.php` principale, interagendo direttamente con `Configuration` per le impostazioni e potenzialmente `Db` per l'archiviazione di dati personalizzati se i minimi specifici del prodotto sono memorizzati al di fuori di `ps_configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo utilizza ampiamente JavaScript per fornire un'esperienza utente dinamica e applicare le regole di quantità in tempo reale.

-   `minqc/views/js/minqc.js`:

    -   **Ambito:** Probabilmente un file JS core, potenzialmente caricato globalmente o su più pagine.
    -   **Responsabilità:** Contiene funzioni di utilità generali, binding di eventi per elementi comuni e potenzialmente la logica principale per il controllo delle quantità minime prima di aggiungere al carrello o aggiornare il carrello. Potrebbe gestire la visualizzazione della notifica pop-up.
    -   **Interazioni:** Si lega agli eventi `click` sui pulsanti "Aggiungi al carrello", agli eventi `change` sui campi di input della quantità e potenzialmente agli eventi `prestashop.on` per gli aggiornamenti del carrello AJAX.
-   `minqc/views/js/minqc-17500.js`:

    -   **Ambito:** Front-office, specificamente per PrestaShop 1.7.5.0 e versioni più recenti (o intervalli di versione simili).
    -   **Responsabilità:** Contiene la logica JavaScript specifica della versione per adattarsi ai cambiamenti nella struttura del front-office di PrestaShop, al comportamento del carrello AJAX o agli elementi della pagina del prodotto introdotti in queste versioni.
    -   **Interazioni:** Sovrascrive o estende `minqc.js` per specifiche strutture DOM e gestione degli eventi di PrestaShop 1.7+.
-   `minqc/views/js/minqc-admin-product.js`:

    -   **Ambito:** Back-office, specificamente sulla pagina di modifica del prodotto (`AdminProducts`).
    -   **Responsabilità:** Se il modulo consente di impostare quantità minime direttamente sulla pagina di modifica del prodotto, questo script gestirebbe l'interfaccia utente per questo (es. aggiungendo campi di input, salvando i valori tramite AJAX).
    -   **Interazioni:** Si lega agli eventi sugli elementi del modulo prodotto, effettua chiamate AJAX per salvare i minimi specifici del prodotto.
-   `minqc/views/js/minqc-cart.js`:

    -   **Ambito:** Front-office, specificamente sulla pagina del carrello.
    -   **Responsabilità:** Monitora le modifiche di quantità all'interno del carrello, convalida rispetto ai minimi e impedisce il checkout se le regole vengono violate. Visualizza messaggi di errore o pop-up sulla pagina del carrello.
    -   **Interazioni:** Si lega alle modifiche dell'input della quantità, ai clic sul pulsante "Procedi al checkout" e potenzialmente agli eventi `prestashop.on` relativi agli aggiornamenti del carrello.
-   `minqc/views/js/minqc-front.js`:

    -   **Ambito:** Utilizzo generale del front-office.
    -   **Responsabilità:** Potrebbe essere uno script front-end più generico, che gestisce potenzialmente la visualizzazione delle informazioni sulla quantità minima negli elenchi di prodotti o in altre pagine non specifiche di prodotto/carrello.
    -   **Interazioni:** Manipolazione del DOM per la visualizzazione dei messaggi, potenzialmente chiamate AJAX per la convalida.
-   `minqc/views/js/minqc-no-autoadd.js`:

    -   **Ambito:** Front-office.
    -   **Responsabilità:** Suggerisce un comportamento specifico relativo alla prevenzione dell'aggiunta automatica di prodotti al carrello se i minimi non sono soddisfatti, o alla gestione di scenari in cui un prodotto potrebbe essere aggiunto automaticamente ma poi fallisce la convalida.
    -   **Interazioni:** Modifica il comportamento predefinito di "Aggiungi al carrello" per garantire che la convalida avvenga *prima* che l'articolo venga aggiunto.
-   `minqc/views/js/minqc-product-classic.js`:

    -   **Ambito:** Front-office, specificamente per i temi basati sul tema PrestaShop Classic (PrestaShop 1.7+).
    -   **Responsabilità:** Adatta l'applicazione e la visualizzazione della quantità minima alla struttura DOM e agli eventi JavaScript specifici della pagina del prodotto del tema Classic.
    -   **Interazioni:** Si lega al pulsante "Aggiungi al carrello" e agli elementi di input della quantità sulla pagina del prodotto del tema Classic.
-   `minqc/views/js/minqc-product-hummingbird.js`:

    -   **Ambito:** Front-office, specificamente per i temi basati sul tema PrestaShop Hummingbird (PrestaShop 8+).
    -   **Responsabilità:** Adatta l'applicazione e la visualizzazione della quantità minima alla struttura DOM e agli eventi JavaScript specifici della pagina del prodotto del tema Hummingbird.
    -   **Interazioni:** Si lega al pulsante "Aggiungi al carrello" e agli elementi di input della quantità sulla pagina del prodotto del tema Hummingbird.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `minqc/views/css/minqc.css`:
    -   **Ambito:** Front-office e potenzialmente Back-office per elementi UI specifici del modulo.
    -   **Componenti UI principali:** Stili per la notifica pop-up (sfondo modale, casella di contenuto, pulsante di chiusura, testo del messaggio), messaggi di errore in linea e potenzialmente indicatori visivi sulle pagine dei prodotti.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori possono ispezionare l'HTML di output del modulo per identificare classi specifiche (es. `.minqc-popup`, `.minqc-error-message`, `.minqc-quantity-input-error`) e sovrascriverle nel file `custom.css` o `theme.css` del loro tema per adattarle al branding del loro negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**: Non esplicitamente elencati, ma è comune per i moduli utilizzare `displayHeader` per JS/CSS, o `displayProductActions` per i messaggi della pagina del prodotto.
-   **Template di amministrazione (`views/templates/admin/`)**:

    -   `minqc/views/templates/admin/admin.tpl`: Probabilmente il template di configurazione principale per il modulo, renderizzato dal metodo `getContent()`. Contenerebbe la ricerca del prodotto, l'elenco dei prodotti configurati e le impostazioni generali.
    -   `minqc/views/templates/admin/admintab.tpl`: Potrebbe essere un sotto-template per una scheda o sezione specifica all'interno della configurazione di amministrazione, o un template legacy.
    -   `minqc/views/templates/admin/_configure/helpers/list/list_content.tpl`: Questo suggerisce che il modulo utilizza `HelperList` di PrestaShop per visualizzare l'elenco dei prodotti con quantità minime configurate nel back office. Questo template definirebbe come viene renderizzata ogni riga di tale elenco.
-   **Template Ajax (`views/templates/ajax/`)**:

    -   `minqc/views/templates/ajax/minqcErrors.tpl`: Questo template è probabilmente utilizzato per renderizzare il contenuto HTML del pop-up di errore o dei messaggi in linea visualizzati al cliente quando una quantità minima non è soddisfatta. Verrebbe caricato tramite AJAX.
-   **Template front-office (`views/templates/front/`)**:

    -   `minqc/views/templates/front/beforeShoppingCart.tpl`: Questo template è probabilmente agganciato a una posizione prima del contenuto principale del carrello, potenzialmente per visualizzare un avviso o un riepilogo relativo alle quantità minime se il carrello non è valido.
    -   `minqc/views/templates/front/product-details.tpl`: Questo template verrebbe utilizzato per iniettare informazioni o avvisi sulla quantità minima direttamente nella pagina dei dettagli del prodotto, spesso vicino al selettore di quantità o al pulsante "Aggiungi al carrello".
    -   `minqc/views/templates/front/productActions.tpl`: Simile a `product-details.tpl`, questo template verrebbe agganciato all'hook `displayProductActions` (o simile) per visualizzare messaggi o modificare il comportamento del pulsante "Aggiungi al carrello" in base alle regole di quantità minima.
    -   `minqc/views/templates/front/qv.tpl`: Questo template è specificamente per la funzionalità "Visualizzazione rapida", iniettando informazioni o avvisi sulla quantità minima nel modale di visualizzazione rapida.

### 4.7 Schema del database e Mappa degli Hook

-   **Tabelle del database**:

    -   Il modulo probabilmente memorizza la sua configurazione per le quantità minime specifiche del prodotto e le associazioni dei gruppi di clienti nella tabella `ps_configuration` per semplici impostazioni globali.
    -   Per i minimi specifici del prodotto e del gruppo, è altamente probabile che il modulo crei la propria tabella di database personalizzata (es. `ps_minqc_product_quantity`) per memorizzare i valori `id_product`, `id_customer_group` e `min_quantity`. Questa tabella verrebbe creata durante il metodo `install()` e eliminata durante `uninstall()`.
-   **Tabella degli Hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS (`minqc.css`) e JavaScript (`minqc.js`, `minqc-front.js`, JS specifico della versione come `minqc-17500.js`, `minqc-product-classic.js`, `minqc-product-hummingbird.js`, `minqc-cart.js`, `minqc-no-autoadd.js`) del modulo per la funzionalità front-end. |
| `displayProductActions` | Sulla pagina del prodotto, tipicamente vicino al pulsante "Aggiungi al carrello". | Inietta `productActions.tpl` per visualizzare i requisiti o gli avvisi di quantità minima direttamente sulla pagina del prodotto. |
| `displayProductExtraContent` (o simile) | Sulla pagina del prodotto, per blocchi di contenuto aggiuntivi. | Potrebbe essere utilizzato per visualizzare `product-details.tpl` o altre informazioni. |
| `displayShoppingCartFooter` (o simile) | In fondo al riepilogo del carrello. | Inietta `beforeShoppingCart.tpl` o simile per visualizzare avvisi se gli articoli del carrello non soddisfano i minimi, impedendo il checkout. |
| `actionCartSave` | Dopo che un carrello viene salvato o aggiornato. | Attiva la logica PHP del modulo per riconvalidare tutte le quantità nel carrello rispetto ai minimi configurati. |
| `actionValidateOrder` | Prima che un ordine venga ufficialmente convalidato. | Controllo finale per garantire che tutte le quantità di prodotto nel carrello soddisfino i loro minimi prima che l'ordine venga effettuato. |
| `actionProductUpdate` / `actionProductAdd` | Quando un prodotto viene aggiornato o aggiunto nel Back Office. | Potenzialmente utilizzato per aggiornare o cancellare i dati di quantità minima memorizzati nella cache per quel prodotto. |
| `displayAdminProductsExtra` | Sulla pagina di modifica del prodotto nel Back Office. | Inietta elementi UI (es. tramite `admintab.tpl` o `admin.tpl`) per consentire l'impostazione di quantità minime specifiche del prodotto direttamente dal modulo del prodotto, utilizzando `minqc-admin-product.js`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda relativa al modulo "Quantità minima di prodotto".
"""
