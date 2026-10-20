---
title: "Limita quantità di prodotti nel carrello per utenti non loggati - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Limita quantità di prodotti nel carrello per utenti non loggati di MyPresta.eu."
sidebar:
  label: "Limita quantità di prodotti nel carrello per utenti non loggati - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Limit quantity of products in cart for unlogged users su MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users/)
>
> ---


# Limita quantità di prodotti nel carrello per utenti non loggati

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo. La troverai navigando su **Moduli > Gestione moduli**, cercando "Limita quantità di prodotti nel carrello per utenti non loggati" e cliccando su "Configura".

#### **Quantità massima di prodotti nel carrello per utenti non loggati**

-   **Cosa fa questa impostazione:** Questa è l'impostazione principale del modulo. Definisce la quantità totale massima assoluta di articoli che un cliente non loggato può avere nel proprio carrello.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su 0:* Il modulo sarà effettivamente disabilitato e gli utenti non loggati potranno aggiungere una quantità illimitata di prodotti al carrello, proprio come gli utenti loggati.
    -   *Se impostato su un numero maggiore di 0 (es. 5):* Un cliente non loggato potrà aggiungere articoli al carrello fino a quando la quantità totale di tutti gli articoli non raggiungerà questo numero. Se tenta di aggiungere un altro articolo che supererebbe questo limite, il modulo impedirà l'aggiunta e visualizzerà il popup di avviso.
-   **Valore consigliato:** Questo dipende interamente dalla tua strategia aziendale.
    -   *Per i negozi B2C che desiderano incoraggiare delicatamente l'accesso:* Un valore come `3` o `5` può essere efficace.
    -   *Per i negozi B2B o i negozi con articoli di alto valore:* Un valore inferiore come `1` o `2` potrebbe essere appropriato per garantire che solo acquirenti seri e loggati possano riservare le scorte.
    -   *Se non desideri alcun limite:* Imposta su `0`.
-   **Scenario/esempio del commerciante:** Vendi magliette personalizzate. Vuoi che i navigatori occasionali vedano alcuni design nel loro carrello, ma per impegnarsi in un ordine più grande, preferisci che accedano. Imposti questo valore su `3`. Un cliente non loggato aggiunge una maglietta (quantità 1), poi un'altra (quantità 1), poi una terza (quantità 1). Il suo carrello ora ha 3 articoli. Se tenta di aggiungere una quarta maglietta, vedrà il messaggio popup, che lo invita ad accedere.

#### **Messaggio per utenti non loggati**

-   **Cosa fa questa impostazione:** Ti consente di personalizzare il testo del messaggio popup che appare quando un utente non loggato tenta di superare il limite di quantità del carrello definito.
-   **Effetto della modifica di questa impostazione:**
    -   *Se lo lasci come predefinito:* Verrà visualizzato il messaggio standard "Come cliente non loggato non puoi aggiungere altri prodotti al carrello. Effettua il login per continuare il processo di aggiunta al carrello."
    -   *Se lo personalizzi:* Verrà mostrato il tuo messaggio personalizzato. Questo ti consente di adattare il tono, aggiungere istruzioni specifiche o persino includere un link (anche se i link diretti nei popup possono essere complicati senza ulteriori personalizzazioni).
-   **Valore consigliato:** Il messaggio predefinito è chiaro ed efficace. Modificalo solo se hai una voce di branding specifica o istruzioni aggiuntive che desideri trasmettere. Mantienilo conciso.
-   **Scenario/esempio del commerciante:** Desideri un tono leggermente più morbido. Modifichi il messaggio in: "Per aggiungere altri articoli al carrello, effettua il login o crea un account. Ci piacerebbe vederti unirti alla nostra community!"

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Quantità massima di prodotti nel carrello per utenti non loggati** | `0` (disabilitato) / `3-5` (consigliato per B2C) | Imposta il numero totale di articoli che un cliente non loggato può aggiungere al carrello. Impedisce ulteriori aggiunte e mostra un popup se superato. |
| Configurazione modulo | **Messaggio per utenti non loggati** | "Come cliente non loggato non puoi aggiungere altri prodotti al carrello. Effettua il login per continuare il processo di aggiunta al carrello." | Personalizza il testo visualizzato nel popup quando un utente non loggato raggiunge il limite del carrello. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho impostato un limite, ma gli utenti non loggati possono ancora aggiungere prodotti illimitati. Cosa c'è che non va?**
R:

1.  **Controlla l'impostazione "Quantità massima":** Assicurati che sia impostata su un numero maggiore di `0`. Se è `0`, il modulo è disabilitato.
2.  **Svuota la cache del browser:** Il tuo browser potrebbe mostrarti una vecchia versione della pagina. Prova a svuotare la cache e i cookie del browser, oppure testa in una finestra di navigazione in incognito/privata.
3.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" in alto a destra.
4.  **Assicurati di essere veramente disconnesso:** Ricontrolla di non essere loggato a un account cliente nel tuo browser. Il modo più semplice per testare è aprire una nuova finestra di navigazione in incognito/privata.

**D: Il messaggio popup non viene visualizzato o appare strano.**
R:

1.  **Controlla l'impostazione "Messaggio per utenti non loggati" del modulo:** Assicurati che non sia vuota se ti aspetti un messaggio personalizzato.
2.  **Compatibilità del tema:** Sebbene il modulo sia progettato per essere compatibile, temi molto pesantemente personalizzati potrebbero talvolta interferire con JavaScript o CSS. Se il popup non appare affatto, controlla la console per sviluppatori del tuo browser per errori JavaScript (tasto F12, quindi scheda Console). Se appare strano, potrebbe essere un conflitto CSS. Contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D: Questo modulo influisce sui clienti loggati?**
R: No, questo modulo si rivolge specificamente agli utenti *non loggati*. Una volta che un cliente accede al proprio account, il limite di quantità imposto da questo modulo non si applica più a loro.

**D: Posso impostare limiti diversi per diverse categorie di prodotti?**
R: No, questo modulo applica un unico limite di quantità globale per tutti i prodotti nel carrello per gli utenti non loggati. Non supporta limiti specifici per categoria o per prodotto.

**D: Cosa succede se un utente non loggato aggiunge 3 articoli, poi accede e poi tenta di aggiungerne altri?**
R: Una volta che l'utente accede, non è più considerato "non loggato". La restrizione del modulo viene rimossa e può continuare ad aggiungere prodotti al carrello senza alcun limite di quantità da parte di questo modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Limita quantità di prodotti nel carrello per utenti non loggati" (`lqfu`) è un modulo PrestaShop leggero implementato principalmente tramite una classe di modulo principale (`lqfu/index.php`) e un file JavaScript personalizzato (`lqfu/views/js/lqfu.js`). Sfrutta il sistema di hook di PrestaShop per iniettare il suo JavaScript nel front office e utilizza AJAX per comunicare con la logica lato server per controllare e applicare il limite di quantità del carrello per gli utenti ospiti. Il modulo memorizza la sua configurazione in `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. La logica front-office del modulo è gestita direttamente tramite il file del modulo principale `hookDisplayHeader` e le richieste AJAX, che vengono elaborate dal `CartController` o `ProductController` di base di PrestaShop e intercettate dalla logica del modulo.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuna classe personalizzata che estende `ObjectModel` è definita in questo modulo. Tutta la logica risiede all'interno della classe principale `Lqfu` in `index.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`lqfu/views/js/lqfu.js`**
    -   **Ambito:** Front-office.
    -   **Scopo:** Questo script è responsabile dell'intercettazione delle azioni "Aggiungi al carrello", del controllo della quantità corrente del carrello per gli utenti non loggati e della visualizzazione del messaggio popup personalizzato se il limite viene superato.
    -   **Funzionalità chiave:**
        -   Associa listener di eventi ai pulsanti "Aggiungi al carrello" (o moduli) in tutto il negozio (es. pagina prodotto, elenchi categorie).
        -   Al tentativo di "Aggiungi al carrello", verifica prima se l'utente è loggato.
        -   Se l'utente non è loggato, recupera la quantità corrente del carrello (da un elemento nascosto o effettuando una chiamata AJAX se necessario).
        -   Confronta la quantità corrente del carrello + la quantità che viene aggiunta con il limite massimo configurato.
        -   Se il limite viene superato, impedisce l'azione predefinita "Aggiungi al carrello", visualizza un modale/popup personalizzato con il messaggio configurato e potenzialmente disabilita temporaneamente il pulsante "Aggiungi al carrello".
        -   Lo script probabilmente utilizza jQuery per la manipolazione del DOM e la gestione degli eventi, comune nel front-office di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`lqfu/views/css/lqfu.css`**
    -   **Ambito:** Stile del cliente front-office.
    -   **Scopo:** Fornisce uno stile di base per il messaggio popup che appare quando un utente non loggato supera il limite di quantità del carrello.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori possono aspettarsi classi relative al contenitore del popup, al testo del messaggio e possibilmente ai pulsanti di chiusura. Questi possono essere sovrascritti nel `custom.css` o `theme.css` di un tema personalizzato per corrispondere al branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, ma il modulo potrebbe implicitamente renderizzare il contenuto tramite `displayHeader` o hook simili se ha bisogno di iniettare dati nascosti o variabili JS iniziali.
-   **Template admin (`views/templates/admin/`)**:
    -   **`lqfu/views/templates/admin/json.tpl`**: Questo template è probabilmente utilizzato per renderizzare dati JSON in modo strutturato all'interno del Back Office, possibilmente per il debug o risposte AJAX specifiche dalla pagina di configurazione del modulo, sebbene il suo uso diretto per la configurazione principale sia meno comune. Potrebbe essere un residuo o utilizzato per una specifica funzione interna del modulo.
-   **Template front-office (`views/templates/front/`)**: Nessuno. Il popup è probabilmente generato dinamicamente tramite JavaScript.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   Il modulo non crea tabelle SQL personalizzate.
    -   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`:
        -   `PS_LQFU_MAX_QUANTITY`: Memorizza il valore intero per la quantità massima di prodotti per gli utenti non loggati.
        -   `PS_LQFU_MESSAGE`: Memorizza il valore stringa per il messaggio personalizzato visualizzato nel popup.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS (`lqfu.css`) e JavaScript (`lqfu.js`) del modulo nel front office. Può anche passare variabili di configurazione (come la quantità massima e il messaggio) al JavaScript. |
| `actionCartSave` | Dopo che un carrello è stato salvato (es. prodotto aggiunto/rimosso). | Il modulo probabilmente intercetta questo hook (o uno simile come `actionObjectCartAddAfter`) per rivalutare la quantità del carrello e potenzialmente impedire l'aggiunta di articoli se il limite viene superato per un utente non loggato. È qui che avverrebbe la convalida lato server prima che venga attivato il popup JS. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo "Limita quantità di prodotti nel carrello per utenti non loggati", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per aiutarti con qualsiasi problema o domanda tu possa avere.
