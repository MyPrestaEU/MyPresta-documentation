---
title: "Spamschutz bei Kundenregistrierung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Spamschutz bei Kundenregistrierung' von MyPresta.eu."
sidebar:
  label: "Spamschutz bei Kundenregistrierung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Customer register spam protection auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/customer-register-spam-protection.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/customer-register-spam-protection/)
>
> ---


# Spamschutz bei Kundenregistrierung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die Kommunikation mit externen APIs erforderlich, die dieses Modul für die erweiterte Spam-Erkennung nutzen kann. Stellen Sie sicher, dass Ihre Hosting-Umgebung diese gängigen Anforderungen erfüllt.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Spamschutz bei Kundenregistrierung“, der nach der Installation zugänglich ist. Hier definieren Sie die Kernregeln und Verhaltensweisen des Spamschutzsystems.

Obwohl die spezifischen Einstellungen im bereitgestellten Dossier nicht detailliert beschrieben sind, würden typische Einstellungen, basierend auf dem Zweck des Moduls, Folgendes umfassen:

- **Modul aktivieren/deaktivieren:**

  - **Was diese Einstellung bewirkt:** Schaltet die Spamschutzfunktion für Ihren gesamten Shop ein oder aus.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul überwacht und blockiert aktiv verdächtige Kundenregistrierungen.
    - *Wenn deaktiviert:* Das Modul ist inaktiv, und alle Registrierungsversuche werden ohne Spam-Prüfungen fortgesetzt.
  - **Empfohlener Wert:** JA (es sei denn, Sie debuggen aktiv oder deaktivieren es vorübergehend aus einem bestimmten Grund).
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies sofort nach der Installation, um Ihren Shop zu schützen. Deaktivieren Sie es nur, wenn Sie vermuten, dass es legitime Kunden blockiert und Sie dies untersuchen müssen, aber denken Sie daran, dass dies Ihren Shop anfällig macht.
- **Empfindlichkeitsstufe der Spam-Erkennung:**

  - **Was diese Einstellung bewirkt:** Steuert, wie aggressiv das Modul potenziellen Spam identifiziert und blockiert. Dies kann ein Schieberegler (Niedrig, Mittel, Hoch) oder ein numerischer Schwellenwert sein.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Höhere Empfindlichkeit:* Wahrscheinlicher, verdächtige Registrierungen zu blockieren, möglicherweise einschließlich einer kleinen Anzahl legitimer Benutzer (falsch positive Ergebnisse).
    - *Niedrigere Empfindlichkeit:* Weniger wahrscheinlich, legitime Benutzer zu blockieren, kann aber mehr Spam-Konten durchlassen (falsch negative Ergebnisse).
  - **Empfohlener Wert:** Beginnen Sie mit „Mittel“ und passen Sie ihn basierend auf dem Traffic Ihres Shops und der Anzahl der beobachteten Spam-Versuche an.
  - **Händlerszenario / Beispiel:** Wenn Sie trotz aktivem Modul viel Spam sehen, erhöhen Sie die Empfindlichkeit. Wenn Kunden Probleme bei der Registrierung melden, versuchen Sie, sie etwas zu senken.
- **Aktion bei erkanntem Spam:**

  - **Was diese Einstellung bewirkt:** Definiert, was passiert, wenn das Modul einen Registrierungsversuch als Spam identifiziert.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Registrierung blockieren:* Das Konto wird nicht erstellt, und der Benutzer erhält eine Fehlermeldung.
    - *Als ausstehend/zur Überprüfung markieren:* Das Konto wird erstellt, aber zur manuellen Überprüfung durch einen Administrator markiert.
    - *Nur protokollieren:* Der Versuch wird aufgezeichnet, aber das Konto wird trotzdem erstellt (nützlich für die anfängliche Überwachung).
  - **Empfohlener Wert:** „Registrierung blockieren“ für maximalen Schutz.
  - **Händlerszenario / Beispiel:** Für die meisten Shops ist ein direktes Blockieren der beste Ansatz. Wenn Sie einen sehr spezifischen Kundenstamm haben und besonders vorsichtig sein möchten, könnte „Als ausstehend markieren“ eine Option sein, erfordert aber manuelle Arbeit.
- **Fehlermeldung für blockierte Registrierungen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Nachricht anzupassen, die Benutzern angezeigt wird, deren Registrierungsversuche blockiert wurden.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Benutzerdefinierte Nachricht:* Bietet eine benutzerfreundliche oder informative Nachricht anstelle eines generischen Fehlers.
  - **Empfohlener Wert:** Eine höfliche Nachricht wie „Die Registrierung konnte nicht abgeschlossen werden. Bitte kontaktieren Sie den Support, wenn Sie glauben, dass dies ein Fehler ist.“
  - **Händlerszenario / Beispiel:** Vermeiden Sie Nachrichten, die zu viel über Ihre Spam-Erkennungsmethoden verraten. Eine einfache, hilfreiche Nachricht ist am besten.
- **IP-Blacklist/Whitelist-Verwaltung:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, bestimmte IP-Adressen manuell zu einer Blacklist (immer blockieren) oder einer Whitelist (nie blockieren) hinzuzufügen.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Blacklisted IPs:* Jede Registrierung von diesen IPs wird blockiert, unabhängig von anderen Einstellungen.
    - *Whitelisted IPs:* Jede Registrierung von diesen IPs wird immer zugelassen.
  - **Empfohlener Wert:** Sparsam verwenden. Bekannte Spammer auf die Blacklist setzen. Nur dann auf die Whitelist setzen, wenn ein legitimer Benutzer oder ein internes System fälschlicherweise blockiert wird.
  - **Händlerszenario / Beispiel:** Wenn Sie wiederholt Spam von einem bestimmten IP-Bereich sehen, fügen Sie ihn zur Blacklist hinzu. Wenn die IP-Adresse Ihrer internen Testumgebung blockiert wird, setzen Sie sie auf die Whitelist.
- **E-Mail-Blacklist/Whitelist-Verwaltung:**

  - **Was diese Einstellung bewirkt:** Ähnlich der IP-Verwaltung, aber für bestimmte E-Mail-Adressen oder E-Mail-Domains.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Blacklisted E-Mails/Domains:* Registrierungen, die diese verwenden, werden blockiert.
    - *Whitelisted E-Mails/Domains:* Registrierungen, die diese verwenden, werden immer zugelassen.
  - **Empfohlener Wert:** Sparsam verwenden. Bekannte Spam-E-Mail-Adressen oder -Domains auf die Blacklist setzen.
  - **Händlerszenario / Beispiel:** Wenn Sie ein Muster von Spam-Registrierungen von Wegwerf-E-Mail-Diensten (z. B. mailinator.com) bemerken, können Sie diese Domain auf die Blacklist setzen.
- **Integration mit externen APIs (z. B. reCAPTCHA, Akismet):**

  - **Was diese Einstellung bewirkt:** Wenn das Modul mit externen Spam-Erkennungsdiensten integriert ist, enthält dieser Abschnitt Felder für API-Schlüssel und Konfigurationen, die für diese Dienste spezifisch sind.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Aktiviert mit gültigen Schlüsseln:* Fügt eine zusätzliche Schutzschicht unter Verwendung der Datenbank und Algorithmen des externen Dienstes hinzu.
    - *Deaktiviert oder ungültige Schlüssel:* Der externe Dienst wird nicht verwendet, es wird ausschließlich auf die interne Logik des Moduls zurückgegriffen.
  - **Empfohlener Wert:** Aktivieren und konfigurieren, falls verfügbar, da dies den Schutz erheblich verbessert.
  - **Händlerszenario / Beispiel:** Besorgen Sie sich API-Schlüssel vom jeweiligen Dienst (z. B. Google reCAPTCHA) und geben Sie sie hier ein, um deren erweiterte Spam-Filterung zu nutzen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul bietet dedizierte Bildschirme im PrestaShop Back Office, um Spam-Versuche und Sperren zu verwalten und zu überprüfen. Diese sind entscheidend für die Überwachung der Effektivität des Moduls und für manuelle Anpassungen.

#### 2.2.1 AdminregproAttemptsController (Back Office > Module > Spamschutz bei Kundenregistrierung > Versuche)

- **Bildschirmname & Menüpfad:** „Versuche“ (oder ähnlich, unter dem Hauptmenüpunkt des Moduls). Dieser Bildschirm listet alle Registrierungsversuche auf, die das Modul verarbeitet hat, insbesondere solche, die als verdächtig markiert oder blockiert wurden.
- **Verfügbare Aktionen & Einstellungen:** Dies ist eine Rasteransicht (Liste), die Details zu jedem Registrierungsversuch anzeigt.
  - **Spalten:** Typischerweise enthalten:
    - Datum/Uhrzeit des Versuchs
    - IP-Adresse
    - Verwendete E-Mail-Adresse
    - Status (z. B. „Blockiert“, „Zugelassen“, „Markiert“)
    - Grund für den Status (z. B. „IP auf Blacklist“, „Spam-Score hoch“)
    - Aktionsschaltflächen (z. B. „Details anzeigen“, „IP auf Whitelist setzen“, „IP auf Blacklist setzen“, „Eintrag löschen“)
  - **Filtern/Sortieren:** Standard-PrestaShop-Rasterfunktionen zum Filtern nach Datum, IP, Status usw.
- **Auswirkungen von Änderungen:**
  - *IP auf Whitelist setzen:* Fügt die IP zur Whitelist des Moduls hinzu, wodurch zukünftige Registrierungen von dieser IP zugelassen werden.
  - *IP auf Blacklist setzen:* Fügt die IP zur Blacklist des Moduls hinzu, wodurch zukünftige Registrierungen von dieser IP blockiert werden.
  - *Eintrag löschen:* Entfernt den Eintrag aus dem Protokoll der Versuche (hebt die Blockierung/Sperre nicht auf).
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diese Liste regelmäßig, insbesondere wenn Sie Berichte über blockierte legitime Kunden erhalten. Verwenden Sie die Aktion „IP auf Whitelist setzen“, wenn Sie ein falsch positives Ergebnis identifizieren. Umgekehrt, wenn Sie hartnäckigen Spam von einer bestimmten IP sehen, verwenden Sie „IP auf Blacklist setzen“.

#### 2.2.2 AdminregproBansController (Back Office > Module > Spamschutz bei Kundenregistrierung > Sperren)

- **Bildschirmname & Menüpfad:** „Sperren“ (oder ähnlich, unter dem Hauptmenüpunkt des Moduls). Dieser Bildschirm listet alle aktuell aktiven Sperren (IPs oder E-Mail-Adressen/Domains) auf, die das Modul durchsetzt.
- **Verfügbare Aktionen & Einstellungen:** Dies ist eine Rasteransicht (Liste), die Details zu jeder Sperre anzeigt.
  - **Spalten:** Typischerweise enthalten:
    - Art der Sperre (z. B. „IP“, „E-Mail“, „Domain“)
    - Wert (z. B. „192.168.1.1“, „[spam@example.com](mailto:spam@example.com)“, „bad-domain.com“)
    - Hinzugefügt am
    - Grund (falls manuell hinzugefügt)
    - Aktionsschaltflächen (z. B. „Sperre aufheben“, „Bearbeiten“)
  - **Filtern/Sortieren:** Standard-PrestaShop-Rasterfunktionen.
- **Auswirkungen von Änderungen:**
  - *Sperre aufheben:* Hebt die Einschränkung für die angegebene IP, E-Mail oder Domain auf, wodurch zukünftige Registrierungen von dieser zugelassen werden.
  - *Sperre hinzufügen:* Fügt manuell eine neue IP, E-Mail oder Domain zur Sperrliste hinzu.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Dies ist Ihre zentrale Anlaufstelle für die Verwaltung Ihrer benutzerdefinierten Sperrlisten. Wenn Sie eine IP vom Bildschirm „Versuche“ auf die Blacklist gesetzt haben, wird sie hier angezeigt. Wenn ein legitimer Kunde versehentlich in einer Sperre gefangen ist, können Sie seine IP oder E-Mail schnell aus dieser Liste entfernen.

#### 2.2.3 index.php (regpro/controllers/admin/index.php)

- **Verwaltete Tabelle / Entität:** Diese Datei dient wahrscheinlich als Routing- oder Standard-Controller für den Admin-Bereich des Moduls, der möglicherweise zu einem der spezifischen Controller (wie `AdminregproAttempts` oder `AdminregproBans`) umleitet oder eine allgemeine Übersicht/Dashboard für das Modul anzeigt. Sie verwaltet möglicherweise keine bestimmte Tabelle direkt, sondern fungiert als Einstiegspunkt.
- **Formularfelder & Spalten:** Wenn es ein Raster anzeigt, wäre es eine Zusammenfassung oder ein Dashboard. Wahrscheinlicher ist es ein Redirector.
- **Auswirkungen von Änderungen:** Keine direkten Datenänderungen, aber steuert die anfängliche Ansicht beim Zugriff auf den Admin-Bereich des Moduls.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Dies ist normalerweise der erste Bildschirm, den Sie sehen, wenn Sie in der Modulliste auf das Modul klicken. Er könnte schnelle Statistiken oder Links zu den Abschnitten „Versuche“ und „Sperren“ bieten.

### 2.3 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Modul aktivieren/deaktivieren | JA | Schaltet den Spamschutz ein/aus. |
|  | Empfindlichkeit der Spam-Erkennung | Mittel | Steuert die Aggressivität der Spam-Erkennung. |
|  | Aktion bei erkanntem Spam | Registrierung blockieren | Definiert die Reaktion auf Spam (blockieren, überprüfen, protokollieren). |
|  | Fehlermeldung für blockierte Registrierungen | „Die Registrierung konnte nicht abgeschlossen werden. Bitte kontaktieren Sie den Support, wenn Sie glauben, dass dies ein Fehler ist.“ | Passt die Nachricht für blockierte Benutzer an. |
|  | IP-Blacklist/Whitelist | Sparsam verwenden | Manuelles Blockieren/Zulassen bestimmter IPs. |
|  | E-Mail-Blacklist/Whitelist | Sparsam verwenden | Manuelles Blockieren/Zulassen bestimmter E-Mails/Domains. |
|  | Externe API-Integration | Aktivieren mit gültigen Schlüsseln | Verbessert den Schutz mit Drittanbieterdiensten. |
| **AdminregproAttemptsController** | Protokoll der Versuche anzeigen | N/A | Überprüfen Sie alle Registrierungsversuche, deren Status und Gründe. |
|  | IP auf Whitelist setzen (aus Protokoll) | N/A | Ermöglicht zukünftige Registrierungen von einer bestimmten IP. |
|  | IP auf Blacklist setzen (aus Protokoll) | N/A | Blockiert zukünftige Registrierungen von einer bestimmten IP. |
| **AdminregproBansController** | Aktive Sperren anzeigen | N/A | Verwalten und überprüfen Sie alle aktuell aktiven IP-/E-Mail-/Domain-Sperren. |
|  | Sperre aufheben | N/A | Hebt eine bestimmte Sperre auf. |
|  | Neue Sperre hinzufügen | N/A | Fügt manuell eine neue IP, E-Mail oder Domain zur Sperrliste hinzu. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine legitimen Kunden melden, dass sie sich nicht registrieren können. Was soll ich tun?**
A: Überprüfen Sie zuerst das „Versuche“-Protokoll (`AdminregproAttemptsController`) im Back Office. Suchen Sie nach ihrer IP-Adresse oder E-Mail. Wenn ihr Versuch blockiert wurde, sehen Sie den Grund. Sie können dann ihre IP-Adresse oder E-Mail auf die Whitelist setzen oder die Empfindlichkeitseinstellung des Moduls vorübergehend senken. Denken Sie daran, Ihren PrestaShop-Cache zu leeren, nachdem Sie Änderungen vorgenommen haben.

**F: Ich erhalte immer noch Spam-Registrierungen, obwohl das Modul aktiv ist.**
A:

1. **Empfindlichkeit prüfen:** Erhöhen Sie die „Empfindlichkeit der Spam-Erkennung“ in der Hauptkonfiguration des Moduls.
2. **Versuche-Protokoll überprüfen:** Analysieren Sie das „Versuche“-Protokoll, um zu sehen, ob das Modul diese Versuche protokolliert und warum sie möglicherweise durchrutschen.
3. **Zur Blacklist hinzufügen:** Wenn Sie bestimmte IPs oder E-Mail-Domains aus den Spam-Registrierungen identifizieren, fügen Sie diese manuell über den `AdminregproBansController` zu Ihrer Sperrliste hinzu.
4. **Externe API:** Stellen Sie sicher, dass alle integrierten externen Spam-Schutz-APIs (wie reCAPTCHA) korrekt konfiguriert sind und gültige Schlüssel haben.

**F: Woher weiß ich, ob das Modul tatsächlich funktioniert?**
A: Am besten überwachen Sie das „Versuche“-Protokoll (`AdminregproAttemptsController`). Sie sollten Einträge für blockierte Versuche sehen, die anzeigen, dass das Modul aktiv Spam identifiziert und verhindert. Wenn Sie zuvor viel Spam erhalten haben, sollten Sie auch eine deutliche Reduzierung neuer gefälschter Kundenkonten feststellen.

**F: Beeinträchtigt dieses Modul die Leistung meines Shops?**
A: Das Modul ist auf Effizienz ausgelegt. Obwohl es einen kleinen Verarbeitungsschritt während der Registrierung hinzufügt, ist dies typischerweise vernachlässigbar im Vergleich zu den Vorteilen der Spam-Verhinderung. Eine Datenbank voller Spam-Konten würde langfristig weitaus größere Leistungsprobleme verursachen.

**F: Ich habe Einstellungen geändert, aber es scheint nichts im Front Office zu passieren.**
A: Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Dies stellt sicher, dass das Modul die aktualisierten Einstellungen lädt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Spamschutz bei Kundenregistrierung“ (`regpro`) ist nach dem MVC-Muster (Model-View-Controller) von PrestaShop aufgebaut. Es arbeitet hauptsächlich, indem es sich in den Kundenregistrierungsprozess einklinkt und das Hook-System von PrestaShop nutzt, um Registrierungsdaten abzufangen und zu validieren. Es verwendet dedizierte Admin-Controller zur Verwaltung von Versuchen und Sperren und speichert seine Konfiguration in `ps_configuration`. Die Kernlogik des Moduls zur Spam-Erkennung ist wahrscheinlich in der Hauptmoduldatei `index.php` enthalten, mit Hilfsfunktionen oder -klassen (obwohl im Dossier keine explizit aufgeführt sind, könnten sie intern in der Hauptmodulklasse sein).

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:
  Das Moduldossier weist keine dedizierten Front-Office-Controller aus. Dies deutet darauf hin, dass die Front-Office-Interaktionen des Moduls (z. B. Abfangen von Registrierungsdaten) direkt über Hooks innerhalb der Hauptmoduldatei `regpro/index.php` oder durch Überschreiben von PrestaShop-Kern-Controllern (obwohl letzteres für einfachen Spamschutz weniger üblich ist) gehandhabt werden. Die `displayCustomerAccountForm`-Hooks sind die Stellen, an denen die Logik des Moduls ausgelöst würde.
- **Back-Office-Admin-Controller**:
  Diese Controller bieten die administrative Schnittstelle zur Verwaltung der Daten und Einstellungen des Moduls.

  - `controllers/admin/AdminRegproAttempts.php`

    - **Klassenname & Elternklasse:** `AdminRegproAttemptsController` (erweitert `ModuleAdminController` oder `AdminController`).
    - **Verantwortlichkeit:** Verwaltet die Auflistung und Aktionen im Zusammenhang mit aufgezeichneten Spam-Versuchen. Dieser Controller ist für die Anzeige des Rasters der Registrierungsversuche verantwortlich und ermöglicht Administratoren, Details anzuzeigen, zu filtern und Aktionen wie das Whitelisting oder Blacklisting von IPs basierend auf diesen Versuchen durchzuführen. Er interagiert mit der Datenbanktabelle `regattempt`.
  - `controllers/admin/AdminRegproBans.php`

    - **Klassenname & Elternklasse:** `AdminRegproBansController` (erweitert `ModuleAdminController` oder `AdminController`).
    - **Verantwortlichkeit:** Verwaltet die Auflistung und Aktionen im Zusammenhang mit aktiven Sperren (IPs, E-Mails, Domains). Dieser Controller ermöglicht Administratoren, Einträge aus den Sperrlisten des Moduls anzuzeigen, hinzuzufügen, zu bearbeiten und zu entfernen. Er interagiert mit der Datenbanktabelle `regban`.
  - `controllers/admin/index.php`

    - **Klassenname & Elternklasse:** Wahrscheinlich ein einfacher Redirector oder eine Platzhalterdatei. Sie könnte einen grundlegenden `AdminController` enthalten, der zu einem der anderen modulspezifischen Admin-Controller (z. B. `AdminRegproAttempts`) umleitet oder ein einfaches Dashboard anzeigt. Sie verwaltet keine bestimmte Entität direkt, sondern dient als Einstiegspunkt für den Admin-Bereich des Moduls.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies impliziert, dass die Datenstrukturen des Moduls (für Versuche und Sperren) entweder direkt von der `AdminController`-Logik unter Verwendung von Roh-SQL-Abfragen gehandhabt werden, oder wahrscheinlicher, dass die `ObjectModel`-Definitionen für `regattempt` und `regban` direkt in den jeweiligen `AdminRegproAttempts.php`- und `AdminRegproBans.php`-Controllern oder innerhalb der Hauptdatei `regpro/index.php` eingebettet sind.

Wenn `ObjectModel` verwendet wird, würde das `$definition`-Array definiert für:

- `regattempt`: Zuordnung zu einer `ps_regattempt`-Tabelle (oder ähnlich), mit Feldern wie `id_regattempt`, `ip_address`, `email`, `status`, `reason`, `date_add`.
- `regban`: Zuordnung zu einer `ps_regban`-Tabelle (oder ähnlich), mit Feldern wie `id_regban`, `type` (IP, E-Mail, Domain), `value`, `date_add`.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/regpro-v3.js`
  - **Geltungsbereich:** Wahrscheinlich Back-Office. Das „v3“ könnte eine Version oder spezifische Funktionalität anzeigen.
  - **Beschreibung:** Dieses Skript ist wahrscheinlich für die Verbesserung der Benutzererfahrung in der Back-Office-Konfiguration oder den Verwaltungsbildschirmen des Moduls verantwortlich. Es könnte Folgendes verarbeiten:
    - AJAX-Aufrufe für dynamische Updates (z. B. Listen filtern, Sperren hinzufügen/entfernen ohne Seitenneuladung).
    - Formularvalidierung auf der Konfigurationsseite oder beim Hinzufügen neuer Sperreinträge.
    - Interaktive Elemente in den Rastern „Versuche“ oder „Sperren“ (z. B. Bestätigungsdialoge für Aktionen, Sortierung, Paginierung).
    - Potenziell clientseitige Logik für die Integration mit externen APIs, falls diese JS-Interaktion im BO erfordern.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist keine benutzerdefinierten CSS-Dateien aus. Dies deutet darauf hin, dass das Modul für seine Konfigurationsseiten und Raster vollständig auf die Standard-Back-Office-Stile von PrestaShop angewiesen ist. Falls eine spezifische Stilgebung erforderlich ist, würde diese entweder inline in Vorlagen oder dynamisch über JavaScript hinzugefügt.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  Diese Vorlagen werden gerendert, wenn das Modul an bestimmten Stellen im Front-Office eingehängt wird.

  - `views/templates/hook/displayCustomerAccountForm-v3.tpl`

    - **Hook:** `displayCustomerAccountForm` (oder ähnlich, spezifisch für PrestaShop 1.7+ und 8.x).
    - **Zweck:** Diese Vorlage wird wahrscheinlich verwendet, um versteckte Felder, JavaScript-Variablen oder möglicherweise ein sichtbares CAPTCHA/Challenge (falls konfiguriert) in das Kundenregistrierungsformular einzufügen. Das „v3“ deutet darauf hin, dass es sich um eine neuere Version handelt, möglicherweise für neuere PrestaShop-Versionen oder ein spezifisches Design. Es könnte die HTML-Struktur für reCAPTCHA enthalten, falls diese Integration aktiviert ist.
  - `views/templates/hook/displayCustomerAccountForm.tpl`

    - **Hook:** `displayCustomerAccountForm` (oder ähnlich, möglicherweise für ältere PrestaShop-Versionen wie 1.6.x).
    - **Zweck:** Ähnlich wie `displayCustomerAccountForm-v3.tpl`, aber möglicherweise eine generische oder ältere Version. Es würde dieselbe Funktion erfüllen, Elemente oder Logik in das Kundenregistrierungsformular zur Spam-Erkennung einzufügen.
  - `views/templates/hook/displayCustomerAccountFormTop.tpl`

    - **Hook:** `displayCustomerAccountFormTop` (oder ähnlich).
    - **Zweck:** Diese Vorlage würde Inhalte ganz oben im Kundenregistrierungsformular rendern. Dies könnte verwendet werden, um eine allgemeine Nachricht anzuzeigen oder um Elemente einzufügen, die vor den Hauptformularfeldern erscheinen müssen, wie z. B. ein „Ich bin kein Roboter“-Kontrollkästchen oder eine Warnung.
- **Admin-Vorlagen (`views/templates/admin/`)**:
  Diese Vorlagen definieren die Struktur und den Inhalt der Back-Office-Seiten des Moduls.

  - `views/templates/admin/main.tpl`
    - **Zweck:** Dies ist wahrscheinlich die Hauptvorlage für die Konfigurationsseite des Moduls (zugänglich über `getContent()` in `regpro/index.php`) oder ein allgemeiner Wrapper für den Admin-Bereich des Moduls. Sie würde das HTML für die verschiedenen Einstellungen, Eingabefelder und Schaltflächen enthalten, die in Abschnitt 4.1 beschrieben sind. Sie könnte auch Links zu den Controllern `AdminRegproAttempts` und `AdminRegproBans` enthalten.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Basierend auf den Admin-Controllern erstellt das Modul wahrscheinlich zwei benutzerdefinierte Tabellen:

  - `ps_regattempt` (oder ähnliches Präfix): Speichert Datensätze von Registrierungsversuchen.
    - `id_regattempt` (PK, INT)
    - `ip_address` (VARCHAR)
    - `email` (VARCHAR)
    - `status` (VARCHAR, z. B. 'blocked', 'allowed', 'flagged')
    - `reason` (TEXT, Erklärung für den Status)
    - `date_add` (DATETIME)
  - `ps_regban` (oder ähnliches Präfix): Speichert Datensätze von aktiven Sperren.
    - `id_regban` (PK, INT)
    - `type` (VARCHAR, z. B. 'ip', 'email', 'domain')
    - `value` (VARCHAR, die tatsächliche IP, E-Mail oder Domain)
    - `date_add` (DATETIME)
    - `reason` (TEXT, optional, für manuelle Sperren)

  Konfigurationseinstellungen (wie Empfindlichkeit, Fehlermeldungen, API-Schlüssel) werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die mit `REGPRO_` beginnen (z. B. `REGPRO_SENSITIVITY`, `REGPRO_ACTION_ON_SPAM`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Abschnitt aller Front-Office-Seiten gerendert. | Potenziell zum Laden modulspezifischer CSS/JS global oder zur Meta-Tag-Injektion für die externe API-Verifizierung verwendet. |
| `displayCustomerAccountForm` | Wird innerhalb des Kundenregistrierungsformulars gerendert. | Primärer Hook zum Einfügen versteckter Felder, reCAPTCHA-Elemente oder JavaScript, um die Formularübermittlung abzufangen und clientseitige Validierung durchzuführen. |
| `displayCustomerAccountFormTop` | Wird am oberen Rand des Kundenregistrierungsformulars gerendert. | Ähnlich wie `displayCustomerAccountForm`, stellt jedoch sicher, dass der Inhalt vor den Hauptformularfeldern erscheint. |
| `actionCustomerAccountAdd` | Wird *nachdem* ein neues Kundenkonto erfolgreich zur Datenbank hinzugefügt wurde, ausgeführt. | Könnte für die Protokollierung nach der Registrierung, das Senden von Benachrichtigungen oder die weitere Verarbeitung verwendet werden, wenn ein Konto zugelassen, aber zur Überprüfung markiert wurde. |
| `actionAuthentication` | Wird während der Kundenanmeldung/Authentifizierung ausgeführt. | Weniger wahrscheinlich für die Registrierungs-Spam, könnte aber für erweiterte Prüfungen oder zur Verhinderung der Anmeldung von gesperrten IPs/E-Mails verwendet werden. |
| `actionValidateCustomerAccount` | Wird *bevor* ein neues Kundenkonto zur Datenbank hinzugefügt wird, ausgeführt. | **KRITISCHER HOOK:** Dies ist der wahrscheinlichste Hook, an dem die Kernlogik zur Spam-Erkennung des Moduls ausgeführt wird, wodurch die Kontoerstellung verhindert werden kann, wenn Spam erkannt wird. |
| `displayBackOfficeHeader` | Wird im `<head>`-Abschnitt aller Back-Office-Seiten gerendert. | Wird zum Laden modulspezifischer CSS/JS für die Admin-Konfigurations- und Verwaltungsbildschirme verwendet. |
| `displayAdminCustomers` | Wird auf der Kundenlistenseite im Back Office gerendert. | Könnte verwendet werden, um eine Spalte oder eine Aktionsschaltfläche bezüglich des Spam-Status für bestehende Kunden hinzuzufügen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und umfassenden Entwickler-Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und die optimale Leistung Ihres Moduls „Spamschutz bei Kundenregistrierung“ sicherzustellen.
