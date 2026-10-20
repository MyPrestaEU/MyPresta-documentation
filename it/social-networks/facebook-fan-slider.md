---
title: "Facebook Fan Slider - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Facebook Fan Slider di MyPresta.eu."
sidebar:
  label: "Facebook Fan Slider - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Fan Slider su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-fan-slider/)
>
> ---


# Facebook Fan Slider

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono richieste per PrestaShop stesso e generalmente disponibili su tutti gli ambienti di hosting moderni. Non sono necessarie configurazioni speciali del server oltre a una configurazione standard di PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alle impostazioni del modulo, vai su **Moduli > Gestione moduli**, cerca "Facebook Fan Slider" e clicca sul pulsante "Configura".

Ecco una ripartizione dettagliata di ogni impostazione:

-   **URL della pagina Facebook (fs\_url)**

    *   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Indica al modulo quale Pagina Facebook specifica visualizzare nella casella scorrevole.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato sull'URL della tua Pagina Facebook:* Il modulo recupererà e visualizzerà il Like Box/Page Plugin per quella pagina esatta.
        *   *Quando lasciato vuoto o impostato in modo errato:* Il modulo non visualizzerà il contenuto di Facebook, oppure mostrerà un errore, poiché non saprà a quale pagina connettersi.
    *   **Valore consigliato:** Inserisci l'URL completo della tua Pagina Facebook (ad esempio, `https://www.facebook.com/MyPresta.eu`).
    *   **Scenario / esempio del commerciante:** Se la tua pagina aziendale è `https://www.facebook.com/MyAwesomeShop`, dovresti inserire quell'URL qui.
-   **Larghezza (fs\_width)**

    *   **Cosa fa questa impostazione:** Controlla la larghezza del Like Box/Page Plugin di Facebook *all'interno* del pannello scorrevole, in pixel.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un valore in pixel specifico (ad esempio, 280):* Il contenuto di Facebook avrà esattamente quella larghezza.
        *   *Quando impostato su un valore più piccolo:* Il contenuto potrebbe apparire compresso o alcuni elementi potrebbero essere tagliati.
        *   *Quando impostato su un valore più grande:* Il contenuto si espanderà, ma assicurati che non superi la larghezza dello schermo o appaia sproporzionato.
    *   **Valore consigliato:** Inizia con `280` o `300` pixel. Regola in base a quanto contenuto visualizzi (ad esempio, se mostri post, potresti aver bisogno di più larghezza).
    *   **Scenario / esempio del commerciante:** Vuoi che la casella scorrevole sia abbastanza larga da mostrare chiaramente la foto di copertina della tua pagina e il pulsante "Mi piace" senza essere troppo ingombrante.
-   **Altezza (fs\_height)**

    *   **Cosa fa questa impostazione:** Controlla l'altezza del Like Box/Page Plugin di Facebook *all'interno* del pannello scorrevole, in pixel.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un valore in pixel specifico (ad esempio, 400):* Il contenuto di Facebook avrà esattamente quell'altezza.
        *   *Quando impostato su un valore più piccolo:* Il contenuto potrebbe essere tagliato, richiedendo agli utenti di scorrere all'interno della casella.
        *   *Quando impostato su un valore più grande:* La casella sarà più alta, potenzialmente occupando più spazio sullo schermo.
    *   **Valore consigliato:** Inizia con `400` o `500` pixel. Se abiliti "Mostra post", probabilmente avrai bisogno di più altezza (ad esempio, `600-700px`) per visualizzare alcuni post senza uno scorrimento eccessivo.
    *   **Scenario / esempio del commerciante:** Vuoi mostrare alcuni post recenti dalla tua pagina Facebook, quindi aumenti l'altezza a `600px` per renderli visibili.
-   **Nascondi foto di copertina (fs\_hide\_cover)**

    *   **Cosa fa questa impostazione:** Determina se la grande foto di copertina della tua Pagina Facebook viene visualizzata nella parte superiore del Like Box/Page Plugin.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (selezionato):* La foto di copertina non verrà mostrata, rendendo il Like Box più compatto.
        *   *Quando disabilitato (deselezionato):* La foto di copertina verrà visualizzata, rendendo il Like Box visivamente più ricco ma anche più alto.
    *   **Valore consigliato:** *Disabilitato* (deselezionato) se desideri una casella più accattivante visivamente. *Abilitato* (selezionato) se hai bisogno di risparmiare spazio verticale.
    *   **Scenario / esempio del commerciante:** Hai una bellissima foto di copertina su Facebook e vuoi mostrarla, quindi la lasci deselezionata. Se hai poco spazio, potresti selezionarla.
-   **Mostra volti degli amici (fs\_show\_facepile)**

    *   **Cosa fa questa impostazione:** Controlla se le immagini del profilo degli amici che già hanno messo "Mi piace" alla tua pagina vengono visualizzate sotto il pulsante "Mi piace".
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (selezionato):* Apparirà una riga di immagini del profilo di amici in comune che hanno messo "Mi piace" alla tua pagina, aggiungendo prova sociale.
        *   *Quando disabilitato (deselezionato):* Queste immagini del profilo non verranno mostrate.
    *   **Valore consigliato:** *Abilitato* (selezionato). La prova sociale può incoraggiare altri a mettere "Mi piace" alla tua pagina.
    *   **Scenario / esempio del commerciante:** Vuoi sfruttare la prova sociale per incoraggiare nuovi "Mi piace", quindi abiliti questa opzione per mostrare gli amici che già hanno messo "Mi piace" alla tua pagina.
-   **Mostra post (fs\_show\_posts)**

    *   **Cosa fa questa impostazione:** Determina se i post recenti dalla timeline della tua Pagina Facebook vengono visualizzati all'interno del Like Box/Page Plugin.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (selezionato):* I tuoi ultimi post di Facebook appariranno, rendendo la casella più dinamica e coinvolgente. Probabilmente dovrai aumentare l'impostazione `Altezza`.
        *   *Quando disabilitato (deselezionato):* Verrà mostrata solo la funzionalità di base "Mi piace alla pagina" e i volti degli amici (se abilitato).
    *   **Valore consigliato:** *Abilitato* (selezionato) se pubblichi regolarmente contenuti coinvolgenti e vuoi mostrarli. Ricorda di regolare `Altezza`.
    *   **Scenario / esempio del commerciante:** Pubblichi frequentemente nuovi prodotti e promozioni su Facebook. Abilitando questa opzione, i clienti possono vedere i tuoi ultimi aggiornamenti direttamente dal tuo negozio.
-   **Nascondi Call To Action (fs\_hide\_cta)**

    *   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Call To Action" (ad esempio, "Invia messaggio", "Acquista ora") che potresti aver configurato sulla tua Pagina Facebook.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (selezionato):* Il pulsante CTA non verrà visualizzato nel Like Box.
        *   *Quando disabilitato (deselezionato):* Il pulsante CTA (se se configurato sulla tua Pagina Facebook) sarà visibile.
    *   **Valore consigliato:** *Disabilitato* (deselezionato) se la tua CTA è rilevante per i visitatori del tuo negozio. *Abilitato* (selezionato) se preferisci concentrarti solo sull'ottenere "Mi piace".
    *   **Scenario / esempio del commerciante:** La tua pagina Facebook ha un pulsante "Acquista ora". Vuoi che i clienti lo usino, quindi lasci questa opzione deselezionata.
-   **Intestazione piccola (fs\_small\_header)**

    *   **Cosa fa questa impostazione:** Utilizza una versione più piccola dell'intestazione per il Like Box/Page Plugin di Facebook.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (selezionato):* L'area dell'intestazione del Like Box sarà più compatta, risparmiando spazio verticale.
        *   *Quando disabilitato (deselezionato):* Verrà utilizzata l'intestazione standard, più grande.
    *   **Valore consigliato:** *Abilitato* (selezionato) se desideri un aspetto più snello o hai bisogno di risparmiare spazio.
    *   **Scenario / esempio del commerciante:** Vuoi che la casella scorrevole sia il più compatta possibile senza nascondere informazioni essenziali, quindi abiliti l'intestazione piccola.
-   **Scorri su (fanslider\_slideon)**

    *   **Cosa fa questa impostazione:** Determina il metodo di interazione che fa scorrere fuori la casella di Facebook.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su "Click":* La casella scorrerà fuori solo quando il cliente clicca esplicitamente sulla scheda.
        *   *Quando impostato su "Hover":* La casella scorrerà fuori quando il cliente sposta il cursore del mouse sulla scheda.
    *   **Valore consigliato:** "Click" è generalmente meno intrusivo e previene aperture accidentali. "Hover" può essere più immediato ma potrebbe infastidire alcuni utenti.
    *   **Scenario / esempio del commerciante:** Vuoi assicurarti che lo slider appaia solo quando un cliente sceglie attivamente di vederlo, quindi lo imposti su "Click".
-   **Posizione (fs\_pos)**

    *   **Cosa fa questa impostazione:** Controlla dove appare la scheda scorrevole sul tuo sito web.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su "Sinistra":* La scheda apparirà sul lato sinistro della finestra del browser.
        *   *Quando impostato su "Destra":* La scheda apparirà sul lato destro della finestra del browser.
    *   **Valore consigliato:** "Sinistra" o "Destra", a seconda del layout del tuo tema e di dove causa meno interferenze con altri elementi.
    *   **Scenario / esempio del commerciante:** Il tuo tema ha un widget di chat dal vivo sulla destra, quindi imposti il Facebook Fan Slider su "Sinistra" per evitare conflitti.
-   **Colore di sfondo (fs\_bg\_color)**

    *   **Cosa fa questa impostazione:** Imposta il colore di sfondo del pannello scorrevole stesso (non il contenuto di Facebook, ma il contenitore in cui scorre).
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un colore specifico (ad esempio, #FFFFFF per il bianco, #0000FF per il blu):* Lo sfondo della casella scorrevole cambierà in quel colore.
    *   **Valore consigliato:** Un colore che si abbina al branding del tuo negozio o un colore neutro come il bianco (`#FFFFFF`) o il grigio chiaro (`#F0F0F0`).
    *   **Scenario / esempio del commerciante:** Il tuo brand utilizza una specifica tonalità di blu. Inserisci il codice esadecimale per quel blu per assicurarti che lo slider corrisponda all'identità del tuo brand.
-   **Colore del bordo (fs\_br\_color)**

    *   **Cosa fa questa impostazione:** Imposta il colore del bordo attorno al pannello scorrevole.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un colore specifico (ad esempio, #CCCCCC per il grigio chiaro):* Il bordo della casella scorrevole cambierà in quel colore.
    *   **Valore consigliato:** Un colore sottile che complementa il colore di sfondo, o un colore che si abbina al tuo brand.
    *   **Scenario / esempio del commerciante:** Vuoi un bordo sottile attorno allo slider, quindi scegli un colore grigio chiaro (`#DDDDDD`).
-   **Lingua (fs\_langarray)**

    *   **Cosa fa questa impostazione:** Ti consente di selezionare la lingua per il Like Box/Page Plugin di Facebook. Questo assicura che il pulsante "Mi piace alla pagina" e altri testi generati da Facebook siano nella lingua corretta per il tuo pubblico.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su una lingua specifica (ad esempio, "en\_US" per l'inglese, "fr\_FR" per il francese):* Il plugin di Facebook verrà renderizzato in quella lingua.
    *   **Valore consigliato:** Seleziona la lingua principale del tuo negozio o del tuo pubblico di destinazione.
    *   **Scenario / esempio del commerciante:** Il tuo negozio serve principalmente clienti in Francia, quindi selezioni "fr\_FR" per visualizzare il contenuto di Facebook in francese.
-   **Adatta larghezza contenitore (fs\_adapt\_container\_width)**

    *   **Cosa fa questa impostazione:** Indica al Page Plugin di Facebook di adattare la sua larghezza alla larghezza del suo contenitore padre (la casella scorrevole).
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (selezionato):* Il contenuto di Facebook cercherà di riempire la `Larghezza` specificata per la casella scorrevole, rendendolo reattivo all'interno di quel contenitore.
        *   *Quando disabilitato (deselezionato):* Il contenuto di Facebook potrebbe utilizzare la sua larghezza predefinita, potenzialmente portando a overflow o spazio vuoto se non corrisponde all'impostazione `Larghezza`.
    *   **Valore consigliato:** *Abilitato* (selezionato) per una migliore reattività e per garantire che il contenuto di Facebook si adatti bene alla `Larghezza` specificata.
    *   **Scenario / esempio del commerciante:** Vuoi che il contenuto di Facebook si adatti automaticamente alla larghezza del tuo slider, quindi abiliti questa opzione per un aspetto più pulito.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | URL pagina Facebook (fs\_url) | URL della tua pagina Facebook | Specifica quale pagina Facebook visualizzare. **CRITICO!** |
| Configurazione modulo | Larghezza (fs\_width) | 280-300px | Imposta la larghezza del contenuto Facebook all'interno dello slider. |
| Configurazione modulo | Altezza (fs\_height) | 400-500px (di più se si mostrano post) | Imposta l'altezza del contenuto Facebook all'interno dello slider. |
| Configurazione modulo | Nascondi foto di copertina (fs\_hide\_cover) | Disabilitato (deselezionato) | Mostra/nasconde la grande foto di copertina dalla tua pagina Facebook. |
| Configurazione modulo | Mostra volti degli amici (fs\_show\_facepile) | Abilitato (selezionato) | Visualizza le immagini del profilo degli amici che hanno messo "Mi piace" alla tua pagina (prova sociale). |
| Configurazione modulo | Mostra post (fs\_show\_posts) | Abilitato (selezionato) | Visualizza i post recenti dalla tua timeline di Facebook. Richiede più altezza. |
| Configurazione modulo | Nascondi Call To Action (fs\_hide\_cta) | Disabilitato (deselezionato) | Mostra/nasconde il pulsante CTA configurato sulla tua pagina Facebook. |
| Configurazione modulo | Intestazione piccola (fs\_small\_header) | Abilitato (selezionato) | Utilizza un'intestazione più compatta per il plugin di Facebook. |
| Configurazione modulo | Scorri su (fanslider\_slideon) | Click | Determina se la casella scorre fuori al "Click" o all'"Hover". "Click" è meno intrusivo. |
| Configurazione modulo | Posizione (fs\_pos) | Sinistra / Destra | Imposta il lato dello schermo in cui appare la scheda. |
| Configurazione modulo | Colore di sfondo (fs\_bg\_color) | Corrisponde al tema / Bianco (#FFFFFF) | Imposta il colore di sfondo del pannello scorrevole. |
| Configurazione modulo | Colore del bordo (fs\_br\_color) | Grigio tenue (#DDDDDD) | Imposta il colore del bordo del pannello scorrevole. |
| Configurazione modulo | Lingua (fs\_langarray) | Lingua principale del tuo negozio | Imposta la lingua per il testo del plugin di Facebook. |
| Configurazione modulo | Adatta larghezza contenitore (fs\_adapt\_container\_width) | Abilitato (selezionato) | Rende il contenuto di Facebook reattivo alla larghezza dello slider. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Lo slider di Facebook non appare nel mio negozio. Cosa dovrei controllare per prima cosa?**
R1:

-   **Modulo abilitato:** Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Facebook Fan Slider" sia installato e abilitato.
-   **URL della pagina Facebook:** Ricontrolla l'`URL della pagina Facebook (fs_url)` nella configurazione del modulo. Assicurati che sia l'URL *esatto* della tua pagina Facebook (ad esempio, `https://www.facebook.com/MyPresta.eu`) e non solo il tuo profilo o un gruppo.
-   **Cache:** Svuota la cache di PrestaShop (Vai su **Parametri avanzati > Prestazioni**, quindi clicca su "Svuota la cache" nell'angolo in alto a destra). Svuota anche la cache del tuo browser.
-   **Conflitti del tema:** Passa temporaneamente al tema predefinito di PrestaShop per vedere se lo slider appare. Se lo fa, il tuo tema personalizzato potrebbe avere conflitti CSS o JavaScript.

**D2: Il contenuto di Facebook all'interno dello slider appare tagliato o troppo piccolo/grande.**
R2:

-   **Larghezza e Altezza:** Regola le impostazioni `Larghezza (fs_width)` e `Altezza (fs_height)` nella configurazione del modulo. Se stai mostrando post, avrai sicuramente bisogno di più altezza.
-   **Adatta larghezza contenitore:** Assicurati che `Adatta larghezza contenitore (fs_adapt_container_width)` sia abilitato (selezionato). Questo aiuta il contenuto di Facebook ad adattarsi in modo reattivo all'interno dello slider.
-   **Intestazione piccola:** Se stai cercando di risparmiare spazio verticale, prova ad abilitare `Intestazione piccola (fs_small_header)`.

**D3: La lingua del Like Box di Facebook è errata.**
R3:

-   **Impostazione lingua:** Vai alla configurazione del modulo e verifica l'impostazione `Lingua (fs_langarray)`. Seleziona il codice lingua corretto per il tuo pubblico di destinazione (ad esempio, `en_US` per l'inglese americano, `fr_FR` per il francese).

**D4: Ho modificato le impostazioni, ma non succede nulla nel front office.**
R4:

-   **Salva modifiche:** Clicca sempre sul pulsante "Salva" dopo aver apportato modifiche nella configurazione del modulo.
-   **Svuota cache:** PrestaShop si basa molto sulla cache. Dopo aver salvato, svuota sempre la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**) e la cache del tuo browser. Questa è la ragione più comune per cui le modifiche non appaiono immediatamente.

**D5: Lo slider si sovrappone a un altro elemento del mio sito.**
R5:

-   **Posizione:** Regola l'impostazione `Posizione (fs_pos)` (Sinistra o Destra) per vedere se spostare lo slider sull'altro lato risolve il conflitto.
-   **Regolazioni CSS (necessario sviluppatore):** Se il problema persiste, potrebbe richiedere regolazioni CSS personalizzate sia allo slider che all'elemento in conflitto. Questo di solito coinvolgerebbe un webmaster o uno sviluppatore.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Facebook Fan Slider (`fanslider`) è un modulo PrestaShop standard che implementa la classe `Module`. Sfrutta principalmente il sistema di hook di PrestaShop per iniettare il suo HTML, CSS e JavaScript nel front-office. La funzionalità principale ruota attorno alla visualizzazione del Page Plugin ufficiale di Facebook all'interno di un elemento UI scorrevole personalizzato. La configurazione è gestita tramite il metodo `getContent()`, che memorizza le impostazioni in `ps_configuration`. Il modulo non utilizza tabelle di database personalizzate o classi `ObjectModel`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Tutto il rendering e la logica del front-office sono gestiti direttamente all'interno del file principale del modulo (`fanslider.php`) tramite hook e JavaScript iniettato.
-   **Controller Admin Back-Office**: Nessuno. La configurazione è gestita dal metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

-   Non sono presenti classi personalizzate o definizioni `ObjectModel` nella directory `classes/`. La logica del modulo è autocontenuta all'interno di `fanslider/fanslider.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include diversi file JavaScript, principalmente per l'animazione scorrevole e la funzionalità del selettore colori.

-   `fanslider/jscolor/jscolor.js`

    *   **Ambito:** Back-office (utilizzato in `getContent()` per gli input del selettore colori).
    *   **Responsabilità:** Fornisce un'utilità JavaScript per il selettore colori, consentendo agli amministratori di selezionare visivamente i colori per lo sfondo e il bordo dello slider. Si collega ai campi di input con la classe `jscolor`.
-   `fanslider/js/fanslider-click.js`

    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questo script gestisce l'interazione "click" per lo slider. Ascolta gli eventi di click sulla scheda dello slider e attiva/disattiva la visibilità e la posizione del contenitore principale dello slider (`#fanslider`). Gestisce anche la classe `fanslider_open` per controllare lo stato aperto/chiuso.
-   `fanslider/js/fanslider.js`

    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questo è probabilmente lo script principale per l'animazione e la configurazione iniziale dello slider. Gestisce l'interazione "hover" se configurata e potenzialmente calcola le posizioni iniziali o applica trasformazioni CSS per l'effetto scorrevole. Interagisce con gli elementi `#fanslider` e `#fanslider_tab`.
-   `fanslider/script.js`

    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questo script contiene probabilmente la logica principale per l'inizializzazione del Page Plugin di Facebook (FB.init e FB.XFBML.parse) e potenzialmente altre configurazioni generali o binding di eventi relativi al comportamento dello slider. Assicura che l'SDK di Facebook sia caricato e che il plugin sia renderizzato correttamente.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non elenca esplicitamente i file CSS in `views/css/`. Lo stile per lo slider è probabilmente incorporato direttamente nel metodo `hookDisplayHeader` del file `fanslider.php` o all'interno del template `rightcolumn.tpl`, o generato dinamicamente in base alla configurazione. Gli sviluppatori dovrebbero ispezionare l'HTML generato e il file principale del modulo per stili inline o blocchi `<style>`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   `fanslider/views/templates/hook/rightcolumn.tpl`
        *   **Hook:** Questo template è progettato principalmente per essere renderizzato in un hook che consente l'iniezione di contenuto nella pagina, come `displayFooter` o `displayHeader` (anche se il suo nome suggerisce `displayRightColumn`, l'implementazione del modulo lo posiziona come un elemento fisso).
        *   **Blocco visivo:** Questo template produce la struttura HTML principale per il Facebook Fan Slider. Tipicamente include:
            *   Il contenitore principale per lo slider (`#fanslider`).
            *   La scheda cliccabile (`#fanslider_tab`).
            *   Il contenitore per il Page Plugin di Facebook (`<div class="fb-page">`).
            *   Riceve variabili di configurazione dal modulo per impostare dinamicamente gli attributi per il Page Plugin di Facebook (ad esempio, `data-href`, `data-width`, `data-height`, `data-hide-cover`, `data-show-facepile`, `data-show-posts`, `data-hide-cta`, `data-small-header`, `data-adapt-container-width`).
            *   Include anche il `div` necessario per l'SDK di Facebook per renderizzare il plugin.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    *   Il modulo non crea tabelle di database personalizzate.
    *   Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi prefissate con `FS_` o `FANSIDER_` (ad esempio, `FS_WIDTH`, `FANSIDER_SLIDEON`).
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Inietta i file CSS e JavaScript necessari e potenzialmente lo script di inizializzazione dell'SDK di Facebook. Inoltre, può produrre stili inline basati sulla configurazione. |
| `displayFooter` | Eseguito nella parte inferiore di ogni pagina, prima del tag di chiusura `</body>`. | Renderizza la struttura HTML principale del Facebook Fan Slider (da `rightcolumn.tpl`) e assicura che l'SDK di Facebook sia caricato e il Page Plugin sia inizializzato dopo che il DOM è pronto. Questo è il punto in cui il componente visivo viene aggiunto alla pagina. |

## 5. Supporto ufficiale e aggiornamenti

Per le ultime versioni, aggiornamenti e supporto professionale per il modulo Facebook Fan Slider, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
"""
