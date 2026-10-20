---
title: "Prestashop Popup Pro - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Popup Pro di MyPresta.eu."
sidebar:
  label: "Prestashop Popup Pro - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Prestashop Popup Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/prestashop-popup-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/prestashop-popup-pro/)
>
> ---


# Prestashop Popup Pro

## 1. Requisiti e compatibilità

Per garantire che il modulo Prestashop Popup Pro funzioni senza problemi sul tuo negozio, controlla i seguenti requisiti:

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il funzionamento generale di PrestaShop e dovrebbero essere disponibili su qualsiasi ambiente di hosting moderno. Non sono necessarie estensioni speciali o insolite per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

La pagina di configurazione principale per Prestashop Popup Pro è dove definisci tutto ciò che riguarda il tuo popup: il suo contenuto, l'aspetto e il comportamento.

**Scheda Impostazioni Generali**

- **Abilita Popup Pro:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo inizierà a visualizzare i popup in base alle altre impostazioni.
    - *Quando disabilitato:* Nessun popup apparirà sul tuo negozio, indipendentemente dalle altre configurazioni.
  - **Valore consigliato:** SÌ (quando vuoi usare i popup).
  - **Scenario / esempio del commerciante:** Stai eseguendo una campagna e vuoi attivare il tuo popup. Lo abiliti. Dopo la campagna, lo disabiliti senza perdere le tue impostazioni.
- **Contenuto Popup (Editor HTML):**

  - **Cosa fa questa impostazione:** Questo è il cuore del tuo popup. È un potente editor HTML dove progetti ciò che appare all'interno della finestra popup. Puoi aggiungere testo, immagini, link, video e persino incorporare moduli (ad esempio, iscrizione alla newsletter).
  - **Effetto della modifica di questa impostazione:** Qualsiasi modifica qui aggiorna direttamente il contenuto visivo visualizzato ai tuoi clienti nel popup.
  - **Valore consigliato:** Il tuo messaggio promozionale desiderato, immagine o invito all'azione.
  - **Scenario / esempio del commerciante:** Vuoi annunciare uno sconto del 15%. Digiteresti "Ottieni il 15% di sconto sul tuo primo ordine! Usa il codice: SAVE15" e magari aggiungeresti un'immagine di prodotti popolari.
- **Larghezza Popup (px):**

  - **Cosa fa questa impostazione:** Definisce la larghezza della tua finestra popup in pixel.
  - **Effetto della modifica di questa impostazione:**
    - *Aumentando il valore:* Rende il popup più largo.
    - *Diminuendo il valore:* Rende il popup più stretto.
  - **Valore consigliato:** Inizia con `600px` a `800px` per desktop, quindi regola in base al tuo contenuto e design.
  - **Scenario / esempio del commerciante:** Hai una grande immagine banner nel tuo popup. Potresti impostare la larghezza a `800px` per assicurarti che l'immagine venga visualizzata correttamente. Per un semplice messaggio di testo, `400px` potrebbe essere sufficiente.
- **Altezza Popup (px):**

  - **Cosa fa questa impostazione:** Definisce l'altezza della tua finestra popup in pixel.
  - **Effetto della modifica di questa impostazione:**
    - *Aumentando il valore:* Rende il popup più alto.
    - *Diminuendo il valore:* Rende il popup più corto.
  - **Valore consigliato:** `auto` (lascia vuoto) o un valore specifico in pixel se il tuo contenuto ha un'altezza fissa.
  - **Scenario / esempio del commerciante:** Se il contenuto del tuo popup è dinamico o breve, lasciandolo vuoto (`auto`) consente al popup di regolare la sua altezza per adattarsi al contenuto. Se hai un video che richiede un rapporto di aspetto specifico, potresti impostare un'altezza fissa.
- **Visualizza Popup Su:**

  - **Cosa fa questa impostazione:** Determina *quando* appare il popup.
  - **Effetto della modifica di questa impostazione:**
    - *Caricamento Pagina:* Il popup appare dopo il caricamento della pagina.
    - *Intento di Uscita:* Il popup appare quando il mouse dell'utente si sposta fuori dalla finestra del browser (indicando che potrebbe lasciare il sito).
    - *Scorrimento:* Il popup appare dopo che l'utente ha scorre una certa percentuale della pagina.
    - *Ritardo Temporale:* Il popup appare dopo un numero specificato di secondi.
  - **Valore consigliato:** Dipende dal tuo obiettivo. "Intento di Uscita" è spesso efficace per catturare i visitatori che stanno abbandonando. "Caricamento Pagina" con un breve ritardo (es. 3-5 secondi) è buono per annunci generali.
  - **Scenario / esempio del commerciante:** Per ridurre l'abbandono del carrello, sceglieresti "Intento di Uscita" e offrirai un codice sconto. Per annunciare una nuova linea di prodotti, potresti usare "Caricamento Pagina" con un ritardo di 3 secondi.
- **Ritardo prima della comparsa del popup (secondi):**

  - **Cosa fa questa impostazione:** Se "Visualizza Popup Su" è impostato su "Caricamento Pagina" o "Ritardo Temporale", questo specifica quanti secondi attendere prima che il popup venga visualizzato.
  - **Effetto della modifica di questa impostazione:** Un valore più alto significa che il popup appare più tardi, dando al cliente più tempo per navigare. Un valore più basso significa che appare prima.
  - **Valore consigliato:** Da `3` a `5` secondi. Troppo veloce può essere intrusivo, troppo lento potrebbe non raggiungere il cliente.
  - **Scenario / esempio del commerciante:** Vuoi dare ai clienti un momento per vedere la tua homepage prima di mostrare un'iscrizione alla newsletter. Imposti questo a `5` secondi.
- **Frequenza Popup (giorni):**

  - **Cosa fa questa impostazione:** Controlla la frequenza con cui un cliente *di ritorno* vede il popup. Una volta che un cliente chiude il popup, questa impostazione determina quanti giorni passano prima che lo riveda.
  - **Effetto della modifica di questa impostazione:**
    - *0:* Il popup appare ad ogni visita (può essere fastidioso).
    - *Valore più alto:* Il popup appare meno frequentemente per i visitatori di ritorno.
  - **Valore consigliato:** Da `7` a `30` giorni. Evita di infastidire i tuoi clienti fedeli.
  - **Scenario / esempio del commerciante:** Stai eseguendo una vendita che dura un mese. Imposti questo a `7` giorni in modo che i clienti vengano ricordati settimanalmente, ma non ad ogni singola visita.
- **Mostra Popup su Dispositivi Mobili:**

  - **Cosa fa questa impostazione:** Attiva o disattiva la visualizzazione del popup su smartphone e tablet.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il popup appare sui dispositivi mobili, adattandosi in modo responsivo.
    - *Disabilitato:* Il popup apparirà solo sui computer desktop.
  - **Valore consigliato:** SÌ, ma assicurati che il contenuto del tuo popup sia ottimizzato per i dispositivi mobili.
  - **Scenario / esempio del commerciante:** Hai un popup semplice, basato su testo, che si visualizza bene su mobile. Lo abiliti per raggiungere tutti i tuoi clienti. Se il tuo popup ha immagini o moduli complessi che si rompono su mobile, potresti disabilitarlo.
- **Colore Sfondo Popup:**

  - **Cosa fa questa impostazione:** Imposta il colore di sfondo della finestra popup stessa.
  - **Effetto della modifica di questa impostazione:** Cambia il colore visivo dietro il tuo contenuto.
  - **Valore consigliato:** Un colore che si abbina al tuo marchio e fa risaltare il tuo contenuto. Spesso bianco (`#FFFFFF`) o un colore neutro chiaro.
  - **Scenario / esempio del commerciante:** Il tuo marchio usa molto blu. Potresti scegliere uno sfondo azzurro per il popup per abbinarlo.
- **Colore Bordo Popup:**

  - **Cosa fa questa impostazione:** Imposta il colore del bordo attorno alla finestra popup.
  - **Effetto della modifica di questa impostazione:** Cambia il colore visivo del bordo del popup.
  - **Valore consigliato:** Spesso un colore tenue, o trasparente se preferisci nessun bordo.
  - **Scenario / esempio del commerciante:** Vuoi un aspetto pulito, quindi imposti questo su un grigio molto chiaro o trasparente.
- **Spessore Bordo Popup (px):**

  - **Cosa fa questa impostazione:** Imposta lo spessore del bordo attorno alla finestra popup.
  - **Effetto della modifica di questa impostazione:** Un valore più alto rende il bordo più spesso.
  - **Valore consigliato:** Da `0` a `2` pixel per un effetto sottile.
  - **Scenario / esempio del commerciante:** Vuoi un popup molto definito, quindi imposti un bordo di `2px`. Per un design minimalista, lo imposti a `0`.
- **Raggio Bordo Popup (px):**

  - **Cosa fa questa impostazione:** Controlla l'arrotondamento degli angoli del popup.
  - **Effetto della modifica di questa impostazione:**
    - *0:* Angoli netti, quadrati.
    - *Valore più alto:* Angoli più arrotondati.
  - **Valore consigliato:** Da `0` a `10` pixel per un aspetto moderno.
  - **Scenario / esempio del commerciante:** Vuoi che il tuo popup abbia bordi morbidi e moderni, quindi imposti questo a `8px`.
- **Colore Sfondo Overlay:**

  - **Cosa fa questa impostazione:** Imposta il colore dello strato semi-trasparente che appare *dietro* il popup, oscurando il resto del contenuto del tuo negozio.
  - **Effetto della modifica di questa impostazione:** Cambia il colore dell'overlay. Spesso un colore scuro con trasparenza.
  - **Valore consigliato:** Nero (`#000000`) con una certa trasparenza (ad esempio, `rgba(0,0,0,0.7)` se puoi inserire RGBA).
  - **Scenario / esempio del commerciante:** Vuoi che il popup sia l'assoluto focus, quindi scegli un overlay scuro, quasi opaco.
- **Opacità Overlay (0-100):**

  - **Cosa fa questa impostazione:** Controlla quanto è trasparente o opaco lo sfondo dell'overlay. `0` è completamente trasparente (invisibile), `100` è completamente opaco (colore solido).
  - **Effetto della modifica di questa impostazione:**
    - *Valore più alto:* Più opaco, sfondo più scuro, maggiore attenzione al popup.
    - *Valore più basso:* Più trasparente, sfondo più chiaro, più contenuto del tuo negozio visibile.
  - **Valore consigliato:** Da `50` a `80`.
  - **Scenario / esempio del commerciante:** Vuoi attenuare leggermente lo sfondo ma consentire comunque ai clienti di vedere il tuo negozio dietro il popup. Imposti questo a `60`.
- **Mostra Pulsante Chiudi:**

  - **Cosa fa questa impostazione:** Attiva o disattiva la visibilità del pulsante di chiusura "X" standard sul popup.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Appare un pulsante di chiusura, consentendo ai clienti di chiudere facilmente il popup.
    - *Disabilitato:* Nessun pulsante "X". I clienti dovranno cliccare al di fuori del popup o premere ESC (se abilitato) per chiuderlo.
  - **Valore consigliato:** SÌ, per una buona esperienza utente.
  - **Scenario / esempio del commerciante:** Vuoi rendere facile per i clienti chiudere il popup, quindi abiliti il pulsante di chiusura.
- **Consenti chiusura cliccando all'esterno:**

  - **Cosa fa questa impostazione:** Determina se cliccando in qualsiasi punto dell'overlay (al di fuori del contenuto del popup) si chiuderà il popup.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Cliccando sull'overlay si chiude il popup.
    - *Disabilitato:* Solo il pulsante di chiusura o il tasto ESC chiuderanno il popup.
  - **Valore consigliato:** SÌ, per una buona esperienza utente.
  - **Scenario / esempio del commerciante:** Vuoi fornire più modi per i clienti di chiudere il popup, quindi abiliti questa opzione.
- **Consenti chiusura con tasto ESC:**

  - **Cosa fa questa impostazione:** Determina se premendo il tasto ESC sulla tastiera si chiuderà il popup.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il tasto ESC chiude il popup.
    - *Disabilitato:* Il tasto ESC non ha alcun effetto sul popup.
  - **Valore consigliato:** SÌ, per una buona esperienza utente.
  - **Scenario / esempio del commerciante:** Vuoi fornire un modo accessibile per i clienti di chiudere il popup, quindi abiliti questa opzione.
- **CSS Personalizzato:**

  - **Cosa fa questa impostazione:** Ti permette di aggiungere le tue regole CSS personalizzate per stilizzare ulteriormente il popup o il suo contenuto. Questo è per utenti avanzati o sviluppatori.
  - **Effetto della modifica di questa impostazione:** Qualsiasi regola CSS valida che aggiungi qui verrà applicata al popup, potenzialmente sovrascrivendo gli stili predefiniti.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia esigenze di stile specifiche.
  - **Scenario / esempio del commerciante:** Vuoi cambiare la dimensione del carattere di un paragrafo specifico all'interno del tuo popup, o aggiungere un effetto ombra unico non disponibile in altre impostazioni. Aggiungeresti il CSS qui.

**Scheda Impostazioni Avanzate (o raggruppamento simile se disponibile)**

- **Animazione Popup (Effetto di ingresso):**

  - **Cosa fa questa impostazione:** Seleziona un effetto di animazione per quando il popup appare sullo schermo.
  - **Effetto della modifica di questa impostazione:** Il popup si animerà in vista utilizzando l'effetto scelto (ad esempio, dissolvenza in entrata, scorrimento verso il basso, zoom).
  - **Valore consigliato:** "Dissolvenza in entrata" o "Scorrimento verso il basso" sono generalmente sottili e professionali.
  - **Scenario / esempio del commerciante:** Vuoi che il tuo popup appaia in modo fluido piuttosto che semplicemente spuntare istantaneamente, quindi scegli "Dissolvenza in entrata".
- **Animazione Popup (Effetto di uscita):**

  - **Cosa fa questa impostazione:** Seleziona un effetto di animazione per quando il popup scompare dallo schermo.
  - **Effetto della modifica di questa impostazione:** Il popup si animerà fuori dalla vista utilizzando l'effetto scelto.
  - **Valore consigliato:** "Dissolvenza in uscita" o "Scorrimento verso l'alto" per abbinare l'effetto di ingresso.
  - **Scenario / esempio del commerciante:** Per mantenere un'esperienza utente coerente e fluida, scegli "Dissolvenza in uscita" come animazione di uscita.
- **Visualizza Popup su Pagine Specifiche (URL):**

  - **Cosa fa questa impostazione:** Ti permette di specificare URL esatti o pattern di URL dove il popup dovrebbe (o non dovrebbe) apparire.
  - **Effetto della modifica di questa impostazione:** Il popup verrà mostrato solo sulle pagine che corrispondono ai tuoi criteri, o sarà nascosto da esse.
  - **Valore consigliato:** Usalo per indirizzare i tuoi popup in modo efficace.
  - **Scenario / esempio del commerciante:** Hai un'offerta speciale per una specifica categoria di prodotti. Inseriresti l'URL di quella pagina di categoria qui per assicurarti che il popup appaia solo per i visitatori pertinenti.
- **Non visualizzare Popup su Pagine Specifiche (URL):**

  - **Cosa fa questa impostazione:** Ti permette di specificare URL esatti o pattern di URL dove il popup *non* dovrebbe apparire.
  - **Effetto della modifica di questa impostazione:** Il popup sarà nascosto dalle pagine che corrispondono ai tuoi criteri.
  - **Valore consigliato:** Usalo per evitare di mostrare popup su pagine sensibili come il checkout o il login.
  - **Scenario / esempio del commerciante:** Non vuoi che il popup interrompa il processo di checkout. Aggiungeresti l'URL della tua pagina di checkout (es. `/order`) qui.
- **Visualizza Popup per Gruppi di Clienti Specifici:**

  - **Cosa fa questa impostazione:** Limita la visibilità del popup a determinati gruppi di clienti (es. Visitatori, Clienti, Ospiti, Grossisti).
  - **Effetto della modifica di questa impostazione:** Solo i clienti appartenenti ai gruppi selezionati vedranno il popup.
  - **Valore consigliato:** Dipende dal tuo pubblico di riferimento. "Visitatori" e "Ospiti" sono comuni per la generazione di lead.
  - **Scenario / esempio del commerciante:** Hai un'offerta speciale esclusivamente per i tuoi clienti registrati. Selezioneresti "Clienti" qui.
- **Visualizza Popup per Lingue Specifiche:**

  - **Cosa fa questa impostazione:** Limita la visibilità del popup ai clienti che navigano in lingue specifiche.
  - **Effetto della modifica di questa impostazione:** Solo i clienti che utilizzano la lingua selezionata vedranno il popup.
  - **Valore consigliato:** Tutte le lingue, o quelle specifiche se il contenuto del tuo popup dipende dalla lingua.
  - **Scenario / esempio del commerciante:** Hai un popup con contenuto tradotto solo in inglese e francese. Selezioneresti "Inglese" e "Francese" qui.
- **Visualizza Popup per Valute Specifiche:**

  - **Cosa fa questa impostazione:** Limita la visibilità del popup ai clienti che navigano con valute specifiche.
  - **Effetto della modifica di questa impostazione:** Solo i clienti che utilizzano la valuta selezionata vedranno il popup.
  - **Valore consigliato:** Tutte le valute, o quelle specifiche se il contenuto del tuo popup dipende dalla valuta.
  - **Scenario / esempio del commerciante:** Hai un'offerta speciale valida solo per i clienti che pagano in USD. Selezioneresti "USD" qui.
- **Visualizza Popup per Paesi Specifici:**

  - **Cosa fa questa impostazione:** Limita la visibilità del popup ai clienti provenienti da paesi specifici.
  - **Effetto della modifica di questa impostazione:** Solo i clienti rilevati come provenienti dai paesi selezionati vedranno il popup.
  - **Valore consigliato:** Tutti i paesi, o quelli specifici per campagne geo-mirate.
  - **Scenario / esempio del commerciante:** Stai eseguendo una promozione esclusiva per i clienti in Francia. Selezioneresti "Francia" qui.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Abilita Popup Pro | SÌ | Interruttore principale per attivare/disattivare il popup. |
| | Contenuto Popup (Editor HTML) | (Vuoto) | Progetta ciò che appare all'interno del popup (testo, immagini, link). |
| | Larghezza Popup (px) | 600-800px | Imposta la dimensione orizzontale del popup. |
| | Altezza Popup (px) | auto (vuoto) | Imposta la dimensione verticale del popup, o si adatta automaticamente. |
| | Visualizza Popup Su | Intento di Uscita / Caricamento Pagina (ritardo 3-5s) | Determina il trigger per la comparsa del popup. |
| | Ritardo prima della comparsa del popup (secondi) | 3-5 | Ritardo temporale prima della visualizzazione del popup (se selezionato "Caricamento Pagina"). |
| | Frequenza Popup (giorni) | 7-30 | Quanto spesso un cliente di ritorno vede il popup. |
| | Mostra Popup su Dispositivi Mobili | SÌ | Controlla la visibilità del popup su telefoni/tablet. |
| | Colore Sfondo Popup | #FFFFFF (Bianco) | Colore dello sfondo della finestra popup. |
| | Colore Bordo Popup | Trasparente / Grigio Chiaro | Colore del bordo del popup. |
| | Spessore Bordo Popup (px) | 0-2 | Spessore del bordo del popup. |
| | Raggio Bordo Popup (px) | 0-10 | Arrotondamento degli angoli del popup. |
| | Colore Sfondo Overlay | #000000 (Nero) | Colore dello sfondo semi-trasparente dietro il popup. |
| | Opacità Overlay (0-100) | 50-80 | Livello di trasparenza dell'overlay. |
| | Mostra Pulsante Chiudi | SÌ | Visualizza il pulsante 'X' per chiudere il popup. |
| | Consenti chiusura cliccando all'esterno | SÌ | Consente la chiusura cliccando sull'overlay. |
| | Consenti chiusura con tasto ESC | SÌ | Consente la chiusura premendo il tasto ESC. |
| | CSS Personalizzato | (Vuoto) | Aggiungi CSS personalizzato per uno stile avanzato. |
| | Animazione Popup (Effetto di ingresso) | Dissolvenza in entrata / Scorrimento verso il basso | Effetto visivo quando il popup appare. |
| | Animazione Popup (Effetto di uscita) | Dissolvenza in uscita / Scorrimento verso l'alto | Effetto visivo quando il popup scompare. |
| | Visualizza Popup su Pagine Specifiche (URL) | (Vuoto) | Mostra popup solo su URL specificati. |
| | Non visualizzare Popup su Pagine Specifiche (URL) | (Vuoto) | Nascondi popup da URL specificati (es. checkout). |
| | Visualizza Popup per Gruppi di Clienti Specifici | Tutti | Indirizza il popup a tipi di clienti specifici. |
| | Visualizza Popup per Lingue Specifiche | Tutte | Indirizza il popup a lingue specifiche. |
| | Visualizza Popup per Valute Specifiche | Tutte | Indirizza il popup a valute specifiche. |
| | Visualizza Popup per Paesi Specifici | Tutti | Indirizza il popup a paesi specifici. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio popup non viene visualizzato affatto. Cosa devo controllare per prima cosa?**
**R1:**

1.  **Il modulo è abilitato?** Vai su **Moduli > Gestione moduli** e assicurati che "Prestashop Popup Pro" sia installato e abilitato.
2.  **"Abilita Popup Pro" è impostato su SÌ nella configurazione del modulo?** Questo è l'interruttore principale.
3.  **Controlla le tue impostazioni "Visualizza Popup Su":** Se è impostato su "Ritardo Temporale", assicurati che il ritardo non sia troppo lungo. Se "Intento di Uscita", assicurati di attivarlo correttamente (spostando il mouse fuori dalla finestra del browser).
4.  **Svuota la cache di PrestaShop:** Vai su **Parametri Avanzati > Prestazioni**, scorri verso il basso e clicca su "Svuota la cache". A volte i vecchi file di cache impediscono alle nuove impostazioni del modulo di avere effetto.
5.  **Verifica la presenza di conflitti:** Disabilita temporaneamente altri moduli popup o overlay per vedere se c'è un conflitto.

**D2: Il mio popup appare strano o rotto sui dispositivi mobili.**
**R2:**

1.  **"Mostra Popup su Dispositivi Mobili" è abilitato?** In caso contrario, non verrà visualizzato affatto.
2.  **Rivedi il tuo "Contenuto Popup":** HTML complesso, immagini molto grandi o contenuti non progettati per schermi piccoli possono causare problemi. Prova a semplificare il contenuto o a utilizzare immagini più piccole e ottimizzate.
3.  **Controlla "Larghezza Popup" e "Altezza Popup":** Sebbene il modulo sia responsivo, a volte i valori fissi in pixel possono causare problemi su schermi molto piccoli. Considera di lasciare "Altezza Popup" vuoto per `auto`.
4.  **CSS Personalizzato:** Se hai aggiunto CSS personalizzato, potrebbe non essere ottimizzato per i dispositivi mobili. Testa il tuo CSS utilizzando gli strumenti per sviluppatori del browser (ispeziona elemento) su diverse dimensioni dello schermo.

**D3: Il popup appare troppo spesso per i miei clienti. Come posso controllarlo?**
**R3:**

1.  **Regola "Frequenza Popup (giorni)":** Questa è l'impostazione chiave. Un numero più alto significa che i clienti vedranno il popup meno spesso. Ad esempio, impostandolo a `30` significa che lo vedranno solo una volta al mese dopo averlo chiuso.
2.  **Considera la tua impostazione "Visualizza Popup Su":** Se è "Caricamento Pagina" con un breve ritardo, potrebbe risultare più intrusivo rispetto a "Intento di Uscita".

**D4: Voglio tradurre il contenuto del mio popup in più lingue. Come faccio?**
**R4:** L'editor HTML "Contenuto Popup" dovrebbe supportare l'input multilingue di PrestaShop. Durante la modifica del contenuto, cerca le schede o i menu a discesa delle lingue (solitamente in alto a destra dell'editor) per passare da una lingua all'altra e fornire contenuti diversi per ciascuna. Assicurati di avere le lingue desiderate installate in PrestaShop. Se l'editor non mostra le schede delle lingue, potrebbe essere necessario inserire il contenuto per ogni lingua manualmente cambiando la lingua del tuo back office.

**D5: Il contenuto del popup è troppo piccolo/grande, o il carattere è sbagliato.**
**R5:**

1.  **Usa l'editor HTML:** L'editor HTML integrato di solito fornisce opzioni per modificare la dimensione del carattere, il colore e altri stili per il tuo testo.
2.  **CSS Personalizzato:** Per un controllo più preciso, usa il campo "CSS Personalizzato". Ad esempio, per cambiare la dimensione del carattere di tutto il testo nel popup, potresti aggiungere:

   ```
   .popuppro-content p { font-size: 16px !important;}
   ```

   (Potrebbe essere necessario ispezionare il popup nel tuo browser per trovare i selettori CSS corretti come `.popuppro-content`).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo Prestashop Popup Pro, destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo Prestashop Popup Pro segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale e `ModuleFrontController` per le interazioni AJAX. Si basa fortemente su JavaScript per la logica di visualizzazione del front-office, le animazioni e la gestione degli eventi (come l'intento di uscita). La configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo, memorizzando le impostazioni in `ps_configuration`. Il modulo integra un Smarty Templates Manager per una creazione flessibile dei contenuti e un selettore di colori per la personalizzazione dell'interfaccia utente.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `popuppro/controllers/front/index.php`
    - **Nome Classe:** `PopupproIndexModuleFrontController` (probabilmente, basato sulla convenzione di denominazione dei file)
    - **Classe Padre:** `ModuleFrontController`
    - **Responsabilità:** Questo controller potrebbe fungere da punto di ingresso generale o da fallback per le richieste del front-office relative al modulo. Potrebbe essere responsabile del caricamento iniziale dei dati o del rendering di una vista base del modulo se non viene richiesta alcuna azione specifica.
  - `popuppro/controllers/front/popuploader.php`
    - **Nome Classe:** `PopupproPopuploaderModuleFrontController`
    - **Classe Padre:** `ModuleFrontController`
    - **Responsabilità:** Questo controller è molto probabilmente responsabile del caricamento dinamico del contenuto e della configurazione del popup tramite AJAX. Quando un utente visita una pagina, uno script JavaScript invierebbe una richiesta AJAX a questo controller per recuperare l'HTML, lo stile e le impostazioni comportamentali del popup in base alla configurazione del modulo. Restituirebbe un payload JSON o HTML.
  - `popuppro/controllers/front/popupstat.php`
    - **Nome Classe:** `PopupproPopupstatModuleFrontController`
    - **Classe Padre:** `ModuleFrontController`
    - **Responsabilità:** Questo controller è progettato per gestire i dati statistici relativi al popup. Riceverebbe richieste AJAX dal JavaScript del front-office per registrare impressioni del popup, clic sul pulsante di chiusura o altre interazioni, consentendo al modulo di tracciare le prestazioni (sebbene una vista statistiche dedicata non sia esplicitamente elencata nei controller di amministrazione, questi dati potrebbero essere archiviati per uso futuro o per la registrazione interna).
- **Controller Admin Back-Office**: Nessuno esplicitamente elencato, indicando che tutta l'amministrazione è gestita tramite il metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Non sono elencate classi personalizzate o definizioni `ObjectModel` nella directory `classes/`. Ciò suggerisce che il modulo memorizza principalmente la sua configurazione direttamente nella tabella `ps_configuration` utilizzando `Configuration::updateValue()` e `Configuration::get()`, e non gestisce entità di dati personalizzate complesse che richiedono tabelle di database dedicate o mappatura `ObjectModel`.

### 4.4 Risorse JavaScript (`views/js/`)

- `popuppro/js/popup-engine.js`:
  - **Ambito:** Front-office.
  - **Dettaglio:** Questo è probabilmente il file JavaScript principale responsabile della meccanica fondamentale del popup. Gestirebbe la creazione degli elementi DOM del popup (l'overlay, il contenitore del popup, il pulsante di chiusura), l'iniezione del contenuto, la gestione delle animazioni (effetti di ingresso/uscita) e il posizionamento del popup sullo schermo. Probabilmente definisce l'oggetto principale `PopupPro` o simile.
- `popuppro/js/popup-events.js`:
  - **Ambito:** Front-office.
  - **Dettaglio:** Questo script gestirebbe tutti i listener di eventi che attivano il popup. Ciò include:
    - `DOMContentLoaded` o `window.load` per la configurazione iniziale.
    - `setTimeout` per i popup con ritardo temporale.
    - Listener di eventi di scorrimento per i popup attivati dallo scorrimento.
    - `mouseleave` o eventi simili su `document.body` per il rilevamento dell'intento di uscita.
    - Listener di clic per il pulsante di chiusura e la chiusura con clic esterno.
    - Listener `keyup` per il tasto ESC.
    - Chiamate AJAX a `popuploader.php` per recuperare il contenuto e a `popupstat.php` per registrare gli eventi.
- `popuppro/js/popup-scripts.js`:
  - **Ambito:** Front-office.
  - **Dettaglio:** Questo file potrebbe contenere script aggiuntivi, forse più specifici, relativi al comportamento o alle interazioni del popup, gestendo eventualmente l'invio di moduli all'interno del popup, aggiornamenti dinamici dei contenuti o l'integrazione con altri elementi del front-office.
- `popuppro/js/script.js`:
  - **Ambito:** Front-office/Back-office (nome generico, potrebbe essere uno o l'altro).
  - **Dettaglio:** Dato il suo nome generico, questo potrebbe essere uno script di utilità generale, oppure potrebbe contenere la logica di inizializzazione per il popup sul front-office, o anche qualche script minore per il back-office se viene caricato lì. È comune che i moduli abbiano un `script.js` per codice generico.
- `popuppro/js/tinymce16-force-urls.inc.js`, `popuppro/js/tinymce16.inc.js`:
  - **Ambito:** Back-office.
  - **Dettaglio:** Questi file sono correlati all'editor di testo ricco TinyMCE, in particolare la versione 1.6. Sono inclusi per fornire la funzionalità dell'editor HTML per il campo "Contenuto Popup" nella configurazione del back-office del modulo. `tinymce16-force-urls.inc.js` probabilmente gestisce l'assicurazione che gli URL siano formattati correttamente all'interno dell'editor.
- `popuppro/jscolor/jscolor.js`:
  - **Ambito:** Back-office.
  - **Dettaglio:** Questa è la libreria JavaScript per la funzionalità del selettore di colori utilizzata nella configurazione del back-office (ad esempio, per il colore di sfondo del popup, il colore del bordo, il colore dell'overlay). Fornisce l'interfaccia interattiva di selezione del colore.
- `popuppro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`:
  - **Ambito:** Back-office.
  - **Dettaglio:** Questo script fa parte di una libreria interna per la gestione dei template Smarty all'interno della configurazione del modulo. Probabilmente fornisce funzionalità per l'anteprima dei template, la loro selezione o l'inserimento dinamico di contenuti basati su template nell'editor HTML.

### 4.5 Fogli di stile CSS (`views/css/`)

- `popuppro/css.css`:
  - **Ambito:** Front-office.
  - **Dettaglio:** Questo è probabilmente il foglio di stile principale per il popup del front-office, che definisce il suo aspetto predefinito: posizionamento, dimensionamento, bordo, ombra, stile del pulsante di chiusura e potenzialmente regolazioni responsive.
  - **Selettori chiave:** `.popuppro-overlay`, `.popuppro-popup`, `.popuppro-close-btn`, `.popuppro-content`.
- `popuppro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`:
  - **Ambito:** Back-office.
  - **Dettaglio:** Fogli di stile per l'interfaccia di Smarty Templates Manager all'interno della configurazione del back-office del modulo. Stilizzerebbe la selezione dei template, le aree di anteprima e gli elementi UI correlati.
- `popuppro/popuppro.css`:
  - **Ambito:** Front-office.
  - **Dettaglio:** Simile a `css.css`, questo potrebbe contenere stili aggiuntivi o specifici per il popup, potenzialmente per diversi stati di animazione o elementi di contenuto specifici. Potrebbe esserci una certa sovrapposizione o separazione delle responsabilità tra `css.css` e `popuppro.css`.
  - **Selettori chiave:** Probabilmente simili a `css.css`, concentrandosi sui componenti principali del popup.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template Hook (`views/templates/hook/`)**: (Nessuno esplicitamente elencato in `views/templates/hook/`, ma `views/header.tpl` è probabilmente agganciato)

  - `popuppro/views/header.tpl`:
    - **Hook:** `displayHeader`
    - **Output:** Questo template è quasi certamente agganciato a `displayHeader`. Sarebbe responsabile dell'iniezione dei file JavaScript e CSS necessari nella sezione `<head>` del front-office, e potenzialmente di una struttura HTML iniziale o di dati di configurazione da utilizzare per JavaScript.
  - `popuppro/views/header_address.tpl`, `popuppro/views/header_carrier.tpl`:
    - **Hook:** Potenzialmente `displayHeader` o altri hook specifici relativi alle informazioni di indirizzo/corriere.
    - **Output:** Questi sembrano template di intestazione specializzati, possibilmente per visualizzare contenuti dinamici relativi all'indirizzo del cliente o alle informazioni del corriere *all'interno* di un popup, o per scenari di popup specifici. Il loro uso esatto dipenderebbe dalla logica del modulo.
  - `popuppro/views/popup.tpl`:
    - **Hook:** Non direttamente agganciato, ma renderizzato da JavaScript.
    - **Output:** Questo è il template principale per la struttura del popup del front-office. Definisce l'HTML per l'overlay, il contenitore del popup, il pulsante di chiusura e un segnaposto per il contenuto dinamico caricato tramite AJAX.
- **Template Admin (`views/templates/admin/`)**:

  - `popuppro/views/admin/admin.tpl`:
    - **Scopo:** Il template principale per la pagina di configurazione del modulo nel back office. Contiene il layout generale, le schede e la struttura per i moduli delle impostazioni.
  - `popuppro/views/admin/boscript.tpl`:
    - **Scopo:** Template JavaScript del back-office. Questo probabilmente inietta codice JavaScript specifico necessario per la pagina di configurazione dell'amministratore, come l'inizializzazione di TinyMCE, il selettore di colori o la convalida personalizzata del modulo.
  - `popuppro/views/admin/popup_preview.tpl`:
    - **Scopo:** Template per la visualizzazione di un'anteprima live o simulata del popup all'interno della configurazione del back-office, consentendo ai commercianti di vedere le modifiche mentre le apportano.
  - `popuppro/views/admin/presets.tpl`:
    - **Scopo:** Template per la gestione o la visualizzazione di template o stili popup predefiniti.
  - `popuppro/views/admin/shadow_editor.tpl`:
    - **Scopo:** Un template specializzato per la configurazione degli effetti ombra per il popup, offrendo potenzialmente controlli avanzati oltre il semplice colore/opacità.
  - `popuppro/views/admin/stats.tpl`:
    - **Scopo:** Se il modulo raccoglie statistiche (come suggerito da `popupstat.php`), questo template verrebbe utilizzato per visualizzare tali statistiche nel back office.
  - `popuppro/views/templates/admin/_configure/helpers/form/form.tpl`:
    - **Scopo:** Questo è un template di override standard di PrestaShop per la classe `HelperForm`, specificamente per il modulo di configurazione del modulo. Consente al modulo di personalizzare il modo in cui viene renderizzato il suo modulo di impostazioni, aggiungendo potenzialmente campi o layout personalizzati.
- **Template della libreria SmartyTemplatesManager (`popuppro/lib/smartyTemplatesManager/tpl/` e `views/`)**:

  - `popuppro/lib/smartyTemplatesManager/tpl/cartMini.tpl`, `example.tpl`, `freeShippingBar.tpl`, `helloCustomer.tpl`, `lastOrder.tpl`, `productHighlight.tpl`, `showReachedQtyInCart.tpl`:
    - **Scopo:** Questi sono template di contenuto predefiniti che il commerciante può selezionare o utilizzare come punto di partenza per il contenuto del proprio popup. Offrono casi d'uso comuni come display mini-carrello, annunci di spedizione gratuita, messaggi di benvenuto, dettagli dell'ultimo ordine, evidenziazioni di prodotti o messaggi di quantità raggiunta nel carrello. Questi verrebbero renderizzati dinamicamente nell'area principale del contenuto del popup.
  - `popuppro/lib/smartyTemplatesManager/views/buttonManager.tpl`, `buttonManagerNoJs.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`:
    - **Scopo:** Questi template fanno parte della libreria interna Smarty Templates Manager, utilizzati all'interno della configurazione del back-office per gestire e interagire con i template di contenuto. Forniscono l'interfaccia utente per creare, modificare e selezionare questi blocchi di contenuto predefiniti.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non sembra creare tabelle SQL personalizzate.
  - Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`. I nomi delle configurazioni chiave seguirebbero tipicamente il modello `POPUPPRO_NOME_IMPOSTAZIONE`. Esempi includono:
    - `POPUPPRO_ENABLED`
    - `POPUPPRO_CONTENT` (probabilmente multilingue)
    - `POPUPPRO_WIDTH`
    - `POPUPPRO_DISPLAY_ON`
    - `POPUPPRO_FREQUENCY`
    - `POPUPPRO_BG_COLOR`
    - …e così via per tutte le opzioni di configurazione.
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS e JavaScript necessari per il funzionamento del popup e potenzialmente inizializza variabili JavaScript globali o dati di configurazione. |
| `displayRightColumn` | Eseguito nella colonna destra delle pagine (se abilitato dal tema). | Sebbene la descrizione del modulo menzioni "Colonne", è meno probabile per un popup a schermo intero. Se utilizzato, potrebbe renderizzare un trigger per il popup o un elemento più piccolo, non sovrapposto. |
| `displayLeftColumn` | Eseguito nella colonna sinistra delle pagine (se abilitato dal tema). | Simile a `displayRightColumn`, meno probabile per il popup principale, ma potrebbe essere utilizzato per un trigger. |
| `displayFooter` | Eseguito in fondo a ogni pagina del front-office, prima del tag di chiusura `</body>`. | Potrebbe essere utilizzato per iniettare JavaScript che deve essere eseguito dopo che il DOM è completamente caricato, o per posizionare la struttura HTML del popup alla fine del documento. |
| `displayProductAdditionalInfo` (o hook simile per pagina prodotto) | Eseguito sulla pagina del prodotto, tipicamente sotto i dettagli principali del prodotto. | Se il modulo supporta popup specifici per prodotto, potrebbe utilizzare questo hook per iniettare un trigger o una logica popup specifica rilevante per il prodotto. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-end imposta i suoi media (CSS/JS). | Un hook comune per i moduli per registrare le loro risorse (CSS/JS) in modo efficiente, assicurando che vengano caricate solo quando necessario. |

## 5. Supporto Ufficiale e Aggiornamenti

Per il supporto ufficiale, gli aggiornamenti del modulo e qualsiasi ulteriore assistenza con il tuo modulo Prestashop Popup Pro, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto dedicato è pronto ad aiutarti a massimizzare il potenziale del tuo modulo.
