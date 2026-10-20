---
title: "Twitter widget free - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Twitter widget free di MyPresta.eu."
sidebar:
  label: "Twitter widget free - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Twitter widget free su MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-widget-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/twitter-widget-free/)
>
> ---


# Twitter widget free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito speciale oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Twitter widget free". Qui definirai come la tua timeline di Twitter appare e funziona nel tuo negozio.

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- |
| **Nome utente Twitter** | `mypresta` (esempio) | **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Specifica l'account Twitter (X) i cui tweet pubblici verranno visualizzati. Devi inserire il nome utente del tuo account (es. `mypresta`, `nomedelnegozio`).   **Effetto della modifica di questa impostazione:**   *Quando impostato sul tuo nome utente:* Il widget recupererà e visualizzerà i tweet dal tuo account specificato.   *Quando lasciato vuoto o errato:* Il widget non visualizzerà alcun tweet o visualizzerà un messaggio di errore, poiché non saprà da quale account recuperare i dati.   **Valore consigliato:** Il tuo nome utente Twitter (X) ufficiale, senza il simbolo "@".   **Scenario / esempio per il commerciante:** Se il tuo handle Twitter è `@MyAwesomeStore`, dovresti inserire `MyAwesomeStore` qui. |
| **ID Widget** | `(vuoto)` | **Cosa fa questa impostazione:** Questa è un'impostazione avanzata per configurazioni specifiche del widget di Twitter. Twitter ti consente di creare widget personalizzati sulla loro piattaforma, che generano un ID univoco. Questo ID può essere utilizzato per visualizzare una timeline altamente personalizzata (es. una timeline di elenchi specifici, risultati di ricerca o collezioni).   **Effetto della modifica di questa impostazione:**   *Quando lasciato vuoto:* Il modulo genererà una timeline standard basata sul tuo "Nome utente Twitter". Questo è solitamente sufficiente per la maggior parte dei commercianti.   *Quando viene inserito un ID Widget valido:* Il modulo visualizzerà la timeline specifica e personalizzata associata a quell'ID, sovrascrivendo la timeline utente predefinita.   **Valore consigliato:** Lascia vuoto a meno che tu non abbia creato un widget personalizzato sulla piattaforma per sviluppatori di Twitter e desideri specificamente utilizzare il suo ID.   **Scenario / esempio per il commerciante:** Potresti creare un widget Twitter personalizzato che mostra solo i tweet contenenti un hashtag specifico relativo a una campagna. Dovresti quindi ottenere l'ID di quel widget da Twitter e inserirlo qui. |
| **Tema** | `light` | **Cosa fa questa impostazione:** Controlla il tema visivo del widget di Twitter.   **Effetto della modifica di questa impostazione:**   *Quando impostato su `light` (predefinito):* Il widget avrà uno sfondo chiaro e testo scuro, adatto alla maggior parte dei negozi PrestaShop con tema chiaro.   *Quando impostato su `dark` (se disponibile):* Il widget avrà uno sfondo scuro e testo chiaro, ideale per negozi con tema scuro o per creare un contrasto.   **Valore consigliato:** `light` per la maggior parte dei negozi. Scegli `dark` se il design del tuo negozio utilizza una combinazione di colori scuri.   **Scenario / esempio per il commerciante:** Se il tuo sito web ha uno sfondo pulito e bianco, il tema `light` si integrerà perfettamente. Se il tuo sito utilizza uno sfondo grigio scuro o nero sofisticato, il tema `dark` sarebbe più appropriato. |
| **Colore Link** | `(vuoto)` | **Cosa fa questa impostazione:** Ti permette di personalizzare il colore dei link all'interno del widget di Twitter (es. hashtag, menzioni, URL).   **Effetto della modifica di questa impostazione:**   *Quando lasciato vuoto:* Il widget utilizzerà il colore predefinito dei link di Twitter (tipicamente una tonalità di blu).   *Quando viene inserito un codice colore esadecimale valido (es. `#FF0000` per il rosso):* Tutti i link all'interno del widget verranno visualizzati in quel colore personalizzato.   **Valore consigliato:** Lascia vuoto per il predefinito, o inserisci un codice colore esadecimale che corrisponda al branding del tuo negozio.   **Scenario / esempio per il commerciante:** Se il colore primario del tuo brand è il verde, potresti inserire `#008000` per far sì che i link nel widget corrispondano al tuo brand. |
| **Colore Bordo** | `(vuoto)` | **Cosa fa questa impostazione:** Ti permette di personalizzare il colore del bordo attorno al widget di Twitter.   **Effetto della modifica di questa impostazione:**   *Quando lasciato vuoto:* Il widget utilizzerà il colore predefinito del bordo di Twitter.   *Quando viene inserito un codice colore esadecimale valido:* Il bordo del widget verrà visualizzato in quel colore personalizzato.   **Valore consigliato:** Lascia vuoto per il predefinito, o inserisci un codice colore esadecimale che corrisponda al branding del tuo negozio o si integri con il tuo layout.   **Scenario / esempio per il commerciante:** Per far risaltare il widget con una cornice sottile, potresti usare un bordo grigio chiaro `#CCCCCC`. |
| **Limite Tweet** | `20` | **Cosa fa questa impostazione:** Determina il numero massimo di tweet che verranno visualizzati nella timeline.   **Effetto della modifica di questa impostazione:**   *Quando impostato su un numero inferiore (es. `3`):* Saranno visibili solo i tweet più recenti, rendendo il widget più corto.   *Quando impostato su un numero superiore (es. `20`):* Verranno caricati più tweet, rendendo il widget più lungo e consentendo più scorrimento.   **Valore consigliato:** Da `3` a `7` per le colonne laterali per mantenerlo conciso, da `10` a `20` per aree più ampie come il piè di pagina o il contenuto principale.   **Scenario / esempio per il commerciante:** Se posizioni il widget in una colonna sinistra stretta, potresti impostarlo a `3` per evitare di rendere la colonna troppo lunga. Nel piè di pagina, potresti impostarlo a `10` per mostrare più attività. |
| **Altezza** | `300` | **Cosa fa questa impostazione:** Imposta l'altezza fissa del widget di Twitter in pixel.   **Effetto della modifica di questa impostazione:**   *Quando impostato su un numero inferiore (es. `200`):* Il widget sarà più corto, richiedendo potenzialmente più scorrimento per vedere tutti i tweet (fino al Limite Tweet).   *Quando impostato su un numero superiore (es. `500`):* Il widget sarà più alto, visualizzando più tweet contemporaneamente senza scorrimento.   **Valore consigliato:** Da `280` a `400` pixel, a seconda del posizionamento e dello spazio disponibile.   **Scenario / esempio per il commerciante:** Per una colonna destra, un'altezza di `300px` è spesso un buon equilibrio. Per un posizionamento nel piè di pagina, potresti aumentarla a `400px` se hai ampio spazio verticale. |
| **Larghezza** | `(vuoto)` | **Cosa fa questa impostazione:** Imposta la larghezza fissa del widget di Twitter in pixel.   **Effetto della modifica di questa impostazione:**   *Quando lasciato vuoto:* Il widget tenterà di regolare automaticamente la sua larghezza per adattarsi al contenitore in cui è posizionato (comportamento responsive). Questo è generalmente consigliato.   *Quando impostato su un numero specifico (es. `250`):* Il widget manterrà quella larghezza fissa, il che potrebbe causare overflow o spazio vuoto se il contenitore è più grande o più piccolo.   **Valore consigliato:** Lascia vuoto per un comportamento responsive, o imposta una larghezza specifica se hai bisogno di un controllo preciso e comprendi le implicazioni per diverse dimensioni dello schermo.   **Scenario / esempio per il commerciante:** Lasciarlo vuoto assicura che appaia bene su mobile. Se hai assolutamente bisogno di una larghezza fissa per un layout molto specifico, potresti impostarla a `280px` per una colonna stretta. |
| **Lingua** | `en` | **Cosa fa questa impostazione:** Determina la lingua in cui viene visualizzata l'interfaccia del widget di Twitter (es. pulsante "Visualizza su Twitter", timestamp).   **Effetto della modifica di questa impostazione:**   *Quando impostato su `en` (Inglese):* L'interfaccia del widget sarà in inglese.   *Quando impostato su un altro codice lingua valido (es. `fr` per il francese, `es` per lo spagnolo):* L'interfaccia del widget sarà localizzata in quella lingua.   **Valore consigliato:** La lingua principale del tuo negozio.   **Scenario / esempio per il commerciante:** Se il tuo negozio serve principalmente clienti in Francia, impostare questo su `fr` renderà il widget più user-friendly per loro. |
| **Mostra Intestazione** | `YES` | **Cosa fa questa impostazione:** Controlla se la sezione dell'intestazione del widget di Twitter (che mostra il nome del tuo account e l'etichetta "Tweet") è visibile.   **Effetto della modifica di questa impostazione:**   *Quando abilitato (YES):* L'intestazione verrà visualizzata, fornendo un contesto chiaro su chi sono i tweet mostrati.   *Quando disabilitato (NO):* L'intestazione verrà nascosta, risultando in un widget più compatto, ma potenzialmente con un contesto meno chiaro.   **Valore consigliato:** `YES` per chiarezza, a meno che tu non abbia bisogno di un design molto minimalista.   **Scenario / esempio per il commerciante:** Se il widget si trova in una posizione prominente, `YES` è una buona scelta. Se è un piccolo widget in un'area affollata, `NO` potrebbe far risparmiare spazio. |
| **Mostra Piè di pagina** | `YES` | **Cosa fa questa impostazione:** Controlla se la sezione del piè di pagina del widget di Twitter (tipicamente che mostra il link "Visualizza su Twitter") è visibile.   **Effetto della modifica di questa impostazione:**   *Quando abilitato (YES):* Il piè di pagina verrà visualizzato, fornendo un link diretto per gli utenti per visitare il tuo profilo Twitter completo.   *Quando disabilitato (NO):* Il piè di pagina verrà nascosto, rendendo il widget più compatto.   **Valore consigliato:** `YES` per incoraggiare gli utenti a seguirti su Twitter.   **Scenario / esempio per il commerciante:** Mantenere `YES` aiuta a generare traffico verso il tuo profilo Twitter. |
| **Mostra Bordo** | `YES` | **Cosa fa questa impostazione:** Controlla se un bordo viene visualizzato attorno al widget di Twitter.   **Effetto della modifica di questa impostazione:**   *Quando abilitato (YES):* Un bordo incornicerà il widget, aiutandolo a distinguersi dal contenuto circostante.   *Quando disabilitato (NO):* Il widget non avrà un bordo visibile, integrandosi più fluidamente con lo sfondo.   **Valore consigliato:** `YES` per una migliore separazione visiva, specialmente nelle colonne.   **Scenario / esempio per il commerciante:** Se la tua pagina ha molto contenuto, un bordo aiuta a definire lo spazio del widget. Se desideri un aspetto molto pulito e integrato, `NO` potrebbe essere preferito. |
| **Mostra Barra di Scorrimento** | `YES` | **Cosa fa questa impostazione:** Controlla se una barra di scorrimento appare all'interno del widget se il contenuto (tweet) supera l'altezza impostata.   **Effetto della modifica di questa impostazione:**   *Quando abilitato (YES):* Apparirà una barra di scorrimento, consentendo agli utenti di scorrere tutti i tweet caricati all'interno dell'altezza fissa.   *Quando disabilitato (NO):* Non apparirà alcuna barra di scorrimento. Se i tweet superano l'altezza, verranno tagliati o il widget potrebbe espandersi (a seconda di altre impostazioni e del comportamento del browser). Questo non è generalmente consigliato in quanto nasconde il contenuto.   **Valore consigliato:** `YES` per garantire che tutti i tweet siano accessibili.   **Scenario / esempio per il commerciante:** Mantieni sempre `YES` a meno che tu non voglia mostrare solo 1-2 tweet e non desideri mai lo scorrimento. |
| **Sfondo Trasparente** | `YES` | **Cosa fa questa impostazione:** Controlla se lo sfondo del widget di Twitter è trasparente.   **Effetto della modifica di questa impostazione:**   *Quando abilitato (YES):* Lo sfondo del widget sarà trasparente, consentendo al colore o all'immagine di sfondo del tuo negozio di essere visibile.   *Quando disabilitato (NO):* Il widget avrà uno sfondo solido (bianco per il tema `light`, scuro per il tema `dark`), creando potenzialmente un aspetto squadrato.   **Valore consigliato:** `YES` per una migliore integrazione con il tuo tema.   **Scenario / esempio per il commerciante:** Se il tuo negozio ha uno sfondo testurizzato o un colore di sfondo specifico, `YES` farà apparire il widget come una parte naturale del tuo design. |
| **Mostra Risposte** | `YES` | **Cosa fa questa impostazione:** Controlla se le risposte ai tweet sono incluse nella timeline.   **Effetto della modifica di questa impostazione:**   *Quando abilitato (YES):* Le risposte verranno mostrate, fornendo un contesto di conversazione più completo.   *Quando disabilitato (NO):* Verranno mostrati solo i tweet originali e i retweet, rendendo la timeline potenzialmente più pulita ma meno conversazionale.   **Valore consigliato:** `YES` per un feed più attivo e coinvolgente.   **Scenario / esempio per il commerciante:** Se interagisci frequentemente con i clienti tramite risposte, `YES` è importante per mostrare tale interazione. Se il tuo feed è puramente per annunci, `NO` potrebbe essere preferito. |
| **Riproduzione Automatica Video** | `NO` | **Cosa fa questa impostazione:** Controlla se i video incorporati nei tweet all'interno del widget verranno riprodotti automaticamente.   **Effetto della modifica di questa impostazione:**   *Quando abilitato (YES):* I video inizieranno a essere riprodotti automaticamente quando appaiono nel viewport. Questo può essere coinvolgente ma potrebbe consumare larghezza di banda e infastidire alcuni utenti.   *Quando disabilitato (NO):* I video richiederanno un clic dell'utente per essere riprodotti.   **Valore consigliato:** `NO` per evitare di sorprendere i clienti con il suono o di consumare i loro dati senza consenso.   **Scenario / esempio per il commerciante:** Generalmente, `NO` è migliore per l'esperienza utente. Se hai un video molto specifico, silenzioso e breve che vuoi evidenziare, potresti considerare `YES`, ma procedi con cautela. |
| **Nascondi Barra di Scorrimento** | `NO` | **Cosa fa questa impostazione:** Questa impostazione è probabilmente ridondante o in conflitto con "Mostra Barra di Scorrimento". In generale, se "Mostra Barra di Scorrimento" è YES, questa impostazione dovrebbe essere NO.   **Effetto della modifica di questa impostazione:**   *Quando abilitato (YES):* Tenta di nascondere la barra di scorrimento. Ciò può portare a contenuti inaccessibili se l'altezza è fissa e i tweet la superano.   *Quando disabilitato (NO):* Consente alla barra di scorrimento di essere visibile se anche "Mostra Barra di Scorrimento" è YES.   **Valore consigliato:** `NO` per garantire che il contenuto sia sempre accessibile.   **Scenario / esempio per il commerciante:** Mantieni sempre `NO` in combinazione con `Mostra Barra di Scorrimento: YES`. |
| **Posiziona nell'hook** | `displayRightColumn` | **Cosa fa questa impostazione:** Determina dove nel tuo negozio PrestaShop verrà visualizzato il widget di Twitter.   **Effetto della modifica di questa impostazione:**   *Quando impostato su `displayRightColumn` (predefinito):* Il widget apparirà nella barra laterale destra.   *Quando impostato su `displayLeftColumn` (se disponibile):* Il widget apparirà nella barra laterale sinistra.   *Quando impostato su `displayFooter` (se disponibile):* Il widget apparirà nella sezione del piè di pagina.   *Quando impostato su `displayHeader` (se disponibile):* Il widget apparirà nella sezione dell'intestazione.   *Quando impostato su `displayProductButtons` o simili (se disponibile):* Il widget apparirà sulle pagine prodotto.   **Valore consigliato:** `displayRightColumn` o `displayLeftColumn` per visibilità generale, `displayFooter` per un posizionamento meno intrusivo. Scegli in base al layout del tuo tema e a dove vuoi attirare l'attenzione.   **Scenario / esempio per il commerciante:** Se il tuo tema ha una barra laterale destra prominente, `displayRightColumn` è una buona scelta. Se vuoi che sia visibile su ogni pagina ma non occupi molto spazio, `displayFooter` è adatto. |

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|
| Configurazione Modulo | Nome utente Twitter | Il tuo nome utente X | Specifica l'account da cui visualizzare i tweet. |
| Configurazione Modulo | ID Widget | Vuoto | Avanzato: Utilizza per widget personalizzati generati da Twitter. |
| Configurazione Modulo | Tema | `light` | Tema visivo del widget (chiaro/scuro). |
| Configurazione Modulo | Colore Link | Vuoto | Personalizza i colori dei link all'interno del widget. |
| Configurazione Modulo | Colore Bordo | Vuoto | Personalizza il colore del bordo del widget. |
| Configurazione Modulo | Limite Tweet | `20` | Numero massimo di tweet da visualizzare. |
| Configurazione Modulo | Altezza | `300` | Altezza fissa del widget in pixel. |
| Configurazione Modulo | Larghezza | Vuoto | Larghezza fissa del widget in pixel (lascia vuoto per responsive). |
| Configurazione Modulo | Lingua | `en` | Lingua dell'interfaccia del widget. |
| Configurazione Modulo | Mostra Intestazione | `YES` | Mostra/nascondi l'intestazione del widget (nome account). |
| Configurazione Modulo | Mostra Piè di pagina | `YES` | Mostra/nascondi il piè di pagina del widget (link Visualizza su Twitter). |
| Configurazione Modulo | Mostra Bordo | `YES` | Mostra/nascondi il bordo esterno del widget. |
| Configurazione Modulo | Mostra Barra di Scorrimento | `YES` | Mostra/nascondi la barra di scorrimento interna per i tweet. |
| Configurazione Modulo | Sfondo Trasparente | `YES` | Rendi trasparente lo sfondo del widget. |
| Configurazione Modulo | Mostra Risposte | `YES` | Includi/escludi le risposte nella timeline. |
| Configurazione Modulo | Riproduzione Automatica Video | `NO` | Riproduzione automatica dei video nei tweet. |
| Configurazione Modulo | Nascondi Barra di Scorrimento | `NO` | (Ridondante con Mostra Barra di Scorrimento) Mantieni NO. |
| Configurazione Modulo | Posiziona nell'hook | `displayRightColumn` | Dove il widget appare nel tuo negozio. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Il mio widget di Twitter non viene visualizzato nel mio negozio. Cosa devo fare?**
R:

1. **Controlla la configurazione:** Vai su **Moduli > Gestione moduli > Twitter widget free > Configura**. Assicurati di aver inserito il tuo "Nome utente Twitter" corretto e di aver salvato le impostazioni.
2. **Controlla il posizionamento dell'hook:** Verifica che l'impostazione "Posiziona nell'hook" sia impostata su un hook effettivamente renderizzato dal tuo tema (es. `displayRightColumn`). Alcuni temi potrebbero non visualizzare tutti gli hook standard.
3. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, la cache di PrestaShop impedisce la visualizzazione immediata dei nuovi contenuti del modulo.
4. **Compatibilità del tema:** Sebbene il modulo sia ampiamente compatibile, temi molto personalizzati potrebbero richiedere piccole modifiche. Se il problema persiste, contatta il supporto MyPresta.eu.

**D: Il widget appare, ma è vuoto o mostra un messaggio di errore.**
R:

1. **Nome utente errato:** Ricontrolla il tuo "Nome utente Twitter" nella configurazione del modulo. Anche un piccolo errore di battitura impedirà il recupero dei tweet.
2. **Account privato:** Assicurati che il tuo account Twitter sia pubblico. Il widget non può visualizzare tweet da account privati (protetti).
3. **Problemi API di Twitter:** Occasionalmente, potrebbero esserci problemi temporanei con l'API di Twitter. Attendi un po' e controlla di nuovo.

**D: Come posso cambiare la lingua del widget?**
R: Nella configurazione del modulo, trova l'impostazione "Lingua" e seleziona il codice lingua di due lettere appropriato (es. `fr` per il francese, `es` per lo spagnolo).

**D: Il widget appare troppo largo/stretto o troppo alto/basso.**
R:

1. **Larghezza:** Per un comportamento responsive, lascia vuota l'impostazione "Larghezza". Se hai impostato un valore in pixel specifico, prova a rimuoverlo.
2. **Altezza:** Regola l'impostazione "Altezza" (in pixel) per rendere il widget più alto o più basso.
3. **Limite Tweet:** Riduci il "Limite Tweet" per rendere il widget più corto se hai un'altezza fissa e vuoi visualizzare meno tweet.

**D: Posso visualizzare tweet da un hashtag o una lista specifica invece del mio account principale?**
R: Sì, ma questo richiede una configurazione avanzata. Dovresti creare un widget di timeline incorporato personalizzato direttamente sulla piattaforma per sviluppatori di Twitter (developer.twitter.com), configurarlo lì per mostrare un hashtag o una lista, e quindi ottenere l'unico "ID Widget" che fornisce. Dovresti quindi inserire questo "ID Widget" nella configurazione del modulo, lasciando vuoto il "Nome utente Twitter".

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Twitter widget free" è un modulo PrestaShop semplice progettato per integrare la funzionalità di timeline incorporata di Twitter. Sfrutta principalmente la struttura standard dei moduli di PrestaShop, utilizzando il file `index.php` principale sia per l'installazione/disinstallazione che per la configurazione (`getContent()`). Il modulo inietta un widget Twitter basato su JavaScript nel front-office utilizzando un template Smarty e un file CSS per lo stile di base. Si basa sul `widgets.js` di Twitter per il rendering della timeline, che viene caricato in modo asincrono.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. La visualizzazione del front-office del modulo è gestita interamente tramite hook e un template Smarty.
- **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

- Nessuna classe personalizzata o definizione di `ObjectModel` è presente in questo modulo. Tutta la logica è autocontenuta all'interno del file principale `twitterwidget/index.php`.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessun file JavaScript personalizzato è incluso direttamente nella directory `views/js/` del modulo.
- Il modulo si basa fortemente sullo script ufficiale `widgets.js` di Twitter, che viene caricato dinamicamente nel template del front-office (`rightcolumn.tpl`) per renderizzare la timeline incorporata. Questo script gestisce tutta la logica complessa di recupero e visualizzazione dei tweet.

### 4.5 Fogli di stile CSS (`views/css/`)

- `twitterwidget/twitterwidget.css`:
  - **Ambito**: Stile del cliente del front-office.
  - **Componenti UI principali e contenitori che stilizza**: Questo file contiene probabilmente uno stile minimo, principalmente per garantire che il widget di Twitter si integri bene con vari temi PrestaShop. Potrebbe includere regole per il contenitore `.twitter-widget`, reset di base o aggiustamenti responsive.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Gli sviluppatori possono ispezionare questo file per identificare selettori specifici (es. `.twitter-widget-container`, `.twitter-timeline`) e sovrascriverli nel `custom.css` o `theme.css` del loro tema per personalizzare ulteriormente l'aspetto del widget.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**:
  - `twitterwidget/rightcolumn.tpl`:
    - **Hook(s) renderizzati in**: Questo template è progettato per essere renderizzato in vari hook di visualizzazione, come configurato dal commerciante (es. `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayHeader`, `displayProductButtons`). I metodi `hookDisplay*` del modulo chiameranno questo template.
    - **Output del blocco visivo**: Questo template produce la struttura HTML richiesta per la timeline incorporata di Twitter. Tipicamente include un tag `<a>` con attributi `data-` (es. `data-tweet-limit`, `data-theme`, `data-link-color`, `data-border-color`, `data-height`, `data-width`, `data-lang`, `data-chrome`, `data-dnt`, `data-show-replies`, `data-autoplay`) che lo script `widgets.js` di Twitter legge per renderizzare la timeline. Include anche il tag `<script>` per caricare `widgets.js` in modo asincrono.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:
  - Questo modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi di configurazione standard di PrestaShop (es. `TWITTERWIDGET_USERNAME`, `TWITTERWIDGET_WIDGETID`, `TWITTERWIDGET_THEME`, ecc.).
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Potenzialmente utilizzato per caricare lo script del widget di Twitter globalmente, o per visualizzare il widget nell'area dell'intestazione. |
| `displayRightColumn` | Nella barra laterale destra delle pagine che ne hanno una. | Visualizza il widget di Twitter nella colonna destra. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine che ne hanno una. | Visualizza il widget di Twitter nella colonna sinistra. |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Visualizza il widget di Twitter nel piè di pagina. |
| `displayProductButtons` | Sulla pagina del prodotto, tipicamente vicino al pulsante "aggiungi al carrello" o alla descrizione del prodotto. | Visualizza il widget di Twitter sulle pagine del prodotto. |
| `actionFrontControllerSetMedia` | Dopo che il front controller ha impostato i suoi media, consentendo ai moduli di aggiungere i propri. | Utilizzato per registrare i file CSS e potenzialmente JS del modulo (anche se questo modulo carica il JS di Twitter direttamente nel TPL). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Twitter widget free", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere.
