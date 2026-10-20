---
title: "Zalando Fashion Connector Importer (FCI) - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Zalando Fashion Connector Importer (FCI) von MyPresta.eu."
sidebar:
  label: "Zalando Fashion Connector Importer (FCI) - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Zalando Fashion Connector Importer (FCI) auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/zalando-fashion-connector-importer-fci.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/zalando-fashion-connector-importer-fci/)
>
> ---


# Zalando Fashion Connector Importer (FCI)

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die meisten PrestaShop-Module erforderlich und in jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Zalando Fashion Connector Importer (FCI))

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die grundlegenden Parameter für Ihren Zalando-Feed einrichten.

-   **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, die Kerninformationen zu definieren, die in Ihrem Zalando-Produkt-Feed enthalten sein werden.
-   **Auswirkung der Änderung dieser Einstellung:** Die hier festgelegten Werte beeinflussen direkt die Daten, die Zalando über Ihre Produkte erhält, und wirken sich darauf aus, wie diese auf ihrer Plattform angezeigt und verwaltet werden.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| :------------------- | :-------------------------- | :---------------------------------------- | :---------------- | :------------------------ |
| **Shop** | Gibt den Namen Ihres Shops an, wie er auf Zalando erscheinen soll. Dies hilft Zalando, Ihr spezifisches Einzelhandelsgeschäft zu identifizieren. | *Wenn festgelegt:* Ihr angegebener Shop-Name wird in den Produkt-Feed aufgenommen. *Wenn leer gelassen:* Zalando könnte einen Standard-Identifikator verwenden oder den Feed ablehnen, wenn ein Shop-Name obligatorisch ist. | Ihr tatsächlicher Shop-Name (z.B. „Meine Boutique Mode“) | Wenn Sie mehrere physische Geschäfte oder Marken haben, hilft dies Zalando, Ihr Inventar zu unterscheiden. |
| **EAN (European Article Number)** | Bestimmt, ob die EAN (Barcode) Ihrer Produkte in den Feed aufgenommen werden soll. EANs sind entscheidend für die Produktidentifikation. | *Wenn aktiviert:* EANs werden Teil des Feeds sein, wodurch Zalando Ihre Produkte genau zuordnen kann. *Wenn deaktiviert:* Produkte könnten nicht korrekt identifiziert oder von Zalando abgelehnt werden, wenn EAN ein Pflichtfeld ist. | JA | Wesentlich für die meisten Produktlisten, insbesondere in der Mode, um eine eindeutige Identifikation zu gewährleisten. |
| **Preis** | Steuert, ob der Verkaufspreis des Produkts in den Feed aufgenommen wird. | *Wenn aktiviert:* Der aktuelle Verkaufspreis aus Ihrem PrestaShop-Shop wird an Zalando gesendet. *Wenn deaktiviert:* Zalando erhält keine Preisaktualisierungen, was möglicherweise zu veralteten Preisen auf ihrer Plattform führt. | JA | Entscheidend, um sicherzustellen, dass Kunden den korrekten Preis auf Zalando sehen. |
| **UVP (Unverbindliche Preisempfehlung)** | Bestimmt, ob der ursprüngliche Verkaufspreis (oft der durchgestrichene Preis für Rabatte) enthalten ist. | *Wenn aktiviert:* Der ursprüngliche Preis wird gesendet, wodurch Zalando Einsparungen oder Werbeaktionen anzeigen kann. *Wenn deaktiviert:* Nur der aktuelle Verkaufspreis wird gesendet, wodurch Rabattinformationen möglicherweise verborgen bleiben. | JA (wenn Sie UVP für Werbeaktionen verwenden) | Wenn Sie Verkäufe durchführen, hilft die Angabe des UVP, den Rabatt für Kunden auf Zalando hervorzuheben. |
| **Menge** | Gibt an, ob die aktuelle Lagerbestandsmenge Ihrer Produkte in den Feed aufgenommen wird. | *Wenn aktiviert:* Ihre Produktlagerbestände werden auf Zalando aktualisiert, wodurch Überverkäufe verhindert werden. *Wenn deaktiviert:* Zalando erhält keine Bestandsaktualisierungen, was zu potenziellen Diskrepanzen und Kundenunzufriedenheit führen kann, wenn ein Artikel nicht vorrätig ist. | JA | Absolut entscheidend, um den Verkauf von Produkten zu vermeiden, die Sie nicht mehr verfügbar haben. |
| **Produktname** | Steuert, ob der Produktname in den Feed aufgenommen wird. | *Wenn aktiviert:* Der Produktname aus Ihrem PrestaShop-Shop wird an Zalando gesendet. *Wenn deaktiviert:* Produkte könnten ohne Namen gelistet oder abgelehnt werden, wenn dies ein Pflichtfeld ist. | JA | Wesentlich für Kunden, um Ihre Produkte auf Zalando zu identifizieren und zu suchen. |
| **Client ID (zf\_client)** | Ihre eindeutige Client-ID, die von Zalando für den API-Zugriff bereitgestellt wird. | *Wenn korrekt eingegeben:* Ermöglicht dem Modul die Authentifizierung bei den Systemen von Zalando. *Wenn falsch oder leer:* Die Feed-Generierung und -Aktualisierungen schlagen fehl. | Die von Zalando bereitgestellte ID | Sie müssen diese von Ihrem Zalando Connected Retail Account Manager erhalten. |
| **API Key (zf\_api)** | Ihr eindeutiger API-Schlüssel, der von Zalando für eine sichere Kommunikation bereitgestellt wird. | *Wenn korrekt eingegeben:* Ermöglicht eine sichere Datenübertragung zwischen Ihrem Shop und Zalando. *Wenn falsch oder leer:* Die Feed-Generierung und -Aktualisierungen schlagen aufgrund von Authentifizierungsproblemen fehl. | Der von Zalando bereitgestellte Schlüssel | Dies ist ein Sicherheitsmerkmal; halten Sie es vertraulich und erhalten Sie es von Zalando. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Produkt-Export-Konfiguration (Back Office > Zalando FCI > Produkte exportieren)

Dieser Bildschirm, der über das PrestaShop Back Office-Menü zugänglich ist, ist der Ort, an dem Sie die detaillierten Parameter für die Generierung Ihres Produkt-Feeds für Zalando definieren. Er ermöglicht eine Feinabstimmung, welche Daten enthalten sind und wie sie formatiert werden.

-   **Bildschirmname & Menüpfad:** **Zalando FCI > Produkte exportieren** (Dies wird als neuer Menüpunkt in Ihrer PrestaShop Back Office-Navigation erscheinen).
-   **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm präsentiert ein Formular mit zahlreichen Optionen zur Anpassung Ihres Produktexports. Sie finden Felder zur Auswahl von Shops, Währungen, Produktattributen und Filteroptionen.
-   **Auswirkung von Änderungen:** Änderungen hier wirken sich direkt auf den Inhalt und die Struktur der generierten Produkt-Feed-Datei aus. Falsche Einstellungen können dazu führen, dass Zalando Ihren Feed ablehnt oder falsche Produktinformationen anzeigt.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Konfigurieren Sie zunächst alle Einstellungen sorgfältig gemäß den Spezifikationen von Zalando und den Anforderungen Ihres Shops.
    2.  Generieren Sie einen Test-Feed und validieren Sie ihn (falls möglich) mit Zalando, um sicherzustellen, dass alle Daten korrekt sind.
    3.  Nach der Konfiguration verwenden Sie diesen Bildschirm hauptsächlich, um den Feed bei Bedarf manuell zu generieren, oder Sie richten einen Cron-Job (eine geplante Aufgabe) ein, um die Feed-Generierung basierend auf diesen Einstellungen zu automatisieren.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| :------------------- | :-------------------------- | :---------------------------------------- | :---------------- | :------------------------ |
| **Einstellungen merken (zf\_remember\_settings)** | Wenn aktiviert, merkt sich das Modul Ihre zuletzt gewählten Export-Einstellungen zur Vereinfachung. | *Wenn aktiviert:* Ihre Auswahlen auf dieser Seite bleiben für zukünftige Exporte erhalten. *Wenn deaktiviert:* Die Einstellungen werden jedes Mal, wenn Sie die Seite besuchen, auf die Standardwerte zurückgesetzt. | JA | Spart Zeit, wenn Sie häufig Feeds mit denselben Parametern generieren. |
| **Export-Dateiformat (zf\_export\_file\_format)** | Wählt das Ausgabeformat für die Produkt-Feed-Datei (z.B. CSV, XML). | *Wenn festgelegt:* Die generierte Datei wird im gewählten Format vorliegen. *Wenn falsch:* Zalando kann die Datei möglicherweise nicht verarbeiten. | Überprüfen Sie die Anforderungen von Zalando (normalerweise CSV oder XML) | Zalando gibt das erforderliche Format für ihr Importsystem an. |
| **Export-Typ (zf\_export\_type)** | Definiert, welche Art von Produkten exportiert werden soll (z.B. alle Produkte, nur aktive, nur bestimmte Kategorien). | *Wenn festgelegt:* Nur Produkte, die den Kriterien entsprechen, werden aufgenommen. *Wenn falsch:* Sie könnten zu viele oder zu wenige Produkte exportieren. | Alle aktiven Produkte, oder gemäß Zalando-Onboarding | Wenn Sie nur eine Untermenge Ihres Katalogs auf Zalando listen möchten. |
| **Shop (zf\_export\_store)** | Ermöglicht die Auswahl, aus welchem PrestaShop-Shop (in einer Multi-Shop-Einrichtung) Produkte exportiert werden sollen. | *Wenn ausgewählt:* Produkte aus diesem spezifischen Shop werden exportiert. *Wenn falsch:* Produkte aus dem falschen Shop könnten enthalten sein. | Ihr primärer Shop, oder der relevante Shop für Zalando | Für Händler, die mehrere unterschiedliche Shops von einer PrestaShop-Installation aus betreiben. |
| **Trennzeichen (zf\_export\_delimiter)** | Gibt das Zeichen an, das zum Trennen von Datenfeldern in der Exportdatei verwendet wird (z.B. Komma, Semikolon). | *Wenn festgelegt:* Das gewählte Trennzeichen wird verwendet. *Wenn falsch:* Die Datei ist für Zalando unlesbar. | Überprüfen Sie die Anforderungen von Zalando (oft Komma oder Semikolon) | Entscheidend für CSV-Dateien, um sicherzustellen, dass Daten korrekt geparst werden. |
| **Währung (zf\_export\_currency)** | Wählt die Währung für Produktpreise in der Exportdatei. | *Wenn ausgewählt:* Preise werden in diese Währung umgerechnet oder angezeigt. *Wenn falsch:* Zalando könnte falsche Preise anzeigen oder den Feed ablehnen. | Die von Zalando geforderte Währung (z.B. EUR) | Wenn Ihr Shop in mehreren Währungen betrieben wird, stellen Sie sicher, dass Sie in der von Zalando erwarteten Währung exportieren. |
| **Produktnamenformat (zf\_export\_product\_name\_format)** | Definiert, wie Produktnamen formatiert werden (z.B. Hersteller, Attribute einschließen). | *Wenn festgelegt:* Produktnamen folgen diesem Format. *Wenn falsch:* Namen könnten unklar sein oder nicht den Richtlinien von Zalando entsprechen. | Gemäß den Empfehlungen von Zalando für Klarheit | Um sicherzustellen, dass Produktnamen auf Zalando informativ und konsistent sind. |
| **Steuer einschließen (zf\_export\_tax)** | Bestimmt, ob Produktpreise im Feed die Steuer enthalten sollen. | *Wenn aktiviert:* Preise sind inklusive Steuer. *Wenn deaktiviert:* Preise sind exklusive Steuer. | Überprüfen Sie die Anforderungen von Zalando für die Preisanzeige | Wichtig für die Steuerkonformität und korrekte Preisanzeige auf Zalando. |
| **Länderpreise exportieren (zf\_export\_country\_prices)** | Wenn aktiviert, werden Preise, die für verschiedene Länder spezifisch sind, eingeschlossen (sofern in PrestaShop konfiguriert). | *Wenn aktiviert:* Länderspezifische Preise werden exportiert. *Wenn deaktiviert:* Nur Standardpreise werden exportiert. | JA (wenn Sie länderspezifische Preise haben) | Für internationale Verkäufer mit unterschiedlichen Preisstrategien pro Region. |
| **Standardland (PS\_COUNTRY\_DEFAULT)** | Das Standardland für Ihren PrestaShop-Shop, das als Fallback für einige Einstellungen verwendet wird. | *Wenn festgelegt:* Bietet ein Basisland für Preis- und Steuerberechnungen. | Das primäre Land Ihres Shops | Gewährleistet ein konsistentes Standardverhalten für internationale Einstellungen. |
| **Nur aktive Produkte exportieren (zf\_export\_active)** | Wenn aktiviert, werden nur Produkte exportiert, die in PrestaShop als „aktiv“ markiert sind. | *Wenn aktiviert:* Nur verfügbare Produkte werden gesendet. *Wenn deaktiviert:* Inaktive Produkte könnten enthalten sein, was zu Fehlern auf Zalando führt. | JA | Verhindert das Auflisten von Produkten, die Sie nicht verkaufen möchten oder die nicht mehr verfügbar sind. |
| **Hersteller exportieren (zf\_export\_manufacturers)** | Wenn aktiviert, werden Herstellerinformationen in den Feed aufgenommen. | *Wenn aktiviert:* Herstellerdaten werden gesendet. *Wenn deaktiviert:* Herstellerdaten werden weggelassen. | JA | Nützlich für Kunden, um auf Zalando nach Marke zu filtern. |
| **Lieferanten exportieren (zf\_export\_suppliers)** | Wenn aktiviert, werden Lieferanteninformationen in den Feed aufgenommen. | *Wenn aktiviert:* Lieferantendaten werden gesendet. *Wenn deaktiviert:* Lieferantendaten werden weggelassen. | NEIN (es sei denn, von Zalando gefordert) | Weniger üblich für kundenorientierte Feeds, mehr für die interne Nachverfolgung. |
| **Kategorie exportieren (zf\_export\_category)** | Wenn aktiviert, werden Produktkategorieinformationen aufgenommen. | *Wenn aktiviert:* Kategoriedaten werden gesendet. *Wenn deaktiviert:* Kategoriedaten werden weggelassen. | JA | Hilft Zalando, Ihre Produkte korrekt zu kategorisieren und unterstützt die Kundennavigation. |
| **Nur vorrätige Produkte exportieren (zf\_export\_instock)** | Wenn aktiviert, werden nur Produkte mit verfügbarem Lagerbestand exportiert. | *Wenn aktiviert:* Nur Produkte, die Sie erfüllen können, werden gesendet. *Wenn deaktiviert:* Ausverkaufte Produkte könnten enthalten sein, was zu Überverkaufsproblemen führt. | JA | Entscheidend, um Kundenenttäuschungen aufgrund nicht verfügbarer Artikel zu vermeiden. |
| **Preis-Maximalwert ausschließen (zf\_export\_exclude\_price\_max)** | Wenn aktiviert, werden Produkte über einem bestimmten Preisschwellenwert aus dem Feed ausgeschlossen. | *Wenn aktiviert:* Produkte, die den Maximalpreis überschreiten, werden nicht exportiert. *Wenn deaktiviert:* Alle Produkte, unabhängig vom Preis, werden exportiert. | NEIN (es sei denn, Sie haben bestimmte hochwertige Artikel auszuschließen) | Nützlich, wenn Zalando Preislimits hat oder wenn Sie nur bestimmte Preisbereiche auf ihrer Plattform verkaufen möchten. |
| **Preis-Maximalwert (zf\_export\_exclude\_price\_max\_v)** | Der maximale Preiswert für die Einstellung „Preis-Maximalwert ausschließen“. | *Wenn festgelegt:* Definiert die obere Preisgrenze für exportierte Produkte. | Leer lassen, wenn nicht nach Maximalpreis ausgeschlossen wird | Wenn Sie nur Artikel unter 500 € auf Zalando verkaufen möchten, setzen Sie diesen Wert auf 500. |

#### 2.2.2 Admin Index-Bildschirm (Back Office > Zalando FCI > Index)

Dieser Bildschirm dient wahrscheinlich als Startseite oder einfache Verwaltungsansicht für das Modul, die möglicherweise Informationen anzeigt oder schnelle Links bereitstellt.

-   **Bildschirmname & Menüpfad:** **Zalando FCI > Index** (Dies wird als neuer Menüpunkt in Ihrer PrestaShop Back Office-Navigation erscheinen, oft der erste Punkt unter dem Hauptmenü des Moduls).
-   **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt typischerweise ein Raster oder ein einfaches Informationspanel an. Er könnte das Datum des letzten Exports, einen Link zur Generierung des Feeds oder den allgemeinen Modulstatus anzeigen. Es ist normalerweise kein Bildschirm für detaillierte Konfiguration, sondern eher für einen Überblick oder schnelle Aktionen.
-   **Auswirkung von Änderungen:** Es gibt normalerweise keine direkten „Einstellungen“, die auf diesem Bildschirm geändert werden können. Sein Zweck ist eher informativ oder navigierend.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie dies als schnellen Einstiegspunkt zum Modul, um den Status Ihres letzten Exports zu überprüfen oder zum Bildschirm „Produkte exportieren“ für detaillierte Konfiguration und Feed-Generierung zu navigieren.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------------- | :------------------- | :------------------- | :----------------- |
| **Modulkonfiguration** | Shop | Ihr Shop-Name | Identifiziert Ihren Shop auf Zalando. |
| **Modulkonfiguration** | EAN | JA | Wesentlich für die Produktidentifikation. |
| **Modulkonfiguration** | Preis | JA | Stellt korrekte Preise auf Zalando sicher. |
| **Modulkonfiguration** | UVP | JA (falls verwendet) | Zeigt den Originalpreis für Werbeaktionen an. |
| **Modulkonfiguration** | Menge | JA | Entscheidend für genaue Lagerbestände, verhindert Überverkäufe. |
| **Modulkonfiguration** | Produktname | JA | Wesentlich für Produktidentifikation und Suche. |
| **Modulkonfiguration** | Client ID (zf\_client) | Von Zalando bereitgestellt | Authentifiziert sich bei der Zalando API. |
| **Modulkonfiguration** | API Key (zf\_api) | Von Zalando bereitgestellt | Sichert die Kommunikation mit der Zalando API. |
| **Produkte exportieren** | Einstellungen merken | JA | Spart Zeit durch Beibehalten der Exportauswahlen. |
| **Produkte exportieren** | Export-Dateiformat | Überprüfen Sie die Anforderungen von Zalando | Definiert den Ausgabedateityp. |
| **Produkte exportieren** | Export-Typ | Alle aktiven Produkte | Steuert, welche Produkte enthalten sind. |
| **Produkte exportieren** | Shop | Ihr primärer Shop | Wählt Produkte aus einem bestimmten Shop (Multi-Shop). |
| **Produkte exportieren** | Trennzeichen | Überprüfen Sie die Anforderungen von Zalando | Trennt Felder in CSV-Dateien. |
| **Produkte exportieren** | Währung | Von Zalando gefordert (z.B. EUR) | Legt die Währung für exportierte Preise fest. |
| **Produkte exportieren** | Produktnamenformat | Gemäß den Empfehlungen von Zalando | Formatiert Produktnamen für Klarheit. |
| **Produkte exportieren** | Steuer einschließen | Überprüfen Sie die Anforderungen von Zalando | Bestimmt, ob Preise steuerinklusiv sind. |
| **Produkte exportieren** | Länderpreise exportieren | JA (falls zutreffend) | Enthält länderspezifische Preise. |
| **Produkte exportieren** | Standardland | Das primäre Land Ihres Shops | Fallback für länderspezifische Einstellungen. |
| **Produkte exportieren** | Nur aktive Produkte exportieren | JA | Verhindert das Auflisten inaktiver Produkte. |
| **Produkte exportieren** | Hersteller exportieren | JA | Enthält Markeninformationen. |
| **Produkte exportieren** | Lieferanten exportieren | NEIN (es sei denn, erforderlich) | Enthält Lieferanteninformationen. |
| **Produkte exportieren** | Kategorie exportieren | JA | Hilft Zalando, Produkte zu kategorisieren. |
| **Produkte exportieren** | Nur vorrätige Produkte exportieren | JA | Verhindert das Auflisten nicht vorrätiger Artikel. |
| **Produkte exportieren** | Preis-Maximalwert ausschließen | NEIN (es sei denn, benötigt) | Schließt Produkte über einem festgelegten Preis aus. |
| **Produkte exportieren** | Preis-Maximalwert | Leer lassen, wenn nicht ausgeschlossen wird | Legt den Maximalpreis für den Ausschluss fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Produkte erscheinen nicht auf Zalando, oder der Feed wird abgelehnt. Was sollte ich zuerst überprüfen?**
A1:

-   **Modulkonfiguration überprüfen:** Gehen Sie zu **Module > Modul-Manager > Zalando Fashion Connector Importer (FCI) > Konfigurieren**. Stellen Sie sicher, dass Ihre „Client ID“ und Ihr „API Key“ korrekt eingegeben sind, wie von Zalando bereitgestellt.
-   **Exporteinstellungen überprüfen:** Navigieren Sie zu **Zalando FCI > Produkte exportieren**. Überprüfen Sie, ob das „Export-Dateiformat“ und das „Trennzeichen“ den genauen Anforderungen von Zalando entsprechen. Stellen Sie außerdem sicher, dass „Nur aktive Produkte exportieren“ und „Nur vorrätige Produkte exportieren“ aktiviert sind, wenn Sie nur verfügbare Artikel senden möchten.
-   **Produktdaten validieren:** Stellen Sie sicher, dass Ihre Produkte in PrestaShop gültige EANs, Namen, Preise und Lagerbestandsmengen haben. Fehlende oder ungültige Daten sind ein häufiger Grund für Ablehnungen.
-   **Cache leeren:** Manchmal können alte Daten bestehen bleiben. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).

**F2: Die Preise oder Lagerbestände auf Zalando werden nicht korrekt aktualisiert.**
A2:

-   **Exportfrequenz überprüfen:** Wie oft generieren Sie den Feed? Wenn Sie dies manuell tun, müssen Sie es regelmäßig tun. Wenn Sie einen Cron-Job eingerichtet haben, stellen Sie sicher, dass er mit der gewünschten Frequenz (z.B. stündlich) ausgeführt wird.
-   **Modulkonfiguration:** Überprüfen Sie nochmals, ob „Preis“ und „Menge“ auf dem Hauptkonfigurationsbildschirm des Moduls aktiviert sind.
-   **Verarbeitungszeit von Zalando:** Denken Sie daran, dass selbst nachdem Sie den Feed generiert und gesendet haben, die Systeme von Zalando Zeit benötigen, um die Daten zu verarbeiten und zu aktualisieren. Dies kann je nach Auslastung manchmal einige Minuten bis mehrere Stunden dauern.

**F3: Ich habe ein benutzerdefiniertes Theme, und die Admin-Oberfläche des Moduls sieht etwas seltsam aus.**
A3:

-   Die Admin-Oberfläche des Moduls verwendet Standard-PrestaShop-Styling, aber geringfügige visuelle Inkonsistenzen können bei stark angepassten Back-Office-Themes auftreten. Dies beeinträchtigt normalerweise nicht die Funktionalität.
-   Wenn es ein erhebliches Problem ist, wenden Sie sich an den MyPresta.eu-Support. Für kleinere Anpassungen kann ein Webentwickler oft die Datei `zalandofci/views/admin-theme.css` anpassen oder benutzerdefiniertes CSS zu Ihrem PrestaShop Back Office hinzufügen.

**F4: Wie richte ich einen Cron-Job ein, um die Feed-Generierung zu automatisieren?**
A4:

-   Die genauen Schritte hängen von Ihrem Hosting-Anbieter ab. Sie finden normalerweise einen Abschnitt „Cron-Jobs“ oder „Geplante Aufgaben“ in Ihrem Hosting-Kontrollpanel (z.B. cPanel, Plesk).
-   Sie benötigen die URL, die die Feed-Generierung auslöst. Diese URL wird normalerweise auf der Konfigurationsseite „Produkte exportieren“ des Moduls angezeigt, nachdem Sie Ihre Einstellungen gespeichert haben, oder sie kann über den Front-Controller-Pfad konstruiert werden (z.B. `ihrshop.com/module/zalandofci/feed`).
-   Stellen Sie den Cron-Job so ein, dass diese URL in Ihrem gewünschten Intervall ausgeführt wird (z.B. `wget -q -O /dev/null "http://ihrshop.com/module/zalandofci/feed"`). Wenn Sie unsicher sind, konsultieren Sie die Dokumentation oder den Support Ihres Hosting-Anbieters.

**F5: Das Modul ist installiert, aber ich sehe „Zalando FCI“ nicht in meinem Back Office-Menü.**
A5:

-   **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und leeren Sie den Cache. Manchmal wird das Menü nach der Modulinstallation nicht sofort aktualisiert.
-   **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und suchen Sie nach „Zalando Fashion Connector Importer (FCI)“. Stellen Sie sicher, dass es als „Installiert“ und „Aktiviert“ aufgeführt ist.
-   **Berechtigungen:** In seltenen Fällen können Mitarbeiterberechtigungen die Sichtbarkeit des Menüs einschränken. Überprüfen Sie **Verwaltung > Berechtigungen** für Ihr Mitarbeiterprofil.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul Zalando Fashion Connector Importer (FCI) folgt einer Standard-PrestaShop-Modularchitektur und nutzt, wo anwendbar, MVC-Prinzipien. Es konzentriert sich hauptsächlich auf den Datenexport und verwendet eine Kombination aus Front- und Admin-Controllern. Die Kernlogik befindet sich in der Hauptmoduldatei und den Admin-Controllern für Konfiguration und Feed-Generierung. Es scheint keine benutzerdefinierten `ObjectModel`-Klassen zu verwenden, sondern fragt die PrestaShop-Datenbank direkt nach Produktdaten ab. Die Hauptfunktion des Moduls besteht darin, einen Daten-Feed zu generieren, der typischerweise von einem externen System (Zalando) über eine geplante Aufgabe (Cron-Job), die einen Front-Controller aufruft, konsumiert wird.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller sind über die Front-Office-URL zugänglich und werden typischerweise zur Generierung des Produkt-Feeds verwendet, oft ausgelöst durch einen Cron-Job.

-   `controllers/front/feed.php`
    -   **Klassenname & Elternklasse**: `ZalandofciFeedModuleFrontController` erweitert `ModuleFrontController`.
    -   **Verantwortlichkeit**: Dies ist der primäre Endpunkt für die Generierung des Produkt-Feeds. Er reagiert auf Anfragen (typischerweise von Cron-Jobs) und generiert dynamisch die Produktdaten basierend auf der Modulkonfiguration. Er ruft wahrscheinlich Produktinformationen (EAN, Preis, Menge, Name) ab und formatiert sie in die angegebene Ausgabe (z.B. CSV, XML) für Zalando. Dieser Controller rendert keine visuelle Seite, sondern gibt Rohdaten aus.
-   `controllers/front/index.php`
    -   **Klassenname & Elternklasse**: `ZalandofciIndexModuleFrontController` erweitert `ModuleFrontController`.
    -   **Verantwortlichkeit**: Dieser Controller dient wahrscheinlich als Fallback oder einfacher Einstiegspunkt, der möglicherweise umleitet oder eine minimale Nachricht anzeigt. In vielen Modulen ist ein `index.php`-Front-Controller vorhanden, um die Verzeichnisauflistung zu verhindern oder eine Standardaktion bereitzustellen, wenn keine spezifische Aktion angefordert wird.

#### Back-Office-Admin-Controller

Diese Controller verwalten die Konfiguration des Moduls und die Produkt-Export-Einstellungen innerhalb des PrestaShop Back Office.

-   `controllers/admin/AdminExportProductsFci.php`
    -   **Tab-Name und verwaltete Entität**: „Produkte exportieren“ unter dem Menü „Zalando FCI“. Dieser Controller verwaltet die detaillierte Produkt-Export-Konfiguration.
    -   **Verantwortlichkeit**: Dieser Controller behandelt die Anzeige und Übermittlung des Produkt-Export-Formulars. Er ruft Konfigurationseinstellungen (z.B. `zf_export_file_format`, `zf_export_type`, `zf_export_currency`, `zf_export_tax`, `zf_export_active` usw.) aus `ps_configuration ab`, verarbeitet Benutzereingaben und löst die eigentliche Produktdatenabruf- und Formatierungslogik für die Feed-Generierung aus. Er verwendet wahrscheinlich `AdminController`-Methoden für die Formularwiedergabe (`renderForm`) und das Speichern (`postProcess`).
-   `controllers/admin/index.php`
    -   **Tab-Name und verwaltete Entität**: „Index“ unter dem Menü „Zalando FCI“.
    -   **Verantwortlichkeit**: Ähnlich wie sein Front-Office-Pendant dient dieser Admin-Controller wahrscheinlich als Landingpage oder einfache Übersicht. Er könnte allgemeine Modulinformationen, schnelle Links zu anderen Admin-Seiten oder eine Statusmeldung anzeigen. Er ist typischerweise nicht an komplexer Datenverwaltung beteiligt, sondern an Navigation und Informationsanzeige.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass das Modul direkt mit den Kern-`Product`- und `ProductSupplier` (oder ähnlichen) `ObjectModel`-Klassen von PrestaShop und der `Configuration`-Klasse für Einstellungen interagiert. Der Datenabruf wird wahrscheinlich direkt in den Controllern oder der Hauptmoduldatei mit `Db::getInstance()->executeS()` oder `DbQuery`-Objekten gehandhabt.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist keine benutzerdefinierten JavaScript-Dateien aus. Dies impliziert, dass die Konfiguration und Funktionalität des Moduls hauptsächlich serverseitig gesteuert werden, mit minimalen oder keinen dynamischen Frontend-Interaktionen im Back Office oder Front Office, die benutzerdefiniertes JS erfordern.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `zalandofci/views/admin-theme.css`
    -   **Geltungsbereich**: Styling von Back-Office-Admin-Formularen.
    -   **Wichtige UI-Komponenten und Container, die es stylt**: Dieses Stylesheet ist für die visuelle Darstellung der Konfigurationsformulare des Moduls und möglicherweise aller benutzerdefinierten Raster oder Informationspanels innerhalb des PrestaShop Back Office verantwortlich. Es stellt sicher, dass die Benutzeroberfläche des Moduls visuell in das PrestaShop-Admin-Theme integriert ist.
    -   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Entwickler können die Admin-Seiten des Moduls inspizieren, um spezifische Klassen (z.B. `.zalandofci-form`, `.zalandofci-panel`, `.zalandofci-alert`) zu identifizieren und diese in ihrem benutzerdefinierten Admin-Theme oder durch Hinzufügen von CSS über einen `displayBackOfficeHeader`-Hook zu überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    -   Das Moduldossier listet keine expliziten Templates in einem `hook/`-Unterverzeichnis auf, registriert aber Hooks wie `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`. Wenn eine visuelle Ausgabe für diese Hooks beabsichtigt wäre, würden Templates typischerweise hier liegen. Angesichts des Zwecks des Moduls (Backend-Daten-Feed) ist es wahrscheinlich, dass diese Hooks für technische Zwecke verwendet werden (z.B. Hinzufügen von JS/CSS oder überhaupt keine visuelle Ausgabe).
-   **Admin-Templates (`views/templates/admin/`)**:
    -   `zalandofci/views/how-it-works.tpl`
        -   **Zweck**: Dieses Template liefert wahrscheinlich informative Inhalte im Back Office, möglicherweise auf der Hauptkonfigurationsseite oder dem „Index“-Bildschirm, die die Funktionsweise des Moduls erklären oder Einrichtungsanweisungen geben.
    -   `zalandofci/views/returnAlert.tpl`
        -   **Zweck**: Dieses Template wird wahrscheinlich verwendet, um Erfolgs- oder Fehlermeldungen (Alerts) im Back Office nach einer Aktion (z.B. Speichern der Konfiguration, Generieren eines Feeds) anzuzeigen.
    -   `zalandofci/views/script.tpl`
        -   **Zweck**: Dieses Template könnte Inline-JavaScript-Code enthalten oder verwendet werden, um externe JS-Dateien bedingt im Back Office einzuschließen. Es könnte für dynamisches Formularverhalten oder zum Auslösen spezifischer Aktionen verwendet werden.
-   **Front-Office-Templates (`views/templates/front/`)**:
    -   Das Moduldossier listet keine spezifischen Front-Office-Templates auf, was die Annahme verstärkt, dass das Modul keine direkte visuelle Präsenz auf der kundenorientierten Seite des Shops hat.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Das Modul scheint während der Installation (`install()`-Methode) keine benutzerdefinierten SQL-Tabellen zu erstellen.
    -   Alle modulspezifischen Konfigurationseinstellungen (z.B. `zf_client`, `zf_api`, `zf_export_file_format`, `zf_remember_settings` usw.) werden in der Standardtabelle `ps_configuration` von PrestaShop gespeichert. Diese Schlüssel sind mit `zf_` oder `PS_` (für von dem Modul verwendete PrestaShop-Kerndaten) präfixiert.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :------------------ | :---------------- |
| `displayHeader` | Wird im `<head>`-Bereich aller Front-Office-Seiten gerendert. | Potenziell zur Einbindung modulspezifischer CSS oder JS verwendet, obwohl keine benutzerdefinierten JS/CSS für das Front Office aufgeführt sind. Könnte auch für Meta-Tags oder andere nicht-visuelle Elemente verwendet werden. |
| `displayRightColumn` | Wird in der rechten Spalte von Seiten gerendert, die eine haben. | Unwahrscheinlich für visuelle Ausgabe verwendet, angesichts des Zwecks des Moduls. Könnte ein veralteter Hook sein oder für sehr spezifische, nicht-visuelle Dateninjektion verwendet werden. |
| `displayProduct` | Wird auf der Produktseite gerendert. | Unwahrscheinlich für visuelle Ausgabe verwendet. Könnte verwendet werden, um versteckte Datenattribute zu Produktelementen für externe Skripte hinzuzufügen, obwohl keine benutzerdefinierten JS aufgeführt sind. |
| `displayFooter` | Wird im Footer-Bereich aller Front-Office-Seiten gerendert. | Ähnlich wie `displayHeader` könnte es zum Einbinden von JS/CSS oder anderen nicht-visuellen Elementen am Ende des Seitenladevorgangs verwendet werden. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (JS/CSS) einstellt. | Wird von `AdminExportProductsFci` verwendet, um `zalandofci/views/admin-theme.css` für seine Konfigurationsformulare zu laden. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls Zalando Fashion Connector Importer (FCI) besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
