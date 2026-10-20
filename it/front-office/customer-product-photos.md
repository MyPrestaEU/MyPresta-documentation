---
title: "Foto prodotti dei clienti - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Foto prodotti dei clienti di MyPresta.eu."
sidebar:
  label: "Foto prodotti dei clienti - Manuale del commerciatore e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Customer product photos su MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-product-photos.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/customer-product-photos/)
>
> ---


# Foto prodotti dei clienti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Sono richieste le estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Foto prodotti dei clienti". Qui troverai una varietà di impostazioni per controllare il comportamento e l'aspetto del modulo sul tuo negozio.

#### Impostazioni generali

- **Consenti file JPEG?**
  - **Cosa fa questa impostazione:** Determina se i clienti possono caricare immagini in formato JPEG.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti possono caricare file `.jpg` o `.jpeg`.
    - *Quando disabilitato:* I file JPEG verranno rifiutati durante il caricamento.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** La maggior parte delle foto sono scattate in JPEG. Mantenere questa opzione abilitata garantisce la massima compatibilità per i caricamenti dei clienti.
- **Consenti file GIF?**
  - **Cosa fa questa impostazione:** Determina se i clienti possono caricare immagini in formato GIF.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti possono caricare file `.gif`.
    - *Quando disabilitato:* I file GIF verranno rifiutati durante il caricamento.
  - **Valore consigliato:** SÌ (a meno che tu non abbia un motivo specifico per non consentire immagini animate)
  - **Scenario / esempio del commerciante:** I GIF possono essere utili per mostrare brevi animazioni di un prodotto, ma possono anche essere file più grandi. Abilita se vuoi supportarli.
- **Consenti file PNG?**
  - **Cosa fa questa impostazione:** Determina se i clienti possono caricare immagini in formato PNG.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti possono caricare file `.png`.
    - *Quando disabilitato:* I file PNG verranno rifiutati durante il caricamento.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** I PNG sono ottimi per immagini con trasparenza o grafica nitida. È un formato comune, quindi abilitarlo è generalmente una buona idea.
- **Consenti file BMP?**
  - **Cosa fa questa impostazione:** Determina se i clienti possono caricare immagini in formato BMP.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti possono caricare file `.bmp`.
    - *Quando disabilitato:* I file BMP verranno rifiutati durante il caricamento.
  - **Valore consigliato:** NO (a meno che non sia specificamente richiesto)
  - **Scenario / esempio del commerciante:** I file BMP sono tipicamente molto grandi e non compressi, rendendoli inadatti per l'uso web. Disabilitare questa opzione aiuta a mantenere efficiente la tua galleria.
- **Consenti ai clienti non loggati di caricare foto?**
  - **Cosa fa questa impostazione:** Controlla se i visitatori che non sono loggati a un account cliente possono caricare foto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli ospiti possono caricare foto. Potrebbe essere loro richiesto un indirizzo email o un nome.
    - *Quando disabilitato:* Solo i clienti registrati e loggati possono caricare foto.
  - **Valore consigliato:** SÌ (se vuoi la massima generazione di contenuti), NO (se vuoi collegare i contenuti a specifici account cliente)
  - **Scenario / esempio del commerciante:** Se vuoi massimizzare i contenuti generati dagli utenti, consentire agli ospiti è vantaggioso. Se vuoi tenere traccia di chi carica cosa e potenzialmente premiarli, richiedi il login.
- **Dimensione massima del file (in MB)**
  - **Cosa fa questa impostazione:** Imposta il limite superiore per la dimensione di un file immagine che un cliente può caricare.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato a 5:* I clienti non possono caricare file più grandi di 5MB.
    - *Quando impostato a 0:* Nessun limite (anche se i limiti del server PHP si applicheranno comunque).
  - **Valore consigliato:** 2-5 MB
  - **Scenario / esempio del commerciante:** Un limite ragionevole impedisce ai clienti di caricare file eccessivamente grandi che potrebbero rallentare il tuo sito o consumare troppo spazio sul server. 2-5MB sono solitamente sufficienti per immagini web di alta qualità.
- **Altezza miniatura (px)**
  - **Cosa fa questa impostazione:** Definisce l'altezza delle immagini in miniatura generate per la galleria.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato a 100:* Tutte le miniature avranno un'altezza di 100 pixel.
    - *Quando impostato a 200:* Tutte le miniature avranno un'altezza di 200 pixel.
  - **Valore consigliato:** 150-250px (regola in base al design del tuo tema)
  - **Scenario / esempio del commerciante:** Dimensioni coerenti delle miniature garantiscono un layout della galleria pulito e organizzato. Regola questo per adattarlo all'estetica del tuo tema.
- **Larghezza miniatura (px)**
  - **Cosa fa questa impostazione:** Definisce la larghezza delle immagini in miniatura generate per la galleria.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato a 100:* Tutte le miniature avranno una larghezza di 100 pixel.
    - *Quando impostato a 200:* Tutte le miniature avranno una larghezza di 200 pixel.
  - **Valore consigliato:** 150-250px (regola in base al design del tuo tema)
  - **Scenario / esempio del commerciante:** Similmente all'altezza, una larghezza coerente aiuta a mantenere una galleria visivamente accattivante.
- **Foto per pagina nella galleria** (CG\_PAGINATION)
  - **Cosa fa questa impostazione:** Controlla quante foto dei clienti vengono visualizzate su una singola pagina nella vista principale della galleria prima che entri in gioco la paginazione.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato a 12:* La galleria mostrerà 12 foto per pagina.
    - *Quando impostato a 24:* La galleria mostrerà 24 foto per pagina.
  - **Valore consigliato:** 12-24
  - **Scenario / esempio del commerciante:** Un numero moderato impedisce di sopraffare l'utente e mantiene i tempi di caricamento della pagina ragionevoli. Troppo poche significano più clic, troppe possono rallentare la pagina.
- **Abilita votazione per le foto?** (CG\_voting)
  - **Cosa fa questa impostazione:** Consente ai clienti di votare le foto caricate, tipicamente con un semplice "mi piace" o una valutazione a stelle.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I controlli di votazione (ad esempio, stelle, pollice in su) appariranno accanto a ogni foto.
    - *Quando disabilitato:* Non verranno visualizzate opzioni di votazione.
  - **Valore consigliato:** SÌ (incoraggia l'interazione)
  - **Scenario / esempio del commerciante:** Abilitare la votazione può evidenziare le foto popolari e incoraggiare un maggiore coinvolgimento dalla tua comunità.
- **Consenti ai clienti non loggati di votare?** (cg\_unl\_voting)
  - **Cosa fa questa impostazione:** Determina se i visitatori che non sono loggati possono esprimere voti sulle foto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli ospiti possono votare le foto.
    - *Quando disabilitato:* Solo i clienti loggati possono votare.
  - **Valore consigliato:** NO (per prevenire voti spam/bot e garantire un coinvolgimento più significativo)
  - **Scenario / esempio del commerciante:** Limitare la votazione agli utenti loggati aiuta a garantire che i voti provengano da clienti reali e riduce il rischio di manipolazione.
- **Stile di votazione** (CG\_VOTE\_STAR, CGV\_voting)
  - **Cosa fa questa impostazione:** Seleziona lo stile visivo per il meccanismo di votazione (ad esempio, diversi colori delle stelle).
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 'Stelle Nere':* La votazione utilizzerà icone a stella nere.
    - *Quando impostato su 'Stelle Oro':* La votazione utilizzerà icone a stella dorate.
  - **Valore consigliato:** Stelle Oro (spesso associate a qualità e recensioni)
  - **Scenario / esempio del commerciante:** Scegli uno stile che si adatti meglio al branding e all'estetica del tuo negozio.
- **Abilita modalità concorso?** (cg\_contest)
  - **Cosa fa questa impostazione:** Attiva funzionalità che supportano l'esecuzione di un concorso fotografico, come la visualizzazione dei vincitori o regole specifiche del concorso.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Potrebbero apparire opzioni o visualizzazioni aggiuntive relative al concorso.
    - *Quando disabilitato:* Comportamento standard della galleria.
  - **Valore consigliato:** NO (a meno che tu non stia attivamente gestendo un concorso)
  - **Scenario / esempio del commerciante:** Se hai intenzione di organizzare un concorso "miglior foto", abilita questa opzione per sfruttare le funzionalità di concorso del modulo.

#### Posizioni di visualizzazione Front-Office

Queste impostazioni controllano dove la galleria fotografica dei clienti e le opzioni di caricamento appaiono sul tuo negozio.

- **Mostra modulo di caricamento nella pagina prodotto?** (CG\_FUPLOADON)
  - **Cosa fa questa impostazione:** Determina se il modulo di caricamento foto è direttamente visibile nella pagina prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti vedranno un modulo per caricare foto direttamente nella pagina prodotto.
    - *Quando disabilitato:* Il modulo di caricamento non apparirà nella pagina prodotto; i clienti potrebbero dover andare al loro account o a una pagina galleria dedicata per caricare.
  - **Valore consigliato:** SÌ (per la massima comodità e generazione di contenuti)
  - **Scenario / esempio del commerciante:** Rendere il modulo di caricamento facilmente accessibile nella pagina prodotto incoraggia più clienti a condividere le loro foto subito dopo aver visualizzato il prodotto.
- **Mostra galleria nella pagina prodotto come scheda?** (CG\_PRODUCTTAB, cg\_productTabM)
  - **Cosa fa questa impostazione:** Integra la galleria fotografica dei clienti come una nuova scheda nella pagina prodotto (ad esempio, accanto a "Descrizione" o "Scheda tecnica").
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Una nuova scheda apparirà nelle pagine prodotto, mostrando le foto dei clienti per quel prodotto specifico.
    - *Quando disabilitato:* La galleria non apparirà come scheda.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Questo è un modo molto prominente ed efficace per visualizzare i contenuti generati dagli utenti, rendendoli facilmente scopribili per gli acquirenti.
- **Mostra galleria nella pagina prodotto nel footer?** (CG\_PRODUCTFOOTER)
  - **Cosa fa questa impostazione:** Visualizza una sezione di foto dei clienti nell'area del footer della pagina prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un blocco di foto dei clienti apparirà sotto il contenuto principale del prodotto.
    - *Quando disabilitato:* Nessuna foto apparirà nel footer della pagina prodotto.
  - **Valore consigliato:** SÌ (come punto di visualizzazione aggiuntivo)
  - **Scenario / esempio del commerciante:** Questo offre un'altra opportunità per mostrare le foto dei clienti senza ingombrare l'area principale delle informazioni sul prodotto.
- **Mostra galleria nell'account cliente?** (CG\_CUSTOMERACCOUNT, CG\_CUSTOMERACCOUNTV)
  - **Cosa fa questa impostazione:** Crea una sezione dedicata "Le mie foto" all'interno dell'area account personale del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti loggati vedranno un nuovo link e una pagina nel loro account per gestire le loro foto caricate.
    - *Quando disabilitato:* I clienti non possono gestire le loro foto dal loro account.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Essenziale per i clienti per visualizzare e gestire i loro contributi, promuovendo un senso di proprietà e comunità.
- **Mostra link alla galleria nel blocco "Il mio account"?** (CG\_MYACCOUNTBLOCK, CG\_MYACCOUNTBLOCKV)
  - **Cosa fa questa impostazione:** Aggiunge un link alla sezione "Le mie foto" (o alla galleria principale) nel blocco "Il mio account", che si trova spesso nella colonna sinistra o destra o nel footer.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un link rapido apparirà per gli utenti loggati.
    - *Quando disabilitato:* Il link non sarà presente nel blocco.
  - **Valore consigliato:** SÌ (per una facile navigazione)
  - **Scenario / esempio del commerciante:** Rende molto facile per i clienti accedere alla loro galleria fotografica o caricare nuove foto da quasi ogni pagina.
- **Mostra galleria nella colonna destra?** (CG\_RIGHTCOL)
  - **Cosa fa questa impostazione:** Visualizza un blocco di foto dei clienti nella colonna destra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un blocco dinamico di foto apparirà nella barra laterale destra.
    - *Quando disabilitato:* Nessuna foto apparirà nella colonna destra.
  - **Valore consigliato:** NO (può essere fonte di distrazione, considera solo se il tuo tema ha ampio spazio)
  - **Scenario / esempio del commerciante:** Utile se hai un layout ampio e vuoi mostrare costantemente i contenuti dei clienti, ma a volte può ingombrare la pagina.
- **Mostra galleria nella colonna sinistra?** (CG\_LEFTCOL)
  - **Cosa fa questa impostazione:** Visualizza un blocco di foto dei clienti nella colonna sinistra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un blocco dinamico di foto apparirà nella barra laterale sinistra.
    - *Quando disabilitato:* Nessuna foto apparirà nella colonna sinistra.
  - **Valore consigliato:** NO (simile alla colonna destra, usa con parsimonia)
  - **Scenario / esempio del commerciante:** Simile alla colonna destra, usa se il design del tuo tema lo consente senza compromettere la leggibilità.
- **Mostra galleria nella homepage?** (CG\_GALLERY, cg\_hpg\_nb, cg\_hpg\_o)
  - **Cosa fa questa impostazione:** Visualizza una selezione di foto dei clienti direttamente sulla homepage del tuo negozio. Potresti anche avere opzioni per controllare il numero di foto (cg\_hpg\_nb) e il loro ordine (cg\_hpg\_o).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Una sezione con foto dei clienti apparirà nella homepage.
    - *Quando disabilitato:* Nessuna foto dei clienti verrà mostrata nella homepage.
  - **Valore consigliato:** SÌ (altamente raccomandato per l'engagement)
  - **Scenario / esempio del commerciante:** La homepage è un'area privilegiata. Mostrare le foto dei clienti qui trasmette immediatamente fiducia e senso di comunità ai nuovi visitatori.
- **Escludi prodotti specifici dalla galleria?** (cg\_excludeproduct)
  - **Cosa fa questa impostazione:** Ti consente di specificare gli ID dei prodotti per i quali non devono essere visualizzate o caricate foto dei clienti.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene inserito l'ID prodotto 123:* Il prodotto 123 non mostrerà foto dei clienti e i caricamenti per esso saranno disabilitati.
    - *Quando lasciato vuoto:* Tutti i prodotti sono idonei per le foto dei clienti.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia prodotti sensibili o non visivi.
  - **Scenario / esempio del commerciante:** Se vendi prodotti digitali o servizi che non hanno una componente visiva, o prodotti per i quali non desideri contenuti generati dagli utenti, puoi escluderli qui.

#### Notifiche e aggiornamenti

- **Abilita notifiche email per nuovi caricamenti?** (CG\_NTF)
  - **Cosa fa questa impostazione:** Invia una notifica email all'amministratore del negozio ogni volta che viene caricata una nuova foto del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Riceverai un'email per ogni nuovo caricamento, permettendoti di moderare rapidamente.
    - *Quando disabilitato:* Non verranno inviate notifiche email.
  - **Valore consigliato:** SÌ (essenziale per la moderazione e il controllo qualità)
  - **Scenario / esempio del commerciante:** Tenere sotto controllo i nuovi caricamenti ti aiuta a garantire che tutti i contenuti siano appropriati e di alta qualità prima che siano ampiamente visibili.
- **Aggiornamenti MyPresta.eu** (mypresta\_updates, update\_, updatev\_)
  - **Cosa fa questa impostazione:** Questa è un'impostazione standard nei moduli MyPresta.eu per verificare la disponibilità di aggiornamenti.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo controllerà periodicamente MyPresta.eu per nuove versioni.
    - *Quando disabilitato:* Il modulo non controllerà automaticamente gli aggiornamenti.
  - **Valore consigliato:** SÌ (rimani sempre aggiornato per sicurezza e funzionalità)
  - **Scenario / esempio del commerciante:** Mantenere questa opzione abilitata ti assicura di essere informato su nuove funzionalità, correzioni di bug e patch di sicurezza, aiutando il tuo negozio a rimanere aggiornato e sicuro.

#### Impostazioni interne/avanzate (solitamente lasciare come predefinite)

- **CG\_LAST\_TAB**: Impostazione interna per ricordare l'ultima scheda attiva nella configurazione del modulo.
- **cg\_altered1, cg\_altered2**: Flag interni, solitamente correlati agli aggiornamenti del modulo o alle migrazioni di dati.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Consenti file JPEG? | SÌ | Consente ai clienti di caricare immagini JPEG. |
| Configurazione modulo | Consenti file GIF? | SÌ | Consente ai clienti di caricare immagini GIF. |
| Configurazione modulo | Consenti file PNG? | SÌ | Consente ai clienti di caricare immagini PNG. |
| Configurazione modulo | Consenti file BMP? | NO | Non consente immagini BMP grandi e non compresse. |
| Configurazione modulo | Consenti ai clienti non loggati di caricare foto? | SÌ / NO (Scelta del commerciante) | Controlla i caricamenti degli ospiti. |
| Configurazione modulo | Dimensione massima del file (in MB) | 2-5 MB | Limita la dimensione del caricamento per prevenire file grandi. |
| Configurazione modulo | Altezza miniatura (px) | 150-250px | Imposta un'altezza coerente per le miniature della galleria. |
| Configurazione modulo | Larghezza miniatura (px) | 150-250px | Imposta una larghezza coerente per le miniature della galleria. |
| Configurazione modulo | Foto per pagina nella galleria | 12-24 | Controlla la paginazione per la galleria principale. |
| Configurazione modulo | Abilita votazione per le foto? | SÌ | Consente ai clienti di votare le foto. |
| Configurazione modulo | Consenti ai clienti non loggati di votare? | NO | Previene voti spam/bot. |
| Configurazione modulo | Stile di votazione | Stelle Oro | Imposta lo stile visivo per le icone di votazione. |
| Configurazione modulo | Abilita modalità concorso? | NO | Attiva funzionalità specifiche per i concorsi. |
| Configurazione modulo | Mostra modulo di caricamento nella pagina prodotto? | SÌ | Visualizza il modulo di caricamento direttamente nelle pagine prodotto. |
| Configurazione modulo | Mostra galleria nella pagina prodotto come scheda? | SÌ | Aggiunge una scheda dedicata per le foto nelle pagine prodotto. |
| Configurazione modulo | Mostra galleria nella pagina prodotto nel footer? | SÌ | Visualizza le foto sotto il contenuto del prodotto. |
| Configurazione modulo | Mostra galleria nell'account cliente? | SÌ | Crea una sezione "Le mie foto" negli account cliente. |
| Configurazione modulo | Mostra link alla galleria nel blocco "Il mio account"? | SÌ | Aggiunge un link rapido alla galleria nel blocco Il mio account. |
| Configurazione modulo | Mostra galleria nella colonna destra? | NO | Visualizza le foto nella barra laterale destra. |
| Configurazione modulo | Mostra galleria nella colonna sinistra? | NO | Visualizza le foto nella barra laterale sinistra. |
| Configurazione modulo | Mostra galleria nella homepage? | SÌ | Visualizza le foto nella homepage del negozio. |
| Configurazione modulo | Escludi prodotti specifici dalla galleria? | Lascia vuoto | Impedisce le foto per i prodotti specificati. |
| Configurazione modulo | Abilita notifiche email per nuovi caricamenti? | SÌ | Invia email all'amministratore per i nuovi caricamenti di foto. |
| Configurazione modulo | Aggiornamenti MyPresta.eu | SÌ | Abilita i controlli automatici degli aggiornamenti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le mie foto dei clienti non vengono visualizzate dopo il caricamento, o la galleria appare vuota.**
**R1:**

- **Controlla la configurazione del modulo:** Assicurati che le opzioni di visualizzazione (ad esempio, "Mostra galleria nella pagina prodotto come scheda", "Mostra galleria nella homepage?") siano abilitate nelle impostazioni del modulo.
- **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" e "Svuota cache" se sono opzioni separate). Questo spesso risolve i problemi di visualizzazione.
- **Moderazione delle immagini:** Alcuni moduli hanno un processo di approvazione. Controlla se esiste una sezione amministrativa (anche se questo modulo non ha un controller amministrativo dedicato, potrebbe avere uno stato di approvazione interno) dove le foto devono essere approvate prima di essere pubblicate.
- **Permessi dei file:** Assicurati che la tua cartella `img/customersgallery` (o percorso simile dove sono archiviate le immagini) abbia i permessi di scrittura corretti (solitamente 755 o 775). Il tuo provider di hosting può aiutarti con questo.

**D2: I clienti hanno problemi a caricare le foto, o ricevono un messaggio di errore.**
**R2:**

- **Controlla i limiti di tipo e dimensione del file:** Rivedi le impostazioni "Consenti file JPEG/GIF/PNG/BMP?" e "Dimensione massima del file (in MB)" nella configurazione del modulo. Assicurati che il file del cliente corrisponda ai tipi consentiti e rientri nel limite di dimensione.
- **Limiti PHP del server:** Anche se il modulo consente una dimensione di file elevata, la configurazione PHP del tuo server (ad esempio, `upload_max_filesize`, `post_max_size` in `php.ini`) potrebbe imporre un limite più severo. Contatta il tuo provider di hosting per verificare ed eventualmente aumentare questi limiti se necessario.
- **Compatibilità del browser:** Chiedi al cliente di provare un browser diverso o di svuotare la cache del browser.
- **Errori JavaScript:** Apri la console per sviluppatori del tuo browser (F12) e controlla eventuali errori JavaScript durante il processo di caricamento. Questo potrebbe indicare un conflitto con un altro modulo o tema.

**D3: Le foto dei clienti appaiono distorte o di dimensioni errate nella galleria.**
**R3:**

- **Dimensioni delle miniature:** Regola le impostazioni "Altezza miniatura (px)" e "Larghezza miniatura (px)" nella configurazione del modulo. Sperimenta con valori diversi per trovare ciò che si adatta meglio al tuo tema. Ricorda di svuotare la cache di PrestaShop dopo aver apportato modifiche.
- **Conflitti CSS:** Il CSS del tuo tema potrebbe sovrascrivere lo stile del modulo. Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare gli elementi e identificare eventuali regole CSS in conflitto. Potrebbe essere necessario un webmaster per aggiungere CSS personalizzato al tuo tema per correggere questo problema.

**D4: Il link "Le mie foto" non appare nell'account cliente o nel blocco "Il mio account".**
**R4:**

- **Aggancio del modulo:** Assicurati che il modulo sia correttamente agganciato a `displayCustomerAccount` e `displayMyAccountBlock` (o `displayMyAccountBlockFooter` a seconda del tuo tema). Puoi verificarlo in **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti) e cercare il modulo. Se non è agganciato, prova a reinstallare il modulo o ad agganciarlo manualmente.
- **Configurazione del modulo:** Ricontrolla che "Mostra galleria nell'account cliente?" e "Mostra link alla galleria nel blocco 'Il mio account'?" siano abilitati nelle impostazioni del modulo.
- **Accesso cliente:** Il link "Le mie foto" è visibile solo ai clienti loggati. Assicurati di essere loggato durante il test.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Foto prodotti dei clienti", progettata per sviluppatori e webmaster che necessitano di comprenderne il funzionamento interno, personalizzarne il comportamento o risolvere problemi avanzati.

### 4.1 Panoramica dell'architettura

Il modulo "Foto prodotti dei clienti" segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente i Front Controller per l'interazione con l'utente e i template Smarty per il rendering. Utilizza la classe principale del modulo (`customersgallery.php`) per la gestione della configurazione e la registrazione degli hook. Sebbene non estenda `ObjectModel` per i suoi dati principali, interagisce direttamente con il database per archiviare i metadati delle foto e si affida al file system di PrestaShop per l'archiviazione delle immagini. AJAX è ampiamente utilizzato per il caricamento dinamico dei contenuti e il caricamento delle foto, fornendo un'esperienza utente fluida senza ricariche complete della pagina.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono tutte le interazioni rivolte al cliente, inclusa la visualizzazione delle gallerie, la gestione delle foto degli utenti e l'elaborazione delle richieste AJAX.

- **`controllers/front/ajax.php`**
  - **Nome classe:** `CustomersGalleryAjaxModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Questo è l'endpoint primario per tutte le operazioni asincrone (AJAX). Gestisce:
    - Caricamenti di foto dalla pagina prodotto o dall'account cliente.
    - Azioni di voto (mi piace/valutazione delle foto).
    - Potenzialmente richieste di eliminazione o moderazione delle immagini dalla sezione "Le mie foto" del cliente.
    - Restituisce risposte JSON che indicano successo o fallimento, insieme ai dati pertinenti.
- **`controllers/front/gallery.php`**
  - **Nome classe:** `CustomersGalleryGalleryModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Renderizza la pagina principale e dedicata della galleria fotografica dei clienti. Questa pagina visualizza tipicamente tutte le foto dei clienti approvate, possibilmente con opzioni di paginazione e filtro. Recupera i dati delle foto dal database e li assegna al template `gallery.tpl`.
- **`controllers/front/index.php`**
  - **Nome classe:** `CustomersGalleryIndexModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller funge probabilmente da punto di ingresso predefinito o di fallback per le rotte front-office del modulo. Potrebbe reindirizzare alla galleria principale o al controller `myphotos` se acceduto direttamente senza parametri specifici.
- **`controllers/front/myphotos.php`**
  - **Nome classe:** `CustomersGalleryMyPhotosModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Gestisce la sezione "Le mie foto" all'interno dell'account del cliente. Visualizza le foto caricate dal cliente attualmente loggato, consente loro di gestire (ad esempio, eliminare) le proprie foto e potenzialmente fornisce un'interfaccia di caricamento. Richiede l'autenticazione del cliente.
- **`controllers/front/myvideos.php`**
  - **Nome classe:** `CustomersGalleryMyVideosModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Sebbene il nome del modulo sia "Foto prodotti dei clienti", questo controller suggerisce una potenziale (o pianificata) funzionalità per il caricamento di video da parte dei clienti. Funzionerebbe probabilmente in modo simile a `myphotos.php` ma per i contenuti video.

#### Controller Admin Back-Office

Il modulo non ha controller Admin dedicati. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non sembra definire classi personalizzate che estendono `ObjectModel` in una directory `classes/` dedicata. Tutta la logica principale per l'interazione con il database, l'elaborazione delle immagini e le regole aziendali è probabilmente incapsulata nel file principale `customersgallery.php` e nei controller frontali. Ciò significa che le operazioni sul database sono gestite direttamente tramite chiamate a `Db::getInstance()`.

### 4.4 Risorse JavaScript (`views/js/`)

- **`customersgallery/js/customersgallery.js`**
  - **Ambito:** Front-office
  - **Dettagli:** Questo è il JavaScript personalizzato principale per il modulo. Probabilmente gestisce:
    - Chiamate AJAX per il caricamento di foto (ad esempio, binding alle sottomissioni di moduli).
    - Chiamate AJAX per i meccanismi di votazione.
    - Caricamento dinamico del contenuto della galleria.
    - Validazione lato client per tipi e dimensioni di file prima del caricamento.
    - Interazione con la libreria Fancybox per lightbox di immagini.
    - Listener di eventi per paginazione, filtraggio e altre interazioni della galleria.
- **`customersgallery/js/fancybox.js`**
  - **Ambito:** Front-office
  - **Dettagli:** Questa è una libreria di terze parti (Fancybox) utilizzata per visualizzare le immagini in un overlay lightbox reattivo ed elegante quando un utente clicca su una miniatura. Gestisce lo zoom delle immagini, la navigazione tra le immagini della galleria e la presentazione modale.
- **`customersgallery/js/script.js`**
  - **Ambito:** Front-office
  - **Dettagli:** Questo potrebbe essere uno script supplementare, potenzialmente per miglioramenti generali dell'interfaccia utente, animazioni specifiche o gestione di eventi aggiuntivi non coperti da `customersgallery.js`. Potrebbe anche contenere routine di inizializzazione per altri componenti JS.
- **`customersgallery/lib/voucherengine/script.js`**
  - **Ambito:** Front-office (potenzialmente)
  - **Dettagli:** La presenza di `voucherengine` suggerisce una potenziale integrazione o una funzionalità separata per la generazione/gestione di buoni, possibilmente come ricompensa per il caricamento di foto o la partecipazione a concorsi. Questo script gestirebbe la logica lato client per un tale sistema.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`customersgallery/css/customersgallery.css`**
  - **Ambito:** Stile del cliente Front-office
  - **Dettagli:** Questo è il foglio di stile principale per i componenti front-office del modulo. Stila:
    - Il layout della galleria fotografica (griglia, flexbox).
    - Contenitori e miniature delle singole foto.
    - Moduli e pulsanti di caricamento.
    - Controlli di paginazione.
    - Elementi di votazione (se non gestiti da CSS specifici per le stelle).
    - Regolazioni reattive per diverse dimensioni dello schermo.
  - **Selettori di classe CSS chiave:** `.customer-photo-gallery`, `.cg-item`, `.cg-thumbnail`, `.cg-upload-form`, `.cg-vote-stars`
- **`customersgallery/css/fancybox.css`**
  - **Ambito:** Stile del cliente Front-office
  - **Dettagli:** Foglio di stile per la libreria lightbox Fancybox, che garantisce che l'overlay dell'immagine, le frecce di navigazione, il pulsante di chiusura e le didascalie siano visivamente coerenti e accattivanti.
- **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**
  - **Ambito:** Stile del cliente Front-office
  - **Dettagli:** Questi sono fogli di stile specifici per il sistema di votazione basato su stelle. Ogni file fornisce una diversa combinazione di colori o stile visivo per le icone a stella, consentendo al commerciante di scegliere un design che si adatti al proprio tema. `star.css` è probabilmente lo stile di base, con gli altri che forniscono override di colore.
- **`customersgallery/lib/voucherengine/ps16.css`**
  - **Ambito:** Front-office (potenzialmente)
  - **Dettagli:** Questo foglio di stile, trovato all'interno della directory `voucherengine`, suggerisce uno stile specifico per le funzionalità relative ai buoni, potenzialmente ottimizzato per i temi di PrestaShop 1.6, ma probabilmente compatibile o adattabile per le versioni più recenti.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

Questi template sono progettati per essere renderizzati quando vengono eseguiti specifici hook di PrestaShop, integrando il contenuto del modulo in varie parti del negozio.

- **`customersgallery/views/templates/hook/column-link.tpl`**
  - **Hook:** `displayLeftColumn`, `displayRightColumn`
  - **Output:** Un link o un blocco che indirizza gli utenti alla galleria fotografica principale dei clienti o alla sezione "Le mie foto", tipicamente posizionato nelle barre laterali.
- **`customersgallery/views/templates/hook/customer-my-account.tpl`**
  - **Hook:** `displayCustomerAccount`
  - **Output:** Un link o un blocco all'interno della pagina "Il mio account" del cliente, che porta alla sua sezione dedicata "Le mie foto".
- **`customersgallery/views/templates/hook/hookHome.tpl`**
  - **Hook:** `displayHome`
  - **Output:** Un blocco o una sezione che visualizza una selezione di foto dei clienti sulla homepage del negozio, spesso con i caricamenti più recenti o più popolari.
- **`customersgallery/views/templates/hook/my-account.tpl`**
  - **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
  - **Output:** Un link alla sezione "Le mie foto", integrato nel blocco standard "Il mio account" che appare nelle colonne o nel footer per gli utenti loggati.
- **`customersgallery/views/templates/hook/productfooter.tpl`**
  - **Hook:** `displayProductFooter`, `displayProductExtraContent`
  - **Output:** Una sezione che visualizza le foto dei clienti per il prodotto corrente, situata sotto il contenuto principale del prodotto nella pagina prodotto.
- **`customersgallery/views/templates/hook/tab.tpl`**
  - **Hook:** `displayProductTab`
  - **Output:** L'HTML per un'intestazione di una nuova scheda (ad esempio, "Foto clienti") che appare nella pagina prodotto.
- **`customersgallery/views/templates/hook/tabContents.tpl`**
  - **Hook:** `displayProductTabContent`
  - **Output:** Il contenuto effettivo visualizzato quando la scheda "Foto clienti" è attiva nella pagina prodotto, mostrando la galleria e potenzialmente il modulo di caricamento per quel prodotto specifico.

#### Template personalizzati (`views/templates/custom/`)

Questi template sono probabilmente utilizzati per moduli specifici o parti del processo di caricamento.

- **`customersgallery/views/templates/custom/upload-form.tpl`**
  - **Scopo:** Renderizza il modulo HTML che i clienti utilizzano per caricare le loro foto prodotto. Questa potrebbe essere una versione più semplice o un'iterazione precedente.
- **`customersgallery/views/templates/custom/upload-form2.tpl`**
  - **Scopo:** Probabilmente una versione aggiornata o alternativa del modulo di caricamento, potenzialmente con stili, funzionalità o compatibilità diversi per le versioni più recenti di PrestaShop.

#### Template Front-Office (`views/templates/front/`)

Questi template sono tipicamente utilizzati dai controller frontali del modulo per renderizzare pagine complete o sezioni significative della funzionalità del modulo.

- **`customersgallery/views/templates/front/gallery.tpl`**
  - **Scopo:** Il template principale per la pagina dedicata della galleria fotografica dei clienti, che visualizza tutte le foto con paginazione.
- **`customersgallery/views/templates/front/gallery2.tpl`**
  - **Scopo:** Una versione alternativa o aggiornata del template della galleria principale, che offre potenzialmente layout o funzionalità diverse.
- **`customersgallery/views/templates/front/gallery3.tpl`**
  - **Scopo:** Un'altra versione alternativa o aggiornata del template della galleria principale. Il modulo potrebbe passare da una all'altra in base alla configurazione o alla versione di PrestaShop.
- **`customersgallery/views/templates/front/menu.tpl`**
  - **Scopo:** Renderizza un menu di navigazione specifico per la galleria fotografica dei clienti, potenzialmente per filtrare, ordinare o navigare tra "Le mie foto" e la galleria principale.
- **`customersgallery/views/templates/front/my-photos.tpl`**
  - **Scopo:** Renderizza la pagina "Le mie foto" all'interno dell'account del cliente, mostrando le immagini caricate e le opzioni di gestione.
- **`customersgallery/views/templates/front/my-videos-16.tpl`**
  - **Scopo:** Template per la sezione "I miei video", specificamente progettato o ottimizzato per PrestaShop 1.6, se la funzione di caricamento video è abilitata.
- **`customersgallery/views/templates/front/video-upload.tpl`**
  - **Scopo:** Renderizza il modulo per i clienti per caricare video, se questa funzione è attiva.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo non definisce esplicitamente file SQL personalizzati, ma in base alla sua funzionalità, interagirà con il database.

- **Tabelle personalizzate (probabilmente create durante install()):**
  - `_customersgallery`: Archivia i metadati per ogni foto caricata (ad esempio, `id_customersgallery`, `id_customer`, `id_product`, `filename`, `date_add`, `approved`, `votes`, `active`).
  - `_customersgallery_vote`: Archivia i record dei voti dei clienti (ad esempio, `id_customersgallery_vote`, `id_customersgallery`, `id_customer`, `ip_address`, `date_add`).
- **Record di configurazione (archiviati in `ps_configuration`):**
  - `CG_LAST_TAB`, `CG_ALLOW_JPEG`, `CG_ALLOW_GIF`, `CG_ALLOW_PNG`, `CG_ALLOW_BMP`, `mypresta_updates`, `CG_PAGINATION`, `CG_ALLOW_UNLOGGED`, `CG_MAX_FILE_SIZE`, `CG_PRODUCTTAB`, `cg_productTabM`, `CG_PRODUCTFOOTER`, `CG_CUSTOMERACCOUNT`, `CG_MYACCOUNTBLOCK`, `CG_THUMBHEIGHT`, `CG_THUMBWIDTH`, `CG_FUPLOADON`, `CG_GALLERY`, `CG_RIGHTCOL`, `CG_LEFTCOL`, `CG_NTF`, `update_`, `updatev_`, `cg_altered1`, `cg_altered2`, `cg_hpg_nb`, `cg_hpg_o`, `cg_contest`, `cg_excludeproduct`, `CG_CUSTOMERACCOUNTV`, `CG_MYACCOUNTBLOCKV`, `CG_voting`, `CG_VOTE_STAR`, `CGV_voting`, `cg_unl_voting`.

#### Tabella degli hook registrati

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta le risorse CSS e JavaScript richieste dal modulo (ad esempio, `customersgallery.css`, `fancybox.js`, `customersgallery.js`). |
| `displayMyAccountBlock` | Nel blocco "Il mio account" del cliente (spesso nella colonna sinistra/destra o nel footer). | Aggiunge un link alla sezione "Le mie foto" del cliente. |
| `displayLeftColumn` | Nella barra laterale sinistra del negozio. | Visualizza un blocco di foto dei clienti o un link alla galleria. |
| `displayRightColumn` | Nella barra laterale destra del negozio. | Visualizza un blocco di foto dei clienti o un link alla galleria. |
| `displayHome` | Nella homepage del negozio. | Visualizza una sezione di foto dei clienti (più recenti, più popolari). |
| `displayProductTab` | Nella pagina prodotto, per aggiungere nuove schede. | Aggiunge l'intestazione della scheda "Foto clienti". |
| `displayProductTabContent` | Nella pagina prodotto, per il contenuto di una scheda. | Visualizza la galleria fotografica dei clienti e il modulo di caricamento all'interno della scheda "Foto clienti". |
| `displayProductFooter` | Nella parte inferiore della pagina prodotto. | Visualizza una sezione di foto dei clienti per il prodotto corrente. |
| `displayProductExtraContent` | Un altro hook per contenuti extra nella pagina prodotto. | Può essere utilizzato come posizionamento alternativo o aggiuntivo per contenuti fotografici specifici del prodotto. |
| `displayCustomerAccount` | Nella pagina "Il mio account" del cliente. | Aggiunge un link alla sezione "Le mie foto" per il cliente loggato. |
| `displayLeftColumnProduct` | Nella colonna sinistra specificamente nelle pagine prodotto. | Visualizza un blocco di foto dei clienti o un link alla galleria nelle pagine prodotto. |
| `displayRightColumnProduct` | Nella colonna destra specificamente nelle pagine prodotto. | Visualizza un blocco di foto dei clienti o un link alla galleria nelle pagine prodotto. |
| `displayMyAccountBlockFooter` | Nella versione del footer del blocco "Il mio account". | Aggiunge un link alla sezione "Le mie foto" del cliente nel footer. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | (Potenziale) Potrebbe essere utilizzato per attivare un'email al cliente che incoraggia il caricamento di foto per i prodotti acquistati. |

## 5. Supporto ufficiale e aggiornamenti

Per il supporto ufficiale, gli aggiornamenti del modulo e qualsiasi ulteriore assistenza riguardante il modulo "Foto prodotti dei clienti", si prega di fare riferimento al proprio account cliente MyPresta.eu. È possibile accedere a [MyPresta.eu Cronologia ordini e download](https://mypresta.eu/my-account/orders/) per accedere alle ultime versioni e inviare ticket di supporto.
