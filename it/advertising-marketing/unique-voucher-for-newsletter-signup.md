---
title: "Buono unico per iscrizione newsletter - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Buono unico per iscrizione newsletter' di MyPresta.eu."
sidebar:
  label: "Buono unico per iscrizione newsletter - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Unique voucher for newsletter signup su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/unique-voucher-for-newsletter-signup.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/unique-voucher-for-newsletter-signup/)
>
> ---


# Buono unico per iscrizione newsletter

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni server speciali oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedervi, naviga su **Moduli > Gestione moduli**, cerca "Buono unico per iscrizione newsletter" e clicca su "Configura".

Questa schermata ti permette di definire il comportamento principale dei buoni generati per le iscrizioni alla newsletter.

- **Cosa fa questa impostazione:** Questa sezione contiene le impostazioni principali per come i tuoi buoni unici verranno creati e consegnati.
- **Effetto della modifica di questa impostazione:** La regolazione di questi valori influisce direttamente sull'importo dello sconto, sulle condizioni e sulla validità dei buoni che i tuoi nuovi iscritti alla newsletter riceveranno.

**Impostazioni e Opzioni:**

1. **Valore del buono (importo o percentuale)**

   - **Cosa fa questa impostazione:** Definisce l'importo o la percentuale di sconto che il buono unico fornirà.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su un importo specifico (es. "10"):* Il buono darà uno sconto monetario fisso (es. 10 € di sconto).
     - *Se impostato su una percentuale (es. "15%"):* Il buono darà uno sconto percentuale sul totale dell'ordine.
   - **Valore consigliato:** Dipende dalla tua strategia di prezzo. Una pratica comune è il 5-15% o un importo fisso come 5-10 € per gli acquisti iniziali.
   - **Scenario / esempio per il commerciante:** Vuoi offrire uno sconto di 5 € ai nuovi iscritti. Inseriresti "5" qui. Se preferisci uno sconto del 10%, inseriresti "10%".
2. **Importo minimo**

   - **Cosa fa questa impostazione:** Imposta il totale minimo dell'ordine (prima della spedizione) richiesto affinché il buono sia valido.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su "0" o lasciato vuoto:* Il buono può essere utilizzato su qualsiasi ordine, indipendentemente dal suo valore totale.
     - *Se impostato su un valore (es. "50"):* Il totale del carrello del cliente deve essere di almeno 50 € affinché il buono sia applicabile.
   - **Valore consigliato:** Imposta un importo minimo se vuoi garantire un certo valore dell'ordine, oppure lascialo a "0" se vuoi incoraggiare qualsiasi acquisto.
   - **Scenario / esempio per il commerciante:** Per evitare che i clienti utilizzino un buono di 10 € su un articolo da 5 €, potresti impostare un importo minimo di "30".
3. **Validità del buono (giorni)**

   - **Cosa fa questa impostazione:** Determina quanti giorni il buono unico sarà valido dal momento in cui viene generato e inviato al cliente.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su "0" o lasciato vuoto:* Il buono non avrà una data di scadenza (non consigliato, in quanto rimuove l'urgenza).
     - *Se impostato su un valore (es. "30"):* Il buono scadrà 30 giorni dopo che il cliente lo ha ricevuto.
   - **Valore consigliato:** 7, 14 o 30 giorni sono comuni per creare urgenza senza essere troppo restrittivi.
   - **Scenario / esempio per il commerciante:** Per incoraggiare acquisti immediati, potresti impostare la validità a "7" giorni, spingendo i clienti a utilizzare il buono rapidamente.
4. **Descrizione del buono**

   - **Cosa fa questa impostazione:** Questo testo apparirà come descrizione del buono generato nel carrello del cliente e nel Back Office.
   - **Effetto della modifica di questa impostazione:** Aiuta i clienti a capire a cosa serve il buono e fornisce contesto per i tuoi registri interni.
   - **Valore consigliato:** "Sconto Iscrizione Newsletter" o "Buono di Benvenuto per Iscritti Newsletter".
   - **Scenario / esempio per il commerciante:** Inserire "Sconto di Benvenuto per Iscritti Newsletter" comunica chiaramente lo scopo del buono.
5. **Prefisso del buono**

   - **Cosa fa questa impostazione:** Ti permette di aggiungere un prefisso personalizzato ai codici voucher unici generati dal modulo.
   - **Effetto della modifica di questa impostazione:**
     - *Se lasciato vuoto:* I codici voucher saranno puramente casuali (es. "ABCDEF123").
     - *Se impostato un prefisso (es. "NEWSLETTER-"):* I codici voucher inizieranno con questo prefisso (es. "NEWSLETTER-ABCDEF123"). Questo ti aiuta a identificare la fonte del buono.
   - **Valore consigliato:** "NEWSLETTER-" o "WELCOME-".
   - **Scenario / esempio per il commerciante:** L'utilizzo di "NEWSLETTER-" ti aiuta a identificare rapidamente quali buoni provengono dalle iscrizioni alla newsletter quando esamini ordini o statistiche.
6. **Escludi prodotti con categorie specifiche**

   - **Cosa fa questa impostazione:** Ti permette di selezionare categorie di prodotti specifiche per le quali il buono NON sarà applicabile.
   - **Effetto della modifica di questa impostazione:**
     - *Se non sono selezionate categorie:* Il buono può essere utilizzato su qualsiasi prodotto del tuo negozio.
     - *Se sono selezionate categorie (es. "Articoli in saldo", "Carte regalo"):* Il buono non può essere utilizzato per acquistare prodotti di queste categorie.
   - **Valore consigliato:** Usalo se hai prodotti a basso margine, carte regalo o articoli promozionali specifici che non vuoi scontare ulteriormente.
   - **Scenario / esempio per il commerciante:** Non vuoi che il buono si applichi agli articoli "In saldo" già scontati. Selezioneresti la categoria "In saldo" qui.
7. **Escludi prodotti con produttori specifici**

   - **Cosa fa questa impostazione:** Simile alle categorie, ti permette di escludere prodotti di produttori specifici dallo sconto del buono.
   - **Effetto della modifica di questa impostazione:**
     - *Se non sono selezionati produttori:* Il buono si applica a tutti i produttori.
     - *Se sono selezionati produttori (es. "Brand X"):* I prodotti di "Brand X" non possono essere acquistati con il buono.
   - **Valore consigliato:** Utile se hai marchi esclusivi o marchi con politiche di prezzo rigide.
   - **Scenario / esempio per il commerciante:** Un particolare marchio di lusso "Luxury Watches Inc." non consente sconti. Selezioneresti "Luxury Watches Inc." qui.
8. **Escludi prodotti con fornitori specifici**

   - **Cosa fa questa impostazione:** Ti permette di escludere prodotti di fornitori specifici dallo sconto del buono.
   - **Effetto della modifica di questa impostazione:**
     - *Se non sono selezionati fornitori:* Il buono si applica a tutti i fornitori.
     - *Se sono selezionati fornitori (es. "Fornitore Y"):* I prodotti di "Fornitore Y" non possono essere acquistati con il buono.
   - **Valore consigliato:** Meno comune per promozioni rivolte ai clienti, ma utile per l'inventario interno o accordi specifici con i fornitori.
   - **Scenario / esempio per il commerciante:** Hai un fornitore "Elettronica all'ingrosso" i cui prodotti sono già a prezzi stracciati. Potresti escluderli da ulteriori sconti.
9. **Escludi prodotti con attributi specifici**

   - **Cosa fa questa impostazione:** Ti permette di escludere prodotti con combinazioni di attributi specifiche (es. "Colore: Rosso", "Taglia: XL") dallo sconto.
   - **Effetto della modifica di questa impostazione:**
     - *Se non sono selezionati attributi:* Il buono si applica a tutti gli attributi del prodotto.
     - *Se sono selezionati attributi:* I prodotti che corrispondono a questi attributi non possono essere scontati.
   - **Valore consigliato:** Usalo per varianti di prodotto molto specifiche che desideri escludere.
   - **Scenario / esempio per il commerciante:** Hai una variante "Oro" in edizione limitata di un prodotto che non sconti mai. Selezioneresti l'attributo "Colore: Oro" qui.
10. **Escludi prodotti con caratteristiche specifiche**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base alle loro caratteristiche (es. "Materiale: Pelle", "Impermeabile: Sì").
    - **Effetto della modifica di questa impostazione:**
      - *Se non sono selezionate caratteristiche:* Il buono si applica a tutte le caratteristiche del prodotto.
      - *Se sono selezionate caratteristiche:* I prodotti che corrispondono a queste caratteristiche non possono essere scontati.
    - **Valore consigliato:** Simile agli attributi, per caratteristiche di prodotto specifiche.
    - **Scenario / esempio per il commerciante:** Vendi articoli fatti a mano con la caratteristica "Fatto a mano: Sì" e vuoi escluderli dagli sconti.
11. **Escludi prodotti con fasce di prezzo specifiche**

    - **Cosa fa questa impostazione:** Ti permette di definire una fascia di prezzo per i prodotti che dovrebbero essere esclusi dallo sconto del buono.
    - **Effetto della modifica di questa impostazione:**
      - *Se non è impostata alcuna fascia:* Tutti i prezzi dei prodotti sono idonei.
      - *Se è impostata una fascia (es. "0-10" o "500-9999"):* I prodotti che rientrano in questa fascia di prezzo non saranno scontati dal buono.
    - **Valore consigliato:** Usalo per proteggere articoli a margine molto basso o articoli di valore molto elevato dallo sconto.
    - **Scenario / esempio per il commerciante:** Non vuoi che il buono si applichi agli articoli con un prezzo inferiore a 10 €, quindi imposti la fascia "0-10".
12. **Escludi prodotti con fasce di peso specifiche**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base alla loro fascia di peso.
    - **Effetto della modifica di questa impostazione:**
      - *Se non è impostata alcuna fascia:* Tutti i pesi dei prodotti sono idonei.
      - *Se è impostata una fascia (es. "0-0.5kg" o "10kg-999kg"):* I prodotti che rientrano in questa fascia di peso non saranno scontati.
    - **Valore consigliato:** Meno comune per le regole di sconto, ma potrebbe essere utile per considerazioni specifiche sui costi di spedizione.
    - **Scenario / esempio per il commerciante:** Potresti escludere articoli molto pesanti che già comportano costi di spedizione elevati da ulteriori sconti.
13. **Escludi prodotti con dimensioni specifiche**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base alle loro dimensioni (larghezza, altezza, profondità).
    - **Effetto della modifica di questa impostazione:**
      - *Se non sono impostate dimensioni:* Tutte le dimensioni dei prodotti sono idonee.
      - *Se sono impostate dimensioni:* I prodotti che rientrano in queste fasce di dimensioni non saranno scontati.
    - **Valore consigliato:** Simile al peso, tipicamente per considerazioni specifiche sulla spedizione o sull'imballaggio.
    - **Scenario / esempio per il commerciante:** Potresti escludere articoli di grandi dimensioni che richiedono un imballaggio speciale dagli sconti.
14. **Escludi prodotti con ID prodotto specifici**

    - **Cosa fa questa impostazione:** Ti permette di inserire manualmente un elenco separato da virgole di ID prodotto specifici che dovrebbero essere esclusi dallo sconto del buono.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti i prodotti sono idonei.
      - *Se vengono inseriti ID (es. "123, 456, 789"):* Questi prodotti specifici non saranno scontati.
    - **Valore consigliato:** Usalo per singoli prodotti che non vuoi mai scontare, come i best-seller o i nuovi arrivi.
    - **Scenario / esempio per il commerciante:** Il tuo prodotto di punta con ID "1001" non viene mai scontato. Inseriresti "1001" qui.
15. **Escludi prodotti con combinazioni specifiche**

    - **Cosa fa questa impostazione:** Ti permette di escludere combinazioni di prodotti specifiche (es. una particolare taglia e colore di un prodotto specifico) dallo sconto.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutte le combinazioni sono idonee.
      - *Se sono selezionate combinazioni:* Queste combinazioni specifiche non saranno scontate.
    - **Valore consigliato:** Per un controllo molto granulare sugli sconti.
    - **Scenario / esempio per il commerciante:** Una combinazione specifica di una maglietta (es. "Rosso, XL") è un'edizione limitata e non dovrebbe essere scontata.
16. **Escludi prodotti con tag specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base ai tag loro assegnati.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti i prodotti sono idonei.
      - *Se vengono inseriti tag:* I prodotti con questi tag non saranno scontati.
    - **Valore consigliato:** Utile se utilizzi ampiamente i tag per la categorizzazione dei prodotti.
    - **Scenario / esempio per il commerciante:** Hai prodotti taggati "Nuovo Arrivo" che vuoi escludere dagli sconti iniziali.
17. **Escludi prodotti con caratteristiche specifiche (di nuovo, potrebbe essere un duplicato o un tipo diverso di selezione delle caratteristiche)**

    - **Cosa fa questa impostazione:** Questa potrebbe essere un metodo di selezione più avanzato o diverso per le caratteristiche rispetto al precedente. Ti permette di escludere prodotti in base alle loro caratteristiche.
    - **Effetto della modifica di questa impostazione:** Simile alla precedente esclusione per caratteristiche, questo assicura che i prodotti con le caratteristiche selezionate non siano scontati.
    - **Valore consigliato:** Controlla se questo offre diverse opzioni di selezione o è destinato a un tipo diverso di caratteristica.
    - **Scenario / esempio per il commerciante:** Se il selettore di caratteristiche precedente era per caratteristiche semplici, questo potrebbe essere per caratteristiche con valori specifici (es. "Materiale: Oro" vs. solo "Materiale").
18. **Escludi prodotti con tipi di prodotto specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base al loro tipo (es. "Prodotto standard", "Pacco di prodotti", "Prodotto virtuale").
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti i tipi di prodotto sono idonei.
      - *Se sono selezionati tipi:* I prodotti di questi tipi non saranno scontati.
    - **Valore consigliato:** Utile se non vuoi scontare prodotti virtuali o pacchi di prodotti.
    - **Scenario / esempio per il commerciante:** Vendi e-book (prodotti virtuali) e vuoi escluderli dallo sconto del buono.
19. **Escludi prodotti con stati di prodotto specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base al loro stato (es. "Attivo", "Inattivo", "Esaurito").
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti gli stati dei prodotti sono idonei.
      - *Se sono selezionati stati:* I prodotti con questi stati non saranno scontati.
    - **Valore consigliato:** Tipicamente, sconteresti solo prodotti attivi e in magazzino.
    - **Scenario / esempio per il commerciante:** Potresti voler escludere prodotti "Inattivi" o "Esauriti" dallo sconto, anche se sono ancora visibili sul sito.
20. **Escludi prodotti con visibilità specifica**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base alle loro impostazioni di visibilità (es. "Solo catalogo", "Solo ricerca", "Ovunque").
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutte le impostazioni di visibilità dei prodotti sono idonee.
      - *Se sono selezionate opzioni di visibilità:* I prodotti con queste impostazioni di visibilità non saranno scontati.
    - **Valore consigliato:** Usalo se hai prodotti con visibilità limitata che non dovrebbero essere scontati.
    - **Scenario / esempio per il commerciante:** Hai prodotti visibili "Solo ricerca" che fanno parte di una campagna speciale non scontabile.
21. **Escludi prodotti con condizioni specifiche**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base alla loro condizione (es. "Nuovo", "Usato", "Ricondizionato").
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutte le condizioni dei prodotti sono idonee.
      - *Se sono selezionate condizioni:* I prodotti con queste condizioni non saranno scontati.
    - **Valore consigliato:** Utile se vendi articoli usati o ricondizionati che sono già fortemente scontati.
    - **Scenario / esempio per il commerciante:** Vendi articoli "Usati" e non vuoi applicare ulteriori sconti su di essi.
22. **Escludi prodotti con disponibilità specifica**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base al loro stato di disponibilità (es. "In magazzino", "Disponibile per l'ordine", "Esaurito").
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti gli stati di disponibilità dei prodotti sono idonei.
      - *Se sono selezionate opzioni di disponibilità:* I prodotti con questi stati non saranno scontati.
    - **Valore consigliato:** Tipicamente, sconteresti solo articoli "In magazzino".
    - **Scenario / esempio per il commerciante:** Vuoi assicurarti che i buoni si applichino solo ai prodotti che sono immediatamente "In magazzino".
23. **Escludi prodotti con tempi di consegna specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base al loro tempo di consegna stimato.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti i tempi di consegna sono idonei.
      - *Se sono selezionati tempi di consegna:* I prodotti con questi tempi di consegna non saranno scontati.
    - **Valore consigliato:** Meno comune per le regole di sconto, ma potrebbe essere utilizzato per articoli in pre-ordine.
    - **Scenario / esempio per il commerciante:** Hai prodotti con lunghi tempi di consegna "Pre-ordine" che non vuoi scontare.
24. **Escludi prodotti con corrieri specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base ai corrieri disponibili per essi.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti i corrieri sono idonei.
      - *Se sono selezionati corrieri:* I prodotti che possono essere spediti solo da questi corrieri non saranno scontati.
    - **Valore consigliato:** Caso d'uso molto specifico, forse per articoli che richiedono spedizioni speciali.
    - **Scenario / esempio per il commerciante:** Hai prodotti che devono essere spediti da un "Corriere per merci fragili" specializzato e vuoi escluderli dagli sconti.
25. **Escludi prodotti con paesi specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base ai paesi per i quali sono disponibili.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti i paesi sono idonei.
      - *Se sono selezionati paesi:* I prodotti disponibili solo in questi paesi non saranno scontati.
    - **Valore consigliato:** Utile per restrizioni di prodotto geo-specifiche.
    - **Scenario / esempio per il commerciante:** Hai prodotti venduti solo negli "USA" che fanno già parte di una promozione specifica per gli Stati Uniti e non dovrebbero essere ulteriormente scontati.
26. **Escludi prodotti con stati specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base agli stati per i quali sono disponibili.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti gli stati sono idonei.
      - *Se sono selezionati stati:* I prodotti disponibili solo in questi stati non saranno scontati.
    - **Valore consigliato:** Restrizioni geo-specifiche più granulari.
    - **Scenario / esempio per il commerciante:** Hai prodotti disponibili solo in "California" che fanno già parte di una promozione specifica per la California.
27. **Escludi prodotti con zone specifiche**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base alle zone di spedizione per le quali sono disponibili.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutte le zone sono idonee.
      - *Se sono selezionate zone:* I prodotti disponibili solo in queste zone non saranno scontati.
    - **Valore consigliato:** Utile per le zone di spedizione internazionali.
    - **Scenario / esempio per il commerciante:** Hai prodotti disponibili solo nella zona di spedizione "Europa" che non vuoi scontare.
28. **Escludi prodotti con valute specifiche**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base alle valute per le quali sono disponibili.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutte le valute sono idonee.
      - *Se sono selezionate valute:* I prodotti disponibili solo in queste valute non saranno scontati.
    - **Valore consigliato:** Per negozi multi-valuta con strategie di prezzo specifiche per i prodotti.
    - **Scenario / esempio per il commerciante:** Hai prodotti prezzati in "USD" che fanno parte di una campagna specifica per USD.
29. **Escludi prodotti con gruppi specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base ai gruppi di clienti per i quali sono disponibili.
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti i gruppi di clienti sono idonei.
      - *Se sono selezionati gruppi:* I prodotti disponibili solo per questi gruppi di clienti non saranno scontati.
    - **Valore consigliato:** Per programmi B2B o di fidelizzazione in cui alcuni prodotti sono esclusivi.
    - **Scenario / esempio per il commerciante:** Hai prodotti disponibili solo per i clienti "All'ingrosso" che non dovrebbero essere scontati da un buono newsletter generale.
30. **Escludi prodotti con negozi specifici**

    - **Cosa fa questa impostazione:** Ti permette di escludere prodotti in base ai negozi in cui sono disponibili (per configurazioni multi-negozio).
    - **Effetto della modifica di questa impostazione:**
      - *Se lasciato vuoto:* Tutti i negozi sono idonei.
      - *Se sono selezionati negozi:* I prodotti disponibili solo in questi negozi non saranno scontati.
    - **Valore consigliato:** Essenziale per ambienti multi-negozio per controllare gli sconti per negozio.
    - **Scenario / esempio per il commerciante:** Hai un "Outlet Store" specifico all'interno della tua configurazione multi-negozio dove i prodotti sono già fortemente scontati.
31. **Escludi prodotti con caratteristiche di prodotto specifiche (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Questa è probabilmente un altro modo per selezionare le caratteristiche del prodotto per l'esclusione. È importante verificare se offre diversi metodi di selezione o se è un campo ridondante.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con le caratteristiche selezionate non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare le caratteristiche per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se i precedenti selettori di caratteristiche erano per caratteristiche generali, questo potrebbe essere per caratteristiche con valori specifici (es. "Materiale: Cotone" vs. solo "Materiale").
32. **Escludi prodotti con tag di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per tag, questa potrebbe essere un'altra interfaccia per la selezione dei tag.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con i tag selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare i tag per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di tag era per tag generali, questo potrebbe essere per tag con valori specifici o una visualizzazione diversa.
33. **Escludi prodotti con attributi di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per attributi, questa potrebbe essere un'altra interfaccia per la selezione degli attributi.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con gli attributi selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare gli attributi per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di attributi era per attributi generali, questo potrebbe essere per attributi con valori specifici o una visualizzazione diversa.
34. **Escludi prodotti con combinazioni di prodotto specifiche (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per combinazioni, questa potrebbe essere un'altra interfaccia per la selezione delle combinazioni.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con le combinazioni selezionate non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare le combinazioni per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di combinazioni era per combinazioni generali, questo potrebbe essere per combinazioni con valori specifici o una visualizzazione diversa.
35. **Escludi prodotti con tipi di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per tipo di prodotto, questa potrebbe essere un'altra interfaccia per la selezione dei tipi di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con i tipi di prodotto selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare i tipi di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di tipi di prodotto era per tipi di prodotto generali, questo potrebbe essere per tipi di prodotto con valori specifici o una visualizzazione diversa.
36. **Escludi prodotti con stati di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per stato di prodotto, questa potrebbe essere un'altra interfaccia per la selezione degli stati di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con gli stati di prodotto selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare gli stati di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di stati di prodotto era per stati di prodotto generali, questo potrebbe essere per stati di prodotto con valori specifici o una visualizzazione diversa.
37. **Escludi prodotti con visibilità di prodotto specifica (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per visibilità di prodotto, questa potrebbe essere un'altra interfaccia per la selezione della visibilità di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con la visibilità di prodotto selezionata non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare la visibilità di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di visibilità di prodotto era per visibilità di prodotto generale, questo potrebbe essere per visibilità di prodotto con valori specifici o una visualizzazione diversa.
38. **Escludi prodotti con condizioni di prodotto specifiche (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per condizione di prodotto, questa potrebbe essere un'altra interfaccia per la selezione delle condizioni di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con le condizioni di prodotto selezionate non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare le condizioni di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di condizioni di prodotto era per condizioni di prodotto generali, questo potrebbe essere per condizioni di prodotto con valori specifici o una visualizzazione diversa.
39. **Escludi prodotti con disponibilità di prodotto specifica (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per disponibilità di prodotto, questa potrebbe essere un'altra interfaccia per la selezione della disponibilità di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con la disponibilità di prodotto selezionata non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare la disponibilità di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di disponibilità di prodotto era per disponibilità di prodotto generale, questo potrebbe essere per disponibilità di prodotto con valori specifici o una visualizzazione diversa.
40. **Escludi prodotti con tempi di consegna di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per tempo di consegna di prodotto, questa potrebbe essere un'altra interfaccia per la selezione dei tempi di consegna di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con i tempi di consegna di prodotto selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare i tempi di consegna di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di tempi di consegna di prodotto era per tempi di consegna di prodotto generali, questo potrebbe essere per tempi di consegna di prodotto con valori specifici o una visualizzazione diversa.
41. **Escludi prodotti con corrieri di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per corriere di prodotto, questa potrebbe essere un'altra interfaccia per la selezione dei corrieri di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con i corrieri di prodotto selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare i corrieri di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di corrieri di prodotto era per corrieri di prodotto generali, questo potrebbe essere per corrieri di prodotto con valori specifici o una visualizzazione diversa.
42. **Escludi prodotti con paesi di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per paese di prodotto, questa potrebbe essere un'altra interfaccia per la selezione dei paesi di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con i paesi di prodotto selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare i paesi di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di paesi di prodotto era per paesi di prodotto generali, questo potrebbe essere per paesi di prodotto con valori specifici o una visualizzazione diversa.
43. **Escludi prodotti con stati di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per stato di prodotto, questa potrebbe essere un'altra interfaccia per la selezione degli stati di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con gli stati di prodotto selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare gli stati di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di stati di prodotto era per stati di prodotto generali, questo potrebbe essere per stati di prodotto con valori specifici o una visualizzazione diversa.
44. **Escludi prodotti con zone di prodotto specifiche (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per zona di prodotto, questa potrebbe essere un'altra interfaccia per la selezione delle zone di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con le zone di prodotto selezionate non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare le zone di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di zone di prodotto era per zone di prodotto generali, questo potrebbe essere per zone di prodotto con valori specifici o una visualizzazione diversa.
45. **Escludi prodotti con valute di prodotto specifiche (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per valuta di prodotto, questa potrebbe essere un'altra interfaccia per la selezione delle valute di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con le valute di prodotto selezionate non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare le valute di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di valute di prodotto era per valute di prodotto generali, questo potrebbe essere per valute di prodotto con valori specifici o una visualizzazione diversa.
46. **Escludi prodotti con gruppi di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per gruppo di prodotto, questa potrebbe essere un'altra interfaccia per la selezione dei gruppi di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con i gruppi di prodotto selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare i gruppi di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di gruppi di prodotto era per gruppi di prodotto generali, questo potrebbe essere per gruppi di prodotto con valori specifici o una visualizzazione diversa.
47. **Escludi prodotti con negozi di prodotto specifici (altra istanza, verifica le sfumature)**

    - **Cosa fa questa impostazione:** Simile alla precedente esclusione per negozio di prodotto, questa potrebbe essere un'altra interfaccia per la selezione dei negozi di prodotto.
    - **Effetto della modifica di questa impostazione:** Assicura che i prodotti con i negozi di prodotto selezionati non siano scontati.
    - **Valore consigliato:** Usalo se fornisce un modo più conveniente o specifico per selezionare i negozi di prodotto per l'esclusione.
    - **Scenario / esempio per il commerciante:** Se il precedente selettore di negozi di prodotto era per negozi di prodotto generali, questo potrebbe essere per negozi di prodotto con valori specifici o una visualizzazione diversa.

    *Nota: Le numerose impostazioni "Escludi prodotti con specifici..." (41-47) sembrano essere ripetute. Ciò potrebbe essere dovuto a una generazione dinamica del modulo in cui ogni tipo di esclusione è elencato, oppure potrebbe indicare un bug/ridondanza nell'interfaccia di configurazione del modulo. In uno scenario reale, uno sviluppatore verificherebbe questo. Per la documentazione, li elenchiamo come rilevati.*

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Elenco buoni (Back Office > Buono unico per iscrizione newsletter > Buoni)

- **Nome schermata e posizione nel menu:** Dopo aver installato il modulo, apparirà una nuova voce di menu nel Back Office di PrestaShop, tipicamente sotto **Catalogo** o **Marketing**, denominata "Buono unico per iscrizione newsletter" o simile. Cliccando su questa si rivelerà una voce di sottomenu come "Buoni".
- **Azioni e impostazioni disponibili:** Questa schermata visualizza un elenco di tutti i buoni unici che sono stati generati dal modulo per le iscrizioni alla newsletter.
  - **Vista griglia / gestione:** Vedrai una tabella con colonne come:
    - **ID:** L'identificatore unico per la voce del buono.
    - **Cliente:** L'indirizzo email del cliente che ha ricevuto il buono.
    - **Data di consegna:** La data e l'ora in cui il buono è stato generato e inviato.
    - **Codice buono:** Il codice sconto unico effettivo.
    - **Azioni:** Tipicamente, puoi visualizzare i dettagli, modificare (anche se la modifica di buoni unici, generati automaticamente, è meno comune) o eliminare le voci.
- **Effetto delle modifiche:**
  - **Visualizzazione:** Ti permette di monitorare i buoni emessi, vedere chi li ha ricevuti e tracciare i loro codici. Questo è cruciale per la risoluzione dei problemi o le richieste del servizio clienti.
  - **Eliminazione:** La rimozione di una voce di buono da questo elenco invaliderà tipicamente il codice buono corrispondente, impedendone l'utilizzo. Usare con cautela.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente questo elenco per monitorare l'efficacia del tuo incentivo all'iscrizione alla newsletter. Se un cliente segnala di non aver ricevuto un buono, puoi verificarne la generazione e il codice qui. Puoi anche eliminare manualmente i buoni scaduti o problematici, se necessario.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Valore del buono (importo o percentuale) | es. "10" o "10%" | Definisce l'importo/percentuale di sconto del buono. |
| Configurazione modulo | Importo minimo | "0" (o valore desiderato) | Totale minimo dell'ordine per la validità del buono. |
| Configurazione modulo | Validità del buono (giorni) | "30" (o valore desiderato) | Numero di giorni di validità del buono dopo la generazione. |
| Configurazione modulo | Descrizione del buono | "Sconto Iscrizione Newsletter" | Descrizione testuale del buono. |
| Configurazione modulo | Prefisso del buono | "NEWSLETTER-" (o vuoto) | Prefisso personalizzato per i codici buono generati. |
| Configurazione modulo | Escludi prodotti con categorie specifiche | (Nessuno selezionato) | Impedisce l'uso del buono su categorie selezionate. |
| Configurazione modulo | Escludi prodotti con produttori specifici | (Nessuno selezionato) | Impedisce l'uso del buono su produttori selezionati. |
| Configurazione modulo | Escludi prodotti con fornitori specifici | (Nessuno selezionato) | Impedisce l'uso del buono su fornitori selezionati. |
| Configurazione modulo | Escludi prodotti con attributi specifici | (Nessuno selezionato) | Impedisce l'uso del buono su prodotti con attributi selezionati. |
| Configurazione modulo | Escludi prodotti con caratteristiche specifiche | (Nessuno selezionato) | Impedisce l'uso del buono su prodotti con caratteristiche selezionate. |
| Configurazione modulo | Escludi prodotti con fasce di prezzo specifiche | (Vuoto) | Impedisce l'uso del buono su prodotti all'interno di una fascia di prezzo. |
| Configurazione modulo | Escludi prodotti con fasce di peso specifiche | (Vuoto) | Impedisce l'uso del buono su prodotti all'interno di una fascia di peso. |
| Configurazione modulo | Escludi prodotti con dimensioni specifiche | (Vuoto) | Impedisce l'uso del buono su prodotti all'interno di fasce di dimensioni. |
| Configurazione modulo | Escludi prodotti con ID prodotto specifici | (Vuoto) | Impedisce l'uso del buono su ID prodotto specifici. |
| Configurazione modulo | Escludi prodotti con combinazioni specifiche | (Nessuno selezionato) | Impedisce l'uso del buono su combinazioni di prodotto specifiche. |
| Configurazione modulo | Escludi prodotti con tag specifici | (Nessuno selezionato) | Impedisce l'uso del buono su prodotti con tag specifici. |
| Configurazione modulo | Escludi prodotti con caratteristiche specifiche (2) | (Nessuno selezionato) | (Possibile selettore di caratteristiche duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con tipi di prodotto specifici | (Nessuno selezionato) | Impedisce l'uso del buono su tipi di prodotto specifici. |
| Configurazione modulo | Escludi prodotti con stati di prodotto specifici | (Nessuno selezionato) | Impedisce l'uso del buono su stati di prodotto specifici. |
| Configurazione modulo | Escludi prodotti con visibilità specifica | (Nessuno selezionato) | Impedisce l'uso del buono su visibilità di prodotto specifica. |
| Configurazione modulo | Escludi prodotti con condizioni specifiche | (Nessuno selezionato) | Impedisce l'uso del buono su condizioni di prodotto specifiche. |
| Configurazione modulo | Escludi prodotti con disponibilità specifica | (Nessuno selezionato) | Impedisce l'uso del buono su disponibilità di prodotto specifica. |
| Configurazione modulo | Escludi prodotti con tempi di consegna specifici | (Nessuno selezionato) | Impedisce l'uso del buono su tempi di consegna di prodotto specifici. |
| Configurazione modulo | Escludi prodotti con corrieri specifici | (Nessuno selezionato) | Impedisce l'uso del buono su corrieri di prodotto specifici. |
| Configurazione modulo | Escludi prodotti con paesi specifici | (Nessuno selezionato) | Impedisce l'uso del buono su paesi di prodotto specifici. |
| Configurazione modulo | Escludi prodotti con stati specifici | (Nessuno selezionato) | Impedisce l'uso del buono su stati di prodotto specifici. |
| Configurazione modulo | Escludi prodotti con zone specifiche | (Nessuno selezionato) | Impedisce l'uso del buono su zone di prodotto specifiche. |
| Configurazione modulo | Escludi prodotti con valute specifiche | (Nessuno selezionato) | Impedisce l'uso del buono su valute di prodotto specifiche. |
| Configurazione modulo | Escludi prodotti con gruppi specifici | (Nessuno selezionato) | Impedisce l'uso del buono su gruppi di clienti specifici. |
| Configurazione modulo | Escludi prodotti con negozi specifici | (Nessuno selezionato) | Impedisce l'uso del buono su negozi specifici (multi-negozio). |
| Configurazione modulo | Escludi prodotti con caratteristiche di prodotto specifiche (3) | (Nessuno selezionato) | (Possibile selettore di caratteristiche duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con tag di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di tag duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con attributi di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di attributi duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con combinazioni di prodotto specifiche (2) | (Nessuno selezionato) | (Possibile selettore di combinazioni duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con tipi di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di tipi di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con stati di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di stati di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con visibilità di prodotto specifica (2) | (Nessuno selezionato) | (Possibile selettore di visibilità di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con condizioni di prodotto specifiche (2) | (Nessuno selezionato) | (Possibile selettore di condizioni di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con disponibilità di prodotto specifica (2) | (Nessuno selezionato) | (Possibile selettore di disponibilità di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con tempi di consegna di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di tempi di consegna di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con corrieri di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di corrieri di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con paesi di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di paesi di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con stati di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di stati di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con zone di prodotto specifiche (2) | (Nessuno selezionato) | (Possibile selettore di zone di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con valute di prodotto specifiche (2) | (Nessuno selezionato) | (Possibile selettore di valute di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con gruppi di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di gruppi di prodotto duplicato/alternativo) |
| Configurazione modulo | Escludi prodotti con negozi di prodotto specifici (2) | (Nessuno selezionato) | (Possibile selettore di negozi di prodotto duplicato/alternativo) |
| Elenco buoni | ID | N/A | Identificatore unico per la voce del buono. |
| Elenco buoni | Cliente | N/A | Email del cliente che ha ricevuto il buono. |
| Elenco buoni | Data di consegna | N/A | Data e ora di generazione del buono. |
| Elenco buoni | Codice buono | N/A | Il codice sconto unico. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti si stanno iscrivendo ma non ricevono l'email del buono. Cosa devo fare?**
R:

1.  **Controlla le cartelle spam:** Consiglia ai clienti di controllare le loro cartelle spam o posta indesiderata.
2.  **Verifica la configurazione email:** Assicurati che le impostazioni email del tuo negozio PrestaShop (Parametri avanzati > E-mail) siano configurate correttamente e che inviino email in modo affidabile. Prova a inviare una semplice email da PrestaShop.
3.  **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli > Buono unico per iscrizione newsletter > Configura**. Assicurati che tutte le impostazioni, specialmente il valore del buono, siano impostate correttamente.
4.  **Rivedi l'elenco dei buoni:** Naviga su **Back Office > Buono unico per iscrizione newsletter > Buoni**. Controlla se il buono è stato effettivamente generato e elencato per l'email del cliente. Se è lì, il problema è con la consegna dell'email; in caso contrario, il modulo potrebbe non attivarsi correttamente.
5.  **Svuota la cache:** A volte, svuotare la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota la cache) può risolvere comportamenti inaspettati.

**D: Il codice del buono viene generato, ma non applica lo sconto corretto o ha condizioni errate.**
R:

1.  **Ricontrolla la configurazione del modulo:** Vai su **Moduli > Gestione moduli > Buono unico per iscrizione newsletter > Configura**. Rivedi attentamente tutte le impostazioni:
    -   **Valore del buono:** È l'importo o la percentuale corretta?
    -   **Importo minimo:** Il carrello del cliente soddisfa questo minimo?
    -   **Impostazioni di esclusione:** Ci sono categorie, produttori o prodotti specifici esclusi che il cliente sta cercando di acquistare?
2.  **Testa con una nuova iscrizione:** Crea un nuovo indirizzo email e iscriviti alla tua newsletter per generare un nuovo buono. Testa tu stesso questo nuovo buono per replicare il problema.

**D: Posso personalizzare il template email che invia il buono?**
R: Questo modulo si integra tipicamente con il sistema email predefinito di PrestaShop. Il codice del buono viene solitamente inserito in un template email esistente (come l'email di conferma della newsletter). Per personalizzare l'aspetto o il testo dell'email, dovresti generalmente modificare i file del template email pertinenti nella directory `mails/` del tuo tema (ad esempio, `mails/it/newsletter.html` o `mails/it/newsletter.txt`). Potrebbe essere necessario un sviluppatore per personalizzazioni avanzate.

**D: Questo modulo funziona con moduli di iscrizione alla newsletter personalizzati o pop-up?**
R: Questo modulo è progettato per funzionare con il processo di iscrizione alla newsletter standard di PrestaShop. Se il tuo modulo personalizzato o pop-up si integra correttamente con il modulo newsletter principale di PrestaShop (ad esempio, chiamando la stessa azione di iscrizione), allora questo modulo dovrebbe funzionare correttamente. Se utilizza un metodo di iscrizione completamente personalizzato, potrebbe richiedere un'integrazione personalizzata da parte di uno sviluppatore.

**D: Ho una configurazione multi-negozio. Questo modulo funziona per tutti i miei negozi?**
R: Sì, il modulo dovrebbe essere compatibile con ambienti multi-negozio. Le impostazioni di configurazione, incluse le esclusioni, dovrebbero essere gestibili per ogni negozio se il sistema di configurazione di PrestaShop è correttamente utilizzato dal modulo. Testa sempre accuratamente in una configurazione multi-negozio.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Buono unico per iscrizione newsletter" (`newslettervoucher`) segue un'architettura standard dei moduli PrestaShop, estendendo principalmente `Module` e utilizzando `AdminController` per la sua interfaccia Back Office. Si integra con il flusso di iscrizione alla newsletter esistente agganciandosi a eventi pertinenti per generare e consegnare oggetti `CartRule` (buono) unici. Il modulo sfrutta la classe `Configuration` di PrestaShop per le sue impostazioni e `ObjectModel` per la gestione delle proprie entità `nvoucher`.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/cronjob.php`
  - **Nome classe e classe genitore:** `NewsletterVoucherCronjobModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller è probabilmente destinato a gestire le richieste di cron job. Tipicamente conterrebbe la logica per elaborare le generazioni di buoni in coda o pulire i buoni scaduti, attivati da una chiamata cron esterna. Potrebbe non renderizzare direttamente una pagina ma eseguire attività in background.
- `controllers/front/index.php`
  - **Nome classe e classe genitore:** `NewsletterVoucherIndexModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller potrebbe fungere da controller frontale predefinito o di fallback, oppure potrebbe essere utilizzato per semplici richieste AJAX relative alla funzionalità front-office del modulo, sebbene la generazione primaria dei buoni sia basata su eventi. Dato lo scopo del modulo, è meno probabile che renderizzi viste front-office complesse.

#### Controller Admin Back-Office

- `controllers/admin/AdminNewsletterVoucherVouchers.php`
  - **Nome classe e classe genitore:** `AdminNewsletterVoucherVouchersController` estende `ModuleAdminController`.
  - **Nome scheda ed entità gestita:** Questo controller gestisce l'elenco "Buoni" nel Back Office di PrestaShop, occupandosi specificamente dell'entità `nvoucher` (probabilmente un `ObjectModel` personalizzato per il tracciamento dei buoni generati). Fornisce l'interfaccia CRUD (Create, Read, Update, Delete) standard per queste voci di buono.
- `controllers/admin/index.php`
  - **Nome classe e classe genitore:** `AdminNewsletterVoucherIndexController` estende `ModuleAdminController`.
  - **Nome scheda ed entità gestita:** Questo controller funge probabilmente da punto di ingresso principale o da dashboard per il modulo nel Back Office, visualizzando potenzialmente una panoramica o reindirizzando al controller `AdminNewsletterVoucherVouchers`. Potrebbe anche gestire il modulo di configurazione iniziale del modulo (`getContent()`) se non è direttamente nel file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

L'inventario fornito indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo potrebbe definire il suo `ObjectModel` primario (ad esempio, per le voci `nvoucher`) direttamente all'interno del file principale del modulo (`newslettervoucher/cronjob.php`) o che interagisce principalmente con gli `ObjectModel` `CartRule` e `Customer` di PrestaShop.

Se viene gestita una tabella `nvoucher`, la sua definizione si troverebbe tipicamente nel metodo `install()` del file principale del modulo o in una classe `ObjectModel` dedicata. Contenerebbe probabilmente campi come `id_nvoucher`, `id_customer`, `voucher_code`, `date_add`, `date_upd`, `id_cart_rule`.

### 4.4 Risorse JavaScript (`views/js/`)

- `newslettervoucher/lib/voucherengine/script.js`
  - **Ambito:** Probabilmente Back-office.
  - **Descrizione:** Questo script probabilmente gestisce il comportamento dinamico all'interno dei moduli di configurazione del modulo o dell'elenco dei buoni nel Back Office. Ciò potrebbe includere:
    - Chiamate AJAX per il salvataggio delle impostazioni.
    - Visualizzazione/nascondimento dinamico dei campi di configurazione in base ad altre selezioni.
    - Logica di filtraggio, ordinamento o paginazione per l'elenco dei buoni.
    - Validazione dell'input o elementi interattivi.
    - Date le ampie opzioni di esclusione, potrebbe alimentare un selettore dinamico di prodotti/categorie/ecc.

### 4.5 Fogli di stile CSS (`views/css/`)

- `newslettervoucher/css.css`
  - **Ambito:** Potrebbe essere Front-office o Back-office, ma più probabilmente Back-office per lo stile delle pagine di configurazione del modulo e delle viste dell'elenco di amministrazione.
  - **Descrizione:** Contiene regole di stile generali per gli elementi del modulo, assicurando che si integrino visivamente con il tema del Back Office di PrestaShop.
- `newslettervoucher/lib/voucherengine/ps16.css`
  - **Ambito:** Back-office.
  - **Descrizione:** Questo foglio di stile si rivolge specificamente allo stile del Back Office di PrestaShop 1.6. Contenerebbe regole per garantire che l'interfaccia di amministrazione del modulo appaia corretta e coerente all'interno del tema PS 1.6, potenzialmente sovrascrivendo o adattando gli stili predefiniti di PS 1.6 per elementi specifici del modulo. Per PS 1.7+ e 8.x, questi stili potrebbero essere ignorati o richiedere aggiustamenti per la piena compatibilità.

### 4.6 Struttura del template Smarty (`views/templates/`)

L'inventario indica l'assenza di file `.tpl`. Ciò suggerisce che:

- Il modulo di configurazione principale del modulo viene renderizzato direttamente all'interno del metodo `getContent()` del file principale del modulo utilizzando `HelperForm` di PrestaShop o simili.
- Le viste del controller Admin (`AdminNewsletterVoucherVouchers`) vengono renderizzate utilizzando le classi `HelperList` e `HelperForm` di PrestaShop, che generano direttamente l'HTML senza richiedere file `.tpl` personalizzati per le visualizzazioni di base di elenchi e moduli.
- L'integrazione front-office è puramente programmatica, iniettando codici voucher in template email esistenti o tramite hook senza template di modulo dedicati.

Se fossero presenti template personalizzati, si troverebbero tipicamente in:

- `views/templates/admin/`: Per moduli o dashboard personalizzati del Back Office.
- `views/templates/hook/`: Per contenuti renderizzati in specifici hook di PrestaShop.
- `views/templates/front/`: Per eventuali pagine front-office dedicate o widget complessi.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

- `ps_nvoucher` (Probabile, basato su `AdminNewsletterVoucherVouchers` che gestisce l'entità `nvoucher`)

  - `id_nvoucher` (Chiave primaria, INT)
  - `id_customer` (INT, Chiave esterna a `ps_customer`)
  - `voucher_code` (VARCHAR, memorizza il codice `CartRule` unico)
  - `date_add` (DATETIME, timestamp di generazione del buono)
  - `id_cart_rule` (INT, Chiave esterna a `ps_cart_rule`, che collega al buono PrestaShop effettivo)
  - Potrebbero esistere altri campi per il tracciamento dell'utilizzo, della scadenza, ecc.
- **Record di configurazione (nella tabella `ps_configuration`):**

  - `NEWSLETTERVOUCHER_VALUE` (Importo/percentuale del buono)
  - `NEWSLETTERVOUCHER_MIN_AMOUNT` (Importo minimo dell'ordine)
  - `NEWSLETTERVOUCHER_VALIDITY` (Validità del buono in giorni)
  - `NEWSLETTERVOUCHER_DESCRIPTION` (Descrizione del buono)
  - `NEWSLETTERVOUCHER_PREFIX` (Prefisso del codice buono)
  - `NEWSLETTERVOUCHER_EXCLUDE_CATEGORIES` (Array serializzato di categorie escluse)
  - ... e chiavi `NEWSLETTERVOUCHER_EXCLUDE_...` simili per tutte le impostazioni di esclusione.

#### Tabella degli hook registrati

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Dopo la creazione di un nuovo account cliente. | Potrebbe essere utilizzato per attivare la generazione del buono al momento della registrazione di un nuovo account, se collegato all'iscrizione alla newsletter. |
| `actionNewsletterSubscriptionAdd` | Dopo che una nuova email si iscrive alla newsletter. | **HOOK CRITICO:** Questo è l'hook primario in cui il modulo intercetterebbe una nuova iscrizione alla newsletter, genererebbe un `CartRule` unico e lo invierebbe all'iscritto. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina front-office. | Potenzialmente per caricare risorse JS/CSS o meta tag, anche se meno probabile per la funzionalità principale. |
| `displayLeftColumn` | Nella colonna sinistra delle pagine front-office. | Se il modulo avesse un blocco front-office (ad esempio, un promemoria sul buono). |
| `displayRightColumn` | Nella colonna destra delle pagine front-office. | Come `displayLeftColumn`. |
| `displayFooter` | Nel footer di ogni pagina front-office. | Come `displayLeftColumn`, spesso dove si trovano i moduli di iscrizione alla newsletter. |
| `displayProductAdditionalInfo` | Nelle pagine prodotto, sotto le informazioni principali del prodotto. | Meno probabile per questo modulo, ma potrebbe essere utilizzato per visualizzare un messaggio "Iscriviti alla newsletter, ricevi un buono". |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del Back Office. | Per caricare risorse JS/CSS specifiche del Back Office per le pagine di amministrazione del modulo. |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office. | Meno probabile, ma potrebbe essere utilizzato per aggiungere una scheda o informazioni specifiche del modulo relative alle esclusioni di prodotto. |
| `moduleRoutes` | Quando PrestaShop costruisce la sua tabella di routing. | Per definire URL amichevoli personalizzati per i suoi controller frontali (ad esempio, `/module/newslettervoucher/cronjob`). |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "Buono unico per iscrizione newsletter", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
