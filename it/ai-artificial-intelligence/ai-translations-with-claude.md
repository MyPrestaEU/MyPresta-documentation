---
title: "AI Translations with Claude - documentazione e manuale utente"
description: "Manuale di configurazione e risoluzione dei problemi per chi ha già installato il modulo AI Translations with Claude."
sidebar:
  label: "AI Translations with Claude - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo AI Translations with Claude su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-claude.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/ai-translations-with-claude/)
>
> ---


## 1. Requisiti

Il modulo funziona con PrestaShop 1.7.0.0 e versioni successive, incluse PrestaShop 8 e 9.

- **PrestaShop:** 1.7.0.0 o successiva.
- **PHP:** 5.6 o successiva.
- **Estensioni PHP:** cURL, OpenSSL, SimpleXML e mbstring.
- **Altri moduli:** il modulo non richiede nessun altro modulo.
- **Fuori dal negozio:** un account Anthropic e una chiave API, che si crea su https://console.anthropic.com/settings/keys. Il server del negozio deve poter raggiungere `https://api.anthropic.com/v1/messages`.
- **Facoltativo:** un'attività pianificata sul server che richiama l'indirizzo cron indicato in **Settings**. Senza di essa, i job si elaborano a mano da **Jobs**.
- **Cataloghi grandi:** un dominio con migliaia di stringhe richiede molte chiamate API. Il job viene diviso in porzioni della dimensione di **Batch size**. Prima di iniziare, esegua **Estimate** su **Bulk** per vedere la stima.
- Il negozio deve avere almeno due lingue. Con una sola lingua, il back office mostra **The shop needs at least two languages.** e non c'è nulla da tradurre.

## 2. Installazione

1. Apra **Modules**, poi **Module Manager**. Scelga **Upload a module**, carichi il file ZIP e prema **Install** accanto a **AI Translations with Claude**.
2. Dopo l'installazione, **AI Translations with Claude** compare nel menu **International**.
3. L'installazione non svuota la cache del negozio. Il modulo la svuota quando salva una traduzione.

Apra poi **AI Translations with Claude**, passi a **Settings** e incolli la sua chiave Claude. Finché non viene salvata una chiave, ogni pagina del modulo mostra **No Claude API key.** con il link **Open Settings**.

**Disinstallazione.** In **Module Manager** prema **Uninstall** e confermi **Delete this module and its data (jobs, glossary, cache)?**

- La voce di menu scompare. Vengono eliminati job, glossario, pattern di esclusione, cronologia delle chiamate, coda **Review**, copie per il **Rollback**, registro dei costi e impostazioni del modulo, chiave API compresa.
- Restano i testi che il modulo ha già scritto nel negozio: le traduzioni del catalogo e i file di traduzione dei moduli classici scritti da questo modulo. Resta anche la scelta sul controllo degli aggiornamenti.
- Una nuova installazione non recupera job, glossario e cronologia già eliminati. Ripristina i valori predefiniti e crea un nuovo indirizzo cron.

## 3. Configurazione e uso quotidiano

L'intero modulo sta in una sola pagina: **International**, poi **AI Translations with Claude**. Le schede sono **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** e **Settings**. **Updates** si trova in fondo alla barra. **Help** apre un pannello di aiuto per la scheda in cui si trova.

I nomi di pulsanti e campi di questo manuale sono quelli del back office inglese. Con un back office in un'altra lingua, vedrà la traduzione dello stesso elemento.

**Dal primo clic alla traduzione salvata**

Il lavoro lo avvia un addetto dal back office. Il cliente non lo avvia.

1. **Settings.** Incolli la chiave Claude, scelga il modello e la lingua di origine, prema **Test connection**, poi **Save**. Senza chiave, nessuno strumento invia testo a Claude.
2. **Scelga come procedere.**
   - Poche stringhe, o un dominio, con controllo prima del salvataggio: **Manual** (3.3).
   - Un dominio grande, un tema o un modulo: **Bulk**, poi il job su **Jobs** (3.4 e 3.5).
   - Campi di prodotto, categoria e CMS: **Catalog**, fino a 100 record alla volta (3.7).
   - Singoli campi su **International → Translations** (3.12) e sulle schede di prodotto, categoria e CMS (3.13).
3. **Controllo qualità.** Ogni stringa tradotta viene verificata per segnaposto e HTML. Una stringa che non supera il controllo non viene salvata. Finiscono in **Review** le stringhe con punteggio sotto 70, quelle più lunghe di due volte e mezzo rispetto all'originale e quelle che contengono ancora parole inglesi come *the*, *and*, *with*, *your* o *please*.
4. **Salvataggio.**
   - **Manual:** **Translate selected (review)** non salva nulla finché non preme **Save approved**. **Save now (skip review)** salva subito le righe valide.
   - **Bulk:** il job attende su **Jobs**. Salva solo dopo **Process slice**, **Auto-process** o la chiamata dell'indirizzo cron. Un job con **Dry-run job** attivo non salva nulla.
   - **Catalog:** le righe valide vengono salvate subito nella lingua di destinazione.
   - **International → Translations** e i form del negozio: i pulsanti si limitano a compilare i campi. Il pulsante **Save** di PrestaShop li salva.
   - Con **Allow publish / save** disattivato, **Manual**, **Bulk** e **Catalog** non scrivono nulla nel negozio.
5. **Fine del job.** Su **Jobs** lo stato diventa **completed** oppure **completed_with_errors**. Le righe di **Review** escono dall'elenco dopo **Approve** o **Reject**. **Catalog** indica quante righe sono state salvate e quante sono fallite.

### 3.1. Configurazione del modulo

Apra **Modules**, **Module Manager**, trovi **AI Translations with Claude** e prema **Configure**. Si apre **Dashboard**. Passi a **Settings**.

**Save** e **Test connection** si trovano in fondo al form. Salvare questo form non avvia nessuna traduzione e non modifica le traduzioni già salvate nel negozio.

![Impostazioni, back office inglese. Parte alta del form: Claude API key, Model, Add a Claude model, Tone e Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings.webp)

**Connessione**

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Claude API key** | vuoto | La chiave segreta che questo negozio invia a Claude. Incolli la chiave ottenuta da https://console.anthropic.com/settings/keys. Lasci il campo vuoto per conservare la chiave già salvata. Un valore nuovo sostituisce quella salvata. Un campo vuoto non la cancella. Quando una chiave è salvata, il testo di aiuto mostra **Key saved:** e la chiave mascherata. |
| **Model** | claude-haiku-4-5 | Il modello Claude che scrive le traduzioni. I nomi integrati restano nell'elenco: claude-haiku-4-5, claude-sonnet-4-5 e claude-opus-4-5. La traduzione successiva usa il modello selezionato. Se l'account non può usare un modello, la chiamata fallisce e l'errore compare in **History**. |
| **Add a Claude model** | vuoto | Scriva l'identificativo esatto dell'account Anthropic, poi prema **Add model**. Il nuovo identificativo compare in **Model** e diventa il modello attivo. **Remove** elimina solo gli identificativi aggiunti qui. Gli identificativi integrati non si possono eliminare. |

Messaggi: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example claude-haiku-4-5.**, **Built-in models cannot be removed.**

**Tono e origine**

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Tone** | Formal | Aggiunge un'indicazione di stile a ogni prompt. **Formal** è adatto ai testi del negozio e del back office, **Casual** dà una voce più leggera, **Brand** funziona insieme a **Brand voice**. Le nuove traduzioni seguono lo stile scelto. Quelle già presenti restano come sono finché non le riesegue. |
| **Brand voice** | vuoto | Visibile quando **Tone** è **Brand**. Poche frasi semplici su come deve suonare il negozio. Il testo viene aggiunto al prompt successivo. Se è vuoto, non c'è nessuna voce aggiuntiva. Non riscrive le traduzioni già salvate. |
| **Source locale** | vuoto | La lingua che il modello tratta come originale. La scelta vuota è un trattino nell'elenco: la fonte è la schermata che si sta traducendo. Scelga la locale in cui sono scritti i cataloghi, di solito en-US. **Manual**, **Bulk** e le icone su **International → Translations** inviano questa locale come origine. La lingua predefinita del negozio non cambia. |
| **Individual field buttons — shop forms** | Yes | Un pulsante accanto a ogni campo multilingue dei form del negozio: prodotto, categoria, CMS e gli altri form del back office. Il pulsante traduce solo quel campo. **No** nasconde questi pulsanti in tutto il negozio. Le traduzioni salvate non cambiano. |
| **Individual field checkboxes — shop forms** | Yes | Ognuno di quei campi ha una casella, e la barra traduce solo i campi selezionati. **No** nasconde le caselle e la barra. I pulsanti sopra hanno un interruttore a parte. |
| **Individual field buttons — International → Translations** | Yes | Un pulsante accanto a ogni campo di **International → Translations**. **No** nasconde questi pulsanti. I form del negozio non sono coinvolti. Un clic compila quel campo. Il pulsante **Save** di PrestaShop salva comunque la pagina. |
| **Individual field checkboxes — International → Translations** | Yes | Caselle e barra su **International → Translations**. **No** le nasconde. I form del negozio non sono coinvolti. |

![Impostazioni, back office inglese. Parte bassa del form: limiti, posta, indirizzo cron, Test connection e Save.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings-limits.webp)

**Limiti**

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Batch size** | 25 | Quante stringhe partono in una singola chiamata API. Per la prima prova usi un valore tra 10 e 25. Il valore resta tra 1 e 100. Un lotto più grande chiude il job con meno chiamate. Se una chiamata fallisce, il nuovo tentativo riguarda una porzione più grande. |
| **Dry-run sample** | 10 | Quante stringhe di esempio mostra **Estimate** prima di un job bulk. Il valore resta tra 1 e 50. **Estimate** non scrive traduzioni. |
| **Max tokens (0 = default)** | 0 | Un tetto alla lunghezza di una risposta. Con 0 viene inviato un tetto di 4096 token. Imposti un numero se le risposte vengono troncate o se le vuole più brevi. Il tetto vale solo per la chiamata successiva. Le traduzioni già salvate non vengono accorciate. |
| **Budget USD / month** | 0 | Un tetto mensile in dollari USA, calcolato dal registro dei consumi. 0 significa nessun tetto. Quando il registro raggiunge l'importo, le nuove traduzioni si fermano. Il lavoro già salvato resta. |
| **Rate limit / min** | 60 | Quante chiamate API questo negozio può avviare in un minuto. 0 disattiva questo limite locale. Le chiamate oltre il limite vengono saltate e compaiono in **History**. Claude può comunque applicare un proprio limite. |
| **Log retention days** | 30 | Per quanti giorni conservare le righe in **History**. Minimo 1. Le righe più vecchie vengono eliminate. Questo numero non cancella job, glossario o traduzioni salvate. |
| **Temperature** | 0.2 | Quanto il modello può riformulare liberamente. Intorno a 0.2 resta vicino all'originale. Valori più vicini a 1 cambiano di più le frasi. Il valore salvato resta tra 0 e 1. Segnaposto e HTML vengono comunque verificati dopo. I modelli integrati ricevono questo valore. Un identificativo di modello aggiunto che non sia Claude Haiku, Sonnet o Opus 4.0, 4.1, 4.5 o 4.6 non lo riceve, quindi questo campo non ha effetto su quel modello. |
| **Allow publish / save** | Yes | Se questo modulo può salvare una traduzione in PrestaShop. **No** blocca il salvataggio su **Manual**, nei job bulk e su **Catalog**. Le icone nella pagina delle traduzioni e nei form del negozio continuano a compilare soltanto il form. Il pulsante **Save** di PrestaShop è separato. |

Dopo **Save**:

- **Settings saved. No translation was started.** Le impostazioni sono salvate e non è stato tradotto nulla.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Incolli una chiave in **Claude API key** e prema di nuovo **Save**.

**Posta e cron**

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Email notify on complete** | No | Invia una sola email quando un job bulk termina. Il job viene eseguito comunque. L'email viene aggiunta o saltata, nient'altro. |
| **Notify email** | vuoto | L'indirizzo che riceve quell'email. Il campo serve solo se l'interruttore sopra è attivo. Salvare l'indirizzo, da solo, non invia alcun messaggio. |
| **CRON URL** | indirizzo con token | Indirizzo segreto che il server può chiamare per elaborare una porzione di un job in attesa. Lo incolli nel pianificatore del server. Non pubblicarlo. Chiunque abbia l'indirizzo può avviare una porzione. Aprire **Settings** non avvia alcun job. |

**Test connection** verifica chiave e modello con una richiesta breve. Non traduce e non salva nulla.

- **Connection OK (N ms). No translation was started.** La connessione funziona.
- **Connection was not made. Nothing was translated.** seguito dal motivo. Controlli chiave e modello. I dettagli sono su **History**.

Per iniziare: incolli la chiave, scelga modello e locale di origine, prema **Test connection**, poi **Save**. Lasci i numeri sui valori di installazione finché un job non dà problemi.

### 3.2. Dashboard

Apra la scheda **Dashboard**. Conta le stringhe di catalogo mancanti, poi mostra l'uso di Claude sotto forma di schede, grafici e le dieci richieste più recenti. La pagina non traduce e non modifica alcuna stringa.

![Dashboard, back office inglese. Copertura per una locale, riga del cron e filtri della cronologia.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-dashboard.webp)

**Copertura**

- **Locale:** la locale del negozio di cui si contano le stringhe mancanti.
- **Show:** ridisegna la tabella per quella locale.
- Colonne: **Section**, **Total**, **Missing**, **Done** e una barra di avanzamento. Le sezioni sono **Back office**, **Themes**, **Installed modules**, **Emails** e **Others**. **Missing** è il numero di stringhe senza traduzione in quella locale.
- Sotto la tabella, **CRON** mostra lo stesso indirizzo di **CRON URL** in **Settings**.
- Una tabella vuota significa che il negozio non ha ancora un catalogo per quella locale. Lo crei da **International → Translations**.

Dopo **Show**, il messaggio è **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Consumo**

- Intervalli predefiniti: **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filtri: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** e **Prompt or reply contains**. Prema **Filter**.
- Schede: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** ed **Estimated cost**. Il costo stimato è un calcolo locale, non una fattura di Anthropic.
- Grafici: **Requests and errors**, **Tokens sent and received**, **Requests by model**. Sotto ci sono i gruppi **By day**, **By model**, **By type**, **By language** e **By employee**, con le colonne **Group**, **Calls**, **Sent**, **Received** e **Total**. Un gruppo vuoto mostra **No requests in this range.**
- **Latest prompts** elenca dieci chiamate. **View** apre il prompt e la risposta. **See all** apre **History** (3.10). Un elenco vuoto mostra **No requests yet.**

Filtrare non cancella la cronologia e non modifica le traduzioni.

Se in una sezione mancano quasi tutte le stringhe, apra **Manual** per poche stringhe oppure **Bulk** per un intero dominio.

### 3.3. Manual

Apra **Manual**. Traduce un dominio o un modulo classico, qualche decina di stringhe alla volta. Il solo filtro non salva nulla.

![Manual, back office inglese. Section, Source, Target, Domain, Only empty e Search.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-manual.webp)

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Section** | Back office | Quale catalogo viene letto: **Back office**, **Themes**, **Installed modules**, **Emails** oppure **Others**. Cambiare sezione ricarica la pagina e mostra solo i campi di quella sezione. Non viene chiamato Claude. |
| **Theme** | vuoto | Visibile solo con **Themes**. Limita l'elenco a un tema. |
| **Module** | vuoto | Visibile solo con **Installed modules**. Limita l'elenco a un modulo. Un modulo classico senza dominio carica tutte le stringhe di quel modulo. |
| **Domain** | vuoto | La stessa suddivisione che si vede su **International → Translations**. Scelga un dominio e prema **Filter**. Nascosto per un modulo classico e per una sezione senza domini. |
| **Source** | il **Source locale** di **Settings**, oppure en-US | La lingua da cui vengono prese le stringhe. Scelga una lingua che abbia già un buon testo. |
| **Target** | la prima lingua dell'elenco | La lingua che vuole completare. Deve esistere in **International → Localization → Languages**. |
| **Only empty** | Yes | Mostra solo le stringhe senza traduzione. Disattivandolo, si vedono tutte le stringhe. Le traduzioni salvate non vengono cancellate. |
| **Search** | vuoto | Mantiene solo le stringhe di origine che contengono la parola digitata. |

Passi:

1. Imposti **Section**, **Source** e **Target**.
2. Per **Themes**, scelga un **Theme**. Per **Installed modules**, scelga un **Module**.
3. Prema **Filter**. L'elenco **Domain** si aggiorna. Scelga un dominio e prema di nuovo **Filter**. Per un modulo classico salti il dominio: **Filter** carica tutte le stringhe del modulo.
4. Spunti le righe da tradurre. **Check all** e **Uncheck all** selezionano o deselezionano l'intero elenco.
5. Prema **Translate selected (review)**. Si apre la tabella **Review before save** con **Source**, **AI proposal** e **Warnings**. Tolga la spunta dalle righe che non vuole. Se una proposta va corretta, la modifichi direttamente nel campo. Prema **Save approved**.
6. Oppure spunti **Save now (skip review)** prima di tradurre. Le righe valide vengono salvate subito, senza passare dalla tabella di revisione.

Le colonne dell'elenco stringhe sono **Source**, **Current** e **Status** (**empty** oppure **filled**).

Messaggi:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** È l'elenco di un modulo classico.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Claude.**
- **No strings match this filter. Nothing was sent to Claude.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to Claude.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Queste righe sono state saltate. Correggi segnaposto e tag perché corrispondano all'originale, poi salvi di nuovo.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Cambiando sezione compare anche una breve riga, per esempio **Section is Back office. Theme and module are not used.**, insieme a **Nothing was sent to Claude.** Lo stesso schema vale per **Themes**, **Installed modules**, **Emails** e **Others**.

### 3.4. Bulk

Apra **Bulk**. Crea un unico job per molti domini e molte lingue. **Estimate** non salva nulla. **Start job** aggiunge una riga su **Jobs**. Non viene salvato nulla finché il job non viene elaborato e **Allow publish / save** non è attivo.

![Bulk, back office inglese. Section, Source, Targets, Domains, Policy e Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-bulk.webp)

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Section** | Back office | Quale catalogo legge il job. Le stesse scelte di **Manual**. |
| **Theme** / **Module** | vuoto | Visibili solo nella sezione corrispondente, come su **Manual**. |
| **Source** | il **Source locale** di **Settings**, oppure en-US | La lingua trattata come originale. Ogni lingua di destinazione viene tradotta a partire da questa. |
| **Targets** | nessuna | Una o più lingue da completare. Tenga premuto Ctrl, oppure Cmd su Mac, per selezionarne più d'una. Un clic semplice sostituisce la selezione. |
| **Domains** | nessuno | I domini che entrano nel job. Tenga premuto Ctrl o Cmd. Se non ne seleziona nessuno, il job copre tutti i domini della sezione scelta. |
| **Policy** | Fill empty | **Fill empty** invia solo le stringhe senza traduzione. **Overwrite all** invia ogni stringa, anche quelle che hanno già una traduzione, e può sostituirle. **Outdated if equals source** invia solo le stringhe la cui traduzione è identica all'originale. |
| **Dry-run job** | No | Claude lavora comunque e il job compare su **Jobs**, ma le risposte non vengono scritte nel negozio. |

Passi:

1. Scelga sezione, origine, lingue di destinazione, domini e policy.
2. Prema **Estimate**. La pagina mostra **Estimate**, il numero di stringhe, una stima dei token, una stima del costo e un **Sample**.
3. Se la stima va bene, prema **Start job**. Si apre **Jobs** con il nuovo job.
4. Lo elabori su **Jobs** (3.5), oppure lo lasci all'indirizzo cron.

Messaggi:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Claude and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no Claude API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Apra **Jobs**. Ogni riga è un'esecuzione avviata da **Bulk**.

![Jobs, back office inglese. L'elenco dei job. In questo negozio non c'è ancora nessun job.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-jobs.webp)

Colonne: **#**, **Status**, **Locales** (origine, poi lingue di destinazione), **Progress** (fatte/totale), **Cost**, **Employee**, **Date** e **Open**. Un elenco vuoto mostra **No jobs yet.**

Stati del job, come compaiono a schermo:

- `pending` - in attesa. Non parte da solo.
- `running` - in corso.
- `paused` - fermo finché non lo riprende.
- `cancelled` - fermato. Le stringhe che stavano aspettando non sono state tradotte.
- `completed` - ogni stringa elaborata, senza errori.
- `completed_with_errors` - concluso, ma alcune stringhe non sono passate.
- `failed` - il job si è interrotto con un errore.

**La schermata del job**

**Open** mostra **Job #N**, lo stato, l'avanzamento (fatte/totale), **failed**, **skipped**, il costo, il numero del dipendente e l'etichetta **dry-run** quando il job è una prova. La barra di avanzamento si aggiorna da sola finché il job è aperto. La tabella sotto ha le colonne **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** ed **Error**.

Stati delle righe: `pending`, `processing`, `done`, `failed`, `skipped` (è scattata un'esclusione, oppure la stringa era già tradotta) e `rolled_back`.

Pulsanti:

- **Process slice** - elabora una porzione della dimensione di **Batch size**, poi si ferma. Messaggio: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Se non resta nulla: **The job has no more strings waiting.**
- **Auto-process** - ripete le porzioni finché il job non termina o un errore lo ferma. Gira nel browser, quindi la scheda deve restare aperta. Chiuderla interrompe il ciclo. Il job resta e si può completare con **Process slice** o con l'indirizzo cron.
- **Pause** - messaggio: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - messaggio: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - le stringhe in errore tornano in attesa e il job torna in attesa. Messaggio: **Retried N failed items.**
- **Rollback** - chiede **Roll back this job?** e ripristina la traduzione precedente dove il modulo aveva conservato una copia prima della modifica. Messaggio: **Rollback: restored N translations.**
- **Error CSV** - scarica le righe in errore. Colonne: id, domain, locale, source, error.
- **Failed only** - mostra solo le righe in errore.
- **Review queue** - apre **Review** (3.6).

Nella schermata del job non c'è un pulsante Cancel. Per fermare il lavoro successivo, usi **Pause**.

**Pausa automatica**

Quando Claude rifiuta le chiamate per un limite di frequenza, il job si mette in pausa da solo. La riga di errore dice **Rate limit — job auto-paused. Resume later.** Attenda, poi prema **Resume**. **Rate limit / min** in **Settings** abbassa il numero di chiamate che il negozio avvia al minuto.

Altri messaggi su questa schermata:

- **Nothing was translated.** seguito da **No Claude API key. Nothing was translated.** Incolli la chiave in **Settings**.
- **Allow publish is off in Settings.** Un job che non è una prova non parte finché non attiva **Allow publish / save**.
- **Monthly API budget has been exhausted.** Alzi **Budget USD / month**, oppure lo imposti a 0.

### 3.6. Review

Apra **Review**, oppure prema **Review queue** su un job. Il titolo della pagina è **Needs-review queue (quality score / flags).** L'elenco mostra le righe più recenti che il controllo qualità non ha fatto passare in automatico, fino a 100.

![Review, back office inglese. La coda di revisione è vuota.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-review.webp)

Colonne: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, poi **Approve** e **Reject**. Un elenco vuoto mostra **The queue is empty.**

Come leggere una riga:

- **Score** va da 0 a 100. Sotto 70, la riga finisce in coda.
- **Flags:**
  - `validation_failed` - segnaposto o HTML non hanno superato il controllo.
  - `warning` - una nota di controllo minore.
  - `length_explosion` - la traduzione supera di due volte e mezzo la lunghezza dell'originale.
  - `too_short` - la traduzione è molto più corta di un originale lungo.
  - `possible_untranslated` - nella traduzione restano parole inglesi come *the*, *and*, *with*, *your* o *please*.
- **Source** è l'originale. **AI** è la proposta del modello.

**Approve** e **Reject** cambiano solo lo stato della riga. Il messaggio è **Review updated.** e la riga esce dall'elenco. L'azione non scrive il testo nel negozio e non modifica il resto del dominio.

Se il job era autorizzato a salvare, la proposta potrebbe essere già nel negozio. Per annullare le modifiche di quel job, usi **Rollback** sul job, nella pagina **Jobs**.

### 3.7. Catalog

Apra **Catalog**. Traduce campi di prodotti, categorie o CMS memorizzati nelle lingue del negozio. Non modifica **International → Translations**. Un clic gestisce al massimo 100 record. Le righe salvate vengono scritte nella lingua di destinazione.

![Catalog, back office inglese. Entity, Fields, lingue, Only empty e Start after ID.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-catalog.webp)

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Entity** | product | Cosa viene letto: **product**, **category** oppure **cms**. Cambiarlo ricarica la pagina e mostra solo l'elenco di campi di quell'entità. Il cambio in sé non traduce nulla. |
| **Fields** | tutti i campi dell'entità | Quali testi invia il lotto. Tenga premuto Ctrl o Cmd. I campi non selezionati non vengono inviati e restano come sono. Prodotto: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Categoria: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. Per un prodotto o una categoria, **Title** è il nome. Per il CMS, **Title** è il titolo della pagina e **Content** è il contenuto della pagina. Lasci **Friendly URL** non selezionato se i link devono restare invariati. |
| **Source language** | la prima lingua del negozio | La lingua da cui vengono copiati i campi. Quella lingua non viene modificata. |
| **Target language** | la prima lingua del negozio | La lingua che riceve la traduzione. Deve essere diversa dall'origine. |
| **Only empty** | Yes | Salta i campi che hanno già un testo nella lingua di destinazione. Lo disattivi solo se vuole sostituire un testo esistente. Attivo: il testo di destinazione già presente resta. Disattivo: il lotto può sovrascriverlo, se il salvataggio è consentito. |
| **Start after ID** | 0 | Salta i record fino a questo ID. 0 parte dal primo record. Dopo un lotto, il campo prende il valore dell'ID più alto di quel lotto, incluse le righe fallite. Prema di nuovo il pulsante per proseguire. Per riprovare una riga fallita, riporti l'ID al di sotto di quel record prima del clic successivo. |

Pulsante: **Translate batch (max 100)**.

Passi:

1. Scelga **Entity** e spunti i campi.
2. Scelga **Source language** e **Target language**.
3. Lasci attivo **Only empty**.
4. Prema **Translate batch (max 100)**. Il messaggio è **Catalog finished: saved N, failed M.** La pagina mostra anche i contatori **Saved** e **failed**.
5. Apra un record nella lingua di destinazione e controlli il risultato prima di disattivare **Only empty** o di lanciare il lotto successivo.

Messaggi:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- Cambiando **Entity** compare **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Apra **Glossary**. Il glossario è un elenco di parole e frasi che il modello deve lasciare invariate, oppure tradurre sempre allo stesso modo. Aggiungere una riga non modifica le traduzioni già salvate. La traduzione successiva leggerà l'elenco.

![Glossary, back office inglese. Aggiunta di un termine e importazione CSV.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-glossary.webp)

**Un termine**

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Source term** | vuoto, obbligatorio | La parola o la frase nella lingua di origine. La scriva esattamente come compare, con le maiuscole dove contano. |
| **Target locale** | vuoto | Limita la riga a una sola locale, per esempio pl-PL. Vuoto: la riga vale per tutte le lingue di destinazione. Una locale compilata viene ignorata per le altre lingue. |
| **Target term** | vuoto | La traduzione approvata. Può restare vuoto solo se **Do not translate** è attivo. |
| **Do not translate** | No | Attivo: il modello copia il termine senza modificarlo, per esempio un marchio, uno SKU o un tag. Disattivo: usa **Target term**. |

Prema **Add**. Messaggi: **Glossary term added. Translations already stored were not changed.** oppure **Nothing was added. Type a source term.**

**La tabella**

Colonne: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** oppure **No**) e **Delete**. **Delete** rimuove solo quella riga. Messaggio: **Glossary term deleted.** Un elenco vuoto mostra **No glossary terms yet.**

**CSV**

- Scelga **CSV file** e prema **Import CSV**. Messaggio: **Imported N rows.** Se manca il file: **CSV file is missing.** Se non può essere letto: **Cannot open the CSV file.**
- La prima riga è l'intestazione: `source_term`, `target_locale`, `target_term`, `do_not_translate`. Quella prima riga viene sempre saltata. Le righe con meno di tre colonne vengono saltate. Nella quarta colonna, un valore vuoto o 0 significa **No**. Qualsiasi altro valore significa **Yes**.
- L'importazione aggiunge le righe del file. Non controlla se il termine esiste già, quindi importare due volte lo stesso file crea duplicati.
- **Export CSV** scarica l'elenco attuale come `glossary.csv`. Non richiede un file di input e non modifica l'elenco.

Usi termini brevi e precisi. Un termine troppo generico viene applicato a ogni occorrenza.

### 3.9. Excludes

Apra **Excludes**. Un'esclusione è un pattern sul testo di origine che il modulo non invia a Claude. Il testo resta nel negozio senza modifiche. Il pattern vale per **Manual**, **Bulk**, **Catalog** e le pagine di traduzione.

![Excludes, back office inglese. Pattern, Type e l'elenco vuoto.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-excludes.webp)

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Pattern** | vuoto, obbligatorio | Il testo confrontato con ogni stringa di origine. Il modo di confrontare dipende da **Type**. |
| **Type** | exact | **exact** corrisponde all'intera stringa. **prefix** corrisponde all'inizio. **contains** corrisponde a un frammento in un punto qualsiasi. **regex** è un'espressione regolare PHP, applicata così come è scritta. Un'espressione errata non corrisponde a nulla. Parta da un pattern breve e controlli cosa viene saltato. Un tipo sbagliato può saltare troppo oppure niente. |

Prema **Add**. Messaggio: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Se il pattern è vuoto: **Nothing was added. Type a pattern.**

Colonne: **Pattern**, **Type**, **On** e **Delete**. **On** mostra 1 quando il pattern è attivo. Questa schermata non ha un interruttore per disattivare un pattern. Per smettere di usarlo, prema **Delete** e, se serve ancora, lo aggiunga di nuovo. **Delete** rimuove solo quel pattern. Non cancella le traduzioni esistenti. Messaggio: **Pattern deleted.** Un elenco vuoto mostra **No patterns yet.**

Usi le esclusioni per il testo che deve restare nella lingua di origine, come una ragione sociale o un token tecnico. Per un termine che va sempre tradotto allo stesso modo, usi **Glossary**.

### 3.10. History

Apra **History**, oppure prema **See all** su **Dashboard**.

![History, back office inglese. L'elenco delle chiamate e Clear history.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-history.webp)

**History** è l'elenco completo delle chiamate a Claude registrate: esecuzioni manuali, la pagina delle traduzioni, i job bulk, i lotti di **Catalog** e il test di connessione. Ogni riga conserva prompt, risposta, modello, lingue, conteggio dei token e durata della chiamata. Schede e grafici sono su **Dashboard**. Aprire questa pagina non invia nuove richieste e non modifica le traduzioni.

Filtri e grafici restano su **Dashboard**. Questa pagina è solo l'elenco.

Colonne: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** e **Prompt**. Tipi: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** e **Not sent** (la chiamata non è stata inviata, per esempio per il limite locale o per il budget). Una riga **Bulk job** mostra il numero del job.

- **View** apre prompt e risposta, con **HTTP**, **Sent**, **Received** e **Total**. In caso di errore, la risposta è il testo dell'errore. **Back to the list** torna alla tabella. Se la riga non esiste più: **This history row no longer exists.**
- Un errore di accesso significa che la chiave in **Settings** è sbagliata, oppure che l'account non può usare il modello scelto.
- **Previous**, **Next** e **Page** scorrono l'elenco.
- **Clear history** chiede **Clear the stored history? Saved translations stay.** Dopo l'operazione compare **History cleared. Saved translations were not changed.** L'aiuto del pulsante dice **Clear history deletes these rows only. Saved translations stay.**

Un elenco vuoto mostra **No requests yet.**

Quando le traduzioni si fermano all'improvviso, apra qui la riga di errore più recente prima di modificare il glossario.

### 3.11. Updates

Apra **Updates** all'estremità destra della barra del modulo. Il titolo del form è **MyPresta Updates**.

![Updates, back office inglese. Manual Check, Automatic Notifications e Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-updates.webp)

- **Manual Check** contiene **Check Now**. Controlla la versione subito.
- **Automatic Notifications** è **Enabled** oppure **Disabled**. **Enabled** è il valore finché non viene salvata una scelta. Se è attivo, il modulo verifica se MyPresta ha una versione più recente e può mostrare un avviso nel back office.
- **Product Page** è un link che apre la pagina di contatto usata da questo modulo.
- **Save** salva la scelta. Messaggio: **Update settings saved.**

Dopo **Check Now**: **New version available!** oppure **Module is up to date!**

### 3.12. Pulsanti su International → Translations

Apra **International → Translations**. I pulsanti accanto ai campi compaiono quando **Individual field buttons — International → Translations** è attivo. Caselle e barra compaiono quando è attivo **Individual field checkboxes — International → Translations**.

Cosa vede:

- Un pulsante **Translate** accanto a ogni campo di testo.
- Una casella su ogni campo, quando le caselle sono attive.
- Una barra intitolata **Claude translations**, con **Source** (en-US, oppure il **Source locale** di **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** e il suggerimento **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** compila i campi vuoti della sezione corrente.

Passi:

1. Scelga **Target**.
2. Spunti i campi, oppure prema **Check empty**.
3. Prema **Translate selected** oppure **Translate empty**.
4. Attenda che la barra mostri **Done**. Mentre lavora, lo stato è **Translating…** con il conteggio. Se non ha spuntato nulla, la barra dice **Tick at least one field.**
5. Controlli i campi compilati e salvi la pagina con il pulsante **Save** di PrestaShop.

I pulsanti si limitano a compilare i campi. Senza il pulsante **Save** di PrestaShop il testo non arriva nel negozio. Con **Allow publish / save** disattivato, i campi vengono comunque compilati, e il pulsante **Save** di PrestaShop salva la pagina.

Messaggi:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** Per **Emails**, il testo di origine viene dal file del template email, non da un campo della pagina. Scelga un'altra **Source locale** che abbia quei file email.

### 3.13. Pulsanti sulle schede di prodotto, categoria e CMS

Apra un prodotto, una categoria, una pagina CMS o un altro form del negozio con campi multilingue. I pulsanti compaiono quando **Individual field buttons — shop forms** è attivo. Caselle e barra compaiono quando è attivo **Individual field checkboxes — shop forms**.

Cosa vede:

- Un pulsante **Translate** accanto a ogni campo multilingue.
- Una casella per la barra.
- Una barra intitolata **Claude translations**, con **Translate from** e **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** e il suggerimento **Fills the fields. Save with the PrestaShop button.**

Passi:

1. Compili il campo nella lingua di origine. Se è vuoto, la barra dice **Fill the source language field first.**
2. Scelga la lingua di destinazione sulla barra.
3. Prema il pulsante accanto a un campo, oppure spunti più campi e prema **Translate selected**. **Translate empty** compila i campi vuoti.
4. Prema **Save** nel form di PrestaShop. Senza questo passaggio il testo non viene salvato.

Il pulsante compila solo il campo nel form. I campi che non spunta restano invariati.

## 4. Vetrina

Il modulo non aggiunge nulla alla pagina che vede il cliente. Non c'è nessun blocco, pulsante o messaggio in vetrina, quindi il tema non ha niente da mostrare per questo modulo.

L'unico indirizzo fuori dal back office è quello del cron. Serve a un'attività pianificata sul server. Non è destinato ai clienti.

- Lo copi da **Settings**, campo **CRON URL**, oppure dalla riga **CRON** su **Dashboard**.
- Lo incolli nel pianificatore del server, per esempio ogni pochi minuti. Ogni chiamata elabora una porzione di un job in attesa.
- Usi l'indirizzo `https://` se nel negozio è attivo SSL.

| Cosa compare aprendo l'indirizzo | Cosa fare |
|---|---|
| **Forbidden** | L'indirizzo è incompleto o è stato modificato. Lo copi di nuovo da **Settings**. |
| **No pending jobs** | Non c'è nessun job in `pending` o `running`. Ne crei uno su **Bulk**, oppure riprenda un job in pausa su **Jobs**. |
| Un risultato JSON con `ok`, `finished` e `counts` | È stata elaborata una porzione. Controlli l'avanzamento su **Jobs**. |

L'indirizzo cron elabora solo i job in `pending` e `running`. Un job `paused` va ripreso su **Jobs**.

## 5. Problemi

| Cosa compare | Causa | Cosa fare |
|---|---|---|
| **No Claude API key.** su ogni pagina del modulo | Nessuna chiave è salvata. | Apra **Settings**, incolli la chiave in **Claude API key** e prema **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Impostazioni salvate senza chiave. | Incolli la chiave e prema **Save**. |
| **Connection was not made. Nothing was translated.** dopo **Test connection** | Chiave errata, nessun collegamento ad Anthropic, oppure modello che l'account non può usare. | Controlli la chiave, scelga un altro **Model** oppure aggiunga l'identificativo corretto in **Add a Claude model**. Legga la riga su **History**. |
| Errori di accesso su **History** | La chiave è errata, oppure l'account non può usare il modello scelto. | Correggi la chiave oppure scelga un modello che l'account può chiamare. |
| **Nothing was started. There is no Claude API key.** su **Bulk** | Chiave mancante. | Incolli la chiave in **Settings**, poi esegua di nuovo **Estimate** e **Start job**. |
| Un job resta su `pending` | Un job non parte da solo. | Prema **Process slice** o **Auto-process** su **Jobs**, oppure configuri l'indirizzo cron (sezione 4). |
| Un job è `paused` con **Rate limit — job auto-paused. Resume later.** | Claude ha rifiutato le chiamate per un limite di frequenza. | Attenda qualche minuto e prema **Resume**. Abbassi **Batch size** oppure **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | È stato raggiunto **Budget USD / month**. | Alzi l'importo oppure imposti 0. Un nuovo mese riparte da zero. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** è disattivato. | Attivi **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** su **Manual** | La traduzione ha modificato segnaposto o tag HTML. | Correggi la riga in **Review before save** in modo che segnaposto e tag coincidano con l'originale, poi prema **Save approved**. |
| Un job termina come `completed_with_errors` | Alcune stringhe non sono passate. | Apra il job, prema **Failed only**, scarichi **Error CSV**, poi prema **Retry failed**. |
| Le righe di **Review** hanno uno **Score** basso | Il controllo qualità le ha messe in coda. | Legga **Source** e **AI**. Prema **Approve** o **Reject**. Se un testo errato è già stato salvato, usi **Rollback** sul job. |
| La traduzione è stata salvata, ma il negozio mostra ancora il vecchio testo | La cache della pagina non si è aggiornata. Il modulo svuota la cache quando salva una traduzione del catalogo, una porzione di un job bulk o un rollback. | Svuoti la cache nel back office di PrestaShop. |
| Un'esclusione non salta la stringa | **Type** errato, oppure un **regex** che non corrisponde a nulla. | Su **Excludes**, elimini il pattern e ne aggiunga uno più corto con il **Type** giusto. |
| Un nuovo termine del glossario non cambia le traduzioni salvate | Il glossario viene letto alla traduzione successiva. I testi già salvati restano. | Riesegua quelle stringhe su **Bulk** con **Overwrite all**, dopo aver letto **Estimate**. |
| **The source language mail file was not found.** | L'origine scelta non ha il file email. | Scelga un'altra **Source locale** in **Settings**, oppure un'altra **Source** nella pagina delle traduzioni, che abbia i file email. |
| **No strings match this filter. Nothing was sent to Claude.** | Il filtro non corrisponde a nulla. | Disattivi **Only empty**, svuoti **Search** oppure scelga un altro dominio. |
| **Nothing was translated. Tick at least one row.** | Nessuna riga era spuntata. | Spunti le righe e prema **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** su **Catalog** | Origine e destinazione sono la stessa lingua. | Scelga un'altra **Target language**. |
| **Catalog finished** ha spostato **Start after ID** oltre le righe fallite | Il campo prende l'ID più alto del lotto, incluse le righe fallite. | Imposti **Start after ID** al di sotto del record fallito e riesegua il lotto. |
| La copertura su **Dashboard** è vuota | Il negozio non ha ancora un catalogo per quella locale. | Lo crei da **International → Translations**, poi torni su **Dashboard**. |
| **History** mostra **Not sent** | Il limite locale o il budget ha fermato la chiamata prima dell'invio. | Controlli **Rate limit / min** e **Budget USD / month** su **Settings**. |
| **The shop needs at least two languages.** | Il negozio ha una sola lingua. | Aggiunga una lingua da **International → Localization → Languages**. |

## 6. Per gli sviluppatori

### 6.1. Panoramica

- Classe principale: `myaitranslationsclaude`, file `myaitranslationsclaude.php`.
- Versione: 1.2.0.
- Nome tecnico: `myaitranslationsclaude`. Nome nell'elenco dei moduli: **AI Translations with Claude**.
- Autore: MyPresta.eu. Scheda in Module Manager: `administration`.
- Scheda del back office: `AdminMyaitranslationsclaude`, padre `AdminInternational`, padre di riserva `IMPROVE`. L'etichetta visibile della scheda è `AI Translations with Claude`. `ensureTab()` ripara una scheda mancante. `renameTabIfTechnical()` sostituisce un nome di scheda che è ancora quello tecnico.
- Installazione: `parent::install()`, tabelle da `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (scrive una chiave solo se manca), hook `displayBackOfficeHeader` e `actionAdminControllerSetMedia`, poi la scheda.
- Disinstallazione: elimina la scheda, esegue `sql/uninstall.php` (elimina 11 tabelle), `removeConfiguration()` elimina le chiavi `MYAITCL_*` elencate lì, poi `parent::uninstall()`. Non elimina `mypresta_updates`, `update_myaitranslationsclaude` né `updatev_myaitranslationsclaude`.
- Non esistono `enable()` né `disable()`.
- `getContent()` chiama `ensureTab()` e reindirizza a `AdminMyaitranslationsclaude` (scheda predefinita `dashboard`).

Flusso dei dati:

1. Il form delle impostazioni invia un POST a `AdminMyaitranslationsclaudeController::initContent()`.
2. `MyaitclConfigService::saveFromForm()` salva i `MYAITCL_*` in `Configuration`. `MyaitclApiKeyEncryptor` cifra la chiave API con AES-256-CBC, usando una chiave derivata da `_COOKIE_KEY_`, e la salva come `MYAITCL_API_KEY_ENC`. Una chiave inviata vuota, o un valore mascherato, non sostituisce quella salvata.
3. Traduzione: `MyaitclTranslateService::translateMessages()` costruisce i prompt (`MyaitclPromptBuilder`), li invia tramite `MyaitclClaudeTranslationProvider` (POST cURL verso `https://api.anthropic.com/v1/messages`, intestazione `anthropic-version: 2023-06-01`), controlla la risposta (`MyaitclPlaceholderValidator`, `MyaitclHtmlValidator`, `MyaitclPsNativeValidator`), la valuta (`MyaitclQualityScorer`) e la salva tramite `MyaitclTranslationAdapter`.
4. Quando **Max tokens** è 0, il provider invia `max_tokens` 4096. `acceptsTemperature()` invia **Temperature** solo se l'identificativo del modello corrisponde a `claude-(opus|sonnet|haiku)-4-(0|1|5|6)`.
5. Il salvataggio del catalogo usa il servizio di traduzione di PrestaShop, se esiste, altrimenti la tabella `_DB_PREFIX_translation`. Le chiavi dei moduli classici vengono scritte in `translations/{iso}.php` del modulo da `MyaitclLegacyModuleCatalogue`.
6. Bulk: `MyaitclBulkJobFactory` inserisce in `myaitcl_job` e `myaitcl_job_item`. `MyaitclJobWorker::processSlice()` esegue una porzione di `BATCH_SIZE`. La chiamano **Process slice**, il ciclo di **Auto-process** (AJAX `ProcessJob`) e `controllers/front/cron.php`.
7. Catalog: `MyaitclCatalogTranslateService::collect()` legge al massimo 100 righe. `translateAndSave()` scrive in `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` o `_DB_PREFIX_cms_lang`. I risultati vengono abbinati per id. Dopo il lotto, **Start after ID** diventa l'`id_entity` più alto dell'insieme raccolto, incluse le righe fallite.
8. Ogni chiamata viene salvata in `myaitcl_request` (**History**). Gli errori vanno anche in `myaitcl_api_log`. Il costo va in `myaitcl_usage_ledger`. `MyaitclSnapshotService` copia il valore precedente in `myaitcl_snapshot` per **Rollback**. `clearTranslationCache()` chiama `Tools::clearCache()` dopo il salvataggio del catalogo, dopo una porzione che non è una prova e dopo un rollback.

### 6.2. File

| File | Ruolo |
|---|---|
| `myaitranslationsclaude.php` | Installazione, disinstallazione, scheda, hook, asset, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Controllo degli aggiornamenti per la scheda **Updates** e per l'avviso nel back office. Classe `myaitranslationsclaudeUpdate`. |
| `logo.png`, `logo.gif` | Logo nell'intestazione del modulo. |
| `controllers/admin/AdminMyaitranslationsclaudeController.php` | Tutte le schede del back office, i salvataggi, le azioni sui job, glossario, esclusioni, catalogo, CSV e AJAX. |
| `controllers/front/cron.php` | Indirizzo cron. Elabora una porzione e restituisce JSON. |
| `sql/install.php`, `sql/uninstall.php` | Creazione ed eliminazione delle tabelle. |
| `src/Adapter/MyaitclTranslationAdapterInterface.php` | Interfaccia di lettura e scrittura delle traduzioni PrestaShop. |
| `src/Adapter/MyaitclAbstractTranslationAdapter.php` | Sezioni, domini, locale, salvataggio tramite il servizio o la tabella `translation`, svuotamento della cache. |
| `src/Adapter/MyaitclTranslationAdapter.php` | Adapter concreto. |
| `src/Adapter/MyaitclTranslationAdapterFactory.php` | Costruisce l'adapter. |
| `src/Adapter/MyaitclFilesystemCatalogueTrait.php` | Legge i cataloghi XLF di temi e moduli. |
| `src/Adapter/MyaitclLegacyModuleCatalogue.php` | Moduli classici: legge e scrive `translations/{iso}.php`. |
| `src/Admin/MyaitclForms.php` | Form del back office e testo `desc` dei campi. |
| `src/Admin/MyaitclSectionHelp.php` | Testo del pannello **Help** per ogni scheda. |
| `src/Audit/MyaitclRequestLogRepository.php` | **History**: righe, schede, grafici, filtri, svuotamento, conservazione. |
| `src/Audit/MyaitclApiLogRepository.php` | Registro degli errori e degli avvisi dell'API, conservazione. |
| `src/Audit/MyaitclTranslationMemory.php` | Riutilizza un risultato per lo stesso testo, locale, modello e glossario. |
| `src/Audit/MyaitclUsageLedger.php` | Stima del costo dalla tabella dei prezzi di questo file, e budget mensile. |
| `src/Audit/MyaitclSnapshotService.php` | Copie prima di una scrittura, e ripristino con **Rollback**. |
| `src/Glossary/MyaitclGlossaryRepository.php` | Elenco del glossario, inserimento, eliminazione. |
| `src/Glossary/MyaitclExcludePatternRepository.php` | Inserimento, eliminazione e confronto delle esclusioni. |
| `src/Job/MyaitclJobStatuses.php` | Costanti di stato per job e righe. |
| `src/Job/MyaitclJobRepository.php` | Job e righe: lettura, stato, porzione successiva, contatori. |
| `src/Job/MyaitclJobWorker.php` | Elaborazione delle porzioni, nuovo tentativo, chiusura, coda di review, email di completamento. |
| `src/Provider/MyaitclTranslationProviderInterface.php` | Interfaccia del provider. |
| `src/Provider/MyaitclClaudeTranslationProvider.php` | Chiamate a Claude, test di connessione, registro delle richieste. |
| `src/Provider/MyaitclPromptBuilder.php` | Prompt di sistema e utente: tono, voce del marchio, glossario. |
| `src/Provider/MyaitclProviderFactory.php` | Costruisce il provider. |
| `src/Quality/MyaitclPlaceholderValidator.php` | Controllo di segnaposto e tag. |
| `src/Quality/MyaitclHtmlValidator.php` | Controllo HTML. |
| `src/Quality/MyaitclPsNativeValidator.php` | Controllo prima di un salvataggio da **Manual**. |
| `src/Quality/MyaitclEmailHtmlPipeline.php` | Protegge l'HTML delle email prima della chiamata e lo ripristina dopo la risposta. |
| `src/Quality/MyaitclQualityScorer.php` | Punteggio 0-100, flag, decisione di review. |
| `src/Security/MyaitclApiKeyEncryptor.php` | Cifratura e decifratura della chiave API. |
| `src/Service/MyaitclConfigService.php` | Lettura e salvataggio di impostazioni, modelli, token cron, intervalli. |
| `src/Service/MyaitclRateLimiter.php` | Limite locale al minuto, file `var/rate_limit.json`. |
| `src/Service/MyaitclTranslateService.php` | Esclusioni, memoria, chiamate, validazione, punteggio, salvataggio, stima. |
| `src/Service/MyaitclBulkJobFactory.php` | Costruisce un job **Bulk** e la stima. |
| `src/Service/MyaitclCatalogTranslateService.php` | Raccoglie e salva le righe di **Catalog**. |
| `src/Service/MyaitclDashboardService.php` | Conteggi di copertura su **Dashboard**. |
| `translations/*.php` | Traduzioni dell'interfaccia, un file per lingua. |
| `views/templates/admin/configure.tpl` | Pagina del modulo e pannello **Help**. |
| `views/templates/admin/_partials/*.tpl` | Schede: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Stili del back office. |
| `views/js/admin.js` | Avanzamento di **Jobs** e **Auto-process**, spunte delle righe, AJAX. |
| `views/js/admin-help.js` | Pannello **Help**. |
| `views/js/translations-tool.js` | Pulsanti e barra su **International → Translations**. |
| `views/js/entity-fields.js` | Pulsanti e barra sulle schede di prodotto, categoria e CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Grafici su **Dashboard**. |
| `var/rate_limit.json` | Contatore del limite locale al minuto. |
| `index.php` in ogni cartella | Blocca l'elenco dei contenuti della cartella. |

### 6.3. Controller

**Back office: `AdminMyaitranslationsclaudeController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsclaude&token=…`, facoltativo `&myaitcl_tab=` con `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (l'etichetta della scheda è **History**), `settings`, `updates`.
- Azioni sui job, query `job_action` più `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, `export_errors`. Il template non mostra un pulsante Cancel. `filter_failed=1` limita la tabella delle righe.
- Azioni di review: `review_action=approve|reject` e `id_review`.
- Glossario: `delete_glossary`. Esclusioni: `delete_exclude`. Modelli: `delete_claude_model`, e POST `new_claude_model` con `submitMyaitranslationsclaudeAddModel`.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, più gli endpoint di traduzione dei campi usati da `translations-tool.js` e `entity-fields.js`.

**Front: `MyaitranslationsclaudeCronModuleFrontController`** (`controllers/front/cron.php`).

- URL del negozio: `module/myaitranslationsclaude/cron`.
- Il parametro `token` deve coincidere con `MYAITCL_CRON_TOKEN` (`hash_equals`). Un token mancante o errato restituisce HTTP 403 e il JSON `{"ok":false,"error":"Forbidden"}`.
- `id_job` facoltativo elabora quel job. Senza di esso, viene elaborato il primo job `pending` o `running`.
- Una porzione riuscita restituisce JSON con `ok`, `finished` e `counts`. Se nessun job è in attesa, il corpo è `{"ok":true,"message":"No pending jobs"}`.
- `ssl` è true sul controller.

### 6.4. Hook

Hook registrati:

- `displayBackOfficeHeader` - rinomina l'etichetta tecnica della scheda, poi carica CSS e JS.
- `actionAdminControllerSetMedia` - carica gli stessi asset.

`translations-tool.js` viene aggiunto sul controller delle traduzioni. `entity-fields.js` viene aggiunto sui form del negozio quando gli interruttori dei campi sono attivi. `Media::addJsDef` pubblica `myaitclTr` (URL ajax, locale di origine, lingue ed etichette della barra).

Il modulo non registra un proprio hook che altri moduli possano implementare. Non esistono `enable()` né `disable()`.

### 6.5. Override

Il modulo non sovrascrive nessuna classe né nessun controller di PrestaShop.

### 6.6. Database

| Tabella | Contenuto |
|---|---|
| `myaitcl_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, id del negozio, date. |
| `myaitcl_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitcl_job` | Un'esecuzione bulk: locali, `scope_json`, `policy_json`, `dry_run`, contatori, totali dei token, costo, dipendente, errore, timestamp. |
| `myaitcl_job_item` | Una stringa di un job: dominio, chiave, tema, locale, origine, valore precedente, valore nuovo, stato, motivo dello scarto, errore, token, validazione. |
| `myaitcl_memory` | Memoria di traduzione: hash, origine, locale, traduzione, modello, numero di riscontri. |
| `myaitcl_usage_ledger` | Righe giornaliere di token e costo, id del job facoltativo, modello. |
| `myaitcl_snapshot` | Valore prima di una scrittura del job, usato da **Rollback**. |
| `myaitcl_api_log` | Righe di errore e avviso: livello, provider `claude`, codice HTTP, messaggio, contesto. |
| `myaitcl_request` | Righe di **History**: tipo, stato, modello, locali, codice HTTP, durata, token, costo, dipendente, job, prompt, risposta, errore. |
| `myaitcl_review` | Coda di review: voce del job, stato, punteggio, flag, dipendente. |
| `myaitcl_catalog_item` | Righe dei lotti di **Catalog**: entità, campo, lingue, origine, valore precedente, valore nuovo, stato, errore. |

La disinstallazione elimina tutte e undici le tabelle. L'installazione usa `CREATE TABLE IF NOT EXISTS`, quindi una reinstallazione su un database che ha ancora le tabelle conserva quelle righe. Una disinstallazione normale le rimuove prima. Alla prima visita di una pagina non viene aggiunta nessuna colonna.

### 6.7. Chiavi e traduzioni

Prefisso `MYAITCL_`. Valori usati quando una chiave manca; sono anche i valori scritti in fase di installazione:

| Chiave | Valore se manca |
|---|---|
| `API_KEY_ENC` | vuoto |
| `MODEL` | `claude-haiku-4-5` |
| `EXTRA_MODELS` | vuoto |
| `PROVIDER` | `claude` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vuoto |
| `BATCH_SIZE` | `25` (al salvataggio viene riportato nell'intervallo 1-100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vuoto |
| `TEMPERATURE` | `0.2` (al salvataggio viene riportato nell'intervallo 0-1) |
| `DRY_RUN_SAMPLE` | `10` (al salvataggio viene riportato nell'intervallo 1-50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (minimo 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vuoto |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (il provider invia allora 4096) |
| `CRON_TOKEN` | 16 byte casuali in esadecimale, generati in installazione |

`removeConfiguration()` elimina anche i vecchi nomi `DEEPL_API_KEY` e `CLAUDE_API_KEY` con lo stesso prefisso. Non elimina le chiavi del controllo degli aggiornamenti.

Le descrizioni dei campi sono le stringhe `desc` in `src/Admin/MyaitclForms.php`, composte da `help()` come scopo, modo di impostazione ed effetto. L'aiuto delle schede è in `src/Admin/MyaitclSectionHelp.php`.

Le stringhe dell'interfaccia passano da `$this->l()` / `{l s=... mod='myaitranslationsclaude'}`. Per aggiungere una lingua si crea `translations/{iso}.php`. Gli errori di job **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No Claude API key. Nothing was translated.** e **Monthly API budget has been exhausted.** sono stringhe in inglese restituite da `MyaitclJobWorker` e `MyaitclTranslateService`, non chiamate a `$this->l()`. Le stringhe di **Updates** usano il dominio di traduzione `updatechecker`.

### 6.8. Estensione

La vetrina non mostra un template del modulo, quindi il tema non ha nulla da sovrascrivere.

I template del back office si trovano in `views/templates/admin/`. PrestaShop non prevede un override da tema per questi template di amministrazione. Le etichette si cambiano tramite `translations/{iso}.php`. I pulsanti su **International → Translations** e sui form del negozio vengono inseriti da `views/js/translations-tool.js` e `views/js/entity-fields.js` a partire da `myaitclTr`. Non esiste un hook con cui un tema possa sostituire quella barra.

## 7. Assistenza

Pagina del modulo: https://mypresta.eu/it/ia-intelligenza-artificiale/traduzioni-ai-con-claude.html

Per scrivere a proposito di questo modulo, acceda al suo account cliente su mypresta.eu, apra il modulo di contatto e scelga l'argomento **Support for paid modules**. Il modulo indica che per i moduli a pagamento è necessario l'accesso. Dopo l'accesso, scelga questo modulo dalla cronologia degli acquisti.
