---
title: "Integrazione del monitoraggio delle vendite Kelkoo - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop di integrazione del monitoraggio delle vendite Kelkoo di MyPresta.eu."
sidebar:
  label: "Integrazione del monitoraggio delle vendite Kelkoo"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Kelkoo sales tracking integration su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/kelkoo-sales-tracking-integration.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/kelkoo-sales-tracking-integration/)
>
> ---


# Integrazione del monitoraggio delle vendite Kelkoo

## 1. Requisiti e compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per la maggior parte dei moduli PrestaShop e sono solitamente disponibili su qualsiasi ambiente di hosting moderno. Nessun requisito speciale o insolito per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, clicca su "Configura" accanto al modulo "Integrazione del monitoraggio delle vendite Kelkoo". Ti verrà presentata una semplice schermata di configurazione.

#### ID di tracciamento Kelkoo
-   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. È qui che inserisci il tuo ID di tracciamento univoco fornito da Kelkoo. Questo ID dice a Kelkoo a quale commerciante (il tuo negozio) appartengono i dati di vendita.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando inserito correttamente:* Il modulo utilizzerà questo ID per inviare i dati di vendita al tuo account Kelkoo specifico, consentendo a Kelkoo di attribuire le vendite alle tue campagne.
    -   *Quando lasciato vuoto o errato:* Il monitoraggio delle vendite non funzionerà correttamente e Kelkoo non riceverà dati sugli acquisti effettuati tramite la loro piattaforma, rendendo impossibile misurare le prestazioni della tua campagna.
-   **Valore consigliato:** Inserisci l'ID di tracciamento esatto fornito da Kelkoo. Questo è solitamente una stringa numerica o alfanumerica.
-   **Scenario / esempio del commerciante:** Hai configurato un account commerciante con Kelkoo. Ti forniranno un "ID di tracciamento Kelkoo" o "ID commerciante" univoco. Devi copiare e incollare questo ID precisamente in questo campo. Senza di esso, l'integrazione è incompleta.

#### Abilita tracciamento
-   **Cosa fa questa impostazione:** Questo è un semplice interruttore ON/OFF per attivare o disattivare la funzionalità di monitoraggio delle vendite Kelkoo in tutto il tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo inietterà attivamente gli script di tracciamento necessari e invierà i dati di vendita a Kelkoo sulla pagina di conferma dell'ordine.
    -   *Quando disabilitato (NO):* Il modulo cesserà tutte le attività di tracciamento. Nessuno script verrà iniettato e nessun dato di vendita verrà inviato a Kelkoo.
-   **Valore consigliato:** SÌ. Dovresti disabilitarlo solo se desideri temporaneamente interrompere il monitoraggio delle vendite tramite Kelkoo o stai risolvendo un problema.
-   **Scenario / esempio del commerciante:** Hai completato la configurazione di Kelkoo e vuoi iniziare subito a monitorare le vendite. Imposta questo su SÌ. Se decidi di mettere in pausa le tue campagne Kelkoo o hai bisogno di eseguire la manutenzione, potresti temporaneamente impostarlo su NO.

### 2.2 Tabella di riferimento rapido della configurazione
| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Configurazione modulo | ID di tracciamento Kelkoo | Il tuo ID Kelkoo | Identificatore univoco per il tuo account commerciante Kelkoo. Essenziale per l'attribuzione delle vendite. |
| Configurazione modulo | Abilita tracciamento | SÌ | Attiva/disattiva la funzionalità di monitoraggio delle vendite Kelkoo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma Kelkoo non mostra alcuna vendita. Cosa devo fare?**
R:
1.  **Ricontrolla il tuo ID di tracciamento Kelkoo:** Assicurati che sia inserito esattamente come fornito da Kelkoo, senza spazi o caratteri extra.
2.  **Assicurati che "Abilita tracciamento" sia SÌ:** Questo interruttore deve essere attivo affinché il modulo funzioni.
3.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte, il contenuto memorizzato nella cache può impedire che le nuove impostazioni del modulo abbiano effetto.
4.  **Effettua un acquisto di prova:** Completa un ordine completo sul tuo negozio per attivare il tracciamento.
5.  **Contatta il supporto Kelkoo:** Se tutte le impostazioni sono corrette e hai svuotato la cache, contatta il team di supporto di Kelkoo. Spesso possono controllare la loro parte per vedere se vengono ricevuti dati o se c'è un problema con la configurazione del tuo account sulla loro piattaforma.

**D: Questo modulo rallenterà il mio sito web?**
R: No, il modulo è molto leggero. Inietta solo un piccolo snippet JavaScript non bloccante nell'header e invia dati sulla pagina di conferma dell'ordine. Questo processo è ottimizzato per non influire sulla velocità di caricamento del tuo negozio o sull'esperienza del cliente.

**D: Questo modulo funziona con configurazioni multi-negozio?**
R: Sì, il modulo dovrebbe funzionare correttamente in un ambiente multi-negozio. Configurerai l'ID di tracciamento Kelkoo per ogni negozio individualmente se hanno account Kelkoo separati, o userai lo stesso ID se stai monitorando tutti i negozi sotto un unico account Kelkoo.

**D: Sto usando un tema personalizzato. Questo modulo funzionerà comunque?**
R: Sì, il modulo utilizza gli hook standard di PrestaShop (`displayHeader`, `displayOrderConfirmation`) che sono quasi universalmente presenti in tutti i temi ben codificati. Non si basa su elementi specifici del tema, quindi dovrebbe essere compatibile con i temi personalizzati. Se riscontri problemi, assicurati che il tuo tema personalizzato implementi correttamente questi hook principali di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo "Integrazione del monitoraggio delle vendite Kelkoo" è un modulo PrestaShop semplice progettato per integrare il pixel di monitoraggio delle vendite di Kelkoo. Sfrutta principalmente il sistema di hook di PrestaShop per iniettare uno script di tracciamento globale nell'header e uno script di tracciamento delle conversioni nella pagina di conferma dell'ordine. Segue una struttura di modulo PrestaShop di base, con la sua logica principale contenuta nel file del modulo principale e file di template per il rendering degli hook. Non ci sono controller personalizzati, modelli o asset JavaScript/CSS complessi oltre a quanto necessario per il pixel di tracciamento.

### 4.2 Controller (`controllers/`)
- **Controller Front-Office**: Nessuno. Tutte le funzionalità del front-office sono gestite tramite hook all'interno del file del modulo principale.
- **Controller Admin Back-Office**: Nessuno. La configurazione è gestita direttamente dal metodo `getContent()` nel file del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)
- Nessuna classe personalizzata o definizione di `ObjectModel` è presente in questo modulo. Tutta la logica risiede nel file del modulo principale `Kelkoo.php` (o `index.php` nelle strutture più vecchie).

### 4.4 Asset JavaScript (`views/js/`)
- Nessun file JavaScript dedicato è incluso nel modulo. Lo script di tracciamento Kelkoo necessario viene generato dinamicamente e iniettato direttamente nell'HTML tramite i template Smarty o l'hook `displayHeader`.

### 4.5 Fogli di stile CSS (`views/css/`)
- Nessun file CSS dedicato è incluso nel modulo. Il modulo non ha componenti visivi nel front-office e la sua configurazione nel back-office utilizza lo styling standard dei moduli di PrestaShop.

### 4.6 Struttura dei template Smarty (`views/templates/`)
- **Template degli hook (`views/templates/hook/`)**:
    *   `kelkoo/views/templates/hook/displayOrderConfirmation.tpl`:
        *   **Hook**: `displayOrderConfirmation`
        *   **Scopo**: Questo template viene renderizzato nella pagina di conferma dell'ordine dopo un acquisto riuscito. È responsabile della generazione del pixel di monitoraggio delle vendite Kelkoo (KST) con dettagli dinamici dell'ordine (ID ordine, totale, dettagli del prodotto). Recupera le informazioni dell'ordine passate all'hook e le formatta secondo le specifiche di Kelkoo.
    *   `kelkoo/views/templates/hook/header.tpl`:
        *   **Hook**: `displayHeader`
        *   **Scopo**: Questo template viene renderizzato all'interno della sezione `<head>` di ogni pagina. È destinato a includere eventuali script di tracciamento globali di Kelkoo o inizializzatori che devono essere presenti in tutto il sito, sebbene per il semplice monitoraggio delle vendite, la logica principale sia spesso in `displayOrderConfirmation`. Potrebbe contenere un pixel base di Kelkoo o un segnaposto per future funzionalità di Kelkoo.

- **Template di amministrazione (`views/templates/admin/`)**: Nessuno. Il modulo di configurazione è costruito direttamente all'interno di `getContent()` utilizzando le classi helper di PrestaShop.
- **Template front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook
- **Tabelle del database**:
    *   Il modulo non crea tabelle SQL personalizzate.
    *   Le impostazioni di configurazione (`Kelkoo Tracking ID`, `Enable Tracking`) sono memorizzate nella tabella `ps_configuration` (o prefisso `_configuration`) utilizzando chiavi come `KELKOO_TRACKING_ID` e `KELKOO_ENABLED`.

- **Tabella degli hook registrati**:
  | Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
  |---|---|---|
  | `displayHeader` | Renderizza nella sezione `<head>` di ogni pagina. | Inietta script di tracciamento globali di Kelkoo o pixel base. |
  | `displayOrderConfirmation` | Renderizza nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Invia dati di vendita dettagliati (ID ordine, importo, prodotti) a Kelkoo per il monitoraggio delle conversioni. |

## 5. Supporto ufficiale e aggiornamenti
Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo "Integrazione del monitoraggio delle vendite Kelkoo", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
"""
