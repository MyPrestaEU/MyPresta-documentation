---
title: "Vorher & Nachher - Bildvergleichstool - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Vorher & Nachher - Bildvergleichstool“ von MyPresta.eu."
sidebar:
  label: "Vorher & Nachher - Bildvergleichstool - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Before & after - pictures diff tool auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/before-after-pictures-diff-tool.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/before-after-pictures-diff-tool/)
>
> ---


# Vorher & Nachher - Bildvergleichstool

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation klicken Sie auf „Konfigurieren“ neben dem Modul „Vorher & Nachher - Bildvergleichstool“, um auf dessen Haupteinstellungen zuzugreifen.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt steuert die Gesamtaktivierung und den Betriebsmodus des Moduls.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Aktiviert:* Das Modul ist in Ihrem Shop aktiv. Das „Vorher & Nachher“-Bildvergleichstool ist auf Produktseiten verfügbar, auf denen Sie Bilder konfiguriert haben.
  - *Deaktiviert:* Das Modul ist inaktiv. Das „Vorher & Nachher“-Bildvergleichstool wird auf keiner Produktseite angezeigt, selbst wenn Sie Bilder dafür konfiguriert haben.
  - *Testmodus:* Diese Option wird typischerweise für Entwicklungs- oder Staging-Umgebungen verwendet. Wenn aktiviert, kann das Modul zusätzliche Debugging-Informationen anzeigen oder unter spezifischen Bedingungen arbeiten, die nicht für einen Live-Produktionsshop geeignet sind. Es wird im Allgemeinen nicht für Live-Shops empfohlen, es sei denn, der Support weist ausdrücklich darauf hin.
- **Empfohlener Wert:** „Aktiviert“ für einen Live-Shop. „Deaktiviert“, wenn Sie die Funktion vorübergehend ausblenden möchten, ohne das Modul zu deinstallieren.
- **Händlerszenario / Beispiel:** Wenn Sie eine neue Produktlinie einführen, die stark auf visuelle Transformationen angewiesen ist (z. B. individuell bemalte Schuhe), würden Sie dies auf „Aktiviert“ setzen, um die Arbeit zu präsentieren. Wenn Sie Wartungsarbeiten durchführen oder die Funktion für einen bestimmten Zeitraum nicht aktiv haben möchten, würden Sie sie auf „Deaktiviert“ setzen.

#### Spracheinstellungen (Implizit)

Obwohl nicht explizit als Einstellung aufgeführt, respektiert das Modul die Standard-Spracheinstellungen Ihres PrestaShop für das Back Office.

- **`PS_LANG_DEFAULT`**: Diese PrestaShop-Kerneinstellung bestimmt die Standardsprache für Ihren Shop.
- **`PS_BO_ALLOW_EMPLOYEE_FORM_LANG`**: Diese PrestaShop-Kerneinstellung ermöglicht es Mitarbeitern, ihre bevorzugte Sprache für Formulare zu wählen.
- **Auswirkung der Änderung dieser Einstellung:** Diese PrestaShop-Kerneinstellungen stellen sicher, dass alle vom Modul im Back Office bereitgestellten Texte oder Beschriftungen (z. B. auf der Produktbearbeitungsseite zum Hinzufügen von Vorher-/Nachher-Bildern) in der richtigen Sprache für den Administrator angezeigt werden.
- **Empfohlener Wert:** Stellen Sie sicher, dass Ihr `PS_LANG_DEFAULT` auf Ihre primäre Shop-Sprache eingestellt ist. Wenn Sie ein mehrsprachiges Team haben, sollte `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` aktiviert sein.

#### Update-Einstellungen (Implizit)

Das Modul enthält auch interne Einstellungen für Updates von MyPresta.eu. Diese werden normalerweise automatisch verwaltet.

- **`mypresta_updates`, `update_`, `updatev_`**: Dies sind interne Konfigurationsschlüssel, die von MyPresta.eu-Modulen verwendet werden, um Updates zu überprüfen und zu verwalten. Sie müssen normalerweise nicht mit diesen interagieren.
- **Auswirkung der Änderung dieser Einstellung:** Eine direkte Änderung könnte die Fähigkeit des Moduls beeinträchtigen, wichtige Updates und Fehlerbehebungen zu erhalten.
- **Empfohlener Wert:** Lassen Sie diese unberührt.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### Produktbearbeitungsseite (Back Office > Katalog > Produkte > Produkt bearbeiten)

Dieses Modul integriert sich direkt in die Standard-PrestaShop-Produktbearbeitungsoberfläche.

- **Bildschirmname & Menüpfad:** Um darauf zuzugreifen, navigieren Sie zu **Katalog > Produkte** und klicken Sie dann auf „Bearbeiten“ bei einem beliebigen Produkt.
- **Verfügbare Aktionen & Einstellungen:** Innerhalb der Produktbearbeitungsseite finden Sie einen neuen Abschnitt oder Tab speziell für das „Vorher & Nachher - Bildvergleichstool“. Hier können Sie:
  - **„Vorher“-Bild hochladen:** Wählen und laden Sie das Ausgangsbild für Ihr Produkt hoch.
  - **„Nachher“-Bild hochladen:** Wählen und laden Sie das Endzustandsbild für Ihr Produkt hoch.
  - **Speichern:** Nach dem Hochladen denken Sie daran, das Produkt zu speichern, um die Änderungen zu übernehmen.
- **Auswirkung von Änderungen:**
  - *Bilder hinzufügen:* Sobald Sie sowohl ein „Vorher“- als auch ein „Nachher“-Bild für ein bestimmtes Produkt hochgeladen und gespeichert haben, erscheint der interaktive Vergleichsschieberegler automatisch auf der Front-Office-Seite dieses Produkts.
  - *Bilder entfernen:* Wenn Sie eines oder beide Bilder entfernen, wird der Vergleichsschieberegler für dieses Produkt nicht mehr angezeigt.
  - *Bilder aktualisieren:* Das Ersetzen von Bildern aktualisiert den Schieberegler im Front Office.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Wenn Sie ein neues Produkt hinzufügen, das von einem Vorher-/Nachher-Vergleich profitiert, erstellen Sie das Produkt zunächst wie gewohnt.
  2. Navigieren Sie zu dessen Bearbeitungsseite.
  3. Suchen Sie den Abschnitt „Vorher & Nachher“.
  4. Laden Sie Ihre „Vorher“- und „Nachher“-Bilder hoch. Stellen Sie sicher, dass sie ähnliche Abmessungen haben, um den besten visuellen Effekt zu erzielen.
  5. Speichern Sie das Produkt.
  6. Überprüfen Sie die Produktseite im Front Office, um zu bestätigen, dass der Schieberegler wie erwartet funktioniert.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modulstatus | Aktiviert | Aktiviert/deaktiviert die gesamte Modulfunktionalität. |
| Produktbearbeitungsseite | „Vorher“-Bild hochladen | N/A | Definiert das Ausgangsbild für den Vergleich. |
| Produktbearbeitungsseite | „Nachher“-Bild hochladen | N/A | Definiert das Endzustandsbild für den Vergleich. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der „Vorher & Nachher“-Schieberegler wird auf meiner Produktseite nicht angezeigt.**
A1:

- **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Vorher & Nachher - Bildvergleichstool“ „Aktiviert“ ist.
- **Produktbilder überprüfen:** Bearbeiten Sie das spezifische Produkt (**Katalog > Produkte > Bearbeiten**) und überprüfen Sie, ob sowohl ein „Vorher“- als auch ein „Nachher“-Bild im Modulbereich hochgeladen und gespeichert wurden.
- **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass neue Inhalte angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
- **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können einige stark angepasste Themes geringfügige CSS-Anpassungen erfordern. Wenn die oben genannten Schritte nicht funktionieren, wenden Sie sich an den MyPresta.eu-Support.

**F2: Die Bilder sehen im Schieberegler verzerrt oder falsch ausgerichtet aus.**
A2:

- **Bildabmessungen:** Für die besten Ergebnisse stellen Sie sicher, dass Ihre „Vorher“- und „Nachher“-Bilder genau die gleichen Abmessungen (Breite und Höhe) haben. Wenn sie sich erheblich unterscheiden, kann der Schieberegler Schwierigkeiten haben, sie perfekt auszurichten.
- **Bildqualität:** Verwenden Sie hochwertige Bilder. Bilder mit niedriger Auflösung können beim Skalieren verpixelt erscheinen.

**F3: Kann ich dieses Modul für Produkte mit mehreren Variationen (Kombinationen) verwenden?**
A3: Das Modul ermöglicht es Ihnen derzeit, ein „Vorher“- und ein „Nachher“-Bild pro Produkt festzulegen, nicht pro Kombination. Wenn Ihre Variationen unterschiedliche Vorher-/Nachher-Zustände haben, müssen Sie möglicherweise separate Produkte erstellen oder die Hauptproduktbilder für den Vergleich verwenden.

**F4: Wie übersetze ich den Text des Moduls (falls vorhanden) in andere Sprachen?**
A4: Alle vom Modul im Back Office eingeführten Textbeschriftungen (z. B. „Vorher-Bild hochladen“) können typischerweise über das integrierte PrestaShop-Übersetzungssystem übersetzt werden. Gehen Sie zu **International > Übersetzungen**, wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und suchen Sie dann das Modul „Vorher & Nachher - Bildvergleichstool“, um dessen Übersetzungen zu bearbeiten.

**F5: Der Schieberegler funktioniert, sieht aber mit dem Design meines Themes nicht ganz richtig aus.**
A5: Dies liegt oft an der CSS-Formatierung. Ihr Theme könnte widersprüchliche Stile haben. Sie können versuchen, das Element mit den Entwicklertools Ihres Browsers zu überprüfen, um das widersprüchliche CSS zu identifizieren. Für fortgeschrittenere Anpassungen benötigen Sie möglicherweise einen Webentwickler oder wenden sich an den MyPresta.eu-Support, um Anleitungen zum Überschreiben der Standardstile des Moduls zu erhalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Vorher & Nachher - Bildvergleichstool“ ist ein Standard-PrestaShop-Modul, das einem MVC-ähnlichen Muster folgt. Es erweitert hauptsächlich die Klasse `Module`, integriert sich über Hooks in die Produktverwaltungsseite und injiziert seine Front-Office-Assets und Templates in den Produktseiten-Footer. Es nutzt externe jQuery-Plugins (`jquery.event.move.js`, `jquery.twentytwenty.js`) für die interaktive Schiebereglerfunktionalität.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Logik wird innerhalb der Hauptmodulklasse und über Hooks verarbeitet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s. Es speichert seine Konfiguration direkt in `ps_configuration` und produktspezifische Bildpfade als Produktattribute oder Konfigurationswerte, die über den Hook `displayAdminProductsExtra` verwaltet werden.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien, hauptsächlich für den „TwentyTwenty“-Bildvergleichsschieberegler. Diese werden im Front Office geladen.

- **`beforeafter/js/jquery.event.move.js`**
  - **Umfang:** Front-Office.
  - **Zweck:** Ein leichtgewichtiges jQuery-Plugin, das Touch- und Mausereignisbehandlung für das Ziehen von Elementen bereitstellt. Es ist eine Abhängigkeit für `jquery.twentytwenty.js`.
  - **Details:** Bindet Ereignisse wie `move`, `movestart`, `moveend`, um die Drag-Funktionalität zu ermöglichen.
- **`beforeafter/js/jquery.twentytwenty.js`**
  - **Umfang:** Front-Office.
  - **Zweck:** Das Kern-jQuery-Plugin, das den „TwentyTwenty“-Bildvergleichsschieberegler implementiert.
  - **Details:** Initialisiert den Schieberegler auf angegebenen Elementen, handhabt die visuelle Darstellung der Vorher-/Nachher-Bilder und verwaltet den interaktiven Teiler basierend auf `jquery.event.move.js`. Es zielt typischerweise auf einen Container mit zwei `img`-Tags im Inneren ab.
- **`beforeafter/js/twentytwenty.js`**
  - **Umfang:** Front-Office.
  - **Zweck:** Diese Datei enthält wahrscheinlich die modulspezifische Initialisierungslogik für das `jquery.twentytwenty.js`-Plugin, das es auf die richtigen Elemente auf der Produktseite anwendet.
  - **Details:** Sie enthält jQuery-Selektoren, um das `div`-Element zu identifizieren, das die Vorher-/Nachher-Bilder umschließt, und ruft die Methode `.twentytwenty()` darauf auf, möglicherweise mit Konfigurationsoptionen.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält CSS-Dateien, um den Bildvergleichsschieberegler und seine Komponenten zu gestalten.

- **`beforeafter/css/foundation.css`**
  - **Umfang:** Front-Office.
  - **Zweck:** Diese Datei enthält wahrscheinlich grundlegende Reset- oder grundlegende Stile, möglicherweise eine Untermenge des Zurb Foundation Frameworks, um eine konsistente Darstellung der Schieberegler-Elemente zu gewährleisten. Sie könnte grundlegende Raster-, Typografie- oder Formularstile definieren, die das Modul verwendet.
  - **Wichtige Selektoren:** Kann allgemeine `div`-, `img`-, `button`-Stile oder spezifische Klassen wie `.row`, `.column` enthalten.
- **`beforeafter/css/twentytwenty.css`**
  - **Umfang:** Front-Office.
  - **Zweck:** Enthält die spezifische Formatierung, die für den „TwentyTwenty“-Bildvergleichsschieberegler selbst erforderlich ist.
  - **Wichtige Selektoren:** Definiert das Aussehen des Schieberegler-Containers, des Teilergriffs, des Overlays und der Positionierung der „Vorher“- und „Nachher“-Bilder. Beispiele: `.twentytwenty-container`, `.twentytwenty-overlay`, `.twentytwenty-handle`, `.twentytwenty-before`, `.twentytwenty-after`. Entwickler können diese Klassen in der `custom.css` oder `theme.css` ihres Themes überschreiben, um sie an das Design ihres Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `beforeafter/views/templates/front/hook/displayFooter.tpl`
    - **Hook:** `displayFooter` (oder potenziell `displayFooterProduct` abhängig von der internen Logik).
    - **Zweck:** Dieses Template ist für das Rendern der eigentlichen HTML-Struktur für den „Vorher & Nachher“-Bildvergleichsschieberegler im Front Office verantwortlich. Es enthält die `div`-Elemente, die das JavaScript zum Initialisieren des `twentytwenty`-Plugins ansteuert, einschließlich der `img`-Tags für die „Vorher“- und „Nachher“-Bilder. Es enthält wahrscheinlich auch das Laden der notwendigen JavaScript- und CSS-Assets.
  - `beforeafter/views/templates/front/hook/displayFooterCms.tpl`
    - **Hook:** Wahrscheinlich `displayFooter` oder `displayFooterProduct`, aber möglicherweise mit bedingter Logik für CMS-Seiten.
    - **Zweck:** Dieses Template könnte ein Fallback oder eine Alternative für das Rendern des Schiebereglers auf CMS-Seiten sein, obwohl sich die Modulbeschreibung auf Produktseiten konzentriert. Sein Inhalt wäre ähnlich wie `displayFooter.tpl`.
- **Admin-Templates (`views/templates/admin/`)**:
  - `beforeafter/views/templates/admin/displayAdminProductsExtra.tpl`
    - **Hook:** `displayAdminProductsExtra`
    - **Zweck:** Dieses Template rendert die benutzerdefinierten Eingabefelder und Upload-Formulare innerhalb der PrestaShop-Produktbearbeitungsseite im Back Office. Es bietet die Oberfläche für Administratoren, um die „Vorher“- und „Nachher“-Bilder für jedes Produkt hochzuladen und zu verwalten. Es enthält Formularelemente (z. B. `input type="file"`) und zeigt möglicherweise Miniaturansichten bereits hochgeladener Bilder an.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen (wie `BA_TEST`) in der Tabelle `ps_configuration`.
  - Produktspezifische „Vorher“- und „Nachher“-Bildpfade werden wahrscheinlich als produktspezifische Konfigurationswerte oder Attribute gespeichert, die über den Hook `displayAdminProductsExtra` und die `install()`- und `uninstall()`-Methoden des Moduls verwaltet werden.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Wird verwendet, um die Pfade der „Vorher“- und „Nachher“-Bilder zu speichern, die über die Produktbearbeitungsseite hochgeladen wurden. |
| `displayFooterProduct` | Rendert Inhalte im Footer-Bereich der Produktseite. | Wird verwendet, um den „Vorher & Nachher“-Bildvergleichsschieberegler auf der Front-Office-Produktseite anzuzeigen. |
| `displayAdminProductsExtra` | Rendert zusätzliche Inhalte auf der Produktbearbeitungsseite im Back Office. | Wird verwendet, um die benutzerdefinierten Formularfelder zum Hochladen von „Vorher“- und „Nachher“-Bildern in die Produktverwaltungsoberfläche einzufügen. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Ansicht rendert, ermöglicht Modulen das Hinzufügen von JS/CSS. | Wird verwendet, um die notwendigen JavaScript-Dateien (`jquery.event.move.js`, `jquery.twentytwenty.js`, `twentytwenty.js`) und CSS-Dateien (`foundation.css`, `twentytwenty.css`) für das Modul im Back Office (falls für die Admin-Produktseite erforderlich) und potenziell im Front Office zu laden. |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich der Front-Office-Seiten. | Wird verwendet, um die notwendigen JavaScript- und CSS-Dateien für den „Vorher & Nachher“-Schieberegler im Front Office zu laden, um sicherzustellen, dass sie verfügbar sind, bevor der `displayFooterProduct`-Hook das HTML des Schiebereglers rendert. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Updates und weitere Unterstützung für das Modul „Vorher & Nachher - Bildvergleichstool“ wenden Sie sich bitte an Ihr MyPresta.eu-Kundenkonto. Dort finden Sie die neuesten Modulversionen, Dokumentationen und können unser Support-Team direkt über die MyPresta.eu-Website kontaktieren.
