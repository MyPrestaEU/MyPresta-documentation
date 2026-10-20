---
title: "Basispreise (ohne Rabatte) anzeigen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Basispreise (ohne Rabatte) anzeigen“ von MyPresta.eu."
sidebar:
  label: "Basispreise (ohne Rabatte) anzeigen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Display base prices (without discounts) auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/display-base-prices-without-discounts.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/display-base-prices-without-discounts/)
>
> ---


# Basispreise (ohne Rabatte) anzeigen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modulnamen auf „Konfigurieren“, um auf die Einstellungen zuzugreifen. Dies ist der Hauptbildschirm, auf dem Sie steuern, wie und wo die Basispreise angezeigt werden.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Modul aktivieren** | Dies ist der Hauptschalter, um die Funktionalität des Moduls ein- oder auszuschalten. | *Wenn aktiviert:* Das Modul beginnt, Basispreise in Ihrem Front-Office gemäß anderen Einstellungen anzuzeigen. *Wenn deaktiviert:* Das Modul stoppt die Anzeige von Basispreisen, und Ihr Shop kehrt zur Anzeige nur der aktuellen Preise zurück. | JA | Sie haben das Modul gerade installiert und möchten seine Funktionen aktivieren. |
| **Auf Produktseite anzeigen** | Steuert, ob der Basispreis auf einzelnen Produktdetailseiten angezeigt wird. | *Wenn aktiviert:* Der Originalpreis erscheint neben dem reduzierten Preis auf jeder Produktseite. *Wenn deaktiviert:* Der Basispreis wird auf Produktseiten nicht angezeigt, auch wenn er an anderer Stelle aktiviert ist. | JA | Sie möchten, dass Kunden, die ein bestimmtes Produkt ansehen, die Ersparnisse deutlich sehen. |
| **Auf Kategorieseiten anzeigen** | Steuert, ob der Basispreis auf Produktlistenseiten (z. B. Kategorieseiten, Suchergebnisse) angezeigt wird. | *Wenn aktiviert:* Der Originalpreis erscheint neben dem reduzierten Preis für jedes Produkt, das in Kategorien, Suchergebnissen usw. aufgeführt ist. *Wenn deaktiviert:* Der Basispreis wird auf Produktlistenseiten nicht angezeigt. | JA | Sie möchten, dass Kunden, die Kategorien durchsuchen, schnell reduzierte Artikel und ihre Ersparnisse erkennen. |
| **In Warenkorbzusammenfassung anzeigen** | Steuert, ob der Basispreis in der Warenkorbzusammenfassung angezeigt wird. | *Wenn aktiviert:* Der Originalpreis ist für jedes Produkt im Warenkorb des Kunden sichtbar, was die Gesamtersparnisse verdeutlicht. *Wenn deaktiviert:* Nur der aktuelle, reduzierte Preis wird im Warenkorb angezeigt. | NEIN (oder JA, je nach Theme) | Sie möchten Kunden an ihre Gesamtersparnisse erinnern, bevor sie zur Kasse gehen. Einige Themes haben jedoch möglicherweise keinen geeigneten Anzeigebereich, oder es könnte den Warenkorb überladen. Gründlich testen. |
| **Benutzerdefiniertes CSS für Basispreis** | Ermöglicht das Hinzufügen benutzerdefinierter CSS-Regeln zur Gestaltung des angezeigten Basispreises. | *Wenn mit CSS gefüllt:* Der Basispreis wird gemäß Ihrer Eingabe gestaltet (z. B. Schriftgröße, Farbe, Durchstreichung). *Wenn leer:* Das Modul verwendet seine Standardformatierung oder erbt Stile von Ihrem Theme. | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Sie möchten, dass der Basispreis ausgegraut und durchgestrichen wird, um ihn deutlich vom aktuellen Preis zu unterscheiden. |
| **Position des Basispreises** | Bestimmt, wo der Basispreis relativ zum aktuellen Preis eingefügt wird. | *Optionen: Vor aktuellem Preis, Nach aktuellem Preis.* *Wenn auf „Vor“ gesetzt:* Der Basispreis erscheint links vom aktuellen Preis. *Wenn auf „Nach“ gesetzt:* Der Basispreis erscheint rechts vom aktuellen Preis. | Vor aktuellem Preis | Sie möchten, dass der Kunde zuerst den Originalpreis und dann den neuen, niedrigeren Preis sieht. |

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren | JA | Aktiviert/deaktiviert die Kernfunktionalität des Moduls. |
| Modulkonfiguration | Auf Produktseite anzeigen | JA | Zeigt den Basispreis auf einzelnen Produktseiten an. |
| Modulkonfiguration | Auf Kategorieseiten anzeigen | JA | Zeigt den Basispreis auf Produktlistenseiten (Kategorien, Suche) an. |
| Modulkonfiguration | In Warenkorbzusammenfassung anzeigen | NEIN (oder JA, testen) | Zeigt den Basispreis im Warenkorb an. |
| Modulkonfiguration | Benutzerdefiniertes CSS für Basispreis | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Passt den visuellen Stil des Basispreises an. |
| Modulkonfiguration | Position des Basispreises | Vor aktuellem Preis | Steuert die Platzierung relativ zum aktuellen Preis. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Die Basispreise werden in meinem Shop nicht angezeigt, obwohl das Modul aktiviert ist.**
A:

1. **Moduleinstellungen überprüfen:** Stellen Sie sicher, dass „Modul aktivieren“ und die spezifischen Anzeigeoptionen (z. B. „Auf Produktseite anzeigen“) auf JA gesetzt sind.
2. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Der Smarty-Cache muss oft geleert werden, damit Template-Änderungen sichtbar werden.
3. **Auf Rabatte prüfen:** Stellen Sie sicher, dass die Produkte, die Sie testen, tatsächlich aktive Rabatte (Katalogpreisregeln, spezifische Preise oder prozentuale Reduzierungen) angewendet haben. Das Modul zeigt nur einen Basispreis an, wenn es einen Unterschied gibt.
4. **Theme-Kompatibilität:** Einige stark angepasste Themes können die Kernfunktionen der PrestaShop-Preisanzeige überschreiben. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

**F: Der Basispreis wird angezeigt, sieht aber mit meinem Theme nicht gut aus (falsche Farbe, Größe usw.).**
A: Verwenden Sie die Einstellung „Benutzerdefiniertes CSS für Basispreis“ in der Modulkonfiguration. Sie können CSS-Regeln hinzufügen, um das Design Ihres Themes anzupassen. Zum Beispiel, um es grau und durchgestrichen zu machen: `text-decoration: line-through; color: #999; font-size: 0.9em;`. Wenn Sie sich bei CSS unsicher sind, kann ein Webentwickler helfen.

**F: Wird dieses Modul meinen Shop verlangsamen?**
A: Das Modul ist leichtgewichtig konzipiert. Es überschreibt hauptsächlich eine PrestaShop-Kernklasse (`Product.php`), um den Basispreis abzurufen und ein kleines Template einzufügen. Die Leistungsauswirkungen sollten vernachlässigbar sein. Stellen Sie immer sicher, dass Ihr PrestaShop-Cache für optimale Geschwindigkeit aktiviert ist.

**F: Funktioniert dieses Modul mit mehrsprachigen Shops?**
A: Ja, das Modul funktioniert mit den Mehrsprachigkeitsfunktionen von PrestaShop. Die Preise werden in der Währung und im Format der aktiven Sprache/des aktiven Landes angezeigt.

**F: Ich sehe nach der Installation des Moduls einen „Override-Konflikt“-Fehler.**
A: Dieses Modul überschreibt die Klasse `Product.php`. Wenn ein anderes Modul ebenfalls versucht, dieselbe Klasse zu überschreiben, kann es zu einem Konflikt kommen. PrestaShop 1.7+ verfügt über ein besseres Override-Management, aber Konflikte können immer noch auftreten. Sie müssen entweder eines der widersprüchlichen Module deaktivieren oder die Overrides manuell zusammenführen (erfordert Entwicklerkenntnisse). Wenden Sie sich an den MyPresta.eu-Support, um Unterstützung zu erhalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Basispreise (ohne Rabatte) anzeigen“ funktioniert hauptsächlich durch das Überschreiben der Kernklasse `Product`, um eine Methode zum Abrufen des Basispreises des Produkts ohne Reduzierungen einzuführen. Es verwendet dann ein Smarty-Template, um diesen Preis im Front Office anzuzeigen, eingefügt über einen benutzerdefinierten Hook-Mechanismus. Die Konfiguration des Moduls wird über eine Standard-PrestaShop-Methode `getContent()` in der Hauptmoduldatei verwaltet.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität ist direkt in bestehende PrestaShop-Preisanzeigemechanismen und über ein Override integriert.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`baseprices/override/classes/index.php`**: Eine standardmäßige leere `index.php`-Datei, um das Auflisten von Verzeichnissen zu verhindern.
- **`baseprices/override/classes/Product.php`**:
  - **Klassenname**: `Product` (überschreibt die Kernklasse `Product`)
  - **Elternklasse**: `ProductCore`
  - **Verantwortlichkeit**: Dieses Override ist der Kern der Modulfunktionalität. Es führt eine neue Methode, `getBasePrice()`, ein, die den Preis des Produkts *vor* der Anwendung von spezifischen Preisen, Katalogpreisregeln oder Gruppenreduzierungen berechnet und zurückgibt. Diese Methode stellt sicher, dass der wahre Originalpreis immer zur Anzeige verfügbar ist. Sie beinhaltet typischerweise das Umgehen der Standard-Preisberechnungslogik, die Rabatte berücksichtigt.

### 4.4 JavaScript-Assets (`views/js/`)

- **`baseprices/views/js/baseprices-admin.js`**:
  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Verantwortlichkeit**: Dieses Skript behandelt wahrscheinlich dynamisches Verhalten oder Validierungen auf dem Konfigurationsformular des Moduls. Zum Beispiel könnte es Einstellungen basierend auf anderen Auswahlen ein-/ausblenden oder Echtzeit-Feedback für das benutzerdefinierte CSS-Feld bereitstellen.
- **`baseprices/views/js/baseprices.js`**:
  - **Geltungsbereich**: Front-Office.
  - **Verantwortlichkeit**: Dieses Skript ist dafür verantwortlich, den Basispreis dynamisch in das DOM einzufügen, wo immer dies erforderlich ist, insbesondere für AJAX-geladene Inhalte oder wenn sich Produktattribute ändern (z. B. Auswahl einer anderen Kombination auf der Produktseite). Es lauscht auf PrestaShop-Ereignisse wie `updateProduct` oder ähnliche Ereignisse, um die Preisanzeige zu aktualisieren. Es könnte auch die Gestaltung oder Sichtbarkeitsschalter für das Basispreiselement handhaben.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`baseprices/views/css/baseprices.css`**:
  - **Geltungsbereich**: Front-Office-Kundenstyling.
  - **Wichtige UI-Komponenten und Container, die es gestaltet**: Dieses Stylesheet bietet die Standard-visuelle Darstellung für den Basispreis. Es enthält typischerweise Regeln für:
    - `span.base-price` oder ähnliche Selektoren.
    - `text-decoration: line-through;` um den Preis durchzustreichen.
    - `color`, `font-size`, `margin`, `padding` um den Basispreis relativ zum aktuellen Preis zu positionieren und zu gestalten.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: `span.base-price`, `div.product-price-and-shipping .base-price`, etc. Entwickler können diese Klassen im benutzerdefinierten CSS ihres Themes ansprechen, um die Standardformatierung des Moduls zu überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`baseprices/views/templates/baseprices.tpl`**:
  - **Geltungsbereich**: Front-Office.
  - **Verantwortlichkeit**: Dieses Template ist die primäre Ausgabe zur Anzeige des Basispreises. Es ist so konzipiert, dass es überall dort eingebunden oder gerendert wird, wo der Preis eines Produkts angezeigt wird. Es empfängt typischerweise Variablen wie `$base_price` und `$current_price` und formatiert sie gemäß den Moduleinstellungen (z. B. benutzerdefiniertes CSS, Position). Es enthält die HTML-Struktur (z. B. `<span class="base-price">...</span>`), die das CSS anspricht.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert, wobei die Schlüssel mit `BASEPRICES_` präfixiert sind.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um die Front-Office-CSS- und JavaScript-Assets des Moduls zu laden. |
| `displayProductPriceBlock` | Innerhalb des Produktpreisanzeigeblocks auf Produktseiten und Listen. | Das Modul nutzt wahrscheinlich diesen Hook (oder ähnliche preisbezogene Hooks), um sein `baseprices.tpl`-Template einzufügen und den Basispreis neben dem aktuellen Preis anzuzeigen. |
| `actionProductUpdate` / `actionProductSave` | Nach der Aktualisierung oder Speicherung eines Produkts im Back Office. | Obwohl nicht explizit aufgeführt, könnten Module, die `Product.php` überschreiben, solche Hooks verwenden, um Caches zu leeren oder Produktdaten bei Bedarf neu zu indizieren, obwohl die Hauptfunktion dieses Moduls nur die Anzeige ist. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller sein Template rendert. | Wird verwendet, um Front-Office-JavaScript- und CSS-Dateien für die aktuelle Seite zu registrieren. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Basispreise (ohne Rabatte) anzeigen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
