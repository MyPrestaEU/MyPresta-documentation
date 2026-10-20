---
title: "Passwortgeschützte Kategorieseiten – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Passwortgeschützte Kategorieseiten“ von MyPresta.eu."
sidebar:
  label: "Passwortgeschützte Kategorieseiten – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Password protected category pages auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/password-protected-category-pages.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/password-protected-category-pages/)
>
> ---


# Passwortgeschützte Kategorieseiten

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls klicken Sie auf „Konfigurieren“, um auf die Haupteinstellungen zuzugreifen. Dieser Bildschirm bietet allgemeine Modulverwaltungsoptionen.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält typischerweise Standardeinstellungen für MyPresta.eu-Module, die sich auf Updates und Lizenzierung beziehen. Er stellt sicher, dass Ihr Modul aktuell und ordnungsgemäß lizenziert ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - *`mypresta_updates`*: Diese Einstellung steuert, ob das Modul automatisch nach Updates sucht. Wenn sie aktiviert ist, werden Sie über neue Versionen benachrichtigt.
  - *`update_` und `updatev_`*: Dies sind interne Einstellungen, die vom Modul zur Verwaltung von Update-Prüfungen und Versionsinformationen verwendet werden. Sie müssen in der Regel nicht direkt mit diesen interagieren.
- **Empfohlener Wert:** Lassen Sie `mypresta_updates` aktiviert, um wichtige Updates und Fehlerbehebungen zu erhalten.
- **Händlerszenario / Beispiel:** Wenn Sie sicherstellen möchten, dass Ihr Modul immer die neuesten Funktionen und Sicherheitspatches hat, lassen Sie die Update-Prüfung aktiviert. Wenn Sie einen stark angepassten Shop haben und Updates nach gründlichen Tests manuell steuern möchten, könnten Sie sie deaktivieren, dies wird jedoch für die meisten Händler im Allgemeinen nicht empfohlen.

### 2.2 Dedizierter Admin-Bildschirm: Kategorie-Passwörter (Back Office > Katalog > Kategorie-Passwörter)

Dies ist der zentrale Verwaltungsbildschirm zum Einrichten und Verwalten von Passwörtern für Ihre Kategorien.

- **Bildschirmname & Menüpfad:** Sie finden diesen Bildschirm, indem Sie im PrestaShop Back Office-Menü zu **Katalog > Kategorie-Passwörter** navigieren.
- **Verfügbare Aktionen & Einstellungen:**
  - **Kategorieliste:** Dieser Bildschirm zeigt eine Liste all Ihrer Kategorien an. Für jede Kategorie sehen Sie, ob sie derzeit passwortgeschützt ist und wie viele Passwörter ihr zugewiesen sind.
  - **Passwörter hinzufügen/bearbeiten:** Für jede Kategorie können Sie auf eine Schaltfläche „Bearbeiten“ oder „Passwörter verwalten“ (oder ein ähnliches Symbol) klicken, um eine dedizierte Oberfläche zu öffnen. Hier können Sie:
    - **Eine Kategorie auswählen:** Wählen Sie die spezifische Kategorie aus, die Sie schützen möchten.
    - **Neues Passwort hinzufügen:** Geben Sie ein neues Passwort für die ausgewählte Kategorie ein. Sie können mehrere Passwörter für eine einzelne Kategorie hinzufügen. Dies ist nützlich, wenn Sie verschiedenen Kundengruppen unterschiedliche Zugangscodes geben möchten (z. B. „VIP123“ für Premium-Kunden, „GROSSHANDEL456“ für B2B-Partner).
    - **Passwort löschen:** Bestehende Passwörter entfernen.
    - **Schutz aktivieren/deaktivieren:** Ein Schalter oder Kontrollkästchen kann verfügbar sein, um den Passwortschutz für eine Kategorie schnell zu aktivieren oder zu deaktivieren, ohne alle Passwörter zu löschen.
- **Auswirkung von Änderungen:**
  - **Hinzufügen eines Passworts:** Die ausgewählte Kategorie wird im Front Office sofort passwortgeschützt. Kunden müssen eines der zugewiesenen Passwörter eingeben, um die Produkte anzuzeigen.
  - **Löschen eines Passworts:** Dieses spezifische Passwort gewährt keinen Zugriff mehr. Wenn es das einzige Passwort für eine Kategorie war, könnte die Kategorie ungeschützt werden (abhängig von der genauen Logik des Moduls; es ist sicherer, den Schutz explizit zu deaktivieren, wenn Sie ihn öffnen möchten).
  - **Deaktivieren des Schutzes:** Die Kategorie wird wieder öffentlich zugänglich, und Kunden sehen ihre Produkte, ohne ein Passwort zu benötigen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Gehen Sie zu **Katalog > Kategorie-Passwörter**.
  2. Identifizieren Sie die Kategorie, die Sie schützen möchten.
  3. Klicken Sie auf das Symbol „Passwörter verwalten“ oder „Bearbeiten“ daneben.
  4. Fügen Sie im neuen Bildschirm ein oder mehrere Passwörter hinzu. Denken Sie daran, dass jedes hinzugefügte Passwort den Zugriff gewährt.
  5. Speichern Sie Ihre Änderungen.
  6. Um den Schutz zu entfernen, löschen Sie entweder alle Passwörter für diese Kategorie oder verwenden Sie einen „Aktivieren/Deaktivieren“-Schalter, falls verfügbar.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | `mypresta_updates` | Aktiviert | Steuert die automatische Update-Prüfung für das Modul. Für die neuesten Funktionen und Sicherheit aktiviert lassen. |
| Modulkonfigurationsseite | `update_`, `updatev_` | (Intern) | Interne Einstellungen für die Update-Verwaltung. Keine Händlerinteraktion erforderlich. |
| Kategorie-Passwörter (Katalog > Kategorie-Passwörter) | Kategorieliste | N/A | Übersicht aller Kategorien und ihres Passwortschutzstatus. |
| Kategorie-Passwörter (Katalog > Kategorie-Passwörter) | Passwörter hinzufügen/bearbeiten | N/A | Ermöglicht das Hinzufügen, Bearbeiten oder Löschen von Passwörtern für bestimmte Kategorien. Mehrere Passwörter pro Kategorie werden unterstützt. |
| Kategorie-Passwörter (Katalog > Kategorie-Passwörter) | Schutz aktivieren/deaktivieren | N/A | Schaltet den Passwortschutz für eine Kategorie ein oder aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe ein Passwort festgelegt, aber die Kategorie ist immer noch ohne sichtbar. Was ist falsch?**
A1:

- **Cache leeren:** Der häufigste Grund ist das Caching. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ und „Cache leeren“ für alle Caches).
- **Kategorienstatus überprüfen:** Stellen Sie sicher, dass die Kategorie selbst aktiv und in Ihrem Shop sichtbar ist.
- **Passworteingabe überprüfen:** Überprüfen Sie nochmals, ob Sie das/die Passwort(e) im Bereich **Katalog > Kategorie-Passwörter** korrekt eingegeben und gespeichert haben.
- **Modulposition:** Stellen Sie sicher, dass das Modul korrekt gehookt ist. Obwohl das Modul dies automatisch handhabt, können bei stark angepassten Themes manchmal Hooks überschrieben werden.

**F2: Kann ich mehrere Passwörter für eine Kategorie haben?**
A2: Ja! Dieses Modul unterstützt explizit eine unbegrenzte Anzahl von Passwörtern für eine einzelne Kategorie. Dies ist nützlich, um verschiedenen Gruppen unterschiedliche Zugangscodes zu geben (z. B. „VIP“-Passwort, „Großhandel“-Passwort).

**F3: Was passiert, wenn ein Kunde versucht, ein Produkt direkt über seine URL aus einer geschützten Kategorie aufzurufen?**
A3: Wenn ein Produkt zu einer passwortgeschützten Kategorie gehört, muss beim direkten Zugriff auf die Produktseite zuerst das Kategoriepasswort eingegeben werden. Das Modul stellt sicher, dass der Kategoriekontext respektiert wird, und verhindert den direkten Zugriff auf Produkte innerhalb einer gesicherten Kategorie ohne Authentifizierung.

**F4: Wie entferne ich den Passwortschutz von einer Kategorie?**
A4: Gehen Sie zu **Katalog > Kategorie-Passwörter**. Suchen Sie die Kategorie, die Sie entsperren möchten. Sie können entweder alle Passwörter löschen, die mit dieser Kategorie verknüpft sind, oder, falls ein expliziter „Aktivieren/Deaktivieren“-Schalter für den Kategorieschutz vorhanden ist, diesen verwenden. Sobald alle Passwörter entfernt oder der Schutz deaktiviert ist, wird die Kategorie wieder öffentlich zugänglich.

**F5: Das Passwortformular sieht in meinem benutzerdefinierten Theme nicht gut aus. Wie kann ich das beheben?**
A5: Das Modul verwendet Standard-PrestaShop-Templating und CSS. Wenn es nicht richtig aussieht, liegt es wahrscheinlich an einem CSS-Konflikt mit Ihrem benutzerdefinierten Theme.

- **Elemente untersuchen:** Verwenden Sie die Entwicklertools Ihres Browsers (F12), um die Elemente des Passwortformulars zu untersuchen. Suchen Sie nach widersprüchlichen CSS-Regeln aus Ihrem Theme.
- **Benutzerdefiniertes CSS:** Sie können benutzerdefiniertes CSS in die `custom.css`-Datei Ihres Themes (oder eine ähnliche) einfügen, um das Standard-Styling des Moduls zu überschreiben und es an Ihr Theme anzupassen.
- **Support kontaktieren:** Wenn Sie mit CSS nicht vertraut sind, wenden Sie sich an Ihren Theme-Entwickler oder den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Passwortgeschützte Kategorieseiten“ integriert sich in die MVC-Architektur von PrestaShop, indem es hauptsächlich den Kern-`CategoryController` überschreibt, um Anfragen an Kategorieseiten abzufangen. Es verwendet einen dedizierten Admin-Controller (`AdminCatPasswordController`) zur Verwaltung von Kategorie-Passwort-Zuordnungen, die in einer benutzerdefinierten Datenbanktabelle gespeichert werden. Die Anzeige im Front-Office erfolgt über ein benutzerdefiniertes Smarty-Template für das Passworteingabeformular.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `catpswd/override/controllers/front/listing/CategoryController.php`
    - **Klassenname:** `CategoryController` (überschreibt den Kern-PrestaShop `CategoryController`)
    - **Elternklasse:** `CategoryControllerCore`
    - **Verantwortlichkeit:** Diese Überschreibung ist der Kern der Front-Office-Funktionalität des Moduls. Sie fängt Anfragen an Kategorieseiten ab. Bevor der eigentliche Kategorieinhalt angezeigt wird, prüft sie, ob die Kategorie passwortgeschützt ist. Wenn dies der Fall ist und der Benutzer das richtige Passwort noch nicht eingegeben hat (oder die Sitzung abgelaufen ist), rendert sie das Passworteingabeformular (`category.tpl`) anstelle der Standard-Kategorieseite. Sie verarbeitet die Übermittlung des Passwortformulars, validiert das eingegebene Passwort und setzt eine Sitzungsvariable bei erfolgreicher Authentifizierung.
  - `catpswd/override/controllers/front/listing/index.php`
    - **Verantwortlichkeit:** Dies ist eine Standard-PrestaShop-`index.php`-Datei in einem Override-Verzeichnis, die typischerweise verwendet wird, um direkte Verzeichnisauflistungen zu verhindern und das ordnungsgemäße Laden des Moduls sicherzustellen. Sie enthält selbst keine aktive Controller-Logik.
- **Back-Office-Admin-Controller**:

  - `catpswd/controllers/admin/AdminCatPasswordController.php`
    - **Tab-Name:** „Kategorie-Passwörter“ (unter dem Katalog-Menü)
    - **Verwaltete Entität:** `CatPassword` (obwohl kein `ObjectModel` explizit aufgeführt ist, verwaltet dieser Controller die Kategorie-Passwort-Beziehungen und interagiert wahrscheinlich direkt mit der Datenbank oder einer Hilfsklasse).
    - **Verantwortlichkeit:** Dieser Controller stellt die Schnittstelle im PrestaShop Back Office für Administratoren bereit, um den Passwortschutz für Kategorien zu verwalten. Er listet Kategorien auf, ermöglicht das Hinzufügen mehrerer Passwörter zu einer Kategorie und deren Entfernung. Er verarbeitet die CRUD-Operationen für die Kategorie-Passwort-Daten.
  - `catpswd/controllers/admin/index.php`
    - **Verantwortlichkeit:** Ähnlich wie die Front-Office-`index.php` verhindert diese Datei die direkte Verzeichnisauflistung für das Admin-Controller-Verzeichnis.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine expliziten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass der `AdminCatPasswordController` die Datenbankinteraktionen wahrscheinlich direkt handhabt oder eine einfache Hilfsfunktion innerhalb der Hauptmoduldatei (`catpswd.php`) für die Datenverwaltung verwendet, anstatt ein dediziertes `ObjectModel`.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist keine spezifischen JavaScript-Dateien aus. Die Passwortübermittlung und -validierung werden wahrscheinlich über die Standard-HTML-Formularübermittlung und serverseitige Verarbeitung innerhalb der `CategoryController`-Überschreibung gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist keine spezifischen CSS-Dateien aus. Das Styling für das Passworteingabeformular ist wahrscheinlich minimal und basiert auf dem Basis-Styling des Standard-PrestaShop-Themes. Entwickler, die das Erscheinungsbild anpassen möchten, sollten die Formularelemente innerhalb des `category.tpl`-Templates mit dem benutzerdefinierten CSS ihres Themes ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `catpswd/lib/searchTool/views/scripts.tpl`
    - **Hook:** Wahrscheinlich in `displayHeader` oder `actionAdminControllerSetMedia` verwendet (wenn es JS/CSS-Includes für ein Suchwerkzeug enthält).
    - **Ausgabe:** Dieses Template enthält wahrscheinlich JavaScript- oder CSS-Inklusionen, möglicherweise für ein Suchdienstprogramm, das in der Admin-Oberfläche des Moduls oder für Front-Office-Funktionalität verwendet wird.
- **Front-Office-Templates (`views/templates/front/`)**:
  - `catpswd/views/templates/front/category.tpl`
    - **Zweck:** Dies ist das Template, das vom überschriebenen `CategoryController` gerendert wird, wenn eine passwortgeschützte Kategorie ohne Authentifizierung aufgerufen wird. Es zeigt dem Kunden das Passworteingabeformular an. Es enthält typischerweise Felder für das Passwort, einen Absende-Button und Nachrichten für erfolgreiche oder fehlgeschlagene Versuche.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - `ps_catpassword`: Diese benutzerdefinierte Tabelle wird vom Modul während der Installation erstellt. Sie speichert die Zuordnungen zwischen Kategorie-IDs und ihren jeweiligen Passwörtern.
    - **Spalten (erwartet):** `id_catpassword` (Primärschlüssel), `id_category` (Fremdschlüssel zu `ps_category`), `password` (der gehashte oder Klartext-Passwort-String).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Potenziell verwendet, um globale CSS- oder JS-Assets einzubinden oder um Meta-Tags im Zusammenhang mit der Funktionalität des Moduls festzulegen. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird und seine Medien (JS/CSS) festgelegt werden. | Wird vom Modul verwendet, um seine spezifischen JavaScript- und CSS-Dateien in das Back Office für den `AdminCatPasswordController` oder andere Admin-Seiten einzufügen, auf denen Modul-Assets benötigt werden. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und professionellen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und sicherzustellen, dass Ihr Modul reibungslos funktioniert.
