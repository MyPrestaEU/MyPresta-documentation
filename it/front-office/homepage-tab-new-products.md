---
title: "Scheda prodotti nuovi in homepage - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Homepage tab new products' di MyPresta.eu."
sidebar:
  label: "Scheda prodotti nuovi in homepage"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homepage tab new products su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-new-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homepage-tab-new-products/)
>
> ---


# Scheda prodotti nuovi in homepage

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, clicca su "Configura" accanto al modulo "Homepage tab new products" in Gestione moduli. Verrai reindirizzato alla schermata di configurazione principale.

#### **Numero di prodotti da visualizzare**
-   **Cosa fa questa impostazione:** Controlla quanti dei tuoi prodotti più recenti verranno mostrati nella scheda "Nuovi Prodotti" sulla tua homepage.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su un numero più alto (es. 12):* Più nuovi prodotti saranno visibili ai clienti senza che debbano navigare a una pagina completa "Nuovi Prodotti". Questo può essere ottimo per i negozi con un alto volume di nuovi arrivi.
    -   *Se impostato su un numero più basso (es. 4):* Verranno visualizzati meno prodotti, con un aspetto più pulito e meno ingombrante. Questo potrebbe essere preferito se si desidera evidenziare solo gli articoli più freschi o si ha spazio limitato.
-   **Valore consigliato:** Inizia con `8` o `12`. Regola in base al layout del tuo tema e a quanti prodotti aggiungi tipicamente.
-   **Scenario / esempio del commerciante:** Se gestisci un negozio di moda e aggiungi 20 nuovi articoli settimanalmente, impostare questo valore a `12` assicura che una buona selezione sia sempre visibile. Se vendi prodotti di nicchia di alto valore e aggiungi solo 2-3 nuovi articoli al mese, `4` potrebbe essere sufficiente per evitare spazi vuoti.

#### **Classi dell'elenco prodotti**
-   **Cosa fa questa impostazione:** Questa impostazione avanzata ti consente di aggiungere classi CSS personalizzate al contenitore che ospita l'elenco dei nuovi prodotti. Questo è utilizzato principalmente per scopi di stile, spesso per integrarsi perfettamente con il design specifico del tuo tema PrestaShop.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando vengono aggiunte classi (es. `product-grid-container my-custom-style`):* Il CSS del tuo tema o il tuo CSS personalizzato possono quindi mirare a queste classi per applicare uno stile specifico (es. modificare il layout delle colonne, la spaziatura, le dimensioni dei caratteri, i colori) all'elenco dei nuovi prodotti.
    -   *Se lasciato vuoto:* Il modulo utilizzerà il suo stile predefinito o erediterà gli stili dall'elenco generale dei prodotti del tuo tema.
-   **Valore consigliato:** Lascia vuoto a meno che tu o il tuo sviluppatore web non abbiate bisogno di applicare uno stile personalizzato specifico all'elenco dei prodotti. Se non sei sicuro, non modificare questa impostazione.
-   **Scenario / esempio del commerciante:** Il tuo tema visualizza le griglie dei prodotti con 3 colonne, ma desideri che la scheda "Nuovi Prodotti" mostri 4 colonne. Il tuo sviluppatore web potrebbe dirti di aggiungere una classe come `col-lg-3` (se il tuo tema utilizza le classi di griglia di Bootstrap) qui, quindi aggiungere CSS personalizzato per farlo funzionare.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione           | Predefinito / Consigliato | Scopo e Impatto
|---|---|---|---
| Pagina di configurazione del modulo | Numero di prodotti da visualizzare | 8 o 12 | Controlla quanti prodotti recenti vengono mostrati nella scheda "Nuovi Prodotti". Influisce sulla visibilità e sull'ingombro.
| Pagina di configurazione del modulo | Classi dell'elenco prodotti | Vuoto | Consente l'aggiunta di classi CSS personalizzate per lo styling avanzato dell'elenco dei prodotti. Utilizzato per l'integrazione del tema.
