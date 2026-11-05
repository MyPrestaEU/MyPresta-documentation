---
title: "AI Translations with ChatGPT - documentazione e manuale utente"
description: "Configurazione e risoluzione dei problemi per i negozi che hanno già AI Translations with ChatGPT."
sidebar:
  label: "AI Translations with ChatGPT - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo AI Translations with ChatGPT su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/ai-translations-with-chatgpt/)
>
> ---


## 1. Requisiti

Il modulo funziona su PrestaShop 1.7.0.0 e versioni successive, comprese PrestaShop 8 e 9.

- **PrestaShop:** 1.7.0.0 o successivo.
- **PHP:** 5.6 o successivo.
- **Estensioni PHP:** cURL, OpenSSL, SimpleXML e mbstring.
- **Altri moduli:** questo modulo non ne richiede un altro.
- **Fuori dal negozio:** un account OpenAI e una chiave API. Il server del negozio deve poter aprire `https://api.openai.com/v1/chat/completions`.
- **Facoltativo:** un'attività pianificata sul server che apra l'indirizzo cron di **Settings**. Senza di essa, elabora i lavori in **Jobs**.
- **Cataloghi grandi:** un dominio con migliaia di stringhe sono molte chiamate API. Il lavoro è diviso in fette della dimensione di **Batch size**. Esegui **Estimate** in **Bulk** prima di iniziare.
- Il negozio ha bisogno di almeno due lingue. Con una sola lingua il back office mostra **The shop needs at least two languages.** e non c'è nulla da tradurre.

## 2. Installazione

1. Apri **Modules**, poi **Module Manager**. Scegli **Upload a module**, carica lo ZIP e premi **Install** su **AI Translations with ChatGPT**.
2. Dopo l'installazione, **AI Translations with ChatGPT** compare nel menu **International**.
3. L'installazione non svuota la cache del negozio. Il modulo svuota la cache quando salva una traduzione.

Apri **AI Translations with ChatGPT**, poi **Settings**, e incolla la chiave ChatGPT. Finché non c'è una chiave salvata, ogni pagina del modulo mostra **No ChatGPT API key.** e il collegamento **Open Settings**.

**Disinstallazione.** In **Module Manager**, premi **Uninstall** e conferma **Delete this module and its data (jobs, glossary, cache)?**

- La voce di menu sparisce. Lavori, glossario, schemi di esclusione, cronologia delle chiamate, coda **Review**, copie per il ripristino, registro dei costi e impostazioni del modulo (compresa la chiave API) vengono eliminati.
- Il testo che il modulo ha già scritto nel negozio resta: traduzioni del catalogo e i file di traduzione dei moduli classici che questo modulo ha scritto. Resta anche la scelta del controllo aggiornamenti.
- Una nuova installazione non riporta i lavori, il glossario o la cronologia eliminati. Imposta i valori predefiniti e crea un nuovo indirizzo cron.

## 3. Configurazione e lavoro quotidiano

Tutto il modulo è una pagina: **International**, poi **AI Translations with ChatGPT**. Le schede sono **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** e **Settings**. **Updates** sta in fondo alla barra. **Help** apre un pannello per la scheda corrente.

I nomi di pulsanti e campi in questo manuale sono quelli del back office inglese. In un'altra lingua del pannello vedi la traduzione dello stesso controllo. Le schermate sono del back office inglese.

Un uso normale ha quattro parti.

1. **Connessione.** In **Settings**, incolla la chiave, scegli il modello e premi **Test connection**, poi **Save**.
2. **Una prova piccola.** In **Manual**, filtra un dominio, spunta alcune stringhe vuote e traducile. Controlla il risultato prima di lanciare un intero catalogo.
3. **Un lavoro.** In **Bulk**, scegli la sezione, le lingue e i domini, premi **Estimate**, poi **Start job**. Apri il lavoro e premi **Process slice** oppure **Auto-process**, oppure lascia che l'indirizzo cron lo chiami.
4. **Un controllo.** Apri **Review** per le righe trattenute dal controllo di qualità, e **History** quando una chiamata fallisce. **Rollback** sul lavoro ripristina il testo precedente dove il modulo ha tenuto una copia.

Il modulo non avvia una traduzione da solo. **Estimate**, **Filter** e **Save** in **Settings** non scrivono il testo del catalogo. Un lavoro resta in **Jobs** finché non lo elabori o finché non viene chiamato l'indirizzo cron.

### 3.1. Configurazione del modulo

Apri **Modules**, **Module Manager**, trova **AI Translations with ChatGPT** e premi **Configure**. Si apre **Dashboard**. Vai a **Settings**.

**Save** e **Test connection** sono in fondo al modulo. Salvare questo modulo non avvia una traduzione e non riscrive le traduzioni già salvate.

![Impostazioni, back office inglese. Parte alta del modulo: ChatGPT API key, Model, Add a ChatGPT model, Tone e Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings.webp)

**Connessione**

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **ChatGPT API key** | vuoto | Il segreto che questo negozio invia a ChatGPT. Incolla la chiave del tuo account OpenAI. Lascia la casella vuota per tenere la chiave già salvata. Un valore nuovo sostituisce la chiave salvata. Una casella vuota non la cancella. Quando una chiave è salvata, l'aiuto mostra **Key saved:** e una chiave mascherata. |
| **Model** | gpt-4.1-mini | Il modello ChatGPT che scrive la traduzione. I nomi integrati restano nell'elenco: gpt-4.1, gpt-4.1-mini, gpt-4.1-nano, gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4-turbo-preview, gpt-4, gpt-4-0613, gpt-3.5-turbo, gpt-3.5-turbo-0125, o4-mini, o3-mini e o1-mini. La traduzione successiva usa il modello scelto. Un modello che l'account non può usare fa fallire la chiamata, e l'errore è elencato in **History**. |
| **Add a ChatGPT model** | vuoto | Scrivi l'identificativo esatto dell'account OpenAI, poi premi **Add model**. Il testo di esempio nella casella è gpt-4.1. Il nuovo identificativo compare in **Model** e diventa il modello attivo. **Remove** cancella solo gli identificativi aggiunti qui. Gli identificativi integrati non si possono cancellare. |

Messaggi: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example gpt-4.1.**, **Built-in models cannot be removed.**

**Voce e origine**

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **Tone** | Formal | Aggiunge un'indicazione di stile a ogni prompt. **Formal** è per i testi del negozio e del back office, **Casual** è più leggero, **Brand** si usa insieme a **Brand voice**. Le traduzioni nuove seguono quello stile. Quelle esistenti restano finché non le esegui di nuovo. |
| **Brand voice** | vuoto | Visibile quando **Tone** è **Brand**. Qualche frase semplice su come deve suonare il negozio, oppure una casella vuota. Il testo entra nel prompt successivo. Vuoto significa nessuna voce aggiuntiva. Non riscrive le traduzioni già salvate. |
| **Source locale** | vuoto | La lingua che il modello tratta come originale. La scelta vuota è un trattino nell'elenco: la schermata che stai traducendo fornisce l'origine. Scegli la locale in cui sono scritti i cataloghi, di solito en-US. **Manual**, **Bulk** e le icone di **International → Translations** inviano questa locale come origine. La lingua predefinita del negozio non cambia. |
| **Individual field buttons — shop forms** | Yes | Un pulsante su ogni campo multilingua dei moduli del negozio: prodotto, categoria, CMS e gli altri moduli del back office. Il pulsante traduce solo quel campo. **No** nasconde quei pulsanti in tutto il negozio. Le traduzioni salvate non cambiano. |
| **Individual field checkboxes — shop forms** | Yes | Ognuno di quei campi riceve una casella, e la barra traduce solo i campi che spunti. **No** nasconde le caselle e la barra. I pulsanti sopra seguono il proprio interruttore. |
| **Individual field buttons — International → Translations** | Yes | Un pulsante su ogni campo di **International → Translations**. **No** nasconde quei pulsanti. I moduli del negozio non sono toccati. Un clic riempie quel campo. **Save** di PrestaShop scrive comunque la pagina. |
| **Individual field checkboxes — International → Translations** | Yes | Caselle e barra su **International → Translations**. **No** le nasconde. I moduli del negozio non sono toccati. |

**Limiti**

![Impostazioni, back office inglese. Batch size e i campi dei limiti sotto di esso.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings-limits.webp)

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **Batch size** | 25 | Quante stringhe partono in una chiamata API. Per la prima volta usa da 10 a 25. Il valore resta tra 1 e 100. Una fetta più grande chiude un lavoro con meno chiamate. Un errore ritenta allora un pezzo più grande. |
| **Dry-run sample** | 10 | Quante stringhe di esempio mostra **Estimate** prima di un lavoro di massa. Il valore resta tra 1 e 50. **Estimate** non scrive traduzioni. |
| **Max tokens (0 = default)** | 0 | Il modulo salva questo numero. La richiesta di traduzione non lo invia, quindi non accorcia la risposta e non ferma una risposta tagliata. Il test di connessione usa una propria richiesta breve. Le traduzioni già salvate non vengono tagliate. |
| **Budget USD / month** | 0 | Un tetto mensile in dollari USA, contato dal registro d'uso. 0 significa nessun tetto. Quando il registro raggiunge l'importo, le traduzioni nuove si fermano. Ciò che è già salvato resta. |
| **Rate limit / min** | 60 | Quante chiamate API questo negozio può avviare in un minuto. 0 spegne questo limite locale. Le chiamate oltre il limite vengono saltate e elencate in **History**. ChatGPT può comunque applicare il proprio limite. |
| **Log retention days** | 30 | Quanti giorni di righe tenere in **History**. Almeno 1. Le righe più vecchie vengono rimosse. Questo numero non cancella lavori, glossario né traduzioni salvate. |
| **Temperature** | 0.2 | Quanto liberamente il modello può riformulare. Circa 0,2 resta vicino all'origine. I valori vicini a 1 variano di più le frasi. Il valore salvato resta tra 0 e 1. Segnaposto e HTML vengono controllati dopo. La richiesta di traduzione invia questo valore per ogni modello dell'elenco, anche per un identificativo che aggiungi. |
| **Allow publish / save** | Yes | Se questo modulo può scrivere una traduzione in PrestaShop. **No** blocca il salvataggio in **Manual**, nei lavori di massa e in **Catalog**. Le icone della pagina traduzioni e dei moduli del negozio riempiono soltanto il modulo. **Save** di PrestaShop è a parte. |

Dopo **Save**:

- **Settings saved. No translation was started.** Le impostazioni sono salvate e non è stato tradotto nulla.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Incolla una chiave in **ChatGPT API key** e premi di nuovo **Save**.

**Posta e cron**

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **Email notify on complete** | No | Invia una e-mail quando un lavoro di massa finisce. Il lavoro gira in ogni caso. Si aggiunge o si salta solo l'e-mail. |
| **Notify email** | vuoto | L'indirizzo che riceve quell'e-mail. Il campo si vede solo quando l'interruttore sopra è acceso. Salvare l'indirizzo non invia un messaggio da solo. |
| **CRON URL** | un indirizzo con token | Un indirizzo segreto con cui il server può elaborare una fetta di un lavoro in attesa. Copialo nel pianificatore del server. Non pubblicarlo. Chi ha l'indirizzo può avviare una fetta. Aprire **Settings** non avvia un lavoro. |

**Test connection** controlla chiave e modello con una richiesta breve. Non traduce e non salva.

- **Connection OK (N ms). No translation was started.** La connessione funziona.
- **Connection was not made. Nothing was translated.** seguito dal motivo. Controlla chiave e modello. Il dettaglio è in **History**.

Un avvio pratico: incolla la chiave, scegli il modello e la locale di origine, premi **Test connection**, poi **Save**. Lascia i numeri ai valori di installazione finché un lavoro non si comporta male.

### 3.2. Dashboard

Apri la scheda **Dashboard**. Conta le stringhe di catalogo mancanti, poi mostra l'uso di ChatGPT come schede, grafici e i dieci prompt più recenti. La pagina non traduce e non cambia le stringhe.

![Dashboard, back office inglese. Copertura di una locale, la riga cron e i filtri della cronologia.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-dashboard.webp)

**Copertura**

- **Locale:** la locale del negozio di cui si contano le stringhe mancanti.
- **Show:** ridisegna la tabella per quella locale.
- Colonne: **Section**, **Total**, **Missing**, **Done** e una barra di avanzamento. Le sezioni sono **Back office**, **Themes**, **Installed modules**, **Emails** e **Others**. **Missing** è il numero di stringhe senza traduzione in quella locale.
- Sotto la tabella, **CRON** mostra lo stesso indirizzo di **CRON URL** in **Settings**.
- Una tabella vuota significa che il negozio non ha ancora un catalogo per quella locale. Crealo in **International → Translations**.

Dopo **Show**, il messaggio è **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Uso**

- Preimpostazioni: **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filtri: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** e **Prompt or reply contains**. Premi **Filter**.
- Schede: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** e **Estimated cost**. Il costo stimato è un calcolo locale, non una fattura OpenAI.
- Grafici: **Requests and errors**, **Tokens sent and received**, **Requests by model**. Sotto, i gruppi **By day**, **By model**, **By type**, **By language** e **By employee**, con le colonne **Group**, **Calls**, **Sent**, **Received** e **Total**. Un gruppo vuoto dice **No requests in this range.**
- **Latest prompts** elenca dieci chiamate. **View** apre il prompt e la risposta. **See all** apre **History** (3.10). Un elenco vuoto dice **No requests yet.**

Filtrare non cancella la cronologia e non cambia le traduzioni.

Se una sezione manca in gran parte, apri **Manual** per poche stringhe o **Bulk** per un intero dominio.

### 3.3. Manual

Apri **Manual**. Traduce un dominio, o un modulo classico, qualche decina di stringhe alla volta. Filtrare non salva nulla.

![Manual, back office inglese. Section, Source, Target, Domain, Only empty e Search.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-manual.webp)

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **Section** | Back office | Quale catalogo viene letto: **Back office**, **Themes**, **Installed modules**, **Emails** oppure **Others**. Cambiare sezione ricarica la pagina e mostra solo i campi di quella sezione. Non chiama ChatGPT. |
| **Theme** | vuoto | Visibile solo per **Themes**. Limita l'elenco a un tema. |
| **Module** | vuoto | Visibile solo per **Installed modules**. Limita l'elenco a un modulo. Un modulo classico senza dominio carica ogni stringa di quel modulo. |
| **Domain** | vuoto | Lo stesso raggruppamento di **International → Translations**. Sceglilo e premi **Filter**. Nascosto per un modulo classico e per una sezione senza domini. |
| **Source** | la **Source locale** di **Settings**, oppure en-US | La lingua da cui si prendono le stringhe. Scegli una lingua che ha già un buon testo. |
| **Target** | la prima lingua dell'elenco | La lingua che vuoi riempire. Deve esistere in **International → Localization → Languages**. |
| **Only empty** | Yes | Mostra solo le stringhe senza traduzione. Spegnendolo mostra ogni stringa. Le traduzioni salvate non vengono cancellate. |
| **Search** | vuoto | Tiene solo le stringhe di origine che contengono la parola che scrivi. |

Passi:

1. Imposta **Section**, **Source** e **Target**.
2. Per **Themes**, scegli **Theme**. Per **Installed modules**, scegli **Module**.
3. Premi **Filter**. L'elenco **Domain** si aggiorna. Scegli un dominio e premi di nuovo **Filter**. Per un modulo classico, salta il dominio: **Filter** carica ogni stringa del modulo.
4. Spunta le righe. **Check all** e **Uncheck all** selezionano o svuotano l'elenco.
5. Premi **Translate selected (review)**. Si apre una tabella **Review before save** con **Source**, **AI proposal** e **Warnings**. Togli il segno alle righe che non vuoi. Modifica la proposta nella casella. Premi **Save approved**.
6. Oppure spunta **Save now (skip review)** prima di tradurre. Le righe valide vengono scritte subito, senza la tabella di revisione.

Le colonne dell'elenco stringhe sono **Source**, **Current** e **Status** (**empty** oppure **filled**).

Messaggi:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** Questo è l'elenco di un modulo classico.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to ChatGPT.**
- **No strings match this filter. Nothing was sent to ChatGPT.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to ChatGPT.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Quelle righe sono state saltate. Correggi segnaposto e tag perché corrispondano all'origine, poi salva di nuovo.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Cambiare sezione mostra anche una riga breve come **Section is Back office. Theme and module are not used.** insieme a **Nothing was sent to ChatGPT.** Lo stesso schema vale per **Themes**, **Installed modules**, **Emails** e **Others**.

### 3.4. Bulk

Apri **Bulk**. Crea un lavoro per molti domini e lingue. **Estimate** non salva. **Start job** crea una riga in **Jobs**. Non si scrive nulla finché il lavoro non viene elaborato e **Allow publish / save** è acceso.

![Bulk, back office inglese. Section, Source, Targets, Domains, Policy e Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-bulk.webp)

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **Section** | Back office | Quale catalogo legge il lavoro. Le stesse scelte di **Manual**. |
| **Theme** / **Module** | vuoto | Visibile solo per la sezione corrispondente, come in **Manual**. |
| **Source** | la **Source locale** di **Settings**, oppure en-US | La lingua trattata come originale. Ogni destinazione viene tradotta da questa lingua. |
| **Targets** | nessuna | Una o più lingue da riempire. Tieni premuto Ctrl, o Cmd su un Mac, per selezionarne diverse. Un clic semplice sostituisce la selezione. |
| **Domains** | nessuno | Domini inclusi nel lavoro. Tieni premuto Ctrl o Cmd. I domini che non selezioni non vengono tradotti. Lasciali tutti non selezionati solo se vuoi un lavoro vuoto. L'eccezione è un modulo classico senza dominio: il lavoro copre allora quel modulo. |
| **Policy** | Fill empty | **Fill empty** invia solo le stringhe senza traduzione. **Overwrite all** invia ogni stringa, comprese quelle che hanno già una traduzione, e può sostituirle. **Outdated if equals source** invia solo le stringhe la cui traduzione è identica all'origine. |
| **Dry-run job** | No | ChatGPT gira comunque e il lavoro compare in **Jobs**, ma le risposte non vengono scritte nel negozio. |

Passi:

1. Scegli la sezione, l'origine, le destinazioni, i domini e la politica.
2. Premi **Estimate**. La pagina mostra **Estimate**, il numero di stringhe, una stima dei token, una stima del costo e un **Sample**.
3. Se la stima va bene, premi **Start job**. **Jobs** si apre con il lavoro nuovo.
4. Elaboralo in **Jobs** (3.5), oppure lascialo per l'indirizzo cron.

Messaggi:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to ChatGPT and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no ChatGPT API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Apri **Jobs**. Ogni riga è un'esecuzione di **Bulk**.

![Jobs, back office inglese. L'elenco dei lavori vuoto.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-jobs.webp)

Colonne: **#**, **Status**, **Locales** (origine, poi destinazioni), **Progress** (fatti/totale), **Cost**, **Employee**, **Date** e **Open**. Un elenco vuoto dice **No jobs yet.**

Stati del lavoro, come a schermo:

- `pending` - in attesa. Non parte da solo.
- `running` - in corso.
- `paused` - fermo finché non lo riprendi.
- `cancelled` - fermato. Le stringhe che aspettavano ancora non sono state tradotte.
- `completed` - ogni stringa elaborata, senza errori.
- `completed_with_errors` - finito, e alcune stringhe sono fallite.
- `failed` - il lavoro è finito con un errore.

**La schermata del lavoro**

**Open** mostra **Job #N**, lo stato, l'avanzamento (fatti/totale), **failed**, **skipped**, il costo, il numero del dipendente e l'etichetta **dry-run** quando il lavoro è di prova. La barra di avanzamento si aggiorna da sola finché il lavoro è aperto. La tabella sotto ha **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** e **Error**.

Stati di riga: `pending`, `processing`, `done`, `failed`, `skipped` (ha coinciso un'esclusione, oppure la stringa era già tradotta) e `rolled_back`.

Pulsanti:

- **Process slice** - una fetta della dimensione di **Batch size**, poi si ferma. Messaggio: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Quando non resta nulla: **The job has no more strings waiting.**
- **Auto-process** - ripete le fette finché il lavoro finisce o un errore lo ferma. Gira nel browser, quindi la scheda deve restare aperta. Chiudere la scheda ferma il ciclo. Il lavoro resta e si può finire con **Process slice** o con l'indirizzo cron.
- **Pause** - messaggio: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - messaggio: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - le stringhe fallite tornano in attesa e il lavoro aspetta di nuovo. Messaggio: **Retried N failed items.**
- **Rollback** - chiede **Roll back this job?** e ripristina la traduzione precedente dove il modulo ha salvato una copia prima del cambiamento. Messaggio: **Rollback: restored N translations.**
- **Error CSV** - scarica le righe fallite. Colonne: id, domain, locale, source, error.
- **Failed only** - mostra solo le righe fallite.
- **Review queue** - apre **Review** (3.6).

La schermata del lavoro non ha un pulsante Cancel. Usa **Pause** per fermare il resto del lavoro.

**Pausa automatica**

Quando ChatGPT rifiuta le chiamate per un limite di frequenza, il lavoro si mette in pausa da solo. La riga di errore è **Rate limit — job auto-paused. Resume later.** Aspetta, poi premi **Resume**. **Rate limit / min** in **Settings** abbassa quante chiamate il negozio avvia in un minuto.

Altri messaggi su questa schermata:

- **Nothing was translated.** seguito da **No ChatGPT API key. Nothing was translated.** Incolla la chiave in **Settings**.
- **Allow publish is off in Settings.** Un lavoro che non è di prova non parte finché non accendi **Allow publish / save**.
- **Monthly API budget has been exhausted.** Alza **Budget USD / month**, oppure mettilo a 0.

### 3.6. Review

Apri **Review**, oppure premi **Review queue** su un lavoro. La riga del titolo è **Needs-review queue (quality score / flags).** Elenca le righe più recenti che il controllo di qualità non ha lasciato passare da solo, fino a 100.

![Review, back office inglese. La coda di revisione vuota.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-review.webp)

Colonne: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, poi **Approve** e **Reject**. Un elenco vuoto dice **The queue is empty.**

Come leggere una riga:

- **Score** va da 0 a 100. Sotto 70, la riga entra in coda.
- **Flags:**
  - `validation_failed` - segnaposto o HTML non hanno superato il controllo.
  - `warning` - una nota di controllo più piccola.
  - `length_explosion` - la traduzione è più di due volte e mezzo l'origine.
  - `too_short` - la traduzione è molto più corta di un'origine lunga.
  - `possible_untranslated` - nella traduzione restano parole inglesi come the, and, with, your o please.
- **Source** è l'originale. **AI** è la proposta del modello.

**Approve** e **Reject** cambiano solo lo stato della riga. Il messaggio è **Review updated.** La riga esce dall'elenco. Questa pagina non incolla il testo nel catalogo da sola.

Se il lavoro poteva salvare, la proposta può essere già nel negozio. Per annullare un cambiamento di quel lavoro, usa **Rollback** sul lavoro in **Jobs**.

### 3.7. Catalog

Apri **Catalog**. Traduce i campi di prodotto, categoria o CMS salvati nelle lingue del negozio. Non modifica **International → Translations**. Una pressione tratta al massimo 100 record. Le righe salvate vengono scritte nella lingua di destinazione.

![Catalog, back office inglese. Entità, campi, lingue e Translate batch.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-catalog.webp)

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **Entity** | product | Che cosa viene letto: **product**, **category** oppure **cms**. Cambiarlo ricarica la pagina e mostra solo quell'elenco di campi. Il cambiamento da solo non traduce. |
| **Fields** | ogni campo di quell'entità | Quali testi invia il lotto. Tieni premuto Ctrl o Cmd. I campi non selezionati non vengono inviati e restano come sono. Prodotto: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Categoria: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. **Title** di un prodotto o di una categoria è il nome. Nel CMS, **Title** è il titolo della pagina e **Content** è il corpo. Lascia **Friendly URL** non selezionato quando i collegamenti devono restare. |
| **Source language** | la prima lingua del negozio | La lingua da cui si copiano i campi. Quella lingua non viene modificata. |
| **Target language** | la prima lingua del negozio | La lingua che riceve la traduzione. Deve essere diversa dall'origine. |
| **Only empty** | Yes | Salta i campi che hanno già testo nella lingua di destinazione. Spegnilo solo quando vuoi sostituire il testo esistente. Acceso: il testo di destinazione esistente resta. Spento: il lotto può sostituirlo quando la pubblicazione è consentita. |
| **Start after ID** | 0 | Salta i record fino a questo ID. 0 parte dal primo record. Dopo un lotto il campo diventa l'ID più alto di quel lotto, comprese le righe fallite. Premi di nuovo il pulsante per continuare. Per ritentare una riga fallita, rimetti l'ID sotto quel record prima della pressione successiva. |

Pulsante: **Translate batch (max 100)**.

Passi:

1. Scegli **Entity** e spunta i campi.
2. Scegli **Source language** e **Target language**.
3. Lascia **Only empty** acceso.
4. Premi **Translate batch (max 100)**. Il messaggio è **Catalog finished: saved N, failed M.** La pagina mostra anche i conteggi **Saved** e **failed**.
5. Apri un record nella lingua di destinazione e controlla il risultato prima di spegnere **Only empty** o di lanciare il lotto successivo.

Messaggi:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- Cambiare **Entity** mostra **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Apri **Glossary**. Il glossario è un elenco di parole e frasi che il modello deve tenere o tradurre sempre allo stesso modo. Aggiungere una riga non cambia le traduzioni già salvate. La traduzione successiva legge l'elenco.

![Glossary, back office inglese. Aggiunta di un termine e l'elenco dei termini.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-glossary.webp)

**Un termine**

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **Source term** | vuoto, obbligatorio | La parola o la frase nella lingua di origine. Scrivila esattamente come compare, maiuscole comprese quando contano. |
| **Target locale** | vuoto | Limita la riga a una locale, per esempio pl-PL. Vuoto significa che la riga vale per ogni lingua di destinazione. Una locale compilata viene ignorata per le altre lingue. |
| **Target term** | vuoto | La traduzione approvata. Può essere vuota solo quando **Do not translate** è acceso. |
| **Do not translate** | No | Acceso: il modello copia il termine senza cambiamenti, per esempio un marchio, uno SKU o un tag. Spento: usa **Target term**. |

Premi **Add**. Messaggi: **Glossary term added. Translations already stored were not changed.** oppure **Nothing was added. Type a source term.**

**La tabella**

Colonne: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** oppure **No**) e **Delete**. **Delete** toglie solo quella riga. Messaggio: **Glossary term deleted.** Un elenco vuoto dice **No glossary terms yet.**

**CSV**

- Scegli **CSV file** e premi **Import CSV**. Messaggio: **Imported N rows.** Se manca il file: **CSV file is missing.** Se non si può leggere: **Cannot open the CSV file.**
- La prima riga è un'intestazione: `source_term`, `target_locale`, `target_term`, `do_not_translate`. Quella prima riga viene sempre saltata. Le righe con meno di tre colonne vengono saltate. Nella quarta colonna, un valore vuoto o 0 significa **No**. Qualsiasi altro valore significa **Yes**.
- L'importazione aggiunge le righe che riesce a leggere. Non cerca un termine esistente per sostituirlo, quindi importare di nuovo lo stesso file aggiunge duplicati.
- **Export CSV** scarica l'elenco corrente come `glossary.csv`. Non ha bisogno di un file in ingresso e non cambia l'elenco.

Usa termini brevi ed esatti. Un termine molto ampio viene forzato ogni volta che compare.

### 3.9. Excludes

Apri **Excludes**. Un'esclusione è uno schema di testo di origine che il modulo non invia a ChatGPT. Il testo resta nel negozio senza cambiamenti. Lo schema vale in **Manual**, **Bulk**, **Catalog** e nelle pagine di traduzione.

![Excludes, back office inglese. Pattern, Type e l'elenco degli schemi.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-excludes.webp)

| Campo | All'installazione | Che cosa fa |
|---|---|---|
| **Pattern** | vuoto, obbligatorio | Il testo confrontato con ogni stringa di origine. Il confronto dipende da **Type**. |
| **Type** | exact | **exact** è l'intera stringa. **prefix** è l'inizio. **contains** è un frammento in un punto qualsiasi della stringa. **regex** è un'espressione regolare PHP, applicata così com'è scritta. Un'espressione sbagliata non coincide con nulla. Inizia con uno schema breve e controlla che cosa è stato saltato. Un tipo sbagliato può saltare troppo o nulla. |

Premi **Add**. Messaggio: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Uno schema vuoto: **Nothing was added. Type a pattern.**

Colonne: **Pattern**, **Type**, **On** e **Delete**. **On** mostra 1 quando lo schema è attivo. Questa schermata non ha un interruttore per spegnere uno schema. Per smettere di usarlo, **Delete** e aggiungilo di nuovo se ti serve ancora. **Delete** toglie solo quello schema. Le traduzioni esistenti non vengono cancellate. Messaggio: **Pattern deleted.** Un elenco vuoto dice **No patterns yet.**

Usa le esclusioni per un testo che deve restare nella lingua di origine, come un nome legale o un token tecnico. Per un termine che deve essere sempre tradotto in un solo modo, usa **Glossary**.

### 3.10. History

Apri **History**, oppure premi **See all** in **Dashboard**.

![History, back office inglese. L'elenco delle richieste.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-history.webp)

**History** è l'elenco completo delle chiamate ChatGPT salvate: esecuzioni manuali, la pagina traduzioni, i lavori di massa, i lotti di catalogo e il test di connessione. Ogni riga tiene il prompt, la risposta, il modello, le lingue, i conteggi dei token e quanto è durata la chiamata. Schede e grafici sono in **Dashboard**. Aprire questa pagina non invia una richiesta nuova e non cambia le traduzioni.

I filtri sono gli stessi di **Dashboard** (3.2).

Colonne: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** e **Prompt**. Tipi: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** e **Not sent** (la chiamata non è stata inviata, per esempio per il limite locale o il budget). Una riga **Bulk job** mostra il numero del lavoro.

- **View** apre il prompt e la risposta, con **HTTP**, **Sent**, **Received** e **Total**. In caso di errore, la risposta è il testo dell'errore. **Back to the list** torna alla tabella. Se la riga non c'è più: **This history row no longer exists.**
- Un errore di accesso significa che la chiave in **Settings** è sbagliata, oppure che l'account non può usare il modello scelto.
- **Previous**, **Next** e **Page** scorrono l'elenco.
- **Clear history** chiede **Clear the stored history? Saved translations stay.** Dopo: **History cleared. Saved translations were not changed.** L'aiuto del pulsante dice **Clear history deletes these rows only. Saved translations stay.**

Un elenco vuoto dice **No requests yet.**

Quando le traduzioni si fermano all'improvviso, apri qui la riga di errore più recente prima di cambiare il glossario.

### 3.11. Updates

Apri **Updates** all'estremità destra della barra del modulo. Il titolo del modulo è **MyPresta Updates**.

![Updates, back office inglese. Manual Check, Automatic Notifications e Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-updates.webp)

- **Manual Check** contiene **Check Now**. Controlla la versione subito.
- **Automatic Notifications** è **Enabled** oppure **Disabled**. **Enabled** è il valore quando la scelta non è mai stata salvata. Quando è acceso, il modulo controlla se MyPresta ha una versione più nuova e può mostrare un avviso nel back office.
- **Product Page** è un collegamento che apre la pagina di contatto usata da questo modulo.
- **Save** salva la scelta. Messaggio: **Update settings saved.**

Dopo **Check Now**: **New version available!** oppure **Module is up to date!**

### 3.12. Pulsanti su International → Translations

Apri **International → Translations**. I pulsanti dei campi compaiono quando **Individual field buttons — International → Translations** è acceso. Caselle e barra compaiono quando **Individual field checkboxes — International → Translations** è acceso.

Che cosa vedi:

- Un pulsante **Translate** su ogni campo di testo.
- Una casella su ogni campo, quando le caselle sono accese.
- Una barra **ChatGPT translations**, con **Source** (en-US, oppure la **Source locale** di **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** e l'indicazione **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** riempie i campi vuoti della sezione corrente.

Passi:

1. Scegli **Target**.
2. Spunta i campi, oppure premi **Check empty**.
3. Premi **Translate selected**, oppure **Translate empty**.
4. Aspetta che la barra mostri **Done**. Mentre lavora, lo stato è **Translating…** con il conteggio. Se non spunti nulla, la barra dice **Tick at least one field.**
5. Controlla i campi riempiti. Salva la pagina con il pulsante **Save** di PrestaShop.

I pulsanti riempiono soltanto i campi. Senza **Save** di PrestaShop, il testo non entra nel negozio. Con **Allow publish / save** spento, i campi vengono comunque riempiti, e **Save** di PrestaShop scrive la pagina.

Messaggi:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** Per **Emails**, il testo di origine viene dal file del modello di posta, non dal campo della pagina. Scegli un'altra **Source locale** che abbia quei file di posta.

### 3.13. Pulsanti sui moduli di prodotto, categoria e CMS

Apri un prodotto, una categoria, una pagina CMS o un altro modulo del negozio con campi multilingua. I pulsanti sono visibili quando **Individual field buttons — shop forms** è acceso. Le caselle e la barra sono visibili quando **Individual field checkboxes — shop forms** è acceso.

Che cosa vedi:

- Un pulsante **Translate** su ogni campo multilingua.
- Una casella per la barra.
- Una barra **ChatGPT translations**, con **Translate from** e **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** e l'indicazione **Fills the fields. Save with the PrestaShop button.**

Passi:

1. Riempi il campo nella lingua di origine. Se è vuoto, la barra dice **Fill the source language field first.**
2. Scegli la lingua di destinazione sulla barra.
3. Premi il pulsante di un campo, oppure spunta i campi e premi **Translate selected**. **Translate empty** riempie i campi vuoti.
4. Premi **Save** sul modulo PrestaShop. Senza quello, il testo non viene salvato.

Il pulsante riempie solo il campo nel modulo. I campi che non spunti restano invariati.

## 4. Vetrina

Il modulo non aggiunge nulla alla pagina che vede il cliente. Non c'è un blocco, un pulsante o un messaggio in vetrina, quindi il tema non ha nulla da mostrare per questo modulo.

L'unico indirizzo fuori dal back office è l'indirizzo cron. Serve a un'attività pianificata sul server. Non è per i clienti.

- Copialo da **Settings**, **CRON URL**, oppure dalla riga **CRON** di **Dashboard**.
- Incollalo nel pianificatore del server, per esempio ogni pochi minuti. Ogni chiamata elabora una fetta di un lavoro in attesa.
- Usa l'indirizzo `https://` quando il negozio ha SSL acceso.

| Che cosa vedi aprendo l'indirizzo | Che cosa fare |
|---|---|
| **Forbidden** | L'indirizzo è incompleto o è stato cambiato. Copialo di nuovo da **Settings**. |
| **No pending jobs** | Non c'è un lavoro in `pending` né in `running`. Creane uno in **Bulk**, oppure riprendi un lavoro in pausa in **Jobs**. |
| Un risultato JSON con `ok`, `finished` e `counts` | Una fetta è stata elaborata. Controlla l'avanzamento in **Jobs**. |

L'indirizzo cron elabora solo i lavori in `pending` e `running`. Un lavoro `paused` va ripreso in **Jobs**.

## 5. Problemi

| Che cosa vedi | Causa | Che cosa fare |
|---|---|---|
| **No ChatGPT API key.** su ogni pagina del modulo | Non c'è una chiave salvata. | Apri **Settings**, incolla la chiave in **ChatGPT API key** e premi **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Le impostazioni sono state salvate senza chiave. | Incolla la chiave e premi **Save**. |
| **Connection was not made. Nothing was translated.** dopo **Test connection** | Chiave sbagliata, nessuna rotta verso OpenAI, o un modello che l'account non può usare. | Controlla la chiave, scegli un altro **Model**, oppure aggiungi l'identificativo giusto in **Add a ChatGPT model**. Leggi la riga in **History**. |
| Errori di accesso in **History** | La chiave è sbagliata, oppure l'account non può usare il modello scelto. | Correggi la chiave, oppure scegli un modello che l'account può chiamare. |
| **Nothing was started. There is no ChatGPT API key.** in **Bulk** | Manca la chiave. | Incolla la chiave in **Settings**, poi esegui di nuovo **Estimate** e **Start job**. |
| Un lavoro resta su `pending` | Un lavoro non parte da solo. | Premi **Process slice** o **Auto-process** in **Jobs**, oppure imposta l'indirizzo cron (sezione 4). |
| Un lavoro è `paused` con **Rate limit — job auto-paused. Resume later.** | ChatGPT ha rifiutato le chiamate per un limite di frequenza. La risposta in **History** può anche dire **ChatGPT rate limit (429). Try again later.** | Aspetta qualche minuto e premi **Resume**. Abbassa **Batch size** o **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | È stato raggiunto **Budget USD / month**. | Alza l'importo, oppure metti 0. Un mese nuovo parte da zero. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** è spento. | Accendi **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** in **Manual** | La traduzione ha cambiato segnaposto o tag HTML. | Modifica la riga in **Review before save** perché segnaposto e tag corrispondano all'origine, poi premi **Save approved**. |
| Un lavoro finisce come `completed_with_errors` | Alcune stringhe sono fallite. | Apri il lavoro, premi **Failed only**, scarica **Error CSV**, poi premi **Retry failed**. |
| Una riga è in **Review** | Il punteggio è sotto 70, il controllo di lunghezza è fallito, oppure i segnaposto sono falliti. | Leggi **Flags**. **Approve** o **Reject** cambia solo la coda. Usa **Rollback** sul lavoro quando il testo è già stato scritto. |
| **The shop needs at least two languages.** | Il negozio ha una lingua. | Aggiungi una lingua in **International → Localization → Languages**, poi riapri il modulo. |
| Mancano i pulsanti su un modulo prodotto | Gli interruttori dei moduli del negozio sono spenti. | In **Settings**, accendi **Individual field buttons — shop forms** e, se vuoi la barra, **Individual field checkboxes — shop forms**. |
| La pagina traduzioni non ha la barra | Gli interruttori della pagina traduzioni sono spenti. | Accendi i due interruttori **International → Translations** in **Settings**. |
| **Max tokens** non cambia la lunghezza delle risposte | La richiesta di traduzione non invia quel numero. | Lascialo a 0. Accorcia un singolo risultato modificandolo prima di **Save approved**. |
| L'importazione di un CSV del glossario ha creato duplicati | L'importazione aggiunge righe. Non sostituisce un termine già salvato. | Cancella le righe in più, oppure esporta, pulisci il file, cancella le righe vecchie e importa una sola volta. |

## 6. Per gli sviluppatori

### 6.1. Panoramica

- Classe principale: `myaitranslationsgpt`, file `myaitranslationsgpt.php`.
- Versione: 1.2.0.
- Nome tecnico: `myaitranslationsgpt`. Nome nell'elenco moduli: **AI Translations with ChatGPT**.
- Autore: MyPresta.eu. Scheda del Module Manager: `administration`.
- Scheda del back office: `AdminMyaitranslationsgpt`, padre `AdminInternational`, padre di riserva `IMPROVE`. L'etichetta visibile è `AI Translations with ChatGPT`. `ensureTab()` ripara una scheda mancante. `renameTabIfTechnical()` sostituisce un nome di scheda che è ancora il nome tecnico.
- Installazione: `parent::install()`, tabelle da `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (scrive una chiave solo quando manca), hook `displayBackOfficeHeader` e `actionAdminControllerSetMedia`, poi la scheda.
- Disinstallazione: cancella la scheda, `sql/uninstall.php` (elimina 11 tabelle), `removeConfiguration()` cancella le chiavi `MYAITGPT_*` elencate lì, poi `parent::uninstall()`. Non cancella `mypresta_updates`, `update_myaitranslationsgpt` né `updatev_myaitranslationsgpt`.
- Non ci sono `enable()` né `disable()`.
- `getContent()` chiama `ensureTab()` e reindirizza a `AdminMyaitranslationsgpt` (scheda predefinita `dashboard`).

Flusso dei dati:

1. Il modulo delle impostazioni invia a `AdminMyaitranslationsgptController::initContent()`.
2. `ConfigService::saveFromForm()` salva `MYAITGPT_*` in `Configuration`. `ApiKeyEncryptor` cifra la chiave API con AES-256-CBC. La chiave è `hash('sha256', _COOKIE_KEY_ . '|myaitranslationsgpt|v1', true)`. Il valore salvato ha il prefisso `MYAITGPT1:`. Una chiave inviata vuota, o un valore mascherato, non sostituisce la chiave salvata.
3. Traduzione: `TranslateService::translateMessages()` costruisce i prompt (`PromptBuilder`), li invia tramite `OpenAiTranslationProvider` (cURL POST a `https://api.openai.com/v1/chat/completions`, intestazione `Authorization: Bearer`), controlla la risposta (`PlaceholderValidator`, `HtmlValidator`, `PsNativeValidator`), la valuta (`QualityScorer`) e la salva tramite `TranslationAdapter`.
4. `translateBatch()` invia `temperature` dalle impostazioni e non invia `max_tokens`. Il test di connessione (`ping`) invia `max_tokens` 5 e `temperature` 0. `MYAITGPT_MAX_TOKENS` è salvato e `translateBatch()` non lo legge.
5. Il salvataggio del catalogo usa il servizio di traduzione di PrestaShop quando esiste, altrimenti la tabella `_DB_PREFIX_translation`. Le chiavi dei moduli classici le scrive `LegacyModuleCatalogue` in `translations/{iso}.php` di quel modulo.
6. Bulk: `BulkJobFactory` inserisce `myaitgpt_job` e `myaitgpt_job_item`. Un elenco di domini vuoto non produce elementi, salvo un modulo classico, che usa `LegacyModuleCatalogue::DOMAIN`. `JobWorker::processSlice()` esegue una fetta di `BATCH_SIZE`. Viene chiamato da **Process slice**, dal ciclo **Auto-process** (AJAX `ProcessJob`) e da `controllers/front/cron.php`.
7. Catalog: `CatalogTranslateService::collect()` viene chiamato con un limite di 100. `translateAndSave()` scrive `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` o `_DB_PREFIX_cms_lang`. I risultati sono abbinati per id. Dopo il lotto, **Start after ID** diventa il più alto `id_entity` dell'insieme raccolto, comprese le righe fallite.
8. Ogni chiamata è salvata in `myaitgpt_request` (**History**). Gli errori vanno anche in `myaitgpt_api_log` (la colonna `provider` vale per impostazione predefinita `openai`). Il costo va in `myaitgpt_usage_ledger`. `SnapshotService` copia il valore precedente in `myaitgpt_snapshot` per **Rollback**. `clearTranslationCache()` chiama `Tools::clearCache()` dopo un salvataggio di catalogo, dopo una fetta che non è di prova e dopo un ripristino.

`QualityScorer` parte da 100. `validation_failed` toglie 40. Ogni avviso toglie 5. Un rapporto di lunghezza sopra 2,5 imposta `length_explosion` e toglie 20. Un rapporto sotto 0,3 quando l'origine è più lunga di 20 caratteri imposta `too_short` e toglie 15. Le parole inglesi the, and, with, your o please rimaste impostano `possible_untranslated` e tolgono 10. La riga ha bisogno di revisione quando il punteggio è sotto 70, oppure quando è impostato `validation_failed` o `length_explosion`.

### 6.2. File

| File | Ruolo |
|---|---|
| `myaitranslationsgpt.php` | Installazione, disinstallazione, scheda, hook, risorse, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Controllo aggiornamenti per la scheda **Updates** e l'avviso del back office. Classe `myaitranslationsgptUpdate`. |
| `logo.png`, `logo.gif` | Logo nell'intestazione del modulo. |
| `controllers/admin/AdminMyaitranslationsgptController.php` | Ogni scheda del back office, salvataggi, azioni dei lavori, glossario, esclusioni, catalogo, CSV, AJAX. |
| `controllers/front/cron.php` | Indirizzo cron. Elabora una fetta e restituisce JSON. |
| `sql/install.php`, `sql/uninstall.php` | Creazione e rimozione delle tabelle. |
| `src/Adapter/TranslationAdapterInterface.php` | Interfaccia di lettura e scrittura delle traduzioni PrestaShop. |
| `src/Adapter/AbstractTranslationAdapter.php` | Sezioni, domini, locale, salvataggio tramite il servizio o la tabella `translation`, svuotamento della cache. |
| `src/Adapter/TranslationAdapter.php` | Adattatore concreto. |
| `src/Adapter/TranslationAdapterFactory.php` | Costruisce l'adattatore. |
| `src/Adapter/FilesystemCatalogueTrait.php` | Legge i cataloghi XLF di temi e moduli. |
| `src/Adapter/LegacyModuleCatalogue.php` | Moduli classici: lettura e scrittura di `translations/{iso}.php`. |
| `src/Admin/MyaitgptForms.php` | Moduli del back office e testo `desc` dei campi. |
| `src/Admin/MyaitgptSectionHelp.php` | Testo del pannello **Help** di ogni scheda. |
| `src/Audit/RequestLogRepository.php` | **History**: righe, schede, grafici, filtri, svuotamento, conservazione. |
| `src/Audit/ApiLogRepository.php` | Registro di errori e avvisi API, conservazione. |
| `src/Audit/TranslationMemory.php` | Riutilizza un risultato per lo stesso testo, locale, modello e glossario. |
| `src/Audit/UsageLedger.php` | Stima del costo e budget mensile. |
| `src/Audit/SnapshotService.php` | Copie prima di una scrittura e ripristino in **Rollback**. |
| `src/Glossary/GlossaryRepository.php` | Elenco del glossario, inserimento, cancellazione. |
| `src/Glossary/ExcludePatternRepository.php` | Inserimento, cancellazione e confronto delle esclusioni. |
| `src/Job/JobStatuses.php` | Costanti di stato di lavori e righe. |
| `src/Job/JobRepository.php` | Lavori e righe: lettura, stato, fetta successiva, contatori. |
| `src/Job/JobWorker.php` | Elaborazione della fetta, nuovo tentativo, fine, coda di revisione, e-mail di completamento. |
| `src/Provider/TranslationProviderInterface.php` | Interfaccia del fornitore. |
| `src/Provider/OpenAiTranslationProvider.php` | Chiamate ChatGPT, test di connessione, registro delle richieste. |
| `src/Provider/PromptBuilder.php` | Prompt di sistema e utente: tono, voce del marchio, glossario. |
| `src/Provider/ProviderFactory.php` | Costruisce il fornitore. |
| `src/Quality/PlaceholderValidator.php` | Controllo di segnaposto e tag. |
| `src/Quality/HtmlValidator.php` | Controllo HTML. |
| `src/Quality/PsNativeValidator.php` | Controllo prima di un salvataggio in **Manual**. |
| `src/Quality/EmailHtmlPipeline.php` | Protegge l'HTML della posta prima della chiamata e lo ripristina dopo la risposta. |
| `src/Quality/QualityScorer.php` | Punteggio 0-100, flag, decisione di revisione. |
| `src/Security/ApiKeyEncryptor.php` | Cifra e decifra la chiave API. |
| `src/Service/ConfigService.php` | Lettura e salvataggio delle impostazioni, modelli, token cron, intervalli. |
| `src/Service/RateLimiter.php` | Limite locale al minuto, file `var/rate_limit.json`. |
| `src/Service/TranslateService.php` | Esclusioni, memoria, chiamate, validazione, punteggio, salvataggio, stima. |
| `src/Service/BulkJobFactory.php` | Costruisce un lavoro **Bulk** e la stima. |
| `src/Service/CatalogTranslateService.php` | Raccoglie e salva le righe di **Catalog**. |
| `src/Service/DashboardService.php` | Conteggi di copertura in **Dashboard**. |
| `translations/*.php` | Testi dell'interfaccia, un file per lingua. |
| `views/templates/admin/configure.tpl` | La pagina del modulo e il cassetto **Help**. |
| `views/templates/admin/_partials/*.tpl` | Schede: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Stili del back office. |
| `views/js/admin.js` | Avanzamento di **Jobs** e **Auto-process**, spunte delle righe, AJAX. Mostra **Brand voice** solo quando **Tone** è **Brand**, e **Notify email** solo quando l'avviso e-mail è acceso. |
| `views/js/admin-help.js` | Pannello **Help**. |
| `views/js/translations-tool.js` | Pulsanti e barra su **International → Translations**. |
| `views/js/entity-fields.js` | Pulsanti e barra sui moduli di prodotto, categoria e CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Grafici di **Dashboard**. |
| `var/rate_limit.json` | Contatore del limite locale al minuto. |
| `index.php` in ogni directory | Blocca l'elenco della directory. |

### 6.3. Controller

**Back office: `AdminMyaitranslationsgptController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsgpt&token=…`, facoltativo `&myaitgpt_tab=` con `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (l'etichetta della scheda è **History**), `settings`, `updates`.
- Azioni del lavoro, query `job_action` più `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, `export_errors`. Il template non disegna un pulsante Cancel. `filter_failed=1` limita la tabella delle righe. `cancel` mette il lavoro su `cancelled` e lascia non tradotte le stringhe in attesa. Messaggio: **Job cancelled. Strings still waiting were not translated.**
- Azioni di revisione: `review_action=approve|reject` e `id_review`.
- Glossario: `delete_glossary`. Esclusioni: `delete_exclude`. Modelli: `delete_openai_model`, e POST `new_openai_model` con `submitMyaitranslationsgptAddModel`.
- CSV del glossario: `importGlossaryCsv()` salta l'intestazione e ogni riga con meno di tre colonne, poi inserisce ogni riga restante. Non aggiorna un termine esistente.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, `displayAjaxTranslatePageLines`, `displayAjaxMailSource`, `displayAjaxListDomains`.

**Vetrina: `MyaitranslationsgptCronModuleFrontController`** (`controllers/front/cron.php`).

- URL del negozio: `module/myaitranslationsgpt/cron`.
- La query `token` deve corrispondere a `MYAITGPT_CRON_TOKEN` (`hash_equals`). Un token assente o errato restituisce HTTP 403 e JSON `{"ok":false,"error":"Forbidden"}`.
- Un `id_job` facoltativo elabora quel lavoro. Senza di esso viene elaborato il primo lavoro `pending` o `running`.
- Una fetta riuscita restituisce JSON con `ok`, `finished` e `counts`. Quando nessun lavoro è in attesa, il corpo è `{"ok":true,"message":"No pending jobs"}`.
- `ssl` del controller è true.

### 6.4. Hook

Hook registrati:

- `displayBackOfficeHeader` - rinomina un'etichetta tecnica di scheda, poi carica CSS e JS.
- `actionAdminControllerSetMedia` - carica le stesse risorse.

`translations-tool.js` viene aggiunto sul controller delle traduzioni. `entity-fields.js` viene aggiunto sui moduli del negozio quando gli interruttori dei campi sono accesi. `Media::addJsDef` pubblica `myaitgptTr` (URL ajax, locale di origine, lingue ed etichette della barra). L'etichetta della barra è **ChatGPT translations**.

Il modulo non registra un hook proprio che altri moduli debbano implementare. Non ci sono `enable()` né `disable()`.

### 6.5. Override

Il modulo non sovrascrive alcuna classe o controller di PrestaShop.

### 6.6. Database

| Tabella | Contenuto |
|---|---|
| `myaitgpt_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, id negozio, date. |
| `myaitgpt_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgpt_job` | Un'esecuzione di massa: locale, `scope_json`, `policy_json`, `dry_run`, contatori, totali token, costo, dipendente, errore, marche temporali. |
| `myaitgpt_job_item` | Una stringa di un lavoro: dominio, chiave, tema, locale, origine, valore precedente, valore nuovo, stato, motivo di salto, errore, token, validazione. |
| `myaitgpt_memory` | Memoria di traduzione: hash, origine, locale, traduzione, modello, numero di riscontri. |
| `myaitgpt_usage_ledger` | Righe giornaliere di token e costo, id lavoro facoltativo, modello. |
| `myaitgpt_snapshot` | Valore prima di una scrittura del lavoro, usato da **Rollback**. |
| `myaitgpt_api_log` | Righe di errore e avviso: livello, fornitore (predefinito `openai`), codice HTTP, messaggio, contesto. |
| `myaitgpt_request` | Righe di **History**: tipo, stato, modello, locale, codice HTTP, durata, token, costo, dipendente, lavoro, prompt, risposta, errore. |
| `myaitgpt_review` | Coda di revisione: elemento del lavoro, stato, punteggio, flag, dipendente. |
| `myaitgpt_catalog_item` | Righe del lotto di catalogo: entità, campo, lingue, origine, precedente, nuova, stato, errore. |

La disinstallazione elimina tutte e undici le tabelle. L'installazione usa `CREATE TABLE IF NOT EXISTS`, quindi una reinstallazione su un database che ha ancora le tabelle conserva quelle righe. Una disinstallazione normale le rimuove prima. Nessuna colonna viene aggiunta alla prima visita di una pagina.

### 6.7. Chiavi e traduzioni

Prefisso `MYAITGPT_`. Valori quando la chiave manca, che è anche il valore scritto all'installazione:

| Chiave | Quando manca |
|---|---|
| `API_KEY_ENC` | vuoto |
| `MODEL` | `gpt-4.1-mini` |
| `EXTRA_MODELS` | vuoto |
| `PROVIDER` | `openai` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vuoto |
| `BATCH_SIZE` | `25` (al salvataggio di nuovo limitato a 1-100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vuoto |
| `TEMPERATURE` | `0.2` (al salvataggio di nuovo limitato a 0-1) |
| `DRY_RUN_SAMPLE` | `10` (al salvataggio di nuovo limitato a 1-50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (minimo 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vuoto |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (solo salvato; `translateBatch()` non lo invia) |
| `CRON_TOKEN` | 16 byte casuali in esadecimale, generati all'installazione |

`removeConfiguration()` cancella anche i nomi residui `DEEPL_API_KEY` e `CLAUDE_API_KEY` sotto lo stesso prefisso. Non cancella le chiavi del controllo aggiornamenti.

Le descrizioni dei campi sono le stringhe `desc` in `src/Admin/MyaitgptForms.php`, costruite da `help()` come scopo, modo di impostazione ed effetto. L'aiuto di **Max tokens** dice di lasciare 0 per il valore predefinito di ChatGPT. La richiesta ignora il valore salvato. L'aiuto delle schede è `src/Admin/MyaitgptSectionHelp.php`.

Le stringhe dell'interfaccia passano da `$this->l()` / `{l s=... mod='myaitranslationsgpt'}`. Aggiungi una lingua con `translations/{iso}.php`. L'errore del lavoro **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No ChatGPT API key. Nothing was translated.** e **Monthly API budget has been exhausted.** sono stringhe inglesi restituite da `JobWorker` e `TranslateService`, non chiamate a `$this->l()`. Le stringhe di **Updates** usano il dominio di traduzione `updatechecker`. `OpenAiTranslationProvider` restituisce **ChatGPT rate limit (429). Try again later.** su HTTP 429.

### 6.8. Estensione

La vetrina non rende un template del modulo, quindi il tema non ha nulla da sovrascrivere.

I template del back office stanno in `views/templates/admin/`. PrestaShop non offre una sovrascrittura di tema per quei template di amministrazione. Cambia le etichette con `translations/{iso}.php`. I pulsanti di **International → Translations** e dei moduli del negozio sono iniettati da `views/js/translations-tool.js` e `views/js/entity-fields.js` a partire da `myaitgptTr`. Non c'è un hook che un tema possa usare per sostituire quella barra.

## 7. Aiuto

Pagina del modulo: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html

Per scrivere a proposito di questo modulo, accedi al tuo account cliente su mypresta.eu, apri il modulo di contatto e scegli **Support for paid modules**. Il modulo dice che per i moduli a pagamento è necessario l'accesso. Dopo l'accesso, scegli questo modulo dalla cronologia degli acquisti.
