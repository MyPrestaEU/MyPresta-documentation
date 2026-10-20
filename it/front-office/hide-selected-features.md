---
title: "Nascondi funzionalità selezionate - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Nascondi funzionalità selezionate di MyPresta.eu."
sidebar:
  label: "Nascondi funzionalità selezionate - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Hide selected features su MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-selected-features.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/hide-selected-features/)
>
> ---


# Nascondi funzionalità selezionate

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Puoi accedere a questa pagina navigando su **Moduli > Gestione moduli** e cercando "Nascondi funzionalità selezionate", quindi cliccando su "Configura".

Questa schermata presenta un elenco di tutte le funzionalità del prodotto attualmente definite nel tuo negozio PrestaShop. Per ogni funzionalità, vedrai un interruttore per controllarne la visibilità.

-   **Cosa fa questa impostazione:** Questa sezione elenca tutte le tue funzionalità di prodotto esistenti (ad esempio, "Materiale", "Colore", "Peso", "Dimensioni"). Accanto a ogni funzionalità, c'è un interruttore che controlla se quella specifica funzionalità verrà visualizzata sulle pagine dei tuoi prodotti nel front office.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (interruttore su ON):* La funzionalità sarà visibile ai clienti su tutte le pagine dei prodotti a cui è assegnata. Questo è il comportamento predefinito di PrestaShop.
    -   *Quando disabilitato (interruttore su OFF):* La funzionalità sarà nascosta ai clienti su tutte le pagine dei prodotti, anche se è assegnata a un prodotto. Esisterà comunque nel tuo back office per uso interno o per il filtraggio.
-   **Valore consigliato:** Questo dipende interamente dalle tue esigenze aziendali.
    -   **Abilita** le funzionalità che sono cruciali per il processo decisionale del cliente (ad esempio, "Materiale" per l'abbigliamento, "Capacità" per l'elettronica).
    -   **Disabilita** le funzionalità che sono note interne, specifiche tecniche irrilevanti per il cliente medio o informazioni ridondanti.
-   **Scenario / esempio del commerciante:**
    -   **Scenario 1 (Nascondere note interne):** Utilizzi una funzionalità chiamata "SKU Fornitore" per tenere traccia dei codici prodotto interni. Questa informazione non è utile per i clienti. **Disabiliteresti** la funzionalità "SKU Fornitore" qui per mantenere pulite le pagine dei tuoi prodotti.
    -   **Scenario 2 (Semplificare la visualizzazione):** Vendi magliette e hai funzionalità come "Materiale: Cotone", "Lunghezza manica: Corta", "Scollatura: Girocollo". Decidi che "Lunghezza manica" e "Scollatura" sono solitamente chiare dall'immagine del prodotto e vuoi enfatizzare "Materiale". **Disabiliteresti** "Lunghezza manica" e "Scollatura" e **abiliteresti** "Materiale".

**Altre chiavi di configurazione (Interne/Avanzate):**
Potresti vedere altre chiavi di configurazione come `mypresta_updates`, `update_`, `updatev_`, `hidefeatures_OSTATE`, `PS_OS_PREPARATION`, `hidefeatures_MIN_CHARGE`. Queste sono tipicamente impostazioni interne del modulo relative ad aggiornamenti, stati degli ordini o costi minimi, e non sono direttamente configurabili dal commerciante tramite l'interfaccia principale. Sono solitamente gestite automaticamente dal modulo o utilizzate per scenari specifici e avanzati non esposti nell'interfaccia utente primaria. Per questo modulo, la funzionalità principale è gestita dagli interruttori delle funzionalità.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 AdminFeaturesController (Back Office > Catalogo > Attributi e Funzionalità > Funzionalità)

Questo modulo sovrascrive la schermata di gestione standard delle "Funzionalità" di PrestaShop.

-   **Nome schermata e posizione menu:** **Back Office > Catalogo > Attributi e Funzionalità > Funzionalità**.
-   **Azioni e impostazioni disponibili:** Quando vai a questa schermata, vedrai un elenco di tutte le funzionalità del tuo prodotto. Il modulo aggiunge una nuova colonna o un indicatore a questo elenco, tipicamente etichettato **"Attivo nel front office"** o simile. Questa colonna ti mostrerà a colpo d'occhio se una funzionalità è attualmente impostata per essere visibile o nascosta nel front-end del tuo negozio, in base alle impostazioni che hai fatto nella pagina di configurazione principale del modulo.
-   **Effetto delle modifiche:** Sebbene tu non possa modificare direttamente la visibilità da questa schermata (lo fai nella pagina di configurazione del modulo), questa schermata fornisce una comoda panoramica. Ti aiuta a verificare rapidamente lo stato front-office di ogni funzionalità senza dover tornare al modulo.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Usa questa schermata come riferimento rapido quando gestisci le funzionalità del tuo prodotto. Se aggiungi una nuova funzionalità, ricordati di visitare la pagina di configurazione del modulo "Nascondi funzionalità selezionate" per decidere se deve essere visibile ai clienti.

#### 2.2.2 index.php (hidefeatures/override/controllers/admin/index.php)

Questo file fa parte della struttura di override e tipicamente serve come segnaposto o punto di ingresso per la logica del controller sovrascritto. Non rappresenta una schermata di configurazione distinta e rivolta all'utente, ma piuttosto facilita la modifica delle pagine di amministrazione esistenti di PrestaShop da parte del modulo.

-   **Tabella / Entità gestita:** Questo file non gestisce direttamente una tabella o un'entità specifica, ma piuttosto assicura il corretto caricamento ed esecuzione dell'`AdminFeaturesController` sovrascritto.
-   **Campi modulo e colonne:** Nessun campo modulo o colonna diretto è gestito da questo file specifico. Il suo scopo è architetturale, garantendo che le modifiche del modulo alla griglia/vista di gestione delle "Funzionalità" siano applicate.
-   **Effetto delle modifiche:** Questo file assicura che la colonna "Attivo nel front office" (o indicatore simile) sia visualizzata correttamente nell'elenco **Catalogo > Attributi e Funzionalità > Funzionalità**, fornendo la vista di gestione migliorata.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Elenco di tutte le funzionalità con interruttori ON/OFF | Varia per funzionalità (ON per le nuove funzionalità) | Controlla se una specifica funzionalità del prodotto viene visualizzata sulle pagine dei prodotti nel front office. ON = Visibile, OFF = Nascosto. |
| **AdminFeaturesController** (Catalogo > Attributi e Funzionalità > Funzionalità) | Colonna/indicatore "Attivo nel front office" | Riflette la configurazione del modulo | Fornisce una rapida panoramica dello stato di visibilità front-office di una funzionalità direttamente nell'elenco delle funzionalità. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho nascosto una funzionalità, ma è ancora visibile sulla pagina del mio prodotto. Cosa c'è che non va?**
R:

1.  **Svuota la cache:** La ragione più comune è che la cache di PrestaShop (e possibilmente la cache del tuo browser) non si è aggiornata. Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Inoltre, prova a svuotare la cache del tuo browser o a visualizzare la pagina in una finestra in incognito/privata.
2.  **Configurazione del modulo salvata?** Ricontrolla di aver cliccato su "Salva" dopo aver apportato modifiche nella pagina di configurazione del modulo.
3.  **Funzionalità corretta?** Assicurati di aver disabilitato la funzionalità esatta che intendi nascondere. I nomi delle funzionalità a volte possono essere simili.

**D: Posso nascondere le funzionalità solo per prodotti specifici, non globalmente?**
R: No, questo modulo nasconde le funzionalità globalmente su tutti i prodotti. Se hai bisogno di visibilità delle funzionalità specifica per prodotto, di solito la gestisci non assegnando la funzionalità al prodotto in primo luogo, o utilizzando una soluzione personalizzata più avanzata. Questo modulo fornisce un interruttore a livello di negozio per i tipi di funzionalità.

**D: Nascondere una funzionalità influirà sui miei filtri prodotto o sui risultati di ricerca?**
R: No, questo modulo influisce solo sulla *visualizzazione* delle funzionalità sulla pagina del prodotto nel front office. I dati della funzionalità stessa rimangono nel tuo database. Se utilizzi le funzionalità per la navigazione a livelli (filtri) o la ricerca, dovrebbero continuare a funzionare come previsto, purché la funzionalità sia assegnata al prodotto.

**D: La colonna "Attivo nel front office" non viene visualizzata nell'elenco delle mie funzionalità (Catalogo > Attributi e Funzionalità > Funzionalità).**
R:

1.  **Modulo installato e abilitato?** Assicurati che il modulo "Nascondi funzionalità selezionate" sia correttamente installato e abilitato in **Moduli > Gestione moduli**.
2.  **Cache:** Svuota la cache di PrestaShop come descritto sopra.
3.  **Compatibilità del tema:** In rari casi, un tema altamente personalizzato potrebbe interferire con gli override. Se svuotare la cache non aiuta, contatta il supporto MyPresta.eu.

**D: Come traduco il testo del modulo (se presente)?**
R: Sebbene questo modulo utilizzi principalmente i nomi delle funzionalità esistenti di PrestaShop, se ci sono testi o etichette specifici del modulo, puoi tradurli andando su **Internazionale > Traduzioni** nel tuo Back Office. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, seleziona la tua lingua e quindi trova il modulo "Nascondi funzionalità selezionate" per modificarne le traduzioni.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Nascondi funzionalità selezionate" opera sovrascrivendo le classi e i controller principali di PrestaShop per iniettare la sua logica di visibilità. Estende le classi `Feature` e `Product` per aggiungere una nuova proprietà per la visibilità nel front-office e modifica l'`AdminFeaturesController` per visualizzare questo stato nel back-office. Il modulo utilizza un hook personalizzato (`displayHiddenFeatures`) per renderizzare l'elenco effettivo delle funzionalità sulla pagina del prodotto, consentendogli di filtrare le funzionalità nascoste prima della visualizzazione.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Questo modulo non introduce alcun controller front-office personalizzato. Tutta la logica front-office è gestita tramite override delle classi e degli hook principali.
-   **Controller Admin Back-Office**:

    -   `hidefeatures/override/controllers/admin/AdminFeaturesController.php`
        -   **Nome classe e classe genitore**: `AdminFeaturesController` (sovrascrive il core `AdminFeaturesController`)
        -   **Responsabilità**: Questo override modifica l'`AdminFeaturesController` per visualizzare lo stato di visibilità front-office di ogni funzionalità nell'elenco delle funzionalità. Probabilmente aggiunge una nuova colonna alla tabella dell'elenco, consentendo agli amministratori di vedere rapidamente quali funzionalità sono nascoste/visibili senza dover accedere alla configurazione del modulo. Sfrutta l'override della classe `Feature` per recuperare questo stato.
    -   `hidefeatures/override/controllers/admin/index.php`
        -   **Nome classe e classe genitore**: Non è un file di classe, tipicamente un `index.php` vuoto per prevenire l'elenco delle directory.
        -   **Responsabilità**: Pratica standard per le directory `override` per prevenire l'accesso diretto e garantire la sicurezza. Non contiene codice funzionale.

### 4.3 Classi e Modelli Core (`classes/`)

-   `hidefeatures/override/classes/Feature.php`

    -   **Con quale tabella del database interagisce**: `ps_feature` (tabella principale delle funzionalità) e `ps_configuration` (per le impostazioni del modulo).
    -   **Estende `ObjectModel`**: Sì, estende la classe core `Feature` che a sua volta estende `ObjectModel`.
    -   **Campi `$definition`**: Questo override probabilmente aggiunge un nuovo campo all'array `$definition` della classe `Feature`, o più comunemente, aggiunge una proprietà dinamica all'oggetto `Feature` per memorizzare il suo stato di visibilità front-office, che viene poi recuperato da `ps_configuration` o da una tabella personalizzata. Contenerebbe anche metodi per recuperare e impostare questo stato di visibilità.
    -   **Metodi pubblici chiave e logica di business incapsulata**:
        -   Metodi per recuperare lo stato di visibilità di una specifica funzionalità.
        -   Metodi per aggiornare lo stato di visibilità, probabilmente interagendo con `Configuration::updateValue()`.
        -   Potenzialmente modifica `getFeatures()` o metodi simili per filtrare i risultati in base alla visibilità.
-   `hidefeatures/override/classes/index.php`

    -   **Nome classe e classe genitore**: Non è un file di classe, tipicamente un `index.php` vuoto per prevenire l'elenco delle directory.
    -   **Responsabilità**: Pratica standard per le directory `override` per prevenire l'accesso diretto e garantire la sicurezza. Non contiene codice funzionale.
-   `hidefeatures/override/classes/Product.php`

    -   **Con quale tabella del database interagisce**: `ps_product` e `ps_feature_product`.
    -   **Estende `ObjectModel`**: Sì, estende la classe core `Product` che a sua volta estende `ObjectModel`.
    -   **Campi `$definition`**: Nessuna modifica diretta a `$definition` è prevista qui.
    -   **Metodi pubblici chiave e logica di business incapsulata**: Questo override è cruciale per filtrare le funzionalità sulla pagina del prodotto. Probabilmente modifica metodi come `getFeatures()` o `getFrontFeatures()` (se esistono nella classe core `Product`) per:
        1.  Recuperare tutte le funzionalità assegnate a un prodotto.
        2.  Iterare attraverso queste funzionalità.
        3.  Per ogni funzionalità, controllare il suo stato di visibilità utilizzando la logica della classe `Feature` sovrascritta.
        4.  Restituire solo le funzionalità contrassegnate come visibili.
            Questo assicura che quando le funzionalità di un prodotto vengono recuperate per la visualizzazione, quelle nascoste vengano automaticamente escluse.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non sembra contenere alcun file JavaScript personalizzato. La sua funzionalità è principalmente lato server tramite override PHP e logica del template Smarty.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non sembra contenere alcun file CSS personalizzato. Qualsiasi stile per la colonna aggiunta in AdminFeaturesController verrebbe tipicamente gestito dal CSS predefinito del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Hook (`views/templates/hook/`)**:

    -   `hidefeatures/views/templates/front/hook/displayHiddenFeatures.tpl`
        -   **Hook**: `displayHiddenFeatures` (hook personalizzato, probabilmente chiamato all'interno della classe `Product` sovrascritta o del `product.tpl` di un tema)
        -   **Output**: Questo template è responsabile del rendering dell'elenco delle funzionalità del prodotto sulla pagina del prodotto nel front office. Riceve l'elenco filtrato delle funzionalità (dopo che quelle nascoste sono state rimosse dall'override della classe `Product`) e le visualizza nel formato standard della tabella/elenco delle funzionalità di PrestaShop. Gli sviluppatori possono ispezionare questo template per capire come le funzionalità vengono iterate e visualizzate.
-   **Template Admin (`views/templates/admin/`)**:

    -   `hidefeatures/views/templates/admin/_configure/helpers/list/list_content.tpl`
        -   **Scopo**: Questo template è un override per il template standard del contenuto dell'elenco di PrestaShop, utilizzato specificamente all'interno dell'`AdminFeaturesController`. È responsabile del rendering delle righe della tabella dell'elenco delle funzionalità nel back office.
        -   **Contenuto**: Conterrà la logica per visualizzare la colonna "Attivo nel front office" (o simile) per ogni funzionalità, mostrando un indicatore visivo (ad esempio, un segno di spunta, una X rossa o un interruttore) in base allo stato di visibilità della funzionalità. Questo template funziona in congiunzione con l'override dell'`AdminFeaturesController` per presentare le informazioni aggiuntive.
-   **Template Front-office (`views/templates/front/`)**:

    -   Nessun template di pagina front-office autonomo dedicato.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea nuove tabelle di database personalizzate.
    -   Memorizza la sua configurazione (quali funzionalità sono nascoste/visibili) nella tabella `ps_configuration`. Le chiavi di configurazione seguirebbero tipicamente un modello come `HIDEFEATURES_FEATURE_ID_X` o simile, dove `X` è l'`id_feature`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHiddenFeatures` | Hook personalizzato, probabilmente chiamato all'interno di `product.tpl` o tramite l'override di `Product::getFrontFeatures()`. | Renderizza l'elenco filtrato delle funzionalità del prodotto sulla pagina del prodotto nel front-office, assicurando che vengano mostrate solo le funzionalità visibili. |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto. | (Implicito, se il modulo deve rivalutare la visibilità delle funzionalità al salvataggio del prodotto, sebbene non esplicitamente elencato come hook primario per la funzione principale di questo modulo). |
| `actionFeatureSave` / `actionFeatureDelete` | Dopo il salvataggio o l'eliminazione di una funzionalità. | (Implicito, se il modulo deve aggiornare la sua configurazione interna quando le funzionalità vengono aggiunte/rimosse). |
| `displayBackOfficeHeader` | Renderizza il contenuto nella sezione `<head>` del Back Office. | (Possibile, per iniettare JS/CSS se necessario per l'interfaccia utente amministrativa, ma non presente nell'inventario). |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi domanda relativa al modulo "Nascondi funzionalità selezionate", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere.
