---
title: "Gutschrift-Nummernänderung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gutschrift-Nummernänderung“ von MyPresta.eu."
sidebar:
  label: "Gutschrift-Nummernänderung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Credit slip number change auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/credit-slip-number-change.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/credit-slip-number-change/)
>
> ---


# Gutschrift-Nummernänderung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Backoffice > Module > Konfigurieren)

Dieses Modul hat eine sehr einfache Konfigurationsseite, hauptsächlich für interne MyPresta.eu-Updates. Die Kernfunktionalität zum Ändern von Gutschriftnummern wird direkt über die Bestelldetailseite aufgerufen.

- **Menüpfad:** Backoffice > Module > Modul-Manager > Suchen Sie nach „Gutschrift-Nummernänderung“ > Klicken Sie auf „Konfigurieren“.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **MyPresta.eu-Updates** | Diese Einstellung steuert, ob das Modul nach Updates von MyPresta.eu sucht. | *Wenn aktiviert:* Das Modul sucht regelmäßig nach neuen Versionen und benachrichtigt Sie im Backoffice. *Wenn deaktiviert:* Das Modul sucht nicht automatisch nach Updates. | JA | Wenn diese Option aktiviert bleibt, stellen Sie sicher, dass Sie immer über neue Versionen, Fehlerbehebungen und Funktionserweiterungen für das Modul informiert sind. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Die primäre Funktionalität dieses Moduls ist direkt in die **Bestelldetailseite** in Ihrem PrestaShop-Backoffice integriert. Es gibt keine separaten dedizierten Admin-Bildschirme.

- **Bildschirmname & Menüpfad:** Backoffice > Bestellungen > Bestellungen > Klicken Sie auf eine beliebige Bestellung, um deren Details anzuzeigen.
- **Verfügbare Aktionen & Einstellungen:**
  - Scrollen Sie auf der Bestelldetailseite zum Abschnitt „Gutschriften“.
  - Für jede aufgelistete Gutschrift sehen Sie ein neues Eingabefeld neben ihrer aktuellen Nummer.
  - Sie können eine neue Nummer in dieses Feld eingeben.
  - Nachdem Sie die neue Nummer eingegeben haben, klicken Sie auf die Schaltfläche „Speichern“ (oder ein ähnliches Symbol, normalerweise eine Diskette oder ein Häkchen) neben dem Eingabefeld, um die Änderung zu übernehmen.
- **Auswirkung der Änderungen:**
  - Wenn Sie eine Gutschriftnummer ändern und speichern, wird die neue Nummer sofort in Ihrer PrestaShop-Datenbank aktualisiert.
  - Diese neue Nummer wird dann auf dem für diese spezifische Gutschrift generierten Gutschrift-PDF angezeigt. Sowohl Sie als auch Ihr Kunde sehen die aktualisierte Nummer auf dem Dokument.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Gehen Sie in Ihrem PrestaShop-Backoffice zu **Bestellungen > Bestellungen**.
  2. Wählen Sie die Bestellung aus, für die Sie eine Gutschriftnummer ändern müssen.
  3. Suchen Sie auf der Bestelldetailseite den Block „Gutschriften“.
  4. Finden Sie die spezifische Gutschrift, die Sie ändern möchten.
  5. Geben Sie die gewünschte neue Nummer in das dafür vorgesehene Eingabefeld ein.
  6. Klicken Sie auf das Speichern-Symbol neben dem Eingabefeld.
  7. Überprüfen Sie die Änderung, indem Sie das Gutschrift-PDF herunterladen; es sollte nun die neue Nummer anzeigen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | MyPresta.eu-Updates | JA | Steuert die automatische Update-Prüfung für das Modul. |
| Bestelldetailseite (Abschnitt Gutschriften) | Eingabefeld für Gutschriftnummer | N/A (Benutzerdefiniert) | Ermöglicht die direkte Änderung einzelner Gutschriftnummern. Änderungen werden im PDF widergespiegelt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe die Gutschriftnummer geändert, aber sie wird nicht auf dem PDF angezeigt.**
A: Stellen Sie nach dem Ändern der Nummer sicher, dass Sie auf die Schaltfläche „Speichern“ neben dem Eingabefeld geklickt haben. Generieren oder laden Sie dann das Gutschrift-PDF neu herunter. Wenn es immer noch nicht angezeigt wird, versuchen Sie, Ihren Browser-Cache oder den Smarty-Cache von PrestaShop zu leeren (Erweiterte Einstellungen > Leistung > Cache leeren).

**F: Kann ich die Nummer einer bereits validierten oder gesendeten Gutschrift ändern?**
A: Ja, das Modul ermöglicht es Ihnen, die Nummer jeder bestehenden Gutschrift zu ändern. Die Änderung betrifft nur die auf dem PDF angezeigte Nummer, nicht die zugrunde liegende Finanztransaktion selbst.

**F: Gibt es eine Möglichkeit, Gutschriftnummern in großen Mengen zu bearbeiten?**
A: Nein, dieses Modul ist für individuelle Gutschriftnummernänderungen direkt auf der Bestelldetailseite konzipiert. Es bietet keine Funktion zur Massenbearbeitung. Für Massenoperationen könnte eine kundenspezifische Entwicklung erforderlich sein.

**F: Was passiert, wenn ich eine doppelte Gutschriftnummer eingebe?**
A: Das Kernsystem von PrestaShop verhindert möglicherweise keine doppelten Gutschriftnummern, da das Modul die Nummer direkt aktualisiert. Es liegt in Ihrer Verantwortung, die Einzigartigkeit sicherzustellen, wenn Ihre Buchhaltungspraktiken dies erfordern. Das Modul erleichtert die Änderung, erzwingt jedoch keine Einzigartigkeitsbeschränkungen über das Standardverhalten von PrestaShop hinaus.

**F: Das Eingabefeld zum Ändern der Nummer wird auf meiner Bestellseite nicht angezeigt.**
A:

1. **Modulinstallation prüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** korrekt installiert und aktiviert ist.
2. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
3. **Theme-Kompatibilität:** Obwohl das Modul Standard-PrestaShop-Hooks verwendet, können stark angepasste Themes manchmal stören. Wenn das Problem weiterhin besteht, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob das Feld angezeigt wird. Wenn ja, benötigt Ihr Theme möglicherweise eine kleine Anpassung.
4. **PrestaShop-Version:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre PrestaShop-Installation heruntergeladen haben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Gutschrift-Nummernänderung“ (`creditnb`) ist ein leichtgewichtiges PrestaShop-Modul, das die Backoffice-Funktionalität erweitert, indem es ein benutzerdefiniertes Eingabefeld in den `displayAdminOrder`-Hook injiziert. Dies ermöglicht Administratoren, Gutschriftnummern direkt auf der Bestelldetailseite zu ändern. Das Modul interagiert hauptsächlich mit dem `OrderSlip`-Objekt von PrestaShop und seiner zugehörigen Datenbanktabelle, um das Feld `number` zu aktualisieren. Es nutzt die Standard-PrestaShop-Modulstruktur und das Templating.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Alle Interaktionen werden über die Hauptmoduldatei (`creditnb.php`) und Standard-PrestaShop-AJAX-Mechanismen für Formularübermittlungen innerhalb der Admin-Bestellseite abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/` ein. Es interagiert direkt mit dem nativen `OrderSlip`-Objekt von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die Funktionalität zum Speichern der neuen Gutschriftnummer wird durch die Formularübermittlung innerhalb der `displayAdminOrder`-Hook-Vorlage gehandhabt, wahrscheinlich unter Verwendung bestehender PrestaShop-AJAX- oder Formularverarbeitungsmechanismen.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling des Eingabefeldes soll vom PrestaShop-Backoffice-Theme geerbt werden.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Das Modul verwendet Hook-Vorlagen, um seine Funktionalität in das PrestaShop-Backoffice zu integrieren.

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `creditnb/views/templates/hook/displayAdminOrder16.tpl`
    - **Zweck:** Diese Vorlage ist für PrestaShop 1.6.x konzipiert (obwohl das Modul 1.7.x, 8.x, 9.x Kompatibilität auflistet, könnte diese Datei eine Legacy-Inklusion oder für breitere Kompatibilität sein). Sie rendert das Eingabefeld und die Schaltfläche zum Speichern für die Änderung von Gutschriftnummern innerhalb des Abschnitts „Gutschriften“ der Bestelldetailseite.
    - **Hook:** `displayAdminOrder`
    - **Ausgabe:** Ein HTML-Block, der ein Formularelement mit einem Eingabefeld für die Nummer jeder Gutschrift und einen Mechanismus zum Speichern des aktualisierten Wertes enthält.
  - `creditnb/views/templates/hook/displayAdminOrder17.tpl`
    - **Zweck:** Diese Vorlage ist für PrestaShop 1.7.x, 8.x und 9.x konzipiert. Sie rendert das Eingabefeld und die Schaltfläche zum Speichern für die Änderung von Gutschriftnummern innerhalb des Abschnitts „Gutschriften“ der Bestelldetailseite, angepasst an die neuere Backoffice-Benutzeroberfläche.
    - **Hook:** `displayAdminOrder`
    - **Ausgabe:** Ein HTML-Block, der ein Formularelement mit einem Eingabefeld für die Nummer jeder Gutschrift und einen Mechanismus zum Speichern des aktualisierten Wertes enthält.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine neuen benutzerdefinierten Datenbanktabellen.
  - Es ändert die Spalte `number` in der Tabelle `ps_order_slip` (oder `_order_slip`), die Teil des PrestaShop-Kerndatenbankschemas ist.
  - Konfigurationseinstellungen (`mypresta_updates`, `update_`, `updatev_`) werden in der Tabelle `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayAdminOrder` | Rendert Inhalte auf der PrestaShop-Backoffice-Bestelldetailseite. | Injiziert das benutzerdefinierte Eingabefeld und den Speichermechanismus zum Ändern von Gutschriftnummern direkt in den Abschnitt „Gutschriften“ der Bestellansicht. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Gutschrift-Nummernänderung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung unserer Module sicherzustellen.
