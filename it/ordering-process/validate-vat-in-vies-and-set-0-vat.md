---
title: "Convalida partita IVA nel VIES e imposta IVA 0% - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Convalida partita IVA nel VIES e imposta IVA 0%' di MyPresta.eu."
sidebar:
  label: "Convalida partita IVA nel VIES e imposta IVA 0%"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Validate VAT in VIES and set 0% VAT su MyPresta.eu](https://mypresta.eu/modules/ordering-process/validate-vat-in-vies-and-set-0-vat.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/validate-vat-in-vies-and-set-0-vat/)
>
> ---


# Convalida partita IVA nel VIES e imposta IVA 0%

## 1. Requisiti e Compatibilità

Per garantire il buon funzionamento del modulo "Convalida partita IVA nel VIES e imposta IVA 0%", si prega di rivedere i seguenti requisiti:

*   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
*   **Compatibilità PHP**: PHP 7.1 - 8.5
*   **Requisiti di hosting**: Il tuo ambiente di hosting deve supportare le estensioni PHP standard come `cURL` (per comunicare con il sistema VIES), `JSON` e `OpenSSL`. Queste sono tipicamente abilitate per impostazione predefinita sulla maggior parte dei moderni provider di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è l'area di configurazione principale per il modulo, dove controlli il suo comportamento e aspetto. Vai su **Moduli > Gestione moduli**, cerca "Convalida partita IVA nel VIES e imposta IVA 0%" e clicca su "Configura".

#### **Impostazioni generali**

*   **Il tuo paese:**
    *   **Cosa fa questa impostazione:** Definisce il paese in cui è registrata la tua attività. Questo è cruciale per determinare se il numero di partita IVA di un cliente si qualifica per l'IVA 0% (cioè, se proviene da un paese UE *diverso*).
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato sul tuo paese:* Il modulo identificherà correttamente le vendite intracomunitarie.
        *   *Quando impostato in modo errato:* La logica di convalida dell'IVA potrebbe fallire o applicare l'IVA 0% in modo errato.
    *   **Valore consigliato:** Il paese di registrazione ufficiale del tuo negozio (ad esempio, "Italia").
    *   **Scenario / esempio del commerciante:** Se il tuo negozio ha sede in Germania, selezioneresti "Germania". Un cliente dalla Francia con un numero di partita IVA francese valido sarebbe quindi idoneo per l'IVA 0%.
*   **Paesi idonei:**
    *   **Cosa fa questa impostazione:** Ti consente di selezionare quali paesi dell'UE sono idonei per la regola dell'IVA 0%. Puoi scegliere paesi specifici o selezionare tutti i paesi dell'UE.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando sono selezionati paesi specifici:* Solo i clienti di quei paesi (con IVA valida) otterranno l'IVA 0%.
        *   *Quando sono selezionati tutti i paesi dell'UE:* Tutti i paesi dell'UE (escluso il tuo) saranno idonei.
    *   **Valore consigliato:** Seleziona tutti i paesi dell'UE a meno che tu non abbia ragioni commerciali specifiche per escluderne alcuni.
    *   **Scenario / esempio del commerciante:** Se desideri offrire l'IVA 0% solo alle aziende in Francia, Germania e Spagna, selezioneresti solo quei paesi.
*   **Seleziona regola fiscale:**
    *   **Cosa fa questa impostazione:** Specifica quale regola fiscale di PrestaShop deve essere applicata quando l'IVA di un cliente è convalidata come 0%. Dovresti avere una regola fiscale impostata in PrestaShop per l'IVA 0%.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando viene selezionata una regola fiscale 0%:* Il modulo applicherà questa regola agli ordini idonei.
        *   *Quando viene selezionata una regola fiscale errata:* Potrebbe essere applicata l'aliquota fiscale sbagliata, o il modulo potrebbe non funzionare come previsto.
    *   **Valore consigliato:** Una regola fiscale che hai creato in PrestaShop con un'aliquota fiscale dello 0%.
    *   **Scenario / esempio del commerciante:** Creeresti una regola fiscale denominata "IVA B2B UE 0%" con un'aliquota dello 0% e la selezioneresti qui.
*   **Disabilita modulo per le lingue selezionate:**
    *   **Cosa fa questa impostazione:** Ti consente di disabilitare la funzionalità di convalida dell'IVA per lingue specifiche nel tuo negozio. Questo può essere utile se operi in paesi non UE con diverse normative fiscali, ma utilizzi comunque la stessa istanza di PrestaShop.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando le lingue sono selezionate:* Il modulo di convalida dell'IVA e la logica non appariranno o non si applicheranno per i clienti che navigano in quelle lingue.
        *   *Quando non sono selezionate lingue:* Il modulo sarà attivo per tutte le lingue.
    *   **Valore consigliato:** Lascia vuoto a meno che tu non abbia requisiti fiscali specifici basati sulla lingua.
    *   **Scenario / esempio del commerciante:** Se hai una versione inglese del tuo negozio che si rivolge sia a clienti UE che statunitensi, ma desideri la convalida dell'IVA solo per i clienti UE, potresti non disabilitarla. Tuttavia, se hai una vista del negozio separata per un paese non UE (ad esempio, "Giappone"), potresti disabilitarla per la lingua giapponese.

#### **Impostazioni di visualizzazione (Visibilità Front-Office)**

Queste impostazioni controllano dove il modulo di input IVA e i messaggi di stato appaiono ai tuoi clienti.

*   **Mostra modulo di modifica IVA nella barra dell'intestazione:**
    *   **Cosa fa questa impostazione:** Visualizza un piccolo modulo o una notifica nell'area dell'intestazione del tuo negozio, invitando i clienti a inserire il loro numero di partita IVA.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Una barra appare nella parte superiore del tuo sito.
        *   *Quando disabilitato:* Nessun modulo/notifica IVA nell'intestazione.
    *   **Valore consigliato:** "Off" a meno che tu non desideri un'alta visibilità per i clienti B2B.
    *   **Scenario / esempio del commerciante:** Potresti abilitarlo se il tuo negozio è principalmente B2B e desideri informare immediatamente i clienti aziendali sull'IVA 0%.
*   **Mostra modulo di modifica IVA in displayCustomhtml1 (tema personalizzato sp_topdeals):**
    *   **Cosa fa questa impostazione:** Questo è un hook specifico spesso utilizzato da temi personalizzati (come 'sp_topdeals') per visualizzare contenuti personalizzati. L'abilitazione di questa opzione posizionerà il modulo IVA in quell'area specifica.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Il modulo IVA appare nell'area dell'hook `displayCustomhtml1`.
        *   *Quando disabilitato:* Il modulo non apparirà in quest'area personalizzata specifica.
    *   **Valore consigliato:** "Off" a meno che il tuo tema non utilizzi questo hook e tu non voglia il modulo lì.
    *   **Scenario / esempio del commerciante:** Se il tuo tema ha un'area banner prominente in alto e desideri il modulo IVA lì, lo abiliteresti.
*   **Mostra barra di stato IVA per i clienti loggati:**
    *   **Cosa fa questa impostazione:** Visualizza una barra o un messaggio ai clienti loggati, indicando il loro stato IVA attuale (ad esempio, "La tua IVA è valida, 0% applicato").
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I clienti loggati vedono il loro stato IVA.
        *   *Quando disabilitato:* Nessuna barra di stato IVA specifica per gli utenti loggati.
    *   **Valore consigliato:** "On" per fornire chiarezza e rassicurazione ai tuoi clienti B2B.
    *   **Scenario / esempio del commerciante:** Un cliente aziendale che torna si logga e vede immediatamente "La tua IVA è valida, IVA 0% applicata al tuo carrello", il che migliora la sua esperienza di acquisto.
*   **Mostra barra IVA nel passo informazioni personali del checkout:**
    *   **Cosa fa questa impostazione:** Visualizza il campo di input IVA e lo stato di convalida nel primo passo del processo di checkout (dove i clienti inseriscono nome, indirizzo, ecc.). Questa è la posizione più comune e consigliata.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Il campo IVA è visibile e interattivo nel passo delle informazioni personali.
        *   *Quando disabilitato:* Il campo IVA non apparirà in questo passo, potenzialmente rendendo più difficile per i clienti applicare l'IVA 0%.
    *   **Valore consigliato:** "On" (Altamente consigliato).
    *   **Scenario / esempio del commerciante:** Un cliente arriva al checkout, inserisce l'indirizzo della sua azienda e poi inserisce il suo numero di partita IVA nel campo dedicato. Il modulo lo convalida e il prezzo si aggiorna.
*   **Mostra barra IVA nel riepilogo del checkout:**
    *   **Cosa fa questa impostazione:** Visualizza lo stato dell'IVA (ad esempio, "IVA: 0%") nella pagina di riepilogo del checkout, prima del pagamento finale.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I clienti vedono il loro stato IVA nel riepilogo.
        *   *Quando disabilitato:* Nessuno stato IVA specifico nel riepilogo.
    *   **Valore consigliato:** "On" per trasparenza.
    *   **Scenario / esempio del commerciante:** Un cliente rivede il suo ordine prima del pagamento e vede una chiara conferma che è stata applicata l'IVA 0%.
*   **Mostra barra IVA nel passo di pagamento:**
    *   **Cosa fa questa impostazione:** Visualizza lo stato dell'IVA nel passo finale di pagamento del checkout.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I clienti vedono il loro stato IVA nel passo di pagamento.
        *   *Quando disabilitato:* Nessuno stato IVA specifico nel passo di pagamento.
    *   **Valore consigliato:** "On" per la conferma finale.
    *   **Scenario / esempio del commerciante:** Poco prima di cliccare su "Paga ora", il cliente vede "Totale: €100.00 (IVA 0%)", confermando la corretta applicazione dell'imposta.
*   **Mostra barra di modifica IVA nella pagina del prodotto:**
    *   **Cosa fa questa impostazione:** Visualizza un modulo di input IVA o un messaggio di stato direttamente sulle singole pagine dei prodotti.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un modulo/messaggio IVA appare sulle pagine dei prodotti.
        *   *Quando disabilitato:* Nessun modulo/messaggio IVA sulle pagine dei prodotti.
    *   **Valore consigliato:** "Off" per evitare disordine, a meno che tu non abbia un forte focus B2B e desideri mostrare i prezzi IVA esclusa in anticipo.
    *   **Scenario / esempio del commerciante:** Un cliente aziendale che naviga in una pagina di prodotto può inserire il suo numero di partita IVA per vedere immediatamente il prezzo senza IVA, aiutandolo nelle decisioni di acquisto.
*   **Mostra modulo di modifica IVA in displayProductAdditionalInfo:**
    *   **Cosa fa questa impostazione:** Questo è un hook standard di PrestaShop nella pagina del prodotto, tipicamente utilizzato per informazioni aggiuntive. L'abilitazione di questa opzione posizionerà il modulo IVA in quell'area.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Il modulo IVA appare nell'area dell'hook `displayProductAdditionalInfo`.
        *   *Quando disabilitato:* Il modulo non apparirà in quest'area specifica.
    *   **Valore consigliato:** "Off" a meno che tu non lo voglia specificamente lì.
    *   **Scenario / esempio del commerciante:** Simile all'impostazione "Mostra barra di modifica IVA nella pagina del prodotto", ma si rivolge a un hook specifico.
*   **Mostra modulo di modifica IVA in displayBanner:**
    *   **Cosa fa questa impostazione:** Visualizza il modulo IVA o lo stato nell'hook `displayBanner`, che è spesso utilizzato per banner superiori o messaggi promozionali.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Il modulo/stato IVA appare nell'area del banner.
        *   *Quando disabilitato:* Nessun modulo/stato IVA nell'area del banner.
    *   **Valore consigliato:** "Off" per evitare disordine, a meno che tu non abbia un design di banner specifico per questo.
    *   **Scenario / esempio del commerciante:** Potresti usarlo per visualizzare un messaggio "Sei un'azienda? Inserisci la tua partita IVA per IVA 0%!" in un banner prominente.
*   **Mostra modulo di modifica IVA in displayCustomhtml1 (tema personalizzato sp_topdeals):** (Duplicato, già trattato sopra)
*   **Mostra barra di stato IVA per i clienti loggati:** (Duplicato, già trattato sopra)
*   **Mostra barra IVA nel passo informazioni personali del checkout:** (Duplicato, già trattato sopra)
*   **Mostra barra IVA nel riepilogo del checkout:** (Duplicato, già trattato sopra)
*   **Mostra barra IVA nel passo di pagamento:** (Duplicato, già trattato sopra)
*   **Nota di inversione contabile in fattura:**
    *   **Cosa fa questa impostazione:** Quando viene applicata l'IVA 0% a causa di un controllo VIES valido, questa impostazione garantisce che una nota di "Inversione contabile" venga automaticamente aggiunta alla fattura del cliente. Questo è un requisito legale per le vendite B2B intracomunitarie.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Le fatture per ordini con IVA 0% includeranno la nota di inversione contabile.
        *   *Quando disabilitato:* Le fatture non includeranno la nota, potenzialmente portando a non conformità.
    *   **Valore consigliato:** "On" (Altamente consigliato per la conformità legale).
    *   **Scenario / esempio del commerciante:** Un cliente aziendale tedesco acquista dal tuo negozio polacco con un numero di partita IVA valido. La fattura dichiara automaticamente "Inversione contabile - IVA non applicabile ai sensi dell'articolo 196 della Direttiva del Consiglio 2006/112/CE".

#### **Impostazioni avanzate**

*   **Riconvalida il numero di partita IVA del cliente ad ogni ordine:**
    *   **Cosa fa questa impostazione:** Se abilitata, il modulo ricontrollerà il numero di partita IVA del cliente con VIES ogni volta che effettua un ordine, anche se era stato precedentemente convalidato.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Assicura che il numero di partita IVA sia sempre attuale e valido, ma aggiunge un leggero ritardo al checkout.
        *   *Quando disabilitato:* Si basa sulla convalida iniziale, che è più veloce ma potrebbe perdere modifiche nello stato IVA.
    *   **Valore consigliato:** "On" per la massima conformità e accuratezza.
    *   **Scenario / esempio del commerciante:** Il numero di partita IVA di un cliente aziendale potrebbe diventare non valido nel tempo. La riconvalida assicura che tu non applichi erroneamente l'IVA 0% a un numero non valido.
*   **Previeni il flood di richieste VIES (blocca per X minuti):**
    *   **Cosa fa questa impostazione:** Se un cliente inserisce ripetutamente numeri di partita IVA non validi, questa impostazione blocca temporaneamente ulteriori tentativi di convalida per un periodo specificato per prevenire abusi o il sovraccarico del sistema VIES.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Dopo più tentativi falliti, il cliente viene temporaneamente bloccato dal riprovare.
        *   *Quando disabilitato:* Nessuna protezione dal flood, consentendo tentativi illimitati.
    *   **Valore consigliato:** "On" con un tempo di blocco ragionevole (ad esempio, 5-10 minuti).
    *   **Scenario / esempio del commerciante:** Un bot o un utente malintenzionato tenta di indovinare i numeri di partita IVA. Questa impostazione impedisce loro di colpire continuamente l'API VIES.
*   **Memorizza nella cache i risultati della convalida VIES per X ore:**
    *   **Cosa fa questa impostazione:** Memorizza i risultati delle convalide VIES riuscite per un numero specificato di ore. Questo riduce il numero di chiamate dirette al sistema VIES, accelerando il processo e riducendo l'utilizzo di API esterne.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Convalida più veloce per i clienti abituali o entro il periodo di cache.
        *   *Quando disabilitato:* Ogni convalida è una chiamata VIES in tempo reale, che può essere più lenta.
    *   **Valore consigliato:** "On" con un tempo di cache di 24-72 ore (ad esempio, 48 ore).
    *   **Scenario / esempio del commerciante:** Un cliente convalida il suo numero di partita IVA. Se torna sul tuo sito entro 48 ore, il modulo utilizza il risultato memorizzato nella cache invece di effettuare una nuova richiesta VIES.
*   **Ricontrolla lo stato IVA del carrello ogni X secondi:**
    *   **Cosa fa questa impostazione:** Definisce la frequenza con cui il modulo ricontrolla lo stato IVA del carrello in background, particolarmente utile se i prezzi sono dinamici o se il cliente cambia il suo indirizzo/numero di partita IVA durante il checkout.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un valore basso:* Aggiornamenti più frequenti, esperienza potenzialmente più fluida ma maggiore carico del server.
        *   *Quando impostato su un valore alto:* Aggiornamenti meno frequenti, potrebbe richiedere un aggiornamento manuale della pagina per riflettere le modifiche IVA.
    *   **Valore consigliato:** 5-10 secondi.
    *   **Scenario / esempio del commerciante:** Un cliente inserisce il suo numero di partita IVA e, entro 5 secondi, il totale del carrello si aggiorna per riflettere l'IVA 0% senza un ricaricamento della pagina.
*   **Abilita riconvalida automatica del numero di partita IVA (Cron Job):**
    *   **Cosa fa questa impostazione:** Attiva un'attività in background (cron job) che riconvalida periodicamente tutti i numeri di partita IVA dei clienti memorizzati con VIES. Questo assicura che anche i vecchi numeri di partita IVA rimangano validi.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I numeri di partita IVA vengono periodicamente controllati per la validità, garantendo la conformità.
        *   *Quando disabilitato:* I numeri di partita IVA vengono controllati solo al momento dell'inserimento o dell'ordine, potenzialmente portando a informazioni obsolete.
    *   **Valore consigliato:** "On" (Altamente consigliato per la conformità a lungo termine).
    *   **Scenario / esempio del commerciante:** Un cliente ha effettuato un ordine 6 mesi fa con un numero di partita IVA valido. Il cron job lo ricontrolla e scopre che ora non è valido, consentendoti di contrassegnarlo per ordini futuri.
*   **Intervallo di riconvalida del Cron Job (giorni):**
    *   **Cosa fa questa impostazione:** Imposta la frequenza con cui il cron job viene eseguito per riconvalidare i numeri di partita IVA.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un numero basso:* Riconvalide più frequenti, maggiore precisione, ma più richieste VIES.
        *   *Quando impostato su un numero alto:* Riconvalide meno frequenti, minore precisione, meno richieste VIES.
    *   **Valore consigliato:** 30-90 giorni (ad esempio, 60 giorni).
    *   **Scenario / esempio del commerciante:** Impostarlo a 30 giorni significa che tutti i numeri di partita IVA vengono ricontrollati una volta al mese.
*   **Chiave API VIES (Opzionale):**
    *   **Cosa fa questa impostazione:** Ti consente di utilizzare API di convalida IVA alternative (come Apilayer, AbstractAPI, VATStack) invece del sistema VIES predefinito. Queste possono talvolta offrire funzionalità più robuste o opzioni di fallback.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando viene inserita una chiave:* Il modulo tenterà di utilizzare l'API di terze parti specificata per la convalida.
        *   *Quando vuoto:* Il modulo utilizza il sistema VIES ufficiale per impostazione predefinita.
    *   **Valore consigliato:** Lascia vuoto a meno che tu non riscontri problemi con VIES o richieda funzionalità specifiche da un'API di terze parti. Se ne usi una, inserisci la chiave fornita da quel servizio.
    *   **Scenario / esempio del commerciante:** Se il sistema VIES è frequentemente inattivo o lento, potresti abbonarti al servizio di convalida IVA di Apilayer e inserire la tua chiave API qui come alternativa affidabile.

#### **Chiavi API (Opzionale - per servizi di convalida IVA alternativi)**

*   **Chiave API Apilayer:**
    *   **Cosa fa questa impostazione:** Inserisci la tua chiave API se ti abboni al servizio di convalida IVA di Apilayer.
    *   **Effetto della modifica di questa impostazione:** Abilita la convalida tramite Apilayer.
    *   **Valore consigliato:** Lascia vuoto a meno che tu non abbia un account Apilayer.
*   **Chiave API AbstractAPI:**
    *   **Cosa fa questa impostazione:** Inserisci la tua chiave API se ti abboni al servizio di convalida IVA di AbstractAPI.
    *   **Effetto della modifica di questa impostazione:** Abilita la convalida tramite AbstractAPI.
    *   **Valore consigliato:** Lascia vuoto a meno che tu non abbia un account AbstractAPI.
*   **Chiave API VATStack:**
    *   **Cosa fa questa impostazione:** Inserisci la tua chiave API se ti abboni al servizio di convalida IVA di VATStack.
    *   **Effetto della modifica di questa impostazione:** Abilita la convalida tramite VATStack.
    *   **Valore consigliato:** Lascia vuoto a meno che tu non abbia un account VATStack.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Config. principale | Il tuo paese     | Paese del tuo negozio  | Definisce il paese della tua attività per le vendite intracomunitarie. |
| Config. principale | Paesi idonei | Tutti i paesi UE      | Seleziona i paesi UE in cui si applica l'IVA 0%. |
| Config. principale | Seleziona regola fiscale  | La tua regola fiscale 0%      | Specifica la regola fiscale di PrestaShop per l'IVA 0%. |
| Config. principale | Disabilita modulo per le lingue selezionate | Vuoto | Disabilita il modulo per lingue specifiche. |
| Config. principale | Mostra modulo di modifica IVA nella barra dell'intestazione | Off | Visualizza il modulo IVA nell'intestazione. |
| Config. principale | Mostra modulo di modifica IVA in displayCustomhtml1 | Off | Visualizza il modulo IVA nell'hook del tema personalizzato. |
| Config. principale | Mostra barra di stato IVA per i clienti loggati | On | Mostra lo stato IVA agli utenti loggati. |
| Config. principale | Mostra barra IVA nel passo informazioni personali del checkout | On (Altamente consigliato) | Visualizza il campo IVA nel primo passo del checkout. |
| Config. principale | Mostra barra IVA nel riepilogo del checkout | On | Visualizza lo stato IVA nel riepilogo del checkout. |
| Config. principale | Mostra barra IVA nel passo di pagamento | On | Visualizza lo stato IVA nel passo di pagamento. |
| Config. principale | Mostra barra di modifica IVA nella pagina del prodotto | Off | Visualizza il modulo IVA nelle pagine dei prodotti. |
| Config. principale | Mostra modulo di modifica IVA in displayProductAdditionalInfo | Off | Visualizza il modulo IVA nell'hook delle informazioni aggiuntive del prodotto. |
| Config. principale | Mostra modulo di modifica IVA in displayBanner | Off | Visualizza il modulo IVA nell'hook del banner. |
| Config. principale | Nota di inversione contabile in fattura | On (Altamente consigliato) | Aggiunge la nota legale "Inversione contabile" alle fatture. |
| Config. principale | Riconvalida il numero di partita IVA del cliente ad ogni ordine | On | Ricontrolla l'IVA per ogni nuovo ordine. |
| Config. principale | Previeni il flood di richieste VIES (blocca per X minuti) | On (5-10 minuti) | Blocca i tentativi ripetuti di IVA non valida. |
| Config. principale | Memorizza nella cache i risultati della convalida VIES per X ore | On (24-72 ore) | Memorizza nella cache i risultati VIES per velocizzare la convalida. |
| Config. principale | Ricontrolla lo stato IVA del carrello ogni X secondi | 5-10 secondi | Frequenza di aggiornamento dello stato IVA del carrello. |
| Config. principale | Abilita riconvalida automatica del numero di partita IVA (Cron Job) | On (Altamente consigliato) | Attiva la riconvalida in background di tutti i numeri di partita IVA. |
| Config. principale | Intervallo di riconvalida del Cron Job (giorni) | 30-90 giorni (ad esempio, 60) | Frequenza di riconvalida del cron job. |
| Config. principale | Chiave API Apilayer | Vuoto | Chiave per il servizio di convalida IVA Apilayer. |
| Config. principale | Chiave API AbstractAPI | Vuoto | Chiave per il servizio di convalida IVA AbstractAPI. |
| Config. principale | Chiave API VATStack | Vuoto | Chiave per il servizio di convalida IVA VATStack. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### **Audit di convalida IVA (Back Office > Clienti > Audit di convalida IVA)**

Questa sezione dedicata ti consente di rivedere e gestire tutti i tentativi di convalida IVA effettuati tramite il tuo negozio.

*   **Nome schermata e posizione menu:** **Clienti > Audit di convalida IVA** (Questa nuova voce di menu è aggiunta dal modulo).
*   **Azioni e impostazioni disponibili:**
    *   **Vista Griglia / Gestione:** Questa schermata presenta una tabella (griglia) di tutti i tentativi di convalida IVA. Per ogni voce, vedrai tipicamente:
        *   **Nome cliente:** Il nome del cliente associato alla convalida.
        *   **Numero di partita IVA:** Il numero di partita IVA che è stato inserito.
        *   **Paese:** Il codice del paese associato al numero di partita IVA.
        *   **Stato di convalida:** Se il numero di partita IVA era "Valido", "Non valido" o "Errore" (ad esempio, sistema VIES non disponibile).
        *   **Data di convalida:** Quando è avvenuto il tentativo di convalida.
        *   **ID ordine:** Se la convalida ha portato a un ordine, l'ID dell'ordine associato.
        *   **Fonte:** Dove è avvenuta la convalida (ad esempio, "Checkout", "Account cliente").
        *   **Dettagli/Motivo:** Maggiori informazioni sul risultato della convalida, specialmente per le voci non valide.
    *   **Filtro e Ordinamento:** Di solito puoi filtrare l'elenco per cliente, numero di partita IVA, stato o intervallo di date per trovare voci specifiche. L'ordinamento ti consente di organizzare i dati.
    *   **Esporta:** Il modulo potrebbe offrire un'opzione per esportare questo registro di audit, utile per la contabilità e gli audit fiscali.
*   **Effetto delle modifiche:** Questa schermata è principalmente per l'audit e la reportistica. Non puoi modificare direttamente lo stato IVA di un cliente qui, ma puoi rivedere la cronologia delle convalide. Questi dati sono cruciali per dimostrare la conformità durante le ispezioni fiscali.
*   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Rivedi periodicamente questo registro di audit, specialmente se noti discrepanze nell'applicazione dell'IVA o ricevi richieste dai clienti sull'IVA.
    2.  Cerca gli stati "Non valido" o "Errore" per identificare potenziali problemi con l'input del cliente o la disponibilità del sistema VIES.
    3.  Usa la funzione di esportazione per fornire dati al tuo commercialista o alle autorità fiscali, se richiesto.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Audit di convalida IVA | Vista Griglia | N/A | Visualizza un registro storico di tutti i tentativi di convalida IVA. |
| Audit di convalida IVA | Filtri e Ordinamento | N/A | Aiuta a localizzare voci di convalida specifiche. |
| Audit di convalida IVA | Esporta dati | N/A | Consente l'esportazione del registro di audit per la tenuta dei registri e a fini fiscali. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti stanno inserendo numeri di partita IVA validi, ma l'IVA 0% non viene applicata.**
*   **R:**
    1.  **Controlla l'impostazione "Il tuo paese":** Assicurati che sia impostata correttamente sul paese del tuo negozio nella configurazione del modulo.
    2.  **Verifica "Paesi idonei":** Assicurati che il paese del cliente sia selezionato nell'elenco dei paesi idonei.
    3.  **Conferma "Seleziona regola fiscale":** Assicurati di aver creato una regola fiscale 0% in PrestaShop (**Internazionale > Tasse > Regole tasse**) e che sia correttamente selezionata nelle impostazioni del modulo.
    4.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache". A volte la vecchia cache può impedire che le nuove impostazioni abbiano effetto.
    5.  **Controlla la disponibilità del VIES:** Il sistema VIES a volte può essere temporaneamente non disponibile. Puoi controllare il suo stato sul sito web ufficiale della Commissione Europea.

**D2: Il modulo di convalida IVA non appare nella mia pagina di checkout.**
*   **A:**
    1.  **Controlla le impostazioni di visualizzazione:** Nella configurazione del modulo, assicurati che "Mostra barra IVA nel passo informazioni personali del checkout" (e altre opzioni di visualizzazione pertinenti) sia impostato su "On".
    2.  **Compatibilità del tema:** Se stai utilizzando un tema altamente personalizzato, potrebbe sovrascrivere gli hook standard di PrestaShop. Controlla se il tuo tema ha aree specifiche per `displayProductAdditionalInfo`, `displayCustomhtml1` o altri hook in cui hai provato a posizionare il modulo. Potrebbe essere necessario consultare lo sviluppatore del tuo tema.
    3.  **Conflitti tra moduli:** Disabilita temporaneamente altri moduli relativi al checkout per vedere se c'è un conflitto.

**D3: Vedo messaggi di "Errore" o "VIES non disponibile" durante la convalida.**
*   **A:**
    1.  **Stato del sistema VIES:** Il sistema VIES può subire tempi di inattività. Controlla il sito web ufficiale del VIES per lo stato attuale.
    2.  **Estensione cURL:** Assicurati che il tuo provider di hosting abbia l'estensione PHP `cURL` abilitata. Questo è essenziale affinché il modulo possa comunicare con API esterne come VIES. Contatta il tuo host se non sei sicuro.
    3.  **Firewall/Sicurezza:** Il firewall o le impostazioni di sicurezza del tuo server potrebbero bloccare le connessioni in uscita al server VIES. Ancora una volta, contatta il tuo provider di hosting.
    4.  **Chiavi API:** Se stai cercando di utilizzare un'API di terze parti (Apilayer, AbstractAPI, VATStack), assicurati che la chiave API sia inserita correttamente e attiva con quel servizio.

**D4: Come mi assicuro che il cron job per la riconvalida sia in esecuzione?**
*   **A:**
    1.  **Abilita Cron Job:** Nella configurazione del modulo, assicurati che "Abilita riconvalida automatica del numero di partita IVA (Cron Job)" sia "On".
    2.  **Modulo Cron di PrestaShop:** Hai bisogno di un modulo cron job separato di PrestaShop (ad esempio, "Gestore attività cron" di PrestaShop) installato e configurato per attivare periodicamente l'attività cron del modulo.
    3.  **Cron di hosting:** In alternativa, puoi impostare un cron job a livello di server (tramite cPanel, Plesk o SSH) per chiamare l'URL cron del modulo. La configurazione del modulo di solito fornisce l'URL esatto da utilizzare.
    4.  **Controlla il registro di audit:** Dopo che il cron job dovrebbe essere stato eseguito, controlla la schermata "Audit di convalida IVA" nel Back Office. Dovresti vedere nuove voci di convalida con una fonte "Cron".

**D5: Perché alcuni paesi dell'UE non compaiono nell'elenco "Paesi idonei"?**
*   **A:** Il modulo si basa sull'elenco dei paesi di PrestaShop. Assicurati che tutti i paesi UE desiderati siano abilitati nel tuo negozio PrestaShop (**Internazionale > Localizzazione > Paesi**) e che siano contrassegnati come "È un paese UE" e "Contiene stati" (se applicabile).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Convalida partita IVA nel VIES e imposta IVA 0%", progettata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo segue un modello MVC (Model-View-Controller) standard di PrestaShop, sfruttando pesantemente gli hook per l'integrazione nel front e back office. Introduce diverse classi personalizzate per la logica di business, l'interazione con le API e la gestione dei dati. I componenti chiave includono:

*   **Classe principale del modulo (`eurovat.php`):** Gestisce l'installazione, la disinstallazione, la registrazione degli hook e il modulo di configurazione principale (`getContent()`).
*   **Controller front-office:** Gestiscono le richieste AJAX per la convalida IVA e l'invio di moduli.
*   **Controller admin:** Forniscono interfacce dedicate per l'audit della convalida IVA.
*   **Classi Core:** Incapsulano la logica di business per l'interazione con VIES, la gestione delle tasse, l'analisi e la persistenza dei dati (spesso estendendo `ObjectModel` o utilizzando un pattern repository).
*   **Template:** Template Smarty per il rendering di moduli front-office, configurazione back-office e viste di audit.
*   **Hook:** Ampio uso di hook per iniettare funzionalità in vari punti del ciclo di vita di PrestaShop (ad esempio, pagina del prodotto, checkout, elaborazione degli ordini, vista cliente admin).

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

*   `controllers/front/cron.php`
    *   **Nome classe:** `EurovatCronModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Gestisce l'esecuzione del cron job del modulo. Questo controller viene tipicamente chiamato da un servizio cron esterno (ad esempio, cron del server o modulo `Gestore attività cron` di PrestaShop) per attivare attività in background come la riconvalida dei numeri di partita IVA. Elabora l'hook `ActionCronJob`.
*   `controllers/front/form.php`
    *   **Nome classe:** `EurovatFormModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Probabilmente gestisce la visualizzazione e l'invio del modulo di input IVA in vari contesti del front-office (ad esempio, pagina del prodotto, blocchi HTML personalizzati). Potrebbe renderizzare `views/templates/front/form.tpl`.
*   `controllers/front/index.php`
    *   **Nome classe:** `EurovatIndexModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Un controller front-office generico, potenzialmente utilizzato per fallback o logica di visualizzazione semplice. Spesso, `index.php` in una directory di controller funge da segnaposto o da base per altri controller.
*   `controllers/front/validate.php`
    *   **Nome classe:** `EurovatValidateModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** L'endpoint AJAX principale per la convalida in tempo reale del numero di partita IVA. Riceve il numero di partita IVA e i dati del paese, interagisce con il client VIES e restituisce una risposta JSON che indica la validità e potenzialmente aggiorna lo stato fiscale del carrello.

#### Controller Admin Back-Office

*   `controllers/admin/AdminEurovatVatValidationAuditController.php`
    *   **Nome classe:** `AdminEurovatVatValidationAuditController` (estende `ModuleAdminController`)
    *   **Nome scheda:** "Audit di convalida IVA" (sotto il menu Clienti)
    *   **Entità gestita:** `EurovatValidation` (tabella personalizzata `ps_eurovat_validation`)
    *   **Responsabilità:** Fornisce l'interfaccia amministrativa per la visualizzazione, il filtro e la gestione del registro di audit di tutti i tentativi di convalida IVA. Utilizza i componenti `HelperList` o `Grid` di PrestaShop per visualizzare i dati dalla tabella `ps_eurovat_validation`.
*   `controllers/admin/index.php`
    *   **Nome classe:** `EurovatIndexAdminController` (estende `ModuleAdminController`)
    *   **Responsabilità:** Simile a `index.php` del front-office, questo è probabilmente un segnaposto o un controller di base. Potrebbe reindirizzare alla configurazione principale o al controller di audit.

### 4.3 Classi e modelli Core (`classes/`)

*   `classes/EurovatAlertService.php`
    *   **Responsabilità:** Gestisce e visualizza avvisi o notifiche all'interno del modulo, possibilmente relativi allo stato VIES, a problemi di chiave API o a problemi di configurazione.
*   `classes/EurovatAlertsHelper.php`
    *   **Responsabilità:** Una classe helper per `EurovatAlertService`, che fornisce funzioni di utilità per la gestione degli avvisi.
*   `classes/EurovatAnalyticsService.php`
    *   **Responsabilità:** Raccoglie ed elabora dati relativi alla convalida IVA, come tassi di successo, tipi di errore e utilizzo delle API, potenzialmente per la visualizzazione in un widget della dashboard.
*   `classes/EurovatApiUsageHelper.php`
    *   **Responsabilità:** Traccia e gestisce l'utilizzo delle API di convalida IVA esterne (VIES, Apilayer, ecc.), implementando potenzialmente la limitazione della frequenza o il monitoraggio.
*   `classes/EurovatAuditHelper.php`
    *   **Responsabilità:** Assiste `AdminEurovatVatValidationAuditController` nella gestione e nell'interrogazione della tabella `ps_eurovat_validation`.
*   `classes/EurovatConfiguration.php`
    *   **Responsabilità:** Una classe statica o singleton per centralizzare l'accesso ai valori di configurazione del modulo (`Configuration::get('EUROVAT_...')`). Fornisce un modo più pulito per recuperare le impostazioni.
*   `classes/EurovatCronHelper.php`
    *   **Responsabilità:** Contiene la logica eseguita dal cron job, come l'iterazione attraverso i numeri di partita IVA dei clienti e l'avvio della riconvalida.
*   `classes/EurovatErrorClassifier.php`
    *   **Responsabilità:** Categorizza e fornisce messaggi user-friendly per diversi tipi di errori di convalida IVA (ad esempio, formato non valido, VIES non disponibile, mancata corrispondenza del paese).
*   `classes/EurovatExportService.php`
    *   **Responsabilità:** Gestisce l'esportazione dei dati di audit della convalida IVA, probabilmente in formato CSV o Excel.
*   `classes/EurovatOrderProofHelper.php`
    *   **Responsabilità:** Raccoglie e prepara i dati relativi alla convalida IVA per un ordine specifico, utilizzati per generare la prova dell'applicazione dell'IVA 0%.
*   `classes/EurovatOrderTaxNormalizer.php`
    *   **Responsabilità:** Regola i dettagli fiscali dell'ordine quando viene applicata l'IVA 0%, garantendo la coerenza tra carrello, ordine e fattura.
*   `classes/EurovatProofPackService.php`
    *   **Responsabilità:** Potrebbe creare un "pacchetto di prova" (ad esempio, un documento PDF) contenente tutte le prove necessarie per una transazione con IVA 0%.
*   `classes/EurovatTaxManager.php`
    *   **Responsabilità:** La classe centrale per l'applicazione e la gestione delle modifiche fiscali basate sui risultati della convalida IVA, interagendo con il sistema fiscale di PrestaShop.
*   `classes/EurovatTaxService.php`
    *   **Responsabilità:** Fornisce metodi di utilità relativi ai calcoli e all'applicazione delle tasse all'interno del modulo.
*   `classes/EurovatValidationRepository.php`
    *   **Con quale tabella del database interagisce:** `ps_eurovat_validation`
    *   **Se estende `ObjectModel`:** Probabilmente non direttamente, ma gestisce oggetti `EurovatValidation` o query di database grezze.
    *   **Metodi pubblici chiave e logica di business incapsulata:** Operazioni CRUD per i record di convalida IVA, interrogazione della cronologia di convalida, memorizzazione dei risultati di convalida.
*   `classes/EurovatViesClient.php`
    *   **Responsabilità:** L'interfaccia principale per la comunicazione con il sistema VIES (o API alternative come Apilayer, AbstractAPI, VATStack). Gestisce le richieste API, le risposte e la gestione degli errori.
*   `classes/index.php`
    *   **Responsabilità:** Un segnaposto di sicurezza per impedire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

*   `eurovat/views/js/adminEurovatAlerts.js`
    *   **Ambito:** Back-office
    *   **Descrizione:** Gestisce la visualizzazione e l'interazione con gli avvisi nel pannello di amministrazione, potenzialmente aggiornamenti dinamici o messaggi ignorabili.
*   `eurovat/views/js/adminEurovatCountries.js`
    *   **Ambito:** Back-office
    *   **Descrizione:** Gestisce l'interfaccia di selezione del paese nella configurazione del modulo, possibilmente con funzionalità di selezione multipla o filtro dinamico.
*   `eurovat/views/js/adminEurovatCron.js`
    *   **Ambito:** Back-office
    *   **Descrizione:** Fornisce la logica UI per le impostazioni del cron job, visualizzando potenzialmente gli orari dell'ultima esecuzione, la prossima esecuzione programmata o le opzioni di attivazione manuale.
*   `eurovat/views/js/adminEurovatDashboard.js`
    *   **Ambito:** Back-office
    *   **Descrizione:** Alimenta il widget della dashboard (se presente) che visualizza analisi o metriche chiave relative alla convalida IVA. Utilizza AJAX per recuperare i dati e potenzialmente librerie di grafici.
*   `eurovat/views/js/adminEurovatTooltips.js`
    *   **Ambito:** Back-office
    *   **Descrizione:** Inizializza e gestisce i tooltip per le opzioni di configurazione nel pannello di amministrazione, fornendo un contesto utile.
*   `eurovat/views/js/eurovat.js`
    *   **Ambito:** Front-office
    *   **Descrizione:** Il principale JavaScript del front-office.
        *   **Listener di eventi:** Si lega agli eventi di input sul campo del numero di partita IVA (ad esempio, `keyup`, `change`), agli invii di moduli e potenzialmente a `prestashop.on('updateCart')` o eventi simili.
        *   **Manipolazione del DOM:** Visualizza dinamicamente i messaggi di stato di convalida (valido/non valido), aggiorna i totali del carrello, mostra/nasconde elementi in base allo stato IVA.
        *   **Chiamate AJAX:** Invia il numero di partita IVA e i dati del paese a `controllers/front/validate.php` per la convalida in tempo reale.
        *   **Altro:** Implementa l'intervallo di "ricontrollo dello stato IVA del carrello", la logica di protezione dal flood.
*   `eurovat/views/js/eurovatBoMockConsole.js`
    *   **Ambito:** Back-office (sviluppo/debug)
    *   **Descrizione:** Probabilmente un'utilità per simulare l'output della console o fornire funzionalità di debug avanzate all'interno del Back Office di PrestaShop, non tipicamente utilizzata in produzione.

### 4.5 Fogli di stile CSS (`views/css/`)

*   `eurovat/views/css/admin_eurovat.css`
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Componenti e contenitori UI principali che stilizza:** Elementi della pagina di configurazione, tabella dell'elenco di audit, widget della dashboard, avvisi e tooltip all'interno dell'interfaccia di amministrazione del modulo.
    *   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** `.eurovat-admin-config`, `.eurovat-alert`, `.eurovat-dashboard-widget`, `.eurovat-audit-table`.
*   `eurovat/views/css/eurovat.css`
    *   **Ambito:** Stile del cliente del Front-office.
    *   **Componenti e contenitori UI principali che stilizza:** Campi di input IVA, messaggi di stato di convalida (successo/errore), barre di stato IVA nell'intestazione/pagina del prodotto/checkout, note di inversione contabile.
    *   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** `.eurovat-vat-form`, `.eurovat-status-message.valid`, `.eurovat-status-message.invalid`, `.eurovat-header-bar`, `.eurovat-product-vat-info`, `.eurovat-checkout-vat-status`.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

*   `eurovat/views/templates/hook/adminDashboardWidget.tpl`
    *   **Hook:** Potenzialmente `displayAdminHomeQuickview` o un hook dashboard personalizzato.
    *   **Output:** Un widget per la dashboard di amministrazione di PrestaShop, che visualizza analisi o statistiche rapide relative alla convalida IVA.
*   `eurovat/views/templates/hook/adminOrderProofPack.tpl`
    *   **Hook:** `displayAdminOrder` o `displayAdminOrderTabContent` (nella pagina di visualizzazione dell'ordine).
    *   **Output:** Un blocco o una scheda all'interno della pagina dei dettagli dell'ordine di amministrazione, che consente agli amministratori di visualizzare o generare documenti di prova IVA per un ordine specifico.
*   `eurovat/views/templates/hook/customerHistory.tpl`
    *   **Hook:** `displayCustomerAccount` o `displayMyAccountBlock`.
    *   **Output:** Informazioni sulla cronologia di convalida IVA del cliente o sullo stato attuale all'interno della sua area account personale.
*   `eurovat/views/templates/hook/displayBanner.tpl`
    *   **Hook:** `displayBanner` (o hook banner globale simile).
    *   **Output:** Il modulo di input IVA o un messaggio promozionale sull'IVA 0%, tipicamente visualizzato nella parte superiore del negozio.

#### Template admin (`views/templates/admin/`)

*   `eurovat/views/templates/admin/alerts.tpl`
    *   **Output:** Struttura HTML per la visualizzazione di vari avvisi e notifiche nel Back Office.
*   `eurovat/views/templates/admin/audit.tpl`
    *   **Output:** Il template principale per `AdminEurovatVatValidationAuditController`, che renderizza l'elenco di audit della convalida IVA.
*   `eurovat/views/templates/admin/configure.tpl`
    *   **Output:** Il modulo di configurazione principale per il modulo, renderizzato da `getContent()` in `eurovat.php`. Contiene tutte le impostazioni descritte nella sezione 4.1.
*   `eurovat/views/templates/admin/countriesSelector.tpl`
    *   **Output:** Un template riutilizzabile per l'interfaccia di selezione del paese all'interno della configurazione.
*   `eurovat/views/templates/admin/cron.tpl`
    *   **Output:** La sezione di configurazione relativa alle impostazioni del cron job, inclusi intervallo e attivazione.
*   `eurovat/views/templates/admin/dashboard.tpl`
    *   **Output:** La vista completa della dashboard, che potenzialmente integra `adminDashboardWidget.tpl` e altre analisi.
*   `eurovat/views/templates/admin/hooksRepair.tpl`
    *   **Output:** Un template di utilità, possibilmente per la diagnosi e la riparazione di hook mancanti o registrati in modo errato.
*   `eurovat/views/templates/admin/proof_pack_view.tpl`
    *   **Output:** Una vista dettagliata per un pacchetto di prova IVA, probabilmente all'interno della pagina dei dettagli dell'ordine.
*   `eurovat/views/templates/admin/vat_audit_list_settings.tpl`
    *   **Output:** Impostazioni o filtri specifici per la visualizzazione dell'elenco di audit IVA.
*   `eurovat/views/templates/admin/vat_audit_tabs.tpl`
    *   **Output:** Navigazione a schede per la sezione di audit IVA, se ci sono più sottosezioni (ad esempio, registro di audit, analisi).

#### Template front-office (`views/templates/front/`)

*   `eurovat/views/templates/front/form.tpl`
    *   **Output:** La struttura HTML principale per il modulo di input del numero di partita IVA, utilizzata in vari hook del front-office (pagina del prodotto, checkout, intestazione).

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

*   `ps_eurovat_validation`
    *   **Scopo:** Memorizza un registro storico di tutti i tentativi di convalida IVA.
    *   **Campi chiave (previsti):**
        *   `id_eurovat_validation` (Chiave primaria)
        *   `id_customer` (Chiave esterna a `ps_customer`)
        *   `id_cart` (Chiave esterna a `ps_cart`)
        *   `id_order` (Chiave esterna a `ps_order`)
        *   `vat_number` (Il numero di partita IVA inserito)
        *   `country_code` (Il codice del paese associato al numero di partita IVA)
        *   `validation_status` (ad esempio, 'valido', 'non valido', 'errore')
        *   `validation_response` (Risposta grezza da VIES/API)
        *   `validation_date` (Timestamp della convalida)
        *   `source` (ad esempio, 'checkout', 'customer_account', 'cron')
        *   `ip_address` (Indirizzo IP dell'utente che ha eseguito la convalida)

*   `ps_configuration`
    *   **Scopo:** Memorizza tutte le impostazioni di configurazione del modulo.
    *   **Chiavi di configurazione chiave:**
        *   `EUROVAT_YOUR_COUNTRY`
        *   `EUROVAT_ELIGIBLE_COUNTRIES`
        *   `EUROVAT_TAX_RULE`
        *   `EUROVAT_DISPLAY_HEADER`
        *   `EUROVAT_DISPLAY_CUSTOMHTML1`
        *   `EUROVAT_DISPLAY_LOGGED_STATUS`
        *   `EUROVAT_DISPLAY_CHECKOUT_PERSONAL`
        *   `EUROVAT_DISPLAY_CHECKOUT_SUMMARY`
        *   `EUROVAT_DISPLAY_CHECKOUT_PAYMENT`
        *   `EUROVAT_DISPLAY_PRODUCT_PAGE`
        *   `EUROVAT_REVERSE_CHARGE_NOTE`
        *   `EUROVAT_REVALIDATE_ON_ORDER`
        *   `EUROVAT_FLOOD_OFF_MINUTES`
        *   `EUROVAT_CACHE_TTL_HOURS`
        *   `EUROVAT_CART_RECHECK_INTERVAL`
        *   `EUROVAT_CRON_REVALIDATE_ENABLED`
        *   `EUROVAT_CRON_INTERVAL_DAYS`
        *   `EUROVAT_APILAYER_KEY`
        *   `EUROVAT_ABSTRACTAPI_KEY`
        *   `EUROVAT_VATSTACK_KEY`
        *   `EUROVAT_DISABLED_LANGS`

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta CSS/JS o visualizza una barra di stato IVA globale. |
| `displayProductAdditionalInfo` | Nella pagina del prodotto, tipicamente sotto la descrizione del prodotto. | Visualizza il modulo di input IVA o lo stato nelle pagine dei prodotti. |
| `displayCustomhtml1` | Hook personalizzato, spesso nella sezione superiore del tema (ad esempio, `sp_topdeals`). | Visualizza il modulo di input IVA in aree specifiche del tema. |
| `displayPaymentTop` | Nella parte superiore del passo di pagamento nel checkout. | Visualizza lo stato IVA o il modulo prima del pagamento. |
| `displayBanner` | In un'area banner, tipicamente nella parte superiore del sito. | Visualizza il modulo di input IVA o un messaggio promozionale. |
| `displayAdminCustomers` | Nell'elenco clienti o nella pagina dei dettagli del cliente nel BO. | Aggiungi informazioni o azioni relative all'IVA per i clienti. |
| `ActionDispatcher` | Prima che un controller venga inviato. | Modifica il routing o il contesto in base allo stato IVA. |
| `ActionGetProductPropertiesAfter` | Dopo il recupero delle proprietà del prodotto. | Regola i prezzi dei prodotti in base allo stato IVA del cliente. |
| `ActionProductPriceCalculation` | Durante il calcolo del prezzo del prodotto. | Applica l'IVA 0% ai prezzi dei prodotti se idoneo. |
| `ActionBeforeValidateOrder` | Poco prima che un ordine venga convalidato. | Esegui la convalida finale dell'IVA, regola le tasse dell'ordine. |
| `ActionCronJob` | Attivato dal modulo cron di PrestaShop. | Esegui attività in background come la riconvalida IVA. |
| `ActionObjectAddressUpdateAfter` | Dopo l'aggiornamento di un oggetto indirizzo (ad esempio, nell'account cliente). | Riconvalida l'IVA se i dettagli dell'indirizzo cambiano. |
| `ActionTaxManager` | Quando le regole fiscali vengono gestite o applicate. | Intercetta e modifica l'applicazione delle tasse in base alla convalida IVA. |
| `ActionPresentCart` | Prima della visualizzazione del carrello. | Aggiorna i totali del carrello e visualizza lo stato IVA. |
| `ActionFilterDeliveryOptionList` | Filtra le opzioni di consegna disponibili. | Potenziale regolazione dei costi di consegna in base allo stato IVA (meno comune). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team è dedicato a garantire che il modulo funzioni in modo ottimale e rimanga compatibile con le più recenti versioni di PrestaShop.

*   **MyPresta.eu Cronologia ordini e download:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
*   **MyPresta.eu Supporto:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
