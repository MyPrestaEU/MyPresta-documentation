---
title: "Maximaler Einkaufswert nach Kategorien – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Maximaler Einkaufswert nach Kategorien“ von MyPresta.eu."
sidebar:
  label: "Maximaler Einkaufswert nach Kategorien – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Maximum purchase value by categories auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-categories.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/maximum-purchase-value-by-categories/)
>
> ---


# Maximaler Einkaufswert nach Kategorien

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Installation hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie die allgemeinen Einstellungen verwalten und auf die Regeln für maximale Einkaufswerte zugreifen.

- **Was diese Einstellung bewirkt:** Diese Seite bietet allgemeine Informationen über das Modul und enthält oft einen Link oder eine Schaltfläche zur Verwaltung der eigentlichen Regeln.
- **Auswirkung der Änderung dieser Einstellung:** Obwohl dieser spezifische Bildschirm möglicherweise keine direkten „Einstellungen“ zum Ändern hat, dient er als Einstiegspunkt zur Funktionalität des Moduls.
- **Empfohlener Wert:** N/A (Dies ist ein Informationsbildschirm).
- **Händlerszenario / Beispiel:** Nach der Installation landen Sie hier. Sie klicken dann auf eine Schaltfläche oder einen Link (z.B. „Regeln verwalten“ oder „Maximale Werte konfigurieren“), um zum dedizierten Bildschirm zu gelangen, auf dem Sie Ihre Kategorielimits definieren.

### 2.2 Dedizierter Admin-Bildschirm: Regeln für den maximalen Einkaufswert (Back Office > Module > Maximaler Einkaufswert nach Kategorien > Konfigurieren)

Dies ist der Kern des Moduls, wo Sie Ihre Regeln für den maximalen Einkaufswert für verschiedene Kategorien definieren und verwalten. Sie finden diesen Bildschirm normalerweise, indem Sie nach der Installation des Moduls auf „Konfigurieren“ klicken oder indem Sie zu **Module > Modul-Manager** navigieren, das Modul suchen und auf „Konfigurieren“ klicken.

**Bildschirmname & Menüpfad:**
Sie greifen auf diesen Bildschirm zu, indem Sie zu **Module > Modul-Manager** navigieren, nach „Maximaler Einkaufswert nach Kategorien“ suchen und auf die Schaltfläche „Konfigurieren“ klicken. Dies führt Sie zu einer dedizierten Verwaltungsoberfläche zur Verwaltung Ihrer Regeln.

**Verfügbare Aktionen & Einstellungen:**
Auf diesem Bildschirm sehen Sie eine Liste (Raster) aller Ihrer aktuell definierten Regeln für den maximalen Einkaufswert. Für jede Regel sehen Sie typischerweise:

- **Kategoriename:** Der Name der Produktkategorie, für die die Regel gilt.
- **Maximaler Wert:** Der höchste Gesamtwert (in Ihrer Standardwährung), der für Produkte aus dieser Kategorie in einer einzigen Bestellung zulässig ist.
- **Aktionen:** Schaltflächen zum „Bearbeiten“ einer bestehenden Regel oder zum „Löschen“ derselben.

Sie finden auch:

- **Schaltfläche „Neue Regel hinzufügen“:** Eine prominente Schaltfläche zum Erstellen einer neuen Regel für den maximalen Einkaufswert.

**Beim Hinzufügen oder Bearbeiten einer Regel werden Sie typischerweise die folgenden Felder finden:**

1. **Kategorie auswählen:**

   - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl, für welche spezifische Produktkategorie diese Regel für den maximalen Einkaufswert gelten soll. Sie sehen normalerweise ein Dropdown-Menü oder einen Kategoriebaum-Selektor.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn eine Kategorie ausgewählt ist:* Die Regel gilt für alle Produkte innerhalb dieser Kategorie (und oft auch für deren Unterkategorien, abhängig von der Modullogik).
     - *Wenn keine Kategorie ausgewählt ist (oder wenn Sie sie ändern):* Die Regel ist entweder ungültig oder gilt für eine andere Kategorie.
   - **Empfohlener Wert:** Wählen Sie die spezifische Kategorie aus, die Sie begrenzen möchten.
   - **Händlerszenario / Beispiel:** Sie möchten den Kauf von „Elektronik“-Produkten begrenzen. Sie würden „Elektronik“ aus der Liste auswählen.
2. **Maximaler Einkaufswert:**

   - **Was diese Einstellung bewirkt:** Dies ist der numerische Wert (in der Standardwährung Ihres Shops), der den höchsten zulässigen Gesamtbetrag für Produkte aus der ausgewählten Kategorie im Warenkorb eines Kunden darstellt.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf einen bestimmten Wert eingestellt (z.B. 500):* Kunden können nicht mehr als 500 Einheiten Ihrer Standardwährung an Produkten aus der ausgewählten Kategorie in ihrem Warenkorb haben.
     - *Wenn auf 0 gesetzt oder leer gelassen (falls erlaubt):* Dies könnte die Regel für die Kategorie deaktivieren oder als ungültige Eingabe betrachtet werden.
   - **Empfohlener Wert:** Ein positiver numerischer Wert, der Ihr gewünschtes Limit darstellt (z.B. `250.00`).
   - **Händlerszenario / Beispiel:** Sie möchten „Limitierte Kunstdrucke“ auf maximal 250 € pro Bestellung begrenzen. Sie würden hier `250` eingeben. Das Modul berechnet automatisch äquivalente Werte für andere Währungen, falls Ihr Shop diese unterstützt.

**Auswirkung von Änderungen:**

- **Hinzufügen einer neuen Regel:** Setzt den maximalen Einkaufswert für die ausgewählte Kategorie sofort in Ihrem gesamten Shop durch. Kunden wird es untersagt, dieses Limit zu überschreiten.
- **Bearbeiten einer Regel:** Aktualisiert den Maximalwert für eine bestehende Kategorie. Das neue Limit tritt sofort in Kraft.
- **Löschen einer Regel:** Entfernt die Beschränkung für diese Kategorie. Kunden sind nicht länger in ihren Einkäufen aus dieser Kategorie begrenzt.

**Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**

1. Überprüfen Sie regelmäßig Ihre Produktkategorien und identifizieren Sie diejenigen, die von einem Einkaufswertlimit profitieren könnten (z.B. neue Produkte mit hoher Nachfrage, Artikel mit begrenztem Lagerbestand oder Produkte mit spezifischen Vertriebsvereinbarungen).
2. Navigieren Sie zum Konfigurationsbildschirm „Maximaler Einkaufswert nach Kategorien“.
3. Verwenden Sie die Schaltfläche „Neue Regel hinzufügen“, um neue Limits zu erstellen.
4. Überwachen Sie Kundenfeedback oder Bestellmuster, um bestehende Limits bei Bedarf mit der Aktion „Bearbeiten“ anzupassen.
5. Wenn eine Produktlinie oder Kategorie kein Limit mehr benötigt, verwenden Sie die Aktion „Löschen“, um die Regel zu entfernen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| AdminMaobcController (Regelverwaltung) | **Kategorie auswählen** | Spezifischer Kategoriename | Definiert, für welche Produktkategorie der Maximalwert gilt. |
| AdminMaobcController (Regelverwaltung) | **Maximaler Einkaufswert** | Numerischer Wert (z.B. `250.00`) | Legt den höchsten Gesamtwert fest, der für Produkte aus der ausgewählten Kategorie in einer einzigen Bestellung zulässig ist (in Standardwährung). Konvertiert automatisch für andere Währungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe ein Limit festgelegt, aber Kunden können es immer noch überschreiten. Was ist falsch?**
A1:

- **Kategorienzuweisung prüfen:** Stellen Sie sicher, dass die betreffenden Produkte der Kategorie korrekt zugewiesen sind, für die Sie das Limit festgelegt haben.
- **Modul aktiviert:** Überprüfen Sie, ob das Modul „Maximaler Einkaufswert nach Kategorien“ unter **Module > Modul-Manager** aktiviert ist.
- **Regel aktiv:** Gehen Sie zur Modulkonfiguration und bestätigen Sie, dass die Regel für die spezifische Kategorie vorhanden ist und einen gültigen Maximalwert hat.
- **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort wirksam werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.

**F2: Das Modul zeigt die falsche Währung an oder konvertiert nicht korrekt.**
A2: Das Modul verwendet automatisch die Standardwährung Ihres Shops für den von Ihnen eingegebenen Wert und konvertiert diesen dann für andere Währungen.

- **Standardwährung:** Stellen Sie sicher, dass Ihre Standardwährung unter **International > Währungen** korrekt eingestellt ist. Der Wert, den Sie in der Modulkonfiguration eingeben, sollte immer in dieser Standardwährung sein.
- **Wechselkurse:** Überprüfen Sie Ihre Wechselkurse unter **International > Währungen**, um sicherzustellen, dass sie aktuell und genau für die von Ihnen unterstützten Währungen sind.

**F3: Kann ich unterschiedliche Limits für verschiedene Kundengruppen festlegen?**
A3: Dieses spezifische Modul legt ein globales Limit pro Kategorie fest, das für alle Kunden gilt. Wenn Sie unterschiedliche Limits für bestimmte Kundengruppen (z.B. Großhandel vs. Einzelhandel) benötigen, benötigen Sie ein fortschrittlicheres Modul oder eine kundenspezifische Entwicklung.

**F4: Wie übersetze ich die Fehlermeldungen, die Kunden angezeigt werden?**
A4: Die Front-Office-Nachrichten des Moduls sind in der Regel über das PrestaShop-Übersetzungssystem übersetzbar:

1. Gehen Sie zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“.
3. Wählen Sie Ihr Theme, die Sprache und dann „Maximaler Einkaufswert nach Kategorien“ aus der Modulliste.
4. Sie können dann die Textzeichenfolgen, die das Modul Ihren Kunden anzeigt, finden und bearbeiten.

**F5: Das Modul scheint mit einem anderen Modul in meinem Warenkorb/Checkout zu kollidieren.**
A5: Modulkonflikte können manchmal auftreten.

- **Problem isolieren:** Deaktivieren Sie vorübergehend andere Module, die mit dem Warenkorb oder der Produktseite interagieren, einzeln, um zu sehen, ob der Konflikt behoben wird.
- **Theme-Kompatibilität:** Wenn Sie ein benutzerdefiniertes Theme verwenden, kann es spezifische Überschreibungen geben, die stören. Prüfen Sie, ob das Problem mit dem Standard-PrestaShop-Theme weiterhin besteht.
- **Support kontaktieren:** Wenn Sie den Konflikt nicht identifizieren können, sammeln Sie Details (welche Module, welcher genaue Fehler) und kontaktieren Sie den MyPresta.eu-Support für Unterstützung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Maximaler Einkaufswert nach Kategorien“ (`maobc`) folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller). Es verwendet hauptsächlich einen Admin Controller zur Verwaltung der Konfiguration und Regeln sowie einen Front Controller, um AJAX-Anfragen im Zusammenhang mit Warenkorb-Updates abzufangen. Die Kernlogik befindet sich in der Hauptmodulklasse, die sich in verschiedene PrestaShop-Ereignisse einklinkt, um die kategoriebasierten Wertlimits durchzusetzen. Es speichert seine Konfiguration in der Tabelle `ps_configuration` und verwaltet seine Regeln über eine benutzerdefinierte Tabelle und einen Admin Controller.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/ajax.php`
    - **Klassenname**: `MaobcAjaxModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller ist für die Bearbeitung von AJAX-Anfragen aus dem Front-Office verantwortlich, hauptsächlich jener, die sich auf das Hinzufügen von Produkten zum Warenkorb oder das Aktualisieren von Warenkorbmengen beziehen. Er fängt diese Anfragen ab, um eine Echtzeitvalidierung gegen die definierten Regeln für den maximalen Einkaufswert durchzuführen, bevor PrestaShop das Warenkorb-Update verarbeitet. Er gibt JSON-Antworten zurück, die den Erfolg oder Misserfolg mit entsprechenden Meldungen anzeigen.
  - `controllers/front/index.php`
    - **Klassenname**: `MaobcIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller könnte als Fallback oder einfacher Einstiegspunkt dienen, aber angesichts der Funktionalität des Moduls ist `ajax.php` der primäre Front-Office-Interaktionspunkt. Er könnte eine einfache Seite rendern oder umleiten, wenn direkt darauf zugegriffen wird.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMaobc.php`
    - **Klassenname**: `AdminMaobcController` (erweitert `ModuleAdminController`)
    - **Tab-Name**: „Maximaler Einkaufswert nach Kategorien“ (oder ähnlich, zugänglich über die Schaltfläche „Konfigurieren“ des Moduls).
    - **Verwaltete Entität**: Dieser Controller verwaltet die benutzerdefinierte `maobc`-Entität, die die einzelnen Regeln für maximale Einkaufswerte pro Kategorie darstellt. Er behandelt die CRUD-Operationen (Create, Read, Update, Delete) für diese Regeln.
    - **Verantwortlichkeit**: Zeigt eine Liste (Raster) aller konfigurierten Regeln an, ermöglicht Administratoren das Hinzufügen neuer Regeln, das Bearbeiten bestehender Regeln (Auswahl einer Kategorie und Festlegen eines Maximalwerts) und das Löschen von Regeln. Er interagiert mit der internen Datenspeicherung des Moduls (wahrscheinlich eine benutzerdefinierte Datenbanktabelle oder `ps_configuration`-Einträge).
  - `controllers/admin/index.php`
    - **Klassenname**: `AdminMaobcIndexController` (erweitert `ModuleAdminController`)
    - **Verantwortlichkeit**: Ähnlich wie der Front-Office `index.php` könnte dies ein einfacher Einstiegspunkt oder ein Fallback sein. Der `AdminMaobcController` ist der primäre Controller zur Verwaltung der Modulregeln.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass die Kernlogik und Datenverarbeitung des Moduls wahrscheinlich direkt in die Hauptmoduldatei (`maobc/index.php`) integriert oder über die Standard-PrestaShop-Klasse `Configuration` für Einstellungen und möglicherweise eine benutzerdefinierte Datenbanktabelle, die direkt vom `AdminMaobcController` verwaltet wird, ohne ein dediziertes `ObjectModel`, gehandhabt werden.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/maobc.js`
  - **Umfang**: Front-Office.
  - **Details**: Dieses Skript ist wahrscheinlich für clientseitige Interaktionen im Zusammenhang mit Warenkorb-Updates verantwortlich. Es könnte:
    - Standard-PrestaShop-AJAX-Warenkorbfunktionen (z.B. Klicks auf die Schaltfläche `In den Warenkorb`) überschreiben oder erweitern.
    - AJAX-Antworten von `controllers/front/ajax.php` abfangen, um dem Benutzer benutzerdefinierte Fehlermeldungen anzuzeigen, wenn ein Maximalwert überschritten wird.
    - Potenziell die Benutzeroberfläche aktualisieren (z.B. Schaltflächen deaktivieren, Warnungen anzeigen) basierend auf Validierungsergebnissen.
    - Es wird wahrscheinlich `jQuery` oder `prestashop.on`-Ereignisse verwenden, um seine Logik zu binden.

### 4.5 CSS-Stylesheets (`views/css/`)

- `views/css/maobc.css`
  - **Umfang**: Front-Office.
  - **Details**: Dieses Stylesheet bietet benutzerdefinierte Stile für die Front-Office-Elemente des Moduls, hauptsächlich die Benachrichtigungen, die Kunden angezeigt werden, wenn ein maximaler Einkaufswert überschritten wird.
  - **Wichtige CSS-Klassenselektoren**: Entwickler sollten diese Datei auf Klassen wie `.maobc-error-message`, `.maobc-alert` oder ähnliche überprüfen, die in der `custom.css` oder `theme.css` ihres Themes überschrieben werden können, um dem Branding des Shops zu entsprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - Das Moduldossier listet keine Templates explizit in `views/templates/hook/` auf. Dies deutet darauf hin, dass Nachrichten oder dynamische Inhalte direkt über JavaScript injiziert oder von der Hauptmoduldatei mit `display()`-Methoden gerendert werden könnten.
- **Admin-Templates (`views/templates/admin/`)**:

  - Das Moduldossier listet keine Templates explizit in `views/templates/admin/` auf. Der `AdminMaobcController` verwendet wahrscheinlich Standard-PrestaShop-Hilfsformulare (`HelperList`, `HelperForm`) für sein Raster und seine Konfigurationsformulare, die ihren HTML-Code dynamisch generieren.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Zweck**: Dieses Template wird wahrscheinlich verwendet, um die benutzerdefinierte Fehlermeldung auf der Warenkorbseite anzuzeigen, wenn der maximale Einkaufswert für eine Kategorie überschritten wird. Es würde die HTML-Struktur für die Warnung oder Benachrichtigung enthalten, die den Kunden über das Limit informiert. Es ist wahrscheinlich in einen `displayShoppingCartFooter` oder ähnlichen Hook eingehängt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt wahrscheinlich eine benutzerdefinierte Datenbanktabelle (z.B. `ps_maobc_rules`), um die Kategorie-ID und den zugehörigen maximalen Einkaufswert für jede Regel zu speichern.
  - Konfigurationswerte (z.B. Modul-Aktivierungsstatus, allgemeine Einstellungen) werden in der Tabelle `ps_configuration` gespeichert, typischerweise mit dem Präfix `MAOBC_`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich aller Front-Office-Seiten gerendert. | Potenziell zum Laden von `maobc.js` und `maobc.css` Assets oder zum Injizieren von JavaScript-Variablen verwendet. |
| `displayRightColumn` / `displayLeftColumn` | Rendert Inhalte in den Seitenleisten. | Weniger wahrscheinlich für dieses Modul, könnte aber verwendet werden, um eine statische Nachricht über Einkaufslimits anzuzeigen. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Rendert auf der Produktseite. | Könnte verwendet werden, um eine Warnmeldung auf der Produktseite anzuzeigen, wenn der Artikel zu einer eingeschränkten Kategorie gehört. |
| `displayShoppingCartFooter` / `displayShoppingCart` | Rendert auf der Warenkorbseite. | Wird verwendet, um das Template `displayShoppingCart.tpl` mit Fehlermeldungen anzuzeigen, wenn Limits überschritten werden. |
| `actionCartSave` | Wird ausgeführt, nachdem ein Warenkorb gespeichert wurde (z.B. Produkt hinzugefügt/entfernt, Menge geändert). | Entscheidend für die serverseitige Validierung des Warenkorbinhalts gegen Kategorielimits. Hier verhindert die Kernlogik ungültige Warenkorbzustände. |
| `actionAjaxDieCartController` | Wird vor einer AJAX-Antwort vom CartController ausgeführt. | Ermöglicht dem Modul, AJAX-Antworten abzufangen und zu ändern, indem benutzerdefinierte Fehlermeldungen eingefügt werden, wenn Limits während AJAX-Warenkorb-Updates überschritten werden. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, bevor ein Front-Controller seine Ausgabe rendert. | Wird verwendet, um Front-Office-CSS- und JavaScript-Dateien zu registrieren. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Maximaler Einkaufswert nach Kategorien“ melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität oder Integration des Moduls zur Verfügung.
