---
title: "CMS auf der Startseite – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'CMS auf der Startseite' von MyPresta.eu."
sidebar:
  label: "CMS auf der Startseite – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul CMS on homepage auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/cms-on-homepage.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/cms-on-homepage/)
>
> ---


# CMS auf der Startseite

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5 (Wird ständig auf PHP 8.5 erweitert)
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich, und dieses Modul hat keine zusätzlichen speziellen Anforderungen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modul „CMS auf der Startseite“ auf „Konfigurieren“. Sie gelangen zur Hauptkonfigurationsseite.

#### CMS-Seite auswählen

Dies ist die primäre Einstellung für das Modul. Sie ermöglicht es Ihnen, auszuwählen, welche Ihrer bestehenden CMS-Seiten auf der Startseite angezeigt werden sollen.

- **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü listet alle CMS-Seiten auf, die Sie in Ihrem PrestaShop-Shop erstellt haben (zu finden unter **Shop-Parameter > Seiten**). Sie wählen eine dieser Seiten aus.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn eine CMS-Seite ausgewählt ist:* Der Inhalt der ausgewählten CMS-Seite wird abgerufen und auf der Startseite Ihres Shops angezeigt.
  - *Wenn keine CMS-Seite ausgewählt ist (oder wenn Sie Ihre Meinung ändern):* Das Modul zeigt keinen Inhalt an, oder es zeigt den Inhalt der neu ausgewählten Seite an.
- **Empfohlener Wert:** Wählen Sie die CMS-Seite, deren Inhalt Sie prominent auf Ihrer Startseite präsentieren möchten. Dies könnte Ihre Seite „Über uns“, „Versandinformationen“, „Datenschutzrichtlinie“ (wenn Sie sie sehr sichtbar haben möchten) oder eine benutzerdefinierte Seite mit Werbeinhalten sein.
- **Händlerszenario / Beispiel:** Sie haben eine CMS-Seite mit dem Titel „Unsere Geschichte“, die die Geschichte und Werte Ihrer Marke detailliert beschreibt. Wenn Sie hier „Unsere Geschichte“ auswählen, sieht jeder Besucher Ihrer Startseite diesen Inhalt sofort, was dazu beiträgt, eine Markenbindung und Vertrauen aufzubauen.

Nachdem Sie Ihre Auswahl getroffen haben, denken Sie daran, auf die Schaltfläche **„Speichern“** zu klicken, um Ihre Änderungen zu übernehmen.

### 2.2 Kurzübersicht der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | CMS-Seite auswählen | (Zunächst keine ausgewählt) | Wählen Sie aus, welcher CMS-Seiteninhalt auf der Startseite erscheint. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F: Ich habe eine CMS-Seite ausgewählt, aber auf meiner Startseite wird nichts angezeigt. Was ist falsch?**
A:

1. **Cache leeren:** Gehen Sie in Ihrem Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal benötigt PrestaShop eine Cache-Aktualisierung, um neue Inhalte anzuzeigen.
2. **Status der CMS-Seite überprüfen:** Stellen Sie sicher, dass die ausgewählte CMS-Seite selbst aktiv und in Ihrem Shop sichtbar ist (gehen Sie zu **Shop-Parameter > Seiten** und überprüfen Sie ihren Status).
3. **Theme-Kompatibilität:** Obwohl das Modul Standard-PrestaShop-Hooks verwendet, können einige stark angepasste Themes diese Hooks überschreiben oder spezifische Layout-Anforderungen haben. Wenn das Leeren des Caches nicht hilft, wenden Sie sich an Ihren Theme-Entwickler oder den MyPresta.eu-Support.

**F: Der CMS-Inhalt wird angezeigt, sieht aber nicht richtig aus (z. B. falsche Schriftarten, Farben, Layout).**
A: Das Modul fügt lediglich den Inhalt Ihrer CMS-Seite ein. Die Gestaltung (Schriftarten, Farben, Abstände) wird typischerweise durch das CSS Ihres PrestaShop-Themes gesteuert.

1. **Inhalt der CMS-Seite überprüfen:** Stellen Sie sicher, dass sich im Inhalt der CMS-Seite selbst kein benutzerdefiniertes, widersprüchliches HTML oder Inline-Styling befindet, das Probleme verursachen könnte.
2. **Theme-Anpassung:** Möglicherweise müssen Sie Ihrem Theme benutzerdefiniertes CSS hinzufügen, um den CMS-Inhalt visuell besser zu integrieren. Ein Webentwickler kann Ihnen dabei helfen.

**F: Kann ich mehrere CMS-Seiten auf der Startseite anzeigen?**
A: Dieses spezifische Modul ist darauf ausgelegt, *eine* ausgewählte CMS-Seite anzuzeigen. Wenn Sie mehrere separate Blöcke von CMS-Inhalten anzeigen müssen, müssten Sie diese entweder zu einer einzigen CMS-Seite zusammenfassen oder nach einem fortschrittlicheren Content-Management-Modul suchen.

**F: Wie übersetze ich den CMS-Inhalt für verschiedene Sprachen?**
A: Der Inhalt Ihrer CMS-Seite wird direkt innerhalb der PrestaShop-Kern-CMS-Funktionalität verwaltet. Wenn Sie eine CMS-Seite bearbeiten (**Shop-Parameter > Seiten**), können Sie die Sprache auswählen, um deren Inhalt zu bearbeiten. Das Modul zeigt den Inhalt automatisch in der Sprache an, die der Kunde derzeit in Ihrem Shop ausgewählt hat.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „CMS auf der Startseite“ ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, vorhandene CMS-Seiteninhalte in verschiedene Startseiten-Hooks einzufügen. Es folgt einer Standard-PrestaShop-Modulstruktur, die die `Module`-Klasse und ihre `install()`- und `uninstall()`-Methoden für die Einrichtung und Bereinigung sowie `getContent()` für die Back-Office-Konfiguration nutzt. Die Front-Office-Anzeige wird vollständig durch Hook-Registrierung und Smarty-Templates gehandhabt. Es führt keine benutzerdefinierten Controller, Modelle oder komplexes JavaScript ein.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die gesamte Front-Office-Inhaltswiedergabe wird direkt über registrierte Hooks innerhalb der Hauptmoduldatei gehandhabt.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration des Moduls wird über die `getContent()`-Methode der Hauptmodulklasse verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul basiert auf den PrestaShop-Kernklassen `CMS` und `Configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul enthält kein benutzerdefiniertes JavaScript.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul enthält kein benutzerdefiniertes CSS. Der angezeigte CMS-Inhalt erbt das Styling vom aktiven PrestaShop-Theme.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`cmshomepage/views/templates/hook/cmshomepage.tpl`**

  - **Zweck:** Dies ist das primäre Template, das für die Wiedergabe des tatsächlichen Inhalts der ausgewählten CMS-Seite verantwortlich ist. Es ist so konzipiert, dass es in `displayHome` oder `displayHomeTabContent` für die direkte Inhaltsausgabe eingehängt wird.
  - **Variablen:**
    - `{$cms_content}`: Der HTML-Inhalt der ausgewählten CMS-Seite, vom Modul abgerufen und zugewiesen.
  - **Ausgabe:** Rendert den rohen HTML-Inhalt der CMS-Seite.
- **`cmshomepage/views/templates/hook/tab.tpl`**

  - **Zweck:** Dieses Template wird verwendet, wenn das Modul in `displayHomeTab` eingehängt ist. Es generiert das HTML für einen Tab-Header, der beim Klicken den CMS-Inhalt anzeigt.
  - **Variablen:**
    - `{$tab_name}`: Der Titel des Tabs, typischerweise abgeleitet vom Titel der CMS-Seite.
    - `{$tab_id}`: Eine eindeutige ID für den Tab, die verwendet wird, um ihn mit seinem entsprechenden Inhaltsbereich zu verknüpfen.
  - **Ausgabe:** Ein `<li>`-Element, das ein `<a>`-Tag enthält, geeignet zur Aufnahme in eine Tab-Navigationsstruktur.
- **`cmshomepage/views/templates/hook/tabContents.tpl`**

  - **Zweck:** Dieses Template wird verwendet, wenn das Modul in `displayHomeTabContent` eingehängt ist. Es generiert das HTML für den Inhaltsbereich, der einem Tab zugeordnet ist.
  - **Variablen:**
    - `{$tab_id}`: Die eindeutige ID, die mit der ID von `tab.tpl` übereinstimmt.
    - `{$cms_content}`: Der HTML-Inhalt der ausgewählten CMS-Seite.
  - **Ausgabe:** Ein `<div>`-Element mit dem Tab-Inhalt, typischerweise standardmäßig ausgeblendet und über JavaScript angezeigt, wenn der entsprechende Tab angeklickt wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfiguration in der Tabelle `ps_configuration` unter dem Schlüssel `CMSHOMEPAGE_ID_CMS`, um die ID der ausgewählten CMS-Seite zu speichern.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHomeTabContent` | Rendert Inhalt innerhalb eines Startseiten-Tabs. | Gibt `cmshomepage.tpl` oder `tabContents.tpl` mit dem CMS-Inhalt aus. |
| `displayHomeTab` | Rendert einen Tab-Header auf der Startseite. | Gibt `tab.tpl` mit dem CMS-Seitentitel als Tab-Namen aus. |
| `displayHome` | Rendert Inhalt direkt im Hauptbereich der Startseite. | Gibt `cmshomepage.tpl` mit dem CMS-Inhalt aus. |

Die `install()`-Methode des Moduls registriert diese Hooks. Die Methoden `hookDisplayHome()`, `hookDisplayHomeTab()` und `hookDisplayHomeTabContent()` in `cmshomepage.php` sind für das Abrufen des ausgewählten CMS-Seiteninhalts und das Rendern des entsprechenden Templates verantwortlich.

### 4.8 Konfigurationsschlüssel

Das Modul verwendet die folgenden Konfigurationsschlüssel in `ps_configuration`:

- `CMSHOMEPAGE_ID_CMS`: Speichert die `id_cms` der vom Händler ausgewählten CMS-Seite, die auf der Startseite angezeigt werden soll.

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und dedizierten Entwicklersupport verweisen wir auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Stellen Sie sicher, dass Sie die neueste Version des Moduls verwenden, um optimale Leistung und Kompatibilität mit Ihrem PrestaShop-Shop zu gewährleisten.
