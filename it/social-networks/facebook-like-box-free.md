---
title: "Facebook Like Box Free - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Facebook Like Box Free di MyPresta.eu."
sidebar:
  label: "Facebook Like Box Free - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Like Box Free su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-like-box-free/)
>
> ---


# Facebook Like Box Free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo. Nessun requisito di hosting speciale oltre a una configurazione PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo Facebook Like Box Free. Qui troverai tutte le impostazioni per controllarne l'aspetto e il comportamento.

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio del commerciante |
| --- | --- | --- | --- | --- |
| **Abilitato** / **Disabilitato** | Controlla se il Facebook Like Box è attivo e visibile sul tuo negozio. | *Quando Abilitato:* Il Like Box apparirà sul tuo negozio nella posizione scelta. *Quando Disabilitato:* Il Like Box sarà nascosto dal tuo negozio. | **Abilitato** | Vuoi iniziare a promuovere la tua pagina Facebook. |
| **Posizione** | Determina dove verrà visualizzato il Like Box sul tuo negozio. | *Quando impostato su Colonna sinistra:* Il Like Box appare nella barra laterale sinistra. *Quando impostato su Colonna destra:* Il Like Box appare nella barra laterale destra. *Quando impostato su Homepage:* Il Like Box appare nell'area del contenuto principale della tua homepage. *Quando impostato su Footer:* Il Like Box appare nella parte inferiore di ogni pagina. | **Colonna destra** o **Homepage** | Vuoi che il Like Box sia ben visibile senza interferire con la visualizzazione dei prodotti. |
| **URL Pagina Facebook** | Questo è il link diretto alla tua Pagina Facebook ufficiale. | *Quando impostato sull'URL della tua pagina (es. `https://www.facebook.com/MyPrestaEU`):* Il Like Box visualizzerà il contenuto e un pulsante "Mi Piace" per la *tua* specifica Pagina Facebook. *Quando lasciato vuoto o errato:* Il Like Box potrebbe non essere visualizzato correttamente o mostrerà un errore. | L'URL della tua Pagina Facebook | Vuoi connettere i visitatori del tuo negozio alla presenza Facebook del tuo brand. |
| **Larghezza** | Imposta la larghezza del Like Box in pixel. | *Quando impostato su un valore in pixel specifico (es. `280`):* Il Like Box avrà esattamente quella larghezza. *Quando lasciato vuoto:* Il modulo tenterà di regolare automaticamente la larghezza, ma è spesso meglio impostare un valore specifico per un design coerente. | `280` (o regola per adattarlo alla tua colonna/layout) | La tua colonna destra è larga 300px, quindi imposti la larghezza del Like Box a 280px per adattarsi bene con un po' di spaziatura. |
| **Altezza** | Imposta l'altezza del Like Box in pixel. | *Quando impostato su un valore in pixel specifico (es. `500`):* Il Like Box avrà esattamente quell'altezza. *Quando lasciato vuoto:* Il modulo tenterà di regolare automaticamente l'altezza. | `500` (o regola in base al contenuto che vuoi mostrare) | Vuoi mostrare alcuni post recenti, quindi imposti l'altezza a 500px per consentire spazio sufficiente. |
| **Nascondi copertina** | Controlla se la grande foto di copertina della tua Pagina Facebook viene visualizzata nella parte superiore del Like Box. | *Quando abilitato:* La foto di copertina sarà nascosta, rendendo il Like Box più compatto. *Quando disabilitato:* La foto di copertina sarà visibile. | **Abilitato** (per un aspetto più pulito) | Preferisci un design minimalista e vuoi che il Like Box occupi meno spazio verticale. |
| **Immagini del profilo** (Mostra Facepile) | Determina se le immagini del profilo delle persone che hanno messo "Mi Piace" alla tua pagina vengono mostrate sotto il pulsante "Mi Piace". | *Quando abilitato:* Apparirà una riga di piccole immagini del profilo, mostrando la prova sociale. *Quando disabilitato:* Queste immagini del profilo non verranno mostrate. | **Abilitato** (per la prova sociale) | Vuoi mostrare ai visitatori che molti altri hanno già messo "Mi Piace" alla tua pagina, incoraggiandoli a fare lo stesso. |
| **Mostra post** (Mostra Stream) | Controlla se i post recenti della tua Pagina Facebook vengono visualizzati all'interno del Like Box. | *Quando abilitato:* I tuoi ultimi post di Facebook saranno visibili, rendendo il Like Box più dinamico. *Quando disabilitato:* Verranno mostrati solo il pulsante "Mi Piace" e il facepile (se abilitato). | **Abilitato** | Pubblichi attivamente su Facebook e vuoi mostrare i tuoi ultimi contenuti direttamente sul tuo negozio. |
| **Pulsante di invito all'azione** (Nascondi CTA) | Controlla se il pulsante "Invito all'azione" (es. "Invia messaggio", "Acquista ora") dalla tua Pagina Facebook è nascosto. | *Quando abilitato:* Il pulsante CTA sarà nascosto. *Quando disabilitato:* Il pulsante CTA sarà visibile se configurato sulla tua Pagina Facebook. | **Abilitato** (spesso per un aspetto più pulito) | Vuoi concentrarti esclusivamente sull'ottenere un "Mi Piace" e non vuoi che un altro pulsante distragga i visitatori. |
| **Intestazione piccola** | Rende l'intestazione del Like Box più piccola. | *Quando abilitato:* L'intestazione (contenente il nome della tua pagina e il pulsante "Mi Piace") sarà più compatta. *Quando disabilitato:* L'intestazione avrà dimensioni standard. | **Abilitato** (per un design più compatto) | Vuoi che il Like Box sia meno invadente e si integri più facilmente nel design del tuo negozio. |
| **Libreria Facebook** (Includi App) | Questa impostazione controlla se il necessario SDK JavaScript di Facebook viene caricato. | *Quando abilitato:* Il modulo caricherà l'SDK di Facebook, che è essenziale per il corretto funzionamento del Like Box. *Quando disabilitato:* Il Like Box probabilmente non verrà visualizzato o non funzionerà correttamente. | **Abilitato** | Questo è fondamentale per il funzionamento del Like Box. |

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilitato/Disabilitato | Abilitato | Attiva/Disattiva il Like Box sul tuo negozio. |
| Configurazione modulo | Posizione | Colonna destra / Homepage | Determina dove appare il Like Box (Colonna sinistra/destra, Homepage, Footer). |
| Configurazione modulo | URL Pagina Facebook | L'URL della tua Pagina Facebook | Collega il Like Box alla tua specifica Pagina Facebook. |
| Configurazione modulo | Larghezza | 280 | Imposta la larghezza del Like Box in pixel. |
| Configurazione modulo | Altezza | 500 | Imposta l'altezza del Like Box in pixel. |
| Configurazione modulo | Nascondi copertina | Abilitato | Nasconde la grande foto di copertina per un aspetto più compatto. |
| Configurazione modulo | Immagini del profilo (Mostra Facepile) | Abilitato | Mostra le immagini del profilo delle persone che hanno messo "Mi Piace" alla tua pagina (prova sociale). |
| Configurazione modulo | Mostra post (Mostra Stream) | Abilitato | Visualizza i post recenti della tua Pagina Facebook. |
| Configurazione modulo | Pulsante di invito all'azione (Nascondi CTA) | Abilitato | Nasconde il pulsante di invito all'azione della Pagina Facebook. |
| Configurazione modulo | Intestazione piccola | Abilitato | Rende l'intestazione del Like Box più compatta. |
| Configurazione modulo | Libreria Facebook (Includi App) | Abilitato | Carica l'SDK JavaScript di Facebook necessario per la funzionalità. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il Facebook Like Box non viene visualizzato nel mio negozio. Cosa devo fare?**
R:

1.  **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Facebook Like Box Free" sia installato e abilitato.
2.  **Verifica la configurazione:** Vai alla pagina di configurazione del modulo.
    -   Assicurati che "Abilitato" sia impostato su SÌ.
    -   Ricontrolla che l'URL della Pagina Facebook sia corretto e completo (es. `https://www.facebook.com/MyPrestaEU`).
    -   Assicurati che "Libreria Facebook" (Includi App) sia abilitato.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte i vecchi file memorizzati nella cache impediscono la visualizzazione di nuovi moduli.
4.  **Controlla la posizione dell'hook:** Assicurati che la "Posizione" selezionata (es. Colonna destra, Homepage) sia effettivamente attiva nel tuo tema. Alcuni temi potrebbero non visualizzare determinate colonne. Puoi controllare **Design > Posizioni** per vedere se il modulo è agganciato correttamente.

**D: Il Like Box sembra troppo largo/stretto o troppo alto/basso.**
R: Regola le impostazioni "Larghezza" e "Altezza" nella pagina di configurazione del modulo. Sperimenta con diversi valori in pixel finché non si adatta perfettamente al layout del tuo tema. Ricorda di svuotare la cache del tuo browser dopo aver apportato modifiche per vedere l'aggiornamento.

**D: Ho cambiato le impostazioni, ma non è successo nulla nel mio negozio.**
R: Dopo aver salvato le modifiche nella configurazione del modulo, svuota sempre la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**) e poi svuota la cache del tuo browser (Ctrl+F5 o Cmd+R) per assicurarti di visualizzare l'ultima versione del tuo negozio.

**D: Il Like Box mostra un messaggio di errore o non carica il contenuto.**
R:

1.  **URL errato:** La ragione più comune è un "URL Pagina Facebook" errato. Ricontrollalo per errori di battitura.
2.  **Problemi con l'API di Facebook:** Occasionalmente, potrebbero esserci problemi temporanei con l'API di Facebook. Attendi un po' e ricontrolla.
3.  **Conflitti con il tema:** Raramente, il JavaScript o il CSS del tuo tema potrebbero entrare in conflitto. Se i passaggi precedenti non funzionano, prova a passare temporaneamente al tema PrestaShop predefinito per escludere un conflitto con il tema.

**D: Posso tradurre il testo "Mi Piace alla Pagina" in altre lingue?**
R: Il testo all'interno del Facebook Like Box stesso (come "Mi Piace alla Pagina" o il contenuto del post) è controllato da Facebook e si adatterà automaticamente alle impostazioni della lingua di Facebook dell'utente. Le impostazioni del back-office del modulo sono traducibili tramite **Internazionale > Traduzioni** in PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che lavorano con il modulo Facebook Like Box Free.

### 4.1 Panoramica dell'architettura

Il modulo `Facebook Like Box Free` è un modulo PrestaShop semplice progettato principalmente per incorporare il Facebook Page Plugin (precedentemente Like Box) utilizzando l'SDK JavaScript ufficiale di Facebook. Segue una struttura di modulo PrestaShop di base, sfruttando la classe `Module` per l'installazione, la disinstallazione e la configurazione. La sua funzionalità principale ruota attorno alla visualizzazione del widget di Facebook tramite un template Smarty agganciato a varie posizioni del front-office. Non ci sono tabelle di database personalizzate o ObjectModels complessi coinvolti; tutta la configurazione è memorizzata in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la logica è incapsulata nel file principale del modulo (`likeboxfree.php`).

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** definisce alcuna classe o ObjectModels personalizzato nella directory `classes/`. Tutta la logica del modulo risiede nel file principale `likeboxfree.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato in `views/js/`.
L'SDK JavaScript di Facebook viene caricato dinamicamente dal template del modulo se l'impostazione `lbf_includeapp` è abilitata. Questo è gestito dallo script di Facebook stesso, non da uno script di modulo personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`likeboxfree/css.css`**
    -   **Scopo:** Stile del front-office per il cliente.
    -   **Componenti UI principali e contenitori che stilizza:** Questo file fornisce uno stile di base per il wrapper attorno al Facebook Like Box per garantire che si integri in modo pulito nel layout di PrestaShop, in particolare per gli hook di colonna. Potrebbe contenere regole per padding, margini o reattività di base.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori possono ispezionare l'HTML generato per trovare l'elemento wrapper (ad esempio, un `div` con un ID o una classe specifica generata dal modulo) e sovrascrivere i suoi stili nel `custom.css` o `theme.css` del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   **`likeboxfree/rightcolumn.tpl`**
        -   **Agganciato a:** `displayHome`, `displayFooter`, `displayRightColumn`, `displayLeftColumn` (a seconda della configurazione `likeboxfree_position`).
        -   **Output del blocco visivo:** Questo template è responsabile del rendering della struttura HTML che incorpora il Facebook Page Plugin. Genera dinamicamente l'elemento `div` con la classe `fb-page` e gli attributi di dati (`data-href`, `data-width`, `data-height`, ecc.) in base alle impostazioni di configurazione del modulo. Include anche il frammento JavaScript necessario per inizializzare l'SDK di Facebook e analizzare il plugin.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:
    Questo modulo non crea tabelle di database personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi con prefisso `likeboxfree_` o `lbf_`.

    -   Voci di `ps_configuration`:
        -   `likeboxfree_position`: Memorizza la posizione dell'hook scelta (es. `displayRightColumn`).
        -   `lbf_width`: Larghezza del Like Box.
        -   `lbf_height`: Altezza del Like Box.
        -   `lbf_hide_cover`: Booleano (0/1) per nascondere la foto di copertina.
        -   `lbf_show_facepile`: Booleano (0/1) per mostrare le immagini del profilo.
        -   `lbf_show_posts`: Booleano (0/1) per mostrare i post.
        -   `lbf_hide_cta`: Booleano (0/1) per nascondere il pulsante di invito all'azione.
        -   `lbf_small_header`: Booleano (0/1) per un'intestazione piccola.
        -   `lbf_url`: L'URL della Pagina Facebook.
        -   `lbf_includeapp`: Booleano (0/1) per includere l'SDK di Facebook.
        -   (Potrebbero esistere anche chiavi legacy/non utilizzate da versioni precedenti, ma quelle sopra sono attive).
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHome` | Rende il contenuto sulla homepage. | Visualizza il Facebook Like Box nell'area del contenuto principale della homepage se configurato. |
| `displayFooter` | Rende il contenuto nel footer del negozio. | Visualizza il Facebook Like Box nella parte inferiore di ogni pagina se configurato. |
| `displayRightColumn` | Rende il contenuto nella barra laterale destra. | Visualizza il Facebook Like Box nella colonna destra delle pagine se configurato. |
| `displayLeftColumn` | Rende il contenuto nella barra laterale sinistra. | Visualizza il Facebook Like Box nella colonna sinistra delle pagine se configurato. |

I metodi `hookDisplay*` del modulo controllano il valore di configurazione `likeboxfree_position` e rendono il template `rightcolumn.tpl` solo se l'hook corrente corrisponde alla posizione configurata.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Facebook Like Box Free", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e all'integrazione del modulo.
