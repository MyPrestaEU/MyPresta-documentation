---
title: "Stylight - pixel di tracciamento vendite - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Stylight - pixel di tracciamento vendite di MyPresta.eu."
sidebar:
  label: "Stylight - pixel di tracciamento vendite"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Stylight - sales tracking pixel su MyPresta.eu](https://mypresta.eu/modules/ordering-process/stylight-sales-tracking-pixel.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/stylight-sales-tracking-pixel/)
>
> ---


# Stylight - pixel di tracciamento vendite

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL) tipicamente disponibili sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Il modulo "Stylight - pixel di tracciamento vendite" è progettato per essere estremamente semplice da configurare, non richiedendo impostazioni specifiche da parte del commerciante. La sua funzionalità è principalmente autonoma, rilevando e trasmettendo automaticamente i dati dell'ordine necessari.

Navigando alla pagina di configurazione del modulo (Back Office > Moduli > Gestione moduli > Stylight - pixel di tracciamento vendite > Configura), troverai tipicamente un messaggio di conferma che indica che il modulo è installato e attivo.

-   **Cosa fa questa schermata:** Questa pagina serve come conferma che il modulo è correttamente installato e pronto a tracciare le vendite. Non ci sono campi di input o interruttori da regolare. Il modulo si aggancia automaticamente al processo di conferma dell'ordine e raccoglie tutti i dati richiesti (Importo Totale, Valuta, Conteggio Articoli, numeri SKU, ID Ordine) direttamente dai dettagli dell'ordine di PrestaShop.
-   **Effetto della modifica di questa impostazione:** Poiché non ci sono impostazioni configurabili, non c'è nulla da modificare. Il modulo funziona immediatamente dopo l'installazione.
-   **Valore consigliato:** Nessuna azione richiesta.
-   **Scenario/esempio del commerciante:** Dopo aver installato il modulo, visiti semplicemente questa pagina per confermare la sua presenza. Non è necessario inserire ID o chiavi specifiche di Stylight, poiché il pixel stesso è generico e progettato per funzionare con il sistema di Stylight inviando dati e-commerce standard.

### 2.2 Tabella di riferimento rapido della configurazione
| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | *(Nessuna impostazione configurabile dall'utente)* | N/A | Il modulo traccia automaticamente i dati di vendita (importo totale, valuta, conteggio articoli, SKU, ID ordine) sulla pagina di conferma dell'ordine per Stylight.com. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo alcuna vendita riportata nel mio account Stylight. Cosa devo fare?**
R: Innanzitutto, assicurati che il modulo sia abilitato nel tuo Back Office di PrestaShop. Quindi, prova a svuotare la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota cache). Se il problema persiste, effettua tu stesso un ordine di prova. Se ancora non ci sono dati, contatta il supporto MyPresta.eu con i dettagli della tua versione di PrestaShop e di eventuali altri moduli installati di recente.

**D: Questo modulo rallenta la mia pagina di conferma dell'ordine?**
R: Il pixel di tracciamento è molto leggero e si carica in modo asincrono, il che significa che generalmente non influisce in modo significativo sui tempi di caricamento della pagina o sull'esperienza del cliente. Il suo effetto sulle prestazioni è minimo.

**D: Devo inserire un ID Stylight o una chiave API nel modulo?**
R: No, questo modulo è progettato per funzionare immediatamente. Implementa un pixel di tracciamento Stylight standard che invia automaticamente i dati dell'ordine necessari senza richiedere ID specifici inseriti dal commerciante nella configurazione del modulo stesso. Il tuo account Stylight è collegato al tuo dominio e il loro sistema identifica il tuo negozio in base all'origine del pixel.

**D: Questo modulo è compatibile con temi personalizzati?**
R: Sì, il modulo si aggancia a un hook standard di PrestaShop (`displayOrderConfirmation`) che è tipicamente presente in tutti i temi ben codificati. Non si basa su elementi specifici del tema, quindi dovrebbe funzionare senza problemi con la maggior parte dei temi personalizzati.

**D: Ho più lingue/valute. Il modulo le traccia correttamente?**
R: Sì, il modulo è progettato per acquisire automaticamente l'importo totale e la valuta dell'ordine elaborati da PrestaShop, garantendo un tracciamento accurato per negozi multi-valuta e multi-lingua.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo "Stylight - pixel di tracciamento vendite" è un modulo PrestaShop semplice, focalizzato principalmente sull'aggancio di eventi del front-office. Sfrutta l'hook `displayOrderConfirmation` per iniettare un pixel di tracciamento basato su JavaScript nella pagina finale di conferma dell'ordine. La logica del modulo è contenuta nel suo file PHP principale, `index.php`, che gestisce l'installazione, la disinstallazione e la registrazione dell'hook. La raccolta dei dati è dinamica, estraendo i dettagli dell'ordine direttamente dagli oggetti `Order` e `Product` disponibili nel contesto della pagina di conferma dell'ordine.

### 4.2 Controller (`controllers/`)
-   **Controller Front-Office**: Nessuno. La funzionalità front-office del modulo è interamente gestita agganciandosi a `displayOrderConfirmation` e renderizzando un template Smarty.
-   **Controller Admin Back-Office**: Nessuno. Il modulo non ha un'interfaccia di amministrazione dedicata oltre alla pagina di configurazione standard del modulo (`getContent()`).

### 4.3 Classi e Modelli Core (`classes/`)
-   Nessuno. Il modulo non definisce classi personalizzate né estende `ObjectModel`. Tutta la logica risiede nel file principale `stylightpixel/index.php`.

### 4.4 Risorse JavaScript (`views/js/`)
-   Nessuno. Il codice del pixel di tracciamento è incorporato direttamente nel template Smarty (`displayOrderConfirmation.tpl`) per assicurarsi che si attivi immediatamente al caricamento della pagina.

### 4.5 Fogli di stile CSS (`views/css/`)
-   Nessuno. Il modulo è puramente funzionale e non ha componenti visivi o requisiti di stile.

### 4.6 Struttura del template Smarty (`views/templates/`)
-   **Template degli hook (`views/templates/hook/`)**:
    *   `stylightpixel/views/templates/hook/displayOrderConfirmation.tpl`
        *   **Hook**: `displayOrderConfirmation`
        *   **Scopo**: Questo template viene renderizzato nella pagina di conferma dell'ordine dopo un acquisto riuscito. Contiene il codice JavaScript per il pixel di tracciamento di Stylight.
        *   **Dati disponibili**: Il template riceve `$order` (un oggetto `Order`) e `$products` (un array di oggetti `Product` associati all'ordine) dal metodo `hookDisplayOrderConfirmation`.
        *   **Output**: Emette un blocco `<script>` che costruisce l'URL del pixel di tracciamento di Stylight con parametri dinamici come `order_id`, `total_amount`, `currency`, `item_count` e `sku` per ogni prodotto.

### 4.7 Schema del database e Mappa degli hook
-   **Tabelle del database**: Il modulo non crea tabelle di database personalizzate. Si basa su tabelle standard di PrestaShop (`ps_orders`, `ps_order_detail`, `ps_product`, ecc.) per recuperare le informazioni sull'ordine.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
|---|---|---|
| `displayOrderConfirmation` | Eseguito sulla pagina finale di conferma dell'ordine dopo un acquisto riuscito. | Inietta il JavaScript del pixel di tracciamento di Stylight nella pagina per inviare dati di conversione (ID ordine, totale, valuta, SKU prodotto, conteggio articoli) a Stylight. |

## 5. Supporto Ufficiale e Aggiornamenti
Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore assistenza con il modulo "Stylight - pixel di tracciamento vendite", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per aiutare con domande relative al modulo e garantire che il pixel di tracciamento funzioni correttamente.
