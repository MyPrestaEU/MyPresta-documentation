---
title: "Aggiungi al carrello solo per utenti loggati - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Aggiungi al carrello solo per utenti loggati' di MyPresta.eu."
sidebar:
  label: "Aggiungi al carrello solo per utenti loggati - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Add to cart for logged only su MyPresta.eu](https://mypresta.eu/modules/ordering-process/add-to-cart-for-logged-only.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/add-to-cart-for-logged-only/)
>
> ---


# Aggiungi al carrello solo per utenti loggati

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Aggiungi al carrello solo per utenti loggati" per accedere alle sue impostazioni.

#### **Mostra**

- **Cosa fa questa impostazione:** Questo è l'interruttore principale per abilitare o disabilitare la funzionalità principale del modulo.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (Sì):* Il modulo sarà attivo. Gli utenti non loggati saranno impediti di aggiungere prodotti al carrello e verrà visualizzato un messaggio che li invita ad accedere.
  - *Quando disabilitato (No):* Il modulo sarà inattivo. Tutti gli utenti, loggati o meno, potranno aggiungere prodotti al carrello secondo il comportamento standard di PrestaShop.
- **Valore consigliato:** **Sì** se vuoi applicare la regola del carrello "solo per utenti loggati". **No** se vuoi disabilitare temporaneamente la funzione senza disinstallare il modulo.
- **Scenario / esempio del commerciante:** Se gestisci un negozio B2B e desideri che solo i tuoi clienti aziendali registrati possano visualizzare i prezzi ed effettuare ordini, imposteresti questo valore su "Sì". Se stai temporaneamente aprendo il tuo negozio alla navigazione pubblica e all'aggiunta al carrello per una promozione speciale, potresti impostarlo su "No" per quel periodo.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Mostra | Sì | Abilita/disabilita la funzionalità principale del modulo, limitando "Aggiungi al carrello" agli utenti loggati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato il modulo, ma gli utenti non loggati possono ancora aggiungere prodotti al carrello. Cosa c'è che non va?**
R:

1. **Svuota la cache:** Il problema più comune è la cache. Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
2. **Posizione del modulo:** Assicurati che il modulo sia agganciato correttamente. Sebbene il modulo gestisca questo automaticamente, a volte i conflitti del tema possono interferire. Controlla la configurazione del modulo e assicurati che sia attivo.
3. **Compatibilità del tema:** Molto raramente, un tema altamente personalizzato potrebbe sovrascrivere i comportamenti standard dei pulsanti di PrestaShop. Se svuotare la cache non funziona, passa temporaneamente al tema predefinito di PrestaShop (ad esempio, Classic) per vedere se il problema persiste. Se si risolve, il tuo tema sta probabilmente causando un conflitto e potresti aver bisogno di uno sviluppatore per indagare.

**D: Posso personalizzare il messaggio mostrato agli utenti non loggati?**
R: Sì, il messaggio è tipicamente traducibile. Vai su **Internazionale > Traduzioni** nel tuo Back Office. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona "Aggiungi al carrello solo per utenti loggati". Dovresti trovare la stringa di testo lì per modificarla per ogni lingua.

**D: Questo modulo influenzerà la mia SEO?**
R: No, questo modulo influisce principalmente sulla funzionalità del pulsante "Aggiungi al carrello" per gli utenti front-end. Non impedisce ai crawler dei motori di ricerca di indicizzare le tue pagine prodotto o i tuoi contenuti. I tuoi prodotti saranno comunque visibili e scopribili.

**D: Cosa succede se un cliente si disconnette dopo aver aggiunto articoli al carrello?**
R: Il modulo impedisce l'*aggiunta* al carrello quando non si è loggati. Se un cliente accede, aggiunge articoli e poi si disconnette, gli articoli rimangono tipicamente nel suo carrello (associati al suo account) per quando si ricollegherà. La restrizione del modulo si applica all'azione di aggiungere nuovi articoli quando non si è loggati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Aggiungi al carrello solo per utenti loggati" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Aggiungi al carrello solo per utenti loggati" è un modulo PrestaShop leggero progettato principalmente per intercettare e modificare il comportamento dell'azione "Aggiungi al carrello" in base allo stato di accesso dell'utente. Lo fa sfruttando il sistema di hook di PrestaShop e iniettando JavaScript per disabilitare o modificare il pulsante "Aggiungi al carrello" e visualizzare un messaggio per gli utenti non loggati. Non introduce nuove tabelle di database o modelli di oggetti complessi, concentrandosi invece sull'interazione front-end e sulle funzionalità core esistenti di PrestaShop.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office Admin personalizzati. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli core (`classes/`)

Questo modulo non introduce classi personalizzate né estende `ObjectModel`. La sua logica è principalmente contenuta nel file principale `cartforlogged.php`.

### 4.4 Risorse JavaScript (`views/js/`)

- **`cartforlogged/views/js/cfl-17500.js`**

  - **Ambito:** Front-office.
  - **Scopo:** Questo script è probabilmente progettato per le versioni di PrestaShop 1.7.x e 8.x (indicato da `17500`). Si rivolge al pulsante "Aggiungi al carrello" (`#add_to_cart button`, `.add-to-cart`) e potenzialmente ad altri elementi come gli input di quantità.
  - **Funzionalità:**
    - Controlla se l'utente è loggato (`isLogged`).
    - Se non è loggato, disabilita il pulsante "Aggiungi al carrello", ne cambia il testo (ad esempio, in "Solo utenti loggati...") e potenzialmente aggiunge una classe CSS per stilizzarlo visivamente come disabilitato.
    - Potrebbe anche impedire l'invio di moduli o le chiamate AJAX relative all'aggiunta di prodotti al carrello.
    - Probabilmente utilizza `prestashop.on('updateCart', ...)` o listener di eventi simili per riapplicare la sua logica dopo gli aggiornamenti del carrello o i cambiamenti di pagina (ad esempio, quando gli attributi del prodotto vengono modificati).
- **`cartforlogged/views/js/cfl.js`**

  - **Ambito:** Front-office.
  - **Scopo:** Questo script è probabilmente una versione più generica o di fallback, potenzialmente per versioni precedenti di PrestaShop (1.5.x, 1.6.x) o come base per il più specifico `cfl-17500.js`.
  - **Funzionalità:** Simile a `cfl-17500.js`, identifica il pulsante "Aggiungi al carrello" (ad esempio, `#add_to_cart button`, `.exclusive button`), controlla lo stato di accesso e disabilita il pulsante per gli utenti non loggati. Potrebbe utilizzare `$(document).ready()` di jQuery e la delega degli eventi per gestire i contenuti dinamici.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`cartforlogged/views/css/cfl.css`**
  - **Ambito:** Styling del cliente front-office.
  - **Scopo:** Fornisce uno stile di base per il pulsante "Aggiungi al carrello" disabilitato o il messaggio visualizzato agli utenti non loggati.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:**
    - `.cfl_disabled_button`: Probabilmente applicato al pulsante "Aggiungi al carrello" quando è disabilitato dal modulo. Gli sviluppatori possono usarlo per cambiare il colore di sfondo, il cursore, l'opacità, ecc., per indicare chiaramente che è inattivo.
    - `.cfl_message`: Se il modulo inietta un elemento messaggio specifico, questa classe lo stilizzerebbe.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`cartforlogged/views/templates/admin/json.tpl`**
  - **Ambito:** Template di amministrazione.
  - **Scopo:** Questo template è probabilmente utilizzato internamente dal metodo `getContent()` del modulo per produrre dati JSON, possibilmente per richieste AJAX all'interno della pagina di configurazione o per aggiornamenti dinamici dei contenuti. Non è un template visibile nel front-office. Potrebbe essere utilizzato per restituire lo stato della configurazione o altri dati al JavaScript nella pagina di amministrazione.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Questo modulo non crea tabelle di database personalizzate. Memorizza le sue impostazioni di configurazione (ad esempio, `CFL_LOGIN`) nella tabella standard `ps_configuration`.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere risorse CSS e JavaScript (`cfl.css`, `cfl.js`, `cfl-17500.js`) che modificano il comportamento del pulsante "Aggiungi al carrello". |
| `actionCartSave` | Dopo che un carrello viene salvato o aggiornato. | Questo hook potrebbe potenzialmente essere utilizzato per rivalutare il contenuto del carrello o applicare restrizioni, ma data la descrizione del modulo, la sua funzione principale è probabilmente l'iniezione JS front-end tramite `displayHeader`. Potrebbe essere un fallback o un modo per garantire la validazione lato server, sebbene la descrizione del modulo enfatizzi il lato client. |
| `actionAdminControllerSetMedia` | Quando un controller admin viene caricato e i suoi media (JS/CSS) vengono impostati. | Utilizzato per includere qualsiasi JavaScript o CSS necessario per la pagina di configurazione del Back Office del modulo. |
| `header` | Simile a `displayHeader`, spesso usato in modo intercambiabile o per temi legacy specifici. | Utilizzato per includere risorse CSS e JavaScript, garantendo la compatibilità tra diverse versioni e temi di PrestaShop. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Aggiungi al carrello solo per utenti loggati", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
