---
title: "Tassi di cambio della Banca Centrale Europea - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Tassi di cambio della Banca Centrale Europea di MyPresta.eu."
sidebar:
  label: "Tassi di cambio della Banca Centrale Europea - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo European Central Bank currency rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/european-central-bank-currency-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/european-central-bank-currency-rates/)
>
> ---


# Tassi di cambio della Banca Centrale Europea

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni, e sono quasi universalmente disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alle impostazioni principali del modulo. Qui è dove controlli come e quando vengono aggiornati i tassi di cambio.

La schermata di configurazione presenterà tipicamente un modulo con opzioni per abilitare/disabilitare la funzionalità del modulo e potenzialmente un modo per attivare manualmente un aggiornamento o impostare un cron job.

**URL del Cronjob:**

- **Cosa fa questa impostazione:** Visualizza un URL unico che, quando viene richiamato, attiva il modulo per recuperare gli ultimi tassi di cambio dalla Banca Centrale Europea e aggiornarli nel tuo negozio PrestaShop. Questo è il meccanismo principale per gli aggiornamenti automatici.
- **Effetto della modifica di questa impostazione:** Questo è un URL di sola lettura generato dal modulo. Non lo modifichi direttamente.
  - *Quando usato in un cron job:* I tuoi tassi di cambio verranno aggiornati automaticamente a intervalli regolari senza alcun intervento manuale.
  - *Quando non usato:* I tassi si aggiorneranno solo se clicchi manualmente il pulsante "Aggiorna ora" (se disponibile) o se viene utilizzato il meccanismo di aggiornamento della valuta predefinito di PrestaShop, meno affidabile.
- **Valore consigliato:** Copia questo URL e impostalo come cron job sul tuo server di hosting. Questo è il modo più efficiente e affidabile per mantenere i tuoi tassi aggiornati.
- **Scenario / esempio del commerciante:** Vuoi che i tuoi tassi di cambio si aggiornino ogni giorno alle 3 del mattino. Copi questo URL e lo aggiungi allo scheduler dei cron job del tuo pannello di controllo hosting, impostato per essere eseguito quotidianamente alle 3 del mattino.

**Pulsante "Aggiorna ora" (se presente):**

- **Cosa fa questa impostazione:** Questo è un trigger manuale per recuperare e aggiornare immediatamente tutti i tassi di cambio dalla BCE.
- **Effetto della modifica di questa impostazione:**
  - *Quando cliccato:* Il modulo si connetterà istantaneamente alla BCE, recupererà gli ultimi tassi di cambio e li applicherà alle valute del tuo negozio. Questo è utile per aggiornamenti immediati o test.
- **Valore consigliato:** Usalo per i test di configurazione iniziale o se hai bisogno di un aggiornamento immediato al di fuori dei tuoi cron job programmati. Per gli aggiornamenti regolari, affidati al cron job.
- **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi assicurarti che funzioni correttamente. Clicchi su "Aggiorna ora" e poi controlli i tuoi tassi di cambio in PrestaShop per confermare che sono cambiati.

**Configurazione generale del modulo (se presente, ad es. Abilita/Disabilita):**

- **Cosa fa questa impostazione:** Questo è un interruttore standard del modulo PrestaShop per attivare o disattivare la funzionalità principale del modulo.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Il modulo sarà attivo e il suo URL del cron job funzionerà, consentendo aggiornamenti automatici delle valute.
  - *Quando disabilitato:* Il modulo non eseguirà alcun aggiornamento e l'URL del cron job non funzionerà. I tuoi tassi di cambio non verranno aggiornati da questo modulo.
- **Valore consigliato:** **SÌ** (Abilitato) per garantire che i tuoi tassi di cambio vengano aggiornati automaticamente.
- **Scenario / esempio del commerciante:** Vuoi che il modulo gestisca i tuoi tassi di cambio, quindi ti assicuri che sia abilitato. Se per qualche motivo volessi interrompere temporaneamente gli aggiornamenti automatici, lo disabiliteresti.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo non introduce nuove schermate di amministrazione dedicate o controller personalizzati oltre alla sua pagina di configurazione principale. Tutte le interazioni avvengono direttamente sul modulo di configurazione del modulo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | URL del Cronjob | Copia e configura sull'hosting | Attiva gli aggiornamenti automatici dei tassi di cambio dalla BCE. Essenziale per un funzionamento senza intervento manuale. |
| Pagina di configurazione del modulo | Pulsante Aggiorna ora | Usa per test/aggiornamento manuale | Recupera e applica immediatamente gli ultimi tassi BCE. |
| Pagina di configurazione del modulo | Modulo Abilitato/Disabilitato | Abilitato (SÌ) | Attiva o disattiva la funzionalità di aggiornamento valuta del modulo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei tassi di cambio non si aggiornano automaticamente. Cosa devo controllare?**
R:

1. **Configurazione del Cron Job:** Il problema più comune è un cron job configurato in modo errato. Ricontrolla l'URL che hai usato nel tuo pannello di hosting e assicurati che la pianificazione sia attiva e corretta.
2. **Modulo Abilitato:** Assicurati che il modulo "Tassi di cambio della Banca Centrale Europea" sia abilitato nel tuo Back Office di PrestaShop (**Moduli > Gestione moduli**).
3. **Versione PHP:** Assicurati che la tua versione di PHP rientri nell'intervallo di compatibilità del modulo (PHP 5.6 - 8.5).
4. **Log del Server:** Controlla i log dei cron job del tuo server (se il tuo host li fornisce) per eventuali errori quando il cron job tenta di essere eseguito.
5. **Aggiornamento Manuale:** Prova a cliccare il pulsante "Aggiorna ora" nella pagina di configurazione del modulo. Se questo funziona, il problema è sicuramente nella configurazione del tuo cron job.

**D: I tassi sono stati aggiornati, ma sembrano errati o diversi da quanto mi aspettavo.**
R:

1. **Fonte BCE:** Questo modulo recupera i tassi direttamente dalla Banca Centrale Europea. Questi sono tassi interbancari ufficiali, che potrebbero differire leggermente dai tassi al consumo che vedi su Google o altri siti finanziari a causa di commissioni bancarie, spread o tempi di aggiornamento diversi.
2. **Valuta Base:** Assicurati che la valuta predefinita del tuo PrestaShop sia configurata correttamente. Il modulo aggiorna i tassi rispetto alla valuta base.
3. **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**) dopo un aggiornamento per assicurarti di visualizzare i dati più recenti.

**D: Questo modulo funziona con temi personalizzati?**
R: Sì, assolutamente. Questo modulo funziona in background per aggiornare i dati (tassi di cambio) nel tuo database. Non produce alcun elemento visivo né modifica il design del tuo tema, quindi è completamente compatibile con qualsiasi tema PrestaShop.

**D: Con quale frequenza dovrei aggiornare i tassi di cambio?**
R: Per la maggior parte dei negozi e-commerce, un aggiornamento giornaliero è sufficiente. Se gestisci articoli di alto valore o operi in mercati altamente volatili, potresti considerare di aggiornare due volte al giorno. La BCE di solito pubblica i suoi tassi di riferimento una volta al giorno, intorno alle 16:00 CET.

**D: Vedo un "500 Internal Server Error" quando cerco di accedere direttamente all'URL del cron job.**
R: Questo di solito indica un errore PHP. Controlla i log degli errori PHP del tuo server per dettagli più specifici. Le cause comuni potrebbero essere permessi di file errati, un'estensione PHP mancante o un conflitto con un altro modulo. Contatta il tuo provider di hosting o uno sviluppatore con i dettagli del log degli errori.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Tassi di cambio della Banca Centrale Europea" (`ecbrates`) è un modulo PrestaShop leggero progettato principalmente per automatizzare l'aggiornamento dei tassi di cambio di `ps_currency`. Segue un semplice modello di progettazione:

- Un singolo file principale del modulo (`cronjob.php`) gestisce l'installazione, la disinstallazione e la logica principale per il recupero e l'aggiornamento dei tassi di cambio.
- Il modulo espone un metodo `getContent()` per la sua configurazione nel Back Office, che renderizza un template di base.
- La funzionalità principale viene attivata tramite una chiamata diretta al file `cronjob.php` del modulo, tipicamente da un cron job lato server, bypassando il routing standard del controller front/admin di PrestaShop per efficienza.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza i controller standard di PrestaShop Front-Office o Back-Office Admin. La sua logica di aggiornamento principale è direttamente accessibile tramite il file `cronjob.php`, che agisce come uno script autonomo quando chiamato tramite l'URL del cron.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate né estende `ObjectModel`. Tutta la logica è contenuta nel file principale `ecbrates/cronjob.php`. Interagisce direttamente con la classe `Currency` e la classe `Configuration` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template amministrativi (`views/templates/admin/`)**:
  - `ecbrates/views/admin.tpl`: Questo template viene renderizzato dal metodo `getContent()` del file principale del modulo. Visualizza il modulo di configurazione del modulo, inclusi l'URL del cron job e potenzialmente un pulsante di aggiornamento manuale. È un template semplice per le impostazioni del modulo.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle di database personalizzate.
  - Interagisce con la tabella standard `ps_currency` di PrestaShop per aggiornare la colonna `conversion_rate` per le valute attive.
  - Memorizza la sua configurazione (ad esempio, lo stato abilitato del modulo) nella tabella `ps_configuration`, utilizzando chiavi come `ECBRATES_LAST_UPDATE` o simili, sebbene le chiavi specifiche non siano esplicitamente dettagliate nelle informazioni fornite.
- **Tabella degli hook registrati**:
  Questo modulo non si registra esplicitamente a nessun hook standard di PrestaShop nel senso tradizionale (ad esempio, `displayHeader`, `actionValidateOrder`) per la sua funzionalità principale. Il suo meccanismo primario è una chiamata diretta al suo file `cronjob.php`.

  Tuttavia, come modulo PrestaShop, utilizza implicitamente:

  | Nome dell'Hook | Tempo di Esecuzione | Scopo Tecnico |
  | --- | --- | --- |
  | `install()` | Durante l'installazione del modulo | Crea voci di configurazione, potenzialmente imposta i tassi iniziali. |
  | `uninstall()` | Durante la disinstallazione del modulo | Pulisce le voci di configurazione. |
  | `getContent()` | Quando si accede alla configurazione del modulo nel BO | Renderizza il modulo di configurazione del modulo. |

  La funzionalità principale del modulo (recupero e aggiornamento dei tassi) viene attivata dall'accesso HTTP diretto a `cronjob.php`, non da un hook di PrestaShop.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo "Tassi di cambio della Banca Centrale Europea", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). È possibile scaricare le ultime versioni del modulo dalla cronologia degli ordini. Per il supporto, si prega di utilizzare i canali di supporto dedicati forniti sul sito web di MyPresta.eu.
