---
title: "Microsoft Merchant Center Produkt-Feed - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Microsoft Merchant Center Produkt-Feed von MyPresta.eu."
sidebar:
  label: "Microsoft Merchant Center Produkt-Feed - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Microsoft Merchant Center Product Feed auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


# Microsoft Merchant Center Produkt-Feed

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ihr Server muss in der Lage sein, Cron-Jobs für die automatisierte Feed-Generierung auszuführen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls. Hier legen Sie das allgemeine Verhalten fest und greifen auf die Feed-Verwaltungstools zu.

#### Allgemeine Einstellungen

Dieser Abschnitt behandelt typischerweise globale Einstellungen, die die Funktionsweise des Moduls und die Generierung von Feeds beeinflussen.

- **Was diese Einstellung bewirkt:** Dies sind die Kerneinstellungen, die definieren, wie Ihre Produktdaten für das Microsoft Merchant Center aufbereitet werden. Sie finden hier typischerweise Optionen zur Auswahl der Sprache, Währung und des Landes für Ihren Feed sowie allgemeine Exportpräferenzen.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Sprache:* Bestimmt, welche Sprachversion Ihrer Produktnamen, Beschreibungen und Kategorien in den Feed aufgenommen wird. Entscheidend für die Ausrichtung auf spezifische internationale Märkte.
  - *Währung:* Legt die Währung für alle Preise im Feed fest. Muss mit der im Microsoft Merchant Center-Konto für das Zielland konfigurierten Währung übereinstimmen.
  - *Land:* Gibt das Zielland für den Feed an. Dies beeinflusst Steuervorschriften, Versandeinstellungen und andere länderspezifische Anforderungen im Microsoft Merchant Center.
  - *Weitere Exportoptionen:* Können Einstellungen für die Handhabung von Produktvarianten, den Ausschluss bestimmter Kategorien oder die Definition der Exportweise spezifischer Attribute (wie Größe oder Farbe) umfassen.
- **Empfohlener Wert:**
  - *Sprache, Währung, Land:* Wählen Sie die primäre Sprache, Währung und das Land aus, auf die Sie Ihre Microsoft Shopping Ads ausrichten. Wenn Sie in mehreren Ländern/Sprachen werben, werden Sie wahrscheinlich separate Feeds für jedes erstellen.
  - *Weitere Optionen:* Befolgen Sie die Empfehlungen des Moduls oder passen Sie sie basierend auf Ihrem spezifischen Produktkatalog und Ihrer Werbestrategie an.
- **Händlerszenario / Beispiel:** Wenn Sie in Frankreich verkaufen und die Standardsprache Ihres Shops Französisch ist, würden Sie Französisch für die Sprache, EUR für die Währung und Frankreich für das Land auswählen. Wenn Sie auch in Deutschland verkaufen, würden Sie einen separaten Feed erstellen, der für die deutsche Sprache, EUR-Währung und Deutschland als Land konfiguriert ist.

#### Feed-Verwaltung & Generierung

Dieser Abschnitt bietet Zugriff zum Erstellen, Verwalten und Generieren Ihrer Produkt-Feeds.

- **Was diese Einstellung bewirkt:** Dies ist das Herzstück des Moduls, das Ihnen ermöglicht, die eigentlichen Produkt-Feed-Dateien zu definieren und zu generieren. Sie finden hier typischerweise Optionen zum Erstellen neuer Feeds, zum Anzeigen bestehender Feeds und zum Auslösen des Generierungsprozesses.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Einen neuen Feed erstellen:* Leitet den Prozess der Einrichtung eines neuen Produkt-Feeds mit eigenen spezifischen Einstellungen (Sprache, Währung, Kategorien usw.) ein.
  - *Einen Feed generieren:* Verarbeitet Ihre PrestaShop-Produktdaten und erstellt die CSV-, XML- oder TSV-Datei, die Sie in das Microsoft Merchant Center hochladen werden. Diese Datei enthält alle Produktattribute im von Microsoft geforderten Format.
  - *Cron-URL:* Bietet eine spezielle Webadresse, die bei Aufruf automatisch die Feed-Generierung auslöst. Dies ist unerlässlich für die Einrichtung automatischer täglicher oder stündlicher Aktualisierungen Ihres Produkt-Feeds ohne manuelles Eingreifen.
- **Empfohlener Wert:**
  - Erstellen Sie mindestens einen Feed für Ihren primären Zielmarkt.
  - Richten Sie einen Cron-Job mit der bereitgestellten URL ein, um sicherzustellen, dass Ihr Produkt-Feed regelmäßig (z.B. täglich) mit den neuesten Produktinformationen (Lagerbestände, Preise, neue Produkte) aktualisiert wird.
- **Händlerszenario / Beispiel:** Sie haben gerade eine neue Produktlinie eingeführt. Durch einen täglichen Cron-Job spiegeln Ihre Microsoft Shopping Ads diese neuen Produkte und deren aktuelle Lagerbestände automatisch am nächsten Tag wider, ohne dass Sie den Feed manuell neu hochladen müssen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminExportProductsFeedMicrosoftController (Back Office > Microsoft Merchant Center > Produkt-Feed exportieren)

Dies ist der primäre dedizierte Bildschirm zur Verwaltung der Details Ihrer Produkt-Feeds. Sie greifen darauf über einen neuen Menüpunkt zu, der vom Modul hinzugefügt wird, wahrscheinlich unter „Katalog“ oder einem neuen Abschnitt „Microsoft Merchant Center“.

- **Bildschirmname & Menüpfad:** **Back Office > Microsoft Merchant Center > Produkt-Feed exportieren** (oder ähnlich, abhängig von Modulversion und PrestaShop-Menüstruktur).
- **Verfügbare Aktionen & Einstellungen:** Auf diesem Bildschirm definieren Sie den spezifischen Inhalt und die Zuordnung für jeden Ihrer Produkt-Feeds. Sie sehen typischerweise eine Liste bestehender Feeds mit Optionen zum „Neuen Feed hinzufügen“ oder „Bearbeiten“ eines bestehenden Feeds. Beim Hinzufügen/Bearbeiten konfigurieren Sie:
  - **Feed-Name:** Ein beschreibender Name für Ihren Feed (z.B. „Frankreich - Französischer Feed“, „USA - Englischer Feed“).
  - **Zielland:** Das Land, für das dieser Feed bestimmt ist (z.B. Frankreich, Vereinigte Staaten). Dies beeinflusst Währung, Sprache und Steuervorschriften.
  - **Inhaltssprache:** Die Sprache der Produktdaten in diesem Feed (z.B. Französisch, Englisch).
  - **Währung:** Die Währung, die für Preise in diesem Feed verwendet wird (z.B. EUR, USD).
  - **Dateiformat:** Wählen Sie zwischen CSV, XML oder TSV, wie vom Microsoft Merchant Center gefordert.
  - **Kategoriezuordnung:** Dies ist ein entscheidender Abschnitt, in dem Sie Ihre PrestaShop-Kategorien der Produkt-Taxonomie von Microsoft zuordnen. Dies hilft Microsoft zu verstehen, was Ihre Produkte sind, und sie in relevanten Suchanfragen anzuzeigen.
  - **Produktfilterung:** Optionen zum Ein- oder Ausschließen spezifischer Produkte oder ganzer Kategorien aus dem Feed.
  - **Attributzuordnung:** Ordnen Sie PrestaShop-Produktattribute (wie Größe, Farbe, Material) den von Microsoft geforderten Attributen zu (z.B. `size`, `color`, `material`).
  - **Benutzerdefinierte Labels:** Definieren Sie bis zu 5 benutzerdefinierte Labels (`custom_label_0` bis `custom_label_4`), um Ihre Produkte für Gebotsstrategien in Microsoft Ads zu segmentieren.
  - **Verfügbarkeit & Zustand:** Einstellungen zur Definition, wie Produktverfügbarkeit (auf Lager, nicht auf Lager, Vorbestellung) und Zustand (neu, gebraucht, überholt) exportiert werden.
  - **GTIN (Global Trade Item Number):** Einstellungen für den Export von EAN/UPC-Codes als GTINs.
  - **Marke:** Wie Produktmarken exportiert werden.
  - **Beschreibung:** Optionen für den Export von Produktbeschreibungen, oft mit Klartextkonvertierung.
  - **Bild-Links:** Wie Produktbilder verlinkt werden.
  - **Preis & Verkaufspreis:** Wie reguläre Preise und Verkaufspreise exportiert werden, einschließlich Steuerüberlegungen.
  - **Cron-URL:** Die eindeutige URL für diesen spezifischen Feed, die Sie für automatisierte Updates verwenden werden.
- **Auswirkungen von Änderungen:**
  - Änderungen hier wirken sich direkt auf den Inhalt und die Struktur der generierten Produkt-Feed-Datei aus. Falsche Einstellungen können zu Produktablehnungen im Microsoft Merchant Center führen.
  - Eine korrekte Kategoriezuordnung stellt sicher, dass Ihre Produkte in relevanten Shopping-Kategorien auf Bing erscheinen.
  - Genaue Preis- und Verfügbarkeitsdaten verhindern Kundenfrustration und Anzeigenablehnungen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Ersteinrichtung:** Erstellen Sie einen Feed für jede Ziel-Land-/Sprachkombination, in der Sie werben. Ordnen Sie Ihre Kategorien sorgfältig der Microsoft-Taxonomie zu.
  2. **Attribute überprüfen:** Stellen Sie sicher, dass alle kritischen Attribute (GTIN, Marke, Preis, Verfügbarkeit, Bild-Links) korrekt zugeordnet und exportiert werden.
  3. **Cron-Jobs einrichten:** Implementieren Sie die bereitgestellten Cron-URLs auf Ihrem Hosting-Server, um die tägliche (oder häufigere) Feed-Generierung zu automatisieren. Dies ist entscheidend, um Ihre Produktdaten aktuell zu halten.
  4. **Microsoft Merchant Center überwachen:** Überprüfen Sie regelmäßig Ihr Microsoft Merchant Center-Konto auf Produktablehnungen oder Warnungen und passen Sie die Moduleinstellungen bei Bedarf an.
  5. **Produktaktualisierungen:** Wenn Sie neue Produkte hinzufügen oder wesentliche Änderungen an bestehenden vornehmen, stellen Sie sicher, dass Ihr Cron-Job läuft, oder generieren Sie den Feed manuell neu, wenn eine sofortige Aktualisierung erforderlich ist.

#### index.php (mmcfeed/controllers/admin/index.php)

Dieser Controller dient wahrscheinlich als Dashboard oder allgemeine Verwaltungsansicht für das Modul innerhalb des PrestaShop Back Office.

- **Bildschirmname & Menüpfad:** Wahrscheinlich Teil des Hauptmenüabschnitts „Microsoft Merchant Center“, möglicherweise die Standard-Landingpage.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt wahrscheinlich eine Übersicht Ihrer konfigurierten Feeds, deren letztes Generierungsdatum, Status und schnelle Links zum Bearbeiten oder Generieren an. Er könnte auch den allgemeinen Modulstatus oder wichtige Warnungen anzeigen.
- **Auswirkungen von Änderungen:** Diese Ansicht bietet einen schnellen Überblick über Ihre Feed-Einrichtung. Aktionen hier (wie das Klicken auf „Feed generieren“) lösen den Feed-Generierungsprozess aus.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm als schnelles Dashboard, um den Zustand Ihrer Produkt-Feeds zu überwachen. Wenn Sie eine Feed-Aktualisierung manuell auslösen müssen, tun Sie dies hier.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | Zielsprache | Ihre primäre Shop-Sprache | Bestimmt die Sprache für Produktnamen, Beschreibungen usw. |
|  | Zielwährung | Ihre primäre Shop-Währung | Legt die Währung für alle Preise im Feed fest. |
|  | Zielland | Ihr primärer Zielmarkt | Beeinflusst Steuer-, Versand- und länderspezifische Regeln. |
|  | Cron-URL | Vom Modul bereitgestellt | Automatisiert die Feed-Generierung in geplanten Intervallen. |
| **AdminExportProductsFeedMicrosoftController** | Feed-Name | Beschreibend (z.B. „Frankreich - FR“) | Identifiziert den spezifischen Feed. |
|  | Dateiformat | CSV, XML oder TSV | Wählen Sie basierend auf den Anforderungen des Microsoft Merchant Centers. |
|  | Kategoriezuordnung | PrestaShop der Microsoft-Taxonomie zuordnen | Stellt sicher, dass Produkte in den richtigen Shopping-Kategorien erscheinen. |
|  | Produktfilterung | Basierend auf Ihrer Strategie | Bestimmte Produkte oder Kategorien ein-/ausschließen. |
|  | Attributzuordnung | PrestaShop den Microsoft-Attributen zuordnen | Bietet detaillierte Produktinformationen für Anzeigen. |
|  | Benutzerdefinierte Labels (0-4) | Nach Bedarf für Anzeigenkampagnen | Segmentiert Produkte für Gebotsstrategien. |
|  | GTIN-Export | Aktiviert, falls verfügbar | Exportiert EAN/UPC zur Produktidentifikation. |
|  | Verfügbarkeitsdatum | Aktiviert, falls zutreffend | Exportiert das Produktverfügbarkeitsdatum für Vorbestellungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Produkte erscheinen nicht in Microsoft Shopping Ads. Was sollte ich überprüfen?**
A:

1. **Feed-Upload-Status:** Überprüfen Sie zunächst Ihr Microsoft Merchant Center-Konto, um sicherzustellen, dass Ihr Feed erfolgreich hochgeladen und ohne größere Fehler verarbeitet wurde.
2. **Produktablehnungen:** Suchen Sie im Abschnitt „Diagnosen“ des Microsoft Merchant Centers nach Produktablehnungen. Diese zeigen Ihnen genau an, warum Produkte nicht angezeigt werden. Häufige Gründe sind fehlende GTINs, falsche Bild-Links oder Richtlinienverstöße.
3. **Modulkonfiguration:** Überprüfen Sie, ob Ihre Moduleinstellungen (Sprache, Währung, Land, Kategoriezuordnung) korrekt sind und mit Ihren Microsoft Merchant Center-Kontoeinstellungen übereinstimmen.
4. **Feed-Generierung:** Stellen Sie sicher, dass der Feed vom Modul korrekt generiert wird. Versuchen Sie, ihn manuell zu generieren und die Ausgabedatei zu überprüfen.
5. **Anzeigenkampagnen:** Bestätigen Sie, dass Ihre Microsoft Ads-Kampagnen aktiv, richtig ausgerichtet und mit dem korrekten Produkt-Feed verknüpft sind.

**F: Meine Produktpreise oder Lagerbestände sind in Microsoft Shopping Ads veraltet.**
A: Dies bedeutet normalerweise, dass Ihr Produkt-Feed nicht häufig genug aktualisiert wird.

1. **Cron-Job:** Stellen Sie sicher, dass Ihr Cron-Job auf Ihrem Hosting-Server korrekt eingerichtet ist und mit der gewünschten Häufigkeit (z.B. täglich) ausgeführt wird. Das Modul bietet hierfür eine eindeutige URL.
2. **Manuelle Generierung:** Wenn Sie dringende Änderungen vorgenommen haben, können Sie den Feed manuell über die Konfigurationsseite des Moduls neu generieren und ihn erneut in das Microsoft Merchant Center hochladen (falls keine geplanten Abrufe verwendet werden).

**F: Einige meiner Produkte fehlen im Feed.**
A:

1. **Kategorieausschluss:** Überprüfen Sie, ob die Kategorien, die diese Produkte enthalten, versehentlich in den Moduleinstellungen ausgeschlossen wurden.
2. **Produktstatus:** Stellen Sie sicher, dass die Produkte in Ihrem PrestaShop-Shop aktiv, sichtbar und auf Lager sind. Produkte, die als „deaktiviert“ oder „nicht auf Lager“ (abhängig von Ihren Einstellungen) markiert sind, könnten ausgeschlossen werden.
3. **Spezifische Filter:** Überprüfen Sie alle spezifischen Produktfilter, die Sie in der Modulkonfiguration angewendet haben könnten.

**F: Wie ordne ich meine PrestaShop-Kategorien der Produkt-Taxonomie von Microsoft zu?**
A: Im Feed-Konfigurationsbildschirm des Moduls gibt es einen Abschnitt für die „Kategoriezuordnung“. Sie sehen dort typischerweise eine Liste Ihrer PrestaShop-Kategorien. Für jede müssen Sie die am besten geeignete Kategorie aus der vordefinierten Taxonomie-Liste von Microsoft auswählen. Dies ist ein entscheidender Schritt für die Anzeigenrelevanz. Nehmen Sie sich Zeit, um dies richtig zu machen.

**F: Mein benutzerdefiniertes Theme verursacht Anzeigeprobleme mit der Admin-Oberfläche des Moduls.**
A: Während das Modul im Front-Office keine Auswirkungen hat, kann seine Back-Office-Oberfläche manchmal mit stark angepassten Admin-Themes in Konflikt geraten.

1. **Cache leeren:** Versuchen Sie zunächst, Ihren PrestaShop Smarty-Cache zu leeren (Erweiterte Parameter > Leistung > Cache leeren).
2. **Standard-Theme:** Wechseln Sie vorübergehend Ihr Back-Office-Theme zum Standard-PrestaShop-Theme, um zu sehen, ob das Problem weiterhin besteht. Wenn es sich löst, liegt der Konflikt bei Ihrem benutzerdefinierten Admin-Theme.
3. **Support kontaktieren:** Wenn das Problem weiterhin besteht, sammeln Sie Screenshots und Details und kontaktieren Sie den MyPresta.eu-Support für Unterstützung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Microsoft Merchant Center Produkt-Feed` (`mmcfeed`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Admin-Controller für die Back-Office-Verwaltung und Front-Controller für die Generierung des Produkt-Feeds über Cron-Jobs nutzt. Es führt keine neuen `ObjectModel`-Klassen ein, sondern fragt bestehende PrestaShop-Produktdaten ab und formatiert sie gemäß den Spezifikationen des Microsoft Merchant Centers. Das Modul stützt sich stark auf Konfigurationswerte, die in `ps_configuration` gespeichert sind, und verwendet Smarty-Templates für die Darstellung sowohl der Admin-Oberflächen als auch potenziell Teilen der Feed-Generierungslogik (obwohl Feeds typischerweise programmatisch generiert werden).

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `mmcfeed/controllers/front/feed.php`
  - **Klassenname & Elternklasse:** `MmcfeedFeedModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist der primäre Endpunkt für die Generierung des Produkt-Feeds. Er ist so konzipiert, dass er über eine eindeutige URL (die „Cron-URL“) für die automatisierte Feed-Generierung aufgerufen wird. Er verarbeitet die Logik zum Abfragen von Produktdaten, zum Anwenden von Filter- und Zuordnungsregeln, die im Back Office definiert wurden, und zur Ausgabe des Produkt-Feeds im angegebenen Format (CSV, XML, TSV). Er rendert typischerweise keine visuelle Seite, sondern gibt Rohdaten aus.
- `mmcfeed/controllers/front/index.php`
  - **Klassenname & Elternklasse:** `MmcfeedIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist ein Platzhalter oder Fallback-Front-Controller. In vielen Modulen dient `index.php` in einem Controller-Verzeichnis als Standard oder einfacher Einstiegspunkt. Er könnte umleiten oder einfach eine leere Antwort zurückgeben, wenn keine spezifische Aktion definiert ist. Seine direkte funktionale Rolle bei der Feed-Generierung ist wahrscheinlich minimal im Vergleich zu `feed.php`.

#### Back-Office-Admin-Controller

- `mmcfeed/controllers/admin/AdminExportProductsFeedMicrosoft.php`
  - **Tab-Name und verwaltete Entität:** Verwaltet die Konfiguration und Generierung einzelner Microsoft Merchant Center Produkt-Feeds. Erstellt einen neuen Menüpunkt im PrestaShop Back Office.
  - **Verantwortlichkeit:** Dieser Controller verarbeitet die CRUD-Operationen für Produkt-Feed-Konfigurationen. Er zeigt die Liste der konfigurierten Feeds an, ermöglicht das Hinzufügen neuer Feeds, das Bearbeiten bestehender Feeds und das Auslösen ihrer Generierung. Er verarbeitet Formularübermittlungen zur Definition von Feed-spezifischen Einstellungen wie Zielland, Sprache, Währung, Dateiformat, Kategoriezuordnung, Produktfilterung und Attributzuordnung (z.B. `gtin`, `identifier_exists`, `title`, `availability`, `brand`, `link`, `image_link`, `description`, `product_type`, `condition`, `price`, `sale_price`, `tax rate`, `custom_label_0`, `google_product_category`). Er interagiert mit `ps_configuration` zur Speicherung dieser Einstellungen und orchestriert den Datenabruf und die Formatierung für den Feed-Generierungsprozess.
- `mmcfeed/controllers/admin/index.php`
  - **Tab-Name und verwaltete Entität:** Wahrscheinlich ein Dashboard oder eine Übersichtsseite für das Modul im PrestaShop Back Office.
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Haupteinstiegspunkt für die Admin-Oberfläche des Moduls und bietet eine Zusammenfassung der konfigurierten Feeds, deren Status und schnelle Aktionen. Er könnte ein Dashboard-ähnliches Template (`dashboard.tpl`) rendern, um einen Überblick über die Modulaktivität zu geben.

### 4.3 Kernklassen & Modelle (`classes/`)

Die bereitgestellten Informationen zeigen keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/`. Dies deutet darauf hin, dass das Modul hauptsächlich durch direkte Abfragen der PrestaShop-Kernklassen `Product`, `Category`, `Language`, `Currency` usw. `ObjectModel` und `ps_configuration` für seine Einstellungen arbeitet. Die Logik für die Datenverarbeitung und Feed-Generierung ist wahrscheinlich in der Hauptmoduldatei `mmcfeed.php` und den Admin-/Front-Controllern gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

- `mmcfeed/lib/searchTool/views/js/autocomplete.js`
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität, wahrscheinlich zum Suchen von Produkten, Kategorien oder Attributen innerhalb der Konfigurationsformulare des Moduls. Dies verbessert die Benutzererfahrung beim Zuordnen von Kategorien oder Filtern von Produkten. Es bindet an Eingabefelder und führt AJAX-Anfragen aus, um Vorschläge abzurufen.
- `mmcfeed/views/js/admin-app.js`
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Dies ist die Haupt-JavaScript-Datei für die Back-Office-Oberfläche des Moduls. Sie verarbeitet verschiedene interaktive Elemente, Formularvalidierungen, dynamisches Laden von Inhalten (z.B. Fancybox-Modals für die Kategorieauswahl) und AJAX-Aufrufe im Zusammenhang mit dem Speichern von Konfigurationen oder dem Auslösen der Feed-Generierung. Sie bindet wahrscheinlich Event-Listener an Schaltflächen, Auswahllisten und Eingabefelder innerhalb der Formulare des `AdminExportProductsFeedMicrosoft`-Controllers.

### 4.5 CSS-Stylesheets (`views/css/`)

- `mmcfeed/lib/searchTool/views/css/autocomplete.css`
  - **Umfang:** Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit:** Gestaltet die Autocomplete-Dropdowns und Eingabefelder, die vom `autocomplete.js`-Skript verwendet werden, um ein konsistentes und benutzerfreundliches Erscheinungsbild im PrestaShop Back Office zu gewährleisten.
- `mmcfeed/views/admin-theme.css`
  - **Umfang:** Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit:** Bietet allgemeine Styling-Anpassungen und Überschreibungen für die Back-Office-Seiten des Moduls, um sich nahtlos in das PrestaShop-Admin-Theme zu integrieren. Es könnte Stile für Layout, Schaltflächen, Tabellen und Formularelemente definieren, die spezifisch für das Modul sind.
- `mmcfeed/views/css/admin-app.css`
  - **Umfang:** Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit:** Enthält spezifische Stile für die benutzerdefinierten UI-Komponenten und Layouts des Moduls im Admin-Panel, wie z.B. Kategoriezuordnungs-Oberflächen, Produktausschlusslisten oder Dashboard-Elemente. Es arbeitet in Verbindung mit `admin-theme.css`, um die visuelle Identität des Moduls im Back Office zu gewährleisten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, was darauf hindeutet, dass das Modul keine Inhalte direkt in Standard-Front-Office-Hooks rendert.
- **Admin-Templates (`views/templates/admin/`)**:
  - `mmcfeed/views/templates/admin/dashboard.tpl`: Wahrscheinlich das Haupt-Dashboard-Template, das von `controllers/admin/index.php` gerendert wird und eine Übersicht über das Modul und seine konfigurierten Feeds bietet.
  - `mmcfeed/views/templates/admin/feeds.tpl`: Rendert wahrscheinlich die Liste der Produkt-Feeds, die vom `AdminExportProductsFeedMicrosoftController` verwaltet werden, und zeigt deren Status, letztes Generierungsdatum und Aktionen an.
  - `mmcfeed/views/templates/admin/form-chrome.tpl`: Ein generisches Template zum Umhüllen von Formularen in der PrestaShop-Admin-Oberfläche, das ein konsistentes Styling und eine konsistente Struktur bietet (z.B. Header, Footer, Speicher-Schaltflächen).
  - `mmcfeed/views/templates/admin/layout.tpl`: Ein Basis-Layout-Template für die Admin-Seiten des Moduls, das die Gesamtstruktur, einschließlich Header, Menüs und Inhaltsbereiche, definiert.
- **Weitere Templates (`views/`)**:
  - `mmcfeed/lib/searchTool/views/scripts.tpl`: Enthält JavaScript-Code oder Skript-Inklusionen im Zusammenhang mit der Suchwerkzeug-/Autocomplete-Funktionalität.
  - `mmcfeed/views/categories-fancybox.tpl`: Rendert den Inhalt für ein Fancybox-Modal, das für die Kategorieauswahl oder -zuordnung verwendet wird und wahrscheinlich eine baumartige Struktur für eine einfache Navigation bietet.
  - `mmcfeed/views/category_taxonomy.tpl`: Ein partielles Template, das in `categories-fancybox.tpl` oder dem Haupt-Feed-Konfigurationsformular verwendet wird, um die Zuordnung von PrestaShop-Kategorien zur Microsoft-Taxonomie anzuzeigen und zu verwalten.
  - `mmcfeed/views/exclude-products.tpl`: Rendert die Oberfläche zum Auswählen und Verwalten von Produkten, die aus dem Feed ausgeschlossen werden sollen.
  - `mmcfeed/views/google_lang_links.tpl`: Dieser Template-Name ist für ein Microsoft-Modul merkwürdig. Es könnte ein Überbleibsel eines Google Merchant Center-Moduls oder eine generische Komponente zur Handhabung sprachspezifischer Links sein, möglicherweise für die Feed-URLs selbst.
  - `mmcfeed/views/returnAlert.tpl`: Ein generisches Template zum Anzeigen von Erfolgs- oder Fehlermeldungen an den Benutzer im Back Office.
  - `mmcfeed/views/script-fancybox.tpl`: Enthält JavaScript-Code oder Skript-Inklusionen speziell für die Fancybox-Bibliothek, die für modale Popups verwendet wird.
  - `mmcfeed/views/script.tpl`: Ein allgemeines Skript-Inklusionstemplate, möglicherweise für modulweite JavaScript-Variablen oder Initialisierungen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen basierend auf den bereitgestellten Informationen.
  - Alle Modulkonfigurationen werden in der Tabelle `ps_configuration` gespeichert, wobei die Schlüssel mit `mmc_` präfixiert sind (z.B. `mmc_pf_tree`, `mmc_mmcfeed_products`, `mmc_export_size_attribute`, `mmc_export_exclude_categories`, `mmc_export_availability_date`).
  - Es interagiert mit Standard-PrestaShop-Tabellen wie `ps_product`, `ps_product_lang`, `ps_category`, `ps_category_lang`, `ps_image`, `ps_stock_available`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_value`, `ps_manufacturer`, `ps_tax_rule` usw., um Produktdaten abzurufen.
- **Registrierte Hooks-Tabelle**:
  Das Modul verwendet hauptsächlich Back-Office-Hooks für seine Verwaltungsoberfläche und potenziell `action`-Hooks für die interne Logik. Front-Office-Hooks werden nicht zum Rendern von Inhalten verwendet, aber der Front-Controller `feed.php` des Moduls fungiert als direkter Endpunkt für externe Dienste (wie Cron-Jobs).

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt von Front-Office-Seiten. | *Nicht zum Rendern von Inhalten verwendet.* Falls registriert, wahrscheinlich für internes JS/CSS-Laden, aber die primäre Funktion des Moduls ist die Feed-Generierung, nicht die Front-Office-Anzeige. |
| `displayRightColumn` | In der rechten Spalte von Front-Office-Seiten. | *Nicht zum Rendern von Inhalten verwendet.* |
| `displayLeftColumn` | In der linken Spalte von Front-Office-Seiten. | *Nicht zum Rendern von Inhalten verwendet.* |
| `displayFooter` | Im Footer von Front-Office-Seiten. | *Nicht zum Rendern von Inhalten verwendet.* |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | *Potenziell verwendet*, um einen Tab oder Abschnitt für produktspezifische Feed-Ausschlüsse oder Überschreibungen hinzuzufügen. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller initialisiert wird und bevor seine Medien (JS/CSS) geladen werden. | Wird verwendet, um modulspezifisches JavaScript (`admin-app.js`, `autocomplete.js`) und CSS (`admin-app.css`, `admin-theme.css`, `autocomplete.css`) für die Back-Office-Oberfläche zu registrieren. |
| `actionModuleInstall` | Während der Modulinstallation. | Zum Erstellen von Konfigurationseinträgen in `ps_configuration` und potenziell zum Registrieren von Admin-Tabs. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Zum Bereinigen von Konfigurationseinträgen und Entfernen von Admin-Tabs. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | *Unwahrscheinlich für dieses Modul.* Falls vorhanden, wäre es zur Verfolgung von Konversionen oder zur Aktualisierung von Feed-Daten basierend auf Verkäufen, aber keine Kernfunktion für einen Feed-Generator. |
| `actionProductUpdate` | Nachdem ein Produkt aktualisiert wurde. | *Potenziell verwendet*, um ein Flag für die Feed-Regenerierung auszulösen oder interne Caches zu aktualisieren, falls das Modul solche verwaltet. |
| `actionProductAdd` | Nachdem ein neues Produkt hinzugefügt wurde. | *Potenziell verwendet*, um ein Flag für die Feed-Regenerierung auszulösen oder interne Caches zu aktualisieren. |
| `displayAdminNavBarBefore` | Vor der Hauptnavigationsleiste im Back Office. | *Potenziell verwendet*, um einen Schnelllink oder eine Benachrichtigung im Zusammenhang mit dem Modul hinzuzufügen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu bietet dedizierten Support für alle gekauften Module, um sicherzustellen, dass Ihr Shop aktuell und funktionsfähig bleibt.
