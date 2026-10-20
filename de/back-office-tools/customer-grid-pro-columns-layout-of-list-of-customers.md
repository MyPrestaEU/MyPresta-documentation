---
title: "Customer Grid Pro - Spalten & Layout der Kundenliste - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Customer Grid Pro - Spalten & Layout der Kundenliste von MyPresta.eu."
sidebar:
  label: "Customer Grid Pro - Spalten & Layout der Kundenliste"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Customer Grid Pro - columns & layout of list of customers auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/customer-grid-pro-columns-layout-of-list-of-customers.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/customer-grid-pro-columns-layout-of-list-of-customers/)
>
> ---


# Customer Grid Pro - Spalten & Layout der Kundenliste

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x, 8.x, 1.7.8.x, 1.7.7.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation des Moduls klicken Sie auf "Konfigurieren", um auf dessen Einstellungen zuzugreifen. Auf dieser Seite können Sie auswählen, welche Spalten in Ihrer Kundenliste erscheinen und in welcher Reihenfolge.

Die Konfigurationsseite zeigt eine Liste aller verfügbaren Spalten für Ihr Kundenraster an. Dazu gehören Standard-PrestaShop-Spalten und neue, vom Modul hinzugefügte Spalten (wie Telefon, Adresse, Bestellstatistiken).

**So verwenden Sie die Konfigurationsoberfläche:**

1.  **Liste der verfügbaren Spalten:** Auf der linken Seite sehen Sie eine Liste aller Spalten, die *angezeigt werden können*.
2.  **Liste der aktiven Spalten:** Auf der rechten Seite sehen Sie eine Liste der Spalten, die derzeit *aktiv* sind und in Ihrer Kundenliste angezeigt werden.
3.  **Eine Spalte hinzufügen:** Um eine Spalte zu Ihrer Kundenliste hinzuzufügen, ziehen Sie sie einfach aus der Liste "Verfügbare Spalten" auf der linken Seite und legen Sie sie in der Liste "Aktive Spalten" auf der rechten Seite ab.
4.  **Eine Spalte entfernen:** Um eine Spalte aus Ihrer Kundenliste zu entfernen, ziehen Sie sie aus der Liste "Aktive Spalten" auf der rechten Seite und legen Sie sie wieder in der Liste "Verfügbare Spalten" auf der linken Seite ab.
5.  **Spalten neu anordnen:** Innerhalb der Liste "Aktive Spalten" können Sie Spalten per Drag-and-Drop nach oben oder unten verschieben, um deren Anzeigereihenfolge in Ihrem Kundenraster zu ändern. Die Spalte ganz oben in der Liste erscheint zuerst (ganz links) in Ihrer Kundenliste.
6.  **Speichern-Schaltfläche:** Nach dem Vornehmen von Änderungen (Hinzufügen, Entfernen oder Neuanordnen von Spalten) denken Sie daran, auf die Schaltfläche **"Speichern"** am unteren Rand der Seite zu klicken, um Ihre neue Konfiguration zu übernehmen.

**Liste der verfügbaren Spalten und deren Zweck:**

| Spaltenname (Beispiel) | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
|---|---|---|---|---|
| **ID** | Zeigt die eindeutige Identifikationsnummer für jeden Kunden an. | *Wenn aktiv:* Zeigt die Kunden-ID an. *Wenn inaktiv:* Blendet die ID-Spalte aus. | Aktiv | Nützlich zum schnellen Referenzieren von Kunden anhand ihrer internen ID, insbesondere bei Support-Tickets. |
| **Anrede** | Zeigt die vom Kunden gewählte Anrede an (z.B. Herr, Frau). | *Wenn aktiv:* Zeigt die Anrede an. *Wenn inaktiv:* Blendet die Anrede-Spalte aus. | Aktiv (optional) | Gut für formelle Kommunikation oder wenn Ihr Unternehmen spezifische Anreden erfordert. |
| **Vorname** | Zeigt den Vornamen des Kunden an. | *Wenn aktiv:* Zeigt den Vornamen an. *Wenn inaktiv:* Blendet die Vornamen-Spalte aus. | Aktiv | Wesentlich zur Identifizierung von Kunden. |
| **Nachname** | Zeigt den Nachnamen des Kunden an. | *Wenn aktiv:* Zeigt den Nachnamen an. *Wenn inaktiv:* Blendet die Nachnamen-Spalte aus. | Aktiv | Wesentlich zur Identifizierung von Kunden. |
| **E-Mail-Adresse** | Zeigt die E-Mail-Adresse des Kunden an. | *Wenn aktiv:* Zeigt die E-Mail-Adresse an. *Wenn inaktiv:* Blendet die E-Mail-Spalte aus. | Aktiv | Entscheidend für die Kontaktaufnahme mit Kunden und oft als primärer Identifikator verwendet. |
| **Alter** | Zeigt das Alter des Kunden an (sofern Geburtsdatum angegeben). | *Wenn aktiv:* Zeigt das berechnete Alter des Kunden an. *Wenn inaktiv:* Blendet die Alters-Spalte aus. | Aktiv (optional) | Nützlich für Marketingsegmentierung oder altersbeschränkte Produkte. |
| **Registrierungsdatum** | Zeigt das Datum an, an dem der Kunde sein Konto registriert hat. | *Wenn aktiv:* Zeigt das Registrierungsdatum an. *Wenn inaktiv:* Blendet die Registrierungsdatum-Spalte aus. | Aktiv | Hilft bei der Verfolgung der Kundenakquise und der Identifizierung neuer vs. alter Kunden. |
| **Letzter Besuch** | Zeigt das Datum des letzten Logins/Besuchs des Kunden an. | *Wenn aktiv:* Zeigt das Datum des letzten Besuchs an. *Wenn inaktiv:* Blendet die Spalte für den letzten Besuch aus. | Aktiv (optional) | Nützlich zur Identifizierung aktiver vs. inaktiver Kunden für Re-Engagement-Kampagnen. |
| **Gesamtbestellungen** | Zeigt die Gesamtzahl der vom Kunden getätigten Bestellungen an. | *Wenn aktiv:* Zeigt eine Zählung aller Bestellungen an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv | Hervorragend zur Identifizierung häufiger Käufer oder Kunden mit mehreren Käufen. |
| **Gesamtausgaben** | Zeigt den gesamten vom Kunden über alle Bestellungen hinweg ausgegebenen Geldwert an. | *Wenn aktiv:* Zeigt die Summe aller Bestellsummen an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv | Entscheidend zur Identifizierung von hochwertigen Kunden (VIPs) und für das B2B-Kundenmanagement. |
| **Telefonnummer** | Zeigt die primäre Telefonnummer des Kunden an (aus seiner Standardadresse). | *Wenn aktiv:* Zeigt die Telefonnummer an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv | Wesentlich für den direkten Kontakt, insbesondere bei Lieferproblemen oder dringenden Anfragen. |
| **Mobiltelefon** | Zeigt die Mobiltelefonnummer des Kunden an (aus seiner Standardadresse). | *Wenn aktiv:* Zeigt die Mobiltelefonnummer an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv | Bietet eine alternative Kontaktmethode, oft bevorzugt für schnelle Kommunikation. |
| **Adresse 1** | Zeigt die erste Zeile der Standardadresse des Kunden an. | *Wenn aktiv:* Zeigt die Adresszeile an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (optional) | Nützlich für eine schnelle Referenz des Standorts, ohne die vollständige Adresse zu öffnen. |
| **Adresse 2** | Zeigt die zweite Zeile der Standardadresse des Kunden an. | *Wenn aktiv:* Zeigt die Adresszeile an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (optional) | Bietet zusätzliche Adressdetails. |
| **Postleitzahl** | Zeigt die Postleitzahl der Standardadresse des Kunden an. | *Wenn aktiv:* Zeigt die Postleitzahl an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (optional) | Nützlich für geografische Segmentierung oder Lieferplanung. |
| **Stadt** | Zeigt die Stadt der Standardadresse des Kunden an. | *Wenn aktiv:* Zeigt die Stadt an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (optional) | Nützlich für geografische Segmentierung oder lokales Marketing. |
| **Bundesland** | Zeigt das Bundesland/die Provinz der Standardadresse des Kunden an. | *Wenn aktiv:* Zeigt das Bundesland/die Provinz an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (optional) | Wichtig für regionale Zielgruppenansprache und Versand. |
| **Land** | Zeigt das Land der Standardadresse des Kunden an. | *Wenn aktiv:* Zeigt das Land an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (optional) | Wesentlich für internationale Shops und Versandlogistik. |
| **Newsletter** | Zeigt an, ob der Kunde Ihren Newsletter abonniert hat. | *Wenn aktiv:* Zeigt einen "Ja" oder "Nein" Indikator an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv | Hilft bei der Identifizierung von Marketingmöglichkeiten und der Verwaltung von E-Mail-Listen. |
| **Opt-in** | Zeigt an, ob der Kunde Partnerangeboten zugestimmt hat. | *Wenn aktiv:* Zeigt einen "Ja" oder "Nein" Indikator an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (optional) | Nützlich für die Verwaltung von Partner-Marketingmaßnahmen. |
| **Aktiv** | Zeigt an, ob das Kundenkonto derzeit aktiv ist. | *Wenn aktiv:* Zeigt einen "Ja" oder "Nein" Indikator an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv | Hilft bei der Identifizierung deaktivierter Konten. |
| **Standardgruppe** | Zeigt die primäre Kundengruppe des Kunden an. | *Wenn aktiv:* Zeigt den Namen der Standardgruppe an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv | Entscheidend für B2B-Shops oder Shops mit gestaffelten Preisen/Zugängen. |
| **Shop-Name** | Zeigt den Shop-Namen an, wenn der Multi-Store-Modus verwendet wird. | *Wenn aktiv:* Zeigt den Shop-Namen an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (wenn Multi-Store) | Wesentlich für Multi-Store-Umgebungen, um Kunden nach Shop zu unterscheiden. |
| **Offener Betrag** | Zeigt einen eventuellen offenen Saldo an, den der Kunde schuldet (falls zutreffend, z.B. für B2B-Kredit). | *Wenn aktiv:* Zeigt den offenen Betrag an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (falls zutreffend) | Wichtig für das B2B-Kreditmanagement. |
| **Nachbestellung erlaubt** | Zeigt an, ob der Kunde Nachbestellungen aufgeben darf. | *Wenn aktiv:* Zeigt "Ja" oder "Nein" an. *Wenn inaktiv:* Blendet diese Spalte aus. | Aktiv (falls zutreffend) | Relevant für die Bestandsverwaltung und spezifische Kundenvereinbarungen. |

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfigurationsseite | Drag & Drop Spaltenreihenfolge | Benutzerdefiniert | Steuert die visuelle Reihenfolge der Spalten in der Kundenliste des Back Office. |
| Modulkonfigurationsseite | Liste der aktiven Spalten | Benutzerdefiniert | Bestimmt, welche Spalten in der Kundenliste des Back Office sichtbar sind. |
| Modulkonfigurationsseite | Liste der verfügbaren Spalten | Benutzerdefiniert | Listet alle möglichen Spalten auf, die der Kundenliste hinzugefügt werden können. |
| Modulkonfigurationsseite | Speichern-Schaltfläche | Nach Änderungen klicken | Wendet alle Änderungen an der Spaltensichtbarkeit und -reihenfolge auf das Kundenraster an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe die Spalten konfiguriert, sehe aber keine Änderungen in meiner Kundenliste.**
A:
1.  **Haben Sie auf "Speichern" geklickt?** Nachdem Sie Änderungen auf der Modulkonfigurationsseite vorgenommen haben, müssen Sie auf die Schaltfläche "Speichern" klicken.
2.  **PrestaShop-Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf "Cache leeren" (oder "Smarty-Cache leeren" in älteren Versionen).
3.  **Browser-Cache überprüfen:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder das Back Office in einem Inkognito-/privaten Browserfenster zu öffnen.

**F: Einige Spalten, die ich erwarte (wie "Firmenname" oder "Offener Betrag"), sind in der Liste nicht verfügbar.**
A:
1.  **Modulkompatibilität:** Stellen Sie sicher, dass Sie die richtige Version des Moduls für Ihre spezifische PrestaShop-Version heruntergeladen und installiert haben.
2.  **PrestaShop-Funktionen:** Einige Spalten (z.B. "Offener Betrag") sind nur relevant, wenn Sie bestimmte PrestaShop-Funktionen (wie den B2B-Modus) aktiviert haben oder andere Module installiert sind, die diese Daten bereitstellen. Wenn die Daten in Ihrem Shop nicht existieren, kann das Modul sie möglicherweise nicht anzeigen.

**F: Die Drag-and-Drop-Funktionalität funktioniert auf der Konfigurationsseite nicht.**
A:
1.  **Browser-Kompatibilität:** Stellen Sie sicher, dass Sie einen modernen Webbrowser (Chrome, Firefox, Edge, Safari) verwenden und dass JavaScript aktiviert ist.
2.  **Konfliktierende Module:** Selten kann ein anderes Modul oder eine benutzerdefinierte Theme-Modifikation JavaScript stören. Versuchen Sie, andere Module vorübergehend zu deaktivieren, um zu sehen, ob das Problem behoben wird. Wenn ja, wenden Sie sich an den MyPresta.eu-Support.

**F: Kann ich die neuen Spaltennamen in andere Sprachen übersetzen?**
A: Ja, das PrestaShop-Übersetzungssystem sollte es Ihnen ermöglichen, die Zeichenketten des Moduls zu übersetzen.
1.  Gehen Sie zu **International > Übersetzungen**.
2.  Wählen Sie "Übersetzungen installierter Module".
3.  Wählen Sie Ihr Theme, Ihre Sprache und dann "Customer Grid Pro".
4.  Dort sollten Sie die Zeichenketten für die Spaltennamen zur Übersetzung finden.

**F: Wird dieses Modul mein Back Office verlangsamen?**
A: Das Modul ist optimiert, um sich in das Kern-Kundenraster von PrestaShop zu integrieren. Während das Hinzufügen vieler komplexer Spalten (insbesondere solcher, die Berechnungen wie "Gesamtausgaben" erfordern) die Ladezeit im Vergleich zu einer minimalistischen Liste leicht erhöhen kann, ist der Einfluss auf einem gut konfigurierten Server im Allgemeinen vernachlässigbar. Die Vorteile in Bezug auf die Effizienz überwiegen in der Regel alle geringfügigen Leistungsunterschiede bei weitem.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul `Customer Grid Pro` erweitert hauptsächlich die Funktionalität der PrestaShop Back Office Kundenliste. Dies wird durch das Einhaken in die Hooks `actionCustomerGridDefinitionModifier` und `actionCustomerGridDataModifier` erreicht, die Teil des neuen Grid-Systems von PrestaShop sind, das in 1.7.x eingeführt wurde. Dies ermöglicht dem Modul, Spalten und die zugehörigen Daten dynamisch hinzuzufügen, zu entfernen und neu anzuordnen, ohne Kerndateien direkt zu ändern. Die Konfiguration wird über eine Standard-`getContent()`-Methode in der Hauptmoduldatei verwaltet, die ein benutzerdefiniertes JavaScript und CSS für die Drag-and-Drop-Oberfläche verwendet.

### 4.2 Controller (`controllers/`)
Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Entitäten in einem `classes/`-Verzeichnis. Die gesamte Logik ist in der Hauptmoduldatei `index.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`mycustomergridpro/views/js/customer_grid_admin.js`**
    *   **Geltungsbereich:** Back-Office (insbesondere die Modulkonfigurationsseite).
    *   **Zweck:** Dieses Skript stellt die Drag-and-Drop-Funktionalität für die Spaltenauswahloberfläche auf der Konfigurationsseite des Moduls bereit. Es verwendet das `sortable`-Widget von jQuery UI, um das Neuanordnen und Verschieben von Elementen zwischen den Listen "Verfügbare Spalten" und "Aktive Spalten" zu ermöglichen.
    *   **Hauptfunktionalität:**
        *   Initialisiert zwei sortierbare Listen: `#available_columns` und `#active_columns`.
        *   Konfiguriert `connectWith`, um das Verschieben von Elementen zwischen diesen beiden Listen zu ermöglichen.
        *   Behandelt das `update`-Ereignis für die sortierbaren Listen, um möglicherweise das Speichern auszulösen oder versteckte Eingabefelder zu aktualisieren (obwohl das eigentliche Speichern durch die Formularübermittlung erfolgt).
        *   Stellt sicher, dass die Reihenfolge der Elemente in der Liste `#active_columns` korrekt mit dem Formular übermittelt wird.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`mycustomergridpro/views/css/customer_grid_admin.css`**
    *   **Geltungsbereich:** Back-Office (insbesondere die Modulkonfigurationsseite).
    *   **Zweck:** Bietet Styling für die Drag-and-Drop-Spaltenauswahloberfläche.
    *   **Haupt-Styling:**
        *   Stile für die Spaltenlisten-Container (`#available_columns`, `#active_columns`).
        *   Stile für einzelne Spaltenelemente (`.column-item`).
        *   Visuelle Hinweise für Drag-and-Drop-Operationen (z.B. `ui-sortable-helper`, `ui-sortable-placeholder`).
        *   Stellt sicher, dass die beiden Spaltenlisten nebeneinander oder in einem übersichtlichen Layout für die Benutzerfreundlichkeit angezeigt werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
Dieses Modul verwendet keine separaten `.tpl`-Dateien für seine Konfiguration oder Front-Office-Anzeige. Der gesamte HTML-Code des Konfigurationsformulars wird direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei `index.php` generiert.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    *   Es speichert seine Konfiguration (die Liste der aktiven Spalten und deren Reihenfolge) in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `MYCUSTOMERGRIDPRO_ACTIVE_COLUMNS`. Diese Konfiguration wird als serialisiertes Array oder JSON-String gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `actionCustomerGridDefinitionModifier` | Wird ausgeführt, wenn die Definition des Kundenrasters im Back Office erstellt wird. | Ermöglicht dem Modul, neue Spalten (z.B. Telefon, Gesamtbestellungen, Gesamtausgaben, Adressfelder) hinzuzufügen und bestehende aus der Rasterdefinition zu entfernen. Dieser Hook empfängt das `GridDefinition`-Objekt. |
| `actionCustomerGridDataModifier` | Wird ausgeführt, nachdem die Daten des Kundenrasters abgerufen wurden, aber bevor sie gerendert werden. | Ermöglicht dem Modul, die Daten für die über `actionCustomerGridDefinitionModifier` hinzugefügten benutzerdefinierten Spalten zu füllen. Dieser Hook empfängt das `QueryResult`-Objekt, was die Änderung der Datenzeilen ermöglicht. |
| `displayBackOfficeHeader` | Wird im `<head>`-Abschnitt der Back Office-Seiten ausgeführt. | Wird verwendet, um die benutzerdefinierten CSS (`customer_grid_admin.css`) und JavaScript (`customer_grid_admin.js`) Dateien des Moduls auf der Konfigurationsseite des Moduls einzubinden, um die Drag-and-Drop-Oberfläche zu ermöglichen. |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul "Customer Grid Pro - Spalten & Layout der Kundenliste" besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
