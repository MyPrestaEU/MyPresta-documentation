---
title: "IVA 0% per gruppi di clienti selezionati - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop IVA 0% per gruppi di clienti selezionati di MyPresta.eu."
sidebar:
  label: "IVA 0% per gruppi di clienti selezionati"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo VAT 0% for selected groups of customers su MyPresta.eu](https://mypresta.eu/modules/ordering-process/vat-0-for-selected-groups-of-customers.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/vat-0-for-selected-groups-of-customers/)
>
> ---


# IVA 0% per gruppi di clienti selezionati

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono richieste per PrestaShop stesso e per i controlli di aggiornamento del modulo.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)
Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina di configurazione principale per il modulo "IVA 0% per gruppi di clienti selezionati". Questa pagina è divisa in diverse sezioni.

#### Scheda Impostazioni

Questa è la scheda principale dove definisci quali gruppi di clienti beneficeranno dell'IVA 0%.

**1. Gruppi di clienti che avranno IVA 0%**
-   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Ti consente di selezionare uno o più gruppi di clienti dal tuo negozio PrestaShop che saranno esenti da IVA.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando uno o più gruppi sono selezionati:* Qualsiasi cliente appartenente ad *almeno uno* dei gruppi selezionati avrà tutti i prezzi dei prodotti, la spedizione e i totali dell'ordine calcolati con IVA 0%.
    -   *Quando nessun gruppo è selezionato:* Il modulo non applicherà alcuna esenzione IVA e a tutti i clienti verrà addebitata l'IVA secondo le tue regole fiscali standard di PrestaShop.
-   **Valore consigliato:** Seleziona tutti i gruppi di clienti che intendi esentare dall'IVA (ad esempio, "Clienti all'ingrosso", "Clienti B2B").
-   **Scenario / esempio del commerciante:** Gestisci un negozio B2B. Hai un gruppo di clienti chiamato "Clienti all'ingrosso" che sono tutte aziende registrate IVA. Selezioneresti "Clienti all'ingrosso" da questo elenco. Quando un cliente di questo gruppo effettua il login, vedrà tutti i prezzi senza IVA.

**2. Seleziona regola fiscale**
-   **Cosa fa questa impostazione:** Questa opzione ti consente di specificare una particolare regola fiscale che il modulo dovrebbe utilizzare quando applica l'IVA 0%. Sebbene il modulo imposti l'aliquota fiscale a 0%, PrestaShop spesso richiede che una regola fiscale valida sia associata al calcolo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando viene selezionata una regola fiscale specifica:* Il modulo tenterà di utilizzare questa regola fiscale, ma con un'aliquota dello 0%, per i gruppi di clienti esenti. Questo può essere utile per garantire la compatibilità con altri moduli o configurazioni contabili specifiche che si aspettano che una regola fiscale sia sempre presente.
    -   *Quando "Nessuno" o nessuna regola specifica è selezionata (comportamento predefinito):* Il modulo gestirà l'applicazione dell'IVA 0% direttamente, spesso sovrascrivendo l'aliquota fiscale a 0% senza aderire strettamente a una regola fiscale predefinita, il che di solito è sufficiente.
-   **Valore consigliato:** Lascia come predefinito a meno che non si riscontrino problemi di compatibilità specifici con altri moduli o si abbia un requisito contabile molto particolare. Se ne selezioni uno, scegli una regola fiscale generica dello 0% se ne hai una, o una regola fiscale standard che il modulo può poi sovrascrivere a 0%.
-   **Scenario / esempio del commerciante:** Il tuo commercialista richiede che tutte le transazioni, anche quelle con IVA 0%, siano collegate a un ID di regola fiscale specifico per scopi di rendicontazione. Potresti creare una regola fiscale "IVA 0% (Esente)" in PrestaShop e selezionarla qui.

#### Scheda Riparazione Hook
Questa scheda è per la risoluzione avanzata dei problemi e per garantire che gli hook del modulo siano correttamente registrati.

-   **Cosa fa questa impostazione:** Questa sezione fornisce strumenti per registrare nuovamente gli hook del modulo nel caso in cui diventino non registrati o corrotti, cosa che a volte può accadere dopo modifiche al tema, conflitti tra moduli o problemi di database.
-   **Effetto della modifica di questa impostazione:**
    -   *Cliccando su "Ripara hook":* Questa azione tenterà di registrare nuovamente tutti gli hook necessari che il modulo utilizza per funzionare correttamente. Se il modulo non funzionava come previsto (ad esempio, l'IVA non veniva rimossa), questo potrebbe risolvere il problema.
-   **Valore consigliato:** Utilizza questa opzione solo se sospetti che il modulo non funzioni correttamente (ad esempio, l'IVA viene ancora addebitata ai gruppi esenti) e dopo aver confermato che le tue impostazioni principali sono corrette.
-   **Scenario / esempio del commerciante:** Hai appena aggiornato il tuo tema PrestaShop e ora ai tuoi clienti esenti IVA viene improvvisamente addebitata l'IVA. Hai controllato le impostazioni del tuo gruppo e sono corrette. Cliccando su "Ripara hook" qui potresti risolvere il problema sottostante.

#### Scheda Aggiornamenti
Questa scheda fornisce informazioni sugli aggiornamenti del modulo.

-   **Cosa fa questa impostazione:** Questa sezione controlla la disponibilità di aggiornamenti per il modulo e fornisce informazioni sulla tua versione attuale.
-   **Effetto della modifica di questa impostazione:**
    -   *Controllo degli aggiornamenti:* Ti informa se è disponibile una versione più recente del modulo, consentendoti di mantenere il tuo modulo aggiornato con le ultime funzionalità e correzioni di bug.
-   **Valore consigliato:** Controlla periodicamente questa scheda per assicurarti di utilizzare l'ultima versione per prestazioni e sicurezza ottimali.
-   **Scenario / esempio del commerciante:** Vuoi assicurarti che il tuo negozio esegua sempre il software più stabile e sicuro. Visiti questa scheda una volta al mese per vedere se ci sono nuovi aggiornamenti per i tuoi moduli MyPresta.eu.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Pagina di Configurazione del Modulo | **Gruppi di clienti che avranno IVA 0%** | Seleziona i gruppi pertinenti (ad esempio, "Clienti all'ingrosso") | Definisce quali gruppi di clienti avranno IVA 0% applicata a tutti i prezzi e totali. |
| Pagina di Configurazione del Modulo | **Seleziona regola fiscale** | Lascia come predefinito (o seleziona una regola fiscale 0% se necessaria per la contabilità) | Associa il calcolo IVA 0% a una regola fiscale specifica per compatibilità o rendicontazione. |
| Scheda Riparazione Hook | **Pulsante Ripara hook** | Utilizzare solo per la risoluzione dei problemi | Registra nuovamente gli hook del modulo per risolvere problemi di funzionalità (ad esempio, IVA non rimossa). |
| Scheda Aggiornamenti | **Verifica aggiornamenti** | Controlla periodicamente | Informa sugli aggiornamenti del modulo disponibili per nuove funzionalità e correzioni di bug. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: L'IVA viene ancora addebitata anche se ho selezionato il gruppo di clienti.**
R1:
*   **Verifica Assegnazione Gruppo:** Assicurati che il cliente con cui stai testando sia effettivamente assegnato a uno dei gruppi esenti IVA selezionati. Accedi come cliente, vai ai dettagli del suo account o controlla nel Back Office sotto `Clienti > Clienti`.
*   **Configurazione Modulo:** Ricontrolla che i gruppi corretti siano selezionati nella pagina di configurazione del modulo (`Moduli > Gestione moduli > Configura` per "IVA 0% per gruppi di clienti selezionati").
*   **Cache:** Cancella la cache di PrestaShop (sotto `Parametri Avanzati > Prestazioni`) e la cache del tuo browser. A volte possono essere visualizzati dati vecchi.
*   **Riparazione Hook:** Vai alla scheda "Riparazione hook" nella configurazione del modulo e clicca sul pulsante "Ripara hook". Questo può risolvere problemi in cui i punti di integrazione del modulo con PrestaShop potrebbero essere diventati non registrati.

**D2: Questo modulo influenzerà le mie regole fiscali esistenti per i clienti non esenti?**
R2: No, questo modulo è progettato per applicare l'IVA 0% *solo* ai clienti appartenenti ai gruppi specifici che selezioni. Per tutti gli altri clienti, le tue regole fiscali e configurazioni standard di PrestaShop si applicheranno come di consueto.

**D3: Questo modulo funziona anche per i costi di spedizione?**
R3: Sì, il modulo è progettato per applicare l'IVA 0% a tutti gli aspetti dell'ordine, inclusi i prezzi dei prodotti, i costi di spedizione e qualsiasi altro elemento tassabile, risultando in un valore totale dell'ordine con IVA 0% per i gruppi di clienti selezionati.

**D4: Ho un tema personalizzato. Questo modulo funzionerà con esso?**
R4: Sì, questo modulo funziona modificando la logica di calcolo delle tasse di base di PrestaShop tramite hook, piuttosto che alterando direttamente i template del front-office. Pertanto, dovrebbe essere compatibile con la maggior parte dei temi personalizzati senza problemi. Se riscontri problemi di visualizzazione (ad esempio, i prezzi non si aggiornano), è probabile che si tratti di un problema di cache o di un conflitto con un altro modulo che modifica pesantemente i calcoli delle tasse.

**D5: Come traduco il testo del modulo in altre lingue?**
R5: Se il modulo introduce nuove stringhe di testo (anche se questo modulo funziona principalmente in background), puoi tradurle tramite l'interfaccia di traduzione di PrestaShop:
1.  Vai su `Internazionale > Traduzioni`.
2.  Seleziona "Traduzioni dei moduli installati".
3.  Scegli il tuo tema, la lingua e quindi seleziona "IVA 0% per gruppi di clienti selezionati" dall'elenco dei moduli.
4.  Potrai quindi modificare qualsiasi stringa traducibile.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura
Il modulo "IVA 0% per gruppi di clienti selezionati" opera sfruttando il sistema di hook di PrestaShop per intercettare e modificare i calcoli fiscali in varie fasi del processo di ordinazione. Utilizza principalmente gli hook `actionTaxManager` e `actionProductPriceCalculation` per regolare dinamicamente l'aliquota fiscale allo 0% per i clienti appartenenti a gruppi specifici. Include anche una classe `TaxManager` personalizzata per gestire la logica di override delle tasse. Il modulo segue una struttura standard di modulo PrestaShop, con un file di modulo principale, una classe dedicata per la gestione delle tasse e template Smarty per la sua configurazione Back Office.

### 4.2 Controller (`controllers/`)
Questo modulo non utilizza controller Front-Office o Back-Office Admin personalizzati. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

-   **`groupvat/classes/GroupvatTaxManager.php`**
    *   **Nome Classe:** `GroupvatTaxManager`
    *   **Classe Padre:** `TaxManager` (la classe `TaxManager` core di PrestaShop)
    *   **Responsabilità:** Questa classe è il cuore della funzionalità del modulo. Estende il `TaxManager` predefinito di PrestaShop per sovrascriverne il comportamento. Il suo metodo principale, `getTaxCalculator()`, è cruciale. Quando un cliente viene identificato come appartenente a un gruppo esente IVA, questa classe assicura che il `TaxCalculator` restituisca un'aliquota fiscale dello 0%, rimuovendo efficacemente l'IVA dai prezzi. Contiene anche la logica per verificare se il cliente corrente si trova in uno dei gruppi esenti configurati.
    *   **Metodi Chiave:**
        *   `getTaxCalculator(array $params)`: Sovrascrive il calcolatore fiscale predefinito per restituire un'aliquota fiscale dello 0% se il cliente si trova in un gruppo esente.
        *   `isCustomerInGroup(int $id_customer)`: Metodo di supporto per determinare se un dato ID cliente appartiene a uno qualsiasi dei gruppi esenti IVA configurati.

-   **`groupvat/classes/index.php`**
    *   **Responsabilità:** File `index.php` vuoto standard per prevenire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)
Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di Stile CSS (`views/css/`)
Questo modulo non include alcun file CSS personalizzato. Lo stile per la configurazione del Back Office è gestito dal tema admin predefinito di PrestaShop.

### 4.6 Struttura dei Template Smarty (`views/templates/`)

-   **`groupvat/views/templates/admin/configure.tpl`**
    *   **Ambito:** Configurazione admin del Back Office.
    *   **Scopo:** Questo è il template principale per la pagina di configurazione del modulo, renderizzato da `getContent()` in `groupvat.php`. Include altri template per sezioni specifiche come la selezione del gruppo di clienti e la riparazione degli hook. Di solito racchiude l'intero modulo di configurazione.

-   **`groupvat/views/templates/admin/customerGroups.tpl`**
    *   **Ambito:** Configurazione admin del Back Office.
    *   **Scopo:** Questo template renderizza la sezione in cui il commerciante seleziona i gruppi di clienti che avranno IVA 0%. Visualizza un elenco di gruppi di clienti disponibili con caselle di controllo.
    *   **Variabili:** Probabilmente utilizza `$groups` (array di gruppi di clienti), `$selected_groups` (array di ID di gruppi attualmente selezionati), `$tax_rules` (array di regole fiscali disponibili), `$selected_tax_rule` (ID della regola fiscale attualmente selezionata).

-   **`groupvat/views/templates/admin/hooksRepair.tpl`**
    *   **Ambito:** Configurazione admin del Back Office.
    *   **Scopo:** Questo template renderizza la sezione "Riparazione hook", fornendo un pulsante per registrare nuovamente gli hook del modulo.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:
    *   Questo modulo non crea tabelle di database personalizzate.
    *   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop.
        *   `groupvat_groups`: Memorizza un elenco separato da virgole di ID di gruppi di clienti selezionati per l'esenzione IVA.
        *   `groupvat_tax`: Memorizza l'ID della regola fiscale selezionata (se presente).
        *   `mypresta_updates`: Memorizza informazioni relative agli aggiornamenti del modulo.

-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
|---|---|---|
| `actionDispatcher` | Prima che un controller venga spedito. | Utilizzato per potenzialmente sovrascrivere o modificare il comportamento di spedizione, anche se spesso utilizzato per la configurazione generale. |
| `ActionDispatcher` | (Alias di `actionDispatcher`) | Come sopra. |
| `actionCartGetPackageShippingCost` | Durante il calcolo dei costi di spedizione per un pacchetto nel carrello. | Cruciale per garantire che i costi di spedizione siano calcolati anch'essi con IVA 0% per i gruppi esenti. |
| `displayTaxManager` | (Deprecato/meno comune) | Storicamente utilizzato per visualizzare informazioni relative alle tasse. |
| `ActionGetProductPropertiesAfter` | Dopo il recupero delle proprietà del prodotto. | Consente la modifica dei dati del prodotto, inclusi prezzo e tasse, prima della visualizzazione. |
| `taxManager` | (Deprecato/meno comune) | Storicamente utilizzato per la gestione delle tasse. |
| `ActionAuthentication` | Dopo che un cliente si autentica (effettua il login). | Può essere utilizzato per impostare variabili di sessione o eseguire azioni basate sul gruppo di clienti dopo il login. |
| `ActionTaxManager` | Quando la classe `TaxManager` viene istanziata o i suoi metodi vengono chiamati. | **Hook primario per questo modulo.** Consente al modulo di iniettare il suo `GroupvatTaxManager` personalizzato o modificare la logica di calcolo delle tasse. |
| `ActionPresentCart` | Prima che il carrello venga presentato all'utente. | Consente la modifica dei dati del carrello, inclusi prezzi e totali, prima del rendering. |
| `ActionProductPriceCalculation` | Durante il processo di calcolo del prezzo del prodotto. | **Hook primario per questo modulo.** Consente al modulo di modificare l'aliquota fiscale applicata ai prezzi dei prodotti. |
| `actionGetProductPropertiesAfter` | (Alias di `ActionGetProductPropertiesAfter`) | Come sopra. |
| `ActionFilterDeliveryOptionList` | Prima che venga visualizzato l'elenco delle opzioni di consegna. | Consente la modifica delle opzioni di consegna, potenzialmente influenzando i loro prezzi (e quindi le tasse). |

## 5. Supporto Ufficiale e Aggiornamenti
Per supporto ufficiale, aggiornamenti e le ultime versioni del modulo "IVA 0% per gruppi di clienti selezionati", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
