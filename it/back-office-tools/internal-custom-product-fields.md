---
title: "Campi prodotto interni e personalizzati - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Campi prodotto interni e personalizzati' di MyPresta.eu."
sidebar:
  label: "Campi prodotto interni e personalizzati"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Internal, custom product fields su MyPresta.eu](https://mypresta.eu/modules/administration-tools/internal-custom-product-fields.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/internal-custom-product-fields/)
>
> ---


# Campi prodotto interni e personalizzati

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Campi prodotto interni e personalizzati)

Questa è la schermata di configurazione principale del modulo, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestione moduli.

-   **Cosa fa questa impostazione:** Questa schermata gestisce principalmente il meccanismo di aggiornamento interno del modulo e le impostazioni di base.
-   **Effetto della modifica di questa impostazione:**
    -   `mypresta_updates`: Questa impostazione interna controlla se il modulo verifica la presenza di aggiornamenti da MyPresta.eu.
    -   `update_`: Relativo al processo di verifica degli aggiornamenti.
    -   `updatev_`: Relativo al processo di verifica degli aggiornamenti.
    -   `PS_LANG_DEFAULT`: Questa è una chiave di configurazione standard di PrestaShop e viene solitamente letta dai moduli per determinare la lingua predefinita per la visualizzazione dei contenuti nel Back Office. Non è un'impostazione che si modifica tipicamente direttamente all'interno della configurazione di questo modulo.
-   **Valore consigliato:** Per `mypresta_updates`, è generalmente consigliato mantenerlo abilitato per ricevere notifiche su nuove versioni e correzioni di bug. Le altre impostazioni sono interne e non dovrebbero essere modificate manualmente.
-   **Scenario / esempio per il commerciante:** Di solito non si interagisce direttamente con queste impostazioni specifiche. Lo scopo principale di questa schermata è fornire una pagina di destinazione per il modulo e garantire che il suo meccanismo di aggiornamento sia attivo.

### 2.2 Schermata di amministrazione dedicata: Gestione campi interni (Back Office > Catalogo > Campi interni)

Questa è la schermata principale in cui definisci e gestisci i tuoi campi prodotto interni personalizzati. Dopo aver installato il modulo, una nuova voce di menu denominata "Campi interni" apparirà sotto il menu "Catalogo" nel tuo Back Office PrestaShop.

-   **Nome schermata e posizione menu:** **Catalogo > Campi interni**
-   **Azioni e impostazioni disponibili:**
    -   **Vista a griglia:** Questa schermata visualizza un elenco di tutti i campi interni personalizzati che hai creato. Ogni riga mostra il nome del campo e il suo stato (abilitato/disabilitato).
    -   **Pulsante "Aggiungi nuovo campo":** Clicca su questo pulsante per creare un nuovo campo personalizzato.
    -   **Azioni Modifica/Elimina:** Per ogni campo nell'elenco, vedrai i pulsanti di azione (icona a matita per modifica, icona a cestino per elimina) per modificare o rimuovere i campi esistenti.
    -   **Modulo di creazione/modifica campo:** Quando aggiungi o modifichi un campo, vedrai tipicamente:
        -   **Nome campo:** (es. "SKU fornitore", "Posizione magazzino", "Note di movimentazione speciale"). Questa è l'etichetta che apparirà accanto alla casella di input nella pagina di modifica del prodotto.
        -   **Interruttore Attivo/Inattivo:** Controlla se questo campo personalizzato è attualmente disponibile per l'uso nelle pagine dei prodotti. Se inattivo, non verrà visualizzato.
        -   **Tipo di campo:** (es. Testo, Area di testo, Numero, ecc. - *basato sulle effettive capacità del modulo, assumendo testo per ora*). Questo determina il tipo di casella di input.
        -   **Pulsante Salva:** Per salvare le modifiche o il nuovo campo.
-   **Effetto delle modifiche:**
    -   **Aggiunta di un nuovo campo:** Una volta salvato, questo nuovo campo apparirà immediatamente nella pagina di modifica di *ogni* prodotto nel tuo Back Office, pronto per l'inserimento dei dati.
    -   **Modifica di un campo:** Le modifiche al nome o allo stato del campo si rifletteranno istantaneamente su tutte le pagine di modifica del prodotto.
    -   **Eliminazione di un campo:** Il campo verrà rimosso da tutte le pagine di modifica del prodotto. **Fai attenzione:** L'eliminazione di un campo eliminerà anche tutti i dati precedentemente inseriti in quel campo per tutti i prodotti.
    -   **Attivazione/Disattivazione di un campo:** Un campo attivo è visibile nelle pagine dei prodotti; un campo inattivo è nascosto.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Vai su **Catalogo > Campi interni**.
    2.  Clicca su "Aggiungi nuovo campo" per creare un campo come "Codice articolo fornitore" o "Note interne".
    3.  Imposta il nome del campo e assicurati che sia attivo.
    4.  Salva il campo.
    5.  Ora, quando vai su **Catalogo > Prodotti** e modifichi un qualsiasi prodotto, vedrai una nuova casella di input per il tuo "Codice articolo fornitore" dove potrai inserire dati specifici per quel prodotto.
    6.  Ripeti per qualsiasi altro dato interno che devi tracciare.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | `mypresta_updates` | Abilitato | Controlla la verifica degli aggiornamenti del modulo. Mantienilo abilitato per gli aggiornamenti. |
| Pagina di configurazione del modulo | `update_`, `updatev_` | (Interno) | Variabili interne del meccanismo di aggiornamento. Non modificare. |
| Pagina di configurazione del modulo | `PS_LANG_DEFAULT` | (Interno) | ID lingua predefinita di PrestaShop. Sola lettura. |
| Catalogo > Campi interni | **Aggiungi nuovo campo** | N/A | Crea un nuovo campo prodotto interno personalizzato. |
| Catalogo > Campi interni | **Nome campo** | Definito dall'utente | Etichetta per il campo personalizzato nelle pagine di modifica del prodotto. |
| Catalogo > Campi interni | **Attivo/Inattivo** | Attivo | Controlla la visibilità del campo nelle pagine di modifica del prodotto. |
| Catalogo > Campi interni | **Azioni Modifica/Elimina** | N/A | Modifica o rimuovi i campi personalizzati esistenti. L'eliminazione rimuove tutti i dati associati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho creato un nuovo campo, ma non lo vedo nella pagina di modifica del mio prodotto.**
R:
1.  Vai su **Catalogo > Campi interni** e assicurati che il campo che hai creato sia contrassegnato come "Attivo".
2.  Svuota la cache di PrestaShop: Vai su **Parametri avanzati > Prestazioni**, quindi clicca su "Svuota la cache" nell'angolo in alto a destra.
3.  Prova a modificare nuovamente un prodotto. Se non appare ancora, assicurati che la tua versione di PrestaShop sia completamente compatibile con il modulo.

**D: Posso visualizzare questi campi personalizzati nel mio front-office per i clienti?**
R: No, questo modulo è progettato specificamente solo per l'uso interno del Back Office. I dati inseriti in questi campi non sono destinati a essere visualizzati ai clienti. Se hai bisogno di campi personalizzati per il front-office, avresti bisogno di un diverso tipo di modulo o di uno sviluppo personalizzato.

**D: Cosa succede se elimino un campo personalizzato?**
R: Quando elimini un campo personalizzato da **Catalogo > Campi interni**, tutti i dati che hai inserito in quel campo specifico per *tutti* i tuoi prodotti verranno rimossi in modo permanente. Assicurati sempre di non aver più bisogno dei dati prima di eliminare un campo.

**D: Il modulo sembra causare problemi con il mio tema personalizzato. Cosa devo fare?**
R:
1.  Innanzitutto, svuota la cache di Smarty (come menzionato sopra).
2.  Se il problema persiste, prova a disabilitare temporaneamente altri moduli uno per uno per vedere se c'è un conflitto.
3.  Controlla la console per sviluppatori del tuo browser (F12) per eventuali errori JavaScript.
4.  Se non riesci ancora a risolverlo, contatta il supporto MyPresta.eu con i dettagli del tuo tema e del problema specifico.

**D: Come posso tradurre i nomi dei miei campi personalizzati in diverse lingue?**
R: Il modulo dovrebbe consentirti di definire il nome del campo per ogni lingua abilitata nel tuo negozio PrestaShop quando crei o modifichi il campo. Cerca le schede della lingua accanto alla casella di input "Nome campo" nel modulo di creazione/modifica del campo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura
Il modulo "Campi prodotto interni e personalizzati" estende le capacità di gestione dei prodotti di PrestaShop iniettando campi personalizzati nella pagina di modifica del prodotto nel Back Office. Sfrutta il pattern MVC di PrestaShop, principalmente tramite un Controller Admin per la gestione delle definizioni dei campi personalizzati e gli override per integrare questi campi nei moduli prodotto esistenti. I dati vengono archiviati in una tabella di database dedicata e JavaScript viene utilizzato per la manipolazione dinamica dei moduli.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Questo modulo non ha controller front-office dedicati poiché la sua funzionalità è interamente orientata al Back Office. Gli hook front-office sono probabilmente utilizzati per la configurazione generale del modulo o per garantire l'assenza di conflitti front-office.

-   **Controller Admin Back-Office**:
    *   `aipf/controllers/admin/AdminInternalFields.php`
        *   **Nome classe**: `AdminInternalFieldsController` (estende `ModuleAdminController`)
        *   **Nome scheda**: "Campi interni" (sotto il menu Catalogo)
        *   **Responsabilità**: Questo è il controller principale per la gestione delle definizioni dei campi prodotto interni personalizzati. Gestisce l'elenco, la creazione, la modifica e l'eliminazione di questi campi. Utilizza `HelperList` di PrestaShop per la vista a griglia e `HelperForm` per i moduli di aggiunta/modifica. Interagisce con l'`ObjectModel` personalizzato del modulo (probabilmente `AipfInternalField`) per persistere le definizioni dei campi.
    *   `aipf/controllers/admin/index.php`
        *   **Responsabilità**: Questo è un file `index.php` vuoto standard spesso posizionato nelle directory per impedire l'elenco delle directory sui server web, migliorando la sicurezza. Non contiene alcuna logica funzionale del controller.

### 4.3 Classi e modelli core (`classes/`)

Il modulo utilizza gli override per integrare la sua funzionalità nel core di PrestaShop.

-   `aipf/override/classes/controller/Controller.php`
    *   **Nome classe**: `Controller` (sovrascrive la classe `Controller` core)
    *   **Responsabilità**: Questo override è probabilmente utilizzato per iniettare JavaScript o CSS specifici del modulo a livello globale o condizionalmente, o per modificare il comportamento di tutti i controller. Dato lo scopo del modulo, potrebbe essere utilizzato per garantire che le risorse necessarie siano caricate per la pagina del prodotto o per gestire richieste AJAX specifiche relative ai campi personalizzati.
-   `aipf/override/classes/controller/index.php`
    *   **Responsabilità**: Segnaposto di sicurezza.
-   `aipf/override/classes/index.php`
    *   **Responsabilità**: Segnaposto di sicurezza.

*Nota: In base alla descrizione, dovrebbe esserci una classe `ObjectModel` per `AipfInternalField` (es. `classes/AipfInternalField.php`) per gestire le definizioni dei campi personalizzati e potenzialmente un'altra per gestire i dati effettivi del prodotto per questi campi. Questo non è esplicitamente elencato nell'inventario ma è implicito dalla funzionalità.*

### 4.4 Risorse JavaScript (`views/js/`)

-   `aipf/lib/js/admin/aipf-configuration.js`
    *   **Ambito**: Back-office (configurazione del modulo).
    *   **Scopo**: Probabilmente gestisce la logica JavaScript specifica per la schermata di configurazione principale del modulo, come i controlli degli aggiornamenti o semplici interazioni con i moduli.
-   `aipf/lib/js/admin/aipf.js`
    *   **Ambito**: Back-office (amministrazione generale, potenzialmente pagina del prodotto).
    *   **Scopo**: Contiene la logica JavaScript principale per il modulo all'interno del Back Office. Ciò potrebbe includere chiamate AJAX per il salvataggio dei dati dei campi del prodotto, il rendering dinamico dei campi nella pagina del prodotto o le interazioni con `AdminInternalFieldsController`.
-   `aipf/lib/js/front/aipf-front.js`
    *   **Ambito**: Front-office.
    *   **Scopo**: Sebbene il modulo sia per uso interno, questo file potrebbe esistere come segnaposto o per gestire attività front-office molto specifiche e non visive, come garantire l'assenza di conflitti con altri script, o per una potenziale funzionalità futura che non è stata implementata. Data la descrizione del modulo, il suo impatto sul front-office dovrebbe essere minimo o nullo.
-   `aipf/views/js/AdminInternalFields.js`
    *   **Ambito**: Back-office (schermata AdminInternalFieldsController).
    *   **Scopo**: JavaScript specifico per la schermata di gestione "Catalogo > Campi interni". Questo gestirebbe le interazioni all'interno della griglia, la convalida del modulo per l'aggiunta/modifica dei campi e le richieste AJAX relative alla gestione dei campi.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `aipf/lib/css/aipf.css`
    *   **Ambito**: Principalmente Back-office, potenzialmente minimo front-office.
    *   **Scopo**: Fornisce lo stile per i campi personalizzati nella pagina di modifica del prodotto, nella schermata di gestione "Campi interni" e in qualsiasi altro elemento dell'interfaccia utente introdotto dal modulo nel Back Office. Potrebbe anche contenere stili di reset o regole molto basilari che potrebbero applicarsi al front-office per prevenire conflitti, sebbene il suo focus principale sia l'interfaccia utente amministrativa.
    *   **Selettori di classe CSS chiave**: Gli sviluppatori potrebbero cercare classi come `.aipf-field-container`, `.aipf-input`, `.aipf-label` per sovrascrivere o personalizzare l'aspetto dei campi personalizzati.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Non esplicitamente elencati, ma il modulo utilizzerebbe probabilmente template per hook come `displayAdminProductsExtra` o `displayAdminProductsMainStepLeftColumnMiddle` per iniettare i campi personalizzati nella pagina di modifica del prodotto.
-   **Template admin (`views/templates/admin/`)**:
    *   `aipf/views/templates/admin/combination.tpl`
        *   **Scopo**: Questo template è specificamente progettato per iniettare campi interni personalizzati nell'interfaccia di modifica delle combinazioni di prodotto (varianti) all'interno del Back Office. Renderizzerebbe i campi di input per i dati personalizzati associati a ogni combinazione di prodotto. Questo è cruciale per i prodotti con attributi (come taglia, colore) dove ogni combinazione potrebbe aver bisogno delle proprie note o identificatori interni.
-   **Template front-office (`views/templates/front/`)**: Nessuno esplicitamente elencato, in linea con la natura solo Back Office del modulo.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   `ps_aipf_internal_field`: Questa tabella memorizzerebbe le definizioni dei campi interni personalizzati (es. `id_aipf_internal_field`, `name`, `active`, `field_type`).
    *   `ps_aipf_internal_field_lang`: Se i nomi dei campi sono traducibili, questa tabella memorizzerebbe i nomi specifici della lingua per i campi personalizzati (es. `id_aipf_internal_field`, `id_lang`, `name`).
    *   `ps_aipf_product_data`: Questa tabella memorizzerebbe i dati effettivi inseriti dal commerciante per ogni campo personalizzato, collegati a un prodotto specifico e potenzialmente a una combinazione specifica (es. `id_aipf_internal_field`, `id_product`, `id_product_attribute` (se applicabile), `value`).
    *   `ps_configuration`: Tabella standard di PrestaShop utilizzata per memorizzare i valori di configurazione del modulo come `mypresta_updates`, `update_`, `updatev_`.

-   **Tabella degli hook registrati**:

| Nome Hook | Ambito | Tempo di esecuzione | Scopo tecnico |
|---|---|---|---|
| `actionAjaxDieProductControllerdisplayAjaxRefreshBefore` | Front/Admin | Prima della risposta AJAX in ProductController | Potenzialmente per la pre-elaborazione delle richieste AJAX relative ai dati del prodotto, garantendo che i campi personalizzati siano considerati. |
| `actionOutputHTMLBefore` | Front/Admin | Prima dell'output HTML | Hook generale, potrebbe essere utilizzato per l'iniezione globale di risorse o per l'elaborazione anticipata. |
| `ActionAfterUpdateCombinationFormFormHandler` | Admin | Dopo l'aggiornamento del modulo combinazione | Per salvare o elaborare i dati dei campi personalizzati relativi alle combinazioni di prodotto. |
| `actionAdminControllerSetMedia` | Admin | Quando il controller admin imposta i media | Per iniettare CSS/JS specifici del modulo nelle pagine del Back Office (es. pagina di modifica del prodotto, configurazione del modulo). |
| `actionCombinationFormFormBuilderModifier` | Admin | Quando il builder del modulo combinazione viene modificato | Per aggiungere dinamicamente campi personalizzati al modulo di combinazione del prodotto. |
| `actionProductUpdate` | Admin | Dopo l'aggiornamento di un prodotto | Per salvare o elaborare i dati dei campi personalizzati quando un prodotto viene salvato. |
| `ActionFrontControllerSetMedia` | Front | Quando il controller front imposta i media | Per iniettare CSS/JS specifici del modulo nelle pagine del Front Office (se necessario, anche se improbabile per questo modulo). |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Campi prodotto interni e personalizzati", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
