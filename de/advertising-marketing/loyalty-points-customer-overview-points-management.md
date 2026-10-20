---
title: "Loyalty points – Kundenübersicht & Punkteverwaltung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Loyalty points – Kundenübersicht & Punkteverwaltung“ von MyPresta.eu."
sidebar:
  label: "Loyalty points – Kundenübersicht & Punkteverwaltung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Loyalty points – Customer overview & points management auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-customer-overview-points-management.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/loyalty-points-customer-overview-points-management/)
>
> ---


# Loyalty points – Kundenübersicht & Punkteverwaltung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für PrestaShop selbst erforderlich und typischerweise in allen kompatiblen Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite für das Modul „Loyalty points – Kundenübersicht & Punkteverwaltung“. Dieser Bildschirm bietet allgemeine Einstellungen für das Verhalten des Moduls.

#### Manuelle E-Mail-Benachrichtigung aktivieren

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob eine E-Mail-Benachrichtigung an den Kunden gesendet wird, wenn Sie seine Treuepunkte manuell anpassen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Wenn Sie manuell Punkte für einen Kunden hinzufügen oder entfernen, erhält dieser eine E-Mail, die ihn über die Änderung und seinen neuen Saldo informiert. Dies hilft, Kunden auf dem Laufenden zu halten und Transparenz zu schaffen.
  - *Wenn deaktiviert:* Manuelle Punkteanpassungen erfolgen stillschweigend, ohne E-Mail-Benachrichtigung an den Kunden. Dies könnte für kleinere interne Korrekturen oder wenn Sie die Kundenkommunikation über andere Kanäle verwalten, bevorzugt werden.
- **Empfohlener Wert:** JA
- **Händlerszenario / Beispiel:** Sie haben gerade 50 Bonuspunkte zum Konto eines Kunden als Geburtstagsgeschenk hinzugefügt. Wenn diese Einstellung aktiviert ist, erhält der Kunde sofort eine E-Mail mit dem Text: „Herzlichen Glückwunsch zum Geburtstag! Wir haben Ihrem Konto 50 Treuepunkte hinzugefügt. Ihr neuer Saldo beträgt X Punkte.“ Dies verbessert das Kundenerlebnis und macht die Belohnung greifbar.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### Kunden-Treuepunkte-Verwaltung (Back Office > Katalog > Treuepunkte)

Dies ist der zentrale Verwaltungsbildschirm für das Modul, der über einen neuen Menüpunkt in Ihrem PrestaShop-Back-Office zugänglich ist.

- **Bildschirmname & Menüpfad:** **Katalog > Treuepunkte** (oder ähnlich, abhängig von Ihrer PrestaShop-Version und Menüanpassung).
- **Verfügbare Aktionen & Einstellungen:**
  - **Kundenliste:** Sie sehen eine umfassende Liste all Ihrer Kunden zusammen mit ihren aktuellen Treuepunktsalden.
  - **Suchen & Filtern:** Finden Sie bestimmte Kunden einfach nach Name, E-Mail oder ID.
  - **Historie anzeigen:** Für jeden Kunden können Sie klicken, um ein detailliertes Protokoll aller Treuepunkttransaktionen (verdient, ausgegeben, abgelaufen und manuell angepasst) anzuzeigen.
  - **Punkte hinzufügen/entfernen:**
    - Klicken Sie auf eine Kundenzeile oder ein „Bearbeiten“-Symbol, um auf die individuelle Punkteverwaltung zuzugreifen.
    - Sie finden Felder, um eine bestimmte Anzahl von Treuepunkten manuell hinzuzufügen oder abzuziehen.
    - Ein Feld „Grund“ ermöglicht es Ihnen, den Grund für die Anpassung zu notieren (z. B. „Geburtstagsbonus“, „Entschädigung für verspätete Bestellung“, „Punktekorrektur“). Dieser Grund ist entscheidend für Ihre internen Aufzeichnungen und für den Kundenservice.
    - Nach dem Speichern wird der Saldo des Kunden aktualisiert, und wenn die Einstellung „Manuelle E-Mail-Benachrichtigung aktivieren“ aktiv ist, wird eine E-Mail gesendet.
  - **Paginierung:** Die Standard-PrestaShop-Paginierung (`PS_LIST_LIMIT`) wird angewendet, sodass Sie steuern können, wie viele Kunden pro Seite angezeigt werden.
- **Auswirkung von Änderungen:**
  - **Punkte hinzufügen:** Erhöht den Treuepunktsaldo des Kunden. Dies kann verwendet werden, um Kunden zu belohnen, Entschädigungen anzubieten oder spezielle Aktionen durchzuführen.
  - **Punkte entfernen:** Verringert den Treuepunktsaldo des Kunden. Dies kann notwendig sein, um Fehler zu korrigieren, Punkte von zurückgegebenen Bestellungen zu widerrufen oder betrügerische Aktivitäten zu verwalten.
  - **Historie anzeigen:** Bietet eine transparente Prüfspur aller Punktbewegungen, die für den Kundensupport und die interne Berichterstattung von unschätzbarem Wert ist.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Regelmäßige Überprüfung der Kundenpunktsalden:** Insbesondere nach Aktionen oder wenn Kunden Unstimmigkeiten melden.
  2. **Sorgfältige Verwendung des Feldes „Grund“:** Geben Sie immer einen klaren, prägnanten Grund für jede manuelle Anpassung an. Dies spart Ihnen später Zeit und Verwirrung beim Überprüfen der Historie oder Erklären von Änderungen an Kunden.
  3. **E-Mail-Benachrichtigungen nutzen:** Bei positiven Anpassungen (Boni, Belohnungen) kann die Aktivierung von E-Mail-Benachrichtigungen die Kundenzufriedenheit und das Bewusstsein für ihre Treuevorteile erheblich steigern. Bei Korrekturen überlegen Sie, ob eine E-Mail notwendig ist oder ob interne Notizen ausreichen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Manuelle E-Mail-Benachrichtigung aktivieren | JA | Steuert, ob Kunden eine E-Mail erhalten, wenn ihre Treuepunkte manuell angepasst werden. |
| Katalog > Treuepunkte | Kundenliste & Suche | N/A | Zeigt alle Kunden und ihre aktuellen Treuepunktsalden an. |
| Katalog > Treuepunkte | Punkte hinzufügen/entfernen | N/A | Ermöglicht die manuelle Anpassung der Treuepunkte eines Kunden. |
| Katalog > Treuepunkte | Grund für Anpassung | N/A (Erforderliche Eingabe) | Bietet eine interne Notiz, warum Punkte hinzugefügt oder entfernt wurden. |
| Katalog > Treuepunkte | Historie anzeigen | N/A | Zeigt ein detailliertes Protokoll aller Treuepunkttransaktionen für einen bestimmten Kunden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe Punkte hinzugefügt, aber der Kunde sagt, er habe keine E-Mail erhalten.**
A: Überprüfen Sie zunächst, ob „Manuelle E-Mail-Benachrichtigung aktivieren“ in der Hauptkonfiguration des Moduls auf JA gesetzt ist. Wenn ja, überprüfen Sie die E-Mail-Protokolle Ihres Shops (falls verfügbar) oder die Mail-Protokolle Ihres Servers, um zu sehen, ob die E-Mail gesendet wurde. Weisen Sie den Kunden auch an, seinen Spam-/Junk-Ordner zu überprüfen. Stellen Sie sicher, dass Ihre PrestaShop-E-Mail-Einstellungen korrekt konfiguriert sind und Ihr Mailserver funktioniert.

**F2: Ich kann den Menüpunkt „Treuepunkte“ in meinem Back Office nicht finden.**
A: Nach der Installation sollte das Modul einen neuen Menüpunkt erstellen, typischerweise unter „Katalog“ oder „Kunden“. Wenn er fehlt, versuchen Sie, Ihren PrestaShop-Cache zu leeren (Erweiterte Parameter > Leistung > Cache leeren). Wenn er immer noch nicht erscheint, stellen Sie sicher, dass das Modul aktiviert und korrekt installiert ist. Überprüfen Sie auch Ihre Benutzerberechtigungen unter **Erweiterte Parameter > Team > Profile**, um sicherzustellen, dass Ihr Admin-Profil Zugriff auf den Controller des Moduls hat.

**F3: Der Treuepunktsaldo des Kunden wird im Front Office nicht aktualisiert, nachdem ich eine manuelle Änderung vorgenommen habe.**
A: Dies ist normalerweise ein Caching-Problem. Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren). Wenn Sie ein Drittanbieter-Caching-Modul oder CDN verwenden, leeren Sie auch dessen Cache. Das Modul aktualisiert die Datenbank direkt, daher sollte das Front Office Änderungen widerspiegeln, sobald der Cache aktualisiert wurde.

**F4: Kann ich mit diesem Modul Treuepunktdaten importieren/exportieren?**
A: Dieses Modul konzentriert sich auf die manuelle Verwaltung und Anzeige innerhalb des PrestaShop-Back-Office. Es enthält keine integrierten Import-/Exportfunktionen für Massendatenoperationen. Für solche Aufgaben müssen Sie möglicherweise benutzerdefinierte Datenbankabfragen oder andere spezialisierte Module in Betracht ziehen.

**F5: Was passiert, wenn ich dieses Modul deinstalliere?**
A: Bei der Deinstallation entfernt das Modul seine dedizierten Admin-Menüpunkte und möglicherweise seine Konfigurationseinstellungen. Es ist jedoch darauf ausgelegt, bestehende Treuepunkte zu verwalten, die typischerweise Teil des PrestaShop-Kern-Treuesystems oder eines anderen Treuemoduls sind. Die Punkte selbst sollten in der Datenbank verbleiben, aber Sie würden die bequeme Verwaltungsoberfläche verlieren, die dieses Modul bietet. Sichern Sie immer Ihre Datenbank, bevor Sie ein Modul deinstallieren.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Loyalty points – Kundenübersicht & Punkteverwaltung“ (`myprestaloyalty_customerpoints`) ist nach dem MVC-Muster von PrestaShop aufgebaut und erweitert hauptsächlich `Module` für seine Kernfunktionalität und `AdminController` für seine dedizierte Back-Office-Schnittstelle. Es interagiert mit dem Kern-Treuesystem von PrestaShop (oder einem kompatiblen Treuemodul), indem es eine erweiterte Verwaltungsebene bereitstellt. Das Modul führt ein benutzerdefiniertes `ObjectModel` ein, um manuelle Punkteanpassungen zu protokollieren und so eine Prüfspur zu gewährleisten.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul enthält keine dedizierten Front-Office-Controller. Alle kundenorientierten Interaktionen bezüglich Treuepunkten werden vom PrestaShop-Kern-Treuemodul oder dem Theme selbst gehandhabt.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMyprestaloyaltyCustomerPointsController.php`
    - **Klassenname & Elternklasse**: `AdminMyprestaloyaltyCustomerPointsController` erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dies ist der primäre Back-Office-Controller zur Verwaltung von Kunden-Treuepunkten. Er bietet die Listenansicht der Kunden mit ihren Treuesalden, ermöglicht das Suchen und Filtern und handhabt das Formular zum manuellen Hinzufügen/Entfernen von Punkten für einzelne Kunden. Er verwaltet die `customer_points`-Entität (obwohl er hauptsächlich mit bestehenden Treuepunktdaten interagiert, protokolliert er auch manuelle Änderungen über `MyprestaloyaltyCustomerPointsManualLog`).
    - **Tab-Name**: „Treuepunkte“ (oder ähnlich, dynamisch während der Installation festgelegt).
    - **Verwaltete Entität**: Er zeigt Kunden-Treuepunkte an und ermöglicht deren Änderung, wobei diese Änderungen protokolliert werden.
  - `controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Diese Datei dient typischerweise als Platzhalter oder einfache Weiterleitung in PrestaShop-Modulen. Sie kann eine einfache `die()`-Anweisung oder eine Weiterleitung enthalten, um direkten Zugriff zu verhindern und sicherzustellen, dass die Controller-Logik über den Dispatching-Mechanismus von PrestaShop ausgeführt wird. Sie verwaltet keine spezifische Entität und bietet keine eigenständige Ansicht.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/MyprestaloyaltyCustomerPointsManualLog.php`
  - **Klassenname**: `MyprestaloyaltyCustomerPointsManualLog` erweitert `ObjectModel`.
  - **Datenbanktabelle**: `_myprestaloyalty_customer_points_manual_log` (oder ähnlich, mit Präfix `_DB_PREFIX_`).
  - **`$definition`-Felder**:
    - `id_myprestaloyalty_customer_points_manual_log`: Primärschlüssel.
    - `id_customer`: Die ID des Kunden, dessen Punkte angepasst wurden.
    - `id_employee`: Die ID des Mitarbeiters, der die Anpassung vorgenommen hat.
    - `points_change`: Die Anzahl der hinzugefügten oder entfernten Punkte (kann positiv oder negativ sein).
    - `reason`: Ein Textfeld, das den Grund für die Anpassung erklärt.
    - `date_add`: Zeitstempel, wann die Anpassung vorgenommen wurde.
  - **Wichtige öffentliche Methoden und Geschäftslogik**: Diese Klasse ist für die Persistierung der Details jeder manuellen Treuepunkteanpassung verantwortlich, die über die Back-Office-Schnittstelle vorgenommen wurde. Sie bietet eine historische Aufzeichnung, die für Audits und den Kundensupport entscheidend ist.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Alle Interaktionen auf dem Back-Office-Verwaltungsbildschirm werden durch die Standard-jQuery- und Formularübermittlungsmechanismen von PrestaShop gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien. Es verlässt sich auf die Standard-Back-Office-Formatierung von PrestaShop für seine Konfigurationsformulare und Listenansichten, um ein konsistentes Erscheinungsbild zu gewährleisten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Das Konfigurationsformular und die Admin-Listen-/Bearbeitungsansichten werden mit den Standard-`getContent()`- und `ModuleAdminController`-Templates von PrestaShop gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_myprestaloyalty_customer_points_manual_log`:
    - `id_myprestaloyalty_customer_points_manual_log` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `points_change` INT(11) NOT NULL
    - `reason` TEXT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_customer_points_manual_log`)
    - KEY `id_customer` (`id_customer`)
    - KEY `id_employee` (`id_employee`)
  - **Konfigurationsdatensätze (in `ps_configuration`)**:
    - `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Speichert den booleschen Wert zum Aktivieren/Deaktivieren von E-Mail-Benachrichtigungen für manuelle Punkteanpassungen.
- **Registrierte Hooks-Tabelle**:
  Dieses Modul bietet hauptsächlich Back-Office-Funktionalität und registriert in seiner Kern-`install()`-Methode keine Front-Office-Anzeige-Hooks (`displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductExtraContent` usw.) oder Aktions-Hooks (`actionValidateOrder`, `actionProductUpdate` usw.). Die Integration erfolgt über den `AdminController` und die direkte Datenbankinteraktion zur Protokollierung.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Loyalty points – Kundenübersicht & Punkteverwaltung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
