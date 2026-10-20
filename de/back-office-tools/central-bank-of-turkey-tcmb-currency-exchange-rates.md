---
title: "Zentralbank der Türkei (TCMB) – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Zentralbank der Türkei (TCMB) – Wechselkurse“ von MyPresta.eu."
sidebar:
  label: "Zentralbank der Türkei (TCMB) – Wechselkurse – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Central Bank of Turkey (TCMB) - currency exchange rates auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/central-bank-of-turkey-tcmb-currency-exchange-rates.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/central-bank-of-turkey-tcmb-currency-exchange-rates/)
>
> ---


# Zentralbank der Türkei (TCMB) – Wechselkurse

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für das Abrufen externer Daten erforderlich. Ihre Hosting-Umgebung sollte ausgehende Verbindungen zur TCMB-Website zulassen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modulnamen, um auf dessen Einstellungen zuzugreifen.

#### Allgemeine Einstellungen

- **Modul aktivieren**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul beginnt, Wechselkurse abzurufen und die Währungspreise Ihres Stores gemäß Ihren anderen Einstellungen zu aktualisieren.
    - *Wenn deaktiviert:* Das Modul stellt alle Operationen ein. Wechselkurse werden nicht automatisch aktualisiert, und Ihre Preise bleiben statisch, bis sie manuell geändert oder das Modul wieder aktiviert wird.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten, aktivieren Sie es, um seine Funktionen zu nutzen. Wenn Sie automatische Updates vorübergehend stoppen müssen (z. B. für Wartungsarbeiten), können Sie es deaktivieren.
- **CRON-URL**

  - **Was diese Einstellung bewirkt:** Dieses Feld zeigt eine eindeutige URL an, die, wenn sie aufgerufen wird, das Modul dazu veranlasst, die neuesten Wechselkurse von der TCMB abzurufen und die Währungspreise Ihres Stores zu aktualisieren.
  - **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld. Das Kopieren und Festlegen dieser URL im CRON-Job-Scheduler Ihres Hosting-Panels automatisiert die Kursaktualisierungen.
  - **Empfohlener Wert:** Kopieren Sie diese URL.
  - **Händlerszenario / Beispiel:** Sie kopieren diese URL und fügen sie in Ihr Hosting-Kontrollpanel (z. B. cPanel, Plesk oder eine benutzerdefinierte CRON-Job-Oberfläche) ein, um automatische Updates zu planen. Sie könnten es beispielsweise so einstellen, dass es einmal alle 24 Stunden ausgeführt wird, um die tägliche Preisgenauigkeit zu gewährleisten.
- **Marge (%)**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, eine prozentuale Marge zusätzlich zu den von der TCMB abgerufenen offiziellen Wechselkursen hinzuzufügen. Dies kann verwendet werden, um Transaktionsgebühren, Währungsumrechnungskosten zu decken oder einfach Ihre Preisstrategie anzupassen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf 0 gesetzt:* Ihr Store verwendet die exakten offiziellen Wechselkurse der TCMB.
    - *Wenn auf einen positiven Wert gesetzt (z. B. 2):* Das Modul erhöht den berechneten Wechselkurs um diesen Prozentsatz. Wenn der offizielle Kurs beispielsweise 1 USD = 30 TRY beträgt und Sie eine Marge von 2 % festlegen, verwendet das Modul 1 USD = 30,6 TRY für Umrechnungen. Dies bedeutet, dass in USD bepreiste Produkte in TRY etwas teurer erscheinen, oder umgekehrt, abhängig von Ihrer Basiswährung.
  - **Empfohlener Wert:** 0 (wenn Sie exakte offizielle Kurse wünschen) oder ein kleiner positiver Prozentsatz (z. B. 1-3 %), um Kosten zu decken.
  - **Händlerszenario / Beispiel:** Wenn Ihr Zahlungs-Gateway eine Gebühr von 1,5 % für Währungsumrechnungen erhebt, könnten Sie eine „Marge (%)“ von 1,5 festlegen, um diese Kosten zu absorbieren und Ihre Gewinnmargen zu erhalten.
- **Letzte Aktualisierung**

  - **Was diese Einstellung bewirkt:** Dieses schreibgeschützte Feld zeigt Datum und Uhrzeit an, wann das Modul zuletzt erfolgreich Wechselkursaktualisierungen abgerufen und angewendet hat.
  - **Auswirkung einer Änderung dieser Einstellung:** Dieses Feld wird nach jeder erfolgreichen CRON-Job-Ausführung oder manuellen Aktualisierung automatisch aktualisiert. Es hilft Ihnen zu überprüfen, ob das Modul korrekt funktioniert und wann die Kurse zuletzt aktualisiert wurden.
  - **Empfohlener Wert:** Überwachen Sie diesen Wert, um regelmäßige Updates sicherzustellen.
  - **Händlerszenario / Beispiel:** Nachdem Sie Ihren CRON-Job eingerichtet haben, können Sie dieses Feld überprüfen, um zu bestätigen, dass die automatischen Updates wie erwartet ausgeführt werden. Wenn das Datum alt ist, deutet dies auf ein Problem mit Ihrer CRON-Job-Einrichtung hin.

#### Manuelle Aktualisierung

- **Jetzt aktualisieren** Schaltfläche
  - **Was diese Einstellung bewirkt:** Diese Schaltfläche ermöglicht es Ihnen, den Wechselkursaktualisierungsprozess sofort manuell auszulösen, ohne auf den CRON-Job zu warten.
  - **Auswirkung einer Änderung dieser Einstellung:** Das Klicken auf diese Schaltfläche ruft sofort die neuesten Kurse von der TCMB ab und aktualisiert die Währungspreise Ihres Stores. Dies ist nützlich zum Testen oder für dringende Updates.
  - **Empfohlener Wert:** Klicken Sie, wenn Sie eine sofortige Aktualisierung benötigen oder zum Testen.
  - **Händlerszenario / Beispiel:** Sie haben gerade ein neues Produkt eingeführt und möchten sicherstellen, dass dessen Preis auf den allerneuesten Wechselkursen basiert, bevor Kunden bestellen. Sie können auf „Jetzt aktualisieren“ klicken, um alle Kurse sofort zu aktualisieren.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren | JA | Aktiviert/deaktiviert die Kernfunktionalität des Moduls. |
| Modulkonfiguration | CRON-URL | Diese URL kopieren | URL zum Einrichten automatischer Wechselkursaktualisierungen über Ihren Hosting-CRON-Job. |
| Modulkonfiguration | Marge (%) | 0-3% | Fügt eine prozentuale Marge zusätzlich zu den offiziellen TCMB-Wechselkursen für Preisgestaltungsflexibilität hinzu. |
| Modulkonfiguration | Letzte Aktualisierung | Überwachen | Zeigt Datum/Uhrzeit der letzten erfolgreichen Wechselkursaktualisierung an. |
| Modulkonfiguration | Jetzt aktualisieren Schaltfläche | Bei Bedarf klicken | Löst eine sofortige manuelle Wechselkursaktualisierung aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Preise werden nicht aktualisiert, obwohl ich das Modul konfiguriert habe.**
A1: Überprüfen Sie zunächst, ob die Einstellung „Modul aktivieren“ auf JA steht. Zweitens, überprüfen Sie Ihre CRON-Job-Einrichtung in Ihrem Hosting-Panel. Stellen Sie sicher, dass die CRON-URL korrekt ist und der Job zur Ausführung geplant ist. Sie können auch versuchen, auf die Schaltfläche „Jetzt aktualisieren“ in der Modulkonfiguration zu klicken, um zu sehen, ob eine manuelle Aktualisierung funktioniert. Wenn dies der Fall ist, liegt das Problem wahrscheinlich bei Ihrem CRON-Job.

**F2: Das Feld „Letzte Aktualisierung“ zeigt ein altes Datum an, aber mein CRON-Job ist eingerichtet.**
A2: Dies bedeutet normalerweise, dass Ihr CRON-Job nicht korrekt ausgeführt wird oder das Modul beim Versuch, Daten abzurufen, einen Fehler feststellt.
- **CRON-Job-Protokolle überprüfen:** Viele Hosting-Anbieter bieten Protokolle für CRON-Job-Ausführungen an. Suchen Sie dort nach Fehlern.
- **Serverzugriff:** Stellen Sie sicher, dass Ihr Server ausgehenden Internetzugriff auf `www.tcmb.gov.tr` (die Website der Zentralbank der Türkei) hat. Firewalls oder Netzwerkbeschränkungen können dies blockieren.
- **PHP-Version:** Bestätigen Sie, dass Ihre PHP-Version innerhalb des unterstützten Bereichs liegt (PHP 5.6 - 8.5).
- **Modul-Neuinstallation:** Als letzten Ausweg versuchen Sie, das Modul zu deinstallieren und neu zu installieren (nachdem Sie Ihren Store gesichert haben), um sicherzustellen, dass alle Dateien korrekt vorhanden sind.

**F3: Kann ich die Kurse häufiger als einmal täglich aktualisieren?**
A3: Ja, Sie können Ihren CRON-Job so konfigurieren, dass er häufiger ausgeführt wird (z. B. alle 6 Stunden, jede Stunde). Berücksichtigen Sie jedoch die Auswirkungen auf Ihre Serverressourcen und die tatsächliche Häufigkeit der TCMB-Kursänderungen. Tägliche Updates sind für die meisten E-Commerce-Stores in der Regel ausreichend, da sich die offiziellen Kurse typischerweise einmal pro Geschäftstag ändern.

**F4: Ich habe mehrere Währungen. Wird dieses Modul alle aktualisieren?**
A4: Ja, das Modul ruft die offiziellen Wechselkurse für die Türkische Lira (TRY) gegenüber anderen wichtigen Währungen ab. Es verwendet diese Kurse dann, um die Preise für alle aktiven Währungen in Ihrem PrestaShop-Store basierend auf Ihrer Basiswährung und den abgerufenen TRY-Kursen neu zu berechnen und zu aktualisieren.

**F5: Was passiert, wenn die TCMB-Website nicht erreichbar ist?**
A5: Wenn das Modul keine Verbindung zur TCMB-Website herstellen kann, schlägt es typischerweise fehl, die Kurse zu aktualisieren. Ihre bestehenden Währungskurse bleiben unverändert, bis eine erfolgreiche Verbindung und Aktualisierung hergestellt werden kann. Das Feld „Letzte Aktualisierung“ ändert sich nicht, was auf ein Problem hinweist.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Store-Webmaster und technische Agenturen, die den Store warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `tcmbrates` ist als Standard-PrestaShop-Modul konzipiert und nutzt hauptsächlich die `Module`-Klasse für seine Kernfunktionalität. Sein Hauptzweck ist das Abrufen externer Daten (TCMB-Wechselkurse) und das Aktualisieren der internen Währungskurse von PrestaShop. Es verwendet einen Front-Controller für die CRON-Job-Ausführung, wodurch es extern ohne direkte Back-Office-Interaktion ausgelöst werden kann. Die Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt, die ein einfaches Formular für Einstellungen und einen manuellen Update-Trigger anzeigt.

### 4.2 Controller (`controllers/`)

Das Modul enthält Front-Controller zur Bearbeitung externer Anfragen, insbesondere für den CRON-Job.

- **Front-Office-Controller**:

  - `controllers/front/cronjob.php`
    - **Klassenname & Elternklasse:** `TcmbratesCronjobModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dieser Controller ist dafür konzipiert, von einem externen CRON-Job-Scheduler aufgerufen zu werden. Beim Zugriff löst er die Kernlogik des Moduls aus, um die neuesten Wechselkurse von der Zentralbank der Türkei abzurufen und die Währungskurse in der PrestaShop-Datenbank zu aktualisieren. Er gibt typischerweise eine Erfolgs- oder Fehlermeldung aus.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse:** `TcmbratesIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dies ist ein Platzhalter oder Standard-Front-Controller, der oft in Modulen enthalten ist, aber nicht immer aktiv für spezifische Funktionen verwendet wird. Im Kontext dieses Moduls dient er wahrscheinlich als Fallback oder einfacher Einstiegspunkt, wenn kein anderer spezifischer Front-Controller angefordert wird. Seine primäre Funktion ist normalerweise die Weiterleitung oder die Anzeige einer generischen Nachricht.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Administration erfolgt über die `getContent()`-Methode des Moduls.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen, die `ObjectModel` erweitern. Seine Kernlogik befindet sich in der Hauptmoduldatei (`cronjob.php`).

### 4.4 JavaScript-Assets (`views/js/`)

In diesem Modul sind keine benutzerdefinierten JavaScript-Dateien enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

In diesem Modul sind keine benutzerdefinierten CSS-Dateien enthalten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet ein einziges Smarty-Template für seine Back-Office-Konfigurationsoberfläche.

- **Admin-Templates (`views/templates/admin/`)**:
  - `views/admin.tpl`
    - **Zweck:** Dieses Template wird von der `getContent()`-Methode der Hauptmoduldatei (`cronjob.php`) gerendert. Es zeigt das Konfigurationsformular des Moduls im PrestaShop Back Office an, einschließlich Feldern zum Aktivieren des Moduls, Festlegen der Marge, Anzeigen der CRON-URL und Bereitstellen einer manuellen Aktualisierungsschaltfläche.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Es speichert seine Konfigurationseinstellungen (z. B. `PS_TCMBRATES_ENABLED`, `PS_TCMBRATES_MARGIN`, `PS_TCMBRATES_LAST_UPDATE`) in der Standardtabelle `ps_configuration`. Es interagiert direkt mit der PrestaShop-Tabelle `ps_currency`, um Wechselkurse zu aktualisieren.
- **Registrierte Hooks-Tabelle**: Das Modul registriert sich nicht explizit bei Standard-Display-Hooks wie `displayHeader` oder `displayFooter` für Front-Office-Inhalte. Seine primäre Interaktion mit dem PrestaShop-System erfolgt über seine interne Logik, die durch den CRON-Job oder die manuelle Aktualisierung ausgelöst wird und dann vorhandene Währungsdaten modifiziert.

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `install()` | Modulinstallation | Erstellt Konfigurationseinträge in `ps_configuration`. |
  | `uninstall()` | Moduldeinstallation | Löscht Konfigurationseinträge aus `ps_configuration`. |
  | (Keine expliziten Front-Office-Display-Hooks) | N/A | Modul arbeitet im Hintergrund, um Daten zu aktualisieren, nicht um Inhalte anzuzeigen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Zentralbank der Türkei (TCMB) – Wechselkurse“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
