---
title: "AI Translations with Mistral – documentazione e manuale utente"
description: "Guida alla configurazione e alla risoluzione dei problemi per chi usa il modulo AI Translations with Mistral."
sidebar:
  label: "AI Translations with Mistral – documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo AI Translations with Mistral su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/ai-translations-with-mistral/)
>
> ---


## 1. Requisiti

Il modulo funziona con PrestaShop a partire dalla versione 1.7.0.0.

- **PrestaShop:** 1.7.0.0 o successiva.
- **PHP:** la versione richiesta dalla sua versione di PrestaShop. Il modulo non impone un minimo proprio.
- **Estensioni PHP:** cURL (connessione a Mistral), OpenSSL (cifratura della chiave API), SimpleXML (lettura dei file di traduzione XLF), mbstring.
- **Altri moduli:** il modulo non dipende da nessun altro modulo.
- **Fuori dal negozio:** un account Mistral AI e una chiave API, che può generare su https://console.mistral.ai/api-keys. Il server del negozio deve poter raggiungere `api.mistral.ai` in HTTPS.
- **Facoltativo:** un'attività pianificata sul server che richiama l'indirizzo cron (descritto in 3.1). Senza di essa, le attività si elaborano a mano nella scheda **Jobs**.
- **Cataloghi grandi:** tradurre un intero dominio con migliaia di testi significa molte chiamate API e tempi più lunghi. L'attività viene suddivisa in porzioni della dimensione impostata in **Batch size**. Prima di iniziare esegua sempre **Estimate** in **Bulk**.
- Il negozio deve avere almeno due lingue. Con una sola lingua il back office mostra un avviso, perché non c'è nulla da tradurre.

## 2. Installazione

1. Vada in **Modules** → **Module Manager**. Scelga **Upload a module**, carichi il file ZIP del modulo e prema **Install** accanto a **AI Translations with Mistral**.
2. Dopo l'installazione, la voce **AI Translations with Mistral** compare nel menu **International**.
3. L'installazione non svuota la cache del negozio. Quando salva una traduzione, il modulo svuota da solo la cache di PrestaShop.
4. Vada in **AI Translations with Mistral** → **Settings** e incolli la sua chiave Mistral. Finché non c'è una chiave salvata, il back office mostra il messaggio **No Mistral API key.**

**Disinstallazione.** In **Module Manager** prema **Uninstall** e confermi il messaggio **Delete this module and its data (jobs, glossary, cache)?**

- Spariscono: la voce di menu, tutte le attività, il glossario, le esclusioni, la cronologia delle chiamate, la coda **Review**, le copie salvate per l'annullamento, il riepilogo dei costi e le impostazioni del modulo (chiave API inclusa).
- Restano: i testi che il modulo ha salvato nel negozio, cioè le traduzioni nel catalogo di PrestaShop e i file di traduzione dei moduli classici in cui il modulo ha scritto. Restano anche le impostazioni del controllo degli aggiornamenti.
- Reinstallare il modulo non ripristina le attività, il glossario o la cronologia eliminati. Imposta i valori predefiniti e crea un nuovo indirizzo cron.

## 3. Configurazione e uso nel back office

L'intero modulo si trova in un'unica pagina: **International** → **AI Translations with Mistral**. In alto ci sono le schede **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** e **Settings**. La scheda **Updates** è all'estremità destra della barra. Il pulsante **Help** apre un pannello con la descrizione della scheda corrente.

I nomi di campi e pulsanti di questo manuale sono quelli della versione inglese del back office. Se il pannello è in un'altra lingua, vedrà la traduzione dei nomi. Anche le schermate sono tratte dalla versione inglese.

Ogni scheda si apre con una frase che spiega che cosa fa, come si usa e quale effetto produce. La stessa spiegazione, divisa in tre parti, compare anche sotto i campi del form. Il pulsante **Help**, in basso a destra, la mostra per la scheda corrente. Aprire **Help** non traduce nulla.

**Il processo dall'inizio alla fine**

Una traduzione viene avviata sempre da un collaboratore del negozio nel back office. I clienti non avviano nulla.

1. **Impostazioni.** In **Settings** incolli la chiave Mistral, scelga il modello e la lingua di origine. Prema **Test connection**, poi **Save**. Senza chiave nessun metodo può inviare testo a Mistral.
2. **Scelga il modo di lavorare.**
   - Poche frasi oppure un dominio, con revisione prima del salvataggio: **Manual** (3.3).
   - Un dominio grande, un tema o un modulo: **Bulk**, poi lavori sull'attività in **Jobs** (3.4, 3.5).
   - Campi di prodotti, categorie e pagine CMS: **Catalog** (lotti fino a 100 record, 3.7).
   - Singoli campi nella pagina **International → Translations** (3.12) e nei form di prodotto, categoria e CMS (3.13).
3. **Controllo della qualità.** Ogni testo tradotto viene verificato: variabili, marcatori e HTML. Un testo con errori non viene salvato. Un testo con punteggio basso (inferiore a 70), troppo lungo (più di due volte e mezza l'originale) o con parole inglesi nella traduzione finisce in **Review**.
4. **Salvataggio.** Dipende dal modo di lavorare:
   - **Manual:** dopo **Translate selected (review)** non si salva nulla finché non preme **Save approved**. Selezionare **Save now (skip review)** salva subito le righe corrette.
   - **Bulk:** l'attività attende in **Jobs** e salva solo quando la elabora (**Process slice**, **Auto-process**) o quando la elabora il cron. Un'attività dry-run non salva nulla.
   - **Catalog:** salva subito le righe nella lingua di destinazione scelta.
   - **La pagina International → Translations e i form del negozio:** i pulsanti si limitano a compilare i campi. Il testo arriva nel negozio dopo che preme **Save** in PrestaShop.
   - Con **Allow publish / save** disattivato, nessun modo di lavorare salva testo nel negozio.
5. **Fine del lavoro.** Un'attività in **Jobs** termina con lo stato **completed** (tutto salvato) oppure **completed_with_errors** (ci sono stati errori, vedi 3.5). Le righe in **Review** scompaiono dopo **Approve** o **Reject**. Il risultato di **Catalog** indica quante righe sono state salvate e quante no.

### 3.1. Pagina di configurazione del modulo

Vada in **Modules** → **Module Manager**, trovi **AI Translations with Mistral** e prema **Configure**. Si apre **Dashboard**. Passi alla scheda **Settings**.

**Settings** è un unico form. I campi seguono l'ordine descritto qui sotto. I pulsanti **Save** e **Test connection** si trovano in fondo al form, non in alto.

![Impostazioni: chiave, modello, tono e lingua di origine. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings.webp)

![Interruttori dei pulsanti accanto ai campi e limiti. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-fields.webp)

![Costi, posta, indirizzo cron e pulsanti Test connection e Save. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-cron.webp)

**Connessione**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Mistral API key** | vuoto | La chiave del suo account Mistral. Si copia da https://console.mistral.ai/api-keys. Lasci il campo vuoto per conservare la chiave già salvata. Un nuovo valore sostituisce la chiave salvata; un campo vuoto non la cancella. La chiave salvata viene mostrata in forma mascherata. |
| **Model** | mistral-small-latest | Il modello Mistral che traduce. L'elenco comprende mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest e codestral-latest. Il modello scelto si applica dalla traduzione successiva. Se il suo account non può usare un modello, la chiamata fallisce e l'errore finisce in **History**. |
| **Add a Mistral model** | vuoto | Campo sotto l'elenco dei modelli. Inserisca l'identificativo esatto del modello del suo account e prema **Add model**. Il nuovo modello compare nell'elenco e diventa attivo. Sotto il campo c'è l'elenco dei modelli aggiunti a mano, ognuno con **Remove**. I modelli integrati non si possono rimuovere. |

Messaggi dopo le azioni: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example mistral-small-latest.**, **Built-in models cannot be removed.**

**Stile e lingua**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Tone** | Formal | Aggiunge uno stile a ogni istruzione: **Formal** per un tono formale nel negozio e nel back office, **Casual** per un tono più leggero, **Brand** insieme al campo **Brand voice**. Le nuove traduzioni seguono lo stile scelto. Quelle esistenti restano invariate finché non le rilancia. |
| **Brand voice** | vuoto | Compare dopo la scelta di **Tone: Brand**. Alcune frasi che descrivono il tono del negozio. Un campo vuoto non aggiunge alcuna descrizione. Il testo entra nelle istruzioni successive, ma non modifica le traduzioni già salvate. |
| **Source locale** | — | La lingua che il modello tratta come originale. Di solito si sceglie en-US, cioè la lingua in cui scrive i cataloghi. Il segno **—** indica che la lingua di origine è quella della schermata da cui traduce. Questa impostazione non cambia la lingua predefinita del negozio. |
| **Individual field buttons — shop forms** | Yes | Un pulsante di traduzione accanto a ogni campo multilingua dei form del negozio: prodotto, categoria, CMS e altri. Ogni pulsante traduce solo il proprio campo. Con **No** questi pulsanti vengono nascosti in tutto il negozio. Le traduzioni salvate non cambiano. |
| **Individual field checkboxes — shop forms** | Yes | I campi multilingua dei form del negozio ricevono una casella di selezione. La barra in fondo al form traduce i campi selezionati uno dopo l'altro. Con **No** caselle e barra scompaiono. |
| **Individual field buttons — International → Translations** | Yes | Un pulsante accanto a ogni campo della pagina **International → Translations**. I form del negozio non vengono modificati. |
| **Individual field checkboxes — International → Translations** | Yes | Caselle di selezione e barra nella pagina **International → Translations**. Con **No** scompaiono solo da quella pagina. |

**Limiti e costi**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Batch size** | 25 | Quanti testi vanno in una singola chiamata. Alla prima esecuzione scelga un valore tra 10 e 25. Il valore resta nell'intervallo 1–100. Un lotto più grande porta a termine l'attività con meno chiamate; in caso di errore viene ritentata una porzione più grande. |
| **Dry-run sample** | 10 | Quanti testi di esempio mostra **Estimate** in **Bulk**. Il valore resta nell'intervallo 1–50. La stima non salva nulla. |
| **Max tokens (0 = default)** | 0 | Il limite di lunghezza di una singola risposta. Inserisca 0 per usare il limite predefinito di Mistral. Imposti un numero quando le risposte vengono tagliate o risultano troppo lunghe. Vale dalla chiamata successiva. |
| **Budget USD / month** | 0 | Un limite mensile in dollari, calcolato dal riepilogo dei costi. Inserisca 0 per non avere limiti. Quando l'importo viene raggiunto, le nuove traduzioni si fermano. Il lavoro già completato resta. |
| **Rate limit / min** | 60 | Quante chiamate API il negozio può effettuare in un minuto. Inserisca 0 per disattivare questo limite locale. Le chiamate oltre il limite vengono saltate e annotate in **History**. Mistral può applicare un proprio limite. |
| **Temperature** | 0.2 | Quanta libertà ha il modello nel riformulare il testo. Intorno a 0.2 resta fedele all'originale; valori vicini a 1 cambiano di più le frasi. L'intervallo è 0–1. I controlli su variabili e HTML continuano a funzionare. |
| **Log retention days** | 30 | Per quanti giorni conservare le voci in **History**. Il minimo è 1. Le voci più vecchie vengono eliminate. Attività, glossario e traduzioni salvate non vengono cancellati. |
| **Allow publish / save** | Yes | Se il modulo può salvare la traduzione nel negozio. Con **No** il salvataggio è bloccato in **Manual** (pulsanti **Save approved** e **Save now**), in **Bulk** (attività senza dry-run) e in **Catalog**. I pulsanti delle pagine si limitano a compilare i campi; il salvataggio lo esegue PrestaShop. |

Messaggi dopo **Save**:

- **Settings saved. No translation was started.** (verde) – impostazioni salvate, nulla è stato tradotto.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** (giallo) – manca la chiave; la incolli.

**Posta e cron**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Email notify on complete** | No | Invia un'e-mail quando un'attività di **Bulk** termina. L'attività funziona allo stesso modo; cambia solo l'invio. |
| **Notify email** | vuoto | L'indirizzo che riceve l'e-mail di fine attività. Il campo compare dopo aver attivato **Email notify on complete**. Il solo salvataggio dell'indirizzo non invia alcun messaggio. |
| **CRON URL** | indirizzo con token | L'indirizzo che il server può richiamare per elaborare una porzione di un'attività in attesa. Ogni chiamata elabora una porzione e termina. Non pubblichi questo indirizzo: chiunque lo conosca può avviare una porzione. Aprire **Settings** da solo non avvia alcuna attività. |

**Test connection** verifica la chiave e il modello con una breve richiesta. Non traduce e non salva nulla. Risultato:

- **Connection OK (N ms). No translation was started.** – la connessione funziona.
- **Connection was not made. Nothing was translated.** con il motivo indicato – controlli la chiave e il modello.

Per iniziare: incolli la chiave, scelga il modello e la lingua di origine, poi prema **Test connection**. Lasci gli altri valori ai predefiniti finché le attività non si comportano correttamente.

### 3.2. Dashboard

Accesso: la prima scheda, **Dashboard**.

![Riepilogo dei testi mancanti, filtri della cronologia e schede delle chiamate. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard.webp)

![Grafici delle chiamate e dei token. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-charts.webp)

![Riepiloghi e le ultime dieci chiamate. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-latest.webp)

Il **Dashboard** si divide in due parti. La prima è il riepilogo dei testi che mancano di traduzione. La seconda è la cronologia delle chiamate a Mistral, sotto forma di schede e grafici. La pagina non traduce né modifica alcun testo.

**Riepilogo dei testi mancanti**

- **Locale:** scelga la lingua di cui vuole contare i testi mancanti.
- **Show:** aggiorna la tabella per la lingua scelta.
- La tabella ha le colonne **Section**, **Total**, **Missing** e **Done**. La colonna **Done** contiene una barra di avanzamento. Le sezioni sono **Back office**, **Themes**, **Installed modules**, **Emails** e **Others**. **Missing** è il numero di testi senza traduzione in quella lingua.
- Dopo **Show** compare il messaggio **Coverage for [lingua]. This page only counts strings. Nothing was translated.**
- Sotto la tabella c'è una riga **CRON** con l'indirizzo cron, lo stesso di **Settings**.
- Una tabella vuota significa che il negozio non ha ancora un catalogo per quella lingua. Lo crea in **International → Translations**.

**Cronologia delle chiamate**

- **Filter** funziona con i preset **Today**, **7 days**, **30 days**, **This month**, **All time** e con i campi **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** e **Prompt or reply contains**.
- Le schede mostrano **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** ed **Estimated cost**. Il costo è una stima, non una fattura.
- Grafici: **Requests and errors**, **Tokens sent and received**, **Requests by model**.
- Sotto i grafici ci sono cinque riepiloghi: **By day**, **By model**, **By type**, **By language** e **By employee**. Se nel periodo ci sono chiamate, ogni riepilogo è una tabella con le colonne **Group**, **Calls**, **Sent**, **Received** e **Total**. Se non ci sono chiamate, compare **No requests in this range.**
- **Latest prompts** mostra le ultime dieci chiamate, con le colonne **When**, **Status**, **Type**, **Languages** e **Preview**. Se l'elenco è vuoto, compare **No requests yet.** **View** apre una finestra con l'istruzione inviata e la risposta. **See all** porta a **History** (3.10).

Cosa fare dopo: se in una sezione mancano quasi tutti i testi, apra **Manual** per tradurne alcuni oppure **Bulk** per l'intero dominio.

### 3.3. Manual

Accesso: scheda **Manual**.

![Filtro di Manual. Il pulsante Filter si trova sotto il campo Search. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-manual.webp)

**Manual** traduce un dominio o un modulo, qualche decina di testi alla volta. Filtrare non salva nulla.

**Campi del filtro**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Section** | Back office | Sceglie il catalogo PrestaShop da leggere: **Back office**, **Themes**, **Installed modules**, **Emails** oppure **Others**. Cambiare sezione ricarica la pagina, mostra solo i campi di quella sezione e non richiama Mistral. |
| **Theme** | — | Visibile solo per **Themes**. Limita l'elenco a un tema. Gli altri temi vengono saltati. |
| **Module** | — | Visibile solo per **Installed modules**. Limita l'elenco a un modulo. Un modulo senza domini (classico) mostra tutti i suoi testi insieme. |
| **Domain** | — | Il gruppo di testi, lo stesso di **International → Translations**. Lo scelga e prema **Filter**. Nascosto per i moduli classici e per le sezioni senza domini. |
| **Source** | en-US oppure il valore di **Settings** | La lingua da cui prende i testi. Scelga una lingua che ha già buone traduzioni. |
| **Target** | la prima lingua dell'elenco | La lingua che vuole completare. Deve esistere in **International → Localization → Languages**. |
| **Only empty** | Yes | Mostra solo i testi senza traduzione. Se lo disattiva, vede tutti i testi. Le traduzioni salvate non vengono cancellate. |
| **Search** | vuoto | Lascia solo i testi di origine che contengono la parola digitata. |

Passaggi:

1. Imposti **Section**, **Source** e **Target**.
2. Per **Themes** scelga un **Theme**. Per **Installed modules** scelga un **Module**.
3. Prema **Filter**. L'elenco **Domain** si aggiorna. Scelga un dominio e prema di nuovo **Filter**. Per un modulo classico salti il dominio: **Filter** carica tutti i testi del modulo.
4. Selezioni le righe. Per selezionare usi **Check all**, **Uncheck all** o le caselle accanto alle righe.
5. Dopo **Filter**, l'elenco ha le colonne **Source**, **Current** e **Status** (**empty** o **filled**). Sopra l'elenco ci sono **Translate selected (review)** e la casella **Save now (skip review)**.
6. Prema **Translate selected (review)**. Compare la tabella **Review before save** con le colonne casella, **Source**, **AI proposal** e **Warnings**. Le righe corrette sono già selezionate. Deselezioni quelle che non vuole e, se serve, corregga la proposta direttamente nel campo. Prema **Save approved** per salvare le righe selezionate.
7. Invece del passaggio 6 può selezionare **Save now (skip review)** prima di tradurre. In questo caso le righe corrette vengono salvate subito, senza la tabella di revisione.

**Messaggi**

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – l'elenco è pronto.
- **No strings match this filter. Nothing was sent to Mistral.** – modifichi il filtro o disattivi **Only empty**.
- **Nothing was translated. Choose a domain, then press Filter to load the strings.** – scelga un dominio.
- **Nothing was translated. Tick at least one row.** – selezioni almeno una riga.
- **Review is ready. Nothing is saved until you press Save approved.** – la traduzione è pronta; il salvataggio avviene solo dopo **Save approved**.
- **Saved. The approved strings were written for the target language.** – dopo **Save now (skip review)** sono state salvate le righe corrette.
- **Saved N. Only the ticked rows were written.** – dopo **Save approved** sono state salvate le righe selezionate.
- **Nothing was saved. Tick OK on the rows you want to keep.** – nella tabella di revisione non c'è nessuna riga selezionata. Selezioni le righe che vuole conservare e prema di nuovo **Save approved**.
- **Not saved because of broken placeholders or HTML: N.** – N righe non hanno superato il controllo e sono state saltate. Le corregga a mano nella tabella, in modo che variabili e marcatori HTML siano uguali all'originale.
- **Nothing was saved. Turn on Allow publish in Settings.** – attivi **Allow publish / save**.
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.** – l'elenco è cambiato. Prema **Filter** e selezioni di nuovo le righe.
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – modulo classico, senza domini. L'elenco è completo.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Mistral.** – lo stesso caso, prima di premere **Filter**.
- **Nothing was translated. Pick a theme, then press Filter.** / **Nothing was translated. Pick a module, then press Filter.** – scelga un tema o un modulo.

### 3.4. Bulk

Accesso: scheda **Bulk**.

![Ambito dell'attività Bulk. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk.webp)

![Politica, prova senza salvataggio e pulsanti Start job ed Estimate. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk-actions.webp)

**Bulk** crea un'unica attività per più domini e più lingue. La stima non salva nulla. **Start job** aggiunge l'attività all'elenco **Jobs**. Nulla viene salvato finché l'attività non viene elaborata e **Allow publish / save** è attivo.

**Campi**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Section** | Back office | Quale catalogo legge l'attività. Stessa scelta di **Manual**. |
| **Theme** / **Module** | — | Compaiono solo per la sezione corrispondente, come in **Manual**. |
| **Source** | en-US oppure il valore di **Settings** | La lingua trattata come originale. Ogni lingua di destinazione viene tradotta a partire da questa. |
| **Targets** | nessuna | Una o più lingue da completare. Per selezionarne più d'una tenga premuto Ctrl (Cmd su Mac). Un semplice clic sostituisce la selezione. |
| **Domains** | nessuno | I domini compresi nell'attività. Per selezionarne più d'uno usi Ctrl o Cmd. Se non ne seleziona nessuno, l'attività copre tutti i domini della sezione scelta. |
| **Policy** | Fill empty | **Fill empty** invia solo i testi senza traduzione. **Overwrite all** invia tutti i testi, anche quelli già tradotti, e può sovrascriverli. **Outdated if equals source** invia solo i testi la cui traduzione è identica all'originale. |
| **Dry-run job** | No | Il modello svolge il lavoro e l'attività compare in **Jobs**, ma le risposte non arrivano nel negozio. Utile per verificare costi e qualità. |

**Passaggi**

1. Scelga la sezione, la lingua di origine, le lingue di destinazione, i domini e la politica.
2. Prema **Estimate**. Sopra il form compare la stima: numero di testi, numero di token previsto, costo e un campione di testi.
3. Se la stima è corretta, prema **Start job**. Si apre **Jobs** con la nuova attività.
4. Elabori l'attività in **Jobs** (3.5) oppure lasci fare il cron.

**Messaggi**

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Mistral and nothing was saved.** – risultato della stima.
- **Job #N is waiting (N strings, est. $X). It has not run yet.** – attività creata, in attesa.
- **Nothing was started. Select at least one target language.** – manca una lingua di destinazione.
- **Nothing was started. Pick a theme.** / **Nothing was started. Pick a module.** – scelga un tema o un modulo.
- **Nothing was started. There is no Mistral API key. Open Settings and paste the key. No job was created.** – manca la chiave.

### 3.5. Jobs

Accesso: scheda **Jobs**.

![Elenco delle attività. Con l'elenco vuoto compare No jobs yet. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-jobs.webp)

**Elenco delle attività**

Quando non c'è nessuna attività, la tabella mostra **No jobs yet.**

Ogni riga è un avvio da **Bulk**. Colonne: **#**, **Status**, **Locales** (lingua di origine → lingue di destinazione), **Progress** (eseguiti/totali), **Cost**, **Employee** e **Date**. **Open** apre l'attività.

Stati dell'attività, esattamente come appaiono a schermo:

- `pending` – in attesa, nulla è ancora stato elaborato. Non parte da sola.
- `running` – in corso.
- `paused` – in pausa. Non elabora oltre finché non la riprende.
- `cancelled` – annullata. I testi che aspettavano ancora non sono stati tradotti.
- `completed` – tutti i testi elaborati senza errori.
- `completed_with_errors` – terminata, ma una parte dei testi non è riuscita.
- `failed` – l'attività si è conclusa con un errore.

**Schermata dell'attività**

Aprendo un'attività vede l'intestazione **Job #N**, lo stato, l'avanzamento (**done/total**), il numero di **failed** e **skipped**, il costo, il collaboratore e l'etichetta **dry-run** se l'attività è di prova. La barra di avanzamento si aggiorna da sola ogni 2–3 secondi, finché l'attività resta aperta. La tabella sotto mostra le righe dell'attività: **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** ed **Error**.

Stati delle righe: `pending`, `processing`, `done`, `failed`, `skipped` (saltata perché corrisponde a un'esclusione oppure perché il testo era già tradotto) e `rolled_back` (annullata).

**Pulsanti**

- **Process slice** – elabora una porzione (**Batch size** testi) e si ferma. Messaggio: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Se non resta nulla da fare: **The job has no more strings waiting.**
- **Auto-process** – ripete le porzioni finché l'attività non termina o non si verifica un errore. Funziona nel browser, quindi solo finché la scheda resta aperta. Chiudere la scheda lo ferma: l'attività resta e si può completare con un altro **Process slice** o con il cron.
- **Pause** – mette in pausa l'attività. Messaggio: **Job paused. It will not translate more strings until you resume it.**
- **Resume** – la rimette in coda. Messaggio: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.** L'attività non riparte da sola.
- **Retry failed** – i testi con errore tornano in attesa e l'attività torna allo stato di attesa. Messaggio: **Retried N failed items.**
- **Rollback** – ripristina la traduzione precedente dove il modulo aveva salvato una copia prima della modifica. Deve prima confermare **Roll back this job?** Messaggio al termine: **Rollback: restored N translations.**
- **Error CSV** – scarica un file CSV con le righe in errore. Colonne: **id**, **domain**, **locale**, **source**, **error**.
- **Failed only** – mostra nella tabella solo le righe in errore.
- **Review queue** – porta a **Review** (3.6).

Nella schermata dell'attività non c'è un pulsante di annullamento. Per fermarla usi **Pause**.

**Pausa automatica**

Quando Mistral rifiuta le chiamate per un limite, l'attività si ferma da sola con lo stato `paused` e il messaggio nel campo dell'errore: **Rate limit — job auto-paused. Resume later.** Attenda e prema **Resume**. L'impostazione **Rate limit / min** in **Settings** riduce il numero di chiamate al minuto.

**Messaggi di errore**

- **Nothing was translated.** con l'aggiunta **No Mistral API key. Nothing was translated.** – manca la chiave, l'attività non parte. Incolli la chiave in **Settings**.
- **Allow publish is off in Settings.** – un'attività senza dry-run non parte finché non attiva **Allow publish / save**.
- **Monthly API budget has been exhausted.** – il budget mensile è esaurito. Aumenti **Budget USD / month** oppure imposti 0.

### 3.6. Review

Accesso: scheda **Review**, oppure il pulsante **Review queue** nella schermata di un'attività.

![Coda di Review. Con l'elenco vuoto compare The queue is empty. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-review.webp)

Sopra la tabella c'è l'intestazione **Needs-review queue (quality score / flags).** **Review** è l'elenco dei testi che il controllo di qualità non ha lasciato passare in automatico. Mostra fino alle 100 righe più recenti.

Colonne: **ID**, **Score**, **Domain**, **Source**, **AI** (proposta), **Flags** e i pulsanti **Approve** e **Reject**. Con l'elenco vuoto compare **The queue is empty.**

**Come leggere una riga**

- **Score** – punteggio da 0 a 100. Sotto 70 la riga va in revisione.
- **Flags** – motivi del blocco:
  - `validation_failed` – il testo non ha superato il controllo di variabili o HTML.
  - `warning` – una piccola segnalazione del controllo.
  - `length_explosion` – la traduzione è più di due volte e mezza più lunga dell'originale.
  - `too_short` – la traduzione è sensibilmente più corta di un originale più lungo.
  - `possible_untranslated` – nella traduzione sono rimaste parole inglesi, ad esempio the, and, with, your, please.
- **Source** – il testo originale. **AI** – la proposta del modello.

**Approve** e **Reject** cambiano solo lo stato della riga. Messaggio: **Review updated.** La riga scompare dall'elenco. Questa azione non inserisce testo nel negozio e non modifica il resto del dominio.

Se l'attività stava salvando risultati, la proposta potrebbe essere già arrivata nel negozio. Per annullare le modifiche di un'attività, usi **Rollback** nella schermata di quell'attività in **Jobs**.

### 3.7. Catalog

Accesso: scheda **Catalog**.

![Lotto del catalogo. Il pulsante Translate batch (max 100) si trova sotto il campo Start after ID. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-catalog.webp)

**Catalog** traduce i campi di prodotti, categorie e pagine CMS salvati nelle lingue del negozio. Non riguarda **International → Translations**. Un solo clic elabora al massimo 100 record. Il salvataggio avviene subito nei dati della lingua di destinazione scelta.

**Campi**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Entity** | product | Che cosa traduce: **product**, **category** oppure **cms**. Il cambio aggiorna la pagina e mostra solo l'elenco dei campi di quel tipo. Il solo cambio non traduce nulla. |
| **Fields** | tutti i campi dell'elenco | Quali testi invia il lotto. Selezioni solo quelli che devono cambiare. I campi non selezionati non vengono inviati e non cambiano. Per il prodotto: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Per la categoria: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Per il CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. |
| **Source language** | la prima lingua dell'elenco | La lingua da cui si prendono i testi. |
| **Target language** | la prima lingua dell'elenco | La lingua in cui va la traduzione. Deve essere diversa da quella di origine. |
| **Only empty** | Yes | Salta i campi che hanno già un testo nella lingua di destinazione. Lo disattivi solo se vuole sostituire il testo esistente. |
| **Start after ID** | 0 | Salta i record con un ID minore o uguale al valore inserito. Dopo un lotto il campo si imposta sull'ultimo ID elaborato. Prema di nuovo il pulsante per andare avanti. |

Pulsante: **Translate batch (max 100)**.

**Passaggi**

1. Scelga **Entity** e selezioni i campi.
2. Scelga **Source language** e **Target language**.
3. Lasci **Only empty** attivo.
4. Prema **Translate batch (max 100)**. Il risultato è: **Catalog finished: saved N, failed M.**
5. Apra un prodotto nella lingua di destinazione e controlli il risultato. Solo dopo disattivi **Only empty** o passi al lotto successivo.

**Messaggi**

- **Nothing was translated. Select at least one field.** – selezioni dei campi.
- **Nothing was translated. Source and target language must be different.** – scelga lingue diverse.
- **Nothing was saved. Turn on Allow publish in Settings.** – attivi **Allow publish / save**.
- **Nothing was translated. There is no Mistral API key. Open Settings and paste the key.** – manca la chiave.

### 3.8. Glossary

Accesso: scheda **Glossary**.

![Aggiunta di un termine. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary.webp)

![Importazione ed esportazione CSV ed elenco dei termini vuoto. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary-csv.webp)

Il glossario è un elenco di parole e frasi che il modello deve sempre conservare o tradurre allo stesso modo. Aggiungere una riga non cambia le traduzioni già salvate; la traduzione successiva, invece, terrà conto dell'elenco.

**Aggiunta di un singolo termine**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Source term** | vuoto, obbligatorio | La parola o l'espressione nella lingua di origine. La scriva esattamente come compare, con le maiuscole se contano. |
| **Target locale** | vuoto | Limita la riga a una sola lingua, ad esempio pl-PL. Se è vuoto, la riga vale per ogni lingua di destinazione. |
| **Target term** | vuoto | La traduzione approvata del termine. Può restare vuoto solo se **Do not translate** è attivo. |
| **Do not translate** | No | Attivo: il modello copia il termine senza modificarlo, ad esempio un nome di marchio, uno SKU o un tag. Disattivo: usa **Target term**. |

Pulsante: **Add**. Messaggi: **Glossary term added. Translations already stored were not changed.** oppure **Nothing was added. Type a source term.**

**Tabella**

Colonne: **Source**, **Locale**, **Target**, **Do not translate** (Yes o No) e il pulsante **Delete** su ogni riga. Elimina solo quella riga. Messaggio: **Glossary term deleted.** Elenco vuoto: **No glossary terms yet.**

**Importazione ed esportazione CSV**

- **CSV file** – scelga un file e prema **Import CSV**. Messaggio: **Imported N rows.**
- Formato del file: la prima riga è l'intestazione `source_term`, `target_locale`, `target_term`, `do_not_translate`. L'intestazione viene sempre saltata. Le righe con meno di tre colonne vengono saltate. Nella quarta colonna un valore vuoto o 0 significa **No**, qualsiasi altro valore significa **Yes**.
- L'importazione aggiunge le righe del file. Non verifica se un termine esiste già, quindi reimportare lo stesso file crea dei duplicati.
- **Export CSV** scarica l'elenco attuale come file `glossary.csv`. Non richiede un file in ingresso e non modifica nulla.

Suggerimento: usi termini brevi e precisi. Un termine troppo generico verrà imposto ogni volta che compare.

### 3.9. Excludes

Accesso: scheda **Excludes**.

![Modelli di esclusione. Con l'elenco vuoto compare No patterns yet. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-excludes.webp)

Un'esclusione è un modello di testo di origine che il modulo non invia a Mistral. Il testo resta nel negozio così com'è. Le esclusioni valgono su tutti i modi di lavorare: **Manual**, **Bulk**, **Catalog** e le pagine di traduzione.

**Aggiunta di un modello**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Pattern** | vuoto, obbligatorio | Il testo o l'espressione confrontato con ogni testo di origine. Il tipo di confronto dipende da **Type**. |
| **Type** | exact | **exact** – l'intero testo deve coincidere. **prefix** – il testo inizia con il modello. **contains** – il modello compare in un punto qualsiasi. **regex** – espressione regolare PHP. |

Pulsante: **Add**. Messaggio: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Campo vuoto: **Nothing was added. Type a pattern.**

Un modello di tipo **regex** viene applicato esattamente come lo ha scritto. Un'espressione errata non corrisponde a nulla. Parta da un modello breve e verifichi che cosa ha saltato.

**Tabella**

Colonne: **Pattern**, **Type**, **On** e **Delete**. La colonna **On** mostra 1 per un modello attivo. In questa schermata non c'è un interruttore: per disattivare un modello bisogna eliminarlo e aggiungerlo di nuovo. **Delete** elimina solo quel modello; le traduzioni esistenti restano. Messaggio: **Pattern deleted.** Elenco vuoto: **No patterns yet.**

Usi le esclusioni per i testi che devono restare nella lingua di origine, ad esempio una denominazione legale o un tag tecnico. Per i testi che devono sempre essere tradotti nello stesso modo serve **Glossary**.

### 3.10. History

Accesso: scheda **History**, oppure il pulsante **See all** nel **Dashboard**.

![Elenco della cronologia. Con l'elenco vuoto compare No requests yet. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-history.webp)

**History** è l'elenco completo delle chiamate a Mistral registrate: traduzioni manuali, pagine di traduzione, attività **Bulk**, **Catalog** e test di connessione. Ogni voce contiene il testo inviato, la risposta, il modello, le lingue, il numero di token e la durata della chiamata. Schede, grafici e filtri si trovano in **Dashboard**, non su questa pagina. Aprire questa pagina non invia richieste e non modifica le traduzioni. La nota sotto il campo **Model** in **Settings** parla di **Logs**: le voci sono proprio queste, ma non esiste una scheda Logs separata.

**Colonne dell'elenco:** **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** e **Prompt**. Tipi: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** e **Not sent** (la chiamata non è partita, ad esempio per il limite locale o il budget). Nelle voci di **Bulk job** compare il numero dell'attività.

- **View** apre una finestra con l'istruzione inviata e la risposta. In caso di errore, al posto della risposta compare il messaggio d'errore.
- Una voce con errore di accesso significa che la chiave in **Settings** è errata o che l'account non può usare il modello scelto.
- **Previous**, **Next** e il campo **Page** consentono di scorrere le pagine dell'elenco.
- **Clear history** elimina queste voci. Deve confermare con il messaggio **Clear the stored history? Saved translations stay.** Al termine compare **History cleared. Saved translations were not changed.**

Quando le traduzioni si fermano all'improvviso, apra la voce con errore più recente in questa pagina prima di modificare il glossario.

### 3.11. Updates

Accesso: scheda **Updates** sulla destra del menu.

![Controllo degli aggiornamenti. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-updates.webp)

Il pannello si chiama **MyPresta Updates**.

- **Manual Check** – il pulsante **Check Now** verifica subito la versione.
- **Automatic Notifications** – **Enabled** oppure **Disabled**. Se attivo, il modulo controlla se sul server MyPresta è disponibile una versione più recente e mostra un avviso nel back office.
- **Product Page** – il link alla pagina del modulo.
- **Save** – salva la scelta fatta in **Automatic Notifications**.

Messaggi: **Update settings saved.**, **New version available!**, **Module is up to date!**

### 3.12. Pulsanti nella pagina International → Translations

Accesso: **International** → **Translations**. Scelga il tipo di traduzione e la lingua, poi prema **Modify**. I pulsanti accanto ai campi compaiono quando in **Settings** è attivo **Individual field buttons — International → Translations**. Le caselle e la barra compaiono quando è attivo **Individual field checkboxes — International → Translations**.

![Barra Mistral translations in fondo alla pagina International → Translations. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-translations-page.webp)

**Che cosa si vede**

- Accanto a ogni campo di testo, il pulsante che traduce quel campo.
- Accanto a ogni campo, una casella di selezione (quando le caselle sono attive).
- La barra **Mistral translations**: il campo **Source** (di default en-US oppure il valore di **Settings**), l'elenco **Target**, i pulsanti **Check all**, **Uncheck all**, **Check empty**, **Translate empty** e **Translate selected**, con il suggerimento **Fills the fields. Save with the PrestaShop button.**

**Passaggi**

1. Scelga **Target**.
2. Selezioni i campi da compilare oppure prema **Check empty**.
3. Prema **Translate selected** oppure **Translate empty**, che compila i campi vuoti della sezione.
4. Attenda che la barra mostri **Done (N)**. Durante il lavoro vede **Translating… N/M**.
5. Controlli i campi compilati e salvi la pagina con il pulsante **Save** di PrestaShop.

I pulsanti si limitano a compilare i campi. Senza **Save** di PrestaShop il testo non arriva nel negozio. Con **Allow publish / save** disattivato i campi vengono comunque compilati, e il salvataggio lo esegue PrestaShop.

**Messaggi**

- **Target is not a language from this shop.** – la lingua scelta non esiste in questo negozio.
- **Fill the source language field first.** – compili prima il campo della lingua di origine.
- **The source language field is not on this page.** – in questa pagina non c'è un campo per la lingua di origine.
- **The source language mail file was not found.** – il file di origine dell'e-mail non è stato trovato. In **Settings** scelga un altro **Source locale** per il quale esistono file di e-mail.

Per la sezione **Emails** il testo di origine proviene dal file di origine del modello di e-mail, non da un campo della pagina.

### 3.13. Pulsanti nei form di prodotto, categoria e CMS

Accesso: il form di un prodotto, di una categoria, di una pagina CMS o di un altro form del negozio con campi multilingua. I pulsanti sono visibili quando in **Settings** sono attivi **Individual field buttons — shop forms** e **Individual field checkboxes — shop forms**.

![Barra in fondo al form di prodotto e casella di selezione accanto a un campo multilingua. Schermata in inglese.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-product-form.webp)

**Che cosa si vede**

- Accanto a ogni campo multilingua, il pulsante che traduce quel campo.
- Accanto ai campi, la casella per inserirli nella barra.
- Una barra in fondo alla pagina del prodotto con l'etichetta **Mistral translations**, l'elenco delle lingue **Translate from … to …**, i pulsanti **Check all**, **Uncheck all**, **Check empty**, **Translate empty** e **Translate selected** e il suggerimento **Fills the fields. Save with the PrestaShop button.**

**Passaggi**

1. Compili il campo nella lingua di origine. Senza di esso la barra mostra **Fill the source language field first.**
2. Scelga la lingua di destinazione nella barra.
3. Prema il pulsante accanto a un singolo campo, oppure selezioni più campi e prema **Translate selected**. **Translate empty** compila i campi vuoti.
4. Al termine prema **Save** nel form di PrestaShop. Senza questo passaggio il testo non viene salvato.

Il pulsante si limita a compilare il campo nel form. A salvare è solo il pulsante **Save** del form di prodotto, categoria o CMS. I campi che non ha selezionato restano invariati.

## 4. Front del negozio

Il modulo non aggiunge nulla alle pagine del negozio che vede il cliente. Il cliente non ha schermate né pulsanti legati al modulo, quindi nel tema non c'è niente da controllare.

L'unico indirizzo fuori dal back office è quello del cron. È pensato per un'attività pianificata sul server e non per l'uso da parte dei clienti.

- **Dove copiare l'indirizzo:** **Settings** → **CRON URL**, oppure **Dashboard** → riga **CRON**.
- **Cosa fare:** incolli l'indirizzo nel pianificatore di attività del server, ad esempio ogni pochi minuti. Ogni chiamata elabora una porzione di un'attività in attesa.
- **L'indirizzo funziona in HTTPS.** Se il negozio usa SSL, usi l'indirizzo che inizia con `https://`.

| Cosa si vede aprendo l'indirizzo | Cosa fare |
|---|---|
| Il messaggio **Forbidden** | L'indirizzo è incompleto o è cambiato. Lo copi di nuovo da **Settings**. |
| Il messaggio **No pending jobs** | Non ci sono attività in attesa o in corso. Crei un'attività in **Bulk**, oppure riprenda una di quelle in pausa in **Jobs**. |
| Dati in formato JSON con il risultato della porzione (campi `ok`, `finished`, `counts`) | È stata elaborata una porzione dell'attività. Controlli l'avanzamento in **Jobs**. |

Il cron gestisce solo le attività con stato `pending` e `running`. Un'attività `paused` va ripresa a mano.

## 5. Problemi comuni

| Sintomo (cosa si vede) | Causa | Cosa fare |
|---|---|---|
| **No Mistral API key.** in ogni pagina del modulo | La chiave non è stata salvata. | Vada in **Settings**, incolli la chiave in **Mistral API key** e prema **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Le impostazioni sono state salvate senza chiave. | Incolli la chiave in **Mistral API key** e prema **Save**. |
| **Connection was not made. Nothing was translated.** dopo **Test connection** | Chiave errata, nessuna connessione con il server oppure modello non disponibile per l'account. | Controlli la chiave, scelga un altro **Model** oppure aggiunga un identificativo corretto in **Add a Mistral model**. I dettagli sono in **History**. |
| Le chiamate terminano con un errore di accesso in **History** | La chiave è errata oppure l'account non può usare il modello scelto. | Corregga la chiave oppure scelga un modello disponibile per l'account. |
| **Nothing was started. There is no Mistral API key.** in **Bulk** | Manca la chiave. | Incolli la chiave in **Settings**, poi esegua di nuovo **Estimate** e **Start job**. |
| L'attività resta in `pending` e non succede nulla | L'attività non parte da sola. | Prema **Process slice** oppure **Auto-process** in **Jobs**. Oppure imposti il cron (sezione 4). |
| Attività in `paused` con il messaggio **Rate limit — job auto-paused. Resume later.** | Mistral ha rifiutato le chiamate per un limite. | Attenda qualche minuto e prema **Resume**. Riduca **Batch size** o **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | È stato superato **Budget USD / month**. | Aumenti l'importo oppure imposti 0. Il nuovo mese riparte da zero. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** è disattivato. | Attivi **Allow publish / save** in **Settings**. |
| **Not saved because of broken placeholders or HTML: N.** in **Manual** | La traduzione ha modificato variabili o marcatori HTML. | Corregga la riga a mano nella tabella di revisione, in modo che variabili e marcatori siano come nell'originale, poi salvi. |
| L'attività termina con lo stato `completed_with_errors` | Una parte dei testi non è riuscita. | Apra l'attività, selezioni **Failed only**, scarichi **Error CSV** e prema **Retry failed**. |
| Le righe in **Review** hanno uno **Score** basso | Il controllo di qualità non le ha fatte passare. | Legga **Source** e **AI**. Approvi con **Approve** oppure rifiuti con **Reject**. In caso di salvataggio errato usi **Rollback** nell'attività. |
| Traduzione salvata, ma nel negozio compare ancora il vecchio testo | Il salvataggio svuota la cache di PrestaShop, ma il tema o il browser possono conservare la pagina precedente. | Vada in **Advanced Parameters** → **Performance**, svuoti la cache e aggiorni la pagina del negozio. |
| **Exclude pattern** non salta il testo | **Type** sbagliato oppure espressione **regex** errata. | In **Excludes** cambi il tipo oppure elimini il modello e lo aggiunga di nuovo con un testo più breve. |
| Un nuovo termine del glossario non compare nelle traduzioni salvate | Il glossario vale per le nuove traduzioni. I testi salvati non vengono modificati. | Rilanci la traduzione di quei testi in **Bulk** con la politica **Overwrite all**, dopo aver verificato la stima in **Estimate**. |
| **The source language mail file was not found.** | Per la lingua di origine scelta non esiste il file dell'e-mail. | Scelga in **Settings**, oppure nella pagina delle traduzioni, un altro **Source locale** per il quale esistono file di e-mail. |
| **No strings match this filter. Nothing was sent to Mistral.** | Il filtro non corrisponde a nessun testo. | Disattivi **Only empty**, svuoti **Search** oppure scelga un altro dominio. |
| **Nothing was translated. Tick at least one row.** | Nessuna riga è selezionata. | Selezioni le righe e prema **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** in **Catalog** | La stessa lingua è indicata come origine e come destinazione. | Scelga un'altra **Target language**. |
| Dashboard mostra un riepilogo vuoto | Il negozio non ha ancora un catalogo per la lingua scelta. | Crei il catalogo in **International → Translations** e torni alla **Dashboard**. |
| La cronologia contiene voci **Not sent** | Il limite locale o il budget ha fermato la chiamata. | Controlli **Rate limit / min** e **Budget USD / month** in **Settings**. |

## 6. Per lo sviluppatore

### 6.1. Panoramica

- **Classe principale:** `myaitranslationsmistral`, file `myaitranslationsmistral.php`.
- **Versione:** 1.2.0.
- **Nome tecnico:** `myaitranslationsmistral`. Nell'elenco dei moduli compare come **AI Translations with Mistral**.
- **Autore:** MyPresta.eu. Scheda del modulo in Module Manager: `administration`.
- **Scheda del back office:** `AdminMyaitranslationsmistral`, genitore `AdminInternational` (in alternativa `IMPROVE`).
- **Installazione:** `parent::install()`, tabelle da `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), valori predefiniti tramite `installDefaults()` (vengono impostate solo le chiavi mancanti), registrazione degli hook `displayBackOfficeHeader` e `actionAdminControllerSetMedia`, creazione della scheda.
- **Disinstallazione:** rimozione della scheda, esecuzione di `sql/uninstall.php` (elimina 11 tabelle), rimozione delle chiavi `MYAITMI_*` tramite `removeConfiguration()`, poi `parent::uninstall()`.
- Il modulo **non** ha i metodi `enable()` e `disable()`.
- **Configurazione:** `getContent()` reindirizza a `AdminMyaitranslationsmistral` (di default la scheda `dashboard`).

**Flusso dei dati**

1. I form di `MyaitmiForms` (scheda `settings`) inviano i valori a `AdminMyaitranslationsmistralController::initContent()`.
2. `MyaitmiConfigService::saveFromForm()` salva le chiavi `MYAITMI_*` in `Configuration`. La chiave API viene cifrata da `MyaitmiApiKeyEncryptor` (AES-256-CBC, chiave derivata da `_COOKIE_KEY_`) e salvata in `MYAITMI_API_KEY_ENC`.
3. Traduzione: `MyaitmiTranslateService::translateMessages()` costruisce le istruzioni (`MyaitmiPromptBuilder`), le invia tramite `MyaitmiMistralTranslationProvider` (cURL, POST su `https://api.mistral.ai/v1/chat/completions`), verifica la risposta (`MyaitmiPlaceholderValidator`, `MyaitmiHtmlValidator`, `MyaitmiPsNativeValidator`), la valuta (`MyaitmiQualityScorer`) e la salva tramite `MyaitmiTranslationAdapter`.
4. Salvataggio della traduzione: tramite il servizio `prestashop.service.translation`; se il servizio manca, direttamente nella tabella `_DB_PREFIX_translation`. Le chiavi dei moduli classici (nella forma `<{nome}prestashop>…`) vengono scritte nel file `translations/{iso}.php` di quel modulo (`MyaitmiLegacyModuleCatalogue`).
5. Bulk: `MyaitmiBulkJobFactory` crea l'attività e le righe in `myaitmi_job` e `myaitmi_job_item`. `MyaitmiJobWorker::processSlice()` elabora una porzione (dimensione da `BATCH_SIZE`). La richiamano il pulsante **Process slice** (richiesta della scheda **Jobs**), il ciclo **Auto-process** nel browser (AJAX `ProcessJob`) oppure il cron (`controllers/front/cron.php`).
6. Catalog: `MyaitmiCatalogTranslateService` seleziona i record (`collect()`, al massimo 100) e li salva direttamente in `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` o `_DB_PREFIX_cms_lang`.
7. Ogni chiamata viene registrata in `myaitmi_request` (scheda **History**) e gli errori in `myaitmi_api_log`. Il costo finisce in `myaitmi_usage_ledger`. Prima che un'attività modifichi un testo, `MyaitmiSnapshotService` ne copia il valore precedente in `myaitmi_snapshot`, così è possibile annullare con **Rollback**.

### 6.2. File

| File | A cosa serve |
|---|---|
| `myaitranslationsmistral.php` | Classe principale: installazione, disinstallazione, scheda di menu, hook, caricamento degli asset, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Controllo degli aggiornamenti (scheda **Updates**, avviso nel back office). |
| `logo.png`, `logo.gif` | Logo nell'intestazione delle schede e nel menu del modulo. |
| `controllers/admin/AdminMyaitranslationsmistralController.php` | L'intero back office: schede, salvataggi, azioni sulle attività, glossario, esclusioni, catalogo, CSV, risposte AJAX. |
| `controllers/front/cron.php` | Indirizzo cron: elabora una porzione di attività e restituisce JSON. |
| `sql/install.php`, `sql/uninstall.php` | Creazione ed eliminazione delle tabelle. |
| `src/Adapter/MyaitmiTranslationAdapterInterface.php` | Interfaccia di lettura e scrittura delle traduzioni PrestaShop. |
| `src/Adapter/MyaitmiAbstractTranslationAdapter.php` | Logica comune dell'adattatore: elenchi di sezioni, domini e lingue, salvataggio tramite servizio o tabella `translation`, pulizia della cache. |
| `src/Adapter/MyaitmiTranslationAdapter.php` | Adattatore concreto (usato dalla factory). |
| `src/Adapter/MyaitmiTranslationAdapterFactory.php` | Crea l'adattatore. |
| `src/Adapter/MyaitmiFilesystemCatalogueTrait.php` | Lettura dei cataloghi XLF di temi e moduli (domini). |
| `src/Adapter/MyaitmiLegacyModuleCatalogue.php` | Moduli classici: lettura e scrittura di `translations/{iso}.php`, pulizia di OPcache dopo il salvataggio. |
| `src/Admin/MyaitmiForms.php` | Costruzione di tutti i form del back office e delle descrizioni dei campi (`desc`). |
| `src/Admin/MyaitmiSectionHelp.php` | Testi del pannello **Help** per ogni scheda. |
| `src/Audit/MyaitmiRequestLogRepository.php` | Cronologia delle chiamate, schede, grafici, filtri, pulizia, conservazione. |
| `src/Audit/MyaitmiApiLogRepository.php` | Log di errori e avvisi dell'API, conservazione. |
| `src/Audit/MyaitmiTranslationMemory.php` | Memoria di traduzione (cache): riutilizzo del risultato per lo stesso testo, la stessa lingua, lo stesso modello e lo stesso glossario. |
| `src/Audit/MyaitmiUsageLedger.php` | Costo secondo la tabella dei prezzi nel codice, budget mensile. |
| `src/Audit/MyaitmiSnapshotService.php` | Copie prima del salvataggio e annullamento dell'attività. |
| `src/Glossary/MyaitmiGlossaryRepository.php` | Glossario: elenco, salvataggio, eliminazione. |
| `src/Glossary/MyaitmiExcludePatternRepository.php` | Esclusioni: aggiunta, eliminazione, corrispondenza. |
| `src/Job/MyaitmiJobStatuses.php` | Costanti degli stati di attività e righe. |
| `src/Job/MyaitmiJobRepository.php` | Attività e righe: lettura, cambio di stato, recupero delle porzioni, ricalcolo dei contatori. |
| `src/Job/MyaitmiJobWorker.php` | Elaborazione delle porzioni, nuovi tentativi per gli errori, chiusura dell'attività, coda di revisione, e-mail al termine. |
| `src/Provider/MyaitmiTranslationProviderInterface.php` | Interfaccia del fornitore di traduzioni. |
| `src/Provider/MyaitmiMistralTranslationProvider.php` | Chiamate a Mistral (cURL), test di connessione, salvataggio della cronologia delle chiamate. |
| `src/Provider/MyaitmiPromptBuilder.php` | Costruzione delle istruzioni di sistema e utente (tono, voce del marchio, glossario). |
| `src/Provider/MyaitmiProviderFactory.php` | Crea il fornitore. |
| `src/Quality/MyaitmiPlaceholderValidator.php` | Controllo di variabili e marcatori nel testo. |
| `src/Quality/MyaitmiHtmlValidator.php` | Controllo della correttezza dell'HTML. |
| `src/Quality/MyaitmiPsNativeValidator.php` | Controllo prima del salvataggio nella sezione **Manual**. |
| `src/Quality/MyaitmiEmailHtmlPipeline.php` | Protezione dell'HTML dei modelli di e-mail prima dell'invio e ripristino dopo la risposta. |
| `src/Quality/MyaitmiQualityScorer.php` | Valutazione 0–100, flag e decisione sulla revisione. |
| `src/Security/MyaitmiApiKeyEncryptor.php` | Cifratura e decifratura della chiave API. |
| `src/Service/MyaitmiConfigService.php` | Lettura e salvataggio delle impostazioni, dei modelli, del token cron e validazione degli intervalli. |
| `src/Service/MyaitmiRateLimiter.php` | Limite locale di chiamate al minuto (file `var/rate_limit.json`). |
| `src/Service/MyaitmiTranslateService.php` | Flusso principale di traduzione: esclusioni, memoria, chiamate, validazione, valutazione, salvataggio, stima. |
| `src/Service/MyaitmiBulkJobFactory.php` | Costruzione dell'attività **Bulk** e della stima. |
| `src/Service/MyaitmiCatalogTranslateService.php` | Raccolta e salvataggio dei record di **Catalog**. |
| `src/Service/MyaitmiDashboardService.php` | Riepilogo dei testi mancanti nel **Dashboard**. |
| `translations/*.php` | Traduzioni dell'interfaccia (un file per lingua). |
| `views/templates/admin/configure.tpl` | Template dell'intera pagina del back office e del pannello **Help**. |
| `views/templates/admin/_partials/*.tpl` | Schede: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Stili del back office. |
| `views/js/admin.js` | Scheda **Jobs** (avanzamento, **Auto-process**), selezione delle righe, risposte AJAX. |
| `views/js/admin-help.js` | Pannello **Help**. |
| `views/js/translations-tool.js` | Pulsanti e barra in **International → Translations**. |
| `views/js/entity-fields.js` | Pulsanti e barra nei form di prodotto, categoria e CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Grafici nel **Dashboard**. |
| `var/rate_limit.json` | Contatore del limite locale di chiamate nel minuto corrente. |
| `index.php` (in ogni directory) | Protezione contro la navigazione nelle directory. |

### 6.3. Controller

**Back office: `AdminMyaitranslationsmistralController`** (classe `ModuleAdminController`, scheda sotto `AdminInternational`).

- Indirizzo: `index.php?controller=AdminMyaitranslationsmistral&token=…`, facoltativamente `&myaitmi_tab=…`.
- Valori ammessi per `myaitmi_tab`: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (**History**), `review`, `catalog`, `updates`. Qualsiasi altro valore porta a `dashboard`.
- Parametri in ingresso (GET/POST):
  - Impostazioni: campi `MYAITMI_*` del form, `new_mistral_model`, `delete_mistral_model`, pulsanti `submitMyaitranslationsmistralSettings`, `…Ping`, `…AddModel`.
  - Filtri e traduzione: `section`, `theme`, `module`, `domain`, `source_locale`, `target_locale`, `only_empty`, `search`, `selected_keys[]`, `save_now`, `review_key[]`, `review_value[]`, `review_approve[]`, `review_source[]`.
  - Bulk: `target_locales[]`, `domains[]`, `policy_mode` (`fill_empty`, `overwrite`, `outdated_if_changed`), `dry_run`, `bulk_step` (`estimate`).
  - Attività: `id_job`, `job_action` (`pause`, `resume`, `cancel`, `process`, `retry_failed`, `rollback`, `export_errors`), `filter_failed`.
  - Revisione: `review_action` (`approve`, `reject`) e `id_review`.
  - Catalog: `entity_type` (`product`, `category`, `cms`), `id_lang_source`, `id_lang_target`, `catalog_fields_{entity}[]`, `catalog_start_id`, `only_empty`.
  - Glossario ed esclusioni: `source_term`, `target_locale`, `target_term`, `do_not_translate`, `glossary_csv` (file), `pattern`, `pattern_type`, `delete_glossary`, `delete_exclude`.
  - Cronologia e schede: `dash_locale`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_q`, `stats_preset`, `hist_id`.
- Restituisce una pagina HTML (`configure.tpl`) oppure dei file: `glossary.csv` (esportazione del glossario) o `job-{id}-errors.csv` (errori dell'attività).
- I messaggi di successo ed errore vengono passati nei parametri `flash` e `flash_kind` (`info`, `success`, `warning`, `danger`).

**Azioni AJAX del back office** (`index.php?controller=AdminMyaitranslationsmistral&ajax=1&action=…`):

| `action` | Parametri | Restituisce |
|---|---|---|
| `ProcessJob` | `id_job` | Risultato della porzione: `ok`, `finished`, `paused`, `rate_limited`, `counts`, `job`. |
| `JobStatus` | `id_job` | `ok` e l'oggetto `job`. |
| `TranslatePageLines` | `items` (JSON), `source_locale`, `target_locale` | `translations` (id → testo), `error`. Non salva. |
| `MailSource` | `template`, `kind` (`html`/`txt`), `module`, `theme` | Il file di origine dell'e-mail. |
| `ListDomains` | `section`, `locale`, `theme`, `module` | Elenco `domains`. |
| `HistoryDetail` | `hist_id` | Dettagli della chiamata. |

**Front: `MyaitranslationsmistralCronModuleFrontController`** (`ajax = true`, `ssl = true`).

- Indirizzo: `index.php?fc=module&module=myaitranslationsmistral&controller=cron&token=…`, facoltativamente `&id_job=N`.
- `token` è obbligatorio e viene confrontato con `MYAITMI_CRON_TOKEN` tramite `hash_equals()`. Un token errato restituisce il codice 403 e il JSON `{"ok":false,"error":"Forbidden"}`.
- Con `id_job`: elabora una porzione di quell'attività.
- Senza `id_job`: prende la prima attività con stato `pending` o `running` tra le ultime 20. Se non ce n'è nessuna, restituisce `{"ok":true,"message":"No pending jobs"}`.

### 6.4. Hook

Registrati durante l'installazione:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: sostituisce il nome tecnico della scheda con l'etichetta (`renameTabIfTechnical()`) e carica gli asset del back office (`loadBoAssets()`).
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: carica gli asset (`loadBoAssets()`).

Asset caricati da `loadBoAssets()`:

- Nella scheda del modulo: `admin.css`, `admin.js`, `admin-help.js`; nella scheda **Dashboard** anche `chart.min.js` e `history-charts.js`. `Media::addJsDef` con `aitHelpLabels`.
- Nella pagina **International → Translations** (`AdminTranslations` oppure l'indirizzo `/international/translations`), quando i pulsanti di quella pagina sono attivi: `admin.css` e `translations-tool.js`.
- Nelle altre pagine del back office (form di prodotti, categorie, CMS), quando i pulsanti dei form sono attivi: `admin.css` e `entity-fields.js`.
- Dati per JS: `Media::addJsDef(['myaitmiTr' => …])` con l'elenco delle lingue, i locale, i flag dei pulsanti e le etichette (`translationClientConfig()`).

Il modulo non espone hook propri (nessun `Hook::exec`).

### 6.5. Override

Il modulo non sovrascrive alcuna classe né alcun controller di PrestaShop. Non esiste una directory `override`.

### 6.6. Database

Tabelle create in `sql/install.php` (`_DB_PREFIX_` è il prefisso del negozio, di default `ps_`). Tutte usano il motore `_MYSQL_ENGINE_` e `utf8mb4_unicode_ci`.

| Tabella | Contenuto |
|---|---|
| `myaitmi_glossary` | `id_myaitmi_glossary`, `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, `date_add`, `date_upd`. Chiave `idx_shop_locale` (`id_shop`, `target_locale`). Lettura: `id_shop` IN (0, negozio). |
| `myaitmi_exclude_pattern` | `id_myaitmi_exclude_pattern`, `pattern` (VARCHAR 512), `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled` (sempre 1 all'inserimento), `date_add`. |
| `myaitmi_job` | `id_myaitmi_job`, `uuid` (univoco), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, `items_total`, `items_done`, `items_failed`, `items_skipped`, `tokens_prompt`, `tokens_completion`, `cost_usd_estimate`, `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`, `date_add`, `date_upd`. Chiave `idx_status`. |
| `myaitmi_job_item` | `id_myaitmi_job_item`, `id_myaitmi_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`, `date_add`, `date_upd`. Chiave `idx_job_status`. Una porzione corrisponde a una lingua di destinazione. |
| `myaitmi_memory` | Memoria di traduzione: `memory_hash` (univoco), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitmi_usage_ledger` | `usage_date`, `id_myaitmi_job`, `model`, `tokens_prompt`, `tokens_completion`, `cost_usd`, `date_add`. La somma mensile calcola il budget. |
| `myaitmi_snapshot` | Copia prima del salvataggio: `id_myaitmi_job`, `id_myaitmi_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. |
| `myaitmi_api_log` | Log di errori e avvisi: `id_myaitmi_job`, `level`, `provider`, `http_code`, `message`, `context_json`, `date_add`. Conservazione secondo `MYAITMI_LOG_RETENTION_DAYS`. |
| `myaitmi_review` | Coda di revisione: `id_myaitmi_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`, `date_add`, `date_upd`. |
| `myaitmi_catalog_item` | Creata all'installazione ed eliminata alla disinstallazione. Il codice del modulo non vi scrive; **Catalog** salva direttamente nelle tabelle linguistiche del negozio. |
| `myaitmi_request` | Cronologia delle chiamate: `request_type` (`translate`, `manual`, `page`, `job`, `catalog`, `ping`, `blocked`), `status`, `model`, `source_locale`, `target_locale`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `cost_usd`, `id_employee`, `id_myaitmi_job`, `item_count`, `prompt`, `reply`, `error_message`, `date_add`. Se manca, la tabella viene creata da `ensure()` al primo salvataggio o all'apertura di **History**. |

La disinstallazione elimina tutte le 11 tabelle dell'elenco sopra. Le tabelle delle traduzioni di PrestaShop (`_DB_PREFIX_translation`) e le tabelle linguistiche di prodotti, categorie e CMS non vengono eliminate.

### 6.7. Chiavi e traduzioni

**Chiavi `Configuration`** (prefisso `MYAITMI_`), con i valori predefiniti di `installDefaults()`:

| Chiave | Predefinito | Note |
|---|---|---|
| `API_KEY_ENC` | `''` | Chiave API cifrata. Lettura tramite `MyaitmiConfigService::getApiKey()`. |
| `MODEL` | `mistral-small-latest` | Modello attivo. |
| `EXTRA_MODELS` | `''` | Identificativi dei modelli aggiunti a mano, uno per riga. |
| `PROVIDER` | `mistral` | Sempre `mistral` dopo il salvataggio del form. |
| `TONE` | `formal` | `formal`, `casual` oppure `brand`. |
| `CUSTOM_VOICE` | `''` | Testo di **Brand voice**. |
| `BATCH_SIZE` | `25` | Intervallo 1–100. |
| `MONTHLY_BUDGET` | `0` | USD, 0 = nessun limite. |
| `SOURCE_LOCALE` | `''` | Vuoto = la lingua è indicata dalla schermata. |
| `TEMPERATURE` | `0.2` | Intervallo 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Intervallo 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | 0 disattiva il limite locale. |
| `LOG_RETENTION_DAYS` | `30` | Minimo 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Invio di un'e-mail al termine dell'attività (modello `contact`). |
| `NOTIFY_EMAIL` | `''` | Indirizzo del destinatario. Se vuoto, si usa `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Salvataggio nel negozio. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Pulsanti e barra nei form del negozio. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Pulsanti e barra nella pagina delle traduzioni. |
| `MAX_TOKENS` | `0` | 0 = limite predefinito del fornitore. |
| `CRON_TOKEN` | esadecimale casuale di 32 caratteri | Token dell'indirizzo cron. Viene generato anche alla prima lettura, se manca. |

Chiavi rimosse al salvataggio del form o alla disinstallazione: `DEEPL_API_KEY` e `CLAUDE_API_KEY` (residui di versioni precedenti). Le chiavi del controllo aggiornamenti (`mypresta_updates`, `update_{nome}`, `updatev_{nome}`) non vengono eliminate.

**Traduzioni dell'interfaccia.** Ogni lingua è `translations/{iso}.php` (ad esempio `pl.php`, `de.php`, `fr.php`). Il file `en.php` è la fonte delle stringhe. Le stringhe passano da `$this->l()` oppure dai domini `myaitmiforms` e `sectionhelp` (descrizioni dei campi e pannello **Help**). Le stringhe dei template si scrivono `{l s='…' mod='myaitranslationsmistral'}`. Anche le stringhe passate a JS (`labels` in `translationClientConfig()` e `aitHelpLabels`) passano da `$this->l()`.

Per aggiungere una lingua: copi `translations/en.php` in `translations/{iso}.php`, traduca i valori e mantenga invariati gli identificativi delle chiavi.

### 6.8. Estensione

- **Tema del negozio:** il modulo non genera nulla nel tema, quindi non c'è alcun template da sovrascrivere.
- **Fornitore di traduzioni:** un nuovo fornitore richiede una classe conforme a `MyaitmiTranslationProviderInterface` e una modifica a `MyaitmiProviderFactory`. Al momento la factory restituisce solo Mistral.
- **Adattatore del catalogo:** l'interfaccia `MyaitmiTranslationAdapterInterface` e la factory `MyaitmiTranslationAdapterFactory`.
- **Listino:** le tariffe per milione di token sono scritte in `MyaitmiUsageLedger::estimateCost()`. Se Mistral cambia i prezzi, vanno aggiornati nel codice.
- **Limite locale:** il file `var/rate_limit.json` viene creato nella directory del modulo.

## 7. Assistenza

Pagina del modulo: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html

Se ha bisogno di aiuto con il modulo:

1. Acceda al suo account cliente su mypresta.eu.
2. Vada alla pagina dei contatti e scelga l'argomento **Support for paid modules**. Il modulo indica che per i moduli a pagamento è richiesto l'accesso.
3. Dopo l'accesso, scelga questo modulo dalla cronologia degli acquisti.
