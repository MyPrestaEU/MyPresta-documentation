---
title: "Pagine CMS solo per utenti loggati - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Pagine CMS solo per utenti loggati' di MyPresta.eu."
sidebar:
  label: "Pagine CMS solo per utenti loggati - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo CMS pages for logged only su MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-logged-only.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/cms-pages-for-logged-only/)
>
> ---


# Pagine CMS solo per utenti loggati

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Pagine CMS solo per utenti loggati". Vedrai una singola schermata di configurazione.

![Esempio di schermata di configurazione del modulo Pagine CMS solo per utenti loggati](https://mypresta.eu/images/art/cms-pages-for-logged-only-configuration.png)

Questa schermata presenta un elenco di tutte le tue pagine CMS esistenti. Per ogni pagina, vedrai un semplice interruttore per abilitare o disabilitare la restrizione "solo per utenti loggati".

-   **Nome impostazione:** `cmsp` (Questo è l'identificatore interno, vedrai i titoli effettivi delle pagine CMS).
-   **Cosa fa questa impostazione:** Questa impostazione ti consente di selezionare quali specifiche pagine CMS saranno limitate solo ai clienti che hanno effettuato l'accesso. Ogni riga rappresenta una delle pagine CMS del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (l'interruttore è ON/verde):* La pagina CMS selezionata sarà accessibile solo ai clienti che hanno effettuato l'accesso ai loro account. Se un cliente non loggato tenta di visitare questa pagina, verrà reindirizzato alla pagina di accesso. Dopo un accesso riuscito, verrà reindirizzato a questa specifica pagina CMS.
    -   *Quando disabilitato (l'interruttore è OFF/rosso):* La pagina CMS selezionata sarà pubblicamente accessibile a tutti i visitatori, che siano loggati o meno. Questo è il comportamento predefinito per tutte le pagine CMS in PrestaShop.
-   **Valore consigliato:** Questo dipende interamente dalle tue esigenze aziendali. Abilitalo per qualsiasi pagina CMS che contenga informazioni sensibili, esclusive o riservate ai membri.
-   **Scenario / esempio per il commerciante:**
    -   Hai una pagina CMS "Termini e Condizioni all'ingrosso". Abiliteresti l'interruttore accanto a questa pagina in modo che solo i tuoi clienti all'ingrosso registrati possano visualizzarla.
    -   Crei una pagina CMS "Guida ai contenuti Premium" per i clienti fedeli. Abiliteresti l'interruttore per questa pagina per incoraggiare la registrazione e premiare i clienti esistenti.
    -   Hai una pagina standard "Chi siamo". Lasceresti l'interruttore disabilitato, poiché questa pagina dovrebbe essere visibile pubblicamente a tutti i visitatori.

Dopo aver effettuato le tue selezioni, ricorda di cliccare sul pulsante **"Salva"** in fondo alla pagina per applicare le modifiche.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Interruttori individuali per pagine CMS | Disabilitato (OFF) | Controlla se una specifica pagina CMS richiede che un cliente sia loggato per visualizzarla. L'abilitazione reindirizza gli utenti non loggati alla pagina di accesso, quindi di nuovo alla pagina CMS dopo un accesso riuscito. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato la restrizione per una pagina CMS, ma gli utenti non loggati possono ancora vederla. Cosa c'è che non va?**
R:

1.  **Svuota la cache:** La ragione più comune è la cache. Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache Smarty" nelle versioni precedenti). Potrebbe essere necessario svuotare anche la cache del tuo browser.
2.  **Salva la configurazione:** Assicurati di aver cliccato sul pulsante "Salva" nella pagina di configurazione del modulo dopo aver abilitato la restrizione per la specifica pagina CMS.
3.  **Controlla l'URL della pagina CMS:** Ricontrolla di stare testando l'URL corretto per la pagina CMS che hai limitato.

**D: Dopo aver effettuato l'accesso, il cliente viene reindirizzato alla homepage invece che alla pagina CMS con restrizioni. Perché?**
R: Questo modulo è progettato per reindirizzare il cliente alla pagina CMS originale con restrizioni dopo un accesso riuscito. Se ciò non avviene, potrebbe essere dovuto a:

1.  **Reindirizzamenti di accesso personalizzati:** Un altro modulo o una modifica personalizzata del tema potrebbe sovrascrivere il comportamento di reindirizzamento di accesso predefinito di PrestaShop. Disabilita temporaneamente altri moduli che influenzano l'accesso/reindirizzamento per testare.
2.  **Specifiche della versione di PrestaShop:** Sebbene il modulo sia compatibile con molte versioni, override molto specifici del tema o del core in versioni PrestaShop più vecchie/nuove potrebbero interferire. Assicurati che i file core di PrestaShop siano standard.

**D: Posso limitare categorie o prodotti invece delle pagine CMS?**
R: No, questo modulo è specificamente progettato solo per le pagine CMS. Non fornisce funzionalità per limitare categorie, prodotti o altri tipi di contenuto. Avresti bisogno di un modulo diverso per tali scopi.

**D: Questo modulo influisce sulla SEO?**
R: Quando una pagina è limitata, i crawler dei motori di ricerca (come Googlebot) verranno tipicamente reindirizzati alla pagina di accesso, proprio come un utente umano. Ciò significa che il contenuto della pagina CMS limitata non verrà indicizzato dai motori di ricerca. Se il contenuto deve essere pubblico e indicizzato, non limitarlo con questo modulo. Per i contenuti che dovrebbero essere nascosti ai motori di ricerca ma comunque accessibili agli utenti loggati, questo comportamento è desiderato.

**D: Come traduco il testo del modulo (se presente)?**
R: Questo modulo ha pochissimo testo nel front-office, poiché gestisce principalmente il reindirizzamento. Eventuali messaggi relativi all'accesso sono gestiti dalla pagina di autenticazione principale di PrestaShop. Se ci fossero testi specifici del modulo, li tradurresti tramite **Internazionale > Traduzioni** nel tuo Back Office. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi trova "Pagine CMS solo per utenti loggati" nell'elenco.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Pagine CMS solo per utenti loggati" (`privatecms`) opera principalmente sovrascrivendo il `CmsController` principale per intercettare le richieste di pagine CMS. Controlla se una pagina CMS richiesta è configurata per l'accesso "solo per utenti loggati" e, se l'utente non ha effettuato l'accesso, attiva un reindirizzamento alla pagina di autenticazione. Dopo un accesso riuscito, il meccanismo di reindirizzamento predefinito di PrestaShop (che il modulo sfrutta) rimanda l'utente alla pagina originariamente richiesta. La configurazione è gestita tramite un metodo `getContent()` standard nel file principale del modulo, memorizzando le impostazioni in `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `override/controllers/front/CmsController.php`
        -   **Nome classe:** `CmsController` (sovrascrive il `CmsController` principale di PrestaShop)
        -   **Classe genitore:** `CmsControllerCore`
        -   **Responsabilità:** Questa sovrascrittura è il cuore della funzionalità del modulo. Intercetta il metodo `init()` del `CmsController`. Prima che la pagina CMS venga renderizzata, controlla se l'ID della pagina CMS corrente (`$this->cms->id`) è presente nell'elenco delle pagine con restrizioni memorizzate nella configurazione del modulo. Se la pagina è con restrizioni e il cliente non ha effettuato l'accesso (`$this->context->customer->isLogged()`), reindirizza l'utente alla pagina di autenticazione (`$this->context->link->getPageLink('authentication')`). Include anche un parametro `back` nell'URL di reindirizzamento, garantendo che PrestaShop reindirizzi l'utente alla pagina CMS originale dopo un accesso riuscito.
-   **Controller di amministrazione Back-Office**: Nessuno. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

Nessuno. Il modulo non definisce classi personalizzate o entità `ObjectModel`. Interagisce direttamente con le classi principali esistenti di PrestaShop come `Configuration`, `Cms`, `Customer` e `Link`.

### 4.4 Risorse JavaScript (`views/js/`)

Nessuno. Il modulo non include file JavaScript personalizzati. La sua funzionalità è puramente lato server (basata su PHP per il reindirizzamento).

### 4.5 Fogli di stile CSS (`views/css/`)

-   `privatecms/css.css`
    -   **Ambito:** Stile del modulo di amministrazione del Back-Office.
    -   **Principali componenti UI e contenitori che stilizza:** Questo foglio di stile contiene probabilmente uno stile minimo per il modulo di configurazione del modulo nel Back Office di PrestaShop, garantendo che il layout e gli elementi (come l'elenco delle pagine CMS e gli interruttori) siano visualizzati correttamente e in modo coerente con il tema di amministrazione di PrestaShop.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** I selettori specifici si troverebbero all'interno del file, tipicamente mirati agli elementi all'interno del template `admin.tpl`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template di amministrazione (`views/templates/admin/`)**:
    -   `privatecms/admin.tpl`
        -   **Scopo:** Questo template viene renderizzato dal metodo `getContent()` del file principale del modulo (`privatecms.php`). Visualizza l'elenco di tutte le pagine CMS disponibili nel Back Office, insieme a un interruttore per ogni pagina, consentendo all'amministratore di abilitare o disabilitare la restrizione "solo per utenti loggati". Itera attraverso le pagine CMS e visualizza i loro titoli e lo stato attuale della restrizione (selezionato/deselezionato).

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   La configurazione è memorizzata nella tabella `ps_configuration` (o prefisso `_configuration`).
        -   **Chiave:** `cmsp`
        -   **Valore:** Un array serializzato (o stringa JSON, a seconda della versione di PrestaShop e dell'implementazione del modulo) contenente gli ID delle pagine CMS selezionate per l'accesso "solo per utenti loggati".
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente alcun hook standard di PrestaShop nel suo metodo `install()`. La sua funzionalità principale si basa sulla sovrascrittura del `CmsController`, che è un modo più diretto per intercettare le richieste di pagine CMS.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `override/controllers/front/CmsController.php` | Durante l'inizializzazione di `CmsController` | Intercetta le richieste di pagine CMS per controllare lo stato di accesso e reindirizzare se necessario. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Pagine CMS solo per utenti loggati", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
