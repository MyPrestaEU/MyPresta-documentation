---
title: "Blocco immagini produttori (marchi) - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Blocco immagini produttori (marchi) di MyPresta.eu."
sidebar:
  label: "Blocco immagini produttori (marchi) - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Manufacturers (brands) images block su MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturers-brands-images-block.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/manufacturers-brands-images-block/)
>
> ---


# Blocco immagini produttori (marchi)

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali per il modulo "Blocco immagini produttori (marchi)". Qui puoi personalizzare l'aspetto e il comportamento del blocco marchi nel tuo negozio.

#### **Posizione del blocco produttori**

-   **Cosa fa questa impostazione:** Questa impostazione cruciale determina dove apparirà il blocco di immagini dei marchi sul tuo sito web. Puoi scegliere tra varie posizioni predefinite (hook) all'interno del tuo tema PrestaShop.
-   **Effetto della modifica di questa impostazione:**
    *   *Se impostato su `displayRightColumn` (o `displayLeftColumn`):* Il blocco marchi apparirà nella barra laterale destra (o sinistra) del tuo negozio, tipicamente insieme ad altri blocchi come categorie o bestseller. Questo è ottimo per una visibilità costante.
    *   *Se impostato su `displayFooter`:* Il blocco apparirà nella parte inferiore del tuo sito web, spesso utilizzato per la navigazione supplementare.
    *   *Se impostato su `displayTop` (o `displayTopColumn`):* Il blocco sarà visibile vicino alla parte superiore della tua pagina, spesso nell'area dell'intestazione, rendendo i marchi immediatamente evidenti.
    *   *Se impostato su `displayHome`:* Il blocco apparirà solo sulla homepage del tuo negozio, rendendolo una caratteristica centrale per la scoperta dei marchi.
-   **Valore consigliato:** `displayHome` per una caratteristica prominente della homepage, o `displayRightColumn` (o `displayLeftColumn`) per una visibilità costante su pagine di prodotti e categorie.
-   **Scenario / esempio del commerciante:** Se vuoi che i clienti possano facilmente sfogliare i marchi mentre fanno acquisti di prodotti, scegli `displayRightColumn`. Se vuoi fare una forte dichiarazione di marchio sulla tua homepage, scegli `displayHome`.

#### **Abilita carosello**

-   **Cosa fa questa impostazione:** Questa impostazione trasforma la griglia statica di loghi di marchi in un carosello animato e scorrevole.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* I loghi dei marchi scorreranno orizzontalmente, permettendoti di visualizzare molti marchi in uno spazio compatto. Questo è visivamente dinamico e risparmia spazio sullo schermo.
    *   *Se disabilitato (NO):* I loghi dei marchi verranno visualizzati come una griglia statica, mostrando tutti i loghi disponibili contemporaneamente (o quanti ne rientrano nelle dimensioni del blocco). Questo offre una panoramica immediata senza interazione.
-   **Valore consigliato:** `SÌ` se hai molti marchi o desideri un aspetto più moderno e dinamico. `NO` se hai solo pochi marchi e preferisci una visualizzazione statica.
-   **Scenario / esempio del commerciante:** Se hai più di 50 marchi, abilitare il carosello è essenziale per evitare un blocco molto lungo e disordinato. Se hai solo 5-10 marchi, una visualizzazione statica potrebbe essere sufficiente.

#### **Attiva filtro categorie**

-   **Cosa fa questa impostazione:** Questo permette al modulo di visualizzare solo i produttori associati ai prodotti all'interno della *categoria attualmente visualizzata*.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Su una pagina di categoria (ad esempio, "Magliette"), il blocco marchi mostrerà solo i loghi dei produttori che producono magliette. Questo rende il blocco altamente pertinente al contesto di navigazione attuale del cliente.
    *   *Se disabilitato (NO):* Il blocco marchi mostrerà sempre *tutti* i produttori attivi nel tuo negozio, indipendentemente dalla pagina o categoria corrente.
-   **Valore consigliato:** `SÌ` per una migliore esperienza utente e pertinenza, specialmente nei negozi con diverse categorie di prodotti.
-   **Scenario / esempio del commerciante:** Un cliente che naviga in "Smartphone" vedrà solo marchi come Apple, Samsung e Xiaomi se questa opzione è abilitata, invece di vedere anche marchi di abbigliamento. Questo li aiuta a restringere la ricerca.

#### **Abilita scorrimento automatico per il carosello**

-   **Cosa fa questa impostazione:** Se il carosello è abilitato, questa impostazione controlla se i loghi dei marchi scorrono automaticamente senza interazione del cliente.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Il carosello scorrerà automaticamente i loghi dei marchi a una velocità impostata, creando un effetto visivo dinamico.
    *   *Se disabilitato (NO):* Il carosello scorrerà solo quando il cliente clicca manualmente sulle frecce di navigazione o trascina il carosello.
-   **Valore consigliato:** `SÌ` per una visualizzazione più coinvolgente e dinamica, ma assicurati che la velocità non sia troppo elevata.
-   **Scenario / esempio del commerciante:** Vuoi assicurarti che tutti i tuoi marchi ottengano visibilità anche se i clienti non interagiscono con il carosello. L'abilitazione dello scorrimento automatico lo consente.

#### **Velocità di scorrimento automatico**

-   **Cosa fa questa impostazione:** Questa impostazione definisce la velocità con cui il carosello scorre automaticamente da un set di marchi all'altro, misurata in millisecondi. (Applicabile solo se "Abilita scorrimento automatico per carosello" è SÌ).
-   **Effetto della modifica di questa impostazione:**
    *   *Valore più alto (ad esempio, 5000ms = 5 secondi):* Velocità di scorrimento più lenta, dando ai clienti più tempo per visualizzare ogni set di loghi.
    *   *Valore più basso (ad esempio, 2000ms = 2 secondi):* Velocità di scorrimento più veloce, rendendo il carosello più dinamico ma potenzialmente più difficile da leggere.
-   **Valore consigliato:** 3000-5000 millisecondi (3-5 secondi) per un'esperienza di visualizzazione confortevole.
-   **Scenario / esempio del commerciante:** Se hai molti marchi e vuoi che i clienti li vedano tutti senza sentirsi di fretta, imposta una velocità più lenta come 4000ms.

#### **Metti in pausa il carosello al passaggio del mouse**

-   **Cosa fa questa impostazione:** Se lo scorrimento automatico è abilitato, questa impostazione controlla se il carosello si ferma temporaneamente quando un cliente sposta il cursore del mouse sul blocco dei marchi.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Il carosello si metterà in pausa, consentendo al cliente di esaminare comodamente un logo del marchio o cliccarci sopra senza che il carosello si sposti. Questo migliora l'esperienza utente.
    *   *Se disabilitato (NO):* Il carosello continuerà a scorrere automaticamente anche se il mouse è sopra di esso, il che può essere frustrante per i clienti che cercano di interagire.
-   **Valore consigliato:** `SÌ` per una migliore esperienza utente.
-   **Scenario / esempio del commerciante:** Un cliente vede un marchio che gli piace e sposta il mouse per cliccarci sopra. Se il carosello si ferma, può cliccare facilmente. Se non si ferma, il marchio potrebbe scorrere via prima che possa reagire.

#### **Dimensione dell'immagine del marchio**

-   **Cosa fa questa impostazione:** Questa impostazione consente di definire la larghezza massima delle immagini dei marchi visualizzate nel blocco. L'altezza si adatterà proporzionalmente.
-   **Effetto della modifica di questa impostazione:**
    *   *Valore più grande (ad esempio, 150px):* I loghi dei marchi appariranno più grandi, rendendoli più prominenti e facili da vedere. Questo potrebbe occupare più spazio nel blocco.
    *   *Valore più piccolo (ad esempio, 80px):* I loghi dei marchi appariranno più piccoli, consentendo a più loghi di adattarsi in uno spazio dato ma potenzialmente rendendoli meno evidenti.
-   **Valore consigliato:** 100-120 pixel per un buon equilibrio tra visibilità ed efficienza dello spazio. Regola in base al layout del tuo tema.
-   **Scenario / esempio del commerciante:** Se la tua barra laterale è stretta, potresti dover impostare una dimensione dell'immagine più piccola (ad esempio, 80px) per evitare che i loghi trabocchino. Su un blocco homepage ampio, potresti usare 150px per un maggiore impatto.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Posizione del blocco produttori | `displayHome` o `displayRightColumn` | Determina dove appare il blocco marchi (es. homepage, barra laterale, piè di pagina). |
| Configurazione modulo | Abilita carosello | `SÌ` | Trasforma la griglia statica in un carosello scorrevole per una visualizzazione dinamica. |
| Configurazione modulo | Attiva filtro categorie | `SÌ` | Mostra solo i marchi pertinenti alla categoria attualmente visualizzata. |
| Configurazione modulo | Abilita scorrimento automatico per carosello | `SÌ` | Fa scorrere automaticamente il carosello tra i marchi. |
| Configurazione modulo | Velocità di scorrimento automatico | 3000-5000ms | Controlla la velocità di scorrimento del carosello (in millisecondi). |
| Configurazione modulo | Metti in pausa il carosello al passaggio del mouse | `SÌ` | Ferma lo scorrimento automatico quando un cliente passa il mouse sul blocco. |
| Configurazione modulo | Dimensione dell'immagine del marchio | 100-120px | Imposta la larghezza massima per i loghi dei marchi nel blocco. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio blocco marchi non viene visualizzato dopo l'installazione, o si trova nel posto sbagliato.**

-   **R:** Innanzitutto, controlla la pagina di configurazione del modulo nel tuo Back Office. Assicurati che l'impostazione "Posizione del blocco produttori" sia stata scelta correttamente. Se è impostata su `displayHome`, apparirà solo sulla homepage. Se è impostata su una colonna, assicurati che il tuo tema visualizzi effettivamente quella colonna sulle pagine che stai visualizzando.
-   **R:** Svuota la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni**, quindi clicca su "Svuota la cache" in alto a destra. A volte, le modifiche al tema o le nuove installazioni di moduli richiedono un aggiornamento della cache.
-   **R:** Controlla le "Posizioni" del tuo tema (Design > Posizioni in PS 1.7/8). Assicurati che il modulo sia agganciato alla posizione desiderata. Se non è elencato, prova a salvare nuovamente la configurazione del modulo.

**D2: Le mie immagini dei marchi appaiono distorte o non hanno la dimensione giusta.**

-   **R:** Vai alla configurazione del modulo e regola l'impostazione "Dimensione dell'immagine del marchio". Questo controlla la larghezza massima.
-   **R:** Assicurati che le immagini originali del produttore caricate su PrestaShop (Catalogo > Produttori) siano di buona qualità e idealmente abbiano un rapporto di aspetto coerente. Anche se il modulo le ridimensiona, le immagini sorgente fortemente distorte appariranno comunque male.
-   **R:** Dopo aver modificato le dimensioni delle immagini, è spesso una buona idea rigenerare le miniature. Vai su **Design > Impostazioni immagini** (o **Preferenze > Immagini** nelle versioni precedenti di PS) e clicca su "Rigenera miniature". Seleziona "produttori" come tipo di immagine.

**D3: Il carosello non scorre, o lo scorrimento automatico non funziona.**

-   **R:** Controlla se "Abilita carosello" è impostato su `SÌ`. In caso contrario, sarà un blocco statico.
-   **R:** Se il carosello è abilitato, controlla se "Abilita scorrimento automatico per carosello" è anch'esso impostato su `SÌ`. Se questo è `NO`, il carosello si muoverà solo manualmente.
-   **R:** Se entrambi sono abilitati, controlla la console per sviluppatori del tuo browser (F12) per eventuali errori JavaScript. Conflitti con altri moduli o script del tema possono talvolta impedire il funzionamento dei caroselli. Prova a disabilitare temporaneamente altri moduli per isolare il problema.

**D4: Il "Filtro categorie" non funziona; vedo ancora tutti i marchi sulle pagine delle categorie.**

-   **R:** Assicurati che questa impostazione sia impostata su `SÌ` nella configurazione del modulo.
-   **R:** Verifica che i tuoi prodotti siano correttamente associati sia a una categoria che a un produttore nel tuo catalogo PrestaShop. Se un prodotto non è collegato a un produttore, o il produttore non è collegato a nessun prodotto in quella categoria, non apparirà quando filtrato.
-   **R:** Svuota la cache di PrestaShop dopo aver apportato modifiche alle associazioni prodotto/produttore.

**D5: Come posso tradurre il titolo o il testo del modulo?**

-   **R:** Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
-   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e seleziona la lingua che desideri tradurre.
-   Trova il modulo "Blocco immagini produttori (marchi)" nell'elenco e potrai modificare qualsiasi stringa traducibile che fornisce (ad esempio, il titolo del blocco).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Blocco immagini produttori (marchi)" (`mib`) è un modulo PrestaShop standard che segue un modello simile a MVC. Sfrutta principalmente il sistema di hook di PrestaShop per iniettare il suo contenuto in varie posizioni del front-office. La logica principale risiede nel file `mib.php`, che gestisce l'installazione, la disinstallazione, la configurazione e il rendering del contenuto per gli hook. Utilizza una libreria JavaScript di terze parti (`lightslider.js`) per la funzionalità del carosello e CSS personalizzati per lo stile. Le impostazioni di configurazione sono memorizzate in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller personalizzati per il Front-Office o il Back-Office Admin. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo, e il rendering del front-office viene eseguito direttamente tramite i metodi degli hook.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate o entità `ObjectModel`. Interagisce direttamente con gli oggetti core `Manufacturer` e `Category` di PrestaShop e `Configuration` per le impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`mib/lib/js/lightslider.js`**
    *   **Ambito:** Front-office.
    *   **Descrizione:** Questo è un plugin jQuery di terze parti responsabile della creazione del carosello di contenuti reattivo. Gestisce l'animazione di scorrimento, i controlli di navigazione e il comportamento reattivo per i loghi dei marchi quando l'opzione carosello è abilitata.
    *   **Funzionalità chiave:** Inizializza `lightSlider` su un elemento HTML specificato, gestisce le transizioni delle slide, i gesti touch/swipe e le regolazioni reattive.
-   **`mib/views/js/mib.js`**
    *   **Ambito:** Front-office.
    *   **Descrizione:** Questo è il file JavaScript personalizzato del modulo. Contiene la logica di inizializzazione per il plugin `lightslider.js` basata sulle impostazioni di configurazione del modulo.
    *   **Funzionalità chiave:**
        *   Verifica se il carosello è abilitato (configurazione `MIB_CAROUSEL`).
        *   Inizializza `lightSlider` sull'elemento `#lightSlider` all'interno del template del modulo.
        *   Passa le opzioni di configurazione a `lightSlider` come `auto`, `pause`, `pauseOnHover`, `item`, `slideMove`, `speed`, `loop`, `controls`, `responsive` basate sulle impostazioni `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED` e `MIB_IMG`.
        *   Assicura che lo slider sia inizializzato solo se l'elemento esiste.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`mib/lib/css/lightslider.css`**
    *   **Ambito:** Stile del cliente del front-office.
    *   **Descrizione:** Questo è il foglio di stile principale per il plugin `lightslider.js`. Fornisce lo stile necessario per la struttura del carosello, le frecce di navigazione e i punti di paginazione.
    *   **Selettori CSS chiave:** `.lightSlider`, `.lSAction`, `.lSPager`, `.lslide`, ecc. Gli sviluppatori possono sovrascrivere questi per personalizzare l'aspetto del carosello.
-   **`mib/mib.css`**
    *   **Ambito:** Stile del cliente del front-office.
    *   **Descrizione:** Questo è il foglio di stile personalizzato del modulo. Fornisce uno stile specifico per il contenitore del blocco marchi, le singole immagini dei marchi e qualsiasi effetto hover.
    *   **Selettori CSS chiave:**
        *   `#manufacturers_block_top`, `#manufacturers_block_left`, `#manufacturers_block_right`, `#manufacturers_block_home`, `#manufacturers_block_footer`: ID dei contenitori principali per diverse posizioni degli hook.
        *   `.mib_manufacturer_item`: Stili per i singoli link/contenitori dei produttori.
        *   `.mib_manufacturer_item img`: Stili per le immagini dei marchi, inclusi gli aggiustamenti di `max-width` e `height`.
        *   `.mib_manufacturer_item:hover img`: Definisce l'animazione al passaggio del mouse (ad esempio, `transform: scale(1.1)` per un effetto zoom).

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    *   **`mib/views/templates/hook/mib.tpl`**
        *   **Agganciato a:** `displayRightColumn`, `displayFooter`, `displayTop`, `displayLeftColumn`, `displayHome`, `displayTopColumn`.
        *   **Scopo:** Questo è il template principale del front-office responsabile del rendering del blocco marchi. Genera dinamicamente la struttura HTML per una griglia statica di loghi dei produttori o per il carosello `lightSlider`, in base alla configurazione del modulo.
        *   **Elementi chiave:**
            *   Rendering condizionale per il carosello (`{if $mib_carousel}`).
            *   Ciclo sull'array `$manufacturers` per visualizzare l'immagine e il link di ogni marchio.
            *   Include `mib.js` e `lightslider.js` se il carosello è abilitato.
            *   Include `mib.css` e `lightslider.css`.
            *   Utilizza `{$link->getManufacturerLink($manufacturer.id_manufacturer, $manufacturer.link_rewrite)}` per gli URL dei produttori.
            *   Utilizza `{$manufacturer.image}` per i percorsi delle immagini dei marchi.
-   **Template di amministrazione (`views/templates/admin/`)**:
    *   **`mib/views/templates/admin/admin.tpl`**
        *   **Scopo:** Questo template renderizza il modulo di configurazione del modulo nel Back Office di PrestaShop. Visualizza tutte le impostazioni (posizione, opzioni del carosello, dimensione dell'immagine, ecc.) come campi di input, caselle di selezione e interruttori.
        *   **Elementi chiave:**
            *   Struttura standard del modulo helper di PrestaShop (`{include file="{$smarty.const._PS_ROOT_DIR_}/src/PrestaShopBundle/Resources/views/Admin/Configure/AdvancedParameters/Blocks/form_block_content.html.twig"}`).
            *   Campi di input per `MIB_WHERE`, `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`.
            *   Utilizza `{$mib_form_action}` per l'invio del modulo.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Questo modulo non crea tabelle di database personalizzate.
    *   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`, `MIB_WHERE`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica e posizione di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayRightColumn` | Renderizza nella barra laterale destra del front-office. | Visualizza il blocco marchi nella colonna destra. |
| `displayFooter` | Renderizza nella sezione del piè di pagina del front-office. | Visualizza il blocco marchi nel piè di pagina del negozio. |
| `displayTop` | Renderizza nella sezione superiore del front-office (spesso l'intestazione). | Visualizza il blocco marchi nell'area dell'intestazione. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin imposta le sue risorse multimediali. | Utilizzato per includere i file CSS e JS del modulo nel Back Office per la configurazione. |
| `displayLeftColumn` | Renderizza nella barra laterale sinistra del front-office. | Visualizza il blocco marchi nella colonna sinistra. |
| `displayHome` | Renderizza sulla homepage del front-office. | Visualizza il blocco marchi in modo prominente sulla homepage. |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere i file CSS e JS necessari per la visualizzazione del front-office. |
| `displayTopColumn` | Renderizza nella sezione della colonna superiore del front-office (sotto `displayTop`). | Visualizza il blocco marchi nell'area della colonna superiore. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Blocco immagini produttori (marchi)", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
