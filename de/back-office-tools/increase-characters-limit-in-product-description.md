---
title: "Zeichenlimit in der Produktbeschreibung erhöhen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Zeichenlimit in der Produktbeschreibung erhöhen' von MyPresta.eu."
sidebar:
  label: "Zeichenlimit in der Produktbeschreibung erhöhen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Increase characters limit in product description auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/increase-characters-limit-in-product-description.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/increase-characters-limit-in-product-description/)
>
> ---


# Zeichenlimit in der Produktbeschreibung erhöhen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5 (Wird für zukünftige Kompatibilität stets auf PHP 8.5 erweitert)
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modulnamen auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen. Dies ist der Haupt- und einzige Konfigurationsbildschirm für dieses Modul.

#### Einstellungen & Optionen:

1. **Länge der Produktbeschreibung**

   - **Was diese Einstellung bewirkt:** Dieses Feld steuert die maximale Anzahl von Zeichen, die im Hauptfeld „Beschreibung“ für alle Ihre Produkte im PrestaShop Back Office zulässig sind. Die Standardbegrenzung von PrestaShop beträgt 21.844 Zeichen.
   - **Auswirkung einer Änderung dieser Einstellung:**
     - *Bei Einstellung auf eine höhere Zahl:* Sie können beim Bearbeiten von Produkten mehr Zeichen in das Produktbeschreibungsfeld eingeben. Dies ermöglicht detailliertere Inhalte.
     - *Bei Einstellung auf eine niedrigere Zahl (nicht empfohlen):* Sie würden Ihre Fähigkeit einschränken, detaillierte Inhalte hinzuzufügen, und möglicherweise vorhandene längere Beschreibungen kürzen.
   - **Empfohlener Wert:** Eine deutlich höhere Zahl wie `65535` oder `16777215` (was den `MEDIUMTEXT`- oder `LONGTEXT`-Grenzen von MySQL entspricht und praktische Grenzen für die meisten Inhalte effektiv aufhebt). Sie können es auch auf `0` setzen oder leer lassen, um das Limit vollständig zu entfernen und das maximal mögliche zu verwenden.
   - **Händlerszenario / Beispiel:** Sie verkaufen High-Tech-Gadgets und müssen umfangreiche technische Spezifikationen, Kompatibilitätslisten und Benutzerhandbücher direkt in die Produktbeschreibung aufnehmen. Die Einstellung auf `65535` stellt sicher, dass Sie ausreichend Platz haben.
2. **Länge des Produktnamens**

   - **Was diese Einstellung bewirkt:** Dieses Feld steuert die maximale Anzahl von Zeichen, die für das Feld „Produktname“ für alle Ihre Produkte zulässig sind. Die Standardbegrenzung von PrestaShop beträgt typischerweise 128 oder 255 Zeichen, je nach Version.
   - **Auswirkung einer Änderung dieser Einstellung:**
     - *Bei Einstellung auf eine höhere Zahl:* Sie können längere Produktnamen verwenden, was für sehr spezifische Produkte, einschließlich Modellnummern, oder für SEO-Zwecke nützlich sein kann, wo längere, beschreibende Titel vorteilhaft sind.
     - *Bei Einstellung auf eine niedrigere Zahl (nicht empfohlen):* Sie würden die Produktbenennung einschränken, was potenziell Probleme mit bestehenden Produkten verursachen oder die Unterscheidung von Artikeln erschweren könnte.
   - **Empfohlener Wert:** Eine höhere Zahl wie `512` oder `1024`, wenn Sie sehr lange Produktnamen benötigen. Für die meisten Geschäfte ist der Standard ausreichend, aber wenn Sie spezifische Bedürfnisse haben (z.B. die Aufnahme vollständiger Teilenummern oder detaillierter Modellbeschreibungen), ist eine Erhöhung hilfreich.
   - **Händlerszenario / Beispiel:** Sie verkaufen Industrieanlagen, und Produktnamen enthalten oft Hersteller, Modell, spezifische Merkmale und Versionsnummern (z.B. „XYZ Corp. Schwerlast-Industriemischer Modell 5000-A mit variabler Geschwindigkeitsregelung und Edelstahltrichter“). Eine Erhöhung dieses Limits auf `512` ermöglicht es Ihnen, den vollständigen, beschreibenden Namen unterzubringen.
3. **PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG** (Dies ist eine Standard-PrestaShop-Einstellung, die nicht direkt vom Modul gesteuert wird, aber oft für die Inhaltsbearbeitung relevant ist)

   - **Was diese Einstellung bewirkt:** Diese PrestaShop-Kerneinstellung bestimmt, ob Mitarbeiter die Sprache für ein Formularfeld direkt innerhalb des Formulars auswählen können oder ob die Formularsprache durch die Back-Office-Sprache des Mitarbeiters bestimmt wird. Es ist keine Moduleinstellung, aber oft sichtbar oder relevant, wenn es um mehrsprachige Inhalte geht.
   - **Auswirkung einer Änderung dieser Einstellung:**
     - *Wenn aktiviert:* Mitarbeiter können die Sprache für Textfelder (wie Produktbeschreibungen) direkt auf der Produktbearbeitungsseite wechseln, sodass sie Inhalte für verschiedene Sprachen eingeben können, ohne ihre gesamte Back-Office-Sprache ändern zu müssen.
     - *Wenn deaktiviert:* Die Sprache der Textfelder entspricht der aktuellen Back-Office-Sprache des Mitarbeiters. Um Inhalte in einer anderen Sprache zu bearbeiten, muss der Mitarbeiter seine Back-Office-Sprache ändern.
   - **Empfohlener Wert:** Im Allgemeinen **JA** für mehrsprachige Shops mit mehreren Inhaltsredakteuren, da dies den Arbeitsablauf verbessert.
   - **Händlerszenario / Beispiel:** Sie haben einen französischsprachigen und einen englischsprachigen Inhaltsredakteur. Wenn dies aktiviert ist, kann der französische Redakteur die französische Beschreibung schreiben und dann die Sprachauswahl auf Englisch umstellen, um die englische Beschreibung zu schreiben, alles auf derselben Produktseite.

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Länge der Produktbeschreibung | `65535` oder `0` (kein Limit) | Erhöht die maximale Zeichenanzahl für Produktbeschreibungen. Ermöglicht detailliertere Inhalte und bessere SEO. |
| Modulkonfiguration | Länge des Produktnamens | `512` oder `1024` | Erhöht die maximale Zeichenanzahl für Produktnamen. Nützlich für sehr spezifische oder beschreibende Produkttitel. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Zeichenlimit erhöht, aber meine Produktbeschreibungen scheinen im Front Office immer noch abgeschnitten zu sein. Was ist falsch?**
A: Dies ist normalerweise ein Theme-bezogenes Problem, kein Modulproblem.
- **Überprüfen Sie die Anzeigeeinstellungen Ihres Themes:** Einige Themes haben möglicherweise eigene CSS- oder JavaScript-Regeln, die lange Texte kürzen, um sie an ein bestimmtes Designlayout anzupassen. Möglicherweise müssen Sie Ihre Theme-Dokumentation oder einen Webentwickler konsultieren, um diese anzupassen.
- **Smarty-Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung**, scrollen Sie zu „Cache leeren“ und klicken Sie auf „Cache leeren“. Manchmal werden alte Vorlagendateien zwischengespeichert.
- **Im Back Office überprüfen:** Überprüfen Sie nochmals, ob die vollständige Beschreibung auf der Produktbearbeitungsseite in Ihrem Back Office korrekt gespeichert ist. Wenn sie dort abgeschnitten ist, wurde das Modul möglicherweise nicht korrekt angewendet (obwohl dies selten vorkommt).

**F: Beeinflusst dieses Modul SEO?**
A: Indirekt, ja, auf eine sehr positive Weise. Indem es Ihnen ermöglicht, längere, detailliertere und keyword-reichere Produktbeschreibungen zu schreiben, stellen Sie Suchmaschinen mehr Inhalte zum Crawlen und Indexieren zur Verfügung. Dies kann zu besseren Rankings für relevante Suchanfragen führen und mehr organischen Traffic auf Ihre Produktseiten lenken.

**F: Wird dieses Modul meinen Shop verlangsamen?**
A: Nein, dieses Modul hat einen vernachlässigbaren Einfluss auf die Shop-Leistung. Es ändert hauptsächlich Datenbankspaltendefinitionen während der Installation/Konfiguration. Einmal konfiguriert, fügt es keine komplexe Verarbeitung oder Front-Office-Skripte hinzu, die die Ladezeiten der Seite verlangsamen würden. Die einzige potenzielle „Verlangsamung“ könnte auftreten, wenn Sie extrem lange Beschreibungen schreiben, deren Laden aus der Datenbank länger dauert, aber dies ist normalerweise minimal und wird durch die SEO-Vorteile ausgeglichen.

**F: Ich habe die Limits geändert, sehe die Änderung aber nicht auf der Produktbearbeitungsseite. Was soll ich tun?**
A:
- **Modulkonfiguration speichern:** Stellen Sie sicher, dass Sie nach dem Ändern der Zeichenlimits auf der Konfigurationsseite des Moduls auf die Schaltfläche „Speichern“ geklickt haben.
- **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
- **Browser aktualisieren:** Manchmal speichert der Browser alte Formulare. Führen Sie einen Hard Refresh durch (Strg+F5 oder Cmd+Shift+R).
- **Abmelden und wieder anmelden:** Bei einigen administrativen Änderungen kann das Ab- und Wiederanmelden im Back Office sicherstellen, dass alle Sitzungsdaten aktualisiert werden.

**F: Gibt es ein maximales Limit, das ich festlegen kann?**
A: Obwohl das Modul es Ihnen ermöglicht, praktisch jede Zahl einzustellen, wird das praktische Limit durch die Fähigkeiten Ihrer Datenbank bestimmt. Für `TEXT`-Felder in MySQL beträgt das Maximum `65.535` Zeichen. Für `MEDIUMTEXT` sind es `16.777.215` Zeichen und für `LONGTEXT` sind es `4.294.967.295` Zeichen. Das Setzen von `0` oder das Leerlassen des Feldes führt typischerweise zum größten möglichen `TEXT`-Typ, wodurch praktisch alle Grenzen für die meisten Inhalte aufgehoben werden. Für Produktnamen sind `255` oder `512` Zeichen normalerweise mehr als ausreichend.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Zeichenlimit in der Produktbeschreibung erhöhen“ ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, das Datenbankschema für produktbezogene Textfelder zu ändern. Es funktioniert, indem es den `type` und die `size` spezifischer Spalten in der Tabelle `ps_product_lang` (für Beschreibungen) und den Tabellen `ps_product` / `ps_product_lang` (für Namen) während seiner Installation und Konfiguration ändert. Es führt keine Front-Office-Controller, benutzerdefinierten Klassen oder komplexes JavaScript/CSS ein. Seine Kernfunktionalität wird über die Methoden `install()` und `getContent()` der Hauptmodulklasse ausgeführt.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt innerhalb der `getContent()`-Methode des Moduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen ein. Es interagiert direkt mit bestehenden PrestaShop-Kerndatenbanktabellen und Konfigurationseinstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält **keine** benutzerdefinierten Smarty-Template-Dateien. Das Konfigurationsformular wird direkt innerhalb der `getContent()`-Methode unter Verwendung der Standard-`HelperForm`-Komponenten von PrestaShop gerendert.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul interagiert hauptsächlich mit den folgenden PrestaShop-Kerntabellen:

- `ps_product_lang`:
  - **`description`-Spalte**: Geändert zu einem größeren `TEXT`-Typ (z.B. `MEDIUMTEXT` oder `LONGTEXT`), um mehr Zeichen aufzunehmen.
  - **`description_short`-Spalte**: Nicht direkt von diesem Modul geändert, aber oft verwandt.
  - **`name`-Spalte**: Geändert zu einem größeren `VARCHAR`-Typ (z.B. `VARCHAR(512)`), um mehr Zeichen aufzunehmen.
- `ps_configuration`:
  - `chr_max_description_length`: Speichert die konfigurierte maximale Länge für Produktbeschreibungen.
  - `chr_max_name_length`: Speichert die konfigurierte maximale Länge für Produktnamen.
  - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Ein Standard-PrestaShop-Konfigurationsschlüssel, der nicht vom Modul erstellt wird, aber oft im Kontext der Inhaltsbearbeitung referenziert wird.

Die `install()`-Methode des Moduls enthält SQL-Abfragen, um diese Tabellenspalten zu ändern. Die `uninstall()`-Methode versucht, diese Änderungen rückgängig zu machen, obwohl je nach Datenbankstatus eine manuelle Überprüfung erforderlich sein kann.

#### Registrierte Hooks-Tabelle

Dieses Modul registriert **keine** Front-Office- oder Back-Office-Anzeige-Hooks. Seine Funktionalität ist vollständig backend-gesteuert durch die Änderung des Datenbankschemas.

Die `install()`-Methode des Moduls könnte implizit `Configuration::updateValue()` verwenden, was keine Hooks direkt registriert, aber Werte speichert.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Zeichenlimit in der Produktbeschreibung erhöhen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
