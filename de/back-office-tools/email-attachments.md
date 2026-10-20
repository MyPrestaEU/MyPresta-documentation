---
title: "E-Mail-Anhänge – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „E-Mail-Anhänge“ von MyPresta.eu."
sidebar:
  label: "E-Mail-Anhänge – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Email attachments auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/email-attachments.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/email-attachments/)
>
> ---


# E-Mail-Anhänge

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „E-Mail-Anhänge“ bietet einen unkomplizierten Konfigurationsprozess, hauptsächlich über einen dedizierten Administrationsbildschirm, auf dem Sie Ihre Anhänge verwalten und mit bestimmten E-Mail-Vorlagen verknüpfen.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Wenn Sie nach der Installation zum ersten Mal auf „Konfigurieren“ klicken, gelangen Sie zur Hauptkonfigurationsseite des Moduls. Diese Seite dient hauptsächlich als Einstiegspunkt und kann allgemeine Informationen oder einen Link zum dedizierten Anhangsverwaltungsbildschirm enthalten.

-   **Was dieser Bildschirm bewirkt:** Dieser anfängliche Bildschirm bietet einen kurzen Überblick über das Modul und leitet Sie in der Regel zur Hauptschnittstelle für die Verwaltung von E-Mail-Anhängen weiter. Er könnte auch allgemeine Einstellungen enthalten, falls das Modul welche hätte, aber für dieses Modul wird die Kernfunktionalität in einem separaten Admin-Controller verwaltet.
-   **Auswirkung der Änderung von Einstellungen:** Alle hier vorgenommenen Einstellungen würden das allgemeine Verhalten des Moduls beeinflussen. Für „E-Mail-Anhänge“ besteht die primäre Aktion jedoch darin, zur dedizierten Verwaltungsseite „E-Mail-Anhänge“ zu navigieren.
-   **Empfohlener Wert:** Befolgen Sie die Anweisungen auf dem Bildschirm, die normalerweise das Klicken auf eine Schaltfläche oder einen Link beinhalten, um zum Bereich der Anhangsverwaltung zu gelangen.

### 2.2 Dedizierter Admin-Bildschirm: E-Mail-Anhänge (Back Office > Module > E-Mail-Anhänge)

Dies ist die zentrale Anlaufstelle für die Verwaltung all Ihrer E-Mail-Anhänge. Sie finden in der Regel einen neuen Menüpunkt unter **Module** oder **Shop-Parameter** (abhängig von Ihrer PrestaShop-Version und dem Design des Moduls) mit dem Namen „E-Mail-Anhänge“ oder ähnlich.

**Menüpfad:** Back Office > Module > E-Mail-Anhänge (oder ähnlich, überprüfen Sie Ihr Admin-Menü nach der Installation)

#### Übersicht über den Verwaltungsbildschirm „E-Mail-Anhänge“

Dieser Bildschirm zeigt eine Liste (ein „Raster“ oder eine „Tabelle“) aller von Ihnen konfigurierten E-Mail-Anhänge an. Von hier aus können Sie:

-   **Neuen Anhang hinzufügen:** Eine neue Anhangsregel erstellen.
-   **Bestehenden Anhang bearbeiten:** Die Einstellungen für einen bereits erstellten Anhang ändern.
-   **Anhang löschen:** Eine Anhangsregel entfernen.

#### Hinzufügen/Bearbeiten eines E-Mail-Anhangs

Wenn Sie auf „Neuen Anhang hinzufügen“ klicken oder einen bestehenden „Bearbeiten“, wird Ihnen ein Formular zur Definition der Eigenschaften des Anhangs angezeigt.

**Formularfelder & Optionen:**

1.  **Anhangsname:**
    *   **Was diese Einstellung bewirkt:** Dies ist ein interner Name für Ihre Referenz im Back Office. Er hilft Ihnen, die Anhangsregel leicht zu identifizieren.
    *   **Auswirkung der Änderung dieser Einstellung:** Ändert nur die Bezeichnung, die Sie in der Admin-Liste sehen. Sie beeinflusst nicht den Dateinamen, den der Kunde sieht.
    *   **Empfohlener Wert:** Ein aussagekräftiger Name, z. B. „Willkommensleitfaden PDF“, „Bestellbestätigung AGB“, „Produkthandbuch für neue Bestellungen“.
    *   **Händlerszenario:** Sie haben mehrere Anhänge für verschiedene Zwecke; ein klarer Name hilft Ihnen, sie zu unterscheiden.
2.  **E-Mail-Vorlage(n) auswählen:**
    *   **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung bestimmt, *welchen* PrestaShop-E-Mails dieser Anhang hinzugefügt wird. Sie sehen in der Regel eine Liste aller Standard-PrestaShop-E-Mail-Vorlagen (z. B. `account`, `order_conf`, `shipped`, `contact_form`). Sie können eine oder mehrere Vorlagen auswählen.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn ausgewählt:* Der Anhang wird in jede E-Mail aufgenommen, die mit der/den ausgewählten Vorlage(n) gesendet wird.
        *   *Wenn nicht ausgewählt:* Der Anhang wird nicht in E-Mails aufgenommen, die diese Vorlage verwenden.
    *   **Empfohlener Wert:** Wählen Sie nur die relevanten E-Mail-Vorlagen aus. Zum Beispiel sollte ein „Willkommensleitfaden“ nur an die `account`-E-Mail (Kundenkontoerstellung) angehängt werden.
    *   **Händlerszenario:** Sie möchten eine PDF-Datei mit den „Rückgaberichtlinien“ an `order_conf` (Bestellbestätigung) und `shipped` (Versandbenachrichtigung) E-Mails anhängen.
3.  **Anhangstyp:**
    *   **Was diese Einstellung bewirkt:** Dies definiert die Quelle Ihrer Anhangsdatei. Das Modul bietet verschiedene Optionen:
        *   **Datei hochladen:** Eine vorhandene Datei von Ihrem Computer anhängen.
        *   **PDF aus CMS-Seite generieren:** Eine PDF aus einer Ihrer vorhandenen PrestaShop-CMS-Seiten erstellen.
        *   **PDF aus Rich-Text-Editor erstellen:** Benutzerdefinierte PDF-Inhalte direkt im Modul mit einem visuellen Editor gestalten.
    *   **Auswirkung der Änderung dieser Einstellung:** Bestimmt die nächsten Optionen, die Sie zur Angabe des Anhangsinhalts sehen werden.
    *   **Empfohlener Wert:** Wählen Sie den Typ, der am besten zu Ihrer Inhaltsquelle passt.
    *   **Händlerszenario:** Sie haben eine vorgefertigte „Garantie.pdf“ (Datei hochladen), oder Sie möchten Ihre CMS-Seite „Über uns“ in eine PDF umwandeln (PDF aus CMS-Seite generieren), oder Sie müssen eine benutzerdefinierte „Sonderangebot“-PDF schreiben (PDF aus Rich-Text-Editor erstellen).

    **Unter-Einstellungen basierend auf dem Anhangstyp:**

    *   **Wenn „Datei hochladen“ ausgewählt ist:**
        *   **Dateiupload-Feld:**
            *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Ihren Computer zu durchsuchen und eine Datei (z. B. PDF, JPG, DOCX) hochzuladen.
            *   **Auswirkung der Änderung dieser Einstellung:** Die ausgewählte Datei wird auf Ihrem Server gespeichert und als Anhang verwendet.
            *   **Empfohlener Wert:** Laden Sie eine Datei hoch, die nicht übermäßig groß ist, um Probleme bei der E-Mail-Zustellung zu vermeiden. PDFs werden im Allgemeinen für Dokumente bevorzugt.
            *   **Händlerszenario:** Anfügen der PDF-Datei „Allgemeine Geschäftsbedingungen“ Ihres Unternehmens.
    *   **Wenn „PDF aus CMS-Seite generieren“ ausgewählt ist:**
        *   **CMS-Seite auswählen:**
            *   **Was diese Einstellung bewirkt:** Bietet eine Dropdown-Liste aller Ihrer aktiven PrestaShop-CMS-Seiten.
            *   **Auswirkung der Änderung dieser Einstellung:** Der Inhalt der ausgewählten CMS-Seite wird in eine PDF umgewandelt und angehängt.
            *   **Empfohlener Wert:** Wählen Sie eine CMS-Seite mit Inhalten, die für ein PDF-Dokument geeignet sind (z. B. „Über uns“, „Datenschutzrichtlinie“).
            *   **Händlerszenario:** Automatisches Anfügen Ihrer CMS-Seite „Rückgaberichtlinien“ als PDF an relevante E-Mails.
    *   **Wenn „PDF aus Rich-Text-Editor erstellen“ ausgewählt ist:**
        *   **Rich-Text-Editor (WYSIWYG):**
            *   **Was diese Einstellung bewirkt:** Ein visueller Editor, in dem Sie benutzerdefinierte Inhalte eingeben und formatieren, Bilder, Links usw. hinzufügen können. Dieser Inhalt wird dann in eine PDF umgewandelt.
            *   **Auswirkung der Änderung dieser Einstellung:** Der hier erstellte Inhalt bildet den Hauptteil der angehängten PDF.
            *   **Empfohlener Wert:** Verwenden Sie dies für dynamische oder einzigartige Inhalte, die nicht als Datei oder CMS-Seite existieren. Halten Sie das Design einfach, um die besten PDF-Konvertierungsergebnisse zu erzielen.
            *   **Händlerszenario:** Erstellen einer benutzerdefinierten „Dankeschön“-Nachricht mit einem Rabattcode als PDF-Anhang.
4.  **Anhangsdateiname (wie vom Kunden gesehen):**
    *   **Was diese Einstellung bewirkt:** Dies ist der Name der Datei, den der Kunde in seinem E-Mail-Client sieht, wenn er den Anhang erhält.
    *   **Auswirkung der Änderung dieser Einstellung:** Ändert, wie die Datei im Posteingang des Kunden erscheint.
    *   **Empfohlener Wert:** Ein klarer, beschreibender und professioneller Dateiname (z. B. `Ihre-Bestellbestaetigung.pdf`, `Garantie-Informationen.pdf`). Fügen Sie die Dateierweiterung hinzu (z. B. `.pdf`).
    *   **Händlerszenario:** Sie haben `my_internal_doc_v2.pdf` hochgeladen, möchten aber, dass der Kunde `Produkt-Leitfaden.pdf` sieht.
5.  **Aktiv:**
    *   **Was diese Einstellung bewirkt:** Ein einfacher EIN/AUS-Schalter zum Aktivieren oder Deaktivieren dieser spezifischen Anhangsregel.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Die Anhangsregel ist aktiv und wird auf ausgewählte E-Mails angewendet.
        *   *Wenn deaktiviert:* Die Anhangsregel ist inaktiv und fügt keine Dateien zu E-Mails hinzu.
    *   **Empfohlener Wert:** Auf „JA“ setzen, wenn der Anhang gesendet werden soll.
    *   **Händlerszenario:** Sie testen einen Anhang und möchten ihn vorübergehend deaktivieren, ohne die Konfiguration zu löschen.

#### 2.2.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :-------------------- | :------------------- | :------------------- | :----------------- |
| **E-Mail-Anhänge (Admin-Controller)** | Anhangsname | Beschreibender Text | Interne Bezeichnung zur einfachen Identifizierung im BO. |
| | E-Mail-Vorlage(n) auswählen | Spezifische Vorlagen (z. B. `order_conf`) | Bestimmt, welche E-Mails den Anhang erhalten. |
| | Anhangstyp | Variiert (Datei hochladen, CMS-Seite, Rich Text) | Definiert die Quelle des Anhangsinhalts. |
| | *Wenn Datei hochladen:* Dateiupload-Feld | N/A | Lädt eine vorhandene Datei von Ihrem Computer hoch. |
| | *Wenn PDF aus CMS-Seite generieren:* CMS-Seite auswählen | Spezifische CMS-Seite | Konvertiert den Inhalt der ausgewählten CMS-Seite in PDF. |
| | *Wenn PDF aus Rich-Text-Editor erstellen:* Rich-Text-Editor | Benutzerdefinierter Inhalt | Erstellt eine PDF aus dem im Editor eingegebenen Inhalt. |
| | Anhangsdateiname | Beschreibender Dateiname (z. B. `dokument.pdf`) | Der Name, den Kunden in ihrem E-Mail-Client sehen. |
| | Aktiv | JA | Aktiviert/deaktiviert die Anhangsregel. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Meine Anhänge werden nicht gesendet, oder Kunden berichten, sie nicht zu erhalten.**

-   **A:** Überprüfen Sie zunächst, ob die Anhangsregel in der Modulkonfiguration „Aktiv“ ist.
-   **A:** Stellen Sie sicher, dass Sie die richtigen E-Mail-Vorlage(n) für den Anhang ausgewählt haben. Testen Sie dies, indem Sie selbst eine dieser E-Mails auslösen (z. B. eine Testbestellung aufgeben, ein neues Kundenkonto erstellen).
-   **A:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen (Shop-Parameter > E-Mail), um sicherzustellen, dass E-Mails generell korrekt gesendet werden. Versuchen Sie, eine Test-E-Mail von PrestaShop zu senden.
-   **A:** Die Anhangsdatei ist möglicherweise zu groß, was dazu führt, dass E-Mail-Anbieter die E-Mail ablehnen. Versuchen Sie eine kleinere Dateigröße.
-   **A:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren).

**F2: Die aus meiner CMS-Seite generierte PDF sieht seltsam aus oder hat Formatierungsprobleme.**

-   **A:** Die PDF-Generierung aus HTML kann manchmal knifflig sein. Stellen Sie sicher, dass der Inhalt Ihrer CMS-Seite sauberes HTML ohne komplexe JavaScript- oder hochdynamische Elemente ist.
-   **A:** Versuchen Sie, das Layout Ihrer CMS-Seite zu vereinfachen. Vermeiden Sie übermäßig komplexe CSS oder sehr breite Bilder, die möglicherweise nicht gut auf eine Standard-PDF-Seite passen.
-   **A:** Wenn Probleme weiterhin bestehen, ziehen Sie in Betracht, eine dedizierte PDF-Datei extern zu erstellen und stattdessen die Option „Datei hochladen“ zu verwenden.

**F3: Kann ich verschiedene Dateien basierend auf dem bestellten Produkt oder der Kundengruppe anhängen?**

-   **A:** Dieses Modul hängt in seiner Standardkonfiguration Dateien an *alle* E-Mails eines ausgewählten Typs an, unabhängig von einem bestimmten Produkt oder einer Kundengruppe. Für fortgeschrittenere, bedingte Anhänge ist möglicherweise eine kundenspezifische Entwicklung oder ein spezialisierteres Modul erforderlich.

**F4: Wie übersetze ich den Inhalt einer mit dem Rich-Text-Editor erstellten PDF für verschiedene Sprachen?**

-   **A:** Wenn Sie den Rich-Text-Editor verwenden, sollten Sie Sprachregisterkarten (z. B. Deutsch, Englisch, Französisch) sehen, wenn Ihr PrestaShop-Shop mehrere Sprachen unterstützt. Sie müssen den Inhalt für jede Sprache separat im Editor eingeben und formatieren. Das Modul hängt dann die korrekte Sprachversion basierend auf der vom Kunden ausgewählten Sprache an.

**F5: Wo werden die hochgeladenen Dateien auf meinem Server gespeichert?**

-   **A:** Hochgeladene Dateien werden typischerweise im Verzeichnis des Moduls oder in einem dafür vorgesehenen Upload-Ordner innerhalb des Moduls gespeichert. Sie müssen in der Regel nicht direkt über FTP mit diesen Dateien interagieren, da das Modul sie verwaltet.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „E-Mail-Anhänge“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „E-Mail-Anhänge“ (`mattach`) erweitert die Kern-E-Mail-Funktionalität von PrestaShop, indem es die Klasse `Mail` überschreibt. Dies ermöglicht es, benutzerdefinierte Anhänge in ausgehende E-Mails einzufügen, ohne Kerndateien direkt zu ändern. Es folgt einem Standard-PrestaShop-MVC-Muster für seine Back-Office-Verwaltungsoberfläche und verwendet einen `AdminController` zur Verwaltung von `mailfile`-Entitäten, die die Anhangskonfigurationen darstellen. Die PDF-Generierung wird intern gehandhabt, entweder durch Konvertierung von CMS-Inhalten oder Rich-Text-Editor-Eingaben.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    *   Dieses Modul enthält **keine** dedizierten Front-Office-Controller. Alle Operationen werden im Back Office oder durch Überschreiben von Kernklassen während des E-Mail-Versands durchgeführt.
-   **Back-Office-Admin-Controller**:
    *   `mattach/controllers/admin/AdminMailAttachments.php`
        *   **Klassenname**: `AdminMailAttachmentsController`
        *   **Elternklasse**: `ModuleAdminController`
        *   **Verantwortlichkeit**: Dies ist der primäre Controller für die Verwaltung von E-Mail-Anhangsregeln. Er verarbeitet die CRUD-Operationen (Create, Read, Update, Delete) für die `mailfile`-Entität. Er zeigt eine Liste der konfigurierten Anhänge an, bietet Formulare zum Hinzufügen/Bearbeiten und verwaltet Dateiuploads, CMS-Seitenauswahl und Rich-Text-Editor-Inhalte für die PDF-Generierung. Er verwendet PrestaShops `HelperList` für die Rasteransicht und `HelperForm` für die Hinzufügen/Bearbeiten-Formulare.
        *   **Verwaltete Tabelle / Entität**: `mailfile` (benutzerdefinierte Tabelle für Moduldaten).
        *   **Zugehörige Konfigurationsschlüssel**: `PS_LANG_DEFAULT` (wird für mehrsprachige Felder verwendet).
    *   `mattach/controllers/admin/index.php`
        *   **Klassenname**: (Keine explizite Klasse, typischerweise ein Platzhalter oder eine Weiterleitung)
        *   **Verantwortlichkeit**: Diese Datei ist oft eine Sicherheitsmaßnahme (um direkte Verzeichnisauflistungen zu verhindern) oder eine einfache Weiterleitung innerhalb der PrestaShop-Admin-Struktur. Sie enthält keine aktive Controller-Logik für die Funktionalität des Moduls.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `mattach/override/classes/index.php`
    *   **Verantwortlichkeit**: Standard-PrestaShop-Sicherheitsdatei zur Verhinderung von Verzeichnisauflistungen.
-   `mattach/override/classes/Mail.php`
    *   **Klassenname**: `Mail` (überschreibt PrestaShops Kernklasse `Mail`)
    *   **Elternklasse**: `MailCore`
    *   **Verantwortlichkeit**: Dies ist der kritischste Teil der Modulfunktionalität. Durch das Überschreiben der Klasse `Mail` fängt das Modul die Methode `send()` ab. Innerhalb der überschriebenen `send()`-Methode prüft es, ob Anhangsregeln für die spezifische E-Mail-Vorlage konfiguriert sind, die gesendet wird. Wenn Übereinstimmungen gefunden werden, ruft es die Anhangsdaten ab (hochgeladener Dateipfad, generierter PDF-Inhalt), erstellt die notwendigen `Swift_Attachment`-Objekte und fügt sie der E-Mail hinzu, bevor diese versendet wird. Dies stellt sicher, dass Anhänge nahtlos in alle relevanten ausgehenden E-Mails aufgenommen werden.
    *   **Datenbankinteraktion**: Interagiert mit der benutzerdefinierten `mailfile`-Tabelle des Moduls, um Anhangskonfigurationen abzurufen.
    *   **Wichtige öffentliche Methoden**: Überschreibt `send()`, um die Anhangslogik einzufügen.

### 4.4 JavaScript-Assets (`views/js/`)

-   `mattach/views/templates/admin/js/mattach.js`
    *   **Geltungsbereich**: Back-Office (`AdminMailAttachmentsController`).
    *   **Funktionalität**: Dieses Skript verarbeitet wahrscheinlich das dynamische Verhalten des Anhangskonfigurationsformulars. Dies könnte Folgendes umfassen:
        *   Anzeigen/Ausblenden spezifischer Eingabefelder basierend auf dem ausgewählten „Anhangstyp“ (z. B. Anzeige des Dateiupload-Feldes nur, wenn „Datei hochladen“ ausgewählt ist).
        *   AJAX-Aufrufe zum Abrufen von CMS-Seitenlisten oder anderen dynamischen Daten.
        *   Initialisierung des Rich-Text-Editors (z. B. TinyMCE oder CKEditor) für die Option „PDF aus Rich-Text-Editor erstellen“.
        *   Clientseitige Validierung oder UI-Verbesserungen für die Anhangsverwaltungsoberfläche.

### 4.5 CSS-Stylesheets (`views/css/`)

-   Dieses Modul scheint **keine** benutzerdefinierten CSS-Dateien im bereitgestellten Inventar zu enthalten. Es verlässt sich wahrscheinlich auf die Standard-Back-Office-Stile von PrestaShop für seine Konfigurationsformulare und Listen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

-   **Hook-Vorlagen (`views/templates/hook/`)**:
    *   Dieses Modul enthält **keine** spezifischen Hook-Vorlagen im bereitgestellten Inventar. Sein Front-Office-Einfluss erfolgt ausschließlich über E-Mail-Anhänge, nicht über visuelle Elemente.
-   **Admin-Vorlagen (`views/templates/admin/`)**:
    *   `mattach/views/templates/admin/orderstates.tpl`
        *   **Zweck**: Der Name dieser Vorlage deutet darauf hin, dass sie zur Anzeige oder Verwaltung von Bestellstatus in Bezug auf Anhänge verwendet werden könnte, oder vielleicht zur Auswahl von Bestellstatus für bedingte Anhänge (obwohl die Modulbeschreibung diese erweiterte Funktion nicht explizit erwähnt). Sie könnte Teil des `AdminMailAttachmentsController`-Formulars sein, möglicherweise zur Auswahl, welche Bestellstatusänderungen eine E-Mail mit einem Anhang auslösen.
    *   `mattach/lib/searchTool/views/scripts.tpl`
        *   **Zweck**: Diese Vorlage enthält wahrscheinlich JavaScript- oder Smarty-Logik, die sich auf ein Such- oder Filterwerkzeug bezieht, das innerhalb der Admin-Oberfläche verwendet wird, möglicherweise zum Durchsuchen von E-Mail-Vorlagen oder CMS-Seiten. Es handelt sich um eine Dienstprogrammvorlage zur Verbesserung der Admin-Benutzeroberfläche.
-   **Front-Office-Vorlagen (`views/templates/front/`)**:
    *   Dieses Modul enthält **keine** Front-Office-Vorlagen.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   `ps_mailfile`: Dies ist die primäre benutzerdefinierte Tabelle, die vom Modul erstellt wird, um jede E-Mail-Anhangskonfiguration zu speichern.
        *   `id_mailfile`: Primärschlüssel.
        *   `name`: Interner Name der Anhangsregel.
        *   `file_name`: Der tatsächliche Dateiname (oder generierte Name) des Anhangs.
        *   `file_path`: Pfad zur hochgeladenen Datei oder wo die generierte PDF temporär gespeichert wird.
        *   `file_type`: Typ des Anhangs (z. B. „upload“, „cms“, „editor“).
        *   `id_cms`: Wenn `file_type` „cms“ ist, speichert die ID der CMS-Seite.
        *   `content`: Wenn `file_type` „editor“ ist, speichert den Rich-Text-Inhalt (mehrsprachig).
        *   `mail_templates`: Ein serialisiertes Array oder eine durch Kommas getrennte Zeichenfolge von E-Mail-Vorlagennamen (z. B. `account`, `order_conf`), auf die dieser Anhang angewendet wird.
        *   `active`: Boolescher Wert (0 oder 1), der angibt, ob die Anhangsregel aktiv ist.
    *   `ps_mailfile_lang`: Begleittabelle für mehrsprachige Felder wie `content` (wenn `file_type` „editor“ ist).
        *   `id_mailfile`: Fremdschlüssel zu `ps_mailfile`.
        *   `id_lang`: Sprach-ID.
        *   `content`: Übersetzter Rich-Text-Inhalt.
-   **Registrierte Hooks-Tabelle**:
    *   Das Modul arbeitet hauptsächlich durch Überschreiben der Kernklasse `Mail`, was eine direktere und leistungsfähigere Methode ist, als sich ausschließlich auf Hooks für die E-Mail-Modifikation zu verlassen. Obwohl es einige Standard-Hooks für die Modulinstallation/-deinstallation oder die Back-Office-Menüintegration registrieren könnte, befindet sich seine Kernlogik zur Anhangsinjektion im `Mail`-Override.
    *   **`install()`-Methode**:
        *   Registriert das Modul im Back-Office-Menü.
        *   Erstellt die Datenbanktabellen `ps_mailfile` und `ps_mailfile_lang`.
        *   Installiert den `Mail`-Klassen-Override.
    *   **`uninstall()`-Methode**:
        *   Entfernt das Modul aus dem Back-Office-Menü.
        *   Löscht die Datenbanktabellen `ps_mailfile` und `ps_mailfile_lang`.
        *   Deinstalliert den `Mail`-Klassen-Override.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „E-Mail-Anhänge“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
