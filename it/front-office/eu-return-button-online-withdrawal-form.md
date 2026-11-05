---
title: "Return Button Pro - documentazione e manuale utente"
description: "Configuri il modulo di recesso UE, gestisca i casi nel back office e risolva i problemi più comuni se già utilizza Return Button Pro."
sidebar:
  label: "Return Button Pro - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo EU Return Button – Online Withdrawal Form su MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/eu-return-button-online-withdrawal-form/)
>
> ---



Le schermate di questo manuale mostrano il back office in inglese. Utilizzi gli stessi nomi di menu e etichette riportati qui.

## 1. Requisiti

Return Button Pro funziona su PrestaShop 1.6, 1.7, 8 e 9. Usi il pacchetto adatto al negozio: la build dedicata a PrestaShop 1.6 per i negozi 1.6 e la build per PrestaShop 1.7–9 per quelli più recenti. Se nello storico ordini MyPresta.eu sono disponibili entrambi i pacchetti, scarichi lo ZIP corretto.

- PrestaShop: 1.6.x, 1.7.x, 8.x e 9.x
- PHP: le versioni su cui gira già il Suo PrestaShop, inclusi ambienti più vecchi con PrestaShop 1.6 (PHP 5.6 e PHP 7.x) e le versioni richieste da PrestaShop 1.7–9 (PHP 7.1+ / PHP 8.x in base a hosting e negozio). Il modulo è mantenuto anche per ambienti PHP 7.x e per il PHP attuale del negozio.
- Estensioni PHP usate dal modulo: JSON, curl (controlli aggiornamento), fileinfo (controlli MIME degli allegati), hash (token e sicurezza ospiti)
- Altri moduli: non richiesti. Se il modulo gratuito Return Button è installato e abilitato, lo disabiliti prima di configurare o usare Return Button Pro. Entrambi non possono funzionare contemporaneamente.
- Account esterni: nessuno. I controlli aggiornamento opzionali di MyPresta.eu usano Internet dalla scheda **Updates**.

## 2. Installazione

1. Carichi lo ZIP del modulo in **Modules** → **Module Manager**, quindi installi e abiliti **Return Button Pro**.
2. Dopo l’installazione, sotto **Customers** compare la voce **Withdrawals**. Apra la configurazione da **Module Manager** → **Return Button Pro** → **Configure** (schede: **Dashboard**, **Settings**, **Updates**).
3. L’installazione non svuota la cache PrestaShop. Svuoti la cache autonomamente dopo modifiche al tema o agli hook se il front store appare ancora errato.

Disinstallazione: la voce di menu **Withdrawals** viene rimossa e i valori di configurazione vengono eliminati. Le tabelle di recesso e i record dei casi restano nel database come prova legale. La reinstallazione non cancella quei record; il modulo può riutilizzarli quando le tabelle esistono già. Gli allegati del personale caricati nella cartella del modulo non vengono rimossi alla disinstallazione.

Se aggiorna dal modulo gratuito Return Button, Pro può copiare impostazioni compatibili e migrare tabelle Pro vuote dai dati del modulo gratuito quando Pro non ha ancora righe. Disabiliti prima il modulo gratuito.

## 3. Configurazione e lavoro nel back office

### 3.1 Processo completo di recesso

Flusso end-to-end dal front store alla gestione del personale:

1. Il cliente trova l’ingresso al recesso: pulsante nel footer, link Il mio account, pulsante nel dettaglio ordine, oppure l’URL del modulo quando l’accesso ospite è attivo.
2. **Passo 1 – ordine:** i clienti autenticati vedono i propri ordini con indicazioni di idoneità (giorni rimasti, motivi di indisponibilità). Gli ospiti inseriscono riferimento ordine e e-mail. Il cliente seleziona un ordine idoneo, sceglie **Full order** o **Partial** (con quantità sulle righe consentite), aggiunge facoltativamente un messaggio e l’IBAN, quindi continua.
3. **Passo 2 – conferma:** il cliente rivede il riepilogo della dichiarazione. Quando **Require legal confirmation checkbox** è attivo, deve spuntare il testo legale e poi inviare.
4. Il modulo salva il caso, lo porta a **Registered** e invia la conferma al cliente (supporto durevole) più una notifica al negozio (e **Notification email** se impostata). La pagina di successo mostra il riferimento di recesso.
5. Il personale apre **Customers** → **Withdrawals** (o il pannello laterale dell’ordine), apre **View**, imposta lo stato (**In progress**, **Refunded**, **Rejected**, ecc.) e inserisce un messaggio al cliente quando richiesto.
6. Il cliente segue lo stato tramite **Track withdrawal status**, la pagina di stato e **Print / save PDF**. I messaggi del personale dai cambi di stato compaiono nella cronologia di recesso del cliente.

Stati usati dal modulo:

| Campo | All’inizio | Cosa fa |
|---|---|---|
| **Pending** | Stato breve quando la dichiarazione viene salvata per la prima volta | Caso aperto prima che termini la conferma legale del cliente, o quando il personale imposta questo stato in seguito. Concorre al blocco dei duplicati con gli altri stati aperti. |
| **Registered** | Dopo la conferma del cliente al passo 2 | Dichiarazione registrata; tentativi di e-mail di conferma. Stato predefinito dopo l’invio. |
| **In progress** | Azione del personale | Il negozio gestisce il caso (resi, controlli, preparazione rimborso). Continua a bloccare una seconda richiesta attiva se il blocco duplicati è attivo. |
| **Refunded** | Azione del personale | Caso chiuso con rimborso. Visibile nella pagina di stato del cliente. |
| **Rejected** | Azione del personale | Caso chiuso senza rimborso. Usi un messaggio chiaro al cliente quando l’impostazione lo richiede. |

Ambito sul modulo: **Full order** o **Partial**. Tipo: **Contract withdrawal** (pagato) o **Contract cancellation (unpaid order)** quando l’ordine non è mai stato pagato.

### 3.2 Dashboard

Apra **Modules** → **Module Manager** → **Return Button Pro** → **Configure** → **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/rbpro-dashboard.webp)

Filtri con **From** / **To** e **Apply**, oppure reimposti con **Last 30 days**. Il pannello mostra totali di tutti i tempi, backlog in attesa, profilo tema rilevato, hook footer attivo, KPI (recessi nel periodo, tasso vs ordini, quota conferma e-mail, giorni medi dall’ordine al recesso, quota parziale/totale, cancellazioni, quota rimborsata dei casi chiusi, tasso di rifiuto), un grafico degli invii giornalieri, ripartizione per stato, prodotti più recessi e casi in attesa più vecchi con **Open**.

Usi **Manage all withdrawals** per l’elenco sotto Customers, o **Export CSV** per scaricare i casi del negozio corrente.

### 3.3 Settings

Apra la scheda **Settings** e clicchi su **Save** dopo le modifiche.

![Settings](https://mypresta.eu/docs/images/docs/rbpro-settings.webp)

#### Integrazione tema

Adatti il modulo a Classic, Hummingbird o a un tema personalizzato. Regoli queste opzioni se pulsanti o moduli risultano senza stile dopo un aggiornamento del tema.

| Campo | All’inizio | Cosa fa |
|---|---|---|
| **Storefront theme profile** | Auto-detect | Sceglie quali template e CSS di front office carica il modulo (Classic vs Hummingbird). Stile corretto del pulsante, layout del modulo e aspetto del link Il mio account. Lasci Auto-detect salvo se il pulsante appare errato dopo un cambio tema; allora forzi Classic-type o Hummingbird-type in base al tema attivo. Dopo la modifica, svuoti la cache PrestaShop e aggiorni il front store. |
| **Footer button hook** | Auto (by theme profile) | Definisce dove nel footer della pagina viene iniettato il pulsante di recesso. Auto segue il profilo tema (Hummingbird → displayFooterBefore, Classic → displayFooter). Se il pulsante manca o è disallineato, provi displayFooterBefore o displayFooter manualmente, salvi, svuoti la cache e controlli il footer del negozio. Per il posizionamento manuale, inserisca l’hook personalizzato in un template del tema e selezioni displayRbproButton qui; tenga **Footer button** abilitato così il pulsante appare solo in quel template. |

#### Generali e accesso

| Campo | All’inizio | Cosa fa |
|---|---|---|
| **Module enabled** | Yes | Interruttore principale di tutto il modulo. Se disabilitato, pulsanti di recesso, modulo, accesso ospite e tracking sono nascosti sul front store; i record esistenti nel back office restano. Lo usi per manutenzione o revisione legale senza disinstallare. |
| **Public status tracking page** | Yes | Abilita una pagina pubblica in cui i clienti verificano lo stato del recesso con riferimento + e-mail (senza login). Riduce i ticket «dove è il mio reso?». La abiliti se vuole un link **Track withdrawal status** accanto al pulsante del footer; comunichi il riferimento dall’e-mail di conferma. La disabiliti se gestisce lo stato solo via e-mail dell’account o telefono. |
| **Guest access (order ref + email)** | Yes | Consente ai clienti non autenticati di aprire il modulo inserendo riferimento ordine e e-mail al passo 1. Consigliato per le vendite a distanza B2C in UE. Lo disattivi se solo i clienti autenticati possono recedere. Le sessioni ospite usano un cookie firmato. |
| **Block duplicate active requests** | Yes | Impedisce un secondo recesso aperto per lo stesso ordine mentre uno è già Pending, Registered o In progress. Evita casi duplicati e rimborsi in conflitto. Lo lasci attivo in produzione. Lo disabiliti solo per test o processi insoliti di richiesta parziale. |
| **Require legal confirmation checkbox (step 2)** | Yes | Obbliga il cliente a spuntare una casella con formulazione legale prima dell’invio. Traccia di consenso esplicito allineata alle regole di recesso UE. Modifichi il testo della casella per lingua in Texts & SEO. Se disabilitato, l’invio viene comunque registrato senza casella obbligatoria. |
| **Require message to customer when changing status** | Yes | Il personale deve inserire un messaggio al cliente prima di aggiornare lo stato di un recesso. Il messaggio è memorizzato nella pista di audit e mostrato nella pagina di stato del cliente. Lo disattivi solo se necessita di cambi di stato rapidi senza scrivere ogni volta. |
| **Show deadline countdown to customer** | Yes | Mostra quanti giorni restano del periodo legale di recesso (elenco ordini e modulo). Richiede un mapping corretto di **Order state = delivered** e il periodo di recesso. Se le date sembrano errate, controlli la cronologia ordine e lo stato consegnato. |
| **Optional IBAN field** | No | Aggiunge un campo IBAN opzionale sul modulo per i rimborsi. Lo abiliti solo se rimborsa tramite bonifico e la privacy policy lo copre. Lo lasci disattivo se rimborsa solo sul metodo di pagamento originale. |
| **Notification email** | Empty | Indirizzo aggiuntivo che riceve le notifiche di nuovi recessi (oltre al contatto del negozio). Esempio: returns@yourshop.com. Lo lasci vuoto per usare solo il flusso mail predefinito di PrestaShop senza questo destinatario. |

#### Regole di recesso

| Campo | All’inizio | Cosa fa |
|---|---|---|
| **Withdrawal period (days from delivery)** | 14 | Giorni di calendario a disposizione dei clienti per recedere dopo che l’ordine è considerato consegnato. Predefinito 14 per i contratti a distanza UE. Lo cambi solo se la legge o i suoi termini richiedono un altro valore. Il conto alla rovescia parte dalla data di consegna derivata dalla cronologia ordine e da **Order state = delivered**. |
| **Order state = delivered** | Auto | Stato ordine che segna la merce come consegnata (inizio del periodo di recesso). Scelga lo stato impostato quando il pacco è consegnato (ad esempio Delivered, o Shipped se quello è lo stato finale). Auto usa un valore sensato del negozio; lo sovrascriva se le scadenze usano la data sbagliata. |
| **Allowed order statuses** | All order statuses | Controlla quando i clienti possono inviare un recesso in base allo stato attuale dell’ordine. Scelga **All order statuses** per saltare il filtro, oppure **Only selected statuses** e sposti gli stati dalla colonna sinistra a **Allowed for withdrawal**. Gli ordini fuori elenco risultano non disponibili nell’elenco ordini dell’account. |
| **Excluded products** | Empty | Prodotti specifici non recessibili (beni sigillati, personalizzati, ecc.). Cerchi per nome o mantenga gli ID; le righe escluse mostrano il messaggio di esclusione sul modulo. |
| **Excluded product variants** | Empty | Varianti specifiche escluse dal recesso. Cerchi il prodotto, poi selezioni la variante. |
| **Excluded categories** | Empty | Tutti i prodotti in queste categorie non sono recessibili. |
| **Excluded manufacturers** | Empty | I prodotti di questi produttori non possono essere recessi. |
| **Excluded suppliers** | Empty | I prodotti collegati a questi fornitori non possono essere recessi. |
| **Excluded customer groups** | Empty | I clienti in questi gruppi non possono usare il recesso affatto (nessun accesso al modulo, pulsanti nascosti). |

#### Footer e aspetto

| Campo | All’inizio | Cosa fa |
|---|---|---|
| **Footer button** | Yes | Mostra la call-to-action principale di recesso nel footer del negozio (hook configurato sopra). Lo disabiliti se vuole solo i link Il mio account e dettaglio ordine. Richiede **Module enabled** e un hook footer corretto. |
| **Footer theme** | Light footer (dark text) | Schema colori per testo e link del footer (non lo sfondo del pulsante). Scelga Light su footer chiari, Dark su footer neri/scuri così **Track withdrawal status** resta leggibile. Svuoti la cache dopo la modifica. |
| **Footer alignment** | Center | Allineamento orizzontale del blocco pulsante del footer: Left, Center o Right. Influenza solo l’output dell’hook footer. |
| **Button color** | #2563eb | Colore di sfondo dei pulsanti di recesso (footer, dettaglio ordine, ecc.). Scelga un colore hex con contrasto sufficiente rispetto al testo bianco. Non cambia il colore primario del tema a livello globale. |
| **Custom CSS** | Empty | CSS aggiuntivo sulle pagine in cui compaiono i pulsanti del modulo. Per margini, font o nascondere elementi senza modificare i file del tema. Testi prima in staging. |
| **Link in customer account** | Yes | Aggiunge una voce di recesso in My Account. Consigliato attivo. Lo disabiliti solo se si basa esclusivamente su link del footer o dell’ordine. |
| **Link on order detail** | Yes | Mostra l’azione di recesso nella pagina dettaglio ordine quando l’ordine è idoneo. Gli ordini bloccati mostrano un breve motivo al posto del pulsante. |

#### Texts & SEO

Compili ogni lingua attiva del negozio.

| Campo | All’inizio | Cosa fa |
|---|---|---|
| **Noindex on form page** | Yes | Aggiunge robots noindex,nofollow sull’URL del modulo di recesso così le pagine legali/modulo restano fuori dai risultati di ricerca. Lo disattivi solo se vuole indexare intenzionalmente il modulo. |
| **Button label** | Withdraw from contract | Testo di tutti i pulsanti e link di recesso. Un’etichetta breve funziona meglio nel footer. Frase principale orientata al cliente del modulo. |
| **Exclusion message** | This product is excluded from the statutory right of withdrawal. | Mostrato accanto ai prodotti esclusi sul modulo. Spieghi perché l’articolo non è selezionabile; menzioni i termini se necessario. |
| **SEO title** | Withdraw from contract | Titolo HTML della pagina del modulo di recesso (scheda del browser). Lo tenga sotto circa 60 caratteri per lingua. |
| **SEO description** | Online withdrawal form for distance contracts. | Meta description del modulo. Di solito inutilizzata per il ranking con noindex attivo. La lasci vuota per ometterla. |
| **Legal confirmation checkbox text** | I confirm that I am submitting a withdrawal statement and understand the legal consequences. | Etichetta accanto alla casella obbligatoria al passo 2. Usi una formulazione chiara e adeguata al Paese. Richiesto quando **Require legal confirmation checkbox** è attivo. |

### 3.4 Updates

Apra la scheda **Updates**.

| Campo | All’inizio | Cosa fa |
|---|---|---|
| **Manual Check** | — | Controlla su MyPresta.eu se esiste una versione più recente del modulo. Vedrà **New version available!** o **Module is up to date!**. Richiede curl e HTTPS in uscita. |
| **Automatic Notifications** | Enabled (module default for update prefs) | Se abilitato, il back office può mostrare un avviso che esiste una nuova versione. Salvi con **Save**. |
| **Product Page** | Link on form | Apre la pagina prodotto ufficiale per le informazioni di rilascio. Usi Supporto (§7) per l’aiuto sui moduli a pagamento dopo il login. |

Se il modulo gratuito Return Button è ancora abilitato, impostazioni e azioni di aggiornamento restano bloccate finché non lo disabilita.

### 3.5 Elenco recessi

Vada a **Customers** → **Withdrawals**.

![Withdrawals list](https://mypresta.eu/docs/images/docs/rbpro-withdrawals.webp)

L’ordinamento predefinito è l’invio più recente per primo. Colonne:

| Campo | All’inizio | Cosa fa |
|---|---|---|
| **ID** | Auto | Id interno del caso. |
| **Submitted** | From form | Data e ora dell’invio del cliente. |
| **Order** | From order | Riferimento ordine PrestaShop. |
| **First name** / **Last name** / **Email** | From customer | Identità di contatto del caso. |
| **Scope** | Full order or Partial | Se è stato recessato l’intero ordine o righe selezionate. |
| **Type** | Contract withdrawal or cancellation | Recesso su ordine pagato vs cancellazione di ordine non pagato. |
| **Status** | Registered after confirm | Stato attuale del caso (Pending, Registered, In progress, Refunded, Rejected). |
| **Email** | Yes/No | Se l’e-mail di conferma è stata registrata come inviata. |

Usi ricerca e ordinamento sull’elenco. Apra un caso con **View**. Non c’è azione **Add new**: le richieste sono create solo dai clienti sul front store. Se qualcuno tenta di creare un caso nel back office, l’avviso spiega che i recessi non possono essere creati manualmente e viene mostrato di nuovo l’elenco.

Esporti CSV da **Dashboard** (**Export CSV**) quando serve un foglio di calcolo dei casi del negozio.

### 3.6 Vista del caso di recesso

Apra una riga con **View**.

L’intestazione mostra riferimento, ID, data di invio, stato, tipo, ambito, flag e ora e-mail inviata, scadenza, IP, user-agent, nome e e-mail del cliente, e un link all’ordine PrestaShop. Il blocco prodotti elenca ogni riga recessata con quantità e prezzo unitario. IBAN e messaggio del cliente compaiono quando il cliente li ha forniti.

**Update status**

1. Scelga **New status**.
2. Scriva **Message to customer** (obbligatorio quando quella impostazione è attiva; altrimenti facoltativo). Il testo di aiuto spiega che il messaggio appare nella cronologia di recesso del front store.
3. Clicchi su **Update status**.

Successo: **Status updated.** Altri messaggi: **Please enter a message for the customer when changing the status.**, **Status is already set to this value.**, **Invalid status.**, **Could not update status.**

**Resend confirmation email** reinviia la conferma al cliente, aggiorna il flag di inviato se ha successo e registra l’evento. Successo: **Confirmation email sent.** Fallimento: **Could not send email.**

**Internal notes** sono solo per il personale. Inserisca il testo e clicchi su **Add note**. Le note compaiono sotto **Internal notes** e nella pista di audit; non sostituiscono il messaggio di stato rivolto al cliente.

**Attachments** accettano caricamenti del personale (PDF e immagini comuni, max 10 MB). Scarichi cliccando sul nome del file. Messaggi: **Attachment uploaded.**, **Invalid file or size over 10 MB.**, **File type not allowed.**, **Upload failed.**

**Audit trail** elenca data, evento, dipendente e dettagli (transizioni di stato e messaggi). Eventi tipici: il cliente ha inviato la dichiarazione, il cliente ha confermato la dichiarazione legale, stato aggiornato, e-mail di conferma inviata, documento aggiunto, nota interna aggiunta.

Usi **Back to list** per tornare a **Withdrawals**.

### 3.7 Pannello laterale ordine nel back office

Su PrestaShop 1.7.7 e successive, apra un ordine nel back office. Quando quell’ordine ha casi di recesso, un blocco laterale **Withdrawal requests** elenca ogni riferimento, badge di stato, data e **View** (apre il caso). Su build 1.7 più vecchie senza l’hook laterale ordine, usi **Customers** → **Withdrawals** e filtri per riferimento ordine.

I casi in attesa possono anche generare un avviso nel back office con il conteggio delle richieste in attesa di revisione e un link all’elenco.

## 4. Front store

Qui non sono incluse schermate del front store; colleghi il tema e controlli il negozio live dopo aver salvato Settings e svuotato la cache.

### 4.1 Footer

Con **Footer button** attivo e l’hook corretto, le pagine mostrano il pulsante di recesso (etichetta da **Button label**) stilizzato con **Button color**, più **Track withdrawal status** quando il tracking pubblico è attivo. **Footer alignment** e **Footer theme** controllano layout e contrasto del testo. Se il tema non chiama mai l’hook footer selezionato, cambi l’hook o inserisca l’hook personalizzato in un template e selezioni quell’opzione sotto **Footer button hook**.

### 4.2 Account cliente

Con **Link in customer account** attivo, My Account mostra la voce di recesso (e il link di tracking dove il template dell’account lo include). I gruppi clienti esclusi non vedono punti di ingresso.

### 4.3 Dettaglio ordine

Con **Link on order detail** attivo, gli ordini idonei mostrano il pulsante di recesso precompilato per quell’ordine. I casi esistenti per l’ordine sono elencati con lo stato. Gli ordini non idonei mostrano un breve motivo al posto del pulsante, ad esempio periodo scaduto, stato non consentito, richiesta attiva duplicata o nessun prodotto idoneo.

### 4.4 Accesso ospite

Quando **Guest access** è attivo, un visitatore apre il modulo, inserisce riferimento ordine e e-mail, quindi continua come un cliente autenticato per quell’ordine. Quando l’accesso ospite è disattivo, gli ospiti vedono che devono accedere (o che deve abilitare l’accesso ospite in Settings). Token di sicurezza non validi e troppi tentativi mostrano messaggi chiari di attesa / nuovo tentativo.

### 4.5 Traccia stato

**Track withdrawal status** chiede il riferimento di recesso (formato tipo RBP-…) e l’e-mail, poi mostra stato, data di invio, ambito, stato dell’e-mail di conferma e link a dettagli e stampa. Coppia errata: **No withdrawal found for these details.**

### 4.6 Pagina di stato e stampa

Dopo l’invio, **Withdrawal submitted** mostra il riferimento, una checklist (dichiarazione salvata, e-mail di conferma, il negozio elaborerà), poi **View withdrawal details**, **Track status** e **Print / save PDF**. La pagina di stato elenca prodotti, quantità, prezzi, totali e **Withdrawal history** inclusi i messaggi del personale dagli aggiornamenti di stato. La stampa apre una pagina di prova stampabile con un token sicuro dal flusso di conferma.

## 5. Problemi

### 5.1 Return Button gratuito ancora abilitato

**Sintomo:** la configurazione è bloccata; avviso che l’altro modulo di reso è abilitato; il salvataggio può indicare che le modifiche non sono state salvate finché quel modulo non è disabilitato.

**Cosa fare:** **Modules** → **Module Manager** → trovi il modulo gratuito Return Button → **Disable**. Poi riapra Return Button Pro.

### 5.2 Pulsante footer mancante

**Sintomo:** nessun pulsante di recesso nel footer.

**Cosa fare:** confermi che **Module enabled** e **Footer button** sono attivi. In **Settings**, imposti **Footer button hook** su Auto o provi le altre posizioni footer una alla volta. Svuoti la cache e ricarichi forzatamente il negozio. Per temi personalizzati, inserisca l’hook personalizzato del modulo nel template e selezioni quell’opzione in **Footer button hook**. Apra **Dashboard**: mostra il profilo tema rilevato e il nome dell’hook footer attivo per il confronto con il tema.

### 5.3 «Return not available — the withdrawal period has ended.»

**Sintomo:** dettaglio ordine o modulo bloccano il recesso con questo messaggio.

**Cosa fare:** controlli **Withdrawal period** e **Order state = delivered**. Corregga la cronologia ordine se la consegna non è mai stata registrata. Estenda il periodo solo se i suoi termini lo consentono.

### 5.4 «An active withdrawal request already exists for this order.»

**Sintomo:** il cliente non può aprire un secondo caso.

**Cosa fare:** concluda o chiuda il caso esistente (**Refunded** / **Rejected**), oppure disattivi temporaneamente **Block duplicate active requests** solo se il processo consente davvero più richieste aperte.

### 5.5 «This order status does not allow withdrawal.»

**Sintomo:** l’ordine è fuori dal filtro degli stati consentiti.

**Cosa fare:** in **Settings**, imposti **Allowed order statuses** su **All order statuses**, oppure aggiunga lo stato attuale dell’ordine a **Allowed for withdrawal**.

### 5.6 «No products in this order are eligible for withdrawal.» / messaggio di esclusione sulle righe

**Sintomo:** ogni riga esclusa, oppure righe parziali selezionate non valide.

**Cosa fare:** esamini prodotti, varianti, categorie, produttori e fornitori esclusi. Regoli **Exclusion message** così i clienti capiscono il motivo.

### 5.7 «Withdrawal is not available for your customer account.»

**Sintomo:** modulo o pulsanti nascosti per un cliente autenticato.

**Cosa fare:** rimuova il gruppo del cliente da **Excluded customer groups**, oppure sposti il cliente in un gruppo consentito.

### 5.8 «Please enter a message for the customer when changing the status.»

**Sintomo:** l’aggiornamento di stato fallisce nella vista del caso.

**Cosa fare:** compili **Message to customer**, oppure disattivi **Require message to customer when changing status** se il processo consente messaggi vuoti.

### 5.9 E-mail di conferma non inviata

**Sintomo:** il caso mostra e-mail non inviata; il cliente non ha conferma durevole.

**Cosa fare:** corregga le impostazioni mail PrestaShop, controlli lo spam, usi **Resend confirmation email**. Imposti **Notification email** per le copie al personale. Confermi che l’e-mail di contatto del negozio funziona.

### 5.10 L’ospite non trova l’ordine

**Sintomo:** **No order found for the given details.** oppure attesa per rate limit.

**Cosa fare:** faccia corrispondere esattamente riferimento ordine e e-mail dell’ordine. Attenda se ci sono troppi tentativi. Confermi che **Guest access** è attivo.

### 5.11 Il controllo aggiornamenti fallisce o resta silenzioso

**Sintomo:** il controllo manuale non segnala una versione.

**Cosa fare:** si assicuri che curl funzioni e che il server raggiunga MyPresta.eu. Disabiliti il modulo gratuito se Pro è bloccato. Riprovi **Manual Check** nella scheda **Updates**.

## 6. Per sviluppatori

### 6.1 Panoramica

- Nome tecnico: `rbpro`
- Versione: pacchetto attuale 1.7–9 (es. 1.4.6); PrestaShop 1.6 come pacchetto separato (es. 1.4.5) con `ps_versions_compliancy` min `1.6.0.0`
- Nome visualizzato: Return Button Pro
- Autore: MyPresta.eu
- Tab: `front_office_features`
- Classe principale: `Rbpro`
- `ps_versions_compliancy` nel pacchetto 1.7–9: min `1.7.0.0`; nel pacchetto 1.6: min `1.6.0.0`
- Layer di servizio: `RbpWithdrawalService`; sicurezza: `RbpSecurity`; tema/hook: `RbpCompatibility`; analytics: `RbpStatsService`
- Flusso: chiavi di configurazione → hook / controller front → tabelle `rbp_withdrawal*` → admin `AdminRbpWithdrawal` → stato/traccia/stampa cliente

### 6.2 File importanti

| Percorso | Ruolo |
|---|---|
| `rbpro.php` | Bootstrap del modulo, install/uninstall, schede configure, hook, default |
| `classes/RbpWithdrawal.php` | Modello oggetto del caso e stati |
| `classes/RbpWithdrawalService.php` | Idoneità, scadenze, create/confirm, e-mail, aggiornamenti di stato |
| `classes/RbpSecurity.php` | CSRF, grant ospite, rate limit, sanitizzazione IBAN |
| `classes/RbpCompatibility.php` | Profilo tema, risoluzione hook footer, URL admin, hook richiesti |
| `controllers/admin/AdminRbpWithdrawalController.php` | Elenco e vista caso |
| `controllers/front/form.php` | Modulo in due passi |
| `controllers/front/confirm.php` | Pagina di successo |
| `controllers/front/track.php` | Tracking pubblico |
| `controllers/front/status.php` | Dettagli caso per il cliente |
| `controllers/front/print.php` | Prova stampabile |
| `sql/install.sql` | Crea le tabelle `rbp_*` |
| `sql/uninstall.sql` | Solo commento — tabelle conservate |
| `lib/updateChecker.php` | UI aggiornamento MyPresta (`rbproUpdate`) |
| `views/templates/admin/*` | Dashboard, shell configure, vista caso, avviso laterale ordine |
| `views/templates/front/*` | Modulo, confirm, track, status, print, error |
| `views/templates/hook/*` | Pulsanti footer/account/ordine (classic / hummingbird) |
| `mails/*` | Template `rbf_withdrawal_customer` / `rbf_withdrawal_admin` |
| `translations/*.php` | Traduzioni del pack |

### 6.3 Controller

| Controller | Parent / ingresso | Note |
|---|---|---|
| Configure (`getContent`) | Module Manager | Schede `rbp_tab`: `dashboard`, `settings`, `updates` |
| `AdminRbpWithdrawal` | Customers → Withdrawals | `add`/`edit` false; percorso di creazione solo lettura; export CSV; download allegati |
| Front `form` | Module link | Passi 1–2; lookup ospite; cookie bozza |
| Front `confirm` | Module link | Successo dopo l’invio |
| Front `track` | Module link | Riferimento + e-mail |
| Front `status` | Module link | Timeline + prodotti |
| Front `print` | Module link | Token HMAC sul riferimento |

I permessi seguono la scheda admin. I controller front richiedono il modulo abilitato per il modulo; il tracking rispetta `RBP_ENABLE_STATUS_TRACK`.

### 6.4 Hook

Registrati: `displayHeader`, `actionFrontControllerSetMedia`, `displayCustomerAccount`, `displayOrderDetail`, `actionPresentOrder`, `displayFooter`, `displayFooterBefore`, `displayFooterAfter`, `displayRbproButton`; su PS ≥ 1.7.7 anche `displayBackOfficeHeader`, `displayAdminOrderSide`.

Eseguiti dal modulo: `actionRbpWithdrawalCreated`, `actionRbpWithdrawalConfirmed` (e hook legati allo stato dal service dove definiti).

L’output del footer viene eseguito solo per il nome hook risolto da `RbpCompatibility::getFooterHookName()`.

### 6.5 Override

Nessun override di classe o controller. L’integrazione tema usa solo hook e template selezionabili.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `PREFIX_rbp_withdrawal` | Intestazione caso: negozio, ordine, cliente, riferimento, ambito, tipo, stato, IBAN, messaggio, IP, UA, lingua, flag e-mail, scadenza, date |
| `PREFIX_rbp_withdrawal_product` | Righe selezionate e quantità |
| `PREFIX_rbp_withdrawal_note` | Note interne del personale |
| `PREFIX_rbp_withdrawal_attachment` | Metadati caricamenti del personale |
| `PREFIX_rbp_withdrawal_history` | Eventi di audit |

La disinstallazione **non** elimina queste tabelle. `ensureDatabase()` crea le tabelle mancanti e può migrare da `rbf_*` quando le tabelle Pro sono vuote e quelle gratuite hanno righe.

### 6.7 Chiavi di configurazione e traduzioni

Default da `Rbpro::CONFIG`:

| Chiave | Default |
|---|---|
| `RBP_ENABLED` | 1 |
| `RBP_GUEST_ENABLED` | 1 |
| `RBP_IBAN_ENABLED` | 0 |
| `RBP_WITHDRAWAL_DAYS` | 14 |
| `RBP_DELIVERED_STATUS` | 0 (Auto) |
| `RBP_EXCLUDED_PRODUCTS` / `_COMBINATIONS` / `_CATEGORIES` / `_MANUFACTURERS` / `_SUPPLIERS` / `_CUSTOMER_GROUPS` | empty |
| `RBP_ALLOWED_ORDER_STATES` | empty |
| `RBP_ALLOWED_ORDER_STATES_RESTRICT` | 0 |
| `RBP_FOOTER_ENABLED` | 1 |
| `RBP_FOOTER_THEME` | light |
| `RBP_FOOTER_POSITION` | center |
| `RBP_BUTTON_COLOR` | `#2563eb` |
| `RBP_CUSTOM_CSS` | empty |
| `RBP_SHOW_ACCOUNT` / `RBP_SHOW_ORDER` | 1 |
| `RBP_SEO_NOINDEX` | 1 |
| `RBP_ADMIN_EMAIL` | empty |
| `RBP_BLOCK_DUPLICATE` | 1 |
| `RBP_SHOW_DEADLINE` | 1 |
| `RBP_REQUIRE_CHECKBOX` | 1 |
| `RBP_REQUIRE_STATUS_MESSAGE` | 1 |
| `RBP_THEME_TYPE` | auto |
| `RBP_FOOTER_HOOK` | auto |
| `RBP_ENABLE_STATUS_TRACK` | 1 |

Multilingua (non nell’array `CONFIG`, installati dai default): `RBP_BUTTON_TEXT`, `RBP_EXCLUSION_MSG`, `RBP_SEO_TITLE`, `RBP_SEO_DESC`, `RBP_LEGAL_CHECKBOX`. Runtime: `RBP_ADMIN_FOLDER`. Le preferenze di aggiornamento usano le chiavi del checker MyPresta. La migrazione dal modulo gratuito mappa `RBF_*` → `RBP_*` quando le chiavi Pro sono vuote.

Traduzioni: `translations/{iso}.php`. Le stringhe `desc` dei campi vivono in `renderConfigurationForm()` tramite `$this->l()`.

Stati: `pending`, `confirmed` (etichetta Registered), `processing`, `refunded`, `rejected`.

### 6.8 Estensione

Sovrascriva TPL/CSS degli hook nel tema per `modules/rbpro/...` senza modificare il modulo. Inserisca `{hook h='displayRbproButton'}` per il posizionamento personalizzato del pulsante. Ascolti `actionRbpWithdrawalCreated` / `actionRbpWithdrawalConfirmed`. Non si affidi agli override: non ce ne sono da concatenare.

## 7. Supporto

Pagina prodotto: https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html

Aiuto per questo modulo a pagamento: acceda al suo account cliente su mypresta.eu, apra Contact e scelga **Support for paid modules**. Il modulo richiede login per i moduli a pagamento; dopo il login, selezioni Return Button Pro dalla cronologia degli acquisti.