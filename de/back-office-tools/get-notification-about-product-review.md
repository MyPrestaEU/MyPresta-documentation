---
title: "Benachrichtigung über Produktbewertung erhalten - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Benachrichtigung über Produktbewertung erhalten' von MyPresta.eu."
sidebar:
  label: "Benachrichtigung über Produktbewertung erhalten"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Get notification about product review auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/get-notification-about-product-review.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/get-notification-about-product-review/)
>
> ---


# Benachrichtigung über Produktbewertung erhalten

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).
-   **Voraussetzung**: Dieses Modul erfordert, dass unser kostenloses Produktbewertungs-Addon installiert und aktiv ist. Es erweitert die Funktionalität dieses Moduls.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation gelangen Sie durch Klicken auf "Konfigurieren" zum Haupt- und einzigen Konfigurationsbildschirm für dieses Modul. Dieser Bildschirm ermöglicht es Ihnen, festzulegen, welche E-Mail-Adresse die Benachrichtigungen erhält.

#### **E-Mail-Adresse für Benachrichtigungen**
-   **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie bestimmt die E-Mail-Adresse, an die alle bewertungsbezogenen Benachrichtigungen gesendet werden.
-   **Auswirkung einer Änderung dieser Einstellung:**
    -   *Wenn eine gültige E-Mail-Adresse eingegeben wird:* Alle Benachrichtigungen (neue Bewertung, gemeldeter Kommentar, nützliche Stimme) werden an diese spezifische E-Mail-Adresse gesendet.
    -   *Wenn leer gelassen oder eine ungültige E-Mail-Adresse eingegeben wird:* Sie erhalten keine Benachrichtigungen, wodurch die Kernfunktion des Moduls effektiv deaktiviert wird.
-   **Empfohlener Wert:** Ihre primäre Geschäfts-E-Mail-Adresse oder eine E-Mail-Adresse, die regelmäßig von Ihrem Kundenservice- oder Marketingteam überwacht wird.
-   **Händlerszenario / Beispiel:** Wenn Ihr Kundenservice-Team alle Kundeninteraktionen bearbeitet, könnten Sie hier `kundenservice@ihrshop.com` eingeben. Wenn Sie als Inhaber persönlich informiert werden möchten, verwenden Sie Ihre direkte E-Mail-Adresse.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Modulkonfiguration | E-Mail-Adresse für Benachrichtigungen | Ihre primäre Geschäfts-E-Mail | Gibt den E-Mail-Empfänger für alle bewertungsbezogenen Benachrichtigungen an (neue Bewertung, gemeldeter Kommentar, nützliche Stimme). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich erhalte keine E-Mail-Benachrichtigungen. Was soll ich tun?**
A:
1.  **Überprüfen Sie die E-Mail-Adresse:** Gehen Sie zu **Module > Modul-Manager > Konfigurieren** für "Benachrichtigung über Produktbewertung erhalten" und stellen Sie sicher, dass die eingegebene E-Mail-Adresse korrekt und fehlerfrei ist.
2.  **Überprüfen Sie Ihren Spam-Ordner:** Benachrichtigungen können manchmal in Ihren Spam- oder Junk-Ordner gefiltert werden. Fügen Sie die Absender-E-Mail-Adresse (normalerweise die Standard-E-Mail Ihres Shops) zu Ihrer Liste der sicheren Absender hinzu.
3.  **Überprüfen Sie die PrestaShop-E-Mail-Einstellungen:** Stellen Sie sicher, dass die E-Mail-Einstellungen Ihres PrestaShop-Shops korrekt konfiguriert sind und E-Mails im Allgemeinen gesendet werden. Sie können dies testen, indem Sie ein neues Kundenkonto erstellen oder eine Testbestellung aufgeben. Gehen Sie in Ihrem Back Office zu **Erweiterte Einstellungen > E-Mail**.
4.  **Kontaktieren Sie Ihren Hosting-Anbieter:** Wenn die E-Mails von PrestaShop überhaupt nicht funktionieren, könnte ein Problem mit der Mailfunktion Ihres Servers vorliegen. Ihr Hosting-Anbieter kann Ihnen bei der Diagnose helfen.
5.  **Stellen Sie sicher, dass das Voraussetzungsmodul installiert ist:** Dieses Modul erweitert unser kostenloses Produktbewertungs-Addon. Stellen Sie sicher, dass dieses Modul installiert ist und korrekt funktioniert.

**F: Kann ich Benachrichtigungen an mehrere E-Mail-Adressen senden?**
A: Das aktuelle Design des Moduls erlaubt die Konfiguration nur einer E-Mail-Adresse. Wenn Sie an mehrere Empfänger senden müssen, können Sie eine E-Mail-Weiterleitungsregel in Ihrem E-Mail-Client oder Server einrichten (z. B. E-Mails von der konfigurierten Adresse an einen Gruppenalias weiterleiten).

**F: Funktioniert dieses Modul mit jedem Produktbewertungssystem?**
A: Nein, dieses Modul wurde speziell entwickelt, um als Erweiterung des **kostenlosen Produktbewertungs-Addons von MyPresta.eu** zu funktionieren. Es wird keine Benachrichtigungen für andere Produktbewertungsmodule von Drittanbietern bereitstellen.

**F: Ich habe mein PrestaShop-Theme aktualisiert, und jetzt funktionieren die Benachrichtigungen nicht mehr.**
A: Dieses Modul hat keine Front-Office-Komponenten, daher sollte eine Theme-Änderung seine Benachrichtigungsfunktion nicht direkt beeinflussen. Überprüfen Sie die E-Mail-Konfiguration im Modul und Ihre PrestaShop-E-Mail-Einstellungen wie oben beschrieben erneut. Wenn das Problem weiterhin besteht, ist es wahrscheinlich nicht mit dem Theme verbunden und deutet auf ein Server- oder PrestaShop-Kern-E-Mail-Problem hin.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul "Benachrichtigung über Produktbewertung erhalten" (`reviewsalerts`) ist ein leichtgewichtiges PrestaShop-Modul, das entwickelt wurde, um die Funktionalität des Kernmoduls `productcomments` (oder eines ähnlichen Bewertungsmoduls, speziell des kostenlosen Produktbewertungs-Addons von MyPresta.eu) zu erweitern. Es arbeitet hauptsächlich, indem es sich in relevante Aktionen einklinkt, die vom Bewertungssystem ausgelöst werden, und E-Mail-Benachrichtigungen basierend auf diesen Ereignissen sendet. Es folgt einem einfachen ereignisgesteuerten Muster und nutzt das Hook-System von PrestaShop, ohne komplexe MVC-Strukturen oder benutzerdefinierte Datenbanktabellen einzuführen.

### 4.2 Controller (`controllers/`)
Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der Hauptmoduldatei gekapselt und wird über Hooks ausgeführt.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Seine Funktionalität ist in der Hauptklasse `reviewsalerts` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)
Dieses Modul enthält keine JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)
Dieses Modul enthält keine CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien für die Front-Office-Anzeige oder die Back-Office-Konfiguration. Das Konfigurationsformular wird dynamisch von `getContent()` in der Hauptmoduldatei generiert.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine einzelne Konfigurationseinstellung (die Benachrichtigungs-E-Mail-Adresse) in der Standardtabelle `ps_configuration`.
    *   **Konfigurationsschlüssel**: `REVIEWSALERTS_EMAIL`

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `actionObjectProductCommentAddAfter` | Nachdem eine neue Produktbewertung (Kommentar) erfolgreich in die Datenbank hinzugefügt wurde. | Löst eine E-Mail-Benachrichtigung an die konfigurierte Adresse aus, die den Händler über die neue Bewertung informiert. |
| `actionObjectProductCommentReportAfter` | Nachdem eine Produktbewertung erfolgreich von einem Kunden gemeldet wurde. | Löst eine E-Mail-Benachrichtigung an die konfigurierte Adresse aus, die den Händler darüber informiert, dass eine Bewertung gemeldet wurde. |
| `actionObjectProductCommentUsefulAfter` | Nachdem ein Kunde eine Produktbewertung als "nützlich" markiert hat. | Löst eine E-Mail-Benachrichtigung an die konfigurierte Adresse aus, die den Händler darüber informiert, dass über die Nützlichkeit einer Bewertung abgestimmt wurde. |

Die `install()`-Methode des Moduls registriert diese Hooks, und die entsprechenden Methoden `hookActionObjectProductCommentAddAfter()`, `hookActionObjectProductCommentReportAfter()` und `hookActionObjectProductCommentUsefulAfter()` behandeln die E-Mail-Versandlogik.

Der E-Mail-Versand wird typischerweise von der PrestaShop-Funktion `Mail::Send()` gehandhabt, die die konfigurierten E-Mail-Vorlagen und -Einstellungen des Shops nutzt. Das Modul würde den E-Mail-Inhalt wahrscheinlich dynamisch basierend auf dem Kontext der ausgelösten Aktion (z. B. Bewertungsinhalt, Produktname, Details des Meldenden) erstellen.

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul "Benachrichtigung über Produktbewertung erhalten" besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
