---
title: "Mostra due prezzi - tasse incluse / escluse - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Mostra due prezzi - tasse incluse / escluse di MyPresta.eu."
sidebar:
  label: "Mostra due prezzi - tasse incluse / escluse - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Show two prices - tax included / excluded su MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-two-prices-tax-included-excluded.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/show-two-prices-tax-included-excluded/)
>
> ---


# Mostra due prezzi - tasse incluse / escluse

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono richieste per PrestaShop stesso e generalmente per le operazioni del modulo. Nessun requisito di hosting speciale oltre a un ambiente standard compatibile con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Mostra due prezzi - tasse incluse / escluse". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### Impostazioni generali

-   **Abilitato / Disabilitato (Interruttore globale)**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità dell'intero modulo in tutto il tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo inizierà a visualizzare entrambi i prezzi con tasse incluse ed escluse in base alle altre impostazioni.
        -   *Quando disabilitato:* Il modulo smetterà di visualizzare le informazioni aggiuntive sui prezzi e il tuo negozio tornerà al suo comportamento predefinito di visualizzazione dei prezzi.
    -   **Valore consigliato:** Abilitato (per utilizzare le funzionalità del modulo).
    -   **Scenario / esempio del commerciante:** Se stai eseguendo la manutenzione o desideri temporaneamente nascondere la visualizzazione a doppio prezzo, puoi disabilitarla qui.

#### Impostazioni pagina prodotto

-   **Mostra nella pagina prodotto (BF\_PP)**

    -   **Cosa fa questa impostazione:** Controlla se entrambi i prezzi con tasse incluse ed escluse vengono visualizzati nelle singole pagine di dettaglio del prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Entrambi i prezzi appariranno nelle pagine prodotto.
        -   *Quando disabilitato:* Solo il prezzo predefinito di PrestaShop (solitamente con tasse incluse) verrà mostrato nelle pagine prodotto.
    -   **Valore consigliato:** Attivo (per fornire piena trasparenza).
    -   **Scenario / esempio del commerciante:** Se desideri mostrare i prezzi doppi solo negli elenchi di categoria ma mantenere le pagine prodotto più pulite, potresti disabilitare questa opzione.
-   **Nascondi prezzo tasse incluse nella pagina prodotto (BOTH\_HIDE\_P)**

    -   **Cosa fa questa impostazione:** Se "Mostra nella pagina prodotto" è abilitato, questa opzione ti consente di nascondere il prezzo con tasse incluse, mostrando di fatto solo il prezzo con tasse escluse accanto al prezzo originale (se non nascosto).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il prezzo con tasse incluse sarà nascosto nelle pagine prodotto.
        -   *Quando disabilitato:* Il prezzo con tasse incluse sarà visibile nelle pagine prodotto (se "Mostra nella pagina prodotto" è abilitato).
    -   **Valore consigliato:** Disattivato (a meno che tu non abbia un motivo specifico per nasconderlo, ad esempio, un negozio focalizzato sul B2B).
    -   **Scenario / esempio del commerciante:** Un negozio B2B potrebbe voler enfatizzare i prezzi con tasse escluse e nascondere il prezzo con tasse incluse per semplificare la visualizzazione per i propri clienti aziendali.
-   **CSS personalizzato per la pagina prodotto (BF\_PPC)**

    -   **Cosa fa questa impostazione:** Ti consente di aggiungere regole CSS personalizzate specificamente per la visualizzazione a doppio prezzo nelle pagine prodotto. Questo è per utenti avanzati o webmaster.
    -   **Effetto della modifica di questa impostazione:** Qualsiasi codice CSS inserito qui verrà applicato agli elementi di prezzo del modulo nelle pagine prodotto, consentendoti di modificare colori, font, dimensioni o posizionamento.
    -   **Valore consigliato:** Lasciare vuoto a meno che tu non abbia esigenze di stile specifiche.
    -   **Scenario / esempio del commerciante:** Potresti voler rendere il prezzo con tasse escluse più piccolo o di un colore diverso rispetto al prezzo con tasse incluse per differenziarli visivamente.
-   **Forza nascondi pagina prodotto (BP\_FORCE\_HIDE)**

    -   **Cosa fa questa impostazione:** Questa è un'opzione più aggressiva per nascondere l'output del modulo nella pagina prodotto. Può essere utile se l'output del modulo è in conflitto con il tuo tema o altri moduli.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo tenterà di nascondere forzatamente la sua visualizzazione dei prezzi nelle pagine prodotto, indipendentemente dalle altre impostazioni.
        -   *Quando disabilitato:* Il modulo visualizzerà i prezzi in base alle altre impostazioni.
    -   **Valore consigliato:** Disattivato (abilitare solo se si verificano problemi di visualizzazione).
    -   **Scenario / esempio del commerciante:** Se la visualizzazione a doppio prezzo si sovrappone a un altro elemento nella tua pagina prodotto, l'abilitazione di questa opzione potrebbe risolvere il conflitto.
-   **Etichetta prezzo tasse incluse (BP\_TIN)**

    -   **Cosa fa questa impostazione:** Definisce l'etichetta di testo visualizzata accanto al prezzo con tasse incluse nelle pagine prodotto.
    -   **Effetto della modifica di questa impostazione:** Modifica il testo dell'etichetta.
    -   **Valore consigliato:** "Tasse incl." o "IVA incl."
    -   **Scenario / esempio del commerciante:** Potresti cambiarlo in "Prezzo con IVA" per chiarezza in alcune regioni.
-   **Etichetta prezzo tasse escluse (BP\_TEX)**

    -   **Cosa fa questa impostazione:** Definisce l'etichetta di testo visualizzata accanto al prezzo con tasse escluse nelle pagine prodotto.
    -   **Effetto della modifica di questa impostazione:** Modifica il testo dell'etichetta.
    -   **Valore consigliato:** "Tasse escl." o "IVA escl."
    -   **Scenario / esempio del commerciante:** Potresti cambiarlo in "Prezzo senza IVA" per chiarezza.
-   **Etichetta prezzo originale tasse incluse (BP\_O\_TIN)**

    -   **Cosa fa questa impostazione:** Definisce l'etichetta di testo per il prezzo *originale* con tasse incluse, particolarmente utile quando vengono applicati prezzi specifici o sconti.
    -   **Effetto della modifica di questa impostazione:** Modifica il testo dell'etichetta.
    -   **Valore consigliato:** "Tasse incl. originali"
    -   **Scenario / esempio del commerciante:** Quando un prodotto è in saldo, potresti voler mostrare il prezzo originale con un'etichetta specifica.

#### Impostazioni pagina elenco prodotti

-   **Mostra nell'elenco prodotti (BF\_PL)**

    -   **Cosa fa questa impostazione:** Controlla se entrambi i prezzi con tasse incluse ed escluse vengono visualizzati nelle pagine di elenco prodotti (categorie, risultati di ricerca, moduli della homepage).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Entrambi i prezzi appariranno nelle pagine di elenco prodotti.
        -   *Quando disabilitato:* Solo il prezzo predefinito di PrestaShop verrà mostrato nelle pagine di elenco prodotti.
    -   **Valore consigliato:** Attivo (per una trasparenza coerente).
    -   **Scenario / esempio del commerciante:** Se le tue pagine di categoria sono molto dense, potresti disabilitare questa opzione per ridurre l'ingombro visivo.
-   **Nascondi prezzo tasse incluse nell'elenco prodotti (BOTH\_HIDE\_PL)**

    -   **Cosa fa questa impostazione:** Se "Mostra nell'elenco prodotti" è abilitato, questa opzione ti consente di nascondere il prezzo con tasse incluse nelle pagine di elenco.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il prezzo con tasse incluse sarà nascosto nelle pagine di elenco prodotti.
        -   *Quando disabilitato:* Il prezzo con tasse incluse sarà visibile nelle pagine di elenco prodotti.
    -   **Valore consigliato:** Disattivato (a meno che tu non abbia un motivo specifico per nasconderlo).
    -   **Scenario / esempio del commerciante:** Un negozio B2B potrebbe voler mostrare solo i prezzi con tasse escluse in tutti gli elenchi di prodotti.
-   **CSS personalizzato per l'elenco prodotti (BF\_PLC)**

    -   **Cosa fa questa impostazione:** Ti consente di aggiungere regole CSS personalizzate specificamente per la visualizzazione a doppio prezzo nelle pagine di elenco prodotti.
    -   **Effetto della modifica di questa impostazione:** Qualsiasi codice CSS inserito qui verrà applicato agli elementi di prezzo del modulo nelle pagine di elenco.
    -   **Valore consigliato:** Lasciare vuoto a meno che tu non abbia esigenze di stile specifiche.
    -   **Scenario / esempio del commerciante:** Potresti voler che il prezzo con tasse escluse sia più piccolo e in grigio nelle pagine di categoria per far risaltare maggiormente il prezzo primario (tasse incluse).
-   **Etichetta prezzo tasse incluse (BP\_TINL)**

    -   **Cosa fa questa impostazione:** Definisce l'etichetta di testo visualizzata accanto al prezzo con tasse incluse nelle pagine di elenco prodotti.
    -   **Effetto della modifica di questa impostazione:** Modifica il testo dell'etichetta.
    -   **Valore consigliato:** "Tasse incl." o "IVA incl."
    -   **Scenario / esempio del commerciante:** Potresti usare un'etichetta più breve come "incl." nelle pagine di elenco a causa dello spazio limitato.
-   **Etichetta prezzo tasse escluse (BP\_TEXL)**

    -   **Cosa fa questa impostazione:** Definisce l'etichetta di testo visualizzata accanto al prezzo con tasse escluse nelle pagine di elenco prodotti.
    -   **Effetto della modifica di questa impostazione:** Modifica il testo dell'etichetta.
    -   **Valore consigliato:** "Tasse escl." o "IVA escl."
    -   **Scenario / esempio del commerciante:** Potresti usare un'etichetta più breve come "escl." nelle pagine di elenco.

#### Regole di visibilità

-   **Regola di visibilità (bp\_visibility\_rule)**

    -   **Cosa fa questa impostazione:** Determina come si comporta la visualizzazione a doppio prezzo in base a gruppi di clienti, prodotti specifici o categorie.
    -   **Effetto della modifica di questa impostazione:**
        -   *Mostra sempre:* I prezzi doppi vengono sempre mostrati per tutti i clienti, prodotti e categorie.
        -   *Nascondi per gruppi/prodotti/categorie selezionati:* I prezzi doppi vengono nascosti per selezioni specifiche.
        -   *Mostra solo per gruppi/prodotti/categorie selezionati:* I prezzi doppi vengono mostrati solo per selezioni specifiche.
    -   **Valore consigliato:** Mostra sempre (per la massima trasparenza), o "Mostra solo per gruppi selezionati" se ti rivolgi specificamente a clienti B2B.
    -   **Scenario / esempio del commerciante:** Potresti scegliere "Mostra solo per gruppi selezionati" e quindi selezionare il tuo gruppo "Clienti all'ingrosso" per visualizzare i prezzi doppi solo per i tuoi clienti B2B.
-   **Visibilità per gruppi di clienti (actionAdminGroupsControllerSaveAfter)**

    -   **Cosa fa questa impostazione:** Ti consente di selezionare quali gruppi di clienti vedranno la visualizzazione a doppio prezzo, in base alla "Regola di visibilità" sopra.
    -   **Effetto della modifica di questa impostazione:** Solo i clienti appartenenti ai gruppi selezionati vedranno i prezzi doppi (se la regola è "Mostra solo per gruppi selezionati") o *non* li vedranno (se la regola è "Nascondi per gruppi selezionati").
    -   **Valore consigliato:** Seleziona "Tutti i gruppi di clienti" se la tua regola è "Mostra sempre". Altrimenti, seleziona i gruppi pertinenti.
    -   **Scenario / esempio del commerciante:** Se desideri che solo i tuoi gruppi "Ospite" e "Cliente" vedano principalmente i prezzi con tasse incluse, ma "All'ingrosso" veda entrambi, imposteresti la regola su "Mostra solo per gruppi selezionati" e selezioneresti "All'ingrosso".
-   **Visibilità per prodotti (bp\_visibility\_products)**

    -   **Cosa fa questa impostazione:** Ti consente di specificare singoli prodotti per i quali la visualizzazione a doppio prezzo dovrebbe applicarsi (o non applicarsi), in base alla "Regola di visibilità". Questo utilizza un campo di ricerca con completamento automatico.
    -   **Effetto della modifica di questa impostazione:** La visualizzazione a doppio prezzo sarà abilitata o disabilitata per i prodotti selezionati in base alla regola di visibilità scelta.
    -   **Valore consigliato:** Lasciare vuoto se si desidera che si applichi a tutti i prodotti.
    -   **Scenario / esempio del commerciante:** Potresti avere alcuni prodotti specifici in cui mostrare entrambi i prezzi è confuso, quindi imposteresti la regola su "Nascondi per prodotti selezionati" e aggiungeresti quei prodotti qui.
-   **Visibilità per categorie (bp\_visibility\_cat)**

    -   **Cosa fa questa impostazione:** Ti consente di specificare le categorie per le quali la visualizzazione a doppio prezzo dovrebbe applicarsi (o non applicarsi), in base alla "Regola di visibilità".
    -   **Effetto della modifica di questa impostazione:** La visualizzazione a doppio prezzo sarà abilitata o disabilitata per tutti i prodotti all'interno delle categorie selezionate in base alla regola di visibilità scelta.
    -   **Valore consigliato:** Lasciare vuoto se si desidera che si applichi a tutte le categorie.
    -   **Scenario / esempio del commerciante:** Se vendi sia beni fisici (dove la tassa è rilevante) che prodotti digitali (dove la tassa potrebbe essere gestita in modo diverso), potresti nascondere i prezzi doppi per la tua categoria "Download digitali".

#### Opzioni di visualizzazione

-   **Mostra tipi di prezzo (BF\_SHOW\_TYPES)**

    -   **Cosa fa questa impostazione:** Determina quali tipi di prezzo vengono visualizzati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Tasse incluse e Tasse escluse:* Mostra entrambi i prezzi.
        -   *Solo tasse incluse:* Mostra solo il prezzo con tasse incluse (il modulo elabora comunque, ma visualizza solo uno).
        -   *Solo tasse escluse:* Mostra solo il prezzo con tasse escluse.
    -   **Valore consigliato:** Tasse incluse e Tasse escluse (per sfruttare la funzionalità principale del modulo).
    -   **Scenario / esempio del commerciante:** Se il tuo obiettivo principale è mostrare i prezzi con tasse escluse ai clienti B2B, potresti selezionare "Solo tasse escluse" in combinazione con una regola di visibilità per gruppo di clienti.
-   **Usa CSS tema Classic (BF\_CLASSICCSS)**

    -   **Cosa fa questa impostazione:** Se il tuo tema è basato sul tema PrestaShop Classic predefinito, l'abilitazione di questa opzione applicherà regole CSS specifiche progettate per integrarsi senza problemi con lo stile di quel tema.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo caricherà un foglio di stile dedicato (`classic.css`) per garantire una migliore integrazione visiva con i temi basati su Classic.
        -   *Quando disabilitato:* Il modulo utilizzerà il suo stile predefinito, che potrebbe richiedere CSS personalizzati per una perfetta integrazione con temi non Classic.
    -   **Valore consigliato:** Abilitare se il tuo tema è basato su Classic o un tema figlio di Classic. Disabilitare altrimenti.
    -   **Scenario / esempio del commerciante:** Se hai appena installato il modulo e i prezzi sembrano disallineati sul tuo tema Classic, l'abilitazione di questa opzione potrebbe risolvere il problema.
-   **CSS proprio (BF\_OWNCSS)**

    -   **Cosa fa questa impostazione:** Fornisce un'area di testo in cui puoi inserire il tuo codice CSS personalizzato per sovrascrivere o aggiungere stili all'output del modulo. Questo è per utenti avanzati o webmaster.
    -   **Effetto della modifica di questa impostazione:** Qualsiasi codice CSS inserito qui verrà applicato globalmente alle visualizzazioni dei prezzi del modulo, consentendo un controllo completo sullo stile.
    -   **Valore consigliato:** Lasciare vuoto a meno che tu non abbia esigenze di stile specifiche.
    -   **Scenario / esempio del commerciante:** Vuoi cambiare la dimensione del carattere dei prezzi visualizzati o aggiungere un bordo attorno ad essi per renderli più prominenti.

#### Impostazioni avanzate

-   **Percentuale tasse pagina prodotto (BP\_PP\_TPERCENT)**

    -   **Cosa fa questa impostazione:** Ti consente di visualizzare la percentuale di tasse nelle pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Attivo:* La percentuale di tasse (es. "20% IVA") verrà mostrata accanto ai prezzi.
        -   *Disattivo:* La percentuale di tasse non verrà visualizzata.
    -   **Valore consigliato:** Disattivo (a meno che tu non voglia mostrare esplicitamente l'aliquota fiscale).
    -   **Scenario / esempio del commerciante:** Nei paesi in cui i clienti sono molto attenti alle tasse, mostrare la percentuale può aggiungere un ulteriore livello di trasparenza.
-   **Percentuale tasse pagina prodotto (Tasse escluse) (BP\_PP\_TPERCENT\_TEXL)**

    -   **Cosa fa questa impostazione:** Simile a quanto sopra, ma specificamente per la visualizzazione del prezzo con tasse escluse nelle pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Attivo:* La percentuale di tasse verrà mostrata accanto al prezzo con tasse escluse.
        -   *Disattivo:* La percentuale di tasse non verrà visualizzata.
    -   **Valore consigliato:** Disattivo.
    -   **Scenario / esempio del commerciante:** Utile se si desidera evidenziare l'aliquota fiscale che viene esclusa.
-   **Percentuale tasse elenco prodotti (BP\_PL\_TPERCENT)**

    -   **Cosa fa questa impostazione:** Ti consente di visualizzare la percentuale di tasse nelle pagine di elenco prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Attivo:* La percentuale di tasse verrà mostrata accanto ai prezzi nelle pagine di elenco.
        -   *Disattivo:* La percentuale di tasse non verrà visualizzata.
    -   **Valore consigliato:** Disattivo (per mantenere le pagine di elenco più pulite).
    -   **Scenario / esempio del commerciante:** Se i tuoi elenchi di prodotti non sono troppo affollati, mostrare la percentuale di tasse può essere informativo.
-   **Percentuale tasse elenco prodotti (Tasse escluse) (BP\_PL\_TPERCENT\_TEXL)**

    -   **Cosa fa questa impostazione:** Simile a quanto sopra, ma specificamente per la visualizzazione del prezzo con tasse escluse nelle pagine di elenco prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Attivo:* La percentuale di tasse verrà mostrata accanto al prezzo con tasse escluse nelle pagine di elenco.
        -   *Disattivo:* La percentuale di tasse non verrà visualizzata.
    -   **Valore consigliato:** Disattivo.
    -   **Scenario / esempio del commerciante:** Meno comune, ma potrebbe essere utilizzato per enfatizzare la componente fiscale che viene rimossa.

#### Impostazioni lingua (Interne)

-   **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**
    -   **Cosa fa questa impostazione:** Queste sono impostazioni interne di PrestaShop relative alla lingua predefinita e alla lingua del modulo per i dipendenti. Sono visualizzate qui a scopo informativo e non sono direttamente configurabili dal modulo.
    -   **Effetto della modifica di questa impostazione:** Non applicabile, questi sono valori di sola lettura dalla tua configurazione PrestaShop.
    -   **Valore consigliato:** N/A
    -   **Scenario / esempio del commerciante:** Questi valori aiutano il modulo a determinare quale lingua utilizzare per le etichette se non le hai impostate esplicitamente per tutte le lingue.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminBothpricesSearchController (Back Office > Moduli > Mostra due prezzi - tasse incluse / escluse > Cerca prodotti)

Questa schermata di amministrazione dedicata viene utilizzata per gestire l'impostazione "Visibilità per prodotti". Fornisce un'interfaccia per cercare e selezionare prodotti specifici che dovrebbero essere influenzati dalle regole di visibilità del modulo.

-   **Nome schermata e posizione nel menu:** Puoi accedere a questa schermata cliccando sul link o pulsante "Cerca prodotti" all'interno della pagina di configurazione principale del modulo, solitamente accanto all'impostazione "Visibilità per prodotti".
-   **Azioni e impostazioni disponibili:**
    -   **Campo di ricerca prodotto:** Un campo di testo dove puoi digitare nomi o ID di prodotti per trovare prodotti specifici.
    -   **Griglia dei risultati di ricerca:** Visualizza un elenco di prodotti che corrispondono alla tua query di ricerca.
    -   **Pulsanti Aggiungi/Rimuovi:** Ti consente di aggiungere o rimuovere prodotti selezionati dall'elenco dei prodotti interessati dalla regola di visibilità.
    -   **Elenco prodotti selezionati:** Mostra tutti i prodotti attualmente configurati per la regola di visibilità.
-   **Effetto delle modifiche:**
    -   L'aggiunta di un prodotto all'elenco significa che la visualizzazione a doppio prezzo del modulo verrà mostrata *solo* per quel prodotto o *nascosta* per quel prodotto, a seconda dell'impostazione generale della "Regola di visibilità".
    -   La rimozione di un prodotto significa che non sarà più specificamente influenzato dalla regola di visibilità a livello di prodotto e tornerà alle impostazioni generali del modulo.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Vai alla pagina di configurazione principale del modulo.
    2.  Imposta la tua "Regola di visibilità" (es. "Nascondi per prodotti selezionati").
    3.  Clicca sul link/pulsante per aprire la schermata "AdminBothpricesSearchController".
    4.  Usa il campo di ricerca per trovare i prodotti che desideri includere nella regola.
    5.  Aggiungili all'"Elenco prodotti selezionati".
    6.  Salva le modifiche nella pagina di configurazione principale del modulo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Config. Modulo | Abilitato / Disabilitato | Abilitato | Interruttore principale per la funzionalità del modulo. |
| Config. Modulo | Mostra nella pagina prodotto (BF\_PP) | Attivo | Visualizza prezzi doppi nelle pagine di dettaglio prodotto. |
| Config. Modulo | Nascondi prezzo tasse incluse nella pagina prodotto (BOTH\_HIDE\_P) | Disattivo | Nasconde il prezzo tasse incl. nelle pagine prodotto. |
| Config. Modulo | CSS personalizzato per la pagina prodotto (BF\_PPC) | Vuoto | CSS personalizzato per la visualizzazione del prezzo nella pagina prodotto. |
| Config. Modulo | Forza nascondi pagina prodotto (BP\_FORCE\_HIDE) | Disattivo | Nasconde forzatamente l'output del modulo nella pagina prodotto. |
| Config. Modulo | Etichetta prezzo tasse incluse (BP\_TIN) | "Tasse incl." | Etichetta per il prezzo tasse incluse nella pagina prodotto. |
| Config. Modulo | Etichetta prezzo tasse escluse (BP\_TEX) | "Tasse escl." | Etichetta per il prezzo tasse escluse nella pagina prodotto. |
| Config. Modulo | Etichetta prezzo originale tasse incluse (BP\_O\_TIN) | "Tasse incl. originali" | Etichetta per il prezzo originale tasse incluse nella pagina prodotto. |
| Config. Modulo | Mostra nell'elenco prodotti (BF\_PL) | Attivo | Visualizza prezzi doppi nelle pagine di categoria/elenco. |
| Config. Modulo | Nascondi prezzo tasse incluse nell'elenco prodotti (BOTH\_HIDE\_PL) | Disattivo | Nasconde il prezzo tasse incl. nelle pagine di elenco. |
| Config. Modulo | CSS personalizzato per l'elenco prodotti (BF\_PLC) | Vuoto | CSS personalizzato per la visualizzazione del prezzo nella pagina di elenco. |
| Config. Modulo | Etichetta prezzo tasse incluse (BP\_TINL) | "Tasse incl." | Etichetta per il prezzo tasse incluse nelle pagine di elenco. |
| Config. Modulo | Etichetta prezzo tasse escluse (BP\_TEXL) | "Tasse escl." | Etichetta per il prezzo tasse escluse nelle pagine di elenco. |
| Config. Modulo | Regola di visibilità (bp\_visibility\_rule) | Mostra sempre | Definisce come vengono applicate le regole di visibilità (mostra/nascondi per selezionati). |
| Config. Modulo | Visibilità per gruppi di clienti | Tutti i gruppi di clienti | Seleziona i gruppi di clienti interessati dalla regola di visibilità. |
| Config. Modulo | Visibilità per prodotti (bp\_visibility\_products) | Vuoto | Seleziona prodotti specifici interessati dalla regola di visibilità. |
| Config. Modulo | Visibilità per categorie (bp\_visibility\_cat) | Vuoto | Seleziona categorie specifiche interessate dalla regola di visibilità. |
| Config. Modulo | Mostra tipi di prezzo (BF\_SHOW\_TYPES) | Tasse incluse e Tasse escluse | Determina quali tipi di prezzo vengono visualizzati (entrambi, solo incl, solo escl). |
| Config. Modulo | Usa CSS tema Classic (BF\_CLASSICCSS) | Disattivo (Abilita per temi Classic) | Applica lo stile specifico del tema Classic. |
| Config. Modulo | CSS proprio (BF\_OWNCSS) | Vuoto | CSS personalizzato globale per l'output del modulo. |
| Config. Modulo | Percentuale tasse pagina prodotto (BP\_PP\_TPERCENT) | Disattivo | Visualizza la percentuale di tasse nelle pagine prodotto. |
| Config. Modulo | Percentuale tasse pagina prodotto (Tasse escluse) (BP\_PP\_TPERCENT\_TEXL) | Disattivo | Visualizza la percentuale di tasse per il prezzo tasse escluse nelle pagine prodotto. |
| Config. Modulo | Percentuale tasse elenco prodotti (BP\_PL\_TPERCENT) | Disattivo | Visualizza la percentuale di tasse nelle pagine di elenco. |
| Config. Modulo | Percentuale tasse elenco prodotti (Tasse escluse) (BP\_PL\_TPERCENT\_TEXL) | Disattivo | Visualizza la percentuale di tasse per il prezzo tasse escluse nelle pagine di elenco. |
| AdminBothpricesSearchController | Ricerca prodotto / Aggiungi/Rimuovi | N/A | Gestisce l'elenco dei prodotti per le regole di visibilità. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il modulo è abilitato, ma non vedo due prezzi nel mio negozio.**
R:

-   **Verifica abilitazione globale:** Assicurati che l'interruttore principale "Abilitato / Disabilitato" nella parte superiore della configurazione del modulo sia impostato su "Abilitato".
-   **Verifica impostazioni specifiche della pagina:** Verifica che "Mostra nella pagina prodotto" (BF\_PP) e/o "Mostra nell'elenco prodotti" (BF\_PL) siano abilitati, a seconda di dove ti aspetti di vedere i prezzi.
-   **Verifica regole di visibilità:** Se hai impostato una "Regola di visibilità", assicurati che il tuo gruppo di clienti, prodotto o categoria attuale sia incluso nella regola "mostra" o non sia escluso da una regola "nascondi".
-   **Svuota cache:** Svuota sempre la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) dopo aver apportato modifiche alla configurazione del modulo. Svuota anche la cache del tuo browser.
-   **Conflitti con il tema:** Alcuni temi altamente personalizzati potrebbero essere in conflitto. Prova a passare temporaneamente al tema PrestaShop Classic predefinito per vedere se i prezzi appaiono. Se lo fanno, si tratta di un conflitto CSS o JS relativo al tema.

**D2: I prezzi vengono visualizzati, ma sembrano disallineati o hanno uno stile errato.**
R:

-   **Usa CSS tema Classic:** Se il tuo tema è basato sul tema PrestaShop Classic predefinito, prova ad abilitare l'opzione "Usa CSS tema Classic (BF\_CLASSICCSS)" nella configurazione del modulo.
-   **CSS personalizzato:** Se hai un tema personalizzato, potresti dover aggiungere CSS personalizzati. Usa gli strumenti per sviluppatori del tuo browser (F12) per identificare le classi CSS degli elementi di prezzo del modulo. Quindi, usa il campo "CSS proprio (BF\_OWNCSS)" nella configurazione del modulo per aggiungere le tue regole di stile.
-   **Posizione del modulo:** Assicurati che il modulo sia agganciato correttamente. Sebbene il modulo gestisca la maggior parte degli hook automaticamente, a volte potrebbero essere necessari hook specifici del tema.

**D3: I prezzi non si aggiornano quando cambio gli attributi del prodotto (es. taglia, colore) nella pagina del prodotto.**
R:

-   **Compatibilità del modulo:** Assicurati che la tua versione di PrestaShop rientri nell'intervallo supportato.
-   **Conflitti JavaScript:** Questo è spesso causato da conflitti JavaScript con il tuo tema o un altro modulo. Controlla la console del tuo browser (F12 > scheda Console) per eventuali errori JavaScript quando cambi gli attributi.
-   **Sovrascritture del tema:** Se il tuo tema sovrascrive pesantemente il JavaScript predefinito della pagina prodotto di PrestaShop, potrebbe impedire al modulo di rilevare le modifiche di prezzo. Contatta lo sviluppatore del tuo tema o un webmaster per assistenza.
-   **Svuota cache:** Svuota la cache di PrestaShop e del browser.

**D4: Come traduco le etichette dei prezzi (es. "Tasse incl.", "Tasse escl.") in altre lingue?**
R:

-   Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
-   Seleziona "Traduzioni dei moduli installati".
-   Scegli il tuo tema.
-   Seleziona la tua lingua.
-   Trova il modulo "Mostra due prezzi - tasse incluse / escluse" nell'elenco.
-   Troverai i campi per "Etichetta prezzo tasse incluse", "Etichetta prezzo tasse escluse", ecc., sia per le pagine prodotto che per le pagine di elenco. Inserisci le tue traduzioni lì e salva.

**D5: Voglio mostrare i prezzi tasse escluse solo a gruppi di clienti specifici (es. B2B). Come faccio?**
R:

-   Nella configurazione del modulo, imposta **"Regola di visibilità"** su "Mostra solo per gruppi selezionati".
-   Quindi, seleziona il/i gruppo/i di clienti specifico/i (es. "All'ingrosso", "B2B") che dovrebbero vedere i prezzi doppi.
-   Facoltativamente, imposta **"Mostra tipi di prezzo"** su "Solo tasse escluse" se desideri nascondere completamente il prezzo tasse incluse per questi gruppi.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Mostra due prezzi - tasse incluse / escluse" (`bothprices`) è un modulo PrestaShop standard che segue il modello MVC. Estende principalmente la classe `Module`, sfruttando il sistema di hook di PrestaShop per iniettare informazioni sui prezzi e modificare la visualizzazione. Utilizza un Controller Admin dedicato per la funzionalità di ricerca prodotti e controller frontali per le interazioni AJAX. Il modulo si basa sui template Smarty per il rendering e su JavaScript/CSS personalizzati per aggiornamenti dinamici e stile. La configurazione è memorizzata in `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nome classe e classe padre**: `BothpricesAjaxModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Gestisce le richieste AJAX dal front-office, principalmente per aggiornare dinamicamente i prezzi quando gli attributi del prodotto vengono modificati. Probabilmente recupera le informazioni sul prodotto e calcola i prezzi in base agli attributi selezionati e al contesto del cliente, restituendo dati JSON.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre**: `BothpricesIndexModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo è un controller segnaposto o di fallback. In molti moduli, i controller `index.php` vengono utilizzati per il routing di base o per prevenire l'elenco delle directory. Potrebbe non avere una logica personalizzata significativa oltre alla spedizione di base.
-   **Controller Admin Back-Office**:

    -   `controllers/admin/AdminBothpricesSearchController.php`
        -   **Nome classe e classe padre**: `AdminBothpricesSearchController` estende `ModuleAdminController`.
        -   **Nome tab ed entità gestita**: Questo controller gestisce la ricerca e la selezione dei prodotti per le regole di visibilità del modulo. Non gestisce direttamente una specifica `ObjectModel` ma interagisce con i dati `Product` per la selezione. Fornisce un'interfaccia a griglia per la ricerca e l'aggiunta/rimozione di prodotti dalla configurazione `bp_visibility_products`.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non sembra definire alcuna classe `ObjectModel` personalizzata nella directory `classes/`. Probabilmente si basa sulle classi `Product` e `Configuration` esistenti di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   `bothprices/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Fornisce la funzionalità di completamento automatico per il campo di ricerca prodotti all'interno di `AdminBothpricesSearchController`, consentendo agli amministratori di trovare e selezionare rapidamente i prodotti per le regole di visibilità.
-   `bothprices/views/js/both-hide-p.js`
    -   **Ambito**: Front-office (Pagina prodotto).
    -   **Descrizione**: Contiene la logica JavaScript per nascondere il prezzo con tasse incluse specificamente nella pagina prodotto, in base all'impostazione di configurazione `BOTH_HIDE_P`. Probabilmente si rivolge a specifici elementi DOM per applicare `display: none` o uno stile simile.
-   `bothprices/views/js/both-hide-pl.js`
    -   **Ambito**: Front-office (Pagine di elenco prodotti).
    -   **Descrizione**: Simile a `both-hide-p.js`, ma per le pagine di elenco prodotti, nascondendo il prezzo con tasse incluse in base alla configurazione `BOTH_HIDE_PL`.
-   `bothprices/views/js/bothprices-admin.js`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Contiene JavaScript generale per la pagina di configurazione back-office del modulo. Questo potrebbe includere la logica per mostrare/nascondere i campi di configurazione in base ad altre selezioni (es. modifiche alla regola di visibilità), la validazione del modulo o le chiamate AJAX per il salvataggio delle impostazioni.
-   `bothprices/views/js/bothprices.js`
    -   **Ambito**: Front-office (Globale).
    -   **Descrizione**: Questo è il file JavaScript principale del front-office. È responsabile di:
        -   Ascoltare `prestashop.on('updateProduct', ...)` o eventi simili per rilevare le modifiche agli attributi del prodotto.
        -   Effettuare chiamate AJAX a `controllers/front/ajax.php` per recuperare i prezzi doppi aggiornati.
        -   Aggiornare dinamicamente i prezzi con tasse incluse ed escluse visualizzati nella pagina prodotto e potenzialmente nelle pagine di elenco.
        -   Applicare CSS o classi personalizzate in base alle impostazioni del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `bothprices/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Stili per il menu a discesa di completamento automatico e i risultati di ricerca all'interno dell'interfaccia `AdminBothpricesSearchController`.
-   `bothprices/views/css/admin.css`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Stile generale per la pagina di configurazione del modulo nel Back Office di PrestaShop, garantendo un aspetto coerente con il pannello di amministrazione.
-   `bothprices/views/css/bothprices.css`
    -   **Ambito**: Front-office (Globale).
    -   **Descrizione**: Contiene le regole CSS predefinite per la visualizzazione dei prezzi doppi sia nelle pagine prodotto che nelle pagine di elenco. Questo include la formattazione di base, il posizionamento e la differenziazione dei due elementi di prezzo.
    -   **Selettori di classe CSS chiave**: Gli sviluppatori possono cercare classi come `.bothprices_price_tax_incl`, `.bothprices_price_tax_excl`, `.bothprices_wrapper` da sovrascrivere.
-   `bothprices/views/css/classic.css`
    -   **Ambito**: Front-office (Specifico per il tema Classic).
    -   **Descrizione**: Contiene regole CSS aggiuntive o di override specificamente progettate per migliorare l'integrazione visiva con il tema PrestaShop Classic predefinito o temi basati su di esso. Questo file viene caricato condizionalmente in base all'impostazione `BF_CLASSICCSS`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `bothprices/views/templates/bothprices.tpl`
        -   **Hook**: Probabilmente renderizzato in hook come `displayProductPriceBlock`, `displayProductListReviews`, `displayProductPriceBlock`, `displayProductPriceBlock`, `displayAfterProductThumbs` o simili, sia nelle pagine prodotto che nelle pagine di elenco.
        -   **Output**: Questo template è responsabile del rendering della struttura HTML effettiva della visualizzazione a doppio prezzo (prezzi con tasse incluse ed escluse) insieme alle loro etichette. Riceve variabili di prezzo dalla logica PHP del modulo.
-   **Template admin (`views/templates/admin/`)**:
    -   `bothprices/views/templates/admin/configure_shell.tpl`
        -   **Hook**: Renderizzato all'interno del metodo `getContent()` del modulo per la pagina di configurazione principale.
        -   **Output**: Questo funge da wrapper o shell per il modulo di configurazione del modulo, includendo potenzialmente schede, intestazioni e piè di pagina per l'interfaccia di amministrazione.
    -   `bothprices/views/templates/selectedProducts.tpl`
        -   **Hook**: Utilizzato da `AdminBothpricesSearchController`.
        -   **Output**: Renderizza l'elenco dei prodotti che sono stati selezionati per le regole di visibilità, tipicamente in formato tabella o elenco all'interno dell'interfaccia di ricerca admin.
-   **Template front-office (`views/templates/front/`)**:
    -   `bothprices/views/templates/bothprices-product-page.tpl`
        -   **Hook**: Probabilmente renderizzato nella pagina prodotto, possibilmente all'interno di `displayProductPriceBlock` o simili.
        -   **Output**: Un template specifico per la visualizzazione a doppio prezzo della pagina prodotto, potenzialmente con informazioni più dettagliate o un layout diverso rispetto alle pagine di elenco.
-   **Template libreria (`lib/searchTool/views/scripts.tpl`)**:
    -   `bothprices/lib/searchTool/views/scripts.tpl`
        -   **Hook**: Probabilmente incluso nella vista `AdminBothpricesSearchController`.
        -   **Output**: Contiene script di inizializzazione JavaScript o variabili di configurazione per lo strumento di ricerca con completamento automatico.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo utilizza principalmente la tabella `ps_configuration` di PrestaShop per memorizzare le sue impostazioni. Le chiavi di configurazione includono: `mypresta_updates`, `update_`, `updatev_`, `BOTH_HIDE_PL_CSS`, `BOTH_HIDE_P_CSS`, `BF_PP`, `BF_PL`, `bp_visibility_rule`, `bp_visibility_products`, `bp_visibility_cat`, `BF_SHOW_TYPES`, `BF_PLC`, `BF_PPC`, `BP_FORCE_HIDE`, `BP_PP_TPERCENT_TEXL`, `BP_PP_TPERCENT`, `BP_PL_TPERCENT_TEXL`, `BP_PL_TPERCENT`, `BOTH_HIDE_PL`, `BOTH_HIDE_P`, `BF_OWNCSS`, `BF_CLASSICCSS`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `BP_TIN`, `BP_TIN_L`, `BP_TEX`, `BP_TEX_L`, `BP_TINL`, `BP_TINL_L`, `BP_TEXL`, `BP_TEXL_L`, `BP_O_TIN`, `BP_O_TIN_L`, `BP_O_TEX`.
    -   Non sembra creare tabelle SQL personalizzate.
-   **Tabella degli hook registrati**:

| Nome Hook | Ambito | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- | --- |
| `ActionFrontControllerSetMedia` | Front-Office | Prima dell'output del controller, dopo l'inizializzazione dei media. | Inietta le risorse CSS e JS del modulo nel front-office. |
| `ActionAdminGroupsControllerSaveAfter` | Back-Office | Dopo che un amministratore salva un gruppo di clienti. | Potenzialmente utilizzato per svuotare la cache o rivalutare le regole di visibilità relative ai gruppi di clienti. |
| `ActionAdminControllerSetMedia` | Back-Office | Prima dell'output del controller admin, dopo l'inizializzazione dei media. | Inietta le risorse CSS e JS del modulo nel back-office (es. per la pagina di configurazione, controller di ricerca). |
| `updateproduct` | Back-Office | Dopo l'aggiornamento di un prodotto. | Svuota le cache pertinenti, rivaluta i dati di prezzo specifici del prodotto. |
| `ActionProductDelete` | Back-Office | Dopo l'eliminazione di un prodotto. | Pulisce eventuali dati specifici del modulo relativi al prodotto eliminato (es. da `bp_visibility_products`). |
| `displayUpdateProduct` | Back-Office | Nella pagina di modifica del prodotto. | Potenzialmente inietta campi o informazioni personalizzate nel modulo di modifica del prodotto. |
| `actionProductUpdate` | Back-Office | Dopo l'aggiornamento di un prodotto. | Simile a `updateproduct`, assicura che i dati interni del modulo riflettano le modifiche del prodotto. |
| `displayHeader` | Front-Office | Nella sezione `<head>` di ogni pagina del front-office. | Inietta CSS e JS del modulo per la disponibilità globale, o renderizza un piccolo snippet. |
| `displayCategoryUpdate` | Back-Office | Nella pagina di modifica della categoria. | Potenzialmente inietta campi o informazioni personalizzate nel modulo di modifica della categoria. |
| `ActionCategoryUpdate` | Back-Office | Dopo l'aggiornamento di una categoria. | Svuota le cache pertinenti, rivaluta i dati di prezzo specifici della categoria. |
| `actionProductAdd` | Back-Office | Dopo l'aggiunta di un nuovo prodotto. | Inizializza i dati specifici del modulo per il nuovo prodotto. |
| `actionObjectSpecificPriceUpdateAfter` | Back-Office | Dopo l'aggiornamento di un prezzo specifico (sconto). | Assicura che i calcoli dinamici dei prezzi riflettano i nuovi prezzi specifici. |
| `categoryUpdate` | Back-Office | Dopo l'aggiornamento di una categoria. | Alias o duplicato di `ActionCategoryUpdate`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Mostra due prezzi - tasse incluse / escluse", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere riguardo alla funzionalità del modulo.
