---
title: "Zopim Chat Free - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Zopim Chat Free di MyPresta.eu."
sidebar:
  label: "Zopim Chat Free - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Zopim Chat Free su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zopim-chat-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/zopim-chat-free/)
>
> ---


# Zopim Chat Free

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e per qualsiasi integrazione API esterna, incluso Zendesk Chat.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Zopim Chat Free)

Questa è la schermata di configurazione principale e unica per il modulo Zopim Chat Free. Qui inserirai la tua chiave account Zendesk Chat (Zopim) e deciderai dove lo script del widget di chat dovrebbe essere caricato nel tuo negozio.

#### **Chiave account Zopim**

-   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. È qui che inserisci l'identificatore unico fornito da Zendesk Chat (Zopim) per il tuo widget di live chat. Questa chiave indica al modulo quale widget di chat caricare sul tuo sito web. Puoi trovare questa chiave all'interno della tua dashboard di Zendesk Chat (solitamente sotto Impostazioni > Widget > Codice di incorporamento).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando viene inserita una chiave valida:* Il widget di chat Zopim associato al tuo account Zendesk Chat apparirà nel front-office del tuo negozio, consentendo ai clienti di avviare chat.
    -   *Quando lasciato vuoto o viene inserita una chiave non valida:* Il widget di chat Zopim non apparirà nel tuo negozio e la funzionalità di live chat non sarà disponibile.
-   **Valore consigliato:** La tua chiave account Zendesk Chat (Zopim) unica.
-   **Scenario / esempio per il commerciante:** Dopo esserti iscritto a Zendesk Chat, riceverai un frammento di codice. All'interno di quel codice, troverai una stringa specifica (ad esempio, `zopim.setAndDefer('account', 'YOUR_ACCOUNT_KEY');`). Copia `YOUR_ACCOUNT_KEY` e incollala qui.

#### **Carica Zopim Chat nell'Hook**

-   **Cosa fa questa impostazione:** Questa opzione determina dove nel codice del tuo negozio PrestaShop verrà iniettato lo script di chat Zopim. Sebbene il widget di chat stesso di solito fluttui sullo schermo, il posizionamento dello script a volte può influire sulla velocità di caricamento o sulla compatibilità con temi specifici.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su `displayHeader` (Intestazione):* Lo script di chat si caricherà molto presto, tipicamente prima della maggior parte del contenuto della tua pagina. Questo può far apparire il widget di chat rapidamente.
    -   *Quando impostato su `displayRightColumn` (Colonna destra):* Lo script si caricherà con il contenuto della colonna destra. Questo è meno comune per i widget di chat e potrebbe non essere l'ideale se il tuo tema non mostra sempre una colonna destra.
    -   *Quando impostato su `displayLeftColumn` (Colonna sinistra):* Simile alla colonna destra, lo script si carica con il contenuto della colonna sinistra.
    -   *Quando impostato su `displayProductButtons` (Pulsanti pagina prodotto):* Lo script si caricherà specificamente sulle pagine dei prodotti, vicino all'area del pulsante "Aggiungi al carrello". Questo potrebbe essere utile se desideri principalmente il supporto chat sulle pagine dei prodotti.
    -   *Quando impostato su `displayFooter` (Piè di pagina):* Lo script si caricherà alla fine del contenuto della tua pagina. Questo può migliorare la velocità di caricamento iniziale della pagina percepita dall'utente, poiché il contenuto principale si carica per primo e il widget di chat si carica successivamente.
-   **Valore consigliato:** `displayHeader` o `displayFooter`. Per la maggior parte dei negozi, `displayHeader` assicura che la chat si carichi rapidamente. Se riscontri conflitti o desideri dare priorità al caricamento del contenuto, `displayFooter` è una buona alternativa.
-   **Scenario / esempio per il commerciante:** Se i tuoi clienti pongono frequentemente domande *prima* ancora di iniziare a sfogliare i prodotti, caricare la chat in `displayHeader` assicura che sia disponibile immediatamente. Se noti che la tua pagina si carica lentamente e sospetti lo script di chat, passare a `displayFooter` potrebbe aiutare, poiché la chat si caricherà dopo il contenuto principale della pagina.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Chiave account Zopim | La tua chiave Zendesk Chat unica | Collega il tuo negozio al tuo account Zendesk Chat. Essenziale per la visualizzazione del widget. |
| Pagina di configurazione del modulo | Carica Zopim Chat nell'Hook | `displayHeader` o `displayFooter` | Determina dove viene iniettato lo script di chat (Intestazione, Colonne, Prodotto, Piè di pagina). Influisce sull'ordine di caricamento e sulla potenziale compatibilità del tema. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Il widget di chat Zopim non appare nel mio negozio. Cosa devo fare?**
R1:

1.  **Controlla la tua chiave account Zopim:** Vai alla pagina di configurazione del modulo e assicurati che la tua chiave account Zopim sia stata inserita correttamente. Anche un singolo errore di battitura ne impedirà il caricamento.
2.  **Verifica lo stato di Zendesk Chat:** Accedi alla tua dashboard di Zendesk Chat. Il tuo widget è attivo? I tuoi agenti sono online?
3.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** nel back office di PrestaShop e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte, i vecchi file memorizzati nella cache impediscono la visualizzazione delle nuove modifiche del modulo.
4.  **Verifica la presenza di conflitti con il tema:** Passa temporaneamente al tema predefinito di PrestaShop (ad esempio, Classic) e vedi se il widget appare. Se lo fa, il tuo tema personalizzato potrebbe causare un conflitto. Contatta lo sviluppatore del tuo tema o un webmaster.
5.  **Ispeziona la console del browser:** Apri gli strumenti per sviluppatori del tuo browser (F12) e controlla la scheda "Console" per eventuali errori JavaScript. Questo può fornire indizi se lo script non riesce a caricarsi.

**D2: Il widget di chat si carica, ma appare strano o è posizionato in modo errato.**
R2: Il modulo inietta lo script Zopim, ma lo stile visivo e il posizionamento esatto del widget sono in gran parte controllati dalle impostazioni del tuo account Zendesk Chat e dal CSS del tuo negozio.

1.  **Dashboard di Zendesk Chat:** Accedi alla tua dashboard di Zendesk Chat e rivedi le impostazioni di aspetto del tuo widget (ad esempio, posizione, colori, dimensioni).
2.  **CSS del tema:** Il CSS del tuo tema personalizzato potrebbe sovrascrivere alcuni stili Zopim predefiniti. Un webmaster può ispezionare l'elemento utilizzando gli strumenti per sviluppatori del browser e identificare le regole CSS in conflitto.

**D3: Posso tradurre il testo del widget di chat in diverse lingue?**
R3: Il modulo Zopim Chat Free stesso non gestisce le traduzioni per l'interfaccia del widget. Questa funzionalità è gestita direttamente all'interno delle impostazioni del tuo account Zendesk Chat. Zendesk Chat supporta più lingue e puoi configurare il widget per visualizzarlo nella lingua preferita del cliente in base alle impostazioni del suo browser o alla tua configurazione di Zendesk Chat.

**D4: Questo modulo rallenterà il mio sito web?**
R4: Il modulo Zopim Chat Free inietta solo lo script Zendesk Chat necessario. L'impatto sulle prestazioni dipende principalmente dal servizio Zendesk Chat stesso e dalla tua connessione internet. Puoi provare a impostare l'opzione "Carica Zopim Chat nell'Hook" su `displayFooter` per assicurarti che il contenuto principale della tua pagina si carichi prima dello script di chat, il che può migliorare la velocità di caricamento percepita della pagina.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che lavorano con il modulo Zopim Chat Free.

### 4.1 Panoramica dell'architettura

Il modulo `ZopimFree` è un modulo PrestaShop semplice progettato per integrare il widget Zendesk Chat (precedentemente Zopim). Funziona principalmente iniettando lo script di incorporamento di Zendesk Chat nel front-office del negozio PrestaShop. Il modulo segue una struttura standard dei moduli PrestaShop, utilizzando la classe `Module` per l'installazione, la disinstallazione e la gestione della configurazione tramite `getContent()`. Registra un singolo hook (`displayHeader` per impostazione predefinita, ma configurabile) per l'output del JavaScript necessario.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Il modulo inietta direttamente il contenuto negli hook.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuna classe personalizzata o definizione di `ObjectModel` è presente in questo modulo. Tutta la logica risiede all'interno del file principale `zopimfree.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   Nessun file JavaScript personalizzato è incluso in questo modulo. Il modulo produce lo script di incorporamento di Zendesk Chat direttamente nel template, che poi carica il JS necessario dal CDN di Zendesk.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessun file CSS personalizzato è incluso in questo modulo. Lo stile del widget di chat è gestito dal servizio Zendesk Chat stesso, con potenziali override dal tema PrestaShop attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   `zopimfree/header-new-widget.tpl`
        -   **Hook:** Questo template è progettato per essere renderizzato all'interno di un hook di PrestaShop, in particolare quello scelto nella configurazione del modulo (ad esempio, `displayHeader`, `displayFooter`).
        -   **Scopo:** Contiene il tag `<script>` responsabile dell'incorporamento del widget Zendesk Chat. Inserisce dinamicamente la `ZOPIMFREE_ACCOUNT_KEY` dalla configurazione del modulo nello script di inizializzazione di Zendesk Chat.
        -   **Output:** Produce il codice di incorporamento standard di Zendesk Chat, che poi carica il widget di chat dai server di Zendesk.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration`:
        -   `ZOPIMFREE_ACCOUNT_KEY`: Memorizza la chiave account di Zendesk Chat.
        -   `ZOPIMFREE_HOOK`: Memorizza il nome dell'hook in cui lo script dovrebbe essere iniettato (ad esempio, `displayHeader`, `displayFooter`).
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Hook predefinito per iniettare lo script Zendesk Chat all'inizio del caricamento della pagina. |
| `displayRightColumn` | Eseguito nella colonna destra delle pagine in cui è attivo. | Hook alternativo per l'iniezione dello script, meno comune per i widget di chat. |
| `displayLeftColumn` | Eseguito nella colonna sinistra delle pagine in cui è attivo. | Hook alternativo per l'iniezione dello script, meno comune per i widget di chat. |
| `displayProductButtons` | Eseguito sulle pagine dei prodotti, tipicamente vicino al pulsante "aggiungi al carrello". | Hook specifico per iniettare lo script di chat solo sulle pagine dei prodotti. |
| `displayFooter` | Eseguito appena prima del tag di chiusura `</body>`. | Hook alternativo per iniettare lo script Zendesk Chat più tardi nel caricamento della pagina, migliorando potenzialmente la velocità di caricamento iniziale percepita. |

Il modulo registra questi hook dinamicamente in base al valore di configurazione `ZOPIMFREE_HOOK`. Il metodo `install()` registra tutti i potenziali hook e `uninstall()` li deregistra. Il metodo `hook{NomeHook}` quindi controlla la configurazione per decidere se deve renderizzare il template.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto per sviluppatori per il modulo Zopim Chat Free, fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Assicurarsi di scaricare l'ultima versione compatibile con la propria installazione di PrestaShop.
