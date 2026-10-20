---
title: "CMS-Seiten für Gruppen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „CMS-Seiten für Gruppen“ von MyPresta.eu."
sidebar:
  label: "CMS-Seiten für Gruppen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul CMS pages for groups auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/cms-pages-for-groups.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/cms-pages-for-groups/)
>
> ---


# CMS-Seiten für Gruppen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > CMS-Seiten für Gruppen)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie verwalten, welche Kundengruppen auf bestimmte CMS-Seiten zugreifen können.

Wenn Sie die Konfigurationsseite zum ersten Mal aufrufen, sehen Sie eine Liste aller Ihrer vorhandenen CMS-Seiten. Für jede CMS-Seite finden Sie Optionen zur Steuerung ihrer Sichtbarkeit.

**Gesamtseitenstruktur:**
Die Konfigurationsseite zeigt eine Tabelle an. Jede Zeile in der Tabelle repräsentiert eine Ihrer CMS-Seiten. Für jede CMS-Seite sehen Sie:

- **Seitenname:** Der Titel Ihrer CMS-Seite (z. B. „Über uns“, „Allgemeine Geschäftsbedingungen“).
- **Kundengruppen:** Eine Liste von Kontrollkästchen, eines für jede in Ihrem PrestaShop-Shop definierte Kundengruppe (z. B. „Besucher“, „Gast“, „Kunde“, „Großhandel“).

**Was diese Einstellung bewirkt:**
Für jede CMS-Seite wählen Sie die Kundengruppen aus, die diese spezifische Seite **anzeigen dürfen**. Wenn ein Kunde nicht zu einer der ausgewählten Gruppen für eine bestimmte Seite gehört, wird ihm der Zugriff auf diese Seite verweigert.

**Auswirkungen der Änderung dieser Einstellung:**

- **Wenn eine Gruppe für eine CMS-Seite aktiviert ist:** Kunden, die dieser Gruppe angehören, können die CMS-Seite normal anzeigen.
- **Wenn eine Gruppe für eine CMS-Seite deaktiviert ist:** Kunden, die dieser Gruppe angehören, können die CMS-Seite **nicht** anzeigen. Wenn sie versuchen, darauf zuzugreifen, werden sie auf eine „Seite nicht gefunden“-Fehlerseite umgeleitet.
- **Wenn keine Gruppen für eine CMS-Seite ausgewählt sind:** Dies bedeutet, dass die Seite effektiv vor *allen* Kunden verborgen ist, da keine Gruppe die Berechtigung hat, sie anzuzeigen. Dies kann nützlich für Seiten im Aufbau oder nur für interne Inhalte sein.
- **Wenn alle Gruppen für eine CMS-Seite ausgewählt sind:** Dies bedeutet, dass die Seite für jeden sichtbar ist, wodurch das Standardverhalten von PrestaShop für diese spezifische Seite wiederhergestellt wird.

**Empfohlener Wert:**
Dies hängt vollständig von Ihren Geschäftsanforderungen ab.

- Für Standardseiten wie „Über uns“ oder „Kontakt“ werden Sie wahrscheinlich alle Gruppen aktivieren.
- Für spezifische rechtliche Bedingungen für B2B aktivieren Sie möglicherweise nur Ihre Gruppe „Großhandel“.
- Für eine Seite „Vorteile des VIP-Clubs“ aktivieren Sie möglicherweise nur Ihre Gruppe „VIP-Kunde“.

**Händlerszenario / Beispiel:**
Nehmen wir an, Sie haben drei Kundengruppen: „Besucher“ (nicht angemeldet), „Kunde“ (standardmäßige registrierte Benutzer) und „Großhandel“ (B2B-Kunden).

1. **Szenario 1: Seite „Über uns“**

   - **Zweck:** Allgemeine Informationen für alle.
   - **Aktion:** Aktivieren Sie „Besucher“, „Kunde“ und „Großhandel“ für die Seite „Über uns“.
   - **Ergebnis:** Jeder kann die Seite „Über uns“ sehen.
2. **Szenario 2: Seite „Großhandels-AGB“**

   - **Zweck:** Spezifische rechtliche Bedingungen nur für Ihre B2B-Kunden.
   - **Aktion:** Aktivieren Sie nur „Großhandel“ für die Seite „Großhandels-AGB“.
   - **Ergebnis:** Nur Kunden der Gruppe „Großhandel“ können diese Seite sehen. Den Gruppen „Besucher“ und „Kunde“ wird der Zugriff verweigert.
3. **Szenario 3: Seite „Details zum Treueprogramm“**

   - **Zweck:** Informationen für registrierte Kunden über ihre Treuepunkte.
   - **Aktion:** Aktivieren Sie „Kunde“ und „Großhandel“ (vorausgesetzt, Großhandelskunden können auch Teil des Treueprogramms sein) für die Seite „Details zum Treueprogramm“.
   - **Ergebnis:** Nur angemeldete Kunden (Standard oder Großhandel) können diese Seite sehen. Besuchern wird der Zugriff verweigert.

**Speichern Ihrer Änderungen:**
Nachdem Sie Ihre Auswahl für alle CMS-Seiten getroffen haben, denken Sie daran, auf die Schaltfläche **„Speichern“** (normalerweise am unteren Rand der Seite) zu klicken, um Ihre Änderungen zu übernehmen.

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | **CMS-Seitenname** (z. B. „Über uns“) | Variiert je nach Seite | Steuert, welche Kundengruppen diese spezifische CMS-Seite anzeigen können. |
| | Kontrollkästchen für Gruppe **„Besucher“** | Variiert | Wenn aktiviert, können nicht angemeldete Benutzer die Seite anzeigen. |
| | Kontrollkästchen für Gruppe **„Gast“** | Variiert | Wenn aktiviert, können Benutzer, die als Gast ausgecheckt haben, die Seite anzeigen. |
| | Kontrollkästchen für Gruppe **„Kunde“** | Variiert | Wenn aktiviert, können standardmäßige registrierte Kunden die Seite anzeigen. |
| | Kontrollkästchen für Gruppe **„Großhandel“** (oder jede benutzerdefinierte Gruppe) | Variiert | Wenn aktiviert, können Kunden dieser spezifischen Gruppe die Seite anzeigen. |
| | **Speichern-Schaltfläche** | N/A | Wendet alle ausgewählten Sichtbarkeitseinstellungen auf die CMS-Seiten an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe eine CMS-Seite eingeschränkt, aber sie erscheint immer noch in meinem Footer-/Header-Menü. Warum?**
A1: Dieses Modul steuert den *Zugriff* auf den Seiteninhalt, nicht dessen Sichtbarkeit in Navigationsmenüs. Wenn Sie den Link selbst vor bestimmten Gruppen verbergen möchten, müssen Sie entweder:
\* Den Link manuell aus den Template-Dateien Ihres Themes entfernen (z. B. `footer.tpl`, `header.tpl`).
\* Ein Menüverwaltungsmodul verwenden, das eine gruppenbasierte Sichtbarkeit für Menüpunkte bietet.
\* Wenn ein Kunde auf einen eingeschränkten Link klickt, wird ihm der Zugriff auf den Seiteninhalt trotzdem verweigert.

**F2: Ein Kunde ist angemeldet, kann aber eine Seite, die ich für seine Gruppe erlaubt habe, immer noch nicht sehen. Was ist falsch?**
A2:
\* **Cache leeren:** Beginnen Sie immer damit, Ihren PrestaShop-Cache zu leeren. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
\* **Gruppenzuweisung überprüfen:** Überprüfen Sie nochmals, ob der Kunde tatsächlich der/den korrekten Kundengruppe(n) zugewiesen ist, die Sie für die CMS-Seite erlaubt haben. Sie können dies unter **Kunden > Kunden** überprüfen, indem Sie das Kundenprofil bearbeiten.
\* **Modulkonfiguration:** Überprüfen Sie die Konfigurationsseite des Moduls erneut und stellen Sie sicher, dass das richtige Gruppen-Kontrollkästchen für diese spezifische CMS-Seite aktiviert ist.
\* **Browser-Cache:** Bitten Sie den Kunden, seinen Browser-Cache zu leeren oder versuchen Sie, die Seite in einem Inkognito-/privaten Browsing-Fenster aufzurufen.

**F3: Kann ich eine benutzerdefinierte Nachricht anstelle einer „Seite nicht gefunden“-Fehlermeldung anzeigen, wenn der Zugriff verweigert wird?**
A3: Dieses Modul leitet in seiner aktuellen Version auf die Standard-PrestaShop-Seite „Seite nicht gefunden“ um. Eine Anpassung würde Theme-Modifikationen oder ein zusätzliches Modul erfordern, das speziell benutzerdefinierte Fehlerseiten basierend auf Zugriffsverweigerung handhabt.

**F4: Wird dieses Modul meinen Shop verlangsamen?**
A4: Nein, das Modul ist sehr leichtgewichtig. Es überschreibt einen PrestaShop-Core-Controller, um die Berechtigungen der Kundengruppe zu überprüfen, bevor eine CMS-Seite geladen wird. Diese Überprüfung ist effizient und sollte die Leistung Ihres Shops nicht merklich beeinträchtigen.

**F5: Ich habe PrestaShop aktualisiert, und jetzt funktioniert das Modul nicht mehr. Was soll ich tun?**
A5:
\* **Modulversion überprüfen:** Stellen Sie sicher, dass Sie die neueste Version des Moduls „CMS-Seiten für Gruppen“ von Ihrem MyPresta.eu-Konto haben, die mit Ihrer neuen PrestaShop-Version kompatibel ist.
\* **Neu installieren/neu konfigurieren:** Manchmal müssen Module nach einem größeren PrestaShop-Update neu installiert oder neu konfiguriert werden. Versuchen Sie, das Modul zu deinstallieren und dann neu zu installieren (Ihre Einstellungen sollten erhalten bleiben, aber sichern Sie immer zuerst). Überprüfen Sie dann Ihre Einstellungen auf der Konfigurationsseite des Moduls erneut.
\* **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache nach jedem Update oder jeder Moduländerung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „CMS-Seiten für Gruppen“ funktioniert, indem es den Core `CmsController` im Front Office von PrestaShop überschreibt. Dies ermöglicht es, Anfragen für CMS-Seiten abzufangen, *bevor* sie gerendert werden, und eine benutzerdefinierte Zugriffslogik basierend auf den im Back Office des Moduls konfigurierten Kundengruppenberechtigungen anzuwenden. Das Modul speichert seine Konfiguration direkt in der Tabelle `ps_configuration`.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `groupscms/override/controllers/front/CmsController.php`
    - **Klassenname & Elternklasse**: `CmsController` (überschreibt den Core `CmsController`)
    - **Verantwortlichkeit**: Dies ist die kritische Komponente. Sie erweitert den ursprünglichen `CmsController`, um eine `init()`-Methode hinzuzufügen. Innerhalb von `init()` ruft sie die ID der aktuellen CMS-Seite ab und überprüft die Modulkonfiguration (`Configuration::get('CMSG_CMS_ID_' . (int)$cms->id)`), um festzustellen, welche Kundengruppen Zugriff haben. Wenn der aktuelle Kunde (oder Besucher) nicht in einer erlaubten Gruppe ist, wird er auf die „Seite nicht gefunden“-Seite umgeleitet (`$this->redirect_after = '404';`). Dies stellt sicher, dass unautorisierte Benutzer keine eingeschränkten CMS-Inhalte anzeigen können.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration des Moduls wird direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Core-Klassen & Modelle (`classes/`)

Keine. Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen. Es interagiert direkt mit bestehenden PrestaShop `CMS`- und `Group`-Objekten und speichert seine Konfiguration in `ps_configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

Keine. Das Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- `groupscms/css.css`
  - **Geltungsbereich**: Styling des Back-Office-Admin-Formulars.
  - **Wichtige UI-Komponenten und Container, die gestylt werden**: Dieses Stylesheet wird wahrscheinlich verwendet, um die Konfigurationstabelle des Moduls im PrestaShop Back Office zu stylen und sicherzustellen, dass sie mit dem PrestaShop-Admin-Theme konsistent aussieht. Es könnte Stile für die Tabellenzeilen, Kontrollkästchen oder Beschriftungen innerhalb des Konfigurationsformulars des Moduls definieren.
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können**: Spezifische Selektoren wären in der Datei zu finden, aber typischerweise würden sie Elemente innerhalb der `getContent()`-Ausgabe des Moduls ansprechen, wie z. B. `table.groupscms_table`, `tr.groupscms_row`, `input[type="checkbox"].groupscms_checkbox` usw.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Keine. Das Modul rendert keine Inhalte über Standard-Front-Office-Hooks.
- **Admin-Templates (`views/templates/admin/`)**:

  - `groupscms/admin.tpl`
    - **Zweck**: Dieses Template wird von der `getContent()`-Methode der Hauptmoduldatei (`groupscms.php`) gerendert. Es generiert die gesamte Konfigurationsoberfläche für das Modul im PrestaShop Back Office. Dies umfasst die Tabelle, die alle CMS-Seiten auflistet, und die Kontrollkästchen für jede Kundengruppe.
  - `groupscms/cms.tpl`
    - **Zweck**: Dieses Template ist wahrscheinlich eine Inklusion oder ein Partial, das innerhalb von `admin.tpl` verwendet wird, um einzelne Zeilen oder Abschnitte im Zusammenhang mit CMS-Seiten innerhalb der Konfigurationstabelle zu rendern. Es würde die Schleife zum Anzeigen jeder CMS-Seite und ihrer zugehörigen Gruppen-Kontrollkästchen enthalten.
- **Front-Office-Templates (`views/templates/front/`)**: Keine. Das Modul fügt keine neuen Front-Office-Templates hinzu. Es steuert den Zugriff auf bestehende CMS-Seiten-Templates.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationsdaten werden in der Tabelle `ps_configuration` gespeichert.

  - **Konfigurationsschlüssel**:
    - `CMSG_CMS_ID_[CMS_ID]`: Speichert eine durch Kommas getrennte Zeichenfolge von `group_id`-Werten für jede CMS-Seite. Zum Beispiel könnte `CMSG_CMS_ID_12` `"1,2,3"` speichern, was bedeutet, dass Gruppen mit den IDs 1, 2 und 3 Zugriff auf die CMS-Seite mit der ID 12 haben.
    - `groupscms_many_page`: (Wahrscheinlich ein internes Flag oder eine veraltete Einstellung, nicht direkt vom Benutzer konfigurierbar).
    - `mypresta_updates`, `update_`, `updatev_`: Dies sind gängige Schlüssel, die von MyPresta.eu-Modulen für Update-Prüfungen und Versionsverfolgung verwendet werden.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (CSS/JS) einstellt. | Wird vom Modul verwendet, um sein `css.css`-Stylesheet für die Back-Office-Konfigurationsseite einzubinden. |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich des Back Office ausgeführt. | Wird oft zum Einbinden globaler Admin-CSS/JS oder für Update-Prüfungen verwendet. Das Modul könnte dies für seinen Update-Mechanismus nutzen. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „CMS-Seiten für Gruppen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
