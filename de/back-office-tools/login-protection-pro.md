---
title: "Login protection pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Login protection pro“ von MyPresta.eu."
sidebar:
  label: "Login protection pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Login protection pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/login-protection-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/login-protection-pro/)
>
> ---


# Login protection pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die Kernregeln für den Anmeldeschutz definieren.

- **Menüpfad:** Back Office > Module > Modul-Manager > Login protection pro > Konfigurieren

#### Einstellungen & Optionen:

1. **Anmeldeschutz aktivieren:**

   - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Er schaltet das gesamte Anmeldeschutzsystem ein oder aus.
   - **Auswirkungen einer Änderung dieser Einstellung:**
     - *Wenn aktiviert:* Das Modul beginnt, Anmeldeversuche zu überwachen und die unten festgelegten Regeln anzuwenden.
     - *Wenn deaktiviert:* Das Modul ist inaktiv, und es werden keine Anmeldeversuche überwacht oder blockiert. Ihr Shop verlässt sich auf die Standard-Sicherheit von PrestaShop, die keinen Brute-Force-Schutz beinhaltet.
   - **Empfohlener Wert:** **JA**
   - **Händlerszenario / Beispiel:** Lassen Sie dies immer aktiviert, um sicherzustellen, dass Ihr Shop geschützt ist. Deaktivieren Sie es nur für spezifisches Debugging, wenn dies vom Support angewiesen wird.
2. **Max. fehlgeschlagene Versuche:**

   - **Was diese Einstellung bewirkt:** Definiert die maximale Anzahl von falschen Anmeldeversuchen, die von einer einzelnen IP-Adresse innerhalb eines bestimmten Zeitraums (definiert durch „Zeitfenster für Versuche“) zugelassen werden, bevor diese IP vorübergehend blockiert wird.
   - **Auswirkungen einer Änderung dieser Einstellung:**
     - *Einstellung einer niedrigeren Zahl (z. B. 3):* Macht den Schutz aggressiver und blockiert verdächtige IPs schneller. Dies könnte versehentlich legitime Benutzer blockieren, die ihr Passwort mehrmals vergessen.
     - *Einstellung einer höheren Zahl (z. B. 10):* Macht den Schutz weniger aggressiv und erlaubt mehr fehlgeschlagene Versuche. Dies reduziert die Wahrscheinlichkeit, legitime Benutzer zu blockieren, gibt Hackern aber mehr Versuche.
   - **Empfohlener Wert:** **5**
   - **Händlerszenario / Beispiel:** Wenn Sie bemerken, dass viele legitime Kunden blockiert werden, könnten Sie diesen Wert erhöhen. Wenn Sie viele Brute-Force-Angriffe in Ihren Protokollen sehen, könnten Sie ihn verringern. 5 ist ein guter Kompromiss.
3. **Zeitfenster für Versuche (Minuten):**

   - **Was diese Einstellung bewirkt:** Gibt die Dauer (in Minuten) an, während der die Zählung der „Max. fehlgeschlagenen Versuche“ aktiv ist. Wenn eine IP innerhalb dieses Fensters `Max. fehlgeschlagene Versuche` erreicht, wird sie blockiert. Nach diesem Fenster wird die Zählung zurückgesetzt.
   - **Auswirkungen einer Änderung dieser Einstellung:**
     - *Einstellung eines kürzeren Fensters (z. B. 5 Minuten):* Eine IP muss die `Max. fehlgeschlagenen Versuche` sehr schnell erreichen, um blockiert zu werden. Dies ist gut für schnelle Brute-Force-Angriffe.
     - *Einstellung eines längeren Fensters (z. B. 60 Minuten):* Eine IP kann `Max. fehlgeschlagene Versuche` über einen längeren Zeitraum erreichen, um blockiert zu werden. Dies fängt langsamere, verteiltere Angriffe ab, könnte aber auch legitime Benutzer blockieren, die versuchen, sich anzumelden, abgelenkt werden und es später erneut versuchen.
   - **Empfohlener Wert:** **15**
   - **Händlerszenario / Beispiel:** Ein 15-Minuten-Fenster ist in der Regel ausreichend, um automatisierte Angriffe abzufangen, ohne einen menschlichen Benutzer, der sich möglicherweise über ein paar Minuten an sein Passwort zu erinnern versucht, unangemessen zu bestrafen.
4. **Sperrdauer (Minuten):**

   - **Was diese Einstellung bewirkt:** Bestimmt, wie lange eine IP-Adresse blockiert bleibt, sobald sie die `Max. fehlgeschlagenen Versuche` innerhalb des `Zeitfensters für Versuche` überschreitet.
   - **Auswirkungen einer Änderung dieser Einstellung:**
     - *Einstellung einer kürzeren Dauer (z. B. 30 Minuten):* Die IP wird früher entsperrt. Dies ist weniger störend für legitime Benutzer, die versehentlich blockiert wurden, gibt Hackern aber eine schnellere Wiederholungsmöglichkeit.
     - *Einstellung einer längeren Dauer (z. B. 1440 Minuten = 24 Stunden):* Die IP bleibt für einen längeren Zeitraum blockiert. Dies ist sehr effektiv gegen automatisierte Angriffe, kann aber für legitime Benutzer, die blockiert sind, frustrierend sein.
   - **Empfohlener Wert:** **60** (1 Stunde)
   - **Händlerszenario / Beispiel:** Eine 60-minütige Sperre ist in der Regel ausreichend, um automatisierte Bots abzuschrecken, da diese wahrscheinlich weiterziehen werden. Für einen Menschen bietet sie eine angemessene Abkühlphase.
5. **Admin-Login schützen:**

   - **Was diese Einstellung bewirkt:** Dieser Schalter wendet die Anmeldeschutzregeln speziell auf die Anmeldeseite des PrestaShop Back Office (Admin-Panel) an.
   - **Auswirkungen einer Änderung dieser Einstellung:**
     - *Wenn aktiviert:* Ihre Admin-Anmeldeseite ist geschützt. Wenn ein Angreifer versucht, Ihr Admin-Passwort zu oft zu erraten, wird seine IP blockiert.
     - *Wenn deaktiviert:* Nur Kunden-Anmeldeversuche werden überwacht. Ihre Admin-Anmeldeseite bleibt anfällig für Brute-Force-Angriffe.
   - **Empfohlener Wert:** **JA**
   - **Händlerszenario / Beispiel:** Es ist absolut entscheidend, Ihr Admin-Login zu schützen, da ein unbefugter Zugriff hier Ihren gesamten Shop gefährden kann. Lassen Sie dies immer aktiviert.
6. **Kunden-Login schützen:**

   - **Was diese Einstellung bewirkt:** Dieser Schalter wendet die Anmeldeschutzregeln speziell auf die Kunden-Anmeldeseite (Front Office) an.
   - **Auswirkungen einer Änderung dieser Einstellung:**
     - *Wenn aktiviert:* Kunden-Anmeldeversuche sind geschützt. Wenn ein Angreifer versucht, Kundenpasswörter zu erraten, wird seine IP blockiert.
     - *Wenn deaktiviert:* Nur Admin-Anmeldeversuche werden überwacht. Kundenkonten bleiben anfällig für Brute-Force-Angriffe.
   - **Empfohlener Wert:** **JA**
   - **Händlerszenario / Beispiel:** Der Schutz von Kundenkonten ist für die Datensicherheit und die Aufrechterhaltung des Kundenvertrauens von entscheidender Bedeutung. Lassen Sie dies immer aktiviert.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Anmeldeschutz aktivieren | JA | Hauptschalter für die Modulfunktionalität. **Immer JA.** |
| Modulkonfiguration | Max. fehlgeschlagene Versuche | 5 | Anzahl der falschen Anmeldungen, bevor eine IP blockiert wird. |
| Modulkonfiguration | Zeitfenster für Versuche (Minuten) | 15 | Dauer, über die fehlgeschlagene Versuche gezählt werden. |
| Modulkonfiguration | Sperrdauer (Minuten) | 60 | Wie lange eine blockierte IP gesperrt bleibt. |
| Modulkonfiguration | Admin-Login schützen | JA | Wendet den Schutz auf das Back Office-Login an. **Immer JA.** |
| Modulkonfiguration | Kunden-Login schützen | JA | Wendet den Schutz auf das Front Office-Kunden-Login an. **Immer JA.** |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul bietet zwei dedizierte Bildschirme in Ihrem PrestaShop Back Office, um Anmeldeversuche und Sperren zu verwalten und zu überprüfen.

#### 2.2.1 AdminLproAttemptsController: Protokoll der Anmeldeversuche

Dieser Bildschirm ermöglicht es Ihnen, ein detailliertes Protokoll aller vom Modul erfassten fehlgeschlagenen Anmeldeversuche anzuzeigen.

- **Bildschirmname & Menüpfad:** Back Office > Module > Login Protection Pro > **Anmeldeversuche** (oder ähnlich, je nach PrestaShop-Version und Menüanpassung).
- **Verfügbare Aktionen & Einstellungen:**
  - **Listentabelle:** Sie sehen eine Tabelle mit folgenden Informationen:
    - **IP-Adresse:** Die IP-Adresse, von der der fehlgeschlagene Versuch ausging.
    - **Versuchszeit:** Das genaue Datum und die Uhrzeit des fehlgeschlagenen Versuchs.
    - **Login-Typ:** Ob es sich um einen „Admin“- oder „Kunden“-Anmeldeversuch handelte.
    - **Benutzername/E-Mail:** Der Benutzername oder die E-Mail-Adresse, die versucht wurde.
    - **Status:** Zeigt an, ob der Versuch zu einer Sperre führte oder nur ein fehlgeschlagener Versuch war.
  - **Filtern & Sortieren:** Sie können normalerweise nach IP-Adresse, Login-Typ oder Datumsbereich filtern, um spezifische Versuche zu finden.
  - **Keine direkten Aktionen:** Dieser Bildschirm dient hauptsächlich der Überwachung und Überprüfung. Sie können IPs von hier aus nicht direkt sperren oder entsperren, aber er hilft Ihnen, verdächtige Muster zu erkennen.
- **Auswirkungen von Änderungen:** Das Anzeigen dieses Protokolls hilft Ihnen, die Häufigkeit und Quelle von Angriffen zu verstehen. Wenn Sie bemerken, dass eine bestimmte IP-Adresse viele Versuche unternimmt, können Sie diese manuell über den Bildschirm „Gesperrte IPs“ zur Sperrliste hinzufügen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie dieses Protokoll regelmäßig, insbesondere wenn Sie einen Angriff vermuten oder Kunden Probleme beim Anmelden melden. Suchen Sie nach Mustern wiederholter fehlgeschlagener Versuche von derselben IP oder demselben IP-Bereich.

#### 2.2.2 AdminLproBansController: Verwaltung gesperrter IPs

Dieser Bildschirm ermöglicht es Ihnen, IP-Adressen in der Sperrliste des Moduls anzuzeigen, hinzuzufügen und zu entfernen.

- **Bildschirmname & Menüpfad:** Back Office > Module > Login Protection Pro > **Gesperrte IPs** (oder ähnlich, je nach PrestaShop-Version und Menüanpassung).
- **Verfügbare Aktionen & Einstellungen:**
  - **Listentabelle:** Zeigt alle aktuell gesperrten IP-Adressen an, einschließlich:
    - **IP-Adresse:** Die blockierte IP.
    - **Sperrgrund:** (Falls zutreffend, z. B. „Automatische Sperre aufgrund fehlgeschlagener Versuche“).
    - **Sperrbeginn:** Wann die Sperre initiiert wurde.
    - **Sperrende:** Wann die Sperre voraussichtlich abläuft (falls temporär).
    - **Aktionen:** Enthält normalerweise eine Option zum „Löschen“ oder „Entsperren“ einer bestimmten IP.
  - **Schaltfläche „Neue IP hinzufügen“:** Ermöglicht Ihnen, eine IP-Adresse manuell zur Sperrliste hinzuzufügen. Dies ist nützlich, wenn Sie eine böswillige IP aus Ihren Serverprotokollen oder dem Bildschirm „Anmeldeversuche“ identifizieren, die noch nicht automatisch gesperrt wurde.
    - Beim Hinzufügen können Sie möglicherweise die IP, einen Grund und eine optionale Ablaufzeit für die Sperre angeben.
- **Auswirkungen von Änderungen:**
  - *Hinzufügen einer IP:* Blockiert sofort alle Anmeldeversuche von dieser IP-Adresse für die angegebene Dauer (oder dauerhaft, wenn keine Dauer festgelegt ist).
  - *Entfernen einer IP:* Entsperrt die IP-Adresse und erlaubt wieder Anmeldeversuche von dieser. Gehen Sie hierbei vorsichtig vor, um sicherzustellen, dass Sie keinen bekannten Angreifer entsperren.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - Überprüfen Sie diese Liste regelmäßig.
  - Wenn ein legitimer Kunde meldet, dass er sich nicht anmelden kann, und Sie seine IP-Adresse bestätigt haben (z. B. indem Sie ihn bitten, eine „was ist meine IP“-Seite zu besuchen), können Sie seine IP hier vorübergehend entsperren.
  - Wenn Sie eine hartnäckige Bedrohung identifizieren, können Sie deren IP manuell hinzufügen, um sicherzustellen, dass sie blockiert bleibt.

#### 2.2.3 index.php (lpro/controllers/admin/index.php)

Diese Datei dient typischerweise als Platzhalter oder Weiterleitung innerhalb des Admin-Controller-Verzeichnisses. In PrestaShop verhindern `index.php`-Dateien in Controller-Verzeichnissen oft die direkte Verzeichnisauflistung oder fungieren als Standard-Einstiegspunkt, wenn kein spezifischer Controller angefordert wird. Sie stellt selbst keinen konfigurierbaren Bildschirm oder eine verwaltete Entität dar.

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden beschweren sich, dass sie sich nicht anmelden können, obwohl sie das richtige Passwort verwenden. Was soll ich tun?**
A1: Dies liegt wahrscheinlich daran, dass das Modul ihre IP-Adresse nach zu vielen fehlgeschlagenen Versuchen (vielleicht von einer früheren Sitzung oder einem gemeinsam genutzten Netzwerk) blockiert hat.
1. Bitten Sie den Kunden um seine aktuelle IP-Adresse (er kann sie finden, indem er bei Google nach „was ist meine IP“ sucht).
2. Gehen Sie zu **Back Office > Module > Login Protection Pro > Gesperrte IPs**.
3. Suchen Sie die IP-Adresse des Kunden in der Liste.
4. Wenn gefunden, löschen/entsperren Sie seine IP.
5. Raten Sie dem Kunden, sich erneut anzumelden. Sie könnten ihm auch vorschlagen, sein Passwort zurückzusetzen.

**F2: Ich bin aus meinem eigenen Admin-Panel ausgesperrt! Wie kann ich wieder Zugang erhalten?**
A2: Dies kann passieren, wenn Sie zu viele fehlgeschlagene Versuche unternommen haben.
1. Wenn Sie FTP-Zugang zu Ihrem Shop haben, können Sie das Modul vorübergehend deaktivieren. Gehen Sie zu `modules/lpro/` und benennen Sie die Datei `index.php` um (z. B. in `index.php.bak`). Dies deaktiviert das Modul.
2. Melden Sie sich in Ihrem Admin-Panel an.
3. Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Login protection pro“ und klicken Sie auf „Konfigurieren“.
4. Gehen Sie zu **Gesperrte IPs** und entfernen Sie Ihre IP-Adresse aus der Liste.
5. Benennen Sie `index.php.bak` im Verzeichnis `modules/lpro/` wieder in `index.php` um.
6. Aktivieren Sie das Modul erneut, falls Sie es im Modul-Manager deaktiviert haben.
7. Passen Sie die Einstellungen für `Max. fehlgeschlagene Versuche` oder `Sperrdauer` an, wenn Sie sich häufig ausgesperrt finden.

**F3: Das Modul scheint keine IPs zu blockieren, selbst nach vielen fehlgeschlagenen Versuchen. Was könnte falsch sein?**
A3:
1. **„Anmeldeschutz aktivieren“ überprüfen:** Stellen Sie sicher, dass der Hauptschalter in der Modulkonfiguration auf **JA** steht.
2. **„Admin-Login schützen“ / „Kunden-Login schützen“ überprüfen:** Stellen Sie sicher, dass der entsprechende Schutz (Admin oder Kunde) aktiviert ist.
3. **Einstellungen überprüfen:** Vergewissern Sie sich, dass `Max. fehlgeschlagene Versuche`, `Zeitfenster für Versuche` und `Sperrdauer` auf vernünftige Werte eingestellt sind. Wenn das `Zeitfenster für Versuche` zu kurz oder `Max. fehlgeschlagene Versuche` zu hoch ist, könnte ein sehr aggressiver Angriff erforderlich sein, um eine Sperre auszulösen.
4. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Manchmal werden Moduleinstellungen aufgrund von Caching nicht sofort angewendet.
5. **Server-Logs überprüfen:** Die Server-Zugriffsprotokolle Ihres Hosting-Anbieters könnten zeigen, ob das Modul PHP-Fehler aufweist.

**F4: Wird dieses Modul meinen Shop verlangsamen?**
A4: Das Modul ist so konzipiert, dass es leichtgewichtig ist. Es führt nur Prüfungen bei Anmeldeversuchen durch, die im Vergleich zu Seitenaufrufen relativ selten sind. Die Leistungsauswirkungen sollten vernachlässigbar sein. Wenn Sie eine Verlangsamung bemerken, stellen Sie sicher, dass Ihre PrestaShop-Installation und Ihr Server die Mindestanforderungen erfüllen.

**F5: Wie übersetze ich die Nachrichten des Moduls in andere Sprachen?**
A5: Obwohl dieses Modul hauptsächlich im Hintergrund arbeitet, können alle potenziellen Front-Office-Nachrichten (wie „Zu viele fehlgeschlagene Versuche“) oder Back-Office-Beschriftungen übersetzt werden:
1. Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“.
3. Wählen Sie Ihr Theme.
4. Wählen Sie die Sprache aus, die Sie übersetzen möchten.
5. Suchen Sie das Modul „Login protection pro“ und übersetzen Sie die relevanten Textzeichenfolgen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Moduls „Login protection pro“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul `Login protection pro` folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Admin-Controller für seine Verwaltungsoberfläche und Hooks für seine Kernfunktionalität nutzt. Es führt keine komplexen Front-Office-Controller oder benutzerdefinierten `ObjectModel`-Klassen ein, sondern verlässt sich auf die `Configuration`-Klasse von PrestaShop für Einstellungen und direkte Datenbankinteraktion für die Protokollierung von Versuchen und die Verwaltung von Sperren. Die Logik des Moduls zur Erkennung und Blockierung von Versuchen wird über PrestaShop-Hooks, insbesondere um den Authentifizierungsprozess herum, injiziert.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Das Modul enthält **keine** dedizierten Front-Office-Controller. Die gesamte Front-Office-bezogene Logik (Überwachung von Kunden-Anmeldeversuchen) wird direkt in der Hauptmoduldatei (`lpro/index.php`) durch Einhaken in den PrestaShop-Authentifizierungsprozess behandelt.

#### Back-Office-Admin-Controller

Das Modul bietet dedizierte Admin-Controller zur Verwaltung von Anmeldeversuchen und Sperren.

- **`controllers/admin/AdminLproAttempts.php`**

  - **Klassenname:** `AdminLproAttemptsController` (erweitert `ModuleAdminController`)
  - **Verantwortlichkeit:** Dieser Controller ist für die Anzeige einer Liste aller aufgezeichneten fehlgeschlagenen Anmeldeversuche verantwortlich. Er bietet eine schreibgeschützte Rasteransicht der `lattempt`-Daten, die es Administratoren ermöglicht, verdächtige Aktivitäten zu überwachen. Er verwendet typischerweise `HelperList` zum Rendern der Tabelle.
  - **Verwaltete Entität:** `lattempt` (repräsentiert einen Datensatz eines fehlgeschlagenen Anmeldeversuchs).
  - **Tab-Name:** Anmeldeversuche (sichtbar unter dem Hauptmenüpunkt des Moduls).
- **`controllers/admin/AdminLproBans.php`**

  - **Klassenname:** `AdminLproBansController` (erweitert `ModuleAdminController`)
  - **Verantwortlichkeit:** Dieser Controller verwaltet die Liste der gesperrten IP-Adressen. Er bietet eine Rasteransicht der `lban`-Daten und ermöglicht es Administratoren, neue Sperren hinzuzufügen, bestehende zu bearbeiten und IPs zu löschen (entsperren). Er verwendet wahrscheinlich `HelperList` für die Tabelle und `HelperForm` für Hinzufüge-/Bearbeitungsformulare.
  - **Verwaltete Entität:** `lban` (repräsentiert einen Datensatz einer gesperrten IP-Adresse).
  - **Tab-Name:** Gesperrte IPs (sichtbar unter dem Hauptmenüpunkt des Moduls).
- **`controllers/admin/index.php`**

  - **Genauer Dateipfad:** `lpro/controllers/admin/index.php`
  - **Klassenname & Elternklasse:** Keine Klassendatei.
  - **Verantwortlichkeit:** Dies ist eine Standard-PrestaShop-Platzhalterdatei. Ihr Hauptzweck ist es, die Verzeichnisauflistung zu verhindern, falls die Webserver-Konfiguration dies zulässt, und manchmal kann sie eine einfache Weiterleitung oder eine Sicherheitsprüfung enthalten. Sie enthält keine funktionale Logik für das Modul selbst.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul enthält **keine** benutzerdefinierten Klassen im Verzeichnis `classes/`. Es behandelt Datenbankinteraktionen wahrscheinlich direkt in der Hauptmoduldatei (`lpro/index.php`) oder seinen Admin-Controllern unter Verwendung von Standard-PrestaShop-Datenbankabfragemethoden. Dies impliziert, dass die Entitäten `lattempt` und `lban` ohne dedizierte `ObjectModel`-Klassen verwaltet werden, wobei auf direkte SQL- oder `Db::getInstance()`-Aufrufe zurückgegriffen wird.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Dies deutet darauf hin, dass seine Konfigurations- und Verwaltungsoberflächen vollständig auf den Standard-JavaScript-Bibliotheken und -Verhaltensweisen von PrestaShop basieren (z. B. für Formularübermittlung, Tabellenfilterung).

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält **keine** benutzerdefinierten CSS-Dateien. Dies zeigt an, dass seine Back Office-Oberflächen (Konfiguration, Versuchsprotokolle, Sperrlisten) das Styling direkt vom PrestaShop Back Office-Theme erben, wodurch ein konsistentes Erscheinungsbild ohne Einführung benutzerdefinierter visueller Elemente gewährleistet wird.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - **`lpro/views/templates/admin/main.tpl`**:
    - **Zweck:** Dieses Template wird wahrscheinlich für die Hauptkonfigurationsseite des Moduls verwendet, gerendert durch die Methode `getContent()` in `lpro/index.php`. Es enthält die HTML-Struktur für die in Abschnitt 4.1 beschriebenen Einstellungen (Anmeldeschutz aktivieren, Max. fehlgeschlagene Versuche usw.). Es würde typischerweise Formularelemente (Schalter, Eingabefelder) und möglicherweise Links zu den Controllern `AdminLproAttempts` und `AdminLproBans` enthalten.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt während seiner `install()`-Methode (definiert in `lpro/index.php`) benutzerdefinierte Datenbanktabellen.

- **`ps_lpro_attempt`**:
  - **Zweck:** Speichert Datensätze aller fehlgeschlagenen Anmeldeversuche.
  - **Wahrscheinliche Felder:**
    - `id_lpro_attempt` (Primärschlüssel)
    - `ip_address` (VARCHAR): Die IP-Adresse des fehlgeschlagenen Versuchs.
    - `attempt_time` (DATETIME): Zeitstempel des Versuchs.
    - `login_type` (VARCHAR): „admin“ oder „customer“.
    - `username` (VARCHAR): Der versuchte Benutzername/E-Mail.
    - `is_banned` (TINYINT): Flag, das anzeigt, ob dieser Versuch zu einer Sperre führte.
- **`ps_lpro_ban`**:
  - **Zweck:** Speichert Datensätze der aktuell aktiven IP-Sperren.
  - **Wahrscheinliche Felder:**
    - `id_lpro_ban` (Primärschlüssel)
    - `ip_address` (VARCHAR): Die gesperrte IP-Adresse.
    - `ban_start_time` (DATETIME): Wann die Sperre begann.
    - `ban_end_time` (DATETIME): Wann die Sperre voraussichtlich abläuft (NULL für dauerhafte Sperren).
    - `reason` (TEXT): Optionaler Grund für die Sperre.
    - `is_permanent` (TINYINT): Flag für dauerhafte Sperren.

#### Registrierte Hooks-Tabelle

Das Modul registriert Hooks, um Anmeldeversuche abzufangen und seine Schutzlogik anzuwenden.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAuthentication` | Nach einem Kunden-Anmeldeversuch (Front Office). | Prüft, ob der Kunden-Anmeldeversuch erfolgreich oder fehlgeschlagen war. Bei Fehlschlag wird der Versuch protokolliert und auf Sperrbedingungen geprüft. |
| `actionAdminLoginController` | Nach einem Administrator-Anmeldeversuch (Back Office). | Prüft, ob der Admin-Anmeldeversuch erfolgreich oder fehlgeschlagen war. Bei Fehlschlag wird der Versuch protokolliert und auf Sperrbedingungen geprüft. |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Potenziell zum Einbinden von CSS/JS (obwohl keine vorhanden sind) oder für frühe Prüfungen verwendet, jedoch weniger wahrscheinlich für die Kernlogik. Häufiger für die allgemeine Modulinitialisierung. |
| `displayRightColumn` | In der rechten Spalte der Front-Office-Seiten. | Nicht direkt relevant für die Sicherheitslogik. Falls verwendet, wäre es zur Anzeige einer Nachricht oder eines Blocks, was für dieses Modul unwahrscheinlich ist. |
| `displayLeftColumn` | In der linken Spalte der Front-Office-Seiten. | Gleiches wie `displayRightColumn`. |
| `displayFooter` | Im Footer jeder Front-Office-Seite. | Nicht direkt relevant für die Sicherheitslogik. |
| `displayProductExtraContent` | Auf der Produktseite, im Bereich „zusätzlicher Inhalt“. | Nicht direkt relevant für die Sicherheitslogik. |

**Hinweis zu Hooks:** Die Kernlogik zur Erkennung und Blockierung von Versuchen wird hauptsächlich in den Hooks `actionAuthentication` und `actionAdminLoginController` liegen. Andere `display`-Hooks sind wahrscheinlich standardmäßig registriert, werden aber für die Kernsicherheitsfunktionalität des Moduls nicht aktiv genutzt.

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Login protection pro“ gerne zur Verfügung.
