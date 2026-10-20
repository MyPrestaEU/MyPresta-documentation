---
title: "Produkte auf CMS-Seiten – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produkte auf CMS-Seiten' von MyPresta.eu."
sidebar:
  label: "Produkte auf CMS-Seiten – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Products on CMS pages auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/products-on-cms-pages.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/products-on-cms-pages/)
>
> ---


# Produkte auf CMS-Seiten

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation klicken Sie im Modul-Manager neben dem Modul „Produkte auf CMS-Seiten“ auf „Konfigurieren“. Sie sehen den Hauptkonfigurationsbildschirm.

#### **Produkte und Shortcodes ausblenden**

-   **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob das Modul Produkte aus den Shortcodes, die Sie auf Ihren CMS-Seiten platziert haben, verarbeitet und anzeigt. Sie beeinflusst auch, ob die Shortcodes selbst für Kunden sichtbar sind, wenn das Modul sie nicht verarbeitet.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Wenn aktiviert (JA):* Das Modul wird die Shortcodes *nicht* verarbeiten. Anstatt Produktlisten anzuzeigen, werden die Shortcodes (z.B. `[products ids="1,2,3"]`) im Front Office für den Kunden ausgeblendet. Dies ist nützlich, wenn Sie die Produktanzeige vorübergehend deaktivieren möchten, ohne die Shortcodes aus Ihrem CMS-Inhalt zu entfernen.
    *   *Wenn deaktiviert (NEIN):* Das Modul sucht aktiv nach den Shortcodes auf Ihren CMS-Seiten und verarbeitet sie. Es ersetzt sie durch die entsprechenden Produktlisten, wodurch Ihre Produkte für Kunden sichtbar werden.
-   **Empfohlener Wert:** **NEIN** (es sei denn, Sie möchten die Produktlisten und Shortcodes explizit ausblenden).
-   **Händlerszenario / Beispiel:**
    *   Sie haben mehrere CMS-Seiten mit Produkt-Shortcodes für eine saisonale Aktion eingerichtet. Wenn die Aktion endet, können Sie, anstatt jede CMS-Seite manuell zu bearbeiten, um die Shortcodes zu entfernen, einfach „Produkte und Shortcodes ausblenden“ aktivieren, um alle Produktlisten auf diesen Seiten sofort auszublenden. Wenn die nächste Aktion beginnt, deaktivieren Sie es wieder.

### 2.2 Wie man Shortcodes auf CMS-Seiten verwendet

Dieses Modul verfügt über keine dedizierten Admin-Bildschirme über die Hauptkonfiguration hinaus. Seine primäre Funktionalität wird durch „Shortcodes“ gesteuert, die Sie direkt in den Inhalt Ihrer CMS-Seite einfügen.

**Um Produkte zu einer CMS-Seite hinzuzufügen:**

1.  Navigieren Sie in Ihrem PrestaShop Back Office zu **Shop-Parameter > CMS**.
2.  Bearbeiten Sie eine bestehende CMS-Seite oder erstellen Sie eine neue.
3.  Im Hauptinhaltseditor (normalerweise ein Rich-Text-Editor wie TinyMCE) können Sie die Shortcodes eingeben oder einfügen.

**Verfügbare Shortcodes:**

-   **Spezifische Produkte nach ID anzeigen:**

    *   `[products ids="1,2,3,4"]`
    *   **Zweck:** Dieser Shortcode ermöglicht es Ihnen, eine Liste spezifischer Produkte anhand ihrer eindeutigen ID-Nummern anzuzeigen. Produkt-IDs finden Sie in Ihrem Back Office unter **Katalog > Produkte**.
    *   **Beispiel:** Wenn Sie Produkt A (ID 1), Produkt B (ID 2) und Produkt C (ID 3) anzeigen möchten, verwenden Sie `[products ids="1,2,3"]`.
-   **Produkte aus einer bestimmten Kategorie anzeigen:**

    *   `[products category="5"]`
    *   **Zweck:** Dieser Shortcode zeigt alle Produkte an, die zu einer bestimmten Kategorie gehören. Kategorie-IDs finden Sie in Ihrem Back Office unter **Katalog > Kategorien**, indem Sie eine Kategorie bearbeiten und die URL oder die Spalte „ID“ in der Kategorieliste betrachten.
    *   **Beispiel:** Um alle Produkte aus Ihrer Kategorie „Elektronik“ anzuzeigen (angenommen, ihre ID ist 5), verwenden Sie `[products category="5"]`.
-   **Produkte eines bestimmten Herstellers/einer bestimmten Marke anzeigen:**

    *   `[products manufacturer="1"]`
    *   **Zweck:** Dieser Shortcode zeigt alle Produkte an, die einem bestimmten Hersteller oder einer bestimmten Marke zugeordnet sind. Hersteller-IDs finden Sie unter **Katalog > Marken & Lieferanten > Marken**.
    *   **Beispiel:** Um alle Produkte von „Apple“ anzuzeigen (angenommen, ihre ID ist 1), verwenden Sie `[products manufacturer="1"]`.
-   **Neue Produkte anzeigen:**

    *   `[products new="5"]`
    *   **Zweck:** Dieser Shortcode zeigt die zuletzt hinzugefügten Produkte in Ihrem Shop an. Die Zahl „5“ gibt an, wie viele neue Produkte Sie anzeigen möchten.
    *   **Beispiel:** Um die 5 neuesten Produkte anzuzeigen, verwenden Sie `[products new="5"]`.
-   **Meistverkaufte Produkte anzeigen:**

    *   `[products bestseller="5"]`
    *   **Zweck:** Dieser Shortcode zeigt Ihre meistverkauften Produkte an. Die Zahl „5“ gibt an, wie viele meistverkaufte Produkte Sie anzeigen möchten.
    *   **Beispiel:** Um Ihre 5 meistverkauften Produkte anzuzeigen, verwenden Sie `[products bestseller="5"]`.
-   **Produkte im Angebot anzeigen:**

    *   `[products sale="5"]`
    *   **Zweck:** Dieser Shortcode zeigt Produkte an, die derzeit im Angebot sind. Die Zahl „5“ gibt an, wie viele Angebotsprodukte Sie anzeigen möchten.
    *   **Beispiel:** Um 5 Produkte anzuzeigen, die derzeit reduziert sind, verwenden Sie `[products sale="5"]`.
-   **Vorgestellte Produkte anzeigen (von der Startseite):**

    *   `[products featured="5"]`
    *   **Zweck:** Dieser Shortcode zeigt Produkte an, die auf Ihrer Startseite als „vorgestellt“ markiert sind (normalerweise über das Modul „Vorgestellte Produkte“ gesteuert). Die Zahl „5“ gibt an, wie viele vorgestellte Produkte Sie anzeigen möchten.
    *   **Beispiel:** Um 5 Ihrer vorgestellten Produkte anzuzeigen, verwenden Sie `[products featured="5"]`.

**Wichtige Hinweise:**

-   Sie können Shortcodes auf derselben Seite kombinieren, aber jeder Shortcode generiert seine eigene Produktliste.
-   Stellen Sie sicher, dass sich keine zusätzlichen Leerzeichen oder Tippfehler innerhalb der Shortcode-Klammern `[]` befinden.
-   Nach dem Hinzufügen von Shortcodes speichern Sie Ihre CMS-Seite. Die Produkte erscheinen automatisch im Front Office (es sei denn, Sie haben „Produkte und Shortcodes ausblenden“ in der Modulkonfiguration aktiviert).

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Produkte und Shortcodes ausblenden | NEIN | Steuert, ob Produktlisten aus Shortcodes auf CMS-Seiten angezeigt (NEIN) oder ausgeblendet (JA) werden. |
| CMS-Seiten-Editor | `[products ids="1,2,3"]` | N/A | Zeigt spezifische Produkte anhand ihrer IDs an. |
| CMS-Seiten-Editor | `[products category="5"]` | N/A | Zeigt alle Produkte einer bestimmten Kategorie an. |
| CMS-Seiten-Editor | `[products manufacturer="1"]` | N/A | Zeigt alle Produkte eines bestimmten Herstellers an. |
| CMS-Seiten-Editor | `[products new="5"]` | N/A | Zeigt die 5 neuesten Produkte an. |
| CMS-Seiten-Editor | `[products bestseller="5"]` | N/A | Zeigt die 5 meistverkauften Produkte an. |
| CMS-Seiten-Editor | `[products sale="5"]` | N/A | Zeigt die 5 Produkte an, die derzeit im Angebot sind. |
| CMS-Seiten-Editor | `[products featured="5"]` | N/A | Zeigt die 5 vorgestellten Produkte von der Startseite an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Produkte werden auf der CMS-Seite nicht angezeigt, aber die Shortcodes sind sichtbar.**
A: Überprüfen Sie die Konfigurationsseite des Moduls (**Module > Modul-Manager > Konfigurieren** für „Produkte auf CMS-Seiten“). Stellen Sie sicher, dass „Produkte und Shortcodes ausblenden“ auf **NEIN** eingestellt ist. Wenn es auf JA eingestellt ist, blendet das Modul die Produkte und die Shortcodes selbst aus. Überprüfen Sie auch Ihre Shortcode-Syntax auf Tippfehler oder fehlende Anführungszeichen.

**F: Meine Produkte werden nicht angezeigt, und die Shortcodes auch nicht (nur leerer Raum).**
A: Dies bedeutet normalerweise, dass das Modul aktiv ist und versucht, die Shortcodes zu verarbeiten, aber auf ein Problem stößt.
1.  **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
2.  **Produkt-IDs/Kategorie-IDs überprüfen:** Stellen Sie sicher, dass die IDs, die Sie in `[products ids="..."]`, `[products category="..."]` oder `[products manufacturer="..."]` verwenden, korrekt sind und zu bestehenden, aktiven Produkten/Kategorien/Herstellern in Ihrem Shop gehören.
3.  **Produktsichtbarkeit:** Stellen Sie sicher, dass die Produkte, die Sie anzeigen möchten, aktiv und in Ihrem Shop sichtbar sind (nicht deaktiviert, nicht auf Lager, wenn die Lagerverwaltung streng ist, oder auf „versteckt“ eingestellt).

**F: Die Produkte erscheinen, sehen aber mit dem Styling meines Themes nicht gut aus.**
A: Das Modul verwendet ein grundlegendes Styling, aber das CSS Ihres Themes könnte es überschreiben oder damit in Konflikt geraten.
1.  **Theme-Anpassung:** Die meisten Themes bieten Optionen für benutzerdefiniertes CSS. Sie oder Ihr Webmaster können benutzerdefinierte CSS-Regeln hinzufügen, um die von diesem Modul generierten Produktlisten anzusprechen.
2.  **Theme-Entwickler kontaktieren:** Wenn Sie unsicher sind, wenden Sie sich an Ihren Theme-Entwickler, um Ratschläge zur besten Gestaltung von Produktgittern zu erhalten.
3.  **MyPresta.eu-Support kontaktieren:** Wenn Sie ein modulspezifisches Styling-Problem vermuten, wenden Sie sich an den MyPresta.eu-Support.

**F: Kann ich mehrere Shortcodes auf derselben CMS-Seite verwenden?**
A: Ja, Sie können beliebig viele verschiedene Shortcodes auf einer einzigen CMS-Seite verwenden. Jeder Shortcode generiert seine eigene separate Produktliste.

**F: Unterstützt dieses Modul mehrsprachige Shops?**
A: Ja, das Modul funktioniert mit den Mehrsprachigkeitsfunktionen von PrestaShop. Die angezeigten Produktnamen und Beschreibungen werden in der vom Kunden ausgewählten Sprache angezeigt, genau wie auf regulären Produkt- oder Kategorieseiten. Die Shortcodes selbst (`[products ids="..."]`) bleiben in allen Sprachen gleich.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Produkte auf CMS-Seiten“ funktioniert hauptsächlich durch das Überschreiben des Kern-`CmsController`, um Inhalte abzufangen und zu verarbeiten, bevor sie dem Benutzer gerendert werden. Es verwendet reguläre Ausdrücke, um spezifische Shortcodes innerhalb des CMS-Seiteninhalts zu finden und diese durch dynamisch generierte Produktlisten zu ersetzen. Die Produktdaten werden mit den PrestaShop-Methoden `Product::getProducts` und `Product::getProductsProperties` abgerufen und dann über Smarty-Templates gerendert.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet eine Überschreibung, um die Kernfunktionalität von PrestaShop zu erweitern.

-   **Front-Office-Controller**:

    *   `cmsproducts/override/controllers/front/CmsController.php`
        *   **Klassenname & Elternklasse**: `CmsController` (überschreibt `CmsControllerCore`)
        *   **Verantwortlichkeit**: Dies ist der Kern der Modulfunktionalität. Es überschreibt die Methode `initContent()` des Standard-`CmsController`. Innerhalb von `initContent()` ruft es den CMS-Seiteninhalt ab, scannt ihn nach den definierten Shortcodes (z.B. `[products ids="...]`), verarbeitet diese Shortcodes durch Abrufen relevanter Produktdaten und ersetzt dann die Shortcodes durch gerendertes Produkt-HTML, bevor der Seiteninhalt angezeigt wird. Es stellt auch sicher, dass das CSS des Moduls geladen wird.
    *   `cmsproducts/override/controllers/front/index.php`
        *   **Klassenname & Elternklasse**: N/A (leere Datei)
        *   **Verantwortlichkeit**: Dies ist eine standardmäßige leere `index.php`-Datei, die in Unterverzeichnissen platziert wird, um die Verzeichnisauflistung zu verhindern, eine gängige Sicherheitspraxis. Sie hat keine funktionale Auswirkung auf die Modullogik.
-   **Back-Office-Admin-Controller**: Keine. Die Modulkonfiguration wird direkt in der `getContent()`-Methode der Hauptmodulklasse behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Es nutzt bestehende PrestaShop-Kernklassen wie `Product`, `Category`, `Manufacturer`, `Context`, `Tools` und `Configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

In diesem Modul sind keine benutzerdefinierten JavaScript-Dateien enthalten. Die gesamte Funktionalität wird serverseitig über PHP abgewickelt.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält zwei CSS-Dateien zum Stylen der Produktlisten. Diese werden über den Hook `actionAdminControllerSetMedia` geladen (für den Back-Office-Kontext, obwohl die Überschreibung das Laden im Front-Office übernimmt).

-   `cmsproducts/cmsproducts.css`
    *   **Geltungsbereich**: Front-Office-Kunden-Styling.
    *   **Haupt-UI-Komponenten und Container, die es stylt**: Enthält allgemeines Styling für das Produktgitter/-liste, das von den Shortcodes generiert wird. Dies würde Stile für Produktcontainer, Bilder, Namen, Preise und möglicherweise „In den Warenkorb“-Buttons umfassen, um ein konsistentes Aussehen zu gewährleisten.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Zielt wahrscheinlich auf Klassen wie `.cmsproducts-product-list`, `.cmsproducts-product-item`, `.cmsproducts-product-image`, `.cmsproducts-product-name`, `.cmsproducts-product-price`.
-   `cmsproducts/css.css`
    *   **Geltungsbereich**: Front-Office-Kunden-Styling.
    *   **Haupt-UI-Komponenten und Container, die es stylt**: Ähnlich wie `cmsproducts.css` bietet diese Datei wahrscheinlich zusätzliche oder spezifische Styling-Regeln für die Produktanzeige, möglicherweise für Responsivität oder spezifische Layoutanpassungen.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Ähnlich wie `cmsproducts.css`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates, um die Produktlisten zu rendern.

-   **Hook-Templates (`views/templates/hook/`)**: Keine explizit als Hook-Templates definiert. Die Templates werden direkt von der `CmsController`-Überschreibung gerendert.
-   **Admin-Templates (`views/templates/admin/`)**: Keine.
-   **Front-Office-Templates (`views/templates/front/`)**:
    *   `cmsproducts/html.tpl`
        *   **Zweck**: Dieses Template dient wahrscheinlich als Wrapper oder allgemeiner Container für die Produktlisten. Es könnte eine grundlegende HTML-Struktur um die Produktelemente herum enthalten.
    *   `cmsproducts/products-carousel.tpl`
        *   **Zweck**: Dieses Template ist darauf ausgelegt, Produkte in einem Karussell- oder Slider-Format zu rendern. Es würde die notwendige HTML-Struktur und möglicherweise JavaScript-Initialisierung für ein Produktkarussell enthalten. Dieses Template wird wahrscheinlich verwendet, wenn ein spezifischer Shortcode-Parameter oder eine Moduleinstellung (nicht in der aktuellen Konfiguration offengelegt) eine Karussellanzeige impliziert.
    *   `cmsproducts/products.tpl`
        *   **Zweck**: Dies ist das primäre Template zum Rendern eines Standardrasters oder einer Liste von Produkten. Es iteriert durch die vom PHP-Controller übergebenen Produktdaten und zeigt einzelne Produktdetails (Bild, Name, Preis, In den Warenkorb-Button usw.) an. Dies ist das am häufigsten verwendete Template für die `[products ...]`-Shortcodes.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der Standardtabelle `ps_configuration`.
    *   `ps_configuration`-Einträge:
        *   `mypresta_updates`: Speichert Informationen zu Modul-Updates von MyPresta.eu.
        *   `cmsproducts_hide`: Speichert den Wert der Einstellung „Produkte und Shortcodes ausblenden“ (1 für aktiviert/JA, 0 für deaktiviert/NEIN).
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets setzt. | Obwohl aufgeführt, wird das primäre CSS-Laden für das Front Office durch die `CmsController`-Überschreibung gehandhabt. Dieser Hook könnte für potenzielles zukünftiges Admin-seitiges Styling oder wenn das Modul einen Admin-Controller hätte, verwendet werden. |

Die Kernfunktionalität der Verarbeitung von Shortcodes und des Renderns von Produkten wird durch die `CmsController`-Überschreibung erreicht, die den Inhalt direkt vor der Anzeige manipuliert, anstatt sich auf einen spezifischen Front-Office-Hook für die Inhaltseinfügung zu verlassen.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um die neuesten Versionen des Moduls „Produkte auf CMS-Seiten“ zu erhalten, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Händlern und Entwicklern bei allen Fragen oder Problemen im Zusammenhang mit dem Modul zur Verfügung.
