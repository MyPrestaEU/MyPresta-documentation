---
title: "Social tabs slider - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Social tabs slider von MyPresta.eu."
sidebar:
  label: "Social tabs slider - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Social tabs slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/social-tabs-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/social-tabs-slider/)
>
> ---


# Social tabs slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und gewährleisten eine ordnungsgemäße Kommunikation mit Social-Media-APIs.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptbildschirm, auf dem Sie alle Optionen für Ihren Social tabs slider einrichten.

#### Allgemeine Einstellungen

- **Vorlage:**

  - **Was diese Einstellung bewirkt:** Hiermit können Sie den visuellen Stil und das Design Ihrer sozialen Tabs auswählen. Das Modul wird mit mehreren vorgefertigten Vorlagen geliefert.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf Vorlage 1, 2, 3 usw. eingestellt:* Das Aussehen der sozialen Symbole, das Tab-Design und möglicherweise der Animationsstil ändern sich in Ihrem Front Office.
  - **Empfohlener Wert:** Experimentieren Sie, um diejenige zu finden, die am besten zum Thema Ihres Shops passt.
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop ein minimalistisches Design hat, könnten Sie eine Vorlage mit sauberen, flachen Symbolen wählen. Wenn Sie einen lebhafteren Look bevorzugen, könnte eine andere Vorlage farbenfrohe, glänzende Symbole bieten.
- **Position:**

  - **Was diese Einstellung bewirkt:** Bestimmt, wo der Social tabs slider auf Ihrer Website erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Links“ eingestellt:* Der Slider wird an der linken Seite des Browserfensters fixiert.
    - *Wenn auf „Rechts“ eingestellt:* Der Slider wird an der rechten Seite des Browserfensters fixiert.
  - **Empfohlener Wert:** „Links“ oder „Rechts“, je nach Layout Ihres Themes und wo es weniger Interferenzen mit anderen Elementen verursacht.
  - **Händlerszenario / Beispiel:** Wenn Ihr Theme eine linke Seitenleiste hat, könnten Sie „Rechts“ wählen, um Unordnung zu vermeiden. Wenn Ihr Theme breit und zentriert ist, könnten sowohl „Links“ als auch „Rechts“ gut funktionieren.
- **Letzter Tab standardmäßig geöffnet:**

  - **Was diese Einstellung bewirkt:** Steuert, ob einer der sozialen Tabs automatisch geöffnet werden soll, wenn ein Besucher Ihre Seite zum ersten Mal aufruft.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „JA“ eingestellt:* Der letzte soziale Tab, der von einem früheren Besucher geöffnet wurde (oder ein Standard-Tab, wenn keine Historie vorhanden ist), gleitet automatisch heraus, wenn ein neuer Besucher ankommt.
    - *Wenn auf „NEIN“ eingestellt:* Alle sozialen Tabs bleiben geschlossen, bis der Besucher aktiv auf einen klickt oder darüber fährt.
  - **Empfohlener Wert:** „NEIN“, um potenziell störende Besucher mit einem automatisch öffnenden Tab zu vermeiden.
  - **Händlerszenario / Beispiel:** Sie könnten es vorübergehend auf „JA“ setzen, wenn Sie eine spezielle Kampagne in einem sozialen Netzwerk durchführen und sofortige Aufmerksamkeit darauf lenken möchten, aber im Allgemeinen bietet „NEIN“ eine bessere Benutzererfahrung.

#### Facebook Like Box Einstellungen

- **Facebook Like Box anzeigen:**

  - **Was diese Einstellung bewirkt:** Schaltet die Sichtbarkeit des Facebook-Tabs und seiner eingebetteten Like Box um.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der Facebook-Tab erscheint im Slider, und wenn er geöffnet wird, zeigt er Ihre Facebook-Fanpage Like Box an.
    - *Wenn deaktiviert (NEIN):* Der Facebook-Tab wird nicht im Slider angezeigt.
  - **Empfohlener Wert:** „JA“, wenn Sie eine aktive Facebook-Seite haben, die Sie bewerben möchten.
  - **Händlerszenario / Beispiel:** Wenn Facebook ein primärer Kanal für Kundeninteraktion und Marketing ist, sollten Sie dies unbedingt aktivieren.
- **Facebook Like Box Höhe:**

  - **Was diese Einstellung bewirkt:** Legt die vertikale Größe des Inhaltsbereichs der Facebook Like Box fest, wenn der Tab geöffnet ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf einen höheren Wert eingestellt (z. B. 500px):* Mehr Inhalte (Beiträge, Gesichter) von Ihrer Facebook-Seite werden innerhalb des Tabs sichtbar sein.
    - *Wenn auf einen niedrigeren Wert eingestellt (z. B. 200px):* Weniger Inhalte werden sichtbar sein, was bei einem langen Feed ein Scrollen erfordert.
  - **Empfohlener Wert:** Beginnen Sie mit `280px` und passen Sie ihn an, je nachdem, wie viel Inhalt Sie anzeigen möchten und wie es auf Ihrer Website aussieht.
  - **Händlerszenario / Beispiel:** Wenn Sie häufig posten und möchten, dass Besucher mehr von Ihrer jüngsten Aktivität sehen, erhöhen Sie die Höhe.
- **Facebook Like Box Farbschema:**

  - **Was diese Einstellung bewirkt:** Ändert das Farbschema der Facebook Like Box selbst (nicht das Tab-Symbol).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Hell“ eingestellt:* Der Hintergrund und der Text der Like Box verwenden hellere Farben.
    - *Wenn auf „Dunkel“ eingestellt:* Der Hintergrund und der Text der Like Box verwenden dunklere Farben.
  - **Empfohlener Wert:** Wählen Sie „Hell“ oder „Dunkel“, um am besten zum Gesamtdesign Ihres Shops zu passen.
  - **Händlerszenario / Beispiel:** Wenn Ihre Website einen dunklen Hintergrund hat, könnte ein „Dunkles“ Farbschema für die Like Box visuell besser integriert werden.
- **Facebook Like Box Gesichter anzeigen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Profilbilder von Personen, die Ihre Seite mögen, in der Like Box angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Eine Reihe von Profilbildern der Fans Ihrer Seite wird angezeigt.
    - *Wenn deaktiviert (NEIN):* Die Profilbilder werden nicht angezeigt.
  - **Empfohlener Wert:** „JA“, da dies ein Element des Social Proofs hinzufügt und zeigt, dass echte Menschen Ihre Seite mögen.
  - **Händlerszenario / Beispiel:** Das Anzeigen von Gesichtern kann andere dazu ermutigen, Ihre Seite zu liken, da es Popularität demonstriert.
- **Facebook Like Box Rahmenfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des Rahmens um die Facebook Like Box fest.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf eine bestimmte Farbe eingestellt (z. B. #CCCCCC):* Der Rahmen erscheint in dieser Farbe.
  - **Empfohlener Wert:** Eine Farbe, die das Design Ihrer Website ergänzt, oder transparent/unsichtbar, wenn Sie dies bevorzugen.
  - **Händlerszenario / Beispiel:** Sie könnten die Primärfarbe Ihrer Marke für den Rahmen verwenden, um das Branding zu verstärken.
- **Facebook Like Box Stream anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob Ihre neuesten Facebook-Beiträge (der „Stream“) innerhalb der Like Box angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Ihre neuesten Facebook-Beiträge werden im Tab sichtbar sein.
    - *Wenn deaktiviert (NEIN):* Nur der „Gefällt mir“-Button und möglicherweise Gesichter werden angezeigt, ohne den Beitrags-Stream.
  - **Empfohlener Wert:** „JA“, um frische Inhalte bereitzustellen und das Engagement zu fördern.
  - **Händlerszenario / Beispiel:** Wenn Sie regelmäßig Nachrichten, Aktionen oder Produktaktualisierungen auf Facebook teilen, hält das Anzeigen des Streams die Besucher auf dem Laufenden.
- **Facebook Like Box Header anzeigen:**

  - **Was diese Einstellung bewirkt:** Schaltet die Sichtbarkeit des Headers „Finde uns auf Facebook“ oben in der Like Box um.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der Header wird angezeigt.
    - *Wenn deaktiviert (NEIN):* Der Header wird ausgeblendet, wodurch die Like Box kompakter wird.
  - **Empfohlener Wert:** „JA“ zur Klarheit, oder „NEIN“, wenn Sie ein saubereres Aussehen wünschen und davon ausgehen, dass Benutzer verstehen, dass es sich um Facebook handelt.
  - **Händlerszenario / Beispiel:** Wenn der Platz begrenzt ist, kann das Ausblenden des Headers vertikalen Raum sparen.
- **Facebook Fanpage URL:**

  - **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung für Facebook. Sie müssen die vollständige URL Ihrer Facebook-Fanpage eingeben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Der Facebook-Tab zeigt die Like Box für Ihre angegebene Seite an.
    - *Bei falscher oder leerer Eingabe:* Der Facebook-Tab wird möglicherweise nicht korrekt angezeigt oder zeigt einen Fehler an.
  - **Empfohlener Wert:** Ihre exakte Facebook-Fanpage-URL (z. B. `https://www.facebook.com/MyPresta`).
  - **Händlerszenario / Beispiel:** Kopieren Sie die URL direkt aus Ihrem Browser, wenn Sie Ihre Facebook-Seite anzeigen, um die Genauigkeit sicherzustellen.

#### Google+ Einstellungen

- **Google+ Folgen anzeigen:**

  - **Was diese Einstellung bewirkt:** Schaltet die Sichtbarkeit des Google+-Tabs und seiner eingebetteten Folgen-Schaltfläche/Profil um.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der Google+-Tab erscheint im Slider.
    - *Wenn deaktiviert (NEIN):* Der Google+-Tab wird nicht angezeigt.
  - **Empfohlener Wert:** „JA“, wenn Sie Google+ aktiv nutzen (obwohl seine Nutzung zurückgegangen ist, könnte es für einige Nischen immer noch relevant sein).
  - **Händlerszenario / Beispiel:** Wenn Ihr Unternehmen eine starke Präsenz auf Google My Business oder spezifische lokale SEO-Strategien mit Google+ hat, kann dies von Vorteil sein.
- **Google+ Profil-ID:**

  - **Was diese Einstellung bewirkt:** Sie müssen Ihre Google+ Profil-ID (eine numerische Zeichenfolge) angeben, damit das Modul das richtige Profil anzeigt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Der Google+-Tab zeigt die Folgen-Schaltfläche/das Profil für Ihre angegebene ID an.
    - *Bei falscher oder leerer Eingabe:* Der Google+-Tab wird möglicherweise nicht korrekt angezeigt.
  - **Empfohlener Wert:** Ihre Google+ Profil-ID.
  - **Händlerszenario / Beispiel:** Finden Sie Ihre Google+ ID, indem Sie zu Ihrer Google+-Profilseite navigieren und die URL betrachten (es ist normalerweise eine lange Zahlenfolge).

#### Twitter Einstellungen

- **Twitter Benutzer-Timeline anzeigen:**

  - **Was diese Einstellung bewirkt:** Schaltet die Sichtbarkeit des Twitter-Tabs und seines eingebetteten Benutzer-Timeline-Widgets um.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der Twitter-Tab erscheint im Slider und zeigt Ihre neuesten Tweets an.
    - *Wenn deaktiviert (NEIN):* Der Twitter-Tab wird nicht angezeigt.
  - **Empfohlener Wert:** „JA“, wenn Sie ein aktives Twitter-Konto für Ihr Unternehmen haben.
  - **Händlerszenario / Beispiel:** Wenn Sie Twitter für den Kundenservice, Ankündigungen oder Blitzverkäufe nutzen, ist dies eine großartige Möglichkeit, Besucher auf dem Laufenden zu halten.
- **Twitter Benutzername:**

  - **Was diese Einstellung bewirkt:** Gibt das Twitter-Konto an, dessen Timeline angezeigt werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe (z. B. MyPresta):* Der Twitter-Tab zeigt Tweets von diesem Benutzernamen an.
    - *Bei falscher oder leerer Eingabe:* Der Twitter-Tab wird möglicherweise nicht korrekt angezeigt.
  - **Empfohlener Wert:** Ihr Twitter-Benutzername (ohne das „@“-Symbol).
  - **Händlerszenario / Beispiel:** Geben Sie `MyPresta` ein, wenn Ihr Twitter-Handle `@MyPresta` ist.
- **Twitter Widget-ID:**

  - **Was diese Einstellung bewirkt:** Dies ist eine eindeutige ID, die von Twitter generiert wird, wenn Sie ein eingebettetes Timeline-Widget erstellen. Sie ist entscheidend für die Funktion des Widgets.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Die Twitter-Timeline wird geladen und korrekt angezeigt.
    - *Bei falscher oder leerer Eingabe:* Der Twitter-Tab zeigt wahrscheinlich einen Fehler an oder bleibt leer.
  - **Empfohlener Wert:** Ihre Twitter Widget-ID.
  - **Händlerszenario / Beispiel:** Um diese zu erhalten, gehen Sie zu [Twitter Publish](https://publish.twitter.com/), wählen Sie „Eingebettete Timeline“, geben Sie Ihre Profil-URL ein und kopieren Sie die `data-widget-id` aus dem generierten Code.

#### YouTube Einstellungen

- **YouTube-Konto anzeigen:**

  - **Was diese Einstellung bewirkt:** Schaltet die Sichtbarkeit des YouTube-Tabs und seines eingebetteten Kanal-/Benutzer-Feeds um.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der YouTube-Tab erscheint im Slider.
    - *Wenn deaktiviert (NEIN):* Der YouTube-Tab wird nicht angezeigt.
  - **Empfohlener Wert:** „JA“, wenn Sie einen YouTube-Kanal mit Produktvideos, Tutorials oder Marken-Inhalten haben.
  - **Händlerszenario / Beispiel:** Wenn Sie Produkte verkaufen, die von Videodemonstrationen profitieren, ist dies eine hervorragende Möglichkeit, diese in Ihrem Shop zu präsentieren.
- **YouTube Benutzername:**

  - **Was diese Einstellung bewirkt:** Gibt den YouTube-Kanal oder Benutzer an, dessen Videos angezeigt werden sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Der YouTube-Tab zeigt Inhalte von diesem Kanal/Benutzer an.
    - *Bei falscher oder leerer Eingabe:* Der YouTube-Tab wird möglicherweise nicht korrekt angezeigt.
  - **Empfohlener Wert:** Der benutzerdefinierte URL-Name oder der alte Benutzername Ihres YouTube-Kanals.
  - **Händlerszenario / Beispiel:** Wenn die URL Ihres YouTube-Kanals `youtube.com/user/MyPrestaVideos` lautet, wäre Ihr Benutzername `MyPrestaVideos`. Wenn es `youtube.com/c/MyPresta` ist, müssen Sie möglicherweise den alten Benutzernamen oder die Kanal-ID finden.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Vorlage** | (Wählen Sie die beste Passform) | Ändert den visuellen Stil der sozialen Tabs. |
| | **Position** | Rechts | Bestimmt, ob die Tabs auf der linken oder rechten Seite des Browsers erscheinen. |
| | **Letzter Tab standardmäßig geöffnet** | NEIN | Steuert, ob ein Tab beim Laden der Seite automatisch geöffnet wird. |
| | **Facebook Like Box anzeigen** | JA | Zeigt/versteckt den Facebook-Tab. |
| | **Facebook Like Box Höhe** | 280px | Legt die Höhe des Facebook-Inhaltsbereichs fest. |
| | **Facebook Like Box Farbschema** | Hell | Ändert das Farbschema der Facebook Like Box. |
| | **Facebook Like Box Gesichter anzeigen** | JA | Zeigt Profilbilder von Fans an. |
| | **Facebook Like Box Rahmenfarbe** | (leer/transparent) | Legt die Rahmenfarbe der Like Box fest. |
| | **Facebook Like Box Stream anzeigen** | JA | Zeigt aktuelle Facebook-Beiträge an. |
| | **Facebook Like Box Header anzeigen** | JA | Zeigt/versteckt den Header „Finde uns auf Facebook“. |
| | **Facebook Fanpage URL** | (Ihre Facebook-URL) | **KRITISCH:** URL Ihrer Facebook-Fanpage. |
| | **Google+ Folgen anzeigen** | NEIN | Zeigt/versteckt den Google+-Tab. |
| | **Google+ Profil-ID** | (Ihre Google+ ID) | **KRITISCH:** Ihre numerische Google+ Profil-ID. |
| | **Twitter Benutzer-Timeline anzeigen** | JA | Zeigt/versteckt den Twitter-Tab. |
| | **Twitter Benutzername** | (Ihr Twitter-Handle) | **KRITISCH:** Ihr Twitter-Benutzername (z. B. `MyPresta`). |
| | **Twitter Widget-ID** | (Ihre Twitter Widget-ID) | **KRITISCH:** Eindeutige ID für Ihr Twitter-Timeline-Widget. |
| | **YouTube-Konto anzeigen** | JA | Zeigt/versteckt den YouTube-Tab. |
| | **YouTube Benutzername** | (Ihr YouTube-Benutzername) | **KRITISCH:** Der Benutzername oder die alte ID Ihres YouTube-Kanals. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die sozialen Tabs erscheinen nicht in meinem Shop, oder es werden nur einige davon angezeigt.**
**A1:**

- **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Social tabs slider“ installiert und aktiviert ist.
- **Konfiguration überprüfen:** Gehen Sie zur Konfigurationsseite des Moduls. Stellen Sie sicher, dass „Facebook Like Box anzeigen“, „Google+ Folgen anzeigen“ usw. für die Tabs, die Sie anzeigen möchten, auf „JA“ eingestellt sind.
- **Korrekte IDs/URLs:** Überprüfen Sie nochmals, ob Ihre Facebook Fanpage URL, Google+ Profil-ID, Twitter Benutzername/Widget-ID und YouTube Benutzername *genau* wie erforderlich eingegeben wurden. Ein einziger Tippfehler verhindert das Laden des Tabs.
- **Theme-Kompatibilität:** Einige stark angepasste Themes können Probleme mit Modul-Hooks haben. Versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob die Tabs erscheinen. Wenn ja, benötigt Ihr Theme möglicherweise geringfügige Anpassungen.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Modulinhalte angezeigt werden.

**F2: Mein Facebook-/Twitter-/YouTube-Tab zeigt einen Fehler an oder ist leer, wenn er geöffnet wird.**
**A2:**

- **Falsche IDs/URLs:** Dies ist der häufigste Grund. Überprüfen Sie jedes einzelne Zeichen Ihrer Facebook Fanpage URL, Google+ Profil-ID, Twitter Benutzernamen, Twitter Widget-ID und YouTube Benutzernamen erneut. Selbst ein fehlender Schrägstrich oder ein zusätzliches Leerzeichen kann Probleme verursachen.
- **API-Änderungen:** Social-Media-Plattformen aktualisieren gelegentlich ihre APIs oder Einbettungscodes. Stellen Sie sicher, dass Ihre Modulversion von MyPresta.eu auf dem neuesten Stand ist.
- **Datenschutzeinstellungen:** Stellen Sie sicher, dass Ihre Social-Media-Seiten/Profile öffentlich und zugänglich sind. Wenn sie auf privat eingestellt sind, kann das Modul deren Inhalte nicht anzeigen.
- **Netzwerkprobleme:** Deaktivieren Sie vorübergehend alle Werbeblocker oder Browser-Erweiterungen, die Social-Media-Widgets stören könnten.

**F3: Die sozialen Tabs sehen auf meinem Mobilgerät seltsam oder falsch ausgerichtet aus.**
**A3:**

- **Theme-Responsivität:** Obwohl das Modul responsiv gestaltet ist, kann sein Erscheinungsbild durch die allgemeine Responsivität Ihres PrestaShop-Themes beeinflusst werden.
- **CSS-Konflikte:** Das CSS Ihres Themes könnte das Styling des Moduls überschreiben. Wenn Sie einen Webmaster haben, kann dieser die Elemente mit den Browser-Entwicklertools untersuchen, um Konflikte zu identifizieren.
- **Modulvorlage:** Versuchen Sie, in der Modulkonfiguration zu einer anderen „Vorlage“ zu wechseln, um zu sehen, ob sich eine besser an mobile Geräte anpasst.
- **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F4: Wie erhalte ich meine Twitter Widget-ID?**
**A4:**

1. Gehen Sie zu [Twitter Publish](https://publish.twitter.com/).
2. Wählen Sie „Eingebettete Timeline“.
3. Geben Sie die vollständige URL Ihres Twitter-Profils ein (z. B. `https://twitter.com/MyPresta`).
4. Klicken Sie auf den Pfeil und wählen Sie dann „Eingebettete Timeline“.
5. Twitter generiert einen Code. Suchen Sie in diesem Code nach `data-widget-id="IHRE_WIDGET_ID_HIER"`. Kopieren Sie nur die numerische ID.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Social tabs slider“ ist ein klassisches PrestaShop-Modul, das als einzelne PHP-Datei (`socialslider.php`) gemäß der PrestaShop-Modulstruktur implementiert ist. Es nutzt das Hook-System von PrestaShop, um seine CSS-, JavaScript- und HTML-Inhalte in das Front Office einzufügen. Die Konfiguration wird über die Methode `getContent()` in der Hauptmodulklasse verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden. Das Modul verwendet externe JavaScript-Bibliotheken (jscolor) und benutzerdefinierte Skripte, um die Schiebeanimation und das Laden von Social-Media-Widgets zu handhaben.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik ist in der Hauptmoduldatei gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder erweitert `ObjectModel`. Die gesamte Kernlogik befindet sich in der Klasse `Socialslider` in `socialslider.php`. Konfigurationswerte werden direkt in der Tabelle `ps_configuration` mithilfe von `Configuration::get()` und `Configuration::updateValue()` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien zur Verwaltung seiner Funktionalität:

- `socialslider/jscolor/jscolor.js`
  - **Umfang:** Back-Office (wird in `getContent()` für die Farbauswahl verwendet).
  - **Verantwortlichkeit:** Bietet eine JavaScript-Farbauswahlfunktion für Eingabefelder, speziell für die Facebook-Rahmenfarbeinstellung.
- `socialslider/left.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Enthält die JavaScript-Logik für die Schiebeanimation und Tab-Interaktion, wenn der Slider auf der **linken** Seite des Bildschirms positioniert ist. Es handhabt das Öffnen/Schließen von Tabs, das dynamische Laden von Social-Media-Inhalten und möglicherweise die Verwaltung von Cookies für die Funktion „zuletzt geöffneter Tab“.
- `socialslider/right.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Enthält die JavaScript-Logik für die Schiebeanimation und Tab-Interaktion, wenn der Slider auf der **rechten** Seite des Bildschirms positioniert ist. Ähnlich wie `left.js`, aber an die rechte Positionierung angepasst.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul verwendet einen vorlagenbasierten Ansatz für sein Styling, mit separaten CSS-Dateien für jede Vorlage und Position.

- `socialslider/templates/1/css/left.css`
  - **Umfang:** Front-Office (für Vorlage 1, linke Position).
  - **Verantwortlichkeit:** Definiert die visuellen Stile für die sozialen Tabs, Symbole und den Slider-Container, wenn Vorlage 1 ausgewählt ist und der Slider links positioniert ist.
  - **Wichtige Selektoren:** `.socialslider_left`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
- `socialslider/templates/1/css/right.css`
  - **Umfang:** Front-Office (für Vorlage 1, rechte Position).
  - **Verantwortlichkeit:** Definiert die visuellen Stile für die sozialen Tabs, Symbole und den Slider-Container, wenn Vorlage 1 ausgewählt ist und der Slider rechts positioniert ist.
  - **Wichtige Selektoren:** `.socialslider_right`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
- `socialslider/templates/2/css/left.css`
  - **Umfang:** Front-Office (für Vorlage 2, linke Position).
  - **Verantwortlichkeit:** Styling für Vorlage 2, linke Position.
- `socialslider/templates/2/css/right.css`
  - **Umfang:** Front-Office (für Vorlage 2, rechte Position).
  - **Verantwortlichkeit:** Styling für Vorlage 2, rechte Position.
- `socialslider/templates/3/css/left.css`
  - **Umfang:** Front-Office (für Vorlage 3, linke Position).
  - **Verantwortlichkeit:** Styling für Vorlage 3, linke Position.
- `socialslider/templates/3/css/right.css`
  - **Umfang:** Front-Office (für Vorlage 3, rechte Position).
  - **Verantwortlichkeit:** Styling für Vorlage 3, rechte Position.
- `socialslider/templates/4/css/left.css`
  - **Umfang:** Front-Office (für Vorlage 4, linke Position).
  - **Verantwortlichkeit:** Styling für Vorlage 4, linke Position.
- `socialslider/templates/4/css/right.css`
  - **Umfang:** Front-Office (für Vorlage 4, rechte Position).
  - **Verantwortlichkeit:** Styling für Vorlage 4, rechte Position.
- `socialslider/templates/5/css/left.css`
  - **Umfang:** Front-Office (für Vorlage 5, linke Position).
  - **Verantwortlichkeit:** Styling für Vorlage 5, linke Position.
- `socialslider/templates/5/css/right.css`
  - **Umfang:** Front-Office (für Vorlage 5, rechte Position).
  - **Verantwortlichkeit:** Styling für Vorlage 5, rechte Position.
- `socialslider/templates/6/css/left.css`
  - **Umfang:** Front-Office (für Vorlage 6, linke Position).
  - **Verantwortlichkeit:** Styling für Vorlage 6, linke Position.
- `socialslider/templates/6/css/right.css`
  - **Umfang:** Front-Office (für Vorlage 6, rechte Position).
  - **Verantwortlichkeit:** Styling für Vorlage 6, rechte Position.

Entwickler können diese Stile in der `custom.css` ihres Themes oder durch Erstellen eines Child-Themes überschreiben.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Das Modul verwendet Smarty-Vorlagen zum Rendern seiner Front-Office-Inhalte und für das Back-Office-Konfigurationsformular.

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `socialslider/header.tpl`
    - **Hook:** `displayHeader`
    - **Ausgabe:** Diese Vorlage ist dafür verantwortlich, die notwendigen CSS- und JavaScript-Dateien dynamisch basierend auf der Modulkonfiguration einzubinden (z. B. Laden von `left.js` oder `right.js` und dem korrekten vorlagenspezifischen CSS). Sie enthält auch die Facebook-, Twitter- und Google+-SDKs/Widgets, falls aktiviert.
  - `socialslider/top.tpl`
    - **Hook:** `displayTop`
    - **Ausgabe:** Dies ist die Hauptvorlage, die die HTML-Struktur des Social Tabs Sliders selbst rendert. Sie generiert die `div`-Elemente für den Slider-Container, einzelne Tabs (Facebook, Google+, Twitter, YouTube) und deren jeweilige Inhaltsbereiche und füllt diese mit Konfigurationswerten.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen werden in der Standard-PrestaShop-Tabelle `ps_configuration` gespeichert.

  - `ps_configuration` (oder `_configuration` mit Ihrem Präfix): Speichert Schlüssel-Wert-Paare für Moduleinstellungen, z. B. `SS_TEMPLATE`, `SS_POSITION`, `SS_FCB_FANPAGEURL`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt die CSS- und JavaScript-Dateien des Moduls sowie die SDKs/Widget-Skripte der Social-Media-Plattformen (Facebook SDK, Twitter Widget-Skript, Google+-Skript) ein. |
| `displayTop` | Typischerweise ganz oben im Inhaltsbereich, unterhalb des Haupt-Headers. | Rendert die Haupt-HTML-Struktur des Social Tabs Sliders (den festen Container, einzelne Tabs und deren Inhaltsbereiche). |
| `header` | (Alias für `displayHeader` in einigen PrestaShop-Versionen oder für ältere Themes verwendet) | Gleiches wie `displayHeader`, gewährleistet Kompatibilität für das Einfügen von Assets. |

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und Entwickler-Support für das Modul „Social tabs slider“ verweisen wir auf Ihr MyPresta.eu-Kundenkonto. Sie können die neuesten Versionen herunterladen und direkt über Ihren Bestellverlauf auf Support-Ressourcen zugreifen.
