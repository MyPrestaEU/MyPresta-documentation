---
title: "Assegna clienti a gruppi in base ai prodotti acquistati - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Assegna clienti a gruppi in base ai prodotti acquistati' di MyPresta.eu."
sidebar:
  label: "Assegna clienti a gruppi in base ai prodotti acquistati - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Assign customers to group by purchased products su MyPresta.eu](https://mypresta.eu/modules/ordering-process/assign-customers-to-group-by-purchased-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/assign-customers-to-group-by-purchased-products/)
>
> ---


# Assegna clienti a gruppi in base ai prodotti acquistati

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove gestisci le impostazioni principali del modulo.

-   **Cosa fa questa impostazione:** Questa sezione contiene tipicamente le impostazioni generali per il modulo, come l'abilitazione/disabilitazione della sua funzionalità principale.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo monitorerà attivamente gli acquisti dei clienti e applicherà le regole di assegnazione del gruppo definite.
    -   *Quando disabilitato:* Il modulo smetterà di elaborare nuovi ordini per le assegnazioni di gruppo. Le assegnazioni esistenti rimarranno, ma non ne verranno create di nuove automaticamente.
-   **Valore consigliato:** **SÌ** (Abilitato) per consentire al modulo di funzionare.
-   **Scenario / esempio del commerciante:** Se stai configurando il modulo per la prima volta, vorrai abilitarlo immediatamente dopo la configurazione. Se hai bisogno di interrompere temporaneamente le assegnazioni automatiche (ad esempio, durante una migrazione importante del negozio), puoi disabilitarlo qui.

### 2.2 Schermata di amministrazione dedicata: Associazioni Gruppo Prodotto

Questa è l'area di gestione principale dove definisci le regole per assegnare i clienti ai gruppi in base ai loro acquisti.

**Nome schermata e posizione nel menu:**
Puoi accedere a questa schermata navigando in **Moduli > Gestione moduli**, trovando "Assegna clienti a gruppi in base ai prodotti acquistati" e cliccando su "Configura". All'interno della configurazione del modulo, troverai una sezione o una scheda dedicata a "Associazioni Gruppo Prodotto" o simile.

**Azioni e impostazioni disponibili:**
In questa schermata, troverai tipicamente un elenco di regole di assegnazione esistenti. Avrai opzioni per:

-   **Aggiungi nuova regola:** Crea una nuova condizione per l'assegnazione del gruppo.
-   **Modifica regola:** Modifica una regola esistente.
-   **Elimina regola:** Rimuovi una regola.

Quando aggiungi o modifichi una regola, configurerai quanto segue:

1.  **Seleziona Gruppo Clienti:**

    -   **Cosa fa questa impostazione:** Questo è il gruppo di destinazione a cui i clienti verranno assegnati se soddisfano le condizioni della regola.
    -   **Effetto della modifica di questa impostazione:** Quando l'acquisto di un cliente attiva questa regola, verrà spostato (o aggiunto) al gruppo di clienti selezionato.
    -   **Valore consigliato:** Scegli il gruppo di clienti specifico che desideri segmentare (ad esempio, "Clienti all'ingrosso", "Acquirenti VIP", "Appassionati di elettronica").
    -   **Scenario / esempio del commerciante:** Vuoi creare una regola per assegnare i clienti al tuo gruppo "Acquirenti VIP".
2.  **Seleziona Prodotti / Categorie:**

    -   **Cosa fa questa impostazione:** Qui definisci *quali* prodotti o categorie di prodotti, una volta acquistati, attiveranno l'assegnazione del gruppo. Di solito puoi selezionare più prodotti o categorie. Il modulo probabilmente include uno strumento di ricerca per trovare facilmente i prodotti.
    -   **Effetto della modifica di questa impostazione:** Solo gli acquisti contenenti i prodotti specificati o dalle categorie specificate attiveranno questa regola.
    -   **Valore consigliato:** Sii preciso. Utilizza lo strumento di ricerca per selezionare tutti i prodotti o le categorie pertinenti.
    -   **Scenario / esempio del commerciante:** Per il gruppo "Acquirenti VIP", potresti selezionare prodotti di alto valore come "Orologio di lusso X" e "Collana di diamanti Y". Per gli "Appassionati di elettronica", potresti selezionare l'intera categoria "Elettronica".
3.  **Quantità minima (Opzionale):**

    -   **Cosa fa questa impostazione:** Se specificato, il cliente deve acquistare almeno questa quantità dei prodotti/categorie selezionati in un singolo ordine per essere assegnato al gruppo.
    -   **Effetto della modifica di questa impostazione:** Se un cliente acquista meno della quantità minima, la regola non si applicherà, anche se ha acquistato i prodotti specificati.
    -   **Valore consigliato:** Lascia vuoto per qualsiasi quantità, o imposta un valore come "1" per almeno un articolo, o "5" per acquirenti all'ingrosso.
    -   **Scenario / esempio del commerciante:** Per essere un "Cliente all'ingrosso", devono acquistare almeno 10 unità di qualsiasi prodotto dalla categoria "Prodotti sfusi".
4.  **Stato dell'ordine per attivare l'assegnazione:**

    -   **Cosa fa questa impostazione:** Questo determina a quale stato dell'ordine dovrebbe avvenire l'assegnazione del gruppo clienti. Ad esempio, potresti voler assegnare i gruppi solo una volta che un ordine è "Pagamento accettato" o "Consegnato".
    -   **Effetto della modifica di questa impostazione:** Il modulo elaborerà l'assegnazione del gruppo solo quando un ordine raggiunge lo stato selezionato. Se un ordine non raggiunge mai quello stato (ad esempio, "Annullato"), l'assegnazione non avverrà.
    -   **Valore consigliato:** "Pagamento accettato" o "Consegnato" sono generalmente scelte sicure per garantire che l'acquisto sia confermato.
    -   **Scenario / esempio del commerciante:** Vuoi assicurarti che i clienti abbiano effettivamente pagato prima di essere aggiunti a un gruppo speciale, quindi selezioni "Pagamento accettato".
5.  **Assegna al gruppo (Aggiungi o Sostituisci):**

    -   **Cosa fa questa impostazione:** Questa opzione cruciale determina come viene gestita l'appartenenza al gruppo del cliente.
        -   **Aggiungi al gruppo:** Il cliente verrà aggiunto al gruppo selezionato *in aggiunta* a qualsiasi gruppo in cui si trova già.
        -   **Sostituisci gruppo attuale:** Il gruppo *primario* del cliente verrà modificato nel gruppo selezionato, rimuovendolo potenzialmente dal suo precedente gruppo primario.
    -   **Effetto della modifica di questa impostazione:**
        -   *Aggiungi al gruppo:* I clienti possono appartenere a più gruppi, consentendo una segmentazione flessibile.
        -   *Sostituisci gruppo attuale:* I clienti apparterranno a un solo gruppo primario, semplificando la gestione ma potenzialmente perdendo altre affiliazioni di gruppo.
    -   **Valore consigliato:** "Aggiungi al gruppo" offre maggiore flessibilità per la maggior parte degli scenari. Utilizza "Sostituisci gruppo attuale" con cautela, specialmente se altri moduli si basano su assegnazioni di gruppo primarie.
    -   **Scenario / esempio del commerciante:**
        -   *Aggiungi al gruppo:* Un cliente che acquista un prodotto specifico viene aggiunto a "Acquirenti VIP" ma rimane in "Clienti Generali".
        -   *Sostituisci gruppo attuale:* Un cliente che acquista un prodotto specifico viene spostato da "Clienti Generali" a "Clienti all'ingrosso", diventando il loro nuovo gruppo primario.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1.  **Pianifica i tuoi segmenti di clienti:** Prima di creare le regole, decidi quali gruppi di clienti vuoi avere e quali criteri li definiscono.
2.  **Crea i tuoi gruppi di clienti:** Vai su **Clienti > Gruppi** nel tuo Back Office di PrestaShop e crea tutti i nuovi gruppi di cui hai bisogno (ad esempio, "Grossisti", "VIP", "Acquirenti Prodotto X").
3.  **Definisci le regole:** Per ogni gruppo di clienti, crea una nuova regola di associazione nella configurazione del modulo.
4.  **Testa accuratamente:** Effettua un acquisto di prova con un account cliente di prova per assicurarti che l'assegnazione del gruppo avvenga come previsto.
5.  **Rivedi regolarmente:** Controlla periodicamente le tue regole e le assegnazioni dei gruppi di clienti per assicurarti che siano ancora pertinenti ai tuoi obiettivi aziendali.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Modulo Abilitato/Disabilitato | Abilitato | Controlla se il modulo elabora attivamente gli ordini per le assegnazioni di gruppo. |
| **Associazioni Gruppo Prodotto** | Gruppo Clienti di Destinazione | N/A (Definito dall'utente) | Il gruppo a cui i clienti verranno assegnati. |
| | Prodotti / Categorie | N/A (Definito dall'utente) | I prodotti o le categorie specifici il cui acquisto attiva l'assegnazione. |
| | Quantità minima | Vuoto (Qualsiasi quantità) | Numero minimo di articoli dai prodotti/categorie della regola richiesto in un ordine. |
| | Stato dell'ordine per attivare | Pagamento accettato / Consegnato | Lo stato dell'ordine in cui viene elaborata l'assegnazione del gruppo. |
| | Tipo di assegnazione | Aggiungi al gruppo | Determina se il cliente viene aggiunto al gruppo o se il suo gruppo primario viene sostituito. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non vengono assegnati ai gruppi dopo l'acquisto. Cosa c'è che non va?**
R:

1.  **Controlla lo stato del modulo:** Assicurati che il modulo sia abilitato in **Moduli > Gestione moduli** e nella sua pagina di configurazione principale.
2.  **Verifica lo stato dell'ordine:** Controlla l'impostazione "Stato dell'ordine per attivare l'assegnazione" della tua regola. L'ordine del cliente ha effettivamente raggiunto quello stato specifico (ad esempio, "Pagamento accettato", "Consegnato")? Gli ordini in stato "In sospeso" o "Annullato" non attiveranno l'assegnazione se la tua regola specifica uno stato successivo.
3.  **Rivedi le condizioni della regola:** Ricontrolla i prodotti/categorie selezionati nella tua regola. Sono esattamente quelli che il cliente ha acquistato? La "Quantità minima" è stata raggiunta?
4.  **Svuota la cache:** A volte la cache di PrestaShop può causare problemi. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".
5.  **Verifica la presenza di conflitti:** Disabilita temporaneamente altri moduli che modificano i gruppi di clienti o l'elaborazione degli ordini per vedere se c'è un conflitto.

**D: Un cliente può far parte di più gruppi?**
R: Sì, se utilizzi l'opzione "Aggiungi al gruppo" quando crei le tue regole. Questo permette ai clienti di accumulare appartenenze a gruppi in base a vari comportamenti di acquisto. Se utilizzi "Sostituisci gruppo attuale", faranno parte di un solo gruppo primario.

**D: Cosa succede se un cliente acquista prodotti che attivano più regole?**
R: Il modulo elaborerà tutte le regole applicabili. Se le regole utilizzano "Aggiungi al gruppo", il cliente verrà aggiunto a tutti i gruppi pertinenti. Se le regole utilizzano "Sostituisci gruppo attuale", l'ultima regola elaborata (in base alla logica interna del modulo o all'ordine di creazione delle regole) potrebbe determinare il gruppo primario finale, ma è buona pratica evitare regole "Sostituisci" in conflitto.

**D: Ho modificato una regola, ma gli ordini precedenti non si aggiornano. Perché?**
R: Il modulo elabora tipicamente le assegnazioni di gruppo quando lo stato di un ordine *cambia* allo stato specificato. Non applica retroattivamente le regole agli ordini già completati ed elaborati. Se hai bisogno di rivalutare i clienti passati, potresti doverli assegnare manualmente o considerare uno script personalizzato (per gli sviluppatori) per rieseguire la logica.

**D: Come si traduce il testo del modulo?**
R: Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi seleziona "Assegna clienti a gruppi in base ai prodotti acquistati" dall'elenco dei moduli. Potrai quindi tradurre tutte le stringhe visibili.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Assegna clienti a gruppi in base ai prodotti acquistati" (`pgroup`) segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente il pattern MVC per i suoi componenti del Back Office. Si integra con la funzionalità principale di PrestaShop tramite hook, in particolare reagendo ai cambiamenti di stato degli ordini per attivare la sua logica di assegnazione del gruppo clienti. Il modulo non introduce alcun controller front-office, poiché la sua funzionalità è interamente basata sul backend. Utilizza un `AdminController` personalizzato per la gestione delle regole di associazione prodotto-gruppo e si basa su `ObjectModel` di PrestaShop per la persistenza dei dati.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Tutta la logica è gestita nel Back Office o tramite hook.
-   **Controller Admin Back-Office**:

    -   `pgroup/controllers/admin/AdminProductGroupsAssociationsController.php`
        -   **Nome classe:** `AdminProductGroupsAssociationsController` (estende `ModuleAdminController`)
        -   **Responsabilità:** Questo è il controller principale per la gestione delle regole di associazione prodotto-gruppo clienti. Gestisce la visualizzazione dell'elenco delle regole (utilizzando `HelperList`) e la creazione/modifica delle singole regole (utilizzando `HelperForm`). Interagisce con l'`ObjectModel` `PgAssign` per persistere e recuperare i dati di associazione. Questo controller è responsabile del rendering della griglia delle associazioni e del modulo per aggiungerle/modificarle.
    -   `pgroup/controllers/admin/index.php`
        -   **Nome classe:** Non una classe, tipicamente un file vuoto o un semplice reindirizzamento per prevenire l'accesso diretto alla directory. In PrestaShop, i file `index.php` all'interno delle directory dei controller di solito servono come segnaposto di sicurezza.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che il modello di dati primario per le assegnazioni prodotto-gruppo è probabilmente definito direttamente all'interno del file principale del modulo (`pgroup/index.php`) come `ObjectModel` o gestito tramite query dirette al database.

-   **Modello probabile (all'interno di `pgroup/index.php`):**
    -   **Nome classe:** `PgAssign` (o simile, che estende `ObjectModel`)
    -   **Tabella del database:** `ps_pgassign` (o simile, basato sull'`AdminProductGroupsAssociationsController` che gestisce l'entità `pgassign`).
    -   **Campi `$definition`:** Includerebbe tipicamente campi come:
        -   `id_pgassign` (Chiave primaria)
        -   `id_group` (ID del gruppo clienti di destinazione)
        -   `id_product` (ID del prodotto, se la regola è specifica del prodotto)
        -   `id_category` (ID della categoria, se la regola è specifica della categoria)
        -   `min_quantity` (Quantità minima richiesta)
        -   `id_order_state` (Stato dell'ordine per attivare l'assegnazione)
        -   `assignment_type` (ad es. 'add' o 'replace')
    -   **Metodi pubblici chiave:**
        -   `add()`: Per salvare una nuova regola di associazione.
        -   `update()`: Per modificare una regola di associazione esistente.
        -   `delete()`: Per rimuovere una regola di associazione.
        -   `getAssociationsByProduct($id_product)`: Per recuperare le regole in base a un prodotto.
        -   `getAssociationsByCategory($id_category)`: Per recuperare le regole in base a una categoria.

### 4.4 Risorse JavaScript (`views/js/`)

-   `pgroup/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office (probabilmente utilizzato nel modulo `AdminProductGroupsAssociationsController`).
    -   **Funzionalità:** Implementa una funzione di ricerca con autocompletamento, probabilmente per selezionare prodotti o categorie durante la creazione/modifica di una regola di assegnazione. Ascolta l'input dell'utente in un campo di testo specifico, invia richieste AJAX a un endpoint backend (probabilmente un controller AJAX admin dedicato o il metodo `ajaxProcess` del modulo principale) per recuperare prodotti/categorie corrispondenti e visualizza i suggerimenti. Gestisce quindi la selezione di un elemento, popolando i campi di input nascosti con gli ID.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `pgroup/css.css`
    -   **Ambito:** Back-office (stile generale del modulo).
    -   **Funzionalità:** Contiene regole di stile generali per la pagina di configurazione del modulo e potenzialmente l'interfaccia di `AdminProductGroupsAssociationsController`. Questo potrebbe includere stili per elementi del modulo, pulsanti o regolazioni del layout specifiche del modulo.
-   `pgroup/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office (stile specifico dell'autocompletamento).
    -   **Funzionalità:** Fornisce lo stile per il campo di input di ricerca con autocompletamento, l'elenco a discesa dei suggerimenti e gli elementi evidenziati all'interno dell'elenco. Gli sviluppatori possono sovrascrivere queste classi per adattarle ai temi personalizzati del Back Office.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, indicando che l'impatto front-office del modulo è indiretto e non tramite iniezione diretta di contenuti tramite hook.
-   **Template admin (`views/templates/admin/`)**:

    -   `pgroup/lib/searchTool/views/scripts.tpl`
        -   **Ambito:** Back-office.
        -   **Funzionalità:** Probabilmente include script di inizializzazione JavaScript per la funzionalità di autocompletamento. Questo template verrebbe incluso nel modulo di `AdminProductGroupsAssociationsController` per renderizzare il JS necessario per lo strumento di ricerca prodotti/categorie.
    -   `pgroup/views/templates/admin/orderstates.tpl`
        -   **Ambito:** Back-office.
        -   **Funzionalità:** Questo template probabilmente renderizza un menu a discesa o un elenco di stati dell'ordine di PrestaShop, consentendo al commerciante di selezionare quale stato dovrebbe attivare l'assegnazione del gruppo clienti. Farebbe parte dell'`HelperForm` utilizzato in `AdminProductGroupsAssociationsController`.
    -   `pgroup/views/templates/admin/script.tpl`
        -   **Ambito:** Back-office.
        -   **Funzionalità:** Potrebbe contenere JavaScript aggiuntivo o logica Smarty specifica per la pagina di configurazione del modulo o i moduli di `AdminProductGroupsAssociationsController`, come la visualizzazione condizionale dei campi o le chiamate AJAX.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_pgassign`: Questa tabella viene creata dal modulo durante l'installazione. Memorizza le regole di associazione prodotto-gruppo.
        -   `id_pgassign` (INT, CHIAVE PRIMARIA, AUTO_INCREMENT)
        -   `id_group` (INT, chiave esterna a `ps_group`)
        -   `id_product` (INT, chiave esterna a `ps_product`, nullable se la regola è basata sulla categoria)
        -   `id_category` (INT, chiave esterna a `ps_category`, nullable se la regola è basata sul prodotto)
        -   `min_quantity` (INT, predefinito 1)
        -   `id_order_state` (INT, chiave esterna a `ps_order_state`)
        -   `assignment_type` (VARCHAR, ad es. 'add', 'replace')
    -   Record di configurazione in `ps_configuration`: Il modulo potrebbe memorizzare la sua impostazione principale `PS_PGROUP_ENABLED` (o simile) qui.
-   **Tabella degli hook registrati**:
    La funzionalità principale del modulo si basa su hook che si attivano quando lo stato di un ordine cambia.

    | Nome Hook | Tempo di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `actionOrderStatusPostUpdate` | Eseguito immediatamente dopo l'aggiornamento dello stato di un ordine. | Questo è l'hook più probabile utilizzato dal modulo per verificare se un ordine ha raggiunto lo stato configurato e quindi applicare le regole di assegnazione del gruppo in base ai prodotti in quell'ordine. |
    | `actionObjectOrderUpdateAfter` | Eseguito dopo l'aggiornamento di un oggetto Ordine. | Potrebbe essere utilizzato anche, in modo simile a `actionOrderStatusPostUpdate`, per reagire ai cambiamenti dell'ordine. |
    | `displayHeader` | Renderizza il contenuto nella sezione `<head>` delle pagine del front-office. | Non utilizzato direttamente per la funzionalità principale, ma potrebbe essere utilizzato per caricare JS/CSS globali se il modulo avesse componenti front-office (cosa che non sembra avere). |
    | `displayRightColumn` / `displayLeftColumn` | Renderizza il contenuto nelle colonne laterali delle pagine del front-office. | Non utilizzato direttamente per la funzionalità principale. |
    | `displayProductAdditionalInfo` / `displayProductButtons` | Renderizza il contenuto nella pagina del prodotto. | Non utilizzato direttamente per la funzionalità principale. |
    | `displayFooter` | Renderizza il contenuto nel piè di pagina delle pagine del front-office. | Non utilizzato direttamente per la funzionalità principale. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Assegna clienti a gruppi in base ai prodotti acquistati", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
