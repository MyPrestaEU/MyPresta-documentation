---
title: "GPSR Enterprise - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop GPSR Enterprise di MyPresta.eu."
sidebar:
  label: "GPSR Enterprise"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo GPSR Enterprise su MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-enterprise.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/gpsr-enterprise/)
>
> ---


# GPSR Enterprise

## 1. Requisiti e Compatibilità

*   **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
*   **Compatibilità PHP**: PHP 7.1 - 8.5
*   **Requisiti di Hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL) e sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

Il modulo GPSR Enterprise offre un set completo di opzioni di configurazione, distribuite sulla sua pagina di configurazione principale e su diverse schermate di amministrazione dedicate.

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Gestione moduli > GPSR Enterprise > Configura)

Questa è la schermata di configurazione principale del modulo, dove controlli il suo comportamento generale e la visualizzazione nel front-office.

*   **Modulo abilitato**
    *   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo GPSR Enterprise.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* Il modulo sarà attivo, visualizzando le informazioni GPSR sulle pagine dei prodotti, consentendoti di gestire entità, avvisi e mappature, e abilitando l'API e i cron job.
        *   *Quando disabilitato (No):* Il modulo sarà completamente inattivo. Nessuna informazione GPSR sarà mostrata nel front office e le funzionalità di gestione del backend saranno non disponibili o non funzionanti.
    *   **Valore consigliato:** **Sì** (per utilizzare le funzionalità del modulo).
    *   **Scenario / esempio per il commerciante:** Se stai configurando il modulo per la prima volta, mantienilo disabilitato fino a quando tutte le configurazioni non sono complete, quindi abilitalo per andare online.

*   **Profilo tema storefront**
    *   **Cosa fa questa impostazione:** Ti consente di selezionare il profilo di stile visivo per il blocco informazioni GPSR sulle pagine dei tuoi prodotti, ottimizzato per diversi temi PrestaShop.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su 'Classic':* Il modulo utilizzerà uno stile ottimizzato per il tema PrestaShop Classic predefinito (e molti temi compatibili).
        *   *Quando impostato su 'Hummingbird':* Il modulo utilizzerà uno stile ottimizzato per il nuovo tema PrestaShop Hummingbird (PrestaShop 8.1+).
    *   **Valore consigliato:** Seleziona il profilo che meglio si adatta al tuo tema PrestaShop attuale. Se non sei sicuro, prova prima 'Classic'.
    *   **Scenario / esempio per il commerciante:** Se il tuo negozio utilizza PrestaShop 8.1+ con il tema predefinito, scegli 'Hummingbird' per la migliore integrazione visiva. Se sei su PrestaShop 1.7 o 8.0 con il tema Classic, scegli 'Classic'.

*   **Modalità di visualizzazione**
    *   **Cosa fa questa impostazione:** Controlla come viene presentato il blocco informazioni GPSR sulla pagina del prodotto.
    *   **Effetto della modifica di questa impostazione:**
        *   *Le opzioni variano (es. 'Tab', 'Accordion', 'Block'):*
            *   **Tab:** Le informazioni GPSR appariranno come una nuova scheda accanto a "Descrizione", "Dettagli prodotto", ecc.
            *   **Accordion:** Le informazioni saranno presentate in una sezione a fisarmonica espandibile/collassabile.
            *   **Block:** Le informazioni saranno visualizzate come un blocco statico all'interno del flusso di contenuto della pagina del prodotto.
    *   **Valore consigliato:** **Tab** o **Accordion** per un layout più pulito della pagina del prodotto, specialmente se hai molte informazioni.
    *   **Scenario / esempio per il commerciante:** Se le tue pagine prodotto sono già molto lunghe, l'utilizzo della modalità 'Tab' o 'Accordion' mantiene la pagina ordinata pur rendendo le informazioni accessibili.

*   **Stile visivo**
    *   **Cosa fa questa impostazione:** Definisce l'estetica generale del blocco informazioni GPSR.
    *   **Effetto della modifica di questa impostazione:**
        *   *Le opzioni variano (es. 'Default', 'Minimal', 'Detailed'):* Questo cambierà la densità visiva, l'uso di icone e la presentazione generale delle informazioni.
    *   **Valore consigliato:** **Default** o **Minimal** per un aspetto pulito. Sperimenta per vedere cosa si adatta meglio al tuo tema.
    *   **Scenario / esempio per il commerciante:** Se il tuo tema è molto minimalista, scegliere uno stile visivo 'Minimal' per il blocco GPSR garantirà una migliore integrazione.

*   **Mostra titolo blocco**
    *   **Cosa fa questa impostazione:** Determina se un titolo viene visualizzato sopra il blocco informazioni GPSR sulla pagina del prodotto.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* Il testo specificato in "Testo titolo blocco" apparirà come intestazione.
        *   *Quando disabilitato (No):* Nessun titolo verrà visualizzato, facendo sì che il blocco si integri più fluidamente o si basi sul contesto.
    *   **Valore consigliato:** **Sì** per chiarezza, in modo che i clienti comprendano immediatamente cosa contiene il blocco.
    *   **Scenario / esempio per il commerciante:** Abilitando questa opzione con un titolo come "Informazioni sulla sicurezza del prodotto" si rende chiaro ai clienti cosa stanno visualizzando.

*   **Testo titolo blocco**
    *   **Cosa fa questa impostazione:** Ti consente di personalizzare il titolo del blocco informazioni GPSR. Questa impostazione si applica solo se "Mostra titolo blocco" è abilitato.
    *   **Effetto della modifica di questa impostazione:** Il testo che inserisci qui verrà visualizzato come intestazione per il blocco informazioni GPSR sulla pagina del prodotto.
    *   **Valore consigliato:** Un titolo chiaro e descrittivo come "Sicurezza e Conformità del Prodotto", "Informazioni sulla Sicurezza UE" o "Dettagli del Passaporto del Prodotto".
    *   **Scenario / esempio per il commerciante:** Puoi impostarlo su "Informazioni sulla Sicurezza del Prodotto UE" per comunicare chiaramente lo scopo del blocco ai tuoi clienti europei.

*   **Nascondi blocco quando i dati sono incompleti**
    *   **Cosa fa questa impostazione:** Controlla se il blocco informazioni GPSR viene visualizzato sulla pagina del prodotto se non tutti i dati richiesti (produttore, persona responsabile UE, avvisi, documenti) sono stati completamente configurati per quel prodotto.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* Se mancano dati GPSR per un prodotto, l'intero blocco non verrà mostrato nel front office. Ciò impedisce la visualizzazione di informazioni incomplete o fuorvianti.
        *   *Quando disabilitato (No):* Il blocco verrà sempre visualizzato, anche se alcune sezioni sono vuote. Ciò potrebbe mostrare un blocco parzialmente compilato, il che potrebbe essere confuso.
    *   **Valore consigliato:** **Sì** per mantenere un aspetto professionale ed evitare di mostrare sezioni mezze vuote.
    *   **Scenario / esempio per il commerciante:** Sei ancora in fase di aggiunta dei dati GPSR a tutti i tuoi prodotti. Abilitando questa opzione, solo le pagine prodotto completamente conformi visualizzeranno il blocco, prevenendo la confusione dei clienti sui prodotti ancora in fase di aggiornamento.

*   **Mostra entità produttore**
    *   **Cosa fa questa impostazione:** Determina se i dettagli dell'entità GPSR del produttore vengono visualizzati nel blocco del front-office.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* Il nome, l'indirizzo e altri dettagli configurati del produttore saranno visibili.
        *   *Quando disabilitato (No):* La sezione del produttore sarà nascosta.
    *   **Valore consigliato:** **Sì** in quanto questo è un requisito GPSR fondamentale.
    *   **Scenario / esempio per il commerciante:** Per conformarsi pienamente al GPSR, è necessario mostrare i dettagli del produttore. Mantieni questa opzione abilitata.

*   **Mostra persona responsabile UE**
    *   **Cosa fa questa impostazione:** Determina se i dettagli dell'entità GPSR della persona responsabile UE vengono visualizzati nel blocco del front-office.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* Il nome, l'indirizzo e altri dettagli configurati della persona responsabile UE saranno visibili.
        *   *Quando disabilitato (No):* La sezione della persona responsabile UE sarà nascosta.
    *   **Valore consigliato:** **Sì** in quanto questo è un requisito GPSR fondamentale per i prodotti venduti nell'UE.
    *   **Scenario / esempio per il commerciante:** Se i tuoi prodotti richiedono una persona responsabile UE, abilitando questa opzione si assicura che i loro dettagli siano mostrati.

*   **Mostra avvisi di sicurezza**
    *   **Cosa fa questa impostazione:** Determina se eventuali avvisi di sicurezza associati vengono visualizzati nel blocco del front-office.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* Gli avvisi di sicurezza configurati per il prodotto saranno visibili.
        *   *Quando disabilitato (No):* La sezione degli avvisi di sicurezza sarà nascosta.
    *   **Valore consigliato:** **Sì** per informare i clienti di potenziali pericoli.
    *   **Scenario / esempio per il commerciante:** Per prodotti con istruzioni di sicurezza specifiche (es. "Tenere fuori dalla portata dei bambini"), abilitando questa opzione si assicura che questi avvisi siano visualizzati in modo prominente.

*   **Mostra documenti collegati**
    *   **Cosa fa questa impostazione:** Determina se i link a documenti associati (come manuali, dichiarazioni) vengono visualizzati nel blocco del front-office.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* I link ai documenti caricati saranno visibili.
        *   *Quando disabilitato (No):* La sezione dei documenti collegati sarà nascosta.
    *   **Valore consigliato:** **Sì** per fornire ai clienti la documentazione essenziale del prodotto.
    *   **Scenario / esempio per il commerciante:** Se devi fornire una "Dichiarazione di Conformità" o un manuale utente dettagliato, abilitando questa opzione i clienti potranno accedere facilmente a questi file.

*   **Mostra pulsante passaporto del prodotto**
    *   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Scarica Passaporto del Prodotto" sulla pagina del prodotto.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* Apparirà un pulsante, consentendo ai clienti di scaricare un PDF contenente tutte le informazioni GPSR per il prodotto.
        *   *Quando disabilitato (No):* Il pulsante non verrà mostrato.
    *   **Valore consigliato:** **Sì** in quanto il passaporto del prodotto è una caratteristica chiave del GPSR.
    *   **Scenario / esempio per il commerciante:** Per offrire ai clienti un riepilogo completo e scaricabile di tutte le informazioni sulla sicurezza e la conformità, mantieni questa opzione abilitata.

*   **Condividi mappature tra tutti i negozi**
    *   **Cosa fa questa impostazione:** (Visibile solo in una configurazione multi-negozio) Determina se le mappature GPSR (come entità, avvisi e documenti sono assegnati a prodotti, categorie o produttori) sono condivise tra tutti i tuoi negozi PrestaShop.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato (Sì):* Tutte le mappature GPSR che crei si applicheranno a tutti i negozi nel tuo ambiente multi-negozio. Ciò semplifica la gestione se il tuo catalogo prodotti e le esigenze di conformità sono simili tra i negozi.
        *   *Quando disabilitato (No):* Ogni negozio avrà il proprio set indipendente di mappature GPSR, consentendo configurazioni di conformità specifiche per negozio.
    *   **Valore consigliato:** **Sì** se le tue esigenze di conformità sono coerenti tra i negozi; altrimenti, **No**.
    *   **Scenario / esempio per il commerciante:** Se gestisci più negozi specifici per paese ma vendi gli stessi prodotti con gli stessi requisiti di conformità, abilitando questa opzione risparmi molto tempo gestendo le mappature una sola volta.

*   **Azione all'abilitazione della condivisione**
    *   **Cosa fa questa impostazione:** (Visibile solo in una configurazione multi-negozio, appare quando "Condividi mappature tra tutti i negozi" è abilitato) Definisce cosa succede alle mappature esistenti specifiche del negozio quando si passa alle mappature condivise.
    *   **Effetto della modifica di questa impostazione:**
        *   *Le opzioni variano (es. 'Unisci', 'Sovrascrivi', 'Mantieni negozio corrente'):*
            *   **Unisci:** Tenta di combinare le mappature esistenti da tutti i negozi in un unico set condiviso.
            *   **Sovrascrivi:** Sostituisce tutte le mappature esistenti specifiche del negozio con le mappature del negozio attualmente attivo.
            *   **Mantieni negozio corrente:** Utilizza le mappature del negozio attualmente attivo come mappature condivise, scartando le altre.
    *   **Valore consigliato:** Scegli con attenzione in base ai tuoi dati. **Esegui il backup del tuo database** prima di modificare questa opzione!
    *   **Scenario / esempio per il commerciante:** Se hai gestito i dati GPSR separatamente per ogni negozio e ora vuoi centralizzare, dovrai decidere se vuoi combinare tutti i dati, o se i dati di un negozio dovrebbero diventare il master.

*   **Azione alla disabilitazione della condivisione**
    *   **Cosa fa questa impostazione:** (Visibile solo in una configurazione multi-negozio, appare quando "Condividi mappature tra tutti i negozi" è disabilitato) Definisce cosa succede alle mappature condivise quando si torna alle mappature specifiche del negozio.
    *   **Effetto della modifica di questa impostazione:**
        *   *Le opzioni variano (es. 'Duplica in tutti i negozi', 'Mantieni solo per il negozio corrente'):*
            *   **Duplica in tutti i negozi:** Le mappature condivise attuali vengono copiate in ogni singolo negozio, consentendo di modificarle indipendentemente in seguito.
            *   **Mantieni solo per il negozio corrente:** Le mappature condivise vengono assegnate solo al negozio attualmente attivo e gli altri negozi inizieranno senza mappature GPSR.
    *   **Valore consigliato:** Scegli con attenzione in base ai tuoi dati. **Esegui il backup del tuo database** prima di modificare questa opzione!
    *   **Scenario / esempio per il commerciante:** Se decidi di passare dalle mappature condivise alla gestione individuale del negozio, devi decidere se i dati condivisi devono essere copiati in tutti i negozi come punto di partenza, o se solo il negozio corrente deve conservarli.

*   **CSS personalizzato**
    *   **Cosa fa questa impostazione:** Fornisce un'area di testo dove puoi aggiungere regole CSS personalizzate per stilizzare ulteriormente il blocco informazioni GPSR sul tuo storefront.
    *   **Effetto della modifica di questa impostazione:** Qualsiasi codice CSS valido inserito qui verrà applicato agli elementi del front-office del modulo GPSR, consentendoti di perfezionare colori, font, spaziatura, ecc., per abbinare perfettamente il tuo tema.
    *   **Valore consigliato:** Lascia vuoto a meno che tu non abbia esigenze di stile specifiche e sia a tuo agio con il CSS.
    *   **Scenario / esempio per il commerciante:** Il tuo tema utilizza una specifica tonalità di blu per le intestazioni. Puoi aggiungere CSS qui per assicurarti che anche il titolo del blocco GPSR utilizzi quel blu esatto, mantenendo la coerenza visiva.

### 2.2 Schermate di Amministrazione Dedicate e Viste Controller

Il modulo GPSR Enterprise aggiunge diverse nuove voci di menu sotto un menu principale "GPSR Enterprise" nel tuo Back Office di PrestaShop. Queste schermate sono dove gestisci tutti i dati dettagliati di conformità.

#### 2.2.1 Dashboard GPSR Enterprise (Back Office > GPSR Enterprise > Dashboard)

Questa schermata fornisce una panoramica dello stato di conformità GPSR e un accesso rapido alle aree di gestione chiave.

*   **Azioni e Impostazioni Disponibili:**
    *   **Statistiche Riepilogative:** Potrebbe mostrare il numero di entità configurate, avvisi, prodotti mappati, ecc.
    *   **Link Rapidi:** Pulsanti o link per passare direttamente alla gestione di Entità, Avvisi, Mappature, Documenti, ecc.
    *   **Stato Cron Job:** Informazioni sull'ultima esecuzione e il risultato del cron job GPSR (per la reindicizzazione o la sincronizzazione dei dati).
    *   **Token API:** Visualizza il tuo token API univoco per integrazioni esterne.
    *   **Token Cron:** Visualizza il tuo token cron job univoco per un'esecuzione sicura.
*   **Effetto delle modifiche:** Questa schermata è principalmente per il monitoraggio e la navigazione. Le modifiche qui (es. generazione di nuovi token API/Cron) influiscono direttamente sulla sicurezza e sulla funzionalità delle integrazioni esterne e delle attività automatizzate.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla periodicamente questa dashboard per monitorare lo stato di conformità e assicurarti che i cron job siano eseguiti correttamente.

#### 2.2.2 Entità (Back Office > GPSR Enterprise > Entità)

Questa schermata è dove definisci e gestisci le "entità" richieste dal GPSR, come produttori e persone responsabili UE.

*   **Azioni e Impostazioni Disponibili:**
    *   **Elenco Entità:** Una tabella che mostra tutte le entità configurate, con colonne per nome, tipo (Produttore, Persona Responsabile UE), indirizzo, contatto, ecc.
    *   **Aggiungi Nuova Entità:** Un pulsante per creare una nuova entità.
    *   **Modifica/Elimina:** Azioni per ogni entità nell'elenco.
    *   **Modulo Entità:** Quando aggiungi/modifica, troverai campi per:
        *   **Nome:** Il nome ufficiale dell'entità.
        *   **Tipo:** Seleziona se è un Produttore o una Persona Responsabile UE.
        *   **Indirizzo:** Indirizzo postale completo.
        *   **Informazioni di Contatto:** Email, telefono, sito web.
        *   **Campi Multilingue:** Alcuni campi possono essere traducibili per diverse lingue.
*   **Effetto delle modifiche:** La creazione o l'aggiornamento delle entità qui le rende disponibili per la selezione durante la mappatura dei dati GPSR ai prodotti. Dati di entità errati o incompleti porteranno alla non conformità.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Prima di mappare i prodotti, assicurati che tutti i tuoi produttori e le persone responsabili UE siano inseriti accuratamente qui. Aggiorna i dettagli prontamente se cambiano.

#### 2.2.3 Avvisi (Back Office > GPSR Enterprise > Avvisi)

Questa schermata ti consente di definire e gestire vari avvisi di sicurezza che possono essere associati ai tuoi prodotti.

*   **Azioni e Impostazioni Disponibili:**
    *   **Elenco Avvisi:** Una tabella che mostra tutti gli avvisi creati, con colonne per titolo, icona e contenuto.
    *   **Aggiungi Nuovo Avviso:** Un pulsante per creare un nuovo avviso.
    *   **Modifica/Elimina:** Azioni per ogni avviso nell'elenco.
    *   **Modulo Avviso:** Quando aggiungi/modifica, troverai campi per:
        *   **Titolo:** Un titolo breve e descrittivo per l'avviso.
        *   **Icona:** Un'opzione per selezionare un'icona visiva da accompagnare all'avviso (es. un simbolo di pericolo).
        *   **Contenuto:** Il testo completo dell'avviso di sicurezza (multilingue).
        *   **Gravità/Tipo:** (Se disponibile) Categorizza l'avviso.
*   **Effetto delle modifiche:** Gli avvisi creati qui diventano disponibili per la selezione durante la mappatura dei dati GPSR ai prodotti. Appariranno quindi sulla pagina del prodotto nel front-office.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Crea prima tutti gli avvisi di sicurezza necessari qui. Assicurati che il contenuto sia accurato e legalmente conforme per tutte le lingue che supporti.

#### 2.2.4 Documenti (Back Office > GPSR Enterprise > Documenti)

Questa schermata serve per caricare e gestire documenti che devono essere collegati ai prodotti, come dichiarazioni di conformità, manuali utente o schede di dati di sicurezza.

*   **Azioni e Impostazioni Disponibili:**
    *   **Elenco Documenti:** Una tabella che mostra i documenti caricati, con colonne per nome, tipo di file e prodotti associati.
    *   **Carica Nuovo Documento:** Un pulsante per caricare un nuovo file.
    *   **Modifica/Elimina:** Azioni per ogni documento.
    *   **Modulo Documento:** Quando carichi/modifica, troverai campi per:
        *   **Nome:** Un nome descrittivo per il documento (multilingue).
        *   **Caricamento File:** Il file effettivo (es. PDF).
        *   **Tipo:** (Se disponibile) Categorizza il documento (es. "Manuale", "Dichiarazione").
*   **Effetto delle modifiche:** I documenti caricati diventano disponibili per la selezione durante la mappatura dei dati GPSR ai prodotti. I link a questi documenti appariranno sulla pagina del prodotto nel front-office.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Carica qui tutta la documentazione pertinente del prodotto. Assicurati che i documenti siano aggiornati e correttamente denominati per una facile identificazione.

#### 2.2.5 Mappature (Back Office > GPSR Enterprise > Mappature)

Questo è il cuore dell'automazione del modulo, che ti consente di definire come i dati GPSR vengono assegnati ai prodotti in base a vari criteri. Questa sezione probabilmente contiene diverse sottosezioni per diversi tipi di mappatura.

*   **Azioni e Impostazioni Disponibili:**
    *   **Mappature Globali:** Applica i dati GPSR a tutti i prodotti per impostazione predefinita.
    *   **Mappature per Categoria:** Applica i dati GPSR a tutti i prodotti all'interno di una categoria specifica.
    *   **Mappature per Produttore:** Applica i dati GPSR a tutti i prodotti di un produttore specifico.
    *   **Mappature per Prodotto/Combinazione:** Applica i dati GPSR a singoli prodotti o a specifiche combinazioni di prodotti (varianti).
    *   **Moduli di Mappatura:** Per ogni tipo di mappatura, configurerai:
        *   **Entità Produttore Assegnata:** Seleziona un'entità definita nella sezione "Entità".
        *   **Entità Persona Responsabile UE Assegnata:** Seleziona un'entità definita nella sezione "Entità".
        *   **Avvisi Assegnati:** Seleziona uno o più avvisi definiti nella sezione "Avvisi".
        *   **Documenti Assegnati:** Seleziona uno o più documenti caricati nella sezione "Documenti".
        *   **Regole di Priorità/Sovrascrittura:** (Se disponibili) Definisci come le mappature da diversi livelli (globale, categoria, produttore, prodotto) interagiscono e si sovrascrivono a vicenda.
*   **Effetto delle modifiche:** Le modifiche qui determinano direttamente quali informazioni GPSR vengono visualizzate sulle pagine dei tuoi prodotti. Una strategia di mappatura ben strutturata riduce significativamente il lavoro manuale.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Inizia con le Mappature Globali, quindi affina con le Mappature per Categoria e Produttore. Utilizza le Mappature per Prodotto/Combinazione solo per eccezioni o prodotti unici. Rivedi regolarmente le tue mappature, specialmente quando aggiungi nuovi prodotti o categorie.

#### 2.2.6 Azioni di Massa (Back Office > GPSR Enterprise > Azioni di Massa)

Questa schermata fornisce strumenti per applicare i dati GPSR a più prodotti contemporaneamente, o per eseguire operazioni in blocco.

*   **Azioni e Impostazioni Disponibili:**
    *   **Griglia Prodotti:** Un elenco di prodotti filtrabile e ricercabile.
    *   **Assegnazione in Blocco:** Seleziona più prodotti e quindi assegna un'Entità Produttore, una Persona Responsabile UE, Avvisi o Documenti a tutti i prodotti selezionati.
    *   **Rimozione in Blocco:** Rimuovi i dati GPSR dai prodotti selezionati.
    *   **Importa/Esporta:** (Se disponibile) Strumenti per importare dati GPSR da un file CSV o esportare dati esistenti.
*   **Effetto delle modifiche:** Le azioni di massa possono aggiornare rapidamente i dati GPSR per un gran numero di prodotti, risparmiando tempo significativo. Usare con cautela, poiché le modifiche vengono applicate ampiamente.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa opzione dopo la configurazione iniziale per applicare rapidamente dati GPSR comuni a grandi set di prodotti. Utile anche per aggiornare i dati su molti prodotti se una normativa cambia.

#### 2.2.7 Matcher (Back Office > GPSR Enterprise > Matcher)

Questa schermata aiuta a identificare i prodotti a cui potrebbero mancare dati GPSR o suggerisce potenziali mappature.

*   **Tabella / Entità Gestita:** `gpsr_match_suggestion`
*   **Azioni e Impostazioni Disponibili:**
    *   **Elenco Suggerimenti:** Visualizza prodotti o gruppi di prodotti che il modulo identifica come potenzialmente bisognosi di dati GPSR o con dati incompleti.
    *   **Regole di Corrispondenza:** (Se disponibile) Configura le regole su come il modulo suggerisce le corrispondenze (es. basate su parole chiave del nome del prodotto, attributi esistenti).
    *   **Applica/Ignora Suggerimenti:** Azioni per applicare i dati GPSR suggeriti o ignorare il suggerimento.
*   **Effetto delle modifiche:** L'applicazione dei suggerimenti aggiornerà i dati GPSR per i prodotti identificati. Questo aiuta a garantire una conformità completa.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla periodicamente questa schermata per individuare eventuali prodotti che potrebbero essere sfuggiti alla tua strategia di mappatura.

#### 2.2.8 Registro di Controllo (Back Office > GPSR Enterprise > Registro di Controllo)

Questa schermata fornisce un registro storico delle modifiche apportate ai dati GPSR all'interno del modulo.

*   **Tabella / Entità Gestita:** `gpsr_audit_log`
*   **Azioni e Impostazioni Disponibili:**
    *   **Griglia del Registro:** Una tabella che mostra le voci con dettagli come:
        *   **Data/Ora:** Quando è avvenuta la modifica.
        *   **Utente:** Quale amministratore ha apportato la modifica.
        *   **Azione:** Quale azione è stata eseguita (es. "Entità creata", "Prodotto mappato", "Avviso aggiornato").
        *   **Dettagli:** Specifiche della modifica.
*   **Effetto delle modifiche:** Questa schermata è per l'audit e il monitoraggio. Qui non vengono apportate modifiche dirette ai dati GPSR, ma fornisce un registro cruciale per la responsabilità e la risoluzione dei problemi.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questo registro per rivedere le modifiche, specialmente se hai più amministratori che gestiscono i dati GPSR, o se hai bisogno di risolvere il problema del perché certi dati appaiono (o non appaiono) nel front office.

#### 2.2.9 Registro (Back Office > GPSR Enterprise > Registro)

Questa schermata probabilmente fornisce un registro più dettagliato e "silente" di tutti i dati GPSR applicati ai prodotti, potenzialmente includendo versioni storiche o una panoramica completa per scopi normativi.

*   **Azioni e Impostazioni Disponibili:**
    *   **Vista Centrata sul Prodotto:** Un modo per visualizzare tutti i dati GPSR associati a un prodotto specifico, possibilmente includendo come sono stati derivati (es. da una mappatura di categoria, o assegnati direttamente).
    *   **Opzioni di Esportazione:** (Se disponibili) Esporta il registro completo per revisione esterna o archiviazione.
*   **Effetto delle modifiche:** Questa schermata è principalmente per la reportistica e la revisione dettagliata. Non modifica direttamente i dati del front-office ma fornisce il record di conformità sottostante.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa opzione per controlli di conformità approfonditi o quando ti prepari per audit normativi.

#### 2.2.10 API (Back Office > GPSR Enterprise > API)

Questa schermata fornisce informazioni e impostazioni relative all'API del modulo per integrazioni esterne.

*   **Azioni e Impostazioni Disponibili:**
    *   **Token API:** Visualizza il token univoco richiesto per autenticare le richieste API.
    *   **Genera Nuovo Token:** Un pulsante per generare un nuovo token API (utile per la sicurezza se un token viene compromesso).
    *   **Link Documentazione API:** Un link alla documentazione tecnica per gli sviluppatori su come utilizzare l'API.
*   **Effetto delle modifiche:** La generazione di un nuovo token invaliderà quello vecchio, richiedendo che tutti i sistemi esterni che utilizzano l'API vengano aggiornati con il nuovo token.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Accedi a questa sezione solo se stai integrando il modulo GPSR con sistemi esterni (es. ERP, PIM). Mantieni il tuo token API al sicuro.

#### 2.2.11 Cron (Back Office > GPSR Enterprise > Cron)

Questa schermata gestisce le attività pianificate del modulo, come la reindicizzazione dei dati GPSR o la sincronizzazione delle informazioni.

*   **Azioni e Impostazioni Disponibili:**
    *   **URL Cron Job:** L'URL per attivare il cron job esternamente (es. tramite il servizio cron del tuo provider di hosting).
    *   **Token Cron:** Il token univoco per l'esecuzione sicura del cron job.
    *   **Abilita/Disabilita Cron:** Un interruttore per attivare o disattivare il cron job.
    *   **Ultima Esecuzione/Risultato:** Informazioni sull'ultima volta che il cron job è stato eseguito e il suo esito.
    *   **Impostazioni di Reindicizzazione:** Opzioni per la frequenza e il numero di prodotti da reindicizzare per esecuzione (es. `GPSR_CRON_REINDEX_OFFSET`, `GPSR_CRON_REINDEX_LIMIT`).
*   **Effetto delle modifiche:** L'abilitazione del cron job assicura che i dati GPSR vengano regolarmente elaborati e aggiornati in background, mantenendo aggiornate le informazioni del tuo front-office. Impostazioni cron errate possono portare a dati obsoleti o problemi di carico del server.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Assicurati che il cron job sia abilitato e configurato correttamente sul tuo server di hosting per automatizzare l'elaborazione dei dati. Monitora il suo stato sulla dashboard.

### 2.3 Tabella di Riferimento Rapido alla Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| **Configurazione Modulo** | Modulo abilitato | Sì | Interruttore principale per la funzionalità del modulo. |
| | Profilo tema storefront | Corrisponde al tuo tema | Ottimizza lo stile visivo per i temi Classic o Hummingbird. |
| | Modalità di visualizzazione | Tab / Accordion | Come appare il blocco GPSR (Tab, Accordion, Block). |
| | Stile visivo | Default / Minimal | Estetica del blocco informazioni GPSR. |
| | Mostra titolo blocco | Sì | Visualizza un titolo sopra il blocco GPSR. |
| | Testo titolo blocco | "Sicurezza e Conformità del Prodotto" | Testo personalizzato per il titolo del blocco. |
| | Nascondi blocco quando i dati sono incompleti | Sì | Impedisce la visualizzazione di informazioni GPSR incomplete. |
| | Mostra entità produttore | Sì | Visualizza i dettagli del produttore. |
| | Mostra persona responsabile UE | Sì | Visualizza i dettagli della persona responsabile UE. |
| | Mostra avvisi di sicurezza | Sì | Visualizza gli avvisi di sicurezza del prodotto. |
| | Mostra documenti collegati | Sì | Visualizza i link ai documenti del prodotto. |
| | Mostra pulsante passaporto del prodotto | Sì | Visualizza il pulsante per scaricare il passaporto del prodotto PDF. |
| | Condividi mappature tra tutti i negozi | Sì (se multi-negozio) | Centralizza le mappature GPSR per il multi-negozio. |
| | Azione all'abilitazione della condivisione | (Scelta attenta) | Definisce la gestione dei dati all'abilitazione delle mappature condivise. |
| | Azione alla disabilitazione della condivisione | (Scelta attenta) | Definisce la gestione dei dati alla disabilitazione delle mappature condivise. |
| | CSS personalizzato | Vuoto | Aggiungi CSS personalizzato per lo stile del front-office. |
| **Entità** | Aggiungi/Modifica Entità | N/A | Definisci produttori e persone responsabili UE. |
| **Avvisi** | Aggiungi/Modifica Avviso | N/A | Crea e gestisci avvisi di sicurezza. |
| **Documenti** | Carica/Gestisci Documento | N/A | Carica e collega documenti relativi al prodotto. |
| **Mappature** | Mappature Globali/Categoria/Produttore/Prodotto | N/A | Assegna i dati GPSR in base ai criteri del prodotto. |
| **Azioni di Massa** | Assegnazione/Rimozione in Blocco | N/A | Applica/rimuovi i dati GPSR per più prodotti. |
| **Matcher** | Rivedi Suggerimenti | N/A | Identifica i prodotti che necessitano di dati GPSR. |
| **Registro di Controllo** | Visualizza Registro | N/A | Traccia le modifiche apportate ai dati GPSR. |
| **Registro** | Visualizza/Esporta Dati | N/A | Registro completo dei dati GPSR del prodotto. |
| **API** | Token API, Genera Nuovo Token | N/A | Gestisci l'accesso API per integrazioni esterne. |
| **Cron** | URL Cron Job, Abilita/Disabilita | Abilitato | Automatizza l'elaborazione dei dati GPSR in background. |

## 3. Risoluzione dei Problemi per il Commerciante e Domande Frequenti (FAQ)

**D: Ho configurato tutto, ma il blocco GPSR non viene visualizzato sulle mie pagine prodotto.**
R:
1.  **Controlla "Modulo abilitato":** Vai su **Moduli > Gestione moduli > GPSR Enterprise > Configura** e assicurati che "Modulo abilitato" sia impostato su "Sì".
2.  **Controlla "Nascondi blocco quando i dati sono incompleti":** Se questa opzione è impostata su "Sì", il blocco non verrà visualizzato se mancano dati richiesti (produttore, persona responsabile UE, avvisi, documenti) per quel prodotto specifico. Assicurati che il prodotto abbia dati GPSR completi assegnati tramite mappature o modifiche dirette del prodotto.
3.  **Svuota Cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte, il vecchio contenuto memorizzato nella cache impedisce la visualizzazione di nuovi elementi del modulo.
4.  **Compatibilità Tema:** Assicurati che l'impostazione "Profilo tema storefront" corrisponda al tuo tema (Classic o Hummingbird). Se hai un tema altamente personalizzato, potrebbe esserci un conflitto CSS. Prova ad aggiungere del CSS personalizzato per forzare la visibilità o contatta il supporto.

**D: Il mio blocco informazioni GPSR ha un aspetto strano o è disallineato sul mio sito web.**
R:
1.  **Profilo Tema:** Ricontrolla l'impostazione "Profilo tema storefront" nella configurazione del modulo. Assicurati che sia impostato sul profilo corretto per il tuo tema PrestaShop (Classic o Hummingbird).
2.  **CSS Personalizzato:** Se hai CSS personalizzato nel tuo tema o nel campo "CSS personalizzato" del modulo, potrebbe essere in conflitto. Prova a rimuovere temporaneamente il CSS personalizzato per vedere se il problema si risolve.
3.  **Cache del Browser:** Svuota la cache del tuo browser (Ctrl+F5 o Cmd+R) per assicurarti di visualizzare lo stile più recente.
4.  **Contatta il Supporto:** Se il problema persiste, il tuo tema potrebbe avere uno stile unico che richiede aggiustamenti specifici. Contatta il supporto MyPresta.eu con screenshot e il nome del tuo tema.

**D: Come mi assicuro che i miei dati GPSR siano tradotti per i clienti internazionali?**
R:
1.  **Campi Multilingue:** Quando crei **Entità** e **Avvisi**, assicurati di compilare il contenuto per tutte le lingue abilitate nel tuo negozio. Cerca le bandiere delle lingue accanto ai campi di input.
2.  **Traduzioni PrestaShop:** Per le frasi predefinite del modulo (come "Scarica Passaporto del Prodotto" o il titolo del blocco), vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", scegli "GPSR Enterprise" e seleziona la tua lingua di destinazione. Traduci eventuali frasi mancanti lì.
3.  **Passaporto del Prodotto:** Il Passaporto del Prodotto PDF generato rifletterà la lingua dei dati del prodotto e degli avvisi che hai inserito.

**D: Il cron job non sembra essere in esecuzione, o i miei dati non si aggiornano automaticamente.**
A:
1.  **Cron Abilitato:** Nella schermata **Cron** del modulo (Back Office > GPSR Enterprise > Cron), assicurati che il cron job sia abilitato.
2.  **Configurazione Cron Hosting:** Verifica di aver configurato correttamente il cron job sul tuo server di hosting utilizzando l'"URL Cron Job" e il "Token Cron" forniti. Questo viene solitamente fatto nel pannello di controllo del tuo hosting (cPanel, Plesk, ecc.). Il cron job deve essere attivato periodicamente (es. ogni ora).
3.  **Stato Ultima Esecuzione:** Controlla "Ultima Esecuzione" e "Ultimo Risultato" nella schermata Cron. Se mostra errori o non è stato eseguito di recente, c'è un problema con la configurazione del cron o un problema lato server.
4.  **Log del Server:** Controlla i log degli errori PHP del tuo server per eventuali messaggi relativi all'esecuzione del cron job.

**D: Ho commesso un errore con un'azione di massa e ora molti prodotti hanno dati GPSR errati.**
R:
1.  **Registro di Controllo:** Controlla immediatamente il **Registro di Controllo** (Back Office > GPSR Enterprise > Registro di Controllo) per identificare esattamente quali modifiche sono state apportate e da chi.
2.  **Annulla Manualmente/Tramite Azioni di Massa:** A seconda dell'entità dell'errore, potresti dover utilizzare nuovamente la schermata **Azioni di Massa** per correggere i dati, o modificare manualmente le mappature dei singoli prodotti se solo pochi sono stati interessati.
3.  **Backup del Database:** Se l'errore è grave e diffuso, e hai un backup recente del database da *prima* dell'errore, il ripristino di quel backup potrebbe essere la soluzione più rapida. Questo è il motivo per cui i backup regolari sono cruciali.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo GPSR Enterprise, destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'Architettura

Il modulo GPSR Enterprise aderisce al pattern MVC (Model-View-Controller) di PrestaShop, estendendo le funzionalità principali e introducendo entità personalizzate. Sfrutta `ObjectModel` per le interazioni con il database, `ModuleFrontController` per la consegna dei dati nel front-office (API, cron, generazione del passaporto) e `AdminController` per la gestione completa del back-office. Il modulo si basa fortemente sugli hook per l'integrazione nelle pagine dei prodotti e nelle interfacce amministrative, garantendo una soluzione non intrusiva ma potente. La mappatura dei dati è gerarchica, consentendo override globali, per categoria, per produttore e specifici per prodotto.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

*   `controllers/front/api.php`
    *   **Nome Classe:** `GpsrEnterpriseApiModuleFrontController`
    *   **Classe Padre:** `ModuleFrontController`
    *   **Responsabilità:** Gestisce le richieste API per i dati GPSR. Fornisce endpoint per sistemi esterni per interrogare informazioni sulla sicurezza dei prodotti, entità, avvisi e documenti. Richiede autenticazione tramite `GPSR_API_TOKEN`. Restituisce payload JSON.
*   `controllers/front/cron.php`
    *   **Nome Classe:** `GpsrEnterpriseCronModuleFrontController`
    *   **Classe Padre:** `ModuleFrontController`
    *   **Responsabilità:** Serve come endpoint per le attività pianificate (cron job). Attiva processi in background come la reindicizzazione dei dati GPSR, la sincronizzazione delle mappature o l'esecuzione della pulizia dei dati. Richiede autenticazione tramite `GPSR_CRON_TOKEN`.
*   `controllers/front/data.php`
    *   **Nome Classe:** `GpsrEnterpriseDataModuleFrontController`
    *   **Classe Padre:** `ModuleFrontController`
    *   **Responsabilità:** Fornisce endpoint AJAX per il recupero dinamico dei dati GPSR sulla pagina del prodotto nel front-office. Questo controller probabilmente recupera il produttore specifico, la persona responsabile UE, gli avvisi e i documenti per un dato ID prodotto o ID combinazione.
*   `controllers/front/index.php`
    *   **Nome Classe:** `GpsrEnterpriseIndexModuleFrontController`
    *   **Classe Padre:** `ModuleFrontController`
    *   **Responsabilità:** Un controller frontale segnaposto o di fallback. Spesso utilizzato per il routing di base del modulo o per impedire l'elenco delle directory.
*   `controllers/front/passport.php`
    *   **Nome Classe:** `GpsrEnterprisePassportModuleFrontController`
    *   **Classe Padre:** `ModuleFrontController`
    *   **Responsabilità:** Genera e serve il Passaporto del Prodotto PDF per un prodotto specificato. Raccoglie tutti i dati GPSR pertinenti per il prodotto e li rende in un documento PDF scaricabile.

#### Controller Admin Back-Office

Tutti i controller admin estendono `GpsrAdminController` (una classe base personalizzata all'interno del modulo) che a sua volta estende `ModuleAdminController`.

*   `controllers/admin/AdminGpsrAuditController.php`
    *   **Nome Tab:** GPSR Enterprise > Registro di Controllo
    *   **Entità Gestita:** `GpsrAuditLogEntry`
    *   **Responsabilità:** Gestisce la visualizzazione e il filtraggio della tabella `gpsr_audit_log`, registrando tutte le modifiche significative apportate all'interno del modulo GPSR.
*   `controllers/admin/AdminGpsrController.php`
    *   **Nome Tab:** GPSR Enterprise (punto di ingresso principale)
    *   **Responsabilità:** Probabilmente funge da dashboard principale o da reindirizzamento alla schermata principale di configurazione/dashboard per il modulo.
*   `controllers/admin/AdminGpsrDocumentsController.php`
    *   **Nome Tab:** GPSR Enterprise > Documenti
    *   **Entità Gestita:** `GpsrDocument` (implicito, poiché nessuna classe specifica è stata elencata, ma gestisce i documenti)
    *   **Responsabilità:** Gestisce il caricamento, l'elenco e la gestione dei documenti relativi al GPSR (es. PDF).
*   `controllers/admin/AdminGpsrEnterpriseController.php`
    *   **Nome Tab:** GPSR Enterprise > Dashboard (o configurazione principale)
    *   **Responsabilità:** Gestisce le impostazioni di configurazione principali del modulo, inclusi i token API/Cron, le opzioni di visualizzazione globali e la condivisione multi-negozio.
*   `controllers/admin/AdminGpsrEntitiesController.php`
    *   **Nome Tab:** GPSR Enterprise > Entità
    *   **Entità Gestita:** `GpsrEntity`
    *   **Responsabilità:** Gestisce la creazione, la modifica e l'eliminazione delle entità GPSR (produttori, persone responsabili UE).
*   `controllers/admin/AdminGpsrLedgerController.php`
    *   **Nome Tab:** GPSR Enterprise > Registro
    *   **Responsabilità:** Fornisce una vista completa e un'interfaccia di gestione per il "registro silente" dei dati GPSR associati ai prodotti, potenzialmente inclusi i dati storici.
*   `controllers/admin/AdminGpsrMapBrandsController.php`
    *   **Nome Tab:** GPSR Enterprise > Mappature > Marche
    *   **Entità Gestita:** `Manufacturer` (core di PrestaShop)
    *   **Responsabilità:** Gestisce le mappature dei dati GPSR basate sui produttori di PrestaShop.
*   `controllers/admin/AdminGpsrMapCategoriesController.php`
    *   **Nome Tab:** GPSR Enterprise > Mappature > Categorie
    *   **Entità Gestita:** `Category` (core di PrestaShop)
    *   **Responsabilità:** Gestisce le mappature dei dati GPSR basate sulle categorie di PrestaShop.
*   `controllers/admin/AdminGpsrMapCombinationsController.php`
    *   **Nome Tab:** GPSR Enterprise > Mappature > Combinazioni
    *   **Entità Gestita:** `ProductCombination` (implicito)
    *   **Responsabilità:** Gestisce le mappature dei dati GPSR per specifiche combinazioni di attributi del prodotto.
*   `controllers/admin/AdminGpsrMapGlobalController.php`
    *   **Nome Tab:** GPSR Enterprise > Mappature > Globale
    *   **Responsabilità:** Gestisce le mappature globali dei dati GPSR che si applicano come impostazione predefinita a tutti i prodotti.
*   `controllers/admin/AdminGpsrMassController.php`
    *   **Nome Tab:** GPSR Enterprise > Azioni di Massa
    *   **Responsabilità:** Fornisce strumenti per l'assegnazione e la rimozione in blocco dei dati GPSR a più prodotti.
*   `controllers/admin/AdminGpsrMatcherController.php`
    *   **Nome Tab:** GPSR Enterprise > Matcher
    *   **Entità Gestita:** `GpsrMatchSuggestion`
    *   **Responsabilità:** Gestisce i suggerimenti per i prodotti che potrebbero aver bisogno di dati GPSR o avere mappature incomplete.
*   `controllers/admin/AdminGpsrWarningsController.php`
    *   **Nome Tab:** GPSR Enterprise > Avvisi
    *   **Entità Gestita:** `GpsrWarning`
    *   **Responsabilità:** Gestisce la creazione, la modifica e l'eliminazione degli avvisi di sicurezza.
*   `controllers/admin/index.php`
    *   **Responsabilità:** File `index.php` vuoto standard di PrestaShop per impedire l'elenco delle directory.

### 4.3 Classi e Modelli Core (`classes/`)

*   `classes/GpsrAdminController.php`
    *   **Responsabilità:** Una classe base personalizzata per tutti i controller admin all'interno del modulo GPSR. Probabilmente fornisce metodi, proprietà e variabili di template comuni utilizzati in tutte le interfacce del back-office del modulo, garantendo coerenza e riducendo la duplicazione del codice.
*   `classes/GpsrAuditLogEntry.php`
    *   **Estende:** `ObjectModel`
    *   **Tabella Database:** `ps_gpsr_audit_log`
    *   **Campi `$definition`:** `id_gpsr_audit_log`, `id_employee`, `action`, `object_type`, `object_id`, `details`, `date_add`
    *   **Metodi pubblici chiave:** Metodi per la registrazione delle voci di audit, il recupero dei dati di log.
    *   **Logica di Business:** Registra ogni azione significativa eseguita all'interno del modulo GPSR per l'audit e la conformità.
*   `classes/GpsrCompatibility.php`
    *   **Responsabilità:** Gestisce i livelli di compatibilità per diverse versioni di PrestaShop (1.7.x, 8.x, 9.x). Questa classe probabilmente contiene metodi statici per astrarre le differenze specifiche della versione nelle chiamate API, nei nomi degli hook o nel rendering dei template, garantendo che il modulo funzioni senza problemi su tutte le versioni supportate.
*   `classes/GpsrEntity.php`
    *   **Estende:** `ObjectModel`
    *   **Tabella Database:** `ps_gpsr_entity` (e `ps_gpsr_entity_lang` per i campi multilingue)
    *   **Campi `$definition`:** `id_gpsr_entity`, `type`, `name`, `address`, `contact_email`, `contact_phone`, `contact_website`, `active`, `date_add`, `date_upd` (e campi multilingue come `name_lang`, `address_lang` ecc.)
    *   **Metodi pubblici chiave:** Metodi per operazioni CRUD sulle entità, recupero delle entità per tipo, associazione delle entità con prodotti/mappature.
    *   **Logica di Business:** Gestisce i dati per i produttori e le persone responsabili UE.
*   `classes/GpsrWarning.php`
    *   **Estende:** `ObjectModel`
    *   **Tabella Database:** `ps_gpsr_warning` (e `ps_gpsr_warning_lang` per i campi multilingue)
    *   **Campi `$definition`:** `id_gpsr_warning`, `icon`, `active`, `date_add`, `date_upd` (e campi multilingue come `title`, `content`)
    *   **Metodi pubblici chiave:** Metodi per operazioni CRUD sugli avvisi, recupero degli avvisi per ID, associazione degli avvisi con prodotti/mappature.
    *   **Logica di Business:** Gestisce i dati per gli avvisi di sicurezza.
*   `classes/index.php`
    *   **Responsabilità:** File `index.php` vuoto standard di PrestaShop per impedire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

*   `gpsrenterprise/lib/searchTool/views/js/autocomplete.js`
    *   **Ambito:** Probabilmente Back-office.
    *   **Responsabilità:** Fornisce funzionalità di completamento automatico per i campi di ricerca all'interno dell'interfaccia di amministrazione, possibilmente per la selezione di prodotti, categorie o entità nelle schermate di mappatura.
*   `gpsrenterprise/views/js/admin-api.js`
    *   **Ambito:** Back-office (AdminGpsrEnterpriseController, scheda API).
    *   **Responsabilità:** Gestisce le interazioni AJAX per la schermata di configurazione API, come la generazione di nuovi token API o la visualizzazione di modali di documentazione API.
*   `gpsrenterprise/views/js/admin-combination-map.js`
    *   **Ambito:** Back-office (AdminGpsrMapCombinationsController).
    *   **Responsabilità:** Gestisce l'interfaccia utente e le chiamate AJAX per la mappatura dei dati GPSR a specifiche combinazioni di prodotti. Ciò probabilmente comporta il caricamento dinamico degli elenchi di combinazioni e la gestione delle assegnazioni.
*   `gpsrenterprise/views/js/admin-combination-picker.js`
    *   **Ambito:** Back-office (scheda pagina prodotto, moduli di mappatura).
    *   **Responsabilità:** Fornisce un componente UI per la selezione delle combinazioni di prodotti, spesso utilizzato all'interno dei moduli di mappatura o della scheda di modifica del prodotto.
*   `gpsrenterprise/views/js/admin-country-rules.js`
    *   **Ambito:** Back-office (Potenzialmente all'interno di moduli di entità o avvisi).
    *   **Responsabilità:** Gestisce la logica dell'interfaccia utente per l'applicazione delle regole GPSR basate su paesi specifici, se il modulo supporta la conformità specifica per paese.
*   `gpsrenterprise/views/js/admin-entity-picker.js`
    *   **Ambito:** Back-office (moduli di mappatura, scheda pagina prodotto).
    *   **Responsabilità:** Fornisce un componente UI per la selezione di istanze `GpsrEntity` (produttori, persone responsabili UE) da un menu a discesa o un'interfaccia di ricerca.
*   `gpsrenterprise/views/js/admin-icon-picker-data.js`
    *   **Ambito:** Back-office (moduli di avviso).
    *   **Responsabilità:** Contiene dati (es. un array di nomi/percorsi di icone) utilizzati da `admin-icon-picker.js`.
*   `gpsrenterprise/views/js/admin-icon-picker.js`
    *   **Ambito:** Back-office (moduli di avviso).
    *   **Responsabilità:** Implementa un componente UI per la selezione visiva di un'icona da associare a un `GpsrWarning`.
*   `gpsrenterprise/views/js/admin-identifier-shortcodes.js`
    *   **Ambito:** Back-office (aree di testo nei moduli, es. per i template del passaporto del prodotto).
    *   **Responsabilità:** Fornisce funzionalità per inserire "shortcode" o segnaposto predefiniti nei campi di testo, che verranno sostituiti dinamicamente con i dati del prodotto quando renderizzati.
*   `gpsrenterprise/views/js/admin-item-picker.js`
    *   **Ambito:** Back-office (moduli di mappatura generali).
    *   **Responsabilità:** Un componente UI generico per la selezione di vari elementi (prodotti, categorie, documenti, avvisi) da un elenco o una ricerca.
*   `gpsrenterprise/views/js/admin-mass-grid.js`
    *   **Ambito:** Back-office (AdminGpsrMassController).
    *   **Responsabilità:** Gestisce la griglia interattiva dei prodotti e la funzionalità di azioni in blocco nella schermata "Azioni di Massa".
*   `gpsrenterprise/views/js/admin-product-tab.js`
    *   **Ambito:** Back-office (pagina di modifica del prodotto).
    *   **Responsabilità:** Inietta e gestisce la scheda GPSR personalizzata nella pagina di modifica del prodotto di PrestaShop, consentendo l'assegnazione diretta dei dati GPSR ai singoli prodotti.
*   `gpsrenterprise/views/js/adminGpsrDashboard.js`
    *   **Ambito:** Back-office (dashboard AdminGpsrController/AdminGpsrEnterpriseController).
    *   **Responsabilità:** Gestisce elementi dinamici e aggiornamenti AJAX sulla dashboard del modulo, come l'aggiornamento dello stato del cron o la visualizzazione delle statistiche.
*   `gpsrenterprise/views/js/front.js`
    *   **Ambito:** Front-office.
    *   **Responsabilità:** JavaScript principale per il blocco informazioni GPSR del front-office. Gestisce il caricamento dinamico dei dati (tramite il controller `data.php`), la funzionalità di schede/accordion e potenzialmente le interazioni con il pulsante del Passaporto del Prodotto.
*   `gpsrenterprise/views/js/gpsr-barcode.js`
    *   **Ambito:** Front-office o Back-office (generazione del Passaporto del Prodotto).
    *   **Responsabilità:** Probabilmente uno script di utilità per la generazione o la visualizzazione di codici a barre, potenzialmente utilizzato all'interno del PDF del Passaporto del Prodotto o per l'identificazione del prodotto.

### 4.5 Fogli di Stile CSS (`views/css/`)

*   `gpsrenterprise/lib/searchTool/views/css/autocomplete.css`
    *   **Ambito:** Back-office.
    *   **Responsabilità:** Stili per i campi di ricerca con completamento automatico utilizzati nell'interfaccia di amministrazione.
*   `gpsrenterprise/views/css/admin-api.css`
    *   **Ambito:** Back-office (AdminGpsrEnterpriseController, scheda API).
    *   **Responsabilità:** Stili specifici per la configurazione API e la visualizzazione della documentazione.
*   `gpsrenterprise/views/css/admin-combination-map.css`
    *   **Ambito:** Back-office (AdminGpsrMapCombinationsController).
    *   **Responsabilità:** Stili per l'interfaccia di mappatura delle combinazioni.
*   `gpsrenterprise/views/css/admin-combination-picker.css`
    *   **Ambito:** Back-office.
    *   **Responsabilità:** Stili per il componente di selezione delle combinazioni di prodotti.
*   `gpsrenterprise/views/css/admin-config.css`
    *   **Ambito:** Back-office (pagina di configurazione del modulo).
    *   **Responsabilità:** Stili generali per il modulo di configurazione principale.
*   `gpsrenterprise/views/css/admin-country-rules.css`
    *   **Ambito:** Back-office.
    *   **Responsabilità:** Stili per le interfacce di configurazione delle regole specifiche per paese.
*   `gpsrenterprise/views/css/admin-dashboard.css`
    *   **Ambito:** Back-office (dashboard AdminGpsrController/AdminGpsrEnterpriseController).
    *   **Responsabilità:** Stili per la dashboard amministrativa del modulo.
*   `gpsrenterprise/views/css/admin-help.css`
    *   **Ambito:** Back-office.
    *   **Responsabilità:** Stili per testi di aiuto, tooltip o sezioni di documentazione all'interno dell'amministrazione.
*   `gpsrenterprise/views/css/admin-item-picker.css`
    *   **Ambito:** Back-office.
    *   **Responsabilità:** Stili per il componente generico di selezione degli elementi.
*   `gpsrenterprise/views/css/admin-list-enhanced.css`
    *   **Ambito:** Back-office.
    *   **Responsabilità:** Miglioramenti allo stile predefinito dell'elenco/griglia di PrestaShop per una migliore leggibilità o funzionalità.
*   `gpsrenterprise/views/css/admin-mass-grid.css`
    *   **Ambito:** Back-office (AdminGpsrMassController).
    *   **Responsabilità:** Stili per la griglia dei prodotti delle azioni di massa.
*   `gpsrenterprise/views/css/admin-nav.css`
    *   **Ambito:** Back-office.
    *   **Responsabilità:** Stili per le schede di navigazione personalizzate del modulo o le voci di menu all'interno dell'amministrazione.
*   `gpsrenterprise/views/css/admin-product-tab.css`
    *   **Ambito:** Back-office (pagina di modifica del prodotto).
    *   **Responsabilità:** Stili per la scheda GPSR aggiunta alla pagina di modifica del prodotto di PrestaShop.
*   `gpsrenterprise/views/css/front-classic.css`
    *   **Ambito:** Front-office (tema Classic).
    *   **Responsabilità:** Stile specifico per il blocco GPSR quando è selezionato il profilo del tema "Classic".
*   `gpsrenterprise/views/css/front-hummingbird.css`
    *   **Ambito:** Front-office (tema Hummingbird).
    *   **Responsabilità:** Stile specifico per il blocco GPSR quando è selezionato il profilo del tema "Hummingbird".
*   `gpsrenterprise/views/css/front.css`
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Stile generale di base per il blocco informazioni GPSR sul storefront, applicato indipendentemente dal profilo del tema, che viene poi potenzialmente sovrascritto da `front-classic.css` o `front-hummingbird.css`.

### 4.6 Struttura dei Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

*   `gpsrenterprise/views/templates/hook/product-gpsr-classic.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (a seconda della configurazione)
    *   **Output:** Il blocco informazioni GPSR principale per la pagina del prodotto nel front-office, specificamente stilizzato per il profilo del tema Classic.
*   `gpsrenterprise/views/templates/hook/product-gpsr-hummingbird.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (a seconda della configurazione)
    *   **Output:** Il blocco informazioni GPSR principale per la pagina del prodotto nel front-office, specificamente stilizzato per il profilo del tema Hummingbird.
*   `gpsrenterprise/views/templates/hook/product-gpsr.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (a seconda della configurazione)
    *   **Output:** Un template generico o di base per il blocco informazioni GPSR, che potrebbe includere la logica per caricare i template specifici per classic o hummingbird in base alla configurazione del modulo.
*   `gpsrenterprise/views/templates/hook/_product-gpsr-attrs.tpl`
    *   **Hook:** Template parziale interno.
    *   **Output:** Rende attributi o dettagli specifici all'interno del blocco principale del prodotto GPSR, come avvisi individuali, dettagli dell'entità o link ai documenti. Questo è probabilmente incluso da `product-gpsr.tpl` o dalle sue varianti specifiche per tema.

#### Template Admin (`views/templates/admin/`)

*   `gpsrenterprise/lib/searchTool/views/scripts.tpl`
    *   **Output:** Contiene JavaScript o logica Smarty per la funzionalità dello strumento di ricerca, probabilmente inclusa in varie pagine di amministrazione.
*   `gpsrenterprise/views/templates/admin/api.tpl`
    *   **Output:** Rende il contenuto per la schermata di configurazione API, inclusa la visualizzazione del token, il pulsante di generazione e il link alla documentazione.
*   `gpsrenterprise/views/templates/admin/back-office.tpl`
    *   **Output:** Un template generico del back-office, possibilmente per la dashboard principale del modulo o un wrapper per altre viste di amministrazione.
*   `gpsrenterprise/views/templates/admin/combination-list.tpl`
    *   **Output:** Visualizza un elenco di combinazioni di prodotti, utilizzato nelle interfacce di mappatura o di selezione.
*   `gpsrenterprise/views/templates/admin/combination-picker.tpl`
    *   **Output:** Rende l'interfaccia utente per la selezione delle combinazioni di prodotti.
*   `gpsrenterprise/views/templates/admin/combination-script.tpl`
    *   **Output:** Contiene JavaScript specifico per la gestione delle combinazioni, probabilmente incluso nelle pagine che trattano le combinazioni di prodotti.
*   `gpsrenterprise/views/templates/admin/configure.tpl`
    *   **Output:** Rende il modulo di configurazione principale del modulo (accessibile tramite Moduli > Configura).
*   `gpsrenterprise/views/templates/admin/country-rules-panel.tpl`
    *   **Output:** Rende un pannello per la gestione delle regole GPSR specifiche per paese.
*   `gpsrenterprise/views/templates/admin/cron.tpl`
    *   **Output:** Rende il contenuto per la schermata di configurazione e stato del Cron job.
*   `gpsrenterprise/views/templates/admin/dashboard.tpl`
    *   **Output:** Rende la dashboard principale del modulo con statistiche e link rapidi.
*   `gpsrenterprise/views/templates/admin/documents.tpl`
    *   **Output:** Rende l'elenco e l'interfaccia di gestione per i documenti GPSR.
*   `gpsrenterprise/views/templates/admin/entities-list.tpl`
    *   **Output:** Visualizza l'elenco delle entità GPSR configurate.
*   `gpsrenterprise/views/templates/admin/entities.tpl`
    *   **Output:** Template wrapper principale per la schermata di gestione delle Entità.
*   `gpsrenterprise/views/templates/admin/entity-form.tpl`
    *   **Output:** Rende il modulo per l'aggiunta o la modifica di un `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/entity-picker.tpl`
    *   **Output:** Rende l'interfaccia utente per la selezione di un `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/getCombinations.tpl`
    *   **Output:** Un template probabilmente utilizzato per le risposte AJAX per caricare dinamicamente le combinazioni di prodotti.
*   `gpsrenterprise/views/templates/admin/item-picker.tpl`
    *   **Output:** Rende un componente UI generico per la selezione di elementi.
*   `gpsrenterprise/views/templates/admin/ledger.tpl`
    *   **Output:** Rende la vista dettagliata del registro GPSR.
*   `gpsrenterprise/views/templates/admin/map-fields.tpl`
    *   **Output:** Un template parziale contenente campi comuni per le mappature GPSR (es. selettori di entità, selettori di avvisi).
*   `gpsrenterprise/views/templates/admin/map-form-category.tpl`
    *   **Output:** Rende il modulo per la creazione/modifica delle mappature GPSR a livello di categoria.
*   `gpsrenterprise/views/templates/admin/map-form-combination.tpl`
    *   **Output:** Rende il modulo per la creazione/modifica delle mappature GPSR a livello di combinazione di prodotto.
*   `gpsrenterprise/views/templates/admin/map-form-global.tpl`
    *   **Output:** Rende il modulo per la creazione/modifica delle mappature GPSR globali.
*   `gpsrenterprise/views/templates/admin/map-form-manufacturer.tpl`
    *   **Output:** Rende il modulo per la creazione/modifica delle mappature GPSR a livello di produttore.
*   `gpsrenterprise/views/templates/admin/mappings.tpl`
    *   **Output:** Template wrapper principale per la sezione Mappature, probabilmente inclusa la navigazione per diversi tipi di mappatura.
*   `gpsrenterprise/views/templates/admin/mass-grid.tpl`
    *   **Output:** Rende la griglia dei prodotti e i controlli delle azioni di massa per la schermata "Azioni di Massa".
*   `gpsrenterprise/views/templates/admin/matcher.tpl`
    *   **Output:** Rende l'interfaccia per il GPSR Matcher, visualizzando i suggerimenti.
*   `gpsrenterprise/views/templates/admin/nav-tabs.tpl`
    *   **Output:** Rende le schede di navigazione per le sezioni del back-office del modulo (Dashboard, Entità, Avvisi, Mappature, ecc.).
*   `gpsrenterprise/views/templates/admin/product-preview-card.tpl`
    *   **Output:** Rende una piccola scheda di anteprima per un prodotto, possibilmente utilizzata nei componenti di selezione o nelle griglie di azioni di massa.
*   `gpsrenterprise/views/templates/admin/product-tab.tpl`
    *   **Output:** Rende il contenuto della scheda GPSR personalizzata nella pagina di modifica del prodotto di PrestaShop.
*   `gpsrenterprise/views/templates/admin/warning-form.tpl`
    *   **Output:** Rende il modulo per l'aggiunta o la modifica di un `GpsrWarning`.
*   `gpsrenterprise/views/templates/admin/warnings-list.tpl`
    *   **Output:** Visualizza l'elenco degli avvisi GPSR configurati.
*   `gpsrenterprise/views/templates/admin/_api_documentation_modal.tpl`
    *   **Output:** Rende il contenuto per una finestra modale che visualizza la documentazione API.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

*   `ps_gpsr_audit_log`: Memorizza le voci del registro di controllo per le modifiche apportate all'interno del modulo.
    *   `id_gpsr_audit_log` (PK)
    *   `id_employee` (FK a `ps_employee`)
    *   `action` (es. 'add', 'edit', 'delete', 'map')
    *   `object_type` (es. 'entity', 'warning', 'product_mapping')
    *   `object_id`
    *   `details` (JSON o testo per maggiori informazioni)
    *   `date_add`
*   `ps_gpsr_entity`: Memorizza i dettagli per i produttori e le persone responsabili UE.
    *   `id_gpsr_entity` (PK)
    *   `type` (es. 'manufacturer', 'eu_responsible')
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_entity_lang`: Campi multilingue per `ps_gpsr_entity`.
    *   `id_gpsr_entity` (FK)
    *   `id_lang` (FK)
    *   `name`
    *   `address`
    *   `contact_email`
    *   `contact_phone`
    *   `contact_website`
*   `ps_gpsr_warning`: Memorizza le definizioni degli avvisi di sicurezza.
    *   `id_gpsr_warning` (PK)
    *   `icon`
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_warning_lang`: Campi multilingue per `ps_gpsr_warning`.
    *   `id_gpsr_warning` (FK)
    *   `id_lang` (FK)
    *   `title`
    *   `content`
*   `ps_gpsr_document`: Memorizza i dettagli dei documenti caricati.
    *   `id_gpsr_document` (PK)
    *   `filename`
    *   `mime_type`
    *   `file_size`
    *   `date_add`, `date_upd`
*   `ps_gpsr_document_lang`: Campi multilingue per `ps_gpsr_document` (es. `name`).
*   `ps_gpsr_product_mapping`: Assegnazioni dirette dei dati GPSR a livello di prodotto.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK, per le combinazioni)
    *   `id_gpsr_entity_manufacturer` (FK a `ps_gpsr_entity`)
    *   `id_gpsr_entity_eu_responsible` (FK a `ps_gpsr_entity`)
    *   `date_add`, `date_upd`
*   `ps_gpsr_product_warning`: Tabella di giunzione per le relazioni prodotto-avviso.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_warning` (FK)
*   `ps_gpsr_product_document`: Tabella di giunzione per le relazioni prodotto-documento.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_document` (FK)
*   `ps_gpsr_category_mapping`: Assegnazioni dei dati GPSR a livello di categoria.
    *   `id_category` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_category_warning`: Tabella di giunzione per le relazioni categoria-avviso.
*   `ps_gpsr_category_document`: Tabella di giunzione per le relazioni categoria-documento.
*   `ps_gpsr_manufacturer_mapping`: Assegnazioni dei dati GPSR a livello di produttore.
    *   `id_manufacturer` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_manufacturer_warning`: Tabella di giunzione per le relazioni produttore-avviso.
*   `ps_gpsr_manufacturer_document`: Tabella di giunzione per le relazioni produttore-documento.
*   `ps_gpsr_global_mapping`: Memorizza i dati GPSR globali predefiniti.
*   `ps_gpsr_match_suggestion`: Memorizza i suggerimenti generati dal matcher.
    *   `id_gpsr_match_suggestion` (PK)
    *   `id_product`
    *   `suggestion_type`
    *   `suggested_data` (JSON)
    *   `date_add`
*   `ps_configuration`: Le impostazioni del modulo sono memorizzate qui con chiavi come `GPSR_ENABLED`, `GPSR_CUSTOM_CSS`, `GPSR_API_TOKEN`, `GPSR_CRON_TOKEN`, ecc.

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| :-------- | :--------------- | :---------------- |
| `actionProductSave` | Dopo il salvataggio di un prodotto (aggiunta o aggiornamento). | Attiva la rivalutazione dei dati GPSR per il prodotto, aggiorna le mappature o registra le modifiche. |
| `actionAfterUpdateProductFormHandler` | Dopo l'aggiornamento di un modulo prodotto nel BO. | Aggiorna i dati GPSR visualizzati nella scheda prodotto o attiva gli aggiornamenti correlati. |
| `actionObjectProductDeleteAfter` | Dopo l'eliminazione di un oggetto prodotto. | Pulisce i dati e le mappature GPSR associati al prodotto eliminato. |
| `actionAfterCreateProductFormHandler` | Dopo la creazione di un modulo prodotto nel BO. | Inizializza i dati GPSR per un nuovo prodotto, applicando potenzialmente mappature predefinite. |
| `displayAfterProductThumbs` | Sulla pagina del prodotto, dopo le immagini del prodotto. | Rende il blocco informazioni GPSR del front-office. (Il posizionamento dipende dal tema/configurazione) |
| `actionObjectProductAddAfter` | Dopo l'aggiunta di un nuovo oggetto prodotto. | Attiva l'assegnazione iniziale dei dati GPSR per il nuovo prodotto. |
| `displayProductAdditionalInfo` | Sulla pagina del prodotto, nella sezione "Informazioni aggiuntive". | Rende il blocco informazioni GPSR del front-office, spesso come scheda. |
| `displayAdminProductsExtra` | Sulla pagina di modifica del prodotto nel Back Office. | Inietta la scheda GPSR personalizzata per la gestione dei dati specifici del prodotto. |
| `displayBackOfficeHeader` | Nell'intestazione di ogni pagina del Back Office. | Carica CSS/JS specifici del modulo per le interfacce di amministrazione, aggiunge voci di menu. |
| `actionAdminControllerSetMedia` | Quando un controller admin imposta i suoi media (CSS/JS). | Carica CSS/JS specifici del modulo per le pagine admin pertinenti. |
| `displayProductExtraContent` | Sulla pagina del prodotto, per blocchi di contenuto extra. | Rende il blocco informazioni GPSR del front-office, offrendo un posizionamento flessibile. |
| `displayFooterProduct` | Nella sezione piè di pagina della pagina del prodotto. | Rende il blocco informazioni GPSR del front-office, spesso come blocco sotto il contenuto principale. |
| `displayReassurance` | Nel blocco di rassicurazione del prodotto (es. spedizione gratuita, pagamento sicuro). | Rende il blocco informazioni GPSR del front-office, potenzialmente come un piccolo badge o link rassicurante. |
| `actionProductAttributeUpdate` | Dopo l'aggiornamento di una combinazione di prodotto (attributo). | Attiva la rivalutazione dei dati GPSR per la combinazione specifica. |
| `actionFrontControllerSetMedia` | Quando un controller frontale imposta i suoi media (CSS/JS). | Carica CSS/JS specifici del modulo per le pagine del front-office in cui vengono visualizzati i dati GPSR. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo GPSR Enterprise, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità o all'integrazione del modulo.
