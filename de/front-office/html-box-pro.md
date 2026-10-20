---
title: "HTML Box Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul HTML Box Pro von MyPresta.eu."
sidebar:
  label: "HTML Box Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul HTML Box Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/html-box-pro/)
>
> ---


# HTML Box Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > HTML Box Pro)

Dies ist der Hauptbildschirm, auf dem Sie alle Ihre HTML-Boxen verwalten. Das Modul zeigt eine Liste der vorhandenen Boxen und Optionen zum Hinzufügen neuer Boxen oder zum Ändern globaler Einstellungen an.

#### Abschnitt Globale Einstellungen

Oben auf der Konfigurationsseite finden Sie einige globale Einstellungen, die die Funktionsweise des Moduls beeinflussen.

- **Internes Modul verwenden**

  - **Was diese Einstellung bewirkt:** Dies ist eine veraltete Einstellung, die sich typischerweise auf den internen Aktualisierungsmechanismus des Moduls bezieht.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Das Modul könnte seine eigenen internen Methoden zur Überprüfung von Updates verwenden.
    - *Wenn deaktiviert („Aus“):* Das Modul verlässt sich auf Standard-PrestaShop-Update-Mechanismen oder manuelle Updates.
  - **Empfohlener Wert:** „An“ (es sei denn, Sie treten Probleme auf, dann versuchen Sie „Aus“).
  - **Händlerszenario / Beispiel:** Lassen Sie dies im Allgemeinen aktiviert. Wenn Sie Probleme mit Modul-Updates oder Benachrichtigungen haben, könnte Ihr Webmaster vorschlagen, dies umzuschalten.
- **URLs aus Bildern nicht entfernen**

  - **Was diese Einstellung bewirkt:** Wenn Sie den integrierten TinyMCE-Editor (den Rich-Text-Editor) verwenden, um Bilder hinzuzufügen, kann dieser manchmal automatisch den vollständigen URL-Pfad entfernen, insbesondere wenn Sie Inhalte kopieren und einfügen. Diese Einstellung verhindert dieses Verhalten.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Bild-URLs, die Sie in den HTML-Box-Inhalt einfügen, werden genau so beibehalten, wie Sie sie eingegeben haben, wodurch defekte Bildlinks verhindert werden.
    - *Wenn deaktiviert („Nicht“):* Der Editor könnte Teile von Bild-URLs ändern oder entfernen, was möglicherweise dazu führt, dass Bilder nicht korrekt angezeigt werden.
  - **Empfohlener Wert:** „An“
  - **Händlerszenario / Beispiel:** Wenn Sie Bilder aus externen Quellen (z.B. einem CDN oder einer anderen Website) oder sogar interne Bilder mit absoluten Pfaden hinzufügen, stellt die Aktivierung dieser Option sicher, dass Ihre Bilder immer angezeigt werden.
- **tinyMCE-Bibliotheken nicht laden**

  - **Was diese Einstellung bewirkt:** TinyMCE ist der Rich-Text-Editor, mit dem Sie Text einfach formatieren, Bilder hinzufügen und Tabellen erstellen können, ohne direkt HTML-Code schreiben zu müssen. Diese Einstellung steuert, ob das Modul seine eigene Version des TinyMCE-Editors lädt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Das Modul lädt seinen TinyMCE-Editor NICHT. Dies kann nützlich sein, wenn Ihr Theme oder ein anderes Modul bereits TinyMCE lädt, um Konflikte oder doppeltes Laden zu vermeiden. Sie verlieren jedoch den visuellen Editor für Ihre HTML-Boxen und müssen reines HTML schreiben.
    - *Wenn deaktiviert („Aus“):* Das Modul lädt seinen TinyMCE-Editor und bietet Ihnen eine benutzerfreundliche Oberfläche zum Erstellen und Bearbeiten Ihrer HTML-Box-Inhalte.
  - **Empfohlener Wert:** „Aus“ (es sei denn, Sie sind Entwickler und bevorzugen es, reines HTML zu schreiben, oder wenn Sie Konflikte mit anderen TinyMCE-Instanzen erleben).
  - **Händlerszenario / Beispiel:** Wenn Sie den visuellen Editor verwenden möchten, um Text, Fett, Kursiv, Bilder und Links einfach hinzuzufügen, ohne HTML zu kennen, lassen Sie dies „Aus“. Wenn Sie seltsames Verhalten mit dem Editor oder Konsolenfehler sehen, könnte ein Entwickler vorschlagen, dies auf „An“ zu stellen, um Fehler zu beheben.

#### Abschnitt HTML-Boxen-Verwaltung

Unterhalb der globalen Einstellungen finden Sie eine Tabelle mit all Ihren erstellten HTML-Boxen. Von hier aus können Sie neue Boxen hinzufügen, bestehende bearbeiten oder löschen.

- **Neue HTML-Box hinzufügen** (Schaltfläche)

  - **Was dies bewirkt:** Durch Klicken auf diese Schaltfläche gelangen Sie zu einem neuen Formular, in dem Sie eine brandneue HTML-Box definieren können.
  - **Auswirkung:** Öffnet das Formular „Neue HTML-Box hinzufügen“.
- **Bearbeiten** (Symbol neben jeder Box)

  - **Was dies bewirkt:** Ermöglicht Ihnen, die Einstellungen und Inhalte einer bestehenden HTML-Box zu ändern.
  - **Auswirkung:** Öffnet das Formular „HTML-Box bearbeiten“, das mit den aktuellen Einstellungen der Box vorausgefüllt ist.
- **Löschen** (Symbol neben jeder Box)

  - **Was dies bewirkt:** Entfernt eine HTML-Box dauerhaft aus Ihrem Shop.
  - **Auswirkung:** Die HTML-Box wird nicht mehr in Ihrem Front Office angezeigt. Diese Aktion ist irreversibel.
  - **Empfohlener Wert:** Löschen Sie nur Boxen, die Sie nicht mehr benötigen.

#### Formular zum Hinzufügen/Bearbeiten von HTML-Boxen

Wenn Sie auf „Neue HTML-Box hinzufügen“ klicken oder eine bestehende „Bearbeiten“, sehen Sie ein Formular mit den folgenden Feldern:

- **Name**

  - **Was diese Einstellung bewirkt:** Dies ist ein interner Name für Ihre HTML-Box, der nur im Back Office sichtbar ist. Er hilft Ihnen, verschiedene Boxen zu identifizieren.
  - **Auswirkung einer Änderung dieser Einstellung:** Ändert die Bezeichnung für diese Box in Ihrer Modulkonfigurationsliste. Keine Front-Office-Auswirkung.
  - **Empfohlener Wert:** Ein aussagekräftiger Name (z.B. „Startseiten-Banner - Sommerschlussverkauf“, „Produktseiten-Vertrauenssiegel“, „Footer-Kontaktinformationen“).
  - **Händlerszenario / Beispiel:** Eine klare Benennung Ihrer Boxen hilft Ihnen, diese schnell zu finden und zu verwalten, insbesondere wenn Ihr Shop wächst und Sie mehr benutzerdefinierte Inhalte hinzufügen.
- **Shop** (Nur in Multi-Store-Umgebungen sichtbar)

  - **Was diese Einstellung bewirkt:** Wenn Sie mehrere Shops von einer einzigen PrestaShop-Installation aus betreiben, können Sie hier festlegen, in welchen Shop(s) diese HTML-Box erscheinen soll.
  - **Auswirkung einer Änderung dieser Einstellung:** Die HTML-Box wird nur in den ausgewählten Shops angezeigt.
  - **Empfohlener Wert:** Wählen Sie die spezifischen Shops aus, in denen der Inhalt relevant ist.
  - **Händlerszenario / Beispiel:** Sie könnten ein anderes Werbebanner für Ihren französischen Shop als für Ihren deutschen Shop haben.
- **Position**

  - **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung, die bestimmt, *wo* in Ihrem Shop die HTML-Box angezeigt wird. Es ist eine Dropdown-Liste aller verfügbaren PrestaShop-Hooks.
  - **Auswirkung einer Änderung dieser Einstellung:** Der Inhalt Ihrer HTML-Box wird an der Position des ausgewählten Hooks gerendert.
  - **Empfohlener Wert:** Wählen Sie den Hook, der am besten zum Zweck des Inhalts passt (z.B. `displayHeader` für ein Top-Banner, `displayLeftColumn` für einen Seitenleistenblock).
  - **Händlerszenario / Beispiel:** Wenn Sie eine „Kostenloser Versand“-Nachricht über Ihren Produktbeschreibungen hinzufügen möchten, wählen Sie `displayProductAdditionalInfo`.
- **Aktiv**

  - **Was diese Einstellung bewirkt:** Steuert, ob die HTML-Box derzeit in Ihrem Shop sichtbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Die HTML-Box wird in Ihrem Front Office angezeigt.
    - *Wenn deaktiviert („Aus“):* Die HTML-Box wird ausgeblendet, aber ihr Inhalt und ihre Einstellungen werden gespeichert, sodass Sie sie später wieder aktivieren können.
  - **Empfohlener Wert:** „An“ für aktive Inhalte, „Aus“ für Inhalte, die Sie vorübergehend ausblenden oder für die zukünftige Verwendung vorbereiten möchten.
  - **Händlerszenario / Beispiel:** Sie können eine Weihnachtsaktionsbox im Voraus vorbereiten, sie auf „Aus“ lassen und dann zum gegebenen Zeitpunkt auf „An“ schalten, ohne sie neu erstellen zu müssen.
- **Nur auf gesicherten (SSL) Seiten**

  - **Was diese Einstellung bewirkt:** Beschränkt die Anzeige der HTML-Box auf Seiten, die über HTTPS (sichere Verbindung) geladen werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Die Box wird nur auf Seiten mit `https://` in der URL angezeigt.
    - *Wenn deaktiviert („Aus“):* Die Box wird sowohl auf sicheren (HTTPS) als auch auf nicht-sicheren (HTTP) Seiten angezeigt (falls Ihr Shop noch HTTP verwendet, was nicht empfohlen wird).
  - **Empfohlener Wert:** „An“, wenn der Inhalt sensible Informationen enthält oder wenn Sie sicherstellen möchten, dass er nur auf sicheren Seiten geladen wird. Im Allgemeinen sollten alle modernen Shops vollständig HTTPS sein, daher ist dies möglicherweise nicht unbedingt erforderlich, aber es bietet eine zusätzliche Kontrollebene.
  - **Händlerszenario / Beispiel:** Wenn Ihre HTML-Box ein Zahlungsabzeichen oder ein Sicherheitssiegel enthält, möchten Sie möglicherweise sicherstellen, dass es nur auf sicheren Seiten angezeigt wird, um das Vertrauen zu stärken.
- **Nur auf Startseite**

  - **Was diese Einstellung bewirkt:** Beschränkt die Anzeige der HTML-Box ausschließlich auf die Startseite Ihres Shops.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert („An“):* Die Box wird nur angezeigt, wenn Kunden Ihre Hauptstartseite besuchen.
    - *Wenn deaktiviert („Aus“):* Die Box wird auf allen Seiten angezeigt, auf denen ihre ausgewählte „Position“ (Hook) verfügbar ist.
  - **Empfohlener Wert:** „Aus“, es sei denn, der Inhalt ist speziell für die Startseite konzipiert.
  - **Händlerszenario / Beispiel:** Ein großes Werbebanner für einen shopweiten Sale würde typischerweise für diese Option auf „An“ gesetzt, wenn Sie es nur auf der Startseite haben möchten, oder auf „Aus“, wenn Sie es im Header auf jeder Seite anzeigen möchten.
- **Inhalte** (Dies ist der Hauptinhaltseditor)

  - **Was diese Einstellung bewirkt:** Hier geben Sie den eigentlichen HTML-, JavaScript- oder CSS-Code ein, der angezeigt werden soll. Es verwendet den TinyMCE Rich-Text-Editor (sofern nicht global deaktiviert) für eine einfache Inhaltserstellung.
  - **Auswirkung einer Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird in Ihrem Front Office im ausgewählten Hook gerendert.
  - **Empfohlener Wert:** Geben Sie Ihren gewünschten Inhalt ein. Sie können verwenden:
    - Einfachen Text
    - HTML (z.B. `<p>Hallo Welt!</p>`, `<img>`-Tags, `<a>`-Links)
    - CSS (in `<style>`-Tags einschließen, z.B. `<style>.my-class { color: red; }</style>`)
    - JavaScript (in `<script>`-Tags einschließen, z.B. `<script>alert('Willkommen!');</script>`)
  - **Händlerszenario / Beispiel:**
    - *HTML:* Hinzufügen eines benutzerdefinierten Bannerbildes: `<img src="https://ihrshop.com/img/cms/banner.jpg" alt="Sommerschlussverkauf" style="width:100%;">`
    - *JavaScript:* Einbetten eines Google Analytics Tracking-Codes: `<script> (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){ (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o), m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m) })(window,document,'script','//www.google-analytics.com/analytics.js','ga'); ga('create', 'UA-XXXXX-Y', 'auto'); ga('send', 'pageview'); </script>`
    - *CSS:* Ändern der Farbe eines bestimmten Elements: `<style> #header .logo { border: 2px solid blue; } </style>`

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfigurationsseite | Internes Modul verwenden | An | Steuert den internen Aktualisierungsmechanismus. |
| Hauptkonfigurationsseite | URLs aus Bildern nicht entfernen | An | Stellt sicher, dass Bild-URLs im Editor erhalten bleiben. |
| Hauptkonfigurationsseite | tinyMCE-Bibliotheken nicht laden | Aus | Aktiviert den visuellen Editor für einfache Inhaltserstellung. |
| Formular Hinzufügen/Bearbeiten | Name | Beschreibender Name | Interne Bezeichnung für die HTML-Box. |
| Formular Hinzufügen/Bearbeiten | Shop | Alle Shops | Wählt aus, welche Shops den Inhalt anzeigen (Multi-Store). |
| Formular Hinzufügen/Bearbeiten | Position | (Hook auswählen) | Bestimmt, wo der Inhalt im Front Office erscheint. |
| Formular Hinzufügen/Bearbeiten | Aktiv | An | Schaltet die Sichtbarkeit der HTML-Box im Front Office um. |
| Formular Hinzufügen/Bearbeiten | Nur auf gesicherten (SSL) Seiten | Aus (oder An, wenn kritisch) | Beschränkt die Anzeige auf HTTPS-Seiten. |
| Formular Hinzufügen/Bearbeiten | Nur auf Startseite | Aus | Beschränkt die Anzeige nur auf die Startseite. |
| Formular Hinzufügen/Bearbeiten | Inhalte | (Ihr HTML/JS/CSS) | Der tatsächlich anzuzeigende Inhalt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine HTML-Box wird im Front Office nicht angezeigt. Was soll ich überprüfen?**
A1:

- **Ist sie aktiv?** Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass der Schalter „Aktiv“ für Ihre Box auf „An“ steht.
- **Korrekte Position (Hook)?** Überprüfen Sie nochmals, ob Sie die richtige „Position“ (Hook) ausgewählt haben, an der der Inhalt erscheinen soll. Einige Hooks sind seitenabhängig (z.B. `displayProductAdditionalInfo` nur auf Produktseiten).
- **Nur Startseite?** Wenn Sie „Nur auf Startseite“ auf „An“ gesetzt haben, wird sie nur auf Ihrer Hauptstartseite angezeigt.
- **Nur SSL?** Wenn „Nur auf gesicherten (SSL) Seiten“ auf „An“ steht, stellen Sie sicher, dass Sie eine HTTPS-Seite betrachten.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren) und Ihren Browser-Cache.
- **Inhaltsfehler:** Wenn Ihr HTML/JS/CSS-Inhalt Fehler enthält, könnte dies die Anzeige der Box verhindern. Versuchen Sie einen einfachen „Hallo Welt“-Text zum Testen.

**F2: Der TinyMCE-Editor (visueller Editor) funktioniert nicht oder sieht seltsam aus.**
A2:

- **Einstellung „tinyMCE-Bibliotheken nicht laden“:** Stellen Sie sicher, dass diese in den globalen Einstellungen des Moduls auf „Aus“ steht, wenn Sie den visuellen Editor verwenden möchten.
- **Theme-Konflikte:** Manchmal können benutzerdefinierte Themes oder andere Module TinyMCE stören. Versuchen Sie, andere Module vorübergehend zu deaktivieren, um zu sehen, ob das Problem behoben wird.
- **Browser-Probleme:** Versuchen Sie einen anderen Browser oder leeren Sie den Cache und die Cookies Ihres Browsers.

**F3: Meine Bilder oder Links sind nach dem Speichern des HTML-Box-Inhalts defekt.**
A3:

- **Einstellung „URLs aus Bildern nicht entfernen“:** Stellen Sie sicher, dass diese in den globalen Einstellungen des Moduls auf „An“ steht.
- **Absolute vs. relative Pfade:** Verwenden Sie immer absolute URLs (beginnend mit `http://` oder `https://`) für Bilder und Links, insbesondere wenn sie extern sind oder wenn Sie möchten, dass sie auf Ihrer gesamten Website konsistent funktionieren.
- **HTML überprüfen:** Überprüfen Sie den generierten HTML-Code im Editor (normalerweise eine Schaltfläche „Quellcode“), um sicherzustellen, dass Ihre `src`- und `href`-Attribute korrekt sind.

**F4: Wie übersetze ich den Inhalt meiner HTML-Boxen für verschiedene Sprachen?**
A4:

- HTML Box Pro unterstützt mehrsprachige Inhalte. Wenn Sie eine HTML-Box bearbeiten, sehen Sie Sprachregisterkarten (z.B. Deutsch, Englisch, Französisch) neben dem Feld „Inhalte“.
- Klicken Sie auf jede Sprachregisterkarte und geben Sie den übersetzten Inhalt für diese spezifische Sprache ein. Das Modul zeigt Ihren Kunden automatisch die korrekte Sprachversion an, basierend auf der von ihnen ausgewählten Shop-Sprache.

**F5: Der Inhalt sieht auf dem Desktop gut aus, ist aber auf Mobilgeräten verzerrt.**
A5:

- **Responsives Design:** Stellen Sie sicher, dass der von Ihnen hinzugefügte HTML-Inhalt responsiv gestaltet ist. Verwenden Sie CSS-Eigenschaften wie `max-width: 100%; height: auto;` für Bilder und ziehen Sie die Verwendung von CSS-Media-Queries innerhalb Ihrer `<style>`-Tags für komplexere Layouts in Betracht.
- **Theme-Responsivität:** Obwohl das Modul selbst responsiv ist, kann es das Layout stören, wenn Ihr benutzerdefiniertes HTML nicht responsiv ist. Testen Sie gründlich auf verschiedenen Geräten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das HTML Box Pro Modul folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für ihre Kernfunktionalität und `getContent()` für ihre Back-Office-Konfiguration nutzt. Es registriert Hooks dynamisch und rendert Inhalte basierend auf gespeicherten Konfigurationen. Das Modul verwendet eine benutzerdefinierte `SmartyTemplatesManager`-Bibliothek zur Verwaltung seiner Back-Office-Formulare und -Templates, die eine konsistente Benutzeroberfläche zum Hinzufügen und Bearbeiten von HTML-Boxen bietet. Inhalte werden in der Tabelle `ps_configuration` gespeichert, wobei jede HTML-Box durch einen eindeutigen Konfigurationsschlüssel repräsentiert wird.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller in den Verzeichnissen `controllers/front` oder `controllers/admin`. Die gesamte Back-Office-Logik wird innerhalb der `getContent()`-Methode der Datei `htmlboxpro.php` behandelt, die Formulare rendert und Übermittlungen verarbeitet. Die Front-Office-Inhaltswiedergabe erfolgt direkt über die Hook-Ausführung innerhalb der Hauptmoduldatei.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder andere Kernklassen in einem `classes/`-Verzeichnis. Die gesamte Datenverwaltung und Geschäftslogik sind in der Hauptmoduldatei `htmlboxpro.php` gekapselt. HTML-Box-Konfigurationen werden direkt in der Tabelle `ps_configuration` gespeichert, mit Schlüsseln wie `hbp_name_X`, `hbp_content_X_Y`, `hbp_hook_X` usw., wobei `X` die Box-ID und `Y` die Sprach-ID ist.

### 4.4 JavaScript-Assets (`views/js/`)

- `htmlboxpro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Bietet JavaScript-Funktionalität für die `SmartyTemplatesManager`-Bibliothek, die zum Rendern und Verwalten der Konfigurationsformulare des Moduls (z.B. Hinzufügen/Bearbeiten von HTML-Boxen) verwendet wird. Dies umfasst dynamische Formularelemente, AJAX-Interaktionen zum Speichern/Laden von Template-Daten und möglicherweise die Tab-Verwaltung.
- `htmlboxpro/views/js/script.js`
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Enthält modulspezifisches JavaScript für die Back-Office-Konfigurationsseite. Dies kann Event-Listener für Formularübermittlungen, dynamische Aktualisierungen der HTML-Box-Liste oder andere UI-Verbesserungen speziell für HTML Box Pro umfassen.
- `htmlboxpro/views/js/tinymce16-force-urls.inc.js`
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Dieses Skript wird geladen, wenn die Option „URLs aus Bildern nicht entfernen“ aktiviert ist. Es enthält die TinyMCE-Konfiguration und Plugins, die speziell darauf ausgelegt sind, zu verhindern, dass der Editor absolute URLs, insbesondere für Bilder, entfernt oder modifiziert. Es stellt sicher, dass `src`-Attribute intakt bleiben.
- `htmlboxpro/views/js/tinymce16.inc.js`
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Dieses Skript enthält die Kerninitialisierung und Konfiguration des TinyMCE-Editors für das Modul. Es definiert die Symbolleiste, Plugins und das allgemeine Verhalten des Editors beim Bearbeiten von HTML-Box-Inhalten. Es wird geladen, wenn die Option „tinyMCE-Bibliotheken nicht laden“ deaktiviert ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- `htmlboxpro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
  - **Umfang:** Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit:** Bietet Styling für die UI-Komponenten der `SmartyTemplatesManager`-Bibliothek, um ein konsistentes Aussehen der Konfigurationsformulare des Moduls innerhalb des PrestaShop Back Office zu gewährleisten.
- `htmlboxpro/views/css/styles.css`
  - **Umfang:** Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit:** Enthält modulspezifische CSS-Regeln für die HTML Box Pro Konfigurationsseite, wie z.B. Styling für die Liste der HTML-Boxen, Schaltflächen oder andere benutzerdefinierte Elemente innerhalb der Admin-Oberfläche des Moduls.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates intensiv für seine Back-Office-Oberfläche.

- **Hook-Templates (`htmlboxpro/`)**:
  - `htmlboxpro/html.tpl`: Dies ist das primäre Front-Office-Template. Es ist für das Rendern des tatsächlichen HTML-Box-Inhalts (`{$htmlboxpro_content}`) innerhalb des ausgewählten Hooks im Front Office verantwortlich.
- **Admin-Templates (`views/templates/admin/`)**:
  - `htmlboxpro/views/templates/admin/_configure/helpers/form/form.tpl`: Dieses Template ist wahrscheinlich eine Überschreibung oder ein spezifisches Template, das vom Konfigurationsformular des Moduls verwendet wird, möglicherweise zur Anpassung der Darstellung von Feldern durch den Standard-PrestaShop `HelperForm`, insbesondere für den TinyMCE-Editor.
- **Admin-Templates (`views/templates/`)**:
  - `htmlboxpro/views/custom_hook_info.tpl`: Zeigt wahrscheinlich Informationen oder Anweisungen zu benutzerdefinierten Hooks an.
  - `htmlboxpro/views/form-add-new.tpl`: Template für das Formular „Neue HTML-Box hinzufügen“.
  - `htmlboxpro/views/form-edit.tpl`: Template für das Formular „HTML-Box bearbeiten“.
  - `htmlboxpro/views/messages.tpl`: Wird verwendet, um Erfolgs-, Fehler- oder Informationsmeldungen im Back Office anzuzeigen.
  - `htmlboxpro/views/scripts.tpl`: Enthält wahrscheinlich JavaScript- und CSS-Assets für die Back-Office-Konfigurationsseite.
- **SmartyTemplatesManager-Bibliotheks-Templates (`htmlboxpro/lib/smartyTemplatesManager/tpl/`, `htmlboxpro/lib/smartyTemplatesManager/views/`)**:
  - `htmlboxpro/lib/smartyTemplatesManager/tpl/example.tpl`: Ein Beispiel-Template, wahrscheinlich für Entwicklungs- oder Demonstrationszwecke innerhalb der Bibliothek.
  - `htmlboxpro/lib/smartyTemplatesManager/views/buttonManager.tpl`: Rendert Schaltflächen oder Aktionslinks innerhalb der `SmartyTemplatesManager`-Oberfläche.
  - `htmlboxpro/lib/smartyTemplatesManager/views/createTemplateForm.tpl`: Wird zum Erstellen neuer Templates/Elemente im `SmartyTemplatesManager`-Kontext verwendet.
  - `htmlboxpro/lib/smartyTemplatesManager/views/editTemplateForm.tpl`: Wird zum Bearbeiten bestehender Templates/Elemente im `SmartyTemplatesManager`-Kontext verwendet.
  - `htmlboxpro/lib/smartyTemplatesManager/views/mainForm.tpl`: Der Haupt-Wrapper oder die Struktur für Formulare, die vom `SmartyTemplatesManager` verwaltet werden.
  - `htmlboxpro/lib/smartyTemplatesManager/views/selectInput.tpl`: Ein generisches Template zum Rendern eines Dropdown-Auswahlfeldes.
  - `htmlboxpro/lib/searchTool/views/scripts.tpl`: Enthält wahrscheinlich JavaScript- und CSS-Assets für eine Suchwerkzeugkomponente innerhalb des Back Office.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationen für HTML-Boxen werden in der Standard-PrestaShop-Tabelle `ps_configuration` gespeichert.
  - Konfigurationsschlüssel folgen einem Muster wie:
    - `HBP_NAME_{ID}`: Name der HTML-Box.
    - `HBP_CONTENT_{ID}_{LANG_ID}`: Der eigentliche HTML/JS/CSS-Inhalt für eine bestimmte Box und Sprache.
    - `HBP_HOOK_{ID}`: Der Name des Hooks, in dem die Box angezeigt wird.
    - `HBP_ACTIVE_{ID}`: Boolescher Wert (0/1), der angibt, ob die Box aktiv ist.
    - `HBP_SSL_{ID}`: Boolescher Wert (0/1), der angibt, ob sie nur auf SSL-Seiten angezeigt wird.
    - `HBP_HOMEPAGE_{ID}`: Boolescher Wert (0/1), der angibt, ob sie nur auf der Startseite angezeigt wird.
    - `HBP_SHOP_{ID}`: Kommagetrennte Liste von Shop-IDs (für Multi-Store).
    - `HBP_LAST_ID`: Speichert die zuletzt verwendete ID für eine HTML-Box, um eindeutige IDs zu generieren.
    - `HBP_NOTINYJS`: Globale Einstellung für „tinyMCE-Bibliotheken nicht laden“.
    - `HBP_FORCEURLS`: Globale Einstellung für „URLs aus Bildern nicht entfernen“.
    - Andere Schlüssel wie `MYPRESTA_UPDATES`, `UPDATE_HTMLBOXPRO`, `UPDATEV_HTMLBOXPRO` für die Update-Verwaltung.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayAfterCarrier` | Nach der Auswahl des Versanddienstleisters im Checkout. | Anzeige von Inhalten im Zusammenhang mit Versandoptionen oder letzten Schritten. |
| `displayFooterBefore` | Vor dem Haupt-Footer-Inhalt. | Inhalt oberhalb des Standard-Footers hinzufügen. |
| `displayLeftColumn` | In der linken Seitenleiste der entsprechenden Seiten. | Anzeige von Seitenleistenblöcken (z.B. Kategorien, Filter, benutzerdefinierte Informationen). |
| `displayCustomerAccountForm` | Innerhalb des Formulars zur Erstellung/Bearbeitung des Kundenkontos. | Hinzufügen von benutzerdefinierten Feldern oder Informationen zu Kundenkonten. |
| `displayRightColumnProduct` | In der rechten Seitenleiste auf Produktseiten. | Anzeige von produktspezifischen Seitenleisteninhalten (z.B. verwandte Produkte, Vertrauenssiegel). |
| `displayBanner` | Oben auf der Seite, typischerweise für ein shopweites Banner. | Anzeige von Werbebannern oder Ankündigungen. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien (CSS/JS) festlegt. | Einfügen von benutzerdefiniertem CSS/JS in das Back Office (vom Modul für eigene Admin-Assets verwendet). |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Anzeige von Dankesnachrichten, Tracking-Informationen oder Upsells. |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Ideal zum Einfügen von Meta-Tags, Tracking-Skripten oder globalem CSS/JS. |
| `displayCartExtraProductActions` | Innerhalb der Warenkorbzusammenfassung, in der Nähe der Produktaktionen. | Hinzufügen von Inhalten zu Warenkorbartikeln (z.B. Upsells, Cross-Sells, Versandinformationen). |
| `displayFooter` | Im Haupt-Footer-Bereich des Shops. | Hinzufügen von allgemeinen Footer-Inhalten, Links oder Copyright-Informationen. |
| `displayPaymentByBinaries` | Während des Zahlungsauswahlprozesses. | Anzeige von zahlungsbezogenen Informationen oder Vertrauenssiegeln. |
| `displayCustomerLoginFormAfter` | Nach dem Kunden-Login-Formular. | Hinzufügen von Inhalten unter dem Login-Formular (z.B. „Passwort vergessen“-Links, Registrierungsaufforderungen). |
| `displayReassurance` | Innerhalb des Produkt-Reassurance-Blocks (oft unter dem Produktbild). | Anzeige von Vertrauenselementen wie kostenlosem Versand, sicherer Zahlung, einfacher Rücksendung. |
| `displayProductAdditionalInfo` | Unterhalb der Produktbeschreibung oder des Hauptinformationsblocks. | Hinzufügen von zusätzlichen Produktdetails, Größenratgebern oder benutzerdefinierten Inhalten. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum HTML Box Pro Modul gerne zur Verfügung.
