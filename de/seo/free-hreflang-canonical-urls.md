---
title: "Kostenlose hreflang & canonical urls - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kostenlose hreflang & canonical urls“ von MyPresta.eu."
sidebar:
  label: "Kostenlose hreflang & canonical urls - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Free hreflang & canonical urls auf MyPresta.eu kaufen](https://mypresta.eu/modules/seo/free-hreflang-canonical-urls.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/seo/free-hreflang-canonical-urls/)
>
> ---


# Kostenlose hreflang & canonical urls

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen vorinstalliert. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Kostenlose hreflang & canonical urls“ und klicken Sie auf „Konfigurieren“. Sie sehen dann den Hauptkonfigurationsbildschirm des Moduls.

#### **Konfigurationsoptionen:**

- **Hreflang-Tags aktivieren:**

  - **Was diese Einstellung bewirkt:** Dieser Hauptschalter steuert, ob das Modul `hreflang`-Tags generiert und zum HTML-Header Ihres Shops hinzufügt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul generiert und fügt aktiv `hreflang`-Tags für alle verfügbaren Sprachversionen Ihrer Seiten (Produktseiten, Kategorieseiten, CMS-Seiten usw.) ein. Dies ist entscheidend für die internationale SEO.
    - *Wenn deaktiviert (NEIN):* Es werden keine `hreflang`-Tags von diesem Modul hinzugefügt. Wenn Sie einen mehrsprachigen Shop haben, könnten Suchmaschinen Ihre verschiedenen Sprachversionen als doppelten Inhalt behandeln, was Ihre internationalen Rankings potenziell schädigen könnte.
  - **Empfohlener Wert:** **JA**. Aktivieren Sie dies immer, wenn Ihr Shop mehrere Sprachen unterstützt oder verschiedene Regionen anspricht.
  - **Händlerszenario / Beispiel:** Wenn Sie Produkte sowohl auf Englisch als auch auf Spanisch verkaufen, stellt die Aktivierung sicher, dass ein spanischsprachiger Kunde, der auf Google sucht, die spanische Version Ihrer Produktseite sieht, und ein englischsprachiger Kunde die englische Version.
- **Canonical URLs aktivieren:**

  - **Was diese Einstellung bewirkt:** Dieser Hauptschalter steuert, ob das Modul `canonical`-URL-Tags generiert und zum HTML-Header Ihres Shops hinzufügt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul generiert und fügt aktiv `canonical`-Tags für alle Seiten ein, die auf die bevorzugte Version jeder Seite verweisen. Dies hilft, SEO-Signale zu konsolidieren und Probleme mit doppeltem Inhalt zu vermeiden.
    - *Wenn deaktiviert (NEIN):* Es werden keine `canonical`-Tags von diesem Modul hinzugefügt. Ihr Shop könnte unter Problemen mit doppeltem Inhalt leiden, wenn derselbe Inhalt über mehrere URLs zugänglich ist (z.B. mit oder ohne abschließende Schrägstriche, mit verschiedenen Parametern oder über verschiedene Kategoriepfade).
  - **Empfohlener Wert:** **JA**. Canonical-Tags sind für eine gute SEO auf fast jeder Website von grundlegender Bedeutung.
  - **Händlerszenario / Beispiel:** Eine Produktseite könnte über `ihrshop.com/produktname` und auch `ihrshop.com/kategorie/produktname` zugänglich sein. Die Aktivierung von Canonical URLs teilt Google mit, dass `ihrshop.com/produktname` die Hauptversion ist, wodurch sichergestellt wird, dass alle SEO-Gutschriften auf diese einzelne URL entfallen.
- **x-default hreflang verwenden:**

  - **Was diese Einstellung bewirkt:** Das `x-default`-hreflang-Attribut gibt eine Standardseite an, die Benutzern angezeigt werden soll, wenn keine andere Sprache/Region ihren Browsereinstellungen oder ihrem Standort entspricht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul fügt einen `x-default`-hreflang-Tag hinzu, der typischerweise auf die Standardsprache Ihres Shops oder eine generische internationale Version verweist. Dies ist nützlich für Benutzer, deren Sprache oder Region nicht explizit von Ihren anderen hreflang-Tags angesprochen wird.
    - *Wenn deaktiviert (NEIN):* Es wird kein `x-default`-hreflang-Tag hinzugefügt. Benutzern, deren Sprache/Region keinem spezifischen hreflang entspricht, könnte eine weniger relevante Seite angezeigt werden, oder Suchmaschinen müssten raten, welche Seite angezeigt werden soll.
  - **Empfohlener Wert:** **JA**. Es ist im Allgemeinen eine gute Praxis, ein `x-default` für eine umfassende internationale SEO einzuschließen, insbesondere wenn Sie ein globales Publikum haben.
  - **Händlerszenario / Beispiel:** Wenn Sie englische (US), englische (UK) und französische Versionen haben, aber ein Benutzer aus Deutschland auf Englisch sucht, kann das `x-default` ihn auf Ihre allgemeine englische (US) Seite leiten, um sicherzustellen, dass er immer noch relevante Inhalte erhält.
- **Nur Sprachcode verwenden (z.B. „en“ statt „en-us“):**

  - **Was diese Einstellung bewirkt:** Dies steuert das Format der Sprachcodes, die in Ihren `hreflang`-Tags verwendet werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul verwendet nur den zweistelligen ISO-Sprachcode (z.B. `en`, `fr`, `de`). Dies ist einfacher und geeignet, wenn Sie eine Sprache global ansprechen, anstatt spezifische Regionen.
    - *Wenn deaktiviert (NEIN):* Das Modul verwendet sowohl den Sprach- als auch den Regionscode (z.B. `en-US`, `en-GB`, `fr-CA`). Dies ist präziser und wird empfohlen, wenn Sie unterschiedliche Inhalte oder Preise für bestimmte Länder innerhalb derselben Sprache haben.
  - **Empfohlener Wert:**
    - **NEIN**, wenn Sie eine spezifische regionale Ausrichtung haben (z.B. unterschiedliche englische Inhalte für die USA vs. Großbritannien).
    - **JA**, wenn Ihre verschiedenen Sprachversionen generisch und nicht länderspezifisch sind (z.B. eine „englische“ Version für alle Englischsprachigen).
  - **Händlerszenario / Beispiel:** Wenn Sie auf Englisch verkaufen und eine englische Version für alle Länder haben, wählen Sie JA. Wenn Sie separate englische Inhalte/Preise für die USA und Großbritannien haben, wählen Sie NEIN, um `en-US` und `en-GB` zu verwenden.

#### **Speichern Ihrer Einstellungen:**

Nachdem Sie Ihre Auswahl getroffen haben, klicken Sie auf die Schaltfläche **„Speichern“** am unteren Rand der Konfigurationsseite, um Ihre Änderungen zu übernehmen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Hreflang-Tags aktivieren | JA | Aktiviert hreflang-Tags für internationale SEO. |
| Modulkonfiguration | Canonical URLs aktivieren | JA | Aktiviert Canonical-Tags zur Vermeidung von doppeltem Inhalt. |
| Modulkonfiguration | x-default hreflang verwenden | JA | Bietet eine Fallback-Seite für Benutzer mit nicht übereinstimmender Sprache/Region. |
| Modulkonfiguration | Nur Sprachcode verwenden (z.B. „en“ statt „en-us“) | NEIN (abhängig von der Strategie) | Bestimmt, ob hreflang nur die Sprache (`en`) oder Sprache-Region (`en-US`) verwendet. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul aktiviert, sehe aber keine visuellen Änderungen auf meiner Website. Funktioniert es?**
A1: Ja, es funktioniert wie vorgesehen! Dieses Modul arbeitet vollständig im Hintergrund. Es fügt speziellen Code (hreflang- und Canonical-Tags) zum `<head>`-Bereich des HTML Ihrer Website hinzu, der für Suchmaschinen sichtbar ist, aber nicht für Ihre Kunden. Um zu überprüfen, ob es funktioniert, können Sie mit der rechten Maustaste auf eine beliebige Seite Ihres Shops klicken, „Seitenquelltext anzeigen“ (oder Ähnliches) auswählen und nach „hreflang“ oder „canonical“ suchen. Sie sollten die Tags dort sehen.

**F2: Nach der Aktivierung des Moduls haben sich meine Suchrankings nicht sofort verbessert. Was sollte ich erwarten?**
A2: SEO-Änderungen, insbesondere solche, die das Crawling und die Indexierung betreffen, brauchen Zeit, um sich in den Suchmaschinenergebnissen widerzuspiegeln. Google und andere Suchmaschinen müssen Ihre Website erneut crawlen, die neuen Tags verarbeiten und ihren Index aktualisieren. Dieser Prozess kann einige Tage bis mehrere Wochen oder sogar Monate dauern. Überwachen Sie weiterhin Ihre Google Search Console auf Änderungen in der Indexierung oder in internationalen Targeting-Berichten.

**F3: Mein benutzerdefiniertes Theme hat einige einzigartige URL-Strukturen. Funktioniert dieses Modul trotzdem korrekt?**
A3: Das Modul ist so konzipiert, dass es sich in die Kern-URL-Generierungsmechanismen von PrestaShop integriert. In den meisten Fällen sollte es nahtlos mit benutzerdefinierten Themes funktionieren. Wenn Ihr Theme jedoch die Standard-URL-Weiterleitung oder das Seiten-Rendering von PrestaShop stark modifiziert, besteht eine geringe Wahrscheinlichkeit eines Konflikts. Wenn Sie ein Problem vermuten, leeren Sie zuerst Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**). Wenn die Probleme weiterhin bestehen, wenden Sie sich an den MyPresta.eu-Support mit Details zu Ihrem Theme und spezifischen Seiten, auf denen Sie Probleme feststellen.

**F4: Ich habe einen mehrsprachigen Shop, aber einige Seiten haben keine Übersetzungen für alle Sprachen. Wie geht das Modul damit um?**
A4: Das Modul generiert typischerweise `hreflang`-Tags nur für die Sprachen, für die tatsächlich Inhalte für eine bestimmte Seite verfügbar sind. Wenn ein Produkt oder eine Kategorie nicht in eine bestimmte Sprache übersetzt ist, sollte das Modul keinen `hreflang`-Tag für diese nicht existierende Übersetzung generieren. Stellen Sie sicher, dass Ihre PrestaShop-Übersetzungen im Back Office korrekt verwaltet werden.

**F5: Ich sehe mehrere Canonical-Tags oder falsche hreflang-Tags. Was könnte falsch sein?**
A5: Dies deutet normalerweise auf einen Konflikt mit einem anderen SEO-Modul oder Ihrem Theme hin, das möglicherweise ebenfalls versucht, Canonical- oder hreflang-Tags hinzuzufügen.
1. **Suchen Sie nach anderen SEO-Modulen:** Deaktivieren Sie alle anderen SEO-Module nacheinander, um das Konflikt verursachende zu identifizieren.
2. **Überprüfen Sie Ihr Theme:** Einige Themes könnten Canonical-Tags fest codiert haben.
3. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**), nachdem Sie Moduländerungen vorgenommen haben.
Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Kostenlose hreflang & canonical urls“ (`myhreflang`) ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, `hreflang`- und `canonical`-Meta-Tags in den `<head>`-Bereich der Front-Office-Seiten einzufügen. Es hält sich an die Standard-PrestaShop-Modularchitektur und verwendet Hooks, um seine Funktionalität zu integrieren, ohne Kerndateien zu ändern. Die Modullogik befindet sich hauptsächlich in seiner Haupt-PHP-Datei, `index.php`, die die Konfiguration, Installation, Deinstallation und die Kernlogik für die Tag-Generierung handhabt. Es nutzt die PrestaShop-Klassen `Context` und `Link`, um die aktuelle Seite, verfügbare Sprachen und die Generierung korrekter URLs zu bestimmen.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik wird innerhalb der Hauptmoduldatei und ihrer gehookten Methoden verarbeitet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder `ObjectModel`s in einem `classes/`-Verzeichnis. Die gesamte Kernlogik ist in der Klasse `myhreflang` in `index.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Seine Funktionalität ist rein serverseitige HTML-Tag-Generierung.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Seine Funktionalität ist rein serverseitige HTML-Tag-Generierung und hat keine visuellen Auswirkungen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet ein einziges Smarty-Template, um die `hreflang`- und `canonical`-Tags zu rendern.

- **Hook-Templates (`views/templates/hook/`)**:
  - `myhreflang/views/templates/hook/hreflang.tpl`: Dieses Template ist für die Ausgabe der eigentlichen `<link rel="alternate" hreflang="..." href="..." />` und `<link rel="canonical" href="..." />` Tags verantwortlich.
    - **Gerendert in Hook**: `displayHeader`
    - **Zweck**: Es empfängt ein Array von `hreflang_links` und einen `canonical_link` von der `hookDisplayHeader()`-Methode des Moduls. Es iteriert dann durch diese, um die notwendigen HTML `<link>`-Tags zu generieren.
    - **Verfügbare Variablen**:
      - `$hreflang_links`: Ein Array von assoziativen Arrays, die jeweils `lang_code` (z.B. 'en', 'en-US', 'x-default') und `url` enthalten.
      - `$canonical_link`: Ein String, der die kanonische URL für die aktuelle Seite enthält.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Dieses Modul erstellt **keine** benutzerdefinierten SQL-Tabellen. Es speichert seine Konfigurationseinstellungen direkt in der Tabelle `ps_configuration` unter Verwendung der Standard-PrestaShop-Methoden `Configuration::get()` und `Configuration::updateValue()`.

  - In `ps_configuration` gespeicherte Konfigurationsschlüssel:
    - `MYHREFLANG_HREFLANG_ENABLED` (boolean)
    - `MYHREFLANG_CANONICAL_ENABLED` (boolean)
    - `MYHREFLANG_XDEFAULT_ENABLED` (boolean)
    - `MYHREFLANG_LANG_CODE_ONLY` (boolean)
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Dies ist der primäre Hook, der vom Modul verwendet wird. Er ruft die Methode `hookDisplayHeader()` auf, um die `hreflang`- und `canonical`-`<link>`-Tags zu generieren und in den HTML-`<head>` der Seite einzufügen. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Modul-Updates und weitere Unterstützung mit dem Modul „Kostenlose hreflang & canonical urls“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder technischen Problemen gerne zur Verfügung.
