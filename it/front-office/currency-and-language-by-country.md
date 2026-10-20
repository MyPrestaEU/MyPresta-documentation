---
title: "Valuta e lingua per paese - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Valuta e lingua per paese di MyPresta.eu."
sidebar:
  label: "Valuta e lingua per paese - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Currency and language by country su MyPresta.eu](https://mypresta.eu/modules/front-office-features/currency-and-language-by-country.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/currency-and-language-by-country/)
>
> ---


# Valuta e lingua per paese

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su qualsiasi ambiente di hosting moderno. Nessuna estensione speciale è necessaria per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Valuta e lingua per paese". Qui troverai tutte le impostazioni per definire come il tuo negozio si adatta ai visitatori da paesi specifici.

**Accesso:** Back Office > Moduli > Gestione moduli > Cerca "Valuta e lingua per paese" > Clicca su "Configura".

#### **1. Seleziona paese**

-   **Cosa fa questa impostazione:** Questo menu a discesa ti consente di scegliere il paese specifico per il quale desideri applicare le modifiche automatiche di lingua e valuta.
-   **Effetto della modifica di questa impostazione:** Quando selezioni un paese (es. "Francia"), il modulo applicherà le impostazioni di lingua e valuta che definisci di seguito *solo* per i visitatori rilevati come provenienti da quel paese. Se non selezioni un paese, il modulo non applicherà alcuna regola di geolocalizzazione.
-   **Valore consigliato:** Seleziona prima il paese che desideri targettizzare. Con questa versione gratuita puoi configurare un solo paese alla volta.
-   **Scenario / esempio del commerciante:** Se desideri che i visitatori dalla Germania vedano il tuo negozio in tedesco con valuta Euro, selezioneresti "Germania" qui.

#### **2. Attiva cambio lingua per visitatore**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se il modulo deve cambiare automaticamente la lingua del negozio per i visitatori dal paese selezionato.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato ("Abilitato"):* Il modulo tenterà di cambiare la lingua del front-office del negozio a quella specificata nell'impostazione "Seleziona lingua" di seguito, per i visitatori dal paese scelto.
    -   *Quando disabilitato ("Disabilitato"):* La lingua non verrà cambiata automaticamente, anche se hai selezionato una lingua di seguito. Il visitatore vedrà il negozio nella tua lingua predefinita o nella lingua preferita del suo browser (se il comportamento predefinito di PrestaShop lo consente).
-   **Valore consigliato:** "Abilitato" se desideri fornire un'esperienza linguistica localizzata.
-   **Scenario / esempio del commerciante:** Se hai selezionato "Francia" come paese, abilitando questa impostazione significa che puoi quindi scegliere "Francese" come lingua per i visitatori francesi.

#### **3. Seleziona lingua**

-   **Cosa fa questa impostazione:** Questo menu a discesa appare solo se "Attiva cambio lingua per visitatore" è abilitato. Ti consente di scegliere quale lingua verrà impostata per i visitatori dal paese selezionato.
-   **Effetto della modifica di questa impostazione:** La lingua del front-office del negozio cambierà automaticamente nella lingua selezionata per i visitatori dal paese scelto. Assicurati che questa lingua sia già installata e abilitata nel tuo negozio PrestaShop (Back Office > Internazionale > Lingue).
-   **Valore consigliato:** La lingua ufficiale del paese selezionato.
-   **Scenario / esempio del commerciante:** Se hai selezionato "Spagna" come paese e abilitato il cambio lingua, selezioneresti "Spagnolo" qui.

#### **4. Attiva cambio valuta per visitatore**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se il modulo deve cambiare automaticamente la valuta del negozio per i visitatori dal paese selezionato.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato ("Abilitato"):* Il modulo tenterà di cambiare la valuta del front-office del negozio a quella specificata nell'impostazione "Seleziona valuta" di seguito, per i visitatori dal paese scelto.
    -   *Quando disabilitato ("Disabilitato"):* La valuta non verrà cambiata automaticamente. I prezzi verranno visualizzati nella valuta predefinita del tuo negozio o nella valuta selezionata manualmente dal cliente.
-   **Valore consigliato:** "Abilitato" se desideri visualizzare i prezzi nella valuta locale.
-   **Scenario / esempio del commerciante:** Se hai selezionato "Stati Uniti" come paese, abilitando questa impostazione significa che puoi quindi scegliere "Dollaro USA" come valuta per i visitatori statunitensi.

#### **5. Seleziona valuta**

-   **Cosa fa questa impostazione:** Questo menu a discesa appare solo se "Attiva cambio valuta per visitatore" è abilitato. Ti consente di scegliere quale valuta verrà impostata per i visitatori dal paese selezionato.
-   **Effetto della modifica di questa impostazione:** Tutti i prezzi nel front-office del negozio cambieranno automaticamente nella valuta selezionata per i visitatori dal paese scelto. Assicurati che questa valuta sia già installata e abilitata nel tuo negozio PrestaShop (Back Office > Internazionale > Valute).
-   **Valore consigliato:** La valuta ufficiale del paese selezionato.
-   **Scenario / esempio del commerciante:** Se hai selezionato "Giappone" come paese e abilitato il cambio valuta, selezioneresti "Yen giapponese" qui.

#### **Nota importante sugli override:**

Questo modulo utilizza il sistema di override di PrestaShop per modificare il comportamento principale di valuta e lingua. Se hai altri moduli che utilizzano anche override per `Currency.php` o `Language.php`, potrebbero esserci dei conflitti. Testa sempre accuratamente dopo l'installazione.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Seleziona paese | Il tuo paese target | Definisce il paese per cui si applicano le regole. |
| Configurazione modulo | Attiva cambio lingua per visitatore | Abilitato | Attiva il cambio automatico della lingua per il paese selezionato. |
| Configurazione modulo | Seleziona lingua | Lingua ufficiale del paese | Imposta la lingua specifica per i visitatori dal paese scelto. |
| Configurazione modulo | Attiva cambio valuta per visitatore | Abilitato | Attiva il cambio automatico della valuta per il paese selezionato. |
| Configurazione modulo | Seleziona valuta | Valuta ufficiale del paese | Imposta la valuta specifica per i visitatori dal paese scelto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: La lingua/valuta non cambia per i visitatori dal paese selezionato. Cosa devo controllare?**
R:

1.  **Modulo abilitato:** Assicurati che il modulo "Valuta e lingua per paese" sia installato e abilitato in Gestione moduli.
2.  **Configurazione salvata:** Ricontrolla di aver selezionato un paese, abilitato le rispettive opzioni di cambio lingua/valuta, scelto la lingua/valuta corretta e cliccato su "Salva" nella pagina di configurazione del modulo.
3.  **Lingua/Valuta installata e abilitata:** Verifica che la lingua e la valuta target siano installate e abilitate nel tuo Back Office PrestaShop (Internazionale > Lingue e Internazionale > Valute).
4.  **Cache:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) e la cache del tuo browser.
5.  **Accuratezza della geolocalizzazione:** I servizi di geolocalizzazione non sono sempre precisi al 100%. Testa con una VPN per assicurarti che il tuo IP sia correttamente identificato come proveniente dal paese target.

**D: Posso configurare lingue/valute diverse per più paesi?**
R: Il modulo gratuito "Valuta e lingua per paese" ti consente di configurare regole per un solo paese alla volta. Se hai bisogno di un targeting multi-paese avanzato, considera l'aggiornamento al modulo "Geolocation Pro" di MyPresta.eu, che offre funzionalità più estese.

**D: La lingua/valuta predefinita del mio negozio viene ancora visualizzata anche dopo la configurazione.**
R: Questo modulo si rivolge specificamente ai visitatori dal paese *selezionato*. Per tutti gli altri visitatori, si applicheranno la lingua e la valuta predefinite del tuo negozio, o le impostazioni preferite del loro browser se PrestaShop è configurato per rispettarle. Assicurati di testare dal paese esatto che hai configurato.

**D: Ho installato un altro modulo e ora il cambio di lingua/valuta non funziona.**
R: Questo modulo utilizza il sistema di override di PrestaShop. Se un altro modulo sovrascrive anche `classes/Currency.php` o `classes/Language.php`, potrebbe esserci un conflitto. Controlla il tuo `app/config/parameters.php` (per PS 1.7+) o `config/settings.inc.php` (per PS 1.6) per `_PS_MODE_DEV_` e impostalo su `true` per vedere i messaggi di errore. Potrebbe essere necessario contattare il supporto per assistenza nella risoluzione dei conflitti di override.

**D: Come fa il modulo a rilevare il paese del visitatore?**
R: Il modulo utilizza l'indirizzo IP del visitatore per determinare la sua posizione geografica. Questo è un metodo standard per la geolocalizzazione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Valuta e lingua per paese".

### 4.1 Panoramica dell'architettura

Il modulo "Valuta e lingua per paese" (`freegeo`) è un modulo PrestaShop leggero progettato principalmente per modificare la lingua e la valuta predefinite in base all'indirizzo IP di un visitatore. Lo raggiunge sfruttando il sistema di override di PrestaShop per le classi `Currency` e `Language` principali e agganciandosi all'evento `actionDispatcherBefore` per eseguire la logica di geolocalizzazione prima che venga renderizzato il contenuto principale della pagina. La configurazione del modulo è gestita tramite il metodo `getContent()` standard nel file principale del modulo.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller Front-Office o Back-Office personalizzato. La sua logica viene eseguita principalmente tramite hook e override di classe.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo utilizza il sistema di override di PrestaShop per iniettare la sua logica nelle funzionalità principali.

-   **`freegeo/override/classes/Currency.php`**

    -   **Nome classe:** `Currency` (sovrascrive la classe `Currency` principale)
    -   **Classe genitore:** `CurrencyCore`
    -   **Responsabilità:** Questo override è cruciale per impostare la valuta in base alla geolocalizzazione. Modifica il comportamento di come viene determinata la valuta attiva. La logica del modulo all'interno di questo override controllerà se l'impostazione `FREEGEO_CURRENCY_ON` è abilitata e se il paese del visitatore corrisponde al `FREEGEO_COUNTRY` configurato. In tal caso, tenterà di forzare la valuta a `FREEGEO_CURRENCY`.
    -   **Metodi chiave:** L'override probabilmente modifica i metodi relativi a `getCurrent()` o `getCurrency()` per iniettare l'ID della valuta geolocalizzata.
-   **`freegeo/override/classes/Language.php`**

    -   **Nome classe:** `Language` (sovrascrive la classe `Language` principale)
    -   **Classe genitore:** `LanguageCore`
    -   **Responsabilità:** Simile all'override di `Currency`, questa classe è responsabile dell'impostazione della lingua in base alla geolocalizzazione. Controlla `FREEGEO_LANGUAGE_ON` e `FREEGEO_COUNTRY` e, se le condizioni sono soddisfatte, forza la lingua a `FREEGEO_LANGUAGE`.
    -   **Metodi chiave:** L'override probabilmente modifica i metodi relativi a `getCurrentLanguage()` o `getLanguage()` per iniettare l'ID della lingua geolocalizzata.
-   **`freegeo/override/classes/index.php`**

    -   **Scopo:** Questo è un file `index.php` vuoto standard, tipicamente posizionato nelle directory per impedire l'elenco delle directory sui server web, migliorando la sicurezza. Non ha alcun impatto funzionale sulla logica del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. Tutte le sue funzionalità sono gestite lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. La sua funzionalità non implica alcuna specifica stilizzazione del front-office.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`freegeo/views/advert.tpl`**
    -   **Ambito:** Back-office (pagina di configurazione del modulo).
    -   **Scopo:** Questo template è probabilmente utilizzato per visualizzare un annuncio o un messaggio promozionale per il modulo "Geolocation Pro" di MyPresta.eu sulla pagina di configurazione del modulo. Serve come elemento di marketing all'interno dell'interfaccia di amministrazione.
    -   **Hook:** Questo template viene renderizzato all'interno del metodo `getContent()` del file principale del modulo, tipicamente prima o dopo il modulo di configurazione principale.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea alcuna tabella di database personalizzata. Memorizza le sue impostazioni di configurazione direttamente nella tabella `ps_configuration` di PrestaShop.
-   **Record di configurazione in `ps_configuration`**:

    -   `FREEGEO_CURRENCY_ON`: Memorizza un booleano (0 o 1) che indica se il cambio valuta è abilitato.
    -   `FREEGEO_LANGUAGE_ON`: Memorizza un booleano (0 o 1) che indica se il cambio lingua è abilitato.
    -   `FREEGEO_CURRENCY`: Memorizza l'ID della valuta da impostare (es. `id_currency`).
    -   `FREEGEO_LANGUAGE`: Memorizza l'ID della lingua da impostare (es. `id_lang`).
    -   `FREEGEO_COUNTRY`: Memorizza il codice ISO o l'ID del paese da targettizzare.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin imposta le sue risorse multimediali (JS/CSS). | Sebbene elencato, questo modulo probabilmente lo usa minimamente o per il caricamento di script/stili specifici lato admin, se presenti (nessuno rilevato nell'inventario). |
| `actionDispatcherBefore` | Eseguito molto presto nel ciclo di vita della richiesta PrestaShop, prima che il dispatcher elabori l'URL. | **HOOK CRITICO:** Qui risiede la logica di geolocalizzazione principale del modulo. Viene utilizzato per rilevare l'IP del visitatore, determinare il suo paese e quindi, in base alle impostazioni del modulo, potenzialmente sovrascrivere `Context::getContext()->language` e `Context::getContext()->currency` prima che la pagina venga renderizzata. |
| `actionFrontControllerAfterInit` | Eseguito dopo che un Front Controller è stato inizializzato. | Questo hook potrebbe essere utilizzato per eseguire controlli o aggiustamenti aggiuntivi dopo che il controller principale è stato impostato, ma prima del rendering. Potrebbe servire come fallback o punto supplementare per gli aggiustamenti di lingua/valuta se `actionDispatcherBefore` non è sufficiente in tutti gli scenari. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Valuta e lingua per paese", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
