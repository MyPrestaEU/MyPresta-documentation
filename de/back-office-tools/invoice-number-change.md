---
title: "Rechnungsnummer ändern – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Rechnungsnummer ändern' von MyPresta.eu."
sidebar:
  label: "Rechnungsnummer ändern – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Invoice number change auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/invoice-number-change.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/invoice-number-change/)
>
> ---


# Rechnungsnummer ändern

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Navigieren Sie nach der Installation zu **Module > Modul-Manager** und suchen Sie nach „Rechnungsnummer ändern“. Klicken Sie auf die Schaltfläche „Konfigurieren“.

Dieses Modul verfügt über keinen separaten Konfigurationsbildschirm mit mehreren Einstellungen. Seine Funktionalität ist direkt in die Bestelldetailseite in Ihrem Back Office integriert. Die Schaltfläche „Konfigurieren“ bestätigt lediglich, dass das Modul installiert und einsatzbereit ist.

Die Kernfunktionalität dieses Moduls besteht darin, ein neues Feld hinzuzufügen oder eine bestehende Anzeige auf der Bestelldetailseite zu ändern, sodass Sie die Rechnungsnummer direkt bearbeiten können.

**So verwenden Sie das Modul:**

1. **Navigieren Sie zu einer Bestellung:** Gehen Sie in Ihrem PrestaShop Back Office zu **Bestellungen > Bestellungen**.
2. **Wählen Sie eine Bestellung aus:** Klicken Sie auf eine beliebige Bestellung, um deren Details anzuzeigen.
3. **Suchen Sie den Rechnungsbereich:** Scrollen Sie auf der Bestelldetailseite nach unten, bis Sie den Bereich „Dokumente“ oder „Rechnungen“ finden.
4. **Rechnungsnummer bearbeiten:** Sie sehen nun ein bearbeitbares Feld oder eine Schaltfläche neben der Rechnungsnummer, mit der Sie diese ändern können.
   - **Was diese Einstellung bewirkt:** Diese Funktion ermöglicht es Ihnen, direkt eine neue Rechnungsnummer für eine bestimmte Rechnung einzugeben, die mit der aktuellen Bestellung verknüpft ist.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn Sie eine neue Nummer eingeben und speichern:* Die Rechnungsnummer für diese spezifische Bestellrechnung wird in Ihrer Datenbank aktualisiert und auf dem Rechnungsdokument selbst (falls neu generiert oder angezeigt) widergespiegelt. Diese Änderung ist dauerhaft und wirkt sich auf Ihre Finanzunterlagen aus.
   - **Empfohlener Wert:** Ändern Sie Rechnungsnummern nur, wenn dies unbedingt erforderlich ist, und überprüfen Sie die Genauigkeit immer zweimal. Stellen Sie sicher, dass die neue Nummer Ihrem internen Nummerierungsschema oder den gesetzlichen Anforderungen entspricht.
   - **Händlerszenario / Beispiel:** Eine Bestellung wurde ursprünglich als INV00123 in Rechnung gestellt. Aufgrund einer Datenmigration muss diese Rechnung INV2024-005 sein. Sie würden zur Bestellung navigieren, INV00123 finden, auf Bearbeiten klicken, INV2024-005 eingeben und speichern.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Bestelldetailseite (Abschnitt Dokumente/Rechnungen) | Rechnungsnummer (bearbeitbares Feld) | N/A (abhängig von bestehender Rechnung) | Ermöglicht die direkte Änderung einer Rechnungsnummer für eine bestimmte Bestellung. Entscheidend für Korrekturen, Compliance oder Integration mit externen Systemen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul installiert, sehe aber keine neue Einstellungsseite. Funktioniert es?**
A1: Ja, das Modul funktioniert wie vorgesehen. Dieses Modul fügt keine separate Konfigurationsseite hinzu. Seine Funktionalität ist direkt in die Bestelldetailseite integriert. Navigieren Sie zu **Bestellungen > Bestellungen**, wählen Sie eine Bestellung aus, und Sie sollten ein bearbeitbares Feld oder eine Option finden, um die Rechnungsnummer im Abschnitt „Dokumente“ oder „Rechnungen“ zu ändern.

**F2: Ich habe eine Rechnungsnummer geändert, aber die alte Nummer erscheint immer noch auf der PDF-Rechnung.**
A2: Nachdem Sie die Rechnungsnummer im Back Office geändert haben, müssen Sie möglicherweise die PDF-Rechnung für diese Bestellung neu generieren, damit die neue Nummer angezeigt wird. PrestaShop speichert PDF-Inhalte oft im Cache. Laden Sie die Rechnung erneut von der Bestelldetailseite herunter, und sie sollte die aktualisierte Nummer anzeigen.

**F3: Kann ich eine Rechnungsnummernänderung rückgängig machen?**
A3: Das Modul ermöglicht es Ihnen, die Nummer nach Belieben zu ändern. Wenn Sie sie rückgängig machen müssen, bearbeiten Sie das Feld einfach erneut und geben Sie die ursprüngliche Nummer ein (wenn Sie sich daran erinnern oder sie protokolliert haben). Das Modul selbst führt keine Änderungshistorie, daher wird eine sorgfältige Protokollierung Ihrerseits empfohlen.

**F4: Wirkt sich das Ändern einer Rechnungsnummer auf meine Buchhaltungsberichte in PrestaShop aus?**
A4: Ja, das Ändern einer Rechnungsnummer aktualisiert das Feld `invoice_number` in Ihrer Datenbank für diese spezifische Rechnung. Alle PrestaShop-Berichte, die Rechnungsnummern direkt aus der Datenbank abrufen, spiegeln die neue Nummer wider. Stellen Sie sicher, dass Ihre Änderungen mit Ihren Buchhaltungspraktiken übereinstimmen.

**F5: Das Modul scheint auf meinem benutzerdefinierten Theme nicht aktiv zu sein. Was soll ich tun?**
A5: Dieses Modul verwendet das PrestaShop-Override-System, um das Kernverhalten zu ändern und sich in Standard-Admin-Templates einzuhaken. Es sollte mit den meisten benutzerdefinierten Themes ohne Probleme funktionieren, da es nur das Back Office betrifft. Wenn Sie Probleme haben, leeren Sie zuerst Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**). Wenn das Problem weiterhin besteht, könnte es ein Konflikt mit einem anderen Modul oder einem stark angepassten Admin-Template sein. Kontaktieren Sie den MyPresta.eu-Support mit Details zu Ihrem Theme und anderen relevanten Modulen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Rechnungsnummer ändern“ (`invoicenb`) wurde entwickelt, um die Kernfunktionalität der PrestaShop-Rechnungsverwaltung zu erweitern, ohne das Datenbankschema zu ändern. Dies wird hauptsächlich durch ein `override` der Klasse `OrderInvoice` und durch das Einhaken in die Back Office-Bestelldetailseite erreicht, um eine bearbeitbare Oberfläche für die Rechnungsnummer bereitzustellen. Dieser Ansatz gewährleistet minimale Auswirkungen auf das Kernsystem, während die gewünschte Funktion bereitgestellt wird.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Funktionalität ist über die Hauptmoduldatei, Overrides und Template-Hooks integriert.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`invoicenb/override/classes/order/OrderInvoice.php`**
  - **Klassenname**: `OrderInvoice` (überschreibt die Kernklasse `OrderInvoice`)
  - **Elternklasse**: `OrderInvoiceCore`
  - **Verantwortlichkeit**: Dieser Override ist der Kern der Modulfunktionalität. Er ändert das Verhalten der Klasse `OrderInvoice`, insbesondere wie Rechnungsnummern behandelt und möglicherweise gespeichert werden. Der Override ist dafür verantwortlich, dass die Rechnungsnummer aus dem Back Office aktualisiert werden kann. Er fügt wahrscheinlich eine Methode hinzu oder ändert eine bestehende, um das Speichern einer neuen Rechnungsnummer zu erleichtern, wenn diese über die Admin-Oberfläche übermittelt wird.
  - **Datenbanktabelle**: `ps_order_invoice` (oder Ihr Tabellenpräfix)
  - **`$definition`-Felder**: Dieser Override arbeitet mit der bestehenden `$definition` von `OrderInvoiceCore`, insbesondere dem Feld `number`.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die interaktive Bearbeitungsfunktion wird direkt in den Smarty-Templates und potenziell über Standard-PrestaShop-AJAX-Mechanismen gehandhabt, falls eine Formularübermittlung involviert ist.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling für das bearbeitbare Feld oder die Schaltfläche auf der Bestellseite basiert auf dem Standard-Back Office-CSS von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul verwendet Templates, um das bearbeitbare Rechnungsnummernfeld in die Back Office-Bestelldetailseite einzufügen.

- **Hook-Templates (`views/templates/hook/`)**:
  - **`invoicenb/views/templates/hook/displayAdminOrder16.tpl`**
    - **Hook**: `displayAdminOrder` (für PrestaShop 1.6.x)
    - **Zweck**: Dieses Template wird auf der Bestelldetailseite in PrestaShop 1.6.x gerendert. Es fügt die HTML-Formularelemente (z. B. ein Eingabefeld und eine Speichern-Schaltfläche) ein, die es dem Administrator ermöglichen, die Rechnungsnummer für eine bestimmte Bestellung anzuzeigen und zu ändern. Es enthält wahrscheinlich Logik zur Anzeige der aktuellen Rechnungsnummer und zur Handhabung der Übermittlung einer neuen.
  - **`invoicenb/views/templates/hook/displayAdminOrder17.tpl`**
    - **Hook**: `displayAdminOrder` (für PrestaShop 1.7.x, 8.x, 9.x)
    - **Zweck**: Ähnlich wie `displayAdminOrder16.tpl`, aber angepasst an die Template-Struktur und potenziell unterschiedliche Hook-Parameter von PrestaShop 1.7.x und neueren Versionen. Es bietet die gleiche Funktionalität: Anzeige eines bearbeitbaren Rechnungsnummernfeldes auf der Bestelldetailseite.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine neuen benutzerdefinierten Datenbanktabellen. Es interagiert mit der bestehenden Tabelle `ps_order_invoice` (oder Ihrem Tabellenpräfix), um die Spalte `number` zu aktualisieren.
  - Konfigurationseinträge werden in `ps_configuration` für die internen Einstellungen des Moduls gespeichert (falls vorhanden, obwohl dieses Modul minimale explizite Einstellungen zu haben scheint).
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayAdminOrder` | Rendert Inhalte auf der Back Office-Bestelldetailseite. | Wird verwendet, um das HTML-Formular zur Bearbeitung der Rechnungsnummer direkt in die Bestellansicht einzufügen. Das Modul bietet separate Templates für PrestaShop 1.6 und 1.7+ für diesen Hook. |
  | `actionObjectOrderInvoiceUpdateAfter` | Wird ausgeführt, nachdem ein `OrderInvoice`-Objekt aktualisiert wurde. | (Implizit, wenn der Override dies verwendet) Könnte verwendet werden, um zusätzliche Aktionen oder Protokollierungen auszulösen, nachdem eine Rechnungsnummer erfolgreich geändert wurde. |
  | `actionObjectOrderInvoiceAddAfter` | Wird ausgeführt, nachdem ein `OrderInvoice`-Objekt hinzugefügt wurde. | (Implizit, wenn der Override dies verwendet) Könnte verwendet werden, um die anfängliche Rechnungsnummer bei der Erstellung zu ändern, obwohl der primäre Fokus auf der Änderung bestehender liegt. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Rechnungsnummer ändern“ verweisen wir Sie auf Ihr MyPresta.eu-Kundenkonto. Sie können die neuesten Versionen aus Ihrer Bestellhistorie herunterladen und unsere speziellen Supportkanäle für technische Unterstützung oder Anfragen nutzen.
