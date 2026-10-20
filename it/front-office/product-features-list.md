---
title: "Elenco delle caratteristiche del prodotto - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Elenco delle caratteristiche del prodotto di MyPresta.eu."
sidebar:
  label: "Elenco delle caratteristiche del prodotto - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product features list su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-features-list.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-features-list/)
>
> ---


# Elenco delle caratteristiche del prodotto

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Elenco delle caratteristiche del prodotto)

Questa è la schermata di configurazione principale del modulo, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestore moduli.

- **Cosa fa questa impostazione:** Questa impostazione controlla dove l'elenco delle caratteristiche del prodotto apparirà visivamente nelle pagine di elenco dei prodotti (pagine di categoria, risultati di ricerca, ecc.).
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "displayProductListReviews":* Le caratteristiche appariranno vicino alla sezione delle recensioni del prodotto nell'elenco dei prodotti. Questo è spesso un buon punto per raggruppare la prova sociale con gli attributi chiave del prodotto.
  - *Quando impostato su "displayProductDeliveryTime":* Le caratteristiche appariranno vicino a qualsiasi informazione sul tempo di consegna visualizzata. Questo può essere utile per i prodotti in cui le caratteristiche sono strettamente legate alla logistica o alla disponibilità.
  - *Quando impostato su "displayHeader":* Questa opzione è meno comune per la visualizzazione visiva negli elenchi di prodotti e potrebbe posizionare le caratteristiche nell'intestazione della pagina, che generalmente non è dove si desidera che appaiano le caratteristiche specifiche del prodotto. È principalmente un hook tecnico.
- **Valore consigliato:** "displayProductListReviews" o "displayProductDeliveryTime". Scegli quello che si integra meglio con il layout del tuo tema e dove ritieni che le caratteristiche saranno più visibili senza ingombrare.
- **Scenario/esempio del commerciante:** Se il tuo tema mostra valutazioni a stelle e conteggi di recensioni in modo prominente, "displayProductListReviews" posizionerebbe le caratteristiche proprio accanto ad esse, creando un ricco blocco di informazioni. Se i tuoi prodotti hanno spesso dettagli di consegna specifici (ad esempio, "Spedito in 24h"), posizionare le caratteristiche con "displayProductDeliveryTime" potrebbe avere senso.

### 2.2 Schermata di amministrazione dedicata: Associazione delle caratteristiche (Back Office > Moduli > Elenco delle caratteristiche del prodotto > Configura > "Gestisci associazioni di caratteristiche" o link simile)

Questa schermata è cruciale per definire *quali* caratteristiche appaiono per *quali* prodotti e categorie. È qui che associ caratteristiche specifiche del prodotto alle categorie.

- **Nome schermata e posizione nel menu:** Dopo aver configurato il modulo principale, di solito troverai un link o un pulsante nella pagina di configurazione del modulo (o una nuova voce di menu sotto "Catalogo") che porta a "Gestisci associazioni di caratteristiche" o "Elenco delle caratteristiche del prodotto". Il percorso esatto potrebbe variare leggermente a seconda della tua versione di PrestaShop, ma sarà collegato dalla configurazione principale del modulo.
- **Azioni e impostazioni disponibili:**
  - **Vista griglia/gestione:** Vedrai una tabella che elenca le tue caratteristiche del prodotto esistenti (queste sono le caratteristiche standard che definisci in **Catalogo > Attributi e caratteristiche > Caratteristiche**).
  - **Pulsante Modifica/Associa:** Per ogni caratteristica, ci sarà un pulsante "Modifica" o "Associa". Cliccando su questo si aprirà un modulo in cui puoi:
    - **Selezionare categorie:** Scegli una o più categorie per le quali questa specifica caratteristica dovrebbe essere visualizzata negli elenchi dei prodotti. Ad esempio, se hai una caratteristica "Materiale", potresti associarla alle categorie "T-shirt", "Vestiti" e "Giacche".
    - **Abilita/Disabilita:** Potresti avere un'opzione per abilitare o disabilitare la visualizzazione di questa caratteristica negli elenchi dei prodotti a livello globale o per categoria.
- **Effetto delle modifiche:**
  - *Quando associ una caratteristica a una categoria:* I prodotti all'interno di quella categoria che possiedono questa caratteristica la visualizzeranno nella loro voce dell'elenco dei prodotti.
  - *Quando rimuovi un'associazione:* La caratteristica non apparirà più per i prodotti in quella categoria negli elenchi dei prodotti.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Innanzitutto, assicurati che tutte le tue caratteristiche del prodotto siano configurate correttamente in **Catalogo > Attributi e caratteristiche > Caratteristiche**.
  2. Vai alla schermata "Gestisci associazioni di caratteristiche" del modulo "Elenco delle caratteristiche del prodotto".
  3. Esamina ogni caratteristica pertinente.
  4. Per ogni caratteristica, seleziona le categorie in cui desideri che questa caratteristica sia visibile nelle pagine di elenco dei prodotti.
  5. Salva le modifiche.
  6. Rivedi periodicamente queste associazioni, specialmente quando aggiungi nuovi prodotti, categorie o caratteristiche, per assicurarti che i tuoi elenchi di prodotti rimangano informativi.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Posizione dei tag (`fplist_position`) | `displayProductListReviews` | Determina dove le caratteristiche appaiono nelle pagine di elenco dei prodotti (ad esempio, vicino alle recensioni, vicino al tempo di consegna). |
| Associazione caratteristiche | Nome caratteristica (es. "Materiale") | N/A | Caratteristica standard di PrestaShop da gestire. |
| Associazione caratteristiche | Categorie associate | N/A | Seleziona le categorie in cui questa caratteristica dovrebbe essere visibile negli elenchi dei prodotti. |
| Associazione caratteristiche | Abilita/Disabilita caratteristica | Abilitato | Controlla se una caratteristica è attivamente visualizzata per le sue categorie associate. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma le caratteristiche non vengono visualizzate nelle mie pagine di categoria.**
R:

1. **Controlla le associazioni delle caratteristiche:** Vai alla schermata "Gestisci associazioni delle caratteristiche" e assicurati che le caratteristiche che ti aspetti di vedere siano effettivamente associate alle categorie che stai visualizzando.
2. **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" se disponibile).
3. **Posizione del modulo:** Ricontrolla l'impostazione "Posizione dei tag" nella configurazione principale del modulo. Assicurati che sia impostata su un hook che il tuo tema effettivamente renderizza nel contesto dell'elenco dei prodotti (ad esempio, `displayProductListReviews` o `displayProductDeliveryTime`). Alcuni temi personalizzati potrebbero non richiamare esplicitamente tutti gli hook standard.
4. **Dati del prodotto:** Verifica che i prodotti in questione abbiano effettivamente valori per le caratteristiche che stai cercando di visualizzare (ad esempio, se vuoi mostrare "Materiale", assicurati che al prodotto sia assegnato un materiale).

**D: Le caratteristiche vengono visualizzate, ma sembrano disordinate o non si adattano al design del mio tema.**
R:

1. **Conflitto CSS:** Questo è probabilmente un conflitto di stile con il tuo tema. Il modulo include il proprio CSS (`fplist/views/css/fplist.css`), ma gli stili del tuo tema potrebbero sovrascriverlo o causare problemi di layout.
2. **Tema personalizzato:** Se stai utilizzando un tema altamente personalizzato, potresti aver bisogno di un webmaster o di uno sviluppatore per regolare il CSS del modulo o il CSS del tuo tema per garantire una corretta integrazione.
3. **Posizionamento:** Prova a cambiare l'impostazione "Posizione dei tag" per vedere se un hook diverso si integra meglio visivamente con il tuo tema.

**D: Posso visualizzare caratteristiche diverse per categorie diverse?**
R: Sì, assolutamente! Questa è una delle principali forze del modulo. Utilizza la schermata "Gestisci associazioni delle caratteristiche" per selezionare categorie specifiche per ogni caratteristica. Questo ti consente di adattare le informazioni visualizzate con precisione al contesto dell'elenco dei prodotti.

**D: Questo modulo influisce sulle mie pagine prodotto?**
R: No, questo modulo si rivolge specificamente alle pagine di *elenco* dei prodotti (categoria, risultati di ricerca, ecc.). Non altera il modo in cui le caratteristiche vengono visualizzate nelle singole pagine di dettaglio del prodotto.

**D: Il mio negozio è multilingue. I nomi delle caratteristiche sono tradotti?**
R: Sì, le caratteristiche standard di PrestaShop (che questo modulo utilizza) sono completamente traducibili. Assicurati di aver fornito le traduzioni per i nomi e i valori delle tue caratteristiche in **Catalogo > Attributi e caratteristiche > Caratteristiche** per tutte le lingue attive nel tuo negozio. Il modulo visualizzerà quindi la traduzione corretta nel front office.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Elenco delle caratteristiche del prodotto" (`fplist`) segue un'architettura standard dei moduli PrestaShop, estendendo principalmente `Module` per la sua funzionalità principale e `AdminController` per la sua interfaccia di gestione del Back Office. Sfrutta il sistema di hook di PrestaShop per iniettare contenuto nelle pagine di elenco dei prodotti e utilizza un `ObjectModel` (implicitamente tramite `AdminFplistAssociationController`) per gestire l'associazione tra caratteristiche e categorie. La visualizzazione del front-office del modulo è gestita da un template Smarty renderizzato tramite un hook.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Questo modulo non contiene controller front-office dedicati. Tutta la logica di visualizzazione del front-office è gestita direttamente all'interno del file principale del modulo (`fplist.php`) tramite hook registrati.
- **Controller Admin Back-Office**:

  - `fplist/controllers/admin/AdminFplistAssociation.php`
    - **Nome classe:** `AdminFplistAssociationController` (estende `ModuleAdminController`)
    - **Responsabilità:** Questo controller gestisce l'associazione tra le caratteristiche di PrestaShop e le categorie. Fornisce l'interfaccia del Back Office (un elenco e potenzialmente un modulo di modifica) per gli amministratori per selezionare quali caratteristiche devono essere visualizzate negli elenchi dei prodotti per categorie specifiche. Interagisce con l'archiviazione interna dei dati del modulo (probabilmente la tabella `ps_fplist_association`, sebbene nessun `ObjectModel` esplicito sia fornito nel dossier, il controller implica la sua esistenza e gestione).
  - `fplist/controllers/admin/index.php`
    - **Nome classe:** N/A (questo è tipicamente un file vuoto o un reindirizzamento per impedire l'accesso diretto alla directory, non un controller funzionale).
    - **Responsabilità:** Misura di sicurezza standard di PrestaShop per prevenire l'elenco delle directory.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. L'`AdminFplistAssociationController` implica l'esistenza di un modello di dati per le associazioni caratteristica-categoria, che è probabilmente gestito direttamente all'interno del controller o del file principale del modulo utilizzando query `Db::getInstance()`, piuttosto che un `ObjectModel` dedicato. Se fosse presente un `ObjectModel`, sarebbe tipicamente chiamato `FplistAssociation` o simile.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo non indica file JavaScript personalizzati. Qualsiasi comportamento dinamico o interazione AJAX dovrebbe essere implementato direttamente all'interno dei file PHP o template del modulo, o basarsi sul JS core di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

- `fplist/views/css/fplist.css`
  - **Ambito:** Stile del front-office per il cliente.
  - **Componenti UI principali e contenitori che stilizza:** Questo foglio di stile è responsabile della presentazione visiva dell'elenco delle caratteristiche del prodotto nelle pagine di categoria e di elenco. Definisce gli stili per il contenitore che ospita le caratteristiche, i singoli elementi delle caratteristiche e potenzialmente icone o etichette ad essi associate.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori dovrebbero ispezionare l'HTML renderizzato per identificare classi specifiche (ad esempio, `.fplist-container`, `.fplist-item`, `.fplist-feature-name`, `.fplist-feature-value`) da sovrascrivere nel `custom.css` o `theme.css` del loro tema per un'integrazione perfetta.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**:
  - `fplist/views/templates/fplist-front.tpl`
    - **Hook:** Questo template viene renderizzato all'interno degli hook `displayProductListReviews` e `displayProductDeliveryTime` (come configurato da `fplist_position`).
    - **Output:** Genera la struttura HTML per l'elenco delle caratteristiche di un singolo prodotto in una pagina di elenco prodotti. Itera attraverso le caratteristiche recuperate dal modulo per il prodotto e la categoria corrente, visualizzando i loro nomi e valori.
  - `fplist/views/templates/fplist.tpl`
    - **Hook:** Questo template è probabilmente utilizzato per la pagina di configurazione principale del modulo nel Back Office (tramite `getContent()`).
    - **Output:** Renderizza il modulo per l'impostazione "Posizione dei tag" e potenzialmente i link a `AdminFplistAssociationController` per la gestione delle associazioni delle caratteristiche.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - `ps_fplist_association` (implicita): Questa tabella non è esplicitamente definita nel dossier ma è necessaria per l'`AdminFplistAssociationController` per memorizzare la relazione molti-a-molti tra le caratteristiche di PrestaShop e le categorie. Tipicamente conterrebbe colonne come `id_feature`, `id_category` e potenzialmente `id_shop`.
  - Record di configurazione in `ps_configuration`:
    - `mypresta_updates`: Memorizza le informazioni di aggiornamento per i moduli MyPresta.eu.
    - `update_`: Relativo ai controlli di aggiornamento del modulo.
    - `updatev_`: Relativo ai controlli di aggiornamento del modulo.
    - `fplist_position`: Memorizza il nome dell'hook selezionato per la visualizzazione delle caratteristiche (ad esempio, `displayProductListReviews`).
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Configurazione standard di PrestaShop per la lingua del modulo dipendente.
- **Tabella degli hook registrati**:

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato principalmente per caricare risorse CSS/JS o meta tag. Il modulo lo usa come posizione configurabile per le caratteristiche, sebbene meno comune per la visualizzazione visiva. |
| `displayProductListReviews` | All'interno dell'elemento dell'elenco prodotti, tipicamente vicino alle recensioni del prodotto. | Inietta l'HTML dell'elenco delle caratteristiche in ogni voce del prodotto nelle pagine di categoria/ricerca. |
| `displayProductDeliveryTime` | All'interno dell'elemento dell'elenco prodotti, tipicamente vicino alle informazioni sul tempo di consegna. | Inietta l'HTML dell'elenco delle caratteristiche in ogni voce del prodotto nelle pagine di categoria/ricerca. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | (Non esplicitamente utilizzato da questo modulo, ma un hook comune per le azioni relative agli ordini). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto professionale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda riguardante il modulo "Elenco delle caratteristiche del prodotto".
