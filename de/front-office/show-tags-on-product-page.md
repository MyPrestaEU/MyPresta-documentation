---
title: "Tags auf Produktseite anzeigen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Tags auf Produktseite anzeigen“ von MyPresta.eu."
sidebar:
  label: "Tags auf Produktseite anzeigen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Show tags on product page auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/show-tags-on-product-page.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/show-tags-on-product-page/)
>
> ---


# Tags auf Produktseite anzeigen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL), die typischerweise in jeder modernen PrestaShop-Hosting-Umgebung zu finden sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dieses Modul verfügt über eine unkomplizierte Konfigurationsseite, die es Ihnen ermöglicht, seine Funktionalität schnell zu aktivieren oder zu deaktivieren und auszuwählen, wo die Tags auf Ihren Produktseiten erscheinen sollen.

**Zugriff:** Navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Tags auf Produktseite anzeigen“ und klicken Sie auf „Konfigurieren“.

#### **Modul aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für die Funktionalität des Moduls.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul beginnt, Produkt-Tags auf Ihren Front-Office-Produktseiten gemäß dem von Ihnen gewählten Hook anzuzeigen.
  - *Wenn deaktiviert:* Das Modul stellt die Anzeige von Produkt-Tags ein. Alle anderen Einstellungen werden gespeichert, bleiben aber inaktiv.
- **Empfohlener Wert:** JA
- **Händlerszenario / Beispiel:** Sie möchten das Modul testen oder Tags während einer Website-Neugestaltung vorübergehend ausblenden. Sie würden es deaktivieren und dann wieder aktivieren, wenn Sie bereit sind.

#### **Hook zum Anzeigen von Tags auswählen**

- **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung bestimmt, *wo* auf Ihrer Produktseite die Tags angezeigt werden. PrestaShop verwendet „Hooks“ als spezifische Punkte im Code der Seite, an denen Module ihre Inhalte einfügen können.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf `displayProductButtons` (PrestaShop 1.7+) eingestellt:* Tags erscheinen typischerweise in der Nähe des „In den Warenkorb“-Buttons oder anderer Produktaktionsbuttons. Dies ist oft eine prominente und effektive Position.
  - *Wenn auf `displayProductExtraContent` (PrestaShop 1.7+) eingestellt:* Tags erscheinen in einem dedizierten Bereich für zusätzliche Produktinhalte, oft unter den Hauptproduktinformationen oder innerhalb eines Tabs.
  - *Wenn auf `displayFooterProduct` (PrestaShop 1.7+) eingestellt:* Tags erscheinen am unteren Ende der Produktseite, oft über der Fußzeile der gesamten Website.
  - *Wenn auf `displayLeftColumnProduct` (PrestaShop 1.7+) eingestellt:* Tags erscheinen in der linken Spalte speziell auf der Produktseite.
  - *Wenn auf `displayRightColumnProduct` (PrestaShop 1.7+) eingestellt:* Tags erscheinen in der rechten Spalte speziell auf der Produktseite.
  - *Andere Hooks (z. B. `displayProductTab`, `displayProductTabContent`, `displayFooter`):* Die genaue Platzierung hängt von der Implementierung dieser Hooks in Ihrem Theme ab. `displayFooter` würde Tags in der allgemeinen Website-Fußzeile platzieren, was normalerweise nicht produktspezifisch ist.
- **Empfohlener Wert:** `displayProductButtons` oder `displayProductExtraContent` sind im Allgemeinen am effektivsten für Sichtbarkeit und Kontext. Experimentieren Sie, um zu sehen, was am besten zu Ihrem Theme passt.
- **Händlerszenario / Beispiel:** Sie möchten, dass Tags gut sichtbar sind, um die sofortige Entdeckung ähnlicher Produkte zu fördern, daher wählen Sie `displayProductButtons`. Wenn Sie sie weniger aufdringlich und als Teil ergänzender Informationen bevorzugen, könnte `displayProductExtraContent` besser sein.

#### **Titel für Tag-Block**

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, einen benutzerdefinierten Titel festzulegen, der über der Liste der Tags auf der Produktseite erscheint.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Titel eingegeben wird (z. B. „Produkt-Tags“, „Verwandte Keywords“):* Dieser Titel wird über der Liste der Tags angezeigt und bietet eine klare Überschrift für Ihre Kunden.
  - *Wenn leer gelassen:* Es wird kein Titel angezeigt, und nur die Liste der Tags erscheint.
- **Empfohlener Wert:** „Produkt-Tags“ oder „Keywords“
- **Händlerszenario / Beispiel:** Sie möchten den Abschnitt klar kennzeichnen, damit Kunden seinen Zweck verstehen. Das Festlegen des Titels auf „Verwandte Tags“ hilft, ihre Interaktion zu leiten.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren | JA | Aktiviert/deaktiviert die Tag-Anzeigefunktion des Moduls. |
| Modulkonfiguration | Hook zum Anzeigen von Tags auswählen | `displayProductButtons` oder `displayProductExtraContent` | Bestimmt die genaue Position der Tags auf der Produktseite. |
| Modulkonfiguration | Titel für Tag-Block | „Produkt-Tags“ | Legt eine Überschrift für die angezeigten Tags fest, was die Klarheit für Kunden verbessert. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul installiert und konfiguriert, aber die Tags werden auf meinen Produktseiten nicht angezeigt. Was ist falsch?**
**A1:**

- **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul in seiner Konfiguration „Aktiviert“ ist.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). PrestaShop speichert Inhalte oft im Cache, und die neue Modulausgabe wird möglicherweise erst nach dem Leeren des Caches angezeigt.
- **Produkt-Tags überprüfen:** Stellen Sie sicher, dass das spezifische Produkt, das Sie anzeigen, tatsächlich Tags zugewiesen hat. Bearbeiten Sie das Produkt im Back Office und überprüfen Sie den Tab „SEO“ oder „Tags“.
- **Theme-Kompatibilität:** Einige stark angepasste Themes könnten Standard-PrestaShop-Hooks überschreiben oder einzigartige Layouts haben. Versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme (z. B. Classic) zu wechseln, um zu sehen, ob die Tags erscheinen. Wenn ja, erfordert Ihr benutzerdefiniertes Theme möglicherweise eine kleine Anpassung (siehe F3).
- **Hook-Auswahl:** Überprüfen Sie nochmals, ob Sie einen geeigneten Hook in der Modulkonfiguration ausgewählt haben. Einige Hooks werden von Ihrem Theme möglicherweise nicht an einer sichtbaren Stelle gerendert.

**F2: Die Tags werden angezeigt, aber sie sehen schlicht aus oder passen nicht zum Stil meines Themes.**
**A2:**

- Das Modul bietet ein grundlegendes Styling. Wenn Sie möchten, dass sie perfekt zu Ihrem Theme passen, müssen Sie benutzerdefiniertes CSS hinzufügen.
- **So geht's:**
  1. Überprüfen Sie die Tags auf Ihrer Produktseite mit den Entwicklertools Ihres Browsers (Rechtsklick, dann „Untersuchen“).
  2. Identifizieren Sie die CSS-Klassen, die von den Tags verwendet werden (z. B. `ptags_block`, `ptags_item`).
  3. Fügen Sie benutzerdefinierte CSS-Regeln zur `custom.css`-Datei Ihres Themes hinzu (falls vorhanden) oder direkt in die `ptags.css`-Datei des Moduls (obwohl das direkte Ändern von Moduldateien nicht empfohlen wird, da Updates sie überschreiben würden).
  - **Beispiel-CSS:**

    ```
    .ptags\_block { margin-top: 20px; padding: 15px; border: 1px solid #eee; background-color: #f9f9f9;}.ptags\_block h3 { font-size: 18px; color: #333; margin-bottom: 10px;}.ptags\_item { display: inline-block; margin-right: 8px; margin-bottom: 8px;}.ptags\_item a { background-color: #007bff; color: white; padding: 5px 10px; border-radius: 3px; text-decoration: none; font-size: 14px;}.ptags\_item a:hover { background-color: #0056b3;}
    ```

**F3: Die Tags erscheinen, aber sie sind an einer ungünstigen Position, oder ich möchte sie an einer sehr spezifischen Stelle haben, die nicht in den Hook-Optionen aufgeführt ist.**
**A3:**

- Das Modul basiert auf Standard-PrestaShop-Hooks. Wenn Sie eine sehr spezifische, nicht standardmäßige Platzierung benötigen, erfordert dies normalerweise eine Theme-Modifikation.
- **Lösung:** Sie oder Ihr Webentwickler müssten die Anzeigefunktion des Moduls manuell in die Produktseiten-Vorlage Ihres Themes (`product.tpl` oder `product-details.tpl` in Ihrem Theme-Ordner) einfügen.
  - Finden Sie die genaue Stelle in der `.tpl`-Datei Ihres Themes, an der die Tags erscheinen sollen.
  - Fügen Sie den folgenden Smarty-Code ein: `{hook h='displayProductTags' product=$product}` (Hinweis: `displayProductTags` ist ein benutzerdefinierter Hook-Name, den Sie im Modul registrieren würden, oder Sie können `displayProductButtons` verwenden, wenn Sie dies konfiguriert haben).
  - Alternativ können Sie das Modul direkt aufrufen: `{Module::getInstanceByName('ptags')->hookDisplayProductTags(['product' => $product])}`. Dies ist direkter, aber weniger flexibel als die Verwendung eines Hooks.
- **Wichtig:** Dies erfordert grundlegende Kenntnisse der PrestaShop-Theme-Entwicklung.

**F4: Wird dieses Modul meinen Shop verlangsamen?**
**A4:**

- Nein, dieses Modul ist sehr leichtgewichtig. Es führt eine einfache Datenbankabfrage durch, um Tags abzurufen, die dem aktuellen Produkt zugeordnet sind. Dieser Vorgang ist durch den PrestaShop-Kern hochoptimiert und wird Ihre Seitenladezeiten nicht merklich beeinflussen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Tags auf Produktseite anzeigen“ (`ptags`) ist ein unkompliziertes PrestaShop-Modul, das zur Erweiterung der Front-Office-Funktionalität entwickelt wurde. Es folgt einer klassischen PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse und ihre `install()`, `uninstall()` und `hook`-Methoden nutzt. Es führt keine benutzerdefinierten Controller, Modelle oder komplexes JavaScript ein. Seine Kernfunktion besteht darin, Produkt-Tags abzurufen und sie über eine Smarty-Vorlage in einem ausgewählten Front-Office-Hook zu rendern.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der Hauptmodulklasse (`ptags/index.php`) gekapselt und wird über das PrestaShop-Hook-System ausgeführt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen ein. Es verwendet direkt die Kernklassen `Tag` und `Product` von PrestaShop, um die erforderlichen Daten abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Seine Funktionalität ist rein serverseitiges Rendern von HTML.

### 4.5 CSS-Stylesheets (`views/css/`)

- **Dateipfad**: `ptags/views/css/ptags.css`
- **Geltungsbereich**: Front-Office-Kunden-Styling.
- **Wichtige UI-Komponenten und Container, die es stylt**: Dieses Stylesheet bietet ein grundlegendes Styling für den Block, der die Produkt-Tags enthält, und die einzelnen Tag-Links.
- **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können**:
  - `.ptags_block`: Stylt den Hauptcontainerblock für die Tags.
  - `.ptags_block h3`: Stylt den Titel des Tag-Blocks.
  - `.ptags_item`: Stylt jedes einzelne Tag-Element (z. B. `display: inline-block`, Ränder).
  - `.ptags_item a`: Stylt die anklickbaren Tag-Links (z. B. Hintergrund, Farbe, Polsterung, `border-radius`).

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - **Dateipfad**: `ptags/views/front/ptags.tpl`
  - **Gerendert im Hook**: Diese Vorlage wird von den `hook`-Methoden des Moduls gerendert (z. B. `hookDisplayProductButtons`, `hookDisplayProductExtraContent` usw., je nach Konfiguration).
  - **Visuelle Blockausgabe**: Diese Vorlage ist für die Ausgabe der HTML-Struktur für den Tag-Block verantwortlich, einschließlich des optionalen Titels und der Liste der anklickbaren Tag-Links. Sie iteriert über die Variable `$tags` (ein Array von Tag-Objekten), die von der Hook-Methode des Moduls übergeben wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es basiert auf vorhandenen PrestaShop-Tabellen, hauptsächlich `ps_tag`, `ps_product_tag` und `ps_lang` für Tag-Daten.

  - Konfigurationseinstellungen werden in `ps_configuration` mit Schlüsseln wie `PTAGS_ENABLED`, `PTAGS_HOOK`, `PTAGS_TITLE` gespeichert.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um das CSS-Stylesheet des Moduls (`ptags.css`) zu laden. |
  | `displayProductButtons` | Auf der Produktseite, typischerweise in der Nähe des „In den Warenkorb“-Buttons. | Zeigt den Produkt-Tags-Block an. (PrestaShop 1.7+) |
  | `displayProductExtraContent` | Auf der Produktseite, in einem dedizierten Bereich für zusätzliche Inhalte. | Zeigt den Produkt-Tags-Block an. (PrestaShop 1.7+) |
  | `displayFooterProduct` | Am unteren Ende des Produktseiteninhalts. | Zeigt den Produkt-Tags-Block an. (PrestaShop 1.7+) |
  | `displayLeftColumnProduct` | In der linken Spalte speziell auf der Produktseite. | Zeigt den Produkt-Tags-Block an. (PrestaShop 1.7+) |
  | `displayRightColumnProduct` | In der rechten Spalte speziell auf der Produktseite. | Zeigt den Produkt-Tags-Block an. (PrestaShop 1.7+) |
  | `displayProductTab` | Fügt einen neuen Tab zur Produktseite hinzu. | (Wenn konfiguriert) Zeigt die Produkt-Tags innerhalb eines Tabs an. |
  | `displayProductTabContent` | Inhalt für einen Produktseiten-Tab. | (Wenn konfiguriert) Zeigt die Produkt-Tags als Inhalt für einen Tab an. |
  | `displayFooter` | In der allgemeinen Website-Fußzeile. | (Wenn konfiguriert) Zeigt den Produkt-Tags-Block in der globalen Fußzeile an. |
  | `displayLeftColumn` | In der linken Spalte von Seiten (nicht produktspezifisch). | (Wenn konfiguriert) Zeigt den Produkt-Tags-Block in der globalen linken Spalte an. |
  | `displayRightColumn` | In der rechten Spalte von Seiten (nicht produktspezifisch). | (Wenn konfiguriert) Zeigt den Produkt-Tags-Block in der globalen rechten Spalte an. |

  Das Modul registriert sich dynamisch für den in seiner Konfiguration ausgewählten Hook. Die Datei `index.php` enthält die `hook[HookName]`-Methoden, die die Produkt-ID abrufen, die zugehörigen Tags ermitteln und diese zur Darstellung an `ptags.tpl` übergeben.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Tags auf Produktseite anzeigen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
