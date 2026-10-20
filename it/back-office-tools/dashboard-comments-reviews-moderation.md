---
title: "Moderazione commenti/recensioni della Dashboard - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop di MyPresta.eu per la moderazione di commenti/recensioni della Dashboard."
sidebar:
  label: "Moderazione commenti/recensioni della Dashboard"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Dashboard comments / reviews moderation su MyPresta.eu](https://mypresta.eu/modules/administration-tools/dashboard-comments-reviews-moderation.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/dashboard-comments-reviews-moderation/)
>
> ---


# Moderazione commenti/recensioni della Dashboard

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono richieste per PrestaShop stesso e sono tipicamente disponibili su tutti gli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale del modulo. Questo modulo è progettato per essere molto semplice, con impostazioni minime, poiché la sua funzione principale è visualizzare informazioni sulla tua dashboard.

**Nome schermata:** Configurazione moderazione commenti/recensioni della Dashboard

**Posizione menu:** Back Office > Moduli > Gestione moduli > Moderazione commenti/recensioni della Dashboard > Configura

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio del commerciante |
|---|---|---|---|---|
| **Aggiornamenti MyPresta.eu** | Questa sezione si riferisce tipicamente al controllo degli aggiornamenti per i moduli MyPresta.eu. Potrebbe includere opzioni per abilitare/disabilitare i controlli degli aggiornamenti o visualizzare le notifiche di aggiornamento. | *Quando abilitato:* Il modulo controllerà periodicamente MyPresta.eu per nuove versioni e ti avviserà nel back office se è disponibile un aggiornamento. Questo ti aiuta a mantenere il tuo modulo aggiornato con le ultime funzionalità e correzioni di bug. *Quando disabilitato:* Il modulo non controllerà automaticamente gli aggiornamenti. Dovresti controllare manualmente gli aggiornamenti su MyPresta.eu. | **Abilitato (Sì)** | Mantenere questa opzione abilitata ti assicura di essere sempre a conoscenza delle nuove versioni, permettendoti di beneficiare di miglioramenti e aggiornamenti di sicurezza senza controlli manuali. |
| **Update_ (Interno)** | Questa è un'impostazione interna, probabilmente correlata al meccanismo di aggiornamento stesso. Non è tipicamente destinata all'interazione diretta del commerciante. | La modifica di questa impostazione non è consigliata in quanto potrebbe interferire con la capacità del modulo di controllare e applicare gli aggiornamenti. | **Lasciare come predefinito** | Questa è un'impostazione tecnica; i proprietari dei negozi non dovrebbero modificarla. |
| **Updatev_ (Interno)** | Simile a `update_`, questa è un'impostazione interna relativa alla versione per il meccanismo di aggiornamento. | La modifica di questa impostazione non è consigliata in quanto potrebbe interferire con la capacità del modulo di controllare e applicare gli aggiornamenti. | **Lasciare come predefinito** | Questa è un'impostazione tecnica; i proprietari dei negozi non dovrebbero modificarla. |

**Nota importante:** La funzionalità principale di visualizzazione di commenti e recensioni sulla tua dashboard non richiede una configurazione estesa. Una volta installato, il modulo si integra automaticamente con la tua dashboard per mostrare le recensioni in sospeso e i commenti segnalati, supponendo che tu abbia il modulo standard "Commenti sui prodotti" di PrestaShop (o un'alternativa compatibile) installato e attivo.

### 2.2 Schermate di amministrazione dedicate e viste del controller
Questo modulo **non** introduce nuove schermate di amministrazione dedicate o viste del controller personalizzate. La sua funzionalità è integrata direttamente nella dashboard esistente di PrestaShop.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | Aggiornamenti MyPresta.eu | Abilitato (Sì) | Abilita i controlli automatici per gli aggiornamenti del modulo da MyPresta.eu. |
| Pagina di configurazione del modulo | Update_ | Lasciare come predefinito | Impostazione interna per il meccanismo di aggiornamento. |
| Pagina di configurazione del modulo | Updatev_ | Lasciare come predefinito | Impostazione interna per il meccanismo di aggiornamento. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho installato il modulo, ma non vedo commenti/recensioni sulla mia dashboard.**
**R1:**
*   **Controlla il modulo "Commenti sui prodotti":** Questo modulo si basa sul modulo standard "Commenti sui prodotti" di PrestaShop (o un modulo di recensioni di terze parti compatibile) per funzionare. Assicurati che il modulo "Commenti sui prodotti" sia installato, abilitato e configurato correttamente nel tuo negozio.
*   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. A volte, la cache di PrestaShop deve essere aggiornata affinché i nuovi elementi della dashboard appaiano.
*   **Controlla le recensioni in sospeso:** Hai effettivamente delle recensioni in attesa di moderazione o dei commenti segnalati come offensivi? Il modulo visualizzerà solo i contenuti che richiedono la tua attenzione. Se non ci sono tali elementi, il blocco della dashboard potrebbe apparire vuoto o non comparire se non c'è nulla da visualizzare.

**D2: Il blocco della dashboard sembra strano o non è stilizzato correttamente.**
**R2:**
*   **Svuota la cache del browser:** A volte il tuo browser web memorizza nella cache vecchi file CSS. Prova a svuotare la cache del tuo browser o ad aprire il tuo back office in una finestra in incognito/privata.
*   **Controlla i conflitti del tema:** Sebbene rari per i moduli della dashboard, un tema di amministrazione altamente personalizzato potrebbe potenzialmente entrare in conflitto. Se lo sospetti, prova a passare temporaneamente al tema di amministrazione predefinito di PrestaShop (se possibile) per vedere se il problema persiste. Se si risolve, consulta lo sviluppatore del tuo tema.
*   **Svuota la cache di PrestaShop:** Come menzionato sopra, svuotare la cache di Smarty in **Parametri avanzati > Prestazioni** può risolvere i problemi di visualizzazione.

**D3: Come posso tradurre il testo del modulo in un'altra lingua?**
**R3:**
*   Naviga su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
*   Seleziona "Traduzioni dei moduli installati" per il "Tipo di traduzione".
*   Scegli il tuo tema (es. "Classic") e la lingua che desideri tradurre.
*   Trova "Moderazione commenti/recensioni della Dashboard" nell'elenco, clicca su "Modifica" e potrai quindi tradurre tutte le stringhe di testo disponibili.

**D4: Ho cliccato su "Configura" ma vedo solo le impostazioni di aggiornamento, non gli strumenti di moderazione.**
**R4:** Il pulsante "Configura" per questo modulo porta alla sua pagina di impostazioni minime, principalmente per la gestione degli aggiornamenti. Gli strumenti di moderazione effettivi (l'elenco di commenti/recensioni) vengono visualizzati direttamente sulla tua dashboard principale di PrestaShop, di solito in una delle aree della "Zona Dashboard". Naviga sulla tua "Dashboard" principale (la prima pagina che vedi dopo aver effettuato l'accesso) per trovare l'output del modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo "Moderazione commenti/recensioni della Dashboard" (`dashcomments`) è un modulo PrestaShop leggero progettato per estendere la dashboard del Back Office. Sfrutta il sistema di hook di PrestaShop per iniettare un blocco personalizzato nella dashboard, visualizzando le recensioni dei prodotti in sospeso e i commenti segnalati. Non introduce nuove tabelle di database o complesse strutture `ObjectModel`, ma si basa sui dati esistenti del modulo `ps_product_comment`. La sua funzione principale è la presentazione e l'interazione con i dati esistenti tramite AJAX.

### 4.2 Controller (`controllers/`)
Questo modulo **non** include alcun controller front-office o back-office personalizzato. Tutte le interazioni sono gestite direttamente all'interno della classe principale del modulo (`dashcomments.php`) o tramite chiamate AJAX elaborate dai metodi `ajaxProcess` del modulo.

### 4.3 Classi e modelli principali (`classes/`)
Questo modulo **non** definisce classi o modelli personalizzati nella directory `classes/`. Interagisce direttamente con le funzionalità principali di PrestaShop e, implicitamente, con la classe `ProductComment` del modulo `ps_product_comments` (se installato).

### 4.4 Risorse JavaScript (`views/js/`)

-   **`dashcomments/js/dashcomments.js`**
    *   **Ambito:** Back-office (Dashboard).
    *   **Scopo:** Gestisce le interazioni AJAX per la moderazione di commenti e recensioni direttamente dal widget della dashboard.
    *   **Funzionalità chiave:**
        *   Associa i listener di eventi click ai pulsanti "Approva", "Disapprova" ed "Elimina" all'interno del widget della dashboard.
        *   Invia richieste AJAX ai metodi `ajaxProcess` del modulo (es. `ajaxProcessApproveComment`, `ajaxProcessDisapproveComment`, `ajaxProcessDeleteComment`) per eseguire azioni di moderazione.
        *   Aggiorna il DOM (rimuove la riga del commento moderato, aggiorna i conteggi) dopo una risposta AJAX riuscita.
        *   Può includere la logica per la gestione delle azioni "segnala come offensivo" se implementate per i commenti stessi.
        *   Utilizza `$.ajax` per la comunicazione asincrona.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`dashcomments/css/dashcomments.css`**
    *   **Ambito:** Back-office (Dashboard).
    *   **Scopo:** Fornisce lo stile per il widget della dashboard che visualizza i commenti e le recensioni in sospeso.
    *   **Stile chiave:**
        *   Stili per l'elenco dei commenti, le singole righe dei commenti, i pulsanti di azione (approva, disapprova, elimina) e potenzialmente i contatori per gli elementi in sospeso.
        *   Garantisce che il widget si integri visivamente con il tema del back-office di PrestaShop 1.7+/8+.
        *   **Selettori di classe CSS chiave:** Gli sviluppatori possono ispezionare l'HTML generato per classi specifiche (es. `.dashcomments-widget`, `.dashcomments-item`, `.dashcomments-actions`) per sovrascrivere o estendere lo stile nei loro temi di amministrazione personalizzati.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`dashcomments/dashboardZoneOne.tpl`**
    *   **Ambito:** Back-office (Dashboard).
    *   **Hook:** `displaydashboardZoneTwo` (o `dashboardZoneTwo` nelle versioni precedenti).
    *   **Scopo:** Questo template è responsabile del rendering della struttura HTML del widget di moderazione di commenti/recensioni sulla dashboard di PrestaShop.
    *   **Contenuto:**
        *   Visualizza un elenco di commenti sui prodotti in attesa di approvazione.
        *   Visualizza un elenco di commenti sui prodotti che sono stati segnalati come offensivi.
        *   Per ogni commento, di solito mostra il nome del prodotto, il nome del cliente, il contenuto del commento, la valutazione e i pulsanti di azione (Approva, Disapprova, Elimina).
        *   Include la logica per iterare sulle variabili `$pending_comments` e `$reported_comments` passate dal modulo.
        *   Contiene gli elementi HTML e gli attributi di dati necessari per lo script `dashcomments.js` per allegare i suoi listener di eventi ed eseguire azioni AJAX.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Questo modulo non crea tabelle di database personalizzate. Si basa sulla tabella `ps_product_comment` (e tabelle correlate come `ps_product_comment_grade`, `ps_product_comment_criterion`) che sono create dal modulo ufficiale `ps_product_comments`.
-   **Record di configurazione**:
    *   `PS_DASHCOMMENTS_UPDATES`: Memorizza lo stato dei controlli degli aggiornamenti.
    *   `PS_DASHCOMMENTS_UPDATE_`: Flag di aggiornamento interno.
    *   `PS_DASHCOMMENTS_UPDATEV_`: Flag di versione interno per gli aggiornamenti.

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
|---|---|---|
| `actionAdminControllerSetMedia` | Eseguito quando un controller di amministrazione sta impostando le sue risorse multimediali (CSS/JS). | Utilizzato per registrare i file `dashcomments.js` e `dashcomments.css` del modulo per la dashboard del Back Office. |
| `displaydashboardZoneTwo` | Renderizza il contenuto nella seconda zona della dashboard del Back Office di PrestaShop. | Questo è l'hook principale utilizzato per visualizzare il widget di moderazione di commenti/recensioni. |
| `dashboardZoneTwo` | (Hook legacy, simile a `displaydashboardZoneTwo`) | Fornisce compatibilità per versioni precedenti di PrestaShop o layout di dashboard alternativi per visualizzare il widget. |

## 5. Supporto ufficiale e aggiornamenti
Per supporto ufficiale, aggiornamenti del modulo e qualsiasi ulteriore assistenza, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Puoi scaricare le ultime versioni del modulo dalla cronologia degli ordini e accedere ai nostri canali di supporto dedicati per qualsiasi domanda o problema tecnico.
