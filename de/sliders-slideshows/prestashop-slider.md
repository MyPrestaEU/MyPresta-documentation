---
title: "Prestashop Slider - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop Slider Modul von MyPresta.eu."
sidebar:
  label: "Prestashop Slider - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Prestashop Slider auf MyPresta.eu kaufen](https://mypresta.eu/modules/slider-slideshow/prestashop-slider.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/sliders-slideshows/prestashop-slider/)
>
> ---


# Prestashop Slider

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Webhosting-Umgebungen vorinstalliert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist das Hauptkontrollfeld für Ihren Prestashop Slider. Hier definieren Sie das Aussehen, die Haptik und den Inhalt Ihrer Slider.

#### **Allgemeine Einstellungen**

- **Was diese Einstellung bewirkt:** Diese Einstellungen steuern das Gesamtverhalten und Aussehen Ihres Sliders.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Slider-Breite:* Definiert, wie breit der Slider sein wird. Kann ein fester Pixelwert oder ein Prozentsatz für Responsivität sein.
  - *Slider-Höhe:* Definiert die Höhe des Sliders.
  - *Animationstyp:* Wählt einen der 40 verfügbaren Übergangseffekte zwischen den Folien aus.
  - *Animationsgeschwindigkeit:* Steuert, wie schnell der Übergang zwischen den Folien erfolgt.
  - *Folienintervall:* Legt die Dauer fest, für die jede Folie angezeigt wird, bevor automatisch zur nächsten gewechselt wird.
  - *Navigationspfeile:* Aktiviert/deaktiviert die Links/Rechts-Pfeile für die manuelle Foliennavigation.
  - *Navigationspunkte/Bullets:* Aktiviert/deaktiviert die kleinen Punkte, die sich normalerweise am unteren Rand des Sliders befinden, zur direkten Folienauswahl.
  - *Miniaturansichten:* Aktiviert/deaktiviert kleine Vorschaubilder jeder Folie, die oft unter dem Hauptslider angezeigt werden.
  - *Miniaturansicht-Vorschau:* Wenn Miniaturansichten aktiviert sind, steuert diese Einstellung, ob eine größere Vorschau beim Überfahren einer Miniaturansicht angezeigt wird.
  - *Bildunterschrift-Anzeige:* Steuert, ob und wie Text-Bildunterschriften, die mit jeder Folie verbunden sind, angezeigt werden.
- **Empfohlener Wert:**
  - *Slider-Breite:* `100%` für einen vollbreiten, responsiven Slider oder ein spezifischer Pixelwert wie `1140px`, um dem Hauptinhaltsbereich Ihres Themes zu entsprechen.
  - *Slider-Höhe:* Beginnen Sie mit `400px` und passen Sie sie basierend auf Ihrem Bildseitenverhältnis und Design an.
  - *Animationstyp:* Experimentieren Sie! `fade` oder `slice` sind gute Ausgangspunkte für ein sauberes Aussehen.
  - *Animationsgeschwindigkeit:* `800` (Millisekunden) für einen sanften Übergang.
  - *Folienintervall:* `5000` (5 Sekunden) ist ein gutes Gleichgewicht, damit Benutzer Inhalte lesen können, ohne sich gehetzt zu fühlen.
  - *Navigationspfeile:* `JA` für bessere Benutzerkontrolle.
  - *Navigationspunkte/Bullets:* `JA` für einfache Übersicht und Navigation.
  - *Miniaturansichten:* Zunächst `NEIN`, aktivieren Sie sie, wenn Sie viele Folien haben und einen visuellen Index wünschen.
  - *Miniaturansicht-Vorschau:* `JA`, wenn Miniaturansichten aktiviert sind.
  - *Bildunterschrift-Anzeige:* `JA`, wenn Sie Text zu Ihren Folien hinzufügen möchten.
- **Händlerszenario / Beispiel:** Sie möchten ein vollbreites Banner auf Ihrer Startseite, das durch drei neue Produktlinien rotiert. Sie würden die Breite auf `100%` einstellen, eine `fade`-Animation wählen und ein `5-Sekunden`-Intervall festlegen. Sie würden Navigationspfeile und Punkte aktivieren, damit Kunden bei Bedarf manuell blättern können.

#### **Folienverwaltung**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, einzelne Folien zu Ihrem Slider hinzuzufügen, zu bearbeiten und zu entfernen. Jede Folie besteht aus einem Bild und zugehörigen Einstellungen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Hinzufügen einer neuen Folie:* Ein neues Bild wird zu Ihrer Slider-Rotation hinzugefügt. Sie laden ein Bild hoch, definieren dessen Link, Bildunterschrift und möglicherweise eine einzigartige Animation.
  - *Bearbeiten einer vorhandenen Folie:* Sie können das Bild, seinen Ziellink, den Bildunterschriftstext oder den individuellen Animationstyp für diese spezifische Folie ändern.
  - *Löschen einer Folie:* Die ausgewählte Folie wird aus Ihrem Slider entfernt.
  - *Folien neu anordnen:* Sie können Folien per Drag & Drop verschieben, um die Reihenfolge zu ändern, in der sie in der Rotation erscheinen.
- **Empfohlener Wert:** Verwenden Sie immer hochwertige, optimierte Bilder, die in Größe und Seitenverhältnis konsistent sind, um ein professionelles Aussehen zu gewährleisten.
- **Händlerszenario / Beispiel:** Sie starten eine neue Sommerkollektion. Sie würden drei Folien hinzufügen: eine für Kleider, eine für Bademode und eine für Accessoires. Jede Folie würde ein Hero-Bild, eine Bildunterschrift wie „Jetzt Sommerkleider shoppen!“ und einen Link direkt zur jeweiligen Kategorieseite enthalten. Sie könnten der Bademode-Folie eine „cube“-Animation für ein spielerisches Gefühl geben, während die anderen „fade“ verwenden.

#### **Hook-Auswahl**

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen zu wählen, wo in Ihrem PrestaShop-Store der Slider angezeigt werden soll.
- **Auswirkung der Änderung dieser Einstellung:** Durch die Auswahl eines Hooks (z.B. `displayHeader`, `displayLeftColumn`) injiziert das Modul den Code des Sliders in diesen spezifischen Bereich Ihres Themes.
- **Empfohlener Wert:**
  - Für ein prominentes, vollbreites Banner: `displayHeader` oder ein benutzerdefinierter Hook, der von Ihrem Theme für Top-Banner bereitgestellt wird.
  - Für einen kleineren, kontextbezogenen Slider: `displayLeftColumn` oder `displayRightColumn`.
  - Für produktspezifische Slider: `displayProductExtraContent` oder `displayProductButtons`.
- **Händlerszenario / Beispiel:** Sie möchten, dass Ihr Haupt-Promotions-Slider direkt unter dem Hauptmenü Ihrer Website erscheint. Sie würden den `displayHeader`-Hook auswählen (oder einen ähnlichen themenspezifischen Hook, falls verfügbar). Wenn Sie einen kleineren Slider mit „verwandten Produkten“ an der Seite anzeigen möchten, würden Sie `displayLeftColumn` wählen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Slider-Breite | `100%` / `1140px` | Legt die horizontale Größe des Sliders fest. |
| Modulkonfiguration | Slider-Höhe | `400px` | Legt die vertikale Größe des Sliders fest. |
| Modulkonfiguration | Animationstyp | `fade` / `slice` | Definiert den visuellen Übergang zwischen den Folien (40 Optionen). |
| Modulkonfiguration | Animationsgeschwindigkeit | `800` (ms) | Wie schnell der Animationsübergang erfolgt. |
| Modulkonfiguration | Folienintervall | `5000` (ms) | Wie lange jede Folie sichtbar ist, bevor sie wechselt. |
| Modulkonfiguration | Navigationspfeile | `JA` | Zeigt Links/Rechts-Pfeile für die manuelle Navigation an. |
| Modulkonfiguration | Navigationspunkte/Bullets | `JA` | Zeigt Punkte/Bullets zur direkten Folienauswahl an. |
| Modulkonfiguration | Miniaturansichten | `NEIN` | Zeigt kleine Vorschaubilder jeder Folie an. |
| Modulkonfiguration | Miniaturansicht-Vorschau | `JA` | Zeigt eine größere Vorschau beim Überfahren der Miniaturansicht an (falls aktiviert). |
| Modulkonfiguration | Bildunterschrift-Anzeige | `JA` | Steuert die Sichtbarkeit von Text-Bildunterschriften auf Folien. |
| Modulkonfiguration | Folie hinzufügen/bearbeiten | N/A | Bild hochladen, Link, Bildunterschrift und individuelle Animation festlegen. |
| Modulkonfiguration | Hook-Auswahl | `displayHeader` | Bestimmt, wo der Slider in Ihrem Shop erscheint. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Slider wird nach der Konfiguration nicht angezeigt. Was soll ich tun?**
A:

1. **Hook-Auswahl überprüfen:** Gehen Sie zurück zur Modulkonfiguration und stellen Sie sicher, dass Sie mindestens einen Hook (z.B. `displayHeader`) ausgewählt haben.
2. **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
3. **Auf Konflikte prüfen:** Deaktivieren Sie vorübergehend andere Module, die denselben Hook verwenden oder dieselben Seitenbereiche ändern könnten (insbesondere andere Slider-Module).
4. **Theme-Kompatibilität:** Einige stark angepasste Themes erfordern möglicherweise geringfügige Anpassungen. Wenn das Problem weiterhin besteht, wenden Sie sich mit Ihren Theme-Details an den MyPresta.eu-Support.

**F: Meine Bilder sehen im Slider unscharf oder verzerrt aus.**
A: Dies bedeutet normalerweise, dass Ihre Bilder nicht die richtigen Abmessungen oder die richtige Auflösung für Ihre Slider-Einstellungen haben.

1. **Konsistente Abmessungen:** Stellen Sie sicher, dass alle für Ihre Folien hochgeladenen Bilder die gleiche Breite und Höhe haben.
2. **Hohe Auflösung:** Laden Sie Bilder mit ausreichender Auflösung hoch. Wenn Ihr Slider `1140px` breit ist, sollten Ihre Bilder mindestens `1140px` breit sein.
3. **Seitenverhältnis:** Passen Sie das Seitenverhältnis Ihrer Bilder an die konfigurierte Breite und Höhe des Sliders an. Wenn Ihr Slider `1140x400px` ist, versuchen Sie, Bilder mit einem ähnlichen Seitenverhältnis von 114:40 zu verwenden.

**F: Wie übersetze ich die Bildunterschriften für meine Folien in verschiedene Sprachen?**
A: Das Modul sollte das Standard-Übersetzungssystem von PrestaShop unterstützen.

1. Gehen Sie zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“, Ihr Theme und die Sprache, in die Sie übersetzen möchten.
3. Suchen Sie das Modul „Prestashop Slider“ in der Liste. Sie sollten die Bildunterschriften für jede Folie direkt dort bearbeiten können. Falls nicht, speichert das Modul die Bildunterschriften möglicherweise direkt in der Datenbank, sodass Sie jede Folie für jede Sprache in der Modulkonfiguration bearbeiten müssen.

**F: Der Slider sieht auf dem Desktop gut aus, ist aber auf dem Handy kaputt.**
A:

1. **Responsivität prüfen:** Das Modul ist responsiv konzipiert. Stellen Sie sicher, dass Ihr Theme selbst responsiv ist.
2. **CSS-Konflikte:** Ein anderes Modul oder das CSS Ihres Themes könnte die responsiven Stile des Sliders überschreiben. Verwenden Sie die Entwicklertools Ihres Browsers, um den Slider auf dem Handy zu überprüfen und nach widersprüchlichen CSS-Regeln zu suchen.
3. **Bildgröße:** Sehr große Bilder können manchmal Probleme auf Mobilgeräten verursachen. Stellen Sie sicher, dass die Bilder optimiert sind.

**F: Kann ich mehrere Slider auf verschiedenen Seiten haben?**
A: Die aktuelle Modulkonfiguration verwaltet typischerweise eine Haupt-Slider-Instanz mit ihren Folien. Wenn Sie mehrere *unterschiedliche* Slider mit unterschiedlichen Inhalten und Einstellungen auf verschiedenen Seiten benötigen, müssen Sie möglicherweise das Modul duplizieren (wenn Ihr Theme dies zulässt) oder eine fortschrittlichere Slider-Lösung verwenden. Für dieses Modul konfigurieren Sie einen Slider und wählen dessen Platzierung über Hooks.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Prestashop Slider Moduls, der für Entwickler, Webmaster und technische Agenturen gedacht ist.

### 4.1 Architekturübersicht

Das `Prestashop Slider`-Modul (`pslider`) ist ein Standard-PrestaShop-Modul, das hauptsächlich die `Module`-Klasse nutzt. Es verwaltet seine Konfiguration und Folien-Daten direkt in der Tabelle `ps_configuration`. Die Front-Office-Anzeige wird durch Smarty-Templates gehandhabt, die über das PrestaShop-Hook-System gerendert werden, wobei JavaScript- und CSS-Assets für die Slider-Funktionalität injiziert werden. Das Modul verwendet das `Skitter` jQuery-Plugin für seine Animationsfähigkeiten.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen, die `ObjectModel` erweitern. Alle Konfigurations- und Folien-Daten werden als serialisierte Arrays in der Tabelle `ps_configuration` gespeichert und direkt von der `Configuration`-Klasse verwaltet.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul basiert auf dem Skitter jQuery-Plugin für seine Slider-Funktionalität.

- `pslider/js/jquery.easing.1.3.js`:
  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Bietet erweiterte Easing-Funktionen für jQuery-Animationen, die die visuelle Glätte der vom Skitter-Plugin verwendeten Übergänge verbessern.
- `pslider/js/jquery.skitter.js`:
  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Dies ist das Kern-Skitter-Slider-Plugin. Es initialisiert den Slider, verwaltet Folienübergänge, Navigation und Responsivität. Es liest Konfigurationsoptionen (Animationstyp, Geschwindigkeit, Intervall usw.) aus den Moduleinstellungen und wendet sie auf die Slider-Instanz an.
- `pslider/js/noconflict.js`:
  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Stellt sicher, dass jQuery im `noConflict()`-Modus arbeitet, um Konflikte mit anderen JavaScript-Bibliotheken (wie Prototype.js, das PrestaShop 1.6 und frühere Versionen manchmal verwendeten) zu vermeiden, die ebenfalls den `$`-Alias verwenden könnten. Dies ist entscheidend für die Kompatibilität.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält eine einzige CSS-Datei zur Gestaltung des Skitter-Sliders.

- `pslider/css/skitter.styles.css`:
  - **Geltungsbereich:** Front-Office Kunden-Styling.
  - **Zweck:** Enthält alle Standard-Visual-Styles für den Skitter-Slider, einschließlich:
    - Layout des Slider-Containers (`.box_skitter`).
    - Styling für Navigationselemente (Pfeile, Punkte, Miniaturansichten).
    - Standardaussehen von Bildunterschriften.
    - Responsive Anpassungen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:**
    - `.box_skitter`: Haupt-Slider-Container.
    - `.box_skitter ul`: Liste der Folien.
    - `.box_skitter .info_slide`: Bildunterschriften-Container.
    - `.box_skitter .nav_cont`: Navigations-Container.
    - `.box_skitter .prev_button`, `.box_skitter .next_button`: Navigationspfeile.
    - `.box_skitter .info_slide_dots`: Navigationspunkte.
    - `.box_skitter .box_thumbs`: Miniaturansichten-Container.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates, um seine Front-Office-Inhalte und Teile seiner Back-Office-Konfiguration zu rendern.

- **Hook-Templates (`views/templates/hook/`)**:

  - `pslider/header.tpl`: Dieses Template ist wahrscheinlich dazu gedacht, in `displayHeader` oder einen ähnlichen Hook am Seitenanfang eingebunden zu werden. Es enthält die Haupt-HTML-Struktur für den Slider und oft den notwendigen JavaScript-Initialisierungscode für das Skitter-Plugin.
  - `pslider/top.tpl`: Ähnlich wie `header.tpl` könnte dies für einen anderen Top-Level-Hook verwendet werden, möglicherweise `displayTop` oder einen anderen themenspezifischen Banner-Hook. Es würde ebenfalls den HTML- und JS-Initialisierungscode des Sliders enthalten.
  - `pslider/views/templates/hook/left-column.tpl`: Dieses Template ist speziell für die Platzierung im `displayLeftColumn`-Hook konzipiert. Es würde eine kleinere, potenziell andere Instanz des Sliders oder ein modifiziertes Layout enthalten, das für eine Seitenleiste geeignet ist.
- **Admin-Templates (`views/templates/admin/`)**:

  - `pslider/views/templates/front/form.tpl`: Obwohl sich diese Datei in `views/templates/front/` befindet, wird sie tatsächlich für das Konfigurationsformular des Moduls im Back Office verwendet. Sie definiert die HTML-Struktur für die Einstellungsfelder (Breite, Höhe, Animation, Folienverwaltung usw.), mit denen der Händler interagiert. Dies wird von der `getContent()`-Methode in `ajax_pslider.php` gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Alle Konfigurationseinstellungen und Folien-Daten (Bildpfade, Links, Bildunterschriften, individuelle Animationstypen) werden als serialisierte Arrays in der Tabelle `ps_configuration` gespeichert. Schlüsselnamen würden typischerweise einem Muster wie `PSLIDER_WIDTH`, `PSLIDER_SLIDES` usw. folgen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert im `<head>`-Bereich der Front-Office-Seite oder ganz oben im `<body>`. | Injiziert CSS- und JavaScript-Assets und potenziell die Haupt-HTML-Struktur des Sliders. |
| `displayTop` | Rendert oben im Seiteninhalt, typischerweise über dem Hauptinhaltsbereich, aber unter dem Header. | Zeigt das Haupt-Slider-Banner an. |
| `displayLeftColumn` | Rendert in der linken Seitenleiste der Front-Office-Seite. | Zeigt einen seitenleistenspezifischen Slider an. |
| `displayRightColumn` | Rendert in der rechten Seitenleiste der Front-Office-Seite. | Zeigt einen seitenleistenspezifischen Slider an. |
| `displayFooter` | Rendert im Footer-Bereich der Front-Office-Seite. | Zeigt einen footer-spezifischen Slider an. |
| `displayProductExtraContent` | Rendert auf der Produktseite, typischerweise unter den Hauptproduktinformationen. | Zeigt produktbezogene Slider an (z.B. alternative Ansichten, Funktionen). |
| `displayProductButtons` | Rendert in der Nähe des „In den Warenkorb“-Buttons auf der Produktseite. | Könnte für kleine, kontextbezogene produktbezogene Slider verwendet werden. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien-Assets festlegt. | Ermöglicht dem Modul, seine JS- und CSS-Dateien bedingt zu registrieren. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Prestashop Slider Modul besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
