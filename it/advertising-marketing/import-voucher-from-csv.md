---
title: "Importa voucher da CSV - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Importa voucher da CSV di MyPresta.eu."
sidebar:
  label: "Importa voucher da CSV - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Import voucher from CSV su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/import-voucher-from-csv.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/import-voucher-from-csv/)
>
> ---


# Importa voucher da CSV

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e solitamente abilitate di default sulla maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale del modulo. Qui caricherai il tuo file CSV e definirai come i codici voucher devono essere importati e quali proprietà devono avere.

La pagina di configurazione è tipicamente strutturata in diverse sezioni, guidandoti attraverso il processo di importazione.

#### **Passaggio 1: Carica il tuo file CSV**

-   **Cosa fa questa impostazione:** Qui selezioni il file CSV contenente i tuoi codici voucher dal tuo computer.
-   **Effetto della modifica di questa impostazione:** Cliccando su "Sfoglia" o "Scegli file" si apre una finestra di dialogo per la selezione del file. Una volta selezionato un file, il suo nome apparirà accanto al pulsante, indicando che è pronto per il caricamento.
-   **Valore consigliato:** Seleziona il file CSV che hai preparato con i tuoi codici voucher.
-   **Scenario / esempio del commerciante:** Hai ricevuto un elenco di 1000 codici voucher unici da un partner come Groupon. Hai salvato questi codici in un file CSV (es. `groupon_vouchers.csv`). Cliccheresti su "Scegli file" e selezioneresti questo file.

#### **Passaggio 2: Impostazioni file CSV**

Questa sezione definisce come il modulo deve interpretare il tuo file CSV.

-   **Separatore CSV:**

    -   **Cosa fa questa impostazione:** Specifica il carattere utilizzato per separare i valori (colonne) all'interno del tuo file CSV. I separatori comuni sono la virgola (`,`), il punto e virgola (`;`) o il tab (`\t`).
    -   **Effetto della modifica di questa impostazione:** Se viene scelto il separatore sbagliato, il modulo non analizzerà correttamente il tuo file e tutti i dati potrebbero apparire in una singola colonna o essere divisi in modo errato.
    -   **Valore consigliato:** Corrisponde al separatore utilizzato quando hai creato o esportato il tuo file CSV. La maggior parte dei software di fogli di calcolo utilizza la virgola come predefinito.
    -   **Scenario / esempio del commerciante:** Se il tuo CSV assomiglia a `CODE123,10,USD`, sceglieresti "Virgola". Se è `CODE123;10;USD`, sceglieresti "Punto e virgola".
-   **Delimitatore di testo:**

    -   **Cosa fa questa impostazione:** Specifica il carattere utilizzato per racchiudere i valori di testo, specialmente quelli che potrebbero contenere il carattere separatore. Spesso, questo è un doppio apice (`"`).
    -   **Effetto della modifica di questa impostazione:** Se i tuoi campi di testo contengono il separatore (es. un nome di prodotto con una virgola) e non sono correttamente delimitati, il modulo potrebbe interpretare erroneamente i dati, portando a un'analisi errata.
    -   **Valore consigliato:** Corrisponde al delimitatore utilizzato nel tuo CSV. Solitamente "Doppio apice".
    -   **Scenario / esempio del commerciante:** Se una descrizione del voucher è `"10% di sconto, offerta a tempo limitato"` e il tuo separatore è una virgola, i doppi apici assicurano che "10% di sconto, offerta a tempo limitato" sia trattato come un unico campo.
-   **Salta la prima riga (intestazione):**

    -   **Cosa fa questa impostazione:** Se il tuo file CSV ha una riga di intestazione (es. `Codice Voucher,Importo Sconto,Data di Scadenza`) che descrive le colonne, abilitando questa opzione dirai al modulo di ignorare quella prima riga durante l'importazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* La riga di intestazione viene saltata e vengono importate solo le righe di dati effettive.
        -   *Quando disabilitato:* La prima riga del tuo CSV verrà trattata come un codice voucher o dati, il che di solito è errato e può portare a errori.
    -   **Valore consigliato:** "SÌ" se il tuo CSV ha una riga di intestazione, "NO" se contiene solo dati.
    -   **Scenario / esempio del commerciante:** Il tuo CSV inizia con `code,value,currency`. Abiliteresti questa opzione per evitare che "code" venga importato come un voucher effettivo.

#### **Passaggio 3: Impostazioni voucher (Proprietà generali)**

Questa sezione definisce le proprietà comuni per tutti i voucher che stai importando. Queste impostazioni si applicano a *tutti* i codici nel tuo file CSV.

-   **Nome:**

    -   **Cosa fa questa impostazione:** Questo è il nome interno della regola del voucher nel tuo Back Office. Ti aiuta a identificare il gruppo di voucher.
    -   **Effetto della modifica di questa impostazione:** Questo nome è visibile solo a te nel Back Office, non ai clienti.
    -   **Valore consigliato:** Un nome descrittivo, es. "Codici Groupon - Maggio 2024".
    -   **Scenario / esempio del commerciante:** Stai importando codici da una campagna "Saldi Estivi 2024". Lo chiameresti "Voucher Saldi Estivi 2024".
-   **Descrizione:**

    -   **Cosa fa questa impostazione:** Una descrizione interna opzionale per la regola del voucher.
    -   **Effetto della modifica di questa impostazione:** Fornisce più contesto per il tuo team nel Back Office.
    -   **Valore consigliato:** Una breve spiegazione, es. "Codici unici per il 10% di sconto, monouso, scade il 31/05/2024".
    -   **Scenario / esempio del commerciante:** "Codici forniti da LivingSocial per i nuovi clienti."
-   **Evidenzia:**

    -   **Cosa fa questa impostazione:** Determina se il voucher viene evidenziato nel riepilogo del carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il voucher sarà visualizzato in modo più prominente nel riepilogo del carrello, attirando potenzialmente più attenzione sullo sconto.
        -   *Quando disabilitato:* Il voucher sarà elencato normalmente.
    -   **Valore consigliato:** "NO" per uso generale, "SÌ" se vuoi enfatizzare lo sconto.
    -   **Scenario / esempio del commerciante:** Per un'offerta speciale a tempo limitato, potresti abilitare "SÌ" per assicurarti che i clienti notino lo sconto applicato.
-   **Uso parziale:**

    -   **Cosa fa questa impostazione:** Consente ai clienti di utilizzare solo una parte del valore del voucher e di conservare il resto per acquisti futuri.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Se un cliente ha un voucher da $50 e acquista un articolo da $30, conserva un saldo di $20 sul voucher.
        -   *Quando disabilitato:* L'intero valore del voucher deve essere utilizzato in una transazione; qualsiasi saldo rimanente viene perso.
    -   **Valore consigliato:** "NO" per la maggior parte dei codici sconto. "SÌ" per buoni regalo o credito del negozio.
    -   **Scenario / esempio del commerciante:** Se stai importando codici di buoni regalo, abiliteresti "SÌ". Per un coupon standard "10% di sconto", useresti "NO".
-   **Priorità:**

    -   **Cosa fa questa impostazione:** Determina l'ordine in cui vengono applicati più voucher se un cliente ne usa più di uno. I voucher con priorità più alta vengono applicati per primi.
    -   **Effetto della modifica di questa impostazione:** Può influenzare l'importo finale dello sconto se più voucher interagiscono (es. sconti percentuali vs. sconti a importo fisso).
    -   **Valore consigliato:** "1" per la massima priorità, o lasciare il valore predefinito se non hai interazioni complesse tra i voucher.
    -   **Scenario / esempio del commerciante:** Se hai un voucher "Spedizione gratuita" e un voucher "10% di sconto", potresti dare a "Spedizione gratuita" una priorità più alta per assicurarti che venga applicato per primo, quindi lo sconto percentuale.
-   **Stato:**

    -   **Cosa fa questa impostazione:** Attiva o disattiva la regola del voucher.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I voucher importati sotto questa regola possono essere utilizzati dai clienti.
        -   *Quando disabilitato:* I voucher non possono essere utilizzati, anche se validi.
    -   **Valore consigliato:** "SÌ" per rendere i voucher immediatamente utilizzabili. Puoi disabilitarlo in seguito se necessario.
    -   **Scenario / esempio del commerciante:** Vuoi preparare i voucher in anticipo ma attivarli solo il giorno del lancio di una campagna. Imposteresti "NO" inizialmente e poi cambieresti in "SÌ" quando pronto.

#### **Passaggio 4: Impostazioni voucher (Condizioni)**

Questa sezione definisce le condizioni in base alle quali i voucher importati possono essere utilizzati.

-   **Importo minimo:**

    -   **Cosa fa questa impostazione:** Specifica il totale minimo dell'ordine (prima della spedizione e delle tasse) richiesto affinché il voucher sia valido.
    -   **Effetto della modifica di questa impostazione:** I clienti devono soddisfare questo valore minimo di acquisto per applicare lo sconto.
    -   **Valore consigliato:** "0" se non è richiesto un minimo, o un importo specifico (es. "50.00").
    -   **Scenario / esempio del commerciante:** "Ottieni $10 di sconto su ordini superiori a $100." Imposteresti "100.00".
-   **Valuta:**

    -   **Cosa fa questa impostazione:** Seleziona la valuta per l'importo minimo.
    -   **Effetto della modifica di questa impostazione:** Assicura che l'importo minimo sia interpretato correttamente per i negozi multi-valuta.
    -   **Valore consigliato:** La valuta predefinita del tuo negozio (es. "USD", "EUR").
    -   **Scenario / esempio del commerciante:** Se il tuo negozio opera in più valute, assicurati che questa corrisponda alla valuta che ti aspetti che i clienti utilizzino per questo voucher.
-   **Cumulativo con altri voucher:**

    -   **Cosa fa questa impostazione:** Determina se questo voucher può essere combinato con altri voucher attivi nello stesso ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono utilizzare questo voucher insieme ad altri voucher validi.
        -   *Quando disabilitato:* Questo voucher non può essere utilizzato se un altro voucher è già applicato al carrello.
    -   **Valore consigliato:** "NO" per la maggior parte dei codici unici per prevenire sconti eccessivi. "SÌ" per promozioni specifiche come "spedizione gratuita" che vuoi combinare.
    -   **Scenario / esempio del commerciante:** Stai importando codici "10% di sconto". Probabilmente vuoi "NO" per impedire ai clienti di accumulare più sconti percentuali.
-   **Data di scadenza (Da):**

    -   **Cosa fa questa impostazione:** Imposta la data di inizio da cui i voucher importati diventano validi.
    -   **Effetto della modifica di questa impostazione:** I voucher non possono essere utilizzati prima di questa data.
    -   **Valore consigliato:** La data odierna o una data futura per promozioni programmate.
    -   **Scenario / esempio del commerciante:** Vuoi che i voucher siano attivi a partire dal prossimo lunedì. Selezioneresti la data del prossimo lunedì.
-   **Data di scadenza (A):**

    -   **Cosa fa questa impostazione:** Imposta la data di fine dopo la quale i voucher importati non sono più validi.
    -   **Effetto della modifica di questa impostazione:** I voucher non possono essere utilizzati dopo questa data.
    -   **Valore consigliato:** Una data futura corrispondente alla fine della tua promozione.
    -   **Scenario / esempio del commerciante:** La tua campagna termina il 31 dicembre. Selezioneresti il 31 dicembre.
-   **Quantità:**

    -   **Cosa fa questa impostazione:** Definisce il numero totale di volte in cui *ogni singolo codice voucher* può essere utilizzato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostato su 1:* Ogni codice nel tuo CSV può essere utilizzato solo una volta (il più comune per codici unici).
        -   *Impostato su >1:* Ogni codice può essere utilizzato più volte fino a questo limite.
    -   **Valore consigliato:** "1" per codici unici e monouso (es. da Groupon).
    -   **Scenario / esempio del commerciante:** Per 1000 codici Groupon unici, imposteresti questo valore su "1" in modo che ogni cliente possa utilizzare il proprio codice specifico solo una volta.
-   **Quantità per utente:**

    -   **Cosa fa questa impostazione:** Definisce quante volte *un singolo cliente* può utilizzare *qualsiasi* voucher da questo lotto importato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostato su 1:* Un cliente può utilizzare un solo voucher da questo lotto, anche se ha più codici unici.
        -   *Impostato su >1:* Un cliente può utilizzare più voucher da questo lotto, fino a questo limite.
    -   **Valore consigliato:** "1" per la maggior parte delle campagne con codici unici per impedire a un singolo cliente di utilizzare molti codici.
    -   **Scenario / esempio del commerciante:** Vuoi che ogni cliente benefici di un solo voucher "di benvenuto". Imposteresti questo valore su "1".

#### **Passaggio 5: Impostazioni voucher (Azioni)**

Questa sezione definisce il tipo di sconto che i voucher importati forniranno.

-   **Spedizione gratuita:**

    -   **Cosa fa questa impostazione:** Se abilitato, il voucher garantirà la spedizione gratuita per l'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I costi di spedizione vengono annullati quando il voucher viene applicato.
        -   *Quando disabilitato:* I costi di spedizione vengono calcolati normalmente.
    -   **Valore consigliato:** "NO" a meno che lo scopo principale di questi voucher non sia la spedizione gratuita.
    -   **Scenario / esempio del commerciante:** Stai importando codici per una promozione "Weekend di spedizione gratuita". Abiliteresti "SÌ".
-   **Applica uno sconto:**

    -   **Cosa fa questa impostazione:** Determina il tipo e il valore dello sconto applicato dal voucher.
    -   **Effetto della modifica di questa impostazione:** Questo è il meccanismo di sconto principale.
    -   **Valore consigliato:** Scegli una delle opzioni seguenti in base alla tua promozione.
    -   **Scenario / esempio del commerciante:** Vuoi dare il 10% di sconto.
    -   **Percentuale:**

        -   **Cosa fa questa impostazione:** Applica uno sconto percentuale all'ordine.
        -   **Effetto della modifica di questa impostazione:** Il campo `Valore` verrà interpretato come una percentuale (es. `10` per il 10%).
        -   **Valore consigliato:** Seleziona questa opzione per sconti basati su percentuale.
        -   **Scenario / esempio del commerciante:** Per una promozione "15% di sconto", seleziona "Percentuale" e inserisci `15` nel campo `Valore`.
    -   **Importo:**

        -   **Cosa fa questa impostazione:** Applica uno sconto monetario fisso all'ordine.
        -   **Effetto della modifica di questa impostazione:** Il campo `Valore` verrà interpretato come un importo fisso nella valuta scelta (es. `10.00` per $10 di sconto).
        -   **Valore consigliato:** Seleziona questa opzione per sconti a importo fisso.
        -   **Scenario / esempio del commerciante:** Per una promozione "$20 di sconto", seleziona "Importo" e inserisci `20.00` nel campo `Valore`.
    -   **Nessuno:**

        -   **Cosa fa questa impostazione:** Se selezionato, il voucher non applicherà alcuno sconto monetario o percentuale. Questo viene tipicamente utilizzato quando l'unica azione del voucher è "Spedizione gratuita" o "Invia un regalo".
        -   **Effetto della modifica di questa impostazione:** Non viene applicato alcun valore di sconto.
        -   **Valore consigliato:** Seleziona "Nessuno" solo se stai utilizzando "Spedizione gratuita" o "Invia un regalo" come azione principale.
        -   **Scenario / esempio del commerciante:** Se vuoi offrire solo la spedizione gratuita, selezioneresti "Nessuno" qui e abiliteresti "Spedizione gratuita" sopra.
-   **Valore:**

    -   **Cosa fa questa impostazione:** Il valore numerico effettivo dello sconto. La sua interpretazione dipende dal fatto che sia selezionato "Percentuale" o "Importo" sopra.
    -   **Effetto della modifica di questa impostazione:** Controlla direttamente l'entità dello sconto.
    -   **Valore consigliato:** Un valore numerico (es. `10` per il 10% o $10).
    -   **Scenario / esempio del commerciante:** Se hai scelto "Percentuale" e vuoi il 15% di sconto, inserisci `15`. Se hai scelto "Importo" e vuoi $20 di sconto, inserisci `20.00`.
-   **Applica sconto a:**

    -   **Cosa fa questa impostazione:** Determina a cosa viene applicato lo sconto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Ordine (senza spedizione):* Lo sconto si applica al valore totale del prodotto nel carrello.
        -   *Prodotto specifico:* Lo sconto si applica solo a un prodotto particolare che specifichi.
        -   *Prodotto più economico:* Lo sconto si applica al prodotto con il prezzo più basso nel carrello.
        -   *Prodotti selezionati:* Lo sconto si applica a una selezione di prodotti.
    -   **Valore consigliato:** "Ordine (senza spedizione)" per sconti generali.
    -   **Scenario / esempio del commerciante:** Per una campagna generale "10% di sconto su tutto", scegli "Ordine (senza spedizione)". Se è "10% di sconto su tutte le magliette", selezioneresti "Prodotti selezionati" e poi sceglieresti la tua categoria/prodotti di magliette.
-   **Invia un regalo:**

    -   **Cosa fa questa impostazione:** Se abilitato, il voucher aggiungerà un prodotto specifico al carrello del cliente come regalo gratuito.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Ti verrà chiesto di selezionare un prodotto da aggiungere come regalo.
        -   *Quando disabilitato:* Nessun regalo viene aggiunto.
    -   **Valore consigliato:** "NO" a meno che tu non stia eseguendo una promozione del tipo "compra X e ottieni Y gratis".
    -   **Scenario / esempio del commerciante:** "Acquista qualsiasi prodotto, ottieni un portachiavi gratuito." Abiliteresti "SÌ" e selezioneresti il prodotto portachiavi.

Dopo aver configurato tutte le impostazioni, troverai tipicamente un pulsante "Salva" o "Importa". Clicca su questo per avviare il processo di importazione. Il modulo leggerà quindi il tuo file CSV e creerà le regole voucher corrispondenti nel tuo database PrestaShop in base alle impostazioni che hai definito.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Carica file CSV | Il tuo CSV preparato | Seleziona il file contenente i codici voucher. |
| | Separatore CSV | Virgola (`,`) | Carattere che separa le colonne nel tuo CSV. Deve corrispondere al tuo file. |
| | Delimitatore di testo | Doppio apice (`"`) | Carattere che racchiude i campi di testo nel tuo CSV. Deve corrispondere al tuo file. |
| | Salta la prima riga (intestazione) | SÌ (se l'intestazione esiste) | Ignora la prima riga del tuo CSV se è un'intestazione. |
| | **Impostazioni voucher (Generali)** | | |
| | Nome | Nome descrittivo | Nome interno per la regola del voucher nel BO. |
| | Descrizione | Testo opzionale | Descrizione interna per la regola del voucher. |
| | Evidenzia | NO | Evidenzia il voucher nel riepilogo del carrello. |
| | Uso parziale | NO | Consente l'uso parziale del valore del voucher. SÌ per buoni regalo. |
| | Priorità | 1 | Ordine di applicazione per più voucher. |
| | Stato | SÌ | Attiva/disattiva la regola del voucher. |
| | **Impostazioni voucher (Condizioni)** | | |
| | Importo minimo | 0 | Importo minimo dell'ordine per la validità del voucher. |
| | Valuta | Predefinita del negozio | Valuta per l'importo minimo. |
| | Cumulativo con altri voucher | NO | Consente la combinazione con altri voucher. |
| | Data di scadenza (Da) | Data odierna | Data di inizio validità del voucher. |
| | Data di scadenza (A) | Data futura | Data di fine validità del voucher. |
| | Quantità | 1 | Usi totali per *singolo* codice voucher. |
| | Quantità per utente | 1 | Usi totali per *cliente* da questo lotto. |
| | **Impostazioni voucher (Azioni)** | | |
| | Spedizione gratuita | NO | Concede la spedizione gratuita. |
| | Applica uno sconto | Percentuale / Importo | Tipo di sconto (percentuale o importo fisso). |
| | Valore | Valore numerico | Il valore effettivo dello sconto (es. 10 per 10% o $10). |
| | Applica sconto a | Ordine (senza spedizione) | A cosa si applica lo sconto (ordine, prodotto specifico, ecc.). |
| | Invia un regalo | NO | Aggiunge un prodotto gratuito come regalo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho importato il mio CSV, ma i voucher non funzionano o non vengono visualizzati.**
R:

1.  **Controlla lo stato del modulo:** Assicurati che il modulo stesso sia abilitato in **Moduli > Gestione moduli**.
2.  **Controlla lo stato del voucher:** Vai su **Catalogo > Sconti > Regole carrello** (o **Regole prezzo > Regole carrello** nelle versioni precedenti). Trova la regola del voucher creata dall'importazione (avrà il "Nome" specificato durante la configurazione). Assicurati che il suo "Stato" sia impostato su "SÌ" (attivo).
3.  **Date di scadenza:** Ricontrolla le impostazioni "Data di scadenza (Da)" e "Data di scadenza (A)". Se la data corrente è al di fuori di questo intervallo, i voucher non funzioneranno.
4.  **Importo minimo:** Verifica se il carrello del cliente soddisfa la condizione di "Importo minimo" che hai impostato.
5.  **Codici voucher:** Assicurati che i codici nel tuo CSV siano esattamente come i clienti li stanno inserendo (sensibili alle maiuscole/minuscole, senza spazi extra).

**D: Il mio file CSV non viene analizzato correttamente. Tutti i dati sono in una colonna, o le colonne sono mescolate.**
R: Questo è quasi sempre dovuto a impostazioni errate di "Separatore CSV" o "Delimitatore di testo".

1.  **Apri il tuo file CSV** in un editor di testo semplice (come Blocco note, Sublime Text, VS Code, o anche Excel/Fogli Google ma poi salvalo di nuovo come CSV).
2.  **Identifica il separatore:** Guarda come i valori sono separati. È una virgola (`,`), un punto e virgola (`;`), o un tab? Seleziona quello corretto nelle impostazioni del modulo.
3.  **Identifica il delimitatore:** Cerca i caratteri che racchiudono il testo, di solito i doppi apici (`"`). Se presenti, assicurati che "Delimitatore di testo" sia impostato su "Doppio apice".
4.  **Riga di intestazione:** Se il tuo CSV ha un'intestazione, assicurati che "Salta la prima riga (intestazione)" sia impostato su "SÌ".

**D: Ho importato i voucher, ma ora voglio eliminarli o disabilitarli.**
R:

1.  Vai su **Catalogo > Sconti > Regole carrello** (o **Regole prezzo > Regole carrello**).
2.  Trova la regola del voucher che hai creato con il modulo (usando il "Nome" che hai assegnato).
3.  Puoi:
    -   **Disabilitare:** Clicca sul segno di spunta verde accanto alla regola per trasformarlo in una "X" rossa. Questo disattiva tutti i voucher sotto quella regola.
    -   **Eliminare:** Seleziona la regola e usa le azioni in blocco o clicca sull'icona di eliminazione per rimuovere l'intera regola e tutti i codici voucher associati.

L'eliminazione di una regola del carrello è permanente e non può essere annullata.

**D: Posso aggiornare i voucher esistenti con questo modulo?**
R: No, questo modulo è progettato per importare *nuovi* voucher. Non ha funzionalità per aggiornare codici voucher o regole del carrello esistenti. Se devi modificare un voucher esistente, devi farlo manualmente tramite **Catalogo > Sconti > Regole carrello**.

**D: Perché i miei voucher importati non sono cumulativi con altri sconti?**
R: Controlla l'impostazione "Cumulativo con altri voucher" nella configurazione del modulo. Se l'hai impostata su "NO" (il che è spesso consigliato per codici unici), i clienti non potranno utilizzare questi voucher insieme ad altri sconti attivi nel loro carrello. Se vuoi che siano cumulativi, impostalo su "SÌ" durante l'importazione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Importa voucher da CSV".

### 4.1 Panoramica dell'architettura

Il modulo `importvoucher` è un modulo PrestaShop standard focalizzato principalmente sulla funzionalità del Back Office. Sfrutta gli ObjectModels `CartRule` e `CartRuleProduct` di PrestaShop per creare e gestire i codici sconto. La logica principale del modulo risiede nel suo file PHP primario, gestendo i caricamenti di file, l'analisi CSV e le interazioni con il database. Non introduce modelli MVC complessi con controller front o admin dedicati, ma utilizza il metodo `getContent()` per la sua interfaccia di configurazione.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office dedicati nelle directory `controllers/front` o `controllers/admin`. Tutta la logica amministrativa, inclusa la maschera di configurazione e il processo di importazione CSV, è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce classi personalizzate in una directory `classes/`. Interagisce direttamente con gli ObjectModels `CartRule` e `CartRuleProduct` di PrestaShop per creare e gestire i codici sconto.

-   **`CartRule` (Classe Core di PrestaShop):**

    -   Interagisce con la tabella del database `ps_cart_rule`.
    -   Il modulo popola le proprietà degli oggetti `CartRule` (es. `name`, `description`, `code`, `quantity`, `quantity_per_user`, `date_from`, `date_to`, `minimum_amount`, `reduction_percent`, `reduction_amount`, `free_shipping`, `active`, `highlight`, `partial_use`, `priority`, `cumulative_with_other_rules`) in base alla configurazione e ai dati CSV.
    -   Il metodo `add()` di `CartRule` viene utilizzato per rendere persistenti le nuove regole del voucher nel database.
-   **`CartRuleProduct` (Classe Core di PrestaShop):**

    -   Interagisce con le tabelle `ps_cart_rule_product_rule_group` e `ps_cart_rule_product_rule`.
    -   Utilizzato quando viene scelta l'opzione "Applica sconto a: Prodotti selezionati", per collegare la regola del carrello a prodotti, categorie o produttori specifici.

### 4.4 Risorse JavaScript (`views/js/`)

-   `importvoucher/lib/voucherengine/script.js`:
    -   **Ambito:** Back-office.
    -   **Scopo:** Questo script probabilmente gestisce le interazioni dinamiche nella pagina di configurazione del modulo. Ciò potrebbe includere:
        -   Mostrare/nascondere campi in base alle opzioni selezionate (es. mostrare l'input "Valore" solo quando è selezionato il tipo di sconto "Percentuale" o "Importo").
        -   Chiamate AJAX per la convalida o l'elaborazione del modulo.
        -   Inizializzazione del selettore di data per "Data di scadenza (Da)" e "Data di scadenza (A)".
        -   Potenzialmente anteprime di analisi CSV lato client o gestione degli errori.
    -   **Interazione:** Collega i listener di eventi agli elementi del modulo (es. eventi `change` sui pulsanti radio, `click` sui pulsanti).

### 4.5 Fogli di stile CSS (`views/css/`)

-   `importvoucher/lib/voucherengine/ps16.css`:

    -   **Ambito:** Back-office (probabilmente per la compatibilità con PrestaShop 1.6, ma potrebbe essere caricato su versioni più recenti per lo stile generale).
    -   **Scopo:** Fornisce lo stile per l'interfaccia di configurazione del modulo, assicurando che si integri visivamente con il tema del Back Office di PrestaShop 1.6. Può contenere stili generali per gli elementi del modulo, regolazioni del layout e stili specifici basati su classi per i componenti del modulo.
    -   **Selettori chiave:** Probabilmente si rivolge a elementi generici del modulo (`.form-group`, `.control-label`, `.form-control`) e potenzialmente a wrapper specifici del modulo (es. `#module_form_importvoucher`).
-   `importvoucher/views/css/css.css`:

    -   **Ambito:** Back-office.
    -   **Scopo:** Contiene regole di stile generali o specifiche per la pagina di configurazione del modulo. Questo potrebbe sovrascrivere o estendere `ps16.css` per le versioni più recenti di PrestaShop o fornire uno stile unico per elementi personalizzati all'interno del template del modulo.
    -   **Selettori chiave:** Simili a `ps16.css`, focalizzati sugli elementi dell'interfaccia utente del modulo. Gli sviluppatori dovrebbero ispezionare questo file per nomi di classi specifici da sovrascrivere nei loro temi admin personalizzati, se necessario.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per il rendering della sua interfaccia di configurazione del Back Office.

-   **`importvoucher/views/backoffice.tpl`**:

    -   **Ambito:** Template admin.
    -   **Scopo:** Questo è probabilmente il file di template principale renderizzato dal metodo `getContent()`. Agisce come contenitore per l'intera maschera di configurazione del modulo, inclusi tutte le impostazioni, i campi di input e i pulsanti. Probabilmente include altri template parziali.
    -   **Contenuto:** Contiene la struttura HTML per la pagina di configurazione del modulo, inclusi tag di form, fieldset e potenzialmente chiamate per includere altri file `.tpl`.
-   **`importvoucher/views/csv.tpl`**:

    -   **Ambito:** Template admin.
    -   **Scopo:** Questo template probabilmente gestisce la visualizzazione della sezione di caricamento del file CSV e le impostazioni correlate (separatore, delimitatore, salta intestazione). È un template parziale incluso in `backoffice.tpl`.
-   **`importvoucher/views/csv_file.tpl`**:

    -   **Ambito:** Template admin.
    -   **Scopo:** Un template parziale più granulare, possibilmente specifico per il campo di input del file stesso, o per la visualizzazione di informazioni sul file CSV caricato.
-   **`importvoucher/views/file_settings.tpl`**:

    -   **Ambito:** Template admin.
    -   **Scopo:** Questo template probabilmente renderizza la sezione "Impostazioni file CSV", inclusi gli input per il separatore CSV, il delimitatore di testo e la casella di controllo "salta la prima riga".

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database:**
    Il modulo non crea tabelle di database personalizzate. Interagisce direttamente con le tabelle core di PrestaShop relative alle regole del carrello:

    -   `ps_cart_rule`: Memorizza le proprietà principali di ogni regola di sconto (nome, codice, date, importo minimo, ecc.).
    -   `ps_cart_rule_lang`: Memorizza i campi specifici della lingua per le regole del carrello (es. `name` se è multilingue).
    -   `ps_cart_rule_product_rule_group`: Utilizzato quando si applicano sconti a prodotti/categorie specifici.
    -   `ps_cart_rule_product_rule`: Definisce le regole di prodotto effettive all'interno di un gruppo.
    -   `ps_cart_rule_product_rule_exclusion`: Per escludere prodotti specifici da una regola.
    -   `ps_cart_rule_carrier`: Per le restrizioni del corriere.
    -   `ps_cart_rule_country`: Per le restrizioni del paese.
    -   `ps_cart_rule_group`: Per le restrizioni del gruppo di clienti.
    -   `ps_cart_rule_shop`: Per il contesto multi-negozio.
-   **Tabella degli hook registrati:**
    La funzione principale del modulo è nella configurazione del Back Office. Sebbene la descrizione del modulo menzioni "Hook Front-Office: Header, Colonne, Prodotto o Footer", l'inventario dei file fornito e la funzionalità tipica di un modulo di importazione suggeriscono che non renderizza attivamente contenuti in questi hook del front-office. Queste menzioni potrebbero essere generiche o riferirsi a dove si vedono gli *effetti* dei voucher importati (es. un voucher applicato nel carrello, che fa parte del flusso di checkout, potenzialmente influenzato dagli hook).

    Il modulo utilizza principalmente il seguente hook per la sua interfaccia del Back Office:

    | Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Renderizza nella sezione `<head>` delle pagine del Back Office. | Utilizzato per includere risorse CSS e JavaScript per la pagina di configurazione del modulo. |
    | `moduleRoutes` (PrestaShop 1.7+) | Quando le route del modulo vengono inizializzate. | Se il modulo avesse controller front personalizzati, questo hook definirebbe i loro URL. (Non applicabile qui in quanto non sono presenti controller front personalizzati). |

    La logica principale del modulo per *creare* i voucher non si basa su hook specifici di PrestaShop, ma piuttosto su chiamate dirette ai metodi `CartRule` attivate dall'invio del modulo in `getContent()`.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Importa voucher da CSV", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
