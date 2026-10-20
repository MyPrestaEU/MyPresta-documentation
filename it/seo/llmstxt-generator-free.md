---
title: "LLMS.txt Generator Free - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop LLMS.txt Generator Free di MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Free - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo LLMS.txt Generator Free su MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/seo/llmstxt-generator-free/)
>
> ---


# LLMS.txt Generator Free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Il tuo server deve consentire la scrittura di file nella directory principale della tua installazione PrestaShop affinché il file `llms.txt` possa essere creato e aggiornato.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alla pagina delle impostazioni principali del modulo. Qui definirai quali contenuti andranno nel tuo file `llms.txt`.

#### Impostazioni Generali

-   **Profilo del Negozio (per ogni lingua attiva)**
    *   **Cosa fa questa impostazione:** Ti permette di scrivere una descrizione breve e concisa del tuo negozio in ogni lingua supportata dal tuo shop. Questo profilo sarà incluso nel file `llms.txt`, fornendo ai modelli AI una rapida panoramica della tua attività.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se compilato:* Il testo che fornisci verrà aggiunto al file `llms.txt`, aiutando i modelli AI a comprendere lo scopo e le offerte del tuo negozio in lingue specifiche.
        *   *Se lasciato vuoto:* Nessun profilo del negozio verrà incluso per quella lingua, rendendo potenzialmente più difficile per l'AI cogliere l'essenza del tuo negozio.
    *   **Valore consigliato:** Compila questo campo per ogni lingua attiva. Mantienilo breve (1-2 frasi) e descrittivo.
    *   **Scenario / esempio per il commerciante:** Se il tuo negozio vende cibo biologico per animali domestici, potresti scrivere: "MyStore offre un'ampia selezione di cibo biologico premium per animali domestici e forniture naturali per cani e gatti. Diamo priorità alla salute, alla sostenibilità e alla felicità degli animali domestici."

#### Selezione Contenuti

-   **Categorie Promosse**

    *   **Cosa fa questa impostazione:** Ti permette di selezionare specifiche categorie di prodotti dal tuo negozio che desideri evidenziare ai crawler AI. Queste categorie saranno esplicitamente elencate nel file `llms.txt`.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando le categorie sono selezionate:* I modelli AI saranno indirizzati a queste categorie, segnalando la loro importanza e potenzialmente aumentandone la visibilità nelle ricerche basate sull'AI.
        *   *Quando nessuna categoria è selezionata:* I modelli AI non riceveranno indicazioni specifiche su quali categorie dare priorità dal tuo file `llms.txt`.
    *   **Valore consigliato:** Seleziona 3-5 delle tue categorie più importanti o più vendute.
    *   **Scenario / esempio per il commerciante:** Se sei specializzato in "Abiti da Donna", "Scarpe da Uomo" e "Giocattoli per Bambini", seleziona queste categorie per dire all'AI che queste sono le offerte principali.
-   **Includi i 5 Prodotti Più Venduti con Prezzi**

    *   **Cosa fa questa impostazione:** Se abilitato, il modulo identificherà automaticamente i tuoi 5 prodotti più venduti e includerà i loro nomi, link e prezzi attuali nel file `llms.txt`.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I modelli AI avranno accesso diretto alle informazioni sui tuoi prodotti più popolari, inclusi i loro prezzi, il che può essere cruciale per le raccomandazioni di acquisto basate sull'AI.
        *   *Quando disabilitato:* I tuoi prodotti più venduti non saranno esplicitamente evidenziati con i loro prezzi nel file `llms.txt`.
    *   **Valore consigliato:** SÌ. Questa è una potente funzionalità per mostrare i tuoi articoli più popolari.
    *   **Scenario / esempio per il commerciante:** Un cliente chiede a un'AI: "Quali sono gli articoli più venduti su [Nome del tuo negozio]?" Con questa opzione abilitata, l'AI può fornire una risposta diretta con i prezzi attuali.
-   **Includi Pagine CMS**

    *   **Cosa fa questa impostazione:** Ti permette di selezionare pagine di contenuto statico importanti (come "Chi siamo", "Contattaci", "Informativa sulla privacy", "Informazioni sulla consegna") di cui vuoi che i modelli AI siano a conoscenza.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando le pagine CMS sono selezionate:* I modelli AI saranno indirizzati a queste pagine informative, aiutandoli a comprendere le politiche, il background del tuo negozio e come contattarti.
        *   *Quando nessuna pagina CMS è selezionata:* I modelli AI potrebbero dover scoprire queste pagine tramite la scansione generale, il che potrebbe essere meno efficiente.
    *   **Valore consigliato:** Seleziona tutte le pagine informative essenziali che creano fiducia e forniscono dettagli sul servizio clienti.
    *   **Scenario / esempio per il commerciante:** Assicurati che le tue pagine "Politica di reso" e "FAQ" siano incluse in modo che l'AI possa rispondere accuratamente alle domande dei clienti su questi argomenti.

#### Azione

-   **Salva e Rigenera il file llms.txt**
    *   **Cosa fa questo pulsante:** Questo pulsante salva tutte le impostazioni che hai configurato in questa pagina e rigenera immediatamente il file `llms.txt` nella directory principale del tuo negozio con le informazioni aggiornate.
    *   **Effetto del clic su questo pulsante:** Il tuo file `llms.txt` verrà aggiornato con le tue ultime selezioni. Questa azione viene attivata automaticamente anche quando aggiorni prodotti o categorie nel tuo negozio.
    *   **Valore consigliato:** Clicca sempre su questo pulsante dopo aver apportato modifiche per assicurarti che il tuo file `llms.txt` sia aggiornato.
    *   **Scenario / esempio per il commerciante:** Dopo aver aggiunto una nuova descrizione del "Profilo del negozio", clicca su questo pulsante per assicurarti che i crawler AI ricevano le nuove informazioni.

#### Aggiorna alla Versione Pro (Blocco Upsell)

Questa sezione è un blocco informativo che promuove la versione Pro del modulo. Evidenzia funzionalità aggiuntive disponibili nella versione a pagamento, come l'esportazione completa del catalogo, l'analisi dei crawler, i filtri e il supporto per i cron job. Questa non è un'impostazione configurabile ma un suggerimento per esigenze avanzate.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Profilo del Negozio (per lingua) | Compila per tutte le lingue | Fornisce ai modelli AI una breve descrizione strutturata del tuo negozio. |
| Configurazione Modulo | Categorie Promosse | Seleziona 3-5 categorie chiave | Indirizza i crawler AI alle tue categorie di prodotti più importanti. |
| Configurazione Modulo | Includi i 5 Prodotti Più Venduti con Prezzi | SÌ | Evidenzia i tuoi prodotti più popolari con i prezzi attuali all'AI. |
| Configurazione Modulo | Includi Pagine CMS | Seleziona tutte le pagine essenziali | Guida l'AI a importanti pagine informative (es. Chi siamo, Contatti). |
| Configurazione Modulo | Salva e Rigenera il file llms.txt | Clicca dopo ogni modifica | Salva le impostazioni e aggiorna il file `llms.txt` nella directory principale del tuo negozio. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Ho configurato il modulo, ma non vedo alcuna modifica sul mio sito web. Funziona?**
R1: Sì, è probabile che funzioni correttamente! Il file `llms.txt` è un file tecnico per i crawler AI, non per i visitatori umani. Non vedrai alcuna modifica visiva nel front-office del tuo negozio. Per verificare che funzioni, puoi provare ad accedere a `iltuonegozio.com/llms.txt` nel tuo browser. Dovresti vedere il contenuto generato lì.

**D2: Ricevo un errore che il modulo non può scrivere il file `llms.txt`.**
R2: Questo di solito indica un problema di permessi dei file sul tuo server. Il modulo necessita del permesso di creare e aggiornare il file `llms.txt` nella directory principale del tuo PrestaShop.
- **Soluzione:** Contatta il tuo provider di hosting e chiedi loro di assicurarsi che l'applicazione PrestaShop abbia i permessi di scrittura (es. chmod 755 o 775 per le directory, 644 o 664 per i file) nella cartella principale del tuo negozio.

**D3: Con quale frequenza viene aggiornato il file `llms.txt`?**
R3: Il file `llms.txt` viene rigenerato automaticamente ogni volta che:
- Clicchi sul pulsante "Salva e Rigenera il file llms.txt" nella configurazione del modulo.
- Aggiorni un prodotto (es. modifichi prezzo, nome, descrizione).
- Aggiorni una categoria (es. modifichi nome, descrizione).
Questo assicura che il file sia sempre aggiornato con i tuoi ultimi dati del negozio.

**D4: Il mio tema personalizzato non sembra essere influenzato da questo modulo. C'è un conflitto?**
R4: No, non dovrebbe esserci alcun conflitto. Questo modulo opera interamente in background, generando un file di testo. Non modifica il design, il CSS o il JavaScript del tuo tema. Il suo scopo è fornire dati strutturati ai crawler AI, non modificare l'aspetto visivo del tuo negozio.

**D5: Posso modificare manualmente il file `llms.txt`?**
R5: È fortemente sconsigliato **non** modificare manualmente il file `llms.txt` direttamente. Qualsiasi modifica apportata verrà sovrascritta la prossima volta che il modulo rigenererà il file (es. quando salvi le impostazioni o aggiorni prodotti/categorie). Utilizza sempre l'interfaccia di configurazione del modulo per controllarne il contenuto.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'Architettura

Il modulo `LLMS.txt Generator Free` è un modulo PrestaShop leggero principalmente focalizzato sulla generazione di un file di testo statico (`llms.txt`) nella directory principale del negozio. Segue una struttura standard del modulo PrestaShop, sfruttando la classe `Module` per l'installazione, la disinstallazione e la configurazione. La logica principale risiede nel file principale del modulo, gestendo la persistenza della configurazione e la generazione dei file. Utilizza la classe `Configuration` di PrestaShop per le impostazioni e gli hook per la rigenerazione automatica.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller personalizzato Front-Office o Back-Office Admin. Tutta la logica è gestita all'interno del metodo `getContent()` del file principale del modulo per la configurazione e tramite hook per le operazioni in background.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo **non** contiene classi personalizzate o definizioni di `ObjectModel` nella directory `classes/`. Utilizza direttamente le classi core di PrestaShop come `Configuration`, `Product`, `Category`, `CMS`, `Language` e `Shop`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** contiene alcun file JavaScript personalizzato.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   **`llmstxtfree/views/css/admin-config.css`**
    *   **Scopo:** Stile del modulo di amministrazione del Back-office.
    *   **Componenti UI principali e contenitori che stilizza:** Fornisce uno stile di base per la pagina di configurazione del modulo, probabilmente per il layout, la spaziatura e potenzialmente alcuni segnali visivi per il blocco di upsell.
    *   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:** Tipicamente mira agli elementi all'interno dell'output `getContent()` del modulo, come `.panel`, `.form-group` o classi personalizzate definite in `configure.tpl`.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    *   **`llmstxtfree/views/templates/admin/configure.tpl`**
        *   **Scopo:** Questo è il template Smarty principale renderizzato dal metodo `getContent()` del modulo. Definisce la struttura e i campi per la pagina di configurazione del modulo nel Back Office di PrestaShop.
        *   **Contenuto:** Contiene il modulo HTML per tutte le impostazioni descritte nella Sezione 4.1, inclusi i campi di input per il profilo del negozio, la selezione delle categorie, l'interruttore dei bestseller, la selezione delle pagine CMS e il pulsante di salvataggio. Include anche il template `pro-upsell.tpl`.
    *   **`llmstxtfree/views/templates/admin/pro-upsell.tpl`**
        *   **Scopo:** Questo template è incluso in `configure.tpl` e visualizza il contenuto promozionale per la versione Pro del modulo.
        *   **Contenuto:** Tipicamente contiene testo, immagini e link che incoraggiano il commerciante ad aggiornare alla versione a pagamento, evidenziando funzionalità aggiuntive.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    *   Questo modulo **non** crea tabelle SQL personalizzate.
    *   Memorizza le sue impostazioni di configurazione (es. categorie selezionate, pagine CMS, profili del negozio, interruttore dei bestseller) nella tabella standard di PrestaShop `ps_configuration`. Le chiavi di configurazione seguono tipicamente il modello `LLMSTXTFREE_SETTING_NAME`.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Rende il contenuto nella sezione `<head>` delle pagine del front-office. | Non utilizzato direttamente per l'output del contenuto, ma spesso registrato dai moduli per il caricamento di risorse o la configurazione iniziale. In questo modulo, è probabilmente per l'inizializzazione generale del modulo o potenzialmente per funzionalità future. |
| `displayRightColumn` | Rende il contenuto nella colonna destra delle pagine del front-office. | Non utilizzato per l'output del contenuto in questo modulo. |
| `displayLeftColumn` | Rende il contenuto nella colonna sinistra delle pagine del front-office. | Non utilizzato per l'output del contenuto in questo modulo. |
| `displayFooter` | Rende il contenuto nel footer delle pagine del front-office. | Non utilizzato per l'output del contenuto in questo modulo. |
| `displayProductExtraContent` | Rende contenuto extra nella pagina del prodotto. | Non utilizzato per l'output del contenuto in questo modulo. |
| `actionProductUpdate` | Eseguito dopo l'aggiornamento di un prodotto nel Back Office. | **Cruciale per questo modulo:** Attiva la rigenerazione automatica del file `llms.txt` per garantire che i dati dei bestseller e i link dei prodotti siano aggiornati. |
| `actionCategoryUpdate` | Eseguito dopo l'aggiornamento di una categoria nel Back Office. | **Cruciale per questo modulo:** Attiva la rigenerazione automatica del file `llms.txt` per garantire che i link e i nomi delle categorie promosse siano aggiornati. |
| `actionObjectCmsUpdateAfter` | Eseguito dopo l'aggiornamento di una pagina CMS. | Attiva la rigenerazione automatica del file `llms.txt` per garantire che i link e i titoli delle pagine CMS selezionate siano aggiornati. |
| `actionObjectCmsAddAfter` | Eseguito dopo l'aggiunta di una nuova pagina CMS. | Attiva la rigenerazione automatica del file `llms.txt`. |
| `actionObjectCmsDeleteAfter` | Eseguito dopo l'eliminazione di una pagina CMS. | Attiva la rigenerazione automatica del file `llms.txt`. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per esplorare moduli e servizi aggiuntivi, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante il modulo LLMS.txt Generator Free.
