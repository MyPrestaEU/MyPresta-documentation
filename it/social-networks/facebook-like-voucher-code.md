---
title: "Codice voucher Facebook like - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Codice voucher Facebook like' di MyPresta.eu."
sidebar:
  label: "Codice voucher Facebook like"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook like voucher code su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-voucher-code.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-like-voucher-code/)
>
> ---


# Codice voucher Facebook like

## 1. Requisiti e compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e per qualsiasi modulo che interagisca con API esterne come Facebook.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Questa è la schermata di configurazione principale per il modulo "Codice voucher Facebook like", accessibile dopo l'installazione cliccando sul pulsante "Configura". Qui definirai come appare il pulsante Mi piace di Facebook e come vengono generati i codici voucher.

#### **URL della pagina Facebook**
- **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Indica al modulo quale pagina Facebook i tuoi clienti dovrebbero "mettere mi piace" per ricevere il voucher.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato sull'URL della tua pagina Facebook (es. `https://www.facebook.com/MyPresta.eu`):* Il pulsante "Mi piace" sul tuo negozio si collegherà direttamente e traccerà i mi piace per questa specifica pagina Facebook.
  - *Quando lasciato vuoto o impostato in modo errato:* Il pulsante "Mi piace" non funzionerà correttamente, o potrebbe collegarsi a una pagina inesistente, impedendo ai clienti di ricevere i voucher.
- **Valore consigliato:** Inserisci l'URL completo della tua pagina aziendale ufficiale di Facebook.
- **Scenario / esempio del commerciante:** Se la tua pagina Facebook è `https://www.facebook.com/myawesomestore`, dovresti inserire esattamente quell'URL qui.

#### **Prefisso codice voucher**
- **Cosa fa questa impostazione:** Ti permette di aggiungere un prefisso personalizzato a tutti i codici voucher generati da questo modulo. Questo ti aiuta a identificare facilmente quali voucher provengono dalla tua promozione Facebook.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "FB":* Tutti i codici voucher generati inizieranno con "FB" (es. FB123456).
  - *Quando lasciato vuoto:* I codici voucher verranno generati senza un prefisso specifico, rendendoli più difficili da distinguere da altri tipi di voucher.
- **Valore consigliato:** Un prefisso breve e memorabile come "FB", "LIKE" o "SOCIAL".
- **Scenario / esempio del commerciante:** L'uso di "FB" ti consente di filtrare rapidamente i tuoi codici voucher nel Back Office di PrestaShop per vedere quanti sono stati generati tramite questo modulo.

#### **Valore codice voucher**
- **Cosa fa questa impostazione:** Definisce il valore di sconto del codice voucher. Questo può essere un importo fisso o una percentuale.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "10" e "Percentuale":* I clienti ricevono uno sconto del 10%.
  - *Quando impostato su "5" e "Importo":* I clienti ricevono uno sconto di $5 (o la tua valuta predefinita).
- **Valore consigliato:** Un valore sufficientemente attraente da incoraggiare un acquisto ma anche sostenibile per i tuoi margini di profitto (es. 5, 10, 15).
- **Scenario / esempio del commerciante:** Offrire "10" e "Percentuale" per uno sconto del 10% è una strategia comune ed efficace per incoraggiare i nuovi acquirenti.

#### **Tipo codice voucher**
- **Cosa fa questa impostazione:** Determina se il codice voucher offre uno sconto percentuale o uno sconto a importo fisso.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "Percentuale":* Il "Valore codice voucher" verrà interpretato come una percentuale (es. 10% di sconto).
  - *Quando impostato su "Importo":* Il "Valore codice voucher" verrà interpretato come un importo monetario fisso (es. $10 di sconto).
- **Valore consigliato:** "Percentuale" è spesso più attraente in quanto si adatta al valore dell'ordine, ma "Importo" può essere efficace per articoli a basso prezzo o promozioni specifiche.
- **Scenario / esempio del commerciante:** Se vuoi dare uno sconto fisso di $5 indipendentemente dalla dimensione dell'ordine, scegli "Importo". Se vuoi dare uno sconto che aumenta con il valore dell'ordine, scegli "Percentuale".

#### **Importo minimo codice voucher**
- **Cosa fa questa impostazione:** Imposta un totale minimo dell'ordine (prima della spedizione) che un cliente deve raggiungere per poter utilizzare il codice voucher.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "50":* Il voucher può essere utilizzato solo se il totale del carrello è di $50 o più.
  - *Quando lasciato vuoto o impostato su "0":* Il voucher può essere utilizzato su qualsiasi importo dell'ordine.
- **Valore consigliato:** Un valore che incoraggi i clienti ad aggiungere più articoli al carrello, aumentando il valore medio dell'ordine (es. 25, 50).
- **Scenario / esempio del commerciante:** Se il tuo valore medio dell'ordine è di $40, impostare un importo minimo di $50 per un voucher del 10% incoraggia i clienti ad aggiungere un articolo extra per qualificarsi per lo sconto.

#### **Giorni di scadenza codice voucher**
- **Cosa fa questa impostazione:** Definisce quanti giorni il codice voucher generato sarà valido dal momento in cui viene emesso.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "7":* Il codice voucher scadrà 7 giorni dopo che il cliente lo ha ricevuto.
  - *Quando lasciato vuoto o impostato su "0":* Il codice voucher non avrà una data di scadenza (o una data predefinita molto lunga impostata da PrestaShop).
- **Valore consigliato:** Un lasso di tempo ragionevole per creare urgenza senza essere troppo restrittivo (es. 7, 14, 30 giorni).
- **Scenario / esempio del commerciante:** Impostarlo a "7" giorni incoraggia i clienti a effettuare un acquisto prima piuttosto che dopo, impedendo loro di dimenticare il voucher.

#### **Descrizione codice voucher**
- **Cosa fa questa impostazione:** Ti permette di aggiungere una descrizione personalizzata al codice voucher generato nel tuo Back Office di PrestaShop. Questo ti aiuta a tenere traccia dello scopo del voucher.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "Promozione Mi piace Facebook":* Questa descrizione sarà visibile quando visualizzi i dettagli del voucher nel tuo Back Office di PrestaShop, rendendo chiaro da dove proviene il voucher.
  - *Quando lasciato vuoto:* Il voucher non avrà una descrizione specifica, rendendo più difficile identificarne la fonte.
- **Valore consigliato:** Una descrizione chiara e concisa come "Voucher Mi piace Facebook" o "Promo Social Media".
- **Scenario / esempio del commerciante:** L'uso di "Promozione Mi piace Facebook" aiuta il tuo team di assistenza clienti a comprendere il contesto del voucher se un cliente ha domande al riguardo.

#### **Visualizza blocco in**
- **Cosa fa questa impostazione:** Determina dove apparirà il blocco del pulsante "Mi piace" di Facebook nel front office del tuo negozio.
- **Effetto della modifica di questa impostazione:**
  - *Quando è selezionato "Intestazione":* Il blocco appare nella parte superiore di ogni pagina.
  - *Quando è selezionato "Colonna sinistra":* Il blocco appare nella barra laterale sinistra.
  - *Quando è selezionato "Colonna destra":* Il blocco appare nella barra laterale destra.
  - *Quando è selezionato "Pagina prodotto":* Il blocco appare sulle singole pagine dei prodotti.
  - *Quando è selezionato "Piè di pagina":* Il blocco appare nella parte inferiore di ogni pagina.
- **Valore consigliato:** "Intestazione" o "Pagina prodotto" per la massima visibilità e impatto, o "Colonna sinistra/destra" se preferisci un posizionamento meno invasivo.
- **Scenario / esempio del commerciante:** Posizionarlo nell'"Intestazione" assicura che ogni visitatore lo veda. Posizionarlo sulla "Pagina prodotto" si rivolge ai clienti che sono già interessati a fare un acquisto.

#### **Messaggio popup codice voucher**
- **Cosa fa questa impostazione:** Questo è il messaggio che i clienti vedranno nella finestra popup insieme al loro codice voucher dopo aver "messo mi piace" alla tua pagina Facebook.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "Grazie per averci messo mi piace! Ecco il tuo codice sconto: {voucher_code}":* Il cliente vedrà esattamente questo messaggio con il suo codice unico inserito.
  - *Quando lasciato vuoto:* Il cliente potrebbe vedere solo il codice senza alcun testo di accompagnamento, il che potrebbe essere confuso.
- **Valore consigliato:** Un messaggio amichevole e chiaro che ringrazia il cliente e dichiara esplicitamente che il codice è per uno sconto. **Includi sempre `{voucher_code}`** in modo che il codice effettivo venga visualizzato.
- **Scenario / esempio del commerciante:** "Grazie per esserti unito alla nostra community! Ecco un regalo speciale per te: {voucher_code}. Buono shopping!"

#### **Titolo popup codice voucher**
- **Cosa fa questa impostazione:** Imposta il titolo della finestra popup che visualizza il codice voucher.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "Il tuo sconto esclusivo!":* Questo titolo apparirà nella parte superiore della finestra popup.
  - *Quando lasciato vuoto:* Il popup potrebbe avere un titolo generico o nessun titolo, il che è meno professionale.
- **Valore consigliato:** Un titolo accattivante e chiaro che rafforzi la ricompensa (es. "Il tuo voucher gratuito!", "Grazie per averci messo mi piace!").
- **Scenario / esempio del commerciante:** "Il tuo sconto esclusivo!" dice immediatamente al cliente che ha ricevuto una ricompensa preziosa.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto
