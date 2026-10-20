---
title: "Cart protection pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Cart protection pro von MyPresta.eu."
sidebar:
  label: "Cart protection pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cart protection pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/cart-protection-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/cart-protection-pro/)
>
> ---


# Cart protection pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel für externe API-Integrationen (wie CleanTalk oder StopForumSpam) erforderlich, falls Sie diese aktivieren möchten. Die meisten modernen Hosting-Umgebungen stellen diese bereits bereit.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist die Hauptsteuerzentrale für „Cart protection pro“, wo Sie definieren, wie das Modul verdächtige Warenkorbaktivitäten erkennt und darauf reagiert.

#### Allgemeine Einstellungen

- **Aktiviert**:

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul überwacht aktiv die Warenkorbaktivität und wendet Ihre gewählten Schutzregeln an.
    - *Wenn deaktiviert:* Das Modul ist inaktiv und schützt Ihren Shop nicht vor gefälschten Warenkorb-Angriffen.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Halten Sie dies immer aktiviert, um sicherzustellen, dass Ihr Shop geschützt ist. Deaktivieren Sie es nur zur Fehlerbehebung oder Wartung.
- **Schutztyp**:

  - **Was diese Einstellung bewirkt:** Bestimmt die Methode, die das Modul verwendet, um verdächtige Aktivitäten zu identifizieren und zu blockieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „IP-Adresse“ eingestellt:* Das Modul verfolgt Warenkorbversuche basierend auf der IP-Adresse des Besuchers. Wenn eine IP die zulässigen Versuche überschreitet, wird sie blockiert.
    - *Wenn auf „Cookie“ eingestellt:* Das Modul verfolgt Warenkorbversuche mithilfe eines Browser-Cookies. Wenn ein Browser (identifiziert durch Cookie) die Versuche überschreitet, wird er blockiert. Dies ist weniger zuverlässig, da Cookies gelöscht werden können.
    - *Wenn auf „IP-Adresse + Cookie“ eingestellt:* Kombiniert beide Methoden für stärkeren Schutz. Eine IP oder ein Cookie, das die Grenzwerte überschreitet, löst eine Blockierung aus.
    - *Wenn auf „CleanTalk“ eingestellt:* Verwendet den externen CleanTalk Anti-Spam-Dienst zur Überprüfung von Anfragen. Erfordert einen CleanTalk API-Schlüssel.
    - *Wenn auf „StopForumSpam“ eingestellt:* Verwendet die externe StopForumSpam-Datenbank, um zu überprüfen, ob eine IP für Spam bekannt ist. Erfordert einen StopForumSpam-Schlüssel.
  - **Empfohlener Wert:** „IP-Adresse + Cookie“ für robusten lokalen Schutz, oder „CleanTalk“ / „StopForumSpam“, wenn Sie Konten bei diesen Diensten für erweiterte externe Prüfungen haben.
  - **Händlerszenario / Beispiel:** Wenn Sie eine große Anzahl gefälschter Warenkörbe erleben, beginnen Sie mit „IP-Adresse + Cookie“. Wenn das Problem weiterhin besteht oder Sie erweiterte Prüfungen wünschen, ziehen Sie die Integration mit CleanTalk oder StopForumSpam in Betracht.
- **Zeitrahmen**:

  - **Was diese Einstellung bewirkt:** Definiert die Dauer (in Minuten), innerhalb derer das Modul Warenkorbversuche von einer einzelnen Quelle (IP oder Cookie) zählt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Ein kürzerer Zeitrahmen (z. B. 5 Minuten):* Aggressiverer Schutz. Ein Benutzer/Bot wird schneller blockiert, wenn er in kurzer Zeit viele Versuche unternimmt.
    - *Ein längerer Zeitrahmen (z. B. 60 Minuten):* Weniger aggressiv. Ermöglicht mehr Versuche über einen längeren Zeitraum, bevor eine Blockierung erfolgt.
  - **Empfohlener Wert:** 10 Minuten
  - **Händlerszenario / Beispiel:** Wenn Bots schnell Warenkörbe erstellen, fängt ein kürzerer Zeitrahmen sie schneller ab. Wenn Sie feststellen, dass legitime Benutzer blockiert werden (selten), können Sie diesen Wert leicht erhöhen.
- **Anzahl der Versuche**:

  - **Was diese Einstellung bewirkt:** Legt die maximale Anzahl von Warenkorb-Hinzufügungen fest, die von einer einzelnen Quelle (IP oder Cookie) innerhalb des definierten „Zeitrahmens“ zulässig sind, bevor eine Blockierung ausgelöst wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Eine niedrigere Zahl (z. B. 3):* Sehr aggressiv. Ein Benutzer/Bot wird bereits nach wenigen Warenkorb-Hinzufügungen blockiert.
    - *Eine höhere Zahl (z. B. 10):* Weniger aggressiv. Ermöglicht mehr Warenkorb-Hinzufügungen vor einer Blockierung.
  - **Empfohlener Wert:** 5
  - **Händlerszenario / Beispiel:** Ein normaler Kunde legt selten mehr als 5 Artikel innerhalb von 10 Minuten in seinen Warenkorb. Bots hingegen versuchen oft, Dutzende oder Hunderte hinzuzufügen. Eine Einstellung auf 5 hilft, dies zu unterscheiden.
- **Titel der E-Mail an den Händler**:

  - **Was diese Einstellung bewirkt:** Legt die Betreffzeile für die E-Mail-Benachrichtigung fest, die an Sie (den Händler) gesendet wird, wenn eine Warenkorb-Schutzsperre auftritt.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Betreffzeile der Warn-E-Mails, die Sie erhalten.
  - **Empfohlener Wert:** „Cart Protection Pro - Sperrwarnung!“
  - **Händlerszenario / Beispiel:** Passen Sie dies an, um die Warnungen in Ihrem Posteingang leicht erkennbar zu machen, z. B. „DRINGEND: Bot blockiert auf [Ihr Shop-Name]“.
- **Protokolle**:

  - **Was diese Einstellung bewirkt:** Steuert, ob das Modul Details zu Warenkorbversuchen und Sperren in Ihrer PrestaShop-Datenbank aufzeichnet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul speichert eine Historie aller Versuche und Sperren, die Sie in den Abschnitten „Versuche“ und „Sperren“ des Moduls überprüfen können. Dies ist entscheidend für die Überwachung und das Verständnis von Angriffen.
    - *Wenn deaktiviert:* Es werden keine Protokolle geführt, was die Verfolgung oder Fehlerbehebung erschwert.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Halten Sie die Protokolle immer aktiviert. Sie liefern wertvolle Einblicke in die Arten und Häufigkeit der Angriffe, denen Ihr Shop ausgesetzt ist, und helfen Ihnen, Ihre Einstellungen zu optimieren.

#### CleanTalk-Integration

- **CleanTalk kostenlosen Support aktivieren**:

  - **Was diese Einstellung bewirkt:** Ermöglicht die Integration mit dem CleanTalk Anti-Spam-Dienst für Echtzeit-Spam-Prüfungen. CleanTalk bietet einen kostenlosen Plan für grundlegende Prüfungen an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul sendet Anfragen an CleanTalk, um zu überprüfen, ob eine IP-Adresse oder E-Mail (falls verfügbar) als Spam bekannt ist, bevor Warenkorb-Hinzufügungen zugelassen werden.
    - *Wenn deaktiviert:* CleanTalk-Prüfungen werden nicht durchgeführt.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben ein CleanTalk-Konto und einen API-Schlüssel)
  - **Händlerszenario / Beispiel:** Wenn Sie CleanTalk bereits für anderen Spamschutz (z. B. Kommentare, Registrierungen) verwenden oder eine zusätzliche Ebene externer Überprüfung wünschen, aktivieren Sie dies.
- **CleanTalk kostenpflichtigen Support aktivieren**:

  - **Was diese Einstellung bewirkt:** Ermöglicht die Integration mit dem CleanTalk Anti-Spam-Dienst, speziell für Funktionen, die mit einem kostenpflichtigen CleanTalk-Abonnement verfügbar sind.
  - **Auswirkung der Änderung dieser Einstellung:** Ähnlich wie beim kostenlosen Support, aber potenziell mit erweiterten Prüfungen, wenn Ihr CleanTalk-Plan dies zulässt.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben ein kostenpflichtiges CleanTalk-Konto und einen API-Schlüssel)
  - **Händlerszenario / Beispiel:** Wählen Sie dies, wenn Sie ein kostenpflichtiges CleanTalk-Abonnement haben und dessen volle Funktionen für den Warenkorbschutz nutzen möchten.
- **CleanTalk API-Schlüssel**:

  - **Was diese Einstellung bewirkt:** Dies ist der eindeutige Schlüssel, der von CleanTalk bereitgestellt wird und Ihren Shop bei deren Dienst authentifiziert.
  - **Auswirkung der Änderung dieser Einstellung:** Ohne einen gültigen API-Schlüssel funktioniert die CleanTalk-Integration nicht, selbst wenn sie aktiviert ist.
  - **Empfohlener Wert:** Ihr tatsächlicher CleanTalk API-Schlüssel (leer lassen, wenn CleanTalk nicht verwendet wird).
  - **Händlerszenario / Beispiel:** Nach der Anmeldung bei CleanTalk erhalten Sie einen API-Schlüssel. Geben Sie ihn hier ein, um deren Dienst zu aktivieren.

#### StopForumSpam-Integration

- **StopForumSpam-Support aktivieren**:

  - **Was diese Einstellung bewirkt:** Ermöglicht die Integration mit der StopForumSpam-Datenbank, die IPs, E-Mails und Benutzernamen auflistet, die für das Spammen von Foren und Websites bekannt sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul fragt StopForumSpam ab, um zu überprüfen, ob die IP-Adresse des Besuchers als bekannter Spammer gelistet ist.
    - *Wenn deaktiviert:* StopForumSpam-Prüfungen werden nicht durchgeführt.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben einen StopForumSpam-Schlüssel)
  - **Händlerszenario / Beispiel:** Dies ist eine gute zusätzliche Schutzschicht, wenn Sie IPs blockieren möchten, die weltweit als Spammer bekannt sind, auch wenn sie Ihre lokalen Warenkorbgrenzen noch nicht ausgelöst haben.
- **StopForumSpam-Schlüssel**:

  - **Was diese Einstellung bewirkt:** Dies ist der eindeutige Schlüssel, der von StopForumSpam bereitgestellt wird und Ihren Shop bei deren Dienst authentifiziert.
  - **Auswirkung der Änderung dieser Einstellung:** Ohne einen gültigen Schlüssel funktioniert die StopForumSpam-Integration nicht, selbst wenn sie aktiviert ist.
  - **Empfohlener Wert:** Ihr tatsächlicher StopForumSpam API-Schlüssel (leer lassen, wenn StopForumSpam nicht verwendet wird).
  - **Händlerszenario / Beispiel:** Nach der Registrierung bei StopForumSpam erhalten Sie einen API-Schlüssel. Geben Sie ihn hier ein, um deren Dienst zu aktivieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Cart Protection Pro > Versuche (Back Office > Module > Cart Protection Pro > Versuche)

- **Bildschirmname & Menüpfad:** Sie finden diesen Bildschirm, indem Sie zu **Module > Modul-Manager** navigieren, dann auf „Konfigurieren“ bei „Cart protection pro“ klicken und anschließend den Reiter „Versuche“ (oder einen ähnlichen Menüpunkt, falls das Modul ein eigenes Top-Level-Menü hinzufügt) auswählen.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Liste (Rasteransicht) aller aufgezeichneten Warenkorbversuche an, die die Protokollierung des Moduls ausgelöst haben. Er zeigt Details wie:
  - **IP-Adresse:** Die IP-Adresse des Besuchers.
  - **Cookie-ID:** Die eindeutige Cookie-Kennung (wenn „Cookie“-Schutz aktiviert ist).
  - **Versuche:** Die Anzahl der Warenkorb-Hinzufügungen, die von dieser Quelle innerhalb des konfigurierten Zeitrahmens vorgenommen wurden.
  - **Zeitstempel:** Wann der Versuch aufgezeichnet wurde.
  - **Status:** Ob es zu einer Sperre führte oder nur ein Versuch war.
- **Auswirkung von Änderungen:** Dies ist ein schreibgeschütztes Protokoll. Sie können Versuche hier nicht direkt ändern. Sein Zweck ist es, Transparenz und Daten bereitzustellen, damit Sie potenzielle Angriffe verstehen können. Sie können die Liste normalerweise filtern und sortieren, um Muster zu analysieren.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie dieses Protokoll regelmäßig, insbesondere wenn Sie Bot-Aktivitäten vermuten. Achten Sie auf Muster:
  - Viele Versuche von derselben IP oder demselben Cookie.
  - Versuche, die sich auf einen kurzen Zeitraum konzentrieren.
  - Ungewöhnliche IP-Bereiche oder geografische Standorte.
    Diese Daten helfen Ihnen, Ihre Einstellungen für „Zeitrahmen“ und „Anzahl der Versuche“ zu optimieren.

#### 2.2.2 Cart Protection Pro > Sperren (Back Office > Module > Cart Protection Pro > Sperren)

- **Bildschirmname & Menüpfad:** Ähnlich wie der Bildschirm „Versuche“ ist dieser über **Module > Modul-Manager > „Cart protection pro“ konfigurieren > Sperren** (Tab/Menüpunkt) zugänglich.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Liste (Rasteransicht) aller IP-Adressen oder Cookie-IDs an, die vom Modul blockiert wurden. Er zeigt typischerweise:
  - **IP-Adresse:** Die blockierte IP.
  - **Cookie-ID:** Das blockierte Cookie (falls zutreffend).
  - **Grund:** Warum die Sperre erfolgte (z. B. „Zu viele Versuche“).
  - **Sperrbeginn/-ende:** Wann die Sperre initiiert wurde und ob sie temporär ist.
  - **Aktionen:** Enthält oft Optionen zum manuellen „Entsperren“ eines Eintrags.
- **Auswirkung von Änderungen:**
  - *Entsperren eines Eintrags:* Entfernt die Blockierung für diese spezifische IP oder dieses Cookie, sodass sie wieder auf Ihre Warenkorbfunktion zugreifen können. Mit Vorsicht verwenden!
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - Überprüfen Sie regelmäßig die Liste der Sperren. Wenn Sie feststellen, dass eine legitime IP-Adresse (z. B. Ihre eigene oder die eines bekannten Partners) versehentlich gesperrt wurde, können Sie sie hier entsperren.
  - Achten Sie auf wiederkehrende IP-Adressen oder Muster bei Sperren, die auf hartnäckige Angriffe hindeuten könnten.
  - Dieser Bildschirm ist entscheidend, um sicherzustellen, dass das Modul bösartigen Datenverkehr effektiv blockiert, ohne unbeabsichtigt echte Kunden zu beeinträchtigen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Aktiviert | JA | Hauptschalter für die Modulfunktionalität. |
| Modulkonfiguration | Schutztyp | IP-Adresse + Cookie | Methode zur Identifizierung und Blockierung verdächtiger Aktivitäten (IP, Cookie, beides, CleanTalk, StopForumSpam). |
| Modulkonfiguration | Zeitrahmen | 10 Minuten | Dauer (Minuten) für die Zählung von Warenkorbversuchen. |
| Modulkonfiguration | Anzahl der Versuche | 5 | Max. Warenkorb-Hinzufügungen innerhalb des Zeitrahmens vor einer Blockierung. |
| Modulkonfiguration | Titel der E-Mail an den Händler | Cart Protection Pro - Sperrwarnung! | Betreffzeile für Händler-Benachrichtigungs-E-Mails. |
| Modulkonfiguration | Protokolle | JA | Aktiviert/deaktiviert die Protokollierung von Versuchen und Sperren. |
| Modulkonfiguration | CleanTalk kostenlosen Support aktivieren | NEIN | Aktiviert kostenlose CleanTalk Anti-Spam-Prüfungen. |
| Modulkonfiguration | CleanTalk kostenpflichtigen Support aktivieren | NEIN | Aktiviert kostenpflichtige CleanTalk Anti-Spam-Prüfungen. |
| Modulkonfiguration | CleanTalk API-Schlüssel | (leer) | Ihr eindeutiger CleanTalk API-Schlüssel. |
| Modulkonfiguration | StopForumSpam-Support aktivieren | NEIN | Aktiviert StopForumSpam IP-Datenbankprüfungen. |
| Modulkonfiguration | StopForumSpam-Schlüssel | (leer) | Ihr eindeutiger StopForumSpam API-Schlüssel. |
| AdminCproAttempts | Raster- / Verwaltungsansicht | N/A | Zeigt ein Protokoll aller Warenkorbversuche an. |
| AdminCproBans | Raster- / Verwaltungsansicht | N/A | Zeigt eine Liste aller blockierten IPs/Cookies mit Entsperrungsoption an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden beschweren sich, dass sie keine Artikel in den Warenkorb legen können, aber ich sehe keine Sperren.**
A1: Überprüfen Sie zunächst, ob das Modul „Cart protection pro“ in seiner Konfiguration „Aktiviert“ ist. Wenn ja, navigieren Sie zum Abschnitt „Sperren“ innerhalb der Modulkonfiguration. Prüfen Sie, ob dort legitime Kunden-IPs aufgeführt sind. Wenn ja, haben Sie möglicherweise die „Anzahl der Versuche“ oder den „Zeitrahmen“ zu aggressiv eingestellt. Versuchen Sie, die „Anzahl der Versuche“ leicht zu erhöhen (z. B. von 3 auf 5 oder 7) oder den „Zeitrahmen“ zu verlängern (z. B. von 5 auf 10-15 Minuten). Stellen Sie auch sicher, dass Ihr Theme oder andere Module den Warenkorbprozess nicht stören.

**F2: Ich habe CleanTalk/StopForumSpam konfiguriert, aber es scheint nicht zu funktionieren.**
A2: Überprüfen Sie Folgendes:
1. Stellen Sie sicher, dass „CleanTalk/StopForumSpam-Support aktivieren“ aktiviert ist.
2. Überprüfen Sie, ob Ihr „CleanTalk API-Schlüssel“ oder „StopForumSpam-Schlüssel“ korrekt eingegeben wurde und beim jeweiligen Dienst aktiv ist. Schon ein einziger Tippfehler verhindert die Funktion.
3. Bestätigen Sie, dass Ihre Hosting-Umgebung ausgehende cURL-Anfragen zulässt, die für die Kommunikation mit diesen externen Diensten erforderlich sind. Ihr Host kann dies bestätigen.
4. Überprüfen Sie die „Versuche“- und „Sperren“-Protokolle des Moduls auf Einträge, die eine Blockierung durch diese Dienste anzeigen.

**F3: Mein Shop erhält immer noch viele gefälschte Warenkörbe, obwohl das Modul aktiviert ist.**
A3: Dies könnte auf einen ausgeklügelten Bot hindeuten oder darauf, dass Ihre Einstellungen nicht aggressiv genug sind.
1. **Überprüfen Sie Ihre Einstellungen:** Versuchen Sie, die „Anzahl der Versuche“ zu verringern (z. B. von 5 auf 3) und/oder den „Zeitrahmen“ zu verkürzen (z. B. von 10 auf 5 Minuten).
2. **Externe Dienste aktivieren:** Falls noch nicht geschehen, ziehen Sie in Betracht, CleanTalk oder StopForumSpam für eine zusätzliche Schutzschicht zu aktivieren und zu konfigurieren.
3. **Auf Konflikte prüfen:** Deaktivieren Sie vorübergehend andere Sicherheits- oder Caching-Module, um zu sehen, ob ein Konflikt vorliegt.
4. **Cache leeren:** Manchmal kann der Smarty-Cache von PrestaShop verhindern, dass neue Moduleinstellungen sofort wirksam werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.

**F4: Wird dieses Modul meinen Shop verlangsamen?**
A4: Das Modul ist leichtgewichtig konzipiert. Die primären Prüfungen (IP/Cookie) sind sehr schnell. Wenn Sie externe Dienste wie CleanTalk oder StopForumSpam aktivieren, kommt es zu einer geringfügigen Verzögerung, da Ihr Server mit deren APIs kommuniziert. Diese Dienste sind jedoch auf Geschwindigkeit optimiert, und die Auswirkungen sind in der Regel vernachlässigbar. Der Vorteil, eine Serverüberlastung durch gefälschte Warenkörbe zu verhindern, überwiegt jede minimale Verarbeitungszeit bei weitem.

**F5: Wie übersetze ich den E-Mail-Titel oder andere Modultexte?**
A5: Für den „Titel der E-Mail an den Händler“ können Sie den Text einfach direkt in der Modulkonfiguration ändern. Für andere Modultexte (falls welche für Kunden sichtbar wären, was bei diesem Modul im Allgemeinen nicht der Fall ist) würden Sie normalerweise im PrestaShop Back Office zu **International > Übersetzungen** gehen. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Cart protection pro“, um die übersetzbaren Zeichenfolgen zu finden und zu bearbeiten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Moduls „Cart protection pro“, der für Entwickler und Webmaster gedacht ist, die dessen Funktionalität verstehen, debuggen oder erweitern müssen.

### 4.1 Architekturübersicht

Das Modul „Cart protection pro“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Hooks für seine Kernfunktionalität und dedizierte Admin-Controller für die Back-Office-Verwaltung nutzt. Es integriert externe Anti-Spam-Dienste (CleanTalk, StopForumSpam) über cURL-Anfragen. Die Modullogik ist in seiner Hauptklasse und Hilfsklassen gekapselt, wobei die Konfiguration in `ps_configuration` und die Protokolle in benutzerdefinierten Datenbanktabellen gespeichert sind.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Dieses Modul definiert keine expliziten benutzerdefinierten Front-Office-Controller. Seine Front-Office-Logik wird hauptsächlich über Hooks innerhalb der Hauptmoduldatei `cpro.php` ausgeführt, die Warenkorbaktionen abfangen, bevor sie vollständig verarbeitet werden.

#### Back-Office-Admin-Controller

Diese Controller verwalten die dedizierten Administrationsbildschirme des Moduls und bieten Rasteransichten für Versuche und Sperren.

- `cpro/controllers/admin/AdminCproAttempts.php`

  - **Klassenname & Elternklasse**: `AdminCproAttemptsController` erweitert `ModuleAdminController`.
  - **Verantwortlichkeit**: Verwaltet die Anzeige und Interaktion für das „Versuche“-Protokoll im PrestaShop Back Office. Es ruft Daten aus der Datenbanktabelle `cattempt` ab und rendert sie in einem Listenformat, sodass der Administrator alle aufgezeichneten Warenkorbversuche anzeigen kann. Es erlaubt keine direkte Änderung von Versuchen und fungiert als schreibgeschützter Protokollbetrachter.
- `cpro/controllers/admin/AdminCproBans.php`

  - **Klassenname & Elternklasse**: `AdminCproBansController` erweitert `ModuleAdminController`.
  - **Verantwortlichkeit**: Verwaltet die Anzeige und Interaktion für die „Sperren“-Liste im PrestaShop Back Office. Es ruft Daten aus der Datenbanktabelle `cban` ab und präsentiert sie in einer Liste. Dieser Controller behandelt auch Aktionen wie „Entsperren“, die es einem Administrator ermöglichen, eine bestimmte IP oder ein Cookie aus der Sperrliste zu entfernen.
- `cpro/controllers/admin/index.php`

  - **Klassenname & Elternklasse**: Diese Datei dient typischerweise als Sicherheitsmaßnahme in PrestaShop und enthält `die('No direct script access');`, um den direkten Zugriff auf das Verzeichnis zu verhindern. Sie enthält keine funktionale Controller-Klasse.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Die Kernlogik für die Behandlung von Versuchen und Sperren, einschließlich Datenbankinteraktionen, wird wahrscheinlich direkt in der Hauptmoduldatei `cpro.php` oder über direkte `Db::getInstance()`-Aufrufe verwaltet.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist keine benutzerdefinierten JavaScript-Dateien auf. Jegliches dynamische Verhalten im Back Office wird wahrscheinlich durch PrestaShop's Kern-JS oder Inline-Skripte innerhalb von Templates gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist keine benutzerdefinierten CSS-Dateien auf. Das Styling für die Back-Office-Bildschirme basiert auf dem Standard-Admin-Theme von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `cpro/views/templates/admin/main.tpl`
    - **Zweck**: Dieses Template wird wahrscheinlich für die Hauptkonfigurationsseite des Moduls verwendet, die von der `getContent()`-Methode in `cpro.php` gerendert wird. Es enthält die HTML-Struktur für alle in Abschnitt 4.1 beschriebenen Einstellungen, einschließlich Formularfeldern für „Schutztyp“, „Zeitrahmen“, „Anzahl der Versuche“, API-Schlüssel und den Schalter „Aktiviert“. Es könnte auch Navigationsregisterkarten oder Links zu den Controllern `AdminCproAttempts` und `AdminCproBans` enthalten.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_cattempt`: Speichert Protokolle von Warenkorbversuchen.
    - `id_cattempt` (Primärschlüssel)
    - `ip_address` (VARCHAR): IP-Adresse des Besuchers.
    - `cookie_id` (VARCHAR): Eindeutige Kennung aus dem Browser-Cookie.
    - `attempts` (INT): Anzahl der Warenkorb-Hinzufügungen.
    - `date_add` (DATETIME): Zeitstempel des Versuchs.
    - `status` (TINYINT): Status, z. B. 0 für Versuch, 1 für gesperrt.
  - `ps_cban`: Speichert Datensätze von gesperrten IPs/Cookies.
    - `id_cban` (Primärschlüssel)
    - `ip_address` (VARCHAR): Gesperrte IP-Adresse.
    - `cookie_id` (VARCHAR): Gesperrte Cookie-ID.
    - `reason` (TEXT): Grund für die Sperre (z. B. „Zu viele Versuche“).
    - `date_add` (DATETIME): Wann die Sperre initiiert wurde.
    - `date_expire` (DATETIME): Wenn die Sperre temporär ist.
  - **Konfigurationsdatensätze (in `ps_configuration`)**:
    - `CPRO_PTYPE_5`: Einstellung des Schutztyps (z. B. IP, Cookie, CleanTalk).
    - `CPRO_CTALK_APIKEY`: CleanTalk API-Schlüssel.
    - `CPRO_CTALK`: CleanTalk kostenloser Support aktiviert/deaktiviert.
    - `CPRO_CTALK_PAID`: CleanTalk kostenpflichtiger Support aktiviert/deaktiviert.
    - `CPRO_ATMPT`: Anzahl der zulässigen Versuche.
    - `CPRO_TIME`: Zeitrahmen in Minuten.
    - `CPRO_PTYPE_1`, `CPRO_PTYPE_2`, `CPRO_PTYPE_3`, `CPRO_PTYPE_4`: Interne Flags für Schutztypen.
    - `CPRO_SFS`: StopForumSpam-Support aktiviert/deaktiviert.
    - `CPRO_SFS_KEY`: StopForumSpam API-Schlüssel.
    - `CPRO_MTITLE`: E-Mail-Titel für Händlerbenachrichtigungen.
    - `CPRO_LOGS`: Protokollierung aktiviert/deaktiviert.
    - `mypresta_updates`, `update_`, `updatev_`: Interne Schlüssel für Modul-Updates.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionObjectCartAddAfter` | Nachdem ein Warenkorbobjekt in der Datenbank hinzugefügt/aktualisiert wurde. | Potenziell zur Protokollierung erfolgreicher Warenkorb-Hinzufügungen oder zur Nachbearbeitung nach dem Speichern eines Warenkorbs verwendet. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert (eingefügt oder aktualisiert) wurde. | Ähnlich wie `actionObjectCartAddAfter`, wird zur Überwachung oder Protokollierung von Warenkorbänderungen verwendet. |
| `actionFrontControllerInitBefore` | Bevor der Front-Controller initialisiert wird. | Früher Abfangpunkt, um nach gesperrten IPs/Cookies zu suchen, bevor Seiteninhalte gerendert werden, möglicherweise Umleitung oder Anzeige einer Sperrmeldung. |
| `actionObjectCartAddBefore` | Bevor ein Warenkorbobjekt in der Datenbank hinzugefügt/aktualisiert wird. | **KRITISCH**: Dies ist der primäre Hook zum Abfangen und Validieren von Warenkorb-Hinzufügungen. Das Modul führt hier seine Prüfungen (IP, Cookie, CleanTalk, StopForumSpam) durch und kann die Warenkorb-Hinzufügung verhindern, wenn Grenzwerte überschritten oder eine Sperre erkannt wird. |
| `displayHeader` | Im `<head>`-Bereich der Front-Office-Seiten. | Könnte verwendet werden, um notwendiges JavaScript (obwohl keines erkannt wurde) oder CSS einzufügen oder Cookies zur Verfolgung zu setzen. |
| `actionDispatcherBefore` | Bevor der Dispatcher die Anfrage verarbeitet. | Ein weiterer früher Abfangpunkt, ähnlich wie `actionFrontControllerInitBefore`, der es dem Modul ermöglicht, Prüfungen durchzuführen und Anfragen möglicherweise zu blockieren, bevor sie einen bestimmten Controller erreichen. |

### 4.8 Externe API-Integrationen

- **CleanTalk**: Verwendet cURL, um IP-Adressen und potenziell andere Daten zur Spam-Verifizierung an die CleanTalk-API zu senden.
- **StopForumSpam**: Verwendet cURL, um die StopForumSpam-Datenbank mit IP-Adressen abzufragen, um nach bekannten Spammern zu suchen.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für Ihr Modul „Cart protection pro“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul optimal funktioniert und Ihr Shop sicher bleibt.
