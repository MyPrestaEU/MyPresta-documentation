---
title: "Recensioni gratuite dei prodotti (commenti) - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Recensioni gratuite dei prodotti (commenti) di MyPresta.eu."
sidebar:
  label: "Recensioni gratuite dei prodotti (commenti)"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Free product reviews (comments) su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/free-product-reviews-comments.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/free-product-reviews-comments/)
>
> ---


# Recensioni gratuite dei prodotti (commenti)

## 1. Requisiti e Compatibilità
Questo modulo è progettato per un'ampia compatibilità con le moderne versioni di PrestaShop e gli ambienti di hosting standard.

-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili su qualsiasi ambiente di hosting moderno compatibile con PrestaShop. Non sono necessarie configurazioni server insolite o specializzate.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale del modulo "Recensioni gratuite dei prodotti (commenti)". Qui è dove controlli come le recensioni si comportano e appaiono nel tuo negozio.

#### Impostazioni generali

-   **Abilita recensioni:**
    *   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero sistema di recensioni.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* La sezione delle recensioni apparirà sulle pagine prodotto e i clienti potranno leggere e inviare recensioni.
        *   *Quando disabilitato:* La sezione delle recensioni sarà nascosta dalle pagine prodotto e non potranno essere inviate o visualizzate nuove recensioni.
    *   **Valore consigliato:** SÌ
    *   **Scenario / esempio per il commerciante:** Abilita questa opzione per iniziare a raccogliere e visualizzare il feedback dei clienti immediatamente dopo l'installazione.

-   **Le recensioni devono essere approvate da un dipendente:**
    *   **Cosa fa questa impostazione:** Determina se le recensioni vengono pubblicate automaticamente o richiedono l'approvazione manuale da parte di un amministratore del negozio.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Tutte le recensioni inviate entreranno in uno stato "in sospeso" e non saranno visibili nel front office finché un amministratore non le approverà manualmente nella sezione di gestione delle recensioni del modulo. Questo ti consente di filtrare spam, contenuti inappropriati o recensioni che non soddisfano le tue linee guida.
        *   *Quando disabilitato:* Le recensioni vengono pubblicate istantaneamente dopo l'invio, senza alcun intervento umano.
    *   **Valore consigliato:** SÌ (specialmente per i nuovi negozi o per mantenere il controllo qualità)
    *   **Scenario / esempio per il commerciante:** Se vuoi assicurarti che tutte le recensioni siano appropriate e costruttive prima che vengano pubblicate, abilita questa opzione. Questo è cruciale per mantenere l'immagine del tuo marchio e prevenire lo spam.

-   **Consenti recensioni degli ospiti:**
    *   **Cosa fa questa impostazione:** Controlla se i visitatori non loggati (ospiti) possono inviare recensioni.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Qualsiasi visitatore della tua pagina prodotto può inviare una recensione, anche se non ha un account o non è loggato. Tipicamente verrà chiesto un nome e un indirizzo email.
        *   *Quando disabilitato:* Solo i clienti che sono loggati nel loro account PrestaShop possono inviare recensioni.
    *   **Valore consigliato:** SÌ (per incoraggiare più recensioni) o NO (per assicurarsi che le recensioni provengano da clienti reali).
    *   **Scenario / esempio per il commerciante:** Se vuoi massimizzare il numero di recensioni, anche da parte di navigatori occasionali, abilita le recensioni degli ospiti. Se preferisci raccogliere recensioni solo da clienti verificati che hanno acquistato da te, disabilita questa opzione.

-   **Tempo minimo tra 2 recensioni dello stesso utente (in secondi):**
    *   **Cosa fa questa impostazione:** Imposta un periodo di attesa per impedire a un singolo utente di inviare più recensioni in rapida successione per lo stesso prodotto.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un valore (ad esempio, 3600 per 1 ora):* Un utente deve attendere almeno questo numero di secondi dopo aver inviato una recensione prima di poterne inviare un'altra per lo stesso prodotto.
        *   *Quando impostato su 0:* Non c'è limite di tempo e gli utenti possono inviare recensioni con la frequenza che desiderano.
    *   **Valore consigliato:** 3600 (1 ora) o 86400 (24 ore) per prevenire lo spam.
    *   **Scenario / esempio per il commerciante:** Per impedire a un singolo cliente di inondare un prodotto con più recensioni, imposta questo valore su una durata ragionevole come 3600 secondi (1 ora).

-   **Visualizza recensioni sulla pagina prodotto:**
    *   **Cosa fa questa impostazione:** Determina se l'elenco delle recensioni e il modulo di invio vengono mostrati direttamente sulla pagina prodotto.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* La sezione delle recensioni sarà visibile sulla pagina prodotto, consentendo ai clienti di leggere e scrivere recensioni.
        *   *Quando disabilitato:* La sezione delle recensioni sarà nascosta dalla pagina prodotto. Questo potrebbe essere usato se preferisci collegarti a una pagina di recensioni separata o gestire le recensioni in modo diverso.
    *   **Valore consigliato:** SÌ
    *   **Scenario / esempio per il commerciante:** Per rendere le recensioni facilmente accessibili agli acquirenti che navigano tra i tuoi prodotti, mantieni questa opzione abilitata.

-   **Numero di recensioni per pagina:**
    *   **Cosa fa questa impostazione:** Controlla quante recensioni vengono visualizzate su una singola pagina all'interno dell'elenco delle recensioni prima che venga applicata la paginazione.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un valore (ad esempio, 5):* Verranno mostrate solo 5 recensioni alla volta, con i pulsanti "Avanti" e "Indietro" o i numeri di pagina per navigare tra le restanti.
        *   *Quando impostato su un numero molto alto:* Tutte le recensioni potrebbero caricarsi su una pagina, il che può influire sulla velocità di caricamento della pagina se ci sono molte recensioni.
    *   **Valore consigliato:** 5-10
    *   **Scenario / esempio per il commerciante:** Se un prodotto ha molte recensioni, impostare questo valore su 5 o 10 manterrà la pagina prodotto ordinata e si caricherà rapidamente, consentendo comunque ai clienti di sfogliare tutti i feedback.

#### Gestione dei criteri di recensione

Questa sezione ti consente di definire criteri specifici (ad esempio, "Qualità", "Prezzo", "Caratteristiche") che i clienti possono valutare oltre alla valutazione complessiva del prodotto.

-   **Aggiungi nuovo criterio:**
    *   **Cosa fa:** Ti consente di creare un nuovo aspetto specifico di un prodotto che i clienti possono valutare (ad esempio, "Rapporto qualità-prezzo", "Facilità d'uso", "Durata").
    *   **Effetto della modifica di questa impostazione:** Quando aggiungi un criterio, questo apparirà come un'opzione di valutazione aggiuntiva nel modulo di invio delle recensioni sulla pagina del prodotto. I clienti potranno dare una valutazione a stelle per ogni criterio che definisci.
    *   **Valore consigliato:** Aggiungi criteri pertinenti ai tuoi prodotti.
    *   **Scenario / esempio per il commerciante:** Per un negozio di elettronica, potresti aggiungere criteri come "Prestazioni", "Durata della batteria" e "Design". Per un negozio di abbigliamento, "Vestibilità", "Qualità del materiale" e "Stile".

-   **Elenco dei criteri esistenti:**
    *   **Cosa fa:** Visualizza una tabella di tutti i criteri che hai precedentemente aggiunto, insieme alle opzioni per modificarli o eliminarli.
    *   **Effetto della modifica di questa impostazione:** Puoi modificare il nome di un criterio (ad esempio, cambiare "Qualità" in "Qualità del prodotto") o rimuovere un criterio se non è più pertinente. L'eliminazione di un criterio lo rimuoverà dagli invii futuri di recensioni, ma le recensioni esistenti che hanno utilizzato quel criterio potrebbero comunque visualizzare le loro valutazioni (a seconda dell'implementazione del modulo).
    *   **Valore consigliato:** Mantieni l'elenco dei tuoi criteri aggiornato e pertinente.
    *   **Scenario / esempio per il commerciante:** Se introduci una nuova linea di prodotti con caratteristiche uniche, potresti aggiungere un nuovo criterio. Se un criterio diventa ridondante, puoi eliminarlo.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Configurazione modulo | Abilita recensioni | SÌ | Interruttore principale per il sistema di recensioni. |
| Configurazione modulo | Le recensioni devono essere approvate da un dipendente | SÌ | Controlla l'approvazione manuale delle recensioni per prevenire spam/contenuti inappropriati. |
| Configurazione modulo | Consenti recensioni degli ospiti | SÌ | Consente agli utenti non loggati di inviare recensioni. |
| Configurazione modulo | Tempo minimo tra 2 recensioni dello stesso utente (in secondi) | 3600 (1 ora) | Previene lo spam di recensioni da parte di un singolo utente. |
| Configurazione modulo | Visualizza recensioni sulla pagina prodotto | SÌ | Mostra o nasconde la sezione delle recensioni sulle pagine prodotto. |
| Configurazione modulo | Numero di recensioni per pagina | 5-10 | Controlla la paginazione per l'elenco delle recensioni sulle pagine prodotto. |
| Configurazione modulo | Aggiungi nuovo criterio | N/A | Crea aspetti di valutazione specifici (ad esempio, "Qualità", "Prezzo"). |
| Configurazione modulo | Elenco dei criteri esistenti | N/A | Gestisce (modifica/elimina) i criteri di recensione personalizzati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le mie recensioni non vengono visualizzate sulla pagina prodotto dopo l'invio.**
R: Controlla se "Le recensioni devono essere approvate da un dipendente" è abilitato nella configurazione del modulo. In tal caso, devi approvarle manualmente nell'interfaccia di amministrazione del modulo (solitamente si trova nella pagina di configurazione del modulo, dove vedrai un elenco di recensioni). Una volta approvate, appariranno nel front office.

**D2: La sezione delle recensioni appare strana o non si adatta al design del mio tema.**
R: Questo è spesso un conflitto CSS con il tuo tema PrestaShop personalizzato.
    *   **Svuota la cache:** Per prima cosa, prova a svuotare la cache di PrestaShop in **Parametri avanzati > Prestazioni**.
    *   **Override del tema:** Il tuo tema potrebbe avere un proprio stile per gli elementi delle recensioni o potrebbe mancare uno stile specifico per questo modulo. Potrebbe essere necessario che un webmaster ispezioni il CSS e applichi stili personalizzati per farlo integrare perfettamente. Il modulo fornisce i propri file CSS (`myprestacomments.css`, ecc.), ma gli stili del tuo tema potrebbero sovrascriverli.

**D3: I clienti si lamentano di non poter inviare recensioni, o il modulo non appare.**
R:
    *   **Controlla "Abilita recensioni":** Assicurati che l'interruttore principale nella configurazione del modulo sia impostato su SÌ.
    *   **Controlla "Visualizza recensioni sulla pagina prodotto":** Assicurati che anche questo sia abilitato.
    *   **Recensioni degli ospiti:** Se gli utenti non loggati non possono inviare, controlla "Consenti recensioni degli ospiti". Se è disabilitato, solo i clienti loggati possono inviare.
    *   **Tempo minimo tra le recensioni:** Se un utente specifico non può inviare, potrebbe aver raggiunto il limite di "Tempo minimo tra 2 recensioni".

**D4: Come posso tradurre il testo del modulo in altre lingue?**
R: Puoi tradurre il testo del modulo direttamente all'interno di PrestaShop:
    1.  Vai su **Internazionale > Traduzioni**.
    2.  Seleziona "Traduzioni dei moduli installati" per il "Tipo di traduzione".
    3.  Scegli il tuo tema.
    4.  Seleziona la lingua che desideri tradurre.
    5.  Trova "Recensioni gratuite dei prodotti (commenti)" nell'elenco dei moduli e clicca su "Modifica". Potrai quindi modificare tutte le stringhe traducibili.

**D5: Voglio rimuovere una recensione inappropriata o spam.**
R: Naviga alla pagina di configurazione del modulo nel Back Office. Dovresti vedere un elenco di tutte le recensioni inviate. Da lì, puoi tipicamente "Eliminare" o "Disapprovare" le recensioni. Se hai abilitato "Le recensioni devono essere approvate da un dipendente", puoi semplicemente scegliere di non approvarla.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)
Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura
Il modulo "Recensioni gratuite dei prodotti (commenti)" (`myprestacomments`) segue un'architettura standard dei moduli PrestaShop, sfruttando `ModuleFrontController` per le interazioni del front-office e `Module` per la sua configurazione principale e la gestione degli hook. Utilizza una tabella di database personalizzata per archiviare i dati delle recensioni e si basa sui template Smarty per il rendering sia delle visualizzazioni delle recensioni del front-office che dei moduli di configurazione del back-office. Il modulo si integra con il sistema di hook di PrestaShop per iniettare il suo contenuto nelle pagine prodotto.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    *   `controllers/front/default.php`
        *   **Nome classe e classe genitore**: `MyPrestaCommentsDefaultModuleFrontController` che estende `ModuleFrontController`
        *   **Responsabilità**: Questo controller probabilmente gestisce la visualizzazione iniziale delle recensioni sulla pagina prodotto o funge da fallback per azioni generali relative alle recensioni. Tipicamente recupererebbe le recensioni per un dato prodotto e le passerebbe al template Smarty.
    *   `controllers/front/feedback.php`
        *   **Nome classe e classe genitore**: `MyPrestaCommentsFeedbackModuleFrontController` che estende `ModuleFrontController`
        *   **Responsabilità**: Questo controller è dedicato alla gestione dell'invio di nuove recensioni. Elabora le richieste POST dal modulo di recensione, convalida l'input (valutazione, commento, criteri), controlla i permessi di recensione degli ospiti e i limiti di tempo, quindi salva la recensione nel database. Gestisce anche lo stato di approvazione in base alla configurazione del modulo.
    *   `controllers/front/index.php`
        *   **Nome classe e classe genitore**: `MyPrestaCommentsIndexModuleFrontController` che estende `ModuleFrontController`
        *   **Responsabilità**: Questo controller potrebbe fungere da punto di ingresso generale o gestire le richieste AJAX relative alle recensioni, come il caricamento di più recensioni tramite paginazione o la gestione della funzionalità "segnala abuso".

-   **Controller Admin Back-Office**:
    *   Non sono elencati controller Admin personalizzati dedicati (`controllers/admin/`). Ciò suggerisce che l'amministrazione delle recensioni (elenco, approvazione, eliminazione) è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo (`index.php`) o tramite un `AdminController` standard che il modulo estende o integra. La presenza dei template `list_action_approve.tpl` e `list_action_noabuse.tpl` indica fortemente che la gestione delle recensioni è integrata in una vista elenco standard di PrestaShop, probabilmente all'interno della pagina di configurazione del modulo stesso.

### 4.3 Classi e modelli principali (`classes/`)
Nessuna classe personalizzata è elencata nella directory `classes/`. Ciò implica che il modulo potrebbe utilizzare un approccio più diretto per l'interazione con il database all'interno del suo file principale del modulo o dei controller, oppure potrebbe sfruttare gli `ObjectModel` esistenti di PrestaShop, se applicabile (anche se improbabile per dati di recensioni personalizzati). È probabile che la struttura dei dati delle recensioni sia gestita direttamente all'interno di `install.sql` e del file `index.php` del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

-   `js/jquery.rating.pack.js`
    *   **Ambito**: Front-office
    *   **Descrizione**: Un plugin jQuery per la creazione di widget di valutazione a stelle interattivi. Gestisce la visualizzazione visiva delle stelle e cattura la selezione della valutazione dell'utente nel modulo di invio delle recensioni.
-   `js/jquery.textareaCounter.plugin.js`
    *   **Ambito**: Front-office
    *   **Descrizione**: Un plugin jQuery per contare i caratteri o le parole in una textarea, spesso utilizzato per fornire feedback in tempo reale agli utenti sulla lunghezza della loro recensione.
-   `js/moderate.js`
    *   **Ambito**: Back-office
    *   **Descrizione**: Questo script probabilmente gestisce le azioni AJAX per la moderazione delle recensioni nel Back Office. Sarebbe responsabile dell'approvazione, disapprovazione o eliminazione delle recensioni senza un ricaricamento completo della pagina, interagendo con il metodo `getContent()` del modulo o con un controller admin nascosto.
-   `js/myprestacomments.js`
    *   **Ambito**: Front-office
    *   **Descrizione**: Il principale JavaScript personalizzato per il modulo. Orchesta la funzionalità di recensione del front-office, inclusi:
        *   Inizializzazione di `jquery.rating.pack.js` per le valutazioni a stelle.
        *   Gestione dell'invio del modulo di recensione (potenzialmente tramite AJAX).
        *   Visualizzazione di messaggi di successo o di errore.
        *   Gestione della paginazione o della funzionalità "carica altro" per le recensioni.
        *   Potenziale gestione dei clic su "segnala abuso".
-   `js/productCriterion.js`
    *   **Ambito**: Back-office
    *   **Descrizione**: Questo script viene utilizzato nel Back Office per la gestione dei criteri di recensione. Probabilmente gestisce l'aggiunta, la modifica e l'eliminazione dinamica dei campi dei criteri nella pagina di configurazione del modulo, possibilmente utilizzando AJAX per aggiornare il database.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `myprestacomments.css`
    *   **Ambito**: Front-office e Back-office
    *   **Descrizione**: Il foglio di stile principale per il modulo, contenente stili generali per la sezione delle recensioni, le valutazioni a stelle, i moduli di recensione e potenzialmente alcuni stili di base del pannello di amministrazione.
    *   **Selettori chiave**: `.myprestacomments_block`, `.myprestacomments_review_list`, `.myprestacomments_form`, `.star_content`, `.comment_item`, `.review_rating`.
-   `myprestacomments16.css`
    *   **Ambito**: Front-office e Back-office
    *   **Descrizione**: Probabilmente un foglio di stile di compatibilità per PrestaShop 1.6.x, contenente override o aggiustamenti specifici per la struttura del tema predefinito di quella versione.
-   `myprestacomments24.css`
    *   **Ambito**: Front-office e Back-office
    *   **Descrizione**: Probabilmente un foglio di stile di compatibilità per PrestaShop 1.7.x o 8.x, contenente override o aggiustamenti specifici per la struttura del tema predefinito di quelle versioni (ad esempio, tema Classic).
-   `myprestacomments32.css`
    *   **Ambito**: Front-office e Back-office
    *   **Descrizione**: Probabilmente un foglio di stile di compatibilità per PrestaShop 9.x, contenente override o aggiustamenti specifici per la struttura del tema predefinito più recente.

### 4.6 Struttura dei template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    *   `myprestacomments/mypresta_myprestacomments.tpl`
        *   **Hook**: Probabilmente `displayProductButtons` o `displayProductExtraContent` (o hook simili della pagina prodotto).
        *   **Output**: Questo è il template principale per visualizzare il riepilogo delle recensioni (valutazione media, numero di recensioni) e il pulsante/link "Scrivi una recensione" sulla pagina prodotto. Spesso funge da wrapper per l'elenco completo delle recensioni e il modulo.
    *   `myprestacomments/mypresta_myprestacomments_reviews_list.tpl`
        *   **Hook**: Renderizzato all'interno di `mypresta_myprestacomments.tpl` o agganciato direttamente se il modulo utilizza una scheda separata.
        *   **Output**: Visualizza l'elenco effettivo delle singole recensioni dei clienti, incluse le loro valutazioni, titoli, commenti e informazioni sul recensore. Gestirà anche la paginazione.

-   **Template admin (`views/templates/admin/`)**:
    *   `myprestacomments/views/templates/admin/advert.tpl`
        *   **Output**: Probabilmente visualizza una pubblicità o un messaggio promozionale da MyPresta.eu all'interno della pagina di configurazione del modulo.
    *   `myprestacomments/views/templates/admin/list_action_approve.tpl`
        *   **Output**: Un frammento di template per un pulsante o link di azione "Approva", utilizzato all'interno di un elenco di recensioni in sospeso nel Back Office.
    *   `myprestacomments/views/templates/admin/list_action_noabuse.tpl`
        *   **Output**: Un frammento di template per un pulsante o link di azione "Segna come non abusivo", utilizzato all'interno di un elenco di recensioni segnalate nel Back Office.
    *   `myprestacomments/views/templates/admin/_configure/helpers/form/form.tpl`
        *   **Output**: Questo è un override di un template helper standard di PrestaShop, utilizzato per renderizzare il modulo di configurazione del modulo (impostazioni generali, gestione dei criteri) nel Back Office. Definisce il layout e i campi di input per il metodo `getContent()`.
    *   `myprestacomments/views/templates/admin/_configure/helpers/list/list_content.tpl`
        *   **Output**: Un altro override di un template helper standard di PrestaShop, utilizzato per renderizzare l'elenco delle recensioni (o dei criteri) nel Back Office, incluse le colonne per i dettagli delle recensioni, lo stato e i pulsanti di azione (approva, elimina).

-   **Template front-office (`views/templates/front/`)**:
    *   `myprestacomments/views/templates/front/feedback.tpl`
        *   **Output**: Il template per il modulo di invio delle recensioni stesso. Include l'input per la valutazione a stelle, i campi di testo per titolo e commento e potenzialmente i campi per le valutazioni dei criteri personalizzati. Viene renderizzato quando un cliente clicca su "Scrivi una recensione".

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   `myprestacomments/install.sql`: Questo file contiene le istruzioni SQL eseguite durante l'installazione del modulo. Definirà almeno una tabella personalizzata:
        *   `ps_myprestacomments_reviews`: Archivia i dati effettivi delle recensioni (ID prodotto, ID cliente, valutazione, titolo, commento, data, stato di approvazione, stato di abuso).
        *   `ps_myprestacomments_criteria`: Archivia i criteri di recensione personalizzati definiti dal commerciante (ad esempio, "Qualità", "Prezzo").
        *   `ps_myprestacomments_review_criterion`: Una tabella di collegamento se le recensioni possono valutare più criteri.

-   **Tabella degli hook registrati**:

| Nome hook | Tempo di esecuzione | Scopo tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Per includere i file CSS e JS del modulo globalmente o condizionalmente. |
| `displayProductExtraContent` | Sulla pagina prodotto, tipicamente sotto la descrizione principale del prodotto o in una scheda. | Per visualizzare il riepilogo delle recensioni, l'elenco delle recensioni e il modulo "Scrivi una recensione". |
| `displayProductButtons` | Sulla pagina prodotto, vicino al pulsante Aggiungi al carrello. | Per visualizzare un collegamento rapido o un pulsante alla sezione delle recensioni. |
| `displayFooter` | Nel piè di pagina di ogni pagina. | Meno comune, ma potrebbe essere utilizzato per un collegamento generale alle recensioni o a contenuti specifici del modulo. |
| `displayLeftColumn` / `displayRightColumn` | Nella barra laterale sinistra o destra. | Potrebbe essere utilizzato per visualizzare un blocco di recensioni recenti o un riepilogo delle recensioni. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Potenzialmente utilizzato per attivare un'e-mail al cliente che chiede una recensione dei prodotti acquistati. |
| `actionProductUpdate` | Dopo che un prodotto è stato aggiornato nel Back Office. | Per svuotare la cache relativa alle recensioni dei prodotti, se necessario. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Dopo che un prodotto è stato aggiunto o aggiornato. | Per garantire l'integrità dei dati delle recensioni o l'invalidazione della cache. |

## 5. Supporto ufficiale e aggiornamenti
Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore assistenza con il modulo "Recensioni gratuite dei prodotti (commenti)", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per aiutare con problemi relativi al modulo e garantire che il tuo negozio funzioni senza intoppi.
