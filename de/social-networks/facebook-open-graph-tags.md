---
title: "Facebook Open Graph Tags – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Open Graph Tags von MyPresta.eu."
sidebar:
  label: "Facebook Open Graph Tags – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Open Graph Tags auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-open-graph-tags.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-open-graph-tags/)
>
> ---


# Facebook Open Graph Tags

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.3.x, 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Facebook Open Graph Tags)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Kernverhalten des Moduls steuern.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Open Graph Tags aktivieren** | Dieser Hauptschalter steuert, ob das Modul überhaupt Open Graph Tags generiert. | *Wenn aktiviert:* Das Modul fügt die notwendigen Open Graph Tags in den HTML `<head>`-Bereich Ihres Shops ein, sodass Facebook Rich Previews anzeigen kann. *Wenn deaktiviert:* Es werden keine Open Graph Tags von diesem Modul generiert, und Facebook versucht, Inhalte zu erraten, was oft zu schlechten oder fehlenden Vorschauen führt. | **JA** | Sie möchten, dass Ihre Produkt-Shares auf Facebook professionell aussehen. |
| **Facebook App ID** | Ihre eindeutige Kennung für Ihre Facebook-Anwendung. Dies verknüpft die Shares Ihrer Website mit Ihrer Facebook-App und ermöglicht Einblicke und Analysen. | *Wenn angegeben:* Facebook kann Shares Ihrer App zuordnen und Ihnen Analysen zur Leistung Ihrer Inhalte auf deren Plattform bereitstellen. *Wenn leer gelassen:* Shares funktionieren weiterhin, aber Sie erhalten keine detaillierten Einblicke über die Entwicklertools von Facebook. | **Ihre Facebook App ID** (falls vorhanden) | Sie möchten die Leistung Ihrer geteilten Inhalte auf Facebook mithilfe von Facebook Insights verfolgen. Wenn Sie keine haben, können Sie es leer lassen. |
| **Facebook Admin ID** | Die Facebook-Benutzer-ID des/der Administrators/Administratoren Ihrer Facebook-Seite oder App. Dies hilft Facebook zu verstehen, wer die Inhalte verwaltet. | *Wenn angegeben:* Facebook weiß, wer der Autor/Administrator des Inhalts ist, was für die Moderation oder spezifische Facebook-Funktionen nützlich sein kann. *Wenn leer gelassen:* Es wird kein spezifischer Administrator verknüpft. | **Ihre Facebook-Benutzer-ID** (falls zutreffend) | Sie möchten Ihr persönliches Facebook-Profil als Administrator für die geteilten Inhalte verknüpfen. |
| **Standardbild für die Startseite** | Diese Einstellung ermöglicht es Ihnen, ein Fallback-Bild anzugeben, das Facebook verwendet, wenn Ihre Startseite geteilt wird, insbesondere wenn Ihre Startseite selbst kein prominentes Bild hat. | *Wenn ein Bild hochgeladen wird:* Dieses Bild wird als `og:image` verwendet, wenn die Startseite Ihres Shops auf Facebook geteilt wird. *Wenn leer gelassen:* Facebook versucht, ein Bild auf Ihrer Startseite zu finden, was nicht immer ideal ist (z. B. ein kleines Logo oder Banner). | **Laden Sie das Hauptlogo Ihres Shops oder ein ansprechendes Bannerbild hoch.** | Ihre Startseite besteht hauptsächlich aus Text, und Sie möchten, dass ein bestimmtes, attraktives Bild erscheint, wenn jemand Ihre Haupt-Shop-URL teilt. |
| **Standardtitel für die Startseite** | Der Titel, den Facebook anzeigt, wenn die Startseite Ihres Shops geteilt wird. | *Wenn angegeben:* Dieser Titel wird als `og:title` für Ihre Startseiten-Shares verwendet. *Wenn leer gelassen:* Facebook verwendet wahrscheinlich den Standard-Meta-Titel Ihres Shops, der möglicherweise nicht für die soziale Freigabe optimiert ist. | **Ihr Shop-Name - Slogan** (z. B. „Mein toller Shop - Entdecken Sie einzigartige Produkte!“) | Sie möchten einen eingängigen, markengerechten Titel, der erscheint, wenn Ihre Haupt-Shop-URL geteilt wird. |
| **Standardbeschreibung für die Startseite** | Die Beschreibung, die Facebook anzeigt, wenn die Startseite Ihres Shops geteilt wird. | *Wenn angegeben:* Diese Beschreibung wird als `og:description` für Ihre Startseiten-Shares verwendet. *Wenn leer gelassen:* Facebook verwendet wahrscheinlich die Standard-Meta-Beschreibung Ihres Shops, die möglicherweise nicht für die soziale Freigabe optimiert ist. | **Eine prägnante, ansprechende Zusammenfassung Ihres Shops.** (z. B. „Entdecken Sie die neuesten Trends in Mode und Elektronik. Schneller weltweiter Versand!“) | Sie möchten die Nachricht steuern, die erscheint, wenn die Startseite Ihres Shops geteilt wird, um Benutzer zum Klicken zu verleiten. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AdminOpenGraphController (Back Office > Erweiterte Einstellungen > Open Graph Tags)

Dieser Bildschirm ermöglicht es Ihnen, spezifische Open Graph Tags für einzelne Seiten zu verwalten oder das Standardverhalten zu überschreiben. Während das Modul automatisch Tags für Produkte und Kategorien generiert, ist dieser Abschnitt nützlich für benutzerdefinierte Seiten oder zur Feinabstimmung.

- **Bildschirmname & Menüpfad:** Sie können diesen Bildschirm erreichen, indem Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Open Graph Tags** navigieren.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt typischerweise eine Tabelle (Liste) der von Ihnen hinzugefügten benutzerdefinierten Open Graph Tag-Konfigurationen. Sie finden Optionen zum:
  - **Neu hinzufügen:** Erstellen Sie einen neuen Satz benutzerdefinierter Open Graph Tags für eine bestimmte URL.
  - **Bearbeiten:** Ändern Sie einen vorhandenen Satz benutzerdefinierter Tags.
  - **Löschen:** Entfernen Sie einen Satz benutzerdefinierter Tags.
  - **Tabellenspalten:** Zeigt normalerweise die URL, den Titel, die Beschreibung und das Bild an, die mit dem benutzerdefinierten Tag verknüpft sind.
- **Auswirkung von Änderungen:**
  - **Hinzufügen eines neuen Eintrags:** Wenn Sie einen neuen Eintrag für eine bestimmte URL hinzufügen (z. B. eine benutzerdefinierte CMS-Seite oder eine Blog-Post-URL), verwendet das Modul den von Ihnen hier angegebenen Titel, die Beschreibung und das Bild, anstatt zu versuchen, diese automatisch zu generieren, wenn diese spezifische URL auf Facebook geteilt wird.
  - **Bearbeiten eines Eintrags:** Aktualisiert die soziale Vorschau für diese spezifische URL.
  - **Löschen eines Eintrags:** Setzt das Verhalten für diese URL auf die automatische Generierung des Moduls oder die Standardeinstellungen der Startseite zurück.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Identifizieren Sie Seiten, die benutzerdefinierte Vorschauen benötigen:** Für die meisten Produkte und Kategorien funktioniert das Modul automatisch. Für benutzerdefinierte CMS-Seiten (z. B. „Über uns“, „Kontakt“, Blog-Beiträge, wenn Sie einen Blog integriert haben) möchten Sie jedoch möglicherweise spezifische, ansprechende Vorschauen.
  2. **Klicken Sie auf „Neu hinzufügen“**, um einen neuen Eintrag zu erstellen.
  3. **Geben Sie die genaue URL** der Seite ein, die Sie anpassen möchten.
  4. **Geben Sie einen überzeugenden Titel, eine Beschreibung und laden Sie ein relevantes Bild** für diese spezifische Seite hoch.
  5. **Speichern** Sie Ihre Änderungen.
  6. **Testen:** Verwenden Sie den [Sharing Debugger](https://developers.facebook.com/tools/debug/) von Facebook, um zu überprüfen, wie Ihre Seite nach den Änderungen aussieht.

#### 2.2.2 index.php (opengraph/controllers/admin/index.php)

Diese Datei ist ein Standard-Einstiegspunkt für PrestaShop-Controller und stellt keinen eigenständigen, konfigurierbaren Bildschirm für Händler dar. Sie wird typischerweise für das Routing oder die grundlegende Modulverwaltung verwendet, nicht für die Verwaltung spezifischer Inhalte oder Einstellungen. Alle händlerseitigen Konfigurationen werden über die Hauptmodulkonfigurationsseite oder den `AdminOpenGraphController` abgewickelt.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Open Graph Tags aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
|  | Facebook App ID | (Ihre App ID) / Leer | Verknüpft Shares mit Ihrer Facebook App für Analysen. |
|  | Facebook Admin ID | (Ihre Benutzer ID) / Leer | Identifiziert den Inhaltsadministrator auf Facebook. |
|  | Standardbild für die Startseite | Ihr Logo hochladen | Fallback-Bild für Startseiten-Shares. |
|  | Standardtitel für die Startseite | Ihr Shop-Name | Titel für Startseiten-Shares. |
|  | Standardbeschreibung für die Startseite | Shop-Slogan | Beschreibung für Startseiten-Shares. |
| **Erweiterte Einstellungen > Open Graph Tags** | Benutzerdefinierte Tags hinzufügen/bearbeiten/löschen | N/A | Überschreibt automatisch generierte Tags für spezifische URLs mit benutzerdefinierten Titeln, Beschreibungen und Bildern. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Shares auf Facebook sehen immer noch schlecht aus, selbst nach der Installation des Moduls. Was ist falsch?**
A:

1. **Modulaktivierung prüfen:** Stellen Sie sicher, dass „Open Graph Tags aktivieren“ in der Modulkonfiguration auf JA eingestellt ist.
2. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Dies ist entscheidend, damit Änderungen wirksam werden.
3. **Facebook Sharing Debugger verwenden:** Das ist Ihr bester Freund! Gehen Sie zu [developers.facebook.com/tools/debug/](https://developers.facebook.com/tools/debug/), fügen Sie die URL ein, die Sie teilen möchten, und klicken Sie auf „Debuggen“. Es zeigt Ihnen genau, welche Tags Facebook sieht und ob es Fehler gibt. Möglicherweise müssen Sie auf „Erneut scrapen“ klicken, um Facebook zu zwingen, Ihre Seite nach Änderungen erneut zu lesen.
4. **Auf Konflikte prüfen:** Ein anderes Modul oder Ihr Theme könnte widersprüchliche Open Graph Tags hinzufügen. Der Debugger hebt oft doppelte Tags hervor.

**F: Das Bild für meine Produkt-Shares ist falsch oder fehlt.**
A:

1. **Produktbild:** Stellen Sie sicher, dass Ihrem Produkt in den Produkteinstellungen ein Hauptbild zugewiesen ist.
2. **Bildgröße:** Obwohl Facebook die Größe ändern kann, werden sehr kleine oder ungewöhnliche Seitenverhältnisbilder möglicherweise ignoriert. Streben Sie mindestens 600x315 Pixel an, idealerweise 1200x628 für eine optimale Anzeige.
3. **Cache:** Leeren Sie den PrestaShop-Cache und verwenden Sie den Facebook Sharing Debugger, um „Erneut scrapen“ auszuführen.

**F: Wie erhalte ich eine Facebook App ID oder Admin ID?**
A:

1. **Facebook App ID:** Gehen Sie zu [developers.facebook.com](https://developers.facebook.com/), melden Sie sich an und erstellen Sie eine neue App. Befolgen Sie die Schritte, um Ihre App ID zu erhalten. Es ist eine numerische Zeichenfolge.
2. **Facebook Admin ID:** Dies ist Ihre persönliche Facebook-Benutzer-ID. Sie finden sie, indem Sie zu Ihrem Facebook-Profil gehen, auf Ihr Profilbild klicken und die URL in Ihrem Browser überprüfen (z. B. `facebook.com/profile.php?id=IHRE_BENUTZER_ID`).

**F: Funktioniert dieses Modul mit benutzerdefinierten Themes?**
A: Ja, das Modul fügt Tags direkt in den `<head>`-Bereich Ihres HTML ein, was Standardpraxis ist und mit jedem gut kodierten PrestaShop-Theme funktionieren sollte. Wenn Sie Probleme haben, handelt es sich normalerweise um ein Caching-Problem oder einen Konflikt mit einem anderen Modul.

**F: Meine benutzerdefinierte Seite (z. B. ein Blog-Beitrag) zeigt nicht die richtige Vorschau an.**
A: Verwenden Sie den Bereich **Erweiterte Einstellungen > Open Graph Tags** im Back Office. Fügen Sie einen neuen Eintrag für die genaue URL Ihrer benutzerdefinierten Seite hinzu und geben Sie manuell den gewünschten Titel, die Beschreibung und das Bild an. Denken Sie daran, den Cache zu leeren und anschließend den Facebook Sharing Debugger zu verwenden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Facebook Open Graph Tags“ ist so konzipiert, dass es sich nahtlos in die Kernfunktionalität von PrestaShop integriert, hauptsächlich durch die Nutzung von Hooks, um Open Graph Meta-Tags in den HTML `<head>`-Bereich verschiedener Front-Office-Seiten einzufügen. Es folgt einer Standard-PrestaShop-Modulstruktur, die eine Hauptmodulklasse, einen Admin-Controller für die Verwaltung benutzerdefinierter Tags und Smarty-Templates für das Rendering verwendet. Das Modul führt keine komplexen Datenbankschemata oder benutzerdefinierten Objektmodelle für seine primäre Funktion ein, verwendet aber `Configuration` für seine Haupteinstellungen und möglicherweise eine benutzerdefinierte Tabelle für `og_tags`, die vom `AdminOpenGraphController` verwaltet wird.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul enthält keine dedizierten Front-Office-Controller. Die gesamte Front-Office-Logik für die Tag-Generierung wird direkt in der Hauptmodulklasse (`index.php`) über Hook-Listener behandelt.
- **Back-Office-Admin-Controller**:

  - `opengraph/controllers/admin/AdminOpenGraphController.php`
    - **Klassenname & Elternklasse**: `AdminOpenGraphController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität**: Dieser Controller verwaltet eine benutzerdefinierte Entität, wahrscheinlich `og_tags`, die benutzerdefinierte Open Graph-Konfigurationen für bestimmte URLs speichert. Er erstellt einen neuen Menüeintrag unter „Erweiterte Einstellungen“ (oder ähnlich) im Back Office.
    - **Verantwortlichkeit**: Bietet eine Standard-PrestaShop-CRUD-Schnittstelle (Create, Read, Update, Delete) zur Verwaltung benutzerdefinierter Open Graph Tag-Sets. Er behandelt die Anzeige einer Liste benutzerdefinierter Tags (mithilfe von `renderList()`) und das Formular zum Hinzufügen/Bearbeiten dieser (mithilfe von `renderForm()`). Er verarbeitet Formularübermittlungen und interagiert mit der Datenbank, um `og_tags`-Daten zu speichern und abzurufen.
  - `opengraph/controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Dies ist typischerweise eine leere `index.php`-Datei in einem Controller-Verzeichnis, die als Sicherheitsmaßnahme dient, um direkte Verzeichnisauflistungen zu verhindern. Sie enthält keine funktionale Klasse oder Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Die primäre Logik zur Generierung von Open Graph-Tags ist wahrscheinlich in der Hauptmoduldatei (`opengraph/index.php`) enthalten, und der `AdminOpenGraphController` würde die Interaktionen mit einer benutzerdefinierten Datenbanktabelle direkt oder über ein einfaches `ObjectModel` handhaben, falls eines intern definiert wäre.

Wenn eine benutzerdefinierte Tabelle `og_tags` vom `AdminOpenGraphController` verwaltet wird, ist es sehr wahrscheinlich, dass der `AdminOpenGraphController` selbst die Eigenschaften `$this->table` und `$this->className` definiert und möglicherweise eine einfache `ObjectModel`-Definition für `og_tags` innerhalb der Hauptdatei des Moduls oder des Controllers selbst deklariert ist, auch wenn nicht in einer separaten `classes/`-Datei.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist keine benutzerdefinierten JavaScript-Dateien aus. Jegliches dynamisches Verhalten oder AJAX-Interaktionen würden entweder von PrestaShops Kern-JS gehandhabt oder sind in diesem Modul nicht vorhanden.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist keine benutzerdefinierten CSS-Dateien aus. Das Modul verlässt sich auf PrestaShops Standard-Back-Office-Styling für seine Konfigurationsformulare, und jede Front-Office-Ausgabe besteht ausschließlich aus Meta-Tags, nicht aus visuellen Elementen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `opengraph/views/templates/front/hook/header.tpl`:
    - **Hook**: Wahrscheinlich `displayHeader` oder `actionFrontControllerSetMedia`.
    - **Zweck**: Dies ist das primäre Template, das für das Rendern der eigentlichen Open Graph `<meta>`-Tags im `<head>`-Bereich der Front-Office-Seiten verantwortlich ist. Es empfängt Variablen (z. B. `og_title`, `og_description`, `og_image`, `og_url`, `og_type`, `og_app_id`, `og_admin_id`) von der `hookDisplayHeader`-Methode (oder ähnlichem) des Moduls und gibt die entsprechenden HTML-Meta-Tags aus.
  - `opengraph/views/templates/hook/form.tpl`:
    - **Hook**: Dieses Template wird wahrscheinlich intern vom `AdminOpenGraphController` zum Rendern der Formularfelder beim Hinzufügen oder Bearbeiten eines benutzerdefinierten Open Graph Tag-Eintrags verwendet. Es ist kein Front-Office-Hook-Template.
    - **Zweck**: Definiert die Struktur und Eingabefelder für das benutzerdefinierte Open Graph Tag-Konfigurationsformular im Back Office.
  - `opengraph/views/templates/hook/script.tpl`:
    - **Hook**: Könnte `displayHeader` oder `actionFrontControllerSetMedia` sein.
    - **Zweck**: Dieses Template könnte verwendet werden, um Inline-JavaScript im Zusammenhang mit Open Graph auszugeben, wie z. B. die Initialisierung des Facebook SDK oder spezifisches Event-Tracking, obwohl das Dossier keine JS-Dateien angibt, könnte es für ein sehr minimales Skript oder einen Platzhalter sein.
- **Admin-Templates (`views/templates/admin/`)**: Nicht explizit aufgeführt, aber `form.tpl` und möglicherweise eine `list.tpl` würden vom `AdminOpenGraphController` für seine Ansichten verwendet.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `opengraph/views/templates/front/hook/header.tpl` ist das einzige identifizierte Front-Office-Template, speziell für die Hook-Injektion.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_configuration`: Speichert die Hauptmodul-Einstellungen (z. B. `PS_OG_ENABLED`, `PS_OG_APP_ID`, `PS_OG_ADMIN_ID`, `PS_OG_HOME_IMAGE`, `PS_OG_HOME_TITLE`, `PS_OG_HOME_DESCRIPTION`).
  - `ps_og_tags` (oder ähnlich, verwaltet vom `AdminOpenGraphController`): Eine benutzerdefinierte Tabelle zum Speichern benutzerdefinierter Open Graph Tag-Überschreibungen für bestimmte URLs.
    - Wahrscheinliche Felder: `id_og_tag`, `url`, `title`, `description`, `image`, `date_add`, `date_upd`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert Inhalte innerhalb des `<head>`-Bereichs aller Front-Office-Seiten. | Primärer Hook zum Einfügen von Open Graph Meta-Tags (`og:title`, `og:description`, `og:image`, `og:url`, `og:type` usw.) in das HTML. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, nachdem der Front-Controller seine Medien (CSS/JS) gesetzt hat. | Könnte als alternativer oder zusätzlicher Hook zum Einfügen von Meta-Tags oder verwandten Skripten verwendet werden, insbesondere in PrestaShop 1.7+. |
| `displayBackOfficeHeader` | Rendert Inhalte innerhalb des `<head>`-Bereichs von Back-Office-Seiten. | Wird verwendet, um notwendige CSS oder JS für die Konfigurationsseiten des Moduls im Back Office einzubinden. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, nachdem ein Admin-Controller seine Medien gesetzt hat. | Ähnlich wie `displayBackOfficeHeader`, aber spezifischer für Admin-Controller, zum Laden von Assets für `AdminOpenGraphController`. |
| `moduleRoutes` (PrestaShop 1.7+) | Ermöglicht Modulen das Definieren benutzerdefinierter Routen. | Nicht explizit für die Kernfunktion dieses Moduls verwendet, könnte aber für zukünftige Erweiterungen oder spezifische URL-Behandlung vorhanden sein. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und den Zugriff auf die neuesten Versionen des Moduls „Facebook Open Graph Tags“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
