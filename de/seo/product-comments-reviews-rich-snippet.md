---
title: "Produktkommentare - Rich Snippet für Bewertungen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produktkommentare - Rich Snippet für Bewertungen“ von MyPresta.eu."
sidebar:
  label: "Produktkommentare - Rich Snippet für Bewertungen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product Comments - Reviews rich snippet auf MyPresta.eu kaufen](https://mypresta.eu/modules/seo/product-comments-reviews-rich-snippet.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/seo/product-comments-reviews-rich-snippet/)
>
> ---


# Produktkommentare - Rich Snippet für Bewertungen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).
- **Abhängigkeit**: Dieses Modul erweitert die Funktionalität des **kostenlosen PrestaShop Produktkommentare Moduls**. Sie müssen das offizielle PrestaShop Produktkommentare Modul installiert und aktiv haben, damit dieses Modul korrekt funktioniert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dieses Modul verfügt über eine unkomplizierte Konfigurationsseite, die sich hauptsächlich auf das Aktivieren oder Deaktivieren seiner Kernfunktionalität und die Auswahl des Ortes konzentriert, an dem die Rich-Snippet-Daten eingefügt werden sollen.

**Zugriff:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie nach „Produktkommentare - Rich Snippet für Bewertungen“ und klicken Sie auf „Konfigurieren“.

#### **Rich Snippets aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls. Wenn aktiviert, beginnt das Modul, die notwendigen strukturierten Daten zu Ihren Produktseiten hinzuzufügen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul fügt den Rich-Snippet-Code in Ihre Produktseiten ein, sodass Google Sternenbewertungen und die Anzahl der Bewertungen in den Suchergebnissen anzeigen kann.
  - *Wenn deaktiviert:* Das Modul stoppt das Einfügen des Rich-Snippet-Codes. Ihre Produktlisten in den Google-Suchergebnissen werden auf Standardtext zurückgesetzt, ohne Sterne oder die Anzahl der Bewertungen.
- **Empfohlener Wert:** **JA** (Aktiviert). Der Hauptzweck dieses Moduls ist die Anzeige von Rich Snippets, daher sollte es fast immer aktiviert sein.
- **Händlerszenario / Beispiel:** Wenn Sie das Modul testen oder vorübergehend Bewertungsdaten aus den Suchergebnissen ausblenden möchten (z. B. während einer größeren Überarbeitung der Website), können Sie es deaktivieren. Andernfalls lassen Sie es aktiviert, um die Sichtbarkeit zu maximieren.

#### **Rich Snippets in Hook anzeigen**

- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen zu wählen, *wo* auf Ihrer Produktseite das Modul die strukturierten Daten einfügen soll. Obwohl die Daten für den Kunden unsichtbar sind, kann ihre Platzierung manchmal die Kompatibilität mit Themes oder anderen Modulen beeinflussen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Header“ eingestellt:* Die Rich-Snippet-Daten werden im `<head>`-Bereich des HTML Ihrer Produktseite platziert. Dies ist im Allgemeinen der gebräuchlichste und empfohlene Ort für strukturierte Daten.
  - *Wenn auf „Produkt“ eingestellt:* Die Rich-Snippet-Daten werden im Hauptinhaltsbereich des Produkts platziert.
  - *Wenn auf „Spalten“ eingestellt:* Die Rich-Snippet-Daten werden in einer der Seitenleisten Ihres Shops platziert (links oder rechts, je nach Layout Ihres Themes).
  - *Wenn auf „Footer“ eingestellt:* Die Rich-Snippet-Daten werden im `<footer>`-Bereich des HTML Ihrer Produktseite platziert.
- **Empfohlener Wert:** **Header**. Dies ist der standardmäßigste und robusteste Ort für strukturierte Daten, da er frühzeitig von Suchmaschinen-Crawlern verarbeitet wird und weniger wahrscheinlich mit visuellen Elementen oder anderen Skripten auf Ihrer Seite in Konflikt gerät.
- **Händlerszenario / Beispiel:** Wenn Sie unerwartete Probleme mit dem Layout Ihrer Produktseite oder anderen Modulen nach dem Aktivieren von Rich Snippets feststellen, könnten Sie versuchen, diesen Hook auf „Produkt“ oder „Footer“ umzustellen, um das Problem zu beheben. „Header“ ist jedoch normalerweise die sicherste Wahl.

#### **Kurze Rich Snippets anzeigen (nur Sterne)**

- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, zwischen der Anzeige des vollständigen Rich Snippets (Sterne + Anzahl der Bewertungen) oder einer „kurzen“ Version zu wählen, die nur die Sterne ohne die Anzahl der Bewertungen anzeigt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Google zeigt in den Suchergebnissen nur die Sternenbewertung an (z. B. „★★★★★ 4.5“), wobei der Teil „(X Bewertungen)“ weggelassen wird.
  - *Wenn deaktiviert:* Google zeigt sowohl die Sternenbewertung als auch die Anzahl der Bewertungen an (z. B. „★★★★★ 4.5 (12 Bewertungen)“).
- **Empfohlener Wert:** **NEIN** (Deaktiviert). Die Anzeige sowohl der Sterne als auch der Anzahl der Bewertungen liefert vollständigere Informationen und schafft oft mehr Vertrauen, insbesondere wenn Sie eine hohe Anzahl von Bewertungen haben.
- **Händlerszenario / Beispiel:** Wenn Sie auf vielen Produkten sehr wenige Bewertungen haben und der Meinung sind, dass die Anzeige von „1 Bewertung“ weniger beeindruckend aussehen könnte als nur die Sterne, könnten Sie diese Option aktivieren. Für die meisten Shops mit einer gesunden Anzahl von Bewertungen ist die Anzeige der Anzahl jedoch vorteilhaft.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Rich Snippets aktivieren / deaktivieren | JA (Aktiviert) | Aktiviert/deaktiviert die Rich-Snippet-Code-Injektion für Google-Suchergebnisse. |
| Modulkonfiguration | Rich Snippets in Hook anzeigen | Header | Bestimmt, wo der unsichtbare Rich-Snippet-Code auf der Produktseite platziert wird. „Header“ ist im Allgemeinen am besten für die Kompatibilität. |
| Modulkonfiguration | Kurze Rich Snippets anzeigen (nur Sterne) | NEIN (Deaktiviert) | Steuert, ob nur Sterne oder Sterne + Anzahl der Bewertungen in den Google-Suchergebnissen angezeigt werden. Es wird empfohlen, beides anzuzeigen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber keine Sterne in den Google-Suchergebnissen. Was ist falsch?**
A: Mehrere Faktoren könnten eine Rolle spielen:
1. **Google Crawling-Zeit:** Es dauert eine Weile, bis Google Ihre Website erneut crawlt und seinen Index aktualisiert. Dies kann von einigen Tagen bis zu einigen Wochen dauern, insbesondere bei neuen Seiten oder wesentlichen Änderungen.
2. **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren) nach der Konfiguration.
3. **Google Search Console:** Überprüfen Sie Ihre Google Search Console unter „Optimierungen“ auf „Bewertungs-Snippets“. Wenn Fehler vorliegen, zeigt Google die Snippets möglicherweise nicht an.
4. **Keine Bewertungen:** Stellen Sie sicher, dass das Produkt tatsächlich genehmigte Bewertungen in Ihrem Shop hat. Google zeigt keine Sterne an, wenn keine Bewertungen vorhanden sind.
5. **Produktkommentare-Modul:** Überprüfen Sie, ob das offizielle PrestaShop Produktkommentare-Modul installiert und aktiv ist. Dieses Modul ist davon abhängig.
6. **Googles Ermessen:** Obwohl das Modul die Daten bereitstellt, entscheidet Google letztendlich, ob Rich Snippets angezeigt werden. Sie können sich dafür entscheiden, sie nicht anzuzeigen, wenn sie den Inhalt als irrelevant oder von geringer Qualität erachten.

**F: Meine Produktseite sieht nach der Installation des Moduls kaputt aus.**
A: Dies ist höchst unwahrscheinlich, da das Modul nur unsichtbare strukturierte Daten einfügt. Sollte es jedoch passieren:
1. **Deaktivieren Sie das Modul:** Gehen Sie zum Modul-Manager und deaktivieren Sie „Produktkommentare - Rich Snippet für Bewertungen“. Wenn die Seite wieder normal aussieht, könnte das Modul die Ursache sein.
2. **Ändern Sie die Einstellung „Rich Snippets in Hook anzeigen“:** Versuchen Sie, den Hook von „Header“ auf „Produkt“ oder „Footer“ umzustellen. Manchmal können Theme-Konflikte bei bestimmten Hook-Platzierungen auftreten.
3. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Änderungen vorgenommen haben.

**F: Beeinflusst dieses Modul die Ladezeit meiner Website?**
A: Nein, die Auswirkungen auf die Ladezeit sind vernachlässigbar. Das Modul fügt lediglich einen kleinen Textblock (strukturierte Daten) zum HTML Ihrer Seite hinzu, der sehr leichtgewichtig ist und von Browsern und Suchmaschinen schnell verarbeitet wird.

**F: Kann ich das Aussehen der Sterne in den Google-Suchergebnissen anpassen?**
A: Nein, das Aussehen der Sterne und der Anzahl der Bewertungen in den Google-Suchergebnissen wird vollständig von der Google-Oberfläche gesteuert. Dieses Modul liefert die Daten; Google rendert sie. Sie können die Farbe, Größe oder den Stil der Sterne in den Suchergebnissen nicht ändern.

**F: Funktioniert dieses Modul mit benutzerdefinierten Themes?**
A: Ja, dieses Modul ist so konzipiert, dass es unabhängig von der visuellen Gestaltung Ihres Themes funktioniert. Es fügt strukturierte Daten in das HTML ein, was eine Standardpraxis ist. Solange Ihr benutzerdefiniertes Theme das Hook-System von PrestaShop korrekt implementiert, sollte das Modul ohne Probleme funktionieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Architektur des Moduls „Produktkommentare - Rich Snippet für Bewertungen“, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul `prrs` (Product Reviews Rich Snippet) ist ein leichtgewichtiges PrestaShop-Modul, das entwickelt wurde, um Schema.org `AggregateRating` strukturierte Daten in Produktseiten einzufügen. Es nutzt vorhandene Daten aus dem offiziellen `productcomments`-Modul. Das Modul arbeitet hauptsächlich, indem es sich in einen Anzeigepunkt (vom Händler konfigurierbar) einklinkt und ein Smarty-Template rendert, das die JSON-LD strukturierten Daten enthält. Es folgt einer Standard-PrestaShop-Modulstruktur mit einer Hauptmodulklasse und einigen unterstützenden Assets.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik wird innerhalb der Hauptmoduldatei `index.php` und der zugehörigen Templates verarbeitet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Es basiert hauptsächlich auf vorhandenen PrestaShop-Kernfunktionen und den Daten des `productcomments`-Moduls.

### 4.4 JavaScript-Assets (`views/js/`)

- **`prrs/lib/searchTool/views/js/autocomplete.js`**
  - **Umfang:** Back-Office (wahrscheinlich für ein internes Suchwerkzeug, obwohl nicht direkt von der Rich-Snippet-Funktionalität des Hauptmoduls verwendet).
  - **Verantwortlichkeit:** Dieses Skript scheint Teil eines generischen Autocomplete-Dienstprogramms zu sein. Es verarbeitet wahrscheinlich AJAX-Anfragen für Suchvorschläge, aktualisiert Eingabefelder und verwaltet die Anzeige von Suchergebnissen in einem Dropdown-Menü. Angesichts der Hauptfunktion des Moduls könnte dies ein Überbleibsel oder eine Abhängigkeit von einer gemeinsam genutzten Bibliothek sein. Es ist nicht direkt an der Rich-Snippet-Generierung beteiligt.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`prrs/lib/searchTool/views/css/autocomplete.css`**
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Bietet Styling für das oben erwähnte Autocomplete-Suchwerkzeug. Dies würde Stile für die Sucheingabe, Dropdown-Vorschläge, hervorgehobene Ergebnisse usw. umfassen. Nicht relevant für die Front-Office-Anzeige.
- **`prrs/views/css/prrs.css`**
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dieses Stylesheet ist wahrscheinlich minimal oder leer, da die Hauptfunktion des Moduls darin besteht, unsichtbare strukturierte Daten einzufügen. Wenn es Stile enthält, wären diese für sehr subtile, nicht-intrusive Elemente oder möglicherweise für eine visuelle Fallback-Lösung, falls die strukturierten Daten selbst eine sichtbare Komponente hätten (was bei Rich Snippets typischerweise nicht der Fall ist). Entwickler sollten diese Datei auf unerwartete visuelle Ausgaben überprüfen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`prrs/lib/searchTool/views/scripts.tpl`**
  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Template enthält wahrscheinlich das JavaScript für das Autocomplete-Suchwerkzeug (`autocomplete.js`) und möglicherweise andere verwandte Skripte oder Inline-Skriptkonfigurationen. Es würde in einem Admin-Kontext gerendert werden.
- **`prrs/views/templates/prrs-json.tpl`**
  - **Umfang:** Front-Office (Produktseite).
  - **Zweck:** Dies ist das Kerntemplate, das für die Generierung der JSON-LD strukturierten Daten für das `AggregateRating` Rich Snippet verantwortlich ist. Es ruft dynamisch die durchschnittliche Bewertung und die Anzahl der Bewertungen des Produkts aus dem `productcomments`-Modul ab und formatiert sie gemäß den Schema.org-Spezifikationen. Dieses Template wird gerendert, wenn die Option „Kurze Rich Snippets anzeigen“ deaktiviert ist.
  - **Wichtige Datenpunkte:** `product.id_product`, `product.name`, `product.link_rewrite`, `product.link`, `product.cover.bySize.home_default.url`, `average_grade`, `nb_comments`.
- **`prrs/views/templates/prrs.tpl`**
  - **Umfang:** Front-Office (Produktseite).
  - **Zweck:** Dieses Template ist wahrscheinlich ein Wrapper oder eine Alternative zu `prrs-json.tpl`, möglicherweise für ältere PrestaShop-Versionen oder spezifische Hook-Integrationen verwendet. Es generiert ebenfalls die Rich-Snippet-Daten. Es ist wichtig zu überprüfen, welches Template aktiv verwendet wird, basierend auf der `getContent()`-Logik des Moduls und der Hook-Registrierung.
- **`prrs/views/templates/shortprrs.tpl`**
  - **Umfang:** Front-Office (Produktseite).
  - **Zweck:** Dieses Template generiert ein vereinfachtes JSON-LD strukturiertes Daten-Snippet, das typischerweise nur die durchschnittliche Sternenbewertung ohne die explizite Anzahl der Bewertungen enthält. Es wird gerendert, wenn die Option „Kurze Rich Snippets anzeigen“ aktiviert ist.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es verwendet die Tabelle `ps_configuration`, um seine Einstellungen zu speichern (z. B. `PRRS_ENABLED`, `PRRS_HOOK`, `PRRS_SHORT`).
  - Es ruft Bewertungsdaten aus den Tabellen ab, die vom offiziellen `productcomments`-Modul erstellt wurden (z. B. `ps_product_comment`, `ps_product_comment_criterion`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt / Kontext | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert innerhalb des `<head>`-Bereichs der Seite. | Fügt JSON-LD strukturierte Daten für Rich Snippets frühzeitig beim Laden der Seite ein. Konfigurierbar über die Moduleinstellungen. |
| `displayProductAdditionalInfo` | Rendert innerhalb der Produktseite, typischerweise unterhalb der Hauptproduktdetails. | Alternativer Hook zum Einfügen von JSON-LD strukturierten Daten. Konfigurierbar über die Moduleinstellungen. |
| `displayLeftColumn` / `displayRightColumn` | Rendert innerhalb der jeweiligen Seitenleisten. | Weniger gebräuchlich, aber als alternativer Hook zum Einfügen von JSON-LD strukturierten Daten verfügbar. Konfigurierbar über die Moduleinstellungen. |
| `displayFooter` | Rendert innerhalb des `<footer>`-Bereichs der Seite. | Alternativer Hook zum Einfügen von JSON-LD strukturierten Daten, typischerweise am Ende der Seite. Konfigurierbar über die Moduleinstellungen. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien-Assets festlegt. | Wird verwendet, um CSS- und JavaScript-Dateien für das Front-Office zu registrieren. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets festlegt. | Wird verwendet, um CSS- und JavaScript-Dateien für das Back-Office zu registrieren (z. B. `autocomplete.js`, `autocomplete.css`). |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Produktkommentare - Rich Snippet für Bewertungen“ zur Verfügung.
