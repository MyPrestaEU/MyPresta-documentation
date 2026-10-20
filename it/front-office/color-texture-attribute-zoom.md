---
title: "Zoom attributo colore/texture - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Zoom attributo colore/texture di MyPresta.eu."
sidebar:
  label: "Zoom attributo colore/texture - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Color / texture attribute zoom su MyPresta.eu](https://mypresta.eu/modules/front-office-features/color-texture-attribute-zoom.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/color-texture-attribute-zoom/)
>
> ---


# Zoom attributo colore/texture

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Zoom attributo colore/texture", accessibile dopo l'installazione cliccando sul pulsante "Configura".

#### **Abilita / Disabilita Modulo**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo in tutto il tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* La funzione di zoom colore/texture sarà attiva sulle tue pagine prodotto e sui pop-up di visualizzazione rapida, in base alle altre impostazioni che hai scelto.
    -   *Quando disabilitato:* La funzione di zoom sarà completamente disattivata e non appariranno anteprime ingrandite.
-   **Valore consigliato:** **Abilitato** (per utilizzare le funzionalità del modulo).
-   **Scenario / esempio del commerciante:** Se desideri disabilitare temporaneamente la funzione di zoom per manutenzione o test, puoi disattivarla senza disinstallare il modulo.

#### **Mostra nome colore / texture (valore)**

-   **Cosa fa questa impostazione:** Determina se il nome testuale del colore o della texture (ad esempio, "Rosso", "Pelle") appare accanto alla finestra di anteprima ingrandita.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il nome dell'attributo verrà visualizzato accanto all'immagine ingrandita, fornendo un contesto aggiuntivo al cliente.
    -   *Quando disabilitato:* Apparirà solo l'immagine ingrandita, senza l'etichetta testuale.
-   **Valore consigliato:** **Abilitato**. Questo fornisce informazioni più chiare al cliente, soprattutto se i colori sono simili o le texture sono sottili.
-   **Scenario / esempio del commerciante:** Se hai molte sfumature di blu (ad esempio, "Blu Cielo", "Blu Navy"), mostrare il nome aiuta i clienti a distinguerle chiaramente.

#### **Disabilita cambio attributo al tocco**

-   **Cosa fa questa impostazione:** Controlla il comportamento del modulo sui dispositivi touch (come smartphone e tablet) quando un cliente tocca un campione di colore/texture.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Toccando un campione di colore/texture verrà mostrata solo l'anteprima dello zoom. L'immagine principale del prodotto sulla pagina NON cambierà per riflettere l'attributo toccato.
    -   *Quando disabilitato:* Toccando un campione di colore/texture verrà mostrata l'anteprima dello zoom E aggiornerà anche l'immagine principale del prodotto per mostrare il prodotto in quel colore/texture selezionato.
-   **Valore consigliato:** **Disabilitato**. La maggior parte dei clienti si aspetta che l'immagine principale del prodotto si aggiorni quando seleziona un colore/texture, anche su mobile. Abilita questa opzione solo se hai un motivo specifico per non cambiare l'immagine principale al tocco.
-   **Scenario / esempio del commerciante:** Se le tue immagini prodotto sono generiche e non cambiano in base agli attributi di colore, o se vuoi prevenire modifiche accidentali dell'immagine principale su mobile, potresti abilitare questa opzione. Altrimenti, mantienila disabilitata per il comportamento standard.

#### **Larghezza finestra anteprima colore**

-   **Cosa fa questa impostazione:** Imposta la larghezza (in pixel) della finestra pop-up che visualizza l'anteprima del colore ingrandita.
-   **Effetto della modifica di questa impostazione:**
    -   *Aumentando il valore:* Rende la finestra di anteprima più ampia, mostrando più dettagli.
    -   *Diminuendo il valore:* Rende la finestra di anteprima più stretta.
-   **Valore consigliato:** Un valore tra **200px e 300px** è solitamente un buon equilibrio. Inizia con `280` e regola in base alle tue immagini prodotto e al design del tema.
-   **Scenario / esempio del commerciante:** Se i tuoi campioni di colore sono molto piccoli e vuoi mostrare un ingrandimento significativo, aumenta questo valore. Se il layout della tua pagina prodotto è molto stretto, potresti doverlo ridurre.

#### **Altezza finestra anteprima colore**

-   **Cosa fa questa impostazione:** Imposta l'altezza (in pixel) della finestra pop-up che visualizza l'anteprima del colore ingrandita.
-   **Effetto della modifica di questa impostazione:**
    -   *Aumentando il valore:* Rende la finestra di anteprima più alta, mostrando più dettagli.
    -   *Diminuendo il valore:* Rende la finestra di anteprima più corta.
-   **Valore consigliato:** Un valore tra **200px e 300px** è solitamente un buon equilibrio. Inizia con `280` e regola in base alle tue immagini prodotto e al design del tema.
-   **Scenario / esempio del commerciante:** Similmente alla larghezza, regola questo valore per assicurarti che il colore ingrandito sia chiaramente visibile senza essere eccessivamente grande o piccolo per la tua pagina prodotto.

#### **Attiva zoom nella tabella delle combinazioni**

-   **Cosa fa questa impostazione:** Determina se la funzione di zoom deve essere applicata anche agli attributi di colore/texture visualizzati all'interno di una tabella di combinazioni di prodotti (se il tuo tema ne utilizza una).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* I clienti possono passare il mouse/toccare i campioni di colore/texture all'interno di una tabella di combinazioni per vedere l'anteprima ingrandita.
    -   *Quando disabilitato:* La funzione di zoom funzionerà solo per gli attributi di colore/texture al di fuori di qualsiasi tabella di combinazioni.
-   **Valore consigliato:** **Abilitato**. Questo fornisce un'esperienza coerente e utile in tutte le aree in cui vengono visualizzati gli attributi di colore/texture.
-   **Scenario / esempio del commerciante:** Se vendi magliette con una tabella che mostra taglie e colori disponibili, abilitando questa opzione i clienti possono ingrandire i colori direttamente da quella tabella.

#### **Larghezza finestra anteprima texture**

-   **Cosa fa questa impostazione:** Imposta la larghezza (in pixel) della finestra pop-up che visualizza l'anteprima della texture ingrandita. Questo è separato dalla larghezza dell'anteprima del colore, consentendoti di ottimizzare per diversi tipi di immagini attributo.
-   **Effetto della modifica di questa impostazione:**
    -   *Aumentando il valore:* Rende l'anteprima della texture più ampia.
    -   *Diminuendo il valore:* Rende l'anteprima della texture più stretta.
-   **Valore consigliato:** Similmente al colore, un valore tra **200px e 300px** è spesso adatto. Inizia con `280`.
-   **Scenario / esempio del commerciante:** Se le tue immagini di texture sono molto dettagliate e richiedono una visualizzazione più ampia per essere apprezzate, potresti impostare una larghezza maggiore qui rispetto ai semplici campioni di colore.

#### **Escludi alcuni gruppi di attributi colore dallo ZOOM**

-   **Cosa fa questa impostazione:** Ti consente di specificare determinati gruppi di attributi (ad esempio, "Taglia", "Materiale") per i quali la funzione di zoom NON deve essere applicata, anche se utilizzano immagini di colore o texture.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando vengono inseriti gli ID dei gruppi di attributi:* La funzione di zoom sarà disabilitata per tutti gli attributi appartenenti ai gruppi specificati.
    -   *Quando lasciato vuoto:* La funzione di zoom si applicherà a tutti i gruppi di attributi di colore/texture.
-   **Valore consigliato:** Lascia **vuoto** a meno che tu non abbia un motivo specifico per escludere gruppi. Se devi escludere, inserisci gli ID numerici dei gruppi di attributi, separati da virgole (ad esempio, `1, 5, 12`). Puoi trovare gli ID dei gruppi di attributi nel tuo Back Office di PrestaShop sotto **Catalogo > Attributi e Caratteristiche > Gruppi di Attributi**.
-   **Scenario / esempio del commerciante:** Potresti avere un gruppo di attributi "Disponibilità" che utilizza campioni di colore (ad esempio, verde per disponibile, rosso per esaurito), ma non vuoi che questi attivino uno zoom. In questo caso, troveresti l'ID del gruppo di attributi "Disponibilità" e lo inseriresti qui.

#### **Tipo di animazione**

-   **Cosa fa questa impostazione:** Seleziona l'effetto visivo utilizzato quando appare la finestra di anteprima dello zoom.
-   **Effetto della modifica di questa impostazione:** Cambia il modo in cui la finestra di anteprima si anima (ad esempio, dissolvenza, scorrimento).
-   **Valore consigliato:** **Dissolvenza**. Questa è generalmente l'animazione più sottile e professionale. Sperimenta con altre se preferisci un effetto diverso.
-   **Scenario / esempio del commerciante:** Puoi scegliere un'animazione che si adatti meglio all'estetica generale del tuo negozio.

#### **Aggiorna tipo di animazione**

-   **Cosa fa questa impostazione:** Seleziona l'effetto visivo utilizzato quando il contenuto della finestra di anteprima dello zoom cambia (ad esempio, quando si passa tra diversi colori/texture mentre l'anteprima è già aperta).
-   **Effetto della modifica di questa impostazione:** Cambia l'animazione per gli aggiornamenti del contenuto all'interno dell'anteprima.
-   **Valore consigliato:** **Dissolvenza**. Similmente all'animazione iniziale, una dissolvenza è solitamente fluida e non distraente.
-   **Scenario / esempio del commerciante:** Se un cliente passa rapidamente il mouse su più campioni di colore, questa animazione determina la fluidità della transizione del contenuto dell'anteprima.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita / Disabilita Modulo | Abilitato | Interruttore principale per la funzionalità del modulo. |
| Configurazione modulo | Mostra nome colore / texture (valore) | Abilitato | Visualizza il nome dell'attributo con l'anteprima dello zoom. |
| Configurazione modulo | Disabilita cambio attributo al tocco | Disabilitato | Impedisce il cambio dell'immagine principale al tocco su mobile (se abilitato). |
| Configurazione modulo | Larghezza finestra anteprima colore | 280 | Larghezza del pop-up di zoom colore in pixel. |
| Configurazione modulo | Altezza finestra anteprima colore | 280 | Altezza del pop-up di zoom colore in pixel. |
| Configurazione modulo | Attiva zoom nella tabella delle combinazioni | Abilitato | Estende lo zoom agli attributi all'interno delle tabelle di combinazione. |
| Configurazione modulo | Larghezza finestra anteprima texture | 280 | Larghezza del pop-up di zoom texture in pixel. |
| Configurazione modulo | Escludi alcuni gruppi di attributi colore dallo ZOOM | Vuoto | ID separati da virgole dei gruppi di attributi da ignorare per lo zoom. |
| Configurazione modulo | Tipo di animazione | Dissolvenza | Animazione per l'aspetto dell'anteprima dello zoom. |
| Configurazione modulo | Aggiorna tipo di animazione | Dissolvenza | Animazione per le modifiche del contenuto all'interno dell'anteprima dello zoom. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Lo zoom non appare sulla mia pagina prodotto. Cosa devo controllare?**
R:

1.  **Modulo abilitato:** Vai su **Moduli > Gestione moduli** e assicurati che "Zoom attributo colore/texture" sia abilitato.
2.  **Configurazione attributi:** Verifica che i tuoi attributi di prodotto siano correttamente impostati come tipo "Colore" o "Texture" in **Catalogo > Attributi e Caratteristiche > Attributi**. Assicurati di aver caricato immagini reali per questi attributi, non solo codici colore.
3.  **Cache:** Svuota la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni**, scorri fino a "Svuota cache" e clicca su "Svuota cache". Svuota anche la cache del tuo browser.
4.  **Compatibilità tema:** Sebbene il modulo sia progettato per un'ampia compatibilità, temi molto personalizzati potrebbero talvolta interferire. Se i passaggi precedenti non funzionano, passa temporaneamente al tema predefinito di PrestaShop per vedere se lo zoom appare. Se lo fa, il tuo tema potrebbe richiedere una piccola regolazione.

**D: La finestra di anteprima dello zoom è troppo piccola/grande.**
R: Regola le impostazioni "Larghezza finestra anteprima colore", "Altezza finestra anteprima colore" e "Larghezza finestra anteprima texture" nella pagina di configurazione del modulo. Aumenta i valori per rendere la finestra più grande, diminuiscili per renderla più piccola. Ricorda di salvare le modifiche e svuotare la cache.

**D: Il nome del colore/texture non viene visualizzato con lo zoom.**
R: Controlla l'impostazione "Mostra nome colore / texture (valore)" nella configurazione del modulo. Assicurati che sia impostata su "Abilitato".

**D: Su mobile, quando tocco un colore, l'immagine principale del prodotto non cambia, ma vorrei che cambiasse.**
R: Vai alla configurazione del modulo e assicurati che "Disabilita cambio attributo al tocco" sia impostato su "Disabilitato". Questo consentirà all'immagine principale del prodotto di aggiornarsi quando viene toccato un colore/texture.

**D: Voglio escludere un gruppo di attributi specifico dalla funzione di zoom.**
R: Naviga su **Catalogo > Attributi e Caratteristiche > Gruppi di Attributi** nel tuo Back Office di PrestaShop. Trova il gruppo di attributi che desideri escludere e annota il suo ID (solitamente visibile nell'URL quando lo modifichi, o nella tabella stessa). Quindi, vai alla configurazione del modulo, trova "Escludi alcuni gruppi di attributi colore dallo ZOOM" e inserisci gli ID separati da virgole (ad esempio, `1,5,12`).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Zoom attributo colore/texture" (`colorzoom`) è un modulo di funzionalità front-office progettato per migliorare la visualizzazione degli attributi del prodotto. Sfrutta principalmente il sistema di hook di PrestaShop per iniettare i suoi asset JavaScript e CSS nell'intestazione del front-office e per renderizzare il suo specifico template di zoom sulle pagine prodotto. Utilizza la libreria `tooltipster` per la funzionalità di zoom/tooltip effettiva, collegandola dinamicamente agli elementi degli attributi di colore e texture. La configurazione è gestita tramite il metodo standard `getContent()` nel file principale del modulo, memorizzando le impostazioni in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Il modulo include due controller front-office, sebbene la loro funzione primaria in questo modulo sia spesso minima o per specifiche esigenze AJAX, con gran parte della logica gestita lato client tramite JavaScript.

-   **Controller Front-Office**:

    -   `controllers/front/index.php`
        -   Nome classe: `ColorzoomIndexModuleFrontController` (estende `ModuleFrontController`)
        -   Responsabilità: Questo controller funge probabilmente da fallback o da punto di ingresso generico. Data la funzione primaria del modulo di miglioramento dell'interfaccia utente tramite JS/CSS, questo controller potrebbe non avere una logica estesa o potrebbe essere utilizzato per un semplice recupero di dati se necessario dal front-end.
    -   `controllers/front/loader.php`
        -   Nome classe: `ColorzoomLoaderModuleFrontController` (estende `ModuleFrontController`)
        -   Responsabilità: Questo controller potrebbe essere utilizzato per caricare risorse o dati specifici dinamicamente, potenzialmente per richieste AJAX relative alla funzionalità di zoom, sebbene la logica di zoom principale sia lato client.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce alcuna classe `ObjectModel` personalizzata o classi di logica di business dedicate nella directory `classes/`. La sua funzionalità principale è implementata all'interno del file `colorzoom.php` principale e tramite i suoi asset JavaScript.

### 4.4 Asset JavaScript (`views/js/`)

Il modulo si basa fortemente su JavaScript per la sua funzionalità di zoom interattivo, in particolare sulla libreria `tooltipster`.

-   `colorzoom/lib/tooltipster/dist/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
    -   Ambito: Front-office.
    -   Dettagli: Un plugin per la libreria `tooltipster`, specificamente per la gestione di elementi SVG all'interno dei tooltip. Questo potrebbe essere utilizzato se le immagini degli attributi sono basate su SVG o se il modulo deve interagire con elementi SVG sulla pagina.
-   `colorzoom/lib/tooltipster/dist/js/tooltipster.bundle.js`
    -   Ambito: Front-office.
    -   Dettagli: La versione completa in bundle della libreria `tooltipster`, che fornisce la funzionalità principale per la creazione di tooltip flessibili e personalizzabili. Questa è la libreria principale responsabile dei pop-up di zoom.
-   `colorzoom/lib/tooltipster/dist/js/tooltipster.core.js`
    -   Ambito: Front-office.
    -   Dettagli: Il file JavaScript principale per la libreria `tooltipster`. È possibile che `tooltipster.bundle.js` includa già questo, ma è elencato separatamente, indicando un'inclusione modulare.
-   `colorzoom/views/js/colorzoom-combinationstable.js`
    -   Ambito: Front-office.
    -   Dettagli: Questo script si rivolge specificamente alle tabelle di combinazioni di prodotti. Probabilmente contiene la logica per identificare gli attributi di colore/texture all'interno di queste tabelle e inizializzare la funzionalità di zoom `tooltipster` su di essi, rispettando l'impostazione di configurazione `cz_ctab`. Collega i listener di eventi agli elementi all'interno di queste tabelle.
-   `colorzoom/views/js/colorzoom.js`
    -   Ambito: Front-office.
    -   Dettagli: Questo è il JavaScript personalizzato principale per il modulo. È responsabile di:
        -   Identificare gli elementi degli attributi di colore/texture sulla pagina del prodotto (al di fuori delle tabelle di combinazioni).
        -   Inizializzare `tooltipster` su questi elementi con configurazioni specifiche del modulo (larghezza, altezza, tipo di animazione, visualizzazione del nome).
        -   Gestire la logica "Disabilita cambio attributo al tocco" per i dispositivi mobili.
        -   Potenzialmente ascoltare gli eventi `prestashop.on` come `updateProduct` per reinizializzare i tooltip se il contenuto del prodotto cambia tramite AJAX.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include CSS per lo stile delle anteprime dello zoom e della libreria `tooltipster`.

-   `colorzoom/lib/tooltipster/dist/css/tooltipster.bundle.css`
    -   Ambito: Stile del cliente front-office.
    -   Dettagli: Il CSS in bundle per la libreria `tooltipster`, che fornisce lo stile predefinito per i tooltip (le finestre di anteprima dello zoom).
-   `colorzoom/lib/tooltipster/dist/css/tooltipster.core.css`
    -   Ambito: Stile del cliente front-office.
    -   Dettagli: Il CSS principale per `tooltipster`, che definisce gli stili fondamentali.
-   `colorzoom/views/css/colorszoom.css`
    -   Ambito: Stile del cliente front-office.
    -   Dettagli: CSS personalizzato specifico per il modulo "Zoom attributo colore/texture". Questo file contiene probabilmente override o stili aggiuntivi per integrare i tooltip `tooltipster` senza soluzione di continuità nella pagina del prodotto di PrestaShop, garantendo un posizionamento corretto, dimensioni dei caratteri per i nomi degli attributi e reattività. Gli sviluppatori possono ispezionare questo file per i selettori chiave da sovrascrivere nel CSS personalizzato del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per iniettare il suo JavaScript e CSS e per renderizzare il contenuto dell'anteprima dello zoom.

-   **Template hook (`views/templates/hook/`)**:
    -   `colorzoom/views/header.tpl`
        -   Hook: `displayHeader`
        -   Scopo: Questo template è responsabile dell'inclusione dei file CSS e JavaScript del modulo nella sezione `<head>` delle pagine del front-office. Passa anche le variabili di configurazione dal back office (come `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_ctab`, `cz_exclusions`) al JavaScript del front-end, rendendole accessibili per l'inizializzazione dinamica.
-   **Template front-office (`views/templates/front/`)**:
    -   `colorzoom/views/quickview.tpl`
        -   Scopo: Questo template è probabilmente progettato per essere renderizzato all'interno di un pop-up di visualizzazione rapida del prodotto. Contiene il markup o la logica necessaria per garantire che la funzionalità di zoom sia correttamente inizializzata per gli attributi visualizzati nei modali di visualizzazione rapida.
    -   `colorzoom/views/zoom.tpl`
        -   Scopo: Questo è il template principale per il contenuto visualizzato all'interno dell'anteprima dello zoom (tooltip). Riceve dinamicamente l'URL dell'immagine dell'attributo e il nome dell'attributo, renderizzandoli all'interno della struttura del tooltip. È il componente visivo che la libreria `tooltipster` visualizzerà.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle SQL personalizzate. Tutte le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi prefissate con `cz_` (ad esempio, `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_exclusions`, `cz_ctab`) e `mypresta_updates`, `update_`, `updatev_` per la gestione degli aggiornamenti.
-   **Tabella degli hook registrati**:

    | Nome Hook | Tempo di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS e JavaScript del modulo e passa le variabili di configurazione al front-end. |
    | `displayProductAdditionalInfo` | All'interno del blocco informazioni prodotto nella pagina prodotto. | Questo hook viene utilizzato per renderizzare l'inizializzazione JavaScript necessaria o il markup specifico per la funzione di zoom sulla pagina prodotto, garantendo che sia attiva per gli attributi di colore/texture. |

## 5. Supporto ufficiale e aggiornamenti

Per supporto ufficiale, aggiornamenti del modulo e qualsiasi ulteriore assistenza, fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team è dedicato a fornire supporto tempestivo e a garantire che il tuo modulo funzioni in modo ottimale.
