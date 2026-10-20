---
title: "Chiedi informazioni sul prodotto - moduli di contatto pro - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Chiedi informazioni sul prodotto - moduli di contatto pro di MyPresta.eu."
sidebar:
  label: "Chiedi informazioni sul prodotto - moduli di contatto pro - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Ask about product - contact forms pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-contact-forms-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/ask-about-product-contact-forms-pro/)
>
> ---


# Chiedi informazioni sul prodotto - moduli di contatto pro

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono necessarie per il corretto funzionamento del modulo, in particolare per funzionalità come reCAPTCHA e webhook. Queste sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Questo modulo offre ampie opzioni di personalizzazione per adattare i moduli di contatto alle tue esigenze specifiche. Esamineremo ogni schermata di configurazione e impostazione.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è l'area di configurazione principale per il modulo, accessibile direttamente dopo l'installazione o navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto a "Chiedi informazioni sul prodotto - moduli di contatto pro".

#### Impostazioni generali

- **Profilo di supporto del template**

  - **Cosa fa questa impostazione:** Questa impostazione ti consente di selezionare un profilo di template predefinito che meglio si adatta al tuo tema PrestaShop. Temi diversi potrebbero richiedere stili o aggiustamenti strutturali diversi affinché il modulo venga visualizzato correttamente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su "Classic" (o simile):* Il modulo utilizzerà template e stili ottimizzati per il tema PrestaShop Classic predefinito o temi basati su di esso.
    - *Quando impostato su un profilo tema specifico:* Il modulo caricherà template e CSS progettati per integrarsi senza problemi con quel particolare tema, garantendo una migliore coerenza visiva.
  - **Valore consigliato:** Scegli il profilo che corrisponde al tuo tema PrestaShop attivo. Se non sei sicuro, inizia con "Classic" e regola se si verificano problemi di stile.
  - **Scenario/esempio del commerciante:** Se stai utilizzando un tema personalizzato, potresti dover testare diversi profili o utilizzare l'opzione "CSS personalizzato" per perfezionare l'aspetto.
- **Titolo email (per il proprietario del negozio)**

  - **Cosa fa questa impostazione:** Questa è la riga dell'oggetto per la notifica email che *tu* (il proprietario/amministratore del negozio) ricevi quando un cliente invia una domanda.
  - **Effetto della modifica di questa impostazione:** Modifica la riga dell'oggetto delle email di notifica interne.
  - **Valore consigliato:** Qualcosa di chiaro e informativo, come "Nuova domanda sul prodotto dal tuo negozio - [Nome Prodotto]".
  - **Scenario/esempio del commerciante:** Impostare questo su "URGENTE: Nuova richiesta per [Nome Prodotto]" può aiutare il tuo team a dare priorità.
- **Email del destinatario/i**

  - **Cosa fa questa impostazione:** Specifica l'indirizzo/i email a cui verranno inviate le richieste di prodotto. Puoi inserire più email separate da virgole.
  - **Effetto della modifica di questa impostazione:** Determina chi nella tua organizzazione riceve le domande dei clienti.
  - **Valore consigliato:** L'indirizzo email del tuo team di assistenza clienti o del reparto pertinente.
  - **Scenario/esempio del commerciante:** Se hai un indirizzo dedicato "[sales@yourstore.com](mailto:sales@yourstore.com)" o "[support@yourstore.com](mailto:support@yourstore.com)", inseriscilo qui. Per team più grandi, potresti inviarlo a una lista di distribuzione.
- **BCC per email di notifica del negozio**

  - **Cosa fa questa impostazione:** Ti consente di inviare una copia conoscenza nascosta (BCC) dell'email di notifica del negozio a indirizzi email aggiuntivi. Questi destinatari non saranno visibili al destinatario principale.
  - **Effetto della modifica di questa impostazione:** Fornisce un modo discreto per notificare altri membri del team o archiviare le richieste senza intasare la casella di posta del destinatario principale o rivelare destinatari aggiuntivi.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia una necessità specifica per il tracciamento interno o notifiche secondarie.
  - **Scenario/esempio del commerciante:** Potresti mettere in BCC il tuo responsabile marketing per tracciare l'interesse dei clienti, o un indirizzo email di archivio interno.
- **Email di risposta automatica**

  - **Cosa fa questa impostazione:** Questa è la riga dell'oggetto per l'email automatica inviata *al cliente* dopo che ha inviato una domanda.
  - **Effetto della modifica di questa impostazione:** Modifica la riga dell'oggetto dell'email di conferma che i tuoi clienti ricevono.
  - **Valore consigliato:** "Grazie per la tua richiesta - [Nome del tuo negozio]".
  - **Scenario/esempio del commerciante:** Un oggetto chiaro dell'auto-risponditore assicura al cliente che il suo messaggio è stato ricevuto.
- **Durata messaggio di successo (ms)**

  - **Cosa fa questa impostazione:** Controlla per quanto tempo la notifica "Il tuo messaggio è stato inviato con successo" rimane visibile sullo schermo dopo che un cliente invia un modulo, misurata in millisecondi (ms).
  - **Effetto della modifica di questa impostazione:**
    - *Valore più alto (es. 5000ms):* Il messaggio rimane visibile più a lungo, dando ai clienti più tempo per leggerlo.
    - *Valore più basso (es. 2000ms):* Il messaggio scompare rapidamente.
  - **Valore consigliato:** 3000-5000ms (3-5 secondi) è di solito un buon equilibrio.
  - **Scenario/esempio del commerciante:** Se i tuoi clienti sono spesso su connessioni più lente o hanno bisogno di più tempo per elaborare le informazioni, una durata maggiore potrebbe essere utile.
- **Nascondi "Fai una domanda" per prodotti esauriti (aappro\_HIDE\_OOS)**

  - **Cosa fa questa impostazione:** Se abilitata, il modulo o il pulsante "Fai una domanda" non verrà visualizzato sulle pagine prodotto in cui il prodotto è attualmente esaurito.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Impedisce ai clienti di chiedere informazioni su prodotti non disponibili, riducendo potenzialmente le richieste irrilevanti per il tuo team.
    - *Quando disabilitato:* Il modulo rimane visibile indipendentemente dallo stato delle scorte.
  - **Valore consigliato:** "Sì" per ridurre le richieste su articoli non disponibili, a meno che tu non voglia specificamente catturare l'interesse per i rifornimenti.
  - **Scenario/esempio del commerciante:** Se vendi articoli unici o in edizione limitata che non verranno riforniti, nascondere il modulo per i prodotti esauriti ha senso. Se vuoi valutare l'interesse per futuri rifornimenti, lascialo disabilitato.
- **Consenti solo ai clienti loggati di fare domande (aappro\_LOGGED\_CUSTOMERS\_ONLY)**

  - **Cosa fa questa impostazione:** Limita la possibilità di inviare domande sui prodotti solo ai clienti che hanno effettuato l'accesso ai loro account del negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli utenti non registrati o ospiti non vedranno o non potranno utilizzare il modulo "Fai una domanda". Questo può aiutare a ridurre lo spam e garantire che tu abbia i dettagli dell'account cliente collegati alle richieste.
    - *Quando disabilitato:* Chiunque può inviare una domanda, inclusi gli ospiti.
  - **Valore consigliato:** "No" per la massima portata dei clienti, "Sì" se dai priorità all'engagement dei clienti registrati e vuoi ridurre le richieste anonime.
  - **Scenario/esempio del commerciante:** Se gestisci un negozio B2B in cui tutte le interazioni richiedono un account, abilitare questa opzione sarebbe appropriato. Per un negozio al dettaglio generale, mantenerla disabilitata è di solito meglio per la conversione.

#### Campi del modulo e convalida

- **Sì / No (aappro\_FIELD\_PHONE\_REQUIRED, aappro\_FIELD\_PHONE\_VISIBLE, aappro\_FIELD\_TOPIC\_VISIBLE, aappro\_QUOTE\_QUANTITY\_VISIBLE)**

  - **Cosa fa questa impostazione:** Questi sono un gruppo di interruttori "Sì/No" che controllano la visibilità e la richiesta di campi specifici all'interno dei tuoi moduli di richiesta prodotto:
    - **Numero di telefono visibile:** Mostra il campo del numero di telefono.
    - **Numero di telefono richiesto:** Rende il campo del numero di telefono obbligatorio se visibile.
    - **Selezione argomento visibile:** Mostra un menu a discesa per i clienti per selezionare un argomento per la loro domanda (ad esempio, "Spedizione", "Specifiche tecniche", "Disponibilità").
    - **Quantità preventivo visibile:** Mostra un campo in cui i clienti possono richiedere un preventivo per una quantità specifica del prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato (Visibile):* Il campo appare sul modulo.
    - *Disabilitato (Visibile):* Il campo è nascosto.
    - *Abilitato (Richiesto):* Il cliente *deve* compilare il campo per inviare il modulo.
  - **Valore consigliato:**
    - **Telefono:** Visibile "No", Richiesto "No" (a meno che il contatto telefonico non sia fondamentale per il tuo modello di business).
    - **Argomento:** Visibile "Sì" (aiuta a categorizzare le richieste), Richiesto "No".
    - **Quantità preventivo:** Visibile "Sì" (se offri sconti per quantità o vendite B2B), Richiesto "No".
  - **Scenario/esempio del commerciante:** Se vendi elettronica complessa, rendere "Selezione argomento" visibile con opzioni come "Supporto tecnico" o "Compatibilità" sarebbe molto utile. Se sei un grossista, "Quantità preventivo" è essenziale.
- **Lunghezza minima domanda (caratteri)**

  - **Cosa fa questa impostazione:** Imposta il numero minimo di caratteri che un cliente deve digitare nel campo della domanda prima di poter inviare il modulo.
  - **Effetto della modifica di questa impostazione:** Impedisce domande molto brevi, potenzialmente inutili o spam.
  - **Valore consigliato:** 10-20 caratteri.
  - **Scenario/esempio del commerciante:** Impostare questo a 15 caratteri assicura che i clienti forniscano dettagli sufficienti oltre a "Domanda".
- **Lunghezza massima domanda (caratteri)**

  - **Cosa fa questa impostazione:** Imposta il numero massimo di caratteri che un cliente può digitare nel campo della domanda.
  - **Effetto della modifica di questa impostazione:** Impedisce domande eccessivamente lunghe che potrebbero essere difficili da leggere o indicare un cliente che cerca di utilizzare il modulo come una chat generica.
  - **Valore consigliato:** 500-1000 caratteri.
  - **Scenario/esempio del commerciante:** Un limite di 750 caratteri è di solito sufficiente per la maggior parte delle richieste di prodotto.
- **Consenti allegato immagine**

  - **Cosa fa questa impostazione:** Consente ai clienti di caricare un file immagine (ad esempio, uno screenshot, una foto di un articolo danneggiato o un diagramma) insieme alla loro domanda.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un campo "Carica file" appare sul modulo.
    - *Quando disabilitato:* Nessuna opzione di allegato è disponibile.
  - **Valore consigliato:** "Sì" può essere molto utile per le richieste visive, ma assicurati che il tuo server possa gestire l'archiviazione.
  - **Scenario/esempio del commerciante:** Un cliente potrebbe voler allegare una foto di una parte specifica di un prodotto su cui ha una domanda, o uno screenshot di un errore che sta riscontrando.
- **Dimensione massima allegato (MB)**

  - **Cosa fa questa impostazione:** Se l'allegato immagine è abilitato, imposta la dimensione massima del file (in megabyte) consentita per ogni allegato.
  - **Effetto della modifica di questa impostazione:** Controlla il carico del server e l'utilizzo dello storage.
  - **Valore consigliato:** 2-5 MB è di solito sufficiente per la maggior parte delle immagini.
  - **Scenario/esempio del commerciante:** Impostarlo a 3MB impedisce ai clienti di caricare immagini molto grandi e ad alta risoluzione che non sono necessarie per una richiesta.

#### Sicurezza e conformità

- **Conforme al GDPR**

  - **Cosa fa questa impostazione:** Abilita funzionalità per aiutare i tuoi moduli a essere conformi ai requisiti del GDPR (Regolamento generale sulla protezione dei dati), tipicamente aggiungendo una casella di controllo per il consenso al trattamento dei dati.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà una casella di controllo sul modulo, che richiederà ai clienti di accettare esplicitamente la tua politica sulla privacy prima di inviare la loro domanda.
    - *Quando disabilitato:* Non viene mostrata alcuna casella di controllo per il consenso al GDPR.
  - **Valore consigliato:** "Sì" se il tuo negozio opera o serve clienti in regioni soggette al GDPR (ad esempio, UE).
  - **Scenario/esempio del commerciante:** Se vendi a clienti in Europa, abilitare questa opzione è legalmente importante.
- **Pagina politica sulla privacy**

  - **Cosa fa questa impostazione:** Se la conformità al GDPR è abilitata, questa impostazione ti consente di selezionare la pagina CMS che contiene la politica sulla privacy del tuo negozio. La casella di controllo per il consenso al GDPR si collegherà a questa pagina.
  - **Effetto della modifica di questa impostazione:** Fornisce ai clienti un facile accesso alla tua politica sulla privacy, soddisfacendo un requisito chiave del GDPR.
  - **Valore consigliato:** Seleziona la tua pagina CMS dedicata alla Politica sulla privacy.
  - **Scenario/esempio del commerciante:** Dopo aver abilitato il GDPR, devi selezionare la pagina CMS corretta in modo che i clienti possano rivedere le tue pratiche di gestione dei dati.
- **ReCaptcha (v2)**

  - **Cosa fa questa impostazione:** Integra Google reCAPTCHA v2 (la casella di controllo "Non sono un robot") nei tuoi moduli per prevenire spam e invii da bot.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* La casella di controllo reCAPTCHA appare sul modulo, richiedendo l'interazione dell'utente per dimostrare di essere umano.
    - *Quando disabilitato:* Non viene utilizzato reCAPTCHA.
  - **Valore consigliato:** "Sì" per ridurre significativamente lo spam, specialmente se ricevi molte richieste da bot.
  - **Scenario/esempio del commerciante:** Se ricevi molte richieste indesiderate, abilitare reCAPTCHA è una forte difesa.
- **Chiave del sito ReCaptcha**

  - **Cosa fa questa impostazione:** Questa è la chiave pubblica fornita da Google quando registri il tuo sito web per reCAPTCHA. Viene utilizzata per visualizzare il widget reCAPTCHA sul tuo sito.
  - **Effetto della modifica di questa impostazione:** Essenziale per il funzionamento di reCAPTCHA. Senza di essa, reCAPTCHA non apparirà o non funzionerà.
  - **Valore consigliato:** La tua chiave del sito reCAPTCHA unica da Google.
  - **Scenario/esempio del commerciante:** Dovrai andare alla console di amministrazione di Google reCAPTCHA, registrare il tuo dominio e copiare questa chiave nelle impostazioni del modulo.
- **Chiave segreta ReCaptcha**

  - **Cosa fa questa impostazione:** Questa è la chiave privata fornita da Google, utilizzata per la verifica lato server della risposta reCAPTCHA.
  - **Effetto della modifica di questa impostazione:** Essenziale per il funzionamento sicuro di reCAPTCHA. Il modulo utilizza questa chiave per confermare che l'utente ha effettivamente superato la sfida reCAPTCHA.
  - **Valore consigliato:** La tua chiave segreta reCAPTCHA unica da Google.
  - **Scenario/esempio del commerciante:** Questa chiave deve essere mantenuta confidenziale e mai esposta nel codice lato client.

#### Integrazione e personalizzazione

- **URL Webhook (Slack/Discord)**

  - **Cosa fa questa impostazione:** Ti consente di inviare notifiche di nuove richieste di prodotto a un URL webhook, tipicamente utilizzato per servizi come Slack o Discord.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene fornito un URL:* Le nuove richieste attiveranno una notifica al canale di chat specificato.
    - *Quando vuoto:* Non vengono inviate notifiche webhook.
  - **Valore consigliato:** Lascia vuoto a meno che tu non utilizzi attivamente Slack, Discord o un altro servizio che supporta webhook in entrata per la comunicazione del team.
  - **Scenario/esempio del commerciante:** Il tuo team di assistenza clienti utilizza Slack. Puoi configurare un webhook in entrata in Slack e incollare il suo URL qui, in modo che ogni nuova domanda sul prodotto appaia immediatamente nel tuo canale #customer-support.
- **CSS personalizzato (solo pagina prodotto)**

  - **Cosa fa questa impostazione:** Fornisce un'area di testo dove puoi aggiungere regole CSS personalizzate per stilizzare il modulo di richiesta prodotto specificamente sulle pagine prodotto.
  - **Effetto della modifica di questa impostazione:** Ti consente di sovrascrivere gli stili predefiniti del modulo o gli stili del tuo tema per abbinare perfettamente l'estetica del tuo marchio senza modificare direttamente i file del modulo.
  - **Valore consigliato:** Utilizzare con parsimonia per piccole modifiche. Per modifiche di stile importanti, considerare le sovrascritture del tema.
  - **Scenario/esempio del commerciante:** Vuoi cambiare il colore del pulsante "Invia" al colore primario del tuo marchio, o regolare la spaziatura intorno ai campi del modulo. Puoi aggiungere `.aappro-form-submit-button { background-color: #FF0000; }` qui.
- **Campi personalizzati (aappro\_CUSTOM\_FIELDS\_JSON)**

  - **Cosa fa questa impostazione:** Questa è una potente funzionalità che ti consente di definire campi aggiuntivi e personalizzati per i tuoi moduli di contatto. Puoi specificare i tipi di campo (testo, textarea, select, checkbox), le etichette e se sono obbligatori. Questo è tipicamente gestito tramite un'interfaccia dedicata, non un campo JSON grezzo.
  - **Effetto della modifica di questa impostazione:** Aggiunge nuovi campi di input ai tuoi moduli, consentendoti di raccogliere informazioni più specifiche dai clienti.
  - **Valore consigliato:** Aggiungi campi pertinenti ai tuoi prodotti o servizi (ad esempio, "Numero d'ordine" per i clienti esistenti, "Uso previsto" per il B2B).
  - **Scenario/esempio del commerciante:** Per un negozio di abbigliamento, potresti aggiungere un campo personalizzato "Taglia desiderata" se i clienti spesso chiedono informazioni su taglie specifiche non elencate. Per un negozio di tecnologia, "Modello dispositivo attuale" potrebbe essere utile.
- **Consenti commenti (aappro\_ALLOW\_COMMENTS)**

  - **Cosa fa questa impostazione:** Questa impostazione probabilmente controlla se i clienti possono lasciare commenti generali sulla pagina del prodotto, possibilmente separati dal modulo specifico "Fai una domanda".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Potrebbe apparire una sezione di commenti generale.
    - *Quando disabilitato:* È disponibile solo il modulo strutturato "Fai una domanda".
  - **Valore consigliato:** "No" se vuoi mantenere la comunicazione focalizzata attraverso il modulo di domanda strutturato. "Sì" se vuoi incoraggiare una discussione pubblica più ampia.
  - **Scenario/esempio del commerciante:** Se preferisci richieste dirette e private rispetto ai commenti pubblici, disabilita questa opzione.
- **PS\_STOCK\_MANAGEMENT**

  - **Cosa fa questa impostazione:** Questa è un'impostazione core di PrestaShop, non direttamente controllata dal modulo, ma il modulo potrebbe leggerne il valore. Determina se la gestione delle scorte è abilitata globalmente nel tuo negozio.
  - **Effetto della modifica di questa impostazione:** Se la gestione delle scorte è disabilitata, l'impostazione del modulo "Nascondi per prodotti esauriti" potrebbe non funzionare come previsto, poiché i prodotti non avranno uno stato di scorte chiaro.
  - **Valore consigliato:** "Sì" per la maggior parte dei negozi e-commerce per tracciare accuratamente l'inventario.
  - **Scenario/esempio del commerciante:** Se vendi prodotti digitali, potresti disabilitare la gestione delle scorte. Tuttavia, per i beni fisici, è fondamentale.
- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**

  - **Cosa fanno queste impostazioni:** Queste sono impostazioni core di PrestaShop relative alla lingua. `PS_LANG_DEFAULT` imposta la lingua predefinita del front-office e `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` consente ai dipendenti di scegliere la lingua del loro back-office. Il modulo le utilizza per garantire la corretta visualizzazione della lingua per moduli e notifiche.
  - **Effetto della modifica di queste impostazioni:** Influisce sulla lingua dei moduli e delle notifiche.
  - **Valore consigliato:** Imposta `PS_LANG_DEFAULT` sulla lingua principale del tuo negozio. `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` può essere abilitato se hai un team multilingue.
  - **Scenario/esempio del commerciante:** Se la lingua principale del tuo negozio è il francese, assicurati che `PS_LANG_DEFAULT` sia impostato su francese.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione principale | Profilo di supporto del template | Il tuo tema / Classic | Garantisce lo stile e l'integrazione corretti con il tuo tema. |
| Configurazione principale | Titolo email (per il proprietario del negozio) | "Nuova domanda sul prodotto" | Riga dell'oggetto per le email di notifica interne dell'amministratore. |
| Configurazione principale | Email del destinatario/i | La tua email di amministratore | Dove vengono inviate le domande dei clienti. |
| Configurazione principale | BCC per email di notifica del negozio | Vuoto | Invia discretamente copie delle notifiche ad altri. |
| Configurazione principale | Email di risposta automatica | "Grazie per la tua richiesta" | Riga dell'oggetto per le email di conferma del cliente. |
| Configurazione principale | Durata messaggio di successo (ms) | 3000-5000 | Per quanto tempo la notifica "messaggio inviato" rimane visibile. |
| Configurazione principale | Nascondi per prodotti esauriti | Sì | Impedisce domande su prodotti non disponibili. |
| Configurazione principale | Consenti solo ai clienti loggati | No | Limita l'accesso al modulo agli utenti registrati. |
| Configurazione principale | Numero di telefono visibile | No | Mostra/nasconde il campo del numero di telefono. |
| Configurazione principale | Numero di telefono richiesto | No | Rende il numero di telefono obbligatorio se visibile. |
| Configurazione principale | Selezione argomento visibile | Sì | Mostra/nasconde un menu a discesa per gli argomenti delle domande. |
| Configurazione principale | Quantità preventivo visibile | Sì (se B2B) | Mostra/nasconde un campo per le richieste di preventivo per quantità. |
| Configurazione principale | Lunghezza minima domanda | 15 caratteri | Impedisce domande eccessivamente brevi. |
| Configurazione principale | Lunghezza massima domanda | 750 caratteri | Impedisce domande eccessivamente lunghe. |
| Configurazione principale | Consenti allegato immagine | Sì | Consente ai clienti di caricare file. |
| Configurazione principale | Dimensione massima allegato (MB) | 3 MB | Limita la dimensione dei file caricati. |
| Configurazione principale | Conforme al GDPR | Sì (se applicabile) | Aggiunge una casella di controllo per il consenso al trattamento dei dati. |
| Configurazione principale | Pagina politica sulla privacy | La tua pagina CMS sulla privacy | Collega la casella di controllo GDPR alla tua pagina della politica. |
| Configurazione principale | ReCaptcha (v2) | Sì | Integra Google reCAPTCHA per la protezione dallo spam. |
| Configurazione principale | Chiave del sito ReCaptcha | La tua chiave del sito Google | Chiave pubblica per la visualizzazione del widget reCAPTCHA. |
| Configurazione principale | Chiave segreta ReCaptcha | La tua chiave segreta Google | Chiave privata per la verifica lato server di reCAPTCHA. |
| Configurazione principale | URL Webhook (Slack/Discord) | Vuoto | Invia notifiche a servizi di chat esterni. |
| Configurazione principale | CSS personalizzato (solo pagina prodotto) | Vuoto | Aggiungi CSS personalizzato per stilizzare il modulo. |
| Configurazione principale | Campi personalizzati | Configurati tramite AdminAapproForm | Definisci campi aggiuntivi per i tuoi moduli. |
| Configurazione principale | Consenti commenti | No | Controlla i commenti generali sui prodotti rispetto alle domande strutturate. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

Oltre alla configurazione principale, questo modulo fornisce sezioni dedicate nel tuo Back Office di PrestaShop per gestire moduli, domande e campi personalizzati.

#### 2.2.1 AdminAapproFormController: Gestione moduli (Back Office > Moduli > Chiedi informazioni sul prodotto > Moduli)

Questa schermata ti consente di creare e gestire diversi moduli di richiesta prodotto e specificare dove appaiono nel tuo negozio.

- **Nome schermata e posizione menu:** **Moduli > Chiedi informazioni sul prodotto > Moduli**
- **Azioni e impostazioni disponibili:**
  - **Tabella di elenco:** Visualizza tutti i moduli creati con i loro nomi, stato e prodotti/categorie/produttori associati.
  - **Pulsante Aggiungi nuovo modulo:** Clicca per creare un nuovo modulo.
  - **Azioni Modifica/Elimina:** Modifica o rimuovi i moduli esistenti.
  - **Campi del modulo:** Quando aggiungi o modifichi un modulo, configurerai:
    - **Nome modulo:** Nome interno per tuo riferimento.
    - **Attivo:** Abilita o disabilita il modulo.
    - **Visualizza sulla pagina prodotto:** Scegli se questo modulo deve apparire sulle pagine prodotto.
    - **Visualizza sulla pagina categoria:** Scegli se questo modulo deve apparire sulle pagine categoria.
    - **Visualizza sulla pagina produttore:** Scegli se questo modulo deve apparire sulle pagine produttore.
    - **Email del destinatario/i per questo modulo:** Sovrascrivi l'email del destinatario globale per questo modulo specifico. Questo è cruciale per instradare le domande a team specifici.
    - **Prodotti:** Seleziona prodotti specifici in cui questo modulo deve apparire.
    - **Categorie:** Seleziona categorie specifiche in cui questo modulo deve apparire.
    - **Produttori:** Seleziona produttori specifici in cui questo modulo deve apparire.
    - **Campi personalizzati:** Qui è dove definisci i campi unici per *questo modulo specifico*. Puoi aggiungere input di testo, aree di testo, menu a discesa, caselle di controllo, ecc., e contrassegnarli come obbligatori.
- **Effetto delle modifiche:**
  - La creazione di un nuovo modulo ti consente di definire un set unico di domande e regole di routing.
  - L'associazione di moduli a prodotti, categorie o produttori specifici significa che solo quel particolare modulo verrà visualizzato quando un cliente visualizza un articolo che corrisponde a tali criteri.
  - La sovrascrittura delle email dei destinatari garantisce che le domande su, ad esempio, "Elettronica" vadano al reparto elettronica, mentre le domande su "Abbigliamento" vadano al team della moda.
  - I campi personalizzati ti consentono di raccogliere informazioni altamente specifiche pertinenti al contesto del modulo.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. **Identifica le esigenze:** Determina se hai bisogno di moduli diversi per diversi tipi di prodotto, reparti o segmenti di clientela.
  2. **Crea moduli:** Vai su **Moduli** e clicca su "Aggiungi nuovo modulo".
  3. **Configura il routing:** Imposta le "Email del destinatario/i per questo modulo" specifiche per garantire che le domande vadano al posto giusto.
  4. **Definisci l'ambito:** Utilizza i selettori "Prodotti", "Categorie" e "Produttori" per controllare dove appare ogni modulo.
  5. **Aggiungi campi personalizzati:** Personalizza le domande poste su ogni modulo utilizzando la sezione "Campi personalizzati" per raccogliere informazioni pertinenti.
  6. **Testa:** Testa sempre i tuoi moduli sul front-office per assicurarti che appaiano correttamente e inviino email ai destinatari giusti.

#### 2.2.2 AdminAapproQuestionController: Gestione domande (Back Office > Moduli > Chiedi informazioni sul prodotto > Domande)

Questa schermata funge da hub centrale per visualizzare e gestire tutte le domande dei clienti inviate.

- **Nome schermata e posizione menu:** **Moduli > Chiedi informazioni sul prodotto > Domande**
- **Tabella / Entità gestita:** `aappro_question` (memorizza tutte le richieste inviate)
- **Campi del modulo e colonne:**
  - **Vista griglia / gestione:** Visualizza un elenco di tutte le domande inviate.
    - **Colonne:** Tipicamente include: Nome cliente, Email cliente, Nome prodotto (se applicabile), Argomento domanda, Data invio, Stato (es. Nuovo, Risposto, Chiuso).
    - **Filtro e ordinamento:** Funzionalità standard delle liste di PrestaShop per filtrare per data, cliente, prodotto o stato.
  - **Azione Visualizza/Rispondi:** Cliccando su una domanda puoi visualizzarne i dettagli completi e rispondere al cliente.
    - **Dettagli domanda:** Mostra il messaggio completo del cliente, le informazioni di contatto, i dettagli del prodotto e gli eventuali allegati.
    - **Interfaccia di risposta:** Un'area di testo per comporre la tua risposta, che verrà inviata direttamente all'indirizzo email del cliente.
    - **Aggiornamento stato:** Opzione per cambiare lo stato della domanda (es. da "Nuovo" a "Risposto").
- **Effetto delle modifiche:**
  - Questa schermata fornisce una casella di posta centralizzata per tutte le richieste relative ai prodotti, rendendo facile tracciare e rispondere.
  - Rispondere direttamente da qui garantisce che la cronologia delle conversazioni sia mantenuta all'interno di PrestaShop e collegata al prodotto specifico.
  - L'aggiornamento dello stato aiuta il tuo team a gestire il carico di lavoro e garantisce che nessuna domanda venga persa.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. **Controlla regolarmente:** Prendi l'abitudine di controllare questa sezione quotidianamente (o più volte al giorno, a seconda del volume).
  2. **Dai priorità:** Utilizza i filtri per identificare le domande urgenti o senza risposta.
  3. **Visualizza e rispondi:** Clicca su "Visualizza" su una domanda, leggi i dettagli e componi una risposta chiara e utile.
  4. **Aggiorna lo stato:** Dopo aver risposto, cambia lo stato della domanda in "Risposto" o "Chiuso" per mantenere la tua coda organizzata.
  5. **Utilizza il contesto del prodotto:** Il modulo collega automaticamente la domanda al prodotto, in modo da avere tutto il contesto necessario quando rispondi.

#### 2.2.3 index.php (aappro/controllers/admin/index.php)

Questo file è una pratica standard di PrestaShop per prevenire la visualizzazione diretta delle directory nel Back Office. Tipicamente contiene un semplice `header('Location: ../../index.php?controller=AdminHome');` o un reindirizzamento simile, garantendo che se qualcuno tenta di accedere direttamente alla directory `controllers/admin/`, venga reindirizzato alla dashboard principale dell'amministratore. Non gestisce alcuna entità specifica o ha campi configurabili.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

- **D: Il mio modulo non viene visualizzato sulla pagina del prodotto.**

  - **R:**
    1. **Controlla lo stato del modulo:** Assicurati che il modulo sia installato e abilitato in **Moduli > Gestione moduli**.
    2. **Controlla la configurazione del modulo:** Vai su **Moduli > Chiedi informazioni sul prodotto > Moduli**. Assicurati che il modulo specifico che ti aspetti di vedere sia "Attivo" e correttamente associato al prodotto, alla categoria o al produttore che stai visualizzando.
    3. **Posizionamento dell'hook:** Verifica che il modulo sia agganciato a un'area di visualizzazione che il tuo tema renderizza (ad esempio, `displayProductExtraContent`, `displayProductAdditionalInfo`). A volte i temi sovrascrivono le posizioni predefinite degli hook.
    4. **Compatibilità del tema:** Se stai utilizzando un tema altamente personalizzato, prova a passare temporaneamente al tema Classic predefinito per vedere se il modulo appare. Se lo fa, potrebbe esserci un conflitto con i file di template o CSS del tuo tema personalizzato.
    5. **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**).
- **D: Non ricevo notifiche email quando un cliente invia una domanda.**

  - **R:**
    1. **Controlla le email del destinatario:** Verifica le "Email del destinatario/i" nella configurazione principale del modulo e anche le "Email del destinatario/i per questo modulo" specifiche all'interno delle impostazioni del modulo (**Moduli > Chiedi informazioni sul prodotto > Moduli > Modifica modulo**). Assicurati che siano corrette e prive di errori di battitura.
    2. **Cartella spam:** Controlla la cartella spam o posta indesiderata della tua email.
    3. **Impostazioni di posta del server:** Assicurati che le impostazioni email del tuo negozio PrestaShop siano configurate correttamente (**Parametri avanzati > E-mail**). Invia un'email di prova da PrestaShop per confermare che il tuo server può inviare email.
    4. **Provider di hosting:** Contatta il tuo provider di hosting per verificare eventuali restrizioni o problemi di invio email lato server.
    5. **Log del modulo:** Controlla i log degli errori di PrestaShop (se disponibili) o i log degli errori PHP del tuo server per eventuali errori relativi alla posta.
- **D: Il reCAPTCHA non funziona o non viene visualizzato.**

  - **R:**
    1. **Abilita reCAPTCHA:** Assicurati che "ReCaptcha (v2)" sia impostato su "Sì" nella configurazione principale del modulo.
    2. **Chiavi:** Ricontrolla che la tua "Chiave del sito ReCaptcha" e la "Chiave segreta ReCaptcha" siano inserite correttamente e corrispondano alle chiavi del tuo account Google reCAPTCHA per il tuo dominio.
    3. **Registrazione del dominio:** Assicurati che il tuo dominio sia correttamente registrato nella console di amministrazione di Google reCAPTCHA.
    4. **Problemi del browser:** Testa in diversi browser e svuota la cache del browser. A volte i blocchi pubblicitari possono interferire con reCAPTCHA.
- **D: Come posso tradurre i campi del modulo e i messaggi in altre lingue?**

  - **R:**
    1. Vai su **Internazionale > Traduzioni**.
    2. Seleziona "Traduzioni dei moduli installati".
    3. Scegli il tuo tema, la lingua che desideri tradurre, quindi seleziona "Chiedi informazioni sul prodotto - moduli di contatto pro" dall'elenco dei moduli.
    4. Potrai quindi tradurre tutte le stringhe visibili, le etichette dei campi e i messaggi utilizzati dal modulo. Ricorda di salvare le modifiche.
- **D: Lo stile del modulo appare strano con il mio tema personalizzato.**

  - **R:**
    1. **Profilo di supporto del template:** Prova a regolare l'impostazione "Profilo di supporto del template" nella configurazione principale del modulo per vedere se un profilo diverso funziona meglio.
    2. **CSS personalizzato:** Utilizza il campo "CSS personalizzato (solo pagina prodotto)" nella configurazione del modulo per aggiungere regole CSS specifiche per sovrascrivere o regolare lo stile. Avrai bisogno di conoscenze CSS di base o di uno sviluppatore web per questo.
    3. **Sovrascritture del tema:** Per modifiche più estese, uno sviluppatore potrebbe dover creare sovrascritture del tema per i file di template (`.tpl`) o i file CSS del modulo, posizionandoli nella directory `modules/aappro/` del tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Chiedi informazioni sul prodotto - moduli di contatto pro", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo segue un modello MVC (Model-View-Controller) standard di PrestaShop, estendendo le classi core di PrestaShop per la sua funzionalità. Sfrutta `ModuleFrontController` per le interazioni front-office (invio di moduli, risposte) e `AdminController` per la gestione back-office di moduli e domande. Le classi `ObjectModel` personalizzate (`AapproCustomFields`, `AapproFormMatcher`) vengono utilizzate per persistere i dati specifici del modulo. Gli hook sono ampiamente utilizzati per integrare il modulo in varie parti del front-office.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/index.php`
  - **Nome classe e classe genitore:** `AapproIndexModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Probabilmente gestisce il rendering iniziale del modulo o un trigger per il modulo, potenzialmente tramite AJAX. Potrebbe preparare i dati per il template del modulo.
- `controllers/front/question.php`
  - **Nome classe e classe genitore:** `AapproQuestionModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller è responsabile dell'elaborazione dell'invio del modulo di richiesta prodotto. Convalida l'input, gestisce la verifica reCAPTCHA, elabora i caricamenti di file (se abilitati), salva la domanda nel database, invia notifiche email al proprietario del negozio e potenzialmente un auto-risponditore al cliente. Restituisce risposte JSON per gli invii AJAX.
- `controllers/front/reply.php`
  - **Nome classe e classe genitore:** `AapproReplyModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller probabilmente gestisce il meccanismo di risposta rivolto al cliente, se il modulo consente ai clienti di visualizzare le risposte nel front-office o fornisce un link specifico per la visualizzazione delle risposte. Recupererebbe la domanda e le risposte associate.

#### Controller Admin Back-Office

- `controllers/admin/AdminAapproForm.php`
  - **Nome classe e classe genitore:** `AdminAapproFormController` estende `ModuleAdminController`.
  - **Nome scheda ed entità gestita:** Gestisce i moduli di richiesta personalizzati. Accessibile tramite **Moduli > Chiedi informazioni sul prodotto > Moduli**. Gestisce le operazioni CRUD per gli oggetti `AapproFormMatcher`, inclusa la definizione dei nomi dei moduli, lo stato di attivazione, i prodotti/categorie/produttori associati e i campi personalizzati.
- `controllers/admin/AdminAapproQuestion.php`
  - **Nome classe e classe genitore:** `AdminAapproQuestionController` estende `ModuleAdminController`.
  - **Nome scheda ed entità gestita:** Gestisce le domande dei clienti inviate. Accessibile tramite **Moduli > Chiedi informazioni sul prodotto > Domande**. Fornisce una vista elenco delle domande, consente di visualizzare i dettagli completi delle domande e offre un'interfaccia per rispondere ai clienti e aggiornare lo stato delle domande.
- `controllers/admin/index.php`
  - **Nome classe e classe genitore:** Non un controller funzionale.
  - **Responsabilità:** File di sicurezza standard di PrestaShop per prevenire la visualizzazione delle directory. Tipicamente reindirizza alla dashboard dell'amministratore.

### 4.3 Classi e modelli core (`classes/`)

- `classes/AapproCustomFields.php`
  - **Con quale tabella del database interagisce:** Probabilmente `ps_aappro_custom_field` (o simile).
  - **Estende ObjectModel:** Sì, estende `ObjectModel`.
  - **Campi `$definition`:** Definirebbe campi come `id_aappro_custom_field`, `id_aappro_form`, `name`, `type`, `label`, `required`, `options` (per i campi select, spesso codificati in JSON), `position`, `active`.
  - **Metodi pubblici chiave e logica di business:** Metodi per salvare, recuperare ed eliminare le definizioni dei campi personalizzati associati a moduli specifici. Logica per l'analisi e il rendering dei dati dei campi personalizzati.
- `classes/AapproFormMatcher.php`
  - **Con quale tabella del database interagisce:** Probabilmente `ps_aappro_form` (o simile).
  - **Estende ObjectModel:** Sì, estende `ObjectModel`.
  - **Campi `$definition`:** Definirebbe campi come `id_aappro_form`, `name`, `active`, `recipient_emails`, `products` (array di ID prodotto codificato in JSON), `categories` (array di ID categoria codificato in JSON), `manufacturers` (array di ID produttore codificato in JSON), `display_product`, `display_category`, `display_manufacturer`.
  - **Metodi pubblici chiave e logica di business:** Metodi per la gestione delle configurazioni dei moduli, inclusa la memorizzazione delle associazioni con prodotti/categorie/produttori e il recupero del modulo corretto in base al contesto attuale (ID prodotto, ID categoria).

### 4.4 Risorse JavaScript (`views/js/`)

- `aappro/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Descrizione:** Fornisce la funzionalità di completamento automatico per la selezione di prodotti, categorie o produttori durante la configurazione dei moduli in `AdminAapproFormController`. Si lega ai campi di input per suggerire entità mentre l'utente digita, migliorando l'UX per l'associazione dei moduli.
- `aappro/views/aappro.js`
  - **Ambito:** Front-office.
  - **Descrizione:** Script principale del front-office per il modulo.
    - **Listener di eventi:** Lega gli eventi click ai pulsanti/link "Fai una domanda", gli eventi submit ai moduli di richiesta.
    - **Manipolazione del DOM:** Gestisce la visualizzazione/nascondimento del modulo (ad esempio, in un modale o in una sezione espandibile), la visualizzazione di messaggi di successo/errore (notifiche toast).
    - **Chiamate AJAX:** Invia i dati del modulo in modo asincrono a `AapproQuestionModuleFrontController`, gestisce la risposta reCAPTCHA e aggiorna l'interfaccia utente in base alla risposta JSON del server.
    - **Validazione:** Può includere la validazione lato client per i campi del modulo (ad esempio, lunghezza min/max).
- `aappro/views/js/admin-button-style.js`
  - **Ambito:** Back-office.
  - **Descrizione:** Probabilmente fornisce elementi interattivi o anteprime per la configurazione degli stili dei pulsanti (ad esempio, selettori di colore, cursori di dimensione) all'interno delle schermate di configurazione del modulo o di gestione dei moduli.
- `aappro/views/js/admin-form-layout.js`
  - **Ambito:** Back-office.
  - **Descrizione:** Gestisce il layout dinamico e l'interazione per la creazione/modifica di moduli in `AdminAapproFormController`, in particolare per la gestione dei campi personalizzati. Ciò potrebbe includere l'aggiunta/rimozione di righe di campi personalizzati, il riordino dei campi e la gestione delle opzioni specifiche per il tipo di campo.
- `aappro/views/js/admin-icon-picker-data.js`
  - **Ambito:** Back-office.
  - **Descrizione:** Contiene dati (ad esempio, un array di classi di icone o percorsi SVG) per un'interfaccia di selezione icone utilizzata nel back-office, possibilmente per icone di campi personalizzati o opzioni di visualizzazione del modulo.
- `aappro/views/js/admin-icon-picker.js`
  - **Ambito:** Back-office.
  - **Descrizione:** Implementa la logica dell'interfaccia utente del selettore di icone, consentendo agli amministratori di selezionare icone da un set predefinito, probabilmente utilizzata in combinazione con `admin-icon-picker-data.js`.

### 4.5 Fogli di stile CSS (`views/css/`)

- `aappro/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office.
  - **Descrizione:** Stili per i menu a discesa di completamento automatico e i campi di input utilizzati nella configurazione del modulo amministrativo (ad esempio, per la selezione di prodotti/categorie).
- `aappro/views/aappro.css`
  - **Ambito:** Stile del cliente del front-office.
  - **Descrizione:** Stile principale per i moduli di richiesta prodotto, pulsanti, modali, messaggi di successo/errore (notifiche toast) e qualsiasi altro elemento del front-office renderizzato dal modulo.
  - **Selettori di classe CSS chiave:** `.aappro-form-container`, `.aappro-form-trigger`, `.aappro-modal`, `.aappro-field-group`, `.aappro-submit-button`, `.aappro-success-toast`, `.aappro-error-toast`.
- `aappro/views/css/admin-button-style.css`
  - **Ambito:** Stile del modulo amministrativo del back-office.
  - **Descrizione:** Stili per gli elementi di configurazione dei pulsanti all'interno dell'interfaccia di amministrazione del modulo.
- `aappro/views/css/admin-custom-fields.css`
  - **Ambito:** Stile del modulo amministrativo del back-office.
  - **Descrizione:** Stili per l'interfaccia di gestione dinamica dei campi personalizzati in `AdminAapproFormController`, garantendo un layout chiaro e utilizzabile per l'aggiunta/modifica dei campi personalizzati.
- `aappro/views/css/admin-form-layout.css`
  - **Ambito:** Stile del modulo amministrativo del back-office.
  - **Descrizione:** Layout generale e stile per le schermate di creazione/modifica dei moduli nel pannello di amministrazione, fornendo un aspetto e una sensazione coerenti.
- `aappro/views/css/admin-icon-picker.css`
  - **Ambito:** Stile del modulo amministrativo del back-office.
  - **Descrizione:** Stili per l'interfaccia di selezione delle icone utilizzata nel pannello di amministrazione.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

- `aappro/views/aappro-extra-forms.tpl`
  - **Hook:** `displayProductExtraContent` o simile.
  - **Output:** Renderizza moduli aggiuntivi o blocchi di contenuto relativi al prodotto, potenzialmente includendo il modulo di richiesta stesso o un trigger per esso.
- `aappro/views/aappro-extra-trigger.tpl`
  - **Hook:** `displayProductButtons`, `displayProductAdditionalInfo`.
  - **Output:** Renderizza un pulsante o un link (ad esempio, "Fai una domanda") che attiva la visualizzazione del modulo di richiesta, spesso in un modale o in una sezione nascosta.
- `aappro/views/aappro-extra.tpl`
  - **Hook:** `displayProductExtraContent`, `displayProductAdditionalInfo`.
  - **Output:** Un template generale per contenuti extra sulla pagina del prodotto, potenzialmente che avvolge il modulo o il suo trigger.
- `aappro/views/aappro-faq-tab-title.tpl`
  - **Hook:** `displayProductTab`.
  - **Output:** Renderizza il titolo per una scheda prodotto (ad esempio, "Fai una domanda" o "FAQ") che, quando cliccata, rivela il contenuto del modulo.
- `aappro/views/aappro-faq-tab.tpl`
  - **Hook:** `displayProductTabContent`.
  - **Output:** Renderizza il contenuto effettivo della scheda prodotto, che sarebbe il modulo di richiesta stesso.
- `aappro/views/aappro-form-body.tpl`
  - **Hook:** Inclusione interna.
  - **Output:** La struttura HTML principale per i campi del modulo di richiesta (nome, email, domanda, campi personalizzati, reCAPTCHA, casella di controllo GDPR). Questo è probabilmente incluso da altri template.
- `aappro/views/aappro-form-tab.tpl`
  - **Hook:** `displayProductTabContent`.
  - **Output:** Simile a `aappro-faq-tab.tpl`, specificamente per il rendering del modulo all'interno di una scheda prodotto.
- `aappro/views/aappro-product-embed.tpl`
  - **Hook:** `displayProductAdditionalInfo`, `displayReassurance`.
  - **Output:** Incorpora il modulo di richiesta direttamente nel contenuto della pagina del prodotto, piuttosto che in una scheda o un modale.
- `aappro/views/classic/` (e `views/partials/`)
  - Queste directory contengono template specifici per il tema (per il tema Classic) e parziali riutilizzabili. Riflettono la struttura della directory principale `views/` ma sono ottimizzati o specificamente stilizzati per il tema Classic.
  - `aappro-custom-field-single.tpl`: Renderizza un singolo campo personalizzato in base al suo tipo.
  - `aappro-custom-fields.tpl`: Itera e renderizza tutti i campi personalizzati per un modulo.
  - `aappro-field-fragment.tpl`: Un frammento riutilizzabile per il rendering di elementi comuni dei campi del modulo.

#### Template amministrativi (`views/templates/admin/`)

- `aappro/views/templates/admin/button_style_block.tpl`
  - **Scopo:** Renderizza l'interfaccia per la configurazione degli stili dei pulsanti all'interno del pannello di amministrazione.
- `aappro/views/templates/admin/conversation_reply.tpl`
  - **Scopo:** Renderizza l'interfaccia di risposta quando si visualizza una domanda del cliente in `AdminAapproQuestionController`.
- `aappro/views/templates/admin/custom_fields_block.tpl`
  - **Scopo:** Renderizza l'interfaccia dinamica per l'aggiunta, la modifica e la gestione dei campi personalizzati all'interno di `AdminAapproFormController`.
- `aappro/views/templates/admin/form_layout_block.tpl`
  - **Scopo:** Renderizza le opzioni di layout generali per i moduli nel pannello di amministrazione.
- `aappro/views/templates/admin/question_extras.tpl`
  - **Scopo:** Visualizza dettagli o azioni aggiuntive relative a una domanda specifica in `AdminAapproQuestionController`.
- `aappro/views/templates/admin/question_product_preview.tpl`
  - **Scopo:** Renderizza una piccola anteprima del prodotto associato a una domanda in `AdminAapproQuestionController`.
- `aappro/views/templates/admin/topic_options_block.tpl`
  - **Scopo:** Renderizza l'interfaccia di configurazione per la definizione degli argomenti disponibili per il menu a discesa "Selezione argomento".
- `aappro/views/templates/admin/view_question.tpl`
  - **Scopo:** Il template principale per la visualizzazione di una singola domanda del cliente e dei suoi dettagli in `AdminAapproQuestionController`.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

- `ps_aappro_form`: Memorizza le definizioni di ogni modulo di richiesta personalizzato creato dal commerciante.

  - `id_aappro_form` (PK)
  - `name` (VARCHAR)
  - `active` (TINYINT)
  - `recipient_emails` (TEXT)
  - `products` (TEXT, array di ID prodotto codificato in JSON)
  - `categories` (TEXT, array di ID categoria codificato in JSON)
  - `manufacturers` (TEXT, array di ID produttore codificato in JSON)
  - `display_product` (TINYINT)
  - `display_category` (TINYINT)
  - `display_manufacturer` (TINYINT)
- `ps_aappro_custom_field`: Memorizza le definizioni dei campi personalizzati associati a ciascun modulo.

  - `id_aappro_custom_field` (PK)
  - `id_aappro_form` (FK a `ps_aappro_form`)
  - `name` (VARCHAR)
  - `type` (VARCHAR, ad esempio 'text', 'textarea', 'select', 'checkbox')
  - `label` (TEXT, multilingua)
  - `required` (TINYINT)
  - `options` (TEXT, codificato in JSON per opzioni select/radio)
  - `position` (INT)
  - `active` (TINYINT)
- `ps_aappro_question`: Memorizza ogni domanda del cliente inviata.

  - `id_aappro_question` (PK)
  - `id_product` (FK a `ps_product`)
  - `id_customer` (FK a `ps_customer`, se loggato)
  - `id_aappro_form` (FK a `ps_aappro_form`)
  - `customer_name` (VARCHAR)
  - `customer_email` (VARCHAR)
  - `customer_phone` (VARCHAR, se abilitato)
  - `topic` (VARCHAR, se abilitato)
  - `quantity_request` (INT, se abilitato)
  - `question_text` (TEXT)
  - `attachment_path` (VARCHAR, se abilitato)
  - `custom_fields_data` (TEXT, array di valori di campi personalizzati codificato in JSON)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
  - `status` (VARCHAR, ad esempio 'new', 'replied', 'closed')
- `ps_aappro_question_reply`: Memorizza le risposte dell'amministratore alle domande dei clienti.

  - `id_aappro_question_reply` (PK)
  - `id_aappro_question` (FK a `ps_aappro_question`)
  - `id_employee` (FK a `ps_employee`)
  - `reply_text` (TEXT)
  - `date_add` (DATETIME)
- **Record di configurazione (nella tabella `ps_configuration`):**

  - `aappro_TITLE`
  - `aappro_AUTORESPONDER`
  - `aappro_FIELD_PHONE_REQUIRED`
  - `aappro_FIELD_PHONE_VISIBLE`
  - `aappro_FIELD_TOPIC_VISIBLE`
  - `aappro_QUOTE_QUANTITY_VISIBLE`
  - `aappro_WEBHOOK_URL`
  - `aappro_Q_LEN_MIN`
  - `aappro_Q_LEN_MAX`
  - `aappro_ATTACHMENT_ENABLE`
  - `aappro_ATTACHMENT_MAX_MB`
  - `aappro_SHOP_MAIL_BCC`
  - `aappro_TOAST_MS`
  - `aappro_FLOAT_DELAY_MS`
  - `aappro_THEME_SUPPORT`
  - `aappro_CUSTOM_CSS`
  - `aappro_CUSTOM_FIELDS_JSON` (probabilmente deprecato a favore della tabella `ps_aappro_custom_field`)
  - `aappro_recaptcha`
  - `aappro_GDPR`
  - `aappro_GDPRCMS`
  - `aappro_recaptcha_sitekey`
  - `aappro_ALLOW_COMMENTS`
  - `aappro_recaptcha_secretkey`
  - `aappro_emailslist`
  - `aappro_HIDE_OOS`
  - `aappro_LOGGED_CUSTOMERS_ONLY`

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Registra risorse CSS/JS, inizializza variabili JS globali o renderizza elementi nascosti per la funzionalità del modulo. |
| `displayFooter` | In fondo a ogni pagina, prima di `</body>`. | Può essere utilizzato per iniettare HTML modale, pulsanti fluttuanti o script che devono essere eseguiti dopo il caricamento della pagina. |
| `displayProductExtraContent` | Nel blocco "contenuto extra" sulle pagine prodotto (spesso sotto la descrizione). | Renderizza il modulo di richiesta o un trigger per esso, spesso come un blocco completo. |
| `displayProductAdditionalInfo` | Nel blocco informazioni prodotto, tipicamente vicino al prezzo/aggiungi al carrello. | Renderizza un trigger più piccolo o un modulo compatto direttamente all'interno delle informazioni principali del prodotto. |
| `displayProductButtons` | Vicino al pulsante "Aggiungi al carrello". | Renderizza un pulsante o un link per aprire il modulo di richiesta. |
| `displayProductTab` | Per aggiungere un nuovo titolo di scheda sulla pagina prodotto. | Renderizza il titolo della scheda "Fai una domanda" o "FAQ". |
| `displayProductTabContent` | Per aggiungere contenuto a una nuova scheda sulla pagina prodotto. | Renderizza il modulo di richiesta effettivo all'interno della sua scheda prodotto dedicata. |
| `displayReassurance` | Nel blocco di rassicurazione (ad esempio, "pagamento sicuro", "spedizione gratuita"). | Può essere utilizzato per iniettare un piccolo link o icona "Fai una domanda" all'interno del blocco di rassicurazione. |
| `actionAdminControllerSetMedia` | Quando un controller amministrativo viene caricato e le sue risorse multimediali vengono impostate. | Registra CSS e JS specifici del modulo per i controller del back-office (`AdminAapproForm`, `AdminAapproQuestion`). |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | (Non direttamente utilizzato dalla funzione core di questo modulo, ma potrebbe essere utilizzato per domande di follow-up post-acquisto se esteso). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Chiedi informazioni sul prodotto - moduli di contatto pro", fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda relativa alla funzionalità del modulo. Assicurati sempre di utilizzare l'ultima versione compatibile del modulo per prestazioni e sicurezza ottimali.
