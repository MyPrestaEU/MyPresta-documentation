---
title: "tinyMCE pro - erweiterter Rich-Text-Editor - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul tinyMCE pro - erweiterter Rich-Text-Editor von MyPresta.eu."
sidebar:
  label: "tinyMCE pro - erweiterter Rich-Text-Editor - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul tinyMCE pro - extended rich text editor auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/tinymce-pro-extended-rich-text-editor.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/tinymce-pro-extended-rich-text-editor/)
>
> ---


# tinyMCE pro - erweiterter Rich-Text-Editor

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Haupteinstellungen des Moduls zuzugreifen. Auf diesem Bildschirm können Sie den erweiterten Editor aktivieren oder deaktivieren und seine Kernfunktionen verwalten.

Die Konfigurationsseite für „tinyMCE pro“ ist einfach gehalten, da das Modul hauptsächlich durch das Ersetzen und Erweitern des vorhandenen Editors funktioniert, ohne umfangreiche benutzerspezifische Einstellungen über seine Aktivierung hinaus.

- **Was diese Einstellung bewirkt:** Dieses Modul ersetzt hauptsächlich den Standard-PrestaShop-Editor durch eine erweiterte Version von tinyMCE. Die Konfigurationsseite enthält typischerweise einen „Aktivieren/Deaktivieren“-Schalter für das Modul selbst und möglicherweise Optionen zur Steuerung, auf welche spezifischen Bereiche des Back-Office der erweiterte Editor angewendet werden soll.
- **Auswirkung einer Änderung dieser Einstellung:**

  - *Wenn aktiviert:* Der standardmäßige, oft eingeschränkte Texteditor in Bereichen wie Produktbeschreibungen, CMS-Seiten und Kategoriebeschreibungen wird durch den Editor „tinyMCE pro“ ersetzt. Dieser neue Editor verfügt über eine reichhaltigere Symbolleiste mit Optionen für Font Awesome-Symbole, YouTube-Videoeinbettung, erweiterte HTML-/JavaScript-Code-Akzeptanz und mehr.
  - *Wenn deaktiviert:* Das Modul funktioniert nicht mehr, und PrestaShop kehrt zu seinem Standard-Texteditor zurück. Alle erweiterten Funktionen von „tinyMCE pro“ sind nicht mehr verfügbar.
- **Empfohlener Wert:** **Aktiviert**. Um die Funktionen des Moduls nutzen zu können, sollte es immer aktiviert sein.
- **Händlerszenario / Beispiel:** Sie bearbeiten eine Produktbeschreibung für einen neuen Artikel. Mit aktiviertem „tinyMCE pro“ können Sie ganz einfach ein YouTube-Video hinzufügen, das das Produkt vorstellt, Font Awesome-Symbole für Funktionen (z. B. ein Häkchen-Symbol für „Auf Lager“) einfügen und erweiterte Formatierungen verwenden, um ein visuell ansprechendes Layout zu erstellen, alles direkt im Editor. Wenn es deaktiviert ist, wären Sie auf grundlegende Textformatierungen beschränkt.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | **Modulstatus (Aktivieren/Deaktivieren)** | Aktiviert | Steuert, ob der erweiterte tinyMCE-Editor den Standard-PrestaShop-Editor im Back-Office ersetzt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul aktiviert, aber der Editor sieht immer noch gleich aus. Was soll ich tun?**
**A1:** Nach der Aktivierung eines Moduls, das das Back-Office modifiziert, ist es ratsam, den Cache Ihres Browsers und den Smarty-Cache von PrestaShop zu leeren.
- **Browser-Cache:** Führen Sie einen Hard-Refresh Ihres Browsers durch (Strg+F5 oder Cmd+Shift+R).
- **PrestaShop-Cache:** Gehen Sie in Ihrem PrestaShop-Back-Office zu **Erweiterte Einstellungen > Performance**. Klicken Sie oben rechts auf die Schaltfläche „Cache leeren“.

**F2: Einige der neuen Editor-Funktionen (wie Font Awesome-Symbole) werden in meinem Front-Office nicht korrekt angezeigt.**
**A2:** Dies deutet in der Regel auf einen Konflikt mit dem CSS oder JavaScript Ihres benutzerdefinierten Themes hin.
- **Auf Konflikte prüfen:** Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (Classic oder Hummingbird) und prüfen Sie, ob die Funktionen korrekt angezeigt werden. Wenn ja, liegt das Problem bei Ihrem benutzerdefinierten Theme.
- **Theme-Anpassung:** Ihr Theme überschreibt möglicherweise notwendiges CSS/JS für diese Elemente oder enthält es nicht. Möglicherweise müssen Sie Ihren Theme-Entwickler oder einen Webmaster konsultieren, um die Front-Office-Assets des Moduls korrekt in Ihr Theme zu integrieren.

**F3: Kann ich diesen Editor für alle Sprachen in meinem Shop verwenden?**
**A3:** Ja, der tinyMCE-Editor ist so konzipiert, dass er nahtlos mit den Mehrsprachigkeitsfunktionen von PrestaShop zusammenarbeitet. Wenn Sie im Back-Office die Sprache wechseln, steht Ihnen der Editor weiterhin zur Verfügung, um Inhalte in der ausgewählten Sprache einzugeben. Das Modul enthält auch Sprachdateien für viele seiner Plugins (z. B. Font Awesome, PowerPaste), um ein lokalisiertes Erlebnis zu gewährleisten, wo verfügbar.

**F4: Ich sehe nach der Installation des Moduls einen Fehler, oder mein Back-Office ist langsam.**
**A4:**
- **Server-Fehlerprotokolle prüfen:** Der erste Schritt ist immer, die PHP-Fehlerprotokolle Ihres Servers zu überprüfen. Diese Protokolle liefern oft spezifische Details darüber, was schiefgelaufen ist.
- **Andere Module deaktivieren:** Deaktivieren Sie vorübergehend andere kürzlich installierte oder komplexe Module, um Konflikte auszuschließen.
- **PHP-Version:** Stellen Sie sicher, dass Ihre PHP-Version innerhalb des unterstützten Bereichs liegt (PHP 7.1 - 8.5). Eine inkompatible PHP-Version kann verschiedene Probleme verursachen.
- **Support kontaktieren:** Wenn das Problem weiterhin besteht, sammeln Sie alle Fehlermeldungen und kontaktieren Sie den MyPresta.eu-Support für Unterstützung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `tinyMCE pro` funktioniert hauptsächlich durch das Überschreiben der Standard-`Validate`-Klasse von PrestaShop, um die Kompatibilität mit den erweiterten HTML-Inhalten zu gewährleisten, die vom erweiterten tinyMCE-Editor generiert werden. Es injiziert seine eigene Version der tinyMCE-Bibliothek und eine Vielzahl von Plugins in das Back-Office und ersetzt so effektiv den Standardeditor. Die Kernlogik des Moduls befindet sich in `index.php`, das die Installation, Deinstallation und das Konfigurationsformular verwaltet. Es nutzt das Hook-System von PrestaShop, um seine Assets zu laden und den Editor bei Bedarf zu initialisieren.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität wird hauptsächlich über die Hauptmoduldatei (`index.php`) und durch das Überschreiben von PrestaShop-Kernklassen integriert.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`tinymcepro/override/classes/index.php`**: Diese Datei ist typischerweise ein leerer Platzhalter, um die Verzeichnisauflistung zu verhindern, eine gängige Sicherheitspraxis. Sie enthält keine funktionalen Klassendefinitionen.
- **`tinymcepro/override/classes/Validate.php`**:
  - **Zweck**: Dies ist ein entscheidendes Override. Die `Validate`-Klasse von PrestaShop ist für die Bereinigung und Validierung verschiedener Eingaben, einschließlich HTML-Inhalten, verantwortlich. Die Standardmethode `isCleanHtml()` kann für Rich Content übermäßig restriktiv sein und gültige HTML5-Elemente, Attribute oder JavaScript entfernen, die der erweiterte tinyMCE-Editor generieren könnte.
  - **Override-Logik**: Dieses Override modifiziert oder erweitert wahrscheinlich die Methode `isCleanHtml()` (oder verwandte Validierungsmethoden), um eine breitere Palette von HTML, Attributen und potenziell eingebetteten Skripten/Stilen zuzulassen, um sicherzustellen, dass der von tinyMCE pro generierte Inhalt nicht von der PrestaShop-Kernvalidierung entfernt oder als ungültig angesehen wird.
  - **Auswirkung**: Entwickler sollten sich bewusst sein, dass dieses Override das Kernvalidierungsverhalten ändert. Wenn benutzerdefinierte Validierungsregeln vorhanden sind oder andere Module auf strikte `isCleanHtml()` angewiesen sind, können Konflikte auftreten.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält eine Vielzahl von JavaScript-Dateien, hauptsächlich für die tinyMCE-Kernbibliothek und ihre zahlreichen Plugins.

- **`tinymcepro/js/accordion.js`**: Wahrscheinlich ein benutzerdefiniertes Skript zur Handhabung der Akkordeon-Funktionalität im Front-Office, möglicherweise im Zusammenhang mit dem `bootstrapaccordion` tinyMCE-Plugin.
- **`tinymcepro/js/alerts.js`**: Benutzerdefiniertes Skript zur Handhabung von Warnmeldungen, möglicherweise an ein Bootstrap-Alert-Plugin gebunden.
- **`tinymcepro/js/fancybox.js`**: Integration der Fancybox-Bibliothek für Lightboxen, wahrscheinlich für die Bild- oder Medienanzeige innerhalb der Editorausgabe verwendet.
- **`tinymcepro/js/readmore.js`**: Skript zur Implementierung der „Weiterlesen“-Funktionalität, die lange Inhaltsabschnitte zusammenklappt.
- **`tinymcepro/js/tinymce-cmscategory.js`**: Spezifisches Initialisierungs- oder Konfigurationsskript für tinyMCE, wenn es in CMS- oder Kategoriebeschreibungsfeldern verwendet wird.
- **`tinymcepro/lib/htmlTemplatesManager/js/htmlTemplatesManager.js`**: Kern-JavaScript für das HTML Templates Manager-Plugin, das die Erstellung, Bearbeitung und Einfügung vordefinierter HTML-Snippets ermöglicht.
- **`tinymcepro/lib/plugins/bootstrapaccordion/plugin.js`**: tinyMCE-Plugin zum Einfügen und Verwalten von Akkordeons im Bootstrap-Stil.
- **`tinymcepro/lib/plugins/codesample/plugin.js`**: tinyMCE-Plugin zum Einfügen und Syntax-Hervorheben von Codebeispielen. Enthält `prism.css` für die Formatierung.
- **`tinymcepro/lib/plugins/editattributes/plugin.js`**: tinyMCE-Plugin zum einfachen Bearbeiten von HTML-Attributen ausgewählter Elemente.
- **`tinymcepro/lib/plugins/fontawesome/langs/*.js`**: Sprachdateien für das Font Awesome tinyMCE-Plugin.
- **`tinymcepro/lib/plugins/lineheight/index.js`, `langs/de.js`, `plugin.js`**: tinyMCE-Plugin zur Steuerung der Zeilenhöhe von Text.
- **`tinymcepro/lib/plugins/paragraph/*.js`**: Ein komplexes Plugin zur Verwaltung von Absatzstilen und möglicherweise zur Anzeige von Blockelementen. Enthält mehrere interne Hilfsskripte.
- **`tinymcepro/lib/plugins/powerpaste/*.js`**: Erweitertes tinyMCE-Plugin zum Bereinigen und Desinfizieren von Inhalten, die aus Microsoft Word, Google Docs usw. eingefügt wurden. Enthält viele Sprachdateien.
- **`tinymcepro/lib/plugins/smileys/plugin.js`**: tinyMCE-Plugin zum Einfügen von Emojis/Smileys.
- **`tinymcepro/lib/plugins/youtube/includes/youtube.js`, `plugin.js`**: tinyMCE-Plugin zum Einbetten von YouTube-Videos.
- **`tinymcepro/lib/tinymce.inc.js`**: Wahrscheinlich die Haupt-tinyMCE-Kernbibliotheksdatei oder eine benutzerdefinierte Build-/Konfigurationsdatei für den Editor.
- **`tinymcepro/lib/tinymce_loader.js`**: Skript, das für das Laden und Initialisieren der tinyMCE-Editorinstanzen im gesamten PrestaShop-Back-Office verantwortlich ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`tinymcepro/css/tinymcepro.css`**: Allgemeine benutzerdefinierte Stile für das Modul, möglicherweise für seine Konfigurationsseite oder Front-Office-Elemente.
- **`tinymcepro/css.css`**: Ein weiteres allgemeines Stylesheet, möglicherweise für ältere PrestaShop-Versionen oder spezifische UI-Elemente.
- **`tinymcepro/lib/editor.css`**: Kern-CSS für den tinyMCE-Editor selbst, das sein Erscheinungsbild im Back-Office definiert.
- **`tinymcepro/lib/htmlTemplatesManager/css/htmlTemplatesManager.css`**: Stile für die Benutzeroberfläche des HTML Templates Managers.
- **`tinymcepro/lib/iconset.css`**: Enthält wahrscheinlich Stile für benutzerdefinierte Symbole, die im Editor oder Modul verwendet werden.
- **`tinymcepro/lib/plugins/bs_alert/assets/css/bootstrap.css`, `plugin.css`**: Bootstrap-CSS und spezifische Plugin-Stile für das Bootstrap Alert tinyMCE-Plugin.
- **`tinymcepro/lib/plugins/bs_images/assets/css/bootstrap.css`, `plugin.css`**: Bootstrap-CSS und spezifische Plugin-Stile für das Bootstrap Images tinyMCE-Plugin.
- **`tinymcepro/lib/plugins/codesample/css/prism.css`**: Stylesheet für die Syntaxhervorhebung, die vom `codesample`-Plugin verwendet wird.
- **`tinymcepro/lib/plugins/powerpaste/css/editorcss.css`**: Stile speziell für das PowerPaste-Plugin, möglicherweise für visuelles Feedback während des Einfügens.
- **`tinymcepro/lib/plugins/tinyplusBootstrapTools/flat-blue.css`, `res-show-blocks-style.css`**: Zusätzliche Bootstrap-bezogene oder Blockanzeigestile, möglicherweise für bestimmte Editor-Themes oder Tools.
- **`tinymcepro/lib/plugins/youtube/includes/youtube.css`**: Stile für die YouTube-Video-Einbettungsfunktion.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **`tinymcepro/header.tpl`**: Diese Vorlage ist wahrscheinlich in `displayHeader` eingehängt, um die notwendigen CSS- und JavaScript-Assets für das Modul zu laden, sowohl im Back-Office (für den Editor selbst) als auch potenziell im Front-Office (für gerenderte Inhalte wie Akkordeons oder Fancybox).
- **`tinymcepro/lib/htmlTemplatesManager/views/buttonManager.tpl`**: Vorlage für die Schaltfläche oder Benutzeroberfläche, die den HTML Templates Manager öffnet.
- **`tinymcepro/lib/htmlTemplatesManager/views/createTemplateForm.tpl`**: Formularvorlage zum Erstellen neuer HTML-Vorlagen.
- **`tinymcepro/lib/htmlTemplatesManager/views/editTemplateForm.tpl`**: Formularvorlage zum Bearbeiten vorhandener HTML-Vorlagen.
- **`tinymcepro/lib/htmlTemplatesManager/views/mainForm.tpl`**: Die Hauptschnittstellenvorlage für den HTML Templates Manager.
- **`tinymcepro/lib/htmlTemplatesManager/views/selectInput.tpl`**: Eine wiederverwendbare Vorlage für ein Dropdown-Auswahlfeld innerhalb des Vorlagenmanagers.
- **`tinymcepro/views/admin/fonts.tpl`**: Vorlage im Zusammenhang mit der Schriftauswahl oder -anzeige, möglicherweise für die Integration benutzerdefinierter Schriftarten in den Editor.
- **`tinymcepro/views/admin/form.tpl`**: Die Hauptkonfigurationsformularvorlage für das Modul, gerendert über `getContent()` in `index.php`.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen. Seine Konfigurationseinstellungen werden in `ps_configuration` gespeichert (z. B. `PS_TINYMCEPRO_ENABLED`). HTML-Vorlagen, die über den `htmlTemplatesManager` erstellt wurden, könnten in einer benutzerdefinierten Tabelle oder serialisiert in `ps_configuration` gespeichert werden, obwohl keine explizite SQL-Datei vorhanden ist, was auf eine dynamische Erstellung oder Konfigurationsspeicherung hindeutet.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Abschnitt des PrestaShop-Back-Office gerendert. | Injiziert notwendige CSS- und JavaScript-Dateien, damit der tinyMCE-Editor und seine Plugins funktionieren. Hier werden die tinyMCE-Kernbibliothek und ihre Initialisierungsskripte geladen. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets festlegt. | Ermöglicht dem Modul, seine spezifischen JS/CSS-Dateien zur aktuellen Admin-Seite hinzuzufügen, um sicherzustellen, dass der tinyMCE-Editor nur auf Seiten geladen wird, auf denen er benötigt wird (z. B. Produktbearbeitung, CMS-Seitenbearbeitung). |
| `actionGetContentEditor` | (Wenn benutzerdefinierter Hook) | Dieser Hook würde verwendet, um die Standard-Editorinstanz durch den erweiterten tinyMCE-Editor des Moduls zu ersetzen. |
| `displayHeader` | Wird im `<head>`-Abschnitt des Front-Office gerendert. | Lädt potenziell Front-Office-spezifische Assets (wie `accordion.js`, `fancybox.js`, `tinymcepro.css`), wenn der vom Editor generierte Inhalt spezielle Stile oder JavaScript benötigt, um korrekt angezeigt zu werden (z. B. Akkordeons, Lightboxen). |
| `displayRightColumn` | Wird in der rechten Spalte des Front-Office gerendert. | (Unwahrscheinlich, dass es direkt für die Editorfunktionalität verwendet wird, könnte aber verwendet werden, um Inhalte anzuzeigen, die vom Editor *erstellt* wurden, wenn das Modul ein Front-Office-Widget hätte). |
| `displayLeftColumn` | Wird in der linken Spalte des Front-Office gerendert. | (Ähnlich wie `displayRightColumn`). |
| `displayFooter` | Wird im Footer des Front-Office gerendert. | Könnte verwendet werden, um nicht-kritische JavaScript- oder CSS-Dateien für die Front-Office-Anzeige zu laden. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung für das Modul „tinyMCE pro - erweiterter Rich-Text-Editor“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei Installation, Konfiguration und Fehlerbehebung zur Seite.
