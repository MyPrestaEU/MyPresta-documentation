---
title: "Bestell-PDF-Export & Lager-Checkliste – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bestell-PDF-Export & Lager-Checkliste“ von MyPresta.eu."
sidebar:
  label: "Bestell-PDF-Export & Lager-Checkliste – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Order PDF Export & Warehouse Checklist auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/order-pdf-export-warehouse-checklist.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/order-pdf-export-warehouse-checklist/)
>
> ---


# Bestell-PDF-Export & Lager-Checkliste

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Um auf diesen Bildschirm zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Bestell-PDF-Export & Lager-Checkliste“ und klicken Sie auf „Konfigurieren“.

#### **PDF-Vorlage**

- **Was diese Einstellung bewirkt:** Hiermit können Sie das visuelle Design und Layout für die vom Modul generierten PDF-Dokumente auswählen. Sie können aus einer Vielzahl von vorgefertigten Vorlagen wählen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Clean“ eingestellt:* Ihre PDFs erhalten ein minimalistisches, modernes Aussehen.
  - *Wenn auf „Warehouse Big“ eingestellt:* Das PDF wird für den Lagergebrauch optimiert, möglicherweise mit größeren Schriftarten und klaren Abschnitten für die Kommissionierung.
  - *Wenn auf „Retro“ eingestellt:* Ihre PDFs erhalten ein Vintage-inspiriertes Design.
- **Empfohlener Wert:** Beginnen Sie mit „Clean“ oder „Warehouse Big“, je nach Ihrem primären Anwendungsfall (Kunden-Lieferschein vs. interne Kommissionierliste). Experimentieren Sie, um die beste Passform für Ihre Marke und Ihre betrieblichen Anforderungen zu finden.
- **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Ihre Lieferscheine ein modernes, professionelles Markenimage widerspiegeln, könnten Sie „Clean“ oder „Elegant Serif“ wählen. Wenn Ihr Hauptziel darin besteht, dem Lagerpersonal eine gut lesbare Kommissionierliste zur Verfügung zu stellen, könnte „Warehouse Big“ besser geeignet sein.

#### **MyPresta.eu-Updates aktivieren** (mypresta\_updates)

- **Was diese Einstellung bewirkt:** Dies steuert, ob das Modul nach verfügbaren Updates von MyPresta.eu suchen und Sie darüber benachrichtigen kann.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (Ja):* Das Modul sucht regelmäßig nach neuen Versionen, um sicherzustellen, dass Sie mit den neuesten Funktionen, Fehlerbehebungen und Kompatibilitätsverbesserungen auf dem Laufenden bleiben. Möglicherweise sehen Sie Benachrichtigungen in Ihrem PrestaShop Back Office, wenn ein Update verfügbar ist.
  - *Wenn deaktiviert (Nein):* Das Modul sucht nicht nach Updates. Sie müssen manuell in Ihrem MyPresta.eu-Konto nach neuen Versionen suchen.
- **Empfohlener Wert:** **Ja**. Das Aktualisieren von Modulen ist entscheidend für Sicherheit, Leistung und Kompatibilität mit neuen PrestaShop-Versionen.
- **Händlerszenario / Beispiel:** Die Aktivierung stellt sicher, dass Sie immer die stabilste und funktionsreichste Version des Moduls verwenden, ohne ständig manuell nachsehen zu müssen.

#### **Update-Version** (update\_) & **Update-Versionswert** (updatev\_)

- **Was diese Einstellungen bewirken:** Dies sind interne Einstellungen, die vom Modul zur Verwaltung seines Update-Mechanismus verwendet werden. Sie speichern Informationen über die neueste verfügbare Version oder die aktuell installierte Version.
- **Auswirkung der Änderung dieser Einstellung:** Diese sind **nicht dazu gedacht, manuell** vom Händler geändert zu werden. Eine Änderung könnte die Fähigkeit des Moduls beeinträchtigen, Updates korrekt zu überprüfen und anzuwenden.
- **Empfohlener Wert:** Belassen Sie diese Einstellungen, wie sie sind. Sie werden automatisch vom Modul verwaltet.
- **Händlerszenario / Beispiel:** Sie werden normalerweise nicht mit diesen Einstellungen interagieren. Sie sind Teil der internen Update-Logik des Moduls.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul fügt neue Menüpunkte unter **Bestellungen** in Ihrem PrestaShop Back Office hinzu, mit denen Sie Ihre Lager-Checklistenkategorien und -elemente verwalten können.

#### **Bildschirmname: Checklistenkategorien**

- **Menüpfad:** Back Office > Bestellungen > **Checklistenkategorien**
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm ermöglicht es Ihnen, Kategorien für Ihre Lager-Checkliste zu erstellen, zu bearbeiten und zu löschen. Stellen Sie sich Kategorien als logische Gruppierungen für Ihre Checklistenpunkte vor (z. B. „Verpackungsqualität“, „Produktverifizierung“, „Versanddokumente“).
  - **Neue Kategorie hinzufügen:** Klicken Sie auf „Neue Kategorie hinzufügen“, um eine neue Gruppe zu definieren. Sie geben typischerweise einen Namen für die Kategorie an (z. B. „Produktprüfung“).
  - **Kategorien bearbeiten/löschen:** Sie können bestehende Kategorien ändern oder entfernen, wenn sie nicht mehr benötigt werden.
- **Auswirkung von Änderungen:**
  - *Hinzufügen einer Kategorie:* Erstellt einen neuen Abschnitt, unter dem Sie später spezifische Checklisten-Elemente hinzufügen können.
  - *Ändern einer Kategorie:* Ändert den Namen oder die Eigenschaften einer bestehenden Kategorie.
  - *Löschen einer Kategorie:* Entfernt die Kategorie und alle zugehörigen Checklisten-Elemente aus dem System. Diese werden nicht mehr auf Ihren generierten PDFs angezeigt.
- **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
  1. Beginnen Sie mit der Definition breiter Kategorien, die Ihren Lagerprozess widerspiegeln. Zum Beispiel: „Bestellgenauigkeit“, „Verpackungsintegrität“, „Dokumentation“.
  2. Stellen Sie sicher, dass die Kategorienamen für Ihr Personal klar und beschreibend sind.

#### **Bildschirmname: Checklisten-Elemente**

- **Menüpfad:** Back Office > Bestellungen > **Checklisten-Elemente**
- **Verfügbare Aktionen & Einstellungen:** Auf diesem Bildschirm definieren Sie die tatsächlichen Elemente, die auf Ihrer Lager-Checkliste im PDF erscheinen. Jedes Element kann einer zuvor von Ihnen erstellten Kategorie zugewiesen werden.
  - **Neues Element hinzufügen:** Klicken Sie auf „Neues Element hinzufügen“. Sie geben an:
    - **Name:** Der Text des Checklistenpunkts (z. B. „Alle Artikel vorhanden und berücksichtigt?“).
    - **Kategorie:** Weisen Sie es einer der von Ihnen definierten Kategorien zu (z. B. „Bestellgenauigkeit“).
    - **Aktiv:** Ob dieses Element auf der Checkliste erscheinen soll.
  - **Elemente bearbeiten/löschen:** Einzelne Checklistenpunkte ändern oder entfernen.
- **Auswirkung von Änderungen:**
  - *Hinzufügen eines Elements:* Das neue Element erscheint auf der generierten PDF-Checkliste unter seiner zugewiesenen Kategorie.
  - *Ändern eines Elements:* Ändert den Text oder die Kategorie eines bestehenden Checklistenpunkts.
  - *Löschen eines Elements:* Entfernt das Element von der Checkliste auf den PDFs.
- **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
  1. Sobald die Kategorien eingerichtet sind, füllen Sie diese mit spezifischen, umsetzbaren Checklistenpunkten.
  2. Beispiele: „Produktmenge stimmt mit Bestellung überein?“, „Zerbrechliche Artikel richtig gepolstert?“, „Versandetikett korrekt?“, „Rechnung enthalten?“.
  3. Überprüfen und aktualisieren Sie Ihre Checklisten-Elemente regelmäßig, um Änderungen an Ihren Produkten, Verpackungen oder Versandverfahren widerzuspiegeln.

#### **Bildschirmname: Bestellliste (mit Export-Button)**

- **Menüpfad:** Back Office > Bestellungen > **Bestellungen**
- **Verfügbare Aktionen & Einstellungen:** Dieses Modul integriert sich direkt in Ihre Standard-PrestaShop-Bestellliste. Sie finden neue Schaltflächen oder Optionen, um PDFs für einzelne Bestellungen oder potenziell in großen Mengen zu generieren.
  - **Einzelbestellungs-Export:** Wenn Sie eine bestimmte Bestellung im Back Office anzeigen, sehen Sie eine neue Schaltfläche (z. B. „PDF exportieren“ oder „Kommissionierliste drucken“), mit der Sie das angepasste PDF für diese Bestellung generieren können.
  - **Massenbestellungs-Export:** (Je nach Modulversion und PrestaShop-Version) Sie können möglicherweise mehrere Bestellungen aus der Bestellliste auswählen und PDFs für alle gleichzeitig generieren.
- **Auswirkung von Änderungen:** Durch Klicken auf diese Schaltflächen wird ein PDF-Dokument auf Ihren Computer heruntergeladen, das gemäß Ihrer gewählten Vorlage formatiert ist und Ihre benutzerdefinierte Checkliste enthält.
- **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
  1. Nachdem eine Bestellung aufgegeben und validiert wurde, navigieren Sie zur Bestellliste.
  2. Öffnen Sie die spezifische Bestellung, die Sie ausführen müssen.
  3. Klicken Sie auf die Schaltfläche „PDF exportieren“, um die Kommissionierliste/den Lieferschein mit der Checkliste zu generieren.
  4. Drucken Sie das PDF aus und übergeben Sie es Ihrem Lagerpersonal zur Abwicklung.
  5. Das Personal verwendet das PDF, um Artikel zu kommissionieren, die Genauigkeit anhand der Checkliste zu überprüfen und möglicherweise Unterschriften vor dem Verpacken einzuholen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | PDF-Vorlage | Clean / Warehouse Big | Wählt das visuelle Layout und Design der generierten PDF-Dokumente aus. |
| **Modulkonfiguration** | MyPresta.eu-Updates aktivieren | Ja | Ermöglicht dem Modul, nach neuen Versionen zu suchen und darüber zu benachrichtigen. |
| **Checklistenkategorien** | Kategorie hinzufügen/bearbeiten/löschen | N/A | Verwaltet die logischen Gruppierungen für Ihre Lager-Checklistenpunkte. |
| **Checklisten-Elemente** | Element hinzufügen/bearbeiten/löschen | N/A | Definiert die spezifischen Elemente, die auf Ihrer Lager-Checkliste im PDF erscheinen. |
| **Bestellliste / Bestellansicht** | PDF exportieren Schaltfläche | N/A | Generiert ein PDF-Dokument für die ausgewählte(n) Bestellung(en) unter Verwendung der konfigurierten Vorlage und Checkliste. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Das PDF sieht seltsam aus oder hat Formatierungsprobleme. Was soll ich tun?**
A:

1. **Smarty-Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Leistung**. Scrollen Sie nach unten zu „Cache“ und klicken Sie auf „Cache leeren“. Manchmal können alte Vorlagendateien Anzeigeprobleme verursachen.
2. **Versuchen Sie eine andere PDF-Vorlage:** Wählen Sie in der Modulkonfiguration eine andere „PDF-Vorlage“ aus, um zu sehen, ob das Problem spezifisch für ein Layout ist.
3. **Auf Theme-Konflikte prüfen:** Wenn Sie ein stark angepasstes Theme verwenden, könnte es CSS oder JS enthalten, das stört. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (z. B. Classic) und testen Sie erneut. Wenn es funktioniert, benötigt Ihr Theme möglicherweise Anpassungen.
4. **Support kontaktieren:** Wenn Probleme weiterhin bestehen, sammeln Sie Screenshots und Details und kontaktieren Sie dann den MyPresta.eu-Support.

**F: Meine benutzerdefinierten Checklistenpunkte erscheinen nicht auf dem PDF.**
A:

1. **„Checklistenkategorien“ überprüfen:** Stellen Sie sicher, dass Sie Kategorien unter **Bestellungen > Checklistenkategorien** erstellt haben.
2. **„Checklisten-Elemente“ überprüfen:** Vergewissern Sie sich, dass Sie Elemente unter **Bestellungen > Checklisten-Elemente** hinzugefügt haben und dass diese einer aktiven Kategorie zugewiesen sind. Stellen Sie außerdem sicher, dass der Schalter „Aktiv“ für jedes Element auf „Ja“ steht.
3. **Modulkonfiguration:** Stellen Sie sicher, dass das Modul ordnungsgemäß konfiguriert und gespeichert ist.

**F: Ich sehe die Schaltfläche „PDF exportieren“ auf meinen Bestellseiten nicht.**
A:

1. **Modul installiert & aktiviert:** Überprüfen Sie nochmals, ob das Modul unter **Module > Modul-Manager** installiert und aktiviert ist.
2. **Berechtigungen:** Stellen Sie sicher, dass Ihr Mitarbeiterprofil die erforderlichen Berechtigungen zum Zugriff und zur Nutzung dieses Moduls besitzt. Gehen Sie zu **Erweiterte Parameter > Team > Profile** und überprüfen Sie die Berechtigungen für das Ihrem Mitarbeiterkonto zugewiesene Profil.
3. **PrestaShop-Version:** Bestätigen Sie, dass Ihre PrestaShop-Version kompatibel ist (1.7.x, 8.x, 9.x).
4. **Cache leeren:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung**).

**F: Kann ich die PDF-Vorlagen weiter anpassen (z. B. mein Logo hinzufügen, Schriftarten ändern)?**
A: Ja, dies erfordert jedoch technisches Wissen. Das Modul bietet mehrere Vorlagen, aber für tiefgreifende Anpassungen (wie das Hinzufügen Ihres spezifischen Logos, das Ändern von Schriftarten oder das Ändern des Layouts über die Modul-Einstellungen hinaus) müssten Sie:

1. **Die Vorlagendatei identifizieren:** Suchen Sie die `.tpl`-Datei für die gewählte PDF-Vorlage im Verzeichnis `pdf/en/` des Moduls.
2. **Die Vorlage bearbeiten:** Dies beinhaltet die Bearbeitung von Smarty-Vorlagencode und möglicherweise HTML/CSS. Dies ist eine Aufgabe für einen Webmaster oder Entwickler.
3. **Eine benutzerdefinierte Vorlage in Betracht ziehen:** Für signifikante Änderungen ist es oft besser, eine neue benutzerdefinierte Vorlage zu erstellen, anstatt die Kernmoduldateien zu ändern, um sicherzustellen, dass Ihre Änderungen bei Modul-Updates nicht überschrieben werden.

**F: Das Modul sucht nicht nach Updates.**
A:

1. **Update-Prüfung aktivieren:** Gehen Sie zur Konfigurationsseite des Moduls (**Module > Modul-Manager > Konfigurieren** für „Bestell-PDF-Export & Lager-Checkliste“) und stellen Sie sicher, dass „MyPresta.eu-Updates aktivieren“ auf „Ja“ eingestellt ist.
2. **Server-Konnektivität:** Stellen Sie sicher, dass Ihr Server ausgehenden Internetzugang hat, um eine Verbindung zu den Update-Servern von MyPresta.eu herzustellen. Dies kann die Überprüfung von Firewall-Einstellungen oder Proxy-Konfigurationen bei Ihrem Hosting-Anbieter beinhalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Bestell-PDF-Export & Lager-Checkliste“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller), wobei es hauptsächlich `Module` für seine Kernfunktionalität und `AdminController` für seine Back-Office-Verwaltungsbildschirme erweitert. Es nutzt `ObjectModel` zur Verwaltung benutzerdefinierter Datenbankentitäten (Checklistenkategorien und -elemente). Die PDF-Generierung wird von einer dedizierten Klasse (`OrderPdfGenerator`) gehandhabt, die Smarty-Vorlagen zum Rendern des PDF-Inhalts verwendet und wahrscheinlich eine Bibliothek wie Dompdf oder TCPDF integriert (obwohl die spezifische Bibliothek nicht explizit angegeben ist, deutet die `.tpl`-Struktur auf eine Rendering-Engine hin). Hooks werden verwendet, um die Funktionalität des Moduls in das PrestaShop Back Office zu integrieren, insbesondere zum Hinzufügen von PDF-Export-Schaltflächen zu Bestellseiten.

### 4.2 Controller (`controllers/`)

#### Back-Office Admin-Controller

- `orderexportpdf/controllers/admin/AdminOrderExportChecklistCategoriesController.php`

  - **Klassenname:** `AdminOrderExportChecklistCategoriesController`
  - **Elternklasse:** `ModuleAdminController`
  - **Verantwortlichkeit:** Verwaltet die CRUD-Operationen (Create, Read, Update, Delete) für `OrderExportChecklistCategory`-Objekte. Es bietet die Back-Office-Oberfläche zum Auflisten, Hinzufügen, Bearbeiten und Löschen von Checklistenkategorien. Dieser Controller ist dem Menüpunkt „Checklistenkategorien“ unter „Bestellungen“ zugeordnet.
  - **Tab-Name:** Checklistenkategorien
  - **Verwaltete Entität:** `OrderExportChecklistCategory` (zugeordnet zur Tabelle `ps_orderexport_checklist_cat`).
- `orderexportpdf/controllers/admin/AdminOrderExportChecklistElementsController.php`

  - **Klassenname:** `AdminOrderExportChecklistElementsController`
  - **Elternklasse:** `ModuleAdminController`
  - **Verantwortlichkeit:** Verwaltet die CRUD-Operationen für `OrderExportChecklistElement`-Objekte. Es bietet die Back-Office-Oberfläche zum Auflisten, Hinzufügen, Bearbeiten und Löschen einzelner Checklisten-Elemente, wobei die Zuweisung zu Kategorien möglich ist. Dieser Controller ist dem Menüpunkt „Checklisten-Elemente“ unter „Bestellungen“ zugeordnet.
  - **Tab-Name:** Checklisten-Elemente
  - **Verwaltete Entität:** `OrderExportChecklistElement` (zugeordnet zur Tabelle `ps_orderexport_checklist_elem`).
- `orderexportpdf/controllers/admin/index.php`

  - **Verantwortlichkeit:** Dies ist typischerweise eine leere Datei oder eine Datei, die eine Sicherheits-`die()`-Anweisung enthält, um direkte Verzeichnisauflistungen zu verhindern. Sie enthält selbst keine Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

- `orderexportpdf/classes/index.php`

  - **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsdatei, enthält normalerweise `<?php exit;` um Verzeichnisauflistungen zu verhindern.
- `orderexportpdf/classes/OrderExport.php`

  - **Klassenname:** `OrderExport`
  - **Elternklasse:** `Object` (wahrscheinlich, oder eine benutzerdefinierte Basisklasse)
  - **Verantwortlichkeit:** Diese Klasse enthält wahrscheinlich Hilfsmethoden oder Kernlogik, die sich auf den gesamten Bestell-Exportprozess beziehen, möglicherweise die Datenabfrage, Formatierung oder Interaktion mit der PDF-Generierungsklasse. Es handelt sich möglicherweise nicht um ein `ObjectModel`, sondern um eine Dienstprogrammklasse.
- `orderexportpdf/classes/OrderExportChecklistCategory.php`

  - **Klassenname:** `OrderExportChecklistCategory`
  - **Elternklasse:** `ObjectModel`
  - **Datenbanktabelle:** `ps_orderexport_checklist_cat`
  - **`$definition`-Felder:** Definiert die Struktur einer Checklistenkategorie, einschließlich Feldern wie `id_orderexport_checklist_cat`, `name` (mehrsprachig), `active`, `position`.
  - **Wichtige öffentliche Methoden:** Standard-`ObjectModel`-Methoden (`add`, `update`, `delete`, `getFields`, `validateFields`, `validateController`). Kann Methoden zum Abrufen aller aktiven Kategorien oder Kategorien nach ID enthalten.
- `orderexportpdf/classes/OrderExportChecklistElement.php`

  - **Klassenname:** `OrderExportChecklistElement`
  - **Elternklasse:** `ObjectModel`
  - **Datenbanktabelle:** `ps_orderexport_checklist_elem`
  - **`$definition`-Felder:** Definiert die Struktur eines Checklisten-Elements, einschließlich Feldern wie `id_orderexport_checklist_elem`, `id_orderexport_checklist_cat` (Fremdschlüssel), `name` (mehrsprachig), `active`, `position`.
  - **Wichtige öffentliche Methoden:** Standard-`ObjectModel`-Methoden. Kann Methoden zum Abrufen von Elementen nach Kategorie oder aller aktiven Elemente enthalten.
- `orderexportpdf/classes/OrderPdfGenerator.php`

  - **Klassenname:** `OrderPdfGenerator`
  - **Elternklasse:** Wahrscheinlich `Object` oder eine benutzerdefinierte Basisklasse.
  - **Verantwortlichkeit:** Dies ist die Kernklasse, die für die Generierung der PDF-Dokumente verantwortlich ist. Sie nimmt eine Bestell-ID, die ausgewählte Vorlage und Checklisten-Daten entgegen und rendert den Inhalt dann in ein PDF-Format. Sie verwendet wahrscheinlich intern eine Drittanbieter-PDF-Bibliothek (z. B. Dompdf, mPDF).
  - **Wichtige öffentliche Methoden:** `generatePdf($orderId, $templateName, $checklistData)`, `renderTemplate($templatePath, $data)`, `downloadPdf()`.

### 4.4 JavaScript-Assets (`views/js/`)

- `orderexportpdf/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`

  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Verwaltet wahrscheinlich die dynamische Verwaltung von PDF-Vorlagen innerhalb der Konfigurationsoberfläche des Moduls. Dies könnte AJAX-Aufrufe zum Speichern von Vorlageneinstellungen, zum Vorschau von Vorlagen oder zum Wechseln zwischen verschiedenen Vorlagenoptionen umfassen.
- `orderexportpdf/views/js/order-list-legacy.js`

  - **Geltungsbereich:** Back-Office (für PrestaShop 1.7.x oder ältere Versionen, die Legacy-JS verwenden).
  - **Verantwortlichkeit:** Integriert die PDF-Export-Schaltflächenfunktionalität in die PrestaShop Back Office Bestelllistenansicht für ältere PrestaShop-Versionen. Es bindet Klickereignisse an Schaltflächen, führt möglicherweise AJAX-Aufrufe zur Auslösung der PDF-Generierung durch und handhabt den Download des generierten PDFs.
- `orderexportpdf/views/js/order-list-modern.js`

  - **Geltungsbereich:** Back-Office (für PrestaShop 8.x, 9.x oder neuere Versionen, die modernes JS verwenden).
  - **Verantwortlichkeit:** Ähnlich wie `order-list-legacy.js`, aber angepasst an neuere PrestaShop Back Office-Oberflächen und möglicherweise unter Verwendung moderner JavaScript-Praktiken (z. B. ES6, Webpack-kompilierte Assets). Es stellt sicher, dass die PDF-Export-Schaltfläche auf der Bestellliste und den einzelnen Bestellansichtsseiten korrekt angezeigt und funktionsfähig ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- `orderexportpdf/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`

  - **Geltungsbereich:** Back-Office Admin-Formular-Styling.
  - **Verantwortlichkeit:** Bietet Styling für die Konfigurationsoberfläche des Moduls, speziell für den PDF-Vorlagenmanager-Bereich. Dies könnte Stile für Schaltflächen, Dropdowns, Vorschaubereiche oder Formularelemente im Zusammenhang mit der Vorlagenauswahl umfassen.
- `orderexportpdf/views/css/order-export.css`

  - **Geltungsbereich:** Back-Office Admin-Formular-Styling.
  - **Verantwortlichkeit:** Allgemeines Styling für die Back-Office-Komponenten des Moduls, wie die Verwaltungsbildschirme für Checklistenkategorien und -elemente oder möglicherweise Styling für die hinzugefügten Schaltflächen auf den Bestellseiten.
  - **Wichtige CSS-Klassenselektoren:** Entwickler können den generierten HTML-Code nach Klassen wie `.orderexportpdf-button`, `.orderexport-checklist-table` usw. untersuchen, um Stile in ihrem benutzerdefinierten Admin-Theme zu überschreiben.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)

- `orderexportpdf/lib/pdfTemplatesManager/views/buttonManager.tpl`

  - **Hook:** Wahrscheinlich in einem Hook innerhalb der Modulkonfiguration oder einer Admin-Bestellseite gerendert, um Schaltflächen im Zusammenhang mit der Vorlagenverwaltung anzuzeigen (z. B. „Vorlagen verwalten“, „Neue Vorlage erstellen“).
  - **Ausgabe:** HTML für Schaltflächen oder Links zur Verwaltung von PDF-Vorlagen.
- `orderexportpdf/lib/pdfTemplatesManager/views/createTemplateForm.tpl`

  - **Hook:** Intern zum Vorlagenmanager des Moduls, wird beim Erstellen einer neuen PDF-Vorlage angezeigt.
  - **Ausgabe:** HTML-Formular zum Definieren von Eigenschaften einer neuen PDF-Vorlage.
- `orderexportpdf/lib/pdfTemplatesManager/views/editTemplateForm.tpl`

  - **Hook:** Intern zum Vorlagenmanager des Moduls, wird beim Bearbeiten einer bestehenden PDF-Vorlage angezeigt.
  - **Ausgabe:** HTML-Formular zum Ändern von Eigenschaften einer bestehenden PDF-Vorlage.
- `orderexportpdf/lib/pdfTemplatesManager/views/mainForm.tpl`

  - **Hook:** Das Hauptkonfigurationsformular für das Modul (z. B. `getContent()`-Methode).
  - **Ausgabe:** Das primäre HTML-Formular, das das Dropdown-Menü „PDF-Vorlage“ und andere Einstellungen auf Modulebene enthält.
- `orderexportpdf/lib/pdfTemplatesManager/views/selectInput.tpl`

  - **Hook:** Eine wiederverwendbare Teilvorlage, wahrscheinlich in `mainForm.tpl` oder anderen Formularen enthalten, um ein Dropdown-(`select`)-Eingabefeld zur Auswahl von Vorlagen zu rendern.
  - **Ausgabe:** HTML für ein `<select>`-Element, das mit verfügbaren PDF-Vorlagen gefüllt ist.
- `orderexportpdf/pdf/en/*.tpl` (z. B. `blue-line-dompdf.tpl`, `boxed-layout-dompdf.tpl`, `clean-dompdf.tpl`, `warehouse-big-dompdf.tpl`, etc.)

  - **Hook:** Dies sind **keine** PrestaShop-Hook-Vorlagen. Dies sind die eigentlichen **PDF-Layout-Vorlagen**, die von `OrderPdfGenerator` zum Rendern des Inhalts der Kommissionierliste/des Lieferscheins verwendet werden. Sie werden über die Modulkonfiguration ausgewählt.
  - **Ausgabe:** HTML/CSS-Struktur, die in ein PDF-Dokument konvertiert wird. Diese Vorlagen enthalten Platzhalter für Bestelldetails, Produktlisten, Kundeninformationen und die benutzerdefinierte Checkliste.
  - **Hinweis:** Der `dompdf`-Suffix deutet auf die Verwendung der Dompdf-Bibliothek für die HTML-zu-PDF-Konvertierung hin.
- `orderexportpdf/pdf/fr/kids-play.tpl`

  - **Hook:** Ähnlich wie die `en`-Vorlagen, aber eine französischsprachige Version des „kids-play“-PDF-Layouts. Dies deutet auf mehrsprachige Unterstützung für PDF-Vorlagen hin.
- `orderexportpdf/pdf/en/order-export.tpl`

  - **Hook:** Dies könnte eine generische Basisvorlage oder eine Fallback-Vorlage für die PDF-Generierung sein.
  - **Ausgabe:** Eine allgemeine Struktur für das Bestell-Export-PDF.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_orderexport_checklist_cat`: Speichert Informationen über die benutzerdefinierten Checklistenkategorien.

  - `id_orderexport_checklist_cat` (Primärschlüssel, INT)
  - `name` (VARCHAR, Mehrsprachig): Der Name der Checklistenkategorie.
  - `active` (TINYINT): Ob die Kategorie aktiv ist.
  - `position` (INT): Anzeigereihenfolge der Kategorien.
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_orderexport_checklist_elem`: Speichert Informationen über die einzelnen Checklisten-Elemente.

  - `id_orderexport_checklist_elem` (Primärschlüssel, INT)
  - `id_orderexport_checklist_cat` (Fremdschlüssel zu `ps_orderexport_checklist_cat`, INT): Die Kategorie, zu der dieses Element gehört.
  - `name` (VARCHAR, Mehrsprachig): Der Text des Checklistenpunkts.
  - `active` (TINYINT): Ob das Element aktiv ist.
  - `position` (INT): Anzeigereihenfolge der Elemente innerhalb einer Kategorie.
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_configuration`: Das Modul speichert hier seine Hauptkonfigurationseinstellungen.

  - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: (PrestaShop-Kerndaten, nicht modulspezifisch)
  - `MYPRESTA_UPDATES`: (Moduleinstellung) Speichert den Status der Update-Prüfung (1 für aktiviert, 0 für deaktiviert).
  - `UPDATE_`: (Moduleinstellung) Interne Update-Versionsverfolgung.
  - `UPDATEV_`: (Moduleinstellung) Interner Update-Versionswert.
  - `ORDEREXPORTPDF_TEMPLATE`: (Moduleinstellung) Speichert den Namen der aktuell ausgewählten PDF-Vorlage.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein AdminController seine Assets lädt. | Fügt modulspezifisches CSS (`order-export.css`, `pdfTemplatesManager.css`) und JavaScript (`order-list-legacy.js`, `order-list-modern.js`, `pdfTemplatesManager.js`) in das Back Office ein, insbesondere für Bestellseiten und die Modulkonfiguration. |
| `displayAdminOrder` | Wird auf der individuellen Bestellansichtsseite im Back Office ausgeführt. | Rendert die Schaltfläche „PDF exportieren“ oder ein ähnliches Widget auf der Bestelldetailseite, um die PDF-Generierung für eine einzelne Bestellung zu ermöglichen. |
| `actionGetAdminOrderButtons` | Wird ausgeführt, um Modulen das Hinzufügen benutzerdefinierter Schaltflächen zur Admin-Bestellansicht zu ermöglichen. | Bietet einen Mechanismus zum Einfügen benutzerdefinierter Schaltflächen (wie „PDF exportieren“) in die PrestaShop 1.7+-Bestellansicht, um die Kompatibilität mit der modernen Benutzeroberfläche zu gewährleisten. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Bestell-PDF-Export & Lager-Checkliste“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität oder Konfiguration des Moduls zur Verfügung.
