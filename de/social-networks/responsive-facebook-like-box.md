---
title: "Responsive Facebook Like Box – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Responsive Facebook Like Box von MyPresta.eu."
sidebar:
  label: "Responsive Facebook Like Box – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Responsive Facebook Like Box auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/responsive-facebook-like-box.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/responsive-facebook-like-box/)
>
> ---


# Responsive Facebook Like Box

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung verfügbar. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Einrichtung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für Ihr Modul „Responsive Facebook Like Box“. Hier legen Sie fest, wie Ihre Facebook Like Box in Ihrem Shop aussieht und sich verhält.

- **Menüpfad:** Back Office > Module > Modul-Manager > Suchen Sie nach „Responsive Facebook Like Box“ > Klicken Sie auf „Konfigurieren“.

#### Einstellungen & Optionen:

1.  **Facebook Fanpage URL:**

    - **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie teilt dem Modul mit, welche spezifische Facebook-Seite in der Like Box angezeigt werden soll.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf die URL Ihrer Facebook-Seite eingestellt (z.B. `https://www.facebook.com/MyPresta.eu`):* Das Modul zeigt die Like Box für diese spezifische Seite an.
      - *Wenn leer gelassen oder auf eine ungültige URL eingestellt:* Die Like Box wird nicht korrekt oder gar nicht angezeigt.
    - **Empfohlener Wert:** Ihre offizielle Facebook Fanpage URL.
    - **Händlerszenario / Beispiel:** Wenn die Facebook-Seite Ihres Shops `https://www.facebook.com/MyAwesomeStore` ist, würden Sie diese URL hier eingeben.
2.  **Breite der Like Box (in Pixeln):**

    - **Was diese Einstellung bewirkt:** Steuert die horizontale Größe der Facebook Like Box.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf einen bestimmten Pixelwert eingestellt (z.B. `340`):* Die Like Box versucht, in dieser genauen Breite zu rendern.
      - *Wenn auf einen kleineren Wert eingestellt:* Die Box wird schmaler, wodurch möglicherweise Inhalte ausgeblendet oder Text kleiner werden.
      - *Wenn auf einen größeren Wert eingestellt:* Die Box wird breiter und nimmt mehr horizontalen Platz ein.
    - **Empfohlener Wert:** `340` (Dies ist ein gängiger Standard für das Facebook Page Plugin und funktioniert oft gut in Seitenleisten). Für Abschnitte mit voller Breite können Sie einen größeren Wert verwenden oder es der automatischen Anpassung überlassen, wenn das Thema dies zulässt.
    - **Händlerszenario / Beispiel:** Wenn Ihre rechte Spalte 300px breit ist, würde eine Einstellung auf 280-300px sicherstellen, dass sie perfekt passt, ohne zu überlaufen.
3.  **Höhe der Like Box (in Pixeln):**

    - **Was diese Einstellung bewirkt:** Steuert die vertikale Größe der Facebook Like Box.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf einen bestimmten Pixelwert eingestellt (z.B. `500`):* Die Like Box wird in dieser genauen Höhe gerendert.
      - *Wenn auf einen kleineren Wert eingestellt:* Die Box wird kürzer, wodurch möglicherweise gescrollt werden muss, um alle Inhalte (wie aktuelle Beiträge oder Freundesgesichter) zu sehen.
      - *Wenn auf einen größeren Wert eingestellt:* Die Box wird höher und nimmt mehr vertikalen Platz ein.
    - **Empfohlener Wert:** `500` (Ein gutes Gleichgewicht, um Inhalte anzuzeigen, ohne übermäßig lang zu sein). Passen Sie dies an, je nachdem, wie viele Inhalte Sie anzeigen möchten (z.B. mehr Beiträge = mehr Höhe).
    - **Händlerszenario / Beispiel:** Wenn Sie 3-4 aktuelle Beiträge von Ihrer Facebook-Seite anzeigen möchten, benötigen Sie möglicherweise eine Höhe von 500px oder mehr. Wenn Sie nur den „Gefällt mir“-Button und das Titelbild anzeigen möchten, könnte eine kleinere Höhe wie 200px ausreichen.
4.  **Gesichter von Freunden anzeigen:**

    - **Was diese Einstellung bewirkt:** Legt fest, ob die Like Box Profilbilder von Personen anzeigt, die Ihre Seite gelikt haben und auch mit dem aktuellen Betrachter befreundet sind.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Die Like Box zeigt Gesichter an und fügt ein Element des sozialen Beweises hinzu, da Besucher sehen, dass ihre Freunde mit Ihrer Marke verbunden sind.
      - *Wenn deaktiviert (NEIN):* Gesichter werden nicht angezeigt, was zu einem saubereren, kompakteren Aussehen führt.
    - **Empfohlener Wert:** JA (Nutzt sozialen Beweis, um mehr Likes zu fördern).
    - **Händlerszenario / Beispiel:** Das Aktivieren dieser Option kann das Vertrauen und Engagement erhöhen, da Kunden eher einer Marke folgen, die ihre Freunde bereits mögen.
5.  **Stream anzeigen (Beiträge von Ihrer Seite):**

    - **Was diese Einstellung bewirkt:** Steuert, ob aktuelle Beiträge von Ihrer Facebook-Seite in der Like Box angezeigt werden.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Ihre neuesten Facebook-Beiträge erscheinen in der Box, bieten frische Inhalte und fördern die Interaktion.
      - *Wenn deaktiviert (NEIN):* Nur das Titelbild, der Seitenname und der „Gefällt mir“-Button sind sichtbar, wodurch die Box kompakter wird.
    - **Empfohlener Wert:** JA (Hält den Inhalt frisch und zeigt Besuchern, welche Art von Inhalten sie erwarten können, wenn sie Ihnen folgen).
    - **Händlerszenario / Beispiel:** Wenn Sie regelmäßig Updates, Aktionen oder interessante Inhalte auf Facebook posten, hält das Anzeigen des Streams Ihre Website-Besucher mit Ihren Social-Media-Aktivitäten in Kontakt.
6.  **Header anzeigen:**

    - **Was diese Einstellung bewirkt:** Legt fest, ob ein kleiner „Facebook“-Header oben in der Like Box angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Ein kleiner Header mit dem Facebook-Logo und Text wird angezeigt.
      - *Wenn deaktiviert (NEIN):* Der Header wird entfernt, was ein etwas integrierteres Aussehen ergibt, aber möglicherweise weniger klar macht, dass es sich um ein Facebook-Widget handelt.
    - **Empfohlener Wert:** JA (Bietet klare Markenbildung und Kontext).
    - **Händlerszenario / Beispiel:** Das Beibehalten des Headers hilft Benutzern, es sofort als Facebook-Widget zu erkennen.
7.  **Kleinen Header verwenden:**

    - **Was diese Einstellung bewirkt:** Wenn „Header anzeigen“ aktiviert ist, steuert diese Option, ob eine kleinere Version des Headers verwendet wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Der Header wird kompakter.
      - *Wenn deaktiviert (NEIN):* Der Standard-Header wird verwendet.
    - **Empfohlener Wert:** JA (Sieht oft besser in Seitenleisten oder kleineren Bereichen aus).
    - **Händlerszenario / Beispiel:** Nützlich, wenn Sie die Like Box in einer schmalen Spalte platzieren, wo der Platz begrenzt ist.
8.  **An Containerbreite anpassen:**

    - **Was diese Einstellung bewirkt:** Dies ist eine entscheidende Responsivitäts-Einstellung. Sie weist die Facebook Like Box an, ihre Breite automatisch an die Breite des Containers anzupassen, in dem sie platziert ist (z.B. die Spalte Ihres Themas).
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Die Like Box wird dynamisch in der Größe angepasst, wodurch sie wirklich responsiv ist und Überlaufprobleme auf verschiedenen Bildschirmgrößen verhindert werden. Die Einstellung „Breite der Like Box“ kann überschrieben oder als Maximum verwendet werden.
      - *Wenn deaktiviert (NEIN):* Die Like Box versucht, die Einstellung „Breite der Like Box“ beizubehalten, was potenziell zu Layout-Problemen auf kleineren Bildschirmen führen kann, wenn die eingestellte Breite zu groß ist.
    - **Empfohlener Wert:** JA (Unerlässlich für ein responsives Design und eine gute Benutzererfahrung auf Mobilgeräten).
    - **Händlerszenario / Beispiel:** Wenn Sie die Like Box in einer responsiven Seitenleiste platzieren, stellt das Aktivieren dieser Option sicher, dass sie immer perfekt passt, unabhängig vom Gerät, das Ihr Kunde verwendet.
9.  **Hintergrundfarbe (Hex-Code):**

    - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine benutzerdefinierte Hintergrundfarbe für die Like Box mithilfe eines hexadezimalen Farbcodes festzulegen (z.B. `#FFFFFF` für Weiß).
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf einen bestimmten Hex-Code eingestellt:* Der Hintergrund der Like Box ändert sich zu dieser Farbe.
      - *Wenn leer gelassen oder auf einen ungültigen Code eingestellt:* Die Standard-Facebook-Hintergrundfarbe (normalerweise hellgrau oder weiß) wird verwendet.
    - **Empfohlener Wert:** Passen Sie die Hintergrundfarbe Ihres Themas an oder lassen Sie sie für den Standardwert leer.
    - **Händlerszenario / Beispiel:** Wenn Ihr Shop ein dunkles Thema hat, könnten Sie dies auf ein dunkles Grau einstellen, um es besser zu integrieren.
10. **Platzierungs-Hook:**

    - **Was diese Einstellung bewirkt:** Legt fest, wo in Ihrem PrestaShop-Store die Facebook Like Box angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn auf `displayHeader` eingestellt:* Die Like Box erscheint im Header-Bereich Ihres Shops.
      - *Wenn auf `displayLeftColumn` oder `displayRightColumn` eingestellt:* Die Like Box erscheint in der jeweiligen Seitenleiste.
      - *Wenn auf `displayFooter` eingestellt:* Die Like Box erscheint im Footer-Bereich.
      - *Wenn auf `displayProductButtons` oder einen ähnlichen Produktseiten-Hook eingestellt:* Die Like Box erscheint auf Produktseiten.
    - **Empfohlener Wert:** `displayRightColumn` oder `displayLeftColumn` (Üblich und effektiv für Sichtbarkeit, ohne aufdringlich zu sein).
    - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass die Like Box auf den meisten Seiten sichtbar ist, ohne den primären Header-Bereich einzunehmen, ist die Platzierung in einer Spalte eine gute Wahl. Wenn Sie möchten, dass sie sehr prominent ist, könnte der Header bevorzugt werden.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Facebook Fanpage URL | Ihre Facebook-Seiten-URL | Verknüpft das Modul mit Ihrer spezifischen Facebook-Seite. |
| Modulkonfiguration | Breite der Like Box (px) | 340 | Legt die horizontale Größe fest. |
| Modulkonfiguration | Höhe der Like Box (px) | 500 | Legt die vertikale Größe fest. |
| Modulkonfiguration | Gesichter von Freunden anzeigen | JA | Zeigt Profilbilder von Freunden als sozialen Beweis an. |
| Modulkonfiguration | Stream anzeigen (Beiträge) | JA | Zeigt aktuelle Beiträge von Ihrer Facebook-Seite an. |
| Modulkonfiguration | Header anzeigen | JA | Zeigt den „Facebook“-Header an. |
| Modulkonfiguration | Kleinen Header verwenden | JA | Verwendet einen kompakten Header, wenn „Header anzeigen“ aktiviert ist. |
| Modulkonfiguration | An Containerbreite anpassen | JA | Macht die Like Box responsiv zum übergeordneten Container. |
| Modulkonfiguration | Hintergrundfarbe (Hex) | (Leer lassen für Standard) | Passt die Hintergrundfarbe der Box an. |
| Modulkonfiguration | Platzierungs-Hook | displayRightColumn / displayLeftColumn | Legt fest, wo die Box in Ihrem Shop erscheint. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Facebook Like Box wird in meinem Shop nicht angezeigt. Was soll ich tun?**

-   **A:** Überprüfen Sie zunächst, ob Sie die korrekte und vollständige **„Facebook Fanpage URL“** in der Modulkonfiguration eingegeben haben. Stellen Sie sicher, dass sie mit `https://` beginnt.
-   **A:** Überprüfen Sie, ob der von Ihnen gewählte **„Platzierungs-Hook“** tatsächlich aktiv ist und von Ihrem Thema angezeigt wird. Einige Themen zeigen möglicherweise bestimmte Hooks (z.B. linke Spalte) nicht auf allen Seiten an. Versuchen Sie, zu einem anderen Hook wie `displayFooter` zu wechseln, um zu sehen, ob er dort erscheint.
-   **A:** Leeren Sie Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Leeren Sie auch den Cache Ihres Browsers.
-   **A:** Stellen Sie sicher, dass das Modul aktiviert ist. Suchen Sie unter **Module > Modul-Manager** nach dem Modul und vergewissern Sie sich, dass es nicht deaktiviert ist.

**F2: Die Like Box sieht zu breit/schmal oder zu hoch/kurz aus.**

-   **A:** Passen Sie die Einstellungen **„Breite der Like Box“** und **„Höhe der Like Box“** in der Modulkonfiguration an.
-   **A:** Wenn Sie möchten, dass sie sich automatisch an die Spalte Ihres Themas anpasst, stellen Sie sicher, dass **„An Containerbreite anpassen“** auf JA gesetzt ist. Dies ist besonders wichtig für responsive Themes.

**F3: Warum werden aktuelle Beiträge oder Gesichter von Freunden nicht in der Like Box angezeigt?**

-   **A:** Überprüfen Sie die Modulkonfigurationseinstellungen:
    -   Stellen Sie sicher, dass **„Stream anzeigen (Beiträge von Ihrer Seite)“** auf JA gesetzt ist, um Beiträge anzuzeigen.
    -   Stellen Sie sicher, dass **„Gesichter von Freunden anzeigen“** auf JA gesetzt ist, um Freundesgesichter anzuzeigen.
-   **A:** Die Facebook-API hat manchmal Einschränkungen oder Verzögerungen. Stellen Sie sicher, dass Ihre Facebook-Seite aktuelle öffentliche Beiträge hat.

**F4: Die von mir eingestellte Hintergrundfarbe wird nicht angezeigt.**

-   **A:** Stellen Sie sicher, dass Sie einen gültigen hexadezimalen Farbcode eingegeben haben (z.B. `#RRGGBB`). Wenn Sie ein benutzerdefiniertes Thema verwenden, kann es zu widersprüchlichen CSS-Stilen kommen. Möglicherweise müssen Sie einen Webentwickler beauftragen, das Element zu überprüfen und eine spezifischere CSS-Regel anzuwenden, falls die Einstellung des Moduls überschrieben wird.

**F5: Das Modul funktioniert auf dem Desktop, sieht aber auf Mobilgeräten seltsam aus.**

-   **A:** Dies liegt fast immer an der Einstellung **„An Containerbreite anpassen“**. Stellen Sie sicher, dass diese auf JA gesetzt ist. Dies weist das Facebook-Widget an, responsiv zu sein. Überprüfen Sie auch die Responsivität Ihres Themas; wenn der Container, in dem sich das Modul befindet, nicht responsiv ist, kann sich das Modul nicht perfekt anpassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Responsive Facebook Like Box“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul `Responsive Facebook Like Box` (`likebox/ar.php`) ist ein Standard-PrestaShop-Modul, das, wo anwendbar, dem MVC-Muster für seine Konfiguration folgt. Es nutzt hauptsächlich das Hook-System von PrestaShop, um das Facebook Page Plugin (Like Box) in verschiedene Front-Office-Bereiche zu injizieren. Die Kernfunktionalität basiert auf dem JavaScript SDK des Facebook Page Plugins, das dynamisch geladen und basierend auf den Moduleinstellungen konfiguriert wird. Die Konfiguration wird über `Configuration::get()` und `Configuration::updateValue()` innerhalb der Hauptmodulklasse verwaltet.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt in der Methode `getContent()` der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Die gesamte Logik ist in der Hauptmoduldatei `ar.php` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**

    -   **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite).
    -   **Zweck:** Dies ist eine JavaScript-Bibliothek eines Drittanbieters für einen Farbwähler. Sie wird auf der Konfigurationsseite des Moduls verwendet, um eine benutzerfreundliche Oberfläche zur Auswahl der Einstellung „Hintergrundfarbe“ bereitzustellen.
    -   **Funktionalität:** Sie wandelt ein Standard-Texteingabefeld in einen interaktiven Farbwähler um, der es dem Administrator ermöglicht, visuell einen hexadezimalen Farbcode auszuwählen.
-   **`likebox/script.js`**

    -   **Geltungsbereich:** Front-Office.
    -   **Zweck:** Dieses Skript ist für das dynamische Laden des Facebook JavaScript SDK und die Initialisierung des Facebook Page Plugins (Like Box) im Front-Office verantwortlich.
    -   **Funktionalität:**
        -   Es prüft typischerweise das Vorhandensein des Facebook SDK (`FB`) und lädt es, falls es noch nicht vorhanden ist.
        -   Anschließend ruft es `FB.XFBML.parse()` oder ähnliche Methoden auf, um das `div`-Element mit der Klasse `fb-page` zu rendern, wobei die Attribute (data-href, data-width usw.) basierend auf der Modulkonfiguration angewendet werden.
        -   Es stellt sicher, dass die Like Box korrekt gerendert wird, nachdem das DOM bereit ist.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`likebox/css/css.css`**

    -   **Geltungsbereich:** Front-Office.
    -   **Zweck:** Enthält allgemeine Styling-Regeln für den Facebook Like Box-Container und potenziell einige responsive Anpassungen.
    -   **Wichtige Selektoren:** Zielt wahrscheinlich auf das Haupt-Container-`div` ab, das das Facebook Page Plugin umschließt, um sicherzustellen, dass es in das Layout des Themas passt und grundlegende Responsivität handhabt. Entwickler können diese Stile bei Bedarf in der `custom.css` oder `theme.css` ihres Themas überschreiben.
-   **`likebox/css.css`**

    -   **Geltungsbereich:** Front-Office.
    -   **Zweck:** Ähnlich wie `likebox/css/css.css` enthält diese Datei wahrscheinlich zusätzliche oder alternative Styling-Regeln für die Front-Office-Anzeige der Like Box. Sie könnte Regeln für spezifische Platzierungen oder kleinere visuelle Anpassungen enthalten.
    -   **Wichtige Selektoren:** Zielt auf den Facebook Like Box-Container und verwandte Elemente ab.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **`likebox/header.tpl`**

    -   **Geltungsbereich:** Front-Office.
    -   **Hook:** `displayHeader` (oder ähnlicher Header-bezogener Hook).
    -   **Zweck:** Dieses Template ist für die Ausgabe der HTML-Struktur der Facebook Like Box verantwortlich, wenn das Modul so konfiguriert ist, dass es im Header angezeigt wird. Es enthält das `div`-Element mit der Klasse `fb-page` und `data-*`-Attributen, die das Facebook SDK zum Rendern des Plugins verwendet.
    -   **Variablen:** Greift auf Konfigurationsvariablen (z.B. `{$facebook_page_url}`, `{$width}`, `{$height}`, `{$show_faces}` usw.) zu, die von der PHP-Logik des Moduls übergeben werden.
-   **`likebox/rightcolumn.tpl`**

    -   **Geltungsbereich:** Front-Office.
    -   **Hook:** `displayRightColumn` (oder `displayLeftColumn`, `displayFooter`, `displayProductButtons` usw., je nach gewähltem Hook).
    -   **Zweck:** Dieses Template ist für die Ausgabe der HTML-Struktur der Facebook Like Box verantwortlich, wenn das Modul so konfiguriert ist, dass es in einer Spalte oder anderen Inhaltsbereichen angezeigt wird. Es enthält das `div`-Element mit der Klasse `fb-page` und `data-*`-Attributen.
    -   **Variablen:** Ähnlich wie `header.tpl` greift es auf Konfigurationsvariablen zu, um die Attribute des Plugins dynamisch festzulegen.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    -   Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` (oder `_configuration`-Präfix) unter Schlüsseln wie `RESPONSIVE_FB_LIKEBOX_URL`, `RESPONSIVE_FB_LIKEBOX_WIDTH` usw. gespeichert.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert im `<head>`-Bereich der Seite oder am Anfang des `<body>`. | Injiziert den HTML-Code der Facebook Like Box und potenziell das Initialisierungsskript des Facebook SDK. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste des Shops. | Injiziert den HTML-Code der Facebook Like Box in die linke Spalte. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste des Shops. | Injiziert den HTML-Code der Facebook Like Box in die rechte Spalte. |
| `displayFooter` | Rendert Inhalte im Footer-Bereich des Shops. | Injiziert den HTML-Code der Facebook Like Box in den Footer. |
| `displayProductButtons` (oder ähnlicher Produktseiten-Hook) | Rendert Inhalte auf der Produktseite, oft in der Nähe des In-den-Warenkorb-Buttons oder der Beschreibung. | Injiziert den HTML-Code der Facebook Like Box auf Produktseiten. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (JS/CSS) festlegt. | Registriert die CSS- und JavaScript-Dateien des Moduls für die Front-Office-Anzeige. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (JS/CSS) festlegt. | Registriert das `jscolor.js`-Skript und potenziell admin-spezifisches CSS für die Konfigurationsseite des Moduls. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, neue Versionen und offiziellen Support für das Modul „Responsive Facebook Like Box“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
