---
title: "Feed di tag prodotto Instagram - Manuale commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Feed di tag prodotto Instagram di MyPresta.eu."
sidebar:
  label: "Feed di tag prodotto Instagram - Manuale commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Instagram product tag feed su MyPresta.eu](https://mypresta.eu/modules/social-networks/instagram-product-tag-feed.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/instagram-product-tag-feed/)
>
> ---


# Feed di tag prodotto Instagram

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per la comunicazione API, e sono quasi universalmente disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alle impostazioni del modulo, vai su **Moduli > Gestione moduli** nel tuo Back Office di PrestaShop, cerca "Feed di tag prodotto Instagram" e clicca sul pulsante "Configura".

Qui troverai le principali opzioni di configurazione per controllare come vengono visualizzati i tuoi feed Instagram.

#### Impostazioni generali

- **Token di accesso Instagram:**

  - **Cosa fa questa impostazione:** Questo è un codice univoco che concede al tuo negozio PrestaShop il permesso di accedere ai dati pubblici del tuo account Instagram (come le foto associate a tag specifici). Devi generare questo token dagli strumenti per sviluppatori di Instagram o da uno strumento di terze parti che semplifica il processo.
  - **Effetto della modifica di questa impostazione:**
    - *Se inserito correttamente:* Il tuo modulo sarà in grado di recuperare e visualizzare le foto di Instagram.
    - *Se errato o vuoto:* Il modulo non sarà in grado di connettersi a Instagram e non verranno visualizzate foto, con conseguente feed vuoto o messaggio di errore.
  - **Valore consigliato:** Il tuo token di accesso Instagram valido.
  - **Scenario/esempio del commerciante:** Hai appena configurato il tuo account Instagram Business. Dovrai seguire le istruzioni di Instagram (o utilizzare uno strumento di aiuto) per ottenere questo token e incollarlo qui. Senza di esso, il modulo non può "vedere" le tue foto di Instagram.
- **ID utente Instagram:**

  - **Cosa fa questa impostazione:** Questo è l'identificatore numerico univoco per il tuo account Instagram. È spesso richiesto insieme al token di accesso per recuperare correttamente i dati.
  - **Effetto della modifica di questa impostazione:**
    - *Se inserito correttamente:* Assicura che il modulo recuperi i dati dal tuo account Instagram specifico.
    - *Se errato o vuoto:* Potrebbe portare a errori nel recupero dei dati o al recupero dei dati dall'account sbagliato, con conseguente feed vuoto o errato.
  - **Valore consigliato:** Il tuo ID utente Instagram valido.
  - **Scenario/esempio del commerciante:** Similmente al token di accesso, otterrai questo ID quando configuri l'accesso all'API di Instagram. Indica al modulo *di chi* è il feed di Instagram da guardare.
- **Numero di foto da visualizzare:**

  - **Cosa fa questa impostazione:** Controlla quante foto di Instagram vengono recuperate e visualizzate in una singola istanza del feed.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su un numero più alto (es. 10):* Verranno caricate e potenzialmente mostrate più foto nel feed, rendendolo più ricco ma forse più lento da caricare.
    - *Se impostato su un numero più basso (es. 3):* Verranno visualizzate meno foto, con conseguente feed più conciso e tempi di caricamento più rapidi.
  - **Valore consigliato:** Inizia con 6-9 foto per un buon equilibrio tra contenuto e prestazioni. Regola in base al tuo layout e ai test di velocità della pagina.
  - **Scenario/esempio del commerciante:** Per una scheda della pagina prodotto, potresti volere 6 foto. Per un carosello della homepage, potresti volerne 12 per dare più varietà mentre gli utenti scorrono.
- **Visualizza sulla Homepage:**

  - **Cosa fa questa impostazione:** Un semplice interruttore per abilitare o disabilitare il feed Instagram sulla homepage del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo tenterà di visualizzare un feed Instagram sulla tua homepage (solitamente tramite l'hook `displayHome`).
    - *Quando disabilitato:* Nessun feed Instagram apparirà sulla tua homepage.
  - **Valore consigliato:** SÌ, se vuoi mostrare in modo prominente i tuoi contenuti Instagram. NO, se preferisci una homepage più pulita o vuoi solo i feed sulle pagine prodotto.
  - **Scenario/esempio del commerciante:** Vuoi mostrare i tuoi ultimi scatti lifestyle sulla homepage per coinvolgere immediatamente i visitatori. Abiliteresti questa opzione.
- **Visualizza sulla Pagina Prodotto:**

  - **Cosa fa questa impostazione:** Un semplice interruttore per abilitare o disabilitare il feed Instagram sulle singole pagine prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo tenterà di visualizzare un feed Instagram specifico per il prodotto sulle tue pagine prodotto (solitamente tramite gli hook `displayProductTab` o `displayProductExtraContent`).
    - *Quando disabilitato:* Nessun feed Instagram apparirà sulle pagine prodotto.
  - **Valore consigliato:** SÌ, poiché questa è una delle funzionalità principali del modulo e un potente strumento di conversione.
  - **Scenario/esempio del commerciante:** Vendi scarpe e vuoi mostrare foto Instagram di persone che indossano *quel modello specifico di scarpa* sulla sua pagina prodotto. Abiliteresti questa opzione.
- **Visualizza nella Colonna Sinistra:**

  - **Cosa fa questa impostazione:** Controlla se il feed Instagram appare nella colonna laterale sinistra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un feed verrà renderizzato nella colonna sinistra sulle pagine in cui è agganciato.
    - *Quando disabilitato:* Nessun feed nella colonna sinistra.
  - **Valore consigliato:** NO, a meno che tu non abbia un'esigenza di design molto specifica. Le colonne possono diventare ingombre.
  - **Scenario/esempio del commerciante:** Vuoi un piccolo feed persistente visibile mentre i clienti navigano tra le categorie.
- **Visualizza nella Colonna Destra:**

  - **Cosa fa questa impostazione:** Controlla se il feed Instagram appare nella colonna laterale destra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un feed verrà renderizzato nella colonna destra sulle pagine in cui è agganciato.
    - *Quando disabilitato:* Nessun feed nella colonna destra.
  - **Valore consigliato:** NO, a meno che tu non abbia un'esigenza di design molto specifica. Le colonne possono diventare ingombre.
  - **Scenario/esempio del commerciante:** Simile alla colonna sinistra, per un feed persistente e più piccolo.
- **Visualizza nel Footer:**

  - **Cosa fa questa impostazione:** Controlla se il feed Instagram appare nell'area del footer del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un feed verrà renderizzato nel footer.
    - *Quando disabilitato:* Nessun feed nel footer.
  - **Valore consigliato:** SÌ, per un modo discreto ma efficace di mostrare il tuo Instagram. È meno invasivo delle colonne.
  - **Scenario/esempio del commerciante:** Vuoi aggiungere una sezione visivamente accattivante nella parte inferiore di ogni pagina, incoraggiando i visitatori a esplorare il tuo Instagram.
- **Visualizza nell'Header (Sinistra):**

  - **Cosa fa questa impostazione:** Controlla se il feed Instagram appare nella parte sinistra dell'header del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un feed verrà renderizzato nella sezione sinistra dell'header.
    - *Quando disabilitato:* Nessun feed nell'header.
  - **Valore consigliato:** NO, tipicamente gli header sono riservati alla navigazione e al branding.
  - **Scenario/esempio del commerciante:** Design molto specifico in cui si desidera una piccola icona Instagram rotante o una singola immagine nell'header.
- **Visualizza nell'Header (Destra):**

  - **Cosa fa questa impostazione:** Controlla se il feed Instagram appare nella parte destra dell'header del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un feed verrà renderizzato nella sezione destra dell'header.
    - *Quando disabilitato:* Nessun feed nell'header.
  - **Valore consigliato:** NO, tipicamente gli header sono riservati alla navigazione e al branding.
  - **Scenario/esempio del commerciante:** Simile all'Header (Sinistra).
- **Funzione Carosello:**

  - **Cosa fa questa impostazione:** Abilita o disabilita la funzionalità carosello (galleria scorrevole) per i feed Instagram.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Le foto verranno visualizzate in un carosello orizzontale e scorrevole, risparmiando spazio e consentendo agli utenti di sfogliare facilmente molte immagini.
    - *Quando disabilitato:* Le foto verranno probabilmente visualizzate in una griglia statica o in un elenco, a seconda del template.
  - **Valore consigliato:** SÌ, per la maggior parte dei posizionamenti (homepage, pagina prodotto) in quanto è efficiente in termini di spazio e coinvolgente.
  - **Scenario/esempio del commerciante:** Hai 9 foto per un prodotto, ma spazio solo per 3 alla volta. L'abilitazione del carosello consente ai clienti di scorrere tutte le 9.
- **Funzione Fancybox:**

  - **Cosa fa questa impostazione:** Abilita o disabilita l'effetto "Fancybox", che è una popolare libreria JavaScript che visualizza le immagini in un elegante popup sovrapposto quando vengono cliccate.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Cliccando su una foto di Instagram nel feed, questa si aprirà in una grande ed elegante finestra popup, consentendo ai clienti di visualizzare i dettagli senza lasciare la pagina.
    - *Quando disabilitato:* Cliccando su un'immagine, questa potrebbe aprirsi direttamente in una nuova scheda del browser o semplicemente non fare nulla, a seconda del tema.
  - **Valore consigliato:** SÌ, in quanto offre un'esperienza utente molto migliore per la visualizzazione delle immagini.
  - **Scenario/esempio del commerciante:** Un cliente vede un ottimo outfit su Instagram nel tuo feed. Cliccandoci sopra si apre una visualizzazione grande e chiara della foto, rendendo più facile apprezzare i dettagli.

#### Impostazioni specifiche della pagina prodotto (scheda Back Office prodotto)

Dopo aver installato il modulo, troverai un nuovo campo o una nuova scheda quando modifichi un prodotto nel tuo Back Office di PrestaShop:

- **Hashtag Instagram (per prodotto):**
  - **Cosa fa questa impostazione:** Questo campo ti consente di specificare un hashtag Instagram univoco per ogni singolo prodotto. Il modulo utilizzerà quindi questo hashtag per recuperare le foto pertinenti dal tuo account Instagram.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene inserito un hashtag (es. #nomedelprodotto):* Il feed Instagram su quella specifica pagina prodotto visualizzerà le foto dal tuo account Instagram che sono taggate con `#nomedelprodotto`.
    - *Se lasciato vuoto:* Nessun feed Instagram specifico per il prodotto verrà visualizzato per quel prodotto, anche se "Visualizza sulla Pagina Prodotto" è abilitato.
  - **Valore consigliato:** Un hashtag univoco e descrittivo per ogni prodotto. Assicurati di utilizzare costantemente questo hashtag nei tuoi post di Instagram.
  - **Scenario/esempio del commerciante:** Per un prodotto chiamato "Abito Brezza Estiva", potresti inserire `#AbitoBrezzaEstiva` o `#MioBrandAbitoEstivo`. Quindi, quando pubblichi foto di questo abito su Instagram, includi quell'hashtag. Il modulo quindi preleverà quelle foto sulla pagina prodotto dell'abito.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Config. Modulo | Token di accesso Instagram | Il tuo token valido | Si connette all'API di Instagram per recuperare le foto. **CRITICO.** |
| Config. Modulo | ID utente Instagram | Il tuo ID utente valido | Identifica il tuo account Instagram per il recupero dei dati. |
| Config. Modulo | Numero di foto da visualizzare | 6-9 | Controlla quante foto vengono mostrate in un'istanza del feed. |
| Config. Modulo | Visualizza sulla Homepage | SÌ | Mostra un feed generale sulla homepage del tuo negozio. |
| Config. Modulo | Visualizza sulla Pagina Prodotto | SÌ | Mostra un feed specifico per il prodotto sulle pagine prodotto. |
| Config. Modulo | Visualizza nella Colonna Sinistra | NO | Mostra un feed nella barra laterale sinistra. Può ingombrare il layout. |
| Config. Modulo | Visualizza nella Colonna Destra | NO | Mostra un feed nella barra laterale destra. Può ingombrare il layout. |
| Config. Modulo | Visualizza nel Footer | SÌ | Mostra un feed nel footer del negozio. Ottimo per una promozione discreta. |
| Config. Modulo | Visualizza nell'Header (Sinistra) | NO | Mostra un feed nell'header sinistro. Generalmente non consigliato. |
| Config. Modulo | Visualizza nell'Header (Destra) | NO | Mostra un feed nell'header destro. Generalmente non consigliato. |
| Config. Modulo | Funzione Carosello | SÌ | Visualizza le foto in una galleria scorrevole, risparmiando spazio. |
| Config. Modulo | Funzione Fancybox | SÌ | Apre le foto in un elegante popup per una migliore visualizzazione. |
| Pagina Modifica Prodotto | Hashtag Instagram | Unico per prodotto | Definisce l'hashtag per recuperare le foto per *questo specifico prodotto*. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il mio feed Instagram non mostra alcuna foto. Cosa devo fare?**
R:

1.  **Controlla il tuo token di accesso Instagram e l'ID utente:** Questi sono i colpevoli più comuni. Assicurati che siano inseriti correttamente nella configurazione del modulo e che siano ancora validi. I token di Instagram possono scadere, quindi potresti doverli rigenerare.
2.  **Verifica gli hashtag:** Per le pagine prodotto, assicurati che il campo "Hashtag Instagram" sia compilato per il prodotto specifico e che tu abbia effettivamente post su Instagram che utilizzano esattamente quell'hashtag.
3.  **Account pubblico:** Assicurati che il tuo account Instagram sia pubblico. Il modulo non può recuperare foto da account privati.
4.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e svuota la cache di Smarty (e, facoltativamente, tutte le cache). A volte i vecchi dati memorizzati nella cache impediscono la visualizzazione di nuovi contenuti.
5.  **Verifica i limiti API:** Instagram ha limiti di frequenza API. Se stai recuperando troppo frequentemente o hai un numero molto elevato di prodotti, potresti raggiungere temporaneamente questi limiti.

**D: Le immagini vengono visualizzate, ma sembrano strane o rompono il layout del mio tema.**
R:

1.  **Conflitti del tema:** Il tuo tema PrestaShop personalizzato potrebbe avere stili CSS in conflitto. Questo è un problema comune con i moduli di terze parti.
2.  **CSS del modulo:** Il modulo include il proprio CSS (`instagramfeed/css/css.css`, `instagramfeed/lib/src/css/lightslider.css`). Il tuo webmaster o sviluppatore può ispezionare la pagina per identificare gli stili in conflitto e scrivere override CSS personalizzati nel foglio di stile del tuo tema.
3.  **Dimensioni dell'immagine:** Assicurati che le immagini che pubblichi su Instagram siano di qualità e proporzioni ragionevoli. Sebbene il modulo cerchi di adattarsi, immagini estremamente larghe o alte potrebbero causare problemi di visualizzazione.

**D: Come ottengo un token di accesso e un ID utente Instagram?**
R: L'accesso all'API di Instagram è cambiato nel tempo. In genere, hai bisogno di un account Instagram Business e di un account sviluppatore Facebook. Il processo prevede la creazione di un'app Facebook, la connessione al tuo account Instagram Business e quindi la generazione di un token. Esistono anche strumenti di terze parti (cerca "Generatore di token di accesso Instagram") che possono semplificare questo processo, ma usa sempre quelli affidabili.

**D: Posso visualizzare feed diversi su pagine diverse (ad esempio, un feed generale sulla homepage e feed specifici per i prodotti)?**
R: Sì, assolutamente! Questa è la funzionalità principale. Usa l'impostazione "Visualizza sulla Homepage" per un feed generale (che in genere preleverà da un hashtag predefinito o dal tuo feed utente principale), e poi usa il campo "Hashtag Instagram" sulle singole pagine prodotto per i feed specifici per i prodotti.

**D: Il carosello o Fancybox non funziona.**
R:

1.  **Abilita le funzionalità:** Ricontrolla che "Funzione Carosello" e "Funzione Fancybox" siano abilitate nella configurazione del modulo.
2.  **Conflitti JavaScript:** Un altro modulo o il tuo tema potrebbero caricare librerie JavaScript in conflitto (ad esempio, un altro script carosello o lightbox). Il tuo webmaster dovrebbe eseguire il debug di questo utilizzando la console per sviluppatori del browser (cerca errori JavaScript).
3.  **jQuery:** Assicurati che jQuery sia caricato correttamente nel tuo negozio, poiché molte funzionalità JavaScript dipendono da esso.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente riservata a sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Feed di tag prodotto Instagram` segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` per la configurazione e il sistema `Hook` per la visualizzazione nel front-office. Integra una classe personalizzata per l'interazione con l'API di Instagram e utilizza librerie JavaScript esterne (lightslider, fancybox) per migliorare l'UI/UX. La logica principale del modulo risiede nel suo file `index.php` principale, che gestisce la configurazione, l'installazione e la registrazione degli hook. Il rendering del front-office è ottenuto passando i dati ai template Smarty registrati a vari hook di visualizzazione.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene controller dedicati per il front-office o il back-office. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo, e la visualizzazione nel front-office è gestita direttamente tramite gli hook registrati.

### 4.3 Classi e modelli principali (`classes/`)

- `instagramfeed/classes/index.php`:

  - Questo è tipicamente un file vuoto o un file contenente `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` per impedire la visualizzazione diretta della directory. Non contiene alcuna logica di classe funzionale.
- `instagramfeed/classes/instagram_class.php`:

  - **Nome classe**: `Instagram`
  - **Classe genitore**: Nessuna (classe utility autonoma)
  - **Responsabilità**: Questa classe incapsula la logica per interagire con l'API di Instagram. È responsabile di effettuare richieste HTTP per recuperare i media in base all'ID utente e agli hashtag, gestire i token di accesso e analizzare le risposte JSON da Instagram.
  - **Metodi pubblici chiave**:
    - `__construct($access_token, $user_id)`: Costruttore, inizializza con il token di accesso Instagram e l'ID utente.
    - `getMediaByHashtag($hashtag, $count)`: Recupera un numero specificato di elementi multimediali dall'API di Instagram che sono taggati con l'hashtag dato e associati all'ID utente configurato. Restituisce un array di oggetti multimediali.
    - `getMediaByUser($count)`: Recupera un numero specificato di elementi multimediali direttamente dal feed dell'utente (se supportato dalla versione API e dallo scope del token).
    - (Potenzialmente altri metodi di supporto per chiamate API, gestione degli errori, ecc.)

### 4.4 Risorse JavaScript (`views/js/`)

- `instagramfeed/js/if_carousell.js`:
  - **Ambito**: Front-office.
  - **Descrizione**: Questo script probabilmente inizializza e configura la funzionalità carosello `lightslider` per i feed Instagram. Si lega a specifici elementi DOM (ad esempio, `ul` con una certa classe) e applica il comportamento del carosello, incluse le impostazioni per la reattività, l'auto-play, la navigazione, ecc.
  - **Dipendenze**: Si basa su `lightslider.js` e jQuery.
- `instagramfeed/js/if_fancybox.js`:
  - **Ambito**: Front-office.
  - **Descrizione**: Questo script inizializza e configura la funzionalità lightbox Fancybox. Si rivolge ai link delle immagini all'interno del feed Instagram (ad esempio, tag `a` che avvolgono tag `img`) e li abilita ad aprirsi in un popup Fancybox quando vengono cliccati, fornendo una visualizzazione più grande e immersiva dell'immagine.
  - **Dipendenze**: Si basa sulla libreria Fancybox (non inclusa in questo modulo, ma si prevede che venga caricata dal tema o da un altro modulo) e jQuery.
- `instagramfeed/js/if_sliding.js`:
  - **Ambito**: Front-office.
  - **Descrizione**: Questo file potrebbe essere uno script alternativo o supplementare per la funzionalità di scorrimento, possibilmente per versioni precedenti di PrestaShop o layout specifici. Dato `if_carousell.js` e `lightslider.js`, potrebbe essere uno script legacy o un wrapper per comportamenti di scorrimento specifici non coperti dal carosello principale.
  - **Dipendenze**: Probabilmente jQuery.
- `instagramfeed/js/ps14.js`:
  - **Ambito**: Front-office (specificamente per la compatibilità con PrestaShop 1.4).
  - **Descrizione**: Questo script probabilmente contiene correzioni di compatibilità o polyfill per ambienti PrestaShop 1.4 più vecchi, affrontando potenziali differenze JavaScript o versioni/funzionalità jQuery mancanti rispetto alle versioni più recenti di PrestaShop.
  - **Dipendenze**: jQuery.
- `instagramfeed/lib/src/js/lightslider.js`:
  - **Ambito**: Front-office.
  - **Descrizione**: Questa è la libreria plugin jQuery `lightslider` principale. Fornisce la funzionalità per creare caroselli e slider di contenuti reattivi e abilitati al tocco. `if_carousell.js` tipicamente chiamerebbe i metodi di questa libreria.
  - **Dipendenze**: jQuery.

### 4.5 Fogli di stile CSS (`views/css/`)

- `instagramfeed/css/css.css`:
  - **Ambito**: Stile del cliente del front-office.
  - **Descrizione**: Contiene regole CSS personalizzate specifiche per il layout del feed Instagram, il dimensionamento delle immagini, la spaziatura e l'aspetto generale all'interno dei vari hook. Definisce le classi per il contenitore del feed, i singoli elementi immagine e potenzialmente didascalie o link.
  - **Selettori di classe CSS chiave**: Gli sviluppatori possono ispezionare l'HTML generato per trovare classi come `.instagram-feed-container`, `.instagram-item`, `.instagram-image`, ecc., che possono essere sovrascritte nel `custom.css` o `theme.css` del tema.
- `instagramfeed/lib/src/css/lightslider.css`:
  - **Ambito**: Stile del cliente del front-office.
  - **Descrizione**: Questo è il foglio di stile predefinito per il plugin jQuery `lightslider`. Fornisce lo stile essenziale per le frecce di navigazione del carosello, i punti di paginazione, le transizioni delle diapositive e il comportamento reattivo.
  - **Selettori di classe CSS chiave**: Classi come `.lightSlider`, `.lSAction`, `.lSPager`, ecc., che possono essere personalizzate per corrispondere al branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template di amministrazione (`views/templates/admin/`)**:

  - `instagramfeed/views/templates/admin/instagram_feed.tpl`: Questo template viene renderizzato dal metodo `getContent()` nel file principale del modulo. Visualizza il modulo di configurazione del back-office, inclusi i campi di input per il token di accesso Instagram, l'ID utente, il numero di foto e vari interruttori di visualizzazione (homepage, pagina prodotto, colonne, piè di pagina, intestazione, carosello, fancybox). Tipicamente utilizza i componenti del modulo di aiuto di PrestaShop.
- **Template degli hook (`views/templates/hook/`)**:

  - `instagramfeed/views/templates/hook/column-feed.tpl`: Renderizza il feed Instagram quando agganciato a `displayLeftColumn` o `displayRightColumn`. Tipicamente visualizza una versione più compatta del feed.
  - `instagramfeed/views/templates/hook/feed.tpl`: Un template di feed generico, probabilmente utilizzato per la visualizzazione principale della homepage o del piè di pagina. Contiene la struttura principale per la visualizzazione delle immagini di Instagram, potenzialmente avvolte in un contenitore carosello.
  - `instagramfeed/views/templates/hook/header-left.tpl`: Renderizza il feed quando agganciato a `displayHeaderLeft`.
  - `instagramfeed/views/templates/hook/header-right.tpl`: Renderizza il feed quando agganciato a `displayHeaderRight`.
  - `instagramfeed/views/templates/hook/homepage-feed.tpl`: Specificamente progettato per l'hook `displayHome`, spesso presenta un layout più prominente o più ampio per la homepage.
  - `instagramfeed/views/templates/hook/tab.tpl`: Renderizza il titolo della scheda per il feed Instagram sulla pagina prodotto (ad esempio, "Foto Instagram"). Questo è tipicamente agganciato a `displayProductTab` (PrestaShop 1.6) o `displayProductExtraContent` (PrestaShop 1.7+).
  - `instagramfeed/views/templates/hook/tabcontents.tpl`: Renderizza il contenuto effettivo del feed Instagram all'interno della scheda della pagina prodotto. Questo template conterrà la logica per visualizzare le immagini recuperate utilizzando l'hashtag specifico del prodotto, spesso utilizzando le funzionalità carosello e fancybox.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione (Token di accesso, ID utente, opzioni di visualizzazione, ecc.) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `INSTAGRAMFEED_ACCESS_TOKEN`, `INSTAGRAMFEED_USER_ID`, `INSTAGRAMFEED_NUM_PHOTOS`, ecc.
  - L'hashtag Instagram specifico del prodotto è memorizzato nella tabella `ps_product_lang` (o una tabella simile relativa al prodotto) come nuovo campo aggiunto dal modulo durante l'installazione. Questo campo sarebbe tipicamente chiamato `instagram_hashtag` o simile.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per caricare risorse CSS e JavaScript (lightslider, fancybox, script personalizzati) richieste per i feed Instagram. |
| `displayHome` | Sulla homepage del negozio. | Renderizza il feed Instagram generale sulla homepage. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine in cui è abilitato. | Renderizza un feed Instagram compatto nella colonna sinistra. |
| `displayRightColumn` | Nella barra laterale destra delle pagine in cui è abilitato. | Renderizza un feed Instagram compatto nella colonna destra. |
| `displayFooter` | Nella sezione del piè di pagina del negozio. | Renderizza un feed Instagram generale nel piè di pagina. |
| `displayHeaderLeft` | Nella parte sinistra dell'intestazione del negozio. | Renderizza un piccolo feed Instagram nell'intestazione. |
| `displayHeaderRight` | Nella parte destra dell'intestazione del negozio. | Renderizza un piccolo feed Instagram nell'intestazione. |
| `displayProductTab` (PS 1.6) | Sulla pagina prodotto, per aggiungere nuove schede. | Renderizza il titolo della scheda del feed Instagram sulla pagina prodotto. |
| `displayProductTabContent` (PS 1.6) | Sulla pagina prodotto, per aggiungere contenuto alle schede. | Renderizza il contenuto (il feed Instagram effettivo) all'interno della scheda della pagina prodotto. |
| `displayProductExtraContent` (PS 1.7+) | Sulla pagina prodotto, per aggiungere blocchi di contenuto extra. | Hook alternativo per PrestaShop 1.7+ per visualizzare il feed Instagram sulle pagine prodotto, spesso come un nuovo blocco sotto le informazioni principali del prodotto. |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Utilizzato per salvare il valore del campo `instagram_hashtag` per il prodotto. |
| `actionProductAdd` | Dopo l'aggiunta di un nuovo prodotto nel Back Office. | Utilizzato per salvare il valore del campo `instagram_hashtag` per il nuovo prodotto. |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office. | Renderizza il campo di input per l'"Hashtag Instagram" nella pagina di configurazione del prodotto. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza e garantire che il tuo modulo funzioni in modo ottimale.
