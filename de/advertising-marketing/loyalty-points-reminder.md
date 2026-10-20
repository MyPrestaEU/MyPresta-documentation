---
title: "Erinnerung an Treuepunkte – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Erinnerung an Treuepunkte“ von MyPresta.eu."
sidebar:
  label: "Erinnerung an Treuepunkte – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Loyalty points reminder auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-reminder.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/loyalty-points-reminder/)
>
> ---


# Erinnerung an Treuepunkte

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Das Modul basiert auf den nativen PrestaShop-Mailfunktionen und Cronjob-Fähigkeiten.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Erinnerung an Treuepunkte)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Erinnerung an Treuepunkte“. Hier definieren Sie, wie und wann die Erinnerungs-E-Mails gesendet werden.

#### **Modul aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul prüft aktiv auf ablaufende Treuepunkte und sendet Erinnerungs-E-Mails gemäß Ihren anderen Einstellungen.
  - *Wenn deaktiviert:* Das Modul sendet keine Erinnerungs-E-Mails, unabhängig von anderen Einstellungen.
- **Empfohlener Wert:** JA (sobald Sie die anderen Einstellungen konfiguriert haben).
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten beginnen, Kunden zu erinnern. Sie würden dies aktivieren, nachdem Sie die Tage vor dem Ablaufdatum eingerichtet haben.

#### **Tage vor Ablauf, um Erinnerung zu senden**

- **Was diese Einstellung bewirkt:** Dies bestimmt, wie viele Tage *vor* dem Ablauf der Treuepunkte eines Kunden die Erinnerungs-E-Mail gesendet wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf 7 eingestellt:* Kunden erhalten 7 Tage vor Ablauf ihrer Punkte eine E-Mail.
  - *Wenn auf 30 eingestellt:* Kunden erhalten 30 Tage vor Ablauf ihrer Punkte eine E-Mail.
- **Empfohlener Wert:** 7-14 Tage. Dies gibt Kunden genügend Zeit zum Reagieren, ohne zu weit im Voraus zu sein, sodass sie es vergessen.
- **Händlerszenario / Beispiel:** Sie möchten Kunden eine Woche Zeit geben, ihre Punkte zu nutzen. Sie würden dies auf „7“ setzen. Wenn Sie ihnen mehr Spielraum geben möchten, vielleicht „14“.

#### **Cron Job URL**

- **Was diese Einstellung bewirkt:** Dies zeigt eine eindeutige URL an, die Sie als Cronjob auf Ihrem Server einrichten müssen. Ein Cronjob ist eine geplante Aufgabe, die Ihrem Server mitteilt, ein bestimmtes Skript in regelmäßigen Abständen (z. B. einmal täglich) auszuführen. So prüft das Modul automatisch auf ablaufende Punkte und sendet E-Mails, ohne dass Sie manuell etwas tun müssen.
- **Auswirkung der Änderung dieser Einstellung:** Sie können diese Einstellung nicht direkt ändern. Es ist eine generierte URL.
  - *Wenn der Cronjob korrekt eingerichtet ist:* Das Modul wird automatisch ausgeführt und sendet E-Mails wie konfiguriert.
  - *Wenn der Cronjob NICHT eingerichtet ist:* Das Modul sendet niemals Erinnerungs-E-Mails, auch wenn es aktiviert ist.
- **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie als täglichen Cronjob auf Ihrem Hosting-Server ein.
- **Händlerszenario / Beispiel:** Nachdem Sie die Einstellung „Tage vor Ablauf“ konfiguriert haben, würden Sie diese URL kopieren und in den Cronjob-Scheduler Ihres Hosting-Kontrollpanels (z. B. cPanel, Plesk oder direkter Serverzugriff) einfügen. Sie würden ihn normalerweise so einstellen, dass er einmal alle 24 Stunden ausgeführt wird.

#### **Test-E-Mail-Adresse**

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine Test-Erinnerungs-E-Mail an eine bestimmte Adresse zu senden, um sicherzustellen, dass das Modul korrekt funktioniert und der E-Mail-Inhalt gut aussieht.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Eingabe einer E-Mail-Adresse und Klicken auf „Test-E-Mail senden“:* Eine E-Mail wird an die angegebene Adresse gesendet, die eine Erinnerung an Treuepunkte simuliert. Diese E-Mail enthält Platzhalterdaten, da es sich um einen Test handelt.
- **Empfohlener Wert:** Verwenden Sie Ihre eigene E-Mail-Adresse oder die eines Kollegen zum Testen.
- **Händlerszenario / Beispiel:** Bevor Sie live gehen, möchten Sie sehen, wie die Erinnerungs-E-Mail aussieht. Sie würden hier Ihre E-Mail-Adresse eingeben und auf die Testschaltfläche klicken.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Modul aktivieren / deaktivieren** | JA | Hauptschalter zum Aktivieren oder Deaktivieren der Erinnerungs-E-Mails. |
| Modulkonfiguration | **Tage vor Ablauf, um Erinnerung zu senden** | 7-14 Tage | Definiert, wie viele Tage vor Ablauf der Punkte die E-Mail gesendet wird. |
| Modulkonfiguration | **Cron Job URL** | Kopieren & Täglich einstellen | Wesentlich für den automatischen E-Mail-Versand; muss auf Ihrem Server konfiguriert werden. |
| Modulkonfiguration | **Test-E-Mail-Adresse** | Ihre E-Mail zum Testen | Sendet eine Beispiel-Erinnerungs-E-Mail zur Überprüfung des Inhalts und der Zustellung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden erhalten keine Erinnerungs-E-Mails. Was sollte ich überprüfen?**
A:

1. **Ist das Modul aktiviert?** Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass „Modul aktivieren / deaktivieren“ auf JA eingestellt ist.
2. **Ist der Cronjob korrekt eingerichtet?** Dies ist das häufigste Problem. Das Modul benötigt einen Cronjob, um automatisch ausgeführt zu werden. Kopieren Sie die „Cron Job URL“ aus der Modulkonfiguration und stellen Sie sicher, dass sie auf Ihrem Hosting-Server korrekt für die tägliche Ausführung konfiguriert ist.
3. **Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen:** Gehen Sie in Ihrem Back Office zu **Erweiterte Einstellungen > E-Mail**. Senden Sie von dort eine Test-E-Mail, um sicherzustellen, dass das E-Mail-System Ihres Shops funktioniert.
4. **Überprüfen Sie die Spam-Ordner:** Bitten Sie Kunden, ihre Spam- oder Junk-Ordner zu überprüfen.
5. **Smarty-Cache leeren:** Manchmal erfordern Template-Änderungen oder Modul-Updates das Leeren des Caches. Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten zu „Cache leeren“ und klicken Sie auf „Cache leeren“.

**F: Die Test-E-Mail funktioniert, aber Kunden erhalten immer noch keine Erinnerungen.**
A: Dies deutet stark darauf hin, dass der Cronjob das Problem ist. Die Test-E-Mail verwendet den sofortigen E-Mail-Versand von PrestaShop, während tatsächliche Erinnerungen davon abhängen, dass der Cronjob den Hintergrundprozess des Moduls ausführt. Überprüfen Sie Ihre Cronjob-Einrichtung noch einmal mit Ihrem Hosting-Anbieter.

**F: Kann ich den Inhalt der Erinnerungs-E-Mail anpassen?**
A: Das Modul verwendet die Standard-E-Mail-Vorlagen von PrestaShop. Sie finden die E-Mail-Vorlagendateien normalerweise im `mails/`-Verzeichnis Ihres Themes (z. B. `themes/yourtheme/mails/de/loyalty_points_reminder.html` und `loyalty_points_reminder.txt`). Wenn diese nicht existieren, verwendet das Modul die Standard-PrestaShop-Mail-Vorlagen. Sie können diese in Ihrem Theme überschreiben, um den Text und das Erscheinungsbild anzupassen.

**F: Was passiert, wenn ein Kunde keine Treuepunkte hat?**
A: Das Modul ist so konzipiert, dass es nur E-Mails an Kunden sendet, die tatsächlich Treuepunkte haben, deren Ablaufdatum sich nähert. Wenn ein Kunde keine Punkte hat oder seine Punkte nicht bald ablaufen, erhält er keine E-Mail.

**F: Funktioniert dieses Modul mit benutzerdefinierten Treuepunkte-Modulen?**
A: Dieses Modul ist für die Zusammenarbeit mit dem nativen PrestaShop-Treuepunktesystem konzipiert. Wenn Sie ein Treuepunkte-Modul eines Drittanbieters verwenden, integriert es sich möglicherweise nicht direkt, es sei denn, dieses Modul erweitert oder verwendet die Kernfunktionen von PrestaShop in einer kompatiblen Weise.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Erinnerung an Treuepunkte“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Erinnerung an Treuepunkte“ (`lpreminder`) ist ein Standard-PrestaShop-Modul, das einem MVC-ähnlichen Muster folgt. Seine Kernfunktionalität dreht sich um eine geplante Aufgabe (Cronjob), die einen Front-Controller auslöst, um ablaufende Treuepunkte zu verarbeiten und E-Mails zu senden. Es nutzt die nativen PrestaShop-Klassen `LoyaltyModule` und `Mail`.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller sind so konzipiert, dass sie über eine bestimmte URL zugänglich sind, hauptsächlich für die Cronjob-Ausführung.

- **`controllers/front/cronjob.php`**
  - **Klassenname & Elternklasse:** `LpreminderCronjobModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist der kritische Endpunkt für den Cronjob. Beim Zugriff führt er die Logik des Moduls aus, um Kunden mit ablaufenden Treuepunkten zu identifizieren und Erinnerungs-E-Mails zu versenden. Er sollte idealerweise geschützt sein (z. B. durch ein Token oder eine IP-Beschränkung), falls dies nicht bereits vom Modul implementiert wurde, um unbefugten Zugriff zu verhindern. Er rendert keine visuelle Ausgabe, sondern führt Hintergrundverarbeitung durch.
- **`controllers/front/index.php`**
  - **Klassenname & Elternklasse:** `LpreminderIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller könnte als Standard-Einstiegspunkt oder Platzhalter dienen. In vielen Modulen, wenn eine bestimmte Aktion nicht definiert ist, könnte `index.php` diese behandeln. Angesichts der primären Funktion des Moduls ist `cronjob.php` der wichtigste operative Front-Controller. Dieses `index.php` könnte ein Fallback sein oder für zukünftige Erweiterungen verwendet werden.

#### Back-Office-Admin-Controller

Das Modul verwendet keine benutzerdefinierten Admin-Controller. Die gesamte Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s im Verzeichnis `classes/`. Es interagiert direkt mit den Kernklassen von PrestaShop, insbesondere:

- `LoyaltyModule`: Zum Abrufen von Kunden-Treuepunkten und deren Ablaufdaten.
- `Customer`: Zum Abrufen von Kundendetails für den E-Mail-Versand.
- `Mail`: Zum Senden der Erinnerungs-E-Mails.
- `Configuration`: Zum Speichern und Abrufen von Moduleinstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Alle Funktionen werden serverseitig verarbeitet.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien. Die Konfigurationsseite verwendet das Standard-Back-Office-Styling von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul enthält keine benutzerdefinierten Smarty-Template-Dateien in seinem Verzeichnis `views/templates/`.

- **E-Mail-Vorlagen:** Das Modul basiert auf dem Standard-E-Mail-Vorlagensystem von PrestaShop. Der E-Mail-Inhalt für die Erinnerung wird mithilfe einer Vorlage namens `loyalty_points_reminder` generiert. Entwickler können diese E-Mail anpassen, indem sie die folgenden Dateien im `mails/`-Verzeichnis ihres aktiven Themes erstellen oder überschreiben:
  - `themes/yourtheme/mails/de/loyalty_points_reminder.html` (für HTML-E-Mail-Inhalt)
  - `themes/yourtheme/mails/de/loyalty_points_reminder.txt` (für Nur-Text-E-Mail-Inhalt)
  - Ersetzen Sie `de` durch den entsprechenden Sprachcode.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen (z. B. `PS_LPREMINDER_DAYS_BEFORE_EXPIRY`, `PS_LPREMINDER_ENABLED`) in der Tabelle `ps_configuration`. Es fragt bestehende PrestaShop-Tabellen wie `ps_loyalty_history` und `ps_customer` ab.
- **Registrierte Hooks-Tabelle**:
  Das Modul verwendet hauptsächlich den Hook `actionFrontControllerSetMedia` für potenzielle zukünftige JS/CSS-Einbindung (obwohl derzeit keine vorhanden sind) und verlässt sich implizit auf den Cronjob-Mechanismus für seine Kernfunktionalität, der kein traditioneller PrestaShop-Hook, sondern ein externer Trigger für einen Front-Controller ist.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich von Front-Office-Seiten. | Nicht direkt für die Kernlogik des Moduls verwendet, könnte aber bei Bedarf für JS/CSS verwendet werden. |
| `displayRightColumn` | Rendert Inhalte in der rechten Spalte von Front-Office-Seiten. | Nicht direkt für die Kernlogik des Moduls verwendet. |
| `displayLeftColumn` | Rendert Inhalte in der linken Spalte von Front-Office-Seiten. | Nicht direkt für die Kernlogik des Moduls verwendet. |
| `displayFooter` | Rendert Inhalte im Footer von Front-Office-Seiten. | Nicht direkt für die Kernlogik des Moduls verwendet. |
| `displayProductExtraContent` | Rendert Inhalte auf der Produktseite. | Nicht direkt für die Kernlogik des Moduls verwendet. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (JS/CSS) einstellt. | Ermöglicht dem Modul, bei Bedarf eigene JS/CSS-Assets zu registrieren. |
| *(Cronjob-Trigger)* | Externe serverseitig geplante Aufgabe (z. B. täglich). | Löst den `cronjob.php`-Front-Controller aus, um ablaufende Treuepunkte zu verarbeiten und E-Mails zu senden. Dies ist der primäre operative Trigger des Moduls. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Erinnerung an Treuepunkte“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
