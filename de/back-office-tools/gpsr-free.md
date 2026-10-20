---
title: "GPSR Free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul GPSR Free von MyPresta.eu."
sidebar:
  label: "GPSR Free"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul GPSR Free auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/gpsr-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/gpsr-free/)
>
> ---


# GPSR Free

## 1. Anforderungen & Kompatibilität
-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsübersicht (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > GPSR Free)

Dies ist der Hauptkonfigurationsbildschirm für das Modul GPSR Free, der sofort nach der Installation oder durch Klicken auf "Konfigurieren" im Modul-Manager zugänglich ist.

-   **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob der GPSR-Informationsblock auf Ihren Produktseiten im Front Office angezeigt wird.
-   **Auswirkungen einer Änderung dieser Einstellung:**
    -   *Wenn aktiviert (Ja):* Der GPSR-Informationsblock, der Hersteller-, verantwortliche Person- und Warnhinweisdetails enthält, wird auf Produktseiten angezeigt, für die Sie die relevanten Informationen zugeordnet haben.
    -   *Wenn deaktiviert (Nein):* Der GPSR-Informationsblock wird auf allen Produktseiten ausgeblendet, unabhängig von der von Ihnen konfigurierten Zuordnung.
-   **Empfohlener Wert:** **Ja**. Um die GPSR einzuhalten und die Informationen anzuzeigen, sollte dies aktiviert sein.
-   **Händlerszenario / Beispiel:** Wenn Sie Ihre GPSR-Daten aktiv einrichten und diese für Kunden sichtbar machen möchten, aktivieren Sie diese Option. Wenn Sie sich noch im Prozess der Datenkonfiguration befinden oder den Block vorübergehend ausblenden möchten (z.B. während einer Website-Neugestaltung), können Sie ihn deaktivieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul GPSR Free fügt mehrere neue Menüpunkte unter einem Hauptbereich "GPSR Free" in Ihrem PrestaShop Back Office hinzu. Diese Bildschirme ermöglichen es Ihnen, die verschiedenen Informationen zu verwalten, die für die GPSR-Konformität erforderlich sind.

#### 2.2.1 GPSR Free Dashboard (Back Office > GPSR Free > Dashboard)
Dieser Bildschirm dient als Haupteinstiegspunkt für die dedizierte Administration des Moduls. Er bietet typischerweise eine Übersicht oder schnelle Links zu den anderen Verwaltungsbereichen.

-   **Verfügbare Aktionen & Einstellungen:** Diese Ansicht präsentiert normalerweise eine Dashboard-ähnliche Oberfläche, die möglicherweise Statistiken oder schnelle Links zur Verwaltung von Herstellern, Entitäten, Warnhinweisen und Produktzuordnungen anzeigt.
-   **Auswirkungen von Änderungen:** Dieser Bildschirm selbst hat keine direkten Einstellungen, die das Verhalten im Front Office ändern, aber er ist Ihr Navigationszentrum für die gesamte GPSR-Datenverwaltung.
-   **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:** Beginnen Sie hier, um einen Überblick zu erhalten, und navigieren Sie dann zu den spezifischen Abschnitten (Hersteller, Entitäten, Warnhinweise, Produktzuordnung), um Daten hinzuzufügen oder zu ändern.

#### 2.2.2 Hersteller (Back Office > GPSR Free > Hersteller)
Dieser Bildschirm ermöglicht es Ihnen, die Hersteller Ihrer Produkte zu definieren und zu verwalten.

-   **Verfügbare Aktionen & Einstellungen:**
    -   **Auflistungstabelle:** Zeigt alle von Ihnen hinzugefügten Hersteller an, mit Spalten für Name, Adresse und Aktionen wie "Bearbeiten" oder "Löschen".
    -   **Schaltfläche "Neuen Hersteller hinzufügen":** Klicken Sie hier, um ein Formular zum Erstellen eines neuen Herstellereintrags zu öffnen.
    -   **Formularfelder (zum Hinzufügen/Bearbeiten eines Herstellers):**
        -   **Name:** Der offizielle Name des Herstellers.
        -   **Adresse:** Die vollständige Postanschrift des Herstellers.
        -   **Ist EU-Hersteller?:** Ein Schalter, um anzugeben, ob dieser Hersteller in der Europäischen Union ansässig ist. Dies ist entscheidend für die Bestimmung, ob eine "Verantwortliche Person in der EU" zugewiesen werden muss.
-   **Auswirkungen von Änderungen:** Das Hinzufügen oder Bearbeiten von Herstellern hier erstellt oder aktualisiert die zentrale Liste der Hersteller, die Sie dann Ihren Produkten zuordnen können. Diese Informationen werden auf den Produktseiten angezeigt, wenn sie zugeordnet sind.
-   **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:** Stellen Sie vor der Produktzuordnung sicher, dass alle Ihre Produkthersteller hier mit genauen Details aufgeführt sind. Wenn eine neue Produktlinie von einem neuen Hersteller stammt, fügen Sie diese zuerst hier hinzu.

#### 2.2.3 Verantwortliche Personen in der EU (Back Office > GPSR Free > Verantwortliche Personen in der EU)
Dieser Bildschirm dient zur Verwaltung der "Verantwortlichen Personen in der EU" (im internen Modulnamen auch als "Entitäten" bezeichnet), die für Produkte benannt werden, die außerhalb der EU hergestellt werden.

-   **Verfügbare Aktionen & Einstellungen:**
    -   **Auflistungstabelle:** Zeigt alle definierten verantwortlichen Personen in der EU mit deren Namen, Adressen und Aktionen an.
    -   **Schaltfläche "Neue verantwortliche Person in der EU hinzufügen":** Öffnet ein Formular zum Hinzufügen einer neuen verantwortlichen Person.
    -   **Formularfelder (zum Hinzufügen/Bearbeiten einer verantwortlichen Person in der EU):**
        -   **Name:** Der Name der verantwortlichen Person oder Entität in der EU (z.B. Importeur, Bevollmächtigter).
        -   **Adresse:** Die vollständige Postanschrift der verantwortlichen Person in der EU innerhalb der EU.
-   **Auswirkungen von Änderungen:** Dies erstellt oder aktualisiert die Liste der verantwortlichen Personen in der EU, die mit Nicht-EU-Herstellern oder direkt mit Produkten verknüpft werden können. Diese Informationen werden auf den Produktseiten angezeigt, wenn zutreffend.
-   **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:** Wenn Sie Produkte von außerhalb der EU importieren, stellen Sie sicher, dass Sie die korrekten Details der verantwortlichen Person in der EU hier eingetragen haben.

#### 2.2.4 Warnhinweise (Back Office > GPSR Free > Warnhinweise)
Dieser Bildschirm ermöglicht es Ihnen, benutzerdefinierte Sicherheitshinweise oder Haftungsausschlüsse zu erstellen und zu verwalten.

-   **Verfügbare Aktionen & Einstellungen:**
    -   **Auflistungstabelle:** Zeigt alle erstellten Warnhinweise mit deren Text und Aktionen an.
    -   **Schaltfläche "Neuen Warnhinweis hinzufügen":** Öffnet ein Formular zum Erstellen eines neuen Warnhinweises.
    -   **Formularfelder (zum Hinzufügen/Bearbeiten eines Warnhinweises):**
        -   **Warnhinweis-Text:** Der eigentliche Text des Sicherheitshinweises oder der Anweisung. Dieses Feld ist normalerweise mehrsprachig, sodass Sie Übersetzungen für jede in Ihrem Shop aktivierte Sprache bereitstellen können (gesteuert durch `PS_LANG_DEFAULT`).
-   **Auswirkungen von Änderungen:** Das Hinzufügen oder Bearbeiten von Warnhinweisen hier erstellt oder aktualisiert den Pool von Warnhinweisen, die Sie Produkten zuordnen können. Die ausgewählten Warnhinweise werden auf der Produktseite angezeigt.
-   **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:** Erstellen Sie generische Warnhinweise, die für mehrere Produkte gelten (z.B. "Außerhalb der Reichweite von Kindern aufbewahren", "Anleitung vor Gebrauch lesen"). Sie können diese dann einfach für einzelne Produkte auswählen.

#### 2.2.5 Produktzuordnung (Back Office > GPSR Free > Produktzuordnung)
Dies ist der wichtigste Bildschirm, auf dem Sie Ihre Produkte mit den von Ihnen definierten Herstellern, verantwortlichen Personen in der EU und Warnhinweisen verknüpfen.

-   **Verfügbare Aktionen & Einstellungen:**
    -   **Auflistungstabelle:** Zeigt bestehende Produktzuordnungen an, typischerweise mit Produktname, zugeordnetem Hersteller, verantwortlicher Person in der EU und Warnhinweisen.
    -   **Schaltfläche "Neue Produktzuordnung hinzufügen":** Öffnet ein Formular zum Erstellen einer neuen Zuordnung.
    -   **Formularfelder (zum Hinzufügen/Bearbeiten einer Produktzuordnung):**
        -   **Produktsuche:** Ein Feld zum Suchen und Auswählen des spezifischen Produkts, das Sie zuordnen möchten.
        -   **Hersteller:** Eine Dropdown-Liste zur Auswahl eines der Hersteller, die Sie im Abschnitt "Hersteller" definiert haben.
        -   **Verantwortliche Person in der EU:** Eine Dropdown-Liste zur Auswahl einer der von Ihnen definierten verantwortlichen Personen in der EU. Dieses Feld ist möglicherweise nur obligatorisch oder erscheint, wenn der ausgewählte Hersteller *kein* EU-Hersteller ist.
        -   **Warnhinweise:** Ein Mehrfachauswahlfeld oder eine Checkliste, um einen oder mehrere Warnhinweise aus dem Abschnitt "Warnhinweise" auszuwählen, die diesem Produkt zugeordnet werden sollen.
-   **Auswirkungen von Änderungen:** Wenn Sie eine Produktzuordnung speichern, werden der ausgewählte Hersteller, die verantwortliche Person in der EU (falls zutreffend) und die Warnhinweise auf der Front-Office-Produktseite für dieses spezifische Produkt angezeigt, vorausgesetzt, die Einstellung "GPSR-Block aktivieren" ist aktiv.
-   **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:** Nachdem Sie Ihre Hersteller, verantwortlichen Personen in der EU und Warnhinweise eingerichtet haben, gehen Sie Ihren Produktkatalog durch und ordnen Sie jedes relevante Produkt hier zu. Hier kommen die GPSR-Informationen zur Anzeige zusammen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | GPSR-Block aktivieren | Ja | Steuert die Sichtbarkeit des GPSR-Informationsblocks auf Produktseiten. |
| Hersteller | Name | N/A | Offizieller Name des Produktherstellers. |
| Hersteller | Adresse | N/A | Vollständige Postanschrift des Herstellers. |
| Hersteller | Ist EU-Hersteller? | Ja | Zeigt an, ob der Hersteller in der EU ansässig ist, was die Notwendigkeit einer verantwortlichen Person in der EU beeinflusst. |
| Verantwortliche Personen in der EU | Name | N/A | Name der benannten verantwortlichen Person/Entität in der EU. |
| Verantwortliche Personen in der EU | Adresse | N/A | Vollständige Postanschrift der verantwortlichen Person in der EU innerhalb der EU. |
| Warnhinweise | Warnhinweis-Text | N/A | Der eigentliche Sicherheitshinweis oder Anweisungstext (mehrsprachig). |
| Produktzuordnung | Produkt | N/A | Wählt das Produkt aus, dem GPSR-Informationen zugeordnet werden sollen. |
| Produktzuordnung | Hersteller | N/A | Ordnet dem ausgewählten Produkt einen definierten Hersteller zu. |
| Produktzuordnung | Verantwortliche Person in der EU | N/A | Ordnet dem ausgewählten Produkt eine definierte verantwortliche Person in der EU zu (wenn der Hersteller nicht aus der EU stammt). |
| Produktzuordnung | Warnhinweise | N/A | Wählt einen oder mehrere definierte Warnhinweise aus, die für das Produkt angezeigt werden sollen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe alles konfiguriert, aber der GPSR-Block wird auf meinen Produktseiten nicht angezeigt.**
A:
1.  **"GPSR-Block aktivieren" prüfen:** Gehen Sie zu **Module > Modul-Manager > GPSR Free > Konfigurieren** und stellen Sie sicher, dass die Einstellung "GPSR-Block aktivieren" auf "Ja" gesetzt ist.
2.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf "Cache leeren" (oder "Smarty-Cache leeren" in älteren Versionen). Manchmal verhindert der PrestaShop-Cache, dass neue Inhalte sofort erscheinen.
3.  **Produktzuordnung:** Überprüfen Sie nochmals, ob das spezifische Produkt, das Sie anzeigen, unter **GPSR Free > Produktzuordnung** mit einem Hersteller und mindestens einem Warnhinweis/einer Entität zugeordnet wurde.
4.  **Theme-Kompatibilität:** Obwohl das Modul versucht, mit den meisten Themes kompatibel zu sein, können sehr stark angepasste Themes geringfügige Anpassungen erfordern. Wenn der Block nach Überprüfung der oben genannten Punkte vollständig fehlt, wenden Sie sich an den MyPresta.eu-Support.

**F: Der Warnhinweis-Text oder die Herstellerdetails werden nicht in der richtigen Sprache angezeigt.**
A:
1.  **Übersetzungen prüfen:** Stellen Sie beim Bearbeiten eines Warnhinweises oder Herstellers sicher, dass Sie Übersetzungen für alle aktiven Sprachen in Ihrem Shop bereitgestellt haben. Suchen Sie nach Sprach-Tabs neben den Eingabefeldern.
2.  **Standardsprache:** Das Modul verwendet die Standardsprache von PrestaShop (`PS_LANG_DEFAULT`), wenn eine spezifische Übersetzung fehlt. Stellen Sie sicher, dass Ihre Standardsprache unter **International > Lokalisierung** korrekt eingestellt ist.

**F: Wie entferne ich die mit dem Modul installierten Beispieldaten?**
A: Sie können zu jedem entsprechenden Verwaltungsbildschirm (**GPSR Free > Hersteller**, **GPSR Free > Verantwortliche Personen in der EU**, **GPSR Free > Warnhinweise**, **GPSR Free > Produktzuordnung**) gehen und die Aktion "Löschen" für jeden Beispieleintrag verwenden.

**F: Kann ich das Aussehen des GPSR-Blocks anpassen?**
A: Ja, das Modul enthält eine `front.css`-Datei. Für grundlegende Stiländerungen (Farben, Schriftarten, Abstände) können Sie diese Stile oft in der benutzerdefinierten CSS-Datei Ihres Themes überschreiben, ohne das Modul direkt zu ändern. Für fortgeschrittenere Layoutänderungen müssen Sie möglicherweise die Vorlage `product-footer.tpl` anpassen. (Siehe Abschnitt 7 für Entwicklerdetails).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul GPSR Free folgt dem MVC-Muster (Model-View-Controller) von PrestaShop. Es verwendet benutzerdefinierte Admin-Controller zur Verwaltung von GPSR-bezogenen Daten (Hersteller, Entitäten, Warnhinweise, Produktzuordnungen) und nutzt PrestaShops `ObjectModel` für die Datenpersistenz. Die Front-Office-Anzeige wird über eine Hook-Vorlage abgewickelt. Das Modul verwendet ein Repository-Muster (`GpsrFreeRepository`) für Datenbankinteraktionen, was zu saubererem Code und einer Trennung der Verantwortlichkeiten führt.

### 4.2 Controller (`controllers/`)

Das Modul verwendet hauptsächlich Back-Office-Admin-Controller für die Datenverwaltung. Es gibt keine dedizierten Front-Office-Controller, da die Front-Office-Anzeige direkt über Hooks erfolgt.

-   **Back-Office Admin Controller**:
    -   `controllers/admin/AdminGpsrFreeController.php`
        -   **Klassenname:** `AdminGpsrFreeController` (erweitert `ModuleAdminController`)
        -   **Tab-Name:** GPSR Free (Haupteintrag des Dashboards)
        -   **Verantwortlichkeit:** Dient als Haupteinstiegspunkt für die Administration des Moduls, zeigt wahrscheinlich ein Dashboard oder Links zu anderen spezifischen Verwaltungsbildschirmen an. Es verwaltet keine spezifische Entität, sondern orchestriert den Zugriff auf andere Controller.
    -   `controllers/admin/AdminGpsrFreeEntitiesController.php`
        -   **Klassenname:** `AdminGpsrFreeEntitiesController` (erweitert `ModuleAdminController`)
        -   **Tab-Name:** Verantwortliche Personen in der EU
        -   **Verwaltete Entität:** `GpsrFreeEntity` (entspricht Tabelle `ps_gpsrfree_entity`)
        -   **Verantwortlichkeit:** Verwaltet das Erstellen, Bearbeiten, Auflisten und Löschen von verantwortlichen Personen in der EU (Entitäten). Bietet eine Standard-PrestaShop-Listen- und Formularansicht für diese Daten.
    -   `controllers/admin/AdminGpsrFreeManufacturersController.php`
        -   **Klassenname:** `AdminGpsrFreeManufacturersController` (erweitert `ModuleAdminController`)
        -   **Tab-Name:** Hersteller
        -   **Verwaltete Entität:** `GpsrFreeManufacturer` (entspricht Tabelle `ps_gpsrfree_manufacturer`)
        -   **Verantwortlichkeit:** Verwaltet das Erstellen, Bearbeiten, Auflisten und Löschen von Produktherstellern. Enthält Logik für `is_eu_manufacturer`.
    -   `controllers/admin/AdminGpsrFreeMapController.php`
        -   **Klassenname:** `AdminGpsrFreeMapController` (erweitert `ModuleAdminController`)
        -   **Tab-Name:** Produktzuordnung
        -   **Verwaltete Entität:** `GpsrFreeProductMap` (entspricht Tabelle `ps_gpsrfree_product_map`)
        -   **Verantwortlichkeit:** Verwaltet die Zuordnung zwischen Produkten, Herstellern, verantwortlichen Personen in der EU und Warnhinweisen. Dieser Controller behandelt die komplexen Beziehungen zwischen den verschiedenen GPSR-Datentypen.
    -   `controllers/admin/AdminGpsrFreeWarningsController.php`
        -   **Klassenname:** `AdminGpsrFreeWarningsController` (erweitert `ModuleAdminController`)
        -   **Tab-Name:** Warnhinweise
        -   **Verwaltete Entität:** `GpsrFreeWarning` (entspricht Tabelle `ps_gpsrfree_warning`)
        -   **Verantwortlichkeit:** Verwaltet das Erstellen, Bearbeiten, Auflisten und Löschen von Sicherheitshinweisen. Unterstützt mehrsprachige Felder.
    -   `controllers/admin/GpsrFreeAdminController.php`
        -   **Klassenname:** `GpsrFreeAdminController` (erweitert `ModuleAdminController`)
        -   **Tab-Name:** (Wahrscheinlich ein Basis- oder abstrakter Controller für andere Admin-Controller oder ein älterer/redundanter Einstiegspunkt)
        -   **Verantwortlichkeit:** Angesichts seines generischen Namens könnte er als Basisklasse für andere Admin-Controller im Modul dienen, gemeinsame Methoden oder Eigenschaften bereitstellen, oder es könnte ein veralteter Einstiegspunkt sein.
    -   `controllers/admin/index.php`
        -   **Klassenname:** N/A
        -   **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsdatei, um direkte Verzeichnisauflistung zu verhindern.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `classes/GpsrFreeAdminUi.php`
    -   **Klassenname:** `GpsrFreeAdminUi`
    -   **Verantwortlichkeit:** Wahrscheinlich eine Hilfsklasse zum Generieren oder Verwalten von UI-Elementen im Back Office, wie z.B. Formularfeldern, Listenkonfigurationen oder allgemeinen Admin-Oberflächenkomponenten. Sie hilft, das Erscheinungsbild der Admin-Bildschirme des Moduls zu standardisieren.
-   `classes/GpsrFreeEntity.php`
    -   **Klassenname:** `GpsrFreeEntity` (erweitert `ObjectModel`)
    -   **Datenbanktabelle:** `ps_gpsrfree_entity`
    -   **`$definition`-Felder:** Definiert Felder wie `name`, `address`.
    -   **Wichtige öffentliche Methoden:** Standard-`ObjectModel`-Methoden für CRUD-Operationen. Repräsentiert eine verantwortliche Person in der EU.
-   `classes/GpsrFreeManufacturer.php`
    -   **Klassenname:** `GpsrFreeManufacturer` (erweitert `ObjectModel`)
    -   **Datenbanktabelle:** `ps_gpsrfree_manufacturer`
    -   **`$definition`-Felder:** Definiert Felder wie `name`, `address`, `is_eu_manufacturer`.
    -   **Wichtige öffentliche Methoden:** Standard-`ObjectModel`-Methoden für CRUD-Operationen. Repräsentiert einen Produkthersteller.
-   `classes/GpsrFreeProductMap.php`
    -   **Klassenname:** `GpsrFreeProductMap` (erweitert `ObjectModel`)
    -   **Datenbanktabelle:** `ps_gpsrfree_product_map`
    -   **`$definition`-Felder:** Definiert Felder wie `id_product`, `id_manufacturer`, `id_entity`, `id_warning`. Diese Tabelle speichert wahrscheinlich die Many-to-Many-Beziehungen oder direkte Zuordnungen.
    -   **Wichtige öffentliche Methoden:** Standard-`ObjectModel`-Methoden für CRUD-Operationen. Verwaltet die Verknüpfungen zwischen Produkten und GPSR-Daten.
-   `classes/GpsrFreeRepository.php`
    -   **Klassenname:** `GpsrFreeRepository`
    -   **Verantwortlichkeit:** Implementiert das Repository-Muster. Diese Klasse ist für alle direkten Datenbankinteraktionen verantwortlich und abstrahiert sie von Controllern und Modellen. Sie enthält Methoden zum Abrufen, Einfügen, Aktualisieren und Löschen von GPSR-bezogenen Daten, oft unter Verwendung der `Db`-Klasse von PrestaShop. Sie würde Methoden wie `getMappedProductData($id_product)` enthalten.
-   `classes/GpsrFreeWarning.php`
    -   **Klassenname:** `GpsrFreeWarning` (erweitert `ObjectModel`)
    -   **Datenbanktabelle:** `ps_gpsrfree_warning`
    -   **`$definition`-Felder:** Definiert Felder wie `text` (mehrsprachig).
    -   **Wichtige öffentliche Methoden:** Standard-`ObjectModel`-Methoden für CRUD-Operationen. Repräsentiert einen Sicherheitshinweis.
-   `classes/index.php`
    -   **Klassenname:** N/A
    -   **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsdatei, um direkte Verzeichnisauflistung zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)
Das bereitgestellte Inventar zeigt an, dass keine benutzerdefinierten JavaScript-Dateien im Modul enthalten sind. Dies deutet darauf hin, dass das Modul hauptsächlich auf die integrierten JavaScript-Funktionen von PrestaShop für seine Admin-Formulare und potenziell minimale Front-Office-Interaktionen angewiesen ist, oder dass jegliches dynamische Verhalten serverseitig gehandhabt wird.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `views/css/admin.css`
    -   **Geltungsbereich:** Styling von Back-Office-Admin-Formularen.
    -   **Wichtige UI-Komponenten und Container, die gestylt werden:** Bietet wahrscheinlich spezifisches Styling für die benutzerdefinierten Admin-Seiten des Moduls, wie z.B. Listentabellen, Formularelemente oder Dashboard-Widgets, um ein konsistentes Erscheinungsbild innerhalb des PrestaShop Back Office zu gewährleisten.
    -   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Alle benutzerdefinierten Klassen, die in den Admin-Vorlagen des Moduls verwendet werden (z.B. `.gpsrfree-admin-panel`, `.gpsrfree-table`).
-   `views/css/front.css`
    -   **Geltungsbereich:** Styling für Kunden im Front Office.
    -   **Wichtige UI-Komponenten und Container, die gestylt werden:** Stylt den GPSR-Informationsblock, der auf Produktseiten angezeigt wird. Dies würde das Styling für den Block-Container, Überschriften, Herstellerdetails, Details der verantwortlichen Person in der EU und Warnlisten umfassen.
    -   **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Klassen wie `.gpsrfree-block`, `.gpsrfree-manufacturer`, `.gpsrfree-entity`, `.gpsrfree-warnings` usw. Entwickler können diese Klassen in der `custom.css` oder `theme.css` ihres Themes ansprechen, um sie an das Branding des Shops anzupassen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

-   **Hook-Vorlagen (`views/templates/hook/`)**:
    -   `views/templates/hook/product-footer.tpl`
        -   **Hook:** `displayFooterProduct` (und potenziell `displayProductButtons` oder ähnliches, obwohl `displayFooterProduct` explizit aufgeführt ist).
        -   **Visuelle Blockausgabe:** Diese Vorlage ist für das Rendern des gesamten GPSR-Informationsblocks auf der Produktseite verantwortlich. Sie enthält die Logik zur Anzeige der Herstellerdetails, der Details der verantwortlichen Person in der EU (falls zutreffend) und einer Liste der zugehörigen Warnhinweise, basierend auf den Daten, die aus dem `GpsrFreeRepository` für das aktuelle Produkt abgerufen wurden.
-   **Admin-Vorlagen (`views/templates/admin/`)**:
    -   `views/templates/admin/configure.tpl`
        -   **Hook:** Gerendert durch die `getContent()`-Methode der Hauptmoduldatei `gpsrfree.php`.
        -   **Visuelle Blockausgabe:** Diese Vorlage rendert das Hauptmodul-Konfigurationsformular im Back Office, insbesondere den Schalter "GPSR-Block aktivieren". Sie kann auch Links oder Einführungstexte zur Navigation zu den dedizierten Admin-Controllern enthalten.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    -   `ps_gpsrfree_entity`: Speichert Informationen über verantwortliche Personen in der EU (ID, Name, Adresse).
    -   `ps_gpsrfree_manufacturer`: Speichert Informationen über Produkthersteller (ID, Name, Adresse, is_eu_manufacturer).
    -   `ps_gpsrfree_product_map`: Speichert die Zuordnungsbeziehungen zwischen Produkten, Herstellern, verantwortlichen Personen in der EU und Warnhinweisen (id_product, id_manufacturer, id_entity, id_warning). Diese Tabelle handhabt wahrscheinlich Many-to-Many-Beziehungen, indem sie mehrere Einträge für ein einzelnes Produkt speichert, wenn es mehrere Warnhinweise hat.
    -   `ps_gpsrfree_warning`: Speichert den Text von Sicherheitshinweisen (ID, Text - mehrsprachig).
    -   `ps_configuration`: Moduleinstellungen wie `GPSRFREE_ENABLED` werden hier gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Potenziell zum Laden von Front-Office-CSS (`front.css`) oder JavaScript (falls vorhanden) global verwendet. |
| `displayFooterProduct` | Am unteren Rand der Produktseite, typischerweise unter dem Hauptproduktinhalt. | Primärer Hook zum Rendern des GPSR-Informationsblocks (`product-footer.tpl`) auf der Produktseite. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back-Office-Seite. | Wird zum Laden von Back-Office-CSS (`admin.css`) oder JavaScript für die Admin-Bildschirme des Moduls verwendet. |
| `displayAdminProductsExtra` | (Implizit, oft zum Hinzufügen von Tabs/Abschnitten zur Produktbearbeitungsseite verwendet) | Obwohl nicht explizit als registriert aufgeführt, verwenden Module dies oder ähnliche Hooks oft, um sich in die Produktbearbeitungsseite zu integrieren, wenn die Zuordnung direkt dort erfolgte. Angesichts von `AdminGpsrFreeMapController` handelt es sich wahrscheinlich um einen separaten Bildschirm. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | (Nicht explizit als registriert aufgeführt, aber üblich für Module, die mit Bestellungen interagieren. Falls vorhanden, wäre es für die auftragsbezogene GPSR-Datenverarbeitung, was durch die Modulbeschreibung nicht angezeigt wird.) |

*Hinweis: Das Moduldossier listete `DisplayHeader`, `DisplayFooterProduct`, `displayHeader`, `DisplayBackOfficeHeader`, `displayFooterProduct`, `displayBackOfficeHeader` auf. Dies sind Duplikate aufgrund der Groß-/Kleinschreibung, beziehen sich aber funktional auf dieselben Hooks.*

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul GPSR Free, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
