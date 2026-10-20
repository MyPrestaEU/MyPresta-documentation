---
title: "Link per assegnare il cliente a un gruppo - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Link per assegnare il cliente a un gruppo' di MyPresta.eu."
sidebar:
  label: "Link per assegnare il cliente a un gruppo"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Link to assign customer to group su MyPresta.eu](https://mypresta.eu/modules/administration-tools/link-to-assign-customer-to-group.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/link-to-assign-customer-to-group/)
>
> ---


# Link per assegnare il cliente a un gruppo

## 1. Requisiti e Compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Gestione moduli > Configura Link per assegnare il cliente a un gruppo)

Questa è la schermata di configurazione principale e unica per il modulo. Qui puoi definire come il modulo si comporta quando assegna i clienti ai gruppi.

#### **Cambia gruppo in predefinito**
-   **Cosa fa questa impostazione:** Questa impostazione determina se il modulo deve assegnare il cliente anche al gruppo clienti "Predefinito" oltre al gruppo specificato nell'URL.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Se un cliente clicca su un link per essere assegnato al "Gruppo X", verrà assegnato anche al gruppo "Predefinito". Ciò significa che farà parte sia del "Gruppo X" che del "Predefinito". Questo può essere utile se il tuo gruppo "Predefinito" ha determinate autorizzazioni o sconti di base che vuoi che i clienti abbiano sempre, indipendentemente dagli altri gruppi a cui si uniscono.
    -   *Quando disabilitato (NO):* Il cliente verrà assegnato solo al gruppo specificato nell'URL (es. "Gruppo X"). Non verrà aggiunto automaticamente al gruppo "Predefinito" a meno che non ne faccia già parte o che un altro meccanismo lo aggiunga.
-   **Valore consigliato:** **NO**. Nella maggior parte dei casi, vuoi assegnare i clienti a un gruppo *specifico* senza necessariamente aggiungerli al gruppo "Predefinito", specialmente se il tuo gruppo "Predefinito" non ha un significato speciale o se vuoi gestire i gruppi in modo più preciso. Abilita questa opzione solo se hai un motivo specifico per includere sempre il gruppo "Predefinito".
-   **Scenario / esempio del commerciante:** Hai un gruppo "VIP" con sconti speciali. Se abiliti questa opzione, un cliente che clicca su un link VIP sarà sia in "VIP" che in "Predefinito". Se "Predefinito" ha uno sconto del 5% su tutto il negozio e "VIP" ha uno sconto del 15% su prodotti specifici, il cliente beneficerà di entrambi dove applicabile. Se disabilitato, otterrebbe solo i vantaggi "VIP".

#### **Disassegna il cliente da altri gruppi**
-   **Cosa fa questa impostazione:** Questa impostazione controlla se il modulo deve rimuovere il cliente da *tutti gli altri* gruppi di clienti quando viene assegnato a un nuovo gruppo tramite il link speciale.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Se un cliente è attualmente nel "Gruppo A" e nel "Gruppo B", e poi clicca su un link per essere assegnato al "Gruppo X", verrà rimosso dal "Gruppo A" e dal "Gruppo B", e rimarrà solo nel "Gruppo X" (e potenzialmente "Predefinito" se l'impostazione precedente è abilitata). Questo assicura che il cliente sia *solo* nel gruppo target.
    -   *Quando disabilitato (NO):* Il cliente verrà *aggiunto* al nuovo gruppo ("Gruppo X") ma *rimarrà* in tutti gli altri gruppi di cui faceva già parte (es. "Gruppo A", "Gruppo B"). Ciò consente ai clienti di essere membri di più gruppi contemporaneamente.
-   **Valore consigliato:** **NO**. Consentire ai clienti di essere in più gruppi offre maggiore flessibilità per una segmentazione complessa. Abilita questa opzione solo se hai bisogno di gruppi stretti e mutuamente esclusivi (es. un cliente può essere solo "Dettaglio" O "Ingrosso", mai entrambi).
-   **Scenario / esempio del commerciante:**
    -   *Abilitato (SÌ):* Hai i gruppi "Cliente Standard" e "Cliente Ingrosso". Un cliente clicca su un link per diventare "Ingrosso". Se abilitato, viene rimosso da "Cliente Standard" e rimane solo "Ingrosso". Questo è l'ideale per tipi di clienti chiari e distinti.
    -   *Disabilitato (NO):* Hai i gruppi "Iscritto alla Newsletter" e "Membro del Programma Fedeltà". Un cliente clicca su un link per unirsi al "Programma Fedeltà". Se disabilitato, rimane un "Iscritto alla Newsletter" *e* diventa un "Membro del Programma Fedeltà". Questo è l'ideale per benefici aggiuntivi.

#### **Come creare il link speciale**
Il modulo funziona aggiungendo un parametro speciale a qualsiasi URL del tuo negozio. Il formato del parametro è: `?asg={group_id}`

1.  **Trova l'ID del gruppo:**
    -   Vai su **Clienti > Gruppi** nel tuo Back Office di PrestaShop.
    -   Annota il numero ID accanto al gruppo a cui vuoi assegnare i clienti. Ad esempio, se "Ingrosso" ha un ID di `3`, allora `3` è il tuo `group_id`.
2.  **Costruisci il link:**
    -   Prendi qualsiasi URL dal tuo negozio (es. `https://iltuonegozio.com/`)
    -   Aggiungi `?asg={group_id}` ad esso.
    -   **Esempio:** Per assegnare un cliente al gruppo ID `3` (es. "Ingrosso") e reindirizzarlo alla tua homepage: `https://iltuonegozio.com/?asg=3`
    -   **Esempio:** Per assegnare un cliente al gruppo ID `5` (es. "VIP") e reindirizzarlo a una pagina prodotto specifica: `https://iltuonegozio.com/it/prodotto/123-prodotto-fantastico?asg=5`

:::warning
Il parametro `asg` deve essere il *primo* parametro se non ci sono altri parametri nell'URL (cioè, usa `?`). Se l'URL ha già parametri (es. `https://iltuonegozio.com/categoria/1-abbigliamento?id_categoria=1`), devi usare `&` per aggiungere il parametro `asg`: `https://iltuonegozio.com/categoria/1-abbigliamento?id_categoria=1&asg=3`.
:::

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configurazione modulo | Cambia gruppo in predefinito | NO | Se SÌ, il cliente viene aggiunto anche al gruppo 'Predefinito'. Se NO, solo al gruppo specificato. |
| Configurazione modulo | Disassegna il cliente da altri gruppi | NO | Se SÌ, il cliente viene rimosso da tutti gli altri gruppi. Se NO, il cliente rimane nei gruppi esistenti e viene aggiunto a quello nuovo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il cliente ha cliccato sul link ma non è stato assegnato al gruppo. Cosa c'è che non va?**
R:
1.  **Cliente non loggato:** Il modulo funziona solo per i clienti *loggati*. Se non erano loggati, verranno semplicemente reindirizzati alla pagina senza assegnazione di gruppo.
2.  **ID gruppo errato:** Ricontrolla l'`group_id` nel tuo URL rispetto all'ID effettivo in **Clienti > Gruppi**.
3.  **Parametro URL errato:** Assicurati di usare `?asg=` per il primo parametro e `&asg=` per i parametri successivi.
4.  **Modulo non abilitato:** Verifica che il modulo sia installato e abilitato in **Moduli > Gestione moduli**.
5.  **Cache:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) e la cache del tuo browser.

**D: Posso assegnare un cliente a più gruppi con un solo link?**
R: No, il parametro `asg` supporta l'assegnazione a un solo gruppo alla volta. Tuttavia, se "Disassegna il cliente da altri gruppi" è impostato su NO, il cliente verrà *aggiunto* al nuovo gruppo mantenendo l'appartenenza ai suoi gruppi esistenti.

**D: Questo modulo influisce sulla SEO?**
R: No, questo modulo non ha un impatto diretto sulla SEO del tuo negozio. Il parametro `asg` è un parametro dinamico che i motori di ricerca tipicamente ignorano.

**D: Cosa succede se un cliente clicca sul link più volte?**
R: Se il cliente è già nel gruppo target, non cambia nulla. Se non lo è, verrà assegnato ad esso. Il modulo è progettato per gestire questo in modo elegante senza errori.

**D: Voglio rimuovere un cliente da un gruppo usando un link. È possibile?**
R: No, questo modulo è progettato solo per *assegnare* i clienti ai gruppi. Non fornisce funzionalità per rimuovere i clienti dai gruppi tramite un URL. Dovresti farlo manualmente nel Back Office o utilizzare un altro modulo/sviluppo personalizzato.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo "Link per assegnare il cliente a un gruppo" (`assigntogroup`) è un modulo PrestaShop leggero progettato principalmente per intercettare le richieste del front-office e modificare le assegnazioni dei gruppi di clienti in base a un parametro URL. Sfrutta il sistema di hook di PrestaShop (`displayHeader`) per eseguire la sua logica all'inizio del processo di caricamento della pagina, garantendo che le modifiche ai gruppi vengano applicate prima che il contenuto della pagina venga renderizzato. Non introduce controller, modelli personalizzati o JavaScript/CSS complessi. La sua funzionalità principale risiede all'interno della classe del modulo principale.

### 4.2 Controller (`controllers/`)
-   **Controller Front-Office**: Nessuno. La logica del modulo viene eseguita tramite un hook, non un controller frontale dedicato.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)
-   Nessuna classe o `ObjectModel` personalizzata è definita nella directory `classes/`. Il modulo interagisce direttamente con gli `ObjectModel` core di PrestaShop `Customer` e `Group`.

### 4.4 Risorse JavaScript (`views/js/`)
-   Nessun file JavaScript è incluso con questo modulo.

### 4.5 Fogli di stile CSS (`views/css/`)
-   Nessun file CSS è incluso con questo modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    *   `assigntogroup/views/templates/hook/form.tpl`
        *   **Scopo**: Questo template viene utilizzato per renderizzare il modulo di configurazione del modulo nel Back Office di PrestaShop. Viene renderizzato dal metodo `getContent()` della classe del modulo principale.
        *   **Contenuto**: Contiene la struttura HTML per i due interruttori di configurazione (`asg_unassign`, `asg_default`) e il pulsante di invio del modulo. Utilizza gli elementi standard del modulo helper di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Il modulo non crea tabelle SQL personalizzate.
    *   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration`:
        *   `PS_ASG_UNASSIGN`: Memorizza il valore dell'impostazione "Disassegna il cliente da altri gruppi" (0 o 1).
        *   `PS_ASG_DEFAULT`: Memorizza il valore dell'impostazione "Cambia gruppo in predefinito" (0 o 1).

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Eseguito all'inizio del caricamento della pagina del front-office, all'interno della sezione `<head>`. | Questo è l'hook principale utilizzato dal modulo. Controlla il parametro URL `asg`, verifica se un cliente è loggato e quindi esegue la logica di assegnazione del gruppo in base alle impostazioni di configurazione del modulo (`PS_ASG_UNASSIGN`, `PS_ASG_DEFAULT`). |

### 4.8 File PHP del modulo principale (`assigntogroup/assigntogroup.php`)

Questo è il file centrale per il modulo, contenente la sua installazione, disinstallazione, configurazione e logica principale.

-   **Nome della classe**: `Assigntogroup`
-   **Classe genitore**: `Module`
-   **Metodi chiave**:
    *   `__construct()`: Inizializza i metadati del modulo (nome, tab, versione, autore, ecc.).
    *   `install()`:
        *   Registra l'hook `displayHeader`.
        *   Imposta i valori di configurazione predefiniti per `PS_ASG_UNASSIGN` (0) e `PS_ASG_DEFAULT` (0) in `ps_configuration`.
        *   Restituisce `true` in caso di successo.
    *   `uninstall()`:
        *   Deregistra l'hook `displayHeader`.
        *   Elimina i valori di configurazione `PS_ASG_UNASSIGN` e `PS_ASG_DEFAULT` da `ps_configuration`.
        *   Restituisce `true` in caso di successo.
    *   `getContent()`:
        *   Gestisce l'invio del modulo di configurazione del Back Office del modulo.
        *   Aggiorna `PS_ASG_UNASSIGN` e `PS_ASG_DEFAULT` in `ps_configuration` in base all'input dell'utente.
        *   Renderizza il modulo di configurazione usando `display(__FILE__, 'views/templates/hook/form.tpl')`.
    *   `hookDisplayHeader()`:
        *   **Logica principale**: Questo metodo viene eseguito ad ogni caricamento della pagina del front-office.
        *   Controlla se il parametro GET `asg` è presente ed è un intero valido che rappresenta un `id_group`.
        *   Verifica se un cliente è loggato (`$this->context->customer->isLogged()`).
        *   Recupera l'oggetto `Group` target.
        *   Recupera l'oggetto `Customer` corrente.
        *   In base alla configurazione `PS_ASG_UNASSIGN` e `PS_ASG_DEFAULT`:
            *   Gestisce le associazioni di gruppo del cliente (`$customer->updateGroup()`).
            *   Aggiunge il cliente al gruppo specificato.
            *   Opzionalmente rimuove il cliente da altri gruppi.
            *   Opzionalmente aggiunge il cliente al gruppo predefinito.
        *   Reindirizza l'utente all'URL corrente senza il parametro `asg` per prevenire la rielaborazione all'aggiornamento.

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Link per assegnare il cliente a un gruppo", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda riguardante la funzionalità del modulo.
