---
title: "Aggiornamento massivo gratuito dei prezzi dei prodotti - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Aggiornamento massivo gratuito dei prezzi dei prodotti' di MyPresta.eu."
sidebar:
  label: "Aggiornamento massivo gratuito dei prezzi dei prodotti - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Free mass products prices update su MyPresta.eu](https://mypresta.eu/modules/administration-tools/free-mass-products-prices-update.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/free-mass-products-prices-update/)
>
> ---


# Aggiornamento massivo gratuito dei prezzi dei prodotti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Aggiornamento massivo gratuito dei prezzi dei prodotti)

Questa è la schermata di configurazione principale e unica per il modulo "Aggiornamento massivo gratuito dei prezzi dei prodotti". Qui definirai come desideri regolare i prezzi dei tuoi prodotti.

#### **Tipo di regolazione del prezzo**

-   **Cosa fa questa impostazione:** Questa impostazione cruciale determina se desideri aumentare o diminuire i prezzi dei tuoi prodotti.
-   **Effetto della modifica di questa impostazione:**
    *   *Se impostato su "Aumenta":* Il modulo aggiungerà la percentuale specificata al prezzo corrente di ogni prodotto.
    *   *Se impostato su "Diminuisci":* Il modulo sottrarrà la percentuale specificata dal prezzo corrente di ogni prodotto.
-   **Valore consigliato:** Scegli in base alle tue immediate esigenze aziendali (es. "Aumenta" per un aumento generale dei prezzi, "Diminuisci" per un saldo).
-   **Scenario / esempio del commerciante:** Se i costi del tuo fornitore sono aumentati, selezioneresti "Aumenta". Se stai eseguendo un'offerta lampo, selezioneresti "Diminuisci".

#### **Valore percentuale**

-   **Cosa fa questa impostazione:** Questo campo ti consente di inserire la percentuale esatta con cui desideri regolare i prezzi.
-   **Effetto della modifica di questa impostazione:**
    *   *Se impostato su "10":* Se è selezionato "Aumenta", i prezzi aumenteranno del 10%. Se è selezionato "Diminuisci", i prezzi diminuiranno del 10%.
    *   *Se impostato su "0":* Non si verificherà alcuna modifica di prezzo.
-   **Valore consigliato:** Inserisci la percentuale precisa di cui hai bisogno. Usa numeri interi o decimali (es. "5" per 5%, "2.5" per 2.5%).
-   **Scenario / esempio del commerciante:** Per offrire uno sconto del 15% su tutto il negozio, imposteresti "Tipo di regolazione del prezzo" su "Diminuisci" e "Valore percentuale" su "15". Per aumentare i prezzi del 7.5%, imposteresti "Tipo di regolazione del prezzo" su "Aumenta" e "Valore percentuale" su "7.5".

#### **Pulsante Applica modifiche**

-   **Cosa fa:** Questo pulsante avvia il processo di aggiornamento effettivo dei prezzi.
-   **Effetto del clic su questo pulsante:** Una volta cliccato, il modulo elaborerà tutti i prodotti nel tuo negozio in base al "Tipo di regolazione del prezzo" e al "Valore percentuale" che hai impostato. **Questa azione è irreversibile senza un backup del database.**
-   **Azione consigliata:** Controlla sempre due volte il tuo "Tipo di regolazione del prezzo" e il "Valore percentuale" prima di cliccare su questo pulsante. Assicurati di avere un backup recente del database.
-   **Scenario / esempio del commerciante:** Dopo aver impostato attentamente "Diminuisci" e "20" per un saldo del fine settimana, clicchi su "Applica modifiche" per aggiornare istantaneamente tutti i prezzi dei prodotti del -20%.

:::warning NOTA IMPORTANTE
Il modulo "Aggiornamento massivo gratuito dei prezzi dei prodotti" esegue un aggiornamento diretto sui prezzi dei tuoi prodotti. **Non esiste un pulsante "annulla".** Prima di applicare qualsiasi modifica, è **CRITICO** che tu crei un backup completo del tuo database PrestaShop. Questo ti permetterà di ripristinare i tuoi prezzi allo stato precedente se commetti un errore o cambi idea.
:::

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Tipo di regolazione del prezzo | (Seleziona Aumenta/Diminuisci) | Determina se i prezzi aumenteranno o diminuiranno. |
| Configurazione modulo | Valore percentuale | (Inserisci la percentuale desiderata) | La percentuale esatta per la regolazione del prezzo. |
| Configurazione modulo | Pulsante Applica modifiche | (Clicca con cautela) | Esegue l'aggiornamento massivo dei prezzi. **Irreversibile senza backup.** |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho aggiornato i prezzi, ma non vengono visualizzati nel mio negozio. Cosa c'è che non va?**
R1: Dopo qualsiasi modifica significativa dei dati in PrestaShop, specialmente relativa ai prodotti, è buona pratica svuotare la cache del tuo negozio.
\* Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office.
\* Clicca sul pulsante "Svuota la cache" nell'angolo in alto a destra.
\* Inoltre, assicurati che la cache del tuo browser sia svuotata, o prova a visualizzare il tuo negozio in una finestra di navigazione in incognito/privata.

**D2: Ho commesso un errore e ho aggiornato i prezzi in modo errato. Come posso annullare?**
R2: Come accennato, questo modulo non ha un pulsante "annulla". Ecco perché un backup del database è cruciale.
\* Se hai fatto un backup *prima* di applicare le modifiche, dovrai ripristinare il tuo database da quel backup. Questo di solito richiede l'accesso al pannello di controllo del tuo hosting (es. cPanel, Plesk) o l'utilizzo di un modulo di backup di PrestaShop.
\* Se *non* hai fatto un backup, dovrai reinserire manualmente i prezzi corretti per i tuoi prodotti, o utilizzare nuovamente il modulo con un calcolo inverso (es. se hai diminuito del 20%, dovresti aumentare del 25% per tornare al valore originale, ma questo potrebbe non essere perfettamente accurato a causa degli arrotondamenti).

**D3: Questo modulo influisce su prezzi specifici o combinazioni?**
R3: Il modulo aggiorna il *prezzo base* dei tuoi prodotti. Non gestisce direttamente prezzi specifici (sconti, sconti per quantità) o impatti sui prezzi delle combinazioni di prodotti. Se hai impostato prezzi specifici, la modifica del prezzo base influenzerà il punto di partenza per tali prezzi specifici.

**D4: È possibile aggiornare i prezzi solo per categorie o produttori specifici?**
R4: No, questa versione gratuita del modulo esegue un aggiornamento massivo su *tutti* i prodotti del tuo negozio. Non offre filtri per categoria, produttore o altri criteri. Per aggiornamenti di prezzo più avanzati e filtrati, avresti tipicamente bisogno di un modulo di importazione/esportazione o di aggiornamento massivo più sofisticato, spesso a pagamento.

**D5: Il modulo sembra bloccato o non risponde quando clicco su "Applica modifiche".**
R5: Per i negozi con un numero molto elevato di prodotti (migliaia), il processo di aggiornamento può richiedere del tempo.
\* Assicurati che il limite di tempo di esecuzione PHP del tuo server sia sufficiente. Potresti vedere un "Errore interno del server 500" o un timeout se è troppo basso. Questo è un problema di configurazione del server, non un bug del modulo.
\* Controlla i log degli errori di PrestaShop (situati in `var/logs/` in PrestaShop 1.7/8/9) per eventuali errori specifici.
\* Se il problema persiste, contatta il tuo provider di hosting o uno sviluppatore web per controllare i log del server e le impostazioni PHP.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Aggiornamento massivo gratuito dei prezzi dei prodotti" è un modulo PrestaShop semplice progettato principalmente per l'amministrazione del Back Office. Segue una struttura di modulo PrestaShop di base, sfruttando la classe `Module` e il suo metodo `getContent()` per la configurazione. Interagisce direttamente con il database di PrestaShop per aggiornare i prezzi dei prodotti senza controller personalizzati, modelli o interazioni JavaScript complesse. La logica del modulo è autocontenuta all'interno del suo file PHP principale.

### 4.2 Controller (`controllers/`)

Questo modulo **non** utilizza alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutte le funzionalità sono gestite direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** definisce alcuna classe personalizzata né estende `ObjectModel`. Interagisce direttamente con i metodi `Product` e `Product::updatePrice()` forniti dal core di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato. Lo stile per la pagina di configurazione è gestito dal tema predefinito del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza due semplici template Smarty:

-   **`masspricefree/views/advert.tpl`**:
    *   **Ambito:** Back-office (pagina di configurazione del modulo).
    *   **Scopo:** Probabilmente utilizzato per visualizzare un annuncio o un messaggio promozionale da MyPresta.eu all'interno dell'interfaccia di configurazione del modulo. Viene tipicamente renderizzato nella parte superiore o inferiore dell'output di `getContent()`.
-   **`masspricefree/views/script.tpl`**:
    *   **Ambito:** Back-office (pagina di configurazione del modulo).
    *   **Scopo:** Questo template potrebbe contenere JavaScript inline o semplici elementi HTML che fanno parte del modulo di configurazione del modulo, sebbene la descrizione del modulo suggerisca un JS minimo. Data la semplicità del modulo, è più probabile che sia un segnaposto o contenga elementi UI molto basilari.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    *   Questo modulo **non** crea alcuna tabella di database personalizzata.
    *   Modifica direttamente i dati nella tabella `ps_product` (in particolare la colonna `price`) e potenzialmente `ps_product_shop` (per contesti multi-negozio) chiamando i metodi core di PrestaShop.
    *   Le impostazioni di configurazione (Tipo di regolazione del prezzo, Valore percentuale) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi di configurazione standard di PrestaShop (es. `PS_MASS_PRICE_FREE_TYPE`, `PS_MASS_PRICE_FREE_VALUE`).
-   **Tabella degli hook registrati**:
    Questo modulo **non** registra alcun hook specifico per la visualizzazione front-office o le azioni back-office oltre a `displayBackOfficeHeader` (implicitamente per la configurazione del modulo) e `actionModuleInstall`/`actionModuleUninstall`. La sua funzione principale è una manipolazione diretta del database attivata dall'invio del modulo amministrativo.

| Nome dell'Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` del Back Office. | Utilizzato da `getContent()` per caricare potenzialmente risorse o visualizzare avvisi, sebbene non esplicitamente utilizzato per risorse personalizzate in questo modulo. |
| `actionModuleInstall` | Attivato quando il modulo viene installato. | Utilizzato per impostare i valori di configurazione predefiniti in `ps_configuration`. |
| `actionModuleUninstall` | Attivato quando il modulo viene disinstallato. | Utilizzato per pulire i valori di configurazione da `ps_configuration`. |

### 4.8 File principale del modulo (`masspricefree/index.php`)

La logica principale risiede in `masspricefree/index.php`.

-   **Nome della classe:** `MassPriceFree`
-   **Classe genitore:** `Module`
-   **Metodi chiave:**
    *   `__construct()`: Inizializza le proprietà del modulo (nome, tab, versione, autore, need\_instance, bootstrap).
    *   `install()`: Registra il modulo, imposta i valori di configurazione predefiniti (es. `PS_MASS_PRICE_FREE_TYPE` su 'increase', `PS_MASS_PRICE_FREE_VALUE` su '0').
    *   `uninstall()`: Elimina i valori di configurazione.
    *   `getContent()`: Questo è il metodo principale per la funzionalità del modulo.
        *   Gestisce l'invio del modulo (`Tools::isSubmit('submitMassPriceFree')`).
        *   Recupera `price_type` e `price_value` dal modulo inviato.
        *   Aggiorna `ps_configuration` con le nuove impostazioni.
        *   **Crucialmente, itera su tutti i prodotti attivi (`Product::getProducts(Context::getContext()->language->id, 0, 0, 'id_product', 'ASC', false, true)`) e aggiorna i loro prezzi in base alla percentuale e al tipo configurati.** Utilizza `Product::updatePrice()` per questo.
        *   Renderizza il modulo di configurazione utilizzando `displayForm()` e include i template `advert.tpl` e `script.tpl`.
    *   `displayForm()`: Genera l'HTML per il modulo di configurazione del modulo, inclusi i pulsanti radio per aumentare/diminuire e il campo di input per la percentuale.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto dedicato per il modulo "Aggiornamento massivo gratuito dei prezzi dei prodotti", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo.
