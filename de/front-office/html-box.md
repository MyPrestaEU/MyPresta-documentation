---
title: "Html-Box – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Html-Box von MyPresta.eu."
sidebar:
  label: "Html-Box – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Html box auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/html-box.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/html-box/)
>
> ---


# Html-Box

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Html-Box)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie den Inhalt für Ihre HTML-Boxen und deren Erscheinungsort definieren.

#### Allgemeine Einstellungen

- **SSL (https) für dieses Modul aktivieren?** (`htmlbox_ssl`)

  - **Was diese Einstellung bewirkt:** Legt fest, ob der Inhalt des Moduls sicher über HTTPS geladen werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Stellt sicher, dass alle von diesem Modul generierten Inhalte über HTTPS bereitgestellt werden, wodurch „Mixed Content“-Warnungen in Browsern vermieden werden, wenn Ihr Shop SSL verwendet.
    - *Wenn deaktiviert (NEIN):* Inhalte könnten über HTTP bereitgestellt werden, was auf HTTPS-fähigen Shops zu Sicherheitswarnungen führen kann.
  - **Empfohlener Wert:** **JA**
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop HTTPS verwendet (was er sollte!), stellt die Aktivierung sicher, dass Ihre benutzerdefinierten Inhalte keine Sicherheitswarnungen für Ihre Kunden auslösen.
- **TinyMCE-Editor deaktivieren?** (`htmlbox_disabletiny`)

  - **Was diese Einstellung bewirkt:** Steuert, ob der Rich-Text-Editor (TinyMCE) für die Eingabe Ihrer HTML-Inhalte verwendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Sie sehen ein einfaches Textfeld zur Eingabe Ihres HTML, JavaScript oder CSS. Dies ist nützlich, wenn Sie komplexen Code einfügen, den TinyMCE möglicherweise „bereinigen“ möchte, oder wenn Sie lieber reines HTML schreiben.
    - *Wenn deaktiviert (NEIN):* Sie haben einen benutzerfreundlichen Rich-Text-Editor, ähnlich einem Textverarbeitungsprogramm, mit dem Sie Text formatieren, Bilder hinzufügen und Links erstellen können, ohne direkt HTML zu schreiben.
  - **Empfohlener Wert:** **NEIN** (es sei denn, Sie sind Entwickler oder fügen komplexen Code ein).
  - **Händlerszenario / Beispiel:** Wenn Sie schnell eine fettgedruckte Textankündigung hinzufügen möchten, lassen Sie es deaktiviert. Wenn Sie einen Facebook-Widget-Code einfügen, aktivieren Sie es, um zu verhindern, dass der Editor Ihren Code ändert.
- **Nur für eingeloggte Kunden anzeigen?** (`htmlbox_logged`)

  - **Was diese Einstellung bewirkt:** Beschränkt die Sichtbarkeit des HTML-Box-Inhalts nur auf Kunden, die in ihren Konten angemeldet sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Nur registrierte und eingeloggte Kunden sehen den Inhalt der HTML-Box.
    - *Wenn deaktiviert (NEIN):* Alle Besucher, ob angemeldet oder nicht, sehen den Inhalt.
  - **Empfohlener Wert:** **NEIN** (es sei denn, Sie haben spezifische Inhalte für eingeloggte Benutzer).
  - **Händlerszenario / Beispiel:** Sie könnten dies aktivieren, wenn Sie eine spezielle Nachricht für ein Treueprogramm oder exklusive Angebote nur für Ihren bestehenden Kundenstamm anzeigen möchten.
- **Nur für NICHT eingeloggte Kunden anzeigen?** (`htmlbox_unlogged`)

  - **Was diese Einstellung bewirkt:** Beschränkt die Sichtbarkeit des HTML-Box-Inhalts nur auf Kunden, die *nicht* in ihren Konten angemeldet sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Nur Besucher, die nicht angemeldet sind, sehen den Inhalt der HTML-Box.
    - *Wenn deaktiviert (NEIN):* Alle Besucher, ob angemeldet oder nicht, sehen den Inhalt.
  - **Empfohlener Wert:** **NEIN** (es sei denn, Sie haben spezifische Inhalte für Gäste).
  - **Händlerszenario / Beispiel:** Sie könnten dies aktivieren, um eine Nachricht wie „Anmelden oder Registrieren für exklusive Angebote“ anzuzeigen, um neue Anmeldungen oder wiederkehrende Kunden zur Anmeldung zu ermutigen.

#### HTML-Box Inhaltsfelder

In diesen Feldern geben Sie den eigentlichen HTML-, JavaScript- oder CSS-Inhalt für jeden spezifischen Hook ein. Jedes Feld entspricht einem anderen Ort in Ihrem Shop.

- **HTML für Header (`displayTop`, `displayNav1`, `displayNav2`)** (`htmlbox_header`)

  - **Was diese Einstellung bewirkt:** Dies ist der Inhalt, der im Header-Bereich Ihres Shops erscheint. Je nach Ihrem Theme könnte dies `displayTop`, `displayNav1` oder `displayNav2` sein.
  - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird ganz oben auf Ihrer Website sichtbar sein.
  - **Empfohlener Wert:** Leer lassen, wenn nicht benötigt.
  - **Händlerszenario / Beispiel:** Ein websiteübergreifendes Ankündigungsbanner („Kostenloser Versand für alle Bestellungen über 50 $!“), eine kleine Social-Media-Icon-Leiste oder eine benutzerdefinierte Suchleiste.
- **HTML für obere Spalte (`displayTopColumn`)** (`htmlbox_top`)

  - **Was diese Einstellung bewirkt:** Dieser Inhalt erscheint direkt unter dem Header und erstreckt sich oft über die gesamte Breite des Hauptinhaltsbereichs.
  - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird prominent oben im Hauptinhaltsbereich angezeigt, typischerweise über den Hauptproduktlisten oder dem Startseiteninhalt.
  - **Empfohlener Wert:** Leer lassen, wenn nicht benötigt.
  - **Händlerszenario / Beispiel:** Ein großes Werbebanner für einen saisonalen Verkauf, ein Slider für vorgestellte Produkte oder eine Video-Einführung in Ihre Marke.
- **HTML für linke Spalte (`displayLeftColumn`)** (`htmlbox_leftcol`)

  - **Was diese Einstellung bewirkt:** Dieser Inhalt erscheint in der linken Seitenleiste Ihres Shops (wenn Ihr Theme eine hat und diese aktiviert ist).
  - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird in der linken Spalte angezeigt, neben anderen Modulen wie Kategoriefiltern oder Navigation.
  - **Empfohlener Wert:** Leer lassen, wenn nicht benötigt.
  - **Händlerszenario / Beispiel:** Eine „Nach Marke einkaufen“-Liste, ein Newsletter-Anmeldeformular, eine kleine Anzeige für eine bestimmte Produktkategorie oder eine Facebook-Like-Box.
- **HTML für rechte Spalte (`displayRightColumn`)** (`htmlbox_rightcol`)

  - **Was diese Einstellung bewirkt:** Dieser Inhalt erscheint in der rechten Seitenleiste Ihres Shops (wenn Ihr Theme eine hat und diese aktiviert ist).
  - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird in der rechten Spalte angezeigt, ähnlich der linken Spalte.
  - **Empfohlener Wert:** Leer lassen, wenn nicht benötigt.
  - **Händlerszenario / Beispiel:** Eine „Bestseller“-Liste, ein Kundenservice-Kontaktblock, ein Pinterest-Feed oder ein Bereich für „Zuletzt angesehene Produkte“.
- **HTML für Footer (`displayFooter`)** (`htmlbox_footercol`)

  - **Was diese Einstellung bewirkt:** Dieser Inhalt erscheint im Footer-Bereich am unteren Rand jeder Seite.
  - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird ganz unten auf Ihrer Website sichtbar sein.
  - **Empfohlener Wert:** Leer lassen, wenn nicht benötigt.
  - **Händlerszenario / Beispiel:** Logos für Zahlungsmethoden, Vertrauenssiegel, ein kurzer „Über uns“-Text, Social-Media-Links oder ein benutzerdefinierter Copyright-Hinweis.
- **HTML für Startseite (`displayHome`)** (`htmlbox_homecol`)

  - **Was diese Einstellung bewirkt:** Dieser Inhalt wird speziell auf der Startseite Ihres Shops angezeigt.
  - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird ein zentraler Bestandteil Ihres Startseiten-Layouts sein.
  - **Empfohlener Wert:** Leer lassen, wenn nicht benötigt.
  - **Händlerszenario / Beispiel:** Ein Raster mit vorgestellten Kategorien, ein Abschnitt „Warum bei uns einkaufen“, Kundenreferenzen oder ein großer Call-to-Action-Button.
- **HTML für Body (`displayBody`)** (`htmlbox_body`)

  - **Was diese Einstellung bewirkt:** Dieser Inhalt wird in das `<body>`-Tag Ihres HTML eingefügt, typischerweise ganz am Ende vor dem schließenden `</body>`-Tag. Er wird oft für globale Skripte oder Elemente verwendet, die auf der gesamten Website verfügbar sein müssen, aber nicht visuell an einen bestimmten Abschnitt gebunden sind.
  - **Auswirkung der Änderung dieser Einstellung:** Der Inhalt ist auf jeder Seite Ihres Shops vorhanden, aber seine visuelle Platzierung kann von den CSS-Einstellungen Ihres Themes abhängen. Er eignet sich hervorragend für Tracking-Codes oder Pop-ups.
  - **Empfohlener Wert:** Leer lassen, wenn nicht benötigt.
  - **Händlerszenario / Beispiel:** Google Analytics Tracking-Code, Facebook Pixel, ein globales Cookie-Zustimmungsbanner (falls nicht von einem anderen Modul gehandhabt) oder ein Chat-Widget-Skript.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | SSL (https) für dieses Modul aktivieren? | JA | Stellt sicher, dass Inhalte sicher geladen werden, verhindert Mixed-Content-Warnungen. |
| Modulkonfiguration | TinyMCE-Editor deaktivieren? | NEIN | Steuert den Rich-Text-Editor für die Inhaltseingabe. Für Rohcode aktivieren. |
| Modulkonfiguration | Nur für eingeloggte Kunden anzeigen? | NEIN | Beschränkt die Sichtbarkeit des Inhalts auf eingeloggte Benutzer. |
| Modulkonfiguration | Nur für NICHT eingeloggte Kunden anzeigen? | NEIN | Beschränkt die Sichtbarkeit des Inhalts auf Gastbenutzer. |
| Modulkonfiguration | HTML für Header | Leer | Benutzerdefinierter Inhalt im Header-Bereich (z. B. Ankündigungen, Top-Banner). |
| Modulkonfiguration | HTML für obere Spalte | Leer | Benutzerdefinierter Inhalt unter dem Header, oft vollbreit (z. B. Hauptaktionen). |
| Modulkonfiguration | HTML für linke Spalte | Leer | Benutzerdefinierter Inhalt in der linken Seitenleiste (z. B. Social Feeds, Newsletter). |
| Modulkonfiguration | HTML für rechte Spalte | Leer | Benutzerdefinierter Inhalt in der rechten Seitenleiste (z. B. Bestseller, Kundenservice). |
| Modulkonfiguration | HTML für Footer | Leer | Benutzerdefinierter Inhalt im Footer (z. B. Zahlungslogos, Vertrauenssiegel). |
| Modulkonfiguration | HTML für Startseite | Leer | Benutzerdefinierter Inhalt speziell auf der Startseite (z. B. vorgestellte Produkte). |
| Modulkonfiguration | HTML für Body | Leer | Globale Inhalte/Skripte, die in den `<body>` eingefügt werden (z. B. Analytics, Chat-Widgets). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein benutzerdefiniertes HTML wird nicht angezeigt oder sieht fehlerhaft aus.**
A:

1.  **Hook überprüfen:** Stellen Sie sicher, dass Sie den Inhalt im richtigen HTML-Box-Feld für den gewünschten Ort eingegeben haben (z. B. `HTML für Startseite` für die Startseite).
2.  **Cache leeren:** Gehen Sie im PrestaShop Back Office zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). PrestaShop speichert Inhalte oft im Cache, und neue Moduleinstellungen werden möglicherweise nicht sofort angezeigt.
3.  **HTML überprüfen:** Wenn Sie sich damit auskennen, verwenden Sie die Entwicklertools Ihres Browsers (F12), um den Bereich zu überprüfen, in dem der Inhalt erscheinen sollte. Suchen Sie in der Konsole nach Fehlern oder prüfen Sie, ob Ihr HTML vorhanden, aber falsch formatiert ist.
4.  **TinyMCE-Interferenz:** Wenn Sie komplexen Code (insbesondere JavaScript oder Iframes) einfügen, versuchen Sie, „TinyMCE-Editor deaktivieren?“ zu aktivieren, um sicherzustellen, dass der Editor Ihren Code nicht entfernt oder ändert.

**F: Der Inhalt wird angezeigt, sieht aber auf Mobilgeräten nicht gut aus.**
A: Das Modul selbst ist responsiv, aber der *Inhalt, den Sie hinzufügen*, muss ebenfalls responsiv sein.

1.  **Responsives HTML/CSS verwenden:** Wenn Sie benutzerdefiniertes HTML schreiben, stellen Sie sicher, dass Sie responsive Designprinzipien verwenden (z. B. `max-width: 100%` für Bilder, CSS-Media-Queries).
2.  **Drittanbieter-Widgets:** Wenn Sie ein Widget einbetten (wie Facebook oder Twitter), prüfen Sie, ob der Widget-Anbieter responsive Embed-Codes oder Einstellungen anbietet.
3.  **Einfacher Inhalt:** Für kritische mobile Inhalte halten Sie es einfach: einfacher Text, kleine Bilder und klare Handlungsaufforderungen.

**F: Ich habe JavaScript hinzugefügt, aber es wird nicht ausgeführt.**
A:

1.  **Platzierung:** JavaScript, das dem Feld `HTML für Body` hinzugefügt wird, ist im Allgemeinen der sicherste Ort für globale Skripte, da es am Ende der Seite geladen wird.
2.  **Syntaxfehler:** Überprüfen Sie Ihren JavaScript-Code auf Syntaxfehler. Ein einziger Fehler kann die Ausführung des gesamten Skripts verhindern.
3.  **jQuery-Konflikte:** Wenn Ihr Skript auf jQuery basiert, stellen Sie sicher, dass es korrekt geladen wird und dass es keine Konflikte mit der jQuery-Version von PrestaShop gibt. Möglicherweise müssen Sie Ihren Code in `(function($){ /* Ihr Code */ })(jQuery);` einschließen oder `jQuery.noConflict();` verwenden.
4.  **Externe Skripte:** Wenn Sie auf eine externe `.js`-Datei verlinken, stellen Sie sicher, dass die URL korrekt und zugänglich ist.

**F: Wie übersetze ich den Inhalt meiner HTML-Boxen für verschiedene Sprachen?**
A: Die aktuelle Version des Moduls bietet keine integrierten mehrsprachigen Felder für jede HTML-Box. Um mehrsprachigen Inhalt zu erzielen, haben Sie zwei Hauptoptionen:

1.  **Manuelle Spracherkennung (Fortgeschritten):** Sie können bedingte Logik in Ihren HTML-Box-Inhalt einbetten, indem Sie Smarty-Variablen (wenn Ihr Theme Smarty-Verarbeitung in Hooks zulässt) oder JavaScript verwenden, um die aktuelle Sprache zu erkennen und unterschiedliche Inhalte anzuzeigen. Dies ist eine fortgeschrittenere Lösung.
    *Beispiel (Smarty):*

    ```
    {if $language.iso\_code == 'en'} <p>Welcome to our English store!</p>{elseif $language.iso\_code == 'fr'} <p>Bienvenue dans notre boutique française !</p>{/if}
    ```
2.  **Separate Module (Workaround):** Für kritische Inhalte könnten Sie in Betracht ziehen, separate Instanzen des Moduls „Html-Box“ zu installieren (falls vom Modulentwickler erlaubt oder durch Duplizieren des Moduls) und jede einer bestimmten Sprache zuzuweisen, dann deren Anzeige über die Modulpositionen von PrestaShop zu verwalten. Dies ist ein komplexerer Workaround.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Html-Box-Modul arbeiten.

### 4.1 Architekturübersicht

Das `Html-Box`-Modul ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, benutzerdefinierte HTML/JS/CSS-Inhalte in verschiedene Front-Office-Hooks einzufügen. Es folgt einer klassischen PrestaShop-Modulstruktur, die die `Module`-Klasse für Installation, Deinstallation und Konfiguration nutzt und die `hook`-Methoden verwendet, um Inhalte im Front Office zu rendern. Die Konfiguration wird über die `getContent()`-Methode verwaltet, die ein Standard-PrestaShop-Konfigurationsformular rendert. Das Modul speichert seine Inhalte direkt in der Tabelle `ps_configuration`.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Funktionalität, einschließlich Konfiguration und Front-Office-Rendering, wird direkt in der Hauptmoduldatei `htmlbox.php` behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Alle Daten werden als Konfigurationswerte gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

- **`htmlbox/tinymce16.inc.js`**
  - **Geltungsbereich:** Back-Office (speziell die Modulkonfigurationsseite).
  - **Zweck:** Diese Datei ist für die Initialisierung und Konfiguration des TinyMCE-Rich-Text-Editors innerhalb des Konfigurationsformulars des Moduls verantwortlich. Sie wandelt Standard-`<textarea>`-Elemente in einen benutzerfreundlichen WYSIWYG-Editor um, der es Händlern ermöglicht, Text zu formatieren, Bilder einzufügen und HTML-Inhalte ohne direkte Codierung zu verwalten. Sie enthält wahrscheinlich benutzerdefinierte Einstellungen zur Integration von TinyMCE mit dem PrestaShop-Dateimanager für Bild-Uploads.
  - **Entwicklerhinweise:** Wenn `htmlbox_disabletiny` aktiviert ist, wird dieses Skript nicht geladen oder seine Funktionalität wird umgangen. Entwickler, die das TinyMCE-Erlebnis anpassen möchten (z. B. benutzerdefinierte Schaltflächen hinzufügen, das Toolbar-Layout ändern), müssten diese Datei ändern oder ihr Laden/ihre Konfiguration überschreiben.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Jede Stilgebung für den eingefügten HTML-Inhalt muss innerhalb des HTML-Inhalts selbst (Inline-Styles oder `<style>`-Tags) oder durch das aktive PrestaShop-Theme bereitgestellt werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`views/templates/hook/html.tpl`**
  - **Geltungsbereich:** Front-Office.
  - **Hook-Rendering:** Dies ist die primäre Template-Datei, die vom Modul verwendet wird, um den benutzerdefinierten HTML-Inhalt in allen registrierten Front-Office-Hooks zu rendern.
  - **Inhalt:** Sie enthält wahrscheinlich eine einfache Struktur, um die Variable `$html_content` auszugeben, die von den Hook-Methoden des Moduls übergeben wird.
  - **Entwicklerhinweise:** Dieses Template ist minimalistisch. Der eigentliche Inhalt wird dynamisch aus der Tabelle `ps_configuration` basierend auf dem Hook geladen. Entwickler können dieses Template in ihrem Theme überschreiben (z. B. `themes/yourtheme/modules/htmlbox/html.tpl`), um den Inhalt in benutzerdefinierte `div`s zu verpacken, spezifische Klassen hinzuzufügen oder bedingte Logik anzuwenden, obwohl die meisten Anpassungen direkt im HTML-Box-Inhalt selbst vorgenommen werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle Konfigurationen und Inhalte werden in der Standard-PrestaShop-Tabelle `ps_configuration` unter Verwendung der folgenden Schlüssel gespeichert:

  - `mypresta_updates`
  - `update_`
  - `updatev_`
  - `htmlbox_header`
  - `htmlbox_top`
  - `htmlbox_leftcol`
  - `htmlbox_rightcol`
  - `htmlbox_footercol`
  - `htmlbox_homecol`
  - `htmlbox_body`
  - `htmlbox_ssl`
  - `htmlbox_origtiny`
  - `htmlbox_disabletiny`
  - `htmlbox_home`
  - `htmlbox_hook`
  - `htmlbox_logged`
  - `htmlbox_unlogged`
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Hauptsächlich zum Hinzufügen von Meta-Tags, CSS-Links oder JavaScript, die früh geladen werden müssen. |
| `displayTop` | Oberer Bereich der Seite, typischerweise über dem Hauptinhalt. | Allgemeiner Inhalt für den oberen Bereich der Seite, oft Theme-abhängig. |
| `displayNav1` | Navigationsleiste, oft die oberste Leiste mit Schnelllinks. | Inhalt für die erste Navigationsleiste. |
| `displayNav2` | Sekundäre Navigationsleiste, oft unter `displayNav1`. | Inhalt für die zweite Navigationsleiste. |
| `displayTopColumn` | Vollbreiter Bereich unter dem Header, über dem Hauptinhalt. | Prominenter Inhaltsbereich, oft für Banner oder Slider verwendet. |
| `displayLeftColumn` | Linke Seitenleiste auf Seiten, auf denen sie aktiviert ist. | Inhalt für die linke Seitenleiste (z. B. Filter, Kategorien, benutzerdefinierte Blöcke). |
| `displayRightColumn` | Rechte Seitenleiste auf Seiten, auf denen sie aktiviert ist. | Inhalt für die rechte Seitenleiste (z. B. Anzeigen, Social Widgets). |
| `displayHome` | Hauptinhaltsbereich der Startseite. | Inhalt speziell für die Startseite. |
| `displayFooter` | Unterer Bereich jeder Seite. | Inhalt für den Footer (z. B. Copyright, Zahlungslogos, Links). |
| `displayBody` | Am Ende des `<body>`-Tags. | Ideal für globales JavaScript (z. B. Analytics, Chat-Widgets) oder Elemente, die zuletzt geladen werden sollen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu bietet dedizierten Support für alle seine Module.
