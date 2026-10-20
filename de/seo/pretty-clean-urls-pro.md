---
title: "Pretty / Clean URLs PRO - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Pretty / Clean URLs PRO von MyPresta.eu."
sidebar:
  label: "Pretty / Clean URLs PRO - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Pretty / Clean URLs PRO auf MyPresta.eu kaufen](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/seo/pretty-clean-urls-pro/)
>
> ---


# Pretty / Clean URLs PRO

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.0.0 - 1.7.4.x, 1.7.5.0 - 1.7.7.x, 1.7.8.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ihr Server muss außerdem `mod_rewrite` für Apache oder eine gleichwertige URL-Rewriting-Funktionalität für Nginx aktiviert haben, was für die meisten PrestaShop-Installationen Standard ist.
-   **PrestaShop Friendly URLs**: Die native Option „Friendly URL“ von PrestaShop (zu finden unter **Shop-Parameter > SEO & URLs**) *muss aktiviert sein*, damit dieses Modul korrekt funktioniert. Dieses Modul erweitert die native Funktionalität von PrestaShop, es ersetzt sie nicht.

## 2. Vollständige Konfigurationsanleitung

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite für „Pretty / Clean URLs PRO“. Hier steuern Sie das Kernverhalten des Moduls.

**Allgemeine Einstellungen**

-   **Pretty URLs aktivieren:**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Er steuert, ob das Modul aktiv saubere URLs in Ihrem gesamten Shop generiert und verwendet.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul beginnt, saubere URLs für alle unterstützten Seitentypen (Produkte, Kategorien, CMS usw.) zu generieren und darauf umzuleiten.
        -   *Wenn deaktiviert:* Das Modul ist inaktiv, und PrestaShop kehrt zu seiner Standard-URL-Struktur zurück (die IDs enthalten kann).
    -   **Empfohlener Wert:** **JA** (Dies ist die Hauptfunktion des Moduls).
    -   **Händler-Szenario / Beispiel:** Sie haben das Modul gerade installiert und möchten seine SEO-Vorteile aktivieren. Sie würden diese Einstellung aktivieren. Wenn Sie vorübergehend Fehler beheben oder zum Standardverhalten von PrestaShop zurückkehren müssen, könnten Sie sie deaktivieren.
-   **IDs aus URLs entfernen:**
    -   **Was diese Einstellung bewirkt:** Diese Option steuert speziell, ob die numerische ID (z. B. `123` in `ihrshop.com/123-mein-produkt`) aus den URLs entfernt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* URLs werden kürzer und sauberer, wie `ihrshop.com/mein-produkt`. Dies ist im Allgemeinen besser für SEO und Ästhetik.
        -   *Wenn deaktiviert:* URLs bleiben „schön“, behalten aber die ID bei, z. B. `ihrshop.com/123-mein-produkt`. Dies könnte nützlich sein, wenn Sie externe Systeme haben, die darauf angewiesen sind, dass die ID in der URL vorhanden ist, obwohl dies seltener vorkommt.
    -   **Empfohlener Wert:** **JA** (Für maximalen SEO-Vorteil und saubere Ästhetik).
    -   **Händler-Szenario / Beispiel:** Sie möchten die absolut saubersten URLs für eine bessere Suchmaschinenindizierung und Benutzerlesbarkeit. Sie würden dies aktivieren.
-   **Automatische 301-Weiterleitung:**
    -   **Was diese Einstellung bewirkt:** Diese kritische Einstellung weist das Modul an, automatisch permanente 301-Weiterleitungen von alten, ID-basierten URLs zu den neuen, sauberen URLs zu erstellen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Jeder Besucher oder Suchmaschinen-Bot, der versucht, auf eine alte URL zuzugreifen (z. B. eine, die vor der Aktivierung des Moduls indiziert wurde), wird nahtlos zur neuen, sauberen URL weitergeleitet. Dies verhindert 404-Fehler und bewahrt Ihren SEO-Link-Wert.
        -   *Wenn deaktiviert:* Alte URLs führen zu 404 „Seite nicht gefunden“-Fehlern, was schlecht für die Benutzererfahrung ist und Ihrem SEO erheblich schaden kann.
    -   **Empfohlener Wert:** **JA** (Absolut unerlässlich für die Aufrechterhaltung von SEO und Benutzererfahrung während und nach dem Übergang zu sauberen URLs).
    -   **Händler-Szenario / Beispiel:** Sie haben das Modul gerade in einem bestehenden Shop mit vielen indizierten Seiten aktiviert. Die Aktivierung stellt sicher, dass alle Ihre alten Links weiterhin funktionieren und ihren SEO-Wert an die neuen Links weitergeben.
-   **Trailing Slash erzwingen:**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob immer ein abschließender Schrägstrich (`/`) am Ende Ihrer URLs hinzugefügt wird (z. B. `ihrshop.com/kategorie/` vs. `ihrshop.com/kategorie`).
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Alle generierten URLs enden mit einem Schrägstrich. Dies kann zur URL-Konsistenz beitragen und wird von einigen SEO-Tools bevorzugt.
        -   *Wenn deaktiviert:* URLs enden nicht unbedingt mit einem Schrägstrich, abhängig vom Standardverhalten von PrestaShop für diesen Seitentyp.
    -   **Empfohlener Wert:** **JA** (Für Konsistenz und um potenzielle Probleme mit doppeltem Inhalt zu vermeiden, falls Suchmaschinen `url` und `url/` als verschiedene Seiten behandeln).
    -   **Händler-Szenario / Beispiel:** Sie möchten sicherstellen, dass alle Ihre Kategorie- und CMS-Seiten-URLs konsistent mit einem Schrägstrich enden, um ein besseres SEO-Management zu gewährleisten und potenzielle Probleme mit doppeltem Inhalt zu vermeiden.
-   **`.html`-Erweiterung entfernen:**
    -   **Was diese Einstellung bewirkt:** Diese Option steuert, ob die `.html`-Erweiterung aus Produkt- und CMS-Seiten-URLs entfernt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* URLs werden noch kürzer, z. B. `ihrshop.com/mein-produkt` anstelle von `ihrshop.com/mein-produkt.html`. Dies wird im Allgemeinen für modernes Webdesign und SEO bevorzugt.
        -   *Wenn deaktiviert:* Produkt- und CMS-Seiten-URLs behalten die `.html`-Erweiterung bei.
    -   **Empfohlener Wert:** **JA** (Für die sauberste, modernste URL-Struktur).
    -   **Händler-Szenario / Beispiel:** Sie möchten, dass Ihre Produktseiten wie `ihrshop.com/mein-produkt` anstelle von `ihrshop.com/mein-produkt.html` aussehen, um ein schlankeres Erscheinungsbild und besseres SEO zu erzielen.

**Speichern-Schaltfläche:**

-   Klicken Sie immer auf die Schaltfläche „Speichern“, nachdem Sie Änderungen vorgenommen haben, um sie in Ihrem Shop anzuwenden.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul funktioniert hauptsächlich, indem es Kern-PrestaShop-Klassen und -Controller überschreibt, um die URL-Generierung und das Routing zu ändern. Obwohl es kein neues, dediziertes Menüelement im Back Office zur Verwaltung einer Liste von „Pretty URLs“ einführt, integriert es sich direkt in bestehende PrestaShop-Funktionalitäten.

**`AdminProductsController`-Integration (Back Office > Katalog > Produkte)**

-   **Bildschirmname & Menüpfad:** **Katalog > Produkte**
-   **Verfügbare Aktionen & Einstellungen:**
    -   Wenn Sie ein Produkt bearbeiten oder erstellen, beeinflusst das Modul das Verhalten des Feldes „Friendly URL“. Anstatt dass Sie IDs manuell entfernen oder eine saubere Struktur sicherstellen müssen, generiert und schlägt die Modullogik automatisch eine saubere, ID-freie URL basierend auf Ihrem Produktnamen und den Moduleinstellungen vor.
    -   Das Modul stellt sicher, dass beim Speichern eines Produkts dessen URL gemäß Ihren „Pretty / Clean URLs PRO“-Einstellungen generiert wird (z. B. keine ID, keine `.html`-Erweiterung, falls konfiguriert).
-   **Auswirkung von Änderungen:**
    -   Wenn Sie ein Produkt speichern, spiegelt die von PrestaShop generierte und verwendete URL die in der Modulkonfiguration definierte saubere URL-Struktur wider.
    -   Wenn Sie den Namen eines Produkts ändern, hilft das Modul sicherzustellen, dass die Friendly URL sauber aktualisiert wird.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    -   Verwalten Sie Ihre Produkte wie gewohnt unter **Katalog > Produkte**. Das Modul arbeitet im Hintergrund, um sicherzustellen, dass die URLs optimiert sind.
    -   Stellen Sie beim Erstellen oder Bearbeiten von Produkten sicher, dass Ihre Produktnamen beschreibend sind, da diese zur Generierung der Friendly URLs verwendet werden.
    -   Sie können das Feld „Friendly URL“ für ein Produkt weiterhin manuell anpassen, wenn Sie eine bestimmte URL benötigen, aber die Modullogik leitet die anfängliche Generierung.

**Andere Admin-Controller (Implizite Integration)**

Das Modul beeinflusst auch implizit andere Bereiche, in denen URLs generiert werden, wie zum Beispiel:

-   **Katalog > Kategorien**: Beim Erstellen oder Bearbeiten von Kategorien.
-   **Katalog > Hersteller**: Beim Erstellen oder Bearbeiten von Herstellern.
-   **Katalog > Lieferanten**: Beim Erstellen oder Bearbeiten von Lieferanten.
-   **Design > Seiten (CMS)**: Beim Erstellen oder Bearbeiten von CMS-Seiten.

In all diesen Fällen stellt das Modul sicher, dass die von PrestaShop generierten Friendly URLs den „Pretty / Clean URLs PRO“-Einstellungen entsprechen und IDs und Erweiterungen wie konfiguriert entfernen.

### 2.3 PrestaShop SEO & URLs Einstellungen Integration

Das Modul "Pretty / Clean URLs PRO" ab Version 2.8.3 und höher verfügt über einen eigenen Bereich zur Definition von URL-Schemata, wodurch es nicht mehr notwendig ist, diese Einstellungen manuell unter PrestaShops nativem Bereich **Shop-Parameter > SEO & URLs** zu konfigurieren. Es ist jedoch entscheidend, die Interaktion zu verstehen.

:::caution Wichtiger Hinweis
Während das Modul das URL-Schema verwaltet, *muss* die native PrestaShop-Option **Friendly URL** unter **Shop-Parameter > SEO & URLs** aktiviert sein, damit das Modul funktioniert. Das Modul erweitert diese Kernfunktionalität von PrestaShop.
:::

**Schema der URLs (vom Modul verwaltet)**

Historisch gesehen definierten PrestaShop-Benutzer die URL-Muster (Routen) für Produkte, Kategorien, CMS-Seiten usw. im Bereich **Shop-Parameter > SEO & URLs**. Das Modul "Pretty / Clean URLs PRO" übernimmt nun diese Verantwortung und ermöglicht es Ihnen, diese direkt von seiner eigenen Konfigurationsseite aus zu konfigurieren.

Das Modul stellt sicher, dass die Routen so eingestellt sind, dass `{id}` aus den URLs entfernt wird, was für wirklich saubere URLs unerlässlich ist. Wenn Sie aus irgendeinem Grund feststellen, dass die Routen unter **Shop-Parameter > SEO & URLs** nach der Installation und Konfiguration des Moduls immer noch `{id}` enthalten, könnte dies auf ein Problem mit Modul-Overrides hinweisen (siehe Abschnitt 6 zur Fehlerbehebung).

Als Referenz sind hier die empfohlenen Routenstrukturen aufgeführt, die das Modul implementieren soll:

| Routentyp                 | Standard PrestaShop-Wert (Beispiel) | Gewünschter Wert des Moduls (Sauber) |
| :------------------------ | :---------------------------------- | :----------------------------------- |
| Route zum Produkt         | `{category:/}{id}-{rewrite}{-:ean13}.html` | `{category:/}{rewrite}.html` (oder `{rewrite}.html`) |
| Route zur Kategorie       | `{id}-{rewrite}`                    | `{parent_categories:/}{rewrite}/` (oder `{rewrite}/`) |
| Route zum Lieferanten     | `{id}__{rewrite}`                   | `supplier/{rewrite}/`                |
| Route zum Hersteller      | `{id}_{rewrite}`                    | `manufacturer/{rewrite}/`            |
| Route zur CMS-Seite       | `content/{id}-{rewrite}`            | `info/{rewrite}.html`                |
| Route zur CMS-Kategorieseite | `content/category/{id}-{rewrite}`   | `info/{rewrite}`                     |

:::tip Multishop-Umgebung
Wenn Sie einen PrestaShop-Multishop betreiben, denken Sie daran, die URL-Schema-Einstellungen für jeden einzelnen Shop zu überprüfen und gegebenenfalls anzupassen. Sie können den Shop, den Sie konfigurieren möchten, über das Shop-Kontextmenü in Ihrem Back Office auswählen.
:::

### 2.4 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Pretty URLs aktivieren | JA | Aktiviert/deaktiviert die Kernfunktionalität des Moduls. |
| Modulkonfiguration | IDs aus URLs entfernen | JA | Entfernt numerische IDs aus URLs (z. B. `123-produkt` wird zu `produkt`). |
| Modulkonfiguration | Automatische 301-Weiterleitung | JA | Leitet alte ID-basierte URLs auf neue saubere URLs um, bewahrt SEO. |
| Modulkonfiguration | Trailing Slash erzwingen | JA | Stellt sicher, dass alle URLs mit einem `/` enden, für Konsistenz und SEO. |
| Modulkonfiguration | `.html`-Erweiterung entfernen | JA | Entfernt `.html` aus Produkt-/CMS-Seiten-URLs für sauberere Links. |
| Katalog > Produkte (Bearbeiten) | Friendly URL-Feld | Automatisch generiert | Modul beeinflusst die automatische Generierung sauberer URLs für Produkte. |
| Katalog > Kategorien (Bearbeiten) | Friendly URL-Feld | Automatisch generiert | Modul beeinflusst die automatische Generierung sauberer URLs für Kategorien. |
| Design > Seiten (Bearbeiten) | Friendly URL-Feld | Automatisch generiert | Modul beeinflusst die automatische Generierung sauberer URLs für CMS-Seiten. |
| Shop-Parameter > SEO & URLs | Friendly URL | JA | **KRITISCH:** Muss aktiviert sein, damit das Modul funktioniert. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Nach der Installation sehen meine URLs immer noch gleich aus, oder ich erhalte 404-Fehler.**

-   **A:** Stellen Sie zunächst sicher, dass „Pretty URLs aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
-   Zweitens, gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
-   Drittens, stellen Sie sicher, dass die native PrestaShop-Option „Friendly URL“ unter **Shop-Parameter > SEO & URLs** aktiviert ist. Dieses Modul erweitert die native Friendly URL-Funktionalität von PrestaShop, es ersetzt sie nicht vollständig.
-   Überprüfen Sie schließlich die `.htaccess`-Datei Ihres Servers (wenn Sie Apache verwenden) oder die Nginx-Konfiguration. Das Modul ist auf serverseitiges URL-Rewriting (mod_rewrite für Apache) angewiesen, um korrekt zu funktionieren. Wenn Sie unsicher sind, wenden Sie sich an Ihren Hosting-Anbieter.

**F2: Mein benutzerdefiniertes Theme hat nach der Aktivierung des Moduls einige seltsame Anzeigeprobleme.**

-   **A:** Dieses Modul beeinflusst hauptsächlich die URL-Generierung und -Weiterleitung, nicht die visuelle Anzeige. Es ist unwahrscheinlich, dass es direkt Theme-Anzeigeprobleme verursacht. Wenn Sie jedoch den Cache geleert haben, müssen die CSS- oder JS-Dateien Ihres Themes möglicherweise neu geladen werden. Versuchen Sie, den Browser-Cache zu leeren. Wenn das Problem weiterhin besteht, könnte es ein Konflikt mit einem anderen Modul oder einer benutzerdefinierten Theme-Modifikation sein. Deaktivieren Sie „Pretty / Clean URLs PRO“ vorübergehend, um zu sehen, ob das Problem behoben wird. Wenn ja, wenden Sie sich an den MyPresta.eu-Support.

**F3: Funktioniert dieses Modul mit meinen bestehenden benutzerdefinierten URLs oder Weiterleitungen?**

-   **A:** Das Modul konzentriert sich auf die Generierung sauberer URLs für Kern-PrestaShop-Entitäten (Produkte, Kategorien, CMS usw.). Wenn Sie manuell benutzerdefinierte Weiterleitungen oder spezifische Friendly URLs außerhalb des PrestaShop-Standardsystems erstellt haben, priorisiert die automatische 301-Weiterleitung des Moduls seine eigenen generierten sauberen URLs. Es ist im Allgemeinen am besten, das Modul alle Kern-Entitäts-URLs für Konsistenz verwalten zu lassen. Wenn Sie sehr spezifische benutzerdefinierte Weiterleitungen haben, müssen Sie möglicherweise testen, wie sie interagieren.

**F4: Ich habe einen Produktnamen geändert, aber die URL wurde nicht automatisch aktualisiert.**

-   **A:** Wenn Sie den Namen eines Produkts ändern, schlägt PrestaShop normalerweise eine neue Friendly URL vor. Sie müssen das Produkt explizit speichern, damit die Änderungen wirksam werden und das Modul die neue URL verarbeiten kann. Wenn das Friendly URL-Feld nicht automatisch aktualisiert wird, müssen Sie möglicherweise manuell auf „URL generieren“ neben dem Friendly URL-Feld auf der Produktbearbeitungsseite klicken und dann das Produkt speichern. Das Modul stellt dann sicher, dass diese neue URL sauber ist und die Weiterleitung von der alten URL übernimmt.

**F5: Beeinflusst dieses Modul meine mehrsprachigen URLs?**

-   **A:** Nein, es verbessert sie! Das Modul arbeitet mit den mehrsprachigen Funktionen von PrestaShop zusammen. Es generiert saubere URLs für jede Sprache, wobei der Sprachcode in der URL berücksichtigt wird (z. B. `/de/mein-produkt` und `/fr/mon-produit`). Stellen Sie sicher, dass Ihre Produkt-, Kategorie- und CMS-Seitennamen für jede Sprache übersetzt sind, um die besten Friendly URLs zu erhalten.

**F6: Ich sehe eine Fehlermeldung "Schlüsselwort {id} ist für die Route (...) erforderlich", wenn ich versuche, URL-Schemata zu speichern.**

-   **A:** Dieser Fehler tritt typischerweise auf, wenn die Overrides des Moduls (ein Kernbestandteil seiner Funktionalität) nicht korrekt installiert oder in Ihrem PrestaShop-Shop deaktiviert sind. Das Modul ist auf diese Overrides angewiesen, um das Standard-URL-Routing-Verhalten von PrestaShop zu ändern, wodurch es das `{id}` aus den Routen entfernen kann.
    -   **Lösung:**
        1.  **Overrides überprüfen:** Stellen Sie sicher, dass das Override-System von PrestaShop aktiviert ist. Diese Einstellung finden Sie normalerweise unter **Erweiterte Parameter > Leistung**. Suchen Sie nach einer Option, die sich auf "Nicht-PrestaShop-Module deaktivieren" oder "Overrides deaktivieren" bezieht, und stellen Sie sicher, dass sie auf "Nein" gesetzt ist.
        2.  **Modul neu installieren:** Manchmal kann eine Neuinstallation des Moduls Override-Probleme beheben. Deinstallieren Sie das Modul, leeren Sie Ihren PrestaShop-Cache und installieren Sie es dann erneut.
        3.  **Manuelle Override-Überprüfung:** Überprüfen Sie, ob die Override-Dateien des Moduls in Ihren Verzeichnissen `override/classes/` und `override/controllers/` vorhanden sind (z. B. `override/classes/Dispatcher.php`, `override/controllers/front/ProductController.php`). Wenn sie fehlen, deutet dies auf ein Installationsproblem hin.
    -   Wenn das Problem weiterhin besteht, wenden Sie sich bitte an den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Pretty / Clean URLs PRO“ arbeitet, indem es Kern-PrestaShop-Klassen, insbesondere `Dispatcher` und `Link`, überschreibt, um die Generierung und das Parsen von URLs zu ändern. Es fängt die Standard-URL-Routing- und Generierungslogik ab, um IDs und Erweiterungen basierend auf seinen Konfigurationseinstellungen zu entfernen. Das Modul nutzt das Override-System von PrestaShop (`/override/`), um seine benutzerdefinierte Logik ohne direkte Änderung von Kerndateien einzufügen, wodurch die Upgrade-Kompatibilität gewährleistet wird. Es enthält auch einen Admin-Controller-Override für `AdminProductsController`, um sicherzustellen, dass die Friendly URL-Generierung im Back Office mit den Moduleinstellungen übereinstimmt.

### 4.2 Controller (`controllers/`)

Das Modul verwendet hauptsächlich Front-Office-Controller-Overrides, um die URL-Generierung und das Routing zu ändern.

-   **Front-Office-Controller**:

    -   `purls/override/controllers/front/CartController.php`
        -   **Klassenname & übergeordnete Klasse**: `CartController` (überschreibt `CartControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Warenkorb-bezogene Links, um sicherzustellen, dass sie sauber und, wo zutreffend, ID-frei sind.
    -   `purls/override/controllers/front/CmsController.php`
        -   **Klassenname & übergeordnete Klasse**: `CmsController` (überschreibt `CmsControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für CMS-Seiten, entfernt IDs und `.html`-Erweiterungen wie konfiguriert.
    -   `purls/override/controllers/front/listing/CategoryController.php`
        -   **Klassenname & übergeordnete Klasse**: `CategoryController` (überschreibt `CategoryControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Kategorieseiten, entfernt IDs und sorgt für saubere URLs.
    -   `purls/override/controllers/front/listing/index.php`
        -   **Klassenname & übergeordnete Klasse**: Kein direkter Controller, wahrscheinlich eine leere Datei oder ein Platzhalter. Der PrestaShop-Autoloader könnte andere Dateien in diesem Verzeichnis aufnehmen.
        -   **Verantwortlichkeit**: Keine direkte Verantwortlichkeit; dient als Verzeichnis-Marker.
    -   `purls/override/controllers/front/listing/ManufacturerController.php`
        -   **Klassenname & übergeordnete Klasse**: `ManufacturerController` (überschreibt `ManufacturerControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Herstellerseiten, entfernt IDs und sorgt für saubere URLs.
    -   `purls/override/controllers/front/listing/SupplierController.php`
        -   **Klassenname & übergeordnete Klasse**: `SupplierController` (überschreibt `SupplierControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Lieferantenseiten, entfernt IDs und sorgt für saubere URLs.
    -   `purls/override/controllers/front/ProductController.php`
        -   **Klassenname & übergeordnete Klasse**: `ProductController` (überschreibt `ProductControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Produktseiten, entfernt IDs und `.html`-Erweiterungen wie konfiguriert.
-   **Back-Office Admin-Controller**:

    -   `purls/override/controllers/admin/AdminProductsController.php`
        -   **Klassenname & übergeordnete Klasse**: `AdminProductsController` (überschreibt `AdminProductsControllerCore`)
        -   **Verantwortlichkeit**: Integriert sich in die Produktverwaltungsoberfläche, um sicherzustellen, dass beim Generieren oder Aktualisieren von Friendly URLs im Back Office diese den Moduleinstellungen entsprechen (z. B. Entfernen von IDs). Es modifiziert wahrscheinlich die Methode `generateFriendlyUrl` oder ähnliche Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

Die Kernlogik des Moduls liegt in seinen Klassen-Overrides, die grundlegend dafür sind, wie PrestaShop URLs handhabt.

-   `purls/override/classes/Dispatcher.php`
    -   **Klassenname & übergeordnete Klasse**: `Dispatcher` (überschreibt `DispatcherCore`)
    -   **Datenbankinteraktion**: Keine direkte, aber interagiert mit `ps_configuration` für Moduleinstellungen.
    -   **Wichtige öffentliche Methoden und Geschäftslogik**: Diese Klasse ist verantwortlich für das Routing eingehender Anfragen an den richtigen Controller und für die Generierung von URLs. Der Override modifiziert wahrscheinlich Methoden wie `getFriendlyUrl` oder `createUrl`, um IDs und Erweiterungen zu entfernen und die 301-Weiterleitungslogik für alte URLs zu handhaben. Es ist der zentrale Punkt für das Parsen und Generieren von URLs.
-   `purls/override/classes/Link.php`
    -   **Klassenname & übergeordnete Klasse**: `Link` (überschreibt `LinkCore`)
    -   **Datenbankinteraktion**: Keine direkte, aber interagiert mit `ps_configuration` für Moduleinstellungen.
    -   **Wichtige öffentliche Methoden und Geschäftslogik**: Die `Link`-Klasse wird in PrestaShop verwendet, um URLs für verschiedene Entitäten (Produkte, Kategorien, CMS usw.) zu konstruieren. Der Override in diesem Modul modifiziert Methoden wie `getProductLink`, `getCategoryLink`, `getCMSLink` usw., um URLs zu generieren, die sauber, ID-frei und ohne `.html`-Erweiterungen gemäß der Modulkonfiguration sind. Es arbeitet in Verbindung mit dem `Dispatcher`-Override, um eine konsistente URL-Generierung zu gewährleisten.

### 4.4 JavaScript-Assets (`views/js/`)

-   `purls/views/js/purls.js`
    -   **Geltungsbereich**: Back-Office (wahrscheinlich auf Produkt-/Kategorie-/CMS-Bearbeitungsseiten).
    -   **Details**: Dieses Skript enthält wahrscheinlich clientseitige Logik, um den Friendly URL-Generierungsprozess innerhalb des PrestaShop Back Office zu verbessern. Es könnte:
        -   Auf Änderungen in Produkt-/Kategorie-/CMS-Namen reagieren und das Feld „Friendly URL“ automatisch basierend auf den Moduleinstellungen aktualisieren.
        -   Echtzeit-Feedback oder Validierung für die generierten URLs bereitstellen.
        -   Potenziell mit AJAX-Aufrufen an den Server interagieren, um vorgeschlagene Friendly URLs zu erhalten.
        -   Sicherstellen, dass die Schaltfläche „URL generieren“ (falls vorhanden) die Modullogik auslöst.

### 4.5 CSS-Stylesheets (`views/css/`)

Es wurden keine benutzerdefinierten CSS-Dateien im Modularchiv gefunden, was darauf hindeutet, dass das Modul keine neuen visuellen Elemente einführt, die eine spezifische Formatierung erfordern. Es verlässt sich auf die Standard-Back-Office-Formatierung von PrestaShop für seine Konfigurationsseite.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Admin-Templates (`views/templates/admin/`)**:
    -   `purls/views/purls.tpl`
        -   **Geltungsbereich**: Back-Office, Modulkonfigurationsseite.
        -   **Details**: Dieses Template rendert das Hauptkonfigurationsformular für das Modul „Pretty / Clean URLs PRO“. Es enthält die HTML-Struktur für alle in Abschnitt 4.1 beschriebenen Einstellungen, einschließlich Schaltern zum Aktivieren/Deaktivieren von Funktionen und der Schaltfläche „Speichern“. Es verwendet Standard-PrestaShop-Formularhelfer und -Styling.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    -   Es speichert seine Konfigurationseinstellungen in der Standard-PrestaShop-Tabelle `ps_configuration`. Die Konfigurationsschlüssel würden typischerweise einem Muster wie `PURLS_ENABLE`, `PURLS_REMOVE_IDS`, `PURLS_301_REDIRECT` usw. folgen.
-   **Registrierte Hooks-Tabelle**:
    Das Modul arbeitet hauptsächlich über Klassen-Overrides und nicht über direkte Hook-Registrierung für seine Kernfunktionalität. Es könnte jedoch implizit mit Hooks interagieren, die die URL-Generierung oder -Weiterleitung auslösen.

| Hook-Name                 | Ausführungszeitpunkt | Technischer Zweck
title: "Pretty / Clean URLs PRO - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Pretty / Clean URLs PRO von MyPresta.eu."
sidebar:
  label: "Pretty / Clean URLs PRO - Händlerhandurationsanleitung"
---

# Pretty / Clean URLs PRO

## 5. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.0.0 - 1.7.4.x, 1.7.5.0 - 1.7.7.x, 1.7.8.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ihr Server muss außerdem `mod_rewrite` für Apache oder eine gleichwertige URL-Rewriting-Funktionalität für Nginx aktiviert haben, was für die meisten PrestaShop-Installationen Standard ist.
-   **PrestaShop Friendly URLs**: Die native Option „Friendly URL“ von PrestaShop (zu finden unter **Shop-Parameter > SEO & URLs**) *muss aktiviert sein*, damit dieses Modul korrekt funktioniert. Dieses Modul erweitert die native Funktionalität von PrestaShop, es ersetzt sie nicht.

## 6. Vollständige Konfigurationsanleitung

### 6.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite für „Pretty / Clean URLs PRO“. Hier steuern Sie das Kernverhalten des Moduls.

**Allgemeine Einstellungen**

-   **Pretty URLs aktivieren:**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Er steuert, ob das Modul aktiv saubere URLs in Ihrem gesamten Shop generiert und verwendet.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul beginnt, saubere URLs für alle unterstützten Seitentypen (Produkte, Kategorien, CMS usw.) zu generieren und darauf umzuleiten.
        -   *Wenn deaktiviert:* Das Modul ist inaktiv, und PrestaShop kehrt zu seiner Standard-URL-Struktur zurück (die IDs enthalten kann).
    -   **Empfohlener Wert:** **JA** (Dies ist die Hauptfunktion des Moduls).
    -   **Händler-Szenario / Beispiel:** Sie haben das Modul gerade installiert und möchten seine SEO-Vorteile aktivieren. Sie würden diese Einstellung aktivieren. Wenn Sie vorübergehend Fehler beheben oder zum Standardverhalten von PrestaShop zurückkehren müssen, könnten Sie sie deaktivieren.
-   **IDs aus URLs entfernen:**
    -   **Was diese Einstellung bewirkt:** Diese Option steuert speziell, ob die numerische ID (z. B. `123` in `ihrshop.com/123-mein-produkt`) aus den URLs entfernt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* URLs werden kürzer und sauberer, wie `ihrshop.com/mein-produkt`. Dies ist im Allgemeinen besser für SEO und Ästhetik.
        -   *Wenn deaktiviert:* URLs bleiben „schön“, behalten aber die ID bei, z. B. `ihrshop.com/123-mein-produkt`. Dies könnte nützlich sein, wenn Sie externe Systeme haben, die darauf angewiesen sind, dass die ID in der URL vorhanden ist, obwohl dies seltener vorkommt.
    -   **Empfohlener Wert:** **JA** (Für maximalen SEO-Vorteil und saubere Ästhetik).
    -   **Händler-Szenario / Beispiel:** Sie möchten die absolut saubersten URLs für eine bessere Suchmaschinenindizierung und Benutzerlesbarkeit. Sie würden dies aktivieren.
-   **Automatische 301-Weiterleitung:**
    -   **Was diese Einstellung bewirkt:** Diese kritische Einstellung weist das Modul an, automatisch permanente 301-Weiterleitungen von alten, ID-basierten URLs zu den neuen, sauberen URLs zu erstellen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Jeder Besucher oder Suchmaschinen-Bot, der versucht, auf eine alte URL zuzugreifen (z. B. eine, die vor der Aktivierung des Moduls indiziert wurde), wird nahtlos zur neuen, sauberen URL weitergeleitet. Dies verhindert 404-Fehler und bewahrt Ihren SEO-Link-Wert.
        -   *Wenn deaktiviert:* Alte URLs führen zu 404 „Seite nicht gefunden“-Fehlern, was schlecht für die Benutzererfahrung ist und Ihrem SEO erheblich schaden kann.
    -   **Empfohlener Wert:** **JA** (Absolut unerlässlich für die Aufrechterhaltung von SEO und Benutzererfahrung während und nach dem Übergang zu sauberen URLs).
    -   **Händler-Szenario / Beispiel:** Sie haben das Modul gerade in einem bestehenden Shop mit vielen indizierten Seiten aktiviert. Die Aktivierung stellt sicher, dass alle Ihre alten Links weiterhin funktionieren und ihren SEO-Wert an die neuen Links weitergeben.
-   **Trailing Slash erzwingen:**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob immer ein abschließender Schrägstrich (`/`) am Ende Ihrer URLs hinzugefügt wird (z. B. `ihrshop.com/kategorie/` vs. `ihrshop.com/kategorie`).
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Alle generierten URLs enden mit einem Schrägstrich. Dies kann zur URL-Konsistenz beitragen und wird von einigen SEO-Tools bevorzugt.
        -   *Wenn deaktiviert:* URLs enden nicht unbedingt mit einem Schrägstrich, abhängig vom Standardverhalten von PrestaShop für diesen Seitentyp.
    -   **Empfohlener Wert:** **JA** (Für Konsistenz und um potenzielle Probleme mit doppeltem Inhalt zu vermeiden, falls Suchmaschinen `url` und `url/` als verschiedene Seiten behandeln).
    -   **Händler-Szenario / Beispiel:** Sie möchten sicherstellen, dass alle Ihre Kategorie- und CMS-Seiten-URLs konsistent mit einem Schrägstrich enden, um ein besseres SEO-Management zu gewährleisten und potenzielle Probleme mit doppeltem Inhalt zu vermeiden.
-   **`.html`-Erweiterung entfernen:**
    -   **Was diese Einstellung bewirkt:** Diese Option steuert, ob die `.html`-Erweiterung aus Produkt- und CMS-Seiten-URLs entfernt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* URLs werden noch kürzer, z. B. `ihrshop.com/mein-produkt` anstelle von `ihrshop.com/mein-produkt.html`. Dies wird im Allgemeinen für modernes Webdesign und SEO bevorzugt.
        -   *Wenn deaktiviert:* Produkt- und CMS-Seiten-URLs behalten die `.html`-Erweiterung bei.
    -   **Empfohlener Wert:** **JA** (Für die sauberste, modernste URL-Struktur).
    -   **Händler-Szenario / Beispiel:** Sie möchten, dass Ihre Produktseiten wie `ihrshop.com/mein-produkt` anstelle von `ihrshop.com/mein-produkt.html` aussehen, um ein schlankeres Erscheinungsbild und besseres SEO zu erzielen.

**Speichern-Schaltfläche:**

-   Klicken Sie immer auf die Schaltfläche „Speichern“, nachdem Sie Änderungen vorgenommen haben, um sie in Ihrem Shop anzuwenden.

### 6.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul funktioniert hauptsächlich, indem es Kern-PrestaShop-Klassen und -Controller überschreibt, um die URL-Generierung und das Routing zu ändern. Obwohl es kein neues, dediziertes Menüelement im Back Office zur Verwaltung einer Liste von „Pretty URLs“ einführt, integriert es sich direkt in bestehende PrestaShop-Funktionalitäten.

**`AdminProductsController`-Integration (Back Office > Katalog > Produkte)**

-   **Bildschirmname & Menüpfad:** **Katalog > Produkte**
-   **Verfügbare Aktionen & Einstellungen:**
    -   Wenn Sie ein Produkt bearbeiten oder erstellen, beeinflusst das Modul das Verhalten des Feldes „Friendly URL“. Anstatt dass Sie IDs manuell entfernen oder eine saubere Struktur sicherstellen müssen, generiert und schlägt die Modullogik automatisch eine saubere, ID-freie URL basierend auf Ihrem Produktnamen und den Moduleinstellungen vor.
    -   Das Modul stellt sicher, dass beim Speichern eines Produkts dessen URL gemäß Ihren „Pretty / Clean URLs PRO“-Einstellungen generiert wird (z. B. keine ID, keine `.html`-Erweiterung, falls konfiguriert).
-   **Auswirkung von Änderungen:**
    -   Wenn Sie ein Produkt speichern, spiegelt die von PrestaShop generierte und verwendete URL die in der Modulkonfiguration definierte saubere URL-Struktur wider.
    -   Wenn Sie den Namen eines Produkts ändern, hilft das Modul sicherzustellen, dass die Friendly URL sauber aktualisiert wird.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    -   Verwalten Sie Ihre Produkte wie gewohnt unter **Katalog > Produkte**. Das Modul arbeitet im Hintergrund, um sicherzustellen, dass die URLs optimiert sind.
    -   Stellen Sie beim Erstellen oder Bearbeiten von Produkten sicher, dass Ihre Produktnamen beschreibend sind, da diese zur Generierung der Friendly URLs verwendet werden.
    -   Sie können das Feld „Friendly URL“ für ein Produkt weiterhin manuell anpassen, wenn Sie eine bestimmte URL benötigen, aber die Modullogik leitet die anfängliche Generierung.

**Andere Admin-Controller (Implizite Integration)**

Das Modul beeinflusst auch implizit andere Bereiche, in denen URLs generiert werden, wie zum Beispiel:

-   **Katalog > Kategorien**: Beim Erstellen oder Bearbeiten von Kategorien.
-   **Katalog > Hersteller**: Beim Erstellen oder Bearbeiten von Herstellern.
-   **Katalog > Lieferanten**: Beim Erstellen oder Bearbeiten von Lieferanten.
-   **Design > Seiten (CMS)**: Beim Erstellen oder Bearbeiten von CMS-Seiten.

In all diesen Fällen stellt das Modul sicher, dass die von PrestaShop generierten Friendly URLs den „Pretty / Clean URLs PRO“-Einstellungen entsprechen und IDs und Erweiterungen wie konfiguriert entfernen.

### 6.3 PrestaShop SEO & URLs Einstellungen Integration

Das Modul "Pretty / Clean URLs PRO" ab Version 2.8.3 und höher verfügt über einen eigenen Bereich zur Definition von URL-Schemata, wodurch es nicht mehr notwendig ist, diese Einstellungen manuell unter PrestaShops nativem Bereich **Shop-Parameter > SEO & URLs** zu konfigurieren. Es ist jedoch entscheidend, die Interaktion zu verstehen.

:::caution Wichtiger Hinweis
Während das Modul das URL-Schema verwaltet, *muss* die native PrestaShop-Option **Friendly URL** unter **Shop-Parameter > SEO & URLs** aktiviert sein, damit das Modul funktioniert. Das Modul erweitert diese Kernfunktionalität von PrestaShop.
:::

**Schema der URLs (vom Modul verwaltet)**

Historisch gesehen definierten PrestaShop-Benutzer die URL-Muster (Routen) für Produkte, Kategorien, CMS-Seiten usw. im Bereich **Shop-Parameter > SEO & URLs**. Das Modul "Pretty / Clean URLs PRO" übernimmt nun diese Verantwortung und ermöglicht es Ihnen, diese direkt von seiner eigenen Konfigurationsseite aus zu konfigurieren.

Das Modul stellt sicher, dass die Routen so eingestellt sind, dass `{id}` aus den URLs entfernt wird, was für wirklich saubere URLs unerlässlich ist. Wenn Sie aus irgendeinem Grund feststellen, dass die Routen unter **Shop-Parameter > SEO & URLs** nach der Installation und Konfiguration des Moduls immer noch `{id}` enthalten, könnte dies auf ein Problem mit Modul-Overrides hinweisen (siehe Abschnitt 6 zur Fehlerbehebung).

Als Referenz sind hier die empfohlenen Routenstrukturen aufgeführt, die das Modul implementieren soll:

| Routentyp                 | Standard PrestaShop-Wert (Beispiel) | Gewünschter Wert des Moduls (Sauber) |
| :------------------------ | :---------------------------------- | :----------------------------------- |
| Route zum Produkt         | `{category:/}{id}-{rewrite}{-:ean13}.html` | `{category:/}{rewrite}.html` (oder `{rewrite}.html`) |
| Route zur Kategorie       | `{id}-{rewrite}`                    | `{parent_categories:/}{rewrite}/` (oder `{rewrite}/`) |
| Route zum Lieferanten     | `{id}__{rewrite}`                   | `supplier/{rewrite}/`                |
| Route zum Hersteller      | `{id}_{rewrite}`                    | `manufacturer/{rewrite}/`            |
| Route zur CMS-Seite       | `content/{id}-{rewrite}`            | `info/{rewrite}.html`                |
| Route zur CMS-Kategorieseite | `content/category/{id}-{rewrite}`   | `info/{rewrite}`                     |

:::tip Multishop-Umgebung
Wenn Sie einen PrestaShop-Multishop betreiben, denken Sie daran, die URL-Schema-Einstellungen für jeden einzelnen Shop zu überprüfen und gegebenenfalls anzupassen. Sie können den Shop, den Sie konfigurieren möchten, über das Shop-Kontextmenü in Ihrem Back Office auswählen.
:::

### 6.4 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Pretty URLs aktivieren | JA | Aktiviert/deaktiviert die Kernfunktionalität des Moduls. |
| Modulkonfiguration | IDs aus URLs entfernen | JA | Entfernt numerische IDs aus URLs (z. B. `123-produkt` wird zu `produkt`). |
| Modulkonfiguration | Automatische 301-Weiterleitung | JA | Leitet alte ID-basierte URLs auf neue saubere URLs um, bewahrt SEO. |
| Modulkonfiguration | Trailing Slash erzwingen | JA | Stellt sicher, dass alle URLs mit einem `/` enden, für Konsistenz und SEO. |
| Modulkonfiguration | `.html`-Erweiterung entfernen | JA | Entfernt `.html` aus Produkt-/CMS-Seiten-URLs für sauberere Links. |
| Katalog > Produkte (Bearbeiten) | Friendly URL-Feld | Automatisch generiert | Modul beeinflusst die automatische Generierung sauberer URLs für Produkte. |
| Katalog > Kategorien (Bearbeiten) | Friendly URL-Feld | Automatisch generiert | Modul beeinflusst die automatische Generierung sauberer URLs für Kategorien. |
| Design > Seiten (Bearbeiten) | Friendly URL-Feld | Automatisch generiert | Modul beeinflusst die automatische Generierung sauberer URLs für CMS-Seiten. |
| Shop-Parameter > SEO & URLs | Friendly URL | JA | **KRITISCH:** Muss aktiviert sein, damit das Modul funktioniert. |

## 7. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Nach der Installation sehen meine URLs immer noch gleich aus, oder ich erhalte 404-Fehler.**

-   **A:** Stellen Sie zunächst sicher, dass „Pretty URLs aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
-   Zweitens, gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
-   Drittens, stellen Sie sicher, dass die native PrestaShop-Option „Friendly URL“ unter **Shop-Parameter > SEO & URLs** aktiviert ist. Dieses Modul erweitert die native Friendly URL-Funktionalität von PrestaShop, es ersetzt sie nicht vollständig.
-   Überprüfen Sie schließlich die `.htaccess`-Datei Ihres Servers (wenn Sie Apache verwenden) oder die Nginx-Konfiguration. Das Modul ist auf serverseitiges URL-Rewriting (mod_rewrite für Apache) angewiesen, um korrekt zu funktionieren. Wenn Sie unsicher sind, wenden Sie sich an Ihren Hosting-Anbieter.

**F2: Mein benutzerdefiniertes Theme hat nach der Aktivierung des Moduls einige seltsame Anzeigeprobleme.**

-   **A:** Dieses Modul beeinflusst hauptsächlich die URL-Generierung und -Weiterleitung, nicht die visuelle Anzeige. Es ist unwahrscheinlich, dass es direkt Theme-Anzeigeprobleme verursacht. Wenn Sie jedoch den Cache geleert haben, müssen die CSS- oder JS-Dateien Ihres Themes möglicherweise neu geladen werden. Versuchen Sie, den Browser-Cache zu leeren. Wenn das Problem weiterhin besteht, könnte es ein Konflikt mit einem anderen Modul oder einer benutzerdefinierten Theme-Modifikation sein. Deaktivieren Sie „Pretty / Clean URLs PRO“ vorübergehend, um zu sehen, ob das Problem behoben wird. Wenn ja, wenden Sie sich an den MyPresta.eu-Support.

**F3: Wird dieses Modul mit meinen bestehenden benutzerdefinierten URLs oder Weiterleitungen funktionieren?**

-   **A:** Das Modul konzentriert sich auf die Generierung sauberer URLs für Kern-PrestaShop-Entitäten (Produkte, Kategorien, CMS usw.). Wenn Sie manuell benutzerdefinierte Weiterleitungen oder spezifische Friendly URLs außerhalb des PrestaShop-Standardsystems erstellt haben, priorisiert die automatische 301-Weiterleitung des Moduls seine eigenen generierten sauberen URLs. Es ist im Allgemeinen am besten, das Modul alle Kern-Entitäts-URLs für Konsistenz verwalten zu lassen. Wenn Sie sehr spezifische benutzerdefinierte Weiterleitungen haben, müssen Sie möglicherweise testen, wie sie interagieren.

**F4: Ich habe einen Produktnamen geändert, aber die URL wurde nicht automatisch aktualisiert.**

-   **A:** Wenn Sie den Namen eines Produkts ändern, schlägt PrestaShop normalerweise eine neue Friendly URL vor. Sie müssen das Produkt explizit speichern, damit die Änderungen wirksam werden und das Modul die neue URL verarbeiten kann. Wenn das Friendly URL-Feld nicht automatisch aktualisiert wird, müssen Sie möglicherweise manuell auf „URL generieren“ neben dem Friendly URL-Feld auf der Produktbearbeitungsseite klicken und dann das Produkt speichern. Das Modul stellt dann sicher, dass diese neue URL sauber ist und die Weiterleitung von der alten URL übernimmt.

**F5: Beeinflusst dieses Modul meine mehrsprachigen URLs?**

-   **A:** Nein, es verbessert sie! Das Modul arbeitet mit den mehrsprachigen Funktionen von PrestaShop zusammen. Es generiert saubere URLs für jede Sprache, wobei der Sprachcode in der URL berücksichtigt wird (z. B. `/de/mein-produkt` und `/fr/mon-produit`). Stellen Sie sicher, dass Ihre Produkt-, Kategorie- und CMS-Seitennamen für jede Sprache übersetzt sind, um die besten Friendly URLs zu erhalten.

**F6: Ich sehe eine Fehlermeldung "Schlüsselwort {id} ist für die Route (...) erforderlich", wenn ich versuche, URL-Schemata zu speichern.**

-   **A:** Dieser Fehler tritt typischerweise auf, wenn die Overrides des Moduls (ein Kernbestandteil seiner Funktionalität) nicht korrekt installiert oder in Ihrem PrestaShop-Shop deaktiviert sind. Das Modul ist auf diese Overrides angewiesen, um das Standard-URL-Routing-Verhalten von PrestaShop zu ändern, wodurch es das `{id}` aus den Routen entfernen kann.
    -   **Lösung:**
        1.  **Overrides überprüfen:** Stellen Sie sicher, dass das Override-System von PrestaShop aktiviert ist. Diese Einstellung finden Sie normalerweise unter **Erweiterte Parameter > Leistung**. Suchen Sie nach einer Option, die sich auf "Nicht-PrestaShop-Module deaktivieren" oder "Overrides deaktivieren" bezieht, und stellen Sie sicher, dass sie auf "Nein" gesetzt ist.
        2.  **Modul neu installieren:** Manchmal kann eine Neuinstallation des Moduls Override-Probleme beheben. Deinstallieren Sie das Modul, leeren Sie Ihren PrestaShop-Cache und installieren Sie es dann erneut.
        3.  **Manuelle Override-Überprüfung:** Überprüfen Sie, ob die Override-Dateien des Moduls in Ihren Verzeichnissen `override/classes/` und `override/controllers/` vorhanden sind (z. B. `override/classes/Dispatcher.php`, `override/controllers/front/ProductController.php`). Wenn sie fehlen, deutet dies auf ein Installationsproblem hin.
    -   Wenn das Problem weiterhin besteht, wenden Sie sich bitte an den MyPresta.eu-Support.

## 8. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 8.1 Architekturübersicht

Das Modul „Pretty / Clean URLs PRO“ arbeitet, indem es Kern-PrestaShop-Klassen, insbesondere `Dispatcher` und `Link`, überschreibt, um die Generierung und das Parsen von URLs zu ändern. Es fängt die Standard-URL-Routing- und Generierungslogik ab, um IDs und Erweiterungen basierend auf seinen Konfigurationseinstellungen zu entfernen. Das Modul nutzt das Override-System von PrestaShop (`/override/`), um seine benutzerdefinierte Logik ohne direkte Änderung von Kerndateien einzufügen, wodurch die Upgrade-Kompatibilität gewährleistet wird. Es enthält auch einen Admin-Controller-Override für `AdminProductsController`, um sicherzustellen, dass die Friendly URL-Generierung im Back Office mit den Moduleinstellungen übereinstimmt.

### 8.2 Controller (`controllers/`)

Das Modul verwendet hauptsächlich Front-Office-Controller-Overrides, um die URL-Generierung und das Routing zu ändern.

-   **Front-Office-Controller**:

    -   `purls/override/controllers/front/CartController.php`
        -   **Klassenname & übergeordnete Klasse**: `CartController` (überschreibt `CartControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Warenkorb-bezogene Links, um sicherzustellen, dass sie sauber und, wo zutreffend, ID-frei sind.
    -   `purls/override/controllers/front/CmsController.php`
        -   **Klassenname & übergeordnete Klasse**: `CmsController` (überschreibt `CmsControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für CMS-Seiten, entfernt IDs und `.html`-Erweiterungen wie konfiguriert.
    -   `purls/override/controllers/front/listing/CategoryController.php`
        -   **Klassenname & übergeordnete Klasse**: `CategoryController` (überschreibt `CategoryControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Kategorieseiten, entfernt IDs und sorgt für saubere URLs.
    -   `purls/override/controllers/front/listing/index.php`
        -   **Klassenname & übergeordnete Klasse**: Kein direkter Controller, wahrscheinlich eine leere Datei oder ein Platzhalter. Der PrestaShop-Autoloader könnte andere Dateien in diesem Verzeichnis aufnehmen.
        -   **Verantwortlichkeit**: Keine direkte Verantwortlichkeit; dient als Verzeichnis-Marker.
    -   `purls/override/controllers/front/listing/ManufacturerController.php`
        -   **Klassenname & übergeordnete Klasse**: `ManufacturerController` (überschreibt `ManufacturerControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Herstellerseiten, entfernt IDs und sorgt für saubere URLs.
    -   `purls/override/controllers/front/listing/SupplierController.php`
        -   **Klassenname & übergeordnete Klasse**: `SupplierController` (überschreibt `SupplierControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Lieferantenseiten, entfernt IDs und sorgt für saubere URLs.
    -   `purls/override/controllers/front/ProductController.php`
        -   **Klassenname & übergeordnete Klasse**: `ProductController` (überschreibt `ProductControllerCore`)
        -   **Verantwortlichkeit**: Ändert die URL-Generierung für Produktseiten, entfernt IDs und `.html`-Erweiterungen wie konfiguriert.
-   **Back-Office Admin-Controller**:

    -   `purls/override/controllers/admin/AdminProductsController.php`
        -   **Klassenname & übergeordnete Klasse**: `AdminProductsController` (überschreibt `AdminProductsControllerCore`)
        -   **Verantwortlichkeit**: Integriert sich in die Produktverwaltungsoberfläche, um sicherzustellen, dass beim Generieren oder Aktualisieren von Friendly URLs im Back Office diese den Moduleinstellungen entsprechen (z. B. Entfernen von IDs). Es modifiziert wahrscheinlich die Methode `generateFriendlyUrl` oder ähnliche Logik.

### 8.3 Kernklassen & Modelle (`classes/`)

Die Kernlogik des Moduls liegt in seinen Klassen-Overrides, die grundlegend dafür sind, wie PrestaShop URLs handhabt.

-   `purls/override/classes/Dispatcher.php`
    -   **Klassenname & übergeordnete Klasse**: `Dispatcher` (überschreibt `DispatcherCore`)
    -   **Datenbankinteraktion**: Keine direkte, aber interagiert mit `ps_configuration` für Moduleinstellungen.
    -   **Wichtige öffentliche Methoden und Geschäftslogik**: Diese Klasse ist verantwortlich für das Routing eingehender Anfragen an den richtigen Controller und für die Generierung von URLs. Der Override modifiziert wahrscheinlich Methoden wie `getFriendlyUrl` oder `createUrl`, um IDs und Erweiterungen zu entfernen und die 301-Weiterleitungslogik für alte URLs zu handhaben. Es ist der zentrale Punkt für das Parsen und Generieren von URLs.
-   `purls/override/classes/Link.php`
    -   **Klassenname & übergeordnete Klasse**: `Link` (überschreibt `LinkCore`)
    -   **Datenbankinteraktion**: Keine direkte, aber interagiert mit `ps_configuration` für Moduleinstellungen.
    -   **Wichtige öffentliche Methoden und Geschäftslogik**: Die `Link`-Klasse wird in PrestaShop verwendet, um URLs für verschiedene Entitäten (Produkte, Kategorien, CMS usw.) zu konstruieren. Der Override in diesem Modul modifiziert Methoden wie `getProductLink`, `getCategoryLink`, `getCMSLink` usw., um URLs zu generieren, die sauber, ID-frei und ohne `.html`-Erweiterungen gemäß der Modulkonfiguration sind. Es arbeitet in Verbindung mit dem `Dispatcher`-Override, um eine konsistente URL-Generierung zu gewährleisten.

### 8.4 JavaScript-Assets (`views/js/`)

-   `purls/views/js/purls.js`
    -   **Geltungsbereich**: Back-Office (wahrscheinlich auf Produkt-/Kategorie-/CMS-Bearbeitungsseiten).
    -   **Details**: Dieses Skript enthält wahrscheinlich clientseitige Logik, um den Friendly URL-Generierungsprozess innerhalb des PrestaShop Back Office zu verbessern. Es könnte:
        -   Auf Änderungen in Produkt-/Kategorie-/CMS-Namen reagieren und das Feld „Friendly URL“ automatisch basierend auf den Moduleinstellungen aktualisieren.
        -   Echtzeit-Feedback oder Validierung für die generierten URLs bereitstellen.
        -   Potenziell mit AJAX-Aufrufen an den Server interagieren, um vorgeschlagene Friendly URLs zu erhalten.
        -   Sicherstellen, dass die Schaltfläche „URL generieren“ (falls vorhanden) die Modullogik auslöst.

### 8.5 CSS-Stylesheets (`views/css/`)

Es wurden keine benutzerdefinierten CSS-Dateien im Modularchiv gefunden, was darauf hindeutet, dass das Modul keine neuen visuellen Elemente einführt, die eine spezifische Formatierung erfordern. Es verlässt sich auf die Standard-Back-Office-Formatierung von PrestaShop für seine Konfigurationsseite.

### 8.6 Smarty-Template-Struktur (`views/templates/`)

-   **Admin-Templates (`views/templates/admin/`)**:
    -   `purls/views/purls.tpl`
        -   **Geltungsbereich**: Back-Office, Modulkonfigurationsseite.
        -   **Details**: Dieses Template rendert das Hauptkonfigurationsformular für das Modul „Pretty / Clean URLs PRO“. Es enthält die HTML-Struktur für alle in Abschnitt 4.1 beschriebenen Einstellungen, einschließlich Schaltern zum Aktivieren/Deaktivieren von Funktionen und der Schaltfläche „Speichern“. Es verwendet Standard-PrestaShop-Formularhelfer und -Styling.

### 8.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    -   Es speichert seine Konfigurationseinstellungen in der Standard-PrestaShop-Tabelle `ps_configuration`. Die Konfigurationsschlüssel würden typischerweise einem Muster wie `PURLS_ENABLE`, `PURLS_REMOVE_IDS`, `PURLS_301_REDIRECT` usw. folgen.
-   **Registrierte Hooks-Tabelle**:
    Das Modul arbeitet hauptsächlich über Klassen-Overrides und nicht über direkte Hook-Registrierung für seine Kernfunktionalität. Es könnte jedoch implizit mit Hooks interagieren, die die URL-Generierung oder -Weiterleitung auslösen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Bei jedem Seitenaufruf im Front Office, innerhalb des `<head>`-Bereichs. | Obwohl keine visuellen Elemente direkt registriert werden, sind die `Dispatcher`- und `Link`-Overrides des Moduls während des Seiten-Renderings aktiv und beeinflussen alle im Header generierten URLs (z. B. kanonische URLs, Sprachumschalter). |
| `actionDispatcherBefore` | Bevor der Dispatcher die Anfrage verarbeitet. | Der `Dispatcher`-Override ist in diesem Stadium aktiv, wodurch das Modul die URL-Parsing- und Routing-Logik abfangen und ändern kann, bevor PrestaShop entscheidet, welcher Controller geladen werden soll. Dies ist entscheidend für die Handhabung von 301-Weiterleitungen von alten URLs. |
| `actionDispatcherAfter` | Nachdem der Dispatcher die Anfrage verarbeitet hat. | Der `Dispatcher`-Override kann auch hier aktiv sein, potenziell für die Nachbearbeitung oder Protokollierung im Zusammenhang mit der URL-Behandlung. |
| `actionProductUpdate` / `actionProductAdd` | Nachdem ein Produkt im Back Office aktualisiert oder hinzugefügt wurde. | Der `AdminProductsController`-Override stellt sicher, dass beim Speichern eines Produkts dessen Friendly URL gemäß den Moduleinstellungen generiert wird. Dies ist eine implizite Interaktion und keine direkte Hook-Registrierung durch das Modul selbst. |
| `actionCategoryUpdate` / `actionCategoryAdd` | Nachdem eine Kategorie im Back Office aktualisiert oder hinzugefügt wurde. | Ähnlich wie bei Produkten sorgt das Modul für saubere URLs für Kategorien. |
| `actionCmsUpdate` / `actionCmsAdd` | Nachdem eine CMS-Seite im Back Office aktualisiert oder hinzugefügt wurde. | Ähnlich wie bei Produkten sorgt das Modul für saubere URLs für CMS-Seiten. |

## 9. Offizieller Support & Ressourcen

Für offizielle Updates, technischen Support und alle Anfragen bezüglich des Moduls „Pretty / Clean URLs PRO“ verweisen wir auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
