---
title: "Pinterest Produkte-Feed - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Pinterest Produkte-Feed“ von MyPresta.eu."
sidebar:
  label: "Pinterest Produkte-Feed - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Pinterest products feed auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/pinterest-products-feed.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/pinterest-products-feed/)
>
> ---


# Pinterest Produkte-Feed

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und gewährleisten einen reibungslosen Betrieb der Module. Ihre Hosting-Umgebung sollte auch ausreichend Speicher und Ausführungszeit für die Generierung großer Produkt-Feeds ermöglichen, insbesondere wenn Sie viele Produkte haben.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Pinterest Produkte-Feed“ verfügt über einen Hauptkonfigurationsbildschirm und einen dedizierten Administrationsbildschirm zur Verwaltung Ihrer Produkt-Feeds.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Modul-Manager > Pinterest Produkte-Feed konfigurieren)

Dies ist der Haupt-Einrichtungsbildschirm, auf dem Sie die Kernparameter für Ihren Pinterest-Produkt-Feed definieren.

#### Registerkarte „Allgemeine Einstellungen“

Diese Registerkarte enthält die grundlegenden Einstellungen für die Generierung Ihres Produkt-Feeds.

-   **Pinterest Feed aktivieren:**
    *   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (JA):* Das Modul generiert den Produkt-Feed und macht ihn über eine URL zugänglich.
        *   *Wenn deaktiviert (NEIN):* Das Modul generiert oder aktualisiert den Feed nicht, und die Feed-URL wird inaktiv.
    *   **Empfohlener Wert:** JA (sobald Sie andere Einstellungen konfiguriert haben).
    *   **Händlerszenario / Beispiel:** Sie sind bereit, auf Pinterest zu verkaufen, also aktivieren Sie dies, nachdem Sie Ihre Produktfilter eingerichtet haben.
-   **Feed-Dateityp:**
    *   **Was diese Einstellung bewirkt:** Bestimmt das Format der Produkt-Feed-Datei. Pinterest unterstützt sowohl CSV (Comma Separated Values) als auch XML (Extensible Markup Language).
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf CSV eingestellt:* Der Feed ist eine einfache Textdatei mit durch Kommas getrennten Produktdaten.
        *   *Wenn auf XML eingestellt:* Der Feed ist eine strukturierte Datei, die XML-Tags verwendet.
    *   **Empfohlener Wert:** XML (generell robuster für komplexe Daten, aber beide funktionieren mit Pinterest).
    *   **Händlerszenario / Beispiel:** Pinterest empfiehlt oft XML für umfassendere Daten, daher könnten Sie XML für bessere Kompatibilität und Zukunftssicherheit wählen.
-   **Standardsprache für Feed:**
    *   **Was diese Einstellung bewirkt:** Wählt die Sprache aus, in der Produktnamen, Beschreibungen und andere Textdaten im Feed exportiert werden.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf Englisch eingestellt:* Alle Produkttexte sind in Englisch.
        *   *Wenn auf Französisch eingestellt:* Alle Produkttexte sind in Französisch.
    *   **Empfohlener Wert:** Die primäre Sprache Ihrer Zielgruppe auf Pinterest.
    *   **Händlerszenario / Beispiel:** Wenn Sie Kunden in Frankreich ansprechen, würden Sie Französisch auswählen. Wenn Sie ein globales englischsprachiges Publikum ansprechen, würden Sie Englisch auswählen.
-   **Standardwährung für Feed:**
    *   **Was diese Einstellung bewirkt:** Wählt die Währung aus, in der Produktpreise im Feed exportiert werden.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf USD eingestellt:* Alle Preise sind in US-Dollar.
        *   *Wenn auf EUR eingestellt:* Alle Preise sind in Euro.
    *   **Empfohlener Wert:** Die primäre Währung Ihres Zielmarktes auf Pinterest.
    *   **Händlerszenario / Beispiel:** Wenn Ihr Hauptmarkt Euro verwendet, stellen Sie dies auf EUR ein, um die korrekte Preisanzeige auf Pinterest zu gewährleisten.
-   **Standardland für Feed:**
    *   **Was diese Einstellung bewirkt:** Wählt das Land aus, das Ihren Produkten im Feed zugeordnet ist. Dies kann die Versand- und Steuerberechnungen auf Pinterest beeinflussen.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf Vereinigte Staaten eingestellt:* Produkte sind dem US-Markt zugeordnet.
        *   *Wenn auf Frankreich eingestellt:* Produkte sind dem französischen Markt zugeordnet.
    *   **Empfohlener Wert:** Ihr primäres Betriebsland oder Zielmarkt.
    *   **Händlerszenario / Beispiel:** Wenn Ihr Unternehmen in Deutschland ansässig ist und hauptsächlich an deutsche Kunden verkauft, würden Sie Deutschland auswählen.
-   **Standardversanddienstleister für Feed:**
    *   **Was diese Einstellung bewirkt:** Gibt den Standardversanddienstleister an, der den Produkten im Feed zugeordnet werden soll. Dies kann von Pinterest zur Schätzung der Versandkosten verwendet werden.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn auf „Mein Versanddienstleister“ eingestellt:* Pinterest könnte die allgemeinen Versandregeln dieses Dienstleisters (falls verfügbar) zur Anzeige verwenden.
    *   **Empfohlener Wert:** Ihr am häufigsten verwendeter oder Standardversanddienstleister.
    *   **Händlerszenario / Beispiel:** Wenn Sie hauptsächlich mit FedEx versenden, würden Sie hier FedEx auswählen.
-   **Produktkombinationen (Variationen) einschließen:**
    *   **Was diese Einstellung bewirkt:** Bestimmt, ob einzelne Produktvariationen (wie verschiedene Größen oder Farben eines Hemdes) als separate Artikel im Feed enthalten sind.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (JA):* Jede Kombination (z.B. „Rotes T-Shirt - Klein“, „Rotes T-Shirt - Mittel“) ist ein eigener Eintrag im Feed.
        *   *Wenn deaktiviert (NEIN):* Nur das Hauptprodukt wird ohne individuelle Variationen aufgenommen.
    *   **Empfohlener Wert:** JA (wenn Sie möchten, dass Kunden spezifische Variationen auf Pinterest sehen und anklicken können).
    *   **Händlerszenario / Beispiel:** Sie verkaufen T-Shirts in verschiedenen Größen und Farben. Wenn Sie dies aktivieren, erhält jede einzigartige Größen-/Farbkombination einen eigenen Pin auf Pinterest, sodass Kunden genau das finden, wonach sie suchen.
-   **Produkte mit spezifischem Attribut exportieren (z.B. Größe):**
    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, ein bestimmtes Attribut (wie „Größe“ oder „Farbe“) anzugeben, das im Produkt-Feed enthalten sein soll, oft für umfassende Produktdaten verwendet.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn ausgewählt (z.B. „Größe“):* Das Größenattribut Ihrer Produkte wird explizit in die Feed-Daten aufgenommen.
        *   *Wenn nicht ausgewählt:* Dieses spezifische Attribut wird nicht explizit exportiert.
    *   **Empfohlener Wert:** Wählen Sie ein Attribut, das für die Produktdifferenzierung entscheidend ist, wie „Größe“ oder „Farbe“.
    *   **Händlerszenario / Beispiel:** Wenn Sie Kleidung verkaufen, stellt die Auswahl von „Größe“ sicher, dass Pinterest Größeninformationen direkt auf dem Pin anzeigen kann, was das Einkaufserlebnis verbessert.
-   **Produkte mit spezifischem Merkmal exportieren (z.B. Material):**
    *   **Was diese Einstellung bewirkt:** Ähnlich wie Attribute ermöglicht dies die Aufnahme eines spezifischen Produktmerkmals (wie „Material“ oder „Marke“) in den Feed.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn ausgewählt (z.B. „Material“):* Das Materialmerkmal Ihrer Produkte wird explizit in die Feed-Daten aufgenommen.
        *   *Wenn nicht ausgewählt:* Dieses spezifische Merkmal wird nicht explizit exportiert.
    *   **Empfohlener Wert:** Wählen Sie ein Merkmal, das wertvolle Informationen für Käufer hinzufügt, wie „Material“, „Marke“ oder „Stil“.
    *   **Händlerszenario / Beispiel:** Wenn Sie Möbel verkaufen, hilft die Auswahl von „Material“ (z.B. „Eiche“, „Kiefer“) Kunden, Produkte basierend auf ihren Präferenzen zu filtern und zu finden.
-   **Produkte mit spezifischem benutzerdefinierten Label exportieren (z.B. Bestseller):**
    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, ein benutzerdefiniertes Label (falls Sie diese in PrestaShop definiert haben) in den Feed aufzunehmen. Diese können für spezifische Marketingkampagnen auf Pinterest verwendet werden.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn ausgewählt (z.B. „Bestseller“):* Produkte mit diesem benutzerdefinierten Label werden in ihren Feed-Daten enthalten sein.
        *   *Wenn nicht ausgewählt:* Benutzerdefinierte Labels werden nicht exportiert.
    *   **Empfohlener Wert:** Verwenden Sie dies, wenn Sie spezifische Labels für Marketing oder Kategorisierung auf Pinterest haben.
    *   **Händlerszenario / Beispiel:** Sie haben bestimmte Produkte in PrestaShop als „Bestseller“ markiert. Der Export dieses Labels ermöglicht es Ihnen, Pinterest-Werbekampagnen speziell für diese leistungsstarken Produkte zu erstellen.
-   **Produkte nach Kategorie ausschließen:**
    *   **Was diese Einstellung bewirkt:** Bietet einen baumartigen Selektor, um ganze Produktkategorien auszuwählen, die Sie NICHT in Ihren Pinterest-Feed aufnehmen möchten.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn Kategorien ausgewählt sind:* Alle Produkte innerhalb dieser Kategorien (und ihrer Unterkategorien) werden aus dem generierten Feed ausgeschlossen.
        *   *Wenn keine Kategorien ausgewählt sind:* Alle Produkte aus allen Kategorien werden für den Export berücksichtigt (es sei denn, sie werden durch andere Einstellungen ausgeschlossen).
    *   **Empfohlener Wert:** Schließen Sie Kategorien aus, die nicht für Pinterest geeignet sind (z.B. Dienstleistungen, digitale Downloads oder Produkte, die Sie nicht bewerben möchten).
    *   **Händlerszenario / Beispiel:** Sie verkaufen sowohl physische Produkte als auch digitale Geschenkkarten. Sie würden die Kategorie „Digitale Geschenkkarten“ aus dem Feed ausschließen, da Pinterest hauptsächlich für physische Produkte ist.
-   **Spezifische Produkte ausschließen:**
    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, einzelne Produkte zu suchen und auszuwählen, die Sie explizit aus dem Pinterest-Feed ausschließen möchten.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn Produkte ausgewählt sind:* Diese spezifischen Produkte werden nicht im generierten Feed erscheinen.
        *   *Wenn keine Produkte ausgewählt sind:* Alle Produkte (die nicht nach Kategorie ausgeschlossen sind) werden für den Export berücksichtigt.
    *   **Empfohlener Wert:** Schließen Sie spezifische Produkte aus, die auf unbestimmte Zeit nicht auf Lager sind, eingestellt wurden oder aus anderen Gründen nicht auf Pinterest erscheinen sollen.
    *   **Händlerszenario / Beispiel:** Ein bestimmtes Produkt ist aufgrund eines Lieferantenproblems vorübergehend nicht verfügbar, daher schließen Sie es aus, bis es wieder auf Lager ist.
-   **Feed-URL generieren:**
    *   **Was diese Einstellung bewirkt:** Zeigt die eindeutige URL an, unter der Ihr Pinterest-Produkt-Feed abgerufen werden kann. Dies ist die URL, die Sie Pinterest zur Verfügung stellen werden.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld. Die URL ändert sich, wenn Sie die Domain Ihres Shops oder die SSL-Einstellungen ändern.
    *   **Empfohlener Wert:** Kopieren Sie diese URL und fügen Sie sie in die Einstellungen Ihres Pinterest Business-Kontos ein, wenn Sie Ihren Produktkatalog einrichten.
    *   **Händlerszenario / Beispiel:** Nachdem Sie alle Einstellungen konfiguriert haben, kopieren Sie diese URL und gehen zu Ihrem Pinterest Business-Konto, um Ihren Produktkatalog einzurichten, indem Sie diese URL in das Feld „Datenquelle“ einfügen.
-   **Feed generieren (Schaltfläche):**
    *   **Was diese Einstellung bewirkt:** Löst manuell die Generierung der Produkt-Feed-Datei aus.
    *   **Auswirkung einer Änderung dieser Einstellung:** Das Klicken auf diese Schaltfläche erstellt oder aktualisiert die Feed-Datei sofort basierend auf Ihren aktuellen Einstellungen. Dies kann bei großen Katalogen einige Zeit in Anspruch nehmen.
    *   **Empfohlener Wert:** Klicken Sie darauf, nachdem Sie Änderungen an Ihren Feed-Einstellungen vorgenommen haben oder wenn Sie eine sofortige Aktualisierung erzwingen möchten.
    *   **Händlerszenario / Beispiel:** Sie haben gerade 50 neue Produkte hinzugefügt und möchten, dass diese so schnell wie möglich auf Pinterest erscheinen, also klicken Sie auf „Feed generieren“.

#### Registerkarte „Cron-Job-Einstellungen“

Diese Registerkarte enthält Informationen zur Automatisierung des Feed-Generierungsprozesses.

-   **Cron-Job-URL:**
    *   **Was diese Einstellung bewirkt:** Zeigt eine spezielle URL an, die, wenn sie aufgerufen wird, den Feed-Generierungsprozess automatisch auslöst, ohne dass Sie im Back Office auf die Schaltfläche „Feed generieren“ klicken müssen.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld.
    *   **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als „Cron-Job“ auf Ihrem Webhosting-Server ein.
    *   **Händlerszenario / Beispiel:** Sie möchten, dass Ihr Pinterest-Feed jede Nacht um 3 Uhr morgens aktualisiert wird. Sie kopieren diese URL und konfigurieren einen Cron-Job auf Ihrem Server, um diese URL täglich um 3 Uhr morgens aufzurufen.
-   **Wie man einen Cron-Job einrichtet:**
    *   **Was diese Einstellung bewirkt:** Bietet Anweisungen, wie Sie eine automatisierte Aufgabe (Cron-Job) auf Ihrem Webserver einrichten, um Ihren Produkt-Feed regelmäßig zu aktualisieren.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Informationsbereich.
    *   **Empfohlener Wert:** Befolgen Sie diese Anweisungen oder geben Sie sie an Ihren Webmaster/Hosting-Support weiter, um sicherzustellen, dass Ihr Feed immer aktuell ist.
    *   **Händlerszenario / Beispiel:** Sie sind sich nicht sicher, wie Sie einen Cron-Job einrichten sollen. Dieser Abschnitt gibt Ihnen die genauen Schritte oder die Informationen, die Sie an Ihren Hosting-Anbieter weitergeben können.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### Pinterest Feeds Dashboard (Back Office > Verkaufen > Pinterest Feeds)

Dieser dedizierte Bereich Ihres PrestaShop Back Office bietet eine Übersicht und Verwaltungsoberfläche für Ihre Pinterest-Produkt-Feeds. Sie finden ihn unter dem Menüpunkt „Verkaufen“ in PrestaShop 1.7/8/9.

-   **Bildschirmname & Menüpfad:** Pinterest Feeds (unter „Verkaufen“ im Hauptmenü).
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Feed-Auflistungstabelle:** Diese Tabelle zeigt alle generierten Feeds an (wenn das Modul mehrere Feeds unterstützt, ansonsten wird der Haupt-Feed angezeigt). Sie enthält typischerweise:
        *   **Feed-Name/ID:** Eine eindeutige Kennung für den Feed.
        *   **Sprache:** Die Sprache der Produkte im Feed.
        *   **Währung:** Die Währung der Preise im Feed.
        *   **Zuletzt generiert:** Datum und Uhrzeit der letzten Aktualisierung des Feeds.
        *   **Feed-URL:** Der direkte Link zur generierten Feed-Datei.
        *   **Aktionen:** Schaltflächen zum Anzeigen, Herunterladen oder Regenerieren des Feeds.
    *   **Neuen Feed hinzufügen / Feed bearbeiten:** Obwohl sich das Modul hauptsächlich auf einen einzigen Haupt-Feed konzentriert, könnte diese Oberfläche zukünftige Erweiterungen oder spezifische Feed-Konfigurationen ermöglichen. Vorerst spiegelt sie weitgehend die Einstellungen der Hauptkonfigurationsseite wider.
    *   **Raster- / Verwaltungsansicht:** Dieser Bildschirm bietet einen klaren Überblick über den Status Ihres Feeds und schnellen Zugriff auf dessen URL und Regenerierungsoptionen.
-   **Auswirkung von Änderungen:**
    *   *Regenerieren eines Feeds:* Aktualisiert die Feed-Datei mit den neuesten Produktdaten aus Ihrem Shop und spiegelt alle Änderungen an Produktinformationen, Preisen oder Lagerbeständen wider.
    *   *Anzeigen der Feed-URL:* Ermöglicht Ihnen, die für Pinterest benötigte URL schnell zu kopieren.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Überprüfen Sie regelmäßig dieses Dashboard, um sicherzustellen, dass Ihr Feed regelmäßig generiert wird (wenn Sie einen Cron-Job eingerichtet haben) und dass der Zeitstempel „Zuletzt generiert“ aktuell ist.
    2.  Wenn Sie wesentliche Produktänderungen vornehmen (z.B. Massenpreisaktualisierungen, neue Produkteinführungen), können Sie den Feed manuell von diesem Bildschirm oder der Modulkonfiguration aus regenerieren, um sicherzustellen, dass Pinterest die neuesten Daten schnell erhält.
    3.  Kopieren Sie die Feed-URL von hier, wenn Sie Ihr Pinterest Business-Konto initial einrichten.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Pinterest Feed aktivieren | JA | Aktiviert/deaktiviert die Feed-Generierung. |
| | Feed-Dateityp | XML | Legt das Ausgabeformat für den Feed fest (CSV oder XML). |
| | Standardsprache für Feed | Ihre Primärsprache | Sprache für Produktnamen/Beschreibungen. |
| | Standardwährung für Feed | Ihre Primärwährung | Währung für Produktpreise. |
| | Standardland für Feed | Ihr Primärland | Länderzuordnung für Produkte. |
| | Standardversanddienstleister für Feed | Ihr Standardversanddienstleister | Versanddienstleister für Pinterest-Schätzungen. |
| | Produktkombinationen einschließen | JA | Exportiert individuelle Produktvariationen. |
| | Produkte mit spezifischem Attribut exportieren | Relevantes Attribut auswählen (z.B. Größe) | Schließt spezifische Produktattribute in den Feed ein. |
| | Produkte mit spezifischem Merkmal exportieren | Relevantes Merkmal auswählen (z.B. Material) | Schließt spezifische Produktmerkmale in den Feed ein. |
| | Produkte mit spezifischem benutzerdefinierten Label exportieren | Relevantes Label auswählen (z.B. Bestseller) | Schließt benutzerdefinierte Labels für Marketing ein. |
| | Produkte nach Kategorie ausschließen | Kategorien zum Ausschließen auswählen | Verhindert, dass Produkte aus ausgewählten Kategorien im Feed erscheinen. |
| | Spezifische Produkte ausschließen | Einzelne Produkte zum Ausschließen auswählen | Verhindert, dass spezifische Produkte im Feed erscheinen. |
| | Feed-URL generieren | (Nur Anzeige) | Die URL, die Pinterest zum Abrufen Ihres Feeds bereitgestellt wird. |
| | Feed generieren (Schaltfläche) | Nach Änderungen klicken | Löst die sofortige Feed-Generierung manuell aus. |
| **Cron-Job-Einstellungen-Tab** | Cron-Job-URL | (Nur Anzeige) | URL für die automatisierte Feed-Generierung über Server-Cron. |
| | Wie man einen Cron-Job einrichtet | Anweisungen befolgen | Anleitung zum Einrichten automatischer Feed-Updates. |
| **Pinterest Feeds Dashboard** | Feed-Auflistungstabelle | (Ansicht) | Übersicht über generierte Feeds, Status und URLs. |
| | Feed regenerieren (Aktion) | Bei Bedarf klicken | Aktualisiert den Feed mit den neuesten Shop-Daten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Produkte erscheinen nicht auf Pinterest, nachdem ich den Feed eingerichtet habe. Was soll ich tun?**
A1: Stellen Sie zunächst sicher, dass die Einstellung „Pinterest Feed aktivieren“ in der Modulkonfiguration auf JA gesetzt ist. Klicken Sie dann manuell auf die Schaltfläche „Feed generieren“, um die anfängliche Feed-Datei zu erstellen. Überprüfen Sie anschließend nochmals, ob Sie die „Feed-URL generieren“ korrekt in die Produktkatalogeinstellungen Ihres Pinterest Business-Kontos kopiert und eingefügt haben. Pinterest kann einige Zeit (bis zu 24-48 Stunden) benötigen, um einen neuen Feed zu verarbeiten. Überprüfen Sie auch Ihr Pinterest Business-Konto auf Fehlermeldungen bezüglich des Feeds.

**F2: Die Preise oder Lagerbestände auf Pinterest sind veraltet. Wie kann ich das beheben?**
A2: Dies bedeutet normalerweise, dass Ihr Feed nicht regelmäßig aktualisiert wird. Stellen Sie sicher, dass Sie den Cron-Job auf Ihrem Hosting-Server mit der im Modul bereitgestellten „Cron-Job-URL“ eingerichtet haben. Wenn der Cron-Job eingerichtet ist, überprüfen Sie, ob er korrekt ausgeführt wird (Ihr Hosting-Anbieter kann Ihnen dabei helfen). Sie können den Feed auch manuell regenerieren, indem Sie in der Modulkonfiguration auf die Schaltfläche „Feed generieren“ klicken, um eine sofortige Aktualisierung zu erzwingen.

**F3: Einige meiner Produkte fehlen im Pinterest-Feed.**
A3: Gehen Sie zur Konfigurationsseite des Moduls und überprüfen Sie die Einstellungen „Produkte nach Kategorie ausschließen“ und „Spezifische Produkte ausschließen“. Möglicherweise haben Sie versehentlich Kategorien oder einzelne Produkte ausgeschlossen. Stellen Sie außerdem sicher, dass die Produkte gültige Bilder und Preise haben und in Ihrem PrestaShop-Shop auf „aktiv“ und „bestellbar“ gesetzt sind, da das Modul typischerweise nur aktive, kaufbare Produkte exportiert.

**F4: Der Feed-Generierungsprozess dauert sehr lange oder bricht mit einem Timeout ab.**
A4: Wenn Sie einen sehr großen Katalog (Tausende von Produkten) haben, kann die Generierung des Feeds ressourcenintensiv sein.
\* **Lösung 1:** Erhöhen Sie die PHP-Einstellungen `memory_limit` und `max_execution_time` in der `php.ini`-Datei Ihres Servers. Ihr Hosting-Anbieter kann Ihnen dabei helfen.
\* **Lösung 2:** Stellen Sie sicher, dass Ihr Cron-Job so eingestellt ist, dass er außerhalb der Spitzenzeiten ausgeführt wird, um die Auswirkungen auf die Shop-Leistung zu minimieren.
\* **Lösung 3:** Erwägen Sie, weniger wichtige Kategorien oder Produkte auszuschließen, wenn die Feed-Größe durchweg ein Problem darstellt.

**F5: Meine benutzerdefinierten Theme-Stile werden nicht auf die Admin-Oberfläche des Moduls angewendet.**
A5: Die Admin-Oberfläche des Moduls verwendet ihre eigenen CSS-Dateien (`admin-app.css`, `admin-theme.css`). Diese sind getrennt von Ihrem Front-Office-Theme. Wenn Sie das Aussehen der Back-Office-Seiten des Moduls anpassen möchten, müssten Sie diese spezifischen CSS-Dateien überschreiben oder benutzerdefiniertes CSS zu Ihrem PrestaShop Back Office hinzufügen. Dies ist typischerweise eine Aufgabe für einen Webentwickler.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Pinterest Produkte-Feed“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul `pinterestfeed` folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) mit dedizierten Front-Controllern für die Feed-Generierung und Cron-Ausführung sowie Admin-Controllern für Konfiguration und Verwaltung. Es nutzt `ObjectModel` für potenzielle Datenpersistenz (obwohl es sich hauptsächlich auf die dynamische Feed-Generierung konzentriert) und verwendet Smarty-Templates für die Darstellung sowohl der Back-Office-Konfiguration als auch der Informationsansichten. Die Kernlogik zur Generierung des Feeds gemäß den Pinterest-Spezifikationen ist in dedizierten Hilfsklassen gekapselt.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verarbeiten öffentlich zugängliche Anfragen, hauptsächlich für den Feed selbst und die Cron-Job-Ausführung.

-   `controllers/front/cron.php`
    *   **Klassenname & übergeordnete Klasse:** `PinterestFeedCronModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller ist dafür konzipiert, von einem serverseitigen Cron-Job aufgerufen zu werden. Beim Zugriff löst er die Klasse `PinterestFeedGenerator` aus, um den Produkt-Feed basierend auf der aktuellen Modulkonfiguration neu zu generieren. Er gibt typischerweise eine einfache Erfolgs-/Fehlermeldung zurück oder protokolliert den Prozess. Er rendert keine visuelle Seite.
-   `controllers/front/feed.php`
    *   **Klassenname & übergeordnete Klasse:** `PinterestFeedFeedModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller liefert die eigentliche Produkt-Feed-Datei. Beim Zugriff über die „Feed-URL generieren“ liest er die vorab generierte Feed-Datei (oder generiert sie, falls sie nicht existiert/veraltet ist, je nach Implementierung) und gibt ihren Inhalt (CSV oder XML) mit entsprechenden HTTP-Headern (`Content-Type`) aus.

#### Back-Office-Admin-Controller

Diese Controller verwalten die Modulkonfiguration und stellen administrative Schnittstellen bereit.

-   `controllers/admin/AdminExportProductsFeedPinterest.php`
    *   **Klassenname & übergeordnete Klasse:** `AdminExportProductsFeedPinterestController` erweitert `ModuleAdminController`.
    *   **Tab-Name und verwaltete Entität:** Dieser Controller ist für das „Pinterest Feeds“-Dashboard verantwortlich, das sich unter dem Menüpunkt „Verkaufen“ befindet. Er verwaltet die Anzeige und Aktionen im Zusammenhang mit den generierten Produkt-Feeds. Er verwaltet keine spezifische `ObjectModel`-Entität direkt, sondern orchestriert die Generierung und Anzeige von Feed-bezogenen Daten.
    *   **Genutzte Schlüsselkonfigurationsschlüssel:** `PS_LANG_DEFAULT`, `PS_CARRIER_DEFAULT`, `PS_COUNTRY_DEFAULT`, `PS_CURRENCY_DEFAULT` (für Standardwerte in Formularen), `pm_pinterestfeed_products`, `pm_export_size_attribute` (für modulspezifische Einstellungen). Es verwendet auch `pf_tree` für die Kategorieauswahl und `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` für die Sprachauswahl in Formularen.
-   `controllers/admin/index.php`
    *   **Klassenname & übergeordnete Klasse:** Diese Datei dient wahrscheinlich als Platzhalter oder einfacher Redirect/Einstiegspunkt für den Admin-Bereich, anstatt als vollwertiger Controller. In PrestaShop verhindern `index.php`-Dateien in Unterverzeichnissen oft die direkte Verzeichnisauflistung. Ihre Hauptaufgabe ist es, die Sicherheit zu gewährleisten, indem sie den direkten Zugriff auf die Verzeichnisinhalte verhindert.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `classes/index.php`
    *   **Zweck:** Standard-PrestaShop-Sicherheitsdatei zur Verhinderung der direkten Verzeichnisauflistung.
-   `classes/PinterestFeedGenerator.php`
    *   **Verantwortlichkeit:** Dies ist die Kernlogikklasse für den Aufbau des Produkt-Feeds.
    *   **Datenbankinteraktion:** Interagiert mit verschiedenen PrestaShop-Kerntabellen (z.B. `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_attribute`, `ps_feature`, `ps_stock_available`), um Produktdaten abzurufen.
    *   **ObjectModel-Erweiterung:** Erweitert `ObjectModel` nicht direkt, da sein Zweck die Datenaggregation und -formatierung und nicht die Persistenz einzelner Entitäten ist.
    *   **Wichtige öffentliche Methoden:** Enthält Methoden zum Abrufen von Produkten, zum Verwalten von Kombinationen, zum Anwenden von Filtern (Kategorien, spezifische Produkte), zum Formatieren von Daten gemäß den Pinterest-Spezifikationen und zum Schreiben der Ausgabe in den gewählten Dateityp (CSV/XML).
-   `classes/PinterestFeedSpec.php`
    *   **Verantwortlichkeit:** Diese Klasse definiert wahrscheinlich die erforderlichen und optionalen Felder für die Pinterest-Produkt-Feed-Spezifikation. Sie fungiert als Mapping- oder Validierungsschicht, um sicherzustellen, dass der generierte Feed den Pinterest-Richtlinien entspricht.
    *   **Datenbankinteraktion:** Keine direkte.
    *   **ObjectModel-Erweiterung:** Erweitert `ObjectModel` nicht.
    *   **Wichtige öffentliche Methoden:** Kann Methoden zum Abrufen der Liste der erforderlichen/optionalen Felder, ihrer Datentypen und spezifischer Formatierungsregeln enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Bietet Autocomplete-Funktionalität, wahrscheinlich zum Suchen und Auswählen von Produkten oder Kategorien in den Admin-Konfigurationsformularen (z.B. für „Spezifische Produkte ausschließen“).
    *   **Event-Listener:** Bindet an `keyup`- oder `input`-Ereignisse von Eingabefeldern, um AJAX-Suchen auszulösen.
    *   **DOM-Manipulation:** Zeigt Suchergebnisse in einer Dropdown-Liste an, ermöglicht die Auswahl und aktualisiert versteckte Eingabefelder.
-   `views/js/admin-app.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Zweck:** Haupt-JavaScript für die Back-Office-Konfiguration und das Dashboard des Moduls. Verwaltet Formularübermittlungen, dynamische Updates und potenziell AJAX-Aufrufe für den Feed-Generierungsstatus.
    *   **Event-Listener:** Bindet an `submit`-Ereignisse von Formularen, `click`-Ereignisse von Schaltflächen (z.B. „Feed generieren“) und potenziell `change`-Ereignisse von Auswahlfeldern.
    *   **DOM-Manipulation:** Verwaltet die Anzeige von Konfigurations-Tabs, aktualisiert Statusmeldungen und interagiert mit der Autocomplete-Komponente.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Zweck:** Gestaltet das Autocomplete-Suchfeld und seine Dropdown-Ergebnisse, um ein konsistentes Erscheinungsbild innerhalb des PrestaShop Back Office zu gewährleisten.
    *   **Wichtige CSS-Klassenselektoren:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
-   `views/admin-theme.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Zweck:** Bietet allgemeines Styling für die Back-Office-Konfigurationsseiten des Moduls, um eine gute Integration in das PrestaShop-Admin-Theme zu gewährleisten.
    *   **Wichtige CSS-Klassenselektoren:** `.panel`, `.form-group`, `.control-label`, `.help-block`.
-   `views/css/admin-app.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Zweck:** Spezifisches Styling für die benutzerdefinierten Elemente und das Layout des Moduls innerhalb der Admin-Oberfläche, wie z.B. Tab-Navigation, benutzerdefinierte Schaltflächen oder einzigartige Informationsblöcke.
    *   **Wichtige CSS-Klassenselektoren:** `.pinterestfeed-tabs`, `.pinterestfeed-panel`, `.pinterestfeed-alert`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**: Die Modulbeschreibung listet keine Hook-Templates explizit auf, was darauf hindeutet, dass die Front-Office-Präsenz hauptsächlich über die Feed-URL und nicht über direkte Anzeige erfolgt. Falls vorhanden, wären sie für Informationsblöcke.
-   **Admin-Templates (`views/templates/admin/`)**:
    *   `views/templates/admin/dashboard.tpl`: Wahrscheinlich das Haupt-Template für das „Pinterest Feeds“-Dashboard, das die Liste der Feeds, ihren Status und Aktionen anzeigt.
    *   `views/templates/admin/feeds.tpl`: Könnte ein partielles Template sein, das innerhalb von `dashboard.tpl` verwendet wird, um die Tabelle der Feeds zu rendern.
    *   `views/templates/admin/form-chrome.tpl`: Ein generisches Wrapper-Template für Admin-Formulare, das die Standard-PrestaShop-Panel- und Formularstruktur bereitstellt.
    *   `views/templates/admin/layout.tpl`: Das Haupt-Layout-Template für den Admin-Bereich des Moduls, das die Gesamtstruktur einschließlich Header, Tabs und Inhaltsbereich definiert.
-   **Konfigurations- & Dienstprogramm-Templates (`views/`)**:
    *   `views/categories-fancybox.tpl`: Template für ein Fancybox-Modal, das für die Kategorieauswahl verwendet wird (z.B. zum Ausschließen).
    *   `views/custom-labels.tpl`: Template zum Anzeigen oder Verwalten benutzerdefinierter Labels.
    *   `views/exclude-products.tpl`: Template für die Such- und Auswahl-Oberfläche zum Produktausschluss.
    *   `views/google_lang_links.tpl`: Potenziell zur Anzeige sprachspezifischer Links oder Informationen, obwohl seine direkte Verwendung in einem Pinterest-Feed-Modul zu Informationszwecken dienen könnte.
    *   `views/returnAlert.tpl`: Ein generisches Template zum Anzeigen von Erfolgs- oder Fehlerwarnungen im Back Office.
    *   `views/script-fancybox.tpl`: Enthält JavaScript zur Initialisierung und Verwaltung von Fancybox-Modals.
    *   `views/script.tpl`: Allgemeine JavaScript-Snippets oder Initialisierungsskripte für die Admin-Seiten des Moduls.
    *   `lib/searchTool/views/scripts.tpl`: Enthält JavaScript für das Autocomplete-Suchwerkzeug.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul scheint basierend auf dem bereitgestellten Inventar keine eigenen benutzerdefinierten SQL-Tabellen zu erstellen.
    *   Es stützt sich stark auf bestehende PrestaShop-Kerntabellen: `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_category_product`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_product`, `ps_stock_available`, `ps_configuration` (für Moduleinstellungen wie `PINTERESTFEED_ENABLED`, `PINTERESTFEED_FILE_TYPE` usw.).
-   **Registrierte Hooks-Tabelle**:
    Die Hauptfunktion des Moduls ist die Feed-Generierung, die typischerweise durch direkten Controller-Zugriff (Feed-URL, Cron-URL) oder Admin-Aktionen ausgelöst wird. Obwohl die Modulbeschreibung „Front-Office Hooks: Header, Columns, Product, or Footer“ erwähnt, deuten das bereitgestellte Dateiverzeichnis und die Funktionsbeschreibung darauf hin, dass diese von *diesem spezifischen Modul* nicht aktiv für die visuelle Anzeige verwendet werden. Stattdessen registriert das Modul wahrscheinlich Hooks für interne Prozesse oder potenzielle zukünftige Erweiterungen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Bei jedem Seitenaufruf im Front Office. | Potenziell zum Hinzufügen von benutzerdefiniertem JS/CSS, falls das Modul eine Front-Office-Komponente hätte, oder für interne Nachverfolgung. (Unwahrscheinlich für visuelle Ausgabe durch dieses Modul verwendet). |
| `displayRightColumn` | In der rechten Spalte des Front Office. | (Unwahrscheinlich für visuelle Ausgabe durch dieses Modul verwendet). |
| `displayLeftColumn` | In der linken Spalte des Front Office. | (Unwahrscheinlich für visuelle Ausgabe durch dieses Modul verwendet). |
| `displayFooter` | Im Footer jeder Seite im Front Office. | (Unwahrscheinlich für visuelle Ausgabe durch dieses Modul verwendet). |
| `displayProductExtraContent` | Auf der Produktseite, unterhalb des Hauptinhalts. | (Unwahrscheinlich für visuelle Ausgabe durch dieses Modul verwendet). |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Potenziell, um den Feed als regenerierungsbedürftig zu markieren oder eine Teilaktualisierung auszulösen. |
| `actionProductAdd` | Nach dem Hinzufügen eines neuen Produkts. | Ähnlich wie `actionProductUpdate`. |
| `actionProductDelete` | Nach dem Löschen eines Produkts. | Ähnlich wie `actionProductUpdate`. |
| `actionUpdateQuantity` | Nach Änderungen der Produktbestandsmenge. | Potenziell, um die Feed-Regenerierung auszulösen, wenn Bestandsänderungen für den Feed kritisch sind. |
| `actionModuleInstall` | Während der Modulinstallation. | Zum Erstellen von Konfigurationseinträgen und potenziell der anfänglichen Feed-Datei. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Zum Bereinigen von Konfigurationseinträgen und generierten Dateien. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Könnte verwendet werden, um einen spezifischen Tab oder ein Feld für Pinterest-Feed-Einstellungen für einzelne Produkte hinzuzufügen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für Ihr Modul „Pinterest Produkte-Feed“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser Team setzt sich dafür ein, dass Ihr Modul perfekt funktioniert und Ihnen hilft, Ihre E-Commerce-Ziele zu erreichen.

-   **MyPresta.eu Bestellhistorie & Downloads:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Support-Kontakt:** <https://mypresta.eu/contact>
