---
title: "Quote Enterprise - manuale per il rivenditore"
sidebar:
  label: "Quote Enterprise - manuale per il rivenditore"
description: "Come configurare Quote Enterprise, gestire l'intero processo da preventivo a ordine e risolvere i problemi comuni."
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Quote Enterprise su MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/quote-enterprise/)
>
> ---


## 1. Requisiti

Il modulo funziona su PrestaShop 1.7, 8 e 9 e su PHP da 7.1 a 8.5.

Il server richiede cURL e JSON. Non richiede un altro modulo.

Crei Lei stesso le chiavi Google reCAPTCHA solo se attiva reCAPTCHA. I webhook Slack o Teams sono opzionali e servono solo ai digest per lo staff. Le e-mail di promemoria e i digest richiedono un job cron sul server all'URL cron del modulo.

## 2. Installazione

1. Carichi il modulo in **Modules**, **Module Manager** e lo attivi.
2. Dopo l'installazione, **Orders** ha due voci: **Quotes** e **Audit log**.
3. Il modulo non svuota la cache durante l'installazione.
4. L'installazione crea le tabelle dei preventivi e un prodotto virtuale nascosto per le righe di servizio personalizzate. Scrive anche le impostazioni predefinite descritte di seguito.

La disinstallazione rimuove le voci di menu, le tabelle del modulo e le chiavi di configurazione. Il prodotto fee nascosto nel catalogo non viene eliminato dalla disinstallazione.

## 3. Configurazione e lavoro nel back office

Apra **Modules**, **Module Manager**, **Quote Enterprise**, **Configure**. Il modulo si apre su **Dashboard**. La barra superiore ha: **Dashboard**, **Quotes**, **Audit log**, **Settings**, **PDF**, **Emails**, **API**, **Notifications**, **Updates**.

Le schermate di questo manuale provengono da un back office in inglese.

Il lavoro quotidiano sui preventivi si trova anche in **Orders**, **Quotes** (elenco completo ed editor) e **Orders**, **Audit log**.

### 3.1 Processo completo del preventivo

Usi questo flusso come mappa. Le sezioni seguenti spiegano ogni schermata.

1. Un cliente richiede un preventivo dalla pagina prodotto, da un elenco prodotti, dal carrello o da un elenco preventivo multiprodotto. Gli ospiti possono vedere i pulsanti se consentito, ma il salvataggio della richiesta richiede sempre un account cliente.
2. La richiesta diventa un preventivo in **Pending review** (richiesta del cliente) oppure lo staff crea una **Draft** dal back office.
3. Lo staff apre il preventivo in **Orders**, **Quotes**, imposta prezzi, sconti, spedizione e messaggi, poi **Save** oppure **Save & send**.
4. **Save & send** invia l'e-mail al cliente e porta il preventivo a **Sent** (oppure mantiene il flusso di negoziazione in caso di reinvio).
5. Il cliente apre **My quotes**, visualizza l'offerta, può scaricare il PDF, accettare, rifiutare o chiedere modifiche (**Negotiation**).
6. Dopo **Accepted**, il cliente può procedere al checkout. Il checkout costruisce un carrello dal preventivo e può diventare un ordine (**Converted**). Il preventivo si blocca.
7. Dopo **valid until**, i preventivi inviati o in negoziazione diventano **Expired** quando vengono aperti o quando viene eseguito il cron. Le e-mail di promemoria richiedono il cron.

Stati che vedrà: **Draft**, **Pending review**, **Sent**, **Negotiation**, **Accepted**, **Converted**, **Expired**, **Rejected**, **Cancelled**.

Solo **Sent** e **Negotiation** possono essere accettati dal cliente. Cambi lo stato manualmente nell'editor quando serve.

### 3.2 Dashboard

La dashboard mostra la pipeline dei preventivi. Apra **Analytics parameters** per impostare il periodo KPI e gli intervalli dei grafici, poi faccia clic su **Save analytics parameters**. Conferma: **Tracking parameters updated.**

![Dashboard](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard.webp)

![Dashboard tables](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard-b.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **KPI period** | **Last 90 days** | Finestra temporale per le card KPI, la tabella funnel, i migliori clienti e lo staff. Scelga 30, 90, 180 o 365 giorni e salvi. Conta preventivi creati, inviati, accettati, convertiti e rifiutati in quel periodo. |
| **Weekly chart range** | 12 | Numero di settimane sul grafico funnel settimanale (4–52). La scheda Weekly mostra creati, inviati, accettati e convertiti per settimana ISO. |
| **Monthly chart range** | 12 | Numero di mesi sul grafico funnel mensile (3–24). |
| **Yearly chart range** | 5 | Numero di anni sul grafico funnel annuale (2–10). |
| **Default chart tab** | **Monthly** | Quale scheda grafico si apre per prima: Weekly, Monthly o Yearly. Può comunque cambiare scheda senza salvare. |
| **Expiring soon window** | 7 | Quanti giorni in avanti contrassegnare i preventivi come in scadenza. In genere 7 o 14. Solo preventivi sent e negotiation con una data valid_until in questa finestra vengono elencati. |

Card KPI: valore della pipeline aperta, pending review, in scadenza, valore convertito, tasso di conversione, win rate. Sotto: creati, inviati, accettati, convertiti, rifiutati, giorni medi alla conversione, valore medio del preventivo. I grafici mostrano il funnel nel tempo. Tabelle: funnel del periodo, aging della pipeline aperta, in scadenza, attività recente, migliori clienti e staff. Pipeline aperta significa preventivi sent, negotiation o accepted.

### 3.3 Scheda Quotes nella configurazione del modulo

Questa scheda è una panoramica breve. Filtri completi, azioni di massa ed editor sono in **Orders**, **Quotes**.

![Quotes overview](https://mypresta.eu/docs/images/docs/quoteenterprise-quotes.webp)

Scopo di questa schermata: un elenco rapido dei preventivi recenti dalla configurazione del modulo. Faccia clic su **View** per aprire l'editor completo del preventivo. Usi **Manage all quotes** per filtri, esportazione e operazioni di massa. Effetto: mantiene leggere le impostazioni del modulo mentre il lavoro completo sui preventivi avviene nella schermata dedicata del back office.

**Create quote:** selezioni un cliente (ricerca), facoltativamente digiti una **Internal note**, faccia clic su **Create draft quote**. Viene reindirizzato all'editor completo. Cliente vuoto mostra **Please select a customer.**

**Quote templates** (quando esistono modelli): scelga un modello e un cliente, poi **Create from template**.

Colonne **Recent quotes**: Reference, Customer, Status, Total. Vuoto: **No quotes yet.** Collegamenti: **Manage all quotes**, **CSV**, **XML**, **Open full quotes list**.

### 3.4 Elenco Quotes (menu Orders)

Apra **Orders**, **Quotes**. Questa è la schermata principale di gestione.

Colonne: **ID**, **Reference**, **Customer**, **Status**, **Total**, **Valid until**, **Assigned**, **Created**. Azioni di riga: modifica e duplica. Non può aggiungere un preventivo vuoto dalla barra dell'elenco; crei dalla panoramica del modulo, da un modello o duplicando. Errore se ci prova: **Create quotes from module configuration or duplicate an existing quote.**

Azioni di massa:

| Azione | Cosa fa |
|---|---|
| **Assign to employee** | Imposta l'impiegato assegnato sui preventivi selezionati. |
| **Extend validity** | Sposta in avanti la validità per la selezione. |
| **Send expiry reminder** | Invia e-mail di promemoria ai clienti selezionati (finestra di conferma). |
| **Export CSV** | Scarica CSV per la selezione. |
| **Export XML** | Scarica XML per la selezione. |

Filtri per stato e ricerca come in un elenco PrestaShop standard. Apra una riga per modificare.

### 3.5 Editor preventivo — come gestire una richiesta

Apra un preventivo dall'elenco. La legenda mostra il riferimento e lo stato, ad esempio `Q-2026-00001 — Pending review`.

**Percorso tipico dello staff per una nuova richiesta del cliente**

1. Filtri o apra i preventivi in **Pending review**.
2. Controlli **Messages from customer** (testo della richiesta, poi motivi di modifica o rifiuto). Solo lettura.
3. Aggiunga o regoli **Line items** (prodotti di catalogo e servizi personalizzati).
4. Imposti **Global discount %** / **Global discount amount**, **Shipping label** e gli importi di spedizione.
5. Scriva **General message to customer** e facoltativamente **Internal note**.
6. Imposti **Validity period** e **Validity unit**, controlli la validità attuale.
7. Imposti **Status** se necessario, poi **Save** (**Quote saved.**) oppure **Save & send** (**Quote sent to customer by e-mail.**).

**Blocco.** I preventivi accepted o converted si bloccano. I preventivi scaduti mostrano: **This quote has expired. Click Unlock to extend validity and send an updated offer.** Convertiti: **This quote is locked because it was converted to an order.** Accettati: **This quote is locked because the customer accepted it. Click Unlock to make changes.** Sblocco: **Quote unlocked for editing.** Blocco di nuovo: **Quote locked again.**

| Campo | Cosa fa (dalle descrizioni dei campi) |
|---|---|
| **Status** | Fase attuale nel flusso di vendita. Draft: solo interno. Pending review: richiesta del cliente, in attesa del Suo prezzo. Sent: inviato via e-mail al cliente. Accepted: il cliente ha accettato. Converted: è diventato un ordine. Solo Sent e Negotiation possono essere accettati dal cliente. Cambi lo stato manualmente quando serve. |
| **Validity period** | Per quanto tempo il cliente ha per accettare, contato dal salvataggio/invio. Esempi: 15 con Minutes, 1 con Hours, 30 con Days. Il salvataggio ricalcola la scadenza da ora. Il cliente non può accettare dopo la scadenza. Periodi brevi possono scadere prima che il cron giornaliero invii i promemoria. |
| **Validity unit** | Minuti, ore o giorni con il numero di validità. |
| **Payment hint** | Nota breve sul pagamento previsto, ad es. "30 days net transfer". Mostrata nella vista cliente e nel PDF. Non obbliga un modulo di pagamento. |
| **Global discount %** | Sconto extra 0–100 su tutte le righe prodotto prima della spedizione. Al checkout può applicarsi come regola carrello. |
| **Global discount amount (tax excl.)** | Sconto fisso sul subtotale prodotti. La percentuale si applica per prima quando entrambi sono impostati. |
| **Shipping label** | Nome sul PDF, ad es. "Express delivery". |
| **Shipping (tax excl.)** / **Shipping (tax incl.)** | Costo di consegna. Tax incl. si calcola automaticamente da excl. quando una regola fiscale è impostata nelle impostazioni del modulo. Incluso nel totale e passato al checkout come spedizione fissa. |
| **Messages from customer** | Tutto ciò che il cliente ha scritto (richiesta, richiesta di modifica, rifiuto). Solo lettura. Risponda nei campi sotto. |
| **General message to customer** | Messaggio permanente sempre visibile al cliente (ambito, tempi, condizioni). Mostrato nella vista preventivo, PDF ed e-mail. |
| **Internal note** | Nota privata del team. Mai mostrata al cliente. |
| **Line items** | Righe prodotto e righe di servizio personalizzate. Aggiunga un prodotto di catalogo (scelga la combinazione quando richiesta). Aggiunga una riga personalizzata: descrizione, qty, prezzo unitario tax excl., tax %. Le righe personalizzate compaiono sul PDF e al checkout vanno nel prodotto fee. Messaggi: **Product line added.**, **Custom line added.**, **Line removed.**, **Select a product to add.**, **Please select a product combination.**, **Enter a service line description.** |
| **Comment for this send** | Nota una tantum solo per questo **Save & send**. Spiega cosa è cambiato. Cancellata dopo l'invio. Compare nella timeline, nella cronologia PDF opzionale e nell'e-mail di quell'invio. |
| **Version history** | Istantanee delle versioni precedenti. |
| **Save as template** | Inserisca un nome modello e salvi. In seguito crei nuovi preventivi da quel modello per un altro cliente. Messaggi: **Please enter a template name.**, **Template "…" saved.** |
| **Quote timeline** | Cronologia degli eventi di staff e cliente su questo preventivo. |

Duplicazione dall'elenco o dall'editor: **Unable to duplicate quote.** in caso di errore. Dopo la duplicazione modifichi la copia.

### 3.6 Audit log

Scheda del modulo: attività recente (richieste, invii, accettazione/rifiuto, negoziazioni). Usi **View** per il contesto completo. Apra **Orders**, **Audit log** per filtri, esportazione e cronologia completa.

Scopo: traccia append-only per conformità e risoluzione problemi. Le voci non possono essere modificate né eliminate. Ogni riga memorizza nome e ID dell'attore (impiegato o cliente) al momento dell'azione. Badge attore: Employee, Customer, System.

### 3.7 Settings — Theme & display

Apra **Settings**. Faccia clic su **Save** in basso dopo le modifiche.

![Theme and display](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-theme.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Front theme template** | **Auto-detect (recommended)** | Seleziona quale set di template e CSS è usato per My quotes, anteprima preventivo e collegamento account cliente. Lasci su Auto-detect salvo che il fork del tema non sia rilevato male — allora forzi Classic o Hummingbird. |
| **Quantity display format** | **Integer (e.g. 1, 2)** | Come le quantità di riga appaiono nel front office, back office, PDF ed e-mail. Oppure **Fixed decimals (e.g. 1.000, 2.500)**. Gli input del modulo usano lo stesso formato per i valori predefiniti. |
| **Quantity decimal places** | 3 | Cifre dopo la virgola quando il formato è fixed decimals. In genere 3 per B2B o 2 per retail. Ignorato in modalità integer. |

### 3.8 Settings — General

![General](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-general.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Module enabled** | **Yes** | Interruttore principale per l'intera funzione quote-to-order. Yes: i clienti richiedono preventivi e lo staff gestisce le offerte. No: nasconde tutti i pulsanti preventivo e i collegamenti account cliente senza disinstallare. Quando disabilitato, nessuna nuova richiesta e nessun pulsante su carrello, prodotto o categorie. I preventivi esistenti restano nel back office. |
| **Product page quote button** | **Yes** | Mostra **Request a quote** su ogni pagina prodotto. Per negozi B2B in cui gli acquirenti chiedono un prezzo su un singolo SKU. Il cliente deve essere connesso (o flusso ospite consentito) e in un gruppo consentito. La modalità Instant apre il modulo per quel prodotto. La modalità List aggiunge quantità e combinazione all'elenco preventivo flottante. |
| **Cart quote button** | **Yes** | Mostra **Request a quote** sul carrello. Attivi quando i clienti richiedono offerte per più prodotti insieme. Rispetta il totale minimo carrello sotto. Il contenuto attuale del carrello diventa la base di una nuova richiesta preventivo dopo la conferma. |
| **Category / list quote button** | **Yes** | **Request quote** compatto sulle pagine elenco (categoria, ricerca, novità). Stesse regole di idoneità. Instant apre il flusso preventivo prodotto. List aggiunge il prodotto (combinazione predefinita, qty 1) all'elenco flottante. |
| **Product quote mode** | **Instant — open form for this product** | Instant: apre il modulo per il prodotto corrente. List: aggiunge a un cestino preventivo; il pulsante flottante apre un modulo con tutti i prodotti. Le richieste dal carrello restano indipendenti. Il pulsante flottante appare solo in modalità List quando l'elenco non è vuoto. |
| **Floating quote button position** | **Bottom right** | Oppure **Bottom left**. Solo quando product quote mode è List. Il badge mostra il conteggio prodotti; apre il modulo di richiesta multiprodotto. |
| **Allow guests** | **No** | Se i visitatori senza account possono avviare una richiesta. Lasci disattivato per B2B rigoroso. Attivi se gli ospiti devono vedere il pulsante — viene comunque chiesto di accedere o registrarsi prima che la richiesta sia salvata. Non crea preventivi anonimi. |

### 3.9 Settings — Quote button visibility

![Visibility](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-visibility.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Customer groups | all groups | Limita chi può vedere i pulsanti preventivo. Tutti i gruppi, o solo gruppi selezionati (ad es. Wholesale). I clienti fuori dai gruppi selezionati non vedranno i pulsanti anche con il modulo abilitato. |
| **Enable catalog visibility rules** | **No** | Attiva o disattiva le regole di pulsante preventivo basate sul catalogo. Attivi per limitare i preventivi a prodotti, categorie, marche o fornitori specifici. Quando disabilitato, ogni prodotto può essere quotato (le regole di gruppo restano). Quando abilitato, vengono applicati whitelist/blacklist e i filtri sotto. |
| **Catalog rule mode** | **Whitelist — only matching products** | Whitelist: pulsanti solo sui prodotti corrispondenti. Blacklist: nasconde i pulsanti sui prodotti corrispondenti. Un prodotto corrisponde se è nell'elenco prodotti o appartiene a una categoria, produttore o fornitore selezionato. |
| Catalog pickers | empty | Categorie (albero), prodotti (ricerca), produttori e fornitori. Lasci vuoti per applicare solo i filtri ausiliari. Le regole si combinano con OR — una corrispondenza basta. |
| **Minimum product price** | 0 | Nasconde i pulsanti preventivo sotto questo prezzo storefront tasse incluse. 0 disabilita. Applicato quando le regole catalogo sono abilitate. |
| **Exclude virtual products** | **No** | Impedisce di quotare prodotti scaricabili / virtuali quando le regole catalogo sono abilitate. |
| **Exclude out-of-stock products** | **No** | Nasconde i pulsanti quando il prodotto non può essere ordinato fuori stock (rispetta il comportamento PrestaShop fuori stock). |
| **Mixed cart (eligible + excluded items)** | **Hide cart quote button** | Quando il carrello mescola prodotti quotabili e non quotabili: Show = pulsante visibile, solo le righe idonee importate; Hide = pulsante nascosto finché il carrello non è solo quotabile. Tutti idonei → mostra sempre. Tutti esclusi → nasconde sempre. |

### 3.10 Settings — Product quote request form

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Require privacy policy acceptance** | **Yes** | Casella privacy obbligatoria sulla modale di richiesta preventivo prodotto (GDPR). I clienti devono accettare prima dell'invio. |
| **Privacy policy CMS page** | none | Pagina CMS collegata dalla casella. Se vuota, il testo della casella non ha collegamento. |
| **Enable reCAPTCHA** | **No** | Protegge il modulo di richiesta preventivo prodotto con Google reCAPTCHA v2. Quando abilitato, le chiavi site e secret sotto sono obbligatorie. |
| **reCAPTCHA site key** | empty | Chiave site pubblica dall'admin Google reCAPTCHA (v2 checkbox). |
| **reCAPTCHA secret key** | empty | Chiave secret. Memorizzata nella configurazione del negozio. |
| **Minimum cart total** | 0 | Valore minimo del carrello prima che il pulsante preventivo carrello sia mostrato. Valuta predefinita del negozio. 0 = nessun minimo. Influisce solo sul pulsante carrello, non sulle richieste prodotto singolo. Carrelli piccoli non mostreranno il pulsante. |

### 3.11 Settings — Offers & references

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Default validity** | 30 | Durata predefinita di validità di un preventivo dopo la creazione. Numero più unità: minuti per offerte flash, ore per decisioni in giornata, giorni per B2B standard. Imposta valid_until sui nuovi preventivi da storefront, back office e duplicati. Sovrascrivibile per preventivo nell'editor. |
| **Default validity unit** | **Days** | Minuti, ore o giorni con il numero sopra. Le e-mail di promemoria e lo stato Expired automatico si basano comunque sul cron per i promemoria. |
| **Expiry reminder (days before)** | 3 | E-mail di promemoria prima della scadenza. Inviata solo dal job cron giornaliero. Ogni preventivo idoneo riceve al massimo un promemoria con collegamento per visualizzare e accettare. Senza cron, nessun promemoria. |
| Cron URL | generated token | Promemoria di scadenza automatici e aggiornamenti di stato. Aggiunga l'URL al crontab una volta al giorno (esempio 08:00). Rigeneri il token se esposto. La scadenza è applicata anche quando qualcuno apre il preventivo; le e-mail di promemoria richiedono comunque il cron. |
| **Reference prefix** | Q | Prefisso per i numeri preventivo. Il modulo aggiunge anno e sequenza, ad es. Q-2026-00042. Aiuta staff e clienti a riconoscere i documenti in e-mail e PDF. |
| **Notify staff on new request** | **Yes** | E-mail allo staff del negozio quando un cliente invia una richiesta. Verifichi che Preferences > Contact e-mail sia corretta. Template: qe-request-staff nella scheda Emails. |

Avviso giallo a schermo: il cron è richiesto per l'automazione della validità; la scadenza si applica anche all'apertura; i promemoria usano l'URL cron.

### 3.12 Settings — Checkout

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Shipping / service tax rule** | shop default tax rule | Regola IVA per spedizione e righe di servizio personalizzate quando inserisce importi tax-exclusive. Scelga un gruppo regole fiscali da Catalog → Products. Quando selezionato, salvando un preventivo si ricalcola la spedizione tax-incl da tax-excl. |
| **Fee product (custom lines)** | created on install | Prodotto virtuale nascosto che porta le righe di servizio personalizzate nel checkout. Creato automaticamente — lo cambi solo se deve puntare le righe personalizzate a un prodotto diverso. Al checkout, i totali servizio diventano una riga carrello con il prezzo preventivo bloccato. |

### 3.13 PDF

Apra la scheda **PDF**. Legenda: **PDF documents**. Quando il PDF è disabilitato, i pulsanti di download sono nascosti e gli URL PDF restituiscono not found.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Enable PDF** | **Yes** | Interruttore principale per generazione PDF e collegamenti di download. Disabiliti se non vuole proforma PDF. Quando off, i pulsanti PDF sono nascosti in back office, storefront e dettaglio ordine; gli URL PDF diretti restituiscono not found. I template e-mail ricevono comunque un placeholder URL PDF vuoto. |
| **Use shop logo on PDF** | **Yes** | Usa il logo del negozio da Preferences > Themes. No: usa solo un logo personalizzato caricato sotto (se presente). Il logo appare in alto sui documenti PDF / proforma. |
| **Add negotiation history to PDF** | **No** | Aggiunge un breve log di comunicazione (richieste di modifica, reinvii, accettazione, rifiuto). Tabella compatta prima delle condizioni. Vuota quando non c'è attività di negoziazione. |
| **Custom PDF logo** | empty | PNG o JPG opzionale solo per i PDF preventivo. Sovrascrive il logo del negozio quando presente. |
| **PDF terms & conditions** | empty | Condizioni legali o commerciali in fondo a ogni PDF. |
| **Authorized signature** | empty | Nome o riga firmatario, ad es. "John Smith, Sales Director". Lasci vuoto per omettere. |

### 3.14 Emails

Apra la scheda **Emails**. E-mail transazionali per il ciclo di vita del preventivo. Modifichi oggetto e corpo per lingua. Usi i placeholder dalla barra laterale dell'editor (nome cliente, riferimento preventivo, collegamento, totali). Chiavi integrate: qe-request-staff, qe-quote-sent, qe-quote-accepted, qe-quote-rejected, qe-quote-negotiation, qe-quote-reminder, qe-staff-digest. Clienti e staff le ricevono quando un preventivo è richiesto, inviato, accettato o in scadenza. Esegua un test dopo le modifiche.

### 3.15 API

Apra la scheda **API**. Colleghi CRM, ERP o automazione. Inserisca un'etichetta chiave e **Generate new API key**. Copi la chiave. **Revoke** la disabilita (conferma). Vuoto: **No API keys yet.** **API documentation** descrive le azioni: list, get, pending, stats, update_status. Chiami l'URL API del modulo con la chiave.

### 3.16 Notifications

Apra **Notifications** (**Staff digest notifications**). Riepilogo periodico quando i preventivi richiedono azione, senza un'e-mail per evento.

Cosa conta come in attesa: **Pending review** (nuova richiesta) o **Negotiation** (il cliente ha chiesto modifiche). Sent, accepted, expired e converted non sono inclusi. Il cron gira secondo la Sua pianificazione. Quando il digest è abilitato, almeno un preventivo è in attesa e l'intervallo è trascorso, un messaggio va a ogni canale configurato. Lo staff vede un riepilogo con riferimenti, stato, nome cliente e collegamenti back office (fino a 20 preventivi elencati).

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Enable digest** | **No** | Interruttore principale. Abiliti dopo aver impostato almeno un canale. Il cron deve essere pianificato — i digest non sono inviati dalle visite di pagina. Quando off, il cron gestisce comunque promemoria di scadenza e aggiornamenti di stato, ma nessun digest. |
| **Interval (hours)** | 24 | Tempo minimo tra i digest (1–168). Esegua il cron almeno con questa frequenza. Dopo un digest riuscito, il successivo attende che passino queste ore. |
| **E-mail recipients** | empty | Separati da virgola o punto e virgola. Vuoto usa l'e-mail del negozio da Preferences > Contact. Template qe-staff-digest. |
| **Slack webhook URL** | empty | URL webhook in ingresso. Lasci vuoto per saltare Slack. |
| **Teams webhook URL** | empty | URL webhook connector. Lasci vuoto per saltare Teams. |

**Save** memorizza le impostazioni. **Send test digest now** invia un test quando ci sono preventivi in attesa. Stesso URL cron di Settings.

### 3.17 Updates

Apra **Updates**. **Check Now** verifica se c'è una nuova versione. **Automatic Notifications** abilitato o disabilitato. **Save** memorizza le impostazioni di aggiornamento.

### 3.18 Blocco preventivo su un ordine

Su un ordine creato da un preventivo, il back office mostra **Source quote** con un collegamento al preventivo e facoltativamente **View quote PDF**.

## 4. Front office

I clienti vedono gli strumenti preventivo quando il modulo è abilitato e il loro gruppo è consentito.

**Product page.** **Request a quote** apre il modulo (instant) o aggiunge all'elenco preventivo (list mode). Casella privacy e reCAPTCHA si applicano quando abilitati.

**Product list.** **Request quote** — stesse regole.

**Cart.** **Request a quote** — rispetta il totale minimo carrello e le regole mixed-cart. Il carrello confermato diventa un preventivo pending.

**List mode.** Pulsante flottante con conteggio apre il modulo di richiesta multiprodotto.

**Customer account.** Collegamento a **My quotes**: cronologia, stato, valid until, **View**, PDF quando abilitato, **Checkout** dopo l'accettazione, **Request re-opening** quando scaduto/bloccato. Vuoto: **You have no quotes yet. Request a quote from a product page or your cart to get started.** Dopo l'invio: **Your quote request has been submitted. Our team will prepare an offer shortly.**

**Quote view.** Accetta, rifiuta, richiedi modifiche, scarica PDF, checkout quando accettato. Scaduto bloccato: **Locked — validity expired**.

I visitatori ospiti possono vedere i pulsanti se **Allow guests** è **Yes**, ma la richiesta viene salvata solo per un cliente connesso.

Non c'è uno screenshot storefront in questo pacchetto perché il negozio di test non era raggiungibile quando le schermate sono state completate.

## 5. Problemi comuni

**Nessun pulsante preventivo su prodotto o carrello.** Controlli **Module enabled**, l'interruttore del pulsante corrispondente, il gruppo cliente e la visibilità catalogo. Per il carrello, controlli **Minimum cart total** e **Mixed cart**.

**L'ospite non può completare una richiesta.** L'invio richiede sempre un account.

**Il preventivo è bloccato / non si può modificare.** Sblocchi se accepted o expired (estenda la validità). I preventivi converted restano bloccati all'ordine.

**Il cliente non può accettare.** Lo stato deve essere Sent o Negotiation e valid until deve essere nel futuro.

**Le e-mail di promemoria non arrivano mai.** Pianifichi l'URL cron e tenga **Expiry reminder** sopra zero. Aprire un preventivo può farlo scadere senza cron; i promemoria richiedono comunque il cron.

**Pulsanti PDF mancanti.** Attivi **Enable PDF**.

**reCAPTCHA blocca il modulo.** Lo disattivi, oppure inserisca entrambe le chiavi.

**Il digest staff non arriva mai.** Abiliti il digest, imposti un canale, esegua il cron almeno con la frequenza dell'intervallo.

**Disinstallato e il menu è sparito.** Reinstalli. La disinstallazione elimina le tabelle preventivo. Il prodotto fee può restare nel catalogo.

## 6. Guida per sviluppatori

### 6.1 Panoramica

Nome tecnico `quoteenterprise`, versione 1.7.6, classe `quoteenterprise` extends `Module`. Nome visualizzato tramite `$this->l('Quote Enterprise')`. Autore MyPresta.eu. Tab `checkout`. URL prodotto in `$this->mypresta_link`.

Flusso: richiesta → riga `quote` → modifica/invio staff → accettazione/negoziazione cliente → checkout → ordine. I testi campo per i rivenditori sono in `QuoteSettingDescTrait` e nei metodi `desc*` dell'editor preventivo.

### 6.2 File

- `quoteenterprise.php` — install, hooks, entry di configurazione, URL cron.
- `classes/QuoteAdmin.php` — schede di configurazione e moduli impostazioni.
- `classes/QuoteAdminQuoteForm.php` — editor preventivo.
- `classes/QuoteQuotesManager.php` — panoramica, save/send/lines/templates.
- `classes/QuoteDashboard.php`, `QuoteVisibility.php`, `QuoteListHelper.php`, `QuoteRequestHelper.php`, `QuoteMailer.php`, `QuotePdf.php`, `QuoteApi.php`, `QuoteNotifyDigest.php`, `QuoteExpiry.php`, `QuoteConverter.php`, `QuoteFeeProduct.php`, `QuoteSettingDescTrait.php`.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`, `AdminQuoteEnterpriseAuditLog.php`.
- `controllers/front/` — `list`, `view`, `request`, `quoteList`, `pdf`, `cron`, `api`.
- `models/` — `quote`, `quotedetail`, `quoteauditlog`, `quoterevision`, `quoteapikey`.
- `views/templates/`, `lib/updateChecker.php`, `lib/emailTemplatesManager/`, `lib/searchTool/`.

### 6.3 Controller

Admin sotto **Orders** (`AdminParentOrders`). Controller front in `$this->controllers`. Il cron richiede `QE_CRON_TOKEN`. L'API richiede una chiave attiva e un nome azione.

### 6.4 Hook

Registrati: `displayHeader`, `displayShoppingCart`, `displayCustomerAccount`, `displayProductAdditionalInfo`, `displayProductActions`, `displayFooterProduct`, `displayFooter`, `actionProductPriceCalculation`, `actionValidateOrder`, `actionAdminControllerSetMedia`, `displayProductListFunctionalButtons`, `displayProductListReviews`, `displayProductPriceBlock`, `displayAdminOrderMain`, `displayAdminOrderSide`, `displayAdminOrder`, `actionCartGetPackageShippingCost`. Nessun hook personalizzato esposto.

### 6.5 Override

Questo modulo non fornisce override di classi o controller.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `quote` | Intestazione preventivo. |
| `quote_detail` | Righe. |
| `quote_revision` | Istantanee di versione. |
| `quote_audit_log` | Attività append-only. |
| `quote_api_key` | Chiavi API. |
| `qe_cart_quote` | Collegamento carrello–preventivo. |

La disinstallazione elimina queste tabelle. `QuoteSchema::ensure` e `inconsistency()` riparano pezzi mancanti quando si apre la configurazione.

### 6.7 Chiavi e traduzioni

Chiavi di configurazione `QE_*`. Valori predefiniti in `installDefaults()`. Nuova lingua: `translations/{iso}.php`. Aiuto campi rivenditore: `QuoteSettingDescTrait` e metodi `desc*` dell'editor. Stringhe tramite `$this->l()` e `{l s=... mod='quoteenterprise'}`.

### 6.8 Estensione

Sovrascriva i template front sotto `modules/quoteenterprise/` nel tema. Classic e Hummingbird sono supportati. Un layout PDF diverso richiede di modificare il template PDF o il codice del modulo.

## 7. Supporto

Pagina del modulo: [Quote Enterprise](https://mypresta.eu/modules/ordering-process/quote-enterprise.html).

Per scrivere di questo modulo, acceda al Suo account cliente su [mypresta.eu](https://mypresta.eu/), apra [Contact](https://mypresta.eu/contact.html) e scelga l'oggetto **Support for paid modules**. Il modulo indica che il login è obbligatorio. Dopo l'accesso, scelga questo modulo dalla cronologia degli acquisti.
