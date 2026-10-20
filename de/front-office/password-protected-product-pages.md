---
title: "Passwortgeschützte Produktseiten – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Passwortgeschützte Produktseiten“ von MyPresta.eu."
sidebar:
  label: "Passwortgeschützte Produktseiten"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Password protected product pages auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/password-protected-product-pages.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/password-protected-product-pages/)
>
> ---


# Passwortgeschützte Produktseiten

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Dies ist der Hauptkonfigurationsbildschirm für das Modul, der durch Klicken auf „Konfigurieren“ nach der Installation oder über den Modul-Manager aufgerufen wird.

- **Was diese Einstellung bewirkt:** Dieser Bildschirm enthält typischerweise allgemeine Einstellungen für das Modul, obwohl für „Passwortgeschützte Produktseiten“ die primäre Verwaltung von Passwörtern für bestimmte Produkte in einem dedizierten Admin-Bildschirm erfolgt (siehe 4.2). Dieser Bildschirm könnte Optionen für das Erscheinungsbild der Passworteingabeseite oder das allgemeine Modulverhalten bieten.
- **Auswirkung der Änderung dieser Einstellung:** Jegliche Änderungen hier würden sich auf das globale Verhalten des Passwortschutzmechanismus oder das Standarderscheinungsbild des Passworteingabeformulars auswirken.
- **Empfohlener Wert:** Standardwerte sind in der Regel ein guter Ausgangspunkt.
- **Händlerszenario / Beispiel:** Wenn es eine Option gibt, die auf der Passwortseite angezeigte Nachricht anzupassen, könnten Sie diese von „Passwort eingeben“ in „Bitte geben Sie Ihren VIP-Zugangscode ein“ ändern.

### 2.2 Dedizierter Admin-Bildschirm: Produktpasswörter (Back Office > Katalog > Produktpasswörter)
Dies ist der wichtigste Bildschirm zur Verwaltung, welche Produkte passwortgeschützt sind und welche Passwörter dafür verwendet werden. Sie finden diesen neuen Menüpunkt unter **Katalog** in Ihrem PrestaShop Back Office.

- **Bildschirmname & Menüpfad:** **Katalog > Produktpasswörter**
- **Verfügbare Aktionen & Einstellungen:**
    -   **Listentabelle:** Dieser Bildschirm zeigt eine Liste aller Produkte an, denen derzeit ein Passwort zugewiesen ist. Sie sehen typischerweise Spalten wie:
        -   **Produktname:** Der Name des geschützten Produkts.
        -   **Produkt-ID:** Die eindeutige Kennung des Produkts.
        -   **Passwort:** Das Passwort, das für den Zugriff auf die Produktseite erforderlich ist.
        -   **Aktionen:** Buttons zum „Bearbeiten“ oder „Löschen“ des Passworts für ein bestimmtes Produkt.
    -   **Neues Passwort hinzufügen:** Es gibt einen Button (z.B. „Neues Produktpasswort hinzufügen“ oder ein Plus-Symbol), um einen neuen Passwortschutzeintrag hinzuzufügen. Wenn Sie darauf klicken, wird Ihnen typischerweise ein Formular präsentiert:
        -   **Produktauswahl:** Ein Feld zum Suchen und Auswählen des Produkts, das Sie schützen möchten. Dies könnte ein Autocomplete-Feld sein, in das Sie den Produktnamen eingeben.
        -   **Passwortfeld:** Ein Eingabefeld, in dem Sie das Passwort für dieses spezifische Produkt definieren.
    -   **Passwort bearbeiten:** Durch Klicken auf „Bearbeiten“ neben einem bestehenden Eintrag können Sie das Passwort für dieses Produkt ändern oder möglicherweise das zugehörige Produkt ändern.
    -   **Passwort löschen:** Durch Klicken auf „Löschen“ wird der Passwortschutz für dieses Produkt entfernt, wodurch es wieder öffentlich zugänglich wird.
- **Auswirkung von Änderungen:**
    -   **Hinzufügen eines Passworts:** Die ausgewählte Produktseite wird im Front Office sofort passwortgeschützt.
    -   **Ändern eines Passworts:** Kunden müssen das neue Passwort verwenden, um auf die Produktseite zuzugreifen.
    -   **Löschen eines Passworts:** Die Produktseite wird wieder öffentlich zugänglich, ohne dass ein Passwort erforderlich ist.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Um ein neues Produkt zu schützen: Navigieren Sie zu **Katalog > Produktpasswörter**, klicken Sie auf „Neues Produktpasswort hinzufügen“, wählen Sie Ihr Produkt aus und legen Sie ein starkes, eindeutiges Passwort fest.
    2.  Um ein Passwort zu aktualisieren: Suchen Sie das Produkt in der Liste, klicken Sie auf „Bearbeiten“ und geben Sie das neue Passwort ein.
    3.  Um den Schutz zu entfernen: Suchen Sie das Produkt in der Liste und klicken Sie auf „Löschen“.
    4.  Überprüfen Sie regelmäßig Ihre geschützten Produkte, um sicherzustellen, dass die Passwörter weiterhin relevant und sicher sind.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfigurationsseite | (Allgemeine Einstellungen, falls vorhanden) | (Modulstandard) | Globales Verhalten oder Erscheinungsbild der Passworteingabeseite. |
| Katalog > Produktpasswörter | Neues Produktpasswort hinzufügen | N/A | Wählen Sie ein Produkt aus und weisen Sie ein Passwort zu, um den Zugriff auf dessen Seite zu beschränken. |
| Katalog > Produktpasswörter | Produktpasswort bearbeiten | N/A | Ändern Sie das Passwort für ein bereits geschütztes Produkt. |
| Katalog > Produktpasswörter | Produktpasswort löschen | N/A | Entfernen Sie den Passwortschutz, wodurch die Produktseite wieder öffentlich wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe ein Passwort festgelegt, aber die Produktseite ist immer noch öffentlich. Was ist falsch?**
A1:
*   **Passworteingabe überprüfen:** Überprüfen Sie unter **Katalog > Produktpasswörter** nochmals, ob das Produkt aufgeführt und das Passwort korrekt gesetzt ist.
*   **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“, falls verfügbar). Dies stellt sicher, dass Ihr Shop die neueste Konfiguration lädt.
*   **Modulstatus:** Stellen Sie sicher, dass das Modul „Passwortgeschützte Produktseiten“ unter **Module > Modul-Manager** aktiviert ist.
*   **Produktstatus:** Stellen Sie sicher, dass das Produkt selbst aktiviert und in Ihrem Katalog sichtbar ist.

**F2: Kann ich verschiedene Passwörter für verschiedene Produkte haben?**
A2: Ja, absolut! Das Modul ist dafür ausgelegt. Sie können jedem einzelnen Produkt, das Sie schützen möchten, über den Bildschirm **Katalog > Produktpasswörter** ein eindeutiges Passwort zuweisen.

**F3: Was passiert, wenn ein Kunde versucht, direkt über die URL auf eine geschützte Produktseite zuzugreifen, ohne das Passwort zu kennen?**
A3: Er wird auf die Passworteingabeseite weitergeleitet. Er kann den Produktinhalt erst sehen, wenn er das richtige Passwort eingegeben hat.

**F4: Wie übersetze ich den Text auf der Passworteingabeseite (z.B. „Passwort eingeben“)?**
A4: Sie können Modultexte normalerweise über die PrestaShop-Übersetzungsoberfläche übersetzen. Gehen Sie zu **International > Übersetzungen**, wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann das Modul „Passwortgeschützte Produktseiten“. Dort sollten Sie die bearbeitbaren Textzeichenfolgen finden.

**F5: Funktioniert dieses Modul mit meinem benutzerdefinierten Theme?**
A5: Das Modul ist so konzipiert, dass es sich nahtlos in Standard-PrestaShop-Themes integriert. Stark angepasste Themes erfordern jedoch möglicherweise geringfügige CSS-Anpassungen, um sicherzustellen, dass das Passworteingabeformular perfekt aussieht. Wenn Sie Styling-Probleme haben, wenden Sie sich an Ihren Webmaster oder Theme-Entwickler.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht
Das Modul „Passwortgeschützte Produktseiten“ arbeitet hauptsächlich, indem es den Standard-`ProductController` überschreibt, um Anfragen für geschützte Produkte abzufangen. Es verwendet einen dedizierten Admin-Controller, um Produkt-Passwort-Zuordnungen zu verwalten, die in der Datenbank gespeichert sind. Die Front-Office-Logik prüft auf ein gültiges Session-Cookie, das das Passwort für ein bestimmtes Produkt enthält, bevor die eigentliche Produktseite gerendert wird.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    *   `prodpswd/controllers/front/ProductPasswd.php`
        *   **Klassenname & Elternklasse:** `ProductPasswdModuleFrontController` erweitert `ModuleFrontController`.
        *   **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für das Rendern des Passworteingabeformulars verantwortlich, wenn auf ein geschütztes Produkt zugegriffen wird. Er verarbeitet die POST-Anfrage, wenn ein Benutzer ein Passwort sendet, validiert es anhand des gespeicherten Passworts für das Produkt und setzt bei erfolgreicher Authentifizierung eine Session oder ein Cookie, um den Zugriff zu gewähren. Er könnte auch die Weiterleitung zur eigentlichen Produktseite handhaben.
    *   `prodpswd/override/controllers/front/ProductController.php`
        *   **Klassenname & Elternklasse:** `ProductController` (überschrieben).
        *   **Verantwortlichkeit:** Dies ist eine entscheidende Überschreibung. Sie fängt die Methode `init()` oder `postProcess()` des Kern-`ProductController` ab. Bevor der Standardinhalt der Produktseite geladen wird, prüft diese Überschreibung, ob das aktuelle Produkt passwortgeschützt ist und ob der Benutzer das korrekte Passwort bereits angegeben hat (z.B. über ein Session-Cookie). Wenn das Produkt geschützt ist und kein gültiges Passwort gefunden wird, leitet es den Benutzer zum `ProductPasswdModuleFrontController` weiter (oder rendert direkt dessen Template), um zur Passworteingabe aufzufordern.

-   **Back-Office-Admin-Controller**:
    *   `prodpswd/controllers/admin/AdminProdPasswordController.php`
        *   **Tab-Name und verwaltete Entität:** Zugänglich über **Katalog > Produktpasswörter**. Verwaltet `prodpassword`-Entitäten (Produkt-ID und zugehöriges Passwort).
        *   **Verantwortlichkeit:** Dies ist ein Standard-`AdminController`, der für die CRUD-Operationen (Create, Read, Update, Delete) für Produkt-Passwort-Zuordnungen verantwortlich ist. Er zeigt die Liste der geschützten Produkte an, ermöglicht Administratoren das Hinzufügen neuer Produkt-Passwort-Einträge, das Bearbeiten bestehender Passwörter und deren Löschen. Er verwendet wahrscheinlich `HelperList` für die Rasteransicht und `HelperForm` für Hinzufügen-/Bearbeiten-Formulare.
    *   `prodpswd/controllers/admin/index.php`
        *   **Verantwortlichkeit:** Diese Datei ist typischerweise eine leere `index.php`-Datei, die in Unterverzeichnissen von PrestaShop-Modulen platziert wird, um die Verzeichnisauflistung zu verhindern und die Sicherheit zu erhöhen. Sie enthält keine funktionale Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)
Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Die `prodpassword`-Entität wird wahrscheinlich direkt vom `AdminProdPasswordController` unter Verwendung einer einfachen `ObjectModel`-Definition innerhalb der Hauptdatei des Moduls oder des Controllers selbst verwaltet, oder sie interagiert direkt mit `Configuration` oder einer benutzerdefinierten Tabelle ohne ein dediziertes `ObjectModel`. Angesichts der Tatsache, dass der `AdminProdPasswordController` eine `prodpassword`-Tabelle verwaltet, ist es sehr wahrscheinlich, dass ein `ObjectModel` dafür definiert ist, auch wenn nicht in einem separaten `classes/`-Ordner.

### 4.4 JavaScript-Assets (`views/js/`)
Das Moduldossier weist keine benutzerdefinierten JavaScript-Dateien aus. Das Front-Office-Passwortformular und die Back-Office-Raster-/Formularansicht sollen sich auf Standard-PrestaShop-JS oder einfache HTML-Formularübermittlungen verlassen.

### 4.5 CSS-Stylesheets (`views/css/`)
Das Moduldossier weist keine benutzerdefinierten CSS-Dateien aus. Das Styling für die Passworteingabeseite im Front Office und die Admin-Formulare wird wahrscheinlich vom aktiven PrestaShop-Theme und den Back-Office-Stilen geerbt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    *   Es sind keine spezifischen Hook-Templates aufgeführt, was darauf hindeutet, dass das Modul hauptsächlich über Controller-Überschreibungen und dedizierte Front-Office-Templates arbeitet, anstatt Inhalte in Standard-Hooks einzufügen.
-   **Admin-Templates (`views/templates/admin/`)**:
    *   Es sind keine spezifischen Admin-Templates aufgeführt. Der `AdminProdPasswordController` verwendet wahrscheinlich Standard-PrestaShop `HelperList`- und `HelperForm`-Templates für seine Oberfläche.
-   **Front-Office-Templates (`views/templates/front/`)**:
    *   `prodpswd/views/templates/front/product.tpl`
        *   **Zweck:** Dieses Template ist wahrscheinlich das benutzerdefinierte Passworteingabeformular, das Kunden angezeigt wird, wenn sie versuchen, auf eine geschützte Produktseite zuzugreifen. Es enthält die HTML-Struktur für das Passworteingabefeld, den Absende-Button und alle begleitenden Nachrichten (z.B. „Passwort eingeben, um dieses Produkt anzuzeigen“).
    *   `prodpswd/lib/searchTool/views/scripts.tpl`
        *   **Zweck:** Dieses Template enthält wahrscheinlich JavaScript- oder Smarty-Logik, die sich auf ein Suchwerkzeug bezieht, das möglicherweise in der Admin-Konfiguration zur Auswahl von zu schützenden Produkten verwendet wird. Es könnte AJAX-Aufrufe oder dynamische Filterfunktionen für die Produktauswahl enthalten.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   `ps_prodpassword` (oder ähnlich): Diese benutzerdefinierte Tabelle soll die Produkt-ID (`id_product`) und das zugehörige Passwort (`password`) für jedes geschützte Produkt speichern. Sie wird während der `install()`-Methode des Moduls erstellt.
    *   Konfigurationseinträge in `ps_configuration`: Allgemeine Moduleinstellungen (falls vorhanden) würden hier gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `actionFrontControllerSetMedia` | Bevor die Medien (JS/CSS) eines Front-Controllers geladen werden. | Potenziell zum Laden von benutzerdefiniertem JS/CSS für das Passwortformular, obwohl im Dossier keine aufgeführt sind. |
| `displayHeader` | Im `<head>`-Bereich des Front Office. | Könnte für Meta-Tags oder bedingtes JS/CSS verwendet werden, aber nicht explizit für Inhalte. |
| `displayRightColumn` | In der rechten Spalte des Front Office. | Nicht direkt für die Kernfunktionalität des Moduls verwendet. |
| `displayLeftColumn` | In der linken Spalte des Front Office. | Nicht direkt für die Kernfunktionalität des Moduls verwendet. |
| `displayFooter` | Im Footer des Front Office. | Nicht direkt für die Kernfunktionalität des Moduls verwendet. |
| `actionProductControllerSetMedia` | Nachdem der `ProductController` seine Medien gesetzt hat. | Könnte verwendet werden, um spezifisches JS/CSS für die Produktseite einzufügen, aber unwahrscheinlich angesichts der Überschreibung. |
| `actionDispatcherBefore` | Bevor ein Front-Controller versendet wird. | Die `override/controllers/front/ProductController.php` wirkt effektiv in diesem Stadium für Produktseiten. |
| `actionDispatcherAfter` | Nachdem ein Front-Controller versendet wurde. | Weniger wahrscheinlich für die Kernfunktionalität dieses Moduls. |

Der primäre Mechanismus für dieses Modul ist die `ProductController`-Überschreibung, die als impliziter Hook fungiert und Anfragen abfängt, bevor Standard-Hooks überhaupt für den Produktseiteninhalt verarbeitet werden.

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Passwortgeschützte Produktseiten“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
