---
title: "Specials Homepage Tab – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Specials Homepage Tab“ von MyPresta.eu."
sidebar:
  label: "Specials Homepage Tab – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Specials Homepage Tab auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/specials-homepage-tab.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/specials-homepage-tab/)
>
> ---


# Specials Homepage Tab

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modul „Specials Homepage Tab“ auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen.

#### Einstellungen & Optionen:

- **Anzahl der Produkte**

  - **Was diese Einstellung bewirkt:** Dies steuert, wie viele Sonderangebotsprodukte im „Specials“-Tab auf Ihrer Startseite angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Einstellung auf eine höhere Zahl (z.B. 12):* Mehr Produkte werden im Tab sichtbar sein, was Kunden eine größere Auswahl an Angeboten bietet. Dies kann je nach Ihrem Theme mehr Scrollen oder Paginierung erfordern.
    - *Bei Einstellung auf eine niedrigere Zahl (z.B. 4):* Weniger Produkte werden angezeigt, wodurch eine prägnantere Darstellung entsteht. Dies kann nützlich sein, wenn Sie nur Ihre besten Angebote hervorheben oder die Startseite sauber halten möchten.
  - **Empfohlener Wert:** Beginnen Sie mit einer Zahl, die gut zum Design Ihres Themes passt (z.B. 8 oder 12) und passen Sie sie an, basierend darauf, wie viele Sonderangebote Sie typischerweise haben und wie viel Platz sie einnehmen sollen.
  - **Händlerszenario / Beispiel:** Wenn Sie viele Produkte im Angebot haben und Vielfalt zeigen möchten, stellen Sie es auf 12 ein. Wenn Sie eine minimalistische Startseite bevorzugen und nur wenige Top-Angebote hervorheben möchten, stellen Sie es auf 4 ein.
- **Zufällige Produkte**

  - **Was diese Einstellung bewirkt:** Dies bestimmt, ob die im Tab angezeigten Sonderangebotsprodukte in einer festen Reihenfolge (z.B. nach ID, Hinzufügedatum) oder in einer zufälligen Reihenfolge bei jedem Laden der Seite angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Jedes Mal, wenn ein Kunde Ihre Startseite besucht, wird die Reihenfolge der Produkte im „Specials“-Tab zufällig gewählt. Dies stellt sicher, dass verschiedene Produkte Sichtbarkeit erhalten und verhindert, dass immer dieselben wenigen Artikel ganz oben stehen.
    - *Wenn deaktiviert (NEIN):* Produkte werden in einer konsistenten, nicht-zufälligen Reihenfolge angezeigt (typischerweise nach Produkt-ID oder Erstellungsdatum, abhängig von PrestaShops Standard-Sortierung für Sonderangebote). Dies bedeutet, dass immer dieselben Produkte zuerst erscheinen.
  - **Empfohlener Wert:** **JA**. Das Zufallsprinzip bei Produkten wird generell empfohlen, um allen Ihren Sonderangeboten eine faire Chance zu geben, gesehen zu werden, und um die Startseite für wiederkehrende Kunden frisch zu halten.
  - **Händlerszenario / Beispiel:** Wenn Sie 20 Produkte im Angebot haben, aber nur 8 anzeigen, stellt die Aktivierung von „Zufällige Produkte“ sicher, dass im Laufe der Zeit alle 20 Produkte irgendwann im Tab erscheinen, anstatt nur die ersten 8.

#### Andere Konfigurationsschlüssel (Interne PrestaShop-Einstellungen):

Das Modul interagiert auch mit mehreren zentralen PrestaShop-Konfigurationsschlüsseln. Obwohl diese nicht direkt im Modul selbst konfigurierbar sind, hilft das Verständnis ihres Zwecks bei der Fehlerbehebung oder erweiterten Anpassung:

- `PS_CATALOG_MODE`: Wenn Ihr Shop im Katalogmodus ist (keine Preise, kein Warenkorb), sind Sonderpreise nicht relevant.
- `PS_LANG_DEFAULT`: Die Standardsprache Ihres Shops, die zum Abrufen von Produktnamen und -beschreibungen verwendet wird.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Bestimmt, ob Mitarbeiter die Sprache von Formularen im Back Office ändern können.
- `PS_TAX_ADDRESS_TYPE`: Wie Steuern berechnet werden (z.B. basierend auf Liefer- oder Rechnungsadresse).
- `PS_COUNTRY_DEFAULT`: Das Standardland für Ihren Shop, das sich auf Steuer- und Versandberechnungen auswirkt.
- `PS_NB_DAYS_NEW_PRODUCT`: Die Anzahl der Tage, die ein Produkt als „neu“ gilt. (Nicht direkt mit Sonderangeboten verbunden, aber oft in Modulen zu finden, die Produkte auflisten).

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Anzahl der Produkte | 8-12 (An Theme anpassen) | Legt fest, wie viele Sonderangebotsprodukte im Tab angezeigt werden. |
| Modulkonfiguration | Zufällige Produkte | JA | Zufällige Reihenfolge der Produkte im Tab für eine frische Anzeige. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein „Specials“-Tab ist leer oder zeigt keine Produkte an, obwohl ich Produkte im Angebot habe.**

- **A:** Stellen Sie zunächst sicher, dass Ihre Produkte in den Produkteinstellungen im PrestaShop Back Office korrekt als „im Angebot“ gekennzeichnet sind (unter dem Tab „Preise“ stellen Sie sicher, dass „Spezifische Preise“ konfiguriert und aktiv sind). Überprüfen Sie auch die Einstellung „Anzahl der Produkte“ in der Modulkonfiguration; wenn sie auf 0 gesetzt ist, werden keine Produkte angezeigt. Leeren Sie schließlich Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**).

**F2: Der „Specials“-Tab erscheint überhaupt nicht auf meiner Startseite.**

- **A:**
  1. **Modul aktiviert:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „Specials Homepage Tab“ aktiviert ist.
  2. **Korrekt gehookt:** Das Modul verwendet `displayHomeTab` und `displayHomeTabContent`. Ihr Theme muss diese Hooks unterstützen, damit der Tab erscheint. Die meisten Standard-PrestaShop-Themes tun dies. Wenn Sie ein stark angepasstes Theme verwenden, ruft es diese Hooks möglicherweise nicht auf.
  3. **Cache:** Leeren Sie immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**), nachdem Sie Module installiert oder konfiguriert haben.
  4. **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können sehr alte oder stark angepasste Themes geringfügige Anpassungen erfordern. Wenn Probleme weiterhin bestehen, wenden Sie sich an den MyPresta.eu-Support.

**F3: Die Produkte im „Specials“-Tab sehen nicht gut aus oder passen nicht zum Design meines Themes.**

- **A:** Das Modul verwendet die vorhandene Formatierung Ihres Themes für Produktlisten. Wenn die Produkte seltsam aussehen, handelt es sich in der Regel um ein CSS-Problem mit Ihrem Theme und nicht mit dem Modul selbst.
  - **Theme-CSS überprüfen:** Überprüfen Sie das CSS Ihres Themes auf Produktlistenstile.
  - **Benutzerdefiniertes CSS:** Möglicherweise müssen Sie benutzerdefiniertes CSS zu der `custom.css`-Datei Ihres Themes (falls vorhanden) hinzufügen oder das Stylesheet Ihres Themes direkt bearbeiten, um das Erscheinungsbild anzupassen.
  - **Mobile Responsivität:** Testen Sie auf verschiedenen Geräten. Wenn es auf dem Desktop gut aussieht, aber nicht auf dem Handy, handelt es sich um ein Responsivitäts-Problem mit dem CSS Ihres Themes.

**F4: Kann ich den Titel des „Specials“-Tabs ändern (z.B. in „Angebote“ oder „Aktionen“)?**

- **A:** Das Modul verwendet die Standard-PrestaShop-Übersetzung für „Specials“. Um dies zu ändern, würden Sie normalerweise zu **International > Übersetzungen** gehen, „Übersetzungen installierter Module“ auswählen, Ihr Theme wählen und dann das Modul „Specials Homepage Tab“ finden. Dort können Sie die Übersetzung für den Tab-Titel bearbeiten.

**F5: Warum werden einige Produkte, die im Angebot sind, nicht im Tab angezeigt?**

- **A:**
  1. **Produktanazahl-Limit:** Überprüfen Sie die Einstellung „Anzahl der Produkte“ in der Modulkonfiguration. Wenn Sie mehr Sonderangebote haben als dieses Limit, wird nur der erste (oder zufällige, falls aktiviert) Satz angezeigt.
  2. **Produktsichtbarkeit:** Stellen Sie sicher, dass das Produkt aktiv und sichtbar ist und einen tatsächlich konfigurierten spezifischen Preis hat (nicht nur eine reguläre Preisreduzierung).
  3. **Cache:** Leeren Sie Ihren PrestaShop-Cache.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Specials Homepage Tab“ (`blockspecialstab`) ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf die Front-Office-Anzeige konzentriert. Es hält sich an die Standard-PrestaShop-Modularchitektur und nutzt Hooks, um Inhalte in die Startseite einzufügen. Es führt keine benutzerdefinierten Controller, Modelle oder komplexe JavaScript/CSS über das für die grundlegende Templating erforderliche Maß hinaus ein. Seine Kernfunktionalität dreht sich um das Abrufen von Produkten mit spezifischen Preisen und deren Darstellung innerhalb einer Tab-Struktur.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik ist in der Hauptmodulklasse (`blockspecialstab.php`) gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen ein. Es stützt sich auf die PrestaShop-Kernklassen `Product` und `SpecificPrice`, um Produktdaten abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Die Tab-Wechselfunktion und die Produktanzeige werden durch das vorhandene JavaScript des Themes (z.B. jQuery, Bootstrap JS) gehandhabt, das typischerweise `displayHomeTab`- und `displayHomeTabContent`-Interaktionen verwaltet.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Es ist so konzipiert, dass es die Formatierung des aktiven PrestaShop-Themes für Produktlisten erbt, um eine nahtlose Integration zu gewährleisten. Entwickler sollten das CSS ihres Themes für die Formatierung von Produktgittern und Tabs konsultieren.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet zwei primäre Smarty-Templates, beide im Verzeichnis `views/templates/hook/` gelegen, um den Tab und seinen Inhalt zu rendern.

- **`blockspecialstab/views/templates/hook/blockspecialstab.tpl`**

  - **Zweck:** Dieses Template ist für das Rendern des eigentlichen „Specials“-Tab- *Headers* verantwortlich, der neben anderen Tabs (z.B. „Neuheiten“) erscheint.
  - **Hook:** Wird hauptsächlich über `displayHomeTab` gerendert.
  - **Ausgabe:** Gibt typischerweise ein `<li>`-Element aus, das ein `<a>`-Tag mit einem Link zum Inhalt des Tabs enthält (z.B. `#blockspecialstab`).
  - **Schlüsselelemente für Entwickler:**
    - `id="home-page-tabs"`: Der Container für alle Homepage-Tabs (normalerweise im Theme).
    - `id="blockspecialstab"`: Die ID für den Tab selbst, die zum Verknüpfen mit seinem Inhalt verwendet wird.
    - `{l s='Specials' mod='blockspecialstab'}`: Der übersetzbare Text für den Tab-Titel.
- **`blockspecialstab/views/templates/hook/blockspecialstabcontents.tpl`**

  - **Zweck:** Dieses Template rendert den *Inhalt*, der erscheint, wenn auf den „Specials“-Tab geklickt wird. Es enthält die eigentliche Liste der Sonderangebotsprodukte.
  - **Hook:** Wird hauptsächlich über `displayHomeTabContent` gerendert.
  - **Ausgabe:** Gibt typischerweise ein `<div>`-Element aus, das eine Schleife enthält, die die Variable `$products` (vom Modul übergeben) durchläuft und jedes Produkt mithilfe eines gemeinsamen Produktlisten-Partials des Themes anzeigt (z.B. `product-list.tpl` oder ein ähnliches Snippet).
  - **Schlüsselelemente für Entwickler:**
    - `id="blockspecialstab"`: Die ID für den Inhaltsblock, passend zum Tab-Header.
    - `{$products}`: Ein Array von `Product`-Objekten (oder assoziativen Arrays, die Produkte repräsentieren), die vom Modul übergeben werden und Details wie ID, Name, Preis, Bild usw. enthalten.
    - `{include file='catalog/_partials/miniatures/product.tpl' product=$product}` (Beispiel für PS 1.7/8): Das Modul verwendet typischerweise ein Standard-Theme-Partial, um jedes Produkt zu rendern und eine konsistente Formatierung zu gewährleisten. Entwickler sollten die `_partials/miniatures/product.tpl` oder `product-list.tpl` ihres Themes überprüfen, um zu sehen, wie einzelne Produkte gerendert werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `BLOCKSTAB_NB_CACHES` (veraltet), `BLOCKSTABS_NB_CACHES` (aktuell) und `BLOCKSTABS_RAND`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHomeTab` | Rendert im Navigationsbereich der Startseite. | Fügt den „Specials“-Tab-Header (`blockspecialstab.tpl`) in die Haupt-Startseiten-Tab-Liste ein. |
| `displayHomeTabContent` | Rendert im Inhaltsbereich der Startseite, entsprechend dem Tab. | Fügt die Liste der Sonderangebotsprodukte (`blockspecialstabcontents.tpl`) ein, wenn der „Specials“-Tab aktiv ist. |
| `addproduct` | Nach dem Hinzufügen eines Produkts. | Leert den internen Cache des Moduls, um sicherzustellen, dass neue Produkte für Sonderangebote berücksichtigt werden. |
| `updateproduct` | Nach dem Aktualisieren eines Produkts. | Leert den internen Cache des Moduls, um Änderungen an Produktpreisen oder -status widerzuspiegeln. |
| `deleteproduct` | Nach dem Löschen eines Produkts. | Leert den internen Cache des Moduls, um gelöschte Produkte aus den Sonderangeboten zu entfernen. |
| `displayAddProduct` | (Veralteter Hook, oft für Admin-Formulare verwendet) | Leert den internen Cache des Moduls. |
| `displayUpdateProduct` | (Veralteter Hook, oft für Admin-Formulare verwendet) | Leert den internen Cache des Moduls. |
| `displayDeleteProduct` | (Veralteter Hook, oft für Admin-Formulare verwendet) | Leert den internen Cache des Moduls. |

Die Hooks `addproduct`, `updateproduct`, `deleteproduct`, `displayAddProduct`, `displayUpdateProduct` und `displayDeleteProduct` werden hauptsächlich verwendet, um einen Cache-Clear innerhalb des Moduls auszulösen. Dies stellt sicher, dass die auf der Startseite angezeigte Liste der Sonderprodukte immer aktuell ist, wenn sich Produktinformationen (insbesondere Preise oder Status) ändern.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Specials Homepage Tab“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
