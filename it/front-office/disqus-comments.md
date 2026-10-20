---
title: "Commenti DISQUS - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop DISQUS comments di MyPresta.eu."
sidebar:
  label: "Commenti DISQUS - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo DISQUS comments su MyPresta.eu](https://mypresta.eu/modules/front-office-features/disqus-comments.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/disqus-comments/)
>
> ---


# Commenti DISQUS

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop e per la comunicazione con servizi esterni come Disqus.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Commenti DISQUS)

Questa è la schermata di configurazione principale dove imposterai come Disqus si integra con il tuo negozio.

#### **1. Nome breve del sito (Site shortname)**

-   **Cosa fa questa impostazione:** Questo è l'identificatore unico per il tuo sito web Disqus. Lo ottieni dal tuo account Disqus quando registri il tuo sito web. Indica a Disqus quali thread di commenti appartengono al tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato correttamente:* I commenti Disqus verranno caricati e salvati correttamente per i tuoi prodotti.
    -   *Se errato o vuoto:* Disqus non sarà in grado di caricare i commenti, o potrebbe caricare commenti da un sito diverso, portando a errori o commenti mancanti.
-   **Valore consigliato:** Il tuo nome breve Disqus unico (es. `iltuonomenegozio`).
-   **Scenario / esempio per il commerciante:** Se hai registrato il tuo sito web su Disqus come "Il Mio Fantastico Negozio", il tuo nome breve potrebbe essere "il miofantasticonegozio". Inserisci esattamente quella stringa qui.

#### **2. Posizione del widget dei commenti (Comments widget position)**

-   **Cosa fa questa impostazione:** Controlla dove appare la sezione principale dei commenti Disqus sulle pagine dei tuoi prodotti.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su "Sezione Scheda Prodotto":* I commenti appariranno in una nuova scheda sulla pagina del prodotto (es. accanto a "Descrizione" o "Scheda tecnica"). I clienti cliccano sulla scheda per vedere i commenti.
    -   *Se impostato su "Sezione Footer Prodotto":* I commenti appariranno in fondo alla pagina del prodotto, sotto le informazioni principali del prodotto. I clienti li vedranno scorrendo verso il basso.
-   **Valore consigliato:** "Sezione Scheda Prodotto" per un layout più pulito della pagina del prodotto, o "Sezione Footer Prodotto" se vuoi che i commenti siano immediatamente visibili senza cliccare su una scheda.
-   **Scenario / esempio per il commerciante:** Se le tue pagine di prodotto sono già molto lunghe, inserire i commenti in una scheda mantiene la visualizzazione iniziale ordinata. Se vuoi enfatizzare il feedback dei clienti, posizionarli nel footer li rende più prominenti.

#### **3. Pagina delle testimonianze (Testimonials page)**

-   **Cosa fa questa impostazione:** Abilita o disabilita una pagina dedicata sul tuo negozio che aggrega tutti i commenti Disqus da tutti i tuoi prodotti.
-   **Effetto della modifica di questa impostazione:**
    -   *Se "Abilitato":* Verrà creata una nuova pagina a un URL come `iltuonegozio.com/testimonials` (o simile, a seconda dei tuoi URL amichevoli) che mostra tutti i commenti.
    -   *Se "Disabilitato":* Nessuna pagina di questo tipo sarà disponibile.
-   **Valore consigliato:** "Abilitato" per fornire un hub centrale per il feedback dei clienti.
-   **Scenario / esempio per il commerciante:** Abilitando questa opzione puoi collegare una pagina "Recensioni Clienti" o "Cosa dicono i nostri clienti" dal tuo footer, mostrando tutti i feedback positivi in un unico posto.

#### **4. Aspetto del link alle testimonianze (Testimonials link appearance)**

-   **Cosa fa questa impostazione:** Se la "Pagina delle testimonianze" è abilitata, controlla dove appare un link a quella pagina nel layout del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Se "Nascondi":* La pagina delle testimonianze esisterà, ma nessun link automatico verrà aggiunto dal modulo. Dovresti aggiungere manualmente un link (es. nel menu del footer del tuo tema).
    -   *Se "Colonna sinistra":* Un link alla pagina delle testimonianze apparirà nella colonna sinistra del tuo negozio.
    -   *Se "Colonna destra":* Un link alla pagina delle testimonianze apparirà nella colonna destra del tuo negozio.
-   **Valore consigliato:** "Colonna destra" o "Colonna sinistra" per rendere la pagina delle testimonianze facilmente scopribile.
-   **Scenario / esempio per il commerciante:** Se il tuo negozio utilizza una colonna sinistra per le categorie, posizionare il link alle testimonianze nella colonna destra potrebbe essere più appropriato.

#### **5. Commenti recenti nella homepage (Homepage recent comments)**

-   **Cosa fa questa impostazione:** Controlla se un blocco che mostra i commenti Disqus più recenti appare sulla homepage del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Se "Abilitato":* Un blocco con i commenti recenti verrà visualizzato sulla tua homepage.
    -   *Se "Disabilitato":* Nessun blocco di commenti recenti apparirà sulla homepage.
-   **Valore consigliato:** "Abilitato" per mantenere la tua homepage dinamica e evidenziare l'attività recente dei clienti.
-   **Scenario / esempio per il commerciante:** Mostrare i commenti recenti sulla homepage può incoraggiare i visitatori a esplorare prodotti che hanno discussioni attive, portando potenzialmente a più vendite.

#### **6. Commenti recenti nella colonna destra (Right column recent comments)**

-   **Cosa fa questa impostazione:** Controlla se un blocco che mostra i commenti Disqus più recenti appare nella colonna destra del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Se "Abilitato":* Un blocco con i commenti recenti verrà visualizzato nella colonna destra sulle pagine in cui la colonna destra è attiva.
    -   *Se "Disabilitato":* Nessun blocco di commenti recenti apparirà nella colonna destra.
-   **Valore consigliato:** "Abilitato" per mantenere l'engagement in tutto il tuo sito.
-   **Scenario / esempio per il commerciante:** Se il tuo negozio ha una colonna destra, visualizzare i commenti recenti lì può fornire un flusso costante di contenuti freschi e incoraggiare l'esplorazione.

#### **7. Commenti recenti nella colonna sinistra (Left column recent comments)**

-   **Cosa fa questa impostazione:** Controlla se un blocco che mostra i commenti Disqus più recenti appare nella colonna sinistra del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Se "Abilitato":* Un blocco con i commenti recenti verrà visualizzato nella colonna sinistra sulle pagine in cui la colonna sinistra è attiva.
    -   *Se "Disabilitato":* Nessun blocco di commenti recenti apparirà nella colonna sinistra.
-   **Valore consigliato:** "Abilitato" per mantenere l'engagement in tutto il tuo sito.
-   **Scenario / esempio per il commerciante:** Similmente alla colonna destra, utilizzare la colonna sinistra per i commenti recenti può essere efficace se il tuo tema utilizza principalmente la colonna sinistra per la navigazione o altri blocchi.

#### **8. Mostra Disqus solo agli utenti loggati che hanno acquistato il prodotto (Show disqus only for logged users that purchased product)**

-   **Cosa fa questa impostazione:** Questa è un'impostazione potente per limitare chi può vedere e interagire con i commenti Disqus sulle pagine dei prodotti.
-   **Effetto della modifica di questa impostazione:**
    -   *Se "Abilitato":* Solo i clienti che sono loggati nel loro account E hanno precedentemente acquistato il prodotto specifico vedranno la sezione dei commenti Disqus. Tutti gli altri visitatori non la vedranno.
    -   *Se "Disabilitato":* Tutti i visitatori (loggati o ospiti, acquirenti o meno) vedranno la sezione dei commenti Disqus.
-   **Valore consigliato:** "Disabilitato" per il massimo engagement e benefici SEO. "Abilitato" se vuoi assicurarti che solo gli acquirenti verificati possano commentare, il che può aumentare la credibilità delle recensioni ma ridurre il volume dei commenti.
-   **Scenario / esempio per il commerciante:** Se stai avendo problemi con spam o commenti irrilevanti, abilitare questa opzione può filtrare i non acquirenti. Tuttavia, se il tuo obiettivo è una discussione ampia e la SEO, mantienila disabilitata.

#### **9. Quanti commenti recenti mostrare? (How many recent comments to show?)**

-   **Cosa fa questa impostazione:** Determina il numero di commenti recenti visualizzati nei blocchi "Commenti Recenti" (sulla homepage, colonna sinistra o destra).
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su un numero (es. 5):* I blocchi visualizzeranno quel numero di commenti più recenti.
    -   *Se impostato su 0 o vuoto:* Nessun commento recente verrà visualizzato nei blocchi, anche se i blocchi sono abilitati.
-   **Valore consigliato:** Da 3 a 5 commenti per un blocco compatto, o fino a 10 per una visualizzazione più prominente.
-   **Scenario / esempio per il commerciante:** Mostrare 5 commenti fornisce un buon equilibrio tra la visualizzazione dell'attività e il non rendere il blocco troppo lungo.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Nome breve del sito | Il tuo nome breve Disqus | Identificatore unico per il tuo account Disqus; essenziale per il caricamento dei commenti. |
| Configurazione Modulo | Posizione del widget dei commenti | Sezione Scheda Prodotto | Dove appare la sezione principale dei commenti sulle pagine dei prodotti (scheda o footer). |
| Configurazione Modulo | Pagina delle testimonianze | Abilitato | Crea una pagina dedicata che aggrega tutti i commenti. |
| Configurazione Modulo | Aspetto del link alle testimonianze | Colonna destra | Dove appare un link alla pagina delle testimonianze (se abilitato). |
| Configurazione Modulo | Commenti recenti nella homepage | Abilitato | Visualizza un blocco di commenti recenti sulla homepage. |
| Configurazione Modulo | Commenti recenti nella colonna destra | Abilitato | Visualizza un blocco di commenti recenti nella colonna destra. |
| Configurazione Modulo | Commenti recenti nella colonna sinistra | Abilitato | Visualizza un blocco di commenti recenti nella colonna sinistra. |
| Configurazione Modulo | Mostra Disqus solo agli utenti loggati che hanno acquistato il prodotto | Disabilitato | Limita la visibilità/interazione dei commenti agli acquirenti verificati. |
| Configurazione Modulo | Quanti commenti recenti mostrare? | 5 | Numero di commenti da visualizzare nei blocchi dei commenti recenti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei commenti Disqus non appaiono sulle pagine dei prodotti. Cosa devo fare?**

-   **R:** Innanzitutto, ricontrolla il tuo "Nome breve del sito" nella configurazione del modulo. Deve corrispondere esattamente al nome breve del tuo account Disqus. Inoltre, assicurati di aver impostato "Posizione del widget dei commenti" su "Sezione Scheda Prodotto" o "Sezione Footer Prodotto". Infine, svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota cache) e la cache del tuo browser.

**D2: I blocchi "Commenti Recenti" non vengono visualizzati nelle mie colonne/homepage.**

-   **R:** Verifica di aver abilitato "Commenti recenti nella homepage", "Commenti recenti nella colonna destra" o "Commenti recenti nella colonna sinistra" nella configurazione del modulo. Inoltre, assicurati che "Quanti commenti recenti mostrare?" sia impostato su un numero maggiore di 0. Se il tuo tema non visualizza le colonne sinistra/destra su determinate pagine, i blocchi non appariranno lì. Svuota la cache dopo aver apportato modifiche.

**D3: Ho abilitato la "Pagina delle testimonianze", ma non riesco a trovare un link ad essa.**

-   **R:** Se hai impostato "Aspetto del link alle testimonianze" su "Nascondi", il modulo non aggiungerà automaticamente un link. Dovrai aggiungere manualmente un link alla pagina (es. nel menu del footer del tuo tema). L'URL per la pagina delle testimonianze è tipicamente `iltuonegozio.com/module/disqus/testimonials` (o una versione URL amichevole se abilitata). Se hai scelto "Colonna sinistra" o "Colonna destra", assicurati che quelle colonne siano attive sulle pagine che stai visualizzando.

**D4: Solo alcuni utenti possono vedere i commenti, o non riesco a vederli come ospite.**

-   **R:** Controlla l'impostazione "Mostra Disqus solo agli utenti loggati che hanno acquistato il prodotto". Se questa è abilitata, solo i clienti loggati che hanno acquistato il prodotto specifico vedranno i commenti. Disabilita questa impostazione se vuoi che tutti i visitatori vedano e interagiscano con i commenti.

**D5: Lo stile del mio tema personalizzato è in conflitto con i commenti Disqus.**

-   **R:** Il widget Disqus stesso è in gran parte autonomo e stilizzato da Disqus. Tuttavia, il contenitore o la scheda che contiene il widget potrebbe essere influenzato dal CSS del tuo tema. Potrebbe essere necessario un web developer per ispezionare gli elementi utilizzando gli strumenti per sviluppatori del browser e aggiungere CSS personalizzato al tuo tema per regolare la spaziatura, i font o i colori attorno al widget Disqus.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo DISQUS comments per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo DISQUS comments segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente gli hook per la visualizzazione nel front-office e un metodo `getContent()` per la configurazione nel back-office. Integra dinamicamente il codice di incorporamento universale di Disqus. Il modulo utilizza un controller frontale personalizzato per la pagina delle testimonianze e un altro per le chiamate AJAX (anche se attualmente il controller AJAX sembra essere un segnaposto o non è ampiamente utilizzato per la funzionalità principale di Disqus). La configurazione è memorizzata in `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/index.php`
        -   **Nome classe:** `DisqusIndexModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità:** Questo controller è probabilmente un valore predefinito o di fallback per il routing del front-office del modulo. Nel contesto di Disqus, potrebbe essere utilizzato per azioni front-end generali relative al modulo, anche se l'incorporamento principale di Disqus è solitamente gestito tramite hook. Potrebbe servire come base per future funzionalità AJAX o semplici visualizzazioni di pagina, se necessario.
    -   `controllers/front/testimonials.php`
        -   **Nome classe:** `DisqusTestimonialsModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità:** Questo controller è responsabile del rendering della pagina dedicata "Testimonianze". Recupera la configurazione necessaria (es. `disqus_shortname`) e la passa al template `testimonials.tpl`, che poi incorpora il codice di incorporamento universale di Disqus configurato per visualizzare tutti i commenti per il nome breve dato. Questo controller gestisce la rotta `module/disqus/testimonials`.
-   **Controller Admin Back-Office**: Nessuno esplicitamente definito nell'inventario fornito. Tutta la configurazione è gestita tramite il metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Nessuna classe personalizzata o definizione di `ObjectModel` è presente nella directory `classes/` secondo l'inventario. Il modulo si basa sulla classe `Configuration` di PrestaShop per memorizzare le sue impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è presente nella directory `views/js/` secondo l'inventario. Il modulo incorpora direttamente il codice di incorporamento universale di Disqus (solitamente un tag `<script>` con `DISQUS.init()` o logica simile) nei template Smarty pertinenti. Ciò significa che il JavaScript di Disqus viene caricato direttamente da `disqus.com`.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è presente nella directory `views/css/` secondo l'inventario. Lo stile del widget dei commenti Disqus stesso è gestito da Disqus. Qualsiasi stile specifico per l'integrazione (es. per i blocchi dei commenti recenti o il layout della pagina delle testimonianze) sarebbe minimo, ereditato dal tema o inline all'interno dei template.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:

    -   `last-comments.tpl`: Questo template viene utilizzato per visualizzare il blocco "Commenti Recenti". Itera su un elenco di commenti recenti (recuperati da Disqus tramite JavaScript o una chiamata lato server, se implementata) e li visualizza. Questo template è probabilmente renderizzato negli hook `displayHome`, `displayLeftColumn` e `displayRightColumn`.
    -   `leftColumn.tpl`: Questo template è probabilmente un wrapper o un contenuto specifico per l'hook `displayLeftColumn`, potenzialmente includendo `last-comments.tpl` o il link alle testimonianze.
    -   `productfooter.tpl`: Questo template viene renderizzato nell'hook `displayProductFooter`. Contiene il codice di incorporamento universale di Disqus per i commenti sui prodotti quando la "Posizione del widget dei commenti" è impostata su "Sezione Footer Prodotto".
    -   `rightColumn.tpl`: Simile a `leftColumn.tpl`, questo è per l'hook `displayRightColumn`, potenzialmente includendo `last-comments.tpl` o il link alle testimonianze.
-   **Template admin (`views/templates/admin/`)**: Nessuno.
-   **Template front-office (`views/templates/front/`)**:

    -   `testimonials.tpl`: Questo template viene renderizzato da `DisqusTestimonialsModuleFrontController`. Contiene il codice di incorporamento universale di Disqus configurato per visualizzare tutti i commenti per il nome breve del sito, creando efficacemente la pagina aggregata delle testimonianze.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `DISQUS_SHORTNAME`, `DISQUS_HOOK`, `DISQUS_TEST`, `DISQUS_TEST_WHERE`, `DISQUS_RIGHTRECENT`, `DISQUS_LEFTRECENT`, `DISQUS_FORLOGGED`, `DISQUS_LASTCOMMENTS`, `DISQUS_LASTC_NB`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Potenzialmente utilizzato per includere variabili di configurazione globali di Disqus o CSS/JS se necessario, anche se l'incorporamento principale è in hook di contenuto specifici. |
| `displayProductExtraContent` | All'interno della pagina del prodotto, spesso utilizzato per schede o blocchi di contenuto aggiuntivi. | Utilizzato per visualizzare la sezione dei commenti Disqus all'interno di una scheda del prodotto quando la "Posizione del widget dei commenti" è impostata su "Sezione Scheda Prodotto". |
| `displayRightColumn` | Nella colonna destra delle pagine. | Utilizzato per visualizzare il blocco "Commenti Recenti" o il "Link alle testimonianze" se configurato. |
| `displayProductFooter` | In fondo al contenuto della pagina del prodotto. | Utilizzato per visualizzare la sezione dei commenti Disqus quando la "Posizione del widget dei commenti" è impostata su "Sezione Footer Prodotto". |
| `displayLeftColumn` | Nella colonna sinistra delle pagine. | Utilizzato per visualizzare il blocco "Commenti Recenti" o il "Link alle testimonianze" se configurato. |
| `displayHome` | Sulla homepage. | Utilizzato per visualizzare il blocco "Commenti Recenti" sulla homepage. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Questo hook è elencato nel metodo `install()` del modulo, suggerendo una potenziale funzionalità futura o un controllo per i prodotti acquistati. È probabilmente utilizzato in combinazione con l'impostazione "Mostra Disqus solo agli utenti loggati che hanno acquistato il prodotto" per verificare la cronologia degli acquisti. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante il modulo DISQUS comments.
