---
title: "Gezielte Suche – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gezielte Suche“ von MyPresta.eu."
sidebar:
  label: "Gezielte Suche – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Target search auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/target-search.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/target-search/)
>
> ---


# Gezielte Suche

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation klicken Sie neben dem Modul „Gezielte Suche“ auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen. Hier definieren Sie genau, wo die Suchmaschine nach Schlüsselwörtern suchen soll.

Die Konfigurationsseite zeigt eine Reihe von Kontrollkästchen an, die jeweils einem bestimmten Bereich Ihrer Produktdaten entsprechen.

- **Was diese Einstellung bewirkt:** Jedes Kontrollkästchen ermöglicht es Ihnen, die Suche innerhalb eines bestimmten Feldes Ihrer Produktinformationen zu aktivieren oder zu deaktivieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (angekreuzt):* Die PrestaShop-Suchmaschine berücksichtigt Daten aus diesem spezifischen Feld bei der Verarbeitung von Kundenanfragen. Wenn beispielsweise „Produktname“ aktiviert ist, findet eine Suche nach „Kleid“ Produkte mit „Kleid“ im Namen.
  - *Wenn deaktiviert (nicht angekreuzt):* Die PrestaShop-Suchmaschine *ignoriert* Daten aus diesem Feld. Wenn „Produktbeschreibung“ deaktiviert ist, erscheint ein Produkt nicht in den Suchergebnissen, wenn der Suchbegriff nur in seiner Beschreibung gefunden wird.
- **Empfohlener Wert:** Dies hängt vollständig von Ihrem Produktkatalog und davon ab, wie Kunden Produkte finden sollen. Ein guter Ausgangspunkt ist, die wichtigsten Felder zu aktivieren und dann basierend auf Tests zu verfeinern.
- **Händlerszenario / Beispiel:**
  - **Szenario 1: Hochspezifische Produkte (z.B. Elektronikteile, Bücher nach ISBN):** Sie möchten möglicherweise nur in „Produktname“, „Referenz“ und „EAN13/JAN“ suchen. Dies stellt sicher, dass Kunden schnell exakte Übereinstimmungen finden und irrelevante Ergebnisse aus langen Beschreibungen vermieden werden.
  - **Szenario 2: Mode- oder Haushaltswaren (z.B. „rotes Kleid“):** Sie könnten „Produktname“, „Kurzbeschreibung“, „Lange Beschreibung“ und „Tags“ aktivieren. Dies ermöglicht es Kunden, Produkte basierend auf breiteren Begriffen, Farben oder Stilen zu finden, die überall in den Produktdetails erwähnt werden.
  - **Szenario 3: Markenprodukte:** Aktivieren Sie „Herstellername“, damit Kunden alle Produkte einer bestimmten Marke leicht finden können, indem sie den Markennamen in die Suchleiste eingeben.

Hier ist eine Aufschlüsselung der typischen Einstellungen, die Sie finden werden:

| Einstellung / Option | Zweck & Auswirkung | Empfohlener Wert | Händlerszenario |
| --- | --- | --- | --- |
| **Im Produktnamen suchen** | Wenn aktiviert, werden Suchanfragen mit dem Produktnamen abgeglichen. | **JA** | Für die meisten Shops unerlässlich. Kunden suchen oft nach Produktnamen. |
| **In der Produktkurzbeschreibung suchen** | Wenn aktiviert, werden Suchanfragen mit der Kurzbeschreibung des Produkts abgeglichen. | **JA** | Nützlich, um Produkte anhand von Schlüsselmerkmalen oder Zusammenfassungen zu finden. |
| **In der Produktlangbeschreibung suchen** | Wenn aktiviert, werden Suchanfragen mit der vollständigen, detaillierten Beschreibung des Produkts abgeglichen. | **JA / NEIN** | **JA** für breite Suchen (Mode, Haushaltswaren). **NEIN** für sehr spezifische Artikel (Elektronik, Teile), um Rauschen zu vermeiden. |
| **In der Produktreferenz suchen** | Wenn aktiviert, werden Suchanfragen mit der internen Referenznummer des Produkts abgeglichen. | **JA / NEIN** | **JA** für B2B, technische Produkte oder wenn Kunden Teilenummern kennen. **NEIN**, wenn Referenzen nur intern sind. |
| **In Produkt EAN13/JAN suchen** | Wenn aktiviert, werden Suchanfragen mit dem EAN13- oder JAN-Barcode des Produkts abgeglichen. | **JA / NEIN** | **JA** für Shops, in denen Kunden möglicherweise nach Barcode suchen (z.B. Bücher, Lebensmittel). |
| **In Produkt UPC suchen** | Wenn aktiviert, werden Suchanfragen mit dem UPC-Barcode des Produkts abgeglichen. | **JA / NEIN** | Ähnlich wie EAN13/JAN, für Regionen, die UPC verwenden. |
| **In Produkt-Tags suchen** | Wenn aktiviert, werden Suchanfragen mit allen dem Produkt zugewiesenen Tags abgeglichen. | **JA** | Hervorragend zur Verbesserung der Auffindbarkeit mit Schlüsselwörtern, die nicht in Namen/Beschreibungen enthalten sind. |
| **Im Herstellernamen suchen** | Wenn aktiviert, werden Suchanfragen mit dem Namen des Produktherstellers abgeglichen. | **JA** | Entscheidend, wenn Kunden oft nach bestimmten Marken suchen. |
| **Im Lieferantennamen suchen** | Wenn aktiviert, werden Suchanfragen mit dem Namen des Produktlieferanten abgeglichen. | **NEIN / JA** | **NEIN** für die meisten B2C-Shops. **JA** für B2B oder spezialisierte Shops, in denen der Lieferant für Kunden relevant ist. |
| **Im Kategorienamen suchen** | Wenn aktiviert, werden Suchanfragen mit dem Namen der Kategorien abgeglichen, zu denen das Produkt gehört. | **JA** | Hilft Kunden, Produkte nach Kategorienamen zu finden (z.B. „Kleider“, um Produkte in der Kategorie „Kleider“ zu finden). |
| **Im Merkmalswert suchen** | Wenn aktiviert, werden Suchanfragen mit den Werten von Produktmerkmalen abgeglichen (z.B. „rot“ für ein Merkmal „Farbe“). | **JA** | Sehr empfehlenswert für Shops mit reichhaltigen Produktmerkmalen (z.B. Farbe, Größe, Material). |

**Wichtiger Hinweis:** Nachdem Sie Änderungen an diesen Einstellungen vorgenommen haben, klicken Sie immer auf die Schaltfläche „Speichern“. Es ist auch eine gute Praxis, Ihren PrestaShop-Cache zu leeren (Erweiterte Einstellungen > Leistung) und die Suchfunktion in Ihrem Front Office zu testen, um sicherzustellen, dass die Änderungen wie erwartet wirksam geworden sind.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul führt keine neuen dedizierten Admin-Bildschirme oder benutzerdefinierten Controller ein. Die gesamte Konfiguration wird direkt auf der Standard-Modulkonfigurationsseite vorgenommen.

### 2.3 Kurzübersicht der Konfigurationstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | Im Produktnamen suchen | JA | Produktnamen in die Suche einbeziehen. |
| Modul-Konfigurationsseite | In der Produktkurzbeschreibung suchen | JA | Kurzbeschreibungen in die Suche einbeziehen. |
| Modul-Konfigurationsseite | In der Produktlangbeschreibung suchen | JA / NEIN | Vollständige Beschreibungen einbeziehen. |
| Modul-Konfigurationsseite | In der Produktreferenz suchen | JA / NEIN | Produktreferenznummern einbeziehen. |
| Modul-Konfigurationsseite | In Produkt EAN13/JAN suchen | JA / NEIN | EAN13/JAN-Barcodes einbeziehen. |
| Modul-Konfigurationsseite | In Produkt UPC suchen | JA / NEIN | UPC-Barcodes einbeziehen. |
| Modul-Konfigurationsseite | In Produkt-Tags suchen | JA | Produkt-Tags einbeziehen. |
| Modul-Konfigurationsseite | Im Herstellernamen suchen | JA | Herstellernamen einbeziehen. |
| Modul-Konfigurationsseite | Im Lieferantennamen suchen | NEIN / JA | Lieferantennamen einbeziehen. |
| Modul-Konfigurationsseite | Im Kategorienamen suchen | JA | Kategorienamen einbeziehen. |
| Modul-Konfigurationsseite | Im Merkmalswert suchen | JA | Produktmerkmalswerte einbeziehen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe Einstellungen geändert, aber die Suchergebnisse haben sich nicht geändert. Was ist falsch?**
A: PrestaShop verwendet Caching, um Ihren Shop zu beschleunigen. Nach dem Ändern von Moduleinstellungen müssen Sie oft den Cache leeren.

- **Lösung:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung**. Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Testen Sie dann Ihre Suche erneut.

**F2: Die Suchleiste meines benutzerdefinierten Themes sieht anders aus. Funktioniert dieses Modul trotzdem?**
A: Ja, das Modul „Gezielte Suche“ überschreibt primär die *Logik*, wie PrestaShop Suchanfragen verarbeitet, nicht das visuelle Erscheinungsbild der Suchleiste selbst. Es sollte nahtlos mit den meisten benutzerdefinierten Themes funktionieren.

- **Lösung:** Wenn Sie unerwartete visuelle Probleme feststellen oder die Suche nicht zu funktionieren scheint, könnte es ein seltener Konflikt mit der benutzerdefinierten Suchvorlage Ihres Themes sein. Kontaktieren Sie den MyPresta.eu-Support mit Details zu Ihrem Theme.

**F3: Beeinflusst dieses Modul die Suchmaschinenoptimierung (SEO)?**
A: Direkt, nein. Dieses Modul verbessert das *interne* Sucherlebnis für Ihre Kunden auf Ihrer Website. Es hat keinen direkten Einfluss darauf, wie externe Suchmaschinen (wie Google) Ihre Website crawlen oder ranken. Durch die Verbesserung des On-Site-Sucherlebnisses können Sie jedoch die Absprungraten reduzieren und die Verweildauer auf der Website erhöhen, was positive Signale für SEO sind.

**F4: Kann ich die Einstellungen oder Nachrichten des Moduls übersetzen?**
A: Das Modul „Gezielte Suche“ arbeitet primär im Hintergrund und führt keine neuen Front-Office-Texte ein, die übersetzt werden müssten. Die Konfigurationsoptionen im Back Office sind typischerweise auf Englisch. Sollten neue Texte eingeführt werden, würden Sie diese über **International > Übersetzungen** in Ihrem PrestaShop Back Office übersetzen, indem Sie „Übersetzungen installierter Module“ und dann das Modul „Gezielte Suche“ auswählen.

**F5: Was ist, wenn ich in einem Feld suchen möchte, das nicht in den Moduleinstellungen aufgeführt ist?**
A: Das Modul bietet Optionen für die gängigsten und wirkungsvollsten Produktfelder. Wenn Sie ein sehr spezifisches benutzerdefiniertes Feld in die Suche aufnehmen müssen, würde dies eine benutzerdefinierte Entwicklung erfordern.

- **Lösung:** Kontaktieren Sie den MyPresta.eu-Support oder einen PrestaShop-Entwickler, um benutzerdefinierte Anpassungen zu besprechen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Gezielte Suche“ funktioniert hauptsächlich durch das Überschreiben der PrestaShop-Kernklasse `Search`. Dies ermöglicht es, die Standard-Suchabfragelogik abzufangen und zu modifizieren, bevor sie die Datenbank erreicht. Das Modul nutzt das PrestaShop-Override-System, um seine benutzerdefinierten Suchparameter basierend auf der Händlerkonfiguration einzufügen. Es ist ein leichtgewichtiges Modul, das sich auf die Änderung des bestehenden Kernverhaltens konzentriert, anstatt komplexe neue Entitäten oder Controller einzuführen.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller ein. Seine Funktionalität wird durch das Überschreiben einer Kernklasse und über die Standard-Modul `getContent()` für die Konfiguration integriert.

### 4.3 Kernklassen & Modelle (`classes/`)

Der Kern der Funktionalität dieses Moduls liegt in seiner Überschreibung der Klasse `Search`.

- **`targetsearch/override/classes/index.php`**:

  - Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in Verzeichnissen platziert wird, um aus Sicherheitsgründen die Verzeichnisauflistung zu verhindern. Sie enthält keinen funktionalen Code.
- **`targetsearch/override/classes/Search.php`**:

  - **Klassenname**: `Search` (überschreibt die Kernklasse `classes/Search.php`)
  - **Elternklasse**: `SearchCore`
  - **Verantwortlichkeit**: Diese Klasse ist dafür verantwortlich, die `search`-Methode der Kernklasse `Search` zu modifizieren. Sie liest die in `ps_configuration` gespeicherten Konfigurationseinstellungen (z.B. `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION` usw.) und passt die für die Produktsuche verwendete SQL-Abfrage dynamisch an.
  - **Wichtige öffentliche Methoden**:
    - `search($id_lang, $expr, $page_number = 1, $page_size = 10, $order_by = 'position', $order_way = 'desc', $ajax = false, $use_cookie = true, Context $context = null)`: Diese Methode wird überschrieben, um die benutzerdefinierten Suchbedingungen einzufügen. Sie konstruiert die `WHERE`-Klausel der SQL-Abfrage basierend auf den aktivierten Suchzielen. Sie prüft `Configuration::get('TARGETSEARCH_...')` für jedes Ziel (Produktname, Beschreibung, Referenz, EAN13, UPC, Tags, Hersteller, Lieferant, Kategorie, Merkmalswert) und fügt entsprechende `LIKE`-Bedingungen zur Abfrage hinzu.
  - **Datenbankinteraktion**: Es interagiert nicht mit benutzerdefinierten Datenbanktabellen. Es modifiziert die Abfrage, die mit Standard-PrestaShop-Produkt-, Kategorie-, Hersteller-, Lieferanten- und Merkmalstabellen interagiert.
  - **`$definition`**: Nicht zutreffend, da es eine Kernklasse überschreibt und kein neues `ObjectModel` definiert.

### 4.4 JavaScript-Assets (`views/js/`)

- **`targetsearch/targetsearch.js`**:
  - **Geltungsbereich**: Back-Office (potenziell, aber typischerweise nicht für die Front-Office-Suchlogik verwendet).
  - **Zweck**: Diese Datei ist im Allgemeinen leer oder enthält minimales JavaScript, oft für grundlegende UI-Interaktionen auf der Konfigurationsseite des Moduls, falls eine erweiterte clientseitige Logik benötigt würde. Angesichts der primären Funktion des Moduls als serverseitige Suchlogik ist es unwahrscheinlich, dass diese Datei komplexe Front-Office-suchbezogene JS enthält. Es könnte ein Platzhalter oder für kleinere Back-Office-Formularverbesserungen sein.
  - **Event-Listener/DOM-Manipulation**: Es ist unwahrscheinlich, dass es signifikante Front-Office-Event-Listener oder DOM-Manipulationen im Zusammenhang mit der Suche enthält. Seine primäre Rolle wäre für die Konfigurationsseite des Moduls im Back Office.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`targetsearch/targetsearch.css`**:

  - **Geltungsbereich**: Back-Office.
  - **Zweck**: Dieses Stylesheet wird typischerweise verwendet, um die Konfigurationsseite des Moduls im PrestaShop Back Office zu gestalten und sicherzustellen, dass sie mit dem Admin-Theme konsistent aussieht. Es könnte Stile für Formularelemente, Warnungen oder spezifische Layoutanpassungen für die Einstellungen des Moduls enthalten.
  - **Wichtige CSS-Klassenselektoren**: Zielt wahrscheinlich auf Standard-PrestaShop-Admin-Klassen oder spezifische IDs/Klassen innerhalb der `getContent()`-Ausgabe des Moduls ab.
- **`targetsearch/targetsearch15.css`**:

  - **Geltungsbereich**: Back-Office (speziell für PrestaShop 1.5.x).
  - **Zweck**: Diese Datei bietet spezifische Stil-Anpassungen für die Konfigurationsseite des Moduls, wenn es unter PrestaShop 1.5.x läuft, und berücksichtigt dabei Unterschiede in der Struktur und dem CSS des Admin-Themes.
  - **Wichtige CSS-Klassenselektoren**: Ähnlich wie `targetsearch.css`, aber auf die PS 1.5 Admin-Umgebung zugeschnitten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`targetsearch/targetsearch-top.tpl`**:
  - **Geltungsbereich**: Front-Office.
  - **Hook**: Dieses Template ist wahrscheinlich dafür konzipiert, in `displayHeader` oder `displayTop` (oder ähnliche Hooks, die Inhalte im Header-Bereich rendern) eingehängt zu werden.
  - **Zweck**: Während die Kernfunktion des Moduls die Suchlogik ist, könnte dieses Template verwendet werden, um ein verstecktes Eingabefeld, ein kleines Skript oder ein spezifisches visuelles Element im Zusammenhang mit der Präsenz des Moduls auszugeben, obwohl es für das Such-Override selbst nicht unbedingt notwendig ist. Angesichts der Modulbeschreibung ist es wahrscheinlicher, dass dieses Template ein Platzhalter oder für eine sehr geringfügige, nicht kritische visuelle Komponente ist, da der Haupteinfluss des Moduls auf die Such-*ergebnisse* liegt, nicht auf der Such-*eingabe*. Es könnte auch ein Überbleibsel aus einer früheren Version oder ein Template für eine zukünftige Funktion sein.

### 4.7 Datenbank-Schema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfigurationseinstellungen in der Standard-PrestaShop-Tabelle `ps_configuration`.
    - Schlüssel: `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, `TARGETSEARCH_SHORT_DESCRIPTION`, `TARGETSEARCH_REFERENCE`, `TARGETSEARCH_EAN13`, `TARGETSEARCH_UPC`, `TARGETSEARCH_TAGS`, `TARGETSEARCH_MANUFACTURER`, `TARGETSEARCH_SUPPLIER`, `TARGETSEARCH_CATEGORY`, `TARGETSEARCH_FEATURE_VALUE`.
    - Werte: `1` (aktiviert) oder `0` (deaktiviert).
- **Registrierte Hooks-Tabelle**:
Das Modul registriert Standard-Hooks hauptsächlich für seine Installation und Deinstallation und potenziell für die Darstellung seiner Konfiguration. Seine Kernfunktionalität erfolgt über Klassen-Override, nicht direkt über Hooks.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `install` | Während der Modulinstallation. | Erstellt Konfigurationseinträge in `ps_configuration` mit Standardwerten. |
| `uninstall` | Während der Moduldeinstallation. | Entfernt Konfigurationseinträge aus `ps_configuration`. |
| `displayHeader` (oder ähnlich) | Rendert Inhalte im `<head>`-Bereich oder am oberen Rand der Seite. | Wird potenziell verwendet, um `targetsearch.js` oder `targetsearch.css` einzubinden, wenn sie Front-Office-Assets enthalten, oder um `targetsearch-top.tpl` zu rendern. |
| `displayBackOfficeHeader` | Rendert Inhalte im `<head>`-Bereich des Back Office. | Wird verwendet, um `targetsearch.css` (und `targetsearch15.css` bedingt) für die Gestaltung der Konfigurationsseite des Moduls einzubinden. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Gezielte Suche“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
