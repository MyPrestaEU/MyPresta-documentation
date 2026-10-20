---
title: "Facebook Shop - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Facebook Shop di MyPresta.eu."
sidebar:
  label: "Facebook Shop - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Shop su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-shop.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-shop/)
>
> ---


# Facebook Shop

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).
- **Pagina Fan di Facebook**: Devi avere una Pagina Fan di Facebook attiva (non un profilo personale) di cui sei amministratore.
- **Certificato SSL**: Il tuo negozio PrestaShop deve avere un certificato SSL attivo (HTTPS) affinché il Facebook Shop funzioni correttamente, poiché Facebook richiede connessioni sicure per le applicazioni incorporate.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il tuo modulo Facebook Shop. Troverai una serie di schede o sezioni per personalizzare l'aspetto e il funzionamento del tuo negozio su Facebook.

#### Scheda Impostazioni generali (o vista iniziale simile)

-   **Visualizza aggiornamenti MyPresta.eu:**

    -   **Cosa fa questa impostazione:** Controlla se ricevi notifiche sugli aggiornamenti da MyPresta.eu direttamente nella configurazione del tuo modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Riceverai avvisi per nuove versioni o notizie importanti da MyPresta.eu, aiutandoti a mantenere il tuo modulo aggiornato.
        -   *Quando disabilitato:* Non vedrai queste notifiche, il che potrebbe significare che perdi aggiornamenti importanti o correzioni di bug.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Mantieni questa opzione abilitata per assicurarti di essere sempre a conoscenza degli ultimi miglioramenti e patch di sicurezza per il tuo modulo Facebook Shop.
-   **Visualizzazione lingua Facebook Shop:** (`faceshop_lang_disp`)

    -   **Cosa fa questa impostazione:** Determina se il selettore della lingua è visibile nel tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono cambiare la lingua del tuo Facebook Shop, utile per i negozi internazionali.
        -   *Quando disabilitato:* Il negozio verrà visualizzato nella lingua predefinita o nella lingua rilevata da Facebook, senza un selettore esplicito.
    -   **Valore consigliato:** SÌ (se hai più lingue abilitate in PrestaShop)
    -   **Scenario / esempio per il commerciante:** Se vendi a clienti in diversi paesi e hai tradotto il tuo negozio PrestaShop, abilita questa opzione per consentire loro di navigare nella loro lingua preferita.
-   **Visualizzazione valuta Facebook Shop:** (`faceshop_curr_disp`)

    -   **Cosa fa questa impostazione:** Determina se il selettore della valuta è visibile nel tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono cambiare la valuta visualizzata nel tuo Facebook Shop, utile per i negozi internazionali.
        -   *Quando disabilitato:* Il negozio visualizzerà i prezzi nella tua valuta predefinita.
    -   **Valore consigliato:** SÌ (se hai più valute abilitate in PrestaShop)
    -   **Scenario / esempio per il commerciante:** Se accetti pagamenti in USD, EUR e GBP, abilita questa opzione in modo che i clienti possano vedere i prezzi nella loro valuta locale.
-   **Abilita riscrittura modulo (URL SEO friendly):** (`faceshop_modrew`)

    -   **Cosa fa questa impostazione:** Controlla se il modulo utilizza URL SEO friendly all'interno del Facebook Shop, simili a quelli del tuo negozio PrestaShop principale.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Gli URL per prodotti e categorie all'interno del Facebook Shop saranno puliti e descrittivi (es. `iltuonegozio.com/prodotto/il-mio-fantastico-prodotto`). Questo è generalmente migliore per la SEO e l'esperienza utente.
        -   *Quando disabilitato:* Gli URL potrebbero essere meno leggibili (es. `iltuonegozio.com/index.php?id_product=123`).
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Abilita sempre questa opzione per una migliore visibilità sui motori di ricerca e un aspetto più professionale per i tuoi link di prodotto condivisi da Facebook.

#### Scheda Impostazioni homepage

-   **Visualizza conteggio elementi homepage:** (`faceshop_homepage_itemcount`)

    -   **Cosa fa questa impostazione:** Imposta il numero di prodotti da visualizzare sulla homepage del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 10:* La homepage del tuo Facebook Shop mostrerà 10 prodotti.
        -   *Quando impostato su 20:* La homepage del tuo Facebook Shop mostrerà 20 prodotti.
    -   **Valore consigliato:** 12-24 (abbastanza per mostrare varietà senza sovraccaricare la pagina).
    -   **Scenario / esempio per il commerciante:** Se vuoi mostrare una vasta gamma di prodotti immediatamente, imposta un numero più alto. Se preferisci un aspetto più pulito con meno elementi più prominenti, imposta un numero più basso.
-   **Visualizza prodotti scontati homepage:** (`faceshop_homepage_disphot`)

    -   **Cosa fa questa impostazione:** Controlla se i prodotti scontati (in saldo) sono presenti sulla homepage del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I prodotti attualmente in saldo saranno visualizzati in modo prominente, incoraggiando gli acquisti d'impulso.
        -   *Quando disabilitato:* Sulla homepage appariranno solo i prodotti a prezzo normale (a meno che non siano abilitate altre opzioni di visualizzazione).
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Usa questa opzione per attirare l'attenzione sulle tue promozioni e svuotare l'inventario.
-   **Visualizza nuovi prodotti homepage:** (`faceshop_homepage_dispnew`)

    -   **Cosa fa questa impostazione:** Controlla se i tuoi prodotti più recenti sono presenti sulla homepage del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I prodotti aggiunti di recente saranno mostrati, mantenendo il tuo negozio fresco ed emozionante per i visitatori di ritorno.
        -   *Quando disabilitato:* I nuovi prodotti non avranno una sezione dedicata sulla homepage.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Se aggiungi frequentemente nuovi articoli, questo è un ottimo modo per metterli in evidenza e incoraggiare le visite ripetute.
-   **Visualizza categoria radice homepage:** (`faceshop_homepage_root`)

    -   **Cosa fa questa impostazione:** Ti permette di selezionare una categoria radice specifica da cui visualizzare i prodotti sulla homepage del tuo Facebook Shop. Se lasciato vuoto, visualizzerà i prodotti dalla tua categoria radice predefinita di PrestaShop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene selezionata una categoria specifica:* Sulla homepage appariranno solo i prodotti di quella categoria e delle sue sottocategorie.
        -   *Quando lasciato vuoto:* I prodotti dell'intera categoria radice predefinita del tuo negozio saranno considerati per la visualizzazione sulla homepage.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia una strategia di marketing specifica.
    -   **Scenario / esempio per il commerciante:** Se stai conducendo una campagna speciale per la "Collezione Estiva" e vuoi solo quei prodotti sulla homepage del tuo Facebook Shop, selezioneresti qui la categoria "Collezione Estiva".

#### Scheda Impostazioni intestazione

-   **Visualizza intestazione nel Facebook Shop:** (`faceshop_header_disp`)
    -   **Cosa fa questa impostazione:** Controlla se la sezione dell'intestazione del tuo negozio PrestaShop (logo, barra di ricerca, riepilogo carrello) è visibile all'interno del Facebook Shop incorporato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il tuo Facebook Shop avrà un'intestazione familiare, facendolo sentire più simile al tuo negozio principale.
        -   *Quando disabilitato:* L'intestazione sarà nascosta, fornendo un aspetto più minimalista.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Mantenere l'intestazione visibile aiuta a mantenere la coerenza del marchio e fornisce elementi di navigazione essenziali come la barra di ricerca.

#### Scheda Impostazioni pagina categoria

-   **Categoria radice per Facebook Shop:** (`faceshop_cat_root`)

    -   **Cosa fa questa impostazione:** Definisce la categoria principale da cui il tuo Facebook Shop inizierà a visualizzare prodotti e categorie. Questo agisce come la "radice" per la navigazione del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando è selezionato "Home" (radice predefinita di PrestaShop):* Tutte le categorie e i prodotti del tuo intero negozio saranno accessibili.
        -   *Quando è selezionata una categoria specifica (es. "Abbigliamento"):* Solo "Abbigliamento" e le sue sottocategorie/prodotti saranno visibili nel Facebook Shop.
    -   **Valore consigliato:** "Home" (o la categoria radice del tuo negozio principale) a meno che tu non voglia limitare l'ambito del tuo Facebook Shop.
    -   **Scenario / esempio per il commerciante:** Se vuoi vendere solo una linea specifica di prodotti (es. "Elettronica") su Facebook, imposteresti questa opzione sulla tua categoria "Elettronica".
-   **Visualizza nuovi prodotti nelle pagine di categoria:** (`faceshop_cat_dispnew`)

    -   **Cosa fa questa impostazione:** Controlla se i nuovi prodotti sono evidenziati o hanno una sezione dedicata nelle pagine di elenco delle categorie all'interno del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti che navigano nelle categorie individueranno facilmente gli articoli aggiunti di recente.
        -   *Quando disabilitato:* I nuovi prodotti appariranno semplicemente nell'elenco normale senza enfasi speciale.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Aiuta i clienti a scoprire i tuoi ultimi arrivi anche quando stanno navigando tipi di prodotti specifici.
-   **Visualizza prodotti scontati nelle pagine di categoria:** (`faceshop_cat_disphot`)

    -   **Cosa fa questa impostazione:** Controlla se i prodotti scontati sono evidenziati o hanno una sezione dedicata nelle pagine di elenco delle categorie all'interno del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti che navigano nelle categorie individueranno facilmente gli articoli in saldo.
        -   *Quando disabilitato:* I prodotti scontati appariranno semplicemente nell'elenco normale senza enfasi speciale.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Incoraggia gli acquisti rendendo gli articoli in saldo più visibili all'interno delle categorie pertinenti.
-   **Conteggio articoli per pagina di categoria:** (`faceshop_cat_itemcount`)

    -   **Cosa fa questa impostazione:** Imposta il numero di prodotti da visualizzare per pagina quando i clienti navigano nelle categorie del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 12:* Ogni pagina di categoria mostrerà 12 prodotti prima della paginazione.
        -   *Quando impostato su 30:* Ogni pagina di categoria mostrerà 30 prodotti.
    -   **Valore consigliato:** 12-24 (standard per la maggior parte dei siti di e-commerce).
    -   **Scenario / esempio per il commerciante:** Un numero più alto riduce i clic ma può rallentare il caricamento delle pagine. Un numero più basso richiede più clic ma può sembrare meno opprimente.
-   **Stile di visualizzazione categoria:** (`faceshop_cat_dispstyle`)

    -   **Cosa fa questa impostazione:** Determina come le categorie vengono presentate nel Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Opzione A (es. "Vista a griglia"):* Le categorie sono mostrate come una griglia di immagini/nomi.
        -   *Opzione B (es. "Vista a elenco"):* Le categorie sono mostrate come un elenco verticale.
    -   **Valore consigliato:** Vista a griglia (spesso più accattivante visivamente).
    -   **Scenario / esempio per il commerciante:** Scegli lo stile che meglio si adatta all'estetica del tuo marchio e a come vuoi che i clienti navighino nella tua gamma di prodotti.

#### Scheda Impostazioni slider

-   **Visualizza slider nel Facebook Shop:** (`faceshop_slider_disp`)

    -   **Cosa fa questa impostazione:** Controlla se uno slider di immagini (carosello) viene visualizzato nel tuo Facebook Shop. Questo slider tipicamente mostra prodotti in evidenza, promozioni o banner.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Apparirà un banner rotante o uno slider di prodotti, attirando l'attenzione.
        -   *Quando disabilitato:* Non verrà mostrato alcuno slider, risultando in un layout statico.
    -   **Valore consigliato:** SÌ (se hai immagini accattivanti per uno slider).
    -   **Scenario / esempio per il commerciante:** Usa lo slider per evidenziare la tua ultima collezione, le vendite stagionali o gli articoli più venduti proprio in cima al tuo Facebook Shop.
-   **Tempo di transizione slider (in millisecondi):** (`faceshop_slider_time`)

    -   **Cosa fa questa impostazione:** Imposta per quanto tempo ogni slide rimane visibile prima di passare alla successiva.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 3000 (3 secondi):* Le slide cambieranno ogni 3 secondi.
        -   *Quando impostato su 5000 (5 secondi):* Le slide cambieranno ogni 5 secondi.
    -   **Valore consigliato:** 4000-6000 (4-6 secondi) per consentire agli utenti tempo sufficiente per leggere.
    -   **Scenario / esempio per il commerciante:** Regola questo valore in base alla quantità di informazioni sulle tue slide. Tempi più brevi per slide solo immagine, più lunghi per slide con testo.
-   **Posizionamento slider:** (`faceshop_slider_place`)

    -   **Cosa fa questa impostazione:** Determina dove appare lo slider all'interno del tuo Facebook Shop (es. in cima alla pagina, sotto le categorie).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "In alto":* Lo slider sarà la prima cosa che i clienti vedranno.
        -   *Quando impostato su "Sotto i prodotti":* Lo slider apparirà più in basso nella pagina.
    -   **Valore consigliato:** In alto (per la massima visibilità).
    -   **Scenario / esempio per il commerciante:** Posiziona lo slider in alto per catturare immediatamente l'attenzione con le tue promozioni più importanti.

#### Scheda Impostazioni menu

-   **Visualizza link nuovi prodotti nel menu:** (`faceshop_menu_newproducts`)

    -   **Cosa fa questa impostazione:** Aggiunge un link a "Nuovi prodotti" nel menu di navigazione del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono facilmente cliccare per vedere tutte le tue ultime aggiunte.
        -   *Quando disabilitato:* Questo link specifico non apparirà nel menu.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Essenziale per i negozi che aggiornano frequentemente il loro inventario per aiutare i clienti a scoprire nuovi articoli.
-   **Visualizza link prodotti in saldo nel menu:** (`faceshop_menu_saleproducts`)

    -   **Cosa fa questa impostazione:** Aggiunge un link a "Prodotti in saldo" o "Sconti" nel menu di navigazione del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono trovare rapidamente tutti i tuoi articoli scontati.
        -   *Quando disabilitato:* Questo link specifico non apparirà nel menu.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Ottimo per indirizzare il traffico alle tue promozioni e aumentare le vendite.
-   **Visualizza link pagine informative nel menu:** (`faceshop_menu_informations`)

    -   **Cosa fa questa impostazione:** Aggiunge un link alle tue pagine CMS (Informazioni) di PrestaShop (es. Chi siamo, Consegna, Termini e condizioni) nel menu di navigazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono accedere direttamente a importanti informazioni non relative ai prodotti.
        -   *Quando disabilitato:* Questi link non appariranno nel menu.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Cruciale per costruire fiducia e fornire le informazioni necessarie per il servizio clienti.
-   **Visualizza link pagina contatti nel menu:** (`faceshop_menu_contact`)

    -   **Cosa fa questa impostazione:** Aggiunge un link alla tua pagina Contattaci di PrestaShop nel menu di navigazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono facilmente trovare come mettersi in contatto con te.
        -   *Quando disabilitato:* Questo link specifico non apparirà nel menu.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Fornisce un canale diretto per le richieste dei clienti, migliorando il supporto.
-   **Stile di visualizzazione categoria menu:** (`faceshop_menu_catstyle`)

    -   **Cosa fa questa impostazione:** Determina come le categorie vengono visualizzate nel menu di navigazione principale del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Opzione A (es. "Menu a discesa"):* Le categorie appaiono in un menu a discesa.
        -   *Opzione B (es. "Elenco orizzontale"):* Le categorie appaiono come un elenco orizzontale.
    -   **Valore consigliato:** Menu a discesa (per molte categorie) o Elenco orizzontale (per poche categorie).
    -   **Scenario / esempio per il commerciante:** Se hai molte categorie di prodotti, un menu a discesa mantiene la navigazione pulita. Se hai solo poche categorie principali, un elenco orizzontale potrebbe essere più diretto.
-   **Visualizza link produttori nel menu:** (`faceshop_menu_manuf`)

    -   **Cosa fa questa impostazione:** Aggiunge un link alla tua pagina Produttori di PrestaShop nel menu di navigazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono sfogliare i prodotti per marca o produttore.
        -   *Quando disabilitato:* Questo link specifico non apparirà nel menu.
    -   **Valore consigliato:** SÌ (se vendi prodotti di più marchi distinti).
    -   **Scenario / esempio per il commerciante:** Se sei un rivenditore di vari marchi, questo aiuta i clienti a trovare prodotti dai loro produttori preferiti.

#### Scheda Impostazioni pagina prodotto

-   **Visualizza navigazione breadcrumb:** (`faceshop_display_breadcrumb`)

    -   **Cosa fa questa impostazione:** Controlla se la navigazione "breadcrumb" (es. Home > Categoria > Sottocategoria > Prodotto) viene mostrata nelle pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Aiuta i clienti a capire la loro posizione all'interno della gerarchia del negozio e a navigare facilmente verso le categorie genitore.
        -   *Quando disabilitato:* Il percorso breadcrumb sarà nascosto.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Migliora l'esperienza utente fornendo percorsi di navigazione chiari, specialmente per i negozi con strutture di categorie profonde.
-   **Taglia descrizione prodotto:** (`faceshop_pdisp_trim`)

    -   **Cosa fa questa impostazione:** Se abilitata, accorcerà le descrizioni lunghe dei prodotti nella pagina prodotto, spesso mostrando un link "Leggi di più".
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Le pagine prodotto appaiono più pulite e gli utenti possono scegliere di espandere la descrizione se interessati.
        -   *Quando disabilitato:* Le descrizioni complete dei prodotti vengono sempre mostrate, il che può rendere le pagine molto lunghe.
    -   **Valore consigliato:** SÌ (per prodotti con descrizioni molto lunghe).
    -   **Scenario / esempio per il commerciante:** Impedisce che le pagine prodotto siano eccessivamente lunghe, specialmente su mobile, mostrando prima un riassunto conciso.
-   **Visualizza prezzo prodotto:** (`faceshop_pdisp_price`)

    -   **Cosa fa questa impostazione:** Controlla se il prezzo del prodotto è visibile nelle pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il prezzo sarà chiaramente visualizzato.
        -   *Quando disabilitato:* Il prezzo sarà nascosto.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Nascondere i prezzi non è generalmente consigliato per un negozio di e-commerce a meno che tu non abbia una strategia B2B specifica che richieda preventivi. Per la maggior parte del commercio al dettaglio, i prezzi sono essenziali.
-   **Visualizza nome prodotto:** (`faceshop_pdisp_name`)

    -   **Cosa fa questa impostazione:** Controlla se il nome del prodotto è visibile nelle pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il nome del prodotto sarà visualizzato.
        -   *Quando disabilitato:* Il nome del prodotto sarà nascosto.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Il nome del prodotto è fondamentale per l'identificazione; mantieni sempre questa opzione abilitata.
-   **Visualizza immagine prodotto:** (`faceshop_pdisp_image`)

    -   **Cosa fa questa impostazione:** Controlla se l'immagine del prodotto è visibile nelle pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* L'immagine principale del prodotto e le immagini aggiuntive saranno visualizzate.
        -   *Quando disabilitato:* Le immagini del prodotto saranno nascoste.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Le immagini dei prodotti sono cruciali per le vendite online; mantieni sempre questa opzione abilitata.

#### Scheda Impostazioni condivisione social

-   **Visualizza pulsante Condividi su Facebook:** (`faceshop_social_facebook`)

    -   **Cosa fa questa impostazione:** Aggiunge un pulsante "Condividi" di Facebook alle pagine prodotto all'interno del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono facilmente condividere i prodotti con i loro amici di Facebook, aumentando il marketing virale.
        -   *Quando disabilitato:* Il pulsante di condivisione di Facebook non apparirà.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Incoraggia i clienti a diffondere la parola sui tuoi prodotti sulle loro bacheche.
-   **Visualizza pulsante Condividi su Pinterest:** (`faceshop_social_pinterest`)

    -   **Cosa fa questa impostazione:** Aggiunge un pulsante "Pin It" di Pinterest alle pagine prodotto all'interno del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono facilmente appuntare le immagini dei prodotti sulle loro bacheche Pinterest, generando traffico da Pinterest.
        -   *Quando disabilitato:* Il pulsante di condivisione di Pinterest non apparirà.
    -   **Valore consigliato:** SÌ (specialmente se i tuoi prodotti sono visivamente accattivanti).
    -   **Scenario / esempio per il commerciante:** Ottimo per moda, arredamento, artigianato e altri prodotti visivamente orientati per sfruttare il pubblico di Pinterest.
-   **Visualizza pulsante Condividi su Google+:** (`faceshop_social_google`)

    -   **Cosa fa questa impostazione:** Aggiunge un pulsante di condivisione di Google+ alle pagine prodotto all'interno del tuo Facebook Shop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti possono condividere i prodotti su Google+.
        -   *Quando disabilitato:* Il pulsante di condivisione di Google+ non apparirà.
    -   **Valore consigliato:** NO (Google+ è stato disattivato).
    -   **Scenario / esempio per il commerciante:** Questa piattaforma non è più attiva, quindi mantenerla abilitata è inutile.

#### Scheda Impostazioni piè di pagina

-   **Visualizza piè di pagina nel Facebook Shop:** (`faceshop_footer_disp`)
    -   **Cosa fa questa impostazione:** Controlla se la sezione del piè di pagina del tuo negozio PrestaShop (copyright, link, icone di pagamento) è visibile all'interno del Facebook Shop incorporato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il tuo Facebook Shop avrà un piè di pagina familiare, mantenendo la coerenza del marchio e fornendo link aggiuntivi.
        -   *Quando disabilitato:* Il piè di pagina sarà nascosto.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Il piè di pagina spesso contiene importanti link legali (informativa sulla privacy, termini di servizio) e informazioni di contatto, che è bene mantenere visibili per fiducia e conformità.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Impostazioni generali** | Visualizza aggiornamenti MyPresta.eu | SÌ | Ricevi notifiche di aggiornamento del modulo. |
| | Visualizzazione lingua Facebook Shop (`faceshop_lang_disp`) | SÌ | Consenti ai clienti di cambiare la lingua del negozio. |
| | Visualizzazione valuta Facebook Shop (`faceshop_curr_disp`) | SÌ | Consenti ai clienti di cambiare la valuta del negozio. |
| | Abilita riscrittura modulo (URL SEO friendly) (`faceshop_modrew`) | SÌ | Usa URL puliti e descrittivi per una migliore SEO e UX. |
| **Impostazioni homepage** | Visualizza conteggio elementi homepage (`faceshop_homepage_itemcount`) | 12-24 | Numero di prodotti mostrati sulla homepage. |
| | Visualizza prodotti scontati homepage (`faceshop_homepage_disphot`) | SÌ | Metti in evidenza i prodotti in saldo sulla homepage. |
| | Visualizza nuovi prodotti homepage (`faceshop_homepage_dispnew`) | SÌ | Metti in evidenza i nuovi arrivi sulla homepage. |
| | Visualizza categoria radice homepage (`faceshop_homepage_root`) | Vuoto (radice predefinita) | Seleziona una categoria specifica per i prodotti della homepage. |
| **Impostazioni intestazione** | Visualizza intestazione nel Facebook Shop (`faceshop_header_disp`) | SÌ | Mostra l'intestazione del tuo negozio (logo, ricerca, carrello). |
| **Impostazioni pagina categoria** | Categoria radice per Facebook Shop (`faceshop_cat_root`) | Home (radice predefinita) | Definisce la categoria di partenza per il Facebook Shop. |
| | Visualizza nuovi prodotti nelle pagine di categoria (`faceshop_cat_dispnew`) | SÌ | Evidenzia i nuovi prodotti all'interno delle categorie. |
| | Visualizza prodotti scontati nelle pagine di categoria (`faceshop_cat_disphot`) | SÌ | Evidenzia i prodotti in saldo all'interno delle categorie. |
| | Conteggio articoli per pagina di categoria (`faceshop_cat_itemcount`) | 12-24 | Numero di prodotti mostrati per pagina di categoria. |
| | Stile di visualizzazione categoria (`faceshop_cat_dispstyle`) | Vista a griglia | Come vengono presentate le categorie (griglia/elenco). |
| **Impostazioni slider** | Visualizza slider nel Facebook Shop (`faceshop_slider_disp`) | SÌ | Mostra uno slider di immagini/prodotti. |
| | Tempo di transizione slider (in millisecondi) (`faceshop_slider_time`) | 4000-6000 | Velocità delle transizioni delle slide. |
| | Posizionamento slider (`faceshop_slider_place`) | In alto | Posizione dello slider (es. in cima alla pagina). |
| **Impostazioni menu** | Visualizza link nuovi prodotti nel menu (`faceshop_menu_newproducts`) | SÌ | Aggiungi "Nuovi prodotti" al menu di navigazione. |
| | Visualizza link prodotti in saldo nel menu (`faceshop_menu_saleproducts`) | SÌ | Aggiungi "Prodotti in saldo" al menu di navigazione. |
| | Visualizza link pagine informative nel menu (`faceshop_menu_informations`) | SÌ | Aggiungi link alle pagine CMS (Chi siamo, ecc.). |
| | Visualizza link pagina contatti nel menu (`faceshop_menu_contact`) | SÌ | Aggiungi un link "Contattaci". |
| | Stile di visualizzazione categoria menu (`faceshop_menu_catstyle`) | Menu a discesa | Come appaiono le categorie nel menu (a discesa/elenco). |
| | Visualizza link produttori nel menu (`faceshop_menu_manuf`) | SÌ | Aggiungi un link a produttori/marchi. |
| **Impostazioni pagina prodotto** | Visualizza navigazione breadcrumb (`faceshop_display_breadcrumb`) | SÌ | Mostra il percorso di navigazione (Home > Categoria > Prodotto). |
| | Taglia descrizione prodotto (`faceshop_pdisp_trim`) | SÌ | Accorcia le descrizioni lunghe dei prodotti. |
| | Visualizza prezzo prodotto (`faceshop_pdisp_price`) | SÌ | Mostra il prezzo del prodotto. |
| | Visualizza nome prodotto (`faceshop_pdisp_name`) | SÌ | Mostra il nome del prodotto. |
| | Visualizza immagine prodotto (`faceshop_pdisp_image`) | SÌ | Mostra le immagini del prodotto. |
| **Impostazioni condivisione social** | Visualizza pulsante Condividi su Facebook (`faceshop_social_facebook`) | SÌ | Consenti la condivisione su Facebook. |
| | Visualizza pulsante Condividi su Pinterest (`faceshop_social_pinterest`) | SÌ | Consenti la condivisione su Pinterest. |
| | Visualizza pulsante Condividi su Google+ (`faceshop_social_google`) | NO | Google+ è stato disattivato. |
| **Impostazioni piè di pagina** | Visualizza piè di pagina nel Facebook Shop (`faceshop_footer_disp`) | SÌ | Mostra il piè di pagina del tuo negozio. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Il mio Facebook Shop non viene visualizzato o vedo un messaggio di errore.**
R1:

-   **Controlla SSL:** Assicurati che il tuo negozio PrestaShop abbia un certificato SSL valido (HTTPS). Facebook richiede connessioni sicure per le applicazioni incorporate. Se il tuo negozio non è HTTPS, il Facebook Shop non verrà caricato.
-   **Impostazioni pagina Facebook:** Ricontrolla di essere un amministratore della Pagina Fan di Facebook e che la scheda "Shop" sia correttamente aggiunta e configurata su Facebook stesso.
-   **Configurazione modulo:** Torna alla configurazione del modulo in PrestaShop e assicurati che tutte le impostazioni siano state salvate correttamente.
-   **Svuota cache:** In PrestaShop, vai su **Parametri avanzati > Prestazioni** e svuota la cache di Smarty, la cache del browser e qualsiasi altra cache.

**D2: I prodotti non vengono visualizzati correttamente o mancano le immagini.**
R2:

-   **Impostazioni prodotto:** Verifica che i prodotti che ti aspetti di vedere siano attivi e visibili nel tuo negozio PrestaShop principale.
-   **Percorsi immagini:** Assicurati che le tue immagini prodotto abbiano percorsi corretti e siano accessibili pubblicamente.
-   **Impostazioni modulo:** Controlla le impostazioni `faceshop_pdisp_image`, `faceshop_pdisp_name`, `faceshop_pdisp_price` per assicurarti che siano abilitate.
-   **Categoria radice:** Conferma che le tue impostazioni `faceshop_cat_root` e `faceshop_homepage_root` puntino correttamente a categorie che contengono prodotti.

**D3: Il modulo appare diverso sui dispositivi mobili all'interno di Facebook.**
R3:

-   **App Facebook vs. Browser:** L'esperienza può variare leggermente tra l'app mobile di Facebook e l'accesso a Facebook tramite un browser mobile. Il modulo è progettato per essere reattivo, ma il wrapper di Facebook stesso può influenzare l'aspetto finale.
-   **Controlla la reattività:** Testa il tuo negozio PrestaShop principale su mobile per assicurarti che sia completamente reattivo. Il Facebook Shop eredita gran parte del suo stile dal tuo negozio principale.
-   **CSS personalizzato:** Se hai CSS personalizzati nel tuo tema PrestaShop, potrebbero interferire. Consulta uno sviluppatore web per ispezionare il CSS all'interno dell'iframe di Facebook.

**D4: Come posso tradurre il Facebook Shop in altre lingue?**
R4:

-   **Traduzioni PrestaShop:** Il modulo Facebook Shop estrae i contenuti (nomi prodotti, descrizioni, nomi categorie) direttamente dal tuo negozio PrestaShop. Assicurati che tutti i tuoi contenuti di prodotti e categorie siano tradotti all'interno di PrestaShop stesso.
-   **Testo del modulo:** Per il testo dell'interfaccia del modulo (es. link "Nuovi prodotti"), vai su **Internazionale > Traduzioni** nel Back Office di PrestaShop. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, la tua lingua, e poi trova il modulo "Facebook Shop" per tradurre le sue stringhe specifiche.
-   **Selettore lingua:** Assicurati che `faceshop_lang_disp` sia abilitato nella configurazione del modulo per consentire ai clienti di cambiare lingua.

**D5: Il mio Facebook Shop è lento a caricare.**
R5:

-   **Ottimizzazione immagini:** Assicurati che le tue immagini prodotto siano ottimizzate per l'uso web (compresse, dimensioni appropriate). Le immagini grandi sono una causa comune di caricamento lento.
-   **Prestazioni hosting:** Controlla le prestazioni del tuo hosting web. Un server lento influenzerà sia il tuo negozio principale che il tuo Facebook Shop.
-   **Numero di prodotti:** Se stai visualizzando un numero molto elevato di prodotti sulla homepage o sulle pagine di categoria (`faceshop_homepage_itemcount`, `faceshop_cat_itemcount`), considera di ridurre questi numeri.
-   **Caching:** Assicurati che i meccanismi di caching di PrestaShop siano correttamente configurati (**Parametri avanzati > Prestazioni**).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Facebook Shop (`faceshop`) è progettato come un modulo PrestaShop standard, estendendo principalmente la classe `Module`. Sfrutta il sistema di configurazione di PrestaShop (`Configuration::get()`, `Configuration::updateValue()`) per memorizzare le sue impostazioni. La funzionalità principale del modulo consiste nel renderizzare una versione semplificata del front-office di PrestaShop all'interno di un iframe su una Pagina Fan di Facebook. Ciò si ottiene regolando dinamicamente la visualizzazione in base a un parametro URL specifico (`?fc=module&module=faceshop&controller=shop`). Il modulo non introduce tabelle di database personalizzate o ObjectModels complessi, ma piuttosto manipola la visualizzazione esistente del front-office di PrestaShop tramite hook e override di template.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene controller dedicati per il front-office o il back-office nella directory `controllers/`.
La sua funzionalità di front-office è gestita principalmente dal file principale `faceshop.php`, che intercetta le richieste tramite un parametro controller `shop` personalizzato (es. `index.php?fc=module&module=faceshop&controller=shop`). Questo approccio consente al modulo di renderizzare una versione modificata del front-office standard di PrestaShop all'interno dell'iframe di Facebook, piuttosto che creare strutture di pagina completamente nuove.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo **non** introduce classi o ObjectModels personalizzati in una directory `classes/`. Tutta la logica principale è incapsulata nel file principale `faceshop/faceshop.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include diversi file JavaScript, principalmente per migliorare la visualizzazione del front-office all'interno dell'iframe di Facebook.

-   `faceshop/jscolor/jscolor.js`
    -   **Ambito:** Back-office (probabilmente utilizzato nel modulo di configurazione).
    -   **Descrizione:** Una libreria JavaScript per un selettore di colori. Permette agli amministratori di selezionare facilmente i colori per le impostazioni del modulo, sebbene non siano state identificate impostazioni di colore esplicite nelle chiavi di configurazione, è un'utilità comune per la personalizzazione dell'interfaccia utente.
-   `faceshop/js/advajax.js`
    -   **Ambito:** Front-office (all'interno dell'iframe di Facebook).
    -   **Descrizione:** Probabilmente uno script di utilità AJAX personalizzato. Gestirebbe le richieste asincrone per il caricamento dei dati dei prodotti, la paginazione o altri contenuti dinamici all'interno del Facebook Shop senza ricaricare l'intera pagina. Ciò migliora l'esperienza utente rendendo il negozio più reattivo.
-   `faceshop/js/jquery.nivo.slider.pack.js`
    -   **Ambito:** Front-office (all'interno dell'iframe di Facebook).
    -   **Descrizione:** Una versione compressa del plugin jQuery Nivo Slider. Questo script è responsabile della funzionalità dello slider di immagini (`faceshop_slider_disp`) sulla homepage del Facebook Shop, gestendo transizioni, navigazione e riproduzione automatica.
-   `faceshop/js/shop2.js`
    -   **Ambito:** Front-office (all'interno dell'iframe di Facebook).
    -   **Descrizione:** Questo è probabilmente il file JavaScript personalizzato principale per la logica front-end del Facebook Shop. Contenerebbe codice per:
        -   Inizializzare il Nivo Slider.
        -   Gestire il caricamento dinamico dei contenuti (es. pulsanti "Carica altro" per i prodotti).
        -   Regolare il layout o il comportamento specificamente per l'ambiente dell'iframe di Facebook.
        -   Potenzialmente gestire le interazioni con l'SDK di Facebook (sebbene non esplicitamente menzionato, comune per le app di Facebook).
        -   Qualsiasi miglioramento dell'interfaccia utente personalizzato o listener di eventi specifici per il negozio incorporato.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include diversi file CSS per stilizzare il Facebook Shop incorporato, garantendo che abbia un aspetto coerente e funzioni correttamente all'interno dell'iframe.

-   `faceshop/css.css`
    -   **Ambito:** Front-office (all'interno dell'iframe di Facebook).
    -   **Descrizione:** Un foglio di stile generale per il Facebook Shop. Probabilmente contiene regole di layout di base, tipografia e stile di base per elementi comuni (pulsanti, link, moduli) per garantire un aspetto coerente.
-   `faceshop/css/style.css`
    -   **Ambito:** Front-office (all'interno dell'iframe di Facebook).
    -   **Descrizione:** Questo potrebbe essere un foglio di stile più specifico, potenzialmente che sovrascrive o estende `css.css`. Potrebbe contenere stili per funzionalità specifiche del modulo o regolazioni del layout per adattarsi meglio all'ambiente di Facebook.
-   `faceshop/default/default.css`
    -   **Ambito:** Front-office (all'interno dell'iframe di Facebook).
    -   **Descrizione:** Questo foglio di stile fa probabilmente parte del plugin Nivo Slider, fornendo uno stile predefinito per la navigazione, le didascalie e l'aspetto generale dello slider. Gli sviluppatori possono sovrascrivere questi stili per abbinarli al tema del negozio.
-   `faceshop/style.css`
    -   **Ambito:** Front-office (all'interno dell'iframe di Facebook).
    -   **Descrizione:** Simile a `faceshop/css/style.css`, questo potrebbe essere un altro foglio di stile primario o un file di fallback/legacy. Definirebbe la presentazione visiva degli elementi del negozio, assicurando che siano renderizzati correttamente all'interno dell'iframe di Facebook.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il dossier del modulo indica che non sono stati trovati file `.tpl` specifici in `views/templates/`. Ciò suggerisce che il modulo funziona principalmente:

1.  **Intercettando le richieste standard del front-office di PrestaShop:** Quando si accede tramite l'URL del Facebook Shop, il modulo probabilmente modifica le variabili globali di Smarty o i percorsi dei template per renderizzare i template del tema PrestaShop esistenti.
2.  **Utilizzando i metodi `display` all'interno di `faceshop.php`:** I metodi `display()` del modulo potrebbero renderizzare direttamente HTML o includere frammenti dal tema principale di PrestaShop, aggiungendo o rimuovendo dinamicamente elementi in base alla sua configurazione.
3.  **Rendering basato su JavaScript:** Alcuni elementi potrebbero essere iniettati o modificati dinamicamente dai file JavaScript dopo il caricamento iniziale della pagina.

Se fossero presenti template personalizzati, si troverebbero tipicamente in:

-   `views/templates/hook/`: Per contenuti renderizzati in specifici hook di PrestaShop.
-   `views/templates/admin/`: Per moduli o visualizzazioni personalizzate del back-office.
-   `views/templates/front/`: Per pagine front-office autonome o contenuti specifici del modulo.

L'assenza di file `.tpl` espliciti implica una manipolazione più diretta del processo di rendering esistente del front-office di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle di database personalizzate. Tutte le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` (o `_configuration` a seconda del prefisso della tabella) utilizzando le chiavi di configurazione elencate nella sezione 4.1.
-   **Tabella degli hook registrati**:
    Il modulo interagisce principalmente con la visualizzazione del front-office di PrestaShop. Sebbene il dossier elenchi "Intestazione, Colonne, Prodotto o Piè di pagina" come hook del front-office, la funzionalità principale del modulo è quella di incorporare l'*intero* front-office. Probabilmente utilizza una combinazione di:

    -   **`hookDisplayHeader`**: Per iniettare i suoi asset CSS e JavaScript e potenzialmente per modificare la sezione `<head>` per la compatibilità con l'iframe di Facebook.
    -   **`hookDisplayFooter`**: Per iniettare script o contenuti aggiuntivi nella parte inferiore della pagina.
    -   **`actionFrontControllerSetMedia`**: (PrestaShop 1.7+) Per registrare i suoi file CSS e JS.
    -   **Logica interna per il rendering del negozio**: Il modulo probabilmente ha una logica interna che, quando rileva di essere caricato all'interno dell'iframe di Facebook, modifica l'output standard del front-office di PrestaShop per nascondere/mostrare elementi in base alle sue impostazioni di configurazione (es. `faceshop_header_disp`, `faceshop_footer_disp`). Ciò si ottiene spesso sovrascrivendo o manipolando le variabili Smarty e le assegnazioni dei template all'interno dei metodi `display()` o `hook` del modulo.

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Prima del contenuto principale della pagina, all'interno della sezione `<head>`. | Inietta i file CSS e JavaScript del modulo, potenzialmente modifica i meta tag per l'iframe di Facebook. |
| `displayFooter` | Alla fine del contenuto della pagina, prima del tag di chiusura `</body>`. | Inietta script o codici di tracciamento aggiuntivi, o modifica il contenuto del piè di pagina se `faceshop_footer_disp` è abilitato. |
| `actionFrontControllerSetMedia` (PS 1.7+) | Durante la fase di impostazione dei media di un controller frontale. | Registra i file CSS e JS per un caricamento ottimale. |
| (Implicito) Hook pagina prodotto | Nelle pagine di dettaglio del prodotto. | Modifica la visualizzazione della pagina prodotto in base a `faceshop_pdisp_trim`, `faceshop_pdisp_price`, ecc., e inietta i pulsanti di condivisione social. |
| (Implicito) Hook pagina categoria | Nelle pagine di elenco delle categorie. | Modifica la visualizzazione della pagina categoria in base a `faceshop_cat_dispnew`, `faceshop_cat_disphot`, ecc. |
| (Implicito) Hook homepage | Sulla homepage del negozio. | Renderizza slider, prodotti in evidenza, nuovi prodotti e prodotti scontati in base alle impostazioni del modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il tuo modulo Facebook Shop, fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team è dedicato a garantire che il tuo modulo funzioni in modo ottimale e ti aiuti a massimizzare le tue vendite online.

-   **MyPresta.eu Cronologia ordini e download:** <https://mypresta.eu/my-account/orders/>
-   **Contatto supporto MyPresta.eu:** <https://mypresta.eu/contact>
