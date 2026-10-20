---
title: "Facebook Login Connect - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Facebook Login Connect di MyPresta.eu."
sidebar:
  label: "Facebook Login Connect - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Login Connect su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-login-connect.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-login-connect/)
>
> ---


# Facebook Login Connect

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per la comunicazione con l'API di Facebook. Queste sono quasi sempre disponibili su qualsiasi hosting web moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale in cui imposterai il comportamento del pulsante di accesso a Facebook e dove appare.

#### Impostazioni generali

- **ID applicazione Facebook (App ID):**
  - **Cosa fa questa impostazione:** Questo è un identificatore univoco fornito da Facebook per la tua applicazione specifica. È fondamentale per il tuo negozio comunicare con il sistema di accesso di Facebook.
  - **Effetto della modifica di questa impostazione:** Senza un App ID valido, il pulsante di accesso a Facebook non funzionerà, poiché il tuo negozio non può autenticarsi con Facebook.
  - **Valore consigliato:** L'App ID che ottieni dal tuo account sviluppatore Facebook. Questo campo non può essere vuoto.
  - **Scenario/esempio del commerciante:** Devi creare un'app Facebook su [developers.facebook.com](https://developers.facebook.com/) per ottenere questo ID. Segui le istruzioni di Facebook per configurare un'app di base e abilitare l'accesso a Facebook.
- **Gruppo clienti predefinito per i nuovi account:**
  - **Cosa fa questa impostazione:** Quando un nuovo cliente si registra utilizzando Facebook, verrà automaticamente assegnato a questo gruppo clienti.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "Cliente" (predefinito):* I nuovi utenti Facebook diventano clienti regolari, soggetti ai prezzi e agli sconti standard del tuo negozio.
    - *Se impostato su un gruppo personalizzato (es. "Grossista"):* I nuovi utenti Facebook potrebbero accedere immediatamente a prezzi o contenuti speciali se quel gruppo ha regole specifiche.
  - **Valore consigliato:** `Cliente` (o il tuo gruppo clienti predefinito per le nuove registrazioni).
  - **Scenario/esempio del commerciante:** Se hai un gruppo clienti "VIP" con sconti speciali, potresti considerare di assegnare i nuovi utenti Facebook a un gruppo "Cliente" standard prima, quindi aggiornarli manualmente se soddisfano i criteri VIP.
- **Invia email di benvenuto ai nuovi clienti:**
  - **Cosa fa questa impostazione:** Controlla se PrestaShop invia la sua email di benvenuto standard ai clienti che si registrano tramite Facebook.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* I nuovi utenti Facebook ricevono un'email che conferma la creazione del loro account.
    - *Se disabilitato (No):* Non viene inviata alcuna email di benvenuto.
  - **Valore consigliato:** `Sì`. È buona pratica dare il benvenuto ai nuovi clienti e fornire loro i dettagli di accesso (anche se usano Facebook, potrebbero voler impostare una password in seguito).
  - **Scenario/esempio del commerciante:** Mantenere questa opzione abilitata garantisce che i nuovi clienti si sentano benvenuti e abbiano una registrazione del loro account, anche se non hanno bisogno di ricordare immediatamente una password.
- **Abilita accesso tramite browser in-app (per app mobili):**
  - **Cosa fa questa impostazione:** Questa impostazione è principalmente per i negozi accessibili tramite un'app mobile dedicata (non solo un browser mobile). Ottimizza il flusso di accesso a Facebook per i browser in-app.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato:* Migliora l'esperienza di accesso per gli utenti che accedono al tuo negozio tramite una WebView all'interno di un'app mobile.
    - *Se disabilitato:* Viene utilizzato il flusso di accesso standard del browser, che potrebbe essere meno fluido in un'app dedicata.
  - **Valore consigliato:** `No`, a meno che tu non abbia un'applicazione mobile specifica che incorpora il tuo negozio PrestaShop.
  - **Scenario/esempio del commerciante:** Se hai sviluppato un'app nativa iOS o Android che visualizza il contenuto del tuo negozio PrestaShop, abilitare questa opzione potrebbe essere necessario per un'esperienza di accesso a Facebook fluida all'interno di quell'app.
- **Visualizza accesso a Facebook in finestra pop-up:**
  - **Cosa fa questa impostazione:** Se il tuo tema utilizza una finestra pop-up per l'accesso, questa opzione consente al pulsante di accesso a Facebook di apparire all'interno di quel pop-up.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato:* Il pulsante di accesso a Facebook sarà disponibile all'interno del pop-up di accesso del tuo tema.
    - *Se disabilitato:* Il pulsante apparirà solo sulle pagine di accesso standard o in altre posizioni di hook.
  - **Valore consigliato:** `Sì`, se il tuo tema utilizza un pop-up di accesso.
  - **Scenario/esempio del commerciante:** Molti temi moderni utilizzano un pop-up di accesso rapido accessibile dall'intestazione. Abilitare questa opzione rende l'opzione di accesso a Facebook immediatamente visibile lì.
- **Lingua del pulsante di accesso a Facebook:**
  - **Cosa fa questa impostazione:** Ti consente di specificare la lingua per il pulsante di accesso a Facebook e i messaggi correlati.
  - **Effetto della modifica di questa impostazione:** Il testo del pulsante e qualsiasi prompt generato da Facebook appariranno nella lingua selezionata.
  - **Valore consigliato:** `Lingua predefinita di PrestaShop` (per corrispondere alla lingua principale del tuo negozio) o `Rilevamento automatico` se disponibile.
  - **Scenario/esempio del commerciante:** Se il tuo negozio opera in più lingue, potresti voler impostare questa opzione in modo che corrisponda alla lingua corrente del front-office per un'esperienza utente coerente.
- **Consenti a Facebook di identificare gli utenti (Avanzate):**
  - **Cosa fa questa impostazione:** Questa è un'impostazione avanzata relativa al tracciamento dell'identità di Facebook. Consente a Facebook di tracciare potenzialmente gli utenti sul tuo sito per scopi pubblicitari.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato:* Può fornire più dati per la pubblicità su Facebook, ma potrebbe avere implicazioni sulla privacy a seconda delle normative locali (es. GDPR).
    - *Se disabilitato:* Limita la capacità di Facebook di tracciare gli utenti sul tuo sito.
  - **Valore consigliato:** `No`, a meno che tu non abbia una strategia di marketing specifica che lo richieda e abbia affrontato la conformità alla privacy.
  - **Scenario/esempio del commerciante:** Consulta il tuo team di marketing e il consulente legale prima di abilitare questa opzione, soprattutto se operi in regioni con leggi severe sulla privacy dei dati.

#### Opzioni di visualizzazione (Dove mostrare il pulsante di accesso a Facebook)

Queste impostazioni controllano in quali aree specifiche (hook) del tuo negozio PrestaShop verrà visualizzato il pulsante di accesso a Facebook. Puoi abilitare o disabilitare ogni hook individualmente.

- **Visualizza in alto (fbl\_displayTop):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nella sezione superiore del tuo negozio, spesso vicino alla barra di ricerca o al logo.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nell'intestazione.
    - *Disabilitato:* Il pulsante è nascosto dall'intestazione.
  - **Valore consigliato:** `Sì`, per alta visibilità.
- **Visualizza nella colonna superiore (fbl\_displaytopColumn):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nell'area del contenuto principale, di solito sopra gli elenchi di prodotti principali o il contenuto della homepage.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nell'area del contenuto superiore.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `No`, a meno che tu non voglia un pulsante molto prominente sulla homepage.
- **Visualizza sulla homepage (fbl\_displayHome):**
  - **Cosa fa questa impostazione:** Mostra il pulsante specificamente sulla homepage del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare sulla homepage.
    - *Disabilitato:* Il pulsante è nascosto dalla homepage.
  - **Valore consigliato:** `Sì`, per incoraggiare la registrazione immediata.
- **Visualizza nella navigazione (fbl\_displayNav):**
  - **Cosa fa questa impostazione:** Mostra il pulsante all'interno della barra di navigazione principale, spesso accanto ai collegamenti "Il mio account" o "Contattaci".
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella navigazione.
    - *Disabilitato:* Il pulsante è nascosto dalla navigazione.
  - **Valore consigliato:** `Sì`, per un facile accesso da qualsiasi pagina.
- **Visualizza nella navigazione 1 (fbl\_displayNav1):**
  - **Cosa fa questa impostazione:** Simile a `displayNav`, ma si rivolge a un hook di navigazione specifico che alcuni temi utilizzano (spesso per la barra superiore).
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella prima area di navigazione.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `Sì`, se il tuo tema utilizza questo hook e desideri il pulsante lì.
- **Visualizza nella navigazione 2 (fbl\_displayNav2):**
  - **Cosa fa questa impostazione:** Simile a `displayNav`, ma si rivolge a un secondo hook di navigazione che alcuni temi utilizzano (spesso per la barra di navigazione principale).
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella seconda area di navigazione.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `Sì`, se il tuo tema utilizza questo hook e desideri il pulsante lì.
- **Visualizza nel carrello (fbl\_displayShoppingCart):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nella pagina di riepilogo del carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella pagina del carrello, consentendo un accesso rapido prima del checkout.
    - *Disabilitato:* Il pulsante è nascosto dalla pagina del carrello.
  - **Valore consigliato:** `Sì`, per semplificare il checkout per i clienti di ritorno.
- **Visualizza dopo il modulo di accesso cliente (fbl\_displayCustomerLoginFormAfter):**
  - **Cosa fa questa impostazione:** Mostra il pulsante direttamente sotto il modulo di accesso standard di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare come metodo di accesso alternativo nella pagina di accesso.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `Sì`, questa è una posizione privilegiata per le opzioni di accesso alternative.
- **Visualizza in alto informazioni personali (fbl\_displayPersonalInformationTop):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nella parte superiore della sezione "Informazioni personali" durante la creazione o la modifica dell'account.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella pagina delle informazioni personali.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `Sì`, per offrire l'accesso a Facebook come alternativa alla compilazione del modulo.
- **Visualizza nel carrello extra (fbl\_displayShoppingCartExtra):**
  - **Cosa fa questa impostazione:** Mostra il pulsante in un'area aggiuntiva nella pagina del carrello, spesso utilizzata per moduli o informazioni extra.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nell'area extra del carrello.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `No`, a meno che il tuo tema non utilizzi specificamente questo hook per le opzioni di accesso.
- **Visualizza nella colonna sinistra (fbl\_displayLeftColumn):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nella barra laterale sinistra del tuo negozio (se il tuo tema ne ha una).
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella colonna sinistra.
    - *Disabilitato:* Il pulsante è nascosto dalla colonna sinistra.
  - **Valore consigliato:** `No`, a meno che tu non voglia che sia visualizzato in modo prominente nella barra laterale.
- **Visualizza nella colonna destra (fbl\_displayRightColumn):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nella barra laterale destra del tuo negozio (se il tuo tema ne ha una).
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella colonna destra.
    - *Disabilitato:* Il pulsante è nascosto dalla colonna destra.
  - **Valore consigliato:** `No`, a meno che tu non voglia che sia visualizzato in modo prominente nella barra laterale.
- **Visualizza nel modulo di creazione account (fbl\_displayCreateAccountForm):**
  - **Cosa fa questa impostazione:** Mostra il pulsante direttamente all'interno del modulo di creazione account standard di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare come metodo di registrazione alternativo nella pagina di creazione account.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `Sì`, questa è una posizione cruciale per semplificare la registrazione.
- **Visualizza in alto creazione account (fbl\_displayCreateAccountTop):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nella parte superiore della pagina di creazione account, sopra i campi del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella parte superiore della pagina di creazione account.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `Sì`, per la massima visibilità nella pagina di registrazione.
- **Visualizza nel piè di pagina (fbl\_displayFooter):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nella sezione del piè di pagina del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nel piè di pagina.
    - *Disabilitato:* Il pulsante è nascosto dal piè di pagina.
  - **Valore consigliato:** `No`, generalmente non è una posizione primaria per i pulsanti di accesso.
- **Visualizza nell'intestazione (fbl\_displayHeader):**
  - **Cosa fa questa impostazione:** Mostra il pulsante nella sezione dell'intestazione del tuo negozio. Questa è una posizione molto comune ed efficace.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nell'intestazione.
    - *Disabilitato:* Il pulsante è nascosto dall'intestazione.
  - **Valore consigliato:** `Sì`, per alta visibilità su tutte le pagine.
- **Visualizza nella zona uno della dashboard (fbl\_displayDashboardZoneOne):**
  - **Cosa fa questa impostazione:** Questo hook è tipicamente per la visualizzazione di contenuti nella dashboard dell'account del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare nella dashboard del cliente.
    - *Disabilitato:* Il pulsante è nascosto da quest'area.
  - **Valore consigliato:** `No`, poiché i clienti sono già autenticati quando vedono la loro dashboard.
- **Visualizza nell'accesso pop-up (fbl\_popuplogin):**
  - **Cosa fa questa impostazione:** Si rivolge specificamente ai temi che utilizzano un modale pop-up per l'accesso.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare all'interno del pop-up di accesso.
    - *Disabilitato:* Il pulsante è nascosto dal pop-up di accesso.
  - **Valore consigliato:** `Sì`, se il tuo tema utilizza un pop-up di accesso.
- **Visualizza accesso a Facebook (fbl\_fblogin):**
  - **Cosa fa questa impostazione:** Questo è un hook generico per il pulsante di accesso a Facebook. Potrebbe essere utilizzato dal modulo internamente o dai temi per un posizionamento personalizzato.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il pulsante appare in questo hook generico.
    - *Disabilitato:* Il pulsante è nascosto da questo hook.
  - **Valore consigliato:** `Sì`, se altri hook specifici non funzionano o se desideri un fallback.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | ID applicazione Facebook (App ID) | *Il tuo App ID di Facebook* | Essenziale per la connessione a Facebook; il pulsante non funzionerà senza di esso. |
| Configurazione modulo | Gruppo clienti predefinito per i nuovi account | Cliente | Assegna i nuovi utenti Facebook a un gruppo clienti specifico. |
| Configurazione modulo | Invia email di benvenuto ai nuovi clienti | Sì | Determina se le nuove registrazioni Facebook ricevono un'email di benvenuto. |
| Configurazione modulo | Abilita accesso tramite browser in-app | No | Ottimizza l'accesso per le app mobili dedicate (non i browser mobili). |
| Configurazione modulo | Visualizza accesso a Facebook in finestra pop-up | Sì (se il tema usa pop-up) | Mostra il pulsante nel pop-up di accesso del tema. |
| Configurazione modulo | Lingua del pulsante di accesso a Facebook | Lingua predefinita di PrestaShop | Imposta la lingua per il pulsante e i prompt di Facebook. |
| Configurazione modulo | Consenti a Facebook di identificare gli utenti | No | Opzione di tracciamento avanzata; consulta legale/marketing. |
| Configurazione modulo | Visualizza in alto (fbl\_displayTop) | Sì | Mostra il pulsante nell'intestazione. |
| Configurazione modulo | Visualizza nella colonna superiore (fbl\_displaytopColumn) | No | Mostra il pulsante nell'area del contenuto principale, di solito sopra gli elenchi. |
| Configurazione modulo | Visualizza sulla homepage (fbl\_displayHome) | Sì | Mostra il pulsante specificamente sulla homepage. |
| Configurazione modulo | Visualizza nella navigazione (fbl\_displayNav) | Sì | Mostra il pulsante nella barra di navigazione principale. |
| Configurazione modulo | Visualizza nella navigazione 1 (fbl\_displayNav1) | Sì (se il tema usa) | Mostra il pulsante in un'area di navigazione superiore specifica. |
| Configurazione modulo | Visualizza nella navigazione 2 (fbl\_displayNav2) | Sì (se il tema usa) | Mostra il pulsante in un'area di navigazione principale specifica. |
| Configurazione modulo | Visualizza nel carrello (fbl\_displayShoppingCart) | Sì | Mostra il pulsante nella pagina di riepilogo del carrello. |
| Configurazione modulo | Visualizza dopo il modulo di accesso cliente | Sì | Mostra il pulsante sotto il modulo di accesso standard. |
| Configurazione modulo | Visualizza in alto informazioni personali | Sì | Mostra il pulsante nella parte superiore della pagina delle informazioni personali. |
| Configurazione modulo | Visualizza nel carrello extra | No | Mostra il pulsante in un'area aggiuntiva del carrello. |
| Configurazione modulo | Visualizza nella colonna sinistra (fbl\_displayLeftColumn) | No | Mostra il pulsante nella barra laterale sinistra. |
| Configurazione modulo | Visualizza nella colonna destra (fbl\_displayRightColumn) | No | Mostra il pulsante nella barra laterale destra. |
| Configurazione modulo | Visualizza nel modulo di creazione account | Sì | Mostra il pulsante all'interno del modulo di creazione account. |
| Configurazione modulo | Visualizza in alto creazione account | Sì | Mostra il pulsante nella parte superiore della pagina di creazione account. |
| Configurazione modulo | Visualizza nel piè di pagina (fbl\_displayFooter) | No | Mostra il pulsante nel piè di pagina. |
| Configurazione modulo | Visualizza nell'intestazione (fbl\_displayHeader) | Sì | Mostra il pulsante nella sezione dell'intestazione. |
| Configurazione modulo | Visualizza nella zona uno della dashboard | No | Mostra il pulsante nella dashboard dell'account del cliente. |
| Configurazione modulo | Visualizza nell'accesso pop-up (fbl\_popuplogin) | Sì (se il tema usa pop-up) | Mostra il pulsante all'interno del modale pop-up di accesso. |
| Configurazione modulo | Visualizza accesso a Facebook (fbl\_fblogin) | Sì | Hook generico per il pulsante di accesso a Facebook. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il pulsante di accesso a Facebook appare, ma non succede nulla quando ci clicco, oppure mostra un errore.**
R1: Questo indica quasi sempre un problema con il tuo ID app di Facebook o con la configurazione dell'app di Facebook stessa.
- **Controlla il tuo ID app di Facebook:** Vai alla configurazione del tuo modulo in PrestaShop e verifica che l'"ID applicazione Facebook" sia inserito correttamente.
- **Controlla le impostazioni della tua app di Facebook:** Accedi a [developers.facebook.com](https://developers.facebook.com/).
- Assicurati che la tua app sia "Live" (non in modalità Sviluppo).
- Vai su "Accesso a Facebook" > "Impostazioni" e assicurati che "Accesso OAuth client" e "Accesso OAuth web" siano abilitati.
- Sotto "URI di reindirizzamento OAuth validi", devi *aggiungere* il dominio completo del tuo negozio (es. `https://www.iltuonegozio.com/`). A volte, potresti anche dover aggiungere `https://www.iltuonegozio.com/module/fblogin/index` o `https://www.iltuonegozio.com/module/fblogin/loginloader` a seconda della tua versione di PrestaShop e della struttura dell'URL.
- Assicurati che il tuo "URL della politica sulla privacy" e "URL dei termini di servizio" siano impostati nelle "Impostazioni di base" della tua app di Facebook.
- **Svuota la cache:** Dopo aver apportato modifiche, svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).

**D2: I nuovi clienti si registrano tramite Facebook, ma i loro nomi o le loro email non appaiono correttamente.**
R2: Il modulo estrae le informazioni del profilo pubblico da Facebook.
- Assicurati che il cliente abbia concesso l'autorizzazione alla tua app per accedere al suo profilo di base e all'email.
- L'API di Facebook fornisce nome, cognome ed email. Se questi sono mancanti o errati, di solito è un problema nelle impostazioni sulla privacy del profilo Facebook del cliente o un raro problema dell'API.
- Il modulo crea un nuovo account se non viene trovata alcuna email corrispondente. Se un'email esiste già nel tuo database PrestaShop, il modulo dovrebbe tentare di accedere l'utente a quell'account esistente.

**D3: Il pulsante di Facebook non appare nella posizione che mi aspetto, anche dopo aver abilitato l'hook.**
R3:
- **Svuota la cache:** Svuota sempre la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) dopo aver modificato le impostazioni degli hook.
- **Compatibilità del tema:** Alcuni temi personalizzati potrebbero sovrascrivere gli hook standard di PrestaShop o avere strutture uniche. Se il pulsante non appare, il tuo tema potrebbe non visualizzare attivamente quell'hook specifico. Potrebbe essere necessario consultare lo sviluppatore del tuo tema o un webmaster per integrarlo manualmente nei file `.tpl` del tuo tema.
- **Controlla le posizioni del modulo:** Vai su Design > Posizioni (o Moduli > Posizioni nelle versioni precedenti) e cerca `fblogin`. Assicurati che il modulo sia "agganciato" alle posizioni desiderate. Se non lo è, puoi "Trapiantare un modulo" manualmente all'hook corretto.

**D4: I clienti che si sono registrati con Facebook possono impostare una password in seguito per accedere direttamente?**
R4: Sì. Una volta creato un account tramite Facebook, è un account cliente PrestaShop standard.
- I clienti possono utilizzare il link "Password dimenticata" nella pagina di accesso del tuo negozio. Riceveranno un'email per impostare una nuova password, consentendo loro di accedere direttamente con la loro email e la nuova password, anche senza Facebook.

**D5: Questo modulo supporta più lingue per il pulsante?**
R5: Sì, il modulo ha un'impostazione per la "Lingua del pulsante di accesso a Facebook". Puoi impostarla in modo che corrisponda alla lingua predefinita del tuo negozio, o in alcuni casi, l'SDK di Facebook potrebbe rilevare automaticamente la lingua del browser dell'utente.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `Facebook Login Connect` integra l'SDK JavaScript di Facebook per facilitare l'autenticazione dell'utente. Opera principalmente agganciandosi a vari punti di visualizzazione del front-office per renderizzare il pulsante di accesso a Facebook. In caso di accesso a Facebook riuscito, un controller frontale gestisce il callback, recupera i dati dell'utente da Facebook e accede a un cliente PrestaShop esistente o ne crea uno nuovo. Il modulo sfrutta la classe `Module` di PrestaShop per la configurazione e la gestione degli hook, con classi personalizzate minime, affidandosi pesantemente al file principale `fblogin.php` per la logica centrale.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `controllers/front/index.php`
    - **Nome classe:** `FbloginIndexModuleFrontController`
    - **Classe genitore:** `ModuleFrontController`
    - **Responsabilità:** Questo controller funge da endpoint di callback primario per il processo di autenticazione di Facebook. Dopo che un utente ha effettuato l'accesso con successo tramite Facebook, Facebook reindirizza a questo controller. Gestisce il recupero del token di accesso di Facebook, recupera i dati del profilo utente (nome, email) e quindi accede a un cliente PrestaShop esistente o ne crea uno nuovo. Quindi reindirizza l'utente alla sua pagina account o alla homepage.
  - `controllers/front/loginloader.php`
    - **Nome classe:** `FbloginLoginloaderModuleFrontController`
    - **Classe genitore:** `ModuleFrontController`
    - **Responsabilità:** Questo controller è probabilmente un fallback o un punto di ingresso alternativo per il processo di accesso a Facebook, potenzialmente utilizzato per scenari specifici o versioni precedenti di PrestaShop. Eseguirebbe attività di autenticazione e gestione degli utenti simili a `index.php`.
- **Controller Admin Back-Office**:

  - Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

- Nessuno. Il modulo non definisce alcuna classe `ObjectModel` personalizzata o altre classi di logica di business principali nella directory `classes/`. Tutta la logica principale è incapsulata all'interno della classe `Fblogin` in `fblogin.php`.

### 4.4 Risorse JavaScript (`views/js/`)

- `views/js/fblogin4.js`
  - **Ambito:** Front-office.
  - **Responsabilità:** Questo script è responsabile dell'inizializzazione dell'SDK JavaScript di Facebook. Carica l'SDK, imposta la configurazione `FB.init` (inclusi l'App ID e le autorizzazioni desiderate) e gestisce la chiamata `FB.login` quando si fa clic sul pulsante di accesso a Facebook. Probabilmente ascolta l'evento `auth.statusChange` per rilevare gli stati di accesso/disconnessione e reindirizza l'utente al controller frontale PrestaShop appropriato (`index.php` o `loginloader.php`) dopo un'autenticazione riuscita. Gestisce anche la visualizzazione del pulsante di accesso a Facebook e la sua interazione.

### 4.5 Fogli di stile CSS (`views/css/`)

- `css.css`
  - **Ambito:** Front-office.
  - **Responsabilità:** Questo è probabilmente un foglio di stile generico per il modulo, che fornisce uno stile di base per il pulsante di accesso a Facebook e qualsiasi elemento UI correlato.
- `views/css/fblogin.css`
  - **Ambito:** Front-office.
  - **Responsabilità:** Fornisce regole di stile specifiche per il pulsante di accesso a Facebook e il suo contenitore, garantendo un aspetto coerente tra i diversi temi. Potrebbe includere stili per le dimensioni del pulsante, il colore, gli effetti al passaggio del mouse e l'allineamento.
- `views/css/fblogin17.css`
  - **Ambito:** Front-office.
  - **Responsabilità:** Questo foglio di stile contiene probabilmente override specifici o stili aggiuntivi personalizzati per PrestaShop 1.7.x e versioni più recenti, affrontando potenziali differenze di layout o stile nelle nuove strutture dei temi.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:

  - `createAccountForm.tpl`: Renderizza il pulsante di accesso a Facebook all'interno del modulo di creazione account standard.
  - `createAccountTop.tpl`: Renderizza il pulsante di accesso a Facebook nella parte superiore della pagina di creazione account.
  - `dashboardZoneOne.tpl`: Renderizza il pulsante di accesso a Facebook nella zona uno della dashboard del cliente (meno comune per l'accesso, ma disponibile).
  - `displayCustomerLoginFormAfter.tpl`: Renderizza il pulsante di accesso a Facebook direttamente dopo il modulo di accesso cliente standard.
  - `displayNav.tpl`: Renderizza il pulsante di accesso a Facebook nella barra di navigazione principale.
  - `displayPersonalInformationTop.tpl`: Renderizza il pulsante di accesso a Facebook nella parte superiore della pagina delle informazioni personali.
  - `displayPopUpLogin.tpl`: Renderizza il pulsante di accesso a Facebook all'interno di un modale pop-up di accesso del tema.
  - `fblogin.tpl`: Un template generico per il pulsante di accesso a Facebook, potenzialmente utilizzato da `displayfblogin` o come fallback.
  - `footer.tpl`: Renderizza il pulsante di accesso a Facebook nella sezione del piè di pagina del negozio.
  - `header.tpl`: Renderizza il pulsante di accesso a Facebook nell'intestazione del negozio.
  - `home.tpl`: Renderizza il pulsante di accesso a Facebook sulla homepage.
  - `leftcolumn.tpl`: Renderizza il pulsante di accesso a Facebook nella barra laterale sinistra.
  - `rightcolumn.tpl`: Renderizza il pulsante di accesso a Facebook nella barra laterale destra.
  - `shoppingCart.tpl`: Renderizza il pulsante di accesso a Facebook nella pagina del carrello.
  - `shoppingCartExtra.tpl`: Renderizza il pulsante di accesso a Facebook in un'area extra della pagina del carrello.
  - `top.tpl`: Renderizza il pulsante di accesso a Facebook nella sezione superiore del negozio.
  - `topColumn.tpl`: Renderizza il pulsante di accesso a Facebook nell'area del contenuto principale, tipicamente sopra gli elenchi di prodotti.
- **Template admin (`views/templates/admin/`)**:

  - Nessuno. La configurazione del modulo viene renderizzata direttamente tramite `getContent()` in `fblogin.php` utilizzando gli helper standard dei moduli di PrestaShop.
- **Template front-office (`views/templates/front/`)**:

  - Nessuno. Tutta la visualizzazione del front-office è gestita tramite template hook.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `FBL_APPID`, `FBL_GROUPID`, `FBL_POPUP_LOGIN`, `FBL_DISPLAYTOP`, ecc.
- **Tabella degli hook registrati**:

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayRightColumn` | Renderizza il contenuto nella barra laterale destra. | Visualizza il pulsante di accesso a Facebook nella colonna destra. |
| `displaypopuplogin` | Renderizza il contenuto all'interno di un pop-up di accesso del tema. | Visualizza il pulsante di accesso a Facebook nel pop-up di accesso. |
| `displayCreateAccountForm` | Renderizza il contenuto all'interno del modulo di creazione account cliente. | Visualizza il pulsante di accesso a Facebook come metodo di registrazione alternativo. |
| `displayPersonalInformationTop` | Renderizza il contenuto nella parte superiore della pagina delle informazioni personali. | Visualizza il pulsante di accesso a Facebook per una registrazione/accesso rapido. |
| `displayTop` | Renderizza il contenuto nella sezione superiore del negozio. | Visualizza il pulsante di accesso a Facebook nella barra superiore dell'intestazione. |
| `displayCreateAccountTop` | Renderizza il contenuto nella parte superiore della pagina di creazione account. | Visualizza il pulsante di accesso a Facebook sopra il modulo di registrazione. |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` dell'HTML e potenzialmente elementi visibili dell'intestazione. | Inietta il JavaScript dell'SDK di Facebook e visualizza il pulsante di accesso nell'intestazione. |
| `displayNav` | Renderizza il contenuto nella barra di navigazione principale. | Visualizza il pulsante di accesso a Facebook nella navigazione. |
| `displayDashboardZoneOne` | Renderizza il contenuto nella prima zona della dashboard del cliente. | Visualizza il pulsante di accesso a Facebook (meno comune per gli utenti autenticati). |
| `displayNav2` | Renderizza il contenuto in una barra di navigazione secondaria (dipendente dal tema). | Visualizza il pulsante di accesso a Facebook nella navigazione secondaria. |
| `displayShoppingCart` | Renderizza il contenuto nella pagina di riepilogo del carrello. | Visualizza il pulsante di accesso a Facebook per un accesso rapido prima del checkout. |
| `displayTopColumn` | Renderizza il contenuto nell'area del contenuto principale, tipicamente sopra gli elenchi. | Visualizza il pulsante di accesso a Facebook nella colonna del contenuto superiore. |
| `displayFooter` | Renderizza il contenuto nel piè di pagina del negozio. | Visualizza il pulsante di accesso a Facebook nel piè di pagina. |
| `displayfblogin` | Un hook personalizzato definito dal modulo stesso. | Fornisce un punto flessibile per i temi per integrare il pulsante di accesso a Facebook. |
| `displayHome` | Renderizza il contenuto sulla homepage del negozio. | Visualizza il pulsante di accesso a Facebook sulla homepage. |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra. | Visualizza il pulsante di accesso a Facebook nella colonna sinistra. |
| `displayCustomerLoginFormAfter` | Renderizza il contenuto direttamente dopo il modulo di accesso cliente standard. | Visualizza il pulsante di accesso a Facebook come metodo di accesso alternativo. |
| `displayShoppingCartExtra` | Renderizza il contenuto in un'area extra della pagina del carrello. | Visualizza il pulsante di accesso a Facebook in un'area aggiuntiva del carrello. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda relativa al modulo "Facebook Login Connect".
