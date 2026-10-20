---
title: "Horizontales Top-Menü mit Dropdowns – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Horizontales Top-Menü mit Dropdowns' von MyPresta.eu."
sidebar:
  label: "Horizontales Top-Menü mit Dropdowns – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Top horizontal menu with dropdowns auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/top-horizontal-menu-with-dropdowns.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/top-horizontal-menu-with-dropdowns/)
>
> ---


# Horizontales Top-Menü mit Dropdowns

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sollten in jeder kompatiblen Hosting-Umgebung verfügbar sein.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Einstellungen des Moduls zuzugreifen. Dieser Bildschirm ermöglicht es Ihnen, die Elemente zu verwalten, die in Ihrem horizontalen Top-Menü erscheinen, und die Suchleiste zu konfigurieren.

Die Konfigurationsseite ist in zwei Hauptabschnitte unterteilt: **Menüpunkte** und **Suchleiste**.

#### 2.1.1 Verwaltung der Menüpunkte

Dieser Abschnitt ermöglicht es Ihnen, zu definieren, welche Elemente in Ihrem Hauptnavigationsmenü erscheinen. Sie können Links zu Kategorien, CMS-Seiten, Herstellern, Lieferanten oder benutzerdefinierten URLs hinzufügen.

- **Hinzufügen eines neuen Menüpunkts:**

  - **Bezeichnung:** Dies ist der Text, der in Ihrem Menü angezeigt wird (z. B. „Neuheiten“, „Sommerkollektion“, „Über uns“). Sie können für jede Sprache, die Ihr Shop unterstützt, unterschiedliche Bezeichnungen eingeben.
    - *Auswirkung der Änderung:* Ändert direkt den sichtbaren Text des Menüpunkts für Kunden.
    - *Empfohlener Wert:* Klarer, prägnanter und beschreibender Text, der das Ziel des Links genau wiedergibt.
    - *Händlerszenario:* Sie möchten einen Link zu Ihrer Seite „Kontakt“ hinzufügen. Sie würden hier „Kontakt“ eingeben.
  - **Link:** Dies ist die URL, auf die der Menüpunkt verweisen wird. Sie können aus einer Liste bestehender Kategorien, CMS-Seiten, Hersteller oder Lieferanten auswählen oder eine benutzerdefinierte URL eingeben.
    - *Auswirkung der Änderung:* Bestimmt, wohin der Kunde geleitet wird, wenn er auf diesen Menüpunkt klickt.
    - *Empfohlener Wert:* Stellen Sie immer sicher, dass der Link gültig ist und auf die richtige Seite verweist. Für interne Seiten verwenden Sie die bereitgestellten Auswahlwerkzeuge. Für externe Links stellen Sie sicher, dass die vollständige URL (z. B. `https://example.com/blog`) eingegeben wird.
    - *Händlerszenario:* Sie möchten auf Ihre Kategorie „T-Shirts“ verlinken. Sie würden „T-Shirts“ aus dem Dropdown-Menü der Kategorien auswählen. Wenn Sie auf einen externen Blog verlinken möchten, würden Sie die vollständige Blog-URL eingeben.
  - **Neues Fenster:** Ein Umschalter (Ja/Nein), der bestimmt, ob der Link in einem neuen Browser-Tab oder -Fenster geöffnet wird.
    - *Wenn aktiviert (Ja):* Der Link wird in einem neuen Tab geöffnet, wobei die aktuelle Seite Ihres Shops im ursprünglichen Tab geöffnet bleibt.
    - *Wenn deaktiviert (Nein):* Der Link wird im selben Tab geöffnet, wodurch der Kunde von der aktuellen Seite weg navigiert wird.
    - *Empfohlener Wert:* „Ja“ für externe Links (z. B. ein Blog, Social-Media-Profil), um Kunden in Ihrem Shop zu halten. „Nein“ für interne Links (Kategorien, Produkte, CMS-Seiten), um einen natürlichen Browsing-Fluss innerhalb Ihrer Website aufrechtzuerhalten.
    - *Händlerszenario:* Sie verlinken auf Ihre Facebook-Seite. Stellen Sie „Neues Fenster“ auf „Ja“, damit Kunden leicht zu Ihrem Shop zurückkehren können.
- **Verwaltung bestehender Menüpunkte:**

  - Das Modul zeigt eine Liste Ihrer aktuellen Menüpunkte an. Sie können Elemente per Drag & Drop neu anordnen, was sich direkt auf deren Anzeigereihenfolge im Front Office auswirkt.
  - Sie können auf „Bearbeiten“ klicken, um die Bezeichnung, den Link oder die Einstellung für ein neues Fenster eines bestehenden Elements zu ändern.
  - Sie können auf „Löschen“ klicken, um ein Element aus dem Menü zu entfernen.
    - *Auswirkung der Änderungen:* Das Neuordnen, Bearbeiten oder Löschen von Elementen aktualisiert sofort die Menüstruktur und das Erscheinungsbild in Ihrem Live-Shop.
    - *Empfohlener Arbeitsablauf:* Überprüfen Sie regelmäßig Ihre Menüstruktur, um sicherzustellen, dass sie logisch und aktuell ist. Priorisieren Sie wichtige Kategorien oder Aktionen, indem Sie sie früher im Menü platzieren.

#### 2.1.2 Konfiguration der Suchleiste

Dieser Abschnitt steuert die Sichtbarkeit der Suchleiste in Ihrem Top-Menü.

- **Suchleiste:** Ein Umschalter (Aktiviert/Deaktiviert), um die Suchleiste anzuzeigen oder auszublenden.
  - *Wenn aktiviert (Aktiviert):* Ein Suchfeld wird in oder in der Nähe Ihres horizontalen Top-Menüs angezeigt, sodass Kunden schnell nach Produkten suchen können.
  - *Wenn deaktiviert (Deaktiviert):* Die Suchleiste wird aus dem Top-Menübereich ausgeblendet.
  - *Empfohlener Wert:* „Aktiviert“. Eine Suchleiste ist ein entscheidendes Navigationswerkzeug für die meisten E-Commerce-Shops, insbesondere für solche mit einem großen Produktkatalog. Sie verbessert das Benutzererlebnis erheblich.
  - *Händlerszenario:* Sie möchten, dass Kunden Produkte einfach durch Eingabe von Schlüsselwörtern finden können. Aktivieren Sie diese Einstellung. Wenn Ihr Shop sehr klein ist und nur wenige Produkte hat, könnten Sie erwägen, sie zu deaktivieren, um Platz zu sparen, dies wird jedoch im Allgemeinen nicht empfohlen.

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | **Menüpunkte** | | |
| | Bezeichnung | N/A | Text, der für den Menüpunkt angezeigt wird. |
| | Link | N/A | URL, auf die der Menüpunkt verweist. |
| | Neues Fenster | Nein (für interne Links), Ja (für externe Links) | Bestimmt, ob der Link in einem neuen Tab geöffnet wird. |
| | Neuordnung | N/A | Ändert die Anzeigereihenfolge der Menüpunkte. |
| | Bearbeiten/Löschen | N/A | Ändert oder entfernt bestehende Menüpunkte. |
| Modul-Konfigurationsseite | **Suchleiste** | Aktiviert | Zeigt/verbirgt das Suchfeld im Top-Menü. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Menüänderungen werden im Front Office nicht angezeigt.**
A: Nach Änderungen in der Modulkonfiguration müssen Sie möglicherweise Ihren PrestaShop-Cache leeren.
- Gehen Sie zu **Erweiterte Einstellungen > Leistung**.
- Klicken Sie oben rechts auf die Schaltfläche „Cache leeren“.
- Leeren Sie auch den Cache Ihres Browsers (Strg+F5 oder Cmd+R), um sicherzustellen, dass Sie die neueste Version Ihrer Website sehen.

**F2: Die Dropdowns sehen seltsam aus oder werden mit meinem benutzerdefinierten Theme nicht korrekt angezeigt.**
A: Dieses Modul modifiziert das Standard-PrestaShop-Top-Menü. Benutzerdefinierte Themes haben oft ihr eigenes spezifisches CSS (Styling) für das Menü.
- **Lösung:** Das Modul enthält sein eigenes CSS, um die Dropdowns zu aktivieren. Das CSS Ihres Themes könnte es überschreiben oder damit in Konflikt stehen. Möglicherweise benötigen Sie einen Webentwickler, um das CSS zu überprüfen und die Stile Ihres Themes oder die Stile des Moduls anzupassen, um die Kompatibilität sicherzustellen.
- **Temporäre Überprüfung:** Versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme (z. B. Classic) zu wechseln, um zu sehen, ob die Dropdowns dort funktionieren. Wenn ja, bestätigt dies einen Theme-bezogenen CSS-Konflikt.

**F3: Wie übersetze ich meine Menüpunktbezeichnungen in andere Sprachen?**
A: Wenn Sie einen Menüpunkt hinzufügen oder bearbeiten, sehen Sie neben dem Feld „Bezeichnung“ eine Sprachauswahl.
- Klicken Sie auf das Flaggensymbol, um zu einer anderen Sprache zu wechseln.
- Geben Sie die übersetzte Bezeichnung für diese spezifische Sprache ein.
- Wiederholen Sie dies für alle Sprachen, die Ihr Shop unterstützt.

**F4: Kann ich mehrere Ebenen von Dropdowns haben (z. B. Kategorie > Unterkategorie > Unter-Unterkategorie)?**
A: Das Modul erweitert das Standard-PrestaShop-Menü, das typischerweise ein oder zwei Ebenen von Dropdowns effektiv unterstützt. Obwohl es technisch möglich ist, Elemente zu verschachteln, können zu viele Ebenen für Benutzer umständlich werden.
- **Best Practice:** Streben Sie maximal zwei Ebenen an (Hauptelement > Dropdown-Elemente). Für tiefere Hierarchien sollten Sie Kategorie-Landingpages oder Facettennavigation auf Kategorieseiten verwenden, anstatt übermäßig komplexe Dropdown-Menüs.

**F5: Die Suchleiste ist aktiviert, wird aber nicht angezeigt.**
A:
- Stellen Sie zunächst sicher, dass die Einstellung „Suchleiste“ in der Modulkonfiguration tatsächlich „Aktiviert“ ist.
- Zweitens prüfen Sie, ob Ihr Theme einen spezifischen Hook oder ein Styling für die Suchleiste im Header hat. Einige Themes platzieren die Suchleiste möglicherweise an einem anderen Ort oder erfordern eine spezifische Konfiguration innerhalb des Themes selbst.
- Wenn das Problem weiterhin besteht, leeren Sie Ihren Cache (wie in F1 beschrieben).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Horizontales Top-Menü mit Dropdowns“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul `blocktopdropdownmenu` ist als Standard-PrestaShop-Modul konzipiert, das primär die Funktionalität des Kernmoduls `blocktopmenu` (oder dessen Äquivalent in neueren PS-Versionen) erweitert, indem es benutzerdefiniertes JavaScript und CSS injiziert, um das Dropdown-Verhalten zu ermöglichen. Es folgt einem klassischen PrestaShop MVC-Muster für seine Konfiguration, wobei `getContent()` für das Back-Office-Formular verwendet und Hooks für die Front-Office-Anzeige registriert werden. Es führt keine neuen Datenbanktabellen oder komplexen `ObjectModel`-Strukturen ein, sondern verlässt sich auf `Configuration`-Werte, um seine Einstellungen zu speichern, und nutzt bestehende PrestaShop-Entitäten (Kategorien, CMS usw.) für Menüpunkt-Links.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller ein. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten PHP-Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` ein. Die gesamte Logik ist in der Hauptdatei `blocktopdropdownmenu.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul stützt sich stark auf JavaScript, um die Dropdown-Menüfunktionalität zu erstellen.

- `blocktopdropdownmenu/js/blocktopdropdownmenu.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dies ist das Hauptinitialisierungsskript für das Dropdown-Menü. Es enthält wahrscheinlich die Logik, um das Superfish-Plugin (oder eine ähnliche Dropdown-Bibliothek) auf das Hauptnavigationselement anzuwenden. Es bindet Event-Listener für Hover-Intents, handhabt die Erweiterung/Reduzierung von Menüpunkten und gewährleistet die mobile Responsivität (z. B. Umwandlung von Hover in Tap für Touch-Geräte oder Integration in ein Hamburger-Menü). Es könnte auch Logik für das Verhalten der Suchleiste enthalten, wenn diese dynamisch geladen oder umgeschaltet wird.
- `blocktopdropdownmenu/js/hoverIntent.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Ein jQuery-Plugin, das versucht, die Absicht des Benutzers zu bestimmen, über ein Element zu schweben. Es hilft, das versehentliche Auslösen von Dropdowns zu verhindern, indem es eine Verzögerung einführt und die Mausbewegung überprüft, wodurch sich das Menü flüssiger und weniger „flackernd“ anfühlt. Dies ist typischerweise eine Abhängigkeit für Superfish.
- `blocktopdropdownmenu/js/superfish-modified.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dies ist wahrscheinlich eine modifizierte Version des beliebten jQuery-Plugins Superfish, das zur Erstellung von mehrstufigen Dropdown-Menüs entwickelt wurde. Es handhabt die Kernmechanismen des Ein- und Ausblendens von Untermenüs beim Hover, verwaltet Animationen und fügt möglicherweise Zugänglichkeitsfunktionen hinzu. Der Suffix „modified“ deutet darauf hin, dass es benutzerdefinierte Anpassungen für die DOM-Struktur von PrestaShop oder spezifische Theme-Kompatibilität enthalten könnte.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul bietet Styling, um die Dropdown-Menüs visuell darzustellen.

- `blocktopdropdownmenu/css/blocktopdropdownmenu.css`
  - **Umfang:** Front-Office Kunden-Styling.
  - **Verantwortlichkeit:** Enthält benutzerdefinierte CSS-Regeln, die spezifisch für dieses Modul sind, möglicherweise Standard-Theme-Stile überschreiben oder neue Stile für Elemente wie die Suchleiste, spezifische Menüpunktzustände oder allgemeine Layoutanpassungen für die Dropdowns hinzufügen.
  - **Wichtige CSS-Klassenselektoren:** Entwickler sollten diese Datei auf Klassen wie `.sf-menu`, `.sf-menu li`, `.sf-menu li ul`, `.sf-menu li li` usw. überprüfen, die gängige Superfish-Selektoren sind, sowie auf alle vom Modul eingeführten benutzerdefinierten Klassen.
- `blocktopdropdownmenu/css/superfish-modified.css`
  - **Umfang:** Front-Office Kunden-Styling.
  - **Verantwortlichkeit:** Bietet das grundlegende visuelle Styling für die Superfish-Dropdown-Menüstruktur. Dies umfasst Stile für Menüpunktabstände, Hintergrundfarben, Textfarben, Hover-Effekte, Dropdown-Pfeilanzeigen und die Positionierung der Dropdown-Panels. Es ist entscheidend für das visuelle Erscheinungsbild des mehrstufigen Menüs.
  - **Wichtige CSS-Klassenselektoren:** Ähnlich wie `blocktopdropdownmenu.css` enthält diese Datei Kern-Superfish-Selektoren. Entwickler können diese in der `custom.css` oder `theme.css` ihres Themes überschreiben, um sie an die Ästhetik ihrer Marke anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `blocktopdropdownmenu/blocktopdropdownmenu.tpl`
  - **Umfang:** Hook-Template.
  - **Hook:** `displayTop` (und potenziell `displayNav`, wenn die Theme-Struktur dies zulässt).
  - **Verantwortlichkeit:** Dies ist das Haupt-Front-Office-Template, das für das Rendern der HTML-Struktur des horizontalen Top-Menüs verantwortlich ist, einschließlich der Hauptmenüpunkte und ihrer verschachtelten Dropdowns. Es iteriert durch die im Back Office konfigurierten Menüpunkte und generiert die `<ul><li>`-Struktur, die vom Superfish-JavaScript benötigt wird. Es enthält auch die Logik zum Rendern der Suchleiste, falls aktiviert.
- `blocktopdropdownmenu/views/templates/admin/advert.tpl`
  - **Umfang:** Admin-Template.
  - **Verantwortlichkeit:** Zeigt wahrscheinlich eine Werbung oder eine Werbebotschaft von MyPresta.eu innerhalb der Konfigurationsseite des Moduls im Back Office an.
- `blocktopdropdownmenu/views/templates/admin/_configure/helpers/form/form.tpl`
  - **Umfang:** Admin-Template.
  - **Verantwortlichkeit:** Dieses Template ist ein Standard-PrestaShop-Helfer-Template, das zum Rendern des Hauptkonfigurationsformulars für das Modul verwendet wird. Es definiert die Struktur und Felder für die Verwaltung von Menüpunkten und die Einstellung der Suchleiste, wie in `getContent()` konfiguriert.
- `blocktopdropdownmenu/views/templates/admin/_configure/helpers/list/list_content.tpl`
  - **Umfang:** Admin-Template.
  - **Verantwortlichkeit:** Dieses Template ist ein Standard-PrestaShop-Helfer-Template, das zum Rendern der Liste der Menüpunkte innerhalb des Konfigurationsformulars verwendet wird, was das Neuordnen per Drag & Drop, Bearbeiten und Löschen ermöglicht.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Konfigurationseinstellungen (z. B. `MOD_blocktopdropdownmenu_ITEMS`, `MOD_blocktopdropdownmenu_SEARCH`) werden in der Tabelle `ps_configuration` gespeichert. `MOD_blocktopdropdownmenu_ITEMS` speichert ein serialisiertes Array oder einen JSON-String, der die Menüstruktur darstellt.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Injiziert CSS- und JavaScript-Assets (`blocktopdropdownmenu.js`, `hoverIntent.js`, `superfish-modified.js`, `blocktopdropdownmenu.css`, `superfish-modified.css`), die für die Dropdown-Funktionalität erforderlich sind. |
| `displayTop` | Typischerweise im Haupt-Header-Bereich des Themes. | Rendert die Haupt-HTML-Struktur des horizontalen Menüs mit Dropdowns und der Suchleiste. |
| `displayNav` | Oft in der obersten Navigationsleiste (über `displayTop`). | Kann von einigen Themes verwendet werden, um das Menü oder zusätzliche Navigationselemente anzuzeigen. Das Modul könnte hier für eine breitere Theme-Kompatibilität registrieren. |
| `actionObjectProductUpdateAfter` | Nach der Aktualisierung eines Produkts. | Potenziell verwendet, um den Modul-Cache im Zusammenhang mit Produktlinks zu leeren, um sicherzustellen, dass Menüpunkte, die auf Produkte verweisen, aktuell sind. |
| `actionObjectProductDeleteAfter` | Nach dem Löschen eines Produkts. | Potenziell verwendet, um den Modul-Cache zu leeren oder Menüpunkte zu entfernen, die auf das gelöschte Produkt verweisen. |
| `actionObjectManufacturerAddAfter` | Nach dem Hinzufügen eines Herstellers. | Potenziell verwendet, um den Modul-Cache im Zusammenhang mit Herstellerlinks zu leeren. |
| `actionObjectManufacturerUpdateAfter` | Nach der Aktualisierung eines Herstellers. | Potenziell verwendet, um den Modul-Cache im Zusammenhang mit Herstellerlinks zu leeren. |
| `actionObjectManufacturerDeleteAfter` | Nach dem Löschen eines Herstellers. | Potenziell verwendet, um den Modul-Cache zu leeren oder Menüpunkte zu entfernen, die auf den gelöschten Hersteller verweisen. |
| `actionObjectSupplierAddAfter` | Nach dem Hinzufügen eines Lieferanten. | Potenziell verwendet, um den Modul-Cache im Zusammenhang mit Lieferantenlinks zu leeren. |
| `actionObjectSupplierUpdateAfter` | Nach der Aktualisierung eines Lieferanten. | Potenziell verwendet, um den Modul-Cache im Zusammenhang mit Lieferantenlinks zu leeren. |
| `actionObjectSupplierDeleteAfter` | Nach dem Löschen eines Lieferanten. | Potenziell verwendet, um den Modul-Cache zu leeren oder Menüpunkte zu entfernen, die auf den gelöschten Lieferanten verweisen. |
| `actionObjectCmsAddAfter` | Nach dem Hinzufügen einer CMS-Seite. | Potenziell verwendet, um den Modul-Cache im Zusammenhang mit CMS-Seitenlinks zu leeren. |
| `actionObjectCmsUpdateAfter` | Nach der Aktualisierung einer CMS-Seite. | Potenziell verwendet, um den Modul-Cache im Zusammenhang mit CMS-Seitenlinks zu leeren. |
| `actionObjectCmsDeleteAfter` | Nach dem Löschen einer CMS-Seite. | Potenziell verwendet, um den Modul-Cache zu leeren oder Menüpunkte zu entfernen, die auf die gelöschte CMS-Seite verweisen. |
| `actionShopDataDuplication` | Wenn ein Shop dupliziert wird (im Multi-Store-Kontext). | Stellt sicher, dass die Modulkonfiguration (Menüpunkte, Suchleisten-Einstellung) für den neuen Shop korrekt dupliziert wird. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Horizontales Top-Menü mit Dropdowns“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
