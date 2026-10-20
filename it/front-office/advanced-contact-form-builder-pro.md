---
title: "Advanced Contact Form Builder Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Advanced Contact Form Builder Pro di MyPresta.eu."
sidebar:
  label: "Advanced Contact Form Builder Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Advanced Contact Form Builder Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-contact-form-builder-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/advanced-contact-form-builder-pro/)
>
> ---


# Advanced Contact Form Builder Pro

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x (fino a 12.x secondo la definizione del modulo)
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e per funzionalità come webhook o reCAPTCHA.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale in cui si impostano il comportamento generale e le opzioni predefinite per i moduli di contatto.

- **Profilo di supporto del template**

  - **Cosa fa questa impostazione:** Questa impostazione aiuta il modulo ad adattare la sua output visiva per meglio corrispondere al tema del tuo negozio. Diversi temi PrestaShop potrebbero avere strutture HTML leggermente diverse.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 'Classic' (o simile):* Il modulo utilizzerà template ottimizzati per il tema PrestaShop Classic predefinito o temi basati su di esso. Ciò garantisce che i moduli abbiano un bell'aspetto senza sforzi di stile aggiuntivi.
    - *Quando impostato su 'Custom' o un altro nome di tema:* Il modulo potrebbe utilizzare template specifici o regole di stile personalizzate per quel particolare tema, se disponibili.
  - **Valore consigliato:** Scegli l'opzione che meglio si adatta al tuo tema PrestaShop attivo. Se stai utilizzando il tema Classic predefinito o un tema derivato da esso, 'Classic' è di solito la scelta migliore. Se i tuoi moduli non appaiono correttamente, prova a sperimentare con questa impostazione.
  - **Scenario / esempio del commerciante:** Se i tuoi moduli appaiono senza stile o disallineati dopo l'installazione, il passaggio da 'Classic' a un altro profilo disponibile (se presente) potrebbe risolvere il problema.
- **Email di risposta automatica**

  - **Cosa fa questa impostazione:** Questo è l'indirizzo email da cui verranno inviate le email di conferma automatiche ai tuoi clienti dopo che hanno inviato un modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un indirizzo email valido:* I clienti riceveranno un'email immediata di "Grazie per la tua richiesta" da questo indirizzo.
    - *Quando lasciato vuoto:* Nessuna email di conferma automatica verrà inviata al cliente.
  - **Valore consigliato:** Utilizza un indirizzo email professionale associato al tuo negozio, ad esempio, `info@tuonegozio.com` o `noreply@tuonegozio.com`.
  - **Scenario / esempio del commerciante:** Impostare questo su `supporto@miostore.com` assicura che i clienti sappiano che il loro messaggio è stato ricevuto e fornisce loro un punto di contatto per il follow-up.
- **Titolo email (per il proprietario del negozio)**

  - **Cosa fa questa impostazione:** Definisce l'oggetto per le notifiche email che tu (il proprietario del negozio) ricevi quando un cliente invia un modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su "Nuova richiesta dal mio negozio":* Le tue email di notifica avranno questo oggetto, rendendole facili da identificare.
  - **Valore consigliato:** Qualcosa di chiaro e descrittivo, come "Nuova submission modulo di contatto - [Nome del tuo negozio]".
  - **Scenario / esempio del commerciante:** L'utilizzo di "Nuova richiesta cliente - MyPresta.eu" ti aiuta a individuare rapidamente i messaggi importanti nella tua casella di posta.
- **Email del destinatario (o più email)**

  - **Cosa fa questa impostazione:** Qui si specificano uno o più indirizzi email che riceveranno le notifiche quando un cliente invia *qualsiasi* modulo creato da questo modulo. È possibile separare più email con una virgola.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su `vendite@tuonegozio.com`:* Tutte le submission dei moduli verranno inviate al reparto vendite.
    - *Quando impostato su `vendite@tuonegozio.com, supporto@tuonegozio.com`:* Entrambi i reparti riceveranno copie di tutte le submission.
  - **Valore consigliato:** L'indirizzo email principale (o gli indirizzi) per il tuo servizio clienti o team di vendita.
  - **Scenario / esempio del commerciante:** Se hai un team di assistenza clienti dedicato, qui inserirai `assistenzaclienti@tuonegozio.com`.
- **BCC per l'email di notifica del negozio**

  - **Cosa fa questa impostazione:** Ti consente di inviare una "Copia Carbone Nascosta" (BCC) dell'email di notifica del proprietario del negozio a indirizzi email aggiuntivi. Questi destinatari non saranno visibili al destinatario principale.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su `manager@tuonegozio.com`:* Il manager riceverà una copia nascosta di tutte le notifiche di submission dei moduli.
  - **Valore consigliato:** Utilizzalo per il tracciamento interno, il backup o per i manager che devono monitorare le richieste senza essere il contatto principale. Lascia vuoto se non necessario.
  - **Scenario / esempio del commerciante:** Il tuo team di marketing potrebbe voler mettersi in BCC per tracciare la generazione di lead dai moduli senza essere direttamente coinvolto nelle risposte ai clienti.
- **Sì / No (per varie impostazioni di visibilità/requisito dei campi)**

  - **Cosa fa questa impostazione:** Questi sono interruttori generali per abilitare o disabilitare funzionalità specifiche o rendere certi campi obbligatori/opzionali sui tuoi moduli.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* La funzionalità è attiva (ad esempio, il campo telefono è visibile, gli allegati sono consentiti).
    - *Quando disabilitato (No):* La funzionalità è inattiva (ad esempio, il campo telefono è nascosto, gli allegati non sono consentiti).
  - **Valore consigliato:** Dipende interamente dalle tue esigenze aziendali per ogni impostazione specifica (vedi le singole impostazioni di seguito).
- **Conforme al GDPR**

  - **Cosa fa questa impostazione:** Abilita una casella di controllo sui tuoi moduli in cui i clienti devono accettare esplicitamente la tua politica sulla privacy prima di inviare i loro dati. Questo è fondamentale per la conformità al GDPR.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Una casella di controllo obbligatoria appare sui tuoi moduli, tipicamente con una dicitura come "Accetto la politica sulla privacy". Il modulo non può essere inviato finché questa casella non è spuntata.
    - *Quando disabilitato:* Nessuna casella di controllo per il consenso GDPR apparirà.
  - **Valore consigliato:** **SÌ** se il tuo negozio opera in regioni soggette al GDPR (ad esempio, UE) o se desideri garantire le migliori pratiche per la privacy dei dati.
  - **Scenario / esempio del commerciante:** Un negozio con sede nell'UE *deve* abilitare questa opzione per raccogliere legalmente i dati dei clienti tramite moduli.
- **Pagina della politica sulla privacy**

  - **Cosa fa questa impostazione:** Se la conformità GDPR è abilitata, questa impostazione ti consente di collegare alla pagina CMS della politica sulla privacy del tuo negozio. La casella di controllo del consenso GDPR includerà tipicamente un link a questa pagina.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene selezionata una pagina:* Il testo del consenso GDPR includerà un link cliccabile alla pagina della tua politica sulla privacy scelta.
    - *Quando non viene selezionata alcuna pagina:* Il testo del consenso GDPR potrebbe apparire senza un link, o collegare a una pagina predefinita, il che non è l'ideale per la conformità.
  - **Valore consigliato:** Seleziona la pagina CMS ufficiale della politica sulla privacy del tuo negozio.
  - **Scenario / esempio del commerciante:** Dopo aver abilitato il GDPR, selezioneresti la pagina CMS intitolata "Politica sulla privacy" dall'elenco a discesa.
- **ReCaptcha (v2)**

  - **Cosa fa questa impostazione:** Abilita Google reCAPTCHA v2 sui tuoi moduli per proteggere da spam e bot.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* La casella di controllo reCAPTCHA "Non sono un robot" apparirà sui tuoi moduli. Gli utenti devono completare questa sfida prima di inviare.
    - *Quando disabilitato:* Nessuna protezione reCAPTCHA è attiva.
  - **Valore consigliato:** **SÌ** per prevenire submission di spam. Dovrai anche configurare la Chiave del sito e la Chiave segreta di seguito.
  - **Scenario / esempio del commerciante:** Se stai ricevendo molto spam tramite i tuoi moduli di contatto, abilitare reCAPTCHA è il primo passo per combatterlo.
- **Chiave del sito ReCaptcha**

  - **Cosa fa questa impostazione:** Questa è una chiave pubblica fornita da Google reCAPTCHA che consente al tuo sito web di visualizzare il widget reCAPTCHA.
  - **Effetto della modifica di questa impostazione:**
    - *Quando inserita correttamente:* Il widget reCAPTCHA apparirà e funzionerà correttamente sui tuoi moduli.
    - *Quando errata o vuota:* reCAPTCHA non funzionerà e i moduli potrebbero non essere inviati o visualizzare errori.
  - **Valore consigliato:** La Chiave del sito ottenuta dal tuo account Google reCAPTCHA.
  - **Scenario / esempio del commerciante:** Dopo aver creato una coppia di chiavi reCAPTCHA v2 nella console di amministrazione di Google reCAPTCHA, copieresti qui la "Chiave del sito".
- **Chiave segreta ReCaptcha**

  - **Cosa fa questa impostazione:** Questa è una chiave privata fornita da Google reCAPTCHA che consente al tuo server di verificare la risposta reCAPTCHA. Dovrebbe essere mantenuta segreta.
  - **Effetto della modifica di questa impostazione:**
    - *Quando inserita correttamente:* Il tuo server può verificare con successo se un utente ha superato la sfida reCAPTCHA.
    - *Quando errata o vuota:* La verifica fallirà e gli utenti legittimi potrebbero non essere in grado di inviare i moduli.
  - **Valore consigliato:** La Chiave segreta ottenuta dal tuo account Google reCAPTCHA.
  - **Scenario / esempio del commerciante:** Copieresti qui la "Chiave segreta" dalla tua console di amministrazione di Google reCAPTCHA.
- **URL Webhook (Slack/Discord)**

  - **Cosa fa questa impostazione:** Ti consente di inviare notifiche di submission di moduli a un canale Slack o Discord specificato tramite un webhook. Questo fornisce avvisi istantanei al team.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene inserito un URL valido:* Ogni submission di modulo attiverà una notifica al tuo canale Slack/Discord configurato.
    - *Quando vuoto:* Nessuna notifica webhook verrà inviata.
  - **Valore consigliato:** Il tuo URL webhook di Slack o Discord. Lascia vuoto se non utilizzi questi servizi per le notifiche.
  - **Scenario / esempio del commerciante:** Il tuo team di assistenza clienti utilizza Slack. Configuri un webhook in Slack, incolli l'URL qui e ora ogni nuova richiesta appare direttamente nel loro canale #assistenza-clienti.
- **CSS personalizzato (vetrina)**

  - **Cosa fa questa impostazione:** Fornisce un'area di testo in cui puoi aggiungere il tuo codice CSS personalizzato per stilizzare i moduli sulla tua vetrina. Questo è utile per perfezionare l'aspetto in modo che corrisponda perfettamente al tuo marchio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene inserito CSS:* Gli stili definiti qui verranno applicati ai tuoi moduli, sovrascrivendo gli stili predefiniti del modulo.
  - **Valore consigliato:** Utilizzalo solo se hai esigenze di stile specifiche oltre all'aspetto predefinito del modulo. Consulta un web designer se non sei sicuro.
  - **Scenario / esempio del commerciante:** Vuoi che il pulsante di invio del modulo sia di una specifica tonalità di verde che corrisponda al tuo logo. Aggiungeresti CSS come `.cfrompro-form button[type="submit"] { background-color: #00FF00; }` qui.
- **Lunghezza minima della domanda (caratteri)**

  - **Cosa fa questa impostazione:** Imposta il numero minimo di caratteri richiesti per il campo principale "Domanda" o "Messaggio" nei tuoi moduli.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 10:* I clienti devono digitare almeno 10 caratteri nel campo del messaggio per inviare il modulo.
    - *Quando impostato su 0 (o molto basso):* Consente messaggi molto brevi.
  - **Valore consigliato:** 10-20 caratteri per incoraggiare i clienti a fornire dettagli sufficienti.
  - **Scenario / esempio del commerciante:** Per evitare richieste vaghe come "Ciao", imposti questo su 15, assicurando che i clienti forniscano un messaggio più descrittivo.
- **Lunghezza massima della domanda (caratteri)**

  - **Cosa fa questa impostazione:** Imposta il numero massimo di caratteri consentiti per il campo principale "Domanda" o "Messaggio".
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 500:* I clienti non possono digitare più di 500 caratteri nel campo del messaggio.
  - **Valore consigliato:** 500-1000 caratteri, a seconda di quanto dettagliate ti aspetti che siano le richieste. Troppo basso potrebbe frustrare gli utenti, troppo alto potrebbe portare a messaggi eccessivamente lunghi.
  - **Scenario / esempio del commerciante:** Vuoi impedire saggi estremamente lunghi nel modulo di contatto, quindi imposti questo su 750 caratteri.
- **Consenti allegati immagine**

  - **Cosa fa questa impostazione:** Abilita o disabilita la possibilità per i clienti di caricare file (come immagini, PDF) con la loro submission del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un campo di caricamento file apparirà sui tuoi moduli.
    - *Quando disabilitato:* Nessuna opzione di caricamento file sarà disponibile.
  - **Valore consigliato:** **SÌ** se i clienti spesso devono fornire screenshot, conferme d'ordine o altri documenti. **NO** se vuoi mantenere i moduli semplici.
  - **Scenario / esempio del commerciante:** Per un modulo di supporto, abilitare gli allegati consente ai clienti di inviare screenshot dei problemi, il che è molto utile.
- **Dimensione massima allegato (MB)**

  - **Cosa fa questa impostazione:** Se gli allegati sono consentiti, questa impostazione definisce la dimensione massima del file (in megabyte) che un cliente può caricare.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 5:* I clienti possono caricare file fino a 5MB. File più grandi verranno rifiutati.
  - **Valore consigliato:** 2-5 MB è di solito sufficiente per la maggior parte dei documenti e delle immagini senza sovraccaricare il tuo server.
  - **Scenario / esempio del commerciante:** Consenti allegati ma vuoi prevenire file enormi, quindi imposti il limite a 3 MB.
- **Durata messaggio di successo (ms)**

  - **Cosa fa questa impostazione:** Controlla per quanto tempo il messaggio "Modulo inviato con successo" (spesso una notifica "toast") rimane visibile al cliente dopo che ha inviato un modulo. Misurato in millisecondi (1000 ms = 1 secondo).
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 3000:* Il messaggio di successo scomparirà dopo 3 secondi.
    - *Quando impostato su 0:* Il messaggio potrebbe rimanere indefinitamente o scomparire immediatamente (a seconda del tema/browser).
  - **Valore consigliato:** 3000-5000 ms (3-5 secondi) è un buon equilibrio, dando ai clienti abbastanza tempo per leggerlo senza essere invadente.
  - **Scenario / esempio del commerciante:** Vuoi che i clienti vedano chiaramente la conferma, quindi lo imposti a 4000 ms.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo aggiunge nuove voci di menu sotto **"Advanced Contact Form Pro"** nel Back Office di PrestaShop.

#### 2.2.1 Gestione moduli (Back Office > Advanced Contact Form Pro > Moduli)

Questa schermata ti consente di creare, modificare e gestire tutti i tuoi moduli di contatto personalizzati.

- **Nome schermata e posizione menu:** **Advanced Contact Form Pro > Moduli**
- **Azioni e impostazioni disponibili:**
  - **Vista elenco (Griglia):** Visualizza una tabella di tutti i moduli creati, mostrando il loro nome, ID e stato.
  - **Aggiungi nuovo modulo:** Clicca sul pulsante "Aggiungi nuovo modulo" per creare un modulo personalizzato completamente nuovo.
  - **Modifica modulo:** Clicca sull'icona "Modifica" accanto a un modulo nell'elenco per modificarne le impostazioni.
  - **Elimina modulo:** Clicca sull'icona "Elimina" per rimuovere un modulo.
  - **Campi di configurazione del modulo (quando si aggiunge/modifica):**
    - **Nome modulo:** Un nome interno chiaro per il tuo modulo (ad esempio, "Richiesta all'ingrosso", "Supporto prodotto").
    - **Shortcode:** Un codice unico (ad esempio, `[cfrompro id="1"]`) che utilizzerai per incorporare questo modulo specifico nelle pagine CMS o nelle descrizioni dei prodotti.
    - **Stato modulo:** Abilita/Disabilita il modulo. I moduli disabilitati non appariranno sulla vetrina.
    - **Email del destinatario (o più email) per QUESTO Modulo:** Puoi sovrascrivere l'email del destinatario globale (o più email) per questo modulo specifico. Questo è molto potente per l'instradamento delle richieste.
    - **Email di risposta automatica per QUESTO Modulo:** Sovrascrivi l'email di risposta automatica globale per questo modulo.
    - **Titolo email (per il proprietario del negozio) per QUESTO Modulo:** Sovrascrivi l'oggetto email globale per le notifiche da questo modulo.
    - **Campi personalizzati:** Qui è dove definisci i campi unici per *questo* modulo. Puoi aggiungere input di testo, aree di testo, menu a discesa, caselle di controllo, pulsanti radio, caricamenti di file e altro ancora. Per ogni campo personalizzato, puoi impostare:
      - **Etichetta:** Cosa vede il cliente (ad esempio, "Nome della tua azienda").
      - **Tipo:** (Testo, Area di testo, Selezione, Casella di controllo, Radio, File, ecc.).
      - **Obbligatorio:** Questo campo è obbligatorio?
      - **Placeholder:** Testo suggerimento all'interno del campo di input.
      - **Opzioni (per Selezione, Casella di controllo, Radio):** Definisci le scelte che i clienti possono selezionare.
      - **Regole di validazione:** (ad esempio, formato email, solo numeri).
    - **Impostazioni del trigger flottante:**
      - **Abilita trigger flottante:** Mostra un pulsante flottante sulla vetrina che apre questo modulo.
      - **Testo trigger:** Quale testo appare sul pulsante flottante (ad esempio, "Contattaci").
      - **Posizione trigger:** Dove appare il pulsante (ad esempio, sinistra, destra, in basso a sinistra).
      - **Icona trigger:** Scegli un'icona per il pulsante.
      - **Ritardo trigger (ms):** Quanto tempo attendere prima che appaia il pulsante flottante (ad esempio, 2000ms = 2 secondi).
      - **Colore trigger, Colore testo, Colore al passaggio del mouse:** Personalizza l'aspetto del pulsante.
- **Effetto delle modifiche:**
  - L'aggiunta/modifica di un modulo lo rende disponibile per l'incorporamento o come trigger flottante.
  - Le modifiche ai campi personalizzati influenzano direttamente ciò che i clienti vedono e compilano su quel modulo specifico.
  - Le modifiche alle email dei destinatari instradano le submission a diversi reparti.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Decidi che tipo di richiesta vuoi gestire (ad esempio, "Domanda di vendita all'ingrosso").
  2. Vai su **Moduli** e clicca su "Aggiungi nuovo modulo".
  3. Dagli un nome chiaro.
  4. Aggiungi tutti i campi personalizzati specifici di cui hai bisogno (ad esempio, Nome azienda, Partita IVA, Tipo di attività, Volume d'ordine previsto).
  5. Imposta un'email destinatario specifica se questo modulo deve andare a un team particolare (ad esempio, `ingrosso@tuonegozio.com`).
  6. Salva il modulo. Annota il suo shortcode.
  7. Incorpora lo shortcode in una pagina CMS pertinente (ad esempio, "Informazioni all'ingrosso").

#### 2.2.2 Gestione domande (Back Office > Advanced Contact Form Pro > Domande)

Questa schermata funge da tua casella di posta per tutte le submission dei moduli.

- **Nome schermata e posizione menu:** **Advanced Contact Form Pro > Domande**
- **Azioni e impostazioni disponibili:**
  - **Vista elenco (Griglia):** Visualizza una tabella di tutte le domande/richieste inviate.
    - **Colonne:** Mostra informazioni come Nome modulo, Nome cliente, Email, Argomento (se applicabile), Data di submission e Stato.
  - **Visualizza domanda:** Clicca sull'icona "Visualizza" (lente d'ingrandimento) accanto a una richiesta per vederne i dettagli completi.
    - **Vista dettagli:** Mostra tutte le informazioni inviate dal cliente, incluse le risposte ai campi personalizzati, gli allegati (con link per il download) e il modulo da cui proviene.
    - **Sezione Rispondi:** Ti consente di rispondere direttamente al cliente dall'interno del Back Office di PrestaShop. Questa risposta verrà inviata dall'email di contatto predefinita del tuo negozio.
    - **Cambia stato:** Puoi aggiornare lo stato di una richiesta (ad esempio, "Nuovo", "In corso", "Risolto").
  - **Elimina domanda:** Rimuovi una richiesta dall'elenco.
- **Effetto delle modifiche:**
  - La visualizzazione di una domanda ti consente di elaborare le richieste dei clienti in modo efficiente.
  - Rispondere da qui mantiene un registro della comunicazione (anche se il modulo non memorizza la cronologia completa delle risposte al suo interno, invia un'email standard).
  - La modifica dello stato ti aiuta a tenere traccia del progresso di ogni richiesta.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Controlla regolarmente questa sezione "Domande".
  2. Per ogni nuova richiesta, clicca su "Visualizza" per leggere i dettagli.
  3. Se è necessaria una risposta, usa la funzione "Rispondi".
  4. Aggiorna lo stato (ad esempio, a "In corso") per indicare che è in fase di gestione.
  5. Una volta risolto, cambia lo stato in "Risolto".

#### 2.2.3 index.php (cfrompro/controllers/admin/index.php)

Questo file è tipicamente un segnaposto o un reindirizzatore nei moduli PrestaShop e non rappresenta una schermata diretta e configurabile per il commerciante. Assicura che se qualcuno tenta di accedere direttamente alla directory `controllers/admin`, venga reindirizzato o venga intrapresa un'azione predefinita, prevenendo vulnerabilità di elencazione delle directory. I commercianti non interagiranno direttamente con questo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione principale del modulo** | Profilo di supporto del template | Classic | Adatta lo stile del modulo al tuo tema. |
| | Email di risposta automatica | `info@tuonegozio.com` | Indirizzo email per le conferme dei clienti. |
| | Titolo email (per il proprietario del negozio) | Nuova submission modulo di contatto | Oggetto per le tue email di notifica. |
| | Email del destinatario (o più email) | `contatto@tuonegozio.com` | Dove vengono inviate tutte le submission dei moduli (globalmente). |
| | BCC per l'email di notifica del negozio | Vuoto | Copia nascosta delle notifiche per il tracciamento interno. |
| | Conforme al GDPR | SÌ | Aggiunge la casella di controllo obbligatoria per il consenso alla politica sulla privacy. |
| | Pagina della politica sulla privacy | La tua pagina CMS della politica sulla privacy | Collega la casella di controllo GDPR alla tua politica. |
| | ReCaptcha (v2) | SÌ | Abilita Google reCAPTCHA per la protezione dallo spam. |
| | Chiave del sito ReCaptcha | La tua chiave del sito Google | Chiave pubblica per il widget reCAPTCHA. |
| | Chiave segreta ReCaptcha | La tua chiave segreta Google | Chiave privata per la verifica reCAPTCHA. |
| | URL Webhook (Slack/Discord) | Vuoto | Invia notifiche a Slack/Discord. |
| | CSS personalizzato (vetrina) | Vuoto | Aggiungi stili personalizzati ai tuoi moduli. |
| | Lunghezza minima della domanda (caratteri) | 10-20 | Caratteri minimi per il campo del messaggio principale. |
| | Lunghezza massima della domanda (caratteri) | 500-1000 | Caratteri massimi per il campo del messaggio principale. |
| | Consenti allegati immagine | SÌ | Abilita il caricamento di file sui moduli. |
| | Dimensione massima allegato (MB) | 2-5 | Dimensione massima per i file caricati. |
| | Durata messaggio di successo (ms) | 3000-5000 | Per quanto tempo la notifica di successo rimane visibile. |
| **Gestione moduli** | Nome modulo | Nome descrittivo | Nome interno per il tuo modulo personalizzato. |
| | Shortcode | `[cfrompro id="X"]` generato automaticamente | Codice per incorporare il modulo. |
| | Stato modulo | Abilitato | Attiva/disattiva il modulo. |
| | Email del destinatario (o più email) per QUESTO Modulo | Email specifiche | Sovrascrive il destinatario globale per questo modulo. |
| | Campi personalizzati | Varia | Definisci campi di input unici per ogni modulo. |
| | Abilita trigger flottante | NO (o SÌ per moduli specifici) | Mostra un pulsante flottante per aprire il modulo. |
| | Testo trigger | "Contattaci" | Testo sul pulsante flottante. |
| | Posizione trigger | Destra/Sinistra | Posizionamento del pulsante flottante. |
| **Gestione domande** | Visualizza domanda | N/A | Visualizza i dettagli completi di una richiesta del cliente. |
| | Rispondi | N/A | Invia una risposta via email al cliente. |
| | Cambia stato | Nuovo, In corso, Risolto | Tieni traccia della gestione delle richieste. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei moduli non hanno un aspetto corretto o lo stile è danneggiato.**
R:

-   **Controlla "Profilo di supporto del template":** Vai su **Moduli > Gestione moduli > Advanced Contact Form Builder Pro > Configura** e assicurati che il "Profilo di supporto del template" corrisponda al tuo tema PrestaShop attuale (ad esempio, 'Classic' per il tema predefinito).
-   **Svuota la cache di Smarty:** Vai su **Parametri avanzati > Prestazioni**, scorri fino a "Cache" e clicca su "Svuota cache". A volte i vecchi file di stile possono rimanere bloccati.
-   **CSS personalizzato:** Se hai aggiunto CSS personalizzato, ricontrollalo per errori. Rimuovilo temporaneamente per vedere se è la causa del problema.
-   **Conflitti del tema:** Se il problema persiste, il tuo tema potrebbe avere un conflitto. Contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu.

**D: Non ricevo notifiche via email quando viene inviato un modulo.**
R:

-   **Controlla le email del destinatario:** Vai su **Moduli > Gestione moduli > Advanced Contact Form Builder Pro > Configura** e verifica che le "Email del destinatario" siano corrette. Controlla anche le impostazioni del singolo modulo sotto **Advanced Contact Form Pro > Moduli** per vedere se un modulo specifico sovrascrive il destinatario globale.
-   **Controlla la cartella spam:** Le email potrebbero finire nella tua cartella spam o posta indesiderata.
-   **Impostazioni email del server:** Assicurati che le impostazioni email del tuo negozio PrestaShop siano configurate correttamente (**Parametri avanzati > E-mail**). Prova a inviare un'email normale da PrestaShop.
-   **Provider di hosting:** Il tuo provider di hosting potrebbe avere limiti o problemi di invio email. Controlla i log del tuo server o contatta il provider.

**D: reCAPTCHA non funziona o i moduli non vengono inviati con reCAPTCHA abilitato.**
R:

-   **Verifica le chiavi:** Ricontrolla la tua "Chiave del sito ReCaptcha" e la "Chiave segreta ReCaptcha" nella configurazione principale del modulo. Assicurati che non ci siano errori di battitura e che corrispondano a una configurazione reCAPTCHA v2 sul tuo account Google.
-   **Registrazione del dominio:** Assicurati che il nome di dominio del tuo negozio sia correttamente registrato nel tuo account Google reCAPTCHA.
-   **Problemi di rete:** Disabilita temporaneamente reCAPTCHA per vedere se i moduli vengono inviati. Se lo fanno, il problema è sicuramente con la configurazione di reCAPTCHA o la comunicazione con i server di Google.

**D: Come traduco i campi del modulo e i messaggi in altre lingue?**
R:

-   **Sistema di traduzione di PrestaShop:** Vai su **Internazionale > Traduzioni**.
-   **Tipo di traduzione:** Seleziona "Traduzioni dei moduli installati".
-   **Seleziona il tuo tema:** Scegli il tuo tema attuale.
-   **Seleziona la tua lingua:** Scegli la lingua in cui vuoi tradurre.
-   **Modulo:** Seleziona "cfrompro" (il nome tecnico del modulo).
-   Vedrai quindi un elenco di tutte le stringhe traducibili dal modulo, incluse le etichette dei campi, i messaggi di successo e i messaggi di errore. Traducili e salva.

**D: Il mio pulsante di attivazione flottante non appare.**
R:

-   **Abilita trigger:** Vai su **Advanced Contact Form Pro > Moduli**, modifica il modulo che vuoi attivare e assicurati che "Abilita trigger flottante" sia impostato su SÌ.
-   **Ritardo trigger:** Controlla l'impostazione "Ritardo trigger (ms)". Se è un numero elevato, potresti semplicemente dover aspettare più a lungo perché appaia.
-   **Conflitti del tema:** Alcuni temi potrebbero avere CSS che nasconde il pulsante o JavaScript che interferisce. Controlla la console per sviluppatori del tuo browser per errori.
-   **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo **Advanced Contact Form Builder Pro** (`cfrompro`) segue un modello MVC (Model-View-Controller) standard di PrestaShop, estendendo le classi core di PrestaShop per la sua funzionalità. Sfrutta `ObjectModel` per la gestione di moduli personalizzati e domande inviate, utilizza controller Admin dedicati per la gestione del Back Office e si integra con vari hook di PrestaShop per la visualizzazione nel front-office e le azioni di backend. I campi personalizzati sono gestiti tramite una classe dedicata e memorizzati come JSON.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `cfrompro/controllers/front/index.php`
    *   **Nome classe:** `CfromproIndexModuleFrontController` (probabilmente, basato sul nome del file)
    *   **Classe genitore:** `ModuleFrontController`
    *   **Responsabilità:** Questo controller è probabilmente responsabile della visualizzazione iniziale di un modulo se vi si accede tramite un URL diretto (anche se la maggior parte dei moduli sono incorporati o aperti tramite AJAX). Potrebbe anche gestire il rendering iniziale del trigger flottante o del modale contenente il modulo.
-   `cfrompro/controllers/front/question.php`
    *   **Nome classe:** `CfromproQuestionModuleFrontController` (probabilmente)
    *   **Classe genitore:** `ModuleFrontController`
    *   **Responsabilità:** Questo è il controller principale per l'elaborazione delle submission dei moduli. Riceve i dati POST dai moduli, esegue la validazione (inclusi reCAPTCHA, lunghezza dei campi, campi obbligatori, dimensione degli allegati), salva i dati inviati (domanda e campi personalizzati) nel database, invia notifiche email al proprietario del negozio e una risposta automatica al cliente, e potenzialmente attiva il webhook. Restituisce risposte JSON per le submission AJAX (ad esempio, messaggi di successo/errore).

#### Controller Admin Back-Office

-   `cfrompro/controllers/admin/AdminCfromproForm.php`
    *   **Nome classe:** `AdminCfromproFormController`
    *   **Classe genitore:** `ModuleAdminController`
    *   **Nome scheda:** "Moduli" sotto "Advanced Contact Form Pro"
    *   **Entità gestita:** `CfromproForm` (ipotetico `ObjectModel` per i moduli)
    *   **Responsabilità:** Gestisce le operazioni CRUD (Create, Read, Update, Delete) per i moduli personalizzati. Definisce la vista elenco (griglia) per i moduli e la struttura del modulo per l'aggiunta/modifica di un modulo. Questo controller gestisce il salvataggio delle impostazioni del modulo, inclusa la complessa struttura JSON per i campi personalizzati.
-   `cfrompro/controllers/admin/AdminCfromproQuestion.php`
    *   **Nome classe:** `AdminCfromproQuestionController`
    *   **Classe genitore:** `ModuleAdminController`
    *   **Nome scheda:** "Domande" sotto "Advanced Contact Form Pro"
    *   **Entità gestita:** `CfromproQuestion` (ipotetico `ObjectModel` per le domande inviate)
    *   **Responsabilità:** Gestisce le operazioni CRUD per le domande inviate. Visualizza l'elenco delle richieste, consente di visualizzare i dettagli delle singole domande e fornisce la funzionalità per rispondere ai clienti e modificare lo stato di una richiesta.
-   `cfrompro/controllers/admin/index.php`
    *   **Nome classe:** (Nessuno, tipicamente)
    *   **Classe genitore:** (Nessuno, tipicamente)
    *   **Responsabilità:** Questa è una pratica standard di PrestaShop per prevenire l'elencazione diretta delle directory. Di solito contiene un semplice `header('Location: ../../index.php?controller=AdminHome');` o simile per reindirizzare alla dashboard del Back Office. Non rappresenta un controller funzionale per la logica del modulo.

### 4.3 Classi e modelli core (`classes/`)

-   `cfrompro/classes/CfromproCustomFields.php`
    *   **Nome classe:** `CfromproCustomFields`
    *   **Classe genitore:** (Probabilmente `ObjectModel` o una classe base personalizzata per la gestione di dati complessi)
    *   **Tabella del database:** (Probabilmente `ps_cfrompro_form` se memorizza le definizioni dei campi personalizzati all'interno dell'oggetto modulo, o una tabella separata `ps_cfrompro_custom_field` se i campi sono entità autonome). Il dossier del modulo indica `cfrompro_form` e `cfrompro_question` come tabelle gestite, suggerendo che i campi personalizzati sono probabilmente serializzati all'interno della tabella `cfrompro_form`.
    *   **Campi `$definition`:** Se estende `ObjectModel`, definirebbe campi relativi alle proprietà dei campi personalizzati (ad esempio, `id_cfrompro_custom_field`, `id_cfrompro_form`, `type`, `label`, `required`, `options`, `validation`). Data la descrizione del modulo, è più probabile che i campi personalizzati siano memorizzati come stringa JSON all'interno della tabella `cfrompro_form`, e questa classe fornisce metodi helper per analizzare, validare e renderizzare questi campi.
    *   **Metodi pubblici chiave e logica di business:**
        *   Metodi per aggiungere, modificare ed eliminare definizioni di campi personalizzati all'interno di un modulo.
        *   Metodi per renderizzare i campi personalizzati nel template del front-office.
        *   Metodi per validare i dati dei campi personalizzati inviati.
        *   Metodi per serializzare/deserializzare le configurazioni dei campi personalizzati da/a JSON.

### 4.4 Asset JavaScript (`views/js/`)

-   `cfrompro/views/cfrompro.js`
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questo è il file JavaScript principale del front-office. Probabilmente gestisce:
        *   Visualizzazione e gestione del pulsante di attivazione flottante (eventi di click, ritardi).
        *   Apertura e chiusura del modale/popup del modulo.
        *   Submission AJAX dei moduli (raccolta dati, invio al controller `question.php`).
        *   Visualizzazione di messaggi di successo/errore (notifiche toast).
        *   Validazione lato client dei campi del modulo.
        *   Integrazione con reCAPTCHA v2 (rendering del widget, ottenimento del token di risposta).
        *   Aggiornamenti dinamici basati sui tipi di campo personalizzati (ad esempio, mostrare/nascondere opzioni per i menu a discesa).
-   `cfrompro/views/js/admin-button-style.js`
    *   **Ambito:** Back-office (AdminCfromproFormController).
    *   **Responsabilità:** Fornisce funzionalità JavaScript per stilizzare il pulsante di attivazione flottante all'interno dell'interfaccia di configurazione del modulo. Questo potrebbe includere selettori di colore, anteprime di icone e aggiornamenti in tempo reale di un'anteprima del pulsante.
-   `cfrompro/views/js/admin-form-layout.js`
    *   **Ambito:** Back-office (AdminCfromproFormController).
    *   **Responsabilità:** Gestisce il layout dinamico e la gestione dei campi personalizzati all'interno dell'interfaccia di creazione/modifica del modulo. Ciò includerebbe:
        *   Aggiunta di nuovi campi personalizzati (generazione dinamica di HTML per diversi tipi di campo).
        *   Riordino dei campi (drag-and-drop).
        *   Modifica delle proprietà dei campi (etichetta, tipo, obbligatorio, opzioni).
        *   Rimozione dei campi.
        *   Serializzazione della configurazione dei campi personalizzati in una stringa JSON prima di salvare il modulo.
-   `cfrompro/views/js/admin-icon-picker-data.js`
    *   **Ambito:** Back-office (AdminCfromproFormController).
    *   **Responsabilità:** Contiene i dati (ad esempio, un array di classi di icone o percorsi SVG) utilizzati dal selettore di icone per il pulsante di attivazione flottante.
-   `cfrompro/views/js/admin-icon-picker.js`
    *   **Ambito:** Back-office (AdminCfromproFormController).
    *   **Responsabilità:** Implementa l'interfaccia utente e la logica per la selezione di un'icona per il pulsante di attivazione flottante. Utilizza i dati da `admin-icon-picker-data.js` per visualizzare le icone disponibili e aggiorna l'icona selezionata nel modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `cfrompro/views/cfrompro.css`
    *   **Ambito:** Stile del cliente del front-office.
    *   **Responsabilità:** Fornisce lo stile principale per i moduli di contatto, il trigger flottante, i popup modali e i messaggi di successo/errore sulla vetrina. Definisce il layout generale, la tipografia, i colori e la reattività.
    *   **Selettori di classe CSS chiave:** `.cfrompro-form`, `.cfrompro-field`, `.cfrompro-trigger`, `.cfrompro-modal`, `.cfrompro-toast`.
-   `cfrompro/views/css/admin-button-style.css`
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Responsabilità:** Stila gli elementi relativi alla configurazione dell'aspetto del pulsante di attivazione flottante nel Back Office (ad esempio, selettori di colore, aree di anteprima delle icone).
-   `cfrompro/views/css/admin-custom-fields.css`
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Responsabilità:** Stila l'interfaccia per la gestione dei campi personalizzati all'interno del costruttore di moduli (ad esempio, maniglie di trascinamento, pannelli di configurazione dei campi).
-   `cfrompro/views/css/admin-form-layout.css`
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Responsabilità:** Fornisce il layout generale e lo stile per la pagina di creazione/modifica del modulo nel Back Office.
-   `cfrompro/views/css/admin-icon-picker.css`
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Responsabilità:** Stila l'interfaccia di selezione delle icone per il pulsante di attivazione flottante.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

-   `cfrompro/views/templates/hook/dashboard_recent_messages.tpl`
    *   **Hook:** `displaydashboardZoneTwo` (o hook della dashboard simile).
    *   **Output:** Un blocco nella dashboard di PrestaShop che visualizza le submission recenti dei moduli, fornendo una rapida panoramica per il commerciante.

#### Template admin (`views/templates/admin/`)

-   `cfrompro/views/templates/admin/button_style_block.tpl`
    *   **Ambito:** AdminCfromproFormController (pagina di modifica del modulo).
    *   **Output:** HTML per la sezione in cui il commerciante configura l'aspetto del pulsante di attivazione flottante (colori, testo, icona).
-   `cfrompro/views/templates/admin/conversation_reply.tpl`
    *   **Ambito:** AdminCfromproQuestionController (pagina di visualizzazione della domanda).
    *   **Output:** HTML per il modulo di risposta e la sezione di aggiornamento dello stato durante la visualizzazione di una domanda inviata.
-   `cfrompro/views/templates/admin/custom_fields_block.tpl`
    *   **Ambito:** AdminCfromproFormController (pagina di modifica del modulo).
    *   **Output:** Il contenitore principale e i controlli per aggiungere, modificare e organizzare i campi personalizzati all'interno di un modulo. Questo template probabilmente funziona in combinazione con `admin-form-layout.js`.
-   `cfrompro/views/templates/admin/form_layout_block.tpl`
    *   **Ambito:** AdminCfromproFormController (pagina di modifica del modulo).
    *   **Output:** Struttura del layout generale per la pagina di configurazione del modulo, che racchiude altri blocchi come campi personalizzati e stili dei pulsanti.
-   `cfrompro/views/templates/admin/question_extras.tpl`
    *   **Ambito:** AdminCfromproQuestionController (pagina di visualizzazione della domanda).
    *   **Output:** Visualizza dettagli aggiuntivi relativi a una domanda inviata, come allegati o metadati specifici.
-   `cfrompro/views/templates/admin/question_form_profile.tpl`
    *   **Ambito:** AdminCfromproQuestionController (pagina di visualizzazione della domanda).
    *   **Output:** Visualizza i dettagli sul modulo da cui è stata inviata la domanda.
-   `cfrompro/views/templates/admin/topic_options_block.tpl`
    *   **Ambito:** AdminCfromproFormController (pagina di modifica del modulo).
    *   **Output:** Se il modulo supporta argomenti predefiniti, questo template renderizzerebbe le opzioni per la loro configurazione.

#### Template front-office (`views/templates/front/` e root `views/`)

-   `cfrompro/views/cfrompro-extra-forms.tpl`
    *   **Hook:** Probabilmente `displayFooter` o `actionOutputHTMLBefore` per il rendering di moduli non incorporati direttamente ma che appaiono in modali.
    *   **Output:** Contiene la struttura HTML per i moduli destinati a essere visualizzati in una finestra modale, spesso attivata da un pulsante flottante.
-   `cfrompro/views/cfrompro-extra-trigger.tpl`
    *   **Hook:** Probabilmente `displayHeader` o `actionOutputHTMLBefore` per il rendering del pulsante di attivazione flottante.
    *   **Output:** L'HTML per il pulsante flottante che, quando cliccato, apre un modulo di contatto.
-   `cfrompro/views/cfrompro-form-body.tpl`
    *   **Ambito:** Utilizzato da altri template (ad esempio, `cfrompro-extra-forms.tpl`) o direttamente quando si incorpora un modulo tramite shortcode.
    *   **Output:** La struttura HTML principale per un singolo modulo di contatto, inclusi campi, etichette, reCAPTCHA, casella di controllo GDPR e pulsante di invio. Questo template viene popolato dinamicamente con campi personalizzati.
-   `cfrompro/views/classic/cfrompro-extra-forms.tpl`
    *   **Ambito:** Override specifico del tema per `cfrompro-extra-forms.tpl`.
    *   **Output:** Uguale a `cfrompro-extra-forms.tpl` ma specificamente adattato alla struttura HTML del tema Classic.
-   `cfrompro/views/classic/cfrompro-extra-trigger.tpl`
    *   **Ambito:** Override specifico del tema per `cfrompro-extra-trigger.tpl`.
    *   **Output:** Uguale a `cfrompro-extra-trigger.tpl` ma specificamente adattato al tema Classic.
-   `cfrompro/views/partials/cfrompro-custom-field-single.tpl`
    *   **Ambito:** Incluso da `cfrompro-form-body.tpl`.
    *   **Output:** Renderizza l'HTML per un singolo campo personalizzato in base al suo tipo (testo, area di testo, selezione, ecc.).
-   `cfrompro/views/partials/cfrompro-custom-fields.tpl`
    *   **Ambito:** Incluso da `cfrompro-form-body.tpl`.
    *   **Output:** Itera attraverso le definizioni dei campi personalizzati per un modulo e renderizza ciascuno utilizzando `cfrompro-custom-field-single.tpl`.
-   `cfrompro/views/partials/cfrompro-field-fragment.tpl`
    *   **Ambito:** Incluso da `cfrompro-form-body.tpl` o `cfrompro-custom-field-single.tpl`.
    *   **Output:** Un frammento riutilizzabile di HTML per elementi di campo comuni come etichette, messaggi di errore o wrapper.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

-   `ps_cfrompro_form`: Memorizza le definizioni di ogni modulo di contatto personalizzato creato dal modulo.
    *   `id_cfrompro_form`: Chiave primaria.
    *   `name`: Nome interno del modulo.
    *   `shortcode`: Identificatore unico per l'incorporamento.
    *   `active`: (booleano) Stato del modulo.
    *   `recipient_emails`: (testo) Email del destinatario sovrascritte per questo modulo.
    *   `autoresponder_email`: (testo) Email di risposta automatica sovrascritta per questo modulo.
    *   `email_title`: (testo) Oggetto dell'email sovrascritto per questo modulo.
    *   `custom_fields_json`: (testo/JSON) Stringa JSON serializzata contenente le definizioni di tutti i campi personalizzati per questo modulo (tipo, etichetta, obbligatorio, opzioni, validazione, ecc.).
    *   `trigger_enabled`: (booleano) Se il trigger flottante è attivo per questo modulo.
    *   `trigger_text`: (testo) Testo sul trigger flottante.
    *   `trigger_position`: (testo) Posizione del trigger flottante.
    *   `trigger_icon`: (testo) Classe dell'icona per il trigger.
    *   `trigger_delay_ms`: (int) Ritardo per l'apparizione del trigger.
    *   `trigger_color`, `trigger_text_color`, `trigger_hover_color`: (testo) Stile per il trigger.
-   `ps_cfrompro_question`: Memorizza ogni domanda/richiesta inviata.
    *   `id_cfrompro_question`: Chiave primaria.
    *   `id_cfrompro_form`: Chiave esterna a `ps_cfrompro_form`.
    *   `customer_name`: Nome del cliente che ha inviato.
    *   `customer_email`: Email del cliente che ha inviato.
    *   `customer_phone`: Numero di telefono (se visibile/obbligatorio).
    *   `topic`: Argomento selezionato (se visibile/obbligatorio).
    *   `message`: Il contenuto principale della domanda/messaggio.
    *   `submitted_data_json`: (testo/JSON) Stringa JSON serializzata contenente tutti i valori dei campi personalizzati inviati.
    *   `attachments`: (testo/JSON) Percorso/i dei file caricati.
    *   `ip_address`: Indirizzo IP del mittente.
    *   `date_add`: Timestamp di submission.
    *   `status`: (int/testo) Stato della richiesta (ad esempio, 0=Nuovo, 1=In corso, 2=Risolto).
-   `ps_configuration`: Le impostazioni del modulo sono memorizzate qui con chiavi come `cfrompro_TITLE`, `cfrompro_AUTORESPONDER`, `cfrompro_GDPR`, `cfrompro_recaptcha_sitekey`, ecc.

#### Tabella degli hook registrati

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionOutputHTMLBefore` | Prima che l'output HTML venga inviato al browser. | Iniezione di HTML del trigger flottante, moduli modali o CSS/JS personalizzati a livello globale. |
| `displaydashboardZoneTwo` | Renderizza il contenuto nella seconda zona della dashboard di PrestaShop. | Visualizzazione di un riepilogo delle submission recenti dei moduli nel Back Office. |
| `actionAdminControllerSetMedia` | Quando un Controller Admin imposta i suoi media (JS/CSS). | Accodamento di JS (`admin-button-style.js`, `admin-form-layout.js`, ecc.) e CSS (`admin-button-style.css`, `admin-custom-fields.css`, ecc.) specifici del Back Office per le pagine di configurazione del modulo. |
| `displayHeader` | Nella sezione `<head>` del front-office. | Accodamento di JS (`cfrompro.js`) e CSS (`cfrompro.css`) specifici del front-office, e potenzialmente script reCAPTCHA. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo al modulo **Advanced Contact Form Builder Pro**.
