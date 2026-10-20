---
title: "Back office Sticky Notes - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Back office Sticky Notes von MyPresta.eu."
sidebar:
  label: "Back office Sticky Notes - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Back office Sticky Notes auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/back-office-sticky-notes.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/back-office-sticky-notes/)
>
> ---


# Back office Sticky Notes

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und meist auf den meisten Hosting-Umgebungen vorinstalliert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite für das Modul „Back office Sticky Notes“. Hier verwalten Sie Ihre Haftnotizen.

Die Konfigurationsseite selbst hat nicht viele „Einstellungen“ im traditionellen Sinne (wie Ein-/Ausschalter). Stattdessen ist sie Ihre zentrale Anlaufstelle zum Erstellen, Bearbeiten und Verwalten all Ihrer Haftnotizen.

#### **Eine neue Haftnotiz hinzufügen**

Oben auf der Konfigurationsseite finden Sie normalerweise ein Formular oder einen Abschnitt zum Hinzufügen einer neuen Notiz.

- **Notizinhalt (Textbereich):**

  - **Was diese Einstellung bewirkt:** Hier geben Sie die eigentliche Nachricht oder Erinnerung für Ihre Haftnotiz ein.
  - **Auswirkung der Änderung dieser Einstellung:** Was Sie hier eingeben, wird auf der Haftnotiz in Ihrem Back Office angezeigt.
  - **Empfohlener Wert:** Seien Sie prägnant und klar. Verwenden Sie Aufzählungspunkte oder kurze Sätze für bessere Lesbarkeit.
  - **Händlerszenario / Beispiel:** „Erinnerung: Kunden-Nr. 1234 bezüglich des Bestellstatus kontaktieren.“ oder „Neue Produktbilder für ‚Sommerkollektion‘ bis Freitag fällig.“
- **Notizfarbe (Farbauswahl):**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der Hintergrundfarbe Ihrer Haftnotiz.
  - **Auswirkung der Änderung dieser Einstellung:** Die Haftnotiz erscheint mit der gewählten Farbe im Back Office. Verschiedene Farben können helfen, Notizen zu kategorisieren oder Dringlichkeit hervorzuheben.
  - **Empfohlener Wert:** Wählen Sie Farben, die auffallen, aber nicht zu ablenkend sind. Sie könnten Rot für dringende Notizen, Gelb für allgemeine Erinnerungen und Grün für erledigte Aufgaben verwenden.
  - **Händlerszenario / Beispiel:** Eine Notiz über einen kritischen Fehler auf Rot setzen und eine Notiz über eine neue Marketingidee auf Gelb.
- **Speichern / Notiz hinzufügen Schaltfläche:**

  - **Was diese Einstellung bewirkt:** Übermittelt den von Ihnen gewählten Inhalt und die Farbe, um eine neue Haftnotiz zu erstellen.
  - **Auswirkung der Änderung dieser Einstellung:** Eine neue Haftnotiz wird erstellt und erscheint auf Ihren Back-Office-Seiten. Sie wird auch im Abschnitt „Bestehende Notizen“ unten aufgeführt.
  - **Empfohlener Wert:** Klicken Sie darauf, nachdem Sie den Notizinhalt und die Farbe festgelegt haben.
  - **Händlerszenario / Beispiel:** Nachdem Sie Ihre Erinnerung eingegeben und eine Farbe ausgewählt haben, klicken Sie auf „Speichern“, um die Notiz zu aktivieren.

#### **Bestehende Haftnotizen verwalten**

Unter dem Abschnitt „Neue Notiz hinzufügen“ sehen Sie eine Liste oder Tabelle aller bereits erstellten Haftnotizen.

- **Notizliste (Tabelle/Anzeige):**

  - **Was diese Einstellung bewirkt:** Zeigt alle aktiven Haftnotizen, deren Inhalt und zugewiesene Farbe an.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist eine Anzeige Ihrer aktuellen Notizen. Sie können sie hier visuell überprüfen.
  - **Empfohlener Wert:** Überprüfen Sie diese Liste regelmäßig, um sicherzustellen, dass die Notizen noch relevant sind.
  - **Händlerszenario / Beispiel:** Scannen Sie schnell die Liste, um alle ausstehenden Aufgaben oder Erinnerungen zu sehen.
- **Bearbeiten-Schaltfläche (für jede Notiz):**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den Inhalt oder die Farbe einer bestehenden Haftnotiz zu ändern.
  - **Auswirkung der Änderung dieser Einstellung:** Durch Klicken darauf wird der Inhalt der Notiz normalerweise wieder in das Formular „Neue Notiz hinzufügen“ geladen (das sich möglicherweise in den Modus „Notiz bearbeiten“ ändert), sodass Sie Änderungen vornehmen können. Nach dem Speichern wird die Notiz in Ihrem Back Office aktualisiert.
  - **Empfohlener Wert:** Verwenden Sie dies, um Aufgabenstatus zu aktualisieren, weitere Details hinzuzufügen oder die Dringlichkeit zu ändern.
  - **Händlerszenario / Beispiel:** Eine Notiz besagt „Neue Produktbilder prüfen.“ Nach der Prüfung können Sie sie in „Neue Produktbilder genehmigt.“ ändern.
- **Löschen-Schaltfläche (für jede Notiz):**

  - **Was diese Einstellung bewirkt:** Entfernt eine Haftnotiz dauerhaft.
  - **Auswirkung der Änderung dieser Einstellung:** Die Notiz verschwindet aus Ihrem Back Office und wird nicht mehr in der Konfiguration aufgeführt. Diese Aktion ist normalerweise irreversibel.
  - **Empfohlener Wert:** Löschen Sie Notizen nur, wenn die Aufgabe abgeschlossen oder die Information nicht mehr relevant ist.
  - **Händlerszenario / Beispiel:** Sobald ein Bestellproblem behoben ist, löschen Sie die entsprechende Haftnotiz.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | **Notizinhalt (Textbereich)** | Klarer, prägnanter Text | Die eigentliche Nachricht, die auf der Haftnotiz angezeigt wird. |
| Modulkonfigurationsseite | **Notizfarbe (Farbauswahl)** | Vom Benutzer ausgewählt | Legt die Hintergrundfarbe der Notiz zur Kategorisierung/Dringlichkeit fest. |
| Modulkonfigurationsseite | **Speichern / Notiz hinzufügen Schaltfläche** | Klicken nach Festlegung von Inhalt/Farbe | Erstellt eine neue Haftnotiz, die im Back Office sichtbar ist. |
| Modulkonfigurationsseite | **Bearbeiten-Schaltfläche (pro Notiz)** | Klicken zum Ändern | Ermöglicht die Aktualisierung von Inhalt oder Farbe einer bestehenden Notiz. |
| Modulkonfigurationsseite | **Löschen-Schaltfläche (pro Notiz)** | Klicken zum Entfernen | Entfernt eine Haftnotiz dauerhaft aus dem Back Office. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Haftnotizen erscheinen nach dem Speichern nicht im Back Office.**
A1:

- **Cache leeren:** Der häufigste Grund für Anzeigeprobleme ist das Caching. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Performance**. Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
- **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** noch installiert und aktiviert ist.
- **Browser-Cache:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder Ihr Back Office in einem Inkognito-/privaten Browsing-Fenster zu öffnen, um browserbedingte Probleme auszuschließen.

**F2: Kann ich die Haftnotizen auf dem Bildschirm verschieben?**
A2: Ja, sobald eine Haftnotiz in Ihrem Back Office angezeigt wird, sollten Sie sie per Klick und Ziehen an jede beliebige Position auf der Seite verschieben können. Das Modul ist so konzipiert, dass es seine Position für Sie speichert.

**F3: Können verschiedene Administratoren die Haftnotizen des jeweils anderen sehen?**
A3: Ja, standardmäßig sind alle über dieses Modul erstellten Haftnotizen für alle Administratoren sichtbar, die Zugriff auf das Back Office haben. Dies ist eine Schlüsselfunktion für die Teamzusammenarbeit.

**F4: Die Farben meiner Haftnotizen sehen seltsam aus oder werden nicht korrekt angewendet.**
A4:

- **Farbauswahl prüfen:** Stellen Sie sicher, dass Sie das Farbauswahlwerkzeug auf der Konfigurationsseite des Moduls korrekt verwenden.
- **Konflikte mit benutzerdefiniertem Theme:** Wenn Sie ein stark angepasstes Back-Office-Theme verwenden, kann es zu CSS-Konflikten kommen. Versuchen Sie, vorübergehend zum Standard-PrestaShop-Back-Office-Theme zu wechseln, um zu sehen, ob das Problem weiterhin besteht. Wenn es sich löst, überschreibt das CSS Ihres Themes wahrscheinlich die Stile des Moduls.
- **Browser-Kompatibilität:** Stellen Sie sicher, dass Ihr Browser auf dem neuesten Stand ist.

**F5: Wie übersetze ich die Benutzeroberfläche des Moduls in eine andere Sprache?**
A5:

- Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann die Sprache, in die Sie übersetzen möchten.
- Suchen Sie „Back office Sticky Notes“ in der Liste und übersetzen Sie die verfügbaren Textzeichenfolgen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Back office Sticky Notes“ ist ein klassisches PrestaShop-Modul, das hauptsächlich für das Back Office entwickelt wurde. Es nutzt die Modularchitektur von PrestaShop und verwendet die `Module`-Klasse für Installation, Deinstallation und Konfiguration. Die Kernfunktionalität dreht sich um die Anzeige und Verwaltung von benutzerdefinierten „Haftnotizen“ innerhalb des Admin-Panels. Es stützt sich stark auf JavaScript für die Frontend-Interaktion (Ziehen, Positionieren) und AJAX für das Speichern von Notizdaten. Die Datenpersistenz wird über `ps_configuration` für Moduleinstellungen und wahrscheinlich benutzerdefinierte Datenbanktabellen oder `ps_configuration` für die Notizen selbst gehandhabt.

### 4.2 Controller (`controllers/`)

Dieses Modul scheint keine dedizierten Front-Office- oder Back-Office-Admin-Controller im traditionellen PrestaShop-MVC-Sinne zu verwenden (d.h. Dateien in `controllers/front/` oder `controllers/admin/`). Alle Konfigurations- und AJAX-Handhabung scheint direkt in der Hauptmoduldatei (`addstickynote.php`) über die Methode `getContent()` für die Konfiguration und potenziell `ajaxProcess`-Methoden oder direkte AJAX-Aufrufe für die dynamische Notizverwaltung zu erfolgen.

### 4.3 Kernklassen & Modelle (`classes/`)

Basierend auf dem bereitgestellten Inventar gibt es keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen innerhalb eines `classes/`-Verzeichnisses. Dies deutet darauf hin, dass Haftnotizdaten wahrscheinlich direkt in der Tabelle `ps_configuration` gespeichert werden, wobei Inhalt, Farbe und Position jeder Notiz serialisiert oder als einzelne Konfigurationsschlüssel gespeichert werden könnten.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul stützt sich stark auf JavaScript für seine interaktiven Funktionen im Back Office.

- `stickynotes/js/advajax.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Wahrscheinlich ein benutzerdefiniertes AJAX-Dienstprogramm-Skript, möglicherweise ein Wrapper für jQuerys AJAX-Funktionen oder eine eigenständige Implementierung zur Handhabung der asynchronen Kommunikation mit dem PHP-Backend des Moduls zum Speichern/Laden von Notizen.
- `stickynotes/js/joverlay.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Deutet auf Funktionen im Zusammenhang mit Overlays oder modalen Popups hin, die möglicherweise zum Bearbeiten von Notizinhalten in einer benutzerfreundlicheren Oberfläche oder zum Anzeigen von Bestätigungsmeldungen verwendet werden.
- `stickynotes/js/jscolor/jscolor.js`:
  - **Umfang:** Back-Office (speziell auf der Modulkonfigurationsseite).
  - **Verantwortlichkeit:** Eine Drittanbieter-JavaScript-Bibliothek zur Bereitstellung einer Farbauswahl-Oberfläche. Dies wird verwendet, um Administratoren die Auswahl der Hintergrundfarbe für ihre Haftnotizen zu ermöglichen.
- `stickynotes/js/script.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Dies ist wahrscheinlich das Hauptskript für die Frontend-Logik des Moduls. Es würde Folgendes behandeln:
    - Initialisierung von Haftnotizen beim Laden der Seite.
    - Drag-and-Drop-Funktionalität zum Neupositionieren von Notizen.
    - Speichern von Notizpositionen über AJAX.
    - Event-Listener zum Bearbeiten/Löschen von Notizen.
    - Interaktion mit `advajax.js` für die Datenpersistenz.
    - Potenziell dynamisches Rendern neuer Notizen.
- `stickynotes/js/script17.js`:
  - **Umfang:** Back-Office (PrestaShop 1.7.x und 8.x spezifisch).
  - **Verantwortlichkeit:** Dieses Skript enthält wahrscheinlich Anpassungen oder spezifischen Code für PrestaShop 1.7+-Umgebungen, die Unterschiede in der DOM-Struktur, jQuery-Versionen oder Back-Office-Theme-Änderungen im Vergleich zu älteren PrestaShop-Versionen (1.5/1.6) berücksichtigen. Es würde die Kompatibilität und ordnungsgemäße Funktion auf neueren Plattformen sicherstellen.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält CSS-Dateien, um das Erscheinungsbild der Haftnotizen zu gestalten.

- `stickynotes/css/stickynotes-twig-shit.css`:
  - **Umfang:** Back-Office-Admin-Styling.
  - **Verantwortlichkeit:** Der Name deutet darauf hin, dass diese Datei spezifische Styling-Anpassungen oder Überschreibungen für PrestaShop 1.7+-Back-Offices enthält, die Twig-Templating verwenden. Sie zielt wahrscheinlich auf Elemente innerhalb des neuen Back-Office-Themes ab, um sicherzustellen, dass Notizen korrekt und konsistent angezeigt werden.
  - **Wichtige CSS-Selektoren:** `.sticky-note`, `.sticky-note-content`, `.sticky-note-header` (hypothetisch, basierend auf gängigen Namenskonventionen).
- `stickynotes/css/stickynotes.css`:
  - **Umfang:** Back-Office-Admin-Styling.
  - **Verantwortlichkeit:** Dies ist das primäre Stylesheet für die Haftnotizen, das deren Standardaussehen, Positionierung und interaktive Zustände (z.B. beim Ziehen) definiert. Es würde allgemeine Stile enthalten, die über verschiedene PrestaShop-Versionen hinweg anwendbar sind.
  - **Wichtige CSS-Selektoren:** `.sticky-note`, `.draggable`, `.resizable`, `.note-text`, `.note-controls` (hypothetisch). Entwickler können diese Klassen bei Bedarf in ihren benutzerdefinierten Back-Office-Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet ein einziges Smarty-Template zum Rendern der Haftnotizen im Back Office.

- **Hook-Templates (`views/templates/hook/`)**:
  - `stickynotes/sticky-notes-back-office.tpl`:
    - **Gerendert im Hook:** Dieses Template ist wahrscheinlich in einen globalen Back-Office-Hook, wie `displayBackOfficeHeader` oder `displayAdminAfterHeader`, eingehängt, um die notwendige HTML-Struktur und JavaScript-Initialisierung für die Haftnotizen auf allen Admin-Seiten zu injizieren.
    - **Visuelle Blockausgabe:** Es gibt die HTML-Container für die Haftnotizen aus, möglicherweise einschließlich eines versteckten Templates für neue Notizen, und die JavaScript-Aufrufe zur Initialisierung der Notizanzeige und der Drag-Funktionalität. Es würde auch die Logik enthalten, um durch bestehende Notizen zu iterieren und sie zu rendern.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen. Es ist sehr wahrscheinlich, dass alle Haftnotizdaten (Inhalt, Farbe, Position, ID) in der Tabelle `ps_configuration` gespeichert werden. Jede Notiz könnte einem eindeutigen `PS_STICKY_NOTE_X`-Konfigurationsschlüssel entsprechen, wobei `X` ein Bezeichner ist und der Wert ein serialisiertes Array oder ein JSON-String ist, der die Eigenschaften der Notiz enthält.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Abschnitt jeder Back-Office-Seite ausgeführt. | Injiziert CSS- und JavaScript-Dateien, die für die Haftnotiz-Funktionalität und das Styling erforderlich sind. |
| `displayAdminAfterHeader` (oder ähnlich) | Wird nach dem Haupt-Header jeder Back-Office-Seite ausgeführt. | Rendert die HTML-Struktur für die Haftnotizen und initialisiert deren Anzeige und interaktives Verhalten. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (JS/CSS) festlegt. | Potenziell verwendet, um JS/CSS-Assets bedingt basierend auf der aktuellen Admin-Seite zu laden, obwohl `displayBackOfficeHeader` für globale Assets häufiger ist. |
| `actionModuleInstall` | Wird ausgeführt, wenn das Modul installiert wird. | Erstellt anfängliche Konfigurationseinträge in `ps_configuration` (falls vorhanden) und registriert notwendige Hooks. |
| `actionModuleUninstall` | Wird ausgeführt, wenn das Modul deinstalliert wird. | Bereinigt Konfigurationseinträge und hebt die Registrierung von Hooks auf. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Back office Sticky Notes“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
