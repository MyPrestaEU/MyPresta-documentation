---
title: "Treuepunkte – Dienstalter (Seniorität) Regeln - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Treuepunkte – Dienstalter (Seniorität) Regeln“ von MyPresta.eu."
sidebar:
  label: "Treuepunkte – Dienstalter (Seniorität) Regeln - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Loyalty points – Tenure (seniority) rules auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-tenure-seniority-rules.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/loyalty-points-tenure-seniority-rules/)
>
> ---


# Treuepunkte – Dienstalter (Seniorität) Regeln

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in den meisten Hosting-Umgebungen verfügbar. Dieses Modul hat keine zusätzlichen spezifischen Anforderungen über eine Standard-PrestaShop-Installation hinaus.

## 2. Vollständige Konfigurationsübersicht (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der sofort nach der Installation oder durch Klicken auf „Konfigurieren“ im Modul-Manager aufgerufen wird.

**Allgemeine Einstellungen**

-   **Modul aktivieren:**

    *   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der gesamten Funktionalität des Moduls.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das Modul beginnt mit der Verarbeitung von Treueregeln basierend auf dem Dienstalter des Kunden und vergibt Punkte wie konfiguriert.
        *   *Wenn deaktiviert:* Das Modul stellt seine Funktion ein. Es werden keine neuen Punkte basierend auf Dienstalterregeln vergeben, und bestehende Regeln werden ignoriert, bis sie wieder aktiviert werden.
    *   **Empfohlener Wert:** JA
    *   **Händlerszenario / Beispiel:** Sie haben Ihre Regeln eingerichtet und sind bereit, Ihr Treueprogramm zu starten. Aktivieren Sie dies, um Kunden zu belohnen. Wenn Sie das Programm vorübergehend für Wartungsarbeiten oder Überprüfungen pausieren müssen, können Sie es hier deaktivieren.
-   **Cron-Job-URL:**

    *   **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die Sie als „Cron-Job“ auf Ihrem Webserver einrichten müssen. Ein Cron-Job ist eine geplante Aufgabe, die Ihrem Server anweist, diese URL automatisch in regelmäßigen Abständen (z.B. einmal täglich) auszuführen. So überprüft das Modul das Dienstalter des Kunden und vergibt Punkte, ohne dass Sie es manuell auslösen müssen.
    *   **Auswirkung der Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert.
        *   *Wenn korrekt als Cron-Job konfiguriert:* Das Modul führt seine Prüfungen automatisch durch und vergibt Punkte gemäß Ihren Regeln.
        *   *Wenn NICHT als Cron-Job konfiguriert:* Die automatische Punktevergabe des Moduls findet nicht statt. Sie müssten diese URL manuell in Ihrem Browser aufrufen, um den Prozess auszulösen, was den Zweck der Automatisierung zunichtemacht.
    *   **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als täglichen Cron-Job auf Ihrem Server ein.
    *   **Händlerszenario / Beispiel:** Kopieren Sie diese URL nach der Installation des Moduls. Gehen Sie zu Ihrem Hosting-Kontrollpanel (z.B. cPanel, Plesk) und suchen Sie den Abschnitt „Cron-Jobs“ oder „Geplante Aufgaben“. Fügen Sie einen neuen Cron-Job hinzu, um diese URL einmal alle 24 Stunden auszuführen. Dies stellt sicher, dass Ihre Kunden ihre Senioritätspunkte automatisch und pünktlich erhalten.

### 2.2 Dedizierter Admin-Bildschirm: Treue-Dienstalter-Regeln (Back Office > MyPresta.eu > Treue-Dienstalter-Regeln)

Dieser Bildschirm ermöglicht es Ihnen, die spezifischen Regeln für die Vergabe von Treuepunkten basierend auf dem Dienstalter des Kunden zu definieren und zu verwalten.

-   **Bildschirmname & Menüpfad:** Sie finden diesen Bildschirm, indem Sie im PrestaShop Back Office-Menü zu **MyPresta.eu > Treue-Dienstalter-Regeln** navigieren.
-   **Verfügbare Aktionen & Einstellungen:**

    *   **Regellistentabelle:** Diese Tabelle zeigt alle Ihre aktiven und inaktiven Dienstalterregeln an. Für jede Regel sehen Sie:
        *   **ID:** Eine eindeutige Kennung für die Regel.
        *   **Dienstalter (Tage):** Die Mindestanzahl von Tagen, die ein Kunde registriert sein muss, um sich für diese Regel zu qualifizieren.
        *   **Zu vergebende Punkte:** Die Anzahl der Treuepunkte, die ein Kunde erhält.
        *   **Aktiv:** Ein Schalter zum Aktivieren oder Deaktivieren der Regel.
        *   **Aktionen:** Schaltflächen zum „Bearbeiten“ oder „Löschen“ einer Regel.
    *   **Schaltfläche „Neue Regel hinzufügen“:** Klicken Sie auf diese Schaltfläche, um eine neue Dienstalterregel zu erstellen.

    **Beim Hinzufügen/Bearbeiten einer Regel:**
    Sie erhalten ein Formular, um die Parameter der Regel zu definieren:

    *   **Dienstalter (Tage):**

        *   **Was diese Einstellung bewirkt:** Dies ist die Mindestanzahl von Tagen, die ein Kunde in Ihrem Shop registriert sein muss, um für diese spezifische Treuepunktvergabe berechtigt zu sein.
        *   **Auswirkung der Änderung dieser Einstellung:**
            *   *Einstellung auf 365:* Kunden, die mindestens ein Jahr registriert sind, qualifizieren sich.
            *   *Einstellung auf 730:* Kunden, die mindestens zwei Jahre registriert sind, qualifizieren sich.
        *   **Empfohlener Wert:** Wählen Sie Werte, die sinnvolle Meilensteine für Ihre Kunden darstellen (z.B. 365 Tage für 1 Jahr, 730 Tage für 2 Jahre, 1095 Tage für 3 Jahre).
        *   **Händlerszenario / Beispiel:** Sie möchten Kunden belohnen, die mindestens ein Jahr in Ihrem Shop sind. Sie würden dies auf `365` setzen.
    *   **Zu vergebende Punkte:**

        *   **Was diese Einstellung bewirkt:** Dies ist die genaue Anzahl der Treuepunkte, die einem Kunden gewährt werden, der die Anforderung „Dienstalter (Tage)“ für diese Regel erfüllt.
        *   **Auswirkung der Änderung dieser Einstellung:**
            *   *Einstellung auf 100:* Qualifizierte Kunden erhalten 100 Treuepunkte.
            *   *Einstellung auf 50:* Qualifizierte Kunden erhalten 50 Treuepunkte.
        *   **Empfohlener Wert:** Richten Sie dies am Wert Ihres bestehenden Treuepunkteprogramms aus. Ein guter Ausgangspunkt könnten Punkte sein, die einem kleinen Rabatt entsprechen (z.B. 5-10% eines durchschnittlichen Bestellwerts).
        *   **Händlerszenario / Beispiel:** Um sich für ein Jahr Treue zu bedanken, könnten Sie `250` Punkte vergeben, was einem Rabatt von 5 € auf den nächsten Einkauf entsprechen könnte.
    *   **Aktiv:**

        *   **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob diese spezifische Regel derzeit aktiv ist und vom Modul bei der Punktevergabe berücksichtigt wird.
        *   **Auswirkung der Änderung dieser Einstellung:**
            *   *Wenn aktiviert:* Die Regel wird vom Cron-Job verarbeitet, und Punkte werden an qualifizierte Kunden vergeben.
            *   *Wenn deaktiviert:* Die Regel wird ignoriert, und es werden keine Punkte basierend auf diesem spezifischen Dienstalters-Schwellenwert vergeben.
        *   **Empfohlener Wert:** JA (für Regeln, die Sie aktiv haben möchten).
        *   **Händlerszenario / Beispiel:** Sie haben eine Regel für 5 Jahre Dienstalter erstellt, möchten diese aber intern testen, bevor Sie sie live schalten. Sie können sie deaktiviert lassen, bis Sie bereit sind, sie zu aktivieren.
-   **Auswirkung von Änderungen:**

    *   Das Hinzufügen einer neuen Regel erstellt einen neuen Eintrag in der Datenbank, den der Cron-Job des Moduls überprüfen wird.
    *   Das Bearbeiten einer Regel ändert ihre Parameter (Dienstalter, Punkte, aktiver Status) und beeinflusst zukünftige Punktevergaben.
    *   Das Löschen einer Regel entfernt sie dauerhaft, und es werden keine weiteren Punkte basierend auf diesem spezifischen Dienstalter vergeben.
    *   Der Konfigurationsschlüssel `PS_LIST_LIMIT` steuert die Anzahl der pro Seite angezeigten Elemente in der Regellistentabelle.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

    1.  **Planen Sie Ihre Treuestufen:** Entscheiden Sie, welche Dienstalters-Meilensteine Sie belohnen möchten (z.B. 1 Jahr, 2 Jahre, 5 Jahre).
    2.  **Berechnen Sie Punktwerte:** Bestimmen Sie, wie viele Punkte Sie für jede Stufe vergeben möchten, unter Berücksichtigung des monetären Werts Ihrer Treuepunkte.
    3.  **Regeln erstellen:** Gehen Sie zu **MyPresta.eu > Treue-Dienstalter-Regeln** und klicken Sie für jede Stufe auf „Neue Regel hinzufügen“.
    4.  **Überwachen:** Überprüfen Sie regelmäßig die Treuepunktestände Ihrer Kunden und stellen Sie sicher, dass der Cron-Job korrekt ausgeführt wird.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------------- | :------------------- | :------------------- | :----------------- |
| Modulkonfiguration   | Modul aktivieren     | JA                   | Aktiviert/deaktiviert die gesamte Modulfunktionalität. |
| Modulkonfiguration   | Cron-Job-URL         | Kopieren & als täglichen Cron-Job einrichten | Ermöglicht die automatische Punktevergabe basierend auf Dienstalter. |
| Treue-Dienstalter-Regeln (Admin-Bildschirm) | Dienstalter (Tage)   | Sinnvolle Meilensteine (z.B. 365, 730) | Mindestanzahl von Tagen, die ein Kunde registriert sein muss, um Punkte zu erhalten. |
| Treue-Dienstalter-Regeln (Admin-Bildschirm) | Zu vergebende Punkte | An den Wert des Treueprogramms anpassen | Anzahl der Treuepunkte, die für diese Regel vergeben werden. |
| Treue-Dienstalter-Regeln (Admin-Bildschirm) | Aktiv                | JA                   | Aktiviert/deaktiviert eine spezifische Dienstalterregel. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden erhalten keine Treuepunkte, obwohl ich Regeln eingerichtet habe.**
A1:

-   **Modulaktivierung prüfen:** Stellen Sie sicher, dass die Einstellung „Modul aktivieren“ auf der Hauptkonfigurationsseite auf JA gesetzt ist.
-   **Cron-Job überprüfen:** Der häufigste Grund ist ein falsch eingerichteter oder nicht laufender Cron-Job. Überprüfen Sie die Cron-Job-URL auf der Konfigurationsseite des Moduls und stellen Sie sicher, dass sie auf Ihrem Hosting-Server korrekt für die tägliche Ausführung konfiguriert ist.
-   **Regelstatus:** Stellen Sie sicher, dass die einzelnen von Ihnen erstellten Treue-Dienstalter-Regeln als „Aktiv“ markiert sind.
-   **Kundenberechtigung:** Hat der Kunde tatsächlich die Anforderung „Dienstalter (Tage)“ für eine Ihrer aktiven Regeln erfüllt? Das Modul vergibt Punkte nur, wenn ein Kunde einen Schwellenwert überschreitet.
-   **Smarty-Cache:** Manchmal kann der PrestaShop-Cache Anzeigeprobleme verursachen. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).

**F2: Woher weiß ich, ob der Cron-Job korrekt ausgeführt wird?**
A2:

-   **Hosting-Protokolle prüfen:** Die meisten Hosting-Anbieter bieten in Ihrem Kontrollpanel (z.B. cPanel) eine Möglichkeit, die Ausführungsprotokolle von Cron-Jobs anzuzeigen. Suchen Sie nach Einträgen, die sich auf die vom Modul bereitgestellte Cron-Job-URL beziehen.
-   **Manueller Test:** Sie können die Cron-Job-URL manuell in Ihrem Webbrowser aufrufen. Dies löst den Punktevergabeprozess für diesen Moment aus. Wenn nach diesem manuellen Besuch Punkte an berechtigte Kunden vergeben werden, bestätigt dies, dass die Modullogik funktioniert und das Problem bei der automatischen Cron-Einrichtung liegt.

**F3: Kann ich Kunden, die einen Dienstalters-Meilenstein bereits vor der Installation des Moduls überschritten haben, rückwirkend Punkte vergeben?**
A3: Ja, wenn der Cron-Job zum ersten Mal ausgeführt wird, nachdem Sie Regeln eingerichtet haben, werden alle bestehenden Kunden anhand Ihrer aktiven Regeln bewertet. Wenn ein Kunde eine Dienstaltersanforderung erfüllt und für diese spezifische Regel zuvor noch keine Punkte erhalten hat, werden diese vergeben. Das bedeutet, dass ältere, treue Kunden ihre verdienten Punkte erhalten.

**F4: Mein benutzerdefiniertes Theme zeigt Treuepunkte nicht korrekt an, oder die Benachrichtigungen sehen seltsam aus.**
A4: Dieses Modul interagiert hauptsächlich mit dem Kern-Treuesystem von PrestaShop. Jegliche Anzeigeprobleme mit Treuepunkten oder Benachrichtigungen hängen normalerweise mit dem Styling Ihres Themes oder Überschreibungen für das native Treuemodul zusammen.

-   **Theme-Anpassung:** Wenn Sie ein benutzerdefiniertes Theme haben, verfügt es möglicherweise über eigene Vorlagen oder CSS zur Anzeige von Treueinformationen. Möglicherweise müssen Sie Ihren Theme-Entwickler oder einen Webmaster konsultieren, um sicherzustellen, dass es korrekt in die Treuefunktionen von PrestaShop integriert ist.
-   **Standard-Theme-Test:** Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (Classic), um zu sehen, ob das Problem weiterhin besteht. Wenn es im Standard-Theme korrekt funktioniert, liegt das Problem definitiv bei Ihrem benutzerdefinierten Theme.

**F5: Was passiert, wenn ich eine Regel ändere (z.B. Punkte erhöhe), nachdem Kunden bereits Punkte daraus erhalten haben?**
A5: Das Modul ist so konzipiert, dass es Punkte *einmal* für jede Regel vergibt, wenn ein Kunde den Dienstalters-Schwellenwert zum ersten Mal erreicht. Wenn Sie eine Regel ändern (z.B. Punkte für 365 Tage von 100 auf 150 erhöhen), erhalten Kunden, die bereits 100 Punkte für 365 Tage erhalten haben, *nicht* automatisch die zusätzlichen 50 Punkte. Die Regel wurde für sie bereits „erfüllt“. Wenn Sie ihnen die zusätzlichen Punkte geben möchten, müssten Sie ihren Treuepunktestand manuell anpassen oder eine neue, temporäre Regel erstellen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Treuepunkte – Dienstalter (Seniorität) Regeln“ (`myprestaloyalty_tenure`) erweitert die Funktionalität von PrestaShop durch die Einführung eines neuen Konzepts der Treuepunktvergabe basierend auf dem Registrierungsdienstalter des Kunden. Es folgt einer Standard-PrestaShop-Modularchitektur, die `ObjectModel` zur Verwaltung von Dienstalterregeln und einen dedizierten Front-Controller für die Cron-Job-Ausführung nutzt. Das Modul integriert sich in das PrestaShop-Kernmodul `LoyaltyModule`, um Punkte zu vergeben und so die Kompatibilität mit dem nativen Treuesystem sicherzustellen.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:

    *   `controllers/front/cron.php`
        *   **Klassenname:** `MyprestaloyaltyTenureCronModuleFrontController` (erweitert `ModuleFrontController`)
        *   **Verantwortlichkeit:** Dieser Controller ist für die Ausführung über einen Cron-Job konzipiert. Beim Zugriff durchläuft er alle aktiven Dienstalterregeln und alle registrierten Kunden. Für jeden Kunden berechnet er das Registrierungsalter und prüft, ob dieser sich für eine aktive Regel qualifiziert, für die er noch keine Punkte erhalten hat. Wenn ein Kunde sich qualifiziert, vergibt er die angegebenen Treuepunkte unter Verwendung der Kernfunktionalität des `LoyaltyModule`. Er gibt typischerweise eine einfache Erfolgsmeldung oder Protokollausgabe zurück.
    *   `controllers/front/index.php`
        *   **Klassenname:** `MyprestaloyaltyTenureIndexModuleFrontController` (erweitert `ModuleFrontController`)
        *   **Verantwortlichkeit:** Dies ist ein Platzhalter oder Standard-Front-Controller. In vielen Modulen, wenn keine spezifische Aktion definiert ist, könnte `index.php` eine Standardansicht behandeln oder umleiten. Für dieses Modul erfolgt die primäre Front-Office-Interaktion über den `cron.php`-Controller.
-   **Back-Office-Admin-Controller**:

    *   `controllers/admin/AdminMyprestaloyaltyTenureController.php`
        *   **Klassenname:** `AdminMyprestaloyaltyTenureController` (erweitert `ModuleAdminController`)
        *   **Tab-Name:** „Treue-Dienstalter-Regeln“ (unter dem MyPresta.eu-Menü)
        *   **Verwaltete Entität:** `MyprestaloyaltyTenureRule` (entspricht der Datenbanktabelle `_myprestaloyalty_tenure_rule`)
        *   **Verantwortlichkeit:** Dieser Controller stellt die CRUD-Schnittstelle (Create, Read, Update, Delete) zur Verwaltung von Treue-Dienstalter-Regeln im PrestaShop Back Office bereit. Er verwendet `HelperList` zur Anzeige der Regelliste und `HelperForm` zum Hinzufügen/Bearbeiten einzelner Regeln. Er verarbeitet Formularübermittlungen, Validierung und die Interaktion mit dem `MyprestaloyaltyTenureRule` `ObjectModel`.
    *   `controllers/admin/index.php`
        *   **Klassenname:** (Keine spezifische Klasse, typischerweise für Sicherheit verwendet)
        *   **Verantwortlichkeit:** Diese Datei enthält normalerweise ein einfaches `header('Location: ../../index.php?controller=AdminHome'); exit;` oder Ähnliches, um direkte Verzeichnisauflistungen zu verhindern und sicherzustellen, dass Admin-Controller über den PrestaShop-Dispatcher aufgerufen werden.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `classes/index.php`

    *   **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsdatei, die typischerweise `header('Location: ../../index.php?controller=AdminHome'); exit;` enthält, um den direkten Zugriff auf das Verzeichnis `classes` zu verhindern.
-   `classes/MyprestaloyaltyTenureRule.php`

    *   **Klassenname:** `MyprestaloyaltyTenureRule` (erweitert `ObjectModel`)
    *   **Datenbanktabelle:** `_myprestaloyalty_tenure_rule`
    *   **`$definition` Felder:**
        *   `id_myprestaloyalty_tenure_rule`: Primärschlüssel.
        *   `tenure_days`: Integer, die Mindestanzahl von Tagen, die ein Kunde registriert sein muss.
        *   `points_to_award`: Integer, die Anzahl der zu vergebenden Treuepunkte.
        *   `active`: Boolean, ob die Regel aktiv ist (0 oder 1).
    *   **Wichtige öffentliche Methoden:**
        *   `__construct()`: Standard `ObjectModel`-Konstruktor.
        *   `add()`: Überschreibt `ObjectModel::add()` für benutzerdefinierte Logik, falls erforderlich (z.B. Datumsbehandlung, Validierung).
        *   `update()`: Überschreibt `ObjectModel::update()`.
        *   `delete()`: Überschreibt `ObjectModel::delete()`.
        *   `getAllActiveRules()`: Statische Methode zum Abrufen aller aktiven Regeln aus der Datenbank.
        *   `hasCustomerReceivedPointsForRule($id_customer, $id_rule)`: Statische Methode zur Überprüfung, ob ein bestimmter Kunde bereits Punkte für eine bestimmte Regel erhalten hat. Dies ist entscheidend, um doppelte Vergaben zu verhindern.
        *   `markCustomerAsAwarded($id_customer, $id_rule)`: Statische Methode zur Aufzeichnung, dass ein Kunde Punkte für eine Regel erhalten hat.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist darauf hin, dass keine benutzerdefinierten JavaScript-Dateien in `views/js/` vorhanden sind. Alle Interaktionen werden serverseitig oder über Standard-PrestaShop-Formular-/Listen-Helfer abgewickelt.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist darauf hin, dass keine benutzerdefinierten CSS-Dateien in `views/css/` vorhanden sind. Die Back Office-Oberfläche basiert auf den Standard-Admin-Theme-Stilen von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Moduldossier weist darauf hin, dass keine benutzerdefinierten Smarty-Template-Dateien in `views/templates/` vorhanden sind. Die Konfigurations- und Regelverwaltungsbildschirme des Moduls werden mithilfe der PrestaShop-Klassen `HelperForm` und `HelperList` gerendert, die auf den Kern-PrestaShop-Template-Dateien basieren.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    *   `ps_myprestaloyalty_tenure_rule`: Speichert die Definitionen jeder Dienstalterregel.
        *   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        *   `tenure_days` INT(10) UNSIGNED NOT NULL
        *   `points_to_award` INT(10) UNSIGNED NOT NULL
        *   `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
        *   PRIMARY KEY (`id_myprestaloyalty_tenure_rule`)
    *   `ps_myprestaloyalty_tenure_awarded`: Zeichnet auf, welche Kunden für welche Regeln Punkte erhalten haben, um doppelte Vergaben zu verhindern.
        *   `id_myprestaloyalty_tenure_awarded` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        *   `id_customer` INT(10) UNSIGNED NOT NULL
        *   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL
        *   `date_awarded` DATETIME NOT NULL
        *   PRIMARY KEY (`id_myprestaloyalty_tenure_awarded`)
        *   UNIQUE KEY `customer_rule` (`id_customer`, `id_myprestaloyalty_tenure_rule`)
-   **Registrierte Hooks-Tabelle**:
    Das Modul registriert keine expliziten Front-Office-Display-Hooks (wie `displayHeader`, `displayRightColumn`, `displayProductExtraContent`, `displayFooter`), da seine Hauptfunktion die Hintergrundverarbeitung über Cron ist.
    Es verwendet implizit:

    | Hook-Name                   | Ausführungszeitpunkt          | Technischer Zweck                                                              |
    | :-------------------------- | :---------------------------- | :----------------------------------------------------------------------------- |
    | `actionModuleInstall`       | Während der Modulinstallation | Erstellt Datenbanktabellen, registriert Admin-Tab.                             |
    | `actionModuleUninstall`     | Während der Moduldeinstallation | Löscht Datenbanktabellen und Konfiguration.                                    |
    | `actionAdminControllerSetMedia` | Beim Laden eines Admin-Controllers | Wenn das Modul benutzerdefiniertes JS/CSS für den Admin hätte, würde es dies hier registrieren. (Wird in diesem Modul laut Inventar nicht verwendet) |
    | `displayBackOfficeTop`      | Rendert Inhalte oben im Back Office | Wird verwendet, um die Cron-Job-URL und Anweisungen auf der Konfigurationsseite des Moduls anzuzeigen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Treuepunkte – Dienstalter (Seniorität) Regeln“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und sicherzustellen, dass Ihr Modul optimal funktioniert.

-   **Zugriff auf Downloads & Updates:** Melden Sie sich in Ihrem Konto unter [MyPresta.eu Bestellhistorie & Downloads](https://mypresta.eu/my-account/orders/) an.
-   **Support kontaktieren:** Nutzen Sie die in Ihrem MyPresta.eu-Konto bereitgestellten Supportkanäle für technische Probleme oder Fragen.
