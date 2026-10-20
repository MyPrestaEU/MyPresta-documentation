---
title: "Attivazione account tramite link email - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Attivazione account tramite link email' di MyPresta.eu."
sidebar:
  label: "Attivazione account tramite link email - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Account activation by email link su MyPresta.eu](https://mypresta.eu/modules/front-office-features/account-activation-by-email-link.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/account-activation-by-email-link/)
>
> ---


# Attivazione account tramite link email

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Attivazione account tramite link email". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### **Impostazioni Generali**

-   **Invia email con link di attivazione account all'amministratore:**

    -   **Cosa fa questa impostazione:** Controlla se una notifica email viene inviata anche all'amministratore del negozio (tu) ogni volta che un nuovo cliente si registra e deve attivare il proprio account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Riceverai una notifica email all'indirizzo email di contatto principale del tuo negozio (solitamente `PS_SHOP_EMAIL`) ogni volta che un nuovo cliente si registra ed è in attesa di attivazione. Questo può essere utile per monitorare le nuove registrazioni.
        -   *Quando disabilitato ("No"):* Nessuna notifica email verrà inviata all'amministratore al momento della nuova registrazione del cliente.
    -   **Valore consigliato:** "No" per la maggior parte dei negozi per evitare l'ingombro della posta elettronica, a meno che tu non abbia specificamente bisogno di monitorare ogni nuova registrazione.
    -   **Scenario / esempio del commerciante:** Se gestisci un piccolo negozio di nicchia e desideri accogliere personalmente o rivedere ogni nuovo cliente, abilitare questa opzione può tenerti informato. Per i negozi più grandi, di solito è inutile.
-   **Titolo dell'email all'amministratore:**

    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email inviata all'amministratore quando viene registrato un nuovo account (se "Invia email con link di attivazione account all'amministratore" è abilitato).
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto dell'email di notifica all'amministratore.
    -   **Valore consigliato:** "Nuova registrazione cliente in attesa di attivazione - {shop\_name}" (o simile, usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Potresti voler includere il nome del tuo negozio nel titolo per una facile identificazione nella tua casella di posta, ad esempio, "Nuovo Cliente su Il Mio Fantastico Negozio - Attivazione in Sospeso."
-   **Accesso automatico del cliente dopo l'attivazione:**

    -   **Cosa fa questa impostazione:** Determina se un cliente viene automaticamente loggato nel proprio account immediatamente dopo aver cliccato sul link di attivazione nella propria email.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Dopo aver cliccato sul link di attivazione, il cliente viene loggato senza problemi nel suo account appena attivato e tipicamente reindirizzato alla sua dashboard account o alla homepage. Questo offre un'esperienza utente più fluida.
        -   *Quando disabilitato ("No"):* Dopo aver cliccato sul link di attivazione, l'account del cliente viene attivato, ma *non* viene automaticamente loggato. Verrà reindirizzato alla pagina di login e gli verrà chiesto di inserire manualmente le proprie credenziali.
    -   **Valore consigliato:** "Sì" per una migliore esperienza del cliente, riducendo l'attrito.
    -   **Scenario / esempio del commerciante:** Abilitare questa opzione rende il processo di attivazione più completo e user-friendly, poiché il cliente non deve fare un passaggio extra dopo aver verificato la propria email.
-   **Attiva account su pagina specifica:**

    -   **Cosa fa questa impostazione:** Ti consente di definire una pagina specifica del tuo negozio dove il cliente verrà reindirizzato *dopo* che il suo account è stato attivato con successo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo utilizzerà l'URL specificato nel campo "Link pagina di attivazione specifica" per il reindirizzamento dopo l'attivazione.
        -   *Quando disabilitato ("No"):* Il cliente verrà reindirizzato alla pagina predefinita (solitamente la homepage o la sua pagina account cliente) dopo l'attivazione.
    -   **Valore consigliato:** "No" per impostazione predefinita, a meno che tu non abbia una strategia di marketing o di onboarding specifica.
    -   **Scenario / esempio del commerciante:** Potresti voler reindirizzare i nuovi clienti a una pagina "Benvenuto" con offerte speciali, una guida al tuo negozio o una categoria di prodotti specifica per incoraggiare il loro primo acquisto.
-   **Link pagina di attivazione specifica:**

    -   **Cosa fa questa impostazione:** Questo campo appare solo se "Attiva account su pagina specifica" è abilitato. È qui che inserisci l'URL completo della pagina a cui vuoi reindirizzare i clienti dopo l'attivazione.
    -   **Effetto della modifica di questa impostazione:** Definisce l'esatto URL di destinazione per il reindirizzamento post-attivazione.
    -   **Valore consigliato:** Lascia vuoto se "Attiva account su pagina specifica" è "No". Se abilitato, fornisci un URL completo e valido (ad esempio, `https://tuonegozio.com/content/1-consegna`).
    -   **Scenario / esempio del commerciante:** Se hai una pagina "Benvenuto Nuovo Cliente" all'indirizzo `https://tuonegozio.com/benvenuto-nuovi-clienti`, dovresti inserire quell'URL qui.

#### **Impostazioni Contenuto Email**

-   **Titolo dell'email al cliente:**
    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email di attivazione inviata al cliente.
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto che i clienti vedono nella loro casella di posta per l'email di attivazione.
    -   **Valore consigliato:** "Attiva il tuo account su {shop\_name}" o "Verifica la tua email per {shop\_name}" (usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Un oggetto chiaro e conciso aiuta i clienti a identificare l'email e li incoraggia ad aprirla, riducendo la possibilità che venga contrassegnata come spam.

#### **Altre Impostazioni (Interne / Tecniche)**

-   **mypresta\_updates, update\_, updatev\_:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni. In generale, **non** dovresti modificarle.
-   **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Questi sono valori di configurazione standard di PrestaShop che il modulo potrebbe leggere o visualizzare per contesto, ma non sono direttamente configurabili all'interno del modulo stesso. Riflettono le tue impostazioni generali di PrestaShop.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :--- | :--- | :--- | :---
---
title: "Account activation by email link - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Account activation by email link PrestaShop module by MyPresta.eu."
sidebar:
  label: "Account activation by email link - Merchant Manual & Configuration Guide"
---

# Attivazione account tramite link email

## 3. Requisiti e Compatibilità

-   **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 4. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 4.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Attivazione account tramite link email". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### **Impostazioni Generali**

-   **Invia email con link di attivazione account all'amministratore:**

    -   **Cosa fa questa impostazione:** Controlla se una notifica email viene inviata anche all'amministratore del negozio (tu) ogni volta che un nuovo cliente si registra e deve attivare il proprio account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Riceverai una notifica email all'indirizzo email di contatto principale del tuo negozio (solitamente `PS_SHOP_EMAIL`) ogni volta che un nuovo cliente si registra ed è in attesa di attivazione. Questo può essere utile per monitorare le nuove registrazioni.
        -   *Quando disabilitato ("No"):* Nessuna notifica email verrà inviata all'amministratore al momento della nuova registrazione del cliente.
    -   **Valore consigliato:** "No" per la maggior parte dei negozi per evitare l'ingombro della posta elettronica, a meno che tu non abbia specificamente bisogno di monitorare ogni nuova registrazione.
    -   **Scenario / esempio del commerciante:** Se gestisci un piccolo negozio di nicchia e desideri accogliere personalmente o rivedere ogni nuovo cliente, abilitare questa opzione può tenerti informato. Per i negozi più grandi, di solito è inutile.
-   **Titolo dell'email all'amministratore:**

    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email inviata all'amministratore quando viene registrato un nuovo account (se "Invia email con link di attivazione account all'amministratore" è abilitato).
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto dell'email di notifica all'amministratore.
    -   **Valore consigliato:** "Nuova registrazione cliente in attesa di attivazione - {shop\_name}" (o simile, usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Potresti voler includere il nome del tuo negozio nel titolo per una facile identificazione nella tua casella di posta, ad esempio, "Nuovo Cliente su Il Mio Fantastico Negozio - Attivazione in Sospeso."
-   **Accesso automatico del cliente dopo l'attivazione:**

    -   **Cosa fa questa impostazione:** Determina se un cliente viene automaticamente loggato nel proprio account immediatamente dopo aver cliccato sul link di attivazione nella propria email.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Dopo aver cliccato sul link di attivazione, il cliente viene loggato senza problemi nel suo account appena attivato e tipicamente reindirizzato alla sua dashboard account o alla homepage. Questo offre un'esperienza utente più fluida.
        -   *Quando disabilitato ("No"):* Dopo aver cliccato sul link di attivazione, l'account del cliente viene attivato, ma *non* viene automaticamente loggato. Verrà reindirizzato alla pagina di login e gli verrà chiesto di inserire manualmente le proprie credenziali.
    -   **Valore consigliato:** "Sì" per una migliore esperienza del cliente, riducendo l'attrito.
    -   **Scenario / esempio del commerciante:** Abilitare questa opzione rende il processo di attivazione più completo e user-friendly, poiché il cliente non deve fare un passaggio extra dopo aver verificato la propria email.
-   **Attiva account su pagina specifica:**

    -   **Cosa fa questa impostazione:** Ti consente di definire una pagina specifica del tuo negozio dove il cliente verrà reindirizzato *dopo* che il suo account è stato attivato con successo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo utilizzerà l'URL specificato nel campo "Link pagina di attivazione specifica" per il reindirizzamento dopo l'attivazione.
        -   *Quando disabilitato ("No"):* Il cliente verrà reindirizzato alla pagina predefinita (solitamente la homepage o la sua pagina account cliente) dopo l'attivazione.
    -   **Valore consigliato:** "No" per impostazione predefinita, a meno che tu non abbia una strategia di marketing o di onboarding specifica.
    -   **Scenario / esempio del commerciante:** Potresti voler reindirizzare i nuovi clienti a una pagina "Benvenuto" con offerte speciali, una guida al tuo negozio o una categoria di prodotti specifica per incoraggiare il loro primo acquisto.
-   **Link pagina di attivazione specifica:**

    -   **Cosa fa questa impostazione:** Questo campo appare solo se "Attiva account su pagina specifica" è abilitato. È qui che inserisci l'URL completo della pagina a cui vuoi reindirizzare i clienti dopo l'attivazione.
    -   **Effetto della modifica di questa impostazione:** Definisce l'esatto URL di destinazione per il reindirizzamento post-attivazione.
    -   **Valore consigliato:** Lascia vuoto se "Attiva account su pagina specifica" è "No". Se abilitato, fornisci un URL completo e valido (ad esempio, `https://tuonegozio.com/content/1-consegna`).
    -   **Scenario / esempio del commerciante:** Se hai una pagina "Benvenuto Nuovo Cliente" all'indirizzo `https://tuonegozio.com/benvenuto-nuovi-clienti`, dovresti inserire quell'URL qui.

#### **Impostazioni Contenuto Email**

-   **Titolo dell'email al cliente:**
    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email di attivazione inviata al cliente.
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto che i clienti vedono nella loro casella di posta per l'email di attivazione.
    -   **Valore consigliato:** "Attiva il tuo account su {shop\_name}" o "Verifica la tua email per {shop\_name}" (usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Un oggetto chiaro e conciso aiuta i clienti a identificare l'email e li incoraggia ad aprirla, riducendo la possibilità che venga contrassegnata come spam.

#### **Altre Impostazioni (Interne / Tecniche)**

-   **mypresta\_updates, update\_, updatev\_:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni. In generale, **non** dovresti modificarle.
-   **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Questi sono valori di configurazione standard di PrestaShop che il modulo potrebbe leggere o visualizzare per contesto, ma non sono direttamente configurabili all'interno del modulo stesso. Riflettono le tue impostazioni generali di PrestaShop.

### 4.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :--- | :--- | :--- | :---
title: "Attivazione account tramite link email - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Attivazione account tramite link email' di MyPresta.eu."
sidebar:
  label: "Attivazione account tramite link email - Manuale Commerciante e Guida alla Configurazione"
---

# Attivazione account tramite link email

## 5. Requisiti e Compatibilità

-   **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 6. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 6.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Attivazione account tramite link email". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### **Impostazioni Generali**

-   **Invia email con link di attivazione account all'amministratore:**

    -   **Cosa fa questa impostazione:** Controlla se una notifica email viene inviata anche all'amministratore del negozio (tu) ogni volta che un nuovo cliente si registra e deve attivare il proprio account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Riceverai una notifica email all'indirizzo email di contatto principale del tuo negozio (solitamente `PS_SHOP_EMAIL`) ogni volta che un nuovo cliente si registra ed è in attesa di attivazione. Questo può essere utile per monitorare le nuove registrazioni.
        -   *Quando disabilitato ("No"):* Nessuna notifica email verrà inviata all'amministratore al momento della nuova registrazione del cliente.
    -   **Valore consigliato:** "No" per la maggior parte dei negozi per evitare l'ingombro della posta elettronica, a meno che tu non abbia specificamente bisogno di monitorare ogni nuova registrazione.
    -   **Scenario / esempio del commerciante:** Se gestisci un piccolo negozio di nicchia e desideri accogliere personalmente o rivedere ogni nuovo cliente, abilitare questa opzione può tenerti informato. Per i negozi più grandi, di solito è inutile.
-   **Titolo dell'email all'amministratore:**

    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email inviata all'amministratore quando viene registrato un nuovo account (se "Invia email con link di attivazione account all'amministratore" è abilitato).
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto dell'email di notifica all'amministratore.
    -   **Valore consigliato:** "Nuova registrazione cliente in attesa di attivazione - {shop\_name}" (o simile, usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Potresti voler includere il nome del tuo negozio nel titolo per una facile identificazione nella tua casella di posta, ad esempio, "Nuovo Cliente su Il Mio Fantastico Negozio - Attivazione in Sospeso."
-   **Accesso automatico del cliente dopo l'attivazione:**

    -   **Cosa fa questa impostazione:** Determina se un cliente viene automaticamente loggato nel proprio account immediatamente dopo aver cliccato sul link di attivazione nella propria email.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Dopo aver cliccato sul link di attivazione, il cliente viene loggato senza problemi nel suo account appena attivato e tipicamente reindirizzato alla sua dashboard account o alla homepage. Questo offre un'esperienza utente più fluida.
        -   *Quando disabilitato ("No"):* Dopo aver cliccato sul link di attivazione, l'account del cliente viene attivato, ma *non* viene automaticamente loggato. Verrà reindirizzato alla pagina di login e gli verrà chiesto di inserire manualmente le proprie credenziali.
    -   **Valore consigliato:** "Sì" per una migliore esperienza del cliente, riducendo l'attrito.
    -   **Scenario / esempio del commerciante:** Abilitare questa opzione rende il processo di attivazione più completo e user-friendly, poiché il cliente non deve fare un passaggio extra dopo aver verificato la propria email.
-   **Attiva account su pagina specifica:**

    -   **Cosa fa questa impostazione:** Ti consente di definire una pagina specifica del tuo negozio dove il cliente verrà reindirizzato *dopo* che il suo account è stato attivato con successo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo utilizzerà l'URL specificato nel campo "Link pagina di attivazione specifica" per il reindirizzamento dopo l'attivazione.
        -   *Quando disabilitato ("No"):* Il cliente verrà reindirizzato alla pagina predefinita (solitamente la homepage o la sua pagina account cliente) dopo l'attivazione.
    -   **Valore consigliato:** "No" per impostazione predefinita, a meno che tu non abbia una strategia di marketing o di onboarding specifica.
    -   **Scenario / esempio del commerciante:** Potresti voler reindirizzare i nuovi clienti a una pagina "Benvenuto" con offerte speciali, una guida al tuo negozio o una categoria di prodotti specifica per incoraggiare il loro primo acquisto.
-   **Link pagina di attivazione specifica:**

    -   **Cosa fa questa impostazione:** Questo campo appare solo se "Attiva account su pagina specifica" è abilitato. È qui che inserisci l'URL completo della pagina a cui vuoi reindirizzare i clienti dopo l'attivazione.
    -   **Effetto della modifica di questa impostazione:** Definisce l'esatto URL di destinazione per il reindirizzamento post-attivazione.
    -   **Valore consigliato:** Lascia vuoto se "Attiva account su pagina specifica" è "No". Se abilitato, fornisci un URL completo e valido (ad esempio, `https://tuonegozio.com/content/1-consegna`).
    -   **Scenario / esempio del commerciante:** Se hai una pagina "Nuovo Cliente Benvenuto" all'indirizzo `https://tuonegozio.com/benvenuto-nuovi-clienti`, dovresti inserire quell'URL qui.

#### **Impostazioni Contenuto Email**

-   **Titolo dell'email al cliente:**
    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email di attivazione inviata al cliente.
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto che i clienti vedono nella loro casella di posta per l'email di attivazione.
    -   **Valore consigliato:** "Attiva il tuo account su {shop\_name}" o "Verifica la tua email per {shop\_name}" (usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Un oggetto chiaro e conciso aiuta i clienti a identificare l'email e li incoraggia ad aprirla, riducendo la possibilità che venga contrassegnata come spam.

#### **Altre Impostazioni (Interne / Tecniche)**

-   **mypresta\_updates, update\_, updatev\_:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni. In generale, **non** dovresti modificarle.
-   **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Questi sono valori di configurazione standard di PrestaShop che il modulo potrebbe leggere o visualizzare per contesto, ma non sono direttamente configurabili all'interno del modulo stesso. Riflettono le tue impostazioni generali di PrestaShop.

### 6.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :--- | :--- | :--- | :---
title: "Account activation by email link - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Account activation by email link PrestaShop module by MyPresta.eu."
sidebar:
  label: "Account activation by email link - Merchant Manual & Configuration Guide"
---

# Attivazione account tramite link email

## 7. Requisiti e Compatibilità

-   **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 8. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 8.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Attivazione account tramite link email". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### **Impostazioni Generali**

-   **Invia email con link di attivazione account all'amministratore:**

    -   **Cosa fa questa impostazione:** Controlla se una notifica email viene inviata anche all'amministratore del negozio (tu) ogni volta che un nuovo cliente si registra e deve attivare il proprio account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Riceverai una notifica email all'indirizzo email di contatto principale del tuo negozio (solitamente `PS_SHOP_EMAIL`) ogni volta che un nuovo cliente si registra ed è in attesa di attivazione. Questo può essere utile per monitorare le nuove registrazioni.
        -   *Quando disabilitato ("No"):* Nessuna notifica email verrà inviata all'amministratore al momento della nuova registrazione del cliente.
    -   **Valore consigliato:** "No" per la maggior parte dei negozi per evitare l'ingombro della posta elettronica, a meno che tu non abbia specificamente bisogno di monitorare ogni nuova registrazione.
    -   **Scenario / esempio del commerciante:** Se gestisci un piccolo negozio di nicchia e desideri accogliere personalmente o rivedere ogni nuovo cliente, abilitare questa opzione può tenerti informato. Per i negozi più grandi, di solito è inutile.
-   **Titolo dell'email all'amministratore:**

    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email inviata all'amministratore quando viene registrato un nuovo account (se "Invia email con link di attivazione account all'amministratore" è abilitato).
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto dell'email di notifica all'amministratore.
    -   **Valore consigliato:** "Nuova registrazione cliente in attesa di attivazione - {shop\_name}" (o simile, usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Potresti voler includere il nome del tuo negozio nel titolo per una facile identificazione nella tua casella di posta, ad esempio, "Nuovo Cliente su Il Mio Fantastico Negozio - Attivazione in Sospeso."
-   **Accesso automatico del cliente dopo l'attivazione:**

    -   **Cosa fa questa impostazione:** Determina se un cliente viene automaticamente loggato nel proprio account immediatamente dopo aver cliccato sul link di attivazione nella propria email.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Dopo aver cliccato sul link di attivazione, il cliente viene loggato senza problemi nel suo account appena attivato e tipicamente reindirizzato alla sua dashboard account o alla homepage. Questo offre un'esperienza utente più fluida.
        -   *Quando disabilitato ("No"):* Dopo aver cliccato sul link di attivazione, l'account del cliente viene attivato, ma *non* viene automaticamente loggato. Verrà reindirizzato alla pagina di login e gli verrà chiesto di inserire manualmente le proprie credenziali.
    -   **Valore consigliato:** "Sì" per una migliore esperienza del cliente, riducendo l'attrito.
    -   **Scenario / esempio del commerciante:** Abilitare questa opzione rende il processo di attivazione più completo e user-friendly, poiché il cliente non deve fare un passaggio extra dopo aver verificato la propria email.
-   **Attiva account su pagina specifica:**

    -   **Cosa fa questa impostazione:** Ti consente di definire una pagina specifica del tuo negozio dove il cliente verrà reindirizzato *dopo* che il suo account è stato attivato con successo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo utilizzerà l'URL specificato nel campo "Link pagina di attivazione specifica" per il reindirizzamento dopo l'attivazione.
        -   *Quando disabilitato ("No"):* Il cliente verrà reindirizzato alla pagina predefinita (solitamente la homepage o la sua pagina account cliente) dopo l'attivazione.
    -   **Valore consigliato:** "No" per impostazione predefinita, a meno che tu non abbia una strategia di marketing o di onboarding specifica.
    -   **Scenario / esempio del commerciante:** Potresti voler reindirizzare i nuovi clienti a una pagina "Benvenuto" con offerte speciali, una guida al tuo negozio o una categoria di prodotti specifica per incoraggiare il loro primo acquisto.
-   **Link pagina di attivazione specifica:**

    -   **Cosa fa questa impostazione:** Questo campo appare solo se "Attiva account su pagina specifica" è abilitato. È qui che inserisci l'URL completo della pagina a cui vuoi reindirizzare i clienti dopo l'attivazione.
    -   **Effetto della modifica di questa impostazione:** Definisce l'esatto URL di destinazione per il reindirizzamento post-attivazione.
    -   **Valore consigliato:** Lascia vuoto se "Attiva account su pagina specifica" è "No". Se abilitato, fornisci un URL completo e valido (ad esempio, `https://tuonegozio.com/content/1-consegna`).
    -   **Scenario / esempio del commerciante:** Se hai una pagina "Nuovo Cliente Benvenuto" all'indirizzo `https://tuonegozio.com/benvenuto-nuovi-clienti`, dovresti inserire quell'URL qui.

#### **Impostazioni Contenuto Email**

-   **Titolo dell'email al cliente:**
    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email di attivazione inviata al cliente.
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto che i clienti vedono nella loro casella di posta per l'email di attivazione.
    -   **Valore consigliato:** "Attiva il tuo account su {shop\_name}" o "Verifica la tua email per {shop\_name}" (usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Un oggetto chiaro e conciso aiuta i clienti a identificare l'email e li incoraggia ad aprirla, riducendo la possibilità che venga contrassegnata come spam.

#### **Altre Impostazioni (Interne / Tecniche)**

-   **mypresta\_updates, update\_, updatev\_:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni. In generale, **non** dovresti modificarle.
-   **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Questi sono valori di configurazione standard di PrestaShop che il modulo potrebbe leggere o visualizzare per contesto, ma non sono direttamente configurabili all'interno del modulo stesso. Riflettono le tue impostazioni generali di PrestaShop.

### 8.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :--- | :--- | :--- | :---
title: "Account activation by email link - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Account activation by email link PrestaShop module by MyPresta.eu."
sidebar:
  label: "Account activation by email link - Merchant Manual & Configuration Guide"
---

# Attivazione account tramite link email

## 9. Requisiti e Compatibilità

-   **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 10. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 10.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Attivazione account tramite link email". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### **Impostazioni Generali**

-   **Invia email con link di attivazione account all'amministratore:**

    -   **Cosa fa questa impostazione:** Controlla se una notifica email viene inviata anche all'amministratore del negozio (tu) ogni volta che un nuovo cliente si registra e deve attivare il proprio account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Riceverai una notifica email all'indirizzo email di contatto principale del tuo negozio (solitamente `PS_SHOP_EMAIL`) ogni volta che un nuovo cliente si registra ed è in attesa di attivazione. Questo può essere utile per monitorare le nuove registrazioni.
        -   *Quando disabilitato ("No"):* Nessuna notifica email verrà inviata all'amministratore al momento della nuova registrazione del cliente.
    -   **Valore consigliato:** "No" per la maggior parte dei negozi per evitare l'ingombro della posta elettronica, a meno che tu non abbia specificamente bisogno di monitorare ogni nuova registrazione.
    -   **Scenario / esempio del commerciante:** Se gestisci un piccolo negozio di nicchia e desideri accogliere personalmente o rivedere ogni nuovo cliente, abilitare questa opzione può tenerti informato. Per i negozi più grandi, è solitamente inutile.
-   **Titolo dell'email all'amministratore:**

    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email inviata all'amministratore quando viene registrato un nuovo account (se "Invia email con link di attivazione account all'amministratore" è abilitato).
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto dell'email di notifica all'amministratore.
    -   **Valore consigliato:** "Nuova registrazione cliente in attesa di attivazione - {shop\_name}" (o simile, usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Potresti voler includere il nome del tuo negozio nel titolo per una facile identificazione nella tua casella di posta, ad esempio, "Nuovo Cliente su Il Mio Fantastico Negozio - Attivazione in Sospeso."
-   **Accesso automatico del cliente dopo l'attivazione:**

    -   **Cosa fa questa impostazione:** Determina se un cliente viene automaticamente loggato nel proprio account immediatamente dopo aver cliccato sul link di attivazione nella propria email.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Dopo aver cliccato sul link di attivazione, il cliente viene loggato senza problemi nel suo account appena attivato e tipicamente reindirizzato alla sua dashboard account o alla homepage. Questo offre un'esperienza utente più fluida.
        -   *Quando disabilitato ("No"):* Dopo aver cliccato sul link di attivazione, l'account del cliente viene attivato, ma *non* viene automaticamente loggato. Verrà reindirizzato alla pagina di login e gli verrà chiesto di inserire manualmente le proprie credenziali.
    -   **Valore consigliato:** "Sì" per una migliore esperienza del cliente, riducendo l'attrito.
    -   **Scenario / esempio del commerciante:** Abilitare questa opzione rende il processo di attivazione più completo e user-friendly, poiché il cliente non deve fare un passaggio extra dopo aver verificato la propria email.
-   **Attiva account su pagina specifica:**

    -   **Cosa fa questa impostazione:** Ti consente di definire una pagina specifica del tuo negozio dove il cliente verrà reindirizzato *dopo* che il suo account è stato attivato con successo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo utilizzerà l'URL specificato nel campo "Link pagina di attivazione specifica" per il reindirizzamento dopo l'attivazione.
        -   *Quando disabilitato ("No"):* Il cliente verrà reindirizzato alla pagina predefinita (solitamente la homepage o la sua pagina account cliente) dopo l'attivazione.
    -   **Valore consigliato:** "No" per impostazione predefinita, a meno che tu non abbia una strategia di marketing o di onboarding specifica.
    -   **Scenario / esempio del commerciante:** Potresti voler reindirizzare i nuovi clienti a una pagina "Benvenuto" con offerte speciali, una guida al tuo negozio o una categoria di prodotti specifica per incoraggiare il loro primo acquisto.
-   **Link pagina di attivazione specifica:**

    -   **Cosa fa questa impostazione:** Questo campo appare solo se "Attiva account su pagina specifica" è abilitato. È qui che inserisci l'URL completo della pagina a cui vuoi reindirizzare i clienti dopo l'attivazione.
    -   **Effetto della modifica di questa impostazione:** Definisce l'esatto URL di destinazione per il reindirizzamento post-attivazione.
    -   **Valore consigliato:** Lascia vuoto se "Attiva account su pagina specifica" è "No". Se abilitato, fornisci un URL completo e valido (ad esempio, `https://tuonegozio.com/content/1-consegna`).
    -   **Scenario / esempio del commerciante:** Se hai una pagina "Nuovo Cliente Benvenuto" all'indirizzo `https://tuonegozio.com/benvenuto-nuovi-clienti`, dovresti inserire quell'URL qui.

#### **Impostazioni Contenuto Email**

-   **Titolo dell'email al cliente:**
    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email di attivazione inviata al cliente.
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto che i clienti vedono nella loro casella di posta per l'email di attivazione.
    -   **Valore consigliato:** "Attiva il tuo account su {shop\_name}" o "Verifica la tua email per {shop\_name}" (usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Un oggetto chiaro e conciso aiuta i clienti a identificare l'email e li incoraggia ad aprirla, riducendo la possibilità che venga contrassegnata come spam.

#### **Altre Impostazioni (Interne / Tecniche)**

-   **mypresta\_updates, update\_, updatev\_:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni. In generale, **non** dovresti modificarle.
-   **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Questi sono valori di configurazione standard di PrestaShop che il modulo potrebbe leggere o visualizzare per contesto, ma non sono direttamente configurabili all'interno del modulo stesso. Riflettono le tue impostazioni generali di PrestaShop.

### 10.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :--- | :--- | :--- | :---
title title: "Account activation activation by email link - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Account activation by email link PrestaShop module by MyPresta.eu."
sidebar:
  label: "Account activation by email link - Merchant Manual & Configuration Guide"
---

# Attivazione account tramite link email

## 11. Requisiti e Compatibilità

-   **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 12. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 12.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Attivazione account tramite link email". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### **Impostazioni Generali**

-   **Invia email con link di attivazione account all'amministratore:**

    -   **Cosa fa questa impostazione:** Controlla se una notifica email viene inviata anche all'amministratore del negozio (tu) ogni volta che un nuovo cliente si registra e deve attivare il proprio account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Riceverai una notifica email all'indirizzo email di contatto principale del tuo negozio (solitamente `PS_SHOP_EMAIL`) ogni volta che un nuovo cliente si registra ed è in attesa di attivazione. Questo può essere utile per monitorare le nuove registrazioni.
        -   *Quando disabilitato ("No"):* Nessuna notifica email verrà inviata all'amministratore al momento della nuova registrazione del cliente.
    -   **Valore consigliato:** "No" per la maggior parte dei negozi per evitare l'ingombro della posta elettronica, a meno che tu non abbia specificamente bisogno di monitorare ogni nuova registrazione.
    -   **Scenario / esempio del commerciante:** Se gestisci un piccolo negozio di nicchia e desideri accogliere personalmente o rivedere ogni nuovo cliente, abilitare questa opzione può tenerti informato. Per i negozi più grandi, è solitamente inutile.
-   **Titolo dell'email all'amministratore:**

    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email inviata all'amministratore quando viene registrato un nuovo account (se "Invia email con link di attivazione account all'amministratore" è abilitato).
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto dell'email di notifica all'amministratore.
    -   **Valore consigliato:** "Nuova registrazione cliente in attesa di attivazione - {shop\_name}" (o simile, usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Potresti voler includere il nome del tuo negozio nel titolo per una facile identificazione nella tua casella di posta, ad esempio, "Nuovo Cliente su Il Mio Fantastico Negozio - Attivazione in Sospeso."
-   **Accesso automatico del cliente dopo l'attivazione:**

    -   **Cosa fa questa impostazione:** Determina se un cliente viene automaticamente loggato nel proprio account immediatamente dopo aver cliccato sul link di attivazione nella propria email.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Dopo aver cliccato sul link di attivazione, il cliente viene loggato senza problemi nel suo account appena attivato e tipicamente reindirizzato alla sua dashboard account o alla homepage. Questo offre un'esperienza utente più fluida.
        -   *Quando disabilitato ("No"):* Dopo aver cliccato sul link di attivazione, l'account del cliente viene attivato, ma *non* viene automaticamente loggato. Verrà reindirizzato alla pagina di login e gli verrà chiesto di inserire manualmente le proprie credenziali.
    -   **Valore consigliato:** "Sì" per una migliore esperienza del cliente, riducendo l'attrito.
    -   **Scenario / esempio del commerciante:** Abilitare questa opzione rende il processo di attivazione più completo e user-friendly, poiché il cliente non deve fare un passaggio extra dopo aver verificato la propria email.
-   **Attiva account su pagina specifica:**

    -   **Cosa fa questa impostazione:** Ti consente di definire una pagina specifica del tuo negozio dove il cliente verrà reindirizzato *dopo* che il suo account è stato attivato con successo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo utilizzerà l'URL specificato nel campo "Link pagina di attivazione specifica" per il reindirizzamento dopo l'attivazione.
        -   *Quando disabilitato ("No"):* Il cliente verrà reindirizzato alla pagina predefinita (solitamente la homepage o la sua pagina account cliente) dopo l'attivazione.
    -   **Valore consigliato:** "No" per impostazione predefinita, a meno che tu non abbia una strategia di marketing o di onboarding specifica.
    -   **Scenario / esempio del commerciante:** Potresti voler reindirizzare i nuovi clienti a una pagina "Benvenuto" con offerte speciali, una guida al tuo negozio o una categoria di prodotti specifica per incoraggiare il loro primo acquisto.
-   **Link pagina di attivazione specifica:**

    -   **Cosa fa questa impostazione:** Questo campo appare solo se "Attiva account su pagina specifica" è abilitato. È qui che inserisci l'URL completo della pagina a cui vuoi reindirizzare i clienti dopo l'attivazione.
    -   **Effetto della modifica di questa impostazione:** Definisce l'esatto URL di destinazione per il reindirizzamento post-attivazione.
    -   **Valore consigliato:** Lascia vuoto se "Attiva account su pagina specifica" è "No". Se abilitato, fornisci un URL completo e valido (ad esempio, `https://tuonegozio.com/content/1-consegna`).
    -   **Scenario / esempio del commerciante:** Se hai una pagina "Nuovo Cliente Benvenuto" all'indirizzo `https://tuonegozio.com/benvenuto-nuovi-clienti`, dovresti inserire quell'URL qui.

#### **Impostazioni Contenuto Email**

-   **Titolo dell'email al cliente:**
    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email di attivazione inviata al cliente.
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto che i clienti vedono nella loro casella di posta per l'email di attivazione.
    -   **Valore consigliato:** "Attiva il tuo account su {shop\_name}" o "Verifica la tua email per {shop\_name}" (usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Un oggetto chiaro e conciso aiuta i clienti a identificare l'email e li incoraggia ad aprirla, riducendo la possibilità che venga contrassegnata come spam.

#### **Altre Impostazioni (Interne / Tecniche)**

-   **mypresta\_updates, update\_, updatev\_:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni. In generale, **non** dovresti modificarle.
-   **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Questi sono valori di configurazione standard di PrestaShop che il modulo potrebbe leggere o visualizzare per contesto, ma non sono direttamente configurabili all'interno del modulo stesso. Riflettono le tue impostazioni generali di PrestaShop.

### 12.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :--- | :--- | :--- | :---
---
title: "Account activation by email link - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Account activation by email link PrestaShop module by MyPresta.eu."
sidebar:
  label: "Account activation by email link - Merchant Manual & Configuration Guide"
---

# Attivazione account tramite link email

## 13. Requisiti e Compatibilità

-   **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 14. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 14.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Attivazione account tramite link email". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### **Impostazioni Generali**

-   **Invia email con link di attivazione account all'amministratore:**

    -   **Cosa fa questa impostazione:** Controlla se una notifica email viene inviata anche all'amministratore del negozio (tu) ogni volta che un nuovo cliente si registra e deve attivare il proprio account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Riceverai una notifica email all'indirizzo email di contatto principale del tuo negozio (solitamente `PS_SHOP_EMAIL`) ogni volta che un nuovo cliente si registra ed è in attesa di attivazione. Questo può essere utile per monitorare le nuove registrazioni.
        -   *Quando disabilitato ("No"):* Nessuna notifica email verrà inviata all'amministratore al momento della nuova registrazione del cliente.
    -   **Valore consigliato:** "No" per la maggior parte dei negozi per evitare l'ingombro della posta elettronica, a meno che tu non abbia specificamente bisogno di monitorare ogni nuova registrazione.
    -   **Scenario / esempio del commerciante:** Se gestisci un piccolo negozio di nicchia e desideri accogliere personalmente o rivedere ogni nuovo cliente, abilitare questa opzione può tenerti informato. Per i negozi più grandi, è solitamente inutile.
-   **Titolo dell'email all'amministratore:**

    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email inviata all'amministratore quando viene registrato un nuovo account (se "Invia email con link di attivazione account all'amministratore" è abilitato).
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto dell'email di notifica all'amministratore.
    -   **Valore consigliato:** "Nuova registrazione cliente in attesa di attivazione - {shop\_name}" (o simile, usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Potresti voler includere il nome del tuo negozio nel titolo per una facile identificazione nella tua casella di posta, ad esempio, "Nuovo Cliente su Il Mio Fantastico Negozio - Attivazione in Sospeso."
-   **Accesso automatico del cliente dopo l'attivazione:**

    -   **Cosa fa questa impostazione:** Determina se un cliente viene automaticamente loggato nel proprio account immediatamente dopo aver cliccato sul link di attivazione nella propria email.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Dopo aver cliccato sul link di attivazione, il cliente viene loggato senza problemi nel suo account appena attivato e tipicamente reindirizzato alla sua dashboard account o alla homepage. Questo offre un'esperienza utente più fluida.
        -   *Quando disabilitato ("No"):* Dopo aver cliccato sul link di attivazione, l'account del cliente viene attivato, ma *non* viene automaticamente loggato. Verrà reindirizzato alla pagina di login e gli verrà chiesto di inserire manualmente le proprie credenziali.
    -   **Valore consigliato:** "Sì" per una migliore esperienza del cliente, riducendo l'attrito.
    -   **Scenario / esempio del commerciante:** Abilitare questa opzione rende il processo di attivazione più completo e user-friendly, poiché il cliente non deve fare un passaggio extra dopo aver verificato la propria email.
-   **Attiva account su pagina specifica:**

    -   **Cosa fa questa impostazione:** Ti consente di definire una pagina specifica del tuo negozio dove il cliente verrà reindirizzato *dopo* che il suo account è stato attivato con successo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo utilizzerà l'URL specificato nel campo "Link pagina di attivazione specifica" per il reindirizzamento dopo l'attivazione.
        -   *Quando disabilitato ("No"):* Il cliente verrà reindirizzato alla pagina predefinita (solitamente la homepage o la sua pagina account cliente) dopo l'attivazione.
    -   **Valore consigliato:** "No" per impostazione predefinita, a meno che tu non abbia una strategia di marketing o di onboarding specifica.
    -   **Scenario / esempio del commerciante:** Potresti voler reindirizzare i nuovi clienti a una pagina "Benvenuto" con offerte speciali, una guida al tuo negozio o una categoria di prodotti specifica per incoraggiare il loro primo acquisto.
-   **Link pagina di attivazione specifica:**

    -   **Cosa fa questa impostazione:** Questo campo appare solo se "Attiva account su pagina specifica" è abilitato. È qui che inserisci l'URL completo della pagina a cui vuoi reindirizzare i clienti dopo l'attivazione.
    -   **Effetto della modifica di questa impostazione:** Definisce l'esatto URL di destinazione per il reindirizzamento post-attivazione.
    -   **Valore consigliato:** Lascia vuoto se "Attiva account su pagina specifica" è "No". Se abilitato, fornisci un URL completo e valido (ad esempio, `https://tuonegozio.com/content/1-consegna`).
    -   **Scenario / esempio del commerciante:** Se hai una pagina "Nuovo Cliente Benvenuto" all'indirizzo `https://tuonegozio.com/benvenuto-nuovi-clienti`, dovresti inserire quell'URL qui.

#### **Impostazioni Contenuto Email**

-   **Titolo dell'email al cliente:**
    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email di attivazione inviata al cliente.
    -   **Effetto della modifica di questa impostazione:** Modifica l'oggetto che i clienti vedono nella loro casella di posta per l'email di attivazione.
    -   **Valore consigliato:** "Attiva il tuo account su {shop\_name}" o "Verifica la tua email per {shop\_name}" (usando `{shop_name}` per il nome del tuo negozio).
    -   **Scenario / esempio del commerciante:** Un oggetto chiaro e conciso aiuta i clienti a identificare l'email e li incoraggia ad aprirla, riducendo la possibilità che venga contrassegnata come spam.

#### **Altre Impostazioni (Interne / Tecniche)**

-   **mypresta\_updates, update\_, updatev\_:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni. In generale, **non** dovresti modificarle.
-   **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Questi sono valori di configurazione standard di PrestaShop che il modulo potrebbe leggere o visualizzare per contesto, ma non sono direttamente configurabili all'interno del modulo stesso. Riflettono le tue impostazioni generali di PrestaShop.

### 14.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :--- | :--- | :--- | :---

## 15. Merchant Troubleshooting & Frequently Asked Questions (FAQ)

**Q1: My customers are not receiving the activation email. What should I do?**

-   **A:**
    1.  **Check Spam/Junk Folders:** Advise customers to check their spam or junk mail folders.
    2.  **Verify Store Email Settings:** Go to **Shop Parameters > Contact > Stores** (or **Advanced Parameters > E-mail** in older versions) in your PrestaShop Back Office. Ensure your store’s email configuration is correct and that emails are being sent successfully (test by sending a test email).
    3.  **Server Mail Functionality:** Contact your hosting provider to ensure your server’s mail function (PHP `mail()` or SMTP) is working correctly and not being blocked.
    4.  **Module Configuration:** Double-check the “Title of email to customer” in the module settings. A very generic or suspicious-looking title might trigger spam filters.
    5.  **Clear Cache:** Go to **Advanced Parameters > Performance** and click “Clear cache” (or “Clear Smarty cache” in older versions). Sometimes caching issues can prevent emails from being sent.

**Q2: A customer activated their account but still can’t log in.**

-   **A:**
    1.  **Check Customer Status:** In your PrestaShop Back Office, go to **Customers > Customers**. Find the customer’s account and verify that their “Enabled” status is set to “Yes.” If not, manually enable it.
    2.  **Password Reset:** Suggest the customer try the “Forgot password” link on your login page. This can resolve issues if they are misremembering their password.
    3.  **Browser Cache/Cookies:** Ask the customer to clear their browser’s cache and cookies, or try logging in from a different browser or incognito window.
    4.  **Module Conflict:** Temporarily disable other modules that interact with customer accounts or login processes to rule out conflicts.

**Q3: How can I manually activate a customer’s account if they can’t receive the email?**

-   **A:** You can manually activate a customer’s account from the PrestaShop Back Office:
    1.  Go to **Customers > Customers**.
    2.  Find the customer’s name in the list and click “Edit” (the pencil icon).
    3.  On the customer’s details page, locate the “Enabled” switch and set it to “Yes.”
    4.  Click “Save.” The customer will now be able to log in.

**Q4: The activation link redirects to the wrong page or shows an error.**

-   **A:**
    1.  **“Specific activation page link” Check:** If you have “Activate account on specific page” enabled, verify that the URL entered in “Specific activation page link” is absolutely correct and accessible. A typo or an invalid URL will cause redirection issues.
    2.  **Friendly URLs:** Ensure your Friendly URLs are enabled and working correctly (**Shop Parameters > Traffic & SEO**).
    3.  **Clear Cache:** Clear your PrestaShop cache (**Advanced Parameters > Performance**).
    4.  **Check .htaccess:** If you’ve made any manual changes to your `.htaccess` file, revert them or ensure they are not interfering with URL rewriting.

## 16. Developer & Webmaster Guide (Technical Architecture & Code Map)

This section is strictly for developers, store webmasters, and technical agencies maintaining or extending the store.

### 16.1 Architecture Overview

The “Account activation by email link” module (`acactiv`) is a standard PrestaShop module primarily designed to intercept the customer registration process. It leverages PrestaShop’s hook system to modify default behavior, specifically `actionCustomerAccountAdd` to mark new accounts as inactive and send activation emails, and `displayHeader` to inject necessary JavaScript. The module does not introduce new database tables or complex `ObjectModel` structures, instead relying on modifying existing `Customer` object properties and using `ps_configuration` for its settings.

### 16.2 Controllers (`controllers/`)

This module does not use dedicated front-office or back-office controllers. All logic is handled within the main module file (`acactiv.php`) and its registered hooks. The activation link itself points to the module’s main dispatch, which then handles the activation logic.

### 16.3 Core Classes & Models (`classes/`)

This module does not introduce any custom classes or models in the `classes/` directory. It directly interacts with PrestaShop’s core `Customer` class and `Configuration` class.

### 16.4 JavaScript Assets (`views/js/`)

-   **`acactiv/views/acactiv-compat.js`**

    -   **Scope:** Front-office.
    -   **Purpose:** This script likely contains compatibility fixes or polyfills for older PrestaShop versions or browsers, ensuring the module’s front-end functionality works across a wider range of environments. It might address differences in jQuery versions or DOM manipulation methods.
    -   **Event Listeners/DOM Manipulation:** Specifics would require code review, but typically involves ensuring elements are present or adjusting behaviors based on PrestaShop version.
-   **`acactiv/views/acactiv.js`**

    -   **Scope:** Front-office.
    -   **Purpose:** This is the main JavaScript file for front-office interactions. It’s responsible for displaying messages to the user after registration (e.g., “Check your email for activation link”) and potentially handling client-side aspects of the activation process.
    -   **Event Listeners/DOM Manipulation:**
        -   May listen for form submissions on the registration page to display custom messages.
        -   Could manipulate the DOM to show/hide elements, display pop-up notifications, or redirect the user after certain actions.
        -   Might use `prestashop.on('updatedProduct', function(event) { ... });` or similar PrestaShop event listeners if it needs to react to dynamic content updates, though less likely for this module’s core function.

### 16.5 CSS Stylesheets (`views/css/`)

-   **`acactiv/views/acactiv.css`**
    -   **Scope:** Front-office customer styling.
    -   **Purpose:** Provides basic styling for any custom messages or elements introduced by the module on the front office. This could include styling for the “account pending activation” message or the “account activated” confirmation.
    -   **Key CSS Class Selectors:** Developers should inspect the module’s output HTML to identify specific classes (e.g., `.acactiv-message`, `.acactiv-success`, `.acactiv-error`) that can be overridden in their theme’s `custom.css` or `theme.css` to match the store’s branding.

### 16.6 Smarty Template Structure (`views/templates/`)

-   **Hook templates (`views/templates/hook/`)**:

    -   **`acactiv/views/checkout_notice.tpl`**
        -   **Hook:** Not explicitly stated as a hook template, but its name suggests it might be rendered in a context related to checkout or account creation, possibly via `displayCustomerAccountForm` or similar, to show a notice about activation.
        -   **Output:** Likely outputs an informational message to the customer after registration, instructing them to check their email for the activation link.
    -   **`acactiv/views/displayHeader.tpl`**
        -   **Hook:** `displayHeader`
        -   **Output:** This template is typically used to include CSS and JavaScript files in the `<head>` section of the front-office pages. It will contain `<link>` tags for `acactiv.css` and `<script>` tags for `acactiv-compat.js` and `acactiv.js`, ensuring these assets are loaded on relevant pages.
-   **Admin templates (`views/templates/admin/`)**: None identified. Configuration is handled directly in `getContent()` within `acactiv.php`.
-   **Front-office templates (`views/templates/front/`)**: None identified as dedicated standalone pages.

### 16.7 Database Schema & Hooks Map

-   **Database Tables**:

    -   This module does not create custom SQL tables.
    -   It modifies the `active` column of the `ps_customer` table (setting it to `0` for new registrations until activated).
    -   Configuration settings are stored in the `ps_configuration` table with keys like `ACACTIV_SENDTOME`, `ACACTIV_SPECURLFEATURE`, `ACACTIV_SPECURL`, `ACACTIV_AUTOLOGIN`, `ACACTIV_ATITLE`, `ACACTIV_CTITLE`.
-   **Registered Hooks Table**:
"""
