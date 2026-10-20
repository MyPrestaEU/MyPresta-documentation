---
title: "Facebook Like Box Free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Like Box Free von MyPresta.eu."
sidebar:
  label: "Facebook Like Box Free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Like Box Free auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-like-box-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-like-box-free/)
>
> ---


# Facebook Like Box Free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Einrichtung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul Facebook Like Box Free. Hier finden Sie alle Einstellungen, um dessen Aussehen und Verhalten zu steuern.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Aktiviert** / **Deaktiviert** | Steuert, ob die Facebook Like Box aktiv und in Ihrem Shop sichtbar ist. | *Wenn aktiviert:* Die Like Box wird in Ihrem Shop an der gewählten Position angezeigt. *Wenn deaktiviert:* Die Like Box wird in Ihrem Shop ausgeblendet. | **Aktiviert** | Sie möchten Ihre Facebook-Seite bewerben. |
| **Position** | Legt fest, wo die Like Box in Ihrem Shop angezeigt wird. | *Wenn auf Linke Spalte eingestellt:* Die Like Box erscheint in der linken Seitenleiste. *Wenn auf Rechte Spalte eingestellt:* Die Like Box erscheint in der rechten Seitenleiste. *Wenn auf Startseite eingestellt:* Die Like Box erscheint im Hauptinhaltsbereich Ihrer Startseite. *Wenn auf Fußzeile eingestellt:* Die Like Box erscheint am unteren Rand jeder Seite. | **Rechte Spalte** oder **Startseite** | Sie möchten, dass die Like Box prominent sichtbar ist, ohne die Produktansicht zu stören. |
| **Facebook Seiten-URL** | Dies ist der direkte Link zu Ihrer offiziellen Facebook-Seite. | *Wenn auf Ihre Seiten-URL eingestellt (z.B. `https://www.facebook.com/MyPrestaEU`):* Die Like Box zeigt Inhalte und einen „Gefällt mir“-Button für *Ihre* spezifische Facebook-Seite an. *Wenn leer oder falsch:* Die Like Box wird möglicherweise nicht korrekt angezeigt oder zeigt einen Fehler an. | Ihre tatsächliche Facebook Seiten-URL | Sie möchten Ihre Shop-Besucher mit der Facebook-Präsenz Ihrer Marke verbinden. |
| **Breite** | Legt die Breite der Like Box in Pixeln fest. | *Wenn auf einen bestimmten Pixelwert eingestellt (z.B. `280`):* Die Like Box wird genau diese Breite haben. *Wenn leer gelassen:* Das Modul versucht, die Breite automatisch anzupassen, aber es ist oft besser, einen bestimmten Wert für ein konsistentes Design festzulegen. | `280` (oder an Ihre Spalte/Layout anpassen) | Ihre rechte Spalte ist 300px breit, daher stellen Sie die Breite der Like Box auf 280px ein, damit sie mit etwas Abstand gut passt. |
| **Höhe** | Legt die Höhe der Like Box in Pixeln fest. | *Wenn auf einen bestimmten Pixelwert eingestellt (z.B. `500`):* Die Like Box wird genau diese Höhe haben. *Wenn leer gelassen:* Das Modul versucht, die Höhe automatisch anzupassen. | `500` (oder an den Inhalt anpassen, den Sie anzeigen möchten) | Sie möchten einige aktuelle Beiträge anzeigen, daher stellen Sie die Höhe auf 500px ein, um genügend Platz zu lassen. |
| **Titelbild ausblenden** | Steuert, ob das große Titelbild Ihrer Facebook-Seite oben in der Like Box angezeigt wird. | *Wenn aktiviert:* Das Titelbild wird ausgeblendet, wodurch die Like Box kompakter wird. *Wenn deaktiviert:* Das Titelbild wird sichtbar sein. | **Aktiviert** (für ein saubereres Aussehen) | Sie bevorzugen ein minimalistisches Design und möchten, dass die Like Box weniger vertikalen Platz einnimmt. |
| **Profilbilder** (Facepile anzeigen) | Legt fest, ob die Profilbilder von Personen, denen Ihre Seite gefällt, unter dem „Gefällt mir“-Button angezeigt werden. | *Wenn aktiviert:* Eine Reihe kleiner Profilbilder wird angezeigt, die sozialen Beweis liefern. *Wenn deaktiviert:* Diese Profilbilder werden nicht angezeigt. | **Aktiviert** (für sozialen Beweis) | Sie möchten Besuchern zeigen, dass viele andere Ihre Seite bereits mögen, und sie ermutigen, dasselbe zu tun. |
| **Beiträge anzeigen** (Stream anzeigen) | Steuert, ob aktuelle Beiträge Ihrer Facebook-Seite in der Like Box angezeigt werden. | *Wenn aktiviert:* Ihre neuesten Facebook-Beiträge werden sichtbar sein, wodurch die Like Box dynamischer wird. *Wenn deaktiviert:* Nur der „Gefällt mir“-Button und der Facepile (falls aktiviert) werden angezeigt. | **Aktiviert** | Sie posten aktiv auf Facebook und möchten Ihre neuesten Inhalte direkt in Ihrem Shop präsentieren. |
| **Call-to-Action-Button** (CTA ausblenden) | Steuert, ob der „Call to Action“-Button (z.B. „Nachricht senden“, „Jetzt einkaufen“) von Ihrer Facebook-Seite ausgeblendet wird. | *Wenn aktiviert:* Der CTA-Button wird ausgeblendet. *Wenn deaktiviert:* Der CTA-Button wird sichtbar sein, wenn er auf Ihrer Facebook-Seite konfiguriert ist. | **Aktiviert** (oft für ein saubereres Aussehen) | Sie möchten sich ausschließlich auf ein „Gefällt mir“ konzentrieren und keinen weiteren Button haben, der Besucher ablenkt. |
| **Kleiner Header** | Macht den Header der Like Box kleiner. | *Wenn aktiviert:* Der Header (mit Ihrem Seitennamen und dem „Gefällt mir“-Button) wird kompakter. *Wenn deaktiviert:* Der Header hat die Standardgröße. | **Aktiviert** (für ein kompakteres Design) | Sie möchten, dass die Like Box weniger aufdringlich ist und sich nahtloser in das Design Ihres Shops einfügt. |
| **Facebook-Bibliothek** (App einbinden) | Diese Einstellung steuert, ob das notwendige Facebook JavaScript SDK geladen wird. | *Wenn aktiviert:* Das Modul lädt das Facebook SDK, das für die korrekte Funktion der Like Box unerlässlich ist. *Wenn deaktiviert:* Die Like Box wird wahrscheinlich nicht korrekt angezeigt oder funktioniert nicht richtig. | **Aktiviert** | Dies ist entscheidend für die Funktion der Like Box. |

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Aktiviert/Deaktiviert | Aktiviert | Aktiviert/Deaktiviert die Like Box in Ihrem Shop. |
| Modulkonfiguration | Position | Rechte Spalte / Startseite | Legt fest, wo die Like Box erscheint (Linke/Rechte Spalte, Startseite, Fußzeile). |
| Modulkonfiguration | Facebook Seiten-URL | Ihre Facebook Seiten-URL | Verknüpft die Like Box mit Ihrer spezifischen Facebook-Seite. |
| Modulkonfiguration | Breite | 280 | Legt die Breite der Like Box in Pixeln fest. |
| Modulkonfiguration | Höhe | 500 | Legt die Höhe der Like Box in Pixeln fest. |
| Modulkonfiguration | Titelbild ausblenden | Aktiviert | Blendet das große Titelbild für ein kompakteres Aussehen aus. |
| Modulkonfiguration | Profilbilder (Facepile anzeigen) | Aktiviert | Zeigt Profilbilder von Personen an, denen Ihre Seite gefällt (sozialer Beweis). |
| Modulkonfiguration | Beiträge anzeigen (Stream anzeigen) | Aktiviert | Zeigt aktuelle Beiträge von Ihrer Facebook-Seite an. |
| Modulkonfiguration | Call-to-Action-Button (CTA ausblenden) | Aktiviert | Blendet den Call-to-Action-Button der Facebook-Seite aus. |
| Modulkonfiguration | Kleiner Header | Aktiviert | Macht den Like Box Header kompakter. |
| Modulkonfiguration | Facebook-Bibliothek (App einbinden) | Aktiviert | Lädt das notwendige Facebook JavaScript SDK für die Funktionalität. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Die Facebook Like Box wird in meinem Shop nicht angezeigt. Was soll ich tun?**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Facebook Like Box Free“ installiert und aktiviert ist.
2. **Konfiguration überprüfen:** Gehen Sie zur Konfigurationsseite des Moduls.
   - Stellen Sie sicher, dass „Aktiviert“ auf JA gesetzt ist.
   - Überprüfen Sie nochmals, ob die „Facebook Seiten-URL“ korrekt und vollständig ist (z.B. `https://www.facebook.com/MyPrestaEU`).
   - Stellen Sie sicher, dass „Facebook-Bibliothek“ (App einbinden) aktiviert ist.
3. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Module angezeigt werden.
4. **Hook-Position überprüfen:** Stellen Sie sicher, dass die von Ihnen gewählte „Position“ (z.B. Rechte Spalte, Startseite) in Ihrem Theme tatsächlich aktiv ist. Einige Themes zeigen möglicherweise bestimmte Spalten nicht an. Sie können unter **Design > Positionen** überprüfen, ob das Modul korrekt eingehängt ist.

**F: Die Like Box sieht zu breit/schmal oder zu hoch/kurz aus.**
A: Passen Sie die Einstellungen für „Breite“ und „Höhe“ auf der Konfigurationsseite des Moduls an. Experimentieren Sie mit verschiedenen Pixelwerten, bis es perfekt zum Layout Ihres Themes passt. Denken Sie daran, Ihren Browser-Cache zu leeren, nachdem Sie Änderungen vorgenommen haben, um die Aktualisierung zu sehen.

**F: Ich habe Einstellungen geändert, aber in meinem Shop ist nichts passiert.**
A: Nach dem Speichern von Änderungen in der Modulkonfiguration leeren Sie immer den PrestaShop-Cache (**Erweiterte Einstellungen > Performance > Cache leeren**) und dann den Cache Ihres Browsers (Strg+F5 oder Cmd+R), um sicherzustellen, dass Sie die neueste Version Ihres Shops sehen.

**F: Die Like Box zeigt eine Fehlermeldung an oder lädt keine Inhalte.**
A:

1. **Falsche URL:** Der häufigste Grund ist eine falsche „Facebook Seiten-URL“. Überprüfen Sie diese auf Tippfehler.
2. **Facebook API-Probleme:** Gelegentlich kann es zu vorübergehenden Problemen mit der Facebook-API kommen. Warten Sie eine Weile und überprüfen Sie es erneut.
3. **Theme-Konflikte:** Selten können JavaScript oder CSS Ihres Themes Konflikte verursachen. Wenn die oben genannten Schritte nicht funktionieren, versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um einen Theme-Konflikt auszuschließen.

**F: Kann ich den Text „Seite liken“ in andere Sprachen übersetzen?**
A: Der Text innerhalb der Facebook Like Box selbst (wie „Seite liken“ oder Beitragsinhalte) wird von Facebook gesteuert und passt sich automatisch an die Spracheinstellungen des Benutzers auf Facebook an. Die Back-Office-Einstellungen des Moduls sind über **International > Übersetzungen** in PrestaShop übersetzbar.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die mit dem Modul Facebook Like Box Free arbeiten.

### 4.1 Architekturübersicht

Das Modul `Facebook Like Box Free` ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, das Facebook Seiten-Plugin (ehemals Like Box) mithilfe des offiziellen Facebook JavaScript SDK einzubetten. Es folgt einer grundlegenden PrestaShop-Modulstruktur und nutzt die `Module`-Klasse für Installation, Deinstallation und Konfiguration. Seine Kernfunktionalität dreht sich um die Anzeige des Facebook-Widgets über ein Smarty-Template, das in verschiedene Front-Office-Positionen eingehängt ist. Es sind keine benutzerdefinierten Datenbanktabellen oder komplexen ObjectModels beteiligt; alle Konfigurationen werden in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik ist in der Hauptmoduldatei (`likeboxfree.php`) gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/`. Die gesamte Modullogik befindet sich in der Hauptdatei `likeboxfree.php`.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien in `views/js/`.
Das Facebook JavaScript SDK wird dynamisch vom Modul-Template geladen, wenn die Einstellung `lbf_includeapp` aktiviert ist. Dies wird durch das eigene Skript von Facebook und nicht durch ein benutzerdefiniertes Modulskript gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`likeboxfree/css.css`**
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Wichtige UI-Komponenten und Container, die es stylt:** Diese Datei bietet grundlegendes Styling für den Wrapper um die Facebook Like Box, um sicherzustellen, dass sie sich sauber in das PrestaShop-Layout integriert, insbesondere für Spalten-Hooks. Sie kann Regeln für Polsterung, Ränder oder grundlegende Responsivität enthalten.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler können den generierten HTML-Code überprüfen, um das Wrapper-Element (z.B. ein `div` mit einer bestimmten ID oder Klasse, die vom Modul generiert wird) zu finden und dessen Stile in der `custom.css` oder `theme.css` ihres Themes zu überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - **`likeboxfree/rightcolumn.tpl`**
    - **Eingehängt in:** `displayHome`, `displayFooter`, `displayRightColumn`, `displayLeftColumn` (abhängig von der Konfiguration `likeboxfree_position`).
    - **Visuelle Blockausgabe:** Dieses Template ist für das Rendern der HTML-Struktur verantwortlich, die das Facebook Seiten-Plugin einbettet. Es generiert dynamisch das `div`-Element mit der Klasse `fb-page` und Datenattributen (`data-href`, `data-width`, `data-height` usw.) basierend auf den Konfigurationseinstellungen des Moduls. Es enthält auch den notwendigen JavaScript-Snippet zur Initialisierung des Facebook SDK und zum Parsen des Plugins.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die mit `likeboxfree_` oder `lbf_` beginnen.

  - `ps_configuration`-Einträge:
    - `likeboxfree_position`: Speichert die gewählte Hook-Position (z.B. `displayRightColumn`).
    - `lbf_width`: Breite der Like Box.
    - `lbf_height`: Höhe der Like Box.
    - `lbf_hide_cover`: Boolean (0/1) zum Ausblenden des Titelbilds.
    - `lbf_show_facepile`: Boolean (0/1) zum Anzeigen von Profilbildern.
    - `lbf_show_posts`: Boolean (0/1) zum Anzeigen von Beiträgen.
    - `lbf_hide_cta`: Boolean (0/1) zum Ausblenden des Call-to-Action-Buttons.
    - `lbf_small_header`: Boolean (0/1) für einen kleinen Header.
    - `lbf_url`: Die Facebook Seiten-URL.
    - `lbf_includeapp`: Boolean (0/1) zum Einbinden des Facebook SDK.
    - (Legacy-/ungenutzte Schlüssel können auch aus älteren Versionen existieren, aber die oben genannten sind aktiv).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHome` | Rendert Inhalte auf der Startseite. | Zeigt die Facebook Like Box im Hauptinhaltsbereich der Startseite an, falls konfiguriert. |
| `displayFooter` | Rendert Inhalte in der Fußzeile des Shops. | Zeigt die Facebook Like Box am unteren Rand jeder Seite an, falls konfiguriert. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste. | Zeigt die Facebook Like Box in der rechten Spalte der Seiten an, falls konfiguriert. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste. | Zeigt die Facebook Like Box in der linken Spalte der Seiten an, falls konfiguriert. |

Die `hookDisplay*`-Methoden des Moduls überprüfen den Konfigurationswert `likeboxfree_position` und rendern das Template `rightcolumn.tpl` nur, wenn der aktuelle Hook mit der konfigurierten Position übereinstimmt.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Facebook Like Box Free“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
