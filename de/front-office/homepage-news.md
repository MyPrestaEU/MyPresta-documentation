---
title: "Homepage-News – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Homepage-News“ von MyPresta.eu."
sidebar:
  label: "Homepage-News – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homepage news auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homepage-news.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homepage-news/)
>
> ---


# Homepage-News

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Homepage-News“, auf dem Sie steuern, wie Ihre Nachrichtenartikel auf der Startseite angezeigt werden.

#### **Kategorie der CMS-Seiten auswählen**

- **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü ermöglicht es Ihnen, auszuwählen, welche spezifische CMS-Kategorie als Quelle für Ihre Homepage-Nachrichten verwendet werden soll. Nur CMS-Seiten, die zu dieser ausgewählten Kategorie gehören, werden vom Modul zur Anzeige berücksichtigt.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn eine Kategorie ausgewählt ist:* Das Modul ruft Nachrichtenartikel nur von CMS-Seiten innerhalb dieser Kategorie ab und zeigt sie an.
  - *Wenn keine Kategorie ausgewählt ist (oder eine ungeeignete):* Das Modul zeigt möglicherweise keine Nachrichten an, oder es zeigt Seiten an, die Sie nicht als Nachrichtenartikel vorgesehen haben.
- **Empfohlener Wert:** Wählen Sie die CMS-Kategorie, die Sie speziell für Ihre Nachrichtenartikel erstellt oder bestimmt haben (z.B. „News“, „Blog“, „Updates“).
- **Händlerszenario / Beispiel:** Sie haben eine CMS-Kategorie namens „Unternehmensnachrichten“ erstellt und mehrere CMS-Seiten hinzugefügt, wie „Neues Produkt eingeführt“, „Sommer-Sale angekündigt“ und „Feiertagsöffnungszeiten“. Durch die Auswahl von „Unternehmensnachrichten“ hier erscheinen nur diese Seiten als Nachrichten auf Ihrer Startseite.

#### **Vollständigen Inhalt der neuesten CMS-Seite anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob der allerneueste Nachrichtenartikel (CMS-Seite) aus Ihrer ausgewählten Kategorie mit seinem vollständigen Inhalt direkt auf der Startseite angezeigt wird.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Der vollständige Inhalt des neuesten Nachrichtenartikels wird auf Ihrer Startseite sichtbar sein und sofortige Informationen liefern, ohne dass ein Klick erforderlich ist.
  - *Wenn deaktiviert (NEIN):* Nur der Titel, die Miniatur und eine kurze Beschreibung (falls konfiguriert) des neuesten Nachrichtenartikels werden angezeigt, ähnlich wie bei anderen Miniaturen. Kunden müssen klicken, um den vollständigen Inhalt zu lesen.
- **Empfohlener Wert:** „JA“, wenn Sie Ihre wichtigsten Nachrichten sofort hervorheben möchten; „NEIN“, wenn Sie einen kompakteren Nachrichtenbereich bevorzugen, bei dem alle Artikel einen Klick erfordern.
- **Händlerszenario / Beispiel:** Sie haben eine wichtige Ankündigung, wie eine neue Geschäftseröffnung. Wenn Sie dies aktivieren, stellen Sie sicher, dass Kunden die vollständigen Details sofort sehen. Wenn Sie eine sauberere Startseite bevorzugen, können Sie es deaktivieren und nur Auszüge anzeigen.

#### **Miniaturen von CMS-Seiten anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob kleinere, zusammengefasste Versionen (Miniaturen) Ihrer Nachrichtenartikel auf der Startseite angezeigt werden. Diese Miniaturen enthalten typischerweise einen Titel, ein kleines Bild und eine kurze Beschreibung.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul zeigt eine Reihe von Miniatur-Nachrichtenblöcken an, die jeweils eine aktuelle CMS-Seite aus Ihrer ausgewählten Kategorie repräsentieren.
  - *Wenn deaktiviert (NEIN):* Es werden keine Miniaturen angezeigt. Wenn „Vollständigen Inhalt der neuesten CMS-Seite anzeigen“ ebenfalls deaktiviert ist, werden überhaupt keine Nachrichten angezeigt.
- **Empfohlener Wert:** „JA“, um einen Überblick über mehrere Nachrichtenartikel zu geben und zur Erkundung anzuregen.
- **Händlerszenario / Beispiel:** Sie möchten die neuesten 3-5 Nachrichtenartikel anzeigen, um Kunden einen schnellen Überblick über aktuelle Updates zu geben. Das Aktivieren von Miniaturen erreicht dies.

#### **Anzahl der anzuzeigenden Miniaturen**

- **Was diese Einstellung bewirkt:** Wenn „Miniaturen von CMS-Seiten anzeigen“ aktiviert ist, bestimmt dieses Eingabefeld, wie viele der neuesten Nachrichtenartikel-Miniaturen auf Ihrer Startseite angezeigt werden.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf eine höhere Zahl eingestellt (z.B. 5):* Es werden mehr Nachrichtenartikel-Miniaturen sichtbar sein, was einen breiteren Überblick bietet.
  - *Wenn auf eine niedrigere Zahl eingestellt (z.B. 2):* Es werden weniger Miniaturen angezeigt, wodurch der Nachrichtenbereich prägnanter wird.
- **Empfohlener Wert:** 3 bis 5, abhängig von Ihrem Startseiten-Layout und wie viel Platz Sie den Nachrichten widmen möchten.
- **Händlerszenario / Beispiel:** Sie haben viele Nachrichten, möchten aber Ihre Startseite sauber halten. Wenn Sie dies auf „3“ setzen, werden nur die drei neuesten Artikel hervorgehoben.

#### **Anzahl der Zeichen, die in der Beschreibung für Miniaturen verwendet werden**

- **Was diese Einstellung bewirkt:** Dieses Eingabefeld steuert die Länge der Kurzbeschreibung (Auszug), die in jeder Nachrichtenminiatur angezeigt wird.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf eine höhere Zahl eingestellt (z.B. 200):* Die Beschreibungen in den Miniaturen werden länger sein und mehr Kontext bieten.
  - *Wenn auf eine niedrigere Zahl eingestellt (z.B. 50):* Die Beschreibungen werden kürzer sein, wodurch die Miniaturen kompakter werden.
- **Empfohlener Wert:** 100 bis 150 Zeichen, genug, um eine gute Zusammenfassung zu geben, ohne die Miniatur zu überladen.
- **Händlerszenario / Beispiel:** Sie möchten Kunden in der Miniatur gerade genug Informationen geben, um ihr Interesse zu wecken. Wenn Sie dies auf „120“ setzen, wird ein prägnanter, aber informativer Ausschnitt gewährleistet.

#### **Stil der Miniaturen**

- **Was diese Einstellung bewirkt:** Diese Option (wahrscheinlich ein Dropdown-Menü oder Radio-Buttons) ermöglicht es Ihnen, das visuelle Layout oder den Stil auszuwählen, wie die Nachrichtenminiaturen auf Ihrer Startseite präsentiert werden. Die verfügbaren Stile könnten Optionen wie ein Raster, eine Liste oder ein Karussell umfassen.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „Raster“ eingestellt:* Miniaturen könnten in Zeilen und Spalten erscheinen, geeignet für die kompakte Anzeige mehrerer Elemente.
  - *Wenn auf „Liste“ eingestellt:* Miniaturen könnten untereinander erscheinen, gut für detailliertere Beschreibungen.
  - *Wenn auf „Karussell“ eingestellt:* Miniaturen könnten horizontal gleiten, Platz sparen und Benutzern ermöglichen, mehr Elemente zu durchsuchen.
- **Empfohlener Wert:** Experimentieren Sie mit den verfügbaren Stilen, um zu sehen, welcher am besten zum Design Ihres Themes und Ihrer gewünschten Startseitenästhetik passt.
- **Händlerszenario / Beispiel:** Ihre Startseite hat begrenzten horizontalen Platz. Die Wahl eines „Karussell“-Stils ermöglicht es Ihnen, viele Nachrichtenartikel anzuzeigen, ohne die Seite zu lang zu machen. Wenn Sie viel Platz haben, könnte ein „Raster“ ansprechender aussehen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Kategorie der CMS-Seiten auswählen | Ihre zugewiesene „News“-CMS-Kategorie | Definiert, welche CMS-Seiten als Nachrichtenquelle dienen. |
| Modulkonfiguration | Vollständigen Inhalt der neuesten CMS-Seite anzeigen | JA | Zeigt den vollständigen Inhalt des neuesten Artikels direkt auf der Startseite an. |
| Modulkonfiguration | Miniaturen von CMS-Seiten anzeigen | JA | Ermöglicht die Anzeige von zusammengefassten Nachrichtenblöcken. |
| Modulkonfiguration | Anzahl der anzuzeigenden Miniaturen | 3-5 | Steuert, wie viele aktuelle Nachrichtenminiaturen angezeigt werden. |
| Modulkonfiguration | Anzahl der Zeichen, die in der Beschreibung für Miniaturen verwendet werden | 100-150 | Legt die Länge des Textauszugs in Miniaturen fest. |
| Modulkonfiguration | Stil der Miniaturen | Variiert (z.B. Raster, Liste, Karussell) | Bestimmt das visuelle Layout der Nachrichtenminiaturen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Nachrichtenbereich wird auf der Startseite nicht angezeigt. Was sollte ich überprüfen?**
A:

1.  **Modul aktiviert:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Homepage-News“ installiert und aktiviert ist.
2.  **CMS-Kategorie ausgewählt:** Überprüfen Sie in der Modulkonfiguration, ob Sie eine gültige CMS-Kategorie unter „Kategorie der CMS-Seiten auswählen“ ausgewählt haben.
3.  **CMS-Seiten vorhanden:** Stellen Sie sicher, dass tatsächlich CMS-Seiten innerhalb der ausgewählten Kategorie veröffentlicht sind.
4.  **Sichtbarkeitseinstellungen:** Überprüfen Sie, ob „Miniaturen von CMS-Seiten anzeigen“ und/oder „Vollständigen Inhalt der neuesten CMS-Seite anzeigen“ in der Modulkonfiguration aktiviert sind. Wenn beide deaktiviert sind, wird nichts angezeigt.
5.  **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**).

**F: Die Bilder für meine Nachrichtenminiaturen werden nicht angezeigt.**
A: Das Modul versucht typischerweise, das erste Bild aus dem Inhalt Ihrer CMS-Seite zu extrahieren.

1.  **Bild auf CMS-Seite:** Stellen Sie sicher, dass der Inhalt Ihrer CMS-Seite tatsächlich ein Bild enthält.
2.  **Bildpfad:** Überprüfen Sie, ob der Bildpfad auf Ihrer CMS-Seite korrekt ist und die Bilddatei auf Ihrem Server existiert.
3.  **Theme-Kompatibilität:** Einige benutzerdefinierte Themes können die Bildwiedergabe beeinträchtigen. Wenn alles andere fehlschlägt, wenden Sie sich an Ihren Theme-Entwickler oder den MyPresta.eu-Support.

**F: Wie übersetze ich die Nachrichtentitel und Beschreibungen?**
A: Die Nachrichtentitel und Inhalte stammen direkt von Ihren CMS-Seiten.

1.  **CMS-Seiten-Übersetzungen:** Gehen Sie zu **Design > Seiten** (oder **CMS** in älteren Versionen) und bearbeiten Sie Ihre Nachrichten-CMS-Seite.
2.  **In allen Sprachen bearbeiten:** Stellen Sie für jede unterstützte Sprache sicher, dass Sie den übersetzten Titel und Inhalt für diese spezifische CMS-Seite bereitgestellt haben. Das Modul zeigt automatisch die korrekte Sprache basierend auf der vom Kunden ausgewählten Shop-Sprache an.

**F: Der Nachrichtenbereich sieht auf meiner Startseite seltsam oder falsch ausgerichtet aus.**
A: Dies ist oft ein CSS-Konflikt mit dem Theme Ihres Shops.

1.  **Cache leeren:** Beginnen Sie immer damit, Ihren PrestaShop-Cache zu leeren (**Erweiterte Einstellungen > Leistung > Cache leeren**).
2.  **Modulkonfiguration:** Überprüfen Sie, ob eine Änderung der Einstellung „Stil der Miniaturen“ hilft.
3.  **Theme-Anpassung:** Das CSS Ihres Themes könnte die Stile des Moduls überschreiben. Möglicherweise müssen Sie einen Webentwickler konsultieren, um benutzerdefiniertes CSS zu Ihrem Theme hinzuzufügen, um das Erscheinungsbild anzupassen. Der MyPresta.eu-Support kann Anleitungen geben, aber keine kundenspezifische Theme-Entwicklung anbieten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Homepage-News“ (`hnews`) ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, Inhalte von bestehenden CMS-Seiten auf der Front-Office-Startseite anzuzeigen. Es nutzt die `Module`-Klasse von PrestaShop und Standard-Hooks. Die Modullogik befindet sich hauptsächlich in seiner Haupt-PHP-Datei, `hnews.php`, die die Konfiguration, Hook-Registrierung und Datenabfrage handhabt. Es führt keine benutzerdefinierten Controller oder komplexen ObjectModels ein, sondern verlässt sich stattdessen auf die nativen `CMSCategory`- und `CMS`-Klassen von PrestaShop für die Daten.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Anzeigelogik des Moduls wird vollständig von seiner `hookDisplayHome`-Methode innerhalb von `hnews.php` und über ein Smarty-Template gerendert.
- **Back-Office-Admin-Controller**: Keine. Alle Konfigurationen werden über die `getContent()`-Methode der Hauptmodulklasse verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- Dieses Modul führt keine benutzerdefinierten Klassen oder ObjectModels ein. Es fragt die Datenbank direkt ab oder verwendet die Kernklassen `CMSCategory` und `CMS` von PrestaShop, um Daten abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

- In diesem Modul sind keine benutzerdefinierten JavaScript-Dateien enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `hnews/views/admin/css/hnews.css`:
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Haupt-UI-Komponenten:** Enthält wahrscheinlich Stile, die spezifisch für die Konfigurationsseite des Moduls sind, um ein konsistentes und lesbares Layout innerhalb des PrestaShop Back Office zu gewährleisten.
  - **Wichtige CSS-Klassenselektoren:** Kann Stile für Formularelemente, Beschriftungen und spezifische Container enthalten, die in `getContent()` verwendet werden.
- `hnews/views/css/hnews.css`:
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Haupt-UI-Komponenten:** Gestaltet den Nachrichtenbereich, der auf der Startseite angezeigt wird, einschließlich des Hauptnachrichtenartikels (wenn der vollständige Inhalt angezeigt wird) und der einzelnen Nachrichtenminiaturen.
  - **Wichtige CSS-Klassenselektoren:** Enthält Selektoren für den Hauptnachrichtencontainer, einzelne Miniaturblöcke, Titel, Beschreibungen und Bilder. Entwickler können diese Klassen in der `custom.css` oder `theme.css` ihres Themes überschreiben, um sie an das Design des Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `hnews/views/hnews.tpl`: Dies ist das primäre Front-Office-Template.
    - **Hook:** Wird in `displayHome` gerendert.
    - **Visueller Block:** Gibt den gesamten Nachrichtenbereich auf der Startseite aus, einschließlich des vollständigen Inhalts des neuesten Nachrichtenartikels (falls aktiviert) und der Liste der Nachrichtenminiaturen. Es iteriert durch die Nachrichtenartikel, die von der PHP-Logik des Moduls übergeben werden.
- **Admin-Templates (`views/templates/admin/`)**:
  - `hnews/views/admin/elements.tpl`:
    - **Hook:** Nicht direkt gehookt, aber von der `getContent()`-Methode in `hnews.php` inkludiert/gerendert.
    - **Visueller Block:** Rendert die Konfigurationsformular-Elemente für das Modul im PrestaShop Back Office. Dies umfasst typischerweise das Dropdown-Menü für CMS-Kategorien, Schalter für Anzeigeoptionen und Eingabefelder für Anzahlen und Zeichenbegrenzungen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `HNEWS_ID_CMSCAT`, `HNEWS_NB_MIN`, `HNEWS_LATEST`, `HNEWS_SIZE_MIN`, `HNEWS_CHR_MIN`, `HNEWS_MINIATURES`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHome` | Rendert Inhalte im Hauptbereich der Startseite. | Zeigt den Nachrichtenbereich mit den neuesten CMS-Seiten an. |
| `displayHeader` | Wird im `<head>`-Bereich der Front-Office-Seite ausgeführt. | Potenziell zum Laden von Front-Office-CSS- oder JS-Assets verwendet (obwohl kein JS vorhanden ist, wird CSS geladen). |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (CSS/JS) setzt. | Wird zum Laden von Back-Office-CSS für die Konfigurationsseite des Moduls verwendet. |
| `header` | Ähnlich wie `displayHeader`, oft zum Laden von Assets verwendet. | Potenziell zum Laden von Front-Office-CSS- oder JS-Assets verwendet. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Homepage-News“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Fragen oder Problemen im Zusammenhang mit dem Modul zur Verfügung.
