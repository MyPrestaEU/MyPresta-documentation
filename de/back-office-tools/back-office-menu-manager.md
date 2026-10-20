---
title: "Back Office Menü-Manager - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Back Office Menü-Manager' von MyPresta.eu."
sidebar:
  label: "Back Office Menü-Manager - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Back office menu manager auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/back-office-menu-manager.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/back-office-menu-manager/)
>
> ---


# Back Office Menü-Manager

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständiger Konfigurations-Durchgang (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zum Hauptkonfigurationsbildschirm für das Modul „Back Office Menü-Manager“.

Dieser Bildschirm enthält typischerweise Standard-Moduleinstellungen, die Folgendes umfassen können:

- **Modul aktivieren/deaktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist ein Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Funktionen des Moduls, einschließlich der neuen Menüverwaltungsoptionen, sind in Ihrem Back Office aktiv.
    - *Wenn deaktiviert:* Das Modul beeinflusst Ihr Back Office-Menü nicht mehr, und das Standard-PrestaShop-Menüverhalten wird wiederhergestellt.
  - **Empfohlener Wert:** **JA** (Aktiviert), um das Modul zu verwenden.
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul testen oder vorübergehend zum Standard-PrestaShop-Menü zurückkehren möchten, können Sie es hier deaktivieren.
- **Moduleinstellungen zurücksetzen:**

  - **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, alle modulspezifischen Einstellungen und potenziell alle benutzerdefinierten Menükonfigurationen auf ihren Standardzustand zurückzusetzen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Beim Klicken:* Alle Ihre benutzerdefinierten Menüanordnungen und Moduleinstellungen werden gelöscht, und das Modul verhält sich so, als wäre es gerade zum ersten Mal installiert worden.
  - **Empfohlener Wert:** Mit Vorsicht verwenden. Klicken Sie nur, wenn Sie Ihre Menükonfiguration komplett neu starten möchten.
  - **Händlerszenario / Beispiel:** Wenn Sie viele Änderungen vorgenommen haben und neu anfangen möchten, oder wenn Sie auf ein unerwartetes Problem stoßen und Konfigurationsprobleme ausschließen möchten, kann dies ein nützlicher Schritt zur Fehlerbehebung sein.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul führt einen neuen, dedizierten Bereich in Ihrem PrestaShop Back Office ein, um die Menü-Tabs zu verwalten.

#### Bildschirmname & Menüposition: AdminMenuTabsController

- **Menüposition:** Nach der Installation des Moduls finden Sie einen neuen Menüpunkt, typischerweise unter **Erweiterte Parameter** oder einem ähnlichen Verwaltungsbereich, der so etwas wie **„Menü-Manager“** oder **„Back Office Menü“** heißt. Ein Klick darauf führt Sie zum Bildschirm `AdminMenuTabsController`.
- **Verfügbare Aktionen & Einstellungen:**
  Dieser Bildschirm bietet eine umfassende Gitteransicht (Tabelle) aller Menü-Tabs, die derzeit in Ihrem PrestaShop Back Office verfügbar sind. Für jeden Menü-Tab sehen Sie typischerweise:

  - **ID:** Die eindeutige Kennung für den Menü-Tab.
  - **Name:** Der Anzeigename des Menü-Tabs (z.B. „Bestellungen“, „Produkte“, „Kunden“).
  - **Eltern-Tab:** Zu welchem Hauptmenüpunkt dieser Tab gehört (z.B. „Bestellungen“ ist ein Elternteil von „Bestellungen“, „Rechnungen“, „Gutschriften“).
  - **Position:** Die numerische Reihenfolge des Tabs innerhalb seiner Elterngruppe.
  - **Aktiv/Inaktiv-Schalter:** Ein Umschalter zum Aktivieren oder Deaktivieren der Sichtbarkeit des Menü-Tabs.
  - **Bearbeiten/Löschen-Aktionen:** Schaltflächen zum Ändern der Details eines bestimmten Tabs oder zum Entfernen (Löschen mit äußerster Vorsicht verwenden, da dies Kernfunktionen entfernen könnte).

  **Wichtige Funktionen, die Sie hier ausführen können:**

  - **Menüpunkte neu anordnen:** Sie können normalerweise Zeilen im Raster per Drag & Drop verschieben oder den Wert für „Position“ manuell ändern, um die Reihenfolge der Menüpunkte zu ändern.
  - **Menüpunkte ausblenden/anzeigen:** Verwenden Sie den Aktiv/Inaktiv-Schalter, um Menüpunkte auszublenden, die Sie nicht verwenden oder die Sie bestimmten Mitarbeiterrollen vorenthalten möchten (wenn sie mit den nativen PrestaShop-Berechtigungen kombiniert werden).
  - **Menüpunkt-Details bearbeiten:** Sie können möglicherweise den Anzeigenamen eines Menüpunkts, sein Symbol oder seine Elternzuordnung ändern (obwohl das Ändern von Elternzuordnungen für Kern-Tabs ohne fortgeschrittene Kenntnisse im Allgemeinen nicht empfohlen wird).
  - **Neue Menüpunkte hinzufügen:** Obwohl für dieses spezifische Modul (das sich auf die Verwaltung *bestehender* Tabs konzentriert) weniger üblich, könnten einige erweiterte Versionen das Hinzufügen benutzerdefinierter Menülinks ermöglichen.
- **Auswirkung von Änderungen:**

  - **Ausblenden eines Tabs:** Der Tab verschwindet sofort aus Ihrem Back Office-Menü für alle Benutzer (es sei denn, es gibt spezifische Berechtigungsüberschreibungen).
  - **Neuanordnung von Tabs:** Die Reihenfolge der Menüpunkte ändert sich sofort in der Back Office-Navigation.
  - **Bearbeiten eines Tab-Namens:** Der im Back Office-Menü angezeigte Name wird aktualisiert.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. **Ersteinrichtung:** Gehen Sie alle Ihre Hauptmenüpunkte und deren Unterpunkte durch. Entscheiden Sie, welche Ihr Team regelmäßig, selten oder nie verwendet.
  2. **Aufräumen:** Verwenden Sie für selten oder nie verwendete Elemente den Schalter „Aktiv/Inaktiv“, um sie auszublenden. Dies vereinfacht das Menü erheblich.
  3. **Priorisieren:** Ordnen Sie häufig aufgerufene Elemente so an, dass sie ganz oben in ihren jeweiligen Abschnitten erscheinen. Wenn Sie beispielsweise die meiste Zeit mit „Bestellungen“ verbringen, stellen Sie sicher, dass „Bestellungen“ der erste Unterpunkt unter dem Hauptmenü „Bestellungen“ ist.
  4. **Regelmäßige Überprüfung:** Wenn sich Ihre Shop-Operationen weiterentwickeln oder neue Module installiert werden (die oft eigene Menüpunkte hinzufügen), besuchen Sie diesen Bildschirm erneut, um Ihr Menü optimiert zu halten.

#### Bildschirmname & Menüposition: index.php (adminmenu/controllers/admin/index.php)

Diese Datei, `index.php` innerhalb eines Admin-Controller-Verzeichnisses, dient typischerweise als Platzhalter oder Einstiegspunkt für die Funktionalität des Controllers, anstatt als eigenständiger Bildschirm mit konfigurierbaren Optionen. In PrestaShop werden die eigentliche Logik und Anzeige für einen Admin-Controller von der Hauptklasse (z.B. `AdminMenuTabsController.php`) gehandhabt.

Daher werden Sie nicht direkt mit einem „index.php“-Bildschirm interagieren. Seine Präsenz ist Teil der internen Struktur des Moduls und stellt sicher, dass der `AdminMenuTabsController` korrekt funktioniert. Alle Ihre Interaktionen erfolgen über die oben beschriebene `AdminMenuTabsController`-Oberfläche.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren/deaktivieren | Aktiviert | Aktiviert/deaktiviert die Menüverwaltungsfunktionen des Moduls. |
| Modulkonfiguration | Moduleinstellungen zurücksetzen | N/A (Aktion) | Setzt alle Moduleinstellungen und Menükonfigurationen auf Standard zurück. Mit Vorsicht verwenden. |
| AdminMenuTabsController | Tab-Name (z.B. „Bestellungen“) | Original PrestaShop Name | Zeigt den Namen des Menüpunkts an. Kann bearbeitet werden. |
| AdminMenuTabsController | Eltern-Tab | Original PrestaShop Eltern | Zeigt die Hauptmenükategorie für dieses Element an. |
| AdminMenuTabsController | Position | Variiert | Steuert die Anzeigereihenfolge des Menüpunkts innerhalb seines Elternteils. Kann per Drag-and-Drop oder direkter Eingabe geändert werden. |
| AdminMenuTabsController | Aktiv/Inaktiv-Schalter | Aktiv | Schaltet die Sichtbarkeit des Menüpunkts im Back Office um. |
| AdminMenuTabsController | Bearbeiten/Löschen-Aktionen | N/A (Aktion) | Ermöglicht die Änderung von Tab-Details oder das Entfernen (Löschen mit Vorsicht). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe einen Menüpunkt ausgeblendet, aber er wird immer noch für einige Benutzer angezeigt. Warum?**
A: Dieses Modul verwaltet die *Sichtbarkeit* und *Reihenfolge* von Menüpunkten. Die nativen PrestaShop-Benutzerberechtigungen (unter **Erweiterte Parameter > Team > Profile** und **Berechtigungen**) bestimmen, *wer auf was zugreifen kann*. Wenn ein Benutzerprofil explizite Berechtigungen für einen Tab hat, kann es diesen möglicherweise immer noch sehen, selbst wenn Sie ihn in diesem Modul als inaktiv markiert haben. Überprüfen Sie immer sowohl die Einstellungen dieses Moduls als auch die PrestaShop-Berechtigungen.

**F: Ich habe Änderungen vorgenommen, aber das Menü wurde nicht aktualisiert. Was soll ich tun?**
A:

1. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Performance**. Klicken Sie oben rechts auf „Cache leeren“. Dies ist oft notwendig, damit Back Office-Änderungen wirksam werden.
2. **Browser aktualisieren:** Manchmal ist ein Hard-Refresh Ihres Browsers (Strg+F5 oder Cmd+Shift+R) erforderlich, um den lokalen Browser-Cache zu leeren.
3. **Modulstatus überprüfen:** Stellen Sie sicher, dass das Modul „Back Office Menü-Manager“ unter **Module > Modul-Manager** noch aktiviert ist.

**F: Kann ich mit diesem Modul völlig neue benutzerdefinierte Links zum Back Office-Menü hinzufügen?**
A: Dieses Modul konzentriert sich hauptsächlich auf die Verwaltung *bestehender* PrestaShop-Menü-Tabs. Während einige erweiterte Versionen die Erstellung benutzerdefinierter Links anbieten könnten, besteht sein Hauptzweck darin, die Verwaltung der Standard-PrestaShop-Menüstruktur zu ermöglichen. Wenn Sie komplexe benutzerdefinierte Links hinzufügen müssen, benötigen Sie möglicherweise ein fortschrittlicheres Modul oder eine benutzerdefinierte Entwicklung.

**F: Ich habe versehentlich einen PrestaShop-Kernmenüpunkt gelöscht. Wie bekomme ich ihn zurück?**
A: Das Löschen von Kernmenüpunkten wird im Allgemeinen nicht empfohlen. Wenn Sie dies getan haben, ist der sicherste Weg, es wiederherzustellen:

1. **Modul deaktivieren und wieder aktivieren:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Back Office Menü-Manager“, deaktivieren Sie es und aktivieren Sie es dann wieder. Dies löst oft eine Neuinitialisierung der Standardmenüeinträge aus.
2. **Moduleinstellungen zurücksetzen:** Wenn das oben Genannte nicht funktioniert, gehen Sie zur Konfigurationsseite des Moduls und verwenden Sie die Option „Moduleinstellungen zurücksetzen“. Beachten Sie, dass dadurch ALLE Ihre benutzerdefinierten Menükonfigurationen gelöscht werden.
3. **Aus Backup wiederherstellen:** Als letztes Mittel, wenn kritische Menüpunkte fehlen, müssen Sie möglicherweise Ihre Datenbank aus einem Backup wiederherstellen, das *vor* dem Löschen erstellt wurde.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Back Office Menü-Manager“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Back Office Menü-Manager“ erweitert die Kernfunktionalität des PrestaShop Back Office hauptsächlich durch das Überschreiben spezifischer Hilfsklassen, um Menüverwaltungsfunktionen wieder einzuführen. Es nutzt das MVC-Muster von PrestaShop mit einem dedizierten Admin Controller (`AdminMenuTabsController`), um die Benutzeroberfläche zur Verwaltung von Menü-Tabs bereitzustellen. Das Modul interagiert mit der Datenbanktabelle `ps_tab`, die Informationen über Back Office-Menüpunkte speichert. Die wichtigste architektonische Entscheidung ist die Verwendung von Overrides, um das Kernverhalten von PrestaShop zu ändern, ohne Kerndateien direkt zu modifizieren, was eine bessere Kompatibilität und Upgrade-Pfade gewährleistet.

### 4.2 Controller (`controllers/`)

- **Front-Office Controller**:
  Dieses Modul enthält keine Front-Office Controller, da seine Funktionalität ausschließlich für das PrestaShop Back Office bestimmt ist.
- **Back-Office Admin Controller**:

  - `adminmenu/controllers/admin/AdminMenuTabs.php`

    - **Klassenname & Elternklasse**: `AdminMenuTabsController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität**: Dieser Controller verwaltet die `Tab`-Entität (die Back Office-Menüpunkte darstellt). Er erstellt einen dedizierten Menüeintrag im Back Office für den „Menü-Manager“.
    - **Verantwortlichkeit**: Dies ist der primäre Controller für die Benutzeroberfläche des Moduls. Er verwaltet die Anzeige der Liste aller Back Office-Tabs und ermöglicht Administratoren, diese anzuzeigen, zu bearbeiten, zu aktivieren/deaktivieren und neu anzuordnen. Er verwendet typischerweise `HelperList` für die Gitteranzeige und `HelperForm` für alle Bearbeitungsformulare. Er verarbeitet POST-Anfragen zum Speichern von Änderungen (z.B. Positionsaktualisierungen, Statusumschaltungen).
  - `adminmenu/controllers/admin/index.php`

    - **Verantwortlichkeit**: Diese Datei ist ein Standard-Platzhalter innerhalb der Controller-Struktur von PrestaShop. Sie enthält typischerweise eine einfache `die('No direct script access allowed');`-Anweisung, um den direkten Zugriff auf das Verzeichnis zu verhindern und sicherzustellen, dass Anfragen über den PrestaShop-Dispatcher geleitet werden. Sie enthält keine funktionale Logik für das Modul selbst.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul verwendet Overrides, um das Kernverhalten von PrestaShop zu ändern.

- `adminmenu/override/classes/helper/HelperList.php`

  - **Klassenname & Elternklasse**: `HelperList` (überschreibt die Kernklasse `HelperList`).
  - **Was es tut**: Dieser Override modifiziert wahrscheinlich das Verhalten von `HelperList` speziell beim Rendern der Liste der `Tab`-Entitäten im Back Office. Dies ist entscheidend, um Funktionen wie Drag-and-Drop-Neuanordnung oder spezifische Spaltenanzeigen wieder zu aktivieren, die aus der Standard-`HelperList`-Implementierung für `Tab` in neueren PrestaShop-Versionen entfernt wurden. Es könnte benutzerdefinierte Aktionen injizieren oder die Art und Weise ändern, wie Daten für Menü-Tabs abgerufen oder angezeigt werden.
- `adminmenu/override/classes/helper/index.php`

  - **Verantwortlichkeit**: Ähnlich wie `controllers/admin/index.php` ist dies eine Platzhalterdatei, um direkte Verzeichnisauflistungen oder Zugriffe zu verhindern.
- `adminmenu/override/classes/index.php`

  - **Verantwortlichkeit**: Eine weitere Platzhalterdatei, um direkte Verzeichnisauflistungen oder Zugriffe zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

Das bereitgestellte Inventar weist keine benutzerdefinierten JavaScript-Dateien innerhalb des Moduls auf. Dies deutet darauf hin, dass die Menüverwaltungsfunktionalität, einschließlich Funktionen wie Drag-and-Drop-Neuanordnung, entweder durch:

1. PrestaShops natives `HelperList`-JavaScript (das der Override des Moduls möglicherweise wieder aktiviert oder konfiguriert).
2. Serverseitige Verarbeitung für Positionsaktualisierungen.
3. Minimales Inline-JS, das von den Klassen `HelperList` oder `HelperForm` generiert wird.

Entwickler sollten den generierten HTML-Code und die Netzwerkanfragen auf der `AdminMenuTabsController`-Seite überprüfen, um die genaue JS-Implementierung für interaktive Elemente zu verstehen.

### 4.5 CSS-Stylesheets (`views/css/`)

Das bereitgestellte Inventar weist keine benutzerdefinierten CSS-Dateien innerhalb des Moduls auf. Dies impliziert, dass das Modul vollständig auf die Standard-Back Office-Formatierung von PrestaShop angewiesen ist. Jede benutzerdefinierte Formatierung für die Menü-Manager-Oberfläche würde entweder:

1. Inline über Smarty-Templates oder PHP injiziert.
2. Bestehende PrestaShop-CSS-Klassen nutzen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das bereitgestellte Inventar weist keine benutzerdefinierten Smarty-Template-Dateien (`.tpl`) innerhalb des Moduls auf. Dies ist ein starker Hinweis darauf, dass das Modul hauptsächlich auf die Standard-`HelperList`- und `HelperForm`-Templates von PrestaShop angewiesen ist, um seine Back Office-Oberfläche zu rendern.

Der `AdminMenuTabsController` würde `HelperList`- und `HelperForm`-Objekte instanziieren, ihnen Konfigurations-Arrays übergeben, und diese Helfer würden dann die Benutzeroberfläche mithilfe der PrestaShop-Kerntemplates rendern (z.B. `_partials/helpers/list_action_enable.tpl`, `helpers/list/list_content.tpl`, `helpers/form/form.tpl`).

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Dieses Modul interagiert hauptsächlich mit der bestehenden PrestaShop-Kerntabelle:

  - `ps_tab`: Diese Tabelle speichert alle Back Office-Menüeinträge, einschließlich ihrer Namen, Eltern-IDs, Positionen und des aktiven Status. Der `AdminMenuTabsController` und der `HelperList`-Override des Moduls lesen und schreiben direkt in diese Tabelle, um das Menü zu verwalten.
  - `ps_configuration`: Standard-PrestaShop-Konfigurationstabelle. Die Hauptkonfigurationseinstellungen des Moduls (z.B. Aktivierungs-/Deaktivierungsstatus) würden hier gespeichert (z.B. `PS_ADMINMENU_MANAGER_ENABLED`).
- **Registrierte Hooks-Tabelle**:
  Basierend auf der Beschreibung und Funktionalität des Moduls registriert es keine expliziten Front-Office- oder Back-Office-Anzeige-Hooks (`displayHeader`, `actionValidateOrder` usw.) im traditionellen Sinne. Seine Funktionalität wird erreicht durch:

  1. **Admin Controller Registrierung**: Das Modul registriert `AdminMenuTabsController` als neuen Back Office-Tab, wodurch er über das Back Office-Menü zugänglich wird.
  2. **Klassen-Overrides**: Der Kernmechanismus basiert auf dem Überschreiben von `classes/helper/HelperList.php`, um die Verwaltung und Anzeige von Menü-Tabs im Back Office zu ändern. Dies ist kein „Hook“, sondern eine direkte Änderung des Kernverhaltens.

  Daher ist eine Tabelle der registrierten Hooks im typischen Sinne für dieses Modul nicht anwendbar. Seine Auswirkungen betreffen die internen Abläufe der Back Office-Menüdarstellung.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Back Office Menü-Manager“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
