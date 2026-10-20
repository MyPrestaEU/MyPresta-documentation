---
title: "Reindirizzamenti SEO 301, 302, 303 - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Seo Redirects 301, 302, 303 di MyPresta.eu."
sidebar:
  label: "Reindirizzamenti SEO 301, 302, 303 - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Seo Redirects 301, 302, 303 su MyPresta.eu](https://mypresta.eu/modules/seo/seo-redirects-301-302-303.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/seo/seo-redirects-301-302-303/)
>
> ---


# Reindirizzamenti SEO 301, 302, 303

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Reindirizzamenti SEO 301, 302, 303" fornisce una suite completa di strumenti, accessibile tramite un menu dedicato nel Back Office di PrestaShop. Dopo l'installazione, troverai una nuova voce di menu, tipicamente sotto **"SEO & SEM"** o **"Parametri avanzati"**, denominata **"Reindirizzamenti SEO"** o simile. Questo menu conterrà diverse sotto-voci, ognuna delle quali conduce a una schermata di configurazione specifica.

### 2.1 Pagina di configurazione principale del modulo (Back Office > Moduli > Configura)

Questa schermata di configurazione iniziale (accessibile cliccando su "Configura" dopo l'installazione) fornisce le impostazioni generali per il modulo.

- **Cosa fa questa impostazione:** Questa schermata contiene tipicamente l'attivazione di base del modulo e forse alcune impostazioni globali.
- **Effetto della modifica di questa impostazione:**
  - *Abilitazione del modulo:* Attiva la logica di reindirizzamento in tutto il tuo negozio.
  - *Disabilitazione del modulo:* Interrompe tutti i reindirizzamenti gestiti da questo modulo.
- **Valore consigliato:** **Abilitato** affinché il modulo funzioni.
- **Scenario/esempio per il commerciante:** Dopo l'installazione, vorrai assicurarti che il modulo sia attivo in modo che possa iniziare a gestire i tuoi reindirizzamenti.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo organizza le sue potenti funzionalità in diverse sezioni distinte, ciascuna gestita da un controller amministrativo dedicato. Le troverai sotto la voce di menu principale "Reindirizzamenti SEO" nel Back Office di PrestaShop.

#### 2.2.1 Dashboard (AdminSeoRedirectDashboardController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Dashboard**
Questa schermata fornisce una panoramica delle prestazioni e dello stato dei tuoi reindirizzamenti. È il tuo hub centrale per comprendere rapidamente come stanno funzionando i tuoi reindirizzamenti.

- **Azioni e impostazioni disponibili:**
  - **Panoramica dei reindirizzamenti:** Mostra statistiche come il numero totale di reindirizzamenti attivi, i reindirizzamenti creati e forse il numero di volte in cui i reindirizzamenti sono stati attivati.
  - **Cronologia/Attività dei reindirizzamenti:** Potrebbe visualizzare i tentativi di reindirizzamento recenti, inclusi gli errori 404 rilevati e gli URL reindirizzati con successo.
  - **SEOR\_DASHBOARD\_PERIOD:** Questa impostazione probabilmente controlla il periodo di tempo per il quale vengono visualizzate le statistiche della dashboard (es. ultimi 7 giorni, ultimi 30 giorni, sempre).
- **Effetto delle modifiche:** La modifica del periodo della dashboard aggiornerà le statistiche mostrate per riflettere l'intervallo di tempo selezionato, aiutandoti ad analizzare le tendenze su diverse durate.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente questa dashboard per monitorare lo stato dei tuoi reindirizzamenti, identificare eventuali nuovi errori 404 che richiedono attenzione e assicurarti che i tuoi sforzi SEO stiano dando i loro frutti.

#### 2.2.2 Elenco reindirizzamenti (AdminSeoRedirectListController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Elenco reindirizzamenti**
Questo è il cuore del modulo, dove crei, modifichi e gestisci le singole regole di reindirizzamento.

- **Azioni e impostazioni disponibili:**
  - **Aggiungi nuovo reindirizzamento:** Un modulo per creare una nuova regola di reindirizzamento.
    - **Vecchio URL (URL sorgente):** L'URL esatto che non è più valido o da cui si desidera reindirizzare.
    - **Nuovo URL (URL di destinazione):** L'URL esatto a cui devono essere inviati i visitatori e i motori di ricerca.
    - **Tipo di reindirizzamento:**
      - **301 Reindirizzamento permanente:** Indica ai motori di ricerca che la pagina è stata spostata in modo permanente. Questo è il tipo più comune e SEO-friendly, che trasferisce quasi tutto il "link juice". Usalo quando una pagina è sparita per sempre e sostituita da un'altra.
      - **302 Trovato / Reindirizzamento temporaneo:** Indica ai motori di ricerca che lo spostamento è temporaneo. Usalo se ti aspetti che il vecchio URL diventi nuovamente attivo in futuro (es. per prodotti stagionali, test A/B). Viene trasferito meno valore SEO.
      - **303 Vedi altro:** Simile al 302, spesso usato dopo una richiesta POST per reindirizzare a una nuova pagina per prevenire la ri-sottomissione. Meno comune per i reindirizzamenti SEO generali.
    - **Stato (Abilitato/Disabilitato):** Ti consente di attivare o disattivare una specifica regola di reindirizzamento senza eliminarla.
  - **Modifica/Elimina reindirizzamenti:** Modifica le regole esistenti o rimuovile.
  - **Cerca/Filtra:** Trova reindirizzamenti specifici per vecchio o nuovo URL.
  - **Azioni di massa:** Applica azioni (abilita, disabilita, elimina) a più reindirizzamenti selezionati.
- **Effetto delle modifiche:**
  - *Aggiunta di un reindirizzamento:* Inizia immediatamente a reindirizzare il traffico dal vecchio URL al nuovo secondo il tipo specificato.
  - *Modifica di un reindirizzamento:* Aggiorna il comportamento di reindirizzamento.
  - *Eliminazione di un reindirizzamento:* Rimuove la regola, potenzialmente portando a errori 404 se il vecchio URL è ancora accessibile.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Ogni volta che rimuovi un prodotto, cambi l'URL di una categoria o aggiorni l'indirizzo di una pagina, crea immediatamente un reindirizzamento 301 dal vecchio URL al nuovo.
  2. Controlla regolarmente i tuoi log degli errori 404 (es. in Google Search Console o nella sezione Audit del modulo) e aggiungi reindirizzamenti per i link interrotti frequentemente incontrati.

#### 2.2.3 Importa reindirizzamenti (AdminSeoRedirectImportController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Importa**
Questa schermata ti consente di caricare un file (tipicamente CSV) contenente molte regole di reindirizzamento, rendendo facile la gestione di un gran numero di reindirizzamenti.

- **Azioni e impostazioni disponibili:**
  - **Carica file CSV:** Seleziona un file dal tuo computer. Il file dovrebbe contenere colonne per "Vecchio URL", "Nuovo URL" e "Tipo di reindirizzamento".
  - **IV\_COL\_DELIMITER:** Questa impostazione definisce il carattere utilizzato per separare le colonne nel tuo file CSV (es. virgola, punto e virgola, tabulazione).
  - **SEOR\_SAFE\_ROLLOUT:** Questa impostazione probabilmente controlla una "modalità sicura" per le importazioni, magari consentendoti di visualizzare in anteprima le modifiche o abilitare i reindirizzamenti gradualmente per prevenire problemi accidentali.
- **Effetto delle modifiche:**
  - *Importazione di un file:* Crea più regole di reindirizzamento in blocco, risparmiando un notevole sforzo manuale.
  - *Modifica del delimitatore:* Assicura che il modulo analizzi correttamente il tuo file CSV.
  - *Rollout sicuro:* Se abilitato, potrebbe consentire la distribuzione a fasi dei reindirizzamenti, dandoti il tempo di verificare prima che vadano online.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa funzione quando migri un negozio, esegui una ristrutturazione importante del sito o pulisci un gran numero di errori 404 accumulati. Testa sempre un piccolo lotto prima, se possibile.

#### 2.2.4 Audit (AdminSeoRedirectAuditController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Audit**
Lo strumento di audit ti aiuta a identificare i link interrotti (errori 404) sul tuo sito web, che sono i principali candidati per il reindirizzamento.

- **Azioni e impostazioni disponibili:**
  - **Scansiona per errori 404:** Avvia una scansione del tuo sito web (o di una parte specifica) per trovare pagine che restituiscono uno stato 404.
  - **Elenco di errori 404:** Visualizza una tabella dei link interrotti rilevati, spesso con la pagina di riferimento (dove è stato trovato il link interrotto) e il numero di volte in cui è stato acceduto.
  - **Opzione per creare reindirizzamento:** Crea direttamente una regola di reindirizzamento per un errore 404 rilevato da questa schermata.
- **Effetto delle modifiche:** L'esecuzione di un audit ti aiuta a trovare e risolvere proattivamente i problemi che danneggiano il SEO e l'esperienza utente.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Esegui un audit periodicamente (es. mensilmente) per rilevare nuovi link interrotti che potrebbero apparire a causa di modifiche ai contenuti o link esterni. Dai priorità alla correzione dei 404 che vengono frequentemente acceduti o collegati da pagine importanti.

#### 2.2.5 Cronologia (AdminSeoRedirectHistoryController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Cronologia**
Questa schermata registra tutti gli eventi di reindirizzamento, fornendo un chiaro registro di quando e come vengono utilizzati i reindirizzamenti.

- **Azioni e impostazioni disponibili:**
  - **Tabella degli eventi di reindirizzamento:** Mostra dettagli come l'URL originale richiesto, il nuovo URL a cui è stato reindirizzato, il tipo di reindirizzamento, la data/ora e potenzialmente l'agente utente o l'indirizzo IP.
  - **Cerca/Filtra:** Ti aiuta a trovare eventi di reindirizzamento specifici.
- **Effetto delle modifiche:** Questo è uno strumento di reporting e diagnostica. Non modifica il comportamento del negozio ma fornisce preziose informazioni su come stanno funzionando i tuoi reindirizzamenti.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza la cronologia per verificare che reindirizzamenti specifici funzionino come previsto, risolvere cicli di reindirizzamento inaspettati o analizzare i modelli di traffico verso le pagine reindirizzate.

#### 2.2.6 Impostazioni (AdminSeoRedirectSettingsController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Impostazioni**
Questa sezione contiene opzioni di configurazione avanzate che controllano il comportamento globale del modulo.

- **Azioni e impostazioni disponibili:**
  - **seor\_pos\_exclude:**
    - **Cosa fa questa impostazione:** Ti consente di escludere URL o pattern specifici dall'essere reindirizzati o controllati automaticamente. Questo è utile per le pagine che vuoi intenzionalmente restituiscano un 404 (es. vecchie pagine di test).
    - **Effetto della modifica di questa impostazione:**
      - *Aggiunta di URL:* Il modulo ignorerà questi URL quando esegue reindirizzamenti o audit.
      - *Rimozione di URL:* Questi URL saranno soggetti alla logica di reindirizzamento del modulo.
    - **Valore consigliato:** Mantieni questo elenco aggiornato con tutti gli URL che dovrebbero essere realmente 404 e non reindirizzati.
    - **Scenario/esempio per il commerciante:** Potresti avere una pagina di destinazione temporanea che desideri rimuovere completamente e non vuoi che il modulo tenti di reindirizzarla.
  - **seor\_unavorder:**
    - **Cosa fa questa impostazione:** Probabilmente controlla come il modulo gestisce i reindirizzamenti per prodotti non disponibili o esauriti.
    - **Effetto della modifica di questa impostazione:**
      - *Abilitato:* Il modulo potrebbe reindirizzare automaticamente le pagine di prodotti non disponibili a una pagina di categoria o a una pagina personalizzata "prodotto non trovato".
      - *Disabilitato:* Le pagine di prodotti non disponibili restituiranno un errore 404 standard.
    - **Valore consigliato:** **Abilitato** per migliorare l'esperienza utente e il SEO per i prodotti fuori produzione.
    - **Scenario/esempio per il commerciante:** Quando un prodotto viene rimosso dal tuo catalogo, puoi reindirizzare automaticamente il suo vecchio URL alla sua categoria padre o a un prodotto simile, invece di mostrare un 404.
  - **seor\_pos\_category, seor\_pins\_category, seor\_pos\_exclude\_cat, seor\_oos\_cat\_include, seor\_emptycat\_exclusions, seor\_pos, seor\_emptycat:**
    - **Cosa fanno queste impostazioni:** Queste sono probabilmente un gruppo di impostazioni relative a come il modulo gestisce i reindirizzamenti per le categorie, in particolare le categorie vuote, i prodotti esauriti all'interno delle categorie o esclusioni di categorie specifiche.
      - `seor_pos_category`: Impostazione generale per i reindirizzamenti di categoria.
      - `seor_pins_category`: Potrebbe riguardare categorie "bloccate" o un comportamento specifico di reindirizzamento di categoria.
      - `seor_pos_exclude_cat`: Esclude categorie specifiche dalla logica di reindirizzamento automatico.
      - `seor_oos_cat_include`: Include i prodotti esauriti nella logica di reindirizzamento di categoria.
      - `seor_emptycat_exclusions`: Esclude categorie vuote specifiche dall'essere reindirizzate.
      - `seor_pos`: Impostazione generale per i reindirizzamenti di posizione prodotto/categoria.
      - `seor_emptycat`: Controlla i reindirizzamenti automatici per le categorie vuote.
    - **Effetto della modifica di queste impostazioni:** Queste impostazioni consentono un controllo granulare su come gli URL delle categorie vengono gestiti quando le categorie sono vuote, i prodotti sono esauriti o le categorie vengono rimosse. Possono prevenire i 404 per i contenuti dinamici.
    - **Valore consigliato:** Rivedi queste impostazioni in base alle esigenze specifiche del tuo negozio. Ad esempio, il reindirizzamento automatico delle categorie vuote alla loro categoria padre può essere vantaggioso.
    - **Scenario/esempio per il commerciante:** Se una categoria diventa vuota perché tutti i prodotti sono esauriti, potresti voler reindirizzare automaticamente il suo URL alla categoria padre per evitare un 404.

#### 2.2.7 Strumenti (AdminSeoRedirectToolsController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Strumenti**
Questa sezione fornisce funzioni di utilità, potenzialmente inclusa l'integrazione con servizi esterni.

- **Azioni e impostazioni disponibili:**
  - **SEOR\_GSC\_TOKEN, SEOR\_GSC\_SITE:** Queste impostazioni suggeriscono l'integrazione con Google Search Console (GSC).
    - **Cosa fanno queste impostazioni:** Ti consentono di connettere il tuo negozio PrestaShop al tuo account Google Search Console. Ciò potrebbe consentire al modulo di recuperare automaticamente gli errori 404 segnalati da Google o di inviare sitemap/reindirizzamenti a GSC.
    - **Effetto della modifica di questa impostazione:**
      - *Configurazione GSC:* Abilita lo scambio di dati tra il tuo negozio e Google Search Console, potenzialmente automatizzando la scoperta di link interrotti e migliorando il tuo flusso di lavoro SEO.
      - *Non configurato:* Dovrai controllare manualmente GSC per i 404 e aggiungere i reindirizzamenti.
    - **Valore consigliato:** Configura se utilizzi attivamente Google Search Console per il SEO del tuo negozio.
    - **Scenario/esempio per il commerciante:** Invece di controllare manualmente Google Search Console per nuovi errori 404, il modulo potrebbe recuperarli direttamente, consentendoti di creare reindirizzamenti più rapidamente.

#### 2.2.8 Statistiche (AdminSeoRedirectStatsController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Statistiche**
Questa schermata fornisce statistiche relative alla salute generale del tuo negozio, potenzialmente inclusi l'impatto dei reindirizzamenti.

- **Azioni e impostazioni disponibili:**
  - **PS\_SHOP\_ENABLE:** Questa è una chiave di configurazione standard di PrestaShop che indica se il tuo negozio è attualmente abilitato o in modalità di manutenzione. Il modulo potrebbe visualizzarla come un rapido controllo dello stato.
  - **Metriche di performance dei reindirizzamenti:** Potrebbe mostrare dati aggregati su quanti reindirizzamenti si sono verificati, quali tipi sono più comuni e il loro impatto complessivo.
- **Effetto delle modifiche:** Questa è principalmente una schermata informativa. Ti aiuta a comprendere le prestazioni complessive e l'utilizzo del modulo.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Rivedi periodicamente queste statistiche per comprendere il volume dei reindirizzamenti e assicurarti che il modulo stia contribuendo attivamente a un sito sano.

#### 2.2.9 Controller API (AdminSeoRedirectApiController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > API** (o simile, potrebbe essere una sezione tecnica)
Questa schermata è per utenti avanzati o sviluppatori che desiderano interagire con la funzionalità di reindirizzamento del modulo in modo programmatico.

- **Azioni e impostazioni disponibili:**
  - **Documentazione API:** Fornisce informazioni su come utilizzare l'API del modulo per creare, recuperare, aggiornare o eliminare reindirizzamenti da applicazioni esterne o script personalizzati.
  - **Gestione chiavi API:** Consente di generare e gestire chiavi API per un accesso sicuro.
- **Effetto delle modifiche:** La configurazione dell'accesso API consente a sistemi esterni (es. un sistema di gestione dell'inventario personalizzato, uno strumento SEO di terze parti) di interagire con i tuoi reindirizzamenti.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questo solo se hai esigenze di integrazione specifiche e competenze tecniche.

#### 2.2.10 Controller CLI (AdminSeoRedirectCliController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > CLI** (o simile, potrebbe essere una sezione tecnica)
Questa schermata fornisce informazioni e strumenti per operazioni da interfaccia a riga di comando (CLI) relative al modulo.

- **Azioni e impostazioni disponibili:**
  - **Documentazione comandi CLI:** Spiega come eseguire attività specifiche del modulo dalla riga di comando del tuo server (es. `php bin/console seoredirect:audit`).
  - **Configurazione Cron Job:** Fornisce istruzioni per la configurazione di cron job per automatizzare attività come audit regolari o pulizie di reindirizzamenti.
- **Effetto delle modifiche:** L'utilizzo degli strumenti CLI consente l'automazione delle attività, particolarmente utile per negozi di grandi dimensioni o operazioni complesse.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Consulta questa sezione se desideri automatizzare attività come audit 404 giornalieri o controlli periodici dello stato dei reindirizzamenti utilizzando cron job del server.

#### 2.2.11 Controller di ricerca (AdminSeoredirectSearchController)

**Nome schermata e posizione menu:** **Reindirizzamenti SEO > Ricerca** (o integrato in altre schermate)
Questo controller probabilmente alimenta funzionalità di ricerca avanzate all'interno delle varie griglie ed elenchi del modulo, aiutandoti a trovare rapidamente reindirizzamenti specifici, errori 404 o voci di cronologia.

- **Azioni e impostazioni disponibili:**
  - **Filtri di ricerca avanzati:** Fornisce opzioni di ricerca più granulari oltre la semplice ricerca testuale, possibilmente includendo intervalli di date, tipi di reindirizzamento o stato.
- **Effetto delle modifiche:** Migliora la tua capacità di navigare e gestire grandi set di dati all'interno del modulo.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questo quando hai bisogno di individuare rapidamente una specifica regola di reindirizzamento o analizzare un sottoinsieme dei tuoi dati.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Dashboard** | `SEOR_DASHBOARD_PERIOD` | Ultimi 30 giorni | Controlla il periodo di tempo per le statistiche della dashboard. |
| **Elenco reindirizzamenti** | Vecchio URL | N/A | L'URL da cui reindirizzare. |
|  | Nuovo URL | N/A | L'URL a cui reindirizzare. |
|  | Tipo di reindirizzamento | 301 Permanente | Tipo di reindirizzamento (301, 302, 303). Il 301 è il migliore per il SEO. |
|  | Stato | Abilitato | Attiva/disattiva una specifica regola di reindirizzamento. |
| **Importa** | `IV_COL_DELIMITER` | Virgola (`,`) | Carattere che separa le colonne nel file CSV di importazione. |
|  | `SEOR_SAFE_ROLLOUT` | No | Abilita una modalità sicura per le importazioni (es. distribuzione a fasi). |
| **Impostazioni** | `seor_pos_exclude` | Vuoto | Elenco di URL/pattern da escludere da reindirizzamento/audit. |
|  | `seor_unavorder` | Sì | Reindirizza automaticamente i prodotti non disponibili. |
|  | `seor_pos_category` | Sì | Impostazione generale per i reindirizzamenti di categoria. |
|  | `seor_pins_category` | No | Comportamento specifico di reindirizzamento di categoria. |
|  | `seor_pos_exclude_cat` | Vuoto | Esclude categorie specifiche dal reindirizzamento automatico. |
|  | `seor_oos_cat_include` | Sì | Include i prodotti esauriti nella logica di reindirizzamento di categoria. |
|  | `seor_emptycat_exclusions` | Vuoto | Esclude categorie vuote specifiche dall'essere reindirizzate. |
|  | `seor_pos` | Sì | Impostazione generale per i reindirizzamenti di posizione prodotto/categoria. |
|  | `seor_emptycat` | Sì | Controlla i reindirizzamenti automatici per le categorie vuote. |
| **Strumenti** | `SEOR_GSC_TOKEN` | Vuoto | Token API di Google Search Console per l'integrazione. |
|  | `SEOR_GSC_SITE` | Vuoto | L'URL del tuo sito web registrato in Google Search Console. |
| **Statistiche** | `PS_SHOP_ENABLE` | Sì | Visualizza lo stato attuale del negozio (abilitato/manutenzione). |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Ho aggiunto un reindirizzamento, ma non funziona. Cosa devo fare?**
R1:

- **Controlla gli errori di battitura:** Assicurati che "Vecchio URL" e "Nuovo URL" siano digitati esattamente correttamente nell'Elenco reindirizzamenti.
- **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache". Svuota anche la cache del tuo browser.
- **Stato del modulo:** Assicurati che il modulo "Reindirizzamenti SEO 301, 302, 303" sia abilitato in **Moduli > Gestione moduli**.
- **Ordine di reindirizzamento:** Se hai più moduli di reindirizzamento o regole `.htaccess`, potrebbe esserci un conflitto. Questo modulo di solito ha la precedenza, ma controlla il file `.htaccess` del tuo server per eventuali regole in conflitto.
- **URL completo vs. URL relativo:** Assicurati di utilizzare il formato corretto per i tuoi URL (es. `/vecchia-pagina.html` per percorsi relativi, o `https://www.iltuonegozio.com/vecchia-pagina.html` per percorsi completi, a seconda di come il modulo li prevede).

**D2: Questo modulo rallenterà il mio negozio?**
R2: Il modulo è progettato per essere efficiente. I reindirizzamenti avvengono in una fase molto precoce del processo di richiesta, minimizzando l'impatto. Tuttavia, avere decine di migliaia di reindirizzamenti potrebbe aggiungere un piccolo overhead. L'audit e la pulizia regolari dei reindirizzamenti non necessari (es. vecchi 302 temporanei) possono aiutare a mantenere le prestazioni.

**D3: Come gestisco i reindirizzamenti per i prodotti temporaneamente esauriti?**
R3:

- Per situazioni temporanee, un **Reindirizzamento temporaneo 302** a una pagina di categoria pertinente o a una pagina "avvisami quando disponibile" è appropriato. Questo indica ai motori di ricerca che il prodotto potrebbe tornare.
- Controlla la schermata **Impostazioni** per opzioni come `seor_unavorder` o `seor_oos_cat_include`, che potrebbero offrire una gestione automatica per i prodotti esauriti.

**D4: Posso usare i caratteri jolly nelle mie regole di reindirizzamento (es. reindirizzare tutte le pagine in una vecchia directory)?**
R4: La documentazione o l'interfaccia del modulo specificheranno se supporta espressioni regolari o caratteri jolly (come `*`). Se lo fa, puoi creare regole potenti come `/vecchia-categoria/*` a `/nuova-categoria/$1` (dove `$1` cattura il resto dell'URL). In caso contrario, dovrai elencare ogni reindirizzamento individualmente o utilizzare la funzione di importazione. Testa sempre attentamente i reindirizzamenti con caratteri jolly!

**D5: Il mio tema personalizzato non visualizza correttamente le funzionalità del modulo (es. nel modale di audit).**
R5: Le interfacce del back-office del modulo sono generalmente indipendenti dal tema del tuo front-office. Se riscontri problemi di visualizzazione nel pannello di amministrazione, potrebbe trattarsi di un conflitto con un altro modulo amministrativo o di una modifica al file core di PrestaShop.

- **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e svuota la cache.
- **Controlla la console del browser:** Apri gli strumenti per sviluppatori del tuo browser (F12) e cerca eventuali errori JavaScript o avvisi CSS nella scheda Console quando ti trovi sulle pagine di configurazione del modulo. Questo può fornire indizi sui conflitti.
- **Contatta il supporto:** Se il problema persiste, fornisci screenshot e eventuali errori della console al supporto di MyPresta.eu.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Reindirizzamenti SEO 301, 302, 303" è costruito seguendo il pattern MVC (Model-View-Controller) di PrestaShop, con una forte enfasi sul controllo amministrativo e la gestione dei dati. Sfrutta `ModuleAdminController` per la sua estesa interfaccia di back-office, `ObjectModel` per la gestione dei dati di reindirizzamento e sovrascrive il `FrontController` per intercettare le richieste precocemente e applicare la logica di reindirizzamento. Il modulo include anche controller API e CLI per la gestione programmatica e automatizzata.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono le richieste sul lato cliente del negozio.

- `seoredirect/controllers/front/api.php`
  - **Nome classe e classe padre:** `SeoredirectApiModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller funge probabilmente da endpoint API front-office, potenzialmente per servizi esterni per interrogare lo stato di reindirizzamento o per chiamate AJAX interne relative alla logica di reindirizzamento front-office (anche se la maggior parte dei reindirizzamenti è gestita tramite l'override di `FrontController`). Risponderebbe a rotte specifiche definite dal modulo.
- `seoredirect/controllers/front/cronjob.php`
  - **Nome classe e classe padre:** `SeoredirectCronjobModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Fornisce un endpoint accessibile dal front-office per l'esecuzione di cron job. Ciò consente alle attività cron lato server (es. comandi `wget` o `curl`) di attivare funzioni del modulo come audit, pulizia o sincronizzazione dei dati senza richiedere l'autenticazione del back-office.
- `seoredirect/controllers/front/index.php`
  - **Nome classe e classe padre:** `SeoredirectIndexModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Un segnaposto o controller frontale predefinito. In molti moduli, questo potrebbe gestire una semplice rotta predefinita o servire da base per altri controller frontali. Data la natura del modulo, la sua logica principale del front-office è probabilmente nell'override di `FrontController`.

#### Controller Admin Back-Office

Questi controller gestiscono l'interfaccia e i dati del modulo all'interno del Back Office di PrestaShop.

- `seoredirect/controllers/admin/AdminSeoRedirectApiController.php`
  - **Nome scheda ed entità gestita:** "API" (o simile, sotto il menu Reindirizzamenti SEO). Gestisce le chiavi API e fornisce la documentazione API.
  - **Responsabilità:** Gestisce la visualizzazione e la gestione delle credenziali API e della documentazione per l'interazione programmatica con il modulo.
- `seoredirect/controllers/admin/AdminSeoRedirectAuditController.php`
  - **Nome scheda ed entità gestita:** "Audit" (sotto il menu Reindirizzamenti SEO). Gestisce il processo di audit per gli errori 404.
  - **Responsabilità:** Fornisce l'interfaccia per la scansione del negozio alla ricerca di errori 404, la visualizzazione dei risultati e l'offerta di opzioni per creare reindirizzamenti da link interrotti rilevati.
- `seoredirect/controllers/admin/AdminSeoRedirectCliController.php`
  - **Nome scheda ed entità gestita:** "CLI" (o simile, sotto il menu Reindirizzamenti SEO). Fornisce la documentazione dei comandi CLI.
  - **Responsabilità:** Visualizza informazioni e istruzioni per l'utilizzo degli strumenti dell'interfaccia a riga di comando del modulo, utili per l'automazione e le attività avanzate.
- `seoredirect/controllers/admin/AdminSeoRedirectDashboardController.php`
  - **Nome scheda ed entità gestita:** "Dashboard" (sotto il menu Reindirizzamenti SEO). Visualizza le statistiche e la panoramica del modulo.
  - **Responsabilità:** Presenta metriche chiave e una panoramica dell'attività di reindirizzamento, potenzialmente inclusi grafici. Gestisce la configurazione `SEOR_DASHBOARD_PERIOD`.
- `seoredirect/controllers/admin/AdminSeoRedirectHistoryController.php`
  - **Nome scheda ed entità gestita:** "Cronologia" (sotto il menu Reindirizzamenti SEO). Gestisce i record `seor_history`.
  - **Responsabilità:** Visualizza un log di tutti gli eventi di reindirizzamento, inclusi origine, destinazione, tipo e timestamp.
- `seoredirect/controllers/admin/AdminSeoRedirectImport.php`
  - **Nome scheda ed entità gestita:** "Importa" (sotto il menu Reindirizzamenti SEO). Gestisce l'importazione massiva di reindirizzamenti.
  - **Responsabilità:** Fornisce l'interfaccia per il caricamento di file CSV per creare più regole di reindirizzamento. Gestisce le configurazioni `IV_COL_DELIMITER` e `SEOR_SAFE_ROLLOUT`.
- `seoredirect/controllers/admin/AdminSeoRedirectListController.php`
  - **Nome scheda ed entità gestita:** "Elenco reindirizzamenti" (sotto il menu Reindirizzamenti SEO). Gestisce i record `seor` (reindirizzamento).
  - **Responsabilità:** L'interfaccia principale per aggiungere, modificare, eliminare ed elencare singole regole di reindirizzamento 301, 302, 303.
- `seoredirect/controllers/admin/AdminSeoredirectSearchController.php`
  - **Nome scheda ed entità gestita:** "Cerca" (o integrato). Alimenta la funzionalità di ricerca.
  - **Responsabilità:** Probabilmente fornisce capacità di ricerca e filtraggio avanzate utilizzate in varie griglie amministrative all'interno del modulo.
- `seoredirect/controllers/admin/AdminSeoRedirectSettings.php`
  - **Nome scheda ed entità gestita:** "Impostazioni" (sotto il menu Reindirizzamenti SEO). Gestisce le impostazioni `ps_configuration` relative al modulo.
  - **Responsabilità:** Fornisce l'interfaccia per la configurazione del comportamento globale del modulo, come esclusioni, reindirizzamenti automatici per prodotti non disponibili/categorie vuote e altre opzioni avanzate. Gestisce `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`.
- `seoredirect/controllers/admin/AdminSeoRedirectStats.php`
  - **Nome scheda ed entità gestita:** "Statistiche" (sotto il menu Reindirizzamenti SEO). Visualizza statistiche generali del negozio e del modulo.
  - **Responsabilità:** Fornisce una panoramica dello stato del negozio (`PS_SHOP_ENABLE`) e potenzialmente dati aggregati sulle prestazioni dei reindirizzamenti.
- `seoredirect/controllers/admin/AdminSeoRedirectToolsController.php`
  - **Nome scheda ed entità gestita:** "Strumenti" (sotto il menu Reindirizzamenti SEO). Fornisce funzioni di utilità.
  - **Responsabilità:** Contiene strumenti come l'integrazione con Google Search Console (`SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`) e altre funzionalità di utilità.
- `seoredirect/controllers/admin/index.php`
  - **Nome scheda ed entità gestita:** Non un controller diretto, tipicamente un file vuoto o una misura di sicurezza per prevenire l'elenco delle directory.

### 4.3 Classi e modelli principali (`classes/`)

- `seoredirect/override/classes/controller/FrontController.php`
  - **Cosa fa:** Questo è un override critico. Estende la classe `FrontController` core di PrestaShop.
  - **Metodi pubblici chiave e logica di business:** L'override intercetta probabilmente il metodo `init()` o `postProcess()` del `FrontController`. Prima che PrestaShop invii la richiesta a un controller di pagina specifico, questo override controlla l'URL richiesto rispetto alle regole di reindirizzamento memorizzate dal modulo. Se viene trovata una corrispondenza, emette l'intestazione HTTP di reindirizzamento 301, 302 o 303 appropriata e termina la richiesta, prevenendo un 404 e inviando l'utente al nuovo URL. Qui risiede la logica di reindirizzamento principale.
- `seoredirect/override/classes/controller/index.php`
  - **Cosa fa:** File segnaposto, solitamente per sicurezza.
- `seoredirect/override/classes/index.php`
  - **Cosa fa:** File segnaposto, solitamente per sicurezza.

*(Nota: il dossier del modulo non elencava esplicitamente classi `ObjectModel` personalizzate come `SeoRedirect` o `SeoRedirectHistory`. Tuttavia, data la presenza di `AdminSeoRedirectListController` che gestisce `seor` e `AdminSeoRedirectHistoryController` che gestisce `seor_history`, è altamente probabile che esistano classi `SeoRedirect` e `SeoRedirectHistory` corrispondenti (o nomi simili) che estendono `ObjectModel` all'interno della directory principale del modulo o di una sottodirectory `classes/` non esplicitamente elencata nell'inventario. Queste definirebbero lo schema del database per i reindirizzamenti e le voci di cronologia.)*

### 4.4 Risorse JavaScript (`views/js/`)

- `seoredirect/examples/console-mock-dashboard-audit.js`
  - **Ambito:** Probabilmente per sviluppo/test, non per produzione.
  - **Dettagli:** Esempio o dati/logica fittizi per le funzionalità di dashboard e audit, possibilmente utilizzati per il debug della console o la dimostrazione.
- `seoredirect/views/js/adminSeoRedirectApi.js`
  - **Ambito:** Back-office (AdminSeoRedirectApiController).
  - **Dettagli:** Gestisce le interazioni lato client nella schermata di configurazione API, come la generazione di chiavi API, la copia di chiavi negli appunti o la visualizzazione di modali di documentazione API.
- `seoredirect/views/js/adminSeoRedirectAudit.js`
  - **Ambito:** Back-office (AdminSeoRedirectAuditController).
  - **Dettagli:** Gestisce il processo di audit, incluse le chiamate AJAX per attivare le scansioni, l'aggiornamento degli indicatori di progresso, la visualizzazione dei risultati dell'audit in una tabella dinamica e la gestione di azioni come la creazione di reindirizzamenti dai risultati dell'audit. Potrebbe includere popup modali per l'anteprima o la conferma dei reindirizzamenti.
- `seoredirect/views/js/adminSeoRedirectConfig.js`
  - **Ambito:** Back-office (Configurazione principale del modulo o AdminSeoRedirectSettingsController).
  - **Dettagli:** JavaScript generale per i moduli di configurazione principali del modulo. Questo potrebbe includere la convalida del modulo, la visibilità dinamica dei campi basata su altre impostazioni o chiamate AJAX per il salvataggio della configurazione.
- `seoredirect/views/js/adminSeoRedirectDashboard.js`
  - **Ambito:** Back-office (AdminSeoRedirectDashboardController).
  - **Dettagli:** Alimenta gli elementi interattivi della dashboard, come il caricamento dei dati tramite AJAX, il rendering dei grafici (se presenti) e la gestione delle modifiche alla selezione del periodo (`SEOR_DASHBOARD_PERIOD`).
- `seoredirect/views/js/adminSeoRedirectImport.js`
  - **Ambito:** Back-office (AdminSeoRedirectImportController).
  - **Dettagli:** Gestisce il processo di importazione CSV, inclusa la selezione del file, gli indicatori di progresso, la visualizzazione dei risultati/errori di importazione e potenzialmente la gestione della logica `SEOR_SAFE_ROLLOUT` lato client.

### 4.5 Fogli di stile CSS (`views/css/`)

- `seoredirect/views/css/seoredirect-admin.css`
  - **Ambito:** Stile dei moduli di amministrazione del back-office.
  - **Dettagli:** Contiene stili specifici per le varie schermate di amministrazione del modulo, garantendo un'interfaccia coerente e user-friendly all'interno del back office di PrestaShop. Ciò includerebbe lo stile per griglie, moduli, pulsanti, modali ed elementi della dashboard.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Cerca classi con prefisso `seor-` o `admin-seoredirect-` per elementi specifici del modulo.

### 4.6 Struttura dei template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:

  - La descrizione del modulo menziona hook front-office (Header, Colonne, Prodotto, Footer), ma l'inventario dei file non elenca template hook specifici in `views/templates/hook/`. Ciò suggerisce che l'interazione front-office è gestita principalmente dall'override di `FrontController` per i reindirizzamenti, piuttosto che dal rendering di contenuti visibili negli hook. Se esistono template hook, sarebbero per elementi di visualizzazione molto specifici, non correlati al reindirizzamento.
- **Template admin (`views/templates/admin/`)**:

  - `seoredirect/lib/searchTool/views/scripts.tpl`: Contiene probabilmente logica JavaScript o Smarty per uno strumento di ricerca generico utilizzato in più schermate di amministrazione.
  - `seoredirect/views/admin/adminSearch.tpl`: Template per un'interfaccia di ricerca generica nell'amministrazione.
  - `seoredirect/views/admin/adminSearchCategory.tpl`: Template per la ricerca/selezione di categorie nell'amministrazione.
  - `seoredirect/views/admin/adminSearchCategoryToMove.tpl`: Template per la ricerca di spostamento di categoria.
  - `seoredirect/views/admin/adminSearchCategoryToMoveInStock.tpl`: Template per la ricerca di spostamento di categoria, specificamente per articoli in magazzino.
  - `seoredirect/views/admin/adminSeoRedirectImport.tpl`: Il template principale per la schermata di importazione (AdminSeoRedirectImportController).
  - `seoredirect/views/admin/stats.tpl`: Template per la schermata delle statistiche (AdminSeoRedirectStatsController).
  - `seoredirect/views/templates/admin/api.tpl`: Template per la schermata di configurazione API (AdminSeoRedirectApiController).
  - `seoredirect/views/templates/admin/audit.tpl`: Template per la schermata di audit (AdminSeoRedirectAuditController).
  - `seoredirect/views/templates/admin/cli.tpl`: Template per la schermata di documentazione CLI (AdminSeoRedirectCliController).
  - `seoredirect/views/templates/admin/dashboard.tpl`: Template per la dashboard del modulo (AdminSeoRedirectDashboardController).
  - `seoredirect/views/templates/admin/employee_permissions.tpl`: Template per la gestione dei permessi dei dipendenti relativi alle schede di amministrazione del modulo.
  - `seoredirect/views/templates/admin/import.tpl`: Un altro template per la funzionalità di importazione (potrebbe essere un wrapper o una parte specifica del processo di importazione).
  - `seoredirect/views/templates/admin/seo_redirect_settings/helpers/options/options.tpl`: Un template parziale per il rendering delle opzioni all'interno della schermata delle impostazioni (AdminSeoRedirectSettingsController).
  - `seoredirect/views/templates/admin/tools.tpl`: Template per la schermata degli strumenti (AdminSeoRedirectToolsController).
  - `seoredirect/views/templates/admin/_api_documentation_modal.tpl`: Un template modale per la visualizzazione della documentazione API.
  - `seoredirect/views/templates/admin/_audit_preview_modal.tpl`: Un template modale per l'anteprima dei risultati dell'audit o delle creazioni di reindirizzamento.
  - `seoredirect/views/templates/admin/_cli_documentation_modal.tpl`: Un template modale per la visualizzazione della documentazione CLI.
- **Template front-office (`views/templates/front/`)**:

  - Non sono elencati template front-office specifici, il che rafforza l'idea che l'operazione front-end del modulo avvenga principalmente tramite l'override di `FrontController` per il reindirizzamento, non tramite contenuti visibili.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - `ps_seor`: Memorizza le regole di reindirizzamento principali (Vecchio URL, Nuovo URL, Tipo di reindirizzamento, Stato, ecc.). Questa tabella è gestita da `AdminSeoRedirectListController` e dall'`ObjectModel` `SeoRedirect` (implicito).
  - `ps_seor_history`: Memorizza un log di tutti i reindirizzamenti attivati (Richiesta originale, Reindirizzato a, Tipo, Timestamp, ecc.). Questa tabella è gestita da `AdminSeoRedirectHistoryController` e dall'`ObjectModel` `SeoRedirectHistory` (implicito).
  - `ps_configuration`: Memorizza le impostazioni globali specifiche del modulo come `SEOR_DASHBOARD_PERIOD`, `IV_COL_DELIMITER`, `SEOR_SAFE_ROLLOUT`, `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`, `SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`.
- **Tabella degli hook registrati**:

  | Nome Hook | Tempistica di esecuzione | Scopo tecnico |
  | --- | --- | --- |
  | `actionFrontControllerSetMedia` | Prima che il controller frontale renda il contenuto | Potenzialmente carica JS/CSS del front-office, se presenti, anche se improbabile per un modulo di reindirizzamento. |
  | `actionDispatcherBefore` | Molto presto nel ciclo di vita della richiesta, prima di inviare a un controller. | **CRITICO:** Questo è l'hook più probabile per l'override di `FrontController` per intercettare la richiesta e applicare la logica di reindirizzamento. Consente al modulo di reindirizzare prima che PrestaShop tenti persino di trovare la pagina originale. |
  | `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel back office. | Potrebbe essere utilizzato per mostrare lo stato di reindirizzamento per un prodotto o suggerire la creazione di un reindirizzamento se l'URL del prodotto viene modificato. |
  | `displayAdminCategoriesExtra` | Nella pagina di modifica della categoria nel back office. | Simile ai prodotti, potrebbe mostrare lo stato di reindirizzamento o suggerire reindirizzamenti per le modifiche all'URL della categoria. |
  | `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Improbabile per la logica di reindirizzamento principale, ma potrebbe essere utilizzato per aggiungere meta tag o canonicali relativi ai reindirizzamenti, se necessario. |
  | `displayRightColumn` | Nella colonna destra delle pagine del front-office. | Improbabile per questo modulo. |
  | `displayFooter` | Nel footer di ogni pagina del front-office. | Improbabile per questo modulo. |
  | `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Potrebbe essere utilizzato per registrare o controllare i reindirizzamenti relativi ai processi di checkout, anche se meno diretto. |
  | `actionModuleInstall` | Durante l'installazione del modulo. | Crea tabelle del database, registra hook, imposta valori di configurazione predefiniti. |
  | `actionModuleUninstall` | Durante la disinstallazione del modulo. | Pulisce le tabelle del database, annulla la registrazione degli hook, rimuove i valori di configurazione. |
  | `actionAdminControllerSetMedia` | Prima che un controller admin renda il contenuto. | Carica JS/CSS del back-office per le pagine admin del modulo. |
  | `actionAdminSeoRedirectSave` | Hook personalizzato, probabilmente attivato dopo che una regola di reindirizzamento viene salvata nel back office. | Consente ad altri moduli o codice personalizzato di reagire alle modifiche di reindirizzamento. |
  | `actionAdminSeoRedirectDelete` | Hook personalizzato, probabilmente attivato dopo che una regola di reindirizzamento viene eliminata. | Consente ad altri moduli o codice personalizzato di reagire alle eliminazioni di reindirizzamento. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante il modulo "Reindirizzamenti SEO 301, 302, 303".
