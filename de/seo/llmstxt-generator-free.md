---
title: "LLMS.txt Generator Free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul LLMS.txt Generator Free von MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul LLMS.txt Generator Free auf MyPresta.eu kaufen](https://mypresta.eu/modules/seo/llmstxt-generator-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/seo/llmstxt-generator-free/)
>
> ---


# LLMS.txt Generator Free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ihr Server muss das Schreiben von Dateien in das Stammverzeichnis Ihrer PrestaShop-Installation erlauben, damit die `llms.txt`-Datei erstellt und aktualisiert werden kann.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Hauptseite der Moduleinstellungen zuzugreifen. Hier legen Sie fest, welche Inhalte in Ihre `llms.txt`-Datei aufgenommen werden.

#### Allgemeine Einstellungen

- **Shop-Profil (für jede aktive Sprache)**
  - **Was diese Einstellung bewirkt:** Hier können Sie eine kurze, prägnante Beschreibung Ihres Shops in jeder von Ihrem Shop unterstützten Sprache verfassen. Dieses Profil wird in die `llms.txt`-Datei aufgenommen und gibt KI-Modellen einen schnellen Überblick über Ihr Geschäft.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* Der von Ihnen angegebene Text wird der `llms.txt`-Datei hinzugefügt, was KI-Modellen hilft, den Zweck und die Angebote Ihres Shops in bestimmten Sprachen zu verstehen.
    - *Wenn leer gelassen:* Es wird kein Shop-Profil für diese Sprache aufgenommen, was es der KI möglicherweise erschwert, die Essenz Ihres Shops zu erfassen.
  - **Empfohlener Wert:** Füllen Sie dies für jede aktive Sprache aus. Halten Sie es kurz (1-2 Sätze) und beschreibend.
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop Bio-Tierfutter verkauft, könnten Sie schreiben: „MeinShop bietet eine große Auswahl an hochwertigem Bio-Tierfutter und natürlichen Tierbedarfsartikeln für Hunde und Katzen. Wir legen Wert auf Gesundheit, Nachhaltigkeit und glückliche Haustiere.“

#### Inhaltsauswahl

- **Beworbene Kategorien**

  - **Was diese Einstellung bewirkt:** Hier können Sie bestimmte Produktkategorien aus Ihrem Shop auswählen, die Sie für KI-Crawler hervorheben möchten. Diese Kategorien werden explizit in der `llms.txt`-Datei aufgeführt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Kategorien ausgewählt sind:* KI-Modelle werden auf diese Kategorien hingewiesen, was deren Bedeutung signalisiert und möglicherweise ihre Sichtbarkeit in KI-gestützten Suchen erhöht.
    - *Wenn keine Kategorien ausgewählt sind:* KI-Modelle erhalten keine spezifische Anleitung, welche Kategorien aus Ihrer `llms.txt`-Datei priorisiert werden sollen.
  - **Empfohlener Wert:** Wählen Sie 3-5 Ihrer wichtigsten oder meistverkauften Kategorien aus.
  - **Händlerszenario / Beispiel:** Wenn Sie sich auf „Damenkleider“, „Herrenschuhe“ und „Kinderspielzeug“ spezialisiert haben, wählen Sie diese Kategorien aus, um der KI mitzuteilen, dass dies Kernangebote sind.
- **Top 5 Bestseller mit Preisen einschließen**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, identifiziert das Modul automatisch Ihre Top 5 meistverkauften Produkte und fügt deren Namen, Links und aktuelle Preise in die `llms.txt`-Datei ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* KI-Modelle erhalten direkten Zugriff auf Informationen über Ihre beliebtesten Produkte, einschließlich deren Preise, was für KI-gesteuerte Einkaufsempfehlungen entscheidend sein kann.
    - *Wenn deaktiviert:* Ihre Bestseller werden nicht explizit mit ihren Preisen in der `llms.txt`-Datei hervorgehoben.
  - **Empfohlener Wert:** JA. Dies ist eine leistungsstarke Funktion, um Ihre beliebtesten Artikel zu präsentieren.
  - **Händlerszenario / Beispiel:** Ein Kunde fragt eine KI: „Was sind die meistverkauften Artikel bei [Name Ihres Shops]?“ Wenn dies aktiviert ist, kann die KI eine direkte Antwort mit aktuellen Preisen geben.
- **CMS-Seiten einschließen**

  - **Was diese Einstellung bewirkt:** Hier können Sie wichtige statische Inhaltsseiten (wie „Über uns“, „Kontakt“, „Datenschutzrichtlinie“, „Lieferinformationen“) auswählen, die KI-Modelle kennen sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn CMS-Seiten ausgewählt sind:* KI-Modelle werden auf diese Informationsseiten hingewiesen, was ihnen hilft, die Richtlinien, den Hintergrund Ihres Shops und die Kontaktmöglichkeiten zu verstehen.
    - *Wenn keine CMS-Seiten ausgewählt sind:* KI-Modelle müssen diese Seiten möglicherweise durch allgemeines Crawling entdecken, was weniger effizient sein könnte.
  - **Empfohlener Wert:** Wählen Sie alle wesentlichen Informationsseiten aus, die Vertrauen aufbauen und Kundendienstdetails bereitstellen.
  - **Händlerszenario / Beispiel:** Stellen Sie sicher, dass Ihre Seiten „Rückgaberichtlinie“ und „FAQ“ enthalten sind, damit die KI Kundenfragen zu diesen Themen genau beantworten kann.

#### Aktion

- **llms.txt-Datei speichern und neu generieren**
  - **Was diese Schaltfläche bewirkt:** Diese Schaltfläche speichert alle auf dieser Seite konfigurierten Einstellungen und generiert sofort die `llms.txt`-Datei im Stammverzeichnis Ihres Shops mit den aktualisierten Informationen neu.
  - **Auswirkung des Klickens auf diese Schaltfläche:** Ihre `llms.txt`-Datei wird mit Ihren neuesten Auswahlen aktualisiert. Diese Aktion wird auch automatisch ausgelöst, wenn Sie Produkte oder Kategorien in Ihrem Shop aktualisieren.
  - **Empfohlener Wert:** Klicken Sie immer auf diese Schaltfläche, nachdem Sie Änderungen vorgenommen haben, um sicherzustellen, dass Ihre `llms.txt`-Datei auf dem neuesten Stand ist.
  - **Händlerszenario / Beispiel:** Nachdem Sie eine neue „Shop-Profil“-Beschreibung hinzugefügt haben, klicken Sie auf diese Schaltfläche, um sicherzustellen, dass die KI-Crawler die neuen Informationen erhalten.

#### Upgrade auf die Pro-Version (Upsell-Block)

Dieser Abschnitt ist ein Informationsblock, der die Pro-Version des Moduls bewirbt. Er hebt zusätzliche Funktionen hervor, die in der kostenpflichtigen Version verfügbar sind, wie z. B. vollständiger Katalogexport, Crawler-Analysen, Filter und Cronjob-Unterstützung. Dies ist keine konfigurierbare Einstellung, sondern ein Vorschlag für erweiterte Anforderungen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Shop-Profil (pro Sprache) | Für alle Sprachen ausfüllen | Bietet KI-Modellen eine kurze, strukturierte Beschreibung Ihres Shops. |
| Modulkonfiguration | Beworbene Kategorien | 3-5 Schlüsselkategorien auswählen | Leitet KI-Crawler zu Ihren wichtigsten Produktkategorien. |
| Modulkonfiguration | Top 5 Bestseller mit Preisen einschließen | JA | Hebt Ihre beliebtesten Produkte mit aktuellen Preisen für die KI hervor. |
| Modulkonfiguration | CMS-Seiten einschließen | Alle wesentlichen Seiten auswählen | Leitet die KI zu wichtigen Informationsseiten (z. B. Über uns, Kontakt). |
| Modulkonfiguration | llms.txt-Datei speichern und neu generieren | Nach Änderungen klicken | Speichert Einstellungen und aktualisiert die `llms.txt`-Datei im Stammverzeichnis Ihres Shops. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul konfiguriert, sehe aber keine Änderungen auf meiner Website. Funktioniert es?**
A1: Ja, es funktioniert wahrscheinlich richtig! Die `llms.txt`-Datei ist eine technische Datei für KI-Crawler, nicht für menschliche Besucher. Sie werden keine visuellen Änderungen im Front-Office Ihres Shops sehen. Um zu überprüfen, ob es funktioniert, können Sie versuchen, `ihrshop.com/llms.txt` in Ihrem Browser aufzurufen. Dort sollten Sie den generierten Inhalt sehen.

**F2: Ich erhalte eine Fehlermeldung, dass das Modul die `llms.txt`-Datei nicht schreiben kann.**
A2: Dies deutet normalerweise auf ein Problem mit den Dateiberechtigungen auf Ihrem Server hin. Das Modul benötigt die Berechtigung, die `llms.txt`-Datei im Stammverzeichnis Ihres PrestaShop zu erstellen und zu aktualisieren.
- **Lösung:** Kontaktieren Sie Ihren Hosting-Anbieter und bitten Sie ihn sicherzustellen, dass die PrestaShop-Anwendung Schreibberechtigungen (z. B. chmod 755 oder 775 für Verzeichnisse, 644 oder 664 für Dateien) im Stammordner Ihres Shops hat.

**F3: Wie oft wird die `llms.txt`-Datei aktualisiert?**
A3: Die `llms.txt`-Datei wird automatisch neu generiert, wenn Sie:
- Auf die Schaltfläche „llms.txt-Datei speichern und neu generieren“ in der Modulkonfiguration klicken.
- Ein Produkt aktualisieren (z. B. Preis, Name, Beschreibung ändern).
- Eine Kategorie aktualisieren (z. B. Name, Beschreibung ändern).
Dies stellt sicher, dass die Datei immer mit Ihren neuesten Shop-Daten aktuell ist.

**F4: Mein benutzerdefiniertes Theme scheint von diesem Modul nicht betroffen zu sein. Gibt es einen Konflikt?**
A4: Nein, es sollte keinen Konflikt geben. Dieses Modul arbeitet vollständig im Hintergrund und generiert eine Textdatei. Es ändert weder das Design, CSS noch JavaScript Ihres Themes. Sein Zweck ist es, KI-Crawlern strukturierte Daten bereitzustellen, nicht das visuelle Erscheinungsbild Ihres Shops zu ändern.

**F5: Kann ich die `llms.txt`-Datei manuell bearbeiten?**
A5: Es wird dringend empfohlen, die `llms.txt`-Datei **nicht** direkt manuell zu bearbeiten. Alle von Ihnen vorgenommenen Änderungen werden überschrieben, wenn das Modul die Datei das nächste Mal neu generiert (z. B. wenn Sie Einstellungen speichern oder Produkte/Kategorien aktualisieren). Verwenden Sie immer die Konfigurationsoberfläche des Moduls, um dessen Inhalt zu steuern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `LLMS.txt Generator Free` ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf die Generierung einer statischen Textdatei (`llms.txt`) im Stammverzeichnis des Shops konzentriert. Es folgt einer Standard-PrestaShop-Modulstruktur und nutzt die `Module`-Klasse für Installation, Deinstallation und Konfiguration. Die Kernlogik befindet sich in der Hauptmoduldatei und verwaltet die Konfigurationspersistenz und Dateigenerierung. Es verwendet die `Configuration`-Klasse von PrestaShop für Einstellungen und Hooks für die automatische Regenerierung.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik wird innerhalb der `getContent()`-Methode der Hauptmoduldatei für die Konfiguration und über Hooks für Hintergrundoperationen verarbeitet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/`. Es verwendet direkt die Kernklassen von PrestaShop wie `Configuration`, `Product`, `Category`, `CMS`, `Language` und `Shop`.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`llmstxtfree/views/css/admin-config.css`**
  - **Umfang:** Styling des Back-Office-Admin-Formulars.
  - **Wichtigste UI-Komponenten und Container, die es stylt:** Bietet grundlegendes Styling für die Konfigurationsseite des Moduls, wahrscheinlich für Layout, Abstände und möglicherweise einige visuelle Hinweise für den Upsell-Block.
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:** Zielt typischerweise auf Elemente innerhalb der `getContent()`-Ausgabe des Moduls ab, wie z. B. `.panel`, `.form-group` oder benutzerdefinierte Klassen, die in `configure.tpl` definiert sind.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - **`llmstxtfree/views/templates/admin/configure.tpl`**
    - **Zweck:** Dies ist das Haupt-Smarty-Template, das von der `getContent()`-Methode des Moduls gerendert wird. Es definiert die Struktur und Felder für die Konfigurationsseite des Moduls im PrestaShop Back Office.
    - **Inhalt:** Enthält das HTML-Formular für alle in Abschnitt 4.1 beschriebenen Einstellungen, einschließlich Eingabefeldern für das Shop-Profil, die Kategorieauswahl, den Bestseller-Schalter, die CMS-Seitenauswahl und die Speichern-Schaltfläche. Es enthält auch das Template `pro-upsell.tpl`.
  - **`llmstxtfree/views/templates/admin/pro-upsell.tpl`**
    - **Zweck:** Dieses Template ist in `configure.tpl` enthalten und zeigt Werbeinhalte für die Pro-Version des Moduls an.
    - **Inhalt:** Enthält typischerweise Text, Bilder und Links, die den Händler ermutigen, auf die kostenpflichtige Version zu aktualisieren, und hebt zusätzliche Funktionen hervor.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt **keine** benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen (z. B. ausgewählte Kategorien, CMS-Seiten, Shop-Profile, Bestseller-Schalter) in der Standard-PrestaShop-Tabelle `ps_configuration`. Konfigurationsschlüssel folgen typischerweise dem Muster `LLMSTXTFREE_SETTING_NAME`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich von Front-Office-Seiten. | Nicht direkt für die Inhaltsausgabe verwendet, aber oft von Modulen für das Laden von Assets oder die Erstkonfiguration registriert. In diesem Modul wahrscheinlich für die allgemeine Modulinitialisierung oder potenziell für zukünftige Funktionen. |
| `displayRightColumn` | Rendert Inhalte in der rechten Spalte von Front-Office-Seiten. | In diesem Modul nicht für die Inhaltsausgabe verwendet. |
| `displayLeftColumn` | Rendert Inhalte in der linken Spalte von Front-Office-Seiten. | In diesem Modul nicht für die Inhaltsausgabe verwendet. |
| `displayFooter` | Rendert Inhalte in der Fußzeile von Front-Office-Seiten. | In diesem Modul nicht für die Inhaltsausgabe verwendet. |
| `displayProductExtraContent` | Rendert zusätzliche Inhalte auf der Produktseite. | In diesem Modul nicht für die Inhaltsausgabe verwendet. |
| `actionProductUpdate` | Wird ausgeführt, nachdem ein Produkt im Back Office aktualisiert wurde. | **Entscheidend für dieses Modul:** Löst die automatische Regenerierung der `llms.txt`-Datei aus, um sicherzustellen, dass Bestsellerdaten und Produktlinks aktuell sind. |
| `actionCategoryUpdate` | Wird ausgeführt, nachdem eine Kategorie im Back Office aktualisiert wurde. | **Entscheidend für dieses Modul:** Löst die automatische Regenerierung der `llms.txt`-Datei aus, um sicherzustellen, dass beworbene Kategorielinks und -namen aktuell sind. |
| `actionObjectCmsUpdateAfter` | Wird ausgeführt, nachdem eine CMS-Seite aktualisiert wurde. | Löst die automatische Regenerierung der `llms.txt`-Datei aus, um sicherzustellen, dass ausgewählte CMS-Seitenlinks und -titel aktuell sind. |
| `actionObjectCmsAddAfter` | Wird ausgeführt, nachdem eine neue CMS-Seite hinzugefügt wurde. | Löst die automatische Regenerierung der `llms.txt`-Datei aus. |
| `actionObjectCmsDeleteAfter` | Wird ausgeführt, nachdem eine CMS-Seite gelöscht wurde. | Löst die automatische Regenerierung der `llms.txt`-Datei aus. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um zusätzliche Module und Dienste zu erkunden, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul LLMS.txt Generator Free zur Verfügung.
