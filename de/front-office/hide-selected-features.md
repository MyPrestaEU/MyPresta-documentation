---
title: "Ausgewählte Merkmale ausblenden – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Ausgewählte Merkmale ausblenden“ von MyPresta.eu."
sidebar:
  label: "Ausgewählte Merkmale ausblenden – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Hide selected features auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/hide-selected-features.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/hide-selected-features/)
>
> ---


# Ausgewählte Merkmale ausblenden

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Sie können diese Seite aufrufen, indem Sie zu **Module > Modulmanager** navigieren, nach „Ausgewählte Merkmale ausblenden“ suchen und dann auf „Konfigurieren“ klicken.

Dieser Bildschirm zeigt eine Liste aller Produktmerkmale, die derzeit in Ihrem PrestaShop-Shop definiert sind. Für jedes Merkmal sehen Sie einen Umschalter, um dessen Sichtbarkeit zu steuern.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt listet alle Ihre vorhandenen Produktmerkmale auf (z. B. „Material“, „Farbe“, „Gewicht“, „Abmessungen“). Neben jedem Merkmal befindet sich ein Schalter, der steuert, ob dieses spezifische Merkmal auf Ihren Produktseiten im Front Office angezeigt wird.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (Schalter ist AN):* Das Merkmal ist für Kunden auf allen Produktseiten sichtbar, denen es zugewiesen ist. Dies ist das Standardverhalten von PrestaShop.
  - *Wenn deaktiviert (Schalter ist AUS):* Das Merkmal wird für Kunden auf allen Produktseiten ausgeblendet, auch wenn es einem Produkt zugewiesen ist. Es bleibt weiterhin in Ihrem Back Office für den internen Gebrauch oder zur Filterung bestehen.
- **Empfohlener Wert:** Dies hängt vollständig von Ihren Geschäftsanforderungen ab.
  - **Aktivieren** Sie Merkmale, die für die Kundenentscheidung entscheidend sind (z. B. „Material“ für Kleidung, „Kapazität“ für Elektronik).
  - **Deaktivieren** Sie Merkmale, die interne Notizen, für den durchschnittlichen Kunden irrelevante technische Spezifikationen oder redundante Informationen sind.
- **Händlerszenario / Beispiel:**
  - **Szenario 1 (Interne Notizen ausblenden):** Sie verwenden ein Merkmal namens „Lieferanten-SKU“, um interne Produktcodes zu verfolgen. Diese Informationen sind für Kunden nicht nützlich. Sie würden das Merkmal „Lieferanten-SKU“ hier **deaktivieren**, um Ihre Produktseiten sauber zu halten.
  - **Szenario 2 (Anzeige vereinfachen):** Sie verkaufen T-Shirts und haben Merkmale wie „Material: Baumwolle“, „Ärmellänge: Kurz“, „Ausschnitt: Rundhals“. Sie entscheiden, dass „Ärmellänge“ und „Ausschnitt“ normalerweise aus dem Produktbild ersichtlich sind und Sie „Material“ hervorheben möchten. Sie würden „Ärmellänge“ und „Ausschnitt“ **deaktivieren** und „Material“ **aktivieren**.

**Weitere Konfigurationsschlüssel (Intern/Erweitert):**
Möglicherweise sehen Sie einige andere Konfigurationsschlüssel wie `mypresta_updates`, `update_`, `updatev_`, `hidefeatures_OSTATE`, `PS_OS_PREPARATION`, `hidefeatures_MIN_CHARGE`. Dies sind typischerweise interne Moduleinstellungen, die sich auf Updates, Bestellstatus oder Mindestgebühren beziehen und nicht direkt vom Händler über die Hauptschnittstelle konfigurierbar sind. Sie werden normalerweise automatisch vom Modul verwaltet oder für spezifische, erweiterte Szenarien verwendet, die in der primären Benutzeroberfläche nicht sichtbar sind. Für dieses Modul wird die Kernfunktionalität durch die Merkmalsschalter verwaltet.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AdminFeaturesController (Back Office > Katalog > Attribute & Merkmale > Merkmale)

Dieses Modul überschreibt den Standard-PrestaShop-Verwaltungsbildschirm „Merkmale“.

- **Bildschirmname & Menüpfad:** **Back Office > Katalog > Attribute & Merkmale > Merkmale**.
- **Verfügbare Aktionen & Einstellungen:** Wenn Sie diesen Bildschirm aufrufen, sehen Sie eine Liste all Ihrer Produktmerkmale. Das Modul fügt dieser Liste eine neue Spalte oder einen Indikator hinzu, typischerweise mit der Bezeichnung **„Im Front Office aktiv“** oder Ähnlichem. Diese Spalte zeigt Ihnen auf einen Blick, ob ein Merkmal derzeit auf der Frontend-Seite Ihres Shops sichtbar oder ausgeblendet ist, basierend auf den Einstellungen, die Sie auf der Hauptkonfigurationsseite des Moduls vorgenommen haben.
- **Auswirkung von Änderungen:** Obwohl Sie die Sichtbarkeit nicht direkt von diesem Bildschirm aus ändern können (dies tun Sie auf der Konfigurationsseite des Moduls), bietet dieser Bildschirm eine praktische Übersicht. Er hilft Ihnen, den Front-Office-Status jedes Merkmals schnell zu überprüfen, ohne zum Modul zurücknavigieren zu müssen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm als schnelle Referenz bei der Verwaltung Ihrer Produktmerkmale. Wenn Sie ein neues Merkmal hinzufügen, denken Sie daran, die Konfigurationsseite des Moduls „Ausgewählte Merkmale ausblenden“ zu besuchen, um zu entscheiden, ob es für Kunden sichtbar sein soll.

#### 2.2.2 index.php (hidefeatures/override/controllers/admin/index.php)

Diese Datei ist Teil der Override-Struktur und dient typischerweise als Platzhalter oder Einstiegspunkt für die überschriebene Controller-Logik. Sie stellt keinen eigenständigen, benutzerorientierten Konfigurationsbildschirm dar, sondern erleichtert die Modifikation bestehender PrestaShop-Admin-Seiten durch das Modul.

- **Verwaltete Tabelle / Entität:** Diese Datei verwaltet keine spezifische Tabelle oder Entität direkt, sondern stellt das korrekte Laden und Ausführen des überschriebenen `AdminFeaturesController` sicher.
- **Formularfelder & Spalten:** Es werden keine direkten Formularfelder oder Spalten von dieser spezifischen Datei verwaltet. Ihr Zweck ist architektonisch, um sicherzustellen, dass die Änderungen des Moduls am „Merkmale“-Raster/Verwaltungsansicht angewendet werden.
- **Auswirkung von Änderungen:** Diese Datei stellt sicher, dass die Spalte „Im Front Office aktiv“ (oder ein ähnlicher Indikator) in der Liste **Katalog > Attribute & Merkmale > Merkmale** korrekt angezeigt wird und die erweiterte Verwaltungsansicht bereitstellt.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Liste aller Merkmale mit AN/AUS-Umschaltern | Variiert je nach Merkmal (AN für neue Merkmale) | Steuert, ob ein bestimmtes Produktmerkmal auf Produktseiten im Front Office angezeigt wird. AN = Sichtbar, AUS = Ausgeblendet. |
| **AdminFeaturesController** (Katalog > Attribute & Merkmale > Merkmale) | Spalte/Indikator „Im Front Office aktiv“ | Spiegelt die Modulkonfiguration wider | Bietet eine schnelle Übersicht über den Front-Office-Sichtbarkeitsstatus eines Merkmals direkt in der Merkmalsliste. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe ein Merkmal ausgeblendet, aber es wird immer noch auf meiner Produktseite angezeigt. Was ist falsch?**
A:

1. **Cache leeren:** Der häufigste Grund ist, dass Ihr PrestaShop-Cache (und möglicherweise Ihr Browser-Cache) nicht aktualisiert wurde. Gehen Sie in Ihrem Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Versuchen Sie auch, den Cache Ihres Browsers zu leeren oder die Seite in einem Inkognito-/privaten Fenster anzuzeigen.
2. **Modulkonfiguration gespeichert?** Überprüfen Sie, ob Sie nach Änderungen auf der Konfigurationsseite des Moduls auf „Speichern“ geklickt haben.
3. **Richtiges Merkmal?** Stellen Sie sicher, dass Sie genau das Merkmal deaktiviert haben, das Sie ausblenden möchten. Merkmalsnamen können manchmal ähnlich sein.

**F: Kann ich Merkmale nur für bestimmte Produkte ausblenden, nicht global?**
A: Nein, dieses Modul blendet Merkmale global für alle Produkte aus. Wenn Sie eine produktspezifische Merkmalssichtbarkeit benötigen, würden Sie dies normalerweise verwalten, indem Sie das Merkmal dem Produkt gar nicht erst zuweisen oder eine fortschrittlichere benutzerdefinierte Lösung verwenden. Dieses Modul bietet einen shopweiten Umschalter für Merkmalstypen.

**F: Beeinträchtigt das Ausblenden eines Merkmals meine Produktfilter oder Suchergebnisse?**
A: Nein, dieses Modul beeinflusst nur die *Anzeige* von Merkmalen auf der Produktseite im Front Office. Die Merkmalsdaten selbst bleiben in Ihrer Datenbank. Wenn Sie Merkmale für die Layered Navigation (Filter) oder die Suche verwenden, sollten diese weiterhin wie erwartet funktionieren, solange das Merkmal dem Produkt zugewiesen ist.

**F: Die Spalte „Im Front Office aktiv“ wird in meiner Merkmalsliste (Katalog > Attribute & Merkmale > Merkmale) nicht angezeigt.**
A:

1. **Modul installiert & aktiviert?** Stellen Sie sicher, dass das Modul „Ausgewählte Merkmale ausblenden“ korrekt installiert und in **Module > Modulmanager** aktiviert ist.
2. **Cache:** Leeren Sie Ihren PrestaShop-Cache wie oben beschrieben.
3. **Theme-Kompatibilität:** In seltenen Fällen kann ein stark angepasstes Theme mit Overrides interferieren. Wenn das Leeren des Caches nicht hilft, wenden Sie sich an den MyPresta.eu-Support.

**F: Wie übersetze ich den Text des Moduls (falls vorhanden)?**
A: Obwohl dieses Modul hauptsächlich vorhandene PrestaShop-Merkmalsnamen verwendet, können Sie, falls es modulspezifische Texte oder Beschriftungen gibt, diese übersetzen, indem Sie in Ihrem Back Office zu **International > Übersetzungen** gehen. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme, wählen Sie Ihre Sprache und suchen Sie dann das Modul „Ausgewählte Merkmale ausblenden“, um dessen Übersetzungen zu bearbeiten.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Ausgewählte Merkmale ausblenden“ arbeitet, indem es zentrale PrestaShop-Klassen und -Controller überschreibt, um seine Sichtbarkeitslogik zu injizieren. Es erweitert die Klassen `Feature` und `Product`, um eine neue Eigenschaft für die Front-Office-Sichtbarkeit hinzuzufügen, und modifiziert den `AdminFeaturesController`, um diesen Status im Back Office anzuzeigen. Das Modul verwendet einen benutzerdefinierten Hook (`displayHiddenFeatures`), um die tatsächliche Merkmalsliste auf der Produktseite zu rendern, wodurch es ausgeblendete Merkmale vor der Anzeige herausfiltern kann.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul führt keine benutzerdefinierten Front-Office-Controller ein. Die gesamte Front-Office-Logik wird über Overrides von Kernklassen und Hooks abgewickelt.
- **Back-Office-Admin-Controller**:

  - `hidefeatures/override/controllers/admin/AdminFeaturesController.php`
    - **Klassenname & Elternklasse**: `AdminFeaturesController` (überschreibt den Kern-`AdminFeaturesController`)
    - **Verantwortlichkeit**: Dieser Override modifiziert den `AdminFeaturesController`, um den Front-Office-Sichtbarkeitsstatus jedes Merkmals in der Merkmalsliste anzuzeigen. Er fügt wahrscheinlich eine neue Spalte zur Listentabelle hinzu, die es Administratoren ermöglicht, schnell zu sehen, welche Merkmale ausgeblendet/sichtbar sind, ohne die Konfiguration des Moduls aufrufen zu müssen. Er nutzt den `Feature`-Klassen-Override, um diesen Status abzurufen.
  - `hidefeatures/override/controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Keine Klassendatei, typischerweise eine leere `index.php`, um die Verzeichnisauflistung zu verhindern.
    - **Verantwortlichkeit**: Standardpraxis für `override`-Verzeichnisse, um direkten Zugriff zu verhindern und die Sicherheit zu gewährleisten. Sie enthält keinen funktionalen Code.

### 4.3 Kernklassen & Modelle (`classes/`)

- `hidefeatures/override/classes/Feature.php`

  - **Mit welcher Datenbanktabelle interagiert es**: `ps_feature` (Hauptmerkmals-Tabelle) und `ps_configuration` (für Moduleinstellungen).
  - **Erweitert `ObjectModel`**: Ja, es erweitert die Kern-`Feature`-Klasse, die selbst `ObjectModel` erweitert.
  - **`$definition`-Felder**: Dieser Override fügt wahrscheinlich ein neues Feld zum `$definition`-Array der `Feature`-Klasse hinzu, oder, häufiger, eine dynamische Eigenschaft zum `Feature`-Objekt, um seinen Front-Office-Sichtbarkeitsstatus zu speichern, der dann aus `ps_configuration` oder einer benutzerdefinierten Tabelle abgerufen wird. Es würde auch Methoden enthalten, um diesen Sichtbarkeitsstatus abzurufen und festzulegen.
  - **Wichtige öffentliche Methoden und gekapselte Geschäftslogik**:
    - Methoden zum Abrufen des Sichtbarkeitsstatus eines bestimmten Merkmals.
    - Methoden zum Aktualisieren des Sichtbarkeitsstatus, wahrscheinlich durch Interaktion mit `Configuration::updateValue()`.
    - Potenziell Modifikation von `getFeatures()` oder ähnlichen Methoden, um Ergebnisse basierend auf der Sichtbarkeit zu filtern.
- `hidefeatures/override/classes/index.php`

  - **Klassenname & Elternklasse**: Keine Klassendatei, typischerweise eine leere `index.php`, um die Verzeichnisauflistung zu verhindern.
  - **Verantwortlichkeit**: Standardpraxis für `override`-Verzeichnisse, um direkten Zugriff zu verhindern und die Sicherheit zu gewährleisten. Sie enthält keinen funktionalen Code.
- `hidefeatures/override/classes/Product.php`

  - **Mit welcher Datenbanktabelle interagiert es**: `ps_product` und `ps_feature_product`.
  - **Erweitert `ObjectModel`**: Ja, es erweitert die Kern-`Product`-Klasse, die selbst `ObjectModel` erweitert.
  - **`$definition`-Felder**: Hier werden keine direkten Änderungen an `$definition` erwartet.
  - **Wichtige öffentliche Methoden und gekapselte Geschäftslogik**: Dieser Override ist entscheidend für die Filterung von Merkmalen auf der Produktseite. Er modifiziert wahrscheinlich Methoden wie `getFeatures()` oder `getFrontFeatures()` (falls sie in der Kern-`Product`-Klasse existieren), um:
    1. Alle zugewiesenen Merkmale für ein Produkt abzurufen.
    2. Diese Merkmale zu durchlaufen.
    3. Für jedes Merkmal seinen Sichtbarkeitsstatus unter Verwendung der Logik aus der überschriebenen `Feature`-Klasse zu überprüfen.
    4. Nur die Merkmale zurückzugeben, die als sichtbar markiert sind.
       Dies stellt sicher, dass, wenn die Merkmale eines Produkts zur Anzeige abgerufen werden, die ausgeblendeten automatisch ausgeschlossen werden.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul scheint keine benutzerdefinierten JavaScript-Dateien zu enthalten. Seine Funktionalität ist primär serverseitig über PHP-Overrides und Smarty-Template-Logik.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul scheint keine benutzerdefinierten CSS-Dateien zu enthalten. Jegliche Stilgebung für die hinzugefügte Spalte im AdminFeaturesController würde typischerweise durch die Standard-Back-Office-CSS von PrestaShop gehandhabt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `hidefeatures/views/templates/front/hook/displayHiddenFeatures.tpl`
    - **Hook**: `displayHiddenFeatures` (benutzerdefinierter Hook, wahrscheinlich innerhalb der überschriebenen `Product`-Klasse oder eines Themes `product.tpl` aufgerufen)
    - **Ausgabe**: Dieses Template ist für das Rendern der Liste der Produktmerkmale auf der Front-Office-Produktseite verantwortlich. Es empfängt die gefilterte Liste der Merkmale (nachdem ausgeblendete durch den `Product`-Klassen-Override entfernt wurden) und zeigt sie im Standard-PrestaShop-Merkmals-Tabellen-/Listenformat an. Entwickler können dieses Template überprüfen, um zu verstehen, wie Merkmale iteriert und angezeigt werden.
- **Admin-Templates (`views/templates/admin/`)**:

  - `hidefeatures/views/templates/admin/_configure/helpers/list/list_content.tpl`
    - **Zweck**: Dieses Template ist ein Override für das Standard-PrestaShop-Listeninhalts-Template, das speziell innerhalb des `AdminFeaturesController` verwendet wird. Es ist für das Rendern der Zeilen der Merkmalslistentabelle im Back Office verantwortlich.
    - **Inhalt**: Es enthält Logik zur Anzeige der Spalte „Im Front Office aktiv“ (oder Ähnlichem) für jedes Merkmal, die einen visuellen Indikator (z. B. ein Häkchen, ein rotes X oder einen Umschalter) basierend auf dem Sichtbarkeitsstatus des Merkmals anzeigt. Dieses Template arbeitet in Verbindung mit dem `AdminFeaturesController`-Override, um die zusätzlichen Informationen darzustellen.
- **Front-Office-Templates (`views/templates/front/`)**:

  - Keine dedizierten eigenständigen Front-Office-Seitentemplates.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine neuen benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfiguration (welche Merkmale ausgeblendet/sichtbar sind) in der Tabelle `ps_configuration`. Die Konfigurationsschlüssel würden typischerweise einem Muster wie `HIDEFEATURES_FEATURE_ID_X` oder Ähnlichem folgen, wobei `X` die `id_feature` ist.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHiddenFeatures` | Benutzerdefinierter Hook, wahrscheinlich innerhalb von `product.tpl` oder über den `Product::getFrontFeatures()`-Override aufgerufen. | Rendert die gefilterte Liste der Produktmerkmale auf der Front-Office-Produktseite und stellt sicher, dass nur sichtbare Merkmale angezeigt werden. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts. | (Implizit, wenn das Modul die Merkmalssichtbarkeit beim Speichern des Produkts neu bewerten muss, obwohl nicht explizit als primärer Hook für die Kernfunktion dieses Moduls aufgeführt). |
| `actionFeatureSave` / `actionFeatureDelete` | Nach dem Speichern oder Löschen eines Merkmals. | (Implizit, wenn das Modul seine interne Konfiguration aktualisieren muss, wenn Merkmale hinzugefügt/entfernt werden). |
| `displayBackOfficeHeader` | Rendert Inhalte im `<head>`-Abschnitt des Back Office. | (Möglich, zum Einfügen von JS/CSS, falls für die Admin-Benutzeroberfläche erforderlich, aber nicht im Inventar vorhanden). |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und alle Anfragen bezüglich des Moduls „Ausgewählte Merkmale ausblenden“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
