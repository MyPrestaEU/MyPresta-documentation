---
title: "CMS-Seiten nur für eingeloggte Benutzer - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „CMS-Seiten nur für eingeloggte Benutzer“ von MyPresta.eu."
sidebar:
  label: "CMS-Seiten nur für eingeloggte Benutzer - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul CMS pages for logged only auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/cms-pages-for-logged-only.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/cms-pages-for-logged-only/)
>
> ---


# CMS-Seiten nur für eingeloggte Benutzer

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modul „CMS-Seiten nur für eingeloggte Benutzer“ auf „Konfigurieren“. Sie sehen einen einzigen Konfigurationsbildschirm.

![Beispiel für den Konfigurationsbildschirm von CMS-Seiten nur für eingeloggte Benutzer](https://mypresta.eu/images/art/cms-pages-for-logged-only-configuration.png)

Dieser Bildschirm zeigt eine Liste all Ihrer vorhandenen CMS-Seiten. Für jede Seite sehen Sie einen einfachen Schalter, um die Beschränkung „nur für eingeloggte Benutzer“ zu aktivieren oder zu deaktivieren.

- **Einstellungsname:** `cmsp` (Dies ist der interne Bezeichner, Sie sehen die tatsächlichen CMS-Seitentitel).
- **Was diese Einstellung bewirkt:** Diese Einstellung ermöglicht es Ihnen, auszuwählen, welche spezifischen CMS-Seiten nur für eingeloggte Kunden zugänglich sein sollen. Jede Zeile repräsentiert eine CMS-Seite Ihres Shops.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (Schalter ist AN/grün):* Die ausgewählte CMS-Seite ist nur für Kunden zugänglich, die in ihrem Konto angemeldet sind. Wenn ein nicht eingeloggter Kunde versucht, diese Seite zu besuchen, wird er zur Anmeldeseite weitergeleitet. Nach erfolgreicher Anmeldung wird er zu dieser spezifischen CMS-Seite zurückgeschickt.
  - *Wenn deaktiviert (Schalter ist AUS/rot):* Die ausgewählte CMS-Seite ist öffentlich für alle Besucher zugänglich, unabhängig davon, ob sie angemeldet sind oder nicht. Dies ist das Standardverhalten für alle CMS-Seiten in PrestaShop.
- **Empfohlener Wert:** Dies hängt vollständig von Ihren Geschäftsanforderungen ab. Aktivieren Sie es für jede CMS-Seite, die sensible, exklusive oder nur für Mitglieder bestimmte Informationen enthält.
- **Händlerszenario / Beispiel:**
  - Sie haben eine CMS-Seite „Großhandelsbedingungen“. Sie würden den Schalter neben dieser Seite aktivieren, damit nur Ihre registrierten Großhandelskunden sie sehen können.
  - Sie erstellen eine CMS-Seite „Premium-Inhaltsführer“ für treue Kunden. Sie würden den Schalter für diese Seite aktivieren, um die Registrierung zu fördern und bestehende Kunden zu belohnen.
  - Sie haben eine Standardseite „Über uns“. Sie würden den Schalter deaktiviert lassen, da diese Seite für alle Besucher öffentlich sichtbar sein sollte.

Nachdem Sie Ihre Auswahl getroffen haben, denken Sie daran, unten auf der Seite auf die Schaltfläche **„Speichern“** zu klicken, um Ihre Änderungen zu übernehmen.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Einzelne CMS-Seitenschalter | Deaktiviert (AUS) | Steuert, ob eine bestimmte CMS-Seite erfordert, dass ein Kunde angemeldet ist, um sie anzuzeigen. Die Aktivierung leitet nicht eingeloggte Benutzer zur Anmeldeseite und nach erfolgreicher Anmeldung zurück zur CMS-Seite. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe die Beschränkung für eine CMS-Seite aktiviert, aber nicht eingeloggte Benutzer können sie immer noch sehen. Was ist falsch?**
A:

1. **Cache leeren:** Der häufigste Grund ist das Caching. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Ihr Browser-Cache muss möglicherweise ebenfalls geleert werden.
2. **Konfiguration speichern:** Stellen Sie sicher, dass Sie auf der Konfigurationsseite des Moduls auf die Schaltfläche „Speichern“ geklickt haben, nachdem Sie die Beschränkung für die spezifische CMS-Seite aktiviert haben.
3. **CMS-Seiten-URL überprüfen:** Überprüfen Sie nochmals, ob Sie die korrekte URL für die von Ihnen eingeschränkte CMS-Seite testen.

**F: Nach dem Einloggen wird der Kunde auf die Startseite statt auf die eingeschränkte CMS-Seite weitergeleitet. Warum?**
A: Dieses Modul ist so konzipiert, dass es den Kunden nach erfolgreicher Anmeldung zur ursprünglich eingeschränkten CMS-Seite zurückleitet. Wenn dies nicht geschieht, könnte es daran liegen:

1. **Benutzerdefinierte Anmelde-Weiterleitungen:** Ein anderes Modul oder eine benutzerdefinierte Theme-Modifikation könnte das Standard-Anmelde-Weiterleitungsverhalten von PrestaShop überschreiben. Deaktivieren Sie vorübergehend andere Module, die die Anmeldung/Weiterleitung beeinflussen, um dies zu testen.
2. **PrestaShop-Versionsspezifika:** Obwohl das Modul mit vielen Versionen kompatibel ist, könnten sehr spezifische Theme- oder Core-Überschreibungen in älteren/neueren PrestaShop-Versionen stören. Stellen Sie sicher, dass Ihre PrestaShop-Kerndateien Standard sind.

**F: Kann ich Kategorien oder Produkte anstelle von CMS-Seiten einschränken?**
A: Nein, dieses Modul ist speziell nur für CMS-Seiten konzipiert. Es bietet keine Funktionalität zum Einschränken von Kategorien, Produkten oder anderen Inhaltstypen. Dafür benötigen Sie ein anderes Modul.

**F: Beeinflusst dieses Modul die SEO?**
A: Wenn eine Seite eingeschränkt ist, werden Suchmaschinen-Crawler (wie Googlebot) in der Regel zur Anmeldeseite weitergeleitet, genau wie ein menschlicher Benutzer. Das bedeutet, dass der Inhalt der eingeschränkten CMS-Seite nicht von Suchmaschinen indiziert wird. Wenn der Inhalt öffentlich sein und indiziert werden soll, beschränken Sie ihn nicht mit diesem Modul. Für Inhalte, die vor Suchmaschinen verborgen, aber für eingeloggte Benutzer zugänglich sein sollen, ist dieses Verhalten erwünscht.

**F: Wie übersetze ich den Text des Moduls (falls vorhanden)?**
A: Dieses Modul hat sehr wenig Front-Office-Text, da es hauptsächlich die Weiterleitung handhabt. Alle Nachrichten im Zusammenhang mit der Anmeldung werden von der Kern-Authentifizierungsseite von PrestaShop verarbeitet. Wenn es modul-spezifische Texte gäbe, würden Sie diese über **International > Übersetzungen** in Ihrem Back Office übersetzen. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und suchen Sie dann „CMS-Seiten nur für eingeloggte Benutzer“ in der Liste.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „CMS-Seiten nur für eingeloggte Benutzer“ (`privatecms`) arbeitet hauptsächlich durch das Überschreiben des Kern-`CmsController`, um Anfragen für CMS-Seiten abzufangen. Es prüft, ob eine angeforderte CMS-Seite für den „nur eingeloggte Benutzer“-Zugriff konfiguriert ist, und wenn der Benutzer nicht angemeldet ist, löst es eine Weiterleitung zur Authentifizierungsseite aus. Nach erfolgreicher Anmeldung sendet der Standard-Weiterleitungsmechanismus von PrestaShop (den das Modul nutzt) den Benutzer zurück zur ursprünglich angeforderten Seite. Die Konfiguration wird über eine Standard-`getContent()`-Methode in der Hauptmoduldatei verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `override/controllers/front/CmsController.php`
    - **Klassenname:** `CmsController` (überschreibt den PrestaShop-Kern-`CmsController`)
    - **Elternklasse:** `CmsControllerCore`
    - **Verantwortlichkeit:** Diese Überschreibung ist der Kern der Modulfunktionalität. Sie fängt die `init()`-Methode des `CmsController` ab. Bevor die CMS-Seite gerendert wird, prüft sie, ob die aktuelle CMS-Seiten-ID (`$this->cms->id`) in der Liste der eingeschränkten Seiten enthalten ist, die in der Modulkonfiguration gespeichert sind. Wenn die Seite eingeschränkt ist und der Kunde nicht angemeldet ist (`$this->context->customer->isLogged()`), leitet sie den Benutzer zur Authentifizierungsseite (`$this->context->link->getPageLink('authentication')`) weiter. Sie enthält auch einen `back`-Parameter in der Weiterleitungs-URL, der sicherstellt, dass PrestaShop den Benutzer nach erfolgreicher Anmeldung zur ursprünglichen CMS-Seite zurückleitet.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Keine. Das Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Entitäten. Es interagiert direkt mit bestehenden PrestaShop-Kernklassen wie `Configuration`, `Cms`, `Customer` und `Link`.

### 4.4 JavaScript-Assets (`views/js/`)

Keine. Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Seine Funktionalität ist rein serverseitig (PHP-basierte Weiterleitung).

### 4.5 CSS-Stylesheets (`views/css/`)

- `privatecms/css.css`
  - **Geltungsbereich:** Styling des Back-Office-Admin-Formulars.
  - **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet enthält wahrscheinlich minimale Stile für das Konfigurationsformular des Moduls im PrestaShop Back Office, um sicherzustellen, dass das Layout und die Elemente (wie die Liste der CMS-Seiten und Schalter) korrekt und konsistent mit dem PrestaShop-Admin-Theme angezeigt werden.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Spezifische Selektoren wären in der Datei zu finden, die typischerweise Elemente innerhalb der `admin.tpl`-Vorlage ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `privatecms/admin.tpl`
    - **Zweck:** Dieses Template wird von der `getContent()`-Methode der Hauptmoduldatei (`privatecms.php`) gerendert. Es zeigt die Liste aller verfügbaren CMS-Seiten im Back Office an, zusammen mit einem Umschalter für jede Seite, der es dem Administrator ermöglicht, die Beschränkung „nur für eingeloggte Benutzer“ zu aktivieren oder zu deaktivieren. Es iteriert durch die CMS-Seiten und zeigt deren Titel und den aktuellen Status der Beschränkung (aktiviert/deaktiviert) an.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Die Konfiguration wird in der Tabelle `ps_configuration` (oder `_configuration` Präfix) gespeichert.
    - **Schlüssel:** `cmsp`
    - **Wert:** Ein serialisiertes Array (oder JSON-String, je nach PrestaShop-Version und Modulimplementierung), das die IDs der CMS-Seiten enthält, die für den „nur eingeloggte Benutzer“-Zugriff ausgewählt sind.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert in seiner `install()`-Methode keine expliziten Standard-PrestaShop-Hooks. Seine Kernfunktionalität basiert auf dem Überschreiben des `CmsController`, was eine direktere Methode ist, um CMS-Seitenanfragen abzufangen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `override/controllers/front/CmsController.php` | Während der `CmsController`-Initialisierung | Fängt CMS-Seitenanfragen ab, um den Anmeldestatus zu überprüfen und bei Bedarf umzuleiten. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „CMS-Seiten nur für eingeloggte Benutzer“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
