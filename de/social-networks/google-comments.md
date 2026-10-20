---
title: "Google+ Kommentare - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Google+ Kommentare von MyPresta.eu."
sidebar:
  label: "Google+ Kommentare - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Google+ Comments auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/google-comments.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/google-comments/)
>
> ---


# Google+ Kommentare

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul Google+ Kommentare. Hier finden Sie alle Einstellungen, um zu steuern, wie die Kommentare in Ihrem Shop erscheinen und funktionieren.

**Zugriff:** Navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Google+ Kommentare“ und klicken Sie auf **„Konfigurieren“**.

#### Einstellungen & Optionen

1. **Google+ Kommentare auf Produktseite anzeigen**

   - **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob der Google+ Kommentarbereich auf Ihren Produktseiten angezeigt wird.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (JA):* Der Google+ Kommentarbereich wird auf allen Ihren Produktseiten angezeigt, sodass Kunden Kommentare ansehen und hinzufügen können.
     - *Wenn deaktiviert (NEIN):* Der Google+ Kommentarbereich wird auf allen Produktseiten ausgeblendet.
   - **Empfohlener Wert:** JA (wenn Sie die Kommentarfunktion nutzen möchten).
   - **Händlerszenario / Beispiel:** Wenn Sie die Kundeninteraktion fördern und nutzergenerierte Inhalte nutzen möchten, aktivieren Sie dies. Wenn Sie ein anderes Kommentarsystem oder gar keine Kommentare bevorzugen, deaktivieren Sie es.
2. **Hook für Google+ Kommentare auswählen**

   - **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü ermöglicht es Ihnen, auszuwählen, wo auf der Produktseite (oder anderen Seiten) der Google+ Kommentarblock angezeigt werden soll. Hooks sind spezifische Orte in Ihrem PrestaShop-Theme, an denen Module Inhalte einfügen können.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Auswahl von `displayProductExtraContent` (oder einem ähnlichen Produktseiten-Hook):* Die Kommentare erscheinen im Hauptinhaltsbereich der Produktseite, typischerweise unterhalb der Produktbeschreibung oder der Tabs. Dies ist die häufigste und empfohlene Platzierung.
     - *Auswahl von `displayLeftColumn` oder `displayRightColumn`:* Der Kommentarblock erscheint in der linken oder rechten Seitenleiste Ihres Shops (sofern Ihr Theme diese hat und sie auf Produktseiten aktiv sind). Dies ist im Allgemeinen nicht ideal für einen vollständigen Kommentarbereich.
     - *Auswahl von `displayFooter`:* Der Kommentarblock erscheint im Footer-Bereich Ihres Shops. Auch dies ist nicht ideal für produktspezifische Kommentare.
   - **Empfohlener Wert:** `displayProductExtraContent` oder ein ähnlicher Hook, der die Kommentare direkt im Inhaltsbereich der Produktseite platziert. Der genaue Hook-Name kann je nach PrestaShop-Version oder Theme leicht variieren, aber zielen Sie auf einen ab, der sich gut in die Produktdetails integriert.
   - **Händlerszenario / Beispiel:** Sie möchten, dass die Kommentare leicht sichtbar sind, wenn ein Kunde ein Produkt überprüft. Die Auswahl von `displayProductExtraContent` stellt sicher, dass sie Teil des Hauptinformationsflusses des Produkts sind.
3. **Breite des Google+ Kommentarblocks (in Pixel)**

   - **Was diese Einstellung bewirkt:** Dieses Eingabefeld ermöglicht es Ihnen, die feste Breite des Google+ Kommentarbereichs in Pixeln zu definieren.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Festlegen eines spezifischen Pixelwerts (z.B. `600`):* Der Kommentarblock wird immer versuchen, in dieser genauen Breite gerendert zu werden. Wenn der Bildschirm kleiner ist, kann es zu Überläufen oder Layoutproblemen kommen.
     - *Leer lassen oder auf `100%` setzen (falls vom Modul erlaubt, obwohl typischerweise Pixel erwartet werden):* Das Modul könnte versuchen, sich automatisch anzupassen, aber für Google+ Kommentare wird oft eine feste Pixelbreite erwartet.
   - **Empfohlener Wert:** Ein Wert, der gut in den Hauptinhaltsbereich Ihrer Produktseite passt, typischerweise `600` bis `800` Pixel, abhängig vom Layout Ihres Themes. Möglicherweise müssen Sie experimentieren, um die beste Passform zu finden.
   - **Händlerszenario / Beispiel:** Der Inhaltsbereich Ihrer Produktseite ist 700px breit. Wenn Sie dies auf `650`px einstellen, passt der Kommentarblock gut, ohne das Layout zu zerstören.
4. **Anzahl der anzuzeigenden Kommentare**

   - **Was diese Einstellung bewirkt:** Dieses Eingabefeld steuert, wie viele Kommentare anfänglich im Google+ Kommentarbereich geladen und angezeigt werden. Weitere Kommentare können normalerweise vom Benutzer durch Klicken auf eine von Google bereitgestellte Schaltfläche „Mehr laden“ geladen werden.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Festlegen einer niedrigen Zahl (z.B. `5`):* Es werden zunächst nur wenige Kommentare angezeigt, wodurch die Seite schneller geladen wird und weniger überladen wirkt. Benutzer müssen klicken, um mehr zu sehen.
     - *Festlegen einer hohen Zahl (z.B. `20`):* Mehr Kommentare sind sofort sichtbar, was gut für stark kommentierte Produkte sein kann, aber die Seite länger machen könnte.
   - **Empfohlener Wert:** `5` bis `10`. Dies bietet ein gutes Gleichgewicht zwischen der Anzeige von Engagement und der Beibehaltung einer prägnanten Seite.
   - **Händlerszenario / Beispiel:** Sie haben viele Kommentare zu beliebten Produkten. Wenn Sie dies auf `7` einstellen, wird genügend Engagement angezeigt, ohne den Kunden mit einem sehr langen Scroll zu überfordern.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Google+ Kommentare auf Produktseite anzeigen | JA | Aktiviert/deaktiviert den Kommentarbereich auf Produktseiten. |
| Modulkonfiguration | Hook für Google+ Kommentare auswählen | `displayProductExtraContent` | Bestimmt, wo der Kommentarblock auf der Seite erscheint. |
| Modulkonfiguration | Breite des Google+ Kommentarblocks (in Pixel) | `600` - `800` | Legt die feste Breite des Kommentarbereichs fest. An Ihr Theme anpassen. |
| Modulkonfiguration | Anzahl der anzuzeigenden Kommentare | `5` - `10` | Steuert, wie viele Kommentare anfänglich sichtbar sind. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Kommentarbereich wird nach der Installation nicht auf meinen Produktseiten angezeigt.**
A:

1. **Modulkonfiguration prüfen:** Gehen Sie zu **Module > Modul-Manager > Google+ Kommentare > Konfigurieren**. Stellen Sie sicher, dass „Google+ Kommentare auf Produktseite anzeigen“ auf JA eingestellt ist.
2. **Hook-Auswahl überprüfen:** Stellen Sie sicher, dass „Hook für Google+ Kommentare auswählen“ auf einen relevanten Produktseiten-Hook wie `displayProductExtraContent` eingestellt ist. Wenn Ihr Theme einen benutzerdefinierten Hook für Produktinhalte verwendet, müssen Sie diesen möglicherweise auswählen oder Ihren Theme-Entwickler konsultieren.
3. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“). Manchmal verhindert der PrestaShop-Cache, dass neue Modulinhalte sofort angezeigt werden.
4. **Theme-Kompatibilität:** Einige stark angepasste Themes können Standard-PrestaShop-Hooks überschreiben. Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren Theme-Entwickler oder den MyPresta.eu-Support.

**F: Der Kommentarbereich sieht zu breit/schmal aus oder zerstört mein Layout.**
A:

1. **Breiteneinstellung anpassen:** Ändern Sie in der Modulkonfiguration die Einstellung „Breite des Google+ Kommentarblocks (in Pixel)“. Experimentieren Sie mit verschiedenen Werten (z.B. 600, 700, 800), bis es zu Ihrem Produktseiten-Layout passt.
2. **Theme-CSS prüfen:** Wenn das Anpassen der Breite nicht hilft, könnte das CSS Ihres Themes stören. Möglicherweise müssen Sie einen Webmaster beauftragen, das Element zu überprüfen und benutzerdefiniertes CSS zu Ihrem Theme hinzuzufügen, um eine korrekte Anzeige zu gewährleisten.

**F: Kann ich die Kommentare moderieren, bevor sie erscheinen?**
A: Das Modul Google+ Kommentare verwendet das eigene Kommentarsystem von Google. Moderationsfunktionen werden typischerweise innerhalb der Google-Plattform selbst gehandhabt, nicht direkt in PrestaShop. Sie müssten die Richtlinien und Tools von Google für die Kommentarmoderation im Zusammenhang mit eingebetteten Widgets überprüfen.

**F: Meine Kunden haben Probleme beim Posten von Kommentaren.**
A:

1. **Google-Konto-Anforderung:** Erinnern Sie Kunden daran, dass sie in einem Google-Konto angemeldet sein müssen, um Kommentare zu posten.
2. **Browser-Probleme:** Raten Sie Kunden, einen anderen Browser zu verwenden oder den Cache und die Cookies ihres Browsers zu löschen.
3. **Google-Dienststatus:** Gelegentlich können Google-Dienste vorübergehende Ausfälle haben. Überprüfen Sie die Statusseiten von Google, wenn viele Benutzer gleichzeitig Probleme melden.

**F: Funktioniert dieses Modul noch, da Google+ abgeschaltet wurde?**
A: Obwohl Google+ als soziales Netzwerk eingestellt wurde, bietet Google weiterhin eingebettete Kommentar-Widgets an, die Google-Konten nutzen. Dieses Modul integriert sich in diese zugrunde liegende Google-Kommentar-Infrastruktur. Es bietet möglicherweise nicht mehr den direkten „SEO-Boost“ durch „+1s“ wie früher, funktioniert aber immer noch als Google-gestütztes Kommentarsystem.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die mit dem Modul Google+ Kommentare arbeiten.

### 4.1 Architekturübersicht

Das Modul `Google+ Kommentare` ist ein einfaches PrestaShop-Modul, das hauptsächlich in seiner Haupt-PHP-Datei (`google-comments.php`) implementiert ist. Es nutzt die PrestaShop-Klasse `Module` und die Klasse `Configuration`, um Einstellungen zu verwalten. Seine Kernfunktionalität besteht darin, einen von Google bereitgestellten JavaScript-Snippet in das Front-Office einzufügen, der dann das Kommentar-Widget rendert. Es gibt keine benutzerdefinierten Controller, Modelle oder komplexen AJAX-Interaktionen innerhalb des Moduls selbst; es verlässt sich stark auf das externe Google-Skript für seine Front-End-Funktionalität.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Anzeige des Moduls wird durch das Einhaken in Standard-PrestaShop-Display-Hooks und das Rendern einer Smarty-Vorlage, die den Google-Kommentar-Einbettungscode enthält, gehandhabt.
- **Back-Office-Admin-Controller**: Keine. Alle Konfigurationen werden über die Methode `getContent()` in der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Alle Daten werden direkt in der PrestaShop-Tabelle `ps_configuration` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

- In diesem Modul sind keine benutzerdefinierten JavaScript-Dateien enthalten. Die Funktionalität des Moduls basiert vollständig auf der externen Google JavaScript-Bibliothek, die es einbettet.

### 4.5 CSS-Stylesheets (`views/css/`)

- In diesem Modul sind keine benutzerdefinierten CSS-Dateien enthalten. Das Styling des Google-Kommentar-Widgets wird durch Googles eigene eingebettete Stile gesteuert. Jede benutzerdefinierte Stilgebung müsste die generierten Google-Iframes/Elemente über Theme-Overrides ansprechen (was aufgrund von Cross-Domain-Iframe-Beschränkungen schwierig sein kann).

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Das Modul verwendet eine einzige Smarty-Vorlage, um das Google-Kommentar-Widget zu rendern.

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `googlecomments.tpl`: Diese Vorlage wird gerendert, wenn das Modul eingehakt ist. Sie enthält die HTML-Struktur für das Google-Kommentar-Widget, einschließlich des `<div>`-Elements mit den Attributen `data-href`, `data-width` und `data-num-comments` sowie des `script`-Tags zum Laden des Google Platform JavaScript SDK.
    - **Zweck:** Zum Einbetten des Google-Kommentar-Widgets im Front-Office.
    - **Verwendete Variablen:**
      - `{$link->getModuleLink('googlecomments', 'ajax', array(), true)|escape:'htmlall':'UTF-8'}`: Dies ist wahrscheinlich ein Überbleibsel oder Platzhalter, da das Modul keinen AJAX-Controller verwendet. Das Attribut `data-href` für Google-Kommentare verweist typischerweise auf die kanonische URL der Seite, auf der Kommentare angezeigt werden (z.B. die Produktseiten-URL).
      - `{Configuration::get('GOOGLE_COMMENTS_WIDTH')}`: Ruft die konfigurierte Breite für den Kommentarblock ab.
      - `{Configuration::get('GOOGLE_COMMENTS_NUM')}`: Ruft die konfigurierte Anzahl der anzuzeigenden Kommentare ab.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert:

  - `GOOGLE_COMMENTS_ENABLED`: Speichert `1` (aktiviert) oder `0` (deaktiviert) für die Anzeige von Kommentaren.
  - `GOOGLE_COMMENTS_HOOK`: Speichert den Namen des ausgewählten Hooks (z.B. `displayProductExtraContent`).
  - `GOOGLE_COMMENTS_WIDTH`: Speichert die Breite des Kommentarblocks in Pixeln.
  - `GOOGLE_COMMENTS_NUM`: Speichert die Anzahl der anzuzeigenden Kommentare.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um Assets zu registrieren (obwohl dieses Modul es dafür nicht verwendet, ist es ein gängiger Hook). |
| `displayProductExtraContent` | Innerhalb des Hauptinhaltsbereichs einer Produktseite, oft in einem Tab oder unter der Beschreibung. | **Primärer Hook zum Anzeigen des Kommentarblocks auf Produktseiten.** |
| `displayLeftColumn` | In der linken Seitenleiste des Shops. | Optionaler Hook zum Anzeigen des Kommentarblocks (weniger üblich für vollständige Kommentare). |
| `displayRightColumn` | In der rechten Seitenleiste des Shops. | Optionaler Hook zum Anzeigen des Kommentarblocks (weniger üblich für vollständige Kommentare). |
| `displayFooter` | Im Footer-Bereich des Shops. | Optionaler Hook zum Anzeigen des Kommentarblocks (weniger üblich für vollständige Kommentare). |
| `actionFrontControllerSetMedia` | Bevor der Front-Controller die Seite rendert, ermöglicht Modulen das Hinzufügen von JS/CSS. | Wird verwendet, um das Google Platform JavaScript SDK zur Seite hinzuzufügen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul Google+ Kommentare, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, Unterstützung zu leisten und den reibungslosen Betrieb Ihrer Module zu gewährleisten.
