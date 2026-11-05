---
title: "Microsoft Advertising UET Tag & Conversions API - documentazione e manuale utente"
description: "Configuri il monitoraggio, verifichi gli eventi con la diagnostica in tempo reale e risolva i problemi dopo l’installazione del modulo."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Microsoft Advertising UET Tag & Conversions API su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


## 1. Requisiti

Preparare il negozio, l'account Microsoft Advertising e l'attività pianificata prima della configurazione.

- Utilizzi PrestaShop 1.7, 8 o 9.
- Utilizzi PHP 7.1–8.x, a seconda della versione PHP richiesta dalla sua installazione PrestaShop.
- Abiliti le estensioni PHP cURL, JSON, OpenSSL e hash.
- Avere un account Microsoft Advertising e un ID tag UET. Ottieni anche un token bearer API Conversions per **Conversions API** o **UET + CAPI**.
- Avere accesso a CRON quando si utilizzi CAPI, poiché la sua coda deve essere eseguita regolarmente.
- Configurare un CMP esterno o un modulo cookie prima di trasformare **Require marketing / analytics consent** in **Yes**.
- Non è richiesto nessun altro modulo PrestaShop. Un modulo feed di Microsoft Merchant Center è facoltativo e può aiutare ad allineare gli ID catalogo.

## 2. Installazione

1. Apra **Modules > Module Manager**.
2. Fare clic su **Upload a module** e caricare il file ZIP.
3. Installare **Microsoft Advertising UET / Conversions API**.
4. Lo trovi in **Module Manager** e faccia clic su **Configure**.
5. Completa **Setup Wizard** o configuri manualmente tutte le schede.

Il modulo non crea una voce di menu **Catalog** visibile. Il suo endpoint dati è una scheda nascosta di back-office utilizzata internamente.

L'installazione non cancella la cache di PrestaShop. Cancellalo in **Advanced Parameters > Performance** solo se le vecchie risorse o una vecchia schermata di configurazione rimangono visibili.

La disinstallazione rimuove il registro eventi del modulo, le regole multi-tag, la coda CAPI, l'endpoint nascosto e le chiavi di configurazione del modulo. Le chiavi di controllo degli aggiornamenti potrebbero rimanere. La reinstallazione inizia con le impostazioni predefinite e non ripristina gli eventi o le regole eliminati.

## 3. Configurazione e lavoro di back-office

Apra **Modules > Module Manager**, trova **Microsoft Advertising UET / Conversions API** e faccia clic su **Configure**.

Segua questo processo:

1. Completa **Setup Wizard**.
2. Confermare il canale e le credenziali in **Tracking mode**.
3. Selezionare i segnali in **Events**.
4. Abbina gli ID prodotto evento al suo feed in **Catalog IDs**.
5. Configurare **Privacy & consent**.
6. Definire il comportamento di pagamento e rimborso in **Order lifecycle**.
7. Aggiunga **Multi-tag rules** solo per credenziali specifiche del contesto.
8. Pianificare l'URL CRON visualizzato ogni 1–5 minuti quando CAPI è attivo.
9. Esplora la vetrina e verifica gli eventi in **Live Statistics** e **Health & diagnostics**.
10. Confermi gli eventi in Microsoft Advertising.

Le schermate presenti in questo manuale provengono da un back office inglese.

### 3.1 Configurazione guidata

Utilizzare la procedura guidata per la prima configurazione. La guida attraverso **Mode**, **Tag ID**, **CAPI token**, **Test** e **Done**.

![Setup Wizard](https://mypresta.eu/docs/images/docs/mybing-wizard.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Mode** | Non selezionato | Scelga **UET Tag** per il monitoraggio del browser, **Conversions API** per il monitoraggio del server o **UET + CAPI** per entrambi. La modalità doppia utilizzi un identificatore di evento condiviso per la deduplicazione. |
| **Tag ID** | Vuoto | Incolli l'ID di Microsoft Advertising in Tag UET o Monitoraggio conversioni. È richiesto in ogni modalità. |
| **CAPI token** | Vuoto | In modalità CAPI o doppia, incolli il token al portatore dalla sezione API Conversioni del tag UET. Trattalo come una password. |
| **Enable Ghost Collector (msclkid / anonymousId sync)** | Sì | Raccogli gli identificatori di clic e visitatori anonimi di Microsoft in modalità compatibili con CAPI senza effettuare chiamate di tracciamento UET. Mantienilo abilitato per una corrispondenza più forte e una continuità della sessione. |
| **Test** | Non correre | In modalità UET, convalida l'ID tag e quindi verifica la visualizzazione di una pagina della vetrina. Nelle modalità compatibili con CAPI, faccia clic su **Send test purchase** per inviare un acquisto di provi da € 1. Concedi 10-30 minuti affinché Microsoft Advertising lo mostri. |
| **Done** | Incompleto | Completa la configurazione e apra i collegamenti a **Tracking mode**, **Health & Data Quality Coach** o **Live Statistics**. |

Utilizzare **Start over** per eseguire nuovamente la procedura guidata. Le credenziali esistenti rimangono precompilate finché non vengono modificate.

### 3.2 Modalità di tracciamento e credenziali

Selezioni il modo in cui tutti gli eventi raggiungono Microsoft Advertising, completa i campi visualizzati per tale modalità e faccia clic su **Save**.

![Tracking mode and credentials](https://mypresta.eu/docs/images/docs/mybing-tracking-mode.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Tracking mode** | Non selezionato | **UET Tag** invia dal browser. **Conversions API** mette in coda gli eventi del server. **UET + CAPI** invia entrambi con lo stesso ID evento in modo che Microsoft possa deduplicarli. |
| **Tag ID(s)** | Vuoto | Digitare un ID tag UET e premere virgola o Invio. L'ID è richiesto per UET, CAPI e modalità doppia. |
| **Conversions API token** | Vuoto | Incolli il token al portatore da **Microsoft Advertising > UET tag > Use Conversions API > Copy Token**. |
| **CAPI endpoint override (advanced)** | Vuoto | Lasci vuoto per utilizzare la destinazione standard di Microsoft. Impostalo solo quando Microsoft documenta un host personalizzato per il suo account. |
| **Ghost collector (CAPI)** | Sì | Cattura `msclkid` e l'ID visitatore anonimo per la corrispondenza CAPI. Non chiama il monitoraggio UET. |
| **Bing ID Sync (remarketing)** | Sì | Quando UET è attivo, invia l'ID visitatore anonimo tramite Bing ID Sync per migliorare la corrispondenza del pubblico di remarketing. |

Per la modalità CAPI o doppia, copiare il **CRON URL** visualizzato nello scheduler ed eseguirlo ogni 1-5 minuti.

### 3.3 Eventi

Selezioni e salva prima una modalità di tracciamento. Quindi abiliti solo i segnali che Le servono e faccia clic su **Save**.

![Tracked events](https://mypresta.eu/docs/images/docs/mybing-events.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **PAGE_VIEW** | Sì | Registra ogni caricamento della pagina del negozio. Supporta il reporting e l'attribuzione del traffico; disattivarlo non interrompe gli altri eventi. |
| **view_item (+ select_item)** | Sì | Invia `view_item` nelle pagine dei prodotti e `select_item` quando si fa clic su un prodotto nella categoria, nella ricerca o negli elenchi dei bestseller. |
| **view_item_list** | Sì | Invia circa i primi 20 prodotti da elenchi di categorie, ricerche ed elenchi in stile bestseller con ID, nomi, prezzi e posizioni. Ha il suo interruttore. |
| **add_to_cart** | Sì | Registra le aggiunte al carrello. UET e la modalità doppia utilizzano l'evento carrello nativo più il fallback CSS opzionale. La modalità solo CAPI utilizzi il percorso del server e non necessita di selettori CSS. |
| **REMOVE_FROM_CART (Microsoft: Other)** | Sì | Registra le rimozioni del carrello come **Other**, perché Microsoft non dispone di un tipo di rimozione dal carrello nativo. |
| **CHECKOUT** | Sì | Si attiva quando il cliente entra nel carrello o nel flusso dell'ordine e contrassegna l'intenzione di acquisto. |
| **CHECKOUT details** | Sì | Aggiunga valore, valuta e dati di prodotto a **CHECKOUT**. Disattivandolo si inviano parametri minimi. |
| **ADD_PAYMENT_INFO (Microsoft: Other)** | Sì | Attiva la fase di pagamento come **Other**. Usalo come segnale opzionale di fine canalizzazione per le statistiche in tempo reale. |
| **purchase** | Sì | Invia **OffMicrosoftPurchases** con valore dell'ordine, valuta e linee di prodotti. Un ID di deduplicazione client stabile rende gli aggiornamenti sicuri. Utilizzi **Order lifecycle** per ritardarlo fino al pagamento. |
| **SEARCH** | Sì | Registra le ricerche della vetrina con il termine di ricerca. |
| **ADD_TO_WISHLIST (Microsoft: Other)** | Sì | Registra le aggiunte alla lista dei desideri come **Other** quando il tema espone controlli compatibili. |
| **SIGN_UP (Signup)** | Sì | Invia **Signup** quando viene creato un account cliente. |
| **LEAD / SUBSCRIBE (newsletter)** | Sì | Invia **Lead** per le iscrizioni alla newsletter. Disabilitalo se un altro strumento tiene traccia della stessa conversione. |
| **LEAD (legacy product interest)** | No | Conserva il vecchio comportamento del lead di interesse del prodotto. Lascialo fuori a meno che una campagna storica non lo richieda; utilizzandolo con `view_item` è possibile gonfiare i piombi. |
| **CONTACT** | Sì | Si attiva quando viene inviato il modulo di contatto, utilizzando il rilevamento fallback del server e del browser. |
| **REFUND (Microsoft: Other)** | Sì | Si attiva quando un ordine raggiunge uno stato di rimborso o annullamento configurato. Microsoft lo riceve come **Other** per la correzione locale e le statistiche. |
| **Rich product payloads (productId / items)** | Sì | Includi ID prodotto, quantità e prezzi. La disattivazione lasci dati minimi su valore/valuta, tranne nei casi in cui gli eventi di elenco o clic richiedono ID. Continualo per la corrispondenza del catalogo. |
| **Add to cart CSS selector** | `.add-to-cart` | In UET e modalità doppia, identifica il pulsante della pagina del prodotto quando il tema non attiva l'evento del carrello nativo. |
| **Product price CSS selector** | `.current-price span` | In UET e modalità duale, legga il prezzo di riserva visibile. Un selettore sbagliato invia zero; abbinalo a **Reformat price string** quando necessario. |

Per CAPI, abilitare **Advanced matching (email / phone)** e **Ghost collector (CAPI)** per una migliore corrispondenza.

### 3.4 ID catalogo e Dottore ID catalogo

Assicurati che gli ID prodotto evento corrispondano esattamente al feed di Microsoft Merchant Center, faccia clic su **Save**, quindi esamina **Catalog ID Doctor**.

![Catalog IDs and Catalog ID Doctor](https://mypresta.eu/docs/images/docs/mybing-catalog.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Product identification** | `id_product` | Scelga l'ID prodotto, l'ID combinazione o l'ID prodotto più separatore più ID combinazione. Gli ID combinati si adattano ai feed che elencano le varianti. Un formato di feed diverso impedisce la corrispondenza. |
| **Separator** | `-` | Separare gli ID prodotto e combinazione in modalità combinata. Il prodotto 12 e la combinazione 5 diventano `12-5`. Utilizzi lo stesso separatore nel feed. |
| **Product ID prefix** | Vuoto per lingua | Aggiunga un valore specifico per la lingua prima di ogni ID solo quando lo utilizzi anche il feed. |
| **Product ID suffix** | Vuoto per lingua | Aggiunga un valore specifico per la lingua dopo ogni ID solo quando lo utilizzi anche il feed. |
| **Exclude free products** | No | Ometti i prodotti a prezzo zero dal carrello e acquista linee di prodotti e calcoli del valore. |
| **Force currency conversion** | No | Converti tutti i valori monetari in una valuta di destinazione. Abiliti solo quando la valuta del negozio non è accettata da Microsoft Advertising. |
| **Target currency** | Selezione dipendente dal negozio | Selezioni la valuta di destinazione. Viene ignorato mentre la conversione forzata è disattivata. |
| **Reformat price string** | No | In modalità UET o doppia, pulisci i prezzi dei temi formattati prima che vengano letti dal fallback di aggiunta al carrello CSS. Non viene utilizzato in modalità solo CAPI. |

**Catalog ID Doctor** mostra esempi generati da un prodotto e una combinazione attivi, gli ID recenti trovati nei dati dell'evento e suggerimenti sull'ID base selezionato, separatore, prefisso e suffisso. Se riporta **No active products found to validate catalog productId values**, attiva un prodotto e riapri la scheda.

### 3.5 Privacy e consenso

Configuri prima un'origine del consenso esterna. Il modulo non visualizza un banner sui cookie.

![Privacy and consent](https://mypresta.eu/docs/images/docs/mybing-privacy.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Require marketing / analytics consent** | No | Blocca UET, CAPI e Ghost finché non viene concesso il consenso. Senza un CMP connesso, il tracciamento rimane silenzioso. |
| **Default consent state** | `auto` | `auto` attende il consenso dei cookie, del TCF o degli eventi del browser; `grant` consente immediatamente; `revoke` blocca finché non viene concesso. Utilizzare `auto` con un banner e `grant` solo con una base legale adeguata. |
| **IAB TCF 2.x (__tcfapi)** | Sì | Ascolta un CMP certificato. Lo scopo 1 più uno degli scopi 2, 3 o 4 sblocca gli annunci e aggiorni il consenso all'archiviazione di pubblicità di Microsoft UET. |
| **Include logged-in customer ID** | No | Aggiunga l'ID cliente PrestaShop al contesto e alla diagnostica di accesso come segnale ID esterno opzionale. Dichiaratelo nella privacy policy. |
| **Advanced matching (email / phone)** | No | Invia e-mail e campi e-mail/telefono con hash disponibili per una migliore attribuzione UET e CAPI. Assicurati che l'informativa sulla privacy copra questo aspetto. È fortemente consigliato per CAPI. |
| **Ignore admin / employee traffic** | Sì | Salta il monitoraggio della vetrina quando viene rilevata una sessione del dipendente. |
| **Simple bot filter** | No | Ignora le richieste il cui identificatore del browser ricorda un bot o un crawler. Questo è euristico. |

Per una configurazione UE, configuri il CMP, utilizzi `auto`, abiliti il consenso richiesto e mantenga il TCF abilitato quando supportato. Provi sia l'accettazione che il rifiuto in un browser privato. La guida riconosce i comuni cookie di marketing/statistici, il proprio cookie di consenso e il relativo risultato TCF. I callback di Cookiebot sono supportati direttamente; altri CMP possono inviare l'evento di consenso del modulo.

### 3.6 Ciclo di vita dell'ordine

Controlli quando le vendite e i rimborsi entrano nei report sulle conversioni.

![Order lifecycle](https://mypresta.eu/docs/images/docs/mybing-orders.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Purchase only when paid** | No | Ritardare l'acquisto fino al pagamento dello stato dell'ordine. Abilitalo quando i bonifici bancari non pagati o gli ordini in contrassegno gonfiano le conversioni. |
| **Paid statuses** | Vuoto | Selezioni una whitelist facoltativa di stati a pagamento. Lasci vuoto per utilizzare il flag a pagamento integrato di PrestaShop. Un elenco compilato viene utilizzato quando è attivo il monitoraggio solo a pagamento. |
| **Refund / cancel statuses** | Vuoto | Selezioni gli stati che attivano il rimborso. Vuoto utilizzi il rilevamento automatico dai nomi di stato contenenti rimborso o annullamento. Anche l'evento Rimborso deve essere abilitato. |

In caso di pagamento ritardato, attiva il monitoraggio solo pagato, sposta un ordine di provi nello stato pagato e verifica che l'acquisto venga visualizzato una volta.

### 3.7 Regole multi-tag

Utilizzi le regole quando un negozio, una lingua, un paese o una valuta necessitano di credenziali diverse. La prima regola attiva corrispondente vince in ordine crescente **Position**. Senza una corrispondenza, vengono utilizzate le credenziali globali.

![Multi-tag rules](https://mypresta.eu/docs/images/docs/mybing-multitag.webp)

L'elenco **Active rules** mostra **Tag ID**, origine token CAPI, **Shop**, **Language**, **Country**, **Currency**, **Active** e **Actions**. Fare clic su **Delete** e confermare per rimuovere una regola. Non sono previste modifiche o azioni collettive; ricreare una regola per modificarla.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Tag ID (UET)** | Vuoto | Imposti il tag UET per il traffico corrispondente. Potrebbe essere vuoto solo per una sostituzione CAPI solo token. |
| **Conversions API token** | Vuoto | Sostituisci il token globale. Vuoto eredita il token da **Tracking mode**. |
| **Shop** | **All shops** | Limita la regola a un negozio multistore o a tutti i negozi. |
| **Language** | **All languages** | Limitalo a una lingua della vetrina o a tutte le lingue. |
| **Country** | **All countries** | Limitalo al contesto attuale del paese cliente. |
| **Currency** | **All currencies** | Limitalo alla valuta corrente. |
| **Active** | Sì | Abiliti o disabiliti la regola. Le regole inattive vengono ignorate. |
| **Position** | `0` | Imposti l'ordine di valutazione. I numeri più bassi vincono quando più regole corrispondono. |

Fare clic su **Add rule**. **Property rule saved** confermi il successo. Se viene visualizzato **Could not save rule — provide a valid Tag ID and/or Conversions API token.**, correggere l'ID tag o fornire un token.

### 3.8 Statistiche in tempo reale

Apra questa scheda in una finestra e sfoglia la vetrina in un'altra. Gli eventi vengono visualizzati sulla sequenza temporale in tempo reale di 30 minuti.

![Live Statistics](https://mypresta.eu/docs/images/docs/mybing-live.webp)

**Recovery Radar** mostra gli acquisti senza aggiunta al carrello, l'aggiunta al carrello senza visualizzazione dei dettagli del prodotto, i rimborsi rispetto agli acquisti e il ripristino CAPI/Ghost. Utilizzi le caselle di controllo degli eventi per filtrare la sequenza temporale; PageView è nascosto per impostazione predefinita. **Pause** interrompe il polling senza interrompere il tracciamento e **Refresh** recupera i dati correnti.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Enable live dashboard** | Sì | Attiva o disattiva il polling della sequenza temporale. La sua disattivazione mette in pausa il feed, mentre il monitoraggio e le registrazioni sanitarie/radar continuano. |
| **Also log PageView into the event database** | No | Aggiunga righe PageView rumorose al registro locale. Non controlli l'attivazione di Microsoft PageView o la registrazione di altri eventi. Abiliti solo per il debug. |
| **Keep events for (days)** | `14` | Elimini le righe più vecchie di questa età. I valori accettati sono 1–365; 7–30 è tipico. |
| **Live poll interval (seconds)** | `5` | Sondaggio ogni 2-60 secondi. I valori più bassi sono più veloci ma creano più richieste di back-office. |

Utilizzare **Purge older than retention**, **Delete failed only** o **Clear entire event log** per una pulizia immediata. La cancellazione di tutto richiede confermi e non può essere annullata. **Export recent events (CSV)** scarichi i record recenti non PageView.

### 3.9 Salute e diagnostica

Utilizzi questa scheda dopo la configurazione e ogni volta che mancano conversioni.

![Health and diagnostics](https://mypresta.eu/docs/images/docs/mybing-health.webp)

**Health Score** modalità di controllo, credenziali, aggiornamento della coda, Ghost, PageView, consenso, TCF, acquisto, deduplicazione, errori recenti, formato del catalogo e qualità dei dati. Legga ogni controllo fallito, non solo l'etichetta **Excellent**, **Good**, **Fair** o **Needs work**.

Per CAPI, programmare **CAPI CRON URL** ogni 1-5 minuti. Esamina **Last CAPI flush**, elaborati, inviati, in sospeso, non riusciti, totali della coda e righe più vecchie di 10 minuti.

**Data Quality Coach** stima la copertura corrispondente dai payload recenti del server o da un campione di acquisto corrente. Elenca gli identificatori presenti e mancanti, gli incrementi attesi, le medie per evento e le correzioni a livello di negozio. Migliora l'ID anonimo, `msclkid`, la corrispondenza avanzata di email/telefono e l'ID cliente opzionale, ove appropriato. Confermi la diagnostica finale in Microsoft Advertising.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Enable front debug inspector** | No | Mostra una sovrapposizione di vetrina mobile con eventi, payload, destinazione CAPI, stato della coda ed errori. Spegnerlo dopo il test. Aggiunga temporaneamente `?mybing_debug=1` all'URL di un negozio per abilitarlo senza salvare. |

Sotto **Test & queue**:

- **Send test purchase** invia una conversione di provi; controlli Microsoft Advertising dopo 10-30 minuti.
- **Test CAPI token** controlli che siano presenti Tag ID e token.
- **Process CAPI queue** esegue lo stesso percorso della coda di CRON.

**Recent events log** mostra evento, ID, canale, stato, risposta/errore, data e risultato. Utilizzare **Re-send** per un tentativo immediato o **Re-add to queue** per la successiva esecuzione CRON.

**Recent queue rows** mostra i dettagli dell'evento, lo stato, i tentativi, l'ultimo errore e l'ora dell'aggiornamento. Utilizzi azioni per riga o **Re-send all failed now** e **Re-add all failed to queue**.

### 3.10 Aggiornamenti

Verifica la presenza di una versione più recente del modulo qui.

![Updates](https://mypresta.eu/docs/images/docs/mybing-updates.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Manual Check** | Nessun risultato | Fare clic su **Check Now** per contattare una volta il servizio di aggiornamento. Mostra **Module is up to date!** o **New version available!**. |
| **Automatic Notifications** | Preferenza di aggiornamento condiviso esistente | **Enabled** controlli circa ogni tre giorni e può avvisare i dipendenti. **Disabled** lasci il manuale di gestione degli aggiornamenti. |
| **Product Page** | Collegamento visualizzato | Apra la pagina ufficiale del modulo per informazioni sulla versione, documentazione e accesso al supporto. |

Fare clic su **Save** dopo aver modificato le notifiche.

## 4. Vetrina del negozio

Il modulo non aggiunge alcun blocco visibile della vetrina, modulo, pulsante o pagina dell'account cliente. I clienti utilizzano le normali schermate di prodotto, carrello, pagamento, registrazione, newsletter, contatto e confermi.

Le pagine dei prodotti contengono un blocco di dati di prodotto nascosto utilizzato dal monitoraggio. Non altera il tema visibile. Quando il debug è abilitato, diventa visibile un ispettore mobile; disabilitarlo dopo il test perché espone i dettagli di tracciamento.

Per CAPI, copi **CAPI CRON URL** da **Tracking mode** o **Health & diagnostics** nello scheduler dell'hosting ed eseguilo ogni 1-5 minuti. L'URL protetto elabora gli eventi in coda e la conservazione. Non pubblicarlo perché contiene una chiave di accesso.

L'endpoint dei dati della vetrina viene chiamato automaticamente per il consenso, gli ID dei visitatori, il carrello, la visualizzazione della pagina, il pagamento, il contatto e le azioni di debug. Non costruirlo o aprirlo manualmente.

| Messaggio visibile | Cosa fare |
|---|---|
| L'ispettore debug mostra il consenso negato | Accettare il consenso al marketing tramite la CMP o riparare la connessione CMP. |
| L'ispettore debug mostra in coda | Esegua CRON o **Process CAPI queue**, quindi controlli **Health & diagnostics**. |
| L'ispettore debug mostra un errore | Legga la risposta in **Health & diagnostics**, corregga le credenziali o la connettività e faccia clic su **Re-send**. |

## 5. Problemi

| Sintomo | Causa e azione |
|---|---|
| La procedura guidata rimane incompleta | Salvare una modalità valida, un ID tag e un token quando applicabile; esegua **Test** e finisci **Done**. |
| Non viene visualizzato alcun evento UET | Salva un ID tag valido, includi UET nella modalità, abiliti l'evento, esamina il consenso ed esegua il test in una sessione cliente privata. |
| **Missing Tag ID and/or Conversions API token** | Inseriscili entrambi in **Tracking mode**, salva ed esegua nuovamente **Test CAPI token**. |
| Gli eventi CAPI rimangono in coda | Pianifichi **CAPI CRON URL** ogni 1-5 minuti, faccia clic su **Process CAPI queue** una volta e ispeziona **Last CAPI flush**. |
| Il test CAPI o il nuovo invio falliscono | Leggere **Response / error**, correggere ID tag/token/connettività, lasciare vuoto l'override dell'endpoint a meno che Microsoft non ne abbia fornito uno e riprovare. |
| Il tracciamento si interrompe dopo che è richiesto il consenso | Configuri il CMP esterno, utilizzi `auto`, collega il TCF o i suoi callback, quindi accetta il consenso del marketing ed esegua nuovamente il test. |
| I prodotti del catalogo non corrispondono | Allinea **Product identification**, separatore, prefisso e suffisso con il feed ed esamina **Catalog ID Doctor**. |
| Gli acquisti compaiono prima del pagamento | Abiliti **Purchase only when paid** e facoltativamente selezioni gli stati esatti di pagamento. |
| Gli ordini pagati non creano acquisto | Abiliti **purchase** e assicurati che lo stato dell'ordine sia pagato o incluso in **Paid statuses**. |
| I rimborsi non vengono visualizzati | Abiliti il rimborso e selezioni lo **Refund / cancel statuses** corretto. |
| I suoi test vengono ignorati | Utilizzi un browser privato senza una sessione dipendente o disabiliti temporaneamente **Ignore admin / employee traffic**. |
| Il traffico di provi tipo bot è assente | Disabiliti **Simple bot filter** per il test, quindi ripristinalo secondo necessità. |
| L'aggiunta al carrello UET è assente | Aggiorni i selettori CSS del pulsante e del prezzo in modo che corrispondano al tema. |
| Il valore Aggiunga al carrello è zero o non è valido | Correggere il selettore del prezzo e abilitare **Reformat price string** quando richiesto. |
| Fase di pagamento Altro evento è assente sebbene la sua attivazione/disattivazione sia Sì | Il tema o la fase di pagamento non hanno attivato il percorso del modulo. Considera questo segnale come facoltativo e verifica l'imbuto rimanente. |
| Le statistiche in tempo reale aspettano gli eventi | Abiliti la dashboard, riprendila, cancella i filtri, faccia clic su **Refresh** e esplora la vetrina come cliente. |
| PageView raggiunge Microsoft ma è assente localmente | Abiliti temporaneamente la registrazione locale di PageView; è disattivato per impostazione predefinita. |
| Viene utilizzata la credenziale multitag errata | Elimini/ricrea regole sovrapposte e assegna a quella più specifica la posizione più bassa. |
| Impossibile salvare la regola | Fornire un ID tag e/o un token valido, quindi fare clic su **Add rule**. |
| La salute mette in guardia sulla qualità dei dati | Segua **Highest-impact fixes**, abiliti la corrispondenza Ghost e avanzata ove consentito e raccogli dati telefonici validi per il checkout. |
| Lo schermo del modulo sembra obsoleto | Svuota la cache in **Advanced Parameters > Performance** e ricarica. |

## 6. Riferimento per gli sviluppatori

### 6.1 Architettura

Il nome tecnico è `mybing`, versione `1.4.0`. La classe principale è `mybing extends Module`; il nome dell'elenco è **Microsoft Advertising UET / Conversions API**, autore `MyPresta.eu`, categoria `front_office_features`.

`MybingTrackerFactory` selezioni `MybingUetTracker`, `MybingCapiTracker` o `MybingHybridTracker`. `MybingEvents` crea eventi; `MybingEventId` genera e rende persistenti gli ID di deduplicazione. `MybingProductIdResolver`, `MybingCurrencyHelper` e `MybingUserData` normalizzano i dati di catalogo, denaro e identità. `MybingCapiClient` crea richieste, le invia e gestisce i nuovi tentativi. Diagnostica di alimentazione `MybingLiveStats`, `MybingHealthScore`, `MybingDataQualityCoach` e `MybingCatalogDoctor`.

La modalità doppia condivide un ID evento tra i canali del browser e del server. L'endpoint predefinito è `https://capi.uet.microsoft.com/v1/{tagId}/events`. Ogni chiamata CRON elabora fino a 50 righe di coda e applica la conservazione.

### 6.2 File e classi

| File o classe | Responsabilità |
|---|---|
| `mybing.php` | Installa/disinstalla, impostazioni predefinite, moduli, azioni, CRON, configurazione frontale e hook. |
| `classes/MybingTrackerInterface.php` | Contratto di localizzazione. |
| `classes/MybingTrackerFactory.php` | Risoluzione del cambio di modalità e di evento. |
| `classes/MybingUetTracker.php` | Payload del browser e record UET locali. |
| `classes/MybingCapiTracker.php` | Consegna e accodamento del server. |
| `classes/MybingHybridTracker.php` | Doppia uscita e deduplica. |
| `classes/MybingCapiClient.php` | Payload, cURL, risposte, coda, tentativi e riepiloghi di svuotamento. |
| `classes/MybingEvents.php` | Implementazione di eventi commerciali. |
| `classes/MybingEventMap.php` | Mappa degli eventi interni a Microsoft. |
| `classes/MybingEventId.php` | ID evento, deduplicazione e correzione della tabella degli eventi. |
| `classes/MybingUserData.php` | ID clic/visitatori, dati dei clienti, normalizzazione e hashing. |
| `classes/MybingConsent.php` | Requisito di consenso, impostazioni predefinite, cookie e TCF. |
| `classes/MybingPropertyRules.php` | Schema delle regole di contesto, corrispondenza e risoluzione delle credenziali. |
| `classes/MybingProductIdResolver.php` | Generazione dell'ID del catalogo. |
| `classes/MybingCurrencyHelper.php` | Contesto valutario e conversione. |
| `classes/MybingLiveStats.php` | Feed, riepiloghi, radar, conservazione e pulizia. |
| `classes/MybingHealthScore.php` | Controlli sanitari ponderati e diagnostica delle code. |
| `classes/MybingDataQualityCoach.php` | Stime sulla copertura dell'identità. |
| `classes/MybingCatalogDoctor.php` | ID prodotto campione e recenti. |
| `controllers/admin/AdminMybingAjaxController.php` | Bridge di back-office JSON autenticato. |
| `controllers/front/ajax.php` | Endpoint JSON di tracciamento protetto da token. |
| `controllers/front/cron.php` | Endpoint JSON della coda protetta da chiave. |
| `views/js/mybing.js` | Rilegature anteriori principali e spedizione. |
| `views/js/mybing-tcf.js` | Ponte di consenso TCF. |
| `views/js/mybing-ghost.js` | Sincronizzazione visitatore/ID clic. |
| `views/js/mybing-debug.js` | Ispettore anteriore. |
| `views/js/mybing-admin.js`, `mybing-wizard.js`, `mybing-live.js` | Moduli di back-office, procedura guidata e dashboard live. |
| `views/templates/hook/header.tpl` | UET, consenso, corrispondenza, visualizzazione di pagina, eventi, script e sincronizzazione ID. |
| `views/templates/hook/product-details.tpl` | Prodotto nascosto JSON. |
| `views/templates/hook/displayOrderConfirmation.tpl` | Output di acquisto del browser. |
| `views/templates/hook/capi-pageview.tpl`, `ghost.tpl`, `debug.tpl` | Visualizzazione della pagina CAPI, Ghost e output dell'ispettore. |
| `views/templates/hook/payment.tpl` | Modello di evento di pagamento non richiamato da un gestore di hook nella versione 1.4.0. |
| `sql/install.php`, `sql/uninstall.php` | Crea/corregga e rilascia tabelle personalizzate. |
| `lib/updateChecker.php` | Controlli manuali e periodici di aggiornamento. |

### 6.3 Controller

`AdminMybingAjaxController extends ModuleAdminController` è installato come scheda nascosta `AdminMybingAjax` con il genitore `-1`. Richiede un dipendente ed emette JSON. Azioni: `liveFeed`, `liveRadar`, `liveClear`, `wizardSave`, `wizardTest`, `wizardComplete`, `wizardReset`, `dqReport`/`emqReport` e `exportCsv`.

`MybingAjaxModuleFrontController extends ModuleFrontController` è solo SSL e JSON. Accetta la chiave sicura o il token frontale generato. Azioni: `ghost`, `consent`, `addToCart`, `removeFromCart`, `wishlist`, `selectItem`, `contact`, `beginCheckout`, `recalculate`, `pageview`, `ping` e solo debug `inspect`. Gli errori includono `invalid_token`, `disabled`, `empty_cart`, `invalid_currency`, `disabled_or_consent`, `debug_off` e `unknown_action`.

`MybingCronModuleFrontController` accetta `key` o `secure_key`, restituisce JSON, emette HTTP 403 con `access_denied` per accesso non valido e chiama `runCapiCron()`.

`controllers/front/index.php` invia solo intestazioni senza cache e reindirizza verso l'alto.

### 6.4 Ganci

| Gancio registrato | Attuazione |
|---|---|
| `displayHeader` | Filtra il traffico; invia segnali di pagina, elenco, prodotto, pagamento, ricerca, contatto e newsletter; esegue il rendering dell'output UET/Ghost/CAPI. |
| `displayOrderConfirmation` | Risolve l'ordine, tiene traccia degli acquisti consentiti, esegue il rendering dell'output del browser. |
| `actionValidateOrder` | Tiene traccia dell'acquisto al momento della creazione, a meno che il solo pagamento non lo ritardi. |
| `actionOrderStatusPostUpdate` | Tiene traccia degli acquisti pagati in ritardo e delle transizioni di rimborso/annullamento. |
| `actionCustomerAccountAdd` | Tiene traccia della registrazione e memorizza l'output del browser per la pagina successiva. |
| `actionFrontControllerSetMedia` | Aggiunge la configurazione frontale e le risorse principali, TCF, Ghost e di debug. |
| `displayPaymentTop` | Registrato, ma `hookDisplayPaymentTop()` non è implementato nella versione 1.4.0. |
| `displayFooter` | Rende l'ispettore di debug e il bootstrap della coda quando abilitato. |
| `actionCartUpdateQuantityBefore`, `actionBeforeCartUpdateQty` | Tieni traccia delle modifiche alla quantità del carrello del server; il secondo delega al primo. |
| `actionObjectProductInCartDeleteBefore`, `actionObjectProductInCartDeleteAfter` | Istantanea e traccia dell'eliminazione completa della riga del carrello. |
| `displayProductAdditionalInfo` | Rende i dettagli del prodotto nascosti. |
| `actionNewsletterRegistrationAfter` | Tiene traccia dei lead della newsletter. |
| `displayContactContent` | Aggiunge l'indicatore di contatto nascosto. |

Non esistono metodi `enable()` o `disable()` personalizzati.

### 6.5 Banca dati

L'attuale prefisso PrestaShop sostituisce `ps_`.

| Tabella | Contenuto |
|---|---|
| `ps_mybing_events` | Nome/ID evento, ordine/carrello/negozio, canale, payload, stato, codice HTTP, risposta, data, indici di ricerca e chiave di deduplica evento/nome/negozio univoco. |
| `ps_mybing_properties` | Selettori di tag, token, negozio/lingua/paese/valuta, attivo, posizione e data. |
| `ps_mybing_queue` | Payload, tentativi, stato, ultimo errore, date di creazione/aggiornamento. |

Riprovare l'installazione con `utf8` se `utf8mb4` fallisce. `MybingPropertyRules::ensureSchema()` può aggiungere `tag_id` e `access_token` quando la configurazione viene aperta e migrare un token di aggiornamento legacy. Lo schema dell'evento aggiunge in modo software il proprio indice univoco. La disinstallazione elimini tutte e tre le tabelle.

### 6.6 Chiavi di configurazione

| Chiavi | Impostazioni predefinite e scopo |
|---|---|
| `MYBING_MODE` | Vuoto; modalità localizzatore. |
| `MYBING_TAG_ID`, `MYBING_CAPI_TOKEN`, `MYBING_CAPI_ENDPOINT` | Vuoto; credenziali/destinazione globali. |
| `MYBING_MSCLKID_DAYS`, `MYBING_ID_SYNC` | `90`, `1`; durata dell'ID clic e sincronizzazione dell'ID. |
| `MYBING_PAGEVIEW`, `MYBING_PURCHASE`, `MYBING_PURCHASE_PAID_ONLY` | `1`, `1`, `0`. |
| `MYBING_LEAD`, `MYBING_LEAD_N`, `MYBING_INITIATE`, `MYBING_INITIATE_D` | `0`, `1`, `1`, `1`. |
| `MYBING_SEARCH`, `MYBING_ADDTOCART`, `MYBING_REMOVECART`, `MYBING_WISHLIST` | Tutti `1`. |
| `MYBING_ADDPAYMENT`, `MYBING_CONTACT`, `MYBING_REFUND` | Tutti `1`. |
| `MYBING_DPA`, `MYBING_VCONTENT`, `MYBING_VIEW_ITEM_LIST`, `MYBING_REG` | Tutti `1`. |
| `MYBING_ATTRID`, `MYBING_SEPSIGN`, `MYBING_PREFIX`, `MYBING_SUFIX` | `0`, `-`, vuoti per lingua, vuoti per lingua. |
| `MYBING_EXFREE`, `MYBING_ATC_B`, `MYBING_ATC_PPP`, `MYBING_PREPRICE` | `0`, `.add-to-cart`, `.current-price span`, `0`. |
| `MYBING_CONCURR`, `MYBING_CURRSELECT` | `0`, `0`. |
| `MYBING_CONSENT_REQUIRED`, `MYBING_CONSENT_MODE`, `MYBING_TCF` | `0`, `auto`, `1`. |
| `MYBING_GHOST`, `MYBING_USER_ID`, `MYBING_ENHANCED_CONV` | `1`, `0`, `0`. |
| `MYBING_IGNORE_ADMIN`, `MYBING_BOT_FILTER`, `MYBING_DEBUG` | `1`, `0`, `0`. |
| `MYBING_PAID_STATUSES`, `MYBING_REFUND_STATUSES` | ID di stato vuoti separati da virgole. |
| `MYBING_STATS_ENABLED`, `MYBING_STATS_RETENTION`, `MYBING_STATS_POLL`, `MYBING_STATS_LOG_PV` | `1`, `14`, `5`, `0`. |
| `MYBING_WIZARD_DONE`, `MYBING_WIZARD_REDO` | `0`, `0`. |
| `MYBING_INSTALL_SQL_WARN`, `MYBING_INSTALL_ERROR` | Diagnostica dell'installazione in runtime. |
| `MYBING_LAST_FLUSH` | Riepilogo dello svuotamento JSON di runtime; non nell'elenco delle chiavi di disinstallazione. |

La configurazione/disinstallazione elimini anche i precedenti `MYBING_CAPI_AUTH_CLIENT_ID`, `MYBING_CAPI_AUTH_CLIENT_SECRET`, `MYBING_CAPI_AUTH_REFRESH_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_EXPIRES`, `MYBING_PROFILE_ID`, `MYBING_CAPI_REGION`, `MYBING_CAPI_COUNTRY`, `MYBING_ATC_PC`, `MYBING_ATC_PP`, `MYBING_LINKER_DOMAINS` e `MYBING_ADS_ID`. `MYBING_DEBUG_MODE` viene eliminato durante l'installazione ma è assente dall'elenco di disinstallazione.

Il programma di aggiornamento utilizzi `mypresta_updates`, `update_mybing` e `updatev_mybing`; questi potrebbero rimanere dopo la disinstallazione. `mypresta_updates` è condiviso.

### 6.7 Disinstallazione, traduzioni ed estensione

`uninstall()` elimini la scheda nascosta, elimini tutte le tabelle dei moduli, elimini i valori `getConfigurationKeys()` e la diagnostica di installazione, quindi richiama `parent::uninstall()`. Non elimini le chiavi di aggiornamento o `MYBING_LAST_FLUSH`.

Non sono presenti override di PrestaShop. Le traduzioni vivono in `translations/{iso}.php`; la maggior parte delle stringhe dell'interfaccia utente utilizza `$this->l()` o Smarty `{l}`, mentre i nomi degli eventi e alcuni parametri diagnostici delle classi rimangono in inglese.

I temi possono riposizionare gli hook supportati e definire lo stile dell'ispettore, ma il blocco del prodotto è intenzionalmente nascosto. Conservi gli attributi dei dati e gli script durante l'override dei modelli di hook. Un CMP personalizzato può inviare `mybing.consent` con la concessione `1` o `0` o fornire un segnale riconosciuto da `MybingConsent`.

## 7. Aiuto

Apra la pagina del modulo: https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html

Acceda al suo account cliente su mypresta.eu, apra la pagina dei contatti e scelga **Support for paid modules**. È richiesto l'accesso; quindi selezioni questo modulo dalla cronologia degli acquisti e includa la modalità di monitoraggio, l'errore visibile e il risultato diagnostico.
