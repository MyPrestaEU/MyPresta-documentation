---
title: "Invia a un amico - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Invia a un amico di MyPresta.eu."
sidebar:
  label: "Invia a un amico - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Send to a friend su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-to-a-friend.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/send-to-a-friend/)
>
> ---


# Invia a un amico

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Invia a un amico". Qui puoi controllare come la funzione si comporta e appare sulle pagine dei tuoi prodotti.

#### Impostazioni generali

-   **Cosa fa questa impostazione:** Questa sezione contiene le impostazioni principali per abilitare o disabilitare il modulo e controllare la sua funzionalità di base.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il link/pulsante "Invia a un amico" e la funzionalità appariranno sulle pagine dei tuoi prodotti come configurato.
    -   *Quando disabilitato:* La funzione sarà completamente nascosta dal tuo negozio e nessuna email potrà essere inviata tramite essa.
-   **Valore consigliato:** **SÌ** (Abilitato) per consentire ai clienti di utilizzare la funzione.
-   **Scenario / esempio del commerciante:** Se desideri disabilitare temporaneamente la funzione per manutenzione o una specifica campagna di marketing, la imposteresti su "NO". Altrimenti, mantienila su "SÌ" per sfruttare il marketing del passaparola.

#### Opzioni di visualizzazione

-   **Cosa fa questa impostazione:** Queste opzioni controllano dove il link o il pulsante "Invia a un amico" apparirà sulle pagine dei tuoi prodotti. Il modulo utilizza il sistema di hook di PrestaShop per posizionare la funzione in diverse aree.
-   **Effetto della modifica di questa impostazione:**
    -   *Selezione di un hook (es. `displayProductButtons`):* Il link "Invia a un amico" verrà renderizzato in quell'area specifica della pagina del tuo prodotto.
    -   *Non selezionando alcun hook:* La funzione potrebbe non apparire affatto, o potrebbe apparire in una posizione predefinita se il tuo tema ha un rendering di fallback specifico.
-   **Valore consigliato:** `displayProductButtons` o `displayProductActions` sono hook comuni e consigliati in quanto posizionano il link vicino al pulsante "Aggiungi al carrello", rendendolo facilmente individuabile. Potresti anche considerare `displayFooterProduct` se preferisci che sia nella parte inferiore dei dettagli del prodotto.
-   **Scenario / esempio del commerciante:** Se desideri che il link "Invia a un amico" sia molto visibile e vicino alla principale call-to-action, scegli `displayProductButtons`. Se preferisci che sia meno prominente, magari nella parte inferiore delle informazioni sul prodotto, seleziona `displayFooterProduct`. Sperimenta con diversi hook per vedere cosa si adatta meglio al tuo tema.

#### Modello e contenuto dell'email

-   **Cosa fa questa impostazione:** Questa sezione ti consente di personalizzare l'oggetto e il contenuto dell'email che viene inviata all'amico.
-   **Effetto della modifica di questa impostazione:**
    -   *Modifica dell'oggetto:* La riga dell'oggetto dell'email rifletterà il tuo testo personalizzato, rendendola più coinvolgente o brandizzata.
    -   *Modifica del contenuto:* Il corpo dell'email includerà il tuo messaggio personalizzato, permettendoti di personalizzare la raccomandazione. Puoi usare segnaposto come `{product_name}` e `{product_link}` che verranno automaticamente sostituiti con i dettagli effettivi del prodotto.
-   **Valore consigliato:** Usa una riga dell'oggetto chiara e invitante (es. "Dai un'occhiata a questo prodotto da {your\_shop\_name}!") e un messaggio amichevole e informativo nel corpo. Includi sempre `{product_name}` e `{product_link}` per assicurarti che l'amico sappia cosa viene raccomandato e come trovarlo.
-   **Scenario / esempio del commerciante:** Potresti personalizzare l'email per dire: "Ciao {friend\_name}, {customer\_name} ha pensato che potresti apprezzare questo prodotto dal mio fantastico negozio! Si chiama {product\_name} e puoi trovarlo qui: {product\_link}. Buono shopping!"

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita/Disabilita Modulo | Abilitato | Controlla se la funzione "Invia a un amico" è attiva sul tuo negozio. |
| Configurazione modulo | Hook di visualizzazione | `displayProductButtons` | Determina dove appare il link "Invia a un amico" sulle pagine dei prodotti. |
| Configurazione modulo | Oggetto email | "Dai un'occhiata a questo prodotto!" | Personalizza la riga dell'oggetto dell'email inviata all'amico. |
| Configurazione modulo | Contenuto email | "Ciao {friend\_name}, {customer\_name} ha pensato che potresti apprezzare questo prodotto: {product\_name}. Puoi trovarlo qui: {product\_link}" | Personalizza il corpo dell'email, inclusi i dettagli dinamici del prodotto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il link "Invia a un amico" non appare sulle pagine dei miei prodotti. Cosa devo fare?**
R:

1.  **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Invia a un amico" sia installato e abilitato.
2.  **Verifica la configurazione:** Vai alla pagina di configurazione del modulo e assicurati che il modulo sia "Abilitato" e che tu abbia selezionato almeno un "Hook di visualizzazione" (es. `displayProductButtons`).
3.  **Svuota la cache:** PrestaShop spesso memorizza i contenuti nella cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
4.  **Compatibilità del tema:** Se stai utilizzando un tema personalizzato, potrebbe non essere esplicitamente progettato per renderizzare tutti gli hook di PrestaShop. Prova a passare temporaneamente al tema predefinito di PrestaShop per vedere se il link appare. Se lo fa, il tuo tema potrebbe richiedere una piccola modifica da parte di un webmaster per visualizzare l'hook scelto.

**D: I miei clienti stanno inviando email, ma non vengono ricevute dai loro amici.**
R:

1.  **Controlla le cartelle spam:** Chiedi all'amico di controllare la sua cartella spam o posta indesiderata.
2.  **Verifica le impostazioni email:** Assicurati che le impostazioni email del tuo negozio PrestaShop siano configurate correttamente in **Parametri avanzati > E-mail**. Prova a inviare un'email generale da PrestaShop per confermare che il tuo server di posta funzioni.
3.  **Log del modulo (Controllo sviluppatore):** Uno sviluppatore può controllare i log di posta di PrestaShop (se abilitati) o i log degli errori del server per problemi relativi all'invio di email.

**D: Posso cambiare il testo del link "Invia a un amico" o dei campi del modulo?**
R: Sì, puoi tradurre o modificare le stringhe di testo (etichette, testo del pulsante, ecc.) del modulo utilizzando lo strumento di traduzione di PrestaShop. Vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona il modulo "Invia a un amico". Potrai quindi modificare tutto il testo visibile.

**D: Il modulo pop-up appare strano o non è stilizzato correttamente sul mio dispositivo mobile.**
R:

1.  **Svuota la cache del browser:** Chiedi al cliente di svuotare la cache del browser sul suo dispositivo mobile.
2.  **Conflitti del tema:** I temi personalizzati possono talvolta sovrascrivere o entrare in conflitto con lo stile del modulo. Sebbene il modulo includa il proprio CSS (`send2friend.css`), il CSS del tuo tema potrebbe avere la precedenza. Un webmaster può ispezionare la pagina utilizzando gli strumenti di sviluppo del browser per identificare e risolvere i conflitti CSS.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Invia a un amico" (`send2friend`) è un modulo PrestaShop standard che implementa il pattern MVC. Utilizza principalmente controller frontali per le richieste AJAX, template Smarty per il rendering del modulo e hook per l'integrazione nella pagina del prodotto. Non introduce tabelle di database personalizzate o ObjectModels complessi, affidandosi alla funzionalità di posta elettronica principale di PrestaShop.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   **`controllers/front/AjaxSend.php`**
    -   **Nome classe:** `Send2FriendAjaxSendModuleFrontController`
    -   **Classe genitore:** `ModuleFrontController`
    -   **Responsabilità:** Questo controller gestisce la richiesta AJAX avviata quando un utente invia il modulo "Invia a un amico". Riceve il nome del mittente, il nome dell'amico, l'email dell'amico e l'ID del prodotto. Costruisce e invia l'email utilizzando il metodo `Mail::Send()` di PrestaShop. Restituisce una risposta JSON che indica successo o fallimento.
-   **`controllers/front/index.php`**
    -   **Nome classe:** `Send2FriendIndexModuleFrontController`
    -   **Classe genitore:** `ModuleFrontController`
    -   **Responsabilità:** Questo è un controller frontale segnaposto o predefinito. In molti moduli, questo potrebbe gestire una pagina front-office dedicata. Per "Invia a un amico", il suo ruolo principale potrebbe essere quello di garantire il caricamento delle risorse front-office del modulo o di servire da base per altri controller frontali. Data la funzionalità del modulo, il controller `AjaxSend` è quello più attivo.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non contiene classi o modelli personalizzati nella directory `classes/`. Sfrutta le funzionalità principali di PrestaShop, in particolare `Mail` per l'invio di email e `Product` per il recupero delle informazioni sul prodotto.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`views/js/send2friend.js`**
    -   **Ambito:** Front-office.
    -   **Dettagli:** Questo script è responsabile dell'interazione front-end della funzione "Invia a un amico".
        -   Probabilmente allega un listener di eventi al link/pulsante "Invia a un amico" per aprire il modale o visualizzare il modulo.
        -   Gestisce l'invio del modulo, raccogliendo i dati (nome del mittente, nome dell'amico, email dell'amico, ID del prodotto).
        -   Invia una richiesta AJAX al controller frontale `AjaxSend.php`.
        -   Elabora la risposta JSON dal server (successo/errore) e fornisce feedback all'utente (es. "Email inviata con successo!" o "Errore nell'invio dell'email.").
        -   Potrebbe includere logica per la convalida del modulo (es. controllo di formati email validi).
        -   Utilizza jQuery per la manipolazione del DOM e le chiamate AJAX, comuni nel front-office di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`views/css/send2friend.css`**
    -   **Ambito:** Styling del cliente front-office.
    -   **Dettagli:** Questo foglio di stile fornisce lo stile visivo di base per il link "Invia a un amico", il modale pop-up (se utilizzato) e i campi del modulo al suo interno.
        -   Definisce gli stili per il pulsante/link, i campi di input, le etichette e qualsiasi messaggio di successo/errore.
        -   I selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema includerebbero tipicamente classi come `.send2friend-button`, `.send2friend-modal`, `.send2friend-form`, `.send2friend-input`, ecc. Gli sviluppatori possono ispezionare l'HTML renderizzato per trovare le classi esatte utilizzate.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`views/templates/hook/send2friend-extra.tpl`**
    -   **Ambito:** Front-office.
    -   **Rendering dell'hook:** Questo template è progettato per essere renderizzato in vari hook della pagina del prodotto (es. `displayProductButtons`, `displayProductActions`, `displayFooterProduct`).
    -   **Blocco visivo:** Emette la struttura HTML per il link/pulsante "Invia a un amico" e il modale associato o il modulo inline. Questo include i campi di input per nomi e indirizzi email, e il pulsante di invio. Contiene anche i campi nascosti necessari (come `product_id`) e potenzialmente la struttura per la visualizzazione di messaggi di successo/errore.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo "Invia a un amico" non crea tabelle di database personalizzate. Memorizza le sue impostazioni di configurazione (come lo stato abilitato, l'hook scelto, l'oggetto e il contenuto dell'email) nella tabella `ps_configuration` di PrestaShop.

-   **`ps_configuration`**: Memorizza le impostazioni del modulo con chiavi tipicamente prefissate da `SEND2FRIEND_`.

#### Tabella degli hook registrati

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per caricare le risorse CSS e JavaScript del modulo a livello globale. |
| `displayProductButtons` | Vicino al pulsante "Aggiungi al carrello" sulle pagine dei prodotti. | Posizionamento comune per il link "Invia a un amico". |
| `displayProductActions` | Un altro hook comune vicino alle azioni del prodotto. | Posizionamento alternativo per il link "Invia a un amico". |
| `displayFooterProduct` | Nella parte inferiore del blocco informazioni del prodotto. | Posizionamento meno prominente per il link "Invia a un amico". |
| `displayRightColumnProduct` | Nella colonna destra della pagina del prodotto (se abilitata dal tema). | Possibile posizionamento per il link "Invia a un amico". |
| `displayLeftColumnProduct` | Nella colonna sinistra della pagina del prodotto (se abilitata dal tema). | Possibile posizionamento per il link "Invia a un amico". |

Il metodo `install()` del modulo registra questi hook, e il metodo `uninstall()` li deregistra. L'hook specifico scelto dal commerciante nella configurazione determina quale viene utilizzato attivamente per visualizzare il template.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Invia a un amico", fai riferimento al tuo account cliente MyPresta.eu. Puoi scaricare le versioni più recenti e accedere alle risorse di supporto direttamente da [MyPresta.eu](https://mypresta.eu).
