---
title: Contact page - spam protection PRO - documentazione e manuale utente
sidebar:
  label: Contact page - spam protection PRO - documentazione e manuale utente
description: Guida alla configurazione e alla risoluzione dei problemi per i negozi che hanno già la protezione antispam della pagina contatti.
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Contact page - spam protection PRO su MyPresta.eu](https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/contact-page-spam-protection-pro/)
>
> ---


## 1. Requisiti

Il modulo funziona su PrestaShop dalla 1.7.7 alla 9. PHP nella versione richiesta da quella versione di PrestaShop. Basta la pagina contatti del negozio. Non serve un altro modulo.

Un account Google reCAPTCHA serve solo per la casella o il punteggio invisibile. Dopo l'installazione l'interruttore reCAPTCHA è attivo, ma il controllo resta spento finché non salva entrambe le chiavi.

Un account CleanTalk serve solo per l'API a pagamento. Il controllo gratuito passa dal proxy MyPresta e non chiede un account CleanTalk. Il CleanTalk gratuito ha bisogno delle funzioni OpenSSL di PHP. Se mancano, quel solo controllo viene saltato e il messaggio passa.

StopForumSpam è una consultazione pubblica. Account e chiave API sono facoltativi. La chiave salvata non viene usata nella consultazione.

Le consultazioni usano cURL quando PHP lo ha. Senza cURL, StopForumSpam, CleanTalk e il controllo aggiornamenti leggono l'indirizzo in modo diretto se il server lo consente. La verifica reCAPTCHA usa cURL quando è disponibile.

## 2. Installazione

Apra **Moduli**, poi **Gestione moduli**. Carichi lo zip e clicchi **Installa**.

Nel menu a sinistra compare **Protezione contatti**. Lo apra per arrivare alla configurazione. Sotto ci sono **Tentativi di invio messaggi** e **Indirizzi IP bannati**.

L'installazione non svuota la cache in un passo separato.

Per spegnerlo usi l'interruttore nella gestione moduli. La pagina contatti non viene più controllata. Impostazioni, tentativi e ban restano. Riaccendendolo, tornano in uso. Le voci di menu sono nascoste finché il modulo è spento.

Per toglierlo clicchi **Disinstalla** e confermi **Sei sicuro di voler disinstallare questo modulo?** La disinstallazione toglie le voci di menu, le impostazioni salvate e le due liste. I file restano sul server finché non cancella il modulo. Una nuova installazione riparte con liste vuote e le impostazioni di un'installazione nuova. I vecchi tentativi e i vecchi ban non tornano.

## 3. Configurazione e lavoro quotidiano

Le immagini di questo capitolo sono il back office in inglese. I nomi sotto sono quelli del pannello in italiano.

Apra **Protezione contatti**. Le schede sono **Panoramica**, **Anti-flood**, **CleanTalk**, **StopForumSpam**, **reCAPTCHA**, **Filtri dei messaggi**, **Whitelist**, **Protezione** e **Email**. **Aggiornamenti** sta in fondo alla riga. **Salva** su una scheda la registra e conferma **Impostazioni salvate.** La scheda aggiornamenti conferma **Impostazioni di aggiornamento salvate.**

Finché vale la condizione, una pagina di configurazione può mostrare:

**reCAPTCHA è attivo, ma la chiave del sito o la chiave segreta è vuota. Il captcha resta disattivato finché entrambe le chiavi non vengono salvate.**

**L'API a pagamento di CleanTalk è attiva, ma la chiave di accesso è vuota.**

Il secondo avviso compare quando l'interruttore a pagamento è attivo e la chiave è vuota. Dopo un'installazione nuova quell'interruttore è spento, quindi l'avviso non c'è finché non attiva l'API a pagamento senza chiave.

Un messaggio viene controllato in questo ordine. Decide il primo risultato.

1. Un indirizzo in whitelist, e un cliente connesso quando **Salta i controlli per i clienti connessi** è attivo, prosegue verso il modulo. Il tentativo non viene scritto in **Tentativi di invio messaggi**.
2. Se tutti i controlli sono spenti e l'indirizzo non è nella lista dei ban, il messaggio prosegue e non viene registrato. Il solo interruttore reCAPTCHA non conta come controllo finché entrambe le chiavi sono vuote.
3. Poi: ban attivo, honeypot, tempo minimo, identificativo del browser vuoto, anti-flood, duplicato di un messaggio di almeno 20 caratteri, troppi link, parola bloccata, email usa e getta, reCAPTCHA (solo con entrambe le chiavi salvate), StopForumSpam, CleanTalk gratuito, poi CleanTalk a pagamento.
4. Se niente corrisponde, il tentativo viene salvato come consentito e il modulo invia il messaggio.
5. Un blocco **Troppo veloce** o **reCAPTCHA** ferma solo quel messaggio. Non banna l'indirizzo, non manda email al negozio e non reindirizza. Con reCAPTCHA il cliente vede **Verifica captcha non riuscita. Riprova.** Se è andato troppo veloce vede **Non è stato possibile inviare il messaggio. Riprova tra qualche minuto.**
6. Ogni altro blocco può bannare l'indirizzo, scrivere al negozio e reindirizzare, secondo le caselle di **Protezione**. Se spunta più reindirizzamenti, prima va la homepage, poi la pagina CMS, infine Google. Senza reindirizzamento il visitatore resta sulla pagina contatti e vede **Non è stato possibile inviare il messaggio. Riprova tra qualche minuto.**

L'anti-flood conta ogni tentativo nella finestra, anche quelli già bloccati. Più tentativi di captcha possono quindi arrivare al limite dei messaggi.

Un duplicato guarda i tentativi precedenti con lo stesso testo. I tentativi falliti solo per **Troppo veloce** o **reCAPTCHA** non contano come copia precedente.

StopForumSpam e entrambi i controlli CleanTalk lasciano passare il messaggio se il servizio non risponde. reCAPTCHA fa il contrario: se Google non risponde, il messaggio viene bloccato.

### 3.1 Panoramica

![Panoramica](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview.webp)

La **Panoramica** conta i messaggi di contatto, i messaggi bloccati e i ban attivi per le date dei **Parametri di analisi**. Un cliente che passa conta come messaggio. Un visitatore che non supera un controllo conta come bloccato e compare sotto con il motivo.

Le schede sono **Messaggi**, **Consentiti**, **Bloccati**, **Tasso di blocco**, **Indirizzi IP bloccati** e **Ban attivi**.

Il grafico **Bloccati e consentiti** mostra **Giornaliero** e **Settimanale** quando il periodo ha più di 7 giorni. **Settimanale** raggruppa i giorni a sette dal inizio del periodo. L'ultimo gruppo può essere più corto. La legenda è **Consentiti**, **Bloccati** e **Totale**. Senza righe nel periodo il grafico dice **Nessun messaggio in questo periodo.**

**Blocchi per motivo** mostra quanti blocchi ha prodotto ogni controllo. I nomi di questa pagina sono **IP bannato**, **Honeypot**, **Troppo veloce**, **User agent vuoto**, **Anti-flood**, **Messaggio duplicato**, **Troppi link**, **Parola bloccata**, **Email usa e getta**, **reCAPTCHA**, **StopForumSpam** e **CleanTalk**. Un motivo vuoto compare come **Sconosciuto**.

**Ultimi messaggi bloccati** ha le colonne **Data**, **IP**, **Email** e **Motivo**. Se non è stato bloccato niente, la tabella dice **Nessun blocco in questo periodo.**

I pulsanti **Tentativi di invio messaggi** e **Indirizzi IP bannati** aprono quelle liste.

I badge colorati sotto il grafico mostrano quali controlli sono attivi. **reCAPTCHA** è verde solo quando entrambe le chiavi sono salvate. Il solo interruttore non accende quel badge. Dopo l'installazione sono attivi **Anti-flood**, **Honeypot**, **Tempo minimo** e **Limite link**.

La riga sotto i badge ha la forma **Messaggi: 0 tra il 2026-10-13 e il 2026-11-11. Bloccati: 0, consentiti: 0. Nuovi ban in questo periodo: 0.** Le date seguono il periodo scelto. Un periodo mobile finisce oggi. Le date sono la finestra attuale del negozio, non un valore fisso del modulo.

### 3.2 Parametri di analisi

![Parametri di analisi](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview-analytics.webp)

Apra il pannello chiuso **Parametri di analisi** nella **Panoramica**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Periodo delle statistiche** | Ultimi 30 giorni | **Ultimi 7 giorni**, **Ultimi 30 giorni**, **Ultimi 90 giorni**, **Ultimi 180 giorni**, **Ultimi 365 giorni** o **Intervallo personalizzato**. Schede, grafico e ultima lista usano questa finestra. L'inizio sono gli ultimi 30 giorni. Gli ultimi 7 giorni mostrano un picco breve e tolgono i blocchi più vecchi dal grafico. Gli ultimi 365 giorni coprono un anno, quindi un giorno intenso è una fetta piccola. L'intervallo personalizzato usa **Da** e **A**. Le altre scelte ignorano quelle date e finiscono sempre oggi. |
| **Da** | l'inizio della finestra attuale | Data AAAA-MM-GG. Usata quando il **Periodo delle statistiche** è **Intervallo personalizzato**. Una data successiva ad **A** viene scambiata con **A**. Un intervallo più lungo di 366 giorni viene accorciato da questo lato. Una data futura torna a oggi. Una data vuota o non valida viene sostituita da quella di 30 giorni fa. I periodi mobili ignorano questo campo. |
| **A** | oggi | Data AAAA-MM-GG. Usata quando il **Periodo delle statistiche** è **Intervallo personalizzato**. Una data futura torna a oggi. Se **A** è precedente a **Da**, le date vengono scambiate. Una data vuota o non valida viene sostituita da oggi. I periodi mobili ignorano questo campo e finiscono sempre oggi. |

**Salva** registra il periodo. La pagina conferma **Impostazioni salvate.**

### 3.3 Anti-flood

![Anti-flood](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-antiflood.webp)

L'anti-flood conta quanti messaggi di contatto invia un indirizzo IP nella finestra. Un cliente che scrive qualche volta passa ancora. Il messaggio successivo oltre il limite viene rifiutato, e **Protezione** può bannare quell'indirizzo se la casella del ban è spuntata.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Attiva anti-flood** | Sì | Attivo: ogni IP viene contata nella finestra e il messaggio successivo oltre il limite viene bloccato. Spento: uno script può continuare a inviare dallo stesso IP senza limite di questo controllo. Un limite basso blocca anche un cliente che invia una correzione dallo stesso ufficio. Lo lasci attivo su una pagina contatti pubblica. Lo spenga solo mentre invia messaggi di prova da un indirizzo. |
| **Finestra di tempo** | 10 minuti | Minuti. Contano solo i messaggi di contatto degli ultimi X minuti. 1 o 2 minuti prendono un picco e poi lo dimenticano, uno script lento può quindi continuare. 60 minuti o più contano anche un cliente che scrive, aspetta e riscrive dallo stesso IP. Uno 0 salvato viene trattato come 1. |
| **Messaggi consentiti** | 5 | Quanti messaggi di contatto un IP può inviare nella finestra. Il successivo viene bloccato. 5 lascia correggere un messaggio e reinviarlo. 1 blocca il secondo invio, quindi gli script e anche un cliente che clicca invia due volte. Un valore alto, per esempio 20, lascia passare molti messaggi. Il contatore include gli invii precedenti di quell'IP, anche quelli bloccati, più tentativi di captcha possono quindi arrivare al limite. Uno 0 salvato viene trattato come 1. |

### 3.4 CleanTalk

![CleanTalk](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-cleantalk.webp)

CleanTalk controlla IP e email in una base di spam. Attivi l'opzione gratuita per usare il proxy MyPresta senza account CleanTalk, o quella a pagamento se ha una chiave propria. Un indirizzo sconosciuto viene accettato. Un indirizzo già segnalato come spam viene rifiutato. Se il servizio non risponde, il messaggio passa.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Attiva CleanTalk gratuito** | No | Chiede al proxy CleanTalk di MyPresta se questo IP o questa email è già noto come spam. Non serve un account CleanTalk. Spento salta questo controllo. Se il proxy non risponde, o PHP non ha la cifratura OpenSSL, il messaggio passa. Passa anche un bot assente dalla base. Lo attivi se non ha una chiave a pagamento. |
| **Attiva l'API a pagamento di CleanTalk** | No | Usa la chiave di accesso del suo account CleanTalk. La attivi dopo aver incollato la chiave. La lasci spenta se non ha un abbonamento. Una chiave vuota o rifiutata non blocca nessuno, quindi lo spam che solo questo controllo avrebbe preso viene accettato. Un indirizzo in lista viene rifiutato, e un cliente sullo stesso IP può esserlo anche lui. |
| **Chiave di accesso** | vuota | Incolli la chiave del suo account CleanTalk, senza spazi in più. Il controllo a pagamento gira solo se questo campo ha una chiave. Vuota, con l'interruttore a pagamento attivo, significa nessun controllo a pagamento, e la pagina mostra **L'API a pagamento di CleanTalk è attiva, ma la chiave di accesso è vuota.** Una chiave revocata viene trattata come controllo fallito e il messaggio passa. |
| **Soglia del tasso di spam** | 1 | Un punteggio da 0.0 a 1.0. Un tasso di spam CleanTalk uguale o superiore a questo valore viene trattato come spam. Un indirizzo che CleanTalk segna come presente nello spam viene bloccato a qualsiasi valore. 1 blocca gli indirizzi di cui CleanTalk è sicuro. Un valore più basso, per esempio 0.5, blocca anche risultati incerti e può fermare un cliente vero su un IP condiviso. Uno 0 salvato viene trattato come 1, il controllo resta quindi stretto. |

Il link **Apri la pagina dell'account CleanTalk** apre l'account in una scheda nuova.

### 3.5 StopForumSpam

![StopForumSpam](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-stopforumspam.webp)

StopForumSpam è una base gratuita di IP e email segnalate per spam. Il controllo non ha bisogno di una chiave API. Un cliente mai segnalato viene accettato. Un indirizzo con abbastanza segnalazioni viene rifiutato. Se il servizio non risponde, il messaggio passa.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Attiva StopForumSpam** | No | Vengono consultati l'IP del visitatore e l'email del modulo. Spento salta il controllo. Se il servizio non risponde, il messaggio passa: un problema di rete non blocca i clienti, e passa anche lo spam che questo controllo avrebbe preso. Lo lasci attivo su una pagina contatti pubblica. |
| **Segnalazioni minime** | 1 | Blocca quando StopForumSpam ha registrato questo IP o questa email almeno tante volte. A 1, una sola segnalazione blocca l'indirizzo, anche un cliente segnalato una volta per errore. A 5 o più, gli indirizzi con poche segnalazioni passano, quindi arriva più spam. Uno 0 salvato viene trattato come 1. |
| **Chiave API** | vuota | Facoltativa. La consultazione pubblica funziona senza chiave. La lasci vuota, o salvi una chiave se ha già un account StopForumSpam. Il modulo usa comunque la consultazione pubblica, una chiave sbagliata non cambia chi viene bloccato. |

Il link **Registrati** apre l'iscrizione a StopForumSpam.

### 3.6 reCAPTCHA

![reCAPTCHA](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-recaptcha.webp)

Google reCAPTCHA gira nel browser, sulla pagina contatti. Lo usi quando i bot inviano messaggi che sembrano testo ordinario, e scelga lo stesso tipo della chiave nella console Google. v2 mostra una casella. v3 valuta la visita senza sfida: un punteggio che passa viene accettato, uno che non passa rifiuta il messaggio senza bannare l'IP.

Il testo **Come ottenere la chiave del sito e la chiave segreta** dice: crei la chiave nella console Google, poi incolli sotto la chiave del sito e la chiave segreta. Il tipo scelto qui deve essere lo stesso di quella chiave. Un tipo diverso fa fallire ogni visitatore, anche un cliente vero.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Attiva reCAPTCHA** | Sì | La pagina contatti chiede di superare reCAPTCHA prima di accettare il messaggio. Con chiavi vuote il captcha resta spento anche se questo interruttore è attivo, e la pagina mostra **reCAPTCHA è attivo, ma la chiave del sito o la chiave segreta è vuota. Il captcha resta disattivato finché entrambe le chiavi non vengono salvate.** Un cliente che fallisce può riprovare. Quel fallimento non banna l'IP. |
| **Tipo di reCAPTCHA** | reCAPTCHA v2 | **reCAPTCHA v2** mostra una casella. **reCAPTCHA v3** valuta la visita in secondo piano e non mostra una sfida. Usi lo stesso tipo scelto per la chiave nella console Google. Uno scarto fa fallire ogni invio, anche quello dei clienti veri. v2 è più chiaro se vuole un controllo visibile. v3 si nota meno e usa la soglia sotto. |
| **Chiave del sito** | vuota | La chiave pubblica dell'amministrazione Google reCAPTCHA per il dominio di questo negozio. Incolli la chiave del sito del tipo scelto sopra, senza spazi. Servono entrambe le chiavi. Una chiave del sito vuota lascia il captcha spento. Una chiave di un altro dominio o di un altro tipo fa fallire i clienti veri. |
| **Chiave segreta** | vuota | La chiave segreta resta sul server. Non viene mai inviata al browser. Usi la chiave segreta della stessa coppia della chiave del sito. Una chiave segreta vuota lascia il captcha spento. Una chiave segreta di un altro sito fa rifiutare ogni visita da Google, i clienti non possono inviare il modulo. |
| **Tema v2** | Chiaro | Colore **Chiaro** o **Scuro** della casella v2. Chiaro su una pagina contatti bianca, Scuro su una scura. v3 ignora questa impostazione e usa il badge standard di Google. Il tema non cambia chi viene bloccato. Un widget scuro su una pagina bianca si vede meno, più persone saltano la casella e il messaggio viene rifiutato. |
| **Soglia di punteggio v3** | 0.5 | Un punteggio da 0.0 a 1.0. Usata quando il tipo è v3. Google valuta la visita e un punteggio sotto questo valore viene rifiutato. L'inizio è 0.5. Un valore più alto, per esempio 0.9, è più stretto e può rifiutare clienti su una rete condivisa o insolita. Un valore più basso, per esempio 0.1, lascia passare più visite automatiche. Un rifiuto non banna l'IP. Se manca il valore salvato, si usa 0.5. |

### 3.7 Filtri dei messaggi

![Filtri dei messaggi, primi campi](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters.webp)

![Filtri dei messaggi, campi successivi](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters-content.webp)

I filtri girano nel negozio, prima di un servizio esterno. Su una pagina contatti pubblica lasci honeypot e tempo minimo, e aggiunga link, parole, email usa e getta o duplicati quando la lista dei blocchi mostra uno schema che si ripete. Un cliente che compila il modulo in modo ordinario viene accettato. Uno script viene rifiutato. Un captcha fallito o un invio troppo veloce non banna l'IP. Gli altri filtri possono bannarla se la casella del ban è spuntata in **Protezione**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Campo honeypot** | Sì | Aggiunge un campo nascosto che le persone non vedono. Il cliente lo lascia vuoto e il messaggio prosegue. Uno script che riempie ogni campo viene bloccato, e **Protezione** può bannare quell'IP. Lo spenga se un completamento automatico riempie il campo nascosto e blocca i suoi clienti. |
| **Tempo minimo sulla pagina** | Sì | Blocca un invio più veloce del limite dopo l'avvio dello script della pagina. Un cliente che legge e scrive ha bisogno di più di qualche secondo. Uno script che invia subito viene bloccato. L'assenza del contatore viene accettata, un browser senza JavaScript può quindi ancora inviare. Questo blocco non banna l'IP. Spento lascia passare gli invii immediati da questo controllo. |
| **Secondi minimi** | 3 | Secondi. Usati quando il tempo minimo è attivo. 1 secondo prende ancora uno script immediato e tocca di rado un cliente. 15 secondi o più bloccano un cliente che conosce già il testo e invia in fretta. Il contatore parte quando gira lo script della pagina. Uno 0 salvato viene trattato come 1. |
| **Limita i link nel messaggio** | Sì | Conta http://, https:// e www. nel messaggio. Attivo quando lo spam che riceve è soprattutto link. Spento quando i clienti incollano spesso un indirizzo prodotto. Spento accetta un messaggio pieno di link. Attivo, con un massimo basso, blocca anche un cliente che incolla diversi indirizzi. |
| **Numero massimo di link** | 3 | Un messaggio con più link viene bloccato. Contato solo quando il limite dei link è attivo. 3 lascia incollare qualche indirizzo. 0 blocca ogni messaggio che contiene un link, anche verso una pagina prodotto. Un valore alto, per esempio 20, lascia passare uno spam di link tipico. |
| **Parole bloccate** | No | Ricerca senza distinzione di maiuscole nell'email e nel messaggio. Lo attivi dopo aver aggiunto frasi viste nello spam. Spento, o attivo con lista vuota, non blocca niente. Una parola corta e comune blocca anche un cliente vero che l'ha usata. |
| **Parole e frasi** | vuoto | Una parola o frase per riga. Usato quando le parole bloccate sono attive. Lo lasci vuoto finché non copia frasi dallo spam vero. Una frase corrisponde in qualsiasi punto dell'email o del messaggio, un pezzo corto come win corrisponde quindi anche a window e blocca una domanda ordinaria. Una frase lunga e precisa blocca solo quel testo. |
| **Blocca email usa e getta** | No | Blocca un elenco integrato di domini di caselle temporanee e i domini aggiunti sotto. Attivo quando non vuole messaggi da caselle usa e getta. Un indirizzo ordinario viene accettato. Una casella temporanea in elenco viene bloccata, e **Protezione** può bannare quell'IP. I domini assenti dall'elenco passano ancora finché non li aggiunge. Spento accetta ogni dominio. |
| **Domini usa e getta aggiuntivi** | vuoto | Un dominio per riga, per esempio dropmail.test. Usato quando le email usa e getta sono bloccate. Lo lasci vuoto finché un dominio non compare nella lista dei tentativi. Un dominio scritto qui blocca anche i suoi sottodomini. Non scriva @. Scrivere un vero fornitore di posta blocca ogni cliente che lo usa. |
| **Blocca messaggi duplicati** | No | Blocca lo stesso testo rinviato nella finestra, da qualsiasi IP. Attivo quando la stessa pubblicità parte da molti indirizzi. I messaggi più corti di 20 caratteri vengono saltati, un saluto breve si può quindi rinviare. Un nuovo tentativo di captcha non viene trattato come duplicato. Un cliente che invia due volte la stessa domanda lunga nella finestra viene bloccato la seconda. Spento permette di rinviare lo stesso testo. |
| **Finestra dei duplicati** | 60 minuti | Per quanto tempo il testo viene ricordato. Una finestra corta, per esempio 5 minuti, dimentica presto il testo, lo stesso spam può quindi tornare. Una finestra lunga, per esempio 1440 minuti (un giorno), blocca anche un cliente che rinvia la stessa domanda più tardi lo stesso giorno. Usata solo quando il blocco dei duplicati è attivo. Uno 0 salvato viene trattato come 1. |
| **Blocca un user agent vuoto** | No | Blocca una richiesta che non invia l'identificativo del browser. Lo lasci spento salvo che i tentativi mostrino spam con identificativo vuoto. I browser veri lo inviano. Attivo blocca anche gli strumenti di privacy che tolgono l'identificativo, quei clienti non possono quindi inviare. Spento ignora un identificativo vuoto. |
| **Salta i controlli per i clienti connessi** | No | Un cliente connesso salta tutti i controlli, anche un ban attivo. Lo lasci spento in un negozio dove chiunque può registrarsi. Lo attivi se i suoi clienti hanno account di cui si fida. Gli ospiti vengono comunque controllati. Attivo lascia passare un bot connesso. Spento controlla i clienti connessi come gli ospiti, un indirizzo di ufficio bannato resta quindi bannato anche per un account. |

### 3.8 Whitelist

![Whitelist](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-whitelist.webp)

La whitelist sono gli indirizzi IP che saltano tutti i controlli, anche un ban attivo. Aggiunga il suo ufficio, un'agenzia o uno strumento di controllo che invia un messaggio di prova. Tutti gli altri vengono comunque controllati. Una lista vuota significa che nessun indirizzo viene saltato. Una riga aggiunta per errore lascia passare quell'indirizzo, anche un bot che lo usa.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Indirizzi IP** | vuoto | Un indirizzo per riga. Una riga che finisce con * corrisponde all'inizio dell'indirizzo, per esempio 192.168.1.*. La lasci vuota salvo che un indirizzo debba sempre poter scrivere, come il suo ufficio. Un indirizzo intero salta i controlli solo per quell'IP. Un prefisso con asterisco salta tutto l'intervallo, compreso ogni bot di quell'intervallo. Un refuso non corrisponde a niente, quel visitatore resta quindi protetto. Confronti IPv4 e IPv6 esattamente come li mostra il negozio. |

### 3.9 Protezione

![Protezione](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-protection.webp)

Un controllo fallito rifiuta sempre il messaggio. Le caselle sotto **Cosa fare con lo spam** sono passi in più per un ban, l'honeypot, il flood, i filtri, StopForumSpam e CleanTalk. Non girano quando l'unico problema è il captcha o un invio troppo veloce. Un cliente che supera i controlli non ne è toccato.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Azioni aggiuntive** | nessuna spuntata | **Banna l'indirizzo IP**: attivo quando lo stesso indirizzo torna. Il messaggio successivo da quell'IP viene rifiutato finché non spegne il ban. Un IP di ufficio condiviso blocca allora ogni cliente che lo usa. **Invia email al negozio**: attivo se vuole un avviso in casella. Una email per IP, poi silenzio per 30 minuti. Spento lascia lo spam bloccato solo nella lista dei tentativi. **Reindirizza alla homepage**, **Reindirizza a una pagina CMS** e **Reindirizza a Google**: le lasci spente così il visitatore resta sulla pagina contatti e legge l'errore. Se spunta più reindirizzamenti, prima va la homepage, poi la pagina CMS, poi Google. |
| **Pagina CMS** | la prima pagina della lista del negozio | Usata quando è spuntato **Reindirizza a una pagina CMS**. Scelga una pagina breve che dice che il messaggio non è stato inviato. Se il negozio non ha pagine CMS, la lista contiene **Nessuna pagina CMS**. Senza pagina scelta, il reindirizzamento CMS viene saltato. Se è spuntato anche **Reindirizza a Google**, poi viene usato Google. Altrimenti il visitatore resta sulla pagina contatti con l'errore. Un cliente che supera i controlli non vede questa pagina per via del modulo. Le pagine della lista sono le pagine CMS del negozio. Se il negozio ha già delle pagine, la scelta vuota salvata non è in lista, quindi compare la prima. Clicchi **Salva** solo quando è la pagina che vuole. |

### 3.10 Email

![Email](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-mail.webp)

Il pannello **Email al negozio** imposta l'oggetto dell'email inviata all'indirizzo del negozio quando un messaggio viene bloccato. L'email parte solo se **Invia email al negozio** è spuntato in **Protezione**, e solo per blocchi diversi da un captcha fallito o da un invio troppo veloce. Parte una email al primo blocco di un IP. I blocchi successivi di quell'IP per 30 minuti non inviano posta. Un cliente accettato non scatena questa email. Se l'email del negozio nei parametri del negozio è vuota, non parte niente.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Oggetto** | Contact form spam blocked | Oggetto dell'avviso al negozio. In fondo viene aggiunto il nome breve del controllo, per esempio [flood]. Il messaggio va all'email del negozio impostata nei parametri del negozio. Un oggetto breve, che le regole della casella riconoscono, compilato per ogni lingua del negozio. Un oggetto vuoto viene sostituito da Contact form spam blocked. L'oggetto non cambia chi viene bloccato. |

Il pulsante della lingua passa l'oggetto a un'altra lingua del negozio. Il corpo della mail è il modello del modulo per quella lingua. Il testo inglese inizia con **Contact form blocked.** e poi indica il controllo, l'IP, l'email, la data e l'inizio del messaggio.

### 3.11 Aggiornamenti

![Aggiornamenti](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-updates.webp)

Questa pagina chiede a MyPresta.eu se esiste una versione più recente del modulo. Le impostazioni qui riguardano solo il controllo aggiornamenti. Non cambiano la protezione della pagina contatti.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Controlla aggiornamenti** | — | **Controlla ora** chiede subito a MyPresta.eu se esiste una versione più recente. Lo usi dopo l'installazione e di nuovo prima di un periodo intenso. Il pulsante non scarica e non installa un file. Se il server del negozio non raggiunge MyPresta.eu, il clic non mostra una versione nuova. |
| **Notifiche di aggiornamento** | Attiva | **Attiva** consulta MyPresta.eu e mostra un avviso nel back office quando esce una versione più recente. Il controllo automatico va circa ogni 3 giorni mentre lavora nel back office. **Disattiva** ferma quel controllo e l'avviso. Una versione nuova resta allora inosservata finché non clicca **Controlla ora**. Questa scelta non cambia la protezione del modulo. |
| **Pagina del modulo** | Contact page - spam protection PRO | Un link diretto alla pagina del modulo su MyPresta.eu. Il changelog di quella pagina mostra cosa è cambiato. La apra prima di un aggiornamento. Il link non installa un file. Se la pagina non carica, apra l'indirizzo in una scheda nuova. |

**Salva** conferma **Impostazioni di aggiornamento salvate.**

Quando esiste una versione più recente, il back office può mostrare **Nuova versione disponibile, visita http://MyPresta.eu per maggiori informazioni** e **Maggiori dettagli nel changelog**. **Controlla ora** risponde **Nuova versione disponibile!** o **Il modulo è aggiornato!**

### 3.12 Tentativi di invio messaggi

![Tentativi di invio messaggi](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-attempts.webp)

Apra **Tentativi di invio messaggi** sotto **Protezione contatti**, o il pulsante omonimo nella **Panoramica**.

Il negozio scrive una riga quando un messaggio di contatto viene controllato. Non c'è un pulsante di aggiunta. Da questa lista non modifica una riga. Può cancellare una riga.

Le colonne sono **ID**, **IP**, **Email**, **Motivo**, **Bloccati** e **Data**. La riga più recente è la prima. Una lista vuota dice, nell'immagine in inglese, **No records found**.

**Motivo** in questa lista è il nome breve, non il nome lungo della **Panoramica**:

| Nella panoramica | In questa lista |
|---|---|
| **IP bannato** | ban |
| **Honeypot** | honeypot |
| **Troppo veloce** | timing |
| **User agent vuoto** | user-agent |
| **Anti-flood** | flood |
| **Messaggio duplicato** | duplicate |
| **Troppi link** | links |
| **Parola bloccata** | keyword |
| **Email usa e getta** | disposable |
| **reCAPTCHA** | recaptcha |
| **StopForumSpam** | stopforumspam |
| **CleanTalk** | cleantalk |

Un messaggio consentito ha il motivo vuoto e **Bloccati** su no.

L'azione di riga è la cancellazione. Spunti le righe e usi **Elimina selezionati**. Il negozio chiede **Eliminare gli elementi selezionati?**

### 3.13 Indirizzi IP bannati

![Indirizzi IP bannati](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-bans.webp)

Apra **Indirizzi IP bannati** sotto **Protezione contatti**, o il pulsante omonimo nella **Panoramica**.

Le colonne sono **ID**, **IP**, **Data** e **Attivo**. La riga più recente è la prima. Una lista vuota dice, nell'immagine in inglese, **No records found**.

Il più apre l'inserimento. Il titolo del modulo è **Indirizzo IP bannato**.

![Nuovo indirizzo IP bannato](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-ban-form.webp)

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Indirizzo IP** | vuoto | Un indirizzo IP. Obbligatorio. Finché il ban è attivo, i messaggi di contatto da questo IP vengono rifiutati. Incolli l'indirizzo dalla lista dei tentativi, esattamente come è stato registrato. Una cifra sbagliata banna un altro visitatore, o nessuno. Un indirizzo di ufficio condiviso blocca anche clienti veri su quell'IP finché non spegne il ban. |
| **Attivo** | No | **Sì** tiene il ban in vigore e il modulo rifiuta questo IP. **No** conserva la riga e smette di bloccare, l'indirizzo può quindi riscrivere salvo che un altro controllo lo fermi. Scelga **Sì** finché quell'indirizzo manda ancora spam. Scelga **No** quando un cliente a quell'IP deve passare e vuole tenere la riga. Un ban creato da **Protezione** viene salvato già attivo. |

**Salva** registra la riga. Annulla torna alla lista senza salvare.

Su una riga esistente, **Modifica** apre lo stesso modulo, la cancellazione toglie la riga e l'icona **Attivo** accende o spegne il ban. Spunti le righe e usi **Elimina selezionati**. Il negozio chiede **Eliminare gli elementi selezionati?**

Un ban di **Protezione** rifiuta il messaggio di contatto successivo di quell'IP con il motivo **IP bannato** (nome breve ban) e non crea un secondo ban per lo stesso risultato.

## 4. Negozio

Il modulo lavora solo sulla pagina contatti del negozio. Sulle altre pagine non aggiunge niente.

Con le impostazioni dell'installazione, prima di salvare entrambe le chiavi reCAPTCHA, il cliente vede il modulo contatti ordinario del tema. Sulla pagina non c'è niente in più da catturare: l'honeypot è fuori dallo schermo, il contatore è nascosto e la casella reCAPTCHA non viene mostrata.

Dopo aver salvato entrambe le chiavi e lasciato **Attiva reCAPTCHA** su Sì:

- **reCAPTCHA v2** aggiunge la casella. Se il cliente invia senza spuntarla, la pagina dice **Conferma di non essere un robot.** e il modulo non parte.
- **reCAPTCHA v3** non mostra una sfida. Può comparire il badge di Google. Un punteggio sotto la soglia viene rifiutato sul server.

| Cosa è successo | Cosa vede il cliente |
|---|---|
| Casella v2 non spuntata | **Conferma di non essere un robot.** Il modulo resta sulla pagina. |
| Captcha fallito, o Google non raggiungibile | **Verifica captcha non riuscita. Riprova.** |
| Qualsiasi altro blocco, e nessun reindirizzamento spuntato | **Non è stato possibile inviare il messaggio. Riprova tra qualche minuto.** |
| Reindirizzamento alla homepage spuntato | La homepage del negozio. Nessun errore sulla pagina contatti. |
| Reindirizzamento CMS spuntato, una pagina scelta, e non quello alla homepage | Quella pagina CMS. |
| Reindirizzamento a Google spuntato, e gli altri non vengono usati | https://www.google.com |

Un messaggio che passa viene inviato dal modulo contatti come al solito. Il modulo non cambia quella conferma.

Il tema può sostituire il foglio di stile e lo script del negozio. Non può sostituire un template di modulo per il form, perché il form è quello dei contatti del negozio. Se il tema toglie il pulsante di invio di quel form, honeypot, contatore e captcha non si agganciano.

## 5. Problemi

**Il cliente vede «Conferma di non essere un robot.»**

La casella v2 non era spuntata. Gli chieda di spuntarla e di inviare di nuovo. Questo non banna l'IP.

**Il cliente vede «Verifica captcha non riuscita. Riprova.»**

Il captcha non è passato, o il negozio non ha raggiunto Google. Controlli che il **Tipo di reCAPTCHA** corrisponda alla chiave nella console Google, che **Chiave del sito** e **Chiave segreta** siano la coppia di questo dominio e che il server del negozio raggiunga Google. Un captcha fallito non banna l'IP. Il cliente può riprovare.

**Il cliente vede «Non è stato possibile inviare il messaggio. Riprova tra qualche minuto.»**

Un altro controllo ha rifiutato il messaggio e nessun reindirizzamento è spuntato. Apra **Tentativi di invio messaggi**, trovi l'IP o l'email e legga **Motivo**. Poi:

- flood: alzi **Messaggi consentiti** o **Finestra di tempo**, o aspetti che la finestra passi.
- honeypot: uno script o il completamento automatico ha riempito il campo nascosto. Spenga **Campo honeypot** se vengono bloccati i suoi clienti.
- timing: il modulo è partito prima di **Secondi minimi**. Alzi quel numero solo se vengono bloccati clienti veri. Questo blocco non banna l'IP.
- user-agent: spenga **Blocca un user agent vuoto** se c'entra uno strumento di privacy.
- duplicate: lo stesso testo di almeno 20 caratteri è stato rinviato nella **Finestra dei duplicati**.
- links: il messaggio ha più link di **Numero massimo di link**.
- keyword: una riga di **Parole e frasi** corrisponde all'email o al messaggio.
- disposable: il dominio dell'email è nell'elenco integrato o in **Domini usa e getta aggiuntivi**.
- stopforumspam o cleantalk: l'indirizzo è in quel servizio. Alzi **Segnalazioni minime** o **Soglia del tasso di spam**, o aggiunga l'indirizzo alla **Whitelist** se è un cliente.
- ban: l'indirizzo è in **Indirizzi IP bannati** con **Attivo** su **Sì**. Lo metta su **No**, o cancelli la riga.

**Il cliente finisce sulla homepage, su una pagina CMS o su Google.**

C'è stato un blocco duro e in **Protezione** è spuntato un reindirizzamento. Tolga la spunta da **Reindirizza alla homepage**, **Reindirizza a una pagina CMS** e **Reindirizza a Google** se vuole che l'errore resti sulla pagina contatti. Se ne sono spuntati diversi, vince la homepage, poi la CMS, poi Google.

**Un intero ufficio non può scrivere.**

L'ufficio condivide un IP. Quell'IP è bannato, ha superato il limite anti-flood o è in un servizio. Apra **Indirizzi IP bannati** e metta **Attivo** su **No**, o aggiunga l'indirizzo alla **Whitelist**. Una riga della whitelist salta tutti i controlli, anche il ban.

**reCAPTCHA resta spento.**

L'avviso dice **reCAPTCHA è attivo, ma la chiave del sito o la chiave segreta è vuota. Il captcha resta disattivato finché entrambe le chiavi non vengono salvate.** Incolli entrambe le chiavi e clicchi **Salva**.

**Il CleanTalk a pagamento non blocca nessuno.**

L'avviso dice **L'API a pagamento di CleanTalk è attiva, ma la chiave di accesso è vuota.** Incolli **Chiave di accesso** e clicchi **Salva**. Una chiave rifiutata lascia passare anche il messaggio. Se il servizio non risponde, il messaggio passa.

**Non arriva email al negozio.**

**Invia email al negozio** deve essere spuntato. Il blocco deve essere qualcosa di diverso dal captcha o da troppo veloce. Lo stesso IP manda una sola email in 30 minuti. L'email del negozio nei parametri del negozio deve essere compilata. L'oggetto riceve il nome breve del controllo, per esempio [flood].

**Controlla ora non mostra niente di nuovo.**

Il server del negozio non ha raggiunto MyPresta.eu, o il modulo è già aggiornato. La risposta **Il modulo è aggiornato!** significa che non è stata segnalata una versione più recente. **Controlla ora** non scarica il file.

**Le liste sono vuote dopo una nuova installazione.**

La disinstallazione cancella tentativi e ban. Una nuova installazione non li riporta.

## 6. Per gli sviluppatori

### 6.1 Panoramica

Classe principale `mycontactprotectionpro`, versione `1.0.0`, autore MyPresta.eu, scheda `administration`. Il nome in elenco è **Contact page - spam protection PRO**. La compatibilità nel file è PrestaShop 1.7.7.0 fino a 9.99.99.

Le impostazioni si leggono con `Configuration::get` nel contesto negozio attivo al clic su **Salva**. Un POST della pagina contatti con `submitMessage` esegue `hookActionFrontControllerInitAfter`. Un passaggio scrive una riga consentita e lascia inviare il modulo. Un blocco scrive una riga bloccata, e un motivo duro può creare un ban, inviare la mail al negozio e reindirizzare.

`install()` chiama l'installazione padre, scrive la configurazione, crea le due tabelle, crea il menu e registra i tre hook. Non svuota la cache. Non c'è un `enable()` o `disable()` proprio. `uninstall()` cancella le chiavi del 6.7 più `update_mycontactprotectionpro` e `updatev_mycontactprotectionpro`, cancella le schede del menu, fa DROP delle due tabelle e chiama la disinstallazione padre. Non cancella `mypresta_updates`. I file restano finché non si toglie la cartella del modulo.

### 6.2 File

| File | Ruolo |
|---|---|
| mycontactprotectionpro.php | install, uninstall, hook, moduli, ordine dei controlli, cruscotto, mail al negozio |
| controllers/admin/AdminMycontactprotectionpro.php | padre del menu; reindirizza alla configurazione del modulo |
| controllers/admin/AdminMycontactprotectionproAttempts.php | lista tentativi e cancellazione |
| controllers/admin/AdminMycontactprotectionproBans.php | lista ban, inserimento, modifica, cancellazione, interruttore active |
| models/attempt.php | tabella tentativi e contatori |
| models/ban.php | tabella ban e `banIp()` |
| lib/sfs.php | consultazione StopForumSpam |
| lib/ctalk.php | CleanTalk gratuito e a pagamento |
| lib/updatesChecker.php | controllo aggiornamenti, classe `mycontactprotectionproUpdate` |
| lib/recaptcha/ | libreria reCAPTCHA usata dal modulo |
| views/templates/admin/configure.tpl | barra schede e markup della panoramica |
| views/css/admin.css | layout della configurazione nel back office |
| views/css/front.css | mette l'honeypot fuori dallo schermo |
| views/js/front.js | honeypot, contatore, casella v2 e token v3 sul modulo |
| mails/{iso}/mcpp_merchant.html | corpo HTML dell'avviso; non passa da `$this->l()` |
| mails/{iso}/mcpp_merchant.txt | corpo testo dell'avviso |
| translations/{iso}.php | testi del back office e del cliente |
| key.php | valore inviato con la richiesta CleanTalk gratuita |

Non c'è un controller di vetrina né un template di vetrina per il modulo contatti.

### 6.3 Controller

| Classe | Padre nel menu | Cosa accetta |
|---|---|---|
| AdminMycontactprotectionproController | id 0, icona security, titolo Contact protection | reindirizza a AdminModules con `configure=mycontactprotectionpro` |
| AdminMycontactprotectionproAttemptsController | AdminMycontactprotectionpro | tabella `mcpp_attempt`, ordine `id_mcpp_attempt` DESC, `list_no_link`, cancella riga, cancellazione di massa. Nessun inserimento. |
| AdminMycontactprotectionproBansController | AdminMycontactprotectionpro | tabella `mcpp_ban`, ordine `id_mcpp_ban` DESC, modifica e cancella riga, cancellazione di massa, stato su `active`. Modulo: `ip` (obbligatorio) e `active`. |

La configurazione è `getContent()` del modulo, non un controller a parte. La scheda passa in `mcpp_tab`. I nomi di invio sono `submitMcppAntiFlood`, `submitMcppCleanTalk`, `submitMcppStopForumSpam`, `submitMcppRecaptcha`, `submitMcppFilters`, `submitMcppWhitelist`, `submitMcppProtection`, `submitMcppMail`. Il modulo aggiornamenti invia `submit_settings_updates` e `submit_settings_updates_now`.

Non c'è un controller di vetrina. La pagina contatti è il `ContactController` del negozio.

### 6.4 Hook

| Hook | Quando gira |
|---|---|
| actionFrontControllerSetMedia | sulla pagina contatti, quando honeypot, contatore o un reCAPTCHA pronto sono attivi; aggiunge front.css e front.js e passa allo script le impostazioni pubbliche |
| actionFrontControllerInitAfter | su un POST della pagina contatti con submitMessage; controlla e torna, ferma il modulo o reindirizza |
| displayBackOfficeHeader | aggiunge views/css/admin.css |

Il modulo non registra un hook di visualizzazione proprio. La pagina contatti si riconosce da `php_self` uguale a `contact`, o dalla classe `ContactController` o `ContactControllerCore`.

Nel back office il costruttore chiama `runUpdateSetUp()`. Quel metodo consulta MyPresta circa ogni 259200 secondi quando `mypresta_updates` non è 0, salva il risultato in `updatev_mycontactprotectionpro` e aggiunge un avviso del controller quando la versione salvata è più recente.

### 6.5 Override

Il modulo non porta override di classi né di controller.

### 6.6 Database

Il prefisso è quello del negozio. Aprire una pagina non aggiunge colonne. La disinstallazione cancella entrambe le tabelle.

| Tabella | Contenuto |
|---|---|
| mcpp_attempt | `id_mcpp_attempt` int chiave primaria, `ip` varchar 64, `email` varchar 255, `message_hash` varchar 64 (MD5 del messaggio in minuscolo), `reason` varchar 255 (nome breve, vuoto se consentito), `blocked` tinyint, `date_add` datetime. Chiavi `ip_date` (`ip`, `date_add`) e `hash_date` (`message_hash`, `date_add`). |
| mcpp_ban | `id_mcpp_ban` int chiave primaria, `ip` varchar 64, `date_add` datetime, `active` tinyint predefinito 1. Chiave `ip_active` (`ip`, `active`). Il modulo di inserimento si apre con Attivo su No. `banIp()` inserisce o aggiorna la riga con `active` 1. |

### 6.7 Chiavi e traduzioni

Valore quando la chiave manca:

| Chiave | Se manca |
|---|---|
| mcpp_af | 1 |
| mcpp_time | 10 |
| mcpp_atmpt | 5 |
| mcpp_ct | 0 |
| mcpp_ct_paid | 0 |
| mcpp_ct_key | vuoto |
| mcpp_ct_rate | 1, e uno 0 salvato viene trattato come 1 |
| mcpp_sfs | 0 |
| mcpp_sfs_key | vuoto |
| mcpp_sfs_freq | 1, e uno 0 salvato viene trattato come 1 |
| mcpp_rc | 1 |
| mcpp_rc_type | 0, cioè v2; 1 è v3 |
| mcpp_rc_site | vuoto |
| mcpp_rc_secret | vuoto |
| mcpp_rc_theme | light, salvo che il valore salvato sia dark |
| mcpp_rc_score | 0.5 |
| mcpp_hp | 1 |
| mcpp_tg | 1 |
| mcpp_tg_sec | 3, e uno 0 salvato viene trattato come 1 |
| mcpp_links | 1 |
| mcpp_links_max | 3 |
| mcpp_kw | 0 |
| mcpp_kw_list | vuoto |
| mcpp_disp | 0 |
| mcpp_disp_extra | vuoto |
| mcpp_dup | 0 |
| mcpp_dup_min | 60, e uno 0 salvato viene trattato come 1 |
| mcpp_ua | 0 |
| mcpp_bypass | 0 |
| mcpp_ptype_1 | 0, banna l'IP |
| mcpp_ptype_4 | 0, email al negozio |
| mcpp_ptype_7 | 0, reindirizzamento alla homepage |
| mcpp_ptype_6 | 0, reindirizzamento CMS |
| mcpp_ptype_5 | 0, reindirizzamento a Google |
| mcpp_cms | 0 |
| mcpp_wh_ip | vuoto |
| mcpp_mtitle | Contact form spam blocked, per lingua; un oggetto vuoto usa questa frase inglese |
| mcpp_dash_preset | 30; ogni valore diverso da 7, 30, 90, 180, 365 o custom torna a 30 |
| mcpp_dash_from | vuoto finché la panoramica non costruisce la finestra |
| mcpp_dash_to | vuoto finché la panoramica non costruisce la finestra |

`mypresta_updates` è condiviso. Se manca, le notifiche vengono trattate come attive. La disinstallazione non lo cancella. `key.php` assegna `mkey`. Se è vuoto, la richiesta CleanTalk gratuita usa `nlc`. Il controllo aggiornamenti usa `nokey` quando manca il valore.

Domini usa e getta integrati, riconosciuti sul dominio e sui sottodomini: mailinator.com, guerrillamail.com, guerrillamail.info, guerrillamail.biz, guerrillamail.de, guerrillamail.net, guerrillamail.org, guerrillamailblock.com, sharklasers.com, grr.la, yopmail.com, yopmail.fr, yopmail.net, trashmail.com, trashmail.de, trash-mail.com, tempmail.com, temp-mail.org, 10minutemail.com, 10minutemail.net, throwawaymail.com, getnada.com, dispostable.com, maildrop.cc, fakeinbox.com, mailnesia.com, mohmal.com, emailondeck.com, tempail.com, moakt.com, spam4.me, byom.de, mintemail.com, mytemp.email, tmpmail.net, tmpmail.org, discard.email, discardmail.com, inboxkitten.com, getairmail.com, generator.email, mailcatch.com. I domini di `mcpp_disp_extra` si aggiungono allo stesso modo.

Etichette, descrizioni dei campi e le tre frasi del cliente sono `$this->l()` in `mycontactprotectionpro.php`, `lib/updatesChecker.php` (sorgente `updatesChecker`), `AdminMycontactprotectionproAttempts.php` (sorgente `AdminMycontactprotectionproAttempts`) e `AdminMycontactprotectionproBans.php` (sorgente `AdminMycontactprotectionproBans`). Aggiunga una lingua con `translations/{iso}.php`. Le descrizioni dei campi stanno nel `desc` dei campi HelperForm della classe principale e del controller dei ban.

I corpi di `mails/{iso}/mcpp_merchant.html` e `mails/{iso}/mcpp_merchant.txt` non passano da `$this->l()`. Il testo inglese inizia con `Contact form blocked.` L'oggetto è `mcpp_mtitle` della lingua della mail, con il motivo breve aggiunto, per esempio ` [flood]`. La mail va a `PS_SHOP_EMAIL`. Un'email negozio vuota non invia niente. Nel corpo ci sono i primi 500 caratteri del messaggio senza tag.

### 6.8 Estensione

Un tema può sovrascrivere `views/css/front.css` e `views/js/front.js`. Non c'è un template di vetrina per il modulo, il tema non ha quindi un template di form del modulo da sovrascrivere. Il markup è il modulo contatti del negozio. `front.js` cerca `form [name=submitMessage]`. Se quel pulsante manca, lo script torna e non aggiunge niente.

Il nome dell'honeypot è `mcpp_website`. Il nome del contatore è `mcpp_ts`. Un honeypot compilato è un risultato. L'assenza del contatore non lo è. Un contatore nel futuro lo è. reCAPTCHA v3 usa l'azione `contact`.

L'ordine dei controlli è fisso: ban, honeypot, timing, user agent vuoto, flood, duplicate, links, keyword, disposable, recaptcha, stopforumspam, CleanTalk gratuito, CleanTalk a pagamento. Vince il primo risultato. Whitelist e l'eccezione del cliente connesso tornano prima che venga scritta una riga. Se `protectionEnabled()` è falso e l'IP non è bannato, l'hook torna senza scrivere. `protectionEnabled()` è vero quando uno fra `mcpp_af`, `mcpp_ct`, `mcpp_ct_paid`, `mcpp_sfs`, `mcpp_hp`, `mcpp_tg`, `mcpp_links`, `mcpp_kw`, `mcpp_disp`, `mcpp_dup`, `mcpp_ua` vale 1, o quando reCAPTCHA è pronto (interruttore attivo ed entrambe le chiavi non vuote).

I motivi duri sono tutti tranne `timing` e `recaptcha`. Solo un motivo duro può creare un ban, inviare la mail al negozio e reindirizzare. La priorità di reindirizzamento è `mcpp_ptype_7` (homepage), poi `mcpp_ptype_6` quando `mcpp_cms` è maggiore di 0, poi `mcpp_ptype_5` (`https://www.google.com`). Altrimenti il modulo toglie `submitMessage` e aggiunge l'errore. Un blocco recaptcha usa la frase del captcha. Ogni altro blocco che resta sulla pagina usa la frase dei pochi minuti.

Il CleanTalk gratuito viene saltato se non esiste `openssl_encrypt`. StopForumSpam e CleanTalk lasciano passare il messaggio se la chiamata remota fallisce. reCAPTCHA blocca il messaggio se la chiamata remota fallisce. Il flood usa `countByIpSince`, che conta ogni tentativo nella finestra. Il duplicato usa `countDuplicateSince`, che ignora le righe il cui motivo è `timing` o `recaptcha`, e gira solo se il messaggio ha almeno 20 caratteri.

Chiamate PHP: `curl_init` se esiste, altrimenti `file_get_contents` per StopForumSpam, CleanTalk e il controllo aggiornamenti quando `allow_url_fopen` è attivo. `openssl_encrypt` per la richiesta CleanTalk gratuita. `json_decode` per le risposte di StopForumSpam, CleanTalk a pagamento e reCAPTCHA. Non serve un altro modulo.

## 7. Aiuto

Pagina del modulo: https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html

Per una domanda su questo modulo acceda all'account cliente su [https://mypresta.eu/](https://mypresta.eu/) e apra il modulo di contatto. Scelga l'argomento **Support for paid modules**. Il modulo indica che l'accesso è obbligatorio. Poi scelga questo modulo dalla cronologia degli acquisti. La pagina è [https://mypresta.eu/contact-form](https://mypresta.eu/contact-form).
