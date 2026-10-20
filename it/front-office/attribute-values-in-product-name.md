---
title: "Valori degli attributi nel nome del prodotto - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Valori degli attributi nel nome del prodotto' di MyPresta.eu."
sidebar:
  label: "Valori degli attributi nel nome del prodotto - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Attribute values in product name su MyPresta.eu](https://mypresta.eu/modules/front-office-features/attribute-values-in-product-name.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/attribute-values-in-product-name/)
>
> ---


# Valori degli attributi nel nome del prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, clicca su "Configura" per accedere alle sue impostazioni.

#### Classe CSS del nome del prodotto

-   **Cosa fa questa impostazione:** Questo campo ti permette di specificare la classe CSS dell'elemento HTML che visualizza il nome del prodotto sulle tue pagine prodotto. Il modulo ha bisogno di conoscere questa classe per poter identificare e modificare correttamente l'elemento del nome del prodotto quando un cliente seleziona una nuova combinazione di attributi.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando viene inserita una classe CSS corretta:* Il modulo individuerà con successo il nome del prodotto sulla pagina e vi aggiungerà dinamicamente i valori degli attributi selezionati.
    *   *Quando viene inserita una classe CSS errata o nessuna classe CSS:* Il modulo non sarà in grado di trovare l'elemento del nome del prodotto e, pertanto, i valori degli attributi non verranno aggiunti al nome del prodotto. Il nome del prodotto rimarrà statico.
-   **Valore consigliato:** Questo valore dipende dal tuo tema PrestaShop.
    *   Per i **temi predefiniti di PrestaShop (Classic)**, una classe comune per il nome del prodotto è `h1.product-detail-name` o `h1[itemprop="name"]`. Potrebbe essere necessario ispezionare la tua pagina prodotto utilizzando gli strumenti per sviluppatori del tuo browser per trovare la classe o l'ID esatto del tag `<h1>` contenente il nome del prodotto.
    *   Se non sei sicuro, prova prima `h1.product-detail-name`. Se non funziona, dovrai consultare lo sviluppatore del tuo tema o utilizzare gli strumenti per sviluppatori del browser (clic destro sul nome del prodotto, seleziona "Ispeziona") per trovare il selettore CSS corretto per l'intestazione principale del nome del prodotto.
-   **Scenario / esempio del commerciante:**
    *   Hai installato un tema personalizzato e il nome del prodotto è racchiuso in un tag `<h2>` con la classe `my-custom-product-title`. In questo campo dovresti inserire `h2.my-custom-product-title`.
    *   Se il tuo tema utilizza la struttura standard del tema PrestaShop Classic, l'inserimento di `h1.product-detail-name` dovrebbe funzionare perfettamente, assicurando che quando un cliente seleziona "Blu" per una maglietta, il titolo si aggiorni da "T-Shirt" a "T-Shirt (Blu)".

#### Altre chiavi di configurazione (Interne)

Potresti vedere altre chiavi di configurazione come `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `mypresta_updates`, `update_`, `updatev_`. Queste sono impostazioni interne utilizzate da PrestaShop e MyPresta.eu per la gestione degli aggiornamenti del modulo e delle preferenze linguistiche. Non è necessario interagire con queste.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Classe CSS del nome del prodotto | `h1.product-detail-name` (per il tema Classic) | Specifica il selettore CSS per l'elemento del nome del prodotto. Essenziale affinché il modulo identifichi e modifichi il titolo del prodotto nella pagina prodotto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il nome del prodotto non cambia quando seleziono gli attributi. Cosa c'è che non va?**
R: La ragione più comune è un'impostazione errata della "Classe CSS del nome del prodotto".
- **Soluzione**:
1.  Vai alla pagina del tuo prodotto nel browser.
2.  Fai clic destro sul nome del prodotto e seleziona "Ispeziona" (o "Ispeziona elemento").
3.  Cerca il tag `<h1>` o `<h2>` che contiene il nome del prodotto. Annota la sua classe (es. `class="product-detail-name"`) o ID (es. `id="product_name"`).
4.  Inserisci il selettore CSS corretto nella configurazione del modulo. Ad esempio, se il tag è `<h1 class="my-product-title">`, dovresti inserire `h1.my-product-title`. Se è `<h2 id="product_heading">`, dovresti inserire `h2#product_heading`.
5.  Salva la configurazione del modulo e svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).

**D: Il modulo ha funzionato inizialmente, ma dopo aver aggiornato il mio tema, ha smesso di funzionare.**
R: Gli aggiornamenti del tema spesso modificano la struttura HTML e le classi CSS.
- **Soluzione**: Ricontrolla l'impostazione "Classe CSS del nome del prodotto" come descritto sopra. Il tuo nuovo tema potrebbe utilizzare una classe o un ID diverso per il nome del prodotto.

**D: Questo modulo influenzerà il mio SEO?**
R: No, questo modulo modifica il nome del prodotto dinamicamente solo lato client (nel browser del cliente) utilizzando JavaScript. Non altera il nome originale del prodotto memorizzato nel tuo database o il tag `<h1>` che i motori di ricerca tipicamente indicizzano. Il tuo SEO rimane inalterato.

**D: Questo modulo supporta più lingue?**
R: Sì, il modulo funziona con i valori degli attributi così come sono configurati nel tuo back office PrestaShop, che sono già compatibili con più lingue. Il modulo semplicemente aggiunge i valori degli attributi attualmente selezionati nella lingua attiva al nome del prodotto.

**D: Vedo i valori degli attributi, ma sono stilizzati in modo errato (es. font, colore sbagliati).**
R: Il modulo aggiunge testo a un elemento HTML esistente. La sua stilizzazione erediterà dal CSS del tuo tema per quell'elemento del nome del prodotto.
- **Soluzione**: Se desideri stilizzare i valori degli attributi aggiunti in modo diverso, avrai bisogno di CSS personalizzato. Puoi mirare all'elemento del nome del prodotto e potenzialmente utilizzare pseudo-elementi o selettori specifici se il modulo racchiude il testo aggiunto in uno span unico (anche se questo modulo tipicamente aggiunge solo testo). Uno sviluppatore web può aiutarti con il CSS personalizzato.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori, webmaster e agenzie.

### 4.1 Panoramica dell'architettura

Il modulo "Valori degli attributi nel nome del prodotto" (`anpn`) è un modulo PrestaShop leggero, focalizzato principalmente sulla manipolazione lato client del front-office. Sfrutta il sistema di hook di PrestaShop per iniettare il suo JavaScript nell'intestazione della pagina prodotto. La logica principale risiede in un singolo file JavaScript che ascolta i cambiamenti nelle selezioni degli attributi del prodotto e aggiorna dinamicamente il contenuto testuale del nome del prodotto. Non introduce nuove tabelle di database o logica complessa lato server oltre alla sua configurazione.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Tutte le funzionalità del front-office sono gestite tramite JavaScript iniettato tramite hook.
-   **Controller Admin Back-Office**: Nessuno. La configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Non sono definite classi personalizzate o istanze di `ObjectModel`. Il modulo opera direttamente sui valori di configurazione e sulla manipolazione del DOM del front-office.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`anpn/views/js/anpn.js`**
    *   **Ambito**: Front-office (pagina prodotto).
    *   **Scopo**: Questo script è responsabile dell'aggiornamento dinamico del nome del prodotto.
    *   **Funzionalità**:
        1.  **DOM Ready / `prestashop.on`**: Attende che il DOM sia completamente caricato e ascolta specificamente l'evento `updatedProduct` attivato dal JavaScript principale di PrestaShop quando una combinazione di prodotto viene modificata (ad esempio, selezionando una taglia o un colore diverso).
        2.  **Identificazione del nome del prodotto**: Recupera il selettore CSS per il nome del prodotto dalla configurazione del modulo (passato tramite la variabile globale `anpn_pn_class` o un meccanismo simile). Utilizza quindi questo selettore per trovare l'elemento HTML di destinazione sulla pagina.
        3.  **Estrazione del valore dell'attributo**: Quando `updatedProduct` viene attivato, accede ai dati della combinazione di prodotto corrente (che include i valori degli attributi selezionati) dal payload dell'evento.
        4.  **Aggiornamento dinamico**: Costruisce una stringa dei valori degli attributi selezionati (ad esempio, "(M, Blu)") e la aggiunge al nome originale del prodotto (che tipicamente memorizza al caricamento iniziale o recupera da un attributo dati).
        5.  **Manipolazione del DOM**: Lo script aggiorna il `textContent` o `innerText` dell'elemento del nome del prodotto identificato con la nuova stringa combinata.
    *   **Dipendenze**: Si basa su jQuery (se PrestaShop 1.7.x) o API DOM native, e sul sistema di eventi `prestashop.on` di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessun file CSS personalizzato è fornito dal modulo. I valori degli attributi aggiunti ereditano lo stile dell'elemento del nome del prodotto esistente nel tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   Nessun file di template personalizzato è fornito dal modulo. Tutto l'output è gestito dal file principale del modulo (`anpn.php`) per la configurazione e da JavaScript per la visualizzazione nel front-office.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Il modulo non crea tabelle di database personalizzate.
    *   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration`:
        *   `ANPN_PN_CLASS`: Memorizza la classe/selettore CSS per l'elemento del nome del prodotto.
-   **Tabella degli hook registrati**:

  | Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
  | --- | --- | --- |
  | `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per registrare il JavaScript del modulo (`anpn.js`) e passare il valore di configurazione `ANPN_PN_CLASS` allo script del front-end. |
  | `displayProductAdditionalInfo` | Nella pagina del prodotto, tipicamente sotto le informazioni principali del prodotto. | Sebbene non esplicitamente utilizzato per l'output visivo in questo modulo, è un hook comune per i moduli per iniettare contenuti o script nella pagina del prodotto. Nel contesto di questo modulo, potrebbe essere utilizzato per garantire che il JS sia caricato al momento giusto, oppure potrebbe essere una registrazione di hook legacy. L'interazione principale avviene tramite `displayHeader` e l'evento `updatedProduct`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Valori degli attributi nel nome del prodotto", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
"""
