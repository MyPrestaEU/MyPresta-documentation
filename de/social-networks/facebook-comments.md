---
title: "Facebook Kommentare - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Kommentare von MyPresta.eu."
sidebar:
  label: "Facebook Kommentare - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Comments auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-comments.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-comments/)
>
> ---


# Facebook Kommentare

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst und jedes Modul, das mit externen APIs wie Facebook interagiert, erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“, um auf die Einstellungen des Moduls zuzugreifen. Hier steuern Sie, wie das Facebook Kommentarfeld auf Ihren Produktseiten erscheint und funktioniert.

#### 2.1.1 Facebook App ID

- **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Kennung für Ihre Facebook App. Obwohl das Modul auch ohne sie funktionieren kann, erhalten Sie durch die Angabe einer App ID Zugriff auf die Moderationstools und Einblicke von Facebook für die Kommentare auf Ihrer Website.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn angegeben:* Sie erhalten Zugriff auf das Facebook-Kommentar-Moderationspanel (developers.facebook.com/tools/comments), wo Sie Kommentare überprüfen, genehmigen oder löschen können. Es hilft Facebook auch, die Kommentare Ihrer spezifischen Website zuzuordnen.
  - *Wenn leer gelassen:* Kommentare werden weiterhin angezeigt, aber Sie haben keine erweiterten Moderationsfunktionen über die Facebook-Entwicklertools. Sie verlassen sich auf die Standard-Spamfilterung von Facebook.
- **Empfohlener Wert:** Es wird dringend empfohlen, eine Facebook App zu erstellen und Ihre App ID hier einzugeben, um eine bessere Kontrolle und Moderation zu ermöglichen.
- **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass alle Kommentare angemessen und themenbezogen sind. Durch die Einrichtung einer Facebook App ID können Sie Kommentare einfach direkt über das Facebook-Entwickler-Dashboard moderieren und Spam oder unangemessene Inhalte entfernen.

#### 2.1.2 Anzahl der Kommentare

- **Was diese Einstellung bewirkt:** Dies steuert, wie viele Kommentare anfänglich im Facebook Kommentarfeld angezeigt werden, bevor Benutzer auf „Weitere Kommentare anzeigen“ oder „Mehr laden“ klicken müssen, um ältere Kommentare zu sehen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf eine niedrige Zahl eingestellt (z.B. 5):* Der Kommentarbereich wird kompakter, und Benutzer müssen klicken, um mehr zu sehen. Dies kann gut für Seiten mit begrenztem Platz sein oder wenn Sie die anfängliche Seitenladezeit geringer halten möchten.
  - *Wenn auf eine höhere Zahl eingestellt (z.B. 20):* Mehr Kommentare sind sofort sichtbar, was auf den ersten Blick mehr sozialen Beweis liefert. Es könnte jedoch die Produktseite länger machen.
- **Empfohlener Wert:** 5-10 Kommentare sind ein guter Ausgangspunkt, um Sichtbarkeit und Seitenlänge auszugleichen. Passen Sie dies basierend auf dem Design Ihrer Produktseite und dem typischen Kommentarvolumen an.
- **Händlerszenario / Beispiel:** Für beliebte Produkte mit vielen Kommentaren könnten Sie dies auf 5 setzen, um die Seite übersichtlich zu halten. Für neuere Produkte könnte das Einstellen auf 10 mehr Interaktion fördern, indem mehr bestehende Kommentare angezeigt werden.

#### 2.1.3 Breite des Kommentarfeldes

- **Was diese Einstellung bewirkt:** Dies bestimmt die Breite des Facebook Kommentarfeldes in Pixeln.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf einen bestimmten Pixelwert eingestellt (z.B. 600px):* Das Kommentarfeld behält diese feste Breite bei, was potenziell leeren Raum erzeugen oder überlaufen kann, wenn der Inhaltsbereich Ihres Themes schmaler oder breiter ist.
  - *Wenn leer gelassen oder auf 100% eingestellt (falls vom Modul unterstützt):* Das Kommentarfeld versucht, sich automatisch an die verfügbare Breite seines übergeordneten Containers anzupassen, wodurch es responsiv wird.
- **Empfohlener Wert:** Leer lassen für automatische Erkennung oder auf 100% setzen, wenn das Modul dies unterstützt, um Responsivität zu gewährleisten. Wenn Sie eine feste Breite benötigen, stellen Sie sicher, dass sie in den Inhaltsbereich Ihres Themes passt.
- **Händlerszenario / Beispiel:** Ihre Produktseite hat eine Hauptinhaltsspalte, die 700px breit ist. Sie könnten die Breite auf 700px einstellen, um diesen Platz perfekt auszufüllen. Wenn Sie möchten, dass es sich an mobile Geräte anpasst, ist es normalerweise am besten, es leer zu lassen.

#### 2.1.4 Sprache des Kommentarfeldes

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, die Sprache für die Benutzeroberfläche des Facebook Kommentare-Plugins festzulegen (z.B. „Kommentar schreiben…“, „Weitere Kommentare anzeigen“).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf einen bestimmten Sprachcode eingestellt (z.B. „en\_US“ für Englisch, „fr\_FR“ für Französisch):* Der Text des Facebook-Plugins wird in dieser Sprache angezeigt, unabhängig von der Browsersprache des Benutzers oder der aktiven Sprache Ihres PrestaShop-Shops.
  - *Wenn leer gelassen:* Facebook versucht typischerweise, die bevorzugte Sprache des Benutzers oder die Sprache Ihres PrestaShop-Shops zu erkennen.
- **Empfohlener Wert:** Es ist im Allgemeinen am besten, dies leer zu lassen, damit Facebook die Sprache des Benutzers automatisch erkennen kann, oder es auf die primäre Sprache Ihres Shops einzustellen, wenn Sie Konsistenz wünschen.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop hauptsächlich Kunden in Deutschland anspricht, könnten Sie dies auf „de\_DE“ einstellen, um sicherzustellen, dass der gesamte Text des Facebook-Plugins auf Deutsch ist, selbst wenn der Browser eines Benutzers auf Englisch eingestellt ist.

#### 2.1.5 Position des Kommentarfeldes

- **Was diese Einstellung bewirkt:** Dies bestimmt, wo auf der Produktseite das Facebook Kommentarfeld angezeigt wird. Sie können aus verschiedenen PrestaShop-Hooks wählen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf `displayProductButtons` (oder ähnlich) eingestellt:* Das Kommentarfeld könnte in der Nähe des „In den Warenkorb“-Buttons oder anderer Produktaktionen erscheinen.
  - *Wenn auf `displayFooterProduct` (oder ähnlich) eingestellt:* Das Kommentarfeld erscheint weiter unten auf der Produktseite, oft unter den Hauptproduktdetails, was ein üblicher und normalerweise bevorzugter Ort ist.
  - *Wenn auf `displayRightColumn` oder `displayLeftColumn` (falls verfügbar) eingestellt:* Das Kommentarfeld würde in einer der Seitenleisten Ihres Shops erscheinen, was für Kommentare weniger üblich ist und visuell möglicherweise nicht ideal ist.
- **Empfohlener Wert:** `displayFooterProduct` oder ein ähnlicher Hook, der den Kommentarbereich unter den Hauptproduktinformationen platziert, ist normalerweise die natürlichste und effektivste Platzierung.
- **Händlerszenario / Beispiel:** Sie möchten, dass die Kommentare sichtbar sind, aber nicht vom primären Ziel ablenken, das Produkt in den Warenkorb zu legen. Die Platzierung in `displayFooterProduct` stellt sicher, dass Kunden zuerst alle Produktdetails sehen und dann mit Kommentaren interagieren können.

#### 2.1.6 Facebook Kommentare aktivieren

- **Was diese Einstellung bewirkt:** Dies ist ein einfacher EIN/AUS-Schalter, um die gesamte Facebook Kommentare-Funktionalität zu aktivieren oder zu deaktivieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Facebook Kommentarfeld wird auf Ihren Produktseiten gemäß Ihren anderen Einstellungen angezeigt.
  - *Wenn deaktiviert (NEIN):* Das Facebook Kommentarfeld wird vollständig von Ihren Produktseiten ausgeblendet, und das Modul lädt keine Facebook-bezogenen Skripte.
- **Empfohlener Wert:** JA, wenn Sie die Funktion nutzen möchten.
- **Händlerszenario / Beispiel:** Sie haben die Einrichtung des Moduls abgeschlossen und möchten es in Ihrem Shop live schalten. Sie stellen dies auf JA. Später, wenn Sie Kommentare vorübergehend für Wartungsarbeiten deaktivieren möchten, können Sie es auf NEIN stellen.

#### 2.1.7 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Facebook App ID | (Leer) / Empfohlen: Ihre App ID | Aktiviert Facebook-Moderationstools für Kommentare. |
| Modulkonfiguration | Anzahl der Kommentare | 5-10 | Legt fest, wie viele Kommentare anfänglich sichtbar sind. Beeinflusst die Seitenlänge. |
| Modulkonfiguration | Breite des Kommentarfeldes | (Leer) / Automatische Erkennung (Responsiv) | Definiert die Breite des Kommentarbereichs. Leer für Responsivität. |
| Modulkonfiguration | Sprache des Kommentarfeldes | (Leer) / Automatische Erkennung | Legt die Sprache der Facebook-Plugin-Oberfläche fest. Leer für Benutzer-/Shop-Sprache. |
| Modulkonfiguration | Position des Kommentarfeldes | `displayFooterProduct` | Bestimmt, wo auf der Produktseite das Kommentarfeld erscheint. |
| Modulkonfiguration | Facebook Kommentare aktivieren | JA | Schaltet die gesamte Facebook Kommentare-Funktion EIN oder AUS. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Das Facebook Kommentarfeld wird auf meinen Produktseiten nicht angezeigt. Was soll ich tun?**
A:

1. **„Facebook Kommentare aktivieren“ überprüfen:** Stellen Sie sicher, dass diese Einstellung in der Modulkonfiguration auf JA gesetzt ist.
2. **Position überprüfen:** Stellen Sie sicher, dass die Einstellung „Position des Kommentarfeldes“ auf einen Hook gesetzt ist, der tatsächlich von Ihrem Theme auf den Produktseiten vorhanden und gerendert wird (z.B. `displayFooterProduct`). Einige benutzerdefinierte Themes verwenden möglicherweise nicht alle Standard-Hooks.
3. **Cache leeren:** Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“). Manchmal verhindert alter Cache-Inhalt, dass neue Module angezeigt werden.
4. **Theme-Kompatibilität:** Wenn Sie ein stark angepasstes Theme verwenden, könnte es Standard-Produktseitenvorlagen überschreiben oder die notwendigen Hooks entfernen. Kontaktieren Sie Ihren Theme-Entwickler oder einen PrestaShop-Experten für Unterstützung.
5. **Browser-Probleme:** Versuchen Sie, den Cache und die Cookies Ihres Browsers zu leeren, oder testen Sie in einem Inkognito-Fenster.

**F: Wie moderiere ich die Kommentare?**
A: Wenn Sie eine Facebook App ID eingerichtet und diese in die Modulkonfiguration eingegeben haben, können Sie Kommentare direkt über die Facebook-Entwicklertools moderieren. Gehen Sie zu [developers.facebook.com/tools/comments](https://developers.facebook.com/tools/comments). Sie müssen mit dem Facebook-Konto angemeldet sein, das mit Ihrer App ID verknüpft ist.

**F: Kann ich das Styling (Farben, Schriftarten) des Facebook Kommentarfeldes ändern?**
A: Das Styling des Facebook Kommentare-Plugins wird größtenteils von Facebook selbst gesteuert, um ein konsistentes Markenerlebnis zu gewährleisten. Sie haben sehr begrenzte Kontrolle über dessen internes Erscheinungsbild. Sie können die Breite und Platzierung steuern, aber nicht das interne CSS.

**F: Wird Facebook Kommentare meine Website verlangsamen?**
A: Das Facebook Kommentare-Plugin lädt externe Skripte von Facebook. Obwohl Facebook diese optimiert, kann jedes externe Skript eine leichte Verzögerung beim Laden der Seite verursachen. Das Modul ist so konzipiert, dass diese Skripte effizient geladen werden. Sie können Tools wie Google PageSpeed Insights verwenden, um die Leistung Ihrer Website zu überwachen.

**F: Benötige ich eine Facebook Business-Seite, damit dieses Modul funktioniert?**
A: Nein, Sie benötigen nicht unbedingt eine Facebook Business-Seite. Wenn Sie jedoch die erweiterten Moderationstools nutzen möchten, benötigen Sie ein Facebook-Entwicklerkonto und müssen eine grundlegende Facebook App erstellen, die eine separate Entität von einer Business-Seite ist.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul Facebook Kommentare (`facebook-comments`) ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, das HTML und das JavaScript SDK des sozialen Plugins Facebook Kommentare in die Front-Office-Produktseiten zu injizieren. Es folgt einer Standard-PrestaShop-Modulstruktur, die Hooks zur Inhaltseinfügung und die `Configuration`-Klasse zur Speicherung von Einstellungen nutzt. Es führt keine benutzerdefinierten Controller, Modelle oder komplexe AJAX-Interaktionen ein.

### 4.2 Controller (`controllers/`)

- Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Dieses Modul enthält **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen. Die gesamte Logik ist in der Hauptdatei `facebook-comments.php` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

- Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Das Facebook JavaScript SDK wird direkt vom CDN von Facebook über die Modulvorlage geladen.

### 4.5 CSS-Stylesheets (`views/css/`)

- Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Das Styling des Facebook Kommentare-Plugins wird von den eigenen Stylesheets von Facebook gehandhabt.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Dieses Modul verwendet hauptsächlich eine einzelne Vorlagendatei, um das Facebook Kommentarfeld zu rendern.

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `facebook-comments.tpl`: Dies ist die Hauptvorlagendatei.
    - **Zweck:** Rendert das `div`-Element, das das JavaScript SDK von Facebook in das Kommentarfeld umwandelt. Es enthält auch den notwendigen JavaScript SDK-Initialisierungscode.
    - **Variablen:**
      - `{$facebook_app_id}`: Die Facebook App ID aus der Modulkonfiguration.
      - `{$facebook_comments_number}`: Die Anzahl der anzuzeigenden Kommentare.
      - `{$facebook_comments_width}`: Die Breite des Kommentarfeldes.
      - `{$facebook_comments_lang}`: Der Sprachcode für das Plugin.
      - `{$product_link}`: Die URL der aktuellen Produktseite, die von Facebook zur Identifizierung des Kommentar-Threads verwendet wird.
    - **Hooks:** Diese Vorlage wird über den in der Modulkonfiguration angegebenen Hook gerendert (z.B. `displayFooterProduct`).

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt **keine** benutzerdefinierten Datenbanktabellen. Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung der Standard-PrestaShop-Methoden `Configuration::get()` und `Configuration::updateValue()` gespeichert.

  - Konfigurationsschlüssel umfassen typischerweise:
    - `FACEBOOK_COMMENTS_APP_ID`
    - `FACEBOOK_COMMENTS_NUMBER`
    - `FACEBOOK_COMMENTS_WIDTH`
    - `FACEBOOK_COMMENTS_LANG`
    - `FACEBOOK_COMMENTS_POSITION`
    - `FACEBOOK_COMMENTS_ENABLED`
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um das Facebook JavaScript SDK einmal pro Seite einzubinden, um sicherzustellen, dass es verfügbar ist, bevor das Kommentarfeld gerendert wird. |
| `displayProductButtons` | In der Nähe des „In den Warenkorb“-Buttons auf Produktseiten. | Optionaler Hook zum Rendern des Kommentarfeldes, falls vom Händler konfiguriert. |
| `displayFooterProduct` | Am unteren Rand des Produktseiteninhalts. | Häufiger und empfohlener Hook zum Rendern des Kommentarfeldes, falls vom Händler konfiguriert. |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten. | Optionaler Hook zum Rendern des Kommentarfeldes, falls vom Händler konfiguriert. (Weniger üblich für Kommentare). |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten. | Optionaler Hook zum Rendern des Kommentarfeldes, falls vom Händler konfiguriert. (Weniger üblich für Kommentare). |
| `displayFooter` | Im Footer-Bereich des Shops. | Optionaler Hook zum Rendern des Kommentarfeldes, falls vom Händler konfiguriert. (Weniger üblich für produktspezifische Kommentare). |

Das Modul registriert sich dynamisch für den vom Händler in der Konfiguration gewählten Hook. Der `displayHeader`-Hook wird immer zum Laden des Facebook SDK verwendet.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul Facebook Kommentare, beziehen Sie sich bitte auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität des Moduls zur Verfügung.
