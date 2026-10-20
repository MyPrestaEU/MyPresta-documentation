---
title: "Versanddienstleister Produkten in großen Mengen zuweisen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Versanddienstleister Produkten in großen Mengen zuweisen' von MyPresta.eu."
sidebar:
  label: "Versanddienstleister Produkten in großen Mengen zuweisen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Assign carrier to products in bulk auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/assign-carrier-to-products-in-bulk.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/assign-carrier-to-products-in-bulk/)
>
> ---


# Versanddienstleister Produkten in großen Mengen zuweisen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Versanddienstleister Produkten in großen Mengen zuweisen)

Dies ist die Hauptschnittstelle, in der Sie Ihre Aufgaben zur Massenzuweisung von Versanddienstleistern definieren. Die Seite ist intuitiv gestaltet und führt Sie durch den Prozess der Auswahl von Versanddienstleistern und der Angabe, welche Produkte betroffen sein sollen.

**Hauptkonfigurationsoptionen:**

1. **Versanddienstleister auswählen:**

   - **Was diese Einstellung bewirkt:** Dieser Abschnitt zeigt eine Liste aller aktiven Versanddienstleister an, die in Ihrem PrestaShop-Shop konfiguriert sind (zu finden unter **Versand > Versanddienstleister**). Sie können einen oder mehrere Versanddienstleister auswählen, die Sie Ihren Produkten zuweisen möchten.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ein oder mehrere Versanddienstleister ausgewählt sind:* Die ausgewählten Versanddienstleister werden den Produkten zugewiesen, die Sie in den nächsten Schritten angeben. Dies bedeutet, dass diese Versanddienstleister während des Checkouts als verfügbare Versandoptionen für diese Produkte angezeigt werden.
     - *Wenn keine Versanddienstleister ausgewählt sind:* Das Modul führt keine Zuweisung durch. Sie müssen mindestens einen Versanddienstleister auswählen, um fortzufahren.
   - **Empfohlener Wert:** Wählen Sie alle Versanddienstleister aus, die für die Zielprodukte verfügbar sein sollen.
   - **Händlerszenario / Beispiel:** Wenn Sie „UPS Ground“ und „FedEx Express“ für eine neue Elektroniklinie verfügbar machen möchten, würden Sie beide aus dieser Liste auswählen.
2. **Produkte auswählen, denen Versanddienstleister zugewiesen werden sollen:**

   - **Was diese Einstellung bewirkt:** Dieser entscheidende Abschnitt ermöglicht es Ihnen, den Umfang der Produkte zu definieren, die die ausgewählten Versanddienstleister-Zuweisungen erhalten sollen. Sie haben drei leistungsstarke Optionen:
     - **Nach Kategorien:** Weisen Sie Versanddienstleister allen Produkten innerhalb spezifischer Kategorien zu.
     - **Nach Herstellern:** Weisen Sie Versanddienstleister allen Produkten bestimmter Hersteller zu.
     - **Nach spezifischen Produkten:** Weisen Sie Versanddienstleister einzelnen Produkten zu, die Sie auswählen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn „Nach Kategorien“ ausgewählt ist:* Eine Liste der Kategorien Ihres Shops wird angezeigt. Die Auswahl von Kategorien hier bedeutet, dass allen Produkten, die zu diesen Kategorien gehören, die ausgewählten Versanddienstleister zugewiesen werden.
     - *Wenn „Nach Herstellern“ ausgewählt ist:* Eine Liste der Hersteller Ihres Shops wird angezeigt. Die Auswahl von Herstellern hier bedeutet, dass allen Produkten, die mit diesen Herstellern verbunden sind, die ausgewählten Versanddienstleister zugewiesen werden.
     - *Wenn „Nach spezifischen Produkten“ ausgewählt ist:* Ein Eingabefeld mit einer Autocomplete-Funktion wird angezeigt. Sie können Produktnamen eingeben, und das System schlägt Produkte vor. Sie können mehrere spezifische Produkte zur Liste hinzufügen.
   - **Empfohlener Wert:** Wählen Sie die Methode, die Ihre Zielprodukte am besten gruppiert. Für umfassende Änderungen sind Kategorien oder Hersteller effizient. Für präzise Anpassungen sind spezifische Produkte am besten geeignet.
   - **Händlerszenario / Beispiel:**
     - *Kategorien:* Sie starten eine neue Kategorie „Zerbrechliche Artikel“. Sie würden diese Kategorie auswählen und einen spezialisierten „Versanddienstleister für zerbrechliche Güter“ allen Produkten darin zuweisen.
     - *Hersteller:* Eine neue Bekleidungsmarke kommt an. Sie wählen den Hersteller aus und weisen allen seinen Produkten Ihren Standard-„Bekleidungsversanddienstleister“ zu.
     - *Spezifische Produkte:* Sie haben drei einzigartige, übergroße Produkte, die einen „Frachtversanddienstleister“ erfordern. Sie würden diese drei Produkte einzeln suchen und hinzufügen.
3. **Aktionsschaltflächen:**

   - **Schaltfläche „Versanddienstleister zuweisen“:**
     - **Was diese Schaltfläche bewirkt:** Startet den Massenzuweisungsprozess. Nach dem Klicken verarbeitet das Modul Ihre Auswahl und aktualisiert die Versanddienstleister-Zuordnungen für alle angegebenen Produkte.
     - **Auswirkung des Klickens auf diese Schaltfläche:** Die ausgewählten Versanddienstleister werden mit den ausgewählten Produkten verknüpft. Eine Erfolgs- oder Fehlermeldung wird normalerweise angezeigt.
     - **Empfohlene Aktion:** Klicken Sie nur, nachdem Sie Ihre Versanddienstleister- und Produktauswahl sorgfältig überprüft haben.
     - **Händlerszenario / Beispiel:** Nachdem Sie Ihre Versanddienstleister und Produktgruppen eingerichtet haben, führt das Klicken auf diese Schaltfläche die Änderungen in Ihrem Shop aus.
   - **Schaltfläche „Alle Zuweisungen löschen“ (oder ähnlich):**
     - **Was diese Schaltfläche bewirkt:** Diese Option (falls vorhanden) würde typischerweise *alle* Versanddienstleister-Zuweisungen für die ausgewählten Produkte oder potenziell für alle Produkte im Shop entfernen, abhängig von der genauen Implementierung des Moduls.
     - **Auswirkung des Klickens auf diese Schaltfläche:** Produkte würden auf keine spezifischen Versanddienstleister zugewiesen oder nur auf Standardversanddienstleister zurückgesetzt, was die Verfügbarkeit des Versands beeinträchtigen könnte.
     - **Empfohlene Aktion:** Mit äußerster Vorsicht verwenden und nur, wenn Sie die Auswirkungen vollständig verstehen. Dies ist eine mächtige Aktion, die Ihre Versandoptionen stören kann.
     - **Händlerszenario / Beispiel:** Sie überarbeiten Ihre Versandstrategie vollständig und müssen alle Produkt-Versanddienstleister-Verknüpfungen zurücksetzen, bevor Sie sie neu zuweisen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AdminMassCarrierCronController (Back Office > Erweiterte Einstellungen > Massen-Versanddienstleister-Cron)

Dieser Bildschirm bietet die Verwaltung von Cron-Jobs, die sich auf das Modul beziehen, und ermöglicht es Ihnen, Aufgaben zur Versanddienstleister-Zuweisung zu planen und zu automatisieren.

- **Bildschirmname & Menüpfad:** Sie finden normalerweise einen neuen Menüpunkt unter **Erweiterte Einstellungen** (oder einem ähnlichen Abschnitt, je nach PrestaShop-Version) mit einem Namen wie „Massen-Versanddienstleister-Cron“ oder „Versanddienstleister-Zuweisungsplaner“.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt wahrscheinlich ein Raster (Liste) der geplanten Aufgaben an. Für jede Aufgabe könnten Sie sehen:
  - **Aufgaben-ID:** Eindeutiger Bezeichner.
  - **Beschreibung:** Eine kurze Erklärung, was die Aufgabe bewirkt (z.B. „UPS Kategorie X zuweisen“).
  - **Häufigkeit:** Wie oft die Aufgabe ausgeführt wird (z.B. täglich, wöchentlich, einmal).
  - **Letzte Ausführung:** Zeitstempel der letzten Ausführung.
  - **Status:** Ob die Aufgabe aktiv, ausstehend oder abgeschlossen ist.
  - **Aktionen:** Schaltflächen zum „Neue Aufgabe hinzufügen“, „Bearbeiten“, „Löschen“ oder „Jetzt ausführen“.
- **Auswirkung von Änderungen:**
  - *Hinzufügen einer neuen Aufgabe:* Ermöglicht Ihnen, einen neuen Massen-Versanddienstleister-Zuweisungsvorgang zu definieren, der automatisch in einem bestimmten Intervall ausgeführt wird. Dies ist nützlich für wiederkehrende Aktualisierungen (z.B. neue Produktimporte).
  - *Bearbeiten einer Aufgabe:* Ändert die Parameter (Versanddienstleister, Produkte, Häufigkeit) einer bestehenden geplanten Zuweisung.
  - *Löschen einer Aufgabe:* Entfernt eine geplante Zuweisung und verhindert deren zukünftige Ausführung.
  - *Jetzt eine Aufgabe ausführen:* Führt eine geplante Aufgabe sofort aus, außerhalb ihres regulären Zeitplans.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - Verwenden Sie diesen Bildschirm, um routinemäßige Versanddienstleister-Zuweisungen zu automatisieren, insbesondere wenn Sie regelmäßig neue Produkte in bestimmte Kategorien oder von bestimmten Herstellern importieren, die immer dieselben Versanddienstleister verwenden.
  - Für einmalige, sofortige Zuweisungen verwenden Sie die Hauptkonfigurationsseite des Moduls (4.1).
  - Überprüfen Sie regelmäßig „Letzte Ausführung“ und „Status“, um sicherzustellen, dass Ihre automatisierten Aufgaben korrekt ausgeführt werden.

#### 2.2.2 index.php (masscarrier/controllers/admin/index.php)

Diese Datei dient typischerweise als Platzhalter oder Weiterleitung innerhalb des Admin-Controller-Verzeichnisses des Moduls und stellt normalerweise keinen eigenständigen, konfigurierbaren Bildschirm für den Händler dar. In der PrestaShop-Modulentwicklung verhindern `index.php`-Dateien in Unterverzeichnissen oft die Verzeichnisauflistung oder handhaben grundlegendes Routing, anstatt eine Benutzeroberfläche bereitzustellen. Daher sind mit dieser Datei keine spezifischen händlerseitigen Einstellungen oder Aktionen verbunden.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | Versanddienstleister auswählen | Alle relevanten auswählen | Wählen Sie aus, welche Versanddienstleister Produkten zugewiesen werden sollen. |
|  | Produkte auswählen: Nach Kategorien | Relevante Kategorien auswählen | Weisen Sie Versanddienstleister allen Produkten innerhalb der ausgewählten Kategorien zu. |
|  | Produkte auswählen: Nach Herstellern | Relevante Hersteller auswählen | Weisen Sie Versanddienstleister allen Produkten der ausgewählten Hersteller zu. |
|  | Produkte auswählen: Nach spezifischen Produkten | Produkte suchen & hinzufügen | Weisen Sie Versanddienstleister individuell ausgewählten Produkten zu. |
|  | Schaltfläche „Versanddienstleister zuweisen“ | Nach Auswahl klicken | Führt die Massenzuweisung von Versanddienstleistern aus. |
|  | Schaltfläche „Alle Zuweisungen löschen“ | Mit Vorsicht verwenden | Entfernt Versanddienstleister-Zuweisungen für ausgewählte Produkte (falls vorhanden). |
| **AdminMassCarrierCronController** | Aufgabe hinzufügen/bearbeiten/löschen | Basierend auf Automatisierungsbedarf | Planen und verwalten Sie automatisierte Massenzuweisungen von Versanddienstleistern. |
|  | Aktion „Jetzt ausführen“ | Bei Bedarf für sofortige Ausführung | Manuelles Auslösen einer geplanten Aufgabe. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe Versanddienstleister zugewiesen, aber sie werden den Kunden an der Kasse nicht angezeigt.**
A:

1. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). PrestaShop speichert die Verfügbarkeit von Versanddienstleistern oft im Cache.
2. **Versanddienstleister-Konfiguration:** Überprüfen Sie nochmals, ob die Versanddienstleister selbst aktiv sind, gültige Versandzonen haben und für den Gewichts-/Preisbereich des Produkts konfiguriert sind. Gehen Sie zu **Versand > Versanddienstleister** und bearbeiten Sie den Versanddienstleister, um seine Einstellungen zu überprüfen.
3. **Produktabmessungen/Gewicht:** Stellen Sie sicher, dass die Abmessungen und das Gewicht des Produkts korrekt eingegeben wurden und in die definierten Bereiche des Versanddienstleisters fallen.
4. **Modulausführung:** Führen Sie den Zuweisungsprozess im Modul erneut aus und stellen Sie sicher, dass Sie die richtigen Versanddienstleister und Produktgruppen ausgewählt haben.

**F: Das Modul scheint zu hängen oder benötigt sehr lange zur Verarbeitung.**
A:

1. **Serverressourcen:** Wenn Sie einen sehr großen Katalog (Zehntausende von Produkten) haben und „allen Produkten“ zuweisen, kann der Prozess ressourcenintensiv sein. Stellen Sie sicher, dass Ihr Hosting über ausreichend PHP-Speicher und Ausführungszeitlimits verfügt.
2. **Cron-Job:** Für extrem große Operationen sollten Sie die Verwendung des „AdminMassCarrierCronController“ in Betracht ziehen, um die Aufgabe als Hintergrund-Cron-Job zu planen, was für langlaufende Prozesse robuster ist.
3. **Aufgaben aufteilen:** Anstatt *allen* Produkten auf einmal zuzuweisen, versuchen Sie, die Zuweisung nach Hauptkategorien oder Herstellern aufzuteilen.

**F: Kann ich mit diesem Modul einen Versanddienstleister in großen Mengen von Produkten entfernen?**
A: Die Hauptfunktion dieses Moduls ist das *Zuweisen* von Versanddienstleistern. Obwohl es keine direkte Funktion zum „Entfernen von Versanddienstleistern von ausgewählten Produkten“ gibt, können Sie dies effektiv erreichen, indem Sie:

1. **Neu zuweisen:** Wenn Sie Versanddienstleister A durch Versanddienstleister B für eine Gruppe von Produkten ersetzen möchten, wählen Sie einfach Versanddienstleister B und die Produktgruppe aus und führen Sie dann die Zuweisung aus. Dadurch wird Versanddienstleister B hinzugefügt. Sie müssten dann Versanddienstleister A manuell von diesen Produkten entfernen, wenn Sie ihn vollständig entfernen möchten, oder ein separates Tool verwenden, falls verfügbar.
2. **Manuelles Entfernen:** Für bestimmte Produkte können Sie weiterhin die Produktbearbeitungsseite (**Katalog > Produkte > Produkt bearbeiten > Registerkarte Versand**) aufrufen und den Versanddienstleister manuell deaktivieren.

**F: Mein benutzerdefiniertes Theme zeigt die Elemente des Moduls nicht korrekt an (falls überhaupt welche sichtbar waren).**
A: Dieses Modul hat keine visuellen Front-Office-Elemente, daher sind Theme-Kompatibilitätsprobleme aus Anzeigesicht unwahrscheinlich. Wenn Sie Probleme mit den *Back-Office*-Konfigurationsbildschirmen haben:

1. **PrestaShop-Version:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre PrestaShop-Installation heruntergeladen haben.
2. **Browser-Cache:** Leeren Sie den Cache Ihres Browsers.
3. **Theme-Overrides:** Wenn Ihr Back-Office-Theme stark angepasst ist, könnte es zu Interferenzen kommen. Versuchen Sie, vorübergehend zum Standard-PrestaShop-Back-Office-Theme zu wechseln, um zu sehen, ob das Problem weiterhin besteht.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Versanddienstleister Produkten in großen Mengen zuweisen“ (`masscarrier`) folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) und konzentriert sich hauptsächlich auf administrative Aufgaben. Es nutzt die `Module`-Klasse von PrestaShop für seine Kernfunktionalität und erweitert `AdminController` für seine dedizierten Back-Office-Verwaltungsbildschirme. Das Modul interagiert direkt mit den Kernprodukt- und Versanddienstleisterdaten von PrestaShop und modifiziert die Tabelle `ps_product_carrier`, um Zuordnungen herzustellen. Es enthält auch einen Front-Controller für die Ausführung von Cron-Jobs, der geplante Massenoperationen ermöglicht.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse**: `MassCarrierCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller ist dafür konzipiert, extern aufgerufen zu werden, typischerweise durch einen serverseitigen Cron-Job. Er führt die im Back-Office definierten geplanten Aufgaben zur Versanddienstleister-Zuweisung aus. Er rendert keine visuelle Ausgabe an den Browser, sondern führt Hintergrundverarbeitung durch. Er handhabt die Logik zum Abrufen ausstehender Aufgaben aus der Tabelle `masscarriercron` und zum Anwenden der Versanddienstleister-Änderungen auf Produkte.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMassCarrierCron.php`
    - **Tab-Name und verwaltete Entität**: Dieser Controller verwaltet die Entität `masscarriercron`, die geplante Massen-Versanddienstleister-Zuweisungsaufgaben darstellt. Er erstellt einen neuen Tab im PrestaShop Back Office (wahrscheinlich unter „Erweiterte Einstellungen“ oder einem benutzerdefinierten „Massen-Versanddienstleister“-Menü).
    - **Verantwortlichkeit**: Bietet eine Standard-PrestaShop `AdminController`-Schnittstelle zum Auflisten, Hinzufügen, Bearbeiten und Löschen geplanter Cron-Aufgaben. Er handhabt die Formularübermittlung zum Erstellen/Aktualisieren von Aufgaben, zur Validierung von Eingaben und zur Interaktion mit der Datenbanktabelle `masscarriercron`.
  - `controllers/admin/index.php`
    - **Verantwortlichkeit**: Dies ist eine standardmäßige leere `index.php`-Datei, die oft in PrestaShop-Modulverzeichnissen platziert wird, um die Verzeichnisauflistung zu verhindern, wenn sie direkt über einen Webbrowser aufgerufen wird. Sie enthält keine funktionale Logik oder verwaltet keine Entität.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies impliziert, dass die Kernlogik für die Versanddienstleister-Zuweisung und die Cron-Job-Verwaltung wahrscheinlich direkt in der Hauptdatei `masscarrier.php` und den jeweiligen Controllern gehandhabt wird, möglicherweise unter direkter Verwendung der PrestaShop `ObjectModel`s `Product` und `Carrier`.

### 4.4 JavaScript-Assets (`views/js/`)

- `masscarrier/lib/searchTool/views/js/autocomplete.js`
  - **Umfang**: Back-Office.
  - **Verantwortlichkeit**: Dieses Skript bietet wahrscheinlich die Autocomplete-Funktionalität zur Auswahl spezifischer Produkte auf der Hauptkonfigurationsseite des Moduls. Es überwacht Benutzereingaben in einem dafür vorgesehenen Produktsuchfeld, sendet AJAX-Anfragen an einen Back-Office-Controller (oder die Hauptmodul-Methode `getContent()`), um Produktvorschläge abzurufen, und zeigt diese in einer Dropdown-Liste an. Es handhabt Auswahlereignisse, um ausgewählte Produkte einer Liste für die Massenzuweisung hinzuzufügen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `masscarrier/lib/searchTool/views/css/autocomplete.css`
  - **Umfang**: Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit**: Bietet Styling für das Autocomplete-Suchfeld und seine Vorschlagsliste, um sicherzustellen, dass es visuell in das PrestaShop Back-Office-Theme integriert ist. Es definiert Stile für das Eingabefeld, den Dropdown-Container und einzelne Vorschlagselemente. Entwickler können diese Klassen bei Bedarf in ihren benutzerdefinierten Back-Office-Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - Es sind keine spezifischen Hook-Templates aufgeführt, was darauf hindeutet, dass die primäre Konfiguration des Moduls über `getContent()` und dedizierte Admin-Controller erfolgt.
- **Admin-Templates (`views/templates/admin/`)**:

  - `masscarrier/lib/searchTool/views/scripts.tpl`
    - **Zweck**: Dieses Template enthält wahrscheinlich das notwendige JavaScript für das Autocomplete-Suchtool (z.B. `autocomplete.js`) und möglicherweise Inline-JavaScript-Konfigurationen oder CSS-Links. Es ist wahrscheinlich im Hauptmodul-Konfigurationsformular oder einem Admin-Controller-Formular enthalten.
  - `masscarrier/masscarrier.tpl`
    - **Zweck**: Dies ist das Hauptkonfigurationstemplate für das Modul, das von der `getContent()`-Methode von `masscarrier.php` gerendert wird. Es enthält die HTML-Struktur zur Auswahl von Versanddienstleistern, zur Auswahl von Produktgruppen (Kategorien, Hersteller, spezifische Produkte) und die Schaltfläche „Versanddienstleister zuweisen“. Es enthält wahrscheinlich das `scripts.tpl` für die Autocomplete-Funktionalität.
  - `masscarrier/views/button-subcategories.tpl`
    - **Zweck**: Dieses Template rendert wahrscheinlich eine Schaltfläche oder einen Abschnitt zur Verwaltung von Unterkategorien, möglicherweise zum Erweitern/Reduzieren von Kategoriebäumen in der Produktauswahloberfläche oder für spezifische Aktionen im Zusammenhang mit der Unterkategorienauswahl.
- **Front-Office-Templates (`views/templates/front/`)**:

  - Es sind keine Front-Office-Templates aufgeführt, was mit dem Back-Office-Verwaltungscharakter des Moduls übereinstimmt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_masscarriercron`: Diese benutzerdefinierte Tabelle speichert die Details der geplanten Massen-Versanddienstleister-Zuweisungsaufgaben. Sie würde typischerweise Felder wie:
    - `id_masscarriercron`: Primärschlüssel.
    - `carriers`: Ein serialisiertes Array oder eine durch Kommas getrennte Zeichenfolge von Versanddienstleister-IDs.
    - `product_selection_type`: (z.B. 'category', 'manufacturer', 'product').
    - `product_selection_ids`: Ein serialisiertes Array oder eine durch Kommas getrennte Zeichenfolge von Kategorie-/Hersteller-/Produkt-IDs.
    - `frequency`: (z.B. 'daily', 'weekly', 'once').
    - `last_run`: DATETIME der letzten Ausführung.
    - `active`: BOOLEAN, das angibt, ob die Aufgabe aktiviert ist.
  - Das Modul interagiert hauptsächlich mit den Kerntabellen von PrestaShop:
    - `ps_product_carrier`: Dies ist die entscheidende Tabelle, die die Many-to-Many-Beziehung zwischen Produkten und Versanddienstleistern speichert. Das Modul fügt Datensätze in diese Tabelle ein/aktualisiert sie.
    - `ps_product`: Zum Abrufen von Produktinformationen.
    - `ps_category_product`: Zum Verknüpfen von Produkten mit Kategorien.
    - `ps_product_supplier` / `ps_manufacturer`: Zum Verknüpfen von Produkten mit Herstellern.
    - `ps_carrier`: Zum Abrufen von Versanddienstleister-Informationen.
- **Registrierte Hooks-Tabelle**:
  Die Modulbeschreibung erwähnt „Front-Office Hooks: Header, Columns, Product, or Footer“, aber basierend auf dem Code-Inventar und dem Modulzweck ist es höchst unwahrscheinlich, dass es Front-Office-Hooks für die visuelle Ausgabe registriert. Dies könnten generische Platzhalter sein oder sich auf interne Hooks beziehen, die für die Modulinitialisierung oder Datenverarbeitung verwendet werden.

  Das Modul würde hauptsächlich interne PrestaShop-Hooks für seine Funktionalität verwenden:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `actionModuleInstall` | Während der Modulinstallation | Erstellt die Tabelle `ps_masscarriercron`, registriert Admin-Tabs. |
  | `actionModuleUninstall` | Während der Moduldeinstallation | Löscht die Tabelle `ps_masscarriercron`, deregistriert Admin-Tabs. |
  | `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird | Fügt JS/CSS-Assets für Back-Office-Formulare ein (z.B. autocomplete.js, autocomplete.css). |
  | `displayBackOfficeHeader` | Rendert im Back-Office-Header | Kann globale Back-Office-JS/CSS oder Konfiguration enthalten. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Versanddienstleister Produkten in großen Mengen zuweisen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu bietet direkten Support und stellt sicher, dass Sie Zugriff auf die kompatibelsten und funktionsreichsten Versionen des Moduls für Ihren PrestaShop-Shop haben.
