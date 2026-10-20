---
title: "Notizie in homepage - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Notizie in homepage di MyPresta.eu."
sidebar:
  label: "Notizie in homepage - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homepage news su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-news.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homepage-news/)
>
> ---


# Notizie in homepage

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Notizie in homepage", dove controlli come i tuoi articoli di notizie vengono visualizzati sulla homepage.

#### **Seleziona Categoria di pagine CMS**

-   **Cosa fa questa impostazione:** Questo menu a discesa ti consente di scegliere quale specifica categoria CMS verrà utilizzata come fonte per le tue notizie in homepage. Solo le pagine CMS appartenenti a questa categoria selezionata verranno considerate per la visualizzazione dal modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando una categoria è selezionata:* Il modulo recupererà e visualizzerà gli articoli di notizie solo dalle pagine CMS all'interno di quella categoria.
    -   *Quando nessuna categoria è selezionata (o una inappropriata):* Il modulo potrebbe non visualizzare alcuna notizia, oppure potrebbe visualizzare pagine che non intendevi fossero articoli di notizie.
-   **Valore consigliato:** Seleziona la categoria CMS che hai specificamente creato o designato per i tuoi articoli di notizie (es. "Notizie", "Blog", "Aggiornamenti").
-   **Scenario / esempio per il commerciante:** Hai creato una categoria CMS chiamata "Notizie Aziendali" e vi hai aggiunto diverse pagine CMS, come "Lancio Nuovo Prodotto", "Saldi Estivi Annunciati" e "Orari di Apertura Festivi". Selezionando "Notizie Aziendali" qui, solo queste pagine appariranno come notizie sulla tua homepage.

#### **Mostra il contenuto completo dell'ultima pagina CMS**

-   **Cosa fa questa impostazione:** Questo interruttore determina se l'ultimo articolo di notizie (pagina CMS) dalla categoria selezionata verrà visualizzato con il suo contenuto completo direttamente sulla homepage.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il contenuto completo dell'articolo di notizie più recente sarà visibile sulla tua homepage, fornendo informazioni immediate senza richiedere un clic.
    -   *Quando disabilitato (NO):* Verranno mostrati solo il titolo, la miniatura e una breve descrizione (se configurata) dell'ultimo articolo di notizie, in modo simile ad altre miniature. I clienti dovranno cliccare per leggere il contenuto completo.
-   **Valore consigliato:** "SÌ" se vuoi evidenziare immediatamente le tue notizie più importanti; "NO" se preferisci una sezione notizie più compatta dove tutti gli articoli richiedono un clic.
-   **Scenario / esempio per il commerciante:** Hai un annuncio importante, come l'apertura di un nuovo negozio. Abilitando questa opzione, i clienti vedranno subito tutti i dettagli. Se preferisci una homepage più pulita, potresti disabilitarla e mostrare solo gli estratti.

#### **Mostra miniature delle pagine CMS**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se le versioni più piccole e riassunte (miniature) dei tuoi articoli di notizie vengono visualizzate sulla homepage. Queste miniature includono tipicamente un titolo, una piccola immagine e una breve descrizione.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo visualizzerà una serie di blocchi di notizie in miniatura, ognuno rappresentante una pagina CMS recente dalla categoria selezionata.
    -   *Quando disabilitato (NO):* Non verranno mostrate miniature. Se anche "Mostra il contenuto completo dell'ultima pagina CMS" è disabilitato, non apparirà alcuna notizia.
-   **Valore consigliato:** "SÌ" per fornire una panoramica di più articoli di notizie e incoraggiare l'esplorazione.
-   **Scenario / esempio per il commerciante:** Vuoi mostrare gli ultimi 3-5 articoli di notizie per dare ai clienti una rapida occhiata agli aggiornamenti recenti. L'abilitazione delle miniature lo consente.

#### **Numero di miniature da visualizzare**

-   **Cosa fa questa impostazione:** Se "Mostra miniature delle pagine CMS" è abilitato, questo campo di input determina quante delle miniature degli articoli di notizie più recenti verranno mostrate sulla tua homepage.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un numero più alto (es. 5):* Saranno visibili più miniature di articoli di notizie, fornendo una panoramica più ampia.
    -   *Quando impostato su un numero più basso (es. 2):* Verranno visualizzate meno miniature, rendendo la sezione notizie più concisa.
-   **Valore consigliato:** Da 3 a 5, a seconda del layout della tua homepage e di quanto spazio vuoi dedicare alle notizie.
-   **Scenario / esempio per il commerciante:** Hai molte notizie ma vuoi mantenere la tua homepage pulita. Impostando questo valore su "3" ti assicuri che vengano evidenziati solo i tre articoli più recenti.

#### **Numero di caratteri utilizzati nella descrizione per le miniature**

-   **Cosa fa questa impostazione:** Questo campo di input controlla la lunghezza della breve descrizione (estratto) visualizzata all'interno di ogni miniatura di notizia.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un numero più alto (es. 200):* Le descrizioni nelle miniature saranno più lunghe, fornendo più contesto.
    -   *Quando impostato su un numero più basso (es. 50):* Le descrizioni saranno più brevi, rendendo le miniature più compatte.
-   **Valore consigliato:** Da 100 a 150 caratteri, sufficienti per dare un buon riassunto senza sovraccaricare la miniatura.
-   **Scenario / esempio per il commerciante:** Vuoi dare ai clienti solo le informazioni sufficienti nella miniatura per incuriosirli. Impostando questo valore su "120" si garantisce un frammento conciso ma informativo.

#### **Stile delle miniature**

-   **Cosa fa questa impostazione:** Questa opzione (probabilmente un menu a discesa o pulsanti radio) ti consente di scegliere il layout visivo o lo stile con cui le miniature delle notizie vengono presentate sulla tua homepage. Gli stili disponibili potrebbero includere opzioni come una griglia, un elenco o un carosello.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "Griglia":* Le miniature potrebbero apparire in righe e colonne, adatte per visualizzare diversi elementi in modo compatto.
    -   *Quando impostato su "Elenco":* Le miniature potrebbero apparire una sotto l'altra, ottimo per descrizioni più dettagliate.
    -   *Quando impostato su "Carosello":* Le miniature potrebbero scorrere orizzontalmente, risparmiando spazio e consentendo agli utenti di sfogliare più elementi.
-   **Valore consigliato:** Sperimenta con gli stili disponibili per vedere quale si adatta meglio al design del tuo tema e all'estetica desiderata della tua homepage.
-   **Scenario / esempio per il commerciante:** La tua homepage ha uno spazio orizzontale limitato. Scegliere uno stile "Carosello" ti consente di visualizzare molti elementi di notizie senza rendere la pagina troppo lunga. Se hai ampio spazio, una "Griglia" potrebbe sembrare più accattivante.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Seleziona Categoria di pagine CMS | La tua categoria CMS "Notizie" designata | Definisce quali pagine CMS vengono utilizzate come fonte di notizie. |
| Configurazione modulo | Mostra il contenuto completo dell'ultima pagina CMS | SÌ | Visualizza il contenuto completo dell'articolo più recente direttamente sulla homepage. |
| Configurazione modulo | Mostra miniature delle pagine CMS | SÌ | Abilita la visualizzazione di blocchi di notizie riassunti. |
| Configurazione modulo | Numero di miniature da visualizzare | 3-5 | Controlla quante miniature di notizie recenti vengono mostrate. |
| Configurazione modulo | Numero di caratteri utilizzati nella descrizione per le miniature | 100-150 | Imposta la lunghezza dell'estratto di testo nelle miniature. |
| Configurazione modulo | Stile delle miniature | Varia (es. Griglia, Elenco, Carosello) | Determina il layout visivo delle miniature delle notizie. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: La mia sezione notizie non viene visualizzata sulla homepage. Cosa dovrei controllare?**
R:

1.  **Modulo Abilitato:** Vai su **Moduli > Gestione moduli** e assicurati che "Notizie in homepage" sia installato e abilitato.
2.  **Categoria CMS Selezionata:** Nella configurazione del modulo, verifica di aver selezionato una categoria CMS valida sotto "Seleziona Categoria di pagine CMS".
3.  **Pagine CMS Esistenti:** Assicurati che ci siano effettivamente pagine CMS pubblicate all'interno della categoria selezionata.
4.  **Impostazioni di Visibilità:** Controlla se "Mostra miniature delle pagine CMS" e/o "Mostra il contenuto completo dell'ultima pagina CMS" sono abilitate nella configurazione del modulo. Se entrambe sono disabilitate, non verrà visualizzato nulla.
5.  **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**).

**D: Le immagini per le mie miniature di notizie non vengono visualizzate.**
R: Il modulo tipicamente cerca di estrarre la prima immagine dal contenuto della tua pagina CMS.

1.  **Immagine nella Pagina CMS:** Assicurati che il contenuto della tua pagina CMS includa effettivamente un'immagine.
2.  **Percorso Immagine:** Verifica che il percorso dell'immagine nella tua pagina CMS sia corretto e che il file immagine esista sul tuo server.
3.  **Compatibilità del Tema:** Alcuni temi personalizzati potrebbero interferire con il rendering delle immagini. Se tutto il resto fallisce, consulta lo sviluppatore del tuo tema o il supporto MyPresta.eu.

**D: Come traduco i titoli e le descrizioni delle notizie?**
R: I titoli e il contenuto delle notizie provengono direttamente dalle tue pagine CMS.

1.  **Traduzioni delle Pagine CMS:** Vai su **Design > Pagine** (o **CMS** nelle versioni precedenti), modifica la tua pagina CMS di notizie.
2.  **Modifica in Tutte le Lingue:** Per ogni lingua che supporti, assicurati di aver fornito il titolo e il contenuto tradotti per quella specifica pagina CMS. Il modulo visualizzerà automaticamente la lingua corretta in base alla lingua del negozio selezionata dal cliente.

**D: La sezione notizie appare strana o disallineata sulla mia homepage.**
R: Questo è spesso un conflitto CSS con il tema del tuo negozio.

1.  **Svuota Cache:** Inizia sempre svuotando la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**).
2.  **Configurazione Modulo:** Controlla se la modifica dell'impostazione "Stile delle miniature" aiuta.
3.  **Personalizzazione del Tema:** Il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo. Potrebbe essere necessario consultare uno sviluppatore web per aggiungere CSS personalizzato al tuo tema per regolare l'aspetto. Il supporto MyPresta.eu può offrire indicazioni ma non può fornire sviluppo di temi personalizzati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Notizie in homepage" (`hnews`) è un modulo PrestaShop semplice, progettato principalmente per visualizzare contenuti da pagine CMS esistenti sulla homepage del front-office. Sfrutta la classe `Module` di PrestaShop e gli hook standard. La logica del modulo risiede principalmente nel suo file PHP principale, `hnews.php`, che gestisce la configurazione, la registrazione degli hook e il recupero dei dati. Non introduce controller personalizzati o ObjectModels complessi, affidandosi invece alle classi native `CMSCategory` e `CMS` di PrestaShop per i dati.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. La logica di visualizzazione del front-office del modulo è interamente gestita dal suo metodo `hookDisplayHome` all'interno di `hnews.php` e renderizzata tramite un template Smarty.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuna classe o ObjectModels personalizzati sono introdotti da questo modulo. Interroga direttamente il database o utilizza le classi `CMSCategory` e `CMS` di PrestaShop per recuperare i dati.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessun file JavaScript personalizzato è incluso in questo modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `hnews/views/admin/css/hnews.css`:
    -   **Scopo:** Stile del modulo di amministrazione del back-office.
    -   **Componenti principali dell'interfaccia utente:** Probabilmente contiene stili specifici per la pagina di configurazione del modulo, garantendo un layout coerente e leggibile all'interno del back office di PrestaShop.
    -   **Selettori di classe CSS chiave:** Potrebbe includere stili per elementi di modulo, etichette e contenitori specifici utilizzati in `getContent()`.
-   `hnews/views/css/hnews.css`:
    -   **Scopo:** Stile del cliente del front-office.
    -   **Componenti principali dell'interfaccia utente:** Stila la sezione notizie visualizzata sulla homepage, inclusi l'articolo di notizie principale (se il contenuto completo è mostrato) e le singole miniature di notizie.
    -   **Selettori di classe CSS chiave:** Conterrà selettori per il contenitore principale delle notizie, i singoli blocchi di miniature, titoli, descrizioni e immagini. Gli sviluppatori possono sovrascrivere queste classi nel `custom.css` o `theme.css` del loro tema per adattarle al design del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   `hnews/views/hnews.tpl`: Questo è il template primario del front-office.
        -   **Hook:** Renderizzato in `displayHome`.
        -   **Blocco visivo:** Visualizza l'intera sezione notizie sulla homepage, inclusi il contenuto completo dell'ultimo articolo di notizie (se abilitato) e l'elenco delle miniature di notizie. Itera attraverso gli articoli di notizie passati dalla logica PHP del modulo.
-   **Template di amministrazione (`views/templates/admin/`)**:
    -   `hnews/views/admin/elements.tpl`:
        -   **Hook:** Non direttamente agganciato, ma incluso/renderizzato dal metodo `getContent()` in `hnews.php`.
        -   **Blocco visivo:** Renderizza gli elementi del modulo di configurazione per il modulo nel back office di PrestaShop. Questo include tipicamente il menu a discesa per le categorie CMS, gli interruttori per le opzioni di visualizzazione e i campi di input per i conteggi e i limiti di caratteri.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` utilizzando chiavi come `HNEWS_ID_CMSCAT`, `HNEWS_NB_MIN`, `HNEWS_LATEST`, `HNEWS_SIZE_MIN`, `HNEWS_CHR_MIN`, `HNEWS_MINIATURES`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHome` | Renderizza il contenuto nell'area principale della homepage. | Visualizza la sezione notizie con le ultime pagine CMS. |
| `displayHeader` | Eseguito nella sezione `<head>` della pagina del front-office. | Potenzialmente utilizzato per caricare risorse CSS o JS del front-office (anche se non è presente JS, il CSS viene caricato). |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin imposta i suoi media (CSS/JS). | Utilizzato per caricare il CSS del back-office per la pagina di configurazione del modulo. |
| `header` | Simile a `displayHeader`, spesso utilizzato per il caricamento di risorse. | Potenzialmente utilizzato per caricare risorse CSS o JS del front-office. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Notizie in homepage", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi domanda o problema relativo al modulo.
