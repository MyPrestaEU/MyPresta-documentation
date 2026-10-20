---
title: "Kategorienblock mit Zähler - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Kategorienblock mit Zähler' von MyPresta.eu."
sidebar:
  label: "Kategorienblock mit Zähler - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Block categories with counter auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/block-categories-with-counter.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/block-categories-with-counter/)
>
> ---


# Kategorienblock mit Zähler

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Kategorienblock mit Zähler“ bietet eine unkomplizierte Konfiguration, die sich hauptsächlich auf das Aktivieren oder Deaktivieren seiner Kernfunktionalität konzentriert.

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ für das Modul „Kategorienblock mit Zähler“ zu dessen Hauptkonfigurationsbildschirm.

#### **Produktzähler anzeigen**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, der steuert, ob die Produktanzahl neben jedem Kategorienamen im Block angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul ruft die Anzahl der aktiven Produkte für jede Kategorie im Kategorienblock ab und zeigt sie an, z.B. „Elektronik (125)“. Dies ist die Kernfunktion des Moduls.
  - *Wenn deaktiviert (NEIN):* Das Modul verhält sich wie ein Standard-Kategorienblock und zeigt nur die Kategorienamen ohne Produktanzahl an. Das Modul zeigt weiterhin den Kategorienbaum an, aber die einzigartige Zählerfunktion ist inaktiv.
- **Empfohlener Wert:** **JA**. Um den Hauptvorteil des Moduls zu nutzen, sollten Sie diese Einstellung aktivieren.
- **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Ihre Kunden schnell sehen, welche Kategorien beliebt oder gut bestückt sind, aktivieren Sie dies. Wenn Sie eine minimalistische Kategorienliste ohne Zahlen bevorzugen, können Sie es deaktivieren, obwohl dies den Zweck der Installation dieses spezifischen Moduls zunichtemachen würde.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfiguration | Produktzähler anzeigen | JA | Steuert, ob die Produktanzahl neben den Kategorienamen angezeigt wird. Die Aktivierung schaltet die Kernfunktion des Moduls ein. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Die Produktanzahlen werden nicht angezeigt oder scheinen falsch zu sein.**
A:

1. **Modulkonfiguration überprüfen:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Kategorienblock mit Zähler“, klicken Sie auf „Konfigurieren“ und stellen Sie sicher, dass „Produktzähler anzeigen“ auf **JA** eingestellt ist.
2. **PrestaShop-Cache leeren:** Navigieren Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindert alter Cache-Inhalt, dass Änderungen sofort angezeigt werden.
3. **Produktstatus:** Stellen Sie sicher, dass die Produkte, die gezählt werden sollen, in Ihren Produkteinstellungen „aktiv“ und „zum Bestellen verfügbar“ sind. Das Modul zählt nur aktive, sichtbare Produkte.
4. **Kategorienzuordnung:** Überprüfen Sie nochmals, ob die Produkte korrekt ihren jeweiligen Kategorien zugeordnet sind.

**F: Der Kategorienblock sieht seltsam aus oder passt nicht zu meinem Theme.**
A: Das Modul erbt das Styling von Ihrem aktiven PrestaShop-Theme.

1. **Theme-Kompatibilität:** Obwohl das Modul mit PrestaShop-Versionen kompatibel ist, können spezifische Theme-Designs manchmal kleinere visuelle Fehlausrichtungen verursachen.
2. **Benutzerdefiniertes CSS:** Wenn Sie ein benutzerdefiniertes Theme oder spezifische Styling-Anforderungen haben, müssen Sie möglicherweise benutzerdefinierte CSS-Regeln zu der `custom.css`-Datei Ihres Themes (oder einer entsprechenden Datei) hinzufügen, um das Erscheinungsbild des Kategorienblocks und des Zählers anzupassen. Ein Webentwickler kann Ihnen dabei helfen.

**F: Kann ich die Position des Kategorienblocks ändern?**
A: Ja, dies ist eine Standardfunktion von PrestaShop.

1. Gehen Sie zu **Design > Positionen** (oder **Design > Theme & Logo > Positionen** in älteren Versionen).
2. Suchen Sie nach dem Hook, in dem das Modul „Kategorienblock mit Zähler“ derzeit angezeigt wird (z.B. `displayLeftColumn`, `displayRightColumn`).
3. Sie können das Modul per Drag & Drop ziehen, um seine Position innerhalb dieses Hooks neu anzuordnen, oder die Schaltfläche „Modul verschieben“ verwenden, um es vollständig in einen anderen Hook zu verschieben.

**F: Verlangsamt dieses Modul meinen Shop?**
A: Das Modul ist auf Effizienz ausgelegt. Es fragt die Datenbank nach Produktanzahlen ab, was ein Standardvorgang ist. Bei sehr großen Shops mit Zehntausenden von Produkten und Kategorien kann es zu minimalen Auswirkungen kommen, aber für die meisten Shops sollte dies vernachlässigbar sein. Stellen Sie sicher, dass Ihr Server die empfohlenen Spezifikationen von PrestaShop für optimale Leistung erfüllt.

**F: Wie übersetze ich das Modul, wenn mein Shop mehrsprachig ist?**
A: Dieses Modul zeigt hauptsächlich Kategorienamen und -nummern an, die bereits vom Kernübersetzungssystem von PrestaShop für Kategorien verwaltet werden. Wenn das Modul selbst spezifische Textzeichenfolgen hätte (z.B. einen Titel für den Block), würden Sie diese über **International > Übersetzungen > Modulübersetzungen** übersetzen. Für dieses spezifische Modul ist der Großteil des Inhalts jedoch dynamisch aus Ihren Kategorien.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Moduls „Kategorienblock mit Zähler“, gedacht für Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das Modul „Kategorienblock mit Zähler“ ist ein leichtgewichtiges, einteiliges PrestaShop-Modul (`block-categories-with-counter.php`). Es erweitert die Kernklasse `Module` und nutzt hauptsächlich das PrestaShop-Hook-System, um seine Funktionalität zu integrieren. Seine Kernlogik dreht sich darum, das Standardverhalten des Kategorienblocks zu überschreiben oder zu erweitern, um Produktanzahlen einzufügen. Es nutzt die PrestaShop `Category`- und `Product`-ObjectModels, um Daten abzurufen.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt innerhalb der Methode `getContent()` der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt **keine** benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/` ein. Es verwendet direkt die Kern-ObjectModels `Category` und `Product` von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Seine Funktionalität ist rein serverseitig gerendert.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Es verlässt sich vollständig auf das Styling, das vom aktiven PrestaShop-Theme für den Standard-Kategorienblock bereitgestellt wird.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält **keine** benutzerdefinierten Template-Dateien in `views/templates/`. Es überschreibt oder modifiziert wahrscheinlich die Ausgabe des Templates des Standard-`blockcategories`-Moduls oder rendert seinen Inhalt direkt innerhalb der `hook`-Methoden. Angesichts seiner Einfachheit ist es sehr wahrscheinlich, dass es die `display`-Methode verwendet, um Inhalte direkt zu rendern, oder es könnte so konzipiert sein, dass es die Ausgabe des Standard-`blockcategories`-Moduls ersetzt, indem es sich in dieselben Positionen einhängt und seinen eigenen HTML-Code bereitstellt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt **keine** benutzerdefinierten Datenbanktabellen. Es speichert seine Konfiguration (insbesondere die Einstellung `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`) in der Standardtabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayLeftColumn` | Rendert den Kategorienblock in der linken Spalte. |
| `displayRightColumn` | Rendert den Kategorienblock in der rechten Spalte. |
| `displayHome` | Rendert den Kategorienblock auf der Startseite. |
| `displayFooter` | Rendert den Kategorienblock im Footer. |
| `displayHeader` | Rendert den Kategorienblock im Header. |

Das Modul generiert dynamisch den HTML-Code für den Kategorienbaum und die Produktanzahlen innerhalb dieser Hook-Methoden, typischerweise unter Verwendung einer rekursiven Funktion zum Aufbau der verschachtelten Listenstruktur.

### 4.8 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - `ps_configuration`: Speichert die primäre Einstellung des Moduls:
    - `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`: Boolescher Wert (0 oder 1), der angibt, ob die Produktanzahlen angezeigt werden sollen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayLeftColumn` | Rendert den Kategorienblock in der linken Spalte. |
| `displayRightColumn` | Rendert den Kategorienblock in der rechten Spalte. |
| `displayHome` | Rendert den Kategorienblock auf der Startseite. |
| `displayFooter` | Rendert den Kategorienblock im Footer. |
| `displayHeader` | Rendert den Kategorienblock im Header. |

Das Modul generiert dynamisch den HTML-Code für den Kategorienbaum und die Produktanzahlen innerhalb dieser Hook-Methoden, typischerweise unter Verwendung einer rekursiven Funktion zum Aufbau der verschachtelten Listenstruktur.

## 5. Offizieller Support & Updates

Für die neuesten Updates, offiziellen Support und zum Herunterladen neuer Versionen des Moduls „Kategorienblock mit Zähler“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
