---
title: "Preis in verschiedenen Währungen gleichzeitig anzeigen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Preis in verschiedenen Währungen gleichzeitig anzeigen“ von MyPresta.eu."
sidebar:
  label: "Preis in verschiedenen Währungen gleichzeitig anzeigen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Show price in different currencies at the same time auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/show-price-in-different-currencies-at-the-same-time.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/show-price-in-different-currencies-at-the-same-time/)
>
> ---


# Preis in verschiedenen Währungen gleichzeitig anzeigen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Preis in verschiedenen Währungen gleichzeitig anzeigen“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren und neben dem Modulnamen auf „Konfigurieren“ klicken.

Die Konfigurationsseite bietet eine Reihe von Optionen, um zu steuern, wie und wo die Preise in mehreren Währungen angezeigt werden.

#### Allgemeine Einstellungen

- **Multi-Währungs-Preisanzeige aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul beginnt, Preise in mehreren Währungen gemäß Ihren anderen Einstellungen anzuzeigen.
    - *Wenn deaktiviert:* Das Modul funktioniert nicht mehr, und nur der Preis in der primären Währung wird angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten oder Wartungsarbeiten durchführen, können Sie es vorübergehend deaktivieren. Für den normalen Betrieb sollte es immer aktiviert sein.
- **Anzuzeigende Währungen auswählen:**

  - **Was diese Einstellung bewirkt:** Hier können Sie auswählen, welche zusätzlichen Währungen, neben der primären, Sie anzeigen möchten. Sie sehen normalerweise eine Liste aller aktiven Währungen in Ihrem PrestaShop-Shop.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn ausgewählt:* Preise werden in den ausgewählten Währungen angezeigt.
    - *Wenn nicht ausgewählt:* Preise werden in dieser spezifischen Währung nicht angezeigt.
  - **Empfohlener Wert:** Wählen Sie alle Währungen aus, die für Ihre internationalen Zielmärkte relevant sind.
  - **Händlerszenario / Beispiel:** Wenn Sie an Kunden in der Eurozone, den USA und Großbritannien verkaufen, würden Sie EUR, USD und GBP auswählen.
- **Auf Produktlistenseiten anzeigen (Kategorien, Suchergebnisse usw.):**

  - **Was diese Einstellung bewirkt:** Steuert, ob die Preise in mehreren Währungen auf Seiten erscheinen, die mehrere Produkte auflisten (z. B. Kategorieseiten, Suchergebnisse, Herstellerseiten).
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Preise in mehreren Währungen sind unter dem Hauptpreis auf Produktkarten sichtbar.
    - *Wenn deaktiviert:* Preise in mehreren Währungen erscheinen nur auf der einzelnen Produktdetailseite.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Die Aktivierung bietet sofortige Preisklarheit, während Kunden stöbern, und hilft ihnen, Produkte schnell in ihrer bevorzugten Währung zu vergleichen.
- **Auf Produktdetailseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob die Preise in mehreren Währungen auf der einzelnen Produktseite erscheinen.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Preise in mehreren Währungen sind in der Nähe des Hauptpreises auf der Produktseite sichtbar.
    - *Wenn deaktiviert:* Preise in mehreren Währungen werden auf der Produktseite nicht angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Dies ist entscheidend für Kunden, die eine endgültige Entscheidung treffen, insbesondere wenn sie Produktkombinationen oder Mengenrabatte in Betracht ziehen, da das Modul sicherstellt, dass diese dynamischen Preise ebenfalls umgerechnet werden.
- **Preis-Anzeigeformat:**

  - **Was diese Einstellung bewirkt:** Definiert, wie die zusätzlichen Währungspreise formatiert werden (z. B. mit oder ohne Währungssymbol, Anzahl der Dezimalstellen). Dies nutzt in der Regel die native Währungsformatierung von PrestaShop.
  - **Auswirkungen der Änderung dieser Einstellung:** Ändert die visuelle Darstellung der umgerechneten Preise.
  - **Empfohlener Wert:** Verwenden Sie ein Format, das klar und konsistent mit internationalen Standards für jede Währung ist (z. B. „$100.00 USD“ oder „€100,00“).
  - **Händlerszenario / Beispiel:** Sie könnten wählen, „USD 100.00“ anstelle von „$100.00“ anzuzeigen, um Verwechslungen mit anderen auf Dollar lautenden Währungen zu vermeiden.
- **Position der zusätzlichen Preise:**

  - **Was diese Einstellung bewirkt:** Bestimmt, wo die zusätzlichen Währungspreise relativ zum Hauptproduktpreis platziert werden. Optionen könnten „Unter dem Hauptpreis“, „Neben dem Hauptpreis“ oder „In einem separaten Block“ sein.
  - **Auswirkungen der Änderung dieser Einstellung:** Ändert das visuelle Layout der Preise auf Ihren Produktseiten.
  - **Empfohlener Wert:** „Unter dem Hauptpreis“ ist oft am klarsten und am wenigsten aufdringlich.
  - **Händlerszenario / Beispiel:** Wenn Ihr Produktseitenlayout sehr kompakt ist, könnte die Platzierung der Preise darunter besser sein als daneben, um Überfüllung zu vermeiden.
- **Preise mit Kombinationen/Mengenrabatten aktualisieren:**

  - **Was diese Einstellung bewirkt:** Stellt sicher, dass, wenn ein Kunde eine andere Produktkombination (z. B. eine größere Größe mit einem anderen Preis) auswählt oder die Menge ändert (was einen Mengenrabatt auslöst), die angezeigten Preise in mehreren Währungen dynamisch aktualisiert werden, um den neuen Gesamtbetrag widerzuspiegeln.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul verwendet JavaScript, um die korrekten umgerechneten Preise in Echtzeit neu zu berechnen und anzuzeigen.
    - *Wenn deaktiviert:* Die zusätzlichen Preise werden möglicherweise nicht aktualisiert, was zu falschen Informationen für den Kunden führt.
  - **Empfohlener Wert:** JA (Entscheidend für Genauigkeit und Kundenvertrauen).
  - **Händlerszenario / Beispiel:** Ein Kunde wählt ein „Großes“ T-Shirt (das mehr kostet) oder fügt 10 Artikel hinzu (was einen Mengenrabatt auslöst). Diese Einstellung stellt sicher, dass er den korrekten umgerechneten Preis für das große T-Shirt oder den reduzierten Mengenpreis in seinen gewählten Währungen sieht.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Multi-Währungs-Preisanzeige aktivieren | JA | Aktiviert/deaktiviert die Kernfunktionalität des Moduls. |
| Modulkonfiguration | Anzuzeigende Währungen auswählen | Relevante Währungen auswählen | Bestimmt, welche zusätzlichen Währungen angezeigt werden. |
| Modulkonfiguration | Auf Produktlistenseiten anzeigen | JA | Zeigt Preise in mehreren Währungen auf Kategorie-, Such- usw. Seiten an. |
| Modulkonfiguration | Auf Produktdetailseite anzeigen | JA | Zeigt Preise in mehreren Währungen auf einzelnen Produktseiten an. |
| Modulkonfiguration | Preis-Anzeigeformat | Variiert (PrestaShop-Standardwerte verwenden) | Steuert die visuelle Formatierung der umgerechneten Preise. |
| Modulkonfiguration | Position der zusätzlichen Preise | Unter dem Hauptpreis | Legt das Layout der zusätzlichen Preise relativ zum Hauptpreis fest. |
| Modulkonfiguration | Preise mit Kombinationen/Mengenrabatten aktualisieren | JA | Stellt dynamische Preisaktualisierungen für Kombinationen und Rabatte sicher. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Preise in mehreren Währungen werden in meinem Shop nicht angezeigt.**
**A1:**

- **Modulstatus prüfen:** Stellen Sie zunächst sicher, dass die Option „Multi-Währungs-Preisanzeige aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
- **Ausgewählte Währungen:** Überprüfen Sie, ob Sie die spezifischen Währungen ausgewählt haben, die Sie in den Moduleinstellungen anzeigen möchten.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren) und Ihren Browser-Cache. Manchmal verhindert alter Cache-Inhalt die Anzeige neuer Module.
- **Theme-Kompatibilität:** Wenn Sie ein stark angepasstes Theme verwenden, kann es zu einem Konflikt kommen. Kontaktieren Sie den MyPresta.eu-Support mit Details zu Ihrem Theme.

**F2: Die Preise in anderen Währungen sind falsch oder werden nicht aktualisiert.**
**A2:**

- **Wechselkurse:** Stellen Sie sicher, dass Ihre PrestaShop-Wechselkurse aktuell sind. Gehen Sie in Ihrem Back Office zu **International > Währungen** und überprüfen Sie die Wechselkurse für jede Währung. Sie können diese normalerweise automatisch oder manuell aktualisieren.
- **Dynamische Update-Einstellung:** Stellen Sie sicher, dass „Preise mit Kombinationen/Mengenrabatten aktualisieren“ in der Modulkonfiguration aktiviert ist, wenn Sie erwarten, dass sich die Preise mit Produktoptionen ändern.
- **Cache:** Leeren Sie alle Caches (PrestaShop und Browser) nach der Aktualisierung der Wechselkurse.

**F3: Die Preise in mehreren Währungen sehen seltsam aus oder sind in meinem Theme nicht korrekt gestylt.**
**A3:**

- **Modulkonfiguration:** Überprüfen Sie die Einstellungen „Preis-Anzeigeformat“ und „Position der zusätzlichen Preise“ im Modul.
- **Theme-CSS:** Das CSS Ihres benutzerdefinierten Themes könnte das Standard-Styling des Moduls überschreiben. Dies erfordert in der Regel, dass ein Webmaster oder Entwickler das CSS überprüft. Sie können oft benutzerdefiniertes CSS zu Ihrem Theme hinzufügen, um das Erscheinungsbild anzupassen.
- **Support kontaktieren:** Wenn Sie Styling-Probleme nicht lösen können, senden Sie Screenshots und Ihre Shop-URL an den MyPresta.eu-Support, um Hilfe zu erhalten.

**F4: Wird dieses Modul meinen Shop verlangsamen?**
**A4:** Das Modul ist leichtgewichtig konzipiert. Es ruft hauptsächlich vorhandene Wechselkurse ab und führt einfache Berechnungen durch. Die dynamischen Updates für Kombinationen verwenden JavaScript, das clientseitig ausgeführt wird. In den meisten Fällen sollte die Leistungseinbuße vernachlässigbar sein. Stellen Sie sicher, dass Ihr Server die Mindestanforderungen von PrestaShop für optimale Leistung erfüllt.

**F5: Wie übersetze ich den Text des Moduls (z. B. „Preis in USD“)?**
**A5:** Sie können alle vom Modul hinzugefügten Textzeichenfolgen über die PrestaShop-Übersetzungsoberfläche übersetzen:

- Navigieren Sie zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“.
- Wählen Sie Ihr Theme, Ihre Sprache und dann das Modul „Preis in verschiedenen Währungen gleichzeitig anzeigen“.
- Sie können dann die Übersetzungen für alle vom Modul eingeführten Phrasen bearbeiten.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Architektur des Moduls „Preis in verschiedenen Währungen gleichzeitig anzeigen“ und richtet sich an Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das Modul `multiprice` (interner Name `ajax_multiprice`) ist ein Standard-PrestaShop-Modul, das sich hauptsächlich auf die Front-Office-Anzeige konzentriert. Es nutzt das Hook-System von PrestaShop, um Informationen zu Preisen in mehreren Währungen in Produktlisten und Produktdetailseiten einzufügen. Die Kernlogik befindet sich in der Hauptmoduldatei und verwaltet die Konfiguration und Hook-Registrierung. Clientseitiges JavaScript wird für dynamische Preisaktualisierungen verwendet, wenn sich Produktkombinationen oder Mengen ändern, um eine Echtzeitgenauigkeit ohne vollständige Seitenneuladungen zu gewährleisten. Es führt keine benutzerdefinierten Datenbanktabellen oder komplexen ObjectModels ein, sondern stützt sich stattdessen auf die vorhandenen Währungs- und Produktpreismechanismen von PrestaShop.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt, und Front-Office-Interaktionen werden über Hooks und clientseitiges JavaScript verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/`. Seine Logik ist in der Hauptmoduldatei `ajax_multiprice.php` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

- **`multiprice/lib/searchTool/views/js/autocomplete.js`**

  - **Umfang:** Potenziell Front-Office (wenn für eine Suchfunktion innerhalb des Moduls verwendet, obwohl nicht direkt mit der Kern-Multi-Preisanzeige zusammenhängend).
  - **Verantwortlichkeit:** Diese Datei scheint Teil einer generischen Autocomplete-Suchwerkzeugbibliothek zu sein, die mit dem Modul gebündelt ist. Sie würde typischerweise AJAX-Anfragen für Suchvorschläge verarbeiten, an Eingabefelder binden und Ergebnisse anzeigen. Ihre direkte Relevanz für die Multi-Währungs-Preisanzeige ist wahrscheinlich minimal, es sei denn, das Modul integriert eine Suchfunktion, die auch Preise anzeigt.
  - **Details:** Bindet an Eingabefelder, lauscht auf `keyup`-Ereignisse, führt AJAX-Aufrufe an einen Backend-Endpunkt durch (nicht in den Controllern dieses Moduls definiert, wahrscheinlich ein generischer PrestaShop-Suchcontroller oder der Controller eines gebündelten Suchwerkzeugs) und manipuliert das DOM, um eine Dropdown-Liste mit Vorschlägen anzuzeigen.
- **`multiprice/views/js/multiprice.js`**

  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dies ist die zentrale JavaScript-Datei für die Multi-Währungs-Preisanzeige. Sie ist verantwortlich für die dynamische Aktualisierung der angezeigten Preise, wenn sich Produktattribute (Kombinationen) oder Mengen auf der Produktseite ändern.
  - **Details:**
    - Lauscht auf `change`-Ereignisse bei Produktkombinationsselektoren (z. B. `select`-Elemente für Attribute, Radio-Buttons).
    - Lauscht auf `change`- oder `blur`-Ereignisse im Mengeneingabefeld.
    - Greift in PrestaShops natives `prestashop.on('updatedProduct', ...)`-Ereignis (für PS 1.7+), das ausgelöst wird, wenn Produktdaten (einschließlich Preis) nach der Kombinationsauswahl aktualisiert werden.
    - Ruft den neuen Basispreis aus den aktualisierten Produktdaten ab.
    - Führt clientseitige Berechnungen durch, um den neuen Basispreis in die konfigurierten zusätzlichen Währungen umzurechnen, wobei Wechselkurse verwendet werden, die möglicherweise vom Backend übergeben oder in einer globalen JS-Variable gespeichert sind.
    - Aktualisiert die DOM-Elemente (`<span>`, `<div>`), in denen die zusätzlichen Währungspreise angezeigt werden.
    - Stellt die korrekte Formatierung der umgerechneten Preise sicher (Währungssymbol, Dezimalstellen).

### 4.5 CSS-Stylesheets (`views/css/`)

- **`multiprice/lib/searchTool/views/css/autocomplete.css`**

  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Gestaltet das Dropdown-Menü der Autocomplete-Suchergebnisse, einschließlich Vorschlägen, Hervorhebungen und allgemeinem Layout.
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf Klassen wie `.autocomplete-results`, `.autocomplete-item`, `.highlighted` ab. Entwickler können diese in der `custom.css` oder `theme.css` ihres Themes überschreiben.
- **`multiprice/views/css/multiprice.css`**

  - **Umfang:** Front-Office-Kunden-Styling.
  - **Verantwortlichkeit:** Bietet das Standard-Styling für die Multi-Währungs-Preisanzeige-Blöcke. Dies umfasst Schriftgrößen, Farben, Ränder und möglicherweise das Layout (z. B. vertikales Stapeln von Preisen).
  - **Wichtige CSS-Klassenselektoren:** Zielt auf spezifische Klassen ab, die von den Modul-Templates hinzugefügt wurden (z. B. `.multiprice-container`, `.multiprice-currency-item`, `.multiprice-price`). Entwickler können diese Selektoren im CSS ihres Themes überschreiben, um sie an das Design ihres Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`multiprice/lib/searchTool/views/scripts.tpl`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Template enthält wahrscheinlich das JavaScript und CSS für die `autocomplete.js`-Funktionalität. Es würde in `displayHeader` oder `displayFooter` eingehängt, um sicherzustellen, dass die notwendigen Assets geladen werden.
- **`multiprice/views/templates/multiprice-custom.tpl`**

  - **Umfang:** Front-Office (Hook-Template).
  - **Zweck:** Dieses Template ist wahrscheinlich ein Fallback oder ein alternatives Template zur Anzeige der Preise in mehreren Währungen, möglicherweise für bestimmte Hooks oder benutzerdefinierte Platzierungen. Es würde die HTML-Struktur enthalten, um den primären Preis zu rendern und dann die zusätzlichen Währungen zu durchlaufen, um deren umgerechnete Preise anzuzeigen.
- **`multiprice/views/templates/multiprice.tpl`**

  - **Umfang:** Front-Office (Hook-Template).
  - **Zweck:** Dies ist das primäre Template, das für das Rendern des Multi-Währungs-Preisblocks verantwortlich ist. Es wird über PrestaShop-Hooks in Produktlistenelemente und die Produktdetailseite eingefügt. Es empfängt ein Array von Währungen und deren umgerechnete Preise und formatiert diese gemäß der Modulkonfiguration.
  - **Variablen:** Erwartet Variablen wie `$product_price`, `$additional_currencies` (ein Array von Währungsobjekten mit umgerechneten Preisen), `$currency_format` usw.
- **`multiprice/views/templates/selectedProducts.tpl`**

  - **Umfang:** Front-Office.
  - **Zweck:** Der Name dieses Templates deutet darauf hin, dass es in einem Kontext verwendet werden könnte, in dem eine Liste ausgewählter Produkte angezeigt wird, möglicherweise in einer Warenkorbzusammenfassung, einer Vergleichsseite oder einem benutzerdefinierten Produktauswahl-Widget. Es würde eine Sammlung von Produkten durchlaufen und deren Preise anzeigen, möglicherweise mit der Multi-Währungsfunktion.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen (z. B. aktivierter Status, ausgewählte Währungen, Anzeigeoptionen) in der Tabelle `ps_configuration`, wobei Schlüssel mit `MULTIPRICE_` oder ähnlichem Präfix verwendet werden.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Um `multiprice.js` und `multiprice.css` (und potenziell `autocomplete`-Assets) auf Front-Office-Seiten einzubinden. |
| `displayProductPriceBlock` (Typ `after_price`) | Nach dem Hauptpreisblock auf Produktseiten. | Um den Inhalt von `multiprice.tpl` oder `multiprice-custom.tpl` einzufügen, der zusätzliche Währungspreise auf der Produktdetailseite anzeigt. |
| `displayProductListReviews` (oder ähnlich für Produktliste) | Innerhalb von Produktlistenelementen (z. B. Kategorieseiten). | Um den Inhalt von `multiprice.tpl` oder `multiprice-custom.tpl` einzufügen, der zusätzliche Währungspreise unter dem Hauptpreis auf Produktlistenseiten anzeigt. Der genaue Hook kann je nach PrestaShop-Version und Theme-Struktur variieren (z. B. kann `displayProductPriceBlock` auch hier verwendet werden, oder ein benutzerdefinierter Hook, der vom Theme bereitgestellt wird). |
| `actionProductUpdate` (oder ähnlich) | Nach der Aktualisierung eines Produkts im Back Office. | (Weniger wahrscheinlich für dieses Modul) Könnte verwendet werden, um den Cache in Bezug auf Produktpreise zu leeren, obwohl dies für seine Kernfunktion nicht unbedingt erforderlich ist. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seinen Inhalt rendert. | Um JavaScript- und CSS-Dateien für das Front Office zu registrieren und sicherzustellen, dass sie korrekt geladen werden. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und alle Anfragen bezüglich des Moduls „Preis in verschiedenen Währungen gleichzeitig anzeigen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei der Installation, Konfiguration und allen Problemen, die auftreten können, zur Verfügung.
