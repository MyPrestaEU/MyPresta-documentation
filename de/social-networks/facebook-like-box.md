---
title: "Facebook Like Box - Händlerhandbuch & Konfigurationsanleitung"
description: ""
sidebar:
  label: "Facebook Like Box - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Like Box auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-like-box.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-like-box/)
>
> ---


# Facebook Like Box

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst und jedes Modul, das mit externen APIs wie Facebook interagiert, erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für Ihr Facebook Like Box-Modul. Hier definieren Sie, wie Ihre Like Box in Ihrem Shop aussieht und sich verhält.

**Bildschirmname & Menüpfad:** Back Office > Module > Modul-Manager > Facebook Like Box > Konfigurieren

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Facebook Seiten-URL** | Dies ist der direkte Link zu Ihrer offiziellen Facebook-Seite. | *Wenn festgelegt:* Die Like Box zeigt Inhalte von dieser spezifischen Facebook-Seite an. *Wenn leer:* Das Modul funktioniert nicht korrekt, da es nicht weiß, welche Seite angezeigt werden soll. | Ihre Facebook Seiten-URL (z.B. `https://www.facebook.com/myprestaeu`) | Sie möchten Ihre Haupt-Facebook-Seite bewerben. |
| **App ID (Facebook)** | Ihre Facebook App ID, erforderlich für einige erweiterte Funktionen und API-Integrationen. | *Wenn festgelegt:* Ermöglicht dem Modul die Interaktion mit der Facebook Graph API über Ihre Anwendung. *Wenn leer:* Kann zu "App nicht konfiguriert"-Fehlern führen, wenn das Modul API-Zugriff benötigt. | Ihre Facebook App ID (z.B. `123456789012345`) | Sie müssen einen "App nicht konfiguriert"-Fehler beheben oder erweiterte Facebook API-Funktionen aktivieren. |
| **Breite** | Steuert die Breite der Facebook Like Box in Pixeln. | *Wenn auf einen bestimmten Wert (z.B. 280) eingestellt:* Die Like Box behält diese exakte Breite bei. *Wenn leer gelassen oder auf 0 gesetzt:* Die Like Box versucht, responsiv zu sein und ihre Breite automatisch an ihren Container anzupassen. | Leer lassen für automatische Erkennung (responsives Verhalten) oder einen spezifischen Wert wie `280` festlegen, wenn Sie eine feste Breite benötigen. | Sie möchten, dass die Like Box perfekt in eine schmale Spalte passt, daher stellen Sie sie auf `280` ein. |
| **Höhe** | Steuert die Höhe der Facebook Like Box in Pixeln. | *Wenn auf einen bestimmten Wert (z.B. 500) eingestellt:* Die Like Box behält diese exakte Höhe bei. *Wenn leer gelassen oder auf 0 gesetzt:* Die Like Box versucht, responsiv zu sein und ihre Höhe automatisch anzupassen. | Leer lassen für automatische Erkennung (responsives Verhalten) oder einen spezifischen Wert wie `500` festlegen, wenn Sie mehr vom Beitragsstream anzeigen möchten. | Sie möchten mehr aktuelle Beiträge von Ihrer Facebook-Seite anzeigen, daher erhöhen Sie die Höhe auf `500`. |
| **Gesichter anzeigen** | Legt fest, ob die Profilbilder von Personen, die Ihre Seite gelikt haben, angezeigt werden. | *Wenn aktiviert (JA):* Kleine Profilbilder einiger Ihrer Facebook-Fans erscheinen unter dem Like-Button und fügen sozialen Beweis hinzu. *Wenn deaktiviert (NEIN):* Nur der Like-Button und die Seiteninformationen werden angezeigt, ohne einzelne Gesichter. | JA | Sie möchten zeigen, dass echte Menschen Ihre Seite mögen, um andere zum Beitritt zu ermutigen. |
| **Stream anzeigen** | Steuert, ob aktuelle Beiträge von Ihrer Facebook-Seite innerhalb der Like Box angezeigt werden. | *Wenn aktiviert (JA):* Ihre neuesten Facebook-Beiträge scrollen innerhalb der Like Box und liefern frische Inhalte. *Wenn deaktiviert (NEIN):* Nur das Seiten-Titelbild, das Profil und der Like-Button sind sichtbar, wodurch die Box kompakter wird. | JA | Sie posten häufig Updates auf Facebook und möchten diese direkt in Ihrem Shop teilen. |
| **Header anzeigen** | Steuert, ob der "Facebook"-Header oben in der Like Box angezeigt wird. | *Wenn aktiviert (JA):* Ein kleiner "Facebook"-Titel erscheint oben im Widget. *Wenn deaktiviert (NEIN):* Der Header wird ausgeblendet, wodurch das Widget sauberer und integrierter aussieht. | NEIN | Sie bevorzugen ein minimalistisches Aussehen für die Like Box und benötigen den expliziten "Facebook"-Header nicht. |
| **Kleiner Header** | Verwendet eine kleinere Version des Headers. | *Wenn aktiviert (JA):* Der Header wird kompakter. *Wenn deaktiviert (NEIN):* Die Standard-Headergröße wird verwendet. | NEIN | Sie möchten vertikalen Platz in Ihrem Layout sparen. |
| **Titelbild ausblenden** | Blendet das Titelbild Ihrer Facebook-Seite aus. | *Wenn aktiviert (JA):* Nur das Profilbild und der Name Ihrer Seite sind sichtbar, wodurch das Widget kompakter wird. *Wenn deaktiviert (NEIN):* Das Titelbild Ihrer Facebook-Seite wird oben im Widget angezeigt. | NEIN | Sie haben sehr wenig Platz und möchten den Like-Button und die Beiträge gegenüber dem Titelbild priorisieren. |
| **An Containerbreite anpassen** | Ermöglicht der Like Box, ihre Breite automatisch an den übergeordneten Container anzupassen, in dem sie platziert ist. | *Wenn aktiviert (JA):* Das Widget passt seine Größe an, um die verfügbare Breite auszufüllen, wodurch es responsiv wird. *Wenn deaktiviert (NEIN):* Das Widget hält sich an die angegebene `Breite`-Einstellung, was möglicherweise zu Überlauf oder leerem Raum führt. | JA | Sie möchten, dass die Like Box auf allen Geräten und Bildschirmgrößen ohne manuelle Anpassungen gut aussieht. |
| **Benutzerdefiniertes CSS** | Ermöglicht das Hinzufügen benutzerdefinierter CSS-Regeln, um die Like Box weiter zu gestalten. | *Wenn mit CSS-Code gefüllt:* Ihre benutzerdefinierten Stile werden angewendet und überschreiben Standardstile. *Wenn leer:* Das Modul verwendet seine Standardstile oder die Standardstile von Facebook. | Leer lassen, es sei denn, Sie haben spezifische Styling-Anforderungen. | Sie möchten die Schriftgröße oder -farbe des Textes in der Like Box ändern, um sie an das Thema Ihrer Marke anzupassen. |
| **Hook zum Anzeigen des Moduls** | Wählt aus, wo in Ihrem Shop die Like Box erscheinen soll. | *Wenn ein Hook ausgewählt ist:* Das Modul rendert seinen Inhalt an dieser spezifischen Position (z.B. `displayRightColumn`, `displayFooter`). *Wenn kein Hook ausgewählt ist:* Das Modul ist in Ihrem Front Office nicht sichtbar. | `displayRightColumn` oder `displayLeftColumn` sind üblich, aber wählen Sie basierend auf dem Layout Ihres Themes. | Sie möchten, dass die Like Box an der Seite Ihrer Produktlisten sichtbar ist, daher wählen Sie `displayRightColumn`. |
| **Hintergrundfarbe** | Legt die Hintergrundfarbe der Like Box fest. | *Wenn eine Farbe ausgewählt ist:* Die Like Box hat diese Hintergrundfarbe. *Wenn leer gelassen:* Die Like Box erbt typischerweise die Hintergrundfarbe ihres übergeordneten Containers oder verwendet die Standardfarbe von Facebook. | Leer lassen oder an die Hintergrundfarbe Ihres Themes anpassen. | Ihr Theme hat einen dunklen Hintergrund, und Sie möchten, dass die Like Box sich einfügt, daher stellen Sie eine dunkle Hintergrundfarbe ein. |
| **Rahmenfarbe** | Legt die Farbe des Rahmens um die Like Box fest. | *Wenn eine Farbe ausgewählt ist:* Die Like Box hat einen Rahmen dieser Farbe. *Wenn leer gelassen:* Die Like Box hat typischerweise keinen Rahmen oder einen Standard-Facebook-Rahmen. | Leer lassen oder an die Rahmenfarben Ihres Themes anpassen. | Sie möchten einen subtilen grauen Rahmen um die Like Box, um sie von anderen Inhalten abzugrenzen. |

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Facebook Seiten-URL | Ihre Facebook Seiten-URL | Verknüpft das Widget mit Ihrer spezifischen Facebook-Seite. |
| Modulkonfiguration | App ID (Facebook) | Leer (falls nicht erforderlich) | Ihre Facebook App ID für die API-Integration. |
| Modulkonfiguration | Breite | Leer (Responsiv) | Steuert die Widget-Breite; leer für automatische Anpassung. |
| Modulkonfiguration | Höhe | Leer (Responsiv) | Steuert die Widget-Höhe; leer für automatische Anpassung. |
| Modulkonfiguration | Gesichter anzeigen | JA | Zeigt Profilbilder von Likern als sozialen Beweis an. |
| Modulkonfiguration | Stream anzeigen | JA | Zeigt aktuelle Beiträge von Ihrer Facebook-Seite an. |
| Modulkonfiguration | Header anzeigen | NEIN | Blendet den "Facebook"-Titel für ein saubereres Aussehen aus. |
| Modulkonfiguration | Kleiner Header | NEIN | Verwendet einen kleineren Header, wenn `Header anzeigen` auf JA steht. |
| Modulkonfiguration | Titelbild ausblenden | NEIN | Zeigt das Titelbild Ihrer Facebook-Seite an. |
| Modulkonfiguration | An Containerbreite anpassen | JA | Stellt sicher, dass das Widget auf seinen übergeordneten Container reagiert. |
| Modulkonfiguration | Benutzerdefiniertes CSS | Leer | Ermöglicht erweiterte Gestaltung mit benutzerdefinierten CSS-Regeln. |
| Modulkonfiguration | Hook zum Anzeigen des Moduls | `displayRightColumn` (oder relevante Spalte) | Bestimmt, wo das Modul in Ihrem Shop erscheint. |
| Modulkonfiguration | Hintergrundfarbe | Leer | Legt die Hintergrundfarbe des Widgets fest. |
| Modulkonfiguration | Rahmenfarbe | Leer | Legt die Rahmenfarbe des Widgets fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Facebook Like Box wird in meinem Shop nicht angezeigt. Was soll ich tun?**
A1:

-   **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul "Facebook Like Box" installiert und aktiviert ist.
-   **Hook-Auswahl überprüfen:** Stellen Sie in der Modulkonfiguration sicher, dass Sie einen "Hook zum Anzeigen des Moduls" ausgewählt haben (z.B. `displayRightColumn`, `displayFooter`). Wenn Ihr Theme den ausgewählten Hook nicht rendert, wird er nicht angezeigt. Versuchen Sie einen anderen gängigen Hook.
-   **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf "Cache leeren" (oder "Smarty-Cache leeren" in älteren Versionen). Manchmal verhindert der PrestaShop-Cache, dass neue Module sofort angezeigt werden.
-   **Facebook Seiten-URL:** Überprüfen Sie nochmals, ob die "Facebook Seiten-URL" in der Modulkonfiguration korrekt und zugänglich ist.

**F2: Die Like Box sieht zu breit/schmal aus oder passt nicht richtig zu meinem Theme.**
A2:

-   **Responsive Einstellungen:** Stellen Sie in der Modulkonfiguration sicher, dass "An Containerbreite anpassen" auf JA gesetzt ist und lassen Sie die Felder "Breite" und "Höhe" leer. Dadurch kann Facebook die Responsivität verwalten.
-   **Theme-Konflikte:** Das CSS Ihres Themes könnte die Stile des Moduls überschreiben. Wenn Sie mit CSS vertraut sind, verwenden Sie die Entwicklertools Ihres Browsers (F12), um das Element zu überprüfen und zu sehen, welche CSS-Regeln angewendet werden.
-   **Benutzerdefiniertes CSS:** Verwenden Sie das Feld "Benutzerdefiniertes CSS" in der Modulkonfiguration, um spezifische Regeln hinzuzufügen, um die Größe oder das Aussehen bei Bedarf anzupassen. Zum Beispiel: `.fb_iframe_widget { max-width: 100% !important; }`.

**F3: Die Like Box zeigt einen Fehler an oder lädt keine Inhalte von meiner Facebook-Seite.**
A3:

-   **Korrekte URL:** Überprüfen Sie, ob die "Facebook Seiten-URL" absolut korrekt ist und auf eine öffentliche Facebook-Seite (nicht auf ein persönliches Profil oder eine Gruppe) verweist.
-   **Facebook API-Probleme:** Gelegentlich kann es zu vorübergehenden Problemen mit der Facebook-API kommen. Warten Sie eine Weile und versuchen Sie es erneut.
-   **Seitenbeschränkungen:** Stellen Sie sicher, dass Ihre Facebook-Seite keine Länder- oder Altersbeschränkungen aufweist, die das Laden des Widgets für alle Besucher verhindern könnten.

:::caution
\*\*„App nicht konfiguriert“-Fehler (Modulversion 1.8 und höher)\*\*
Wenn Sie einen „App nicht konfiguriert“-Fehler erhalten, insbesondere bei Modulversion 1.8 oder höher, die Facebook Graph API v18.0 unterstützt:
1.  \*\*Geben Sie Ihre Facebook App ID ein:\*\* Stellen Sie sicher, dass Sie Ihre Facebook App ID korrekt in das Konfigurationsfeld des Moduls eingegeben haben.
2.  \*\*Überprüfen Sie die Domain-Einstellungen auf Facebook:\*\* Melden Sie sich bei Ihrem Facebook Developer-Konto ([developers.facebook.com](https://developers.facebook.com/)) an. Navigieren Sie zu den Einstellungen Ihrer App und bestätigen Sie, dass die Domain Ihres Shops (z.B. `ihrshop.de`) in den App-Einstellungen korrekt hinzugefügt und verifiziert ist.
:::

**F4: Kann ich mehrere Facebook Like Boxes auf verschiedenen Seiten haben?**
A4: Dieses Modul ist so konzipiert, dass es eine global konfigurierte Facebook Like Box anzeigt. Wenn Sie mehrere, unterschiedliche Like Boxes benötigen (z.B. für verschiedene Facebook-Seiten oder mit unterschiedlichen Einstellungen), müssten Sie das Modul typischerweise mehrmals installieren (falls vom PrestaShop-Modulsystem unterstützt, was bei Single-Instanz-Modulen selten ist) oder benutzerdefinierten Code verwenden. Für dieses spezifische Modul ist es im Allgemeinen eine Instanz, eine Konfiguration.

**F5: Wie übersetze ich den Text innerhalb der Like Box (z.B. "Seite liken")?**
A5: Der Text innerhalb der Facebook Like Box selbst (wie "Seite liken", "Folgen", "Teilen") wird von Facebook basierend auf den Spracheinstellungen des Benutzerbrowsers und der eigenen Lokalisierung von Facebook gesteuert. Dieses Modul übersetzt diese Elemente nicht direkt. Jeder Text *um* die Like Box herum, den Sie in Ihrem Theme oder anderen Modulen hinzufügen, wäre über das PrestaShop-Übersetzungssystem übersetzbar.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Facebook Like Box Modul (`likebox`) ist ein Standard-PrestaShop-Modul, das einem grundlegenden MVC-Muster folgt. Es verwendet hauptsächlich die `Module`-Klasse für Installation, Deinstallation und Konfigurationsverwaltung. Die Kernfunktionalität besteht darin, ein Smarty-Template zu rendern, das das Facebook Page Plugin (ehemals Like Box) mithilfe des offiziellen JavaScript SDK von Facebook einbettet. Konfigurationseinstellungen werden in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Die gesamte Logik ist in der Hauptmoduldatei (`likebox/ar.php`) enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**

    *   **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite)
    *   **Zweck:** Dies ist eine JavaScript-Bibliothek eines Drittanbieters, die eine Farbauswahlfunktion bereitstellt. Sie wird auf der Konfigurationsseite des Moduls verwendet, um dem Händler die visuelle Auswahl der Einstellungen für "Hintergrundfarbe" und "Rahmenfarbe" zu ermöglichen.
    *   **Interaktion:** Sie bindet sich an bestimmte Eingabefelder (wahrscheinlich mit einer Klasse wie `jscolor`), um eine Farbauswahlpalette zu öffnen.
-   **`likebox/script.js`**

    *   **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite)
    *   **Zweck:** Dieses Skript verarbeitet die dynamischen Updates und die Live-Vorschaufunktion auf der Konfigurationsseite des Moduls. Es nimmt die Eingabeeinstellungen des Händlers (Facebook Seiten-URL, Breite, Höhe, Gesichter anzeigen usw.) und aktualisiert dynamisch ein `<iframe>` oder einen Vorschaubereich, um zu zeigen, wie die Facebook Like Box aussehen wird.
    *   **Interaktion:**
        *   Lauscht auf `change`- und `keyup`-Ereignisse bei verschiedenen Eingabefeldern (z.B. `#facebook_page_url`, `#width`, `#height`, Checkboxen).
        *   Konstruiert die Parameter der Facebook Page Plugin-URL basierend auf den aktuellen Einstellungen.
        *   Aktualisiert das `src`-Attribut eines Vorschau-`<iframe>` oder generiert dynamisch den Facebook SDK-Einbettungscode, um Änderungen in Echtzeit widerzuspiegeln.
        *   Verwendet wahrscheinlich `jscolor.js`, um Farbwerte für Hintergrund und Rahmen zu erhalten.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`likebox/css.css`**

    *   **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite)
    *   **Zweck:** Bietet Styling für das Konfigurationsformular des Moduls im PrestaShop Back Office. Dies kann Layoutanpassungen, Styling von Eingabefeldern oder Styling für den Live-Vorschaubereich umfassen.
    *   **Wichtige Selektoren:** Zielt wahrscheinlich auf Elemente innerhalb der `getContent()`-Ausgabe ab, wie Formulargruppen, Labels und den Vorschaubehälter.
-   **`likebox/css/css.css`**

    *   **Geltungsbereich:** Front-Office (Kundenorientierter Shop)
    *   **Zweck:** Bietet minimales Styling für das Facebook Like Box-Widget selbst, hauptsächlich um sicherzustellen, dass es gut in das Layout des Shops integriert ist. Dies kann Standard-Padding, Margins oder grundlegende responsive Anpassungen umfassen.
    *   **Wichtige Selektoren:** Zielt auf das Containerelement ab, in das das Facebook-Widget eingebettet ist (z.B. `.facebook_like_box_container`), und wendet möglicherweise `max-width: 100%` für Responsivität an. Entwickler können diese Stile in der `custom.css` oder `theme.css` ihres Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Die Templates des Moduls befinden sich direkt im Stammverzeichnis des Moduls.

-   **`likebox/header.tpl`**

    *   **Geltungsbereich:** Front-Office
    *   **Hook:** `displayHeader`
    *   **Zweck:** Dieses Template ist dafür konzipiert, in `displayHeader` eingehängt zu werden. Seine Hauptaufgabe ist es, das Facebook JavaScript SDK einzubinden, das für die korrekte Darstellung des Facebook Page Plugins notwendig ist. Es enthält auch das `div`-Element, in dem die Like Box vom SDK gerendert wird.
    *   **Ausgabe:**

        ```
        <div id="fb-root"></div><script> (function(d, s, id) { var js, fjs = d.getElementsByTagName(s)[0]; if (d.getElementById(id)) return; js = d.createElement(s); js.id = id; js.src = "//connect.facebook.net/en\_US/sdk.js#xfbml=1&version=v2.8&appId={$app\_id}"; // Version might vary, appId added fjs.parentNode.insertBefore(js, fjs); }(document, 'script', 'facebook-jssdk'));</script><div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div></div>
        ```

        (Hinweis: Die tatsächliche Version des SDK und der Datenattribute kann je nach genauer Implementierung des Moduls und den API-Änderungen von Facebook leicht variieren.)
-   **`likebox/rightcolumn.tpl`**

    *   **Geltungsbereich:** Front-Office
    *   **Hook:** `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayProductButtons`, etc. (abhängig von der Modulkonfiguration)
    *   **Zweck:** Dieses Template dient als Wrapper für die Facebook Like Box. Es ist flexibel gestaltet und kann an verschiedenen Positionen eingehängt werden. Es enthält typischerweise das `div`-Element mit der Klasse `fb-page`, das das Facebook SDK in die visuelle Like Box umwandelt.
    *   **Ausgabe:**

        ```
        <div class="block facebook\_like\_box\_container"> <h4>{l s='Follow us on Facebook' mod='likebox'}</h4> <div class="block\_content"> <div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show\_posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div> </div> </div></div>
        ```

        Dieses Template enthält auch den `<h4>`-Titel und die `block_content`-Struktur, die für PrestaShop-Spaltenblöcke üblich sind.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    *   Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    *   Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert, wobei die Schlüssel typischerweise mit `LIKEBOX_` beginnen (z.B. `LIKEBOX_FACEBOOK_PAGE_URL`, `LIKEBOX_WIDTH`, `LIKEBOX_HEIGHT`, `LIKEBOX_APP_ID`, etc.).
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite gerendert. | Wird verwendet, um das Facebook JavaScript SDK und das anfängliche `fb-root`-Div einzubinden, die für die Funktion der Like Box unerlässlich sind. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste. | Zeigt das Facebook Like Box-Widget in der linken Spalte an. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste. | Zeigt das Facebook Like Box-Widget in der rechten Spalte an. |
| `displayFooter` | Rendert Inhalte im Footer-Bereich des Shops. | Zeigt das Facebook Like Box-Widget im Footer an. |
| `displayHome` | Rendert Inhalte auf der Startseite. | Zeigt das Facebook Like Box-Widget auf der Startseite an. |
| `displayProductButtons` | Rendert Inhalte in der Nähe der Produktaktionsschaltflächen auf der Produktseite. | Zeigt das Facebook Like Box-Widget auf Produktseiten an. |
| `displayProductExtraContent` | Rendert zusätzliche Inhalte auf der Produktseite, oft in einem Tab oder unterhalb des Hauptinhalts. | Zeigt das Facebook Like Box-Widget auf Produktseiten an. |
| `displayMyAccountBlock` | Rendert Inhalte im "Mein Konto"-Block des Kunden. | Zeigt das Facebook Like Box-Widget im Kundenkontobereich an (weniger üblich für dieses Modul). |
| `displayMyAccountBlockfooter` | Rendert Inhalte im Footer des "Mein Konto"-Blocks. | Zeigt das Facebook Like Box-Widget im Kundenkontobereich an. |

(Hinweis: Die `install()`-Methode des Moduls registriert diese Hooks, und die `hook<HookName>()`-Methoden in `ar.php` sind für das Rendern von `rightcolumn.tpl` oder `header.tpl` basierend auf dem Hook verantwortlich.)

## 5. Offizieller Support & Updates

Für die neuesten Versionen, Updates und dedizierten Support für das Facebook Like Box Modul, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.
