---
title: "Hooks Manager - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Hooks Manager di MyPresta.eu."
sidebar:
  label: "Hooks Manager - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Hooks Manager su MyPresta.eu](https://mypresta.eu/modules/administration-tools/hooks-manager.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/hooks-manager/)
>
> ---


# Hooks Manager

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo Hooks Manager. Vedrai un elenco di tutti gli hook personalizzati che hai creato, insieme alle opzioni per aggiungerne di nuovi.

#### Aggiunta di un nuovo hook personalizzato:

Nella parte superiore della pagina di configurazione, troverai i campi per creare un nuovo hook.

- **Nome dell'Hook:**

  - **Cosa fa questa impostazione:** Questo è il nome tecnico univoco per il tuo nuovo hook. Deve iniziare con `display` (es. `displayMyCustomHook`, `displayProductExtraInfo`). Questo nome è quello che userai in seguito nei file `.tpl` del tuo tema per "chiamare" l'hook.
  - **Effetto della modifica di questa impostazione:** Questo nome è cruciale per gli sviluppatori per posizionare l'hook nel tuo tema. Modificarlo dopo la creazione richiederebbe l'aggiornamento dei file del tuo tema.
  - **Valore consigliato:** Usa nomi descrittivi in camelCase che iniziano con `display`. Esempio: `displayProductBelowAddToCart`, `displayHomepagePromoBanner`.
  - **Scenario / esempio per il commerciante:** Vuoi aggiungere un banner sotto il pulsante "Aggiungi al carrello" nelle pagine prodotto. Potresti chiamare l'hook `displayProductBelowAddToCart`.
- **Titolo dell'Hook:**

  - **Cosa fa questa impostazione:** Questo è un titolo amichevole e leggibile per il tuo hook che apparirà nel tuo Back Office di PrestaShop (ad esempio, quando vai su **Design > Posizioni** per assegnare moduli agli hook).
  - **Effetto della modifica di questa impostazione:** Rende più facile identificare il tuo hook personalizzato tra i molti hook standard nel Back Office.
  - **Valore consigliato:** Un titolo chiaro e descrittivo. Esempio: "Pagina Prodotto - Sotto Aggiungi al Carrello", "Homepage - Banner Promozionale Superiore".
  - **Scenario / esempio per il commerciante:** Per l'hook `displayProductBelowAddToCart`, imposteresti il titolo su "Pagina Prodotto - Sotto Aggiungi al Carrello".
- **Descrizione dell'Hook:**

  - **Cosa fa questa impostazione:** Una descrizione opzionale più lunga per fornire più contesto sullo scopo o sul posizionamento previsto dell'hook. Anche questa è per uso interno nel Back Office.
  - **Effetto della modifica di questa impostazione:** Aiuta te e il tuo team a ricordare il caso d'uso specifico per ogni hook personalizzato.
  - **Valore consigliato:** Spiega brevemente dove l'hook è destinato ad essere posizionato e che tipo di contenuto dovrebbe contenere. Esempio: "Destinato a badge di fiducia o piccoli messaggi promozionali direttamente sotto il pulsante aggiungi al carrello."
  - **Scenario / esempio per il commerciante:** Per l'hook `displayProductBelowAddToCart`, potresti aggiungere "Usa per piccoli badge di fiducia o un messaggio di spedizione gratuita."
- **Visibilità:**

  - **Cosa fa questa impostazione:** Determina se l'hook è visibile nell'elenco degli hook disponibili quando vai su **Design > Posizioni** nel tuo Back Office di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* L'hook apparirà nell'elenco, permettendoti di assegnare facilmente moduli ad esso.
    - *Quando disabilitato:* L'hook esisterà e funzionerà se chiamato nel tuo tema, ma non apparirà nell'elenco "Design > Posizioni", rendendo più difficile la gestione dei moduli per esso.
  - **Valore consigliato:** **Abilitato (Sì)**, a meno che tu non abbia una ragione molto specifica per nasconderlo.
  - **Scenario / esempio per il commerciante:** Hai creato un nuovo hook e vuoi iniziare immediatamente ad assegnare moduli ad esso. Tienilo abilitato.

#### Gestione degli hook personalizzati esistenti:

Sotto la sezione "Aggiungi nuovo hook", vedrai una tabella che elenca tutti gli hook personalizzati che hai creato.

- **Interruttore Abilitato / Disabilitato (per ogni hook):**

  - **Cosa fa questa impostazione:** Questo interruttore ti consente di attivare o disattivare un singolo hook personalizzato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* L'hook è attivo e tutti i moduli ad esso assegnati renderanno il loro contenuto quando l'hook viene chiamato nel tuo tema.
    - *Quando disabilitato:* L'hook è inattivo. Anche se chiamato nel tuo tema, non renderà alcun contenuto dai moduli ad esso assegnati. Questo è un modo soft per nascondere temporaneamente il contenuto senza disconnettere i moduli.
  - **Valore consigliato:** **Abilitato** per gli hook che vuoi usare, **Disabilitato** per gli hook che vuoi nascondere temporaneamente.
  - **Scenario / esempio per il commerciante:** Hai un banner promozionale stagionale posizionato tramite un hook personalizzato. Quando la promozione termina, puoi disabilitare l'hook per nascondere il banner senza rimuovere il modulo.
- **Modifica Live (per ogni hook):**

  - **Cosa fa questa impostazione:** Questo è un collegamento rapido alla pagina "Design > Posizioni", filtrato per mostrare solo l'hook personalizzato selezionato.
  - **Effetto della modifica di questa impostazione:** Cliccando su questo pulsante si accede direttamente alla pagina dove è possibile "agganciare" (assegnare) altri moduli a questo specifico hook personalizzato.
  - **Valore consigliato:** Usa questo pulsante ogni volta che vuoi assegnare un modulo al tuo hook personalizzato appena creato.
  - **Scenario / esempio per il commerciante:** Hai appena creato `displayProductBelowAddToCart` e ora vuoi assegnargli il tuo modulo "Badge di fiducia". Clicca su "Modifica Live" accanto a `displayProductBelowAddToCart`.

#### Altre chiavi di configurazione (Interne):

Potresti vedere `mypresta_updates`, `update_`, `updatev_` nella configurazione interna del modulo. Questi sono tipicamente correlati agli aggiornamenti del modulo e ai controlli di licenza di MyPresta.eu e non richiedono l'interazione del commerciante.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Nome Hook | Descrittivo, prefisso `display` | Identificatore tecnico univoco per l'hook. Utilizzato nei file del tema. |
| Configurazione modulo | Titolo Hook | Chiaro, leggibile | Appare in Design > Posizioni per una facile identificazione. |
| Configurazione modulo | Descrizione Hook | Opzionale, informativa | Fornisce contesto per lo scopo dell'hook. |
| Configurazione modulo | Visibilità | Abilitato (Sì) | Rende l'hook visibile in Design > Posizioni per l'assegnazione del modulo. |
| Configurazione modulo | Abilitato / Disabilitato (per hook) | Abilitato | Attiva/disattiva la capacità dell'hook personalizzato di renderizzare il contenuto. |
| Configurazione modulo | Modifica Live (per hook) | N/A (Pulsante azione) | Collegamento diretto a Design > Posizioni per assegnare moduli all'hook. |

## 3. Risoluzione dei problemi per i commercianti e domande frequenti (FAQ)

**D: Ho creato un hook e assegnato un modulo, ma non appare nulla nel mio negozio. Cosa c'è che non va?**
R: Questo è il problema più comune. Il modulo Hooks Manager *crea* l'hook, ma tu (o il tuo webmaster) devi comunque *posizionare* quell'hook nei file `.tpl` del tuo tema.
- **Soluzione:** Devi modificare i file del tuo tema (ad esempio, `product.tpl`, `index.tpl`, `header.tpl`, `footer.tpl`) e inserire il seguente frammento di codice dove vuoi che appaia l'hook: `{$hook_name}`. Sostituisci `hook_name` con il nome effettivo del tuo hook (ad esempio, `{$hook_displayProductBelowAddToCart}`).
- **Controlla anche:**
1. L'hook è "Abilitato" nella configurazione di Hooks Manager?
2. Il modulo che stai cercando di visualizzare è effettivamente "agganciato" al tuo hook personalizzato in **Design > Posizioni**?
3. Hai svuotato la cache di PrestaShop (**Parametri avanzati > Prestazioni**)?

**D: Posso usare lo stesso hook personalizzato più volte in luoghi diversi?**
R: Sì, puoi. Se posizioni `{$hook_displayMyCustomHook}` in `product.tpl` e anche in `category.tpl`, qualsiasi modulo assegnato a `displayMyCustomHook` verrà renderizzato in entrambe le posizioni. Questo è potente per visualizzare contenuti coerenti su diversi tipi di pagina.

**D: Il mio hook personalizzato viene visualizzato, ma lo stile è sbagliato. Cosa posso fare?**
R: Il modulo Hooks Manager fornisce solo lo "slot". Lo stile del contenuto all'interno di quello slot è determinato dal modulo che hai posizionato lì e dal CSS del tuo tema.
- **Soluzione:** Potrebbe essere necessario aggiungere CSS personalizzato al tuo tema per stilizzare il contenuto renderizzato dal modulo nel tuo hook personalizzato. Il tuo webmaster può aiutarti con questo.

**D: Voglio rimuovere un hook personalizzato. Come posso farlo in sicurezza?**
R: Nella configurazione di Hooks Manager, vedrai un pulsante "Elimina" accanto a ogni hook personalizzato.
- **Importante:** Prima di eliminare, assicurati di aver rimosso tutte le chiamate a quell'hook (`{$hook_yourCustomHookName}`) dai file `.tpl` del tuo tema. Se elimini l'hook ma lasci la chiamata nel tuo tema, potrebbe causare un errore minore o semplicemente non renderizzare nulla. Inoltre, scollega tutti i moduli da esso tramite **Design > Posizioni**.

**D: Questo modulo influisce sulle prestazioni del mio negozio?**
R: Il modulo stesso è molto leggero. L'aggiunta di più hook e l'assegnazione di più moduli *possono* aumentare gradualmente il tempo di caricamento della pagina, ma questo è vero per qualsiasi contenuto aggiuntivo sulla tua pagina, indipendentemente da come è agganciato. L'impatto è generalmente trascurabile a meno che tu non stia aggiungendo dozzine di moduli complessi a una singola pagina.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Hooks Manager è un modulo PrestaShop semplice progettato per estendere il meccanismo di aggancio principale. Sfrutta principalmente la classe `Module` di PrestaShop e la tabella `Configuration` per gestire le definizioni degli hook personalizzati. Non introduce modelli MVC complessi o tabelle di database personalizzate, ma manipola indirettamente le tabelle `ps_hook` e `ps_hook_module` tramite l'API di PrestaShop. La funzionalità principale del modulo risiede nel suo file PHP principale, `hooksmanager.php`, che gestisce l'installazione, la disinstallazione e l'interfaccia di configurazione del Back Office.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Tutti i rendering del front-office sono gestiti dal metodo standard `Hook::exec()` di PrestaShop quando l'hook personalizzato viene chiamato in un file `.tpl`.
- **Controller Admin Back-Office**: Nessuno. Tutta l'amministrazione è gestita direttamente all'interno del metodo `getContent()` del file `hooksmanager.php`.

### 4.3 Classi e modelli principali (`classes/`)

- Nessuna classe personalizzata o definizione di `ObjectModel` è presente nella directory `classes/`. Il modulo interagisce direttamente con le classi `Hook` e `Module` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessun file JavaScript personalizzato è presente nel modulo. La configurazione del Back Office si basa su elementi di form standard di PrestaShop e potenzialmente su jQuery se incluso globalmente da PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessun file CSS personalizzato è presente nel modulo. La configurazione del Back Office utilizza lo stile predefinito del tema admin di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

- Nessun file di template Smarty personalizzato è presente nel modulo. L'intera interfaccia di configurazione viene renderizzata direttamente all'interno del metodo `getContent()` di `hooksmanager.php` utilizzando HTML puro e le classi helper di PrestaShop.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea le proprie tabelle di database personalizzate.
  - Interagisce principalmente con le seguenti tabelle principali di PrestaShop:
    - `ps_hook`: Memorizza le definizioni di tutti gli hook, inclusi quelli creati da questo modulo.
    - `ps_hook_lang`: Memorizza i titoli e le descrizioni traducibili per gli hook.
    - `ps_module_hook`: Collega i moduli agli hook, definendo quale modulo viene visualizzato in quale hook.
    - `ps_configuration`: Memorizza i valori di configurazione specifici del modulo (ad esempio, `mypresta_updates`, `update_`, `updatev_` per la gestione interna del modulo).
- **Tabella degli hook registrati**:
  Il modulo stesso non registra alcun hook per visualizzare il proprio contenuto. Il suo scopo è *creare* nuovi hook da utilizzare per altri moduli.

  La funzionalità principale del modulo include:

  - `install()`:
    - Registra il modulo a `displayAdminProductsExtra` (o simile, anche se non esplicitamente indicato nel dossier, questo è comune per gli strumenti di amministrazione per mostrare un link).
    - Crea una nuova scheda nel Back Office (se applicabile, anche se non esplicitamente indicato per questo modulo, è comune per gli strumenti di amministrazione).
    - Imposta i valori di configurazione predefiniti in `ps_configuration`.
  - `uninstall()`:
    - Elimina tutti gli hook personalizzati creati dal modulo da `ps_hook` e `ps_hook_lang`.
    - Rimuove le voci `ps_module_hook` associate.
    - Pulisce i valori di configurazione da `ps_configuration`.
  - `getContent()`:
    - Gestisce l'invio del modulo di configurazione del Back Office.
    - Elabora la creazione, l'aggiornamento e l'eliminazione degli hook personalizzati.
    - Renderizza l'HTML per la pagina di configurazione, elencando gli hook esistenti e fornendo il modulo per aggiungerne di nuovi.
    - Utilizza i metodi `Hook::add()` e `Hook::remove()` per gestire le voci degli hook nel database.

  **Nota per gli sviluppatori sull'uso degli hook personalizzati:**
  Per utilizzare un hook personalizzato creato da questo modulo, uno sviluppatore deve inserire manualmente la variabile Smarty `{$hook_YOUR_CUSTOM_HOOK_NAME}` nel file `.tpl` desiderato all'interno del tema PrestaShop attivo. Ad esempio, se viene creato un hook chiamato `displayProductBelowAddToCart`, lo sviluppatore aggiungerebbe `{$hook_displayProductBelowAddToCart}` a `themes/your_theme/templates/catalog/_partials/product-details.tpl` o `product.tpl` nella posizione desiderata. Il metodo `Hook::exec()` di PrestaShop gestirà quindi il rendering dei moduli assegnati a questo hook personalizzato.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo Hooks Manager, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il tuo modulo funzioni in modo ottimale e ad assisterti con qualsiasi domanda tecnica tu possa avere.
"""
