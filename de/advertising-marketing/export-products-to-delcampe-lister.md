---
title: "Produkte nach Delcampe Lister exportieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produkte nach Delcampe Lister exportieren“ von MyPresta.eu."
sidebar:
  label: "Produkte nach Delcampe Lister exportieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Export products to Delcampe Lister auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/export-products-to-delcampe-lister.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/export-products-to-delcampe-lister/)
>
> ---


# Produkte nach Delcampe Lister exportieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die korrekte Funktion von PrestaShop erforderlich und sollten in den meisten Hosting-Umgebungen verfügbar sein.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Sie können diesen Bildschirm aufrufen, indem Sie zu **Module > Modul-Manager** navigieren und neben „Produkte nach Delcampe Lister exportieren“ auf „Konfigurieren“ klicken.

Dieser Bildschirm verwaltet hauptsächlich die allgemeinen Einstellungen für das Modul, einschließlich der Update-Prüfungen.

-   **MyPresta.eu Live-Update-Prüfung:**
    -   **Was diese Einstellung bewirkt:** Diese Option steuert, ob das Modul automatisch nach neuen Versionen und Updates von MyPresta.eu sucht.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul verbindet sich regelmäßig mit MyPresta.eu, um zu prüfen, ob eine neuere Version verfügbar ist. Dies hilft Ihnen, mit Fehlerbehebungen und neuen Funktionen auf dem neuesten Stand zu bleiben.
        -   *Wenn deaktiviert:* Das Modul sucht nicht automatisch nach Updates. Sie müssten manuell in Ihrem MyPresta.eu-Konto nach Updates suchen.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Wenn diese Option aktiviert ist, stellen Sie sicher, dass Sie immer die stabilste und funktionsreichste Version des Moduls verwenden, ohne daran denken zu müssen, manuell nach Updates zu suchen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Delcampe Produktverwaltung (Back Office > Katalog > Delcampe Produkte)

Dies ist der Hauptverwaltungsbildschirm für Ihre Delcampe-Produktexporte. Sie können ihn aufrufen, indem Sie im PrestaShop Back Office-Menü zu **Katalog > Delcampe Produkte** navigieren.

Dieser Bildschirm bietet eine Rasteransicht Ihrer Produkte und ermöglicht Ihnen die Verwaltung ihrer Exporteinstellungen für Delcampe. Sie können neue Produkte zur Exportliste hinzufügen, bestehende bearbeiten und die Exportdatei generieren.

**Verfügbare Aktionen & Einstellungen:**

-   **Produkttabelle:** Diese Tabelle zeigt alle Produkte an, die entweder bereits für den Delcampe-Export konfiguriert sind oder zur Konfiguration zur Verfügung stehen. Sie sehen Spalten wie Produkt-ID, Name und möglicherweise deren Delcampe-spezifische Einstellungen.
-   **Neues Produkt hinzufügen / Produkt bearbeiten:**
    -   Durch Klicken auf „Neu hinzufügen“ oder Bearbeiten eines bestehenden Produkts wird ein Formular geöffnet, in dem Sie spezifische Delcampe-Listungsparameter für dieses Produkt definieren können.
    -   **`category_id` (Delcampe Kategorie-ID):**
        -   **Was diese Einstellung bewirkt:** Dies ist die spezifische Kategorie-ID auf Delcampe, unter der Ihr Produkt gelistet wird. Delcampe hat eine eigene Kategorienstruktur, die von der von PrestaShop abweichen kann.
        -   **Auswirkung einer Änderung dieser Einstellung:** Falsche Kategorie-IDs führen dazu, dass Ihr Produkt im falschen Bereich auf Delcampe gelistet wird oder möglicherweise nicht gelistet werden kann.
        -   **Empfohlener Wert:** Die genaue numerische ID der Ziel-Delcampe-Kategorie.
        -   **Händlerszenario / Beispiel:** Wenn Sie eine seltene Briefmarke verkaufen, würden Sie die entsprechende „Briefmarken“-Kategorie-ID auf Delcampe finden und hier eingeben.
    -   **`title` (Delcampe Listungstitel):**
        -   **Was diese Einstellung bewirkt:** Der Titel, der für Ihr Produkt auf Delcampe angezeigt wird. Dieser kann vom PrestaShop-Produktnamen abweichen.
        -   **Auswirkung einer Änderung dieser Einstellung:** Ein überzeugender und keyword-reicher Titel kann die Sichtbarkeit auf Delcampe erheblich verbessern.
        -   **Empfohlener Wert:** Ein beschreibender, prägnanter Titel, optimiert für Delcampe-Suchen.
        -   **Händlerszenario / Beispiel:** Statt „Alte Briefmarke“ könnten Sie „Seltene französische Briefmarke von 1920 – unbenutzt – ausgezeichneter Zustand“ verwenden.
    -   **`description` (Delcampe Listungsbeschreibung):**
        -   **Was diese Einstellung bewirkt:** Die detaillierte Produktbeschreibung, die in Ihrer Delcampe-Listung angezeigt wird.
        -   **Auswirkung einer Änderung dieser Einstellung:** Eine gründliche Beschreibung mit allen relevanten Details hilft Käufern, fundierte Entscheidungen zu treffen und Vertrauen aufzubauen.
        -   **Empfohlener Wert:** Eine umfassende Beschreibung, die möglicherweise historischen Kontext, Zustand und Abmessungen enthält.
        -   **Händlerszenario / Beispiel:** Kopieren Sie Ihre PrestaShop-Beschreibung, aber erwägen Sie, Delcampe-spezifische Details oder Formatierungen hinzuzufügen.
    -   **`personal_reference` (Ihre interne Referenz):**
        -   **Was diese Einstellung bewirkt:** Ein optionales Feld für Ihre eigene interne Nachverfolgung oder Referenznummer für das Produkt auf Delcampe.
        -   **Auswirkung einer Änderung dieser Einstellung:** Hilft Ihnen, Delcampe-Verkäufe Ihrem internen Inventarsystem zuzuordnen.
        -   **Empfohlener Wert:** Ihre PrestaShop-Produktreferenz oder SKU.
        -   **Händlerszenario / Beispiel:** Die Verwendung Ihrer PrestaShop-SKU hier ermöglicht es Ihnen, das Produkt in Ihrem Shop schnell zu identifizieren, wenn eine Delcampe-Bestellung eingeht.
    -   **`currency` (Listungswährung):**
        -   **Was diese Einstellung bewirkt:** Die Währung, in der das Produkt auf Delcampe gelistet wird.
        -   **Auswirkung einer Änderung dieser Einstellung:** Muss mit einer von Delcampe unterstützten Währung übereinstimmen.
        -   **Empfohlener Wert:** Ihre primäre Verkaufswährung (z. B. EUR, USD).
        -   **Händlerszenario / Beispiel:** Wenn Sie hauptsächlich in Euro verkaufen, stellen Sie dies auf EUR ein.
    -   **`selling_type` (Delcampe Verkaufstyp):**
        -   **Was diese Einstellung bewirkt:** Definiert, wie das Produkt auf Delcampe verkauft wird (z. B. Auktion, Festpreis).
        -   **Auswirkung einer Änderung dieser Einstellung:** Bestimmt den Kaufprozess für Kunden auf Delcampe.
        -   **Empfohlener Wert:** Wählen Sie den Typ, der am besten zu Ihrem Produkt und Ihrer Verkaufsstrategie passt (z. B. „Festpreis“ für Standardartikel, „Auktion“ für seltene Artikel).
        -   **Händlerszenario / Beispiel:** Für ein gängiges Sammlerstück könnte „Festpreis“ geeignet sein. Für ein wirklich einzigartiges Stück könnte eine „Auktion“ höhere Gebote erzielen.
    -   **`price` (Startpreis / Festpreis):**
        -   **Was diese Einstellung bewirkt:** Der Anfangspreis für eine Auktion oder der Festpreis für einen Direktverkauf.
        -   **Auswirkung einer Änderung dieser Einstellung:** Wirkt sich direkt auf die Kosten für den Käufer aus.
        -   **Empfohlener Wert:** Ihr gewünschter Verkaufspreis.
        -   **Händlerszenario / Beispiel:** Für einen Festpreisartikel wäre dies Ihr Verkaufspreis. Für eine Auktion ist es das Mindestgebot.
    -   **`initial_quantity` (Verfügbare Menge):**
        -   **Was diese Einstellung bewirkt:** Die Anzahl der Einheiten dieses Produkts, die Sie auf Delcampe zur Verfügung stellen.
        -   **Auswirkung einer Änderung dieser Einstellung:** Bestimmt, wie viele Artikel ein Käufer kaufen kann.
        -   **Empfohlener Wert:** Ihr aktueller Lagerbestand für das Produkt.
        -   **Händlerszenario / Beispiel:** Wenn Sie 5 einer bestimmten Briefmarke haben, stellen Sie dies auf 5 ein.
    -   **`minimum_bid_step` (Auktions-Gebotsschritt):**
        -   **Was diese Einstellung bewirkt:** Für Auktionsangebote definiert dies den Mindestbetrag, um den ein Gebot erhöht werden muss.
        -   **Auswirkung einer Änderung dieser Einstellung:** Beeinflusst das Bietverhalten.
        -   **Empfohlener Wert:** Ein angemessener Schritt (z. B. 0,50, 1,00).
        -   **Händlerszenario / Beispiel:** Wenn auf 1,00 eingestellt, müsste ein Gebot von 10,00 das nächste Gebot mindestens 11,00 betragen.
    -   **`renew_duration` (Dauer der automatischen Verlängerung):**
        -   **Was diese Einstellung bewirkt:** Wenn aktiviert, gibt dies an, wie lange ein unverkaufter Artikel automatisch verlängert wird.
        -   **Auswirkung einer Änderung dieser Einstellung:** Hält Ihr Produkt ohne manuelles Eingreifen auf Delcampe gelistet.
        -   **Empfohlener Wert:** Eine Dauer, die zu Ihrem Verkaufszyklus passt (z. B. 7 Tage, 14 Tage).
        -   **Händlerszenario / Beispiel:** Wenn ein Artikel in 7 Tagen nicht verkauft wird, wird er automatisch für weitere 7 Tage erneut gelistet.
    -   **`renew_total_count` (Limit für automatische Verlängerung):**
        -   **Was diese Einstellung bewirkt:** Die maximale Anzahl, wie oft ein unverkaufter Artikel automatisch verlängert wird.
        -   **Auswirkung einer Änderung dieser Einstellung:** Verhindert die unbegrenzte erneute Listung unbeliebter Artikel.
        -   **Empfohlener Wert:** Ein angemessenes Limit (z. B. 3, 5).
        -   **Händlerszenario / Beispiel:** Wenn ein Artikel nach 3 Verlängerungen nicht verkauft wird, wird er von Delcampe entfernt.
    -   **`shipping_model` (Delcampe Versandmodell):**
        -   **Was diese Einstellung bewirkt:** Die Versandmethode oder das Modell, das Sie auf Delcampe verwenden. Dies muss Ihren vorkonfigurierten Versandeinstellungen auf Delcampe entsprechen.
        -   **Auswirkung einer Änderung dieser Einstellung:** Bestimmt, wie die Versandkosten berechnet und dem Käufer präsentiert werden.
        -   **Empfohlener Wert:** Die ID oder der Name Ihres bevorzugten Delcampe-Versandmodells.
        -   **Händlerszenario / Beispiel:** Wenn Sie ein „Standard International Shipping“-Modell auf Delcampe eingerichtet haben, würden Sie dessen Kennung hier eingeben.
    -   **`weight` (Produktgewicht):**
        -   **Was diese Einstellung bewirkt:** Das Gewicht des Produkts, das für die Versandkostenberechnung auf Delcampe verwendet wird.
        -   **Auswirkung einer Änderung dieser Einstellung:** Entscheidend für eine genaue Schätzung der Versandkosten.
        -   **Empfohlener Wert:** Das tatsächliche Gewicht des Produkts.
        -   **Händlerszenario / Beispiel:** Geben Sie „0.1“ für eine leichte Briefmarke ein.
    -   **`lister_sale_end_time` (Verkaufsendezeit):**
        -   **Was diese Einstellung bewirkt:** Die spezifische Tageszeit, zu der die Listung endet.
        -   **Auswirkung einer Änderung dieser Einstellung:** Ermöglicht Ihnen, das Ende Ihrer Listungen zu planen.
        -   **Empfohlener Wert:** Eine Zeit, zu der Ihr Zielpublikum am wahrscheinlichsten online ist (z. B. 20:00 Uhr).
        -   **Händlerszenario / Beispiel:** Das Beenden einer Auktion um 20 Uhr an einem Sonntag könnte mehr Last-Minute-Gebote anziehen.
    -   **`lister_sale_end_day` (Verkaufsende-Tag):**
        -   **Was diese Einstellung bewirkt:** Der spezifische Wochentag, an dem die Listung endet.
        -   **Auswirkung einer Änderung dieser Einstellung:** Ermöglicht Ihnen, das Ende Ihrer Listungen zu planen.
        -   **Empfohlener Wert:** Ein Tag, an dem Ihr Zielpublikum am wahrscheinlichsten online ist (z. B. Sonntag).
        -   **Händlerszenario / Beispiel:** Das Beenden einer Auktion an einem Sonntag könnte mehr Last-Minute-Gebote anziehen.
    -   **`option_last_minute_extension` (Last-Minute-Verlängerung):**
        -   **Was diese Einstellung bewirkt:** Wenn aktiviert, verlängert sich die Auktionsdauer, wenn in den letzten Minuten ein Gebot abgegeben wird.
        -   **Auswirkung einer Änderung dieser Einstellung:** Verhindert „Sniping“ und fördert höhere Gebote.
        -   **Empfohlener Wert:** JA (für Auktionen).
        -   **Händlerszenario / Beispiel:** Ein Gebot, das 30 Sekunden vor Auktionsende abgegeben wird, verlängert die Auktion um einige Minuten, um anderen die Möglichkeit zu geben, zu kontern.
    -   **`option_anonymous_buyer` (Anonymer Käufer):**
        -   **Was diese Einstellung bewirkt:** Verbirgt die Identität des Käufers vor anderen Bietern in einer Auktion.
        -   **Auswirkung einer Änderung dieser Einstellung:** Kann die Privatsphäre der Bieter erhöhen.
        -   **Empfohlener Wert:** NEIN (es sei denn, spezifische Datenschutzbedenken sind von größter Bedeutung).
        -   **Händlerszenario / Beispiel:** Wenn Sie die Privatsphäre des Käufers schützen möchten, aktivieren Sie diese Option.
    -   **`option_strong_title` (Starker Titel / Fettschrift-Titel):**
        -   **Was diese Einstellung bewirkt:** Macht Ihren Listungstitel auf Delcampe fett, wodurch seine Sichtbarkeit erhöht wird.
        -   **Auswirkung einer Änderung dieser Einstellung:** Ihre Listung sticht in den Suchergebnissen stärker hervor.
        -   **Empfohlener Wert:** JA.
        -   **Händlerszenario / Beispiel:** Ein fetter Titel hilft Ihrer seltenen Briefmarkenlistung, die Aufmerksamkeit von Sammlern zu erregen, die viele ähnliche Artikel durchsuchen.
    -   **`option_background_color` (Hintergrundfarbe):**
        -   **Was diese Einstellung bewirkt:** Legt eine benutzerdefinierte Hintergrundfarbe für Ihre Listung auf Delcampe fest.
        -   **Auswirkung einer Änderung dieser Einstellung:** Kann Ihre Listung optisch ansprechender machen oder zu Ihrer Marke passen.
        -   **Empfohlener Wert:** Leer lassen oder eine dezente Farbe verwenden.
        -   **Händlerszenario / Beispiel:** Ein hellblauer Hintergrund könnte Ihre Listung hervorheben, ohne abzulenken.
    -   **`option_border_color` (Rahmenfarbe):**
        -   **Was diese Einstellung bewirkt:** Legt eine benutzerdefinierte Rahmenfarbe für Ihre Listung auf Delcampe fest.
        -   **Auswirkung einer Änderung dieser Einstellung:** Kann Ihre Listung optisch ansprechender machen oder zu Ihrer Marke passen.
        -   **Empfohlener Wert:** Leer lassen oder eine dezente Farbe verwenden.
        -   **Händlerszenario / Beispiel:** Ein dünner, dunkler Rahmen kann Ihrer Listung ein professionelleres Aussehen verleihen.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1.  **Produkte für Delcampe identifizieren:** Entscheiden Sie, welche Ihrer PrestaShop-Produkte für den Delcampe-Marktplatz geeignet sind.
2.  **Produkte hinzufügen/bearbeiten:** Gehen Sie zu **Katalog > Delcampe Produkte**. Verwenden Sie die Schaltfläche „Neu hinzufügen“ oder bearbeiten Sie bestehende Einträge, um die Delcampe-spezifischen Einstellungen für jedes Produkt zu konfigurieren. Achten Sie besonders auf Delcampe-Kategorie-IDs, Preise und Verkaufstyp.
3.  **Export generieren:** Sobald Ihre Produkte konfiguriert sind, können Sie mit dem Modul die Exportdatei generieren. Diese Datei enthält alle notwendigen Daten in einem Format, das Delcampe Lister importieren kann.
4.  **In Delcampe Lister importieren:** Laden Sie die generierte Datei herunter und importieren Sie sie in Ihr Delcampe Lister-Tool.
5.  **Überwachen & Aktualisieren:** Behalten Sie Ihre Delcampe-Listungen im Auge und aktualisieren Sie die Produktkonfigurationen in PrestaShop bei Bedarf (z. B. für Preisänderungen, Lagerbestandsaktualisierungen).

#### 2.2.2 AdminDelcampeProductsController (delcampeproducts/controllers/admin/AdminDelcampeProducts.php)

Dieser Controller ist für die Verwaltung der Delcampe-Produktlistungen im PrestaShop-Backoffice verantwortlich. Er kümmert sich um die Anzeige der Produktliste sowie um das Erstellen, Bearbeiten und Löschen individueller Delcampe-Produktkonfigurationen.

#### 2.2.3 index.php (delcampeproducts/controllers/admin/index.php)

Diese Datei dient wahrscheinlich als Platzhalter oder einfache Weiterleitung innerhalb der Admin-Controller-Struktur, um sicherzustellen, dass der Admin-Bereich des Moduls ordnungsgemäß initialisiert oder geroutet wird. Sie enthält typischerweise keine direkten Konfigurationsoptionen für den Händler.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | MyPresta.eu Live-Update-Prüfung | JA | Steuert automatische Prüfungen auf Modul-Updates. |
| Delcampe Produktverwaltung | Delcampe Kategorie-ID (`category_id`) | (Spezifische Delcampe-ID) | Ordnet PrestaShop-Produkt einer Delcampe-Kategorie zu. |
| Delcampe Produktverwaltung | Delcampe Listungstitel (`title`) | (Benutzerdefiniert) | Auf Delcampe angezeigter Produkttitel. |
| Delcampe Produktverwaltung | Delcampe Listungsbeschreibung (`description`) | (Benutzerdefiniert) | Detaillierte Produktbeschreibung für Delcampe. |
| Delcampe Produktverwaltung | Ihre interne Referenz (`personal_reference`) | (PrestaShop SKU) | Interne Nachverfolgung Ihrer Produkte. |
| Delcampe Produktverwaltung | Listungswährung (`currency`) | (Ihre primäre Währung) | Währung für die Delcampe-Listung. |
| Delcampe Produktverwaltung | Delcampe Verkaufstyp (`selling_type`) | (Festpreis / Auktion) | Wie das Produkt auf Delcampe verkauft wird. |
| Delcampe Produktverwaltung | Startpreis / Festpreis (`price`) | (Ihr gewünschter Preis) | Preis für Direktverkauf oder Auktionsstart. |
| Delcampe Produktverwaltung | Verfügbare Menge (`initial_quantity`) | (Ihr Lagerbestand) | Anzahl der auf Delcampe verfügbaren Einheiten. |
| Delcampe Produktverwaltung | Auktions-Gebotsschritt (`minimum_bid_step`) | (z. B. 0,50, 1,00) | Mindestbetrag, um den Gebote erhöht werden müssen. |
| Delcampe Produktverwaltung | Dauer der automatischen Verlängerung (`renew_duration`) | (z. B. 7 Tage) | Wie lange ein unverkaufter Artikel verlängert wird. |
| Delcampe Produktverwaltung | Limit für automatische Verlängerung (`renew_total_count`) | (z. B. 3, 5) | Maximale Anzahl der automatischen Verlängerungen eines unverkaufen Artikels. |
| Delcampe Produktverwaltung | Delcampe Versandmodell (`shipping_model`) | (Delcampe Modell-ID/Name) | Auf Delcampe verwendete Versandmethode. |
| Delcampe Produktverwaltung | Produktgewicht (`weight`) | (Tatsächliches Produktgewicht) | Produktgewicht für Versandkostenberechnungen. |
| Delcampe Produktverwaltung | Verkaufsendezeit (`lister_sale_end_time`) | (z. B. 20:00) | Spezifische Tageszeit für das Ende der Listung. |
| Delcampe Produktverwaltung | Verkaufsende-Tag (`lister_sale_end_day`) | (z. B. Sonntag) | Spezifischer Wochentag für das Ende der Listung. |
| Delcampe Produktverwaltung | Last-Minute-Verlängerung (`option_last_minute_extension`) | JA (für Auktionen) | Verlängert Auktion, wenn Gebot in letzten Minuten abgegeben wird. |
| Delcampe Produktverwaltung | Anonymer Käufer (`option_anonymous_buyer`) | NEIN | Verbirgt Käuferidentität in Auktionen. |
| Delcampe Produktverwaltung | Starker Titel / Fettschrift-Titel (`option_strong_title`) | JA | Macht den Listungstitel auf Delcampe fett. |
| Delcampe Produktverwaltung | Hintergrundfarbe (`option_background_color`) | (Leer lassen oder dezent) | Benutzerdefinierte Hintergrundfarbe für die Listung. |
| Delcampe Produktverwaltung | Rahmenfarbe (`option_border_color`) | (Leer lassen oder dezent) | Benutzerdefinierte Rahmenfarbe für die Listung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Produkte werden nach dem Export nicht auf Delcampe angezeigt. Was sollte ich überprüfen?**
A:

1.  **Haben Sie den Import in Delcampe Lister abgeschlossen?** Dieses Modul *exportiert* nur die Daten. Sie müssen die generierte Datei immer noch herunterladen und in Ihr Delcampe Lister-Tool *importieren*.
2.  **Überprüfen Sie die Delcampe Kategorie-IDs:** Stellen Sie sicher, dass die `category_id`, die Sie für jedes Produkt eingegeben haben, korrekt ist und auf Delcampe existiert. Falsche IDs können zu Importfehlern führen.
3.  **Überprüfen Sie die Delcampe Lister-Fehler:** Wenn Sie die Datei in Delcampe Lister importieren, gibt es normalerweise Feedback oder Fehlermeldungen, wenn etwas schief gelaufen ist. Überprüfen Sie diese Nachrichten auf Hinweise.
4.  **Produktstatus:** Stellen Sie sicher, dass die Produkte in Ihrem PrestaShop-Shop aktiv und auf Lager sind, wenn Sie das Modul so konfiguriert haben, dass nur aktive/auf Lager befindliche Artikel exportiert werden.

**F: Wie gehe ich mit Produktaktualisierungen (Preisänderungen, Lagerbestandsänderungen) auf Delcampe um?**
A: Sie müssen die aktualisierten Produktdaten erneut exportieren und in Delcampe Lister importieren. Das Modul generiert eine neue Exportdatei basierend auf Ihren aktuellen PrestaShop-Produktdaten und den von Ihnen konfigurierten Delcampe-spezifischen Einstellungen. Delcampe Lister verarbeitet normalerweise Aktualisierungen bestehender Listungen, wenn Sie eine Datei mit übereinstimmenden Produktidentifikatoren importieren.

**F: Die Exportdatei scheint leer oder unvollständig zu sein.**
A:

1.  **Produktkonfiguration:** Überprüfen Sie nochmals, ob Sie tatsächlich Produkte für den Delcampe-Export unter **Katalog > Delcampe Produkte** konfiguriert haben. Wenn keine Produkte konfiguriert sind, ist der Export leer.
2.  **Moduleinstellungen:** Überprüfen Sie alle allgemeinen Moduleinstellungen (falls vorhanden), die Produkte filtern könnten, wie z. B. „nur aktive Produkte exportieren“ oder „nur Produkte auf Lager exportieren“.
3.  **PrestaShop-Cache:** Manchmal kann das Leeren Ihres PrestaShop-Caches (**Erweiterte Einstellungen > Leistung > Cache leeren**) unerwartetes Verhalten bei der Datengenerierung beheben.

**F: Mein benutzerdefiniertes Theme verursacht Anzeigeprobleme in der Back-Office-Konfiguration des Moduls.**
A: Die Back-Office-Oberfläche dieses Moduls verwendet Standard-PrestaShop-Komponenten, daher sollte sie im Allgemeinen kompatibel sein. Wenn Sie Styling-Probleme feststellen, handelt es sich wahrscheinlich um einen Konflikt mit den Back-Office-Overrides Ihres benutzerdefinierten Themes.

1.  **Auf Overrides prüfen:** Wenn Ihr Theme einen `admin`-Ordner mit Template-Overrides hat, benennen Sie ihn vorübergehend um, um zu sehen, ob das Problem behoben wird.
2.  **Theme-Entwickler kontaktieren:** Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren Theme-Entwickler, da dieser möglicherweise sein CSS anpassen muss, um Standard-Moduloberflächen zu berücksichtigen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Produkte nach Delcampe Lister exportieren“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Admin-Controller für seine Back-Office-Oberfläche und Datenverwaltung nutzt. Es stützt sich nicht stark auf Front-Office-Komponenten für die direkte Kundeninteraktion, verwendet aber Hooks, um sich in den PrestaShop-Lebenszyklus zu integrieren. Die Kernfunktionalität dreht sich um die Verwaltung produktspezifischer Delcampe-Exporteinstellungen und die Generierung eines Datenfeeds für das Delcampe Lister-Tool.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:

    -   `controllers/front/feed.php`
        -   **Klassenname & Elternklasse**: `DelcampeproductsFeedModuleFrontController` erweitert `ModuleFrontController`.
        -   **Verantwortlichkeit**: Dieser Controller ist wahrscheinlich für die Generierung des eigentlichen Delcampe-Produktfeeds (z. B. XML, CSV) verantwortlich, den der Händler herunterladen würde. Er würde die konfigurierten Produkte abfragen und deren Daten gemäß den Delcampe-Spezifikationen formatieren. Er reagiert auf eine spezifische Front-Office-Route, obwohl er für den Endbenutzer, der den Shop durchsucht, nicht direkt sichtbar ist.
    -   `controllers/front/index.php`
        -   **Klassenname & Elternklasse**: `DelcampeproductsIndexModuleFrontController` erweitert `ModuleFrontController`.
        -   **Verantwortlichkeit**: Dies könnte als Standard- oder Fallback-Front-Controller dienen, oder es könnte für eine einfache Weiterleitung verwendet werden. In vielen Modulen, wenn `feed.php die primäre Front-Office-Interaktion (Generierung des Feeds) übernimmt, könnte `index.php` minimal oder ungenutzt sein.
-   **Back-Office-Admin-Controller**:

    -   `controllers/admin/AdminDelcampeProducts.php`
        -   **Klassenname & Elternklasse**: `AdminDelcampeProductsController` erweitert `ModuleAdminController`.
        -   **Tab-Name und verwaltete Entität**: Dieser Controller verwaltet den Bereich „Delcampe Produkte“ unter dem Menü „Katalog“ im PrestaShop Back Office. Er ist für das Auflisten, Hinzufügen, Bearbeiten und Löschen der Delcampe-spezifischen Konfiguration für jedes Produkt verantwortlich. Er verwendet PrestaShops `HelperList` und `HelperForm`, um das Produktgitter und das detaillierte Konfigurationsformular anzuzeigen.
    -   `controllers/admin/index.php`
        -   **Klassenname & Elternklasse**: Keine vollständige Controller-Klasse, typischerweise eine einfache `index.php`-Datei, um das Auflisten von Verzeichnissen zu verhindern oder die Hauptmoduldatei für den Kontext einzubinden. Sie definiert keine eigenständige Admin-Controller-Klasse.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass das Modul seine benutzerdefinierten Produktexporteinstellungen direkt in der Tabelle `ps_configuration` speichert oder bestehende PrestaShop `ObjectModel`-Klassen (wie `Product`) dynamisch erweitert oder eine direktere Datenbankinteraktion innerhalb des Controllers verwendet. Angesichts der detaillierten Formularfelder ist es sehr wahrscheinlich, dass produktspezifische Delcampe-Einstellungen in `ps_configuration` mit Schlüsseln wie `dp_export_categories` oder direkt innerhalb der Logik des `AdminDelcampeProductsController` gespeichert werden.

### 4.4 JavaScript-Assets (`views/js/`)

-   `delcampeproducts/lib/js/admin/delcampeproducts.js`
    -   **Geltungsbereich**: Back-Office.
    -   **Details**: Dieses Skript wird im PrestaShop Back Office geladen, speziell für den `AdminDelcampeProducts`-Controller. Es verarbeitet wahrscheinlich:
        -   Dynamisches Formularverhalten (z. B. Anzeigen/Ausblenden von Feldern basierend auf `selling_type`).
        -   AJAX-Aufrufe zum Speichern von Einstellungen oder Generieren der Exportdatei.
        -   Eingabevalidierung oder Formatierung für Felder wie `category_id`, `price`, `weight`.
        -   Alle interaktiven Elemente innerhalb der Produktkonfigurationsformulare oder des Listengitters.
        -   Potenziell die Verwendung von jQuery für DOM-Manipulation und Ereignisbehandlung.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist keine benutzerdefinierten CSS-Dateien aus. Dies impliziert, dass das Modul vollständig auf die Standard-Back-Office-Stile von PrestaShop für seine Konfigurationsformulare und Listen angewiesen ist, um ein konsistentes Erscheinungsbild mit dem Rest des Admin-Panels zu gewährleisten. Entwickler, die die Admin-Oberfläche des Moduls gestalten möchten, müssten bestehende PrestaShop-CSS-Klassen ansprechen oder benutzerdefiniertes CSS über den Hook `actionAdminControllerSetMedia` injizieren.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, aber Module verwenden oft `displayAdminProductsExtra` oder ähnliches für Produktseiten-Tabs.
-   **Admin-Templates (`views/templates/admin/`)**:
    -   `delcampeproducts/script.tpl`
        -   **Geltungsbereich**: Back-Office.
        -   **Details**: Dieses Template wird wahrscheinlich verwendet, um JavaScript-Variablen oder Inline-Skripte auszugeben, die von `delcampeproducts.js` benötigt werden. Es könnte Konfigurationswerte von PHP an JavaScript übergeben oder globale JS-Objekte definieren. Es wird oft über den Hook `actionAdminControllerSetMedia` gerendert.
-   **Front-Office-Templates (`views/templates/front/`)**: Keine explizit aufgeführt, was mit der Hintergrund-Exportnatur des Moduls übereinstimmt.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Das Modul speichert seine Konfigurationseinstellungen wahrscheinlich in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `dp_export_categories`, `dp_remember_settings`, `dp_option_homepage_promotion`, `dp_lister_status`, `dp_lister_creation_date`, `dp_lister_sending_date`, `dp_llister_sending_date`, `dp_lister_edit_date`, `dp_export_format`, `dp_export_active`, `dp_export_instock`, `dp_export_identification`, `dp_export_category`, `dp_export_manufacturers_default`.
    -   Für produktspezifische Delcampe-Einstellungen (wie `category_id`, `title`, `price` usw.) werden diese, da keine benutzerdefinierte `ObjectModel` aufgeführt ist, wahrscheinlich entweder als serialisierte Daten in `ps_configuration` gespeichert (weniger ideal für pro-Produkt-Einstellungen) oder, wahrscheinlicher, der `AdminDelcampeProductsController` verwaltet direkt eine benutzerdefinierte Datenbanktabelle (z. B. `ps_delcampe_product_settings`), die im Dossier nicht explizit identifiziert wurde, aber ein Standardansatz für solch detaillierte pro-Produkt-Daten wäre. Wenn keine benutzerdefinierte Tabelle existiert, könnte es `Product::addFeature` oder `Product::addCustomization` auf nicht standardmäßige Weise verwenden oder Daten in `ps_product_lang` oder `ps_product_shop` durch Overrides speichern. **(Entwicklerhinweis: Datenbank auf `ps_delcampe_product_settings` oder ähnliche Tabelle bei der Installation untersuchen.)**
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Ermöglicht dem Modul, auf Produktänderungen zu reagieren (z. B. interne Delcampe-Exportdaten aktualisieren, ein Produkt für den Re-Export markieren). |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird und seine Medien (JS/CSS) gesetzt werden. | Wird verwendet, um das benutzerdefinierte JavaScript des Moduls (`delcampeproducts.js`) und potenziell Inline-Skripte (`script.tpl`) in die Back-Office-Seiten einzufügen, insbesondere für den `AdminDelcampeProducts`-Controller. |
| `displayAdminProductsExtra` | (Implizit, oft für Produkt-Tabs verwendet) | Wenn das Modul einen Tab zur Produktbearbeitungsseite für Delcampe-Einstellungen hinzufügt, würde dieser Hook verwendet. (Nicht explizit als Hook aufgeführt, aber üblich für solche Funktionen). |
| `displayBackOfficeHeader` | Im Header jeder Back-Office-Seite. | Kann für globale JS/CSS auf Admin-Seite oder zum Anzeigen von Benachrichtigungen verwendet werden. |
| `moduleRoutes` | Während der Routengenerierung für das Modul. | Wird verwendet, um benutzerdefinierte Front-Office-URLs für Controller wie `feed.php` zu definieren. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und umfassenden Support für das Modul „Produkte nach Delcampe Lister exportieren“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser engagiertes Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
