---
title: "Facebook-Gruppe beitreten Widget – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Facebook-Gruppe beitreten Widget“ von MyPresta.eu."
sidebar:
  label: "Facebook-Gruppe beitreten Widget – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook join to group widget auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-join-to-group-widget.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-join-to-group-widget/)
>
> ---


# Facebook-Gruppe beitreten Widget

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptbildschirm, auf dem Sie alle Optionen für Ihr Facebook-Gruppe beitreten Widget einrichten.

- **Bildschirmname & Menüpfad:** Back Office > Module > Modul-Manager > „Facebook-Gruppe beitreten Widget“ > Konfigurieren

#### Einstellungen & Optionen:

1. **Gruppen-URL** (Konfigurationsschlüssel: `fbg_href`)

   - **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie definiert den direkten Link zu Ihrer Facebook-Gruppe. Wenn Kunden auf den „Gruppe beitreten“-Button klicken, werden sie zu dieser URL weitergeleitet.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf eine gültige Facebook-Gruppen-URL eingestellt:* Der „Gruppe beitreten“-Button leitet Benutzer korrekt zu Ihrer angegebenen Gruppe weiter.
     - *Wenn leer gelassen oder auf eine ungültige URL eingestellt:* Der Button funktioniert möglicherweise nicht oder führt zu einer Fehlerseite, was Ihre Kunden frustriert.
   - **Empfohlener Wert:** Geben Sie immer die vollständige und korrekte URL zu Ihrer Facebook-Gruppe an (z. B. `https://www.facebook.com/groups/ihrgruppenname/`).
   - **Händlerszenario / Beispiel:** Sie möchten, dass Kunden Ihrer Gruppe „Meine tolle Shop-Community“ beitreten. Sie würden hier `https://www.facebook.com/groups/meinetolleshopcommunity/` einfügen.
2. **Box-Breite** (Konfigurationsschlüssel: `fbg_width`)

   - **Was diese Einstellung bewirkt:** Steuert die Breite des Facebook-Gruppe beitreten Widget-Feldes in Ihrem Shop. Sie können dies in Pixeln angeben.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf einen bestimmten Pixelwert eingestellt (z. B. `280`):* Das Feld wird versuchen, in dieser genauen Breite gerendert zu werden.
     - *Wenn leer gelassen oder auf `0` eingestellt:* Das Modul versucht, seine Breite basierend auf dem verfügbaren Platz im Hook, in dem es angezeigt wird, automatisch anzupassen oder einen Standardwert zu verwenden.
   - **Empfohlener Wert:** Beginnen Sie mit `280` oder `300` Pixeln. Testen Sie auf verschiedenen Geräten. Wenn Sie möchten, dass es den verfügbaren Platz in einer Spalte ausfüllt, können Sie es leer lassen, aber beachten Sie, dass es in einigen Hooks zu breit werden könnte.
   - **Händlerszenario / Beispiel:** Sie möchten, dass das Widget sauber in Ihre linke Spalte passt, die 250px breit ist. Sie würden dies auf `250` einstellen.
3. **Wo möchten Sie das Feld anzeigen?** (Konfigurationsschlüssel: `fbg_hook`)

   - **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü ermöglicht es Ihnen, den spezifischen Ort (PrestaShop-Hook) auszuwählen, an dem das Widget in Ihrem Shop erscheinen soll.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Auswahl von `DisplayFooter`:* Das Widget erscheint am unteren Rand jeder Seite.
     - *Auswahl von `DisplayHome`:* Das Widget erscheint nur auf Ihrer Startseite.
     - *Auswahl von `DisplayRightColumn`:* Das Widget erscheint in der rechten Seitenleiste auf Seiten, die eine haben.
     - *Auswahl eines anderen Hooks:* Das Widget erscheint an diesem spezifischen Ort.
   - **Empfohlener Wert:** Dies hängt vollständig von Ihrem Theme und Ihrer Marketingstrategie ab. `DisplayRightColumn` oder `DisplayLeftColumn` sind üblich für Seiten-Widgets. `DisplayFooter` ist gut für eine weniger aufdringliche Platzierung. `DisplayHome` ist großartig für hohe Sichtbarkeit.
   - **Händlerszenario / Beispiel:** Sie möchten, dass das Widget auf den meisten Seiten sichtbar ist, aber Ihre Hauptinhalte nicht stört. Sie wählen `DisplayRightColumn`.
4. **Überschrift** (Konfigurationsschlüssel: `fbg_header`)

   - **Was diese Einstellung bewirkt:** Dies ist der Haupttiteltext, der oben in Ihrem Facebook-Gruppe beitreten Widget angezeigt wird.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „Treten Sie unserer Community bei“ eingestellt:* Dieser Text wird prominent angezeigt.
     - *Wenn leer gelassen:* Es wird kein Überschriftstext angezeigt, wodurch das Widget für Kunden weniger klar wird.
   - **Empfohlener Wert:** Ein klarer, einladender Titel wie „Treten Sie unserer Facebook-Gruppe bei“, „Unsere Community“ oder „Verbinden Sie sich mit uns“.
   - **Händlerszenario / Beispiel:** Sie möchten Kunden klar mitteilen, worum es in dem Feld geht. Sie stellen es auf „Treten Sie unserer exklusiven Facebook-Gruppe bei!“ ein.
5. **Beschreibung** (Konfigurationsschlüssel: `fbg_desc`)

   - **Was diese Einstellung bewirkt:** Dies bietet einen kurzen erklärenden Text unter der Überschrift, der Kunden mehr Kontext zu Ihrer Facebook-Gruppe gibt.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „Erhalten Sie exklusive Angebote und Updates!“ eingestellt:* Diese Nachricht erscheint unter der Überschrift.
     - *Wenn leer gelassen:* Das Widget zeigt nur die Überschrift und den Button an, wodurch möglicherweise eine Gelegenheit verpasst wird, Benutzer zu locken.
   - **Empfohlener Wert:** Ein kurzer, überzeugender Satz oder zwei, der die Vorteile des Beitritts erklärt (z. B. „Seien Sie der Erste, der über neue Produkte und Sonderangebote informiert wird!“).
   - **Händlerszenario / Beispiel:** Sie möchten Anmeldungen fördern, indem Sie Vorteile hervorheben. Sie stellen es auf „Erhalten Sie exklusive Mitglieder-Rabatte, Vorschauen und verbinden Sie sich mit anderen Enthusiasten!“.
6. **Button-Text** (Konfigurationsschlüssel: `fbg_btn_text`)

   - **Was diese Einstellung bewirkt:** Dies ist der Text, der auf dem Button angezeigt wird, den Kunden klicken, um Ihrer Gruppe beizutreten.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „Gruppe beitreten“ eingestellt:* Dieser Text erscheint auf dem Button.
     - *Wenn leer gelassen:* Der Button könnte leer erscheinen oder einen Standardwert verwenden, was weniger effektiv ist.
   - **Empfohlener Wert:** Ein klarer Call-to-Action wie „Gruppe beitreten“, „Jetzt beitreten“ oder „Auf Facebook verbinden“.
   - **Händlerszenario / Beispiel:** Sie möchten einen direkten Call-to-Action. Sie stellen es auf „Unsere Gruppe beitreten“.
7. **Textfarbe** (Konfigurationsschlüssel: `fbg_text_color`)

   - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Farbe des Überschrift- und Beschreibungstextes innerhalb des Widgets festzulegen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf `#000000` (schwarz) eingestellt:* Der Text erscheint schwarz.
     - *Wenn auf `#FFFFFF` (weiß) eingestellt:* Der Text erscheint weiß.
   - **Empfohlener Wert:** Wählen Sie eine Farbe, die gut mit Ihrer gewählten Hintergrundfarbe kontrastiert und zur Farbpalette Ihrer Marke passt. Verwenden Sie einen Hex-Code (z. B. `#333333`).
   - **Händlerszenario / Beispiel:** Ihr Widget hat einen dunklen Hintergrund. Sie stellen die Textfarbe auf `#FFFFFF` für bessere Lesbarkeit ein.
8. **Rahmenstil** (Konfigurationsschlüssel: `fbg_border_style`)

   - **Was diese Einstellung bewirkt:** Definiert den visuellen Stil des Rahmens um das Widget-Feld.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *`solid` (durchgezogen):* Eine einzelne, durchgehende Linie.
     - *`dashed` (gestrichelt):* Eine Reihe kurzer Linien.
     - *`dotted` (gepunktet):* Eine Reihe von Punkten.
     - *`none` (keiner):* Es wird kein Rahmen angezeigt.
   - **Empfohlener Wert:** `solid` oder `none` sind am gebräuchlichsten. `solid` bietet eine klare Abgrenzung.
   - **Händlerszenario / Beispiel:** Sie möchten eine subtile Umrandung für das Feld. Sie wählen `solid`.
9. **Rahmenfarbe** (Konfigurationsschlüssel: `fbg_border_color`)

   - **Was diese Einstellung bewirkt:** Legt die Farbe des Rahmens um das Widget-Feld fest.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf `#CCCCCC` (hellgrau) eingestellt:* Der Rahmen wird hellgrau.
     - *Wenn auf `#FF0000` (rot) eingestellt:* Der Rahmen wird rot.
   - **Empfohlener Wert:** Eine Farbe, die das Design Ihres Shops ergänzt, oft ein subtiles Grau oder eine Akzentfarbe der Marke. Verwenden Sie einen Hex-Code.
   - **Händlerszenario / Beispiel:** Ihre Marke verwendet einen bestimmten Blauton. Sie stellen die Rahmenfarbe auf `#007bff` ein.
10. **Rahmengröße** (Konfigurationsschlüssel: `fbg_border_size`)

    - **Was diese Einstellung bewirkt:** Bestimmt die Dicke des Rahmens in Pixeln.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf `1` eingestellt:* Ein dünner Rahmen erscheint.
      - *Wenn auf `5` eingestellt:* Ein dickerer, prominenterer Rahmen erscheint.
    - **Empfohlener Wert:** `1` oder `2` Pixel für einen subtilen Rahmen.
    - **Händlerszenario / Beispiel:** Sie möchten einen sehr dünnen Rahmen. Sie stellen die Größe auf `1` ein.
11. **Rahmenradius** (Konfigurationsschlüssel: `fbg_border_radius`)

    - **Was diese Einstellung bewirkt:** Steuert die Rundung der Ecken des Widget-Feldes. Ein höherer Wert erzeugt stärker abgerundete Ecken.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf `0` eingestellt:* Das Feld hat scharfe, eckige Ecken.
      - *Wenn auf `10` eingestellt:* Die Ecken sind deutlich abgerundet.
    - **Empfohlener Wert:** `0` für scharfe Ecken, `3` bis `5` für leicht abgerundet oder `10+` für sehr abgerundet, je nach Ästhetik Ihres Themes.
    - **Händlerszenario / Beispiel:** Ihr Theme verwendet leicht abgerundete Elemente. Sie stellen den Rahmenradius auf `5` ein.
12. **Hintergrundfarbe** (Konfigurationsschlüssel: `fbg_bg_color`)

    - **Was diese Einstellung bewirkt:** Legt die primäre Hintergrundfarbe des Widget-Feldes fest.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf `#F0F2F5` (hellgrau, ähnlich dem Facebook-Hintergrund) eingestellt:* Der Feldhintergrund wird hellgrau.
      - *Wenn auf `#FFFFFF` (weiß) eingestellt:* Der Feldhintergrund wird weiß.
    - **Empfohlener Wert:** Eine Farbe, die den Text lesbar macht und zum Design Ihres Shops passt. Verwenden Sie einen Hex-Code.
    - **Händlerszenario / Beispiel:** Sie möchten, dass das Widget sich leicht von einem weißen Seitenhintergrund abhebt. Sie stellen die Hintergrundfarbe auf `#F8F8F8` ein.
13. **Hintergrundverlauf** (Konfigurationsschlüssel: `fbg_bg_gradient`)

    - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, einen CSS-Verlauf zum Hintergrund des Widget-Feldes hinzuzufügen, wodurch ein sanfter Übergang zwischen zwei oder mehr Farben entsteht. Dies überschreibt die einzelne „Hintergrundfarbe“, falls verwendet.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf `linear-gradient(to right, #FFD700, #FFA500)` eingestellt:* Der Hintergrund wechselt von Gold zu Orange.
      - *Wenn leer gelassen:* Die Einstellung „Hintergrundfarbe“ wird stattdessen verwendet.
    - **Empfohlener Wert:** Verwenden Sie eine CSS-Verlaufszeichenfolge, wenn Sie einen dynamischeren Hintergrund wünschen. Wenn Sie unsicher sind, lassen Sie dies leer und verwenden Sie eine einzelne „Hintergrundfarbe“.
    - **Händlerszenario / Beispiel:** Sie möchten einen subtilen, modernen Look. Sie verwenden einen Verlauf wie `linear-gradient(to bottom, #e0eafc, #cfdef3)`.

#### Versteckte/Interne Einstellungen (für Entwicklerreferenz, nicht direkt vom Händler konfigurierbar):

- `mypresta_updates`, `update_`, `updatev_`: Interne Schlüssel für Modul-Updates und Versionsprüfungen.
- `fbg_app`, `fbg_appid`: Diese Schlüssel deuten auf eine potenzielle Facebook-App-Integration hin, sind aber in der aktuellen Konfiguration nicht verfügbar.
- `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: PrestaShop-Kerndaten, die sich auf die Sprachbehandlung im Back Office beziehen.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Gruppen-URL** | Ihre Facebook-Gruppen-URL | Direkter Link zu Ihrer Facebook-Gruppe für den „Gruppe beitreten“-Button. **KRITISCH!** |
| Modulkonfiguration | **Box-Breite** | `280` oder `300`px | Legt die Breite des Widget-Feldes fest. Für automatische Anpassung leer lassen. |
| Modulkonfiguration | **Wo möchten Sie das Feld anzeigen?** | `DisplayRightColumn` oder `DisplayFooter` | Wählt den PrestaShop-Hook aus, an dem das Widget erscheint. |
| Modulkonfiguration | **Überschrift** | „Treten Sie unserer Facebook-Gruppe bei“ | Haupttiteltext für das Widget. |
| Modulkonfiguration | **Beschreibung** | „Erhalten Sie exklusive Angebote und Updates!“ | Kurzer erklärender Text unter der Überschrift. |
| Modulkonfiguration | **Button-Text** | „Gruppe beitreten“ | Text, der auf dem Aktionsbutton angezeigt wird. |
| Modulkonfiguration | **Textfarbe** | `#333333` (dunkelgrau) | Farbe des Überschrift- und Beschreibungstextes. Hex-Code verwenden. |
| Modulkonfiguration | **Rahmenstil** | `solid` oder `none` | Visueller Stil des Box-Rahmens (durchgezogen, gestrichelt, gepunktet, keiner). |
| Modulkonfiguration | **Rahmenfarbe** | `#CCCCCC` (hellgrau) | Farbe des Box-Rahmens. Hex-Code verwenden. |
| Modulkonfiguration | **Rahmengröße** | `1` oder `2`px | Dicke des Box-Rahmens. |
| Modulkonfiguration | **Rahmenradius** | `0` oder `5`px | Rundung der Box-Ecken. |
| Modulkonfiguration | **Hintergrundfarbe** | `#F0F2F5` (hellgrau) | Primäre Hintergrundfarbe des Widget-Feldes. Hex-Code verwenden. |
| Modulkonfiguration | **Hintergrundverlauf** | Leer lassen | CSS-Verlauf für den Hintergrund. Überschreibt `Hintergrundfarbe`, falls festgelegt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

1. **Das Widget wird in meinem Shop nicht angezeigt.**

   - **Prüfung 1:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie nach „Facebook-Gruppe beitreten Widget“ und stellen Sie sicher, dass es installiert und aktiviert ist.
   - **Prüfung 2:** Überprüfen Sie in der Konfiguration des Moduls, ob Sie einen „Wo möchten Sie das Feld anzeigen?“ (Hook) ausgewählt haben. Stellen Sie sicher, dass der ausgewählte Hook tatsächlich existiert und in Ihrem aktuellen Theme aktiv ist. Einige Themes verwenden möglicherweise nicht alle Standard-PrestaShop-Hooks.
   - **Prüfung 3:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Performance > Cache leeren**). Manchmal werden Änderungen erst nach dem Aktualisieren des Caches angezeigt.
   - **Prüfung 4:** Wenn Sie ein benutzerdefiniertes Theme haben, kann es Standard-Hook-Anzeigen überschreiben. Kontaktieren Sie Ihren Theme-Entwickler oder einen Webmaster.
2. **Der „Gruppe beitreten“-Button funktioniert nicht oder führt zu einem Fehler.**

   - **Prüfung:** Gehen Sie zur Konfiguration des Moduls und geben Sie Ihre „Gruppen-URL“ sorgfältig erneut ein. Stellen Sie sicher, dass es die vollständige und korrekte URL zu Ihrer Facebook-Gruppe ist (z. B. `https://www.facebook.com/groups/ihrgruppenname/`). Testen Sie die URL direkt in Ihrem Browser, um zu bestätigen, dass sie funktioniert.
3. **Das Widget sieht seltsam aus oder passt nicht zum Design meines Themes.**

   - **Prüfung 1:** Passen Sie die Einstellung „Box-Breite“ an. Wenn sie für eine Spalte zu breit ist, kann dies das Layout stören. Versuchen Sie einen kleineren Pixelwert.
   - **Prüfung 2:** Verwenden Sie die Einstellungen „Textfarbe“, „Rahmenstil“, „Rahmenfarbe“, „Rahmengröße“, „Rahmenradius“, „Hintergrundfarbe“ und „Hintergrundverlauf“, um die Farben und Stile Ihres Themes anzupassen.
   - **Prüfung 3:** Leeren Sie Ihren PrestaShop-Cache, nachdem Sie Stiländerungen vorgenommen haben.
   - **Prüfung 4:** Wenn das Problem weiterhin besteht, könnte es sich um einen CSS-Konflikt mit Ihrem Theme handeln. Ein Webmaster kann das CSS Ihrer Website überprüfen, um Konflikte zu identifizieren und zu beheben.
4. **Kann ich das Widget an mehreren Stellen anzeigen?**

   - Die aktuelle Version des Moduls ermöglicht es Ihnen, nur einen Hook aus dem Dropdown-Menü auszuwählen. Wenn Sie es an mehreren Stellen anzeigen müssen, müssten Sie das Modul duplizieren (was einen Entwicklereingriff erfordert) oder eine benutzerdefinierte Lösung verwenden.
5. **Mein Text wird nicht in der richtigen Sprache angezeigt.**

   - Die Felder „Überschrift“, „Beschreibung“ und „Button-Text“ sind in der Regel übersetzbar, wenn Ihre PrestaShop-Installation mehrere Sprachen für Modulkonfigurationen unterstützt. Stellen Sie sicher, dass Sie die Modulkonfiguration im Back Office im richtigen Sprachkontext bearbeiten (überprüfen Sie das Sprach-Dropdown oben rechts in Ihrem Admin-Panel).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Facebook-Gruppe beitreten Widget“ ist ein unkompliziertes PrestaShop-Modul, das einem grundlegenden MVC-ähnlichen Muster folgt, das der Modulstruktur von PrestaShop eigen ist. Es verwendet hauptsächlich die `Module`-Klasse für seine Kernfunktionalität, Konfigurationsverwaltung und Hook-Registrierung. Die gesamte Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden. Die Front-Office-Anzeige wird über Smarty-Templates verwaltet, die über registrierte Hooks gerendert werden. Es gibt keine benutzerdefinierten Controller oder ObjectModels.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Alle Front-Office-Renderings werden direkt über `hook`-Methoden innerhalb der Hauptmoduldatei `fbgroup.php` behandelt, die dann Smarty-Templates rendern.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Administration wird über die Methode `getContent()` der Hauptmodulklasse behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`fbgroup/fbgroup.php` (Hauptmodulklasse)**
  - **Klassenname:** `Fbgroup`
  - **Elternklasse:** `Module`
  - **Verantwortlichkeit:**
    - Modulinstallation (`install()`) und Deinstallation (`uninstall()`).
    - Registrierung aller angegebenen Hooks (`registerHook()`).
    - Verwaltung der Modulkonfigurationseinstellungen über die Methode `getContent()`, die die Formularübermittlung verarbeitet und die Tabelle `ps_configuration` aktualisiert.
    - Implementierung verschiedener `hook`-Methoden (z. B. `hookDisplayHeader`, `hookDisplayFooter`, `hookDisplayHome` usw.), um das Widget im Front Office zu rendern.
    - Abrufen von Konfigurationswerten aus `ps_configuration` für das Template-Rendering.
    - Methode `_clearCache()` zum Leeren des modulspezifischen Caches.
    - Methode `_displayForm()` zum Rendern des Konfigurationsformulars im Back Office.

### 4.4 JavaScript-Assets (`views/js/`)

- Es sind keine benutzerdefinierten JavaScript-Dateien in diesem Modul enthalten. Die gesamte Funktionalität wird serverseitig oder über Standard-HTML/CSS gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

- Es sind keine benutzerdefinierten CSS-Dateien in diesem Modul enthalten. Die gesamte Formatierung wird inline innerhalb des `displayHeader.tpl`-Templates oder direkt über die `hookDisplayHeader`-Methode unter Verwendung der Konfigurationswerte angewendet. Dies bedeutet, dass Entwickler, die Stile überschreiben möchten, das generierte HTML direkt ansprechen oder den `displayHeader`-Hook verwenden müssen, um ihr eigenes CSS einzufügen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `fbgroup/views/displayHeader.tpl`:
    - **Hook:** Primär für `displayHeader` vorgesehen (obwohl die `hookDisplayHeader`-Methode des Moduls zum Einfügen von CSS verwendet wird, nicht zum Rendern des Widgets selbst). Dieses Template wird NICHT für die Haupt-Widget-Anzeige verwendet. Es ist wahrscheinlich ein Überbleibsel oder wird für Meta-/CSS-Injektionen verwendet.
    - **Zweck:** Wenn es verwendet würde, würde es HTML innerhalb des `<head>`-Abschnitts ausgeben. Im Kontext dieses Moduls wird die `hookDisplayHeader`-Methode verwendet, um CSS-Stile dynamisch basierend auf Konfigurationseinstellungen *einzufügen*, anstatt ein sichtbares Template zu rendern.
  - `fbgroup/views/displayWidget.tpl`:
    - **Hook:** Dies ist das primäre Template, das zum Rendern des Facebook-Gruppe beitreten Widgets in allen ausgewählten Front-Office-Hooks (z. B. `displayFooter`, `displayHome`, `displayRightColumn` usw.) verwendet wird.
    - **Zweck:** Gibt die HTML-Struktur für das Widget aus, einschließlich Überschrift, Beschreibung und des „Gruppe beitreten“-Buttons. Es empfängt Variablen wie `fbg_href`, `fbg_header`, `fbg_desc`, `fbg_btn_text` und dynamische CSS-Stile von den Hook-Methoden des Moduls.
- **Admin-Templates (`views/templates/admin/`)**: Keine. Das Konfigurationsformular wird programmatisch innerhalb von `getContent()` unter Verwendung von PrestaShops `HelperForm` erstellt.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` (oder `_configuration`-Präfix, je nach Ihrer Einrichtung) unter Verwendung der in Abschnitt 4.1 aufgeführten Konfigurationsschlüssel (z. B. `FBG_HREF`, `FBG_WIDTH`, `FBG_HEADER` usw.) gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Seite. | Wird vom Modul verwendet, um dynamische CSS-Stile für das Widget basierend auf der Konfiguration einzufügen. |
| `displayFooter` | Am unteren Rand jeder Seite, vor `</body>`. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayHome` | Auf der Startseite, normalerweise im Hauptinhaltsbereich. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayNav1` | In der Navigationsleiste, oft oben links. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayNav2` | In der Navigationsleiste, oft oben rechts. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayNav` | Generischer Navigations-Hook, Theme-abhängig. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayFbgroup` | Benutzerdefinierter Hook, erfordert Theme-Integration. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayTop` | Im Header-Bereich, oft über dem Logo. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayTopColumn` | Im Hauptinhaltsbereich des Headers. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten, die eine haben. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten, die eine haben. | Rendert das `displayWidget.tpl`-Template und zeigt das Facebook-Widget an. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Bugfixes und offiziellen Support für das Modul „Facebook-Gruppe beitreten Widget“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
