---
title: "Maximale verfügbare Produktmenge zum Kauf nach Datum - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Maximale verfügbare Produktmenge zum Kauf nach Datum' von MyPresta.eu."
sidebar:
  label: "Maximale verfügbare Produktmenge zum Kauf nach Datum"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Maximum available product quantity to purchase by date auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/maximum-available-product-quantity-to-purchase-by-date.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/maximum-available-product-quantity-to-purchase-by-date/)
>
> ---


# Maximale verfügbare Produktmenge zum Kauf nach Datum

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Dies ist der Hauptkonfigurationsbildschirm für das Modul, der sofort nach der Installation oder durch Klicken auf "Konfigurieren" im Modul-Manager aufgerufen wird.

-   **Was diese Einstellung bewirkt:** Dieser Bildschirm enthält typischerweise allgemeine Einstellungen für das Modul, wie z.B. das Aktivieren/Deaktivieren seiner Kernfunktionalität oder das Festlegen globaler Präferenzen.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert:* Die Mengenbegrenzungsfunktionen des Moduls sind in Ihrem Shop basierend auf den von Ihnen definierten Regeln aktiv.
    -   *Wenn deaktiviert:* Das Modul wird keine Mengenbegrenzungen mehr durchsetzen, und Kunden können jede verfügbare Lagermenge kaufen.
-   **Empfohlener Wert:** "JA" (Aktiviert), um die Kernfunktionalität des Moduls zu aktivieren.
-   **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten mit der Definition von Limits beginnen. Der erste Schritt ist sicherzustellen, dass das Modul auf diesem Bildschirm aktiv ist, bevor Sie mit der Definition spezifischer Produktlimits fortfahren.

### 2.2 Dedizierter Admin-Bildschirm: Produktkaufmengenlimit nach Datum (Back Office > Katalog > Produktkaufmengenlimit nach Datum)
Dies ist der primäre Bildschirm, auf dem Sie alle Ihre Produktmengenlimits basierend auf Datumsbereichen definieren und verwalten.

**Bildschirmname & Menüpfad:**
Sie finden diesen Bildschirm, indem Sie im PrestaShop Back Office-Menü zu **Katalog > Produktkaufmengenlimit nach Datum** navigieren.

**Verfügbare Aktionen & Einstellungen:**
Dieser Bildschirm zeigt eine Liste (Tabelle) aller bestehenden Mengenlimits an, die Sie eingerichtet haben. Sie können neue Limits hinzufügen, bestehende bearbeiten oder löschen.

#### **Spalten der Auflistungstabelle:**
-   **ID:** Eine eindeutige Kennung für jede Mengenbegrenzungsregel.
-   **Produkt:** Der Name des Produkts, für das die Begrenzung gilt.
-   **Datum von:** Das Startdatum und die Startzeit, ab der die Mengenbegrenzung aktiv wird.
-   **Datum bis:** Das Enddatum und die Endzeit, zu der die Mengenbegrenzung abläuft.
-   **Menge:** Die maximale Anzahl von Einheiten des Produkts, die innerhalb des angegebenen Datumsbereichs gekauft werden können.
-   **Aktiv:** Ein Schalter (Ja/Nein) zum Aktivieren oder Deaktivieren einer bestimmten Begrenzungsregel, ohne sie zu löschen.

#### **Hinzufügen / Bearbeiten einer Mengenbegrenzungsregel:**
Wenn Sie auf "Neu hinzufügen" klicken oder eine bestehende Regel bearbeiten, sehen Sie ein Formular mit den folgenden Feldern:

-   **Produktkaufmengenlimit nach Datum:** Dies ist der Haupttitel des Formulars.
-   **ID Produkt:**
    -   **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, das spezifische Produkt auszuwählen, für das diese Mengenbegrenzung gelten soll. Sie verwenden typischerweise eine Suchleiste, um das Produkt nach Name oder ID zu finden.
    -   **Auswirkung der Änderung dieser Einstellung:** Bestimmt, welche Produktkaufmenge durch diese Regel eingeschränkt wird.
    -   **Empfohlener Wert:** Wählen Sie das genaue Produkt aus, das Sie begrenzen möchten.
    -   **Händlerszenario / Beispiel:** Sie möchten den Verkauf von "Sommer-T-Shirt" auf 50 Einheiten begrenzen. Sie würden hier nach "Sommer-T-Shirt" suchen und es auswählen.
-   **Datum von:**
    -   **Was diese Einstellung bewirkt:** Definiert das genaue Datum und die Uhrzeit, wann diese Mengenbegrenzungsregel aktiv wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Die Begrenzung wird nur für Käufe durchgesetzt, die an oder nach diesem Datum/dieser Uhrzeit getätigt werden.
    -   **Empfohlener Wert:** Legen Sie das präzise Startdatum und die Startzeit für Ihre Aktion oder Einschränkung fest.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass die Begrenzung am 1. August 2024 um 9:00 Uhr beginnt.
-   **Datum bis:**
    -   **Was diese Einstellung bewirkt:** Definiert das genaue Datum und die Uhrzeit, wann diese Mengenbegrenzungsregel abläuft.
    -   **Auswirkung der Änderung dieser Einstellung:** Nach diesem Datum/dieser Uhrzeit wird die Begrenzung nicht mehr durchgesetzt, und Kunden können jede verfügbare Lagermenge kaufen.
    -   **Empfohlener Wert:** Legen Sie das präzise Enddatum und die Endzeit für Ihre Aktion oder Einschränkung fest.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass die Begrenzung am 7. August 2024 um 17:00 Uhr endet.
-   **Menge:**
    -   **Was diese Einstellung bewirkt:** Gibt die maximale Anzahl von Einheiten des ausgewählten Produkts an, die innerhalb des Bereichs "Datum von" und "Datum bis" gekauft werden können.
    -   **Auswirkung der Änderung dieser Einstellung:** Dies ist die tatsächlich durchgesetzte Begrenzung. Wenn ein Kunde versucht, mehr als diese Menge innerhalb des aktiven Datumsbereichs in seinen Warenkorb zu legen, wird er daran gehindert.
    -   **Empfohlener Wert:** Die spezifische maximale Menge, die Sie zulassen möchten.
    -   **Händlerszenario / Beispiel:** Sie möchten Käufe auf 5 Einheiten pro Kunde während des angegebenen Zeitraums begrenzen. Sie würden hier "5" eingeben.
-   **Aktiv (Ein/Aus-Schalter):**
    -   **Was diese Einstellung bewirkt:** Schaltet den aktiven Status dieser spezifischen Mengenbegrenzungsregel um.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Ein:* Die Regel ist aktiv und setzt die Mengenbegrenzung während ihres angegebenen Datumsbereichs durch.
        -   *Aus:* Die Regel ist inaktiv und setzt keine Mengenbegrenzung durch, auch wenn ihr Datumsbereich aktuell ist. Dies ist nützlich, um eine Regel vorübergehend zu pausieren, ohne sie zu löschen.
    -   **Empfohlener Wert:** "Ein" für aktive Regeln, "Aus" für Regeln, die Sie vorübergehend deaktivieren möchten.
    -   **Händlerszenario / Beispiel:** Sie haben eine Begrenzung für einen Black Friday Sale eingerichtet, entscheiden sich aber, ihn zu verschieben. Anstatt die Regel zu löschen, können Sie sie auf "Aus" stellen und dann auf "Ein", wenn Sie bereit sind.
-   **Speichern-Schaltfläche:**
    -   **Was diese Einstellung bewirkt:** Speichert alle Änderungen, die Sie an der Mengenbegrenzungsregel vorgenommen haben.
    -   **Auswirkung der Änderung dieser Einstellung:** Wendet die neue oder aktualisierte Regel auf die Produktmengenbegrenzung Ihres Shops an.

**Auswirkung von Änderungen:**
-   **Hinzufügen einer neuen Regel:** Eine neue Mengenbegrenzung wird erstellt und wird aktiv (wenn auf "Ein" gestellt) während ihres angegebenen Datumsbereichs, wodurch Käufe des ausgewählten Produkts eingeschränkt werden.
-   **Ändern einer bestehenden Regel:** Die Änderungen (z.B. Produkt, Daten, Menge, aktiver Status) aktualisieren sofort, wie die Begrenzung durchgesetzt wird.
-   **Löschen einer Regel:** Die Mengenbegrenzung wird dauerhaft entfernt, und für dieses Produkt gelten für diesen Datumsbereich keine Einschränkungen mehr (es sei denn, es existieren andere Regeln).

**Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
1.  **Planen Sie Ihre Aktionen/Einschränkungen:** Bevor Sie die Einrichtung vornehmen, entscheiden Sie, welche Produkte Limits benötigen, wie hoch die maximalen Mengen sein sollen und die genauen Start-/Enddaten und -zeiten.
2.  **Navigieren Sie zu "Produktkaufmengenlimit nach Datum":** Gehen Sie zu **Katalog > Produktkaufmengenlimit nach Datum**.
3.  **Neue Regeln hinzufügen:** Klicken Sie für jedes Produkt, das Sie begrenzen möchten, auf "Neu hinzufügen". Füllen Sie die Felder Produkt, Datum von, Datum bis, Menge sorgfältig aus und stellen Sie sicher, dass "Aktiv" auf "Ein" steht.
4.  **Überprüfen und anpassen:** Überprüfen Sie regelmäßig Ihre Regelliste, um sicherzustellen, dass sie noch relevant und korrekt konfiguriert sind. Verwenden Sie den "Aktiv"-Schalter, um Regeln bei Bedarf vorübergehend zu deaktivieren.
5.  **Kundenfeedback überwachen:** Achten Sie auf Kundenanfragen bezüglich Mengenlimits, um sicherzustellen, dass die Regeln klar sind und wie beabsichtigt funktionieren.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht                                       | Einstellung / Option                     | Standard / Empfohlen | Zweck & Auswirkung
Das Modul "Maximale verfügbare Produktmenge zum Kauf nach Datum" von MyPresta.eu ist ein leistungsstarkes Werkzeug zur Steuerung der Produktverfügbarkeit. Es ermöglicht Ihnen, spezifische maximale Kaufmengen für ein Produkt innerhalb eines definierten Datums- und Zeitbereichs festzulegen. Dies ist entscheidend für die Verwaltung begrenzter Bestände, die Schaffung von Dringlichkeit bei Aktionen oder die Verwaltung spezieller Produktverfügbarkeiten.

## 3. Anforderungen & Kompatibilität
-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich. Diese sind üblich und in den meisten PrestaShop-kompatiblen Hosting-Umgebungen standardmäßig aktiviert.

## 4. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Dies ist der anfängliche Konfigurationsbildschirm, den Sie nach der Installation des Moduls oder durch Klicken auf "Konfigurieren" im Modul-Manager sehen.

-   **Was diese Einstellung bewirkt:** Diese Seite enthält typischerweise einen einfachen Schalter zum Aktivieren oder Deaktivieren der Gesamtfunktionalität des Moduls.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert:* Das Modul prüft und setzt die von Ihnen definierten Produktmengenlimits aktiv durch.
    -   *Wenn deaktiviert:* Das Modul ist inaktiv, und es werden keine Mengenlimits angewendet, unabhängig von den von Ihnen eingerichteten Regeln.
-   **Empfohlener Wert:** "JA" (Aktiviert), um sicherzustellen, dass das Modul aktiv ist und Ihre Mengenregeln durchsetzt.
-   **Händlerszenario / Beispiel:** Nach der Installation müssen Sie sicherstellen, dass diese Einstellung aktiviert ist, um die Funktionen des Moduls nutzen zu können. Wenn Sie jemals alle Mengenlimits vorübergehend aussetzen müssen (z.B. während eines Wartungsfensters der Website), können Sie dies hier deaktivieren.

### 4.2 Dedizierter Admin-Bildschirm: Produktkaufmengenlimit nach Datum (Back Office > Katalog > Produktkaufmengenlimit nach Datum)
Dies ist die zentrale Anlaufstelle zum Erstellen, Verwalten und Überprüfen all Ihrer datumsbasierten Produktmengenlimits.

**Bildschirmname & Menüpfad:**
Sie können diesen Bildschirm aufrufen, indem Sie im PrestaShop Back Office-Menü zu **Katalog > Produktkaufmengenlimit nach Datum** navigieren.

**Verfügbare Aktionen & Einstellungen:**
Dieser Bildschirm zeigt eine Liste aller bestehenden Mengenbegrenzungsregeln an. Von hier aus können Sie neue Regeln hinzufügen, bestehende bearbeiten oder löschen.

#### **Spalten der Auflistungstabelle:**
-   **ID:** Eine eindeutige interne Kennung für jede spezifische Mengenbegrenzungsregel. Nützlich für technische Referenzen.
-   **Produkt:** Der Name des Produkts, für das diese spezifische Regel gilt. Dies hilft Ihnen, schnell zu erkennen, welches Produkt begrenzt wird.
-   **Datum von:** Das genaue Datum und die Uhrzeit (z.B. "2024-08-01 09:00:00"), ab der diese Mengenbegrenzung durchgesetzt wird.
-   **Datum bis:** Das genaue Datum und die Uhrzeit (z.B. "2024-08-07 17:00:00"), zu der diese Mengenbegrenzung nicht mehr durchgesetzt wird.
-   **Menge:** Die maximale Anzahl von Einheiten des angegebenen Produkts, die ein Kunde innerhalb des Zeitraums "Datum von" und "Datum bis" kaufen kann.
-   **Aktiv:** Eine einfache "Ja" oder "Nein" Anzeige (oft ein Umschalter), die anzeigt, ob die Regel derzeit aktiviert ist.

#### **Hinzufügen / Bearbeiten einer Mengenbegrenzungsregel:**
Wenn Sie auf die Schaltfläche "Neu hinzufügen" klicken oder eine bestehende Regel bearbeiten, erscheint ein Formular mit den folgenden Feldern:

-   **Produktkaufmengenlimit nach Datum:** Dies ist der Titel des Formulars, der anzeigt, dass Sie ein neues Limit definieren oder ein bestehendes bearbeiten.
-   **ID Produkt:**
    -   **Was diese Einstellung bewirkt:** Dies ist ein Suchfeld, in das Sie den Namen oder die ID des Produkts eingeben, auf das Sie das Limit anwenden möchten. Während der Eingabe erscheinen Vorschläge, die es Ihnen ermöglichen, das richtige Produkt auszuwählen.
    -   **Auswirkung der Änderung dieser Einstellung:** Verknüpft diese Mengenbegrenzungsregel direkt mit einem bestimmten Produkt in Ihrem Katalog.
    -   **Empfohlener Wert:** Wählen Sie immer das genaue Produkt aus, das Sie begrenzen möchten.
    -   **Händlerszenario / Beispiel:** Sie haben ein Sonderangebot für "Bio-Kaffeebohnen". Sie würden "Bio-Kaffeebohnen" eingeben und es aus der Dropdown-Liste auswählen.
-   **Datum von:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, das genaue Kalenderdatum und die Uhrzeit auszuwählen, wann diese Mengenbeschränkung beginnen soll. Es enthält typischerweise einen Datumswähler und einen Zeitwähler.
    -   **Auswirkung der Änderung dieser Einstellung:** Das Modul beginnt erst ab diesem spezifischen Datum und dieser Uhrzeit, die Mengenbegrenzung für Käufe durchzusetzen.
    -   **Empfohlener Wert:** Legen Sie dies auf den genauen Beginn Ihres Aktionszeitraums oder den Zeitpunkt fest, an dem die Beschränkung in Kraft treten soll.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass ein Limit zu Beginn eines Geschäftstages beginnt, also stellen Sie es auf "2024-09-01 00:00:00" ein.
-   **Datum bis:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, das genaue Kalenderdatum und die Uhrzeit auszuwählen, wann diese Mengenbeschränkung enden soll. Ähnlich wie bei "Datum von" enthält es einen Datumswähler und einen Zeitwähler.
    -   **Auswirkung der Änderung dieser Einstellung:** Nach diesem spezifischen Datum und dieser Uhrzeit ist das in dieser Regel definierte Mengenlimit nicht mehr aktiv, und Kunden können jede verfügbare Lagermenge kaufen.
    -   **Empfohlener Wert:** Legen Sie dies auf das genaue Ende Ihres Aktionszeitraums oder den Zeitpunkt fest, an dem die Beschränkung aufgehoben werden soll.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass das Limit am Ende eines Geschäftstages endet, also stellen Sie es auf "2024-09-07 23:59:59" ein.
-   **Menge:**
    -   **Was diese Einstellung bewirkt:** Dies ist ein numerisches Eingabefeld, in dem Sie die maximale Anzahl von Einheiten des ausgewählten Produkts angeben, die ein einzelner Kunde innerhalb des definierten Bereichs "Datum von" und "Datum bis" kaufen kann.
    -   **Auswirkung der Änderung dieser Einstellung:** Dieser Wert ist der Kern der Beschränkung. Wenn ein Kunde versucht, mehr als diese Menge in seinen Warenkorb zu legen (oder bereits mehr in seinem Warenkorb hat) während des aktiven Zeitraums, greift das Modul ein.
    -   **Empfohlener Wert:** Die spezifische maximale Menge, die Sie zulassen möchten. Zum Beispiel "1" für ein Limit von einem pro Kunde oder "10" für ein Mengenkauflimit.
    -   **Händlerszenario / Beispiel:** Um eine faire Verteilung eines Artikels in limitierter Auflage zu gewährleisten, setzen Sie die Menge auf "2" pro Kunde.
-   **Aktiv (Ein/Aus-Schalter):**
    -   **Was diese Einstellung bewirkt:** Dies ist ein Umschalter (oft mit "Ein" und "Aus" beschriftet), der steuert, ob diese spezifische Mengenbegrenzungsregel derzeit aktiv ist und vom Modul durchgesetzt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Ein:* Die Regel ist aktiv und wendet ihr Mengenlimit während ihres angegebenen Datumsbereichs an.
        -   *Aus:* Die Regel ist inaktiv und wendet kein Mengenlimit an, auch wenn ihr Datumsbereich aktuell ist. Dies ist nützlich, um Regeln im Voraus vorzubereiten oder sie vorübergehend zu pausieren, ohne sie zu löschen.
    -   **Empfohlener Wert:** "Ein" für Regeln, die aktiv sein sollen, "Aus" für Regeln, die Sie vorbereiten oder vorübergehend ausgesetzt haben.
    -   **Händlerszenario / Beispiel:** Sie haben eine Regel für einen Feiertagsverkauf erstellt, aber der Feiertag ist noch einen Monat entfernt. Sie können sie auf "Aus" stellen, bis der Termin näher rückt, und sie dann auf "Ein" schalten, wenn Sie bereit sind.
-   **Speichern-Schaltfläche:**
    -   **Was diese Einstellung bewirkt:** Überträgt alle Änderungen, die Sie im Formular vorgenommen haben, in die Datenbank.
    -   **Auswirkung der Änderung dieser Einstellung:** Die neue oder aktualisierte Mengenbegrenzungsregel wird sofort auf die Produktmengenbegrenzung Ihres Shops angewendet.

**Auswirkung von Änderungen:**
-   **Hinzufügen einer neuen Regel:** Eine neue Beschränkung wird erstellt. Wenn sie als "Aktiv" markiert ist und innerhalb ihres Datumsbereichs liegt, beginnt sie sofort, Käufe für das angegebene Produkt zu begrenzen.
-   **Ändern einer bestehenden Regel:** Alle Änderungen am Produkt, den Daten, der Menge oder dem aktiven Status werden sofort in der Art und Weise widergespiegelt, wie das Modul Limits durchsetzt.
-   **Löschen einer Regel:** Das Mengenlimit wird dauerhaft entfernt, und das Produkt unterliegt für diesen Datumsbereich nicht mehr dieser spezifischen Beschränkung.

**Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
1.  **Produkte für Limits identifizieren:** Bestimmen Sie, welche Produkte Mengenbeschränkungen erfordern (z.B. Neuheiten, Sale-Artikel, Produkte mit hoher Nachfrage).
2.  **Parameter definieren:** Legen Sie für jedes Produkt die maximale Menge sowie die genauen Start- und Enddaten/-zeiten für die Beschränkung fest.
3.  **Regeln erstellen:** Navigieren Sie zu **Katalog > Produktkaufmengenlimit nach Datum** und klicken Sie auf "Neu hinzufügen". Füllen Sie alle Felder sorgfältig aus und stellen Sie sicher, dass die Daten und Zeiten korrekt sind. Setzen Sie "Aktiv" auf "Ein".
4.  **Überprüfen und testen:** Testen Sie nach dem Erstellen der Regeln diese in Ihrem Front Office (z.B. versuchen Sie, mehr als die zulässige Menge in Ihren Warenkorb zu legen), um sicherzustellen, dass sie wie erwartet funktionieren.
5.  **Überwachen und anpassen:** Behalten Sie Ihre Verkäufe und Ihren Lagerbestand im Auge. Wenn eine Aktion verlängert wird oder sich der Lagerbestand ändert, aktualisieren Sie die Felder "Datum bis" oder "Menge" Ihrer Regeln nach Bedarf. Verwenden Sie den "Aktiv"-Schalter, um Regeln bei geänderten Umständen vorübergehend zu deaktivieren, ohne sie zu löschen.

### 4.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht                                       | Einstellung / Option                     | Standard / Empfohlen | Zweck & Auswirkung
