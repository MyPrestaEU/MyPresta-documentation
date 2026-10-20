---
title: "Cambio massivo tipo di prodotto - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Cambio massivo tipo di prodotto' di MyPresta.eu."
sidebar:
  label: "Cambio massivo tipo di prodotto - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Mass change product type su MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-change-product-type.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/mass-change-product-type/)
>
> ---


# Cambio massivo tipo di prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito sono abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Cambio massivo tipo di prodotto" fornisce una singola e intuitiva schermata di configurazione all'interno del tuo Back Office di PrestaShop. Questa schermata ti guida attraverso la selezione dei prodotti e l'applicazione della modifica del tipo di prodotto desiderata.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alla configurazione del modulo, naviga su **Moduli > Gestione moduli**, cerca "Cambio massivo tipo di prodotto" e clicca su **"Configura"**.

La pagina di configurazione è divisa in due sezioni principali: **1. Seleziona prodotti** e **2. Cosa fare con i prodotti selezionati**.

#### Sezione 1: Seleziona prodotti

Questa sezione ti permette di definire quali prodotti saranno interessati dal cambio massivo. Puoi selezionare i prodotti in base a vari criteri.

##### 1.1 Seleziona prodotti per categoria

-   **Cosa fa questa impostazione:** Ti permette di selezionare tutti i prodotti appartenenti a una o più categorie specifiche.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando le categorie sono selezionate:* Solo i prodotti all'interno delle categorie scelte saranno considerati per il cambio di tipo.
    -   *Quando nessuna categoria è selezionata:* Questo criterio non verrà utilizzato per filtrare i prodotti.
-   **Valore consigliato:** Seleziona le categorie pertinenti alla tua operazione di cambio massivo.
-   **Scenario / esempio per il commerciante:** Vuoi convertire tutti i prodotti nella tua categoria "Download Digitali" da prodotti standard a prodotti virtuali. Selezioneresti qui la categoria "Download Digitali".

##### 1.2 Seleziona prodotti per marca

-   **Cosa fa questa impostazione:** Ti permette di selezionare tutti i prodotti associati a una o più marche (produttori) specifiche.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando le marche sono selezionate:* Solo i prodotti delle marche scelte saranno considerati per il cambio di tipo.
    -   *Quando nessuna marca è selezionata:* Questo criterio non verrà utilizzato per filtrare i prodotti.
-   **Valore consigliato:** Seleziona le marche pertinenti alla tua operazione di cambio massivo.
-   **Scenario / esempio per il commerciante:** Hai deciso di vendere tutti i prodotti di "Marca X" come bundle. Selezioneresti qui "Marca X".

##### 1.3 Seleziona prodotti per caratteristica

-   **Cosa fa questa impostazione:** Ti permette di selezionare prodotti che hanno una caratteristica specifica e, opzionalmente, un valore specifico per quella caratteristica.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando una caratteristica (e opzionalmente un valore) è selezionata:* Solo i prodotti che corrispondono a questo criterio di caratteristica saranno considerati.
    -   *Quando nessuna caratteristica è selezionata:* Questo criterio non verrà utilizzato per filtrare i prodotti.
-   **Valore consigliato:** Scegli la caratteristica e il valore che identificano precisamente i prodotti che desideri modificare.
-   **Scenario / esempio per il commerciante:** Vuoi cambiare tutti i prodotti con la caratteristica "Materiale" impostata su "Digitale" in prodotti virtuali. Selezioneresti qui "Materiale" e poi "Digitale".

##### 1.4 Seleziona prodotti per attributo

-   **Cosa fa questa impostazione:** Ti permette di selezionare prodotti che hanno un attributo specifico e, opzionalmente, un valore specifico per quell'attributo. Questo è utile per i prodotti con combinazioni.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando un attributo (e opzionalmente un valore) è selezionato:* Solo i prodotti che corrispondono a questo criterio di attributo saranno considerati.
    -   *Quando nessun attributo è selezionato:* Questo criterio non verrà utilizzato per filtrare i prodotti.
-   **Valore consigliato:** Scegli l'attributo e il valore che identificano precisamente i prodotti che desideri modificare.
-   **Scenario / esempio per il commerciante:** Vuoi convertire tutti i prodotti che hanno l'attributo "Taglia" impostato su "Scaricabile" in prodotti virtuali. Selezioneresti qui "Taglia" e poi "Scaricabile".

##### 1.5 Seleziona prodotti per frase di ricerca

-   **Cosa fa questa impostazione:** Ti permette di selezionare prodotti i cui nomi contengono una frase specifica. Questo utilizza uno strumento di ricerca per trovare i prodotti.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando viene inserita una frase di ricerca:* I prodotti i cui nomi corrispondono alla frase verranno aggiunti alla selezione.
    -   *Quando nessuna frase di ricerca è inserita:* Questo criterio non verrà utilizzato per filtrare i prodotti.
-   **Valore consigliato:** Inserisci una frase chiara e concisa per identificare i tuoi prodotti target.
-   **Scenario / esempio per il commerciante:** Vuoi cambiare tutti i prodotti con "eBook" nel loro nome in prodotti virtuali. Digiteresti "eBook" nella casella di ricerca.

##### 1.6 Elenco prodotti selezionati

-   **Cosa fa questa impostazione:** Dopo aver applicato uno qualsiasi dei filtri sopra, quest'area visualizzerà un elenco di prodotti che corrispondono ai tuoi criteri. Puoi rimuovere manualmente i prodotti da questo elenco se non vuoi che siano interessati.
-   **Effetto della modifica di questa impostazione:**
    -   *Rimozione di un prodotto:* Quel prodotto specifico sarà escluso dal cambio massivo di tipo.
    -   *Lasciare i prodotti nell'elenco:* Saranno inclusi nel cambio massivo di tipo.
-   **Valore consigliato:** Rivedi sempre attentamente questo elenco per assicurarti che siano selezionati solo i prodotti desiderati.
-   **Scenario / esempio per il commerciante:** Hai cercato "eBook" ma è apparso un libro fisico intitolato "Manuale Lettore eBook". Rimuoveresti questo prodotto specifico dall'elenco.

#### Sezione 2: Cosa fare con i prodotti selezionati

Una volta selezionati i prodotti target, questa sezione ti permette di scegliere il nuovo tipo di prodotto che desideri applicare.

##### 2.1 Cambia tipo di prodotto in:

-   **Cosa fa questa impostazione:** Questo menu a discesa ti permette di selezionare il nuovo tipo di prodotto per tutti i prodotti identificati nella Sezione 1.
-   **Opzioni:**
    -   **Prodotto standard:** Un normale prodotto fisico.
    -   **Pacco di prodotti:** Un bundle di altri prodotti.
    -   **Prodotto con combinazioni:** Un prodotto con varianti (es. taglia, colore).
    -   **Prodotto virtuale:** Un prodotto non fisico (es. servizio, download).
-   **Effetto della modifica di questa impostazione:**
    -   *Selezione di un'opzione:* Tutti i prodotti selezionati verranno convertiti in questo nuovo tipo.
-   **Valore consigliato:** Scegli il tipo di prodotto che riflette accuratamente la nuova natura dei tuoi prodotti selezionati.
-   **Scenario / esempio per il commerciante:** Hai selezionato tutti i prodotti "eBook". Sceglieresti qui "Prodotto virtuale".

##### 2.2 Pulsante Applica modifiche

-   **Cosa fa questa impostazione:** Questo pulsante esegue l'operazione di cambio massivo.
-   **Effetto della modifica di questa impostazione:**
    -   *Cliccando il pulsante:* Il modulo elaborerà tutti i prodotti nell'"Elenco prodotti selezionati" e cambierà il loro tipo di prodotto in quello scelto in "Cambia tipo di prodotto in:". Di solito apparirà un messaggio di conferma.
-   **Valore consigliato:** Clicca su questo solo dopo essere assolutamente certo della tua selezione di prodotti e del nuovo tipo desiderato.
-   **Scenario / esempio per il commerciante:** Dopo aver rivisto i tuoi eBook selezionati e aver confermato "Prodotto virtuale" come nuovo tipo, clicchi su "Applica modifiche" per convertirli tutti.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Seleziona prodotti per categoria** | Seleziona categorie pertinenti | Filtra i prodotti in base alle categorie assegnate. |
| Configurazione modulo | **Seleziona prodotti per marca** | Seleziona marche pertinenti | Filtra i prodotti in base al loro produttore/marca. |
| Configurazione modulo | **Seleziona prodotti per caratteristica** | Seleziona caratteristica e valore | Filtra i prodotti in base a caratteristiche specifiche e ai loro valori. |
| Configurazione modulo | **Seleziona prodotti per attributo** | Seleziona attributo e valore | Filtra i prodotti in base ad attributi specifici e ai loro valori (per combinazioni). |
| Configurazione modulo | **Seleziona prodotti per frase di ricerca** | Inserisci termine di ricerca | Filtra i prodotti in base a parole chiave nel loro nome. |
| Configurazione modulo | **Elenco prodotti selezionati** | Rivedi attentamente | Visualizza i prodotti selezionati; consente la rimozione manuale prima dell'elaborazione. |
| Configurazione modulo | **Cambia tipo di prodotto in:** | Scegli il tipo desiderato | Imposta il nuovo tipo di prodotto (Standard, Pacco, Combinazioni, Virtuale) per tutti i prodotti selezionati. |
| Configurazione modulo | **Pulsante Applica modifiche** | Clicca per eseguire | Avvia il cambio massivo del tipo di prodotto per tutti i prodotti selezionati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho cambiato i tipi di prodotto, ma non vedo le modifiche nel front office del mio negozio.**
R: Dopo aver apportato modifiche nel Back Office, svuota sempre la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" nell'angolo in alto a destra. Potrebbe essere necessario svuotare anche la cache del tuo browser (Ctrl+F5 o Cmd+R).

**D: Alcuni prodotti non sono stati modificati, anche se erano nella mia selezione.**
R:

1.  **Controlla di nuovo l'"Elenco prodotti selezionati":** Li hai accidentalmente rimossi dall'elenco prima di applicare le modifiche?
2.  **Verifica i criteri:** Ricontrolla i tuoi criteri di selezione (categoria, marca, caratteristica, attributo, frase di ricerca). I prodotti corrispondono veramente a tutti i filtri selezionati?
3.  **Stato del prodotto:** Assicurati che i prodotti siano attivi e non disabilitati.
4.  **Errori:** Controlla se sono apparsi messaggi di errore durante il processo di "Applica modifiche".

**D: Posso annullare le modifiche apportate da questo modulo?**
R: Questo modulo esegue aggiornamenti diretti del database. Non esiste un pulsante "annulla" all'interno del modulo stesso. Ecco perché un **backup del database prima dell'uso è cruciale**. Se hai bisogno di annullare, in genere ripristineresti il tuo database da un backup effettuato *prima* di utilizzare il modulo. In alternativa, dovresti utilizzare nuovamente il modulo per riportare i tipi di prodotto al loro stato originale, o modificarli manualmente.

**D: Questo modulo influenzerà la SEO o gli URL del mio prodotto?**
R: La modifica del tipo di prodotto in sé non altera direttamente il suo URL SEO-friendly. Tuttavia, se la modifica del tipo porta ad altre modifiche (es. rimozione di combinazioni, modifica della struttura del prodotto), è sempre una buona idea controllare le pagine dei prodotti ed eventualmente rigenerare gli URL (sezione SEO & URL in PrestaShop) se noti problemi, anche se questo è raro per un semplice cambio di tipo.

**D: Il modulo non mostra alcun prodotto quando uso la frase di ricerca.**
R:

1.  **Controlla gli errori di battitura:** Assicurati che la tua frase di ricerca sia scritta correttamente.
2.  **Sensibilità alle maiuscole/minuscole:** I nomi dei prodotti potrebbero essere sensibili alle maiuscole/minuscole a seconda della configurazione del tuo database, prova diverse maiuscole/minuscole.
3.  **Lingua:** Assicurati di cercare nella lingua corretta se il tuo negozio è multilingue.
4.  **Conflitto di moduli:** Disabilita temporaneamente altri moduli correlati alla ricerca per verificare la presenza di conflitti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che mantengono o estendono un negozio PrestaShop utilizzando il modulo "Cambio massivo tipo di prodotto".

### 4.1 Panoramica dell'architettura

Il modulo "Cambio massivo tipo di prodotto" (`massptype`) è un modulo PrestaShop standard che opera principalmente all'interno del Back Office. Sfrutta la classe `Module` di PrestaShop e utilizza AJAX per il filtraggio dei prodotti e il processo di aggiornamento massivo. La logica principale risiede nel file principale del modulo, gestendo la configurazione, la selezione dei prodotti e l'aggiornamento in blocco dei tipi di prodotto. Integra uno strumento di ricerca personalizzato per la selezione dei prodotti.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il front-office o il back-office nelle directory `controllers/admin` o `controllers/front`. Tutta la logica è gestita all'interno del file principale del modulo `massptype.php` e del suo metodo `getContent()`, che funge da punto di ingresso principale per la configurazione. Le richieste AJAX vengono inviate tramite il file `ajax_products_list.php` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce classi `ObjectModel` personalizzate. Interagisce direttamente con i metodi `Product` e `Product::updateProductFlags()` di PrestaShop per modificare i tipi di prodotto.

### 4.4 Risorse JavaScript (`views/js/`)

-   `massptype/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office (utilizzato all'interno della pagina di configurazione del modulo).
    -   **Scopo:** Fornisce la logica principale per la funzionalità di autocompletamento della ricerca prodotti. Probabilmente gestisce l'invio di richieste AJAX all'endpoint `ajax_products_list.php` del modulo per recuperare suggerimenti di prodotti basati sull'input dell'utente.
-   `massptype/views/js/jquery.autocomplete.js`
    -   **Ambito:** Back-office (utilizzato all'interno della pagina di configurazione del modulo).
    -   **Scopo:** Sembra essere un plugin jQuery per la funzionalità di autocompletamento, probabilmente una dipendenza o un'implementazione personalizzata utilizzata dallo strumento di ricerca. Gestisce l'aspetto dell'interfaccia utente per la visualizzazione dei suggerimenti e l'interazione dell'utente.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `massptype/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office (stili gli elementi all'interno della pagina di configurazione del modulo).
    -   **Scopo:** Stila il menu a discesa di autocompletamento, i campi di input e potenzialmente l'elenco dei prodotti selezionati all'interno dell'interfaccia dello strumento di ricerca del modulo. Gli sviluppatori possono sovrascrivere questi stili nel loro tema personalizzato del Back Office o aggiungendo regole CSS più specifiche.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `massptype/views/templates/hook/form.tpl`
        -   **Hook:** Non direttamente agganciato nel senso tradizionale, ma renderizzato da `getContent()` del file principale del modulo.
        -   **Scopo:** Questo è il template principale per il modulo di configurazione del modulo nel Back Office. Contiene la struttura HTML per la selezione dei prodotti in base a vari criteri e la scelta del nuovo tipo di prodotto.
-   **Template admin (`views/templates/admin/`)**:
    -   `massptype/views/templates/admin/target_products.tpl`
        -   **Scopo:** Questo template è probabilmente utilizzato per renderizzare l'elenco dei prodotti selezionati dopo che i criteri di filtraggio sono stati applicati. Si aggiorna dinamicamente tramite AJAX per mostrare quali prodotti saranno interessati.
    -   `massptype/views/templates/admin/wtd.tpl` (Cosa fare)
        -   **Scopo:** Questo template probabilmente renderizza la sezione in cui l'utente seleziona il nuovo tipo di prodotto (Standard, Pacco, Combinazioni, Virtuale) e il pulsante "Applica modifiche".
-   **Altri template**:
    -   `massptype/lib/searchTool/views/scripts.tpl`
        -   **Scopo:** Questo template probabilmente include codice JavaScript o inizializza la funzionalità di autocompletamento JavaScript per lo strumento di ricerca prodotti. Potrebbe essere incluso all'interno di `form.tpl`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle di database personalizzate. Modifica le tabelle principali esistenti di PrestaShop, in particolare `ps_product` (e potenzialmente `ps_product_shop`) aggiornando i campi `cache_is_pack`, `cache_has_attachments`, `is_virtual` e `cache_default_attribute`, che determinano il tipo di prodotto. Le impostazioni di configurazione sono memorizzate in `ps_configuration` utilizzando chiavi standard (es. `_PS_MASS_PTYPE_...`).
-   **Tabella degli hook registrati**:
    Il modulo non registra alcun hook di visualizzazione tradizionale per il front-office o il back-office. La sua funzionalità è interamente contenuta nel suo metodo `getContent()` e nelle chiamate AJAX.

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante l'installazione del modulo | Imposta la configurazione iniziale. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce la configurazione. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Cambio massivo tipo di prodotto", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo.
