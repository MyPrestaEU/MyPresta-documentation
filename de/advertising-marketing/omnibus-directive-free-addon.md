---
title: "Omnibus-Richtlinie – Kostenloses Addon – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Omnibus-Richtlinie – Kostenloses Addon“ von MyPresta.eu."
sidebar:
  label: "Omnibus-Richtlinie – Kostenloses Addon – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Omnibus Directive - Free Addon auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-free-addon.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/omnibus-directive-free-addon/)
>
> ---


# Omnibus-Richtlinie – Kostenloses Addon

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5 (Das Modul ist so konzipiert, dass es mit einer breiten Palette von PHP-Versionen kompatibel ist, bis zu den neuesten stabilen Versionen, die von PrestaShop 9.x unterstützt werden)
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Konfiguration des Moduls zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Omnibus-Richtlinie – Kostenloses Addon“ und klicken Sie auf die Schaltfläche „Konfigurieren“.

#### Allgemeine Einstellungen

- **Omnibus-Richtlinie-Konformität aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul beginnt, Produktpreise zu verfolgen und den niedrigsten 30-Tage-Preis auf Produktseiten anzuzeigen, wenn ein Rabatt aktiv ist.
    - *Wenn deaktiviert (NEIN):* Das Modul stoppt die Preisverfolgung und zeigt keine Omnibus-bezogenen Informationen in Ihrem Shop an.
  - **Empfohlener Wert:** JA (es sei denn, Sie verkaufen nicht an EU-Kunden oder deaktivieren es vorübergehend für Wartungsarbeiten).
  - **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten sicherstellen, dass Ihr Shop konform ist. Sie würden dies auf JA setzen. Wenn Sie ein neues Theme testen und die Anzeige vorübergehend ausblenden möchten, könnten Sie es auf NEIN setzen.
- **Text für niedrigsten Preis anzeigen:**

  - **Was diese Einstellung bewirkt:** Hiermit können Sie den Text anpassen, der vor dem niedrigsten 30-Tage-Preis angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Der den Kunden angezeigte Text spiegelt Ihre benutzerdefinierte Nachricht wider.
    - *Wenn als Standard belassen:* Der Standardtext (z. B. „Niedrigster Preis in den letzten 30 Tagen:“) wird verwendet.
  - **Empfohlener Wert:** „Niedrigster Preis in den letzten 30 Tagen:“ oder ähnlich, um Klarheit für Ihre Kunden zu gewährleisten.
  - **Händlerszenario / Beispiel:** Sie möchten möglicherweise eine leicht abweichende Formulierung wie „Unser niedrigster Preis war kürzlich:“ verwenden, um den Ton Ihrer Marke anzupassen.
- **Auf Produktseite anzeigen (Hook-Auswahl):**

  - **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung bestimmt, *wo* auf Ihrer Produktseite die Informationen zum niedrigsten 30-Tage-Preis angezeigt werden. Das Modul bietet vordefinierte Optionen für gängige Theme-Strukturen (Classic, Hummingbird) und eine Option für einen benutzerdefinierten Hook.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn „Classic Theme-Profil“ ausgewählt ist:* Das Modul versucht, die Preishistorie an einer geeigneten Stelle innerhalb der Standard-Classic-Theme-Struktur einzufügen (z. B. `displayProductPriceBlock` oder `displayProductButtons`).
    - *Wenn „Hummingbird Theme-Profil“ ausgewählt ist:* Das Modul versucht, die Preishistorie an einer geeigneten Stelle innerhalb der Standard-Hummingbird-Theme-Struktur einzufügen.
    - *Wenn „Benutzerdefinierter Hook“ ausgewählt ist:* Sie müssen manuell einen PrestaShop-Hook angeben, an dem das Modul seinen Inhalt anzeigen soll. Dies erfordert einige technische Kenntnisse oder Theme-Anpassungen.
  - **Empfohlener Wert:** Beginnen Sie mit „Classic Theme-Profil“ oder „Hummingbird Theme-Profil“, je nach Ihrem aktiven Theme. Wenn die Anzeige nicht zufriedenstellend ist, konsultieren Sie einen Webmaster für die Integration eines „Benutzerdefinierten Hooks“.
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop das Standard-PrestaShop Classic Theme verwendet, wählen Sie „Classic Theme-Profil“. Wenn Sie auf PrestaShop 8.x aktualisiert haben und das Hummingbird Theme verwenden, wählen Sie „Hummingbird Theme-Profil“. Wenn Sie ein stark angepasstes Theme haben, müssen Sie möglicherweise „Benutzerdefinierter Hook“ verwenden und Ihren Entwickler bitten, `{hook h='displayMyCustomOmnibusHook'}` zu Ihrer Produktseitenvorlage hinzuzufügen.
- **Name des benutzerdefinierten Hooks (wenn oben „Benutzerdefinierter Hook“ ausgewählt ist):**

  - **Was diese Einstellung bewirkt:** Wenn Sie in der vorherigen Einstellung „Benutzerdefinierter Hook“ gewählt haben, können Sie in diesem Feld den genauen Namen des Hooks angeben, an dem das Modul seinen Inhalt rendern soll.
  - **Auswirkung der Änderung dieser Einstellung:** Das Modul zeigt seinen Inhalt nur an, wenn ein Hook mit diesem genauen Namen in der Produktseitenvorlage Ihres Themes vorhanden ist.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben oben „Benutzerdefinierter Hook“ ausgewählt und kennen den genauen Hook-Namen. Beispiel: `displayProductExtraContent`.
  - **Händlerszenario / Beispiel:** Ihr Webmaster hat Ihre Produktseitenvorlage (`product.tpl`) geändert, um `{hook h='displayMyCustomOmnibusHook'}` aufzunehmen. Sie würden dann `displayMyCustomOmnibusHook` in dieses Feld eingeben.

#### Datenverwaltung

- **Omnibus-Daten löschen:**
  - **Was diese Einstellung bewirkt:** Diese Schaltfläche ermöglicht es Ihnen, alle zuvor vom Modul aufgezeichneten Preishistoriedaten zu löschen.
  - **Auswirkung der Änderung dieser Einstellung:** Das Klicken auf diese Schaltfläche entfernt dauerhaft alle historischen Preisaufzeichnungen. Das Modul beginnt dann von neuem mit der Datenerfassung ab dem Zeitpunkt, an dem Produkte angesehen oder aktualisiert werden.
  - **Empfohlener Wert:** Mit Vorsicht verwenden. Löschen Sie Daten nur, wenn Sie die Preishistorie zurücksetzen müssen, z. B. nach einer größeren Überarbeitung des Produktkatalogs oder wenn Sie Datenkorruption vermuten.
  - **Händlerszenario / Beispiel:** Sie haben einen völlig neuen Satz von Produkten mit unterschiedlichen Preisstrategien importiert und möchten sicherstellen, dass die Omnibus-Daten ohne alte Preise neu beginnen. Sie würden auf diese Schaltfläche klicken.

#### 2.1.1 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Omnibus-Richtlinie-Konformität aktivieren | JA | Aktiviert/deaktiviert die Preisverfolgung und -anzeige für die EU-Konformität. |
| Modulkonfiguration | Text für niedrigsten Preis anzeigen | „Niedrigster Preis in den letzten 30 Tagen:“ | Passt den Text an, der vor dem historischen Preis angezeigt wird. |
| Modulkonfiguration | Auf Produktseite anzeigen (Hook-Auswahl) | Classic/Hummingbird-Profil (basierend auf dem Theme) | Bestimmt, wo die Preishistorie auf der Produktseite erscheint. |
| Modulkonfiguration | Name des benutzerdefinierten Hooks | (Leer) | Gibt einen benutzerdefinierten Hook für die Anzeige an, wenn „Benutzerdefinierter Hook“ ausgewählt ist. |
| Modulkonfiguration | Omnibus-Daten löschen | (Schaltfläche) | Löscht alle gespeicherten Preishistoriedaten und erzwingt einen Neustart. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Die Informationen zum niedrigsten Preis werden auf meinen Produktseiten nicht angezeigt.**
A:

1.  **„Omnibus-Richtlinie-Konformität aktivieren“ prüfen:** Stellen Sie sicher, dass diese in der Modulkonfiguration auf JA gesetzt ist.
2.  **„Auf Produktseite anzeigen (Hook-Auswahl)“ überprüfen:** Versuchen Sie, zwischen „Classic Theme-Profil“ und „Hummingbird Theme-Profil“ zu wechseln, wenn Sie unsicher sind, welches am besten zu Ihrem Theme passt.
3.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal erfordern Theme-Änderungen oder Modul-Updates eine Cache-Aktualisierung.
4.  **Auf Rabatte prüfen:** Die Informationen erscheinen nur, wenn ein Produkt tatsächlich rabattiert ist. Stellen Sie sicher, dass für das Produkt, das Sie testen, ein aktiver spezifischer Preis oder eine Katalogpreisregel angewendet wird.
5.  **Benutzerdefiniertes Theme:** Wenn Sie ein stark angepasstes Theme verwenden, kann das Modul den Inhalt möglicherweise nicht automatisch einfügen. Sie müssen wahrscheinlich die Option „Benutzerdefinierter Hook“ verwenden und Ihren Webmaster bitten, diese in die `product.tpl`-Datei Ihres Themes zu integrieren.

**F: Der angezeigte niedrigste Preis scheint falsch oder zu hoch/niedrig zu sein.**
A:

1.  **Datenerfassungszeit:** Das Modul benötigt Zeit, um Daten zu sammeln. Wenn Sie es gerade erst installiert haben, beginnt es erst ab diesem Zeitpunkt mit der Preisverfolgung. Es dauert 30 Tage, um eine vollständige 30-Tage-Historie zu haben.
2.  **Omnibus-Daten löschen:** Wenn Sie vermuten, dass alte, falsche Daten verwendet werden, können Sie in der Modulkonfiguration auf die Schaltfläche „Omnibus-Daten löschen“ klicken. Beachten Sie, dass dadurch die gesamte Historie gelöscht wird und das Modul von Grund auf neu mit der Datenerfassung beginnt.
3.  **Produktkombinationen/Währungen:** Stellen Sie sicher, dass Sie die richtige Kombination und Währung betrachten. Das Modul verfolgt Preise pro Kombination und Währung.

**F: Wird dieses Modul meinen Shop verlangsamen?**
A: Das Modul ist leichtgewichtig konzipiert. Die Preisverfolgung erfolgt im Hintergrund oder während der Produktansichten, und die Anzeige im Front Office ist eine einfache Textausgabe. Jegliche Leistungseinbußen sollten vernachlässigbar sein.

**F: Wie geht dieses Modul mit mehrsprachigen Shops um?**
A: Die Einstellung „Text für niedrigsten Preis anzeigen“ ist übersetzbar. Sie können zu **International > Übersetzungen** gehen, „Übersetzungen installierter Module“ auswählen, Ihr Theme wählen und dann das Modul „Omnibus-Richtlinie – Kostenloses Addon“ auswählen, um den Text in alle Ihre aktiven Sprachen zu übersetzen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Omnibus-Richtlinie – Kostenloses Addon“ folgt einer Standard-PrestaShop-Modularchitektur. Seine Kernfunktionalität befindet sich in der Hauptdatei `index.php`, die als Einstiegspunkt des Moduls fungiert und Installation, Deinstallation, Konfiguration und Hook-Registrierung handhabt. Die Preishistorie wird durch die Beobachtung von Produktpreisänderungen und deren Speicherung verwaltet, wahrscheinlich in einer benutzerdefinierten Tabelle oder `ps_configuration` (obwohl das Dossier keine benutzerdefinierte SQL-Datei angibt, was auf `ps_configuration` oder dynamische Datengenerierung hindeutet). Die Anzeige im Front-Office erfolgt durch das Einhaken in Standard-PrestaShop-Anzeigepunkte, mit spezifischer Logik für Classic- und Hummingbird-Themes.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine explizit im Dossier definiert. Die Front-Office-Logik wird wahrscheinlich direkt in den Hook-Methoden der Hauptmoduldatei behandelt.
- **Back-Office-Admin-Controller**: Keine explizit im Dossier definiert. Die gesamte Back-Office-Konfiguration wird über die Methode `getContent()` der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine explizit im Dossier definiert. Die Logik des Moduls, einschließlich Preisverfolgung und -speicherung, ist wahrscheinlich in der Klasse `Omnifree` in `index.php` gekapselt.
  - **`Omnifree`-Klasse (in `omnifree/index.php`)**:
    - Erweitert `Module`.
    - Handhabt die Modulinstallation (`install()`) und Deinstallation (`uninstall()`).
    - Registriert notwendige Hooks (z. B. `displayHeader`, `displayProductPriceBlock`, `displayProductButtons`, `displayFooter`, `actionProductUpdate`, `actionProductSave`).
    - Verwaltet Konfigurationseinstellungen über `getContent()`.
    - Enthält Methoden zur Preisverfolgung und -abfrage, die wahrscheinlich mit `ps_configuration` interagieren, um historische Preise zu speichern oder diese dynamisch basierend auf der Bestellhistorie zu berechnen.
    - Implementiert Hook-Methoden (`hookDisplayHeader`, `hookDisplayProductPriceBlock`, `hookDisplayProductButtons`, `hookDisplayFooter` usw.), um Inhalte in das Front Office einzufügen.
    - Implementiert Aktions-Hooks (`hookActionProductUpdate`, `hookActionProductSave`), um Preisänderungen aufzuzeichnen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`omnifree/views/js/admin-config.js`**:
  - **Geltungsbereich:** Back-Office.
  - **Zweck:** Dieses Skript handhabt wahrscheinlich das dynamische Verhalten der Konfigurationsseite des Moduls. Dies könnte umfassen:
    - Ein-/Ausblenden des Eingabefelds „Name des benutzerdefinierten Hooks“ basierend auf dem Wert des Dropdown-Menüs „Auf Produktseite anzeigen (Hook-Auswahl)“.
    - AJAX-Aufrufe für die Schaltfläche „Omnibus-Daten löschen“, um die Datenbereinigung ohne vollständiges Neuladen der Seite durchzuführen.
    - Eingabevalidierung oder andere interaktive Elemente auf dem Konfigurationsformular.
  - **Event-Listener:** Hört wahrscheinlich auf `change`-Ereignisse bei Dropdown-Menüs und `click`-Ereignisse bei Schaltflächen innerhalb des Modulkonfigurationsformulars.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`omnifree/views/css/admin-config.css`**:
  - **Geltungsbereich:** Styling des Back-Office-Admin-Formulars.
  - **Zweck:** Bietet spezifisches Styling für Elemente innerhalb der Konfigurationsseite des Moduls im PrestaShop Back Office, um eine konsistente und benutzerfreundliche Admin-Oberfläche zu gewährleisten.
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf spezifische IDs oder Klassen innerhalb der `configure.tpl`-Vorlage ab.
- **`omnifree/views/css/omnibus-classic.css`**:
  - **Geltungsbereich:** Front-Office-Kunden-Styling (speziell für das Classic-Theme).
  - **Zweck:** Enthält CSS-Regeln, um sicherzustellen, dass die angezeigten Informationen zum niedrigsten Preis korrekt gestylt und positioniert sind innerhalb des PrestaShop Classic-Themes, um Konflikte zu vermeiden und die visuelle Harmonie zu erhalten.
  - **Wichtige CSS-Klassenselektoren:** Zielt auf Elemente wie `.product-prices`, `.product-information` oder benutzerdefinierte Klassen ab, die vom Modul für die Preishistorie-Anzeige hinzugefügt wurden.
- **`omnifree/views/css/omnibus-hummingbird.css`**:
  - **Geltungsbereich:** Front-Office-Kunden-Styling (speziell für das Hummingbird-Theme).
  - **Zweck:** Bietet spezifische Styling- und Positionierungsanpassungen für die Informationen zum niedrigsten Preis, wenn das Hummingbird-Theme (Standard von PrestaShop 8.x) aktiv ist.
  - **Wichtige CSS-Klassenselektoren:** Zielt auf Elemente ab, die spezifisch für die Produktseitenstruktur des Hummingbird-Themes sind.
- **`omnifree/views/css/omnibus.css`**:
  - **Geltungsbereich:** Front-Office-Kunden-Styling (allgemein).
  - **Zweck:** Enthält allgemeine, Theme-unabhängige CSS-Regeln für die Anzeige des niedrigsten Preises. Dies könnte grundlegendes Schriftstyling, Farbe oder Ränder umfassen, die unabhängig vom gewählten Theme-Profil gelten.
  - **Wichtige CSS-Klassenselektoren:** Generische Klassen, die in `omnibus.tpl` verwendet werden.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - **`omnifree/views/templates/hook/omnibus.tpl`**:
    - **Zweck:** Dies ist die primäre Front-Office-Vorlage, die für die Darstellung der Informationen zum niedrigsten 30-Tage-Preis verantwortlich ist. Sie wird von den Hook-Methoden des Moduls gerendert (z. B. `hookDisplayProductPriceBlock`, `hookDisplayProductButtons` oder ein benutzerdefinierter Hook).
    - **Variablen:** Erwartet wahrscheinlich Variablen wie `$lowest_price_30_days`, `$currency_symbol`, `$display_text` und möglicherweise `$product_id` oder `$id_product_attribute`.
    - **Ausgabe:** Ein kleines HTML-Snippet, das den konfigurierten Text und den formatierten niedrigsten Preis enthält.
- **Admin-Vorlagen (`views/templates/admin/`)**:
  - **`omnifree/views/templates/admin/configure.tpl`**:
    - **Zweck:** Diese Vorlage rendert das Hauptkonfigurationsformular für das Modul im PrestaShop Back Office. Sie enthält alle in Abschnitt 4.1 beschriebenen Einstellungen.
    - **Variablen:** Empfängt Konfigurationswerte von `getContent()` zum Vorbelegen von Formularfeldern.
    - **Struktur:** Verwendet die Helper-Formularstruktur von PrestaShop (z. B. `AdminForm`), um die Eingabefelder, Schalter und Schaltflächen zu erstellen.
  - **`omnifree/views/templates/admin/pro-teaser.tpl`**:
    - **Zweck:** Diese Vorlage zeigt wahrscheinlich Werbeinhalte oder einen „Teaser“ für eine „Pro“- oder kostenpflichtige Version des Omnibus-Richtlinie-Moduls von MyPresta.eu an. Sie könnte zusätzliche Funktionen hervorheben, die in der Premium-Version verfügbar sind.
    - **Platzierung:** Wahrscheinlich in `configure.tpl` enthalten oder als separater Block auf der Konfigurationsseite angezeigt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Das Dossier weist keine benutzerdefinierten SQL-Dateien aus. Dies deutet darauf hin, dass die Preishistoriedaten entweder:
    1. Direkt in `ps_configuration` als serialisierte Arrays gespeichert werden (weniger effizient für große Datensätze).
    2. Dynamisch basierend auf den Tabellen `ps_order_detail` und `ps_product_attribute_combination` berechnet werden (komplexer, vermeidet aber benutzerdefinierte Tabellen).
    3. Eine benutzerdefinierte Tabelle wird programmatisch innerhalb von `install()` ohne separate SQL-Datei erstellt. Angesichts des Charakters als „Kostenloses Addon“ ist Option 1 oder 2 aus Gründen der Einfachheit wahrscheinlicher.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Geltungsbereich | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Bei jedem Seitenaufruf im `<head>`-Bereich. | Zum Laden der CSS/JS-Assets des Moduls (z. B. `omnibus.css`, `omnibus-classic.css`, `omnibus-hummingbird.css`). |
| `displayProductPriceBlock` | Front-Office | Auf Produktseiten, typischerweise in der Nähe des Preises. | Einer der primären Hooks zur Anzeige der Informationen zum niedrigsten Preis im Classic-Theme. |
| `displayProductButtons` | Front-Office | Auf Produktseiten, typischerweise in der Nähe der Schaltfläche „In den Warenkorb“. | Ein weiterer potenzieller Hook zur Anzeige der Informationen zum niedrigsten Preis im Classic-Theme. |
| `displayFooter` | Front-Office | Am unteren Rand jeder Seite. | Weniger wahrscheinlich für die Preisanzeige, könnte aber für allgemeine Konformitätsmeldungen verwendet werden oder wenn ein benutzerdefinierter Hook hier platziert wird. |
| `actionProductUpdate` | Back-Office | Wenn ein Produkt im Back Office aktualisiert/gespeichert wird. | Zum Auslösen des Preisverfolgungsmechanismus und zur Aufzeichnung des aktuellen Produktpreises für die Historie. |
| `actionProductSave` | Back-Office | Wenn ein Produkt (neu oder bestehend) im Back Office gespeichert wird. | Ähnlich wie `actionProductUpdate`, stellt sicher, dass Preisänderungen erfasst werden. |
| `actionFrontControllerSetMedia` | Front-Office | Bevor ein Front-Controller seine Ausgabe rendert. | Zum bedingten Laden spezifischer CSS/JS basierend auf der aktuellen Seite oder dem Theme. |
| (Benutzerdefinierter Hook-Name) | Front-Office | Wo der Händler `{hook h='CustomHookName'}` in seiner Vorlage platziert. | Ermöglicht eine flexible Platzierung der Anzeige des niedrigsten Preises für stark angepasste Themes. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Omnibus-Richtlinie – Kostenloses Addon“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
