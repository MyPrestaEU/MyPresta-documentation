---
title: "Instagram Produkt-Tag-Feed - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Instagram Produkt-Tag-Feed' von MyPresta.eu."
sidebar:
  label: "Instagram Produkt-Tag-Feed - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Instagram product tag feed auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/instagram-product-tag-feed.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/instagram-product-tag-feed/)
>
> ---


# Instagram Produkt-Tag-Feed

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die API-Kommunikation erforderlich, die auf modernen Hosting-Umgebungen fast universell verfügbar sind.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Einstellungen des Moduls zuzugreifen, gehen Sie in Ihrem PrestaShop Back Office zu **Module > Modul-Manager**, suchen Sie nach „Instagram Produkt-Tag-Feed“ und klicken Sie auf die Schaltfläche „Konfigurieren“.

Hier finden Sie die Hauptkonfigurationsoptionen, um zu steuern, wie Ihre Instagram-Feeds angezeigt werden.

#### Allgemeine Einstellungen

- **Instagram Access Token:**

  - **Was diese Einstellung bewirkt:** Dies ist ein eindeutiger Code, der Ihrem PrestaShop-Shop die Berechtigung erteilt, auf die öffentlichen Daten Ihres Instagram-Kontos zuzugreifen (wie Fotos, die mit bestimmten Tags verknüpft sind). Sie müssen diesen Token über die Entwicklertools von Instagram oder ein Drittanbieter-Tool generieren, das den Prozess vereinfacht.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Ihr Modul kann Instagram-Fotos abrufen und anzeigen.
    - *Bei falscher oder leerer Eingabe:* Das Modul kann keine Verbindung zu Instagram herstellen, und es werden keine Fotos angezeigt, was zu einem leeren Feed oder einer Fehlermeldung führt.
  - **Empfohlener Wert:** Ihr gültiger Instagram Access Token.
  - **Händlerszenario / Beispiel:** Sie haben gerade Ihr Instagram Business-Konto eingerichtet. Sie müssen den Anweisungen von Instagram folgen (oder ein Hilfstool verwenden), um diesen Token zu erhalten und hier einzufügen. Ohne ihn kann das Modul Ihre Instagram-Fotos nicht „sehen“.
- **Instagram User ID:**

  - **Was diese Einstellung bewirkt:** Dies ist die eindeutige numerische Kennung für Ihr Instagram-Konto. Sie wird oft zusammen mit dem Access Token benötigt, um Daten korrekt abzurufen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Stellt sicher, dass das Modul Daten von Ihrem spezifischen Instagram-Konto abruft.
    - *Bei falscher oder leerer Eingabe:* Kann zu Fehlern beim Abrufen von Daten oder zum Abrufen von Daten vom falschen Konto führen, was zu einem leeren oder falschen Feed führt.
  - **Empfohlener Wert:** Ihre gültige Instagram User ID.
  - **Händlerszenario / Beispiel:** Ähnlich wie beim Access Token erhalten Sie diese ID, wenn Sie Ihren Instagram API-Zugang einrichten. Sie teilt dem Modul mit, *wessen* Instagram-Feed es sich ansehen soll.
- **Anzahl der anzuzeigenden Fotos:**

  - **Was diese Einstellung bewirkt:** Steuert, wie viele Instagram-Fotos in einer einzelnen Feed-Instanz abgerufen und angezeigt werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Bei Einstellung auf eine höhere Zahl (z.B. 10):* Es werden mehr Fotos geladen und potenziell im Feed angezeigt, was ihn reichhaltiger, aber möglicherweise langsamer im Laden macht.
    - *Bei Einstellung auf eine niedrigere Zahl (z.B. 3):* Es werden weniger Fotos angezeigt, was zu einem prägnanteren Feed und schnelleren Ladezeiten führt.
  - **Empfohlener Wert:** Beginnen Sie mit 6-9 Fotos für ein gutes Gleichgewicht zwischen Inhalt und Leistung. Passen Sie dies basierend auf Ihrem Layout und Ihren Seiten-Geschwindigkeitstests an.
  - **Händlerszenario / Beispiel:** Für einen Produktseiten-Tab möchten Sie vielleicht 6 Fotos. Für ein Homepage-Karussell möchten Sie vielleicht 12, um mehr Abwechslung zu bieten, wenn Benutzer scrollen.
- **Auf Startseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Ein einfacher Schalter zum Aktivieren oder Deaktivieren des Instagram-Feeds auf der Startseite Ihres Shops.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul versucht, einen Instagram-Feed auf Ihrer Startseite anzuzeigen (normalerweise über den Hook `displayHome`).
    - *Wenn deaktiviert:* Es wird kein Instagram-Feed auf Ihrer Startseite angezeigt.
  - **Empfohlener Wert:** JA, wenn Sie Ihre Instagram-Inhalte prominent präsentieren möchten. NEIN, wenn Sie eine sauberere Startseite bevorzugen oder Feeds nur auf Produktseiten wünschen.
  - **Händlerszenario / Beispiel:** Sie möchten Ihre neuesten Lifestyle-Aufnahmen auf der Startseite zeigen, um Besucher sofort zu begeistern. Sie würden dies aktivieren.
- **Auf Produktseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Ein einfacher Schalter zum Aktivieren oder Deaktivieren des Instagram-Feeds auf einzelnen Produktseiten.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul versucht, einen produktspezifischen Instagram-Feed auf Ihren Produktseiten anzuzeigen (normalerweise über die Hooks `displayProductTab` oder `displayProductExtraContent`).
    - *Wenn deaktiviert:* Es wird kein Instagram-Feed auf Produktseiten angezeigt.
  - **Empfohlener Wert:** JA, da dies eine der Kernfunktionen des Moduls und ein leistungsstarkes Konversionstool ist.
  - **Händlerszenario / Beispiel:** Sie verkaufen Schuhe und möchten Instagram-Fotos von Personen zeigen, die *dieses spezifische Schuhmodell* tragen, auf dessen Produktseite. Sie würden dies aktivieren.
- **In linker Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Instagram-Feed in der linken Seitenleiste Ihres Shops angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Feed wird in der linken Spalte auf Seiten gerendert, auf denen er eingehängt ist.
    - *Wenn deaktiviert:* Kein Feed in der linken Spalte.
  - **Empfohlener Wert:** NEIN, es sei denn, Sie haben einen sehr spezifischen Designbedarf. Spalten können überladen wirken.
  - **Händlerszenario / Beispiel:** Sie möchten einen kleinen, persistenten Feed, der sichtbar ist, während Kunden Kategorien durchsuchen.
- **In rechter Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Instagram-Feed in der rechten Seitenleiste Ihres Shops angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Feed wird in der rechten Spalte auf Seiten gerendert, auf denen er eingehängt ist.
    - *Wenn deaktiviert:* Kein Feed in der rechten Spalte.
  - **Empfohlener Wert:** NEIN, es sei denn, Sie haben einen sehr spezifischen Designbedarf. Spalten können überladen wirken.
  - **Händlerszenario / Beispiel:** Ähnlich wie bei der linken Spalte, für einen persistenten, kleineren Feed.
- **Im Footer anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Instagram-Feed im Footer-Bereich Ihres Shops angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Feed wird im Footer gerendert.
    - *Wenn deaktiviert:* Kein Feed im Footer.
  - **Empfohlener Wert:** JA, für eine subtile, aber effektive Möglichkeit, Ihr Instagram zu präsentieren. Es ist weniger aufdringlich als Spalten.
  - **Händlerszenario / Beispiel:** Sie möchten einen visuell ansprechenden Bereich am unteren Rand jeder Seite hinzufügen, der Besucher dazu anregt, Ihr Instagram zu erkunden.
- **Im Header (Links) anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Instagram-Feed im linken Teil des Headers Ihres Shops angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Feed wird im linken Bereich des Headers gerendert.
    - *Wenn deaktiviert:* Kein Feed im Header.
  - **Empfohlener Wert:** NEIN, Header sind typischerweise für Navigation und Branding reserviert.
  - **Händlerszenario / Beispiel:** Sehr spezifisches Design, bei dem Sie ein kleines, rotierendes Instagram-Symbol oder ein einzelnes Bild im Header wünschen.
- **Im Header (Rechts) anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Instagram-Feed im rechten Teil des Headers Ihres Shops angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Feed wird im rechten Bereich des Headers gerendert.
    - *Wenn deaktiviert:* Kein Feed im Header.
  - **Empfohlener Wert:** NEIN, Header sind typischerweise für Navigation und Branding reserviert.
  - **Händlerszenario / Beispiel:** Ähnlich wie bei Header (Links).
- **Karussell-Funktion:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert die Karussell-Funktionalität (gleitende Galerie) für die Instagram-Feeds.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Fotos werden in einem horizontalen, scrollbaren Karussell angezeigt, was Platz spart und es Benutzern ermöglicht, viele Bilder einfach zu durchsuchen.
    - *Wenn deaktiviert:* Fotos werden wahrscheinlich in einem statischen Raster oder einer Liste angezeigt, je nach Template.
  - **Empfohlener Wert:** JA, für die meisten Platzierungen (Startseite, Produktseite), da es platzsparend und ansprechend ist.
  - **Händlerszenario / Beispiel:** Sie haben 9 Fotos für ein Produkt, aber nur Platz für 3 gleichzeitig. Durch Aktivieren des Karussells können Kunden durch alle 9 wischen.
- **Fancybox-Funktion:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert den „Fancybox“-Effekt, eine beliebte JavaScript-Bibliothek, die Bilder beim Klicken in einem stilvollen, überlagernden Popup anzeigt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Klicken auf ein Instagram-Foto im Feed öffnet es in einem großen, eleganten Popup-Fenster, sodass Kunden Details anzeigen können, ohne die Seite zu verlassen.
    - *Wenn deaktiviert:* Das Klicken auf ein Bild könnte es direkt in einem neuen Browser-Tab öffnen oder einfach nichts tun, je nach Theme.
  - **Empfohlener Wert:** JA, da es eine viel bessere Benutzererfahrung beim Anzeigen von Bildern bietet.
  - **Händlerszenario / Beispiel:** Ein Kunde sieht ein tolles Outfit auf Instagram in Ihrem Feed. Das Klicken darauf öffnet eine große, klare Ansicht des Fotos, wodurch die Details leichter zu erkennen sind.

#### Produktspezifische Einstellungen (Produkt Back Office Tab)

Nach der Installation des Moduls finden Sie ein neues Feld oder einen neuen Tab, wenn Sie ein Produkt in Ihrem PrestaShop Back Office bearbeiten:

- **Instagram Hashtag (pro Produkt):**
  - **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, einen eindeutigen Instagram-Hashtag für jedes einzelne Produkt festzulegen. Das Modul verwendet diesen Hashtag dann, um relevante Fotos von Ihrem Instagram-Konto abzurufen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn ein Hashtag eingegeben wird (z.B. #meinproduktname):* Der Instagram-Feed auf dieser spezifischen Produktseite zeigt Fotos von Ihrem Instagram-Konto an, die mit `#meinproduktname` getaggt sind.
    - *Wenn leer gelassen:* Es wird kein produktspezifischer Instagram-Feed für dieses Produkt angezeigt, selbst wenn „Auf Produktseite anzeigen“ aktiviert ist.
  - **Empfohlener Wert:** Ein eindeutiger, beschreibender Hashtag für jedes Produkt. Stellen Sie sicher, dass Sie diesen Hashtag konsequent in Ihren Instagram-Posts verwenden.
  - **Händlerszenario / Beispiel:** Für ein Produkt namens „Sommerbrise-Kleid“ könnten Sie `#SommerbriseKleid` oder `#MeineMarkeSommerkleid` eingeben. Wenn Sie dann Fotos dieses Kleides auf Instagram posten, fügen Sie diesen Hashtag hinzu. Das Modul zieht diese Fotos dann auf die Produktseite des Kleides.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfig | Instagram Access Token | Ihr gültiger Token | Verbindet sich mit der Instagram API, um Fotos abzurufen. **KRITISCH.** |
| Modul-Konfig | Instagram User ID | Ihre gültige User ID | Identifiziert Ihr Instagram-Konto für den Datenabruf. |
| Modul-Konfig | Anzahl der anzuzeigenden Fotos | 6-9 | Steuert, wie viele Fotos in einer Feed-Instanz angezeigt werden. |
| Modul-Konfig | Auf Startseite anzeigen | JA | Zeigt einen allgemeinen Feed auf der Startseite Ihres Shops an. |
| Modul-Konfig | Auf Produktseite anzeigen | JA | Zeigt einen produktspezifischen Feed auf Produktseiten an. |
| Modul-Konfig | In linker Spalte anzeigen | NEIN | Zeigt einen Feed in der linken Seitenleiste an. Kann das Layout überladen. |
| Modul-Konfig | In rechter Spalte anzeigen | NEIN | Zeigt einen Feed in der rechten Seitenleiste an. Kann das Layout überladen. |
| Modul-Konfig | Im Footer anzeigen | JA | Zeigt einen Feed im Footer des Shops an. Gut für subtile Promotion. |
| Modul-Konfig | Im Header (Links) anzeigen | NEIN | Zeigt einen Feed im linken Header an. Generell nicht empfohlen. |
| Modul-Konfig | Im Header (Rechts) anzeigen | NEIN | Zeigt einen Feed im rechten Header an. Generell nicht empfohlen. |
| Modul-Konfig | Karussell-Funktion | JA | Zeigt Fotos in einer gleitenden Galerie an, spart Platz. |
| Modul-Konfig | Fancybox-Funktion | JA | Öffnet Fotos in einem stilvollen Popup für bessere Ansicht. |
| Produktbearbeitungsseite | Instagram Hashtag | Eindeutig pro Produkt | Definiert den Hashtag, um Fotos für *dieses spezifische Produkt* abzurufen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Instagram-Feed zeigt keine Fotos an. Was soll ich tun?**
A:

1. **Überprüfen Sie Ihren Instagram Access Token und Ihre User ID:** Dies sind die häufigsten Ursachen. Stellen Sie sicher, dass sie korrekt in der Modulkonfiguration eingegeben und noch gültig sind. Instagram-Tokens können ablaufen, daher müssen Sie sie möglicherweise neu generieren.
2. **Hashtags überprüfen:** Stellen Sie für Produktseiten sicher, dass das Feld „Instagram Hashtag“ für das spezifische Produkt ausgefüllt ist und dass Sie tatsächlich Posts auf Instagram mit genau diesem Hashtag haben.
3. **Öffentliches Konto:** Stellen Sie sicher, dass Ihr Instagram-Konto öffentlich ist. Das Modul kann keine Fotos von privaten Konten abrufen.
4. **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und leeren Sie den Smarty-Cache (und optional alle Caches). Manchmal verhindern alte zwischengespeicherte Daten, dass neue Inhalte angezeigt werden.
5. **API-Limits überprüfen:** Instagram hat API-Ratenbegrenzungen. Wenn Sie zu häufig abrufen oder eine sehr große Anzahl von Produkten haben, könnten Sie diese Limits vorübergehend erreichen.

**F: Die Bilder werden angezeigt, aber sie sehen seltsam aus oder zerstören das Layout meines Themes.**
A:

1. **Theme-Konflikte:** Ihr benutzerdefiniertes PrestaShop-Theme könnte widersprüchliche CSS-Stile haben. Dies ist ein häufiges Problem bei Drittanbieter-Modulen.
2. **Modul-CSS:** Das Modul enthält sein eigenes CSS (`instagramfeed/css/css.css`, `instagramfeed/lib/src/css/lightslider.css`). Ihr Webmaster oder Entwickler kann die Seite überprüfen, um widersprüchliche Stile zu identifizieren und benutzerdefinierte CSS-Überschreibungen in der Stylesheet-Datei Ihres Themes zu schreiben.
3. **Bildabmessungen:** Stellen Sie sicher, dass die Bilder, die Sie auf Instagram posten, von angemessener Qualität und Seitenverhältnis sind. Obwohl das Modul versucht, sich anzupassen, können extrem breite oder hohe Bilder Anzeigeprobleme verursachen.

**F: Wie erhalte ich einen Instagram Access Token und eine User ID?**
A: Der Instagram-API-Zugriff hat sich im Laufe der Zeit geändert. Sie benötigen typischerweise ein Instagram Business-Konto und ein Facebook Developer-Konto. Der Prozess umfasst das Erstellen einer Facebook-App, das Verbinden dieser mit Ihrem Instagram Business-Konto und dann das Generieren eines Tokens. Es gibt auch Drittanbieter-Tools (suchen Sie nach „Instagram Access Token Generator“), die diesen Prozess vereinfachen können, aber verwenden Sie immer seriöse.

**F: Kann ich verschiedene Feeds auf verschiedenen Seiten anzeigen (z.B. einen allgemeinen Feed auf der Startseite und produktspezifische Feeds)?**
A: Ja, absolut! Das ist die Kernfunktionalität. Verwenden Sie die Einstellung „Auf Startseite anzeigen“ für einen allgemeinen Feed (der typischerweise von einem Standard-Hashtag oder Ihrem Hauptbenutzer-Feed zieht), und verwenden Sie dann das Feld „Instagram Hashtag“ auf einzelnen Produktseiten für produktspezifische Feeds.

**F: Das Karussell oder die Fancybox funktioniert nicht.**
A:

1. **Funktionen aktivieren:** Überprüfen Sie nochmals, ob „Karussell-Funktion“ und „Fancybox-Funktion“ in der Modulkonfiguration aktiviert sind.
2. **JavaScript-Konflikte:** Ein anderes Modul oder Ihr Theme könnte widersprüchliche JavaScript-Bibliotheken laden (z.B. ein anderes Karussell-Skript oder eine Lightbox). Ihr Webmaster müsste dies mithilfe der Entwicklerkonsole des Browsers debuggen (suchen Sie nach JavaScript-Fehlern).
3. **jQuery:** Stellen Sie sicher, dass jQuery korrekt in Ihrem Shop geladen wird, da viele JavaScript-Funktionen darauf basieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Instagram product tag feed` folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für die Konfiguration und das `Hook`-System für die Front-Office-Anzeige nutzt. Es integriert eine benutzerdefinierte Klasse für die Instagram-API-Interaktion und verwendet externe JavaScript-Bibliotheken (lightslider, fancybox) für eine verbesserte UI/UX. Die Kernlogik des Moduls befindet sich in seiner Hauptdatei `index.php` und verwaltet Konfiguration, Installation und Hook-Registrierung. Die Front-Office-Darstellung wird durch die Übergabe von Daten an Smarty-Templates erreicht, die an verschiedene Anzeige-Hooks registriert sind.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt, und die Front-Office-Anzeige wird direkt über registrierte Hooks verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- `instagramfeed/classes/index.php`:

  - Dies ist typischerweise eine leere Datei oder eine Datei, die `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` enthält, um direkte Verzeichnisauflistungen zu verhindern. Sie enthält keine funktionale Klassenlogik.
- `instagramfeed/classes/instagram_class.php`:

  - **Klassenname**: `Instagram`
  - **Elternklasse**: Keine (eigenständige Dienstprogrammklasse)
  - **Verantwortlichkeit**: Diese Klasse kapselt die Logik für die Interaktion mit der Instagram-API. Sie ist verantwortlich für das Senden von HTTP-Anfragen zum Abrufen von Medien basierend auf Benutzer-ID und Hashtags, die Handhabung von Access Tokens und das Parsen der JSON-Antworten von Instagram.
  - **Wichtige öffentliche Methoden**:
    - `__construct($access_token, $user_id)`: Konstruktor, initialisiert mit dem Instagram Access Token und der Benutzer-ID.
    - `getMediaByHashtag($hashtag, $count)`: Ruft eine angegebene Anzahl von Medienelementen von der Instagram-API ab, die mit dem gegebenen Hashtag getaggt und der konfigurierten Benutzer-ID zugeordnet sind. Gibt ein Array von Medienobjekten zurück.
    - `getMediaByUser($count)`: Ruft eine angegebene Anzahl von Medienelementen direkt aus dem Benutzer-Feed ab (sofern von der API-Version und dem Token-Bereich unterstützt).
    - (Potenziell weitere Hilfsmethoden für API-Aufrufe, Fehlerbehandlung usw.)

### 4.4 JavaScript-Assets (`views/js/`)

- `instagramfeed/js/if_carousell.js`:
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Dieses Skript initialisiert und konfiguriert wahrscheinlich die `lightslider`-Karussellfunktionalität für die Instagram-Feeds. Es bindet an bestimmte DOM-Elemente (z.B. `ul` mit einer bestimmten Klasse) und wendet das Karussellverhalten an, einschließlich Einstellungen für Responsivität, Auto-Play, Navigation usw.
  - **Abhängigkeiten**: Basiert auf `lightslider.js` und jQuery.
- `instagramfeed/js/if_fancybox.js`:
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Dieses Skript initialisiert und konfiguriert die Fancybox-Lightbox-Funktionalität. Es zielt auf Bildlinks innerhalb des Instagram-Feeds ab (z.B. `a`-Tags, die `img`-Tags umschließen) und ermöglicht es ihnen, beim Klicken in einem Fancybox-Popup geöffnet zu werden, was eine größere, immersivere Ansicht des Bildes bietet.
  - **Abhängigkeiten**: Basiert auf der Fancybox-Bibliothek (nicht in diesem Modul enthalten, aber erwartet, dass sie vom Theme oder einem anderen Modul geladen wird) und jQuery.
- `instagramfeed/js/if_sliding.js`:
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Diese Datei könnte ein alternatives oder ergänzendes Skript für die Gleitfunktionalität sein, möglicherweise für ältere PrestaShop-Versionen oder spezifische Layouts. Angesichts von `if_carousell.js` und `lightslider.js` könnte es sich um ein Legacy-Skript oder einen Wrapper für spezifische Gleitverhalten handeln, die nicht vom Hauptkarussell abgedeckt werden.
  - **Abhängigkeiten**: Wahrscheinlich jQuery.
- `instagramfeed/js/ps14.js`:
  - **Geltungsbereich**: Front-Office (speziell für PrestaShop 1.4-Kompatibilität).
  - **Beschreibung**: Dieses Skript enthält wahrscheinlich Kompatibilitätskorrekturen oder Polyfills für ältere PrestaShop 1.4-Umgebungen, die potenzielle JavaScript-Unterschiede oder fehlende jQuery-Versionen/Funktionen im Vergleich zu neueren PrestaShop-Versionen adressieren.
  - **Abhängigkeiten**: jQuery.
- `instagramfeed/lib/src/js/lightslider.js`:
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Dies ist die Kernbibliothek des `lightslider` jQuery-Plugins. Sie bietet die Funktionalität zum Erstellen responsiver, berührungsempfindlicher Inhaltskarussells und Slider. `if_carousell.js` würde typischerweise Methoden aus dieser Bibliothek aufrufen.
  - **Abhängigkeiten**: jQuery.

### 4.5 CSS-Stylesheets (`views/css/`)

- `instagramfeed/css/css.css`:
  - **Geltungsbereich**: Front-Office Kunden-Styling.
  - **Beschreibung**: Enthält benutzerdefinierte CSS-Regeln, die spezifisch für das Layout, die Bildgröße, den Abstand und das allgemeine Erscheinungsbild des Instagram-Feeds innerhalb der verschiedenen Hooks sind. Es definiert Klassen für den Feed-Container, einzelne Bildelemente und potenziell Bildunterschriften oder Links.
  - **Wichtige CSS-Klassenselektoren**: Entwickler können den generierten HTML-Code überprüfen, um Klassen wie `.instagram-feed-container`, `.instagram-item`, `.instagram-image` usw. zu finden, die in der `custom.css` oder `theme.css` des Themes überschrieben werden können.
- `instagramfeed/lib/src/css/lightslider.css`:
  - **Geltungsbereich**: Front-Office Kunden-Styling.
  - **Beschreibung**: Dies ist das Standard-Stylesheet für das `lightslider` jQuery-Plugin. Es bietet das wesentliche Styling für die Navigationspfeile, Paginierungspunkte, Folienübergänge und das responsive Verhalten des Karussells.
  - **Wichtige CSS-Klassenselektoren**: Klassen wie `.lightSlider`, `.lSAction`, `.lSPager` usw., die an das Branding des Shops angepasst werden können.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:

  - `instagramfeed/views/templates/admin/instagram_feed.tpl`: Dieses Template wird von der Methode `getContent()` in der Hauptmoduldatei gerendert. Es zeigt das Back-Office-Konfigurationsformular des Moduls an, einschließlich Eingabefeldern für den Instagram Access Token, die User ID, die Anzahl der Fotos und verschiedene Anzeige-Umschalter (Startseite, Produktseite, Spalten, Footer, Header, Karussell, Fancybox). Es verwendet typischerweise die Helper-Formular-Komponenten von PrestaShop.
- **Hook-Templates (`views/templates/hook/`)**:

  - `instagramfeed/views/templates/hook/column-feed.tpl`: Rendert den Instagram-Feed, wenn er in `displayLeftColumn` oder `displayRightColumn` eingehängt ist. Es zeigt typischerweise eine kompaktere Version des Feeds an.
  - `instagramfeed/views/templates/hook/feed.tpl`: Ein universelles Feed-Template, das wahrscheinlich für die Haupt-Startseite oder die Footer-Anzeige verwendet wird. Es enthält die Kernstruktur zur Anzeige von Instagram-Bildern, potenziell in einem Karussell-Container.
  - `instagramfeed/views/templates/hook/header-left.tpl`: Rendert den Feed, wenn er in `displayHeaderLeft` eingehängt ist.
  - `instagramfeed/views/templates/hook/header-right.tpl`: Rendert den Feed, wenn er in `displayHeaderRight` eingehängt ist.
  - `instagramfeed/views/templates/hook/homepage-feed.tpl`: Speziell für den `displayHome`-Hook konzipiert, oft mit einem prominenteren oder breiteren Layout für die Startseite.
  - `instagramfeed/views/templates/hook/tab.tpl`: Rendert den Tab-Titel für den Instagram-Feed auf der Produktseite (z.B. „Instagram Fotos“). Dies wird typischerweise in `displayProductTab` (PrestaShop 1.6) oder `displayProductExtraContent` (PrestaShop 1.7+) eingehängt.
  - `instagramfeed/views/templates/hook/tabcontents.tpl`: Rendert den tatsächlichen Inhalt des Instagram-Feeds innerhalb des Produktseiten-Tabs. Dieses Template enthält die Logik zur Anzeige der Bilder, die mit dem produktspezifischen Hashtag abgerufen wurden, oft unter Verwendung der Karussell- und Fancybox-Funktionen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen (Access Token, User ID, Anzeigeoptionen usw.) werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `INSTAGRAMFEED_ACCESS_TOKEN`, `INSTAGRAMFEED_USER_ID`, `INSTAGRAMFEED_NUM_PHOTOS` usw. gespeichert.
  - Der produktspezifische Instagram-Hashtag wird in der Tabelle `ps_product_lang` (oder einer ähnlichen produktbezogenen Tabelle) als neues Feld gespeichert, das vom Modul während der Installation hinzugefügt wird. Dieses Feld würde typischerweise `instagram_hashtag` oder ähnlich benannt.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um CSS- und JavaScript-Assets (lightslider, fancybox, benutzerdefinierte Skripte) zu laden, die für die Instagram-Feeds erforderlich sind. |
| `displayHome` | Auf der Startseite des Shops. | Rendert den allgemeinen Instagram-Feed auf der Startseite. |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten, auf denen es aktiviert ist. | Rendert einen kompakten Instagram-Feed in der linken Spalte. |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten, auf denen es aktiviert ist. | Rendert einen kompakten Instagram-Feed in der rechten Spalte. |
| `displayFooter` | Im Footer-Bereich des Shops. | Rendert einen allgemeinen Instagram-Feed im Footer. |
| `displayHeaderLeft` | Im linken Teil des Headers des Shops. | Rendert einen kleinen Instagram-Feed im Header. |
| `displayHeaderRight` | Im rechten Teil des Headers des Shops. | Rendert einen kleinen Instagram-Feed im Header. |
| `displayProductTab` (PS 1.6) | Auf der Produktseite, zum Hinzufügen neuer Tabs. | Rendert den Titel des Instagram-Feed-Tabs auf der Produktseite. |
| `displayProductTabContent` (PS 1.6) | Auf der Produktseite, zum Hinzufügen von Inhalten zu Tabs. | Rendert den Inhalt (den eigentlichen Instagram-Feed) innerhalb des Produktseiten-Tabs. |
| `displayProductExtraContent` (PS 1.7+) | Auf der Produktseite, zum Hinzufügen zusätzlicher Inhaltsblöcke. | Alternativer Hook für PrestaShop 1.7+, um den Instagram-Feed auf Produktseiten anzuzeigen, oft als neuer Block unter den Hauptproduktinformationen. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Wird verwendet, um den Wert des Feldes `instagram_hashtag` für das Produkt zu speichern. |
| `actionProductAdd` | Nach dem Hinzufügen eines neuen Produkts im Back Office. | Wird verwendet, um den Wert des Feldes `instagram_hashtag` für das neue Produkt zu speichern. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Rendert das Eingabefeld für den „Instagram Hashtag“ auf der Produktkonfigurationsseite. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, Unterstützung zu leisten und sicherzustellen, dass Ihr Modul optimal funktioniert.
