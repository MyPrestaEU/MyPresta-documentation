---
title: "Integrazione Shopmania - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Integrazione Shopmania di MyPresta.eu."
sidebar:
  label: "Integrazione Shopmania"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Shopmania Integration su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/shopmania-integration.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/shopmania-integration/)
>
> ---


# Integrazione Shopmania

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il funzionamento generale di PrestaShop, ma questo modulo ha requisiti specifici minimi oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)
Dopo l'installazione, clicca su "Configura" accanto al modulo "Integrazione Shopmania" nel tuo Gestione moduli. Questo ti porterà alla pagina di configurazione principale.

Il modulo Integrazione Shopmania è progettato per essere molto semplice, spesso richiedendo una configurazione minima poiché si concentra principalmente sulla generazione di un feed di prodotti.

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|
| **URL Feed ShopMania** | Generato automaticamente | Questo è il link diretto al feed di prodotti generato dal tuo modulo. Dovrai copiare questo URL e fornirlo a ShopMania quando configuri il tuo account commerciante con loro. Questo URL è ciò che ShopMania utilizzerà per recuperare regolarmente i dati dei tuoi prodotti. |

**Cosa fa questa impostazione:**
Questa sezione visualizza l'URL che ShopMania utilizzerà per accedere al tuo feed di dati dei prodotti. Questo feed contiene tutte le informazioni necessarie sui tuoi prodotti (nome, descrizione, prezzo, immagini, disponibilità, ecc.) in un formato che ShopMania può comprendere e visualizzare sulla propria piattaforma.

**Effetto della modifica di questa impostazione:**
Non puoi modificare direttamente questo URL. Viene generato automaticamente dal modulo in base al dominio del tuo negozio e alla logica interna del modulo.

**Valore consigliato:**
Copia questo URL esattamente come appare. Non modificarlo.

**Scenario / esempio per il commerciante:**
Dopo aver installato e configurato il modulo, accederai al tuo account commerciante ShopMania (o ne creerai uno). ShopMania ti chiederà l'"URL del Feed di Prodotti" o "URL del Feed di Dati". Dovrai quindi incollare l'URL fornito in questa pagina di configurazione nel campo corrispondente sul sito web di ShopMania. ShopMania visiterà quindi periodicamente questo URL per aggiornare i tuoi annunci di prodotti sulla loro piattaforma.

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D: I miei prodotti non appaiono su ShopMania. Cosa devo fare?**
R:
1.  **Controlla l'URL del Feed:** Assicurati di aver copiato e incollato correttamente l'URL esatto del feed dalla pagina di configurazione del modulo nelle impostazioni del tuo account commerciante ShopMania.
2.  **Tempo di Elaborazione di ShopMania:** Potrebbe volerci del tempo (da ore a qualche giorno) affinché ShopMania elabori il tuo feed per la prima volta. Sii paziente.
3.  **Accessibilità del Feed:** Prova ad aprire l'URL del feed nel tuo browser web. Si carica? Mostra i dati del prodotto? Se mostra un errore o una pagina vuota, potrebbe esserci un problema lato server o un problema con il processo di generazione del modulo. Contatta il supporto MyPresta.eu.
4.  **Visibilità del Prodotto:** Assicurati che i tuoi prodotti siano attivi, in stock e visibili nel tuo negozio PrestaShop. I prodotti disabilitati o esauriti potrebbero non essere inclusi nel feed.

**D: Questo modulo aggiorna automaticamente prezzi e stock su ShopMania?**
R: Sì, il feed generato da questo modulo rifletterà i prezzi e i livelli di stock attuali dal tuo negozio PrestaShop. ShopMania recupererà periodicamente questo feed per mantenere aggiornati i propri elenchi. La frequenza degli aggiornamenti dipende dal programma di recupero di ShopMania, che potresti essere in grado di configurare nel tuo account commerciante ShopMania.

**D: Posso scegliere quali prodotti includere nel feed?**
R: La versione base di questo modulo include tipicamente tutti i prodotti attivi e visibili. Se hai bisogno di un filtraggio avanzato (ad esempio, escludere categorie o prodotti specifici), ciò richiederebbe uno sviluppo personalizzato o un modulo di gestione del feed più avanzato. Il modulo "Integrazione Shopmania" si concentra su un'integrazione semplice e completa del catalogo.

**D: Vedo un errore quando cerco di configurare il modulo.**
R:
1.  **Svuota la Cache:** Vai su **Parametri Avanzati > Prestazioni** nel back office del tuo PrestaShop e clicca su "Svuota la cache". A volte, i vecchi file di cache possono interferire con la configurazione del modulo.
2.  **Controlla i Log degli Errori del Server:** Se il problema persiste, controlla i log degli errori PHP del tuo server. Questi log possono fornire dettagli tecnici specifici su cosa è andato storto. Potrebbe essere necessario contattare il tuo provider di hosting o uno sviluppatore per questo.
3.  **Contatta il Supporto:** Se stai ancora riscontrando problemi, raccogli eventuali messaggi di errore o screenshot e contatta il supporto MyPresta.eu per assistenza.

**D: E se il mio tema personalizzato causa problemi di visualizzazione (anche se questo modulo non ha visualizzazione front-office)?**
R: Poiché questo modulo non ha visualizzazione front-office, è altamente improbabile che causi problemi visivi con il tuo tema personalizzato. La sua operazione è puramente backend, generando un file di dati.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)
Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'Architettura
Il modulo `Integrazione Shopmania` è un modulo PrestaShop semplice, a file singolo, progettato per generare un feed di prodotti XML compatibile con la piattaforma ShopMania. Segue una struttura standard dei moduli PrestaShop, utilizzando principalmente i metodi `install()` e `uninstall()` per la configurazione e il metodo `getContent()` per la sua configurazione nel back-office, che in questo caso, visualizza semplicemente l'URL del feed generato. La logica principale risiede all'interno del file principale del modulo, responsabile della generazione dinamica del feed XML quando viene acceduto l'URL specifico del feed. Non utilizza controller personalizzati, modelli o file di template dedicati per la sua funzionalità principale, affidandosi all'output diretto per il feed.

### 4.2 Controller (`controllers/`)
-   **Controller Front-Office**: Nessuno. Il feed di prodotti viene generato direttamente dal file principale del modulo quando viene acceduto il suo URL specifico, piuttosto che tramite un `ModuleFrontController` dedicato.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione (visualizzazione dell'URL del feed) è gestita all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)
-   Nessuna classe personalizzata o definizione di `ObjectModel` è presente in questo modulo. Tutta la logica è contenuta all'interno della classe `ShopmaniaIntegration` nel file principale del modulo.

### 4.4 Risorse JavaScript (`views/js/`)
-   Nessun file JavaScript è incluso o utilizzato da questo modulo.

### 4.5 Fogli di Stile CSS (`views/css/`)
-   Nessun file CSS è incluso o utilizzato da questo modulo.

### 4.6 Struttura del Template Smarty (`views/templates/`)
-   Nessun file di template Smarty personalizzato (`.tpl`) è utilizzato da questo modulo. Il metodo `getContent()` produce direttamente l'HTML per la pagina di configurazione, e il feed di prodotti viene generato come XML grezzo.

### 4.7 Schema del Database e Mappa degli Hook
-   **Tabelle del Database**: Questo modulo non crea tabelle di database personalizzate. Memorizza la sua configurazione (se fosse necessaria oltre all'URL del feed) nella tabella standard `ps_configuration`, sebbene per questo modulo, l'URL del feed sia generato dinamicamente e non memorizzato come valore di configurazione.
-   **Tabella degli Hook Registrati**:
    Questo modulo non registra esplicitamente alcun hook nel metodo `install()` per la visualizzazione o l'azione nel front-office. La sua funzione principale è rispondere a una richiesta URL diretta per il feed XML. Sebbene la descrizione della funzionalità menzioni "Hook Front-Office: Intestazione, Colonne, Prodotto o Piè di pagina", questa è probabilmente una descrizione generica per i moduli che *potrebbero* usarli, ma questo modulo specifico non implementa alcun componente visivo nel front-office. La sua integrazione è puramente basata su feed di dati.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
|---|---|---|
| `displayBackOfficeHeader` | Eseguito durante il rendering dell'intestazione del Back Office. | Utilizzato per includere CSS/JS specifici del modulo per la pagina di configurazione (anche se questo modulo non ne usa). |
| `displayHeader` | Eseguito nella sezione `<head>` delle pagine del front-office. | (Non utilizzato da questo modulo per l'output visivo, ma potrebbe essere utilizzato per meta tag o script se necessario). |
| `displayRightColumn` | Eseguito nella colonna destra delle pagine del front-office. | (Non utilizzato da questo modulo). |
| `displayLeftColumn` | Eseguito nella colonna sinistra delle pagine del front-office. | (Non utilizzato da questo modulo). |
| `displayProductAdditionalInfo` | Eseguito sulla pagina del prodotto. | (Non utilizzato da questo modulo). |
| `displayFooter` | Eseguito nel piè di pagina delle pagine del front-office. | (Non utilizzato da questo modulo). |

La funzionalità principale del modulo (generazione del feed XML) viene attivata quando viene acceduto l'URL specifico del feed (ad esempio, `iltuonegozio.com/modules/shopmania-integration/shopmania-feed.php` o simile, a seconda del routing di PrestaShop). Questo non è un hook standard di PrestaShop ma una richiesta HTTP diretta a un endpoint specifico del modulo.

## 5. Supporto Ufficiale e Aggiornamenti
Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore assistenza con il modulo Integrazione Shopmania, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per aiutare con problemi relativi al modulo e garantire che la tua integrazione funzioni senza intoppi.
"""
