---
title: "Manuelle Treuepunkte & Historie – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Manuelle Treuepunkte & Historie“ von MyPresta.eu."
sidebar:
  label: "Manuelle Treuepunkte & Historie – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Manual Loyalty Points & History auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/manual-loyalty-points-history.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/manual-loyalty-points-history/)
>
> ---


# Manuelle Treuepunkte & Historie

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Dieses Modul erfordert außerdem, dass das Haupt-PrestaShop-Treuesystem (z.B. `myprestaloyalty` oder das Standard-PrestaShop-Treuemodul) installiert und aktiv ist, da es dessen Funktionalität erweitert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Backoffice > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie globale Präferenzen einstellen können.

- **E-Mail-Benachrichtigungen für manuelle Punktänderungen aktivieren:**
  - **Was diese Einstellung bewirkt:** Steuert, ob Kunden eine E-Mail-Benachrichtigung erhalten, wenn ihre Treuepunkte manuell von einem Administrator angepasst werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Nachdem Sie manuell Punkte für einen Kunden hinzugefügt oder abgezogen haben, wird eine E-Mail an dessen registrierte E-Mail-Adresse gesendet, die ihn über die Änderung und seinen neuen Saldo informiert.
    - *Wenn deaktiviert (NEIN):* Es werden keine E-Mail-Benachrichtigungen an Kunden für manuelle Punktanpassungen gesendet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies, um Kunden vollständig informiert und in ihr Treueprogramm eingebunden zu halten. Wenn ein Kunde Punkte als Entschädigung erhält, bestätigt eine E-Mail-Benachrichtigung die Aktion und stärkt Ihren Kundenservice. Wenn deaktiviert, bemerken Kunden möglicherweise nicht sofort, dass sich ihr Guthaben geändert hat.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Manuelle Treuepunkteverwaltung (Backoffice > Module > Manuelle Treuepunkte)

Dies ist der Kernbildschirm, auf dem Sie alle manuellen Treuepunktanpassungen verwalten und protokollieren. Sie finden diesen Bildschirm, indem Sie im PrestaShop-Backoffice-Menü zu **Module > Manuelle Treuepunkte** navigieren.

Dieser Bildschirm zeigt eine Liste aller historischen manuellen Treuepunktanpassungen. Sie können von hier aus auch neue Anpassungen hinzufügen.

**Verfügbare Aktionen & Einstellungen:**

- **Schaltfläche „Neue Treuepunktanpassung hinzufügen“:**

  - **Was diese Schaltfläche bewirkt:** Durch Klicken auf diese Schaltfläche gelangen Sie zu einem Formular, in dem Sie manuell Treuepunkte für einen bestimmten Kunden hinzufügen oder abziehen können.
  - **Auswirkung des Klickens auf diese Schaltfläche:** Öffnet ein neues Formular zum Erstellen eines neuen Treuepunkteintrags.
- **Formular zur Treuepunktanpassung (Zugriff über „Neue Treuepunktanpassung hinzufügen“):**

  - **Kunden-Suchfeld:**

    - **Was dieses Feld bewirkt:** Ermöglicht Ihnen die Suche und Auswahl des Kunden, dessen Treuepunkte Sie anpassen möchten. Beginnen Sie mit der Eingabe des Namens oder der E-Mail-Adresse des Kunden, und eine Liste der übereinstimmenden Kunden wird angezeigt.
    - **Auswirkung der Änderung dieser Einstellung:** Sobald ein Kunde ausgewählt ist, wird die Anpassung auf dessen Konto angewendet.
    - **Empfohlener Wert:** Wählen Sie den korrekten Kunden aus.
    - **Händlerszenario / Beispiel:** Sie müssen Punkte für „Max Mustermann“ hinzufügen. Geben Sie „Max“ ein und wählen Sie ihn aus der Dropdown-Liste aus.
  - **Feld „Punkte hinzufügen/abziehen“:**

    - **Was dieses Feld bewirkt:** Hier geben Sie die Anzahl der anzupassenden Treuepunkte ein.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Positive Zahl (z.B. 50):* Fügt 50 Punkte zum Treueguthaben des Kunden hinzu.
      - *Negative Zahl (z.B. -25):* Zieht 25 Punkte vom Treueguthaben des Kunden ab.
    - **Empfohlener Wert:** Die genaue Anzahl der Punkte, die Sie hinzufügen oder abziehen möchten.
    - **Händlerszenario / Beispiel:** Ein Kunde hat einen beschädigten Artikel erhalten, daher fügen Sie „100“ Punkte als Entschädigung hinzu. Ein anderer Kunde hat einen Artikel zurückgegeben, für den er Punkte erhalten hat, daher ziehen Sie „-50“ Punkte ab.
  - **Feld „Gültigkeitsdauer (Tage)“:**

    - **Was dieses Feld bewirkt:** Definiert, wie viele Tage die manuell hinzugefügten Punkte ab dem Datum der Anpassung gültig sind. Nach diesem Zeitraum verfallen die Punkte.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Auf eine Zahl gesetzt (z.B. 365):* Punkte verfallen nach 365 Tagen.
      - *Auf 0 oder leer gesetzt:* Punkte haben kein Verfallsdatum (oder folgen dem Standardverfall Ihres Haupt-Treuemoduls, falls vorhanden).
    - **Empfohlener Wert:** Berücksichtigen Sie die Gesamtstrategie Ihres Treueprogramms. Wenn Sie eine schnelle Einlösung fördern möchten, legen Sie einen kürzeren Zeitraum fest. Für allgemeine Kulanz könnte ein längerer Zeitraum oder kein Verfall besser sein.
    - **Händlerszenario / Beispiel:** Sie geben 50 Punkte als Geburtstagsgeschenk, gültig für „30“ Tage, um einen schnellen Kauf zu fördern. Für eine größere Entschädigung könnten Sie es leer lassen, um keinen Verfall zu haben.
  - **Feld „Grund / Kommentar“:**

    - **Was dieses Feld bewirkt:** Ein Textfeld zur Aufzeichnung des Grundes für die Treuepunktanpassung. Dies dient der internen Nachverfolgung und Prüfung.
    - **Auswirkung der Änderung dieser Einstellung:** Dieser Text wird im Treueprotokoll gespeichert und bietet eine klare Historie, warum die Punkte angepasst wurden. Er ist für den Kunden nicht sichtbar.
    - **Empfohlener Wert:** Geben Sie immer einen klaren und prägnanten Grund an.
    - **Händlerszenario / Beispiel:** „Entschädigung für beschädigtes Produkt #12345“, „Geburtstagsgeschenk für VIP-Kunden“, „Punkte für die Teilnahme an Offline-Veranstaltungen“.
  - **Schaltfläche „Speichern“:**

    - **Was diese Schaltfläche bewirkt:** Wendet die Treuepunktanpassung auf das Kundenkonto an und speichert den Eintrag im Verlaufsprotokoll.
    - **Auswirkung des Klickens auf diese Schaltfläche:** Die Treuepunkte des Kunden werden aktualisiert, und ein neuer Eintrag erscheint in der Tabelle „Manuelle Treuepunkteverwaltung“. Wenn E-Mail-Benachrichtigungen aktiviert sind, erhält der Kunde eine E-Mail.
- **Tabelle „Treuepunkte-Historie“:**

  - **Was diese Tabelle bewirkt:** Zeigt eine chronologische Liste aller manuellen Treuepunktanpassungen an, die über dieses Modul vorgenommen wurden.
  - **Spalten:**
    - **ID:** Eindeutiger Bezeichner für den Protokolleintrag.
    - **Kunde:** Der Name des Kunden, dessen Punkte angepasst wurden.
    - **Punkte:** Die Anzahl der hinzugefügten oder abgezogenen Punkte.
    - **Gültigkeit (Tage):** Die für die Punkte festgelegte Verfallsperiode.
    - **Grund:** Der interne Kommentar für die Anpassung.
    - **Datum hinzugefügt:** Datum und Uhrzeit der Anpassung.
    - **Admin:** Der Name des Administrators, der die Anpassung vorgenommen hat.
  - **Auswirkung von Änderungen:** Diese Tabelle bietet eine vollständige Prüfspur. Sie können Einträge sortieren und filtern, um vergangene Anpassungen zu überprüfen.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1. Wenn eine Situation eine manuelle Punktanpassung erfordert (z.B. Kundenbeschwerde, Sonderaktion), navigieren Sie zu **Module > Manuelle Treuepunkte**.
2. Klicken Sie auf „Neue Treuepunktanpassung hinzufügen“.
3. Suchen und wählen Sie den Kunden aus.
4. Geben Sie die Anzahl der Punkte ein (positiv zum Hinzufügen, negativ zum Abziehen).
5. Legen Sie bei Bedarf eine Gültigkeitsdauer fest.
6. Fügen Sie unbedingt einen klaren „Grund / Kommentar“ für zukünftige Referenz hinzu.
7. Klicken Sie auf „Speichern“.
8. Überprüfen Sie die Historientabelle, um den Eintrag zu bestätigen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | E-Mail-Benachrichtigungen aktivieren | JA | E-Mail an Kunden bei manuellen Punktänderungen senden. |
| Manuelle Treuepunkte | Kundensuche | N/A | Kunden für Punktanpassung auswählen. |
| Manuelle Treuepunkte | Punkte hinzufügen/abziehen | N/A | Positiven oder negativen Wert für Punkte eingeben. |
| Manuelle Treuepunkte | Gültigkeitsdauer (Tage) | Leer (Kein Verfall) | Verfall für manuell hinzugefügte Punkte festlegen. |
| Manuelle Treuepunkte | Grund / Kommentar | N/A | Interne Notiz für die Prüfspur. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe Punkte hinzugefügt, aber der Kunde sagt, er habe keine E-Mail erhalten.**
A: Überprüfen Sie zunächst, ob „E-Mail-Benachrichtigungen für manuelle Punktänderungen aktivieren“ in der Modulkonfiguration auf JA gesetzt ist. Wenn ja, überprüfen Sie die E-Mail-Protokolle Ihres Shops (falls verfügbar) oder die Mail-Protokolle Ihres Servers, um zu sehen, ob die E-Mail gesendet wurde. Raten Sie dem Kunden auch, seinen Spam- oder Junk-Ordner zu überprüfen. Stellen Sie sicher, dass Ihre PrestaShop-E-Mail-Einstellungen korrekt konfiguriert sind und E-Mails erfolgreich versendet werden.

**F: Der Treuepunktestand des Kunden wurde nicht aktualisiert, nachdem ich Punkte hinzugefügt hatte.**
A: Dieses Modul aktualisiert das Kern-PrestaShop-Treuesystem. Wenn der Saldo nicht angezeigt wird, leeren Sie zuerst Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren). Wenn das Problem weiterhin besteht, stellen Sie sicher, dass Ihr Haupt-Treuemodul (z.B. das Standard-PrestaShop-Treuemodul oder `myprestaloyalty`) korrekt installiert und aktiv ist, da dieses Modul darauf angewiesen ist.

**F: Kann ich eine Treuepunktanpassung bearbeiten, nachdem ich sie gespeichert habe?**
A: Nein, aus Gründen der Prüfung und Datenintegrität können einzelne Treuepunktanpassungen nach dem Speichern nicht bearbeitet werden. Wenn Sie einen Fehler gemacht haben, sollten Sie eine *neue* Anpassung hinzufügen, um ihn zu korrigieren (z.B. wenn Sie versehentlich 100 Punkte statt 50 hinzugefügt haben, fügen Sie einen neuen Eintrag hinzu, der 50 Punkte abzieht) und die Korrektur im Feld „Grund / Kommentar“ deutlich vermerken.

**F: Was passiert, wenn ich mehr Punkte abziehe, als ein Kunde hat?**
A: Das System erlaubt in der Regel den Abzug, was zu einem negativen Treuepunktestand für den Kunden führt. Dies kann in bestimmten Szenarien nützlich sein, aber im Allgemeinen sollten Sie sicherstellen, dass Kunden genügend Punkte haben, bevor Sie abziehen.

**F: Woher weiß ich, wer eine bestimmte Punktanpassung vorgenommen hat?**
A: Die Spalte „Admin“ in der Historientabelle „Manuelle Treuepunkteverwaltung“ zeigt deutlich an, welches Administratorkonto jede Anpassung vorgenommen hat, und bietet so eine vollständige Prüfspur.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `Manuelle Treuepunkte & Historie` (myprestaloyalty_manual) ist als Standard-PrestaShop-Modul konzipiert, das die Kernfunktionalität des Treuesystems erweitert. Es arbeitet hauptsächlich im Backoffice und bietet eine administrative Schnittstelle für manuelle Punktanpassungen und deren Protokollierung. Es nutzt das MVC-Muster von PrestaShop für seinen Admin-Controller und verwendet ein `ObjectModel` zur persistenten Speicherung manueller Protokolleinträge. Das Modul integriert sich in das bestehende Treuesystem, indem es die Treuepunkte des Kunden direkt manipuliert.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul enthält keine dedizierten Front-Office-Controller. Die gesamte kundenorientierte Anzeige der Treuepunkte wird vom Haupt-Treuemodul übernommen.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMyprestaloyaltyManualController.php`

    - **Klassenname & Elternklasse**: `AdminMyprestaloyaltyManualController` erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dies ist der primäre administrative Controller zur Verwaltung manueller Treuepunktanpassungen. Er handhabt die Anzeige der Treueprotokollliste (unter Verwendung von `HelperList`) und das Formular zum Hinzufügen neuer Anpassungen (unter Verwendung von `HelperForm`). Er verarbeitet Formularübermittlungen, validiert Daten, erstellt `MyprestaloyaltyManualLog`-Objekte und aktualisiert die Treuepunkte des Kunden. Er löst auch E-Mail-Benachrichtigungen aus, falls aktiviert.
    - **Tab-Name**: „Manuelle Treuepunkte“ (unter dem Modul-Menü).
    - **Verwaltete Entität**: `MyprestaloyaltyManualLog` (das Protokoll der manuellen Anpassungen).
  - `controllers/admin/index.php`

    - **Verantwortlichkeit**: Dies ist eine leere Platzhalterdatei, die oft in PrestaShop-Modul `controllers/admin`-Verzeichnissen enthalten ist, um die Verzeichnisauflistung zu verhindern. Sie enthält keine funktionale Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/index.php`

  - **Verantwortlichkeit**: Leere Platzhalterdatei zur Verhinderung der Verzeichnisauflistung.
- `classes/MyprestaloyaltyManualLog.php`

  - **Mit welcher Datenbanktabelle interagiert es**: `ps_myprestaloyalty_manual_log`
  - **Erweitert `ObjectModel`**: Ja.
  - **`$definition`-Felder**:
    - `id_myprestaloyalty_manual_log`: Primärschlüssel.
    - `id_customer`: ID des betroffenen Kunden.
    - `points`: Anzahl der angepassten Punkte (kann positiv oder negativ sein).
    - `validity`: Gültigkeitsdauer in Tagen für die Punkte.
    - `reason`: Textlicher Grund für die Anpassung.
    - `id_employee`: ID des Administrators, der die Anpassung vorgenommen hat.
    - `date_add`: Zeitstempel, wann der Eintrag hinzugefügt wurde.
  - **Wichtige öffentliche Methoden und gekapselte Geschäftslogik**:
    - Standard `ObjectModel`-Methoden (`add`, `update`, `delete`).
    - Handhabt die Datenvalidierung für seine Felder.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Standard-PrestaShop-JS für die Formularbehandlung und AJAX (z.B. Kundensuche) wird verwendet.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Es basiert auf dem Standard-Backoffice-Styling von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Es basiert auf den Standard-`HelperList`- und `HelperForm`-Templates von PrestaShop für seine Backoffice-Oberfläche.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_myprestaloyalty_manual_log`:
    - `id_myprestaloyalty_manual_log` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `points` INT(10) NOT NULL
    - `validity` INT(10) UNSIGNED DEFAULT 0
    - `reason` TEXT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_manual_log`)
    - KEY `id_customer` (`id_customer`)
- **Konfigurationseinträge (in `ps_configuration`)**:

  - `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Speichert den booleschen Wert (0 oder 1) zum Aktivieren/Deaktivieren von E-Mail-Benachrichtigungen.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Rendert Inhalte im `<head>`-Bereich des Backoffice. | Wird verwendet, um modulspezifisches CSS/JS (obwohl dieses Modul keines hat) einzubinden oder Admin-Menüpunkte zu registrieren. |
  | `actionCustomerAccountAdd` | Nach der Erstellung eines neuen Kundenkontos. | Wird von diesem Modul nicht explizit verwendet, aber ein gängiger Treue-Hook. |
  | `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Wird von diesem Modul nicht explizit verwendet, aber ein gängiger Treue-Hook. |
  | `actionObjectCustomerUpdateAfter` | Nach der Aktualisierung eines Kundenobjekts. | Wird von diesem Modul nicht explizit verwendet. |
  | `actionObjectCustomerDeleteAfter` | Nach dem Löschen eines Kundenobjekts. | Wird von diesem Modul nicht explizit verwendet. |

  *Hinweis: Die primäre Funktionalität des Moduls (Hinzufügen/Abziehen von Punkten) wird direkt von seinem Admin-Controller ausgelöst, nicht über Front-Office-Hooks. Das Modul interagiert mit den Methoden des Kern-Treuesystems, um Punkte anzupassen.*

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Manuelle Treuepunkte & Historie“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität des Moduls zur Verfügung.
