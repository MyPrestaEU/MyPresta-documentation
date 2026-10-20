---
title: "Pagine CMS per gruppi - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pagine CMS per gruppi di MyPresta.eu."
sidebar:
  label: "Pagine CMS per gruppi - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo CMS pages for groups su MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-groups.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/cms-pages-for-groups/)
>
> ---


# Pagine CMS per gruppi

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Pagine CMS per gruppi)

Questa è la schermata di configurazione principale in cui gestirai quali gruppi di clienti possono accedere a specifiche pagine CMS.

Quando accedi per la prima volta alla pagina di configurazione, vedrai un elenco di tutte le tue pagine CMS esistenti. Per ogni pagina CMS, troverai opzioni per controllarne la visibilità.

**Struttura generale della pagina:**
La pagina di configurazione visualizza una tabella. Ogni riga della tabella rappresenta una delle tue pagine CMS. Per ogni pagina CMS, vedrai:

-   **Nome pagina:** Il titolo della tua pagina CMS (ad esempio, "Chi siamo", "Termini e condizioni").
-   **Gruppi di clienti:** Un elenco di caselle di controllo, una per ogni gruppo di clienti definito nel tuo negozio PrestaShop (ad esempio, "Visitatore", "Ospite", "Cliente", "Grossista").

**Cosa fa questa impostazione:**
Per ogni pagina CMS, selezioni i gruppi di clienti che sono **autorizzati** a visualizzare quella specifica pagina. Se un cliente non fa parte di nessuno dei gruppi selezionati per una data pagina, gli verrà negato l'accesso a quella pagina.

**Effetto della modifica di questa impostazione:**

-   **Quando un gruppo è selezionato per una pagina CMS:** I clienti appartenenti a questo gruppo potranno visualizzare la pagina CMS normalmente.
-   **Quando un gruppo è deselezionato per una pagina CMS:** I clienti appartenenti a questo gruppo **non** potranno visualizzare la pagina CMS. Se tentano di accedervi, verranno reindirizzati a un errore "Pagina non trovata".
-   **Se nessun gruppo è selezionato per una pagina CMS:** Ciò significa che la pagina è effettivamente nascosta a *tutti* i clienti, poiché nessun gruppo ha il permesso di visualizzarla. Questo potrebbe essere utile per pagine in costruzione o contenuti solo interni.
-   **Se tutti i gruppi sono selezionati per una pagina CMS:** Ciò significa che la pagina è visibile a tutti, tornando di fatto al comportamento predefinito di PrestaShop per quella specifica pagina.

**Valore consigliato:**
Questo dipende interamente dalle tue esigenze aziendali.

-   Per pagine standard come "Chi siamo" o "Contattaci", probabilmente selezionerai tutti i gruppi.
-   Per termini legali specifici per il B2B, potresti selezionare solo il tuo gruppo "Grossista".
-   Per una pagina "Vantaggi del Club VIP", potresti selezionare solo il tuo gruppo "Cliente VIP".

**Scenario / esempio del commerciante:**
Supponiamo che tu abbia tre gruppi di clienti: "Visitatore" (non loggato), "Cliente" (utenti registrati standard) e "Grossista" (clienti B2B).

1.  **Scenario 1: Pagina "Chi siamo"**

    -   **Scopo:** Informazioni generali per tutti.
    -   **Azione:** Seleziona "Visitatore", "Cliente" e "Grossista" per la pagina "Chi siamo".
    -   **Risultato:** Tutti possono vedere la pagina "Chi siamo".
2.  **Scenario 2: Pagina "Termini e condizioni all'ingrosso"**

    -   **Scopo:** Termini legali specifici solo per i tuoi clienti B2B.
    -   **Azione:** Seleziona solo "Grossista" per la pagina "Termini e condizioni all'ingrosso".
    -   **Risultato:** Solo i clienti del gruppo "Grossista" possono visualizzare questa pagina. Ai gruppi "Visitatore" e "Cliente" verrà negato l'accesso.
3.  **Scenario 3: Pagina "Dettagli programma fedeltà"**

    -   **Scopo:** Informazioni per i clienti registrati sui loro punti fedeltà.
    -   **Azione:** Seleziona "Cliente" e "Grossista" (supponendo che i clienti all'ingrosso possano anche far parte del programma fedeltà) per la pagina "Dettagli programma fedeltà".
    -   **Risultato:** Solo i clienti loggati (standard o all'ingrosso) possono visualizzare questa pagina. Ai visitatori verrà negato l'accesso.

**Salvataggio delle modifiche:**
Dopo aver effettuato le selezioni per tutte le pagine CMS, ricorda di cliccare sul pulsante **"Salva"** (solitamente in fondo alla pagina) per applicare le modifiche.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | **Nome pagina CMS** (es. "Chi siamo") | Varia per pagina | Controlla quali gruppi di clienti possono visualizzare questa specifica pagina CMS. |
| | Casella di controllo per il gruppo **"Visitatore"** | Varia | Se selezionata, gli utenti non loggati possono visualizzare la pagina. |
| | Casella di controllo per il gruppo **"Ospite"** | Varia | Se selezionata, gli utenti che hanno effettuato il checkout come ospiti possono visualizzare la pagina. |
| | Casella di controllo per il gruppo **"Cliente"** | Varia | Se selezionata, i clienti registrati standard possono visualizzare la pagina. |
| | Casella di controllo per il gruppo **"Grossista"** (o qualsiasi gruppo personalizzato) | Varia | Se selezionata, i clienti di questo specifico gruppo possono visualizzare la pagina. |
| | **Pulsante Salva** | N/A | Applica tutte le impostazioni di visibilità selezionate alle pagine CMS. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho limitato una pagina CMS, ma appare ancora nel mio menu piè di pagina/intestazione. Perché?**
R1: Questo modulo controlla l'*accesso* al contenuto della pagina, non la sua visibilità nei menu di navigazione. Se vuoi nascondere il link stesso a determinati gruppi, dovrai:
\* Rimuovere manualmente il link dai file del template del tuo tema (ad esempio, `footer.tpl`, `header.tpl`).
\* Utilizzare un modulo di gestione dei menu che offra visibilità basata sui gruppi per le voci di menu.
\* Se un cliente clicca su un link limitato, gli verrà comunque negato l'accesso al contenuto della pagina.

**D2: Un cliente è loggato, ma non riesce ancora a vedere una pagina che ho consentito per il suo gruppo. Cosa c'è che non va?**
R2:
\* **Svuota cache:** Inizia sempre svuotando la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
\* **Verifica assegnazione gruppo:** Ricontrolla che il cliente sia effettivamente assegnato al/ai gruppo/i di clienti corretto/i che hai consentito per la pagina CMS. Puoi verificarlo in **Clienti > Clienti** modificando il profilo del cliente.
\* **Configurazione modulo:** Rivedi la pagina di configurazione del modulo e assicurati che la casella di controllo del gruppo corretto sia selezionata per quella specifica pagina CMS.
\* **Cache del browser:** Chiedi al cliente di svuotare la cache del suo browser o di provare ad accedere alla pagina in una finestra di navigazione in incognito/privata.

**D3: Posso visualizzare un messaggio personalizzato invece di un errore "Pagina non trovata" quando l'accesso è negato?**
R3: Questo modulo, nella sua versione attuale, reindirizza alla pagina standard "Pagina non trovata" di PrestaShop. La personalizzazione di questo richiederebbe modifiche al tema o un modulo aggiuntivo che gestisca specificamente le pagine di errore personalizzate in base alla negazione dell'accesso.

**D4: Questo modulo rallenterà il mio negozio?**
R4: No, il modulo è molto leggero. Sovrascrive un controller core di PrestaShop per controllare i permessi del gruppo di clienti prima di caricare una pagina CMS. Questo controllo è efficiente e non dovrebbe influire in modo significativo sulle prestazioni del tuo negozio.

**D5: Ho aggiornato PrestaShop e ora il modulo non funziona. Cosa devo fare?**
R5:
\* **Controlla la versione del modulo:** Assicurati di avere l'ultima versione del modulo "Pagine CMS per gruppi" dal tuo account MyPresta.eu, compatibile con la tua nuova versione di PrestaShop.
\* **Reinstalla/Riconfigura:** A volte, dopo un importante aggiornamento di PrestaShop, i moduli potrebbero aver bisogno di essere reinstallati o riconfigurati. Prova a disinstallare e poi reinstallare il modulo (le tue impostazioni dovrebbero essere conservate, ma fai sempre un backup prima). Quindi, ricontrolla le tue impostazioni nella pagina di configurazione del modulo.
\* **Svuota cache:** Svuota sempre la cache di PrestaShop dopo qualsiasi aggiornamento o modifica del modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Pagine CMS per gruppi" opera sovrascrivendo il `CmsController` core nel front office di PrestaShop. Ciò gli consente di intercettare le richieste per le pagine CMS *prima* che vengano renderizzate e di applicare una logica di accesso personalizzata basata sui permessi del gruppo di clienti configurati nel back office del modulo. Il modulo memorizza la sua configurazione direttamente nella tabella `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `groupscms/override/controllers/front/CmsController.php`
        -   **Nome classe e classe padre**: `CmsController` (sovrascrive il `CmsController` core)
        -   **Responsabilità**: Questo è il componente critico. Estende il `CmsController` originale per aggiungere un metodo `init()`. All'interno di `init()`, recupera l'ID della pagina CMS corrente e controlla la configurazione del modulo (`Configuration::get('CMSG_CMS_ID_' . (int)$cms->id)`) per determinare quali gruppi di clienti sono autorizzati ad accedere. Se il cliente corrente (o visitatore) non fa parte di un gruppo consentito, lo reindirizza alla pagina "Pagina non trovata" (`$this->redirect_after = '404';`). Ciò garantisce che gli utenti non autorizzati non possano visualizzare contenuti CMS limitati.
-   **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli core (`classes/`)

Nessuno. Il modulo non definisce classi `ObjectModel` personalizzate. Interagisce direttamente con gli oggetti `CMS` e `Group` esistenti di PrestaShop e memorizza la sua configurazione in `ps_configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

Nessuno. Il modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `groupscms/css.css`
    -   **Ambito**: Stile del modulo di amministrazione del back-office.
    -   **Principali componenti UI e contenitori che stilizza**: Questo foglio di stile è probabilmente utilizzato per stilizzare la tabella di configurazione del modulo nel back office di PrestaShop, garantendo che abbia un aspetto coerente con il tema di amministrazione di PrestaShop. Potrebbe definire stili per le righe della tabella, le caselle di controllo o le etichette all'interno del modulo di configurazione del modulo.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema**: Selettori specifici si troverebbero all'interno del file, ma in genere mirerebbero a elementi all'interno dell'output `getContent()` del modulo, come `table.groupscms_table`, `tr.groupscms_row`, `input[type="checkbox"].groupscms_checkbox`, ecc.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Nessuno. Il modulo non renderizza contenuti tramite hook standard del front-office.
-   **Template admin (`views/templates/admin/`)**:

    -   `groupscms/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` del file principale del modulo (`groupscms.php`). Genera l'intera interfaccia di configurazione per il modulo nel back office di PrestaShop. Questo include la tabella che elenca tutte le pagine CMS e le caselle di controllo per ogni gruppo di clienti.
    -   `groupscms/cms.tpl`
        -   **Scopo**: Questo template è probabilmente un include o un parziale utilizzato all'interno di `admin.tpl` per renderizzare singole righe o sezioni relative alle pagine CMS all'interno della tabella di configurazione. Contenerebbe il ciclo per visualizzare ogni pagina CMS e le relative caselle di controllo del gruppo.
-   **Template front-office (`views/templates/front/`)**: Nessuno. Il modulo non aggiunge nuovi template front-office. Controlla l'accesso ai template delle pagine CMS esistenti.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle SQL personalizzate. Tutti i dati di configurazione sono memorizzati nella tabella `ps_configuration`.

    -   **Chiavi di configurazione**:
        -   `CMSG_CMS_ID_[CMS_ID]`: Memorizza una stringa separata da virgole di valori `group_id` per ogni pagina CMS. Ad esempio, `CMSG_CMS_ID_12` potrebbe memorizzare `"1,2,3"` indicando che i gruppi con ID 1, 2 e 3 hanno accesso alla pagina CMS con ID 12.
        -   `groupscms_many_page`: (Probabilmente un flag interno o un'impostazione legacy, non direttamente configurabile dall'utente).
        -   `mypresta_updates`, `update_`, `updatev_`: Queste sono chiavi comuni utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e il tracciamento delle versioni.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin imposta i suoi media (CSS/JS). | Utilizzato dal modulo per includere il suo foglio di stile `css.css` per la pagina di configurazione del back-office. |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` del Back Office. | Spesso utilizzato per includere CSS/JS globali dell'amministrazione o per i controlli degli aggiornamenti. Il modulo potrebbe usarlo per il suo meccanismo di aggiornamento. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Pagine CMS per gruppi", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
