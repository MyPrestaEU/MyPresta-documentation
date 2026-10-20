---
title: "Produktpreisspanne - von / bis - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produktpreisspanne - von / bis“ von MyPresta.eu."
sidebar:
  label: "Produktpreisspanne - von / bis - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product price range - from / to auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-price-range-from-to.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-price-range-from-to/)
>
> ---


# Produktpreisspanne - von / bis

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend für PrestaShop-Module. Keine speziellen Hosting-Anforderungen über eine standardmäßige PrestaShop-kompatible Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls navigieren Sie zu **Module > Modul-Manager** und klicken Sie neben „Produktpreisspanne - von / bis“ auf „Konfigurieren“. Sie sehen dann den Hauptkonfigurationsbildschirm.

#### Allgemeine Einstellungen

Dieser Abschnitt steuert das Kernverhalten des Moduls.

- **Preisspanne auf Produktliste anzeigen:**

  - **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob die „von [niedrigster Preis] bis [höchster Preis]“-Spanne auf Seiten angezeigt wird, die mehrere Produkte auflisten, wie z. B. Kategorieseiten, Suchergebnisse oder Module wie „Neue Produkte“ oder „Vorgestellte Produkte“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Produkte mit Kombinationen und variierenden Preisen zeigen eine Preisspanne auf allen Produktlistenseiten an.
    - *Wenn deaktiviert (NEIN):* Auf Produktlistenseiten wird nur ein Einzelpreis (normalerweise der Grundpreis oder der niedrigste Kombinationspreis) angezeigt, gemäß dem Standardverhalten von PrestaShop.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie T-Shirts verkaufen, die für kleine Größen 10 € und für große Größen 15 € kosten, wird bei Aktivierung dieser Option „von 10,00 € bis 15,00 €“ auf Ihrer T-Shirt-Kategorieseite angezeigt, was Kunden einen schnellen Überblick über die Preisoptionen gibt.
- **Preisspanne auf Produktseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob die Preisspanne auf der einzelnen Produktseite selbst angezeigt wird, typischerweise in der Nähe des Hauptproduktpreises.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Die Produktseite zeigt die Preisspanne für Produkte mit Kombinationen an und informiert den Kunden über die Preisvariationen, bevor er Optionen auswählt.
    - *Wenn deaktiviert (NEIN):* Die Produktseite zeigt nur einen Einzelpreis (normalerweise den Grundpreis oder den niedrigsten Kombinationspreis) an, gemäß dem Standardverhalten von PrestaShop.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Auf der Produktseite für einen maßgeschneiderten Computer zeigt die Aktivierung dieser Option „von 800,00 € bis 2500,00 €“ an, bevor der Kunde beginnt, CPU-, RAM- und Speicheroptionen auszuwählen, was klare Erwartungen setzt.
- **Mengenrabatte berücksichtigen:**

  - **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung bestimmt, ob das Modul mengenbasierte Preisreduzierungen (spezifische Preise für Mengen) bei der Berechnung des *niedrigsten* Preises in der Spanne berücksichtigen soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul berechnet den absolut niedrigsten möglichen Preis, einschließlich aller Mengenrabatte, für den „von“-Teil der Spanne. Wenn ein Produkt beispielsweise 10 € kostet, aber 8 €, wenn Sie 10 Einheiten kaufen, beträgt der „von“-Preis 8 €.
    - *Wenn deaktiviert (NEIN):* Mengenrabatte werden ignoriert, und der „von“-Preis basiert ausschließlich auf dem niedrigsten Kombinationspreis, ohne Berücksichtigung von Mengenrabatten.
  - **Empfohlener Wert:** JA (um sicherzustellen, dass der attraktivste und genaueste niedrigste Preis angezeigt wird).
  - **Händlerszenario / Beispiel:** Wenn Sie Stifte für 1 € pro Stück verkaufen, diese aber für 0,80 € anbieten, wenn sie in 100er-Packungen gekauft werden, stellt die Aktivierung dieser Option sicher, dass der „von“-Preis in Ihrer Produktliste 0,80 € widerspiegelt, wodurch das Produkt noch erschwinglicher erscheint.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Preisspanne auf Produktliste anzeigen | JA | Zeigt den „von/bis“-Preis auf Kategorie-, Such- und Listenseiten an. |
| Modulkonfiguration | Preisspanne auf Produktseite anzeigen | JA | Zeigt den „von/bis“-Preis auf der einzelnen Produktdetailseite an. |
| Modulkonfiguration | Mengenrabatte berücksichtigen | JA | Berücksichtigt mengenbasierte Preisreduzierungen bei der Berechnung des niedrigsten Preises in der Spanne. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Preisspanne wird auf meinen Produktseiten/Listen nicht angezeigt.**
A:

1. **Modulkonfiguration prüfen:** Gehen Sie zu **Module > Modul-Manager > Produktpreisspanne - von / bis > Konfigurieren**. Stellen Sie sicher, dass „Preisspanne auf Produktliste anzeigen“ und „Preisspanne auf Produktseite anzeigen“ beide auf **JA** eingestellt sind.
2. **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
3. **Produktkombinationen:** Hat das Produkt tatsächlich Kombinationen mit *unterschiedlichen* Preisen? Wenn alle Kombinationen den gleichen Preis haben, zeigt das Modul wahrscheinlich einen Einzelpreis an, da es keine Spanne anzuzeigen gibt.
4. **Theme-Kompatibilität:** Obwohl das Modul für eine breite Kompatibilität ausgelegt ist, können sehr stark angepasste Themes geringfügige Anpassungen erfordern. Wenn das Problem nach Überprüfung der oben genannten Punkte weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

**F2: Der „von“-Preis scheint meine Mengenrabatte nicht zu berücksichtigen.**
A:

1. **Modulkonfiguration prüfen:** Gehen Sie zu **Module > Modul-Manager > Produktpreisspanne - von / bis > Konfigurieren**. Stellen Sie sicher, dass „Mengenrabatte berücksichtigen“ auf **JA** eingestellt ist.
2. **Mengenrabatte überprüfen:** Überprüfen Sie nochmals, ob Ihre Mengenrabatte (spezifische Preise) für das Produkt und seine Kombinationen im PrestaShop Back Office korrekt konfiguriert sind.
3. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F3: Die Preisspanne sieht etwas seltsam aus oder ist nicht auf das Design meines Themes abgestimmt.**
A:
Das Modul versucht, sich nahtlos zu integrieren, aber jedes Theme ist einzigartig.

1. **Cache leeren:** Manchmal sind Styling-Probleme auf alte zwischengespeicherte Dateien zurückzuführen.
2. **Benutzerdefiniertes CSS:** Möglicherweise müssen Sie Ihrem Theme benutzerdefiniertes CSS hinzufügen, um das Erscheinungsbild anzupassen. Die CSS-Klassen des Moduls sind normalerweise gut definiert (siehe Abschnitt 7.5). Ein Webmaster kann Ihnen helfen, diese Klassen so anzupassen, dass sie zu Ihrem Theme passen.
3. **Support kontaktieren:** Wenn Sie mit CSS nicht vertraut sind, kann der MyPresta.eu-Support oft Anleitungen oder kleine CSS-Snippets zur Verfügung stellen.

**F4: Wird dieses Modul meinen Shop verlangsamen?**
A:
Das Modul ist auf Leistung optimiert. Es berechnet Preise effizient. Obwohl jedes Modul einen geringen Overhead verursacht, ist dieses Modul so konzipiert, dass es leichtgewichtig ist. Wenn Sie erhebliche Verlangsamungen bemerken, stellen Sie sicher, dass Ihr Server die empfohlenen Spezifikationen von PrestaShop erfüllt und dass andere Module keine Konflikte verursachen. Regelmäßiges Leeren des Caches hilft ebenfalls.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Produktpreisspanne - von / bis“ (`prange`) ist ein Standard-PrestaShop-Modul, das dem MVC-Muster folgt. Es arbeitet hauptsächlich, indem es sich in verschiedene Anzeigepunkte (`displayProductPriceBlock`, `displayProductListReviews` usw.) einklinkt, um seine berechnete Preisspanne einzufügen. Die Kernlogik befindet sich in der Hauptdatei `index.php`, die als Einstiegspunkt des Moduls fungiert und Konfiguration, Installation und Hook-Registrierung handhabt. Es nutzt die PrestaShop-Klassen `Product` und `SpecificPrice`, um die Preisspanne, einschließlich Mengenrabatten, zu berechnen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der Hauptmodulklasse gekapselt und wird über Hooks ausgeführt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Alle notwendigen Datenmanipulationen und Preisberechnungen werden mit den nativen PrestaShop-Klassen `Product` und `SpecificPrice` innerhalb der Hauptmoduldatei durchgeführt.

### 4.4 JavaScript-Assets (`views/js/`)

- **`prange/views/js/prange-hide-p.js`**
  - **Umfang:** Front-Office (Produktseite)
  - **Zweck:** Dieses Skript enthält wahrscheinlich Logik zum Ausblenden oder Ändern der Standard-Produktpreisanzeige auf der einzelnen Produktseite, wenn die Preisspanne des Moduls aktiv ist. Es könnte auf DOM-Änderungen oder Seitenladeereignisse warten, um sicherzustellen, dass die Spanne des Moduls der primäre angezeigte Preis ist.
- **`prange/views/js/prange-hide-pl.js`**
  - **Umfang:** Front-Office (Produktlistenseiten)
  - **Zweck:** Ähnlich wie `prange-hide-p.js`, aber speziell auf Produktlistenseiten (Kategorien, Suchergebnisse) ausgerichtet. Es wurde entwickelt, um die Standard-Einzelpreisanzeige auf diesen Seiten auszublenden oder anzupassen, um Platz für die Preisspanne des Moduls zu schaffen.
- **`prange/views/js/prange.js`**
  - **Umfang:** Front-Office
  - **Zweck:** Dies ist wahrscheinlich die Haupt-JavaScript-Datei für das Modul. Sie könnte enthalten:
    - Logik zur dynamischen Aktualisierung der Preisspanne, wenn Produktattribute über AJAX geändert werden (z. B. Auswahl einer Kombination).
    - Event-Listener für `prestashop.on`-Ereignisse im Zusammenhang mit Produktaktualisierungen.
    - Jegliche clientseitige Rendering oder Manipulation, die für die Anzeige der Preisspanne erforderlich ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`prange/views/css/prange.css`**
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet bietet die Standard-visuelle Darstellung für den Preisspannen-Text. Es definiert Stile für den Container, der den „von/bis“-Text enthält, Schriftgrößen, Farben, Ränder und potenziell responsive Anpassungen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler sollten den gerenderten HTML-Code inspizieren, um die spezifischen Klassen (z. B. `.prange-price-range`, `.prange-from`, `.prange-to`) zu identifizieren, die vom Modul verwendet werden. Diese können dann in der `custom.css` oder `theme.css` eines benutzerdefinierten Themes angesprochen werden, um das Erscheinungsbild anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Dieses Modul definiert basierend auf dem bereitgestellten Inventar keine expliziten Templates in einem `hook/`-Unterverzeichnis, aber die unten aufgeführten Templates werden effektiv über Hooks gerendert.
- **Admin-Templates (`views/templates/admin/`)**: Dieses Modul hat keine benutzerdefinierten Admin-Templates über das Standard-`getContent()`-Formular hinaus.
- **Front-Office-Templates (`views/templates/front/`)**:
  - **`prange/views/templates/prange-oneprice.tpl`**
    - **Zweck:** Dieses Template wird wahrscheinlich verwendet, wenn ein Produkt *keine* Kombinationen mit variierenden Preisen hat oder wenn das Modul feststellt, dass nur ein Einzelpreis angezeigt werden soll (z. B. wenn die „von“- und „bis“-Preise identisch sind). Es gewährleistet eine konsistente Formatierung auch für Einzelpreisprodukte, wenn das Modul aktiv ist.
    - **Gerendert über:** Wahrscheinlich in `displayProductPriceBlock` oder ähnliches eingehängt.
  - **`prange/views/templates/prange.tpl`**
    - **Zweck:** Dies ist das primäre Template zur Anzeige der tatsächlichen „von [niedrigster Preis] bis [höchster Preis]“-Spanne. Es empfängt die berechneten niedrigsten und höchsten Preise von der PHP-Logik des Moduls und formatiert sie zur Anzeige.
    - **Gerendert über:** Dieses Template wird gerendert, wenn das Modul in `displayProductPriceBlock` (für die Produktseite) und potenziell andere Hooks für Produktlistenseiten (z. B. `displayProductListReviews`, `displayProductPriceBlock` im Kontext der Produktliste oder durch Überschreiben von Core-Templates) eingehängt wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen (z. B. `PRANGE_DISPLAY_LIST`, `PRANGE_DISPLAY_PRODUCT`, `PRANGE_QUANTITY_DISCOUNT`) in der Standardtabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um die CSS- (`prange.css`) und JavaScript-Dateien (`prange.js`, `prange-hide-p.js`, `prange-hide-pl.js`) des Moduls für das Front-Office-Styling und die Funktionalität einzubinden. |
| `displayProductPriceBlock` | Rendert Inhalte innerhalb des Produktpreisblocks auf Produktseiten und potenziell Produktlisten. | Dies ist der primäre Hook zum Einfügen der berechneten Preisspanne in die Preisanzeige des Produkts. Das Modul prüft wahrscheinlich den `type`-Parameter dieses Hooks, um den Kontext (Produktseite vs. Liste) zu bestimmen. |
| `displayProductListReviews` | Rendert Inhalte in der Nähe von Produktbewertungen auf Produktlistenseiten. | Obwohl nach Bewertungen benannt, wird dieser Hook oft von Modulen verwendet, um zusätzliche Informationen (wie Preisspannen) in Produktlistenelemente einzufügen. |
| `displayProductExtraContent` | Rendert zusätzliche Inhaltsblöcke auf der Produktseite. | Könnte als alternativer oder ergänzender Ort für die Preisspanne auf der Produktseite verwendet werden. |
| `displayAfterProductThumbs` | Rendert Inhalte nach den Produktvorschaubildern auf der Produktseite. | Ein weiterer potenzieller Ort für die Anzeige der Preisspanne auf der Produktseite. |
| `displayProductButtons` | Rendert Inhalte in der Nähe von Produktaktionsschaltflächen (z. B. In den Warenkorb legen). | Weniger wahrscheinlich für die Preisspanne, aber möglich für kontextbezogene Informationen. |
| `displayFooterProduct` | Rendert Inhalte im Fußbereich der Produktseite. | Ein Fallback oder alternativer Ort für die Preisspanne auf der Produktseite. |
| `displayProductAdditionalInfo` | Rendert zusätzliche Informationen auf der Produktseite. | Ein gängiger Hook zum Einfügen benutzerdefinierter Produktdetails. |
| `displayProductPrice` | Rendert den Produktpreis selbst. | Dieser Hook wird oft von Modulen überschrieben oder erweitert, die die Preisanzeige ändern. |
| `actionProductUpdate` | Wird ausgeführt, nachdem ein Produkt im Back Office aktualisiert wurde. | Könnte verwendet werden, um modulspezifische Caches zu leeren oder Preisspannen neu zu indizieren, wenn das Modul einen eigenen Cache verwaltet. |
| `actionProductAdd` | Wird ausgeführt, nachdem ein neues Produkt hinzugefügt wurde. | Ähnlich wie `actionProductUpdate`. |
| `actionProductDelete` | Wird ausgeführt, nachdem ein Produkt gelöscht wurde. | Ähnlich wie `actionProductUpdate`. |

*Hinweis: Die genauen verwendeten Hooks können je nach Modulversion und PrestaShop-Version leicht variieren. Die obige Liste stellt gängige Hooks für die Funktionalität dieses Moduls basierend auf seiner Beschreibung dar.*

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und dedizierten Entwickler-Support für das Modul „Produktpreisspanne - von / bis“ verweisen wir auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Stellen Sie sicher, dass Sie die neueste Version des Moduls verwenden, um optimale Leistung und Kompatibilität mit Ihrem PrestaShop-Shop zu gewährleisten.
