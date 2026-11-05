---
title: "AI Translations with DeepSeek – documentazione e manuale utente (user manual)"
sidebar:
  label: "AI Translations with DeepSeek – documentazione e manuale utente (user manual)"
description: "Guida alla configurazione e alla risoluzione dei problemi del modulo AI Translations with DeepSeek, per i titolari di negozio che hanno già il modulo."
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo AI Translations with DeepSeek su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/ai-translations-with-deepseek/)
>
> ---


## 1. Requisiti

Il modulo funziona con PrestaShop 1.7.0.0 o successivo e richiede una chiave API del Suo account DeepSeek.

- **PrestaShop:** versione 1.7.0.0 o successiva.
- **PHP:** il modulo non dichiara una propria versione minima di PHP. Il server deve eseguire la versione di PHP richiesta dalla Sua versione di PrestaShop.
- **Estensioni PHP:** cURL (connessione a DeepSeek), mbstring (conteggio dei caratteri nei testi), OpenSSL (cifratura della chiave API) e JSON (salvataggio dei dati inviati e ricevuti).
- **Altri moduli:** il modulo non richiede altri moduli.
- **Fuori dal negozio:** un account DeepSeek personale con chiave API. Senza chiave il modulo non può tradurre nulla.
- **Cron sul server:** necessario solo se le attività di massa devono girare senza clic. Vedere il paragrafo 3.1.
- **Catalogo ampio:** un'attività di massa viene suddivisa in blocchi, e ogni blocco è una chiamata a DeepSeek. Gli intervalli grandi richiedono tempo: verificarli con **Estimate** prima di avviare l'attività.

## 2. Installazione

1. Carichi il file ZIP del modulo in **Module Manager** con il pulsante **Upload a module**, quindi clicchi su **Install**.
2. Al termine dell'installazione compare una voce nel menu: **International → AI Translations with DeepSeek**. Questa voce apre il pannello del modulo.
3. L'installazione non svuota la cache del negozio. Se la nuova voce di menu non compare, vada in **Advanced Parameters → Performance** e clicchi su **Clear cache**.

Dopo l'installazione il pannello è vuoto: non c'è una chiave API e le impostazioni hanno i valori iniziali descritti nel paragrafo 3.1.

**La disinstallazione** rimuove la voce di menu, le attività di massa con la loro cronologia, il glossario, l'elenco delle esclusioni, la memoria di traduzione, le copie di backup usate da **Rollback**, la cronologia delle chiamate e degli errori, la coda di revisione, l'elenco della scheda **Catalog** e tutte le impostazioni, compresi la chiave API e l'indirizzo cron.

La disinstallazione **non elimina** le traduzioni già salvate nel negozio: i testi di prodotti, categorie, pagine CMS e International → Translations restano come sono. Dopo la disinstallazione non potrà più annullare queste traduzioni con **Rollback**, perché le copie di backup vengono eliminate insieme al modulo.

Reinstallare **non ripristina** i dati eliminati. Le tabelle vengono ricreate vuote e le impostazioni tornano ai valori iniziali. Anche l'indirizzo cron cambia: copi quello nuovo da **Settings** e aggiorni la pianificazione sul server.

## 3. Configurazione e lavoro nel back office

Le schermate del pannello sono in inglese. In questo manuale i nomi di campi, schede e pulsanti sono riportati esattamente come li vede a schermo.

**Chi avvia il lavoro:** sempre un collaboratore nel back office. I clienti non avviano traduzioni.

**Il processo dall'inizio alla fine:**

1. In **Settings** inserisca la Sua chiave DeepSeek, scelga un modello e clicchi su **Save**. Poi clicchi su **Test connection** per verificare la chiave.
2. Imposti **Source locale** (la lingua dell'originale) e verifichi che **Allow publish / save** sia attivo.
3. Scelga cosa tradurre. I singoli domini e stringhe si traducono in **Manual**. Gli intervalli ampi si affidano tramite **Bulk**. I campi di prodotti, categorie e pagine CMS si traducono in **Catalog**. I pulsanti accanto ai campi dei moduli del negozio e nella pagina International → Translations funzionano direttamente dove sta lavorando.
4. In **Manual** e accanto ai campi ottiene prima una proposta di traduzione. La salva in un passaggio separato: con il pulsante **Save approved** in **Manual**, spuntando **Save now (skip review)**, oppure con il pulsante **Save** di PrestaShop nel modulo.
5. In **Bulk** clicchi su **Estimate**. Non viene inviato né salvato nulla. Se la stima Le sembra corretta, clicchi su **Start job**. L'attività va in **Jobs** e attende. Non parte da sola: clicchi su **Process slice** o **Auto-process**, oppure lasci che una chiamata cron sul server elabori i blocchi.
6. Le traduzioni che non hanno superato il controllo di qualità finiscono in **Review**. Il pulsante **Approve** cambia solo lo stato della riga. Non scrive il testo nel negozio.
7. **Glossary** ed **Excludes** influiscono sulle traduzioni successive. Le traduzioni già salvate non cambiano.
8. **Dashboard** mostra le mancanze e i costi, **History** mostra ogni chiamata a DeepSeek.

**Come finisce il lavoro:** un'attività di massa termina con lo stato **completed** (tutto tradotto) oppure **completed_with_errors** (ci sono stati errori). Se la notifica è attiva, viene poi inviata un'e-mail. Una traduzione manuale termina quando le righe selezionate vengono salvate nel negozio.

### 3.1 Settings (impostazioni del modulo)

Percorso: **Moduli** → **Module Manager** → nome del modulo → **Configure**. Il pulsante **Configure** apre il pannello del modulo, e la scheda **Settings** si trova nella barra in alto.

![Scheda Settings](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings.webp)

Altre parti dello stesso modulo:

![Settings – interruttori dei pulsanti di traduzione e lingua di origine](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-buttons.webp)

![Settings – limiti, budget e temperatura](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-limits.webp)

![Settings – e-mail, salvataggio e indirizzo cron con i pulsanti Test connection e Save](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-publish.webp)

Salvare il modulo con **Save** non modifica le traduzioni completate. Se il campo **DeepSeek API key** è vuoto e in precedenza non è stata salvata alcuna chiave, compare il messaggio: “Settings saved. No API key is stored, so nothing can be translated until you paste one.”

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **DeepSeek API key** | vuoto | La chiave del Suo account DeepSeek. Un campo vuoto mantiene la chiave già salvata, e un valore nuovo la sostituisce. Un campo vuoto non cancella la chiave. Sotto il campo viene mostrata la chiave salvata, mascherata. Le richieste vanno a api.deepseek.com. |
| **Model** | deepseek-flash | Il modello DeepSeek che scrive la traduzione. I modelli integrati sono: deepseek-flash, deepseek-v4-pro, deepseek-v4-flash, deepseek-chat e deepseek-reasoner. Un modello che l'account non può usare fa fallire la chiamata, e l'errore viene salvato in **History**. |
| **Add a DeepSeek model** | vuoto | Aggiunge un identificativo di modello non presente nell'elenco. Lo digiti esattamente come appare nel Suo account DeepSeek e clicchi su **Add model**. Il modello aggiunto diventa subito quello attivo. **Remove** elimina solo i modelli aggiunti qui. I modelli integrati non si possono rimuovere. |
| **Tone** | Formal | Uno stile aggiunto a ogni istruzione per il modello. **Formal** è per i testi del negozio e del back office, **Casual** è più leggero, e **Brand** funziona insieme al campo **Brand voice**. Le nuove traduzioni seguono lo stile. Le traduzioni salvate non cambiano finché non le traduce di nuovo. |
| **Brand voice** | vuoto | Alcune frasi che descrivono come deve suonare il negozio. Il campo compare quando **Tone** è impostato su **Brand**. Il testo viene aggiunto all'istruzione successiva e non riscrive le traduzioni salvate. |
| **Source locale** | vuoto (—) | La lingua trattata come originale, per esempio English (en-US). Il trattino “—” significa che la schermata in cui sta traducendo fornisce da sola la lingua di origine. Le traduzioni manuali e di massa e i pulsanti di International → Translations inviano questa lingua come origine. La lingua predefinita del negozio non cambia. |
| **Individual field buttons — shop forms** | Sì | Un pulsante accanto a ogni campo multilingue dei moduli del negozio: prodotto, categoria, CMS e altri moduli. Il pulsante traduce solo quel campo. **No** nasconde questi pulsanti in tutto il negozio. Non influisce su International → Translations. |
| **Individual field checkboxes — shop forms** | Sì | Una casella accanto ai campi dei moduli del negozio e una barra in basso che traduce i campi selezionati. **No** nasconde le caselle e la barra. I pulsanti della riga superiore hanno un interruttore proprio. |
| **Individual field buttons — International → Translations** | Sì | Un pulsante accanto a ogni campo di International → Translations. **No** nasconde questi pulsanti solo in questa pagina. I moduli del negozio non cambiano. |
| **Individual field checkboxes — International → Translations** | Sì | Caselle e barra su International → Translations. La barra traduce i campi selezionati uno alla volta. **No** nasconde caselle e barra solo in questa pagina. |
| **Batch size** | 25 | Quante stringhe vengono inviate in una chiamata a DeepSeek. I valori ammessi vanno da 1 a 100. Per una prima prova scelga da 10 a 25. Un blocco più grande conclude l'attività con meno chiamate, ma dopo un errore viene ripetuta una parte maggiore. |
| **Dry-run sample** | 10 | Quante stringhe di esempio mostra **Estimate** prima di un'attività di massa. I valori ammessi vanno da 1 a 50. **Estimate** non salva traduzioni. |
| **Max tokens (0 = default)** | 0 | Un limite alla lunghezza di una risposta. 0 significa il limite predefinito di DeepSeek. Imposti un numero se le risposte vengono troncate o sono troppo lunghe. Il limite si applica solo alle chiamate successive. |
| **Budget USD / month** | 0 | Un tetto mensile in dollari USA, calcolato dal consumo salvato. 0 significa nessun tetto. Quando il tetto viene raggiunto, le nuove traduzioni si fermano, e quelle già salvate restano. |
| **Rate limit / min** | 60 | Quante chiamate può effettuare il negozio al minuto. 0 disattiva questo limite locale. Le chiamate oltre il limite vengono saltate e registrate in **History**. DeepSeek può applicare anche un proprio limite. |
| **Log retention days** | 30 | Quanti giorni vengono conservate le voci di **History**. Il minimo è 1 giorno. Le voci più vecchie vengono eliminate. Attività, glossario e traduzioni salvate non vengono cancellati. |
| **Temperature** | 0.2 | Quanto liberamente il modello riformula il testo. Un valore vicino a 0,2 resta fedele all'originale, valori più vicini a 1 cambiano di più le frasi. Intervallo ammesso: da 0 a 1. Segnaposto e HTML vengono comunque verificati dopo ogni traduzione. |
| **Email notify on complete** | No | Invia un'e-mail quando termina un'attività di massa. L'attività in sé funziona allo stesso modo; cambia solo l'invio. |
| **Notify email** | vuoto | L'indirizzo che riceve l'e-mail sull'attività conclusa. Il campo funziona solo se **Email notify on complete** è attivo. Un campo vuoto invia l'e-mail all'indirizzo del negozio indicato nei dati dell'azienda. Salvare l'indirizzo non invia alcun messaggio. Oggetto e testo sono in inglese, per esempio “myaitranslationsdeepseek job #41 completed”, e nel testo compaiono i numeri di stringhe completate, fallite e saltate. |
| **Allow publish / save** | Sì | Se il modulo può salvare traduzioni nel negozio. Con **No** il salvataggio è bloccato in **Manual**, nelle attività di massa e in **Catalog**. I pulsanti di International → Translations si limitano a riempire il modulo, e a salvarlo è il pulsante **Save** di PrestaShop. |
| **CRON URL** | indirizzo generato | Un indirizzo per la pianificazione del server. Ogni chiamata elabora un blocco di un'attività in attesa e poi termina. Non pubblichi questo indirizzo: chiunque lo conosca può avviare un blocco. Aprire **Settings** non avvia alcuna attività. |

Pulsanti in fondo al modulo: **Save** salva le impostazioni. **Test connection** verifica la chiave e non salva alcuna traduzione.

Avvio consigliato: inserisca la chiave, scelga un modello, imposti **Source locale**, clicchi su **Save** e poi su **Test connection**. Lasci gli altri valori ai loro valori iniziali finché un'attività non si comporta come previsto.

### 3.2 Dashboard

La Dashboard mostra quanti testi mancano in ogni parte del catalogo per la lingua scelta, e l'utilizzo di DeepSeek. Aprire **Dashboard** non invia richieste e non modifica le traduzioni.

![Dashboard](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard.webp)

- **Locale** è la lingua di cui si contano le mancanze. La prima volta viene selezionata la prima lingua dell'elenco del negozio. Cambi la lingua e clicchi su **Show** per ricalcolare la tabella.
- **Tabella di copertura** con le colonne **Section**, **Done**, **Missing** e **Total**. Ogni riga è una parte del catalogo: back office, temi, moduli, e-mail o altro. La barra indica quanta parte è già tradotta.
- **Schede e grafici** contano le chiamate del periodo scelto. I campi del filtro sono date (preimpostazioni e **From** e **To**), poi **Model**, tipo, stato, lingua, collaboratore e una parola nel prompt o nella risposta. Il pulsante **Filter** applica il filtro. Le schede mostrano il numero di chiamate, i token inviati e ricevuti, il tempo medio e il costo stimato. Il costo è una stima locale, non una fattura.
- **Latest prompts** elenca le dieci chiamate più recenti. **View** apre il prompt e la risposta in una finestra. **See all** La porta in **History**.
- Sotto la tabella c'è l'indirizzo cron. È lo stesso segreto che si trova in **Settings**.

![Dashboard – grafici e riepiloghi](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard-charts.webp)

Una tabella di copertura vuota significa che il negozio non ha ancora un catalogo per quella lingua. Il catalogo lo crea International → Translations.

### 3.3 Manual

**Manual** traduce un dominio scelto, poche stringhe alla volta. **Filter** carica soltanto l'elenco e non salva nulla.

![Manual](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-manual.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Section** | Back office | Sceglie il catalogo di PrestaShop da leggere: **Back office**, **Themes**, **Installed modules**, **Emails** oppure **Others**. Cambiare sezione ricarica il modulo e non chiama DeepSeek. |
| **Theme** | — | Compare solo per **Themes**. Limita l'elenco a un tema. |
| **Module** | — | Compare solo per **Installed modules**. Limita l'elenco a un modulo. Un modulo senza domini carica subito tutte le sue stringhe. |
| **Source** | Source locale da **Settings** (en-US) | La lingua da cui vengono presi i testi. Scelga quella che ha già una traduzione affidabile. La lingua di destinazione non cambia. |
| **Target** | prima lingua del negozio nell'elenco | La lingua che vuole completare. Deve esistere in International → Localization → Languages. L'elenco e il successivo salvataggio riguardano solo questa lingua. |
| **Domain** | — | Il dominio di traduzione, gli stessi raggruppamenti di International → Translations. Prema **Filter** per riempire l'elenco, scelga un dominio e prema di nuovo **Filter**. Non compare per un modulo senza domini. |
| **Only empty** | Sì | Nasconde le stringhe che hanno già una traduzione. **No** mostra tutte le stringhe. La tabella cambia; le traduzioni salvate non vengono cancellate. |
| **Search** | vuoto | Mantiene solo le stringhe la cui origine contiene la parola digitata. Il catalogo non cambia. |

**Come tradurre:**

1. Spunti le righe, oppure clicchi su **Check all** (seleziona le righe visibili). **Uncheck all** toglie le spunte.
2. Clicchi su **Translate selected (review)**. Il modulo invia le stringhe selezionate e mostra una tabella di revisione. Non viene ancora salvato nulla.
3. Nella tabella di revisione tolga la spunta da una riga che non vuole salvare, e corregga la proposta nel campo **AI proposal**.
4. Clicchi su **Save approved**. Vengono salvate le righe selezionate.

Se spunta **Save now (skip review)** prima di tradurre, le righe accettate vengono salvate subito, senza la tabella di revisione.

La tabella dei risultati ha le colonne **Source**, **Current** (la traduzione attuale), **AI proposal**, **Status** (**empty** o **filled**), **Tokens** e **Warnings**. Una riga con un segnaposto o un HTML danneggiato non viene salvata.

Messaggi che può vedere:

- “No strings match this filter. Nothing was sent to DeepSeek.” — il filtro non ha trovato stringhe. Non è stato inviato nulla.
- “Review is ready. Nothing is saved until you press Save approved.” — le proposte attendono nella tabella. Solo **Save approved** le salva.
- “Saved. The approved strings were written for the target language.” — le righe selezionate sono state salvate.
- “Not saved because of broken placeholders or HTML: N.” — N righe non sono state salvate perché il modello ha modificato un segnaposto o un tag HTML. Le corregga nella tabella oppure tolga la spunta.

### 3.4 Bulk

**Bulk** crea un'attività per molti domini e lingue. L'attività non viene eseguita in questa pagina. Attende in **Jobs**.

![Bulk](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-bulk.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Section** | Back office | Il catalogo che legge l'attività. Il campo **Theme** compare solo per **Themes**, e il campo **Module** solo per **Installed modules**. Le stringhe fuori dalla sezione scelta non entrano nell'attività. |
| **Source** | Source locale da **Settings** (en-US) | La lingua che l'attività considera come originale. Ogni destinazione viene tradotta a partire da essa. |
| **Targets** | vuoto | Le lingue che l'attività completa. Può sceglierne più d'una: tenga premuto Ctrl o Cmd e clicchi. L'attività crea stringhe separate per ogni lingua scelta. |
| **Domains** | vuoto | I domini inclusi nell'attività. I domini non selezionati non vengono tradotti. |
| **Policy** | Fill empty | **Fill empty** salta le stringhe che hanno già una traduzione. **Overwrite all** invia tutte le stringhe, anche quelle tradotte, e può sostituirle. **Outdated if equals source** invia le stringhe la cui traduzione è identica all'originale. |
| **Dry-run job** | No | L'attività chiama il modello e salva il risultato nella cronologia dell'attività, ma non scrive traduzioni nel negozio. Con **No** l'attività salva i risultati, se **Allow publish / save** è attivo. |

**Estimate** mostra il numero di stringhe, i token e il costo stimati, oltre a stringhe di esempio. Non viene inviato né salvato nulla. Messaggio: “Estimate only: N strings, ~N tokens, ~$… Nothing was sent to DeepSeek and nothing was saved.”

**Start job** crea l'attività e La porta in **Jobs** con la nuova attività aperta. Messaggio: “Job #N is waiting (N strings, est. $…). It has not run yet.”

Messaggi di errore che impediscono l'avvio:

- “Nothing was started. Select at least one target language.” — nessuna lingua di destinazione selezionata.
- “Nothing was started. Pick a theme.” oppure “Nothing was started. Pick a module.” — nella sezione **Themes** o **Installed modules** non è stato scelto un tema o un modulo.
- “Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.” — manca la chiave. Non è stata creata alcuna attività.

### 3.5 Jobs

**Jobs** è la coda delle attività di massa. Aprire l'elenco non chiama DeepSeek. Il catalogo cambia solo mentre un'attività viene elaborata e non è una prova (dry-run).

![Jobs](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-jobs.webp)

**L'elenco delle attività** ha le colonne **ID**, **Status**, **Locales**, **Progress**, **Cost**, **Employee** e **Date**. Clicchi su un'attività per vederne le stringhe. Il filtro **Failed only** mostra solo gli errori, e **Error CSV** scarica l'elenco degli errori come file.

Stati delle attività, esattamente come appaiono nella colonna **Status**: **pending** (in attesa), **running** (in corso), **paused** (in pausa), **completed** (completata), **completed_with_errors** (completata con errori), **cancelled** (annullata) e **failed** (terminata con un errore). Stati delle stringhe nei dettagli: **pending**, **processing**, **done**, **failed**, **skipped** e **rolled_back**. L'etichetta **dry-run** segnala un'attività di prova.

**Pulsanti in un'attività:**

- **Process slice** invia il blocco successivo (tante stringhe quante indica **Batch size**) e si ferma. Dopo il clic vede quali righe sono state salvate, saltate o non riuscite.
- **Auto-process** invia blocchi uno dopo l'altro finché l'attività non termina o fallisce. Tenga aperta la pagina, perché la barra di avanzamento si aggiorna da sola.
- **Pause** mette in pausa l'attività. Non traduce altre stringhe finché non la riprende.
- **Resume** rimette l'attività in coda. L'attività non parte da sola: clicchi su **Process slice** o **Auto-process**, oppure attenda la chiamata cron.
- **Retry failed** riporta le stringhe fallite allo stato in attesa.
- **Rollback** ripristina le traduzioni precedenti dove il modulo ha salvato una copia di backup prima della modifica. Prima dell'esecuzione viene chiesto: “Roll back this job?”. Messaggio dopo l'esecuzione: “Rollback: restored N translations.”
- **Error CSV** scarica l'elenco delle righe in errore.

**In questa versione del modulo, nella schermata dell'attività non c'è un pulsante di annullamento.** Non tenti di annullare un'attività da qui. La fermi con **Pause** e non la riprenda.

Se DeepSeek rifiuta troppe chiamate, l'attività si ferma da sola. Il suo errore mostra: “Rate limit — job auto-paused. Resume later.”

### 3.6 Review

**Review** è la coda delle traduzioni trattenute dal controllo di qualità. Vi finiscono le righe con un segnaposto o un HTML danneggiato, con una traduzione molto lunga o molto corta, oppure con un punteggio inferiore a 70.

![Review](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-review.webp)

| Colonna | Cosa mostra |
|---|---|
| **ID** | Il numero della riga nella coda. |
| **Domain** | Il dominio da cui proviene il testo. |
| **Source** | Il testo originale. |
| **AI** | La proposta del modello. |
| **Score** | Il punteggio automatico di qualità, da 0 a 100. |
| **Flags** | I motivi per cui la riga è stata trattenuta, descritti sotto. |

**Indicatori (flags):**

- **validation_failed** — manca un segnaposto o un tag HTML, oppure è stato modificato.
- **length_explosion** — la traduzione ha più di due volte e mezzo i caratteri dell'originale.
- **too_short** — la traduzione è inferiore al 30% della lunghezza dell'originale, e l'originale ha più di 20 caratteri.
- **possible_untranslated** — nella traduzione sono rimaste parole inglesi come “the”, “and”, “with”.
- **warning** — un avviso del controllo che abbassa il punteggio.

**Approve** segna la riga come accettata e **Reject** come rifiutata. Nessuno dei due pulsanti salva testo nel negozio. Una coda vuota mostra: “The queue is empty.” Una coda vuota non significa che tutte le lingue siano tradotte. Lo verifichi nella **Dashboard**.

Se l'attività poteva salvare e la stringa ha superato la validazione, la traduzione potrebbe essere già nel negozio. La coda **Review** è un elenco per il controllo manuale, non un blocco al salvataggio. Il salvataggio separato di righe scelte si fa in **Manual**.

### 3.7 Catalog

**Catalog** traduce i campi di prodotti, categorie e pagine CMS. Non copre i testi di International → Translations. Un blocco comprende al massimo 100 record.

![Catalog](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-catalog.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Entity** | product | Sceglie il tipo di record: **product**, **category** oppure **cms**. L'elenco dei campi cambia con la scelta. La sola scelta non traduce nulla. |
| **Fields** | campi selezionati per impostazione predefinita per il tipo | I testi che il blocco invia. Per i prodotti: **Title**, **Short description**, **Description**, **Meta title**, **Meta description** e **Friendly URL**. Per le categorie: **Title**, **Description**, **Meta title**, **Meta description** e **Friendly URL**. Per il CMS: **Title**, **Meta description**, **Meta keywords**, **Content** e **Friendly URL**. Selezioni tenendo premuto Ctrl o Cmd. I campi non selezionati non vengono inviati né modificati. |
| **Source language** | prima lingua dell'elenco | La lingua da cui viene copiato il testo. Non cambia. |
| **Target language** | prima lingua dell'elenco | La lingua che riceve la traduzione. Scelga una lingua diversa dall'origine. |
| **Only empty** | Sì | Salta i campi che hanno già un testo nella lingua di destinazione. **No** invia anche i campi compilati, e il blocco può sostituire quel testo. |
| **Start after ID** | 0 | Salta i record fino a questo ID. 0 parte dal primo record. Dopo ogni blocco il campo si riempie da solo, e il blocco successivo parte dopo quell'ID. |

Il pulsante **Translate batch (max 100)** avvia un blocco. Il risultato mostra quante righe sono state salvate e quante non sono riuscite.

Prima di portare **Only empty** su **No**, esegua un blocco piccolo e apra un prodotto nella lingua di destinazione.

### 3.8 Glossary

**Glossary** è un elenco di termini che il modello deve mantenere o tradurre in modo fisso. Aggiungere un termine non modifica le traduzioni salvate. Le traduzioni successive leggono l'elenco.

![Glossary](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-glossary.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Source term** | vuoto (obbligatorio) | La parola o l'espressione nella lingua originale, con le maiuscole se contano. Il modello tratta questo termine come fisso quando compare nel testo di origine. |
| **Target locale** | vuoto | Limita la riga a una lingua, per esempio pl-PL. Un campo vuoto applica la riga a tutte le lingue di destinazione. |
| **Target term** | vuoto | La traduzione approvata del termine. Lo lasci vuoto solo se **Do not translate** è attivo. |
| **Do not translate** | No | Il modello copia il termine senza modificarlo. Lo attivi per nomi di marchi, SKU e segnaposto. Lo disattivi quando **Target term** deve essere la traduzione. |

Il pulsante **Add** aggiunge il termine. La tabella sotto il modulo ha le colonne **Source**, **Locale**, **Target** e **Do not translate**, e ogni riga ha un pulsante **Delete** che rimuove solo quella riga. Un elenco vuoto mostra: “No glossary terms yet.”

**Import CSV** aggiunge righe da un file. Il file deve avere le colonne: source_term, target_locale, target_term, do_not_translate. L'importazione aggiunge solo le righe che riesce a leggere. **Export CSV** scarica l'elenco attuale e non modifica nulla.

I termini brevi ed esatti funzionano meglio. Un termine troppo generico verrà imposto ogni volta che compare.

### 3.9 Excludes

**Excludes** sono modelli di testo che non devono essere inviati a DeepSeek. Il testo resta invariato in PrestaShop. Il modulo lo salta alla traduzione manuale successiva, nell'attività di massa e nelle azioni di International → Translations.

![Excludes](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-excludes.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Pattern** | vuoto (obbligatorio) | Il testo o l'espressione confrontata con ogni testo di origine. A seconda di **Type**, è il testo intero, l'inizio, un frammento o un'espressione regolare. |
| **Type** | exact | **exact** è il testo intero, **prefix** è l'inizio, **contains** è un frammento in qualsiasi punto e **regex** è un'espressione regolare PHP. Un modello troppo ampio salta più di quanto si aspetti. Inizi con uno breve. |

Il pulsante **Add** aggiunge il modello. La tabella ha le colonne **Pattern**, **Type** e **On** (se il modello è attivo). Ogni riga ha un pulsante **Delete** che rimuove solo quel modello. Le traduzioni salvate non vengono cancellate. Un elenco vuoto mostra: “No patterns yet.”

Usi i modelli per i testi che devono restare nella lingua di origine, come nomi legali o token tecnici. Se un testo deve essere tradotto in modo fisso, usi **Glossary**.

### 3.10 History

**History** è l'elenco completo delle chiamate salvate a DeepSeek: traduzione manuale, pagina International → Translations, attività di massa, Catalog e test di connessione. Ogni riga conserva il prompt, la risposta, il modello, le lingue, il numero di token e il tempo di risposta.

![History](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-history.webp)

- **When** è la data della chiamata. **Type** indica da dove è partita. Per un'attività di massa il numero dopo il tipo è il numero dell'attività.
- **View** apre il prompt inviato e la risposta ricevuta in una finestra di questa pagina. Una riga con errore mostra l'errore al posto della risposta.
- Filtri: date, **Model**, tipo, stato, lingua, collaboratore e una parola nel prompt o nella risposta. I pulsanti **Previous** e **Next** cambiano pagina.
- **HTTP 401** o **HTTP 403** significa che la chiave in **Settings** è errata o che l'account non ha accesso al modello scelto.
- **Clear history** elimina queste voci, e le traduzioni salvate restano. La domanda prima di eliminare è: “Clear the stored history? Saved translations stay.”

Questa pagina non invia nuove richieste e non modifica le traduzioni. Se le traduzioni si fermano all'improvviso, guardi prima la riga con errore più recente, prima di modificare il glossario.

### 3.11 Updates

La scheda **Updates** mostra la sezione **MyPresta Updates**. Il pulsante **Check Now** accanto a **Manual Check** verifica subito se esiste una versione più recente del modulo. Il campo **Automatic Notifications** (**Enabled** o **Disabled**) decide se il modulo controlla da solo. Salvi la scelta con **Save**.

Quando le notifiche automatiche sono attive, il modulo controlla la versione ogni 3 giorni, all'apertura del back office. Invia al server di MyPresta il nome del modulo, la sua versione, l'indirizzo del negozio e l'identificativo della licenza, se è salvato. Disattivare questa opzione ferma questi controlli automatici.

![Updates](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-updates.webp)

### 3.12 Pulsanti accanto ai campi dei moduli del negozio

Accanto ai campi multilingue dei moduli di prodotti, categorie, CMS e di altri moduli del back office compare un pulsante di traduzione. Quando ci sono campi selezionati, compare anche una barra in fondo al modulo.

![Prodotto – traduzione di un campo](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-translate.webp)

![Prodotto – campi meta](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-meta.webp)

![Prodotto – barra di traduzione](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-bulk-bar.webp)

![Modulo categoria con la barra di traduzione](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-category-translate.webp)

**La barra** in basso ha i campi **Source** e **Target** e i pulsanti **Check all**, **Uncheck all**, **Check empty**, **Translate empty** e **Translate selected**. Il contatore **Selected** mostra quanti campi sono selezionati.

Il pulsante accanto a un campo compila solo quel campo. Perché la modifica resti nel negozio, clicchi sul pulsante **Save** di PrestaShop in fondo al modulo. La barra funziona allo stesso modo: compila i campi selezionati e richiede di salvare il modulo.

Messaggi della barra:

- “Fill the source language field first.” — il campo di origine è vuoto. Scriva un testo nella lingua di origine e riprovi.
- “Tick at least one field.” — non è selezionato nessun campo.
- “Target is not a language from this shop.” — la lingua di destinazione scelta non appartiene al negozio.
- “Translating…” e “Done” — traduzione in corso oppure conclusa.

I pulsanti e la barra scompaiono quando gli interruttori in **Settings** sono disattivati. Per i moduli del negozio sono gli interruttori **shop forms** a controllarli.

### 3.13 Pagina International → Translations

Nella pagina International → Translations compare un pulsante di traduzione accanto a ogni campo, e in basso la stessa barra. La barra ha il campo **Source** (en-US per impostazione predefinita) e il campo **Target**. Scelga la lingua che vuole completare.

![Pagina International → Translations](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-translations-page.webp)

- Il pulsante accanto a un campo lo compila con la traduzione. A salvarlo è solo il pulsante **Save** di PrestaShop in questa pagina.
- La barra traduce i campi selezionati uno alla volta.
- **Translate empty in this section** traduce i campi vuoti della sezione aperta.
- Nella sezione **Emails** il modulo legge il file di origine del modello. Se non lo trova, compare il messaggio: “The source language mail file was not found.” In tal caso scelga un'altra lingua di origine in **Settings**.
- Il messaggio “The source language field is not on this page.” significa che in questa pagina non c'è un campo della lingua di origine. Apra un'altra scheda o sezione che contenga quella lingua.

Gli interruttori **Individual field buttons** e **Individual field checkboxes — International → Translations** in **Settings** nascondono i pulsanti e la barra solo in questa pagina.

## 4. Vetrina

Il modulo non mostra nulla ai clienti. Non aggiunge pagine, blocchi, pulsanti o messaggi nella vetrina del negozio, quindi il tema non mostra alcun effetto del modulo e non viene fatta alcuna cattura della vetrina. I clienti non hanno nessun passaggio nel modulo.

L'unico indirizzo con cui un server esterno può richiamare il modulo è l'indirizzo cron di **Settings**. Non è destinato ai clienti. Il server lo usa per elaborare le attività.

Cosa vede aprendo questo indirizzo nel browser:

| Cosa vede | Cosa fare |
|---|---|
| Il testo `{"ok":false,"error":"Forbidden"}` | L'indirizzo è errato oppure il suo token è scaduto. Copi di nuovo la CRON URL da **Settings** e la incolli nella pianificazione. |
| Il testo `{"ok":true,"message":"No pending jobs"}` | Nessuna attività è in attesa. È normale, non c'è nulla da fare. |
| Il testo `{"ok":true,...}` con i dati di un blocco | Un blocco è stato elaborato. I dettagli si vedono in **Jobs**. |
| Il testo `{"ok":false,"error":"..."}` con un messaggio | Legga il messaggio e vada al paragrafo 5 di questo manuale. |

## 5. Problemi

**Nessuna voce nel menu International.** La causa tipica è la cache del negozio. Vada in **Advanced Parameters → Performance** e clicchi su **Clear cache**. Se la voce continua a non comparire, disinstalli il modulo e lo reinstalli. La disinstallazione rimuove le impostazioni e la cronologia delle attività, quindi salvi prima la chiave API e le impostazioni.

**“Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.”** Non è stata inserita una chiave, oppure è stata rimossa. Apra **Settings**, incolli la chiave del Suo account DeepSeek, clicchi su **Save** e poi su **Test connection**.

**“No DeepSeek API key. Nothing was translated.”** È lo stesso caso: incolli la chiave in **Settings** e salvi.

**“Settings saved. No API key is stored, so nothing can be translated until you paste one.”** Le impostazioni sono state salvate senza chiave. Incolli la chiave e salvi di nuovo.

**Test connection fallisce, oppure History mostra HTTP 401 o 403.** La chiave è errata, scaduta, oppure l'account non ha accesso al modello scelto. Incolli di nuovo la chiave. Se l'errore riguarda il modello, scelga un altro modello dall'elenco oppure aggiunga un identificativo valido in **Add a DeepSeek model**.

**“DeepSeek rate limit (429). Try again later.”** DeepSeek ha limitato il numero di chiamate. Attenda qualche minuto, poi riprenda l'attività in **Jobs** con **Resume** e **Process slice**. Se l'errore torna, abbassi **Batch size** in **Settings**.

**“Rate limit — job auto-paused. Resume later.”** L'attività si è messa in pausa da sola dopo troppe chiamate rifiutate. Dopo un po', clicchi su **Resume** nell'attività, poi su **Process slice** o **Auto-process**.

**“Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.”** L'attività attende un avvio manuale o la chiamata cron. Clicchi su **Process slice** o **Auto-process**. Per far girare le attività senza clic, aggiunga la CRON URL alla pianificazione del server e la richiami regolarmente.

**“Monthly API budget has been exhausted.”** È stato raggiunto il tetto mensile **Budget USD / month**. Apra **Settings**, aumenti l'importo oppure imposti 0 per rimuovere il tetto. Le nuove traduzioni riprendono quando l'attività viene ripresa.

**“Allow publish is off in Settings.”** Il salvataggio delle traduzioni è bloccato. Apra **Settings** e attivi **Allow publish / save**. Senza questa opzione, **Process slice** non salverà alcun testo nel negozio.

**“Not saved because of broken placeholders or HTML: N.”** N righe non sono state salvate perché il modello ha modificato un segnaposto o un tag HTML. Apra **Review** oppure la tabella di **Manual**, corregga la proposta e salvi di nuovo, oppure rifiuti la riga.

**L'attività è terminata con lo stato completed_with_errors.** Alcune stringhe non sono riuscite. In **Jobs** attivi il filtro **Failed only**, scarichi il **Error CSV** e clicchi su **Retry failed** per riprovare le stringhe fallite.

**Una traduzione non si può annullare.** **Rollback** ripristina solo le traduzioni per le quali il modulo ha salvato una copia di backup prima della modifica. Le copie appartengono all'attività. Scompaiono quando il modulo viene disinstallato.

**La traduzione è salvata, ma la pagina mostra il vecchio testo.** Svuoti la cache: **Advanced Parameters → Performance → Clear cache**. Nei moduli del negozio e in International → Translations ricordi che i pulsanti e la barra si limitano a compilare i campi. A salvarli è il pulsante **Save** di PrestaShop.

**I pulsanti di traduzione non compaiono accanto ai campi.** Gli interruttori sono disattivati. Apra **Settings** e attivi l'interruttore giusto: **Individual field buttons** oppure **Individual field checkboxes** per i moduli del negozio, oppure per International → Translations.

**“Fill the source language field first.”** Il campo della lingua di origine è vuoto. Scriva un testo in quella lingua e riprovi.

**“The source language mail file was not found.”** Per questo modello di e-mail non esiste un file nella lingua di origine. Scelga un altro **Source locale** in **Settings**, oppure traduca il modello a mano.

**Dopo Start job non succede nulla.** Start job crea soltanto l'attività e non la avvia. Apra **Jobs** e clicchi su **Process slice** o **Auto-process**.

**L'e-mail sull'attività conclusa non arriva.** Verifichi che **Email notify on complete** sia attivo e che l'indirizzo in **Notify email** sia corretto. Un campo vuoto invia all'indirizzo del negozio. L'e-mail viene inviata solo al termine dell'attività. Verifichi anche che il negozio invii e-mail in **Advanced Parameters → E-mail**.

**Un'attività non si può annullare.** Questa versione del modulo non ha un pulsante di annullamento nella schermata dell'attività. Fermi l'attività con **Pause** e non la riprenda.

**History è vuoto oppure mostra “No requests yet.”** Non è ancora stata effettuata alcuna chiamata a DeepSeek. Anche la Dashboard mostra zeri finché non esegue una traduzione.

## 6. Per gli sviluppatori

Questo paragrafo descrive il codice del modulo. Le chiavi di configurazione e i nomi delle classi compaiono solo qui.

### 6.1 Panoramica

- **Classe principale:** `myaitranslationsdeepseek` (estende `Module`), file `myaitranslationsdeepseek.php`.
- **Nome tecnico:** `myaitranslationsdeepseek`. Il prefisso delle chiavi di configurazione e delle tabelle è `MYAITDS_` e `myaitds_`.
- **Versione:** 1.2.0.
- **Nome nell'elenco dei moduli:** AI Translations with DeepSeek.
- **Autore nel codice:** MyPresta.eu. Scheda: `administration`.
- **Compatibilità:** PrestaShop da 1.7.0.0 a 99.99.99, `bootstrap = true`, `need_instance = 0`.
- **Scheda di menu:** classe `AdminMyaitranslationsdeepseek`, padre `AdminInternational` (ripiego: `IMPROVE`).

Flusso dei dati: le impostazioni vengono lette da `MyaitdsConfigService` da `Configuration` (chiavi `MYAITDS_*`). I servizi `MyaitdsTranslateService`, `MyaitdsJobWorker` e `MyaitdsCatalogTranslateService`, e il controller del back office, chiamano `MyaitdsDeepSeekTranslationProvider`, che invia una richiesta cURL a `https://api.deepseek.com/chat/completions` (timeout di 120 s, timeout di connessione di 15 s). La risposta passa dai validatori (`MyaitdsPlaceholderValidator`, `MyaitdsHtmlValidator`, `MyaitdsPsNativeValidator`) e da `MyaitdsQualityScorer`. Il salvataggio passa da `MyaitdsTranslationAdapterFactory` al servizio di traduzione di PrestaShop, e alla tabella `translation` se il servizio manca. Per i moduli classici il salvataggio va nel `translations/{iso}.php` del modulo stesso. Le chiamate sono registrate in `myaitds_request` e `myaitds_api_log`, i costi in `myaitds_usage_ledger`. La memoria di traduzione (`myaitds_memory`) permette di evitare una chiamata all'API per la stessa origine, lingua, modello e versione del glossario.

### 6.2 File

| File | Scopo |
|---|---|
| `myaitranslationsdeepseek.php` | Classe principale: installazione, disinstallazione, scheda di menu, hook del back office, reindirizzamento `getContent()` al controller. |
| `sql/install.php` | Crea le 11 tabelle (`CREATE TABLE IF NOT EXISTS`). |
| `sql/uninstall.php` | Elimina le 11 tabelle (`DROP TABLE IF EXISTS`). |
| `controllers/admin/AdminMyaitranslationsdeepseekController.php` | Controller del back office: tutte le schede, azioni dei moduli, azioni delle attività e richieste AJAX. |
| `controllers/front/cron.php` | Controller front `cron`: elabora un blocco di un'attività. |
| `src/Admin/MyaitdsForms.php` | Moduli HelperForm e i loro testi `desc`. |
| `src/Admin/MyaitdsSectionHelp.php` | Testo di aiuto di ogni scheda. |
| `src/Service/MyaitdsConfigService.php` | Legge e scrive `MYAITDS_*`, elenco dei modelli, intervalli di valori, chiave API. |
| `src/Service/MyaitdsTranslateService.php` | Traduzione manuale e con pulsanti: memoria, budget, validazione, salvataggio. |
| `src/Service/MyaitdsBulkJobFactory.php` | Stima e creazione delle attività di massa. |
| `src/Service/MyaitdsCatalogTranslateService.php` | Campi di prodotti, categorie e CMS, blocchi di al massimo 100 record. |
| `src/Service/MyaitdsDashboardService.php` | Calcolo della copertura (testi mancanti e tradotti). |
| `src/Service/MyaitdsRateLimiter.php` | Limite di chiamate al minuto, salvato in `var/rate_limit.json`. |
| `src/Job/MyaitdsJobWorker.php` | Elabora i blocchi, salva, snapshot, coda di revisione, e-mail di fine attività. |
| `src/Job/MyaitdsJobRepository.php` | Legge e scrive le attività e le loro stringhe. |
| `src/Job/MyaitdsJobStatuses.php` | Costanti per gli stati di attività e stringhe. |
| `src/Provider/MyaitdsDeepSeekTranslationProvider.php` | Chiamata all'API DeepSeek (cURL), gestione degli errori e dei codici HTTP. |
| `src/Provider/MyaitdsPromptBuilder.php` | Costruisce il prompt con tono, voce del marchio e glossario. |
| `src/Provider/MyaitdsProviderFactory.php` | Crea il fornitore (attualmente solo DeepSeek). |
| `src/Provider/MyaitdsTranslationProviderInterface.php` | Interfaccia del fornitore di traduzione. |
| `src/Adapter/MyaitdsTranslationAdapterInterface.php` | Interfaccia di accesso al catalogo di PrestaShop. |
| `src/Adapter/MyaitdsAbstractTranslationAdapter.php` | Logica comune: sezioni, domini, salvataggio, svuotamento della cache. |
| `src/Adapter/MyaitdsFilesystemCatalogueTrait.php` | Scansione dei file XLF e delle directory di traduzione. |
| `src/Adapter/MyaitdsLegacyModuleCatalogue.php` | Legge e scrive i `translations/{iso}.php` dei moduli classici. |
| `src/Adapter/MyaitdsTranslationAdapter.php` | Implementazione concreta dell'adattatore (estende l'adattatore astratto). |
| `src/Adapter/MyaitdsTranslationAdapterFactory.php` | Crea l'adattatore. |
| `src/Quality/MyaitdsPlaceholderValidator.php` | Controlla i segnaposto nella traduzione. |
| `src/Quality/MyaitdsHtmlValidator.php` | Controlla i tag HTML. |
| `src/Quality/MyaitdsPsNativeValidator.php` | Combina il controllo di segnaposto e HTML. Usa le classi di PrestaShop (`Validate::isCleanHtml`) quando sono disponibili. |
| `src/Quality/MyaitdsEmailHtmlPipeline.php` | Protegge dalla traduzione tag e variabili dei modelli e-mail. |
| `src/Quality/MyaitdsQualityScorer.php` | Punteggio 0–100, indicatori e decisione di messa in coda di revisione (soglia 70). |
| `src/Glossary/MyaitdsGlossaryRepository.php` | Legge e scrive il glossario. Import ed export CSV sono nel controller. |
| `src/Glossary/MyaitdsExcludePatternRepository.php` | Modelli di esclusione. |
| `src/Audit/MyaitdsRequestLogRepository.php` | Cronologia delle chiamate (**History**): salvataggio, filtri, visualizzazione e pulizia secondo la conservazione. |
| `src/Audit/MyaitdsApiLogRepository.php` | Registro dell'API e relativa conservazione. |
| `src/Audit/MyaitdsTranslationMemory.php` | Memoria di traduzione (hash di origine, lingua, modello e glossario). |
| `src/Audit/MyaitdsUsageLedger.php` | Consumo mensile e costi, origine del budget. |
| `src/Audit/MyaitdsSnapshotService.php` | Valori prima di una modifica e relativo ripristino (**Rollback**). |
| `src/Security/MyaitdsApiKeyEncryptor.php` | Cifratura della chiave API (AES-256-CBC). |
| `views/templates/admin/configure.tpl` | Struttura del pannello a schede. |
| `views/templates/admin/_partials/*.tpl` | Contenuto delle schede: dashboard, manual, bulk, jobs, review, catalog, glossary, excludes, logs, settings, history-stats. |
| `views/js/admin.js` | Logica del back office: attività, elaborazione automatica, moduli. |
| `views/js/admin-help.js` | Finestre di aiuto delle schede. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Grafici della **Dashboard**. |
| `views/js/entity-fields.js` | Pulsanti e barra accanto ai campi dei moduli del negozio. |
| `views/js/translations-tool.js` | Pulsanti e barra in International → Translations. |
| `views/css/admin.css` | Stili del pannello e dei pulsanti. |
| `lib/updateChecker.php` | Verifica delle versioni presso MyPresta e scheda **Updates**. |
| `translations/*.php` | Traduzioni del modulo (27 lingue, incluso `pl.php`). |
| `var/rate_limit.json` | Stato del limite di chiamate al minuto. |
| `logo.png`, `logo.gif` | Logo nell'elenco dei moduli e nel pannello. |

### 6.3 Controller

**Back office:** `AdminMyaitranslationsdeepseekController`, scheda `AdminMyaitranslationsdeepseek`, padre `AdminInternational`. La scheda si sceglie con il parametro `myaitds_tab`. Valori ammessi: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (la scheda **History**), `review`, `catalog` e `updates`. Qualsiasi altro valore apre `dashboard`. Il controller non definisce permessi propri: si applicano i permessi di scheda impostati in PrestaShop.

Azioni dei moduli (`Tools::isSubmit`): `submitMyaitranslationsdeepseekSettings`, `…Ping` (Test connection), `…AddModel`, `…GlossaryAdd`, `…GlossaryImport`, `…GlossaryExport`, `…ExcludeAdd`, `…BulkPreview`, `…Bulk`, `…ManualFilter`, `…ManualTranslate`, `…SaveReview`, `…Catalog`, `…Dashboard`, `…ClearHistory`.

Azioni GET: `job_action` (`process`, `pause`, `resume`, `retry_failed`, `rollback`, `export_errors`; `cancel` è gestita, ma nessun template crea un collegamento ad essa), `review_action` (`approve`, `reject`) con `id_review`, `delete_deepseek_model`, `delete_glossary`, `delete_exclude`.

Azioni AJAX (`?controller=AdminMyaitranslationsdeepseek&ajax=1&action=…`), gestite dai metodi `displayAjax*`: `HistoryDetail` (dettaglio di una riga della cronologia, parametro `hist_id`), `ProcessJob` (un blocco, `id_job`), `JobStatus` (stato dell'attività), `TranslatePageLines` (righe della pagina di traduzione), `MailSource` (file di origine di un modello e-mail), `ListDomains` (domini di una sezione).

**Front:** `MyaitranslationsdeepseekCronModuleFrontController` in `controllers/front/cron.php`. L'indirizzo ha la forma `index.php?fc=module&module=myaitranslationsdeepseek&controller=cron&token=…`. Impostazioni del controller: `$ssl = true`, `$ajax = true`. Parametri: `token` (obbligatorio, confrontato con `MYAITDS_CRON_TOKEN` tramite `hash_equals`) e `id_job` facoltativo. Senza `id_job`, il modulo prende la prima attività con stato `pending` o `running` tra le 20 più recenti. Un token errato restituisce HTTP 403 con `{"ok":false,"error":"Forbidden"}`. Senza attività restituisce `{"ok":true,"message":"No pending jobs"}`. Un blocco elaborato restituisce il risultato di `processSlice`.

### 6.4 Hook

Registrati all'installazione:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: rinomina la scheda se il nome è ancora tecnico, e carica le risorse del back office.
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: carica le stesse risorse.

`loadBoAssets()` funziona così: sulla scheda `AdminMyaitranslationsdeepseek` aggiunge `admin.css`, `admin.js`, `admin-help.js`, e su **Dashboard** anche `chart.min.js` e `history-charts.js`. Sulla pagina `AdminTranslations` aggiunge `translations-tool.js` quando pulsanti o barra di International → Translations sono attivi (`MYAITDS_TR_BUTTONS` o `MYAITDS_TR_BULK`). Nelle altre pagine del back office aggiunge `entity-fields.js` quando pulsanti o barra dei moduli del negozio sono attivi (`MYAITDS_ENTITY_BUTTONS` o `MYAITDS_ENTITY_BULK`). Passa la configurazione tramite `Media::addJsDef` come `myaitdsTr` e `aitHelpLabels`.

Il modulo **non espone** hook propri: non chiama `Hook::exec` e non registra hook lato front.

Il modulo **non ha** i metodi `enable()` né `disable()`. Attivare o disattivare non esegue alcuna azione del modulo. PrestaShop rimuove gli hook alla disinstallazione.

### 6.5 Override

Il modulo non ha una directory `override/` e non sovrascrive nessuna classe né nessun controller di PrestaShop.

File scritti dal modulo: le traduzioni passano dal servizio di traduzione di PrestaShop (`prestashop.service.translation`), e dalla tabella `translation` se il servizio manca. Per i moduli classici (chiavi nel formato `<{nome}>prestashop`) il modulo riscrive il `translations/{iso}.php` di quel modulo, prima in un file temporaneo e poi rinominandolo. Svuota la cache con `Tools::clearCache()`. Scrive inoltre `var/rate_limit.json` e i valori `update_<modulo>`, `updatev_<modulo>` e `mypresta_updates` in `Configuration`.

### 6.6 Database

Le tabelle usano il prefisso del negozio (`_DB_PREFIX_`). Sono tutte create con il motore `_MYSQL_ENGINE_` e la collation `utf8mb4_unicode_ci`.

| Tabella | Contenuto |
|---|---|
| `myaitds_glossary` | Termini del glossario: `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, date. Indice `idx_shop_locale`. |
| `myaitds_exclude_pattern` | Modelli di esclusione: `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`, `date_add`. |
| `myaitds_job` | Attività: `uuid` (univoco), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, contatori `items_*`, token, `cost_usd_estimate` e `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`. |
| `myaitds_job_item` | Stringhe di un'attività: `id_myaitds_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`. |
| `myaitds_memory` | Memoria di traduzione: `memory_hash` (univoco), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitds_usage_ledger` | Consumo giornaliero: `usage_date`, `id_myaitds_job`, `model`, token, `cost_usd`. Origine del budget mensile. |
| `myaitds_snapshot` | Valori prima di una modifica: `id_myaitds_job`, `id_myaitds_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. Origine di **Rollback**. |
| `myaitds_api_log` | Registro dell'API: `id_myaitds_job`, `level`, `provider`, `http_code`, `message`, `context_json`. Pulito secondo `MYAITDS_LOG_RETENTION_DAYS`. |
| `myaitds_request` | Cronologia delle chiamate (**History**): tipo, stato, modello, lingue, codice HTTP, durata, token, costo, `prompt`, `reply`, `error_message`. Pulita secondo la conservazione. |
| `myaitds_review` | Coda di revisione: `id_myaitds_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`. |
| `myaitds_catalog_item` | Creata all'installazione, ma nessun codice vi scrive né vi legge. |

L'installazione crea le tabelle solo con `CREATE TABLE IF NOT EXISTS`. Il modulo non aggiunge colonne all'apertura di una pagina (nel codice non c'è alcun `ALTER TABLE`).

La disinstallazione elimina tutte le 11 tabelle. Una reinstallazione le ricrea vuote.

### 6.7 Chiavi e traduzioni

**Chiavi di configurazione** (prefisso `MYAITDS_`) e valori iniziali di `installDefaults()`:

| Chiave | Valore iniziale | Note |
|---|---|---|
| `API_KEY_ENC` | `''` | Chiave cifrata con AES-256-CBC; la chiave di cifratura deriva da `_COOKIE_KEY_`. |
| `MODEL` | `deepseek-flash` | Il modello per le chiamate. |
| `EXTRA_MODELS` | `''` | Identificativi di modello aggiunti (**Add a DeepSeek model**). |
| `PROVIDER` | `deepseek` | L'unico fornitore. Non ha un campo nel pannello. |
| `TONE` | `formal` | `formal`, `casual`, `brand`. |
| `CUSTOM_VOICE` | `''` | Testo della voce del marchio. |
| `BATCH_SIZE` | `25` | Intervallo 1–100. |
| `MONTHLY_BUDGET` | `0` | 0 = nessun tetto. |
| `SOURCE_LOCALE` | `''` | Vuoto significa che la schermata fornisce l'origine. Valore di ripiego nel codice: `en-US`. |
| `TEMPERATURE` | `0.2` | Intervallo 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Intervallo 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | Il campo del modulo si chiama `MYAITDS_RATE_LIMIT`. 0 disattiva il limite. |
| `LOG_RETENTION_DAYS` | `30` | Minimo 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Interruttore dell'e-mail. |
| `NOTIFY_EMAIL` | `''` | Vuoto = `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Blocca il salvataggio da **Manual**, dalle attività e da **Catalog**. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Pulsanti e barra accanto ai campi dei moduli del negozio. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Pulsanti e barra in International → Translations. |
| `MAX_TOKENS` | `0` | 0 = limite predefinito di DeepSeek. |
| `CRON_TOKEN` | 16 byte casuali (hex) | Token dell'indirizzo cron. |

Alla disinstallazione vengono rimosse le chiavi sopra indicate, più `DEEPL_API_KEY` e `CLAUDE_API_KEY`, che il modulo non usa più.

**Testi che non passano da `$this->l()`.** I testi dei campi e dell'aiuto passano da `l()` nei domini `myaitdsforms` (`MyaitdsForms`) e `sectionhelp` (`MyaitdsSectionHelp`). Le etichette JavaScript vanno a `Media::addJsDef` tramite `translationClientConfig()`. Oggetto e testo dell'e-mail di fine attività sono in inglese in `MyaitdsJobWorker::notifyComplete()` e non passano da `l()`. I messaggi mostrati con `$this->module->l()` nel controller usano il dominio `adminmyaitranslationsdeepseekcontroller`.

**Aggiungere una lingua:** crei un file `translations/{iso}.php` seguendo il modello di quelli esistenti (per esempio `translations/pl.php`). PrestaShop carica il file che corrisponde al codice ISO del negozio.

**Origine dei testi dei campi:** `MyaitdsForms::help()` (il `desc` di ogni campo) e `MyaitdsSectionHelp::pages()` e `brief()` (testo di aiuto delle schede).

### 6.8 Estensione

- **Tema:** non c'è nulla da sovrascrivere. Il modulo non renderizza template front.
- **Template del back office:** `views/templates/admin/`. Le modifiche ai file del modulo vengono perse con l'aggiornamento.
- **Nuovi modelli DeepSeek:** nessuna modifica al codice; usi **Add a DeepSeek model** (`EXTRA_MODELS`).
- **Nuovo fornitore:** implementi `MyaitdsTranslationProviderInterface` e aggiunga una voce in `MyaitdsProviderFactory`.
- **Soglia della coda di revisione:** 70 punti, impostata in `MyaitdsQualityScorer::score()`.
- **Glossario ed esclusioni:** si gestiscono nel pannello, senza modifiche al codice.

## 7. Assistenza

Pagina del modulo: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html

Acceda al Suo account cliente su mypresta.eu, vada alla pagina dei contatti e scelga l'argomento **Support for paid modules**. Il modulo indica che per i moduli a pagamento è richiesto l'accesso. Dopo l'accesso, selezioni questo modulo dalla cronologia degli acquisti.
