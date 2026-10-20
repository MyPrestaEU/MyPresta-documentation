---
title: "Regola carrello per il prodotto più costoso - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Regola carrello per il prodotto più costoso' di MyPresta.eu."
sidebar:
  label: "Regola carrello per il prodotto più costoso"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cart rule for the most expensive product su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-rule-for-the-most-expensive-product.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/cart-rule-for-the-most-expensive-product/)
>
> ---


# Regola carrello per il prodotto più costoso

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, clicca su "Configura" accanto al modulo in Gestione moduli. Questo ti porterà alla schermata di configurazione principale per "Regola carrello per il prodotto più costoso".

#### Impostazioni e Opzioni:

-   **Aggiornamenti Live MyPresta.eu (mypresta_updates)**
    -   **Cosa fa questa impostazione:** Questa impostazione controlla se il modulo può verificare la disponibilità di aggiornamenti direttamente da MyPresta.eu. Aiuta a garantire che tu stia sempre utilizzando l'ultima versione con correzioni di bug e nuove funzionalità.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo si connetterà periodicamente a MyPresta.eu per verificare la disponibilità di nuove versioni. Se è disponibile un aggiornamento, potresti vedere una notifica nel tuo back office di PrestaShop.
        -   *Quando disabilitato (NO):* Il modulo non verificherà automaticamente la disponibilità di aggiornamenti. Dovrai controllare e scaricare manualmente gli aggiornamenti dal tuo account MyPresta.eu.
    -   **Valore consigliato:** SÌ
    -   **Scenario/esempio del commerciante:** Mantenere questa opzione abilitata garantisce di ricevere notifiche tempestive per aggiornamenti critici, migliorando la sicurezza e la compatibilità senza sforzo manuale.

-   **Prodotti esclusi (csc_excluded_products)**
    -   **Cosa fa questa impostazione:** Questo campo ti permette di specificare prodotti che *non* dovrebbero mai essere considerati per lo sconto sul "prodotto più costoso", anche se sono effettivamente l'articolo più costoso nel carrello. Questo è utile per prodotti con margini molto bassi, promozioni speciali o articoli che non vuoi scontare.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando vengono inseriti gli ID dei prodotti:* Il modulo ignorerà questi prodotti specifici quando determinerà quale articolo è il "più costoso" per la regola del carrello. Se uno di questi prodotti esclusi è il più costoso, il modulo cercherà il successivo prodotto *non escluso* più costoso a cui applicare lo sconto.
        -   *Quando lasciato vuoto:* Tutti i prodotti nel carrello sono idonei a essere identificati come il "più costoso" per lo sconto.
    -   **Valore consigliato:** Lasciare vuoto a meno che tu non abbia prodotti specifici da escludere.
    -   **Scenario/esempio del commerciante:** Vendi un prodotto molto popolare e ad alto margine (ID 123) e alcuni articoli "loss-leader" (ID 456, ID 789). Vuoi che lo sconto sul "prodotto più costoso" si applichi ai tuoi articoli ad alto margine, ma non ai "loss-leader". Inseriresti `456,789` (ID prodotto separati da virgola) in questo campo.

#### 2.1.1 Pagina di modifica della regola carrello (Back Office > Catalogo > Sconti > Regole carrello > Aggiungi nuova / Modifica)
Questo modulo aggiunge una nuova opzione direttamente alla pagina standard di creazione/modifica delle regole carrello di PrestaShop. Troverai questa opzione quando stai creando o modificando una regola carrello che utilizza uno **sconto percentuale**.

-   **Posizione del menu:** Back Office > Catalogo > Sconti > Regole carrello. Clicca su "Aggiungi nuova regola carrello" o modifica una esistente.
-   **Azione disponibile:** Nella scheda "Azioni" della configurazione della regola carrello, dopo aver selezionato "Percentuale" per l'opzione "Applica uno sconto", apparirà una nuova casella di controllo.

    -   **Applica sconto solo al prodotto più costoso**
        -   **Cosa fa questa impostazione:** Questa è la funzionalità principale del modulo. Quando abilitata per una specifica regola carrello, lo sconto percentuale definito per quella regola verrà applicato solo al singolo prodotto più costoso nel carrello del cliente.
        -   **Effetto della modifica di questa impostazione:**
            -   *Quando abilitata (selezionata):* Lo sconto percentuale della regola carrello verrà calcolato esclusivamente in base al prezzo del prodotto più costoso nel carrello (escludendo eventuali prodotti che hai escluso globalmente nella configurazione principale del modulo).
            -   *Quando disabilitata (deselezionata):* La regola carrello si comporterà come uno sconto percentuale standard di PrestaShop, applicando lo sconto all'intero totale del carrello o ai prodotti idonei secondo altre configurazioni della regola carrello (es. selezione prodotti, importo minimo).
        -   **Valore consigliato:** Abilita questa opzione solo per le regole carrello in cui desideri specificamente mirare all'articolo più costoso.
        -   **Scenario/esempio del commerciante:** Vuoi eseguire una promozione "20% di sconto sul tuo articolo più grande". Crei una nuova regola carrello, imposti lo sconto al 20% (percentuale) e poi selezioni questa casella. Quando i clienti usano questo voucher, otterranno il 20% di sconto sul loro articolo più costoso, non il 20% di sconto sull'intero ordine.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configurazione Modulo | Aggiornamenti Live MyPresta.eu | SÌ | Abilita i controlli automatici degli aggiornamenti per il modulo. |
| Configurazione Modulo | Prodotti esclusi | Vuoto | ID prodotto separati da virgola da escludere dal calcolo del "più costoso". |
| Modifica Regola Carrello (Scheda Azioni) | Applica sconto solo al prodotto più costoso | Deselezionato | Se selezionato, applica lo sconto percentuale solo all'articolo più costoso nel carrello. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Lo sconto non si applica al prodotto più costoso, o non funziona affatto.**
R:
1.  **Controlla la configurazione della regola carrello:** Vai su **Catalogo > Sconti > Regole carrello**, modifica la tua regola e assicurati che nella scheda "Azioni", "Applica uno sconto" sia impostato su "Percentuale" e la casella di controllo "Applica sconto solo al prodotto più costoso" sia **selezionata**.
2.  **Verifica l'idoneità del prodotto:** Controlla la configurazione principale del modulo (**Moduli > Gestione moduli > Configura** per "Regola carrello per il prodotto più costoso"). Assicurati che il prodotto a cui ti aspetti che lo sconto si applichi non sia elencato nel campo "Prodotti esclusi".
3.  **Svuota la cache:** A volte la cache di PrestaShop può impedire che le modifiche abbiano effetto immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
4.  **Conflitti tra moduli:** Se hai altri moduli che modificano pesantemente i calcoli del carrello o degli sconti, potrebbe esserci un conflitto. Prova a disabilitare temporaneamente altri moduli relativi agli sconti per vedere se il problema si risolve.

**D: Posso applicare questo sconto solo a una categoria specifica di prodotti?**
R: Sì, puoi combinare la funzionalità di questo modulo con le restrizioni standard delle regole carrello di PrestaShop. Nella scheda "Condizioni" della tua regola carrello, puoi aggiungere condizioni come "Selezione prodotti" per specificare che lo sconto si applica solo se un prodotto di una certa categoria è nel carrello. Tuttavia, ricorda che *se* tale prodotto è presente, il modulo sceglierà comunque il prodotto *complessivamente* più costoso nel carrello (a meno che quel prodotto non sia escluso) e applicherà lo sconto ad esso, non necessariamente al prodotto più costoso *di quella specifica categoria*.

**D: Questo modulo funziona con sconti a importo fisso?**
R: No, questo modulo è specificamente progettato per funzionare **solo con sconti percentuali**. L'opzione "Applica sconto solo al prodotto più costoso" apparirà e funzionerà solo quando selezioni "Percentuale" come tipo di sconto nella scheda "Azioni" della regola carrello.

**D: Il mio tema personalizzato non visualizza correttamente lo sconto.**
R: Il modulo modifica principalmente la logica di calcolo dello sconto, non la visualizzazione nel front-office. I template predefiniti di PrestaShop dovrebbero mostrare lo sconto correttamente. Se il tuo tema personalizzato ha pesantemente personalizzato il riepilogo del carrello o del checkout, potrebbe richiedere piccole modifiche per riflettere correttamente come vengono applicati gli sconti. Nella maggior parte dei casi, svuotare la cache di Smarty (**Parametri avanzati > Prestazioni > Svuota la cache**) dovrebbe risolvere i problemi di visualizzazione. In caso contrario, consulta lo sviluppatore del tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo "Regola carrello per il prodotto più costoso" (`crexpensive`) estende principalmente la classe `CartRule` di PrestaShop tramite un override. Ciò gli consente di iniettare logica personalizzata nel processo di calcolo dello sconto senza modificare direttamente i file core. Il modulo fornisce anche un'interfaccia di configurazione minima nel Back Office e registra un hook per iniettare il JavaScript necessario per i moduli di amministrazione.

### 4.2 Controller (`controllers/`)
Questo modulo non introduce alcun controller front-office o back-office personalizzato. La sua funzionalità è integrata direttamente nei processi esistenti di PrestaShop tramite override e hook.

### 4.3 Classi e Modelli Core (`classes/`)

-   **`crexpensive/override/classes/CartRule.php`**
    *   **Nome classe:** `CartRule` (sovrascrive la classe core `CartRule`)
    *   **Classe genitore:** `CartRuleCore`
    *   **Responsabilità:** Questo override è il cuore della funzionalità del modulo. Modifica il comportamento di come vengono applicate le regole del carrello, mirando specificamente al calcolo di `reduction_percent`.
    *   **Metodi e logica chiave:**
        *   L'override probabilmente intercetta o modifica i metodi relativi al calcolo di `reduction_percent` all'interno della classe `CartRule`. Conterrà la logica per:
            1.  Verificare se la regola carrello corrente ha il flag `apply_to_most_expensive_product` abilitato (un campo personalizzato aggiunto dal modulo).
            2.  Se abilitato, iterare attraverso i prodotti nel carrello per identificare il più costoso, tenendo conto di eventuali prodotti esclusi globalmente configurati nel modulo.
            3.  Regolare l'applicazione di `reduction_percent` per influenzare solo il prodotto più costoso identificato, assicurando che lo sconto sia calcolato sul suo prezzo piuttosto che sull'intero carrello o su altri prodotti.
        *   Aggiunge anche un nuovo campo alla definizione di `CartRule` (`$definition`) per memorizzare il flag `apply_to_most_expensive_product` nella tabella del database `ps_cart_rule`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`crexpensive/views/js/crexpensive.js`**
    *   **Ambito:** Back-office (specificamente la pagina di modifica della Regola Carrello).
    *   **Responsabilità:** Questo script è responsabile della visualizzazione/nascondimento dinamico della casella di controllo "Applica sconto solo al prodotto più costoso" nella pagina di modifica della Regola Carrello.
    *   **Logica chiave:**
        *   Probabilmente ascolta i cambiamenti nel menu a discesa/pulsanti radio "Applica uno sconto" (specificamente quando viene selezionato "Percentuale").
        *   Quando viene scelto "Percentuale", rende visibile la casella di controllo personalizzata.
        *   Quando vengono scelti altri tipi di sconto (es. "Importo", "Spedizione gratuita"), nasconde la casella di controllo, poiché il modulo si applica solo agli sconti percentuali.
        *   Assicura che lo stato della casella di controllo sia caricato correttamente durante la modifica di una regola carrello esistente.

### 4.5 Fogli di stile CSS (`views/css/`)
Questo modulo non include alcun file CSS personalizzato. Si basa sullo stile predefinito di PrestaShop per i suoi elementi di configurazione e la casella di controllo iniettata nella pagina della regola carrello.

### 4.6 Struttura del template Smarty (`views/templates/`)
Questo modulo non include alcun file di template Smarty personalizzato. Il modulo di configurazione viene renderizzato tramite `getContent()` nel file principale del modulo, e la casella di controllo personalizzata viene iniettata nella pagina di modifica della Regola Carrello esistente tramite JavaScript.

### 4.7 Schema del database e Mappa degli Hook

-   **Tabelle del database**:
    *   Il modulo modifica la tabella `ps_cart_rule` aggiungendo una nuova colonna, probabilmente denominata `apply_to_most_expensive_product` (o simile), che è un campo tinyint (booleano) per memorizzare lo stato della casella di controllo personalizzata per ogni regola carrello.
    *   I valori di configurazione (`mypresta_updates`, `csc_excluded_products`) sono memorizzati nella tabella `ps_configuration`.

-   **Tabella degli Hook registrati**:

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| :-------- | :--------------- | :---------------- |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin sta impostando le sue risorse media (JS/CSS). | Questo hook viene utilizzato per caricare `crexpensive.js` nella pagina di modifica della Regola Carrello nel Back Office, abilitando la visualizzazione dinamica della casella di controllo "Applica sconto solo al prodotto più costoso". |

## 5. Supporto ufficiale e aggiornamenti
Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo "Regola carrello per il prodotto più costoso", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
