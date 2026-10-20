---
title: "Galleria Fotografica Clienti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Galleria Fotografica Clienti di MyPresta.eu."
sidebar:
  label: "Galleria Fotografica Clienti - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Customer Photo Gallery su MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-photo-gallery.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/customer-photo-gallery/)
>
> ---


# Galleria Fotografica Clienti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e per qualsiasi interazione del modulo. Assicurati che il tuo server abbia spazio su disco sufficiente per archiviare le foto e i video caricati.

## 2. Panoramica Completa della Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo Galleria Fotografica Clienti, dove controlli tutte le sue funzionalità e come appare nel tuo negozio.

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- |
| **Consenti Caricamenti JPEG** | SÌ | **Cosa fa questa impostazione:** Controlla se i clienti possono caricare immagini in formato JPEG.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* I clienti possono caricare file .jpg e .jpeg.   *Quando disabilitato:* I file JPEG verranno rifiutati durante il caricamento.   **Valore consigliato:** SÌ (JPEG è un formato immagine molto comune).   **Scenario del commerciante:** Se desideri limitare i tipi di immagine per motivi specifici di qualità o branding, potresti disabilitare alcuni formati. |
| **Consenti Caricamenti GIF** | SÌ | **Cosa fa questa impostazione:** Controlla se i clienti possono caricare immagini in formato GIF.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* I clienti possono caricare file .gif.   *Quando disabilitato:* I file GIF verranno rifiutati.   **Valore consigliato:** SÌ (i GIF possono essere utili per animazioni semplici o sfondi trasparenti). |
| **Consenti Caricamenti PNG** | SÌ | **Cosa fa questa impostazione:** Controlla se i clienti possono caricare immagini in formato PNG.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* I clienti possono caricare file .png.   *Quando disabilitato:* I file PNG verranno rifiutati.   **Valore consigliato:** SÌ (PNG è eccellente per immagini con trasparenza e alta qualità). |
| **Consenti Caricamenti BMP** | NO | **Cosa fa questa impostazione:** Controlla se i clienti possono caricare immagini in formato BMP.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* I clienti possono caricare file .bmp.   *Quando disabilitato:* I file BMP verranno rifiutati.   **Valore consigliato:** NO (i file BMP sono tipicamente molto grandi e non compressi, non ideali per l'uso web).   **Scenario del commerciante:** Abilita solo se hai una necessità specifica di immagini non compresse, ma sii consapevole dell'impatto sullo spazio di archiviazione del server e sui tempi di caricamento della pagina. |
| **Abilita Paginazione** | SÌ | **Cosa fa questa impostazione:** Determina se le pagine della galleria utilizzeranno la paginazione (es. "Pagina 1 di 5").   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Il contenuto della galleria è diviso in più pagine, migliorando i tempi di caricamento per gallerie di grandi dimensioni.   *Quando disabilitato:* Tutto il contenuto della galleria si carica su una singola pagina, il che può essere lento per molte foto.   **Valore consigliato:** SÌ.   **Scenario del commerciante:** Essenziale per gestire gallerie di grandi dimensioni e fornire un'esperienza utente fluida. |
| **Consenti Caricamento Utenti Non Registrati** | NO | **Cosa fa questa impostazione:** Consente ai visitatori che non sono loggati in un account cliente di caricare foto.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Gli ospiti possono caricare foto. Questo può aumentare i contributi ma potrebbe anche portare a più spam o contenuti irrilevanti.   *Quando disabilitato:* Solo i clienti registrati possono caricare foto, garantendo un certo livello di responsabilità.   **Valore consigliato:** NO (a meno che tu non abbia una forte moderazione in atto).   **Scenario del commerciante:** Se vuoi massimizzare i contributi e sei preparato a moderare, abilita questa opzione. Altrimenti, mantienila disabilitata per mantenere il controllo qualità. |
| **Dimensione Massima File (MB)** | 5 | **Cosa fa questa impostazione:** Imposta la dimensione massima (in megabyte) per il caricamento di un singolo file immagine.   **Effetto della modifica di questa impostazione:**   *Quando impostato su un valore più alto:* I clienti possono caricare immagini più grandi, potenzialmente di qualità superiore, ma questo consuma più spazio sul server e larghezza di banda.   *Quando impostato su un valore più basso:* Limita la dimensione del file, risparmiando risorse del server ma potenzialmente limitando la qualità dell'immagine.   **Valore consigliato:** 5-10 MB è solitamente sufficiente per immagini ottimizzate per il web.   **Scenario del commerciante:** Bilancia la qualità dell'immagine con le risorse del server. Troppo basso, e i clienti potrebbero frustrarsi; troppo alto, e i costi di hosting potrebbero aumentare. |
| **Abilita Scheda Prodotto** | NO | **Cosa fa questa impostazione:** Visualizza una scheda dedicata "Foto Clienti" sulle pagine prodotto.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Una nuova scheda appare sulle pagine prodotto, mostrando foto specificamente correlate a quel prodotto.   *Quando disabilitato:* Nessuna scheda dedicata per le foto dei clienti sulle pagine prodotto.   **Valore consigliato:** SÌ (se vuoi mostrare UGC specifico del prodotto).   **Scenario del commerciante:** Ottimo per prodotti in cui le testimonianze visive sono molto efficaci, come moda o arredamento per la casa. |
| **Posizione Scheda Prodotto (Hook Modulo)** | displayProductExtraContent | **Cosa fa questa impostazione:** Determina dove la scheda prodotto è agganciata sulla pagina prodotto.   **Effetto della modifica di questa impostazione:** Cambia il posizionamento visivo della scheda "Foto Clienti" sulla pagina prodotto.   **Valore consigliato:** `displayProductExtraContent` o `displayProductTab`.   **Scenario del commerciante:** Prova diversi hook per trovare la migliore integrazione visiva con il tuo tema. |
| **Visualizza nel Piè di Pagina Prodotto** | NO | **Cosa fa questa impostazione:** Mostra un blocco di foto dei clienti nell'area del piè di pagina delle pagine prodotto.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Un piccolo blocco galleria appare in fondo alle pagine prodotto.   *Quando disabilitato:* Nessuna foto dei clienti nel piè di pagina della pagina prodotto.   **Valore consigliato:** NO (a meno che tu non abbia una specifica esigenza di design).   **Scenario del commerciante:** Può essere utilizzato per incoraggiare la navigazione o il cross-selling mostrando foto di clienti correlate. |
| **Visualizza nell'Account Cliente** | SÌ | **Cosa fa questa impostazione:** Aggiunge un link a "Le mie foto" nella dashboard dell'account del cliente.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* I clienti registrati vedono un link per gestire le loro foto caricate.   *Quando disabilitato:* I clienti non possono accedere facilmente alla loro area di gestione foto dal loro account.   **Valore consigliato:** SÌ.   **Scenario del commerciante:** Essenziale per i clienti per gestire i loro contributi. |
| **Visualizza nel Blocco Il Mio Account** | SÌ | **Cosa fa questa impostazione:** Aggiunge un link a "Le mie foto" nel blocco "Il mio account" (solitamente nella colonna sinistra/destra o nel piè di pagina).   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Un link appare nel blocco di accesso rapido "Il mio account".   *Quando disabilitato:* Nessun link nel blocco "Il mio account".   **Valore consigliato:** SÌ.   **Scenario del commerciante:** Fornisce un altro comodo punto di accesso per i clienti per gestire le loro foto. |
| **Altezza Miniatura (px)** | 100 | **Cosa fa questa impostazione:** Imposta l'altezza delle miniature generate per le immagini della galleria.   **Effetto della modifica di questa impostazione:**   *Quando impostato su un valore più alto:* Miniature più grandi, potenzialmente più chiare ma occupano più spazio.   *Quando impostato su un valore più basso:* Miniature più piccole, risparmiando spazio ma con meno dettagli.   **Valore consigliato:** 100-150px.   **Scenario del commerciante:** Regola per adattarsi al design del tuo tema e garantire un layout della galleria visivamente accattivante. |
| **Larghezza Miniatura (px)** | 100 | **Cosa fa questa impostazione:** Imposta la larghezza delle miniature generate per le immagini della galleria.   **Effetto della modifica di questa impostazione:**   *Quando impostato su un valore più alto:* Miniature più grandi.   *Quando impostato su un valore più basso:* Miniature più piccole.   **Valore consigliato:** 100-150px.   **Scenario del commerciante:** Regola per adattarsi al design del tuo tema e garantire un layout della galleria visivamente accattivante. |
| **Abilita Modulo Caricamento Foto** | SÌ | **Cosa fa questa impostazione:** Controlla la visibilità del modulo di caricamento foto sulla pagina della galleria.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* I clienti possono vedere e utilizzare il modulo di caricamento.   *Quando disabilitato:* Il modulo di caricamento è nascosto, impedendo nuovi contributi.   **Valore consigliato:** SÌ (a meno che tu non voglia temporaneamente interrompere i nuovi caricamenti).   **Scenario del commerciante:** Disabilita se stai organizzando un concorso con una scadenza per l'invio o hai bisogno di mettere in pausa i caricamenti per manutenzione. |
| **Visualizza Link Galleria** | SÌ | **Cosa fa questa impostazione:** Aggiunge un link alla pagina principale della galleria fotografica nella navigazione del tuo negozio.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Un link (es. "Galleria Clienti") appare nell'hook scelto.   *Quando disabilitato:* Il link alla pagina principale della galleria è nascosto.   **Valore consigliato:** SÌ.   **Scenario del commerciante:** Essenziale per i clienti per trovare e sfogliare la galleria. |
| **Visualizza nella Colonna Destra** | NO | **Cosa fa questa impostazione:** Mostra un blocco con le foto recenti dei clienti nella colonna destra del tuo negozio.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Un blocco appare nella colonna destra.   *Quando disabilitato:* Nessun blocco nella colonna destra.   **Valore consigliato:** NO (può ingombrare il layout, ma dipende dal tuo tema).   **Scenario del commerciante:** Utile se il tuo tema ha ampio spazio nella colonna destra e vuoi evidenziare i contributi recenti. |
| **Visualizza nella Colonna Sinistra** | NO | **Cosa fa questa impostazione:** Mostra un blocco con le foto recenti dei clienti nella colonna sinistra del tuo negozio.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Un blocco appare nella colonna sinistra.   *Quando disabilitato:* Nessun blocco nella colonna sinistra.   **Valore consigliato:** NO (può ingombrare il layout, ma dipende dal tuo tema).   **Scenario del commerciante:** Simile alla colonna destra, usa se il tuo tema lo supporta bene. |
| **Abilita Notifiche** | SÌ | **Cosa fa questa impostazione:** Invia notifiche email all'amministratore del negozio quando vengono caricate nuove foto.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Ricevi un'email per ogni nuovo caricamento, consentendo una rapida moderazione.   *Quando disabilitato:* Nessuna notifica email.   **Valore consigliato:** SÌ.   **Scenario del commerciante:** Cruciale per una moderazione tempestiva e per garantire che vengano visualizzati solo contenuti appropriati. |
| **Numero di Foto sulla Homepage** | 8 | **Cosa fa questa impostazione:** Imposta quante foto dei clienti vengono visualizzate nel blocco della homepage.   **Effetto della modifica di questa impostazione:** Cambia la quantità di foto mostrate sulla homepage.   **Valore consigliato:** 6-12, a seconda del layout della tua homepage.   **Scenario del commerciante:** Regola per adattarsi al design della tua homepage senza sovraccaricare la pagina. |
| **Ordine Foto Homepage** | Più Recenti Prima | **Cosa fa questa impostazione:** Determina l'ordine di smistamento delle foto visualizzate sulla homepage.   **Effetto della modifica di questa impostazione:** Le foto possono essere ordinate per più recenti, più vecchie, più popolari, ecc.   **Valore consigliato:** Più Recenti Prima o Più Popolari.   **Scenario del commerciante:** "Più Recenti Prima" mantiene i contenuti freschi; "Più Popolari" evidenzia i contenuti coinvolgenti. |
| **Abilita Modalità Concorso Fotografico** | NO | **Cosa fa questa impostazione:** Attiva le funzionalità per l'organizzazione di un concorso fotografico, potenzialmente inclusi meccanismi di voto e premi.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Potrebbero apparire opzioni aggiuntive relative al concorso, e la galleria potrebbe enfatizzare il voto.   *Quando disabilitato:* Modalità galleria standard.   **Valore consigliato:** NO (a meno che non si stia attivamente organizzando un concorso).   **Scenario del commerciante:** Utilizza questa opzione quando vuoi organizzare una campagna specifica per raccogliere foto e coinvolgere gli utenti con il voto. |
| **Escludi Prodotti dalla Galleria** | (ID Prodotto) | **Cosa fa questa impostazione:** Ti consente di specificare gli ID dei prodotti per i quali le foto dei clienti NON devono essere visualizzate sulle loro pagine prodotto.   **Effetto della modifica di questa impostazione:** Le foto per questi prodotti specifici non appariranno nella scheda/piè di pagina del prodotto, anche se l'impostazione principale della scheda prodotto è abilitata.   **Valore consigliato:** Lascia vuoto a meno che non sia necessario.   **Scenario del commerciante:** Se hai prodotti sensibili, o prodotti per i quali le foto dei clienti sono irrilevanti o inappropriate, puoi escluderli. |
| **Visibilità Link Account Cliente** | SÌ | **Cosa fa questa impostazione:** Controlla la visibilità del link "Le mie foto" all'interno della dashboard dell'account del cliente.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Il link è visibile.   *Quando disabilitato:* Il link è nascosto.   **Valore consigliato:** SÌ.   **Scenario del commerciante:** Mantieni abilitato per comodità del cliente. |
| **Visibilità Link Blocco Il Mio Account** | SÌ | **Cosa fa questa impostazione:** Controlla la visibilità del link "Le mie foto" all'interno del blocco "Il mio account" (es. nelle colonne).   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Il link è visibile.   *Quando disabilitato:* Il link è nascosto.   **Valore consigliato:** SÌ.   **Scenario del commerciante:** Mantieni abilitato per comodità del cliente. |
| **Abilita Voto per le Foto** | SÌ | **Cosa fa questa impostazione:** Consente ai clienti (e opzionalmente agli ospiti) di votare le foto caricate.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Appaiono pulsanti/stelle di voto accanto alle foto.   *Quando disabilitato:* Nessuna funzionalità di voto.   **Valore consigliato:** SÌ (aumenta il coinvolgimento).   **Scenario del commerciante:** Utilizza per identificare le foto popolari, organizzare concorsi o semplicemente incoraggiare l'interazione. |
| **Tipo di Sistema di Voto** | Stelle | **Cosa fa questa impostazione:** Sceglie lo stile visivo del sistema di voto (es. stelle, pollici su/giù).   **Effetto della modifica di questa impostazione:** Cambia l'aspetto del meccanismo di voto.   **Valore consigliato:** Stelle (generalmente più intuitivo).   **Scenario del commerciante:** Seleziona lo stile che meglio si adatta all'estetica del tuo negozio. |
| **Consenti Voto Utenti Non Registrati** | NO | **Cosa fa questa impostazione:** Consente ai visitatori che non sono registrati di votare le foto.   **Effetto della modifica di questa impostazione:**   *Quando abilitato:* Gli ospiti possono votare. Questo può aumentare la partecipazione ma potrebbe essere suscettibile di abusi.   *Quando disabilitato:* Solo i clienti registrati possono votare.   **Valore consigliato:** NO (per prevenire la manipolazione dei voti).   **Scenario del commerciante:** Abilita solo se dai priorità alla massima partecipazione rispetto alla stretta integrità del voto. |

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | CG\_ALLOW\_JPEG | SÌ | Consenti caricamenti di immagini JPEG. |
| Configurazione Modulo | CG\_ALLOW\_GIF | SÌ | Consenti caricamenti di immagini GIF. |
| Configurazione Modulo | CG\_ALLOW\_PNG | SÌ | Consenti caricamenti di immagini PNG. |
| Configurazione Modulo | CG\_ALLOW\_BMP | NO | Consenti caricamenti di immagini BMP (file grandi). |
| Configurazione Modulo | CG\_PAGINATION | SÌ | Abilita paginazione per le pagine della galleria. |
| Configurazione Modulo | CG\_ALLOW\_UNLOGGED | NO | Consenti agli ospiti di caricare foto. |
| Configurazione Modulo | CG\_MAX\_FILE\_SIZE | 5 MB | Dimensione massima file per i caricamenti. |
| Configurazione Modulo | CG\_PRODUCTTAB | NO | Visualizza le foto dei clienti in una scheda prodotto. |
| Configurazione Modulo | cg\_productTabM | displayProductExtraContent | Hook per il posizionamento della scheda prodotto. |
| Configurazione Modulo | CG\_PRODUCTFOOTER | NO | Visualizza le foto nel piè di pagina del prodotto. |
| Configurazione Modulo | CG\_CUSTOMERACCOUNT | SÌ | Mostra il link "Le mie foto" nell'account cliente. |
| Configurazione Modulo | CG\_MYACCOUNTBLOCK | SÌ | Mostra il link "Le mie foto" nel blocco Il mio account. |
| Configurazione Modulo | CG\_THUMBHEIGHT | 100 | Altezza delle miniature generate. |
| Configurazione Modulo | CG\_THUMBWIDTH | 100 | Larghezza delle miniature generate. |
| Configurazione Modulo | CG\_FUPLOADON | SÌ | Abilita il modulo di caricamento foto. |
| Configurazione Modulo | CG\_GALLERY | SÌ | Visualizza il link alla pagina principale della galleria. |
| Configurazione Modulo | CG\_RIGHTCOL | NO | Visualizza le foto nella colonna destra. |
| Configurazione Modulo | CG\_LEFTCOL | NO | Visualizza le foto nella colonna sinistra. |
| Configurazione Modulo | CG\_NTF | SÌ | Invia notifiche email all'amministratore per i nuovi caricamenti. |
| Configurazione Modulo | cg\_hpg\_nb | 8 | Numero di foto sulla homepage. |
| Configurazione Modulo | cg\_hpg\_o | Più Recenti Prima | Ordine delle foto sulla homepage. |
| Configurazione Modulo | cg\_contest | NO | Abilita la modalità concorso fotografico. |
| Configurazione Modulo | cg\_excludeproduct | (vuoto) | ID prodotto da escludere dalla galleria. |
| Configurazione Modulo | CG\_CUSTOMERACCOUNTV | SÌ | Visibilità del link "Le mie foto" nell'account cliente. |
| Configurazione Modulo | CG\_MYACCOUNTBLOCKV | SÌ | Visibilità del link "Le mie foto" nel blocco Il mio account. |
| Configurazione Modulo | CG\_voting | SÌ | Abilita il voto per le foto. |
| Configurazione Modulo | CG\_VOTE\_STAR | Stelle | Stile visivo del sistema di voto. |
| Configurazione Modulo | cg\_unl\_voting | NO | Consenti agli utenti non registrati di votare. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Le mie foto caricate non appaiono nella galleria.**
**R:**

-   **Controlla la Configurazione del Modulo:** Assicurati che "Abilita Modulo Caricamento Foto" (`CG_FUPLOADON`) sia impostato su SÌ.
-   **Tipo e Dimensione del File:** Verifica che il tipo di file caricato (JPEG, PNG, GIF, BMP) sia consentito nelle impostazioni del modulo e che la dimensione del file rientri nel limite di "Dimensione Massima File" (`CG_MAX_FILE_SIZE`).
-   **Moderazione:** Il modulo potrebbe avere una coda di moderazione interna (anche se non esplicitamente elencata come impostazione, molti moduli galleria lo fanno). Controlla se esiste una sezione amministrativa per approvare/rifiutare le foto.
-   **Permessi:** Assicurati che la directory `img/customersgallery/` (o un percorso simile dove le immagini sono archiviate) sul tuo server abbia i permessi di scrittura (solitamente 755 o 777, anche se 777 è meno sicuro).
-   **Svuota Cache:** Vai su **Parametri Avanzati > Prestazioni** nel tuo Back Office di PrestaShop e svuota la cache di Smarty, la cache del browser e la cache del modulo.

**D2: Il link o il blocco della galleria non appare nel mio negozio.**
**R:**

-   **Hook del Modulo:** Controlla la pagina di configurazione del modulo. Assicurati che "Visualizza Link Galleria" (`CG_GALLERY`), "Visualizza nella Colonna Destra" (`CG_RIGHTCOL`), "Visualizza nella Colonna Sinistra" (`CG_LEFTCOL`), ecc., siano abilitati per le posizioni che ti aspetti.
-   **Gestione Hook:** Vai su **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti) nel tuo Back Office di PrestaShop. Cerca il modulo ("Galleria Fotografica Clienti") e assicurati che sia agganciato alle posizioni `display` corrette (es. `displayHeader`, `displayHome`, `displayRightColumn`). Se non lo è, "Trapianta un modulo" all'hook desiderato.
-   **Compatibilità del Tema:** Alcuni temi personalizzati potrebbero sovrascrivere le posizioni degli hook standard. Se il modulo non appare nonostante sia agganciato correttamente, potrebbe richiedere piccole modifiche al tema. Contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu.
-   **Svuota Cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alle posizioni o alle impostazioni del modulo.

**D3: Le foto sulle pagine prodotto non appaiono in una scheda.**
**R:**

-   **Abilita Scheda Prodotto:** Assicurati che `CG_PRODUCTTAB` sia impostato su SÌ nella configurazione del modulo.
-   **Hook Scheda Prodotto:** Verifica che `cg_productTabM` sia impostato su un hook appropriato come `displayProductExtraContent` o `displayProductTab`.
-   **Esclusione Prodotto:** Controlla `cg_excludeproduct` per assicurarti che il prodotto che stai visualizzando non sia elencato lì.
-   **Foto Associate:** Assicurati che ci siano effettivamente foto caricate e associate a quel prodotto specifico.
-   **Svuota Cache:** Svuota tutte le cache.

**D4: Il sistema di voto non funziona o non è visibile.**
**R:**

-   **Abilita Voto:** Assicurati che "Abilita Voto per le Foto" (`CG_voting`) sia impostato su SÌ.
-   **Utenti Non Registrati:** Se gli ospiti non possono votare, controlla "Consenti Voto Utenti Non Registrati" (`cg_unl_voting`).
-   **Conflitti CSS:** A volte, il CSS del tema può nascondere o distorcere gli elementi del modulo. Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare l'area e verificare la presenza di stili in conflitto.
-   **Errori JavaScript:** Controlla la console del tuo browser (F12 > scheda Console) per eventuali errori JavaScript che potrebbero impedire il funzionamento della funzionalità di voto.

**D5: Come traduco il testo del modulo in altre lingue?**
**R:**

-   Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
-   Seleziona "Traduzioni dei moduli installati".
-   Scegli il tuo tema, la lingua in cui vuoi tradurre, quindi seleziona "Galleria Fotografica Clienti" dall'elenco dei moduli.
-   Potrai quindi tradurre tutte le stringhe del front-office e del back-office del modulo.
-   Ricorda di salvare le modifiche e svuotare la cache.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo Galleria Fotografica Clienti segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente i Front Controller per l'interazione con l'utente e i template Smarty per il rendering. Si integra con vari hook di visualizzazione per incorporare le funzionalità della galleria in tutto il negozio. Sebbene non definisca esplicitamente classi `ObjectModel` personalizzate nell'inventario fornito, probabilmente utilizza `Configuration` per le impostazioni e interagisce direttamente con il database per l'archiviazione e la gestione di foto/video. AJAX viene utilizzato per il caricamento dinamico dei contenuti e per interazioni come il voto.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono tutte le interazioni rivolte al cliente e l'elaborazione dei dati per la galleria.

-   **`customersgallery/controllers/front/ajax.php`**

    -   **Nome Classe:** `CustomersGalleryAjaxModuleFrontController` (probabilmente estende `ModuleFrontController`)
    -   **Responsabilità:** Questo controller è la spina dorsale per le interazioni dinamiche senza ricaricamenti completi della pagina. Gestisce le richieste AJAX per azioni come:
        -   Invio di nuove foto/video.
        -   Elaborazione dei voti (es. valutazioni a stelle).
        -   Caricamento di più elementi della galleria (paginazione/scorrimento infinito).
        -   Potenzialmente azioni di moderazione se un utente non registrato carica e richiede approvazione.
        -   Restituisce risposte JSON al JavaScript lato client.
-   **`customersgallery/controllers/front/gallery.php`**

    -   **Nome Classe:** `CustomersGalleryGalleryModuleFrontController` (probabilmente estende `ModuleFrontController`)
    -   **Responsabilità:** Questo controller è responsabile della visualizzazione della pagina principale della galleria di foto e video dei clienti.
        -   Recupera tutte le foto/video approvati dal database.
        -   Applica la logica di paginazione basata sulle impostazioni del modulo (`CG_PAGINATION`).
        -   Prepara i dati per il template `gallery.tpl`, inclusi percorsi immagine, titoli, descrizioni e dati di voto.
        -   Gestisce l'ordinamento (es. per più recenti, più popolari).
-   **`customersgallery/controllers/front/index.php`**

    -   **Nome Classe:** `CustomersGalleryIndexModuleFrontController` (probabilmente estende `ModuleFrontController`)
    -   **Responsabilità:** Questo controller potrebbe fungere da punto di ingresso predefinito o da reindirizzatore per la sezione front-office del modulo. Potrebbe anche essere utilizzato per una semplice pagina di destinazione o per reindirizzare alla galleria principale. In molti moduli, `index.php` in una directory di controller frontale è un fallback o un semplice reindirizzamento alla funzionalità principale.
-   **`customersgallery/controllers/front/myphotos.php`**

    -   **Nome Classe:** `CustomersGalleryMyPhotosModuleFrontController` (probabilmente estende `ModuleFrontController`)
    -   **Responsabilità:** Questo controller gestisce la sezione "Le mie foto" all'interno dell'account di un cliente.
        -   Autentica il cliente registrato.
        -   Recupera tutte le foto caricate dal cliente corrente.
        -   Consente ai clienti di visualizzare, modificare (es. titolo, descrizione) o eliminare i propri contributi.
        -   Prepara i dati per il template `my-photos.tpl`.
-   **`customersgallery/controllers/front/myvideos.php`**

    -   **Nome Classe:** `CustomersGalleryMyVideosModuleFrontController` (probabilmente estende `ModuleFrontController`)
    -   **Responsabilità:** Simile a `myphotos.php`, ma specificamente per la gestione dei video caricati dal cliente corrente.
        -   Autentica il cliente registrato.
        -   Recupera tutti i video caricati dal cliente corrente.
        -   Consente ai clienti di visualizzare, modificare o eliminare i propri contributi video.
        -   Prepara i dati per il template `my-videos-16.tpl`.

#### Controller Admin Back-Office

Il dossier del modulo non indica controller Admin dedicati. Tutta la configurazione del back-office è gestita tramite il metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo probabilmente gestisce i suoi dati direttamente all'interno del file `customersgallery.php` o utilizza metodi generici di interazione con il database di PrestaShop.

-   **Archiviazione Dati:** I metadati di foto e video (percorsi, titoli, ID utente, ID prodotto, stato di approvazione, voti) sono probabilmente archiviati in tabelle di database personalizzate create durante l'installazione del modulo. Il file PHP principale del modulo (`customersgallery.php`) conterrebbe le query SQL per queste tabelle.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`customersgallery/js/customersgallery.js`**

    -   **Ambito:** Front-office.
    -   **Dettaglio:** Questo è probabilmente il file JavaScript personalizzato principale per la galleria. Contenerebbe:
        -   Listener di eventi per il caricamento di foto/video (es. invio di moduli, modifiche all'input del file).
        -   Chiamate AJAX a `ajax.php` per caricamenti, votazioni e caricamento di più contenuti.
        -   Validazione lato client per tipi e dimensioni dei file.
        -   Aggiornamenti dinamici alla visualizzazione della galleria (es. aggiunta di nuove foto senza aggiornamento della pagina).
        -   Interazione con la libreria Fancybox per lightbox di immagini.
-   **`customersgallery/js/fancybox.js`**

    -   **Ambito:** Front-office.
    -   **Dettaglio:** Una libreria di terze parti (Fancybox) per creare lightbox eleganti e reattivi per immagini e multimedia. Questo script abilita la funzionalità "clicca per ingrandire" per le foto della galleria.
-   **`customersgallery/js/script.js`**

    -   **Ambito:** Front-office.
    -   **Dettaglio:** Questo potrebbe essere uno script di utilità generale o uno script legacy. Potrebbe contenere:
        -   Funzioni di supporto per le interazioni dell'interfaccia utente.
        -   Gestori di eventi aggiuntivi non specifici della logica principale della galleria.
        -   Potenzialmente script relativi al meccanismo di voto o ad altri elementi interattivi.
-   **`customersgallery/lib/voucherengine/script.js`**

    -   **Ambito:** Front-office.
    -   **Dettaglio:** Questo suggerisce l'integrazione con un "motore di voucher" o un sistema di ricompensa simile. Questo script gestirebbe:
        -   Logica per l'assegnazione di voucher o sconti in caso di successo nell'invio di foto/video (se `cg_contest` è abilitato o è in atto un sistema di ricompensa simile).
        -   Chiamate AJAX per attivare la generazione o l'applicazione di voucher.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   **`customersgallery/css/customersgallery.css`**

    -   **Ambito:** Front-office (stile principale della galleria).
    -   **Dettaglio:** Contiene le regole CSS principali per il layout, l'aspetto e la reattività della galleria fotografica dei clienti, inclusi:
        -   Layout a griglia per la visualizzazione delle foto.
        -   Stile per miniature, didascalie e informazioni utente.
        -   Stili per il modulo di caricamento e la paginazione.
        -   Regolazioni reattive per diverse dimensioni dello schermo.
    -   **Selettori Chiave:** `.customer-gallery-container`, `.gallery-item`, `.gallery-thumbnail`, `.upload-form`, `.pagination`.
-   **`customersgallery/css/fancybox.css`**

    -   **Ambito:** Front-office.
    -   **Dettaglio:** Foglio di stile per la libreria lightbox Fancybox, che controlla l'aspetto delle immagini ingrandite, delle frecce di navigazione, del pulsante di chiusura e dell'overlay.
    -   **Selettori Chiave:** `.fancybox-container`, `.fancybox-image`, `.fancybox-caption`.
-   **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**

    -   **Ambito:** Front-office.
    -   **Dettaglio:** Questi sono diversi temi di colore per il sistema di voto basato su stelle (`CG_VOTE_STAR`). `star.css` è probabilmente lo stile di base, e gli altri forniscono override di colore.
    -   **Selettori Chiave:** `.star-rating`, `.star-rating-control`, `.star-rating-star`.
-   **`customersgallery/lib/voucherengine/ps16.css`**

    -   **Ambito:** Front-office.
    -   **Dettaglio:** Questo foglio di stile è specifico per l'integrazione del "motore di voucher", probabilmente fornisce lo stile per qualsiasi elemento relativo alla visualizzazione o alla notifica dei voucher, potenzialmente con override specifici per i temi di PrestaShop 1.6.

### 4.6 Struttura dei Template Smarty (`views/templates/`)

#### Template Personalizzati (`views/templates/custom/`)

Questi sono probabilmente moduli o componenti specifici.

-   **`customersgallery/views/templates/custom/upload-form.tpl`**
    -   **Scopo:** Renderizza il modulo HTML per i clienti per caricare foto.
    -   **Variabili:** Probabilmente include campi per l'input del file, titolo, descrizione e potenzialmente associazione del prodotto.
-   **`customersgallery/views/templates/custom/upload-form2.tpl`**
    -   **Scopo:** Potrebbe essere una versione alternativa o aggiornata del modulo di caricamento, possibilmente per caricamenti video o un layout diverso.

#### Template Front-Office (`views/templates/front/`)

Questi template renderizzano le pagine principali della galleria e i contenuti specifici dell'utente.

-   **`customersgallery/views/templates/front/gallery.tpl`**
    -   **Scopo:** Template principale per la visualizzazione della galleria di foto e video dei clienti.
    -   **Variabili:** Cicla attraverso gli array `$photos` e `$videos`, visualizzando miniature, titoli ed elementi di voto. Include la paginazione.
-   **`customersgallery/views/templates/front/gallery2.tpl`**
    -   **Scopo:** Potrebbe essere un layout di galleria alternativo o una vista specifica per i concorsi.
-   **`customersgallery/views/templates/front/gallery3.tpl`**
    -   **Scopo:** Un altro layout di galleria alternativo.
-   **`customersgallery/views/templates/front/menu.tpl`**
    -   **Scopo:** Renderizza un menu di navigazione specifico per la galleria, potenzialmente con link a "Le mie foto", "I miei video", "Carica", ecc.
-   **`customersgallery/views/templates/front/my-photos.tpl`**
    -   **Scopo:** Visualizza l'elenco delle foto caricate dal cliente attualmente registrato, con opzioni per modificare o eliminare.
    -   **Variabili:** Array `$customer_photos`.
-   **`customersgallery/views/templates/front/my-videos-16.tpl`**
    -   **Scopo:** Visualizza l'elenco dei video caricati dal cliente attualmente registrato, specificamente progettato per la compatibilità con PrestaShop 1.6.
    -   **Variabili:** Array `$customer_videos`.
-   **`customersgallery/views/templates/front/video-upload.tpl`**
    -   **Scopo:** Renderizza un modulo specificamente per il caricamento di video, distinto dal modulo di caricamento foto.

#### Template Hook (`views/templates/hook/`)

Questi template sono progettati per essere renderizzati all'interno di specifici hook di PrestaShop.

-   **`customersgallery/views/templates/hook/column-link.tpl`**
    -   **Hook:** `displayLeftColumn`, `displayRightColumn`
    -   **Scopo:** Renderizza un blocco nella colonna sinistra o destra con un link alla pagina principale della galleria o a poche foto recenti.
-   **`customersgallery/views/templates/hook/customer-my-account.tpl`**
    -   **Hook:** `displayCustomerAccount`
    -   **Scopo:** Aggiunge un link o un blocco all'interno della dashboard dell'account del cliente, tipicamente collegandosi a "Le mie foto" o "I miei video".
-   **`customersgallery/views/templates/hook/hookHome.tpl`**
    -   **Hook:** `displayHome`
    -   **Scopo:** Visualizza un blocco di foto recenti o popolari dei clienti sulla homepage del negozio.
    -   **Variabili:** Array `$homepage_photos`.
-   **`customersgallery/views/templates/hook/my-account.tpl`**
    -   **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
    -   **Scopo:** Aggiunge un link a "Le mie foto" all'interno del blocco "Il mio account", spesso trovato nelle colonne laterali o nel piè di pagina.
-   **`customersgallery/views/templates/hook/productfooter.tpl`**
    -   **Hook:** `displayProductFooter`
    -   **Scopo:** Renderizza un blocco di foto dei clienti relative al prodotto corrente nel piè di pagina della pagina prodotto.
-   **`customersgallery/views/templates/hook/tab.tpl`**
    -   **Hook:** `displayProductTab`, `displayProductExtraContent`
    -   **Scopo:** Renderizza l'intestazione della scheda "Foto Clienti" su una pagina prodotto.
-   **`customersgallery/views/templates/hook/tabContents.tpl`**
    -   **Hook:** `displayProductTabContent`, `displayProductExtraContent`
    -   **Scopo:** Renderizza il contenuto effettivo (la galleria di foto) all'interno della scheda "Foto Clienti" su una pagina prodotto.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Il modulo probabilmente crea tabelle personalizzate durante l'installazione. Basandosi sulla funzionalità, queste includerebbero:

-   **`ps_customersgallery_photos`**:

    -   `id_photo` (PRIMARY KEY, INT)
    -   `id_customer` (INT, FK a `ps_customer`)
    -   `id_product` (INT, FK a `ps_product`, NULLABLE)
    -   `filename` (VARCHAR, percorso al file immagine)
    -   `title` (VARCHAR)
    -   `description` (TEXT)
    -   `date_add` (DATETIME)
    -   `active` (TINYINT, per lo stato di moderazione)
    -   `votes` (INT, voti totali)
    -   `rating` (DECIMAL, valutazione media)
-   **`ps_customersgallery_videos`**:

    -   `id_video` (PRIMARY KEY, INT)
    -   `id_customer` (INT, FK a `ps_customer`)
    -   `id_product` (INT, FK a `ps_product`, NULLABLE)
    -   `url` (VARCHAR, per link video esterni come YouTube/Vimeo)
    -   `title` (VARCHAR)
    -   `description` (TEXT)
    -   `date_add` (DATETIME)
    -   `active` (TINYINT)
-   **`ps_customersgallery_votes`**:

    -   `id_vote` (PRIMARY KEY, INT)
    -   `id_photo` (INT, FK a `ps_customersgallery_photos`)
    -   `id_customer` (INT, FK a `ps_customer`, NULLABLE per voti non registrati)
    -   `ip_address` (VARCHAR, per voti non registrati e prevenzione abusi)
    -   `vote_value` (INT, es. 1-5 per le stelle)
    -   `date_add` (DATETIME)
-   **`ps_configuration`**: Le impostazioni del modulo (es. `CG_ALLOW_JPEG`, `CG_MAX_FILE_SIZE`, `CG_PAGINATION`) sono archiviate qui.

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayProductExtraContent` | Renderizza contenuto aggiuntivo sulla pagina prodotto, spesso usato per le schede. | Visualizza la scheda "Foto Clienti" e il suo contenuto sulle pagine prodotto. |
| `displayRightColumnProduct` | Renderizza contenuto nella colonna destra di una pagina prodotto. | Visualizza un blocco di foto dei clienti specifiche del prodotto nella colonna destra. |
| `displayCustomerAccount` | Renderizza contenuto all'interno della dashboard "Il mio account" del cliente. | Aggiunge un link o un blocco a "Le mie foto" e "I miei video" per il cliente registrato. |
| `displayRightColumn` | Renderizza contenuto nella colonna destra delle pagine generali del negozio. | Visualizza un blocco di foto recenti dei clienti nella colonna destra. |
| `displayMyAccountBlockFooter` | Renderizza contenuto nel piè di pagina del blocco "Il mio account". | Aggiunge un link a "Le mie foto" nel blocco "Il mio account", spesso nel piè di pagina. |
| `displayProductFooter` | Renderizza contenuto nell'area del piè di pagina di una pagina prodotto. | Visualizza un blocco di foto dei clienti specifiche del prodotto nel piè di pagina del prodotto. |
| `displayProductTabContent` | Renderizza il contenuto di una scheda prodotto. | Visualizza il contenuto della galleria all'interno della scheda "Foto Clienti" sulle pagine prodotto. |
| `displayLeftColumnProduct` | Renderizza contenuto nella colonna sinistra di una pagina prodotto. | Visualizza un blocco di foto dei clienti specifiche del prodotto nella colonna sinistra. |
| `displayLeftColumn` | Renderizza contenuto nella colonna sinistra delle pagine generali del negozio. | Visualizza un blocco di foto recenti dei clienti nella colonna sinistra. |
| `displayHome` | Renderizza contenuto sulla homepage del negozio. | Visualizza un blocco di foto recenti o popolari dei clienti sulla homepage. |
| `displayHeader` | Renderizza contenuto nella sezione `<head>` di tutte le pagine. | Inietta file CSS e JavaScript richiesti dal modulo in tutto il negozio. |
| `displayMyAccountBlock` | Renderizza contenuto all'interno del blocco "Il mio account" (es. nelle colonne laterali). | Aggiunge un link a "Le mie foto" nel blocco "Il mio account". |
| `displayProductTab` | Renderizza l'intestazione della scheda per una scheda pagina prodotto. | Visualizza il titolo della scheda "Foto Clienti" sulle pagine prodotto. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto professionale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire il buon funzionamento e il miglioramento continuo dei tuoi moduli PrestaShop.
