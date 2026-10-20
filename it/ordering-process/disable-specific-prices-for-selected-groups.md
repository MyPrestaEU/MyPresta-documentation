---
title: "Disabilita prezzi specifici per gruppi selezionati - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Disabilita prezzi specifici per gruppi selezionati' di MyPresta.eu."
sidebar:
  label: "Disabilita prezzi specifici per gruppi selezionati - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Disable specific prices for selected groups su MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-groups.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/disable-specific-prices-for-selected-groups/)
>
> ---


# Disabilita prezzi specifici per gruppi selezionati

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Disabilita prezzi specifici per gruppi selezionati". La troverai navigando su **Moduli > Gestione moduli**, cercando "Disabilita prezzi specifici per gruppi selezionati" e cliccando su "Configura".

#### **1. Disabilita sconti prezzi specifici per gruppi selezionati**

Questa è l'impostazione principale del modulo. Determina quali gruppi di clienti *non* riceveranno sconti di prezzo specifici.

-   **Cosa fa questa impostazione:** Questa sezione presenta un elenco di tutti i gruppi di clienti definiti nel tuo negozio PrestaShop. Puoi selezionare uno o più gruppi da questo elenco.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando uno o più gruppi sono selezionati:* I clienti appartenenti a uno qualsiasi dei gruppi selezionati *non* vedranno o beneficeranno di sconti di prezzo specifici configurati per i prodotti. Vedranno e pagheranno sempre il prezzo standard del prodotto.
    -   *Quando nessun gruppo è selezionato:* Il modulo non disabiliterà i prezzi specifici per nessun gruppo. Tutti i clienti riceveranno sconti di prezzo specifici come configurato nelle impostazioni del prodotto.
-   **Valore consigliato:** Seleziona i gruppi di clienti specifici per i quali desideri disabilitare gli sconti di prezzo specifici. Ad esempio, se hai un gruppo "Grossisti" che vuoi che paghi sempre il prezzo standard, seleziona quel gruppo.
-   **Scenario / esempio per il commerciante:** Hai un gruppo di clienti "Ospite" e un gruppo "Nuovi Clienti". Vuoi riservare sconti di prezzo specifici (come prezzi all'ingrosso o promozioni temporanee) solo al tuo gruppo "Clienti Fedeli". Selezionando "Ospite" e "Nuovi Clienti" qui, questi due gruppi vedranno sempre il prezzo normale, mentre i "Clienti Fedeli" beneficeranno comunque di eventuali prezzi specifici che hai impostato.

#### **2. Abilitato**

Questo è l'interruttore globale di accensione/spegnimento per la funzionalità del modulo.

-   **Cosa fa questa impostazione:** Questo è un semplice interruttore per attivare o disattivare la logica principale del modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo disabiliterà attivamente i prezzi specifici per i gruppi che hai selezionato nella sezione "Disabilita sconti prezzi specifici per gruppi selezionati".
    -   *Quando disabilitato (NO):* Il modulo sarà inattivo. Tutti i prezzi specifici funzioneranno come comportamento standard di PrestaShop, indipendentemente dai gruppi selezionati nella sezione precedente. Questo disattiva efficacemente l'impatto del modulo senza disinstallarlo.
-   **Valore consigliato:** **SÌ** se intendi utilizzare la funzionalità del modulo. **NO** se vuoi disabilitarlo temporaneamente senza perdere le tue selezioni di gruppo.
-   **Scenario / esempio per il commerciante:** Hai configurato il modulo per disabilitare i prezzi specifici per il tuo gruppo di clienti "Vendita al dettaglio". Se vuoi eseguire una promozione temporanea in cui *tutti* i gruppi, incluso "Vendita al dettaglio", dovrebbero ricevere sconti di prezzo specifici, puoi semplicemente impostare "Abilitato" su **NO**. Una volta terminata la promozione, riportalo su **SÌ** per riabilitare la disabilitazione dei prezzi specifici per i clienti "Vendita al dettaglio".

#### **3. Restituisci sempre il prezzo più basso**

Questa impostazione offre un ulteriore livello di controllo, specialmente quando i prezzi specifici potrebbero interagire con altre regole di prezzo.

-   **Cosa fa questa impostazione:** Questo interruttore determina se il modulo deve applicare rigorosamente il prezzo standard per i gruppi selezionati, o se deve comunque considerare il *prezzo più basso possibile* (che potrebbe includere altri tipi di sconti non gestiti dai prezzi specifici) se risulta essere inferiore al prezzo standard.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Per i gruppi selezionati, i prezzi specifici verranno ignorati. Tuttavia, se esiste *un altro* meccanismo (ad esempio, una regola del carrello, uno sconto globale o un diverso tipo di riduzione di prezzo) che si traduce in un prezzo inferiore al prezzo standard, il modulo consentirà l'applicazione di quel prezzo più basso. Ciò garantisce che i clienti ottengano sempre il prezzo più basso assoluto disponibile *al di fuori* dei prezzi specifici.
    -   *Quando disabilitato (NO):* Per i gruppi selezionati, i prezzi specifici verranno ignorati e il modulo applicherà rigorosamente il *prezzo standard del prodotto*. Nessun altro potenziale prezzo inferiore (a meno che non faccia parte del prezzo base stesso) verrà considerato. Ciò fornisce il controllo più rigido sui prezzi per i gruppi selezionati.
-   **Valore consigliato:** **NO** per un controllo rigoroso, garantendo che i gruppi selezionati paghino sempre il prezzo standard. **SÌ** se si desidera disabilitare i prezzi specifici ma consentire comunque l'applicazione di altri sconti non correlati ai prezzi specifici se si traducono in un prezzo inferiore.
-   **Scenario / esempio per il commerciante:**
    -   *Scenario 1 (Consigliato: NO):* Vuoi che il tuo gruppo "Grossisti" paghi *sempre* il prezzo pieno, standard, e non benefici mai di sconti di prezzo specifici o di altre potenziali riduzioni di prezzo. Imposteresti questo su **NO**.
    -   *Scenario 2 (Consigliato: SÌ):* Vuoi disabilitare i prezzi specifici per il tuo gruppo "Ospite", ma hai anche una regola generale del carrello "5% di sconto su tutti i prodotti" che si applica a tutti. Se imposti "Restituisci sempre il prezzo più basso" su **SÌ**, gli ospiti non riceveranno sconti di prezzo specifici, ma *otterranno* comunque lo sconto del 5% della regola del carrello se rende il prezzo inferiore al prezzo standard. Se impostato su **NO**, pagherebbero il prezzo standard completo, ignorando anche lo sconto del 5% della regola del carrello.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Disabilita sconti prezzi specifici per gruppi selezionati | Seleziona i gruppi secondo necessità | Seleziona i gruppi di clienti per i quali gli sconti di prezzo specifici verranno ignorati. |
| Configurazione modulo | Abilitato | SÌ | Interruttore globale ON/OFF per la funzionalità del modulo. |
| Configurazione modulo | Restituisci sempre il prezzo più basso | NO (per controllo rigoroso) / SÌ (per flessibilità) | Determina se altri sconti non specifici per prezzo possono comunque essere applicati se si traducono in un prezzo inferiore per i gruppi interessati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma i clienti nel gruppo selezionato continuano a vedere i prezzi specifici. Cosa c'è che non va?**
R:

1.  **Controlla l'impostazione "Abilitato":** Assicurati che l'interruttore "Abilitato" nella configurazione del modulo sia impostato su **SÌ**.
2.  **Verifica la selezione del gruppo:** Ricontrolla che il/i gruppo/i di clienti corretto/i sia/siano selezionato/i sotto "Disabilita sconti prezzi specifici per gruppi selezionati".
3.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota la cache". PrestaShop spesso memorizza nella cache le informazioni sui prezzi.
4.  **Controlla il gruppo del cliente:** Assicurati che il cliente con cui stai testando sia effettivamente assegnato al gruppo che hai selezionato nel modulo. Puoi verificarlo in **Clienti > Clienti** nel Back Office.
5.  **Compatibilità del tema:** Sebbene raro, alcuni temi fortemente personalizzati potrebbero interferire. Se il problema persiste, prova a passare temporaneamente al tema predefinito di PrestaShop per escludere conflitti con il tema.

**D: Cosa succede se un cliente appartiene a più gruppi, e un gruppo è selezionato per la disabilitazione dei prezzi specifici mentre un altro no?**
R: La logica principale di PrestaShop di solito dà la priorità al prezzo più basso. L'override di questo modulo tenterà di rimuovere i prezzi specifici per *qualsiasi* gruppo selezionato. Se un cliente appartiene a un gruppo che *dovrebbe* avere i prezzi specifici disabilitati, il modulo tenterà di applicare il prezzo standard. L'impostazione "Restituisci sempre il prezzo più basso" determinerà quindi se altri sconti non specifici per prezzo vengono comunque considerati.

**D: Questo modulo influisce su altri tipi di sconti, come le regole del carrello o le regole di prezzo del catalogo?**
R: Questo modulo si rivolge specificamente ai "prezzi specifici" come definiti in PrestaShop (gli sconti impostati direttamente sulle pagine dei prodotti o tramite importazione CSV).

-   Se "Restituisci sempre il prezzo più basso" è **NO**, il modulo applicherà rigorosamente il prezzo standard per i gruppi selezionati, potenzialmente sovrascrivendo altri sconti se si traducono in un prezzo inferiore al prezzo standard.
-   Se "Restituisci sempre il prezzo più basso" è **SÌ**, il modulo disabiliterà i prezzi specifici ma consentirà comunque l'applicazione di altri tipi di sconti (come le regole del carrello o le regole di prezzo del catalogo) se si traducono in un prezzo inferiore al prezzo standard.

**D: Voglio disabilitare temporaneamente il modulo senza perdere le mie impostazioni. Come faccio?**
R: Vai semplicemente alla pagina di configurazione del modulo e imposta l'interruttore "Abilitato" su **NO**. Tutti i tuoi gruppi selezionati e le altre impostazioni verranno conservati e potrai riabilitarlo in qualsiasi momento riportandolo su **SÌ**.

**D: Come traduco il testo del modulo in altre lingue?**
R: Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi seleziona "Disabilita prezzi specifici per gruppi selezionati". Potrai quindi tradurre qualsiasi stringa di testo visibile.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Disabilita prezzi specifici per gruppi selezionati" funziona principalmente sovrascrivendo le classi principali di PrestaShop relative ai prezzi dei prodotti, in particolare `Product.php` e `SpecificPrice.php`. Ciò gli consente di intercettare e modificare la logica che determina se i prezzi specifici vengono applicati a un prodotto, in base al gruppo del cliente corrente e alla configurazione del modulo. Segue una struttura di modulo PrestaShop standard con un file di modulo principale e override di classe.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la configurazione è gestita tramite il metodo `getContent()` della classe del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

La funzionalità principale del modulo è implementata tramite override di classe.

-   **`exsdis/override/classes/index.php`**:

    -   Questo è un file `index.php` vuoto standard, tipicamente posizionato nelle directory per impedire l'elenco delle directory. Non ha alcun impatto funzionale sulla logica del modulo.
-   **`exsdis/override/classes/Product.php`**:

    -   **Classe originale**: `classes/Product.php`
    -   **Scopo**: Questo override modifica la classe `Product`, che è centrale per il modo in cui le informazioni sui prodotti, inclusi i prezzi, vengono recuperate e calcolate in PrestaShop. La logica del modulo all'interno di questo override intercetta le chiamate per recuperare i prezzi specifici per un prodotto.
    -   **Logica chiave**: Controlla se il modulo è abilitato e se il gruppo del cliente corrente è tra quelli selezionati per avere i prezzi specifici disabilitati. In tal caso, manipola il processo di recupero dei prezzi specifici per garantire che nessun prezzo specifico venga restituito per quel cliente. Considera anche la configurazione `exsdis_lowest` per determinare se il prezzo più basso assoluto (esclusi i prezzi specifici) debba comunque essere restituito.
-   **`exsdis/override/classes/SpecificPrice.php`**:

    -   **Classe originale**: `classes/SpecificPrice.php`
    -   **Scopo**: Questo override si rivolge alla classe `SpecificPrice`, che è responsabile della gestione e dell'applicazione delle regole di prezzo specifiche.
    -   **Logica chiave**: Probabilmente modifica i metodi all'interno di questa classe (ad esempio, `getSpecificPrice()`, `getSpecificPrices()`) per impedire che gli oggetti prezzo specifici vengano creati o restituiti per i clienti nei gruppi designati. Questo funziona in combinazione con l'override di `Product.php` per garantire che i prezzi specifici vengano effettivamente ignorati.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non include alcun file di template Smarty personalizzato. Il modulo di configurazione viene renderizzato dinamicamente dal metodo `getContent()` in `exsdis.php`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle di database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration`.

    -   Voci `ps_configuration`:
        -   `exsdis_`: (Prefisso per le impostazioni generali del modulo)
        -   `exsdis_groups`: Memorizza un array serializzato o una stringa separata da virgole di ID di gruppi di clienti per i quali i prezzi specifici sono disabilitati.
        -   `exsdis_lowest`: Memorizza il valore (0 o 1) per l'impostazione "Restituisci sempre il prezzo più basso".
        -   `mypresta_updates`, `update_`, `updatev_`: Relativi ai controlli di aggiornamento di MyPresta.eu.
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente alcun hook standard di PrestaShop nel suo metodo `install()`. La sua funzionalità è principalmente ottenuta tramite override di classe, che modificano direttamente il comportamento principale di PrestaShop piuttosto che reagire agli eventi degli hook.
    La descrizione del modulo menziona "Front-Office Hooks: Header, Columns, Product, or Footer", ma questa è probabilmente un'affermazione generica su dove i *prezzi* potrebbero essere visualizzati, non dove il modulo stesso inietta contenuto tramite hook. Gli override gestiscono la logica dei prezzi a un livello inferiore.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Disabilita prezzi specifici per gruppi selezionati", fai riferimento al tuo account cliente MyPresta.eu. Puoi scaricare le versioni più recenti dalla cronologia degli ordini e accedere ai canali di supporto dedicati forniti da MyPresta.eu.
"""
