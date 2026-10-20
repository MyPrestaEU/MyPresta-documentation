---
title: "Anzahl der erlaubten Bestellungen begrenzen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Anzahl der erlaubten Bestellungen begrenzen' von MyPresta.eu."
sidebar:
  label: "Anzahl der erlaubten Bestellungen begrenzen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Limit number of allowed orders auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/limit-number-of-allowed-orders.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/limit-number-of-allowed-orders/)
>
> ---


# Anzahl der erlaubten Bestellungen begrenzen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die globalen Limits für Ihre Kunden definieren.

-   **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die maximale Anzahl von Bestellungen, die *jeder* Kunde in Ihrem Shop aufgeben kann, bevor er daran gehindert wird, weitere Bestellungen aufzugeben.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z. B. 3):* Jeder Kunde, der erfolgreich 3 Bestellungen aufgegeben hat, kann keine 4. Bestellung mehr aufgeben. Er sieht eine Meldung, die ihn daran hindert, den Checkout abzuschließen.
    -   *Wenn auf 0 gesetzt oder leer gelassen:* Das Modul wird für globale Limits effektiv deaktiviert, was bedeutet, dass Kunden eine unbegrenzte Anzahl von Bestellungen aufgeben können (es sei denn, es sind spezifische Kundenlimits festgelegt, siehe Abschnitt 4.2).
-   **Empfohlener Wert:** Beginnen Sie mit einem Wert, der Ihrem Geschäftsziel entspricht (z. B. 1 für eine strenge „eins pro Kunde“-Aktion, 5 für ein allgemeines Limit). Wenn Sie nur bestimmte Kunden einschränken möchten, können Sie dieses Feld leer lassen und den speziellen Kundenverwaltungsbildschirm verwenden.
-   **Händlerszenario / Beispiel:** Sie führen einen Flash-Sale für ein sehr begehrtes Produkt durch und möchten sicherstellen, dass jeder Kunde nur eine Chance zum Kauf erhält. Sie würden diesen Wert auf `1` setzen.

### 2.2 Dedizierter Admin-Bildschirm: Kundenbestelllimits (Back Office > Module > Anzahl der erlaubten Bestellungen begrenzen > Kundenbestelllimits)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Bestelllimits für bestimmte Kunden zu verwalten, die das in Abschnitt 4.1 festgelegte globale Limit überschreiben.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Anzahl der erlaubten Bestellungen begrenzen“ suchen, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Kundenbestelllimits“ oder Ähnlichem suchen. Alternativ kann es direkt in Ihrem Haupt-PrestaShop-Menü unter einem neuen, vom Modul erstellten Eintrag erscheinen (z. B. **Kunden > Kundenbestelllimits**).
-   **Verfügbare Aktionen & Einstellungen:**

    -   **Kundensuche/-auswahl:** Sie finden in der Regel eine Suchleiste oder ein Dropdown-Menü, um einen bestehenden Kunden aus Ihrem Shop auszuwählen.
    -   **Individuelles Limit festlegen:** Sobald ein Kunde ausgewählt ist, können Sie eine bestimmte Anzahl erlaubter Bestellungen für *diesen bestimmten Kunden* eingeben.
    -   **Bestehende Limits anzeigen/bearbeiten:** Eine Tabelle oder Liste zeigt alle Kunden an, für die Sie benutzerdefinierte Limits festgelegt haben, zusammen mit ihrem aktuellen Limit und möglicherweise ihrer aktuellen Bestellanzahl. Sie können diese Einträge bearbeiten oder löschen.
    -   **Währungsanzeige:** Das Modul kann Währungsinformationen (z. B. `PS_CURRENCY_DEFAULT`) im Kontext von Kundenbestellungen anzeigen, obwohl die Limits selbst numerische Bestellzählungen und keine monetären Werte sind.
-   **Auswirkung von Änderungen:**

    -   *Hinzufügen eines neuen Kundenlimits:* Der ausgewählte Kunde wird nun durch die von Ihnen für ihn festgelegte spezifische Anzahl von Bestellungen eingeschränkt, wodurch das globale Limit (falls eines festgelegt ist) überschrieben wird.
    -   *Bearbeiten eines bestehenden Kundenlimits:* Die erlaubte Bestellanzahl des Kunden wird sofort aktualisiert.
    -   *Löschen eines Kundenlimits:* Der Kunde unterliegt wieder dem globalen Bestelllimit (falls festgelegt) oder hat kein Limit, wenn kein globales Limit aktiv ist.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Spezifische Bedürfnisse identifizieren:** Bestimmen Sie, ob bestimmte VIP-Kunden, problematische Kunden oder Kunden, die an speziellen Programmen teilnehmen, einzigartige Bestelllimits benötigen.
    2.  **Suchen und hinzufügen:** Verwenden Sie die Suchfunktion, um den Kunden zu finden.
    3.  **Limit anwenden:** Geben Sie die gewünschte maximale Anzahl von Bestellungen für diesen Kunden ein.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Liste der Kunden mit benutzerdefinierten Limits, um sicherzustellen, dass die Einstellungen weiterhin angemessen sind.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :--- | :--- | :--- | :---
title: "Limit number of allowed orders - Merchant Manual & Configuration Guide"
description: "Complete user manual, screen-by-screen setup guide, and developer reference for the Limit number of allowed orders PrestaShop module by MyPresta.eu."
sidebar:
  label: "Anzahl der erlaubten Bestellungen begrenzen – Händlerhandbuch & Konfigurationsanleitung"
---

# Anzahl der erlaubten Bestellungen begrenzen

## 3. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend.

## 4. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die globalen Limits für Ihre Kunden definieren.

-   **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die maximale Anzahl von Bestellungen, die *jeder* Kunde in Ihrem Shop aufgeben kann, bevor er daran gehindert wird, weitere Bestellungen aufzugeben.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z. B. 3):* Jeder Kunde, der erfolgreich 3 Bestellungen aufgegeben hat, kann keine 4. Bestellung mehr aufgeben. Er sieht eine Meldung, die ihn daran hindert, den Checkout abzuschließen.
    -   *Wenn auf 0 gesetzt oder leer gelassen:* Das Modul wird für globale Limits effektiv deaktiviert, was bedeutet, dass Kunden eine unbegrenzte Anzahl von Bestellungen aufgeben können (es sei denn, es sind spezifische Kundenlimits festgelegt, siehe Abschnitt 4.2).
-   **Empfohlener Wert:** Beginnen Sie mit einem Wert, der Ihrem Geschäftsziel entspricht (z. B. 1 für eine strenge „eins pro Kunde“-Aktion, 5 für ein allgemeines Limit). Wenn Sie nur bestimmte Kunden einschränken möchten, können Sie dieses Feld leer lassen und den speziellen Kundenverwaltungsbildschirm verwenden.
-   **Händlerszenario / Beispiel:** Sie führen einen Flash-Sale für ein sehr begehrtes Produkt durch und möchten sicherstellen, dass jeder Kunde nur eine Chance zum Kauf erhält. Sie würden diesen Wert auf `1` setzen.

### 4.2 Dedizierter Admin-Bildschirm: Kundenbestelllimits (Back Office > Module > Anzahl der erlaubten Bestellungen begrenzen > Kundenbestelllimits)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Bestelllimits für bestimmte Kunden zu verwalten, die das in Abschnitt 4.1 festgelegte globale Limit überschreiben.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Anzahl der erlaubten Bestellungen begrenzen“ suchen, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Kundenbestelllimits“ oder Ähnlichem suchen. Alternativ kann es direkt in Ihrem Haupt-PrestaShop-Menü unter einem neuen, vom Modul erstellten Eintrag erscheinen (z. B. **Kunden > Kundenbestelllimits**).
-   **Verfügbare Aktionen & Einstellungen:**

    -   **Kundensuche/-auswahl:** Sie finden in der Regel eine Suchleiste oder ein Dropdown-Menü, um einen bestehenden Kunden aus Ihrem Shop auszuwählen.
    -   **Individuelles Limit festlegen:** Sobald ein Kunde ausgewählt ist, können Sie eine spezifische Anzahl erlaubter Bestellungen für *diesen bestimmten Kunden* eingeben.
    -   **Bestehende Limits anzeigen/bearbeiten:** Eine Tabelle oder Liste zeigt alle Kunden an, für die Sie benutzerdefinierte Limits festgelegt haben, zusammen mit ihrem aktuellen Limit und möglicherweise ihrer aktuellen Bestellanzahl. Sie können diese Einträge bearbeiten oder löschen.
    -   **Währungsanzeige:** Das Modul kann Währungsinformationen (z. B. `PS_CURRENCY_DEFAULT`) im Kontext von Kundenbestellungen anzeigen, obwohl die Limits selbst numerische Bestellzählungen und keine monetären Werte sind.
-   **Auswirkung von Änderungen:**

    -   *Hinzufügen eines neuen Kundenlimits:* Der ausgewählte Kunde wird nun durch die von Ihnen für ihn festgelegte spezifische Anzahl von Bestellungen eingeschränkt, wodurch das globale Limit (falls festgelegt) überschrieben wird.
    -   *Bearbeiten eines bestehenden Kundenlimits:* Die erlaubte Bestellanzahl des Kunden wird sofort aktualisiert.
    -   *Löschen eines Kundenlimits:* Der Kunde unterliegt wieder dem globalen Bestelllimit (falls festgelegt) oder hat kein Limit, wenn kein globales Limit aktiv ist.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Spezifische Bedürfnisse identifizieren:** Bestimmen Sie, ob bestimmte VIP-Kunden, problematische Kunden oder Kunden, die an speziellen Programmen teilnehmen, einzigartige Bestelllimits benötigen.
    2.  **Suchen und hinzufügen:** Verwenden Sie die Suchfunktion, um den Kunden zu finden.
    3.  **Limit anwenden:** Geben Sie die gewünschte maximale Anzahl von Bestellungen für diesen Kunden ein.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Liste der Kunden mit benutzerdefinierten Limits, um sicherzustellen, dass die Einstellungen weiterhin angemessen sind.

### 4.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :--- | :--- | :--- | :---
```yaml
title: "Bestellanzahl begrenzen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Anzahl der erlaubten Bestellungen begrenzen' von MyPresta.eu."
sidebar:
  label: "Bestellanzahl begrenzen – Händlerhandbuch & Konfigurationsanleitung"
---

# Anzahl der erlaubten Bestellungen begrenzen

## 1. Was dieses Modul tut und warum Sie es brauchen

Das Modul „Anzahl der erlaubten Bestellungen begrenzen“ gibt Ihnen präzise Kontrolle darüber, wie viele Bestellungen jeder Kunde in Ihrem PrestaShop-Shop aufgeben kann. Stellen Sie sich vor, Sie führen eine Sonderaktion durch, verkaufen Artikel in limitierter Auflage oder betreiben ein Großhandelsgeschäft, in dem Sie verhindern möchten, dass ein einzelner Kunde den Lagerbestand monopolisiert oder Kreditlimits überschreitet. Dieses Modul ist Ihre Lösung.

**Hauptvorteile:**

-   **Bestandskontrolle:** Verhindern Sie, dass einzelne Kunden limitierte Bestände aufkaufen, und sorgen Sie für eine faire Verteilung.
-   **Fairness & Gleichheit:** Geben Sie mehr Kunden die Möglichkeit, beliebte oder limitierte Artikel zu kaufen.
-   **Betrugsprävention:** Mindern Sie potenzielle betrügerische Aktivitäten, indem Sie die Anzahl der Transaktionen pro Benutzer begrenzen.
-   **Großhandelsmanagement:** Setzen Sie spezifische Einkaufsrichtlinien für B2B-Kunden durch, um zu verhindern, dass diese voreingestellte Bestellquoten überschreiten.
-   **Aktionsmanagement:** Stellen Sie sicher, dass Werbeangebote oder Rabatte fair genutzt und nicht von wenigen Kunden missbraucht werden.
-   **Betriebliche Effizienz:** Reduzieren Sie den Aufwand für die Verwaltung übermäßiger Bestellungen von einem einzelnen Kunden, insbesondere bei Nischenprodukten.

Dieses Modul ist ideal für Einzelhändler, die limitierte Bestände verkaufen, Unternehmen, die exklusive Aktionen durchführen, oder B2B-Großhändler, die Kundenkauflimits verwalten müssen.

## 2. Wo Kunden es in Ihrem Shop sehen (Front-Office-Rundgang)

Dieses Modul arbeitet hauptsächlich im Hintergrund und setzt Ihre Bestelllimits durch. Kunden sehen kein spezifisches „Block“ oder „Widget“ dieses Moduls auf jeder Seite. Stattdessen macht sich seine Wirkung am Kaufpunkt bemerkbar:

-   **Während des Checkouts:** Wenn ein Kunde versucht, eine Bestellung aufzugeben, die sein erlaubtes Limit überschreiten würde, verhindert das Modul, dass er den Kauf abschließt. Er sieht dann in der Regel eine Meldung, die darauf hinweist, dass er keine weiteren Bestellungen aufgeben kann.
-   **Warenkorb:** Je nach Konfiguration kann eine Meldung im Warenkorb erscheinen, wenn der Kunde sein Limit bereits erreicht hat, und ihn informieren, bevor er überhaupt zum Checkout geht.
-   **Produktseite (indirekt):** Obwohl nicht direkt sichtbar, bedeuten die Einschränkungen des Moduls, dass ein Kunde, sobald er sein Limit erreicht hat, effektiv keine weiteren Produkte kaufen kann, unabhängig davon, welche Produktseite er besucht.

Das Modul sorgt für ein reibungsloses Erlebnis für Kunden innerhalb ihrer Limits und eine klare, nicht störende Nachricht für diejenigen, die ihre maximal erlaubten Bestellungen erreicht haben. Es ist mobilfreundlich gestaltet, um sicherzustellen, dass die Nachrichten auf jedem Gerät korrekt angezeigt werden.

## 3. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend.

## 4. Schnelle & sichere Installationsanleitung

Befolgen Sie diese Schritte, um das Modul „Anzahl der erlaubten Bestellungen begrenzen“ zu installieren:

1.  **Laden Sie die neueste Version von Ihrem MyPresta.eu-Konto herunter:**
    -   Melden Sie sich in Ihrem Kundenkonto unter [MyPresta.eu Bestellhistorie & Downloads](https://mypresta.eu/my-account/orders/) an.
    -   Das Modul „Anzahl der erlaubten Bestellungen begrenzen“ ist in mehreren Paketdateien erhältlich, je nach Ihrer PrestaShop-Version (z. B. PrestaShop 8.x, 1.7.x usw.).
    -   Stellen Sie sicher, dass Sie die spezifische ZIP-Datei herunterladen, die für Ihre PrestaShop-Version vorgesehen ist. Entpacken Sie die Datei NICHT auf Ihrem Computer.
2.  **Öffnen Sie das PrestaShop Back Office:**
    -   Navigieren Sie in Ihrem Shop-Admin-Panel zu **Module > Modul-Manager** (oder **Module** / **Module & Dienste** in älteren Versionen).
3.  **Laden Sie das Modul-Archiv hoch:**
    -   Klicken Sie auf die Schaltfläche **„Modul hochladen“** in der oberen rechten Ecke der Seite.
    -   Ziehen Sie Ihre heruntergeladene ZIP-Datei in das Feld oder klicken Sie auf „Datei auswählen“, um sie von Ihrem Laufwerk auszuwählen. PrestaShop überprüft und installiert das Modul automatisch.
4.  **Zugriff auf die Modulkonfiguration:**
    -   Sobald die Installation abgeschlossen ist, klicken Sie auf die Schaltfläche **„Konfigurieren“**, um Ihre Optionen einzurichten.

:::note
Stellen Sie immer sicher, dass Sie ein aktuelles Backup Ihres Shops haben, bevor Sie ein neues Addon installieren.
:::

## 4. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die globalen Limits für Ihre Kunden definieren.

-   **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die maximale Anzahl von Bestellungen, die *jeder* Kunde in Ihrem Shop aufgeben kann, bevor er daran gehindert wird, weitere Bestellungen aufzugeben.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z. B. 3):* Jeder Kunde, der erfolgreich 3 Bestellungen aufgegeben hat, kann keine 4. Bestellung mehr aufgeben. Er sieht eine Meldung, die ihn daran hindert, den Checkout abzuschließen.
    -   *Wenn auf 0 gesetzt oder leer gelassen:* Das Modul wird für globale Limits effektiv deaktiviert, was bedeutet, dass Kunden eine unbegrenzte Anzahl von Bestellungen aufgeben können (es sei denn, es sind spezifische Kundenlimits festgelegt, siehe Abschnitt 4.2).
-   **Empfohlener Wert:** Beginnen Sie mit einem Wert, der Ihrem Geschäftsziel entspricht (z. B. 1 für eine strenge „eins pro Kunde“-Aktion, 5 für ein allgemeines Limit). Wenn Sie nur bestimmte Kunden einschränken möchten, können Sie dieses Feld leer lassen und den speziellen Kundenverwaltungsbildschirm verwenden.
-   **Händlerszenario / Beispiel:** Sie führen einen Flash-Sale für ein sehr begehrtes Produkt durch und möchten sicherstellen, dass jeder Kunde nur eine Chance zum Kauf erhält. Sie würden diesen Wert auf `1` setzen.

### 4.2 Dedizierter Admin-Bildschirm: Kundenbestelllimits (Back Office > Module > Anzahl der erlaubten Bestellungen begrenzen > Kundenbestelllimits)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Bestelllimits für bestimmte Kunden zu verwalten, die das in Abschnitt 4.1 festgelegte globale Limit überschreiben.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Anzahl der erlaubten Bestellungen begrenzen“ suchen, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Kundenbestelllimits“ oder Ähnlichem suchen. Alternativ kann es direkt in Ihrem Haupt-PrestaShop-Menü unter einem neuen, vom Modul erstellten Eintrag erscheinen (z. B. **Kunden > Kundenbestelllimits**).
-   **Verfügbare Aktionen & Einstellungen:**

    -   **Kundensuche/-auswahl:** Sie finden in der Regel eine Suchleiste oder ein Dropdown-Menü, um einen bestehenden Kunden aus Ihrem Shop auszuwählen.
    -   **Individuelles Limit festlegen:** Sobald ein Kunde ausgewählt ist, können Sie eine spezifische Anzahl erlaubter Bestellungen für *diesen bestimmten Kunden* eingeben.
    -   **Bestehende Limits anzeigen/bearbeiten:** Eine Tabelle oder Liste zeigt alle Kunden an, für die Sie benutzerdefinierte Limits festgelegt haben, zusammen mit ihrem aktuellen Limit und möglicherweise ihrer aktuellen Bestellanzahl. Sie können diese Einträge bearbeiten oder löschen.
    -   **Währungsanzeige:** Das Modul kann Währungsinformationen (z. B. `PS_CURRENCY_DEFAULT`) im Kontext von Kundenbestellungen anzeigen, obwohl die Limits selbst numerische Bestellzählungen und keine monetären Werte sind.
-   **Auswirkung von Änderungen:**

    -   *Hinzufügen eines neuen Kundenlimits:* Der ausgewählte Kunde wird nun durch die von Ihnen für ihn festgelegte spezifische Anzahl von Bestellungen eingeschränkt, wodurch das globale Limit (falls festgelegt) überschrieben wird.
    -   *Bearbeiten eines bestehenden Kundenlimits:* Die erlaubte Bestellanzahl des Kunden wird sofort aktualisiert.
    -   *Löschen eines Kundenlimits:* Der Kunde unterliegt wieder dem globalen Bestelllimit (falls festgelegt) oder hat kein Limit, wenn kein globales Limit aktiv ist.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Spezifische Bedürfnisse identifizieren:** Bestimmen Sie, ob bestimmte VIP-Kunden, problematische Kunden oder Kunden, die an speziellen Programmen teilnehmen, einzigartige Bestelllimits benötigen.
    2.  **Suchen und hinzufügen:** Verwenden Sie die Suchfunktion, um den Kunden zu finden.
    3.  **Limit anwenden:** Geben Sie die gewünschte maximale Anzahl von Bestellungen für diesen Kunden ein.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Liste der Kunden mit benutzerdefinierten Limits, um sicherzustellen, dass die Einstellungen weiterhin angemessen sind.

### 4.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :--- | :--- | :--- | :--- (PrestaShop 8.x, 1.7.x, etc.).
   - Stellen Sie sicher, dass Sie die spezifische ZIP-Datei herunterladen, die für Ihre PrestaShop-Version vorgesehen ist. Entpacken Sie die Datei NICHT auf Ihrem Computer.
2.  **Öffnen Sie das PrestaShop Back Office:**
    -   Navigieren Sie in Ihrem Shop-Admin-Panel zu **Module > Modul-Manager** (oder **Module** / **Module & Dienste** in älteren Versionen).
3.  **Laden Sie das Modul-Archiv hoch:**
    -   Klicken Sie auf die Schaltfläche **„Modul hochladen“** in der oberen rechten Ecke der Seite.
    -   Ziehen Sie Ihre heruntergeladene ZIP-Datei in das Feld oder klicken Sie auf „Datei auswählen“, um sie von Ihrem Laufwerk auszuwählen. PrestaShop überprüft und installiert das Modul automatisch.
4.  **Zugriff auf die Modulkonfiguration:**
    -   Sobald die Installation abgeschlossen ist, klicken Sie auf die Schaltfläche **„Konfigurieren“**, um Ihre Optionen einzurichten.

:::note
Stellen Sie immer sicher, dass Sie ein aktuelles Backup Ihres Shops haben, bevor Sie ein neues Addon installieren.
:::

## 4. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die globalen Limits für Ihre Kunden definieren.

-   **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die maximale Anzahl von Bestellungen, die *jeder* Kunde in Ihrem Shop aufgeben kann, bevor er daran gehindert wird, weitere Bestellungen aufzugeben.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z. B. 3):* Jeder Kunde, der erfolgreich 3 Bestellungen aufgegeben hat, kann keine 4. Bestellung mehr aufgeben. Er sieht eine Meldung, die ihn daran hindert, den Checkout abzuschließen.
    -   *Wenn auf 0 gesetzt oder leer gelassen:* Das Modul wird für globale Limits effektiv deaktiviert, was bedeutet, dass Kunden eine unbegrenzte Anzahl von Bestellungen aufgeben können (es sei denn, es sind spezifische Kundenlimits festgelegt, siehe Abschnitt 4.2).
-   **Empfohlener Wert:** Beginnen Sie mit einem Wert, der Ihrem Geschäftsziel entspricht (z. B. 1 für eine strenge „eins pro Kunde“-Aktion, 5 für ein allgemeines Limit). Wenn Sie nur bestimmte Kunden einschränken möchten, können Sie dieses Feld leer lassen und den speziellen Kundenverwaltungsbildschirm verwenden.
-   **Händlerszenario / Beispiel:** Sie führen einen Flash-Sale für ein sehr begehrtes Produkt durch und möchten sicherstellen, dass jeder Kunde nur eine Chance zum Kauf erhält. Sie würden diesen Wert auf `1` setzen.

### 4.2 Dedizierter Admin-Bildschirm: Kundenbestelllimits (Back Office > Module > Anzahl der erlaubten Bestellungen begrenzen > Kundenbestelllimits)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Bestelllimits für bestimmte Kunden zu verwalten, die das in Abschnitt 4.1 festgelegte globale Limit überschreiben.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Anzahl der erlaubten Bestellungen begrenzen“ suchen, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Kundenbestelllimits“ oder Ähnlichem suchen. Alternativ kann es direkt in Ihrem Haupt-PrestaShop-Menü unter einem neuen, vom Modul erstellten Eintrag erscheinen (z. B. **Kunden > Kundenbestelllimits**).
-   **Verfügbare Aktionen & Einstellungen:**

    -   **Kundensuche/-auswahl:** Sie finden in der Regel eine Suchleiste oder ein Dropdown-Menü, um einen bestehenden Kunden aus Ihrem Shop auszuwählen.
    -   **Individuelles Limit festlegen:** Sobald ein Kunde ausgewählt ist, können Sie eine spezifische Anzahl erlaubter Bestellungen für *diesen bestimmten Kunden* eingeben.
    -   **Bestehende Limits anzeigen/bearbeiten:** Eine Tabelle oder Liste zeigt alle Kunden an, für die Sie benutzerdefinierte Limits festgelegt haben, zusammen mit ihrem aktuellen Limit und möglicherweise ihrer aktuellen Bestellanzahl. Sie können diese Einträge bearbeiten oder löschen.
    -   **Währungsanzeige:** Das Modul kann Währungsinformationen (z. B. `PS_CURRENCY_DEFAULT`) im Kontext von Kundenbestellungen anzeigen, obwohl die Limits selbst numerische Bestellzählungen und keine monetären Werte sind.
-   **Auswirkung von Änderungen:**

    -   *Hinzufügen eines neuen Kundenlimits:* Der ausgewählte Kunde wird nun durch die von Ihnen für ihn festgelegte spezifische Anzahl von Bestellungen eingeschränkt, wodurch das globale Limit (falls festgelegt) überschrieben wird.
    -   *Bearbeiten eines bestehenden Kundenlimits:* Die erlaubte Bestellanzahl des Kunden wird sofort aktualisiert.
    -   *Löschen eines Kundenlimits:* Der Kunde unterliegt wieder dem globalen Bestelllimit (falls festgelegt) oder hat kein Limit, wenn kein globales Limit aktiv ist.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Spezifische Bedürfnisse identifizieren:** Bestimmen Sie, ob bestimmte VIP-Kunden, problematische Kunden oder Kunden, die an speziellen Programmen teilnehmen, einzigartige Bestelllimits benötigen.
    2.  **Suchen und hinzufügen:** Verwenden Sie die Suchfunktion, um den Kunden zu finden.
    3.  **Limit anwenden:** Geben Sie die gewünschte maximale Anzahl von Bestellungen für diesen Kunden ein.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Liste der Kunden mit benutzerdefinierten Limits, um sicherzustellen, dass die Einstellungen weiterhin angemessen sind.

### 4.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :--- | :--- | :--- | :--- (PrestaShop 8.x, 1.7.x, etc.).
   - Stellen Sie sicher, dass Sie die spezifische ZIP-Datei herunterladen, die für Ihre PrestaShop-Version vorgesehen ist. Entpacken Sie die Datei NICHT auf Ihrem Computer.
2.  **Öffnen Sie das PrestaShop Back Office:**
    -   Navigieren Sie in Ihrem Shop-Admin-Panel zu **Module > Modul-Manager** (oder **Module** / **Module & Dienste** in älteren Versionen).
3.  **Laden Sie das Modul-Archiv hoch:**
    -   Klicken Sie auf die Schaltfläche **„Modul hochladen“** in der oberen rechten Ecke der Seite.
    -   Ziehen Sie Ihre heruntergeladene ZIP-Datei in das Feld oder klicken Sie auf „Datei auswählen“, um sie von Ihrem Laufwerk auszuwählen. PrestaShop überprüft und installiert das Modul automatisch.
4.  **Zugriff auf die Modulkonfiguration:**
    -   Sobald die Installation abgeschlossen ist, klicken Sie auf die Schaltfläche **„Konfigurieren“**, um Ihre Optionen einzurichten.

:::note
Stellen Sie immer sicher, dass Sie ein aktuelles Backup Ihres Shops haben, bevor Sie ein neues Addon installieren.
:::

## 4. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die globalen Limits für Ihre Kunden definieren.

-   **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die maximale Anzahl von Bestellungen, die *jeder* Kunde in Ihrem Shop aufgeben kann, bevor er daran gehindert wird, weitere Bestellungen aufzugeben.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z. B. 3):* Jeder Kunde, der erfolgreich 3 Bestellungen aufgegeben hat, kann keine 4. Bestellung mehr aufgeben. Er sieht eine Meldung, die ihn daran hindert, den Checkout abzuschließen.
    -   *Wenn auf 0 gesetzt oder leer gelassen:* Das Modul wird für globale Limits effektiv deaktiviert, was bedeutet, dass Kunden eine unbegrenzte Anzahl von Bestellungen aufgeben können (es sei denn, es sind spezifische Kundenlimits festgelegt, siehe Abschnitt 4.2).
-   **Empfohlener Wert:** Beginnen Sie mit einem Wert, der Ihrem Geschäftsziel entspricht (z. B. 1 für eine strenge „eins pro Kunde“-Aktion, 5 für ein allgemeines Limit). Wenn Sie nur bestimmte Kunden einschränken möchten, können Sie dieses Feld leer lassen und den speziellen Kundenverwaltungsbildschirm verwenden.
-   **Händlerszenario / Beispiel:** Sie führen einen Flash-Sale für ein sehr begehrtes Produkt durch und möchten sicherstellen, dass jeder Kunde nur eine Chance zum Kauf erhält. Sie würden diesen Wert auf `1` setzen.

### 4.2 Dedizierter Admin-Bildschirm: Kundenbestelllimits (Back Office > Module > Anzahl der erlaubten Bestellungen begrenzen > Kundenbestelllimits)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Bestelllimits für bestimmte Kunden zu verwalten, die das in Abschnitt 4.1 festgelegte globale Limit überschreiben.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Anzahl der erlaubten Bestellungen begrenzen“ suchen, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Kundenbestelllimits“ oder Ähnlichem suchen. Alternativ kann es direkt in Ihrem Haupt-PrestaShop-Menü unter einem neuen, vom Modul erstellten Eintrag erscheinen (z. B. **Kunden > Kundenbestelllimits**).
-   **Verfügbare Aktionen & Einstellungen:**

    -   **Kundensuche/-auswahl:** Sie finden in der Regel eine Suchleiste oder ein Dropdown-Menü, um einen bestehenden Kunden aus Ihrem Shop auszuwählen.
    -   **Individuelles Limit festlegen:** Sobald ein Kunde ausgewählt ist, können Sie eine spezifische Anzahl erlaubter Bestellungen für *diesen bestimmten Kunden* eingeben.
    -   **Bestehende Limits anzeigen/bearbeiten:** Eine Tabelle oder Liste zeigt alle Kunden an, für die Sie benutzerdefinierte Limits festgelegt haben, zusammen mit ihrem aktuellen Limit und möglicherweise ihrer aktuellen Bestellanzahl. Sie können diese Einträge bearbeiten oder löschen.
    -   **Währungsanzeige:** Das Modul kann Währungsinformationen (z. B. `PS_CURRENCY_DEFAULT`) im Kontext von Kundenbestellungen anzeigen, obwohl die Limits selbst numerische Bestellzählungen und keine monetären Werte sind.
-   **Auswirkung von Änderungen:**

    -   *Hinzufügen eines neuen Kundenlimits:* Der ausgewählte Kunde wird nun durch die von Ihnen für ihn festgelegte spezifische Anzahl von Bestellungen eingeschränkt, wodurch das globale Limit (falls festgelegt) überschrieben wird.
    -   *Bearbeiten eines bestehenden Kundenlimits:* Die erlaubte Bestellanzahl des Kunden wird sofort aktualisiert.
    -   *Löschen eines Kundenlimits:* Der Kunde unterliegt wieder dem globalen Bestelllimit (falls festgelegt) oder hat kein Limit, wenn kein globales Limit aktiv ist.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Spezifische Bedürfnisse identifizieren:** Bestimmen Sie, ob bestimmte VIP-Kunden, problematische Kunden oder Kunden, die an speziellen Programmen teilnehmen, einzigartige Bestelllimits benötigen.
    2.  **Suchen und hinzufügen:** Verwenden Sie die Suchfunktion, um den Kunden zu finden.
    3.  **Limit anwenden:** Geben Sie die gewünschte maximale Anzahl von Bestellungen für diesen Kunden ein.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Liste der Kunden mit benutzerdefinierten Limits, um sicherzustellen, dass die Einstellungen weiterhin angemessen sind.

### 4.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :--- | :--- | :--- | :--- (PrestaShop 8.x, 1.7.x, etc.).
   - Stellen Sie sicher, dass Sie die spezifische ZIP-Datei herunterladen, die für Ihre PrestaShop-Version vorgesehen ist. Entpacken Sie die Datei NICHT auf Ihrem Computer.
2.  **Öffnen Sie das PrestaShop Back Office:**
    -   Navigieren Sie in Ihrem Shop-Admin-Panel zu **Module > Modul-Manager** (oder **Module** / **Module & Dienste** in älteren Versionen).
3.  **Laden Sie das Modul-Archiv hoch:**
    -   Klicken Sie auf die Schaltfläche **„Modul hochladen“** in der oberen rechten Ecke der Seite.
    -   Ziehen Sie Ihre heruntergeladene ZIP-Datei in das Feld oder klicken Sie auf „Datei auswählen“, um sie von Ihrem Laufwerk auszuwählen. PrestaShop überprüft und installiert das Modul automatisch.
4.  **Zugriff auf die Modulkonfiguration:**
    -   Sobald die Installation abgeschlossen ist, klicken Sie auf die Schaltfläche **„Konfigurieren“**, um Ihre Optionen einzurichten.

:::note
Stellen Sie immer sicher, dass Sie ein aktuelles Backup Ihres Shops haben, bevor Sie ein neues Addon installieren.
:::

## 4. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die globalen Limits für Ihre Kunden definieren.

-   **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die maximale Anzahl von Bestellungen, die *jeder* Kunde in Ihrem Shop aufgeben kann, bevor er daran gehindert wird, weitere Bestellungen aufzugeben.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z. B. 3):* Jeder Kunde, der erfolgreich 3 Bestellungen aufgegeben hat, kann keine 4. Bestellung mehr aufgeben. Er sieht eine Meldung, die ihn daran hindert, den Checkout abzuschließen.
    -   *Wenn auf 0 gesetzt oder leer gelassen:* Das Modul wird für globale Limits effektiv deaktiviert, was bedeutet, dass Kunden eine unbegrenzte Anzahl von Bestellungen aufgeben können (es sei denn, es sind spezifische Kundenlimits festgelegt, siehe Abschnitt 4.2).
-   **Empfohlener Wert:** Beginnen Sie mit einem Wert, der Ihrem Geschäftsziel entspricht (z. B. 1 für eine strenge „eins pro Kunde“-Aktion, 5 für ein allgemeines Limit). Wenn Sie nur bestimmte Kunden einschränken möchten, können Sie dieses Feld leer lassen und den speziellen Kundenverwaltungsbildschirm verwenden.
-   **Händlerszenario / Beispiel:** Sie führen einen Flash-Sale für ein sehr begehrtes Produkt durch und möchten sicherstellen, dass jeder Kunde nur eine Chance zum Kauf erhält. Sie würden diesen Wert auf `1` setzen.

### 4.2 Dedizierter Admin-Bildschirm: Kundenbestelllimits (Back Office > Module > Anzahl der erlaubten Bestellungen begrenzen > Kundenbestelllimits)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Bestelllimits für bestimmte Kunden zu verwalten, die das in Abschnitt 4.1 festgelegte globale Limit überschreiben.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Anzahl der erlaubten Bestellungen begrenzen“ suchen, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Kundenbestelllimits“ oder Ähnlichem suchen. Alternativ kann es direkt in Ihrem Haupt-PrestaShop-Menü unter einem neuen, vom Modul erstellten Eintrag erscheinen (z. B. **Kunden > Kundenbestelllimits**).
-   **Verfügbare Aktionen & Einstellungen:**

    -   **Kundensuche/-auswahl:** Sie finden in der Regel eine Suchleiste oder ein Dropdown-Menü, um einen bestehenden Kunden aus Ihrem Shop auszuwählen.
    -   **Individuelles Limit festlegen:** Sobald ein Kunde ausgewählt ist, können Sie eine spezifische Anzahl erlaubter Bestellungen für *diesen bestimmten Kunden* eingeben.
    -   **Bestehende Limits anzeigen/bearbeiten:** Eine Tabelle oder Liste zeigt alle Kunden an, für die Sie benutzerdefinierte Limits festgelegt haben, zusammen mit ihrem aktuellen Limit und möglicherweise ihrer aktuellen Bestellanzahl. Sie können diese Einträge bearbeiten oder löschen.
    -   **Währungsanzeige:** Das Modul kann Währungsinformationen (z. B. `PS_CURRENCY_DEFAULT`) im Kontext von Kundenbestellungen anzeigen, obwohl die Limits selbst numerische Bestellzählungen und keine monetären Werte sind.
-   **Auswirkung von Änderungen:**

    -   *Hinzufügen eines neuen Kundenlimits:* Der ausgewählte Kunde wird nun durch die von Ihnen für ihn festgelegte spezifische Anzahl von Bestellungen eingeschränkt, wodurch das globale Limit (falls festgelegt) überschrieben wird.
    -   *Bearbeiten eines bestehenden Kundenlimits:* Die erlaubte Bestellanzahl des Kunden wird sofort aktualisiert.
    -   *Löschen eines Kundenlimits:* Der Kunde unterliegt wieder dem globalen Bestelllimit (falls festgelegt) oder hat kein Limit, wenn kein globales Limit aktiv ist.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Spezifische Bedürfnisse identifizieren:** Bestimmen Sie, ob bestimmte VIP-Kunden, problematische Kunden oder Kunden, die an speziellen Programmen teilnehmen, einzigartige Bestelllimits benötigen.
    2.  **Suchen und hinzufügen:** Verwenden Sie die Suchfunktion, um den Kunden zu finden.
    3.  **Limit anwenden:** Geben Sie die gewünschte maximale Anzahl von Bestellungen für diesen Kunden ein.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Liste der Kunden mit benutzerdefinierten Limits, um sicherzustellen, dass die Einstellungen weiterhin angemessen sind.

### 4.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :--- | :--- | :--- | :--- (PrePrestaShop 8.x, 1.7.x, etc.).
   - Stellen Sie sicher, dass Sie die spezifische ZIP-Datei herunterladen, die für Ihre PrestaShop-Version vorgesehen ist. Entpacken Sie die Datei NICHT auf Ihrem Computer.
2.  **Öffnen Sie das PrestaShop Back Office:**
    -   Navigieren Sie in Ihrem Shop-Admin-Panel zu **Module > Modul-Manager** (oder **Module** / **Module & Dienste** in älteren Versionen).
3.  **Laden Sie das Modul-Archiv hoch:**
    -   Klicken Sie auf die Schaltfläche **„Modul hochladen“** in der oberen rechten Ecke der Seite.
    -   Ziehen Sie Ihre heruntergeladene ZIP-Datei in das Feld oder klicken Sie auf „Datei auswählen“, um sie von Ihrem Laufwerk auszuwählen. PrestaShop überprüft und installiert das Modul automatisch.
4.  **Zugriff auf die Modulkonfiguration:**
    -   Sobald die Installation abgeschlossen ist, klicken Sie auf die Schaltfläche **„Konfigurieren“**, um Ihre Optionen einzurichten.

:::note
Stellen Sie immer sicher, dass Sie ein aktuelles Backup Ihres Shops haben, bevor Sie ein neues Addon installieren.
:::

## 4. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die globalen Limits für Ihre Kunden definieren.

-   **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die maximale Anzahl von Bestellungen, die *jeder* Kunde in Ihrem Shop aufgeben kann, bevor er daran gehindert wird, weitere Bestellungen aufzugeben.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z. B. 3):* Jeder Kunde, der erfolgreich 3 Bestellungen aufgegeben hat, kann keine 4. Bestellung mehr aufgeben. Er sieht eine Meldung, die ihn daran hindert, den Checkout abzuschließen.
    -   *Wenn auf 0 gesetzt oder leer gelassen:* Das Modul wird für globale Limits effektiv deaktiviert, was bedeutet, dass Kunden eine unbegrenzte Anzahl von Bestellungen aufgeben können (es sei denn, es sind spezifische Kundenlimits festgelegt, siehe Abschnitt 4.2).
-   **Empfohlener Wert:** Beginnen Sie mit einem Wert, der Ihrem Geschäftsziel entspricht (z. B. 1 für eine strenge „eins pro Kunde“-Aktion, 5 für ein allgemeines Limit). Wenn Sie nur bestimmte Kunden einschränken möchten, können Sie dieses Feld leer lassen und den speziellen Kundenverwaltungsbildschirm verwenden.
-   **Händlerszenario / Beispiel:** Sie führen einen Flash-Sale für ein sehr begehrtes Produkt durch und möchten sicherstellen, dass jeder Kunde nur eine Chance zum Kauf erhält. Sie würden diesen Wert auf `1` setzen.

### 4.2 Dedizierter Admin-Bildschirm: Kundenbestelllimits (Back Office > Module > Anzahl der erlaubten Bestellungen begrenzen > Kundenbestelllimits)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Bestelllimits für bestimmte Kunden zu verwalten, die das in Abschnitt 4.1 festgelegte globale Limit überschreiben.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Anzahl der erlaubten Bestellungen begrenzen“ suchen, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Kundenbestelllimits“ oder Ähnlichem suchen. Alternativ kann es direkt in Ihrem Haupt-PrestaShop-Menü unter einem neuen, vom Modul erstellten Eintrag erscheinen (z. B. **Kunden > Kundenbestelllimits**).
-   **Verfügbare Aktionen & Einstellungen:**

    -   **Kundensuche/-auswahl:** Sie finden in der Regel eine Suchleiste oder ein Dropdown-Menü, um einen bestehenden Kunden aus Ihrem Shop auszuwählen.
    -   **Individuelles Limit festlegen:** Sobald ein Kunde ausgewählt ist, können Sie eine spezifische Anzahl erlaubter Bestellungen für *diesen bestimmten Kunden* eingeben.
    -   **Bestehende Limits anzeigen/bearbeiten:** Eine Tabelle oder Liste zeigt alle Kunden an, für die Sie benutzerdefinierte Limits festgelegt haben, zusammen mit ihrem aktuellen Limit und möglicherweise ihrer aktuellen Bestellanzahl. Sie können diese Einträge bearbeiten oder löschen.
    -   **Währungsanzeige:** Das Modul kann Währungsinformationen (z. B. `PS_CURRENCY_DEFAULT`) im Kontext von Kundenbestellungen anzeigen, obwohl die Limits selbst numerische Bestellzählungen und keine monetären Werte sind.
-   **Auswirkung von Änderungen:**

    -   *Hinzufügen eines neuen Kundenlimits:* Der ausgewählte Kunde wird nun durch die von Ihnen für ihn festgelegte spezifische Anzahl von Bestellungen eingeschränkt, wodurch das globale Limit (falls festgelegt) überschrieben wird.
    -   *Bearbeiten eines bestehenden Kundenlimits:* Die erlaubte Bestellanzahl des Kunden wird sofort aktualisiert.
    -   *Löschen eines Kundenlimits:* Der Kunde unterliegt wieder dem globalen Bestelllimit (falls festgelegt) oder hat kein Limit, wenn kein globales Limit aktiv ist.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Spezifische Bedürfnisse identifizieren:** Bestimmen Sie, ob bestimmte VIP-Kunden, problematische Kunden oder Kunden, die an speziellen Programmen teilnehmen, einzigartige Bestelllimits benötigen.
    2.  **Suchen und hinzufügen:** Verwenden Sie die Suchfunktion, um den Kunden zu finden.
    3.  **Limit anwenden:** Geben Sie die gewünschte maximale Anzahl von Bestellungen für diesen Kunden ein.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Liste der Kunden mit benutzerdefinierten Limits, um sicherzustellen, dass die Einstellungen weiterhin angemessen sind.

### 4.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :--- | :--- | :--- | :---
```
```yaml
title: "PrestaShop-Modul: Bestellanzahl begrenzen"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Anzahl der erlaubten Bestellungen begrenzen' von MyPresta.eu."
sidebar:
  label: "Bestellanzahl begrenzen – Händlerhandbuch & Konfigurationsanleitung"
---

# Anzahl der erlaubten Bestellungen begrenzen

## 1. Was dieses Modul tut und warum Sie es brauchen

Das Modul „Anzahl der erlaubten Bestellungen begrenzen“ gibt Ihnen präzise Kontrolle darüber, wie viele Bestellungen jeder Kunde in Ihrem PrestaShop-Shop aufgeben kann. Stellen Sie sich vor, Sie führen eine Sonderaktion durch, verkaufen Artikel in limitierter Auflage oder betreiben ein Großhandelsgeschäft, in dem Sie verhindern möchten, dass ein einzelner Kunde den Lagerbestand monopolisiert oder Kreditlimits überschreitet. Dieses Modul ist Ihre Lösung.

**Hauptvorteile:**

-   **Bestandskontrolle:** Verhindern Sie, dass einzelne Kunden limitierte Bestände aufkaufen, und sorgen Sie für eine faire Verteilung.
-   **Fairness & Gleichheit:** Geben Sie mehr Kunden die Möglichkeit, beliebte oder limitierte Artikel zu kaufen.
-   **Betrugsprävention:** Mindern Sie potenzielle betrügerische Aktivitäten, indem Sie die Anzahl der Transaktionen pro Benutzer begrenzen.
-   **Großhandelsmanagement:** Setzen Sie spezifische Einkaufsrichtlinien für B2B-Kunden durch, um zu verhindern, dass diese voreingestellte Bestellquoten überschreiten.
-   **Aktionsmanagement:** Stellen Sie sicher, dass Werbeangebote oder Rabatte fair genutzt und nicht von wenigen Kunden missbraucht werden.
-   **Betriebliche Effizienz:** Reduzieren Sie den Aufwand für die Verwaltung übermäßiger Bestellungen von einem einzelnen Kunden, insbesondere bei Nischenprodukten.

Dieses Modul ist ideal für Einzelhändler, die limitierte Bestände verkaufen, Unternehmen, die exklusive Aktionen durchführen, oder B2B-Großhändler, die Kundenkauflimits verwalten müssen.

## 2. Wo Kunden es in Ihrem Shop sehen (Front-Office-Rundgang)

Dieses Modul arbeitet hauptsächlich im Hintergrund und setzt Ihre Bestelllimits durch. Kunden sehen kein spezifisches „Block“ oder „Widget“ dieses Moduls auf jeder Seite. Stattdessen macht sich seine Wirkung am Kaufpunkt bemerkbar:

-   **Während des Checkouts:** Wenn ein Kunde versucht, eine Bestellung aufzugeben, die sein erlaubtes Limit überschreiten würde, verhindert das Modul, dass er den Kauf abschließt. Er sieht dann in der Regel eine Meldung, die darauf hinweist, dass er keine weiteren Bestellungen aufgeben kann.
-   **Warenkorb:** Je nach Konfiguration kann eine Meldung im Warenkorb erscheinen, wenn der Kunde sein Limit bereits erreicht hat, und ihn informieren, bevor er überhaupt zum Checkout geht.
-   **Produktseite (indirekt):** Obwohl nicht direkt sichtbar, bedeuten die Einschränkungen des Moduls, dass ein Kunde, sobald er sein Limit erreicht hat, effektiv keine weiteren Produkte kaufen kann, unabhängig davon, welche Produktseite er besucht.

Das Modul sorgt für ein reibungsloses Erlebnis für Kunden innerhalb ihrer Limits und eine klare, nicht störende Nachricht für diejenigen, die ihre maximal erlaubten Bestellungen erreicht haben. Es ist mobilfreundlich gestaltet, um sicherzustellen, dass die Nachrichten auf jedem Gerät korrekt angezeigt werden.

## 3. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend.

## 4. Schnelle & sichere Installationsanleitung

Befolgen Sie diese Schritte, um das Modul „Anzahl der erlaubten Bestellungen begrenzen“ zu installieren:

1.  **Laden Sie die neueste Version von Ihrem MyPresta.eu-Konto herunter:**
    -   Melden Sie sich in Ihrem Kundenkonto unter [MyPresta.eu Bestellhistorie & Downloads](https://mypresta.eu/my-account/orders/) an.
    -   Das Modul „Anzahl der erlaubten Bestellungen begrenzen“ ist in mehreren Paketdateien erhältlich, je nach Ihrer PrestaShop-Version (z. B. PrestaShop 8.x, 1.7.x usw.).
    -   Stellen Sie sicher, dass Sie die spezifische ZIP-Datei herunterladen, die für Ihre PrestaShop-Version vorgesehen ist. Entpacken Sie die Datei NICHT auf Ihrem Computer.
2.  **Öffnen Sie das PrestaShop Back Office:**
    -   Navigieren Sie in Ihrem Shop-Admin-Panel zu **Module > Modul-Manager** (oder **Module** / **Module & Dienste** in älteren Versionen).
3.  **Laden Sie das Modul-Archiv hoch:**
    -   Klicken Sie auf die Schaltfläche **„Modul hochladen“** in der oberen rechten Ecke der Seite.
    -   Ziehen Sie Ihre heruntergeladene ZIP-Datei in das Feld oder klicken Sie auf „Datei auswählen“, um sie von Ihrem Laufwerk auszuwählen. PrestaShop überprüft und installiert das Modul automatisch.
4.  **Zugriff auf die Modulkonfiguration:**
    -   Sobald die Installation abgeschlossen ist, klicken Sie auf die Schaltfläche **„Konfigurieren“**, um Ihre Optionen einzurichten.

:::note
Stellen Sie immer sicher, dass Sie ein aktuelles Backup Ihres Shops haben, bevor Sie ein neues Addon installieren.
:::

## 4. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die globalen Limits für Ihre Kunden definieren.

-   **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie definiert die maximale Anzahl von Bestellungen, die *jeder* Kunde in Ihrem Shop aufgeben kann, bevor er daran gehindert wird, weitere Bestellungen aufzugeben.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z. B. 3):* Jeder Kunde, der erfolgreich 3 Bestellungen aufgegeben hat, kann keine 4. Bestellung mehr aufgeben. Er sieht eine Meldung, die ihn daran hindert, den Checkout abzuschließen.
    -   *Wenn auf 0 gesetzt oder leer gelassen:* Das Modul wird für globale Limits effektiv deaktiviert, was bedeutet, dass Kunden eine unbegrenzte Anzahl von Bestellungen aufgeben können (es sei denn, es sind spezifische Kundenlimits festgelegt, siehe Abschnitt 4.2).
-   **Empfohlener Wert:** Beginnen Sie mit einem Wert, der Ihrem Geschäftsziel entspricht (z. B. 1 für eine strenge „eins pro Kunde“-Aktion, 5 für ein allgemeines Limit). Wenn Sie nur bestimmte Kunden einschränken möchten, können Sie dieses Feld leer lassen und den speziellen Kundenverwaltungsbildschirm verwenden.
-   **Händlerszenario / Beispiel:** Sie führen einen Flash-Sale für ein sehr begehrtes Produkt durch und möchten sicherstellen, dass jeder Kunde nur eine Chance zum Kauf erhält. Sie würden diesen Wert auf `1` setzen.

### 4.2 Dedizierter Admin-Bildschirm: Kundenbestelllimits (Back Office > Module > Anzahl der erlaubten Bestellungen begrenzen > Kundenbestelllimits)

Dieser Bildschirm ermöglicht es Ihnen, individuelle Bestelllimits für bestimmte Kunden zu verwalten, die das in Abschnitt 4.1 festgelegte globale Limit überschreiben.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, „Anzahl der erlaubten Bestellungen begrenzen“ suchen, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Kundenbestelllimits“ oder Ähnlichem suchen. Alternativ kann es direkt in Ihrem Haupt-PrestaShop-Menü unter einem neuen, vom Modul erstellten Eintrag erscheinen (z. B. **Kunden > Kundenbestelllimits**).
-   **Verfügbare Aktionen & Einstellungen:**

    -   **Kundensuche/-auswahl:** Sie finden in der Regel eine Suchleiste oder ein Dropdown-Menü, um einen bestehenden Kunden aus Ihrem Shop auszuwählen.
    -   **Individuelles Limit festlegen:** Sobald ein Kunde ausgewählt ist, können Sie eine spezifische Anzahl erlaubter Bestellungen für *diesen bestimmten Kunden* eingeben.
    -   **Bestehende Limits anzeigen/bearbeiten:** Eine Tabelle oder Liste zeigt alle Kunden an, für die Sie benutzerdefinierte Limits festgelegt haben, zusammen mit ihrem aktuellen Limit und möglicherweise ihrer aktuellen Bestellanzahl. Sie können diese Einträge bearbeiten oder löschen.
    -   **Währungsanzeige:** Das Modul kann Währungsinformationen (z. B. `PS_CURRENCY_DEFAULT`) im Kontext von Kundenbestellungen anzeigen, obwohl die Limits selbst numerische Bestellzählungen und keine monetären Werte sind.
-   **Auswirkung von Änderungen:**

    -   *Hinzufügen eines neuen Kundenlimits:* Der ausgewählte Kunde wird nun durch die von Ihnen für ihn festgelegte spezifische Anzahl von Bestellungen eingeschränkt, wodurch das globale Limit (falls festgelegt) überschrieben wird.
    -   *Bearbeiten eines bestehenden Kundenlimits:* Die erlaubte Bestellanzahl des Kunden wird sofort aktualisiert.
    -   *Löschen eines Kundenlimits:* Der Kunde unterliegt wieder dem globalen Bestelllimit (falls festgelegt) oder hat kein Limit, wenn kein globales Limit aktiv ist.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Spezifische Bedürfnisse identifizieren:** Bestimmen Sie, ob bestimmte VIP-Kunden, problematische Kunden oder Kunden, die an speziellen Programmen teilnehmen, einzigartige Bestelllimits benötigen.
    2.  **Suchen und hinzufügen:** Verwenden Sie die Suchfunktion, um den Kunden zu finden.
    3.  **Limit anwenden:** Geben Sie die gewünschte maximale Anzahl von Bestellungen für diesen Kunden ein.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Liste der Kunden mit benutzerdefinierten Limits, um sicherzustellen, dass die Einstellungen weiterhin angemessen sind.

### 4.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :--- | :--- | :--- | :---
