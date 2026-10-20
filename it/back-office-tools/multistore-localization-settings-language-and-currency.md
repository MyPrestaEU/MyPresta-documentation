---
title: "Impostazioni di localizzazione Multistore - lingua e valuta - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Impostazioni di localizzazione Multistore - lingua e valuta' di MyPresta.eu."
sidebar:
  label: "Impostazioni di localizzazione Multistore - lingua e valuta - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Multistore localization settings - language and currency su MyPresta.eu](https://mypresta.eu/modules/administration-tools/multistore-localization-settings-language-and-currency.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/multistore-localization-settings-language-and-currency/)
>
> ---


# Impostazioni di localizzazione Multistore - lingua e valuta

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Il tuo ambiente di hosting deve supportare la funzionalità Multistore di PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Questo modulo introduce una nuova voce di menu nel tuo Back Office di PrestaShop per gestire le regole di localizzazione per ciascuno dei tuoi negozi.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Quando clicchi per la prima volta su "Configura" dopo l'installazione, atterrerai su una pagina di configurazione di base. Questa pagina serve principalmente come punto di ingresso all'interfaccia di gestione principale.

- **Cosa fa questa impostazione:** Questa schermata conterrà probabilmente un semplice messaggio o un pulsante che ti indirizza all'area di gestione dedicata per le regole di localizzazione Multistore. Potrebbe anche includere informazioni sulla versione del modulo o un link al supporto.
- **Effetto della modifica di questa impostazione:** Cliccando su qualsiasi pulsante o link qui, navigherai all'interfaccia principale dove definisci le tue regole di lingua e valuta specifiche per il negozio.
- **Valore consigliato:** Segui le istruzioni sullo schermo, di solito cliccando un pulsante per procedere alla configurazione principale.
- **Scenario / esempio del commerciante:** Dopo l'installazione, vedrai un messaggio come "Clicca qui per gestire le tue regole di localizzazione Multistore". Cliccherai su questo per accedere alla funzionalità principale.

### 2.2 Schermata di amministrazione dedicata: Regole di localizzazione Multistore (Back Office > Regole di localizzazione Multistore)

Questo è il pannello di controllo principale per il modulo. Troverai questa nuova voce di menu sotto **Parametri negozio > Regole di localizzazione Multistore** (o simile, a seconda della tua versione di PrestaShop e della struttura del menu).

Entrando in questa schermata, vedrai un elenco (griglia) dei tuoi negozi esistenti. Per ogni negozio, potrai definire le sue impostazioni specifiche di lingua e valuta.

**Azioni e impostazioni disponibili:**

1. **Elenco negozi / Vista a griglia:**

   - **Scopo:** Questa tabella visualizza tutti i negozi che hai configurato nella tua configurazione Multistore di PrestaShop.
   - **Colonne:** Tipicamente vedrai colonne come "Nome negozio" e potenzialmente "Azioni" o "Configura".
   - **Effetto delle modifiche:** Questa vista ti consente di vedere rapidamente quali negozi sono configurati e fornisce il punto di ingresso per modificare le loro impostazioni di localizzazione.
2. **Pulsante Modifica/Configura per ogni negozio:**

   - **Cosa fa questo pulsante:** Cliccando questo pulsante (spesso un'icona a matita) accanto al nome di un negozio si aprirà un modulo di configurazione dettagliato specificamente per quel negozio.
   - **Effetto della modifica di questa impostazione:** Qui è dove definisci le lingue e le valute specifiche per il negozio selezionato.

**All'interno del modulo di configurazione specifico del negozio:**

Quando clicchi per modificare un negozio, vedrai due sezioni principali: **Lingue** e **Valute**.

#### 2.2.1 Configurazione lingue per [Nome negozio]

- **Elenco lingue disponibili:**

  - **Cosa fa questa impostazione:** Questa sezione presenta un elenco di tutte le lingue installate nel tuo negozio PrestaShop. Per ogni lingua, vedrai tipicamente una casella di controllo.
  - **Effetto della modifica di questa impostazione:**
    - *Se selezionata:* La lingua sarà disponibile per la selezione da parte dei clienti nel front office di questo negozio specifico.
    - *Se deselezionata:* La lingua NON verrà mostrata nel selettore di lingua per questo negozio e i clienti non potranno passarci.
  - **Valore consigliato:** Seleziona solo le lingue pertinenti al pubblico di destinazione di questo negozio specifico.
  - **Scenario / esempio del commerciante:** Per il tuo "Negozio francese", selezioneresti "Français (Francese)" e deselezioneresti tutte le altre lingue.
- **Lingua predefinita per [Nome negozio]:**

  - **Cosa fa questa impostazione:** Una selezione a discesa o a pulsante radio che ti consente di scegliere una delle lingue *abilitate* come predefinita per questo negozio.
  - **Effetto della modifica di questa impostazione:** Quando un cliente visita per la prima volta questo negozio, si caricherà automaticamente nella lingua predefinita selezionata. Se il cliente ha precedentemente selezionato una lingua, la sua preferenza potrebbe essere ricordata, ma per i nuovi visitatori, si applica questa impostazione predefinita.
  - **Valore consigliato:** Imposta la lingua principale per il pubblico di destinazione del negozio.
  - **Scenario / esempio del commerciante:** Per il tuo "Negozio francese", imposteresti "Français (Francese)" come lingua predefinita.

#### 2.2.2 Configurazione valute per [Nome negozio]

- **Elenco valute disponibili:**

  - **Cosa fa questa impostazione:** Questa sezione presenta un elenco di tutte le valute installate nel tuo negozio PrestaShop. Per ogni valuta, vedrai tipicamente una casella di controllo.
  - **Effetto della modifica di questa impostazione:**
    - *Se selezionata:* La valuta sarà disponibile per la selezione da parte dei clienti nel front office di questo negozio specifico. I prezzi verranno visualizzati in questa valuta se selezionata.
    - *Se deselezionata:* La valuta NON verrà mostrata nel selettore di valuta per questo negozio e i clienti non potranno visualizzare i prezzi in essa.
  - **Valore consigliato:** Seleziona solo le valute pertinenti al pubblico di destinazione di questo negozio specifico.
  - **Scenario / esempio del commerciante:** Per il tuo "Negozio USA", selezioneresti "Dollaro USA ($)" e deselezioneresti "Euro (€)" e altre valute.
- **Valuta predefinita per [Nome negozio]:**

  - **Cosa fa questa impostazione:** Una selezione a discesa o a pulsante radio che ti consente di scegliere una delle valute *abilitate* come predefinita per questo negozio.
  - **Effetto della modifica di questa impostazione:** Quando un cliente visita per la prima volta questo negozio, tutti i prezzi verranno automaticamente visualizzati nella valuta predefinita selezionata.
  - **Valore consigliato:** Imposta la valuta principale per il pubblico di destinazione del negozio.
  - **Scenario / esempio del commerciante:** Per il tuo "Negozio USA", imposteresti "Dollaro USA ($)" come valuta predefinita.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1. Naviga su **Parametri negozio > Regole di localizzazione Multistore**.
2. Identifica il negozio che desideri configurare dall'elenco.
3. Clicca sul pulsante "Modifica" o "Configura" accanto a quel negozio.
4. Nella sezione "Lingue", seleziona tutte le lingue che desideri siano disponibili per questo negozio specifico.
5. Seleziona una delle lingue *selezionate* come "Lingua predefinita" per questo negozio.
6. Nella sezione "Valute", seleziona tutte le valute che desideri siano disponibili per questo negozio specifico.
7. Seleziona una delle valute *selezionate* come "Valuta predefinita" per questo negozio.
8. Clicca su "Salva" per applicare le modifiche.
9. Ripeti per tutti gli altri negozi nella tua configurazione Multistore.
10. **Svuota sempre la cache di PrestaShop** (Parametri avanzati > Prestazioni) dopo aver apportato modifiche per assicurarti che vengano immediatamente riflesse nel front office.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Regole di localizzazione Multistore (Vista elenco)** | Pulsante Modifica/Configura | N/A | Accedi alle impostazioni dettagliate di lingua/valuta per un negozio specifico. |
| **Configurazione specifica del negozio (Lingue)** | Lingue disponibili (checkbox) | Seleziona quelle pertinenti | Controlla quali lingue appaiono nel selettore del front office per questo negozio. |
| **Configurazione specifica del negozio (Lingue)** | Lingua predefinita | Lingua principale per il pubblico del negozio | Imposta la lingua iniziale per i nuovi visitatori di questo negozio. |
| **Configurazione specifica del negozio (Valute)** | Valute disponibili (checkbox) | Seleziona quelle pertinenti | Controlla quali valute appaiono nel selettore del front office per questo negozio. |
| **Configurazione specifica del negozio (Valute)** | Valuta predefinita | Valuta principale per il pubblico del negozio | Imposta la valuta iniziale per i nuovi visitatori di questo negozio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato le lingue/valute, ma non cambiano nel mio front office.**
R: La ragione più comune è la cache. Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota cache" (o "Svuota cache Smarty" e "Svuota cache" per tutte le cache). Prova anche a svuotare la cache del tuo browser.

**D: Il mio tema personalizzato non sembra rispettare le impostazioni del modulo per i selettori di lingua/valuta.**
R: Questo modulo controlla *quali* opzioni sono disponibili, ma il tuo tema detta *come* tali opzioni vengono visualizzate. Se il tuo tema ha selettori di lingua/valuta pesantemente personalizzati, potrebbe sovrascrivere il comportamento standard di PrestaShop.
\* **Soluzione:** Controlla la documentazione del tuo tema o contatta lo sviluppatore del tuo tema. Potrebbe essere necessario apportare piccole modifiche ai file `.tpl` del tuo tema per assicurarti che stiano utilizzando le variabili `languages` e `currencies` standard di PrestaShop, che questo modulo modifica.

**D: Posso impostare lingue/valute predefinite diverse per diversi gruppi di clienti?**
R: No, questo modulo imposta la lingua e la valuta predefinite *per negozio*, non per gruppo di clienti. L'impostazione predefinita si applica a tutti i visitatori di quel negozio specifico. I clienti possono quindi modificarla manualmente se sono disponibili altre opzioni.

**D: Cosa succede se disabilito una lingua/valuta che è attualmente impostata come predefinita per un negozio?**
R: Il modulo dovrebbe impedirti di farlo o tornare automaticamente alla lingua/valuta disponibile successiva. Assicurati sempre che la tua scelta predefinita sia una delle opzioni *abilitate* per quel negozio. Se riscontri problemi, riabilita un'impostazione predefinita adatta e svuota la cache.

**D: Ho solo un negozio. Ho bisogno di questo modulo?**
R: No, questo modulo è progettato specificamente per la funzionalità Multistore di PrestaShop. Se hai un solo negozio, le impostazioni di localizzazione predefinite di PrestaShop (sotto Internazionale > Localizzazione) sono sufficienti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita dell'implementazione tecnica del modulo "Impostazioni di localizzazione Multistore - lingua e valuta" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo estende principalmente il comportamento di localizzazione principale di PrestaShop sovrascrivendo le classi `Currency` e `Language`. Introduce un controller di amministrazione personalizzato (`AdminMultirulesController`) per gestire le regole di localizzazione specifiche del negozio, che vengono archiviate in una tabella di database personalizzata. Il modulo sfrutta il modello MVC di PrestaShop per la sua interfaccia di Back Office e utilizza override per iniettare la sua logica nel processo di selezione della lingua e della valuta del front office.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Questo modulo non include alcun controller front-office dedicato. La sua logica front-office viene iniettata tramite override di classe e hook.
- **Controller Admin Back-Office**:

  - `multishoplang/controllers/admin/AdminMultirules.php`
    - **Nome classe e classe genitore**: `AdminMultirulesController` estende `ModuleAdminController`.
    - **Responsabilità**: Questo controller gestisce l'elenco e la modifica delle regole di localizzazione per ogni negozio. È responsabile della visualizzazione della griglia dei negozi, della gestione del modulo per la selezione delle lingue e delle valute disponibili per un negozio specifico e del salvataggio di queste impostazioni nel database. Probabilmente utilizza `HelperList` per la griglia dei negozi e `HelperForm` per la configurazione specifica del negozio.
    - **Nome scheda**: "Regole di localizzazione Multistore" (o simile, definito nel metodo `installTab()`).
  - `multishoplang/controllers/admin/index.php`
    - **Nome classe e classe genitore**: Questo è tipicamente un file vuoto o un file contenente un'istruzione di sicurezza `die()` per impedire l'accesso diretto alla directory. Non rappresenta un controller attivo.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo si basa fortemente sugli override per modificare il comportamento principale di PrestaShop.

- `multishoplang/override/classes/Currency.php`
  - **Nome classe e classe genitore**: `Currency` (sovrascrive la classe `Currency` principale di PrestaShop).
  - **Responsabilità**: Questo override intercetta le chiamate relative al recupero e alla selezione della valuta. Modifica metodi come `getCurrencies()` o `getDefaultCurrency()` per filtrare l'elenco delle valute disponibili in base alla configurazione del negozio corrente come definita dal modulo. Garantisce che solo le valute abilitate per il negozio attivo siano presentate nel front office.
- `multishoplang/override/classes/Language.php`
  - **Nome classe e classe genitore**: `Language` (sovrascrive la classe `Language` principale di PrestaShop).
  - **Responsabilità**: Simile all'override di `Currency`, questa classe intercetta le chiamate relative alla lingua. Modifica metodi come `getLanguages()` o `getDefaultLanguage()` per filtrare l'elenco delle lingue disponibili in base alla configurazione del negozio corrente. Garantisce che solo le lingue abilitate per il negozio attivo siano presentate nel front office.
- `multishoplang/override/classes/index.php`
  - **Nome classe e classe genitore**: Questo è tipicamente un file vuoto o un file contenente un'istruzione di sicurezza `die()` per impedire l'accesso diretto alla directory. Non rappresenta una classe attiva.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non include alcun file JavaScript personalizzato. Tutte le interazioni nel Back Office sono gestite dal JavaScript standard di `HelperForm` e `HelperList` di PrestaShop, e il comportamento del front office è gestito dagli override di classe.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato. La sua interfaccia di Back Office si basa sullo stile del tema di amministrazione predefinito di PrestaShop. La visualizzazione del front office è controllata dal tema attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, ma la logica del modulo opera principalmente tramite override di classe piuttosto che tramite template hook diretti.
- **Template admin (`views/templates/admin/`)**:
  - `multishoplang/views/advert.tpl`
    - **Scopo**: Probabilmente un template per visualizzare messaggi promozionali o informazioni su altri moduli MyPresta.eu all'interno dell'interfaccia di configurazione del modulo.
  - `multishoplang/views/currenciesForm.tpl`
    - **Scopo**: Questo template viene utilizzato all'interno di `AdminMultirulesController` per renderizzare la sezione del modulo per la configurazione delle valute disponibili e della valuta predefinita per un negozio specifico. Conterrà checkbox per le valute e un menu a discesa per la predefinita.
  - `multishoplang/views/languagesForm.tpl`
    - **Scopo**: Questo template viene utilizzato all'interno di `AdminMultirulesController` per renderizzare la sezione del modulo per la configurazione delle lingue disponibili e della lingua predefinita per un negozio specifico. Conterrà checkbox per le lingue e un menu a discesa per la predefinita.
- **Template front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - `ps_multirule`: Questa è la tabella personalizzata creata dal modulo per archiviare le regole di localizzazione. Probabilmente contiene campi come:
    - `id_shop`: Chiave esterna che fa riferimento a `ps_shop.id_shop`.
    - `id_lang_default`: L'ID della lingua predefinita per quel negozio.
    - `id_currency_default`: L'ID della valuta predefinita per quel negozio.
    - `available_languages`: Un array serializzato o una stringa separata da virgole di valori `id_lang` abilitati per il negozio.
    - `available_currencies`: Un array serializzato o una stringa separata da virgole di valori `id_currency` abilitati per il negozio.
  - I record di configurazione sono archiviati in `ps_configuration` per le impostazioni generali del modulo (se presenti).
- **Tabella degli hook registrati**:
  Il modulo opera principalmente tramite override di classe piuttosto che tramite l'esecuzione diretta di hook nel front office. Tuttavia, registrerà hook standard del Back Office per la sua interfaccia di amministrazione.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Quando viene caricato un controller admin | Per caricare CSS/JS specifici del modulo (anche se nessuno è presente in questo modulo). |
| `displayBackOfficeHeader` | Nell'intestazione del Back Office | Potenzialmente per visualizzare avvisi o notifiche specifiche del modulo. |
| `moduleRoutes` | Durante l'inizializzazione del routing URL | Se il modulo ha definito route front-office personalizzate (non applicabile qui). |
| `actionObjectLanguageAddAfter` | Dopo l'aggiunta di una nuova lingua | Per aggiornare potenzialmente i dati interni del modulo per le nuove lingue. |
| `actionObjectCurrencyAddAfter` | Dopo l'aggiunta di una nuova valuta | Per aggiornare potenzialmente i dati interni del modulo per le nuove valute. |
| `actionShopDataDuplication` | Quando un negozio viene duplicato | Per garantire che le regole di localizzazione vengano copiate per il nuovo negozio. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire il buon funzionamento e il continuo miglioramento dei vostri moduli PrestaShop.
