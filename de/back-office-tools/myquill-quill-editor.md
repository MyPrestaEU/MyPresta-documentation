---
title: "MyQuill - Quill Editor - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul MyQuill - Quill Editor von MyPresta.eu."
sidebar:
  label: "MyQuill - Quill Editor"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul MyQuill - Quill editor auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/myquill-quill-editor.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/myquill-quill-editor/)
>
> ---


# MyQuill - Quill Editor

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation gelangen Sie durch Klicken auf "Konfigurieren" zur Hauptkonfigurationsseite für MyQuill. Hier steuern Sie, wie sich der Quill-Editor in Ihrem Back Office verhält.

#### **Registerkarte "Allgemeine Einstellungen"**

**1. MyQuill Editor aktivieren**
-   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren des MyQuill-Editors.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Der Quill-Editor ersetzt den Standard-TinyMCE-Editor in allen unterstützten Bereichen Ihres PrestaShop Back Office (z.B. Produktbeschreibungen, CMS-Seiten, Kategoriebeschreibungen).
    -   *Wenn deaktiviert (NEIN):* Der Standard-TinyMCE-Editor wird wiederhergestellt, und die Funktionen von MyQuill sind nicht verfügbar.
-   **Empfohlener Wert:** **JA** (um die Funktionen des Moduls zu nutzen).
-   **Händlerszenario / Beispiel:** Wenn Sie vorübergehend zu TinyMCE zurückkehren möchten, um die Kompatibilität mit einem anderen Modul zu testen, würden Sie MyQuill hier deaktivieren. Andernfalls lassen Sie es aktiviert, um den erweiterten Editor zu nutzen.

**2. Quill Editor im Front Office laden**
-   **Was diese Einstellung bewirkt:** Legt fest, ob die notwendigen Quill-Editor-Assets (CSS, JS) im Front Office Ihres Shops geladen werden. Dies ist normalerweise nur erforderlich, wenn Sie ein benutzerdefiniertes Theme oder ein anderes Modul haben, das Quill im Frontend verwendet.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Die Core-Dateien von Quill werden in die öffentlichen Seiten Ihres Shops aufgenommen. Dies könnte die Ladezeit der Seite leicht erhöhen, ist aber notwendig, wenn Sie von Quill generierte Inhalte anzeigen, die deren spezifisches Styling oder Funktionalität im Frontend erfordern.
    -   *Wenn deaktiviert (NEIN):* Die Core-Dateien von Quill werden *nicht* im Front Office geladen, was Bandbreite spart und möglicherweise die Ladezeit der Seite verbessert.
-   **Empfohlener Wert:** **NEIN** (es sei denn, Sie haben einen spezifischen Grund, es zu laden, wie z.B. eine benutzerdefinierte Theme-Funktion).
-   **Händlerszenario / Beispiel:** Wenn Sie ein benutzerdefiniertes Theme verwenden, das interaktive Inhalte (wie Akkordeons oder Tabs) anzeigt, die mit MyQuill erstellt wurden, und diese Elemente nicht korrekt gerendert werden, könnte die Aktivierung dieses Problems das Problem beheben. Für die meisten Shops ist es nicht erforderlich.

**3. Quill Editor im Back Office laden**
-   **Was diese Einstellung bewirkt:** Steuert, ob die Quill-Editor-Assets in Ihrem PrestaShop Back Office geladen werden. Dies ist für die Funktion des Moduls unerlässlich.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Der Quill-Editor wird geladen und funktioniert korrekt in Ihrem Back Office.
    -   *Wenn deaktiviert (NEIN):* Der Quill-Editor wird nicht geladen, und Sie sehen wahrscheinlich einen leeren Editorbereich oder den Standard-TinyMCE. Dies deaktiviert effektiv die Kernfunktionalität des Moduls im Back Office.
-   **Empfohlener Wert:** **JA** (Dies muss aktiviert sein, damit das Modul funktioniert).
-   **Händlerszenario / Beispiel:** Sie sollten dies immer aktiviert lassen. Eine Deaktivierung würde Sie daran hindern, die Funktionen von MyQuill im Admin-Panel zu nutzen.

**4. Editor-Höhe (in Pixel)**
-   **Was diese Einstellung bewirkt:** Legt die Standardhöhe des Quill-Editor-Eingabebereichs in Pixeln fest.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf einen höheren Wert eingestellt (z.B. 500px):* Der Editor wird höher angezeigt, wodurch Sie mehr vertikalen Platz zum Anzeigen und Bearbeiten Ihrer Inhalte ohne Scrollen haben.
    -   *Wenn auf einen niedrigeren Wert eingestellt (z.B. 200px):* Der Editor wird kürzer, was für kürzere Inhaltsabschnitte nützlich sein kann, aber bei längeren Beschreibungen mehr Scrollen erfordern könnte.
-   **Empfohlener Wert:** **300px** (oder passen Sie ihn an Ihre Präferenz für die typische Inhaltslänge an).
-   **Händlerszenario / Beispiel:** Wenn Sie häufig sehr lange Produktbeschreibungen schreiben, könnte eine Erhöhung auf 400px oder 500px Ihr Bearbeitungserlebnis komfortabler machen. Für kurze CMS-Seitentitel könnte eine geringere Höhe ausreichend sein.

**5. Editor-Toolbar-Optionen**
-   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Anpassung der Tools, die in der Toolbar des Quill-Editors angezeigt werden. Sie können verschiedene Schaltflächen und Funktionen auswählen oder abwählen.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn Optionen ausgewählt sind:* Die entsprechenden Schaltflächen (z.B. fett, kursiv, Bild, Video, Tabelle) werden in der Editor-Toolbar angezeigt, wodurch diese Funktionen für Sie verfügbar sind.
    -   *Wenn Optionen abgewählt sind:* Die entsprechenden Schaltflächen werden aus der Toolbar ausgeblendet, wodurch ihre Verwendung verhindert wird.
-   **Empfohlener Wert:** Aktivieren Sie zunächst alle Optionen und deaktivieren Sie dann alle Tools, von denen Sie sicher sind, dass Sie sie nie verwenden werden, um die Toolbar zu vereinfachen.
-   **Händlerszenario / Beispiel:** Wenn Sie nie vorhaben, Videos einzubetten, könnten Sie die Option "YouTube/Vimeo" abwählen, um die Toolbar zu entrümpeln. Wenn Sie sicherstellen möchten, dass Ihr Team nur grundlegende Formatierungen verwendet, könnten Sie die Optionen erheblich einschränken.

**6. Bild-Upload-Ordner**
-   **Was diese Einstellung bewirkt:** Gibt den Standardordner auf Ihrem Server an, in dem Bilder gespeichert werden, die über den Quill-Editor hochgeladen werden.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn auf einen bestimmten Pfad eingestellt (z.B. `/img/cms/`):* Alle über den Editor hochgeladenen Bilder werden in diesen Ordner verschoben.
    -   *Wenn als Standard belassen (normalerweise `/img/cms/` oder ähnlich):* Bilder werden im Standard-PrestaShop-CMS-Bildverzeichnis gespeichert.
-   **Empfohlener Wert:** Als Standard belassen (`/img/cms/`), es sei denn, Sie haben einen spezifischen organisatorischen Bedarf, ihn zu ändern.
-   **Händlerszenario / Beispiel:** Wenn Sie produktspezifische Bilder von CMS-Seitenbildern getrennt halten möchten, könnten Sie einen neuen Ordner erstellen (z.B. `/img/products_quill/`) und diese Option entsprechend einstellen. Stellen Sie sicher, dass der Ordner existiert und Schreibrechte hat.

**7. SEO-Link-Generierung aktivieren**
-   **Was diese Einstellung bewirkt:** Aktiviert eine Funktion, die Ihnen hilft, SEO-freundliche Links in Ihren Inhalten zu erstellen.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Das Link-Tool in Quill bietet Optionen zum Generieren sauberer, beschreibender Links, möglicherweise unter Verwendung von Produkt- oder Kategorienamen als Linktext.
    -   *Wenn deaktiviert (NEIN):* Das Link-Tool verhält sich wie ein Standard-Link-Einfüger ohne spezifische SEO-Verbesserungen.
-   **Empfohlener Wert:** **JA** (um von einer verbesserten internen Verlinkung für SEO zu profitieren).
-   **Händlerszenario / Beispiel:** Beim Verlinken auf ein Produkt könnte diese Funktion Ihnen helfen, automatisch einen Link mit dem Namen des Produkts als Ankertext zu generieren, was besser für SEO ist, anstatt nur die URL einzufügen.

**8. YouTube/Vimeo-Einbettung aktivieren**
-   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen das direkte Einbetten von Videos von YouTube und Vimeo in Ihre Inhalte mithilfe des Quill-Editors.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Eine spezielle Schaltfläche oder Option wird in der Toolbar angezeigt, um Video-URLs einfach einzufügen und einzubetten.
    -   *Wenn deaktiviert (NEIN):* Sie können das spezielle Video-Einbettungstool nicht verwenden.
-   **Empfohlener Wert:** **JA** (wenn Sie Videos in Ihren Inhalten verwenden möchten).
-   **Händlerszenario / Beispiel:** Sie können ganz einfach ein Produktdemonstrationsvideo zu einer Produktbeschreibung oder ein Markengeschichtenvideo zu Ihrer "Über uns"-Seite hinzufügen.

**9. Tabellen aktivieren**
-   **Was diese Einstellung bewirkt:** Fügt die Funktionalität zum Erstellen und Bearbeiten von HTML-Tabellen innerhalb des Quill-Editors hinzu.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Ein Tabellen-Erstellungstool wird in der Toolbar verfügbar sein, mit dem Sie Tabellen einfügen und verwalten können (Zeilen/Spalten hinzufügen, Zellen zusammenführen usw.).
    -   *Wenn deaktiviert (NEIN):* Das Tabellen-Tool wird ausgeblendet.
-   **Empfohlener Wert:** **JA** (Tabellen sind nützlich zum Anzeigen strukturierter Daten wie Spezifikationen oder Vergleiche).
-   **Händlerszenario / Beispiel:** Verwenden Sie Tabellen, um Produktspezifikationen, Vergleichstabellen oder Versandkosteninformationen auf einer CMS-Seite anzuzeigen.

**10. Bootstrap-Schaltflächen aktivieren**
-   **Was diese Einstellung bewirkt:** Bietet ein Tool zum einfachen Einfügen von Bootstrap-gestylten Schaltflächen in Ihre Inhalte, die für Call-to-Actions verwendet werden können.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Ein Schaltflächen-Tool wird angezeigt, mit dem Sie Schaltflächenstile (primär, sekundär, Erfolg usw.) auswählen und verlinken können.
    -   *Wenn deaktiviert (NEIN):* Das Schaltflächen-Tool wird ausgeblendet.
-   **Empfohlener Wert:** **JA** (für klare Call-to-Actions).
-   **Händlerszenario / Beispiel:** Fügen Sie eine "Jetzt kaufen"-Schaltfläche zu einem Werbebanner auf einer CMS-Seite oder eine "PDF herunterladen"-Schaltfläche zu den technischen Spezifikationen eines Produkts hinzu.

**11. Tabs aktivieren**
-   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen das Erstellen von Inhaltsbereichen mit Tabs, nützlich zur Organisation großer Informationsmengen auf kompakte Weise.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Ein Tab-Erstellungstool wird verfügbar sein, mit dem Sie Tab-Titel und Inhalte für jeden Tab definieren können.
    -   *Wenn deaktiviert (NEIN):* Das Tab-Tool wird ausgeblendet.
-   **Empfohlener Wert:** **JA** (für eine bessere Inhaltsorganisation).
-   **Händlerszenario / Beispiel:** Verwenden Sie auf einer Produktseite Tabs für "Beschreibung", "Spezifikationen", "Bewertungen" und "Versandinformationen", um die Seite übersichtlich zu halten.

**12. Galerien aktivieren**
-   **Was diese Einstellung bewirkt:** Integriert eine Funktion zum Erstellen einfacher Bildergalerien innerhalb Ihrer Inhalte.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Ein Galerie-Tool wird angezeigt, mit dem Sie mehrere Bilder auswählen und in einer Galerie anordnen können.
    -   *Wenn deaktiviert (NEIN):* Das Galerie-Tool wird ausgeblendet.
-   **Empfohlener Wert:** **JA** (für visuell ansprechende Bildanzeigen).
-   **Händlerszenario / Beispiel:** Zeigen Sie mehrere Ansichten eines Produkts oder eine Sammlung von Lifestyle-Bildern auf einer CMS-Seite.

**13. FAQ (Akkordeon) aktivieren**
-   **Was diese Einstellung bewirkt:** Fügt ein Tool zum Erstellen interaktiver FAQ-Abschnitte im Akkordeon-Format (erweiterbar/einklappbar) hinzu.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Ein FAQ-Tool wird verfügbar sein, mit dem Sie Frage-Antwort-Paare hinzufügen können, die Benutzer erweitern oder einklappen können.
    -   *Wenn deaktiviert (NEIN):* Das FAQ-Tool wird ausgeblendet.
-   **Empfohlener Wert:** **JA** (hervorragend für Support-Seiten oder Produkt-FAQs).
-   **Händlerszenario / Beispiel:** Erstellen Sie eine dedizierte "Häufig gestellte Fragen"-CMS-Seite oder fügen Sie einen kleinen FAQ-Abschnitt zu einer Produktseite hinzu, um häufige Kundenanfragen zu beantworten.

#### **Speichern-Schaltfläche**
-   **Was dies bewirkt:** Nachdem Sie Änderungen an den Einstellungen auf dieser Seite vorgenommen haben, müssen Sie auf die Schaltfläche "Speichern" klicken, um sie zu übernehmen.
-   **Auswirkung des Klickens:** Ihre Änderungen werden in der Datenbank gespeichert, und der Quill-Editor wird diese neuen Einstellungen beim nächsten Öffnen im Back Office widerspiegeln.
-   **Empfohlene Aktion:** Klicken Sie immer auf "Speichern", nachdem Sie eine Einstellung geändert haben.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

MyQuill integriert sich primär direkt in bestehende PrestaShop-Inhaltsbearbeitungsbildschirme (wie Produkt-, Kategorie- und CMS-Seiten-Bearbeitungsformulare). Es führt keine neuen Top-Level-Menüpunkte oder dedizierten Datenverwaltungsbildschirme für eigene Inhalte ein. Die Controller "AdminMyquillAjaxController" und "index.php" sind interne Komponenten, die die Hintergrundoperationen des Moduls verwalten, wie z.B. Bild-Uploads oder das dynamische Laden von Inhalten für die Editor-Funktionen.

Daher gibt es keinen separaten "AdminMyquill"-Bildschirm für Sie zur Verwaltung. Die gesamte Interaktion findet direkt in den Inhaltsbearbeitungsformularen statt, wo Quill TinyMCE ersetzt.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| **Modulkonfigurationsseite** | MyQuill Editor aktivieren | JA | Aktiviert/deaktiviert den Quill-Editor im BO. |
| | Quill Editor im Front Office laden | NEIN | Lädt Quill-Assets im FO (nur bei Bedarf durch Theme/Modul). |
| | Quill Editor im Back Office laden | JA | Lädt Quill-Assets im BO (essenziell für Modulfunktion). |
| | Editor-Höhe (in Pixel) | 300px | Legt die vertikale Größe des Editorfensters fest. |
| | Editor-Toolbar-Optionen | Alle aktiviert | Passt an, welche Tools in der Editor-Toolbar erscheinen. |
| | Bild-Upload-Ordner | `/img/cms/` | Gibt an, wo hochgeladene Bilder gespeichert werden. |
| | SEO-Link-Generierung aktivieren | JA | Fügt Funktionen zum Erstellen von SEO-freundlichen Links hinzu. |
| | YouTube/Vimeo-Einbettung aktivieren | JA | Ermöglicht das Einbetten von Videos von YouTube/Vimeo. |
| | Tabellen aktivieren | JA | Fügt Funktionalität zum Erstellen und Bearbeiten von HTML-Tabellen hinzu. |
| | Bootstrap-Schaltflächen aktivieren | JA | Bietet ein Tool zum Einfügen von Bootstrap-gestylten Schaltflächen. |
| | Tabs aktivieren | JA | Ermöglicht das Erstellen von Inhaltsbereichen mit Tabs. |
| | Galerien aktivieren | JA | Integriert eine Funktion zum Erstellen von Bildergalerien. |
| | FAQ (Akkordeon) aktivieren | JA | Fügt ein Tool zum Erstellen interaktiver FAQ-Abschnitte hinzu. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Nach der Installation von MyQuill ist der Editorbereich leer oder zeigt immer noch TinyMCE an.**
*   **A:** Stellen Sie zunächst sicher, dass "MyQuill Editor aktivieren" und "Quill Editor im Back Office laden" in der Modulkonfiguration beide auf **JA** eingestellt sind. Zweitens, leeren Sie Ihren PrestaShop-Cache: Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie dann oben rechts auf "Cache leeren". Leeren Sie auch den Cache Ihres Browsers.

**F2: Meine Bilder werden nicht hochgeladen, oder ich kann sie nach dem Hochladen nicht sehen.**
*   **A:** Überprüfen Sie die Einstellung "Bild-Upload-Ordner" in der MyQuill-Konfiguration. Stellen Sie sicher, dass der angegebene Ordner auf Ihrem Server existiert (z.B. `/img/cms/`) und die korrekten Schreibrechte (normalerweise 755 oder 775) hat. Wenn der Ordner nicht existiert, erstellen Sie ihn per FTP/SFTP.

**F3: Einige Toolbar-Schaltflächen (z.B. Tabellen, Videos) fehlen im Editor.**
*   **A:** Gehen Sie zur MyQuill-Konfigurationsseite und überprüfen Sie den Abschnitt "Editor-Toolbar-Optionen". Stellen Sie sicher, dass die spezifischen Funktionen, die Sie verwenden möchten (z.B. "Tabellen aktivieren", "YouTube/Vimeo-Einbettung aktivieren"), auf **JA** eingestellt sind. Speichern Sie Ihre Änderungen und leeren Sie den Cache.

**F4: Mit MyQuill erstellte Inhalte (wie Tabs oder Akkordeons) werden in meinem Front Office nicht korrekt angezeigt.**
*   **A:** Dies geschieht oft, wenn Ihr Theme die notwendigen CSS- oder JavaScript-Dateien für diese interaktiven Elemente nicht enthält. Versuchen Sie, "Quill Editor im Front Office laden" in der MyQuill-Konfiguration zu aktivieren. Wenn das Problem weiterhin besteht, benötigt Ihr Theme möglicherweise spezifische Bootstrap- oder JavaScript-Bibliotheken, die nicht standardmäßig geladen werden oder Konflikte verursachen. In diesem Fall müssen Sie möglicherweise einen Webmaster zur Untersuchung hinzuziehen.

**F5: Wie kehre ich zum Standard-TinyMCE-Editor zurück?**
*   **A:** Gehen Sie einfach zu **Module > Modul-Manager**, suchen Sie "MyQuill - Quill Editor" und klicken Sie auf die Schaltfläche "Deaktivieren". Alle zuvor mit MyQuill erstellten Inhalte bleiben erhalten, aber die Bearbeitungsoberfläche kehrt zu TinyMCE zurück. Sie können MyQuill jederzeit wieder aktivieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)
Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht
Das MyQuill-Modul integriert den Rich-Text-Editor Quill.js in das PrestaShop Back Office und ersetzt den Standard-TinyMCE. Dies wird erreicht, indem es sich in den Hook `displayBackOfficeHeader` einklinkt, um seine Assets zu injizieren, und dann JavaScript verwendet, um Quill-Instanzen auf relevanten Textarea-Elementen zu zielen und zu initialisieren. Das Modul bietet erweiterte Funktionen wie Bild-Uploads, Video-Einbettung und benutzerdefinierte Inhaltsblöcke (Tabellen, Tabs, Galerien, FAQs), indem es die Funktionalität von Quill erweitert und AJAX-Endpunkte für serverseitige Operationen bereitstellt. Es vermeidet Core-Überschreibungen, was Kompatibilität und einfache Deinstallation gewährleistet.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    Das Modul enthält keine dedizierten Front-Office-Controller. Alle Front-Office-Funktionalitäten, die mit der Anzeige von Quill-generierten Inhalten zusammenhängen, werden durch das Rendering von Standard-PrestaShop-Inhalten (Produktbeschreibungen, CMS-Seiten usw.) durch das Theme und das optionale Laden der Front-Office-Assets von MyQuill über Hooks gehandhabt.

-   **Back-Office-Admin-Controller**:
    *   `controllers/admin/AdminMyquillAjaxController.php`
        *   **Klassenname & Elternklasse**: `AdminMyquillAjaxController` erweitert `ModuleAdminController`.
        *   **Verantwortlichkeit**: Dieser Controller verarbeitet AJAX-Anfragen, die vom Quill-Editor im Back Office stammen. Seine Hauptaufgabe ist die Verwaltung serverseitiger Operationen wie Bild-Uploads, um sicherzustellen, dass sie korrekt im dafür vorgesehenen Verzeichnis gespeichert werden und die URL zur Einfügung in den Editor zurückgegeben wird. Er könnte auch andere dynamische Datenanfragen für spezifische Quill-Plugins (z.B. Abrufen von Produktdaten für SEO-Links) verarbeiten.
    *   `controllers/admin/index.php`
        *   **Klassenname & Elternklasse**: Diese Datei enthält typischerweise eine einfache `die('Access Denied');`-Anweisung oder eine ähnliche Sicherheitsmaßnahme.
        *   **Verantwortlichkeit**: Es ist eine Standard-PrestaShop-Praxis, eine `index.php`-Datei in jedem Verzeichnis zu platzieren, um die Verzeichnisauflistung und den direkten Zugriff zu verhindern. Sie enthält keine funktionale Controller-Logik für das Modul.

### 4.3 Core-Klassen & Modelle (`classes/`)
Das MyQuill-Modul führt keine benutzerdefinierten `ObjectModel`-Klassen oder Datenbanktabellen ein. Es funktioniert hauptsächlich, indem es die Editor-Oberfläche ersetzt und seine Konfiguration in `ps_configuration` speichert. Mit Quill erstellte Inhalte werden direkt in den vorhandenen PrestaShop-Inhaltsfeldern (z.B. `ps_product_lang.description`, `ps_cms_lang.content`) als Standard-HTML gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

-   `views/js/myquill-admin.js`
    *   **Geltungsbereich**: Back-Office.
    *   **Details**: Dies ist die Haupt-JavaScript-Datei für die Administration. Sie ist verantwortlich für die Initialisierung des Quill-Editors auf allen relevanten Textarea-Elementen innerhalb des PrestaShop Back Office. Sie liest die Konfigurationseinstellungen des Moduls (Editor-Höhe, Toolbar-Optionen, aktivierte Funktionen) und konstruiert dynamisch die Quill-Instanz mit den entsprechenden Modulen und Handlern. Sie enthält auch Logik zur Integration benutzerdefinierter Toolbar-Schaltflächen und zur Handhabung ihrer Aktionen (z.B. Öffnen von Bild-Upload-Dialogen, Einfügen von Video-Einbettungen).
-   `views/js/myquill-editor.js`
    *   **Geltungsbereich**: Back-Office.
    *   **Details**: Diese Datei enthält wahrscheinlich die Kernbibliothek von Quill.js selbst oder spezifische Anpassungen/Erweiterungen des Basis-Quill-Editors. Sie definiert das grundlegende Verhalten, das Rendering und die API des Editors.
-   `views/js/myquill-front.js`
    *   **Geltungsbereich**: Front-Office.
    *   **Details**: Dieses Skript wird bedingt im Front Office geladen, wenn die Einstellung "Quill Editor im Front Office laden" aktiviert ist. Es enthält JavaScript, das notwendig ist, um mit Quill erstellte interaktive Elemente (wie Tabs, Akkordeons, Galerien) auf der kundenorientierten Seite des Shops funktionsfähig zu machen. Es könnte Listener für Klickereignisse auf Tab-Überschriften oder Akkordeon-Titel enthalten, um die Sichtbarkeit des Inhalts umzuschalten.
-   `views/js/myquill-plugins.js`
    *   **Geltungsbereich**: Back-Office.
    *   **Details**: Diese Datei kapselt die JavaScript-Logik für verschiedene benutzerdefinierte Plugins und Erweiterungen, die von MyQuill zu Quill hinzugefügt wurden. Dies umfasst die Implementierung von Funktionen wie Bild-Upload-Verwaltung, Video-Einbettung, Tabellenerstellung, Bootstrap-Schaltflächen, Tabs, Galerien und FAQ-Akkordeons. Sie definiert, wie diese benutzerdefinierten "Blots" (Quills Begriff für benutzerdefinierte Inhaltsblöcke) gerendert werden und wie sich ihre zugehörigen Toolbar-Aktionen verhalten.
-   `views/js/myquill-pro.js`
    *   **Geltungsbereich**: Back-Office.
    *   **Details**: Diese Datei enthält wahrscheinlich erweiterte oder "Pro"-Funktionen und Verbesserungen für den Quill-Editor, die möglicherweise auf `myquill-plugins.js` aufbauen. Sie könnte anspruchsvollere UI-Elemente, zusätzliche Formatierungsoptionen oder weitere Integrationen enthalten, die spezifisch für die MyPresta.eu-Version des Moduls sind.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `views/css/myquill-admin.css`
    *   **Geltungsbereich**: Back-Office-Admin-Formular-Styling.
    *   **Details**: Enthält Stile, die spezifisch für das Erscheinungsbild des Quill-Editors innerhalb des PrestaShop Back Office sind. Dies umfasst das Styling für die Toolbar, den Editor-Container, benutzerdefinierte Dialoge und die Sicherstellung, dass der Editor visuell in das PrestaShop-Admin-Theme integriert ist.
-   `views/css/myquill-editor.css`
    *   **Geltungsbereich**: Back-Office-Admin-Formular-Styling.
    *   **Details**: Diese Datei enthält wahrscheinlich das Kern-CSS für den Quill-Editor selbst, das Basisstile für Textformatierung, Blockzitate, Listen und andere Standard-Quill-Elemente definiert. Es könnte auch Stile für benutzerdefinierte Blots (z.B. Tabellen, Schaltflächen) enthalten, wenn sie innerhalb des Editors gerendert werden.
-   `views/css/myquill-front.css`
    *   **Geltungsbereich**: Front-Office-Kunden-Styling.
    *   **Details**: Dieses Stylesheet wird bedingt im Front Office geladen, wenn die entsprechende Einstellung aktiviert ist. Es stellt das notwendige CSS bereit, um mit MyQuill erstellte interaktive Elemente (wie Tabs, Akkordeons, Galerien) im kundenorientierten Shop korrekt darzustellen. Entwickler können diese Stile in der `custom.css` oder `theme.css` ihres Themes überschreiben, um sie an ihr Branding anzupassen.
-   `views/css/quill.snow.css`
    *   **Geltungsbereich**: Back-Office-Admin-Formular-Styling.
    *   **Details**: Dies ist das Standard-Stylesheet des "Snow"-Themes für Quill.js. Es bietet das Standard-Erscheinungsbild für die Toolbar und den Inhaltsbereich des Quill-Editors, einschließlich Icons, Schaltflächenstilen und grundlegender Formatierung. Dies ist eine Kernkomponente von Quill.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    *   `bo-header.tpl`
        *   **Hook**: `displayBackOfficeHeader`
        *   **Ausgabe**: Dieses Template ist dafür verantwortlich, die notwendigen CSS- und JavaScript-Assets (Quill-Core, modulspezifisches JS/CSS) in den `<head>`-Bereich der Back-Office-Seiten zu injizieren, wo der Editor benötigt wird. Es bindet Dateien dynamisch basierend auf der Modulkonfiguration ein.
-   **Admin-Templates (`views/templates/admin/`)**:
    *   `configure.tpl`
        *   **Ausgabe**: Dieses Template rendert das Hauptkonfigurationsformular für das MyQuill-Modul, zugänglich über **Module > Modul-Manager > Konfigurieren**. Es zeigt alle in Abschnitt 4.1 beschriebenen Einstellungen an, einschließlich Schaltern, Eingabefeldern und der Schaltfläche "Speichern".
    *   `preview.tpl`
        *   **Ausgabe**: Dieses Template könnte für eine Vorschaufunktion innerhalb des Back Office verwendet werden, die möglicherweise zeigt, wie Quill-generierte Inhalte im Frontend aussehen würden. Die genaue Verwendung hängt von der internen Implementierung des Moduls zur Vorschau von Inhalten ab.

-   **Front-Office-Templates (`views/templates/front/`)**:
    Das Modul enthält keine dedizierten Front-Office-Templates. Alle von Quill generierten Inhalte werden innerhalb bestehender PrestaShop-Theme-Templates (z.B. `product.tpl`, `cms.tpl`) gerendert, indem der rohe HTML-Output des Editors eingefügt wird.

### 4.7 Datenbank-Schema & Hooks-Map

-   **Datenbanktabellen**:
    Das MyQuill-Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die typischerweise mit `MYQUILL_` präfixiert sind. Mit dem Editor erstellte Inhalte werden in Standard-PrestaShop-Inhaltstabellen (z.B. `ps_product_lang`, `ps_cms_lang`) gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayBackOfficeHeader` | Wird im `<head>` von Back-Office-Seiten ausgeführt. | Injiziert MyQuills CSS- und JavaScript-Assets (Quill-Editor, Plugins, Admin-Stile) in das Back Office, um den Editor zu initialisieren. |
| `displayHeader` | Wird im `<head>` von Front-Office-Seiten ausgeführt. | Injiziert bedingt MyQuills Front-Office-CSS- und JavaScript-Assets, wenn "Quill Editor im Front Office laden" aktiviert ist, um sicherzustellen, dass interaktive Elemente (Tabs, Akkordeons) korrekt funktionieren. |
| `displayFooter` | Wird am Ende des `<body>` von Front-Office-Seiten ausgeführt. | Potenziell zum Injizieren von spät ladenden Skripten oder zusätzlichen Ressourcen für interaktive Front-Office-Elemente verwendet, falls nicht durch `displayHeader` behandelt. |
| `displayProductExtraContent` | Wird auf der Produktseite ausgeführt. | Ermöglicht das Injizieren zusätzlicher Inhaltsblöcke auf der Produktseite, potenziell nützlich für benutzerdefinierte Quill-generierte Inhalte, wenn das Modul erweitert würde, um solche Blöcke direkt zu verwalten. (Weniger wahrscheinlich direkt von MyQuills Kern-Editor-Ersatzfunktion verwendet, aber für Erweiterungen verfügbar). |
| `displayLeftColumn` | Wird in der linken Spalte von Front-Office-Seiten ausgeführt. | Ähnlich wie `displayProductExtraContent` bietet einen Hook zum Injizieren von Inhalten in die linke Spalte. |
| `displayRightColumn` | Wird in der rechten Spalte von Front-Office-Seiten ausgeführt. | Ähnlich wie `displayProductExtraContent` bietet einen Hook zum Injizieren von Inhalten in die rechte Spalte. |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul MyQuill - Quill Editor besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Sie können die neuesten Versionen aus Ihrer Bestellhistorie herunterladen und direkt auf der MyPresta.eu-Website auf Support-Ressourcen zugreifen.
