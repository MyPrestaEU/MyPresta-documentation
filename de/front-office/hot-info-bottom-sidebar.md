---
title: "Hot Info - untere Seitenleiste - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Hot Info - untere Seitenleiste“ von MyPresta.eu."
sidebar:
  label: "Hot Info - untere Seitenleiste - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Hot Info - bottom sidebar auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/hot-info-bottom-sidebar.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/hot-info-bottom-sidebar/)
>
> ---


# Hot Info - untere Seitenleiste

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und auf jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls klicken Sie auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen. Hier definieren Sie den Inhalt und das Erscheinungsbild Ihrer „Hot Info“-Seitenleiste.

#### **Inhalt für Hot Info Block**

-   **Was diese Einstellung bewirkt:** Dies ist der Hauptbereich, in dem Sie den tatsächlichen Inhalt eingeben, den Kunden in der unteren Seitenleiste sehen werden. Es handelt sich um einen Rich-Text-Editor (WYSIWYG - What You See Is What You Get), ähnlich dem, den Sie für Produktbeschreibungen oder Blogbeiträge verwenden könnten.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Wenn Inhalt hinzugefügt wird:* Der hier eingegebene Text, Bilder, Links oder HTML werden im „Hot Info“-Block in Ihrem Shop angezeigt.
    *   *Wenn leer gelassen:* Der „Hot Info“-Block könnte immer noch erscheinen, aber er wird leer sein, oder das Modul wird überhaupt nicht angezeigt (abhängig von anderen Einstellungen und dem Theme-Verhalten). Es ist entscheidend, hier Inhalt hinzuzufügen, damit das Modul nützlich ist.
-   **Empfohlener Wert:** Geben Sie hier Ihre gewünschten „heißen Informationen“ ein. Verwenden Sie eine klare, prägnante Sprache und starke Handlungsaufforderungen.
-   **Händlerszenario / Beispiel:** Sie könnten hinzufügen: „FLASH SALE! Erhalten Sie 20% Rabatt auf alle Sommerartikel mit dem Code SUMMER20! [Jetzt einkaufen]“ mit einem Link zu Ihrer Sommerkollektion. Oder „Kostenloser Versand für alle Bestellungen über 50 $!“

#### **Hintergrundfarbe**

-   **Was diese Einstellung bewirkt:** Dies steuert die Hintergrundfarbe des „Hot Info“-Blocks. Sie können eine Farbe mit einem Farbwähler-Tool auswählen.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Wenn auf eine bestimmte Farbe eingestellt (z.B. #FF0000 für Rot):* Der Hintergrund des „Hot Info“-Blocks wird in dieser gewählten Farbe angezeigt.
    *   *Wenn Standard oder transparent gelassen:* Es wird typischerweise die Hintergrundfarbe Ihres Themes erben oder transparent sein, was dazu führen könnte, dass es zu stark verschmilzt oder schwer zu lesen ist.
-   **Empfohlener Wert:** Wählen Sie eine Farbe, die entweder zum Branding Ihres Shops passt oder hervorsticht, um Aufmerksamkeit zu erregen, je nach Ihrem Ziel. Eine Kontrastfarbe kann sehr effektiv sein.
-   **Händlerszenario / Beispiel:** Wenn Ihr Shop viel Blau verwendet, könnten Sie ein lebhaftes Orange oder Gelb wählen, um eine Verkaufsankündigung hervorzuheben.

#### **Rahmenfarbe**

-   **Was diese Einstellung bewirkt:** Dies steuert die Farbe des Rahmens um den „Hot Info“-Block.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Wenn auf eine bestimmte Farbe eingestellt (z.B. #000000 für Schwarz):* Der Rahmen des „Hot Info“-Blocks wird in dieser gewählten Farbe angezeigt.
    *   *Wenn Standard oder transparent gelassen:* Der Block könnte ohne sichtbaren Rahmen erscheinen, oder er könnte eine Rahmenfarbe von Ihrem Theme erben.
-   **Empfohlener Wert:** Oft funktioniert eine Rahmenfarbe, die Ihrer Textfarbe entspricht oder ein etwas dunklerer Farbton Ihrer Hintergrundfarbe, gut.
-   **Händlerszenario / Beispiel:** Wenn Ihr Hintergrund hellblau ist, kann ein dunklerer blauer Rahmen ihm ein sauberes, definiertes Aussehen verleihen.

#### **Rahmengröße (in Pixel)**

-   **Was diese Einstellung bewirkt:** Dies bestimmt die Dicke des Rahmens um den „Hot Info“-Block, gemessen in Pixeln.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Wenn auf einen Wert wie „2“ eingestellt:* Der Block hat einen 2 Pixel dicken Rahmen.
    *   *Wenn auf „0“ eingestellt:* Es wird kein Rahmen angezeigt.
-   **Empfohlener Wert:** Beginnen Sie mit einem kleinen Wert wie „1“ oder „2“ für einen subtilen Rahmen. Erhöhen Sie ihn, wenn Sie einen ausgeprägteren Rahmen wünschen.
-   **Händlerszenario / Beispiel:** Ein 2px-Rahmen kann Ihre Nachricht subtil umrahmen und sie wie ein eigenständiges Element auf der Seite aussehen lassen.

#### **Höhe (in Pixel)**

-   **Was diese Einstellung bewirkt:** Dies steuert die feste Höhe des „Hot Info“-Blocks, gemessen in Pixeln.
-   **Auswirkung der Änderung dieser Einstellung:**
    *   *Wenn auf einen Wert wie „50“ eingestellt:* Der Block ist 50 Pixel hoch.
    *   *Wenn der Inhalt die Höhe überschreitet:* Wenn Ihr Inhalt höher ist als die angegebene Höhe, erscheint ein Scrollbalken innerhalb des Blocks, der es Kunden ermöglicht, durch den Inhalt zu scrollen.
-   **Empfohlener Wert:** Halten Sie diesen Wert relativ klein (z.B. 40-60px), um nicht zu viel Bildschirmfläche einzunehmen, insbesondere auf Mobilgeräten. Passen Sie ihn an die Menge des Inhalts an, den Sie haben.
-   **Händlerszenario / Beispiel:** Wenn Sie eine kurze, einzeilige Nachricht haben, könnte eine Höhe von 40px perfekt sein. Wenn Sie mehrere Textzeilen haben, benötigen Sie möglicherweise 60-80px.

#### **Standardsprache (PS\_LANG\_DEFAULT)**

-   **Was diese Einstellung bewirkt:** Dies ist eine Standard-PrestaShop-Einstellung, die die Standardsprache für Ihren Shop definiert. Obwohl nicht direkt von diesem Modul konfiguriert, zeigt das Inhaltsfeld des Moduls typischerweise den Inhalt für die aktuell im Back Office ausgewählte Sprache an, wobei diese als Standard verwendet wird.
-   **Auswirkung der Änderung dieser Einstellung:** Dies beeinflusst die Standardsprache Ihres gesamten PrestaShop-Shops und wie mehrsprachige Inhalte verwaltet werden. Für dieses Modul bedeutet dies, dass der von Ihnen eingegebene Inhalt der Sprache zugeordnet wird, die Sie gerade im Back Office bearbeiten.
-   **Empfohlener Wert:** Dies sollte auf Ihre primäre Shop-Sprache eingestellt sein.
-   **Händlerszenario / Beispiel:** Wenn Ihr Hauptmarkt die USA ist, wäre dies auf Englisch eingestellt. Wenn Sie Inhalte für den „Hot Info“-Block eingeben, stellen Sie sicher, dass Sie in der richtigen Sprache bearbeiten, wenn Ihr Shop mehrere Sprachen unterstützt.

#### **MyPresta.eu Updates (mypresta\_updates, update\_, updatev\_)**

-   **Was diese Einstellungen bewirken:** Dies sind interne Einstellungen, die von MyPresta.eu-Modulen verwendet werden, um nach Updates zu suchen und diese zu verwalten. Sie speichern typischerweise Informationen über die Modulversion und wann zuletzt nach Updates gesucht wurde.
-   **Auswirkung der Änderung dieser Einstellungen:**
    *   *Wenn aktiviert/aktiv:* Das Modul kann mit MyPresta.eu-Servern kommunizieren, um Sie über neue Versionen oder Sicherheitspatches zu informieren.
    *   *Wenn deaktiviert/inaktiv:* Das Modul sucht nicht automatisch nach Updates.
-   **Empfohlener Wert:** Lassen Sie diese Einstellungen unverändert. Sie sind wesentlich, um Ihr Modul aktuell und sicher zu halten.
-   **Händlerszenario / Beispiel:** Sie interagieren normalerweise nicht direkt mit diesen. Sie stellen sicher, dass Sie in Ihrem PrestaShop Back Office benachrichtigt werden, wenn eine neue Version des Moduls zum Download von Ihrem MyPresta.eu-Konto verfügbar ist.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Inhalt für Hot Info Block** | Ihre benutzerdefinierte Nachricht | Der tatsächliche Text, Bilder, Links, die in der unteren Seitenleiste angezeigt werden. |
| Modulkonfiguration | **Hintergrundfarbe** | Wählen Sie passend zum/kontrastierend zum Theme | Legt die Hintergrundfarbe des Infoblocks fest. |
| Modulkonfiguration | **Rahmenfarbe** | Wählen Sie passend zum/kontrastierend zum Theme | Legt die Farbe des Rahmens um den Infoblock fest. |
| Modulkonfiguration | **Rahmengröße (in Pixel)** | 1 oder 2 | Definiert die Dicke des Rahmens. Auf 0 setzen für keinen Rahmen. |
| Modulkonfiguration | **Höhe (in Pixel)** | 40-60 | Legt die feste Höhe des Infoblocks fest. Inhalt, der dies überschreitet, wird gescrollt. |
| Modulkonfiguration | **PS\_LANG\_DEFAULT** | Primäre Sprache Ihres Shops | PrestaShops Standardspracheinstellung, beeinflusst die Inhaltsbearbeitung. |
| Modulkonfiguration | **MyPresta.eu Updates** | Aktiviert | Interne Einstellungen für Modul-Update-Prüfungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein „Hot Info“-Block wird im Front Office nicht angezeigt.**

-   **A:** Stellen Sie zunächst sicher, dass das Modul unter **Module > Modul-Manager** installiert und aktiviert ist. Zweitens prüfen Sie, ob Sie tatsächlich Inhalt in das Feld „Inhalt für Hot Info Block“ in der Modulkonfiguration eingegeben haben. Ein leerer Block wird möglicherweise nicht gerendert. Leeren Sie schließlich Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**) und Ihren Browser-Cache.

**F2: Der „Hot Info“-Block sieht seltsam aus oder passt nicht zum Styling meines Themes.**

-   **A:** Das Modul bietet grundlegende Styling-Optionen (Hintergrund, Rahmenfarbe/-größe, Höhe). Wenn es immer noch mit Ihrem Theme kollidiert, überschreibt möglicherweise das CSS Ihres Themes die Stile des Moduls.
    *   **Lösung für Händler:** Versuchen Sie, die Hintergrund- und Rahmenfarben in den Moduleinstellungen anzupassen, um eine bessere Übereinstimmung zu finden. Falls nicht, benötigen Sie möglicherweise einen Webmaster, der benutzerdefiniertes CSS zu Ihrem Theme hinzufügt, um den Block des Moduls gezielt zu gestalten.
    *   **Lösung für Webmaster:** Überprüfen Sie das Element in den Browser-Entwicklertools, um widersprüchliche CSS-Regeln zu identifizieren und spezifischere oder `!important`-Regeln in der benutzerdefinierten CSS-Datei Ihres Themes anzuwenden.

**F3: Wie füge ich Bilder oder Links zum „Hot Info“-Inhalt hinzu?**

-   **A:** Verwenden Sie den Rich-Text-Editor, der für die Einstellung „Inhalt für Hot Info Block“ bereitgestellt wird. Er verfügt über Schaltflächen zum Einfügen von Bildern, Erstellen von Links, Formatieren von Text (fett, kursiv) und mehr, genau wie ein Standard-Textverarbeitungsprogramm. Klicken Sie auf das „Bild“-Symbol, um ein Bild hochzuladen und einzufügen, oder wählen Sie Text aus und klicken Sie auf das „Link“-Symbol, um einen Hyperlink hinzuzufügen.

**F4: Kann ich den „Hot Info“-Block nur auf bestimmten Seiten anzeigen lassen?**

-   **A:** Dieses Modul ist in seiner aktuellen Version so konzipiert, dass es global auf allen Seiten erscheint, auf denen der `displayHeader`-Hook ausgeführt wird. Wenn Sie eine seiten-spezifische Sichtbarkeit benötigen, wäre eine kundenspezifische Entwicklung erforderlich, um die Anzeigelogik des Moduls zu ändern oder ein separates Modul zu verwenden, das für die bedingte Inhaltsanzeige entwickelt wurde.

**F5: Der Farbwähler funktioniert nicht oder wird nicht angezeigt.**

-   **A:** Stellen Sie sicher, dass JavaScript in Ihrem Browser aktiviert ist. Manchmal können Konflikte mit anderen Modulen oder Theme-JavaScript verhindern, dass der Farbwähler korrekt geladen wird. Versuchen Sie, Ihren Browser-Cache und Cookies zu leeren. Wenn das Problem weiterhin besteht, könnte dies auf einen komplexeren JavaScript-Konflikt hindeuten, den ein Webmaster untersuchen müsste.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Hot Info - untere Seitenleiste“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul `hotinfo` ist ein Standard-PrestaShop-Modul, das, wo anwendbar, dem MVC-Muster folgt. Es fungiert hauptsächlich als Anzeigemodul, das Inhalte in den `displayHeader`-Hook injiziert. Die Konfiguration wird über die `getContent()`-Methode der Hauptmodulklasse gehandhabt, wobei die Einstellungen direkt in `ps_configuration` gespeichert werden. Es nutzt einen Rich-Text-Editor (TinyMCE) für die Inhaltseingabe und einen JavaScript-Farbwähler für Styling-Optionen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Konfiguration wird innerhalb der Hauptmoduldatei `hotinfo.php` über die Methode `getContent()` gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Alle Daten (Konfiguration) werden direkt in der Tabelle `ps_configuration` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`hotinfo/jscolor/jscolor.js`**
    *   **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
    *   **Beschreibung:** Dies ist eine JavaScript-Bibliothek eines Drittanbieters, die eine benutzerfreundliche Farbwähler-Oberfläche bereitstellt. Sie wird typischerweise auf Eingabefeldern mit einer bestimmten Klasse (z.B. `jscolor`) initialisiert, um Administratoren die visuelle Auswahl von Farben für den Hintergrund und den Rahmen des „Hot Info“-Blocks zu ermöglichen. Sie bindet an Eingabefelder und aktualisiert deren Werte basierend auf der Farbauswahl des Benutzers.
-   **`hotinfo/tinymce16.js`**
    *   **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
    *   **Beschreibung:** Dieses Skript initialisiert und konfiguriert wahrscheinlich eine Version des TinyMCE Rich-Text-Editors für das Textfeld „Inhalt für Hot Info Block“. Es verwandelt ein Standard-HTML-`<textarea>` in einen funktionsreichen Editor, der Administratoren ermöglicht, Text zu formatieren, Bilder einzufügen, Links zu erstellen und HTML-Inhalte ohne direkte Codierung zu verwalten. Dieses Skript würde an das relevante Textfeld-Element gebunden und die Editor-Oberfläche bereitstellen.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`hotinfo/css/hotinfo.css`**
    *   **Geltungsbereich:** Front-Office (kundenorientierter Shop).
    *   **Beschreibung:** Dieses Stylesheet enthält die primären CSS-Regeln für die „Hot Info“-Seitenleiste unten. Es definiert die feste Positionierung, Abmessungen, Hintergrund, Rahmen und Textformatierung für den Block.
    *   **Wichtige Selektoren (Entwickler können überschreiben):**
        *   `#hotinfo_block`: Der Hauptcontainer für den gesamten „Hot Info“-Block. Hier werden `position: fixed; bottom: 0; width: 100%;` und andere globale Stile angewendet.
        *   `#hotinfo_block .hotinfo_content`: Der innere Container für den eigentlichen Inhalt, wo `overflow-y: auto;` angewendet werden könnte, wenn der Inhalt die definierte Höhe überschreitet.
        *   Stile für `p`, `a`, `img` innerhalb von `#hotinfo_block`, um sicherzustellen, dass der Inhalt gut aussieht.
    *   **Überschreibungsstrategie:** Entwickler können diese Stile überschreiben, indem sie spezifischere CSS-Regeln in der `custom.css`- oder `theme.css`-Datei ihres Themes hinzufügen oder indem sie ein Child-Theme erstellen und das CSS des Moduls bei Bedarf direkt ändern.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **`hotinfo/hotinfo.tpl`**
    *   **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
    *   **Beschreibung:** Dieses Template wird verwendet, um das Konfigurationsformular im PrestaShop Back Office zu rendern, wenn die Konfigurationsseite des Moduls aufgerufen wird. Es enthält die HTML-Struktur für den Rich-Text-Editor, Farbwähler und Eingabefelder für Höhen- und Rahmeneinstellungen. Es verwendet Smarty-Variablen, um Formularfelder mit aktuellen Konfigurationswerten vorab auszufüllen.
-   **`hotinfo/views/templates/hook/hotinfo.tpl`**
    *   **Geltungsbereich:** Front-Office (kundenorientierter Shop).
    *   **Beschreibung:** Dieses Template ist für das Rendern des „Hot Info“-Blocks im Shop verantwortlich. Es ist in `displayHeader` eingehängt. Es ruft den konfigurierten Inhalt, die Hintergrundfarbe, die Rahmenfarbe, die Rahmengröße und die Höhe aus Smarty-Variablen ab, die vom Modul übergeben werden, und wendet sie auf die HTML-Struktur an.
    *   **Schlüsselelemente:**
        *   Ein Haupt-`div` mit einer ID wie `hotinfo_block` für die feste Positionierung.
        *   Ein inneres `div` für den Inhalt, möglicherweise mit `overflow: auto;` zum Scrollen.
        *   Der eigentliche Inhalt wird mit `{html_entity_decode($hotinfo_body)}` gerendert, um das HTML aus dem Rich-Text-Editor anzuzeigen.
    *   **Hook:** `displayHeader` (obwohl es visuell am unteren Rand erscheint, ist der Hook im Header, um sicherzustellen, dass es frühzeitig geladen wird).

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen werden in der Standard-PrestaShop-Tabelle `ps_configuration` gespeichert.

    *   `PS_CONFIGURATION`-Einträge:
        *   `HOTINFO_BODY`: Speichert den HTML-Inhalt für den „Hot Info“-Block (mehrsprachig).
        *   `HOTINFO_BG_COLOR`: Speichert den hexadezimalen Hintergrundfarbwert.
        *   `HOTINFO_BR_COLOR`: Speichert den hexadezimalen Rahmenfarbwert.
        *   `HOTINFO_BR_SIZE`: Speichert den ganzzahligen Wert für die Rahmendicke.
        *   `HOTINFO_HEIGHT`: Speichert den ganzzahligen Wert für die Blockhöhe.
        *   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Interne Schlüssel für den MyPresta.eu-Update-Mechanismus.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Das Modul verwendet diesen Hook, um seine CSS- und JavaScript-Dateien zu injizieren und die Haupt-HTML-Struktur des „Hot Info“-Blocks zu rendern. Obwohl der Block visuell am unteren Rand positioniert ist, stellt das Rendern über `displayHeader` sicher, dass er frühzeitig beim Seitenaufbau verfügbar ist und effektiv mit `position: fixed;` gestylt werden kann. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Hot Info - untere Seitenleiste“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Sie können die aktuellste Version des Moduls aus Ihrem Bestellverlauf herunterladen. Für technische Unterstützung oder Anfragen kontaktieren Sie bitte direkt den MyPresta.eu-Support.
