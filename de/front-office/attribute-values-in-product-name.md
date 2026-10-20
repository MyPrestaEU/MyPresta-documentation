---
title: "Attributwerte im Produktnamen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Attributwerte im Produktnamen“ von MyPresta.eu."
sidebar:
  label: "Attributwerte im Produktnamen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Attribute values in product name auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/attribute-values-in-product-name.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/attribute-values-in-product-name/)
>
> ---


# Attributwerte im Produktnamen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation des Moduls auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen.

#### CSS-Klasse des Produktnamens

- **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, die CSS-Klasse des HTML-Elements anzugeben, das den Produktnamen auf Ihren Produktseiten anzeigt. Das Modul muss diese Klasse kennen, damit es das Produktnamen-Element korrekt identifizieren und ändern kann, wenn ein Kunde eine neue Attributkombination auswählt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn eine korrekte CSS-Klasse eingegeben wird:* Das Modul findet den Produktnamen auf der Seite erfolgreich und fügt die ausgewählten Attributwerte dynamisch hinzu.
  - *Wenn eine falsche oder keine CSS-Klasse eingegeben wird:* Das Modul kann das Produktnamen-Element nicht finden, und daher werden die Attributwerte nicht zum Produktnamen hinzugefügt. Der Produktname bleibt statisch.
- **Empfohlener Wert:** Dieser Wert hängt von Ihrem PrestaShop-Theme ab.
  - Für **PrestaShops Standard-Themes (Classic)** ist eine gängige Klasse für den Produktnamen `h1.product-detail-name` oder `h1[itemprop="name"]`. Möglicherweise müssen Sie Ihre Produktseite mit den Entwicklertools Ihres Browsers überprüfen, um die genaue Klasse oder ID des `<h1>`-Tags zu finden, das den Produktnamen enthält.
  - Wenn Sie unsicher sind, versuchen Sie zuerst `h1.product-detail-name`. Wenn es nicht funktioniert, müssen Sie Ihren Theme-Entwickler konsultieren oder die Browser-Entwicklertools verwenden (Rechtsklick auf den Produktnamen, „Untersuchen“ auswählen), um den korrekten CSS-Selektor für die Hauptüberschrift des Produktnamens zu finden.
- **Händlerszenario / Beispiel:**
  - Sie haben ein benutzerdefiniertes Theme installiert, und der Produktname ist in einem `<h2>`-Tag mit der Klasse `my-custom-product-title` umschlossen. Sie würden `h2.my-custom-product-title` in dieses Feld eingeben.
  - Wenn Ihr Theme die Standardstruktur des PrestaShop Classic-Themes verwendet, sollte die Eingabe von `h1.product-detail-name` perfekt funktionieren und sicherstellen, dass, wenn ein Kunde „Blau“ für ein Hemd auswählt, der Titel von „T-Shirt“ zu „T-Shirt (Blau)“ aktualisiert wird.

#### Andere Konfigurationsschlüssel (Intern)

Möglicherweise sehen Sie andere Konfigurationsschlüssel wie `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `mypresta_updates`, `update_`, `updatev_`. Dies sind interne Einstellungen, die von PrestaShop und MyPresta.eu zur Verwaltung von Modul-Updates und Spracheinstellungen verwendet werden. Sie müssen nicht mit diesen interagieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | CSS-Klasse des Produktnamens | `h1.product-detail-name` (für Classic-Theme) | Gibt den CSS-Selektor für das Produktnamen-Element an. Wesentlich, damit das Modul den Produkttitel auf der Produktseite identifizieren und ändern kann. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Produktname ändert sich nicht, wenn ich Attribute auswähle. Was ist falsch?**
A: Der häufigste Grund ist eine falsche Einstellung der „CSS-Klasse des Produktnamens“.
- **Lösung**:
1. Gehen Sie in Ihrem Browser zu Ihrer Produktseite.
2. Klicken Sie mit der rechten Maustaste auf den Produktnamen und wählen Sie „Untersuchen“ (oder „Element untersuchen“).
3. Suchen Sie nach dem `<h1>`- oder `<h2>`-Tag, das den Produktnamen enthält. Notieren Sie dessen Klasse (z. B. `class="product-detail-name"`) oder ID (z. B. `id="product_name"`).
4. Geben Sie den korrekten CSS-Selektor in die Konfiguration des Moduls ein. Wenn das Tag beispielsweise `<h1 class="my-product-title">` ist, würden Sie `h1.my-product-title` eingeben. Wenn es `<h2 id="product_heading">` ist, würden Sie `h2#product_heading` eingeben.
5. Speichern Sie die Modulkonfiguration und leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren).

**F: Das Modul funktionierte anfangs, aber nach der Aktualisierung meines Themes funktioniert es nicht mehr.**
A: Theme-Updates ändern oft die HTML-Struktur und CSS-Klassen.
- **Lösung**: Überprüfen Sie die Einstellung „CSS-Klasse des Produktnamens“ wie oben beschrieben erneut. Ihr neues Theme verwendet möglicherweise eine andere Klasse oder ID für den Produktnamen.

**F: Wirkt sich dieses Modul auf meine SEO aus?**
A: Nein, dieses Modul ändert den Produktnamen nur dynamisch auf der Client-Seite (im Browser des Kunden) mithilfe von JavaScript. Es ändert nicht den ursprünglichen Produktnamen, der in Ihrer Datenbank gespeichert ist, oder das `<h1>`-Tag, das Suchmaschinen typischerweise indizieren. Ihre SEO bleibt unberührt.

**F: Unterstützt dieses Modul mehrere Sprachen?**
A: Ja, das Modul arbeitet mit den Attributwerten, wie sie in Ihrem PrestaShop Back Office konfiguriert sind, die bereits mehrsprachig kompatibel sind. Das Modul hängt einfach die aktuell ausgewählten Attributwerte in der aktiven Sprache an den Produktnamen an.

**F: Ich sehe die Attributwerte, aber sie sind falsch formatiert (z. B. falsche Schriftart, Farbe).**
A: Das Modul hängt Text an ein vorhandenes HTML-Element an. Seine Formatierung wird von der CSS Ihres Themes für dieses Produktnamen-Element geerbt.
- **Lösung**: Wenn Sie die angehängten Attributwerte anders gestalten möchten, benötigen Sie benutzerdefiniertes CSS. Sie können das Produktnamen-Element ansprechen und möglicherweise Pseudo-Elemente oder spezifische Selektoren verwenden, wenn das Modul den angehängten Text in ein eindeutiges Span-Element einschließt (obwohl dieses Modul typischerweise nur Text anhängt). Ein Webentwickler kann Ihnen mit benutzerdefiniertem CSS helfen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler, Webmaster und Agenturen.

### 4.1 Architekturübersicht

Das Modul „Attributwerte im Produktnamen“ (`anpn`) ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf die clientseitige Manipulation im Front-Office konzentriert. Es nutzt das Hook-System von PrestaShop, um sein JavaScript in den Produktseiten-Header einzufügen. Die Kernlogik befindet sich in einer einzigen JavaScript-Datei, die auf Änderungen in den Produktattributauswahlen lauscht und den Textinhalt des Produktnamens dynamisch aktualisiert. Es führt keine neuen Datenbanktabellen oder komplexe serverseitige Logik über seine Konfiguration hinaus ein.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Alle Front-Office-Funktionalitäten werden über JavaScript abgewickelt, das über Hooks injiziert wird.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration wird direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen definiert. Das Modul arbeitet direkt mit Konfigurationswerten und Front-Office-DOM-Manipulation.

### 4.4 JavaScript-Assets (`views/js/`)

- **`anpn/views/js/anpn.js`**
  - **Umfang**: Front-Office (Produktseite).
  - **Zweck**: Dieses Skript ist für die dynamische Aktualisierung des Produktnamens verantwortlich.
  - **Funktionalität**:
    1. **DOM Ready / `prestashop.on`**: Es wartet darauf, dass das DOM vollständig geladen ist, und lauscht speziell auf das `updatedProduct`-Ereignis, das von PrestaShops Kern-JavaScript ausgelöst wird, wenn eine Produktkombination geändert wird (z. B. durch Auswahl einer anderen Größe oder Farbe).
    2. **Produktnamen-Identifikation**: Es ruft den CSS-Selektor für den Produktnamen aus der Modulkonfiguration ab (über die globale Variable `anpn_pn_class` oder einen ähnlichen Mechanismus). Es verwendet dann diesen Selektor, um das Ziel-HTML-Element auf der Seite zu finden.
    3. **Attributwert-Extraktion**: Wenn `updatedProduct` ausgelöst wird, greift es auf die aktuellen Produktkombinationsdaten (die die ausgewählten Attributwerte enthalten) aus der Ereignisnutzlast zu.
    4. **Dynamische Aktualisierung**: Es konstruiert eine Zeichenfolge der ausgewählten Attributwerte (z. B. „(M, Blau)“) und hängt diese an den ursprünglichen Produktnamen an (den es typischerweise beim ersten Laden speichert oder aus einem Datenattribut abruft).
    5. **DOM-Manipulation**: Das Skript aktualisiert den `textContent` oder `innerText` des identifizierten Produktnamen-Elements mit der neuen, kombinierten Zeichenfolge.
  - **Abhängigkeiten**: Basiert auf jQuery (falls PrestaShop 1.7.x) oder nativen DOM-APIs und dem `prestashop.on`-Ereignissystem von PrestaShop.

### 4.5 CSS-Stylesheets (`views/css/`)

- Es werden keine benutzerdefinierten CSS-Dateien vom Modul bereitgestellt. Die angehängten Attributwerte erben die Formatierung des vorhandenen Produktnamen-Elements im Theme.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Es werden keine benutzerdefinierten Template-Dateien vom Modul bereitgestellt. Die gesamte Ausgabe wird von der Hauptmoduldatei (`anpn.php`) für die Konfiguration und JavaScript für die Front-Office-Anzeige verarbeitet.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration`:
    - `ANPN_PN_CLASS`: Speichert die CSS-Klasse/den Selektor für das Produktnamen-Element.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um das JavaScript des Moduls (`anpn.js`) zu registrieren und den Konfigurationswert `ANPN_PN_CLASS` an das Front-End-Skript zu übergeben. |
  | `displayProductAdditionalInfo` | Auf der Produktseite, typischerweise unterhalb der Hauptproduktinformationen. | Obwohl in diesem Modul nicht explizit für die visuelle Ausgabe verwendet, ist es ein gängiger Hook für Module, um Inhalte oder Skripte auf der Produktseite einzufügen. Im Kontext dieses Moduls könnte es verwendet werden, um sicherzustellen, dass das JS zur richtigen Zeit geladen wird, oder es könnte eine Legacy-Hook-Registrierung sein. Die primäre Interaktion erfolgt über `displayHeader` und das `updatedProduct`-Ereignis. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Attributwerte im Produktnamen“ verweisen wir Sie auf Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
