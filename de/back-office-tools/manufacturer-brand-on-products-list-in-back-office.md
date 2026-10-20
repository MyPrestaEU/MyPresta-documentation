---
title: "Hersteller (Marke) in der Produktliste im Back Office – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Hersteller (Marke) in der Produktliste im Back Office' von MyPresta.eu."
sidebar:
  label: "Hersteller (Marke) in der Produktliste im Back Office – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Manufacturer (brand) on products list in back office auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/manufacturer-brand-on-products-list-in-back-office.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/manufacturer-brand-on-products-list-in-back-office/)
>
> ---


# Hersteller (Marke) in der Produktliste im Back Office

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.0.0 - 1.7.7.x, 1.7.8.x, 8.x (Standardliste), 8.x (experimentelle Produktliste), 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Moduleinstellungen. Diese Seite verwaltet hauptsächlich Update-Benachrichtigungen und die allgemeine Modulwartung.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt verwaltet typischerweise, wie das Modul nach Updates sucht und Benachrichtigungen anzeigt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul prüft regelmäßig MyPresta.eu auf neue Versionen und informiert Sie, wenn ein Update verfügbar ist. Dies hilft Ihnen, Ihr Modul mit den neuesten Funktionen und Fehlerbehebungen aktuell zu halten.
  - *Wenn deaktiviert:* Das Modul sucht nicht automatisch nach Updates, und Sie erhalten keine Benachrichtigungen über neue Versionen. Sie müssten Ihr MyPresta.eu-Konto manuell auf Updates überprüfen.
- **Empfohlener Wert:** **Aktiviert (Ja)**. Dies aktiviert zu lassen, stellt sicher, dass Sie immer über verfügbare Updates informiert sind, was für die Sicherheit und Kompatibilität mit zukünftigen PrestaShop-Versionen entscheidend ist.
- **Händlerszenario / Beispiel:** Sie möchten benachrichtigt werden, wenn eine neue Version des Moduls veröffentlicht wird, die die neuesten PrestaShop 8.x-Funktionen unterstützt. Durch Aktivieren dieser Einstellung erhalten Sie diese Benachrichtigung direkt in Ihrem Back Office.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul führt keine neuen, separaten Menüpunkte oder dedizierten Admin-Bildschirme zur Verwaltung seiner Kernfunktionalität ein. Stattdessen sind seine Änderungen direkt in die bestehende Seite **Katalog > Produkte** integriert.

**Bildschirmname & Menüpfad:**

- **Katalog > Produkte** (Die Standard-PrestaShop-Produktlistenseite)

**Verfügbare Aktionen & Einstellungen:**
Nach dem Navigieren zu **Katalog > Produkte** werden Sie sofort die vom Modul eingeführten Änderungen bemerken:

- **Neue Spalte: Hersteller/Marke:** Eine neue Spalte erscheint in Ihrer Produktliste, die den Namen des mit jedem Produkt verbundenen Herstellers anzeigt.
- **Herstellerlogo (Optional):** Abhängig von der internen Logik des Moduls kann es auch das Logo des Herstellers neben dem Namen anzeigen, falls verfügbar und konfiguriert.
- **Nach Hersteller filtern:** Oberhalb der Produktliste finden Sie eine neue Filteroption, typischerweise ein Dropdown-Menü, mit der Sie einen bestimmten Hersteller auswählen können. Sobald ausgewählt, wird die Produktliste sofort aktualisiert, um nur Produkte dieser Marke anzuzeigen.

**Auswirkung der Änderungen:**

- **Hinzufügen der Hersteller-Spalte:** Bietet einen sofortigen visuellen Hinweis auf die Marke jedes Produkts, wodurch das individuelle Öffnen von Produktseiten zur Überprüfung dieser Informationen entfällt.
- **Filtern nach Hersteller:** Beschleunigt Aufgaben, bei denen Sie mit Produkten einer bestimmten Marke arbeiten müssen, erheblich. Wenn beispielsweise ein Hersteller eine Preiserhöhung ankündigt, können Sie schnell alle seine Produkte filtern und Preise aktualisieren. Oder wenn Sie Lagerbestände für Artikel einer bestimmten Marke überprüfen müssen.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1. **Schnelle Markenidentifikation:** Verwenden Sie beim Durchsuchen Ihrer Produktliste die neue Spalte „Hersteller“, um Marken schnell zu identifizieren.
2. **Gezielte Verwaltung:** Wenn Sie eine Aktion für alle Produkte einer bestimmten Marke durchführen müssen (z. B. Beschreibungen aktualisieren, Preise anpassen, Lagerbestand überprüfen), verwenden Sie das neue Dropdown-Menü „Nach Hersteller filtern“ oben in der Produktliste. Wählen Sie die gewünschte Marke aus, und Ihre Liste wird sofort verfeinert.
3. **Massenaktionen:** Kombinieren Sie den Herstellerfilter mit den Standard-Massenaktionen von PrestaShop (z. B. Auswahl mehrerer Produkte und Anwenden einer Änderung) für eine hoch effiziente markenspezifische Verwaltung.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Update-Benachrichtigungen | Aktiviert | Benachrichtigt Sie über neue Modulversionen für Sicherheit und Funktionen. |
| Katalog > Produktliste | Hersteller-Spalte | N/A (Immer an) | Zeigt die Produktmarke direkt in der Produktliste zur schnellen Identifizierung an. |
| Katalog > Produktliste | Nach Hersteller filtern | N/A (Immer an) | Ermöglicht das Filtern der Produktliste nach einer bestimmten Marke, wodurch markenspezifische Verwaltungsaufgaben optimiert werden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber die Hersteller-Spalte oder den Filter in meiner Produktliste nicht.**
A:

1. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal benötigt PrestaShop eine Cache-Aktualisierung, um neue Elemente anzuzeigen.
2. **Modul aktiviert:** Überprüfen Sie nochmals, ob das Modul im **Module > Modul-Manager** tatsächlich aktiviert ist.
3. **PrestaShop-Versionskompatibilität:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre spezifische PrestaShop-Installation heruntergeladen haben. Wenn Sie PrestaShop 8.x verwenden, stellen Sie sicher, dass Sie nicht versehentlich eine 1.7.x-Version installiert haben.
4. **Theme-Overrides:** Obwohl das Modul ohne Overrides entwickelt wurde, kann ein stark angepasstes Theme oder ein anderes Modul Konflikte verursachen. Wenn das Problem weiterhin besteht, versuchen Sie, andere Module nacheinander zu deaktivieren, um einen Konflikt zu identifizieren.

**F: Der Herstellername wird angezeigt, aber das Logo nicht.**
A: Das Modul konzentriert sich hauptsächlich auf die Anzeige des Herstellernamens. Wenn es Logos unterstützt, stellen Sie sicher, dass:

1. **Herstellerlogo hochgeladen:** Sie tatsächlich ein Logo für diesen Hersteller unter **Katalog > Hersteller** in Ihrem PrestaShop Back Office hochgeladen haben.
2. **Moduleinstellung:** Es könnte eine interne Einstellung geben (obwohl nicht in der Basiskonfiguration dieses Moduls exponiert), die die Logoanzeige steuert. Wenn nicht, bedeutet dies, dass das Modul nur den Namen anzeigen soll.

**F: Kann ich die Position der Hersteller-Spalte in der Produktliste ändern?**
A: Dieses Modul integriert sich direkt in das Produktgittersystem von PrestaShop. Die genaue Position der Spalte wird durch die Kernkonfiguration der PrestaShop-Produktliste bestimmt. Während dieses Modul die Spalte hinzufügt, bietet es typischerweise keine Optionen zum Ziehen und Ablegen von Spaltenpositionen. Möglicherweise benötigen Sie ein fortschrittlicheres Gitteranpassungsmodul oder eine benutzerdefinierte Entwicklung, um Spalten neu anzuordnen.

**F: Verlangsamt dieses Modul mein Back Office?**
A: Nein, das Modul ist leichtgewichtig und effizient konzipiert. Es nutzt das native Hook-System von PrestaShop, um die Herstellerdaten ohne aufwendige Verarbeitung hinzuzufügen. Sie sollten keine spürbaren Verlangsamungen feststellen.

**F: Funktioniert dieses Modul mit der neuen experimentellen Produktseite in PrestaShop 8.x?**
A: Ja, die Modulbeschreibung gibt explizit die Kompatibilität mit „8.x-experimentelle Produktliste“ an, was bedeutet, dass es sowohl mit der Standard- als auch mit der neueren, experimentellen Produktlistenoberfläche in PrestaShop 8.x funktioniert.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Manufacturer (brand) on products list in back office` (interner Name `dpmypresta`) wurde entwickelt, um die PrestaShop Back Office Produktlistenseite durch Hinzufügen von Herstellerinformationen zu erweitern. Es verfolgt einen Nicht-Override-Ansatz und stützt sich stark auf das Hook-System von PrestaShop, insbesondere auf die in PrestaShop 1.7.x eingeführten `actionProductGrid*`-Hooks zur Modifikation des Produktkatalograsters. Dies macht es robust gegenüber PrestaShop-Core-Updates. Das Modul injiziert hauptsächlich neue Spalten und Filterfunktionen in die vorhandenen Produktdaten und den Rendering-Prozess des Produktrasters.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine Front-Office-Controller. Es enthält zwei Admin-Controller-Dateien, aber `AdminDpMyPrestaController.php` scheint ein Platzhalter oder ein Überbleibsel zu sein, und `index.php` ist eine standardmäßige leere Datei, um das Auflisten von Verzeichnissen zu verhindern. Die Kernlogik des Moduls für die Konfiguration wird in der `getContent()`-Methode von `dpmypresta.php` behandelt, und die Produktgittermodifikationen werden über Hooks abgewickelt.

- **Front-Office-Controller**: Keine. Alle Funktionen sind Back-Office-spezifisch.
- **Back-Office-Admin-Controller**:
  - `controllers/admin/AdminDpMyPrestaController.php`
    - Klassenname: `AdminDpMyPrestaController` (erweitert `ModuleAdminController`)
    - Verantwortung: Dieser Controller ist vorhanden, scheint aber ein Platzhalter zu sein. Seine `__construct`-Methode richtet den grundlegenden Modulkontext ein. Er definiert keine spezifischen Aktionen oder rendert einzigartige Ansichten, die über das hinausgehen, was von `ModuleAdminController` geerbt werden könnte. Er ist nicht direkt mit der Kernfunktionalität des Hinzufügens von Herstellerdaten zur Produktliste verknüpft, die Hook-gesteuert ist.
  - `controllers/admin/index.php`
    - Standardmäßige leere `index.php`-Datei zur Sicherheit, um das Auflisten von Verzeichnissen zu verhindern.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s im Verzeichnis `classes/`. Seine Operationen sind direkt in die bestehenden Datenstrukturen und Gittermechanismen von PrestaShop über Hooks integriert.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Alle Interaktionen und die Anzeigelogik für die Hersteller-Spalte und den Filter werden von den nativen Gitterkomponenten von PrestaShop und der PHP-Logik des Moduls gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling für die hinzugefügte Hersteller-Spalte und den Filter wird vom PrestaShop Back Office Theme geerbt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul nutzt das neue Twig-Templating-System, das in PrestaShop 1.7+ für Back-Office-Gitter verwendet wird.

- **Admin-Templates (`views/templates/admin/`)**:
  - `views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`
    - Dieses Twig-Template erweitert oder modifiziert wahrscheinlich das Kern-PrestaShop-Produktlisten-Template. Es ist für das Rendern der gesamten Produktkatalogseite, einschließlich des Gitters, verantwortlich. Das Modul injiziert die Hersteller-Spalte und den Filter in diese Struktur.
  - `views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`
    - Dieses Twig-Template rendert speziell die Produkttabelle innerhalb der Katalogseite. Das Modul modifiziert dieses Template, um die Herstellerdaten zu jeder Produktzeile hinzuzufügen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es stützt sich auf vorhandene PrestaShop-Tabellen, hauptsächlich `ps_product`, `ps_manufacturer` und `ps_configuration` für seine Einstellungen.

  - Konfigurationswerte (`mypresta_updates`, `update_`, `updatev_`) werden in der Tabelle `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionProductGridDataModifier` | Nach dem Abrufen der Produktdaten für das Gitter. | Modifiziert das Rohdatenarray für jedes Produkt und injiziert Hersteller-ID und -Namen. |
| `actionAdminProductsListingFieldsModifier` | Bevor die Felder des Produktgitters definiert werden. | Fügt die Definition der Spalte „Hersteller“ zum Produktgitter hinzu. |
| `actionProductGridDefinitionModifier` | Modifiziert die Definition des Produktgitters selbst. | Fügt möglicherweise den Herstellerfilter zur Filtersammlung des Gitters hinzu. |
| `actionAdminProductsListingResultsModifier` | Nachdem die Produktlistungsergebnisse vorbereitet wurden. | Modifiziert die Ergebnisse weiter, um sicherzustellen, dass die Herstellerdaten korrekt für die Anzeige formatiert sind. |
| `actionProductGridQueryBuilderModifier` | Modifiziert den Doctrine Query Builder für das Produktgitter. | Verbindet die Tabelle `ps_manufacturer` mit der Produktabfrage und fügt Bedingungen zum Filtern nach Hersteller hinzu. |
| `displayBackOfficeHeader` | Rendert Inhalte im `<head>`-Bereich des Back Office. | Wird zum Laden modulspezifischer Assets (obwohl in diesem Modul keine vorhanden sind) oder für Update-Prüfungen verwendet. |
| `displayAdminProductsExtra` | Rendert zusätzliche Inhalte auf der Produktseite (nicht direkt für die Listenmodifikation verwendet). | Nicht direkt mit der Kernfunktionalität dieses Moduls verbunden, aber ein häufiger Hook für Erweiterungen der Admin-Produktseite. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Manufacturer (brand) on products list in back office“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
