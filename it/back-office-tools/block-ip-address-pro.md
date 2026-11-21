---
title: Ban IP Pro - documentazione e manuale utente
sidebar:
  label: Ban IP Pro - documentazione e manuale utente
description: Manuale di configurazione e di risoluzione dei problemi per i negozi che hanno già Ban IP Pro.
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Block IP address Pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/block-ip-address-pro/)
>
> ---


## 1. Requisiti

Ban IP Pro gira dentro PrestaShop. Non ha bisogno di un altro modulo.

Le etichette del modulo a schermo sono in inglese. In questo manuale compaiono come si vedono nel back office.

- PrestaShop dalla 1.7.1.0 fino a PrestaShop 9.
- PHP 7.1 o più recente, e almeno la versione di PHP richiesta da quella versione di PrestaShop. L'installazione si ferma con PHP più vecchio di 7.1.
- Il riconoscimento del paese e il blocco per paese richiedono PHP 7.2 o più recente e un file paesi MaxMind che carica Lei. I ban, la lista dei permessi, il controllo degli accessi e il limite di richieste funzionano senza quel file, anche su PHP 7.1.
- Non serve alcuna estensione PHP in più. Il controllo degli aggiornamenti usa cURL quando il server ce l'ha. Senza cURL, il controllo legge l'indirizzo solo se il server consente le letture remote.
- Non serve nessun altro modulo. Un account MaxMind serve solo se vuole il file dei paesi. Il modulo non scarica quel file.
- Un import accetta fino a 5000 righe e un file fino a 2 MB. Un elenco lungo di regole viene letto da un file di cache a ogni visita, quindi un elenco molto lungo ingrandisce quel file. Dopo un import grande usi **Rebuild cache** in **Tools** se i contatori sembrano vecchi.

## 2. Installazione

1. Nel back office apra **Moduli**, poi **Gestione moduli**.
2. Carichi lo zip del modulo e faccia clic su **Installa**.
3. Apra **Configura** su **Ban IP pro**. La pagina si apre su **Dashboard**. La barra ha anche **Statistics**, **Behavior**, **Automation**, **Network**, **Tools** e **Updates**.
4. Il menu a sinistra guadagna **Ban IP** sotto **Parametri avanzati**. Quella pagina è l'elenco delle regole. **Manage rules** nella pagina del modulo porta allo stesso elenco.

L'installazione scrive una cache delle regole vuota. Non svuota la cache di PrestaShop. Se la voce di menu manca dopo un aggiornamento, apra **Configura** una volta. La pagina aggiorna le tabelle del modulo. Se l'aggiornamento fallisce, la pagina mostra **The module database could not be updated.**

Per spegnere il modulo usi l'interruttore in **Gestione moduli**. I controlli si fermano. Regole, registri e impostazioni restano. Lo riaccenda e vengono usate le stesse regole. Il modulo non ha un pulsante proprio di accensione o spegnimento.

Per toglierlo, faccia clic su **Disinstalla** e confermi. La disinstallazione toglie la voce **Ban IP** e stacca i controlli. Le regole, il registro dei blocchi, i totali giornalieri, i contatori degli accessi falliti, l'elenco delle azioni del personale e le impostazioni restano nel database. Il file dei paesi caricato resta nella cartella del modulo. Una nuova installazione conserva quelle regole e riempie solo le impostazioni ancora vuote.

## 3. Configurazione e lavoro quotidiano

Un visitatore apre il negozio. Prima che la pagina venga costruita, il modulo legge il suo IP. Una regola Allow vince su un ban. Se un ban corrisponde al negozio, se il paese del visitatore è nell'elenco, se il visitatore ha aperto un percorso sonda, o se l'indirizzo ha superato il limite di richieste, il visitatore vede la pagina di blocco o il reindirizzamento che ha impostato. Il blocco viene scritto nel registro. Il lavoro del personale inizia su **Dashboard** oppure in **Parametri avanzati**, **Ban IP**. Aggiunge una regola, importa un elenco, oppure lascia che **Automation** crei i ban. Un ban può scadere. Alla prima richiesta di ogni giorno le regole scadute vengono spente e le righe vecchie del registro vengono tolte. Il percorso finisce quando il visitatore è bloccato, reindirizzato o lasciato passare.

Apra **Moduli**, **Gestione moduli**, **Ban IP pro**, **Configura**.

### 3.1 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/banippro-configure-dashboard.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Dashboard**.

**Dashboard** è la prima scheda. **Manage rules** apre l'elenco delle regole.

I sette contatori mostrano solo numeri. Non salvano alcuna impostazione.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Manage rules** | un pulsante | Apre **Ban IP** sotto **Parametri avanzati**. |
| **Active bans** | 0 | Regole di ban ancora accese. Le regole Allow non entrano in questo numero. |
| **Blocked today** | 0 | Richieste bloccate da mezzanotte, dai totali giornalieri. |
| **Blocked in 7 days** | 0 | Richieste bloccate negli ultimi 7 giorni, oggi compreso. |
| **Blocked in 30 days** | 0 | Richieste bloccate negli ultimi 30 giorni, oggi compreso. |
| **Unique IPs today** | 0 | Indirizzi IP distinti nel registro di oggi. |
| **Expiring in 48 hours** | 0 | Ban attivi la cui fine cade nelle prossime 48 ore. |
| **Active automatic bans** | 0 | Ban attivi per un accesso fallito, un percorso sonda o il limite di richieste. |

**Blocked requests** è un grafico degli ultimi 30 giorni. Legge i totali giornalieri. Non salva nulla.

**Recent blocks** elenca le ultime richieste bloccate: data, indirizzo IP, paese, percorso e motivo. Il paese resta vuoto finché non carica il file dei paesi in **Network**. Un elenco vuoto dice **No blocked requests yet.**

**Your current IP** mostra l'indirizzo che vede questo back office. **Add to allow list** salva quell'indirizzo come regola Allow per il negozio e il back office. La pagina dice allora **Your current IP address is on the allow list.** Se l'indirizzo non si può leggere, la pagina dice **Your current IP address could not be detected.** Se la riga non si può salvare, dice **The address could not be added to the allow list.**

**Module status** mostra quattro righe.

| Riga | All'inizio | Cosa fa |
|---|---|---|
| **Front hook** | **Registered** dopo un'installazione normale | **Registered** significa che il negozio esegue il controllo. **Missing** significa che il controllo non è agganciato. Reinstalli il modulo oppure apra **Configura** dopo un aggiornamento. |
| **Cached rules** | 0 | Quante regole attive la cache ha accettato. |
| **Unreadable rules** | 0 | Righe attive che la cache non ha potuto leggere come indirizzo. |
| PHP e PrestaShop | le versioni di questo server | Per confrontarle con i requisiti. |

**Quick ban** scrive un ban. L'ambito è quello di **Default scope of new bans** in **Behavior**. Un ban aggiunto qui non invia l'email di avviso.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **IP address** | vuoto | Un indirizzo, uno schema come `192.168.1.*`, una rete come `10.0.0.0/8`, oppure un intervallo come `192.168.1.10-192.168.1.20`. |
| **Reason** | **Manual** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback** o **Competitor**. Le statistiche usano questa etichetta. |
| **Duration** | **Permanent** | **1 hour**, **24 hours**, **7 days**, **30 days**, oppure **Permanent** finché non cancella la regola. |
| **Comment** | vuoto | Una nota privata. Il visitatore non la vede. |
| **I confirm blocking my own IP** | spento | Serve solo quando il ban corrisponderebbe all'IP con cui è nel back office e l'ambito include il back office. |
| **Ban this address** | un pulsante | Salva il ban e mostra **The address was banned.** |

**Test an address** non crea e non cancella alcuna regola.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **IP address** | vuoto | L'indirizzo che vuole controllare. |
| **Test** | un pulsante | Mostra il risultato del negozio, quello del back office e il paese. |
| **Front office** | nascosto fino alla prova | **No matching rule.**, **Allowed by rule #…** oppure **Blocked by rule #…**. |
| **Back office** | nascosto fino alla prova | Gli stessi tre risultati per il pannello. |
| Nota sotto la riga del pannello | quando la protezione è spenta | **Back office protection is disabled, so back-office bans are not enforced.** |
| **Country** | **Unknown** se manca il file | Il codice paese, più **Blocked by country rule** quando quel paese è nell'elenco. |

**Recent admin actions** elenca le ultime azioni del personale, per esempio creazione, import, permesso, sblocco e ricostruzione della cache. Un elenco vuoto dice **No admin actions yet.**

### 3.2 Statistics

![Statistics](https://mypresta.eu/docs/images/docs/banippro-configure-stats.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Statistics**.

**Statistics** legge il registro dei blocchi. **24h**, **7 days** e **30 days** ricaricano la pagina per quel periodo. Alla prima apertura il periodo è **30 days**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **24h** | un pulsante | Ultime 24 ore. Il grafico ha un punto per ora. |
| **7 days** | un pulsante | Ultimi 7 giorni, oggi compreso. Un punto per giorno. |
| **30 days** | un pulsante, scelto all'inizio | Ultimi 30 giorni, oggi compreso. |
| **Export CSV** | un pulsante | Scarica `banippro-hits.csv` per il periodo a schermo. Non cambia le regole. |
| **From** | il primo giorno del periodo aperto | Si usa con **To** e **Apply**. |
| **To** | oggi | Si usa con **From** e **Apply**. Se **From** è successivo a **To**, i due giorni si scambiano. |
| **Apply** | un pulsante | Ricarica la scheda per quei giorni. Non salva alcuna impostazione. |
| **Blocked requests** | 0 | Quanti blocchi cadono nel periodo. |
| **Unique IPs** | 0 | Quanti indirizzi distinti sono stati bloccati nel periodo. |

Il grafico **Blocked requests** segue i pulsanti sopra. Sotto:

| Blocco | Cosa mostra |
|---|---|
| **Top IP addresses** | Un grafico a barre dei 10 indirizzi con più blocchi nel periodo. |
| **Top paths** | I 10 percorsi bloccati più spesso, con un conteggio. |
| **Top reasons** | I 10 motivi delle regole corrispondenti, con un conteggio. |
| **Top countries** | I 10 codici paese, con un conteggio. Vuoto finché il file dei paesi non è caricato. |
| **Block log** | Data, indirizzo IP, paese, percorso, indirizzo della regola e motivo. Fino a 100 righe. |

Un dettaglio vuoto dice **No data for this period.** Un registro vuoto dice **No blocked requests in this period.**

I totali giornalieri dietro il grafico della dashboard restano quando accorcia **Keep logs for days**. Quell'impostazione cancella il registro riga per riga e l'elenco delle azioni del personale. Non cancella i totali giornalieri.

### 3.3 Behavior

![Behavior](https://mypresta.eu/docs/images/docs/banippro-configure-behavior.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Behavior**.

Faccia clic su **Save**. La pagina mostra **Settings updated**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Message for blocked visitors** | **You are blocked** in inglese. I negozi in polacco, spagnolo e portoghese ricevono anche una frase in quella lingua. Ogni altra lingua riceve la frase inglese. | Il testo della pagina di blocco. Lo compili in ogni lingua del negozio. Il visitatore vede la frase della lingua della pagina. |
| **Redirect blocked visitors** | **No** | **Yes** manda i visitatori bloccati a **Redirect URL** al posto del messaggio. **No** tiene la pagina di blocco. |
| **Redirect URL** | vuoto | Un link `http` o `https` completo. Viene ignorato finché l'interruttore sopra è **No**. Un link sbagliato riporta l'interruttore su **No** e mostra **Enter a valid http or https URL for the redirect.** |
| **Default scope of new bans** | **Front office** | Lo usano **Quick ban** e **Import** quando quelle schermate non chiedono l'ambito. **Front office** è il negozio. **Back office** è questo pannello. **Front office and back office** è entrambi. |
| **Protect the back office** | **No** | **Yes** applica i ban anche in questo pannello. Il salvataggio rifiuta **Yes** finché il Suo IP attuale non è nella lista dei permessi, e mostra **Add your current IP to the allow list before you protect the back office.** L'interruttore resta **No**. |

Il modulo mostra anche questo avviso: **Back office protection stays off until your current IP is on the allow list. Rules still apply to the shop front by default.**

### 3.4 Automation

![Automation](https://mypresta.eu/docs/images/docs/banippro-configure-automation.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Automation**.

Faccia clic su **Save**. La pagina mostra **Settings updated**. I ban automatici valgono per il negozio, in ogni negozio dell'installazione. Non accendono **Protect the back office**. Un indirizzo che corrisponde già a una regola Allow non viene bannato. Un indirizzo che ha già un ban attivo resta com'è.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Block known probe paths** | **Yes** | **Yes** banna un visitatore del negozio che apre un percorso dell'elenco sotto. La cartella di amministrazione non viene mai bannata in questo modo. **No** ferma questo controllo. |
| **Probe ban length in hours** | 24 | Quanto dura quel ban. 24 è un giorno. 0 lo tiene finché non lo cancella. |
| **Probe paths** | `/.env`, `/wp-login.php`, `/wp-admin`, `/xmlrpc.php`, `/vendor/phpunit`, `/phpmyadmin`, `/.git/`, `/boaform`, `/cgi-bin/`, uno per riga | Una richiesta il cui percorso contiene una di queste righe viene bannata subito. Un elenco vuoto viene sostituito con questo elenco predefinito al salvataggio. Una riga che è solo `/`, e una riga che è la cartella di amministrazione, vengono scartate. |
| **Ban customers after failed logins** | **No** | **Yes** conta le password cliente sbagliate. Un accesso cliente riuscito azzera il contatore. |
| **Ban employees after failed logins** | **No** | Lo stesso conteggio per l'accesso del dipendente. Metta il proprio IP nella lista dei permessi prima di accenderlo. Il ban vale per il negozio, non per il pannello, salvo che quell'IP sia coperto anche da un ban il cui ambito include il back office. |
| **Failed logins before a ban** | 5 | Con 5, il successivo accesso fallito dentro la finestra crea il ban. Il valore salvato più piccolo è 1. |
| **Failed login window in minutes** | 15 | I fallimenti più vecchi di questo vengono dimenticati. Il valore salvato più piccolo è 1. |
| **Login ban length in hours** | 24 | Quanto dura il ban per l'accesso. 0 lo tiene finché non lo cancella. |
| **Limit requests per IP** | **No** | **Yes** conta le richieste di pagine del negozio. Le immagini e gli altri file che non entrano mai in PrestaShop non vengono contati. Lo lasci su **No** con il traffico normale. In un negozio affollato un limite basso banna clienti veri. |
| **Requests allowed in the window** | 120 | Quante richieste di pagina un IP può fare durante la finestra. Il valore salvato più piccolo è 1. |
| **Rate limit window in minutes** | 1 | Durata di quella finestra. 1 significa che il limite sopra si conta al minuto. |
| **Rate limit ban in minutes** | 15 | Quanti minuti dura il ban dopo il superamento. Il valore salvato più piccolo è 1. |
| **Email me when an automatic ban is created** | **No** | **Yes** invia un'email quando il modulo crea un ban. I ban aggiunti a mano non la inviano. Al massimo un'email all'ora. |
| **Alert email** | vuoto | La casella che riceve l'avviso. La lasci vuota per usare l'email del negozio. Un valore che non è un'email viene cancellato e la pagina mostra **Enter a valid alert email address.** |

L'oggetto della mail è **Ban IP Pro alert**. Il messaggio indica l'IP, il motivo (`auto-login`, `auto-honeypot` o `auto-rate`), l'ora di fine o la parola `permanent`, e il nome del negozio.

### 3.5 Network

![Network](https://mypresta.eu/docs/images/docs/banippro-configure-network.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Network**.

Faccia clic su **Save**. La pagina mostra **Settings updated**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Trust Cloudflare** | **No** | Lo accenda solo quando il dominio del negozio passa da Cloudflare. Il modulo legge allora l'IP del visitatore da Cloudflare, e solo se la connessione arriva davvero da Cloudflare. Lo lasci su **No** se non è sicuro, altrimenti ogni visitatore può sembrare il proxy. |
| **Trusted reverse proxies** | vuoto | Se un proxy o un bilanciatore sta davanti al negozio, metta qui il suo IP o la sua rete, uno per riga. Il modulo legge l'IP del visitatore solo da quel proxy. Lo lasci vuoto se non è sicuro. |
| **Block selected countries** | **No** | **Yes** blocca ogni visitatore il cui paese è nell'elenco sotto. Inizia a funzionare dopo il caricamento del database dei paesi. Non metta il proprio paese. Un blocco per paese non aggiunge una riga in **Ban IP**. Blocca quella richiesta e scrive una riga di registro con il motivo **Country**. |
| **Country codes** | vuoto | Codici di due lettere, per esempio `PL`, `DE` o `US`. Li separi con virgole, spazi o a capo. Tutto ciò che non ha due lettere viene scartato. |
| **Keep logs for days** | 90 | Per quanti giorni restano la storia dei blocchi e l'elenco delle azioni del personale. Le righe più vecchie vengono tolte alla prima richiesta di un giorno successivo. Il valore salvato più piccolo è 1. I valori sopra 3650 vengono salvati come 3650. |
| **GeoLite2 country database** | nessun file | Facoltativo. Scelga un file il cui nome finisce con `.mmdb`. Dopo **Save** le statistiche possono mostrare il paese e il blocco per paese può funzionare. Il resto del modulo non ha bisogno di questo file. |

Sopra il campo file la pagina mostra una di queste righe:

| Cosa vede | Cosa fare |
|---|---|
| **GeoIP database is ready.** | Niente. Il riconoscimento del paese funziona. |
| **Country lookup needs PHP 7.2 or newer. The rest of the module keeps working.** | I ban continuano. Le statistiche per paese e i blocchi per paese restano spenti finché PHP non è 7.2 o più recente. |
| **Upload GeoLite2-Country.mmdb to enable country statistics and country blocks. MaxMind distributes that file.** | Carichi il file e faccia clic su **Save**. |

Un file sbagliato mostra **Upload a GeoLite2 Country file that ends with .mmdb.** Se il file non si può salvare, la pagina mostra **The GeoIP database could not be saved.** Un caricamento riuscito mostra **The GeoIP database was uploaded.**

### 3.6 Tools

![Tools](https://mypresta.eu/docs/images/docs/banippro-configure-tools.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Tools**.

**Import rules** crea ban. L'ambito è **Default scope of new bans**. Ogni riga nuova è attiva, permanente e usa il motivo **Manual**, salvo che la riga dica altro.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Addresses** | vuoto, con un esempio nel segnaposto | Un indirizzo per riga. Una riga CSV può essere indirizzo, commento, motivo. Le righe che iniziano con `#` vengono ignorate. Un indirizzo che esiste già viene saltato. |
| **File** | vuoto | Un file di testo. Le sue righe si aggiungono al riquadro sopra. Un file più grande di 2 MB mostra **The import file is larger than 2 MB.** e non viene importato nulla. |
| **Import** | un pulsante | Crea i ban e mostra **%d rules were imported.** Le righe saltate mostrano anche **%d lines were skipped.** L'import si ferma dopo 5000 righe. |
| **Export rules CSV** | un pulsante | Scarica `banippro-rules.csv` per ogni regola. Non cambia l'elenco. |

**Web server snippet** mostra due riquadri, Apache 2.4 e nginx. L'intestazione dice quanti indirizzi sono stati esportati. Entrano solo i ban attivi e permanenti che sono un IP singolo o una rete. Uno schema come `192.168.1.*` viene scritto come rete. Gli intervalli e i ban temporanei restano fuori. **Copy** copia il riquadro. Il modulo non modifica i file del server. Incolla Lei il testo nella configurazione del server. Se non c'è nulla da esportare, entrambi i riquadri lo dicono.

**Emergency unlock** mostra un indirizzo. Lo apra da un browser che è bloccato. Il modulo aggiunge l'IP di quel browser alla lista dei permessi, per il negozio e il back office, e lascia passare quella richiesta.

| Pulsante | Cosa fa |
|---|---|
| **Copy** | Copia l'indirizzo di sblocco. La chiave resta la stessa. |
| **Create a new key** | Sostituisce la chiave. La pagina dice **A new emergency key was created. The previous unlock link no longer works.** |
| **Rebuild cache** | Riscrive la cache delle regole dall'elenco attuale. La pagina dice **The rule cache was rebuilt.** |

Tenga l'indirizzo di sblocco fuori dal negozio. Chi lo apre entra nella lista dei permessi.

### 3.7 Updates

![Updates](https://mypresta.eu/docs/images/docs/banippro-configure-updates.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Updates**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Check now** | un pulsante | Chiede a MyPresta se esiste una versione più nuova. **New version available!** oppure **Module is up to date!** Il negozio non fa mai questa chiamata. |
| **Updates notifications** | **Disable** | **Enable** fa lo stesso controllo quando apre questa scheda, al massimo una volta ogni tre giorni. Una versione più nuova mostra anche un avviso nella pagina del modulo: **New version available, check MyPresta.eu for more informations**, con **More details in changelog**. |
| **Save** | un pulsante | Salva **Enable** o **Disable**. Non scarica un file. La pagina dice **Settings updated**. |

Il link sotto il modulo apre la pagina del modulo su mypresta.eu, dove è pubblicato il changelog. Questo manuale non elenca le versioni.

### 3.8 Ban IP, l'elenco delle regole

![Ban IP, l'elenco delle regole](https://mypresta.eu/docs/images/docs/banippro-rules-list.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Ban IP, l'elenco delle regole**.

Apra **Parametri avanzati**, **Ban IP**, oppure **Manage rules** su **Dashboard**. La riga sopra l'elenco dice che dashboard, statistiche e automazione sono nella pagina di configurazione del modulo, e offre **Open dashboard**.

**Add new** apre una regola vuota. Su una regola nuova può incollare più indirizzi, uno per riga. Condividono commento, motivo, tipo di regola, ambito, scadenza, flag attivo e negozio.

Le colonne sono **ID**, **IP address**, **Match**, **Rule**, **Scope**, **Hits**, **Last hit**, **Expires**, **Reason** e **Active**. Quando il negozio usa più di un negozio, si aggiunge **Shop**.

| Colonna | Cosa vede |
|---|---|
| **Match** | **Exact**, **Wildcard**, **CIDR** o **Range**. |
| **Rule** | **Ban** o **Allow**. |
| **Scope** | **Front office**, **Back office**, oppure **Front office and back office**. |
| **Hits** | Quante richieste bloccate sono state registrate per questa regola. |
| **Last hit** | Data dell'ultima. |
| **Expires** | Una data e un'ora, oppure **Permanent**. |
| **Reason** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback**, **Competitor**, **Auto ban (login)**, **Auto ban (probe)**, **Auto ban (rate limit)** o **Country**. |
| **Active** | L'icona di stato. Un clic accende o spegne la riga. Una regola inattiva resta nell'elenco e non corrisponde a nessuno. |
| **Shop** | **All shops**, oppure il nome di un negozio. Visibile solo con multinegozio. |

Usi la riga dei filtri per cercare. Filtrare non blocca e non permette nessuno.

Azioni di riga:

| Azione | Cosa fa |
|---|---|
| **Edit** | Apre la regola. Su una riga esistente si può salvare un solo indirizzo. |
| **Whitelist** | Visibile su un ban. Cambia quella riga in **Allow** e ricostruisce la cache. Nascosto su una riga che è già **Allow**. |
| **Delete** | Toglie la riga e ricostruisce la cache. |

Azioni di massa, dopo aver spuntato le righe:

| Azione | Cosa fa |
|---|---|
| **Enable selection** | Accende le righe spuntate e ricostruisce la cache. |
| **Disable selection** | Spegne le righe spuntate e ricostruisce la cache. Restano nell'elenco. |
| **Delete selected** | Chiede **Delete selected items?** e poi toglie le righe spuntate e ricostruisce la cache. |

Una regola Allow viene controllata prima dei ban. Una regola Allow che corrisponde lascia passare il visitatore anche quando un ban corrisponderebbe. 

Una regola la cui ora di fine è passata smette di corrispondere subito. Alla prima richiesta del giorno dopo viene anche messa inattiva.

### 3.9 Il modulo della regola

![Il modulo della regola](https://mypresta.eu/docs/images/docs/banippro-rule-form.webp)

La schermata è in inglese. In questo manuale questa parte si chiama **Il modulo della regola**.

**Save** scrive la regola, ricostruisce la cache e torna all'elenco quando ogni riga è valida.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **IP address** | vuoto | Su una regola nuova, un indirizzo per riga. In modifica, un indirizzo. Un IP singolo, uno schema come `192.168.1.*`, una rete come `10.0.0.0/8`, oppure un intervallo come `192.168.1.10-192.168.1.20`. Gli schemi sono IPv4 e gli asterischi devono stare in fondo. IPv6 vale per un indirizzo singolo, una rete e un intervallo. |
| **Comment** | vuoto | Una nota privata che vede solo Lei in questo elenco. I visitatori non la vedono. |
| **Reason** | **Manual** | Perché questo indirizzo è in elenco. Le statistiche lo usano per distinguere un ban manuale da uno automatico. I motivi automatici non sono in questo menu. Il modulo li scrive da solo. |
| **Rule** | **Ban** | **Ban** blocca l'indirizzo. **Allow** lo lascia sempre passare, anche quando un'altra regola lo bloccherebbe. |
| **Scope** | il valore di **Default scope of new bans** | **Front office** è ciò che vedono i clienti. **Back office** è questo pannello. **Front office and back office** significa che la regola vale nel negozio e nel pannello. |
| **Expires at** | vuoto | Lo lasci vuoto per tenere la regola finché non la cancella. Oppure scriva data e ora in cui deve fermarsi, per esempio `2026-12-31 18:00`. Un valore sbagliato mostra **The expiry date is not valid.** |
| **Active** | **Yes** | **No** lascia la regola nell'elenco, ma non blocca e non permette nessuno. |
| **I confirm blocking my own IP** | **No** | La riga di aiuto mostra il Suo IP attuale, oppure **unknown**. La conferma serve quando un ban corrisponderebbe a questo IP nel back office. |
| **Shop** | **All shops** | Visibile solo con multinegozio. **All shops** significa che la regola vale in ogni negozio di questa installazione. Scelga un negozio per limitare la regola a quello. |
| **Save** | un pulsante | Salva le righe. |

Un campo vuoto mostra **Enter an IP address.** Uno schema che corrisponderebbe a ogni indirizzo, come `*.*.*.*` o una rete con prefisso `0`, mostra **This rule would block every address.** Un indirizzo sbagliato mostra **This IP address or range is not valid.** Una seconda regola attiva con lo stesso indirizzo e lo stesso tipo ban o permesso mostra **This rule already exists.** Un ban che corrisponde al Suo IP attuale nel back office, senza l'interruttore di conferma, mostra **This ban matches your current IP in the back office. Confirm it before saving.** Più di una riga in modifica mostra **Edit one address at a time.** Una riga sbagliata su una regola nuova viene saltata con **Line … was skipped:** e il motivo. Una riga doppia viene saltata con **Line was skipped because it already exists:** e l'indirizzo. Quando alcune righe sono state salvate e altre no, la pagina mostra anche **%d rules were saved.** e resta nel modulo. Se la riga non si può scrivere, la pagina mostra **The rule could not be saved.** Una riga assente mostra **Rule not found.**

## 4. Vetrina del negozio

Il tema non stampa un blocco, un badge o un widget di questo modulo. Su una pagina prodotto, carrello o home normale non c'è nulla da fotografare.

Un visitatore che non è bloccato vede il negozio come al solito. Un visitatore bloccato vede una pagina semplice: il logo del negozio quando il negozio ne ha uno, il titolo 403, il **Message for blocked visitors** nella lingua della pagina e l'IP del visitatore. La pagina chiede ai motori di non indicizzarla. Se **Redirect blocked visitors** è **Yes** e **Redirect URL** è un link `http` o `https` valido, il visitatore va a quell'indirizzo e non vede il messaggio.

La stessa pagina di blocco viene usata nel back office quando **Protect the back office** è **Yes** e l'IP del dipendente corrisponde lì a un ban e non corrisponde a una regola Allow.

Questi controlli girano solo sulle richieste che entrano in PrestaShop. I file serviti direttamente dal server web, come le immagini, non vengono controllati e non vengono contati da **Limit requests per IP**.

Non c'è una pagina account del cliente né un modulo di ricorso. Il visitatore passa, vede la pagina di blocco, oppure finisce sul reindirizzamento.

| Cosa vede il visitatore | Cosa fa Lei |
|---|---|
| Il negozio, come al solito | Nessun ban corrisponde, oppure ha corrisposto una regola Allow. |
| La pagina di blocco con il Suo messaggio e il suo IP | Ha corrisposto un ban, il paese è bloccato, è stato aperto un percorso sonda, oppure è stato superato il limite di richieste. Il reindirizzamento è **No**. |
| Un altro sito, senza messaggio | Il reindirizzamento è **Yes** e l'URL è valido. |
| Il back office, come al solito | **Protect the back office** è **No**, oppure questo IP è nella lista dei permessi. |

## 5. Problemi

**La pagina del modulo dice Ban IP Pro requires PHP 7.1 or newer.**  
Il server è su PHP più vecchio di 7.1. L'installazione viene rifiutata e **Configura** mostra solo quella frase. Passi il negozio a PHP 7.1 o più recente e installi di nuovo.

**Configura dice The module database could not be updated.**  
Le tabelle non si sono potute creare o aggiornare. Chieda all'hosting di permettere all'utente del database di creare e modificare le tabelle, poi apra di nuovo **Configura**.

**Front hook dice Missing.**  
Il controllo non è agganciato. Reinstalli il modulo, oppure lo spenga e lo riaccenda da **Gestione moduli**. Le regole esistenti restano.

**Il salvataggio in Behavior rifiuta Protect the back office.**  
La pagina dice **Add your current IP to the allow list before you protect the back office.** Su **Dashboard** faccia clic su **Add to allow list**, poi metta l'interruttore su **Yes** e salvi di nuovo.

**Si è chiuso fuori dal back office.**  
Apra l'indirizzo di emergenza da **Tools**, **Emergency unlock**, in un browser che raggiunge ancora il negozio. L'IP di quel browser viene aggiunto alla lista dei permessi e la richiesta passa. Se non può aprire **Tools**, usi una copia dell'indirizzo che aveva salvato prima. **Create a new key** rende inutile il vecchio indirizzo, quindi aggiorni la copia dopo averlo usato.

**Un ban del proprio IP viene rifiutato.**  
La pagina dice **This ban matches your current IP in the back office. Confirm it before saving.** Accenda **I confirm blocking my own IP**, oppure cambi l'ambito in **Front office** se vuole bloccare quell'IP solo nel negozio.

**L'import dice The import file is larger than 2 MB.**  
Divida il file. Ogni import si ferma dopo 5000 righe e allora mostra che l'import si è fermato. Passi il resto in un altro import. Le righe saltate mostrano **%d lines were skipped.** Gli indirizzi già presenti vengono saltati di proposito.

**L'indirizzo è stato salvato, ma il negozio lo lascia ancora passare.**  
Controlli **Active**, **Scope** e **Expires at**. Una regola del back office non tocca il negozio. Una regola Allow per quell'IP vince. Su **Dashboard** usi **Test an address**. Poi faccia clic su **Rebuild cache** in **Tools**.

**I ban del back office non fanno nulla.**  
**Test an address** aggiunge **Back office protection is disabled, so back-office bans are not enforced.** Accenda **Protect the back office** in **Behavior** dopo che il Suo IP è nella lista dei permessi.

**Il blocco per paese non fa nulla.**  
**Block selected countries** deve essere **Yes**, i codici devono essere di due lettere e la pagina deve dire **GeoIP database is ready.** Su PHP più vecchio di 7.2 la pagina dice che il riconoscimento del paese richiede PHP 7.2 o più recente. Non metta il proprio paese nell'elenco.

**I clienti vengono bannati durante una vendita normale.**  
**Limit requests per IP** è acceso e il limite è basso per questo negozio. Lo metta su **No**, oppure alzi **Requests allowed in the window**. Cancelli i ban automatici in **Ban IP**. Il loro motivo è **Auto ban (rate limit)**.

**Un accesso fallito del dipendente non ha bloccato il back office.**  
Quel ban automatico vale per il negozio. Il pannello viene bloccato solo quando **Protect the back office** è **Yes** e un ban il cui ambito include il back office corrisponde a quell'IP.

**L'email di avviso non arriva mai.**  
**Email me when an automatic ban is created** deve essere **Yes**. I ban manuali non inviano posta. Un secondo ban automatico nella stessa ora non invia un'altra mail. La casella è **Alert email**, oppure l'email del negozio quando il campo è vuoto. Il negozio deve già saper inviare la posta.

**Il grafico mostra ancora giorni vecchi dopo che ha accorciato il registro.**  
**Keep logs for days** toglie il registro riga per riga e le azioni del personale. I totali giornalieri usati dal grafico della dashboard restano.

**New version available, check MyPresta.eu for more informations.**  
Apra **Updates** e usi il link, oppure faccia clic su **Check now**. Questo manuale non elenca le modifiche.

## 6. Per lo sviluppatore

### 6.1 Panoramica

Nome tecnico `banippro`, versione 2.0.0, classe `banippro`, nome in elenco **Ban IP pro**, autore MyPresta.eu, scheda `administration`. Pagina del prodotto: `https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html`.

`actionDispatcherBefore` chiama `BanIpGuard::protect()`. Il guard risolve l'IP, applica lo sblocco di emergenza, poi `BanIpMatcher::decide()` sulla cache di `cache/rules.php`. Allow vince su ban. Il blocco per paese, i ban sonda e il limite di richieste girano sul negozio. Un blocco registra un hit e o reindirizza o rende `blocked.tpl` con stato 403 e termina la richiesta. `actionDispatcherAfter` esegue `BanIpAutoBan::evaluate()` per un accesso armato prima. Le impostazioni sono valori di configurazione globali letti da `BanIpInstaller`. Il controller di menu `AdminBanIpPro` modifica la tabella `ban`.

Non c'è un override di `enable()` né di `disable()`. Lo spegnimento di PrestaShop stacca gli hook, quindi il guard non gira. I dati restano.

### 6.2 File

| File | Ruolo |
|---|---|
| `banippro.php` | Installazione, hook, schede, ban rapido, import, prova. |
| `controllers/admin/AdminBanIpProController.php` | Elenco, modulo, export CSV, azione di whitelist. |
| `models/banip.php` | Modello di `ban`, più `storeRule()` e `importLines()`. |
| `classes/BanIpGuard.php` | Controllo della richiesta, pagina di blocco, manutenzione giornaliera. |
| `classes/BanIpMatcher.php` | Analisi exact, wildcard, CIDR e range. Decide allow e poi ban. |
| `classes/BanIpClientIp.php` | Indirizzo remoto, Cloudflare, proxy fidati. |
| `classes/BanIpCache.php` | Costruisce e include `cache/rules.php`. |
| `classes/BanIpAutoBan.php` | Sonda, accesso fallito, limite, email di avviso. |
| `classes/BanIpStats.php` | Dashboard, report, CSV, frammenti server. |
| `classes/BanIpGeo.php` | Legge `geo/GeoLite2-Country.mmdb` senza la libreria MaxMind. |
| `classes/BanIpInstaller.php` | Tabelle e configurazione predefinita. |
| `classes/BanIpUpdate.php` | Controllo versione verso `dev.mypresta.eu`. |
| `views/templates/admin/*.tpl` | Dashboard, statistiche, strumenti, guscio. |
| `views/templates/front/blocked.tpl` | Pagina di blocco. |
| `views/js/dashboard.js` | Grafici e pulsanti di copia. |
| `mails/en/banippro_alert.txt`, `mails/pl/banippro_alert.txt` | Corpi dell'avviso. L'oggetto è fisso in `BanIpAutoBan::alert()`. |
| `upgrade/upgrade-2.0.0.php` | Esegue `BanIpInstaller::upgrade()`, sostituisce i vecchi hook con il set 2.0.0 e ricostruisce la cache. |
| `lib/searchTool/` | Caricato nella pagina di configurazione. Nessun campo di configurazione lo chiama. |
| `tests/matcher_test.php` | Controlli CLI del matcher. |

### 6.3 Controller

`AdminBanIpPro` estende `ModuleAdminController`. La scheda padre è `AdminAdvancedParameters`. Nome classe `AdminBanIpPro`. Tabella `ban`, identificatore `id_ban`, oggetto `banip`.

I filtri dell'elenco usano i nomi abituali dell'helper (`banFilter_ip` e gli altri campi). Azioni di riga: modifica, `displayWhitelistLink` (`banippro_whitelist`), cancellazione. Azioni di massa: delete, enable, disable. `exportHits` invia il CSV degli hit. `exportRules` invia il CSV delle regole.

Non c'è un controller di vetrina. La risposta di blocco viene resa nell'hook del dispatcher e la richiesta termina.

`?banippro_unlock=` è letto da `BanIpGuard::tryUnlock()`. Il valore deve corrispondere a `banippro_emergency_key` con `hash_equals`. Una corrispondenza chiama `BanIpAutoBan::ensureAllow()` con ambito negozio e back office (`apply_to` 3, `id_shop` 0) e registra l'audit `unlock`.

### 6.4 Hook

Registrati in installazione:

| Hook | Chiamata |
|---|---|
| `actionDispatcherBefore` | `BanIpGuard::protect()`. |
| `actionDispatcherAfter` | `BanIpAutoBan::evaluate()`. Registrato anche dopo il controllo principale di installazione. |
| `actionFrontControllerSetMedia` | `BanIpAutoBan::arm('customer')`. |
| `actionAuthentication` | `BanIpAutoBan::markSuccess('customer')`. |
| `actionAdminControllerInitAfter` | `BanIpAutoBan::arm('employee')`. |

`upgrade-2.0.0.php` deregistra `header`, `displayHeader`, `home`, `displayHome`, `actionFrontControllerAfterInit` e `actionAdminControllerSetMedia`.

Il modulo non espone un hook proprio. L'armamento dell'accesso cerca `submitLogin` nella richiesta. Un accesso cliente riuscito azzera il contatore dei fallimenti del cliente. Il successo del dipendente si rileva quando il dipendente è connesso in `evaluate()`.

### 6.5 Override

Il modulo non sovrascrive alcuna classe o controller di PrestaShop.

### 6.6 Database

La disinstallazione non elimina queste tabelle e non elimina le chiavi di configurazione. `BanIpInstaller::ensure()` aggiunge le colonne mancanti di `{prefix}ban` all'apertura di **Configura**, quindi una vecchia tabella `ban` resta e viene estesa. Una reinstallazione non svuota le righe.

| Tabella | Contenuto |
|---|---|
| `{prefix}ban` | `id_ban`, `ip`, `ip_end`, `match_type` (`exact`, `wildcard`, `cidr`, `range`), `rule_type` (1 ban, 2 allow), `apply_to` (1 vetrina, 2 back office, 3 entrambi), `views`, `comment`, `reason`, `active`, `date_add`, `date_upd`, `date_end`, `last_hit`, `id_employee`, `id_shop` (0 significa tutti i negozi), `range_start`, `range_end`. |
| `{prefix}banippro_hit` | Una riga per blocco: `id_ban`, `ip`, `request_uri`, `user_agent`, `country_iso`, `id_shop`, `date_add`. |
| `{prefix}banippro_daily` | `day`, `id_shop`, `blocked`, `auto_banned`. Non viene cancellata quando i registri vengono potati. |
| `{prefix}banippro_fail` | `ip`, `context` (`customer`, `employee`, `rate`), `hits`, `window_start`. |
| `{prefix}banippro_audit` | `id_employee`, `action`, `details`, `date_add`. |

`BanIpGuard::dailyMaintenance()` gira una volta per giorno di calendario. Mette `active` a 0 sulle regole il cui `date_end` è nel passato, ricostruisce la cache se una riga è cambiata, e cancella le righe hit e audit più vecchie di `banippro_log_days`.

### 6.7 Chiavi e traduzioni

Tutte le chiavi sono globali (`id_shop` 0). Una chiave assente ricade sul valore predefinito tra parentesi.

| Chiave | Predefinito |
|---|---|
| `banippro_emergency_key` | 32 caratteri hex da `random_bytes`, oppure OpenSSL, oppure `md5` |
| `banippro_msg` | Per lingua. `en` You are blocked. `pl` Dostęp został zablokowany. `es` El acceso ha sido bloqueado. `pt` e `br` O acesso foi bloqueado. Le altre lingue ricevono la frase inglese. In memorizzazione è consentito l'HTML. |
| `banippro_redirect` | 0 |
| `banippro_url` | vuoto |
| `banippro_default_apply` | 1 |
| `banippro_protect_admin` | 0 |
| `banippro_honeypot` | 1 |
| `banippro_honeypot_hours` | 24 |
| `banippro_honeypot_paths` | `BanIpInstaller::defaultHoneypotPaths()` |
| `banippro_autoban_customer` | 0 |
| `banippro_autoban_employee` | 0 |
| `banippro_autoban_threshold` | 5 |
| `banippro_autoban_window` | 15 |
| `banippro_autoban_hours` | 24 |
| `banippro_ratelimit` | 0 |
| `banippro_ratelimit_max` | 120 |
| `banippro_ratelimit_window` | 1 |
| `banippro_ratelimit_ban_minutes` | 15 |
| `banippro_alert` | 0 |
| `banippro_alert_email` | vuoto |
| `banippro_alert_last` | tempo unix dell'ultima mail di avviso, scritto all'invio |
| `banippro_cloudflare` | 0 |
| `banippro_trusted_proxies` | vuoto |
| `banippro_countries_enabled` | 0 |
| `banippro_countries` | vuoto |
| `banippro_log_days` | 90 |
| `banippro_last_maintenance` | `Y-m-d` dell'ultima manutenzione giornaliera |
| `mypresta_updates` | non viene seminato; il modulo tratta un valore assente come 0 |
| `update_banippro` | 0, poi il tempo unix dell'ultimo controllo |
| `updatev_banippro` | stringa di versione remota dell'ultimo controllo |

`BanIpInstaller::seedConfig()` copia un vecchio `banippro_redirect` e `banippro_url` legati al negozio nelle chiavi globali quando il valore globale è vuoto. Un vecchio `banippro_msg` non vuoto viene copiato in ogni lingua prima delle frasi predefinite.

I testi del back office passano da `$this->l()` / `$this->module->l()`. I file di traduzione stanno in `translations/{iso}.php`. Il messaggio della pagina di blocco è il valore di configurazione, non una chiave di traduzione. L'oggetto della mail `Ban IP Pro alert` è un letterale in `BanIpAutoBan::alert()`. L'aiuto dei campi è il `desc` di ogni input HelperForm in `banippro.php` e `AdminBanIpProController.php`.

I valori automatici di `reason` scritti dal modulo sono `auto-login`, `auto-honeypot` e `auto-rate`. I blocchi per paese registrano `country` e non inseriscono una riga `ban`. `banip::importLines()` si ferma dopo 5000 righe non vuote che non sono un commento. I caricamenti sopra 2097152 byte vengono rifiutati. `BanIpMatcher` rifiuta un valore vuoto, una rete `/0` e un jolly di quattro asterischi (`too_broad`). Un duplicato è una riga attiva con lo stesso IP salvato e lo stesso `rule_type`.

`BanIpAutoBan::ensureBan()` salva sempre `apply_to` 1 e `id_shop` 0. `ensureAllow()` salva `apply_to` 3 e `id_shop` 0.

### 6.8 Estensione

Il tema può sovrascrivere `views/templates/front/blocked.tpl`. Il modulo chiama `$module->fetch('blocked.tpl')`. Le variabili assegnate sono `banippro_message`, `banippro_shop`, `banippro_logo`, `banippro_year`, `banippro_ip` e `banippro_lang`. Se il fetch fallisce, il guard stampa una pagina HTML minima con lo stesso messaggio e termina comunque con stato 403.

Non viene reso alcun template di prodotto, carrello o home. Non c'è un hook con cui il tema aggiunga un widget in vetrina. I template di amministrazione stanno in `views/templates/admin/` e non fanno parte del tema.

## 7. Aiuto

Pagina del modulo: [Ban IP pro](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html).

Acceda al Suo account cliente su [mypresta.eu](https://mypresta.eu), apra il modulo di contatto e scelga **Support for paid modules**. Il modulo indica che per quell'argomento l'accesso è obbligatorio. Dopo l'accesso, scelga questo modulo dalla cronologia degli acquisti.
